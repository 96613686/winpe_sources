# Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSyncController::CreateFlushEvent(uint,unsigned __int64 &)

- ea: `0x180029228`
- end: `0x1800293a7`
- name: `?CreateFlushEvent@EtwCollectionSyncController@StandardCollector@DiagnosticsHub@Microsoft@@IEAAJIAEA_K@Z`
- size: `383`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSyncController *__hidden this, unsigned int, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001e1b0`

## callees

- `0x180029228`
- `0x18003d864`
- `0x180049b50`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1800292fc`
- `KERNEL32!SetEvent` at `0x1800292fc`
- `KERNEL32!ResetEvent` at `0x1800292e2`
- `KERNEL32!ResetEvent` at `0x1800292e2`
- `ADVAPI32!EventWrite` at `0x180029353`
- `ADVAPI32!EventWrite` at `0x180029353`

## pseudocode

```c
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSyncController::CreateFlushEvent(
        Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSyncController *this,
        int a2,
        unsigned __int64 *a3)
{
  signed __int64 v6; // rax
  __int64 v7; // rdi
  int v8; // r9d
  __int64 result; // rax
  REGHANDLE v10; // rcx
  signed int v11; // esi
  unsigned __int64 v12; // [rsp+20h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+28h] [rbp-30h] BYREF

  v6 = _InterlockedExchangeAdd64(
         &Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSyncController::s_FlushIdCounter,
         1u);
  v12 = v6 + 1;
  v7 = 3LL * (((_DWORD)v6 + 1) & 0x1F);
  v8 = *((_DWORD *)this + 6 * (((int)v6 + 1) & 0x1F) + 6);
  if ( v8 < 0 )
  {
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 168),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSyncController.cpp",
      L"Event creation failed. HRESULT: %#08x");
    return 2147549183LL;
  }
  if ( *((_DWORD *)this + 6 * (((int)v6 + 1) & 0x1F) + 2) )
  {
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 168),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSyncController.cpp",
      L"Flush event consumption has exceeded expected usage velocity.");
    return 3775987734LL;
  }
  *((_DWORD *)this + 6 * (((int)v6 + 1) & 0x1F) + 2) = a2;
  if ( v8 >= 0 )
    ResetEvent(*((HANDLE *)this + 3 * (((int)v6 + 1) & 0x1F) + 2));
  if ( !a2 )
  {
    if ( *((int *)this + 2 * v7 + 6) >= 0 )
      SetEvent(*((HANDLE *)this + v7 + 2));
    goto LABEL_10;
  }
  v10 = *((_QWORD *)this + 195);
  UserData.Ptr = (ULONGLONG)&v12;
  *(_QWORD *)&UserData.Size = 8;
  v11 = EventWrite(
          v10,
          &Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSyncController::FlushEventDescriptor,
          1u,
          &UserData);
  if ( !v11 )
  {
LABEL_10:
    *a3 = v12;
    return 0;
  }
  DiagHubCommon::LogStream::Write(
    (DiagHubCommon::LogStream *)((char *)_logger + 168),
    L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSyncController.cpp",
    L"Failed to emit flush event for ID: %llu",
    v12);
  result = (unsigned __int16)v11 | 0x80070000;
  *a3 = v12;
  *((_DWORD *)this + 2 * v7 + 2) = 0;
  if ( v11 <= 0 )
    return (unsigned int)v11;
  return result;
}

```

## disassembly

```asm
0x180029228  mov     [rsp+arg_8], rbx
0x18002922d  push    rsi
0x18002922e  push    rdi
0x18002922f  push    r14
0x180029231  sub     rsp, 40h
0x180029235  mov     rax, cs:__security_cookie
0x18002923c  xor     rax, rsp
0x18002923f  mov     [rsp+58h+var_20], rax
0x180029244  mov     r14, r8
0x180029247  mov     esi, edx
0x180029249  mov     rbx, rcx
0x18002924c  mov     eax, 1
0x180029251  lock xadd cs:?s_FlushIdCounter@EtwCollectionSyncController@StandardCollector@DiagnosticsHub@Microsoft@@0_JA, rax; __int64 Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSyncController::s_FlushIdCounter
0x18002925a  inc     rax
0x18002925d  mov     [rsp+58h+var_38], rax
0x180029262  and     eax, 1Fh
0x180029265  lea     rdi, [rax+rax*2]
0x180029269  mov     r9d, [rcx+rdi*8+18h]
0x18002926e  mov     eax, r9d
0x180029271  shr     eax, 1Fh
0x180029274  test    al, al
0x180029276  jz      short loc_1800292A0
0x180029278  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18002927f  lea     r8, aEventCreationF; "Event creation failed. HRESULT: %#08x"
0x180029286  add     rcx, 0A8h; this
0x18002928d  lea     rdx, aDAWork1SSource_13; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180029294  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180029299  mov     eax, 8000FFFFh
0x18002929e  jmp     short loc_18002930C
0x1800292a0  cmp     dword ptr [rcx+rdi*8+8], 0
0x1800292a5  jz      short loc_1800292CF
0x1800292a7  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x1800292ae  lea     r8, aFlushEventCons; "Flush event consumption has exceeded ex"...
0x1800292b5  add     rcx, 0A8h; this
0x1800292bc  lea     rdx, aDAWork1SSource_13; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x1800292c3  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x1800292c8  mov     eax, 0E1110016h
0x1800292cd  jmp     short loc_18002930C
0x1800292cf  mov     eax, r9d
0x1800292d2  mov     [rcx+rdi*8+8], esi
0x1800292d6  shr     eax, 1Fh
0x1800292d9  test    al, al
0x1800292db  jnz     short loc_1800292E8
0x1800292dd  mov     rcx, [rcx+rdi*8+10h]; hEvent
0x1800292e2  call    cs:__imp_ResetEvent
0x1800292e8  test    esi, esi
0x1800292ea  jnz     short loc_180029327
0x1800292ec  mov     eax, [rbx+rdi*8+18h]
0x1800292f0  shr     eax, 1Fh
0x1800292f3  test    al, al
0x1800292f5  jnz     short loc_180029302
0x1800292f7  mov     rcx, [rbx+rdi*8+10h]; hEvent
0x1800292fc  call    cs:__imp_SetEvent
0x180029302  mov     rax, [rsp+58h+var_38]
0x180029307  mov     [r14], rax
0x18002930a  xor     eax, eax
0x18002930c  mov     rcx, [rsp+58h+var_20]
0x180029311  xor     rcx, rsp; StackCookie
0x180029314  call    __security_check_cookie
0x180029319  mov     rbx, [rsp+58h+arg_8]
0x18002931e  add     rsp, 40h
0x180029322  pop     r14
0x180029324  pop     rdi
0x180029325  pop     rsi
0x180029326  retn
0x180029327  mov     rcx, [rbx+618h]; RegHandle
0x18002932e  lea     rax, [rsp+58h+var_38]
0x180029333  lea     r9, [rsp+58h+UserData]; UserData
0x180029338  mov     [rsp+58h+UserData.Ptr], rax
0x18002933d  mov     r8d, 1; UserDataCount
0x180029343  mov     qword ptr [rsp+58h+UserData.Size], 8
0x18002934c  lea     rdx, ?FlushEventDescriptor@EtwCollectionSyncController@StandardCollector@DiagnosticsHub@Microsoft@@1U_EVENT_DESCRIPTOR@@B; EventDescriptor
0x180029353  call    cs:__imp_EventWrite
0x180029359  mov     esi, eax
0x18002935b  test    eax, eax
0x18002935d  jz      short loc_180029302
0x18002935f  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180029366  lea     r8, aFailedToEmitFl; "Failed to emit flush event for ID: %llu"
0x18002936d  mov     r9, [rsp+58h+var_38]
0x180029372  lea     rdx, aDAWork1SSource_13; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180029379  add     rcx, 0A8h; this
0x180029380  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180029385  mov     rcx, [rsp+58h+var_38]
0x18002938a  movzx   eax, si
0x18002938d  or      eax, 80070000h
0x180029392  mov     [r14], rcx
0x180029395  test    esi, esi
0x180029397  mov     dword ptr [rbx+rdi*8+8], 0
0x18002939f  cmovle  eax, esi
0x1800293a2  jmp     loc_18002930C
```
