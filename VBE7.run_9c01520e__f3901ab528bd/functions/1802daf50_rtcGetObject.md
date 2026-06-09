# rtcGetObject

- ea: `0x1802daf50`
- end: `0x1802db3b1`
- name: `rtcGetObject`
- size: `1121`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1800e64b4`
- `0x1800f09f0`
- `0x1800fa390`
- `0x1801012ec`
- `0x180102944`
- `0x180102a4c`
- `0x18011d6f4`
- `0x1801751d8`
- `0x18024bf28`
- `0x1802d9e1c`
- `0x1802daf50`
- `0x180350ad8`
- `0x180379520`

## import_xrefs

- `MSVCR100!_wcsicmp` at `0x1802db082`
- `MSVCR100!_wcsicmp` at `0x1802db082`
- `ole32!CreateBindCtx` at `0x1802daf9b`
- `ole32!CreateBindCtx` at `0x1802daf9b`
- `ole32!MkParseDisplayName` at `0x1802dafdf`
- `ole32!MkParseDisplayName` at `0x1802dafdf`
- `ole32!BindMoniker` at `0x1802db02c`
- `ole32!BindMoniker` at `0x1802db02c`
- `ole32!CoCreateInstance` at `0x1802db15e`
- `ole32!CoCreateInstance` at `0x1802db15e`
- `OLEAUT32!__imp_SysFreeString` at `0x1802daff1`
- `OLEAUT32!__imp_SysFreeString` at `0x1802db091`
- `OLEAUT32!__imp_SysFreeString` at `0x1802db0d4`
- `OLEAUT32!__imp_SysFreeString` at `0x1802db2aa`
- `OLEAUT32!__imp_SysFreeString` at `0x1802daff1`
- `OLEAUT32!__imp_SysFreeString` at `0x1802db091`
- `OLEAUT32!__imp_SysFreeString` at `0x1802db0d4`
- `OLEAUT32!__imp_SysFreeString` at `0x1802db2aa`
- `OLEAUT32!__imp_GetActiveObject` at `0x1802db105`
- `OLEAUT32!__imp_GetActiveObject` at `0x1802db105`

## pseudocode

```c
void *__fastcall rtcGetObject(void *a1, VARIANTARG *a2, VARIANTARG *a3)
{
  HRESULT v4; // [rsp+30h] [rbp-F0h]
  HRESULT v5; // [rsp+30h] [rbp-F0h]
  unsigned int v6; // [rsp+30h] [rbp-F0h]
  int v7; // [rsp+30h] [rbp-F0h]
  HRESULT ActiveObject; // [rsp+30h] [rbp-F0h]
  SCODE v9; // [rsp+30h] [rbp-F0h]
  LPVOID ppvResult; // [rsp+38h] [rbp-E8h] BYREF
  __int64 v11; // [rsp+40h] [rbp-E0h] BYREF
  __int64 v12; // [rsp+48h] [rbp-D8h] BYREF
  wchar_t *String2; // [rsp+50h] [rbp-D0h]
  __int64 v14; // [rsp+58h] [rbp-C8h] BYREF
  LPBC ppbc; // [rsp+60h] [rbp-C0h] BYREF
  LPMONIKER ppmk; // [rsp+68h] [rbp-B8h] BYREF
  ULONG pchEaten; // [rsp+70h] [rbp-B0h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp-A8h]
  LPCOLESTR szUserName; // [rsp+80h] [rbp-A0h]
  __int64 v20; // [rsp+88h] [rbp-98h] BYREF
  _QWORD v21[3]; // [rsp+90h] [rbp-90h] BYREF
  struct tagEXCEPINFO v22; // [rsp+B0h] [rbp-70h] BYREF
  IID rclsid; // [rsp+F0h] [rbp-30h] BYREF

  if ( (unsigned __int16)rtIsMissing(a3) )
  {
    pchEaten = 0;
    v4 = CreateBindCtx(0, &ppbc);
    if ( v4 < 0 )
      HresultCheck((unsigned int)v4, 0);
    szUserName = (LPCOLESTR)_vbaStrVarCopy(a2);
    v5 = MkParseDisplayName(ppbc, szUserName, &pchEaten, &ppmk);
    SysFreeString((BSTR)szUserName);
    ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
    if ( v5 < 0 )
      HresultCheck((unsigned int)v5, 0);
    v6 = BindMoniker(ppmk, 0, &IID_IUnknown, &ppvResult);
    ((void (__fastcall *)(LPMONIKER))ppmk->lpVtbl->Release)(ppmk);
    HresultCheck(v6, 0);
    if ( !ppvResult )
      EbRaiseExceptionCode(429);
  }
  else
  {
    String2 = (wchar_t *)_vbaStrVarCopy(a3);
    if ( _wcsicmp(L"vbscript.regexp", String2) )
    {
      v7 = g_pfnCLSIDFromProgidEx(String2, &rclsid);
      SysFreeString(String2);
      if ( v7 < 0 )
        HresultCheck((unsigned int)v7, 0);
      if ( (unsigned __int16)rtIsMissing(a2) )
      {
        ActiveObject = GetActiveObject(&rclsid, 0, (IUnknown **)&ppvResult);
        if ( ActiveObject < 0 )
          HresultCheck((unsigned int)ActiveObject, 0);
        if ( !ppvResult )
          EbRaiseExceptionCode(429);
      }
      else
      {
        v11 = 0;
        v9 = CoCreateInstance(&rclsid, 0, 0x15u, &IID_IUnknown, &ppvResult);
        if ( v9 < 0 )
          HresultCheck((unsigned int)v9, 0);
        if ( !ppvResult )
          EbRaiseExceptionCode(429);
        bstrString = (BSTR)_vbaStrVarCopy(a2);
        if ( (unsigned int)BstrLen(bstrString) )
        {
          if ( (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))ppvResult)(ppvResult, &IID_IPersistFile, &v11) >= 0 )
          {
            v9 = (*(__int64 (__fastcall **)(__int64, BSTR, _QWORD))(*(_QWORD *)v11 + 40LL))(v11, bstrString, 0);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
            if ( v9 == 1 )
              v9 = HresultOfEberr(429);
          }
          else
          {
            v9 = HresultOfEberr(432);
          }
        }
        else if ( (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))ppvResult)(
                    ppvResult,
                    &IID_IPersistStreamInit,
                    &v12) < 0 )
        {
          if ( (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))ppvResult)(ppvResult, &IID_IPersistPropertyBag, &v14) >= 0 )
          {
            v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 32LL))(v14);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          }
        }
        else
        {
          v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 64LL))(v12);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        }
        SysFreeString(bstrString);
        if ( v9 < 0 )
        {
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppvResult + 16LL))(ppvResult);
          ppvResult = 0;
          if ( !(unsigned int)GetErrorInfo(&v22) )
          {
            v22.scode = v9;
            v22.wCode = 0;
            EbRaiseException(&v22);
          }
          HresultCheck((unsigned int)v9, 0);
        }
      }
      if ( (unsigned int)IsCapabilityEnabled(2) )
        TELMGR::OnComObjectInstantiated(&rclsid);
    }
    else
    {
      SysFreeString(String2);
      if ( (int)CRegExp::Create((struct IUnknown **)&ppvResult) < 0 || !ppvResult )
        EbRaiseExceptionCode(429);
    }
  }
  if ( (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))ppvResult)(ppvResult, &IID_IDispatch, &v20) >= 0 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppvResult + 16LL))(ppvResult);
    LOWORD(v21[0]) = 9;
    v21[1] = v20;
  }
  else
  {
    LOWORD(v21[0]) = 13;
    v21[1] = ppvResult;
  }
  qmemcpy(a1, v21, 0x18u);
  return a1;
}

```

## disassembly

```asm
0x1802daf50  mov     [rsp-8+arg_10], r8
0x1802daf55  mov     [rsp-8+arg_8], rdx
0x1802daf5a  mov     [rsp-8+arg_0], rcx
0x1802daf5f  push    rbp
0x1802daf60  mov     rbp, rsp
0x1802daf63  push    rsi
0x1802daf64  push    rdi
0x1802daf65  sub     rsp, 110h
0x1802daf6c  mov     rax, cs:__security_cookie
0x1802daf73  xor     rax, rsp
0x1802daf76  mov     [rbp+var_20], rax
0x1802daf7a  mov     rcx, [rbp+arg_10]
0x1802daf7e  call    rtIsMissing
0x1802daf83  cwde
0x1802daf84  test    eax, eax
0x1802daf86  jz      loc_1802DB068
0x1802daf8c  mov     [rsp+120h+pchEaten], 0
0x1802daf94  lea     rdx, [rsp+120h+ppbc]; ppbc
0x1802daf99  xor     ecx, ecx; reserved
0x1802daf9b  call    cs:__imp_CreateBindCtx
0x1802dafa1  mov     [rsp+120h+var_F0], eax
0x1802dafa5  cmp     [rsp+120h+var_F0], 0
0x1802dafaa  jge     short loc_1802DAFB7
0x1802dafac  xor     edx, edx
0x1802dafae  mov     ecx, [rsp+120h+var_F0]
0x1802dafb2  call    HresultCheck
0x1802dafb7  mov     rcx, [rbp+arg_8]
0x1802dafbb  call    __vbaStrVarCopy
0x1802dafc0  mov     [rsp+120h+szUserName], rax
0x1802dafc8  lea     r9, [rsp+120h+ppmk]; ppmk
0x1802dafcd  lea     r8, [rsp+120h+pchEaten]; pchEaten
0x1802dafd2  mov     rdx, [rsp+120h+szUserName]; szUserName
0x1802dafda  mov     rcx, [rsp+120h+ppbc]; pbc
0x1802dafdf  call    cs:__imp_MkParseDisplayName
0x1802dafe5  mov     [rsp+120h+var_F0], eax
0x1802dafe9  mov     rcx, [rsp+120h+szUserName]; bstrString
0x1802daff1  call    cs:__imp_SysFreeString
0x1802daff7  mov     rax, [rsp+120h+ppbc]
0x1802daffc  mov     rax, [rax]
0x1802dafff  mov     rcx, [rsp+120h+ppbc]
0x1802db004  call    qword ptr [rax+10h]
0x1802db007  cmp     [rsp+120h+var_F0], 0
0x1802db00c  jge     short loc_1802DB019
0x1802db00e  xor     edx, edx
0x1802db010  mov     ecx, [rsp+120h+var_F0]
0x1802db014  call    HresultCheck
0x1802db019  lea     r9, [rsp+120h+ppvResult]; ppvResult
0x1802db01e  lea     r8, IID_IUnknown; iidResult
0x1802db025  xor     edx, edx; grfOpt
0x1802db027  mov     rcx, [rsp+120h+ppmk]; pmk
0x1802db02c  call    cs:__imp_BindMoniker
0x1802db032  mov     [rsp+120h+var_F0], eax
0x1802db036  mov     rax, [rsp+120h+ppmk]
0x1802db03b  mov     rax, [rax]
0x1802db03e  mov     rcx, [rsp+120h+ppmk]
0x1802db043  call    qword ptr [rax+10h]
0x1802db046  xor     edx, edx
0x1802db048  mov     ecx, [rsp+120h+var_F0]
0x1802db04c  call    HresultCheck
0x1802db051  cmp     [rsp+120h+ppvResult], 0
0x1802db057  jnz     short loc_1802DB063
0x1802db059  mov     ecx, 1ADh
0x1802db05e  call    EbRaiseExceptionCode
0x1802db063  jmp     loc_1802DB315
0x1802db068  mov     rcx, [rbp+arg_10]
0x1802db06c  call    __vbaStrVarCopy
0x1802db071  mov     [rsp+120h+String2], rax
0x1802db076  mov     rdx, [rsp+120h+String2]; String2
0x1802db07b  lea     rcx, aVbscriptRegexp; "vbscript.regexp"
0x1802db082  call    cs:__imp__wcsicmp
0x1802db088  test    eax, eax
0x1802db08a  jnz     short loc_1802DB0BC
0x1802db08c  mov     rcx, [rsp+120h+String2]; bstrString
0x1802db091  call    cs:__imp_SysFreeString
0x1802db097  lea     rcx, [rsp+120h+ppvResult]; struct IUnknown **
0x1802db09c  call    ?Create@CRegExp@@SAJPEAPEAUIUnknown@@@Z; CRegExp::Create(IUnknown * *)
0x1802db0a1  test    eax, eax
0x1802db0a3  jl      short loc_1802DB0AD
0x1802db0a5  cmp     [rsp+120h+ppvResult], 0
0x1802db0ab  jnz     short loc_1802DB0B7
0x1802db0ad  mov     ecx, 1ADh
0x1802db0b2  call    EbRaiseExceptionCode
0x1802db0b7  jmp     loc_1802DB315
0x1802db0bc  lea     rdx, [rbp+rclsid]
0x1802db0c0  mov     rcx, [rsp+120h+String2]
0x1802db0c5  call    cs:?g_pfnCLSIDFromProgidEx@@3P6AJPEB_WPEAU_GUID@@@ZEA; long (*g_pfnCLSIDFromProgidEx)(wchar_t const *,_GUID *)
0x1802db0cb  mov     [rsp+120h+var_F0], eax
0x1802db0cf  mov     rcx, [rsp+120h+String2]; bstrString
0x1802db0d4  call    cs:__imp_SysFreeString
0x1802db0da  cmp     [rsp+120h+var_F0], 0
0x1802db0df  jge     short loc_1802DB0EC
0x1802db0e1  xor     edx, edx
0x1802db0e3  mov     ecx, [rsp+120h+var_F0]
0x1802db0e7  call    HresultCheck
0x1802db0ec  mov     rcx, [rbp+arg_8]
0x1802db0f0  call    rtIsMissing
0x1802db0f5  cwde
0x1802db0f6  test    eax, eax
0x1802db0f8  jz      short loc_1802DB138
0x1802db0fa  lea     r8, [rsp+120h+ppvResult]; ppunk
0x1802db0ff  xor     edx, edx; pvReserved
0x1802db101  lea     rcx, [rbp+rclsid]; rclsid
0x1802db105  call    cs:__imp_GetActiveObject
0x1802db10b  mov     [rsp+120h+var_F0], eax
0x1802db10f  cmp     [rsp+120h+var_F0], 0
0x1802db114  jge     short loc_1802DB121
0x1802db116  xor     edx, edx
0x1802db118  mov     ecx, [rsp+120h+var_F0]
0x1802db11c  call    HresultCheck
0x1802db121  cmp     [rsp+120h+ppvResult], 0
0x1802db127  jnz     short loc_1802DB133
0x1802db129  mov     ecx, 1ADh
0x1802db12e  call    EbRaiseExceptionCode
0x1802db133  jmp     loc_1802DB2FE
0x1802db138  mov     [rsp+120h+var_E0], 0
0x1802db141  lea     rax, [rsp+120h+ppvResult]
0x1802db146  mov     [rsp+120h+ppv], rax; ppv
0x1802db14b  lea     r9, IID_IUnknown; riid
0x1802db152  mov     r8d, 15h; dwClsContext
0x1802db158  xor     edx, edx; pUnkOuter
0x1802db15a  lea     rcx, [rbp+rclsid]; rclsid
0x1802db15e  call    cs:__imp_CoCreateInstance
0x1802db164  mov     [rsp+120h+var_F0], eax
0x1802db168  cmp     [rsp+120h+var_F0], 0
0x1802db16d  jge     short loc_1802DB17A
0x1802db16f  xor     edx, edx
0x1802db171  mov     ecx, [rsp+120h+var_F0]
0x1802db175  call    HresultCheck
0x1802db17a  cmp     [rsp+120h+ppvResult], 0
0x1802db180  jnz     short loc_1802DB18C
0x1802db182  mov     ecx, 1ADh
0x1802db187  call    EbRaiseExceptionCode
0x1802db18c  mov     rcx, [rbp+arg_8]
0x1802db190  call    __vbaStrVarCopy
0x1802db195  mov     [rsp+120h+bstrString], rax
0x1802db19a  mov     rcx, [rsp+120h+bstrString]
0x1802db19f  call    BstrLen
0x1802db1a4  test    eax, eax
0x1802db1a6  jbe     short loc_1802DB21D
0x1802db1a8  mov     rax, [rsp+120h+ppvResult]
0x1802db1ad  mov     rax, [rax]
0x1802db1b0  lea     r8, [rsp+120h+var_E0]
0x1802db1b5  lea     rdx, IID_IPersistFile
0x1802db1bc  mov     rcx, [rsp+120h+ppvResult]
0x1802db1c1  call    qword ptr [rax]
0x1802db1c3  test    eax, eax
0x1802db1c5  jge     short loc_1802DB1D7
0x1802db1c7  mov     ecx, 1B0h
0x1802db1cc  call    HresultOfEberr
0x1802db1d1  mov     [rsp+120h+var_F0], eax
0x1802db1d5  jmp     short loc_1802DB218
0x1802db1d7  mov     rax, [rsp+120h+var_E0]
0x1802db1dc  mov     rax, [rax]
0x1802db1df  xor     r8d, r8d
0x1802db1e2  mov     rdx, [rsp+120h+bstrString]
0x1802db1e7  mov     rcx, [rsp+120h+var_E0]
0x1802db1ec  call    qword ptr [rax+28h]
0x1802db1ef  mov     [rsp+120h+var_F0], eax
0x1802db1f3  mov     rax, [rsp+120h+var_E0]
0x1802db1f8  mov     rax, [rax]
0x1802db1fb  mov     rcx, [rsp+120h+var_E0]
0x1802db200  call    qword ptr [rax+10h]
0x1802db203  cmp     [rsp+120h+var_F0], 1
0x1802db208  jnz     short loc_1802DB218
0x1802db20a  mov     ecx, 1ADh
0x1802db20f  call    HresultOfEberr
0x1802db214  mov     [rsp+120h+var_F0], eax
0x1802db218  jmp     loc_1802DB2A5
0x1802db21d  mov     rax, [rsp+120h+ppvResult]
0x1802db222  mov     rax, [rax]
0x1802db225  lea     r8, [rsp+120h+var_D8]
0x1802db22a  lea     rdx, IID_IPersistStreamInit
0x1802db231  mov     rcx, [rsp+120h+ppvResult]
0x1802db236  call    qword ptr [rax]
0x1802db238  test    eax, eax
0x1802db23a  jl      short loc_1802DB262
0x1802db23c  mov     rax, [rsp+120h+var_D8]
0x1802db241  mov     rax, [rax]
0x1802db244  mov     rcx, [rsp+120h+var_D8]
0x1802db249  call    qword ptr [rax+40h]
0x1802db24c  mov     [rsp+120h+var_F0], eax
0x1802db250  mov     rax, [rsp+120h+var_D8]
0x1802db255  mov     rax, [rax]
0x1802db258  mov     rcx, [rsp+120h+var_D8]
0x1802db25d  call    qword ptr [rax+10h]
0x1802db260  jmp     short loc_1802DB2A5
0x1802db262  mov     rax, [rsp+120h+ppvResult]
0x1802db267  mov     rax, [rax]
0x1802db26a  lea     r8, [rsp+120h+var_C8]
0x1802db26f  lea     rdx, IID_IPersistPropertyBag
0x1802db276  mov     rcx, [rsp+120h+ppvResult]
0x1802db27b  call    qword ptr [rax]
0x1802db27d  test    eax, eax
0x1802db27f  jl      short loc_1802DB2A5
0x1802db281  mov     rax, [rsp+120h+var_C8]
0x1802db286  mov     rax, [rax]
0x1802db289  mov     rcx, [rsp+120h+var_C8]
0x1802db28e  call    qword ptr [rax+20h]
0x1802db291  mov     [rsp+120h+var_F0], eax
0x1802db295  mov     rax, [rsp+120h+var_C8]
0x1802db29a  mov     rax, [rax]
0x1802db29d  mov     rcx, [rsp+120h+var_C8]
0x1802db2a2  call    qword ptr [rax+10h]
0x1802db2a5  mov     rcx, [rsp+120h+bstrString]; bstrString
0x1802db2aa  call    cs:__imp_SysFreeString
0x1802db2b0  cmp     [rsp+120h+var_F0], 0
0x1802db2b5  jge     short loc_1802DB2FE
0x1802db2b7  mov     rax, [rsp+120h+ppvResult]
0x1802db2bc  mov     rax, [rax]
0x1802db2bf  mov     rcx, [rsp+120h+ppvResult]
0x1802db2c4  call    qword ptr [rax+10h]
0x1802db2c7  mov     [rsp+120h+ppvResult], 0
0x1802db2d0  lea     rcx, [rbp+var_70]; struct tagEXCEPINFO *
0x1802db2d4  call    ?GetErrorInfo@@YAJPEAUtagEXCEPINFO@@@Z; GetErrorInfo(tagEXCEPINFO *)
0x1802db2d9  test    eax, eax
0x1802db2db  jnz     short loc_1802DB2F3
0x1802db2dd  mov     eax, [rsp+120h+var_F0]
0x1802db2e1  mov     [rbp+var_70.scode], eax
0x1802db2e4  xor     eax, eax
0x1802db2e6  mov     [rbp+var_70.wCode], ax
0x1802db2ea  lea     rcx, [rbp+var_70]
0x1802db2ee  call    EbRaiseException
0x1802db2f3  xor     edx, edx
0x1802db2f5  mov     ecx, [rsp+120h+var_F0]
0x1802db2f9  call    HresultCheck
0x1802db2fe  mov     ecx, 2
0x1802db303  call    ?IsCapabilityEnabled@@YAHW4_VBACAPABILITYTYPE@@@Z; IsCapabilityEnabled(_VBACAPABILITYTYPE)
0x1802db308  test    eax, eax
0x1802db30a  jz      short loc_1802DB315
0x1802db30c  lea     rcx, [rbp+rclsid]; struct _GUID *
0x1802db310  call    ?OnComObjectInstantiated@TELMGR@@SAXAEBU_GUID@@@Z; TELMGR::OnComObjectInstantiated(_GUID const &)
0x1802db315  mov     rax, [rsp+120h+ppvResult]
0x1802db31a  mov     rax, [rax]
0x1802db31d  lea     r8, [rsp+120h+var_98]
0x1802db325  lea     rdx, IID_IDispatch
0x1802db32c  mov     rcx, [rsp+120h+ppvResult]
0x1802db331  call    qword ptr [rax]
0x1802db333  test    eax, eax
0x1802db335  jge     short loc_1802DB353
0x1802db337  mov     eax, 0Dh
0x1802db33c  mov     [rsp+120h+var_90], ax
0x1802db344  mov     rax, [rsp+120h+ppvResult]
0x1802db349  mov     [rsp+120h+var_88], rax
0x1802db351  jmp     short loc_1802DB380
0x1802db353  mov     rax, [rsp+120h+ppvResult]
0x1802db358  mov     rax, [rax]
0x1802db35b  mov     rcx, [rsp+120h+ppvResult]
0x1802db360  call    qword ptr [rax+10h]
0x1802db363  mov     eax, 9
0x1802db368  mov     [rsp+120h+var_90], ax
0x1802db370  mov     rax, [rsp+120h+var_98]
0x1802db378  mov     [rsp+120h+var_88], rax
0x1802db380  lea     rax, [rsp+120h+var_90]
0x1802db388  mov     rdi, [rbp+arg_0]
0x1802db38c  mov     rsi, rax
0x1802db38f  mov     ecx, 18h
0x1802db394  rep movsb
0x1802db396  mov     rax, [rbp+arg_0]
0x1802db39a  mov     rcx, [rbp+var_20]
0x1802db39e  xor     rcx, rsp; StackCookie
0x1802db3a1  call    __security_check_cookie
0x1802db3a6  add     rsp, 110h
0x1802db3ad  pop     rdi
0x1802db3ae  pop     rsi
0x1802db3af  pop     rbp
0x1802db3b0  retn
```
