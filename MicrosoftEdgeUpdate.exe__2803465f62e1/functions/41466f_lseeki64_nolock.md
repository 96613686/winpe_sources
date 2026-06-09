# __lseeki64_nolock

- ea: `0x41466f`
- end: `0x41468a`
- name: `__lseeki64_nolock`
- size: `27`
- prototype: `DWORD __cdecl(int FileHandle, LARGE_INTEGER liDistanceToMove, DWORD dwMoveMethod)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x414012`

## callees

- `0x4145f3`

## pseudocode

```c
DWORD __cdecl _lseeki64_nolock(int FileHandle, LARGE_INTEGER liDistanceToMove, DWORD dwMoveMethod)
{
  return common_lseek_nolock<__int64>(FileHandle, liDistanceToMove, dwMoveMethod);
}

```

## disassembly

```asm
0x41466f  mov     edi, edi
0x414671  push    ebp
0x414672  mov     ebp, esp
0x414674  push    [ebp+dwMoveMethod]; dwMoveMethod
0x414677  push    dword ptr [ebp+liDistanceToMove+4]
0x41467a  push    dword ptr [ebp+liDistanceToMove]; liDistanceToMove
0x41467d  push    [ebp+FileHandle]; FileHandle
0x414680  call    ??$common_lseek_nolock@_J@@YA_JH_JH@Z
0x414685  add     esp, 10h
0x414688  pop     ebp
0x414689  retn
```
