# win_musl::ZipFileLocal::operator=(win_musl::ZipFileLocal const &)

- ea: `0x1800243c4`
- end: `0x18002478f`
- name: `??4ZipFileLocal@win_musl@@QEAAAEAV01@AEBV01@@Z`
- size: `971`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x180006214`
- `0x180022648`

## callees

- `0x1800208b0`
- `0x1800243c4`
- `0x180025528`
- `0x180026bcc`
- `0x1800786c0`
- `0x18008429c`
- `0x18008e2bc`
- `0x18008e2fc`
- `0x18009987c`
- `0x1800cce54`
- `0x1800cdb60`
- `0x180111cf0`

## import_xrefs

- `msvcrt!memmove_s` at `0x180024631`
- `msvcrt!memmove_s` at `0x18002467f`
- `msvcrt!memmove_s` at `0x180024631`
- `msvcrt!memmove_s` at `0x18002467f`
- `msvcrt!memcpy_s` at `0x18002442f`
- `msvcrt!memcpy_s` at `0x18002442f`

## pseudocode

```c
__int64 __fastcall win_musl::ZipFileLocal::operator=(__int64 a1, __int64 a2)
{
  __int64 v2; // r14
  rsize_t v4; // rdi
  __int64 v5; // rbx
  _QWORD *v7; // r8
  rsize_t v8; // rdx
  void **v9; // r14
  void *v10; // rcx
  __int64 v11; // r9
  unsigned __int64 v12; // rdx
  rsize_t v13; // rax
  __int64 v14; // r10
  __int64 v15; // rax
  _QWORD *v17; // rax
  void *v18; // rcx
  unsigned __int64 v19; // rax
  __int64 v20; // rcx
  unsigned __int64 v21; // rax
  __int64 v22; // rdx
  const void *v23; // r8
  __int64 v24; // r14
  rsize_t v25; // rdi
  __int64 v26; // rax
  const void *v27; // r14
  __int64 v28; // r15
  rsize_t v29; // rdi
  unsigned __int64 v30; // rax
  unsigned __int64 v31; // rdx
  __int64 v32; // r10
  unsigned __int64 v33; // rax
  unsigned __int64 v34; // rdx
  __int64 v35; // rax
  __int64 v36; // r10
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 v39; // rcx
  void *v40; // rcx
  __int64 v41; // rax

  v2 = a2 + 8;
  v4 = *(_QWORD *)(a2 + 32);
  v5 = a1 + 8;
  if ( a1 + 8 == a2 + 8 )
  {
    std::string::erase(a1 + 8, v4, -1);
    std::string::erase(v5, 0, 0);
    goto LABEL_12;
  }
  if ( v4 == -1 )
    std::_String_base::_Xlen();
  if ( *(_QWORD *)(a1 + 40) < v4 )
  {
    std::string::_Copy(a1 + 8, v4, *(_QWORD *)(a1 + 32));
    if ( !v4 )
      goto LABEL_12;
    goto LABEL_5;
  }
  if ( v4 )
  {
LABEL_5:
    v7 = (_QWORD *)(v2 + 8);
    if ( *(_QWORD *)(v2 + 32) >= 0x10u )
      v7 = (_QWORD *)*v7;
    v8 = *(_QWORD *)(v5 + 32);
    v9 = (void **)(v5 + 8);
    if ( v8 < 0x10 )
      v10 = (void *)(v5 + 8);
    else
      v10 = *v9;
    memcpy_s(v10, v8, v7, v4);
    if ( *(_QWORD *)(v5 + 32) >= 0x10u )
      v9 = (void **)*v9;
    *(_QWORD *)(v5 + 24) = v4;
    *((_BYTE *)v9 + v4) = 0;
    goto LABEL_12;
  }
  v17 = (_QWORD *)(a1 + 16);
  if ( *(_QWORD *)(a1 + 40) >= 0x10u )
    v17 = (_QWORD *)*v17;
  *(_QWORD *)(a1 + 32) = 0;
  *(_BYTE *)v17 = 0;
LABEL_12:
  *(_BYTE *)(a1 + 48) = *(_BYTE *)(a2 + 48);
  if ( a1 + 56 == a2 + 56 )
    goto LABEL_19;
  v11 = *(_QWORD *)(a2 + 64);
  if ( !v11 || (v12 = *(_QWORD *)(a2 + 72) - v11) == 0 )
  {
    v13 = *(_QWORD *)(a1 + 64);
    if ( v13 == *(_QWORD *)(a1 + 72) )
      goto LABEL_19;
LABEL_18:
    *(_QWORD *)(a1 + 72) = v13;
    goto LABEL_19;
  }
  v18 = *(void **)(a1 + 64);
  if ( v18 )
    v19 = *(_QWORD *)(a1 + 72) - (_QWORD)v18;
  else
    v19 = 0;
  if ( v12 > v19 )
  {
    if ( v18 )
      v21 = *(_QWORD *)(a1 + 80) - (_QWORD)v18;
    else
      v21 = 0;
    if ( v12 <= v21 )
    {
      if ( v18 )
        v26 = *(_QWORD *)(a1 + 72) - (_QWORD)v18;
      else
        v26 = 0;
      v27 = (const void *)(v11 + v26);
      std::copy<unsigned char const *,unsigned char *>(*(void **)(a2 + 64));
      v28 = *(_QWORD *)(a1 + 72);
      v29 = *(_QWORD *)(a2 + 72) - (_QWORD)v27;
      if ( v29 )
        memmove_s(*(void *const *)(a1 + 72), v29, v27, v29);
      v13 = v29 + v28;
      goto LABEL_18;
    }
    if ( v18 )
      operator delete(v18);
    if ( *(_QWORD *)(a2 + 64) )
      v22 = *(_QWORD *)(a2 + 72) - *(_QWORD *)(a2 + 64);
    else
      v22 = 0;
    if ( (unsigned __int8)std::vector<unsigned char>::_Buy(a1 + 56, v22) )
    {
      v23 = *(const void **)(a2 + 64);
      v24 = *(_QWORD *)(a1 + 64);
      v25 = *(_QWORD *)(a2 + 72) - (_QWORD)v23;
      if ( v25 )
        memmove_s(*(void *const *)(a1 + 64), v25, v23, v25);
      v13 = v25 + v24;
      goto LABEL_18;
    }
  }
  else
  {
    std::copy<unsigned char const *,unsigned char *>(*(void **)(a2 + 64));
    if ( *(_QWORD *)(a2 + 64) )
      v20 = *(_QWORD *)(a2 + 72) - *(_QWORD *)(a2 + 64);
    else
      v20 = 0;
    *(_QWORD *)(a1 + 72) = *(_QWORD *)(a1 + 64) + v20;
  }
LABEL_19:
  if ( a1 + 88 == a2 + 88 )
    goto LABEL_24;
  v14 = *(_QWORD *)(a2 + 96);
  if ( v14 && 0xAAAAAAAAAAAAAAABuLL * ((*(_QWORD *)(a2 + 104) - v14) >> 3) )
  {
    std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::size(a1 + 88);
    v30 = std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::size(a2 + 88);
    if ( v30 <= v31 )
    {
      std::copy<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *>(
        v32,
        *(_QWORD *)(a2 + 104),
        *(_QWORD *)(a1 + 96));
      *(_QWORD *)(a1 + 104) = *(_QWORD *)(a1 + 96)
                            + 24 * std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::size(a2 + 88);
      goto LABEL_24;
    }
    std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::capacity(a1 + 88, v31);
    v33 = std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::size(a2 + 88);
    if ( v33 > v34 )
    {
      v40 = *(void **)(a1 + 96);
      if ( v40 )
        operator delete(v40);
      v41 = std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::size(a2 + 88);
      if ( !(unsigned __int8)std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::_Buy(a1 + 88, v41) )
        goto LABEL_24;
      v37 = *(_QWORD *)(a1 + 96);
      v39 = *(_QWORD *)(a2 + 96);
    }
    else
    {
      v35 = std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::size(a1 + 88);
      std::copy<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *>(
        v36,
        v36 + 24 * v35,
        *(_QWORD *)(a1 + 96));
      v37 = *(_QWORD *)(a1 + 104);
      v39 = v38;
    }
    v15 = std::_Uninit_copy<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,std::allocator<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>>(
            v39,
            *(_QWORD *)(a2 + 104),
            v37);
    goto LABEL_23;
  }
  v15 = *(_QWORD *)(a1 + 96);
  if ( v15 != *(_QWORD *)(a1 + 104) )
LABEL_23:
    *(_QWORD *)(a1 + 104) = v15;
LABEL_24:
  *(_DWORD *)(a1 + 120) = *(_DWORD *)(a2 + 120);
  *(_OWORD *)(a1 + 128) = *(_OWORD *)(a2 + 128);
  *(_OWORD *)(a1 + 144) = *(_OWORD *)(a2 + 144);
  *(_OWORD *)(a1 + 160) = *(_OWORD *)(a2 + 160);
  *(_OWORD *)(a1 + 176) = *(_OWORD *)(a2 + 176);
  *(_QWORD *)(a1 + 192) = *(_QWORD *)(a2 + 192);
  *(_DWORD *)(a1 + 200) = *(_DWORD *)(a2 + 200);
  *(_BYTE *)(a1 + 204) = *(_BYTE *)(a2 + 204);
  *(_BYTE *)(a1 + 205) = *(_BYTE *)(a2 + 205);
  *(_BYTE *)(a1 + 206) = *(_BYTE *)(a2 + 206);
  return a1;
}

```

## disassembly

```asm
0x1800243c4  push    rbx
0x1800243c6  push    rbp
0x1800243c7  push    rsi
0x1800243c8  push    rdi
0x1800243c9  push    r14
0x1800243cb  push    r15
0x1800243cd  sub     rsp, 38h
0x1800243d1  lea     r14, [rdx+8]
0x1800243d5  mov     rbp, rdx
0x1800243d8  mov     rdi, [r14+18h]
0x1800243dc  lea     rbx, [rcx+8]
0x1800243e0  mov     rsi, rcx
0x1800243e3  cmp     rbx, r14
0x1800243e6  jz      loc_1800246A0
0x1800243ec  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x1800243f0  ja      loc_1800246C1
0x1800243f6  cmp     [rbx+20h], rdi
0x1800243fa  jb      loc_180024559
0x180024400  test    rdi, rdi
0x180024403  jz      loc_18002457E
0x180024409  cmp     qword ptr [r14+20h], 10h
0x18002440e  lea     r8, [r14+8]
0x180024412  jb      short loc_180024417
0x180024414  mov     r8, [r8]; Source
0x180024417  mov     rdx, [rbx+20h]; DestinationSize
0x18002441b  lea     r14, [rbx+8]
0x18002441f  cmp     rdx, 10h
0x180024423  jb      loc_180024576
0x180024429  mov     rcx, [r14]; Destination
0x18002442c  mov     r9, rdi; SourceSize
0x18002442f  call    cs:__imp_memcpy_s
0x180024435  cmp     qword ptr [rbx+20h], 10h
0x18002443a  jb      short loc_18002443F
0x18002443c  mov     r14, [r14]
0x18002443f  mov     [rbx+18h], rdi
0x180024443  mov     byte ptr [rdi+r14], 0
0x180024448  mov     al, [rbp+30h]
0x18002444b  lea     rdi, [rbp+38h]
0x18002444f  lea     rbx, [rsi+38h]
0x180024453  mov     [rsi+30h], al
0x180024456  cmp     rbx, rdi
0x180024459  jz      short loc_180024485
0x18002445b  mov     r9, [rdi+8]
0x18002445f  test    r9, r9
0x180024462  jz      short loc_180024471
0x180024464  mov     rdx, [rdi+10h]
0x180024468  sub     rdx, r9
0x18002446b  jnz     loc_18002459C
0x180024471  mov     rax, [rbx+8]
0x180024475  cmp     rax, [rbx+10h]
0x180024479  jnz     short loc_180024481
0x18002447b  jmp     short loc_180024485
0x18002447d  lea     rax, [rdi+r15]
0x180024481  mov     [rbx+10h], rax
0x180024485  lea     rdi, [rbp+58h]
0x180024489  lea     rbx, [rsi+58h]
0x18002448d  cmp     rbx, rdi
0x180024490  jz      short loc_1800244CB
0x180024492  mov     r10, [rdi+8]
0x180024496  test    r10, r10
0x180024499  jz      short loc_1800244BD
0x18002449b  mov     rax, [rdi+10h]
0x18002449f  mov     rcx, 0AAAAAAAAAAAAAAABh
0x1800244a9  sub     rax, r10
0x1800244ac  sar     rax, 3
0x1800244b0  imul    rax, rcx
0x1800244b4  test    rax, rax
0x1800244b7  jnz     loc_1800246CB
0x1800244bd  mov     rax, [rbx+8]
0x1800244c1  cmp     rax, [rbx+10h]
0x1800244c5  jz      short loc_1800244CB
0x1800244c7  mov     [rbx+10h], rax
0x1800244cb  mov     eax, [rbp+78h]
0x1800244ce  mov     [rsi+78h], eax
0x1800244d1  movups  xmm0, xmmword ptr [rbp+80h]
0x1800244d8  movups  xmmword ptr [rsi+80h], xmm0
0x1800244df  movups  xmm1, xmmword ptr [rbp+90h]
0x1800244e6  movups  xmmword ptr [rsi+90h], xmm1
0x1800244ed  movups  xmm0, xmmword ptr [rbp+0A0h]
0x1800244f4  movups  xmmword ptr [rsi+0A0h], xmm0
0x1800244fb  movups  xmm1, xmmword ptr [rbp+0B0h]
0x180024502  movups  xmmword ptr [rsi+0B0h], xmm1
0x180024509  movsd   xmm0, qword ptr [rbp+0C0h]
0x180024511  movsd   qword ptr [rsi+0C0h], xmm0
0x180024519  mov     eax, [rbp+0C8h]
0x18002451f  mov     [rsi+0C8h], eax
0x180024525  mov     al, [rbp+0CCh]
0x18002452b  mov     [rsi+0CCh], al
0x180024531  mov     al, [rbp+0CDh]
0x180024537  mov     [rsi+0CDh], al
0x18002453d  mov     al, [rbp+0CEh]
0x180024543  mov     [rsi+0CEh], al
0x180024549  mov     rax, rsi
0x18002454c  add     rsp, 38h
0x180024550  pop     r15
0x180024552  pop     r14
0x180024554  pop     rdi
0x180024555  pop     rsi
0x180024556  pop     rbp
0x180024557  pop     rbx
0x180024558  retn
0x180024559  mov     r8, [rbx+18h]
0x18002455d  mov     rdx, rdi
0x180024560  mov     rcx, rbx
0x180024563  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x180024568  test    rdi, rdi
0x18002456b  jz      loc_180024448
0x180024571  jmp     loc_180024409
0x180024576  mov     rcx, r14
0x180024579  jmp     loc_18002442C
0x18002457e  cmp     qword ptr [rbx+20h], 10h
0x180024583  lea     rax, [rbx+8]
0x180024587  jb      short loc_18002458C
0x180024589  mov     rax, [rax]
0x18002458c  mov     qword ptr [rbx+18h], 0
0x180024594  mov     byte ptr [rax], 0
0x180024597  jmp     loc_180024448
0x18002459c  mov     rcx, [rbx+8]; Block
0x1800245a0  test    rcx, rcx
0x1800245a3  jnz     short loc_1800245D1
0x1800245a5  xor     eax, eax
0x1800245a7  cmp     rdx, rax
0x1800245aa  ja      short loc_1800245E4
0x1800245ac  mov     rdx, [rdi+10h]
0x1800245b0  mov     r8, rcx
0x1800245b3  mov     rcx, r9; Source
0x1800245b6  call    ??$copy@PEBEPEAE@std@@YAPEAEPEBE0PEAE@Z; std::copy<uchar const *,uchar *>(uchar const *,uchar const *,uchar *)
0x1800245bb  cmp     qword ptr [rdi+8], 0
0x1800245c0  jnz     short loc_1800245DA
0x1800245c2  xor     ecx, ecx
0x1800245c4  add     rcx, [rbx+8]
0x1800245c8  mov     [rbx+10h], rcx
0x1800245cc  jmp     loc_180024485
0x1800245d1  mov     rax, [rbx+10h]
0x1800245d5  sub     rax, rcx
0x1800245d8  jmp     short loc_1800245A7
0x1800245da  mov     rcx, [rdi+10h]
0x1800245de  sub     rcx, [rdi+8]
0x1800245e2  jmp     short loc_1800245C4
0x1800245e4  test    rcx, rcx
0x1800245e7  jnz     short loc_180024640
0x1800245e9  xor     eax, eax
0x1800245eb  cmp     rdx, rax
0x1800245ee  jbe     short loc_180024649
0x1800245f0  test    rcx, rcx
0x1800245f3  jz      short loc_1800245FA
0x1800245f5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800245fa  cmp     qword ptr [rdi+8], 0
0x1800245ff  jnz     loc_180024693
0x180024605  xor     edx, edx
0x180024607  mov     rcx, rbx
0x18002460a  call    ?_Buy@?$vector@EV?$allocator@E@std@@@std@@IEAA_N_K@Z; std::vector<uchar>::_Buy(unsigned __int64)
0x18002460f  test    al, al
0x180024611  jz      loc_180024485
0x180024617  mov     r8, [rdi+8]; Source
0x18002461b  mov     rdi, [rdi+10h]
0x18002461f  mov     r14, [rbx+8]
0x180024623  sub     rdi, r8
0x180024626  jz      short loc_180024637
0x180024628  mov     r9, rdi; SourceSize
0x18002462b  mov     rdx, rdi; DestinationSize
0x18002462e  mov     rcx, r14; Destination
0x180024631  call    cs:__imp_memmove_s
0x180024637  lea     rax, [rdi+r14]
0x18002463b  jmp     loc_180024481
0x180024640  mov     rax, [rbx+18h]
0x180024644  sub     rax, rcx
0x180024647  jmp     short loc_1800245EB
0x180024649  test    rcx, rcx
0x18002464c  jnz     short loc_18002468A
0x18002464e  xor     eax, eax
0x180024650  lea     r14, [r9+rax]
0x180024654  mov     r8, rcx
0x180024657  mov     rdx, r14
0x18002465a  mov     rcx, r9; Source
0x18002465d  call    ??$copy@PEBEPEAE@std@@YAPEAEPEBE0PEAE@Z; std::copy<uchar const *,uchar *>(uchar const *,uchar const *,uchar *)
0x180024662  mov     rdi, [rdi+10h]
0x180024666  mov     r15, [rbx+10h]
0x18002466a  sub     rdi, r14
0x18002466d  jz      loc_18002447D
0x180024673  mov     r9, rdi; SourceSize
0x180024676  mov     r8, r14; Source
0x180024679  mov     rdx, rdi; DestinationSize
0x18002467c  mov     rcx, r15; Destination
0x18002467f  call    cs:__imp_memmove_s
0x180024685  jmp     loc_18002447D
0x18002468a  mov     rax, [rbx+10h]
0x18002468e  sub     rax, rcx
0x180024691  jmp     short loc_180024650
0x180024693  mov     rdx, [rdi+10h]
0x180024697  sub     rdx, [rdi+8]
0x18002469b  jmp     loc_180024607
0x1800246a0  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800246a4  mov     rdx, rdi
0x1800246a7  mov     rcx, rbx
0x1800246aa  call    ?erase@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@_K0@Z; std::string::erase(unsigned __int64,unsigned __int64)
0x1800246af  xor     r8d, r8d
0x1800246b2  xor     edx, edx
0x1800246b4  mov     rcx, rbx
0x1800246b7  call    ?erase@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@_K0@Z; std::string::erase(unsigned __int64,unsigned __int64)
0x1800246bc  jmp     loc_180024448
0x1800246c1  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
0x1800246c6  jmp     loc_1800243F6
0x1800246cb  mov     rcx, rbx
0x1800246ce  call    ?size@?$vector@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@V?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@std@@@std@@QEBA_KXZ; std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::size(void)
0x1800246d3  mov     rcx, rdi
0x1800246d6  mov     rdx, rax
0x1800246d9  call    ?size@?$vector@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@V?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@std@@@std@@QEBA_KXZ; std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::size(void)
0x1800246de  cmp     rax, rdx
0x1800246e1  ja      short loc_180024710
0x1800246e3  mov     r8, [rbx+8]
0x1800246e7  mov     rcx, r10
0x1800246ea  mov     rdx, [rdi+10h]
0x1800246ee  call    ??$copy@PEAU__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@PEAU1@@std@@YAPEAU__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@PEAU1@00@Z; std::copy<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *>(__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *)
0x1800246f3  mov     rcx, rdi
0x1800246f6  call    ?size@?$vector@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@V?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@std@@@std@@QEBA_KXZ; std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::size(void)
0x1800246fb  lea     rcx, [rax+rax*2]
0x1800246ff  mov     rax, [rbx+8]
0x180024703  lea     rcx, [rax+rcx*8]
0x180024707  mov     [rbx+10h], rcx
0x18002470b  jmp     loc_1800244CB
0x180024710  mov     rcx, rbx
0x180024713  call    ?capacity@?$vector@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@V?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@std@@@std@@QEBA_KXZ; std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::capacity(void)
0x180024718  mov     rcx, rdi
0x18002471b  mov     rdx, rax
0x18002471e  call    ?size@?$vector@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@V?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@std@@@std@@QEBA_KXZ; std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::size(void)
0x180024723  cmp     rax, rdx
0x180024726  ja      short loc_180024750
0x180024728  mov     rcx, rbx
0x18002472b  call    ?size@?$vector@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@V?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@std@@@std@@QEBA_KXZ; std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::size(void)
0x180024730  mov     r8, [rbx+8]
0x180024734  lea     rcx, [rax+rax*2]
0x180024738  lea     r9, [r10+rcx*8]
0x18002473c  mov     rcx, r10
0x18002473f  mov     rdx, r9
0x180024742  call    ??$copy@PEAU__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@PEAU1@@std@@YAPEAU__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@PEAU1@00@Z; std::copy<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *>(__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *)
0x180024747  mov     r8, [rbx+10h]
0x18002474b  mov     rcx, r9
0x18002474e  jmp     short loc_180024781
0x180024750  mov     rcx, [rbx+8]; Block
0x180024754  test    rcx, rcx
0x180024757  jz      short loc_18002475E
0x180024759  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002475e  mov     rcx, rdi
0x180024761  call    ?size@?$vector@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@V?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@std@@@std@@QEBA_KXZ; std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::size(void)
0x180024766  mov     rdx, rax
0x180024769  mov     rcx, rbx
0x18002476c  call    ?_Buy@?$vector@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@V?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@std@@@std@@IEAA_N_K@Z; std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::_Buy(unsigned __int64)
0x180024771  test    al, al
0x180024773  jz      loc_1800244CB
0x180024779  mov     r8, [rbx+8]
0x18002477d  mov     rcx, [rdi+8]
0x180024781  mov     rdx, [rdi+10h]
0x180024785  call    ??$_Uninit_copy@PEAU__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@PEAU1@V?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@std@@@std@@YAPEAU__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@PEAU1@00AEAV?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z; std::_Uninit_copy<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,std::allocator<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>>(__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,std::allocator<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)
0x18002478a  jmp     loc_1800244C7
```
