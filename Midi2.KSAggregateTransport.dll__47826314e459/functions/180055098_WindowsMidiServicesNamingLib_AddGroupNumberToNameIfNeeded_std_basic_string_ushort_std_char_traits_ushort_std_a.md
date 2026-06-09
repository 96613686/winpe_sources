# WindowsMidiServicesNamingLib::AddGroupNumberToNameIfNeeded(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,uchar)

- ea: `0x180055098`
- end: `0x1800553ad`
- name: `?AddGroupNumberToNameIfNeeded@WindowsMidiServicesNamingLib@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@00E@Z`
- size: `789`
- prototype: `__int64 __fastcall(void *Src, wchar_t *S2, wchar_t *, wchar_t *S1, char)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x180055d40`

## callees

- `0x180005020`
- `0x180005e90`
- `0x18000d430`
- `0x180013118`
- `0x180013638`
- `0x180014194`
- `0x18001a844`
- `0x18001a96c`
- `0x18001aa6c`
- `0x18001b258`
- `0x18001f870`
- `0x180043908`
- `0x180055098`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800551f3`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800551f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void *__fastcall WindowsMidiServicesNamingLib::AddGroupNumberToNameIfNeeded(
        void *Src,
        wchar_t *S2,
        wchar_t *a3,
        wchar_t *S1,
        unsigned __int8 a5)
{
  __int64 v9; // rdx
  size_t v10; // r8
  const wchar_t *v11; // rcx
  unsigned __int64 v12; // rax
  __int64 v13; // rdx
  const wchar_t *v14; // rcx
  _QWORD *v15; // rcx
  __int64 v16; // rax
  void **v17; // rcx
  _WORD *v18; // r9
  unsigned int v19; // r8d
  unsigned __int64 v20; // rdi
  _QWORD *v21; // rax
  __int64 appended; // rbx
  void **v23; // r9
  __int64 v24; // rcx
  __int64 v25; // r14
  _QWORD *v26; // rsi
  void *v27; // rax
  void *Srca[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v30[2]; // [rsp+50h] [rbp-B0h]
  _QWORD v31[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v32; // [rsp+70h] [rbp-90h]
  unsigned __int64 v33; // [rsp+78h] [rbp-88h]
  _OWORD v34[2]; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v35[2]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v36[42]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v37[6]; // [rsp+EAh] [rbp-16h] BYREF

  std::wstring::wstring(v31, S1);
  v9 = *((_QWORD *)S2 + 2);
  if ( *((_QWORD *)S2 + 3) > 7u )
    S2 = *(wchar_t **)S2;
  v10 = *((_QWORD *)S1 + 2);
  v11 = S1;
  v12 = *((_QWORD *)S1 + 3);
  if ( v12 > 7 )
    v11 = *(const wchar_t **)S1;
  if ( v10 != v9 )
  {
LABEL_9:
    v13 = *((_QWORD *)a3 + 2);
    if ( *((_QWORD *)a3 + 3) > 7u )
      a3 = *(wchar_t **)a3;
    v10 = *((_QWORD *)S1 + 2);
    if ( v12 <= 7 )
      v14 = S1;
    else
      v14 = *(const wchar_t **)S1;
    if ( v10 != v13 || v10 && wmemcmp(v14, a3, v10) )
      goto LABEL_38;
    goto LABEL_17;
  }
  if ( v10 && wmemcmp(v11, S2, v10) )
  {
    v12 = *((_QWORD *)S1 + 3);
    goto LABEL_9;
  }
LABEL_17:
  if ( a5 )
  {
    v15 = v31;
    if ( v33 > 7 )
      v15 = (_QWORD *)v31[0];
    v16 = std::_Traits_find_last_not_of<std::char_traits<unsigned short>>(v15, v32, v10, L"0123456789", 10);
    if ( v16 != -1 && v16 + 1 <= v32 )
    {
      *(_OWORD *)Srca = 0;
      *(_OWORD *)v30 = 0;
      std::wstring::_Construct<1,unsigned short const *>(Srca);
      v17 = Srca;
      if ( v30[1] > 7uLL )
        v17 = (void **)Srca[0];
      if ( (unsigned int)_o__wtoi(v17) == (unsigned __int16)(a5 + 1) )
        goto LABEL_37;
      std::wstring::~wstring(Srca);
    }
    v18 = v37;
    v19 = a5 + 1;
    do
    {
      *--v18 = v19 % 0xA + 48;
      v19 /= 0xAu;
    }
    while ( v19 );
    std::wstring::wstring(Srca, v18, v37);
    memset(v34, 0, sizeof(v34));
    v20 = v30[0];
    std::wstring::_Construct<1,unsigned short const *>(v34);
    v21 = (_QWORD *)std::operator+<unsigned short>(v36, v34, L" ");
    appended = (__int64)v21;
    v23 = Srca;
    if ( v30[1] > 7uLL )
      v23 = (void **)Srca[0];
    v24 = v21[2];
    if ( v20 > v21[3] - v24 )
    {
      appended = ____Reallocate_grow_by_V_lambda_1___1_____Append_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG_K___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Append_G_01_AEAAAEAV01_QEBG0_Z_PEBG_K_Z(
                   v21,
                   v20);
    }
    else
    {
      v25 = v20 + v24;
      v21[2] = v20 + v24;
      if ( v21[3] <= 7u )
        v26 = v21;
      else
        v26 = (_QWORD *)*v21;
      memmove_0((char *)v26 + 2 * v24, v23, 2 * v20);
      *((_WORD *)v26 + v25) = 0;
    }
    v35[0] = *(_OWORD *)appended;
    v35[1] = *(_OWORD *)(appended + 16);
    *(_WORD *)appended = 0;
    *(_QWORD *)(appended + 16) = 0;
    *(_QWORD *)(appended + 24) = 7;
    std::wstring::operator=(v31, v35);
    std::wstring::~wstring(v35);
    std::wstring::~wstring(v36);
    std::wstring::~wstring(v34);
LABEL_37:
    std::wstring::~wstring(Srca);
  }
LABEL_38:
  v27 = (void *)std::wstring::wstring(v36, v31);
  WindowsMidiServicesInternal::TrimmedWStringCopy(Src, v27);
  std::wstring::~wstring(v31);
  return Src;
}

```

## disassembly

```asm
0x180055098  push    rbp
0x18005509a  push    rbx
0x18005509b  push    rsi
0x18005509c  push    rdi
0x18005509d  push    r14
0x18005509f  push    r15
0x1800550a1  lea     rbp, [rsp-8]
0x1800550a6  sub     rsp, 108h
0x1800550ad  mov     rax, cs:__security_cookie
0x1800550b4  xor     rax, rsp
0x1800550b7  mov     [rbp+30h+var_40], rax
0x1800550bb  mov     rbx, r9
0x1800550be  mov     rdi, r8
0x1800550c1  mov     rsi, rdx
0x1800550c4  mov     r15, rcx
0x1800550c7  mov     [rsp+130h+var_F8], rcx
0x1800550cc  mov     rdx, r9
0x1800550cf  lea     rcx, [rsp+130h+var_D0]
0x1800550d4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800550d9  nop
0x1800550da  mov     rdx, [rsi+10h]
0x1800550de  cmp     qword ptr [rsi+18h], 7
0x1800550e3  jbe     short loc_1800550E8
0x1800550e5  mov     rsi, [rsi]
0x1800550e8  mov     r8, [rbx+10h]; N
0x1800550ec  mov     rcx, rbx
0x1800550ef  mov     rax, [rbx+18h]
0x1800550f3  cmp     rax, 7
0x1800550f7  jbe     short loc_1800550FC
0x1800550f9  mov     rcx, [rbx]; S1
0x1800550fc  cmp     r8, rdx
0x1800550ff  jnz     short loc_180055116
0x180055101  test    r8, r8
0x180055104  jz      short loc_180055154
0x180055106  mov     rdx, rsi; S2
0x180055109  call    wmemcmp
0x18005510e  test    eax, eax
0x180055110  jz      short loc_180055154
0x180055112  mov     rax, [rbx+18h]
0x180055116  mov     rdx, [rdi+10h]
0x18005511a  cmp     qword ptr [rdi+18h], 7
0x18005511f  jbe     short loc_180055124
0x180055121  mov     rdi, [rdi]
0x180055124  mov     r8, [rbx+10h]; N
0x180055128  cmp     rax, 7
0x18005512c  jbe     short loc_180055133
0x18005512e  mov     rcx, [rbx]
0x180055131  jmp     short loc_180055136
0x180055133  mov     rcx, rbx; S1
0x180055136  cmp     r8, rdx
0x180055139  jnz     loc_18005536A
0x18005513f  test    r8, r8
0x180055142  jz      short loc_180055154
0x180055144  mov     rdx, rdi; S2
0x180055147  call    wmemcmp
0x18005514c  test    eax, eax
0x18005514e  jnz     loc_18005536A
0x180055154  movzx   edi, [rbp+30h+arg_20]
0x180055158  test    dil, dil
0x18005515b  jz      loc_18005536A
0x180055161  lea     rcx, [rsp+130h+var_D0]
0x180055166  cmp     [rsp+130h+var_B8], 7
0x18005516c  cmova   rcx, [rsp+130h+var_D0]
0x180055172  mov     [rsp+130h+var_110], 0Ah
0x18005517b  lea     r9, a0123456789; "0123456789"
0x180055182  mov     rdx, [rsp+130h+var_C0]
0x180055187  call    ??$_Traits_find_last_not_of@U?$char_traits@G@std@@@std@@YA_KQEBG_K101@Z; std::_Traits_find_last_not_of<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x18005518c  mov     esi, 1
0x180055191  or      r8, 0FFFFFFFFFFFFFFFFh
0x180055195  cmp     rax, r8
0x180055198  jz      short loc_180055211
0x18005519a  mov     rcx, [rsp+130h+var_C0]
0x18005519f  lea     rdx, [rax+1]
0x1800551a3  cmp     rdx, rcx
0x1800551a6  ja      short loc_180055211
0x1800551a8  xorps   xmm0, xmm0
0x1800551ab  movups  xmmword ptr [rsp+130h+Src], xmm0
0x1800551b0  xorps   xmm1, xmm1
0x1800551b3  movdqu  xmmword ptr [rsp+130h+var_E0], xmm1
0x1800551b9  sub     rcx, rdx
0x1800551bc  cmp     rcx, r8
0x1800551bf  cmovb   r8, rcx
0x1800551c3  lea     rax, [rsp+130h+var_D0]
0x1800551c8  cmp     [rsp+130h+var_B8], 7
0x1800551ce  cmova   rax, [rsp+130h+var_D0]
0x1800551d4  lea     rdx, [rax+rdx*2]
0x1800551d8  lea     rcx, [rsp+130h+Src]
0x1800551dd  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800551e2  lea     rcx, [rsp+130h+Src]
0x1800551e7  cmp     [rsp+130h+var_E0+8], 7
0x1800551ed  cmova   rcx, [rsp+130h+Src]
0x1800551f3  call    cs:__imp__o__wtoi
0x1800551f9  lea     ecx, [rsi+rdi]
0x1800551fc  movzx   ecx, cx
0x1800551ff  cmp     eax, ecx
0x180055201  lea     rcx, [rsp+130h+Src]; void *
0x180055206  jz      loc_180055365
0x18005520c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180055211  lea     r9, [rbp+30h+var_46]
0x180055215  lea     r8d, [rsi+rdi]
0x180055219  sub     r9, 2
0x18005521d  mov     eax, 0CCCCCCCDh
0x180055222  mul     r8d
0x180055225  shr     edx, 3
0x180055228  movzx   eax, dx
0x18005522b  shl     ax, 2
0x18005522f  lea     ecx, [rax+rdx]
0x180055232  add     cx, cx
0x180055235  sub     r8w, cx
0x180055239  add     r8w, 30h ; '0'
0x18005523e  mov     [r9], r8w
0x180055242  mov     r8d, edx
0x180055245  test    edx, edx
0x180055247  jnz     short loc_180055219
0x180055249  lea     r8, [rbp+30h+var_46]
0x18005524d  mov     rdx, r9
0x180055250  lea     rcx, [rsp+130h+Src]
0x180055255  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x18005525a  nop
0x18005525b  xorps   xmm0, xmm0
0x18005525e  movups  [rbp+30h+var_B0], xmm0
0x180055262  xorps   xmm1, xmm1
0x180055265  movdqu  [rbp+30h+var_A0], xmm1
0x18005526a  mov     rdi, [rsp+130h+var_E0]
0x18005526f  mov     r8, [rbx+10h]
0x180055273  mov     eax, 1Eh
0x180055278  sub     rax, rdi
0x18005527b  cmp     r8, rax
0x18005527e  cmovnb  r8, rax
0x180055282  cmp     qword ptr [rbx+18h], 7
0x180055287  jbe     short loc_18005528C
0x180055289  mov     rbx, [rbx]
0x18005528c  mov     rdx, rbx
0x18005528f  lea     rcx, [rbp+30h+var_B0]
0x180055293  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180055298  nop
0x180055299  lea     r8, asc_180080F20; " "
0x1800552a0  lea     rdx, [rbp+30h+var_B0]
0x1800552a4  lea     rcx, [rbp+30h+var_70]
0x1800552a8  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800552ad  mov     rbx, rax
0x1800552b0  lea     r9, [rsp+130h+Src]
0x1800552b5  cmp     [rsp+130h+var_E0+8], 7
0x1800552bb  cmova   r9, [rsp+130h+Src]
0x1800552c1  mov     rcx, [rax+10h]
0x1800552c5  mov     rax, [rax+18h]
0x1800552c9  sub     rax, rcx
0x1800552cc  cmp     rdi, rax
0x1800552cf  ja      short loc_180055301
0x1800552d1  lea     r14, [rdi+rcx]
0x1800552d5  mov     [rbx+10h], r14
0x1800552d9  cmp     qword ptr [rbx+18h], 7
0x1800552de  jbe     short loc_1800552E5
0x1800552e0  mov     rsi, [rbx]
0x1800552e3  jmp     short loc_1800552E8
0x1800552e5  mov     rsi, rbx
0x1800552e8  lea     r8, [rdi+rdi]; Size
0x1800552ec  lea     rcx, [rsi+rcx*2]; void *
0x1800552f0  mov     rdx, r9; Src
0x1800552f3  call    memmove_0
0x1800552f8  xor     eax, eax
0x1800552fa  mov     [rsi+r14*2], ax
0x1800552ff  jmp     short loc_180055314
0x180055301  mov     [rsp+130h+var_110], rdi; __int64
0x180055306  mov     rdx, rdi
0x180055309  mov     rcx, rbx; Src
0x18005530c  call    ??$_Reallocate_grow_by@V_lambda_1_@?1???$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Append@G@01@AEAAAEAV01@QEBG0@Z@PEBG_K@Z; std::wstring::_Reallocate_grow_by<`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64>(unsigned __int64,`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64)
0x180055311  mov     rbx, rax
0x180055314  movups  xmm0, xmmword ptr [rbx]
0x180055317  movups  [rbp+30h+var_90], xmm0
0x18005531b  movups  xmm1, xmmword ptr [rbx+10h]
0x18005531f  movups  [rbp+30h+var_80], xmm1
0x180055323  xor     ecx, ecx
0x180055325  mov     [rbx], cx
0x180055328  mov     [rbx+10h], rcx
0x18005532c  mov     qword ptr [rbx+18h], 7
0x180055334  lea     rdx, [rbp+30h+var_90]
0x180055338  lea     rcx, [rsp+130h+var_D0]
0x18005533d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180055342  lea     rcx, [rbp+30h+var_90]; void *
0x180055346  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005534b  nop
0x18005534c  lea     rcx, [rbp+30h+var_70]; void *
0x180055350  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180055355  nop
0x180055356  lea     rcx, [rbp+30h+var_B0]; void *
0x18005535a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005535f  nop
0x180055360  lea     rcx, [rsp+130h+Src]; void *
0x180055365  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005536a  lea     rdx, [rsp+130h+var_D0]
0x18005536f  lea     rcx, [rbp+30h+var_70]
0x180055373  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180055378  mov     rdx, rax; void *
0x18005537b  mov     rcx, r15; Src
0x18005537e  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x180055383  nop
0x180055384  lea     rcx, [rsp+130h+var_D0]; void *
0x180055389  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005538e  mov     rax, r15
0x180055391  mov     rcx, [rbp+30h+var_40]
0x180055395  xor     rcx, rsp; StackCookie
0x180055398  call    __security_check_cookie
0x18005539d  add     rsp, 108h
0x1800553a4  pop     r15
0x1800553a6  pop     r14
0x1800553a8  pop     rdi
0x1800553a9  pop     rsi
0x1800553aa  pop     rbx
0x1800553ab  pop     rbp
0x1800553ac  retn
```
