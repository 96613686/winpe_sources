# _tlgDataDescInit<_tlgIndexSequence<15,0,1,2,3,4,5,6,7,8,9,10,11,12,13,14>>::Fill<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_EVENT_DATA_DESCRIPTOR *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180002560`
- end: `0x1800028f9`
- name: `??$Fill@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgDataDescInit@U?$_tlgIndexSequence@$0P@$0A@$00$01$02$03$04$05$06$07$08$09$0L@$0M@$0N@$0O@@@@@SAXPEAU_EVENT_DATA_DESCRIPTOR@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@232AEBU?$_tlgWrapSz@G@@23234234@Z`
- size: `921`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180002e00`

## callees

- `0x180001a64`
- `0x180001aa0`
- `0x180001ae4`
- `0x180001afc`
- `0x180001d7c`

## pseudocode

```c
__int64 __fastcall _tlgDataDescInit<_tlgIndexSequence<15,0,1,2,3,4,5,6,7,8,9,10,11,12,13,14>>::Fill<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16)
{
  __int64 v16; // rax
  __int64 v18; // [rsp+80h] [rbp-88h]
  __int64 v19; // [rsp+88h] [rbp-80h]
  __int64 v20; // [rsp+90h] [rbp-78h]
  __int64 v21; // [rsp+98h] [rbp-70h]
  __int64 v22; // [rsp+A0h] [rbp-68h]
  __int64 v23; // [rsp+A8h] [rbp-60h]
  __int64 v24; // [rsp+B0h] [rbp-58h]
  __int64 v25; // [rsp+B8h] [rbp-50h]
  __int64 v26; // [rsp+C0h] [rbp-48h]
  __int64 v27; // [rsp+C8h] [rbp-40h]
  __int64 v28; // [rsp+D0h] [rbp-38h]
  __int64 v29; // [rsp+D8h] [rbp-30h]
  __int64 v30; // [rsp+E0h] [rbp-28h]
  __int64 v31; // [rsp+E8h] [rbp-20h]

  v18 = _tlgWrapSz<unsigned short>::Fill(a16, a1 + 224);
  v19 = _tlgWrapSz<char>::Fill(a15, a1 + 208);
  v20 = _tlgWrapperByVal<4>::Fill(a14, a1 + 192);
  v21 = _tlgWrapSz<unsigned short>::Fill(a13, a1 + 176);
  v22 = _tlgWrapSz<char>::Fill(a12, a1 + 160);
  v23 = _tlgWrapperByVal<4>::Fill(a11, a1 + 144);
  v24 = _tlgWrapSz<char>::Fill(a10, a1 + 128);
  v25 = _tlgWrapperByVal<4>::Fill(a9, a1 + 112);
  v26 = _tlgWrapSz<unsigned short>::Fill(a8, a1 + 96);
  v27 = _tlgWrapperByVal<4>::Fill(a7, a1 + 80);
  v28 = _tlgWrapSz<char>::Fill(a6, a1 + 64);
  v29 = _tlgWrapperByVal<4>::Fill(a5, a1 + 48);
  v30 = _tlgWrapSz<char>::Fill(a4, a1 + 32);
  v31 = _tlgWrapperByVal<4>::Fill(a3, a1 + 16);
  v16 = _tlgWrapperByVal<8>::Fill(a2, a1);
  return _tlgDataDescInit<_tlgIndexSequence<15,0,1,2,3,4,5,6,7,8,9,10,11,12,13,14>>::EvaluateArgs<void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *>(
           v16,
           v31,
           v30,
           v29,
           v28,
           v27,
           v26,
           v25,
           v24,
           v23,
           v22,
           v21,
           v20,
           v19,
           v18);
}

```

## disassembly

```asm
0x180002560  mov     [rsp+arg_18], r9
0x180002565  mov     [rsp+arg_10], r8
0x18000256a  mov     [rsp+arg_8], rdx
0x18000256f  mov     [rsp+arg_0], rcx
0x180002574  sub     rsp, 108h
0x18000257b  mov     eax, 10h
0x180002580  imul    rax, 0Eh
0x180002584  mov     rcx, [rsp+108h+arg_0]
0x18000258c  add     rcx, rax
0x18000258f  mov     rax, rcx
0x180002592  mov     rdx, rax
0x180002595  mov     rcx, [rsp+108h+arg_78]
0x18000259d  call    ?Fill@?$_tlgWrapSz@G@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapSz<ushort>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x1800025a2  mov     [rsp+108h+var_88], rax
0x1800025aa  mov     eax, 10h
0x1800025af  imul    rax, 0Dh
0x1800025b3  mov     rcx, [rsp+108h+arg_0]
0x1800025bb  add     rcx, rax
0x1800025be  mov     rax, rcx
0x1800025c1  mov     rdx, rax
0x1800025c4  mov     rcx, [rsp+108h+arg_70]
0x1800025cc  call    ?Fill@?$_tlgWrapSz@D@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapSz<char>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x1800025d1  mov     [rsp+108h+var_80], rax
0x1800025d9  mov     eax, 10h
0x1800025de  imul    rax, 0Ch
0x1800025e2  mov     rcx, [rsp+108h+arg_0]
0x1800025ea  add     rcx, rax
0x1800025ed  mov     rax, rcx
0x1800025f0  mov     rdx, rax
0x1800025f3  mov     rcx, [rsp+108h+arg_68]
0x1800025fb  call    ?Fill@?$_tlgWrapperByVal@$03@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapperByVal<4>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x180002600  mov     [rsp+108h+var_78], rax
0x180002608  mov     eax, 10h
0x18000260d  imul    rax, 0Bh
0x180002611  mov     rcx, [rsp+108h+arg_0]
0x180002619  add     rcx, rax
0x18000261c  mov     rax, rcx
0x18000261f  mov     rdx, rax
0x180002622  mov     rcx, [rsp+108h+arg_60]
0x18000262a  call    ?Fill@?$_tlgWrapSz@G@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapSz<ushort>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x18000262f  mov     [rsp+108h+var_70], rax
0x180002637  mov     eax, 10h
0x18000263c  imul    rax, 0Ah
0x180002640  mov     rcx, [rsp+108h+arg_0]
0x180002648  add     rcx, rax
0x18000264b  mov     rax, rcx
0x18000264e  mov     rdx, rax
0x180002651  mov     rcx, [rsp+108h+arg_58]
0x180002659  call    ?Fill@?$_tlgWrapSz@D@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapSz<char>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x18000265e  mov     [rsp+108h+var_68], rax
0x180002666  mov     eax, 10h
0x18000266b  imul    rax, 9
0x18000266f  mov     rcx, [rsp+108h+arg_0]
0x180002677  add     rcx, rax
0x18000267a  mov     rax, rcx
0x18000267d  mov     rdx, rax
0x180002680  mov     rcx, [rsp+108h+arg_50]
0x180002688  call    ?Fill@?$_tlgWrapperByVal@$03@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapperByVal<4>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x18000268d  mov     [rsp+108h+var_60], rax
0x180002695  mov     eax, 10h
0x18000269a  imul    rax, 8
0x18000269e  mov     rcx, [rsp+108h+arg_0]
0x1800026a6  add     rcx, rax
0x1800026a9  mov     rax, rcx
0x1800026ac  mov     rdx, rax
0x1800026af  mov     rcx, [rsp+108h+arg_48]
0x1800026b7  call    ?Fill@?$_tlgWrapSz@D@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapSz<char>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x1800026bc  mov     [rsp+108h+var_58], rax
0x1800026c4  mov     eax, 10h
0x1800026c9  imul    rax, 7
0x1800026cd  mov     rcx, [rsp+108h+arg_0]
0x1800026d5  add     rcx, rax
0x1800026d8  mov     rax, rcx
0x1800026db  mov     rdx, rax
0x1800026de  mov     rcx, [rsp+108h+arg_40]
0x1800026e6  call    ?Fill@?$_tlgWrapperByVal@$03@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapperByVal<4>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x1800026eb  mov     [rsp+108h+var_50], rax
0x1800026f3  mov     eax, 10h
0x1800026f8  imul    rax, 6
0x1800026fc  mov     rcx, [rsp+108h+arg_0]
0x180002704  add     rcx, rax
0x180002707  mov     rax, rcx
0x18000270a  mov     rdx, rax
0x18000270d  mov     rcx, [rsp+108h+arg_38]
0x180002715  call    ?Fill@?$_tlgWrapSz@G@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapSz<ushort>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x18000271a  mov     [rsp+108h+var_48], rax
0x180002722  mov     eax, 10h
0x180002727  imul    rax, 5
0x18000272b  mov     rcx, [rsp+108h+arg_0]
0x180002733  add     rcx, rax
0x180002736  mov     rax, rcx
0x180002739  mov     rdx, rax
0x18000273c  mov     rcx, [rsp+108h+arg_30]
0x180002744  call    ?Fill@?$_tlgWrapperByVal@$03@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapperByVal<4>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x180002749  mov     [rsp+108h+var_40], rax
0x180002751  mov     eax, 10h
0x180002756  imul    rax, 4
0x18000275a  mov     rcx, [rsp+108h+arg_0]
0x180002762  add     rcx, rax
0x180002765  mov     rax, rcx
0x180002768  mov     rdx, rax
0x18000276b  mov     rcx, [rsp+108h+arg_28]
0x180002773  call    ?Fill@?$_tlgWrapSz@D@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapSz<char>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x180002778  mov     [rsp+108h+var_38], rax
0x180002780  mov     eax, 10h
0x180002785  imul    rax, 3
0x180002789  mov     rcx, [rsp+108h+arg_0]
0x180002791  add     rcx, rax
0x180002794  mov     rax, rcx
0x180002797  mov     rdx, rax
0x18000279a  mov     rcx, [rsp+108h+arg_20]
0x1800027a2  call    ?Fill@?$_tlgWrapperByVal@$03@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapperByVal<4>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x1800027a7  mov     [rsp+108h+var_30], rax
0x1800027af  mov     eax, 10h
0x1800027b4  imul    rax, 2
0x1800027b8  mov     rcx, [rsp+108h+arg_0]
0x1800027c0  add     rcx, rax
0x1800027c3  mov     rax, rcx
0x1800027c6  mov     rdx, rax
0x1800027c9  mov     rcx, [rsp+108h+arg_18]
0x1800027d1  call    ?Fill@?$_tlgWrapSz@D@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapSz<char>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x1800027d6  mov     [rsp+108h+var_28], rax
0x1800027de  mov     eax, 10h
0x1800027e3  imul    rax, 1
0x1800027e7  mov     rcx, [rsp+108h+arg_0]
0x1800027ef  add     rcx, rax
0x1800027f2  mov     rax, rcx
0x1800027f5  mov     rdx, rax
0x1800027f8  mov     rcx, [rsp+108h+arg_10]
0x180002800  call    ?Fill@?$_tlgWrapperByVal@$03@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapperByVal<4>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x180002805  mov     [rsp+108h+var_20], rax
0x18000280d  mov     eax, 10h
0x180002812  imul    rax, 0
0x180002816  mov     rcx, [rsp+108h+arg_0]
0x18000281e  add     rcx, rax
0x180002821  mov     rax, rcx
0x180002824  mov     rdx, rax
0x180002827  mov     rcx, [rsp+108h+arg_8]
0x18000282f  call    ?Fill@?$_tlgWrapperByVal@$07@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapperByVal<8>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x180002834  mov     [rsp+108h+var_18], rax
0x18000283c  mov     rax, [rsp+108h+var_88]
0x180002844  mov     [rsp+108h+var_98], rax
0x180002849  mov     rax, [rsp+108h+var_80]
0x180002851  mov     [rsp+108h+var_A0], rax
0x180002856  mov     rax, [rsp+108h+var_78]
0x18000285e  mov     [rsp+108h+var_A8], rax
0x180002863  mov     rax, [rsp+108h+var_70]
0x18000286b  mov     [rsp+108h+var_B0], rax
0x180002870  mov     rax, [rsp+108h+var_68]
0x180002878  mov     [rsp+108h+var_B8], rax
0x18000287d  mov     rax, [rsp+108h+var_60]
0x180002885  mov     [rsp+108h+var_C0], rax
0x18000288a  mov     rax, [rsp+108h+var_58]
0x180002892  mov     [rsp+108h+var_C8], rax
0x180002897  mov     rax, [rsp+108h+var_50]
0x18000289f  mov     [rsp+108h+var_D0], rax
0x1800028a4  mov     rax, [rsp+108h+var_48]
0x1800028ac  mov     [rsp+108h+var_D8], rax
0x1800028b1  mov     rax, [rsp+108h+var_40]
0x1800028b9  mov     [rsp+108h+var_E0], rax
0x1800028be  mov     rax, [rsp+108h+var_38]
0x1800028c6  mov     [rsp+108h+var_E8], rax
0x1800028cb  mov     r9, [rsp+108h+var_30]
0x1800028d3  mov     r8, [rsp+108h+var_28]
0x1800028db  mov     rdx, [rsp+108h+var_20]
0x1800028e3  mov     rcx, [rsp+108h+var_18]
0x1800028eb  call    ??$EvaluateArgs@PEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAX@?$_tlgDataDescInit@U?$_tlgIndexSequence@$0P@$0A@$00$01$02$03$04$05$06$07$08$09$0L@$0M@$0N@$0O@@@@@CAXPEAX00000000000000@Z; _tlgDataDescInit<_tlgIndexSequence<15,0,1,2,3,4,5,6,7,8,9,10,11,12,13,14>>::EvaluateArgs<void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *>(void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *)
0x1800028f0  nop
0x1800028f1  add     rsp, 108h
0x1800028f8  retn
```
