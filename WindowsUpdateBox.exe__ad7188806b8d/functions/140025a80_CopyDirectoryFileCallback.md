# CopyDirectoryFileCallback

- ea: `0x140025a80`
- end: `0x140025c70`
- name: `CopyDirectoryFileCallback`
- size: `496`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callees

- `0x140022960`
- `0x140023c8c`
- `0x140023dcc`
- `0x140025a80`
- `0x140027f0c`
- `0x140082010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x140025bd7`
- `KERNEL32!FreeLibrary` at `0x140025bd7`
- `KERNEL32!LoadLibraryExW` at `0x140025b8d`
- `KERNEL32!LoadLibraryExW` at `0x140025b8d`
- `KERNEL32!HeapFree` at `0x140025c39`
- `KERNEL32!HeapFree` at `0x140025c39`
- `KERNEL32!GetProcAddress` at `0x140025baf`
- `KERNEL32!GetProcAddress` at `0x140025baf`
- `KERNEL32!GetProcessHeap` at `0x140025c25`
- `KERNEL32!GetProcessHeap` at `0x140025c25`
- `KERNEL32!GetLastError` at `0x140025b62`
- `KERNEL32!GetLastError` at `0x140025b62`
- `KERNEL32!WaitForSingleObject` at `0x140025aab`
- `KERNEL32!WaitForSingleObject` at `0x140025aab`
- `KERNEL32!SetLastError` at `0x140025c48`
- `KERNEL32!SetLastError` at `0x140025c48`

## string_xrefs

- `0x140025abe`: `CopyDirectoryFileCallback: The copy was canceled by the user.`
- `0x140025b84`: `user32.dll`
- `0x140025c08`: `CopyDirectoryFileCallback: Unable to %s file from [%s] to [%s]; GLE = 0x%x`

## pseudocode

```c
__int64 __fastcall CopyDirectoryFileCallback(__int64 a1, __int64 a2)
{
  unsigned int v3; // edi
  void *v4; // rcx
  DWORD v6; // ecx
  unsigned int (__fastcall *v7)(_QWORD, _QWORD); // rax
  _QWORD *v8; // rsi
  __int64 v9; // rax
  void *v10; // r15
  _DWORD *v11; // rbp
  DWORD LastError; // r14d
  HMODULE Library; // rax
  HMODULE v14; // rsi
  FARPROC ProcAddress; // rax
  const wchar_t *v16; // r9
  HANDLE ProcessHeap; // rax

  v3 = 0;
  v4 = *(void **)(a2 + 24);
  if ( v4 && WaitForSingleObject(v4, 0) != 258 )
  {
    LibLog(&g_WdsLibLog, 0x4000000, L"CopyDirectoryFileCallback: The copy was canceled by the user.");
    v6 = 1223;
LABEL_23:
    SetLastError(v6);
    return v3;
  }
  v7 = *(unsigned int (__fastcall **)(_QWORD, _QWORD))(a2 + 32);
  v8 = (_QWORD *)(a1 + 40);
  if ( !v7 || !v7(*v8, *(_QWORD *)(a2 + 40)) )
  {
    v9 = BuildPath(*(STRSAFE_PCNZWCH *)(a2 + 8));
    v10 = (void *)v9;
    if ( !v9 )
      return v3;
    v11 = (_DWORD *)(a2 + 16);
    if ( (unsigned int)CopyFileWithAttributesEx2(
                         *v8,
                         v9,
                         *(unsigned int *)(a2 + 20),
                         *(_QWORD *)(a2 + 56),
                         *(_QWORD *)(a2 + 64)) == 1 )
    {
      if ( !*v11 )
      {
LABEL_12:
        v3 = 1;
        goto LABEL_13;
      }
      if ( (unsigned int)DeleteFileEx2(*v8, 0) == 1 )
      {
        v8 = (_QWORD *)(a1 + 40);
        goto LABEL_12;
      }
    }
LABEL_13:
    LastError = GetLastError();
    if ( v3 == 1 )
    {
      if ( *(_QWORD *)(a2 + 48) )
      {
        Library = LoadLibraryExW(L"user32.dll", 0, 0);
        v14 = Library;
        if ( Library )
        {
          ProcAddress = GetProcAddress(Library, "SendMessageW");
          if ( ProcAddress )
            ((void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))ProcAddress)(*(_QWORD *)(a2 + 48), 1029, 0, 0);
          FreeLibrary(v14);
        }
      }
    }
    else
    {
      v16 = L"move";
      if ( *v11 != 1 )
        v16 = L"copy";
      LibLog(
        &g_WdsLibLog,
        0x2000000,
        L"CopyDirectoryFileCallback: Unable to %s file from [%s] to [%s]; GLE = 0x%x",
        v16,
        *v8,
        v10,
        LastError);
    }
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v10);
    v6 = LastError;
    goto LABEL_23;
  }
  return 1;
}

```

## disassembly

```asm
0x140025a80  mov     [rsp+arg_0], rbx
0x140025a85  mov     [rsp+arg_8], rbp
0x140025a8a  mov     [rsp+arg_10], rsi
0x140025a8f  push    rdi
0x140025a90  push    r14
0x140025a92  push    r15
0x140025a94  sub     rsp, 40h
0x140025a98  mov     r14, rcx
0x140025a9b  xor     edi, edi
0x140025a9d  mov     rcx, [rdx+18h]; hHandle
0x140025aa1  mov     rbx, rdx
0x140025aa4  test    rcx, rcx
0x140025aa7  jz      short loc_140025AE0
0x140025aa9  xor     edx, edx; dwMilliseconds
0x140025aab  call    cs:__imp_WaitForSingleObject
0x140025ab2  nop     dword ptr [rax+rax+00h]
0x140025ab7  cmp     eax, 102h
0x140025abc  jz      short loc_140025AE0
0x140025abe  lea     r8, aCopydirectoryf_0; "CopyDirectoryFileCallback: The copy was"...
0x140025ac5  mov     edx, 4000000h
0x140025aca  lea     rcx, g_WdsLibLog
0x140025ad1  call    LibLog
0x140025ad6  mov     ecx, 4C7h
0x140025adb  jmp     loc_140025C48
0x140025ae0  mov     rax, [rbx+20h]
0x140025ae4  lea     rsi, [r14+28h]
0x140025ae8  test    rax, rax
0x140025aeb  jz      short loc_140025B07
0x140025aed  mov     rdx, [rbx+28h]
0x140025af1  mov     rcx, [rsi]
0x140025af4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025af9  test    eax, eax
0x140025afb  jz      short loc_140025B07
0x140025afd  mov     edi, 1
0x140025b02  jmp     loc_140025C54
0x140025b07  mov     rdx, [r14+30h]
0x140025b0b  mov     rcx, [rbx+8]; pszSrc
0x140025b0f  call    BuildPath
0x140025b14  mov     r15, rax
0x140025b17  test    rax, rax
0x140025b1a  jz      loc_140025C54
0x140025b20  mov     rcx, [rbx+40h]
0x140025b24  mov     rdx, rax
0x140025b27  mov     r9, [rbx+38h]
0x140025b2b  mov     r8d, [rbx+14h]
0x140025b2f  mov     [rsp+58h+var_38], rcx
0x140025b34  mov     rcx, [rsi]
0x140025b37  call    CopyFileWithAttributesEx2
0x140025b3c  lea     rbp, [rbx+10h]
0x140025b40  cmp     eax, 1
0x140025b43  jnz     short loc_140025B62
0x140025b45  cmp     [rbp+0], edi
0x140025b48  jz      short loc_140025B5D
0x140025b4a  mov     rcx, [rsi]
0x140025b4d  xor     edx, edx
0x140025b4f  call    DeleteFileEx2
0x140025b54  cmp     eax, 1
0x140025b57  jnz     short loc_140025B62
0x140025b59  lea     rsi, [r14+28h]
0x140025b5d  mov     edi, 1
0x140025b62  call    cs:__imp_GetLastError
0x140025b69  nop     dword ptr [rax+rax+00h]
0x140025b6e  mov     r14d, eax
0x140025b71  cmp     edi, 1
0x140025b74  jnz     short loc_140025BE5
0x140025b76  cmp     qword ptr [rbx+30h], 0
0x140025b7b  jz      loc_140025C25
0x140025b81  xor     r8d, r8d; dwFlags
0x140025b84  lea     rcx, aUser32Dll_0; "user32.dll"
0x140025b8b  xor     edx, edx; hFile
0x140025b8d  call    cs:__imp_LoadLibraryExW
0x140025b94  nop     dword ptr [rax+rax+00h]
0x140025b99  mov     rsi, rax
0x140025b9c  test    rax, rax
0x140025b9f  jz      loc_140025C25
0x140025ba5  lea     rdx, aSendmessagew; "SendMessageW"
0x140025bac  mov     rcx, rax; hModule
0x140025baf  call    cs:__imp_GetProcAddress
0x140025bb6  nop     dword ptr [rax+rax+00h]
0x140025bbb  test    rax, rax
0x140025bbe  jz      short loc_140025BD4
0x140025bc0  mov     rcx, [rbx+30h]
0x140025bc4  xor     r9d, r9d
0x140025bc7  xor     r8d, r8d
0x140025bca  mov     edx, 405h
0x140025bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025bd4  mov     rcx, rsi; hLibModule
0x140025bd7  call    cs:__imp_FreeLibrary
0x140025bde  nop     dword ptr [rax+rax+00h]
0x140025be3  jmp     short loc_140025C25
0x140025be5  cmp     dword ptr [rbp+0], 1
0x140025be9  lea     rax, aCopy; "copy"
0x140025bf0  mov     [rsp+58h+var_28], r14d
0x140025bf5  lea     r9, aMove; "move"
0x140025bfc  cmovnz  r9, rax
0x140025c00  mov     [rsp+58h+var_30], r15
0x140025c05  mov     rax, [rsi]
0x140025c08  lea     r8, aCopydirectoryf; "CopyDirectoryFileCallback: Unable to %s"...
0x140025c0f  mov     edx, 2000000h
0x140025c14  mov     [rsp+58h+var_38], rax
0x140025c19  lea     rcx, g_WdsLibLog
0x140025c20  call    LibLog
0x140025c25  call    cs:__imp_GetProcessHeap
0x140025c2c  nop     dword ptr [rax+rax+00h]
0x140025c31  mov     r8, r15; lpMem
0x140025c34  xor     edx, edx; dwFlags
0x140025c36  mov     rcx, rax; hHeap
0x140025c39  call    cs:__imp_HeapFree
0x140025c40  nop     dword ptr [rax+rax+00h]
0x140025c45  mov     ecx, r14d; dwErrCode
0x140025c48  call    cs:__imp_SetLastError
0x140025c4f  nop     dword ptr [rax+rax+00h]
0x140025c54  mov     rbx, [rsp+58h+arg_0]
0x140025c59  mov     eax, edi
0x140025c5b  mov     rbp, [rsp+58h+arg_8]
0x140025c60  mov     rsi, [rsp+58h+arg_10]
0x140025c65  add     rsp, 40h
0x140025c69  pop     r15
0x140025c6b  pop     r14
0x140025c6d  pop     rdi
0x140025c6e  retn
```
