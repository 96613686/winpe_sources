# Windows::Graphics::Capture::Server::CaptureSession::SetMinUpdateInterval(uint)

- ea: `0x18001d1d0`
- end: `0x18001d260`
- name: `?SetMinUpdateInterval@CaptureSession@Server@Capture@Graphics@Windows@@UEAAJI@Z`
- size: `144`
- prototype: `int(Windows::Graphics::Capture::Server::CaptureSession *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180005568`
- `0x18000907c`
- `0x18001d1d0`
- `0x18001fcac`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d1eb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d1eb`

## string_xrefs

- `0x18001d22c`: `onecoreuap\windows\dwm\capture\svc\dll\capturesession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Graphics::Capture::Server::CaptureSession::SetMinUpdateInterval(
        RTL_SRWLOCK *this,
        unsigned int a2)
{
  RTL_SRWLOCK *v4; // rbx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  RTL_SRWLOCK *v11; // [rsp+30h] [rbp+8h] BYREF

  v4 = this + 13;
  AcquireSRWLockExclusive(this + 13);
  v11 = v4;
  v5 = (*(__int64 (__fastcall **)(PVOID, _QWORD))(*(_QWORD *)this[5].Ptr + 64LL))(this[5].Ptr, a2);
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
    v7 = 281;
  }
  else
  {
    v7 = 280;
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
0x18001d1d0  mov     [rsp+arg_8], rbx
0x18001d1d5  mov     [rsp+arg_10], rsi
0x18001d1da  push    rdi; int
0x18001d1db  sub     rsp, 20h
0x18001d1df  mov     esi, edx
0x18001d1e1  mov     rdi, rcx
0x18001d1e4  lea     rbx, [rcx+68h]
0x18001d1e8  mov     rcx, rbx; SRWLock
0x18001d1eb  call    cs:__imp_AcquireSRWLockExclusive
0x18001d1f1  mov     [rsp+28h+arg_0], rbx
0x18001d1f6  mov     rcx, [rdi+28h]
0x18001d1fa  mov     rax, [rcx]
0x18001d1fd  mov     edx, esi
0x18001d1ff  mov     rax, [rax+40h]
0x18001d203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d208  mov     ebx, eax
0x18001d20a  test    eax, eax
0x18001d20c  jns     short loc_18001D215
0x18001d20e  mov     edx, 118h
0x18001d213  jmp     short loc_18001D22C
0x18001d215  mov     rcx, cs:?g_DCompManager@Server@Capture@Graphics@Windows@@3V?$unique_ptr@VDCompManager@Server@Capture@Graphics@Windows@@U?$default_delete@VDCompManager@Server@Capture@Graphics@Windows@@@std@@@std@@A; this
0x18001d21c  call    ?Commit@DCompManager@Server@Capture@Graphics@Windows@@QEAAJXZ; Windows::Graphics::Capture::Server::DCompManager::Commit(void)
0x18001d221  mov     ebx, eax
0x18001d223  test    eax, eax
0x18001d225  jns     short loc_18001D242
0x18001d227  mov     edx, 119h; void *
0x18001d22c  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001d233  mov     r9d, eax; char *
0x18001d236  mov     rcx, [rsp+28h]; this
0x18001d23b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d240  jmp     short loc_18001D244
0x18001d242  xor     ebx, ebx
0x18001d244  lea     rcx, [rsp+28h+arg_0]
0x18001d249  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001d24e  mov     eax, ebx
0x18001d250  mov     rbx, [rsp+28h+arg_8]
0x18001d255  mov     rsi, [rsp+28h+arg_10]
0x18001d25a  add     rsp, 20h
0x18001d25e  pop     rdi
0x18001d25f  retn
```
