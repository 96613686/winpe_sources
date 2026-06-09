# AddStringTag

- ea: `0x1800043d8`
- end: `0x1800044de`
- name: `AddStringTag`
- size: `262`
- prototype: `_BYTE *__fastcall(HANDLE hFile, LPCWCH lpWideCharStr, __int16, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800069c0`

## callees

- `0x1800043d8`
- `0x18000eac0`
- `0x18001646c`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x180004492`
- `KERNEL32!SetFilePointer` at `0x180004492`
- `KERNEL32!WriteFile` at `0x1800044bc`
- `KERNEL32!WriteFile` at `0x1800044bc`

## pseudocode

```c
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
0x1800043d8  push    rbx
0x1800043da  push    rbp
0x1800043db  push    rsi
0x1800043dc  push    rdi
0x1800043dd  push    r14
0x1800043df  push    r15
0x1800043e1  sub     rsp, 48h
0x1800043e5  mov     r15, rcx
0x1800043e8  mov     [rsp+78h+NumberOfBytesWritten], 0
0x1800043f0  mov     rcx, rdx; lpWideCharStr
0x1800043f3  mov     rbx, r9
0x1800043f6  movzx   edi, r8w
0x1800043fa  call    UnicodeStringToAnsiString
0x1800043ff  mov     rsi, rax
0x180004402  test    rax, rax
0x180004405  jz      loc_1800044D1
0x18000440b  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000440f  mov     [rbx], di
0x180004412  mov     rax, r14
0x180004415  mov     word ptr [rbx+2], 2
0x18000441b  inc     rax
0x18000441e  cmp     byte ptr [rsi+rax], 0
0x180004422  jnz     short loc_18000441B
0x180004424  inc     eax
0x180004426  mov     [rbx+4], eax
0x180004429  mov     rax, r14
0x18000442c  inc     rax
0x18000442f  cmp     byte ptr [rsi+rax], 0
0x180004433  jnz     short loc_18000442C
0x180004435  mov     ecx, 4
0x18000443a  add     rbx, 8
0x18000443e  lea     edi, [rcx-3]
0x180004441  cmp     rax, rcx
0x180004444  jnb     short loc_180004485
0x180004446  mov     eax, 7FFFFFFEh
0x18000444b  mov     rdx, rsi
0x18000444e  test    rax, rax
0x180004451  jz      short loc_18000446C
0x180004453  mov     r8b, [rdx]
0x180004456  test    r8b, r8b
0x180004459  jz      short loc_18000446C
0x18000445b  mov     [rbx], r8b
0x18000445e  add     rdx, rdi
0x180004461  add     rbx, rdi
0x180004464  sub     rax, rdi
0x180004467  sub     rcx, rdi
0x18000446a  jnz     short loc_18000444E
0x18000446c  test    rcx, rcx
0x18000446f  lea     rax, [rbx-1]
0x180004473  cmovnz  rax, rbx
0x180004477  xor     ebp, ebp
0x180004479  test    rcx, rcx
0x18000447c  setnz   bpl
0x180004480  mov     byte ptr [rax], 0
0x180004483  jmp     short loc_1800044C7
0x180004485  mov     r9d, edi; dwMoveMethod
0x180004488  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000448b  xor     edx, edx; lDistanceToMove
0x18000448d  mov     rcx, r15; hFile
0x180004490  xor     ebp, ebp
0x180004492  call    cs:__imp_SetFilePointer
0x180004498  mov     [rbx], eax
0x18000449a  cmp     eax, 0FFFFFFFFh
0x18000449d  jz      short loc_1800044C7
0x18000449f  inc     r14
0x1800044a2  cmp     [rsi+r14], bpl
0x1800044a6  jnz     short loc_18000449F
0x1800044a8  lea     r8d, [r14+1]; nNumberOfBytesToWrite
0x1800044ac  mov     [rsp+78h+lpOverlapped], rbp; lpOverlapped
0x1800044b1  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800044b6  mov     rdx, rsi; lpBuffer
0x1800044b9  mov     rcx, r15; hFile
0x1800044bc  call    cs:__imp_WriteFile
0x1800044c2  test    eax, eax
0x1800044c4  cmovnz  ebp, edi
0x1800044c7  mov     rcx, rsi; lpMem
0x1800044ca  call    pMemFree
0x1800044cf  mov     eax, ebp
0x1800044d1  add     rsp, 48h
0x1800044d5  pop     r15
0x1800044d7  pop     r14
0x1800044d9  pop     rdi
0x1800044da  pop     rsi
0x1800044db  pop     rbp
0x1800044dc  pop     rbx
0x1800044dd  retn
```
