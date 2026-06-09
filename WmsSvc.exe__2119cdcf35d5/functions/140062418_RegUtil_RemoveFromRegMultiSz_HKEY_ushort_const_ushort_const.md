# RegUtil::RemoveFromRegMultiSz(HKEY__ *,ushort const *,ushort const *)

- ea: `0x140062418`
- end: `0x140062965`
- name: `?RemoveFromRegMultiSz@RegUtil@@YAJPEAUHKEY__@@PEBG1@Z`
- size: `1357`
- prototype: `__int64 __fastcall(HKEY hKey, HKEY lpValueName, wchar_t *String2, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140061134`
- `0x140061ce4`
- `0x14006e4d4`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140062418`
- `0x14007cb92`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x140062582`
- `ADVAPI32!RegGetValueW` at `0x1400626c1`
- `ADVAPI32!RegGetValueW` at `0x140062582`
- `ADVAPI32!RegGetValueW` at `0x1400626c1`
- `ADVAPI32!RegSetValueExW` at `0x1400627d8`
- `ADVAPI32!RegSetValueExW` at `0x1400627d8`
- `KERNEL32!IsDebuggerPresent` at `0x140062492`
- `KERNEL32!IsDebuggerPresent` at `0x140062535`
- `KERNEL32!IsDebuggerPresent` at `0x1400625e2`
- `KERNEL32!IsDebuggerPresent` at `0x140062669`
- `KERNEL32!IsDebuggerPresent` at `0x140062828`
- `KERNEL32!IsDebuggerPresent` at `0x140062892`
- `KERNEL32!IsDebuggerPresent` at `0x140062900`
- `KERNEL32!IsDebuggerPresent` at `0x140062492`
- `KERNEL32!IsDebuggerPresent` at `0x140062535`
- `KERNEL32!IsDebuggerPresent` at `0x1400625e2`
- `KERNEL32!IsDebuggerPresent` at `0x140062669`
- `KERNEL32!IsDebuggerPresent` at `0x140062828`
- `KERNEL32!IsDebuggerPresent` at `0x140062892`
- `KERNEL32!IsDebuggerPresent` at `0x140062900`
- `msvcrt!_wcsicmp` at `0x140062754`
- `msvcrt!_wcsicmp` at `0x140062754`

## string_xrefs

- `0x140062477`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x14006251a`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x1400625c1`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x140062646`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x140062804`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x14006286e`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x1400628dc`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x140062466`: `RegUtil::RemoveFromRegMultiSz`
- `0x140062508`: `RegUtil::RemoveFromRegMultiSz`
- `0x1400625b7`: `RegUtil::RemoveFromRegMultiSz`
- `0x140062636`: `RegUtil::RemoveFromRegMultiSz`
- `0x1400627f7`: `RegUtil::RemoveFromRegMultiSz`
- `0x140062861`: `RegUtil::RemoveFromRegMultiSz`
- `0x1400628cb`: `RegUtil::RemoveFromRegMultiSz`
- `0x1400624f5`: `pszStringToRemove != 0`
- `0x14006253d`: `pszStringToRemove != 0`
- `0x14006254c`: `RegUtil::RemoveFromRegMultiSz - Removing %s from value %s\n`
- `0x140062761`: `RegUtil::RemoveFromRegMultiSz - Found string to remove.\n`

## pseudocode

```c
__int64 __fastcall RegUtil::RemoveFromRegMultiSz(
        HKEY hKey,
        const WCHAR *lpValueName,
        wchar_t *String2,
        const unsigned __int16 *a4)
{
  __int64 v4; // r13
  HKEY v7; // r14
  _WORD *v8; // r15
  unsigned int v9; // r12d
  unsigned int v10; // ebx
  bool v11; // zf
  const unsigned __int16 *v12; // rax
  __int64 v13; // r9
  LSTATUS ValueW; // eax
  LSTATUS v15; // eax
  _WORD *v16; // rdi
  _WORD *v17; // rsi
  __int64 v18; // rdx
  _WORD *v19; // rax
  __int64 v20; // r8
  size_t v21; // rbx
  __int64 v22; // rdx
  __int64 v23; // r8
  LSTATUS v24; // eax
  __int64 v25; // r8
  unsigned int v26; // r13d
  const unsigned __int16 *pvData; // [rsp+28h] [rbp-50h]
  const unsigned __int16 *pvDataa; // [rsp+28h] [rbp-50h]
  LPDWORD pcbData; // [rsp+30h] [rbp-48h]
  const unsigned __int16 *pcbDataa; // [rsp+30h] [rbp-48h]
  int v32; // [rsp+38h] [rbp-40h]
  DWORD v34; // [rsp+88h] [rbp+10h] BYREF
  __int64 v35; // [rsp+98h] [rbp+20h]

  v4 = 0;
  v34 = 0;
  v7 = hKey;
  v8 = 0;
  if ( !lpValueName )
  {
    v9 = 271;
    v10 = -2147024809;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
      0x10Fu,
      L"RegUtil::RemoveFromRegMultiSz",
      L"CBRAEx",
      L"pszValueName != 0",
      -2147024809);
    v11 = !IsDebuggerPresent();
    v12 = L"pszValueName != 0";
LABEL_3:
    if ( !v11 )
    {
      v32 = -2147024809;
      pcbDataa = v12;
LABEL_5:
      pvData = L"CBRAEx";
LABEL_6:
      v13 = v9;
LABEL_7:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
        v13,
        L"RegUtil::RemoveFromRegMultiSz",
        pvData,
        pcbDataa,
        v32);
      goto LABEL_57;
    }
    LODWORD(pcbData) = -2147024809;
    pvDataa = v12;
    goto LABEL_9;
  }
  if ( !String2 )
  {
    v9 = 272;
    v10 = -2147024809;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
      0x110u,
      L"RegUtil::RemoveFromRegMultiSz",
      L"CBRAEx",
      L"pszStringToRemove != 0",
      -2147024809);
    v11 = !IsDebuggerPresent();
    v12 = L"pszStringToRemove != 0";
    goto LABEL_3;
  }
  DEBUGMSG(L"RegUtil::RemoveFromRegMultiSz - Removing %s from value %s\n", String2, lpValueName, a4);
  ValueW = RegGetValueW(v7, 0, lpValueName, 0x20u, 0, 0, &v34);
  v10 = ValueW;
  if ( ValueW == 2 )
  {
LABEL_13:
    v10 = 0;
    goto LABEL_57;
  }
  if ( ValueW )
  {
    if ( ValueW > 0 )
      v10 = (unsigned __int16)ValueW | 0x80070000;
    v9 = 289;
LABEL_18:
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
      v9,
      L"RegUtil::RemoveFromRegMultiSz",
      L"CBRAEx",
      L"lResult == 0L",
      v10);
    if ( IsDebuggerPresent() )
    {
      v32 = v10;
      pcbDataa = L"lResult == 0L";
      goto LABEL_5;
    }
    LODWORD(pcbData) = v10;
    pvDataa = L"lResult == 0L";
LABEL_9:
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
      v9,
      L"RegUtil::RemoveFromRegMultiSz",
      L"CBRAEx",
      pvDataa,
      pcbData);
    goto LABEL_57;
  }
  if ( v34 <= 1 )
    goto LABEL_13;
  v8 = operator new(v34);
  if ( v8 )
  {
    v15 = RegGetValueW(v7, 0, lpValueName, 0x20u, 0, v8, &v34);
    v10 = v15;
    if ( v15 )
    {
      if ( v15 > 0 )
        v10 = (unsigned __int16)v15 | 0x80070000;
      v9 = 304;
      goto LABEL_18;
    }
    v16 = v8;
    v17 = v8;
    if ( *v8 )
    {
      while ( 1 )
      {
        v18 = 0x7FFFFFFF;
        v19 = v16;
        do
        {
          if ( !*v19 )
            break;
          ++v19;
          --v18;
        }
        while ( v18 );
        v10 = v18 == 0 ? 0x80070057 : 0;
        v20 = (0x7FFFFFFF - v18) & -(__int64)(v18 != 0);
        if ( !v18 )
          break;
        v35 = v20 + 1;
        v21 = 2 * (v20 + 1);
        if ( _wcsicmp(v16, String2) )
        {
          DEBUGMSG(L"RegUtil::RemoveFromRegMultiSz - Found string to remove.\n", v22, v23, 0);
          if ( v17 != v16 )
            memmove_0(v17, v16, v21);
          v4 += v35;
          v17 = (_WORD *)((char *)v17 + v21);
        }
        v16 = (_WORD *)((char *)v16 + v21);
        if ( !*v16 )
        {
          v7 = hKey;
          goto LABEL_41;
        }
      }
      v9 = 320;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
        0x140u,
        L"RegUtil::RemoveFromRegMultiSz",
        L"CHRA",
        L"hr",
        v10);
      if ( IsDebuggerPresent() )
      {
        v32 = v10;
        pcbDataa = L"hr";
        pvData = L"CHRA";
        goto LABEL_6;
      }
      v25 = 320;
LABEL_56:
      LODWORD(pcbData) = v10;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
        v25,
        L"RegUtil::RemoveFromRegMultiSz",
        L"CHRA",
        L"hr",
        pcbData);
      goto LABEL_57;
    }
LABEL_41:
    *v17 = 0;
    if ( (unsigned __int64)(v4 + 1) > 0xFFFFFFFF )
    {
      v10 = -2147024362;
      v26 = 362;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
        0x16Au,
        L"RegUtil::RemoveFromRegMultiSz",
        L"CHRA",
        L"hr",
        -2147024362);
      if ( !IsDebuggerPresent() )
      {
        v25 = 362;
        goto LABEL_56;
      }
      v32 = -2147024362;
      pcbDataa = L"hr";
      pvData = L"CHRA";
    }
    else
    {
      v10 = 0;
      v24 = RegSetValueExW(v7, lpValueName, 0, 7u, (const BYTE *)v8, 2 * (v4 + 1));
      if ( !v24 )
        goto LABEL_57;
      if ( v24 > 0 )
        v10 = (unsigned __int16)v24 | 0x80070000;
      else
        v10 = v24;
      v26 = 365;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
        0x16Du,
        L"RegUtil::RemoveFromRegMultiSz",
        L"CBRAEx",
        L"lResult == 0L",
        v10);
      if ( !IsDebuggerPresent() )
      {
        LODWORD(pcbData) = v10;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
          365,
          L"RegUtil::RemoveFromRegMultiSz",
          L"CBRAEx",
          L"lResult == 0L",
          pcbData);
        goto LABEL_57;
      }
      v32 = v10;
      pcbDataa = L"lResult == 0L";
      pvData = L"CBRAEx";
    }
    v13 = v26;
    goto LABEL_7;
  }
  v10 = -2147024882;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
    0x129u,
    L"RegUtil::RemoveFromRegMultiSz",
    L"CPR",
    L"pbBuf",
    -2147024882);
  if ( IsDebuggerPresent() )
  {
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
      297,
      L"RegUtil::RemoveFromRegMultiSz",
      L"CPR",
      L"pbBuf",
      -2147024882);
  }
  else
  {
    LODWORD(pcbData) = -2147024882;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
      297,
      L"RegUtil::RemoveFromRegMultiSz",
      L"CPR",
      L"pbBuf",
      pcbData);
  }
LABEL_57:
  operator delete(v8);
  return v10;
}

```

## disassembly

```asm
0x140062418  mov     r11, rsp
0x14006241b  mov     [r11+18h], rbx
0x14006241f  mov     [r11+8], rcx
0x140062423  push    rbp
0x140062424  push    rsi
0x140062425  push    rdi
0x140062426  push    r12
0x140062428  push    r13
0x14006242a  push    r14
0x14006242c  push    r15
0x14006242e  sub     rsp, 40h
0x140062432  xor     r13d, r13d
0x140062435  mov     r12, r8
0x140062438  mov     [r11+10h], r13d
0x14006243c  mov     rbp, rdx
0x14006243f  mov     r14, rcx
0x140062442  mov     r15d, r13d
0x140062445  test    rdx, rdx
0x140062448  jnz     loc_1400624EA
0x14006244e  mov     r14d, 80070057h
0x140062454  lea     rax, aPszvaluename0; "pszValueName != 0"
0x14006245b  mov     [r11-50h], r14d
0x14006245f  lea     rbp, aCbraex; "CBRAEx"
0x140062466  lea     rsi, aRegutilRemovef_1; "RegUtil::RemoveFromRegMultiSz"
0x14006246d  mov     [r11-58h], rax
0x140062471  mov     r12d, 10Fh
0x140062477  lea     rdi, aTermsrvWmsSrcC_21; "termsrv\\wms\\src\\common\\srcutils\\re"...
0x14006247e  mov     r9, rbp; unsigned __int16 *
0x140062481  mov     r8, rsi; unsigned __int16 *
0x140062484  mov     edx, r12d; unsigned int
0x140062487  mov     rcx, rdi; unsigned __int16 *
0x14006248a  mov     ebx, r14d
0x14006248d  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140062492  call    cs:__imp_IsDebuggerPresent
0x140062498  test    eax, eax
0x14006249a  lea     rax, aPszvaluename0; "pszValueName != 0"
0x1400624a1  jz      short loc_1400624D3
0x1400624a3  mov     [rsp+78h+var_40], r14d
0x1400624a8  mov     [rsp+78h+pcbData], rax
0x1400624ad  mov     [rsp+78h+pvData], rbp
0x1400624b2  mov     r9d, r12d
0x1400624b5  mov     r8, rdi
0x1400624b8  mov     [rsp+78h+pdwType], rsi
0x1400624bd  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400624c4  mov     ecx, 2; unsigned __int8
0x1400624c9  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400624ce  jmp     loc_140062943
0x1400624d3  mov     dword ptr [rsp+78h+pcbData], r14d
0x1400624d8  mov     [rsp+78h+pvData], rax
0x1400624dd  mov     [rsp+78h+pdwType], rbp
0x1400624e2  mov     r8d, r12d
0x1400624e5  jmp     loc_140062931
0x1400624ea  test    r12, r12
0x1400624ed  jnz     short loc_140062549
0x1400624ef  mov     r14d, 80070057h
0x1400624f5  lea     rax, aPszstringtorem; "pszStringToRemove != 0"
0x1400624fc  lea     rbp, aCbraex; "CBRAEx"
0x140062503  mov     dword ptr [rsp+78h+pvData], r14d; int
0x140062508  lea     rsi, aRegutilRemovef_1; "RegUtil::RemoveFromRegMultiSz"
0x14006250f  mov     [rsp+78h+pdwType], rax; unsigned __int16 *
0x140062514  mov     r12d, 110h
0x14006251a  lea     rdi, aTermsrvWmsSrcC_21; "termsrv\\wms\\src\\common\\srcutils\\re"...
0x140062521  mov     r9, rbp; unsigned __int16 *
0x140062524  mov     r8, rsi; unsigned __int16 *
0x140062527  mov     edx, r12d; unsigned int
0x14006252a  mov     rcx, rdi; unsigned __int16 *
0x14006252d  mov     ebx, r14d
0x140062530  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140062535  call    cs:__imp_IsDebuggerPresent
0x14006253b  test    eax, eax
0x14006253d  lea     rax, aPszstringtorem; "pszStringToRemove != 0"
0x140062544  jmp     loc_1400624A1
0x140062549  mov     r8, rbp
0x14006254c  lea     rcx, aRegutilRemovef_0; "RegUtil::RemoveFromRegMultiSz - Removin"...
0x140062553  mov     rdx, r12
0x140062556  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14006255b  lea     rax, [rsp+78h+arg_8]
0x140062563  mov     edi, 20h ; ' '
0x140062568  mov     [rsp+78h+pcbData], rax; pcbData
0x14006256d  mov     r9d, edi; dwFlags
0x140062570  mov     [rsp+78h+pvData], r13; pvData
0x140062575  mov     r8, rbp; lpValue
0x140062578  xor     edx, edx; lpSubKey
0x14006257a  mov     [rsp+78h+pdwType], r13; pdwType
0x14006257f  mov     rcx, r14; hkey
0x140062582  call    cs:__imp_RegGetValueW
0x140062588  mov     ebx, eax
0x14006258a  cmp     eax, 2
0x14006258d  jnz     short loc_140062597
0x14006258f  mov     ebx, r13d
0x140062592  jmp     loc_140062943
0x140062597  test    eax, eax
0x140062599  jz      short loc_140062608
0x14006259b  jle     short loc_1400625A6
0x14006259d  movzx   ebx, ax
0x1400625a0  or      ebx, 80070000h
0x1400625a6  mov     r12d, 121h
0x1400625ac  lea     rbp, aCbraex; "CBRAEx"
0x1400625b3  mov     dword ptr [rsp+78h+pvData], ebx; int
0x1400625b7  lea     rsi, aRegutilRemovef_1; "RegUtil::RemoveFromRegMultiSz"
0x1400625be  mov     r9, rbp; unsigned __int16 *
0x1400625c1  lea     rdi, aTermsrvWmsSrcC_21; "termsrv\\wms\\src\\common\\srcutils\\re"...
0x1400625c8  mov     r8, rsi; unsigned __int16 *
0x1400625cb  lea     r14, aLresult0l; "lResult == 0L"
0x1400625d2  mov     rcx, rdi; unsigned __int16 *
0x1400625d5  mov     edx, r12d; unsigned int
0x1400625d8  mov     [rsp+78h+pdwType], r14; unsigned __int16 *
0x1400625dd  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400625e2  call    cs:__imp_IsDebuggerPresent
0x1400625e8  test    eax, eax
0x1400625ea  jz      short loc_1400625FA
0x1400625ec  mov     [rsp+78h+var_40], ebx
0x1400625f0  mov     [rsp+78h+pcbData], r14
0x1400625f5  jmp     loc_1400624AD
0x1400625fa  mov     dword ptr [rsp+78h+pcbData], ebx
0x1400625fe  mov     [rsp+78h+pvData], r14
0x140062603  jmp     loc_1400624DD
0x140062608  cmp     [rsp+78h+arg_8], 1
0x140062610  jbe     loc_14006258F
0x140062616  mov     ecx, [rsp+78h+arg_8]; Size
0x14006261d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140062622  mov     r15, rax
0x140062625  test    rax, rax
0x140062628  jnz     short loc_14006269F
0x14006262a  mov     ebx, 8007000Eh
0x14006262f  lea     r12, aCpr; "CPR"
0x140062636  lea     rsi, aRegutilRemovef_1; "RegUtil::RemoveFromRegMultiSz"
0x14006263d  mov     dword ptr [rsp+78h+pvData], ebx; int
0x140062641  mov     ebp, 129h
0x140062646  lea     rdi, aTermsrvWmsSrcC_21; "termsrv\\wms\\src\\common\\srcutils\\re"...
0x14006264d  lea     r14, aPbbuf; "pbBuf"
0x140062654  mov     r9, r12; unsigned __int16 *
0x140062657  mov     r8, rsi; unsigned __int16 *
0x14006265a  mov     [rsp+78h+pdwType], r14; unsigned __int16 *
0x14006265f  mov     edx, ebp; unsigned int
0x140062661  mov     rcx, rdi; unsigned __int16 *
0x140062664  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140062669  call    cs:__imp_IsDebuggerPresent
0x14006266f  test    eax, eax
0x140062671  jz      short loc_140062689
0x140062673  mov     [rsp+78h+var_40], ebx
0x140062677  mov     r9d, ebp
0x14006267a  mov     [rsp+78h+pcbData], r14
0x14006267f  mov     [rsp+78h+pvData], r12
0x140062684  jmp     loc_1400624B5
0x140062689  mov     dword ptr [rsp+78h+pcbData], ebx
0x14006268d  mov     r8d, ebp
0x140062690  mov     [rsp+78h+pvData], r14
0x140062695  mov     [rsp+78h+pdwType], r12
0x14006269a  jmp     loc_140062931
0x14006269f  lea     rax, [rsp+78h+arg_8]
0x1400626a7  mov     r9d, edi; dwFlags
0x1400626aa  mov     [rsp+78h+pcbData], rax; pcbData
0x1400626af  mov     r8, rbp; lpValue
0x1400626b2  mov     [rsp+78h+pvData], r15; pvData
0x1400626b7  xor     edx, edx; lpSubKey
0x1400626b9  mov     rcx, r14; hkey
0x1400626bc  mov     [rsp+78h+pdwType], r13; pdwType
0x1400626c1  call    cs:__imp_RegGetValueW
0x1400626c7  mov     ebx, eax
0x1400626c9  test    eax, eax
0x1400626cb  jz      short loc_1400626E3
0x1400626cd  jle     short loc_1400626D8
0x1400626cf  movzx   ebx, ax
0x1400626d2  or      ebx, 80070000h
0x1400626d8  mov     r12d, 130h
0x1400626de  jmp     loc_1400625AC
0x1400626e3  xor     r9d, r9d
0x1400626e6  mov     rdi, r15
0x1400626e9  mov     rsi, r15
0x1400626ec  cmp     [r15], r9w
0x1400626f0  jz      loc_1400627A3
0x1400626f6  mov     r14d, 80070057h
0x1400626fc  mov     edx, 7FFFFFFFh
0x140062701  mov     rax, rdi
0x140062704  cmp     [rax], r9w
0x140062708  jz      short loc_140062714
0x14006270a  add     rax, 2
0x14006270e  sub     rdx, 1
0x140062712  jnz     short loc_140062704
0x140062714  mov     rax, rdx
0x140062717  mov     ecx, 7FFFFFFFh
0x14006271c  neg     rax
0x14006271f  mov     rax, rdx
0x140062722  sbb     ebx, ebx
0x140062724  sub     rcx, rdx
0x140062727  not     ebx
0x140062729  and     ebx, r14d
0x14006272c  neg     rax
0x14006272f  sbb     r8, r8
0x140062732  and     r8, rcx
0x140062735  test    rdx, rdx
0x140062738  jz      loc_1400627EC
0x14006273e  lea     rax, [r8+1]
0x140062742  mov     rdx, r12; String2
0x140062745  mov     rcx, rdi; String1
0x140062748  mov     [rsp+78h+arg_18], rax
0x140062750  lea     rbx, [rax+rax]
0x140062754  call    cs:__imp__wcsicmp
0x14006275a  xor     r9d, r9d
0x14006275d  test    eax, eax
0x14006275f  jz      short loc_14006278E
0x140062761  lea     rcx, aRegutilRemovef; "RegUtil::RemoveFromRegMultiSz - Found s"...
0x140062768  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14006276d  cmp     rsi, rdi
0x140062770  jz      short loc_140062780
0x140062772  mov     r8, rbx; Size
0x140062775  mov     rdx, rdi; Src
0x140062778  mov     rcx, rsi; void *
0x14006277b  call    memmove_0
0x140062780  add     r13, [rsp+78h+arg_18]
0x140062788  add     rsi, rbx
0x14006278b  xor     r9d, r9d
0x14006278e  add     rdi, rbx
0x140062791  cmp     [rdi], r9w
0x140062795  jnz     loc_1400626FC
0x14006279b  mov     r14, [rsp+78h+arg_0]
0x1400627a3  xor     r12d, r12d
0x1400627a6  lea     rax, [r13+1]
0x1400627aa  mov     ecx, 0FFFFFFFFh
0x1400627af  mov     [rsi], r12w
0x1400627b3  cmp     rax, rcx
0x1400627b6  ja      loc_1400628BF
0x1400627bc  add     eax, eax
0x1400627be  lea     r9d, [r12+7]; dwType
0x1400627c3  mov     dword ptr [rsp+78h+pvData], eax; cbData
0x1400627c7  xor     r8d, r8d; Reserved
0x1400627ca  mov     rdx, rbp; lpValueName
0x1400627cd  mov     [rsp+78h+pdwType], r15; lpData
0x1400627d2  mov     rcx, r14; hKey
0x1400627d5  mov     ebx, r12d
0x1400627d8  call    cs:__imp_RegSetValueExW
0x1400627de  test    eax, eax
0x1400627e0  jz      loc_140062943
0x1400627e6  jg      short loc_14006284D
0x1400627e8  mov     ebx, eax
0x1400627ea  jmp     short loc_140062856
0x1400627ec  lea     r14, aChra; "CHRA"
0x1400627f3  mov     dword ptr [rsp+78h+pvData], ebx; int
0x1400627f7  lea     rsi, aRegutilRemovef_1; "RegUtil::RemoveFromRegMultiSz"
0x1400627fe  mov     r12d, 140h
0x140062804  lea     rdi, aTermsrvWmsSrcC_21; "termsrv\\wms\\src\\common\\srcutils\\re"...
0x14006280b  mov     r9, r14; unsigned __int16 *
0x14006280e  lea     rbp, aHr; "hr"
0x140062815  mov     r8, rsi; unsigned __int16 *
0x140062818  mov     edx, r12d; unsigned int
0x14006281b  mov     [rsp+78h+pdwType], rbp; unsigned __int16 *
0x140062820  mov     rcx, rdi; unsigned __int16 *
0x140062823  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140062828  call    cs:__imp_IsDebuggerPresent
0x14006282e  test    eax, eax
0x140062830  jz      short loc_140062845
0x140062832  mov     [rsp+78h+var_40], ebx
0x140062836  mov     [rsp+78h+pcbData], rbp
0x14006283b  mov     [rsp+78h+pvData], r14
0x140062840  jmp     loc_1400624B2
0x140062845  mov     r8d, r12d
0x140062848  jmp     loc_140062923
0x14006284d  movzx   ebx, ax
0x140062850  or      ebx, 80070000h
0x140062856  lea     rbp, aCbraex; "CBRAEx"
0x14006285d  mov     dword ptr [rsp+78h+pvData], ebx; int
0x140062861  lea     rsi, aRegutilRemovef_1; "RegUtil::RemoveFromRegMultiSz"
0x140062868  mov     r13d, 16Dh
0x14006286e  lea     rdi, aTermsrvWmsSrcC_21; "termsrv\\wms\\src\\common\\srcutils\\re"...
0x140062875  mov     r9, rbp; unsigned __int16 *
0x140062878  lea     r14, aLresult0l; "lResult == 0L"
0x14006287f  mov     r8, rsi; unsigned __int16 *
0x140062882  mov     edx, r13d; unsigned int
0x140062885  mov     [rsp+78h+pdwType], r14; unsigned __int16 *
0x14006288a  mov     rcx, rdi; unsigned __int16 *
0x14006288d  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140062892  call    cs:__imp_IsDebuggerPresent
0x140062898  test    eax, eax
0x14006289a  jz      short loc_1400628AC
0x14006289c  mov     [rsp+78h+var_40], ebx
0x1400628a0  mov     [rsp+78h+pcbData], r14
0x1400628a5  mov     [rsp+78h+pvData], rbp
0x1400628aa  jmp     short loc_140062918
0x1400628ac  mov     dword ptr [rsp+78h+pcbData], ebx
0x1400628b0  mov     r8d, r13d
0x1400628b3  mov     [rsp+78h+pvData], r14
0x1400628b8  mov     [rsp+78h+pdwType], rbp
0x1400628bd  jmp     short loc_140062931
0x1400628bf  mov     ebx, 80070216h
0x1400628c4  lea     r14, aChra; "CHRA"
0x1400628cb  lea     rsi, aRegutilRemovef_1; "RegUtil::RemoveFromRegMultiSz"
0x1400628d2  mov     dword ptr [rsp+78h+pvData], ebx; int
0x1400628d6  mov     r13d, 16Ah
0x1400628dc  lea     rdi, aTermsrvWmsSrcC_21; "termsrv\\wms\\src\\common\\srcutils\\re"...
0x1400628e3  lea     rbp, aHr; "hr"
0x1400628ea  mov     r9, r14; unsigned __int16 *
0x1400628ed  mov     r8, rsi; unsigned __int16 *
0x1400628f0  mov     [rsp+78h+pdwType], rbp; unsigned __int16 *
0x1400628f5  mov     edx, r13d; unsigned int
0x1400628f8  mov     rcx, rdi; unsigned __int16 *
0x1400628fb  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140062900  call    cs:__imp_IsDebuggerPresent
0x140062906  test    eax, eax
0x140062908  jz      short loc_140062920
  ... truncated ...
```
