# sub_1800EB3EC

- ea: `0x1800eb3ec`
- end: `0x1800eb417`
- name: `sub_1800EB3EC`
- size: `43`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180034120`
- `0x1800eb000`
- `0x1800f1760`
- `0x1800f2130`
- `0x1800f23b0`
- `0x1800f2430`

## callees

- `0x1800eb3ec`

## pseudocode

```c
__int64 __fastcall sub_1800EB3EC(_DWORD *a1, _DWORD *a2, unsigned int a3, _DWORD *a4, int a5)
{
  __int64 result; // rax

  *a4 = 4;
  if ( a3 < 4 )
    return 3221225507LL;
  result = 0;
  if ( a1 )
    *a1 = 4;
  if ( a2 )
    *a2 = a5;
  return result;
}

```

## disassembly

```asm
0x1800eb3ec  mov     r10d, 4
0x1800eb3f2  mov     [r9], r10d
0x1800eb3f5  cmp     r8d, r10d
0x1800eb3f8  jb      short loc_1800EB411
0x1800eb3fa  xor     eax, eax
0x1800eb3fc  test    rcx, rcx
0x1800eb3ff  jz      short loc_1800EB404
0x1800eb401  mov     [rcx], r10d
0x1800eb404  test    rdx, rdx
0x1800eb407  jz      short locret_1800EB40F
0x1800eb409  mov     ecx, [rsp+arg_20]
0x1800eb40d  mov     [rdx], ecx
0x1800eb40f  retn
0x1800eb411  mov     eax, 0C0000023h
0x1800eb416  retn
```
