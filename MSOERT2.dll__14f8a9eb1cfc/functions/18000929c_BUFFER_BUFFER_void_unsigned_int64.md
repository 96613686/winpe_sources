# BUFFER::BUFFER(void *,unsigned __int64)

- ea: `0x18000929c`
- end: `0x1800092cc`
- name: `??0BUFFER@@QEAA@PEAX_K@Z`
- size: `48`
- prototype: `BUFFER *__fastcall(BUFFER *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800092d4`
- `0x18000b390`
- `0x18001232c`

## callees

- `0x18000929c`

## pseudocode

```c
BUFFER *__fastcall BUFFER::BUFFER(BUFFER *this, _BYTE *a2, __int64 a3)
{
  __int64 v3; // r9
  _BYTE *v4; // rax
  BUFFER *result; // rax

  v3 = a3;
  *((_QWORD *)this + 1) = 0;
  v4 = a2;
  *(_QWORD *)this = 0;
  for ( *((_DWORD *)this + 4) = 0; v3; --v3 )
    *v4++ = 0;
  *(_QWORD *)this = a2;
  result = this;
  *((_QWORD *)this + 1) = a3;
  return result;
}

```

## disassembly

```asm
0x18000929c  xor     r10d, r10d
0x18000929f  mov     r9, r8
0x1800092a2  mov     [rcx+8], r10
0x1800092a6  mov     rax, rdx
0x1800092a9  mov     [rcx], r10
0x1800092ac  mov     [rcx+10h], r10d
0x1800092b0  test    r8, r8
0x1800092b3  jz      short loc_1800092C1
0x1800092b5  mov     [rax], r10b
0x1800092b8  inc     rax
0x1800092bb  sub     r9, 1
0x1800092bf  jnz     short loc_1800092B5
0x1800092c1  mov     [rcx], rdx
0x1800092c4  mov     rax, rcx
0x1800092c7  mov     [rcx+8], r8
0x1800092cb  retn
```
