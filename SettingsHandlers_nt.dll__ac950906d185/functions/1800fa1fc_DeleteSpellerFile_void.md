# DeleteSpellerFile(void)

- ea: `0x1800fa1fc`
- end: `0x1800fa459`
- name: `?DeleteSpellerFile@@YAJXZ`
- size: `605`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800fab20`

## callees

- `0x18000c840`
- `0x18000d44c`
- `0x18001a64c`
- `0x1800fa1fc`
- `0x1800fa808`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x1800fa387`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x1800fa387`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fa3ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fa3ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fa28b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fa41e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fa28b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fa41e`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1800fa2e4`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1800fa2e4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800fa42d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800fa42d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800fa405`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800fa405`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800fa3c1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800fa3c1`
- `SHELL32!SHGetKnownFolderPath` at `0x1800fa274`
- `SHELL32!SHGetKnownFolderPath` at `0x1800fa274`

## pseudocode

```c
__int64 DeleteSpellerFile(void)
{
  HRESULT v0; // ebx
  HANDLE FirstFile; // rdi
  int v2; // edx
  int v3; // edx
  unsigned __int16 v4; // bx
  char *FileW; // rax
  void *v6; // rsi
  PWSTR ppszPath; // [rsp+40h] [rbp-C0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR FileName[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR v11[264]; // [rsp+4B0h] [rbp+3B0h] BYREF

  ppszPath = 0;
  memset_0(v11, 0, 0x208u);
  memset_0(FileName, 0, 0x208u);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v0 = SHGetKnownFolderPath(&FOLDERID_RoamingAppData, 0, 0, &ppszPath);
  if ( v0 < 0 || (v0 = StringCchPrintfW(FileName, 0x104u, L"%s\\Microsoft\\Spelling\\*", ppszPath), v0 < 0) )
  {
    CoTaskMemFree(ppszPath);
  }
  else
  {
    FirstFile = FindFirstFileExW(FileName, FindExInfoStandard, &FindFileData, FindExSearchLimitToDirectories, 0, 0);
    if ( FirstFile != (HANDLE)-1LL )
    {
      do
      {
        if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
        {
          v2 = FindFileData.cFileName[0] - 46;
          if ( FindFileData.cFileName[0] == 46 )
            v2 = FindFileData.cFileName[1];
          if ( v2 )
          {
            v3 = FindFileData.cFileName[0] - 46;
            if ( FindFileData.cFileName[0] == 46 )
            {
              v3 = FindFileData.cFileName[1] - 46;
              if ( FindFileData.cFileName[1] == 46 )
                v3 = FindFileData.cFileName[2];
            }
            if ( v3 )
            {
              v0 = StringCchPrintfW(
                     v11,
                     0x104u,
                     L"%s\\Microsoft\\Spelling\\%s\\default.dic",
                     ppszPath,
                     FindFileData.cFileName);
              if ( v0 >= 0 )
              {
                v4 = LocaleNameToLCID(FindFileData.cFileName, 0);
                FileW = (char *)CreateFileW(v11, 0x40000000u, 1u, 0, 2u, 0x80u, 0);
                v6 = FileW;
                if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
                {
                  v0 = -2147467259;
                }
                else
                {
                  v0 = WriteHeaderToFile(FileW, v4);
                  CloseHandle(v6);
                }
              }
            }
          }
        }
      }
      while ( FindNextFileW(FirstFile, &FindFileData) );
    }
    CoTaskMemFree(ppszPath);
    FindClose(FirstFile);
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x1800fa1fc  push    rbp
0x1800fa1fe  push    rbx
0x1800fa1ff  push    rsi
0x1800fa200  push    rdi
0x1800fa201  push    r15
0x1800fa203  lea     rbp, [rsp-5D0h]
0x1800fa20b  sub     rsp, 6D0h
0x1800fa212  mov     rax, cs:__security_cookie
0x1800fa219  xor     rax, rsp
0x1800fa21c  mov     [rbp+5F0h+var_30], rax
0x1800fa223  mov     ebx, 208h
0x1800fa228  mov     [rsp+6F0h+ppszPath], 0
0x1800fa231  mov     r8d, ebx; Size
0x1800fa234  lea     rcx, [rbp+5F0h+var_240]; void *
0x1800fa23b  xor     edx, edx; Val
0x1800fa23d  call    memset_0
0x1800fa242  mov     r8d, ebx; Size
0x1800fa245  lea     rcx, [rbp+5F0h+FileName]; void *
0x1800fa24c  xor     edx, edx; Val
0x1800fa24e  call    memset_0
0x1800fa253  xor     edx, edx; Val
0x1800fa255  lea     r8d, [rbx+48h]; Size
0x1800fa259  lea     rcx, [rsp+6F0h+FindFileData]; void *
0x1800fa25e  call    memset_0
0x1800fa263  lea     r9, [rsp+6F0h+ppszPath]; ppszPath
0x1800fa268  xor     r8d, r8d; hToken
0x1800fa26b  xor     edx, edx; dwFlags
0x1800fa26d  lea     rcx, FOLDERID_RoamingAppData; rfid
0x1800fa274  call    cs:__imp_SHGetKnownFolderPath
0x1800fa27b  nop     dword ptr [rax+rax+00h]
0x1800fa280  mov     ebx, eax
0x1800fa282  test    eax, eax
0x1800fa284  jns     short loc_1800FA29C
0x1800fa286  mov     rcx, [rsp+6F0h+ppszPath]; pv
0x1800fa28b  call    cs:__imp_CoTaskMemFree
0x1800fa292  nop     dword ptr [rax+rax+00h]
0x1800fa297  jmp     loc_1800FA439
0x1800fa29c  mov     r9, [rsp+6F0h+ppszPath]
0x1800fa2a1  lea     r8, aSMicrosoftSpel_0; "%s\\Microsoft\\Spelling\\*"
0x1800fa2a8  mov     edx, 104h; unsigned __int64
0x1800fa2ad  lea     rcx, [rbp+5F0h+FileName]; unsigned __int16 *
0x1800fa2b4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800fa2b9  mov     ebx, eax
0x1800fa2bb  test    eax, eax
0x1800fa2bd  js      short loc_1800FA286
0x1800fa2bf  mov     [rsp+6F0h+dwAdditionalFlags], 0; dwAdditionalFlags
0x1800fa2c7  lea     r8, [rsp+6F0h+FindFileData]; lpFindFileData
0x1800fa2cc  mov     r9d, 1; fSearchOp
0x1800fa2d2  mov     [rsp+6F0h+lpSearchFilter], 0; lpSearchFilter
0x1800fa2db  xor     edx, edx; fInfoLevelId
0x1800fa2dd  lea     rcx, [rbp+5F0h+FileName]; lpFileName
0x1800fa2e4  call    cs:__imp_FindFirstFileExW
0x1800fa2eb  nop     dword ptr [rax+rax+00h]
0x1800fa2f0  mov     rdi, rax
0x1800fa2f3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800fa2f7  jz      loc_1800FA419
0x1800fa2fd  mov     r15d, 2Eh ; '.'
0x1800fa303  test    [rsp+6F0h+FindFileData], 10h
0x1800fa308  jz      loc_1800FA3FD
0x1800fa30e  movzx   edx, [rsp+6F0h+Name]
0x1800fa313  sub     edx, r15d
0x1800fa316  jnz     short loc_1800FA324
0x1800fa318  movzx   edx, [rsp+6F0h+var_672]
0x1800fa31d  xor     eax, eax
0x1800fa31f  movzx   ecx, ax
0x1800fa322  sub     edx, ecx
0x1800fa324  test    edx, edx
0x1800fa326  jz      loc_1800FA3FD
0x1800fa32c  movzx   edx, [rsp+6F0h+Name]
0x1800fa331  sub     edx, r15d
0x1800fa334  jnz     short loc_1800FA34B
0x1800fa336  movzx   edx, [rsp+6F0h+var_672]
0x1800fa33b  sub     edx, r15d
0x1800fa33e  jnz     short loc_1800FA34B
0x1800fa340  movzx   edx, [rbp+5F0h+var_670]
0x1800fa344  xor     eax, eax
0x1800fa346  movzx   ecx, ax
0x1800fa349  sub     edx, ecx
0x1800fa34b  test    edx, edx
0x1800fa34d  jz      loc_1800FA3FD
0x1800fa353  mov     r9, [rsp+6F0h+ppszPath]
0x1800fa358  lea     rax, [rsp+6F0h+Name]
0x1800fa35d  lea     r8, aSMicrosoftSpel; "%s\\Microsoft\\Spelling\\%s\\default.di"...
0x1800fa364  mov     [rsp+6F0h+lpSearchFilter], rax
0x1800fa369  mov     edx, 104h; unsigned __int64
0x1800fa36e  lea     rcx, [rbp+5F0h+var_240]; unsigned __int16 *
0x1800fa375  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800fa37a  mov     ebx, eax
0x1800fa37c  test    eax, eax
0x1800fa37e  js      short loc_1800FA3FD
0x1800fa380  xor     edx, edx; dwFlags
0x1800fa382  lea     rcx, [rsp+6F0h+Name]; lpName
0x1800fa387  call    cs:__imp_LocaleNameToLCID
0x1800fa38e  nop     dword ptr [rax+rax+00h]
0x1800fa393  xor     r9d, r9d; lpSecurityAttributes
0x1800fa396  mov     [rsp+6F0h+hTemplateFile], 0; hTemplateFile
0x1800fa39f  mov     [rsp+6F0h+dwAdditionalFlags], 80h; dwFlagsAndAttributes
0x1800fa3a7  lea     rcx, [rbp+5F0h+var_240]; lpFileName
0x1800fa3ae  mov     edx, 40000000h; dwDesiredAccess
0x1800fa3b3  mov     dword ptr [rsp+6F0h+lpSearchFilter], 2; dwCreationDisposition
0x1800fa3bb  mov     ebx, eax
0x1800fa3bd  lea     r8d, [r9+1]; dwShareMode
0x1800fa3c1  call    cs:__imp_CreateFileW
0x1800fa3c8  nop     dword ptr [rax+rax+00h]
0x1800fa3cd  mov     rsi, rax
0x1800fa3d0  lea     rcx, [rax-1]
0x1800fa3d4  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800fa3d8  ja      short loc_1800FA3F8
0x1800fa3da  movzx   edx, bx; unsigned __int16
0x1800fa3dd  mov     rcx, rax; hFile
0x1800fa3e0  call    ?WriteHeaderToFile@@YAJQEAXG@Z; WriteHeaderToFile(void * const,ushort)
0x1800fa3e5  mov     rcx, rsi; hObject
0x1800fa3e8  mov     ebx, eax
0x1800fa3ea  call    cs:__imp_CloseHandle
0x1800fa3f1  nop     dword ptr [rax+rax+00h]
0x1800fa3f6  jmp     short loc_1800FA3FD
0x1800fa3f8  mov     ebx, 80004005h
0x1800fa3fd  lea     rdx, [rsp+6F0h+FindFileData]; lpFindFileData
0x1800fa402  mov     rcx, rdi; hFindFile
0x1800fa405  call    cs:__imp_FindNextFileW
0x1800fa40c  nop     dword ptr [rax+rax+00h]
0x1800fa411  test    eax, eax
0x1800fa413  jnz     loc_1800FA303
0x1800fa419  mov     rcx, [rsp+6F0h+ppszPath]; pv
0x1800fa41e  call    cs:__imp_CoTaskMemFree
0x1800fa425  nop     dword ptr [rax+rax+00h]
0x1800fa42a  mov     rcx, rdi; hFindFile
0x1800fa42d  call    cs:__imp_FindClose
0x1800fa434  nop     dword ptr [rax+rax+00h]
0x1800fa439  mov     eax, ebx
0x1800fa43b  mov     rcx, [rbp+5F0h+var_30]
0x1800fa442  xor     rcx, rsp; StackCookie
0x1800fa445  call    __security_check_cookie
0x1800fa44a  add     rsp, 6D0h
0x1800fa451  pop     r15
0x1800fa453  pop     rdi
0x1800fa454  pop     rsi
0x1800fa455  pop     rbx
0x1800fa456  pop     rbp
0x1800fa457  retn
```
