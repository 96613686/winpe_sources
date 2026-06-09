# Windows::Graphics::Capture::Server::CaptureSession::ReevaluateBorderState(void)

- ea: `0x18001c850`
- end: `0x18001c8dc`
- name: `?ReevaluateBorderState@CaptureSession@Server@Capture@Graphics@Windows@@QEAAJXZ`
- size: `140`
- prototype: `int(Windows::Graphics::Capture::Server::CaptureSession *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18001dfe0`

## callees

- `0x180005568`
- `0x18000907c`
- `0x18001c850`
- `0x18001ea08`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c867`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c867`

## string_xrefs

- `0x18001c8b0`: `onecoreuap\windows\dwm\capture\svc\dll\capturesession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Graphics::Capture::Server::CaptureSession::ReevaluateBorderState(
        Windows::Graphics::Capture::Server::CaptureSession *this)
{
  RTL_SRWLOCK *v2; // rbx
  char v3; // dl
  int v4; // eax
  unsigned int v5; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  RTL_SRWLOCK *v9; // [rsp+30h] [rbp+8h] BYREF

  v2 = (RTL_SRWLOCK *)((char *)this + 144);
  AcquireSRWLockExclusive((PSRWLOCK)this + 18);
  v9 = v2;
  v3 = !Windows::Graphics::Capture::Server::CheckCAMCapability(1, *((_DWORD *)this + 27));
  if ( v3 == *((_BYTE *)this + 106)
    || (*((_BYTE *)this + 106) = v3, *((_BYTE *)this + 105))
    || (v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 96LL))(*((_QWORD *)this + 9)),
        v5 = v4,
        v4 >= 0) )
  {
    v5 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AA,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturesession.cpp",
      (const char *)(unsigned int)v4,
      v7);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  return v5;
}

```

## disassembly

```asm
0x18001c850  mov     [rsp+arg_8], rbx
0x18001c855  push    rdi; int
0x18001c856  sub     rsp, 20h
0x18001c85a  mov     rdi, rcx
0x18001c85d  lea     rbx, [rcx+90h]
0x18001c864  mov     rcx, rbx; SRWLock
0x18001c867  call    cs:__imp_AcquireSRWLockExclusive
0x18001c86d  mov     [rsp+28h+arg_0], rbx
0x18001c872  mov     edx, [rdi+6Ch]
0x18001c875  mov     ecx, 1
0x18001c87a  call    ?CheckCAMCapability@Server@Capture@Graphics@Windows@@YA_NW4CaptureServerAccessRequestKind@1234@K@Z; Windows::Graphics::Capture::Server::CheckCAMCapability(Windows::Graphics::Capture::Server::CaptureServerAccessRequestKind,ulong)
0x18001c87f  mov     dl, al
0x18001c881  xor     dl, 1
0x18001c884  cmp     dl, [rdi+6Ah]
0x18001c887  jz      short loc_18001C8C3
0x18001c889  mov     [rdi+6Ah], dl
0x18001c88c  cmp     byte ptr [rdi+69h], 0
0x18001c890  jnz     short loc_18001C8C3
0x18001c892  mov     rcx, [rdi+48h]
0x18001c896  mov     rax, [rcx]
0x18001c899  mov     rax, [rax+60h]
0x18001c89d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8a2  mov     ebx, eax
0x18001c8a4  test    eax, eax
0x18001c8a6  jns     short loc_18001C8C3
0x18001c8a8  mov     rcx, [rsp+28h]; this
0x18001c8ad  mov     r9d, eax; char *
0x18001c8b0  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001c8b7  mov     edx, 1AAh; void *
0x18001c8bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c8c1  jmp     short loc_18001C8C5
0x18001c8c3  xor     ebx, ebx
0x18001c8c5  lea     rcx, [rsp+28h+arg_0]
0x18001c8ca  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001c8cf  mov     eax, ebx
0x18001c8d1  mov     rbx, [rsp+28h+arg_8]
0x18001c8d6  add     rsp, 20h
0x18001c8da  pop     rdi
0x18001c8db  retn
```
