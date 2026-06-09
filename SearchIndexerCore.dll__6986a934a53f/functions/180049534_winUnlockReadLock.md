# winUnlockReadLock

- ea: `0x180049534`
- end: `0x1800495a3`
- name: `winUnlockReadLock`
- size: `111`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180049270`
- `0x1800495b0`

## callees

- `0x18004909c`
- `0x180049534`
- `0x180049698`
- `0x1800b0010`

## string_xrefs

- `0x180049583`: `winUnlockReadLock`

## pseudocode

```c
__int64 __fastcall winUnlockReadLock(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v4; // ebx
  DWORD v6; // eax
  __int64 v7; // r9

  v4 = winUnlockFile(a1 + 16, (unsigned int)(dword_1800D085C + 2), a3, 510);
  if ( !v4 )
  {
    v6 = off_1800CE078();
    if ( v6 != 158 )
    {
      v7 = *(_QWORD *)(a1 + 48);
      *(_DWORD *)(a1 + 32) = v6;
      winLogErrorAtLine(2058, v6, (unsigned int)"winUnlockReadLock", v7, 49957);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180049534  mov     [rsp+arg_0], rbx
0x180049539  push    rdi
0x18004953a  sub     rsp, 30h
0x18004953e  mov     edx, cs:dword_1800D085C
0x180049544  mov     rdi, rcx
0x180049547  add     edx, 2
0x18004954a  add     rcx, 10h
0x18004954e  mov     r9d, 1FEh
0x180049554  call    winUnlockFile
0x180049559  mov     ebx, eax
0x18004955b  test    eax, eax
0x18004955d  jz      short loc_18004956C
0x18004955f  mov     eax, ebx
0x180049561  mov     rbx, [rsp+38h+arg_0]
0x180049566  add     rsp, 30h
0x18004956a  pop     rdi
0x18004956b  retn
0x18004956c  mov     rax, cs:off_1800CE078
0x180049573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049578  cmp     eax, 9Eh
0x18004957d  jz      short loc_18004955F
0x18004957f  mov     r9, [rdi+30h]
0x180049583  lea     r8, aWinunlockreadl; "winUnlockReadLock"
0x18004958a  mov     edx, eax
0x18004958c  mov     [rdi+20h], eax
0x18004958f  mov     ecx, 80Ah
0x180049594  mov     [rsp+38h+var_18], 0C325h
0x18004959c  call    winLogErrorAtLine
0x1800495a1  jmp     short loc_18004955F
```
