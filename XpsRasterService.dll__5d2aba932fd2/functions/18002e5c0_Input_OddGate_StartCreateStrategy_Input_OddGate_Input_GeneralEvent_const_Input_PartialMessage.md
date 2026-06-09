# Input::OddGate::StartCreateStrategy(Input::OddGate &,Input::GeneralEvent const &,Input::PartialMessage &)

- ea: `0x18002e5c0`
- end: `0x18002f1d8`
- name: `?StartCreateStrategy@OddGate@Input@@SAXAEAV12@AEBVGeneralEvent@2@AEAVPartialMessage@2@@Z`
- size: `3096`
- prototype: `void __fastcall(struct Input::OddGate *this, const struct Input::GeneralEvent *, struct Input::PartialMessage *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000e4b0`
- `0x18002d9f0`
- `0x18002e5c0`
- `0x1800bf3b0`

## pseudocode

```c
void __fastcall Input::OddGate::StartCreateStrategy(
        struct Input::OddGate *this,
        const struct Input::GeneralEvent *a2,
        struct Input::PartialMessage *a3)
{
  signed __int64 v4; // r9
  __int64 v7; // r8
  __int64 v8; // rcx
  unsigned int v9; // r10d
  int v10; // r11d
  _BYTE *v11; // rbx
  unsigned int v12; // eax
  unsigned int v13; // edx
  __int64 v14; // rcx
  bool v15; // sf
  void (__fastcall *MixedProvider)(_QWORD, unsigned __int64, __int64); // rax
  int v17; // [rsp+40h] [rbp-30h]
  int v18; // [rsp+48h] [rbp-28h]
  int v19; // [rsp+48h] [rbp-28h]
  int v20; // [rsp+48h] [rbp-28h]
  _BYTE *retaddr; // [rsp+A8h] [rbp+38h]

  v4 = (signed __int64)Input::OddGate::FormulateImportantQuality;
  v7 = ~(~(~(~((2003168 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality) & 0x18484200)
           ^ ((2003168 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality) | 0x18484200)
           | ~(~((2003168 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality) & 0x18484200)
             | (2003168 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality)
             | 0x18484200))
         & 0x133080)
       ^ (~(~((2003168 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality) & 0x18484200)
          ^ ((2003168 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality) | 0x18484200)
          | ~(~((2003168 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality) & 0x18484200)
            | (2003168 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality)
            | 0x18484200))
        | 0x133080)
       | ~(~(~(~((2003168 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality) & 0x18484200)
             ^ ((2003168 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality) | 0x18484200)
             | ~(~((2003168 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality) & 0x18484200)
               | (2003168 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality)
               | 0x18484200))
           & 0x133080)
         | ~(~((2003168 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality) & 0x18484200)
           ^ ((2003168 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality) | 0x18484200)
           | ~(~((2003168 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality) & 0x18484200)
             | (2003168 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality)
             | 0x18484200))
         | 0x133080u));
  if ( (_DWORD)v7 == ~((2003168 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality) ^ 0x185B7280
                     | ~((2003168 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality) | 0x185B7280))
                   + ((2003168 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality)
                    ^ 0x185B7280
                    ^ (2003168 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality)
                    & 0x185B7280
                    | ((2003168 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality)
                     ^ 0x185B7280)
                    & (2003168 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality)
                    & 0x185B7280)
                   - 2003168 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality
                   - 408646272 )
    goto LABEL_9;
  v7 = ~(~(~(~((3619297 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality) | 0x32412D09)
           | ~((3619297 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality) ^ 0x32412D09
             | ~((3619297 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality) | 0x32412D09)))
         | 0x280C0)
       | ~(~(~((3619297 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality) | 0x32412D09)
           | ~((3619297 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality) ^ 0x32412D09
             | ~((3619297 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality) | 0x32412D09)))
         ^ 0x280C0
         | ~(~(~((3619297 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality) | 0x32412D09)
             | ~((3619297 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality) ^ 0x32412D09
               | ~((3619297 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality) | 0x32412D09)))
           | 0x280C0u)));
  v17 = 3619297 * *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality;
  if ( (_DWORD)v7 != ~(~(~(v17 | 0x3243ADC9) | v17 & 0x3243ADC9) | ~(v17 | 0x3243ADC9))
                   + (~(~(v17 | 0x3243ADC9) | v17 & 0x3243ADC9) | ~(v17 ^ 0x3243ADC9 | ~(v17 | 0x3243ADC9)))
                   - v17
                   - 843296201 )
  {
    v19 = *(unsigned __int8 *)Input::OddGate::FormulateImportantQuality;
    v7 = ~(~(~(~((697348 * v19) | 0x9C0860C) | (697348 * v19) & 0x9C0860C) | 0x409A0)
         | ~(~((697348 * v19) | 0x9C0860C) | (697348 * v19) & 0x9C0860C) & 0x409A0u);
    if ( (_DWORD)v7 == ~((697348 * v19) ^ 0x9C48FAC | ~((697348 * v19) | 0x9C48FAC))
                     + ((697348 * v19) ^ 0x9C48FAC | (697348 * v19) & 0x9C48FAC)
                     - 697348 * v19
                     - 163876780 )
    {
      v14 = *((char *)Input::OddGate::FormulateImportantQuality + 1);
      v4 = (signed __int64)Input::OddGate::FormulateImportantQuality + 2;
      v15 = (v14 & 0x80u) != 0LL;
      if ( (char)v14 > 0 )
      {
        if ( v4 > 0x7FFFFFFFFFFFFFFFLL - v14 )
          goto LABEL_27;
        v15 = (v14 & 0x80u) != 0LL;
      }
      if ( !v15 || v4 >= (__int64)(0x8000000000000000uLL - v14) )
      {
        v20 = *(unsigned __int8 *)(v14 + v4);
        v7 = ~(~(~(~((3619297 * v20) | 0x2C021B40) | (3619297 * v20) & 0x2C021B40) | 0x40C)
             | ~(~((3619297 * v20) | 0x2C021B40) | (3619297 * v20) & 0x2C021B40) & 0x40Cu);
        if ( (_DWORD)v7 == ~((3619297 * v20) ^ 0x2C021F4C | ~((3619297 * v20) | 0x2C021F4C))
                         + ((3619297 * v20) ^ 0x2C021F4C | (3619297 * v20) & 0x2C021F4C)
                         - 3619297 * v20
                         - 738336588 )
          goto LABEL_9;
      }
    }
LABEL_27:
    v9 = IntegralRelation::OddMap;
    goto LABEL_10;
  }
  v8 = *(int *)((char *)Input::OddGate::FormulateImportantQuality + 1);
  v4 = (signed __int64)&loc_18002D9F5;
  if ( v8 <= 0 )
  {
    if ( v8 < 0 && (__int64)&loc_18002D9F5 < (__int64)(0x8000000000000000uLL - v8) )
      goto LABEL_27;
    goto LABEL_8;
  }
  if ( (__int64)&loc_18002D9F5 <= 0x7FFFFFFFFFFFFFFFLL - v8 )
  {
LABEL_8:
    v18 = *((unsigned __int8 *)&loc_18002D9F5 + v8);
    v7 = ~(~(~(~((2003168 * v18) | 0x18484200) | (2003168 * v18) & 0x18484200) | 0x133080)
         | ~(~((2003168 * v18) | 0x18484200) | (2003168 * v18) & 0x18484200) & 0x133080u);
    if ( (_DWORD)v7 == ~((2003168 * v18) ^ 0x185B7280 | ~((2003168 * v18) | 0x185B7280))
                     + ((2003168 * v18) ^ 0x185B7280 | (2003168 * v18) & 0x185B7280)
                     - 2003168 * v18
                     - 408646272 )
    {
LABEL_9:
      v9 = ++IntegralRelation::OddMap;
      goto LABEL_10;
    }
    goto LABEL_27;
  }
  v9 = IntegralRelation::OddMap;
LABEL_10:
  v10 = 0;
  LOBYTE(v4) = 1;
  v11 = 0;
  v12 = 676028;
  while ( 1 )
  {
    while ( v12 <= 0xB36FB )
    {
      switch ( v12 )
      {
        case 0xB36FBu:
          v12 = 735025;
          if ( (_BYTE)v4 != 1 )
            v12 = 1410982;
          break;
        case 0xA50BCu:
          LOBYTE(v4) = 0;
          v12 = 734971;
          break;
        case 0xA50CDu:
          v4 = (unsigned __int8)v4;
          v12 = 734971;
          if ( (v9 ^ 0xFB6715B9) == 0xA279EA )
            v12 = 10648042;
          else
            v4 = 1;
          break;
        default:
          v4 = (unsigned __int8)v4;
          v13 = (v9 ^ v10) / 0x7FC166;
          if ( *v11 == (_BYTE)v13 )
            v4 = 1;
          v12 = 734971;
          if ( *v11 != (_BYTE)v13 )
            v12 = 735025;
          break;
      }
    }
    if ( v12 == 735025 )
      break;
    if ( v12 == 1410982 )
    {
      v11 = retaddr;
      v12 = 676045;
    }
    else
    {
      v12 = 676099;
      v10 = -1643417317;
    }
  }
  if ( (_BYTE)v4 )
    IntegralRelation::OddMap = v9 + 1;
  MixedProvider = (void (__fastcall *)(_QWORD, unsigned __int64, __int64))GenerateMixedProvider(
                                                                            0xDF3FDFDF00E05020uLL,
                                                                            830742538,
                                                                            v7,
                                                                            v4);
  MixedProvider(
    Input::OddGate::StartCreateStrategy,
    (unsigned __int64)Input::OddGate::StartCreateStrategy ^ 0x15780B,
    358395);
  Input::OddGate::FormulateImportantQuality(this, a2, a3);
}

```

## disassembly

```asm
0x18002e5c0  mov     [rsp-38h+arg_18], rbx
0x18002e5c5  push    rbp
0x18002e5c6  push    rsi
0x18002e5c7  push    rdi
0x18002e5c8  push    r12
0x18002e5ca  push    r13
0x18002e5cc  push    r14
0x18002e5ce  push    r15
0x18002e5d0  mov     rbp, rsp
0x18002e5d3  sub     rsp, 70h
0x18002e5d7  mov     rdi, rcx
0x18002e5da  mov     [rbp+var_30], 18484200h
0x18002e5e1  lea     r9, ?FormulateImportantQuality@OddGate@Input@@QEAAXAEBVGeneralEvent@2@AEAVPartialMessage@2@@Z; Input::OddGate::FormulateImportantQuality(Input::GeneralEvent const &,Input::PartialMessage &)
0x18002e5e8  mov     r14, r8
0x18002e5eb  movzx   eax, byte ptr [r9]
0x18002e5ef  mov     rsi, rdx
0x18002e5f2  mov     [rbp+var_28], eax
0x18002e5f5  mov     eax, [rbp+var_28]
0x18002e5f8  imul    ecx, eax, 1E90E0h
0x18002e5fe  mov     eax, [rbp+var_30]
0x18002e601  mov     [rbp+var_48], eax
0x18002e604  mov     [rbp+var_20], ecx
0x18002e607  mov     eax, [rbp+var_20]
0x18002e60a  mov     [rbp+var_50], eax
0x18002e60d  mov     ecx, [rbp+var_50]
0x18002e610  mov     eax, [rbp+var_48]
0x18002e613  and     ecx, eax
0x18002e615  mov     eax, [rbp+var_30]
0x18002e618  not     ecx
0x18002e61a  mov     [rbp+var_48], eax
0x18002e61d  mov     eax, [rbp+var_20]
0x18002e620  mov     [rbp+var_50], eax
0x18002e623  mov     [rbp+var_10], ecx
0x18002e626  mov     ecx, [rbp+var_50]
0x18002e629  mov     eax, [rbp+var_48]
0x18002e62c  or      ecx, eax
0x18002e62e  mov     eax, [rbp+var_10]
0x18002e631  mov     [rbp+var_30], ecx
0x18002e634  mov     [rbp+var_48], eax
0x18002e637  mov     eax, [rbp+var_30]
0x18002e63a  mov     [rbp+var_50], eax
0x18002e63d  mov     ecx, [rbp+var_50]
0x18002e640  mov     eax, [rbp+var_48]
0x18002e643  xor     ecx, eax
0x18002e645  mov     eax, [rbp+var_10]
0x18002e648  mov     [rbp+var_48], eax
0x18002e64b  mov     eax, [rbp+var_30]
0x18002e64e  mov     [rbp+var_50], eax
0x18002e651  mov     [rbp+var_20], ecx
0x18002e654  mov     ecx, [rbp+var_50]
0x18002e657  mov     eax, [rbp+var_48]
0x18002e65a  or      ecx, eax
0x18002e65c  not     ecx
0x18002e65e  mov     [rbp+var_10], 133080h
0x18002e665  mov     [rbp+var_50], ecx
0x18002e668  mov     ecx, [rbp+var_50]
0x18002e66b  mov     eax, [rbp+var_20]
0x18002e66e  or      ecx, eax
0x18002e670  mov     eax, [rbp+var_10]
0x18002e673  not     ecx
0x18002e675  mov     [rbp+var_48], eax
0x18002e678  mov     [rbp+var_30], ecx
0x18002e67b  mov     eax, [rbp+var_30]
0x18002e67e  mov     [rbp+var_50], eax
0x18002e681  mov     ecx, [rbp+var_50]
0x18002e684  mov     eax, [rbp+var_48]
0x18002e687  and     ecx, eax
0x18002e689  mov     eax, [rbp+var_10]
0x18002e68c  not     ecx
0x18002e68e  mov     [rbp+var_48], eax
0x18002e691  mov     eax, [rbp+var_30]
0x18002e694  mov     [rbp+var_50], eax
0x18002e697  mov     [rbp+var_20], ecx
0x18002e69a  mov     ecx, [rbp+var_50]
0x18002e69d  mov     eax, [rbp+var_48]
0x18002e6a0  or      ecx, eax
0x18002e6a2  mov     eax, [rbp+var_20]
0x18002e6a5  mov     [rbp+var_48], eax
0x18002e6a8  mov     [rbp+var_10], ecx
0x18002e6ab  mov     eax, [rbp+var_10]
0x18002e6ae  mov     [rbp+var_50], eax
0x18002e6b1  mov     ecx, [rbp+var_50]
0x18002e6b4  mov     eax, [rbp+var_48]
0x18002e6b7  xor     ecx, eax
0x18002e6b9  mov     eax, [rbp+var_20]
0x18002e6bc  mov     [rbp+var_48], eax
0x18002e6bf  mov     eax, [rbp+var_10]
0x18002e6c2  mov     [rbp+var_50], eax
0x18002e6c5  mov     [rbp+var_30], ecx
0x18002e6c8  mov     ecx, [rbp+var_50]
0x18002e6cb  mov     eax, [rbp+var_48]
0x18002e6ce  or      ecx, eax
0x18002e6d0  mov     [rbp+var_10], 18484200h
0x18002e6d7  not     ecx
0x18002e6d9  mov     [rbp+var_50], ecx
0x18002e6dc  mov     r8d, [rbp+var_50]
0x18002e6e0  mov     eax, [rbp+var_30]
0x18002e6e3  or      r8d, eax
0x18002e6e6  mov     eax, [rbp+var_10]
0x18002e6e9  not     r8d
0x18002e6ec  mov     [rbp+var_48], eax
0x18002e6ef  mov     [rbp+var_30], 133080h
0x18002e6f6  mov     eax, [rbp+var_30]
0x18002e6f9  mov     [rbp+var_50], eax
0x18002e6fc  mov     ecx, [rbp+var_50]
0x18002e6ff  mov     eax, [rbp+var_48]
0x18002e702  and     ecx, eax
0x18002e704  mov     eax, [rbp+var_10]
0x18002e707  not     ecx
0x18002e709  mov     [rbp+var_48], eax
0x18002e70c  mov     eax, [rbp+var_30]
0x18002e70f  mov     [rbp+var_50], eax
0x18002e712  mov     [rbp+var_20], ecx
0x18002e715  mov     ecx, [rbp+var_50]
0x18002e718  mov     eax, [rbp+var_48]
0x18002e71b  or      ecx, eax
0x18002e71d  mov     eax, [rbp+var_20]
0x18002e720  mov     [rbp+var_48], eax
0x18002e723  mov     [rbp+var_10], ecx
0x18002e726  mov     eax, [rbp+var_10]
0x18002e729  mov     [rbp+var_50], eax
0x18002e72c  mov     ecx, [rbp+var_50]
0x18002e72f  mov     eax, [rbp+var_48]
0x18002e732  xor     ecx, eax
0x18002e734  mov     eax, [rbp+var_20]
0x18002e737  mov     [rbp+var_48], eax
0x18002e73a  mov     eax, [rbp+var_10]
0x18002e73d  mov     [rbp+var_50], eax
0x18002e740  mov     [rbp+var_30], ecx
0x18002e743  mov     ecx, [rbp+var_50]
0x18002e746  mov     eax, [rbp+var_48]
0x18002e749  or      ecx, eax
0x18002e74b  not     ecx
0x18002e74d  mov     [rbp+var_50], ecx
0x18002e750  mov     ecx, [rbp+var_50]
0x18002e753  mov     eax, [rbp+var_30]
0x18002e756  or      ecx, eax
0x18002e758  mov     eax, [rbp+var_28]
0x18002e75b  not     ecx
0x18002e75d  mov     [rbp+var_30], ecx
0x18002e760  imul    ecx, eax, 1E90E0h
0x18002e766  mov     eax, [rbp+var_30]
0x18002e769  mov     [rbp+var_28], eax
0x18002e76c  mov     [rbp+var_20], ecx
0x18002e76f  mov     eax, [rbp+var_20]
0x18002e772  mov     [rbp+var_10], eax
0x18002e775  mov     eax, [rbp+var_28]
0x18002e778  mov     [rbp+var_48], eax
0x18002e77b  mov     eax, [rbp+var_10]
0x18002e77e  mov     [rbp+var_50], eax
0x18002e781  mov     ecx, [rbp+var_50]
0x18002e784  mov     eax, [rbp+var_48]
0x18002e787  xor     ecx, eax
0x18002e789  mov     eax, [rbp+var_28]
0x18002e78c  mov     [rbp+var_28], eax
0x18002e78f  mov     eax, [rbp+var_10]
0x18002e792  mov     [rbp+var_50], eax
0x18002e795  mov     [rbp+var_48], ecx
0x18002e798  mov     ecx, [rbp+var_50]
0x18002e79b  mov     eax, [rbp+var_28]
0x18002e79e  and     ecx, eax
0x18002e7a0  mov     eax, [rbp+var_48]
0x18002e7a3  mov     [rbp+var_10], eax
0x18002e7a6  mov     [rbp+var_28], ecx
0x18002e7a9  mov     eax, [rbp+var_28]
0x18002e7ac  mov     [rbp+var_50], eax
0x18002e7af  mov     ecx, [rbp+var_50]
0x18002e7b2  mov     eax, [rbp+var_10]
0x18002e7b5  xor     ecx, eax
0x18002e7b7  mov     eax, [rbp+var_48]
0x18002e7ba  mov     [rbp+var_10], ecx
0x18002e7bd  mov     [rbp+var_48], eax
0x18002e7c0  mov     eax, [rbp+var_28]
0x18002e7c3  mov     [rbp+var_50], eax
0x18002e7c6  mov     ecx, [rbp+var_50]
0x18002e7c9  mov     eax, [rbp+var_48]
0x18002e7cc  and     ecx, eax
0x18002e7ce  mov     [rbp+var_50], ecx
0x18002e7d1  mov     edx, [rbp+var_50]
0x18002e7d4  mov     eax, [rbp+var_10]
0x18002e7d7  or      edx, eax
0x18002e7d9  mov     eax, [rbp+var_30]
0x18002e7dc  mov     [rbp+var_48], eax
0x18002e7df  mov     eax, [rbp+var_20]
0x18002e7e2  mov     [rbp+var_28], eax
0x18002e7e5  mov     eax, [rbp+var_48]
0x18002e7e8  mov     [rbp+var_10], eax
0x18002e7eb  mov     eax, [rbp+var_28]
0x18002e7ee  mov     [rbp+var_50], eax
0x18002e7f1  mov     ecx, [rbp+var_50]
0x18002e7f4  mov     eax, [rbp+var_10]
0x18002e7f7  xor     ecx, eax
0x18002e7f9  mov     eax, [rbp+var_48]
0x18002e7fc  mov     [rbp+var_50], eax
0x18002e7ff  mov     eax, [rbp+var_28]
0x18002e802  mov     [rbp+var_48], eax
0x18002e805  mov     eax, [rbp+var_50]
0x18002e808  mov     [rbp+var_28], eax
0x18002e80b  mov     eax, [rbp+var_48]
0x18002e80e  mov     [rbp+var_50], eax
0x18002e811  mov     [rbp+var_10], ecx
0x18002e814  mov     ecx, [rbp+var_50]
0x18002e817  mov     eax, [rbp+var_28]
0x18002e81a  or      ecx, eax
0x18002e81c  mov     [rbp+var_50], ecx
0x18002e81f  mov     eax, [rbp+var_50]
0x18002e822  not     eax
0x18002e824  mov     [rbp+var_50], eax
0x18002e827  mov     ecx, [rbp+var_50]
0x18002e82a  mov     eax, [rbp+var_10]
0x18002e82d  or      ecx, eax
0x18002e82f  mov     eax, [rbp+var_20]
0x18002e832  not     ecx
0x18002e834  add     edx, ecx
0x18002e836  sub     edx, eax
0x18002e838  mov     eax, [rbp+var_30]
0x18002e83b  sub     edx, eax
0x18002e83d  cmp     r8d, edx
0x18002e840  jz      loc_18002ED0A
0x18002e846  movzx   eax, byte ptr [r9]
0x18002e84a  mov     [rbp+var_10], eax
0x18002e84d  mov     eax, [rbp+var_10]
0x18002e850  imul    ecx, eax, 3739E1h
0x18002e856  mov     [rbp+var_48], 32412D09h
0x18002e85d  mov     eax, [rbp+var_48]
0x18002e860  mov     [rbp+var_50], eax
0x18002e863  mov     [rbp+var_28], ecx
0x18002e866  mov     eax, [rbp+var_28]
0x18002e869  mov     [rbp+var_30], eax
0x18002e86c  mov     eax, [rbp+var_50]
0x18002e86f  mov     [rbp+var_20], eax
0x18002e872  mov     eax, [rbp+var_30]
0x18002e875  mov     [rbp+var_50], eax
0x18002e878  mov     ecx, [rbp+var_50]
0x18002e87b  mov     eax, [rbp+var_20]
0x18002e87e  or      ecx, eax
0x18002e880  mov     [rbp+var_50], ecx
0x18002e883  mov     eax, [rbp+var_50]
0x18002e886  not     eax
0x18002e888  mov     [rbp+var_20], eax
0x18002e88b  mov     eax, [rbp+var_48]
0x18002e88e  mov     [rbp+var_48], eax
0x18002e891  mov     eax, [rbp+var_28]
0x18002e894  mov     [rbp+var_28], eax
0x18002e897  mov     eax, [rbp+var_48]
0x18002e89a  mov     [rbp+var_30], eax
0x18002e89d  mov     eax, [rbp+var_28]
0x18002e8a0  mov     [rbp+var_50], eax
0x18002e8a3  mov     ecx, [rbp+var_50]
0x18002e8a6  mov     eax, [rbp+var_30]
0x18002e8a9  xor     ecx, eax
0x18002e8ab  mov     eax, [rbp+var_48]
0x18002e8ae  mov     [rbp+var_48], eax
0x18002e8b1  mov     eax, [rbp+var_28]
0x18002e8b4  mov     [rbp+var_50], eax
0x18002e8b7  mov     [rbp+var_30], ecx
0x18002e8ba  mov     ecx, [rbp+var_50]
0x18002e8bd  mov     eax, [rbp+var_48]
0x18002e8c0  or      ecx, eax
0x18002e8c2  not     ecx
0x18002e8c4  mov     [rbp+var_48], 280C0h
0x18002e8cb  mov     [rbp+var_50], ecx
0x18002e8ce  mov     ecx, [rbp+var_50]
0x18002e8d1  mov     eax, [rbp+var_30]
0x18002e8d4  or      ecx, eax
0x18002e8d6  not     ecx
0x18002e8d8  mov     [rbp+var_50], ecx
0x18002e8db  mov     ecx, [rbp+var_50]
0x18002e8de  mov     eax, [rbp+var_20]
0x18002e8e1  or      ecx, eax
0x18002e8e3  mov     eax, [rbp+var_48]
0x18002e8e6  not     ecx
0x18002e8e8  mov     [rbp+var_50], eax
0x18002e8eb  mov     [rbp+var_28], ecx
0x18002e8ee  mov     eax, [rbp+var_28]
0x18002e8f1  mov     [rbp+var_30], eax
0x18002e8f4  mov     eax, [rbp+var_50]
0x18002e8f7  mov     [rbp+var_20], eax
0x18002e8fa  mov     eax, [rbp+var_30]
0x18002e8fd  mov     [rbp+var_50], eax
0x18002e900  mov     ecx, [rbp+var_50]
0x18002e903  mov     eax, [rbp+var_20]
0x18002e906  or      ecx, eax
0x18002e908  mov     [rbp+var_50], ecx
0x18002e90b  mov     eax, [rbp+var_50]
0x18002e90e  not     eax
0x18002e910  mov     [rbp+var_20], eax
0x18002e913  mov     eax, [rbp+var_48]
0x18002e916  mov     [rbp+var_48], eax
0x18002e919  mov     eax, [rbp+var_28]
0x18002e91c  mov     [rbp+var_28], eax
0x18002e91f  mov     eax, [rbp+var_48]
0x18002e922  mov     [rbp+var_30], eax
0x18002e925  mov     eax, [rbp+var_28]
0x18002e928  mov     [rbp+var_50], eax
0x18002e92b  mov     ecx, [rbp+var_50]
0x18002e92e  mov     eax, [rbp+var_30]
0x18002e931  xor     ecx, eax
0x18002e933  mov     eax, [rbp+var_48]
0x18002e936  mov     [rbp+var_30], ecx
  ... truncated ...
```
