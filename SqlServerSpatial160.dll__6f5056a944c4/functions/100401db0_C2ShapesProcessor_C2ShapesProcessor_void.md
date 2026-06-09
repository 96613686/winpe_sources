# C2ShapesProcessor::~C2ShapesProcessor(void)

- ea: `0x100401db0`
- end: `0x100401dd5`
- name: `??1C2ShapesProcessor@@UEAA@XZ`
- size: `37`
- prototype: `void __fastcall(C2ShapesProcessor *__hidden this)`
- caller_count: `26`
- callee_count: `1`
- tags: ``

## callers

- `0x10046a200`
- `0x10046a45f`
- `0x10046a50f`
- `0x10046abd4`
- `0x10046accd`
- `0x10046afdc`
- `0x10046b1b7`
- `0x10046c9dc`
- `0x10046ca77`
- `0x10046caf7`
- `0x10046cb2c`
- `0x10046cba8`
- `0x10046cbf8`
- `0x10046d399`
- `0x10046d408`
- `0x10046d48a`
- `0x10046d4ca`
- `0x10046d70d`
- `0x10046d77c`
- `0x10046ea40`
- `0x1004706a2`
- `0x10047078d`
- `0x100470878`
- `0x100470963`
- `0x100470a5b`
- `0x100472cb3`

## callees

- `0x100401900`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall C2ShapesProcessor::~C2ShapesProcessor(C2ShapesProcessor *this)
{
  *(_QWORD *)this = &C2ShapesProcessor::`vftable';
  CScanner::~CScanner(this);
}

```

## disassembly

```asm
0x100401db0  mov     [rsp+arg_0], rcx
0x100401db5  sub     rsp, 38h
0x100401db9  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x100401dc2  lea     rax, ??_7C2ShapesProcessor@@6B@; const C2ShapesProcessor::`vftable'
0x100401dc9  mov     [rcx], rax
0x100401dcc  add     rsp, 38h
0x100401dd0  jmp     ??1CScanner@@UEAA@XZ; CScanner::~CScanner(void)
```
