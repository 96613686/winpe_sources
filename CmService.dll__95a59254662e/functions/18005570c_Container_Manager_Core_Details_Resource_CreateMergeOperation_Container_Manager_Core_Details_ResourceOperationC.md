# Container::Manager::Core::Details::Resource::CreateMergeOperation(Container::Manager::Core::Details::ResourceOperationConfiguration,utl::shared_ptr<Container::Manager::Core::Details::ResourceOperation> &)

- ea: `0x18005570c`
- end: `0x180055984`
- name: `?CreateMergeOperation@Resource@Details@Core@Manager@Container@@AEAAJUResourceOperationConfiguration@2345@AEAV?$shared_ptr@VResourceOperation@Details@Core@Manager@Container@@@utl@@@Z`
- size: `632`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180055d7c`

## callees

- `0x180004fc4`
- `0x18000a10c`
- `0x18000da88`
- `0x18000dad8`
- `0x18004feb4`
- `0x180050c7c`
- `0x18005570c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800557bb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180055874`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800557bb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180055874`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180055805`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005583b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800558b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180055805`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005583b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800558b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800557c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180055880`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800557c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180055880`

## string_xrefs

- `0x18005592d`: `onecore\base\gendrv\silos\clem\core\lib\ResourceBroker.h`
- `0x180055944`: `onecore\base\gendrv\silos\clem\core\lib\ResourceBroker.h`
- `0x18005595b`: `onecore\base\gendrv\silos\clem\core\lib\ResourceBroker.h`
- `0x180055972`: `onecore\base\gendrv\silos\clem\core\lib\ResourceBroker.h`
- `0x18005576c`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x1800557f0`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180055891`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::Resource::CreateMergeOperation(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        const char *a4)
{
  __int64 v7; // rsi
  __int64 v8; // r14
  unsigned int v9; // esi
  Container::Manager::Core::ResourceHandle *v10; // rdi
  __int64 v12; // r9
  __int64 v13; // rdx
  int v14; // eax
  RTL_SRWLOCK *v15; // rcx
  RTL_SRWLOCK *v16; // rcx
  int ResourceOperation; // ebp
  Container::Manager::Core::ResourceHandle *v18; // rdi
  Container::Manager::Core::ResourceHandle *v19; // rdi
  int v20[4]; // [rsp+20h] [rbp-58h] BYREF
  __int128 v21; // [rsp+30h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v7 = *(_QWORD *)(*(_QWORD *)(a2 + 8) + 40LL);
  if ( *(_DWORD *)(v7 + 16) != 1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x5C,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\ResourceBroker.h",
      a4);
  if ( !*(_BYTE *)(v7 + 40) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\ResourceBroker.h",
      a4);
  if ( *(_DWORD *)(a1 + 16) != 1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x5C,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\ResourceBroker.h",
      a4);
  if ( !*(_BYTE *)(a1 + 40) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\ResourceBroker.h",
      a4);
  v8 = *(_QWORD *)(v7 + 32);
  if ( *(_DWORD *)(v8 + 240) != 2 )
  {
    v9 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x8DF,
           (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
           (const char *)0x139F,
           v20[0]);
LABEL_7:
    if ( *(_BYTE *)(a2 + 16) )
    {
      v10 = *(Container::Manager::Core::ResourceHandle **)(a2 + 8);
      *(_QWORD *)(a2 + 8) = 0;
      if ( v10 )
      {
        Container::Manager::Core::ResourceHandle::~ResourceHandle(v10);
        operator delete(v10, (const struct std::nothrow_t *)0x58);
      }
    }
    return v9;
  }
  AcquireSRWLockExclusive((PSRWLOCK)(v7 + 112));
  *(_DWORD *)(v7 + 120) = GetCurrentThreadId();
  if ( *(_QWORD *)(v7 + 152) != 1 )
  {
    v12 = 32;
    v13 = 2290;
LABEL_13:
    v14 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v13,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
            (const char *)v12,
            v20[0]);
    v15 = (RTL_SRWLOCK *)(v7 + 112);
    *(_DWORD *)(v7 + 120) = 0;
    v9 = v14;
    ReleaseSRWLockExclusive(v15);
    goto LABEL_7;
  }
  if ( (*(_BYTE *)(v8 + 272) & 2) != 0 )
  {
    v12 = 303;
    v13 = 2301;
    goto LABEL_13;
  }
  *(_BYTE *)(v7 + 256) = 1;
  *(_DWORD *)(v7 + 120) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)(v7 + 112));
  v16 = *(RTL_SRWLOCK **)(a1 + 264);
  *(_OWORD *)v20 = 0;
  v21 = 0;
  ResourceOperation = Container::Manager::Core::Details::ResourceOperationMap::AddOrGetResourceOperation(
                        v16,
                        (int *)a2,
                        (__int64)v20,
                        a3);
  if ( ResourceOperation >= 0 )
  {
    if ( *(_BYTE *)(a2 + 16) )
    {
      v19 = *(Container::Manager::Core::ResourceHandle **)(a2 + 8);
      *(_QWORD *)(a2 + 8) = 0;
      if ( v19 )
      {
        Container::Manager::Core::ResourceHandle::~ResourceHandle(v19);
        operator delete(v19, (const struct std::nothrow_t *)0x58);
      }
    }
    return 0;
  }
  else
  {
    AcquireSRWLockExclusive((PSRWLOCK)(v7 + 112));
    *(_DWORD *)(v7 + 120) = GetCurrentThreadId();
    *(_BYTE *)(v7 + 256) = 0;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x920,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
      (const char *)(unsigned int)ResourceOperation,
      v20[0]);
    *(_DWORD *)(v7 + 120) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)(v7 + 112));
    if ( *(_BYTE *)(a2 + 16) )
    {
      v18 = *(Container::Manager::Core::ResourceHandle **)(a2 + 8);
      *(_QWORD *)(a2 + 8) = 0;
      if ( v18 )
      {
        Container::Manager::Core::ResourceHandle::~ResourceHandle(v18);
        operator delete(v18, (const struct std::nothrow_t *)0x58);
      }
    }
    return (unsigned int)ResourceOperation;
  }
}

```

## disassembly

```asm
0x18005570c  push    rbx
0x18005570e  push    rbp
0x18005570f  push    rsi
0x180055710  push    rdi
0x180055711  push    r12
0x180055713  push    r14
0x180055715  push    r15
0x180055717  sub     rsp, 40h
0x18005571b  mov     rax, [rdx+8]
0x18005571f  mov     r15, r8
0x180055722  mov     rbx, rdx
0x180055725  mov     rbp, rcx
0x180055728  mov     rsi, [rax+28h]
0x18005572c  cmp     dword ptr [rsi+10h], 1
0x180055730  jnz     loc_18005593F
0x180055736  xor     r12d, r12d
0x180055739  cmp     [rsi+28h], r12b
0x18005573d  jz      loc_180055956
0x180055743  cmp     dword ptr [rcx+10h], 1
0x180055747  jnz     loc_18005596D
0x18005574d  cmp     [rcx+28h], r12b
0x180055751  jz      loc_180055928
0x180055757  mov     r14, [rsi+20h]
0x18005575b  mov     eax, [r14+0F0h]
0x180055762  cmp     eax, 2
0x180055765  jz      short loc_1800557B4
0x180055767  mov     rcx, [rsp+78h]; this
0x18005576c  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180055773  mov     r9d, 139Fh; char *
0x180055779  mov     edx, 8DFh; void *
0x18005577e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180055783  mov     esi, eax
0x180055785  cmp     [rbx+10h], r12b
0x180055789  jz      short loc_1800557AD
0x18005578b  mov     rdi, [rbx+8]
0x18005578f  mov     [rbx+8], r12
0x180055793  test    rdi, rdi
0x180055796  jz      short loc_1800557AD
0x180055798  mov     rcx, rdi; this
0x18005579b  call    ??1ResourceHandle@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::ResourceHandle::~ResourceHandle(void)
0x1800557a0  mov     edx, 58h ; 'X'; struct std::nothrow_t *
0x1800557a5  mov     rcx, rdi; void *
0x1800557a8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800557ad  mov     eax, esi
0x1800557af  jmp     loc_180055918
0x1800557b4  lea     rdi, [rsi+70h]
0x1800557b8  mov     rcx, rdi; SRWLock
0x1800557bb  call    cs:__imp_AcquireSRWLockExclusive
0x1800557c2  nop     dword ptr [rax+rax+00h]
0x1800557c7  call    cs:__imp_GetCurrentThreadId
0x1800557ce  nop     dword ptr [rax+rax+00h]
0x1800557d3  mov     [rdi+8], eax
0x1800557d6  cmp     qword ptr [rsi+98h], 1
0x1800557de  jz      short loc_180055816
0x1800557e0  mov     r9d, 20h ; ' '; char *
0x1800557e6  mov     edx, 8F2h; void *
0x1800557eb  mov     rcx, [rsp+78h]; this
0x1800557f0  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800557f7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800557fc  mov     rcx, rdi; SRWLock
0x1800557ff  mov     [rdi+8], r12d
0x180055803  mov     esi, eax
0x180055805  call    cs:__imp_ReleaseSRWLockExclusive
0x18005580c  nop     dword ptr [rax+rax+00h]
0x180055811  jmp     loc_180055785
0x180055816  test    byte ptr [r14+110h], 2
0x18005581e  jz      short loc_18005582D
0x180055820  mov     r9d, 12Fh
0x180055826  mov     edx, 8FDh
0x18005582b  jmp     short loc_1800557EB
0x18005582d  mov     byte ptr [rsi+100h], 1
0x180055834  mov     rcx, rdi; SRWLock
0x180055837  mov     [rdi+8], r12d
0x18005583b  call    cs:__imp_ReleaseSRWLockExclusive
0x180055842  nop     dword ptr [rax+rax+00h]
0x180055847  mov     rcx, [rbp+108h]
0x18005584e  lea     r8, [rsp+78h+var_58]
0x180055853  xorps   xmm0, xmm0
0x180055856  mov     r9, r15
0x180055859  mov     rdx, rbx
0x18005585c  movups  xmmword ptr [rsp+78h+var_58], xmm0; int
0x180055861  movups  [rsp+78h+var_48], xmm0
0x180055866  call    ?AddOrGetResourceOperation@ResourceOperationMap@Details@Core@Manager@Container@@QEAAJAEAUResourceOperationConfiguration@2345@V?$optional@V?$vector@V?$shared_ptr@VResourceOperation@Details@Core@Manager@Container@@@utl@@V?$allocator@V?$shared_ptr@VResourceOperation@Details@Core@Manager@Container@@@utl@@@2@@utl@@@utl@@AEAV?$shared_ptr@VResourceOperation@Details@Core@Manager@Container@@@8@@Z; Container::Manager::Core::Details::ResourceOperationMap::AddOrGetResourceOperation(Container::Manager::Core::Details::ResourceOperationConfiguration &,utl::optional<utl::vector<utl::shared_ptr<Container::Manager::Core::Details::ResourceOperation>,utl::allocator<utl::shared_ptr<Container::Manager::Core::Details::ResourceOperation>>>>,utl::shared_ptr<Container::Manager::Core::Details::ResourceOperation> &)
0x18005586b  mov     ebp, eax
0x18005586d  test    eax, eax
0x18005586f  jns     short loc_1800558EE
0x180055871  mov     rcx, rdi; SRWLock
0x180055874  call    cs:__imp_AcquireSRWLockExclusive
0x18005587b  nop     dword ptr [rax+rax+00h]
0x180055880  call    cs:__imp_GetCurrentThreadId
0x180055887  nop     dword ptr [rax+rax+00h]
0x18005588c  mov     rcx, [rsp+78h]; this
0x180055891  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180055898  mov     [rdi+8], eax
0x18005589b  mov     r9d, ebp; char *
0x18005589e  mov     edx, 920h; void *
0x1800558a3  mov     [rsi+100h], r12b
0x1800558aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800558af  mov     rcx, rdi; SRWLock
0x1800558b2  mov     [rdi+8], r12d
0x1800558b6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800558bd  nop     dword ptr [rax+rax+00h]
0x1800558c2  cmp     [rbx+10h], r12b
0x1800558c6  jz      short loc_1800558EA
0x1800558c8  mov     rdi, [rbx+8]
0x1800558cc  mov     [rbx+8], r12
0x1800558d0  test    rdi, rdi
0x1800558d3  jz      short loc_1800558EA
0x1800558d5  mov     rcx, rdi; this
0x1800558d8  call    ??1ResourceHandle@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::ResourceHandle::~ResourceHandle(void)
0x1800558dd  mov     edx, 58h ; 'X'; struct std::nothrow_t *
0x1800558e2  mov     rcx, rdi; void *
0x1800558e5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800558ea  mov     eax, ebp
0x1800558ec  jmp     short loc_180055918
0x1800558ee  cmp     [rbx+10h], r12b
0x1800558f2  jz      short loc_180055916
0x1800558f4  mov     rdi, [rbx+8]
0x1800558f8  mov     [rbx+8], r12
0x1800558fc  test    rdi, rdi
0x1800558ff  jz      short loc_180055916
0x180055901  mov     rcx, rdi; this
0x180055904  call    ??1ResourceHandle@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::ResourceHandle::~ResourceHandle(void)
0x180055909  mov     edx, 58h ; 'X'; struct std::nothrow_t *
0x18005590e  mov     rcx, rdi; void *
0x180055911  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180055916  xor     eax, eax
0x180055918  add     rsp, 40h
0x18005591c  pop     r15
0x18005591e  pop     r14
0x180055920  pop     r12
0x180055922  pop     rdi
0x180055923  pop     rsi
0x180055924  pop     rbp
0x180055925  pop     rbx
0x180055926  retn
0x180055928  mov     rcx, [rsp+78h]; this
0x18005592d  lea     r8, aOnecoreBaseGen_26; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180055934  mov     edx, 5Dh ; ']'; void *
0x180055939  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18005593f  mov     rcx, [rsp+78h]; this
0x180055944  lea     r8, aOnecoreBaseGen_26; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18005594b  mov     edx, 5Ch ; '\'; void *
0x180055950  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180055956  mov     rcx, [rsp+78h]; this
0x18005595b  lea     r8, aOnecoreBaseGen_26; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180055962  mov     edx, 5Dh ; ']'; void *
0x180055967  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18005596d  mov     rcx, [rsp+78h]; this
0x180055972  lea     r8, aOnecoreBaseGen_26; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180055979  mov     edx, 5Ch ; '\'; void *
0x18005597e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
