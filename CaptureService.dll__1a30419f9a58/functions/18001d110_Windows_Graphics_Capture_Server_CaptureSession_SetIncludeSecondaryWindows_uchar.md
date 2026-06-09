# Windows::Graphics::Capture::Server::CaptureSession::SetIncludeSecondaryWindows(uchar)

- ea: `0x18001d110`
- end: `0x18001d1c8`
- name: `?SetIncludeSecondaryWindows@CaptureSession@Server@Capture@Graphics@Windows@@UEAAJE@Z`
- size: `184`
- prototype: `int(Windows::Graphics::Capture::Server::CaptureSession *__hidden this, unsigned __int8)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005568`
- `0x18000907c`
- `0x18001d110`
- `0x18001fcac`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d12c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d12c`

## string_xrefs

- `0x18001d194`: `onecoreuap\windows\dwm\capture\svc\dll\capturesession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Graphics::Capture::Server::CaptureSession::SetIncludeSecondaryWindows(
        RTL_SRWLOCK *this,
        char a2)
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
  if ( BYTE3(this[8].Ptr) == (a2 != 0) || this[11].Ptr )
    goto LABEL_8;
  BYTE3(this[8].Ptr) = a2 != 0;
  LOBYTE(v5) = a2 == 0;
  v6 = (*(__int64 (__fastcall **)(PVOID, __int64))(*(_QWORD *)this[5].Ptr + 80LL))(this[5].Ptr, v5);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v6 = Windows::Graphics::Capture::Server::DCompManager::Commit(Windows::Graphics::Capture::Server::g_DCompManager);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 320;
      goto LABEL_7;
    }
LABEL_8:
    v7 = 0;
    goto LABEL_9;
  }
  v8 = 319;
LABEL_7:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturesession.cpp",
    (const char *)(unsigned int)v6,
    v10);
LABEL_9:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  return v7;
}

```

## disassembly

```asm
0x18001d110  mov     [rsp+arg_8], rbx
0x18001d115  mov     [rsp+arg_10], rsi
0x18001d11a  push    rdi; int
0x18001d11b  sub     rsp, 20h
0x18001d11f  mov     sil, dl
0x18001d122  mov     rdi, rcx
0x18001d125  lea     rbx, [rcx+68h]
0x18001d129  mov     rcx, rbx; SRWLock
0x18001d12c  call    cs:__imp_AcquireSRWLockExclusive
0x18001d132  mov     [rsp+28h+arg_0], rbx
0x18001d137  xor     r8d, r8d
0x18001d13a  test    sil, sil
0x18001d13d  setnz   r8b
0x18001d141  movzx   eax, byte ptr [rdi+43h]
0x18001d145  cmp     eax, r8d
0x18001d148  jz      short loc_18001D1AA
0x18001d14a  cmp     qword ptr [rdi+58h], 0
0x18001d14f  jnz     short loc_18001D1AA
0x18001d151  test    sil, sil
0x18001d154  setnz   al
0x18001d157  mov     [rdi+43h], al
0x18001d15a  mov     rcx, [rdi+28h]
0x18001d15e  mov     rax, [rcx]
0x18001d161  test    sil, sil
0x18001d164  setz    dl
0x18001d167  mov     rax, [rax+50h]
0x18001d16b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d170  mov     ebx, eax
0x18001d172  test    eax, eax
0x18001d174  jns     short loc_18001D17D
0x18001d176  mov     edx, 13Fh
0x18001d17b  jmp     short loc_18001D194
0x18001d17d  mov     rcx, cs:?g_DCompManager@Server@Capture@Graphics@Windows@@3V?$unique_ptr@VDCompManager@Server@Capture@Graphics@Windows@@U?$default_delete@VDCompManager@Server@Capture@Graphics@Windows@@@std@@@std@@A; this
0x18001d184  call    ?Commit@DCompManager@Server@Capture@Graphics@Windows@@QEAAJXZ; Windows::Graphics::Capture::Server::DCompManager::Commit(void)
0x18001d189  mov     ebx, eax
0x18001d18b  test    eax, eax
0x18001d18d  jns     short loc_18001D1AA
0x18001d18f  mov     edx, 140h; void *
0x18001d194  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001d19b  mov     r9d, eax; char *
0x18001d19e  mov     rcx, [rsp+28h]; this
0x18001d1a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d1a8  jmp     short loc_18001D1AC
0x18001d1aa  xor     ebx, ebx
0x18001d1ac  lea     rcx, [rsp+28h+arg_0]
0x18001d1b1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001d1b6  mov     eax, ebx
0x18001d1b8  mov     rbx, [rsp+28h+arg_8]
0x18001d1bd  mov     rsi, [rsp+28h+arg_10]
0x18001d1c2  add     rsp, 20h
0x18001d1c6  pop     rdi
0x18001d1c7  retn
```
