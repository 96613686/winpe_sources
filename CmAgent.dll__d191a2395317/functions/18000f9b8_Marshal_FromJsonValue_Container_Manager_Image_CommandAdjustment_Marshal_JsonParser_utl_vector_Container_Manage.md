# Marshal::FromJsonValue<Container::Manager::Image::CommandAdjustment,>(Marshal::JsonParser &,utl::vector<Container::Manager::Image::CommandAdjustment,utl::allocator<Container::Manager::Image::CommandAdjustment>> *,Marshal::UnmarshalContext const &,Marshal::ModifierList<>)

- ea: `0x18000f9b8`
- end: `0x18000fc31`
- name: `??$FromJsonValue@UCommandAdjustment@Image@Manager@Container@@$$V@Marshal@@YA_NAEAVJsonParser@0@PEAV?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@utl@@@utl@@AEBVUnmarshalContext@0@U?$ModifierList@$$V@0@@Z`
- size: `633`
- prototype: `char __fastcall(Marshal::JsonParser *, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180010ba0`

## callees

- `0x180002534`
- `0x180003ce4`
- `0x18000f7e4`
- `0x18000f9b8`
- `0x180012fbc`
- `0x1800145ec`
- `0x18001502c`
- `0x180021088`
- `0x18002163c`

## string_xrefs

- `0x18000fc0a`: `onecore\internal\vm\inc\marshaljsonutl.h`
- `0x18000fc1c`: `onecore\internal\vm\inc\marshaljsonutl.h`

## pseudocode

```c
char __fastcall Marshal::FromJsonValue<Container::Manager::Image::CommandAdjustment,>(
        Marshal::JsonParser *a1,
        __int64 *a2,
        __int64 a3)
{
  __int64 v6; // r9
  int v7; // ebx
  __int64 v8; // r8
  __int64 v9; // rdx
  _DWORD *v10; // r8
  _QWORD *v11; // rcx
  _OWORD *v12; // r8
  _OWORD *v13; // r9
  char v14; // r14
  __int64 v15; // rsi
  __int64 v16; // rcx
  __int64 v17; // rbx
  void *v18; // rcx
  __int64 v19; // r8
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // rdx
  char v23; // al
  char v24; // al
  int v25; // ebx
  const char *v26; // r9
  __int128 v28; // [rsp+20h] [rbp-28h] BYREF
  __int64 v29; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]

  v28 = 0;
  v6 = 0;
  v29 = 0;
  v7 = 0;
  v8 = *a2;
  if ( 0xCCCCCCCCCCCCCCCDuLL * ((a2[1] - *a2) >> 3) )
  {
    v9 = *((_QWORD *)&v28 + 1);
    while ( 1 )
    {
      v10 = (_DWORD *)(v8 + 40LL * v7);
      if ( v9 == v6 )
      {
        std::vector<Container::Manager::Image::CommandAdjustment>::_Emplace_reallocate<Container::Manager::Image::CommandAdjustment>(
          &v28,
          v9,
          (__int64)v10);
        v9 = *((_QWORD *)&v28 + 1);
      }
      else
      {
        *(_DWORD *)v9 = *v10;
        v11 = v10 + 2;
        v12 = v10 + 6;
        v13 = (_OWORD *)(v9 + 24);
        if ( (_OWORD *)*v11 == v12 )
        {
          *(_QWORD *)(v9 + 8) = v13;
          *(_QWORD *)(v9 + 16) = v9 + 2 * (((v11[1] - (_QWORD)v11 - 16LL) >> 1) + 12);
          *v13 = *v12;
        }
        else
        {
          *(_QWORD *)(v9 + 8) = *v11;
          *(_QWORD *)(v9 + 16) = v11[1];
          *(_QWORD *)v13 = *(_QWORD *)v12;
        }
        *v11 = v12;
        v11[1] = v12;
        *(_WORD *)v12 = 0;
        v9 = *((_QWORD *)&v28 + 1) + 40LL;
        *((_QWORD *)&v28 + 1) += 40LL;
      }
      ++v7;
      v8 = *a2;
      if ( v7 >= 0xCCCCCCCCCCCCCCCDuLL * ((a2[1] - *a2) >> 3) )
        break;
      v6 = v29;
    }
  }
  v14 = Marshal::FromJsonValue<Container::Manager::Image::CommandAdjustment,>(a1, (__int64 *)&v28, a3);
  if ( v14 )
  {
    v15 = *a2;
    v16 = a2[1];
    a2[1] = *a2;
    v17 = (v16 - v15) / 40;
    while ( v17 )
    {
      --v17;
      v18 = *(void **)(v15 + 40 * v17 + 8);
      if ( v18 != (void *)(v15 + 8 * (5 * v17 + 3)) )
        operator delete(v18, (const struct std::nothrow_t *)&std::nothrow);
    }
    v19 = v28;
    v20 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)&v28 + 1) - v28) >> 3);
    v21 = 0xCCCCCCCCCCCCCCCDuLL * ((a2[2] - *a2) >> 3);
    if ( v20 <= v21 )
      goto LABEL_24;
    v22 = 7 * (v21 >> 2) + 8;
    if ( v22 < v20 )
      v22 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)&v28 + 1) - v28) >> 3);
    if ( v22 > 0x333333333333333LL )
      v22 = 0x333333333333333LL;
    if ( v20 <= v22
      && (v23 = utl::vector<Container::Manager::Image::CommandAdjustment,utl::allocator<Container::Manager::Image::CommandAdjustment>>::_SetCapacity(a2),
          v19 = v28,
          v23) )
    {
LABEL_24:
      v24 = 0;
    }
    else
    {
      v24 = 1;
    }
    if ( v24 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x78,
        (unsigned int)"onecore\\internal\\vm\\inc\\marshaljsonutl.h",
        (const char *)0x8007000ELL,
        v28);
    v25 = 0;
    if ( 0xCCCCCCCCCCCCCCCDuLL * ((*((_QWORD *)&v28 + 1) - v19) >> 3) )
    {
      do
      {
        if ( !utl::vector<Container::Manager::Image::CommandAdjustment,utl::allocator<Container::Manager::Image::CommandAdjustment>>::emplace_back<Container::Manager::Image::CommandAdjustment,0>(
                a2,
                v19 + 40LL * v25) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x7F,
            (unsigned int)"onecore\\internal\\vm\\inc\\marshaljsonutl.h",
            v26);
        ++v25;
        v19 = v28;
      }
      while ( v25 < 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)&v28 + 1) - v28) >> 3) );
    }
  }
  std::vector<Container::Manager::Image::CommandAdjustment>::~vector<Container::Manager::Image::CommandAdjustment>(&v28);
  return v14;
}

```

## disassembly

```asm
0x18000f9b8  push    rbp
0x18000f9ba  push    rbx
0x18000f9bb  push    rsi
0x18000f9bc  push    rdi
0x18000f9bd  push    r14
0x18000f9bf  push    r15
0x18000f9c1  mov     rbp, rsp
0x18000f9c4  sub     rsp, 48h
0x18000f9c8  mov     rsi, r8
0x18000f9cb  mov     rdi, rdx
0x18000f9ce  mov     r14, rcx
0x18000f9d1  xorps   xmm0, xmm0
0x18000f9d4  movdqu  [rbp+var_28], xmm0
0x18000f9d9  xor     r9d, r9d
0x18000f9dc  mov     [rbp+var_18], r9
0x18000f9e0  xor     ebx, ebx
0x18000f9e2  mov     r8, [rdx]
0x18000f9e5  mov     rax, [rdx+8]
0x18000f9e9  sub     rax, r8
0x18000f9ec  sar     rax, 3
0x18000f9f0  mov     r15, 0CCCCCCCCCCCCCCCDh
0x18000f9fa  imul    rax, r15
0x18000f9fe  test    rax, rax
0x18000fa01  jz      loc_18000FABC
0x18000fa07  mov     rdx, qword ptr [rbp+var_28+8]
0x18000fa0b  movsxd  rax, ebx
0x18000fa0e  lea     rcx, [rax+rax*4]
0x18000fa12  lea     r8, [r8+rcx*8]
0x18000fa16  cmp     rdx, r9
0x18000fa19  jz      short loc_18000FA8A
0x18000fa1b  mov     eax, [r8]
0x18000fa1e  mov     [rdx], eax
0x18000fa20  lea     rcx, [r8+8]
0x18000fa24  lea     r8, [rcx+10h]
0x18000fa28  mov     rax, [rcx]
0x18000fa2b  lea     r9, [rdx+18h]
0x18000fa2f  cmp     rax, r8
0x18000fa32  jnz     short loc_18000FA5D
0x18000fa34  mov     [rdx+8], r9
0x18000fa38  mov     rax, [rcx+8]
0x18000fa3c  sub     rax, rcx
0x18000fa3f  sub     rax, 10h
0x18000fa43  sar     rax, 1
0x18000fa46  add     rax, 0Ch
0x18000fa4a  lea     rax, [rdx+rax*2]
0x18000fa4e  mov     [rdx+10h], rax
0x18000fa52  movups  xmm0, xmmword ptr [r8]
0x18000fa56  movdqu  xmmword ptr [r9], xmm0
0x18000fa5b  jmp     short loc_18000FA6F
0x18000fa5d  mov     [rdx+8], rax
0x18000fa61  mov     rax, [rcx+8]
0x18000fa65  mov     [rdx+10h], rax
0x18000fa69  mov     rax, [r8]
0x18000fa6c  mov     [r9], rax
0x18000fa6f  mov     [rcx], r8
0x18000fa72  mov     [rcx+8], r8
0x18000fa76  xor     eax, eax
0x18000fa78  mov     [r8], ax
0x18000fa7c  mov     rdx, qword ptr [rbp+var_28+8]
0x18000fa80  add     rdx, 28h ; '('
0x18000fa84  mov     qword ptr [rbp+var_28+8], rdx
0x18000fa88  jmp     short loc_18000FA97
0x18000fa8a  lea     rcx, [rbp+var_28]
0x18000fa8e  call    ??$_Emplace_reallocate@UCommandAdjustment@Image@Manager@Container@@@?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@std@@@std@@AEAAPEAUCommandAdjustment@Image@Manager@Container@@QEAU2345@$$QEAU2345@@Z; std::vector<Container::Manager::Image::CommandAdjustment>::_Emplace_reallocate<Container::Manager::Image::CommandAdjustment>(Container::Manager::Image::CommandAdjustment * const,Container::Manager::Image::CommandAdjustment &&)
0x18000fa93  mov     rdx, qword ptr [rbp+var_28+8]
0x18000fa97  inc     ebx
0x18000fa99  mov     r8, [rdi]
0x18000fa9c  mov     rcx, [rdi+8]
0x18000faa0  sub     rcx, r8
0x18000faa3  sar     rcx, 3
0x18000faa7  imul    rcx, r15
0x18000faab  movsxd  rax, ebx
0x18000faae  cmp     rax, rcx
0x18000fab1  jnb     short loc_18000FABC
0x18000fab3  mov     r9, [rbp+var_18]
0x18000fab7  jmp     loc_18000FA0B
0x18000fabc  mov     r8, rsi
0x18000fabf  lea     rdx, [rbp+var_28]
0x18000fac3  mov     rcx, r14
0x18000fac6  call    ??$FromJsonValue@UCommandAdjustment@Image@Manager@Container@@$$V@Marshal@@YA_NAEAVJsonParser@0@PEAV?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@std@@@std@@AEBVUnmarshalContext@0@U?$ModifierList@$$V@0@@Z; Marshal::FromJsonValue<Container::Manager::Image::CommandAdjustment,>(Marshal::JsonParser &,std::vector<Container::Manager::Image::CommandAdjustment> *,Marshal::UnmarshalContext const &,Marshal::ModifierList<>)
0x18000facb  mov     r14b, al
0x18000face  test    al, al
0x18000fad0  jz      loc_18000FBEA
0x18000fad6  mov     rsi, [rdi]
0x18000fad9  mov     rcx, [rdi+8]
0x18000fadd  mov     [rdi+8], rsi
0x18000fae1  sub     rcx, rsi
0x18000fae4  mov     rax, 6666666666666667h
0x18000faee  imul    rcx
0x18000faf1  mov     rbx, rdx
0x18000faf4  sar     rbx, 4
0x18000faf8  mov     rax, rbx
0x18000fafb  shr     rax, 3Fh
0x18000faff  add     rbx, rax
0x18000fb02  jz      short loc_18000FB2E
0x18000fb04  dec     rbx
0x18000fb07  lea     rax, [rbx+rbx*4]
0x18000fb0b  mov     rcx, [rsi+rax*8+8]; void *
0x18000fb10  lea     rax, [rax+3]
0x18000fb14  lea     rax, [rsi+rax*8]
0x18000fb18  cmp     rcx, rax
0x18000fb1b  jz      short loc_18000FB29
0x18000fb1d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000fb24  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000fb29  test    rbx, rbx
0x18000fb2c  jnz     short loc_18000FB04
0x18000fb2e  mov     rcx, qword ptr [rbp+var_28+8]
0x18000fb32  mov     r8, qword ptr [rbp+var_28]
0x18000fb36  sub     rcx, r8
0x18000fb39  sar     rcx, 3
0x18000fb3d  imul    rcx, r15
0x18000fb41  mov     rax, [rdi+10h]
0x18000fb45  sub     rax, [rdi]
0x18000fb48  sar     rax, 3
0x18000fb4c  imul    rax, r15
0x18000fb50  cmp     rcx, rax
0x18000fb53  jbe     short loc_18000FB92
0x18000fb55  shr     rax, 2
0x18000fb59  imul    rdx, rax, 7
0x18000fb5d  add     rdx, 8
0x18000fb61  cmp     rdx, rcx
0x18000fb64  cmovb   rdx, rcx
0x18000fb68  mov     rax, 333333333333333h
0x18000fb72  cmp     rdx, rax
0x18000fb75  cmova   rdx, rax
0x18000fb79  cmp     rcx, rdx
0x18000fb7c  ja      short loc_18000FB8E
0x18000fb7e  mov     rcx, rdi
0x18000fb81  call    ?_SetCapacity@?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<Container::Manager::Image::CommandAdjustment,utl::allocator<Container::Manager::Image::CommandAdjustment>>::_SetCapacity(unsigned __int64)
0x18000fb86  mov     r8, qword ptr [rbp+var_28]
0x18000fb8a  test    al, al
0x18000fb8c  jnz     short loc_18000FB92
0x18000fb8e  mov     al, 1
0x18000fb90  jmp     short loc_18000FB94
0x18000fb92  xor     al, al
0x18000fb94  mov     rcx, [rbp+30h]; this
0x18000fb98  test    al, al
0x18000fb9a  jnz     short loc_18000FC04
0x18000fb9c  xor     ebx, ebx
0x18000fb9e  mov     rax, qword ptr [rbp+var_28+8]
0x18000fba2  sub     rax, r8
0x18000fba5  sar     rax, 3
0x18000fba9  imul    rax, r15
0x18000fbad  test    rax, rax
0x18000fbb0  jz      short loc_18000FBEA
0x18000fbb2  mov     rsi, [rbp+30h]
0x18000fbb6  movsxd  rax, ebx
0x18000fbb9  lea     rcx, [rax+rax*4]
0x18000fbbd  lea     rdx, [r8+rcx*8]
0x18000fbc1  mov     rcx, rdi
0x18000fbc4  call    ??$emplace_back@UCommandAdjustment@Image@Manager@Container@@$0A@@?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@utl@@@utl@@QEAA_N$$QEAUCommandAdjustment@Image@Manager@Container@@@Z; utl::vector<Container::Manager::Image::CommandAdjustment,utl::allocator<Container::Manager::Image::CommandAdjustment>>::emplace_back<Container::Manager::Image::CommandAdjustment,0>(Container::Manager::Image::CommandAdjustment &&)
0x18000fbc9  test    al, al
0x18000fbcb  jz      short loc_18000FC1C
0x18000fbcd  inc     ebx
0x18000fbcf  mov     rcx, qword ptr [rbp+var_28+8]
0x18000fbd3  mov     r8, qword ptr [rbp+var_28]
0x18000fbd7  sub     rcx, r8
0x18000fbda  sar     rcx, 3
0x18000fbde  imul    rcx, r15
0x18000fbe2  movsxd  rax, ebx
0x18000fbe5  cmp     rax, rcx
0x18000fbe8  jb      short loc_18000FBB2
0x18000fbea  lea     rcx, [rbp+var_28]
0x18000fbee  call    ??1?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@std@@@std@@QEAA@XZ; std::vector<Container::Manager::Image::CommandAdjustment>::~vector<Container::Manager::Image::CommandAdjustment>(void)
0x18000fbf3  mov     al, r14b
0x18000fbf6  add     rsp, 48h
0x18000fbfa  pop     r15
0x18000fbfc  pop     r14
0x18000fbfe  pop     rdi
0x18000fbff  pop     rsi
0x18000fc00  pop     rbx
0x18000fc01  pop     rbp
0x18000fc02  retn
0x18000fc04  mov     r9d, 8007000Eh; char *
0x18000fc0a  lea     r8, aOnecoreInterna_3; "onecore\\internal\\vm\\inc\\marshaljson"...
0x18000fc11  mov     edx, 78h ; 'x'; void *
0x18000fc16  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000fc1c  lea     r8, aOnecoreInterna_3; "onecore\\internal\\vm\\inc\\marshaljson"...
0x18000fc23  mov     edx, 7Fh; void *
0x18000fc28  mov     rcx, rsi; this
0x18000fc2b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
