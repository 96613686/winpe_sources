# __lseeki64_nolock

- ea: `0x1001ecab`
- end: `0x1001ecc6`
- name: `__lseeki64_nolock`
- size: `27`
- prototype: `int __cdecl(int FileHandle, LARGE_INTEGER liDistanceToMove, DWORD dwMoveMethod)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1001e585`

## callees

- `0x1001ec2d`

## pseudocode

```c
DWORD __cdecl _lseeki64_nolock(int FileHandle, LARGE_INTEGER liDistanceToMove, DWORD dwMoveMethod)
{
  return common_lseek_nolock<__int64>(FileHandle, liDistanceToMove, dwMoveMethod);
}

```

## disassembly

```asm
0x1001ecab  mov     edi, edi
0x1001ecad  push    ebp
0x1001ecae  mov     ebp, esp
0x1001ecb0  push    [ebp+dwMoveMethod]; dwMoveMethod
0x1001ecb3  push    dword ptr [ebp+liDistanceToMove+4]
0x1001ecb6  push    dword ptr [ebp+liDistanceToMove]; liDistanceToMove
0x1001ecb9  push    [ebp+FileHandle]; FileHandle
0x1001ecbc  call    ??$common_lseek_nolock@_J@@YA_JH_JH@Z
0x1001ecc1  add     esp, 10h
0x1001ecc4  pop     ebp
0x1001ecc5  retn
```
