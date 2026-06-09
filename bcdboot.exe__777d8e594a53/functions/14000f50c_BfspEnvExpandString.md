# BfspEnvExpandString

- ea: `0x14000f50c`
- end: `0x14000f726`
- name: `BfspEnvExpandString`
- size: `538`
- prototype: `wchar_t *__fastcall(__int64, const wchar_t *)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x140009fd4`
- `0x14000c024`
- `0x14000cc78`
- `0x14000cfc0`
- `0x14000d494`

## callees

- `0x140003cbc`
- `0x14000f50c`
- `0x14000f72c`
- `0x14000f780`

## import_xrefs

- `msvcrt!wcschr` at `0x14000f5a1`
- `msvcrt!wcschr` at `0x14000f5a1`
- `KERNEL32!SetLastError` at `0x14000f70c`
- `KERNEL32!SetLastError` at `0x14000f70c`
- `KERNEL32!HeapFree` at `0x14000f6e4`
- `KERNEL32!HeapFree` at `0x14000f701`
- `KERNEL32!HeapFree` at `0x14000f6e4`
- `KERNEL32!HeapFree` at `0x14000f701`
- `KERNEL32!HeapAlloc` at `0x14000f56b`
- `KERNEL32!HeapAlloc` at `0x14000f63c`
- `KERNEL32!HeapAlloc` at `0x14000f56b`
- `KERNEL32!HeapAlloc` at `0x14000f63c`
- `KERNEL32!GetProcessHeap` at `0x14000f558`
- `KERNEL32!GetProcessHeap` at `0x14000f62e`
- `KERNEL32!GetProcessHeap` at `0x14000f6d5`
- `KERNEL32!GetProcessHeap` at `0x14000f6f3`
- `KERNEL32!GetProcessHeap` at `0x14000f558`
- `KERNEL32!GetProcessHeap` at `0x14000f62e`
- `KERNEL32!GetProcessHeap` at `0x14000f6d5`
- `KERNEL32!GetProcessHeap` at `0x14000f6f3`

## pseudocode

```c
wchar_t *__fastcall BfspEnvExpandString(__int64 a1, const wchar_t *a2)
{
  int v2; // r15d
  const wchar_t *v3; // rsi
  wchar_t *v4; // r12
  size_t v5; // r13
  __int64 v6; // rax
  size_t v7; // r14
  HANDLE ProcessHeap; // rax
  DWORD v9; // edi
  wchar_t *v10; // r11
  wchar_t *v11; // rbx
  const wchar_t *v12; // r11
  const wchar_t *i; // r14
  wchar_t *v14; // rax
  wchar_t *v15; // rsi
  __int64 v16; // rax
  int v17; // ecx
  HANDLE v18; // rax
  wchar_t *v19; // rax
  const wchar_t *Value; // rax
  __int64 v21; // rcx
  HANDLE v22; // rax
  HANDLE v23; // rax
  DWORD v25; // [rsp+28h] [rbp-30h]
  STRSAFE_LPWSTR ppszDestEnd; // [rsp+30h] [rbp-28h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-20h]
  size_t v28; // [rsp+40h] [rbp-18h]
  int v31; // [rsp+B0h] [rbp+58h]
  size_t pcchRemaining; // [rsp+B8h] [rbp+60h] BYREF

  v2 = 0;
  v3 = a2;
  v4 = 0;
  ppszDestEnd = 0;
  v5 = 0;
  pcchRemaining = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = (unsigned int)(v6 + 1);
  v28 = v7;
  ProcessHeap = GetProcessHeap();
  v9 = 8;
  lpMem = HeapAlloc(ProcessHeap, 8u, 2 * v7);
  v10 = (wchar_t *)lpMem;
  if ( !lpMem )
  {
LABEL_30:
    v11 = 0;
    SetLastError(v9);
    return v11;
  }
  v11 = 0;
LABEL_5:
  StringCchCopyW(v10, v7, v3);
  v31 = 0;
  for ( i = v12; ; i = v15 )
  {
    while ( 1 )
    {
      v14 = wcschr(i, 0x7Cu);
      v15 = v14;
      if ( v14 )
      {
        *v14 = 0;
        v15 = v14 + 1;
      }
      if ( v2 )
        break;
      v16 = -1;
      do
        ++v16;
      while ( i[v16] );
      v17 = v16 + v31;
      v31 += v16;
      if ( v11 )
      {
        StringCchCopyExW(v4, v5, i, &ppszDestEnd, &pcchRemaining, v25);
        v17 = v31;
        v4 = ppszDestEnd;
        v5 = pcchRemaining;
      }
      i = v15;
      v2 = 1;
      if ( !v15 )
      {
        v2 = 0;
        if ( v11 )
        {
          v9 = 0;
          goto LABEL_27;
        }
        v5 = (unsigned int)(v17 + 1);
        pcchRemaining = v5;
        v18 = GetProcessHeap();
        v19 = (wchar_t *)HeapAlloc(v18, 8u, 2 * v5);
        v11 = v19;
        if ( !v19 )
          goto LABEL_27;
        v10 = (wchar_t *)lpMem;
        v4 = v19;
        v3 = a2;
        v7 = v28;
        *v19 = 0;
        ppszDestEnd = v19;
        goto LABEL_5;
      }
    }
    v2 = 0;
    if ( !v15 )
      break;
    Value = (const wchar_t *)BfspEnvGetValue(a1, i);
    if ( !Value )
    {
      v9 = 1168;
      goto LABEL_27;
    }
    v21 = -1;
    do
      ++v21;
    while ( Value[v21] );
    v31 += v21;
    if ( v11 )
    {
      StringCchCopyExW(v4, v5, Value, &ppszDestEnd, &pcchRemaining, v25);
      v4 = ppszDestEnd;
      v5 = pcchRemaining;
    }
  }
  v9 = 87;
LABEL_27:
  v22 = GetProcessHeap();
  HeapFree(v22, 0, lpMem);
  if ( v9 )
  {
    if ( v11 )
    {
      v23 = GetProcessHeap();
      HeapFree(v23, 0, v11);
    }
    goto LABEL_30;
  }
  return v11;
}

```

## disassembly

```asm
0x14000f50c  mov     [rsp-40h+arg_8], rdx
0x14000f511  mov     [rsp-40h+arg_0], rcx
0x14000f516  push    rbp
0x14000f517  push    rbx
0x14000f518  push    rsi
0x14000f519  push    rdi
0x14000f51a  push    r12
0x14000f51c  push    r13
0x14000f51e  push    r14
0x14000f520  push    r15
0x14000f522  mov     rbp, rsp
0x14000f525  sub     rsp, 58h
0x14000f529  xor     r15d, r15d
0x14000f52c  mov     rsi, rdx
0x14000f52f  mov     r12d, r15d
0x14000f532  mov     [rbp+ppszDestEnd], r15
0x14000f536  mov     r13d, r15d
0x14000f539  mov     [rbp+arg_18], r15
0x14000f53d  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000f541  inc     rax
0x14000f544  cmp     [rdx+rax*2], r15w
0x14000f549  jnz     short loc_14000F541
0x14000f54b  inc     eax
0x14000f54d  mov     r14d, eax
0x14000f550  mov     [rbp+var_18], r14
0x14000f554  lea     rbx, [rax+rax]
0x14000f558  call    cs:__imp_GetProcessHeap
0x14000f55e  mov     edi, 8
0x14000f563  mov     r8, rbx; dwBytes
0x14000f566  mov     rcx, rax; hHeap
0x14000f569  mov     edx, edi; dwFlags
0x14000f56b  call    cs:__imp_HeapAlloc
0x14000f571  mov     [rbp+lpMem], rax
0x14000f575  mov     r11, rax
0x14000f578  test    rax, rax
0x14000f57b  jz      loc_14000F707
0x14000f581  mov     rbx, r15
0x14000f584  mov     r8, rsi; pszSrc
0x14000f587  mov     rdx, r14; cchDest
0x14000f58a  mov     rcx, r11; pszDest
0x14000f58d  call    StringCchCopyW
0x14000f592  mov     [rbp+arg_10], r15d
0x14000f596  mov     r14, r11
0x14000f599  mov     edx, 7Ch ; '|'; Ch
0x14000f59e  mov     rcx, r14; Str
0x14000f5a1  call    cs:__imp_wcschr
0x14000f5a7  xor     edx, edx
0x14000f5a9  mov     rsi, rax
0x14000f5ac  test    rax, rax
0x14000f5af  jz      short loc_14000F5B8
0x14000f5b1  mov     [rax], dx
0x14000f5b4  add     rsi, 2
0x14000f5b8  test    r15d, r15d
0x14000f5bb  jnz     loc_14000F66A
0x14000f5c1  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000f5c5  inc     rax
0x14000f5c8  cmp     [r14+rax*2], dx
0x14000f5cd  jnz     short loc_14000F5C5
0x14000f5cf  mov     ecx, [rbp+arg_10]
0x14000f5d2  add     ecx, eax
0x14000f5d4  mov     [rbp+arg_10], ecx
0x14000f5d7  test    rbx, rbx
0x14000f5da  jz      short loc_14000F602
0x14000f5dc  lea     rax, [rbp+arg_18]
0x14000f5e0  mov     r8, r14; pszSrc
0x14000f5e3  lea     r9, [rbp+ppszDestEnd]; ppszDestEnd
0x14000f5e7  mov     [rsp+58h+pcchRemaining], rax; pcchRemaining
0x14000f5ec  mov     rdx, r13; cchDest
0x14000f5ef  mov     rcx, r12; pszDest
0x14000f5f2  call    StringCchCopyExW
0x14000f5f7  mov     ecx, [rbp+arg_10]
0x14000f5fa  mov     r12, [rbp+ppszDestEnd]
0x14000f5fe  mov     r13, [rbp+arg_18]
0x14000f602  mov     r14, rsi
0x14000f605  mov     r15d, 1
0x14000f60b  test    rsi, rsi
0x14000f60e  jnz     short loc_14000F599
0x14000f610  xor     r15d, r15d
0x14000f613  test    rbx, rbx
0x14000f616  jnz     loc_14000F6C4
0x14000f61c  lea     eax, [rcx+1]
0x14000f61f  mov     r13d, eax
0x14000f622  lea     rbx, ds:0[rax*2]
0x14000f62a  mov     [rbp+arg_18], r13
0x14000f62e  call    cs:__imp_GetProcessHeap
0x14000f634  mov     r8, rbx; dwBytes
0x14000f637  mov     edx, edi; dwFlags
0x14000f639  mov     rcx, rax; hHeap
0x14000f63c  call    cs:__imp_HeapAlloc
0x14000f642  mov     rbx, rax
0x14000f645  test    rax, rax
0x14000f648  jz      loc_14000F6D5
0x14000f64e  mov     r11, [rbp+lpMem]
0x14000f652  mov     r12, rax
0x14000f655  mov     rsi, [rbp+arg_8]
0x14000f659  mov     r14, [rbp+var_18]
0x14000f65d  mov     [rax], r15w
0x14000f661  mov     [rbp+ppszDestEnd], rax
0x14000f665  jmp     loc_14000F584
0x14000f66a  xor     r15d, r15d
0x14000f66d  test    rsi, rsi
0x14000f670  jz      short loc_14000F6D0
0x14000f672  mov     rcx, [rbp+arg_0]
0x14000f676  mov     rdx, r14
0x14000f679  call    BfspEnvGetValue
0x14000f67e  test    rax, rax
0x14000f681  jz      short loc_14000F6C9
0x14000f683  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000f687  inc     rcx
0x14000f68a  cmp     [rax+rcx*2], r15w
0x14000f68f  jnz     short loc_14000F687
0x14000f691  add     [rbp+arg_10], ecx
0x14000f694  test    rbx, rbx
0x14000f697  jz      short loc_14000F6BC
0x14000f699  lea     rcx, [rbp+arg_18]
0x14000f69d  mov     r8, rax; pszSrc
0x14000f6a0  mov     [rsp+58h+pcchRemaining], rcx; pcchRemaining
0x14000f6a5  lea     r9, [rbp+ppszDestEnd]; ppszDestEnd
0x14000f6a9  mov     rcx, r12; pszDest
0x14000f6ac  mov     rdx, r13; cchDest
0x14000f6af  call    StringCchCopyExW
0x14000f6b4  mov     r12, [rbp+ppszDestEnd]
0x14000f6b8  mov     r13, [rbp+arg_18]
0x14000f6bc  mov     r14, rsi
0x14000f6bf  jmp     loc_14000F599
0x14000f6c4  mov     edi, r15d
0x14000f6c7  jmp     short loc_14000F6D5
0x14000f6c9  mov     edi, 490h
0x14000f6ce  jmp     short loc_14000F6D5
0x14000f6d0  mov     edi, 57h ; 'W'
0x14000f6d5  call    cs:__imp_GetProcessHeap
0x14000f6db  mov     r8, [rbp+lpMem]; lpMem
0x14000f6df  xor     edx, edx; dwFlags
0x14000f6e1  mov     rcx, rax; hHeap
0x14000f6e4  call    cs:__imp_HeapFree
0x14000f6ea  test    edi, edi
0x14000f6ec  jz      short loc_14000F712
0x14000f6ee  test    rbx, rbx
0x14000f6f1  jz      short loc_14000F707
0x14000f6f3  call    cs:__imp_GetProcessHeap
0x14000f6f9  mov     r8, rbx; lpMem
0x14000f6fc  xor     edx, edx; dwFlags
0x14000f6fe  mov     rcx, rax; hHeap
0x14000f701  call    cs:__imp_HeapFree
0x14000f707  mov     ecx, edi; dwErrCode
0x14000f709  mov     rbx, r15
0x14000f70c  call    cs:__imp_SetLastError
0x14000f712  mov     rax, rbx
0x14000f715  add     rsp, 58h
0x14000f719  pop     r15
0x14000f71b  pop     r14
0x14000f71d  pop     r13
0x14000f71f  pop     r12
0x14000f721  pop     rdi
0x14000f722  pop     rsi
0x14000f723  pop     rbx
0x14000f724  pop     rbp
0x14000f725  retn
```
