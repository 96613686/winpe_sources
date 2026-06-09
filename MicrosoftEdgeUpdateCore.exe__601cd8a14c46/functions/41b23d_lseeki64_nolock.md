# __lseeki64_nolock

- ea: `0x41b23d`
- end: `0x41b258`
- name: `__lseeki64_nolock`
- size: `27`
- prototype: `DWORD __cdecl(int FileHandle, LARGE_INTEGER liDistanceToMove, DWORD dwMoveMethod)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x419037`

## callees

- `0x41b1c1`

## pseudocode

```c
DWORD __cdecl _lseeki64_nolock(int FileHandle, LARGE_INTEGER liDistanceToMove, DWORD dwMoveMethod)
{
  return common_lseek_nolock<__int64>(FileHandle, liDistanceToMove, dwMoveMethod);
}

```

## disassembly

```asm
0x41b23d  mov     edi, edi
0x41b23f  push    ebp
0x41b240  mov     ebp, esp
0x41b242  push    [ebp+dwMoveMethod]; dwMoveMethod
0x41b245  push    dword ptr [ebp+liDistanceToMove+4]
0x41b248  push    dword ptr [ebp+liDistanceToMove]; liDistanceToMove
0x41b24b  push    [ebp+FileHandle]; FileHandle
0x41b24e  call    ??$common_lseek_nolock@_J@@YA_JH_JH@Z
0x41b253  add     esp, 10h
0x41b256  pop     ebp
0x41b257  retn
```
