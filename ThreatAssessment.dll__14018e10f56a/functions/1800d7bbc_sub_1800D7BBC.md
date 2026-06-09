# sub_1800D7BBC

- ea: `0x1800d7bbc`
- end: `0x1800d7c95`
- name: `sub_1800D7BBC`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800dbd40`

## callees

- `0x18000ca10`
- `0x180015920`
- `0x1800d6cc4`
- `0x1800d7bbc`
- `0x1800e2e38`
- `0x18014c880`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800d7bef`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800d7bef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d7c75`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d7c75`

## pseudocode

```c
HMODULE *__fastcall sub_1800D7BBC(HMODULE *a1, _QWORD *a2, _QWORD *a3)
{
  __int64 v5; // rax
  HMODULE Library; // rax
  HMODULE v7; // rsi
  unsigned __int64 v8; // rax
  const CHAR *v9; // rdx
  LPCSTR lpProcName[2]; // [rsp+20h] [rbp-48h] BYREF
  __int128 v12; // [rsp+30h] [rbp-38h]
  HMODULE *v13; // [rsp+48h] [rbp-20h]

  v13 = a1;
  v5 = sub_1800E2E38((__int64)lpProcName, a2);
  if ( *(_QWORD *)(v5 + 24) > 0xFu )
    v5 = *(_QWORD *)v5;
  Library = LoadLibraryExA((LPCSTR)v5, 0, 0x800u);
  *a1 = 0;
  a1[1] = 0;
  sub_1800D6CC4(a1, Library, 0);
  sub_180015920((__int64 *)lpProcName);
  a1[2] = 0;
  v7 = *a1;
  if ( *a1 )
  {
    if ( a3[3] > 0xFu )
      a3 = (_QWORD *)*a3;
    *(_OWORD *)lpProcName = 0;
    v12 = 0;
    v8 = sub_18014C880(a3);
    sub_18000CA10((unsigned __int64 *)lpProcName, (__int64)a3, v8);
    v9 = (const CHAR *)lpProcName;
    if ( *((_QWORD *)&v12 + 1) > 0xFu )
      v9 = lpProcName[0];
    a1[2] = (HMODULE)GetProcAddress(v7, v9);
    sub_180015920((__int64 *)lpProcName);
  }
  return a1;
}

```

## disassembly

```asm
0x1800d7bbc  push    rbx
0x1800d7bbe  push    rsi
0x1800d7bbf  push    rdi
0x1800d7bc0  sub     rsp, 50h
0x1800d7bc4  mov     rdi, r8
0x1800d7bc7  mov     rbx, rcx
0x1800d7bca  mov     [rsp+68h+var_20], rcx
0x1800d7bcf  lea     rcx, [rsp+68h+lpProcName]
0x1800d7bd4  call    sub_1800E2E38
0x1800d7bd9  nop
0x1800d7bda  cmp     qword ptr [rax+18h], 0Fh
0x1800d7bdf  jbe     short loc_1800D7BE4
0x1800d7be1  mov     rax, [rax]
0x1800d7be4  xor     edx, edx; hFile
0x1800d7be6  mov     r8d, 800h; dwFlags
0x1800d7bec  mov     rcx, rax; lpLibFileName
0x1800d7bef  call    cs:LoadLibraryExA
0x1800d7bf5  mov     qword ptr [rbx], 0
0x1800d7bfc  mov     qword ptr [rbx+8], 0
0x1800d7c04  xor     r8d, r8d
0x1800d7c07  mov     rdx, rax
0x1800d7c0a  mov     rcx, rbx
0x1800d7c0d  call    sub_1800D6CC4
0x1800d7c12  nop
0x1800d7c13  lea     rcx, [rsp+68h+lpProcName]
0x1800d7c18  call    sub_180015920
0x1800d7c1d  nop
0x1800d7c1e  mov     qword ptr [rbx+10h], 0
0x1800d7c26  mov     rsi, [rbx]
0x1800d7c29  test    rsi, rsi
0x1800d7c2c  jz      short loc_1800D7C8A
0x1800d7c2e  cmp     qword ptr [rdi+18h], 0Fh
0x1800d7c33  jbe     short loc_1800D7C38
0x1800d7c35  mov     rdi, [rdi]
0x1800d7c38  xorps   xmm0, xmm0
0x1800d7c3b  movups  xmmword ptr [rsp+68h+lpProcName], xmm0
0x1800d7c40  xorps   xmm1, xmm1
0x1800d7c43  movdqu  [rsp+68h+var_38], xmm1
0x1800d7c49  mov     rcx, rdi
0x1800d7c4c  call    sub_18014C880
0x1800d7c51  mov     r8, rax
0x1800d7c54  mov     rdx, rdi
0x1800d7c57  lea     rcx, [rsp+68h+lpProcName]
0x1800d7c5c  call    sub_18000CA10
0x1800d7c61  lea     rdx, [rsp+68h+lpProcName]
0x1800d7c66  cmp     qword ptr [rsp+68h+var_38+8], 0Fh
0x1800d7c6c  cmova   rdx, [rsp+68h+lpProcName]; lpProcName
0x1800d7c72  mov     rcx, rsi; hModule
0x1800d7c75  call    cs:__imp_GetProcAddress
0x1800d7c7b  mov     [rbx+10h], rax
0x1800d7c7f  lea     rcx, [rsp+68h+lpProcName]
0x1800d7c84  call    sub_180015920
0x1800d7c89  nop
0x1800d7c8a  mov     rax, rbx
0x1800d7c8d  add     rsp, 50h
0x1800d7c91  pop     rdi
0x1800d7c92  pop     rsi
0x1800d7c93  pop     rbx
0x1800d7c94  retn
```
