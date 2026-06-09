# _tlgDataDescInit<_tlgIndexSequence<5,0,1,2,3,4>>::Fill<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_EVENT_DATA_DESCRIPTOR *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x18000244c`
- end: `0x180002557`
- name: `??$Fill@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgDataDescInit@U?$_tlgIndexSequence@$04$0A@$00$01$02$03@@@@SAXPEAU_EVENT_DATA_DESCRIPTOR@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180002d34`

## callees

- `0x180001a64`
- `0x180001aa0`
- `0x180001ae4`
- `0x180001afc`
- `0x180001d7c`

## pseudocode

```c

```

## disassembly

```asm
0x18000244c  mov     [rsp+arg_18], r9
0x180002451  mov     [rsp+arg_10], r8
0x180002456  mov     [rsp+arg_8], rdx
0x18000245b  mov     [rsp+arg_0], rcx
0x180002460  sub     rsp, 68h
0x180002464  mov     eax, 10h
0x180002469  imul    rax, 4
0x18000246d  mov     rcx, [rsp+68h+arg_0]
0x180002472  add     rcx, rax
0x180002475  mov     rax, rcx
0x180002478  mov     rdx, rax
0x18000247b  mov     rcx, [rsp+68h+arg_28]
0x180002483  call    ?Fill@?$_tlgWrapSz@G@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapSz<ushort>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x180002488  mov     [rsp+68h+var_38], rax
0x18000248d  mov     eax, 10h
0x180002492  imul    rax, 3
0x180002496  mov     rcx, [rsp+68h+arg_0]
0x18000249b  add     rcx, rax
0x18000249e  mov     rax, rcx
0x1800024a1  mov     rdx, rax
0x1800024a4  mov     rcx, [rsp+68h+arg_20]
0x1800024ac  call    ?Fill@?$_tlgWrapSz@D@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapSz<char>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x1800024b1  mov     [rsp+68h+var_30], rax
0x1800024b6  mov     eax, 10h
0x1800024bb  imul    rax, 2
0x1800024bf  mov     rcx, [rsp+68h+arg_0]
0x1800024c4  add     rcx, rax
0x1800024c7  mov     rax, rcx
0x1800024ca  mov     rdx, rax
0x1800024cd  mov     rcx, [rsp+68h+arg_18]
0x1800024d5  call    ?Fill@?$_tlgWrapperByVal@$03@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapperByVal<4>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x1800024da  mov     [rsp+68h+var_28], rax
0x1800024df  mov     eax, 10h
0x1800024e4  imul    rax, 1
0x1800024e8  mov     rcx, [rsp+68h+arg_0]
0x1800024ed  add     rcx, rax
0x1800024f0  mov     rax, rcx
0x1800024f3  mov     rdx, rax
0x1800024f6  mov     rcx, [rsp+68h+arg_10]
0x1800024fe  call    ?Fill@?$_tlgWrapperByVal@$03@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapperByVal<4>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x180002503  mov     [rsp+68h+var_20], rax
0x180002508  mov     eax, 10h
0x18000250d  imul    rax, 0
0x180002511  mov     rcx, [rsp+68h+arg_0]
0x180002516  add     rcx, rax
0x180002519  mov     rax, rcx
0x18000251c  mov     rdx, rax
0x18000251f  mov     rcx, [rsp+68h+arg_8]
0x180002524  call    ?Fill@?$_tlgWrapperByVal@$07@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapperByVal<8>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x180002529  mov     [rsp+68h+var_18], rax
0x18000252e  mov     rax, [rsp+68h+var_38]
0x180002533  mov     [rsp+68h+var_48], rax
0x180002538  mov     r9, [rsp+68h+var_30]
0x18000253d  mov     r8, [rsp+68h+var_28]
0x180002542  mov     rdx, [rsp+68h+var_20]
0x180002547  mov     rcx, [rsp+68h+var_18]
0x18000254c  call    ??$EvaluateArgs@PEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAX@?$_tlgDataDescInit@U?$_tlgIndexSequence@$0P@$0A@$00$01$02$03$04$05$06$07$08$09$0L@$0M@$0N@$0O@@@@@CAXPEAX00000000000000@Z; _tlgDataDescInit<_tlgIndexSequence<15,0,1,2,3,4,5,6,7,8,9,10,11,12,13,14>>::EvaluateArgs<void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *>(void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *)
0x180002551  nop
0x180002552  add     rsp, 68h
0x180002556  retn
```
