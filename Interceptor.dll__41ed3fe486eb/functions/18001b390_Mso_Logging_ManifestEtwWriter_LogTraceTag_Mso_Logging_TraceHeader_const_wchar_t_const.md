# Mso::Logging::ManifestEtwWriter::LogTraceTag(Mso::Logging::TraceHeader const &,wchar_t const *)

- ea: `0x18001b390`
- end: `0x18001b696`
- name: `?LogTraceTag@ManifestEtwWriter@Logging@Mso@@UEAAXAEBUTraceHeader@23@PEB_W@Z`
- size: `774`
- prototype: `void __fastcall(Mso::Logging::ManifestEtwWriter *__hidden this, const struct Mso::Logging::TraceHeader *, const wchar_t *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x18000410c`
- `0x18000ac10`
- `0x180012318`
- `0x18001293c`
- `0x1800129fc`
- `0x180012b18`
- `0x18001b390`
- `0x1800266e0`
- `0x18002b3c0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001b638`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001b638`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001b63f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001b63f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Mso::Logging::ManifestEtwWriter::LogTraceTag(
        Mso::Logging::ManifestEtwWriter *this,
        const struct Mso::Logging::TraceHeader *a2,
        const wchar_t *a3)
{
  __int64 *v6; // rdi
  __int64 *v7; // rdx
  __int64 v8; // rbx
  __int64 v9; // r8
  __int64 v10; // rax
  const wchar_t *v11; // rsi
  __int64 v12; // rcx
  __int64 v13; // rdx
  void **v14; // rax
  __int64 v15; // rax
  int v16; // ecx
  const wchar_t *v17; // rax
  __int64 v18; // rax
  __int64 v19; // rcx
  void *v20; // rcx
  __int64 v21; // rcx
  _QWORD v22[2]; // [rsp+38h] [rbp-69h] BYREF
  __int64 v23; // [rsp+48h] [rbp-59h] BYREF
  int v24; // [rsp+50h] [rbp-51h]
  void *Block[2]; // [rsp+58h] [rbp-49h] BYREF
  __m128i si128; // [rsp+68h] [rbp-39h]
  void **v27; // [rsp+78h] [rbp-29h] BYREF
  __int32 v28; // [rsp+80h] [rbp-21h]
  int v29; // [rsp+84h] [rbp-1Dh]
  const wchar_t *v30; // [rsp+88h] [rbp-19h]
  int v31; // [rsp+90h] [rbp-11h]
  int v32; // [rsp+94h] [rbp-Dh]
  __int64 *v33; // [rsp+98h] [rbp-9h]
  int v34; // [rsp+A0h] [rbp-1h]
  int v35; // [rsp+A4h] [rbp+3h]
  const wchar_t *v36; // [rsp+A8h] [rbp+7h]
  int v37; // [rsp+B0h] [rbp+Fh]
  int v38; // [rsp+B4h] [rbp+13h]
  __int128 v39; // [rsp+B8h] [rbp+17h] BYREF

  if ( !a3 )
  {
    v21 = 7463952;
LABEL_50:
    MsoShipAssertTagProc(v21);
    return;
  }
  switch ( *((_BYTE *)a2 + 8) )
  {
    case 6:
    case 0xA:
      v6 = LoggingLibletError;
      goto LABEL_13;
    case 0xF:
      v6 = LoggingLibletWarning;
      goto LABEL_13;
    case 0x32:
      v6 = LoggingLibletInfo;
      goto LABEL_13;
    case 0x64:
      v6 = LoggingLibletVerbose;
      goto LABEL_13;
  }
  if ( *((unsigned __int8 *)a2 + 8) != 200 )
  {
    v21 = 7463953;
    goto LABEL_50;
  }
  v6 = LoggingLibletSpam;
LABEL_13:
  v7 = &qword_180064480;
  v8 = -1;
  if ( (*((_QWORD *)&xmmword_180064490 + 1) <= 7u || (v7 = (__int64 *)qword_180064480) != 0) && *(_WORD *)v7 )
  {
    *(_OWORD *)Block = 0;
    si128 = 0;
    v9 = -1;
    do
      ++v9;
    while ( *((_WORD *)v7 + v9) );
    std::wstring::_Construct<1,wchar_t const *>(Block, v7, v9);
  }
  else
  {
    *(_OWORD *)Block = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(Block[0]) = 0;
  }
  v10 = *((unsigned int *)a2 + 1);
  if ( (unsigned int)v10 >= 0xA7A )
  {
    v11 = L"Unknown category";
  }
  else
  {
    _mm_lfence();
    v11 = `Mso::Logging::GetCategoryName'::`2'::categoryNames[v10];
  }
  v12 = *(unsigned int *)a2;
  v23 = 0;
  v24 = 0;
  if ( (unsigned int)v12 > 0xFFFF )
  {
    if ( BYTE3(v12) < 0x24u )
    {
      TaggingUtilities::FiveCharTagToString<wchar_t>(v12, &v23);
    }
    else
    {
      LOWORD(v23) = BYTE3(v12);
      v13 = 255;
      WORD1(v23) = BYTE2(v12);
      WORD2(v23) = BYTE1(v12);
      HIWORD(v23) = (unsigned __int8)v12;
      LOWORD(v24) = 0;
    }
  }
  else
  {
    TaggingUtilities::NumericTagToString<wchar_t>(v12, &v23);
  }
  v14 = Block;
  if ( si128.m128i_i64[1] > 7uLL )
    v14 = (void **)Block[0];
  v27 = v14;
  v28 = 2 * si128.m128i_i32[0] + 2;
  v29 = 0;
  if ( v11 )
  {
    v15 = -1;
    do
      ++v15;
    while ( v11[v15] );
    v16 = 2 * v15 + 2;
  }
  else
  {
    v16 = 10;
  }
  v17 = L"NULL";
  if ( v11 )
    v17 = v11;
  v30 = v17;
  v31 = v16;
  v32 = 0;
  v18 = -1;
  do
    ++v18;
  while ( *((_WORD *)&v23 + v18) );
  v33 = &v23;
  v34 = 2 * v18 + 2;
  v35 = 0;
  do
    ++v8;
  while ( a3[v8] );
  v36 = a3;
  v37 = 2 * v8 + 2;
  v38 = 0;
  v39 = (__int128)*Mso::Logging::GetCurrentCorrelation((Mso::Logging *)v22, (struct _GUID *)v13);
  v22[0] = v6;
  v19 = *((_QWORD *)this + 2);
  if ( !v19 )
    CrashWithRecovery(0x1E3C3840u, 0);
  (*(void (__fastcall **)(__int64, ULONGLONG *, _QWORD *, __int128 *, void ***))(*(_QWORD *)v19 + 24LL))(
    v19,
    &providerEtwLogging_Context,
    v22,
    &v39,
    &v27);
  if ( si128.m128i_i64[1] > 7uLL )
  {
    v20 = Block[0];
    if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
    {
      v20 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v20 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v20);
  }
}

```

## disassembly

```asm
0x18001b390  mov     rax, rsp
0x18001b393  mov     [rax+10h], rbx
0x18001b397  mov     [rax+18h], rsi
0x18001b39b  mov     [rax+20h], rdi
0x18001b39f  push    rbp
0x18001b3a0  push    r12
0x18001b3a2  push    r13
0x18001b3a4  push    r14
0x18001b3a6  push    r15
0x18001b3a8  lea     rbp, [rax-5Fh]
0x18001b3ac  sub     rsp, 0D0h
0x18001b3b3  mov     rax, cs:__security_cookie
0x18001b3ba  xor     rax, rsp
0x18001b3bd  mov     [rbp+57h+var_30], rax
0x18001b3c1  mov     r15, r8
0x18001b3c4  mov     r14, rdx
0x18001b3c7  mov     r13, rcx
0x18001b3ca  xor     r12d, r12d
0x18001b3cd  test    r8, r8
0x18001b3d0  jz      loc_18001B682
0x18001b3d6  movzx   ecx, byte ptr [rdx+8]
0x18001b3da  sub     ecx, 6
0x18001b3dd  jz      short loc_18001B420
0x18001b3df  sub     ecx, 4
0x18001b3e2  jz      short loc_18001B420
0x18001b3e4  sub     ecx, 5
0x18001b3e7  jz      short loc_18001B417
0x18001b3e9  sub     ecx, 23h ; '#'
0x18001b3ec  jz      short loc_18001B40E
0x18001b3ee  sub     ecx, 32h ; '2'
0x18001b3f1  jz      short loc_18001B405
0x18001b3f3  cmp     ecx, 64h ; 'd'
0x18001b3f6  jnz     loc_18001B68E
0x18001b3fc  lea     rdi, LoggingLibletSpam
0x18001b403  jmp     short loc_18001B427
0x18001b405  lea     rdi, LoggingLibletVerbose
0x18001b40c  jmp     short loc_18001B427
0x18001b40e  lea     rdi, LoggingLibletInfo
0x18001b415  jmp     short loc_18001B427
0x18001b417  lea     rdi, LoggingLibletWarning
0x18001b41e  jmp     short loc_18001B427
0x18001b420  lea     rdi, LoggingLibletError
0x18001b427  lea     rdx, qword_180064480
0x18001b42e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001b432  cmp     qword ptr cs:xmmword_180064490+8, 7
0x18001b43a  jbe     short loc_18001B448
0x18001b43c  mov     rdx, cs:qword_180064480
0x18001b443  test    rdx, rdx
0x18001b446  jz      short loc_18001B475
0x18001b448  cmp     [rdx], r12w
0x18001b44c  jz      short loc_18001B475
0x18001b44e  xorps   xmm0, xmm0
0x18001b451  movups  xmmword ptr [rbp+57h+Block], xmm0
0x18001b455  xorps   xmm1, xmm1
0x18001b458  movdqu  [rbp+57h+var_90], xmm1
0x18001b45d  mov     r8, rbx
0x18001b460  inc     r8
0x18001b463  cmp     [rdx+r8*2], r12w
0x18001b468  jnz     short loc_18001B460
0x18001b46a  lea     rcx, [rbp+57h+Block]
0x18001b46e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001b473  jmp     short loc_18001B48E
0x18001b475  xorps   xmm0, xmm0
0x18001b478  movups  xmmword ptr [rbp+57h+Block], xmm0
0x18001b47c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001b484  movdqu  [rbp+57h+var_90], xmm1
0x18001b489  mov     word ptr [rbp+57h+Block], r12w
0x18001b48e  mov     eax, [r14+4]
0x18001b492  cmp     eax, 0A7Ah
0x18001b497  jnb     short loc_18001B4A9
0x18001b499  lfence
0x18001b49c  lea     rsi, ?categoryNames@?1??GetCategoryName@Logging@Mso@@YAPEB_WW4Category@23@@Z@4PAPEB_WA; wchar_t const * near * `Mso::Logging::GetCategoryName(Mso::Logging::Category)'::`2'::categoryNames
0x18001b4a3  mov     rsi, [rsi+rax*8]
0x18001b4a7  jmp     short loc_18001B4B0
0x18001b4a9  lea     rsi, aUnknownCategor; "Unknown category"
0x18001b4b0  mov     ecx, [r14]
0x18001b4b3  xor     eax, eax
0x18001b4b5  mov     [rbp+57h+var_B0], rax
0x18001b4b9  mov     [rbp+57h+var_A8], eax
0x18001b4bc  cmp     ecx, 0FFFFh
0x18001b4c2  ja      short loc_18001B4CF
0x18001b4c4  lea     rdx, [rbp+57h+var_B0]
0x18001b4c8  call    ??$NumericTagToString@_W@TaggingUtilities@@YA_NIPEA_W@Z; TaggingUtilities::NumericTagToString<wchar_t>(uint,wchar_t *)
0x18001b4cd  jmp     short loc_18001B511
0x18001b4cf  mov     eax, ecx
0x18001b4d1  shr     eax, 18h
0x18001b4d4  cmp     eax, 24h ; '$'
0x18001b4d7  jb      short loc_18001B508
0x18001b4d9  mov     word ptr [rbp+57h+var_B0], ax
0x18001b4dd  mov     eax, ecx
0x18001b4df  shr     eax, 10h
0x18001b4e2  mov     edx, 0FFh
0x18001b4e7  and     ax, dx
0x18001b4ea  mov     word ptr [rbp+57h+var_B0+2], ax
0x18001b4ee  mov     eax, ecx
0x18001b4f0  shr     eax, 8
0x18001b4f3  and     ax, dx
0x18001b4f6  mov     word ptr [rbp+57h+var_B0+4], ax
0x18001b4fa  and     cx, dx
0x18001b4fd  mov     word ptr [rbp+57h+var_B0+6], cx
0x18001b501  mov     word ptr [rbp+57h+var_A8], r12w
0x18001b506  jmp     short loc_18001B511
0x18001b508  lea     rdx, [rbp+57h+var_B0]
0x18001b50c  call    ??$FiveCharTagToString@_W@TaggingUtilities@@YA_NIPEA_W@Z; TaggingUtilities::FiveCharTagToString<wchar_t>(uint,wchar_t *)
0x18001b511  lea     rax, [rbp+57h+Block]
0x18001b515  cmp     qword ptr [rbp+57h+var_90+8], 7
0x18001b51a  cmova   rax, [rbp+57h+Block]
0x18001b51f  mov     [rbp+57h+var_80], rax
0x18001b523  mov     eax, dword ptr [rbp+57h+var_90]
0x18001b526  lea     eax, ds:2[rax*2]
0x18001b52d  mov     [rbp+57h+var_78], eax
0x18001b530  mov     [rbp+57h+var_74], r12d
0x18001b534  test    rsi, rsi
0x18001b537  jz      short loc_18001B54F
0x18001b539  mov     rax, rbx
0x18001b53c  inc     rax
0x18001b53f  cmp     [rsi+rax*2], r12w
0x18001b544  jnz     short loc_18001B53C
0x18001b546  lea     ecx, ds:2[rax*2]
0x18001b54d  jmp     short loc_18001B554
0x18001b54f  mov     ecx, 0Ah
0x18001b554  lea     rax, aNull_0; "NULL"
0x18001b55b  test    rsi, rsi
0x18001b55e  cmovnz  rax, rsi
0x18001b562  mov     [rbp+57h+var_70], rax
0x18001b566  mov     [rbp+57h+var_68], ecx
0x18001b569  mov     [rbp+57h+var_64], r12d
0x18001b56d  lea     rcx, [rbp+57h+var_B0]
0x18001b571  mov     rax, rbx
0x18001b574  inc     rax
0x18001b577  cmp     [rcx+rax*2], r12w
0x18001b57c  jnz     short loc_18001B574
0x18001b57e  lea     eax, ds:2[rax*2]
0x18001b585  lea     rcx, [rbp+57h+var_B0]
0x18001b589  mov     [rbp+57h+var_60], rcx
0x18001b58d  mov     [rbp+57h+var_58], eax
0x18001b590  mov     [rbp+57h+var_54], r12d
0x18001b594  inc     rbx
0x18001b597  cmp     [r15+rbx*2], r12w
0x18001b59c  jnz     short loc_18001B594
0x18001b59e  lea     eax, ds:2[rbx*2]
0x18001b5a5  mov     [rbp+57h+var_50], r15
0x18001b5a9  mov     [rbp+57h+var_48], eax
0x18001b5ac  mov     [rbp+57h+var_44], r12d
0x18001b5b0  lea     rcx, [rbp+57h+var_C0]; this
0x18001b5b4  call    ?GetCurrentCorrelation@Logging@Mso@@YA?AU_GUID@@XZ; Mso::Logging::GetCurrentCorrelation(void)
0x18001b5b9  movups  xmm2, xmmword ptr [rax]
0x18001b5bc  movdqu  [rbp+57h+var_40], xmm2
0x18001b5c1  mov     [rbp+57h+var_C0], rdi
0x18001b5c5  mov     rcx, [r13+10h]
0x18001b5c9  test    rcx, rcx
0x18001b5cc  jz      loc_18001B672
0x18001b5d2  mov     rax, [rcx]
0x18001b5d5  lea     rdx, [rbp+57h+var_80]
0x18001b5d9  mov     [rsp+0F0h+Reserved], rdx
0x18001b5de  lea     r9, [rbp+57h+var_40]
0x18001b5e2  lea     r8, [rbp+57h+var_C0]
0x18001b5e6  lea     rdx, providerEtwLogging_Context
0x18001b5ed  mov     rax, [rax+18h]
0x18001b5f1  call    cs:__guard_dispatch_icall_fptr
0x18001b5f7  mov     rax, qword ptr [rbp+57h+var_90+8]
0x18001b5fb  cmp     rax, 7
0x18001b5ff  jbe     short loc_18001B645
0x18001b601  mov     rcx, [rbp+57h+Block]; Block
0x18001b605  mov     rdx, rcx
0x18001b608  lea     rax, ds:2[rax*2]
0x18001b610  cmp     rax, 1000h
0x18001b616  jb      short loc_18001B63F
0x18001b618  mov     rcx, [rcx-8]
0x18001b61c  sub     rdx, rcx
0x18001b61f  lea     rax, [rdx-8]
0x18001b623  cmp     rax, 1Fh
0x18001b627  jbe     short loc_18001B63F
0x18001b629  mov     [rsp+0F0h+Reserved], r12; Reserved
0x18001b62e  xor     r9d, r9d; LineNo
0x18001b631  xor     r8d, r8d; FileName
0x18001b634  xor     edx, edx; FunctionName
0x18001b636  xor     ecx, ecx; Expression
0x18001b638  call    cs:__imp__invoke_watson
0x18001b63f  call    cs:__imp_free
0x18001b645  mov     rcx, [rbp+57h+var_30]
0x18001b649  xor     rcx, rsp; StackCookie
0x18001b64c  call    __security_check_cookie
0x18001b651  lea     r11, [rsp+0F0h+var_20]
0x18001b659  mov     rbx, [r11+38h]
0x18001b65d  mov     rsi, [r11+40h]
0x18001b661  mov     rdi, [r11+48h]
0x18001b665  mov     rsp, r11
0x18001b668  pop     r15
0x18001b66a  pop     r14
0x18001b66c  pop     r13
0x18001b66e  pop     r12
0x18001b670  pop     rbp
0x18001b671  retn
0x18001b672  xor     edx, edx; struct CrashContext *
0x18001b674  mov     ecx, 1E3C3840h; unsigned int
0x18001b679  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18001b67f  jmp     short $+2
0x18001b681  nop
0x18001b682  mov     ecx, 71E410h
0x18001b687  call    MsoShipAssertTagProc
0x18001b68c  jmp     short loc_18001B645
0x18001b68e  mov     ecx, 71E411h
0x18001b693  jmp     short loc_18001B687
```
