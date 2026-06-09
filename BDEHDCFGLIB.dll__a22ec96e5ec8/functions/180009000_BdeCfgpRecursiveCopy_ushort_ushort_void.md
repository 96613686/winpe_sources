# BdeCfgpRecursiveCopy(ushort *,ushort *,void *)

- ea: `0x180009000`
- end: `0x1800093da`
- name: `?BdeCfgpRecursiveCopy@@YAJPEAG0PEAX@Z`
- size: `986`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800086f8`
- `0x180009000`

## callees

- `0x180006c30`
- `0x180008968`
- `0x1800089c4`
- `0x180008e1c`
- `0x180009000`
- `0x18001358e`
- `0x1800135c0`

## import_xrefs

- `ADVAPI32!SetNamedSecurityInfoW` at `0x1800091e2`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x1800091e2`
- `KERNEL32!HeapAlloc` at `0x18000907f`
- `KERNEL32!HeapAlloc` at `0x1800090c2`
- `KERNEL32!HeapAlloc` at `0x18000907f`
- `KERNEL32!HeapAlloc` at `0x1800090c2`
- `KERNEL32!GetProcessHeap` at `0x18000906a`
- `KERNEL32!GetProcessHeap` at `0x1800090b3`
- `KERNEL32!GetProcessHeap` at `0x18000906a`
- `KERNEL32!GetProcessHeap` at `0x1800090b3`
- `KERNEL32!GetLastError` at `0x180009198`
- `KERNEL32!GetLastError` at `0x1800091a5`
- `KERNEL32!GetLastError` at `0x180009372`
- `KERNEL32!GetLastError` at `0x180009198`
- `KERNEL32!GetLastError` at `0x1800091a5`
- `KERNEL32!GetLastError` at `0x180009372`
- `KERNEL32!CompareStringW` at `0x180009343`
- `KERNEL32!CompareStringW` at `0x180009343`
- `KERNEL32!FindFirstFileW` at `0x180009169`
- `KERNEL32!FindFirstFileW` at `0x180009169`
- `KERNEL32!CreateDirectoryExW` at `0x18000918e`
- `KERNEL32!CreateDirectoryExW` at `0x18000918e`
- `KERNEL32!FindNextFileW` at `0x180009356`
- `KERNEL32!FindNextFileW` at `0x180009356`
- `KERNEL32!FindClose` at `0x1800093a7`
- `KERNEL32!FindClose` at `0x1800093a7`

## pseudocode

```c
__int64 __fastcall BdeCfgpRecursiveCopy(unsigned __int16 *a1, unsigned __int16 *a2, void *a3)
{
  __int64 v5; // rax
  __int64 FirstFileW; // rbp
  unsigned __int64 v7; // rdi
  SIZE_T v8; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v10; // r15
  unsigned __int16 *v11; // r14
  signed int v12; // ebx
  __int64 v13; // rax
  unsigned __int64 v14; // rsi
  SIZE_T v15; // rbx
  HANDLE v16; // rax
  unsigned __int16 *v17; // rax
  BOOL NextFileW; // ebx
  __int64 v19; // rdi
  __int64 v20; // rax
  const WCHAR *v21; // r13
  __int64 v22; // rcx
  const wchar_t *v23; // r8
  __int64 v24; // rdx
  WCHAR *v25; // rax
  WCHAR *v26; // rcx
  unsigned __int16 *v27; // rsi
  signed int LastError; // eax
  signed int v29; // eax
  unsigned __int16 *v30; // rdi
  WCHAR *cFileName; // r8
  __int64 v32; // rcx
  __int64 v33; // rdx
  WCHAR *v34; // rax
  WCHAR *v35; // rcx
  __int64 v36; // r8
  WCHAR *v37; // r9
  __int64 v38; // rdx
  unsigned __int16 *v39; // rax
  unsigned __int16 *v40; // rcx
  __int64 v41; // r9
  int v42; // eax
  _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-298h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v5 = -1;
  FirstFileW = -1;
  do
    ++v5;
  while ( a1[v5] );
  v7 = v5 + 262;
  v8 = 2 * (v5 + 262);
  ProcessHeap = GetProcessHeap();
  v10 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v8);
  if ( !v10 )
  {
    v11 = 0;
LABEL_5:
    v12 = -2147024882;
    goto LABEL_60;
  }
  v13 = -1;
  do
    ++v13;
  while ( a2[v13] );
  v14 = v13 + 262;
  v15 = 2 * (v13 + 262);
  v16 = GetProcessHeap();
  v17 = (unsigned __int16 *)HeapAlloc(v16, 8u, v15);
  NextFileW = 0;
  v11 = v17;
  if ( !v17 )
    goto LABEL_5;
  StringCchPrintfW(v10, v7, L"%s\\", a1);
  v19 = -1;
  v20 = -1;
  do
    ++v20;
  while ( v10[v20] );
  v21 = &v10[v20];
  StringCchPrintfW(v11, v14, L"%s\\", a2);
  do
    ++v19;
  while ( v11[v19] );
  v22 = 2147483646;
  v23 = L"*";
  v24 = 261;
  v25 = (WCHAR *)v21;
  do
  {
    if ( !v22 )
      break;
    if ( !*v23 )
      break;
    *v25++ = *v23++;
    --v22;
    --v24;
  }
  while ( v24 );
  v26 = v25 - 1;
  if ( v24 )
    v26 = v25;
  *v26 = 0;
  v27 = a1;
  FirstFileW = (__int64)FindFirstFileW(v10, &FindFileData);
  if ( FirstFileW == -1 )
  {
LABEL_28:
    v30 = &v11[v19];
    if ( !NextFileW )
      goto LABEL_58;
    while ( 1 )
    {
      cFileName = FindFileData.cFileName;
      v32 = 2147483646;
      v33 = 261;
      v34 = (WCHAR *)v21;
      do
      {
        if ( !v32 )
          break;
        if ( !*cFileName )
          break;
        *v34++ = *cFileName++;
        --v32;
        --v33;
      }
      while ( v33 );
      v35 = v34 - 1;
      v36 = 2147483646;
      v37 = FindFileData.cFileName;
      if ( v33 )
        v35 = v34;
      v38 = 261;
      v39 = v30;
      *v35 = 0;
      do
      {
        if ( !v36 )
          break;
        if ( !*v37 )
          break;
        *v39++ = *v37++;
        --v36;
        --v38;
      }
      while ( v38 );
      v40 = v39 - 1;
      if ( v38 )
        v40 = v39;
      *v40 = 0;
      if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
      {
        if ( (FindFileData.cFileName[0] != 46
           || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]))
          && BdeCfgpRecursiveCopy(v10, v11, a3) < 0 )
        {
          goto LABEL_57;
        }
      }
      else if ( (int)BdeCfgpCopyFile(v10, v11, (void *)v36) < 0 )
      {
        v41 = -1;
        do
          ++v41;
        while ( v21[v41] );
        if ( v41 == 3 )
        {
          v42 = CompareStringW(0x7Fu, 1u, v21, 3, L"BCD", 3);
        }
        else
        {
          if ( v41 != 7 )
            goto LABEL_57;
          v42 = CompareStringW(0x7Fu, 1u, v21, 7, L"BCD.LOG", 7);
        }
        if ( v42 != 2 )
        {
LABEL_57:
          v27 = a1;
          if ( NextFileW )
            goto LABEL_59;
LABEL_58:
          if ( GetLastError() == 18 )
          {
LABEL_59:
            v12 = BdeCfgpCopySecurityDescriptor(v27, a2);
            goto LABEL_60;
          }
LABEL_22:
          LastError = GetLastError();
          v12 = LastError;
          if ( LastError > 0 )
            v12 = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_60;
        }
      }
      NextFileW = FindNextFileW((HANDLE)FirstFileW, &FindFileData);
      if ( !NextFileW )
        goto LABEL_57;
    }
  }
  if ( !CreateDirectoryExW(a1, a2, 0) && GetLastError() != 183 )
    goto LABEL_22;
  v29 = SetNamedSecurityInfoW(a2, SE_FILE_OBJECT, 1u, a3, 0, 0, 0);
  v12 = v29;
  if ( v29 > 0 )
    v12 = (unsigned __int16)v29 | 0x80070000;
  if ( v12 >= 0 )
  {
    NextFileW = 1;
    goto LABEL_28;
  }
LABEL_60:
  BdeCfgpFree(v10);
  BdeCfgpFree(v11);
  if ( FirstFileW != -1 )
    FindClose((HANDLE)FirstFileW);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180009000  mov     [rsp+arg_18], rbx
0x180009005  push    rbp
0x180009006  push    rsi
0x180009007  push    rdi
0x180009008  push    r12
0x18000900a  push    r13
0x18000900c  push    r14
0x18000900e  push    r15
0x180009010  sub     rsp, 2B0h
0x180009017  mov     rax, cs:__security_cookie
0x18000901e  xor     rax, rsp
0x180009021  mov     [rsp+2E8h+var_48], rax
0x180009029  mov     [rsp+2E8h+psidOwner], r8
0x18000902e  mov     r12, rdx
0x180009031  mov     r13, rcx
0x180009034  mov     [rsp+2E8h+lpTemplateDirectory], rcx
0x180009039  xor     edx, edx; Val
0x18000903b  lea     rcx, [rsp+2E8h+FindFileData]; void *
0x180009040  mov     r8d, 250h; Size
0x180009046  call    memset_0
0x18000904b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000904f  mov     rbp, rax
0x180009052  xor     esi, esi
0x180009054  inc     rax
0x180009057  cmp     [r13+rax*2+0], si
0x18000905d  jnz     short loc_180009054
0x18000905f  lea     rdi, [rax+106h]
0x180009066  lea     rbx, [rdi+rdi]
0x18000906a  call    cs:__imp_GetProcessHeap
0x180009070  mov     r14d, 8
0x180009076  mov     r8, rbx; dwBytes
0x180009079  mov     rcx, rax; hHeap
0x18000907c  mov     edx, r14d; dwFlags
0x18000907f  call    cs:__imp_HeapAlloc
0x180009085  mov     r15, rax
0x180009088  test    rax, rax
0x18000908b  jnz     short loc_18000909A
0x18000908d  mov     r14, rsi
0x180009090  mov     ebx, 8007000Eh
0x180009095  jmp     loc_18000938E
0x18000909a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000909e  inc     rax
0x1800090a1  cmp     [r12+rax*2], si
0x1800090a6  jnz     short loc_18000909E
0x1800090a8  lea     rsi, [rax+106h]
0x1800090af  lea     rbx, [rsi+rsi]
0x1800090b3  call    cs:__imp_GetProcessHeap
0x1800090b9  mov     r8, rbx; dwBytes
0x1800090bc  mov     edx, r14d; dwFlags
0x1800090bf  mov     rcx, rax; hHeap
0x1800090c2  call    cs:__imp_HeapAlloc
0x1800090c8  xor     ebx, ebx
0x1800090ca  mov     r14, rax
0x1800090cd  test    rax, rax
0x1800090d0  jz      short loc_180009090
0x1800090d2  mov     r9, r13
0x1800090d5  lea     r8, aS; "%s\\"
0x1800090dc  mov     rdx, rdi; unsigned __int64
0x1800090df  mov     rcx, r15; unsigned __int16 *
0x1800090e2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800090e7  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800090eb  mov     rax, rdi
0x1800090ee  inc     rax
0x1800090f1  cmp     [r15+rax*2], bx
0x1800090f6  jnz     short loc_1800090EE
0x1800090f8  mov     r9, r12
0x1800090fb  lea     r8, aS; "%s\\"
0x180009102  mov     rdx, rsi; unsigned __int64
0x180009105  lea     r13, [r15+rax*2]
0x180009109  mov     rcx, r14; unsigned __int16 *
0x18000910c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009111  inc     rdi
0x180009114  cmp     [r14+rdi*2], bx
0x180009119  jnz     short loc_180009111
0x18000911b  mov     ecx, 7FFFFFFEh
0x180009120  lea     r8, asc_1800170A8; "*"
0x180009127  mov     edx, 105h
0x18000912c  mov     rax, r13
0x18000912f  test    rcx, rcx
0x180009132  jz      short loc_180009153
0x180009134  movzx   r9d, word ptr [r8]
0x180009138  test    r9w, r9w
0x18000913c  jz      short loc_180009153
0x18000913e  mov     [rax], r9w
0x180009142  add     r8, 2
0x180009146  add     rax, 2
0x18000914a  dec     rcx
0x18000914d  sub     rdx, 1
0x180009151  jnz     short loc_18000912F
0x180009153  test    rdx, rdx
0x180009156  lea     rcx, [rax-2]
0x18000915a  lea     rdx, [rsp+2E8h+FindFileData]; lpFindFileData
0x18000915f  cmovnz  rcx, rax
0x180009163  mov     [rcx], bx
0x180009166  mov     rcx, r15; lpFileName
0x180009169  call    cs:__imp_FindFirstFileW
0x18000916f  mov     rsi, [rsp+2E8h+lpTemplateDirectory]
0x180009174  mov     rbp, rax
0x180009177  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000917b  jnz     short loc_180009185
0x18000917d  xor     r10d, r10d
0x180009180  jmp     loc_180009207
0x180009185  xor     r8d, r8d; lpSecurityAttributes
0x180009188  mov     rdx, r12; lpNewDirectory
0x18000918b  mov     rcx, rsi; lpTemplateDirectory
0x18000918e  call    cs:__imp_CreateDirectoryExW
0x180009194  test    eax, eax
0x180009196  jnz     short loc_1800091C3
0x180009198  call    cs:__imp_GetLastError
0x18000919e  cmp     eax, 0B7h
0x1800091a3  jz      short loc_1800091C3
0x1800091a5  call    cs:__imp_GetLastError
0x1800091ab  mov     ebx, eax
0x1800091ad  test    eax, eax
0x1800091af  jle     loc_18000938E
0x1800091b5  movzx   ebx, ax
0x1800091b8  or      ebx, 80070000h
0x1800091be  jmp     loc_18000938E
0x1800091c3  mov     r9, [rsp+2E8h+psidOwner]; psidOwner
0x1800091c8  mov     edx, 1; ObjectType
0x1800091cd  mov     [rsp+2E8h+pSacl], rbx; pSacl
0x1800091d2  mov     r8d, edx; SecurityInfo
0x1800091d5  mov     [rsp+2E8h+pDacl], rbx; pDacl
0x1800091da  mov     rcx, r12; pObjectName
0x1800091dd  mov     [rsp+2E8h+psidGroup], rbx; psidGroup
0x1800091e2  call    cs:__imp_SetNamedSecurityInfoW
0x1800091e8  xor     r10d, r10d
0x1800091eb  mov     ebx, eax
0x1800091ed  test    eax, eax
0x1800091ef  jle     short loc_1800091FA
0x1800091f1  movzx   ebx, ax
0x1800091f4  or      ebx, 80070000h
0x1800091fa  test    ebx, ebx
0x1800091fc  js      loc_18000938E
0x180009202  mov     ebx, 1
0x180009207  lea     rdi, [r14+rdi*2]
0x18000920b  test    ebx, ebx
0x18000920d  jz      loc_180009372
0x180009213  mov     rsi, [rsp+2E8h+psidOwner]
0x180009218  mov     r11d, 7FFFFFFEh
0x18000921e  lea     r8, [rsp+2E8h+FindFileData.cFileName]
0x180009223  mov     ecx, r11d
0x180009226  mov     edx, 105h
0x18000922b  mov     rax, r13
0x18000922e  test    rcx, rcx
0x180009231  jz      short loc_180009252
0x180009233  movzx   r9d, word ptr [r8]
0x180009237  test    r9w, r9w
0x18000923b  jz      short loc_180009252
0x18000923d  mov     [rax], r9w
0x180009241  add     r8, 2
0x180009245  add     rax, 2
0x180009249  dec     rcx
0x18000924c  sub     rdx, 1
0x180009250  jnz     short loc_18000922E
0x180009252  test    rdx, rdx
0x180009255  lea     rcx, [rax-2]
0x180009259  mov     r8, r11
0x18000925c  lea     r9, [rsp+2E8h+FindFileData.cFileName]
0x180009261  cmovnz  rcx, rax
0x180009265  mov     edx, 105h
0x18000926a  mov     rax, rdi
0x18000926d  mov     [rcx], r10w
0x180009271  test    r8, r8
0x180009274  jz      short loc_180009293
0x180009276  movzx   ecx, word ptr [r9]
0x18000927a  test    cx, cx
0x18000927d  jz      short loc_180009293
0x18000927f  mov     [rax], cx
0x180009282  add     r9, 2
0x180009286  add     rax, 2
0x18000928a  dec     r8; void *
0x18000928d  sub     rdx, 1
0x180009291  jnz     short loc_180009271
0x180009293  test    rdx, rdx
0x180009296  lea     rcx, [rax-2]
0x18000929a  cmovnz  rcx, rax
0x18000929e  mov     [rcx], r10w
0x1800092a2  test    byte ptr [rsp+2E8h+FindFileData.dwFileAttributes], 10h
0x1800092a7  jz      short loc_1800092EC
0x1800092a9  cmp     [rsp+2E8h+FindFileData.cFileName], 2Eh ; '.'
0x1800092af  movzx   eax, [rsp+2E8h+FindFileData.cFileName+2]
0x1800092b4  jnz     short loc_1800092D8
0x1800092b6  test    ax, ax
0x1800092b9  jz      loc_18000934E
0x1800092bf  cmp     [rsp+2E8h+FindFileData.cFileName], 2Eh ; '.'
0x1800092c5  jnz     short loc_1800092D8
0x1800092c7  cmp     ax, 2Eh ; '.'
0x1800092cb  jnz     short loc_1800092D8
0x1800092cd  cmp     [rsp+2E8h+FindFileData.cFileName+4], r10w
0x1800092d6  jz      short loc_18000934E
0x1800092d8  mov     r8, rsi; void *
0x1800092db  mov     rdx, r14; unsigned __int16 *
0x1800092de  mov     rcx, r15; unsigned __int16 *
0x1800092e1  call    ?BdeCfgpRecursiveCopy@@YAJPEAG0PEAX@Z; BdeCfgpRecursiveCopy(ushort *,ushort *,void *)
0x1800092e6  test    eax, eax
0x1800092e8  js      short loc_180009369
0x1800092ea  jmp     short loc_18000934E
0x1800092ec  mov     rdx, r14; lpFileName
0x1800092ef  mov     rcx, r15; unsigned __int16 *
0x1800092f2  call    ?BdeCfgpCopyFile@@YAJPEAG0PEAX@Z; BdeCfgpCopyFile(ushort *,ushort *,void *)
0x1800092f7  xor     r10d, r10d
0x1800092fa  test    eax, eax
0x1800092fc  jns     short loc_18000934E
0x1800092fe  or      r9, 0FFFFFFFFFFFFFFFFh
0x180009302  inc     r9; cchCount1
0x180009305  cmp     [r13+r9*2+0], r10w
0x18000930b  jnz     short loc_180009302
0x18000930d  cmp     r9, 3
0x180009311  jnz     short loc_180009321
0x180009313  mov     dword ptr [rsp+2E8h+pDacl], r9d
0x180009318  lea     rax, aBcd; "BCD"
0x18000931f  jmp     short loc_180009333
0x180009321  cmp     r9, 7
0x180009325  jnz     short loc_180009369
0x180009327  mov     dword ptr [rsp+2E8h+pDacl], r9d; cchCount2
0x18000932c  lea     rax, aBcdLog; "BCD.LOG"
0x180009333  mov     edx, 1; dwCmpFlags
0x180009338  mov     [rsp+2E8h+psidGroup], rax; lpString2
0x18000933d  mov     r8, r13; lpString1
0x180009340  lea     ecx, [rdx+7Eh]; Locale
0x180009343  call    cs:__imp_CompareStringW
0x180009349  cmp     eax, 2
0x18000934c  jnz     short loc_180009369
0x18000934e  lea     rdx, [rsp+2E8h+FindFileData]; lpFindFileData
0x180009353  mov     rcx, rbp; hFindFile
0x180009356  call    cs:__imp_FindNextFileW
0x18000935c  xor     r10d, r10d
0x18000935f  mov     ebx, eax
0x180009361  test    eax, eax
0x180009363  jnz     loc_180009218
0x180009369  mov     rsi, [rsp+2E8h+lpTemplateDirectory]
0x18000936e  test    ebx, ebx
0x180009370  jnz     short loc_180009381
0x180009372  call    cs:__imp_GetLastError
0x180009378  cmp     eax, 12h
0x18000937b  jnz     loc_1800091A5
0x180009381  mov     rdx, r12; unsigned __int16 *
0x180009384  mov     rcx, rsi; unsigned __int16 *
0x180009387  call    ?BdeCfgpCopySecurityDescriptor@@YAJPEAG0@Z; BdeCfgpCopySecurityDescriptor(ushort *,ushort *)
0x18000938c  mov     ebx, eax
0x18000938e  mov     rcx, r15; lpMem
0x180009391  call    ?BdeCfgpFree@@YAXPEAX@Z; BdeCfgpFree(void *)
0x180009396  mov     rcx, r14; lpMem
0x180009399  call    ?BdeCfgpFree@@YAXPEAX@Z; BdeCfgpFree(void *)
0x18000939e  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x1800093a2  jz      short loc_1800093AD
0x1800093a4  mov     rcx, rbp; hFindFile
0x1800093a7  call    cs:__imp_FindClose
0x1800093ad  mov     eax, ebx
0x1800093af  mov     rcx, [rsp+2E8h+var_48]
0x1800093b7  xor     rcx, rsp; StackCookie
0x1800093ba  call    __security_check_cookie
0x1800093bf  mov     rbx, [rsp+2E8h+arg_18]
0x1800093c7  add     rsp, 2B0h
0x1800093ce  pop     r15
0x1800093d0  pop     r14
0x1800093d2  pop     r13
0x1800093d4  pop     r12
0x1800093d6  pop     rdi
0x1800093d7  pop     rsi
0x1800093d8  pop     rbp
0x1800093d9  retn
```
