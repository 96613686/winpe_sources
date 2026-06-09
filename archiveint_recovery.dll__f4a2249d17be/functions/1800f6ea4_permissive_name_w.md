# permissive_name_w

- ea: `0x1800f6ea4`
- end: `0x1800f7329`
- name: `permissive_name_w`
- size: `1157`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800f5030`

## callees

- `0x18000b4d0`
- `0x1800ed6c0`
- `0x1800f6ea4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800f6f6c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800f705f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800f7128`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800f71c0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800f6f6c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800f705f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800f7128`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800f71c0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f71b5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f7208`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f7211`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f72f7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f7300`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f730e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f71b5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f7208`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f7211`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f72f7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f7300`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f730e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800f70fc`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800f70fc`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x1800f70e5`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x1800f710a`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x1800f70e5`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x1800f710a`

## pseudocode

```c
__int64 __fastcall permissive_name_w(_QWORD *a1)
{
  __int16 *v1; // rbx
  __int16 v3; // cx
  _WORD *v4; // rax
  __int16 v5; // cx
  _WORD *v6; // rax
  __int16 v7; // cx
  _WORD *v8; // rdx
  __int64 v9; // rax
  char *v10; // rbp
  unsigned int v11; // ebx
  __int64 v12; // rdx
  _QWORD *v13; // rsi
  char *v14; // rdx
  __int16 v15; // cx
  __int64 v17; // rax
  __int64 v18; // rdx
  DWORD CurrentDirectoryW; // eax
  DWORD v20; // ebp
  WCHAR *v21; // rsi
  __int64 v22; // rdx
  DWORD v23; // r15d
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rcx
  _QWORD *v28; // r12
  WCHAR *v29; // rbx

  v1 = (__int16 *)a1[44];
  v3 = *v1;
  if ( *v1 == 92 )
  {
    if ( v1[1] == 92 )
    {
      if ( v1[2] == 63 )
      {
        if ( v1[3] == 92 )
          return 0;
      }
      else if ( v1[2] == 46 && v1[3] == 92 )
      {
        v15 = v1[4];
        if ( ((unsigned __int16)(v15 - 97) <= 0x19u || (unsigned __int16)(v15 - 65) <= 0x19u)
          && v1[5] == 58
          && v1[6] == 92 )
        {
          v1[2] = 63;
          return 0;
        }
      }
      if ( v1[1] == 92 )
      {
        v4 = v1 + 2;
        v5 = v1[2];
        if ( v5 != 92 )
        {
          do
          {
            if ( !v5 )
              break;
            v5 = *++v4;
          }
          while ( *v4 != 92 );
          if ( *v4 == 92 )
          {
            v6 = v4 + 1;
            v7 = *v6;
            if ( *v6 != 92 )
            {
              v8 = v6;
              do
              {
                if ( !v7 )
                  break;
                v7 = *++v6;
              }
              while ( *v6 != 92 );
              if ( *v6 == 92 && v6 != v8 )
              {
                v9 = _o__wcsdup(v1, v8);
                v10 = (char *)v9;
                if ( v9 )
                {
                  v11 = -1;
                  v12 = -1;
                  do
                    ++v12;
                  while ( *(_WORD *)(v9 + 2 * v12) );
                  v13 = a1 + 45;
                  if ( !archive_string_ensure(a1 + 45, 2 * v12 + 18) )
                    goto LABEL_53;
                  a1[44] = *v13;
                  a1[46] = 0;
                  archive_wstrncat(a1 + 45, L"\\\\?\\UNC\\", 8);
                  v14 = v10 + 4;
                  goto LABEL_38;
                }
                return -1;
              }
            }
          }
          return 0;
        }
      }
    }
LABEL_40:
    CurrentDirectoryW = GetCurrentDirectoryW(0, 0);
    v20 = CurrentDirectoryW;
    if ( !CurrentDirectoryW )
      return -1;
    v21 = (WCHAR *)malloc(2LL * CurrentDirectoryW);
    v23 = GetCurrentDirectoryW(v20, v21);
    if ( !v23 )
      goto LABEL_68;
    if ( *v1 == 92 )
    {
      v24 = _o__wcsdup(v1, v22);
      v10 = (char *)v24;
      if ( v24 )
      {
        v11 = -1;
        v25 = -1;
        do
          ++v25;
        while ( *(_WORD *)(v24 + 2 * v25) );
        if ( archive_string_ensure(a1 + 45, 2 * v25 + 14) )
        {
          a1[44] = a1[45];
          a1[46] = 0;
          archive_wstrncat(a1 + 45, L"\\\\?\\", 4);
          archive_wstrncat(a1 + 45, v21, 2);
          archive_wstrncat(a1 + 45, v10, 0x1000000);
          free(v21);
          goto LABEL_39;
        }
LABEL_52:
        free(v21);
        goto LABEL_53;
      }
LABEL_68:
      free(v21);
      return -1;
    }
    v26 = _o__wcsdup(v1, v22);
    v10 = (char *)v26;
    if ( !v26 )
      goto LABEL_68;
    v11 = -1;
    v27 = -1;
    do
      ++v27;
    while ( *(_WORD *)(v26 + 2 * v27) );
    v28 = a1 + 45;
    if ( !archive_string_ensure(a1 + 45, 2 * (v27 + v23 + 5) + 2) )
      goto LABEL_52;
    a1[44] = *v28;
    if ( v23 <= 3 )
    {
      if ( v23 > 2 )
      {
LABEL_61:
        if ( *v21 == 92 && v21[1] == 92 )
        {
          v29 = v21 + 2;
          if ( v21[2] != 92 )
          {
            a1[46] = 0;
            archive_wstrncat(a1 + 45, L"\\\\?\\UNC\\", 8);
            v23 -= 2;
LABEL_67:
            archive_wstrncat(a1 + 45, v29, v23);
            archive_wstrncat(a1 + 45, L"\\", 1);
            archive_wstrncat(a1 + 45, v10, 0x1000000);
            a1[44] = *v28;
            free(v21);
            free(v10);
            return 0;
          }
        }
      }
    }
    else if ( *v21 == 92 )
    {
      if ( v21[1] == 92 && v21[2] == 63 && v21[3] == 92 )
      {
        a1[46] = 0;
LABEL_66:
        v29 = v21;
        goto LABEL_67;
      }
      goto LABEL_61;
    }
    a1[46] = 0;
    archive_wstrncat(a1 + 45, L"\\\\?\\", 4);
    goto LABEL_66;
  }
  if ( (unsigned __int16)(v3 - 65) > 0x19u && (unsigned __int16)(v3 - 97) > 0x19u || v1[1] != 58 || v1[2] != 92 )
    goto LABEL_40;
  v17 = _o__wcsdup(v1, 63);
  v10 = (char *)v17;
  if ( v17 )
  {
    v11 = -1;
    v18 = -1;
    do
      ++v18;
    while ( *(_WORD *)(v17 + 2 * v18) );
    v13 = a1 + 45;
    if ( !archive_string_ensure(a1 + 45, 2 * v18 + 10) )
      goto LABEL_53;
    a1[44] = *v13;
    a1[46] = 0;
    archive_wstrncat(a1 + 45, L"\\\\?\\", 4);
    v14 = v10;
LABEL_38:
    archive_wstrncat(v13, v14, 0x1000000);
LABEL_39:
    v11 = 0;
LABEL_53:
    free(v10);
    return v11;
  }
  return -1;
}

```

## disassembly

```asm
0x1800f6ea4  push    rbx
0x1800f6ea6  push    rbp
0x1800f6ea7  push    rsi
0x1800f6ea8  push    rdi
0x1800f6ea9  push    r12
0x1800f6eab  push    r13
0x1800f6ead  push    r14
0x1800f6eaf  push    r15
0x1800f6eb1  sub     rsp, 28h
0x1800f6eb5  mov     rbx, [rcx+160h]
0x1800f6ebc  mov     r14, rcx
0x1800f6ebf  mov     r13w, 5Ch ; '\'
0x1800f6ec4  mov     edx, 3Fh ; '?'
0x1800f6ec9  movzx   ecx, word ptr [rbx]
0x1800f6ecc  cmp     cx, r13w
0x1800f6ed0  jnz     loc_1800F702F
0x1800f6ed6  cmp     [rbx+2], r13w
0x1800f6edb  jnz     loc_1800F70E1
0x1800f6ee1  cmp     [rbx+4], dx
0x1800f6ee5  jnz     loc_1800F6FDD
0x1800f6eeb  cmp     [rbx+6], r13w
0x1800f6ef0  jz      loc_1800F7028
0x1800f6ef6  cmp     [rbx+2], r13w
0x1800f6efb  jnz     loc_1800F70E1
0x1800f6f01  lea     rax, [rbx+4]
0x1800f6f05  movzx   ecx, word ptr [rax]
0x1800f6f08  cmp     cx, r13w
0x1800f6f0c  jz      loc_1800F70E1
0x1800f6f12  xor     edi, edi
0x1800f6f14  test    cx, cx
0x1800f6f17  jz      short loc_1800F6F26
0x1800f6f19  add     rax, 2
0x1800f6f1d  movzx   ecx, word ptr [rax]
0x1800f6f20  cmp     cx, r13w
0x1800f6f24  jnz     short loc_1800F6F14
0x1800f6f26  cmp     [rax], r13w
0x1800f6f2a  jnz     loc_1800F7028
0x1800f6f30  add     rax, 2
0x1800f6f34  movzx   ecx, word ptr [rax]
0x1800f6f37  cmp     cx, r13w
0x1800f6f3b  jz      loc_1800F7028
0x1800f6f41  mov     rdx, rax
0x1800f6f44  test    cx, cx
0x1800f6f47  jz      short loc_1800F6F56
0x1800f6f49  add     rax, 2
0x1800f6f4d  movzx   ecx, word ptr [rax]
0x1800f6f50  cmp     cx, r13w
0x1800f6f54  jnz     short loc_1800F6F44
0x1800f6f56  cmp     [rax], r13w
0x1800f6f5a  jnz     loc_1800F7028
0x1800f6f60  cmp     rax, rdx
0x1800f6f63  jz      loc_1800F7028
0x1800f6f69  mov     rcx, rbx
0x1800f6f6c  call    cs:__imp__o__wcsdup
0x1800f6f72  mov     rbp, rax
0x1800f6f75  test    rax, rax
0x1800f6f78  jz      loc_1800F7314
0x1800f6f7e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800f6f82  mov     rdx, rbx
0x1800f6f85  inc     rdx
0x1800f6f88  cmp     [rax+rdx*2], di
0x1800f6f8c  jnz     short loc_1800F6F85
0x1800f6f8e  lea     rsi, [r14+168h]
0x1800f6f95  mov     rcx, rsi
0x1800f6f98  lea     rdx, ds:12h[rdx*2]
0x1800f6fa0  call    archive_string_ensure
0x1800f6fa5  test    rax, rax
0x1800f6fa8  jz      loc_1800F720E
0x1800f6fae  mov     rax, [rsi]
0x1800f6fb1  lea     rdx, aUnc_0; "\\\\?\\UNC\\"
0x1800f6fb8  mov     r8d, 8
0x1800f6fbe  mov     [r14+160h], rax
0x1800f6fc5  mov     rcx, rsi
0x1800f6fc8  mov     [r14+170h], rdi
0x1800f6fcf  call    archive_wstrncat
0x1800f6fd4  lea     rdx, [rbp+4]
0x1800f6fd8  jmp     loc_1800F70CC
0x1800f6fdd  cmp     word ptr [rbx+4], 2Eh ; '.'
0x1800f6fe2  jnz     loc_1800F6EF6
0x1800f6fe8  cmp     [rbx+6], r13w
0x1800f6fed  jnz     loc_1800F6EF6
0x1800f6ff3  movzx   ecx, word ptr [rbx+8]
0x1800f6ff7  lea     eax, [rcx-61h]
0x1800f6ffa  cmp     ax, 19h
0x1800f6ffe  jbe     short loc_1800F700E
0x1800f7000  sub     cx, 41h ; 'A'
0x1800f7004  cmp     cx, 19h
0x1800f7008  ja      loc_1800F6EF6
0x1800f700e  cmp     word ptr [rbx+0Ah], 3Ah ; ':'
0x1800f7013  jnz     loc_1800F6EF6
0x1800f7019  cmp     [rbx+0Ch], r13w
0x1800f701e  jnz     loc_1800F6EF6
0x1800f7024  mov     [rbx+4], dx
0x1800f7028  xor     eax, eax
0x1800f702a  jmp     loc_1800F7318
0x1800f702f  lea     eax, [rcx-41h]
0x1800f7032  cmp     ax, 19h
0x1800f7036  jbe     short loc_1800F7046
0x1800f7038  sub     cx, 61h ; 'a'
0x1800f703c  cmp     cx, 19h
0x1800f7040  ja      loc_1800F70E1
0x1800f7046  cmp     word ptr [rbx+2], 3Ah ; ':'
0x1800f704b  jnz     loc_1800F70E1
0x1800f7051  cmp     [rbx+4], r13w
0x1800f7056  jnz     loc_1800F70E1
0x1800f705c  mov     rcx, rbx
0x1800f705f  call    cs:__imp__o__wcsdup
0x1800f7065  xor     edi, edi
0x1800f7067  mov     rbp, rax
0x1800f706a  test    rax, rax
0x1800f706d  jz      loc_1800F7314
0x1800f7073  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800f7077  mov     rdx, rbx
0x1800f707a  inc     rdx
0x1800f707d  cmp     [rax+rdx*2], di
0x1800f7081  jnz     short loc_1800F707A
0x1800f7083  lea     rsi, [r14+168h]
0x1800f708a  mov     rcx, rsi
0x1800f708d  lea     rdx, ds:0Ah[rdx*2]
0x1800f7095  call    archive_string_ensure
0x1800f709a  test    rax, rax
0x1800f709d  jz      loc_1800F720E
0x1800f70a3  mov     rax, [rsi]
0x1800f70a6  lea     rdx, Source; "\\\\?\\"
0x1800f70ad  mov     r8d, 4
0x1800f70b3  mov     [r14+160h], rax
0x1800f70ba  mov     rcx, rsi
0x1800f70bd  mov     [r14+170h], rdi
0x1800f70c4  call    archive_wstrncat
0x1800f70c9  mov     rdx, rbp
0x1800f70cc  mov     r8d, 1000000h
0x1800f70d2  mov     rcx, rsi
0x1800f70d5  call    archive_wstrncat
0x1800f70da  mov     ebx, edi
0x1800f70dc  jmp     loc_1800F720E
0x1800f70e1  xor     edx, edx; lpBuffer
0x1800f70e3  xor     ecx, ecx; nBufferLength
0x1800f70e5  call    cs:__imp_GetCurrentDirectoryW
0x1800f70eb  xor     edi, edi
0x1800f70ed  mov     ebp, eax
0x1800f70ef  test    eax, eax
0x1800f70f1  jz      loc_1800F7314
0x1800f70f7  mov     ecx, ebp
0x1800f70f9  add     rcx, rcx; Size
0x1800f70fc  call    cs:__imp_malloc
0x1800f7102  mov     rdx, rax; lpBuffer
0x1800f7105  mov     ecx, ebp; nBufferLength
0x1800f7107  mov     rsi, rax
0x1800f710a  call    cs:__imp_GetCurrentDirectoryW
0x1800f7110  mov     r15d, eax
0x1800f7113  test    eax, eax
0x1800f7115  jz      loc_1800F730B
0x1800f711b  mov     rcx, rbx
0x1800f711e  cmp     [rbx], r13w
0x1800f7122  jnz     loc_1800F71C0
0x1800f7128  call    cs:__imp__o__wcsdup
0x1800f712e  mov     rbp, rax
0x1800f7131  test    rax, rax
0x1800f7134  jz      loc_1800F730B
0x1800f713a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800f713e  mov     rdx, rbx
0x1800f7141  inc     rdx
0x1800f7144  cmp     [rax+rdx*2], di
0x1800f7148  jnz     short loc_1800F7141
0x1800f714a  lea     r15, [r14+168h]
0x1800f7151  mov     rcx, r15
0x1800f7154  lea     rdx, ds:0Eh[rdx*2]
0x1800f715c  call    archive_string_ensure
0x1800f7161  test    rax, rax
0x1800f7164  jz      loc_1800F7205
0x1800f716a  mov     rax, [r15]
0x1800f716d  lea     rdx, Source; "\\\\?\\"
0x1800f7174  mov     r8d, 4
0x1800f717a  mov     [r14+160h], rax
0x1800f7181  mov     rcx, r15
0x1800f7184  mov     [r14+170h], rdi
0x1800f718b  call    archive_wstrncat
0x1800f7190  mov     r8d, 2
0x1800f7196  mov     rdx, rsi
0x1800f7199  mov     rcx, r15
0x1800f719c  call    archive_wstrncat
0x1800f71a1  mov     r8d, 1000000h
0x1800f71a7  mov     rdx, rbp
0x1800f71aa  mov     rcx, r15
0x1800f71ad  call    archive_wstrncat
0x1800f71b2  mov     rcx, rsi; Block
0x1800f71b5  call    cs:__imp_free
0x1800f71bb  jmp     loc_1800F70DA
0x1800f71c0  call    cs:__imp__o__wcsdup
0x1800f71c6  mov     rbp, rax
0x1800f71c9  test    rax, rax
0x1800f71cc  jz      loc_1800F730B
0x1800f71d2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800f71d6  mov     rcx, rbx
0x1800f71d9  inc     rcx
0x1800f71dc  cmp     [rax+rcx*2], di
0x1800f71e0  jnz     short loc_1800F71D9
0x1800f71e2  lea     edx, [r15+5]
0x1800f71e6  add     rdx, rcx
0x1800f71e9  lea     r12, [r14+168h]
0x1800f71f0  mov     rcx, r12
0x1800f71f3  lea     rdx, ds:2[rdx*2]
0x1800f71fb  call    archive_string_ensure
0x1800f7200  test    rax, rax
0x1800f7203  jnz     short loc_1800F721E
0x1800f7205  mov     rcx, rsi; Block
0x1800f7208  call    cs:__imp_free
0x1800f720e  mov     rcx, rbp; Block
0x1800f7211  call    cs:__imp_free
0x1800f7217  mov     eax, ebx
0x1800f7219  jmp     loc_1800F7318
0x1800f721e  mov     rax, [r12]
0x1800f7222  mov     [r14+160h], rax
0x1800f7229  cmp     r15d, 3
0x1800f722d  jbe     short loc_1800F7257
0x1800f722f  cmp     [rsi], r13w
0x1800f7233  jnz     short loc_1800F7296
0x1800f7235  cmp     [rsi+2], r13w
0x1800f723a  jnz     short loc_1800F725D
0x1800f723c  mov     eax, 3Fh ; '?'
0x1800f7241  cmp     [rsi+4], ax
0x1800f7245  jnz     short loc_1800F725D
0x1800f7247  cmp     [rsi+6], r13w
0x1800f724c  jnz     short loc_1800F725D
0x1800f724e  mov     [r14+170h], rdi
0x1800f7255  jmp     short loc_1800F72B2
0x1800f7257  cmp     r15d, 2
0x1800f725b  jbe     short loc_1800F7296
0x1800f725d  cmp     [rsi], r13w
0x1800f7261  jnz     short loc_1800F7296
0x1800f7263  cmp     [rsi+2], r13w
0x1800f7268  jnz     short loc_1800F7296
0x1800f726a  lea     rbx, [rsi+4]
0x1800f726e  cmp     [rbx], r13w
0x1800f7272  jz      short loc_1800F7296
0x1800f7274  mov     r8d, 8
0x1800f727a  mov     [r14+170h], rdi
0x1800f7281  lea     rdx, aUnc_0; "\\\\?\\UNC\\"
0x1800f7288  mov     rcx, r12
0x1800f728b  call    archive_wstrncat
0x1800f7290  add     r15d, 0FFFFFFFEh
0x1800f7294  jmp     short loc_1800F72B5
0x1800f7296  mov     r8d, 4
0x1800f729c  mov     [r14+170h], rdi
0x1800f72a3  lea     rdx, Source; "\\\\?\\"
0x1800f72aa  mov     rcx, r12
0x1800f72ad  call    archive_wstrncat
0x1800f72b2  mov     rbx, rsi
0x1800f72b5  mov     r8d, r15d
0x1800f72b8  mov     rdx, rbx
0x1800f72bb  mov     rcx, r12
0x1800f72be  call    archive_wstrncat
0x1800f72c3  mov     r8d, 1
0x1800f72c9  lea     rdx, asc_18013F69C; "\\"
0x1800f72d0  mov     rcx, r12
0x1800f72d3  call    archive_wstrncat
0x1800f72d8  mov     r8d, 1000000h
0x1800f72de  mov     rdx, rbp
0x1800f72e1  mov     rcx, r12
0x1800f72e4  call    archive_wstrncat
0x1800f72e9  mov     rax, [r12]
0x1800f72ed  mov     rcx, rsi; Block
0x1800f72f0  mov     [r14+160h], rax
0x1800f72f7  call    cs:__imp_free
0x1800f72fd  mov     rcx, rbp; Block
0x1800f7300  call    cs:__imp_free
0x1800f7306  jmp     loc_1800F7028
0x1800f730b  mov     rcx, rsi; Block
0x1800f730e  call    cs:__imp_free
0x1800f7314  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f7318  add     rsp, 28h
0x1800f731c  pop     r15
0x1800f731e  pop     r14
0x1800f7320  pop     r13
0x1800f7322  pop     r12
0x1800f7324  pop     rdi
0x1800f7325  pop     rsi
0x1800f7326  pop     rbp
0x1800f7327  pop     rbx
0x1800f7328  retn
```
