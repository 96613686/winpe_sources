# VsmUtils::Vtl0Tpm::Initialize(void *)

- ea: `0x180076650`
- end: `0x18007679a`
- name: `?Initialize@Vtl0Tpm@VsmUtils@@QEAAJPEAX@Z`
- size: `330`
- prototype: `__int64 __fastcall(VsmUtils::Vtl0Tpm *__hidden this, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012070`

## callees

- `0x18000d62c`
- `0x1800108e4`
- `0x18001cb98`
- `0x18002bfec`
- `0x18004849c`
- `0x18006f1b4`
- `0x18007619c`
- `0x18007626c`
- `0x180076650`
- `0x1800769d4`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x18007668b`
- `ncrypt!NCryptOpenStorageProvider` at `0x18007668b`
- `ncrypt!NCryptGetProperty` at `0x180076718`
- `ncrypt!NCryptGetProperty` at `0x180076718`
- `ncrypt!NCryptSetProperty` at `0x1800766c1`
- `ncrypt!NCryptSetProperty` at `0x1800766c1`

## string_xrefs

- `0x1800766d2`: `onecore\ds\security\trustlet\utils\vtl0\lib\vtl0tpmcommands.cpp`
- `0x180076729`: `onecore\ds\security\trustlet\utils\vtl0\lib\vtl0tpmcommands.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall VsmUtils::Vtl0Tpm::Initialize(VsmUtils::Vtl0Tpm *this, void *a2)
{
  SECURITY_STATUS Property; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  SECURITY_STATUS v6; // eax
  __int64 v7; // rax
  int dwFlags; // [rsp+20h] [rbp-40h]
  int dwFlagsa; // [rsp+20h] [rbp-40h]
  __int64 v11; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v12[16]; // [rsp+38h] [rbp-28h] BYREF
  _BYTE v13[24]; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  void *pcbResult; // [rsp+88h] [rbp+28h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+90h] [rbp+30h] BYREF
  __int64 pbOutput; // [rsp+98h] [rbp+38h] BYREF

  pcbResult = a2;
  v11 = 0;
  phProvider = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
    &phProvider,
    0);
  Property = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0);
  v4 = Property;
  if ( Property >= 0 )
  {
    v6 = NCryptSetProperty(phProvider, L"PCP_SESSIONID", (PBYTE)&byte_18009ADA0, 0x10u, 0);
    if ( v6 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x15F,
        (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl0\\lib\\vtl0tpmcommands.cpp",
        (const char *)(unsigned int)v6,
        dwFlagsa);
    pbOutput = 0;
    LODWORD(pcbResult) = 0;
    Property = NCryptGetProperty(phProvider, L"PCP_PLATFORMHANDLE", (PBYTE)&pbOutput, 8u, (DWORD *)&pcbResult, 0);
    v4 = Property;
    if ( Property >= 0 )
    {
      v7 = lambda_574365f21261df146e143cea233d4554_::_lambda_574365f21261df146e143cea233d4554_(
             v13,
             this,
             &v11,
             &pbOutput);
      std::thread::thread__lambda_574365f21261df146e143cea233d4554__0_(v12, v7);
      std::thread::detach((std::thread *)v12);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>::operator=(
        this,
        &phProvider);
      *((_QWORD *)this + 1) = pbOutput;
      std::thread::~thread((std::thread *)v12);
      v4 = 0;
      goto LABEL_9;
    }
    v5 = 363;
  }
  else
  {
    v5 = 344;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl0\\lib\\vtl0tpmcommands.cpp",
    (const char *)(unsigned int)Property,
    dwFlags);
LABEL_9:
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
  return v4;
}

```

## disassembly

```asm
0x180076650  mov     [rsp-18h+pcbResult], rdx
0x180076655  push    rbp
0x180076656  push    rbx
0x180076657  push    rdi
0x180076658  mov     rbp, rsp
0x18007665b  sub     rsp, 60h
0x18007665f  mov     rdi, rcx
0x180076662  mov     [rbp+var_30], 0
0x18007666a  mov     [rbp+phProvider], 0
0x180076672  xor     edx, edx
0x180076674  lea     rcx, [rbp+phProvider]
0x180076678  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x18007667d  xor     r8d, r8d; dwFlags
0x180076680  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x180076687  lea     rcx, [rbp+phProvider]; phProvider
0x18007668b  call    cs:__imp_NCryptOpenStorageProvider
0x180076691  mov     ebx, eax
0x180076693  test    eax, eax
0x180076695  jns     short loc_1800766A1
0x180076697  mov     edx, 158h
0x18007669c  jmp     loc_180076729
0x1800766a1  mov     [rsp+60h+dwFlags], 0; int
0x1800766a9  mov     r9d, 10h; cbInput
0x1800766af  lea     r8, byte_18009ADA0; pbInput
0x1800766b6  lea     rdx, aPcpSessionid; "PCP_SESSIONID"
0x1800766bd  mov     rcx, [rbp+phProvider]; hObject
0x1800766c1  call    cs:__imp_NCryptSetProperty
0x1800766c7  mov     rcx, [rbp+18h]; this
0x1800766cb  test    eax, eax
0x1800766cd  jns     short loc_1800766E3
0x1800766cf  mov     r9d, eax; char *
0x1800766d2  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\trustlet\\utils"...
0x1800766d9  mov     edx, 15Fh; void *
0x1800766de  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800766e3  mov     [rbp+pbOutput], 0
0x1800766eb  mov     dword ptr [rbp+pcbResult], 0
0x1800766f2  mov     [rsp+60h+var_38], 0; dwFlags
0x1800766fa  lea     rax, [rbp+pcbResult]
0x1800766fe  mov     qword ptr [rsp+60h+dwFlags], rax; int
0x180076703  mov     r9d, 8; cbOutput
0x180076709  lea     r8, [rbp+pbOutput]; pbOutput
0x18007670d  lea     rdx, aPcpPlatformhan; "PCP_PLATFORMHANDLE"
0x180076714  mov     rcx, [rbp+phProvider]; hObject
0x180076718  call    cs:__imp_NCryptGetProperty
0x18007671e  mov     ebx, eax
0x180076720  test    eax, eax
0x180076722  jns     short loc_18007673E
0x180076724  mov     edx, 16Bh; void *
0x180076729  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\trustlet\\utils"...
0x180076730  mov     r9d, eax; char *
0x180076733  mov     rcx, [rbp+18h]; this
0x180076737  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007673c  jmp     short loc_180076787
0x18007673e  lea     r9, [rbp+pbOutput]
0x180076742  lea     r8, [rbp+var_30]
0x180076746  mov     rdx, rdi
0x180076749  lea     rcx, [rbp+var_18]
0x18007674d  call    _lambda_574365f21261df146e143cea233d4554____lambda_574365f21261df146e143cea233d4554_
0x180076752  mov     rdx, rax
0x180076755  lea     rcx, [rbp+var_28]
0x180076759  call    std__thread__thread__lambda_574365f21261df146e143cea233d4554__0_
0x18007675e  nop
0x18007675f  lea     rcx, [rbp+var_28]; this
0x180076763  call    ?detach@thread@std@@QEAAXXZ; std::thread::detach(void)
0x180076768  lea     rdx, [rbp+phProvider]
0x18007676c  mov     rcx, rdi
0x18007676f  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>> &&)
0x180076774  mov     rax, [rbp+pbOutput]
0x180076778  mov     [rdi+8], rax
0x18007677c  lea     rcx, [rbp+var_28]; this
0x180076780  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x180076785  xor     ebx, ebx
0x180076787  lea     rcx, [rbp+phProvider]
0x18007678b  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180076790  mov     eax, ebx
0x180076792  add     rsp, 60h
0x180076796  pop     rdi
0x180076797  pop     rbx
0x180076798  pop     rbp
0x180076799  retn
```
