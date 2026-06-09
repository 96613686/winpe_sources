# Direction::UniqueBinary::AdaptComprehensiveRecord(Direction::UniqueBinary &,Binary::ActiveCategory const &)

- ea: `0x18004ac40`
- end: `0x18004b7bf`
- name: `?AdaptComprehensiveRecord@UniqueBinary@Direction@@SA_NAEAV12@AEBVActiveCategory@Binary@@@Z`
- size: `2943`
- prototype: `bool __fastcall(struct Direction::UniqueBinary *this, const struct Binary::ActiveCategory *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000e4b0`
- `0x18004ac40`
- `0x18004d1d0`
- `0x1800bf3b0`

## pseudocode

```c
bool __fastcall Direction::UniqueBinary::AdaptComprehensiveRecord(
        struct Direction::UniqueBinary *this,
        const struct Binary::ActiveCategory *a2)
{
  __int64 v4; // r8
  __int64 v5; // rcx
  unsigned int v6; // r10d
  int v7; // r11d
  char v8; // r9
  unsigned int v9; // eax
  _BYTE *v10; // rbx
  __int64 v11; // rcx
  char *v12; // r9
  bool v13; // sf
  void (__fastcall *MixedProvider)(bool (__fastcall *)(struct Direction::UniqueBinary *, const struct Binary::ActiveCategory *), unsigned __int64, __int64); // rax
  int v16; // [rsp+48h] [rbp-28h]
  int v17; // [rsp+48h] [rbp-28h]
  int v18; // [rsp+48h] [rbp-28h]
  _BYTE *retaddr; // [rsp+A8h] [rbp+38h]

  v4 = ~(~(~(~((8573879 * *(unsigned __int8 *)Direction::UniqueBinary::LoopOptimalOperation) | 0x6840A140)
           | (8573879 * *(unsigned __int8 *)Direction::UniqueBinary::LoopOptimalOperation) & 0x6840A140)
         | 0x1494)
       | ~(~((8573879 * *(unsigned __int8 *)Direction::UniqueBinary::LoopOptimalOperation) | 0x6840A140)
         | (8573879 * *(unsigned __int8 *)Direction::UniqueBinary::LoopOptimalOperation) & 0x6840A140)
       & 0x1494u);
  if ( (_DWORD)v4 == ~((8573879 * *(unsigned __int8 *)Direction::UniqueBinary::LoopOptimalOperation) ^ 0x6840B5D4
                     | ~((8573879 * *(unsigned __int8 *)Direction::UniqueBinary::LoopOptimalOperation) | 0x6840B5D4))
                   + (~(~((8573879 * *(unsigned __int8 *)Direction::UniqueBinary::LoopOptimalOperation) | 0x6840B5D4)
                      | (8573879 * *(unsigned __int8 *)Direction::UniqueBinary::LoopOptimalOperation) & 0x6840B5D4)
                    | (8573879 * *(unsigned __int8 *)Direction::UniqueBinary::LoopOptimalOperation) & 0x6840B5D4)
                   - 8573879 * *(unsigned __int8 *)Direction::UniqueBinary::LoopOptimalOperation
                   - 1749071316 )
    goto LABEL_9;
  v4 = ~(~(~(~((2839710 * *(unsigned __int8 *)Direction::UniqueBinary::LoopOptimalOperation) | 0x27700048)
           | ~((2839710 * *(unsigned __int8 *)Direction::UniqueBinary::LoopOptimalOperation) ^ 0x27700048
             | ~((2839710 * *(unsigned __int8 *)Direction::UniqueBinary::LoopOptimalOperation) | 0x27700048)))
         | 0x386)
       | ~(~(~((2839710 * *(unsigned __int8 *)Direction::UniqueBinary::LoopOptimalOperation) | 0x27700048)
           | ~((2839710 * *(unsigned __int8 *)Direction::UniqueBinary::LoopOptimalOperation) ^ 0x27700048
             | ~((2839710 * *(unsigned __int8 *)Direction::UniqueBinary::LoopOptimalOperation) | 0x27700048)))
         ^ 0x386
         | ~(~(~((2839710 * *(unsigned __int8 *)Direction::UniqueBinary::LoopOptimalOperation) | 0x27700048)
             | ~((2839710 * *(unsigned __int8 *)Direction::UniqueBinary::LoopOptimalOperation) ^ 0x27700048
               | ~((2839710 * *(unsigned __int8 *)Direction::UniqueBinary::LoopOptimalOperation) | 0x27700048)))
           | 0x386u)));
  if ( (_DWORD)v4 != ~((2839710 * *(unsigned __int8 *)Direction::UniqueBinary::LoopOptimalOperation) ^ 0x277003CE
                     | ~((2839710 * *(unsigned __int8 *)Direction::UniqueBinary::LoopOptimalOperation) | 0x277003CE))
                   + ((2839710 * *(unsigned __int8 *)Direction::UniqueBinary::LoopOptimalOperation) ^ 0x277003CE
                    | ~((2839710 * *(unsigned __int8 *)Direction::UniqueBinary::LoopOptimalOperation) ^ 0x277003CE
                      | ~((2839710 * *(unsigned __int8 *)Direction::UniqueBinary::LoopOptimalOperation) | 0x277003CE)))
                   - 2839710 * *(unsigned __int8 *)Direction::UniqueBinary::LoopOptimalOperation
                   - 661652430 )
  {
    v17 = *(unsigned __int8 *)Direction::UniqueBinary::LoopOptimalOperation;
    v4 = ~(~(~(~((8340672 * v17) | 0x74D40840) | (8340672 * v17) & 0x74D40840) | 0x1400)
         | ~(~((8340672 * v17) | 0x74D40840) | (8340672 * v17) & 0x74D40840) & 0x1400u);
    if ( (_DWORD)v4 == ~((8340672 * v17) ^ 0x74D41C40 | ~((8340672 * v17) | 0x74D41C40))
                     + ((8340672 * v17) ^ 0x74D41C40 | (8340672 * v17) & 0x74D41C40)
                     - 8340672 * v17
                     - 1960057920 )
    {
      v11 = *((char *)Direction::UniqueBinary::LoopOptimalOperation + 1);
      v12 = (char *)Direction::UniqueBinary::LoopOptimalOperation + 2;
      v13 = (v11 & 0x80u) != 0LL;
      if ( (char)v11 > 0 )
      {
        if ( (__int64)v12 > 0x7FFFFFFFFFFFFFFFLL - v11 )
          goto LABEL_25;
        v13 = (v11 & 0x80u) != 0LL;
      }
      if ( !v13 || (__int64)v12 >= (__int64)(0x8000000000000000uLL - v11) )
      {
        v18 = (unsigned __int8)v12[v11];
        v4 = ~(~(~(~((2839710 * v18) | 0x228069E0) | (2839710 * v18) & 0x228069E0) | 0x70408)
             | ~(~((2839710 * v18) | 0x228069E0) | (2839710 * v18) & 0x228069E0) & 0x70408u);
        if ( (_DWORD)v4 == ~((2839710 * v18) ^ 0x22876DE8 | ~((2839710 * v18) | 0x22876DE8))
                         + ((2839710 * v18) ^ 0x22876DE8 | (2839710 * v18) & 0x22876DE8)
                         - 2839710 * v18
                         - 579300840 )
          goto LABEL_9;
      }
    }
LABEL_25:
    v6 = IntegralRelation::OddMap;
    goto LABEL_10;
  }
  v5 = *(int *)((char *)Direction::UniqueBinary::LoopOptimalOperation + 1);
  if ( v5 <= 0 )
  {
    if ( v5 < 0 && (__int64)&loc_18004D1D5 < (__int64)(0x8000000000000000uLL - v5) )
      goto LABEL_25;
    goto LABEL_8;
  }
  if ( (__int64)&loc_18004D1D5 <= 0x7FFFFFFFFFFFFFFFLL - v5 )
  {
LABEL_8:
    v16 = *((unsigned __int8 *)&loc_18004D1D5 + v5);
    v4 = ~(~((8573879 * v16) & 0x6840A140) & ((8573879 * v16) | 0x6840A140) & 0x1494)
       & (~((8573879 * v16) & 0x6840A140) & ((8573879 * v16) | 0x6840A140) | 0x1494u);
    if ( (_DWORD)v4 == ~((8573879 * v16) ^ 0x6840B5D4 | ~((8573879 * v16) | 0x6840B5D4))
                     + ((8573879 * v16) ^ 0x6840B5D4 | (8573879 * v16) & 0x6840B5D4)
                     - 8573879 * v16
                     - 1749071316 )
    {
LABEL_9:
      v6 = ++IntegralRelation::OddMap;
      goto LABEL_10;
    }
    goto LABEL_25;
  }
  v6 = IntegralRelation::OddMap;
LABEL_10:
  v7 = 0;
  v8 = 1;
  v9 = 19523;
  v10 = 0;
  while ( 1 )
  {
    while ( v9 <= 0x164579 )
    {
      switch ( v9 )
      {
        case 0x164579u:
          v9 = 1459631;
          if ( v8 != 1 )
            v9 = 1479083;
          break;
        case 0x4C43u:
          v8 = 0;
          v9 = 1459577;
          break;
        case 0x4C54u:
          v9 = 1459577;
          if ( (v6 ^ 0xFB9732B4) == 0x525EE7 )
            v9 = 5398247;
          else
            v8 = 1;
          break;
        default:
          v9 = 1459577;
          if ( *v10 == (unsigned __int8)((v6 ^ v7) / 0x6D2E31) )
            v8 = 1;
          else
            v9 = 1459631;
          break;
      }
    }
    if ( v9 == 1459631 )
      break;
    if ( v9 == 1479083 )
    {
      v10 = retaddr;
      v9 = 19540;
    }
    else
    {
      v9 = 19594;
      v7 = -1396333729;
    }
  }
  if ( v8 )
    IntegralRelation::OddMap = v6 + 1;
  MixedProvider = (void (__fastcall *)(bool (__fastcall *)(struct Direction::UniqueBinary *, const struct Binary::ActiveCategory *), unsigned __int64, __int64))GenerateMixedProvider(0xFF1F1FFFA0D0D030uLL, 296017962, v4);
  MixedProvider(
    Direction::UniqueBinary::AdaptComprehensiveRecord,
    (unsigned __int64)Direction::UniqueBinary::AdaptComprehensiveRecord ^ 0x28EA3A,
    1632810);
  return Direction::UniqueBinary::LoopOptimalOperation(this, a2);
}

```

## disassembly

```asm
0x18004ac40  mov     [rsp-38h+arg_10], rbx
0x18004ac45  push    rbp
0x18004ac46  push    rsi
0x18004ac47  push    rdi
0x18004ac48  push    r12
0x18004ac4a  push    r13
0x18004ac4c  push    r14
0x18004ac4e  push    r15
0x18004ac50  mov     rbp, rsp
0x18004ac53  sub     rsp, 70h
0x18004ac57  mov     rdi, rcx
0x18004ac5a  mov     [rbp+var_18], 6840A140h
0x18004ac61  lea     r9, ?LoopOptimalOperation@UniqueBinary@Direction@@QEAA_NAEBVActiveCategory@Binary@@@Z; Direction::UniqueBinary::LoopOptimalOperation(Binary::ActiveCategory const &)
0x18004ac68  mov     rsi, rdx
0x18004ac6b  movzx   eax, byte ptr [r9]
0x18004ac6f  mov     [rbp+var_10], eax
0x18004ac72  mov     eax, [rbp+var_10]
0x18004ac75  imul    ecx, eax, 82D3B7h
0x18004ac7b  mov     eax, [rbp+var_18]
0x18004ac7e  mov     [rbp+var_48], eax
0x18004ac81  mov     [rbp+var_20], ecx
0x18004ac84  mov     eax, [rbp+var_20]
0x18004ac87  mov     [rbp+var_38], eax
0x18004ac8a  mov     eax, [rbp+var_48]
0x18004ac8d  mov     [rbp+var_28], eax
0x18004ac90  mov     eax, [rbp+var_38]
0x18004ac93  mov     [rbp+var_48], eax
0x18004ac96  mov     ecx, [rbp+var_48]
0x18004ac99  mov     eax, [rbp+var_28]
0x18004ac9c  or      ecx, eax
0x18004ac9e  mov     [rbp+var_48], ecx
0x18004aca1  mov     eax, [rbp+var_48]
0x18004aca4  not     eax
0x18004aca6  mov     [rbp+var_28], eax
0x18004aca9  mov     eax, [rbp+var_18]
0x18004acac  mov     [rbp+var_38], eax
0x18004acaf  mov     eax, [rbp+var_20]
0x18004acb2  mov     [rbp+var_48], eax
0x18004acb5  mov     ecx, [rbp+var_48]
0x18004acb8  mov     eax, [rbp+var_38]
0x18004acbb  and     ecx, eax
0x18004acbd  mov     eax, [rbp+var_28]
0x18004acc0  mov     [rbp+var_38], eax
0x18004acc3  mov     [rbp+var_48], ecx
0x18004acc6  mov     eax, [rbp+var_48]
0x18004acc9  mov     [rbp+var_48], eax
0x18004accc  mov     ecx, [rbp+var_48]
0x18004accf  mov     eax, [rbp+var_38]
0x18004acd2  or      ecx, eax
0x18004acd4  mov     [rbp+var_48], ecx
0x18004acd7  mov     eax, [rbp+var_48]
0x18004acda  not     eax
0x18004acdc  mov     [rbp+var_18], 1494h
0x18004ace3  mov     [rbp+var_20], eax
0x18004ace6  mov     eax, [rbp+var_18]
0x18004ace9  mov     [rbp+var_48], eax
0x18004acec  mov     eax, [rbp+var_20]
0x18004acef  mov     [rbp+var_38], eax
0x18004acf2  mov     eax, [rbp+var_48]
0x18004acf5  mov     [rbp+var_28], eax
0x18004acf8  mov     eax, [rbp+var_38]
0x18004acfb  mov     [rbp+var_48], eax
0x18004acfe  mov     ecx, [rbp+var_48]
0x18004ad01  mov     eax, [rbp+var_28]
0x18004ad04  or      ecx, eax
0x18004ad06  mov     [rbp+var_48], ecx
0x18004ad09  mov     eax, [rbp+var_48]
0x18004ad0c  not     eax
0x18004ad0e  mov     [rbp+var_28], eax
0x18004ad11  mov     eax, [rbp+var_18]
0x18004ad14  mov     [rbp+var_38], eax
0x18004ad17  mov     eax, [rbp+var_20]
0x18004ad1a  mov     [rbp+var_48], eax
0x18004ad1d  mov     ecx, [rbp+var_48]
0x18004ad20  mov     eax, [rbp+var_38]
0x18004ad23  and     ecx, eax
0x18004ad25  mov     eax, [rbp+var_28]
0x18004ad28  mov     [rbp+var_48], ecx
0x18004ad2b  mov     [rbp+var_38], eax
0x18004ad2e  mov     eax, [rbp+var_48]
0x18004ad31  mov     [rbp+var_48], eax
0x18004ad34  mov     ecx, [rbp+var_48]
0x18004ad37  mov     eax, [rbp+var_38]
0x18004ad3a  or      ecx, eax
0x18004ad3c  mov     [rbp+var_48], ecx
0x18004ad3f  mov     r8d, [rbp+var_48]
0x18004ad43  mov     [rbp+var_18], 6840A140h
0x18004ad4a  not     r8d
0x18004ad4d  mov     eax, [rbp+var_18]
0x18004ad50  mov     [rbp+var_48], eax
0x18004ad53  mov     [rbp+var_20], 1494h
0x18004ad5a  mov     eax, [rbp+var_20]
0x18004ad5d  mov     [rbp+var_38], eax
0x18004ad60  mov     eax, [rbp+var_48]
0x18004ad63  mov     [rbp+var_28], eax
0x18004ad66  mov     eax, [rbp+var_38]
0x18004ad69  mov     [rbp+var_48], eax
0x18004ad6c  mov     ecx, [rbp+var_48]
0x18004ad6f  mov     eax, [rbp+var_28]
0x18004ad72  or      ecx, eax
0x18004ad74  mov     [rbp+var_48], ecx
0x18004ad77  mov     eax, [rbp+var_48]
0x18004ad7a  not     eax
0x18004ad7c  mov     [rbp+var_28], eax
0x18004ad7f  mov     eax, [rbp+var_18]
0x18004ad82  mov     [rbp+var_38], eax
0x18004ad85  mov     eax, [rbp+var_20]
0x18004ad88  mov     [rbp+var_48], eax
0x18004ad8b  mov     ecx, [rbp+var_48]
0x18004ad8e  mov     eax, [rbp+var_38]
0x18004ad91  and     ecx, eax
0x18004ad93  mov     eax, [rbp+var_28]
0x18004ad96  mov     [rbp+var_38], eax
0x18004ad99  mov     [rbp+var_48], ecx
0x18004ad9c  mov     eax, [rbp+var_48]
0x18004ad9f  mov     [rbp+var_48], eax
0x18004ada2  mov     ecx, [rbp+var_48]
0x18004ada5  mov     eax, [rbp+var_38]
0x18004ada8  or      ecx, eax
0x18004adaa  mov     [rbp+var_48], ecx
0x18004adad  mov     eax, [rbp+var_48]
0x18004adb0  not     eax
0x18004adb2  mov     [rbp+var_18], eax
0x18004adb5  mov     eax, [rbp+var_10]
0x18004adb8  imul    ecx, eax, 82D3B7h
0x18004adbe  mov     eax, [rbp+var_18]
0x18004adc1  mov     [rbp+var_38], eax
0x18004adc4  mov     [rbp+var_20], ecx
0x18004adc7  mov     eax, [rbp+var_20]
0x18004adca  mov     [rbp+var_48], eax
0x18004adcd  mov     eax, [rbp+var_38]
0x18004add0  mov     [rbp+var_10], eax
0x18004add3  mov     eax, [rbp+var_48]
0x18004add6  mov     [rbp+var_28], eax
0x18004add9  mov     eax, [rbp+var_10]
0x18004addc  mov     [rbp+var_40], eax
0x18004addf  mov     eax, [rbp+var_28]
0x18004ade2  mov     [rbp+var_30], eax
0x18004ade5  mov     ecx, [rbp+var_30]
0x18004ade8  mov     eax, [rbp+var_40]
0x18004adeb  or      ecx, eax
0x18004aded  mov     eax, [rbp+var_10]
0x18004adf0  not     ecx
0x18004adf2  mov     [rbp+var_30], eax
0x18004adf5  mov     eax, [rbp+var_28]
0x18004adf8  mov     [rbp+var_40], eax
0x18004adfb  mov     [rbp+var_50], ecx
0x18004adfe  mov     ecx, [rbp+var_40]
0x18004ae01  mov     eax, [rbp+var_30]
0x18004ae04  and     ecx, eax
0x18004ae06  mov     [rbp+var_40], ecx
0x18004ae09  mov     ecx, [rbp+var_40]
0x18004ae0c  mov     eax, [rbp+var_50]
0x18004ae0f  or      ecx, eax
0x18004ae11  mov     eax, [rbp+var_38]
0x18004ae14  not     ecx
0x18004ae16  mov     [rbp+var_40], eax
0x18004ae19  mov     eax, [rbp+var_48]
0x18004ae1c  mov     [rbp+var_50], eax
0x18004ae1f  mov     [rbp+var_30], ecx
0x18004ae22  mov     ecx, [rbp+var_50]
0x18004ae25  mov     eax, [rbp+var_40]
0x18004ae28  and     ecx, eax
0x18004ae2a  mov     [rbp+var_50], ecx
0x18004ae2d  mov     edx, [rbp+var_50]
0x18004ae30  mov     eax, [rbp+var_30]
0x18004ae33  or      edx, eax
0x18004ae35  mov     eax, [rbp+var_18]
0x18004ae38  mov     [rbp+var_48], eax
0x18004ae3b  mov     eax, [rbp+var_20]
0x18004ae3e  mov     [rbp+var_38], eax
0x18004ae41  mov     eax, [rbp+var_48]
0x18004ae44  mov     [rbp+var_40], eax
0x18004ae47  mov     eax, [rbp+var_38]
0x18004ae4a  mov     [rbp+var_50], eax
0x18004ae4d  mov     ecx, [rbp+var_50]
0x18004ae50  mov     eax, [rbp+var_40]
0x18004ae53  xor     ecx, eax
0x18004ae55  mov     eax, [rbp+var_48]
0x18004ae58  mov     [rbp+var_50], eax
0x18004ae5b  mov     eax, [rbp+var_38]
0x18004ae5e  mov     [rbp+var_40], eax
0x18004ae61  mov     eax, [rbp+var_50]
0x18004ae64  mov     [rbp+var_30], eax
0x18004ae67  mov     eax, [rbp+var_40]
0x18004ae6a  mov     [rbp+var_50], eax
0x18004ae6d  mov     [rbp+var_28], ecx
0x18004ae70  mov     ecx, [rbp+var_50]
0x18004ae73  mov     eax, [rbp+var_30]
0x18004ae76  or      ecx, eax
0x18004ae78  mov     [rbp+var_50], ecx
0x18004ae7b  mov     eax, [rbp+var_50]
0x18004ae7e  not     eax
0x18004ae80  mov     [rbp+var_50], eax
0x18004ae83  mov     ecx, [rbp+var_50]
0x18004ae86  mov     eax, [rbp+var_28]
0x18004ae89  or      ecx, eax
0x18004ae8b  mov     eax, [rbp+var_20]
0x18004ae8e  not     ecx
0x18004ae90  add     edx, ecx
0x18004ae92  sub     edx, eax
0x18004ae94  mov     eax, [rbp+var_18]
0x18004ae97  sub     edx, eax
0x18004ae99  cmp     r8d, edx
0x18004ae9c  jz      loc_18004B2FA
0x18004aea2  movzx   eax, byte ptr [r9]
0x18004aea6  mov     [rbp+var_28], eax
0x18004aea9  mov     eax, [rbp+var_28]
0x18004aeac  imul    ecx, eax, 2B549Eh
0x18004aeb2  mov     [rbp+var_48], 27700048h
0x18004aeb9  mov     eax, [rbp+var_48]
0x18004aebc  mov     [rbp+var_40], eax
0x18004aebf  mov     [rbp+var_38], ecx
0x18004aec2  mov     eax, [rbp+var_38]
0x18004aec5  mov     [rbp+var_50], eax
0x18004aec8  mov     ecx, [rbp+var_50]
0x18004aecb  mov     eax, [rbp+var_40]
0x18004aece  or      ecx, eax
0x18004aed0  mov     eax, [rbp+var_48]
0x18004aed3  not     ecx
0x18004aed5  mov     [rbp+var_48], eax
0x18004aed8  mov     eax, [rbp+var_38]
0x18004aedb  mov     [rbp+var_38], eax
0x18004aede  mov     eax, [rbp+var_48]
0x18004aee1  mov     [rbp+var_40], eax
0x18004aee4  mov     eax, [rbp+var_38]
0x18004aee7  mov     [rbp+var_50], eax
0x18004aeea  mov     [rbp+var_10], ecx
0x18004aeed  mov     ecx, [rbp+var_50]
0x18004aef0  mov     eax, [rbp+var_40]
0x18004aef3  xor     ecx, eax
0x18004aef5  mov     eax, [rbp+var_48]
0x18004aef8  mov     [rbp+var_40], eax
0x18004aefb  mov     eax, [rbp+var_38]
0x18004aefe  mov     [rbp+var_50], eax
0x18004af01  mov     [rbp+var_30], ecx
0x18004af04  mov     ecx, [rbp+var_50]
0x18004af07  mov     eax, [rbp+var_40]
0x18004af0a  or      ecx, eax
0x18004af0c  not     ecx
0x18004af0e  mov     [rbp+var_48], 386h
0x18004af15  mov     [rbp+var_50], ecx
0x18004af18  mov     ecx, [rbp+var_50]
0x18004af1b  mov     eax, [rbp+var_30]
0x18004af1e  or      ecx, eax
0x18004af20  mov     eax, [rbp+var_10]
0x18004af23  not     ecx
0x18004af25  mov     [rbp+var_40], eax
0x18004af28  mov     [rbp+var_50], ecx
0x18004af2b  mov     eax, [rbp+var_50]
0x18004af2e  mov     [rbp+var_50], eax
0x18004af31  mov     ecx, [rbp+var_50]
0x18004af34  mov     eax, [rbp+var_40]
0x18004af37  or      ecx, eax
0x18004af39  mov     [rbp+var_50], ecx
0x18004af3c  mov     eax, [rbp+var_50]
0x18004af3f  not     eax
0x18004af41  mov     [rbp+var_38], eax
0x18004af44  mov     eax, [rbp+var_48]
0x18004af47  mov     [rbp+var_40], eax
0x18004af4a  mov     eax, [rbp+var_38]
0x18004af4d  mov     [rbp+var_50], eax
0x18004af50  mov     ecx, [rbp+var_50]
0x18004af53  mov     eax, [rbp+var_40]
0x18004af56  or      ecx, eax
0x18004af58  mov     eax, [rbp+var_48]
0x18004af5b  not     ecx
0x18004af5d  mov     [rbp+var_48], eax
0x18004af60  mov     eax, [rbp+var_38]
0x18004af63  mov     [rbp+var_38], eax
0x18004af66  mov     eax, [rbp+var_48]
0x18004af69  mov     [rbp+var_40], eax
0x18004af6c  mov     eax, [rbp+var_38]
0x18004af6f  mov     [rbp+var_50], eax
0x18004af72  mov     [rbp+var_10], ecx
0x18004af75  mov     ecx, [rbp+var_50]
0x18004af78  mov     eax, [rbp+var_40]
0x18004af7b  xor     ecx, eax
0x18004af7d  mov     eax, [rbp+var_48]
0x18004af80  mov     [rbp+var_40], eax
0x18004af83  mov     eax, [rbp+var_38]
0x18004af86  mov     [rbp+var_50], eax
0x18004af89  mov     [rbp+var_30], ecx
0x18004af8c  mov     ecx, [rbp+var_50]
0x18004af8f  mov     eax, [rbp+var_40]
0x18004af92  or      ecx, eax
0x18004af94  not     ecx
0x18004af96  mov     [rbp+var_48], 27700048h
0x18004af9d  mov     [rbp+var_50], ecx
0x18004afa0  mov     ecx, [rbp+var_50]
0x18004afa3  mov     eax, [rbp+var_30]
0x18004afa6  or      ecx, eax
0x18004afa8  mov     eax, [rbp+var_10]
0x18004afab  not     ecx
0x18004afad  mov     [rbp+var_40], eax
0x18004afb0  mov     [rbp+var_50], ecx
0x18004afb3  mov     eax, [rbp+var_50]
0x18004afb6  mov     [rbp+var_50], eax
0x18004afb9  mov     ecx, [rbp+var_50]
0x18004afbc  mov     eax, [rbp+var_40]
  ... truncated ...
```
