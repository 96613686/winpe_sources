# Data::Stack::ConstructInstruction<CommonLicense,64>::Reset<Binary::ActiveCategory const &,Data::Stack::OddMenu &>(Data::Stack::OddMenu &,Binary::ActiveCategory const &,Data::Stack::OddMenu &)

- ea: `0x180066570`
- end: `0x1800666f7`
- name: `??$Reset@AEBVActiveCategory@Binary@@AEAVOddMenu@Stack@Data@@@?$ConstructInstruction@VCommonLicense@@$0EA@@Stack@Data@@QEAAXAEAVOddMenu@12@AEBVActiveCategory@Binary@@0@Z`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180069140`

## callees

- `0x18000f850`
- `0x180059140`
- `0x180066570`
- `0x180086d20`
- `0x1800871f0`
- `0x180087670`
- `0x1800bf3b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Data::Stack::ConstructInstruction<CommonLicense,64>::Reset<Binary::ActiveCategory const &,Data::Stack::OddMenu &>(
        __int64 *a1,
        __int64 (__fastcall ***a2)(_QWORD, __int64),
        __int64 a3,
        __int64 a4)
{
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rbx
  unsigned __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  _QWORD *v13; // rdi
  __int64 v14; // rcx

  Data::Stack::ConstructInstruction<Binary::IntegratedSelection::DerivativeServer<1,4,3,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1,3>,64>::CallComplexSkill(a1);
  v8 = (**a2)(a2, 312);
  v9 = v8;
  if ( v8 )
  {
    v10 = v8 + 32;
    v11 = ((_BYTE)v8 + 32) & 0x3F;
    v8 = 64 - v11;
    if ( !v11 )
      v8 = 0;
    if ( v8 > 0x118 || 280 - v8 < 0xD8 )
      v12 = 0;
    else
      v12 = v8 + v10;
    *(_DWORD *)v9 = 1;
    *(_QWORD *)(v9 + 8) = v12;
    *(_BYTE *)(v9 + 16) = 0;
    *(_QWORD *)(v9 + 24) = a2;
    *a1 = v9;
    if ( !*(_BYTE *)(v9 + 16) )
    {
      v13 = *(_QWORD **)(v9 + 8);
      if ( v13 )
      {
        *v13 = &CommonLicense::`vftable';
        Binary::Definition::FastResource::FastResource((Binary::Definition::FastResource *)(v13 + 1));
        v13[26] = 0;
        Binary::Definition::FastResource::OfferEllipticServer(
          (Binary::Definition::FastResource *)(v13 + 1),
          (const struct Binary::ActiveCategory *)a3);
        Binary::Definition::FastResource::LowerAsyncEntry((Binary::Definition::FastResource *)(v13 + 1));
        LOBYTE(v8) = Binary::IntegratedSelection::DefinePartialDNS<DivideTemporaryCategory,Data::Stack::OddMenu &,Data::Stack::ConstructInstruction<Binary::IntegratedSelection::CompletePaper,64> &>(
                       (Binary::Definition::FastResource *)(v13 + 1),
                       a4,
                       v13 + 26);
        v14 = v13[26];
        if ( v14 )
        {
          if ( *(_BYTE *)(v14 + 16) )
          {
            if ( *(_QWORD *)(v14 + 8) )
            {
              if ( *(int *)v14 > 0 )
              {
                LOBYTE(v8) = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**(_QWORD **)(v14 + 8) + 8LL))(
                               *(_QWORD *)(v14 + 8),
                               v13 + 1);
                if ( *(_DWORD *)(a3 + 80) == 1 )
                  LOBYTE(v8) = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))(**(_QWORD **)(v13[26] + 8LL)
                                                                                                 + 72LL))(
                                 *(_QWORD *)(v13[26] + 8LL),
                                 *(_QWORD *)(a3 + 128),
                                 *(unsigned int *)(a3 + 36),
                                 *(unsigned int *)(a3 + 40),
                                 *(_DWORD *)(a3 + 44));
              }
            }
          }
        }
        *(_BYTE *)(v9 + 16) = 1;
      }
    }
  }
  else
  {
    *a1 = 0;
  }
  return v8;
}

```

## disassembly

```asm
0x180066570  mov     [rsp+arg_8], rbx
0x180066575  mov     [rsp+arg_10], rbp
0x18006657a  mov     [rsp+arg_18], rsi
0x18006657f  push    rdi
0x180066580  push    r14
0x180066582  push    r15
0x180066584  sub     rsp, 30h
0x180066588  mov     r15, r9
0x18006658b  mov     rsi, r8
0x18006658e  mov     r14, rdx
0x180066591  mov     rdi, rcx
0x180066594  call    ?CallComplexSkill@?$ConstructInstruction@V?$DerivativeServer@$00$03$02V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$00$02@IntegratedSelection@Binary@@$0EA@@Stack@Data@@AEAAXXZ; Data::Stack::ConstructInstruction<Binary::IntegratedSelection::DerivativeServer<1,4,3,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1,3>,64>::CallComplexSkill(void)
0x180066599  mov     rax, [r14]
0x18006659c  mov     edx, 138h
0x1800665a1  mov     rcx, r14
0x1800665a4  mov     rax, [rax]
0x1800665a7  call    cs:__guard_dispatch_icall_fptr
0x1800665ad  mov     rbx, rax
0x1800665b0  test    rax, rax
0x1800665b3  jz      loc_1800666D7
0x1800665b9  lea     rdx, [rax+20h]
0x1800665bd  mov     rcx, rdx
0x1800665c0  and     ecx, 3Fh
0x1800665c3  mov     eax, 40h ; '@'
0x1800665c8  sub     rax, rcx
0x1800665cb  test    rcx, rcx
0x1800665ce  cmovz   rax, rcx
0x1800665d2  mov     ecx, 118h
0x1800665d7  cmp     rax, rcx
0x1800665da  ja      short loc_1800665EE
0x1800665dc  sub     rcx, rax
0x1800665df  cmp     rcx, 0D8h
0x1800665e6  jb      short loc_1800665EE
0x1800665e8  lea     rcx, [rax+rdx]
0x1800665ec  jmp     short loc_1800665F0
0x1800665ee  xor     ecx, ecx
0x1800665f0  mov     dword ptr [rbx], 1
0x1800665f6  mov     [rbx+8], rcx
0x1800665fa  mov     byte ptr [rbx+10h], 0
0x1800665fe  mov     [rbx+18h], r14
0x180066602  mov     [rdi], rbx
0x180066605  cmp     byte ptr [rbx+10h], 0
0x180066609  jnz     loc_1800666DE
0x18006660f  mov     rdi, [rbx+8]
0x180066613  test    rdi, rdi
0x180066616  jz      loc_1800666DE
0x18006661c  mov     [rsp+48h+arg_0], rdi
0x180066621  lea     rax, ??_7CommonLicense@@6B@; const CommonLicense::`vftable'
0x180066628  mov     [rdi], rax
0x18006662b  lea     rcx, [rdi+8]; this
0x18006662f  call    ??0FastResource@Definition@Binary@@QEAA@XZ; Binary::Definition::FastResource::FastResource(void)
0x180066634  mov     qword ptr [rdi+0D0h], 0
0x18006663f  mov     rdx, rsi; struct Binary::ActiveCategory *
0x180066642  lea     rcx, [rdi+8]; this
0x180066646  call    ?OfferEllipticServer@FastResource@Definition@Binary@@QEAAXAEBVActiveCategory@3@@Z; Binary::Definition::FastResource::OfferEllipticServer(Binary::ActiveCategory const &)
0x18006664b  lea     rcx, [rdi+8]; this
0x18006664f  call    ?LowerAsyncEntry@FastResource@Definition@Binary@@QEAAXXZ; Binary::Definition::FastResource::LowerAsyncEntry(void)
0x180066654  lea     r8, [rdi+0D0h]
0x18006665b  mov     rdx, r15
0x18006665e  lea     rcx, [rdi+8]
0x180066662  call    ??$DefinePartialDNS@VDivideTemporaryCategory@@AEAVOddMenu@Stack@Data@@AEAV?$ConstructInstruction@VCompletePaper@IntegratedSelection@Binary@@$0EA@@34@@IntegratedSelection@Binary@@YA_NAEBVFastResource@Definition@1@AEAVOddMenu@Stack@Data@@AEAV?$ConstructInstruction@VCompletePaper@IntegratedSelection@Binary@@$0EA@@56@@Z; Binary::IntegratedSelection::DefinePartialDNS<DivideTemporaryCategory,Data::Stack::OddMenu &,Data::Stack::ConstructInstruction<Binary::IntegratedSelection::CompletePaper,64> &>(Binary::Definition::FastResource const &,Data::Stack::OddMenu &,Data::Stack::ConstructInstruction<Binary::IntegratedSelection::CompletePaper,64> &)
0x180066667  mov     rcx, [rdi+0D0h]
0x18006666e  test    rcx, rcx
0x180066671  jz      short loc_1800666D1
0x180066673  cmp     byte ptr [rcx+10h], 0
0x180066677  jz      short loc_1800666D1
0x180066679  cmp     qword ptr [rcx+8], 0
0x18006667e  jz      short loc_1800666D1
0x180066680  cmp     dword ptr [rcx], 0
0x180066683  jle     short loc_1800666D1
0x180066685  mov     rcx, [rcx+8]
0x180066689  mov     rax, [rcx]
0x18006668c  lea     rdx, [rdi+8]
0x180066690  mov     rax, [rax+8]
0x180066694  call    cs:__guard_dispatch_icall_fptr
0x18006669a  cmp     dword ptr [rsi+50h], 1
0x18006669e  jnz     short loc_1800666D1
0x1800666a0  mov     rax, [rdi+0D0h]
0x1800666a7  mov     rcx, [rax+8]
0x1800666ab  mov     rax, [rcx]
0x1800666ae  mov     r10d, [rsi+2Ch]
0x1800666b2  mov     [rsp+48h+var_28], r10d
0x1800666b7  mov     r9d, [rsi+28h]
0x1800666bb  mov     r8d, [rsi+24h]
0x1800666bf  mov     rdx, [rsi+80h]
0x1800666c6  mov     rax, [rax+48h]
0x1800666ca  call    cs:__guard_dispatch_icall_fptr
0x1800666d0  nop
0x1800666d1  mov     byte ptr [rbx+10h], 1
0x1800666d5  jmp     short loc_1800666DE
0x1800666d7  mov     qword ptr [rdi], 0
0x1800666de  mov     rbx, [rsp+48h+arg_8]
0x1800666e3  mov     rbp, [rsp+48h+arg_10]
0x1800666e8  mov     rsi, [rsp+48h+arg_18]
0x1800666ed  add     rsp, 30h
0x1800666f1  pop     r15
0x1800666f3  pop     r14
0x1800666f5  pop     rdi
0x1800666f6  retn
```
