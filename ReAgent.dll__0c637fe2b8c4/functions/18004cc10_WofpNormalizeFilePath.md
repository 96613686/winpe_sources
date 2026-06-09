# WofpNormalizeFilePath

- ea: `0x18004cc10`
- end: `0x18004cdba`
- name: `WofpNormalizeFilePath`
- size: `426`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x18004c820`

## callees

- `0x180006ed8`
- `0x18004ca58`
- `0x18004cae4`
- `0x18004cc10`
- `0x18005cf30`

## import_xrefs

- `msvcrt!wcschr` at `0x18004cc6a`
- `msvcrt!wcschr` at `0x18004cc6a`
- `KERNEL32!HeapAlloc` at `0x18004cd5a`
- `KERNEL32!HeapAlloc` at `0x18004cd5a`
- `KERNEL32!GetProcessHeap` at `0x18004cd4c`
- `KERNEL32!GetProcessHeap` at `0x18004cd4c`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18004ccc0`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18004ccc0`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x18004ccde`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x18004ccde`

## pseudocode

```c
__int64 __fastcall WofpNormalizeFilePath(wchar_t *pszSrc, wchar_t **a2)
{
  wchar_t *v4; // rax
  unsigned int i; // ebx
  wchar_t *v6; // rdi
  __int64 result; // rax
  WCHAR *v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rax
  SIZE_T v12; // r14
  HANDLE ProcessHeap; // rax
  wchar_t *v14; // rax
  wchar_t *v15; // rsi
  DWORD cchReturnLength[4]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR szVolumeName[56]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR szVolumePathNames[264]; // [rsp+2C0h] [rbp+1C0h] BYREF

  cchReturnLength[0] = 0;
  v4 = pszSrc;
  for ( i = 0; ; ++i )
  {
    v6 = v4 + 1;
    if ( i >= 2 )
      break;
    v4 = wcschr(v4 + 1, 0x5Cu);
    if ( !v4 )
      return 2147942487LL;
  }
  StringCchCopyW(pszDest, 0x104u, L"\\\\?\\GlobalRoot");
  StringCchCatNW(pszDest, 0x104u, pszSrc, v6 - pszSrc);
  if ( GetVolumeNameForVolumeMountPointW(pszDest, szVolumeName, 0x32u) )
  {
    if ( GetVolumePathNamesForVolumeNameW(szVolumeName, szVolumePathNames, 0x104u, cchReturnLength)
      && szVolumePathNames[0] )
    {
      v8 = szVolumePathNames;
    }
    else
    {
      v8 = szVolumeName;
    }
  }
  else
  {
    v8 = pszDest;
  }
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( v8[v10] );
  if ( v10 && v8[v10 - 1] == 92 )
    v8[v10 - 1] = 0;
  v11 = -1;
  do
    ++v11;
  while ( v6[v11] );
  do
    ++v9;
  while ( v8[v9] );
  v12 = 2 * (v9 + v11) + 4;
  ProcessHeap = GetProcessHeap();
  v14 = (wchar_t *)HeapAlloc(ProcessHeap, 0, v12);
  v15 = v14;
  if ( !v14 )
    return 2147942414LL;
  StringCbPrintfW(v14, v12, L"%ws\\%ws", v8, v6);
  result = 0;
  *a2 = v15;
  return result;
}

```

## disassembly

```asm
0x18004cc10  mov     [rsp-8+arg_10], rbx
0x18004cc15  mov     [rsp-8+arg_18], rsi
0x18004cc1a  push    rbp
0x18004cc1b  push    rdi
0x18004cc1c  push    r12
0x18004cc1e  push    r14
0x18004cc20  push    r15
0x18004cc22  lea     rbp, [rsp-3E0h]
0x18004cc2a  sub     rsp, 4E0h
0x18004cc31  mov     rax, cs:__security_cookie
0x18004cc38  xor     rax, rsp
0x18004cc3b  mov     [rbp+400h+var_30], rax
0x18004cc42  xor     r12d, r12d
0x18004cc45  mov     r15, rdx
0x18004cc48  mov     rsi, rcx
0x18004cc4b  mov     [rsp+500h+cchReturnLength], r12d
0x18004cc50  mov     rax, rcx
0x18004cc53  mov     ebx, r12d
0x18004cc56  lea     r14d, [r12+5Ch]
0x18004cc5b  lea     rdi, [rax+2]
0x18004cc5f  cmp     ebx, 2
0x18004cc62  jnb     short loc_18004CC83
0x18004cc64  mov     edx, r14d; Ch
0x18004cc67  mov     rcx, rdi; Str
0x18004cc6a  call    cs:__imp_wcschr
0x18004cc70  test    rax, rax
0x18004cc73  jz      short loc_18004CC79
0x18004cc75  inc     ebx
0x18004cc77  jmp     short loc_18004CC5B
0x18004cc79  mov     eax, 80070057h
0x18004cc7e  jmp     loc_18004CD8F
0x18004cc83  mov     ebx, 104h
0x18004cc88  lea     r8, aGlobalroot; "\\\\?\\GlobalRoot"
0x18004cc8f  mov     edx, ebx; unsigned __int64
0x18004cc91  lea     rcx, [rbp+400h+pszDest]; unsigned __int16 *
0x18004cc95  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004cc9a  mov     r9, rdi
0x18004cc9d  lea     rcx, [rbp+400h+pszDest]; pszDest
0x18004cca1  sub     r9, rsi
0x18004cca4  mov     r8, rsi; pszSrc
0x18004cca7  sar     r9, 1; cchToAppend
0x18004ccaa  mov     edx, ebx; cchDest
0x18004ccac  call    StringCchCatNW
0x18004ccb1  mov     r8d, 32h ; '2'; cchBufferLength
0x18004ccb7  lea     rdx, [rsp+500h+szVolumeName]; lpszVolumeName
0x18004ccbc  lea     rcx, [rbp+400h+pszDest]; lpszVolumeMountPoint
0x18004ccc0  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18004ccc6  test    eax, eax
0x18004ccc8  jz      short loc_18004CD02
0x18004ccca  lea     r9, [rsp+500h+cchReturnLength]; lpcchReturnLength
0x18004cccf  mov     r8d, ebx; cchBufferLength
0x18004ccd2  lea     rdx, [rbp+400h+szVolumePathNames]; lpszVolumePathNames
0x18004ccd9  lea     rcx, [rsp+500h+szVolumeName]; lpszVolumeName
0x18004ccde  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18004cce4  test    eax, eax
0x18004cce6  jz      short loc_18004CCFB
0x18004cce8  cmp     [rbp+400h+szVolumePathNames], r12w
0x18004ccf0  jz      short loc_18004CCFB
0x18004ccf2  lea     rbx, [rbp+400h+szVolumePathNames]
0x18004ccf9  jmp     short loc_18004CD06
0x18004ccfb  lea     rbx, [rsp+500h+szVolumeName]
0x18004cd00  jmp     short loc_18004CD06
0x18004cd02  lea     rbx, [rbp+400h+pszDest]
0x18004cd06  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004cd0a  mov     rcx, rdx
0x18004cd0d  inc     rcx
0x18004cd10  cmp     [rbx+rcx*2], r12w
0x18004cd15  jnz     short loc_18004CD0D
0x18004cd17  test    rcx, rcx
0x18004cd1a  jz      short loc_18004CD2A
0x18004cd1c  cmp     [rbx+rcx*2-2], r14w
0x18004cd22  jnz     short loc_18004CD2A
0x18004cd24  mov     [rbx+rcx*2-2], r12w
0x18004cd2a  mov     rax, rdx
0x18004cd2d  inc     rax
0x18004cd30  cmp     [rdi+rax*2], r12w
0x18004cd35  jnz     short loc_18004CD2D
0x18004cd37  inc     rdx
0x18004cd3a  cmp     [rbx+rdx*2], r12w
0x18004cd3f  jnz     short loc_18004CD37
0x18004cd41  add     rax, rdx
0x18004cd44  lea     r14, ds:4[rax*2]
0x18004cd4c  call    cs:__imp_GetProcessHeap
0x18004cd52  mov     r8, r14; dwBytes
0x18004cd55  xor     edx, edx; dwFlags
0x18004cd57  mov     rcx, rax; hHeap
0x18004cd5a  call    cs:__imp_HeapAlloc
0x18004cd60  mov     rsi, rax
0x18004cd63  test    rax, rax
0x18004cd66  jnz     short loc_18004CD6F
0x18004cd68  mov     eax, 8007000Eh
0x18004cd6d  jmp     short loc_18004CD8F
0x18004cd6f  mov     r9, rbx
0x18004cd72  mov     [rsp+500h+var_4E0], rdi
0x18004cd77  lea     r8, aWsWs; "%ws\\%ws"
0x18004cd7e  mov     rdx, r14; cbDest
0x18004cd81  mov     rcx, rsi; pszDest
0x18004cd84  call    StringCbPrintfW
0x18004cd89  mov     eax, r12d
0x18004cd8c  mov     [r15], rsi
0x18004cd8f  mov     rcx, [rbp+400h+var_30]
0x18004cd96  xor     rcx, rsp; StackCookie
0x18004cd99  call    __security_check_cookie
0x18004cd9e  lea     r11, [rsp+500h+var_20]
0x18004cda6  mov     rbx, [r11+40h]
0x18004cdaa  mov     rsi, [r11+48h]
0x18004cdae  mov     rsp, r11
0x18004cdb1  pop     r15
0x18004cdb3  pop     r14
0x18004cdb5  pop     r12
0x18004cdb7  pop     rdi
0x18004cdb8  pop     rbp
0x18004cdb9  retn
```
