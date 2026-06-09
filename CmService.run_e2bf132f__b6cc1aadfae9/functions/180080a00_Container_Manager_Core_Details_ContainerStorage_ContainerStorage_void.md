# Container::Manager::Core::Details::ContainerStorage::~ContainerStorage(void)

- ea: `0x180080a00`
- end: `0x180080b91`
- name: `??1ContainerStorage@Details@Core@Manager@Container@@QEAA@XZ`
- size: `401`
- prototype: `void __fastcall(Container::Manager::Core::Details::ContainerStorage *__hidden this)`
- caller_count: `12`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x18004dfa0`
- `0x18004f630`
- `0x1800506c4`
- `0x180054654`
- `0x18005490c`
- `0x180056cf0`
- `0x180056dac`
- `0x18005ad78`
- `0x18006dce0`
- `0x18008191c`
- `0x180082490`
- `0x180085edc`

## callees

- `0x180004fc4`
- `0x1800471dc`
- `0x180080a00`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180080a23`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180080a23`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180080a4c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180080ae5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180080a4c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180080ae5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080a3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080a3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180080a5a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180080a5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180080a7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180080a7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180080b73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180080b73`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Container::Manager::Core::Details::ContainerStorage::~ContainerStorage(
        Container::Manager::Core::Details::ContainerStorage *this)
{
  struct _TP_WORK *v2; // rcx
  struct _TP_WORK *v3; // rsi
  DWORD LastError; // ebx
  void *v5; // rcx
  utl::_RefCountBase *v6; // rcx
  utl::_RefCountBase *v7; // rcx
  char *v8; // rcx
  struct _TP_WORK *v9; // rcx
  utl::_RefCountBase *v10; // rcx
  char *v11; // rcx
  char *v12; // rcx
  char *v13; // rcx
  char *v14; // rcx
  HKEY v15; // rcx

  v2 = (struct _TP_WORK *)*((_QWORD *)this + 33);
  if ( v2 )
  {
    WaitForThreadpoolWorkCallbacks(v2, 1);
    v3 = (struct _TP_WORK *)*((_QWORD *)this + 33);
    if ( v3 )
    {
      LastError = GetLastError();
      CloseThreadpoolWork(v3);
      SetLastError(LastError);
    }
    *((_QWORD *)this + 33) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 51);
  if ( v5 )
    LocalFree(v5);
  v6 = (utl::_RefCountBase *)*((_QWORD *)this + 48);
  if ( v6 )
    utl::_RefCountBase::_DecStrong(v6);
  v7 = (utl::_RefCountBase *)*((_QWORD *)this + 41);
  if ( v7 )
    utl::_RefCountBase::_DecStrong(v7);
  if ( *((_BYTE *)this + 312) )
  {
    v8 = (char *)*((_QWORD *)this + 35);
    if ( v8 != (char *)this + 296 )
      operator delete(v8, (const struct std::nothrow_t *)&std::nothrow);
  }
  v9 = (struct _TP_WORK *)*((_QWORD *)this + 33);
  if ( v9 )
    CloseThreadpoolWork(v9);
  v10 = (utl::_RefCountBase *)*((_QWORD *)this + 32);
  if ( v10 )
    utl::_RefCountBase::_DecStrong(v10);
  if ( *((_BYTE *)this + 184) )
  {
    v11 = (char *)*((_QWORD *)this + 19);
    if ( v11 != (char *)this + 168 )
      operator delete(v11, (const struct std::nothrow_t *)&std::nothrow);
  }
  v12 = (char *)*((_QWORD *)this + 14);
  if ( v12 != (char *)this + 128 )
    operator delete(v12, (const struct std::nothrow_t *)&std::nothrow);
  v13 = (char *)*((_QWORD *)this + 10);
  if ( v13 != (char *)this + 96 )
    operator delete(v13, (const struct std::nothrow_t *)&std::nothrow);
  v14 = (char *)*((_QWORD *)this + 6);
  if ( v14 != (char *)this + 64 )
    operator delete(v14, (const struct std::nothrow_t *)&std::nothrow);
  v15 = (HKEY)*((_QWORD *)this + 5);
  if ( v15 )
    RegCloseKey(v15);
}

```

## disassembly

```asm
0x180080a00  mov     [rsp+arg_0], rbx
0x180080a05  mov     [rsp+arg_8], rsi
0x180080a0a  push    rdi
0x180080a0b  sub     rsp, 20h
0x180080a0f  mov     rdi, rcx
0x180080a12  mov     rcx, [rcx+108h]; pwk
0x180080a19  test    rcx, rcx
0x180080a1c  jz      short loc_180080A71
0x180080a1e  mov     edx, 1; fCancelPendingCallbacks
0x180080a23  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180080a2a  nop     dword ptr [rax+rax+00h]
0x180080a2f  mov     rsi, [rdi+108h]
0x180080a36  test    rsi, rsi
0x180080a39  jz      short loc_180080A66
0x180080a3b  call    cs:__imp_GetLastError
0x180080a42  nop     dword ptr [rax+rax+00h]
0x180080a47  mov     ebx, eax
0x180080a49  mov     rcx, rsi; pwk
0x180080a4c  call    cs:__imp_CloseThreadpoolWork
0x180080a53  nop     dword ptr [rax+rax+00h]
0x180080a58  mov     ecx, ebx; dwErrCode
0x180080a5a  call    cs:__imp_SetLastError
0x180080a61  nop     dword ptr [rax+rax+00h]
0x180080a66  mov     qword ptr [rdi+108h], 0
0x180080a71  mov     rcx, [rdi+198h]; hMem
0x180080a78  test    rcx, rcx
0x180080a7b  jz      short loc_180080A8A
0x180080a7d  call    cs:__imp_LocalFree
0x180080a84  nop     dword ptr [rax+rax+00h]
0x180080a89  nop
0x180080a8a  mov     rcx, [rdi+180h]; this
0x180080a91  test    rcx, rcx
0x180080a94  jz      short loc_180080A9C
0x180080a96  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180080a9b  nop
0x180080a9c  mov     rcx, [rdi+148h]; this
0x180080aa3  test    rcx, rcx
0x180080aa6  jz      short loc_180080AAE
0x180080aa8  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180080aad  nop
0x180080aae  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180080ab5  cmp     byte ptr [rdi+138h], 0
0x180080abc  jz      short loc_180080AD9
0x180080abe  mov     rcx, [rdi+118h]; void *
0x180080ac5  lea     rax, [rdi+128h]
0x180080acc  cmp     rcx, rax
0x180080acf  jz      short loc_180080AD9
0x180080ad1  mov     rdx, rbx; struct std::nothrow_t *
0x180080ad4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180080ad9  mov     rcx, [rdi+108h]; pwk
0x180080ae0  test    rcx, rcx
0x180080ae3  jz      short loc_180080AF2
0x180080ae5  call    cs:__imp_CloseThreadpoolWork
0x180080aec  nop     dword ptr [rax+rax+00h]
0x180080af1  nop
0x180080af2  mov     rcx, [rdi+100h]; this
0x180080af9  test    rcx, rcx
0x180080afc  jz      short loc_180080B04
0x180080afe  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180080b03  nop
0x180080b04  cmp     byte ptr [rdi+0B8h], 0
0x180080b0b  jz      short loc_180080B28
0x180080b0d  mov     rcx, [rdi+98h]; void *
0x180080b14  lea     rax, [rdi+0A8h]
0x180080b1b  cmp     rcx, rax
0x180080b1e  jz      short loc_180080B28
0x180080b20  mov     rdx, rbx; struct std::nothrow_t *
0x180080b23  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180080b28  mov     rcx, [rdi+70h]; void *
0x180080b2c  lea     rax, [rdi+80h]
0x180080b33  cmp     rcx, rax
0x180080b36  jz      short loc_180080B40
0x180080b38  mov     rdx, rbx; struct std::nothrow_t *
0x180080b3b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180080b40  mov     rcx, [rdi+50h]; void *
0x180080b44  lea     rax, [rdi+60h]
0x180080b48  cmp     rcx, rax
0x180080b4b  jz      short loc_180080B55
0x180080b4d  mov     rdx, rbx; struct std::nothrow_t *
0x180080b50  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180080b55  mov     rcx, [rdi+30h]; void *
0x180080b59  lea     rax, [rdi+40h]
0x180080b5d  cmp     rcx, rax
0x180080b60  jz      short loc_180080B6A
0x180080b62  mov     rdx, rbx; struct std::nothrow_t *
0x180080b65  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180080b6a  mov     rcx, [rdi+28h]; hKey
0x180080b6e  test    rcx, rcx
0x180080b71  jz      short loc_180080B80
0x180080b73  call    cs:__imp_RegCloseKey
0x180080b7a  nop     dword ptr [rax+rax+00h]
0x180080b7f  nop
0x180080b80  mov     rbx, [rsp+28h+arg_0]
0x180080b85  mov     rsi, [rsp+28h+arg_8]
0x180080b8a  add     rsp, 20h
0x180080b8e  pop     rdi
0x180080b8f  retn
```
