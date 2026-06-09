# winUnlockReadLock

- ea: `0x1800067a8`
- end: `0x180006817`
- name: `winUnlockReadLock`
- size: `111`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800064b0`
- `0x180006820`

## callees

- `0x1800061e4`
- `0x1800067a8`
- `0x18000690c`
- `0x18009a010`

## string_xrefs

- `0x1800067f7`: `winUnlockReadLock`

## pseudocode

```c
__int64 __fastcall winUnlockReadLock(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v4; // ebx
  DWORD v6; // eax
  __int64 v7; // r9

  v4 = winUnlockFile(a1 + 16, (unsigned int)(dword_1800B561C + 2), a3, 510);
  if ( !v4 )
  {
    v6 = off_1800B3078();
    if ( v6 != 158 )
    {
      v7 = *(_QWORD *)(a1 + 48);
      *(_DWORD *)(a1 + 32) = v6;
      winLogErrorAtLine(2058, v6, (unsigned int)"winUnlockReadLock", v7, 49958);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800067a8  mov     [rsp+arg_0], rbx
0x1800067ad  push    rdi
0x1800067ae  sub     rsp, 30h
0x1800067b2  mov     edx, cs:dword_1800B561C
0x1800067b8  mov     rdi, rcx
0x1800067bb  add     edx, 2
0x1800067be  add     rcx, 10h
0x1800067c2  mov     r9d, 1FEh
0x1800067c8  call    winUnlockFile
0x1800067cd  mov     ebx, eax
0x1800067cf  test    eax, eax
0x1800067d1  jz      short loc_1800067E0
0x1800067d3  mov     eax, ebx
0x1800067d5  mov     rbx, [rsp+38h+arg_0]
0x1800067da  add     rsp, 30h
0x1800067de  pop     rdi
0x1800067df  retn
0x1800067e0  mov     rax, cs:off_1800B3078
0x1800067e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067ec  cmp     eax, 9Eh
0x1800067f1  jz      short loc_1800067D3
0x1800067f3  mov     r9, [rdi+30h]
0x1800067f7  lea     r8, aWinunlockreadl; "winUnlockReadLock"
0x1800067fe  mov     edx, eax
0x180006800  mov     [rdi+20h], eax
0x180006803  mov     ecx, 80Ah
0x180006808  mov     [rsp+38h+var_18], 0C326h
0x180006810  call    winLogErrorAtLine
0x180006815  jmp     short loc_1800067D3
```
