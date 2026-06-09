# WindowsMidiServicesNamingLib::AddGroupNumberToNameIfNeeded(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,uchar)

- ea: `0x1800373f8`
- end: `0x1800376ba`
- name: `?AddGroupNumberToNameIfNeeded@WindowsMidiServicesNamingLib@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@00E@Z`
- size: `706`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, wchar_t *S2@<rdx>, wchar_t *@<r8>, char)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x1800380ac`

## callees

- `0x180004410`
- `0x180005260`
- `0x18000c250`
- `0x18000f304`
- `0x18000f77c`
- `0x1800156e4`
- `0x1800176c0`
- `0x180017c18`
- `0x1800185dc`
- `0x18001f8e0`
- `0x1800204a0`
- `0x180027148`
- `0x1800373f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180037547`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180037547`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void *__fastcall WindowsMidiServicesNamingLib::AddGroupNumberToNameIfNeeded(
        void *Src,
        wchar_t *S2,
        wchar_t *a3,
        const wchar_t *a4,
        unsigned __int8 a5)
{
  const wchar_t *v5; // rbx
  __int64 v9; // rdx
  size_t v10; // r8
  const wchar_t *v11; // rcx
  unsigned __int64 v12; // rax
  __int64 v13; // rdx
  const wchar_t *v14; // rcx
  _QWORD *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // r8
  __int64 v18; // rdx
  _QWORD *v19; // rax
  void **v20; // rcx
  unsigned __int64 v21; // rdi
  unsigned __int64 v22; // r8
  _QWORD *v23; // rax
  __int64 appended; // rbx
  void **v25; // r9
  __int64 v26; // rcx
  __int64 v27; // r14
  _QWORD *v28; // rsi
  void *v29; // rax
  void *Srca[2]; // [rsp+40h] [rbp-91h] BYREF
  __int64 v32[2]; // [rsp+50h] [rbp-81h]
  _QWORD v33[2]; // [rsp+60h] [rbp-71h] BYREF
  unsigned __int64 v34; // [rsp+70h] [rbp-61h]
  unsigned __int64 v35; // [rsp+78h] [rbp-59h]
  _OWORD v36[2]; // [rsp+80h] [rbp-51h] BYREF
  _OWORD v37[2]; // [rsp+A0h] [rbp-31h] BYREF
  _BYTE v38[32]; // [rsp+C0h] [rbp-11h] BYREF

  v5 = a4;
  std::wstring::wstring(v33, a4);
  v9 = *((_QWORD *)S2 + 2);
  if ( *((_QWORD *)S2 + 3) > 7u )
    S2 = *(wchar_t **)S2;
  v10 = *((_QWORD *)v5 + 2);
  v11 = v5;
  v12 = *((_QWORD *)v5 + 3);
  if ( v12 > 7 )
    v11 = *(const wchar_t **)v5;
  if ( v10 != v9 )
  {
LABEL_9:
    v13 = *((_QWORD *)a3 + 2);
    if ( *((_QWORD *)a3 + 3) > 7u )
      a3 = *(wchar_t **)a3;
    v10 = *((_QWORD *)v5 + 2);
    v14 = v5;
    if ( v12 > 7 )
      v14 = *(const wchar_t **)v5;
    if ( v10 != v13 || v10 && wmemcmp(v14, a3, v10) )
      goto LABEL_43;
    goto LABEL_16;
  }
  if ( v10 && wmemcmp(v11, S2, v10) )
  {
    v12 = *((_QWORD *)v5 + 3);
    goto LABEL_9;
  }
LABEL_16:
  if ( a5 )
  {
    v15 = v33;
    if ( v35 > 7 )
      v15 = (_QWORD *)v33[0];
    v16 = std::_Traits_find_last_not_of<std::char_traits<unsigned short>>(v15, v34, v10, L"0123456789", 10);
    v17 = -1;
    if ( v16 != -1 )
    {
      v18 = v16 + 1;
      if ( v16 + 1 <= v34 )
      {
        *(_OWORD *)Srca = 0;
        *(_OWORD *)v32 = 0;
        if ( v34 - v18 != -1 )
          v17 = v34 - v18;
        v19 = v33;
        if ( v35 > 7 )
          v19 = (_QWORD *)v33[0];
        std::wstring::_Construct<1,unsigned short const *>(Srca, (char *)v19 + 2 * v18, v17);
        v20 = Srca;
        if ( v32[1] > 7uLL )
          v20 = (void **)Srca[0];
        if ( (unsigned int)_o__wtoi(v20) == (unsigned __int16)(a5 + 1) )
          goto LABEL_42;
        std::wstring::~wstring(Srca);
      }
    }
    std::to_wstring(Srca, (unsigned int)a5 + 1);
    memset(v36, 0, sizeof(v36));
    v21 = v32[0];
    v22 = *((_QWORD *)v5 + 2);
    if ( v22 >= 30 - v32[0] )
      v22 = 30 - v32[0];
    if ( *((_QWORD *)v5 + 3) > 7u )
      v5 = *(const wchar_t **)v5;
    std::wstring::_Construct<1,unsigned short const *>(v36, v5, v22);
    v23 = (_QWORD *)std::operator+<unsigned short>(v38, v36);
    appended = (__int64)v23;
    v25 = Srca;
    if ( v32[1] > 7uLL )
      v25 = (void **)Srca[0];
    v26 = v23[2];
    if ( v21 > v23[3] - v26 )
    {
      appended = ____Reallocate_grow_by_V_lambda_1___1_____Append_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG_K___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Append_G_01_AEAAAEAV01_QEBG0_Z_PEBG_K_Z(
                   v23,
                   v21);
    }
    else
    {
      v27 = v26 + v21;
      v23[2] = v26 + v21;
      if ( v23[3] <= 7u )
        v28 = v23;
      else
        v28 = (_QWORD *)*v23;
      memmove_0((char *)v28 + 2 * v26, v25, 2 * v21);
      *((_WORD *)v28 + v27) = 0;
    }
    v37[0] = *(_OWORD *)appended;
    v37[1] = *(_OWORD *)(appended + 16);
    *(_WORD *)appended = 0;
    *(_QWORD *)(appended + 16) = 0;
    *(_QWORD *)(appended + 24) = 7;
    std::wstring::operator=(v33, v37);
    std::wstring::~wstring(v37);
    std::wstring::~wstring(v38);
    std::wstring::~wstring(v36);
LABEL_42:
    std::wstring::~wstring(Srca);
  }
LABEL_43:
  v29 = (void *)std::wstring::wstring(v38, v33);
  WindowsMidiServicesInternal::TrimmedWStringCopy(Src, v29);
  std::wstring::~wstring(v33);
  return Src;
}

```

## disassembly

```asm
0x1800373f8  push    rbp
0x1800373fa  push    rbx
0x1800373fb  push    rsi
0x1800373fc  push    rdi
0x1800373fd  push    r14
0x1800373ff  push    r15
0x180037401  lea     rbp, [rsp-27h]
0x180037406  sub     rsp, 0F8h
0x18003740d  mov     rax, cs:__security_cookie
0x180037414  xor     rax, rsp
0x180037417  mov     [rbp+4Fh+var_40], rax
0x18003741b  mov     rbx, r9
0x18003741e  mov     rdi, r8
0x180037421  mov     rsi, rdx
0x180037424  mov     r15, rcx
0x180037427  mov     [rsp+120h+var_E8], rcx
0x18003742c  mov     rdx, r9
0x18003742f  lea     rcx, [rbp+4Fh+var_C0]
0x180037433  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180037438  nop
0x180037439  mov     rdx, [rsi+10h]
0x18003743d  cmp     qword ptr [rsi+18h], 7
0x180037442  jbe     short loc_180037447
0x180037444  mov     rsi, [rsi]
0x180037447  mov     r8, [rbx+10h]; N
0x18003744b  mov     rcx, rbx
0x18003744e  mov     rax, [rbx+18h]
0x180037452  cmp     rax, 7
0x180037456  jbe     short loc_18003745B
0x180037458  mov     rcx, [rbx]; S1
0x18003745b  cmp     r8, rdx
0x18003745e  jnz     short loc_180037475
0x180037460  test    r8, r8
0x180037463  jz      short loc_1800374B1
0x180037465  mov     rdx, rsi; S2
0x180037468  call    wmemcmp
0x18003746d  test    eax, eax
0x18003746f  jz      short loc_1800374B1
0x180037471  mov     rax, [rbx+18h]
0x180037475  mov     rdx, [rdi+10h]
0x180037479  cmp     qword ptr [rdi+18h], 7
0x18003747e  jbe     short loc_180037483
0x180037480  mov     rdi, [rdi]
0x180037483  mov     r8, [rbx+10h]; N
0x180037487  mov     rcx, rbx
0x18003748a  cmp     rax, 7
0x18003748e  jbe     short loc_180037493
0x180037490  mov     rcx, [rbx]; S1
0x180037493  cmp     r8, rdx
0x180037496  jnz     loc_180037679
0x18003749c  test    r8, r8
0x18003749f  jz      short loc_1800374B1
0x1800374a1  mov     rdx, rdi; S2
0x1800374a4  call    wmemcmp
0x1800374a9  test    eax, eax
0x1800374ab  jnz     loc_180037679
0x1800374b1  movzx   edi, [rbp+4Fh+arg_20]
0x1800374b5  test    dil, dil
0x1800374b8  jz      loc_180037679
0x1800374be  lea     rcx, [rbp+4Fh+var_C0]
0x1800374c2  cmp     [rbp+4Fh+var_A8], 7
0x1800374c7  cmova   rcx, [rbp+4Fh+var_C0]
0x1800374cc  mov     [rsp+120h+var_100], 0Ah
0x1800374d5  lea     r9, a0123456789; "0123456789"
0x1800374dc  mov     rdx, [rbp+4Fh+var_B0]
0x1800374e0  call    ??$_Traits_find_last_not_of@U?$char_traits@G@std@@@std@@YA_KQEBG_K101@Z; std::_Traits_find_last_not_of<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x1800374e5  mov     esi, 1
0x1800374ea  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800374ee  cmp     rax, r8
0x1800374f1  jz      short loc_180037565
0x1800374f3  mov     rcx, [rbp+4Fh+var_B0]
0x1800374f7  lea     rdx, [rax+1]
0x1800374fb  cmp     rdx, rcx
0x1800374fe  ja      short loc_180037565
0x180037500  xorps   xmm0, xmm0
0x180037503  movups  xmmword ptr [rsp+120h+Src], xmm0
0x180037508  xorps   xmm1, xmm1
0x18003750b  movdqu  xmmword ptr [rsp+120h+var_D0], xmm1
0x180037511  sub     rcx, rdx
0x180037514  cmp     rcx, r8
0x180037517  cmovb   r8, rcx
0x18003751b  lea     rax, [rbp+4Fh+var_C0]
0x18003751f  cmp     [rbp+4Fh+var_A8], 7
0x180037524  cmova   rax, [rbp+4Fh+var_C0]
0x180037529  lea     rdx, [rax+rdx*2]
0x18003752d  lea     rcx, [rsp+120h+Src]
0x180037532  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180037537  lea     rcx, [rsp+120h+Src]
0x18003753c  cmp     [rbp+4Fh+var_D0+8], 7
0x180037541  cmova   rcx, [rsp+120h+Src]
0x180037547  call    cs:__imp__o__wtoi
0x18003754d  lea     ecx, [rsi+rdi]
0x180037550  movzx   ecx, cx
0x180037553  cmp     eax, ecx
0x180037555  lea     rcx, [rsp+120h+Src]; void *
0x18003755a  jz      loc_180037674
0x180037560  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180037565  lea     edx, [rsi+rdi]
0x180037568  lea     rcx, [rsp+120h+Src]
0x18003756d  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::to_wstring(int)
0x180037572  nop
0x180037573  xorps   xmm0, xmm0
0x180037576  movups  [rbp+4Fh+var_A0], xmm0
0x18003757a  xorps   xmm1, xmm1
0x18003757d  movdqu  [rbp+4Fh+var_90], xmm1
0x180037582  mov     rdi, [rsp+120h+var_D0]
0x180037587  mov     r8, [rbx+10h]
0x18003758b  mov     eax, 1Eh
0x180037590  sub     rax, rdi
0x180037593  cmp     r8, rax
0x180037596  cmovnb  r8, rax
0x18003759a  cmp     qword ptr [rbx+18h], 7
0x18003759f  jbe     short loc_1800375A4
0x1800375a1  mov     rbx, [rbx]
0x1800375a4  mov     rdx, rbx
0x1800375a7  lea     rcx, [rbp+4Fh+var_A0]
0x1800375ab  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800375b0  nop
0x1800375b1  lea     rdx, [rbp+4Fh+var_A0]
0x1800375b5  lea     rcx, [rbp+4Fh+var_60]
0x1800375b9  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800375be  mov     rbx, rax
0x1800375c1  lea     r9, [rsp+120h+Src]
0x1800375c6  cmp     [rbp+4Fh+var_D0+8], 7
0x1800375cb  cmova   r9, [rsp+120h+Src]
0x1800375d1  mov     rcx, [rax+10h]
0x1800375d5  mov     rax, [rax+18h]
0x1800375d9  sub     rax, rcx
0x1800375dc  cmp     rdi, rax
0x1800375df  ja      short loc_180037611
0x1800375e1  lea     r14, [rcx+rdi]
0x1800375e5  mov     [rbx+10h], r14
0x1800375e9  cmp     qword ptr [rbx+18h], 7
0x1800375ee  jbe     short loc_1800375F5
0x1800375f0  mov     rsi, [rbx]
0x1800375f3  jmp     short loc_1800375F8
0x1800375f5  mov     rsi, rbx
0x1800375f8  lea     r8, [rdi+rdi]; Size
0x1800375fc  lea     rcx, [rsi+rcx*2]; void *
0x180037600  mov     rdx, r9; Src
0x180037603  call    memmove_0
0x180037608  xor     eax, eax
0x18003760a  mov     [rsi+r14*2], ax
0x18003760f  jmp     short loc_180037624
0x180037611  mov     [rsp+120h+var_100], rdi; __int64
0x180037616  mov     rdx, rdi
0x180037619  mov     rcx, rbx; Src
0x18003761c  call    ??$_Reallocate_grow_by@V_lambda_1_@?1???$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Append@G@01@AEAAAEAV01@QEBG0@Z@PEBG_K@Z; std::wstring::_Reallocate_grow_by<`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64>(unsigned __int64,`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64)
0x180037621  mov     rbx, rax
0x180037624  movups  xmm0, xmmword ptr [rbx]
0x180037627  movups  [rbp+4Fh+var_80], xmm0
0x18003762b  movups  xmm1, xmmword ptr [rbx+10h]
0x18003762f  movups  [rbp+4Fh+var_70], xmm1
0x180037633  xor     ecx, ecx
0x180037635  mov     [rbx], cx
0x180037638  mov     [rbx+10h], rcx
0x18003763c  mov     qword ptr [rbx+18h], 7
0x180037644  lea     rdx, [rbp+4Fh+var_80]
0x180037648  lea     rcx, [rbp+4Fh+var_C0]
0x18003764c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180037651  lea     rcx, [rbp+4Fh+var_80]; void *
0x180037655  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003765a  nop
0x18003765b  lea     rcx, [rbp+4Fh+var_60]; void *
0x18003765f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180037664  nop
0x180037665  lea     rcx, [rbp+4Fh+var_A0]; void *
0x180037669  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003766e  nop
0x18003766f  lea     rcx, [rsp+120h+Src]; void *
0x180037674  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180037679  lea     rdx, [rbp+4Fh+var_C0]
0x18003767d  lea     rcx, [rbp+4Fh+var_60]
0x180037681  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180037686  mov     rdx, rax; void *
0x180037689  mov     rcx, r15; Src
0x18003768c  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x180037691  nop
0x180037692  lea     rcx, [rbp+4Fh+var_C0]; void *
0x180037696  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003769b  mov     rax, r15
0x18003769e  mov     rcx, [rbp+4Fh+var_40]
0x1800376a2  xor     rcx, rsp; StackCookie
0x1800376a5  call    __security_check_cookie
0x1800376aa  add     rsp, 0F8h
0x1800376b1  pop     r15
0x1800376b3  pop     r14
0x1800376b5  pop     rdi
0x1800376b6  pop     rsi
0x1800376b7  pop     rbx
0x1800376b8  pop     rbp
0x1800376b9  retn
```
