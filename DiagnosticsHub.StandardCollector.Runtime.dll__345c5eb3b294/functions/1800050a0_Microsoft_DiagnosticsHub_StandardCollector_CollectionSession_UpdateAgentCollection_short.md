# Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::UpdateAgentCollection(short)

- ea: `0x1800050a0`
- end: `0x1800051b2`
- name: `?UpdateAgentCollection@CollectionSession@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJF@Z`
- size: `274`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::CollectionSession *__hidden this, __int16)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180004fe0`
- `0x1800051c0`

## callees

- `0x1800050a0`
- `0x18003d864`
- `0x18004b640`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180005195`
- `KERNEL32!LeaveCriticalSection` at `0x180005195`
- `KERNEL32!EnterCriticalSection` at `0x1800050cf`
- `KERNEL32!EnterCriticalSection` at `0x1800050cf`

## string_xrefs

- `0x180005129`: `Removing IStandardCollectorPausableAgent - event callback failed with %#08x`
- `0x180005176`: `Removing IStandardCollectorPausableAgent - event callback failed with %#08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::UpdateAgentCollection(
        Microsoft::DiagnosticsHub::StandardCollector::CollectionSession *this,
        __int16 a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  __int64 v5; // rax
  _QWORD *v6; // rdi
  _QWORD *v7; // rsi
  int v8; // eax
  int v9; // eax

  v4 = (struct _RTL_CRITICAL_SECTION *)(*((_QWORD *)this + 31) + 568LL);
  EnterCriticalSection(v4);
  v5 = *((_QWORD *)this + 31);
  v6 = *(_QWORD **)(v5 + 608);
  v7 = *(_QWORD **)(v5 + 616);
  if ( v6 != v7 )
  {
    if ( a2 == -1 )
    {
      do
      {
        if ( !*((_BYTE *)v6 + 8) )
        {
          v8 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 40LL))(*v6);
          if ( v8 < 0 )
          {
            _mm_lfence();
            *((_BYTE *)v6 + 8) = 1;
            DiagHubCommon::LogStream::Write(
              (DiagHubCommon::LogStream *)((char *)_logger + 56),
              L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\CollectionSessions.cpp",
              L"Removing IStandardCollectorPausableAgent - event callback failed with %#08x",
              (unsigned int)v8);
          }
        }
        v6 += 2;
      }
      while ( v6 != v7 );
    }
    else
    {
      do
      {
        if ( !*((_BYTE *)v6 + 8) )
        {
          v9 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 48LL))(*v6);
          if ( v9 < 0 )
          {
            _mm_lfence();
            *((_BYTE *)v6 + 8) = 1;
            DiagHubCommon::LogStream::Write(
              (DiagHubCommon::LogStream *)((char *)_logger + 56),
              L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\CollectionSessions.cpp",
              L"Removing IStandardCollectorPausableAgent - event callback failed with %#08x",
              (unsigned int)v9);
          }
        }
        v6 += 2;
      }
      while ( v6 != v7 );
    }
  }
  LeaveCriticalSection(v4);
  return 0;
}

```

## disassembly

```asm
0x1800050a0  mov     rax, rsp
0x1800050a3  mov     [rax+10h], rbx
0x1800050a7  mov     [rax+18h], rbp
0x1800050ab  mov     [rax+20h], rsi
0x1800050af  push    rdi
0x1800050b0  sub     rsp, 20h
0x1800050b4  movzx   ebp, dx
0x1800050b7  mov     rdi, rcx
0x1800050ba  mov     rbx, [rcx+0F8h]
0x1800050c1  add     rbx, 238h
0x1800050c8  mov     [rax+8], rbx
0x1800050cc  mov     rcx, rbx; lpCriticalSection
0x1800050cf  call    cs:__imp_EnterCriticalSection
0x1800050d5  nop
0x1800050d6  mov     rax, [rdi+0F8h]
0x1800050dd  mov     rdi, [rax+260h]
0x1800050e4  mov     rsi, [rax+268h]
0x1800050eb  cmp     rdi, rsi
0x1800050ee  jz      loc_180005192
0x1800050f4  cmp     bp, 0FFFFh
0x1800050f8  jnz     short loc_180005147
0x1800050fa  cmp     byte ptr [rdi+8], 0
0x1800050fe  jnz     short loc_18000513C
0x180005100  mov     rcx, [rdi]
0x180005103  mov     rax, [rcx]
0x180005106  mov     rax, [rax+28h]
0x18000510a  call    cs:__guard_dispatch_icall_fptr
0x180005110  test    eax, eax
0x180005112  jns     short loc_18000513C
0x180005114  lfence
0x180005117  mov     byte ptr [rdi+8], 1
0x18000511b  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180005122  add     rcx, 38h ; '8'; this
0x180005126  mov     r9d, eax
0x180005129  lea     r8, aRemovingIstand; "Removing IStandardCollectorPausableAgen"...
0x180005130  lea     rdx, aDAWork1SSource_9; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180005137  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18000513c  add     rdi, 10h
0x180005140  cmp     rdi, rsi
0x180005143  jnz     short loc_1800050FA
0x180005145  jmp     short loc_180005192
0x180005147  cmp     byte ptr [rdi+8], 0
0x18000514b  jnz     short loc_180005189
0x18000514d  mov     rcx, [rdi]
0x180005150  mov     rax, [rcx]
0x180005153  mov     rax, [rax+30h]
0x180005157  call    cs:__guard_dispatch_icall_fptr
0x18000515d  test    eax, eax
0x18000515f  jns     short loc_180005189
0x180005161  lfence
0x180005164  mov     byte ptr [rdi+8], 1
0x180005168  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18000516f  add     rcx, 38h ; '8'; this
0x180005173  mov     r9d, eax
0x180005176  lea     r8, aRemovingIstand; "Removing IStandardCollectorPausableAgen"...
0x18000517d  lea     rdx, aDAWork1SSource_9; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180005184  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180005189  add     rdi, 10h
0x18000518d  cmp     rdi, rsi
0x180005190  jnz     short loc_180005147
0x180005192  mov     rcx, rbx; lpCriticalSection
0x180005195  call    cs:__imp_LeaveCriticalSection
0x18000519b  xor     eax, eax
0x18000519d  mov     rbx, [rsp+28h+arg_8]
0x1800051a2  mov     rbp, [rsp+28h+arg_10]
0x1800051a7  mov     rsi, [rsp+28h+arg_18]
0x1800051ac  add     rsp, 20h
0x1800051b0  pop     rdi
0x1800051b1  retn
```
