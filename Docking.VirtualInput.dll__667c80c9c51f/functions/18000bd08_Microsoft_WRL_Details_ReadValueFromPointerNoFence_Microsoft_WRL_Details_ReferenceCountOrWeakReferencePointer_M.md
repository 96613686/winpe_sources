# Microsoft::WRL::Details::ReadValueFromPointerNoFence<Microsoft::WRL::Details::ReferenceCountOrWeakReferencePointer>(Microsoft::WRL::Details::ReferenceCountOrWeakReferencePointer const volatile *)

- ea: `0x18000bd08`
- end: `0x18000bd37`
- name: `??$ReadValueFromPointerNoFence@TReferenceCountOrWeakReferencePointer@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@YA?ATReferenceCountOrWeakReferencePointer@012@PEDT3012@@Z`
- size: `47`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000e6d0`
- `0x18000e890`
- `0x18000ebf8`
- `0x18000ecc4`
- `0x18000eee0`
- `0x18000efac`

## callees

- `0x180010560`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::ReadValueFromPointerNoFence<Microsoft::WRL::Details::ReferenceCountOrWeakReferencePointer>(
        Microsoft::WRL::Details *a1,
        const volatile unsigned __int64 *a2)
{
  return Microsoft::WRL::Details::ReadULong64NoFence(a1, a2);
}

```

## disassembly

```asm
0x18000bd08  mov     [rsp+arg_0], rcx
0x18000bd0d  sub     rsp, 38h
0x18000bd11  mov     rcx, [rsp+38h+arg_0]; this
0x18000bd16  call    ?ReadULong64NoFence@Details@WRL@Microsoft@@YA_JPED_K@Z; Microsoft::WRL::Details::ReadULong64NoFence(unsigned __int64 const volatile *)
0x18000bd1b  mov     [rsp+38h+var_18], rax
0x18000bd20  lea     rax, [rsp+38h+var_18]
0x18000bd25  mov     [rsp+38h+var_10], rax
0x18000bd2a  mov     rax, [rsp+38h+var_10]
0x18000bd2f  mov     rax, [rax]
0x18000bd32  add     rsp, 38h
0x18000bd36  retn
```
