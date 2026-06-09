# EdppClearToken

- ea: `0x140003e2c`
- end: `0x140003e8b`
- name: `EdppClearToken`
- size: `95`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14002cd1c`

## callees

- `0x140003c8c`
- `0x140006f40`

## pseudocode

```c
__int64 __fastcall EdppClearToken(__int64 a1, __int64 a2)
{
  int v4; // edx
  _QWORD v6[12]; // [rsp+40h] [rbp-68h] BYREF

  memset(v6, 0, sizeof(v6));
  v6[1] = a2;
  v6[6] = a1;
  return EdpPluginAction((unsigned int)v6, v4, 0, 0, 0);
}

```

## disassembly

```asm
0x140003e2c  mov     [rsp+arg_0], rbx
0x140003e31  push    rdi
0x140003e32  sub     rsp, 0A0h
0x140003e39  mov     rbx, rdx
0x140003e3c  mov     rdi, rcx
0x140003e3f  xor     edx, edx; Val
0x140003e41  lea     rcx, [rsp+0A8h+var_68]; void *
0x140003e46  lea     r8d, [rdx+60h]; Size
0x140003e4a  call    memset
0x140003e4f  xor     r9d, r9d
0x140003e52  mov     [rsp+0A8h+var_78], 2
0x140003e5a  xor     r8d, r8d
0x140003e5d  mov     [rsp+0A8h+var_60], rbx
0x140003e62  lea     rcx, [rsp+0A8h+var_68]
0x140003e67  mov     [rsp+0A8h+var_38], rdi
0x140003e6c  mov     [rsp+0A8h+var_88], 0
0x140003e74  call    EdpPluginAction
0x140003e79  mov     rbx, [rsp+0A8h+arg_0]
0x140003e81  add     rsp, 0A0h
0x140003e88  pop     rdi
0x140003e89  retn
```
