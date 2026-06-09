# TransportManager::Start(void)

- ea: `0x180004ad8`
- end: `0x180004b8d`
- name: `?Start@TransportManager@@QEAAJXZ`
- size: `181`
- prototype: `__int64 __fastcall(TransportManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180003090`

## callees

- `0x18000108c`
- `0x1800044dc`
- `0x180004ad8`
- `0x1800051cc`
- `0x18000aa50`
- `0x18000c010`

## string_xrefs

- `0x180004b10`: `onecoreuap\net\messaging\desktoptransport\service\transportmanager.cpp`

## pseudocode

```c
__int64 __fastcall TransportManager::Start(TransportManager *this)
{
  int started; // ebx
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-38h] BYREF

  started = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 24LL))(*((_QWORD *)this + 6));
  if ( started < 0 || (started = TransportManager::_StartIdleTimer(this), started < 0) )
  {
    Log_HREvent_0(
      (unsigned int)started,
      1,
      "onecoreuap\\net\\messaging\\desktoptransport\\service\\transportmanager.cpp");
    return (unsigned int)started;
  }
  else
  {
    if ( (unsigned int)dword_180013018 > 4 )
      tlgWriteTransfer_EventWriteTransfer((int)&dword_180013018, (int)&byte_18001026F, 0, 0, 2u, &v4);
    return 0;
  }
}

```

## disassembly

```asm
0x180004ad8  mov     [rsp+arg_8], rbx
0x180004add  push    rdi
0x180004ade  sub     rsp, 60h
0x180004ae2  mov     rax, cs:__security_cookie
0x180004ae9  xor     rax, rsp
0x180004aec  mov     [rsp+68h+var_18], rax
0x180004af1  mov     rdi, rcx
0x180004af4  mov     rcx, [rcx+30h]
0x180004af8  mov     rax, [rcx]
0x180004afb  mov     rax, [rax+18h]
0x180004aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b04  mov     ebx, eax
0x180004b06  test    eax, eax
0x180004b08  jns     short loc_180004B27
0x180004b0a  mov     r9d, 30h ; '0'
0x180004b10  lea     r8, aOnecoreuapNetM_6; "onecoreuap\\net\\messaging\\desktoptran"...
0x180004b17  mov     edx, 1
0x180004b1c  mov     ecx, ebx
0x180004b1e  call    Log_HREvent_0
0x180004b23  mov     eax, ebx
0x180004b25  jmp     short loc_180004B75
0x180004b27  mov     rcx, rdi; this
0x180004b2a  call    ?_StartIdleTimer@TransportManager@@AEAAJXZ; TransportManager::_StartIdleTimer(void)
0x180004b2f  mov     ebx, eax
0x180004b31  test    eax, eax
0x180004b33  jns     short loc_180004B3D
0x180004b35  mov     r9d, 32h ; '2'
0x180004b3b  jmp     short loc_180004B10
0x180004b3d  mov     eax, cs:dword_180013018
0x180004b43  cmp     eax, 4
0x180004b46  jbe     short loc_180004B73
0x180004b48  lea     rax, [rsp+68h+var_38]
0x180004b4d  xor     r9d, r9d; int
0x180004b50  mov     [rsp+68h+var_40], rax; PEVENT_DATA_DESCRIPTOR
0x180004b55  lea     rdx, byte_18001026F; int
0x180004b5c  xor     r8d, r8d; int
0x180004b5f  mov     [rsp+68h+var_48], 2; ULONG
0x180004b67  lea     rcx, dword_180013018; int
0x180004b6e  call    _tlgWriteTransfer_EventWriteTransfer
0x180004b73  xor     eax, eax
0x180004b75  mov     rcx, [rsp+68h+var_18]
0x180004b7a  xor     rcx, rsp; StackCookie
0x180004b7d  call    __security_check_cookie
0x180004b82  mov     rbx, [rsp+68h+arg_8]
0x180004b87  add     rsp, 60h
0x180004b8b  pop     rdi
0x180004b8c  retn
```
