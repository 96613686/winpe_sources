# CNorthernHemisphere::~CNorthernHemisphere(void)

- ea: `0x1004086c0`
- end: `0x1004086f1`
- name: `??1CNorthernHemisphere@@UEAA@XZ`
- size: `49`
- prototype: `void __fastcall(CNorthernHemisphere *__hidden this)`
- caller_count: `25`
- callee_count: `1`
- tags: ``

## callers

- `0x100466ba0`
- `0x10046c3cc`
- `0x10046c3dc`
- `0x10046c4bc`
- `0x10046c4cc`
- `0x10046c623`
- `0x10046c633`
- `0x10046cc38`
- `0x10046cc48`
- `0x10046cd38`
- `0x10046cd48`
- `0x10046d07e`
- `0x10046d08e`
- `0x10046d4fa`
- `0x10046d50a`
- `0x10046daa5`
- `0x10046dab5`
- `0x10046e106`
- `0x10046e116`
- `0x100473262`
- `0x100473272`
- `0x1004733ce`
- `0x1004733de`
- `0x1004748e8`
- `0x1004748f8`

## callees

- `0x100408510`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CNorthernHemisphere::~CNorthernHemisphere(CNorthernHemisphere *this)
{
  *((_QWORD *)this + 36) = &IMglGeometrySink::`vftable';
  CTiledConverter::~CTiledConverter(this);
}

```

## disassembly

```asm
0x1004086c0  mov     [rsp+arg_0], rcx
0x1004086c5  sub     rsp, 38h
0x1004086c9  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1004086d2  lea     rax, [rcx+120h]
0x1004086d9  mov     [rsp+38h+arg_8], rax
0x1004086de  lea     rdx, ??_7IMglGeometrySink@@6B@; const IMglGeometrySink::`vftable'
0x1004086e5  mov     [rax], rdx
0x1004086e8  add     rsp, 38h
0x1004086ec  jmp     ??1CTiledConverter@@UEAA@XZ; CTiledConverter::~CTiledConverter(void)
```
