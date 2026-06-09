# Windows::Graphics::Capture::Server::CaptureSession::RequestFrame(void)

- ea: `0x18001c9e0`
- end: `0x18001ca62`
- name: `?RequestFrame@CaptureSession@Server@Capture@Graphics@Windows@@UEAAJXZ`
- size: `130`
- prototype: `int(Windows::Graphics::Capture::Server::CaptureSession *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005568`
- `0x18000907c`
- `0x18001c9e0`
- `0x18001fcac`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c9f4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c9f4`

## string_xrefs

- `0x18001ca33`: `onecoreuap\windows\dwm\capture\svc\dll\capturesession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Graphics::Capture::Server::CaptureSession::RequestFrame(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // rbx
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  RTL_SRWLOCK *v9; // [rsp+30h] [rbp+8h] BYREF

  v2 = this + 13;
  AcquireSRWLockExclusive(this + 13);
  v9 = v2;
  v3 = (*(__int64 (__fastcall **)(PVOID))(*(_QWORD *)this[5].Ptr + 96LL))(this[5].Ptr);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v3 = Windows::Graphics::Capture::Server::DCompManager::Commit(Windows::Graphics::Capture::Server::g_DCompManager);
    v4 = v3;
    if ( v3 >= 0 )
    {
      v4 = 0;
      goto LABEL_7;
    }
    v5 = 343;
  }
  else
  {
    v5 = 342;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturesession.cpp",
    (const char *)(unsigned int)v3,
    v7);
LABEL_7:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  return v4;
}

```

## disassembly

```asm
0x18001c9e0  mov     [rsp+arg_8], rbx
0x18001c9e5  push    rdi; int
0x18001c9e6  sub     rsp, 20h
0x18001c9ea  mov     rdi, rcx
0x18001c9ed  lea     rbx, [rcx+68h]
0x18001c9f1  mov     rcx, rbx; SRWLock
0x18001c9f4  call    cs:__imp_AcquireSRWLockExclusive
0x18001c9fa  mov     [rsp+28h+arg_0], rbx
0x18001c9ff  mov     rcx, [rdi+28h]
0x18001ca03  mov     rax, [rcx]
0x18001ca06  mov     rax, [rax+60h]
0x18001ca0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca0f  mov     ebx, eax
0x18001ca11  test    eax, eax
0x18001ca13  jns     short loc_18001CA1C
0x18001ca15  mov     edx, 156h
0x18001ca1a  jmp     short loc_18001CA33
0x18001ca1c  mov     rcx, cs:?g_DCompManager@Server@Capture@Graphics@Windows@@3V?$unique_ptr@VDCompManager@Server@Capture@Graphics@Windows@@U?$default_delete@VDCompManager@Server@Capture@Graphics@Windows@@@std@@@std@@A; this
0x18001ca23  call    ?Commit@DCompManager@Server@Capture@Graphics@Windows@@QEAAJXZ; Windows::Graphics::Capture::Server::DCompManager::Commit(void)
0x18001ca28  mov     ebx, eax
0x18001ca2a  test    eax, eax
0x18001ca2c  jns     short loc_18001CA49
0x18001ca2e  mov     edx, 157h; void *
0x18001ca33  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001ca3a  mov     r9d, eax; char *
0x18001ca3d  mov     rcx, [rsp+28h]; this
0x18001ca42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ca47  jmp     short loc_18001CA4B
0x18001ca49  xor     ebx, ebx
0x18001ca4b  lea     rcx, [rsp+28h+arg_0]
0x18001ca50  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001ca55  mov     eax, ebx
0x18001ca57  mov     rbx, [rsp+28h+arg_8]
0x18001ca5c  add     rsp, 20h
0x18001ca60  pop     rdi
0x18001ca61  retn
```
