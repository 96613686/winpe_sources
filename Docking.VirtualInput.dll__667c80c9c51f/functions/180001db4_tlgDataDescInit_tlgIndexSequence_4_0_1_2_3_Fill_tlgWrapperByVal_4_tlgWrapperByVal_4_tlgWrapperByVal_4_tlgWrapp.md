# _tlgDataDescInit<_tlgIndexSequence<4,0,1,2,3>>::Fill<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_EVENT_DATA_DESCRIPTOR *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001db4`
- end: `0x180001e83`
- name: `??$Fill@U?$_tlgWrapperByVal@$03@@U1@U1@U1@@?$_tlgDataDescInit@U?$_tlgIndexSequence@$03$0A@$00$01$02@@@@SAXPEAU_EVENT_DATA_DESCRIPTOR@@AEBU?$_tlgWrapperByVal@$03@@111@Z`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000298c`

## callees

- `0x180001ae4`
- `0x180001d7c`

## pseudocode

```c

```

## disassembly

```asm
0x180001db4  mov     [rsp+arg_18], r9
0x180001db9  mov     [rsp+arg_10], r8
0x180001dbe  mov     [rsp+arg_8], rdx
0x180001dc3  mov     [rsp+arg_0], rcx
0x180001dc8  sub     rsp, 48h
0x180001dcc  mov     eax, 10h
0x180001dd1  imul    rax, 3
0x180001dd5  mov     rcx, [rsp+48h+arg_0]
0x180001dda  add     rcx, rax
0x180001ddd  mov     rax, rcx
0x180001de0  mov     rdx, rax
0x180001de3  mov     rcx, [rsp+48h+arg_20]
0x180001de8  call    ?Fill@?$_tlgWrapperByVal@$03@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapperByVal<4>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x180001ded  mov     [rsp+48h+var_28], rax
0x180001df2  mov     eax, 10h
0x180001df7  imul    rax, 2
0x180001dfb  mov     rcx, [rsp+48h+arg_0]
0x180001e00  add     rcx, rax
0x180001e03  mov     rax, rcx
0x180001e06  mov     rdx, rax
0x180001e09  mov     rcx, [rsp+48h+arg_18]
0x180001e0e  call    ?Fill@?$_tlgWrapperByVal@$03@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapperByVal<4>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x180001e13  mov     [rsp+48h+var_20], rax
0x180001e18  mov     eax, 10h
0x180001e1d  imul    rax, 1
0x180001e21  mov     rcx, [rsp+48h+arg_0]
0x180001e26  add     rcx, rax
0x180001e29  mov     rax, rcx
0x180001e2c  mov     rdx, rax
0x180001e2f  mov     rcx, [rsp+48h+arg_10]
0x180001e34  call    ?Fill@?$_tlgWrapperByVal@$03@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapperByVal<4>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x180001e39  mov     [rsp+48h+var_18], rax
0x180001e3e  mov     eax, 10h
0x180001e43  imul    rax, 0
0x180001e47  mov     rcx, [rsp+48h+arg_0]
0x180001e4c  add     rcx, rax
0x180001e4f  mov     rax, rcx
0x180001e52  mov     rdx, rax
0x180001e55  mov     rcx, [rsp+48h+arg_8]
0x180001e5a  call    ?Fill@?$_tlgWrapperByVal@$03@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapperByVal<4>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x180001e5f  mov     [rsp+48h+var_10], rax
0x180001e64  mov     r9, [rsp+48h+var_28]
0x180001e69  mov     r8, [rsp+48h+var_20]
0x180001e6e  mov     rdx, [rsp+48h+var_18]
0x180001e73  mov     rcx, [rsp+48h+var_10]
0x180001e78  call    ??$EvaluateArgs@PEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAXPEAX@?$_tlgDataDescInit@U?$_tlgIndexSequence@$0P@$0A@$00$01$02$03$04$05$06$07$08$09$0L@$0M@$0N@$0O@@@@@CAXPEAX00000000000000@Z; _tlgDataDescInit<_tlgIndexSequence<15,0,1,2,3,4,5,6,7,8,9,10,11,12,13,14>>::EvaluateArgs<void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *>(void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *)
0x180001e7d  nop
0x180001e7e  add     rsp, 48h
0x180001e82  retn
```
