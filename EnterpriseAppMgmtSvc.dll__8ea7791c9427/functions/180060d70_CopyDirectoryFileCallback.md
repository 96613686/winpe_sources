# CopyDirectoryFileCallback

- ea: `0x180060d70`
- end: `0x180060f0e`
- name: `CopyDirectoryFileCallback`
- size: `414`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callees

- `0x18005e658`
- `0x18005e748`
- `0x18005eea8`
- `0x180060d70`
- `0x180061f64`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180060e57`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180060e57`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180060e6f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180060e6f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180060e91`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180060e91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180060ee4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180060ee4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180060ef2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180060ef2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060e37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060e99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060e37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060e99`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060efb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060efb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180060d8c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180060d8c`

## string_xrefs

- `0x180060e4e`: `user32.dll`
- `0x180060d99`: `CopyDirectoryFileCallback: The copy was canceled by the user.`
- `0x180060eac`: `CopyDirectoryFileCallback: Unable to %s file from [%s] to [%s]; GLE = 0x%x`

## pseudocode

```c
__int64 __fastcall CopyDirectoryFileCallback(__int64 a1, __int64 a2)
{
  void *v4; // rcx
  unsigned int v5; // edi
  DWORD v6; // ecx
  unsigned int (__fastcall *v7)(_QWORD, _QWORD); // rax
  __int64 v8; // rax
  void *v9; // rbp
  DWORD LastError; // r14d
  HMODULE Library; // rax
  HMODULE v12; // rsi
  FARPROC ProcAddress; // rax
  DWORD v14; // eax
  const wchar_t *v15; // r9
  HANDLE ProcessHeap; // rax
  DWORD v18; // [rsp+30h] [rbp-38h]

  v4 = *(void **)(a2 + 24);
  if ( v4 && WaitForSingleObject(v4, 0) != 258 )
  {
    LibLog(&g_WdsLibLog, 0x4000000, L"CopyDirectoryFileCallback: The copy was canceled by the user.");
    v5 = 0;
    v6 = 1223;
LABEL_20:
    SetLastError(v6);
    return v5;
  }
  v7 = *(unsigned int (__fastcall **)(_QWORD, _QWORD))(a2 + 32);
  if ( v7 && v7(*(_QWORD *)(a1 + 40), *(_QWORD *)(a2 + 40)) )
  {
    return 1;
  }
  else
  {
    v5 = 0;
    v8 = BuildPath(*(STRSAFE_PCNZWCH *)(a2 + 8), *(STRSAFE_PCNZWCH *)(a1 + 48));
    v9 = (void *)v8;
    if ( v8 )
    {
      v5 = 1;
      if ( (unsigned int)CopyFileWithAttributesEx2(
                           *(_QWORD *)(a1 + 40),
                           v8,
                           *(unsigned int *)(a2 + 20),
                           *(_QWORD *)(a2 + 56),
                           *(_QWORD *)(a2 + 64)) == 1
        && (!*(_DWORD *)(a2 + 16) || DeleteFileEx2(*(_QWORD *)(a1 + 40), 0)) )
      {
        LastError = GetLastError();
        if ( *(_QWORD *)(a2 + 48) )
        {
          Library = LoadLibraryExW(L"user32.dll", 0, 0);
          v12 = Library;
          if ( Library )
          {
            ProcAddress = GetProcAddress(Library, "SendMessageW");
            if ( ProcAddress )
              ((void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))ProcAddress)(*(_QWORD *)(a2 + 48), 1029, 0, 0);
            FreeLibrary(v12);
          }
        }
      }
      else
      {
        v14 = GetLastError();
        v15 = L"move";
        LastError = v14;
        v18 = v14;
        if ( *(_DWORD *)(a2 + 16) != 1 )
          v15 = L"copy";
        LibLog(
          &g_WdsLibLog,
          0x2000000,
          L"CopyDirectoryFileCallback: Unable to %s file from [%s] to [%s]; GLE = 0x%x",
          v15,
          *(_QWORD *)(a1 + 40),
          v9,
          v18);
        v5 = 0;
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v9);
      v6 = LastError;
      goto LABEL_20;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180060d70  push    rbx
0x180060d72  push    rbp
0x180060d73  push    rsi
0x180060d74  push    rdi
0x180060d75  push    r14
0x180060d77  sub     rsp, 40h
0x180060d7b  mov     rsi, rcx
0x180060d7e  mov     rbx, rdx
0x180060d81  mov     rcx, [rdx+18h]; hHandle
0x180060d85  test    rcx, rcx
0x180060d88  jz      short loc_180060DBD
0x180060d8a  xor     edx, edx; dwMilliseconds
0x180060d8c  call    cs:__imp_WaitForSingleObject
0x180060d92  cmp     eax, 102h
0x180060d97  jz      short loc_180060DBD
0x180060d99  lea     r8, aCopydirectoryf_0; "CopyDirectoryFileCallback: The copy was"...
0x180060da0  mov     edx, 4000000h
0x180060da5  lea     rcx, g_WdsLibLog
0x180060dac  call    LibLog
0x180060db1  xor     edi, edi
0x180060db3  mov     ecx, 4C7h
0x180060db8  jmp     loc_180060EFB
0x180060dbd  mov     rax, [rbx+20h]
0x180060dc1  test    rax, rax
0x180060dc4  jz      short loc_180060DE1
0x180060dc6  mov     rdx, [rbx+28h]
0x180060dca  mov     rcx, [rsi+28h]
0x180060dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060dd3  test    eax, eax
0x180060dd5  jz      short loc_180060DE1
0x180060dd7  mov     edi, 1
0x180060ddc  jmp     loc_180060F01
0x180060de1  mov     rdx, [rsi+30h]; STRSAFE_PCNZWCH
0x180060de5  xor     edi, edi
0x180060de7  mov     rcx, [rbx+8]; pszSrc
0x180060deb  call    BuildPath
0x180060df0  mov     rbp, rax
0x180060df3  test    rax, rax
0x180060df6  jz      loc_180060F01
0x180060dfc  mov     rcx, [rbx+40h]
0x180060e00  mov     rdx, rax
0x180060e03  mov     r9, [rbx+38h]
0x180060e07  mov     r8d, [rbx+14h]
0x180060e0b  mov     [rsp+68h+var_48], rcx
0x180060e10  mov     rcx, [rsi+28h]
0x180060e14  call    CopyFileWithAttributesEx2
0x180060e19  mov     edi, 1
0x180060e1e  cmp     eax, edi
0x180060e20  jnz     short loc_180060E99
0x180060e22  cmp     dword ptr [rbx+10h], 0
0x180060e26  jz      short loc_180060E37
0x180060e28  mov     rcx, [rsi+28h]
0x180060e2c  xor     edx, edx
0x180060e2e  call    DeleteFileEx2
0x180060e33  cmp     eax, edi
0x180060e35  jnz     short loc_180060E99
0x180060e37  call    cs:__imp_GetLastError
0x180060e3d  cmp     qword ptr [rbx+30h], 0
0x180060e42  mov     r14d, eax
0x180060e45  jz      loc_180060EE4
0x180060e4b  xor     r8d, r8d; dwFlags
0x180060e4e  lea     rcx, aUser32Dll; "user32.dll"
0x180060e55  xor     edx, edx; hFile
0x180060e57  call    cs:__imp_LoadLibraryExW
0x180060e5d  mov     rsi, rax
0x180060e60  test    rax, rax
0x180060e63  jz      short loc_180060EE4
0x180060e65  lea     rdx, aSendmessagew; "SendMessageW"
0x180060e6c  mov     rcx, rax; hModule
0x180060e6f  call    cs:__imp_GetProcAddress
0x180060e75  test    rax, rax
0x180060e78  jz      short loc_180060E8E
0x180060e7a  mov     rcx, [rbx+30h]
0x180060e7e  xor     r9d, r9d
0x180060e81  xor     r8d, r8d
0x180060e84  mov     edx, 405h
0x180060e89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060e8e  mov     rcx, rsi; hLibModule
0x180060e91  call    cs:__imp_FreeLibrary
0x180060e97  jmp     short loc_180060EE4
0x180060e99  call    cs:__imp_GetLastError
0x180060e9f  cmp     [rbx+10h], edi
0x180060ea2  lea     r9, aMove; "move"
0x180060ea9  mov     r14d, eax
0x180060eac  lea     r8, aCopydirectoryf; "CopyDirectoryFileCallback: Unable to %s"...
0x180060eb3  lea     rax, aCopy; "copy"
0x180060eba  mov     [rsp+68h+var_38], r14d
0x180060ebf  cmovnz  r9, rax
0x180060ec3  mov     [rsp+68h+var_40], rbp
0x180060ec8  mov     rax, [rsi+28h]
0x180060ecc  lea     rcx, g_WdsLibLog
0x180060ed3  mov     edx, 2000000h
0x180060ed8  mov     [rsp+68h+var_48], rax
0x180060edd  call    LibLog
0x180060ee2  xor     edi, edi
0x180060ee4  call    cs:__imp_GetProcessHeap
0x180060eea  mov     r8, rbp; lpMem
0x180060eed  xor     edx, edx; dwFlags
0x180060eef  mov     rcx, rax; hHeap
0x180060ef2  call    cs:__imp_HeapFree
0x180060ef8  mov     ecx, r14d; dwErrCode
0x180060efb  call    cs:__imp_SetLastError
0x180060f01  mov     eax, edi
0x180060f03  add     rsp, 40h
0x180060f07  pop     r14
0x180060f09  pop     rdi
0x180060f0a  pop     rsi
0x180060f0b  pop     rbp
0x180060f0c  pop     rbx
0x180060f0d  retn
```
