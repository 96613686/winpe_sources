# Mso::SVG::TRefContext::SetTarget(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18012e73c`
- end: `0x18012ed3e`
- name: `?SetTarget@TRefContext@SVG@Mso@@AEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `1538`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callers

- `0x1800e0d20`

## callees

- `0x180008bdc`
- `0x180008cf8`
- `0x180009068`
- `0x18001ba6c`
- `0x18012cfb0`
- `0x18012da74`
- `0x18012e73c`
- `0x180130dc0`
- `0x18013b658`
- `0x18013b97c`
- `0x18013d650`
- `0x18013f6e4`
- `0x18013f760`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18012e940`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18012e940`
- `OLEAUT32!__imp_SysFreeString` at `0x18012ec17`
- `OLEAUT32!__imp_SysFreeString` at `0x18012ec26`
- `OLEAUT32!__imp_SysFreeString` at `0x18012ec17`
- `OLEAUT32!__imp_SysFreeString` at `0x18012ec26`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18012ec90`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18012ecac`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18012ecde`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18012ed08`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18012ed37`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18012ec90`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18012ecac`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18012ecde`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18012ed08`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18012ed37`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x18012ecd0`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x18012ed24`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x18012ecd0`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x18012ed24`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18012eb01`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18012eb01`
- `Mso20Win32Client!__imp_?isStartNameChar@XmlCharacter@@SAH_W@Z` at `0x18012e7bd`
- `Mso20Win32Client!__imp_?isStartNameChar@XmlCharacter@@SAH_W@Z` at `0x18012e7bd`
- `Mso20Win32Client!__imp_?isNameChar@XmlCharacter@@SAH_W@Z` at `0x18012e7ec`
- `Mso20Win32Client!__imp_?isNameChar@XmlCharacter@@SAH_W@Z` at `0x18012e7ec`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012e9ac`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012ea0c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012ea67`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012ebcd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012e9ac`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012ea0c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012ea67`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012ebcd`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012e9a2`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012ea05`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012ea60`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012ebc6`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012e9a2`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012ea05`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012ea60`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012ebc6`

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
  std::wstring::_Construct<1,wchar_t *>(Src, L"//*[@id=\"", 9);
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
    JUMPOUT(0x18012ED3DLL);
  }
  *(_OWORD *)v48 = 0;
  v49 = 0;
  do
    ++v19;
  while ( bstrString[v19] );
  std::wstring::_Construct<1,wchar_t *>(v48, bstrString, v19);
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
0x18012e73c  mov     [rsp-8+arg_10], rbx
0x18012e741  push    rbp
0x18012e742  push    rsi
0x18012e743  push    rdi
0x18012e744  push    r12
0x18012e746  push    r13
0x18012e748  push    r14
0x18012e74a  push    r15
0x18012e74c  lea     rbp, [rsp-27h]
0x18012e751  sub     rsp, 0C0h
0x18012e758  mov     rax, cs:__security_cookie
0x18012e75f  xor     rax, rsp
0x18012e762  mov     [rbp+57h+var_38], rax
0x18012e766  mov     rdi, rdx
0x18012e769  mov     r14, rcx
0x18012e76c  xor     r12d, r12d
0x18012e76f  mov     [rbp+57h+var_A8], r12
0x18012e773  mov     rcx, [rcx+1B8h]
0x18012e77a  test    rcx, rcx
0x18012e77d  jz      loc_18012ECA5
0x18012e783  mov     rax, [rcx]
0x18012e786  lea     rdx, [rbp+57h+var_A8]
0x18012e78a  mov     rax, [rax+98h]
0x18012e791  call    cs:__guard_dispatch_icall_fptr
0x18012e797  test    eax, eax
0x18012e799  js      loc_18012ECB3
0x18012e79f  cmp     [rdi+10h], r12
0x18012e7a3  jz      loc_18012EC97
0x18012e7a9  mov     rcx, rdi
0x18012e7ac  lea     r13d, [r12+7]
0x18012e7b1  cmp     [rdi+18h], r13
0x18012e7b5  jbe     short loc_18012E7BA
0x18012e7b7  mov     rcx, [rdi]
0x18012e7ba  movzx   ecx, word ptr [rcx]
0x18012e7bd  call    cs:__imp_?isStartNameChar@XmlCharacter@@SAH_W@Z; XmlCharacter::isStartNameChar(wchar_t)
0x18012e7c3  test    eax, eax
0x18012e7c5  jz      loc_18012EC97
0x18012e7cb  mov     rcx, rdi
0x18012e7ce  cmp     [rdi+18h], r13
0x18012e7d2  jbe     short loc_18012E7D7
0x18012e7d4  mov     rcx, [rdi]
0x18012e7d7  mov     rax, [rdi+10h]
0x18012e7db  lea     rsi, [rcx+rax*2]
0x18012e7df  mov     rbx, rdi
0x18012e7e2  jbe     short loc_18012E7FA
0x18012e7e4  mov     rbx, [rdi]
0x18012e7e7  jmp     short loc_18012E7FA
0x18012e7e9  movzx   ecx, word ptr [rbx]
0x18012e7ec  call    cs:__imp_?isNameChar@XmlCharacter@@SAH_W@Z; XmlCharacter::isNameChar(wchar_t)
0x18012e7f2  test    eax, eax
0x18012e7f4  jz      loc_18012EC97
0x18012e7fa  add     rbx, 2
0x18012e7fe  cmp     rbx, rsi
0x18012e801  jnz     short loc_18012E7E9
0x18012e803  mov     [rbp+57h+var_B0], r12
0x18012e807  xorps   xmm0, xmm0
0x18012e80a  movups  xmmword ptr [rbp+57h+Src], xmm0
0x18012e80e  xorps   xmm1, xmm1
0x18012e811  movdqu  [rbp+57h+var_88], xmm1
0x18012e816  mov     r8d, 9
0x18012e81c  lea     rdx, aId_0; "//*[@id=\""
0x18012e823  lea     rcx, [rbp+57h+Src]
0x18012e827  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x18012e82c  mov     rsi, [rdi+10h]
0x18012e830  cmp     [rdi+18h], r13
0x18012e834  jbe     short loc_18012E839
0x18012e836  mov     rdi, [rdi]
0x18012e839  mov     r15, qword ptr [rbp+57h+var_88]
0x18012e83d  mov     rax, qword ptr [rbp+57h+var_88+8]
0x18012e841  sub     rax, r15
0x18012e844  cmp     rsi, rax
0x18012e847  ja      short loc_18012E87D
0x18012e849  lea     rax, [rsi+r15]
0x18012e84d  mov     qword ptr [rbp+57h+var_88], rax
0x18012e851  lea     rbx, [rbp+57h+Src]
0x18012e855  cmp     qword ptr [rbp+57h+var_88+8], r13
0x18012e859  cmova   rbx, [rbp+57h+Src]
0x18012e85e  lea     rcx, [rbx+r15*2]; void *
0x18012e862  lea     r8, [rsi+rsi]; Size
0x18012e866  mov     rdx, rdi; Src
0x18012e869  call    memmove_0
0x18012e86e  lea     rax, [rsi+r15]
0x18012e872  mov     [rbx+rax*2], r12w
0x18012e877  lea     rax, [rbp+57h+Src]
0x18012e87b  jmp     short loc_18012E891
0x18012e87d  mov     [rsp+0F0h+Reserved], rsi; __int64
0x18012e882  mov     r9, rdi
0x18012e885  mov     rdx, rsi
0x18012e888  lea     rcx, [rbp+57h+Src]; Src
0x18012e88c  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV34@QEB_W_K@Z@PEB_W_K@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@QEB_W0@Z@PEB_W_K@Z; std::wstring::_Reallocate_grow_by<`std::wstring::append(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *,unsigned __int64>(unsigned __int64,`std::wstring::append(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *,unsigned __int64)
0x18012e891  xorps   xmm0, xmm0
0x18012e894  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x18012e898  xorps   xmm1, xmm1
0x18012e89b  movdqu  [rbp+57h+var_68], xmm1
0x18012e8a0  movups  xmm0, xmmword ptr [rax]
0x18012e8a3  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x18012e8a7  movups  xmm1, xmmword ptr [rax+10h]
0x18012e8ab  movups  [rbp+57h+var_68], xmm1
0x18012e8af  mov     [rax+18h], r13
0x18012e8b3  mov     [rax], r12w
0x18012e8b7  mov     [rax+10h], r12
0x18012e8bb  lea     rdx, asc_180155604; "\"]"
0x18012e8c2  lea     rcx, [rbp+57h+var_78]; Src
0x18012e8c6  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x18012e8cb  xorps   xmm0, xmm0
0x18012e8ce  movups  xmmword ptr [rbp+57h+Block], xmm0
0x18012e8d2  xorps   xmm1, xmm1
0x18012e8d5  movdqu  [rbp+57h+var_48], xmm1
0x18012e8da  movups  xmm0, xmmword ptr [rax]
0x18012e8dd  movups  xmmword ptr [rbp+57h+Block], xmm0
0x18012e8e1  movups  xmm1, xmmword ptr [rax+10h]
0x18012e8e5  movups  [rbp+57h+var_48], xmm1
0x18012e8e9  mov     [rax], r12w
0x18012e8ed  mov     [rax+10h], r12
0x18012e8f1  mov     [rax+18h], r13
0x18012e8f5  lea     rcx, [rbp+57h+Block]
0x18012e8f9  mov     r8, [rbp+57h+Block]
0x18012e8fd  mov     r9, qword ptr [rbp+57h+var_48+8]
0x18012e901  cmp     r9, r13
0x18012e904  cmova   rcx, r8
0x18012e908  mov     rbx, r12
0x18012e90b  mov     [rbp+57h+var_A0], rbx
0x18012e90f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18012e913  test    rcx, rcx
0x18012e916  jz      short loc_18012E927
0x18012e918  mov     rdx, rdi
0x18012e91b  inc     rdx
0x18012e91e  cmp     [rcx+rdx*2], r12w
0x18012e923  jnz     short loc_18012E91B
0x18012e925  jmp     short loc_18012E92D
0x18012e927  mov     rcx, r12; strIn
0x18012e92a  mov     rdx, r12; ui
0x18012e92d  test    rcx, rcx
0x18012e930  jz      short loc_18012E95D
0x18012e932  mov     eax, 0FFFFFFFFh
0x18012e937  cmp     rdx, rax
0x18012e93a  ja      loc_18012ECC5
0x18012e940  call    cs:__imp_SysAllocStringLen
0x18012e946  mov     rbx, rax
0x18012e949  mov     [rbp+57h+var_A0], rax
0x18012e94d  test    rax, rax
0x18012e950  setnz   al
0x18012e953  mov     r9, qword ptr [rbp+57h+var_48+8]
0x18012e957  mov     r8, [rbp+57h+Block]
0x18012e95b  jmp     short loc_18012E95F
0x18012e95d  mov     al, 1
0x18012e95f  test    al, al
0x18012e961  jz      loc_18012ECCB
0x18012e967  mov     r15d, 1000h
0x18012e96d  cmp     r9, r13
0x18012e970  jbe     short loc_18012E9B2
0x18012e972  mov     rcx, r8
0x18012e975  lea     rax, ds:2[r9*2]
0x18012e97d  cmp     rax, r15
0x18012e980  jb      short loc_18012E9A9
0x18012e982  mov     r8, [r8-8]
0x18012e986  sub     rcx, r8
0x18012e989  lea     rax, [rcx-8]
0x18012e98d  cmp     rax, 1Fh
0x18012e991  jbe     short loc_18012E9A9
0x18012e993  mov     [rsp+0F0h+Reserved], r12; Reserved
0x18012e998  xor     r9d, r9d; LineNo
0x18012e99b  xor     r8d, r8d; FileName
0x18012e99e  xor     edx, edx; FunctionName
0x18012e9a0  xor     ecx, ecx; Expression
0x18012e9a2  call    cs:__imp__invoke_watson
0x18012e9a9  mov     rcx, r8; Block
0x18012e9ac  call    cs:__imp_free
0x18012e9b2  mov     esi, 4DE1h
0x18012e9b7  mov     [rbp+57h+Block], rsi
0x18012e9bb  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x18012e9c3  movdqu  [rbp+57h+var_48], xmm0
0x18012e9c8  mov     rax, qword ptr [rbp+57h+var_68+8]
0x18012e9cc  cmp     rax, r13
0x18012e9cf  jbe     short loc_18012EA1A
0x18012e9d1  mov     rcx, [rbp+57h+var_78]; Block
0x18012e9d5  mov     rdx, rcx
0x18012e9d8  lea     rax, ds:2[rax*2]
0x18012e9e0  cmp     rax, r15
0x18012e9e3  jb      short loc_18012EA0C
0x18012e9e5  mov     rcx, [rcx-8]
0x18012e9e9  sub     rdx, rcx
0x18012e9ec  lea     rax, [rdx-8]
0x18012e9f0  cmp     rax, 1Fh
0x18012e9f4  jbe     short loc_18012EA0C
0x18012e9f6  mov     [rsp+0F0h+Reserved], r12; Reserved
0x18012e9fb  xor     r9d, r9d; LineNo
0x18012e9fe  xor     r8d, r8d; FileName
0x18012ea01  xor     edx, edx; FunctionName
0x18012ea03  xor     ecx, ecx; Expression
0x18012ea05  call    cs:__imp__invoke_watson
0x18012ea0c  call    cs:__imp_free
0x18012ea12  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x18012ea1a  mov     [rbp+57h+var_78], rsi
0x18012ea1e  movdqu  [rbp+57h+var_68], xmm0
0x18012ea23  mov     rax, qword ptr [rbp+57h+var_88+8]
0x18012ea27  cmp     rax, r13
0x18012ea2a  jbe     short loc_18012EA75
0x18012ea2c  mov     rcx, [rbp+57h+Src]; Block
0x18012ea30  mov     rdx, rcx
0x18012ea33  lea     rax, ds:2[rax*2]
0x18012ea3b  cmp     rax, r15
0x18012ea3e  jb      short loc_18012EA67
0x18012ea40  mov     rcx, [rcx-8]
0x18012ea44  sub     rdx, rcx
0x18012ea47  lea     rax, [rdx-8]
0x18012ea4b  cmp     rax, 1Fh
0x18012ea4f  jbe     short loc_18012EA67
0x18012ea51  mov     [rsp+0F0h+Reserved], r12; Reserved
0x18012ea56  xor     r9d, r9d; LineNo
0x18012ea59  xor     r8d, r8d; FileName
0x18012ea5c  xor     edx, edx; FunctionName
0x18012ea5e  xor     ecx, ecx; Expression
0x18012ea60  call    cs:__imp__invoke_watson
0x18012ea67  call    cs:__imp_free
0x18012ea6d  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x18012ea75  mov     [rbp+57h+Src], rsi
0x18012ea79  movdqu  [rbp+57h+var_88], xmm0
0x18012ea7e  mov     rcx, [rbp+57h+var_A8]
0x18012ea82  test    rcx, rcx
0x18012ea85  jz      loc_18012ECD7
0x18012ea8b  mov     rax, [rcx]
0x18012ea8e  mov     rax, [rax+70h]
0x18012ea92  call    cs:__guard_dispatch_icall_fptr
0x18012ea98  mov     r9, rax
0x18012ea9b  mov     rcx, [rax]
0x18012ea9e  mov     rax, [rcx+0D8h]
0x18012eaa5  lea     r8, [rbp+57h+var_B0]
0x18012eaa9  mov     rdx, rbx
0x18012eaac  mov     rcx, r9
0x18012eaaf  call    cs:__guard_dispatch_icall_fptr
0x18012eab5  test    eax, eax
0x18012eab7  js      loc_18012ECE5
0x18012eabd  cmp     eax, 1
0x18012eac0  jz      loc_18012ECF2
0x18012eac6  mov     [rbp+57h+bstrString], r12
0x18012eaca  mov     rcx, [rbp+57h+var_B0]
0x18012eace  test    rcx, rcx
0x18012ead1  jz      loc_18012ED01
0x18012ead7  mov     rax, [rcx]
0x18012eada  lea     rdx, [rbp+57h+bstrString]
0x18012eade  mov     rax, [rax+0A8h]
0x18012eae5  call    cs:__guard_dispatch_icall_fptr
0x18012eaeb  test    eax, eax
0x18012eaed  js      loc_18012ED0F
0x18012eaf3  xorps   xmm0, xmm0
0x18012eaf6  movups  xmmword ptr [rbp+57h+Src], xmm0
0x18012eafa  xor     edx, edx
0x18012eafc  mov     ecx, 208h
0x18012eb01  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x18012eb07  mov     [rbp+57h+Src], rax
0x18012eb0b  test    rax, rax
0x18012eb0e  jz      loc_18012ED1F
0x18012eb14  mov     r8b, [rbp+57h+var_C0]
0x18012eb18  mov     rdx, r14
0x18012eb1b  mov     rcx, rax
0x18012eb1e  call    ??0TSpanContext@SVG@Mso@@QEAA@AEAVStylableContext@12@Uinit_default_style_t@12@@Z; Mso::SVG::TSpanContext::TSpanContext(Mso::SVG::StylableContext &,Mso::SVG::init_default_style_t)
0x18012eb23  mov     rcx, [r14+1B0h]
0x18012eb2a  mov     [r14+1B0h], rax
0x18012eb31  test    rcx, rcx
0x18012eb34  jz      short loc_18012EB44
0x18012eb36  mov     rax, [rcx]
0x18012eb39  mov     rax, [rax+8]
0x18012eb3d  call    cs:__guard_dispatch_icall_fptr
0x18012eb43  nop
0x18012eb44  mov     rsi, [r14+1B0h]
0x18012eb4b  test    rsi, rsi
0x18012eb4e  jz      loc_18012ED30
0x18012eb54  xorps   xmm0, xmm0
0x18012eb57  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x18012eb5b  xorps   xmm1, xmm1
0x18012eb5e  movdqu  [rbp+57h+var_68], xmm1
0x18012eb63  mov     rdx, [rbp+57h+bstrString]
0x18012eb67  inc     rdi
0x18012eb6a  cmp     [rdx+rdi*2], r12w
0x18012eb6f  jnz     short loc_18012EB67
0x18012eb71  mov     r8, rdi
0x18012eb74  lea     rcx, [rbp+57h+var_78]
0x18012eb78  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x18012eb7d  lea     rdx, [rbp+57h+var_78]
0x18012eb81  mov     rcx, rsi
0x18012eb84  call    ??$set_text@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@TSpanContext@SVG@Mso@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::SVG::TSpanContext::set_text<std::wstring>(std::wstring &&)
0x18012eb89  mov     rax, qword ptr [rbp+57h+var_68+8]
0x18012eb8d  cmp     rax, r13
0x18012eb90  jbe     short loc_18012EBD4
0x18012eb92  mov     rcx, [rbp+57h+var_78]; Block
0x18012eb96  mov     rdx, rcx
0x18012eb99  lea     rax, ds:2[rax*2]
0x18012eba1  cmp     rax, r15
0x18012eba4  jb      short loc_18012EBCD
0x18012eba6  mov     rcx, [rcx-8]
0x18012ebaa  sub     rdx, rcx
0x18012ebad  lea     rax, [rdx-8]
0x18012ebb1  cmp     rax, 1Fh
0x18012ebb5  jbe     short loc_18012EBCD
0x18012ebb7  mov     [rsp+0F0h+Reserved], r12; Reserved
0x18012ebbc  xor     r9d, r9d; LineNo
0x18012ebbf  xor     r8d, r8d; FileName
0x18012ebc2  xor     edx, edx; FunctionName
0x18012ebc4  xor     ecx, ecx; Expression
  ... truncated ...
```
