# CUpdateVmDomainAccountsHostThread::s_GetStationVirtualMachineIds(unsigned __int64 *,ushort * * *)

- ea: `0x140035158`
- end: `0x1400359d4`
- name: `?s_GetStationVirtualMachineIds@CUpdateVmDomainAccountsHostThread@@KAJPEA_KPEAPEAPEAG@Z`
- size: `2172`
- prototype: `__int64 __fastcall(unsigned __int64 *, unsigned __int16 ***)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x140034aa4`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x1400033e8`
- `0x140035158`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c290`
- `0x14005c408`
- `0x140061a0c`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14003528f`
- `ADVAPI32!RegOpenKeyExW` at `0x14003528f`
- `ADVAPI32!RegGetValueW` at `0x140035219`
- `ADVAPI32!RegGetValueW` at `0x140035219`
- `ADVAPI32!RegCloseKey` at `0x140035244`
- `ADVAPI32!RegCloseKey` at `0x140035583`
- `ADVAPI32!RegCloseKey` at `0x140035244`
- `ADVAPI32!RegCloseKey` at `0x140035583`
- `KERNEL32!IsDebuggerPresent` at `0x140035476`
- `KERNEL32!IsDebuggerPresent` at `0x14003550d`
- `KERNEL32!IsDebuggerPresent` at `0x14003565a`
- `KERNEL32!IsDebuggerPresent` at `0x140035708`
- `KERNEL32!IsDebuggerPresent` at `0x1400357a7`
- `KERNEL32!IsDebuggerPresent` at `0x140035891`
- `KERNEL32!IsDebuggerPresent` at `0x14003593d`
- `KERNEL32!IsDebuggerPresent` at `0x140035476`
- `KERNEL32!IsDebuggerPresent` at `0x14003550d`
- `KERNEL32!IsDebuggerPresent` at `0x14003565a`
- `KERNEL32!IsDebuggerPresent` at `0x140035708`
- `KERNEL32!IsDebuggerPresent` at `0x1400357a7`
- `KERNEL32!IsDebuggerPresent` at `0x140035891`
- `KERNEL32!IsDebuggerPresent` at `0x14003593d`
- `OLEAUT32!__imp_SysAllocString` at `0x140035816`
- `OLEAUT32!__imp_SysAllocString` at `0x140035816`
- `OLEAUT32!__imp_SysFreeString` at `0x140035562`
- `OLEAUT32!__imp_SysFreeString` at `0x140035562`

## string_xrefs

- `0x140035449`: `CUpdateVmDomainAccountsHostThread::s_GetStationVirtualMachineIds`
- `0x1400354dc`: `CUpdateVmDomainAccountsHostThread::s_GetStationVirtualMachineIds`
- `0x14003562d`: `CUpdateVmDomainAccountsHostThread::s_GetStationVirtualMachineIds`
- `0x1400356d7`: `CUpdateVmDomainAccountsHostThread::s_GetStationVirtualMachineIds`
- `0x14003576b`: `CUpdateVmDomainAccountsHostThread::s_GetStationVirtualMachineIds`
- `0x140035907`: `CUpdateVmDomainAccountsHostThread::s_GetStationVirtualMachineIds`
- `0x14003545b`: `termsrv\wms\src\devices\wmssvc\updatevmdomainaccountshostthread.cpp`
- `0x1400354e9`: `termsrv\wms\src\devices\wmssvc\updatevmdomainaccountshostthread.cpp`
- `0x14003563f`: `termsrv\wms\src\devices\wmssvc\updatevmdomainaccountshostthread.cpp`
- `0x1400356e4`: `termsrv\wms\src\devices\wmssvc\updatevmdomainaccountshostthread.cpp`
- `0x140035772`: `termsrv\wms\src\devices\wmssvc\updatevmdomainaccountshostthread.cpp`
- `0x14003591c`: `termsrv\wms\src\devices\wmssvc\updatevmdomainaccountshostthread.cpp`

## pseudocode

```c
__int64 __fastcall CUpdateVmDomainAccountsHostThread::s_GetStationVirtualMachineIds(
        unsigned __int64 *a1,
        unsigned __int16 ***a2)
{
  unsigned __int64 v4; // r13
  _QWORD *v5; // r15
  unsigned int v6; // esi
  int ValueW; // ebx
  LSTATUS v8; // eax
  _WORD *v9; // rdi
  _WORD *v10; // rax
  __int64 v11; // rdx
  __int64 ***v12; // rdx
  __int64 v13; // rax
  _WORD *v14; // r9
  _WORD *v15; // rcx
  __int64 v16; // r8
  _WORD *v17; // rcx
  _QWORD *v18; // rax
  const unsigned __int16 *v19; // r9
  _QWORD *v20; // r13
  unsigned __int64 v21; // rsi
  unsigned int v22; // edi
  void *v23; // rcx
  __int64 *v24; // rax
  unsigned int v25; // r12d
  __int64 v26; // r9
  __int64 v27; // r8
  unsigned int v28; // r12d
  const OLECHAR *v29; // r14
  BSTR v30; // rax
  LPDWORD pcbData; // [rsp+30h] [rbp-D0h]
  int v33; // [rsp+38h] [rbp-C8h]
  unsigned int pvData; // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v35; // [rsp+48h] [rbp-B8h] BYREF
  __int64 **v36; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v37; // [rsp+58h] [rbp-A8h]
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  void *Block; // [rsp+68h] [rbp-98h] BYREF
  DWORD v40; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 *v41; // [rsp+78h] [rbp-88h]
  unsigned __int16 ***v42; // [rsp+80h] [rbp-80h]
  WCHAR SubKey[264]; // [rsp+90h] [rbp-70h] BYREF

  v42 = a2;
  v41 = a1;
  v40 = 4;
  pvData = 0;
  hKey = 0;
  memset_0(SubKey, 0, 0x208u);
  *a1 = 0;
  v36 = &v35;
  v37 = 0;
  v35 = (__int64 *)&v35;
  Block = 0;
  *a2 = 0;
  v4 = 0;
  v5 = 0;
  v6 = 1;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows MultiPoint Server\\Stations",
             L"Last Station Id",
             0x18u,
             0,
             &pvData,
             &v40);
  if ( !pvData )
    goto LABEL_39;
  do
  {
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    ValueW = StringCchPrintfW(SubKey, 0x104u, L"SOFTWARE\\Microsoft\\Windows MultiPoint Server\\Stations\\%u", v6);
    if ( ValueW < 0 )
    {
      v25 = 92;
LABEL_75:
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountshostthread.cpp",
        v25,
        L"CUpdateVmDomainAccountsHostThread::s_GetStationVirtualMachineIds",
        L"CHRA",
        L"hr",
        ValueW);
      if ( !IsDebuggerPresent() )
      {
        LODWORD(pcbData) = ValueW;
        v27 = v25;
        goto LABEL_79;
      }
      v33 = ValueW;
      v26 = v25;
LABEL_77:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountshostthread.cpp",
        v26,
        L"CUpdateVmDomainAccountsHostThread::s_GetStationVirtualMachineIds",
        L"CHRA",
        L"hr",
        v33);
LABEL_80:
      v5 = 0;
      goto LABEL_40;
    }
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
    if ( v8 )
    {
      if ( v8 != 2 )
      {
        if ( v8 > 0 )
          ValueW = (unsigned __int16)v8 | 0x80070000;
        else
          ValueW = v8;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountshostthread.cpp",
          0x5Fu,
          L"CUpdateVmDomainAccountsHostThread::s_GetStationVirtualMachineIds",
          L"CBRAEx",
          L"lr == 0L || lr == 2L",
          ValueW);
        if ( IsDebuggerPresent() )
        {
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountshostthread.cpp",
            95,
            L"CUpdateVmDomainAccountsHostThread::s_GetStationVirtualMachineIds",
            L"CBRAEx",
            L"lr == 0L || lr == 2L",
            ValueW);
        }
        else
        {
          LODWORD(pcbData) = ValueW;
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountshostthread.cpp",
            95,
            L"CUpdateVmDomainAccountsHostThread::s_GetStationVirtualMachineIds",
            L"CBRAEx",
            L"lr == 0L || lr == 2L",
            pcbData);
        }
        goto LABEL_39;
      }
    }
    else
    {
      ValueW = RegUtil::GetStringValue(1, hKey, L"Virtual Machine Id", &Block);
      if ( ((ValueW + 0x80000000) & 0x80000000) == 0 && ValueW != -2147024894 )
      {
        ValueW = -2147467259;
        goto LABEL_40;
      }
      if ( ValueW == -2147024894 )
        goto LABEL_29;
      v9 = Block;
      if ( !Block )
      {
        ValueW = -2147024809;
LABEL_58:
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountshostthread.cpp",
          0x6Eu,
          L"CUpdateVmDomainAccountsHostThread::s_GetStationVirtualMachineIds",
          L"CHRA",
          L"hr",
          -2147024809);
        if ( IsDebuggerPresent() )
        {
          v33 = -2147024809;
          v26 = 110;
          goto LABEL_77;
        }
        LODWORD(pcbData) = -2147024809;
        v27 = 110;
LABEL_79:
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountshostthread.cpp",
          v27,
          L"CUpdateVmDomainAccountsHostThread::s_GetStationVirtualMachineIds",
          L"CHRA",
          L"hr",
          pcbData);
        goto LABEL_80;
      }
      v10 = Block;
      v11 = 0x7FFFFFFF;
      do
      {
        if ( !*v10 )
          break;
        ++v10;
        --v11;
      }
      while ( v11 );
      ValueW = v11 == 0 ? 0x80070057 : 0;
      if ( !v11 )
        goto LABEL_58;
      if ( ((0x7FFFFFFF - v11) & -(__int64)(v11 != 0)) != 0 )
      {
        v12 = (__int64 ***)operator new(0x218u);
        if ( !v12 )
        {
          ValueW = -2147024882;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountshostthread.cpp",
            0x73u,
            L"CUpdateVmDomainAccountsHostThread::s_GetStationVirtualMachineIds",
            L"CPR",
            L"pMachineIdNode",
            -2147024882);
          if ( IsDebuggerPresent() )
          {
            DEBUGMSGLEVEL(
              2u,
              L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountshostthread.cpp",
              115,
              L"CUpdateVmDomainAccountsHostThread::s_GetStationVirtualMachineIds",
              L"CPR",
              L"pMachineIdNode",
              -2147024882);
          }
          else
          {
            LODWORD(pcbData) = -2147024882;
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountshostthread.cpp",
              115,
              L"CUpdateVmDomainAccountsHostThread::s_GetStationVirtualMachineIds",
              L"CPR",
              L"pMachineIdNode",
              pcbData);
          }
          goto LABEL_40;
        }
        v13 = 2147483646;
        v14 = v12 + 2;
        v15 = v9;
        v16 = 260;
        do
        {
          if ( !v13 )
            break;
          if ( !*v15 )
            break;
          *v14++ = *v15++;
          --v13;
          --v16;
        }
        while ( v16 );
        v17 = v14 - 1;
        ValueW = v16 == 0 ? 0x8007007A : 0;
        if ( v16 )
          v17 = v14;
        *v17 = 0;
        if ( !v16 )
        {
          v25 = 118;
          goto LABEL_75;
        }
        v18 = v36;
        if ( *v36 != (__int64 *)&v35 )
LABEL_81:
          __fastfail(3u);
        v12[1] = v36;
        *v12 = &v35;
        ++v4;
        *v18 = v12;
        v36 = (__int64 **)v12;
        v37 = v4;
      }
      operator delete(v9);
      Block = 0;
    }
LABEL_29:
    ++v6;
  }
  while ( v6 <= pvData );
  if ( !v4 )
    goto LABEL_39;
  v5 = operator new(saturated_mul(v4, 8u));
  if ( v5 )
  {
    v28 = 0;
    v29 = (const OLECHAR *)v35;
    if ( v35 != (__int64 *)&v35 )
    {
      while ( v28 < (unsigned int)v4 )
      {
        if ( !v29 )
        {
          LOGASSERT(
            L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountshostthread.cpp",
            0x88u,
            L"CUpdateVmDomainAccountsHostThread::s_GetStationVirtualMachineIds",
            v19,
            L"pMachineIdNode != NULL");
          if ( IsDebuggerPresent() )
            DEBUGMSGLEVEL(
              2u,
              L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountshostthread.cpp",
              136,
              L"CUpdateVmDomainAccountsHostThread::s_GetStationVirtualMachineIds",
              L"ASSERT",
              L"pMachineIdNode != NULL");
          else
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountshostthread.cpp",
              136,
              L"CUpdateVmDomainAccountsHostThread::s_GetStationVirtualMachineIds",
              L"ASSERT",
              L"pMachineIdNode != NULL");
        }
        v30 = SysAllocString(v29 + 8);
        v5[v28] = v30;
        if ( !v30 )
        {
          v20 = v5;
          ValueW = -2147024882;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountshostthread.cpp",
            0x8Bu,
            L"CUpdateVmDomainAccountsHostThread::s_GetStationVirtualMachineIds",
            L"CPR",
            L"pbstrMachineIds[idx]",
            -2147024882);
          if ( IsDebuggerPresent() )
          {
            DEBUGMSGLEVEL(
              2u,
              L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountshostthread.cpp",
              139,
              L"CUpdateVmDomainAccountsHostThread::s_GetStationVirtualMachineIds",
              L"CPR",
              L"pbstrMachineIds[idx]",
              -2147024882);
          }
          else
          {
            LODWORD(pcbData) = -2147024882;
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountshostthread.cpp",
              139,
              L"CUpdateVmDomainAccountsHostThread::s_GetStationVirtualMachineIds",
              L"CPR",
              L"pbstrMachineIds[idx]",
              pcbData);
          }
          goto LABEL_35;
        }
        v29 = *(const OLECHAR **)v29;
        ++v28;
        if ( v29 == (const OLECHAR *)&v35 )
          break;
      }
    }
    *v41 = v4;
    *v42 = (unsigned __int16 **)v5;
LABEL_39:
    v5 = 0;
    if ( ValueW >= 0 )
      goto LABEL_43;
LABEL_40:
    v21 = v37;
    v20 = 0;
    v22 = 0;
    if ( v37 )
      goto LABEL_41;
    goto LABEL_42;
  }
  ValueW = -2147024882;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountshostthread.cpp",
    0x82u,
    L"CUpdateVmDomainAccountsHostThread::s_GetStationVirtualMachineIds",
    L"CPR",
    L"pbstrMachineIds",
    -2147024882);
  if ( IsDebuggerPresent() )
  {
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountshostthread.cpp",
      130,
      L"CUpdateVmDomainAccountsHostThread::s_GetStationVirtualMachineIds",
      L"CPR",
      L"pbstrMachineIds",
      -2147024882);
  }
  else
  {
    LODWORD(pcbData) = -2147024882;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountshostthread.cpp",
      130,
      L"CUpdateVmDomainAccountsHostThread::s_GetStationVirtualMachineIds",
      L"CPR",
      L"pbstrMachineIds",
      pcbData);
  }
  v20 = 0;
LABEL_35:
  v21 = v37;
  v22 = 0;
  do
LABEL_41:
    SysFreeString((BSTR)v20[v22++]);
  while ( v22 < v21 );
LABEL_42:
  operator delete(v5);
LABEL_43:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v23 = Block;
  while ( 1 )
  {
    operator delete(v23);
    v23 = v35;
    if ( v35 == (__int64 *)&v35 )
      return (unsigned int)ValueW;
    if ( (__int64 **)v35[1] != &v35 )
      goto LABEL_81;
    v24 = (__int64 *)*v35;
    if ( *(__int64 **)(*v35 + 8) != v35 )
      goto LABEL_81;
    v35 = (__int64 *)*v35;
    v24[1] = (__int64)&v35;
  }
}

```

## disassembly

```asm
0x140035158  mov     [rsp-8+arg_10], rbx
0x14003515d  push    rbp
0x14003515e  push    rsi
0x14003515f  push    rdi
0x140035160  push    r12
0x140035162  push    r13
0x140035164  push    r14
0x140035166  push    r15
0x140035168  lea     rbp, [rsp-1B0h]
0x140035170  sub     rsp, 2B0h
0x140035177  mov     rax, cs:__security_cookie
0x14003517e  xor     rax, rsp
0x140035181  mov     [rbp+1E0h+var_40], rax
0x140035188  mov     rdi, rdx
0x14003518b  mov     [rbp+1E0h+var_260], rdx
0x14003518f  mov     rbx, rcx
0x140035192  mov     [rsp+2E0h+var_268], rcx
0x140035197  xor     r14d, r14d
0x14003519a  mov     [rsp+2E0h+var_270], 4
0x1400351a2  xor     edx, edx; Val
0x1400351a4  mov     [rsp+2E0h+var_2A0], r14d
0x1400351a9  lea     rcx, [rbp+1E0h+SubKey]; void *
0x1400351ad  mov     [rsp+2E0h+hKey], r14
0x1400351b2  mov     r8d, 208h; Size
0x1400351b8  call    memset_0
0x1400351bd  lea     rax, [rsp+2E0h+var_298]
0x1400351c2  mov     [rbx], r14
0x1400351c5  mov     [rsp+2E0h+var_290], rax
0x1400351ca  lea     r9d, [r14+18h]; dwFlags
0x1400351ce  lea     rax, [rsp+2E0h+var_298]
0x1400351d3  mov     [rsp+2E0h+var_288], r14
0x1400351d8  mov     [rsp+2E0h+var_298], rax
0x1400351dd  lea     r8, aLastStationId_0; "Last Station Id"
0x1400351e4  lea     rax, [rsp+2E0h+var_270]
0x1400351e9  mov     [rsp+2E0h+Block], r14
0x1400351ee  mov     [rsp+2E0h+pcbData], rax; pcbData
0x1400351f3  lea     rdx, aSoftwareMicros_21; "SOFTWARE\\Microsoft\\Windows MultiPoint"...
0x1400351fa  lea     rax, [rsp+2E0h+var_2A0]
0x1400351ff  mov     [rdi], r14
0x140035202  mov     [rsp+2E0h+pvData], rax; pvData
0x140035207  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14003520e  mov     [rsp+2E0h+pdwType], r14; pdwType
0x140035213  mov     r13d, r14d
0x140035216  mov     r15d, r14d
0x140035219  call    cs:__imp_RegGetValueW
0x14003521f  lea     esi, [r14+1]
0x140035223  mov     ebx, eax
0x140035225  cmp     [rsp+2E0h+var_2A0], esi
0x140035229  jb      loc_140035544
0x14003522f  mov     edi, 80000000h
0x140035234  mov     r12d, 80070057h
0x14003523a  mov     rcx, [rsp+2E0h+hKey]; hKey
0x14003523f  test    rcx, rcx
0x140035242  jz      short loc_14003524F
0x140035244  call    cs:__imp_RegCloseKey
0x14003524a  mov     [rsp+2E0h+hKey], r14
0x14003524f  mov     r9d, esi
0x140035252  lea     r8, aSoftwareMicros_22; "SOFTWARE\\Microsoft\\Windows MultiPoint"...
0x140035259  mov     edx, 104h; unsigned __int64
0x14003525e  lea     rcx, [rbp+1E0h+SubKey]; unsigned __int16 *
0x140035262  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140035267  mov     ebx, eax
0x140035269  test    eax, eax
0x14003526b  js      loc_140035901
0x140035271  lea     rax, [rsp+2E0h+hKey]
0x140035276  mov     r9d, 20019h; samDesired
0x14003527c  xor     r8d, r8d; ulOptions
0x14003527f  mov     [rsp+2E0h+pdwType], rax; phkResult
0x140035284  lea     rdx, [rbp+1E0h+SubKey]; lpSubKey
0x140035288  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14003528f  call    cs:__imp_RegOpenKeyExW
0x140035295  test    eax, eax
0x140035297  jz      short loc_1400352B1
0x140035299  cmp     eax, 2
0x14003529c  jz      loc_1400353F4
0x1400352a2  test    eax, eax
0x1400352a4  jg      loc_1400354C8
0x1400352aa  mov     ebx, eax
0x1400352ac  jmp     loc_1400354D1
0x1400352b1  mov     rdx, [rsp+2E0h+hKey]
0x1400352b6  lea     r9, [rsp+2E0h+Block]
0x1400352bb  lea     r8, aVirtualMachine_0; "Virtual Machine Id"
0x1400352c2  mov     ecx, 1
0x1400352c7  call    ?GetStringValue@RegUtil@@YAJW4EValueRequired@1@PEAUHKEY__@@PEBGPEAPEAG@Z; RegUtil::GetStringValue(RegUtil::EValueRequired,HKEY__ *,ushort const *,ushort * *)
0x1400352cc  mov     ebx, eax
0x1400352ce  add     eax, edi
0x1400352d0  test    edi, eax
0x1400352d2  jnz     short loc_1400352E0
0x1400352d4  cmp     ebx, 80070002h
0x1400352da  jnz     loc_1400355FF
0x1400352e0  cmp     ebx, 80070002h
0x1400352e6  jz      loc_1400353F4
0x1400352ec  mov     rdi, [rsp+2E0h+Block]
0x1400352f1  test    rdi, rdi
0x1400352f4  jz      loc_1400356C8
0x1400352fa  mov     ecx, 7FFFFFFFh
0x1400352ff  mov     rax, rdi
0x140035302  mov     edx, ecx
0x140035304  cmp     [rax], r14w
0x140035308  jz      short loc_140035314
0x14003530a  add     rax, 2
0x14003530e  sub     rdx, 1
0x140035312  jnz     short loc_140035304
0x140035314  mov     rax, rdx
0x140035317  neg     rax
0x14003531a  mov     rax, rdx
0x14003531d  sbb     ebx, ebx
0x14003531f  sub     rcx, rdx
0x140035322  not     ebx
0x140035324  and     ebx, r12d
0x140035327  neg     rax
0x14003532a  sbb     r8, r8
0x14003532d  and     r8, rcx
0x140035330  test    rdx, rdx
0x140035333  jz      loc_1400356C3
0x140035339  test    r8, r8
0x14003533c  jz      loc_1400353E2
0x140035342  mov     ecx, 218h; Size
0x140035347  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003534c  mov     rdx, rax
0x14003534f  test    rax, rax
0x140035352  jz      loc_140035614
0x140035358  mov     eax, 7FFFFFFEh
0x14003535d  lea     r9, [rdx+10h]
0x140035361  mov     rcx, rdi
0x140035364  mov     r8d, 104h
0x14003536a  test    rax, rax
0x14003536d  jz      short loc_14003538E
0x14003536f  movzx   r10d, word ptr [rcx]
0x140035373  test    r10w, r10w
0x140035377  jz      short loc_14003538E
0x140035379  mov     [r9], r10w
0x14003537d  add     rcx, 2
0x140035381  add     r9, 2
0x140035385  dec     rax
0x140035388  sub     r8, 1
0x14003538c  jnz     short loc_14003536A
0x14003538e  mov     rax, r8
0x140035391  lea     rcx, [r9-2]
0x140035395  neg     rax
0x140035398  sbb     ebx, ebx
0x14003539a  not     ebx
0x14003539c  and     ebx, 8007007Ah
0x1400353a2  test    r8, r8
0x1400353a5  cmovnz  rcx, r9
0x1400353a9  mov     [rcx], r14w
0x1400353ad  jz      loc_140035609
0x1400353b3  mov     rax, [rsp+2E0h+var_290]
0x1400353b8  lea     rcx, [rsp+2E0h+var_298]
0x1400353bd  cmp     [rax], rcx
0x1400353c0  jnz     loc_1400359A1
0x1400353c6  mov     [rdx+8], rax
0x1400353ca  lea     rcx, [rsp+2E0h+var_298]
0x1400353cf  mov     [rdx], rcx
0x1400353d2  inc     r13
0x1400353d5  mov     [rax], rdx
0x1400353d8  mov     [rsp+2E0h+var_290], rdx
0x1400353dd  mov     [rsp+2E0h+var_288], r13
0x1400353e2  mov     rcx, rdi; Block
0x1400353e5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400353ea  mov     [rsp+2E0h+Block], r14
0x1400353ef  mov     edi, 80000000h
0x1400353f4  inc     esi
0x1400353f6  cmp     esi, [rsp+2E0h+var_2A0]
0x1400353fa  jbe     loc_14003523A
0x140035400  test    r13, r13
0x140035403  jz      loc_140035544
0x140035409  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140035410  mov     eax, 8
0x140035415  mul     r13
0x140035418  cmovb   rax, rcx
0x14003541c  mov     rcx, rax; Size
0x14003541f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140035424  mov     r15, rax
0x140035427  test    rax, rax
0x14003542a  jnz     loc_140035755
0x140035430  mov     r14d, 8007000Eh
0x140035436  lea     rax, aPbstrmachineid; "pbstrMachineIds"
0x14003543d  lea     r12, aCpr; "CPR"
0x140035444  mov     dword ptr [rsp+2E0h+pvData], r14d; int
0x140035449  lea     rsi, aCupdatevmdomai_17; "CUpdateVmDomainAccountsHostThread::s_Ge"...
0x140035450  mov     [rsp+2E0h+pdwType], rax; unsigned __int16 *
0x140035455  mov     r13d, 82h
0x14003545b  lea     rdi, aTermsrvWmsSrcD_8; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x140035462  mov     r9, r12; unsigned __int16 *
0x140035465  mov     r8, rsi; unsigned __int16 *
0x140035468  mov     edx, r13d; unsigned int
0x14003546b  mov     rcx, rdi; unsigned __int16 *
0x14003546e  mov     ebx, r14d
0x140035471  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140035476  call    cs:__imp_IsDebuggerPresent
0x14003547c  test    eax, eax
0x14003547e  lea     rax, aPbstrmachineid; "pbstrMachineIds"
0x140035485  jz      loc_14003572C
0x14003548b  mov     [rsp+2E0h+var_2A8], r14d
0x140035490  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140035497  mov     [rsp+2E0h+pcbData], rax
0x14003549c  lea     ecx, [r15+2]; unsigned __int8
0x1400354a0  mov     [rsp+2E0h+pvData], r12
0x1400354a5  mov     r9d, r13d
0x1400354a8  mov     r8, rdi
0x1400354ab  mov     [rsp+2E0h+pdwType], rsi
0x1400354b0  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400354b5  mov     r13, r15
0x1400354b8  mov     rsi, [rsp+2E0h+var_288]
0x1400354bd  xor     r14d, r14d
0x1400354c0  mov     edi, r14d
0x1400354c3  jmp     loc_14003555B
0x1400354c8  movzx   ebx, ax
0x1400354cb  or      ebx, 80070000h
0x1400354d1  lea     r13, aCbraex; "CBRAEx"
0x1400354d8  mov     dword ptr [rsp+2E0h+pvData], ebx; int
0x1400354dc  lea     rsi, aCupdatevmdomai_17; "CUpdateVmDomainAccountsHostThread::s_Ge"...
0x1400354e3  mov     r15d, 5Fh ; '_'
0x1400354e9  lea     rdi, aTermsrvWmsSrcD_8; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x1400354f0  mov     r9, r13; unsigned __int16 *
0x1400354f3  lea     r12, aLr0lLr2l_0; "lr == 0L || lr == 2L"
0x1400354fa  mov     r8, rsi; unsigned __int16 *
0x1400354fd  mov     edx, r15d; unsigned int
0x140035500  mov     [rsp+2E0h+pdwType], r12; unsigned __int16 *
0x140035505  mov     rcx, rdi; unsigned __int16 *
0x140035508  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14003550d  call    cs:__imp_IsDebuggerPresent
0x140035513  test    eax, eax
0x140035515  jz      loc_1400355D7
0x14003551b  mov     [rsp+2E0h+var_2A8], ebx
0x14003551f  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140035526  mov     [rsp+2E0h+pcbData], r12
0x14003552b  lea     ecx, [r15-5Dh]; unsigned __int8
0x14003552f  mov     [rsp+2E0h+pvData], r13
0x140035534  mov     r9d, r15d
0x140035537  mov     r8, rdi
0x14003553a  mov     [rsp+2E0h+pdwType], rsi
0x14003553f  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140035544  mov     r15, r14
0x140035547  test    ebx, ebx
0x140035549  jns     short loc_140035579
0x14003554b  mov     rsi, [rsp+2E0h+var_288]
0x140035550  mov     r13, r15
0x140035553  mov     edi, r14d
0x140035556  test    rsi, rsi
0x140035559  jz      short loc_140035571
0x14003555b  mov     ecx, edi
0x14003555d  mov     rcx, [r13+rcx*8+0]; bstrString
0x140035562  call    cs:__imp_SysFreeString
0x140035568  inc     edi
0x14003556a  mov     eax, edi
0x14003556c  cmp     rax, rsi
0x14003556f  jb      short loc_14003555B
0x140035571  mov     rcx, r15; Block
0x140035574  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140035579  mov     rcx, [rsp+2E0h+hKey]; hKey
0x14003557e  test    rcx, rcx
0x140035581  jz      short loc_14003558E
0x140035583  call    cs:__imp_RegCloseKey
0x140035589  mov     [rsp+2E0h+hKey], r14
0x14003558e  mov     rcx, [rsp+2E0h+Block]; Block
0x140035593  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140035598  mov     rcx, [rsp+2E0h+var_298]
0x14003559d  lea     rax, [rsp+2E0h+var_298]
0x1400355a2  cmp     rcx, rax
0x1400355a5  jz      loc_1400359A8
0x1400355ab  lea     rax, [rsp+2E0h+var_298]
0x1400355b0  cmp     [rcx+8], rax
0x1400355b4  jnz     loc_1400359A1
0x1400355ba  mov     rax, [rcx]
0x1400355bd  cmp     [rax+8], rcx
0x1400355c1  jnz     loc_1400359A1
0x1400355c7  lea     rdx, [rsp+2E0h+var_298]
0x1400355cc  mov     [rsp+2E0h+var_298], rax
0x1400355d1  mov     [rax+8], rdx
0x1400355d5  jmp     short loc_140035593
0x1400355d7  mov     dword ptr [rsp+2E0h+pcbData], ebx
0x1400355db  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400355e2  mov     [rsp+2E0h+pvData], r12
0x1400355e7  mov     r9, rsi
0x1400355ea  mov     r8d, r15d
0x1400355ed  mov     [rsp+2E0h+pdwType], r13
0x1400355f2  mov     rdx, rdi
0x1400355f5  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400355fa  jmp     loc_140035544
0x1400355ff  mov     ebx, 80004005h
0x140035604  jmp     loc_14003554B
0x140035609  mov     r12d, 76h ; 'v'
0x14003560f  jmp     loc_140035907
0x140035614  mov     r14d, 8007000Eh
0x14003561a  lea     rax, aPmachineidnode; "pMachineIdNode"
0x140035621  lea     r12, aCpr; "CPR"
0x140035628  mov     dword ptr [rsp+2E0h+pvData], r14d; int
0x14003562d  lea     rsi, aCupdatevmdomai_17; "CUpdateVmDomainAccountsHostThread::s_Ge"...
0x140035634  mov     [rsp+2E0h+pdwType], rax; unsigned __int16 *
0x140035639  mov     r13d, 73h ; 's'
0x14003563f  lea     rdi, aTermsrvWmsSrcD_8; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x140035646  mov     r9, r12; unsigned __int16 *
0x140035649  mov     r8, rsi; unsigned __int16 *
0x14003564c  mov     edx, r13d; unsigned int
0x14003564f  mov     rcx, rdi; unsigned __int16 *
0x140035652  mov     ebx, r14d
0x140035655  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14003565a  call    cs:__imp_IsDebuggerPresent
  ... truncated ...
```
