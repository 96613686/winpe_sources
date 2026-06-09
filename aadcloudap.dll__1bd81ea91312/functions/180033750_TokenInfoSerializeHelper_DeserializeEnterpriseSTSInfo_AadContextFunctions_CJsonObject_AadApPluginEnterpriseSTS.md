# TokenInfoSerializeHelper::DeserializeEnterpriseSTSInfo(AadContextFunctions *,CJsonObject *,_AadApPluginEnterpriseSTSInfo *)

- ea: `0x180033750`
- end: `0x180033a9d`
- name: `?DeserializeEnterpriseSTSInfo@TokenInfoSerializeHelper@@CAJPEAVAadContextFunctions@@PEAVCJsonObject@@PEAU_AadApPluginEnterpriseSTSInfo@@@Z`
- size: `845`
- prototype: `__int64 __fastcall(struct AadContextFunctions *, struct CJsonObject *, struct _AadApPluginEnterpriseSTSInfo *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180033e08`
- `0x180034590`

## callees

- `0x1800090d0`
- `0x18000a300`
- `0x180033750`
- `0x180033aa4`
- `0x180071e14`
- `0x180078780`
- `0x1800787ec`
- `0x18007a070`
- `0x18007a0bc`
- `0x18007a0fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003399c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003399c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033a42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033a42`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180033992`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180033992`

## string_xrefs

- `0x1800337cb`: `AuthorityUri`
- `0x180033848`: `AuthorizationEndpointUri`
- `0x18003381f`: `TokenEndpointUri`
- `0x18003390f`: `RefreshTokenInfo`
- `0x180033971`: `UserSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall TokenInfoSerializeHelper::DeserializeEnterpriseSTSInfo(
        struct AadContextFunctions *a1,
        struct CJsonObject *a2,
        struct _AadApPluginEnterpriseSTSInfo *a3)
{
  signed int v6; // edi
  int v7; // r8d
  unsigned __int16 *v8; // rbx
  int v9; // r8d
  int v10; // r8d
  int v11; // r8d
  int v12; // r8d
  struct CJsonObject *JsonDataAsObject; // rax
  int v14; // eax
  signed int LastError; // eax
  int v17; // [rsp+20h] [rbp-60h]
  signed int v18; // [rsp+20h] [rbp-60h]
  int v19; // [rsp+30h] [rbp-50h]
  int v20; // [rsp+30h] [rbp-50h]
  unsigned __int16 *v21; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int16 *v22; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int16 *v23; // [rsp+60h] [rbp-20h] BYREF
  unsigned __int16 *v24; // [rsp+68h] [rbp-18h] BYREF
  unsigned __int16 *v25[2]; // [rsp+70h] [rbp-10h] BYREF
  PSID Sid; // [rsp+C0h] [rbp+40h] BYREF
  LPCWSTR StringSid; // [rsp+C8h] [rbp+48h] BYREF

  v6 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v25);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v24);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v23);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v22);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v21);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&StringSid);
  Sid = 0;
  *(_DWORD *)a3 = (int)WebResponseHelper::GetJsonDataAsNumber(a2, L"Version");
  WebResponseHelper::GetJsonDataAsString(a2, L"AuthorityUri", v25);
  v8 = v25[0];
  if ( *((_DWORD *)v25[0] - 4) )
    DuplicateString(a1, v25[0], v7, (unsigned __int16 **)a3 + 1);
  WebResponseHelper::GetJsonDataAsString(a2, L"Issuer", &v24);
  if ( *((_DWORD *)v24 - 4) )
    DuplicateString(a1, v24, v9, (unsigned __int16 **)a3 + 4);
  WebResponseHelper::GetJsonDataAsString(a2, L"TokenEndpointUri", &v22);
  if ( *((_DWORD *)v8 - 4) )
    DuplicateString(a1, v22, v10, (unsigned __int16 **)a3 + 2);
  WebResponseHelper::GetJsonDataAsString(a2, L"AuthorizationEndpointUri", &v23);
  if ( *((_DWORD *)v23 - 4) )
    DuplicateString(a1, v23, v11, (unsigned __int16 **)a3 + 3);
  WebResponseHelper::GetJsonDataAsString(a2, L"Subject", &v21);
  if ( *((_DWORD *)v21 - 4) )
    DuplicateString(a1, v21, v12, (unsigned __int16 **)a3 + 5);
  *((_QWORD *)a3 + 7) = (unsigned int)(int)WebResponseHelper::GetJsonDataAsNumber(a2, L"LastTriedTime");
  *((_DWORD *)a3 + 12) = (int)WebResponseHelper::GetJsonDataAsNumber(a2, L"PRTSupported");
  *((_DWORD *)a3 + 36) = (int)WebResponseHelper::GetJsonDataAsNumber(a2, L"WinHelloSupported");
  *((_DWORD *)a3 + 37) = (int)WebResponseHelper::GetJsonDataAsNumber(a2, L"WinHelloKeyReceiptSupported");
  *((_DWORD *)a3 + 40) = (int)WebResponseHelper::GetJsonDataAsNumber(a2, L"KdfVer2");
  JsonDataAsObject = WebResponseHelper::GetJsonDataAsObject(a2, L"RefreshTokenInfo");
  if ( JsonDataAsObject )
  {
    v14 = TokenInfoSerializeHelper::DeserializeEnterpriseTokenInfo(
            a1,
            JsonDataAsObject,
            (struct _AadApPluginEnterpriseSTSInfo *)((char *)a3 + 64));
    v6 = v14;
    if ( v14 < 0 )
    {
      v19 = 1448;
      v17 = v14;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v17, "serializetokeninfo.cpp", v19, "HRESULT", &base);
      goto LABEL_23;
    }
  }
  WebResponseHelper::GetJsonDataAsString(a2, L"UserSID", &StringSid);
  if ( *((_DWORD *)StringSid - 4) )
  {
    if ( ConvertStringSidToSidW(StringSid, &Sid) )
      goto LABEL_20;
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 >= 0 )
    {
LABEL_20:
      if ( DuplicateSID(a1, Sid, (void **)a3 + 19) >= 0 )
        goto LABEL_23;
      v6 = -2147187625;
      v20 = 1458;
    }
    else
    {
      v20 = 1454;
    }
    v18 = v6;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v18, "serializetokeninfo.cpp", v20, "HRESULT", &base);
  }
LABEL_23:
  if ( Sid )
    LocalFree(Sid);
  CSecureString::~CSecureString((CSecureString *)&StringSid);
  CSecureString::~CSecureString((CSecureString *)&v21);
  CSecureString::~CSecureString((CSecureString *)&v22);
  CSecureString::~CSecureString((CSecureString *)&v23);
  CSecureString::~CSecureString((CSecureString *)&v24);
  CSecureString::~CSecureString((CSecureString *)v25);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180033750  mov     [rsp-28h+arg_0], rbx
0x180033755  push    rbp
0x180033756  push    rsi
0x180033757  push    rdi
0x180033758  push    r14
0x18003375a  push    r15
0x18003375c  mov     rbp, rsp
0x18003375f  sub     rsp, 80h
0x180033766  mov     rsi, r8
0x180033769  mov     r14, rdx
0x18003376c  mov     r15, rcx
0x18003376f  xor     edi, edi
0x180033771  lea     rcx, [rbp+var_10]; void *
0x180033775  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18003377a  nop
0x18003377b  lea     rcx, [rbp+var_18]; void *
0x18003377f  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180033784  nop
0x180033785  lea     rcx, [rbp+var_20]; void *
0x180033789  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18003378e  nop
0x18003378f  lea     rcx, [rbp+var_28]; void *
0x180033793  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180033798  nop
0x180033799  lea     rcx, [rbp+var_30]; void *
0x18003379d  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800337a2  nop
0x1800337a3  lea     rcx, [rbp+StringSid]; void *
0x1800337a7  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800337ac  nop
0x1800337ad  mov     [rbp+Sid], rdi
0x1800337b1  lea     rdx, aVersion_0; "Version"
0x1800337b8  mov     rcx, r14; struct CJsonObject *
0x1800337bb  call    ?GetJsonDataAsNumber@WebResponseHelper@@SANPEAVCJsonObject@@PEBG@Z; WebResponseHelper::GetJsonDataAsNumber(CJsonObject *,ushort const *)
0x1800337c0  cvttsd2si rax, xmm0
0x1800337c5  mov     [rsi], eax
0x1800337c7  lea     r8, [rbp+var_10]
0x1800337cb  lea     rdx, aAuthorityuri; "AuthorityUri"
0x1800337d2  mov     rcx, r14
0x1800337d5  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800337da  mov     rbx, [rbp+var_10]
0x1800337de  cmp     [rbx-10h], edi
0x1800337e1  jz      short loc_1800337F2
0x1800337e3  lea     r9, [rsi+8]; unsigned __int16 **
0x1800337e7  mov     rdx, rbx; unsigned __int16 *
0x1800337ea  mov     rcx, r15; struct AadContextFunctions *
0x1800337ed  call    ?DuplicateString@@YAJPEAVAadContextFunctions@@PEBGHPEAPEAG@Z; DuplicateString(AadContextFunctions *,ushort const *,int,ushort * *)
0x1800337f2  lea     r8, [rbp+var_18]
0x1800337f6  lea     rdx, aIssuer; "Issuer"
0x1800337fd  mov     rcx, r14
0x180033800  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180033805  mov     rdx, [rbp+var_18]; unsigned __int16 *
0x180033809  cmp     dword ptr [rdx-10h], 0
0x18003380d  jz      short loc_18003381B
0x18003380f  lea     r9, [rsi+20h]; unsigned __int16 **
0x180033813  mov     rcx, r15; struct AadContextFunctions *
0x180033816  call    ?DuplicateString@@YAJPEAVAadContextFunctions@@PEBGHPEAPEAG@Z; DuplicateString(AadContextFunctions *,ushort const *,int,ushort * *)
0x18003381b  lea     r8, [rbp+var_28]
0x18003381f  lea     rdx, aTokenendpointu; "TokenEndpointUri"
0x180033826  mov     rcx, r14
0x180033829  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18003382e  cmp     dword ptr [rbx-10h], 0
0x180033832  jz      short loc_180033844
0x180033834  lea     r9, [rsi+10h]; unsigned __int16 **
0x180033838  mov     rdx, [rbp+var_28]; unsigned __int16 *
0x18003383c  mov     rcx, r15; struct AadContextFunctions *
0x18003383f  call    ?DuplicateString@@YAJPEAVAadContextFunctions@@PEBGHPEAPEAG@Z; DuplicateString(AadContextFunctions *,ushort const *,int,ushort * *)
0x180033844  lea     r8, [rbp+var_20]
0x180033848  lea     rdx, aAuthorizatione; "AuthorizationEndpointUri"
0x18003384f  mov     rcx, r14
0x180033852  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180033857  mov     rdx, [rbp+var_20]; unsigned __int16 *
0x18003385b  cmp     dword ptr [rdx-10h], 0
0x18003385f  jz      short loc_18003386D
0x180033861  lea     r9, [rsi+18h]; unsigned __int16 **
0x180033865  mov     rcx, r15; struct AadContextFunctions *
0x180033868  call    ?DuplicateString@@YAJPEAVAadContextFunctions@@PEBGHPEAPEAG@Z; DuplicateString(AadContextFunctions *,ushort const *,int,ushort * *)
0x18003386d  lea     r8, [rbp+var_30]
0x180033871  lea     rdx, aSubject; "Subject"
0x180033878  mov     rcx, r14
0x18003387b  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180033880  mov     rdx, [rbp+var_30]; unsigned __int16 *
0x180033884  cmp     dword ptr [rdx-10h], 0
0x180033888  jz      short loc_180033896
0x18003388a  lea     r9, [rsi+28h]; unsigned __int16 **
0x18003388e  mov     rcx, r15; struct AadContextFunctions *
0x180033891  call    ?DuplicateString@@YAJPEAVAadContextFunctions@@PEBGHPEAPEAG@Z; DuplicateString(AadContextFunctions *,ushort const *,int,ushort * *)
0x180033896  lea     rdx, aLasttriedtime; "LastTriedTime"
0x18003389d  mov     rcx, r14; struct CJsonObject *
0x1800338a0  call    ?GetJsonDataAsNumber@WebResponseHelper@@SANPEAVCJsonObject@@PEBG@Z; WebResponseHelper::GetJsonDataAsNumber(CJsonObject *,ushort const *)
0x1800338a5  cvttsd2si rax, xmm0
0x1800338aa  mov     [rsi+38h], rax
0x1800338ae  lea     rdx, aPrtsupported; "PRTSupported"
0x1800338b5  mov     rcx, r14; struct CJsonObject *
0x1800338b8  call    ?GetJsonDataAsNumber@WebResponseHelper@@SANPEAVCJsonObject@@PEBG@Z; WebResponseHelper::GetJsonDataAsNumber(CJsonObject *,ushort const *)
0x1800338bd  cvttsd2si eax, xmm0
0x1800338c1  mov     [rsi+30h], eax
0x1800338c4  lea     rdx, aWinhellosuppor; "WinHelloSupported"
0x1800338cb  mov     rcx, r14; struct CJsonObject *
0x1800338ce  call    ?GetJsonDataAsNumber@WebResponseHelper@@SANPEAVCJsonObject@@PEBG@Z; WebResponseHelper::GetJsonDataAsNumber(CJsonObject *,ushort const *)
0x1800338d3  cvttsd2si eax, xmm0
0x1800338d7  mov     [rsi+90h], eax
0x1800338dd  lea     rdx, aWinhellokeyrec; "WinHelloKeyReceiptSupported"
0x1800338e4  mov     rcx, r14; struct CJsonObject *
0x1800338e7  call    ?GetJsonDataAsNumber@WebResponseHelper@@SANPEAVCJsonObject@@PEBG@Z; WebResponseHelper::GetJsonDataAsNumber(CJsonObject *,ushort const *)
0x1800338ec  cvttsd2si eax, xmm0
0x1800338f0  mov     [rsi+94h], eax
0x1800338f6  lea     rdx, aKdfver2; "KdfVer2"
0x1800338fd  mov     rcx, r14; struct CJsonObject *
0x180033900  call    ?GetJsonDataAsNumber@WebResponseHelper@@SANPEAVCJsonObject@@PEBG@Z; WebResponseHelper::GetJsonDataAsNumber(CJsonObject *,ushort const *)
0x180033905  cvttsd2si eax, xmm0
0x180033909  mov     [rsi+0A0h], eax
0x18003390f  lea     rdx, aRefreshtokenin; "RefreshTokenInfo"
0x180033916  mov     rcx, r14; struct CJsonObject *
0x180033919  call    ?GetJsonDataAsObject@WebResponseHelper@@SAPEAVCJsonObject@@PEAV2@PEBG@Z; WebResponseHelper::GetJsonDataAsObject(CJsonObject *,ushort const *)
0x18003391e  test    rax, rax
0x180033921  jz      short loc_18003396D
0x180033923  lea     r8, [rsi+40h]; struct _AadApPluginEnterpriseTokenInfo *
0x180033927  mov     rdx, rax; struct CJsonObject *
0x18003392a  mov     rcx, r15; struct AadContextFunctions *
0x18003392d  call    ?DeserializeEnterpriseTokenInfo@TokenInfoSerializeHelper@@CAJPEAVAadContextFunctions@@PEAVCJsonObject@@PEAU_AadApPluginEnterpriseTokenInfo@@@Z; TokenInfoSerializeHelper::DeserializeEnterpriseTokenInfo(AadContextFunctions *,CJsonObject *,_AadApPluginEnterpriseTokenInfo *)
0x180033932  mov     edi, eax
0x180033934  test    eax, eax
0x180033936  jns     short loc_18003396D
0x180033938  lea     rcx, base
0x18003393f  mov     [rsp+80h+var_40], rcx
0x180033944  lea     rcx, aHresult; "HRESULT"
0x18003394b  mov     [rsp+80h+var_48], rcx
0x180033950  mov     [rsp+80h+var_50], 5A8h
0x180033958  lea     rcx, aOnecoreuapDsEx_11+21h; "serializetokeninfo.cpp"
0x18003395f  mov     [rsp+80h+var_58], rcx
0x180033964  mov     [rsp+80h+var_60], eax
0x180033968  jmp     loc_180033A23
0x18003396d  lea     r8, [rbp+StringSid]
0x180033971  lea     rdx, aUsersid; "UserSID"
0x180033978  mov     rcx, r14
0x18003397b  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180033980  mov     rcx, [rbp+StringSid]; StringSid
0x180033984  cmp     dword ptr [rcx-10h], 0
0x180033988  jz      loc_180033A39
0x18003398e  lea     rdx, [rbp+Sid]; Sid
0x180033992  call    cs:__imp_ConvertStringSidToSidW
0x180033998  test    eax, eax
0x18003399a  jnz     short loc_1800339D7
0x18003399c  call    cs:__imp_GetLastError
0x1800339a2  mov     edi, eax
0x1800339a4  test    eax, eax
0x1800339a6  jle     short loc_1800339B1
0x1800339a8  movzx   edi, ax
0x1800339ab  or      edi, 80070000h
0x1800339b1  test    edi, edi
0x1800339b3  jns     short loc_1800339D7
0x1800339b5  lea     rcx, base
0x1800339bc  mov     [rsp+80h+var_40], rcx
0x1800339c1  lea     rcx, aHresult; "HRESULT"
0x1800339c8  mov     [rsp+80h+var_48], rcx
0x1800339cd  mov     [rsp+80h+var_50], 5AEh
0x1800339d5  jmp     short loc_180033A13
0x1800339d7  lea     r8, [rsi+98h]; void **
0x1800339de  mov     rdx, [rbp+Sid]; void *
0x1800339e2  mov     rcx, r15; struct AadContextFunctions *
0x1800339e5  call    ?DuplicateSID@@YAJPEAVAadContextFunctions@@PEAXPEAPEAX@Z; DuplicateSID(AadContextFunctions *,void *,void * *)
0x1800339ea  test    eax, eax
0x1800339ec  jns     short loc_180033A39
0x1800339ee  mov     edi, 80048457h
0x1800339f3  lea     rcx, base
0x1800339fa  mov     [rsp+80h+var_40], rcx
0x1800339ff  lea     rcx, aHresult; "HRESULT"
0x180033a06  mov     [rsp+80h+var_48], rcx
0x180033a0b  mov     [rsp+80h+var_50], 5B2h
0x180033a13  lea     rcx, aOnecoreuapDsEx_11+21h; "serializetokeninfo.cpp"
0x180033a1a  mov     [rsp+80h+var_58], rcx
0x180033a1f  mov     [rsp+80h+var_60], edi
0x180033a23  mov     ecx, 2
0x180033a28  mov     r9d, ecx
0x180033a2b  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180033a32  xor     edx, edx
0x180033a34  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180033a39  mov     rcx, [rbp+Sid]; hMem
0x180033a3d  test    rcx, rcx
0x180033a40  jz      short loc_180033A49
0x180033a42  call    cs:__imp_LocalFree
0x180033a48  nop
0x180033a49  lea     rcx, [rbp+StringSid]; this
0x180033a4d  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x180033a52  nop
0x180033a53  lea     rcx, [rbp+var_30]; this
0x180033a57  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x180033a5c  nop
0x180033a5d  lea     rcx, [rbp+var_28]; this
0x180033a61  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x180033a66  nop
0x180033a67  lea     rcx, [rbp+var_20]; this
0x180033a6b  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x180033a70  nop
0x180033a71  lea     rcx, [rbp+var_18]; this
0x180033a75  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x180033a7a  nop
0x180033a7b  lea     rcx, [rbp+var_10]; this
0x180033a7f  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x180033a84  mov     eax, edi
0x180033a86  mov     rbx, [rsp+80h+arg_0]
0x180033a8e  add     rsp, 80h
0x180033a95  pop     r15
0x180033a97  pop     r14
0x180033a99  pop     rdi
0x180033a9a  pop     rsi
0x180033a9b  pop     rbp
0x180033a9c  retn
```
