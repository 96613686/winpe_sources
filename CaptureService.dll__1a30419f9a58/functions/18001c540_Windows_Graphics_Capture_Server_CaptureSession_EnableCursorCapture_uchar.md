# Windows::Graphics::Capture::Server::CaptureSession::EnableCursorCapture(uchar)

- ea: `0x18001c540`
- end: `0x18001c5d5`
- name: `?EnableCursorCapture@CaptureSession@Server@Capture@Graphics@Windows@@UEAAJE@Z`
- size: `149`
- prototype: `int(Windows::Graphics::Capture::Server::CaptureSession *__hidden this, unsigned __int8)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005568`
- `0x18000907c`
- `0x18001c540`
- `0x18001fcac`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c55c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c55c`

## string_xrefs

- `0x18001c5a1`: `onecoreuap\windows\dwm\capture\svc\dll\capturesession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Graphics::Capture::Server::CaptureSession::EnableCursorCapture(RTL_SRWLOCK *this, char a2)
{
  RTL_SRWLOCK *v4; // rbx
  __int64 v5; // rdx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  RTL_SRWLOCK *v12; // [rsp+30h] [rbp+8h] BYREF

  v4 = this + 13;
  AcquireSRWLockExclusive(this + 13);
  v12 = v4;
  LOBYTE(v5) = a2 != 0;
  v6 = (*(__int64 (__fastcall **)(PVOID, __int64))(*(_QWORD *)this[5].Ptr + 48LL))(this[5].Ptr, v5);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v6 = Windows::Graphics::Capture::Server::DCompManager::Commit(Windows::Graphics::Capture::Server::g_DCompManager);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v7 = 0;
      goto LABEL_7;
    }
    v8 = 187;
  }
  else
  {
    v8 = 186;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturesession.cpp",
    (const char *)(unsigned int)v6,
    v10);
LABEL_7:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  return v7;
}

```

## disassembly

```asm
0x18001c540  mov     [rsp+arg_8], rbx
0x18001c545  mov     [rsp+arg_10], rsi
0x18001c54a  push    rdi; int
0x18001c54b  sub     rsp, 20h
0x18001c54f  mov     sil, dl
0x18001c552  mov     rdi, rcx
0x18001c555  lea     rbx, [rcx+68h]
0x18001c559  mov     rcx, rbx; SRWLock
0x18001c55c  call    cs:__imp_AcquireSRWLockExclusive
0x18001c562  mov     [rsp+28h+arg_0], rbx
0x18001c567  mov     rcx, [rdi+28h]
0x18001c56b  mov     rax, [rcx]
0x18001c56e  test    sil, sil
0x18001c571  setnz   dl
0x18001c574  mov     rax, [rax+30h]
0x18001c578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c57d  mov     ebx, eax
0x18001c57f  test    eax, eax
0x18001c581  jns     short loc_18001C58A
0x18001c583  mov     edx, 0BAh
0x18001c588  jmp     short loc_18001C5A1
0x18001c58a  mov     rcx, cs:?g_DCompManager@Server@Capture@Graphics@Windows@@3V?$unique_ptr@VDCompManager@Server@Capture@Graphics@Windows@@U?$default_delete@VDCompManager@Server@Capture@Graphics@Windows@@@std@@@std@@A; this
0x18001c591  call    ?Commit@DCompManager@Server@Capture@Graphics@Windows@@QEAAJXZ; Windows::Graphics::Capture::Server::DCompManager::Commit(void)
0x18001c596  mov     ebx, eax
0x18001c598  test    eax, eax
0x18001c59a  jns     short loc_18001C5B7
0x18001c59c  mov     edx, 0BBh; void *
0x18001c5a1  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001c5a8  mov     r9d, eax; char *
0x18001c5ab  mov     rcx, [rsp+28h]; this
0x18001c5b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c5b5  jmp     short loc_18001C5B9
0x18001c5b7  xor     ebx, ebx
0x18001c5b9  lea     rcx, [rsp+28h+arg_0]
0x18001c5be  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001c5c3  mov     eax, ebx
0x18001c5c5  mov     rbx, [rsp+28h+arg_8]
0x18001c5ca  mov     rsi, [rsp+28h+arg_10]
0x18001c5cf  add     rsp, 20h
0x18001c5d3  pop     rdi
0x18001c5d4  retn
```
