# bond::OutputMemoryStream<std::allocator<char>>::Write<uchar>(uchar const &)

- ea: `0x180011bcc`
- end: `0x180011bfb`
- name: `??$Write@E@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXAEBE@Z`
- size: `47`
- prototype: `char __fastcall(__int64, char *)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a018`
- `0x18000a0b8`
- `0x18000a158`
- `0x18000a2d0`
- `0x18000ca14`
- `0x18000ca6c`
- `0x18000ce80`
- `0x18000d334`
- `0x18000d4b8`
- `0x18000d66c`
- `0x180022850`

## callees

- `0x180011bcc`
- `0x18002271c`

## pseudocode

```c
char __fastcall bond::OutputMemoryStream<std::allocator<char>>::Write<unsigned char>(__int64 a1, char *a2)
{
  __int64 v2; // r9
  char result; // al

  v2 = *(unsigned int *)(a1 + 28);
  if ( v2 + (unsigned __int64)*(unsigned int *)(a1 + 32) + 1 > *(unsigned int *)(a1 + 24) )
    return bond::OutputMemoryStream<std::allocator<char>>::Write(a1, a2, 1);
  result = *a2;
  *(_BYTE *)(v2 + *(_QWORD *)(a1 + 48)) = *a2;
  ++*(_DWORD *)(a1 + 28);
  return result;
}

```

## disassembly

```asm
0x180011bcc  mov     r8d, [rcx+20h]
0x180011bd0  mov     r9d, [rcx+1Ch]
0x180011bd4  inc     r8
0x180011bd7  mov     eax, [rcx+18h]
0x180011bda  add     r8, r9
0x180011bdd  cmp     r8, rax
0x180011be0  ja      short loc_180011BF0
0x180011be2  mov     al, [rdx]
0x180011be4  mov     r8, [rcx+30h]
0x180011be8  mov     [r9+r8], al
0x180011bec  inc     dword ptr [rcx+1Ch]
0x180011bef  retn
0x180011bf0  mov     r8d, 1
0x180011bf6  jmp     ?Write@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXPEBXI@Z; bond::OutputMemoryStream<std::allocator<char>>::Write(void const *,uint)
```
