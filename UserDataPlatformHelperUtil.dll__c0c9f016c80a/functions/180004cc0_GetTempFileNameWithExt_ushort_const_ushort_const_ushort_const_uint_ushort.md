# GetTempFileNameWithExt(ushort const *,ushort const *,ushort const *,uint,ushort *)

- ea: `0x180004cc0`
- end: `0x180005044`
- name: `?GetTempFileNameWithExt@@YAIPEBG00IPEAG@Z`
- size: `900`
- prototype: `UINT __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16, unsigned __int16 *lpTempFileName)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180004cc0`

## import_xrefs

- `msvcrt!rand` at `0x180004f69`
- `msvcrt!rand` at `0x180004f72`
- `msvcrt!rand` at `0x180004f69`
- `msvcrt!rand` at `0x180004f72`
- `msvcrt!srand` at `0x180004f4b`
- `msvcrt!srand` at `0x180004f4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005001`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005001`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004d7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004d7f`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180004cf0`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180004cf0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004ff5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004ff5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180004dfd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180004dfd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180004f42`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180004f42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000502d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000502d`

## pseudocode

```c
UINT __fastcall GetTempFileNameWithExt(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 a4,
        unsigned __int16 *lpTempFileName)
{
  const unsigned __int16 *v6; // r14
  const unsigned __int16 *v7; // rsi
  const unsigned __int16 *v8; // r10
  const unsigned __int16 *v10; // rax
  __int64 v11; // r8
  unsigned __int64 v12; // rdx
  __int64 v13; // r8
  const unsigned __int16 *v14; // rax
  unsigned __int64 v15; // rdi
  DWORD v16; // ecx
  unsigned __int64 v17; // rcx
  unsigned __int16 *v18; // rax
  __int64 v19; // r8
  unsigned __int16 *v20; // rcx
  unsigned __int64 v21; // r12
  unsigned __int16 *v22; // rbx
  DWORD FileAttributesW; // eax
  const unsigned __int16 *v24; // rax
  __int64 v25; // r8
  unsigned __int64 v26; // rdx
  unsigned __int64 v27; // r8
  unsigned __int64 v28; // rax
  unsigned __int16 *v29; // rcx
  unsigned __int64 v30; // rsi
  unsigned __int64 v31; // rdx
  unsigned __int16 *v32; // r8
  unsigned __int16 *v33; // rcx
  unsigned int TickCount64; // eax
  int v35; // edi
  unsigned int v36; // ebx
  int v37; // ebx
  HANDLE FileW; // rax
  DWORD v39; // eax

  v6 = a3;
  v7 = a2;
  v8 = a1;
  if ( !a3 )
    return GetTempFileNameW(a1, a2, a4, lpTempFileName);
  if ( !a1 )
    goto LABEL_15;
  v10 = a1;
  v11 = 260;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v11;
  }
  while ( v11 );
  v12 = (260 - v11) & ((unsigned __int128)-(__int128)(unsigned __int64)v11 >> 64);
  if ( !v11 || !v12 )
    goto LABEL_15;
  v13 = 260;
  v14 = v6;
  do
  {
    if ( !*v14 )
      break;
    ++v14;
    --v13;
  }
  while ( v13 );
  v15 = (260 - v13) & -(__int64)(v13 != 0);
  if ( !v13 )
    goto LABEL_15;
  if ( v12 > 0x7FFFFFFE )
  {
    *lpTempFileName = 0;
LABEL_15:
    v16 = 87;
    goto LABEL_16;
  }
  v17 = v12;
  v18 = lpTempFileName;
  v19 = 260;
  do
  {
    if ( !v17 )
      break;
    if ( !*v8 )
      break;
    *v18++ = *v8++;
    --v17;
    --v19;
  }
  while ( v19 );
  v20 = v18 - 1;
  if ( v19 )
    v20 = v18;
  *v20 = 0;
  if ( !v19 )
    goto LABEL_15;
  v21 = v12 + 1;
  if ( lpTempFileName[v12 - 1] == 92 )
    v21 = v12;
  v22 = &lpTempFileName[v21];
  *(v22 - 1) = 0;
  FileAttributesW = GetFileAttributesW(lpTempFileName);
  if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
  {
    v16 = 267;
    goto LABEL_16;
  }
  *(v22 - 1) = 92;
  if ( !v7 )
    goto LABEL_15;
  v24 = v7;
  v25 = 260;
  do
  {
    if ( !*v24 )
      break;
    ++v24;
    --v25;
  }
  while ( v25 );
  v26 = (260 - v25) & ((unsigned __int128)-(__int128)(unsigned __int64)v25 >> 64);
  if ( !v25 )
    goto LABEL_15;
  if ( v26 > 3 )
    v26 = 3;
  v27 = 260 - v21;
  if ( 260 == v21 )
    goto LABEL_15;
  if ( v27 > 0x7FFFFFFF )
  {
    *v22 = 0;
    goto LABEL_15;
  }
  v28 = v26;
  do
  {
    if ( !v28 )
      break;
    if ( !*v7 )
      break;
    *v22++ = *v7++;
    --v28;
    --v27;
  }
  while ( v27 );
  v29 = v22 - 1;
  if ( v27 )
    v29 = v22;
  *v29 = 0;
  if ( !v27 )
    goto LABEL_15;
  v30 = v21 + v26;
  if ( v15 + v21 + v26 + 5 > 0x104 )
    goto LABEL_15;
  v31 = 256 - v30;
  if ( v30 == 256 )
    goto LABEL_15;
  v32 = &lpTempFileName[v30 + 4];
  if ( v31 > 0x7FFFFFFF || v15 > 0x7FFFFFFE )
  {
    *v32 = 0;
    goto LABEL_15;
  }
  do
  {
    if ( !v15 )
      break;
    if ( !*v6 )
      break;
    *v32++ = *v6++;
    --v15;
    --v31;
  }
  while ( v31 );
  v33 = v32 - 1;
  if ( v31 )
    v33 = v32;
  *v33 = 0;
  if ( !v31 )
    goto LABEL_15;
  TickCount64 = GetTickCount64();
  srand(TickCount64);
  v35 = 0;
  if ( !a4 )
    goto LABEL_59;
  v36 = a4;
LABEL_60:
  lpTempFileName[v30] = a0123456789abcd[(unsigned __int64)v36 >> 12];
  lpTempFileName[v30 + 1] = a0123456789abcd[(v36 >> 8) & 0xF];
  lpTempFileName[v30 + 2] = a0123456789abcd[(unsigned __int8)v36 >> 4];
  lpTempFileName[v30 + 3] = a0123456789abcd[v36 & 0xF];
  if ( !a4 )
  {
    FileW = CreateFileW(lpTempFileName, 0x80000000, 0, 0, 1u, 0x80u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      v39 = GetLastError() - 80;
      if ( v39 && v39 != 103 )
        return 0;
      while ( (++v35 & 0xFFFF0000) == 0 )
      {
LABEL_59:
        v37 = (unsigned __int8)rand();
        v36 = ((unsigned __int8)rand() << 8) + v37;
        if ( v36 )
          goto LABEL_60;
      }
      v16 = 1237;
LABEL_16:
      SetLastError(v16);
      return 0;
    }
    CloseHandle(FileW);
  }
  return v36;
}

```

## disassembly

```asm
0x180004cc0  push    rbx
0x180004cc2  push    rbp
0x180004cc3  push    rsi
0x180004cc4  push    rdi
0x180004cc5  push    r12
0x180004cc7  push    r13
0x180004cc9  push    r14
0x180004ccb  push    r15
0x180004ccd  sub     rsp, 48h
0x180004cd1  xor     r13d, r13d
0x180004cd4  mov     ebp, r9d
0x180004cd7  mov     r14, r8
0x180004cda  mov     rsi, rdx
0x180004cdd  mov     r10, rcx
0x180004ce0  test    r8, r8
0x180004ce3  jnz     short loc_180004CFB
0x180004ce5  mov     r9, [rsp+88h+lpTempFileName]; lpTempFileName
0x180004ced  mov     r8d, ebp; uUnique
0x180004cf0  call    cs:__imp_GetTempFileNameW
0x180004cf6  jmp     loc_180004D87
0x180004cfb  test    rcx, rcx
0x180004cfe  jz      short loc_180004D7A
0x180004d00  mov     r9d, 104h
0x180004d06  mov     rax, rcx
0x180004d09  mov     r8d, r9d
0x180004d0c  cmp     [rax], r13w
0x180004d10  jz      short loc_180004D1C
0x180004d12  add     rax, 2
0x180004d16  sub     r8, 1
0x180004d1a  jnz     short loc_180004D0C
0x180004d1c  mov     rcx, r9
0x180004d1f  mov     rax, r8
0x180004d22  sub     rcx, r8
0x180004d25  neg     rax
0x180004d28  sbb     rdx, rdx
0x180004d2b  and     rdx, rcx
0x180004d2e  test    r8, r8
0x180004d31  jz      short loc_180004D7A
0x180004d33  test    rdx, rdx
0x180004d36  jz      short loc_180004D7A
0x180004d38  mov     r8, r9
0x180004d3b  mov     rax, r14
0x180004d3e  cmp     [rax], r13w
0x180004d42  jz      short loc_180004D4E
0x180004d44  add     rax, 2
0x180004d48  sub     r8, 1
0x180004d4c  jnz     short loc_180004D3E
0x180004d4e  mov     rcx, r9
0x180004d51  mov     rax, r8
0x180004d54  sub     rcx, r8
0x180004d57  neg     rax
0x180004d5a  sbb     rdi, rdi
0x180004d5d  and     rdi, rcx
0x180004d60  test    r8, r8
0x180004d63  jz      short loc_180004D7A
0x180004d65  cmp     rdx, 7FFFFFFEh
0x180004d6c  jbe     short loc_180004D98
0x180004d6e  mov     rax, [rsp+88h+lpTempFileName]
0x180004d76  mov     [rax], r13w
0x180004d7a  mov     ecx, 57h ; 'W'; dwErrCode
0x180004d7f  call    cs:__imp_SetLastError
0x180004d85  xor     eax, eax
0x180004d87  add     rsp, 48h
0x180004d8b  pop     r15
0x180004d8d  pop     r14
0x180004d8f  pop     r13
0x180004d91  pop     r12
0x180004d93  pop     rdi
0x180004d94  pop     rsi
0x180004d95  pop     rbp
0x180004d96  pop     rbx
0x180004d97  retn
0x180004d98  mov     r15, [rsp+88h+lpTempFileName]
0x180004da0  mov     rcx, rdx
0x180004da3  mov     rax, r15
0x180004da6  mov     r8, r9
0x180004da9  test    rcx, rcx
0x180004dac  jz      short loc_180004DCD
0x180004dae  movzx   r9d, word ptr [r10]
0x180004db2  test    r9w, r9w
0x180004db6  jz      short loc_180004DCD
0x180004db8  mov     [rax], r9w
0x180004dbc  add     r10, 2
0x180004dc0  add     rax, 2
0x180004dc4  dec     rcx
0x180004dc7  sub     r8, 1
0x180004dcb  jnz     short loc_180004DA9
0x180004dcd  test    r8, r8
0x180004dd0  lea     rcx, [rax-2]
0x180004dd4  cmovnz  rcx, rax
0x180004dd8  mov     [rcx], r13w
0x180004ddc  jz      short loc_180004D7A
0x180004dde  mov     eax, 5Ch ; '\'
0x180004de3  lea     r12, [rdx+1]
0x180004de7  cmp     [r15+rdx*2-2], ax
0x180004ded  mov     rcx, r15; lpFileName
0x180004df0  cmovz   r12, rdx
0x180004df4  lea     rbx, [r15+r12*2]
0x180004df8  mov     [rbx-2], r13w
0x180004dfd  call    cs:__imp_GetFileAttributesW
0x180004e03  cmp     eax, 0FFFFFFFFh
0x180004e06  jz      loc_18000503A
0x180004e0c  test    al, 10h
0x180004e0e  jz      loc_18000503A
0x180004e14  mov     word ptr [rbx-2], 5Ch ; '\'
0x180004e1a  test    rsi, rsi
0x180004e1d  jz      loc_180004D7A
0x180004e23  mov     r9d, 104h
0x180004e29  mov     rax, rsi
0x180004e2c  mov     r8d, r9d
0x180004e2f  cmp     [rax], r13w
0x180004e33  jz      short loc_180004E3F
0x180004e35  add     rax, 2
0x180004e39  sub     r8, 1
0x180004e3d  jnz     short loc_180004E2F
0x180004e3f  mov     rcx, r9
0x180004e42  mov     rax, r8
0x180004e45  sub     rcx, r8
0x180004e48  neg     rax
0x180004e4b  sbb     rdx, rdx
0x180004e4e  and     rdx, rcx
0x180004e51  test    r8, r8
0x180004e54  jz      loc_180004D7A
0x180004e5a  mov     eax, 3
0x180004e5f  mov     r8, r9
0x180004e62  cmp     rdx, rax
0x180004e65  cmova   rdx, rax
0x180004e69  sub     r8, r12
0x180004e6c  jz      loc_180004D7A
0x180004e72  mov     r10d, 7FFFFFFFh
0x180004e78  cmp     r8, r10
0x180004e7b  jbe     short loc_180004E86
0x180004e7d  mov     [rbx], r13w
0x180004e81  jmp     loc_180004D7A
0x180004e86  mov     r11d, 7FFFFFFEh
0x180004e8c  cmp     rdx, r11
0x180004e8f  ja      short loc_180004E7D
0x180004e91  mov     rax, rdx
0x180004e94  test    rax, rax
0x180004e97  jz      short loc_180004EB5
0x180004e99  movzx   ecx, word ptr [rsi]
0x180004e9c  test    cx, cx
0x180004e9f  jz      short loc_180004EB5
0x180004ea1  mov     [rbx], cx
0x180004ea4  add     rsi, 2
0x180004ea8  add     rbx, 2
0x180004eac  dec     rax
0x180004eaf  sub     r8, 1
0x180004eb3  jnz     short loc_180004E94
0x180004eb5  test    r8, r8
0x180004eb8  lea     rcx, [rbx-2]
0x180004ebc  cmovnz  rcx, rbx
0x180004ec0  mov     [rcx], r13w
0x180004ec4  jz      loc_180004D7A
0x180004eca  lea     rsi, [r12+rdx]
0x180004ece  lea     rax, [rsi+5]
0x180004ed2  add     rax, rdi
0x180004ed5  cmp     rax, r9
0x180004ed8  ja      loc_180004D7A
0x180004ede  mov     edx, 100h
0x180004ee3  sub     rdx, rsi
0x180004ee6  jz      loc_180004D7A
0x180004eec  lea     r8, [r15+8]
0x180004ef0  lea     r8, [r8+rsi*2]
0x180004ef4  cmp     rdx, r10
0x180004ef7  ja      short loc_180004EFE
0x180004ef9  cmp     rdi, r11
0x180004efc  jbe     short loc_180004F07
0x180004efe  mov     [r8], r13w
0x180004f02  jmp     loc_180004D7A
0x180004f07  test    rdi, rdi
0x180004f0a  jz      short loc_180004F2A
0x180004f0c  movzx   eax, word ptr [r14]
0x180004f10  test    ax, ax
0x180004f13  jz      short loc_180004F2A
0x180004f15  mov     [r8], ax
0x180004f19  add     r14, 2
0x180004f1d  add     r8, 2
0x180004f21  dec     rdi
0x180004f24  sub     rdx, 1
0x180004f28  jnz     short loc_180004F07
0x180004f2a  test    rdx, rdx
0x180004f2d  lea     rcx, [r8-2]
0x180004f31  cmovnz  rcx, r8
0x180004f35  mov     [rcx], r13w
0x180004f39  jz      loc_180004D7A
0x180004f3f  movzx   ebp, bp
0x180004f42  call    cs:__imp_GetTickCount64
0x180004f48  mov     rcx, rax; Seed
0x180004f4b  call    cs:__imp_srand
0x180004f51  lea     r12, a0123456789abcd; "0123456789ABCDEF"
0x180004f58  mov     edi, r13d
0x180004f5b  mov     r14d, 0FFFF0000h
0x180004f61  test    ebp, ebp
0x180004f63  jz      short loc_180004F69
0x180004f65  mov     ebx, ebp
0x180004f67  jmp     short loc_180004F86
0x180004f69  call    cs:__imp_rand
0x180004f6f  movzx   ebx, al
0x180004f72  call    cs:__imp_rand
0x180004f78  movzx   ecx, al
0x180004f7b  shl     ecx, 8
0x180004f7e  add     ebx, ecx
0x180004f80  jz      loc_180005015
0x180004f86  mov     ecx, ebx
0x180004f88  and     ecx, 0Fh
0x180004f8b  mov     eax, ebx
0x180004f8d  shr     rax, 0Ch
0x180004f91  movzx   eax, word ptr [r12+rax*2]
0x180004f96  mov     [r15+rsi*2], ax
0x180004f9b  mov     eax, ebx
0x180004f9d  shr     rax, 8
0x180004fa1  and     eax, 0Fh
0x180004fa4  movzx   eax, word ptr [r12+rax*2]
0x180004fa9  mov     [r15+rsi*2+2], ax
0x180004faf  mov     eax, ebx
0x180004fb1  shr     rax, 4
0x180004fb5  and     eax, 0Fh
0x180004fb8  movzx   eax, word ptr [r12+rax*2]
0x180004fbd  mov     [r15+rsi*2+4], ax
0x180004fc3  movzx   eax, word ptr [r12+rcx*2]
0x180004fc8  mov     [r15+rsi*2+6], ax
0x180004fce  test    ebp, ebp
0x180004fd0  jnz     short loc_180005033
0x180004fd2  mov     [rsp+88h+hTemplateFile], r13; hTemplateFile
0x180004fd7  xor     r9d, r9d; lpSecurityAttributes
0x180004fda  mov     [rsp+88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180004fe2  xor     r8d, r8d; dwShareMode
0x180004fe5  mov     edx, 80000000h; dwDesiredAccess
0x180004fea  mov     [rsp+88h+dwCreationDisposition], 1; dwCreationDisposition
0x180004ff2  mov     rcx, r15; lpFileName
0x180004ff5  call    cs:__imp_CreateFileW
0x180004ffb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004fff  jnz     short loc_18000502A
0x180005001  call    cs:__imp_GetLastError
0x180005007  sub     eax, 50h ; 'P'
0x18000500a  jz      short loc_180005015
0x18000500c  cmp     eax, 67h ; 'g'
0x18000500f  jnz     loc_180004D85
0x180005015  inc     edi
0x180005017  test    r14d, edi
0x18000501a  jz      loc_180004F69
0x180005020  mov     ecx, 4D5h
0x180005025  jmp     loc_180004D7F
0x18000502a  mov     rcx, rax; hObject
0x18000502d  call    cs:__imp_CloseHandle
0x180005033  mov     eax, ebx
0x180005035  jmp     loc_180004D87
0x18000503a  mov     ecx, 10Bh
0x18000503f  jmp     loc_180004D7F
```
