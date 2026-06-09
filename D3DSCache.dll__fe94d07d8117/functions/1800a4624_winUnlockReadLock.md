# winUnlockReadLock

- ea: `0x1800a4624`
- end: `0x1800a4691`
- name: `winUnlockReadLock`
- size: `109`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800a3410`
- `0x1800a4540`

## callees

- `0x1800293d4`
- `0x18003747c`
- `0x1800a4624`
- `0x1800a8010`

## string_xrefs

- `0x1800a4666`: `winUnlockReadLock`

## pseudocode

```c
__int64 __fastcall winUnlockReadLock(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v4; // ebx
  DWORD v5; // eax
  __int64 v6; // r9

  v4 = winUnlockFile(a1 + 16, (unsigned int)(dword_1800C695C + 2), a3, 510);
  if ( !v4 )
  {
    v5 = off_1800C40C8();
    if ( v5 != 158 )
    {
      v6 = *(_QWORD *)(a1 + 48);
      *(_DWORD *)(a1 + 32) = v5;
      winLogErrorAtLine(2058, v5, (unsigned int)"winUnlockReadLock", v6, 49862);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800a4624  mov     [rsp+arg_0], rbx
0x1800a4629  push    rdi
0x1800a462a  sub     rsp, 30h
0x1800a462e  mov     edx, cs:dword_1800C695C
0x1800a4634  mov     rdi, rcx
0x1800a4637  add     edx, 2
0x1800a463a  add     rcx, 10h
0x1800a463e  mov     r9d, 1FEh
0x1800a4644  call    winUnlockFile
0x1800a4649  mov     ebx, eax
0x1800a464b  test    eax, eax
0x1800a464d  jnz     short loc_1800A4684
0x1800a464f  mov     rax, cs:off_1800C40C8
0x1800a4656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a465b  cmp     eax, 9Eh
0x1800a4660  jz      short loc_1800A4684
0x1800a4662  mov     r9, [rdi+30h]
0x1800a4666  lea     r8, aWinunlockreadl; "winUnlockReadLock"
0x1800a466d  mov     edx, eax
0x1800a466f  mov     [rdi+20h], eax
0x1800a4672  mov     ecx, 80Ah
0x1800a4677  mov     [rsp+38h+var_18], 0C2C6h
0x1800a467f  call    winLogErrorAtLine
0x1800a4684  mov     eax, ebx
0x1800a4686  mov     rbx, [rsp+38h+arg_0]
0x1800a468b  add     rsp, 30h
0x1800a468f  pop     rdi
0x1800a4690  retn
```
