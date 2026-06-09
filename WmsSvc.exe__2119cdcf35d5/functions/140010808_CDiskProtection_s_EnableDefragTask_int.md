# CDiskProtection::s_EnableDefragTask(int)

- ea: `0x140010808`
- end: `0x140010d57`
- name: `?s_EnableDefragTask@CDiskProtection@@KAJH@Z`
- size: `1359`
- prototype: `__int64 __fastcall(int)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140009778`
- `0x140009af0`
- `0x14000b980`

## callees

- `0x140010808`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007e010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1400108a9`
- `KERNEL32!IsDebuggerPresent` at `0x140010959`
- `KERNEL32!IsDebuggerPresent` at `0x1400109eb`
- `KERNEL32!IsDebuggerPresent` at `0x140010aa4`
- `KERNEL32!IsDebuggerPresent` at `0x140010b22`
- `KERNEL32!IsDebuggerPresent` at `0x140010ba0`
- `KERNEL32!IsDebuggerPresent` at `0x140010c22`
- `KERNEL32!IsDebuggerPresent` at `0x140010c8d`
- `KERNEL32!IsDebuggerPresent` at `0x1400108a9`
- `KERNEL32!IsDebuggerPresent` at `0x140010959`
- `KERNEL32!IsDebuggerPresent` at `0x1400109eb`
- `KERNEL32!IsDebuggerPresent` at `0x140010aa4`
- `KERNEL32!IsDebuggerPresent` at `0x140010b22`
- `KERNEL32!IsDebuggerPresent` at `0x140010ba0`
- `KERNEL32!IsDebuggerPresent` at `0x140010c22`
- `KERNEL32!IsDebuggerPresent` at `0x140010c8d`
- `ole32!CoCreateInstance` at `0x1400109a7`
- `ole32!CoCreateInstance` at `0x1400109a7`
- `OLEAUT32!__imp_SysAllocString` at `0x140010852`
- `OLEAUT32!__imp_SysAllocString` at `0x140010909`
- `OLEAUT32!__imp_SysAllocString` at `0x140010852`
- `OLEAUT32!__imp_SysAllocString` at `0x140010909`
- `OLEAUT32!__imp_SysFreeString` at `0x140010d2b`
- `OLEAUT32!__imp_SysFreeString` at `0x140010d34`
- `OLEAUT32!__imp_SysFreeString` at `0x140010d2b`
- `OLEAUT32!__imp_SysFreeString` at `0x140010d34`
- `OLEAUT32!__imp_VariantInit` at `0x140010845`
- `OLEAUT32!__imp_VariantInit` at `0x140010845`

## string_xrefs

- `0x14001087d`: `CDiskProtection::s_EnableDefragTask`
- `0x140010930`: `CDiskProtection::s_EnableDefragTask`
- `0x1400109be`: `CDiskProtection::s_EnableDefragTask`
- `0x140010a77`: `CDiskProtection::s_EnableDefragTask`
- `0x140010af5`: `CDiskProtection::s_EnableDefragTask`
- `0x140010b73`: `CDiskProtection::s_EnableDefragTask`
- `0x140010bf5`: `CDiskProtection::s_EnableDefragTask`
- `0x140010c60`: `CDiskProtection::s_EnableDefragTask`
- `0x140010902`: `ScheduledDefrag`
- `0x14001091d`: `bstrDefragTask`
- `0x140010961`: `bstrDefragTask`

## pseudocode

```c
__int64 __fastcall CDiskProtection::s_EnableDefragTask(int a1)
{
  OLECHAR *v2; // r13
  OLECHAR *v3; // r12
  unsigned int v4; // ebx
  bool v5; // zf
  const unsigned __int16 *v6; // rax
  __int64 v7; // r9
  HRESULT v8; // eax
  __int64 v9; // r8
  __int64 v10; // rax
  __int64 (__fastcall *v11)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *); // rax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  __int64 (__fastcall *v15)(__int64, __int64); // rax
  int v16; // eax
  int v17; // eax
  VARIANTARG pvarg; // [rsp+40h] [rbp-79h] BYREF
  __int128 v20; // [rsp+60h] [rbp-59h] BYREF
  IRecordInfo *pRecInfo; // [rsp+70h] [rbp-49h]
  VARIANTARG v22; // [rsp+80h] [rbp-39h] BYREF
  VARIANTARG v23; // [rsp+A0h] [rbp-19h] BYREF
  VARIANTARG v24; // [rsp+C0h] [rbp+7h] BYREF
  LPVOID ppv; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v26; // [rsp+130h] [rbp+77h] BYREF
  __int64 v27; // [rsp+138h] [rbp+7Fh] BYREF

  ppv = 0;
  v27 = 0;
  v26 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v2 = SysAllocString(L"\\Microsoft\\Windows\\Defrag");
  if ( !v2 )
  {
    v3 = 0;
    v4 = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      0x132Fu,
      L"CDiskProtection::s_EnableDefragTask",
      L"CPR",
      L"bstrDefragFolder",
      -2147024882);
    v5 = !IsDebuggerPresent();
    v6 = L"bstrDefragFolder";
    if ( v5 )
    {
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        4911,
        L"CDiskProtection::s_EnableDefragTask",
        L"CPR",
        L"bstrDefragFolder",
        -2147024882);
      goto LABEL_37;
    }
    v7 = 4911;
LABEL_4:
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      v7,
      L"CDiskProtection::s_EnableDefragTask",
      L"CPR",
      v6,
      -2147024882);
    goto LABEL_37;
  }
  v3 = SysAllocString(L"ScheduledDefrag");
  if ( !v3 )
  {
    v4 = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      0x1332u,
      L"CDiskProtection::s_EnableDefragTask",
      L"CPR",
      L"bstrDefragTask",
      -2147024882);
    v5 = !IsDebuggerPresent();
    v6 = L"bstrDefragTask";
    if ( v5 )
    {
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        4914,
        L"CDiskProtection::s_EnableDefragTask",
        L"CPR",
        L"bstrDefragTask",
        -2147024882);
      goto LABEL_37;
    }
    v7 = 4914;
    goto LABEL_4;
  }
  v8 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &ppv);
  v4 = v8;
  if ( v8 >= 0 )
  {
    v20 = *(_OWORD *)&pvarg.vt;
    v10 = *(_QWORD *)ppv;
    pRecInfo = pvarg.pRecInfo;
    v22 = pvarg;
    v11 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *))(v10 + 80);
    v23 = pvarg;
    v24 = pvarg;
    v12 = v11(ppv, &v24, &v23, &v22, &v20);
    v4 = v12;
    if ( v12 >= 0 )
    {
      v13 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, v2, &v27);
      v4 = v13;
      if ( v13 >= 0 )
      {
        v14 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)v27 + 104LL))(v27, v3, &v26);
        v4 = v14;
        if ( v14 >= 0 )
        {
          v15 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 88LL);
          if ( a1 )
          {
            v16 = v15(v26, 0xFFFFFFFFLL);
            v4 = v16;
            if ( v16 >= 0 )
              goto LABEL_37;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
              0x1343u,
              L"CDiskProtection::s_EnableDefragTask",
              L"CHRA",
              L"hr",
              v16);
            if ( IsDebuggerPresent() )
            {
              DEBUGMSGLEVEL(
                2u,
                L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
                L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
                4931,
                L"CDiskProtection::s_EnableDefragTask",
                L"CHRA",
                L"hr",
                v4);
              goto LABEL_37;
            }
            v9 = 4931;
          }
          else
          {
            v17 = v15(v26, 0);
            v4 = v17;
            if ( v17 >= 0 )
              goto LABEL_37;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
              0x1348u,
              L"CDiskProtection::s_EnableDefragTask",
              L"CHRA",
              L"hr",
              v17);
            if ( IsDebuggerPresent() )
            {
              DEBUGMSGLEVEL(
                2u,
                L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
                L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
                4936,
                L"CDiskProtection::s_EnableDefragTask",
                L"CHRA",
                L"hr",
                v4);
              goto LABEL_37;
            }
            v9 = 4936;
          }
        }
        else
        {
          LOGASSERTHR(
            L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
            0x133Eu,
            L"CDiskProtection::s_EnableDefragTask",
            L"CHRA",
            L"hr",
            v14);
          if ( IsDebuggerPresent() )
          {
            DEBUGMSGLEVEL(
              2u,
              L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
              4926,
              L"CDiskProtection::s_EnableDefragTask",
              L"CHRA",
              L"hr",
              v4);
            goto LABEL_37;
          }
          v9 = 4926;
        }
      }
      else
      {
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
          0x133Bu,
          L"CDiskProtection::s_EnableDefragTask",
          L"CHRA",
          L"hr",
          v13);
        if ( IsDebuggerPresent() )
        {
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
            4923,
            L"CDiskProtection::s_EnableDefragTask",
            L"CHRA",
            L"hr",
            v4);
          goto LABEL_37;
        }
        v9 = 4923;
      }
    }
    else
    {
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        0x1338u,
        L"CDiskProtection::s_EnableDefragTask",
        L"CHRA",
        L"hr",
        v12);
      if ( IsDebuggerPresent() )
      {
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
          4920,
          L"CDiskProtection::s_EnableDefragTask",
          L"CHRA",
          L"hr",
          v4);
        goto LABEL_37;
      }
      v9 = 4920;
    }
  }
  else
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      0x1335u,
      L"CDiskProtection::s_EnableDefragTask",
      L"CHRA",
      L"hr",
      v8);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        4917,
        L"CDiskProtection::s_EnableDefragTask",
        L"CHRA",
        L"hr",
        v4);
      goto LABEL_37;
    }
    v9 = 4917;
  }
  DEBUGMSGBOX(
    L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
    L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
    v9,
    L"CDiskProtection::s_EnableDefragTask",
    L"CHRA",
    L"hr",
    v4);
LABEL_37:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v27 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
  }
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
  }
  SysFreeString(v2);
  SysFreeString(v3);
  return v4;
}

```

## disassembly

```asm
0x140010808  mov     [rsp-8+arg_0], rbx
0x14001080d  push    rbp
0x14001080e  push    rsi
0x14001080f  push    rdi
0x140010810  push    r12
0x140010812  push    r13
0x140010814  push    r14
0x140010816  push    r15
0x140010818  lea     rbp, [rsp-27h]
0x14001081d  sub     rsp, 0E0h
0x140010824  xor     ebx, ebx
0x140010826  mov     edi, ecx
0x140010828  xorps   xmm0, xmm0
0x14001082b  mov     [rbp+57h+arg_8], rbx
0x14001082f  xor     eax, eax
0x140010831  mov     [rbp+57h+arg_18], rbx
0x140010835  lea     rcx, [rbp+57h+pvarg]; pvarg
0x140010839  mov     [rbp+57h+arg_10], rbx
0x14001083d  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x140010841  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x140010845  call    cs:__imp_VariantInit
0x14001084b  lea     rcx, aMicrosoftWindo_0; "\\Microsoft\\Windows\\Defrag"
0x140010852  call    cs:__imp_SysAllocString
0x140010858  mov     r13, rax
0x14001085b  test    rax, rax
0x14001085e  jnz     loc_140010902
0x140010864  mov     r14d, 8007000Eh
0x14001086a  lea     rax, aBstrdefragfold; "bstrDefragFolder"
0x140010871  lea     r15, aCpr; "CPR"
0x140010878  mov     [rsp+110h+var_E8], r14d; int
0x14001087d  lea     rsi, aCdiskprotectio_114; "CDiskProtection::s_EnableDefragTask"
0x140010884  mov     [rsp+110h+ppv], rax; unsigned __int16 *
0x140010889  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140010890  mov     r9, r15; unsigned __int16 *
0x140010893  mov     r8, rsi; unsigned __int16 *
0x140010896  mov     rcx, rdi; unsigned __int16 *
0x140010899  mov     r12d, ebx
0x14001089c  mov     edx, 132Fh; unsigned int
0x1400108a1  mov     ebx, r14d
0x1400108a4  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400108a9  call    cs:__imp_IsDebuggerPresent
0x1400108af  test    eax, eax
0x1400108b1  lea     rax, aBstrdefragfold; "bstrDefragFolder"
0x1400108b8  jz      short loc_1400108ED
0x1400108ba  mov     r9d, 132Fh
0x1400108c0  mov     [rsp+110h+var_D8], r14d
0x1400108c5  mov     [rsp+110h+var_E0], rax
0x1400108ca  mov     qword ptr [rsp+110h+var_E8], r15
0x1400108cf  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400108d6  mov     r8, rdi
0x1400108d9  mov     [rsp+110h+ppv], rsi
0x1400108de  mov     ecx, 2; unsigned __int8
0x1400108e3  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400108e8  jmp     loc_140010CD1
0x1400108ed  mov     dword ptr [rsp+110h+var_E0], r14d
0x1400108f2  mov     r8d, 132Fh
0x1400108f8  mov     qword ptr [rsp+110h+var_E8], rax
0x1400108fd  jmp     loc_140010CBA
0x140010902  lea     rcx, aScheduleddefra; "ScheduledDefrag"
0x140010909  call    cs:__imp_SysAllocString
0x14001090f  mov     r12, rax
0x140010912  test    rax, rax
0x140010915  jnz     short loc_14001098A
0x140010917  mov     r14d, 8007000Eh
0x14001091d  lea     rax, aBstrdefragtask; "bstrDefragTask"
0x140010924  lea     r15, aCpr; "CPR"
0x14001092b  mov     [rsp+110h+var_E8], r14d; int
0x140010930  lea     rsi, aCdiskprotectio_114; "CDiskProtection::s_EnableDefragTask"
0x140010937  mov     [rsp+110h+ppv], rax; unsigned __int16 *
0x14001093c  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140010943  mov     r9, r15; unsigned __int16 *
0x140010946  mov     r8, rsi; unsigned __int16 *
0x140010949  mov     rcx, rdi; unsigned __int16 *
0x14001094c  mov     edx, 1332h; unsigned int
0x140010951  mov     ebx, r14d
0x140010954  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140010959  call    cs:__imp_IsDebuggerPresent
0x14001095f  test    eax, eax
0x140010961  lea     rax, aBstrdefragtask; "bstrDefragTask"
0x140010968  jz      short loc_140010975
0x14001096a  mov     r9d, 1332h
0x140010970  jmp     loc_1400108C0
0x140010975  mov     dword ptr [rsp+110h+var_E0], r14d
0x14001097a  mov     r8d, 1332h
0x140010980  mov     qword ptr [rsp+110h+var_E8], rax
0x140010985  jmp     loc_140010CBA
0x14001098a  xor     edx, edx; pUnkOuter
0x14001098c  lea     rax, [rbp+57h+arg_8]
0x140010990  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x140010997  mov     [rsp+110h+ppv], rax; ppv
0x14001099c  lea     rcx, CLSID_TaskScheduler; rclsid
0x1400109a3  lea     r8d, [rdx+1]; dwClsContext
0x1400109a7  call    cs:__imp_CoCreateInstance
0x1400109ad  mov     ebx, eax
0x1400109af  test    eax, eax
0x1400109b1  jns     short loc_140010A14
0x1400109b3  mov     [rsp+110h+var_E8], eax; int
0x1400109b7  lea     r15, aChra; "CHRA"
0x1400109be  lea     rsi, aCdiskprotectio_114; "CDiskProtection::s_EnableDefragTask"
0x1400109c5  mov     r9, r15; unsigned __int16 *
0x1400109c8  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x1400109cf  mov     r8, rsi; unsigned __int16 *
0x1400109d2  lea     r14, aHr; "hr"
0x1400109d9  mov     rcx, rdi; unsigned __int16 *
0x1400109dc  mov     edx, 1335h; unsigned int
0x1400109e1  mov     [rsp+110h+ppv], r14; unsigned __int16 *
0x1400109e6  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400109eb  call    cs:__imp_IsDebuggerPresent
0x1400109f1  test    eax, eax
0x1400109f3  jz      short loc_140010A09
0x1400109f5  mov     [rsp+110h+var_D8], ebx
0x1400109f9  mov     r9d, 1335h
0x1400109ff  mov     [rsp+110h+var_E0], r14
0x140010a04  jmp     loc_1400108CA
0x140010a09  mov     r8d, 1335h
0x140010a0f  jmp     loc_140010CB1
0x140010a14  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x140010a18  lea     rdx, [rbp+57h+var_B0]
0x140010a1c  mov     rcx, [rbp+57h+arg_8]
0x140010a20  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x140010a25  lea     r9, [rbp+57h+var_90]
0x140010a29  mov     [rsp+110h+ppv], rdx
0x140010a2e  lea     r8, [rbp+57h+var_70]
0x140010a32  lea     rdx, [rbp+57h+var_50]
0x140010a36  movaps  [rbp+57h+var_B0], xmm1
0x140010a3a  mov     rax, [rcx]
0x140010a3d  movsd   [rbp+57h+var_A0], xmm0
0x140010a42  movaps  [rbp+57h+var_90], xmm1
0x140010a46  movsd   [rbp+57h+var_80], xmm0
0x140010a4b  mov     rax, [rax+50h]
0x140010a4f  movaps  [rbp+57h+var_70], xmm1
0x140010a53  movsd   [rbp+57h+var_60], xmm0
0x140010a58  movaps  [rbp+57h+var_50], xmm1
0x140010a5c  movsd   [rbp+57h+var_40], xmm0
0x140010a61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010a66  mov     ebx, eax
0x140010a68  test    eax, eax
0x140010a6a  jns     short loc_140010ACD
0x140010a6c  mov     [rsp+110h+var_E8], eax; int
0x140010a70  lea     r15, aChra; "CHRA"
0x140010a77  lea     rsi, aCdiskprotectio_114; "CDiskProtection::s_EnableDefragTask"
0x140010a7e  mov     r9, r15; unsigned __int16 *
0x140010a81  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140010a88  mov     r8, rsi; unsigned __int16 *
0x140010a8b  lea     r14, aHr; "hr"
0x140010a92  mov     rcx, rdi; unsigned __int16 *
0x140010a95  mov     edx, 1338h; unsigned int
0x140010a9a  mov     [rsp+110h+ppv], r14; unsigned __int16 *
0x140010a9f  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140010aa4  call    cs:__imp_IsDebuggerPresent
0x140010aaa  test    eax, eax
0x140010aac  jz      short loc_140010AC2
0x140010aae  mov     [rsp+110h+var_D8], ebx
0x140010ab2  mov     r9d, 1338h
0x140010ab8  mov     [rsp+110h+var_E0], r14
0x140010abd  jmp     loc_1400108CA
0x140010ac2  mov     r8d, 1338h
0x140010ac8  jmp     loc_140010CB1
0x140010acd  mov     rcx, [rbp+57h+arg_8]
0x140010ad1  lea     r8, [rbp+57h+arg_18]
0x140010ad5  mov     rdx, r13
0x140010ad8  mov     rax, [rcx]
0x140010adb  mov     rax, [rax+38h]
0x140010adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010ae4  mov     ebx, eax
0x140010ae6  test    eax, eax
0x140010ae8  jns     short loc_140010B4B
0x140010aea  mov     [rsp+110h+var_E8], eax; int
0x140010aee  lea     r15, aChra; "CHRA"
0x140010af5  lea     rsi, aCdiskprotectio_114; "CDiskProtection::s_EnableDefragTask"
0x140010afc  mov     r9, r15; unsigned __int16 *
0x140010aff  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140010b06  mov     r8, rsi; unsigned __int16 *
0x140010b09  lea     r14, aHr; "hr"
0x140010b10  mov     rcx, rdi; unsigned __int16 *
0x140010b13  mov     edx, 133Bh; unsigned int
0x140010b18  mov     [rsp+110h+ppv], r14; unsigned __int16 *
0x140010b1d  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140010b22  call    cs:__imp_IsDebuggerPresent
0x140010b28  test    eax, eax
0x140010b2a  jz      short loc_140010B40
0x140010b2c  mov     [rsp+110h+var_D8], ebx
0x140010b30  mov     r9d, 133Bh
0x140010b36  mov     [rsp+110h+var_E0], r14
0x140010b3b  jmp     loc_1400108CA
0x140010b40  mov     r8d, 133Bh
0x140010b46  jmp     loc_140010CB1
0x140010b4b  mov     rcx, [rbp+57h+arg_18]
0x140010b4f  lea     r8, [rbp+57h+arg_10]
0x140010b53  mov     rdx, r12
0x140010b56  mov     rax, [rcx]
0x140010b59  mov     rax, [rax+68h]
0x140010b5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010b62  mov     ebx, eax
0x140010b64  test    eax, eax
0x140010b66  jns     short loc_140010BC9
0x140010b68  mov     [rsp+110h+var_E8], eax; int
0x140010b6c  lea     r15, aChra; "CHRA"
0x140010b73  lea     rsi, aCdiskprotectio_114; "CDiskProtection::s_EnableDefragTask"
0x140010b7a  mov     r9, r15; unsigned __int16 *
0x140010b7d  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140010b84  mov     r8, rsi; unsigned __int16 *
0x140010b87  lea     r14, aHr; "hr"
0x140010b8e  mov     rcx, rdi; unsigned __int16 *
0x140010b91  mov     edx, 133Eh; unsigned int
0x140010b96  mov     [rsp+110h+ppv], r14; unsigned __int16 *
0x140010b9b  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140010ba0  call    cs:__imp_IsDebuggerPresent
0x140010ba6  test    eax, eax
0x140010ba8  jz      short loc_140010BBE
0x140010baa  mov     [rsp+110h+var_D8], ebx
0x140010bae  mov     r9d, 133Eh
0x140010bb4  mov     [rsp+110h+var_E0], r14
0x140010bb9  jmp     loc_1400108CA
0x140010bbe  mov     r8d, 133Eh
0x140010bc4  jmp     loc_140010CB1
0x140010bc9  mov     rcx, [rbp+57h+arg_10]
0x140010bcd  mov     rax, [rcx]
0x140010bd0  mov     rax, [rax+58h]
0x140010bd4  test    edi, edi
0x140010bd6  jz      short loc_140010C48
0x140010bd8  or      edx, 0FFFFFFFFh
0x140010bdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010be0  mov     ebx, eax
0x140010be2  test    eax, eax
0x140010be4  jns     loc_140010CD1
0x140010bea  mov     [rsp+110h+var_E8], eax; int
0x140010bee  lea     r15, aChra; "CHRA"
0x140010bf5  lea     rsi, aCdiskprotectio_114; "CDiskProtection::s_EnableDefragTask"
0x140010bfc  mov     r9, r15; unsigned __int16 *
0x140010bff  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140010c06  mov     r8, rsi; unsigned __int16 *
0x140010c09  lea     r14, aHr; "hr"
0x140010c10  mov     rcx, rdi; unsigned __int16 *
0x140010c13  mov     edx, 1343h; unsigned int
0x140010c18  mov     [rsp+110h+ppv], r14; unsigned __int16 *
0x140010c1d  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140010c22  call    cs:__imp_IsDebuggerPresent
0x140010c28  test    eax, eax
0x140010c2a  jz      short loc_140010C40
0x140010c2c  mov     [rsp+110h+var_D8], ebx
0x140010c30  mov     r9d, 1343h
0x140010c36  mov     [rsp+110h+var_E0], r14
0x140010c3b  jmp     loc_1400108CA
0x140010c40  mov     r8d, 1343h
0x140010c46  jmp     short loc_140010CB1
0x140010c48  xor     edx, edx
0x140010c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010c4f  mov     ebx, eax
0x140010c51  test    eax, eax
0x140010c53  jns     short loc_140010CD1
0x140010c55  mov     [rsp+110h+var_E8], eax; int
0x140010c59  lea     r15, aChra; "CHRA"
0x140010c60  lea     rsi, aCdiskprotectio_114; "CDiskProtection::s_EnableDefragTask"
0x140010c67  mov     r9, r15; unsigned __int16 *
0x140010c6a  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140010c71  mov     r8, rsi; unsigned __int16 *
0x140010c74  lea     r14, aHr; "hr"
0x140010c7b  mov     rcx, rdi; unsigned __int16 *
0x140010c7e  mov     edx, 1348h; unsigned int
0x140010c83  mov     [rsp+110h+ppv], r14; unsigned __int16 *
0x140010c88  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140010c8d  call    cs:__imp_IsDebuggerPresent
0x140010c93  test    eax, eax
0x140010c95  jz      short loc_140010CAB
0x140010c97  mov     [rsp+110h+var_D8], ebx
0x140010c9b  mov     r9d, 1348h
0x140010ca1  mov     [rsp+110h+var_E0], r14
0x140010ca6  jmp     loc_1400108CA
0x140010cab  mov     r8d, 1348h
0x140010cb1  mov     dword ptr [rsp+110h+var_E0], ebx
0x140010cb5  mov     qword ptr [rsp+110h+var_E8], r14
0x140010cba  mov     r9, rsi
0x140010cbd  mov     [rsp+110h+ppv], r15
0x140010cc2  mov     rdx, rdi
0x140010cc5  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140010ccc  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140010cd1  mov     rcx, [rbp+57h+arg_8]
0x140010cd5  test    rcx, rcx
0x140010cd8  jz      short loc_140010CEE
0x140010cda  mov     rax, [rcx]
0x140010cdd  mov     rax, [rax+10h]
0x140010ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010ce6  mov     [rbp+57h+arg_8], 0
0x140010cee  mov     rcx, [rbp+57h+arg_18]
0x140010cf2  test    rcx, rcx
0x140010cf5  jz      short loc_140010D0B
0x140010cf7  mov     rax, [rcx]
0x140010cfa  mov     rax, [rax+10h]
0x140010cfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010d03  mov     [rbp+57h+arg_18], 0
0x140010d0b  mov     rcx, [rbp+57h+arg_10]
0x140010d0f  test    rcx, rcx
0x140010d12  jz      short loc_140010D28
0x140010d14  mov     rax, [rcx]
0x140010d17  mov     rax, [rax+10h]
0x140010d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010d20  mov     [rbp+57h+arg_10], 0
0x140010d28  mov     rcx, r13; bstrString
0x140010d2b  call    cs:__imp_SysFreeString
  ... truncated ...
```
