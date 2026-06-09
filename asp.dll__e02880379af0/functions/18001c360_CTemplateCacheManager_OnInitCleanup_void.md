# CTemplateCacheManager::OnInitCleanup(void *)

- ea: `0x18001c360`
- end: `0x18001c61a`
- name: `?OnInitCleanup@CTemplateCacheManager@@CAKPEAX@Z`
- size: `698`
- prototype: `__int64 __fastcall(char *lpThreadParameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x18001c360`
- `0x180023d86`
- `0x180023dd0`

## import_xrefs

- `msvcrt!isdigit` at `0x18001c464`
- `msvcrt!isdigit` at `0x18001c486`
- `msvcrt!isdigit` at `0x18001c464`
- `msvcrt!isdigit` at `0x18001c486`
- `msvcrt!sprintf_s` at `0x18001c3e3`
- `msvcrt!sprintf_s` at `0x18001c3e3`
- `msvcrt!strcpy_s` at `0x18001c4d4`
- `msvcrt!strcpy_s` at `0x18001c50c`
- `msvcrt!strcpy_s` at `0x18001c546`
- `msvcrt!strcpy_s` at `0x18001c4d4`
- `msvcrt!strcpy_s` at `0x18001c50c`
- `msvcrt!strcpy_s` at `0x18001c546`
- `KERNEL32!HeapFree` at `0x18001c5e8`
- `KERNEL32!HeapFree` at `0x18001c5e8`
- `KERNEL32!FindClose` at `0x18001c579`
- `KERNEL32!FindClose` at `0x18001c5b3`
- `KERNEL32!FindClose` at `0x18001c579`
- `KERNEL32!FindClose` at `0x18001c5b3`
- `KERNEL32!FindNextFileA` at `0x18001c56c`
- `KERNEL32!FindNextFileA` at `0x18001c5a2`
- `KERNEL32!FindNextFileA` at `0x18001c56c`
- `KERNEL32!FindNextFileA` at `0x18001c5a2`
- `KERNEL32!DeleteFileA` at `0x18001c553`
- `KERNEL32!DeleteFileA` at `0x18001c553`
- `KERNEL32!FindFirstFileA` at `0x18001c40f`
- `KERNEL32!FindFirstFileA` at `0x18001c520`
- `KERNEL32!FindFirstFileA` at `0x18001c40f`
- `KERNEL32!FindFirstFileA` at `0x18001c520`
- `KERNEL32!RemoveDirectoryA` at `0x18001c58b`
- `KERNEL32!RemoveDirectoryA` at `0x18001c58b`
- `KERNEL32!Wow64EnableWow64FsRedirection` at `0x18001c3c5`
- `KERNEL32!Wow64EnableWow64FsRedirection` at `0x18001c5d1`
- `KERNEL32!Wow64EnableWow64FsRedirection` at `0x18001c3c5`
- `KERNEL32!Wow64EnableWow64FsRedirection` at `0x18001c5d1`
- `KERNEL32!GetCurrentProcess` at `0x18001c39d`
- `KERNEL32!GetCurrentProcess` at `0x18001c39d`
- `KERNEL32!IsWow64Process` at `0x18001c3ab`
- `KERNEL32!IsWow64Process` at `0x18001c3ab`
- `KERNEL32!OpenProcess` at `0x18001c4a2`
- `KERNEL32!OpenProcess` at `0x18001c4a2`
- `KERNEL32!CloseHandle` at `0x18001c4b0`
- `KERNEL32!CloseHandle` at `0x18001c4b0`
- `KERNEL32!GetLastError` at `0x18001c4bb`
- `KERNEL32!GetLastError` at `0x18001c4bb`

## pseudocode

```c
__int64 __fastcall CTemplateCacheManager::OnInitCleanup(char *lpThreadParameter)
{
  char *v1; // rsi
  HANDLE CurrentProcess; // rax
  BOOL v3; // r13d
  HANDLE FirstFileA; // r12
  __int64 v5; // rcx
  unsigned int v6; // ecx
  unsigned int v7; // edi
  char *v8; // r15
  CHAR *v9; // r14
  DWORD v10; // ebx
  int v11; // eax
  HANDLE v12; // rax
  __int64 v13; // rcx
  __int64 v14; // r14
  HANDLE v15; // rbx
  rsize_t v16; // rsi
  BOOL Wow64Process; // [rsp+20h] [rbp-E0h] BYREF
  BOOL v19; // [rsp+24h] [rbp-DCh]
  rsize_t SizeInBytes; // [rsp+28h] [rbp-D8h]
  char *v21; // [rsp+30h] [rbp-D0h]
  _WIN32_FIND_DATAA FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  struct _WIN32_FIND_DATAA v23; // [rsp+180h] [rbp+80h] BYREF
  CHAR Buffer[304]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v1 = lpThreadParameter;
  v21 = lpThreadParameter;
  Wow64Process = 0;
  CurrentProcess = GetCurrentProcess();
  v19 = IsWow64Process(CurrentProcess, &Wow64Process);
  v3 = v19;
  if ( v19 && Wow64Process )
    Wow64EnableWow64FsRedirection(0);
  if ( sprintf_s(Buffer, 0x124u, "%s\\PID*.TMP", v1) < 0 )
    return 122;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileA = FindFirstFileA(Buffer, &FindFileData);
  memset_0(&v23, 0, sizeof(v23));
  if ( FirstFileA != (HANDLE)-1LL )
  {
    v5 = -1;
    do
      ++v5;
    while ( v1[v5] );
    v6 = v5 + 1;
    if ( v6 < 0x124 )
    {
      v7 = 292 - v6;
      v8 = &Buffer[v6];
      while ( 1 )
      {
        v9 = &FindFileData.cFileName[3];
        v10 = 0;
        if ( isdigit(FindFileData.cFileName[3]) )
        {
          do
          {
            v11 = *v9++;
            v10 = v11 + 2 * (v10 + 4 * (v10 - 6));
          }
          while ( isdigit(*v9) );
          if ( v10 )
          {
            v12 = OpenProcess(0x100000u, 0, v10);
            if ( v12 )
            {
              CloseHandle(v12);
            }
            else if ( GetLastError() == 87 )
            {
              strcpy_s(v8, v7, FindFileData.cFileName);
              v13 = -1;
              do
                ++v13;
              while ( v8[v13] );
              v14 = (unsigned int)v13;
              v8[(unsigned int)v13] = 92;
              SizeInBytes = v7 - (unsigned int)v13 - 1;
              strcpy_s(&v8[(unsigned int)v13 + 1], (unsigned int)SizeInBytes, "ASP*.TMP");
              v15 = FindFirstFileA(Buffer, &v23);
              if ( v15 != (HANDLE)-1LL )
              {
                v16 = SizeInBytes;
                do
                {
                  strcpy_s(&v8[v14 + 1], v16, v23.cFileName);
                  DeleteFileA(Buffer);
                }
                while ( !g_fShutDownInProgress && FindNextFileA(v15, &v23) );
                FindClose(v15);
              }
              v8[v14] = 0;
              RemoveDirectoryA(Buffer);
              if ( g_fShutDownInProgress )
              {
LABEL_25:
                FindClose(FirstFileA);
                v1 = v21;
                v3 = v19;
                goto LABEL_26;
              }
            }
          }
        }
        if ( !FindNextFileA(FirstFileA, &FindFileData) )
          goto LABEL_25;
      }
    }
    return 122;
  }
LABEL_26:
  if ( v3 && Wow64Process )
    Wow64EnableWow64FsRedirection(1u);
  if ( v1 )
    HeapFree(g_hDenaliHeap, 0, v1);
  return 0;
}

```

## disassembly

```asm
0x18001c360  push    rbp
0x18001c362  push    rbx
0x18001c363  push    rsi
0x18001c364  push    rdi
0x18001c365  push    r12
0x18001c367  push    r13
0x18001c369  push    r14
0x18001c36b  push    r15
0x18001c36d  lea     rbp, [rsp-308h]
0x18001c375  sub     rsp, 408h
0x18001c37c  mov     rax, cs:__security_cookie
0x18001c383  xor     rax, rsp
0x18001c386  mov     [rbp+340h+var_50], rax
0x18001c38d  mov     rsi, rcx
0x18001c390  mov     [rsp+440h+var_410], rcx
0x18001c395  mov     [rsp+440h+Wow64Process], 0
0x18001c39d  call    cs:__imp_GetCurrentProcess
0x18001c3a3  mov     rcx, rax; hProcess
0x18001c3a6  lea     rdx, [rsp+440h+Wow64Process]; Wow64Process
0x18001c3ab  call    cs:__imp_IsWow64Process
0x18001c3b1  mov     [rsp+440h+var_41C], eax
0x18001c3b5  mov     r13d, eax
0x18001c3b8  test    eax, eax
0x18001c3ba  jz      short loc_18001C3CB
0x18001c3bc  cmp     [rsp+440h+Wow64Process], 0
0x18001c3c1  jz      short loc_18001C3CB
0x18001c3c3  xor     ecx, ecx; Wow64FsEnableRedirection
0x18001c3c5  call    cs:__imp_Wow64EnableWow64FsRedirection
0x18001c3cb  mov     edi, 124h
0x18001c3d0  lea     r8, aSPidTmp; "%s\\PID*.TMP"
0x18001c3d7  mov     edx, edi; BufferCount
0x18001c3d9  lea     rcx, [rbp+340h+Buffer]; Buffer
0x18001c3e0  mov     r9, rsi
0x18001c3e3  call    cs:__imp_sprintf_s
0x18001c3e9  test    eax, eax
0x18001c3eb  js      loc_18001C5F2
0x18001c3f1  lea     ebx, [rdi+1Ch]
0x18001c3f4  xor     edx, edx; Val
0x18001c3f6  mov     r8d, ebx; Size
0x18001c3f9  lea     rcx, [rsp+440h+FindFileData]; void *
0x18001c3fe  call    memset_0
0x18001c403  lea     rdx, [rsp+440h+FindFileData]; lpFindFileData
0x18001c408  lea     rcx, [rbp+340h+Buffer]; lpFileName
0x18001c40f  call    cs:__imp_FindFirstFileA
0x18001c415  mov     r8d, ebx; Size
0x18001c418  lea     rcx, [rbp+340h+var_2C0]; void *
0x18001c41f  xor     edx, edx; Val
0x18001c421  mov     r12, rax
0x18001c424  call    memset_0
0x18001c429  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x18001c42d  jz      loc_18001C5C3
0x18001c433  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001c437  inc     rcx
0x18001c43a  cmp     byte ptr [rsi+rcx], 0
0x18001c43e  jnz     short loc_18001C437
0x18001c440  inc     ecx
0x18001c442  cmp     ecx, edi
0x18001c444  jnb     loc_18001C5F2
0x18001c44a  sub     edi, ecx
0x18001c44c  mov     eax, ecx
0x18001c44e  lea     r15, [rbp+340h+Buffer]
0x18001c455  add     r15, rax
0x18001c458  movsx   ecx, [rsp+440h+FindFileData.cFileName+3]; C
0x18001c45d  lea     r14, [rsp+440h+FindFileData.cFileName+3]
0x18001c462  xor     ebx, ebx
0x18001c464  call    cs:__imp_isdigit
0x18001c46a  test    eax, eax
0x18001c46c  jz      loc_18001C59A
0x18001c472  movsx   eax, byte ptr [r14]
0x18001c476  lea     ecx, [rbx-6]
0x18001c479  lea     ecx, [rbx+rcx*4]
0x18001c47c  inc     r14
0x18001c47f  lea     ebx, [rax+rcx*2]
0x18001c482  movsx   ecx, byte ptr [r14]; C
0x18001c486  call    cs:__imp_isdigit
0x18001c48c  test    eax, eax
0x18001c48e  jnz     short loc_18001C472
0x18001c490  test    ebx, ebx
0x18001c492  jz      loc_18001C59A
0x18001c498  mov     r8d, ebx; dwProcessId
0x18001c49b  xor     edx, edx; bInheritHandle
0x18001c49d  mov     ecx, 100000h; dwDesiredAccess
0x18001c4a2  call    cs:__imp_OpenProcess
0x18001c4a8  test    rax, rax
0x18001c4ab  jz      short loc_18001C4BB
0x18001c4ad  mov     rcx, rax; hObject
0x18001c4b0  call    cs:__imp_CloseHandle
0x18001c4b6  jmp     loc_18001C59A
0x18001c4bb  call    cs:__imp_GetLastError
0x18001c4c1  cmp     eax, 57h ; 'W'
0x18001c4c4  jnz     loc_18001C59A
0x18001c4ca  mov     edx, edi; SizeInBytes
0x18001c4cc  lea     r8, [rsp+440h+FindFileData.cFileName]; Source
0x18001c4d1  mov     rcx, r15; Destination
0x18001c4d4  call    cs:__imp_strcpy_s
0x18001c4da  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001c4de  inc     rcx
0x18001c4e1  cmp     byte ptr [r15+rcx], 0
0x18001c4e6  jnz     short loc_18001C4DE
0x18001c4e8  mov     r14d, ecx
0x18001c4eb  lea     r8, aAspTmp; "ASP*.TMP"
0x18001c4f2  mov     eax, edi
0x18001c4f4  sub     eax, ecx
0x18001c4f6  dec     eax
0x18001c4f8  lea     r9, [r14+1]
0x18001c4fc  mov     byte ptr [r14+r15], 5Ch ; '\'
0x18001c501  lea     rcx, [r9+r15]; Destination
0x18001c505  mov     [rsp+440h+SizeInBytes], rax
0x18001c50a  mov     edx, eax; SizeInBytes
0x18001c50c  call    cs:__imp_strcpy_s
0x18001c512  lea     rdx, [rbp+340h+var_2C0]; lpFindFileData
0x18001c519  lea     rcx, [rbp+340h+Buffer]; lpFileName
0x18001c520  call    cs:__imp_FindFirstFileA
0x18001c526  mov     rbx, rax
0x18001c529  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001c52d  jz      short loc_18001C57F
0x18001c52f  mov     rsi, [rsp+440h+SizeInBytes]
0x18001c534  lea     r13, [r15+1]
0x18001c538  lea     r8, [rbp+340h+var_2C0.cFileName]; Source
0x18001c53f  mov     rdx, rsi; SizeInBytes
0x18001c542  lea     rcx, [r14+r13]; Destination
0x18001c546  call    cs:__imp_strcpy_s
0x18001c54c  lea     rcx, [rbp+340h+Buffer]; lpFileName
0x18001c553  call    cs:__imp_DeleteFileA
0x18001c559  cmp     cs:?g_fShutDownInProgress@@3HA, 0; int g_fShutDownInProgress
0x18001c560  jnz     short loc_18001C576
0x18001c562  lea     rdx, [rbp+340h+var_2C0]; lpFindFileData
0x18001c569  mov     rcx, rbx; hFindFile
0x18001c56c  call    cs:__imp_FindNextFileA
0x18001c572  test    eax, eax
0x18001c574  jnz     short loc_18001C538
0x18001c576  mov     rcx, rbx; hFindFile
0x18001c579  call    cs:__imp_FindClose
0x18001c57f  lea     rcx, [rbp+340h+Buffer]; lpPathName
0x18001c586  mov     byte ptr [r14+r15], 0
0x18001c58b  call    cs:__imp_RemoveDirectoryA
0x18001c591  cmp     cs:?g_fShutDownInProgress@@3HA, 0; int g_fShutDownInProgress
0x18001c598  jnz     short loc_18001C5B0
0x18001c59a  lea     rdx, [rsp+440h+FindFileData]; lpFindFileData
0x18001c59f  mov     rcx, r12; hFindFile
0x18001c5a2  call    cs:__imp_FindNextFileA
0x18001c5a8  test    eax, eax
0x18001c5aa  jnz     loc_18001C458
0x18001c5b0  mov     rcx, r12; hFindFile
0x18001c5b3  call    cs:__imp_FindClose
0x18001c5b9  mov     rsi, [rsp+440h+var_410]
0x18001c5be  mov     r13d, [rsp+440h+var_41C]
0x18001c5c3  test    r13d, r13d
0x18001c5c6  jz      short loc_18001C5D7
0x18001c5c8  cmp     [rsp+440h+Wow64Process], 0
0x18001c5cd  jz      short loc_18001C5D7
0x18001c5cf  mov     cl, 1; Wow64FsEnableRedirection
0x18001c5d1  call    cs:__imp_Wow64EnableWow64FsRedirection
0x18001c5d7  test    rsi, rsi
0x18001c5da  jz      short loc_18001C5EE
0x18001c5dc  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18001c5e3  mov     r8, rsi; lpMem
0x18001c5e6  xor     edx, edx; dwFlags
0x18001c5e8  call    cs:__imp_HeapFree
0x18001c5ee  xor     eax, eax
0x18001c5f0  jmp     short loc_18001C5F7
0x18001c5f2  mov     eax, 7Ah ; 'z'
0x18001c5f7  mov     rcx, [rbp+340h+var_50]
0x18001c5fe  xor     rcx, rsp; StackCookie
0x18001c601  call    __security_check_cookie
0x18001c606  add     rsp, 408h
0x18001c60d  pop     r15
0x18001c60f  pop     r14
0x18001c611  pop     r13
0x18001c613  pop     r12
0x18001c615  pop     rdi
0x18001c616  pop     rsi
0x18001c617  pop     rbx
0x18001c618  pop     rbp
0x18001c619  retn
```
