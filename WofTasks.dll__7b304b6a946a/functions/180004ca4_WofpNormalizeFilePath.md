# WofpNormalizeFilePath

- ea: `0x180004ca4`
- end: `0x180004eee`
- name: `WofpNormalizeFilePath`
- size: `586`
- prototype: `__int64 __fastcall(WCHAR *, wchar_t **)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x180004788`

## callees

- `0x180004bc0`
- `0x180004ca4`
- `0x1800051c0`

## import_xrefs

- `msvcrt!wcschr` at `0x180004cf6`
- `msvcrt!wcschr` at `0x180004cf6`
- `KERNEL32!HeapAlloc` at `0x180004e87`
- `KERNEL32!HeapAlloc` at `0x180004e87`
- `KERNEL32!GetProcessHeap` at `0x180004e79`
- `KERNEL32!GetProcessHeap` at `0x180004e79`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180004ded`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180004ded`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180004e0b`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180004e0b`

## pseudocode

```c
__int64 __fastcall WofpNormalizeFilePath(WCHAR *a1, wchar_t **a2)
{
  WCHAR *v3; // rsi
  wchar_t *v4; // rdi
  unsigned int i; // ebx
  const wchar_t *v6; // r8
  WCHAR *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  wchar_t *v10; // rdi
  bool v11; // zf
  WCHAR *v12; // rcx
  __int64 v13; // rdx
  WCHAR *v14; // rax
  __int64 v15; // r8
  unsigned __int64 v16; // rax
  WCHAR *v17; // r9
  __int64 v18; // rdx
  WCHAR *v19; // rcx
  WCHAR *v20; // rbx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rax
  SIZE_T v24; // r14
  HANDLE ProcessHeap; // rax
  wchar_t *v26; // rax
  wchar_t *v27; // rsi
  __int64 result; // rax
  DWORD cchReturnLength[4]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR szVolumeName[56]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR szVolumeMountPoint[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR szVolumePathNames[264]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v3 = a1;
  cchReturnLength[0] = 0;
  v4 = a1;
  for ( i = 0; i < 2; ++i )
  {
    v4 = wcschr(v4 + 1, 0x5Cu);
    if ( !v4 )
      return 2147942487LL;
  }
  v6 = L"\\\\?\\GlobalRoot";
  v7 = szVolumeMountPoint;
  v8 = 2147483646;
  v9 = 260;
  v10 = v4 + 1;
  do
  {
    if ( !v8 )
      break;
    if ( !*v6 )
      break;
    *v7++ = *v6++;
    --v8;
    --v9;
  }
  while ( v9 );
  v11 = v9 == 0;
  v12 = v7 - 1;
  v13 = 260;
  if ( !v11 )
    v12 = v7;
  v14 = szVolumeMountPoint;
  *v12 = 0;
  do
  {
    if ( !*v14 )
      break;
    ++v14;
    --v13;
  }
  while ( v13 );
  v15 = (260 - v13) & -(__int64)(v13 != 0);
  if ( v13 )
  {
    v16 = v10 - v3;
    if ( v16 <= 0x7FFFFFFE )
    {
      v17 = &szVolumeMountPoint[v15];
      v18 = 260 - v15;
      if ( v15 != 260 )
      {
        do
        {
          if ( !v16 )
            break;
          if ( !*v3 )
            break;
          *v17++ = *v3++;
          --v16;
          --v18;
        }
        while ( v18 );
      }
      v19 = v17 - 1;
      if ( v18 )
        v19 = v17;
      *v19 = 0;
    }
  }
  if ( GetVolumeNameForVolumeMountPointW(szVolumeMountPoint, szVolumeName, 0x32u) )
  {
    if ( GetVolumePathNamesForVolumeNameW(szVolumeName, szVolumePathNames, 0x104u, cchReturnLength)
      && szVolumePathNames[0] )
    {
      v20 = szVolumePathNames;
    }
    else
    {
      v20 = szVolumeName;
    }
  }
  else
  {
    v20 = szVolumeMountPoint;
  }
  v21 = -1;
  v22 = -1;
  do
    ++v22;
  while ( v20[v22] );
  if ( v22 && v20[v22 - 1] == 92 )
    v20[v22 - 1] = 0;
  v23 = -1;
  do
    ++v23;
  while ( v10[v23] );
  do
    ++v21;
  while ( v20[v21] );
  v24 = 2 * (v21 + v23) + 4;
  ProcessHeap = GetProcessHeap();
  v26 = (wchar_t *)HeapAlloc(ProcessHeap, 0, v24);
  v27 = v26;
  if ( !v26 )
    return 2147942414LL;
  StringCbPrintfW(v26, v24, L"%ws\\%ws", v20, v10);
  result = 0;
  *a2 = v27;
  return result;
}

```

## disassembly

```asm
0x180004ca4  mov     [rsp-8+arg_10], rbx
0x180004ca9  mov     [rsp-8+arg_18], rsi
0x180004cae  push    rbp
0x180004caf  push    rdi
0x180004cb0  push    r12
0x180004cb2  push    r14
0x180004cb4  push    r15
0x180004cb6  lea     rbp, [rsp-3E0h]
0x180004cbe  sub     rsp, 4E0h
0x180004cc5  mov     rax, cs:__security_cookie
0x180004ccc  xor     rax, rsp
0x180004ccf  mov     [rbp+400h+var_30], rax
0x180004cd6  xor     r12d, r12d
0x180004cd9  mov     r15, rdx
0x180004cdc  mov     rsi, rcx
0x180004cdf  mov     [rsp+500h+cchReturnLength], r12d
0x180004ce4  mov     rdi, rcx
0x180004ce7  mov     ebx, r12d
0x180004cea  lea     r14d, [r12+5Ch]
0x180004cef  mov     edx, r14d; Ch
0x180004cf2  lea     rcx, [rdi+2]; Str
0x180004cf6  call    cs:__imp_wcschr
0x180004cfc  mov     rdi, rax
0x180004cff  test    rax, rax
0x180004d02  jz      loc_180004EBE
0x180004d08  inc     ebx
0x180004d0a  cmp     ebx, 2
0x180004d0d  jb      short loc_180004CEF
0x180004d0f  mov     r10d, 7FFFFFFEh
0x180004d15  lea     r8, aGlobalroot; "\\\\?\\GlobalRoot"
0x180004d1c  mov     ebx, 104h
0x180004d21  lea     rax, [rbp+400h+szVolumeMountPoint]
0x180004d25  mov     ecx, r10d
0x180004d28  mov     edx, ebx
0x180004d2a  add     rdi, 2
0x180004d2e  test    rcx, rcx
0x180004d31  jz      short loc_180004D52
0x180004d33  movzx   r9d, word ptr [r8]
0x180004d37  test    r9w, r9w
0x180004d3b  jz      short loc_180004D52
0x180004d3d  mov     [rax], r9w
0x180004d41  add     r8, 2
0x180004d45  add     rax, 2
0x180004d49  dec     rcx
0x180004d4c  sub     rdx, 1
0x180004d50  jnz     short loc_180004D2E
0x180004d52  test    rdx, rdx
0x180004d55  lea     rcx, [rax-2]
0x180004d59  mov     rdx, rbx
0x180004d5c  cmovnz  rcx, rax
0x180004d60  lea     rax, [rbp+400h+szVolumeMountPoint]
0x180004d64  mov     [rcx], r12w
0x180004d68  cmp     [rax], r12w
0x180004d6c  jz      short loc_180004D78
0x180004d6e  add     rax, 2
0x180004d72  sub     rdx, 1
0x180004d76  jnz     short loc_180004D68
0x180004d78  mov     rcx, rbx
0x180004d7b  mov     rax, rdx
0x180004d7e  sub     rcx, rdx
0x180004d81  neg     rax
0x180004d84  sbb     r8, r8
0x180004d87  and     r8, rcx
0x180004d8a  test    rdx, rdx
0x180004d8d  jz      short loc_180004DDE
0x180004d8f  mov     rax, rdi
0x180004d92  sub     rax, rsi
0x180004d95  sar     rax, 1
0x180004d98  cmp     rax, r10
0x180004d9b  ja      short loc_180004DDE
0x180004d9d  mov     rdx, rbx
0x180004da0  lea     r9, [rbp+400h+szVolumeMountPoint]
0x180004da4  lea     r9, [r9+r8*2]
0x180004da8  sub     rdx, r8
0x180004dab  jz      short loc_180004DCF
0x180004dad  test    rax, rax
0x180004db0  jz      short loc_180004DCF
0x180004db2  movzx   ecx, word ptr [rsi]
0x180004db5  test    cx, cx
0x180004db8  jz      short loc_180004DCF
0x180004dba  mov     [r9], cx
0x180004dbe  add     rsi, 2
0x180004dc2  add     r9, 2
0x180004dc6  dec     rax
0x180004dc9  sub     rdx, 1
0x180004dcd  jnz     short loc_180004DAD
0x180004dcf  test    rdx, rdx
0x180004dd2  lea     rcx, [r9-2]
0x180004dd6  cmovnz  rcx, r9
0x180004dda  mov     [rcx], r12w
0x180004dde  mov     r8d, 32h ; '2'; cchBufferLength
0x180004de4  lea     rdx, [rsp+500h+szVolumeName]; lpszVolumeName
0x180004de9  lea     rcx, [rbp+400h+szVolumeMountPoint]; lpszVolumeMountPoint
0x180004ded  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180004df3  test    eax, eax
0x180004df5  jz      short loc_180004E2F
0x180004df7  lea     r9, [rsp+500h+cchReturnLength]; lpcchReturnLength
0x180004dfc  mov     r8d, ebx; cchBufferLength
0x180004dff  lea     rdx, [rbp+400h+szVolumePathNames]; lpszVolumePathNames
0x180004e06  lea     rcx, [rsp+500h+szVolumeName]; lpszVolumeName
0x180004e0b  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180004e11  test    eax, eax
0x180004e13  jz      short loc_180004E28
0x180004e15  cmp     [rbp+400h+szVolumePathNames], r12w
0x180004e1d  jz      short loc_180004E28
0x180004e1f  lea     rbx, [rbp+400h+szVolumePathNames]
0x180004e26  jmp     short loc_180004E33
0x180004e28  lea     rbx, [rsp+500h+szVolumeName]
0x180004e2d  jmp     short loc_180004E33
0x180004e2f  lea     rbx, [rbp+400h+szVolumeMountPoint]
0x180004e33  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180004e37  mov     rcx, rdx
0x180004e3a  inc     rcx
0x180004e3d  cmp     [rbx+rcx*2], r12w
0x180004e42  jnz     short loc_180004E3A
0x180004e44  test    rcx, rcx
0x180004e47  jz      short loc_180004E57
0x180004e49  cmp     [rbx+rcx*2-2], r14w
0x180004e4f  jnz     short loc_180004E57
0x180004e51  mov     [rbx+rcx*2-2], r12w
0x180004e57  mov     rax, rdx
0x180004e5a  inc     rax
0x180004e5d  cmp     [rdi+rax*2], r12w
0x180004e62  jnz     short loc_180004E5A
0x180004e64  inc     rdx
0x180004e67  cmp     [rbx+rdx*2], r12w
0x180004e6c  jnz     short loc_180004E64
0x180004e6e  add     rax, rdx
0x180004e71  lea     r14, ds:4[rax*2]
0x180004e79  call    cs:__imp_GetProcessHeap
0x180004e7f  mov     r8, r14; dwBytes
0x180004e82  xor     edx, edx; dwFlags
0x180004e84  mov     rcx, rax; hHeap
0x180004e87  call    cs:__imp_HeapAlloc
0x180004e8d  mov     rsi, rax
0x180004e90  test    rax, rax
0x180004e93  jnz     short loc_180004E9C
0x180004e95  mov     eax, 8007000Eh
0x180004e9a  jmp     short loc_180004EC3
0x180004e9c  mov     r9, rbx
0x180004e9f  mov     [rsp+500h+var_4E0], rdi
0x180004ea4  lea     r8, aWsWs; "%ws\\%ws"
0x180004eab  mov     rdx, r14; cbDest
0x180004eae  mov     rcx, rsi; pszDest
0x180004eb1  call    StringCbPrintfW
0x180004eb6  mov     eax, r12d
0x180004eb9  mov     [r15], rsi
0x180004ebc  jmp     short loc_180004EC3
0x180004ebe  mov     eax, 80070057h
0x180004ec3  mov     rcx, [rbp+400h+var_30]
0x180004eca  xor     rcx, rsp; StackCookie
0x180004ecd  call    __security_check_cookie
0x180004ed2  lea     r11, [rsp+500h+var_20]
0x180004eda  mov     rbx, [r11+40h]
0x180004ede  mov     rsi, [r11+48h]
0x180004ee2  mov     rsp, r11
0x180004ee5  pop     r15
0x180004ee7  pop     r14
0x180004ee9  pop     r12
0x180004eeb  pop     rdi
0x180004eec  pop     rbp
0x180004eed  retn
```
