# Windows::Internal::StateRepository::UserServer::GetUserSidAsSecurityIdentifier(uint *,uchar * *)

- ea: `0x18009b710`
- end: `0x18009b854`
- name: `?GetUserSidAsSecurityIdentifier@UserServer@StateRepository@Internal@Windows@@UEAAJPEAIPEAPEAE@Z`
- size: `324`
- prototype: `int(Windows::Internal::StateRepository::UserServer *__hidden this, unsigned int *, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000a834`
- `0x18000b380`
- `0x18001a9e0`
- `0x180078bd8`
- `0x18009b710`
- `0x18019914d`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18009b73f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18009b73f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18009b774`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18009b774`
- `ntdll!RtlLengthSid` at `0x18009b7d1`
- `ntdll!RtlLengthSid` at `0x18009b7d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b807`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b825`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b807`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b825`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009b7db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009b7db`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::UserServer::GetUserSidAsSecurityIdentifier(
        RTL_SRWLOCK *this,
        unsigned int *a2,
        unsigned __int8 **a3)
{
  RTL_SRWLOCK *v6; // rdi
  unsigned int v7; // ebx
  PVOID Ptr; // rdi
  SIZE_T v9; // rbp
  unsigned __int8 *v10; // rax
  unsigned __int8 *v11; // rbx
  int v13; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  char v15; // [rsp+50h] [rbp+8h] BYREF
  char v16; // [rsp+54h] [rbp+Ch]
  RTL_SRWLOCK *v17; // [rsp+58h] [rbp+10h] BYREF

  StateRepository::WinRT::Client::RequestInProgress::RequestInProgress(
    (StateRepository::WinRT::Client::RequestInProgress *)&v15,
    0);
  v6 = this + 16;
  AcquireSRWLockShared(this + 16);
  v17 = this + 16;
  if ( a2 )
  {
    if ( !a3 )
    {
      v7 = -2147467261;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.user-custom.cpp",
        (const char *)0x80004003LL,
        v13);
LABEL_14:
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v17);
      StateRepository::WinRT::Client::RequestInProgress::~RequestInProgress((StateRepository::WinRT::Client::RequestInProgress *)&v15);
      return v7;
    }
    *a2 = 0;
    *a3 = 0;
    Ptr = this[10].Ptr;
    if ( Ptr )
    {
      v9 = RtlLengthSid(this[10].Ptr);
      v10 = (unsigned __int8 *)CoTaskMemAlloc(v9);
      v11 = v10;
      if ( !v10 )
      {
        v7 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.user-custom.cpp",
          (const char *)0x8007000ELL,
          v13);
        CoTaskMemFree(0);
        goto LABEL_14;
      }
      memcpy_0(v10, Ptr, v9);
      *a2 = v9;
      *a3 = v11;
      CoTaskMemFree(0);
    }
    v7 = 0;
    goto LABEL_14;
  }
  v7 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xF,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.user-custom.cpp",
    (const char *)0x80004003LL,
    v13);
  if ( v6 )
    ReleaseSRWLockShared(v6);
  if ( v16 )
    _InterlockedDecrement((volatile signed __int32 *)&StateRepository::WinRT::Client::RequestInProgress::s_countNonBlocking);
  _InterlockedDecrement(&StateRepository::WinRT::Client::RequestInProgress::s_count);
  return v7;
}

```

## disassembly

```asm
0x18009b710  mov     [rsp+arg_10], rbx
0x18009b715  push    rbp
0x18009b716  push    rsi
0x18009b717  push    rdi
0x18009b718  push    r14
0x18009b71a  push    r15; int
0x18009b71c  sub     rsp, 20h
0x18009b720  mov     r14, rdx
0x18009b723  mov     rbx, rcx
0x18009b726  xor     edx, edx; bool
0x18009b728  lea     rcx, [rsp+48h+arg_0]; this
0x18009b72d  mov     rsi, r8
0x18009b730  call    ??0RequestInProgress@Client@WinRT@StateRepository@@QEAA@_N@Z; StateRepository::WinRT::Client::RequestInProgress::RequestInProgress(bool)
0x18009b735  lea     rdi, [rbx+80h]
0x18009b73c  mov     rcx, rdi; SRWLock
0x18009b73f  call    cs:__imp_AcquireSRWLockShared
0x18009b745  mov     [rsp+48h+arg_8], rdi
0x18009b74a  test    r14, r14
0x18009b74d  jnz     short loc_18009B794
0x18009b74f  mov     rcx, [rsp+48h]; this
0x18009b754  lea     r8, aOnecoreBaseApp_486; "onecore\\base\\appmodel\\staterepositor"...
0x18009b75b  mov     ebx, 80004003h
0x18009b760  lea     edx, [r14+0Fh]; void *
0x18009b764  mov     r9d, ebx; char *
0x18009b767  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009b76c  test    rdi, rdi
0x18009b76f  jz      short loc_18009B77A
0x18009b771  mov     rcx, rdi; SRWLock
0x18009b774  call    cs:__imp_ReleaseSRWLockShared
0x18009b77a  cmp     [rsp+48h+arg_4], 0
0x18009b77f  jz      short loc_18009B788
0x18009b781  lock dec cs:?s_countNonBlocking@RequestInProgress@Client@WinRT@StateRepository@@0JC; long volatile StateRepository::WinRT::Client::RequestInProgress::s_countNonBlocking
0x18009b788  lock dec cs:?s_count@RequestInProgress@Client@WinRT@StateRepository@@0JC; long volatile StateRepository::WinRT::Client::RequestInProgress::s_count
0x18009b78f  jmp     loc_18009B841
0x18009b794  test    rsi, rsi
0x18009b797  jnz     short loc_18009B7B7
0x18009b799  mov     rcx, [rsp+48h]; this
0x18009b79e  lea     r8, aOnecoreBaseApp_486; "onecore\\base\\appmodel\\staterepositor"...
0x18009b7a5  mov     ebx, 80004003h
0x18009b7aa  lea     edx, [rsi+10h]; void *
0x18009b7ad  mov     r9d, ebx; char *
0x18009b7b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009b7b5  jmp     short loc_18009B82D
0x18009b7b7  mov     dword ptr [r14], 0
0x18009b7be  mov     qword ptr [rsi], 0
0x18009b7c5  mov     rdi, [rbx+50h]
0x18009b7c9  test    rdi, rdi
0x18009b7cc  jz      short loc_18009B82B
0x18009b7ce  mov     rcx, rdi; Sid
0x18009b7d1  call    cs:__imp_RtlLengthSid
0x18009b7d7  mov     ecx, eax; cb
0x18009b7d9  mov     ebp, eax
0x18009b7db  call    cs:__imp_CoTaskMemAlloc
0x18009b7e1  mov     rbx, rax
0x18009b7e4  test    rax, rax
0x18009b7e7  jnz     short loc_18009B80F
0x18009b7e9  mov     rcx, [rsp+48h]; this
0x18009b7ee  lea     r8, aOnecoreBaseApp_486; "onecore\\base\\appmodel\\staterepositor"...
0x18009b7f5  mov     ebx, 8007000Eh
0x18009b7fa  lea     edx, [rax+1Ah]; void *
0x18009b7fd  mov     r9d, ebx; char *
0x18009b800  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009b805  xor     ecx, ecx; pv
0x18009b807  call    cs:__imp_CoTaskMemFree
0x18009b80d  jmp     short loc_18009B82D
0x18009b80f  mov     r8, rbp; Size
0x18009b812  mov     rdx, rdi; Src
0x18009b815  mov     rcx, rbx; void *
0x18009b818  call    memcpy_0
0x18009b81d  mov     [r14], ebp
0x18009b820  xor     ecx, ecx; pv
0x18009b822  mov     [rsi], rbx
0x18009b825  call    cs:__imp_CoTaskMemFree
0x18009b82b  xor     ebx, ebx
0x18009b82d  lea     rcx, [rsp+48h+arg_8]
0x18009b832  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18009b837  lea     rcx, [rsp+48h+arg_0]; this
0x18009b83c  call    ??1RequestInProgress@Client@WinRT@StateRepository@@QEAA@XZ; StateRepository::WinRT::Client::RequestInProgress::~RequestInProgress(void)
0x18009b841  mov     eax, ebx
0x18009b843  mov     rbx, [rsp+48h+arg_10]
0x18009b848  add     rsp, 20h
0x18009b84c  pop     r15
0x18009b84e  pop     r14
0x18009b850  pop     rdi
0x18009b851  pop     rsi
0x18009b852  pop     rbp
0x18009b853  retn
```
