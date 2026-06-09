# DiscoveryResponseParser::ParseResponseBody(ushort const *,ulong,struct_dsreg_server_response *)

- ea: `0x18009b430`
- end: `0x18009b773`
- name: `?ParseResponseBody@DiscoveryResponseParser@@MEAAJPEBGKPEAUstruct_dsreg_server_response@@@Z`
- size: `835`
- prototype: `int(DiscoveryResponseParser *__hidden this, const unsigned __int16 *, unsigned int, struct struct_dsreg_server_response *)`
- caller_count: `0`
- callee_count: `25`
- tags: `registry_config, service_task`

## callees

- `0x180003c20`
- `0x180004a24`
- `0x180005f24`
- `0x180085c44`
- `0x18008a9ec`
- `0x18008aa28`
- `0x18008aa9c`
- `0x18008aecc`
- `0x180094390`
- `0x180099678`
- `0x18009979c`
- `0x18009988c`
- `0x180099a28`
- `0x180099bb4`
- `0x180099d4c`
- `0x18009aa44`
- `0x18009adac`
- `0x18009b138`
- `0x18009b430`
- `0x18009b77c`
- `0x18009bab4`
- `0x18009f7b0`
- `0x18009f7ec`
- `0x1800a0508`
- `0x1800a06c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009b744`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009b744`

## string_xrefs

- `0x18009b6f5`: `CopyStringNullSafeW`
- `0x18009b571`: `CJsonParser::Parse`
- `0x18009b53f`: `CJsonParser::Initialize`
- `0x18009b5c6`: `ParseDeviceJoinServiceNode`
- `0x18009b5e3`: `ParseKeyProvisioningServiceNode`
- `0x18009b58f`: `ParseDeviceRegistrationServiceNode`
- `0x18009b5a9`: `ParseAuthenticationServiceNode`
- `0x18009b668`: `ParsePrecreateServiceNode`
- `0x18009b607`: `ParseWebAuthNServiceNode`
- `0x18009b627`: `ParseDeviceManagementServiceNode`
- `0x18009b6d0`: `ParseDeviceJoinResourceServiceNode`
- `0x18009b6a9`: `ParseAzureRbacServiceNode`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DiscoveryResponseParser::ParseResponseBody(
        const unsigned __int16 **this,
        const unsigned __int16 *a2,
        unsigned int a3,
        struct struct_dsreg_server_response *a4)
{
  unsigned __int64 v4; // r15
  void **v7; // rbx
  unsigned int v8; // edi
  void *v9; // rax
  void *v10; // rdi
  int v11; // eax
  const wchar_t *v12; // r8
  __int64 v13; // rcx
  __int64 v14; // rsi
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  unsigned int v19; // edx
  __int64 v21; // [rsp+20h] [rbp-89h] BYREF
  __int64 v22; // [rsp+28h] [rbp-81h]
  void *Block; // [rsp+30h] [rbp-79h]
  __int64 v24; // [rsp+38h] [rbp-71h]
  __int64 v25; // [rsp+40h] [rbp-69h]
  __int64 v26; // [rsp+48h] [rbp-61h]
  __int64 v27; // [rsp+50h] [rbp-59h]
  __int64 v28; // [rsp+60h] [rbp-49h]
  __int64 v29; // [rsp+68h] [rbp-41h]
  _BYTE v30[64]; // [rsp+70h] [rbp-39h] BYREF
  __int64 v31; // [rsp+B0h] [rbp+7h]

  v4 = a3;
  Block = 0;
  v25 = 0;
  LODWORD(v24) = 0;
  v26 = 12;
  BYTE4(v27) = 0;
  v21 = 0;
  v22 = 1;
  LODWORD(v27) = 0;
  v29 = 0;
  v28 = 0;
  dsreg::CJsonValue::CJsonValue((dsreg::CJsonValue *)v30);
  v7 = (void **)(this + 1);
  if ( !a2 )
  {
    v8 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"DiscoveryResponseParser::ParseResponseBody",
      L"responseBody");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"DiscoveryResponseParser::ParseResponseBody", L"responseBody");
LABEL_38:
    DsrFreeDiscoveryMetadata(*v7);
    *v7 = 0;
    goto LABEL_39;
  }
  DsrFreeDiscoveryMetadata(*v7);
  v9 = operator new[](0x100u, (const struct std::nothrow_t *)std::nothrow);
  v10 = v9;
  if ( !v9 )
  {
    *v7 = 0;
    v8 = -2147024882;
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"DiscoveryResponseParser::ParseResponseBody");
    goto LABEL_38;
  }
  memset_0(v9, 0, 0x100u);
  *v7 = v10;
  memset_0(v10, 0, 0x100u);
  v11 = dsreg::CJsonParser::Initialize((dsreg::CJsonParser *)&v21, a2, v4);
  v8 = v11;
  if ( v11 < 0 )
  {
    v12 = L"CJsonParser::Initialize";
LABEL_6:
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"DiscoveryResponseParser::ParseResponseBody",
      v12,
      (unsigned int)v11,
      v21,
      v22,
      Block,
      v24,
      v25,
      v26,
      v27);
    goto LABEL_38;
  }
  v11 = dsreg::CJsonParser::Parse((dsreg::CJsonParser *)&v21, (struct CJsonValue *)v30);
  v8 = v11;
  if ( v11 < 0 )
  {
    v12 = L"CJsonParser::Parse";
    goto LABEL_6;
  }
  v14 = v31;
  v11 = DiscoveryResponseParser::ParseDeviceRegistrationServiceNode(v13, v31, *v7);
  v8 = v11;
  if ( v11 < 0 )
  {
    v12 = L"ParseDeviceRegistrationServiceNode";
    goto LABEL_6;
  }
  v11 = DiscoveryResponseParser::ParseAuthenticationServiceNode(this, v14);
  v8 = v11;
  if ( v11 < 0 )
  {
    v12 = L"ParseAuthenticationServiceNode";
    goto LABEL_6;
  }
  v11 = DiscoveryResponseParser::ParseDeviceJoinServiceNode(this, v14, *v7);
  v8 = v11;
  if ( v11 < 0 )
  {
    v12 = L"ParseDeviceJoinServiceNode";
    goto LABEL_6;
  }
  v11 = DiscoveryResponseParser::ParseKeyProvisioningServiceNode(v15, v14, *v7);
  v8 = v11;
  if ( v11 < 0 )
  {
    v12 = L"ParseKeyProvisioningServiceNode";
    goto LABEL_6;
  }
  if ( *((int *)this + 6) >= 3 )
  {
    v11 = DiscoveryResponseParser::ParseWebAuthNServiceNode(v16, v14, *v7);
    v8 = v11;
    if ( v11 < 0 )
    {
      v12 = L"ParseWebAuthNServiceNode";
      goto LABEL_6;
    }
    v11 = DiscoveryResponseParser::ParseDeviceManagementServiceNode(this, v14, *v7);
    v8 = v11;
    if ( v11 < 0 )
    {
      v12 = L"ParseDeviceManagementServiceNode";
      goto LABEL_6;
    }
    v11 = DiscoveryResponseParser::ParseMsaProviderDataNode(v17, v14, *v7);
    v8 = v11;
    if ( v11 < 0 )
    {
      v12 = L"ParseMsaProviderDataNode";
      goto LABEL_6;
    }
  }
  if ( *((int *)this + 6) >= 4 )
  {
    v11 = DiscoveryResponseParser::ParsePrecreateServiceNode(v16, v14, *v7);
    v8 = v11;
    if ( v11 < 0 )
    {
      v12 = L"ParsePrecreateServiceNode";
      goto LABEL_6;
    }
    v11 = DiscoveryResponseParser::ParseTenantInfoNode(v18, v14, *v7);
    v8 = v11;
    if ( v11 < 0 )
    {
      v12 = L"ParseTenantInfoNode";
      goto LABEL_6;
    }
  }
  if ( *((int *)this + 6) >= 5 )
  {
    v11 = DiscoveryResponseParser::ParseAzureRbacServiceNode(v16, v14, *v7);
    v8 = v11;
    if ( v11 < 0 )
    {
      v12 = L"ParseAzureRbacServiceNode";
      goto LABEL_6;
    }
  }
  if ( *((int *)this + 6) >= 6 )
  {
    v11 = DiscoveryResponseParser::ParseDeviceJoinResourceServiceNode(this, v14, *v7);
    v8 = v11;
    if ( v11 < 0 )
    {
      v12 = L"ParseDeviceJoinResourceServiceNode";
      goto LABEL_6;
    }
  }
  v11 = CopyStringNullSafeW(this[2], (unsigned __int16 **)*v7 + 21);
  v8 = v11;
  if ( v11 < 0 )
  {
    v12 = L"CopyStringNullSafeW";
    goto LABEL_6;
  }
LABEL_39:
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"DiscoveryResponseParser::ParseResponseBody", v8);
  dsreg::CJsonValue::~CJsonValue((dsreg::CJsonValue *)v30, v19);
  free(Block);
  return v8;
}

```

## disassembly

```asm
0x18009b430  mov     [rsp-8+arg_18], rbx
0x18009b435  push    rbp
0x18009b436  push    rsi
0x18009b437  push    rdi
0x18009b438  push    r12
0x18009b43a  push    r13
0x18009b43c  push    r14
0x18009b43e  push    r15
0x18009b440  lea     rbp, [rsp-27h]
0x18009b445  sub     rsp, 0D0h
0x18009b44c  mov     rax, cs:__security_cookie
0x18009b453  xor     rax, rsp
0x18009b456  mov     [rbp+57h+var_40], rax
0x18009b45a  mov     r15d, r8d
0x18009b45d  mov     rsi, rdx
0x18009b460  mov     r14, rcx
0x18009b463  xor     r12d, r12d
0x18009b466  mov     [rbp+57h+Block], r12
0x18009b46a  mov     [rbp+57h+var_C0], r12
0x18009b46e  mov     dword ptr [rbp+57h+var_C8], r12d
0x18009b472  mov     [rbp+57h+var_B8], 0Ch
0x18009b47a  mov     [rbp+57h+var_AC], r12b
0x18009b47e  mov     [rsp+100h+var_E0], r12
0x18009b483  mov     [rsp+100h+var_D8], 1
0x18009b48c  mov     [rbp+57h+var_B0], r12d
0x18009b490  mov     [rbp+57h+var_98], r12
0x18009b494  mov     [rbp+57h+var_A0], r12
0x18009b498  lea     rcx, [rbp+57h+var_90]; this
0x18009b49c  call    ??0CJsonValue@dsreg@@QEAA@XZ; dsreg::CJsonValue::CJsonValue(void)
0x18009b4a1  nop
0x18009b4a2  lea     rbx, [r14+8]
0x18009b4a6  lea     r13, aDiscoveryrespo_10; "DiscoveryResponseParser::ParseResponseB"...
0x18009b4ad  test    rsi, rsi
0x18009b4b0  jnz     short loc_18009B4E1
0x18009b4b2  mov     edi, 80070057h
0x18009b4b7  lea     r8, aResponsebody; "responseBody"
0x18009b4be  mov     rdx, r13
0x18009b4c1  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18009b4c8  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009b4cd  lea     rdx, aResponsebody; "responseBody"
0x18009b4d4  mov     rcx, r13; unsigned __int16 *
0x18009b4d7  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18009b4dc  jmp     loc_18009B718
0x18009b4e1  mov     rcx, [rbx]; void *
0x18009b4e4  call    DsrFreeDiscoveryMetadata
0x18009b4e9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009b4f0  mov     ecx, 100h; unsigned __int64
0x18009b4f5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18009b4fa  mov     rdi, rax
0x18009b4fd  test    rax, rax
0x18009b500  jz      loc_18009B701
0x18009b506  xor     edx, edx; Val
0x18009b508  mov     r8d, 100h; Size
0x18009b50e  mov     rcx, rax; void *
0x18009b511  call    memset_0
0x18009b516  mov     [rbx], rdi
0x18009b519  xor     edx, edx; Val
0x18009b51b  mov     r8d, 100h; Size
0x18009b521  mov     rcx, rdi; void *
0x18009b524  call    memset_0
0x18009b529  mov     r8, r15; unsigned __int64
0x18009b52c  mov     rdx, rsi; unsigned __int16 *
0x18009b52f  lea     rcx, [rsp+100h+var_E0]; this
0x18009b534  call    ?Initialize@CJsonParser@dsreg@@QEAAJPEBG_K@Z; dsreg::CJsonParser::Initialize(ushort const *,unsigned __int64)
0x18009b539  mov     edi, eax
0x18009b53b  test    eax, eax
0x18009b53d  jns     short loc_18009B55D
0x18009b53f  lea     r8, aCjsonparserIni; "CJsonParser::Initialize"
0x18009b546  mov     r9d, eax
0x18009b549  mov     rdx, r13
0x18009b54c  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18009b553  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009b558  jmp     loc_18009B718
0x18009b55d  lea     rdx, [rbp+57h+var_90]; struct CJsonValue *
0x18009b561  lea     rcx, [rsp+100h+var_E0]; this
0x18009b566  call    ?Parse@CJsonParser@dsreg@@QEAAJPEAVCJsonValue@2@@Z; dsreg::CJsonParser::Parse(dsreg::CJsonValue *)
0x18009b56b  mov     edi, eax
0x18009b56d  test    eax, eax
0x18009b56f  jns     short loc_18009B57A
0x18009b571  lea     r8, aCjsonparserPar; "CJsonParser::Parse"
0x18009b578  jmp     short loc_18009B546
0x18009b57a  mov     rsi, [rbp+57h+var_50]
0x18009b57e  mov     r8, [rbx]
0x18009b581  mov     rdx, rsi
0x18009b584  call    ?ParseDeviceRegistrationServiceNode@DiscoveryResponseParser@@AEAAJAEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCJsonValue@dsreg@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCJsonValue@dsreg@@@std@@@2@@std@@PEAU_DISCOVERY_METADATA@@@Z; DiscoveryResponseParser::ParseDeviceRegistrationServiceNode(std::map<std::wstring,dsreg::CJsonValue *> const &,_DISCOVERY_METADATA *)
0x18009b589  mov     edi, eax
0x18009b58b  test    eax, eax
0x18009b58d  jns     short loc_18009B598
0x18009b58f  lea     r8, aParsedevicereg; "ParseDeviceRegistrationServiceNode"
0x18009b596  jmp     short loc_18009B546
0x18009b598  mov     rdx, rsi
0x18009b59b  mov     rcx, r14
0x18009b59e  call    ?ParseAuthenticationServiceNode@DiscoveryResponseParser@@AEAAJAEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCJsonValue@dsreg@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCJsonValue@dsreg@@@std@@@2@@std@@PEAU_DISCOVERY_METADATA@@@Z; DiscoveryResponseParser::ParseAuthenticationServiceNode(std::map<std::wstring,dsreg::CJsonValue *> const &,_DISCOVERY_METADATA *)
0x18009b5a3  mov     edi, eax
0x18009b5a5  test    eax, eax
0x18009b5a7  jns     short loc_18009B5B2
0x18009b5a9  lea     r8, aParseauthentic; "ParseAuthenticationServiceNode"
0x18009b5b0  jmp     short loc_18009B546
0x18009b5b2  mov     r8, [rbx]
0x18009b5b5  mov     rdx, rsi
0x18009b5b8  mov     rcx, r14
0x18009b5bb  call    ?ParseDeviceJoinServiceNode@DiscoveryResponseParser@@AEAAJAEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCJsonValue@dsreg@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCJsonValue@dsreg@@@std@@@2@@std@@PEAU_DISCOVERY_METADATA@@@Z; DiscoveryResponseParser::ParseDeviceJoinServiceNode(std::map<std::wstring,dsreg::CJsonValue *> const &,_DISCOVERY_METADATA *)
0x18009b5c0  mov     edi, eax
0x18009b5c2  test    eax, eax
0x18009b5c4  jns     short loc_18009B5D2
0x18009b5c6  lea     r8, aParsedevicejoi; "ParseDeviceJoinServiceNode"
0x18009b5cd  jmp     loc_18009B546
0x18009b5d2  mov     r8, [rbx]
0x18009b5d5  mov     rdx, rsi
0x18009b5d8  call    ?ParseKeyProvisioningServiceNode@DiscoveryResponseParser@@AEAAJAEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCJsonValue@dsreg@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCJsonValue@dsreg@@@std@@@2@@std@@PEAU_DISCOVERY_METADATA@@@Z; DiscoveryResponseParser::ParseKeyProvisioningServiceNode(std::map<std::wstring,dsreg::CJsonValue *> const &,_DISCOVERY_METADATA *)
0x18009b5dd  mov     edi, eax
0x18009b5df  test    eax, eax
0x18009b5e1  jns     short loc_18009B5EF
0x18009b5e3  lea     r8, aParsekeyprovis; "ParseKeyProvisioningServiceNode"
0x18009b5ea  jmp     loc_18009B546
0x18009b5ef  cmp     dword ptr [r14+18h], 3
0x18009b5f4  jl      short loc_18009B650
0x18009b5f6  mov     r8, [rbx]
0x18009b5f9  mov     rdx, rsi
0x18009b5fc  call    ?ParseWebAuthNServiceNode@DiscoveryResponseParser@@AEAAJAEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCJsonValue@dsreg@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCJsonValue@dsreg@@@std@@@2@@std@@PEAU_DISCOVERY_METADATA@@@Z; DiscoveryResponseParser::ParseWebAuthNServiceNode(std::map<std::wstring,dsreg::CJsonValue *> const &,_DISCOVERY_METADATA *)
0x18009b601  mov     edi, eax
0x18009b603  test    eax, eax
0x18009b605  jns     short loc_18009B613
0x18009b607  lea     r8, aParsewebauthns; "ParseWebAuthNServiceNode"
0x18009b60e  jmp     loc_18009B546
0x18009b613  mov     r8, [rbx]
0x18009b616  mov     rdx, rsi
0x18009b619  mov     rcx, r14
0x18009b61c  call    ?ParseDeviceManagementServiceNode@DiscoveryResponseParser@@AEAAJAEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCJsonValue@dsreg@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCJsonValue@dsreg@@@std@@@2@@std@@PEAU_DISCOVERY_METADATA@@@Z; DiscoveryResponseParser::ParseDeviceManagementServiceNode(std::map<std::wstring,dsreg::CJsonValue *> const &,_DISCOVERY_METADATA *)
0x18009b621  mov     edi, eax
0x18009b623  test    eax, eax
0x18009b625  jns     short loc_18009B633
0x18009b627  lea     r8, aParsedeviceman; "ParseDeviceManagementServiceNode"
0x18009b62e  jmp     loc_18009B546
0x18009b633  mov     r8, [rbx]
0x18009b636  mov     rdx, rsi
0x18009b639  call    ?ParseMsaProviderDataNode@DiscoveryResponseParser@@AEAAJAEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCJsonValue@dsreg@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCJsonValue@dsreg@@@std@@@2@@std@@PEAU_DISCOVERY_METADATA@@@Z; DiscoveryResponseParser::ParseMsaProviderDataNode(std::map<std::wstring,dsreg::CJsonValue *> const &,_DISCOVERY_METADATA *)
0x18009b63e  mov     edi, eax
0x18009b640  test    eax, eax
0x18009b642  jns     short loc_18009B650
0x18009b644  lea     r8, aParsemsaprovid; "ParseMsaProviderDataNode"
0x18009b64b  jmp     loc_18009B546
0x18009b650  cmp     dword ptr [r14+18h], 4
0x18009b655  jl      short loc_18009B691
0x18009b657  mov     r8, [rbx]
0x18009b65a  mov     rdx, rsi
0x18009b65d  call    ?ParsePrecreateServiceNode@DiscoveryResponseParser@@AEAAJAEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCJsonValue@dsreg@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCJsonValue@dsreg@@@std@@@2@@std@@PEAU_DISCOVERY_METADATA@@@Z; DiscoveryResponseParser::ParsePrecreateServiceNode(std::map<std::wstring,dsreg::CJsonValue *> const &,_DISCOVERY_METADATA *)
0x18009b662  mov     edi, eax
0x18009b664  test    eax, eax
0x18009b666  jns     short loc_18009B674
0x18009b668  lea     r8, aParseprecreate; "ParsePrecreateServiceNode"
0x18009b66f  jmp     loc_18009B546
0x18009b674  mov     r8, [rbx]
0x18009b677  mov     rdx, rsi
0x18009b67a  call    ?ParseTenantInfoNode@DiscoveryResponseParser@@AEAAJAEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCJsonValue@dsreg@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCJsonValue@dsreg@@@std@@@2@@std@@PEAU_DISCOVERY_METADATA@@@Z; DiscoveryResponseParser::ParseTenantInfoNode(std::map<std::wstring,dsreg::CJsonValue *> const &,_DISCOVERY_METADATA *)
0x18009b67f  mov     edi, eax
0x18009b681  test    eax, eax
0x18009b683  jns     short loc_18009B691
0x18009b685  lea     r8, aParsetenantinf; "ParseTenantInfoNode"
0x18009b68c  jmp     loc_18009B546
0x18009b691  cmp     dword ptr [r14+18h], 5
0x18009b696  jl      short loc_18009B6B5
0x18009b698  mov     r8, [rbx]
0x18009b69b  mov     rdx, rsi
0x18009b69e  call    ?ParseAzureRbacServiceNode@DiscoveryResponseParser@@AEAAJAEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCJsonValue@dsreg@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCJsonValue@dsreg@@@std@@@2@@std@@PEAU_DISCOVERY_METADATA@@@Z; DiscoveryResponseParser::ParseAzureRbacServiceNode(std::map<std::wstring,dsreg::CJsonValue *> const &,_DISCOVERY_METADATA *)
0x18009b6a3  mov     edi, eax
0x18009b6a5  test    eax, eax
0x18009b6a7  jns     short loc_18009B6B5
0x18009b6a9  lea     r8, aParseazurerbac; "ParseAzureRbacServiceNode"
0x18009b6b0  jmp     loc_18009B546
0x18009b6b5  cmp     dword ptr [r14+18h], 6
0x18009b6ba  jl      short loc_18009B6DC
0x18009b6bc  mov     r8, [rbx]
0x18009b6bf  mov     rdx, rsi
0x18009b6c2  mov     rcx, r14
0x18009b6c5  call    ?ParseDeviceJoinResourceServiceNode@DiscoveryResponseParser@@AEAAJAEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCJsonValue@dsreg@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCJsonValue@dsreg@@@std@@@2@@std@@PEAU_DISCOVERY_METADATA@@@Z; DiscoveryResponseParser::ParseDeviceJoinResourceServiceNode(std::map<std::wstring,dsreg::CJsonValue *> const &,_DISCOVERY_METADATA *)
0x18009b6ca  mov     edi, eax
0x18009b6cc  test    eax, eax
0x18009b6ce  jns     short loc_18009B6DC
0x18009b6d0  lea     r8, aParsedevicejoi_0; "ParseDeviceJoinResourceServiceNode"
0x18009b6d7  jmp     loc_18009B546
0x18009b6dc  mov     rdx, [rbx]
0x18009b6df  add     rdx, 0A8h; unsigned __int16 **
0x18009b6e6  mov     rcx, [r14+10h]; unsigned __int16 *
0x18009b6ea  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x18009b6ef  mov     edi, eax
0x18009b6f1  test    eax, eax
0x18009b6f3  jns     short loc_18009B723
0x18009b6f5  lea     r8, aCopystringnull; "CopyStringNullSafeW"
0x18009b6fc  jmp     loc_18009B546
0x18009b701  mov     [rbx], r12
0x18009b704  mov     edi, 8007000Eh
0x18009b709  mov     rdx, r13
0x18009b70c  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x18009b713  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18009b718  mov     rcx, [rbx]; void *
0x18009b71b  call    DsrFreeDiscoveryMetadata
0x18009b720  mov     [rbx], r12
0x18009b723  mov     r8d, edi
0x18009b726  mov     rdx, r13
0x18009b729  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18009b730  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18009b735  nop
0x18009b736  lea     rcx, [rbp+57h+var_90]; this
0x18009b73a  call    ??1CJsonValue@dsreg@@QEAA@XZ; dsreg::CJsonValue::~CJsonValue(void)
0x18009b73f  nop
0x18009b740  mov     rcx, [rbp+57h+Block]; Block
0x18009b744  call    cs:__imp_free
0x18009b74a  mov     eax, edi
0x18009b74c  mov     rcx, [rbp+57h+var_40]
0x18009b750  xor     rcx, rsp; StackCookie
0x18009b753  call    __security_check_cookie
0x18009b758  mov     rbx, [rsp+100h+arg_18]
0x18009b760  add     rsp, 0D0h
0x18009b767  pop     r15
0x18009b769  pop     r14
0x18009b76b  pop     r13
0x18009b76d  pop     r12
0x18009b76f  pop     rdi
0x18009b770  pop     rsi
0x18009b771  pop     rbp
0x18009b772  retn
```
