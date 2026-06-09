# RemoveChromeFontCache(ushort const *,ushort const *,ushort const *)

- ea: `0x18003483c`
- end: `0x180034bdf`
- name: `?RemoveChromeFontCache@@YAKPEBG00@Z`
- size: `931`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180034610`

## callees

- `0x180001cf0`
- `0x180002874`
- `0x1800028e0`
- `0x18003483c`
- `0x1800543c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18003497a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18003497a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18003495a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18003495a`
- `KERNEL32!LocalAlloc` at `0x1800348b0`
- `KERNEL32!LocalAlloc` at `0x1800348da`
- `KERNEL32!LocalAlloc` at `0x1800348b0`
- `KERNEL32!LocalAlloc` at `0x1800348da`
- `KERNEL32!DeleteFileW` at `0x180034aeb`
- `KERNEL32!DeleteFileW` at `0x180034aeb`
- `KERNEL32!FindClose` at `0x180034b86`
- `KERNEL32!FindClose` at `0x180034b86`
- `KERNEL32!FindNextFileW` at `0x180034b45`
- `KERNEL32!FindNextFileW` at `0x180034b45`
- `KERNEL32!FindFirstFileW` at `0x180034992`
- `KERNEL32!FindFirstFileW` at `0x180034992`
- `KERNEL32!CreateFileW` at `0x180034a8a`
- `KERNEL32!CreateFileW` at `0x180034ac4`
- `KERNEL32!CreateFileW` at `0x180034a8a`
- `KERNEL32!CreateFileW` at `0x180034ac4`
- `KERNEL32!LocalFree` at `0x180034b69`
- `KERNEL32!LocalFree` at `0x180034b77`
- `KERNEL32!LocalFree` at `0x180034b69`
- `KERNEL32!LocalFree` at `0x180034b77`
- `KERNEL32!CloseHandle` at `0x180034a9d`
- `KERNEL32!CloseHandle` at `0x180034ad3`
- `KERNEL32!CloseHandle` at `0x180034a9d`
- `KERNEL32!CloseHandle` at `0x180034ad3`
- `KERNEL32!GetLastError` at `0x180034917`
- `KERNEL32!GetLastError` at `0x1800349a1`
- `KERNEL32!GetLastError` at `0x180034a1e`
- `KERNEL32!GetLastError` at `0x180034af5`
- `KERNEL32!GetLastError` at `0x180034917`
- `KERNEL32!GetLastError` at `0x1800349a1`
- `KERNEL32!GetLastError` at `0x180034a1e`
- `KERNEL32!GetLastError` at `0x180034af5`

## string_xrefs

- `0x180034937`: `RemoveChromeFontCache`
- `0x1800349c4`: `RemoveChromeFontCache`
- `0x180034a35`: `RemoveChromeFontCache`
- `0x180034a45`: `RemoveChromeFontCache`
- `0x180034ba1`: `RemoveChromeFontCache`
- `0x180034a2e`: `Failed to get cachefile path %d\n`
- `0x180034ad9`: `Successfully removed file via CreateFile [%ws]\n`
- `0x180034aff`: `Failed to delete file [%ws] with %d\n`
- `0x180034b20`: `Successfully removed file [%ws]\n`
- `0x180034b90`: `RemoveChromeCacheFile failed with %d\n`

## pseudocode

```c
__int64 __fastcall RemoveChromeFontCache(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rdx
  __int64 v7; // rax
  size_t v8; // rbx
  wchar_t *v9; // rbp
  __int64 v10; // rdx
  size_t v11; // r12
  WCHAR *v12; // rdi
  __int64 FirstFileW; // rsi
  unsigned int v14; // ebx
  DWORD LastError; // eax
  HANDLE FileW; // rax
  HANDLE v17; // rax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-2B8h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-2B8h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-2B0h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-298h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = -1;
  do
    ++v7;
  while ( a3[v7] );
  v8 = v7 + v6 + 16;
  v9 = (wchar_t *)LocalAlloc(0x40u, 2 * v8);
  v10 = -1;
  do
    ++v10;
  while ( a1[v10] );
  v11 = v8 + v10 + 523;
  v12 = (WCHAR *)LocalAlloc(0x40u, 2 * v11);
  if ( !v12 || !v9 )
  {
    FirstFileW = -1;
    v14 = 8;
    if ( !v9 )
      goto LABEL_30;
    goto LABEL_29;
  }
  FirstFileW = -1;
  if ( swprintf_s(v9, v8, L"%s\\%s\\appdata\\local", a2, a3) != -1 )
  {
    v14 = _o_wcscpy_s(v12, v11, v9);
    if ( v14 )
      goto LABEL_29;
    v14 = _o_wcscat_s(v12, v11, L"\\*");
    if ( v14 )
      goto LABEL_29;
    FirstFileW = (__int64)FindFirstFileW(v12, &FindFileData);
    if ( FirstFileW == -1 )
    {
      LastError = GetLastError();
      v14 = LastError;
      if ( LastError - 2 > 1 )
      {
        AslLogCallPrintf(1, "RemoveChromeFontCache", 97, "Failed when calling FindFirstFile with %d\n", LastError);
        goto LABEL_29;
      }
    }
    else
    {
      do
      {
        if ( (FindFileData.dwFileAttributes & 0x10) != 0 && FindFileData.cFileName[0] != 46 )
        {
          if ( swprintf_s(v12, v11, L"%s\\%s\\%s", v9, FindFileData.cFileName, a1) == -1 )
          {
            dwCreationDispositiona[0] = GetLastError();
            AslLogCallPrintf(
              1,
              "RemoveChromeFontCache",
              111,
              "Failed to get cachefile path %d\n",
              *(_QWORD *)dwCreationDispositiona);
          }
          else
          {
            AslLogCallPrintf(3, "RemoveChromeFontCache", 114, "checking file %ws\n", v12);
            FileW = CreateFileW(v12, 0x80000000, 1u, 0, 3u, 0x80u, 0);
            if ( FileW != (HANDLE)-1LL )
            {
              CloseHandle(FileW);
              v17 = CreateFileW(v12, 0x10000u, 4u, 0, 3u, 0x4000000u, 0);
              if ( v17 == (HANDLE)-1LL )
              {
                if ( DeleteFileW(v12) )
                {
                  AslLogCallPrintf(3, "RemoveChromeFontCache", 146, "Successfully removed file [%ws]\n", v12);
                }
                else
                {
                  dwFlagsAndAttributes[0] = GetLastError();
                  AslLogCallPrintf(
                    1,
                    "RemoveChromeFontCache",
                    142,
                    "Failed to delete file [%ws] with %d\n",
                    v12,
                    *(_QWORD *)dwFlagsAndAttributes);
                }
              }
              else
              {
                CloseHandle(v17);
                AslLogCallPrintf(
                  3,
                  "RemoveChromeFontCache",
                  136,
                  "Successfully removed file via CreateFile [%ws]\n",
                  v12);
              }
            }
          }
        }
      }
      while ( FindNextFileW((HANDLE)FirstFileW, &FindFileData) );
    }
    v14 = 0;
    goto LABEL_29;
  }
  dwCreationDisposition[0] = GetLastError();
  v14 = dwCreationDisposition[0];
  AslLogCallPrintf(
    1,
    "RemoveChromeFontCache",
    69,
    "Failed to get app root %d [%ws] [%ws] [%ws]\n",
    *(_QWORD *)dwCreationDisposition,
    a2,
    a3,
    v12);
LABEL_29:
  LocalFree(v9);
LABEL_30:
  if ( v12 )
    LocalFree(v12);
  if ( FirstFileW != -1 )
    FindClose((HANDLE)FirstFileW);
  if ( v14 )
    AslLogCallPrintf(1, "RemoveChromeFontCache", 170, "RemoveChromeCacheFile failed with %d\n", v14);
  return v14;
}

```

## disassembly

```asm
0x18003483c  mov     [rsp+arg_18], rbx
0x180034841  push    rbp
0x180034842  push    rsi
0x180034843  push    rdi
0x180034844  push    r12
0x180034846  push    r13
0x180034848  push    r14
0x18003484a  push    r15
0x18003484c  sub     rsp, 2A0h
0x180034853  mov     rax, cs:__security_cookie
0x18003485a  xor     rax, rsp
0x18003485d  mov     [rsp+2D8h+var_48], rax
0x180034865  mov     r15, r8
0x180034868  mov     r14, rdx
0x18003486b  mov     r13, rcx
0x18003486e  xor     edx, edx; Val
0x180034870  mov     r8d, 250h; Size
0x180034876  lea     rcx, [rsp+2D8h+FindFileData]; void *
0x18003487b  call    memset_0
0x180034880  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180034884  mov     rdx, rdi
0x180034887  xor     esi, esi
0x180034889  inc     rdx
0x18003488c  cmp     [r14+rdx*2], si
0x180034891  jnz     short loc_180034889
0x180034893  mov     rax, rdi
0x180034896  inc     rax
0x180034899  cmp     [r15+rax*2], si
0x18003489e  jnz     short loc_180034896
0x1800348a0  lea     rbx, [rdx+10h]
0x1800348a4  mov     ecx, 40h ; '@'; uFlags
0x1800348a9  add     rbx, rax
0x1800348ac  lea     rdx, [rbx+rbx]; uBytes
0x1800348b0  call    cs:__imp_LocalAlloc
0x1800348b6  mov     rbp, rax
0x1800348b9  mov     rdx, rdi
0x1800348bc  inc     rdx
0x1800348bf  cmp     [r13+rdx*2+0], si
0x1800348c5  jnz     short loc_1800348BC
0x1800348c7  lea     r12, [rdx+20Bh]
0x1800348ce  mov     ecx, 40h ; '@'; uFlags
0x1800348d3  add     r12, rbx
0x1800348d6  lea     rdx, [r12+r12]; uBytes
0x1800348da  call    cs:__imp_LocalAlloc
0x1800348e0  mov     rdi, rax
0x1800348e3  test    rax, rax
0x1800348e6  jz      loc_180034B58
0x1800348ec  test    rbp, rbp
0x1800348ef  jz      loc_180034B58
0x1800348f5  mov     r9, r14
0x1800348f8  mov     qword ptr [rsp+2D8h+dwCreationDisposition], r15
0x1800348fd  lea     r8, aSSAppdataLocal; "%s\\%s\\appdata\\local"
0x180034904  mov     rdx, rbx; BufferCount
0x180034907  mov     rcx, rbp; Buffer
0x18003490a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003490e  call    swprintf_s
0x180034913  cmp     eax, esi
0x180034915  jnz     short loc_180034951
0x180034917  call    cs:__imp_GetLastError
0x18003491d  mov     [rsp+2D8h+var_2A0], rdi
0x180034922  lea     r9, aFailedToGetApp; "Failed to get app root %d [%ws] [%ws] ["...
0x180034929  mov     [rsp+2D8h+hTemplateFile], r15
0x18003492e  lea     r8d, [rsi+46h]
0x180034932  mov     qword ptr [rsp+2D8h+dwFlagsAndAttributes], r14
0x180034937  lea     rdx, aRemovechromefo; "RemoveChromeFontCache"
0x18003493e  lea     ecx, [rsi+2]
0x180034941  mov     [rsp+2D8h+dwCreationDisposition], eax
0x180034945  mov     ebx, eax
0x180034947  call    AslLogCallPrintf
0x18003494c  jmp     loc_180034B66
0x180034951  mov     r8, rbp
0x180034954  mov     rdx, r12
0x180034957  mov     rcx, rdi
0x18003495a  call    cs:__imp__o_wcscpy_s
0x180034960  xor     r14d, r14d
0x180034963  mov     ebx, eax
0x180034965  test    eax, eax
0x180034967  jnz     loc_180034B66
0x18003496d  lea     r8, asc_180075210; "\\*"
0x180034974  mov     rdx, r12
0x180034977  mov     rcx, rdi
0x18003497a  call    cs:__imp__o_wcscat_s
0x180034980  mov     ebx, eax
0x180034982  test    eax, eax
0x180034984  jnz     loc_180034B66
0x18003498a  lea     rdx, [rsp+2D8h+FindFileData]; lpFindFileData
0x18003498f  mov     rcx, rdi; lpFileName
0x180034992  call    cs:__imp_FindFirstFileW
0x180034998  mov     rsi, rax
0x18003499b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003499f  jnz     short loc_1800349D8
0x1800349a1  call    cs:__imp_GetLastError
0x1800349a7  mov     ebx, eax
0x1800349a9  lea     ecx, [rax-2]
0x1800349ac  cmp     ecx, 1
0x1800349af  jbe     loc_180034B53
0x1800349b5  lea     r9, aFailedWhenCall; "Failed when calling FindFirstFile with "...
0x1800349bc  mov     [rsp+2D8h+dwCreationDisposition], eax
0x1800349c0  lea     r8d, [r14+61h]
0x1800349c4  lea     rdx, aRemovechromefo; "RemoveChromeFontCache"
0x1800349cb  lea     ecx, [rsi+2]
0x1800349ce  call    AslLogCallPrintf
0x1800349d3  jmp     loc_180034B66
0x1800349d8  mov     r15d, 3
0x1800349de  test    byte ptr [rsp+2D8h+FindFileData.dwFileAttributes], 10h
0x1800349e3  jz      loc_180034B3D
0x1800349e9  cmp     [rsp+2D8h+FindFileData.cFileName], 2Eh ; '.'
0x1800349ef  jz      loc_180034B3D
0x1800349f5  lea     rax, [rsp+2D8h+FindFileData.cFileName]
0x1800349fa  mov     qword ptr [rsp+2D8h+dwFlagsAndAttributes], r13
0x1800349ff  mov     r9, rbp
0x180034a02  mov     qword ptr [rsp+2D8h+dwCreationDisposition], rax
0x180034a07  lea     r8, aSSS; "%s\\%s\\%s"
0x180034a0e  mov     rdx, r12; BufferCount
0x180034a11  mov     rcx, rdi; Buffer
0x180034a14  call    swprintf_s
0x180034a19  cmp     eax, 0FFFFFFFFh
0x180034a1c  jnz     short loc_180034A45
0x180034a1e  call    cs:__imp_GetLastError
0x180034a24  mov     r8d, 6Fh ; 'o'
0x180034a2a  mov     [rsp+2D8h+dwCreationDisposition], eax
0x180034a2e  lea     r9, aFailedToGetCac; "Failed to get cachefile path %d\n"
0x180034a35  lea     rdx, aRemovechromefo; "RemoveChromeFontCache"
0x180034a3c  lea     ecx, [r8-6Eh]
0x180034a40  jmp     loc_180034B38
0x180034a45  lea     rbx, aRemovechromefo; "RemoveChromeFontCache"
0x180034a4c  mov     qword ptr [rsp+2D8h+dwCreationDisposition], rdi
0x180034a51  mov     rdx, rbx
0x180034a54  lea     r9, aCheckingFileWs; "checking file %ws\n"
0x180034a5b  mov     r8d, 72h ; 'r'
0x180034a61  mov     ecx, r15d
0x180034a64  call    AslLogCallPrintf
0x180034a69  xor     r9d, r9d; lpSecurityAttributes
0x180034a6c  mov     [rsp+2D8h+hTemplateFile], r14; hTemplateFile
0x180034a71  mov     [rsp+2D8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180034a79  mov     edx, 80000000h; dwDesiredAccess
0x180034a7e  mov     rcx, rdi; lpFileName
0x180034a81  mov     [rsp+2D8h+dwCreationDisposition], r15d; dwCreationDisposition
0x180034a86  lea     r8d, [r9+1]; dwShareMode
0x180034a8a  call    cs:__imp_CreateFileW
0x180034a90  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180034a94  jz      loc_180034B3D
0x180034a9a  mov     rcx, rax; hObject
0x180034a9d  call    cs:__imp_CloseHandle
0x180034aa3  xor     r9d, r9d; lpSecurityAttributes
0x180034aa6  mov     [rsp+2D8h+hTemplateFile], r14; hTemplateFile
0x180034aab  mov     [rsp+2D8h+dwFlagsAndAttributes], 4000000h; dwFlagsAndAttributes
0x180034ab3  mov     edx, 10000h; dwDesiredAccess
0x180034ab8  mov     rcx, rdi; lpFileName
0x180034abb  mov     [rsp+2D8h+dwCreationDisposition], r15d; dwCreationDisposition
0x180034ac0  lea     r8d, [r9+4]; dwShareMode
0x180034ac4  call    cs:__imp_CreateFileW
0x180034aca  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180034ace  jz      short loc_180034AE8
0x180034ad0  mov     rcx, rax; hObject
0x180034ad3  call    cs:__imp_CloseHandle
0x180034ad9  lea     r9, aSuccessfullyRe_0; "Successfully removed file via CreateFil"...
0x180034ae0  mov     r8d, 88h
0x180034ae6  jmp     short loc_180034B2D
0x180034ae8  mov     rcx, rdi; lpFileName
0x180034aeb  call    cs:__imp_DeleteFileW
0x180034af1  test    eax, eax
0x180034af3  jnz     short loc_180034B20
0x180034af5  call    cs:__imp_GetLastError
0x180034afb  mov     [rsp+2D8h+dwFlagsAndAttributes], eax
0x180034aff  lea     r9, aFailedToDelete_1; "Failed to delete file [%ws] with %d\n"
0x180034b06  mov     r8d, 8Eh
0x180034b0c  mov     qword ptr [rsp+2D8h+dwCreationDisposition], rdi
0x180034b11  mov     rdx, rbx
0x180034b14  mov     ecx, 1
0x180034b19  call    AslLogCallPrintf
0x180034b1e  jmp     short loc_180034B3D
0x180034b20  lea     r9, aSuccessfullyRe; "Successfully removed file [%ws]\n"
0x180034b27  mov     r8d, 92h
0x180034b2d  mov     ecx, r15d
0x180034b30  mov     qword ptr [rsp+2D8h+dwCreationDisposition], rdi
0x180034b35  mov     rdx, rbx
0x180034b38  call    AslLogCallPrintf
0x180034b3d  lea     rdx, [rsp+2D8h+FindFileData]; lpFindFileData
0x180034b42  mov     rcx, rsi; hFindFile
0x180034b45  call    cs:__imp_FindNextFileW
0x180034b4b  test    eax, eax
0x180034b4d  jnz     loc_1800349DE
0x180034b53  mov     ebx, r14d
0x180034b56  jmp     short loc_180034B66
0x180034b58  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180034b5c  mov     ebx, 8
0x180034b61  test    rbp, rbp
0x180034b64  jz      short loc_180034B6F
0x180034b66  mov     rcx, rbp; hMem
0x180034b69  call    cs:__imp_LocalFree
0x180034b6f  test    rdi, rdi
0x180034b72  jz      short loc_180034B7D
0x180034b74  mov     rcx, rdi; hMem
0x180034b77  call    cs:__imp_LocalFree
0x180034b7d  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180034b81  jz      short loc_180034B8C
0x180034b83  mov     rcx, rsi; hFindFile
0x180034b86  call    cs:__imp_FindClose
0x180034b8c  test    ebx, ebx
0x180034b8e  jz      short loc_180034BB2
0x180034b90  lea     r9, aRemovechromeca; "RemoveChromeCacheFile failed with %d\n"
0x180034b97  mov     [rsp+2D8h+dwCreationDisposition], ebx
0x180034b9b  mov     r8d, 0AAh
0x180034ba1  lea     rdx, aRemovechromefo; "RemoveChromeFontCache"
0x180034ba8  mov     ecx, 1
0x180034bad  call    AslLogCallPrintf
0x180034bb2  mov     eax, ebx
0x180034bb4  mov     rcx, [rsp+2D8h+var_48]
0x180034bbc  xor     rcx, rsp; StackCookie
0x180034bbf  call    __security_check_cookie
0x180034bc4  mov     rbx, [rsp+2D8h+arg_18]
0x180034bcc  add     rsp, 2A0h
0x180034bd3  pop     r15
0x180034bd5  pop     r14
0x180034bd7  pop     r13
0x180034bd9  pop     r12
0x180034bdb  pop     rdi
0x180034bdc  pop     rsi
0x180034bdd  pop     rbp
0x180034bde  retn
```
