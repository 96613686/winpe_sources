# RegUtil::AppendToRegMultiSz(HKEY__ *,ushort const *,ushort const *)

- ea: `0x140061134`
- end: `0x140061a05`
- name: `?AppendToRegMultiSz@RegUtil@@YAJPEAUHKEY__@@PEBG1@Z`
- size: `2257`
- prototype: `__int64 __fastcall(HKEY hkey, HKEY lpValueName, wchar_t *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140010d60`
- `0x14006dcf0`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x140005518`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140061134`
- `0x140062418`
- `0x14007cb9e`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x1400612b9`
- `ADVAPI32!RegGetValueW` at `0x1400614ad`
- `ADVAPI32!RegGetValueW` at `0x1400612b9`
- `ADVAPI32!RegGetValueW` at `0x1400614ad`
- `ADVAPI32!RegSetValueExW` at `0x14006193d`
- `ADVAPI32!RegSetValueExW` at `0x14006193d`
- `KERNEL32!IsDebuggerPresent` at `0x1400611b5`
- `KERNEL32!IsDebuggerPresent` at `0x140061253`
- `KERNEL32!IsDebuggerPresent` at `0x140061311`
- `KERNEL32!IsDebuggerPresent` at `0x14006138f`
- `KERNEL32!IsDebuggerPresent` at `0x140061432`
- `KERNEL32!IsDebuggerPresent` at `0x1400614fc`
- `KERNEL32!IsDebuggerPresent` at `0x140061607`
- `KERNEL32!IsDebuggerPresent` at `0x140061666`
- `KERNEL32!IsDebuggerPresent` at `0x14006172e`
- `KERNEL32!IsDebuggerPresent` at `0x14006184c`
- `KERNEL32!IsDebuggerPresent` at `0x1400618b7`
- `KERNEL32!IsDebuggerPresent` at `0x140061992`
- `KERNEL32!IsDebuggerPresent` at `0x1400611b5`
- `KERNEL32!IsDebuggerPresent` at `0x140061253`
- `KERNEL32!IsDebuggerPresent` at `0x140061311`
- `KERNEL32!IsDebuggerPresent` at `0x14006138f`
- `KERNEL32!IsDebuggerPresent` at `0x140061432`
- `KERNEL32!IsDebuggerPresent` at `0x1400614fc`
- `KERNEL32!IsDebuggerPresent` at `0x140061607`
- `KERNEL32!IsDebuggerPresent` at `0x140061666`
- `KERNEL32!IsDebuggerPresent` at `0x14006172e`
- `KERNEL32!IsDebuggerPresent` at `0x14006184c`
- `KERNEL32!IsDebuggerPresent` at `0x1400618b7`
- `KERNEL32!IsDebuggerPresent` at `0x140061992`

## string_xrefs

- `0x140061195`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x140061238`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x1400612ed`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x140061377`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x140061416`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x1400614d9`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x1400615e4`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x140061643`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x140061712`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x140061829`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x140061894`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x14006196f`: `termsrv\wms\src\common\srcutils\registry.cpp`

## pseudocode

```c
__int64 __fastcall RegUtil::AppendToRegMultiSz(HKEY hkey, HKEY lpValueName, wchar_t *a3, const unsigned __int16 *a4)
{
  BYTE *v7; // r13
  unsigned int v8; // r15d
  signed int v9; // ebx
  bool v10; // zf
  const unsigned __int16 *v11; // rax
  __int64 v12; // r9
  const unsigned __int16 *v13; // r9
  LSTATUS ValueW; // eax
  __int64 v15; // r8
  unsigned __int64 v16; // rbx
  void *v17; // rax
  LSTATUS v18; // eax
  _WORD *v19; // rdi
  __int64 v20; // rdx
  _WORD *v21; // rax
  __int64 v22; // rdx
  wchar_t *v23; // rax
  __int64 v24; // r8
  unsigned __int64 v25; // rdi
  unsigned __int64 v26; // rsi
  BYTE *v27; // rax
  _WORD *v28; // rcx
  unsigned __int64 v29; // rax
  unsigned __int64 v30; // rdx
  BYTE *v31; // r8
  BYTE *v32; // rcx
  int v33; // eax
  __int16 v34; // r11
  LSTATUS v35; // eax
  const unsigned __int16 *pvData; // [rsp+28h] [rbp-60h]
  const unsigned __int16 *pcbData; // [rsp+30h] [rbp-58h]
  LPDWORD pcbDataa; // [rsp+30h] [rbp-58h]
  int v40; // [rsp+38h] [rbp-50h]
  unsigned __int64 v41; // [rsp+40h] [rbp-48h]
  DWORD v43; // [rsp+98h] [rbp+10h] BYREF
  PVOID Block; // [rsp+A8h] [rbp+20h]

  v43 = 0;
  Block = 0;
  v7 = 0;
  if ( !lpValueName )
  {
    v8 = 543;
    v9 = -2147024809;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
      0x21Fu,
      L"RegUtil::AppendToRegMultiSz",
      L"CBRAEx",
      L"pszValueName != 0",
      -2147024809);
    v10 = !IsDebuggerPresent();
    v11 = L"pszValueName != 0";
LABEL_3:
    if ( v10 )
    {
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
        v8,
        L"RegUtil::AppendToRegMultiSz",
        L"CBRAEx",
        v11,
        -2147024809);
      goto LABEL_82;
    }
    v40 = -2147024809;
    pcbData = v11;
    goto LABEL_5;
  }
  if ( !a3 )
  {
    v8 = 544;
    v9 = -2147024809;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
      0x220u,
      L"RegUtil::AppendToRegMultiSz",
      L"CBRAEx",
      L"pszString != 0",
      -2147024809);
    v10 = !IsDebuggerPresent();
    v11 = L"pszString != 0";
    goto LABEL_3;
  }
  DEBUGMSG(L"RegUtil::AppendToRegMultiSz - Appending %s to value %s\n", a3, lpValueName, a4);
  v9 = RegUtil::RemoveFromRegMultiSz(hkey, lpValueName, a3, v13);
  if ( v9 < 0 )
    goto LABEL_82;
  ValueW = RegGetValueW(hkey, 0, (LPCWSTR)lpValueName, 0x20u, 0, 0, &v43);
  v9 = ValueW;
  if ( (ValueW & 0xFFFFFFFD) == 0 )
  {
    if ( v43 )
    {
      if ( (v43 & 1) != 0 )
      {
        v9 = -2147418113;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
          0x23Bu,
          L"RegUtil::AppendToRegMultiSz",
          L"CBRAEx",
          L"(cbCurBuf % sizeof (WCHAR)) == 0",
          -2147418113);
        if ( !IsDebuggerPresent() )
        {
          LODWORD(pcbDataa) = -2147418113;
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
            571,
            L"RegUtil::AppendToRegMultiSz",
            L"CBRAEx",
            L"(cbCurBuf % sizeof (WCHAR)) == 0",
            pcbDataa);
          goto LABEL_82;
        }
        v40 = -2147418113;
        v12 = 571;
        pcbData = L"(cbCurBuf % sizeof (WCHAR)) == 0";
        goto LABEL_21;
      }
      v16 = (unsigned __int64)v43 >> 1;
      v17 = operator new(saturated_mul(v16, 2u));
      Block = v17;
      if ( !v17 )
      {
        v9 = -2147024882;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
          0x23Fu,
          L"RegUtil::AppendToRegMultiSz",
          L"CPR",
          L"pszCurBuf",
          -2147024882);
        if ( !IsDebuggerPresent() )
        {
          LODWORD(pcbDataa) = -2147024882;
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
            575,
            L"RegUtil::AppendToRegMultiSz",
            L"CPR",
            L"pszCurBuf",
            pcbDataa);
          goto LABEL_82;
        }
        v40 = -2147024882;
        v12 = 575;
        pcbData = L"pszCurBuf";
        pvData = L"CPR";
        goto LABEL_6;
      }
      memset_0(v17, 0, 2 * v16);
      v18 = RegGetValueW(hkey, 0, (LPCWSTR)lpValueName, 0x20u, 0, Block, &v43);
      v9 = v18;
      if ( v18 )
      {
        if ( v18 > 0 )
          v9 = (unsigned __int16)v18 | 0x80070000;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
          0x244u,
          L"RegUtil::AppendToRegMultiSz",
          L"CBRAEx",
          L"lResult == 0L",
          v9);
        if ( !IsDebuggerPresent() )
        {
          v15 = 580;
          goto LABEL_81;
        }
        v40 = v9;
        v12 = 580;
        pcbData = L"lResult == 0L";
LABEL_21:
        pvData = L"CBRAEx";
        goto LABEL_6;
      }
    }
    v19 = Block;
    if ( Block && *(_WORD *)Block )
    {
      while ( 1 )
      {
        v20 = 0x7FFFFFFF;
        v21 = v19;
        do
        {
          if ( !*v21 )
            break;
          ++v21;
          --v20;
        }
        while ( v20 );
        v9 = v20 == 0 ? 0x80070057 : 0;
        if ( !v20 )
          break;
        v19 += ((0x7FFFFFFF - v20) & -(__int64)(v20 != 0)) + 1;
        if ( !*v19 )
          goto LABEL_40;
      }
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
        0x252u,
        L"RegUtil::AppendToRegMultiSz",
        L"CHRA",
        L"hr",
        v9);
      if ( !IsDebuggerPresent() )
      {
        LODWORD(pcbDataa) = v9;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
          594,
          L"RegUtil::AppendToRegMultiSz",
          L"CHRA",
          L"hr",
          pcbDataa);
        goto LABEL_82;
      }
      v40 = v9;
      v12 = 594;
      pcbData = L"hr";
      pvData = L"CHRA";
      goto LABEL_6;
    }
LABEL_40:
    v22 = 0x7FFFFFFF;
    v23 = a3;
    do
    {
      if ( !*v23 )
        break;
      ++v23;
      --v22;
    }
    while ( v22 );
    v9 = v22 == 0 ? 0x80070057 : 0;
    v24 = (0x7FFFFFFF - v22) & -(__int64)(v22 != 0);
    if ( !v22 )
    {
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
        0x264u,
        L"RegUtil::AppendToRegMultiSz",
        L"CHRA",
        L"hr",
        -2147024809);
      if ( !IsDebuggerPresent() )
      {
        LODWORD(pcbDataa) = v9;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
          612,
          L"RegUtil::AppendToRegMultiSz",
          L"CHRA",
          L"hr",
          pcbDataa);
        goto LABEL_82;
      }
      v40 = v9;
      v12 = 612;
      pcbData = L"hr";
      pvData = L"CHRA";
      goto LABEL_6;
    }
    v25 = ((char *)v19 - (_BYTE *)Block) >> 1;
    v41 = v25 + v24;
    v26 = v25 + v24 + 2;
    v27 = (BYTE *)operator new(saturated_mul(v26, 2u));
    v7 = v27;
    if ( !v27 )
    {
      v9 = -2147024882;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
        0x26Du,
        L"RegUtil::AppendToRegMultiSz",
        L"CPR",
        L"pszNewBuf",
        -2147024882);
      if ( !IsDebuggerPresent() )
      {
        LODWORD(pcbDataa) = -2147024882;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
          621,
          L"RegUtil::AppendToRegMultiSz",
          L"CPR",
          L"pszNewBuf",
          pcbDataa);
        goto LABEL_82;
      }
      v40 = -2147024882;
      v12 = 621;
      pcbData = L"pszNewBuf";
      pvData = L"CPR";
      goto LABEL_6;
    }
    if ( v25 )
    {
      if ( v26 )
      {
        if ( v26 > 0x7FFFFFFF || v25 > 0x7FFFFFFE )
        {
          v9 = -2147024809;
          *(_WORD *)v27 = 0;
        }
        else
        {
          v28 = Block;
          v29 = v25;
          v30 = v26;
          v31 = v7;
          do
          {
            if ( !v29 )
              break;
            if ( !*v28 )
              break;
            *(_WORD *)v31 = *v28++;
            v31 += 2;
            --v29;
            --v30;
          }
          while ( v30 );
          v32 = v31 - 2;
          v9 = v30 == 0 ? 0x8007007A : 0;
          if ( v30 )
            v32 = v31;
          *(_WORD *)v32 = 0;
          if ( v30 )
            goto LABEL_66;
        }
      }
      else
      {
        v9 = -2147024809;
      }
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
        0x276u,
        L"RegUtil::AppendToRegMultiSz",
        L"CHRA",
        L"hr",
        v9);
      if ( !IsDebuggerPresent() )
      {
        LODWORD(pcbDataa) = v9;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
          630,
          L"RegUtil::AppendToRegMultiSz",
          L"CHRA",
          L"hr",
          pcbDataa);
        goto LABEL_82;
      }
      v40 = v9;
      v12 = 630;
      pcbData = L"hr";
      pvData = L"CHRA";
      goto LABEL_6;
    }
LABEL_66:
    v33 = StringCchCopyW((unsigned __int16 *)&v7[2 * v25], v26 - v25, a3);
    v9 = v33;
    if ( v33 < 0 )
    {
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
        0x27Cu,
        L"RegUtil::AppendToRegMultiSz",
        L"CHRA",
        L"hr",
        v33);
      if ( !IsDebuggerPresent() )
      {
        LODWORD(pcbDataa) = v9;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
          636,
          L"RegUtil::AppendToRegMultiSz",
          L"CHRA",
          L"hr",
          pcbDataa);
        goto LABEL_82;
      }
      v40 = v9;
      v12 = 636;
      pcbData = L"hr";
      pvData = L"CHRA";
      goto LABEL_6;
    }
    *(_WORD *)&v7[2 * v26 - 2] = v34;
    *(_WORD *)&v7[2 * v41] = v34;
    v35 = RegSetValueExW(hkey, (LPCWSTR)lpValueName, 0, 7u, v7, 2 * v26);
    if ( !v35 )
      goto LABEL_82;
    if ( v35 > 0 )
      v9 = (unsigned __int16)v35 | 0x80070000;
    else
      v9 = v35;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
      0x28Cu,
      L"RegUtil::AppendToRegMultiSz",
      L"CBRAEx",
      L"lResult == 0L",
      v9);
    if ( !IsDebuggerPresent() )
    {
      v15 = 652;
      goto LABEL_81;
    }
    v40 = v9;
    v12 = 652;
    pcbData = L"lResult == 0L";
    goto LABEL_21;
  }
  if ( ValueW > 0 )
    v9 = (unsigned __int16)ValueW | 0x80070000;
  v8 = 566;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
    0x236u,
    L"RegUtil::AppendToRegMultiSz",
    L"CBRAEx",
    L"lResult == 0L",
    v9);
  if ( !IsDebuggerPresent() )
  {
    v15 = 566;
LABEL_81:
    LODWORD(pcbDataa) = v9;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
      v15,
      L"RegUtil::AppendToRegMultiSz",
      L"CBRAEx",
      L"lResult == 0L",
      pcbDataa);
    goto LABEL_82;
  }
  v40 = v9;
  pcbData = L"lResult == 0L";
LABEL_5:
  pvData = L"CBRAEx";
  v12 = v8;
LABEL_6:
  DEBUGMSGLEVEL(
    2u,
    L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
    L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
    v12,
    L"RegUtil::AppendToRegMultiSz",
    pvData,
    pcbData,
    v40);
LABEL_82:
  operator delete(Block);
  operator delete(v7);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140061134  mov     rax, rsp
0x140061137  mov     [rax+18h], rbx
0x14006113b  mov     [rax+8], rcx
0x14006113f  push    rbp
0x140061140  push    rsi
0x140061141  push    rdi
0x140061142  push    r12
0x140061144  push    r13
0x140061146  push    r14
0x140061148  push    r15
0x14006114a  sub     rsp, 50h
0x14006114e  xor     esi, esi
0x140061150  mov     r12, r8
0x140061153  mov     [rax+10h], esi
0x140061156  mov     rbp, rdx
0x140061159  mov     [rsp+88h+Block], rsi
0x140061161  mov     rdi, rcx
0x140061164  mov     r13d, esi
0x140061167  test    rdx, rdx
0x14006116a  jnz     loc_140061208
0x140061170  mov     r14d, 80070057h
0x140061176  lea     rbp, aCbraex; "CBRAEx"
0x14006117d  mov     [rax-60h], r14d
0x140061181  lea     rsi, aRegutilAppendt; "RegUtil::AppendToRegMultiSz"
0x140061188  lea     rax, aPszvaluename0; "pszValueName != 0"
0x14006118f  mov     r15d, 21Fh
0x140061195  lea     rdi, aTermsrvWmsSrcC_21; "termsrv\\wms\\src\\common\\srcutils\\re"...
0x14006119c  mov     [rsp+88h+pdwType], rax; unsigned __int16 *
0x1400611a1  mov     r9, rbp; unsigned __int16 *
0x1400611a4  mov     r8, rsi; unsigned __int16 *
0x1400611a7  mov     edx, r15d; unsigned int
0x1400611aa  mov     rcx, rdi; unsigned __int16 *
0x1400611ad  mov     ebx, r14d
0x1400611b0  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400611b5  call    cs:__imp_IsDebuggerPresent
0x1400611bb  test    eax, eax
0x1400611bd  lea     rax, aPszvaluename0; "pszValueName != 0"
0x1400611c4  jz      short loc_1400611F6
0x1400611c6  mov     [rsp+88h+var_50], r14d
0x1400611cb  mov     [rsp+88h+pcbData], rax
0x1400611d0  mov     [rsp+88h+pvData], rbp
0x1400611d5  mov     r9d, r15d
0x1400611d8  mov     ecx, 2; unsigned __int8
0x1400611dd  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400611e4  mov     [rsp+88h+pdwType], rsi
0x1400611e9  mov     r8, rdi
0x1400611ec  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400611f1  jmp     loc_1400619D6
0x1400611f6  mov     dword ptr [rsp+88h+pcbData], r14d
0x1400611fb  mov     r8d, r15d
0x1400611fe  mov     [rsp+88h+pvData], rax
0x140061203  jmp     loc_1400619BF
0x140061208  test    r12, r12
0x14006120b  jnz     short loc_140061267
0x14006120d  mov     r14d, 80070057h
0x140061213  lea     rax, aPszstring0; "pszString != 0"
0x14006121a  lea     rbp, aCbraex; "CBRAEx"
0x140061221  mov     dword ptr [rsp+88h+pvData], r14d; int
0x140061226  lea     rsi, aRegutilAppendt; "RegUtil::AppendToRegMultiSz"
0x14006122d  mov     [rsp+88h+pdwType], rax; unsigned __int16 *
0x140061232  mov     r15d, 220h
0x140061238  lea     rdi, aTermsrvWmsSrcC_21; "termsrv\\wms\\src\\common\\srcutils\\re"...
0x14006123f  mov     r9, rbp; unsigned __int16 *
0x140061242  mov     r8, rsi; unsigned __int16 *
0x140061245  mov     edx, r15d; unsigned int
0x140061248  mov     rcx, rdi; unsigned __int16 *
0x14006124b  mov     ebx, r14d
0x14006124e  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140061253  call    cs:__imp_IsDebuggerPresent
0x140061259  test    eax, eax
0x14006125b  lea     rax, aPszstring0; "pszString != 0"
0x140061262  jmp     loc_1400611C4
0x140061267  mov     r8, rbp
0x14006126a  lea     rcx, aRegutilAppendt_0; "RegUtil::AppendToRegMultiSz - Appending"...
0x140061271  mov     rdx, r12
0x140061274  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140061279  mov     r8, r12; String2
0x14006127c  mov     rdx, rbp; lpValueName
0x14006127f  mov     rcx, rdi; hKey
0x140061282  call    ?RemoveFromRegMultiSz@RegUtil@@YAJPEAUHKEY__@@PEBG1@Z; RegUtil::RemoveFromRegMultiSz(HKEY__ *,ushort const *,ushort const *)
0x140061287  mov     ebx, eax
0x140061289  test    eax, eax
0x14006128b  js      loc_1400619D6
0x140061291  lea     rax, [rsp+88h+arg_8]
0x140061299  mov     r14d, 20h ; ' '
0x14006129f  mov     [rsp+88h+pcbData], rax; pcbData
0x1400612a4  mov     r9d, r14d; dwFlags
0x1400612a7  mov     [rsp+88h+pvData], rsi; pvData
0x1400612ac  mov     r8, rbp; lpValue
0x1400612af  xor     edx, edx; lpSubKey
0x1400612b1  mov     [rsp+88h+pdwType], rsi; pdwType
0x1400612b6  mov     rcx, rdi; hkey
0x1400612b9  call    cs:__imp_RegGetValueW
0x1400612bf  mov     ebx, eax
0x1400612c1  test    eax, 0FFFFFFFDh
0x1400612c6  jz      short loc_140061331
0x1400612c8  test    eax, eax
0x1400612ca  jle     short loc_1400612D5
0x1400612cc  movzx   ebx, ax
0x1400612cf  or      ebx, 80070000h
0x1400612d5  lea     rbp, aCbraex; "CBRAEx"
0x1400612dc  mov     dword ptr [rsp+88h+pvData], ebx; int
0x1400612e0  lea     rsi, aRegutilAppendt; "RegUtil::AppendToRegMultiSz"
0x1400612e7  mov     r15d, 236h
0x1400612ed  lea     rdi, aTermsrvWmsSrcC_21; "termsrv\\wms\\src\\common\\srcutils\\re"...
0x1400612f4  mov     r9, rbp; unsigned __int16 *
0x1400612f7  lea     r14, aLresult0l; "lResult == 0L"
0x1400612fe  mov     r8, rsi; unsigned __int16 *
0x140061301  mov     edx, r15d; unsigned int
0x140061304  mov     [rsp+88h+pdwType], r14; unsigned __int16 *
0x140061309  mov     rcx, rdi; unsigned __int16 *
0x14006130c  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140061311  call    cs:__imp_IsDebuggerPresent
0x140061317  test    eax, eax
0x140061319  jz      short loc_140061329
0x14006131b  mov     [rsp+88h+var_50], ebx
0x14006131f  mov     [rsp+88h+pcbData], r14
0x140061324  jmp     loc_1400611D0
0x140061329  mov     r8d, r15d
0x14006132c  jmp     loc_1400619B6
0x140061331  mov     eax, [rsp+88h+arg_8]
0x140061338  or      r11, 0FFFFFFFFFFFFFFFFh
0x14006133c  mov     r15d, 2
0x140061342  test    eax, eax
0x140061344  jz      loc_140061529
0x14006134a  test    al, 1
0x14006134c  jz      short loc_1400613CA
0x14006134e  lea     rax, aCbcurbufSizeof; "(cbCurBuf % sizeof (WCHAR)) == 0"
0x140061355  mov     ebx, 8000FFFFh
0x14006135a  lea     rbp, aCbraex; "CBRAEx"
0x140061361  mov     dword ptr [rsp+88h+pvData], ebx; int
0x140061365  lea     rsi, aRegutilAppendt; "RegUtil::AppendToRegMultiSz"
0x14006136c  mov     [rsp+88h+pdwType], rax; unsigned __int16 *
0x140061371  mov     r14d, 23Bh
0x140061377  lea     rdi, aTermsrvWmsSrcC_21; "termsrv\\wms\\src\\common\\srcutils\\re"...
0x14006137e  mov     r9, rbp; unsigned __int16 *
0x140061381  mov     r8, rsi; unsigned __int16 *
0x140061384  mov     edx, r14d; unsigned int
0x140061387  mov     rcx, rdi; unsigned __int16 *
0x14006138a  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006138f  call    cs:__imp_IsDebuggerPresent
0x140061395  test    eax, eax
0x140061397  lea     rax, aCbcurbufSizeof; "(cbCurBuf % sizeof (WCHAR)) == 0"
0x14006139e  jz      short loc_1400613B9
0x1400613a0  mov     [rsp+88h+var_50], ebx
0x1400613a4  mov     r9d, r14d
0x1400613a7  mov     [rsp+88h+pcbData], rax
0x1400613ac  mov     [rsp+88h+pvData], rbp
0x1400613b1  mov     ecx, r15d
0x1400613b4  jmp     loc_1400611DD
0x1400613b9  mov     dword ptr [rsp+88h+pcbData], ebx
0x1400613bd  mov     r8d, r14d
0x1400613c0  mov     [rsp+88h+pvData], rax
0x1400613c5  jmp     loc_1400619BF
0x1400613ca  mov     rbx, rax
0x1400613cd  mov     rax, r15
0x1400613d0  shr     rbx, 1
0x1400613d3  mul     rbx
0x1400613d6  cmovb   rax, r11
0x1400613da  mov     rcx, rax; Size
0x1400613dd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400613e2  mov     [rsp+88h+Block], rax
0x1400613ea  test    rax, rax
0x1400613ed  jnz     loc_140061475
0x1400613f3  mov     ebp, 8007000Eh
0x1400613f8  lea     rax, aPszcurbuf; "pszCurBuf"
0x1400613ff  lea     r14, aCpr; "CPR"
0x140061406  mov     dword ptr [rsp+88h+pvData], ebp; int
0x14006140a  lea     rsi, aRegutilAppendt; "RegUtil::AppendToRegMultiSz"
0x140061411  mov     [rsp+88h+pdwType], rax; unsigned __int16 *
0x140061416  lea     rdi, aTermsrvWmsSrcC_21; "termsrv\\wms\\src\\common\\srcutils\\re"...
0x14006141d  mov     r9, r14; unsigned __int16 *
0x140061420  mov     r8, rsi; unsigned __int16 *
0x140061423  mov     rcx, rdi; unsigned __int16 *
0x140061426  mov     edx, 23Fh; unsigned int
0x14006142b  mov     ebx, ebp
0x14006142d  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140061432  call    cs:__imp_IsDebuggerPresent
0x140061438  test    eax, eax
0x14006143a  lea     rax, aPszcurbuf; "pszCurBuf"
0x140061441  jz      short loc_14006145C
0x140061443  mov     [rsp+88h+var_50], ebp
0x140061447  mov     r9d, 23Fh
0x14006144d  mov     [rsp+88h+pcbData], rax
0x140061452  mov     [rsp+88h+pvData], r14
0x140061457  jmp     loc_1400613B1
0x14006145c  mov     dword ptr [rsp+88h+pcbData], ebp
0x140061460  mov     r8d, 23Fh
0x140061466  mov     [rsp+88h+pvData], rax
0x14006146b  mov     [rsp+88h+pdwType], r14
0x140061470  jmp     loc_1400619C4
0x140061475  lea     r8, [rbx+rbx]; Size
0x140061479  xor     edx, edx; Val
0x14006147b  mov     rcx, rax; void *
0x14006147e  call    memset_0
0x140061483  mov     rcx, [rsp+88h+Block]
0x14006148b  lea     rax, [rsp+88h+arg_8]
0x140061493  mov     [rsp+88h+pcbData], rax; pcbData
0x140061498  mov     r9d, r14d; dwFlags
0x14006149b  mov     [rsp+88h+pvData], rcx; pvData
0x1400614a0  mov     r8, rbp; lpValue
0x1400614a3  mov     rcx, rdi; hkey
0x1400614a6  mov     [rsp+88h+pdwType], rsi; pdwType
0x1400614ab  xor     edx, edx; lpSubKey
0x1400614ad  call    cs:__imp_RegGetValueW
0x1400614b3  mov     ebx, eax
0x1400614b5  test    eax, eax
0x1400614b7  jz      short loc_140061525
0x1400614b9  jle     short loc_1400614C4
0x1400614bb  movzx   ebx, ax
0x1400614be  or      ebx, 80070000h
0x1400614c4  lea     rbp, aCbraex; "CBRAEx"
0x1400614cb  mov     dword ptr [rsp+88h+pvData], ebx; int
0x1400614cf  lea     rsi, aRegutilAppendt; "RegUtil::AppendToRegMultiSz"
0x1400614d6  mov     r9, rbp; unsigned __int16 *
0x1400614d9  lea     rdi, aTermsrvWmsSrcC_21; "termsrv\\wms\\src\\common\\srcutils\\re"...
0x1400614e0  mov     r8, rsi; unsigned __int16 *
0x1400614e3  lea     r14, aLresult0l; "lResult == 0L"
0x1400614ea  mov     rcx, rdi; unsigned __int16 *
0x1400614ed  mov     edx, 244h; unsigned int
0x1400614f2  mov     [rsp+88h+pdwType], r14; unsigned __int16 *
0x1400614f7  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400614fc  call    cs:__imp_IsDebuggerPresent
0x140061502  test    eax, eax
0x140061504  jz      short loc_14006151A
0x140061506  mov     [rsp+88h+var_50], ebx
0x14006150a  mov     r9d, 244h
0x140061510  mov     [rsp+88h+pcbData], r14
0x140061515  jmp     loc_1400613AC
0x14006151a  mov     r8d, 244h
0x140061520  jmp     loc_1400619B6
0x140061525  or      r11, 0FFFFFFFFFFFFFFFFh
0x140061529  mov     r9, [rsp+88h+Block]
0x140061531  mov     r14d, 80070057h
0x140061537  mov     rdi, r9
0x14006153a  mov     r10d, 7FFFFFFFh
0x140061540  test    r9, r9
0x140061543  jz      short loc_140061593
0x140061545  cmp     [r9], si
0x140061549  jz      short loc_140061593
0x14006154b  mov     rdx, r10
0x14006154e  mov     rax, rdi
0x140061551  cmp     [rax], si
0x140061554  jz      short loc_14006155F
0x140061556  add     rax, r15
0x140061559  sub     rdx, 1
0x14006155d  jnz     short loc_140061551
0x14006155f  mov     rax, rdx
0x140061562  mov     rcx, r10
0x140061565  neg     rax
0x140061568  mov     rax, rdx
0x14006156b  sbb     ebx, ebx
0x14006156d  sub     rcx, rdx
0x140061570  not     ebx
0x140061572  and     ebx, r14d
0x140061575  neg     rax
0x140061578  sbb     r8, r8
0x14006157b  and     r8, rcx
0x14006157e  test    rdx, rdx
0x140061581  jz      loc_14006162E
0x140061587  lea     rdi, [rdi+r8*2]
0x14006158b  add     rdi, r15
0x14006158e  cmp     [rdi], si
0x140061591  jnz     short loc_14006154B
0x140061593  mov     rdx, r10
0x140061596  mov     rax, r12
0x140061599  cmp     [rax], si
0x14006159c  jz      short loc_1400615A7
0x14006159e  add     rax, r15
0x1400615a1  sub     rdx, 1
0x1400615a5  jnz     short loc_140061599
0x1400615a7  mov     rax, rdx
0x1400615aa  mov     rcx, r10
0x1400615ad  neg     rax
0x1400615b0  mov     rax, rdx
0x1400615b3  sbb     ebx, ebx
0x1400615b5  sub     rcx, rdx
0x1400615b8  not     ebx
0x1400615ba  and     ebx, r14d
0x1400615bd  neg     rax
0x1400615c0  sbb     r8, r8
0x1400615c3  and     r8, rcx
0x1400615c6  test    rdx, rdx
0x1400615c9  jnz     loc_1400616BB
0x1400615cf  lea     r14, aChra; "CHRA"
0x1400615d6  mov     dword ptr [rsp+88h+pvData], ebx; int
0x1400615da  lea     rsi, aRegutilAppendt; "RegUtil::AppendToRegMultiSz"
0x1400615e1  mov     r9, r14; unsigned __int16 *
0x1400615e4  lea     rdi, aTermsrvWmsSrcC_21; "termsrv\\wms\\src\\common\\srcutils\\re"...
0x1400615eb  mov     r8, rsi; unsigned __int16 *
0x1400615ee  lea     rbp, aHr; "hr"
0x1400615f5  mov     rcx, rdi; unsigned __int16 *
0x1400615f8  mov     edx, 264h; unsigned int
0x1400615fd  mov     [rsp+88h+pdwType], rbp; unsigned __int16 *
0x140061602  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140061607  call    cs:__imp_IsDebuggerPresent
0x14006160d  test    eax, eax
0x14006160f  jz      loc_1400616A2
0x140061615  mov     [rsp+88h+var_50], ebx
0x140061619  mov     r9d, 264h
  ... truncated ...
```
