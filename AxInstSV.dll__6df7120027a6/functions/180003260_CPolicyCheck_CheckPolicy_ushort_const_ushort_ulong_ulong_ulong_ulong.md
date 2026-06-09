# CPolicyCheck::CheckPolicy(ushort const *,ushort * *,ulong *,ulong *,ulong *,ulong *)

- ea: `0x180003260`
- end: `0x18000378b`
- name: `?CheckPolicy@CPolicyCheck@@QEAAJPEBGPEAPEAGPEAK222@Z`
- size: `1323`
- prototype: `__int64 __fastcall(CPolicyCheck *this, const unsigned __int16 *, unsigned __int16 **, unsigned int *, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180005ee0`

## callees

- `0x180002af0`
- `0x180002c00`
- `0x180003208`
- `0x180003260`
- `0x1800038dc`
- `0x18000725c`
- `0x180015010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800034dc`
- `OLEAUT32!__imp_SysFreeString` at `0x180003764`
- `OLEAUT32!__imp_SysFreeString` at `0x180003770`
- `OLEAUT32!__imp_SysFreeString` at `0x1800034dc`
- `OLEAUT32!__imp_SysFreeString` at `0x180003764`
- `OLEAUT32!__imp_SysFreeString` at `0x180003770`
- `OLEAUT32!__imp_SysStringLen` at `0x180003477`
- `OLEAUT32!__imp_SysStringLen` at `0x1800034b1`
- `OLEAUT32!__imp_SysStringLen` at `0x180003477`
- `OLEAUT32!__imp_SysStringLen` at `0x1800034b1`
- `OLEAUT32!__imp_VarBstrCat` at `0x1800034cd`
- `OLEAUT32!__imp_VarBstrCat` at `0x1800034cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003758`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003758`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003603`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003603`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800035a2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800035a2`
- `ntdll!RtlReleaseResource` at `0x1800033b9`
- `ntdll!RtlReleaseResource` at `0x1800033ec`
- `ntdll!RtlReleaseResource` at `0x1800033b9`
- `ntdll!RtlReleaseResource` at `0x1800033ec`
- `ntdll!RtlAcquireResourceShared` at `0x1800032f9`
- `ntdll!RtlAcquireResourceShared` at `0x1800032f9`
- `urlmon!CreateUri` at `0x180003408`
- `urlmon!CreateUri` at `0x180003408`

## string_xrefs

- `0x180003399`: `CheckPolicy failed,during Getpolicy Error code  0x%x`
- `0x1800035b0`: `Failed to open Internet Explorer GroupPolicy Registry Key. MapURLToZone will not be called for URL %s RegOpenKeyEx returned 0x%x`
- `0x1800035f7`: `Security_HKLM_only`
- `0x18000372b`: `MapURLToZone not called for URL %s as Security_HKLM_only is not enabled. ReQueryValueEx returned 0x%x, Type is 0x%x and Value is 0x%x `

## pseudocode

```c
__int64 __fastcall CPolicyCheck::CheckPolicy(
        CPolicyCheck *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned int *a6,
        unsigned int *a7)
{
  unsigned __int16 **v7; // r13
  const unsigned __int16 *v8; // r14
  CPolicyCheck *v9; // rsi
  struct _RTL_RESOURCE *v10; // r12
  int PolicyEntry; // edi
  IUri *v12; // r15
  HRESULT v13; // eax
  const wchar_t *v14; // rdx
  OLECHAR *v15; // r15
  HRESULT v16; // eax
  unsigned __int16 *v17; // rax
  LSTATUS v18; // eax
  LSTATUS Value; // edx
  __int64 v20; // rcx
  int v21; // eax
  int v22; // edx
  PHKEY phkResult; // [rsp+20h] [rbp-B8h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-B0h]
  BYTE Data[4]; // [rsp+40h] [rbp-98h] BYREF
  IUri *ppURI; // [rsp+48h] [rbp-90h] BYREF
  int v28; // [rsp+50h] [rbp-88h] BYREF
  BSTR bstrLeft; // [rsp+58h] [rbp-80h] BYREF
  int v30; // [rsp+60h] [rbp-78h]
  int v31; // [rsp+64h] [rbp-74h] BYREF
  BSTR pbstr; // [rsp+68h] [rbp-70h] BYREF
  PRTL_RESOURCE Resource; // [rsp+70h] [rbp-68h] BYREF
  HKEY hKey[2]; // [rsp+78h] [rbp-60h] BYREF
  ATL::CAtlException *v35; // [rsp+88h] [rbp-50h] BYREF
  ATL::CAtlException *v36; // [rsp+90h] [rbp-48h] BYREF
  ATL::CAtlException *v37; // [rsp+98h] [rbp-40h] BYREF
  const unsigned __int16 *Type; // [rsp+E8h] [rbp+10h] BYREF
  unsigned __int16 **v40; // [rsp+F0h] [rbp+18h]
  unsigned int *v41; // [rsp+F8h] [rbp+20h]

  v41 = a4;
  v40 = a3;
  Type = a2;
  v7 = a3;
  v8 = a2;
  v9 = this;
  ppURI = 0;
  v28 = 0;
  v31 = 4;
  hKey[0] = 0;
  pbstr = 0;
  bstrLeft = 0;
  if ( !a2 || !*a2 )
  {
    PolicyEntry = -2147024809;
    goto LABEL_48;
  }
  v30 = 0;
  *a4 = 0;
  *a5 = 0;
  *a6 = 0;
  *a7 = 0;
  *a3 = 0;
  v10 = (struct _RTL_RESOURCE *)((char *)this + 16);
  Resource = (PRTL_RESOURCE)((char *)this + 16);
  hKey[1] = (HKEY)((char *)this + 16);
  RtlAcquireResourceShared((PRTL_RESOURCE)((char *)this + 16), 1u);
  PolicyEntry = CPolicyCheck::FindPolicyEntry(v9, v8, (struct CPolicyEntry **)&ppURI);
  *(_DWORD *)Data = PolicyEntry;
  if ( PolicyEntry >= 0 )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v12 = ppURI;
      *a5 = HIDWORD(ppURI[3].lpVtbl);
      *a6 = (unsigned int)v12[5].lpVtbl;
      *v41 = (unsigned int)v12[4].lpVtbl;
      *a7 = HIDWORD(v12[4].lpVtbl);
      (*((void (__fastcall **)(struct IUriVtbl *, BSTR *))v12[2].lpVtbl->QueryInterface + 13))(v12[2].lpVtbl, &pbstr);
      (*((void (__fastcall **)(struct IUriVtbl *, int *))v12[2].lpVtbl->QueryInterface + 24))(v12[2].lpVtbl, &v28);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v35) )
      {
        *(_DWORD *)Data = *(_DWORD *)v35;
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000338B);
        PolicyEntry = *(_DWORD *)Data;
        if ( *(int *)Data < 0 )
        {
          AxISEvents::DebugMsg(
            (AxISEvents *)&qword_180021AD8,
            1u,
            2u,
            L"CheckPolicy failed,during Getpolicy Error code  0x%x",
            *(_DWORD *)Data);
          RtlReleaseResource(Resource);
          goto LABEL_48;
        }
        v9 = this;
        v7 = v40;
        v8 = Type;
        v10 = Resource;
      }
    }
    v30 = 1;
  }
  RtlReleaseResource(v10);
  if ( PolicyEntry < 0 )
  {
    ppURI = 0;
    v13 = CreateUri(v8, 0, 0, &ppURI);
    if ( __eh34_try(-1, 2) )
    {
      __eh34_scope_strut(2);
      if ( v13 >= 0 && ppURI )
      {
        ((void (__fastcall *)(IUri *, BSTR *))ppURI->lpVtbl->GetHost)(ppURI, &pbstr);
        ((void (__fastcall *)(IUri *, int *))ppURI->lpVtbl->GetScheme)(ppURI, &v28);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppURI);
    }
    if ( __eh34_catch(2) )
    {
      if ( __eh34_catch_type(2, &ATL::CAtlException `RTTI Type Descriptor', &v37) )
      {
        v9 = this;
        v7 = v40;
        v8 = Type;
        PolicyEntry = *(_DWORD *)Data;
        __eh34_try_continuation(2, &ATL::CAtlException `RTTI Type Descriptor', &loc_180003454);
      }
    }
  }
  if ( __eh34_try(-1, 4) )
  {
    __eh34_scope_strut(4);
    if ( SysStringLen(pbstr) )
    {
      if ( v28 == 2 )
      {
        v14 = L"http://";
        goto LABEL_20;
      }
      if ( v28 == 11 )
      {
        v14 = L"https://";
LABEL_20:
        ATL::CComBSTR::operator=(&bstrLeft, v14);
        v15 = pbstr;
        if ( SysStringLen(pbstr) )
        {
          Resource = 0;
          v16 = VarBstrCat(bstrLeft, v15, (LPBSTR)&Resource);
          if ( v16 < 0 )
            ATL::AtlThrowImpl(v16);
          SysFreeString(bstrLeft);
          v17 = (unsigned __int16 *)Resource;
        }
        else
        {
          v17 = bstrLeft;
        }
        bstrLeft = 0;
        *v7 = v17;
      }
    }
  }
  if ( __eh34_catch(4) )
  {
    if ( __eh34_catch_type(4, &ATL::CAtlException `RTTI Type Descriptor', &v36) )
    {
      LODWORD(ppURI) = *(_DWORD *)v36;
      __eh34_try_continuation(4, &ATL::CAtlException `RTTI Type Descriptor', &loc_180003500);
      PolicyEntry = (int)ppURI;
      if ( (int)ppURI < 0 )
      {
        AxISEvents::DebugMsg(
          (AxISEvents *)&qword_180021AD8,
          1u,
          2u,
          L"CheckPolicy failed, Out of memory Error code  0x%x",
          (_DWORD)ppURI);
        goto LABEL_48;
      }
      v9 = this;
      v8 = Type;
      PolicyEntry = *(_DWORD *)Data;
    }
  }
  if ( !v30 && (*((_DWORD *)v9 + 35) || *((_DWORD *)v9 + 36) || *((_DWORD *)v9 + 38)) )
  {
    PolicyEntry = -2146762485;
    *(_DWORD *)Data = 0;
    LODWORD(Type) = 0;
    LODWORD(ppURI) = 4;
    v18 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Policies\\Microsoft\\Windows\\CurrentVersion\\Internet Settings",
            0,
            0x20019u,
            hKey);
    if ( v18 )
    {
      AxISEvents::DebugMsg(
        (AxISEvents *)&qword_180021AD8,
        1u,
        4u,
        L"Failed to open Internet Explorer GroupPolicy Registry Key. MapURLToZone will not be called for URL %s RegOpenKey"
         "Ex returned 0x%x",
        v8,
        v18);
    }
    else
    {
      Value = RegQueryValueExW(hKey[0], L"Security_HKLM_only", 0, (LPDWORD)&Type, Data, (LPDWORD)&ppURI);
      if ( !Value && (_DWORD)Type == 4 && *(_DWORD *)Data == 1 )
      {
        v20 = *((_QWORD *)v9 + 21);
        if ( v20 )
        {
          v21 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, int *, _QWORD))(*(_QWORD *)v20 + 40LL))(
                  v20,
                  v8,
                  &v31,
                  0);
          if ( v21 < 0 )
          {
            LODWORD(phkResult) = v21;
            AxISEvents::DebugMsg(
              (AxISEvents *)&qword_180021AD8,
              1u,
              3u,
              L"MapUrlToZone failed with HRESULT 0x%x",
              phkResult);
          }
          else
          {
            v22 = *((_DWORD *)v9 + 37);
            if ( v22 == v31 )
            {
              PolicyEntry = 0;
              *v41 = *((_DWORD *)v9 + 35);
              *a5 = *((_DWORD *)v9 + 36);
              *a6 = *((_DWORD *)v9 + 38);
              *a7 = *((_DWORD *)v9 + 39);
              if ( v22 == 2 )
              {
                AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 1u, 4u, L"URL %s is in trusted zones.", v8);
              }
              else
              {
                LODWORD(lpcbData) = v22;
                AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 1u, 4u, L"URL %s is in %d zones.", v8, lpcbData);
              }
            }
          }
        }
        else
        {
          AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 1u, 2u, L"Internal Error: spIntSecMgr is NULL");
        }
      }
      else
      {
        LODWORD(lpcbData) = Value;
        AxISEvents::DebugMsg(
          (AxISEvents *)&qword_180021AD8,
          1u,
          4u,
          L"MapURLToZone not called for URL %s as Security_HKLM_only is not enabled. ReQueryValueEx returned 0x%x, Type is"
           " 0x%x and Value is 0x%x ",
          v8,
          lpcbData,
          (_DWORD)Type,
          *(_DWORD *)Data);
      }
    }
  }
LABEL_48:
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  SysFreeString(bstrLeft);
  SysFreeString(pbstr);
  return (unsigned int)PolicyEntry;
}

```

## disassembly

```asm
0x180003260  mov     r11, rsp
0x180003263  mov     [r11+20h], r9
0x180003267  mov     [r11+18h], r8
0x18000326b  mov     [r11+10h], rdx
0x18000326f  mov     [r11+8], rcx
0x180003273  push    rbx
0x180003274  push    rsi
0x180003275  push    rdi
0x180003276  push    r12
0x180003278  push    r13
0x18000327a  push    r14
0x18000327c  push    r15
0x18000327e  sub     rsp, 0A0h
0x180003285  mov     r13, r8
0x180003288  mov     r14, rdx
0x18000328b  mov     rsi, rcx
0x18000328e  xor     ebx, ebx
0x180003290  mov     [rsp+0D8h+ppURI], rbx
0x180003295  mov     [rsp+0D8h+var_88], ebx
0x180003299  mov     [rsp+0D8h+var_74], 4
0x1800032a1  mov     [r11-60h], rbx
0x1800032a5  mov     [r11-70h], rbx
0x1800032a9  mov     [r11-80h], rbx
0x1800032ad  test    rdx, rdx
0x1800032b0  jz      loc_180003749
0x1800032b6  cmp     bx, [rdx]
0x1800032b9  jz      loc_180003749
0x1800032bf  mov     [rsp+0D8h+var_78], ebx
0x1800032c3  mov     [r9], ebx
0x1800032c6  mov     rax, [rsp+0D8h+arg_20]
0x1800032ce  mov     [rax], ebx
0x1800032d0  mov     rax, [rsp+0D8h+arg_28]
0x1800032d8  mov     [rax], ebx
0x1800032da  mov     rax, [rsp+0D8h+arg_30]
0x1800032e2  mov     [rax], ebx
0x1800032e4  mov     [r8], rbx
0x1800032e7  lea     r12, [rcx+10h]
0x1800032eb  mov     [rsp+0D8h+Resource], r12
0x1800032f0  mov     [r11-58h], r12
0x1800032f4  mov     dl, 1; Wait
0x1800032f6  mov     rcx, r12; Resource
0x1800032f9  call    cs:__imp_RtlAcquireResourceShared
0x1800032ff  nop
0x180003300  lea     r8, [rsp+0D8h+ppURI]; struct CPolicyEntry **
0x180003305  mov     rdx, r14; unsigned __int16 *
0x180003308  mov     rcx, rsi; this
0x18000330b  call    ?FindPolicyEntry@CPolicyCheck@@QEAAJPEBGPEAPEAVCPolicyEntry@@@Z; CPolicyCheck::FindPolicyEntry(ushort const *,CPolicyEntry * *)
0x180003310  mov     edi, eax
0x180003312  mov     dword ptr [rsp+0D8h+Data], eax
0x180003316  test    eax, eax
0x180003318  js      loc_1800033E9
0x18000331e  mov     r15, [rsp+0D8h+ppURI]
0x180003323  mov     ecx, [r15+1Ch]
0x180003327  mov     rax, [rsp+0D8h+arg_20]
0x18000332f  mov     [rax], ecx
0x180003331  mov     ecx, [r15+28h]
0x180003335  mov     rax, [rsp+0D8h+arg_28]
0x18000333d  mov     [rax], ecx
0x18000333f  mov     ecx, [r15+20h]
0x180003343  mov     rax, [rsp+0D8h+arg_18]
0x18000334b  mov     [rax], ecx
0x18000334d  mov     ecx, [r15+24h]
0x180003351  mov     rax, [rsp+0D8h+arg_30]
0x180003359  mov     [rax], ecx
0x18000335b  mov     rcx, [r15+10h]
0x18000335f  mov     rax, [rcx]
0x180003362  lea     rdx, [rsp+0D8h+pbstr]
0x180003367  mov     rax, [rax+68h]
0x18000336b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003370  mov     rcx, [r15+10h]
0x180003374  mov     rax, [rcx]
0x180003377  lea     rdx, [rsp+0D8h+var_88]
0x18000337c  mov     rax, [rax+0C0h]
0x180003383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003388  nop
0x180003389  jmp     short loc_1800033E1
0x18000338b  mov     edi, dword ptr [rsp+0D8h+Data]
0x18000338f  xor     ebx, ebx
0x180003391  test    edi, edi
0x180003393  jns     short loc_1800033C4
0x180003395  mov     dword ptr [rsp+0D8h+phkResult], edi
0x180003399  lea     r9, aCheckpolicyFai; "CheckPolicy failed,during Getpolicy Err"...
0x1800033a0  lea     edx, [rbx+1]; unsigned int
0x1800033a3  lea     r8d, [rbx+2]; unsigned __int8
0x1800033a7  lea     rcx, qword_180021AD8; this
0x1800033ae  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x1800033b3  nop
0x1800033b4  mov     rcx, [rsp+0D8h+Resource]; Resource
0x1800033b9  call    cs:__imp_RtlReleaseResource
0x1800033bf  jmp     loc_18000374E
0x1800033c4  mov     rsi, [rsp+0D8h+arg_0]
0x1800033cc  mov     r13, [rsp+0D8h+arg_10]
0x1800033d4  mov     r14, [rsp+0D8h+Type]
0x1800033dc  mov     r12, [rsp+0D8h+Resource]
0x1800033e1  mov     [rsp+0D8h+var_78], 1
0x1800033e9  mov     rcx, r12; Resource
0x1800033ec  call    cs:__imp_RtlReleaseResource
0x1800033f2  test    edi, edi
0x1800033f4  jns     short loc_180003472
0x1800033f6  mov     [rsp+0D8h+ppURI], rbx
0x1800033fb  lea     r9, [rsp+0D8h+ppURI]; ppURI
0x180003400  xor     r8d, r8d; dwReserved
0x180003403  xor     edx, edx; dwFlags
0x180003405  mov     rcx, r14; pwzURI
0x180003408  call    cs:__imp_CreateUri
0x18000340e  test    eax, eax
0x180003410  js      short loc_180003447
0x180003412  mov     rcx, [rsp+0D8h+ppURI]
0x180003417  test    rcx, rcx
0x18000341a  jz      short loc_180003447
0x18000341c  mov     rax, [rcx]
0x18000341f  lea     rdx, [rsp+0D8h+pbstr]
0x180003424  mov     rax, [rax+68h]
0x180003428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000342d  mov     rcx, [rsp+0D8h+ppURI]
0x180003432  mov     rax, [rcx]
0x180003435  lea     rdx, [rsp+0D8h+var_88]
0x18000343a  mov     rax, [rax+0C0h]
0x180003441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003446  nop
0x180003447  lea     rcx, [rsp+0D8h+ppURI]
0x18000344c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180003451  nop
0x180003452  jmp     short loc_180003472
0x180003454  xor     ebx, ebx
0x180003456  mov     rsi, [rsp+0D8h+arg_0]
0x18000345e  mov     r13, [rsp+0D8h+arg_10]
0x180003466  mov     r14, [rsp+0D8h+Type]
0x18000346e  mov     edi, dword ptr [rsp+0D8h+Data]
0x180003472  mov     rcx, [rsp+0D8h+pbstr]; pbstr
0x180003477  call    cs:__imp_SysStringLen
0x18000347d  test    eax, eax
0x18000347f  jz      short loc_1800034FE
0x180003481  cmp     [rsp+0D8h+var_88], 2
0x180003486  jz      short loc_180003498
0x180003488  cmp     [rsp+0D8h+var_88], 0Bh
0x18000348d  jnz     short loc_1800034FE
0x18000348f  lea     rdx, aHttps; "https://"
0x180003496  jmp     short loc_18000349F
0x180003498  lea     rdx, aHttp; "http://"
0x18000349f  lea     rcx, [rsp+0D8h+bstrLeft]
0x1800034a4  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x1800034a9  mov     r15, [rsp+0D8h+pbstr]
0x1800034ae  mov     rcx, r15; pbstr
0x1800034b1  call    cs:__imp_SysStringLen
0x1800034b7  test    eax, eax
0x1800034b9  jz      short loc_1800034F0
0x1800034bb  mov     [rsp+0D8h+Resource], rbx
0x1800034c0  lea     r8, [rsp+0D8h+Resource]; pbstrResult
0x1800034c5  mov     rdx, r15; bstrRight
0x1800034c8  mov     rcx, [rsp+0D8h+bstrLeft]; bstrLeft
0x1800034cd  call    cs:__imp_VarBstrCat
0x1800034d3  test    eax, eax
0x1800034d5  js      short loc_1800034E9
0x1800034d7  mov     rcx, [rsp+0D8h+bstrLeft]; bstrString
0x1800034dc  call    cs:__imp_SysFreeString
0x1800034e2  mov     rax, [rsp+0D8h+Resource]
0x1800034e7  jmp     short loc_1800034F5
0x1800034e9  mov     ecx, eax; int
0x1800034eb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800034f0  mov     rax, [rsp+0D8h+bstrLeft]
0x1800034f5  mov     [rsp+0D8h+bstrLeft], rbx
0x1800034fa  mov     [r13+0], rax
0x1800034fe  jmp     short loc_180003543
0x180003500  mov     edi, dword ptr [rsp+0D8h+ppURI]
0x180003504  xor     ebx, ebx
0x180003506  test    edi, edi
0x180003508  jns     short loc_18000352F
0x18000350a  mov     dword ptr [rsp+0D8h+phkResult], edi
0x18000350e  lea     r9, aCheckpolicyFai_0; "CheckPolicy failed, Out of memory Error"...
0x180003515  lea     r8d, [rbx+2]; unsigned __int8
0x180003519  lea     rcx, qword_180021AD8; this
0x180003520  mov     edx, 1; unsigned int
0x180003525  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x18000352a  jmp     loc_18000374E
0x18000352f  mov     rsi, [rsp+0D8h+arg_0]
0x180003537  mov     r14, [rsp+0D8h+Type]
0x18000353f  mov     edi, dword ptr [rsp+0D8h+Data]
0x180003543  cmp     [rsp+0D8h+var_78], ebx
0x180003547  jnz     loc_18000374E
0x18000354d  cmp     [rsi+8Ch], ebx
0x180003553  jnz     short loc_180003569
0x180003555  cmp     [rsi+90h], ebx
0x18000355b  jnz     short loc_180003569
0x18000355d  cmp     [rsi+98h], ebx
0x180003563  jz      loc_18000374E
0x180003569  mov     edi, 800B010Bh
0x18000356e  mov     dword ptr [rsp+0D8h+Data], ebx
0x180003572  mov     dword ptr [rsp+0D8h+Type], ebx
0x180003579  mov     dword ptr [rsp+0D8h+ppURI], 4
0x180003581  lea     rax, [rsp+0D8h+hKey]
0x180003586  mov     [rsp+0D8h+phkResult], rax; phkResult
0x18000358b  mov     r9d, 20019h; samDesired
0x180003591  xor     r8d, r8d; ulOptions
0x180003594  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Windows"...
0x18000359b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800035a2  call    cs:__imp_RegOpenKeyExW
0x1800035a8  test    eax, eax
0x1800035aa  jz      short loc_1800035D8
0x1800035ac  mov     dword ptr [rsp+0D8h+lpcbData], eax
0x1800035b0  lea     r9, aFailedToOpenIn; "Failed to open Internet Explorer GroupP"...
0x1800035b7  mov     r8d, 4; unsigned __int8
0x1800035bd  lea     rcx, qword_180021AD8; this
0x1800035c4  mov     edx, 1; unsigned int
0x1800035c9  mov     [rsp+0D8h+phkResult], r14
0x1800035ce  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x1800035d3  jmp     loc_18000374E
0x1800035d8  lea     rax, [rsp+0D8h+ppURI]
0x1800035dd  mov     [rsp+0D8h+lpcbData], rax; lpcbData
0x1800035e2  lea     rax, [rsp+0D8h+Data]
0x1800035e7  mov     [rsp+0D8h+phkResult], rax; lpData
0x1800035ec  lea     r9, [rsp+0D8h+Type]; lpType
0x1800035f4  xor     r8d, r8d; lpReserved
0x1800035f7  lea     rdx, aSecurityHklmOn; "Security_HKLM_only"
0x1800035fe  mov     rcx, [rsp+0D8h+hKey]; hKey
0x180003603  call    cs:__imp_RegQueryValueExW
0x180003609  mov     edx, eax
0x18000360b  mov     ecx, dword ptr [rsp+0D8h+Type]
0x180003612  test    eax, eax
0x180003614  jnz     loc_180003716
0x18000361a  cmp     ecx, 4
0x18000361d  jnz     loc_180003716
0x180003623  cmp     dword ptr [rsp+0D8h+Data], 1
0x180003628  jnz     loc_180003716
0x18000362e  mov     rcx, [rsi+0A8h]
0x180003635  test    rcx, rcx
0x180003638  jz      loc_1800036F8
0x18000363e  mov     rax, [rcx]
0x180003641  xor     r9d, r9d
0x180003644  lea     r8, [rsp+0D8h+var_74]
0x180003649  mov     rdx, r14
0x18000364c  mov     rax, [rax+28h]
0x180003650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003655  test    eax, eax
0x180003657  js      loc_1800036E2
0x18000365d  mov     edx, [rsi+94h]
0x180003663  cmp     edx, [rsp+0D8h+var_74]
0x180003667  jnz     loc_18000374E
0x18000366d  mov     edi, ebx
0x18000366f  mov     eax, [rsi+8Ch]
0x180003675  mov     rcx, [rsp+0D8h+arg_18]
0x18000367d  mov     [rcx], eax
0x18000367f  mov     ecx, [rsi+90h]
0x180003685  mov     rax, [rsp+0D8h+arg_20]
0x18000368d  mov     [rax], ecx
0x18000368f  mov     ecx, [rsi+98h]
0x180003695  mov     rax, [rsp+0D8h+arg_28]
0x18000369d  mov     [rax], ecx
0x18000369f  mov     ecx, [rsi+9Ch]
0x1800036a5  mov     rax, [rsp+0D8h+arg_30]
0x1800036ad  mov     [rax], ecx
0x1800036af  mov     r8d, 4
0x1800036b5  lea     rcx, qword_180021AD8
0x1800036bc  cmp     edx, 2
0x1800036bf  jnz     short loc_1800036D2
0x1800036c1  mov     [rsp+0D8h+phkResult], r14
0x1800036c6  lea     r9, aUrlSIsInTruste; "URL %s is in trusted zones."
0x1800036cd  jmp     loc_180003520
0x1800036d2  mov     dword ptr [rsp+0D8h+lpcbData], edx
0x1800036d6  lea     r9, aUrlSIsInDZones; "URL %s is in %d zones."
0x1800036dd  jmp     loc_1800035C4
0x1800036e2  mov     dword ptr [rsp+0D8h+phkResult], eax
0x1800036e6  lea     r9, aMapurltozoneFa; "MapUrlToZone failed with HRESULT 0x%x"
0x1800036ed  mov     r8d, 3
0x1800036f3  jmp     loc_180003519
0x1800036f8  lea     r9, aInternalErrorS; "Internal Error: spIntSecMgr is NULL"
0x1800036ff  mov     edx, 1; unsigned int
0x180003704  lea     r8d, [rdx+1]; unsigned __int8
0x180003708  lea     rcx, qword_180021AD8; this
0x18000370f  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x180003714  jmp     short loc_18000374E
0x180003716  mov     eax, dword ptr [rsp+0D8h+Data]
0x18000371a  mov     [rsp+0D8h+var_A0], eax
0x18000371e  mov     [rsp+0D8h+var_A8], ecx
0x180003722  mov     dword ptr [rsp+0D8h+lpcbData], edx
0x180003726  mov     [rsp+0D8h+phkResult], r14
0x18000372b  lea     r9, aMapurltozoneNo; "MapURLToZone not called for URL %s as S"...
0x180003732  mov     edx, 1; unsigned int
0x180003737  lea     r8d, [rdx+3]; unsigned __int8
0x18000373b  lea     rcx, qword_180021AD8; this
0x180003742  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x180003747  jmp     short loc_18000374E
0x180003749  mov     edi, 80070057h
0x18000374e  mov     rcx, [rsp+0D8h+hKey]; hKey
0x180003753  test    rcx, rcx
0x180003756  jz      short loc_18000375F
0x180003758  call    cs:__imp_RegCloseKey
0x18000375e  nop
0x18000375f  mov     rcx, [rsp+0D8h+bstrLeft]; bstrString
0x180003764  call    cs:__imp_SysFreeString
0x18000376a  nop
0x18000376b  mov     rcx, [rsp+0D8h+pbstr]; bstrString
0x180003770  call    cs:__imp_SysFreeString
0x180003776  mov     eax, edi
0x180003778  add     rsp, 0A0h
0x18000377f  pop     r15
0x180003781  pop     r14
0x180003783  pop     r13
0x180003785  pop     r12
0x180003787  pop     rdi
  ... truncated ...
```
