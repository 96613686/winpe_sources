# Container::Manager::Hcs::Details::ComputeSystemImpl::CreateAsync(_GUID const &,Container::Manager::Hcs::ComputeSystemType,std::optional<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::optional<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::optional<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18017f7d4`
- end: `0x18017fce9`
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
- `0x180176244`
- `0x18017f7d4`
- `0x18017fcf0`
- `0x180182288`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18017f851`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18017fb8f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18017f851`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18017fb8f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18017f9ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18017fc4d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18017f9ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18017fc4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017f93e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017fafb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017f93e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017fafb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18017f95e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18017fb1a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18017f95e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18017fb1a`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCreateComputeSystem` at `0x18017f8e3`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCreateComputeSystem` at `0x18017f8e3`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsTerminateComputeSystem` at `0x18017fabb`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsTerminateComputeSystem` at `0x18017fabb`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsSetComputeSystemCallback` at `0x18017fa10`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsSetComputeSystemCallback` at `0x18017fa10`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseComputeSystem` at `0x18017f950`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseComputeSystem` at `0x18017f9d7`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseComputeSystem` at `0x18017fb0c`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseComputeSystem` at `0x18017f950`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseComputeSystem` at `0x18017f9d7`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseComputeSystem` at `0x18017fb0c`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCreateOperation` at `0x18017fa9d`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCreateOperation` at `0x18017fa9d`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x18017fae6`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x18017fc0b`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x18017fc39`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x18017fc77`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x18017fae6`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x18017fc0b`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x18017fc39`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x18017fc77`

## string_xrefs

- `0x18017fad2`: `onecore\base\gendrv\silos\clem\compute\lib\computesystem.cpp`
- `0x18017fca4`: `onecore\base\gendrv\silos\clem\compute\lib\computesystem.cpp`
- `0x18017fcc2`: `onecore\base\gendrv\silos\clem\compute\lib\computesystem.cpp`
- `0x18017fcd7`: `onecore\base\gendrv\silos\clem\compute\lib\computesystem.cpp`

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
    v30 = ((__int64 (*)(void))wil::verify_hresult<long>)();
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
0x18017f7d4  mov     rax, rsp
0x18017f7d7  mov     [rax+8], rbx
0x18017f7db  mov     [rax+20h], r9d
0x18017f7df  mov     [rax+18h], r8
0x18017f7e3  mov     [rax+10h], rdx
0x18017f7e7  push    rbp
0x18017f7e8  push    rsi
0x18017f7e9  push    rdi
0x18017f7ea  push    r12
0x18017f7ec  push    r13
0x18017f7ee  push    r14
0x18017f7f0  push    r15
0x18017f7f2  lea     rbp, [rax-3Fh]
0x18017f7f6  sub     rsp, 0C0h
0x18017f7fd  mov     r13, rdx
0x18017f800  mov     rsi, rcx
0x18017f803  xor     r15d, r15d
0x18017f806  mov     [rbp+37h+var_90], r15d
0x18017f80a  lea     rax, [rbp+37h+var_70]
0x18017f80e  mov     [rbp+37h+id], rax
0x18017f812  lea     rax, [rbp+37h+var_70]
0x18017f816  mov     [rbp+37h+var_78], rax
0x18017f81a  mov     [rbp+37h+var_70], r15w
0x18017f81f  lea     rdx, [rbp+37h+id]
0x18017f823  mov     rcx, r8
0x18017f826  call    ?GuidToString@Csl@@YAJAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Csl::GuidToString(_GUID const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18017f82b  mov     rcx, [rbp+3Fh]; this
0x18017f82f  test    eax, eax
0x18017f831  js      loc_18017FCD4
0x18017f837  mov     [r13+0], r15
0x18017f83b  mov     [r13+8], r15
0x18017f83f  mov     [r13+10h], r15
0x18017f843  mov     [rbp+37h+var_90], 1
0x18017f84a  lea     rdi, [rsi+20h]
0x18017f84e  mov     rcx, rdi; SRWLock
0x18017f851  call    cs:__imp_AcquireSRWLockExclusive
0x18017f858  nop     dword ptr [rax+rax+00h]
0x18017f85d  mov     [rbp+37h+var_88], rdi
0x18017f861  lea     rdx, [rbp+37h+operation]
0x18017f865  mov     rcx, rsi
0x18017f868  call    ?CreateOperationsForAsyncCall@ComputeSystemImpl@Details@Hcs@Manager@Container@@AEAA?AV?$tuple@PEAUHCS_OPERATION__@@V?$AsyncOperation@X@Csl@@@std@@XZ; Container::Manager::Hcs::Details::ComputeSystemImpl::CreateOperationsForAsyncCall(void)
0x18017f86d  mov     r14, [rax+18h]
0x18017f871  mov     [rbp+37h+var_58], r14
0x18017f875  mov     rdx, rax
0x18017f878  mov     rcx, r13
0x18017f87b  call    ??4?$AsyncOperation@X@Csl@@QEAAAEAV01@$$QEAV01@@Z; Csl::AsyncOperation<void>::operator=(Csl::AsyncOperation<void> &&)
0x18017f880  lea     rcx, [rbp+37h+operation]
0x18017f884  call    ?Cleanup@?$AsyncOperation@X@Csl@@AEAAXXZ; Csl::AsyncOperation<void>::Cleanup(void)
0x18017f889  nop
0x18017f88a  mov     rcx, [rbp+37h+var_A0]; this
0x18017f88e  test    rcx, rcx
0x18017f891  jz      short loc_18017F899
0x18017f893  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18017f898  nop
0x18017f899  mov     rbx, [rbp+37h+operation]
0x18017f89d  mov     [rbp+37h+operation], r15
0x18017f8a1  test    rbx, rbx
0x18017f8a4  jz      short loc_18017F8BC
0x18017f8a6  mov     rcx, rbx
0x18017f8a9  call    ??1?$AsyncOperationImpl@X@Details@Csl@@QEAA@XZ; Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>(void)
0x18017f8ae  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x18017f8b3  mov     rcx, rbx; void *
0x18017f8b6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18017f8bb  nop
0x18017f8bc  mov     [rsp+0F0h+computeSystem], r15
0x18017f8c1  mov     rdx, [rbp+37h+arg_38]
0x18017f8c5  cmp     qword ptr [rdx+18h], 7
0x18017f8ca  jbe     short loc_18017F8CF
0x18017f8cc  mov     rdx, [rdx]; configuration
0x18017f8cf  lea     rax, [rsp+0F0h+computeSystem]
0x18017f8d4  mov     [rsp+20h], rax; int
0x18017f8d9  xor     r9d, r9d; securityDescriptor
0x18017f8dc  mov     r8, r14; operation
0x18017f8df  mov     rcx, [rbp+37h+id]; id
0x18017f8e3  call    cs:__imp_HcsCreateComputeSystem
0x18017f8ea  nop     dword ptr [rax+rax+00h]
0x18017f8ef  mov     ebx, eax
0x18017f8f1  mov     dword ptr [rsp+0F0h+var_C0], eax
0x18017f8f5  mov     r14, [rbp+37h+arg_30]
0x18017f8f9  mov     r15, [rbp+37h+arg_28]
0x18017f8fd  mov     r12, [rbp+37h+arg_20]
0x18017f901  test    eax, eax
0x18017f903  js      loc_18017F9CD
0x18017f909  mov     rax, [rbp+37h+arg_10]
0x18017f90d  movups  xmm0, xmmword ptr [rax]
0x18017f910  movdqu  xmmword ptr [rsi], xmm0
0x18017f914  mov     eax, [rbp+37h+arg_18]
0x18017f917  mov     [rsi+10h], eax
0x18017f91a  lea     r13, [rsi+18h]
0x18017f91e  lea     rax, [rsp+0F0h+computeSystem]
0x18017f923  cmp     r13, rax
0x18017f926  jz      short loc_18017F97F
0x18017f928  mov     rax, [rsp+0F0h+computeSystem]
0x18017f92d  mov     [rbp+37h+var_88], rax
0x18017f931  mov     rax, [r13+0]
0x18017f935  mov     [rbp+37h+var_60], rax
0x18017f939  test    rax, rax
0x18017f93c  jz      short loc_18017F96E
0x18017f93e  call    cs:__imp_GetLastError
0x18017f945  nop     dword ptr [rax+rax+00h]
0x18017f94a  mov     ebx, eax
0x18017f94c  mov     rcx, [rbp+37h+var_60]; computeSystem
0x18017f950  call    cs:__imp_HcsCloseComputeSystem
0x18017f957  nop     dword ptr [rax+rax+00h]
0x18017f95c  mov     ecx, ebx; dwErrCode
0x18017f95e  call    cs:__imp_SetLastError
0x18017f965  nop     dword ptr [rax+rax+00h]
0x18017f96a  mov     ebx, dword ptr [rsp+0F0h+var_C0]
0x18017f96e  mov     rax, [rbp+37h+var_88]
0x18017f972  mov     [r13+0], rax
0x18017f976  mov     [rsp+0F0h+computeSystem], 0
0x18017f97f  mov     dword ptr [rsi+28h], 1
0x18017f986  cmp     byte ptr [r12+20h], 0
0x18017f98c  jz      short loc_18017F99D
0x18017f98e  lea     rcx, [rsi+348h]
0x18017f995  mov     rdx, r12
0x18017f998  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18017f99d  cmp     byte ptr [r15+20h], 0
0x18017f9a2  jz      short loc_18017F9B3
0x18017f9a4  lea     rcx, [rsi+388h]
0x18017f9ab  mov     rdx, r15
0x18017f9ae  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18017f9b3  cmp     byte ptr [r14+20h], 0
0x18017f9b8  jz      short loc_18017F9C9
0x18017f9ba  lea     rcx, [rsi+3A8h]
0x18017f9c1  mov     rdx, r14
0x18017f9c4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18017f9c9  mov     r13, [rbp+37h+arg_8]
0x18017f9cd  mov     rcx, [rsp+0F0h+computeSystem]; computeSystem
0x18017f9d2  test    rcx, rcx
0x18017f9d5  jz      short loc_18017F9E4
0x18017f9d7  call    cs:__imp_HcsCloseComputeSystem
0x18017f9de  nop     dword ptr [rax+rax+00h]
0x18017f9e3  nop
0x18017f9e4  test    rdi, rdi
0x18017f9e7  jz      short loc_18017F9F8
0x18017f9e9  mov     rcx, rdi; SRWLock
0x18017f9ec  call    cs:__imp_ReleaseSRWLockExclusive
0x18017f9f3  nop     dword ptr [rax+rax+00h]
0x18017f9f8  test    ebx, ebx
0x18017f9fa  js      loc_18017FA8C
0x18017fa00  lea     r9, ?OnComputeSystemEvent@ComputeSystemImpl@Details@Hcs@Manager@Container@@CAXPEAUHCS_EVENT@@PEAX@Z; callback
0x18017fa07  mov     r8, rsi; context
0x18017fa0a  xor     edx, edx; callbackOptions
0x18017fa0c  mov     rcx, [rsi+18h]; computeSystem
0x18017fa10  call    cs:__imp_HcsSetComputeSystemCallback
0x18017fa17  nop     dword ptr [rax+rax+00h]
0x18017fa1c  mov     dword ptr [rsp+0F0h+var_C0], eax
0x18017fa20  xor     ebx, ebx
0x18017fa22  test    eax, eax
0x18017fa24  js      short loc_18017FA8C
0x18017fa26  lea     rax, [rbp+37h+var_70]
0x18017fa2a  mov     rcx, [rbp+37h+id]; void *
0x18017fa2e  cmp     rcx, rax
0x18017fa31  jz      short loc_18017FA40
0x18017fa33  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18017fa3a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18017fa3f  nop
0x18017fa40  cmp     [r12+20h], bl
0x18017fa45  jz      short loc_18017FA50
0x18017fa47  mov     rcx, r12; void *
0x18017fa4a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18017fa4f  nop
0x18017fa50  cmp     [r15+20h], bl
0x18017fa54  jz      short loc_18017FA5F
0x18017fa56  mov     rcx, r15; void *
0x18017fa59  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18017fa5e  nop
0x18017fa5f  cmp     [r14+20h], bl
0x18017fa63  jz      short loc_18017FA6D
0x18017fa65  mov     rcx, r14; void *
0x18017fa68  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18017fa6d  mov     rax, r13
0x18017fa70  mov     rbx, [rsp+0F0h+arg_0]
0x18017fa78  add     rsp, 0C0h
0x18017fa7f  pop     r15
0x18017fa81  pop     r14
0x18017fa83  pop     r13
0x18017fa85  pop     r12
0x18017fa87  pop     rdi
0x18017fa88  pop     rsi
0x18017fa89  pop     rbp
0x18017fa8a  retn
0x18017fa8c  xor     r15d, r15d
0x18017fa8f  cmp     [rsi+18h], r15
0x18017fa93  jz      loc_18017FB88
0x18017fa99  xor     edx, edx; callback
0x18017fa9b  xor     ecx, ecx; context
0x18017fa9d  call    cs:__imp_HcsCreateOperation
0x18017faa4  nop     dword ptr [rax+rax+00h]
0x18017faa9  mov     rbx, rax
0x18017faac  test    rax, rax
0x18017faaf  jz      short loc_18017FAF2
0x18017fab1  xor     r8d, r8d; options
0x18017fab4  mov     rdx, rax; operation
0x18017fab7  mov     rcx, [rsi+18h]; computeSystem
0x18017fabb  call    cs:__imp_HcsTerminateComputeSystem
0x18017fac2  nop     dword ptr [rax+rax+00h]
0x18017fac7  mov     rcx, [rbp+3Fh]; this
0x18017facb  test    eax, eax
0x18017facd  jns     short loc_18017FAE3
0x18017facf  mov     r9d, eax; char *
0x18017fad2  lea     r8, aOnecoreBaseGen_50; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x18017fad9  mov     edx, 0E2h; void *
0x18017fade  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18017fae3  mov     rcx, rbx; operation
0x18017fae6  call    cs:__imp_HcsCloseOperation
0x18017faed  nop     dword ptr [rax+rax+00h]
0x18017faf2  mov     r14, [rsi+18h]
0x18017faf6  test    r14, r14
0x18017faf9  jz      short loc_18017FB26
0x18017fafb  call    cs:__imp_GetLastError
0x18017fb02  nop     dword ptr [rax+rax+00h]
0x18017fb07  mov     ebx, eax
0x18017fb09  mov     rcx, r14; computeSystem
0x18017fb0c  call    cs:__imp_HcsCloseComputeSystem
0x18017fb13  nop     dword ptr [rax+rax+00h]
0x18017fb18  mov     ecx, ebx; dwErrCode
0x18017fb1a  call    cs:__imp_SetLastError
0x18017fb21  nop     dword ptr [rax+rax+00h]
0x18017fb26  mov     [rsi+18h], r15
0x18017fb2a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18017fb31  movdqu  xmmword ptr [rsi], xmm0
0x18017fb35  mov     [rsi+10h], r15d
0x18017fb39  mov     [rsi+28h], r15d
0x18017fb3d  lea     rcx, [rsi+348h]
0x18017fb44  mov     [rcx+10h], r15
0x18017fb48  cmp     qword ptr [rcx+18h], 7
0x18017fb4d  jbe     short loc_18017FB52
0x18017fb4f  mov     rcx, [rcx]
0x18017fb52  mov     [rcx], r15w
0x18017fb56  lea     rcx, [rsi+3A8h]
0x18017fb5d  mov     [rcx+10h], r15
0x18017fb61  cmp     qword ptr [rcx+18h], 7
0x18017fb66  jbe     short loc_18017FB6B
0x18017fb68  mov     rcx, [rcx]
0x18017fb6b  mov     [rcx], r15w
0x18017fb6f  lea     rcx, [rsi+388h]
0x18017fb76  mov     [rcx+10h], r15
0x18017fb7a  cmp     qword ptr [rcx+18h], 7
0x18017fb7f  jbe     short loc_18017FB84
0x18017fb81  mov     rcx, [rcx]
0x18017fb84  mov     [rcx], r15w
0x18017fb88  mov     [rbp+37h+var_98], r15b
0x18017fb8c  mov     rcx, rdi; SRWLock
0x18017fb8f  call    cs:__imp_AcquireSRWLockExclusive
0x18017fb96  nop     dword ptr [rax+rax+00h]
0x18017fb9b  mov     r8, [rbp+37h+var_58]
0x18017fb9f  lea     rdx, [rbp+37h+var_50]
0x18017fba3  mov     rcx, rsi
0x18017fba6  call    ?TryRemoveContextForOperation@ComputeSystemImpl@Details@Hcs@Manager@Container@@AEAA?AV?$optional@UOperationContext@ComputeSystemImpl@Details@Hcs@Manager@Container@@@std@@PEAUHCS_OPERATION__@@@Z; Container::Manager::Hcs::Details::ComputeSystemImpl::TryRemoveContextForOperation(HCS_OPERATION__ *)
0x18017fbab  mov     rdx, rax
0x18017fbae  cmp     [rax+18h], r15b
0x18017fbb2  jz      short loc_18017FBED
0x18017fbb4  cmp     [rbp+37h+var_98], r15b
0x18017fbb8  jz      short loc_18017FBC5
0x18017fbba  lea     rcx, [rbp+37h+operation]
0x18017fbbe  call    ??4OperationContext@ComputeSystemImpl@Details@Hcs@Manager@Container@@QEAAAEAU012345@$$QEAU012345@@Z; Container::Manager::Hcs::Details::ComputeSystemImpl::OperationContext::operator=(Container::Manager::Hcs::Details::ComputeSystemImpl::OperationContext &&)
0x18017fbc3  jmp     short loc_18017FC1B
0x18017fbc5  mov     rax, [rax]
0x18017fbc8  mov     [rbp+37h+operation], rax
0x18017fbcc  mov     [rdx], r15
0x18017fbcf  mov     rcx, [rdx+10h]
0x18017fbd3  mov     rax, [rdx+8]
0x18017fbd7  mov     [rbp+37h+var_A8], rax
0x18017fbdb  mov     [rbp+37h+var_A0], rcx
0x18017fbdf  mov     [rdx+8], r15
0x18017fbe3  mov     [rdx+10h], r15
0x18017fbe7  mov     [rbp+37h+var_98], 1
0x18017fbeb  jmp     short loc_18017FC1B
0x18017fbed  cmp     [rbp+37h+var_98], r15b
0x18017fbf1  jz      short loc_18017FC1B
0x18017fbf3  mov     rcx, [rbp+37h+var_A0]; this
0x18017fbf7  test    rcx, rcx
0x18017fbfa  jz      short loc_18017FC02
0x18017fbfc  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18017fc01  nop
0x18017fc02  mov     rcx, [rbp+37h+operation]; operation
0x18017fc06  test    rcx, rcx
0x18017fc09  jz      short loc_18017FC17
0x18017fc0b  call    cs:__imp_HcsCloseOperation
0x18017fc12  nop     dword ptr [rax+rax+00h]
0x18017fc17  mov     [rbp+37h+var_98], r15b
0x18017fc1b  cmp     [rbp+37h+var_38], r15b
0x18017fc1f  jz      short loc_18017FC45
0x18017fc21  mov     rcx, [rbp+37h+var_40]; this
0x18017fc25  test    rcx, rcx
0x18017fc28  jz      short loc_18017FC30
0x18017fc2a  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18017fc2f  nop
0x18017fc30  mov     rcx, [rbp+37h+var_50]; operation
0x18017fc34  test    rcx, rcx
0x18017fc37  jz      short loc_18017FC45
0x18017fc39  call    cs:__imp_HcsCloseOperation
0x18017fc40  nop     dword ptr [rax+rax+00h]
0x18017fc45  test    rdi, rdi
0x18017fc48  jz      short loc_18017FC59
0x18017fc4a  mov     rcx, rdi; SRWLock
0x18017fc4d  call    cs:__imp_ReleaseSRWLockExclusive
0x18017fc54  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
