# _tlgWrapperByVal<8>::Fill(_EVENT_DATA_DESCRIPTOR *)

- ea: `0x180001afc`
- end: `0x180001b0b`
- name: `?Fill@?$_tlgWrapperByVal@$07@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z`
- size: `15`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001e8c`
- `0x180002324`
- `0x1800023a0`
- `0x18000244c`
- `0x180002560`

## pseudocode

```c
_QWORD *__fastcall _tlgWrapperByVal<8>::Fill(__int64 a1, _QWORD *a2)
{
  _QWORD *result; // rax

  *a2 = a1;
  result = a2;
  a2[1] = 8;
  return result;
}

```

## disassembly

```asm
0x180001afc  mov     [rdx], rcx
0x180001aff  mov     rax, rdx
0x180001b02  mov     qword ptr [rdx+8], 8
0x180001b0a  retn
```
