# PszToUnicode

- ea: `0x180001150`
- end: `0x180001237`
- name: `PszToUnicode`
- size: `231`
- prototype: `WCHAR *__fastcall(UINT CodePage, LPCCH lpMultiByteStr)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800095a8`
- `0x18000ae20`

## callees

- `0x180001150`
- `0x18000ff30`
- `0x180014010`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x1800011af`
- `KERNEL32!MultiByteToWideChar` at `0x180001203`
- `KERNEL32!MultiByteToWideChar` at `0x1800011af`
- `KERNEL32!MultiByteToWideChar` at `0x180001203`

## pseudocode

```c
WCHAR *__fastcall PszToUnicode(UINT CodePage, LPCCH lpMultiByteStr)
{
  __int64 v4; // rax
  int v6; // ebp
  DWORD v7; // esi
  int v8; // eax
  __int64 v9; // rdx
  WCHAR *result; // rax
  int cchWideChar; // r15d
  WCHAR *v12; // rdi

  if ( !lpMultiByteStr )
    return 0;
  v4 = -1;
  while ( lpMultiByteStr[++v4] != 0 )
    ;
  v6 = v4 + 1;
  v7 = CodePage != 65001;
  v8 = MultiByteToWideChar(CodePage, v7, lpMultiByteStr, v4 + 1, 0, 0);
  if ( !v8 )
    return 0;
  cchWideChar = v8 + 1;
  result = (WCHAR *)PszAllocW(v8 + 1, v9);
  v12 = result;
  if ( result )
  {
    if ( MultiByteToWideChar(CodePage, v7, lpMultiByteStr, v6, result, cchWideChar) )
    {
      return v12;
    }
    else
    {
      ((void (__fastcall *)(LPMALLOC, WCHAR *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v12);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180001150  mov     [rsp+arg_18], rbx
0x180001155  push    rdi
0x180001156  push    r12
0x180001158  push    r14
0x18000115a  sub     rsp, 30h
0x18000115e  xor     r12d, r12d
0x180001161  mov     rbx, rdx
0x180001164  mov     r14d, ecx
0x180001167  test    rdx, rdx
0x18000116a  jz      loc_180001232
0x180001170  mov     [rsp+48h+arg_0], rbp
0x180001175  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000117c  mov     [rsp+48h+arg_8], rsi
0x180001181  cmp     [rdx+rax+1], r12b
0x180001186  lea     rax, [rax+1]
0x18000118a  jnz     short loc_180001181
0x18000118c  mov     esi, r12d
0x18000118f  mov     [rsp+48h+cchWideChar], r12d; cchWideChar
0x180001194  lea     ebp, [rax+1]
0x180001197  mov     [rsp+48h+lpWideCharStr], r12; lpWideCharStr
0x18000119c  cmp     r14d, 0FDE9h
0x1800011a3  mov     r9d, ebp; cbMultiByte
0x1800011a6  mov     r8, rbx; lpMultiByteStr
0x1800011a9  setnz   sil
0x1800011ad  mov     edx, esi; dwFlags
0x1800011af  call    cs:__imp_MultiByteToWideChar
0x1800011b5  test    eax, eax
0x1800011b7  jnz     short loc_1800011D5
0x1800011b9  mov     rax, r12
0x1800011bc  mov     rbp, [rsp+48h+arg_0]
0x1800011c1  mov     rsi, [rsp+48h+arg_8]
0x1800011c6  mov     rbx, [rsp+48h+arg_18]
0x1800011cb  add     rsp, 30h
0x1800011cf  pop     r14
0x1800011d1  pop     r12
0x1800011d3  pop     rdi
0x1800011d4  retn
0x1800011d5  mov     [rsp+48h+arg_10], r15
0x1800011da  lea     r15d, [rax+1]
0x1800011de  mov     ecx, r15d
0x1800011e1  call    PszAllocW
0x1800011e6  mov     rdi, rax
0x1800011e9  test    rax, rax
0x1800011ec  jz      short loc_180001226
0x1800011ee  mov     [rsp+48h+cchWideChar], r15d; cchWideChar
0x1800011f3  mov     r9d, ebp; cbMultiByte
0x1800011f6  mov     r8, rbx; lpMultiByteStr
0x1800011f9  mov     [rsp+48h+lpWideCharStr], rax; lpWideCharStr
0x1800011fe  mov     edx, esi; dwFlags
0x180001200  mov     ecx, r14d; CodePage
0x180001203  call    cs:__imp_MultiByteToWideChar
0x180001209  test    eax, eax
0x18000120b  jnz     short loc_18000122D
0x18000120d  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180001214  mov     rdx, rdi
0x180001217  mov     rax, [rcx]
0x18000121a  mov     rax, [rax+28h]
0x18000121e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001223  mov     rax, r12
0x180001226  mov     r15, [rsp+48h+arg_10]
0x18000122b  jmp     short loc_1800011BC
0x18000122d  mov     rax, rdi
0x180001230  jmp     short loc_180001226
0x180001232  mov     rax, r12
0x180001235  jmp     short loc_1800011C6
```
