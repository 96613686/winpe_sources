# CopyDirectoryFileCallback

- ea: `0x180066080`
- end: `0x18006625d`
- name: `CopyDirectoryFileCallback`
- size: `477`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callees

- `0x180063410`
- `0x180063538`
- `0x180063df0`
- `0x180066080`
- `0x1800674d8`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180066177`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180066177`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180066199`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180066199`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800661c1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800661c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180066220`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180066220`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066234`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066234`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066151`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800661cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066151`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800661cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066243`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066243`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006609c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006609c`

## string_xrefs

- `0x18006616e`: `user32.dll`
- `0x1800660af`: `CopyDirectoryFileCallback: The copy was canceled by the user.`
- `0x1800661e8`: `CopyDirectoryFileCallback: Unable to %s file from [%s] to [%s]; GLE = 0x%x`

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
0x180066080  push    rbx
0x180066082  push    rbp
0x180066083  push    rsi
0x180066084  push    rdi
0x180066085  push    r14
0x180066087  sub     rsp, 40h
0x18006608b  mov     rsi, rcx
0x18006608e  mov     rbx, rdx
0x180066091  mov     rcx, [rdx+18h]; hHandle
0x180066095  test    rcx, rcx
0x180066098  jz      short loc_1800660D3
0x18006609a  xor     edx, edx; dwMilliseconds
0x18006609c  call    cs:__imp_WaitForSingleObject
0x1800660a3  nop     dword ptr [rax+rax+00h]
0x1800660a8  cmp     eax, 102h
0x1800660ad  jz      short loc_1800660D3
0x1800660af  lea     r8, aCopydirectoryf_0; "CopyDirectoryFileCallback: The copy was"...
0x1800660b6  mov     edx, 4000000h
0x1800660bb  lea     rcx, g_WdsLibLog
0x1800660c2  call    LibLog
0x1800660c7  xor     edi, edi
0x1800660c9  mov     ecx, 4C7h
0x1800660ce  jmp     loc_180066243
0x1800660d3  mov     rax, [rbx+20h]
0x1800660d7  test    rax, rax
0x1800660da  jz      short loc_1800660F7
0x1800660dc  mov     rdx, [rbx+28h]
0x1800660e0  mov     rcx, [rsi+28h]
0x1800660e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800660e9  test    eax, eax
0x1800660eb  jz      short loc_1800660F7
0x1800660ed  mov     edi, 1
0x1800660f2  jmp     loc_18006624F
0x1800660f7  mov     rdx, [rsi+30h]; STRSAFE_PCNZWCH
0x1800660fb  xor     edi, edi
0x1800660fd  mov     rcx, [rbx+8]; pszSrc
0x180066101  call    BuildPath
0x180066106  mov     rbp, rax
0x180066109  test    rax, rax
0x18006610c  jz      loc_18006624F
0x180066112  mov     rcx, [rbx+40h]
0x180066116  mov     rdx, rax
0x180066119  mov     r9, [rbx+38h]
0x18006611d  mov     r8d, [rbx+14h]
0x180066121  mov     [rsp+68h+var_48], rcx
0x180066126  mov     rcx, [rsi+28h]
0x18006612a  call    CopyFileWithAttributesEx2
0x18006612f  mov     edi, 1
0x180066134  cmp     eax, edi
0x180066136  jnz     loc_1800661CF
0x18006613c  cmp     dword ptr [rbx+10h], 0
0x180066140  jz      short loc_180066151
0x180066142  mov     rcx, [rsi+28h]
0x180066146  xor     edx, edx
0x180066148  call    DeleteFileEx2
0x18006614d  cmp     eax, edi
0x18006614f  jnz     short loc_1800661CF
0x180066151  call    cs:__imp_GetLastError
0x180066158  nop     dword ptr [rax+rax+00h]
0x18006615d  cmp     qword ptr [rbx+30h], 0
0x180066162  mov     r14d, eax
0x180066165  jz      loc_180066220
0x18006616b  xor     r8d, r8d; dwFlags
0x18006616e  lea     rcx, aUser32Dll; "user32.dll"
0x180066175  xor     edx, edx; hFile
0x180066177  call    cs:__imp_LoadLibraryExW
0x18006617e  nop     dword ptr [rax+rax+00h]
0x180066183  mov     rsi, rax
0x180066186  test    rax, rax
0x180066189  jz      loc_180066220
0x18006618f  lea     rdx, aSendmessagew; "SendMessageW"
0x180066196  mov     rcx, rax; hModule
0x180066199  call    cs:__imp_GetProcAddress
0x1800661a0  nop     dword ptr [rax+rax+00h]
0x1800661a5  test    rax, rax
0x1800661a8  jz      short loc_1800661BE
0x1800661aa  mov     rcx, [rbx+30h]
0x1800661ae  xor     r9d, r9d
0x1800661b1  xor     r8d, r8d
0x1800661b4  mov     edx, 405h
0x1800661b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800661be  mov     rcx, rsi; hLibModule
0x1800661c1  call    cs:__imp_FreeLibrary
0x1800661c8  nop     dword ptr [rax+rax+00h]
0x1800661cd  jmp     short loc_180066220
0x1800661cf  call    cs:__imp_GetLastError
0x1800661d6  nop     dword ptr [rax+rax+00h]
0x1800661db  cmp     [rbx+10h], edi
0x1800661de  lea     r9, aMove; "move"
0x1800661e5  mov     r14d, eax
0x1800661e8  lea     r8, aCopydirectoryf; "CopyDirectoryFileCallback: Unable to %s"...
0x1800661ef  lea     rax, aCopy; "copy"
0x1800661f6  mov     [rsp+68h+var_38], r14d
0x1800661fb  cmovnz  r9, rax
0x1800661ff  mov     [rsp+68h+var_40], rbp
0x180066204  mov     rax, [rsi+28h]
0x180066208  lea     rcx, g_WdsLibLog
0x18006620f  mov     edx, 2000000h
0x180066214  mov     [rsp+68h+var_48], rax
0x180066219  call    LibLog
0x18006621e  xor     edi, edi
0x180066220  call    cs:__imp_GetProcessHeap
0x180066227  nop     dword ptr [rax+rax+00h]
0x18006622c  mov     r8, rbp; lpMem
0x18006622f  xor     edx, edx; dwFlags
0x180066231  mov     rcx, rax; hHeap
0x180066234  call    cs:__imp_HeapFree
0x18006623b  nop     dword ptr [rax+rax+00h]
0x180066240  mov     ecx, r14d; dwErrCode
0x180066243  call    cs:__imp_SetLastError
0x18006624a  nop     dword ptr [rax+rax+00h]
0x18006624f  mov     eax, edi
0x180066251  add     rsp, 40h
0x180066255  pop     r14
0x180066257  pop     rdi
0x180066258  pop     rsi
0x180066259  pop     rbp
0x18006625a  pop     rbx
0x18006625b  retn
```
