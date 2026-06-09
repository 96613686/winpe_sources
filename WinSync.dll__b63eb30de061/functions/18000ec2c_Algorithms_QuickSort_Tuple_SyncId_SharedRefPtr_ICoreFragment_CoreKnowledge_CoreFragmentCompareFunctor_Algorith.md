# Algorithms::QuickSort<Tuple<SyncId,SharedRefPtr<ICoreFragment>>,CoreKnowledge::CoreFragmentCompareFunctor,Algorithms::SwapFunctor<Tuple<SyncId,SharedRefPtr<ICoreFragment>>>>(Tuple<SyncId,SharedRefPtr<ICoreFragment>> *,ulong,CoreKnowledge::CoreFragmentCompareFunctor,Algorithms::SwapFunctor<Tuple<SyncId,SharedRefPtr<ICoreFragment>>>)

- ea: `0x18000ec2c`
- end: `0x18000ef99`
- name: `??$QuickSort@U?$Tuple@VSyncId@@V?$SharedRefPtr@UICoreFragment@@@@@@UCoreFragmentCompareFunctor@CoreKnowledge@@U?$SwapFunctor@U?$Tuple@VSyncId@@V?$SharedRefPtr@UICoreFragment@@@@@@@Algorithms@@@Algorithms@@SAXPEAU?$Tuple@VSyncId@@V?$SharedRefPtr@UICoreFragment@@@@@@KUCoreFragmentCompareFunctor@CoreKnowledge@@U?$SwapFunctor@U?$Tuple@VSyncId@@V?$SharedRefPtr@UICoreFragment@@@@@@@0@@Z`
- size: `877`
- prototype: `__int64 __fastcall(struct SyncId *, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000d6e0`
- `0x18001e6dc`

## callees

- `0x180008ab0`
- `0x18000c270`
- `0x18000ec2c`
- `0x18001e4a4`
- `0x18007ad80`
- `0x18008bc9c`
- `0x18008be94`
- `0x18009323e`
- `0x180093270`

## pseudocode

```c
__int64 __fastcall Algorithms::QuickSort<Tuple<SyncId,SharedRefPtr<ICoreFragment>>,CoreKnowledge::CoreFragmentCompareFunctor,Algorithms::SwapFunctor<Tuple<SyncId,SharedRefPtr<ICoreFragment>>>>(
        struct SyncId *a1,
        unsigned int a2)
{
  __int64 v2; // rbx
  __int64 result; // rax
  int v5; // r12d
  const struct SyncId *v6; // r15
  unsigned __int64 v7; // rax
  char *v8; // r14
  struct SyncId *v9; // rbx
  const struct SyncId *v10; // r13
  const struct SyncId *v11; // rsi
  struct SyncId *v12; // rax
  _BYTE v13[4]; // [rsp+20h] [rbp-E0h] BYREF
  int v14; // [rsp+24h] [rbp-DCh]
  __int64 v15; // [rsp+28h] [rbp-D8h]
  _BYTE v16[16]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v17[62]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v18[62]; // [rsp+230h] [rbp+130h] BYREF

  v2 = a2;
  memset_0(v17, 0, sizeof(v17));
  result = (__int64)memset_0(v18, 0, sizeof(v18));
  if ( (unsigned int)v2 >= 2 )
  {
    v5 = 0;
    v6 = (struct SyncId *)((char *)a1 + 24 * v2 - 24);
    while ( 1 )
    {
      while ( 1 )
      {
        v7 = -1431655765 * (unsigned int)((v6 - a1) >> 3) + 1;
        if ( (unsigned int)v7 <= 8 )
        {
          result = Algorithms::ShortSort<Tuple<SyncId,SharedRefPtr<ICoreFragment>>,CoreKnowledge::CoreFragmentCompareFunctor,Algorithms::SwapFunctor<Tuple<SyncId,SharedRefPtr<ICoreFragment>>>>(a1);
          goto LABEL_5;
        }
        v8 = (char *)a1 + 24 * (v7 >> 1);
        if ( (int)SyncId::Compare(a1, (const struct SyncId *)v8) > 0 )
        {
          v14 = *((_DWORD *)a1 + 1);
          v15 = *((_QWORD *)a1 + 1);
          SyncId::AddRef((SyncId *)v13);
          SharedRefPtr<IForgottenKnowledge>::SharedRefPtr<IForgottenKnowledge>(v16, (char *)a1 + 16);
          Tuple<SyncId,SharedRefPtr<ICoreFragment>>::operator=(a1, v8);
          Tuple<SyncId,SharedRefPtr<ICoreFragment>>::operator=(v8, v13);
          TableElement<SyncId,SharedRefPtr<ChangeUnitChangeWrapper>,DefaultHashTableContext>::~TableElement<SyncId,SharedRefPtr<ChangeUnitChangeWrapper>,DefaultHashTableContext>((SyncId *)v13);
        }
        if ( (int)SyncId::Compare(a1, v6) > 0 )
        {
          v14 = *((_DWORD *)a1 + 1);
          v15 = *((_QWORD *)a1 + 1);
          SyncId::AddRef((SyncId *)v13);
          SharedRefPtr<IForgottenKnowledge>::SharedRefPtr<IForgottenKnowledge>(v16, (char *)a1 + 16);
          Tuple<SyncId,SharedRefPtr<ICoreFragment>>::operator=(a1, v6);
          Tuple<SyncId,SharedRefPtr<ICoreFragment>>::operator=(v6, v13);
          TableElement<SyncId,SharedRefPtr<ChangeUnitChangeWrapper>,DefaultHashTableContext>::~TableElement<SyncId,SharedRefPtr<ChangeUnitChangeWrapper>,DefaultHashTableContext>((SyncId *)v13);
        }
        if ( (int)SyncId::Compare((const struct SyncId *)v8, v6) > 0 )
        {
          v14 = *((_DWORD *)v8 + 1);
          v15 = *((_QWORD *)v8 + 1);
          SyncId::AddRef((SyncId *)v13);
          SharedRefPtr<IForgottenKnowledge>::SharedRefPtr<IForgottenKnowledge>(v16, v8 + 16);
          Tuple<SyncId,SharedRefPtr<ICoreFragment>>::operator=(v8, v6);
          Tuple<SyncId,SharedRefPtr<ICoreFragment>>::operator=(v6, v13);
          TableElement<SyncId,SharedRefPtr<ChangeUnitChangeWrapper>,DefaultHashTableContext>::~TableElement<SyncId,SharedRefPtr<ChangeUnitChangeWrapper>,DefaultHashTableContext>((SyncId *)v13);
        }
        v9 = a1;
        v10 = v6;
        while ( 1 )
        {
          if ( v8 > (char *)v9 )
          {
            while ( 1 )
            {
              v9 = (struct SyncId *)((char *)v9 + 24);
              if ( v9 >= (struct SyncId *)v8 )
                break;
              if ( (int)SyncId::Compare(v9, (const struct SyncId *)v8) > 0 )
                goto LABEL_20;
            }
          }
          do
            v9 = (struct SyncId *)((char *)v9 + 24);
          while ( v9 <= v6 && (int)SyncId::Compare(v9, (const struct SyncId *)v8) <= 0 );
          do
          {
LABEL_20:
            v11 = v10;
            v10 = (const struct SyncId *)((char *)v10 - 24);
          }
          while ( v10 > (const struct SyncId *)v8 && (int)SyncId::Compare(v10, (const struct SyncId *)v8) > 0 );
          if ( v10 < v9 )
            break;
          v14 = *((_DWORD *)v9 + 1);
          v15 = *((_QWORD *)v9 + 1);
          SyncId::AddRef((SyncId *)v13);
          SharedRefPtr<IForgottenKnowledge>::SharedRefPtr<IForgottenKnowledge>(v16, (char *)v9 + 16);
          Tuple<SyncId,SharedRefPtr<ICoreFragment>>::operator=(v9, v10);
          Tuple<SyncId,SharedRefPtr<ICoreFragment>>::operator=(v10, v13);
          TableElement<SyncId,SharedRefPtr<ChangeUnitChangeWrapper>,DefaultHashTableContext>::~TableElement<SyncId,SharedRefPtr<ChangeUnitChangeWrapper>,DefaultHashTableContext>((SyncId *)v13);
          v12 = v9;
          if ( v8 != (char *)v10 )
            v12 = (struct SyncId *)v8;
          v8 = (char *)v12;
        }
        if ( v8 < (char *)v11 )
        {
          while ( 1 )
          {
            v11 = (const struct SyncId *)((char *)v11 - 24);
            if ( v11 <= (const struct SyncId *)v8 )
              break;
            if ( (unsigned int)SyncId::Compare(v11, (const struct SyncId *)v8) )
              goto LABEL_32;
          }
        }
        do
          v11 = (const struct SyncId *)((char *)v11 - 24);
        while ( v11 > a1 && !(unsigned int)SyncId::Compare(v11, (const struct SyncId *)v8) );
LABEL_32:
        result = 0xAAAAAAAAAAAAAAABuLL * ((v11 - a1) >> 3);
        if ( result >= (__int64)(0xAAAAAAAAAAAAAAABuLL * ((v6 - v9) >> 3)) )
          break;
        if ( v9 < v6 )
        {
          result = v5++;
          v17[result] = v9;
          v18[result] = v6;
        }
        if ( a1 >= v11 )
        {
LABEL_5:
          if ( --v5 < 0 )
            return result;
          a1 = (struct SyncId *)v17[v5];
          v6 = (const struct SyncId *)v18[v5];
        }
        else
        {
          v6 = v11;
        }
      }
      if ( a1 < v11 )
      {
        result = v5++;
        v17[result] = a1;
        v18[result] = v11;
      }
      if ( v9 >= v6 )
        goto LABEL_5;
      a1 = v9;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000ec2c  mov     [rsp-8+arg_10], rbx
0x18000ec31  push    rbp
0x18000ec32  push    rsi
0x18000ec33  push    rdi
0x18000ec34  push    r12
0x18000ec36  push    r13
0x18000ec38  push    r14
0x18000ec3a  push    r15
0x18000ec3c  lea     rbp, [rsp-330h]
0x18000ec44  sub     rsp, 430h
0x18000ec4b  mov     rax, cs:__security_cookie
0x18000ec52  xor     rax, rsp
0x18000ec55  mov     [rbp+360h+var_40], rax
0x18000ec5c  mov     ebx, edx
0x18000ec5e  mov     rdi, rcx
0x18000ec61  mov     esi, 1F0h
0x18000ec66  lea     rcx, [rsp+460h+var_420]; void *
0x18000ec6b  mov     r8d, esi; Size
0x18000ec6e  xor     edx, edx; Val
0x18000ec70  call    memset_0
0x18000ec75  mov     r8d, esi; Size
0x18000ec78  lea     rcx, [rbp+360h+var_230]; void *
0x18000ec7f  xor     edx, edx; Val
0x18000ec81  call    memset_0
0x18000ec86  cmp     ebx, 2
0x18000ec89  jb      loc_18000EF6F
0x18000ec8f  lea     r15, [rbx-1]
0x18000ec93  xor     r12d, r12d
0x18000ec96  lea     r15, [r15+r15*2]
0x18000ec9a  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18000eca4  lea     r15, [rdi+r15*8]
0x18000eca8  mov     rax, r15
0x18000ecab  mov     rcx, rdi; struct SyncId *
0x18000ecae  sub     rax, rdi
0x18000ecb1  sar     rax, 3
0x18000ecb5  imul    rax, rdx
0x18000ecb9  inc     eax
0x18000ecbb  cmp     eax, 8
0x18000ecbe  ja      short loc_18000ECEE
0x18000ecc0  mov     rdx, r15
0x18000ecc3  call    ??$ShortSort@U?$Tuple@VSyncId@@V?$SharedRefPtr@UICoreFragment@@@@@@UCoreFragmentCompareFunctor@CoreKnowledge@@U?$SwapFunctor@U?$Tuple@VSyncId@@V?$SharedRefPtr@UICoreFragment@@@@@@@Algorithms@@@Algorithms@@CAXPEAU?$Tuple@VSyncId@@V?$SharedRefPtr@UICoreFragment@@@@@@0UCoreFragmentCompareFunctor@CoreKnowledge@@U?$SwapFunctor@U?$Tuple@VSyncId@@V?$SharedRefPtr@UICoreFragment@@@@@@@0@@Z; Algorithms::ShortSort<Tuple<SyncId,SharedRefPtr<ICoreFragment>>,CoreKnowledge::CoreFragmentCompareFunctor,Algorithms::SwapFunctor<Tuple<SyncId,SharedRefPtr<ICoreFragment>>>>(Tuple<SyncId,SharedRefPtr<ICoreFragment>> *,Tuple<SyncId,SharedRefPtr<ICoreFragment>> *,CoreKnowledge::CoreFragmentCompareFunctor,Algorithms::SwapFunctor<Tuple<SyncId,SharedRefPtr<ICoreFragment>>>)
0x18000ecc8  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18000ecd2  sub     r12d, 1
0x18000ecd6  js      loc_18000EF6F
0x18000ecdc  movsxd  rax, r12d
0x18000ecdf  mov     rdi, [rsp+rax*8+460h+var_420]
0x18000ece4  mov     r15, [rbp+rax*8+360h+var_230]
0x18000ecec  jmp     short loc_18000ECA8
0x18000ecee  shr     rax, 1
0x18000ecf1  lea     rax, [rax+rax*2]
0x18000ecf5  lea     r14, [rdi+rax*8]
0x18000ecf9  mov     rdx, r14; struct SyncId *
0x18000ecfc  call    ?Compare@SyncId@@SAJAEBV1@0@Z; SyncId::Compare(SyncId const &,SyncId const &)
0x18000ed01  test    eax, eax
0x18000ed03  jle     short loc_18000ED4F
0x18000ed05  mov     eax, [rdi+4]
0x18000ed08  lea     rcx, [rsp+460h+var_440]; this
0x18000ed0d  mov     [rsp+460h+var_43C], eax
0x18000ed11  mov     rax, [rdi+8]
0x18000ed15  mov     [rsp+460h+var_438], rax
0x18000ed1a  call    ?AddRef@SyncId@@AEAAXXZ; SyncId::AddRef(void)
0x18000ed1f  lea     rdx, [rdi+10h]
0x18000ed23  lea     rcx, [rsp+460h+var_430]
0x18000ed28  call    ??0?$SharedRefPtr@UIForgottenKnowledge@@@@QEAA@AEBV0@@Z; SharedRefPtr<IForgottenKnowledge>::SharedRefPtr<IForgottenKnowledge>(SharedRefPtr<IForgottenKnowledge> const &)
0x18000ed2d  mov     rdx, r14
0x18000ed30  mov     rcx, rdi
0x18000ed33  call    ??4?$Tuple@VSyncId@@V?$SharedRefPtr@UICoreFragment@@@@@@QEAAAEAU0@AEBU0@@Z; Tuple<SyncId,SharedRefPtr<ICoreFragment>>::operator=(Tuple<SyncId,SharedRefPtr<ICoreFragment>> const &)
0x18000ed38  lea     rdx, [rsp+460h+var_440]
0x18000ed3d  mov     rcx, r14
0x18000ed40  call    ??4?$Tuple@VSyncId@@V?$SharedRefPtr@UICoreFragment@@@@@@QEAAAEAU0@AEBU0@@Z; Tuple<SyncId,SharedRefPtr<ICoreFragment>>::operator=(Tuple<SyncId,SharedRefPtr<ICoreFragment>> const &)
0x18000ed45  lea     rcx, [rsp+460h+var_440]; this
0x18000ed4a  call    ??1?$TableElement@VSyncId@@V?$SharedRefPtr@VChangeUnitChangeWrapper@@@@VDefaultHashTableContext@@@@QEAA@XZ; TableElement<SyncId,SharedRefPtr<ChangeUnitChangeWrapper>,DefaultHashTableContext>::~TableElement<SyncId,SharedRefPtr<ChangeUnitChangeWrapper>,DefaultHashTableContext>(void)
0x18000ed4f  mov     rdx, r15; struct SyncId *
0x18000ed52  mov     rcx, rdi; struct SyncId *
0x18000ed55  call    ?Compare@SyncId@@SAJAEBV1@0@Z; SyncId::Compare(SyncId const &,SyncId const &)
0x18000ed5a  test    eax, eax
0x18000ed5c  jle     short loc_18000EDA8
0x18000ed5e  mov     eax, [rdi+4]
0x18000ed61  lea     rcx, [rsp+460h+var_440]; this
0x18000ed66  mov     [rsp+460h+var_43C], eax
0x18000ed6a  mov     rax, [rdi+8]
0x18000ed6e  mov     [rsp+460h+var_438], rax
0x18000ed73  call    ?AddRef@SyncId@@AEAAXXZ; SyncId::AddRef(void)
0x18000ed78  lea     rdx, [rdi+10h]
0x18000ed7c  lea     rcx, [rsp+460h+var_430]
0x18000ed81  call    ??0?$SharedRefPtr@UIForgottenKnowledge@@@@QEAA@AEBV0@@Z; SharedRefPtr<IForgottenKnowledge>::SharedRefPtr<IForgottenKnowledge>(SharedRefPtr<IForgottenKnowledge> const &)
0x18000ed86  mov     rdx, r15
0x18000ed89  mov     rcx, rdi
0x18000ed8c  call    ??4?$Tuple@VSyncId@@V?$SharedRefPtr@UICoreFragment@@@@@@QEAAAEAU0@AEBU0@@Z; Tuple<SyncId,SharedRefPtr<ICoreFragment>>::operator=(Tuple<SyncId,SharedRefPtr<ICoreFragment>> const &)
0x18000ed91  lea     rdx, [rsp+460h+var_440]
0x18000ed96  mov     rcx, r15
0x18000ed99  call    ??4?$Tuple@VSyncId@@V?$SharedRefPtr@UICoreFragment@@@@@@QEAAAEAU0@AEBU0@@Z; Tuple<SyncId,SharedRefPtr<ICoreFragment>>::operator=(Tuple<SyncId,SharedRefPtr<ICoreFragment>> const &)
0x18000ed9e  lea     rcx, [rsp+460h+var_440]; this
0x18000eda3  call    ??1?$TableElement@VSyncId@@V?$SharedRefPtr@VChangeUnitChangeWrapper@@@@VDefaultHashTableContext@@@@QEAA@XZ; TableElement<SyncId,SharedRefPtr<ChangeUnitChangeWrapper>,DefaultHashTableContext>::~TableElement<SyncId,SharedRefPtr<ChangeUnitChangeWrapper>,DefaultHashTableContext>(void)
0x18000eda8  mov     rdx, r15; struct SyncId *
0x18000edab  mov     rcx, r14; struct SyncId *
0x18000edae  call    ?Compare@SyncId@@SAJAEBV1@0@Z; SyncId::Compare(SyncId const &,SyncId const &)
0x18000edb3  test    eax, eax
0x18000edb5  jle     short loc_18000EE02
0x18000edb7  mov     eax, [r14+4]
0x18000edbb  lea     rcx, [rsp+460h+var_440]; this
0x18000edc0  mov     [rsp+460h+var_43C], eax
0x18000edc4  mov     rax, [r14+8]
0x18000edc8  mov     [rsp+460h+var_438], rax
0x18000edcd  call    ?AddRef@SyncId@@AEAAXXZ; SyncId::AddRef(void)
0x18000edd2  lea     rdx, [r14+10h]
0x18000edd6  lea     rcx, [rsp+460h+var_430]
0x18000eddb  call    ??0?$SharedRefPtr@UIForgottenKnowledge@@@@QEAA@AEBV0@@Z; SharedRefPtr<IForgottenKnowledge>::SharedRefPtr<IForgottenKnowledge>(SharedRefPtr<IForgottenKnowledge> const &)
0x18000ede0  mov     rdx, r15
0x18000ede3  mov     rcx, r14
0x18000ede6  call    ??4?$Tuple@VSyncId@@V?$SharedRefPtr@UICoreFragment@@@@@@QEAAAEAU0@AEBU0@@Z; Tuple<SyncId,SharedRefPtr<ICoreFragment>>::operator=(Tuple<SyncId,SharedRefPtr<ICoreFragment>> const &)
0x18000edeb  lea     rdx, [rsp+460h+var_440]
0x18000edf0  mov     rcx, r15
0x18000edf3  call    ??4?$Tuple@VSyncId@@V?$SharedRefPtr@UICoreFragment@@@@@@QEAAAEAU0@AEBU0@@Z; Tuple<SyncId,SharedRefPtr<ICoreFragment>>::operator=(Tuple<SyncId,SharedRefPtr<ICoreFragment>> const &)
0x18000edf8  lea     rcx, [rsp+460h+var_440]; this
0x18000edfd  call    ??1?$TableElement@VSyncId@@V?$SharedRefPtr@VChangeUnitChangeWrapper@@@@VDefaultHashTableContext@@@@QEAA@XZ; TableElement<SyncId,SharedRefPtr<ChangeUnitChangeWrapper>,DefaultHashTableContext>::~TableElement<SyncId,SharedRefPtr<ChangeUnitChangeWrapper>,DefaultHashTableContext>(void)
0x18000ee02  mov     rbx, rdi
0x18000ee05  mov     r13, r15
0x18000ee08  cmp     r14, rbx
0x18000ee0b  jbe     short loc_18000EE27
0x18000ee0d  add     rbx, 18h
0x18000ee11  cmp     rbx, r14
0x18000ee14  jnb     short loc_18000EE27
0x18000ee16  mov     rdx, r14; struct SyncId *
0x18000ee19  mov     rcx, rbx; struct SyncId *
0x18000ee1c  call    ?Compare@SyncId@@SAJAEBV1@0@Z; SyncId::Compare(SyncId const &,SyncId const &)
0x18000ee21  test    eax, eax
0x18000ee23  jle     short loc_18000EE0D
0x18000ee25  jmp     short loc_18000EE3F
0x18000ee27  add     rbx, 18h
0x18000ee2b  cmp     rbx, r15
0x18000ee2e  ja      short loc_18000EE3F
0x18000ee30  mov     rdx, r14; struct SyncId *
0x18000ee33  mov     rcx, rbx; struct SyncId *
0x18000ee36  call    ?Compare@SyncId@@SAJAEBV1@0@Z; SyncId::Compare(SyncId const &,SyncId const &)
0x18000ee3b  test    eax, eax
0x18000ee3d  jle     short loc_18000EE27
0x18000ee3f  mov     rsi, r13
0x18000ee42  sub     r13, 18h
0x18000ee46  cmp     r13, r14
0x18000ee49  jbe     short loc_18000EE5A
0x18000ee4b  mov     rdx, r14; struct SyncId *
0x18000ee4e  mov     rcx, r13; struct SyncId *
0x18000ee51  call    ?Compare@SyncId@@SAJAEBV1@0@Z; SyncId::Compare(SyncId const &,SyncId const &)
0x18000ee56  test    eax, eax
0x18000ee58  jg      short loc_18000EE3F
0x18000ee5a  cmp     r13, rbx
0x18000ee5d  jb      short loc_18000EEBB
0x18000ee5f  mov     eax, [rbx+4]
0x18000ee62  lea     rcx, [rsp+460h+var_440]; this
0x18000ee67  mov     [rsp+460h+var_43C], eax
0x18000ee6b  mov     rax, [rbx+8]
0x18000ee6f  mov     [rsp+460h+var_438], rax
0x18000ee74  call    ?AddRef@SyncId@@AEAAXXZ; SyncId::AddRef(void)
0x18000ee79  lea     rdx, [rbx+10h]
0x18000ee7d  lea     rcx, [rsp+460h+var_430]
0x18000ee82  call    ??0?$SharedRefPtr@UIForgottenKnowledge@@@@QEAA@AEBV0@@Z; SharedRefPtr<IForgottenKnowledge>::SharedRefPtr<IForgottenKnowledge>(SharedRefPtr<IForgottenKnowledge> const &)
0x18000ee87  mov     rdx, r13
0x18000ee8a  mov     rcx, rbx
0x18000ee8d  call    ??4?$Tuple@VSyncId@@V?$SharedRefPtr@UICoreFragment@@@@@@QEAAAEAU0@AEBU0@@Z; Tuple<SyncId,SharedRefPtr<ICoreFragment>>::operator=(Tuple<SyncId,SharedRefPtr<ICoreFragment>> const &)
0x18000ee92  lea     rdx, [rsp+460h+var_440]
0x18000ee97  mov     rcx, r13
0x18000ee9a  call    ??4?$Tuple@VSyncId@@V?$SharedRefPtr@UICoreFragment@@@@@@QEAAAEAU0@AEBU0@@Z; Tuple<SyncId,SharedRefPtr<ICoreFragment>>::operator=(Tuple<SyncId,SharedRefPtr<ICoreFragment>> const &)
0x18000ee9f  lea     rcx, [rsp+460h+var_440]; this
0x18000eea4  call    ??1?$TableElement@VSyncId@@V?$SharedRefPtr@VChangeUnitChangeWrapper@@@@VDefaultHashTableContext@@@@QEAA@XZ; TableElement<SyncId,SharedRefPtr<ChangeUnitChangeWrapper>,DefaultHashTableContext>::~TableElement<SyncId,SharedRefPtr<ChangeUnitChangeWrapper>,DefaultHashTableContext>(void)
0x18000eea9  cmp     r14, r13
0x18000eeac  mov     rax, rbx
0x18000eeaf  cmovnz  rax, r14
0x18000eeb3  mov     r14, rax
0x18000eeb6  jmp     loc_18000EE08
0x18000eebb  cmp     r14, rsi
0x18000eebe  jnb     short loc_18000EEDA
0x18000eec0  sub     rsi, 18h
0x18000eec4  cmp     rsi, r14
0x18000eec7  jbe     short loc_18000EEDA
0x18000eec9  mov     rdx, r14; struct SyncId *
0x18000eecc  mov     rcx, rsi; struct SyncId *
0x18000eecf  call    ?Compare@SyncId@@SAJAEBV1@0@Z; SyncId::Compare(SyncId const &,SyncId const &)
0x18000eed4  test    eax, eax
0x18000eed6  jz      short loc_18000EEC0
0x18000eed8  jmp     short loc_18000EEF2
0x18000eeda  sub     rsi, 18h
0x18000eede  cmp     rsi, rdi
0x18000eee1  jbe     short loc_18000EEF2
0x18000eee3  mov     rdx, r14; struct SyncId *
0x18000eee6  mov     rcx, rsi; struct SyncId *
0x18000eee9  call    ?Compare@SyncId@@SAJAEBV1@0@Z; SyncId::Compare(SyncId const &,SyncId const &)
0x18000eeee  test    eax, eax
0x18000eef0  jz      short loc_18000EEDA
0x18000eef2  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18000eefc  mov     rcx, r15
0x18000eeff  sub     rcx, rbx
0x18000ef02  mov     rax, rsi
0x18000ef05  sub     rax, rdi
0x18000ef08  sar     rcx, 3
0x18000ef0c  sar     rax, 3
0x18000ef10  imul    rcx, rdx
0x18000ef14  imul    rax, rdx
0x18000ef18  cmp     rax, rcx
0x18000ef1b  jl      short loc_18000EF46
0x18000ef1d  cmp     rdi, rsi
0x18000ef20  jnb     short loc_18000EF35
0x18000ef22  movsxd  rax, r12d
0x18000ef25  inc     r12d
0x18000ef28  mov     [rsp+rax*8+460h+var_420], rdi
0x18000ef2d  mov     [rbp+rax*8+360h+var_230], rsi
0x18000ef35  cmp     rbx, r15
0x18000ef38  jnb     loc_18000ECD2
0x18000ef3e  mov     rdi, rbx
0x18000ef41  jmp     loc_18000ECA8
0x18000ef46  cmp     rbx, r15
0x18000ef49  jnb     short loc_18000EF5E
0x18000ef4b  movsxd  rax, r12d
0x18000ef4e  inc     r12d
0x18000ef51  mov     [rsp+rax*8+460h+var_420], rbx
0x18000ef56  mov     [rbp+rax*8+360h+var_230], r15
0x18000ef5e  cmp     rdi, rsi
0x18000ef61  jnb     loc_18000ECD2
0x18000ef67  mov     r15, rsi
0x18000ef6a  jmp     loc_18000ECA8
0x18000ef6f  mov     rcx, [rbp+360h+var_40]
0x18000ef76  xor     rcx, rsp; StackCookie
0x18000ef79  call    __security_check_cookie
0x18000ef7e  mov     rbx, [rsp+460h+arg_10]
0x18000ef86  add     rsp, 430h
0x18000ef8d  pop     r15
0x18000ef8f  pop     r14
0x18000ef91  pop     r13
0x18000ef93  pop     r12
0x18000ef95  pop     rdi
0x18000ef96  pop     rsi
0x18000ef97  pop     rbp
0x18000ef98  retn
```
