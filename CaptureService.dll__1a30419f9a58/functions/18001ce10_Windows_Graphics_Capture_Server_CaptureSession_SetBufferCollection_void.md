# Windows::Graphics::Capture::Server::CaptureSession::SetBufferCollection(void *)

- ea: `0x18001ce10`
- end: `0x18001cea2`
- name: `?SetBufferCollection@CaptureSession@Server@Capture@Graphics@Windows@@UEAAJPEAX@Z`
- size: `146`
- prototype: `int(Windows::Graphics::Capture::Server::CaptureSession *__hidden this, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005568`
- `0x18000907c`
- `0x18001ce10`
- `0x18001fcac`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ce2c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ce2c`

## string_xrefs

- `0x18001ce6e`: `onecoreuap\windows\dwm\capture\svc\dll\capturesession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Graphics::Capture::Server::CaptureSession::SetBufferCollection(RTL_SRWLOCK *this, void *a2)
{
  RTL_SRWLOCK *v4; // rbx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  RTL_SRWLOCK *v11; // [rsp+30h] [rbp+8h] BYREF

  v4 = this + 15;
  AcquireSRWLockExclusive(this + 15);
  v11 = v4;
  v5 = (*(__int64 (__fastcall **)(PVOID, void *))(*(_QWORD *)this[7].Ptr + 88LL))(this[7].Ptr, a2);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v5 = Windows::Graphics::Capture::Server::DCompManager::Commit(Windows::Graphics::Capture::Server::g_DCompManager);
    v6 = v5;
    if ( v5 >= 0 )
    {
      v6 = 0;
      goto LABEL_7;
    }
    v7 = 205;
  }
  else
  {
    v7 = 202;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturesession.cpp",
    (const char *)(unsigned int)v5,
    v9);
LABEL_7:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  return v6;
}

```

## disassembly

```asm
0x18001ce10  mov     [rsp+arg_8], rbx
0x18001ce15  mov     [rsp+arg_10], rsi
0x18001ce1a  push    rdi; int
0x18001ce1b  sub     rsp, 20h
0x18001ce1f  mov     rsi, rdx
0x18001ce22  mov     rdi, rcx
0x18001ce25  lea     rbx, [rcx+78h]
0x18001ce29  mov     rcx, rbx; SRWLock
0x18001ce2c  call    cs:__imp_AcquireSRWLockExclusive
0x18001ce32  mov     [rsp+28h+arg_0], rbx
0x18001ce37  mov     rcx, [rdi+38h]
0x18001ce3b  mov     rax, [rcx]
0x18001ce3e  mov     rdx, rsi
0x18001ce41  mov     rax, [rax+58h]
0x18001ce45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce4a  mov     ebx, eax
0x18001ce4c  test    eax, eax
0x18001ce4e  jns     short loc_18001CE57
0x18001ce50  mov     edx, 0CAh
0x18001ce55  jmp     short loc_18001CE6E
0x18001ce57  mov     rcx, cs:?g_DCompManager@Server@Capture@Graphics@Windows@@3V?$unique_ptr@VDCompManager@Server@Capture@Graphics@Windows@@U?$default_delete@VDCompManager@Server@Capture@Graphics@Windows@@@std@@@std@@A; this
0x18001ce5e  call    ?Commit@DCompManager@Server@Capture@Graphics@Windows@@QEAAJXZ; Windows::Graphics::Capture::Server::DCompManager::Commit(void)
0x18001ce63  mov     ebx, eax
0x18001ce65  test    eax, eax
0x18001ce67  jns     short loc_18001CE84
0x18001ce69  mov     edx, 0CDh; void *
0x18001ce6e  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001ce75  mov     r9d, eax; char *
0x18001ce78  mov     rcx, [rsp+28h]; this
0x18001ce7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ce82  jmp     short loc_18001CE86
0x18001ce84  xor     ebx, ebx
0x18001ce86  lea     rcx, [rsp+28h+arg_0]
0x18001ce8b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001ce90  mov     eax, ebx
0x18001ce92  mov     rbx, [rsp+28h+arg_8]
0x18001ce97  mov     rsi, [rsp+28h+arg_10]
0x18001ce9c  add     rsp, 20h
0x18001cea0  pop     rdi
0x18001cea1  retn
```
