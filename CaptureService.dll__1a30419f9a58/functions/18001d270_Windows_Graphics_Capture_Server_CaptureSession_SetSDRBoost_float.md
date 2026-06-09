# Windows::Graphics::Capture::Server::CaptureSession::SetSDRBoost(float)

- ea: `0x18001d270`
- end: `0x18001d302`
- name: `?SetSDRBoost@CaptureSession@Server@Capture@Graphics@Windows@@UEAAJM@Z`
- size: `146`
- prototype: `int(Windows::Graphics::Capture::Server::CaptureSession *__hidden this, float)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005568`
- `0x18000907c`
- `0x18001d270`
- `0x18001fcac`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d28c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d28c`

## string_xrefs

- `0x18001d2ce`: `onecoreuap\windows\dwm\capture\svc\dll\capturesession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Graphics::Capture::Server::CaptureSession::SetSDRBoost(RTL_SRWLOCK *this, float a2)
{
  RTL_SRWLOCK *v3; // rbx
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  int v8; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  RTL_SRWLOCK *v10; // [rsp+40h] [rbp+8h] BYREF

  v3 = this + 13;
  AcquireSRWLockExclusive(this + 13);
  v10 = v3;
  v4 = (*(__int64 (__fastcall **)(PVOID))(*(_QWORD *)this[5].Ptr + 56LL))(this[5].Ptr);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v4 = Windows::Graphics::Capture::Server::DCompManager::Commit(Windows::Graphics::Capture::Server::g_DCompManager);
    v5 = v4;
    if ( v4 >= 0 )
    {
      v5 = 0;
      goto LABEL_7;
    }
    v6 = 354;
  }
  else
  {
    v6 = 353;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturesession.cpp",
    (const char *)(unsigned int)v4,
    v8);
LABEL_7:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  return v5;
}

```

## disassembly

```asm
0x18001d270  mov     [rsp+arg_8], rbx
0x18001d275  push    rdi
0x18001d276  sub     rsp, 30h
0x18001d27a  movaps  xmmword ptr [rsp+38h+var_18], xmm6; int
0x18001d27f  movaps  xmm6, xmm1
0x18001d282  mov     rdi, rcx
0x18001d285  lea     rbx, [rcx+68h]
0x18001d289  mov     rcx, rbx; SRWLock
0x18001d28c  call    cs:__imp_AcquireSRWLockExclusive
0x18001d292  mov     [rsp+38h+arg_0], rbx
0x18001d297  mov     rcx, [rdi+28h]
0x18001d29b  mov     rax, [rcx]
0x18001d29e  movaps  xmm1, xmm6
0x18001d2a1  mov     rax, [rax+38h]
0x18001d2a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2aa  mov     ebx, eax
0x18001d2ac  test    eax, eax
0x18001d2ae  jns     short loc_18001D2B7
0x18001d2b0  mov     edx, 161h
0x18001d2b5  jmp     short loc_18001D2CE
0x18001d2b7  mov     rcx, cs:?g_DCompManager@Server@Capture@Graphics@Windows@@3V?$unique_ptr@VDCompManager@Server@Capture@Graphics@Windows@@U?$default_delete@VDCompManager@Server@Capture@Graphics@Windows@@@std@@@std@@A; this
0x18001d2be  call    ?Commit@DCompManager@Server@Capture@Graphics@Windows@@QEAAJXZ; Windows::Graphics::Capture::Server::DCompManager::Commit(void)
0x18001d2c3  mov     ebx, eax
0x18001d2c5  test    eax, eax
0x18001d2c7  jns     short loc_18001D2E4
0x18001d2c9  mov     edx, 162h; void *
0x18001d2ce  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001d2d5  mov     r9d, eax; char *
0x18001d2d8  mov     rcx, [rsp+38h]; this
0x18001d2dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d2e2  jmp     short loc_18001D2E6
0x18001d2e4  xor     ebx, ebx
0x18001d2e6  lea     rcx, [rsp+38h+arg_0]
0x18001d2eb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001d2f0  mov     eax, ebx
0x18001d2f2  mov     rbx, [rsp+38h+arg_8]
0x18001d2f7  movaps  xmm6, xmmword ptr [rsp+38h+var_18]
0x18001d2fc  add     rsp, 30h
0x18001d300  pop     rdi
0x18001d301  retn
```
