# CabUnzip(ushort const *,ushort const *,CAB_COMMAND (*)(ushort const *,void *),void *)

- ea: `0x18000c398`
- end: `0x18000c470`
- name: `?CabUnzip@@YAKPEBG0P6A?AW4CAB_COMMAND@@0PEAX@Z1@Z`
- size: `216`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPCWSTR, enum CAB_COMMAND (__high *)(const unsigned __int16 *, void *), __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007380`
- `0x18000b7a0`
- `0x18000dabc`

## callees

- `0x18000c284`
- `0x18000c398`
- `0x18000ca5c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000c41a`
- `KERNEL32!GetProcessHeap` at `0x18000c44c`
- `KERNEL32!GetProcessHeap` at `0x18000c41a`
- `KERNEL32!GetProcessHeap` at `0x18000c44c`
- `KERNEL32!HeapFree` at `0x18000c428`
- `KERNEL32!HeapFree` at `0x18000c45a`
- `KERNEL32!HeapFree` at `0x18000c428`
- `KERNEL32!HeapFree` at `0x18000c45a`
- `KERNEL32!GetFileAttributesW` at `0x18000c3c7`
- `KERNEL32!GetFileAttributesW` at `0x18000c3d9`
- `KERNEL32!GetFileAttributesW` at `0x18000c3c7`
- `KERNEL32!GetFileAttributesW` at `0x18000c3d9`
- `Cabinet!__imp_FDIDestroy` at `0x18000c408`
- `Cabinet!__imp_FDIDestroy` at `0x18000c43a`
- `Cabinet!__imp_FDIDestroy` at `0x18000c408`
- `Cabinet!__imp_FDIDestroy` at `0x18000c43a`

## pseudocode

```c
__int64 __fastcall CabUnzip(
        LPCWSTR lpFileName,
        LPCWSTR a2,
        enum CAB_COMMAND (__high *a3)(const unsigned __int16 *, void *),
        __int64 a4)
{
  struct _CAB_STRUCT *v8; // rbx
  DWORD FileAttributesW; // eax
  DWORD v11; // eax
  unsigned int v12; // edi
  HANDLE v13; // rax
  HANDLE ProcessHeap; // rax

  v8 = CabInit();
  if ( !v8 )
    return 110;
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW == -1
    || (FileAttributesW & 0x10) != 0
    || (v11 = GetFileAttributesW(a2), v11 == -1)
    || (v11 & 0x10) == 0 )
  {
    if ( *(_QWORD *)v8 )
      FDIDestroy(*(HFDI *)v8);
    *(_OWORD *)v8 = 0;
    *((_QWORD *)v8 + 2) = 0;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
    return 87;
  }
  else
  {
    v12 = CabUnzip((__int64)v8, lpFileName, (__int64)a2, (__int64)a3, a4);
    if ( *(_QWORD *)v8 )
      FDIDestroy(*(HFDI *)v8);
    *(_OWORD *)v8 = 0;
    *((_QWORD *)v8 + 2) = 0;
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v8);
    return v12;
  }
}

```

## disassembly

```asm
0x18000c398  push    rbx
0x18000c39a  push    rbp
0x18000c39b  push    rsi
0x18000c39c  push    rdi
0x18000c39d  push    r14
0x18000c39f  sub     rsp, 30h
0x18000c3a3  mov     rbp, r9
0x18000c3a6  mov     r14, r8
0x18000c3a9  mov     rsi, rdx
0x18000c3ac  mov     rdi, rcx
0x18000c3af  call    ?CabInit@@YAPEAU_CAB_STRUCT@@XZ; CabInit(void)
0x18000c3b4  mov     rbx, rax
0x18000c3b7  test    rax, rax
0x18000c3ba  jnz     short loc_18000C3C4
0x18000c3bc  lea     eax, [rbx+6Eh]
0x18000c3bf  jmp     loc_18000C465
0x18000c3c4  mov     rcx, rdi; lpFileName
0x18000c3c7  call    cs:__imp_GetFileAttributesW
0x18000c3cd  cmp     eax, 0FFFFFFFFh
0x18000c3d0  jz      short loc_18000C432
0x18000c3d2  test    al, 10h
0x18000c3d4  jnz     short loc_18000C432
0x18000c3d6  mov     rcx, rsi; lpFileName
0x18000c3d9  call    cs:__imp_GetFileAttributesW
0x18000c3df  cmp     eax, 0FFFFFFFFh
0x18000c3e2  jz      short loc_18000C432
0x18000c3e4  test    al, 10h
0x18000c3e6  jz      short loc_18000C432
0x18000c3e8  mov     r9, r14
0x18000c3eb  mov     [rsp+58h+var_38], rbp
0x18000c3f0  mov     r8, rsi
0x18000c3f3  mov     rdx, rdi
0x18000c3f6  mov     rcx, rbx
0x18000c3f9  call    _CabUnzip
0x18000c3fe  mov     rcx, [rbx]; hfdi
0x18000c401  mov     edi, eax
0x18000c403  test    rcx, rcx
0x18000c406  jz      short loc_18000C40E
0x18000c408  call    cs:__imp_FDIDestroy
0x18000c40e  xorps   xmm0, xmm0
0x18000c411  xor     eax, eax
0x18000c413  movups  xmmword ptr [rbx], xmm0
0x18000c416  mov     [rbx+10h], rax
0x18000c41a  call    cs:__imp_GetProcessHeap
0x18000c420  mov     r8, rbx; lpMem
0x18000c423  xor     edx, edx; dwFlags
0x18000c425  mov     rcx, rax; hHeap
0x18000c428  call    cs:__imp_HeapFree
0x18000c42e  mov     eax, edi
0x18000c430  jmp     short loc_18000C465
0x18000c432  mov     rcx, [rbx]; hfdi
0x18000c435  test    rcx, rcx
0x18000c438  jz      short loc_18000C440
0x18000c43a  call    cs:__imp_FDIDestroy
0x18000c440  xorps   xmm0, xmm0
0x18000c443  xor     eax, eax
0x18000c445  movups  xmmword ptr [rbx], xmm0
0x18000c448  mov     [rbx+10h], rax
0x18000c44c  call    cs:__imp_GetProcessHeap
0x18000c452  mov     r8, rbx; lpMem
0x18000c455  xor     edx, edx; dwFlags
0x18000c457  mov     rcx, rax; hHeap
0x18000c45a  call    cs:__imp_HeapFree
0x18000c460  mov     eax, 57h ; 'W'
0x18000c465  add     rsp, 30h
0x18000c469  pop     r14
0x18000c46b  pop     rdi
0x18000c46c  pop     rsi
0x18000c46d  pop     rbp
0x18000c46e  pop     rbx
0x18000c46f  retn
```
