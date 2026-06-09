# AddStringTag

- ea: `0x180004420`
- end: `0x180004533`
- name: `AddStringTag`
- size: `275`
- prototype: `_BYTE *__fastcall(HANDLE hFile, LPCWCH lpWideCharStr, __int16, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180006bb0`

## callees

- `0x180004420`
- `0x18000f1c8`
- `0x18001716c`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x1800044da`
- `KERNEL32!SetFilePointer` at `0x1800044da`
- `KERNEL32!WriteFile` at `0x18000450a`
- `KERNEL32!WriteFile` at `0x18000450a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BYTE *__fastcall AddStringTag(HANDLE hFile, LPCWCH lpWideCharStr, __int16 a3, __int64 a4)
{
  _BYTE *result; // rax
  _BYTE *v8; // rsi
  __int64 v9; // r14
  __int64 v10; // rax
  unsigned __int64 v11; // rax
  __int64 v12; // rcx
  DWORD *v13; // rbx
  __int64 v14; // rax
  _BYTE *v15; // rdx
  DWORD *v16; // rax
  BOOL v17; // ebp
  DWORD v18; // eax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-48h] BYREF

  NumberOfBytesWritten = 0;
  result = (_BYTE *)UnicodeStringToAnsiString(lpWideCharStr);
  v8 = result;
  if ( result )
  {
    v9 = -1;
    *(_WORD *)a4 = a3;
    v10 = -1;
    *(_WORD *)(a4 + 2) = 2;
    do
      ++v10;
    while ( v8[v10] );
    *(_DWORD *)(a4 + 4) = v10 + 1;
    v11 = -1;
    do
      ++v11;
    while ( v8[v11] );
    v12 = 4;
    v13 = (DWORD *)(a4 + 8);
    if ( v11 >= 4 )
    {
      v17 = 0;
      v18 = SetFilePointer(hFile, 0, 0, 1u);
      *v13 = v18;
      if ( v18 != -1 )
      {
        do
          ++v9;
        while ( v8[v9] );
        if ( WriteFile(hFile, v8, v9 + 1, &NumberOfBytesWritten, 0) )
          v17 = 1;
      }
    }
    else
    {
      v14 = 2147483646;
      v15 = v8;
      do
      {
        if ( !v14 )
          break;
        if ( !*v15 )
          break;
        *(_BYTE *)v13 = *v15++;
        v13 = (DWORD *)((char *)v13 + 1);
        --v14;
        --v12;
      }
      while ( v12 );
      v16 = (DWORD *)((char *)v13 - 1);
      if ( v12 )
        v16 = v13;
      v17 = v12 != 0;
      *(_BYTE *)v16 = 0;
    }
    pMemFree(v8);
    return (_BYTE *)v17;
  }
  return result;
}

```

## disassembly

```asm
0x180004420  push    rbx
0x180004422  push    rbp
0x180004423  push    rsi
0x180004424  push    rdi
0x180004425  push    r14
0x180004427  push    r15
0x180004429  sub     rsp, 48h
0x18000442d  mov     r15, rcx
0x180004430  mov     [rsp+78h+NumberOfBytesWritten], 0
0x180004438  mov     rcx, rdx; lpWideCharStr
0x18000443b  mov     rbx, r9
0x18000443e  movzx   edi, r8w
0x180004442  call    UnicodeStringToAnsiString
0x180004447  mov     rsi, rax
0x18000444a  test    rax, rax
0x18000444d  jz      loc_180004525
0x180004453  or      r14, 0FFFFFFFFFFFFFFFFh
0x180004457  mov     [rbx], di
0x18000445a  mov     rax, r14
0x18000445d  mov     word ptr [rbx+2], 2
0x180004463  inc     rax
0x180004466  cmp     byte ptr [rsi+rax], 0
0x18000446a  jnz     short loc_180004463
0x18000446c  inc     eax
0x18000446e  mov     [rbx+4], eax
0x180004471  mov     rax, r14
0x180004474  inc     rax
0x180004477  cmp     byte ptr [rsi+rax], 0
0x18000447b  jnz     short loc_180004474
0x18000447d  mov     ecx, 4
0x180004482  add     rbx, 8
0x180004486  lea     edi, [rcx-3]
0x180004489  cmp     rax, rcx
0x18000448c  jnb     short loc_1800044CD
0x18000448e  mov     eax, 7FFFFFFEh
0x180004493  mov     rdx, rsi
0x180004496  test    rax, rax
0x180004499  jz      short loc_1800044B4
0x18000449b  mov     r8b, [rdx]
0x18000449e  test    r8b, r8b
0x1800044a1  jz      short loc_1800044B4
0x1800044a3  mov     [rbx], r8b
0x1800044a6  add     rdx, rdi
0x1800044a9  add     rbx, rdi
0x1800044ac  sub     rax, rdi
0x1800044af  sub     rcx, rdi
0x1800044b2  jnz     short loc_180004496
0x1800044b4  test    rcx, rcx
0x1800044b7  lea     rax, [rbx-1]
0x1800044bb  cmovnz  rax, rbx
0x1800044bf  xor     ebp, ebp
0x1800044c1  test    rcx, rcx
0x1800044c4  setnz   bpl
0x1800044c8  mov     byte ptr [rax], 0
0x1800044cb  jmp     short loc_18000451B
0x1800044cd  mov     r9d, edi; dwMoveMethod
0x1800044d0  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800044d3  xor     edx, edx; lDistanceToMove
0x1800044d5  mov     rcx, r15; hFile
0x1800044d8  xor     ebp, ebp
0x1800044da  call    cs:__imp_SetFilePointer
0x1800044e1  nop     dword ptr [rax+rax+00h]
0x1800044e6  mov     [rbx], eax
0x1800044e8  cmp     eax, 0FFFFFFFFh
0x1800044eb  jz      short loc_18000451B
0x1800044ed  inc     r14
0x1800044f0  cmp     [rsi+r14], bpl
0x1800044f4  jnz     short loc_1800044ED
0x1800044f6  lea     r8d, [r14+1]; nNumberOfBytesToWrite
0x1800044fa  mov     [rsp+78h+lpOverlapped], rbp; lpOverlapped
0x1800044ff  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180004504  mov     rdx, rsi; lpBuffer
0x180004507  mov     rcx, r15; hFile
0x18000450a  call    cs:__imp_WriteFile
0x180004511  nop     dword ptr [rax+rax+00h]
0x180004516  test    eax, eax
0x180004518  cmovnz  ebp, edi
0x18000451b  mov     rcx, rsi; lpMem
0x18000451e  call    pMemFree
0x180004523  mov     eax, ebp
0x180004525  add     rsp, 48h
0x180004529  pop     r15
0x18000452b  pop     r14
0x18000452d  pop     rdi
0x18000452e  pop     rsi
0x18000452f  pop     rbp
0x180004530  pop     rbx
0x180004531  retn
```
