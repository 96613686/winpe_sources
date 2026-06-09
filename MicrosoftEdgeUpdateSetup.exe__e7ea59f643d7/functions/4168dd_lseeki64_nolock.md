# __lseeki64_nolock

- ea: `0x4168dd`
- end: `0x4168f8`
- name: `__lseeki64_nolock`
- size: `27`
- prototype: `DWORD __cdecl(int FileHandle, LARGE_INTEGER liDistanceToMove, DWORD dwMoveMethod)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x414672`

## callees

- `0x416861`

## pseudocode

```c
DWORD __cdecl _lseeki64_nolock(int FileHandle, LARGE_INTEGER liDistanceToMove, DWORD dwMoveMethod)
{
  return common_lseek_nolock<__int64>(FileHandle, liDistanceToMove, dwMoveMethod);
}

```

## disassembly

```asm
0x4168dd  mov     edi, edi
0x4168df  push    ebp
0x4168e0  mov     ebp, esp
0x4168e2  push    [ebp+dwMoveMethod]; dwMoveMethod
0x4168e5  push    dword ptr [ebp+liDistanceToMove+4]
0x4168e8  push    dword ptr [ebp+liDistanceToMove]; liDistanceToMove
0x4168eb  push    [ebp+FileHandle]; FileHandle
0x4168ee  call    ??$common_lseek_nolock@_J@@YA_JH_JH@Z
0x4168f3  add     esp, 10h
0x4168f6  pop     ebp
0x4168f7  retn
```
