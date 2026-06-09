# _tlgDataDescInit<_tlgIndexSequence<3,0,1,2>>::Fill<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_EVENT_DATA_DESCRIPTOR *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800023a0`
- end: `0x180002444`
- name: `??$Fill@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgDataDescInit@U?$_tlgIndexSequence@$02$0A@$00$01@@@@SAXPEAU_EVENT_DATA_DESCRIPTOR@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@2@Z`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002c84`

## callees

- `0x180001ae4`
- `0x180001afc`
- `0x180001d64`

## pseudocode

```c
__int64 __fastcall _tlgDataDescInit<_tlgIndexSequence<3,0,1,2>>::Fill<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  _QWORD *v5; // [rsp+20h] [rbp-28h]
  _QWORD *v6; // [rsp+28h] [rbp-20h]
  __int64 v7; // [rsp+30h] [rbp-18h]

  v5 = _tlgWrapperByVal<4>::Fill(a4, (_QWORD *)(a1 + 32));
  v6 = _tlgWrapperByVal<4>::Fill(a3, (_QWORD *)(a1 + 16));
  v7 = _tlgWrapperByVal<8>::Fill(a2, a1);
  return _tlgDataDescInit<_tlgIndexSequence<3,0,1,2>>::EvaluateArgs<void *,void *,void *>(v7, v6, v5);
}

```

## disassembly

```asm
0x1800023a0  mov     [rsp+arg_18], r9
0x1800023a5  mov     [rsp+arg_10], r8
0x1800023aa  mov     [rsp+arg_8], rdx
0x1800023af  mov     [rsp+arg_0], rcx
0x1800023b4  sub     rsp, 48h
0x1800023b8  mov     eax, 10h
0x1800023bd  imul    rax, 2
0x1800023c1  mov     rcx, [rsp+48h+arg_0]
0x1800023c6  add     rcx, rax
0x1800023c9  mov     rax, rcx
0x1800023cc  mov     rdx, rax
0x1800023cf  mov     rcx, [rsp+48h+arg_18]
0x1800023d4  call    ?Fill@?$_tlgWrapperByVal@$03@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapperByVal<4>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x1800023d9  mov     [rsp+48h+var_28], rax
0x1800023de  mov     eax, 10h
0x1800023e3  imul    rax, 1
0x1800023e7  mov     rcx, [rsp+48h+arg_0]
0x1800023ec  add     rcx, rax
0x1800023ef  mov     rax, rcx
0x1800023f2  mov     rdx, rax
0x1800023f5  mov     rcx, [rsp+48h+arg_10]
0x1800023fa  call    ?Fill@?$_tlgWrapperByVal@$03@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapperByVal<4>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x1800023ff  mov     [rsp+48h+var_20], rax
0x180002404  mov     eax, 10h
0x180002409  imul    rax, 0
0x18000240d  mov     rcx, [rsp+48h+arg_0]
0x180002412  add     rcx, rax
0x180002415  mov     rax, rcx
0x180002418  mov     rdx, rax
0x18000241b  mov     rcx, [rsp+48h+arg_8]
0x180002420  call    ?Fill@?$_tlgWrapperByVal@$07@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapperByVal<8>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x180002425  mov     [rsp+48h+var_18], rax
0x18000242a  mov     r8, [rsp+48h+var_28]
0x18000242f  mov     rdx, [rsp+48h+var_20]
0x180002434  mov     rcx, [rsp+48h+var_18]
0x180002439  call    ??$EvaluateArgs@PEAXPEAXPEAX@?$_tlgDataDescInit@U?$_tlgIndexSequence@$02$0A@$00$01@@@@CAXPEAX00@Z; _tlgDataDescInit<_tlgIndexSequence<3,0,1,2>>::EvaluateArgs<void *,void *,void *>(void *,void *,void *)
0x18000243e  nop
0x18000243f  add     rsp, 48h
0x180002443  retn
```
