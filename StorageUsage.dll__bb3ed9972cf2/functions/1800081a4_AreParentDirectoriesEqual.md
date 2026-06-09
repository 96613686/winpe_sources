# AreParentDirectoriesEqual

- ea: `0x1800081a4`
- end: `0x1800083bb`
- name: `AreParentDirectoriesEqual`
- size: `535`
- prototype: `__int64 __fastcall(PCWSTR pszPathIn, PCWSTR)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path`

## callers

- `0x18000b0e0`

## callees

- `0x1800010b0`
- `0x1800050f0`
- `0x1800081a4`
- `0x1800267e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180008267`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180008267`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800081e0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180008293`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800081e0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180008293`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x1800081f5`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18000820d`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x1800081f5`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18000820d`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180008232`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180008251`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180008232`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180008251`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000827d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000828d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000827d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000828d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AreParentDirectoriesEqual(PCWSTR pszPathIn, PCWSTR a2)
{
  unsigned int v3; // esi
  ULONGLONG TickCount64; // r14
  HRESULT v6; // ebx
  __int64 v7; // rdi
  __int64 v8; // rdx
  __int64 v9; // r8
  PWSTR ppszPathOut; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR pszPath; // [rsp+38h] [rbp-C8h] BYREF
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  HRESULT v14; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  ULONGLONG v16; // [rsp+50h] [rbp-B0h] BYREF
  ULONGLONG v17; // [rsp+58h] [rbp-A8h] BYREF
  ULONGLONG v18; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v19; // [rsp+68h] [rbp-98h] BYREF
  char v20[32]; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v21; // [rsp+90h] [rbp-70h]
  __int64 v22; // [rsp+98h] [rbp-68h]
  ULONGLONG *v23; // [rsp+A0h] [rbp-60h]
  __int64 v24; // [rsp+A8h] [rbp-58h]
  ULONGLONG *v25; // [rsp+B0h] [rbp-50h]
  __int64 v26; // [rsp+B8h] [rbp-48h]
  ULONGLONG *v27; // [rsp+C0h] [rbp-40h]
  __int64 v28; // [rsp+C8h] [rbp-38h]
  int *v29; // [rsp+D0h] [rbp-30h]
  __int64 v30; // [rsp+D8h] [rbp-28h]
  HRESULT *v31; // [rsp+E0h] [rbp-20h]
  __int64 v32; // [rsp+E8h] [rbp-18h]
  __int64 *v33; // [rsp+F0h] [rbp-10h]
  __int64 v34; // [rsp+F8h] [rbp-8h]

  v3 = 0;
  ppszPathOut = 0;
  pszPath = 0;
  TickCount64 = GetTickCount64();
  v6 = PathAllocCanonicalize(pszPathIn, 1u, &ppszPathOut);
  if ( v6 >= 0 )
  {
    v6 = PathAllocCanonicalize(a2, 1u, &pszPath);
    if ( v6 >= 0 )
    {
      v7 = -1;
      v8 = -1;
      do
        ++v8;
      while ( ppszPathOut[v8] );
      v6 = PathCchRemoveFileSpec(ppszPathOut, v8 + 1);
      if ( v6 >= 0 )
      {
        do
          ++v7;
        while ( pszPath[v7] );
        v6 = PathCchRemoveFileSpec(pszPath, v7 + 1);
        if ( v6 >= 0 )
          LOBYTE(v3) = (unsigned int)_o__wcsicmp(ppszPathOut, pszPath) == 0;
      }
    }
  }
  if ( ppszPathOut )
    LocalFree(ppszPathOut);
  if ( pszPath )
    LocalFree(pszPath);
  GetTickCount64();
  if ( (unsigned int)dword_180040048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180040048, 0x400000000000LL) )
  {
    v16 = v9 - TickCount64;
    v21 = &v15;
    v17 = v9 - TickCount64;
    v23 = &v16;
    v18 = v9 - TickCount64;
    v25 = &v17;
    v15 = 1;
    v27 = &v18;
    v22 = 8;
    v29 = &v13;
    v31 = &v14;
    v33 = &v19;
    v24 = 8;
    v26 = 8;
    v28 = 8;
    v13 = 1;
    v30 = 4;
    v14 = v6;
    v32 = 4;
    v19 = 0x1000000;
    v34 = 8;
    tlgWriteAgg((unsigned int)&dword_180040048, (unsigned int)byte_18003696B, 0, 9, (__int64)v20);
  }
  return v3;
}

```

## disassembly

```asm
0x1800081a4  mov     [rsp-8+arg_10], rbx
0x1800081a9  push    rbp
0x1800081aa  push    rsi
0x1800081ab  push    rdi
0x1800081ac  push    r14
0x1800081ae  push    r15
0x1800081b0  lea     rbp, [rsp-10h]
0x1800081b5  sub     rsp, 110h
0x1800081bc  mov     rax, cs:__security_cookie
0x1800081c3  xor     rax, rsp
0x1800081c6  mov     [rbp+30h+var_30], rax
0x1800081ca  xor     r15d, r15d
0x1800081cd  mov     rdi, rdx
0x1800081d0  mov     esi, r15d
0x1800081d3  mov     [rsp+130h+ppszPathOut], r15
0x1800081d8  mov     [rsp+130h+pszPath], r15
0x1800081dd  mov     rbx, rcx
0x1800081e0  call    cs:__imp_GetTickCount64
0x1800081e6  lea     r8, [rsp+130h+ppszPathOut]; ppszPathOut
0x1800081eb  mov     rcx, rbx; pszPathIn
0x1800081ee  lea     edx, [r15+1]; dwFlags
0x1800081f2  mov     r14, rax
0x1800081f5  call    cs:__imp_PathAllocCanonicalize
0x1800081fb  mov     ebx, eax
0x1800081fd  test    eax, eax
0x1800081ff  js      short loc_180008273
0x180008201  lea     r8, [rsp+130h+pszPath]; ppszPathOut
0x180008206  mov     rcx, rdi; pszPathIn
0x180008209  lea     edx, [r15+1]; dwFlags
0x18000820d  call    cs:__imp_PathAllocCanonicalize
0x180008213  mov     ebx, eax
0x180008215  test    eax, eax
0x180008217  js      short loc_180008273
0x180008219  mov     rcx, [rsp+130h+ppszPathOut]; pszPath
0x18000821e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180008222  mov     rdx, rdi
0x180008225  inc     rdx
0x180008228  cmp     [rcx+rdx*2], r15w
0x18000822d  jnz     short loc_180008225
0x18000822f  inc     rdx; cchPath
0x180008232  call    cs:__imp_PathCchRemoveFileSpec
0x180008238  mov     ebx, eax
0x18000823a  test    eax, eax
0x18000823c  js      short loc_180008273
0x18000823e  mov     rcx, [rsp+130h+pszPath]; pszPath
0x180008243  inc     rdi
0x180008246  cmp     [rcx+rdi*2], r15w
0x18000824b  jnz     short loc_180008243
0x18000824d  lea     rdx, [rdi+1]; cchPath
0x180008251  call    cs:__imp_PathCchRemoveFileSpec
0x180008257  mov     ebx, eax
0x180008259  test    eax, eax
0x18000825b  js      short loc_180008273
0x18000825d  mov     rdx, [rsp+130h+pszPath]
0x180008262  mov     rcx, [rsp+130h+ppszPathOut]
0x180008267  call    cs:__imp__o__wcsicmp
0x18000826d  test    eax, eax
0x18000826f  setz    sil
0x180008273  mov     rcx, [rsp+130h+ppszPathOut]; hMem
0x180008278  test    rcx, rcx
0x18000827b  jz      short loc_180008283
0x18000827d  call    cs:__imp_LocalFree
0x180008283  mov     rcx, [rsp+130h+pszPath]; hMem
0x180008288  test    rcx, rcx
0x18000828b  jz      short loc_180008293
0x18000828d  call    cs:__imp_LocalFree
0x180008293  call    cs:__imp_GetTickCount64
0x180008299  mov     r8, rax
0x18000829c  mov     eax, cs:dword_180040048
0x1800082a2  cmp     eax, 5
0x1800082a5  jbe     loc_180008396
0x1800082ab  mov     rdx, 400000000000h
0x1800082b5  lea     rcx, dword_180040048
0x1800082bc  call    _tlgKeywordOn
0x1800082c1  test    al, al
0x1800082c3  jz      loc_180008396
0x1800082c9  sub     r8, r14
0x1800082cc  lea     rax, [rsp+130h+var_E8]
0x1800082d1  mov     [rsp+130h+var_E0], r8
0x1800082d6  mov     [rbp+30h+var_A0], rax
0x1800082da  lea     rdx, byte_18003696B
0x1800082e1  lea     rax, [rsp+130h+var_E0]
0x1800082e6  mov     [rsp+130h+var_D8], r8
0x1800082eb  mov     [rbp+30h+var_90], rax
0x1800082ef  lea     rcx, dword_180040048
0x1800082f6  lea     rax, [rsp+130h+var_D8]
0x1800082fb  mov     [rsp+130h+var_D0], r8
0x180008300  mov     [rbp+30h+var_80], rax
0x180008304  mov     r9d, 9
0x18000830a  lea     rax, [rsp+130h+var_D0]
0x18000830f  mov     [rsp+130h+var_E8], 1
0x180008318  mov     [rbp+30h+var_70], rax
0x18000831c  xor     r8d, r8d
0x18000831f  lea     rax, [rsp+130h+var_F0]
0x180008324  mov     [rbp+30h+var_98], 8
0x18000832c  mov     [rbp+30h+var_60], rax
0x180008330  lea     rax, [rsp+130h+var_EC]
0x180008335  mov     [rbp+30h+var_50], rax
0x180008339  lea     rax, [rsp+130h+var_C8]
0x18000833e  mov     [rbp+30h+var_40], rax
0x180008342  lea     rax, [rsp+130h+var_C0]
0x180008347  mov     [rsp+130h+var_110], rax
0x18000834c  mov     [rbp+30h+var_88], 8
0x180008354  mov     [rbp+30h+var_78], 8
0x18000835c  mov     [rbp+30h+var_68], 8
0x180008364  mov     [rsp+130h+var_F0], 1
0x18000836c  mov     [rbp+30h+var_58], 4
0x180008374  mov     [rsp+130h+var_EC], ebx
0x180008378  mov     [rbp+30h+var_48], 4
0x180008380  mov     [rsp+130h+var_C8], 1000000h
0x180008389  mov     [rbp+30h+var_38], 8
0x180008391  call    _tlgWriteAgg
0x180008396  mov     eax, esi
0x180008398  mov     rcx, [rbp+30h+var_30]
0x18000839c  xor     rcx, rsp; StackCookie
0x18000839f  call    __security_check_cookie
0x1800083a4  mov     rbx, [rsp+130h+arg_10]
0x1800083ac  add     rsp, 110h
0x1800083b3  pop     r15
0x1800083b5  pop     r14
0x1800083b7  pop     rdi
0x1800083b8  pop     rsi
0x1800083b9  pop     rbp
0x1800083ba  retn
```
