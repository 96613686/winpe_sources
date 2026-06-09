# CUpdateManager::GetPotentialUpdates(IUpdateCollection * *)

- ea: `0x140036c28`
- end: `0x140036f4c`
- name: `?GetPotentialUpdates@CUpdateManager@@IEAAJPEAPEAUIUpdateCollection@@@Z`
- size: `804`
- prototype: `__int64 __fastcall(CUpdateManager *__hidden this, struct IUpdateCollection **)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1400360c4`
- `0x1400373f4`

## callees

- `0x1400367e4`
- `0x140036c28`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007e010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140036ccd`
- `KERNEL32!IsDebuggerPresent` at `0x140036d87`
- `KERNEL32!IsDebuggerPresent` at `0x140036e1c`
- `KERNEL32!IsDebuggerPresent` at `0x140036e8e`
- `KERNEL32!IsDebuggerPresent` at `0x140036ccd`
- `KERNEL32!IsDebuggerPresent` at `0x140036d87`
- `KERNEL32!IsDebuggerPresent` at `0x140036e1c`
- `KERNEL32!IsDebuggerPresent` at `0x140036e8e`
- `ole32!CoCreateInstance` at `0x140036c82`
- `ole32!CoCreateInstance` at `0x140036c82`
- `OLEAUT32!__imp_SysAllocString` at `0x140036d3b`
- `OLEAUT32!__imp_SysAllocString` at `0x140036d3b`
- `OLEAUT32!__imp_SysFreeString` at `0x140036f35`
- `OLEAUT32!__imp_SysFreeString` at `0x140036f35`

## string_xrefs

- `0x140036ca7`: `termsrv\wms\src\devices\wmssvc\updatemanager.cpp`
- `0x140036d5f`: `termsrv\wms\src\devices\wmssvc\updatemanager.cpp`
- `0x140036df9`: `termsrv\wms\src\devices\wmssvc\updatemanager.cpp`
- `0x140036e6b`: `termsrv\wms\src\devices\wmssvc\updatemanager.cpp`
- `0x140036c3e`: `CUpdateManager::GetPotentialUpdates - Enter.\n`
- `0x140036c9d`: `CUpdateManager::GetPotentialUpdates`
- `0x140036d4e`: `CUpdateManager::GetPotentialUpdates`
- `0x140036def`: `CUpdateManager::GetPotentialUpdates`
- `0x140036e61`: `CUpdateManager::GetPotentialUpdates`
- `0x140036eae`: `CUpdateManager::GetPotentialUpdates - Detected the following potential Windows Updates:\n`
- `0x140036d34`: `(IsInstalled=0 and AutoSelectOnWebSites=1)`

## pseudocode

```c
__int64 __fastcall CUpdateManager::GetPotentialUpdates(CUpdateManager *this, struct IUpdateCollection **a2)
{
  HRESULT v3; // eax
  int v4; // ebx
  OLECHAR *v5; // r12
  __int64 v6; // r9
  __int64 v7; // r8
  BSTR v8; // rax
  int v9; // eax
  int v10; // eax
  CUpdateManager *v11; // rcx
  struct IUpdateCollection *v13; // [rsp+80h] [rbp+40h] BYREF
  __int64 v14; // [rsp+90h] [rbp+50h] BYREF
  LPVOID ppv; // [rsp+98h] [rbp+58h] BYREF

  ppv = 0;
  v14 = 0;
  v13 = 0;
  DEBUGMSG(L"CUpdateManager::GetPotentialUpdates - Enter.\n");
  v3 = CoCreateInstance(
         &GUID_b699e5e8_67ff_4177_88b0_3684a3388bfb,
         0,
         1u,
         &GUID_04c6895d_eaf2_4034_97f3_311de9be413a,
         &ppv);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 0;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
      0x499u,
      L"CUpdateManager::GetPotentialUpdates",
      L"CHRA",
      L"hr",
      v3);
    if ( IsDebuggerPresent() )
    {
      v6 = 1177;
LABEL_4:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
        v6,
        L"CUpdateManager::GetPotentialUpdates",
        L"CHRA",
        L"hr",
        v4);
      goto LABEL_23;
    }
    v7 = 1177;
    goto LABEL_7;
  }
  v8 = SysAllocString(L"(IsInstalled=0 and AutoSelectOnWebSites=1)");
  v5 = v8;
  if ( v8 )
  {
    v9 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)ppv + 152LL))(ppv, v8, &v14);
    v4 = v9;
    if ( v9 < 0 )
    {
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
        0x49Fu,
        L"CUpdateManager::GetPotentialUpdates",
        L"CHRA",
        L"hr",
        v9);
      if ( IsDebuggerPresent() )
      {
        v6 = 1183;
        goto LABEL_4;
      }
      v7 = 1183;
      goto LABEL_7;
    }
    v10 = (*(__int64 (__fastcall **)(__int64, struct IUpdateCollection **))(*(_QWORD *)v14 + 72LL))(v14, &v13);
    v4 = v10;
    if ( v10 < 0 )
    {
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
        0x4A2u,
        L"CUpdateManager::GetPotentialUpdates",
        L"CHRA",
        L"hr",
        v10);
      if ( IsDebuggerPresent() )
      {
        v6 = 1186;
        goto LABEL_4;
      }
      v7 = 1186;
LABEL_7:
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
        v7,
        L"CUpdateManager::GetPotentialUpdates",
        L"CHRA",
        L"hr",
        v4);
      goto LABEL_23;
    }
    DEBUGMSG(L"CUpdateManager::GetPotentialUpdates - Detected the following potential Windows Updates:\n");
    v4 = CUpdateManager::DumpUpdates(v11, v13, 0);
    if ( v4 >= 0 )
    {
      *a2 = v13;
      v13 = 0;
    }
  }
  else
  {
    v4 = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
      0x49Cu,
      L"CUpdateManager::GetPotentialUpdates",
      L"CPR",
      L"bstrCriteria",
      -2147024882);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
        1180,
        L"CUpdateManager::GetPotentialUpdates",
        L"CPR",
        L"bstrCriteria",
        -2147024882);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
        1180,
        L"CUpdateManager::GetPotentialUpdates",
        L"CPR",
        L"bstrCriteria",
        -2147024882);
  }
LABEL_23:
  if ( v13 )
  {
    ((void (__fastcall *)(struct IUpdateCollection *))v13->lpVtbl->Release)(v13);
    v13 = 0;
  }
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v14 = 0;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  SysFreeString(v5);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140036c28  mov     [rsp-38h+arg_0], rcx
0x140036c2d  push    rbp
0x140036c2e  push    rbx
0x140036c2f  push    rsi
0x140036c30  push    rdi
0x140036c31  push    r12
0x140036c33  push    r14
0x140036c35  push    r15
0x140036c37  mov     rbp, rsp
0x140036c3a  sub     rsp, 40h
0x140036c3e  lea     rcx, aCupdatemanager_6; "CUpdateManager::GetPotentialUpdates - E"...
0x140036c45  mov     [rbp+arg_18], 0
0x140036c4d  mov     rdi, rdx
0x140036c50  mov     [rbp+arg_10], 0
0x140036c58  mov     [rbp+arg_0], 0
0x140036c60  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140036c65  xor     edx, edx; pUnkOuter
0x140036c67  lea     rax, [rbp+arg_18]
0x140036c6b  lea     r9, _GUID_04c6895d_eaf2_4034_97f3_311de9be413a; riid
0x140036c72  mov     [rsp+40h+ppv], rax; ppv
0x140036c77  lea     rcx, _GUID_b699e5e8_67ff_4177_88b0_3684a3388bfb; rclsid
0x140036c7e  lea     r8d, [rdx+1]; dwClsContext
0x140036c82  call    cs:__imp_CoCreateInstance
0x140036c88  mov     ebx, eax
0x140036c8a  test    eax, eax
0x140036c8c  jns     loc_140036D34
0x140036c92  mov     [rsp+40h+var_18], eax; int
0x140036c96  lea     r15, aChra; "CHRA"
0x140036c9d  lea     rsi, aCupdatemanager_83; "CUpdateManager::GetPotentialUpdates"
0x140036ca4  mov     r9, r15; unsigned __int16 *
0x140036ca7  lea     rdi, aTermsrvWmsSrcD_7; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x140036cae  mov     r8, rsi; unsigned __int16 *
0x140036cb1  lea     r14, aHr; "hr"
0x140036cb8  mov     rcx, rdi; unsigned __int16 *
0x140036cbb  mov     edx, 499h; unsigned int
0x140036cc0  mov     [rsp+40h+ppv], r14; unsigned __int16 *
0x140036cc5  xor     r12d, r12d
0x140036cc8  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140036ccd  call    cs:__imp_IsDebuggerPresent
0x140036cd3  test    eax, eax
0x140036cd5  jz      short loc_140036D09
0x140036cd7  mov     r9d, 499h
0x140036cdd  mov     [rsp+40h+var_8], ebx
0x140036ce1  mov     [rsp+40h+var_10], r14
0x140036ce6  mov     qword ptr [rsp+40h+var_18], r15
0x140036ceb  mov     r8, rdi
0x140036cee  mov     [rsp+40h+ppv], rsi
0x140036cf3  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140036cfa  mov     ecx, 2; unsigned __int8
0x140036cff  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140036d04  jmp     loc_140036EDB
0x140036d09  mov     r8d, 499h
0x140036d0f  mov     dword ptr [rsp+40h+var_10], ebx
0x140036d13  mov     qword ptr [rsp+40h+var_18], r14
0x140036d18  mov     [rsp+40h+ppv], r15
0x140036d1d  mov     r9, rsi
0x140036d20  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140036d27  mov     rdx, rdi
0x140036d2a  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140036d2f  jmp     loc_140036EDB
0x140036d34  lea     rcx, aIsinstalled0An; "(IsInstalled=0 and AutoSelectOnWebSites"...
0x140036d3b  call    cs:__imp_SysAllocString
0x140036d41  mov     r12, rax
0x140036d44  test    rax, rax
0x140036d47  jnz     short loc_140036DC4
0x140036d49  mov     ebx, 8007000Eh
0x140036d4e  lea     rsi, aCupdatemanager_83; "CUpdateManager::GetPotentialUpdates"
0x140036d55  mov     r14d, 49Ch
0x140036d5b  mov     [rsp+40h+var_18], ebx; int
0x140036d5f  lea     rdi, aTermsrvWmsSrcD_7; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x140036d66  mov     r8, rsi; unsigned __int16 *
0x140036d69  lea     r15, aBstrcriteria; "bstrCriteria"
0x140036d70  mov     edx, r14d; unsigned int
0x140036d73  mov     rcx, rdi; unsigned __int16 *
0x140036d76  mov     [rsp+40h+ppv], r15; unsigned __int16 *
0x140036d7b  lea     r9, aCpr; "CPR"
0x140036d82  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140036d87  call    cs:__imp_IsDebuggerPresent
0x140036d8d  test    eax, eax
0x140036d8f  lea     rax, aCpr; "CPR"
0x140036d96  jz      short loc_140036DAE
0x140036d98  mov     [rsp+40h+var_8], ebx
0x140036d9c  mov     r9d, r14d
0x140036d9f  mov     [rsp+40h+var_10], r15
0x140036da4  mov     qword ptr [rsp+40h+var_18], rax
0x140036da9  jmp     loc_140036CEB
0x140036dae  mov     dword ptr [rsp+40h+var_10], ebx
0x140036db2  mov     r8d, r14d
0x140036db5  mov     qword ptr [rsp+40h+var_18], r15
0x140036dba  mov     [rsp+40h+ppv], rax
0x140036dbf  jmp     loc_140036D1D
0x140036dc4  mov     rcx, [rbp+arg_18]
0x140036dc8  lea     r8, [rbp+arg_10]
0x140036dcc  mov     rdx, r12
0x140036dcf  mov     rax, [rcx]
0x140036dd2  mov     rax, [rax+98h]
0x140036dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036dde  mov     ebx, eax
0x140036de0  test    eax, eax
0x140036de2  jns     short loc_140036E3C
0x140036de4  mov     [rsp+40h+var_18], eax; int
0x140036de8  lea     r15, aChra; "CHRA"
0x140036def  lea     rsi, aCupdatemanager_83; "CUpdateManager::GetPotentialUpdates"
0x140036df6  mov     r9, r15; unsigned __int16 *
0x140036df9  lea     rdi, aTermsrvWmsSrcD_7; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x140036e00  mov     r8, rsi; unsigned __int16 *
0x140036e03  lea     r14, aHr; "hr"
0x140036e0a  mov     rcx, rdi; unsigned __int16 *
0x140036e0d  mov     edx, 49Fh; unsigned int
0x140036e12  mov     [rsp+40h+ppv], r14; unsigned __int16 *
0x140036e17  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140036e1c  call    cs:__imp_IsDebuggerPresent
0x140036e22  test    eax, eax
0x140036e24  jz      short loc_140036E31
0x140036e26  mov     r9d, 49Fh
0x140036e2c  jmp     loc_140036CDD
0x140036e31  mov     r8d, 49Fh
0x140036e37  jmp     loc_140036D0F
0x140036e3c  mov     rcx, [rbp+arg_10]
0x140036e40  lea     rdx, [rbp+arg_0]
0x140036e44  mov     rax, [rcx]
0x140036e47  mov     rax, [rax+48h]
0x140036e4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036e50  mov     ebx, eax
0x140036e52  test    eax, eax
0x140036e54  jns     short loc_140036EAE
0x140036e56  mov     [rsp+40h+var_18], eax; int
0x140036e5a  lea     r15, aChra; "CHRA"
0x140036e61  lea     rsi, aCupdatemanager_83; "CUpdateManager::GetPotentialUpdates"
0x140036e68  mov     r9, r15; unsigned __int16 *
0x140036e6b  lea     rdi, aTermsrvWmsSrcD_7; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x140036e72  mov     r8, rsi; unsigned __int16 *
0x140036e75  lea     r14, aHr; "hr"
0x140036e7c  mov     rcx, rdi; unsigned __int16 *
0x140036e7f  mov     edx, 4A2h; unsigned int
0x140036e84  mov     [rsp+40h+ppv], r14; unsigned __int16 *
0x140036e89  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140036e8e  call    cs:__imp_IsDebuggerPresent
0x140036e94  test    eax, eax
0x140036e96  jz      short loc_140036EA3
0x140036e98  mov     r9d, 4A2h
0x140036e9e  jmp     loc_140036CDD
0x140036ea3  mov     r8d, 4A2h
0x140036ea9  jmp     loc_140036D0F
0x140036eae  lea     rcx, aCupdatemanager_82; "CUpdateManager::GetPotentialUpdates - D"...
0x140036eb5  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140036eba  mov     rdx, [rbp+arg_0]; struct IUpdateCollection *
0x140036ebe  xor     r8d, r8d; struct IInstallationResult *
0x140036ec1  call    ?DumpUpdates@CUpdateManager@@IEAAJPEAUIUpdateCollection@@PEAUIInstallationResult@@@Z; CUpdateManager::DumpUpdates(IUpdateCollection *,IInstallationResult *)
0x140036ec6  mov     ebx, eax
0x140036ec8  test    eax, eax
0x140036eca  js      short loc_140036EDB
0x140036ecc  mov     rax, [rbp+arg_0]
0x140036ed0  mov     [rdi], rax
0x140036ed3  mov     [rbp+arg_0], 0
0x140036edb  mov     rcx, [rbp+arg_0]
0x140036edf  test    rcx, rcx
0x140036ee2  jz      short loc_140036EF8
0x140036ee4  mov     rax, [rcx]
0x140036ee7  mov     rax, [rax+10h]
0x140036eeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036ef0  mov     [rbp+arg_0], 0
0x140036ef8  mov     rcx, [rbp+arg_10]
0x140036efc  test    rcx, rcx
0x140036eff  jz      short loc_140036F15
0x140036f01  mov     rax, [rcx]
0x140036f04  mov     rax, [rax+10h]
0x140036f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036f0d  mov     [rbp+arg_10], 0
0x140036f15  mov     rcx, [rbp+arg_18]
0x140036f19  test    rcx, rcx
0x140036f1c  jz      short loc_140036F32
0x140036f1e  mov     rax, [rcx]
0x140036f21  mov     rax, [rax+10h]
0x140036f25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036f2a  mov     [rbp+arg_18], 0
0x140036f32  mov     rcx, r12; bstrString
0x140036f35  call    cs:__imp_SysFreeString
0x140036f3b  mov     eax, ebx
0x140036f3d  add     rsp, 40h
0x140036f41  pop     r15
0x140036f43  pop     r14
0x140036f45  pop     r12
0x140036f47  pop     rdi
0x140036f48  pop     rsi
0x140036f49  pop     rbx
0x140036f4a  pop     rbp
0x140036f4b  retn
```
