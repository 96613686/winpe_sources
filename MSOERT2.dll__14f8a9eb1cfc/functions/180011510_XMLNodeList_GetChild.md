# XMLNodeList_GetChild

- ea: `0x180011510`
- end: `0x180011548`
- name: `XMLNodeList_GetChild`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800116c0`

## callees

- `0x180011510`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall XMLNodeList_GetChild(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 result; // rax

  if ( !a1 || !a3 )
    return 2147942487LL;
  *a3 = 0;
  result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 56LL))(a1);
  if ( (_DWORD)result == 1 )
    return 2147943568LL;
  return result;
}

```

## disassembly

```asm
0x180011510  sub     rsp, 28h
0x180011514  test    rcx, rcx
0x180011517  jz      short loc_18001153E
0x180011519  test    r8, r8
0x18001151c  jz      short loc_18001153E
0x18001151e  mov     qword ptr [r8], 0
0x180011525  mov     rax, [rcx]
0x180011528  mov     rax, [rax+38h]
0x18001152c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011531  cmp     eax, 1
0x180011534  mov     ecx, 80070490h
0x180011539  cmovz   eax, ecx
0x18001153c  jmp     short loc_180011543
0x18001153e  mov     eax, 80070057h
0x180011543  add     rsp, 28h
0x180011547  retn
```
