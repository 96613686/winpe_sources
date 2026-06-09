# Windows::Compat::Ids::IdsRbdModel::ParseRbdRuleStatus(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,std::map<_GUID,Windows::Compat::Ids::IdsRbdRuleStatus,Windows::Compat::Ids::GUIDCompare,std::allocator<std::pair<_GUID const,Windows::Compat::Ids::IdsRbdRuleStatus>>> *)

- ea: `0x1800d3d08`
- end: `0x1800d416d`
- name: `?ParseRbdRuleStatus@IdsRbdModel@Ids@Compat@Windows@@AEAAKV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEAV?$map@U_GUID@@VIdsRbdRuleStatus@Ids@Compat@Windows@@UGUIDCompare@345@V?$allocator@U?$pair@$$CBU_GUID@@VIdsRbdRuleStatus@Ids@Compat@Windows@@@std@@@std@@@std@@@Z`
- size: `1125`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d2d4c`

## callees

- `0x180012920`
- `0x180018768`
- `0x18007a6e8`
- `0x180080a20`
- `0x18008cd3c`
- `0x180096f34`
- `0x1800bb46c`
- `0x1800ceda0`
- `0x1800cf434`
- `0x1800cf7a0`
- `0x1800cf934`
- `0x1800d0f04`
- `0x1800d3d08`
- `0x1800d50b8`
- `0x1800f1f10`
- `0x1800f7010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800d3ff5`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800d3ff5`
- `ntdll!RtlNtStatusToDosError` at `0x1800d3eeb`
- `ntdll!RtlNtStatusToDosError` at `0x1800d3eeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d3e2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d3e5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d3f2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d4007`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d403c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d4059`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d409f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d3e2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d3e5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d3f2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d4007`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d403c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d4059`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d409f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d3d9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d3e89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d3f62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4111`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4121`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4131`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d3d9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d3e89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d3f62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4111`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4121`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4131`

## string_xrefs

- `0x1800d3dfc`: `Windows::Compat::Ids::IdsRbdModel::ParseRbdRuleStatus`
- `0x1800d3e44`: `Windows::Compat::Ids::IdsRbdModel::ParseRbdRuleStatus`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Windows::Compat::Ids::IdsRbdModel::ParseRbdRuleStatus(__int64 a1, HSTRING a2, __int64 *a3)
{
  HSTRING v5; // rax
  void **v6; // r14
  ULONG v7; // esi
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64, HSTRING *); // rbx
  int v10; // eax
  PCWSTR StringRawBuffer; // rax
  NTSTATUS v12; // eax
  NTSTATUS v13; // ebx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64, HSTRING *); // rbx
  int v16; // ebx
  const char *v17; // r9
  int v18; // r8d
  PCWSTR v19; // rax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, __int64, HSTRING *); // rbx
  PCWSTR v22; // rax
  PCWSTR v23; // rax
  __int64 v24; // rbx
  PCWSTR v25; // rax
  __int64 v26; // rax
  PCWSTR v27; // rax
  __int64 v28; // rax
  __int64 v29; // r8
  __int64 v31; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING v33; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING v34[3]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v35[32]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v36[32]; // [rsp+78h] [rbp-88h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp-68h] BYREF
  __int64 v38; // [rsp+B0h] [rbp-50h]
  GUID Guid; // [rsp+B8h] [rbp-48h] BYREF
  GUID v40; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v41[56]; // [rsp+E0h] [rbp-20h] BYREF
  void *v42; // [rsp+118h] [rbp+18h] BYREF

  v34[2] = a2;
  string = 0;
  Guid = 0;
  v34[0] = 0;
  v33 = 0;
  v5 = (HSTRING)operator new(0x48u, (const struct std::nothrow_t *)std::nothrow);
  v6 = (void **)v5;
  v34[1] = v5;
  if ( v5 )
    std::_Tree_comp<0,std::_Tmap_traits<_GUID,bool,Windows::Compat::Ids::GUIDCompare,std::allocator<std::pair<_GUID const,bool>>,0>>::_Tree_comp<0,std::_Tmap_traits<_GUID,bool,Windows::Compat::Ids::GUIDCompare,std::allocator<std::pair<_GUID const,bool>>,0>>((_QWORD *)v5 + 7);
  else
    v6 = 0;
  if ( !v6 )
  {
    v7 = 8;
    goto LABEL_26;
  }
  v8 = *(_QWORD *)a2;
  v9 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(**(_QWORD **)a2 + 80LL);
  WindowsDeleteString(string);
  string = 0;
  v38 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"RuleId", 7u, 6u);
  v10 = v9(v8, v38, &string);
  v7 = v10;
  if ( v10 < 0 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"Windows::Compat::Ids::IdsRbdModel::ParseRbdRuleStatus",
      810,
      (unsigned int)"Failed to get the rule id data [%x]",
      v10);
    if ( (v7 & 0x1FFF0000) == 0x70000 )
      v7 = (unsigned __int16)v7;
    goto LABEL_21;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  AslLogCallPrintf(
    3,
    (unsigned int)"Windows::Compat::Ids::IdsRbdModel::ParseRbdRuleStatus",
    815,
    (unsigned int)"IdsRbdModel: Got rule id [%ws]",
    StringRawBuffer);
  WindowsGetStringRawBuffer(string, 0);
  v12 = AslGuidFromString(&Guid);
  v13 = v12;
  if ( v12 < 0 )
  {
    v7 = RtlNtStatusToDosError(v12);
    if ( v7 == 317 )
      v7 = v13;
    if ( v7 )
    {
      LODWORD(v31) = v7;
      AslLogCallPrintf(
        1,
        (unsigned int)"Windows::Compat::Ids::IdsRbdModel::ParseRbdRuleStatus",
        820,
        (unsigned int)"Failed to convert rule id to GUID [%d]",
        v31);
      goto LABEL_22;
    }
  }
  else
  {
    v7 = 0;
  }
  v14 = *(_QWORD *)a2;
  v15 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(**(_QWORD **)a2 + 80LL);
  WindowsDeleteString(v34[0]);
  v34[0] = 0;
  v38 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"WaitTime_ExpEvalToTrueInMS",
    0x1Bu,
    0x1Au);
  v16 = v15(v14, v38, v34);
  if ( v16 < 0 )
  {
    v17 = "Failed to get the waitTimeInMs_ExpEvalToTrue data [%x]";
    v18 = 829;
    goto LABEL_19;
  }
  v19 = WindowsGetStringRawBuffer(v34[0], 0);
  AslLogCallPrintf(
    3,
    (unsigned int)"Windows::Compat::Ids::IdsRbdModel::ParseRbdRuleStatus",
    834,
    (unsigned int)"IdsRbdModel: Got WaitTimeInMs_ExpEvalToTrue [%ws]",
    v19);
  v20 = *(_QWORD *)a2;
  v21 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(**(_QWORD **)a2 + 80LL);
  WindowsDeleteString(v33);
  v33 = 0;
  v38 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"WaitTime_ExpEvalToFalseInMS",
    0x1Cu,
    0x1Bu);
  v16 = v21(v20, v38, &v33);
  if ( v16 < 0 )
  {
    v17 = "Failed to get the WaitTimeInMs_ExpEvalToFalse data [%x]";
    v18 = 841;
LABEL_19:
    LODWORD(v31) = v16;
    AslLogCallPrintf(1, (unsigned int)"Windows::Compat::Ids::IdsRbdModel::ParseRbdRuleStatus", v18, (_DWORD)v17, v31);
    v7 = (unsigned __int16)v16;
    if ( (v16 & 0x1FFF0000) != 0x70000 )
      v7 = v16;
LABEL_21:
    if ( !v7 )
      goto LABEL_26;
LABEL_22:
    std::_Tree<std::_Tmap_traits<_GUID,bool,Windows::Compat::Ids::GUIDCompare,std::allocator<std::pair<_GUID const,bool>>,0>>::~_Tree<std::_Tmap_traits<_GUID,bool,Windows::Compat::Ids::GUIDCompare,std::allocator<std::pair<_GUID const,bool>>,0>>(v6 + 7);
    operator delete(v6);
    goto LABEL_26;
  }
  v22 = WindowsGetStringRawBuffer(v33, 0);
  AslLogCallPrintf(
    3,
    (unsigned int)"Windows::Compat::Ids::IdsRbdModel::ParseRbdRuleStatus",
    846,
    (unsigned int)"IdsRbdModel: Got WaitTimeInMs_ExpEvalToFalse [%ws]",
    v22);
  hstringHeader.Reserved.Reserved1 = v35;
  v23 = WindowsGetStringRawBuffer(v33, 0);
  v24 = std::wstring::wstring((__int64)v35, (__int64)v23);
  v25 = WindowsGetStringRawBuffer(v34[0], 0);
  v26 = std::wstring::wstring((__int64)v36, (__int64)v25);
  Windows::Compat::Ids::IdsRbdRuleStatus::Initialize(v6, &Guid, v26, v24);
  if ( *(_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,Windows::Compat::Ids::IdsRbdRule *,Windows::Compat::Ids::GUIDCompare,std::allocator<std::pair<_GUID const,Windows::Compat::Ids::IdsRbdRule *>>,0>>::find(
                    a3,
                    &hstringHeader,
                    &Guid) == *a3 )
  {
    v40 = Guid;
    Windows::Compat::Ids::IdsRbdRuleStatus::IdsRbdRuleStatus(
      (Windows::Compat::Ids::IdsRbdRuleStatus *)v41,
      (const struct Windows::Compat::Ids::IdsRbdRuleStatus *)v6);
    v28 = std::_Tree_buy<std::pair<_GUID const,Windows::Compat::Ids::IdsRbdRuleStatus>>::_Buynode<std::pair<_GUID,Windows::Compat::Ids::IdsRbdRuleStatus>>(
            (__int64)a3,
            &v40);
    std::_Tree<std::_Tmap_traits<_GUID,Windows::Compat::Ids::IdsRbdRuleStatus,Windows::Compat::Ids::GUIDCompare,std::allocator<std::pair<_GUID const,Windows::Compat::Ids::IdsRbdRuleStatus>>,0>>::_Insert_nohint<std::pair<_GUID const,Windows::Compat::Ids::IdsRbdRuleStatus> &,std::_Tree_node<std::pair<_GUID const,Windows::Compat::Ids::IdsRbdRuleStatus>,void *> *>(
      a3,
      (__int64)&hstringHeader,
      v29,
      (const void *)(v28 + 32),
      v28);
    std::_Tree<std::_Tmap_traits<_GUID,bool,Windows::Compat::Ids::GUIDCompare,std::allocator<std::pair<_GUID const,bool>>,0>>::~_Tree<std::_Tmap_traits<_GUID,bool,Windows::Compat::Ids::GUIDCompare,std::allocator<std::pair<_GUID const,bool>>,0>>(&v42);
  }
  else
  {
    v27 = WindowsGetStringRawBuffer(string, 0);
    AslLogCallPrintf(
      1,
      (unsigned int)"Windows::Compat::Ids::IdsRbdModel::ParseRbdRuleStatus",
      852,
      (unsigned int)"duplicate ruleIds are mapped to an Event in EventMap. ruleId:%ws %d",
      v27,
      v7);
  }
LABEL_26:
  WindowsDeleteString(v33);
  v33 = 0;
  WindowsDeleteString(v34[0]);
  v34[0] = 0;
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(a2);
  return v7;
}

```

## disassembly

```asm
0x1800d3d08  mov     [rsp-8+arg_0], rbx
0x1800d3d0d  push    rbp
0x1800d3d0e  push    rsi
0x1800d3d0f  push    rdi
0x1800d3d10  push    r12
0x1800d3d12  push    r13
0x1800d3d14  push    r14
0x1800d3d16  push    r15
0x1800d3d18  lea     rbp, [rsp-40h]
0x1800d3d1d  sub     rsp, 140h
0x1800d3d24  mov     rax, cs:__security_cookie
0x1800d3d2b  xor     rax, rsp
0x1800d3d2e  mov     [rbp+70h+var_40], rax
0x1800d3d32  mov     r13, r8
0x1800d3d35  mov     r12, rdx
0x1800d3d38  mov     [rsp+170h+var_120], rdx
0x1800d3d3d  xor     edi, edi
0x1800d3d3f  mov     [rsp+170h+string], rdi
0x1800d3d44  xorps   xmm0, xmm0
0x1800d3d47  movups  xmmword ptr [rbp+70h+Guid.Data1], xmm0
0x1800d3d4b  mov     [rsp+170h+var_130], rdi
0x1800d3d50  mov     [rsp+170h+var_138], rdi
0x1800d3d55  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800d3d5c  lea     ecx, [rdi+48h]; unsigned __int64
0x1800d3d5f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800d3d64  mov     r14, rax
0x1800d3d67  mov     [rsp+170h+var_128], rax
0x1800d3d6c  test    rax, rax
0x1800d3d6f  jz      short loc_1800D3D7C
0x1800d3d71  lea     rcx, [rax+38h]
0x1800d3d75  call    ??0?$_Tree_comp@$0A@V?$_Tmap_traits@U_GUID@@_NUGUIDCompare@Ids@Compat@Windows@@V?$allocator@U?$pair@$$CBU_GUID@@_N@std@@@std@@$0A@@std@@@std@@QEAA@AEBUGUIDCompare@Ids@Compat@Windows@@AEBV?$allocator@U?$pair@$$CBU_GUID@@_N@std@@@1@@Z; std::_Tree_comp<0,std::_Tmap_traits<_GUID,bool,Windows::Compat::Ids::GUIDCompare,std::allocator<std::pair<_GUID const,bool>>,0>>::_Tree_comp<0,std::_Tmap_traits<_GUID,bool,Windows::Compat::Ids::GUIDCompare,std::allocator<std::pair<_GUID const,bool>>,0>>(Windows::Compat::Ids::GUIDCompare const &,std::allocator<std::pair<_GUID const,bool>> const &)
0x1800d3d7a  jmp     short loc_1800D3D7F
0x1800d3d7c  mov     r14, rdi
0x1800d3d7f  test    r14, r14
0x1800d3d82  jnz     short loc_1800D3D8D
0x1800d3d84  lea     esi, [r14+8]
0x1800d3d88  jmp     loc_1800D410C
0x1800d3d8d  mov     rdi, [r12]
0x1800d3d91  mov     rax, [rdi]
0x1800d3d94  mov     rbx, [rax+50h]
0x1800d3d98  mov     rcx, [rsp+170h+string]; string
0x1800d3d9d  call    cs:__imp_WindowsDeleteString
0x1800d3da3  mov     [rsp+170h+string], 0
0x1800d3dac  mov     [rbp+70h+var_C0], 0
0x1800d3db4  mov     r9d, 6; unsigned int
0x1800d3dba  lea     r8d, [r9+1]; unsigned int
0x1800d3dbe  lea     rdx, aRuleid; "RuleId"
0x1800d3dc5  lea     rcx, [rbp+70h+hstringHeader]; hstringHeader
0x1800d3dc9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800d3dce  nop
0x1800d3dcf  lea     r8, [rsp+170h+string]
0x1800d3dd4  mov     rdx, [rbp+70h+var_C0]
0x1800d3dd8  mov     rcx, rdi
0x1800d3ddb  mov     rax, rbx
0x1800d3dde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3de3  mov     esi, eax
0x1800d3de5  xor     edi, edi
0x1800d3de7  test    eax, eax
0x1800d3de9  jns     short loc_1800D3E25
0x1800d3deb  mov     dword ptr [rsp+170h+var_150], eax
0x1800d3def  lea     r9, aFailedToGetThe_8; "Failed to get the rule id data [%x]"
0x1800d3df6  mov     r8d, 32Ah
0x1800d3dfc  lea     rdx, aWindowsCompatI_29; "Windows::Compat::Ids::IdsRbdModel::Pars"...
0x1800d3e03  lea     ecx, [rdi+1]
0x1800d3e06  call    AslLogCallPrintf
0x1800d3e0b  mov     eax, esi
0x1800d3e0d  and     eax, 1FFF0000h
0x1800d3e12  cmp     eax, 70000h
0x1800d3e17  jnz     loc_1800D3FE1
0x1800d3e1d  movzx   esi, si
0x1800d3e20  jmp     loc_1800D3FE1
0x1800d3e25  xor     edx, edx; length
0x1800d3e27  mov     rcx, [rsp+170h+string]; string
0x1800d3e2c  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d3e32  mov     [rsp+170h+var_150], rax
0x1800d3e37  lea     r9, aIdsrbdmodelGot; "IdsRbdModel: Got rule id [%ws]"
0x1800d3e3e  mov     r8d, 32Fh
0x1800d3e44  lea     r15, aWindowsCompatI_29; "Windows::Compat::Ids::IdsRbdModel::Pars"...
0x1800d3e4b  mov     rdx, r15
0x1800d3e4e  mov     ecx, 3
0x1800d3e53  call    AslLogCallPrintf
0x1800d3e58  xor     edx, edx; length
0x1800d3e5a  mov     rcx, [rsp+170h+string]; string
0x1800d3e5f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d3e65  mov     rdx, rax
0x1800d3e68  lea     rcx, [rbp+70h+Guid]; Guid
0x1800d3e6c  call    AslGuidFromString
0x1800d3e71  mov     ebx, eax
0x1800d3e73  test    eax, eax
0x1800d3e75  js      short loc_1800D3EE9
0x1800d3e77  mov     esi, edi
0x1800d3e79  mov     rdi, [r12]
0x1800d3e7d  mov     rax, [rdi]
0x1800d3e80  mov     rbx, [rax+50h]
0x1800d3e84  mov     rcx, [rsp+170h+var_130]; string
0x1800d3e89  call    cs:__imp_WindowsDeleteString
0x1800d3e8f  mov     [rsp+170h+var_130], 0
0x1800d3e98  mov     [rbp+70h+var_C0], 0
0x1800d3ea0  mov     r9d, 1Ah; unsigned int
0x1800d3ea6  lea     r8d, [r9+1]; unsigned int
0x1800d3eaa  lea     rdx, aWaittimeExpeva_0; "WaitTime_ExpEvalToTrueInMS"
0x1800d3eb1  lea     rcx, [rbp+70h+hstringHeader]; hstringHeader
0x1800d3eb5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800d3eba  nop
0x1800d3ebb  lea     r8, [rsp+170h+var_130]
0x1800d3ec0  mov     rdx, [rbp+70h+var_C0]
0x1800d3ec4  mov     rcx, rdi
0x1800d3ec7  mov     rax, rbx
0x1800d3eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3ecf  mov     ebx, eax
0x1800d3ed1  xor     edi, edi
0x1800d3ed3  test    eax, eax
0x1800d3ed5  jns     short loc_1800D3F26
0x1800d3ed7  lea     r9, aFailedToGetThe_23; "Failed to get the waitTimeInMs_ExpEvalT"...
0x1800d3ede  mov     r8d, 33Dh
0x1800d3ee4  jmp     loc_1800D3FBD
0x1800d3ee9  mov     ecx, ebx; Status
0x1800d3eeb  call    cs:__imp_RtlNtStatusToDosError
0x1800d3ef1  mov     esi, eax
0x1800d3ef3  cmp     eax, 13Dh
0x1800d3ef8  cmovz   esi, ebx
0x1800d3efb  test    esi, esi
0x1800d3efd  jz      loc_1800D3E79
0x1800d3f03  mov     dword ptr [rsp+170h+var_150], esi
0x1800d3f07  lea     r9, aFailedToConver_27; "Failed to convert rule id to GUID [%d]"
0x1800d3f0e  mov     r8d, 334h
0x1800d3f14  mov     rdx, r15
0x1800d3f17  mov     ecx, 1
0x1800d3f1c  call    AslLogCallPrintf
0x1800d3f21  jmp     loc_1800D3FE9
0x1800d3f26  xor     edx, edx; length
0x1800d3f28  mov     rcx, [rsp+170h+var_130]; string
0x1800d3f2d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d3f33  mov     [rsp+170h+var_150], rax
0x1800d3f38  lea     r9, aIdsrbdmodelGot_1; "IdsRbdModel: Got WaitTimeInMs_ExpEvalTo"...
0x1800d3f3f  mov     r8d, 342h
0x1800d3f45  mov     rdx, r15
0x1800d3f48  mov     ecx, 3
0x1800d3f4d  call    AslLogCallPrintf
0x1800d3f52  mov     rdi, [r12]
0x1800d3f56  mov     rax, [rdi]
0x1800d3f59  mov     rbx, [rax+50h]
0x1800d3f5d  mov     rcx, [rsp+170h+var_138]; string
0x1800d3f62  call    cs:__imp_WindowsDeleteString
0x1800d3f68  mov     [rsp+170h+var_138], 0
0x1800d3f71  mov     [rbp+70h+var_C0], 0
0x1800d3f79  mov     r9d, 1Bh; unsigned int
0x1800d3f7f  lea     r8d, [r9+1]; unsigned int
0x1800d3f83  lea     rdx, aWaittimeExpeva; "WaitTime_ExpEvalToFalseInMS"
0x1800d3f8a  lea     rcx, [rbp+70h+hstringHeader]; hstringHeader
0x1800d3f8e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800d3f93  nop
0x1800d3f94  lea     r8, [rsp+170h+var_138]
0x1800d3f99  mov     rdx, [rbp+70h+var_C0]
0x1800d3f9d  mov     rcx, rdi
0x1800d3fa0  mov     rax, rbx
0x1800d3fa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3fa8  mov     ebx, eax
0x1800d3faa  xor     edi, edi
0x1800d3fac  test    eax, eax
0x1800d3fae  jns     short loc_1800D4000
0x1800d3fb0  lea     r9, aFailedToGetThe_36; "Failed to get the WaitTimeInMs_ExpEvalT"...
0x1800d3fb7  mov     r8d, 349h
0x1800d3fbd  mov     dword ptr [rsp+170h+var_150], ebx
0x1800d3fc1  mov     rdx, r15
0x1800d3fc4  mov     ecx, 1
0x1800d3fc9  call    AslLogCallPrintf
0x1800d3fce  mov     eax, ebx
0x1800d3fd0  and     eax, 1FFF0000h
0x1800d3fd5  cmp     eax, 70000h
0x1800d3fda  movzx   esi, bx
0x1800d3fdd  jz      short loc_1800D3FE1
0x1800d3fdf  mov     esi, ebx
0x1800d3fe1  test    esi, esi
0x1800d3fe3  jz      loc_1800D410C
0x1800d3fe9  lea     rcx, [r14+38h]
0x1800d3fed  call    ??1?$_Tree@V?$_Tmap_traits@U_GUID@@_NUGUIDCompare@Ids@Compat@Windows@@V?$allocator@U?$pair@$$CBU_GUID@@_N@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_GUID,bool,Windows::Compat::Ids::GUIDCompare,std::allocator<std::pair<_GUID const,bool>>,0>>::~_Tree<std::_Tmap_traits<_GUID,bool,Windows::Compat::Ids::GUIDCompare,std::allocator<std::pair<_GUID const,bool>>,0>>(void)
0x1800d3ff2  mov     rcx, r14
0x1800d3ff5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800d3ffb  jmp     loc_1800D410C
0x1800d4000  xor     edx, edx; length
0x1800d4002  mov     rcx, [rsp+170h+var_138]; string
0x1800d4007  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d400d  mov     [rsp+170h+var_150], rax
0x1800d4012  lea     r9, aIdsrbdmodelGot_2; "IdsRbdModel: Got WaitTimeInMs_ExpEvalTo"...
0x1800d4019  mov     r8d, 34Eh
0x1800d401f  mov     rdx, r15
0x1800d4022  mov     ecx, 3
0x1800d4027  call    AslLogCallPrintf
0x1800d402c  lea     rax, [rsp+170h+var_118]
0x1800d4031  mov     qword ptr [rbp+70h+hstringHeader.Reserved], rax
0x1800d4035  xor     edx, edx; length
0x1800d4037  mov     rcx, [rsp+170h+var_138]; string
0x1800d403c  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d4042  mov     rdx, rax
0x1800d4045  lea     rcx, [rsp+170h+var_118]
0x1800d404a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800d404f  mov     rbx, rax
0x1800d4052  xor     edx, edx; length
0x1800d4054  mov     rcx, [rsp+170h+var_130]; string
0x1800d4059  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d405f  mov     rdx, rax
0x1800d4062  lea     rcx, [rsp+170h+var_F8]
0x1800d4067  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800d406c  nop
0x1800d406d  mov     r9, rbx
0x1800d4070  mov     r8, rax
0x1800d4073  lea     rdx, [rbp+70h+Guid]
0x1800d4077  mov     rcx, r14
0x1800d407a  call    ?Initialize@IdsRbdRuleStatus@Ids@Compat@Windows@@QEAAXAEBU_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; Windows::Compat::Ids::IdsRbdRuleStatus::Initialize(_GUID const &,std::wstring,std::wstring)
0x1800d407f  lea     r8, [rbp+70h+Guid]
0x1800d4083  lea     rdx, [rbp+70h+hstringHeader]
0x1800d4087  mov     rcx, r13
0x1800d408a  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAVIdsRbdRule@Ids@Compat@Windows@@UGUIDCompare@345@V?$allocator@U?$pair@$$CBU_GUID@@PEAVIdsRbdRule@Ids@Compat@Windows@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAVIdsRbdRule@Ids@Compat@Windows@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,Windows::Compat::Ids::IdsRbdRule *,Windows::Compat::Ids::GUIDCompare,std::allocator<std::pair<_GUID const,Windows::Compat::Ids::IdsRbdRule *>>,0>>::find(_GUID const &)
0x1800d408f  mov     rcx, [r13+0]
0x1800d4093  cmp     [rax], rcx
0x1800d4096  jz      short loc_1800D40CA
0x1800d4098  xor     edx, edx; length
0x1800d409a  mov     rcx, [rsp+170h+string]; string
0x1800d409f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d40a5  mov     [rsp+170h+var_148], esi
0x1800d40a9  mov     [rsp+170h+var_150], rax
0x1800d40ae  lea     r9, aDuplicateRulei; "duplicate ruleIds are mapped to an Even"...
0x1800d40b5  mov     r8d, 354h
0x1800d40bb  mov     rdx, r15
0x1800d40be  mov     ecx, 1
0x1800d40c3  call    AslLogCallPrintf
0x1800d40c8  jmp     short loc_1800D410C
0x1800d40ca  movups  xmm0, xmmword ptr [rbp+70h+Guid.Data1]
0x1800d40ce  movdqu  [rbp+70h+var_A0], xmm0
0x1800d40d3  mov     rdx, r14; struct Windows::Compat::Ids::IdsRbdRuleStatus *
0x1800d40d6  lea     rcx, [rbp+70h+var_90]; this
0x1800d40da  call    ??0IdsRbdRuleStatus@Ids@Compat@Windows@@QEAA@AEBV0123@@Z; Windows::Compat::Ids::IdsRbdRuleStatus::IdsRbdRuleStatus(Windows::Compat::Ids::IdsRbdRuleStatus const &)
0x1800d40df  nop
0x1800d40e0  lea     rdx, [rbp+70h+var_A0]
0x1800d40e4  mov     rcx, r13
0x1800d40e7  call    ??$_Buynode@U?$pair@U_GUID@@VIdsRbdRuleStatus@Ids@Compat@Windows@@@std@@@?$_Tree_buy@U?$pair@$$CBU_GUID@@VIdsRbdRuleStatus@Ids@Compat@Windows@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@VIdsRbdRuleStatus@Ids@Compat@Windows@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@VIdsRbdRuleStatus@Ids@Compat@Windows@@@std@@PEAX@1@$$QEAU?$pair@U_GUID@@VIdsRbdRuleStatus@Ids@Compat@Windows@@@1@@Z; std::_Tree_buy<std::pair<_GUID const,Windows::Compat::Ids::IdsRbdRuleStatus>>::_Buynode<std::pair<_GUID,Windows::Compat::Ids::IdsRbdRuleStatus>>(std::pair<_GUID,Windows::Compat::Ids::IdsRbdRuleStatus> &&)
0x1800d40ec  lea     r9, [rax+20h]
0x1800d40f0  mov     [rsp+170h+var_150], rax
0x1800d40f5  lea     rdx, [rbp+70h+hstringHeader]
0x1800d40f9  mov     rcx, r13
0x1800d40fc  call    ??$_Insert_nohint@AEAU?$pair@$$CBU_GUID@@VIdsRbdRuleStatus@Ids@Compat@Windows@@@std@@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@VIdsRbdRuleStatus@Ids@Compat@Windows@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@U_GUID@@VIdsRbdRuleStatus@Ids@Compat@Windows@@UGUIDCompare@345@V?$allocator@U?$pair@$$CBU_GUID@@VIdsRbdRuleStatus@Ids@Compat@Windows@@@std@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@VIdsRbdRuleStatus@Ids@Compat@Windows@@@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@$$CBU_GUID@@VIdsRbdRuleStatus@Ids@Compat@Windows@@@1@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@VIdsRbdRuleStatus@Ids@Compat@Windows@@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<_GUID,Windows::Compat::Ids::IdsRbdRuleStatus,Windows::Compat::Ids::GUIDCompare,std::allocator<std::pair<_GUID const,Windows::Compat::Ids::IdsRbdRuleStatus>>,0>>::_Insert_nohint<std::pair<_GUID const,Windows::Compat::Ids::IdsRbdRuleStatus> &,std::_Tree_node<std::pair<_GUID const,Windows::Compat::Ids::IdsRbdRuleStatus>,void *> *>(bool,std::pair<_GUID const,Windows::Compat::Ids::IdsRbdRuleStatus> &,std::_Tree_node<std::pair<_GUID const,Windows::Compat::Ids::IdsRbdRuleStatus>,void *> *)
0x1800d4101  nop
0x1800d4102  lea     rcx, [rbp+70h+var_58]
0x1800d4106  call    ??1?$_Tree@V?$_Tmap_traits@U_GUID@@_NUGUIDCompare@Ids@Compat@Windows@@V?$allocator@U?$pair@$$CBU_GUID@@_N@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_GUID,bool,Windows::Compat::Ids::GUIDCompare,std::allocator<std::pair<_GUID const,bool>>,0>>::~_Tree<std::_Tmap_traits<_GUID,bool,Windows::Compat::Ids::GUIDCompare,std::allocator<std::pair<_GUID const,bool>>,0>>(void)
0x1800d410b  nop
0x1800d410c  mov     rcx, [rsp+170h+var_138]; string
0x1800d4111  call    cs:__imp_WindowsDeleteString
0x1800d4117  mov     [rsp+170h+var_138], rdi
0x1800d411c  mov     rcx, [rsp+170h+var_130]; string
0x1800d4121  call    cs:__imp_WindowsDeleteString
0x1800d4127  mov     [rsp+170h+var_130], rdi
0x1800d412c  mov     rcx, [rsp+170h+string]; string
0x1800d4131  call    cs:__imp_WindowsDeleteString
0x1800d4137  mov     [rsp+170h+string], rdi
0x1800d413c  mov     rcx, r12
0x1800d413f  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVPackageUserInformation@Deployment@Management@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(void)
0x1800d4144  mov     eax, esi
0x1800d4146  mov     rcx, [rbp+70h+var_40]
0x1800d414a  xor     rcx, rsp; StackCookie
0x1800d414d  call    __security_check_cookie
0x1800d4152  mov     rbx, [rsp+170h+arg_0]
0x1800d415a  add     rsp, 140h
0x1800d4161  pop     r15
0x1800d4163  pop     r14
0x1800d4165  pop     r13
0x1800d4167  pop     r12
0x1800d4169  pop     rdi
0x1800d416a  pop     rsi
0x1800d416b  pop     rbp
0x1800d416c  retn
```
