# PGetFormTrayTable

- ea: `0x18002edb0`
- end: `0x18002ef41`
- name: `PGetFormTrayTable`
- size: `401`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180002f40`

## callees

- `0x18002edb0`
- `0x18002f1b4`
- `0x18005c434`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002ee00`
- `KERNEL32!SetLastError` at `0x18002ee00`
- `KERNEL32!LocalFree` at `0x18002ee09`
- `KERNEL32!LocalFree` at `0x18002ef36`
- `KERNEL32!LocalFree` at `0x18002ee09`
- `KERNEL32!LocalFree` at `0x18002ef36`
- `KERNEL32!LocalAlloc` at `0x18002eeb8`
- `KERNEL32!LocalAlloc` at `0x18002eeb8`

## string_xrefs

- `0x18002edd9`: `TrayFormSize`

## pseudocode

```c
_WORD *__fastcall PGetFormTrayTable(void *a1)
{
  _WORD *PrinterDataBinary; // rax
  void *v2; // rbp
  _WORD *v3; // rdi
  _WORD *v5; // rsi
  _WORD *v6; // rdx
  int v7; // r9d
  _WORD *i; // r8
  __int64 v9; // rax
  _WORD *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  _WORD *v14; // rax
  _WORD *v15; // r15
  __int64 v16; // rax
  _WORD *v17; // rcx
  __int64 v18; // rax
  _WORD *v19; // r14
  __int64 v20; // rax

  PrinterDataBinary = (_WORD *)PvGetPrinterDataBinary(a1);
  v2 = PrinterDataBinary;
  if ( !PrinterDataBinary )
    return 0;
  if ( *PrinterDataBinary )
  {
    SetLastError(0xDu);
LABEL_4:
    LocalFree(v2);
    return 0;
  }
  v5 = PrinterDataBinary + 1;
  v6 = PrinterDataBinary + 1;
  v7 = 1;
  for ( i = PrinterDataBinary + 0x7FFFFFFF; v6 < i; v6 = (_WORD *)(v12 + 2 * (v13 + 2)) )
  {
    if ( !*v6 )
      break;
    v9 = -1;
    do
      ++v9;
    while ( v6[v9] );
    v10 = &v6[v9 + 1];
    v11 = -1;
    do
      ++v11;
    while ( v10[v11] );
    v12 = (__int64)&v10[v11 + 1];
    v7 += (v12 - (__int64)v6) >> 1;
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)(v12 + 2 * v13) );
  }
  if ( v6 != i )
    goto LABEL_4;
  if ( *v6 )
    goto LABEL_4;
  v14 = LocalAlloc(0, (unsigned int)(2 * v7));
  v3 = v14;
  if ( !v14 )
    goto LABEL_4;
  v15 = v14;
  while ( *v5 )
  {
    v16 = -1;
    do
      ++v16;
    while ( v5[v16] );
    v17 = &v5[v16 + 1];
    v18 = -1;
    do
      ++v18;
    while ( v17[v18] );
    v19 = &v17[v18 + 1];
    memcpy_0(v15, v5, 2 * (v19 - v5));
    v15 += v19 - v5;
    v20 = -1;
    do
      ++v20;
    while ( v19[v20] );
    v5 = &v19[v20 + 2];
  }
  *v15 = 0;
  LocalFree(v2);
  return v3;
}

```

## disassembly

```asm
0x18002edb0  mov     rax, rsp
0x18002edb3  mov     [rax+18h], r8d
0x18002edb7  push    rbx
0x18002edb8  push    rbp
0x18002edb9  push    rsi
0x18002edba  push    rdi
0x18002edbb  push    r12
0x18002edbd  push    r13
0x18002edbf  push    r14
0x18002edc1  push    r15
0x18002edc3  sub     rsp, 28h
0x18002edc7  xor     r12d, r12d
0x18002edca  lea     r9, [rax+18h]
0x18002edce  lea     r8, aTrayformtable; "TrayFormTable"
0x18002edd5  mov     [rax+18h], r12d
0x18002edd9  lea     rdx, aTrayformsize; "TrayFormSize"
0x18002ede0  call    PvGetPrinterDataBinary
0x18002ede5  mov     rbp, rax
0x18002ede8  test    rax, rax
0x18002edeb  jz      short loc_18002EE0F
0x18002eded  movzx   eax, word ptr [rax]
0x18002edf0  mov     ecx, [rsp+68h+arg_10]
0x18002edf7  cmp     ecx, eax
0x18002edf9  jz      short loc_18002EE26
0x18002edfb  lea     ecx, [r12+0Dh]; dwErrCode
0x18002ee00  call    cs:__imp_SetLastError
0x18002ee06  mov     rcx, rbp; hMem
0x18002ee09  call    cs:__imp_LocalFree
0x18002ee0f  mov     rdi, r12
0x18002ee12  mov     rax, rdi
0x18002ee15  add     rsp, 28h
0x18002ee19  pop     r15
0x18002ee1b  pop     r14
0x18002ee1d  pop     r13
0x18002ee1f  pop     r12
0x18002ee21  pop     rdi
0x18002ee22  pop     rsi
0x18002ee23  pop     rbp
0x18002ee24  pop     rbx
0x18002ee25  retn
0x18002ee26  lea     rsi, [rbp+2]
0x18002ee2a  or      r13, 0FFFFFFFFFFFFFFFFh
0x18002ee2e  lea     r8d, [rcx-2]
0x18002ee32  mov     rdx, rsi
0x18002ee35  shr     r8, 1
0x18002ee38  mov     r9d, 1
0x18002ee3e  dec     r8
0x18002ee41  lea     r8, [rsi+r8*2]
0x18002ee45  cmp     rsi, r8
0x18002ee48  jnb     short loc_18002EE9F
0x18002ee4a  cmp     [rdx], r12w
0x18002ee4e  jz      short loc_18002EE9F
0x18002ee50  mov     rax, r13
0x18002ee53  inc     rax
0x18002ee56  cmp     [rdx+rax*2], r12w
0x18002ee5b  jnz     short loc_18002EE53
0x18002ee5d  inc     rax
0x18002ee60  lea     rcx, [rdx+rax*2]
0x18002ee64  mov     rax, r13
0x18002ee67  inc     rax
0x18002ee6a  cmp     [rcx+rax*2], r12w
0x18002ee6f  jnz     short loc_18002EE67
0x18002ee71  lea     rcx, [rcx+rax*2]
0x18002ee75  add     rcx, 2
0x18002ee79  mov     rax, rcx
0x18002ee7c  sub     rax, rdx
0x18002ee7f  sar     rax, 1
0x18002ee82  add     r9d, eax
0x18002ee85  mov     rax, r13
0x18002ee88  inc     rax
0x18002ee8b  cmp     [rcx+rax*2], r12w
0x18002ee90  jnz     short loc_18002EE88
0x18002ee92  lea     rdx, [rax+2]
0x18002ee96  lea     rdx, [rcx+rdx*2]
0x18002ee9a  cmp     rdx, r8
0x18002ee9d  jb      short loc_18002EE4A
0x18002ee9f  cmp     rdx, r8
0x18002eea2  jnz     loc_18002EE06
0x18002eea8  cmp     [rdx], r12w
0x18002eeac  jnz     loc_18002EE06
0x18002eeb2  lea     edx, [r9+r9]; uBytes
0x18002eeb6  xor     ecx, ecx; uFlags
0x18002eeb8  call    cs:__imp_LocalAlloc
0x18002eebe  mov     rdi, rax
0x18002eec1  test    rax, rax
0x18002eec4  jz      loc_18002EE06
0x18002eeca  mov     r15, rax
0x18002eecd  jmp     short loc_18002EF29
0x18002eecf  mov     rax, r13
0x18002eed2  inc     rax
0x18002eed5  cmp     [rsi+rax*2], r12w
0x18002eeda  jnz     short loc_18002EED2
0x18002eedc  inc     rax
0x18002eedf  lea     rcx, [rsi+rax*2]
0x18002eee3  mov     rax, r13
0x18002eee6  inc     rax
0x18002eee9  cmp     [rcx+rax*2], r12w
0x18002eeee  jnz     short loc_18002EEE6
0x18002eef0  inc     rax
0x18002eef3  mov     rdx, rsi; Src
0x18002eef6  lea     r14, [rcx+rax*2]
0x18002eefa  mov     rcx, r15; void *
0x18002eefd  mov     rbx, r14
0x18002ef00  sub     rbx, rsi
0x18002ef03  sar     rbx, 1
0x18002ef06  add     rbx, rbx
0x18002ef09  mov     r8, rbx; Size
0x18002ef0c  call    memcpy_0
0x18002ef11  add     r15, rbx
0x18002ef14  mov     rax, r13
0x18002ef17  inc     rax
0x18002ef1a  cmp     [r14+rax*2], r12w
0x18002ef1f  jnz     short loc_18002EF17
0x18002ef21  lea     rsi, [rax+2]
0x18002ef25  lea     rsi, [r14+rsi*2]
0x18002ef29  cmp     [rsi], r12w
0x18002ef2d  jnz     short loc_18002EECF
0x18002ef2f  mov     rcx, rbp; hMem
0x18002ef32  mov     [r15], r12w
0x18002ef36  call    cs:__imp_LocalFree
0x18002ef3c  jmp     loc_18002EE12
```
