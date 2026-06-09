# PSPGetAndConvertOldVersionFormTrayTable

- ea: `0x18002a494`
- end: `0x18002a646`
- name: `PSPGetAndConvertOldVersionFormTrayTable`
- size: `434`
- prototype: `_WORD *__fastcall(void *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180002fe8`

## callees

- `0x18002a494`
- `0x1800306bc`
- `0x18005e0c4`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002a4df`
- `KERNEL32!SetLastError` at `0x18002a4df`
- `KERNEL32!LocalFree` at `0x18002a4ee`
- `KERNEL32!LocalFree` at `0x18002a632`
- `KERNEL32!LocalFree` at `0x18002a4ee`
- `KERNEL32!LocalFree` at `0x18002a632`
- `KERNEL32!LocalAlloc` at `0x18002a59d`
- `KERNEL32!LocalAlloc` at `0x18002a59d`

## string_xrefs

- `0x18002a4b0`: `TrayFormSize`

## pseudocode

```c
_WORD *__fastcall PSPGetAndConvertOldVersionFormTrayTable(void *a1, unsigned int *a2)
{
  unsigned __int16 *PrinterDataBinary; // rax
  void *v4; // rdi
  _WORD *v6; // rsi
  _WORD *v7; // rdx
  int v8; // r15d
  unsigned __int64 v9; // r8
  __int64 v10; // rax
  _WORD *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  unsigned int v15; // r15d
  _WORD *v16; // rax
  _WORD *v17; // rbp
  _WORD *v18; // r12
  __int64 v19; // rcx
  __int64 v20; // rax
  _WORD *v21; // rdx
  _WORD *v22; // r14
  __int64 v23; // rax
  int v24; // [rsp+80h] [rbp+18h] BYREF

  v24 = 0;
  PrinterDataBinary = (unsigned __int16 *)PvGetPrinterDataBinary(a1, L"TrayFormSize", L"TrayFormTable", &v24);
  v4 = PrinterDataBinary;
  if ( !PrinterDataBinary )
    return 0;
  if ( v24 != *PrinterDataBinary )
  {
    SetLastError(0xDu);
LABEL_4:
    LocalFree(v4);
    return 0;
  }
  v6 = PrinterDataBinary + 1;
  v7 = PrinterDataBinary + 1;
  v8 = 1;
  v9 = (unsigned __int64)&PrinterDataBinary[(unsigned __int64)(unsigned int)(v24 - 2) >> 1];
  if ( (unsigned __int64)(PrinterDataBinary + 1) < v9 )
  {
    do
    {
      if ( !*v7 )
        break;
      v10 = -1;
      do
        ++v10;
      while ( v7[v10] );
      v11 = &v7[v10 + 1];
      v12 = -1;
      do
        ++v12;
      while ( v11[v12] );
      v13 = (__int64)&v11[v12 + 1];
      v8 += (v13 - (__int64)v7) >> 1;
      v14 = -1;
      do
        ++v14;
      while ( *(_WORD *)(v13 + 2 * v14) );
      v7 = (_WORD *)(v13 + 2 * (v14 + 2));
    }
    while ( (unsigned __int64)v7 < v9 );
  }
  if ( v7 != (_WORD *)v9 )
    goto LABEL_4;
  if ( *v7 )
    goto LABEL_4;
  v15 = 2 * v8;
  v16 = LocalAlloc(0, v15);
  v17 = v16;
  if ( !v16 )
    goto LABEL_4;
  v18 = v16;
  while ( *v6 )
  {
    v19 = -1;
    do
      ++v19;
    while ( v6[v19] );
    v20 = -1;
    v21 = &v6[v19 + 1];
    do
      ++v20;
    while ( v21[v20] );
    v22 = &v21[v20];
    memcpy_0(v18, v6, 2 * (v22 + 1 - v6));
    v23 = -1;
    v18 += v22 + 1 - v6;
    do
      ++v23;
    while ( v22[v23 + 1] );
    v6 = &v22[v23 + 3];
  }
  *v18 = 0;
  if ( a2 )
    *a2 = v15;
  LocalFree(v4);
  return v17;
}

```

## disassembly

```asm
0x18002a494  mov     rax, rsp
0x18002a497  push    rbx
0x18002a498  push    rbp
0x18002a499  push    rsi
0x18002a49a  push    rdi
0x18002a49b  push    r12
0x18002a49d  push    r13
0x18002a49f  push    r14
0x18002a4a1  push    r15
0x18002a4a3  sub     rsp, 28h
0x18002a4a7  mov     r13, rdx
0x18002a4aa  lea     r9, [rax+18h]
0x18002a4ae  xor     ebx, ebx
0x18002a4b0  lea     rdx, aTrayformsize; "TrayFormSize"
0x18002a4b7  lea     r8, aTrayformtable; "TrayFormTable"
0x18002a4be  mov     [rax+18h], ebx
0x18002a4c1  call    PvGetPrinterDataBinary
0x18002a4c6  mov     rdi, rax
0x18002a4c9  test    rax, rax
0x18002a4cc  jz      short loc_18002A4FA
0x18002a4ce  movzx   eax, word ptr [rax]
0x18002a4d1  mov     ecx, [rsp+68h+arg_10]
0x18002a4d8  cmp     ecx, eax
0x18002a4da  jz      short loc_18002A50E
0x18002a4dc  lea     ecx, [rbx+0Dh]; dwErrCode
0x18002a4df  call    cs:__imp_SetLastError
0x18002a4e6  nop     dword ptr [rax+rax+00h]
0x18002a4eb  mov     rcx, rdi; hMem
0x18002a4ee  call    cs:__imp_LocalFree
0x18002a4f5  nop     dword ptr [rax+rax+00h]
0x18002a4fa  xor     eax, eax
0x18002a4fc  add     rsp, 28h
0x18002a500  pop     r15
0x18002a502  pop     r14
0x18002a504  pop     r13
0x18002a506  pop     r12
0x18002a508  pop     rdi
0x18002a509  pop     rsi
0x18002a50a  pop     rbp
0x18002a50b  pop     rbx
0x18002a50c  retn
0x18002a50e  lea     rsi, [rdi+2]
0x18002a512  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002a516  lea     r8d, [rcx-2]
0x18002a51a  mov     rdx, rsi
0x18002a51d  shr     r8, 1
0x18002a520  mov     r15d, 1
0x18002a526  dec     r8
0x18002a529  lea     r8, [rsi+r8*2]
0x18002a52d  cmp     rsi, r8
0x18002a530  jnb     short loc_18002A583
0x18002a532  cmp     [rdx], bx
0x18002a535  jz      short loc_18002A583
0x18002a537  mov     rax, r14
0x18002a53a  inc     rax
0x18002a53d  cmp     [rdx+rax*2], bx
0x18002a541  jnz     short loc_18002A53A
0x18002a543  inc     rax
0x18002a546  lea     rcx, [rdx+rax*2]
0x18002a54a  mov     rax, r14
0x18002a54d  inc     rax
0x18002a550  cmp     [rcx+rax*2], bx
0x18002a554  jnz     short loc_18002A54D
0x18002a556  lea     rcx, [rcx+rax*2]
0x18002a55a  add     rcx, 2
0x18002a55e  mov     rax, rcx
0x18002a561  sub     rax, rdx
0x18002a564  sar     rax, 1
0x18002a567  add     r15d, eax
0x18002a56a  mov     rax, r14
0x18002a56d  inc     rax
0x18002a570  cmp     [rcx+rax*2], bx
0x18002a574  jnz     short loc_18002A56D
0x18002a576  lea     rdx, [rax+2]
0x18002a57a  lea     rdx, [rcx+rdx*2]
0x18002a57e  cmp     rdx, r8
0x18002a581  jb      short loc_18002A532
0x18002a583  cmp     rdx, r8
0x18002a586  jnz     loc_18002A4EB
0x18002a58c  cmp     [rdx], bx
0x18002a58f  jnz     loc_18002A4EB
0x18002a595  add     r15d, r15d
0x18002a598  xor     ecx, ecx; uFlags
0x18002a59a  mov     edx, r15d; uBytes
0x18002a59d  call    cs:__imp_LocalAlloc
0x18002a5a4  nop     dword ptr [rax+rax+00h]
0x18002a5a9  mov     rbp, rax
0x18002a5ac  test    rax, rax
0x18002a5af  jz      loc_18002A4EB
0x18002a5b5  mov     r12, rax
0x18002a5b8  jmp     short loc_18002A61C
0x18002a5ba  mov     rcx, r14
0x18002a5bd  inc     rcx
0x18002a5c0  cmp     [rsi+rcx*2], bx
0x18002a5c4  jnz     short loc_18002A5BD
0x18002a5c6  lea     rdx, [rcx+1]
0x18002a5ca  mov     rax, r14
0x18002a5cd  lea     rdx, [rsi+rdx*2]
0x18002a5d1  inc     rax
0x18002a5d4  cmp     [rdx+rax*2], bx
0x18002a5d8  jnz     short loc_18002A5D1
0x18002a5da  lea     r14, [rdx+rax*2]
0x18002a5de  mov     rcx, r12; void *
0x18002a5e1  lea     rbx, [r14+2]
0x18002a5e5  mov     rdx, rsi; Src
0x18002a5e8  sub     rbx, rsi
0x18002a5eb  sar     rbx, 1
0x18002a5ee  add     rbx, rbx
0x18002a5f1  mov     r8, rbx; Size
0x18002a5f4  call    memcpy_0
0x18002a5f9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a5fd  add     r12, rbx
0x18002a600  xor     ebx, ebx
0x18002a602  inc     rax
0x18002a605  cmp     [r14+rax*2+2], bx
0x18002a60b  jnz     short loc_18002A602
0x18002a60d  lea     rsi, [r14+6]
0x18002a611  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18002a618  lea     rsi, [rsi+rax*2]
0x18002a61c  cmp     [rsi], bx
0x18002a61f  jnz     short loc_18002A5BA
0x18002a621  mov     [r12], bx
0x18002a626  test    r13, r13
0x18002a629  jz      short loc_18002A62F
0x18002a62b  mov     [r13+0], r15d
0x18002a62f  mov     rcx, rdi; hMem
0x18002a632  call    cs:__imp_LocalFree
0x18002a639  nop     dword ptr [rax+rax+00h]
0x18002a63e  mov     rax, rbp
0x18002a641  jmp     loc_18002A4FC
```
