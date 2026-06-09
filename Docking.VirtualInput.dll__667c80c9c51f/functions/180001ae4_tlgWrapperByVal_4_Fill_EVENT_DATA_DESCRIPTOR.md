# _tlgWrapperByVal<4>::Fill(_EVENT_DATA_DESCRIPTOR *)

- ea: `0x180001ae4`
- end: `0x180001af3`
- name: `?Fill@?$_tlgWrapperByVal@$03@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z`
- size: `15`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180001db4`
- `0x180001e8c`
- `0x180002324`
- `0x1800023a0`
- `0x18000244c`
- `0x180002560`
- `0x180002f9c`

## pseudocode

```c
_QWORD *__fastcall _tlgWrapperByVal<4>::Fill(__int64 a1, _QWORD *a2)
{
  _QWORD *result; // rax

  *a2 = a1;
  result = a2;
  a2[1] = 4;
  return result;
}

```

## disassembly

```asm
0x180001ae4  mov     [rdx], rcx
0x180001ae7  mov     rax, rdx
0x180001aea  mov     qword ptr [rdx+8], 4
0x180001af2  retn
```
