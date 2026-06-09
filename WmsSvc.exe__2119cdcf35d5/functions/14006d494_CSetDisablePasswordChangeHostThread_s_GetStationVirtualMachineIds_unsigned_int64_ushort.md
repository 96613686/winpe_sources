# CSetDisablePasswordChangeHostThread::s_GetStationVirtualMachineIds(unsigned __int64 *,ushort * * *)

- ea: `0x14006d494`
- end: `0x14006dce9`
- name: `?s_GetStationVirtualMachineIds@CSetDisablePasswordChangeHostThread@@KAJPEA_KPEAPEAPEAG@Z`
- size: `2133`
- prototype: `__int64 __fastcall(unsigned __int64 *, unsigned __int16 ***)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14006ce04`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x1400033e8`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c290`
- `0x14005c408`
- `0x140061a0c`
- `0x14006d494`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14006d5cb`
- `ADVAPI32!RegOpenKeyExW` at `0x14006d5cb`
- `ADVAPI32!RegGetValueW` at `0x14006d555`
- `ADVAPI32!RegGetValueW` at `0x14006d555`
- `ADVAPI32!RegCloseKey` at `0x14006d580`
- `ADVAPI32!RegCloseKey` at `0x14006d8b1`
- `ADVAPI32!RegCloseKey` at `0x14006d580`
- `ADVAPI32!RegCloseKey` at `0x14006d8b1`
- `KERNEL32!IsDebuggerPresent` at `0x14006d7a4`
- `KERNEL32!IsDebuggerPresent` at `0x14006d83b`
- `KERNEL32!IsDebuggerPresent` at `0x14006d976`
- `KERNEL32!IsDebuggerPresent` at `0x14006da24`
- `KERNEL32!IsDebuggerPresent` at `0x14006dac3`
- `KERNEL32!IsDebuggerPresent` at `0x14006dbad`
- `KERNEL32!IsDebuggerPresent` at `0x14006dc59`
- `KERNEL32!IsDebuggerPresent` at `0x14006d7a4`
- `KERNEL32!IsDebuggerPresent` at `0x14006d83b`
- `KERNEL32!IsDebuggerPresent` at `0x14006d976`
- `KERNEL32!IsDebuggerPresent` at `0x14006da24`
- `KERNEL32!IsDebuggerPresent` at `0x14006dac3`
- `KERNEL32!IsDebuggerPresent` at `0x14006dbad`
- `KERNEL32!IsDebuggerPresent` at `0x14006dc59`
- `OLEAUT32!__imp_SysAllocString` at `0x14006db32`
- `OLEAUT32!__imp_SysAllocString` at `0x14006db32`
- `OLEAUT32!__imp_SysFreeString` at `0x14006d890`
- `OLEAUT32!__imp_SysFreeString` at `0x14006d890`

## string_xrefs

- `0x14006d777`: `CSetDisablePasswordChangeHostThread::s_GetStationVirtualMachineIds`
- `0x14006d80a`: `CSetDisablePasswordChangeHostThread::s_GetStationVirtualMachineIds`
- `0x14006d949`: `CSetDisablePasswordChangeHostThread::s_GetStationVirtualMachineIds`
- `0x14006d9f3`: `CSetDisablePasswordChangeHostThread::s_GetStationVirtualMachineIds`
- `0x14006da87`: `CSetDisablePasswordChangeHostThread::s_GetStationVirtualMachineIds`
- `0x14006dc23`: `CSetDisablePasswordChangeHostThread::s_GetStationVirtualMachineIds`
- `0x14006d789`: `termsrv\wms\src\common\srcutils\setdisablepasswordchangehostthread.cpp`
- `0x14006d817`: `termsrv\wms\src\common\srcutils\setdisablepasswordchangehostthread.cpp`
- `0x14006d95b`: `termsrv\wms\src\common\srcutils\setdisablepasswordchangehostthread.cpp`
- `0x14006da00`: `termsrv\wms\src\common\srcutils\setdisablepasswordchangehostthread.cpp`
- `0x14006da8e`: `termsrv\wms\src\common\srcutils\setdisablepasswordchangehostthread.cpp`
- `0x14006dc38`: `termsrv\wms\src\common\srcutils\setdisablepasswordchangehostthread.cpp`

## pseudocode

```c
__int64 __fastcall CSetDisablePasswordChangeHostThread::s_GetStationVirtualMachineIds(
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
  const OLECHAR ***v12; // rdx
  __int64 v13; // rax
  _WORD *v14; // r9
  _WORD *v15; // rcx
  __int64 v16; // r8
  _WORD *v17; // rcx
  const OLECHAR **v18; // rax
  const unsigned __int16 *v19; // r9
  _QWORD *v20; // r13
  unsigned __int64 v21; // rsi
  unsigned int v22; // edi
  _QWORD *i; // rcx
  unsigned int v24; // r12d
  __int64 v25; // r9
  __int64 v26; // r8
  unsigned int v27; // r12d
  const OLECHAR *v28; // r14
  BSTR v29; // rax
  LPDWORD pcbData; // [rsp+30h] [rbp-D0h]
  int v32; // [rsp+38h] [rbp-C8h]
  unsigned int pvData; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v34; // [rsp+48h] [rbp-B8h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  const OLECHAR *v36; // [rsp+58h] [rbp-A8h] BYREF
  const OLECHAR **v37; // [rsp+60h] [rbp-A0h]
  void *Block; // [rsp+68h] [rbp-98h] BYREF
  DWORD v39; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 *v40; // [rsp+78h] [rbp-88h]
  unsigned __int16 ***v41; // [rsp+80h] [rbp-80h]
  WCHAR SubKey[264]; // [rsp+90h] [rbp-70h] BYREF

  v41 = a2;
  v40 = a1;
  v39 = 4;
  pvData = 0;
  hKey = 0;
  memset_0(SubKey, 0, 0x208u);
  *a1 = 0;
  v37 = &v36;
  v34 = 0;
  v36 = (const OLECHAR *)&v36;
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
             &v39);
  if ( !pvData )
    goto LABEL_38;
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
      v24 = 93;
LABEL_72:
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\setdisablepasswordchangehostthread.cpp",
        v24,
        L"CSetDisablePasswordChangeHostThread::s_GetStationVirtualMachineIds",
        L"CHRA",
        L"hr",
        ValueW);
      if ( !IsDebuggerPresent() )
      {
        LODWORD(pcbData) = ValueW;
        v26 = v24;
        goto LABEL_76;
      }
      v32 = ValueW;
      v25 = v24;
LABEL_74:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\setdisablepasswordchangehostthread.cpp",
        v25,
        L"CSetDisablePasswordChangeHostThread::s_GetStationVirtualMachineIds",
        L"CHRA",
        L"hr",
        v32);
LABEL_77:
      v5 = 0;
      goto LABEL_39;
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
          L"termsrv\\wms\\src\\common\\srcutils\\setdisablepasswordchangehostthread.cpp",
          0x60u,
          L"CSetDisablePasswordChangeHostThread::s_GetStationVirtualMachineIds",
          L"CBRAEx",
          L"lr == 0L || lr == 2L",
          ValueW);
        if ( IsDebuggerPresent() )
        {
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
            L"termsrv\\wms\\src\\common\\srcutils\\setdisablepasswordchangehostthread.cpp",
            96,
            L"CSetDisablePasswordChangeHostThread::s_GetStationVirtualMachineIds",
            L"CBRAEx",
            L"lr == 0L || lr == 2L",
            ValueW);
        }
        else
        {
          LODWORD(pcbData) = ValueW;
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\common\\srcutils\\setdisablepasswordchangehostthread.cpp",
            96,
            L"CSetDisablePasswordChangeHostThread::s_GetStationVirtualMachineIds",
            L"CBRAEx",
            L"lr == 0L || lr == 2L",
            pcbData);
        }
        goto LABEL_38;
      }
    }
    else
    {
      ValueW = RegUtil::GetStringValue(1, hKey, L"Virtual Machine Id", &Block);
      if ( ((ValueW + 0x80000000) & 0x80000000) == 0 && ValueW != -2147024894 )
      {
        ValueW = -2147467259;
        goto LABEL_39;
      }
      if ( ValueW == -2147024894 )
        goto LABEL_28;
      v9 = Block;
      if ( !Block )
      {
        ValueW = -2147024809;
LABEL_55:
        LOGASSERTHR(
          L"termsrv\\wms\\src\\common\\srcutils\\setdisablepasswordchangehostthread.cpp",
          0x6Fu,
          L"CSetDisablePasswordChangeHostThread::s_GetStationVirtualMachineIds",
          L"CHRA",
          L"hr",
          -2147024809);
        if ( IsDebuggerPresent() )
        {
          v32 = -2147024809;
          v25 = 111;
          goto LABEL_74;
        }
        LODWORD(pcbData) = -2147024809;
        v26 = 111;
LABEL_76:
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\srcutils\\setdisablepasswordchangehostthread.cpp",
          v26,
          L"CSetDisablePasswordChangeHostThread::s_GetStationVirtualMachineIds",
          L"CHRA",
          L"hr",
          pcbData);
        goto LABEL_77;
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
        goto LABEL_55;
      if ( ((0x7FFFFFFF - v11) & -(__int64)(v11 != 0)) != 0 )
      {
        v12 = (const OLECHAR ***)operator new(0x218u);
        if ( !v12 )
        {
          ValueW = -2147024882;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\common\\srcutils\\setdisablepasswordchangehostthread.cpp",
            0x74u,
            L"CSetDisablePasswordChangeHostThread::s_GetStationVirtualMachineIds",
            L"CPR",
            L"pMachineIdNode",
            -2147024882);
          if ( IsDebuggerPresent() )
          {
            DEBUGMSGLEVEL(
              2u,
              L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
              L"termsrv\\wms\\src\\common\\srcutils\\setdisablepasswordchangehostthread.cpp",
              116,
              L"CSetDisablePasswordChangeHostThread::s_GetStationVirtualMachineIds",
              L"CPR",
              L"pMachineIdNode",
              -2147024882);
          }
          else
          {
            LODWORD(pcbData) = -2147024882;
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
              L"termsrv\\wms\\src\\common\\srcutils\\setdisablepasswordchangehostthread.cpp",
              116,
              L"CSetDisablePasswordChangeHostThread::s_GetStationVirtualMachineIds",
              L"CPR",
              L"pMachineIdNode",
              pcbData);
          }
          goto LABEL_39;
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
          v24 = 119;
          goto LABEL_72;
        }
        v18 = v37;
        *v12 = &v36;
        ++v4;
        v12[1] = v18;
        v34 = v4;
        *v18 = (const OLECHAR *)v12;
        v37 = (const OLECHAR **)v12;
      }
      operator delete(v9);
      Block = 0;
    }
LABEL_28:
    ++v6;
  }
  while ( v6 <= pvData );
  if ( !v4 )
    goto LABEL_38;
  v5 = operator new(saturated_mul(v4, 8u));
  if ( v5 )
  {
    v27 = 0;
    v28 = v36;
    if ( v36 != (const OLECHAR *)&v36 )
    {
      while ( v27 < (unsigned int)v4 )
      {
        if ( !v28 )
        {
          LOGASSERT(
            L"termsrv\\wms\\src\\common\\srcutils\\setdisablepasswordchangehostthread.cpp",
            0x89u,
            L"CSetDisablePasswordChangeHostThread::s_GetStationVirtualMachineIds",
            v19,
            L"pMachineIdNode != NULL");
          if ( IsDebuggerPresent() )
            DEBUGMSGLEVEL(
              2u,
              L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
              L"termsrv\\wms\\src\\common\\srcutils\\setdisablepasswordchangehostthread.cpp",
              137,
              L"CSetDisablePasswordChangeHostThread::s_GetStationVirtualMachineIds",
              L"ASSERT",
              L"pMachineIdNode != NULL");
          else
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
              L"termsrv\\wms\\src\\common\\srcutils\\setdisablepasswordchangehostthread.cpp",
              137,
              L"CSetDisablePasswordChangeHostThread::s_GetStationVirtualMachineIds",
              L"ASSERT",
              L"pMachineIdNode != NULL");
        }
        v29 = SysAllocString(v28 + 8);
        v5[v27] = v29;
        if ( !v29 )
        {
          v20 = v5;
          ValueW = -2147024882;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\common\\srcutils\\setdisablepasswordchangehostthread.cpp",
            0x8Cu,
            L"CSetDisablePasswordChangeHostThread::s_GetStationVirtualMachineIds",
            L"CPR",
            L"pbstrMachineIds[idx]",
            -2147024882);
          if ( IsDebuggerPresent() )
          {
            DEBUGMSGLEVEL(
              2u,
              L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
              L"termsrv\\wms\\src\\common\\srcutils\\setdisablepasswordchangehostthread.cpp",
              140,
              L"CSetDisablePasswordChangeHostThread::s_GetStationVirtualMachineIds",
              L"CPR",
              L"pbstrMachineIds[idx]",
              -2147024882);
          }
          else
          {
            LODWORD(pcbData) = -2147024882;
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
              L"termsrv\\wms\\src\\common\\srcutils\\setdisablepasswordchangehostthread.cpp",
              140,
              L"CSetDisablePasswordChangeHostThread::s_GetStationVirtualMachineIds",
              L"CPR",
              L"pbstrMachineIds[idx]",
              pcbData);
          }
          goto LABEL_34;
        }
        v28 = *(const OLECHAR **)v28;
        ++v27;
        if ( v28 == (const OLECHAR *)&v36 )
          break;
      }
    }
    *v40 = v4;
    *v41 = (unsigned __int16 **)v5;
LABEL_38:
    v5 = 0;
    if ( ValueW >= 0 )
      goto LABEL_42;
LABEL_39:
    v21 = v34;
    v20 = 0;
    v22 = 0;
    if ( v34 )
      goto LABEL_40;
    goto LABEL_41;
  }
  ValueW = -2147024882;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\common\\srcutils\\setdisablepasswordchangehostthread.cpp",
    0x83u,
    L"CSetDisablePasswordChangeHostThread::s_GetStationVirtualMachineIds",
    L"CPR",
    L"pbstrMachineIds",
    -2147024882);
  if ( IsDebuggerPresent() )
  {
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\common\\srcutils\\setdisablepasswordchangehostthread.cpp",
      131,
      L"CSetDisablePasswordChangeHostThread::s_GetStationVirtualMachineIds",
      L"CPR",
      L"pbstrMachineIds",
      -2147024882);
  }
  else
  {
    LODWORD(pcbData) = -2147024882;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\setdisablepasswordchangehostthread.cpp",
      131,
      L"CSetDisablePasswordChangeHostThread::s_GetStationVirtualMachineIds",
      L"CPR",
      L"pbstrMachineIds",
      pcbData);
  }
  v20 = 0;
LABEL_34:
  v21 = v34;
  v22 = 0;
  do
LABEL_40:
    SysFreeString((BSTR)v20[v22++]);
  while ( v22 < v21 );
LABEL_41:
  operator delete(v5);
LABEL_42:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  for ( i = Block; ; i[1] = 0 )
  {
    operator delete(i);
    i = v36;
    if ( v36 == (const OLECHAR *)&v36 )
      break;
    v36 = *(const OLECHAR **)v36;
    *((_QWORD *)v36 + 1) = &v36;
    *i = 0;
  }
  return (unsigned int)ValueW;
}

```

## disassembly

```asm
0x14006d494  mov     [rsp-8+arg_10], rbx
0x14006d499  push    rbp
0x14006d49a  push    rsi
0x14006d49b  push    rdi
0x14006d49c  push    r12
0x14006d49e  push    r13
0x14006d4a0  push    r14
0x14006d4a2  push    r15
0x14006d4a4  lea     rbp, [rsp-1B0h]
0x14006d4ac  sub     rsp, 2B0h
0x14006d4b3  mov     rax, cs:__security_cookie
0x14006d4ba  xor     rax, rsp
0x14006d4bd  mov     [rbp+1E0h+var_40], rax
0x14006d4c4  mov     rdi, rdx
0x14006d4c7  mov     [rbp+1E0h+var_260], rdx
0x14006d4cb  mov     rbx, rcx
0x14006d4ce  mov     [rsp+2E0h+var_268], rcx
0x14006d4d3  xor     r14d, r14d
0x14006d4d6  mov     [rsp+2E0h+var_270], 4
0x14006d4de  xor     edx, edx; Val
0x14006d4e0  mov     [rsp+2E0h+var_2A0], r14d
0x14006d4e5  lea     rcx, [rbp+1E0h+SubKey]; void *
0x14006d4e9  mov     [rsp+2E0h+hKey], r14
0x14006d4ee  mov     r8d, 208h; Size
0x14006d4f4  call    memset_0
0x14006d4f9  lea     rax, [rsp+2E0h+var_288]
0x14006d4fe  mov     [rbx], r14
0x14006d501  mov     [rsp+2E0h+var_280], rax
0x14006d506  lea     r9d, [r14+18h]; dwFlags
0x14006d50a  lea     rax, [rsp+2E0h+var_288]
0x14006d50f  mov     [rsp+2E0h+var_298], r14
0x14006d514  mov     [rsp+2E0h+var_288], rax
0x14006d519  lea     r8, aLastStationId_1; "Last Station Id"
0x14006d520  lea     rax, [rsp+2E0h+var_270]
0x14006d525  mov     [rsp+2E0h+Block], r14
0x14006d52a  mov     [rsp+2E0h+pcbData], rax; pcbData
0x14006d52f  lea     rdx, aSoftwareMicros_36; "SOFTWARE\\Microsoft\\Windows MultiPoint"...
0x14006d536  lea     rax, [rsp+2E0h+var_2A0]
0x14006d53b  mov     [rdi], r14
0x14006d53e  mov     [rsp+2E0h+pvData], rax; pvData
0x14006d543  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14006d54a  mov     [rsp+2E0h+pdwType], r14; pdwType
0x14006d54f  mov     r13d, r14d
0x14006d552  mov     r15d, r14d
0x14006d555  call    cs:__imp_RegGetValueW
0x14006d55b  lea     esi, [r14+1]
0x14006d55f  mov     ebx, eax
0x14006d561  cmp     [rsp+2E0h+var_2A0], esi
0x14006d565  jb      loc_14006D872
0x14006d56b  mov     edi, 80000000h
0x14006d570  mov     r12d, 80070057h
0x14006d576  mov     rcx, [rsp+2E0h+hKey]; hKey
0x14006d57b  test    rcx, rcx
0x14006d57e  jz      short loc_14006D58B
0x14006d580  call    cs:__imp_RegCloseKey
0x14006d586  mov     [rsp+2E0h+hKey], r14
0x14006d58b  mov     r9d, esi
0x14006d58e  lea     r8, aSoftwareMicros_37; "SOFTWARE\\Microsoft\\Windows MultiPoint"...
0x14006d595  mov     edx, 104h; unsigned __int64
0x14006d59a  lea     rcx, [rbp+1E0h+SubKey]; unsigned __int16 *
0x14006d59e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14006d5a3  mov     ebx, eax
0x14006d5a5  test    eax, eax
0x14006d5a7  js      loc_14006DC1D
0x14006d5ad  lea     rax, [rsp+2E0h+hKey]
0x14006d5b2  mov     r9d, 20019h; samDesired
0x14006d5b8  xor     r8d, r8d; ulOptions
0x14006d5bb  mov     [rsp+2E0h+pdwType], rax; phkResult
0x14006d5c0  lea     rdx, [rbp+1E0h+SubKey]; lpSubKey
0x14006d5c4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14006d5cb  call    cs:__imp_RegOpenKeyExW
0x14006d5d1  test    eax, eax
0x14006d5d3  jz      short loc_14006D5ED
0x14006d5d5  cmp     eax, 2
0x14006d5d8  jz      loc_14006D722
0x14006d5de  test    eax, eax
0x14006d5e0  jg      loc_14006D7F6
0x14006d5e6  mov     ebx, eax
0x14006d5e8  jmp     loc_14006D7FF
0x14006d5ed  mov     rdx, [rsp+2E0h+hKey]
0x14006d5f2  lea     r9, [rsp+2E0h+Block]
0x14006d5f7  lea     r8, aVirtualMachine_1; "Virtual Machine Id"
0x14006d5fe  mov     ecx, 1
0x14006d603  call    ?GetStringValue@RegUtil@@YAJW4EValueRequired@1@PEAUHKEY__@@PEBGPEAPEAG@Z; RegUtil::GetStringValue(RegUtil::EValueRequired,HKEY__ *,ushort const *,ushort * *)
0x14006d608  mov     ebx, eax
0x14006d60a  add     eax, edi
0x14006d60c  test    edi, eax
0x14006d60e  jnz     short loc_14006D61C
0x14006d610  cmp     ebx, 80070002h
0x14006d616  jnz     loc_14006D91B
0x14006d61c  cmp     ebx, 80070002h
0x14006d622  jz      loc_14006D722
0x14006d628  mov     rdi, [rsp+2E0h+Block]
0x14006d62d  test    rdi, rdi
0x14006d630  jz      loc_14006D9E4
0x14006d636  mov     ecx, 7FFFFFFFh
0x14006d63b  mov     rax, rdi
0x14006d63e  mov     edx, ecx
0x14006d640  cmp     [rax], r14w
0x14006d644  jz      short loc_14006D650
0x14006d646  add     rax, 2
0x14006d64a  sub     rdx, 1
0x14006d64e  jnz     short loc_14006D640
0x14006d650  mov     rax, rdx
0x14006d653  neg     rax
0x14006d656  mov     rax, rdx
0x14006d659  sbb     ebx, ebx
0x14006d65b  sub     rcx, rdx
0x14006d65e  not     ebx
0x14006d660  and     ebx, r12d
0x14006d663  neg     rax
0x14006d666  sbb     r8, r8
0x14006d669  and     r8, rcx
0x14006d66c  test    rdx, rdx
0x14006d66f  jz      loc_14006D9DF
0x14006d675  test    r8, r8
0x14006d678  jz      loc_14006D710
0x14006d67e  mov     ecx, 218h; Size
0x14006d683  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14006d688  mov     rdx, rax
0x14006d68b  test    rax, rax
0x14006d68e  jz      loc_14006D930
0x14006d694  mov     eax, 7FFFFFFEh
0x14006d699  lea     r9, [rdx+10h]
0x14006d69d  mov     rcx, rdi
0x14006d6a0  mov     r8d, 104h
0x14006d6a6  test    rax, rax
0x14006d6a9  jz      short loc_14006D6CA
0x14006d6ab  movzx   r10d, word ptr [rcx]
0x14006d6af  test    r10w, r10w
0x14006d6b3  jz      short loc_14006D6CA
0x14006d6b5  mov     [r9], r10w
0x14006d6b9  add     rcx, 2
0x14006d6bd  add     r9, 2
0x14006d6c1  dec     rax
0x14006d6c4  sub     r8, 1
0x14006d6c8  jnz     short loc_14006D6A6
0x14006d6ca  mov     rax, r8
0x14006d6cd  lea     rcx, [r9-2]
0x14006d6d1  neg     rax
0x14006d6d4  sbb     ebx, ebx
0x14006d6d6  not     ebx
0x14006d6d8  and     ebx, 8007007Ah
0x14006d6de  test    r8, r8
0x14006d6e1  cmovnz  rcx, r9
0x14006d6e5  mov     [rcx], r14w
0x14006d6e9  jz      loc_14006D925
0x14006d6ef  mov     rax, [rsp+2E0h+var_280]
0x14006d6f4  lea     rcx, [rsp+2E0h+var_288]
0x14006d6f9  mov     [rdx], rcx
0x14006d6fc  inc     r13
0x14006d6ff  mov     [rdx+8], rax
0x14006d703  mov     [rsp+2E0h+var_298], r13
0x14006d708  mov     [rax], rdx
0x14006d70b  mov     [rsp+2E0h+var_280], rdx
0x14006d710  mov     rcx, rdi; Block
0x14006d713  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14006d718  mov     [rsp+2E0h+Block], r14
0x14006d71d  mov     edi, 80000000h
0x14006d722  inc     esi
0x14006d724  cmp     esi, [rsp+2E0h+var_2A0]
0x14006d728  jbe     loc_14006D576
0x14006d72e  test    r13, r13
0x14006d731  jz      loc_14006D872
0x14006d737  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14006d73e  mov     eax, 8
0x14006d743  mul     r13
0x14006d746  cmovb   rax, rcx
0x14006d74a  mov     rcx, rax; Size
0x14006d74d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14006d752  mov     r15, rax
0x14006d755  test    rax, rax
0x14006d758  jnz     loc_14006DA71
0x14006d75e  mov     r14d, 8007000Eh
0x14006d764  lea     rax, aPbstrmachineid; "pbstrMachineIds"
0x14006d76b  lea     r12, aCpr; "CPR"
0x14006d772  mov     dword ptr [rsp+2E0h+pvData], r14d; int
0x14006d777  lea     rsi, aCsetdisablepas_16; "CSetDisablePasswordChangeHostThread::s_"...
0x14006d77e  mov     [rsp+2E0h+pdwType], rax; unsigned __int16 *
0x14006d783  mov     r13d, 83h
0x14006d789  lea     rdi, aTermsrvWmsSrcC_2; "termsrv\\wms\\src\\common\\srcutils\\se"...
0x14006d790  mov     r9, r12; unsigned __int16 *
0x14006d793  mov     r8, rsi; unsigned __int16 *
0x14006d796  mov     edx, r13d; unsigned int
0x14006d799  mov     rcx, rdi; unsigned __int16 *
0x14006d79c  mov     ebx, r14d
0x14006d79f  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006d7a4  call    cs:__imp_IsDebuggerPresent
0x14006d7aa  test    eax, eax
0x14006d7ac  lea     rax, aPbstrmachineid; "pbstrMachineIds"
0x14006d7b3  jz      loc_14006DA48
0x14006d7b9  mov     [rsp+2E0h+var_2A8], r14d
0x14006d7be  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14006d7c5  mov     [rsp+2E0h+pcbData], rax
0x14006d7ca  lea     ecx, [r15+2]; unsigned __int8
0x14006d7ce  mov     [rsp+2E0h+pvData], r12
0x14006d7d3  mov     r9d, r13d
0x14006d7d6  mov     r8, rdi
0x14006d7d9  mov     [rsp+2E0h+pdwType], rsi
0x14006d7de  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14006d7e3  mov     r13, r15
0x14006d7e6  mov     rsi, [rsp+2E0h+var_298]
0x14006d7eb  xor     r14d, r14d
0x14006d7ee  mov     edi, r14d
0x14006d7f1  jmp     loc_14006D889
0x14006d7f6  movzx   ebx, ax
0x14006d7f9  or      ebx, 80070000h
0x14006d7ff  lea     r13, aCbraex; "CBRAEx"
0x14006d806  mov     dword ptr [rsp+2E0h+pvData], ebx; int
0x14006d80a  lea     rsi, aCsetdisablepas_16; "CSetDisablePasswordChangeHostThread::s_"...
0x14006d811  mov     r15d, 60h ; '`'
0x14006d817  lea     rdi, aTermsrvWmsSrcC_2; "termsrv\\wms\\src\\common\\srcutils\\se"...
0x14006d81e  mov     r9, r13; unsigned __int16 *
0x14006d821  lea     r12, aLr0lLr2l_0; "lr == 0L || lr == 2L"
0x14006d828  mov     r8, rsi; unsigned __int16 *
0x14006d82b  mov     edx, r15d; unsigned int
0x14006d82e  mov     [rsp+2E0h+pdwType], r12; unsigned __int16 *
0x14006d833  mov     rcx, rdi; unsigned __int16 *
0x14006d836  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006d83b  call    cs:__imp_IsDebuggerPresent
0x14006d841  test    eax, eax
0x14006d843  jz      loc_14006D8F3
0x14006d849  mov     [rsp+2E0h+var_2A8], ebx
0x14006d84d  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14006d854  mov     [rsp+2E0h+pcbData], r12
0x14006d859  lea     ecx, [r15-5Eh]; unsigned __int8
0x14006d85d  mov     [rsp+2E0h+pvData], r13
0x14006d862  mov     r9d, r15d
0x14006d865  mov     r8, rdi
0x14006d868  mov     [rsp+2E0h+pdwType], rsi
0x14006d86d  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14006d872  mov     r15, r14
0x14006d875  test    ebx, ebx
0x14006d877  jns     short loc_14006D8A7
0x14006d879  mov     rsi, [rsp+2E0h+var_298]
0x14006d87e  mov     r13, r15
0x14006d881  mov     edi, r14d
0x14006d884  test    rsi, rsi
0x14006d887  jz      short loc_14006D89F
0x14006d889  mov     ecx, edi
0x14006d88b  mov     rcx, [r13+rcx*8+0]; bstrString
0x14006d890  call    cs:__imp_SysFreeString
0x14006d896  inc     edi
0x14006d898  mov     eax, edi
0x14006d89a  cmp     rax, rsi
0x14006d89d  jb      short loc_14006D889
0x14006d89f  mov     rcx, r15; Block
0x14006d8a2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14006d8a7  mov     rcx, [rsp+2E0h+hKey]; hKey
0x14006d8ac  test    rcx, rcx
0x14006d8af  jz      short loc_14006D8BC
0x14006d8b1  call    cs:__imp_RegCloseKey
0x14006d8b7  mov     [rsp+2E0h+hKey], r14
0x14006d8bc  mov     rcx, [rsp+2E0h+Block]; Block
0x14006d8c1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14006d8c6  mov     rcx, [rsp+2E0h+var_288]
0x14006d8cb  lea     rax, [rsp+2E0h+var_288]
0x14006d8d0  cmp     rcx, rax
0x14006d8d3  jz      loc_14006DCBD
0x14006d8d9  mov     rax, [rcx]
0x14006d8dc  lea     rdx, [rsp+2E0h+var_288]
0x14006d8e1  mov     [rsp+2E0h+var_288], rax
0x14006d8e6  mov     [rax+8], rdx
0x14006d8ea  mov     [rcx], r14
0x14006d8ed  mov     [rcx+8], r14
0x14006d8f1  jmp     short loc_14006D8C1
0x14006d8f3  mov     dword ptr [rsp+2E0h+pcbData], ebx
0x14006d8f7  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14006d8fe  mov     [rsp+2E0h+pvData], r12
0x14006d903  mov     r9, rsi
0x14006d906  mov     r8d, r15d
0x14006d909  mov     [rsp+2E0h+pdwType], r13
0x14006d90e  mov     rdx, rdi
0x14006d911  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14006d916  jmp     loc_14006D872
0x14006d91b  mov     ebx, 80004005h
0x14006d920  jmp     loc_14006D879
0x14006d925  mov     r12d, 77h ; 'w'
0x14006d92b  jmp     loc_14006DC23
0x14006d930  mov     r14d, 8007000Eh
0x14006d936  lea     rax, aPmachineidnode; "pMachineIdNode"
0x14006d93d  lea     r12, aCpr; "CPR"
0x14006d944  mov     dword ptr [rsp+2E0h+pvData], r14d; int
0x14006d949  lea     rsi, aCsetdisablepas_16; "CSetDisablePasswordChangeHostThread::s_"...
0x14006d950  mov     [rsp+2E0h+pdwType], rax; unsigned __int16 *
0x14006d955  mov     r13d, 74h ; 't'
0x14006d95b  lea     rdi, aTermsrvWmsSrcC_2; "termsrv\\wms\\src\\common\\srcutils\\se"...
0x14006d962  mov     r9, r12; unsigned __int16 *
0x14006d965  mov     r8, rsi; unsigned __int16 *
0x14006d968  mov     edx, r13d; unsigned int
0x14006d96b  mov     rcx, rdi; unsigned __int16 *
0x14006d96e  mov     ebx, r14d
0x14006d971  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006d976  call    cs:__imp_IsDebuggerPresent
0x14006d97c  test    eax, eax
0x14006d97e  lea     rax, aPmachineidnode; "pMachineIdNode"
0x14006d985  jz      short loc_14006D9B9
0x14006d987  mov     [rsp+2E0h+var_2A8], r14d
0x14006d98c  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14006d993  mov     [rsp+2E0h+pcbData], rax
  ... truncated ...
```
