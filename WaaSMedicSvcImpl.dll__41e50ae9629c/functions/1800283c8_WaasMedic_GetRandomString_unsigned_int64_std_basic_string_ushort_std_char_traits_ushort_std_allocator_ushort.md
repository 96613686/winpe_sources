# WaasMedic::GetRandomString(unsigned __int64,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800283c8`
- end: `0x180028597`
- name: `?GetRandomString@WaasMedic@@YAJ_KAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `463`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x18001ecdc`

## callees

- `0x1800050a0`
- `0x1800098f0`
- `0x180009cd0`
- `0x18000c638`
- `0x180010db4`
- `0x1800283c8`
- `0x18002a300`
- `0x18002a4e4`
- `0x18002a7b4`
- `0x18002e81c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002854f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002854f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002855d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002855d`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180028543`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180028543`
- `bcrypt!BCryptGenRandom` at `0x180028480`
- `bcrypt!BCryptGenRandom` at `0x180028480`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180028429`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180028429`

## string_xrefs

- `0x18002843f`: `Could not open provider. Error: 0x%08x.`
- `0x180028521`: `Could not write characters to the generated string. Error: 0x%08x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WaasMedic::GetRandomString(__int64 a1, __int64 a2)
{
  void *v3; // rbx
  NTSTATUS v4; // eax
  unsigned __int64 v5; // rdx
  bool v6; // r8
  WaasMedic *v7; // r14
  int v8; // edi
  const unsigned __int16 *v9; // rdx
  UCHAR *v10; // rax
  void *v11; // rdx
  NTSTATUS v12; // eax
  unsigned __int64 v13; // rdx
  bool v14; // r8
  unsigned __int64 i; // rsi
  __int64 v16; // r8
  HANDLE ProcessHeap; // rax
  BCRYPT_ALG_HANDLE phAlgorithm[2]; // [rsp+20h] [rbp-60h] BYREF
  _OWORD v20[2]; // [rsp+30h] [rbp-50h] BYREF
  _OWORD v21[2]; // [rsp+50h] [rbp-30h] BYREF

  phAlgorithm[0] = 0;
  v21[0] = 0;
  v21[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v21[0]) = 0;
  v3 = 0;
  v4 = BCryptOpenAlgorithmProvider(phAlgorithm, L"RNG", 0, 0);
  if ( v4 )
  {
    v7 = 0;
    v8 = WaasMedic::MiscUtil::HRESULT_FROM_NTSTATUS(v4);
    v9 = L"Could not open provider. Error: 0x%08x.";
LABEL_15:
    LogLevelW(2u, v9);
    goto LABEL_16;
  }
  v10 = (UCHAR *)WaasMedic::SafeAlloc((WaasMedic *)0x10, v5, v6);
  v7 = (WaasMedic *)v10;
  if ( !v10 )
    goto LABEL_4;
  v12 = BCryptGenRandom(phAlgorithm[0], v10, 0x10u, 0);
  if ( v12 )
  {
    v8 = WaasMedic::MiscUtil::HRESULT_FROM_NTSTATUS(v12);
    v9 = L"Could not get random number from the provider. Error: 0x%08x.";
    goto LABEL_15;
  }
  v3 = WaasMedic::SafeAlloc((WaasMedic *)0x42, v13, v14);
  phAlgorithm[1] = v3;
  if ( !v3 )
  {
LABEL_4:
    v8 = -2147024882;
    LogLevelW(2u, L"Could not allocate memory for the requested buffer. Error: 0x%08x.");
    goto LABEL_16;
  }
  for ( i = 0; i < 0x10; ++i )
  {
    v8 = StringCchPrintfW((unsigned __int16 *)v3 + 2 * i, 3u, L"%02x", *((unsigned __int8 *)v7 + i));
    if ( v8 < 0 )
    {
      v9 = L"Could not write characters to the generated string. Error: 0x%08x.";
      goto LABEL_15;
    }
  }
  memset(v20, 0, sizeof(v20));
  v16 = -1;
  do
    ++v16;
  while ( *((_WORD *)v3 + v16) );
  std::wstring::_Construct<1,unsigned short const *>(v20, v3);
  std::wstring::operator=(a2, v20);
  std::wstring::~wstring(v20);
LABEL_16:
  WaasMedic::SafeFree(v7, v11);
  BCryptCloseAlgorithmProvider(phAlgorithm[0], 0);
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3);
  }
  std::wstring::~wstring(v21);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800283c8  mov     [rsp-28h+arg_0], rbx
0x1800283cd  mov     [rsp-28h+arg_10], rsi
0x1800283d2  push    rbp
0x1800283d3  push    rdi
0x1800283d4  push    r12
0x1800283d6  push    r14
0x1800283d8  push    r15
0x1800283da  mov     rbp, rsp
0x1800283dd  sub     rsp, 80h
0x1800283e4  mov     rax, cs:__security_cookie
0x1800283eb  xor     rax, rsp
0x1800283ee  mov     [rbp+var_10], rax
0x1800283f2  mov     r15, rdx
0x1800283f5  xor     r12d, r12d
0x1800283f8  mov     [rbp+phAlgorithm], r12
0x1800283fc  xorps   xmm0, xmm0
0x1800283ff  movups  [rbp+var_30], xmm0
0x180028403  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002840b  movdqu  [rbp+var_20], xmm1
0x180028410  mov     word ptr [rbp+var_30], r12w
0x180028415  mov     ebx, r12d
0x180028418  xor     r9d, r9d; dwFlags
0x18002841b  xor     r8d, r8d; pszImplementation
0x18002841e  lea     rdx, pszAlgId; "RNG"
0x180028425  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180028429  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18002842f  test    eax, eax
0x180028431  jz      short loc_18002844B
0x180028433  mov     r14d, r12d
0x180028436  mov     ecx, eax; int
0x180028438  call    ?HRESULT_FROM_NTSTATUS@MiscUtil@WaasMedic@@SAJJ@Z; WaasMedic::MiscUtil::HRESULT_FROM_NTSTATUS(long)
0x18002843d  mov     edi, eax
0x18002843f  lea     rdx, aCouldNotOpenPr; "Could not open provider. Error: 0x%08x."
0x180028446  jmp     loc_180028528
0x18002844b  mov     ecx, 10h; this
0x180028450  call    ?SafeAlloc@WaasMedic@@YAPEAX_K_N@Z; WaasMedic::SafeAlloc(unsigned __int64,bool)
0x180028455  mov     r14, rax
0x180028458  test    rax, rax
0x18002845b  jnz     short loc_180028472
0x18002845d  mov     r8d, 8007000Eh
0x180028463  mov     edi, r8d
0x180028466  lea     rdx, aCouldNotAlloca; "Could not allocate memory for the reque"...
0x18002846d  jmp     loc_18002852B
0x180028472  xor     r9d, r9d; dwFlags
0x180028475  lea     r8d, [r9+10h]; cbBuffer
0x180028479  mov     rdx, r14; pbBuffer
0x18002847c  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180028480  call    cs:__imp_BCryptGenRandom
0x180028486  test    eax, eax
0x180028488  jz      short loc_18002849F
0x18002848a  mov     ecx, eax; int
0x18002848c  call    ?HRESULT_FROM_NTSTATUS@MiscUtil@WaasMedic@@SAJJ@Z; WaasMedic::MiscUtil::HRESULT_FROM_NTSTATUS(long)
0x180028491  mov     edi, eax
0x180028493  lea     rdx, aCouldNotGetRan; "Could not get random number from the pr"...
0x18002849a  jmp     loc_180028528
0x18002849f  mov     ecx, 42h ; 'B'; this
0x1800284a4  call    ?SafeAlloc@WaasMedic@@YAPEAX_K_N@Z; WaasMedic::SafeAlloc(unsigned __int64,bool)
0x1800284a9  mov     rbx, rax
0x1800284ac  mov     [rbp+var_58], rax
0x1800284b0  test    rax, rax
0x1800284b3  jz      short loc_18002845D
0x1800284b5  mov     rsi, r12
0x1800284b8  movzx   r9d, byte ptr [r14+rsi]
0x1800284bd  lea     rcx, [rbx+rsi*4]; unsigned __int16 *
0x1800284c1  lea     r8, a02x; "%02x"
0x1800284c8  mov     edx, 3; unsigned __int64
0x1800284cd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800284d2  mov     edi, eax
0x1800284d4  test    eax, eax
0x1800284d6  js      short loc_180028521
0x1800284d8  inc     rsi
0x1800284db  cmp     rsi, 10h
0x1800284df  jb      short loc_1800284B8
0x1800284e1  xorps   xmm0, xmm0
0x1800284e4  movups  [rbp+var_50], xmm0
0x1800284e8  xorps   xmm1, xmm1
0x1800284eb  movdqu  [rbp+var_40], xmm1
0x1800284f0  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800284f4  inc     r8
0x1800284f7  cmp     [rbx+r8*2], r12w
0x1800284fc  jnz     short loc_1800284F4
0x1800284fe  mov     rdx, rbx
0x180028501  lea     rcx, [rbp+var_50]
0x180028505  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002850a  lea     rdx, [rbp+var_50]
0x18002850e  mov     rcx, r15
0x180028511  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180028516  lea     rcx, [rbp+var_50]; void *
0x18002851a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002851f  jmp     short loc_180028535
0x180028521  lea     rdx, aCouldNotWriteC; "Could not write characters to the gener"...
0x180028528  mov     r8d, eax
0x18002852b  mov     ecx, 2; unsigned __int8
0x180028530  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180028535  mov     rcx, r14; this
0x180028538  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x18002853d  xor     edx, edx; dwFlags
0x18002853f  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180028543  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180028549  nop
0x18002854a  test    rbx, rbx
0x18002854d  jz      short loc_180028564
0x18002854f  call    cs:__imp_GetProcessHeap
0x180028555  mov     rcx, rax; hHeap
0x180028558  mov     r8, rbx; lpMem
0x18002855b  xor     edx, edx; dwFlags
0x18002855d  call    cs:__imp_HeapFree
0x180028563  nop
0x180028564  lea     rcx, [rbp+var_30]; void *
0x180028568  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002856d  mov     eax, edi
0x18002856f  mov     rcx, [rbp+var_10]
0x180028573  xor     rcx, rsp; StackCookie
0x180028576  call    __security_check_cookie
0x18002857b  lea     r11, [rsp+80h+var_s0]
0x180028583  mov     rbx, [r11+30h]
0x180028587  mov     rsi, [r11+40h]
0x18002858b  mov     rsp, r11
0x18002858e  pop     r15
0x180028590  pop     r14
0x180028592  pop     r12
0x180028594  pop     rdi
0x180028595  pop     rbp
0x180028596  retn
```
