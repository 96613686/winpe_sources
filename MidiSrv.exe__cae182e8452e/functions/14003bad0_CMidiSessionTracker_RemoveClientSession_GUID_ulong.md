# CMidiSessionTracker::RemoveClientSession(_GUID,ulong)

- ea: `0x14003bad0`
- end: `0x14003bc0c`
- name: `?RemoveClientSession@CMidiSessionTracker@@UEAAJU_GUID@@K@Z`
- size: `316`
- prototype: `__int64 __fastcall(CMidiSessionTracker *__hidden this, struct _GUID *__struct_ptr, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x14000179c`
- `0x1400054c0`
- `0x14000984c`
- `0x14000a6b4`
- `0x14003a5e0`
- `0x14003bad0`
- `0x14003c664`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003bbbb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003bbea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003bbbb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003bbea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003bb7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003bb7b`

## string_xrefs

- `0x14003bbc9`: `avcore\midi2\service\exe\midisessiontracker.cpp`
- `0x14003bb2c`: `CMidiSessionTracker::RemoveClientSession`

## pseudocode

```c
__int64 __fastcall CMidiSessionTracker::RemoveClientSession(
        CMidiSessionTracker *this,
        struct _GUID *a2,
        unsigned int a3)
{
  _DWORD *v6; // rcx
  int v8; // [rsp+20h] [rbp-69h]
  CMidiSessionTracker *v9; // [rsp+30h] [rbp-59h] BYREF
  unsigned int v10; // [rsp+38h] [rbp-51h] BYREF
  struct _GUID v11; // [rsp+40h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+50h] [rbp-39h] BYREF
  const char *v13; // [rsp+70h] [rbp-19h]
  __int64 v14; // [rsp+78h] [rbp-11h]
  CMidiSessionTracker **v15; // [rsp+80h] [rbp-9h]
  __int64 v16; // [rsp+88h] [rbp-1h]
  struct _GUID *v17; // [rsp+90h] [rbp+7h]
  __int64 v18; // [rsp+98h] [rbp+Fh]
  int *v19; // [rsp+A0h] [rbp+17h]
  __int64 v20; // [rsp+A8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v6 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v6 > 4u )
  {
    v10 = a3;
    v19 = (int *)&v10;
    v9 = this;
    v15 = &v9;
    v20 = 4;
    v13 = "CMidiSessionTracker::RemoveClientSession";
    v17 = a2;
    v18 = 16;
    v16 = 8;
    v14 = 41;
    tlgWriteTransfer_EventWriteTransfer((__int64)v6, (unsigned __int8 *)&word_14008AF0E, 0, 0, 6u, &v12);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v11 = *a2;
  CMidiSessionTracker::FindSession(this, &v9, &v11, a3);
  if ( v9 == *((CMidiSessionTracker **)this + 4) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14D,
      (unsigned int)"avcore\\midi2\\service\\exe\\midisessiontracker.cpp",
      (const char *)0x80070057LL,
      v8);
    if ( this != (CMidiSessionTracker *)-48LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    return 2147942487LL;
  }
  else
  {
    std::vector<MidiSessionEntry>::erase((char *)this + 24, &v9, v9);
    if ( this != (CMidiSessionTracker *)-48LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    return 0;
  }
}

```

## disassembly

```asm
0x14003bad0  push    rbp
0x14003bad2  push    rbx
0x14003bad3  push    rsi
0x14003bad4  push    rdi
0x14003bad5  push    r14
0x14003bad7  lea     rbp, [rsp-37h]
0x14003badc  sub     rsp, 0C0h
0x14003bae3  mov     rax, cs:__security_cookie
0x14003baea  xor     rax, rsp
0x14003baed  mov     [rbp+57h+var_30], rax
0x14003baf1  mov     r14d, r8d
0x14003baf4  mov     rsi, rdx
0x14003baf7  mov     rdi, rcx
0x14003bafa  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003baff  mov     rcx, [rax+8]
0x14003bb03  mov     eax, [rcx]
0x14003bb05  cmp     eax, 4
0x14003bb08  jbe     short loc_14003BB74
0x14003bb0a  lea     rax, [rbp+57h+var_A8]
0x14003bb0e  mov     [rbp+57h+var_A8], r14d
0x14003bb12  mov     [rbp+57h+var_40], rax
0x14003bb16  lea     rdx, word_14008AF0E
0x14003bb1d  lea     rax, [rbp+57h+var_B0]
0x14003bb21  mov     [rbp+57h+var_B0], rdi
0x14003bb25  mov     [rbp+57h+var_60], rax
0x14003bb29  xor     r9d, r9d
0x14003bb2c  lea     rax, aCmidisessiontr_9; "CMidiSessionTracker::RemoveClientSessio"...
0x14003bb33  mov     [rbp+57h+var_38], 4
0x14003bb3b  mov     [rbp+57h+var_70], rax
0x14003bb3f  xor     r8d, r8d
0x14003bb42  lea     rax, [rbp+57h+var_90]
0x14003bb46  mov     [rbp+57h+var_50], rsi
0x14003bb4a  mov     [rsp+0E0h+var_B8], rax
0x14003bb4f  mov     [rsp+0E0h+var_C0], 6; int
0x14003bb57  mov     [rbp+57h+var_48], 10h
0x14003bb5f  mov     [rbp+57h+var_58], 8
0x14003bb67  mov     [rbp+57h+var_68], 29h ; ')'
0x14003bb6f  call    _tlgWriteTransfer_EventWriteTransfer
0x14003bb74  lea     rbx, [rdi+30h]
0x14003bb78  mov     rcx, rbx; lpCriticalSection
0x14003bb7b  call    cs:__imp_EnterCriticalSection
0x14003bb81  movups  xmm0, xmmword ptr [rsi]
0x14003bb84  mov     r9d, r14d
0x14003bb87  lea     r8, [rbp+57h+var_A0]
0x14003bb8b  lea     rdx, [rbp+57h+var_B0]
0x14003bb8f  mov     rcx, rdi
0x14003bb92  movdqu  [rbp+57h+var_A0], xmm0
0x14003bb97  call    ?FindSession@CMidiSessionTracker@@AEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UMidiSessionEntry@@@std@@@std@@@std@@U_GUID@@K@Z; CMidiSessionTracker::FindSession(_GUID,ulong)
0x14003bb9c  mov     r8, [rbp+57h+var_B0]
0x14003bba0  lea     rcx, [rdi+18h]
0x14003bba4  cmp     r8, [rcx+8]
0x14003bba8  jz      short loc_14003BBC5
0x14003bbaa  lea     rdx, [rbp+57h+var_B0]
0x14003bbae  call    ?erase@?$vector@UMidiSessionEntry@@V?$allocator@UMidiSessionEntry@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UMidiSessionEntry@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UMidiSessionEntry@@@std@@@std@@@2@@Z; std::vector<MidiSessionEntry>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<MidiSessionEntry>>>)
0x14003bbb3  test    rbx, rbx
0x14003bbb6  jz      short loc_14003BBC1
0x14003bbb8  mov     rcx, rbx; lpCriticalSection
0x14003bbbb  call    cs:__imp_LeaveCriticalSection
0x14003bbc1  xor     eax, eax
0x14003bbc3  jmp     short loc_14003BBF2
0x14003bbc5  mov     rcx, [rbp+5Fh]; this
0x14003bbc9  lea     r8, aAvcoreMidi2Ser_5; "avcore\\midi2\\service\\exe\\midisessio"...
0x14003bbd0  mov     edi, 80070057h
0x14003bbd5  mov     edx, 14Dh; void *
0x14003bbda  mov     r9d, edi; char *
0x14003bbdd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003bbe2  test    rbx, rbx
0x14003bbe5  jz      short loc_14003BBF0
0x14003bbe7  mov     rcx, rbx; lpCriticalSection
0x14003bbea  call    cs:__imp_LeaveCriticalSection
0x14003bbf0  mov     eax, edi
0x14003bbf2  mov     rcx, [rbp+57h+var_30]
0x14003bbf6  xor     rcx, rsp; StackCookie
0x14003bbf9  call    __security_check_cookie
0x14003bbfe  add     rsp, 0C0h
0x14003bc05  pop     r14
0x14003bc07  pop     rdi
0x14003bc08  pop     rsi
0x14003bc09  pop     rbx
0x14003bc0a  pop     rbp
0x14003bc0b  retn
```
