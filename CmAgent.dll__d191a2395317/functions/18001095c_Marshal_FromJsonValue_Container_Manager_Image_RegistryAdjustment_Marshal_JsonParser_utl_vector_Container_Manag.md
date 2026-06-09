# Marshal::FromJsonValue<Container::Manager::Image::RegistryAdjustment,>(Marshal::JsonParser &,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>> *,Marshal::UnmarshalContext const &,Marshal::ModifierList<>)

- ea: `0x18001095c`
- end: `0x180010b47`
- name: `??$FromJsonValue@URegistryAdjustment@Image@Manager@Container@@$$V@Marshal@@YA_NAEAVJsonParser@0@PEAV?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@utl@@@utl@@AEBVUnmarshalContext@0@U?$ModifierList@$$V@0@@Z`
- size: `491`
- prototype: `char __fastcall(Marshal::JsonParser *, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180010bd0`

## callees

- `0x180003ce4`
- `0x180010740`
- `0x18001095c`
- `0x180013590`
- `0x180013748`
- `0x1800146cc`
- `0x1800149b4`
- `0x1800151c8`
- `0x18002153c`
- `0x18002163c`

## string_xrefs

- `0x180010b20`: `onecore\internal\vm\inc\marshaljsonutl.h`
- `0x180010b32`: `onecore\internal\vm\inc\marshaljsonutl.h`

## pseudocode

```c
char __fastcall Marshal::FromJsonValue<Container::Manager::Image::RegistryAdjustment,>(
        Marshal::JsonParser *a1,
        __int64 *a2,
        __int64 a3)
{
  __int64 v6; // r9
  __int64 v7; // rdx
  int v8; // edi
  __int64 v9; // rdx
  char v10; // si
  __int64 v11; // r9
  __int64 v12; // rcx
  __int64 v13; // r8
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // rdx
  char v17; // al
  char v18; // al
  int v19; // edi
  const char *v20; // r9
  __int128 v22; // [rsp+20h] [rbp-28h] BYREF
  __int64 v23; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]

  v22 = 0;
  v6 = 0;
  v23 = 0;
  v7 = *a2;
  if ( 0xEEEEEEEEEEEEEEEFuLL * ((a2[1] - v7) >> 3) )
  {
    v8 = 0;
    while ( 1 )
    {
      v9 = 120LL * v8 + v7;
      if ( *((_QWORD *)&v22 + 1) == v6 )
      {
        std::vector<Container::Manager::Image::RegistryAdjustment>::_Emplace_reallocate<Container::Manager::Image::RegistryAdjustment>(
          (__int64 *)&v22,
          *((__int64 *)&v22 + 1),
          v9);
      }
      else
      {
        Container::Manager::Image::RegistryAdjustment::RegistryAdjustment(*((_QWORD *)&v22 + 1), v9);
        *((_QWORD *)&v22 + 1) += 120LL;
      }
      ++v8;
      v7 = *a2;
      if ( v8 >= 0xEEEEEEEEEEEEEEEFuLL * ((a2[1] - *a2) >> 3) )
        break;
      v6 = v23;
    }
  }
  v10 = Marshal::FromJsonValue<Container::Manager::Image::RegistryAdjustment,>(a1, (__int64 *)&v22, a3);
  if ( v10 )
  {
    v11 = *a2;
    v12 = a2[1];
    a2[1] = *a2;
    utl::_RangeDestroyApc<utl::allocator<Container::Manager::Image::RegistryAdjustment>>(
      v12 - v11,
      v11,
      (v12 - v11) / 120 + v12 - v11);
    v13 = v22;
    v14 = 0xEEEEEEEEEEEEEEEFuLL * ((__int64)(*((_QWORD *)&v22 + 1) - v22) >> 3);
    v15 = 0xEEEEEEEEEEEEEEEFuLL * ((a2[2] - *a2) >> 3);
    if ( v14 <= v15 )
      goto LABEL_17;
    v16 = 7 * (v15 >> 2) + 8;
    if ( v16 < v14 )
      v16 = 0xEEEEEEEEEEEEEEEFuLL * ((__int64)(*((_QWORD *)&v22 + 1) - v22) >> 3);
    if ( v16 > 0x111111111111111LL )
      v16 = 0x111111111111111LL;
    if ( v14 <= v16
      && (v17 = utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>::_SetCapacity(a2),
          v13 = v22,
          v17) )
    {
LABEL_17:
      v18 = 0;
    }
    else
    {
      v18 = 1;
    }
    if ( v18 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x78,
        (unsigned int)"onecore\\internal\\vm\\inc\\marshaljsonutl.h",
        (const char *)0x8007000ELL,
        v22);
    v19 = 0;
    if ( 0xEEEEEEEEEEEEEEEFuLL * ((*((_QWORD *)&v22 + 1) - v13) >> 3) )
    {
      do
      {
        if ( !utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>::emplace_back<Container::Manager::Image::RegistryAdjustment,0>(
                a2,
                v13 + 120LL * v19) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x7F,
            (unsigned int)"onecore\\internal\\vm\\inc\\marshaljsonutl.h",
            v20);
        ++v19;
        v13 = v22;
      }
      while ( v19 < 0xEEEEEEEEEEEEEEEFuLL * ((__int64)(*((_QWORD *)&v22 + 1) - v22) >> 3) );
    }
  }
  std::vector<Container::Manager::Image::RegistryAdjustment>::~vector<Container::Manager::Image::RegistryAdjustment>(&v22);
  return v10;
}

```

## disassembly

```asm
0x18001095c  push    rbp
0x18001095e  push    rbx
0x18001095f  push    rsi
0x180010960  push    rdi
0x180010961  push    r14
0x180010963  push    r15
0x180010965  mov     rbp, rsp
0x180010968  sub     rsp, 48h
0x18001096c  mov     rsi, r8
0x18001096f  mov     rbx, rdx
0x180010972  mov     r14, rcx
0x180010975  xorps   xmm0, xmm0
0x180010978  movdqu  [rbp+var_28], xmm0
0x18001097d  xor     r9d, r9d
0x180010980  mov     [rbp+var_18], r9
0x180010984  mov     rdx, [rdx]
0x180010987  mov     rax, [rbx+8]
0x18001098b  sub     rax, rdx
0x18001098e  sar     rax, 3
0x180010992  mov     r15, 0EEEEEEEEEEEEEEEFh
0x18001099c  imul    rax, r15
0x1800109a0  test    rax, rax
0x1800109a3  jz      short loc_1800109F7
0x1800109a5  xor     edi, edi
0x1800109a7  movsxd  rax, edi
0x1800109aa  imul    rcx, rax, 78h ; 'x'
0x1800109ae  add     rdx, rcx
0x1800109b1  mov     rcx, qword ptr [rbp+var_28+8]
0x1800109b5  cmp     rcx, r9
0x1800109b8  jz      short loc_1800109C6
0x1800109ba  call    ??0RegistryAdjustment@Image@Manager@Container@@QEAA@$$QEAU0123@@Z; Container::Manager::Image::RegistryAdjustment::RegistryAdjustment(Container::Manager::Image::RegistryAdjustment &&)
0x1800109bf  add     qword ptr [rbp+var_28+8], 78h ; 'x'
0x1800109c4  jmp     short loc_1800109D5
0x1800109c6  mov     r8, rdx
0x1800109c9  mov     rdx, rcx
0x1800109cc  lea     rcx, [rbp+var_28]
0x1800109d0  call    ??$_Emplace_reallocate@URegistryAdjustment@Image@Manager@Container@@@?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@std@@@std@@AEAAPEAURegistryAdjustment@Image@Manager@Container@@QEAU2345@$$QEAU2345@@Z; std::vector<Container::Manager::Image::RegistryAdjustment>::_Emplace_reallocate<Container::Manager::Image::RegistryAdjustment>(Container::Manager::Image::RegistryAdjustment * const,Container::Manager::Image::RegistryAdjustment &&)
0x1800109d5  inc     edi
0x1800109d7  mov     rdx, [rbx]
0x1800109da  mov     rcx, [rbx+8]
0x1800109de  sub     rcx, rdx
0x1800109e1  sar     rcx, 3
0x1800109e5  imul    rcx, r15
0x1800109e9  movsxd  rax, edi
0x1800109ec  cmp     rax, rcx
0x1800109ef  jnb     short loc_1800109F7
0x1800109f1  mov     r9, [rbp+var_18]
0x1800109f5  jmp     short loc_1800109A7
0x1800109f7  mov     r8, rsi
0x1800109fa  lea     rdx, [rbp+var_28]
0x1800109fe  mov     rcx, r14
0x180010a01  call    ??$FromJsonValue@URegistryAdjustment@Image@Manager@Container@@$$V@Marshal@@YA_NAEAVJsonParser@0@PEAV?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@std@@@std@@AEBVUnmarshalContext@0@U?$ModifierList@$$V@0@@Z; Marshal::FromJsonValue<Container::Manager::Image::RegistryAdjustment,>(Marshal::JsonParser &,std::vector<Container::Manager::Image::RegistryAdjustment> *,Marshal::UnmarshalContext const &,Marshal::ModifierList<>)
0x180010a06  mov     sil, al
0x180010a09  test    al, al
0x180010a0b  jz      loc_180010B00
0x180010a11  mov     r9, [rbx]
0x180010a14  mov     rcx, [rbx+8]
0x180010a18  mov     [rbx+8], r9
0x180010a1c  sub     rcx, r9
0x180010a1f  mov     rax, 8888888888888889h
0x180010a29  imul    rcx
0x180010a2c  add     rdx, rcx
0x180010a2f  sar     rdx, 6
0x180010a33  mov     r8, rdx
0x180010a36  shr     r8, 3Fh
0x180010a3a  add     r8, rdx
0x180010a3d  mov     rdx, r9
0x180010a40  call    ??$_RangeDestroyApc@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@utl@@@utl@@YAXAEAV?$allocator@URegistryAdjustment@Image@Manager@Container@@@0@PEAURegistryAdjustment@Image@Manager@Container@@_K@Z; utl::_RangeDestroyApc<utl::allocator<Container::Manager::Image::RegistryAdjustment>>(utl::allocator<Container::Manager::Image::RegistryAdjustment> &,Container::Manager::Image::RegistryAdjustment *,unsigned __int64)
0x180010a45  mov     rcx, qword ptr [rbp+var_28+8]
0x180010a49  mov     r8, qword ptr [rbp+var_28]
0x180010a4d  sub     rcx, r8
0x180010a50  sar     rcx, 3
0x180010a54  imul    rcx, r15
0x180010a58  mov     rax, [rbx+10h]
0x180010a5c  sub     rax, [rbx]
0x180010a5f  sar     rax, 3
0x180010a63  imul    rax, r15
0x180010a67  cmp     rcx, rax
0x180010a6a  jbe     short loc_180010AA9
0x180010a6c  shr     rax, 2
0x180010a70  imul    rdx, rax, 7
0x180010a74  add     rdx, 8
0x180010a78  cmp     rdx, rcx
0x180010a7b  cmovb   rdx, rcx
0x180010a7f  mov     rax, 111111111111111h
0x180010a89  cmp     rdx, rax
0x180010a8c  cmova   rdx, rax
0x180010a90  cmp     rcx, rdx
0x180010a93  ja      short loc_180010AA5
0x180010a95  mov     rcx, rbx
0x180010a98  call    ?_SetCapacity@?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>::_SetCapacity(unsigned __int64)
0x180010a9d  mov     r8, qword ptr [rbp+var_28]
0x180010aa1  test    al, al
0x180010aa3  jnz     short loc_180010AA9
0x180010aa5  mov     al, 1
0x180010aa7  jmp     short loc_180010AAB
0x180010aa9  xor     al, al
0x180010aab  mov     rcx, [rbp+30h]; this
0x180010aaf  test    al, al
0x180010ab1  jnz     short loc_180010B1A
0x180010ab3  xor     edi, edi
0x180010ab5  mov     rax, qword ptr [rbp+var_28+8]
0x180010ab9  sub     rax, r8
0x180010abc  sar     rax, 3
0x180010ac0  imul    rax, r15
0x180010ac4  test    rax, rax
0x180010ac7  jz      short loc_180010B00
0x180010ac9  mov     r14, [rbp+30h]
0x180010acd  movsxd  rax, edi
0x180010ad0  imul    rdx, rax, 78h ; 'x'
0x180010ad4  add     rdx, r8
0x180010ad7  mov     rcx, rbx
0x180010ada  call    ??$emplace_back@URegistryAdjustment@Image@Manager@Container@@$0A@@?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@utl@@@utl@@QEAA_N$$QEAURegistryAdjustment@Image@Manager@Container@@@Z; utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>::emplace_back<Container::Manager::Image::RegistryAdjustment,0>(Container::Manager::Image::RegistryAdjustment &&)
0x180010adf  test    al, al
0x180010ae1  jz      short loc_180010B32
0x180010ae3  inc     edi
0x180010ae5  mov     rcx, qword ptr [rbp+var_28+8]
0x180010ae9  mov     r8, qword ptr [rbp+var_28]
0x180010aed  sub     rcx, r8
0x180010af0  sar     rcx, 3
0x180010af4  imul    rcx, r15
0x180010af8  movsxd  rax, edi
0x180010afb  cmp     rax, rcx
0x180010afe  jb      short loc_180010AC9
0x180010b00  lea     rcx, [rbp+var_28]
0x180010b04  call    ??1?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@std@@@std@@QEAA@XZ; std::vector<Container::Manager::Image::RegistryAdjustment>::~vector<Container::Manager::Image::RegistryAdjustment>(void)
0x180010b09  mov     al, sil
0x180010b0c  add     rsp, 48h
0x180010b10  pop     r15
0x180010b12  pop     r14
0x180010b14  pop     rdi
0x180010b15  pop     rsi
0x180010b16  pop     rbx
0x180010b17  pop     rbp
0x180010b18  retn
0x180010b1a  mov     r9d, 8007000Eh; char *
0x180010b20  lea     r8, aOnecoreInterna_3; "onecore\\internal\\vm\\inc\\marshaljson"...
0x180010b27  mov     edx, 78h ; 'x'; void *
0x180010b2c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180010b32  lea     r8, aOnecoreInterna_3; "onecore\\internal\\vm\\inc\\marshaljson"...
0x180010b39  mov     edx, 7Fh; void *
0x180010b3e  mov     rcx, r14; this
0x180010b41  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
