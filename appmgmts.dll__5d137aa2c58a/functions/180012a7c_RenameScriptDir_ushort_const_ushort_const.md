# RenameScriptDir(ushort const *,ushort const *)

- ea: `0x180012a7c`
- end: `0x180012bbd`
- name: `?RenameScriptDir@@YAKPEBG0@Z`
- size: `321`
- prototype: `DWORD __fastcall(const unsigned __int16 *, const unsigned __int16 *Src)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000e8e8`

## callees

- `0x180002aa0`
- `0x180012a7c`
- `0x18002ada8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180012a9d`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180012ab0`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180012a9d`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180012ab0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ba2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ba2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012b61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012b98`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012b61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012b98`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012b08`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012b08`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180012b8d`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180012b8d`

## pseudocode

```c
DWORD __fastcall RenameScriptDir(const unsigned __int16 *a1, const unsigned __int16 *Src)
{
  wchar_t *v4; // r12
  __int64 v5; // rsi
  wchar_t *v6; // r13
  __int64 v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // r15
  unsigned __int64 v10; // rcx
  SIZE_T v11; // rax
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rdi
  size_t v14; // rbx
  int v15; // ebx
  BOOL v17; // ebx

  v4 = wcsrchr(Src, 0x5Cu);
  *v4 = 0;
  v5 = -1;
  v6 = wcsrchr(Src, 0x5Cu);
  *v6 = 0;
  if ( Src )
  {
    v7 = -1;
    do
      ++v7;
    while ( Src[v7] );
  }
  else
  {
    LODWORD(v7) = 0;
  }
  if ( a1 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a1[v8] );
  }
  else
  {
    v8 = 0;
  }
  v9 = (unsigned int)(v7 + 1);
  v10 = v9 + v8 + 1;
  v11 = 2 * v10;
  if ( !is_mul_ok(v10, 2u) )
    v11 = -1;
  v12 = (unsigned __int16 *)LocalAlloc(0, v11);
  v13 = v12;
  if ( !v12 )
    goto LABEL_17;
  v14 = (unsigned int)v7;
  memcpy_0(v12, Src, v14 * 2);
  v13[v14] = 92;
  if ( a1 )
  {
    do
      ++v5;
    while ( a1[v5] );
  }
  else
  {
    v5 = 0;
  }
  v15 = StringCchCopyW(&v13[v9], v5 + 1, a1);
  if ( v15 < 0 )
  {
    LocalFree(v13);
    return v15;
  }
  else
  {
LABEL_17:
    *v6 = 92;
    *v4 = 92;
    if ( v13 )
    {
      v17 = MoveFileExW(v13, Src, 0);
      LocalFree(v13);
      if ( v17 )
        return 0;
      else
        return GetLastError();
    }
    else
    {
      return 14;
    }
  }
}

```

## disassembly

```asm
0x180012a7c  push    rbx
0x180012a7e  push    rbp
0x180012a7f  push    rsi
0x180012a80  push    rdi
0x180012a81  push    r12
0x180012a83  push    r13
0x180012a85  push    r14
0x180012a87  push    r15
0x180012a89  sub     rsp, 28h
0x180012a8d  mov     r14, rdx
0x180012a90  mov     rbp, rcx
0x180012a93  mov     ebx, 5Ch ; '\'
0x180012a98  mov     rcx, r14; Str
0x180012a9b  mov     edx, ebx; Ch
0x180012a9d  call    cs:__imp_wcsrchr
0x180012aa3  xor     edi, edi
0x180012aa5  mov     edx, ebx; Ch
0x180012aa7  mov     rcx, r14; Str
0x180012aaa  mov     r12, rax
0x180012aad  mov     [rax], di
0x180012ab0  call    cs:__imp_wcsrchr
0x180012ab6  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180012aba  mov     r13, rax
0x180012abd  mov     [rax], di
0x180012ac0  test    r14, r14
0x180012ac3  jnz     short loc_180012AC9
0x180012ac5  mov     ebx, edi
0x180012ac7  jmp     short loc_180012AD6
0x180012ac9  mov     rbx, rsi
0x180012acc  inc     rbx
0x180012acf  cmp     [r14+rbx*2], di
0x180012ad4  jnz     short loc_180012ACC
0x180012ad6  test    rbp, rbp
0x180012ad9  jnz     short loc_180012AE0
0x180012adb  mov     rcx, rdi
0x180012ade  jmp     short loc_180012AED
0x180012ae0  mov     rcx, rsi
0x180012ae3  inc     rcx
0x180012ae6  cmp     [rbp+rcx*2+0], di
0x180012aeb  jnz     short loc_180012AE3
0x180012aed  inc     rcx
0x180012af0  lea     r15d, [rbx+1]
0x180012af4  add     rcx, r15
0x180012af7  mov     eax, 2
0x180012afc  mul     rcx
0x180012aff  cmovb   rax, rsi
0x180012b03  xor     ecx, ecx; uFlags
0x180012b05  mov     rdx, rax; uBytes
0x180012b08  call    cs:__imp_LocalAlloc
0x180012b0e  mov     rdi, rax
0x180012b11  test    rax, rax
0x180012b14  jz      short loc_180012B6B
0x180012b16  mov     ecx, ebx
0x180012b18  mov     rdx, r14; Src
0x180012b1b  lea     rbx, [rcx+rcx]
0x180012b1f  mov     rcx, rax; void *
0x180012b22  mov     r8, rbx; Size
0x180012b25  call    memcpy_0
0x180012b2a  xor     r11d, r11d
0x180012b2d  mov     word ptr [rbx+rdi], 5Ch ; '\'
0x180012b33  test    rbp, rbp
0x180012b36  jnz     short loc_180012B3D
0x180012b38  mov     esi, r11d
0x180012b3b  jmp     short loc_180012B48
0x180012b3d  inc     rsi
0x180012b40  cmp     [rbp+rsi*2+0], r11w
0x180012b46  jnz     short loc_180012B3D
0x180012b48  lea     rdx, [rsi+1]; unsigned __int64
0x180012b4c  mov     r8, rbp; unsigned __int16 *
0x180012b4f  lea     rcx, [rdi+r15*2]; unsigned __int16 *
0x180012b53  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180012b58  mov     ebx, eax
0x180012b5a  test    eax, eax
0x180012b5c  jns     short loc_180012B6B
0x180012b5e  mov     rcx, rdi; hMem
0x180012b61  call    cs:__imp_LocalFree
0x180012b67  mov     eax, ebx
0x180012b69  jmp     short loc_180012BAC
0x180012b6b  mov     eax, 5Ch ; '\'
0x180012b70  mov     [r13+0], ax
0x180012b75  mov     [r12], ax
0x180012b7a  test    rdi, rdi
0x180012b7d  jnz     short loc_180012B84
0x180012b7f  lea     eax, [rdi+0Eh]
0x180012b82  jmp     short loc_180012BAC
0x180012b84  xor     r8d, r8d; dwFlags
0x180012b87  mov     rdx, r14; lpNewFileName
0x180012b8a  mov     rcx, rdi; lpExistingFileName
0x180012b8d  call    cs:__imp_MoveFileExW
0x180012b93  mov     rcx, rdi; hMem
0x180012b96  mov     ebx, eax
0x180012b98  call    cs:__imp_LocalFree
0x180012b9e  test    ebx, ebx
0x180012ba0  jnz     short loc_180012BAA
0x180012ba2  call    cs:__imp_GetLastError
0x180012ba8  jmp     short loc_180012BAC
0x180012baa  xor     eax, eax
0x180012bac  add     rsp, 28h
0x180012bb0  pop     r15
0x180012bb2  pop     r14
0x180012bb4  pop     r13
0x180012bb6  pop     r12
0x180012bb8  pop     rdi
0x180012bb9  pop     rsi
0x180012bba  pop     rbp
0x180012bbb  pop     rbx
0x180012bbc  retn
```
