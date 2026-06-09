# ___acrt_errno_map_os_error

- ea: `0x40ecad`
- end: `0x40ecd0`
- name: `___acrt_errno_map_os_error`
- size: `35`
- prototype: `int *__cdecl(unsigned int)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x40eda8`
- `0x40ee5a`
- `0x40f5c2`
- `0x40f6c4`
- `0x414672`
- `0x416861`
- `0x4176c5`

## callees

- `0x40ec6a`
- `0x40ecd0`
- `0x40ece3`

## pseudocode

```c
int *__cdecl __acrt_errno_map_os_error(unsigned int a1)
{
  int v1; // esi
  int *result; // eax

  *__doserrno() = a1;
  v1 = __acrt_errno_from_os_error(a1);
  result = _errno();
  *result = v1;
  return result;
}

```

## disassembly

```asm
0x40ecad  mov     edi, edi
0x40ecaf  push    ebp
0x40ecb0  mov     ebp, esp
0x40ecb2  push    esi
0x40ecb3  call    ___doserrno
0x40ecb8  mov     ecx, [ebp+arg_0]
0x40ecbb  push    ecx
0x40ecbc  mov     [eax], ecx
0x40ecbe  call    ___acrt_errno_from_os_error
0x40ecc3  pop     ecx
0x40ecc4  mov     esi, eax
0x40ecc6  call    __errno
0x40eccb  mov     [eax], esi
0x40eccd  pop     esi
0x40ecce  pop     ebp
0x40eccf  retn
```
