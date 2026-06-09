# _tlgDataDescInit<_tlgIndexSequence<19,0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18>>::Fill<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_EVENT_DATA_DESCRIPTOR *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001e8c`
- end: `0x18000231e`
- name: `??$Fill@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgDataDescInit@U?$_tlgIndexSequence@$0BD@$0A@$00$01$02$03$04$05$06$07$08$09$0L@$0M@$0N@$0O@$0P@$0BA@$0BB@$0BC@@@@@SAXPEAU_EVENT_DATA_DESCRIPTOR@@AEBU?$_tlgWrapperByVal@$07@@1AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@232AEBU?$_tlgWrapSz@G@@23234234223@Z`
- size: `1170`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180002a48`

## callees

- `0x180001a64`
- `0x180001aa0`
- `0x180001ae4`
- `0x180001afc`
- `0x180001d7c`

## pseudocode

```c
__int64 __fastcall _tlgDataDescInit<_tlgIndexSequence<19,0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18>>::Fill<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
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
        __int64 a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        __int64 a20)
{
  __int64 v20; // rax
  __int64 v22; // [rsp+A0h] [rbp-A8h]
  __int64 v23; // [rsp+A8h] [rbp-A0h]
  __int64 v24; // [rsp+B0h] [rbp-98h]
  __int64 v25; // [rsp+B8h] [rbp-90h]
  __int64 v26; // [rsp+C0h] [rbp-88h]
  __int64 v27; // [rsp+C8h] [rbp-80h]
  __int64 v28; // [rsp+D0h] [rbp-78h]
  __int64 v29; // [rsp+D8h] [rbp-70h]
  __int64 v30; // [rsp+E0h] [rbp-68h]
  __int64 v31; // [rsp+E8h] [rbp-60h]
  __int64 v32; // [rsp+F0h] [rbp-58h]
  __int64 v33; // [rsp+F8h] [rbp-50h]
  __int64 v34; // [rsp+100h] [rbp-48h]
  __int64 v35; // [rsp+108h] [rbp-40h]
  __int64 v36; // [rsp+110h] [rbp-38h]
  __int64 v37; // [rsp+118h] [rbp-30h]
  __int64 v38; // [rsp+120h] [rbp-28h]
  __int64 v39; // [rsp+128h] [rbp-20h]

  v22 = _tlgWrapSz<char>::Fill(a20, a1 + 288);
  v23 = _tlgWrapperByVal<4>::Fill(a19, a1 + 272);
  v24 = _tlgWrapperByVal<4>::Fill(a18, a1 + 256);
  v25 = _tlgWrapSz<unsigned short>::Fill(a17, a1 + 240);
  v26 = _tlgWrapSz<char>::Fill(a16, a1 + 224);
  v27 = _tlgWrapperByVal<4>::Fill(a15, a1 + 208);
  v28 = _tlgWrapSz<unsigned short>::Fill(a14, a1 + 192);
  v29 = _tlgWrapSz<char>::Fill(a13, a1 + 176);
  v30 = _tlgWrapperByVal<4>::Fill(a12, a1 + 160);
  v31 = _tlgWrapSz<char>::Fill(a11, a1 + 144);
  v32 = _tlgWrapperByVal<4>::Fill(a10, a1 + 128);
  v33 = _tlgWrapSz<unsigned short>::Fill(a9, a1 + 112);
  v34 = _tlgWrapperByVal<4>::Fill(a8, a1 + 96);
  v35 = _tlgWrapSz<char>::Fill(a7, a1 + 80);
  v36 = _tlgWrapperByVal<4>::Fill(a6, a1 + 64);
  v37 = _tlgWrapSz<char>::Fill(a5, a1 + 48);
  v38 = _tlgWrapperByVal<4>::Fill(a4, a1 + 32);
  v39 = _tlgWrapperByVal<8>::Fill(a3, a1 + 16);
  v20 = _tlgWrapperByVal<8>::Fill(a2, a1);
  return _tlgDataDescInit<_tlgIndexSequence<15,0,1,2,3,4,5,6,7,8,9,10,11,12,13,14>>::EvaluateArgs<void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *>(
           v20,
           v39,
           v38,
           v37,
           v36,
           v35,
           v34,
           v33,
           v32,
           v31,
           v30,
           v29,
           v28,
           v27,
           v26,
           v25,
           v24,
           v23,
           v22);
}

```

## disassembly

```asm
0x180001e8c  mov     [rsp+arg_18], r9
0x180001e91  mov     [rsp+arg_10], r8
0x180001e96  mov     [rsp+arg_8], rdx
0x180001e9b  mov     [rsp+arg_0], rcx
0x180001ea0  sub     rsp, 148h
0x180001ea7  mov     eax, 10h
0x180001eac  imul    rax, 12h
0x180001eb0  mov     rcx, [rsp+148h+arg_0]
0x180001eb8  add     rcx, rax
0x180001ebb  mov     rax, rcx
0x180001ebe  mov     rdx, rax
0x180001ec1  mov     rcx, [rsp+148h+arg_98]
0x180001ec9  call    ?Fill@?$_tlgWrapSz@D@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapSz<char>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x180001ece  mov     [rsp+148h+var_A8], rax
0x180001ed6  mov     eax, 10h
0x180001edb  imul    rax, 11h
0x180001edf  mov     rcx, [rsp+148h+arg_0]
0x180001ee7  add     rcx, rax
0x180001eea  mov     rax, rcx
0x180001eed  mov     rdx, rax
0x180001ef0  mov     rcx, [rsp+148h+arg_90]
0x180001ef8  call    ?Fill@?$_tlgWrapperByVal@$03@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapperByVal<4>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x180001efd  mov     [rsp+148h+var_A0], rax
0x180001f05  mov     eax, 10h
0x180001f0a  imul    rax, 10h
0x180001f0e  mov     rcx, [rsp+148h+arg_0]
0x180001f16  add     rcx, rax
0x180001f19  mov     rax, rcx
0x180001f1c  mov     rdx, rax
0x180001f1f  mov     rcx, [rsp+148h+arg_88]
0x180001f27  call    ?Fill@?$_tlgWrapperByVal@$03@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapperByVal<4>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x180001f2c  mov     [rsp+148h+var_98], rax
0x180001f34  mov     eax, 10h
0x180001f39  imul    rax, 0Fh
0x180001f3d  mov     rcx, [rsp+148h+arg_0]
0x180001f45  add     rcx, rax
0x180001f48  mov     rax, rcx
0x180001f4b  mov     rdx, rax
0x180001f4e  mov     rcx, [rsp+148h+arg_80]
0x180001f56  call    ?Fill@?$_tlgWrapSz@G@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapSz<ushort>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x180001f5b  mov     [rsp+148h+var_90], rax
0x180001f63  mov     eax, 10h
0x180001f68  imul    rax, 0Eh
0x180001f6c  mov     rcx, [rsp+148h+arg_0]
0x180001f74  add     rcx, rax
0x180001f77  mov     rax, rcx
0x180001f7a  mov     rdx, rax
0x180001f7d  mov     rcx, [rsp+148h+arg_78]
0x180001f85  call    ?Fill@?$_tlgWrapSz@D@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapSz<char>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x180001f8a  mov     [rsp+148h+var_88], rax
0x180001f92  mov     eax, 10h
0x180001f97  imul    rax, 0Dh
0x180001f9b  mov     rcx, [rsp+148h+arg_0]
0x180001fa3  add     rcx, rax
0x180001fa6  mov     rax, rcx
0x180001fa9  mov     rdx, rax
0x180001fac  mov     rcx, [rsp+148h+arg_70]
0x180001fb4  call    ?Fill@?$_tlgWrapperByVal@$03@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapperByVal<4>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x180001fb9  mov     [rsp+148h+var_80], rax
0x180001fc1  mov     eax, 10h
0x180001fc6  imul    rax, 0Ch
0x180001fca  mov     rcx, [rsp+148h+arg_0]
0x180001fd2  add     rcx, rax
0x180001fd5  mov     rax, rcx
0x180001fd8  mov     rdx, rax
0x180001fdb  mov     rcx, [rsp+148h+arg_68]
0x180001fe3  call    ?Fill@?$_tlgWrapSz@G@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapSz<ushort>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x180001fe8  mov     [rsp+148h+var_78], rax
0x180001ff0  mov     eax, 10h
0x180001ff5  imul    rax, 0Bh
0x180001ff9  mov     rcx, [rsp+148h+arg_0]
0x180002001  add     rcx, rax
0x180002004  mov     rax, rcx
0x180002007  mov     rdx, rax
0x18000200a  mov     rcx, [rsp+148h+arg_60]
0x180002012  call    ?Fill@?$_tlgWrapSz@D@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapSz<char>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x180002017  mov     [rsp+148h+var_70], rax
0x18000201f  mov     eax, 10h
0x180002024  imul    rax, 0Ah
0x180002028  mov     rcx, [rsp+148h+arg_0]
0x180002030  add     rcx, rax
0x180002033  mov     rax, rcx
0x180002036  mov     rdx, rax
0x180002039  mov     rcx, [rsp+148h+arg_58]
0x180002041  call    ?Fill@?$_tlgWrapperByVal@$03@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapperByVal<4>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x180002046  mov     [rsp+148h+var_68], rax
0x18000204e  mov     eax, 10h
0x180002053  imul    rax, 9
0x180002057  mov     rcx, [rsp+148h+arg_0]
0x18000205f  add     rcx, rax
0x180002062  mov     rax, rcx
0x180002065  mov     rdx, rax
0x180002068  mov     rcx, [rsp+148h+arg_50]
0x180002070  call    ?Fill@?$_tlgWrapSz@D@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapSz<char>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x180002075  mov     [rsp+148h+var_60], rax
0x18000207d  mov     eax, 10h
0x180002082  imul    rax, 8
0x180002086  mov     rcx, [rsp+148h+arg_0]
0x18000208e  add     rcx, rax
0x180002091  mov     rax, rcx
0x180002094  mov     rdx, rax
0x180002097  mov     rcx, [rsp+148h+arg_48]
0x18000209f  call    ?Fill@?$_tlgWrapperByVal@$03@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapperByVal<4>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x1800020a4  mov     [rsp+148h+var_58], rax
0x1800020ac  mov     eax, 10h
0x1800020b1  imul    rax, 7
0x1800020b5  mov     rcx, [rsp+148h+arg_0]
0x1800020bd  add     rcx, rax
0x1800020c0  mov     rax, rcx
0x1800020c3  mov     rdx, rax
0x1800020c6  mov     rcx, [rsp+148h+arg_40]
0x1800020ce  call    ?Fill@?$_tlgWrapSz@G@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapSz<ushort>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x1800020d3  mov     [rsp+148h+var_50], rax
0x1800020db  mov     eax, 10h
0x1800020e0  imul    rax, 6
0x1800020e4  mov     rcx, [rsp+148h+arg_0]
0x1800020ec  add     rcx, rax
0x1800020ef  mov     rax, rcx
0x1800020f2  mov     rdx, rax
0x1800020f5  mov     rcx, [rsp+148h+arg_38]
0x1800020fd  call    ?Fill@?$_tlgWrapperByVal@$03@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapperByVal<4>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x180002102  mov     [rsp+148h+var_48], rax
0x18000210a  mov     eax, 10h
0x18000210f  imul    rax, 5
0x180002113  mov     rcx, [rsp+148h+arg_0]
0x18000211b  add     rcx, rax
0x18000211e  mov     rax, rcx
0x180002121  mov     rdx, rax
0x180002124  mov     rcx, [rsp+148h+arg_30]
0x18000212c  call    ?Fill@?$_tlgWrapSz@D@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapSz<char>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x180002131  mov     [rsp+148h+var_40], rax
0x180002139  mov     eax, 10h
0x18000213e  imul    rax, 4
0x180002142  mov     rcx, [rsp+148h+arg_0]
0x18000214a  add     rcx, rax
0x18000214d  mov     rax, rcx
0x180002150  mov     rdx, rax
0x180002153  mov     rcx, [rsp+148h+arg_28]
0x18000215b  call    ?Fill@?$_tlgWrapperByVal@$03@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapperByVal<4>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x180002160  mov     [rsp+148h+var_38], rax
0x180002168  mov     eax, 10h
0x18000216d  imul    rax, 3
0x180002171  mov     rcx, [rsp+148h+arg_0]
0x180002179  add     rcx, rax
0x18000217c  mov     rax, rcx
0x18000217f  mov     rdx, rax
0x180002182  mov     rcx, [rsp+148h+arg_20]
0x18000218a  call    ?Fill@?$_tlgWrapSz@D@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapSz<char>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x18000218f  mov     [rsp+148h+var_30], rax
0x180002197  mov     eax, 10h
0x18000219c  imul    rax, 2
0x1800021a0  mov     rcx, [rsp+148h+arg_0]
0x1800021a8  add     rcx, rax
0x1800021ab  mov     rax, rcx
0x1800021ae  mov     rdx, rax
0x1800021b1  mov     rcx, [rsp+148h+arg_18]
0x1800021b9  call    ?Fill@?$_tlgWrapperByVal@$03@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapperByVal<4>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x1800021be  mov     [rsp+148h+var_28], rax
0x1800021c6  mov     eax, 10h
0x1800021cb  imul    rax, 1
0x1800021cf  mov     rcx, [rsp+148h+arg_0]
0x1800021d7  add     rcx, rax
0x1800021da  mov     rax, rcx
0x1800021dd  mov     rdx, rax
0x1800021e0  mov     rcx, [rsp+148h+arg_10]
0x1800021e8  call    ?Fill@?$_tlgWrapperByVal@$07@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapperByVal<8>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x1800021ed  mov     [rsp+148h+var_20], rax
0x1800021f5  mov     eax, 10h
0x1800021fa  imul    rax, 0
0x1800021fe  mov     rcx, [rsp+148h+arg_0]
0x180002206  add     rcx, rax
0x180002209  mov     rax, rcx
0x18000220c  mov     rdx, rax
0x18000220f  mov     rcx, [rsp+148h+arg_8]
0x180002217  call    ?Fill@?$_tlgWrapperByVal@$07@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapperByVal<8>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x18000221c  mov     [rsp+148h+var_18], rax
0x180002224  mov     rax, [rsp+148h+var_A8]
0x18000222c  mov     [rsp+148h+var_B8], rax
0x180002234  mov     rax, [rsp+148h+var_A0]
0x18000223c  mov     [rsp+148h+var_C0], rax
0x180002244  mov     rax, [rsp+148h+var_98]
0x18000224c  mov     [rsp+148h+var_C8], rax
0x180002254  mov     rax, [rsp+148h+var_90]
0x18000225c  mov     [rsp+148h+var_D0], rax
0x180002261  mov     rax, [rsp+148h+var_88]
0x180002269  mov     [rsp+148h+var_D8], rax
0x18000226e  mov     rax, [rsp+148h+var_80]
0x180002276  mov     [rsp+148h+var_E0], rax
0x18000227b  mov     rax, [rsp+148h+var_78]
0x180002283  mov     [rsp+148h+var_E8], rax
0x180002288  mov     rax, [rsp+148h+var_70]
0x180002290  mov     [rsp+148h+var_F0], rax
0x180002295  mov     rax, [rsp+148h+var_68]
0x18000229d  mov     [rsp+148h+var_F8], rax
0x1800022a2  mov     rax, [rsp+148h+var_60]
0x1800022aa  mov     [rsp+148h+var_100], rax
0x1800022af  mov     rax, [rsp+148h+var_58]
0x1800022b7  mov     [rsp+148h+var_108], rax
0x1800022bc  mov     rax, [rsp+148h+var_50]
0x1800022c4  mov     [rsp+148h+var_110], rax
0x1800022c9  mov     rax, [rsp+148h+var_48]
0x1800022d1  mov     [rsp+148h+var_118], rax
0x1800022d6  mov     rax, [rsp+148h+var_40]
0x1800022de  mov     [rsp+148h+var_120], rax
0x1800022e3  mov     rax, [rsp+148h+var_38]
0x1800022eb  mov     [rsp+148h+var_128], rax
0x1800022f0  mov     r9, [rsp+148h+var_30]
0x1800022f8  mov     r8, [rsp+148h+var_28]
0x180002300  mov     rdx, [rsp+148h+var_20]
0x180002308  mov     rcx, [rsp+148h+var_18]
0x180002310  call    ??$EvaluateArgs@PEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAX@?$_tlgDataDescInit@U?$_tlgIndexSequence@$0P@$0A@$00$01$02$03$04$05$06$07$08$09$0L@$0M@$0N@$0O@@@@@CAXPEAX00000000000000@Z; _tlgDataDescInit<_tlgIndexSequence<15,0,1,2,3,4,5,6,7,8,9,10,11,12,13,14>>::EvaluateArgs<void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *>(void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *)
0x180002315  nop
0x180002316  add     rsp, 148h
0x18000231d  retn
```
