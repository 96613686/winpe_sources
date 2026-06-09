# create_dir

- ea: `0x1800f5e24`
- end: `0x1800f608f`
- name: `create_dir`
- size: `619`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1800f5e24`
- `0x1800f7330`

## callees

- `0x180006c00`
- `0x1800149c0`
- `0x180014fc0`
- `0x1800ef3f8`
- `0x1800f5e24`
- `0x1800f65c4`
- `0x1800f661c`
- `0x1800f6e2c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f5f32`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f5f43`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f5f4e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f5f59`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f5f9a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f605d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f5f32`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f5f43`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f5f4e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f5f59`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f5f9a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f605d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f5fe9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f602a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f5fe9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f602a`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800f5e7b`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800f5e7b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800f5fad`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800f5fad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f601a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f601a`

## string_xrefs

- `0x1800f5f05`: `Can't create directory '%ls'`
- `0x1800f5f38`: `Can't create directory '%ls': Conflicting file cannot be removed`
- `0x1800f5f5f`: `Can't test directory '%ls'`
- `0x1800f6063`: `Failed to create dir '%ls'`

## pseudocode

```c
__int64 __fastcall create_dir(__int64 a1, const wchar_t *a2)
{
  wchar_t *v4; // rax
  wchar_t *v5; // rsi
  const wchar_t *v6; // rax
  const char *v7; // r8
  __int64 v8; // rdx
  __int64 result; // rax
  unsigned int *v10; // rax
  __int16 v11; // si
  wchar_t *v12; // rax
  wchar_t *v13; // rbp
  __int16 v14; // si
  __int64 v15; // rax
  DWORD LastError; // eax
  __int16 v17; // [rsp+30h] [rbp-78h] BYREF
  struct _BY_HANDLE_FILE_INFORMATION v18; // [rsp+38h] [rbp-70h] BYREF

  v17 = 0;
  memset(&v18, 0, sizeof(v18));
  v4 = wcsrchr(a2, 0x5Cu);
  v5 = v4;
  if ( v4 )
    v6 = v4 + 1;
  else
    v6 = a2;
  if ( !*v6 || *v6 == 46 && (!v6[1] || v6[1] == 46 && !v6[2]) )
  {
    if ( v5 )
    {
      *v5 = 0;
      result = create_dir(a1, a2);
      *v5 = 92;
      return result;
    }
    return 0;
  }
  if ( !(unsigned int)file_information(a1, a2, &v18, &v17, 0) )
  {
    if ( (v17 & 0xF000) == 0x4000 )
      return 0;
    if ( (*(_BYTE *)(a1 + 424) & 8) != 0 )
    {
      v7 = "Can't create directory '%ls'";
      v8 = 17;
LABEL_13:
      archive_set_error(a1, v8, v7, a2);
      return 4294967271LL;
    }
    if ( (unsigned int)disk_unlink(a2) )
    {
      v10 = (unsigned int *)_o__errno();
      v7 = "Can't create directory '%ls': Conflicting file cannot be removed";
LABEL_16:
      v8 = *v10;
      goto LABEL_13;
    }
LABEL_22:
    v11 = *(_WORD *)(a1 + 144);
    v12 = _la_win_permissive_name_w(a2);
    v13 = v12;
    if ( !v12 )
    {
      *(_DWORD *)_o__errno() = 22;
LABEL_31:
      free(v13);
      if ( (unsigned int)file_information(a1, a2, &v18, &v17, 0) || (v17 & 0xF000) != 0x4000 )
      {
        v10 = (unsigned int *)_o__errno();
        v7 = "Failed to create dir '%ls'";
        goto LABEL_16;
      }
      return 0;
    }
    if ( !CreateDirectoryW(v12, 0) )
    {
      LastError = GetLastError();
      _la_dosmaperr(LastError);
      goto LABEL_31;
    }
    v14 = ~v11 & 0x1FF;
    if ( (v14 & 0x3D | 0x1C0) != v14 )
    {
      v15 = new_fixup(a1, a2);
      *(_DWORD *)(v15 + 124) |= 0x20000000u;
      *(_WORD *)(v15 + 64) = v14;
    }
    free(v13);
    return 0;
  }
  if ( *(_DWORD *)_o__errno() != 2 && *(_DWORD *)_o__errno() != 20 )
  {
    v10 = (unsigned int *)_o__errno();
    v7 = "Can't test directory '%ls'";
    goto LABEL_16;
  }
  if ( !v5 )
    goto LABEL_22;
  *v5 = 0;
  result = create_dir(a1, a2);
  *v5 = 92;
  if ( !(_DWORD)result )
    goto LABEL_22;
  return result;
}

```

## disassembly

```asm
0x1800f5e24  mov     [rsp+arg_10], rbx
0x1800f5e29  mov     [rsp+arg_18], rbp
0x1800f5e2e  push    rsi
0x1800f5e2f  push    rdi
0x1800f5e30  push    r12
0x1800f5e32  push    r14
0x1800f5e34  push    r15
0x1800f5e36  sub     rsp, 80h
0x1800f5e3d  mov     rax, cs:__security_cookie
0x1800f5e44  xor     rax, rsp
0x1800f5e47  mov     [rsp+0A8h+var_38], rax
0x1800f5e4c  xorps   xmm0, xmm0
0x1800f5e4f  xor     eax, eax
0x1800f5e51  mov     rbx, rdx
0x1800f5e54  mov     [rsp+0A8h+var_40], eax
0x1800f5e58  mov     rdi, rcx
0x1800f5e5b  xor     r14d, r14d
0x1800f5e5e  mov     rcx, rbx; Str
0x1800f5e61  mov     [rsp+0A8h+var_78], r14w
0x1800f5e67  lea     ebp, [rax+5Ch]
0x1800f5e6a  mov     edx, ebp; Ch
0x1800f5e6c  movups  [rsp+0A8h+var_70], xmm0
0x1800f5e71  movups  [rsp+0A8h+var_60], xmm0
0x1800f5e76  movups  [rsp+0A8h+var_50], xmm0
0x1800f5e7b  call    cs:__imp_wcsrchr
0x1800f5e81  mov     rsi, rax
0x1800f5e84  test    rax, rax
0x1800f5e87  jnz     short loc_1800F5E8E
0x1800f5e89  mov     rax, rbx
0x1800f5e8c  jmp     short loc_1800F5E92
0x1800f5e8e  add     rax, 2
0x1800f5e92  cmp     [rax], r14w
0x1800f5e96  jz      loc_1800F606F
0x1800f5e9c  cmp     word ptr [rax], 2Eh ; '.'
0x1800f5ea0  jnz     short loc_1800F5EBF
0x1800f5ea2  cmp     [rax+2], r14w
0x1800f5ea7  jz      loc_1800F606F
0x1800f5ead  cmp     word ptr [rax+2], 2Eh ; '.'
0x1800f5eb2  jnz     short loc_1800F5EBF
0x1800f5eb4  cmp     [rax+4], r14w
0x1800f5eb9  jz      loc_1800F606F
0x1800f5ebf  lea     r9, [rsp+0A8h+var_78]
0x1800f5ec4  mov     [rsp+0A8h+var_88], r14d
0x1800f5ec9  lea     r8, [rsp+0A8h+var_70]
0x1800f5ece  mov     rdx, rbx
0x1800f5ed1  mov     rcx, rdi
0x1800f5ed4  call    file_information
0x1800f5ed9  mov     r15d, 0F000h
0x1800f5edf  mov     r12d, 4000h
0x1800f5ee5  test    eax, eax
0x1800f5ee7  jnz     short loc_1800F5F43
0x1800f5ee9  movzx   eax, [rsp+0A8h+var_78]
0x1800f5eee  and     ax, r15w
0x1800f5ef2  cmp     ax, r12w
0x1800f5ef6  jz      loc_1800F5FEF
0x1800f5efc  test    byte ptr [rdi+1A8h], 8
0x1800f5f03  jz      short loc_1800F5F26
0x1800f5f05  lea     r8, aCanTCreateDire; "Can't create directory '%ls'"
0x1800f5f0c  mov     edx, 11h
0x1800f5f11  mov     r9, rbx
0x1800f5f14  mov     rcx, rdi
0x1800f5f17  call    archive_set_error
0x1800f5f1c  mov     eax, 0FFFFFFE7h
0x1800f5f21  jmp     loc_1800F5FF1
0x1800f5f26  mov     rcx, rbx; lpFileName
0x1800f5f29  call    disk_unlink
0x1800f5f2e  test    eax, eax
0x1800f5f30  jz      short loc_1800F5F83
0x1800f5f32  call    cs:__imp__o__errno
0x1800f5f38  lea     r8, aCanTCreateDire_0; "Can't create directory '%ls': Conflicti"...
0x1800f5f3f  mov     edx, [rax]
0x1800f5f41  jmp     short loc_1800F5F11
0x1800f5f43  call    cs:__imp__o__errno
0x1800f5f49  cmp     dword ptr [rax], 2
0x1800f5f4c  jz      short loc_1800F5F68
0x1800f5f4e  call    cs:__imp__o__errno
0x1800f5f54  cmp     dword ptr [rax], 14h
0x1800f5f57  jz      short loc_1800F5F68
0x1800f5f59  call    cs:__imp__o__errno
0x1800f5f5f  lea     r8, aCanTTestDirect; "Can't test directory '%ls'"
0x1800f5f66  jmp     short loc_1800F5F3F
0x1800f5f68  test    rsi, rsi
0x1800f5f6b  jz      short loc_1800F5F83
0x1800f5f6d  mov     rdx, rbx
0x1800f5f70  mov     [rsi], r14w
0x1800f5f74  mov     rcx, rdi
0x1800f5f77  call    create_dir
0x1800f5f7c  mov     [rsi], bp
0x1800f5f7f  test    eax, eax
0x1800f5f81  jnz     short loc_1800F5FF1
0x1800f5f83  movzx   esi, word ptr [rdi+90h]
0x1800f5f8a  mov     rcx, rbx; lpFileName
0x1800f5f8d  call    __la_win_permissive_name_w
0x1800f5f92  mov     rbp, rax
0x1800f5f95  test    rax, rax
0x1800f5f98  jnz     short loc_1800F5FA8
0x1800f5f9a  call    cs:__imp__o__errno
0x1800f5fa0  mov     dword ptr [rax], 16h
0x1800f5fa6  jmp     short loc_1800F6027
0x1800f5fa8  xor     edx, edx; lpSecurityAttributes
0x1800f5faa  mov     rcx, rbp; lpPathName
0x1800f5fad  call    cs:__imp_CreateDirectoryW
0x1800f5fb3  test    eax, eax
0x1800f5fb5  jz      short loc_1800F601A
0x1800f5fb7  mov     eax, 1FFh
0x1800f5fbc  not     si
0x1800f5fbf  and     si, ax
0x1800f5fc2  movzx   eax, si
0x1800f5fc5  and     ax, 3Dh
0x1800f5fc9  or      ax, 1C0h
0x1800f5fcd  cmp     ax, si
0x1800f5fd0  jz      short loc_1800F5FE6
0x1800f5fd2  mov     rdx, rbx
0x1800f5fd5  mov     rcx, rdi
0x1800f5fd8  call    new_fixup
0x1800f5fdd  bts     dword ptr [rax+7Ch], 1Dh
0x1800f5fe2  mov     [rax+40h], si
0x1800f5fe6  mov     rcx, rbp; Block
0x1800f5fe9  call    cs:__imp_free
0x1800f5fef  xor     eax, eax
0x1800f5ff1  mov     rcx, [rsp+0A8h+var_38]
0x1800f5ff6  xor     rcx, rsp; StackCookie
0x1800f5ff9  call    __security_check_cookie
0x1800f5ffe  lea     r11, [rsp+0A8h+var_28]
0x1800f6006  mov     rbx, [r11+40h]
0x1800f600a  mov     rbp, [r11+48h]
0x1800f600e  mov     rsp, r11
0x1800f6011  pop     r15
0x1800f6013  pop     r14
0x1800f6015  pop     r12
0x1800f6017  pop     rdi
0x1800f6018  pop     rsi
0x1800f6019  retn
0x1800f601a  call    cs:__imp_GetLastError
0x1800f6020  mov     ecx, eax
0x1800f6022  call    __la_dosmaperr
0x1800f6027  mov     rcx, rbp; Block
0x1800f602a  call    cs:__imp_free
0x1800f6030  lea     r9, [rsp+0A8h+var_78]
0x1800f6035  mov     [rsp+0A8h+var_88], r14d
0x1800f603a  lea     r8, [rsp+0A8h+var_70]
0x1800f603f  mov     rdx, rbx
0x1800f6042  mov     rcx, rdi
0x1800f6045  call    file_information
0x1800f604a  test    eax, eax
0x1800f604c  jnz     short loc_1800F605D
0x1800f604e  movzx   eax, [rsp+0A8h+var_78]
0x1800f6053  and     ax, r15w
0x1800f6057  cmp     ax, r12w
0x1800f605b  jz      short loc_1800F5FEF
0x1800f605d  call    cs:__imp__o__errno
0x1800f6063  lea     r8, aFailedToCreate; "Failed to create dir '%ls'"
0x1800f606a  jmp     loc_1800F5F3F
0x1800f606f  test    rsi, rsi
0x1800f6072  jz      loc_1800F5FEF
0x1800f6078  mov     rdx, rbx
0x1800f607b  mov     [rsi], r14w
0x1800f607f  mov     rcx, rdi
0x1800f6082  call    create_dir
0x1800f6087  mov     [rsi], bp
0x1800f608a  jmp     loc_1800F5FF1
```
