# check_symlinks

- ea: `0x1800f5838`
- end: `0x1800f5ac3`
- name: `check_symlinks`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path`

## callers

- `0x1800f5030`

## callees

- `0x180006c00`
- `0x180014fc0`
- `0x1800ed6c0`
- `0x1800f5838`
- `0x1800f656c`
- `0x1800f65c4`
- `0x1800f661c`
- `0x1800f7890`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f5914`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f5a0b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f5914`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f5a0b`

## string_xrefs

- `0x1800f5a14`: `Could not remove symlink %ls`
- `0x1800f5a53`: `Removing symlink %ls`
- `0x1800f599a`: `Cannot remove intervening symlink %ls`
- `0x1800f59bf`: `Cannot extract through symlink %ls`

## pseudocode

```c
__int64 __fastcall check_symlinks(__int64 a1)
{
  __int16 *v1; // rsi
  _WORD **v2; // r14
  __int16 v4; // ax
  _WORD *v5; // rcx
  __int16 v6; // bx
  __int16 v7; // ax
  int v8; // eax
  const WCHAR *v9; // rcx
  int v10; // eax
  __int64 result; // rax
  const WCHAR *v12; // rcx
  int v13; // eax
  const wchar_t *v14; // rbx
  unsigned int *v15; // rax
  __int16 v16; // ax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int16 v19; // [rsp+30h] [rbp-68h] BYREF
  struct _BY_HANDLE_FILE_INFORMATION v20; // [rsp+38h] [rbp-60h] BYREF

  v1 = *(__int16 **)(a1 + 352);
  v2 = (_WORD **)(a1 + 256);
  memset(&v20, 0, sizeof(v20));
  v19 = 0;
  v4 = *v1;
  if ( *v1 )
  {
    v5 = *v2;
    do
    {
      if ( *v5 != v4 )
        break;
      ++v1;
      ++v5;
      v4 = *v1;
    }
    while ( *v1 );
  }
  while ( 1 )
  {
    v6 = *v1;
    if ( *v1 != 92 )
      break;
    ++v1;
  }
  while ( 1 )
  {
    v7 = *v1;
    if ( !*v1 )
      goto LABEL_41;
    if ( v7 == 92 )
      break;
    do
    {
      v7 = *++v1;
      if ( !*v1 )
        break;
LABEL_11:
      ;
    }
    while ( v7 != 92 );
    v6 = *v1;
    *v1 = 0;
    if ( (unsigned int)file_information(a1, *(const WCHAR **)(a1 + 352), &v20, &v19, 1) )
    {
      if ( *(_DWORD *)_o__errno() == 2 )
        goto LABEL_41;
LABEL_15:
      if ( !v6 )
        goto LABEL_41;
      goto LABEL_16;
    }
    if ( (v19 & 0xF000) != 0xA000 )
      goto LABEL_15;
    if ( !v6 )
    {
      if ( (*(_DWORD *)(a1 + 424) & 0x20000) != 0 )
        set_fflags_platform(*(LPCWSTR *)(a1 + 352), 0, 1);
      v12 = *(const WCHAR **)(a1 + 352);
      if ( (v20.dwFileAttributes & 0x10) != 0 )
        v13 = disk_rmdir(v12);
      else
        v13 = disk_unlink(v12);
      if ( v13 )
      {
        v14 = *(const wchar_t **)(a1 + 352);
        v15 = (unsigned int *)_o__errno();
        archive_set_error(a1, *v15, "Could not remove symlink %ls", v14);
        result = 4294967271LL;
      }
      else
      {
        v16 = *(_WORD *)(a1 + 476) & 0xF000;
        *(_QWORD *)(a1 + 336) = 0;
        if ( v16 != -24576 )
          archive_set_error(a1, 0, "Removing symlink %ls", *(const wchar_t **)(a1 + 352));
        result = 0;
      }
      *v1 = 0;
      return result;
    }
    v8 = *(_DWORD *)(a1 + 424);
    if ( (v8 & 0x10) == 0 )
    {
      archive_set_error(a1, 0, "Cannot extract through symlink %ls", *(_QWORD *)(a1 + 352));
      goto LABEL_28;
    }
    if ( (v8 & 0x20000) != 0 )
      set_fflags_platform(*(LPCWSTR *)(a1 + 352), 0, 1);
    v9 = *(const WCHAR **)(a1 + 352);
    if ( (v20.dwFileAttributes & 0x10) != 0 )
      v10 = disk_rmdir(v9);
    else
      v10 = disk_unlink(v9);
    if ( v10 )
    {
      archive_set_error(a1, 0, "Cannot remove intervening symlink %ls", *(_QWORD *)(a1 + 352));
LABEL_28:
      result = 4294967271LL;
      *v1 = v6;
      return result;
    }
    *(_QWORD *)(a1 + 336) = 0;
LABEL_16:
    *v1++ = v6;
  }
  if ( v1[1] )
    goto LABEL_11;
LABEL_41:
  *v1 = v6;
  v17 = *(_QWORD *)(a1 + 352);
  *(_QWORD *)(a1 + 264) = 0;
  if ( v17 )
  {
    v18 = -1;
    do
      ++v18;
    while ( *(_WORD *)(v17 + 2 * v18) );
  }
  archive_wstrncat(v2, v17);
  return 0;
}

```

## disassembly

```asm
0x1800f5838  mov     [rsp+arg_8], rbx
0x1800f583d  mov     [rsp+arg_10], rbp
0x1800f5842  push    rsi
0x1800f5843  push    rdi
0x1800f5844  push    r14
0x1800f5846  sub     rsp, 80h
0x1800f584d  mov     rax, cs:__security_cookie
0x1800f5854  xor     rax, rsp
0x1800f5857  mov     [rsp+98h+var_28], rax
0x1800f585c  mov     rsi, [rcx+160h]
0x1800f5863  lea     r14, [rcx+100h]
0x1800f586a  xorps   xmm0, xmm0
0x1800f586d  xor     eax, eax
0x1800f586f  xor     ebp, ebp
0x1800f5871  mov     [rsp+98h+var_30], eax
0x1800f5875  movups  [rsp+98h+var_60], xmm0
0x1800f587a  mov     rdi, rcx
0x1800f587d  mov     [rsp+98h+var_68], bp
0x1800f5882  movups  [rsp+98h+var_50], xmm0
0x1800f5887  movups  [rsp+98h+var_40], xmm0
0x1800f588c  movzx   eax, word ptr [rsi]
0x1800f588f  test    ax, ax
0x1800f5892  jz      short loc_1800F58B2
0x1800f5894  mov     rcx, [r14]
0x1800f5897  cmp     [rcx], ax
0x1800f589a  jnz     short loc_1800F58B2
0x1800f589c  add     rsi, 2
0x1800f58a0  add     rcx, 2
0x1800f58a4  movzx   eax, word ptr [rsi]
0x1800f58a7  test    ax, ax
0x1800f58aa  jnz     short loc_1800F5897
0x1800f58ac  jmp     short loc_1800F58B2
0x1800f58ae  add     rsi, 2
0x1800f58b2  movzx   ebx, word ptr [rsi]
0x1800f58b5  cmp     bx, 5Ch ; '\'
0x1800f58b9  jz      short loc_1800F58AE
0x1800f58bb  movzx   eax, word ptr [rsi]
0x1800f58be  test    ax, ax
0x1800f58c1  jz      loc_1800F5A6B
0x1800f58c7  cmp     ax, 5Ch ; '\'
0x1800f58cb  jnz     short loc_1800F58DD
0x1800f58cd  cmp     [rsi+2], bp
0x1800f58d1  jz      loc_1800F5A6B
0x1800f58d7  cmp     ax, 5Ch ; '\'
0x1800f58db  jz      short loc_1800F58E9
0x1800f58dd  add     rsi, 2
0x1800f58e1  movzx   eax, word ptr [rsi]
0x1800f58e4  test    ax, ax
0x1800f58e7  jnz     short loc_1800F58D7
0x1800f58e9  movzx   ebx, word ptr [rsi]
0x1800f58ec  lea     r9, [rsp+98h+var_68]
0x1800f58f1  mov     [rsi], bp
0x1800f58f4  lea     r8, [rsp+98h+var_60]
0x1800f58f9  mov     rdx, [rdi+160h]
0x1800f5900  mov     rcx, rdi
0x1800f5903  mov     [rsp+98h+var_78], 1
0x1800f590b  call    file_information
0x1800f5910  test    eax, eax
0x1800f5912  jz      short loc_1800F5935
0x1800f5914  call    cs:__imp__o__errno
0x1800f591a  cmp     dword ptr [rax], 2
0x1800f591d  jz      loc_1800F5A6B
0x1800f5923  test    bx, bx
0x1800f5926  jz      loc_1800F5A6B
0x1800f592c  mov     [rsi], bx
0x1800f592f  add     rsi, 2
0x1800f5933  jmp     short loc_1800F58BB
0x1800f5935  movzx   eax, [rsp+98h+var_68]
0x1800f593a  mov     ecx, 0F000h
0x1800f593f  and     ax, cx
0x1800f5942  mov     ecx, 0A000h
0x1800f5947  cmp     ax, cx
0x1800f594a  jnz     short loc_1800F5923
0x1800f594c  test    bx, bx
0x1800f594f  jz      short loc_1800F59C8
0x1800f5951  mov     eax, [rdi+1A8h]
0x1800f5957  test    al, 10h
0x1800f5959  jz      short loc_1800F59BF
0x1800f595b  bt      eax, 11h
0x1800f595f  jnb     short loc_1800F5973
0x1800f5961  mov     rcx, [rdi+160h]; lpFileName
0x1800f5968  xor     edx, edx
0x1800f596a  lea     r8d, [rdx+1]
0x1800f596e  call    set_fflags_platform
0x1800f5973  test    byte ptr [rsp+98h+var_60], 10h
0x1800f5978  mov     rcx, [rdi+160h]; lpFileName
0x1800f597f  jz      short loc_1800F5988
0x1800f5981  call    disk_rmdir
0x1800f5986  jmp     short loc_1800F598D
0x1800f5988  call    disk_unlink
0x1800f598d  test    eax, eax
0x1800f598f  jnz     short loc_1800F599A
0x1800f5991  mov     [rdi+150h], rbp
0x1800f5998  jmp     short loc_1800F592C
0x1800f599a  lea     r8, aCannotRemoveIn; "Cannot remove intervening symlink %ls"
0x1800f59a1  mov     r9, [rdi+160h]
0x1800f59a8  xor     edx, edx
0x1800f59aa  mov     rcx, rdi
0x1800f59ad  call    archive_set_error
0x1800f59b2  mov     eax, 0FFFFFFE7h
0x1800f59b7  mov     [rsi], bx
0x1800f59ba  jmp     loc_1800F5A9E
0x1800f59bf  lea     r8, aCannotExtractT; "Cannot extract through symlink %ls"
0x1800f59c6  jmp     short loc_1800F59A1
0x1800f59c8  test    dword ptr [rdi+1A8h], 20000h
0x1800f59d2  jz      short loc_1800F59E6
0x1800f59d4  mov     rcx, [rdi+160h]; lpFileName
0x1800f59db  xor     edx, edx
0x1800f59dd  lea     r8d, [rdx+1]
0x1800f59e1  call    set_fflags_platform
0x1800f59e6  test    byte ptr [rsp+98h+var_60], 10h
0x1800f59eb  mov     rcx, [rdi+160h]; lpFileName
0x1800f59f2  jz      short loc_1800F59FB
0x1800f59f4  call    disk_rmdir
0x1800f59f9  jmp     short loc_1800F5A00
0x1800f59fb  call    disk_unlink
0x1800f5a00  test    eax, eax
0x1800f5a02  jz      short loc_1800F5A2C
0x1800f5a04  mov     rbx, [rdi+160h]
0x1800f5a0b  call    cs:__imp__o__errno
0x1800f5a11  mov     r9, rbx
0x1800f5a14  lea     r8, aCouldNotRemove; "Could not remove symlink %ls"
0x1800f5a1b  mov     rcx, rdi
0x1800f5a1e  mov     edx, [rax]
0x1800f5a20  call    archive_set_error
0x1800f5a25  mov     eax, 0FFFFFFE7h
0x1800f5a2a  jmp     short loc_1800F5A66
0x1800f5a2c  movzx   eax, word ptr [rdi+1DCh]
0x1800f5a33  mov     ecx, 0F000h
0x1800f5a38  and     ax, cx
0x1800f5a3b  mov     [rdi+150h], rbp
0x1800f5a42  mov     ecx, 0A000h
0x1800f5a47  cmp     ax, cx
0x1800f5a4a  jz      short loc_1800F5A64
0x1800f5a4c  mov     r9, [rdi+160h]
0x1800f5a53  lea     r8, aRemovingSymlin; "Removing symlink %ls"
0x1800f5a5a  xor     edx, edx
0x1800f5a5c  mov     rcx, rdi
0x1800f5a5f  call    archive_set_error
0x1800f5a64  mov     eax, ebp
0x1800f5a66  mov     [rsi], bp
0x1800f5a69  jmp     short loc_1800F5A9E
0x1800f5a6b  mov     [rsi], bx
0x1800f5a6e  mov     rdx, [rdi+160h]
0x1800f5a75  mov     [rdi+108h], rbp
0x1800f5a7c  test    rdx, rdx
0x1800f5a7f  jnz     short loc_1800F5A86
0x1800f5a81  mov     r8, rbp
0x1800f5a84  jmp     short loc_1800F5A94
0x1800f5a86  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800f5a8a  inc     r8
0x1800f5a8d  cmp     [rdx+r8*2], bp
0x1800f5a92  jnz     short loc_1800F5A8A
0x1800f5a94  mov     rcx, r14
0x1800f5a97  call    archive_wstrncat
0x1800f5a9c  xor     eax, eax
0x1800f5a9e  mov     rcx, [rsp+98h+var_28]
0x1800f5aa3  xor     rcx, rsp; StackCookie
0x1800f5aa6  call    __security_check_cookie
0x1800f5aab  lea     r11, [rsp+98h+var_18]
0x1800f5ab3  mov     rbx, [r11+28h]
0x1800f5ab7  mov     rbp, [r11+30h]
0x1800f5abb  mov     rsp, r11
0x1800f5abe  pop     r14
0x1800f5ac0  pop     rdi
0x1800f5ac1  pop     rsi
0x1800f5ac2  retn
```
