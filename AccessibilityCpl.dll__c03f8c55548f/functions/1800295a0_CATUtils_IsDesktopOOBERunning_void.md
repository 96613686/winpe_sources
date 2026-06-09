# CATUtils::IsDesktopOOBERunning(void)

- ea: `0x1800295a0`
- end: `0x1800295cd`
- name: `?IsDesktopOOBERunning@CATUtils@@SA_NXZ`
- size: `45`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180023090`
- `0x1800295d4`

## callees

- `0x1800295a0`

## import_xrefs

- `KERNEL32!OOBEComplete` at `0x1800295b1`
- `KERNEL32!OOBEComplete` at `0x1800295b1`

## pseudocode

```c
bool CATUtils::IsDesktopOOBERunning(void)
{
  int v1; // [rsp+30h] [rbp+8h] BYREF

  v1 = 0;
  return (unsigned int)OOBEComplete(&v1) && !v1;
}

```

## disassembly

```asm
0x1800295a0  sub     rsp, 28h
0x1800295a4  lea     rcx, [rsp+28h+arg_0]
0x1800295a9  mov     [rsp+28h+arg_0], 0
0x1800295b1  call    cs:__imp_OOBEComplete
0x1800295b7  test    eax, eax
0x1800295b9  jz      short loc_1800295C6
0x1800295bb  cmp     [rsp+28h+arg_0], 0
0x1800295c0  jnz     short loc_1800295C6
0x1800295c2  mov     al, 1
0x1800295c4  jmp     short loc_1800295C8
0x1800295c6  xor     al, al
0x1800295c8  add     rsp, 28h
0x1800295cc  retn
```
