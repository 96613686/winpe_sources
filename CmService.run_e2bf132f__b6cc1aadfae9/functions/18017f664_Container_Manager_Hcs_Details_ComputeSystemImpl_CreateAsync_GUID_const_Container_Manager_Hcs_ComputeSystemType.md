# Container::Manager::Hcs::Details::ComputeSystemImpl::CreateAsync(_GUID const &,Container::Manager::Hcs::ComputeSystemType,std::optional<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::optional<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::optional<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18017f664`
- end: `0x18017fb79`
- name: `?CreateAsync@ComputeSystemImpl@Details@Hcs@Manager@Container@@QEAA?AV?$AsyncOperation@X@Csl@@AEBU_GUID@@W4ComputeSystemType@345@V?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@22AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1301`
- prototype: `__int64 __usercall@<rax>(void *context@<rcx>, void *, void *, void *, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1801225a0`

## callees

- `0x180004fc4`
- `0x180007b3c`
- `0x180016718`
- `0x18002c5b4`
- `0x18003dbf8`
- `0x18003de70`
- `0x18003f7d8`
- `0x1800471dc`
- `0x1800491e8`
- `0x180050510`
- `0x180114a84`
- `0x1801760d4`
- `0x18017f664`
- `0x18017fb80`
- `0x180182118`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18017f6e1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18017fa1f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18017f6e1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18017fa1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18017f87c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18017fadd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18017f87c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18017fadd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017f7ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017f98b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017f7ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017f98b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18017f7ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18017f9aa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18017f7ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18017f9aa`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCreateComputeSystem` at `0x18017f773`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCreateComputeSystem` at `0x18017f773`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsTerminateComputeSystem` at `0x18017f94b`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsTerminateComputeSystem` at `0x18017f94b`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsSetComputeSystemCallback` at `0x18017f8a0`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsSetComputeSystemCallback` at `0x18017f8a0`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseComputeSystem` at `0x18017f7e0`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseComputeSystem` at `0x18017f867`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseComputeSystem` at `0x18017f99c`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseComputeSystem` at `0x18017f7e0`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseComputeSystem` at `0x18017f867`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseComputeSystem` at `0x18017f99c`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCreateOperation` at `0x18017f92d`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCreateOperation` at `0x18017f92d`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x18017f976`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x18017fa9b`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x18017fac9`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x18017fb07`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x18017f976`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x18017fa9b`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x18017fac9`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x18017fb07`

## string_xrefs

- `0x18017f962`: `onecore\base\gendrv\silos\clem\compute\lib\computesystem.cpp`
- `0x18017fb34`: `onecore\base\gendrv\silos\clem\compute\lib\computesystem.cpp`
- `0x18017fb52`: `onecore\base\gendrv\silos\clem\compute\lib\computesystem.cpp`
- `0x18017fb67`: `onecore\base\gendrv\silos\clem\compute\lib\computesystem.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
_QWORD *__fastcall Container::Manager::Hcs::Details::ComputeSystemImpl::CreateAsync(
        char *context,
        _QWORD *a2,
        _OWORD *a3,
        int a4,
        _BYTE *a5,
        _BYTE *a6,
        _BYTE *a7,
        __int64 a8)
{
  _QWORD *v8; // r13
  int v10; // eax
  __int64 v11; // rax
  HCS_OPERATION v12; // r14
  HCS_OPERATION v13; // rbx
  const WCHAR *v14; // rdx
  HRESULT v15; // ebx
  HCS_SYSTEM *v16; // r13
  DWORD LastError; // ebx
  HCS_OPERATION v19; // rax
  HCS_OPERATION v20; // rbx
  HRESULT v21; // eax
  HCS_SYSTEM v22; // r14
  DWORD v23; // ebx
  _QWORD *v24; // rcx
  _QWORD *v25; // rcx
  _QWORD *v26; // rcx
  __int64 v27; // rax
  utl::_RefCountBase *v28; // rcx
  unsigned int v29; // eax
  unsigned int v30; // eax
  int v31; // [rsp+28h] [rbp-99h]
  int v32; // [rsp+28h] [rbp-99h]
  HRESULT v33; // [rsp+38h] [rbp-89h]
  HCS_SYSTEM computeSystem; // [rsp+40h] [rbp-81h] BYREF
  HCS_OPERATION operation[2]; // [rsp+48h] [rbp-79h] BYREF
  utl::_RefCountBase *v36; // [rsp+58h] [rbp-69h]
  char v37; // [rsp+60h] [rbp-61h]
  int v38; // [rsp+68h] [rbp-59h]
  HCS_SYSTEM v39; // [rsp+70h] [rbp-51h]
  PCWSTR id[2]; // [rsp+78h] [rbp-49h] BYREF
  _WORD v41[8]; // [rsp+88h] [rbp-39h] BYREF
  HCS_SYSTEM v42; // [rsp+98h] [rbp-29h]
  HCS_OPERATION v43; // [rsp+A0h] [rbp-21h]
  HCS_OPERATION v44[2]; // [rsp+A8h] [rbp-19h] BYREF
  utl::_RefCountBase *v45; // [rsp+B8h] [rbp-9h]
  char v46; // [rsp+C0h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+100h] [rbp+3Fh]

  v8 = a2;
  v38 = 0;
  id[0] = v41;
  id[1] = v41;
  v41[0] = 0;
  v10 = Csl::GuidToString(a3, id);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystem.cpp",
      (const char *)(unsigned int)v10,
      v31);
  *v8 = 0;
  v8[1] = 0;
  v8[2] = 0;
  v38 = 1;
  AcquireSRWLockExclusive((PSRWLOCK)context + 4);
  v39 = (HCS_SYSTEM)(context + 32);
  v11 = Container::Manager::Hcs::Details::ComputeSystemImpl::CreateOperationsForAsyncCall(context, operation);
  v12 = *(HCS_OPERATION *)(v11 + 24);
  v43 = v12;
  Csl::AsyncOperation<void>::operator=(v8, v11);
  Csl::AsyncOperation<void>::Cleanup(operation);
  if ( v36 )
    utl::_RefCountBase::_DecStrong(v36);
  v13 = operation[0];
  operation[0] = 0;
  if ( v13 )
  {
    Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>(v13);
    operator delete(v13, (const struct std::nothrow_t *)0x30);
  }
  computeSystem = 0;
  v14 = (const WCHAR *)a8;
  if ( *(_QWORD *)(a8 + 24) > 7u )
    v14 = *(const WCHAR **)a8;
  v15 = HcsCreateComputeSystem(id[0], v14, v12, 0, &computeSystem);
  v33 = v15;
  if ( v15 >= 0 )
  {
    *(_OWORD *)context = *a3;
    *((_DWORD *)context + 4) = a4;
    v16 = (HCS_SYSTEM *)(context + 24);
    if ( context + 24 != (char *)&computeSystem )
    {
      v39 = computeSystem;
      v42 = *v16;
      if ( v42 )
      {
        LastError = GetLastError();
        HcsCloseComputeSystem(v42);
        SetLastError(LastError);
        v15 = v33;
      }
      *v16 = v39;
      computeSystem = 0;
    }
    *((_DWORD *)context + 10) = 1;
    if ( a5[32] )
      std::wstring::operator=(context + 840, a5);
    if ( a6[32] )
      std::wstring::operator=(context + 904, a6);
    if ( a7[32] )
      std::wstring::operator=(context + 936, a7);
    v8 = a2;
  }
  if ( computeSystem )
    HcsCloseComputeSystem(computeSystem);
  if ( context != (char *)-32LL )
    ReleaseSRWLockExclusive((PSRWLOCK)context + 4);
  if ( v15 < 0
    || (v33 = HcsSetComputeSystemCallback(
                *((HCS_SYSTEM *)context + 3),
                HcsEventOptionNone,
                context,
                Container::Manager::Hcs::Details::ComputeSystemImpl::OnComputeSystemEvent),
        v33 < 0) )
  {
    if ( *((_QWORD *)context + 3) )
    {
      v19 = HcsCreateOperation(0, 0);
      v20 = v19;
      if ( v19 )
      {
        v21 = HcsTerminateComputeSystem(*((HCS_SYSTEM *)context + 3), v19, 0);
        if ( v21 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xE2,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystem.cpp",
            (const char *)(unsigned int)v21,
            v32);
        HcsCloseOperation(v20);
      }
      v22 = (HCS_SYSTEM)*((_QWORD *)context + 3);
      if ( v22 )
      {
        v23 = GetLastError();
        HcsCloseComputeSystem(v22);
        SetLastError(v23);
      }
      *((_QWORD *)context + 3) = 0;
      *(GUID *)context = GUID_NULL;
      *((_DWORD *)context + 4) = 0;
      *((_DWORD *)context + 10) = 0;
      v24 = context + 840;
      *((_QWORD *)context + 107) = 0;
      if ( *((_QWORD *)context + 108) > 7u )
        v24 = (_QWORD *)*v24;
      *(_WORD *)v24 = 0;
      v25 = context + 936;
      *((_QWORD *)context + 119) = 0;
      if ( *((_QWORD *)context + 120) > 7u )
        v25 = (_QWORD *)*v25;
      *(_WORD *)v25 = 0;
      v26 = context + 904;
      *((_QWORD *)context + 115) = 0;
      if ( *((_QWORD *)context + 116) > 7u )
        v26 = (_QWORD *)*v26;
      *(_WORD *)v26 = 0;
    }
    v37 = 0;
    AcquireSRWLockExclusive((PSRWLOCK)context + 4);
    v27 = Container::Manager::Hcs::Details::ComputeSystemImpl::TryRemoveContextForOperation(context, v44, v43);
    if ( *(_BYTE *)(v27 + 24) )
    {
      if ( v37 )
      {
        Container::Manager::Hcs::Details::ComputeSystemImpl::OperationContext::operator=(operation, v27);
      }
      else
      {
        operation[0] = *(HCS_OPERATION *)v27;
        *(_QWORD *)v27 = 0;
        v28 = *(utl::_RefCountBase **)(v27 + 16);
        operation[1] = *(HCS_OPERATION *)(v27 + 8);
        v36 = v28;
        *(_QWORD *)(v27 + 8) = 0;
        *(_QWORD *)(v27 + 16) = 0;
        v37 = 1;
      }
    }
    else if ( v37 )
    {
      if ( v36 )
        utl::_RefCountBase::_DecStrong(v36);
      if ( operation[0] )
        HcsCloseOperation(operation[0]);
      v37 = 0;
    }
    if ( v46 )
    {
      if ( v45 )
        utl::_RefCountBase::_DecStrong(v45);
      if ( v44[0] )
        HcsCloseOperation(v44[0]);
    }
    if ( context != (char *)-32LL )
      ReleaseSRWLockExclusive((PSRWLOCK)context + 4);
    if ( v37 )
    {
      if ( v36 )
        utl::_RefCountBase::_DecStrong(v36);
      if ( operation[0] )
        HcsCloseOperation(operation[0]);
      v37 = 0;
    }
    if ( v33 == -2143878896 )
    {
      v29 = wil::verify_hresult<long>(2151088390LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x108,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystem.cpp",
        (const char *)v29,
        v32);
    }
    v30 = wil::verify_hresult<long>((unsigned int)v33);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10C,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystem.cpp",
      (const char *)v30,
      v32);
  }
  if ( id[0] != v41 )
    operator delete((void *)id[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( a5[32] )
    std::wstring::~wstring(a5);
  if ( a6[32] )
    std::wstring::~wstring(a6);
  if ( a7[32] )
    std::wstring::~wstring(a7);
  return v8;
}

```

## disassembly

```asm
0x18017f664  mov     rax, rsp
0x18017f667  mov     [rax+8], rbx
0x18017f66b  mov     [rax+20h], r9d
0x18017f66f  mov     [rax+18h], r8
0x18017f673  mov     [rax+10h], rdx
0x18017f677  push    rbp
0x18017f678  push    rsi
0x18017f679  push    rdi
0x18017f67a  push    r12
0x18017f67c  push    r13
0x18017f67e  push    r14
0x18017f680  push    r15
0x18017f682  lea     rbp, [rax-3Fh]
0x18017f686  sub     rsp, 0C0h
0x18017f68d  mov     r13, rdx
0x18017f690  mov     rsi, rcx
0x18017f693  xor     r15d, r15d
0x18017f696  mov     [rbp+37h+var_90], r15d
0x18017f69a  lea     rax, [rbp+37h+var_70]
0x18017f69e  mov     [rbp+37h+id], rax
0x18017f6a2  lea     rax, [rbp+37h+var_70]
0x18017f6a6  mov     [rbp+37h+var_78], rax
0x18017f6aa  mov     [rbp+37h+var_70], r15w
0x18017f6af  lea     rdx, [rbp+37h+id]
0x18017f6b3  mov     rcx, r8
0x18017f6b6  call    ?GuidToString@Csl@@YAJAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Csl::GuidToString(_GUID const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18017f6bb  mov     rcx, [rbp+3Fh]; this
0x18017f6bf  test    eax, eax
0x18017f6c1  js      loc_18017FB64
0x18017f6c7  mov     [r13+0], r15
0x18017f6cb  mov     [r13+8], r15
0x18017f6cf  mov     [r13+10h], r15
0x18017f6d3  mov     [rbp+37h+var_90], 1
0x18017f6da  lea     rdi, [rsi+20h]
0x18017f6de  mov     rcx, rdi; SRWLock
0x18017f6e1  call    cs:__imp_AcquireSRWLockExclusive
0x18017f6e8  nop     dword ptr [rax+rax+00h]
0x18017f6ed  mov     [rbp+37h+var_88], rdi
0x18017f6f1  lea     rdx, [rbp+37h+operation]
0x18017f6f5  mov     rcx, rsi
0x18017f6f8  call    ?CreateOperationsForAsyncCall@ComputeSystemImpl@Details@Hcs@Manager@Container@@AEAA?AV?$tuple@PEAUHCS_OPERATION__@@V?$AsyncOperation@X@Csl@@@std@@XZ; Container::Manager::Hcs::Details::ComputeSystemImpl::CreateOperationsForAsyncCall(void)
0x18017f6fd  mov     r14, [rax+18h]
0x18017f701  mov     [rbp+37h+var_58], r14
0x18017f705  mov     rdx, rax
0x18017f708  mov     rcx, r13
0x18017f70b  call    ??4?$AsyncOperation@X@Csl@@QEAAAEAV01@$$QEAV01@@Z; Csl::AsyncOperation<void>::operator=(Csl::AsyncOperation<void> &&)
0x18017f710  lea     rcx, [rbp+37h+operation]
0x18017f714  call    ?Cleanup@?$AsyncOperation@X@Csl@@AEAAXXZ; Csl::AsyncOperation<void>::Cleanup(void)
0x18017f719  nop
0x18017f71a  mov     rcx, [rbp+37h+var_A0]; this
0x18017f71e  test    rcx, rcx
0x18017f721  jz      short loc_18017F729
0x18017f723  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18017f728  nop
0x18017f729  mov     rbx, [rbp+37h+operation]
0x18017f72d  mov     [rbp+37h+operation], r15
0x18017f731  test    rbx, rbx
0x18017f734  jz      short loc_18017F74C
0x18017f736  mov     rcx, rbx
0x18017f739  call    ??1?$AsyncOperationImpl@X@Details@Csl@@QEAA@XZ; Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>(void)
0x18017f73e  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x18017f743  mov     rcx, rbx; void *
0x18017f746  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18017f74b  nop
0x18017f74c  mov     [rsp+0F0h+computeSystem], r15
0x18017f751  mov     rdx, [rbp+37h+arg_38]
0x18017f755  cmp     qword ptr [rdx+18h], 7
0x18017f75a  jbe     short loc_18017F75F
0x18017f75c  mov     rdx, [rdx]; configuration
0x18017f75f  lea     rax, [rsp+0F0h+computeSystem]
0x18017f764  mov     [rsp+20h], rax; int
0x18017f769  xor     r9d, r9d; securityDescriptor
0x18017f76c  mov     r8, r14; operation
0x18017f76f  mov     rcx, [rbp+37h+id]; id
0x18017f773  call    cs:__imp_HcsCreateComputeSystem
0x18017f77a  nop     dword ptr [rax+rax+00h]
0x18017f77f  mov     ebx, eax
0x18017f781  mov     dword ptr [rsp+0F0h+var_C0], eax
0x18017f785  mov     r14, [rbp+37h+arg_30]
0x18017f789  mov     r15, [rbp+37h+arg_28]
0x18017f78d  mov     r12, [rbp+37h+arg_20]
0x18017f791  test    eax, eax
0x18017f793  js      loc_18017F85D
0x18017f799  mov     rax, [rbp+37h+arg_10]
0x18017f79d  movups  xmm0, xmmword ptr [rax]
0x18017f7a0  movdqu  xmmword ptr [rsi], xmm0
0x18017f7a4  mov     eax, [rbp+37h+arg_18]
0x18017f7a7  mov     [rsi+10h], eax
0x18017f7aa  lea     r13, [rsi+18h]
0x18017f7ae  lea     rax, [rsp+0F0h+computeSystem]
0x18017f7b3  cmp     r13, rax
0x18017f7b6  jz      short loc_18017F80F
0x18017f7b8  mov     rax, [rsp+0F0h+computeSystem]
0x18017f7bd  mov     [rbp+37h+var_88], rax
0x18017f7c1  mov     rax, [r13+0]
0x18017f7c5  mov     [rbp+37h+var_60], rax
0x18017f7c9  test    rax, rax
0x18017f7cc  jz      short loc_18017F7FE
0x18017f7ce  call    cs:__imp_GetLastError
0x18017f7d5  nop     dword ptr [rax+rax+00h]
0x18017f7da  mov     ebx, eax
0x18017f7dc  mov     rcx, [rbp+37h+var_60]; computeSystem
0x18017f7e0  call    cs:__imp_HcsCloseComputeSystem
0x18017f7e7  nop     dword ptr [rax+rax+00h]
0x18017f7ec  mov     ecx, ebx; dwErrCode
0x18017f7ee  call    cs:__imp_SetLastError
0x18017f7f5  nop     dword ptr [rax+rax+00h]
0x18017f7fa  mov     ebx, dword ptr [rsp+0F0h+var_C0]
0x18017f7fe  mov     rax, [rbp+37h+var_88]
0x18017f802  mov     [r13+0], rax
0x18017f806  mov     [rsp+0F0h+computeSystem], 0
0x18017f80f  mov     dword ptr [rsi+28h], 1
0x18017f816  cmp     byte ptr [r12+20h], 0
0x18017f81c  jz      short loc_18017F82D
0x18017f81e  lea     rcx, [rsi+348h]
0x18017f825  mov     rdx, r12
0x18017f828  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18017f82d  cmp     byte ptr [r15+20h], 0
0x18017f832  jz      short loc_18017F843
0x18017f834  lea     rcx, [rsi+388h]
0x18017f83b  mov     rdx, r15
0x18017f83e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18017f843  cmp     byte ptr [r14+20h], 0
0x18017f848  jz      short loc_18017F859
0x18017f84a  lea     rcx, [rsi+3A8h]
0x18017f851  mov     rdx, r14
0x18017f854  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18017f859  mov     r13, [rbp+37h+arg_8]
0x18017f85d  mov     rcx, [rsp+0F0h+computeSystem]; computeSystem
0x18017f862  test    rcx, rcx
0x18017f865  jz      short loc_18017F874
0x18017f867  call    cs:__imp_HcsCloseComputeSystem
0x18017f86e  nop     dword ptr [rax+rax+00h]
0x18017f873  nop
0x18017f874  test    rdi, rdi
0x18017f877  jz      short loc_18017F888
0x18017f879  mov     rcx, rdi; SRWLock
0x18017f87c  call    cs:__imp_ReleaseSRWLockExclusive
0x18017f883  nop     dword ptr [rax+rax+00h]
0x18017f888  test    ebx, ebx
0x18017f88a  js      loc_18017F91C
0x18017f890  lea     r9, ?OnComputeSystemEvent@ComputeSystemImpl@Details@Hcs@Manager@Container@@CAXPEAUHCS_EVENT@@PEAX@Z; callback
0x18017f897  mov     r8, rsi; context
0x18017f89a  xor     edx, edx; callbackOptions
0x18017f89c  mov     rcx, [rsi+18h]; computeSystem
0x18017f8a0  call    cs:__imp_HcsSetComputeSystemCallback
0x18017f8a7  nop     dword ptr [rax+rax+00h]
0x18017f8ac  mov     dword ptr [rsp+0F0h+var_C0], eax
0x18017f8b0  xor     ebx, ebx
0x18017f8b2  test    eax, eax
0x18017f8b4  js      short loc_18017F91C
0x18017f8b6  lea     rax, [rbp+37h+var_70]
0x18017f8ba  mov     rcx, [rbp+37h+id]; void *
0x18017f8be  cmp     rcx, rax
0x18017f8c1  jz      short loc_18017F8D0
0x18017f8c3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18017f8ca  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18017f8cf  nop
0x18017f8d0  cmp     [r12+20h], bl
0x18017f8d5  jz      short loc_18017F8E0
0x18017f8d7  mov     rcx, r12; void *
0x18017f8da  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18017f8df  nop
0x18017f8e0  cmp     [r15+20h], bl
0x18017f8e4  jz      short loc_18017F8EF
0x18017f8e6  mov     rcx, r15; void *
0x18017f8e9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18017f8ee  nop
0x18017f8ef  cmp     [r14+20h], bl
0x18017f8f3  jz      short loc_18017F8FD
0x18017f8f5  mov     rcx, r14; void *
0x18017f8f8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18017f8fd  mov     rax, r13
0x18017f900  mov     rbx, [rsp+0F0h+arg_0]
0x18017f908  add     rsp, 0C0h
0x18017f90f  pop     r15
0x18017f911  pop     r14
0x18017f913  pop     r13
0x18017f915  pop     r12
0x18017f917  pop     rdi
0x18017f918  pop     rsi
0x18017f919  pop     rbp
0x18017f91a  retn
0x18017f91c  xor     r15d, r15d
0x18017f91f  cmp     [rsi+18h], r15
0x18017f923  jz      loc_18017FA18
0x18017f929  xor     edx, edx; callback
0x18017f92b  xor     ecx, ecx; context
0x18017f92d  call    cs:__imp_HcsCreateOperation
0x18017f934  nop     dword ptr [rax+rax+00h]
0x18017f939  mov     rbx, rax
0x18017f93c  test    rax, rax
0x18017f93f  jz      short loc_18017F982
0x18017f941  xor     r8d, r8d; options
0x18017f944  mov     rdx, rax; operation
0x18017f947  mov     rcx, [rsi+18h]; computeSystem
0x18017f94b  call    cs:__imp_HcsTerminateComputeSystem
0x18017f952  nop     dword ptr [rax+rax+00h]
0x18017f957  mov     rcx, [rbp+3Fh]; this
0x18017f95b  test    eax, eax
0x18017f95d  jns     short loc_18017F973
0x18017f95f  mov     r9d, eax; char *
0x18017f962  lea     r8, aOnecoreBaseGen_50; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x18017f969  mov     edx, 0E2h; void *
0x18017f96e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18017f973  mov     rcx, rbx; operation
0x18017f976  call    cs:__imp_HcsCloseOperation
0x18017f97d  nop     dword ptr [rax+rax+00h]
0x18017f982  mov     r14, [rsi+18h]
0x18017f986  test    r14, r14
0x18017f989  jz      short loc_18017F9B6
0x18017f98b  call    cs:__imp_GetLastError
0x18017f992  nop     dword ptr [rax+rax+00h]
0x18017f997  mov     ebx, eax
0x18017f999  mov     rcx, r14; computeSystem
0x18017f99c  call    cs:__imp_HcsCloseComputeSystem
0x18017f9a3  nop     dword ptr [rax+rax+00h]
0x18017f9a8  mov     ecx, ebx; dwErrCode
0x18017f9aa  call    cs:__imp_SetLastError
0x18017f9b1  nop     dword ptr [rax+rax+00h]
0x18017f9b6  mov     [rsi+18h], r15
0x18017f9ba  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18017f9c1  movdqu  xmmword ptr [rsi], xmm0
0x18017f9c5  mov     [rsi+10h], r15d
0x18017f9c9  mov     [rsi+28h], r15d
0x18017f9cd  lea     rcx, [rsi+348h]
0x18017f9d4  mov     [rcx+10h], r15
0x18017f9d8  cmp     qword ptr [rcx+18h], 7
0x18017f9dd  jbe     short loc_18017F9E2
0x18017f9df  mov     rcx, [rcx]
0x18017f9e2  mov     [rcx], r15w
0x18017f9e6  lea     rcx, [rsi+3A8h]
0x18017f9ed  mov     [rcx+10h], r15
0x18017f9f1  cmp     qword ptr [rcx+18h], 7
0x18017f9f6  jbe     short loc_18017F9FB
0x18017f9f8  mov     rcx, [rcx]
0x18017f9fb  mov     [rcx], r15w
0x18017f9ff  lea     rcx, [rsi+388h]
0x18017fa06  mov     [rcx+10h], r15
0x18017fa0a  cmp     qword ptr [rcx+18h], 7
0x18017fa0f  jbe     short loc_18017FA14
0x18017fa11  mov     rcx, [rcx]
0x18017fa14  mov     [rcx], r15w
0x18017fa18  mov     [rbp+37h+var_98], r15b
0x18017fa1c  mov     rcx, rdi; SRWLock
0x18017fa1f  call    cs:__imp_AcquireSRWLockExclusive
0x18017fa26  nop     dword ptr [rax+rax+00h]
0x18017fa2b  mov     r8, [rbp+37h+var_58]
0x18017fa2f  lea     rdx, [rbp+37h+var_50]
0x18017fa33  mov     rcx, rsi
0x18017fa36  call    ?TryRemoveContextForOperation@ComputeSystemImpl@Details@Hcs@Manager@Container@@AEAA?AV?$optional@UOperationContext@ComputeSystemImpl@Details@Hcs@Manager@Container@@@std@@PEAUHCS_OPERATION__@@@Z; Container::Manager::Hcs::Details::ComputeSystemImpl::TryRemoveContextForOperation(HCS_OPERATION__ *)
0x18017fa3b  mov     rdx, rax
0x18017fa3e  cmp     [rax+18h], r15b
0x18017fa42  jz      short loc_18017FA7D
0x18017fa44  cmp     [rbp+37h+var_98], r15b
0x18017fa48  jz      short loc_18017FA55
0x18017fa4a  lea     rcx, [rbp+37h+operation]
0x18017fa4e  call    ??4OperationContext@ComputeSystemImpl@Details@Hcs@Manager@Container@@QEAAAEAU012345@$$QEAU012345@@Z; Container::Manager::Hcs::Details::ComputeSystemImpl::OperationContext::operator=(Container::Manager::Hcs::Details::ComputeSystemImpl::OperationContext &&)
0x18017fa53  jmp     short loc_18017FAAB
0x18017fa55  mov     rax, [rax]
0x18017fa58  mov     [rbp+37h+operation], rax
0x18017fa5c  mov     [rdx], r15
0x18017fa5f  mov     rcx, [rdx+10h]
0x18017fa63  mov     rax, [rdx+8]
0x18017fa67  mov     [rbp+37h+var_A8], rax
0x18017fa6b  mov     [rbp+37h+var_A0], rcx
0x18017fa6f  mov     [rdx+8], r15
0x18017fa73  mov     [rdx+10h], r15
0x18017fa77  mov     [rbp+37h+var_98], 1
0x18017fa7b  jmp     short loc_18017FAAB
0x18017fa7d  cmp     [rbp+37h+var_98], r15b
0x18017fa81  jz      short loc_18017FAAB
0x18017fa83  mov     rcx, [rbp+37h+var_A0]; this
0x18017fa87  test    rcx, rcx
0x18017fa8a  jz      short loc_18017FA92
0x18017fa8c  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18017fa91  nop
0x18017fa92  mov     rcx, [rbp+37h+operation]; operation
0x18017fa96  test    rcx, rcx
0x18017fa99  jz      short loc_18017FAA7
0x18017fa9b  call    cs:__imp_HcsCloseOperation
0x18017faa2  nop     dword ptr [rax+rax+00h]
0x18017faa7  mov     [rbp+37h+var_98], r15b
0x18017faab  cmp     [rbp+37h+var_38], r15b
0x18017faaf  jz      short loc_18017FAD5
0x18017fab1  mov     rcx, [rbp+37h+var_40]; this
0x18017fab5  test    rcx, rcx
0x18017fab8  jz      short loc_18017FAC0
0x18017faba  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18017fabf  nop
0x18017fac0  mov     rcx, [rbp+37h+var_50]; operation
0x18017fac4  test    rcx, rcx
0x18017fac7  jz      short loc_18017FAD5
0x18017fac9  call    cs:__imp_HcsCloseOperation
0x18017fad0  nop     dword ptr [rax+rax+00h]
0x18017fad5  test    rdi, rdi
0x18017fad8  jz      short loc_18017FAE9
0x18017fada  mov     rcx, rdi; SRWLock
0x18017fadd  call    cs:__imp_ReleaseSRWLockExclusive
0x18017fae4  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
