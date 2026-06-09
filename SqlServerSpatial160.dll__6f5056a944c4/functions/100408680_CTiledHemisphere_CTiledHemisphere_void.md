# CTiledHemisphere::~CTiledHemisphere(void)

- ea: `0x100408680`
- end: `0x1004086b1`
- name: `??1CTiledHemisphere@@UEAA@XZ`
- size: `49`
- prototype: `void __fastcall(CTiledHemisphere *__hidden this)`
- caller_count: `25`
- callee_count: `1`
- tags: ``

## callers

- `0x10046c360`
- `0x10046c3ef`
- `0x10046c43e`
- `0x10046c4df`
- `0x10046c52e`
- `0x10046c646`
- `0x10046c695`
- `0x10046cc5b`
- `0x10046ccaa`
- `0x10046cd5b`
- `0x10046cdaa`
- `0x10046d0a1`
- `0x10046d0f0`
- `0x10046d51d`
- `0x10046d56c`
- `0x10046dac8`
- `0x10046db17`
- `0x10046e129`
- `0x10046e178`
- `0x100473285`
- `0x1004732d4`
- `0x1004733f1`
- `0x100473440`
- `0x10047490b`
- `0x10047495a`

## callees

- `0x100408510`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CTiledHemisphere::~CTiledHemisphere(CTiledHemisphere *this)
{
  *((_QWORD *)this + 36) = &IMglGeometrySink::`vftable';
  CTiledConverter::~CTiledConverter(this);
}

```

## disassembly

```asm
0x100408680  mov     [rsp+arg_0], rcx
0x100408685  sub     rsp, 38h
0x100408689  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x100408692  lea     rax, [rcx+120h]
0x100408699  mov     [rsp+38h+arg_8], rax
0x10040869e  lea     rdx, ??_7IMglGeometrySink@@6B@; const IMglGeometrySink::`vftable'
0x1004086a5  mov     [rax], rdx
0x1004086a8  add     rsp, 38h
0x1004086ac  jmp     ??1CTiledConverter@@UEAA@XZ; CTiledConverter::~CTiledConverter(void)
```
