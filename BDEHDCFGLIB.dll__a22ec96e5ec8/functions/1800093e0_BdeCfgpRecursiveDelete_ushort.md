# BdeCfgpRecursiveDelete(ushort *)

- ea: `0x1800093e0`
- end: `0x180009606`
- name: `?BdeCfgpRecursiveDelete@@YAJPEAG@Z`
- size: `550`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180007070`
- `0x1800093e0`

## callees

- `0x180006c30`
- `0x180008aac`
- `0x180008e1c`
- `0x1800093e0`
- `0x18001358e`
- `0x1800135c0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000944b`
- `KERNEL32!HeapAlloc` at `0x18000944b`
- `KERNEL32!GetProcessHeap` at `0x18000943a`
- `KERNEL32!GetProcessHeap` at `0x18000943a`
- `KERNEL32!GetLastError` at `0x18000959d`
- `KERNEL32!GetLastError` at `0x1800095b5`
- `KERNEL32!GetLastError` at `0x18000959d`
- `KERNEL32!GetLastError` at `0x1800095b5`
- `KERNEL32!FindFirstFileW` at `0x1800094de`
- `KERNEL32!FindFirstFileW` at `0x1800094de`
- `KERNEL32!FindNextFileW` at `0x180009589`
- `KERNEL32!FindNextFileW` at `0x180009589`
- `KERNEL32!FindClose` at `0x1800095da`
- `KERNEL32!FindClose` at `0x1800095da`
- `KERNEL32!RemoveDirectoryW` at `0x1800095ab`
- `KERNEL32!RemoveDirectoryW` at `0x1800095ab`

## pseudocode

```c
__int64 __fastcall BdeCfgpRecursiveDelete(LPCWSTR lpPathName)
{
  __int64 v2; // rax
  unsigned __int64 v3; // rsi
  SIZE_T v4; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v6; // rax
  WCHAR *v7; // rdi
  __int64 FirstFileW; // rsi
  unsigned int v9; // ebx
  __int64 v10; // rax
  WCHAR *v11; // r15
  __int64 v12; // rcx
  WCHAR *v13; // rax
  const wchar_t *v14; // r8
  __int64 v15; // rdx
  WCHAR *v16; // rcx
  BOOL NextFileW; // ebp
  __int64 v18; // rcx
  WCHAR *cFileName; // r8
  __int64 v20; // rdx
  WCHAR *v21; // rax
  WCHAR *v22; // rcx
  int v23; // eax
  signed int LastError; // eax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+20h] [rbp-2A8h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v2 = -1;
  do
    ++v2;
  while ( lpPathName[v2] );
  v3 = v2 + 262;
  v4 = 2 * (v2 + 262);
  ProcessHeap = GetProcessHeap();
  v6 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v4);
  v7 = v6;
  if ( !v6 )
  {
    FirstFileW = -1;
    v9 = -2147024882;
    goto LABEL_35;
  }
  v9 = 0;
  StringCchPrintfW(v6, v3, L"%s\\", lpPathName);
  v10 = -1;
  do
    ++v10;
  while ( v7[v10] );
  v11 = &v7[v10];
  v12 = 2147483646;
  v13 = v11;
  v14 = L"*";
  v15 = 261;
  do
  {
    if ( !v12 )
      break;
    if ( !*v14 )
      break;
    *v13++ = *v14++;
    --v12;
    --v15;
  }
  while ( v15 );
  v16 = v13 - 1;
  if ( v15 )
    v16 = v13;
  *v16 = 0;
  FirstFileW = (__int64)FindFirstFileW(v7, &FindFileData);
  if ( FirstFileW == -1 )
  {
LABEL_31:
    if ( GetLastError() == 18 )
      goto LABEL_32;
    goto LABEL_33;
  }
  NextFileW = 1;
  do
  {
    v18 = 2147483646;
    cFileName = FindFileData.cFileName;
    v20 = 261;
    v21 = v11;
    do
    {
      if ( !v18 )
        break;
      if ( !*cFileName )
        break;
      *v21++ = *cFileName++;
      --v18;
      --v20;
    }
    while ( v20 );
    v22 = v21 - 1;
    if ( v20 )
      v22 = v21;
    *v22 = 0;
    if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
    {
      if ( FindFileData.cFileName[0] == 46
        && (!FindFileData.cFileName[1] || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2]) )
      {
        goto LABEL_29;
      }
      v23 = BdeCfgpRecursiveDelete(v7);
    }
    else
    {
      v23 = BdeCfgpDeleteFile(v7);
    }
    v9 = v23;
    if ( v23 < 0 )
      break;
LABEL_29:
    NextFileW = FindNextFileW((HANDLE)FirstFileW, &FindFileData);
  }
  while ( NextFileW );
  if ( !NextFileW )
    goto LABEL_31;
LABEL_32:
  if ( !RemoveDirectoryW(lpPathName) )
  {
LABEL_33:
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_35:
  BdeCfgpFree(v7);
  if ( FirstFileW != -1 )
    FindClose((HANDLE)FirstFileW);
  return v9;
}

```

## disassembly

```asm
0x1800093e0  push    rbx
0x1800093e2  push    rbp
0x1800093e3  push    rsi
0x1800093e4  push    rdi
0x1800093e5  push    r12
0x1800093e7  push    r13
0x1800093e9  push    r14
0x1800093eb  push    r15
0x1800093ed  sub     rsp, 288h
0x1800093f4  mov     rax, cs:__security_cookie
0x1800093fb  xor     rax, rsp
0x1800093fe  mov     [rsp+2C8h+var_58], rax
0x180009406  mov     r14, rcx
0x180009409  xor     edx, edx; Val
0x18000940b  lea     rcx, [rsp+2C8h+FindFileData]; void *
0x180009410  mov     r8d, 250h; Size
0x180009416  call    memset_0
0x18000941b  or      r13, 0FFFFFFFFFFFFFFFFh
0x18000941f  mov     rax, r13
0x180009422  xor     r12d, r12d
0x180009425  inc     rax
0x180009428  cmp     [r14+rax*2], r12w
0x18000942d  jnz     short loc_180009425
0x18000942f  lea     rsi, [rax+106h]
0x180009436  lea     rbx, [rsi+rsi]
0x18000943a  call    cs:__imp_GetProcessHeap
0x180009440  mov     r8, rbx; dwBytes
0x180009443  mov     edx, 8; dwFlags
0x180009448  mov     rcx, rax; hHeap
0x18000944b  call    cs:__imp_HeapAlloc
0x180009451  mov     rdi, rax
0x180009454  test    rax, rax
0x180009457  jnz     short loc_180009466
0x180009459  mov     rsi, r13
0x18000945c  mov     ebx, 8007000Eh
0x180009461  jmp     loc_1800095CA
0x180009466  mov     r9, r14
0x180009469  lea     r8, aS; "%s\\"
0x180009470  mov     rdx, rsi; unsigned __int64
0x180009473  mov     rcx, rdi; unsigned __int16 *
0x180009476  mov     ebx, r12d
0x180009479  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000947e  mov     rax, r13
0x180009481  inc     rax
0x180009484  cmp     [rdi+rax*2], r12w
0x180009489  jnz     short loc_180009481
0x18000948b  lea     r15, [rdi+rax*2]
0x18000948f  mov     ecx, 7FFFFFFEh
0x180009494  mov     rax, r15
0x180009497  lea     r8, asc_1800170A8; "*"
0x18000949e  mov     edx, 105h
0x1800094a3  test    rcx, rcx
0x1800094a6  jz      short loc_1800094C7
0x1800094a8  movzx   r9d, word ptr [r8]
0x1800094ac  test    r9w, r9w
0x1800094b0  jz      short loc_1800094C7
0x1800094b2  mov     [rax], r9w
0x1800094b6  add     r8, 2
0x1800094ba  add     rax, 2
0x1800094be  dec     rcx
0x1800094c1  sub     rdx, 1
0x1800094c5  jnz     short loc_1800094A3
0x1800094c7  test    rdx, rdx
0x1800094ca  lea     rcx, [rax-2]
0x1800094ce  lea     rdx, [rsp+2C8h+FindFileData]; lpFindFileData
0x1800094d3  cmovnz  rcx, rax
0x1800094d7  mov     [rcx], r12w
0x1800094db  mov     rcx, rdi; lpFileName
0x1800094de  call    cs:__imp_FindFirstFileW
0x1800094e4  mov     rsi, rax
0x1800094e7  cmp     rax, r13
0x1800094ea  jz      loc_18000959D
0x1800094f0  mov     ebp, 1
0x1800094f5  mov     ecx, 7FFFFFFEh
0x1800094fa  lea     r8, [rsp+2C8h+FindFileData.cFileName]
0x1800094ff  mov     edx, 105h
0x180009504  mov     rax, r15
0x180009507  test    rcx, rcx
0x18000950a  jz      short loc_18000952B
0x18000950c  movzx   r9d, word ptr [r8]
0x180009510  test    r9w, r9w
0x180009514  jz      short loc_18000952B
0x180009516  mov     [rax], r9w
0x18000951a  add     r8, 2
0x18000951e  add     rax, 2
0x180009522  dec     rcx
0x180009525  sub     rdx, 1
0x180009529  jnz     short loc_180009507
0x18000952b  test    rdx, rdx
0x18000952e  lea     rcx, [rax-2]
0x180009532  cmovnz  rcx, rax
0x180009536  mov     [rcx], r12w
0x18000953a  test    byte ptr [rsp+2C8h+FindFileData.dwFileAttributes], 10h
0x18000953f  jz      short loc_180009573
0x180009541  cmp     [rsp+2C8h+FindFileData.cFileName], 2Eh ; '.'
0x180009547  movzx   eax, [rsp+2C8h+FindFileData.cFileName+2]
0x18000954c  jnz     short loc_180009569
0x18000954e  test    ax, ax
0x180009551  jz      short loc_180009581
0x180009553  cmp     [rsp+2C8h+FindFileData.cFileName], 2Eh ; '.'
0x180009559  jnz     short loc_180009569
0x18000955b  cmp     ax, 2Eh ; '.'
0x18000955f  jnz     short loc_180009569
0x180009561  cmp     [rsp+2C8h+FindFileData.cFileName+4], r12w
0x180009567  jz      short loc_180009581
0x180009569  mov     rcx, rdi; lpPathName
0x18000956c  call    ?BdeCfgpRecursiveDelete@@YAJPEAG@Z; BdeCfgpRecursiveDelete(ushort *)
0x180009571  jmp     short loc_18000957B
0x180009573  mov     rcx, rdi; lpFileName
0x180009576  call    ?BdeCfgpDeleteFile@@YAJPEAG@Z; BdeCfgpDeleteFile(ushort *)
0x18000957b  mov     ebx, eax
0x18000957d  test    eax, eax
0x18000957f  js      short loc_180009599
0x180009581  lea     rdx, [rsp+2C8h+FindFileData]; lpFindFileData
0x180009586  mov     rcx, rsi; hFindFile
0x180009589  call    cs:__imp_FindNextFileW
0x18000958f  mov     ebp, eax
0x180009591  test    eax, eax
0x180009593  jnz     loc_1800094F5
0x180009599  test    ebp, ebp
0x18000959b  jnz     short loc_1800095A8
0x18000959d  call    cs:__imp_GetLastError
0x1800095a3  cmp     eax, 12h
0x1800095a6  jnz     short loc_1800095B5
0x1800095a8  mov     rcx, r14; lpPathName
0x1800095ab  call    cs:__imp_RemoveDirectoryW
0x1800095b1  test    eax, eax
0x1800095b3  jnz     short loc_1800095CA
0x1800095b5  call    cs:__imp_GetLastError
0x1800095bb  mov     ebx, eax
0x1800095bd  test    eax, eax
0x1800095bf  jle     short loc_1800095CA
0x1800095c1  movzx   ebx, ax
0x1800095c4  or      ebx, 80070000h
0x1800095ca  mov     rcx, rdi; lpMem
0x1800095cd  call    ?BdeCfgpFree@@YAXPEAX@Z; BdeCfgpFree(void *)
0x1800095d2  cmp     rsi, r13
0x1800095d5  jz      short loc_1800095E0
0x1800095d7  mov     rcx, rsi; hFindFile
0x1800095da  call    cs:__imp_FindClose
0x1800095e0  mov     eax, ebx
0x1800095e2  mov     rcx, [rsp+2C8h+var_58]
0x1800095ea  xor     rcx, rsp; StackCookie
0x1800095ed  call    __security_check_cookie
0x1800095f2  add     rsp, 288h
0x1800095f9  pop     r15
0x1800095fb  pop     r14
0x1800095fd  pop     r13
0x1800095ff  pop     r12
0x180009601  pop     rdi
0x180009602  pop     rsi
0x180009603  pop     rbp
0x180009604  pop     rbx
0x180009605  retn
```
