# atexit

- ea: `0x180013dac`
- end: `0x180013dc3`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x18000f340`
- `0x1800100b0`
- `0x180010350`
- `0x180010570`
- `0x1800105b0`
- `0x180010820`
- `0x1800109c0`
- `0x180010c20`

## callees

- `0x180013d10`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180013dac  sub     rsp, 28h
0x180013db0  call    _onexit_0
0x180013db5  neg     rax
0x180013db8  sbb     eax, eax
0x180013dba  neg     eax
0x180013dbc  dec     eax
0x180013dbe  add     rsp, 28h
0x180013dc2  retn
```
