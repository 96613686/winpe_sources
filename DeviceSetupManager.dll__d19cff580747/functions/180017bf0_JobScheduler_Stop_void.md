# JobScheduler::Stop(void)

- ea: `0x180017bf0`
- end: `0x180017d5c`
- name: `?Stop@JobScheduler@@QEAAJXZ`
- size: `364`
- prototype: `__int64 __fastcall(JobScheduler *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x1800240dc`

## callees

- `0x1800151d4`
- `0x180017bf0`
- `0x180017d64`
- `0x180017d90`
- `0x180021790`
- `0x18002b980`

## import_xrefs

- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180017c88`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180017c88`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180017c73`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180017c73`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180017c58`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180017c58`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall JobScheduler::Stop(JobScheduler *this, void *a2)
{
  bool v3; // al
  void *v4; // rdx
  void *v5; // rdx
  void *v6; // rdx
  const char *v7; // r9
  __int64 result; // rax
  __int128 v9; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_4a19ff13275d346bcbd49403e9cec97f_Traceguids);
  }
  wil::details::SetEvent(*((wil::details **)this + 71), a2);
  wil::slim_event_t<1>::wait((char *)this + 544);
  v3 = __ExceptionPtrToBool((char *)this + 552);
  try
  {
    if ( v3 )
    {
      v9 = 0;
      __ExceptionPtrCopy(&v9, (char *)this + 552);
      __ExceptionPtrRethrow(&v9);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_4a19ff13275d346bcbd49403e9cec97f_Traceguids);
    }
    wil::details::SetEvent(*(wil::details **)(*((_QWORD *)this + 14) + 120LL), v4);
    wil::details::SetEvent(*(wil::details **)(*((_QWORD *)this + 32) + 120LL), v5);
    wil::details::SetEvent(*(wil::details **)(*((_QWORD *)this + 50) + 120LL), v6);
    ContainerManager::CancelAllJobs(*((PSRWLOCK *)this + 57));
    wil::slim_event_t<0>::wait((char *)this + 120);
    wil::slim_event_t<0>::wait((char *)this + 264);
    wil::slim_event_t<0>::wait((char *)this + 408);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_4a19ff13275d346bcbd49403e9cec97f_Traceguids);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x6F,
                           (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\scheduler.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x180017bf0  mov     [rsp+arg_8], rbx
0x180017bf5  mov     [rsp+arg_10], rsi
0x180017bfa  push    rdi
0x180017bfb  sub     rsp, 30h
0x180017bff  mov     rbx, rcx
0x180017c02  lea     rsi, WPP_GLOBAL_Control
0x180017c09  mov     rcx, cs:WPP_GLOBAL_Control
0x180017c10  cmp     rcx, rsi
0x180017c13  jz      short loc_180017C36
0x180017c15  test    byte ptr [rcx+1Ch], 80h
0x180017c19  jz      short loc_180017C36
0x180017c1b  cmp     byte ptr [rcx+19h], 4
0x180017c1f  jb      short loc_180017C36
0x180017c21  mov     edx, 10h
0x180017c26  lea     r8, WPP_4a19ff13275d346bcbd49403e9cec97f_Traceguids
0x180017c2d  mov     rcx, [rcx+10h]
0x180017c31  call    WPP_SF_
0x180017c36  mov     rcx, [rbx+238h]; this
0x180017c3d  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x180017c42  lea     rcx, [rbx+220h]
0x180017c49  call    ?wait@?$slim_event_t@$00@wil@@QEAA_NXZ; wil::slim_event_t<1>::wait(void)
0x180017c4e  lea     rdi, [rbx+228h]
0x180017c55  mov     rcx, rdi
0x180017c58  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180017c5e  test    al, al
0x180017c60  jz      short loc_180017C8F
0x180017c62  xorps   xmm0, xmm0
0x180017c65  movdqu  [rsp+38h+var_18], xmm0
0x180017c6b  mov     rdx, rdi
0x180017c6e  lea     rcx, [rsp+38h+var_18]
0x180017c73  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180017c79  lea     rax, [rsp+38h+var_18]
0x180017c7e  mov     [rsp+38h+arg_0], rax
0x180017c83  lea     rcx, [rsp+38h+var_18]
0x180017c88  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x180017c8e  nop
0x180017c8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180017c96  cmp     rcx, rsi
0x180017c99  jz      short loc_180017CBC
0x180017c9b  test    byte ptr [rcx+1Ch], 80h
0x180017c9f  jz      short loc_180017CBC
0x180017ca1  cmp     byte ptr [rcx+19h], 4
0x180017ca5  jb      short loc_180017CBC
0x180017ca7  mov     edx, 11h
0x180017cac  lea     r8, WPP_4a19ff13275d346bcbd49403e9cec97f_Traceguids
0x180017cb3  mov     rcx, [rcx+10h]
0x180017cb7  call    WPP_SF_
0x180017cbc  mov     rcx, [rbx+70h]
0x180017cc0  mov     rcx, [rcx+78h]; this
0x180017cc4  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x180017cc9  mov     rcx, [rbx+100h]
0x180017cd0  mov     rcx, [rcx+78h]; this
0x180017cd4  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x180017cd9  mov     rcx, [rbx+190h]
0x180017ce0  mov     rcx, [rcx+78h]; this
0x180017ce4  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x180017ce9  mov     rcx, [rbx+1C8h]; SRWLock
0x180017cf0  call    ?CancelAllJobs@ContainerManager@@QEAAJXZ; ContainerManager::CancelAllJobs(void)
0x180017cf5  lea     rcx, [rbx+78h]
0x180017cf9  call    ?wait@?$slim_event_t@$0A@@wil@@QEAA_NXZ; wil::slim_event_t<0>::wait(void)
0x180017cfe  lea     rcx, [rbx+108h]
0x180017d05  call    ?wait@?$slim_event_t@$0A@@wil@@QEAA_NXZ; wil::slim_event_t<0>::wait(void)
0x180017d0a  lea     rcx, [rbx+198h]
0x180017d11  call    ?wait@?$slim_event_t@$0A@@wil@@QEAA_NXZ; wil::slim_event_t<0>::wait(void)
0x180017d16  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d1d  cmp     rcx, rsi
0x180017d20  jz      short loc_180017D43
0x180017d22  test    byte ptr [rcx+1Ch], 80h
0x180017d26  jz      short loc_180017D43
0x180017d28  cmp     byte ptr [rcx+19h], 4
0x180017d2c  jb      short loc_180017D43
0x180017d2e  mov     edx, 12h
0x180017d33  lea     r8, WPP_4a19ff13275d346bcbd49403e9cec97f_Traceguids
0x180017d3a  mov     rcx, [rcx+10h]
0x180017d3e  call    WPP_SF_
0x180017d43  xor     eax, eax
0x180017d45  jmp     short loc_180017D4B
0x180017d47  mov     eax, dword ptr [rsp+38h+arg_0]
0x180017d4b  mov     rbx, [rsp+38h+arg_8]
0x180017d50  mov     rsi, [rsp+38h+arg_10]
0x180017d55  add     rsp, 30h
0x180017d59  pop     rdi
0x180017d5a  retn
```
