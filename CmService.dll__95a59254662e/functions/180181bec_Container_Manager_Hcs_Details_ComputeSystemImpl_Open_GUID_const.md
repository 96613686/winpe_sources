# Container::Manager::Hcs::Details::ComputeSystemImpl::Open(_GUID const &)

- ea: `0x180181bec`
- end: `0x180181fdf`
- name: `?Open@ComputeSystemImpl@Details@Hcs@Manager@Container@@QEAAXAEBU_GUID@@@Z`
- size: `1011`
- prototype: `void __fastcall(Container::Manager::Hcs::Details::ComputeSystemImpl *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180123b78`

## callees

- `0x180004bd0`
- `0x180004fc4`
- `0x180007b3c`
- `0x18002c5b4`
- `0x18003d4dc`
- `0x18003de70`
- `0x1800491e8`
- `0x180049230`
- `0x1801260f0`
- `0x180177ac8`
- `0x18017e6b4`
- `0x18017f020`
- `0x180181bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180181d9f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180181d9f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180181e49`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180181e49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180181e03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180181e03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180181e22`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180181e22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180181e6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180181e6a`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsOpenComputeSystem` at `0x180181c6f`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsOpenComputeSystem` at `0x180181c6f`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsGetComputeSystemProperties` at `0x180181cc2`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsGetComputeSystemProperties` at `0x180181cc2`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsSetComputeSystemCallback` at `0x180181dc1`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsSetComputeSystemCallback` at `0x180181dc1`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseComputeSystem` at `0x180181e14`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseComputeSystem` at `0x180181e91`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseComputeSystem` at `0x180181e14`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseComputeSystem` at `0x180181e91`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCreateOperation` at `0x180181c93`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCreateOperation` at `0x180181c93`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x180181e7a`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x180181e7a`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsWaitForOperationResult` at `0x180181ced`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsWaitForOperationResult` at `0x180181ced`

## string_xrefs

- `0x180181ee7`: `onecore\base\gendrv\silos\clem\compute\lib\computesystem.cpp`
- `0x180181f0d`: `onecore\base\gendrv\silos\clem\compute\lib\computesystem.cpp`
- `0x180181f22`: `onecore\base\gendrv\silos\clem\compute\lib\computesystem.cpp`
- `0x180181f45`: `onecore\base\gendrv\silos\clem\compute\lib\computesystem.cpp`
- `0x180181f57`: `onecore\base\gendrv\silos\clem\compute\lib\computesystem.cpp`
- `0x180181f6c`: `onecore\base\gendrv\silos\clem\compute\lib\computesystem.cpp`
- `0x180181f81`: `onecore\base\gendrv\silos\clem\compute\lib\computesystem.cpp`
- `0x180181fa7`: `onecore\base\gendrv\silos\clem\compute\lib\computesystem.cpp`
- `0x180181fcd`: `onecore\base\gendrv\silos\clem\compute\lib\computesystem.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall Container::Manager::Hcs::Details::ComputeSystemImpl::Open(RTL_SRWLOCK *this, const struct _GUID *a2)
{
  int v4; // eax
  HRESULT v5; // eax
  HCS_OPERATION Operation; // rax
  const char *v7; // r9
  HCS_OPERATION v8; // rbx
  HRESULT ComputeSystemProperties; // eax
  HRESULT v10; // eax
  __int64 v11; // rax
  bool v12; // di
  int v13; // edi
  HRESULT v14; // eax
  HCS_SYSTEM *v15; // rsi
  HCS_SYSTEM v16; // r13
  HCS_SYSTEM v17; // r12
  DWORD LastError; // edi
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  HCS_SYSTEM computeSystem; // [rsp+20h] [rbp-E0h] BYREF
  PWSTR resultDocument; // [rsp+28h] [rbp-D8h] BYREF
  PCWSTR id[2]; // [rsp+30h] [rbp-D0h] BYREF
  _WORD v26[8]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v27[3]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v28[8]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v29[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v30[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v31[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v32[32]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v33[32]; // [rsp+F0h] [rbp-10h] BYREF
  int v34; // [rsp+110h] [rbp+10h]
  wil::details::in1diag3 *retaddr; // [rsp+588h] [rbp+488h]

  id[0] = v26;
  id[1] = v26;
  v26[0] = 0;
  v4 = Csl::GuidToString(a2, id);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x12D,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystem.cpp",
      (const char *)(unsigned int)v4,
      (int)computeSystem);
  computeSystem = 0;
  v5 = HcsOpenComputeSystem(id[0], 0x10000000u, &computeSystem);
  if ( v5 < 0 )
  {
    if ( v5 != -2143878896 )
    {
      v20 = wil::verify_hresult<long>((unsigned int)v5);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x13E,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystem.cpp",
        (const char *)v20,
        (int)computeSystem);
    }
    v19 = wil::verify_hresult<long>(2151088390LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13A,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystem.cpp",
      (const char *)v19,
      (int)computeSystem);
  }
  Operation = HcsCreateOperation(0, 0);
  v8 = Operation;
  v27[2] = Operation;
  if ( !Operation )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x144,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystem.cpp",
      v7);
  ComputeSystemProperties = HcsGetComputeSystemProperties(computeSystem, Operation, 0);
  if ( ComputeSystemProperties < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x148,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystem.cpp",
      (const char *)(unsigned int)ComputeSystemProperties,
      (int)computeSystem);
  resultDocument = 0;
  v10 = HcsWaitForOperationResult(v8, 0xFFFFFFFF, &resultDocument);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14B,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystem.cpp",
      (const char *)(unsigned int)v10,
      (int)computeSystem);
  Schema::Responses::System::Properties::Properties((Schema::Responses::System::Properties *)v33);
  v11 = -1;
  do
    ++v11;
  while ( resultDocument[v11] );
  v27[0] = resultDocument;
  v27[1] = v11;
  Marshal::JsonParser::JsonParser(v30, v27);
  Marshal::FromJson<Schema::Responses::System::Properties,>(v28, v30, v33);
  std::wstring::~wstring(v32);
  std::wstring::~wstring(v31);
  v12 = v28[0] == 0;
  std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(v29);
  if ( v12 )
  {
    v21 = wil::verify_hresult<long>(2151088397LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x150,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystem.cpp",
      (const char *)v21,
      (int)computeSystem);
  }
  if ( v34 )
  {
    if ( v34 != 1 )
    {
      v22 = wil::verify_hresult<long>(2147549183LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x168,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystem.cpp",
        (const char *)v22,
        (int)computeSystem);
    }
    v13 = 1;
  }
  else
  {
    v13 = 2;
  }
  AcquireSRWLockExclusive(this + 4);
  v27[0] = this + 4;
  v14 = HcsSetComputeSystemCallback(
          computeSystem,
          HcsEventOptionNone,
          this,
          Container::Manager::Hcs::Details::ComputeSystemImpl::OnComputeSystemEvent);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x175,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystem.cpp",
      (const char *)(unsigned int)v14,
      (int)computeSystem);
  *(struct _GUID *)&this->Ptr = *a2;
  LODWORD(this[2].Ptr) = v13;
  v15 = (HCS_SYSTEM *)&this[3];
  if ( &this[3] != (RTL_SRWLOCK *)&computeSystem )
  {
    v16 = computeSystem;
    v17 = *v15;
    if ( *v15 )
    {
      LastError = GetLastError();
      HcsCloseComputeSystem(v17);
      SetLastError(LastError);
    }
    *v15 = v16;
    computeSystem = 0;
  }
  LODWORD(this[5].Ptr) = 1;
  if ( this != (RTL_SRWLOCK *)-32LL )
    ReleaseSRWLockExclusive(this + 4);
  Schema::Responses::System::Properties::~Properties((Schema::Responses::System::Properties *)v33);
  if ( resultDocument )
    LocalFree(resultDocument);
  HcsCloseOperation(v8);
  if ( computeSystem )
    HcsCloseComputeSystem(computeSystem);
  if ( id[0] != v26 )
    operator delete((void *)id[0], (const struct std::nothrow_t *)&std::nothrow);
}

```

## disassembly

```asm
0x180181bec  mov     [rsp-8+arg_10], rbx
0x180181bf1  push    rbp
0x180181bf2  push    rsi
0x180181bf3  push    rdi
0x180181bf4  push    r12
0x180181bf6  push    r13
0x180181bf8  push    r14
0x180181bfa  push    r15
0x180181bfc  lea     rbp, [rsp-450h]
0x180181c04  sub     rsp, 550h
0x180181c0b  mov     rax, cs:__security_cookie
0x180181c12  xor     rax, rsp
0x180181c15  mov     [rbp+480h+var_40], rax
0x180181c1c  mov     rsi, rdx
0x180181c1f  mov     r14, rcx
0x180181c22  xor     r12d, r12d
0x180181c25  lea     rax, [rsp+580h+var_540]
0x180181c2a  mov     [rsp+580h+id], rax
0x180181c2f  lea     rax, [rsp+580h+var_540]
0x180181c34  mov     [rsp+580h+var_548], rax
0x180181c39  mov     [rsp+580h+var_540], r12w
0x180181c3f  lea     rdx, [rsp+580h+id]
0x180181c44  mov     rcx, rsi
0x180181c47  call    ?GuidToString@Csl@@YAJAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Csl::GuidToString(_GUID const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x180181c4c  mov     rcx, [rbp+488h]; this
0x180181c53  test    eax, eax
0x180181c55  js      loc_180181F1F
0x180181c5b  mov     [rsp+580h+computeSystem], r12; int
0x180181c60  lea     r8, [rsp+580h+computeSystem]; computeSystem
0x180181c65  mov     edx, 10000000h; requestedAccess
0x180181c6a  mov     rcx, [rsp+580h+id]; id
0x180181c6f  call    cs:__imp_HcsOpenComputeSystem
0x180181c76  nop     dword ptr [rax+rax+00h]
0x180181c7b  test    eax, eax
0x180181c7d  jns     short loc_180181C8F
0x180181c7f  cmp     eax, 80370110h
0x180181c84  jz      loc_180181EF9
0x180181c8a  jmp     loc_180181F34
0x180181c8f  xor     edx, edx; callback
0x180181c91  xor     ecx, ecx; context
0x180181c93  call    cs:__imp_HcsCreateOperation
0x180181c9a  nop     dword ptr [rax+rax+00h]
0x180181c9f  mov     rbx, rax
0x180181ca2  mov     [rsp+580h+var_520], rax
0x180181ca7  mov     rcx, [rbp+488h]; this
0x180181cae  test    rax, rax
0x180181cb1  jz      loc_180181F57
0x180181cb7  xor     r8d, r8d; propertyQuery
0x180181cba  mov     rdx, rax; operation
0x180181cbd  mov     rcx, [rsp+580h+computeSystem]; computeSystem
0x180181cc2  call    cs:__imp_HcsGetComputeSystemProperties
0x180181cc9  nop     dword ptr [rax+rax+00h]
0x180181cce  mov     rcx, [rbp+488h]; this
0x180181cd5  test    eax, eax
0x180181cd7  js      loc_180181F69
0x180181cdd  mov     [rsp+580h+resultDocument], r12
0x180181ce2  lea     r8, [rsp+580h+resultDocument]; resultDocument
0x180181ce7  or      edx, 0FFFFFFFFh; timeoutMs
0x180181cea  mov     rcx, rbx; operation
0x180181ced  call    cs:__imp_HcsWaitForOperationResult
0x180181cf4  nop     dword ptr [rax+rax+00h]
0x180181cf9  mov     rcx, [rbp+488h]; this
0x180181d00  test    eax, eax
0x180181d02  js      loc_180181F7E
0x180181d08  lea     rcx, [rbp+480h+var_490]; this
0x180181d0c  call    ??0Properties@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::Properties::Properties(void)
0x180181d11  nop
0x180181d12  mov     rcx, [rsp+580h+resultDocument]
0x180181d17  or      rax, 0FFFFFFFFFFFFFFFFh
0x180181d1b  inc     rax
0x180181d1e  cmp     [rcx+rax*2], r12w
0x180181d23  jnz     short loc_180181D1B
0x180181d25  mov     [rsp+580h+var_530], rcx
0x180181d2a  mov     [rsp+580h+var_528], rax
0x180181d2f  lea     rdx, [rsp+580h+var_530]
0x180181d34  lea     rcx, [rbp+480h+var_4F0]
0x180181d38  call    ??0JsonParser@Marshal@@QEAA@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; Marshal::JsonParser::JsonParser(std::basic_string_view<ushort>)
0x180181d3d  nop
0x180181d3e  lea     r8, [rbp+480h+var_490]
0x180181d42  lea     rdx, [rbp+480h+var_4F0]
0x180181d46  lea     rcx, [rsp+580h+var_518]
0x180181d4b  call    ??$FromJson@UProperties@System@Responses@Schema@@$$V@Marshal@@YA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@AEAVJsonParser@0@PEAUProperties@System@Responses@Schema@@W4UnmarshalFlags@0@@Z; Marshal::FromJson<Schema::Responses::System::Properties,>(Marshal::JsonParser &,Schema::Responses::System::Properties *,Marshal::UnmarshalFlags)
0x180181d50  nop
0x180181d51  lea     rcx, [rbp+480h+var_4B0]; void *
0x180181d55  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180181d5a  lea     rcx, [rbp+480h+var_4D0]; void *
0x180181d5e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180181d63  cmp     [rsp+580h+var_518], r12b
0x180181d68  setz    dil
0x180181d6c  lea     rcx, [rsp+580h+var_510]
0x180181d71  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x180181d76  test    dil, dil
0x180181d79  jnz     loc_180181F93
0x180181d7f  mov     ecx, [rbp+480h+var_470]
0x180181d82  test    ecx, ecx
0x180181d84  jz      short loc_180181D93
0x180181d86  cmp     ecx, 1
0x180181d89  jnz     loc_180181FB9
0x180181d8f  mov     edi, ecx
0x180181d91  jmp     short loc_180181D98
0x180181d93  mov     edi, 2
0x180181d98  lea     r15, [r14+20h]
0x180181d9c  mov     rcx, r15; SRWLock
0x180181d9f  call    cs:__imp_AcquireSRWLockExclusive
0x180181da6  nop     dword ptr [rax+rax+00h]
0x180181dab  mov     [rsp+580h+var_530], r15
0x180181db0  lea     r9, ?OnComputeSystemEvent@ComputeSystemImpl@Details@Hcs@Manager@Container@@CAXPEAUHCS_EVENT@@PEAX@Z; callback
0x180181db7  mov     r8, r14; context
0x180181dba  xor     edx, edx; callbackOptions
0x180181dbc  mov     rcx, [rsp+580h+computeSystem]; computeSystem
0x180181dc1  call    cs:__imp_HcsSetComputeSystemCallback
0x180181dc8  nop     dword ptr [rax+rax+00h]
0x180181dcd  mov     rcx, [rbp+488h]; this
0x180181dd4  test    eax, eax
0x180181dd6  js      loc_180181EE4
0x180181ddc  movups  xmm0, xmmword ptr [rsi]
0x180181ddf  movdqu  xmmword ptr [r14], xmm0
0x180181de4  mov     [r14+10h], edi
0x180181de8  lea     rsi, [r14+18h]
0x180181dec  lea     rax, [rsp+580h+computeSystem]
0x180181df1  cmp     rsi, rax
0x180181df4  jz      short loc_180181E39
0x180181df6  mov     r13, [rsp+580h+computeSystem]
0x180181dfb  mov     r12, [rsi]
0x180181dfe  test    r12, r12
0x180181e01  jz      short loc_180181E2E
0x180181e03  call    cs:__imp_GetLastError
0x180181e0a  nop     dword ptr [rax+rax+00h]
0x180181e0f  mov     edi, eax
0x180181e11  mov     rcx, r12; computeSystem
0x180181e14  call    cs:__imp_HcsCloseComputeSystem
0x180181e1b  nop     dword ptr [rax+rax+00h]
0x180181e20  mov     ecx, edi; dwErrCode
0x180181e22  call    cs:__imp_SetLastError
0x180181e29  nop     dword ptr [rax+rax+00h]
0x180181e2e  mov     [rsi], r13
0x180181e31  xor     r12d, r12d
0x180181e34  mov     [rsp+580h+computeSystem], r12
0x180181e39  mov     dword ptr [r14+28h], 1
0x180181e41  test    r15, r15
0x180181e44  jz      short loc_180181E56
0x180181e46  mov     rcx, r15; SRWLock
0x180181e49  call    cs:__imp_ReleaseSRWLockExclusive
0x180181e50  nop     dword ptr [rax+rax+00h]
0x180181e55  nop
0x180181e56  lea     rcx, [rbp+480h+var_490]; this
0x180181e5a  call    ??1Properties@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::Properties::~Properties(void)
0x180181e5f  nop
0x180181e60  mov     rcx, [rsp+580h+resultDocument]; hMem
0x180181e65  test    rcx, rcx
0x180181e68  jz      short loc_180181E77
0x180181e6a  call    cs:__imp_LocalFree
0x180181e71  nop     dword ptr [rax+rax+00h]
0x180181e76  nop
0x180181e77  mov     rcx, rbx; operation
0x180181e7a  call    cs:__imp_HcsCloseOperation
0x180181e81  nop     dword ptr [rax+rax+00h]
0x180181e86  nop
0x180181e87  mov     rcx, [rsp+580h+computeSystem]; computeSystem
0x180181e8c  test    rcx, rcx
0x180181e8f  jz      short loc_180181E9E
0x180181e91  call    cs:__imp_HcsCloseComputeSystem
0x180181e98  nop     dword ptr [rax+rax+00h]
0x180181e9d  nop
0x180181e9e  lea     rax, [rsp+580h+var_540]
0x180181ea3  mov     rcx, [rsp+580h+id]; void *
0x180181ea8  cmp     rcx, rax
0x180181eab  jz      short loc_180181EB9
0x180181ead  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180181eb4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180181eb9  mov     rcx, [rbp+480h+var_40]
0x180181ec0  xor     rcx, rsp; StackCookie
0x180181ec3  call    __security_check_cookie
0x180181ec8  mov     rbx, [rsp+580h+arg_10]
0x180181ed0  add     rsp, 550h
0x180181ed7  pop     r15
0x180181ed9  pop     r14
0x180181edb  pop     r13
0x180181edd  pop     r12
0x180181edf  pop     rdi
0x180181ee0  pop     rsi
0x180181ee1  pop     rbp
0x180181ee2  retn
0x180181ee4  mov     r9d, eax; char *
0x180181ee7  lea     r8, aOnecoreBaseGen_50; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x180181eee  mov     edx, 175h; void *
0x180181ef3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180181ef9  mov     ecx, 80370106h
0x180181efe  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180181f03  mov     r9d, eax; char *
0x180181f06  mov     rcx, [rbp+488h]; this
0x180181f0d  lea     r8, aOnecoreBaseGen_50; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x180181f14  mov     edx, 13Ah; void *
0x180181f19  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180181f1f  mov     r9d, eax; char *
0x180181f22  lea     r8, aOnecoreBaseGen_50; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x180181f29  mov     edx, 12Dh; void *
0x180181f2e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180181f34  mov     ecx, eax
0x180181f36  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180181f3b  mov     r9d, eax; char *
0x180181f3e  mov     rcx, [rbp+488h]; this
0x180181f45  lea     r8, aOnecoreBaseGen_50; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x180181f4c  mov     edx, 13Eh; void *
0x180181f51  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180181f57  lea     r8, aOnecoreBaseGen_50; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x180181f5e  mov     edx, 144h; void *
0x180181f63  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180181f69  mov     r9d, eax; char *
0x180181f6c  lea     r8, aOnecoreBaseGen_50; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x180181f73  mov     edx, 148h; void *
0x180181f78  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180181f7e  mov     r9d, eax; char *
0x180181f81  lea     r8, aOnecoreBaseGen_50; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x180181f88  mov     edx, 14Bh; void *
0x180181f8d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180181f93  mov     ecx, 8037010Dh
0x180181f98  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180181f9d  mov     r9d, eax; char *
0x180181fa0  mov     rcx, [rbp+488h]; this
0x180181fa7  lea     r8, aOnecoreBaseGen_50; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x180181fae  mov     edx, 150h; void *
0x180181fb3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180181fb9  mov     ecx, 8000FFFFh
0x180181fbe  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180181fc3  mov     r9d, eax; char *
0x180181fc6  mov     rcx, [rbp+488h]; this
0x180181fcd  lea     r8, aOnecoreBaseGen_50; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x180181fd4  mov     edx, 168h; void *
0x180181fd9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
