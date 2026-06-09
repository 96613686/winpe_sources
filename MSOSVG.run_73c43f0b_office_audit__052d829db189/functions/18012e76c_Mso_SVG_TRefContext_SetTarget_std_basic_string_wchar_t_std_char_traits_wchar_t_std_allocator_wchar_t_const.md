# Mso::SVG::TRefContext::SetTarget(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18012e76c`
- end: `0x18012ed6e`
- name: `?SetTarget@TRefContext@SVG@Mso@@AEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `1538`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callers

- `0x1800e0d40`

## callees

- `0x180008bdc`
- `0x180008cf8`
- `0x180009068`
- `0x18001ba6c`
- `0x18012cfe0`
- `0x18012daa4`
- `0x18012e76c`
- `0x180130df0`
- `0x18013b708`
- `0x18013ba2c`
- `0x18013d700`
- `0x18013f794`
- `0x18013f810`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18012e970`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18012e970`
- `OLEAUT32!__imp_SysFreeString` at `0x18012ec47`
- `OLEAUT32!__imp_SysFreeString` at `0x18012ec56`
- `OLEAUT32!__imp_SysFreeString` at `0x18012ec47`
- `OLEAUT32!__imp_SysFreeString` at `0x18012ec56`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18012ecc0`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18012ecdc`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18012ed0e`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18012ed38`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18012ed67`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18012ecc0`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18012ecdc`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18012ed0e`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18012ed38`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18012ed67`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x18012ed00`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x18012ed54`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x18012ed00`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x18012ed54`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18012eb31`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18012eb31`
- `Mso20Win32Client!__imp_?isStartNameChar@XmlCharacter@@SAH_W@Z` at `0x18012e7ed`
- `Mso20Win32Client!__imp_?isStartNameChar@XmlCharacter@@SAH_W@Z` at `0x18012e7ed`
- `Mso20Win32Client!__imp_?isNameChar@XmlCharacter@@SAH_W@Z` at `0x18012e81c`
- `Mso20Win32Client!__imp_?isNameChar@XmlCharacter@@SAH_W@Z` at `0x18012e81c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012e9dc`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012ea3c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012ea97`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012ebfd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012e9dc`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012ea3c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012ea97`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012ebfd`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012e9d2`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012ea35`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012ea90`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012ebf6`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012e9d2`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012ea35`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012ea90`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012ebf6`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
void __fastcall Mso::SVG::TRefContext::SetTarget(__int64 a1, wchar_t *a2)
{
  __int64 v4; // rcx
  int v5; // eax
  wchar_t *v6; // rcx
  _QWORD *v7; // rcx
  wchar_t *v8; // rsi
  wchar_t *v9; // rbx
  unsigned __int64 v10; // rsi
  __int64 v11; // r15
  void **v12; // rbx
  void **appended; // rax
  __int64 v14; // rax
  void **v15; // rcx
  char *v16; // r8
  unsigned __int64 v17; // r9
  OLECHAR *v18; // rbx
  __int64 v19; // rdi
  unsigned __int64 v20; // rdx
  bool v21; // al
  char *v22; // rcx
  __m128i si128; // xmm0
  void *v24; // rcx
  void *v25; // rcx
  __int64 v26; // rax
  int v27; // eax
  int v28; // eax
  unsigned int v29; // r8d
  void *v30; // rax
  __int64 v31; // r8
  __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rsi
  void *v35; // rcx
  Mso::SVG::TSpanContext *v36; // rcx
  __int64 v37; // rcx
  OLECHAR *v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  char v41; // [rsp+30h] [rbp-69h]
  BSTR bstrString; // [rsp+38h] [rbp-61h] BYREF
  __int64 v43; // [rsp+40h] [rbp-59h] BYREF
  __int64 v44; // [rsp+48h] [rbp-51h] BYREF
  OLECHAR *v45; // [rsp+50h] [rbp-49h]
  void *Src[2]; // [rsp+58h] [rbp-41h] BYREF
  __m128i v47; // [rsp+68h] [rbp-31h]
  void *v48[2]; // [rsp+78h] [rbp-21h] BYREF
  __m128i v49; // [rsp+88h] [rbp-11h]
  void *Block[2]; // [rsp+98h] [rbp-1h] BYREF
  __m128i v51; // [rsp+A8h] [rbp+Fh]

  v44 = 0;
  v4 = *(_QWORD *)(a1 + 440);
  if ( !v4 )
    goto LABEL_77;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v4 + 152LL))(v4, &v44);
  if ( v5 < 0 )
  {
LABEL_78:
    Ofc::CHResultException::ThrowTag(v5, 0x138D8C6u);
LABEL_79:
    safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
  }
  if ( !*((_QWORD *)a2 + 2) )
    goto LABEL_76;
  v6 = a2;
  if ( *((_QWORD *)a2 + 3) > 7u )
    v6 = *(wchar_t **)a2;
  if ( !XmlCharacter::isStartNameChar(*v6) )
  {
LABEL_76:
    Ofc::CInvalidOperationException::ThrowTag(0x138D8C7u);
LABEL_77:
    CrashWithRecovery(0x1E3C3840u, 0);
    goto LABEL_78;
  }
  v7 = a2;
  if ( *((_QWORD *)a2 + 3) > 7u )
    v7 = *(_QWORD **)a2;
  v8 = (wchar_t *)v7 + *((_QWORD *)a2 + 2);
  v9 = a2;
  if ( *((_QWORD *)a2 + 3) > 7u )
    v9 = *(wchar_t **)a2;
  while ( ++v9 != v8 )
  {
    if ( !XmlCharacter::isNameChar(*v9) )
      goto LABEL_76;
  }
  v43 = 0;
  *(_OWORD *)Src = 0;
  v47 = 0;
  std::wstring::_Construct<1,wchar_t *>(Src, L"//*[@id=\"");
  v10 = *((_QWORD *)a2 + 2);
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(wchar_t **)a2;
  v11 = v47.m128i_i64[0];
  if ( v10 > v47.m128i_i64[1] - v47.m128i_i64[0] )
  {
    appended = (void **)____Reallocate_grow_by_V_lambda_1___1__append___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAAEAV34_QEB_W_K_Z_PEB_W_K___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_QEB_W0_Z_PEB_W_K_Z(
                          Src,
                          v10);
  }
  else
  {
    v47.m128i_i64[0] += v10;
    v12 = Src;
    if ( v47.m128i_i64[1] > 7uLL )
      v12 = (void **)Src[0];
    memmove_0((char *)v12 + 2 * v11, a2, 2 * v10);
    *((_WORD *)v12 + v10 + v11) = 0;
    appended = Src;
  }
  *(_OWORD *)v48 = 0;
  v49 = 0;
  *(_OWORD *)v48 = *(_OWORD *)appended;
  v49 = *((__m128i *)appended + 1);
  appended[3] = (void *)7;
  *(_WORD *)appended = 0;
  appended[2] = 0;
  v14 = std::wstring::append(v48, L"\"]");
  *(_OWORD *)Block = 0;
  v51 = 0;
  *(_OWORD *)Block = *(_OWORD *)v14;
  v51 = *(__m128i *)(v14 + 16);
  *(_WORD *)v14 = 0;
  *(_QWORD *)(v14 + 16) = 0;
  *(_QWORD *)(v14 + 24) = 7;
  v15 = Block;
  v16 = (char *)Block[0];
  v17 = v51.m128i_u64[1];
  if ( v51.m128i_i64[1] > 7uLL )
    v15 = (void **)Block[0];
  v18 = 0;
  v45 = 0;
  v19 = -1;
  if ( v15 )
  {
    v20 = -1;
    do
      ++v20;
    while ( *((_WORD *)v15 + v20) );
  }
  else
  {
    v15 = 0;
    v20 = 0;
  }
  if ( v15 )
  {
    if ( v20 > 0xFFFFFFFF )
      goto LABEL_79;
    v18 = SysAllocStringLen((const OLECHAR *)v15, v20);
    v45 = v18;
    v21 = v18 != 0;
    v17 = v51.m128i_u64[1];
    v16 = (char *)Block[0];
  }
  else
  {
    v21 = 1;
  }
  if ( !v21 )
  {
    CrashWithRecoveryOnOOM(0x1F3632D0u);
LABEL_81:
    CrashWithRecovery(0x1E3C3840u, 0);
LABEL_82:
    Ofc::CHResultException::ThrowTag(v27, 0x138D8C8u);
    __debugbreak();
  }
  if ( v17 > 7 )
  {
    v22 = v16;
    if ( 2 * v17 + 2 >= 0x1000 )
    {
      v16 = (char *)*((_QWORD *)v16 - 1);
      if ( (unsigned __int64)(v22 - v16 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v16);
  }
  Block[0] = (void *)19937;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v51 = si128;
  if ( v49.m128i_i64[1] > 7uLL )
  {
    v24 = v48[0];
    if ( (unsigned __int64)(2 * v49.m128i_i64[1] + 2) >= 0x1000 )
    {
      v24 = (void *)*((_QWORD *)v48[0] - 1);
      if ( (unsigned __int64)((char *)v48[0] - (char *)v24 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v24);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
  }
  v48[0] = (void *)19937;
  v49 = si128;
  if ( v47.m128i_i64[1] > 7uLL )
  {
    v25 = Src[0];
    if ( (unsigned __int64)(2 * v47.m128i_i64[1] + 2) >= 0x1000 )
    {
      v25 = (void *)*((_QWORD *)Src[0] - 1);
      if ( (unsigned __int64)((char *)Src[0] - (char *)v25 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v25);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
  }
  Src[0] = (void *)19937;
  v47 = si128;
  if ( !v44 )
    goto LABEL_81;
  v26 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, char *))(*(_QWORD *)v44 + 112LL))(v44, v20, v16);
  v27 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)v26 + 216LL))(v26, v18, &v43);
  if ( v27 < 0 )
    goto LABEL_82;
  if ( v27 == 1 )
  {
    Ofc::CInvalidOperationException::ThrowTag(0x138D8C9u);
    goto LABEL_84;
  }
  bstrString = 0;
  if ( !v43 )
  {
LABEL_84:
    CrashWithRecovery(0x1E3C3840u, 0);
    goto LABEL_85;
  }
  v28 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v43 + 168LL))(v43, &bstrString);
  if ( v28 < 0 )
  {
LABEL_85:
    Ofc::CHResultException::ThrowTag(v28, 0x138D8CAu);
    goto LABEL_86;
  }
  *(_OWORD *)Src = 0;
  v30 = Mso::Memory::AllocateEx((Mso::Memory *)0x208, 0, v29);
  Src[0] = v30;
  if ( !v30 )
  {
LABEL_86:
    CrashWithRecoveryOnOOM(0x1F65259Du);
    goto LABEL_87;
  }
  LOBYTE(v31) = v41;
  v32 = Mso::SVG::TSpanContext::TSpanContext(v30, a1, v31);
  v33 = *(_QWORD *)(a1 + 432);
  *(_QWORD *)(a1 + 432) = v32;
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 8LL))(v33);
  v34 = *(_QWORD *)(a1 + 432);
  if ( !v34 )
  {
LABEL_87:
    CrashWithRecovery(0x1E3C3840u, 0);
    JUMPOUT(0x18012ED6DLL);
  }
  *(_OWORD *)v48 = 0;
  v49 = 0;
  do
    ++v19;
  while ( bstrString[v19] );
  std::wstring::_Construct<1,wchar_t *>(v48, bstrString);
  Mso::SVG::TSpanContext::set_text<std::wstring>(v34, v48);
  if ( v49.m128i_i64[1] > 7uLL )
  {
    v35 = v48[0];
    if ( (unsigned __int64)(2 * v49.m128i_i64[1] + 2) >= 0x1000 )
    {
      v35 = (void *)*((_QWORD *)v48[0] - 1);
      if ( (unsigned __int64)((char *)v48[0] - (char *)v35 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v35);
  }
  v36 = *(Mso::SVG::TSpanContext **)(a1 + 432);
  if ( !v36 )
  {
    CrashWithRecovery(0x1E3C3840u, 0);
    goto LABEL_76;
  }
  Mso::SVG::TSpanContext::on_exit_element(v36);
  v37 = *(_QWORD *)(a1 + 440);
  if ( v37 )
  {
    *(_QWORD *)(a1 + 440) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 8LL))(v37);
  }
  v38 = bstrString;
  if ( bstrString )
  {
    bstrString = 0;
    SysFreeString(v38);
  }
  if ( v18 )
    SysFreeString(v18);
  v39 = v43;
  if ( v43 )
  {
    v43 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 8LL))(v39);
  }
  v40 = v44;
  if ( v44 )
  {
    v44 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 8LL))(v40);
  }
}

```

## disassembly

```asm
0x18012e76c  mov     [rsp-8+arg_10], rbx
0x18012e771  push    rbp
0x18012e772  push    rsi
0x18012e773  push    rdi
0x18012e774  push    r12
0x18012e776  push    r13
0x18012e778  push    r14
0x18012e77a  push    r15
0x18012e77c  lea     rbp, [rsp-27h]
0x18012e781  sub     rsp, 0C0h
0x18012e788  mov     rax, cs:__security_cookie
0x18012e78f  xor     rax, rsp
0x18012e792  mov     [rbp+57h+var_38], rax
0x18012e796  mov     rdi, rdx
0x18012e799  mov     r14, rcx
0x18012e79c  xor     r12d, r12d
0x18012e79f  mov     [rbp+57h+var_A8], r12
0x18012e7a3  mov     rcx, [rcx+1B8h]
0x18012e7aa  test    rcx, rcx
0x18012e7ad  jz      loc_18012ECD5
0x18012e7b3  mov     rax, [rcx]
0x18012e7b6  lea     rdx, [rbp+57h+var_A8]
0x18012e7ba  mov     rax, [rax+98h]
0x18012e7c1  call    cs:__guard_dispatch_icall_fptr
0x18012e7c7  test    eax, eax
0x18012e7c9  js      loc_18012ECE3
0x18012e7cf  cmp     [rdi+10h], r12
0x18012e7d3  jz      loc_18012ECC7
0x18012e7d9  mov     rcx, rdi
0x18012e7dc  lea     r13d, [r12+7]
0x18012e7e1  cmp     [rdi+18h], r13
0x18012e7e5  jbe     short loc_18012E7EA
0x18012e7e7  mov     rcx, [rdi]
0x18012e7ea  movzx   ecx, word ptr [rcx]
0x18012e7ed  call    cs:__imp_?isStartNameChar@XmlCharacter@@SAH_W@Z; XmlCharacter::isStartNameChar(wchar_t)
0x18012e7f3  test    eax, eax
0x18012e7f5  jz      loc_18012ECC7
0x18012e7fb  mov     rcx, rdi
0x18012e7fe  cmp     [rdi+18h], r13
0x18012e802  jbe     short loc_18012E807
0x18012e804  mov     rcx, [rdi]
0x18012e807  mov     rax, [rdi+10h]
0x18012e80b  lea     rsi, [rcx+rax*2]
0x18012e80f  mov     rbx, rdi
0x18012e812  jbe     short loc_18012E82A
0x18012e814  mov     rbx, [rdi]
0x18012e817  jmp     short loc_18012E82A
0x18012e819  movzx   ecx, word ptr [rbx]
0x18012e81c  call    cs:__imp_?isNameChar@XmlCharacter@@SAH_W@Z; XmlCharacter::isNameChar(wchar_t)
0x18012e822  test    eax, eax
0x18012e824  jz      loc_18012ECC7
0x18012e82a  add     rbx, 2
0x18012e82e  cmp     rbx, rsi
0x18012e831  jnz     short loc_18012E819
0x18012e833  mov     [rbp+57h+var_B0], r12
0x18012e837  xorps   xmm0, xmm0
0x18012e83a  movups  xmmword ptr [rbp+57h+Src], xmm0
0x18012e83e  xorps   xmm1, xmm1
0x18012e841  movdqu  [rbp+57h+var_88], xmm1
0x18012e846  mov     r8d, 9
0x18012e84c  lea     rdx, aId_0; "//*[@id=\""
0x18012e853  lea     rcx, [rbp+57h+Src]
0x18012e857  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x18012e85c  mov     rsi, [rdi+10h]
0x18012e860  cmp     [rdi+18h], r13
0x18012e864  jbe     short loc_18012E869
0x18012e866  mov     rdi, [rdi]
0x18012e869  mov     r15, qword ptr [rbp+57h+var_88]
0x18012e86d  mov     rax, qword ptr [rbp+57h+var_88+8]
0x18012e871  sub     rax, r15
0x18012e874  cmp     rsi, rax
0x18012e877  ja      short loc_18012E8AD
0x18012e879  lea     rax, [rsi+r15]
0x18012e87d  mov     qword ptr [rbp+57h+var_88], rax
0x18012e881  lea     rbx, [rbp+57h+Src]
0x18012e885  cmp     qword ptr [rbp+57h+var_88+8], r13
0x18012e889  cmova   rbx, [rbp+57h+Src]
0x18012e88e  lea     rcx, [rbx+r15*2]; void *
0x18012e892  lea     r8, [rsi+rsi]; Size
0x18012e896  mov     rdx, rdi; Src
0x18012e899  call    memmove_0
0x18012e89e  lea     rax, [rsi+r15]
0x18012e8a2  mov     [rbx+rax*2], r12w
0x18012e8a7  lea     rax, [rbp+57h+Src]
0x18012e8ab  jmp     short loc_18012E8C1
0x18012e8ad  mov     [rsp+0F0h+Reserved], rsi; __int64
0x18012e8b2  mov     r9, rdi
0x18012e8b5  mov     rdx, rsi
0x18012e8b8  lea     rcx, [rbp+57h+Src]; Src
0x18012e8bc  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV34@QEB_W_K@Z@PEB_W_K@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@QEB_W0@Z@PEB_W_K@Z; std::wstring::_Reallocate_grow_by<`std::wstring::append(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *,unsigned __int64>(unsigned __int64,`std::wstring::append(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *,unsigned __int64)
0x18012e8c1  xorps   xmm0, xmm0
0x18012e8c4  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x18012e8c8  xorps   xmm1, xmm1
0x18012e8cb  movdqu  [rbp+57h+var_68], xmm1
0x18012e8d0  movups  xmm0, xmmword ptr [rax]
0x18012e8d3  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x18012e8d7  movups  xmm1, xmmword ptr [rax+10h]
0x18012e8db  movups  [rbp+57h+var_68], xmm1
0x18012e8df  mov     [rax+18h], r13
0x18012e8e3  mov     [rax], r12w
0x18012e8e7  mov     [rax+10h], r12
0x18012e8eb  lea     rdx, asc_1801555D4; "\"]"
0x18012e8f2  lea     rcx, [rbp+57h+var_78]; Src
0x18012e8f6  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x18012e8fb  xorps   xmm0, xmm0
0x18012e8fe  movups  xmmword ptr [rbp+57h+Block], xmm0
0x18012e902  xorps   xmm1, xmm1
0x18012e905  movdqu  [rbp+57h+var_48], xmm1
0x18012e90a  movups  xmm0, xmmword ptr [rax]
0x18012e90d  movups  xmmword ptr [rbp+57h+Block], xmm0
0x18012e911  movups  xmm1, xmmword ptr [rax+10h]
0x18012e915  movups  [rbp+57h+var_48], xmm1
0x18012e919  mov     [rax], r12w
0x18012e91d  mov     [rax+10h], r12
0x18012e921  mov     [rax+18h], r13
0x18012e925  lea     rcx, [rbp+57h+Block]
0x18012e929  mov     r8, [rbp+57h+Block]
0x18012e92d  mov     r9, qword ptr [rbp+57h+var_48+8]
0x18012e931  cmp     r9, r13
0x18012e934  cmova   rcx, r8
0x18012e938  mov     rbx, r12
0x18012e93b  mov     [rbp+57h+var_A0], rbx
0x18012e93f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18012e943  test    rcx, rcx
0x18012e946  jz      short loc_18012E957
0x18012e948  mov     rdx, rdi
0x18012e94b  inc     rdx
0x18012e94e  cmp     [rcx+rdx*2], r12w
0x18012e953  jnz     short loc_18012E94B
0x18012e955  jmp     short loc_18012E95D
0x18012e957  mov     rcx, r12; strIn
0x18012e95a  mov     rdx, r12; ui
0x18012e95d  test    rcx, rcx
0x18012e960  jz      short loc_18012E98D
0x18012e962  mov     eax, 0FFFFFFFFh
0x18012e967  cmp     rdx, rax
0x18012e96a  ja      loc_18012ECF5
0x18012e970  call    cs:__imp_SysAllocStringLen
0x18012e976  mov     rbx, rax
0x18012e979  mov     [rbp+57h+var_A0], rax
0x18012e97d  test    rax, rax
0x18012e980  setnz   al
0x18012e983  mov     r9, qword ptr [rbp+57h+var_48+8]
0x18012e987  mov     r8, [rbp+57h+Block]
0x18012e98b  jmp     short loc_18012E98F
0x18012e98d  mov     al, 1
0x18012e98f  test    al, al
0x18012e991  jz      loc_18012ECFB
0x18012e997  mov     r15d, 1000h
0x18012e99d  cmp     r9, r13
0x18012e9a0  jbe     short loc_18012E9E2
0x18012e9a2  mov     rcx, r8
0x18012e9a5  lea     rax, ds:2[r9*2]
0x18012e9ad  cmp     rax, r15
0x18012e9b0  jb      short loc_18012E9D9
0x18012e9b2  mov     r8, [r8-8]
0x18012e9b6  sub     rcx, r8
0x18012e9b9  lea     rax, [rcx-8]
0x18012e9bd  cmp     rax, 1Fh
0x18012e9c1  jbe     short loc_18012E9D9
0x18012e9c3  mov     [rsp+0F0h+Reserved], r12; Reserved
0x18012e9c8  xor     r9d, r9d; LineNo
0x18012e9cb  xor     r8d, r8d; FileName
0x18012e9ce  xor     edx, edx; FunctionName
0x18012e9d0  xor     ecx, ecx; Expression
0x18012e9d2  call    cs:__imp__invoke_watson
0x18012e9d9  mov     rcx, r8; Block
0x18012e9dc  call    cs:__imp_free
0x18012e9e2  mov     esi, 4DE1h
0x18012e9e7  mov     [rbp+57h+Block], rsi
0x18012e9eb  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x18012e9f3  movdqu  [rbp+57h+var_48], xmm0
0x18012e9f8  mov     rax, qword ptr [rbp+57h+var_68+8]
0x18012e9fc  cmp     rax, r13
0x18012e9ff  jbe     short loc_18012EA4A
0x18012ea01  mov     rcx, [rbp+57h+var_78]; Block
0x18012ea05  mov     rdx, rcx
0x18012ea08  lea     rax, ds:2[rax*2]
0x18012ea10  cmp     rax, r15
0x18012ea13  jb      short loc_18012EA3C
0x18012ea15  mov     rcx, [rcx-8]
0x18012ea19  sub     rdx, rcx
0x18012ea1c  lea     rax, [rdx-8]
0x18012ea20  cmp     rax, 1Fh
0x18012ea24  jbe     short loc_18012EA3C
0x18012ea26  mov     [rsp+0F0h+Reserved], r12; Reserved
0x18012ea2b  xor     r9d, r9d; LineNo
0x18012ea2e  xor     r8d, r8d; FileName
0x18012ea31  xor     edx, edx; FunctionName
0x18012ea33  xor     ecx, ecx; Expression
0x18012ea35  call    cs:__imp__invoke_watson
0x18012ea3c  call    cs:__imp_free
0x18012ea42  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x18012ea4a  mov     [rbp+57h+var_78], rsi
0x18012ea4e  movdqu  [rbp+57h+var_68], xmm0
0x18012ea53  mov     rax, qword ptr [rbp+57h+var_88+8]
0x18012ea57  cmp     rax, r13
0x18012ea5a  jbe     short loc_18012EAA5
0x18012ea5c  mov     rcx, [rbp+57h+Src]; Block
0x18012ea60  mov     rdx, rcx
0x18012ea63  lea     rax, ds:2[rax*2]
0x18012ea6b  cmp     rax, r15
0x18012ea6e  jb      short loc_18012EA97
0x18012ea70  mov     rcx, [rcx-8]
0x18012ea74  sub     rdx, rcx
0x18012ea77  lea     rax, [rdx-8]
0x18012ea7b  cmp     rax, 1Fh
0x18012ea7f  jbe     short loc_18012EA97
0x18012ea81  mov     [rsp+0F0h+Reserved], r12; Reserved
0x18012ea86  xor     r9d, r9d; LineNo
0x18012ea89  xor     r8d, r8d; FileName
0x18012ea8c  xor     edx, edx; FunctionName
0x18012ea8e  xor     ecx, ecx; Expression
0x18012ea90  call    cs:__imp__invoke_watson
0x18012ea97  call    cs:__imp_free
0x18012ea9d  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x18012eaa5  mov     [rbp+57h+Src], rsi
0x18012eaa9  movdqu  [rbp+57h+var_88], xmm0
0x18012eaae  mov     rcx, [rbp+57h+var_A8]
0x18012eab2  test    rcx, rcx
0x18012eab5  jz      loc_18012ED07
0x18012eabb  mov     rax, [rcx]
0x18012eabe  mov     rax, [rax+70h]
0x18012eac2  call    cs:__guard_dispatch_icall_fptr
0x18012eac8  mov     r9, rax
0x18012eacb  mov     rcx, [rax]
0x18012eace  mov     rax, [rcx+0D8h]
0x18012ead5  lea     r8, [rbp+57h+var_B0]
0x18012ead9  mov     rdx, rbx
0x18012eadc  mov     rcx, r9
0x18012eadf  call    cs:__guard_dispatch_icall_fptr
0x18012eae5  test    eax, eax
0x18012eae7  js      loc_18012ED15
0x18012eaed  cmp     eax, 1
0x18012eaf0  jz      loc_18012ED22
0x18012eaf6  mov     [rbp+57h+bstrString], r12
0x18012eafa  mov     rcx, [rbp+57h+var_B0]
0x18012eafe  test    rcx, rcx
0x18012eb01  jz      loc_18012ED31
0x18012eb07  mov     rax, [rcx]
0x18012eb0a  lea     rdx, [rbp+57h+bstrString]
0x18012eb0e  mov     rax, [rax+0A8h]
0x18012eb15  call    cs:__guard_dispatch_icall_fptr
0x18012eb1b  test    eax, eax
0x18012eb1d  js      loc_18012ED3F
0x18012eb23  xorps   xmm0, xmm0
0x18012eb26  movups  xmmword ptr [rbp+57h+Src], xmm0
0x18012eb2a  xor     edx, edx
0x18012eb2c  mov     ecx, 208h
0x18012eb31  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x18012eb37  mov     [rbp+57h+Src], rax
0x18012eb3b  test    rax, rax
0x18012eb3e  jz      loc_18012ED4F
0x18012eb44  mov     r8b, [rbp+57h+var_C0]
0x18012eb48  mov     rdx, r14
0x18012eb4b  mov     rcx, rax
0x18012eb4e  call    ??0TSpanContext@SVG@Mso@@QEAA@AEAVStylableContext@12@Uinit_default_style_t@12@@Z; Mso::SVG::TSpanContext::TSpanContext(Mso::SVG::StylableContext &,Mso::SVG::init_default_style_t)
0x18012eb53  mov     rcx, [r14+1B0h]
0x18012eb5a  mov     [r14+1B0h], rax
0x18012eb61  test    rcx, rcx
0x18012eb64  jz      short loc_18012EB74
0x18012eb66  mov     rax, [rcx]
0x18012eb69  mov     rax, [rax+8]
0x18012eb6d  call    cs:__guard_dispatch_icall_fptr
0x18012eb73  nop
0x18012eb74  mov     rsi, [r14+1B0h]
0x18012eb7b  test    rsi, rsi
0x18012eb7e  jz      loc_18012ED60
0x18012eb84  xorps   xmm0, xmm0
0x18012eb87  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x18012eb8b  xorps   xmm1, xmm1
0x18012eb8e  movdqu  [rbp+57h+var_68], xmm1
0x18012eb93  mov     rdx, [rbp+57h+bstrString]
0x18012eb97  inc     rdi
0x18012eb9a  cmp     [rdx+rdi*2], r12w
0x18012eb9f  jnz     short loc_18012EB97
0x18012eba1  mov     r8, rdi
0x18012eba4  lea     rcx, [rbp+57h+var_78]
0x18012eba8  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x18012ebad  lea     rdx, [rbp+57h+var_78]
0x18012ebb1  mov     rcx, rsi
0x18012ebb4  call    ??$set_text@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@TSpanContext@SVG@Mso@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::SVG::TSpanContext::set_text<std::wstring>(std::wstring &&)
0x18012ebb9  mov     rax, qword ptr [rbp+57h+var_68+8]
0x18012ebbd  cmp     rax, r13
0x18012ebc0  jbe     short loc_18012EC04
0x18012ebc2  mov     rcx, [rbp+57h+var_78]; Block
0x18012ebc6  mov     rdx, rcx
0x18012ebc9  lea     rax, ds:2[rax*2]
0x18012ebd1  cmp     rax, r15
0x18012ebd4  jb      short loc_18012EBFD
0x18012ebd6  mov     rcx, [rcx-8]
0x18012ebda  sub     rdx, rcx
0x18012ebdd  lea     rax, [rdx-8]
0x18012ebe1  cmp     rax, 1Fh
0x18012ebe5  jbe     short loc_18012EBFD
0x18012ebe7  mov     [rsp+0F0h+Reserved], r12; Reserved
0x18012ebec  xor     r9d, r9d; LineNo
0x18012ebef  xor     r8d, r8d; FileName
0x18012ebf2  xor     edx, edx; FunctionName
0x18012ebf4  xor     ecx, ecx; Expression
  ... truncated ...
```
