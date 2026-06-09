# StructuredQuery1::ConditionEvaluator::FindSubstring(wchar_t const *,wchar_t const *,ulong,bool,GrowableBuffer<tagHITRANGE> *)

- ea: `0x18006fc98`
- end: `0x18006ff00`
- name: `?FindSubstring@ConditionEvaluator@StructuredQuery1@@QEAAJPEB_W0K_NPEAV?$GrowableBuffer@UtagHITRANGE@@@@@Z`
- size: `616`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800317c4`

## callees

- `0x180030160`
- `0x18003040c`
- `0x180047790`
- `0x18006fb04`
- `0x18006fc98`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FindNLSStringEx` at `0x18006fda0`
- `api-ms-win-core-localization-l1-2-0!FindNLSStringEx` at `0x18006fe7e`
- `api-ms-win-core-localization-l1-2-0!FindNLSStringEx` at `0x18006fda0`
- `api-ms-win-core-localization-l1-2-0!FindNLSStringEx` at `0x18006fe7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006fe08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006fe15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006fe08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006fe15`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::ConditionEvaluator::FindSubstring(
        __int64 a1,
        wchar_t *a2,
        const wchar_t *a3,
        DWORD a4,
        char a5,
        __int64 a6)
{
  DWORD v6; // r15d
  __int64 v7; // rdi
  const wchar_t *v8; // r13
  __int64 v9; // r12
  int v10; // ebx
  __int64 cchValue; // r14
  int HasScript; // eax
  char v13; // r15
  int v14; // eax
  unsigned __int16 *v15; // rsi
  WCHAR *v16; // r13
  signed int NLSString; // r8d
  __int64 v18; // rcx
  unsigned int v19; // r15d
  unsigned int fixed; // ebx
  unsigned int v21; // edx
  unsigned int v22; // eax
  int v23; // esi
  signed int v24; // edi
  unsigned int v25; // ebx
  unsigned int v26; // edx
  unsigned int v27; // eax
  LPCWSTR lpStringSource; // [rsp+50h] [rbp-18h] BYREF
  LPCWSTR lpStringValue; // [rsp+58h] [rbp-10h] BYREF
  __int64 pcchFound; // [rsp+B0h] [rbp+48h] BYREF
  wchar_t *v32; // [rsp+B8h] [rbp+50h]
  const wchar_t *v33; // [rsp+C0h] [rbp+58h]
  DWORD dwFindNLSStringFlags; // [rsp+C8h] [rbp+60h]

  dwFindNLSStringFlags = a4;
  v33 = a3;
  v32 = a2;
  pcchFound = a1;
  v6 = a4;
  v7 = -1;
  v8 = a3;
  v9 = -1;
  v10 = 0;
  do
    ++v9;
  while ( a2[v9] );
  cchValue = -1;
  do
    ++cchValue;
  while ( a3[cchValue] );
  LODWORD(pcchFound) = 0;
  if ( a4 == 0x100000 && !a5 )
  {
    HasScript = CScriptAutoDetection::HasScript((CScriptAutoDetection *)g_scriptAutoDetection, a3, a3);
    a2 = v32;
    v10 = HasScript;
    if ( !HasScript )
    {
      lpStringSource = 0;
      v10 = CKoreanDecomposition::DecomposeKoreanForPrefixMatch(
              (CKoreanDecomposition *)g_koreanDecomposition,
              v32,
              (wchar_t **)&lpStringSource);
      if ( v10 >= 0 )
      {
        v13 = 0;
        lpStringValue = 0;
        v14 = CKoreanDecomposition::DecomposeKoreanForPrefixMatch(
                (CKoreanDecomposition *)g_koreanDecomposition,
                v8,
                (wchar_t **)&lpStringValue);
        v15 = (unsigned __int16 *)lpStringSource;
        v10 = v14;
        if ( v14 >= 0 )
        {
          v16 = (WCHAR *)lpStringValue;
          NLSString = FindNLSStringEx(
                        (LPCWSTR)&cchOriginalDestLength,
                        0x120001u,
                        lpStringSource,
                        -1,
                        lpStringValue,
                        -1,
                        (LPINT)&pcchFound,
                        0,
                        0,
                        0);
          if ( NLSString >= 0 )
          {
            v18 = -1;
            do
              ++v18;
            while ( v16[v18] );
            LODWORD(pcchFound) = cchValue - v18 + pcchFound;
            v19 = pcchFound + NLSString;
            do
              ++v7;
            while ( v15[v7] );
            fixed = FixWordBreakBoundary(v15, v7, NLSString);
            v22 = FixWordBreakBoundary(v15, v21, v19);
            LODWORD(pcchFound) = v22 - fixed;
            v10 = StructuredQuery1::AddMatch(fixed, v22 - fixed, a6);
          }
          v13 = 1;
          CoTaskMemFree(v16);
          v8 = v33;
        }
        CoTaskMemFree(v15);
        if ( v13 )
          return (unsigned int)v10;
        v6 = dwFindNLSStringFlags;
      }
      a2 = v32;
    }
  }
  v23 = 0;
  dwFindNLSStringFlags = v6 | 0x20001;
  do
  {
    lpStringValue = &a2[v23];
    v24 = FindNLSStringEx(
            (LPCWSTR)&cchOriginalDestLength,
            dwFindNLSStringFlags,
            lpStringValue,
            v9 - v23,
            v8,
            cchValue,
            (LPINT)&pcchFound,
            0,
            0,
            0);
    if ( v24 < 0 || (int)pcchFound < 1 )
    {
      if ( v10 < 0 )
        return (unsigned int)v10;
    }
    else
    {
      v25 = pcchFound + v24;
      v24 = FixWordBreakBoundary(lpStringValue, v9 - v23, v24);
      v27 = FixWordBreakBoundary(lpStringValue, v26, v25);
      LODWORD(pcchFound) = v27 - v24;
      v10 = StructuredQuery1::AddMatch((unsigned int)(v24 + v23), v27 - v24, a6);
      if ( v10 < 0 )
        return (unsigned int)v10;
      v23 += v24 + pcchFound;
    }
    if ( !a5 )
      break;
    a2 = v32;
  }
  while ( v24 >= 0 );
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18006fc98  mov     rax, rsp
0x18006fc9b  mov     [rax+20h], r9d
0x18006fc9f  mov     [rax+18h], r8
0x18006fca3  mov     [rax+10h], rdx
0x18006fca7  mov     [rax+8], rcx
0x18006fcab  push    rbp
0x18006fcac  push    rbx
0x18006fcad  push    rsi
0x18006fcae  push    rdi
0x18006fcaf  push    r12
0x18006fcb1  push    r13
0x18006fcb3  push    r14
0x18006fcb5  push    r15
0x18006fcb7  mov     rbp, rsp
0x18006fcba  sub     rsp, 68h
0x18006fcbe  xor     ecx, ecx
0x18006fcc0  mov     r15d, r9d
0x18006fcc3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18006fcc7  mov     r13, r8
0x18006fcca  mov     r12, rdi
0x18006fccd  mov     ebx, ecx
0x18006fccf  inc     r12
0x18006fcd2  cmp     [rdx+r12*2], cx
0x18006fcd7  jnz     short loc_18006FCCF
0x18006fcd9  mov     r14, rdi
0x18006fcdc  inc     r14
0x18006fcdf  cmp     [r8+r14*2], cx
0x18006fce4  jnz     short loc_18006FCDC
0x18006fce6  mov     dword ptr [rbp+arg_0], ecx
0x18006fce9  cmp     r9d, 100000h
0x18006fcf0  jnz     loc_18006FE2E
0x18006fcf6  cmp     [rbp+arg_20], cl
0x18006fcf9  jnz     loc_18006FE2E
0x18006fcff  mov     rdx, r13; wchar_t *
0x18006fd02  lea     rcx, ?g_scriptAutoDetection@@3VCScriptAutoDetection@@A; this
0x18006fd09  call    ?HasScript@CScriptAutoDetection@@QEAAJPEB_W0@Z; CScriptAutoDetection::HasScript(wchar_t const *,wchar_t const *)
0x18006fd0e  mov     rdx, [rbp+arg_8]; wchar_t *
0x18006fd12  xor     ecx, ecx
0x18006fd14  mov     ebx, eax
0x18006fd16  test    eax, eax
0x18006fd18  jnz     loc_18006FE2E
0x18006fd1e  mov     [rbp+lpStringSource], rcx
0x18006fd22  lea     r8, [rbp+lpStringSource]; wchar_t **
0x18006fd26  lea     rcx, ?g_koreanDecomposition@@3VCKoreanDecomposition@@A; this
0x18006fd2d  call    ?DecomposeKoreanForPrefixMatch@CKoreanDecomposition@@QEAAJPEB_WPEAPEA_W@Z; CKoreanDecomposition::DecomposeKoreanForPrefixMatch(wchar_t const *,wchar_t * *)
0x18006fd32  xor     ecx, ecx
0x18006fd34  mov     ebx, eax
0x18006fd36  test    eax, eax
0x18006fd38  js      loc_18006FE2A
0x18006fd3e  mov     r15b, cl
0x18006fd41  mov     [rbp+var_10], rcx
0x18006fd45  lea     rcx, ?g_koreanDecomposition@@3VCKoreanDecomposition@@A; this
0x18006fd4c  mov     rdx, r13; wchar_t *
0x18006fd4f  lea     r8, [rbp+var_10]; wchar_t **
0x18006fd53  call    ?DecomposeKoreanForPrefixMatch@CKoreanDecomposition@@QEAAJPEB_WPEAPEA_W@Z; CKoreanDecomposition::DecomposeKoreanForPrefixMatch(wchar_t const *,wchar_t * *)
0x18006fd58  mov     rsi, [rbp+lpStringSource]
0x18006fd5c  mov     ebx, eax
0x18006fd5e  test    eax, eax
0x18006fd60  js      loc_18006FE12
0x18006fd66  mov     r13, [rbp+var_10]
0x18006fd6a  lea     rax, [rbp+arg_0]
0x18006fd6e  xor     r15d, r15d
0x18006fd71  lea     rcx, cchOriginalDestLength; lpLocaleName
0x18006fd78  mov     [rsp+68h+sortHandle], r15; sortHandle
0x18006fd7d  mov     r9d, edi; cchSource
0x18006fd80  mov     [rsp+68h+lpReserved], r15; lpReserved
0x18006fd85  mov     r8, rsi; lpStringSource
0x18006fd88  mov     [rsp+68h+lpVersionInformation], r15; lpVersionInformation
0x18006fd8d  mov     edx, 120001h; dwFindNLSStringFlags
0x18006fd92  mov     [rsp+68h+pcchFound], rax; pcchFound
0x18006fd97  mov     [rsp+68h+cchValue], edi; cchValue
0x18006fd9b  mov     [rsp+68h+lpStringValue], r13; lpStringValue
0x18006fda0  call    cs:__imp_FindNLSStringEx
0x18006fda6  mov     r8d, eax; unsigned int
0x18006fda9  test    eax, eax
0x18006fdab  js      short loc_18006FE02
0x18006fdad  mov     rcx, rdi
0x18006fdb0  inc     rcx
0x18006fdb3  cmp     [r13+rcx*2+0], r15w
0x18006fdb9  jnz     short loc_18006FDB0
0x18006fdbb  mov     eax, r14d
0x18006fdbe  sub     eax, ecx
0x18006fdc0  mov     ecx, dword ptr [rbp+arg_0]
0x18006fdc3  add     ecx, eax
0x18006fdc5  mov     dword ptr [rbp+arg_0], ecx
0x18006fdc8  xor     eax, eax
0x18006fdca  lea     r15d, [rcx+r8]
0x18006fdce  inc     rdi
0x18006fdd1  cmp     [rsi+rdi*2], ax
0x18006fdd5  jnz     short loc_18006FDCE
0x18006fdd7  mov     edx, edi; unsigned int
0x18006fdd9  mov     rcx, rsi; unsigned __int16 *
0x18006fddc  call    ?FixWordBreakBoundary@@YAKPEBGKK@Z; FixWordBreakBoundary(ushort const *,ulong,ulong)
0x18006fde1  mov     r8d, r15d; unsigned int
0x18006fde4  mov     rcx, rsi; unsigned __int16 *
0x18006fde7  mov     ebx, eax
0x18006fde9  call    ?FixWordBreakBoundary@@YAKPEBGKK@Z; FixWordBreakBoundary(ushort const *,ulong,ulong)
0x18006fdee  mov     r8, [rbp+arg_28]
0x18006fdf2  sub     eax, ebx
0x18006fdf4  mov     edx, eax
0x18006fdf6  mov     dword ptr [rbp+arg_0], eax
0x18006fdf9  mov     ecx, ebx
0x18006fdfb  call    StructuredQuery1__AddMatch
0x18006fe00  mov     ebx, eax
0x18006fe02  mov     rcx, r13; pv
0x18006fe05  mov     r15b, 1
0x18006fe08  call    cs:__imp_CoTaskMemFree
0x18006fe0e  mov     r13, [rbp+arg_10]
0x18006fe12  mov     rcx, rsi; pv
0x18006fe15  call    cs:__imp_CoTaskMemFree
0x18006fe1b  xor     ecx, ecx
0x18006fe1d  test    r15b, r15b
0x18006fe20  jnz     loc_18006FEED
0x18006fe26  mov     r15d, [rbp+dwFindNLSStringFlags]
0x18006fe2a  mov     rdx, [rbp+arg_8]
0x18006fe2e  or      r15d, 20001h
0x18006fe35  mov     esi, ecx
0x18006fe37  mov     [rbp+dwFindNLSStringFlags], r15d
0x18006fe3b  mov     [rsp+68h+sortHandle], rcx; sortHandle
0x18006fe40  mov     r15d, r12d
0x18006fe43  mov     [rsp+68h+lpReserved], rcx; lpReserved
0x18006fe48  sub     r15d, esi
0x18006fe4b  mov     [rsp+68h+lpVersionInformation], rcx; lpVersionInformation
0x18006fe50  mov     r9d, r15d; cchSource
0x18006fe53  lea     rcx, [rbp+arg_0]
0x18006fe57  movsxd  rax, esi
0x18006fe5a  mov     [rsp+68h+pcchFound], rcx; pcchFound
0x18006fe5f  lea     rcx, cchOriginalDestLength; lpLocaleName
0x18006fe66  mov     [rsp+68h+cchValue], r14d; cchValue
0x18006fe6b  mov     [rsp+68h+lpStringValue], r13; lpStringValue
0x18006fe70  lea     rax, [rdx+rax*2]
0x18006fe74  mov     edx, [rbp+dwFindNLSStringFlags]; dwFindNLSStringFlags
0x18006fe77  mov     r8, rax; lpStringSource
0x18006fe7a  mov     [rbp+var_10], rax
0x18006fe7e  call    cs:__imp_FindNLSStringEx
0x18006fe84  xor     ecx, ecx
0x18006fe86  mov     edi, eax
0x18006fe88  test    eax, eax
0x18006fe8a  js      short loc_18006FED8
0x18006fe8c  mov     eax, dword ptr [rbp+arg_0]
0x18006fe8f  cmp     eax, 1
0x18006fe92  jl      short loc_18006FED8
0x18006fe94  mov     rcx, [rbp+var_10]; unsigned __int16 *
0x18006fe98  lea     ebx, [rax+rdi]
0x18006fe9b  mov     r8d, edi; unsigned int
0x18006fe9e  mov     edx, r15d; unsigned int
0x18006fea1  call    ?FixWordBreakBoundary@@YAKPEBGKK@Z; FixWordBreakBoundary(ushort const *,ulong,ulong)
0x18006fea6  mov     rcx, [rbp+var_10]; unsigned __int16 *
0x18006feaa  mov     r8d, ebx; unsigned int
0x18006fead  mov     edi, eax
0x18006feaf  call    ?FixWordBreakBoundary@@YAKPEBGKK@Z; FixWordBreakBoundary(ushort const *,ulong,ulong)
0x18006feb4  mov     r8, [rbp+arg_28]
0x18006feb8  lea     ecx, [rdi+rsi]
0x18006febb  sub     eax, edi
0x18006febd  mov     edx, eax
0x18006febf  mov     dword ptr [rbp+arg_0], eax
0x18006fec2  call    StructuredQuery1__AddMatch
0x18006fec7  mov     ebx, eax
0x18006fec9  test    eax, eax
0x18006fecb  js      short loc_18006FEED
0x18006fecd  mov     ecx, dword ptr [rbp+arg_0]
0x18006fed0  add     ecx, edi
0x18006fed2  add     esi, ecx
0x18006fed4  xor     ecx, ecx
0x18006fed6  jmp     short loc_18006FEDC
0x18006fed8  test    ebx, ebx
0x18006feda  js      short loc_18006FEED
0x18006fedc  cmp     [rbp+arg_20], cl
0x18006fedf  jz      short loc_18006FEED
0x18006fee1  mov     rdx, [rbp+arg_8]
0x18006fee5  test    edi, edi
0x18006fee7  jns     loc_18006FE3B
0x18006feed  mov     eax, ebx
0x18006feef  add     rsp, 68h
0x18006fef3  pop     r15
0x18006fef5  pop     r14
0x18006fef7  pop     r13
0x18006fef9  pop     r12
0x18006fefb  pop     rdi
0x18006fefc  pop     rsi
0x18006fefd  pop     rbx
0x18006fefe  pop     rbp
0x18006feff  retn
```
