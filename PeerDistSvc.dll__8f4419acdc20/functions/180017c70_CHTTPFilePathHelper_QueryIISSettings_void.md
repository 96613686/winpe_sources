# CHTTPFilePathHelper::QueryIISSettings(void)

- ea: `0x180017c70`
- end: `0x180018049`
- name: `?QueryIISSettings@CHTTPFilePathHelper@@AEAAKXZ`
- size: `985`
- prototype: `unsigned int __fastcall(CHTTPFilePathHelper *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017544`

## callees

- `0x180008290`
- `0x180009ec4`
- `0x18000ecf4`
- `0x180015cec`
- `0x180015eec`
- `0x1800176e4`
- `0x180017c70`
- `0x180159010`

## import_xrefs

- `ole32!CoUninitialize` at `0x180017ffe`
- `ole32!CoUninitialize` at `0x180017ffe`
- `ole32!CoCreateInstance` at `0x180017dba`
- `ole32!CoCreateInstance` at `0x180017dba`
- `ole32!CoInitializeEx` at `0x180017d3a`
- `ole32!CoInitializeEx` at `0x180017d3a`
- `OLEAUT32!__imp_SysAllocString` at `0x180017cad`
- `OLEAUT32!__imp_SysAllocString` at `0x180017ce8`
- `OLEAUT32!__imp_SysAllocString` at `0x180017d14`
- `OLEAUT32!__imp_SysAllocString` at `0x180017cad`
- `OLEAUT32!__imp_SysAllocString` at `0x180017ce8`
- `OLEAUT32!__imp_SysAllocString` at `0x180017d14`
- `OLEAUT32!__imp_SysFreeString` at `0x180017fa4`
- `OLEAUT32!__imp_SysFreeString` at `0x180017cce`
- `OLEAUT32!__imp_SysFreeString` at `0x180017fa4`

## string_xrefs

- `0x180017ca6`: `system.webServer/httpCompression`
- `0x180017d0d`: `directory`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CHTTPFilePathHelper::QueryIISSettings(CHTTPFilePathHelper *this)
{
  BSTR v2; // rax
  BSTR v3; // rdi
  BSTR v5; // rax
  BSTR v6; // rsi
  BSTR v7; // rax
  BSTR v8; // r14
  unsigned int v9; // ebx
  HRESULT v10; // eax
  char v11; // r12
  __int64 v12; // r9
  CHostedCacheMsgEncoding *v13; // r10
  __int64 v14; // rdx
  HRESULT Instance; // eax
  int v16; // eax
  int v17; // eax
  __int64 v18; // r8
  int v19; // eax
  CHostedCacheMsgEncoding *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // [rsp+30h] [rbp-39h] BYREF
  __int64 v23; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v24[8]; // [rsp+40h] [rbp-29h] BYREF
  void (__stdcall *v25)(BSTR); // [rsp+48h] [rbp-21h]
  BSTR v26; // [rsp+50h] [rbp-19h]
  _BYTE v27[8]; // [rsp+58h] [rbp-11h] BYREF
  void (__stdcall *v28)(BSTR); // [rsp+60h] [rbp-9h]
  BSTR v29; // [rsp+68h] [rbp-1h]
  _BYTE v30[8]; // [rsp+70h] [rbp+7h] BYREF
  void (__stdcall *v31)(BSTR); // [rsp+78h] [rbp+Fh]
  BSTR v32; // [rsp+80h] [rbp+17h]
  struct IAppHostAdminManager *ppv; // [rsp+D8h] [rbp+6Fh] BYREF
  BSTR bstrString; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v35; // [rsp+E8h] [rbp+7Fh] BYREF

  v23 = 0;
  ppv = 0;
  v22 = 0;
  v35 = 0;
  bstrString = 0;
  v2 = SysAllocString(L"system.webServer/httpCompression");
  v3 = v2;
  if ( !v2 )
    goto LABEL_2;
  v24[0] = 0;
  v25 = SysFreeString;
  v26 = v2;
  v5 = SysAllocString(L"MACHINE/WEBROOT/APPHOST");
  v6 = v5;
  if ( !v5 )
  {
    __1__ScopeGuardImpl1_P6AXPEAV__list_USERVER_LIST_ENTRY_CHostedCacheScpDiscoveryManager__V__allocator_USERVER_LIST_ENTRY_CHostedCacheScpDiscoveryManager___std___std____EPEAV12___QEAA_XZ((__int64)v24);
LABEL_2:
    SmartPointer<CRepubJetSessionContext>::Release(&v23);
    return 14;
  }
  v30[0] = 0;
  v31 = SysFreeString;
  v32 = v5;
  v7 = SysAllocString(L"directory");
  v8 = v7;
  if ( v7 )
  {
    v27[0] = 0;
    v28 = SysFreeString;
    v29 = v7;
    v10 = CoInitializeEx(0, 0);
    if ( v10 >= 0 )
    {
      v11 = 1;
      Instance = CoCreateInstance(
                   &GUID_228fb8f7_fb53_4fd5_8c7b_ff59de606c5b,
                   0,
                   1u,
                   &GUID_9be77978_73ed_4a9a_87fd_13f09fec1b13,
                   (LPVOID *)&ppv);
      if ( Instance >= 0 )
      {
        v16 = ((__int64 (__fastcall *)(struct IAppHostAdminManager *, BSTR, BSTR, __int64 *))ppv->lpVtbl->GetAdminSection)(
                ppv,
                v3,
                v6,
                &v22);
        if ( v16 >= 0 )
        {
          v17 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *, _QWORD))(*(_QWORD *)v22 + 88LL))(
                  v22,
                  v8,
                  &v35,
                  (unsigned int)v16);
          if ( v17 >= 0 )
          {
            v19 = (*(__int64 (__fastcall **)(__int64, BSTR *, __int64, _QWORD))(*(_QWORD *)v35 + 56LL))(
                    v35,
                    &bstrString,
                    v18,
                    (unsigned int)v17);
            if ( v19 >= 0 )
            {
              v9 = CHTTPFilePathHelper::InitializeIISCompressionStorePath(this, bstrString);
              if ( v9 )
              {
                v20 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
                  || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
                {
                  goto LABEL_44;
                }
                v21 = 22;
              }
              else
              {
                v9 = CHTTPFilePathHelper::BuildAppPoolList(this, ppv);
                if ( !v9 )
                  goto LABEL_44;
                v20 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
                  || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
                {
                  goto LABEL_44;
                }
                v21 = 23;
              }
              WPP_SF_d(*((_QWORD *)v20 + 12), v21, WPP_dc3c53ed60a53432ddf31060f441d36e_Traceguids, v9);
LABEL_44:
              if ( bstrString )
              {
                SysFreeString(bstrString);
                bstrString = 0;
              }
              if ( v35 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
                v35 = 0;
              }
              if ( v22 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
                v22 = 0;
              }
              if ( ppv )
              {
                ((void (__fastcall *)(struct IAppHostAdminManager *))ppv->lpVtbl->Release)(ppv);
                ppv = 0;
              }
              if ( v11 )
                CoUninitialize();
              __1__ScopeGuardImpl1_P6AXPEAV__list_USERVER_LIST_ENTRY_CHostedCacheScpDiscoveryManager__V__allocator_USERVER_LIST_ENTRY_CHostedCacheScpDiscoveryManager___std___std____EPEAV12___QEAA_XZ((__int64)v27);
              goto LABEL_55;
            }
            v9 = TnoWin32ErrFromHR(v19);
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
              || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              goto LABEL_44;
            }
            v14 = 21;
          }
          else
          {
            v9 = TnoWin32ErrFromHR(v17);
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
              || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              goto LABEL_44;
            }
            v14 = 20;
          }
        }
        else
        {
          v9 = TnoWin32ErrFromHR(v16);
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
            || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            goto LABEL_44;
          }
          v14 = 19;
        }
      }
      else
      {
        v9 = TnoWin32ErrFromHR(Instance);
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          goto LABEL_44;
        }
        v14 = 18;
      }
    }
    else
    {
      v11 = 0;
      v9 = TnoWin32ErrFromHR(v10);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_44;
      }
      v14 = 17;
    }
    WPP_SF_d(*((_QWORD *)v13 + 12), v14, WPP_dc3c53ed60a53432ddf31060f441d36e_Traceguids, v12);
    goto LABEL_44;
  }
  v9 = 14;
LABEL_55:
  __1__ScopeGuardImpl1_P6AXPEAV__list_USERVER_LIST_ENTRY_CHostedCacheScpDiscoveryManager__V__allocator_USERVER_LIST_ENTRY_CHostedCacheScpDiscoveryManager___std___std____EPEAV12___QEAA_XZ((__int64)v30);
  __1__ScopeGuardImpl1_P6AXPEAV__list_USERVER_LIST_ENTRY_CHostedCacheScpDiscoveryManager__V__allocator_USERVER_LIST_ENTRY_CHostedCacheScpDiscoveryManager___std___std____EPEAV12___QEAA_XZ((__int64)v24);
  SmartPointer<CRepubJetSessionContext>::Release(&v23);
  return v9;
}

```

## disassembly

```asm
0x180017c70  mov     [rsp-8+arg_0], rbx
0x180017c75  push    rbp
0x180017c76  push    rsi
0x180017c77  push    rdi
0x180017c78  push    r12
0x180017c7a  push    r13
0x180017c7c  push    r14
0x180017c7e  push    r15
0x180017c80  lea     rbp, [rsp-27h]
0x180017c85  sub     rsp, 90h
0x180017c8c  mov     r15, rcx
0x180017c8f  xor     r13d, r13d
0x180017c92  mov     [rbp+57h+var_88], r13
0x180017c96  mov     [rbp+57h+arg_8], r13
0x180017c9a  mov     [rbp+57h+var_90], r13
0x180017c9e  mov     [rbp+57h+arg_18], r13
0x180017ca2  mov     [rbp+57h+bstrString], r13
0x180017ca6  lea     rcx, aSystemWebserve; "system.webServer/httpCompression"
0x180017cad  call    cs:__imp_SysAllocString
0x180017cb3  mov     rdi, rax
0x180017cb6  test    rax, rax
0x180017cb9  jnz     short loc_180017CCE
0x180017cbb  lea     rcx, [rbp+57h+var_88]
0x180017cbf  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x180017cc4  mov     eax, 0Eh
0x180017cc9  jmp     loc_18001802E
0x180017cce  mov     rbx, cs:__imp_SysFreeString
0x180017cd5  mov     [rbp+57h+var_80], r13b
0x180017cd9  mov     [rbp+57h+var_78], rbx
0x180017cdd  mov     [rbp+57h+var_70], rdi
0x180017ce1  lea     rcx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180017ce8  call    cs:__imp_SysAllocString
0x180017cee  mov     rsi, rax
0x180017cf1  test    rax, rax
0x180017cf4  jnz     short loc_180017D01
0x180017cf6  lea     rcx, [rbp+57h+var_80]
0x180017cfa  call    ??1?$ScopeGuardImpl1@P6AXPEAV?$list@USERVER_LIST_ENTRY@CHostedCacheScpDiscoveryManager@@V?$allocator@USERVER_LIST_ENTRY@CHostedCacheScpDiscoveryManager@@@std@@@std@@@_EPEAV12@@@QEAA@XZ
0x180017cff  jmp     short loc_180017CBB
0x180017d01  mov     [rbp+57h+var_50], r13b
0x180017d05  mov     [rbp+57h+var_48], rbx
0x180017d09  mov     [rbp+57h+var_40], rsi
0x180017d0d  lea     rcx, aDirectory; "directory"
0x180017d14  call    cs:__imp_SysAllocString
0x180017d1a  mov     r14, rax
0x180017d1d  test    rax, rax
0x180017d20  jnz     short loc_180017D2A
0x180017d22  lea     ebx, [rax+0Eh]
0x180017d25  jmp     loc_18001800F
0x180017d2a  mov     [rbp+57h+var_68], r13b
0x180017d2e  mov     [rbp+57h+var_60], rbx
0x180017d32  mov     [rbp+57h+var_58], r14
0x180017d36  xor     edx, edx; dwCoInit
0x180017d38  xor     ecx, ecx; pvReserved
0x180017d3a  call    cs:__imp_CoInitializeEx
0x180017d40  mov     r9d, eax
0x180017d43  test    eax, eax
0x180017d45  jns     short loc_180017D9A
0x180017d47  mov     r12b, r13b
0x180017d4a  mov     ecx, eax; int
0x180017d4c  call    ?TnoWin32ErrFromHR@@YAKJ@Z; TnoWin32ErrFromHR(long)
0x180017d51  mov     ebx, eax
0x180017d53  lea     rcx, WPP_GLOBAL_Control
0x180017d5a  mov     r10, cs:WPP_GLOBAL_Control
0x180017d61  cmp     r10, rcx
0x180017d64  jz      loc_180017F9B
0x180017d6a  test    byte ptr [r10+6Ch], 4
0x180017d6f  jz      loc_180017F9B
0x180017d75  cmp     byte ptr [r10+69h], 1
0x180017d7a  jb      loc_180017F9B
0x180017d80  mov     edx, 11h
0x180017d85  lea     r8, WPP_dc3c53ed60a53432ddf31060f441d36e_Traceguids
0x180017d8c  mov     rcx, [r10+60h]
0x180017d90  call    WPP_SF_d
0x180017d95  jmp     loc_180017F9B
0x180017d9a  mov     r12b, 1
0x180017d9d  lea     rax, [rbp+57h+arg_8]
0x180017da1  mov     [rsp+0C0h+ppv], rax; ppv
0x180017da6  lea     r9, _GUID_9be77978_73ed_4a9a_87fd_13f09fec1b13; riid
0x180017dad  xor     edx, edx; pUnkOuter
0x180017daf  lea     r8d, [rdx+1]; dwClsContext
0x180017db3  lea     rcx, _GUID_228fb8f7_fb53_4fd5_8c7b_ff59de606c5b; rclsid
0x180017dba  call    cs:__imp_CoCreateInstance
0x180017dc0  mov     r9d, eax
0x180017dc3  test    eax, eax
0x180017dc5  jns     short loc_180017E03
0x180017dc7  mov     ecx, eax; int
0x180017dc9  call    ?TnoWin32ErrFromHR@@YAKJ@Z; TnoWin32ErrFromHR(long)
0x180017dce  mov     ebx, eax
0x180017dd0  lea     rcx, WPP_GLOBAL_Control
0x180017dd7  mov     r10, cs:WPP_GLOBAL_Control
0x180017dde  cmp     r10, rcx
0x180017de1  jz      loc_180017F9B
0x180017de7  test    byte ptr [r10+6Ch], 4
0x180017dec  jz      loc_180017F9B
0x180017df2  cmp     [r10+69h], r12b
0x180017df6  jb      loc_180017F9B
0x180017dfc  mov     edx, 12h
0x180017e01  jmp     short loc_180017D85
0x180017e03  mov     rcx, [rbp+57h+arg_8]
0x180017e07  mov     rax, [rcx]
0x180017e0a  lea     r9, [rbp+57h+var_90]
0x180017e0e  mov     r8, rsi
0x180017e11  mov     rdx, rdi
0x180017e14  mov     rax, [rax+18h]
0x180017e18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e1d  mov     r9d, eax
0x180017e20  test    eax, eax
0x180017e22  jns     short loc_180017E63
0x180017e24  mov     ecx, eax; int
0x180017e26  call    ?TnoWin32ErrFromHR@@YAKJ@Z; TnoWin32ErrFromHR(long)
0x180017e2b  mov     ebx, eax
0x180017e2d  lea     rcx, WPP_GLOBAL_Control
0x180017e34  mov     r10, cs:WPP_GLOBAL_Control
0x180017e3b  cmp     r10, rcx
0x180017e3e  jz      loc_180017F9B
0x180017e44  test    byte ptr [r10+6Ch], 4
0x180017e49  jz      loc_180017F9B
0x180017e4f  cmp     [r10+69h], r12b
0x180017e53  jb      loc_180017F9B
0x180017e59  mov     edx, 13h
0x180017e5e  jmp     loc_180017D85
0x180017e63  mov     rcx, [rbp+57h+var_90]
0x180017e67  mov     rax, [rcx]
0x180017e6a  lea     r8, [rbp+57h+arg_18]
0x180017e6e  mov     rdx, r14
0x180017e71  mov     rax, [rax+58h]
0x180017e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e7a  mov     r9d, eax
0x180017e7d  test    eax, eax
0x180017e7f  jns     short loc_180017EC0
0x180017e81  mov     ecx, eax; int
0x180017e83  call    ?TnoWin32ErrFromHR@@YAKJ@Z; TnoWin32ErrFromHR(long)
0x180017e88  mov     ebx, eax
0x180017e8a  lea     rcx, WPP_GLOBAL_Control
0x180017e91  mov     r10, cs:WPP_GLOBAL_Control
0x180017e98  cmp     r10, rcx
0x180017e9b  jz      loc_180017F9B
0x180017ea1  test    byte ptr [r10+6Ch], 4
0x180017ea6  jz      loc_180017F9B
0x180017eac  cmp     [r10+69h], r12b
0x180017eb0  jb      loc_180017F9B
0x180017eb6  mov     edx, 14h
0x180017ebb  jmp     loc_180017D85
0x180017ec0  mov     rcx, [rbp+57h+arg_18]
0x180017ec4  mov     rax, [rcx]
0x180017ec7  lea     rdx, [rbp+57h+bstrString]
0x180017ecb  mov     rax, [rax+38h]
0x180017ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ed4  mov     r9d, eax
0x180017ed7  test    eax, eax
0x180017ed9  jns     short loc_180017F1A
0x180017edb  mov     ecx, eax; int
0x180017edd  call    ?TnoWin32ErrFromHR@@YAKJ@Z; TnoWin32ErrFromHR(long)
0x180017ee2  mov     ebx, eax
0x180017ee4  lea     rcx, WPP_GLOBAL_Control
0x180017eeb  mov     r10, cs:WPP_GLOBAL_Control
0x180017ef2  cmp     r10, rcx
0x180017ef5  jz      loc_180017F9B
0x180017efb  test    byte ptr [r10+6Ch], 4
0x180017f00  jz      loc_180017F9B
0x180017f06  cmp     [r10+69h], r12b
0x180017f0a  jb      loc_180017F9B
0x180017f10  mov     edx, 15h
0x180017f15  jmp     loc_180017D85
0x180017f1a  mov     rdx, [rbp+57h+bstrString]; unsigned __int16 *
0x180017f1e  mov     rcx, r15; this
0x180017f21  call    ?InitializeIISCompressionStorePath@CHTTPFilePathHelper@@AEAAKPEBG@Z; CHTTPFilePathHelper::InitializeIISCompressionStorePath(ushort const *)
0x180017f26  mov     ebx, eax
0x180017f28  test    eax, eax
0x180017f2a  jz      short loc_180017F52
0x180017f2c  lea     rcx, WPP_GLOBAL_Control
0x180017f33  mov     rax, cs:WPP_GLOBAL_Control
0x180017f3a  cmp     rax, rcx
0x180017f3d  jz      short loc_180017F9B
0x180017f3f  test    byte ptr [rax+6Ch], 4
0x180017f43  jz      short loc_180017F9B
0x180017f45  cmp     [rax+69h], r12b
0x180017f49  jb      short loc_180017F9B
0x180017f4b  mov     edx, 16h
0x180017f50  jmp     short loc_180017F88
0x180017f52  mov     rdx, [rbp+57h+arg_8]; struct IAppHostAdminManager *
0x180017f56  mov     rcx, r15; this
0x180017f59  call    ?BuildAppPoolList@CHTTPFilePathHelper@@AEAAKPEAUIAppHostAdminManager@@@Z; CHTTPFilePathHelper::BuildAppPoolList(IAppHostAdminManager *)
0x180017f5e  mov     ebx, eax
0x180017f60  test    eax, eax
0x180017f62  jz      short loc_180017F9B
0x180017f64  lea     rcx, WPP_GLOBAL_Control
0x180017f6b  mov     rax, cs:WPP_GLOBAL_Control
0x180017f72  cmp     rax, rcx
0x180017f75  jz      short loc_180017F9B
0x180017f77  test    byte ptr [rax+6Ch], 4
0x180017f7b  jz      short loc_180017F9B
0x180017f7d  cmp     [rax+69h], r12b
0x180017f81  jb      short loc_180017F9B
0x180017f83  mov     edx, 17h
0x180017f88  mov     r9d, ebx
0x180017f8b  lea     r8, WPP_dc3c53ed60a53432ddf31060f441d36e_Traceguids
0x180017f92  mov     rcx, [rax+60h]
0x180017f96  call    WPP_SF_d
0x180017f9b  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180017f9f  test    rcx, rcx
0x180017fa2  jz      short loc_180017FAE
0x180017fa4  call    cs:__imp_SysFreeString
0x180017faa  mov     [rbp+57h+bstrString], r13
0x180017fae  mov     rcx, [rbp+57h+arg_18]
0x180017fb2  test    rcx, rcx
0x180017fb5  jz      short loc_180017FC7
0x180017fb7  mov     rax, [rcx]
0x180017fba  mov     rax, [rax+10h]
0x180017fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fc3  mov     [rbp+57h+arg_18], r13
0x180017fc7  mov     rcx, [rbp+57h+var_90]
0x180017fcb  test    rcx, rcx
0x180017fce  jz      short loc_180017FE0
0x180017fd0  mov     rax, [rcx]
0x180017fd3  mov     rax, [rax+10h]
0x180017fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fdc  mov     [rbp+57h+var_90], r13
0x180017fe0  mov     rcx, [rbp+57h+arg_8]
0x180017fe4  test    rcx, rcx
0x180017fe7  jz      short loc_180017FF9
0x180017fe9  mov     rax, [rcx]
0x180017fec  mov     rax, [rax+10h]
0x180017ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ff5  mov     [rbp+57h+arg_8], r13
0x180017ff9  test    r12b, r12b
0x180017ffc  jz      short loc_180018005
0x180017ffe  call    cs:__imp_CoUninitialize
0x180018004  nop
0x180018005  lea     rcx, [rbp+57h+var_68]
0x180018009  call    ??1?$ScopeGuardImpl1@P6AXPEAV?$list@USERVER_LIST_ENTRY@CHostedCacheScpDiscoveryManager@@V?$allocator@USERVER_LIST_ENTRY@CHostedCacheScpDiscoveryManager@@@std@@@std@@@_EPEAV12@@@QEAA@XZ
0x18001800e  nop
0x18001800f  lea     rcx, [rbp+57h+var_50]
0x180018013  call    ??1?$ScopeGuardImpl1@P6AXPEAV?$list@USERVER_LIST_ENTRY@CHostedCacheScpDiscoveryManager@@V?$allocator@USERVER_LIST_ENTRY@CHostedCacheScpDiscoveryManager@@@std@@@std@@@_EPEAV12@@@QEAA@XZ
0x180018018  nop
0x180018019  lea     rcx, [rbp+57h+var_80]
0x18001801d  call    ??1?$ScopeGuardImpl1@P6AXPEAV?$list@USERVER_LIST_ENTRY@CHostedCacheScpDiscoveryManager@@V?$allocator@USERVER_LIST_ENTRY@CHostedCacheScpDiscoveryManager@@@std@@@std@@@_EPEAV12@@@QEAA@XZ
0x180018022  nop
0x180018023  lea     rcx, [rbp+57h+var_88]
0x180018027  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x18001802c  mov     eax, ebx
0x18001802e  mov     rbx, [rsp+0C0h+arg_0]
0x180018036  add     rsp, 90h
0x18001803d  pop     r15
0x18001803f  pop     r14
0x180018041  pop     r13
0x180018043  pop     r12
0x180018045  pop     rdi
0x180018046  pop     rsi
0x180018047  pop     rbp
0x180018048  retn
```
