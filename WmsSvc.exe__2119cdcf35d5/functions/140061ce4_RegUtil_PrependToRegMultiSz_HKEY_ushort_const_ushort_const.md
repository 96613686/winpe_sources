# RegUtil::PrependToRegMultiSz(HKEY__ *,ushort const *,ushort const *)

- ea: `0x140061ce4`
- end: `0x140062411`
- name: `?PrependToRegMultiSz@RegUtil@@YAJPEAUHKEY__@@PEBG1@Z`
- size: `1837`
- prototype: `__int64 __fastcall(HKEY hKey, HKEY lpValueName, const unsigned __int16 *Source, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14006dcf0`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140061ce4`
- `0x140062418`
- `0x14007cb9e`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x140062347`
- `ADVAPI32!RegSetValueExW` at `0x140062347`
- `ADVAPI32!RegQueryValueExW` at `0x140061e0e`
- `ADVAPI32!RegQueryValueExW` at `0x14006211f`
- `ADVAPI32!RegQueryValueExW` at `0x140061e0e`
- `ADVAPI32!RegQueryValueExW` at `0x14006211f`
- `KERNEL32!IsDebuggerPresent` at `0x140061d66`
- `KERNEL32!IsDebuggerPresent` at `0x140061e70`
- `KERNEL32!IsDebuggerPresent` at `0x140061ee3`
- `KERNEL32!IsDebuggerPresent` at `0x140061f94`
- `KERNEL32!IsDebuggerPresent` at `0x14006203b`
- `KERNEL32!IsDebuggerPresent` at `0x1400620da`
- `KERNEL32!IsDebuggerPresent` at `0x14006218f`
- `KERNEL32!IsDebuggerPresent` at `0x14006223e`
- `KERNEL32!IsDebuggerPresent` at `0x1400622ee`
- `KERNEL32!IsDebuggerPresent` at `0x14006239c`
- `KERNEL32!IsDebuggerPresent` at `0x140061d66`
- `KERNEL32!IsDebuggerPresent` at `0x140061e70`
- `KERNEL32!IsDebuggerPresent` at `0x140061ee3`
- `KERNEL32!IsDebuggerPresent` at `0x140061f94`
- `KERNEL32!IsDebuggerPresent` at `0x14006203b`
- `KERNEL32!IsDebuggerPresent` at `0x1400620da`
- `KERNEL32!IsDebuggerPresent` at `0x14006218f`
- `KERNEL32!IsDebuggerPresent` at `0x14006223e`
- `KERNEL32!IsDebuggerPresent` at `0x1400622ee`
- `KERNEL32!IsDebuggerPresent` at `0x14006239c`
- `msvcrt!memcpy_s` at `0x1400621ee`
- `msvcrt!memcpy_s` at `0x14006229e`
- `msvcrt!memcpy_s` at `0x1400621ee`
- `msvcrt!memcpy_s` at `0x14006229e`

## string_xrefs

- `0x140061d46`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x140061e4f`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x140061eba`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x140061f6c`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x140062020`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x1400620bf`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x140062166`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x140062215`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x1400622c5`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x140062379`: `termsrv\wms\src\common\srcutils\registry.cpp`

## pseudocode

```c
__int64 __fastcall RegUtil::PrependToRegMultiSz(
        HKEY hKey,
        const WCHAR *lpValueName,
        wchar_t *Source,
        const unsigned __int16 *a4)
{
  const unsigned __int16 *v7; // r13
  unsigned int v8; // r12d
  int v9; // ebx
  __int64 v10; // r9
  const unsigned __int16 *v11; // r9
  LSTATUS v12; // eax
  unsigned int v13; // r13d
  __int64 v14; // r8
  wchar_t *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // r15
  bool v18; // zf
  const unsigned __int16 *v19; // rax
  BYTE *v20; // rax
  LSTATUS v21; // eax
  rsize_t v22; // r15
  LSTATUS v23; // eax
  const unsigned __int16 *lpcbData; // [rsp+28h] [rbp-38h]
  const unsigned __int16 *v26; // [rsp+30h] [rbp-30h]
  int v27; // [rsp+38h] [rbp-28h]
  DWORD v28; // [rsp+40h] [rbp-20h]
  BYTE *lpData; // [rsp+48h] [rbp-18h]
  char *Destination; // [rsp+50h] [rbp-10h]
  DWORD cbData; // [rsp+A8h] [rbp+48h] BYREF
  DWORD Type; // [rsp+B8h] [rbp+58h] BYREF

  Type = 0;
  cbData = 0;
  Destination = 0;
  lpData = 0;
  if ( lpValueName )
  {
    if ( !Source )
    {
      v7 = L"pszString != 0";
      v8 = 408;
      goto LABEL_3;
    }
    DEBUGMSG(L"RegUtil::PrependToRegMultiSz - Prepending %s to value %s\n", Source, lpValueName, a4);
    v9 = RegUtil::RemoveFromRegMultiSz(hKey, lpValueName, Source, v11);
    if ( v9 < 0 )
      goto LABEL_64;
    v12 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData);
    v9 = v12;
    if ( v12 != 2 )
    {
      if ( v12 )
      {
        if ( v12 > 0 )
          v9 = (unsigned __int16)v12 | 0x80070000;
        v13 = 432;
        goto LABEL_15;
      }
      if ( Type != 7 )
      {
        v9 = -2147467259;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
          0x1B1u,
          L"RegUtil::PrependToRegMultiSz",
          L"CBRA",
          L"dwType == ( 7ul )",
          -2147467259);
        if ( !IsDebuggerPresent() )
        {
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
            433,
            L"RegUtil::PrependToRegMultiSz",
            L"CBRA",
            L"dwType == ( 7ul )",
            -2147467259);
          goto LABEL_64;
        }
        v27 = -2147467259;
        v10 = 433;
        v26 = L"dwType == ( 7ul )";
        lpcbData = L"CBRA";
        goto LABEL_5;
      }
    }
    v15 = Source;
    v16 = 0x7FFFFFFF;
    do
    {
      if ( !*v15 )
        break;
      ++v15;
      --v16;
    }
    while ( v16 );
    v9 = v16 == 0 ? 0x80070057 : 0;
    v17 = (0x7FFFFFFF - v16) & -(__int64)(v16 != 0);
    if ( !v16 )
    {
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
        0x1B5u,
        L"RegUtil::PrependToRegMultiSz",
        L"CHRA",
        L"hr",
        -2147024809);
      if ( !IsDebuggerPresent() )
      {
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
          437,
          L"RegUtil::PrependToRegMultiSz",
          L"CHRA",
          L"hr",
          v9);
        goto LABEL_64;
      }
      v27 = v9;
      v10 = 437;
      v26 = L"hr";
      lpcbData = L"CHRA";
      goto LABEL_5;
    }
    v28 = cbData + 2 * v17 + 4;
    Destination = (char *)operator new(v28);
    if ( !Destination )
    {
      v13 = 446;
      v9 = -2147024882;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
        0x1BEu,
        L"RegUtil::PrependToRegMultiSz",
        L"CPR",
        L"pbNewBuf",
        -2147024882);
      v18 = !IsDebuggerPresent();
      v19 = L"pbNewBuf";
LABEL_32:
      if ( v18 )
      {
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
          v13,
          L"RegUtil::PrependToRegMultiSz",
          L"CPR",
          v19,
          -2147024882);
        goto LABEL_64;
      }
      v27 = -2147024882;
      v26 = v19;
      lpcbData = L"CPR";
      goto LABEL_17;
    }
    if ( cbData )
    {
      v20 = (BYTE *)operator new(cbData + 4LL);
      lpData = v20;
      if ( !v20 )
      {
        v13 = 455;
        v9 = -2147024882;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
          0x1C7u,
          L"RegUtil::PrependToRegMultiSz",
          L"CPR",
          L"pbCurBuf",
          -2147024882);
        v18 = !IsDebuggerPresent();
        v19 = L"pbCurBuf";
        goto LABEL_32;
      }
      memset_0(v20, 0, cbData + 4LL);
      v21 = RegQueryValueExW(hKey, lpValueName, 0, &Type, lpData, &cbData);
      if ( v21 )
      {
        if ( v21 > 0 )
          v9 = (unsigned __int16)v21 | 0x80070000;
        else
          v9 = v21;
        v13 = 460;
LABEL_15:
        LOGASSERTHR(
          L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
          v13,
          L"RegUtil::PrependToRegMultiSz",
          L"CBRAEx",
          L"lResult == 0L",
          v9);
        if ( IsDebuggerPresent() )
        {
          v27 = v9;
          v26 = L"lResult == 0L";
          lpcbData = L"CBRAEx";
LABEL_17:
          v10 = v13;
          goto LABEL_5;
        }
        v14 = v13;
LABEL_63:
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
          v14,
          L"RegUtil::PrependToRegMultiSz",
          L"CBRAEx",
          L"lResult == 0L",
          v9);
        goto LABEL_64;
      }
      if ( Type != 7 )
      {
        v9 = -2147467259;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
          0x1CDu,
          L"RegUtil::PrependToRegMultiSz",
          L"CBRA",
          L"dwType == ( 7ul )",
          -2147467259);
        if ( !IsDebuggerPresent() )
        {
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
            461,
            L"RegUtil::PrependToRegMultiSz",
            L"CBRA",
            L"dwType == ( 7ul )",
            -2147467259);
          goto LABEL_64;
        }
        v27 = -2147467259;
        v10 = 461;
        v26 = L"dwType == ( 7ul )";
        lpcbData = L"CBRA";
        goto LABEL_5;
      }
    }
    memset_0(Destination, 0, v28);
    v22 = 2 * v17;
    if ( memcpy_s(Destination, v28, Source, v22) )
    {
      v9 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
        0x1DDu,
        L"RegUtil::PrependToRegMultiSz",
        L"CBRA",
        L"iError == 0",
        -2147467259);
      if ( !IsDebuggerPresent() )
      {
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
          477,
          L"RegUtil::PrependToRegMultiSz",
          L"CBRA",
          L"iError == 0",
          -2147467259);
        goto LABEL_64;
      }
      v27 = -2147467259;
      v10 = 477;
      v26 = L"iError == 0";
      lpcbData = L"CBRA";
      goto LABEL_5;
    }
    if ( cbData && memcpy_s(&Destination[v22 + 2], v28 - v22 - 2, lpData, cbData) )
    {
      v9 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
        0x1EDu,
        L"RegUtil::PrependToRegMultiSz",
        L"CBRA",
        L"iError == 0",
        -2147467259);
      if ( !IsDebuggerPresent() )
      {
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
          493,
          L"RegUtil::PrependToRegMultiSz",
          L"CBRA",
          L"iError == 0",
          -2147467259);
        goto LABEL_64;
      }
      v27 = -2147467259;
      v10 = 493;
      v26 = L"iError == 0";
      lpcbData = L"CBRA";
      goto LABEL_5;
    }
    v23 = RegSetValueExW(hKey, lpValueName, 0, 7u, (const BYTE *)Destination, v28);
    if ( !v23 )
      goto LABEL_64;
    if ( v23 > 0 )
      v9 = (unsigned __int16)v23 | 0x80070000;
    else
      v9 = v23;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
      0x1F5u,
      L"RegUtil::PrependToRegMultiSz",
      L"CBRAEx",
      L"lResult == 0L",
      v9);
    if ( IsDebuggerPresent() )
    {
      v27 = v9;
      v10 = 501;
      v26 = L"lResult == 0L";
      lpcbData = L"CBRAEx";
      goto LABEL_5;
    }
    v14 = 501;
    goto LABEL_63;
  }
  v7 = L"pszValueName != 0";
  v8 = 407;
LABEL_3:
  v9 = -2147024809;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
    v8,
    L"RegUtil::PrependToRegMultiSz",
    L"CBRAEx",
    v7,
    -2147024809);
  if ( !IsDebuggerPresent() )
  {
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
      v8,
      L"RegUtil::PrependToRegMultiSz",
      L"CBRAEx",
      v7,
      -2147024809);
    goto LABEL_64;
  }
  v27 = -2147024809;
  v10 = v8;
  v26 = v7;
  lpcbData = L"CBRAEx";
LABEL_5:
  DEBUGMSGLEVEL(
    2u,
    L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
    L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
    v10,
    L"RegUtil::PrependToRegMultiSz",
    lpcbData,
    v26,
    v27);
LABEL_64:
  operator delete(lpData);
  operator delete(Destination);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140061ce4  mov     [rsp-38h+arg_0], rbx
0x140061ce9  push    rbp
0x140061cea  push    rsi
0x140061ceb  push    rdi
0x140061cec  push    r12
0x140061cee  push    r13
0x140061cf0  push    r14
0x140061cf2  push    r15
0x140061cf4  mov     rbp, rsp
0x140061cf7  sub     rsp, 60h
0x140061cfb  xor     r14d, r14d
0x140061cfe  mov     rdi, r8
0x140061d01  mov     [rbp+Type], r14d
0x140061d05  mov     rsi, rdx
0x140061d08  mov     [rbp+cbData], r14d
0x140061d0c  mov     r13, rcx
0x140061d0f  mov     [rbp+Destination], r14
0x140061d13  mov     [rbp+var_18], r14
0x140061d17  test    rdx, rdx
0x140061d1a  jnz     loc_140061DB2
0x140061d20  lea     r13, aPszvaluename0; "pszValueName != 0"
0x140061d27  mov     r12d, 197h
0x140061d2d  mov     r15d, 80070057h
0x140061d33  lea     rsi, aRegutilPrepend; "RegUtil::PrependToRegMultiSz"
0x140061d3a  lea     r14, aCbraex; "CBRAEx"
0x140061d41  mov     dword ptr [rsp+60h+lpcbData], r15d; int
0x140061d46  lea     rdi, aTermsrvWmsSrcC_21; "termsrv\\wms\\src\\common\\srcutils\\re"...
0x140061d4d  mov     [rsp+60h+lpData], r13; unsigned __int16 *
0x140061d52  mov     r8, rsi; unsigned __int16 *
0x140061d55  mov     r9, r14; unsigned __int16 *
0x140061d58  mov     rcx, rdi; unsigned __int16 *
0x140061d5b  mov     edx, r12d; unsigned int
0x140061d5e  mov     ebx, r15d
0x140061d61  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140061d66  call    cs:__imp_IsDebuggerPresent
0x140061d6c  test    eax, eax
0x140061d6e  jz      short loc_140061DA0
0x140061d70  mov     [rsp+60h+var_28], r15d
0x140061d75  mov     r9d, r12d
0x140061d78  mov     [rsp+60h+var_30], r13
0x140061d7d  mov     ecx, 2; unsigned __int8
0x140061d82  mov     [rsp+60h+lpcbData], r14
0x140061d87  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140061d8e  mov     [rsp+60h+lpData], rsi
0x140061d93  mov     r8, rdi
0x140061d96  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140061d9b  jmp     loc_1400623E5
0x140061da0  mov     dword ptr [rsp+60h+var_30], r15d
0x140061da5  mov     r8d, r12d
0x140061da8  mov     [rsp+60h+lpcbData], r13
0x140061dad  jmp     loc_1400623CE
0x140061db2  test    rdi, rdi
0x140061db5  jnz     short loc_140061DC9
0x140061db7  lea     r13, aPszstring0; "pszString != 0"
0x140061dbe  mov     r12d, 198h
0x140061dc4  jmp     loc_140061D2D
0x140061dc9  mov     r8, rsi
0x140061dcc  lea     rcx, aRegutilPrepend_0; "RegUtil::PrependToRegMultiSz - Prependi"...
0x140061dd3  mov     rdx, rdi
0x140061dd6  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140061ddb  mov     r8, rdi; String2
0x140061dde  mov     rdx, rsi; lpValueName
0x140061de1  mov     rcx, r13; hKey
0x140061de4  call    ?RemoveFromRegMultiSz@RegUtil@@YAJPEAUHKEY__@@PEBG1@Z; RegUtil::RemoveFromRegMultiSz(HKEY__ *,ushort const *,ushort const *)
0x140061de9  mov     ebx, eax
0x140061deb  test    eax, eax
0x140061ded  js      loc_1400623E5
0x140061df3  lea     rax, [rbp+cbData]
0x140061df7  xor     r8d, r8d; lpReserved
0x140061dfa  mov     [rsp+60h+lpcbData], rax; lpcbData
0x140061dff  lea     r9, [rbp+Type]; lpType
0x140061e03  mov     rdx, rsi; lpValueName
0x140061e06  mov     [rsp+60h+lpData], r14; lpData
0x140061e0b  mov     rcx, r13; hKey
0x140061e0e  call    cs:__imp_RegQueryValueExW
0x140061e14  mov     r12d, 2
0x140061e1a  mov     ebx, eax
0x140061e1c  cmp     eax, r12d
0x140061e1f  jz      loc_140061F1E
0x140061e25  test    eax, eax
0x140061e27  jz      short loc_140061E9B
0x140061e29  jle     short loc_140061E34
0x140061e2b  movzx   ebx, ax
0x140061e2e  or      ebx, 80070000h
0x140061e34  mov     r13d, 1B0h
0x140061e3a  lea     rsi, aRegutilPrepend; "RegUtil::PrependToRegMultiSz"
0x140061e41  mov     dword ptr [rsp+60h+lpcbData], ebx; int
0x140061e45  lea     r14, aCbraex; "CBRAEx"
0x140061e4c  mov     r8, rsi; unsigned __int16 *
0x140061e4f  lea     rdi, aTermsrvWmsSrcC_21; "termsrv\\wms\\src\\common\\srcutils\\re"...
0x140061e56  mov     r9, r14; unsigned __int16 *
0x140061e59  lea     r15, aLresult0l; "lResult == 0L"
0x140061e60  mov     rcx, rdi; unsigned __int16 *
0x140061e63  mov     edx, r13d; unsigned int
0x140061e66  mov     [rsp+60h+lpData], r15; unsigned __int16 *
0x140061e6b  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140061e70  call    cs:__imp_IsDebuggerPresent
0x140061e76  test    eax, eax
0x140061e78  jz      short loc_140061E93
0x140061e7a  mov     [rsp+60h+var_28], ebx
0x140061e7e  mov     [rsp+60h+var_30], r15
0x140061e83  mov     [rsp+60h+lpcbData], r14
0x140061e88  mov     r9d, r13d
0x140061e8b  mov     ecx, r12d
0x140061e8e  jmp     loc_140061D87
0x140061e93  mov     r8d, r13d
0x140061e96  jmp     loc_1400623C5
0x140061e9b  cmp     [rbp+Type], 7
0x140061e9f  jz      short loc_140061F1E
0x140061ea1  mov     r14d, 80004005h
0x140061ea7  lea     r15, aCbra; "CBRA"
0x140061eae  lea     rsi, aRegutilPrepend; "RegUtil::PrependToRegMultiSz"
0x140061eb5  mov     dword ptr [rsp+60h+lpcbData], r14d; int
0x140061eba  lea     rdi, aTermsrvWmsSrcC_21; "termsrv\\wms\\src\\common\\srcutils\\re"...
0x140061ec1  mov     r9, r15; unsigned __int16 *
0x140061ec4  lea     r13, aDwtype7ul; "dwType == ( 7ul )"
0x140061ecb  mov     r8, rsi; unsigned __int16 *
0x140061ece  mov     rcx, rdi; unsigned __int16 *
0x140061ed1  mov     [rsp+60h+lpData], r13; unsigned __int16 *
0x140061ed6  mov     edx, 1B1h; unsigned int
0x140061edb  mov     ebx, r14d
0x140061ede  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140061ee3  call    cs:__imp_IsDebuggerPresent
0x140061ee9  test    eax, eax
0x140061eeb  jz      short loc_140061F04
0x140061eed  mov     [rsp+60h+var_28], r14d
0x140061ef2  mov     r9d, 1B1h
0x140061ef8  mov     [rsp+60h+var_30], r13
0x140061efd  mov     [rsp+60h+lpcbData], r15
0x140061f02  jmp     short loc_140061E8B
0x140061f04  mov     dword ptr [rsp+60h+var_30], r14d
0x140061f09  mov     r8d, 1B1h
0x140061f0f  mov     [rsp+60h+lpcbData], r13
0x140061f14  mov     [rsp+60h+lpData], r15
0x140061f19  jmp     loc_1400623D3
0x140061f1e  mov     edx, 7FFFFFFFh
0x140061f23  mov     rax, rdi
0x140061f26  mov     ecx, edx
0x140061f28  cmp     [rax], r14w
0x140061f2c  jz      short loc_140061F37
0x140061f2e  add     rax, r12
0x140061f31  sub     rcx, 1
0x140061f35  jnz     short loc_140061F28
0x140061f37  mov     rax, rcx
0x140061f3a  neg     rax
0x140061f3d  mov     rax, rcx
0x140061f40  sbb     ebx, ebx
0x140061f42  sub     rdx, rcx
0x140061f45  not     ebx
0x140061f47  and     ebx, 80070057h
0x140061f4d  neg     rax
0x140061f50  sbb     r15, r15
0x140061f53  and     r15, rdx
0x140061f56  test    rcx, rcx
0x140061f59  jnz     short loc_140061FD1
0x140061f5b  lea     rsi, aRegutilPrepend; "RegUtil::PrependToRegMultiSz"
0x140061f62  mov     dword ptr [rsp+60h+lpcbData], ebx; int
0x140061f66  mov     r15d, 1B5h
0x140061f6c  lea     rdi, aTermsrvWmsSrcC_21; "termsrv\\wms\\src\\common\\srcutils\\re"...
0x140061f73  lea     r13, aHr; "hr"
0x140061f7a  mov     r8, rsi; unsigned __int16 *
0x140061f7d  mov     edx, r15d; unsigned int
0x140061f80  mov     [rsp+60h+lpData], r13; unsigned __int16 *
0x140061f85  mov     rcx, rdi; unsigned __int16 *
0x140061f88  lea     r9, aChra; "CHRA"
0x140061f8f  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140061f94  call    cs:__imp_IsDebuggerPresent
0x140061f9a  test    eax, eax
0x140061f9c  lea     rax, aChra; "CHRA"
0x140061fa3  jz      short loc_140061FBB
0x140061fa5  mov     [rsp+60h+var_28], ebx
0x140061fa9  mov     r9d, r15d
0x140061fac  mov     [rsp+60h+var_30], r13
0x140061fb1  mov     [rsp+60h+lpcbData], rax
0x140061fb6  jmp     loc_140061E8B
0x140061fbb  mov     dword ptr [rsp+60h+var_30], ebx
0x140061fbf  mov     r8d, r15d
0x140061fc2  mov     [rsp+60h+lpcbData], r13
0x140061fc7  mov     [rsp+60h+lpData], rax
0x140061fcc  jmp     loc_1400623D3
0x140061fd1  mov     eax, [rbp+cbData]
0x140061fd4  lea     eax, [rax+r15*2]
0x140061fd8  add     eax, 4
0x140061fdb  mov     ecx, eax; Size
0x140061fdd  mov     [rbp+var_20], eax
0x140061fe0  mov     r14d, eax
0x140061fe3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140061fe8  mov     [rbp+Destination], rax
0x140061fec  test    rax, rax
0x140061fef  jnz     loc_140062077
0x140061ff5  mov     r14d, 8007000Eh
0x140061ffb  lea     rax, aPbnewbuf; "pbNewBuf"
0x140062002  lea     r15, aCpr; "CPR"
0x140062009  mov     dword ptr [rsp+60h+lpcbData], r14d; int
0x14006200e  lea     rsi, aRegutilPrepend; "RegUtil::PrependToRegMultiSz"
0x140062015  mov     [rsp+60h+lpData], rax; unsigned __int16 *
0x14006201a  mov     r13d, 1BEh
0x140062020  lea     rdi, aTermsrvWmsSrcC_21; "termsrv\\wms\\src\\common\\srcutils\\re"...
0x140062027  mov     r9, r15; unsigned __int16 *
0x14006202a  mov     r8, rsi; unsigned __int16 *
0x14006202d  mov     edx, r13d; unsigned int
0x140062030  mov     rcx, rdi; unsigned __int16 *
0x140062033  mov     ebx, r14d
0x140062036  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006203b  call    cs:__imp_IsDebuggerPresent
0x140062041  test    eax, eax
0x140062043  lea     rax, aPbnewbuf; "pbNewBuf"
0x14006204a  jz      short loc_140062060
0x14006204c  mov     [rsp+60h+var_28], r14d
0x140062051  mov     [rsp+60h+var_30], rax
0x140062056  mov     [rsp+60h+lpcbData], r15
0x14006205b  jmp     loc_140061E88
0x140062060  mov     dword ptr [rsp+60h+var_30], r14d
0x140062065  mov     r8d, r13d
0x140062068  mov     [rsp+60h+lpcbData], rax
0x14006206d  mov     [rsp+60h+lpData], r15
0x140062072  jmp     loc_1400623D3
0x140062077  mov     eax, [rbp+cbData]
0x14006207a  test    eax, eax
0x14006207c  jz      loc_1400621CD
0x140062082  lea     rcx, [rax+4]; Size
0x140062086  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14006208b  mov     [rbp+var_18], rax
0x14006208f  test    rax, rax
0x140062092  jnz     short loc_1400620EE
0x140062094  mov     r14d, 8007000Eh
0x14006209a  lea     rax, aPbcurbuf; "pbCurBuf"
0x1400620a1  lea     r15, aCpr; "CPR"
0x1400620a8  mov     dword ptr [rsp+60h+lpcbData], r14d; int
0x1400620ad  lea     rsi, aRegutilPrepend; "RegUtil::PrependToRegMultiSz"
0x1400620b4  mov     [rsp+60h+lpData], rax; unsigned __int16 *
0x1400620b9  mov     r13d, 1C7h
0x1400620bf  lea     rdi, aTermsrvWmsSrcC_21; "termsrv\\wms\\src\\common\\srcutils\\re"...
0x1400620c6  mov     r9, r15; unsigned __int16 *
0x1400620c9  mov     r8, rsi; unsigned __int16 *
0x1400620cc  mov     edx, r13d; unsigned int
0x1400620cf  mov     rcx, rdi; unsigned __int16 *
0x1400620d2  mov     ebx, r14d
0x1400620d5  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400620da  call    cs:__imp_IsDebuggerPresent
0x1400620e0  test    eax, eax
0x1400620e2  lea     rax, aPbcurbuf; "pbCurBuf"
0x1400620e9  jmp     loc_14006204A
0x1400620ee  mov     r8d, [rbp+cbData]
0x1400620f2  xor     edx, edx; Val
0x1400620f4  add     r8, 4; Size
0x1400620f8  mov     rcx, rax; void *
0x1400620fb  call    memset_0
0x140062100  lea     rax, [rbp+cbData]
0x140062104  xor     r8d, r8d; lpReserved
0x140062107  mov     [rsp+60h+lpcbData], rax; lpcbData
0x14006210c  lea     r9, [rbp+Type]; lpType
0x140062110  mov     rax, [rbp+var_18]
0x140062114  mov     rdx, rsi; lpValueName
0x140062117  mov     rcx, r13; hKey
0x14006211a  mov     [rsp+60h+lpData], rax; lpData
0x14006211f  call    cs:__imp_RegQueryValueExW
0x140062125  test    eax, eax
0x140062127  jz      short loc_140062143
0x140062129  jg      short loc_14006212F
0x14006212b  mov     ebx, eax
0x14006212d  jmp     short loc_140062138
0x14006212f  movzx   ebx, ax
0x140062132  or      ebx, 80070000h
0x140062138  mov     r13d, 1CCh
0x14006213e  jmp     loc_140061E3A
0x140062143  cmp     [rbp+Type], 7
0x140062147  jz      loc_1400621CD
0x14006214d  mov     r14d, 80004005h
0x140062153  lea     r15, aCbra; "CBRA"
0x14006215a  lea     rsi, aRegutilPrepend; "RegUtil::PrependToRegMultiSz"
0x140062161  mov     dword ptr [rsp+60h+lpcbData], r14d; int
0x140062166  lea     rdi, aTermsrvWmsSrcC_21; "termsrv\\wms\\src\\common\\srcutils\\re"...
0x14006216d  mov     r9, r15; unsigned __int16 *
0x140062170  lea     r13, aDwtype7ul; "dwType == ( 7ul )"
0x140062177  mov     r8, rsi; unsigned __int16 *
0x14006217a  mov     rcx, rdi; unsigned __int16 *
0x14006217d  mov     [rsp+60h+lpData], r13; unsigned __int16 *
0x140062182  mov     edx, 1CDh; unsigned int
0x140062187  mov     ebx, r14d
0x14006218a  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006218f  call    cs:__imp_IsDebuggerPresent
0x140062195  test    eax, eax
0x140062197  jz      short loc_1400621B3
0x140062199  mov     [rsp+60h+var_28], r14d
0x14006219e  mov     r9d, 1CDh
0x1400621a4  mov     [rsp+60h+var_30], r13
0x1400621a9  mov     [rsp+60h+lpcbData], r15
0x1400621ae  jmp     loc_140061E8B
0x1400621b3  mov     dword ptr [rsp+60h+var_30], r14d
0x1400621b8  mov     r8d, 1CDh
0x1400621be  mov     [rsp+60h+lpcbData], r13
0x1400621c3  mov     [rsp+60h+lpData], r15
0x1400621c8  jmp     loc_1400623D3
0x1400621cd  mov     rcx, [rbp+Destination]; void *
0x1400621d1  mov     r8, r14; Size
0x1400621d4  xor     edx, edx; Val
0x1400621d6  call    memset_0
0x1400621db  mov     r8, rdi; Source
0x1400621de  add     r15, r15
  ... truncated ...
```
