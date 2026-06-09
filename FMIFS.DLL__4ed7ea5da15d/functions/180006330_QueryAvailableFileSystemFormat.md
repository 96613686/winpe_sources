# QueryAvailableFileSystemFormat

- ea: `0x180006330`
- end: `0x1800063c0`
- name: `QueryAvailableFileSystemFormat`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006940`

## callees

- `0x180006330`
- `0x180009746`

## pseudocode

```c
char __fastcall QueryAvailableFileSystemFormat(unsigned int a1, void *a2, _BYTE *a3, _BYTE *a4, _BYTE *a5)
{
  __int64 v8; // r14
  unsigned __int64 v9; // r8
  char *v10; // rdx

  if ( a1 >= 0xD )
    return 0;
  if ( !a2 )
    return 0;
  if ( !a3 )
    return 0;
  if ( !a4 )
    return 0;
  if ( !a5 )
    return 0;
  v8 = 22LL * a1;
  v9 = -1;
  v10 = (char *)&fsFormatAvailable + v8;
  do
    ++v9;
  while ( *(_WORD *)&v10[2 * v9] );
  if ( v9 >= 9 )
    return 0;
  memcpy_0(a2, v10, 2 * v9 + 2);
  *a3 = *((_BYTE *)&fsFormatAvailable + v8 + 18);
  *a4 = *((_BYTE *)&fsFormatAvailable + v8 + 19);
  *a5 = *((_BYTE *)&fsFormatAvailable + v8 + 20);
  return 1;
}

```

## disassembly

```asm
0x180006330  push    rbx
0x180006332  push    rbp
0x180006333  push    rsi
0x180006334  push    rdi
0x180006335  push    r14
0x180006337  sub     rsp, 20h
0x18000633b  mov     rdi, r9
0x18000633e  mov     r9, rdx
0x180006341  mov     rsi, r8
0x180006344  cmp     ecx, 0Dh
0x180006347  jnb     short loc_1800063B3
0x180006349  xor     r10d, r10d
0x18000634c  test    rdx, rdx
0x18000634f  jz      short loc_1800063B3
0x180006351  test    r8, r8
0x180006354  jz      short loc_1800063B3
0x180006356  test    rdi, rdi
0x180006359  jz      short loc_1800063B3
0x18000635b  mov     rbx, [rsp+48h+arg_20]
0x180006360  test    rbx, rbx
0x180006363  jz      short loc_1800063B3
0x180006365  mov     eax, ecx
0x180006367  lea     rbp, ?fsFormatAvailable@@3PAU_FILE_SYSTEM_FORMAT_RECORD@@A; "FAT"
0x18000636e  imul    r14, rax, 16h
0x180006372  or      r8, 0FFFFFFFFFFFFFFFFh
0x180006376  lea     rdx, [r14+rbp]; Src
0x18000637a  inc     r8
0x18000637d  cmp     [rdx+r8*2], r10w
0x180006382  jnz     short loc_18000637A
0x180006384  cmp     r8, 9
0x180006388  jnb     short loc_1800063B3
0x18000638a  lea     r8, ds:2[r8*2]; Size
0x180006392  mov     rcx, r9; void *
0x180006395  call    memcpy_0
0x18000639a  mov     al, [r14+rbp+12h]
0x18000639f  mov     [rsi], al
0x1800063a1  mov     al, [r14+rbp+13h]
0x1800063a6  mov     [rdi], al
0x1800063a8  mov     al, [r14+rbp+14h]
0x1800063ad  mov     [rbx], al
0x1800063af  mov     al, 1
0x1800063b1  jmp     short loc_1800063B5
0x1800063b3  xor     al, al
0x1800063b5  add     rsp, 20h
0x1800063b9  pop     r14
0x1800063bb  pop     rdi
0x1800063bc  pop     rsi
0x1800063bd  pop     rbp
0x1800063be  pop     rbx
0x1800063bf  retn
```
