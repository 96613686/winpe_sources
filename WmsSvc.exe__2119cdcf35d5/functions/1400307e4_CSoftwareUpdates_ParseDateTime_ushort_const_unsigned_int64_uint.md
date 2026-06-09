# CSoftwareUpdates::ParseDateTime(ushort const *,unsigned __int64,uint *)

- ea: `0x1400307e4`
- end: `0x140030bc0`
- name: `?ParseDateTime@CSoftwareUpdates@@AEAAJPEBG_KPEAI@Z`
- size: `988`
- prototype: `__int64 __fastcall(CSoftwareUpdates *__hidden this, const unsigned __int16 *, unsigned __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x14002fad4`

## callees

- `0x1400307e4`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007cbd0`

## import_xrefs

- `KERNEL32!SystemTimeToFileTime` at `0x140030992`
- `KERNEL32!SystemTimeToFileTime` at `0x140030992`
- `KERNEL32!GetLastError` at `0x14003099c`
- `KERNEL32!GetLastError` at `0x14003099c`
- `KERNEL32!IsDebuggerPresent` at `0x1400309f5`
- `KERNEL32!IsDebuggerPresent` at `0x140030a68`
- `KERNEL32!IsDebuggerPresent` at `0x140030ae6`
- `KERNEL32!IsDebuggerPresent` at `0x140030b39`
- `KERNEL32!IsDebuggerPresent` at `0x1400309f5`
- `KERNEL32!IsDebuggerPresent` at `0x140030a68`
- `KERNEL32!IsDebuggerPresent` at `0x140030ae6`
- `KERNEL32!IsDebuggerPresent` at `0x140030b39`

## string_xrefs

- `0x1400309cb`: `termsrv\wms\src\devices\wmssvc\softwareupdates.cpp`
- `0x140030a49`: `termsrv\wms\src\devices\wmssvc\softwareupdates.cpp`
- `0x140030ac0`: `termsrv\wms\src\devices\wmssvc\softwareupdates.cpp`
- `0x140030b11`: `termsrv\wms\src\devices\wmssvc\softwareupdates.cpp`
- `0x1400309bf`: `CSoftwareUpdates::ParseDateTime`
- `0x140030a37`: `CSoftwareUpdates::ParseDateTime`
- `0x140030aaf`: `CSoftwareUpdates::ParseDateTime`
- `0x140030b06`: `CSoftwareUpdates::ParseDateTime`

## pseudocode

```c
__int64 __fastcall CSoftwareUpdates::ParseDateTime(
        CSoftwareUpdates *this,
        const unsigned __int16 *a2,
        unsigned __int64 a3,
        unsigned int *a4)
{
  _BOOL8 v5; // rdx
  WORD v7; // cx
  __int64 i; // r9
  __int16 v9; // cx
  _BOOL8 v10; // rdx
  _BOOL8 v11; // r9
  WORD v12; // cx
  __int64 j; // rdx
  __int16 v14; // cx
  unsigned __int64 v15; // rcx
  __int64 v16; // r9
  WORD v17; // cx
  __int64 k; // rdx
  __int16 v19; // cx
  unsigned __int64 v20; // rcx
  __int64 v21; // r9
  WORD v22; // cx
  __int64 m; // rdx
  __int16 v24; // cx
  unsigned __int64 v25; // rcx
  WORD v26; // dx
  const unsigned __int16 *v27; // r8
  __int64 n; // rcx
  __int16 v29; // dx
  signed int LastError; // eax
  unsigned int v31; // ebx
  const unsigned __int16 *v32; // r15
  __int64 v33; // r9
  __int64 v34; // r8
  const unsigned __int16 *v35; // r13
  unsigned int v36; // r15d
  int v38; // [rsp+30h] [rbp-58h]
  int v39; // [rsp+38h] [rbp-50h]
  struct _FILETIME FileTime; // [rsp+40h] [rbp-48h] BYREF
  SYSTEMTIME SystemTime; // [rsp+48h] [rbp-40h] BYREF

  FileTime = 0;
  v5 = 0;
  SystemTime = 0;
  if ( a3 )
    v5 = *a2 == 43;
  v7 = 0;
  for ( i = 0; i != 4; ++i )
  {
    v9 = a2[v5 + i] + 10 * v7;
    v7 = v9 - 48;
  }
  v10 = v5 + 4;
  SystemTime.wYear = v7;
  if ( v10 >= a3 || a2[v10] != 45 )
  {
    v32 = L"(iIndex < cchString) && (pszString[iIndex] == L'-')";
    v31 = -2147024809;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
      0x2CAu,
      L"CSoftwareUpdates::ParseDateTime",
      L"CBRAEx",
      L"(iIndex < cchString) && (pszString[iIndex] == L'-')",
      -2147024809);
    if ( IsDebuggerPresent() )
    {
      v33 = 714;
      goto LABEL_40;
    }
    v34 = 714;
LABEL_43:
    v38 = -2147024809;
    goto LABEL_44;
  }
  v11 = v10 + 1;
  v12 = 0;
  for ( j = 0; j != 2; ++j )
  {
    v14 = a2[v11 + j] + 10 * v12;
    v12 = v14 - 48;
  }
  SystemTime.wMonth = v12;
  v15 = v11 + 2;
  if ( v15 >= a3 || a2[v15] != 45 )
  {
    v32 = L"(iIndex < cchString) && (pszString[iIndex] == L'-')";
    v31 = -2147024809;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
      0x2D2u,
      L"CSoftwareUpdates::ParseDateTime",
      L"CBRAEx",
      L"(iIndex < cchString) && (pszString[iIndex] == L'-')",
      -2147024809);
    if ( IsDebuggerPresent() )
    {
      v33 = 722;
LABEL_40:
      v39 = -2147024809;
      goto LABEL_41;
    }
    v34 = 722;
    goto LABEL_43;
  }
  v16 = (unsigned int)(v15 + 1);
  v17 = 0;
  for ( k = 0; k != 2; ++k )
  {
    v19 = a2[v16 + k] + 10 * v17;
    v17 = v19 - 48;
  }
  SystemTime.wDay = v17;
  v20 = (unsigned int)(v16 + 2);
  if ( v20 >= a3 || a2[v20] != 84 )
  {
    v35 = L"(iIndex < cchString) && (pszString[iIndex] == L'T')";
    v36 = 730;
LABEL_31:
    v31 = -2147024809;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
      v36,
      L"CSoftwareUpdates::ParseDateTime",
      L"CBRAEx",
      v35,
      -2147024809);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
        v36,
        L"CSoftwareUpdates::ParseDateTime",
        L"CBRAEx",
        v35,
        -2147024809,
        FileTime,
        *(_QWORD *)&SystemTime.wYear,
        *(_QWORD *)&SystemTime.wHour);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
        v36,
        L"CSoftwareUpdates::ParseDateTime",
        L"CBRAEx",
        v35,
        -2147024809);
    return v31;
  }
  v21 = (unsigned int)(v20 + 1);
  v22 = 0;
  for ( m = 0; m != 2; ++m )
  {
    v24 = a2[v21 + m] + 10 * v22;
    v22 = v24 - 48;
  }
  SystemTime.wHour = v22;
  v25 = (unsigned int)(v21 + 2);
  if ( v25 >= a3 || a2[v25] != 58 )
  {
    v35 = L"(iIndex < cchString) && (pszString[iIndex] == L':')";
    v36 = 738;
    goto LABEL_31;
  }
  v26 = 0;
  v27 = &a2[(unsigned int)(v25 + 1)];
  for ( n = 0; n != 2; ++n )
  {
    v29 = v27[n] + 10 * v26;
    v26 = v29 - 48;
  }
  SystemTime.wMinute = v26;
  if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
  {
    LastError = GetLastError();
    v31 = LastError;
    if ( LastError > 0 )
      v31 = (unsigned __int16)LastError | 0x80070000;
    if ( (v31 & 0x80000000) == 0 )
      v31 = -2147467259;
    v32 = L"fSuccess";
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
      0x2EFu,
      L"CSoftwareUpdates::ParseDateTime",
      L"CBRAEx",
      L"fSuccess",
      v31);
    if ( IsDebuggerPresent() )
    {
      v39 = v31;
      v33 = 751;
LABEL_41:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
        v33,
        L"CSoftwareUpdates::ParseDateTime",
        L"CBRAEx",
        v32,
        v39,
        FileTime,
        *(_QWORD *)&SystemTime.wYear,
        *(_QWORD *)&SystemTime.wHour);
      return v31;
    }
    v38 = v31;
    v34 = 751;
LABEL_44:
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
      v34,
      L"CSoftwareUpdates::ParseDateTime",
      L"CBRAEx",
      v32,
      v38);
    return v31;
  }
  v31 = 0;
  *a4 = SystemTime.wHour;
  return v31;
}

```

## disassembly

```asm
0x1400307e4  mov     [rsp+arg_0], rbx
0x1400307e9  mov     [rsp+arg_10], rbp
0x1400307ee  push    rsi
0x1400307ef  push    rdi
0x1400307f0  push    r13
0x1400307f2  push    r14
0x1400307f4  push    r15
0x1400307f6  sub     rsp, 60h
0x1400307fa  mov     rax, cs:__security_cookie
0x140030801  xor     rax, rsp
0x140030804  mov     [rsp+88h+var_30], rax
0x140030809  mov     r10, rdx
0x14003080c  mov     qword ptr [rsp+88h+FileTime.dwLowDateTime], 0
0x140030815  xor     edx, edx
0x140030817  xorps   xmm0, xmm0
0x14003081a  mov     rdi, r9
0x14003081d  movups  xmmword ptr [rsp+88h+SystemTime.wYear], xmm0
0x140030822  lea     ebx, [rdx+1]
0x140030825  test    r8, r8
0x140030828  jz      short loc_140030832
0x14003082a  cmp     word ptr [r10], 2Bh ; '+'
0x14003082f  cmovz   edx, ebx
0x140030832  xor     ecx, ecx
0x140030834  lea     r11, [r10+rdx*2]
0x140030838  xor     r9d, r9d
0x14003083b  mov     si, 30h ; '0'
0x14003083f  movzx   eax, cx
0x140030842  shl     ax, 2
0x140030846  add     cx, ax
0x140030849  add     cx, cx
0x14003084c  add     cx, [r11+r9*2]
0x140030851  add     r9, rbx
0x140030854  sub     cx, si
0x140030857  cmp     r9, 4
0x14003085b  jnz     short loc_14003083F
0x14003085d  add     edx, r9d
0x140030860  mov     [rsp+88h+SystemTime.wYear], cx
0x140030865  mov     eax, edx
0x140030867  cmp     rax, r8
0x14003086a  jnb     loc_140030AFA
0x140030870  cmp     word ptr [r10+rdx*2], 2Dh ; '-'
0x140030876  jnz     loc_140030AFA
0x14003087c  lea     r9d, [rdx+1]
0x140030880  xor     ecx, ecx
0x140030882  lea     r11, [r10+r9*2]
0x140030886  xor     edx, edx
0x140030888  movzx   eax, cx
0x14003088b  shl     ax, 2
0x14003088f  add     cx, ax
0x140030892  add     cx, cx
0x140030895  add     cx, [r11+rdx*2]
0x14003089a  add     rdx, rbx
0x14003089d  sub     cx, si
0x1400308a0  cmp     rdx, 2
0x1400308a4  jnz     short loc_140030888
0x1400308a6  mov     [rsp+88h+SystemTime.wMonth], cx
0x1400308ab  lea     ecx, [r9+2]
0x1400308af  mov     eax, ecx
0x1400308b1  cmp     rax, r8
0x1400308b4  jnb     loc_140030AA3
0x1400308ba  cmp     word ptr [r10+rcx*2], 2Dh ; '-'
0x1400308c0  jnz     loc_140030AA3
0x1400308c6  lea     r9d, [rcx+1]
0x1400308ca  xor     ecx, ecx
0x1400308cc  xor     edx, edx
0x1400308ce  lea     r11, [r10+r9*2]
0x1400308d2  movzx   eax, cx
0x1400308d5  shl     ax, 2
0x1400308d9  add     cx, ax
0x1400308dc  add     cx, cx
0x1400308df  add     cx, [r11+rdx*2]
0x1400308e4  add     rdx, rbx
0x1400308e7  sub     cx, si
0x1400308ea  cmp     rdx, 2
0x1400308ee  jnz     short loc_1400308D2
0x1400308f0  mov     [rsp+88h+SystemTime.wDay], cx
0x1400308f5  lea     ecx, [r9+2]
0x1400308f9  mov     eax, ecx
0x1400308fb  cmp     rax, r8
0x1400308fe  jnb     loc_140030A94
0x140030904  cmp     word ptr [r10+rcx*2], 54h ; 'T'
0x14003090a  jnz     loc_140030A94
0x140030910  lea     r9d, [rcx+1]
0x140030914  xor     ecx, ecx
0x140030916  xor     edx, edx
0x140030918  lea     r11, [r10+r9*2]
0x14003091c  movzx   eax, cx
0x14003091f  shl     ax, 2
0x140030923  add     cx, ax
0x140030926  add     cx, cx
0x140030929  add     cx, [r11+rdx*2]
0x14003092e  add     rdx, rbx
0x140030931  sub     cx, si
0x140030934  cmp     rdx, 2
0x140030938  jnz     short loc_14003091C
0x14003093a  mov     [rsp+88h+SystemTime.wHour], cx
0x14003093f  lea     ecx, [r9+2]
0x140030943  mov     eax, ecx
0x140030945  cmp     rax, r8
0x140030948  jnb     loc_140030A25
0x14003094e  cmp     word ptr [r10+rcx*2], 3Ah ; ':'
0x140030954  jnz     loc_140030A25
0x14003095a  lea     eax, [rcx+1]
0x14003095d  xor     edx, edx
0x14003095f  lea     r8, [r10+rax*2]
0x140030963  xor     ecx, ecx
0x140030965  movzx   eax, dx
0x140030968  shl     ax, 2
0x14003096c  add     dx, ax
0x14003096f  add     dx, dx
0x140030972  add     dx, [r8+rcx*2]
0x140030977  add     rcx, rbx
0x14003097a  sub     dx, si
0x14003097d  cmp     rcx, 2
0x140030981  jnz     short loc_140030965
0x140030983  mov     [rsp+88h+SystemTime.wMinute], dx
0x140030988  lea     rcx, [rsp+88h+SystemTime]; lpSystemTime
0x14003098d  lea     rdx, [rsp+88h+FileTime]; lpFileTime
0x140030992  call    cs:__imp_SystemTimeToFileTime
0x140030998  test    eax, eax
0x14003099a  jnz     short loc_140030A17
0x14003099c  call    cs:__imp_GetLastError
0x1400309a2  mov     ebx, eax
0x1400309a4  test    eax, eax
0x1400309a6  jle     short loc_1400309B1
0x1400309a8  movzx   ebx, ax
0x1400309ab  or      ebx, 80070000h
0x1400309b1  mov     eax, 80004005h
0x1400309b6  lea     r14, aCbraex; "CBRAEx"
0x1400309bd  test    ebx, ebx
0x1400309bf  lea     rbp, aCsoftwareupdat_1; "CSoftwareUpdates::ParseDateTime"
0x1400309c6  mov     edi, 2EFh
0x1400309cb  lea     rsi, aTermsrvWmsSrcD_18; "termsrv\\wms\\src\\devices\\wmssvc\\sof"...
0x1400309d2  cmovns  ebx, eax
0x1400309d5  lea     r15, aFsuccess; "fSuccess"
0x1400309dc  mov     [rsp+88h+var_60], ebx; int
0x1400309e0  mov     r9, r14; unsigned __int16 *
0x1400309e3  mov     r8, rbp; unsigned __int16 *
0x1400309e6  mov     [rsp+88h+var_68], r15; unsigned __int16 *
0x1400309eb  mov     edx, edi; unsigned int
0x1400309ed  mov     rcx, rsi; unsigned __int16 *
0x1400309f0  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400309f5  call    cs:__imp_IsDebuggerPresent
0x1400309fb  test    eax, eax
0x1400309fd  jz      short loc_140030A0B
0x1400309ff  mov     [rsp+88h+var_50], ebx
0x140030a03  mov     r9d, edi
0x140030a06  jmp     loc_140030B4D
0x140030a0b  mov     dword ptr [rsp+88h+var_58], ebx
0x140030a0f  mov     r8d, edi
0x140030a12  jmp     loc_140030B7C
0x140030a17  movzx   eax, [rsp+88h+SystemTime.wHour]
0x140030a1c  xor     ebx, ebx
0x140030a1e  mov     [rdi], eax
0x140030a20  jmp     loc_140030B98
0x140030a25  lea     r13, aIindexCchstrin_1; "(iIndex < cchString) && (pszString[iInd"...
0x140030a2c  mov     r15d, 2E2h
0x140030a32  mov     edi, 80070057h
0x140030a37  lea     rbp, aCsoftwareupdat_1; "CSoftwareUpdates::ParseDateTime"
0x140030a3e  lea     r14, aCbraex; "CBRAEx"
0x140030a45  mov     [rsp+88h+var_60], edi; int
0x140030a49  lea     rsi, aTermsrvWmsSrcD_18; "termsrv\\wms\\src\\devices\\wmssvc\\sof"...
0x140030a50  mov     [rsp+88h+var_68], r13; unsigned __int16 *
0x140030a55  mov     r8, rbp; unsigned __int16 *
0x140030a58  mov     r9, r14; unsigned __int16 *
0x140030a5b  mov     rcx, rsi; unsigned __int16 *
0x140030a5e  mov     edx, r15d; unsigned int
0x140030a61  mov     ebx, edi
0x140030a63  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140030a68  call    cs:__imp_IsDebuggerPresent
0x140030a6e  test    eax, eax
0x140030a70  jz      short loc_140030A83
0x140030a72  mov     [rsp+88h+var_50], edi
0x140030a76  mov     r9d, r15d
0x140030a79  mov     [rsp+88h+var_58], r13
0x140030a7e  jmp     loc_140030B52
0x140030a83  mov     dword ptr [rsp+88h+var_58], edi
0x140030a87  mov     r8d, r15d
0x140030a8a  mov     qword ptr [rsp+88h+var_60], r13
0x140030a8f  jmp     loc_140030B81
0x140030a94  lea     r13, aIindexCchstrin_0; "(iIndex < cchString) && (pszString[iInd"...
0x140030a9b  mov     r15d, 2DAh
0x140030aa1  jmp     short loc_140030A32
0x140030aa3  mov     edi, 80070057h
0x140030aa8  lea     r14, aCbraex; "CBRAEx"
0x140030aaf  lea     rbp, aCsoftwareupdat_1; "CSoftwareUpdates::ParseDateTime"
0x140030ab6  mov     [rsp+88h+var_60], edi; int
0x140030aba  mov     r13d, 2D2h
0x140030ac0  lea     rsi, aTermsrvWmsSrcD_18; "termsrv\\wms\\src\\devices\\wmssvc\\sof"...
0x140030ac7  lea     r15, aIindexCchstrin; "(iIndex < cchString) && (pszString[iInd"...
0x140030ace  mov     r9, r14; unsigned __int16 *
0x140030ad1  mov     r8, rbp; unsigned __int16 *
0x140030ad4  mov     [rsp+88h+var_68], r15; unsigned __int16 *
0x140030ad9  mov     edx, r13d; unsigned int
0x140030adc  mov     rcx, rsi; unsigned __int16 *
0x140030adf  mov     ebx, edi
0x140030ae1  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140030ae6  call    cs:__imp_IsDebuggerPresent
0x140030aec  test    eax, eax
0x140030aee  jz      short loc_140030AF5
0x140030af0  mov     r9d, r13d
0x140030af3  jmp     short loc_140030B49
0x140030af5  mov     r8d, r13d
0x140030af8  jmp     short loc_140030B78
0x140030afa  mov     edi, 80070057h
0x140030aff  lea     r14, aCbraex; "CBRAEx"
0x140030b06  lea     rbp, aCsoftwareupdat_1; "CSoftwareUpdates::ParseDateTime"
0x140030b0d  mov     [rsp+88h+var_60], edi; int
0x140030b11  lea     rsi, aTermsrvWmsSrcD_18; "termsrv\\wms\\src\\devices\\wmssvc\\sof"...
0x140030b18  mov     r9, r14; unsigned __int16 *
0x140030b1b  lea     r15, aIindexCchstrin; "(iIndex < cchString) && (pszString[iInd"...
0x140030b22  mov     r8, rbp; unsigned __int16 *
0x140030b25  mov     rcx, rsi; unsigned __int16 *
0x140030b28  mov     [rsp+88h+var_68], r15; unsigned __int16 *
0x140030b2d  mov     edx, 2CAh; unsigned int
0x140030b32  mov     ebx, edi
0x140030b34  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140030b39  call    cs:__imp_IsDebuggerPresent
0x140030b3f  test    eax, eax
0x140030b41  jz      short loc_140030B72
0x140030b43  mov     r9d, 2CAh
0x140030b49  mov     [rsp+88h+var_50], edi
0x140030b4d  mov     [rsp+88h+var_58], r15
0x140030b52  mov     qword ptr [rsp+88h+var_60], r14
0x140030b57  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140030b5e  mov     r8, rsi
0x140030b61  mov     [rsp+88h+var_68], rbp
0x140030b66  mov     ecx, 2; unsigned __int8
0x140030b6b  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140030b70  jmp     short loc_140030B98
0x140030b72  mov     r8d, 2CAh
0x140030b78  mov     dword ptr [rsp+88h+var_58], edi
0x140030b7c  mov     qword ptr [rsp+88h+var_60], r15
0x140030b81  mov     r9, rbp
0x140030b84  mov     [rsp+88h+var_68], r14
0x140030b89  mov     rdx, rsi
0x140030b8c  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140030b93  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140030b98  mov     eax, ebx
0x140030b9a  mov     rcx, [rsp+88h+var_30]
0x140030b9f  xor     rcx, rsp; StackCookie
0x140030ba2  call    __security_check_cookie
0x140030ba7  lea     r11, [rsp+88h+var_28]
0x140030bac  mov     rbx, [r11+30h]
0x140030bb0  mov     rbp, [r11+40h]
0x140030bb4  mov     rsp, r11
0x140030bb7  pop     r15
0x140030bb9  pop     r14
0x140030bbb  pop     r13
0x140030bbd  pop     rdi
0x140030bbe  pop     rsi
0x140030bbf  retn
```
