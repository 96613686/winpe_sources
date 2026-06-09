# DeletePathDirectoryCallback

- ea: `0x18003bbe0`
- end: `0x18003be70`
- name: `DeletePathDirectoryCallback`
- size: `656`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, reparse_path`

## callees

- `0x18003a8d8`
- `0x18003b094`
- `0x18003b878`
- `0x18003bbe0`
- `0x18003c3b8`
- `0x18003cb5c`
- `0x18003cbdc`
- `0x18003e3e0`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003bd24`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003bd24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003bdd8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003bdd8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003bde6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003bde6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bc08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bc4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bcac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bd78`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bd8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bdcb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bc08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bc4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bcac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bd78`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bd8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bdcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bc38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bd51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bd6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003be56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bc38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bd51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bd6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003be56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bd5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bd5e`

## string_xrefs

- `0x18003bda4`: `DeletePathDirectoryCallback: Spoofing detected deleting [%s] -> [%s]`

## pseudocode

```c
__int64 __fastcall DeletePathDirectoryCallback(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 (__fastcall *v6)(_QWORD, _QWORD); // rax
  unsigned int v7; // r15d
  DWORD v8; // ecx
  __int64 v9; // rcx
  DWORD v10; // edi
  BOOL v11; // esi
  int v12; // eax
  int v13; // eax
  unsigned __int16 *v14; // rcx
  int v15; // edx
  BOOL v16; // eax
  const WCHAR *v17; // rcx
  int v18; // r13d
  DWORD LastError; // eax
  bool v20; // zf
  void *v21; // r13
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v23; // rcx
  int v24; // edx
  BOOL v25; // eax
  LPVOID lpMem; // [rsp+40h] [rbp-20h] BYREF
  const WCHAR *v27; // [rsp+48h] [rbp-18h]
  HANDLE hObject; // [rsp+50h] [rbp-10h]
  DWORD dwErrCode; // [rsp+B0h] [rbp+50h] BYREF
  int v30; // [rsp+B8h] [rbp+58h] BYREF

  if ( !a3 )
  {
    SetLastError(0x57u);
    return 0;
  }
  v6 = *(__int64 (__fastcall **)(_QWORD, _QWORD))(a3 + 16);
  v7 = 1;
  if ( v6 )
  {
    v7 = v6(*(_QWORD *)(a1 + 40), *(_QWORD *)(a3 + 24));
    if ( !v7 )
    {
      if ( GetLastError() )
        goto LABEL_47;
      v8 = 1223;
      goto LABEL_7;
    }
  }
  v9 = *(_QWORD *)(a1 + 40);
  dwErrCode = 0;
  v10 = 1;
  v11 = 0;
  if ( (unsigned int)ReparsePointExists(v9, &dwErrCode) )
  {
    if ( dwErrCode )
    {
      v12 = *(_DWORD *)(a3 + 8);
      v10 = 0;
      dwErrCode = 0;
      if ( (v12 & 2) != 0
        || (v13 = ShouldEnumerateReparsePoint(*(_QWORD *)(a1 + 40), &dwErrCode), v10 = dwErrCode, !v13)
        || !dwErrCode )
      {
        v14 = *(unsigned __int16 **)(a1 + 40);
        if ( v14 )
        {
          v15 = *(_DWORD *)(a3 + 12) & 0x21;
          v16 = v15 ? DeleteFileEx2((__int64)v14, v15) : WdsRemoveDirectory(v14);
          v11 = v16;
        }
        else
        {
          SetLastError(0x57u);
          v11 = 0;
        }
        if ( !v10 )
          goto LABEL_46;
      }
    }
  }
  if ( (*(_DWORD *)(a3 + 12) & 0x20) != 0 )
  {
    v17 = *(const WCHAR **)(a1 + 40);
    v18 = 0;
    v30 = 0;
    lpMem = 0;
    v27 = v17;
    if ( v17 && *v17 )
    {
      hObject = CreateFileW(v17, 0, 7u, 0, 3u, 0x2200000u, 0);
      if ( hObject == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        dwErrCode = LastError;
      }
      else
      {
        dwErrCode = 0;
        if ( !(unsigned int)VerifyPathRedirectionByHandle(hObject, v27, &v30, &lpMem) )
          dwErrCode = GetLastError();
        CloseHandle(hObject);
        LastError = dwErrCode;
        v18 = v30;
      }
      SetLastError(LastError);
      if ( !dwErrCode )
        goto LABEL_32;
    }
    else
    {
      SetLastError(0x57u);
    }
    v18 = 1;
LABEL_32:
    v20 = v18 == 0;
    v21 = lpMem;
    if ( v20 )
    {
      LibLog(
        &g_WdsLibLog,
        50331648,
        L"DeletePathDirectoryCallback: Spoofing detected deleting [%s] -> [%s]",
        *(_QWORD *)(a1 + 40),
        lpMem);
      v10 = 0;
      v7 = 0;
      SetLastError(0x2A9u);
      v11 = 0;
    }
    if ( v21 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v21);
    }
  }
  if ( v10 )
  {
    if ( (unsigned int)EnumeratePathEx(*(LPCWSTR *)(a1 + 40), *(_DWORD *)(a3 + 8)) == 1 )
    {
      v23 = *(unsigned __int16 **)(a1 + 40);
      v7 = 1;
      if ( v23 )
      {
        v24 = *(_DWORD *)(a3 + 12) & 0x21;
        if ( v24 )
          v25 = DeleteFileEx2((__int64)v23, v24);
        else
          v25 = WdsRemoveDirectory(v23);
        if ( v25 )
          return v7;
        goto LABEL_47;
      }
      v8 = 87;
LABEL_7:
      SetLastError(v8);
      goto LABEL_47;
    }
    v7 = 0;
LABEL_47:
    ++*(_DWORD *)(a3 + 4);
    if ( !*(_DWORD *)a3 )
      *(_DWORD *)a3 = GetLastError();
    return v7;
  }
LABEL_46:
  if ( !v11 )
    goto LABEL_47;
  return v7;
}

```

## disassembly

```asm
0x18003bbe0  mov     [rsp-38h+arg_8], rdx
0x18003bbe5  push    rbp
0x18003bbe6  push    rbx
0x18003bbe7  push    rsi
0x18003bbe8  push    rdi
0x18003bbe9  push    r13
0x18003bbeb  push    r14
0x18003bbed  push    r15
0x18003bbef  mov     rbp, rsp
0x18003bbf2  sub     rsp, 60h
0x18003bbf6  mov     rbx, r8
0x18003bbf9  mov     r13, rdx
0x18003bbfc  mov     r14, rcx
0x18003bbff  test    r8, r8
0x18003bc02  jnz     short loc_18003BC15
0x18003bc04  lea     ecx, [r8+57h]; dwErrCode
0x18003bc08  call    cs:__imp_SetLastError
0x18003bc0e  xor     eax, eax
0x18003bc10  jmp     loc_18003BE61
0x18003bc15  mov     rax, [r8+10h]
0x18003bc19  mov     r15d, 1
0x18003bc1f  test    rax, rax
0x18003bc22  jz      short loc_18003BC56
0x18003bc24  mov     rdx, [r8+18h]
0x18003bc28  mov     rcx, [rcx+28h]
0x18003bc2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc31  mov     r15d, eax
0x18003bc34  test    eax, eax
0x18003bc36  jnz     short loc_18003BC56
0x18003bc38  call    cs:__imp_GetLastError
0x18003bc3e  test    eax, eax
0x18003bc40  jnz     loc_18003BE4E
0x18003bc46  mov     ecx, 4C7h; dwErrCode
0x18003bc4b  call    cs:__imp_SetLastError
0x18003bc51  jmp     loc_18003BE4E
0x18003bc56  mov     rcx, [r14+28h]
0x18003bc5a  lea     rdx, [rbp+dwErrCode]
0x18003bc5e  mov     [rbp+dwErrCode], 0
0x18003bc65  mov     edi, 1
0x18003bc6a  xor     esi, esi
0x18003bc6c  call    ReparsePointExists
0x18003bc71  test    eax, eax
0x18003bc73  jz      short loc_18003BCD4
0x18003bc75  cmp     [rbp+dwErrCode], esi
0x18003bc78  jz      short loc_18003BCD4
0x18003bc7a  mov     eax, [rbx+8]
0x18003bc7d  xor     edi, edi
0x18003bc7f  mov     [rbp+dwErrCode], edi
0x18003bc82  test    al, 2
0x18003bc84  jnz     short loc_18003BC9E
0x18003bc86  mov     rcx, [r14+28h]
0x18003bc8a  lea     rdx, [rbp+dwErrCode]
0x18003bc8e  call    ShouldEnumerateReparsePoint
0x18003bc93  mov     edi, [rbp+dwErrCode]
0x18003bc96  test    eax, eax
0x18003bc98  jz      short loc_18003BC9E
0x18003bc9a  test    edi, edi
0x18003bc9c  jnz     short loc_18003BCD4
0x18003bc9e  mov     rcx, [r14+28h]
0x18003bca2  test    rcx, rcx
0x18003bca5  jnz     short loc_18003BCB6
0x18003bca7  mov     ecx, 57h ; 'W'; dwErrCode
0x18003bcac  call    cs:__imp_SetLastError
0x18003bcb2  xor     esi, esi
0x18003bcb4  jmp     short loc_18003BCCC
0x18003bcb6  mov     edx, [rbx+0Ch]
0x18003bcb9  and     edx, 21h
0x18003bcbc  jnz     short loc_18003BCC5
0x18003bcbe  call    WdsRemoveDirectory
0x18003bcc3  jmp     short loc_18003BCCA
0x18003bcc5  call    DeleteFileEx2
0x18003bcca  mov     esi, eax
0x18003bccc  test    edi, edi
0x18003bcce  jz      loc_18003BE4A
0x18003bcd4  mov     eax, [rbx+0Ch]
0x18003bcd7  test    al, 20h
0x18003bcd9  jz      loc_18003BDF0
0x18003bcdf  mov     rcx, [r14+28h]; lpFileName
0x18003bce3  xor     r13d, r13d
0x18003bce6  mov     [rbp+arg_18], r13d
0x18003bcea  mov     [rbp+lpMem], r13
0x18003bcee  mov     [rbp+var_18], rcx
0x18003bcf2  test    rcx, rcx
0x18003bcf5  jz      loc_18003BD86
0x18003bcfb  xor     eax, eax
0x18003bcfd  cmp     ax, [rcx]
0x18003bd00  jz      loc_18003BD86
0x18003bd06  mov     [rsp+60h+hTemplateFile], rax; hTemplateFile
0x18003bd0b  lea     r8d, [r13+7]; dwShareMode
0x18003bd0f  mov     [rsp+60h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18003bd17  xor     r9d, r9d; lpSecurityAttributes
0x18003bd1a  xor     edx, edx; dwDesiredAccess
0x18003bd1c  mov     [rsp+60h+dwCreationDisposition], 3; dwCreationDisposition
0x18003bd24  call    cs:__imp_CreateFileW
0x18003bd2a  mov     [rbp+hObject], rax
0x18003bd2e  mov     rcx, rax
0x18003bd31  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003bd35  jz      short loc_18003BD6D
0x18003bd37  mov     rdx, [rbp+var_18]
0x18003bd3b  lea     r9, [rbp+lpMem]
0x18003bd3f  xor     eax, eax
0x18003bd41  lea     r8, [rbp+arg_18]
0x18003bd45  mov     [rbp+dwErrCode], eax
0x18003bd48  call    VerifyPathRedirectionByHandle
0x18003bd4d  test    eax, eax
0x18003bd4f  jnz     short loc_18003BD5A
0x18003bd51  call    cs:__imp_GetLastError
0x18003bd57  mov     [rbp+dwErrCode], eax
0x18003bd5a  mov     rcx, [rbp+hObject]; hObject
0x18003bd5e  call    cs:__imp_CloseHandle
0x18003bd64  mov     eax, [rbp+dwErrCode]
0x18003bd67  mov     r13d, [rbp+arg_18]
0x18003bd6b  jmp     short loc_18003BD76
0x18003bd6d  call    cs:__imp_GetLastError
0x18003bd73  mov     [rbp+dwErrCode], eax
0x18003bd76  mov     ecx, eax; dwErrCode
0x18003bd78  call    cs:__imp_SetLastError
0x18003bd7e  cmp     [rbp+dwErrCode], 0
0x18003bd82  jz      short loc_18003BD97
0x18003bd84  jmp     short loc_18003BD91
0x18003bd86  mov     ecx, 57h ; 'W'; dwErrCode
0x18003bd8b  call    cs:__imp_SetLastError
0x18003bd91  mov     r13d, 1
0x18003bd97  test    r13d, r13d
0x18003bd9a  mov     r13, [rbp+lpMem]
0x18003bd9e  jnz     short loc_18003BDD3
0x18003bda0  mov     r9, [r14+28h]
0x18003bda4  lea     r8, aDeletepathdire; "DeletePathDirectoryCallback: Spoofing d"...
0x18003bdab  mov     edx, 3000000h
0x18003bdb0  mov     qword ptr [rsp+60h+dwCreationDisposition], r13
0x18003bdb5  lea     rcx, g_WdsLibLog
0x18003bdbc  call    LibLog
0x18003bdc1  mov     ecx, 2A9h; dwErrCode
0x18003bdc6  xor     edi, edi
0x18003bdc8  xor     r15d, r15d
0x18003bdcb  call    cs:__imp_SetLastError
0x18003bdd1  xor     esi, esi
0x18003bdd3  test    r13, r13
0x18003bdd6  jz      short loc_18003BDEC
0x18003bdd8  call    cs:__imp_GetProcessHeap
0x18003bdde  mov     r8, r13; lpMem
0x18003bde1  xor     edx, edx; dwFlags
0x18003bde3  mov     rcx, rax; hHeap
0x18003bde6  call    cs:__imp_HeapFree
0x18003bdec  mov     r13, [rbp+arg_8]
0x18003bdf0  test    edi, edi
0x18003bdf2  jz      short loc_18003BE4A
0x18003bdf4  mov     eax, [rbx+8]
0x18003bdf7  lea     rdx, DeletePathDirectoryCallback
0x18003bdfe  mov     rcx, [r14+28h]; lpFileName
0x18003be02  mov     r9, rbx
0x18003be05  mov     r8, r13
0x18003be08  mov     [rsp+60h+dwCreationDisposition], eax; int
0x18003be0c  call    EnumeratePathEx
0x18003be11  cmp     eax, 1
0x18003be14  jnz     short loc_18003BE45
0x18003be16  mov     rcx, [r14+28h]
0x18003be1a  mov     r15d, eax
0x18003be1d  test    rcx, rcx
0x18003be20  jnz     short loc_18003BE2A
0x18003be22  lea     ecx, [rax+56h]
0x18003be25  jmp     loc_18003BC4B
0x18003be2a  mov     edx, [rbx+0Ch]
0x18003be2d  and     edx, 21h
0x18003be30  jnz     short loc_18003BE39
0x18003be32  call    WdsRemoveDirectory
0x18003be37  jmp     short loc_18003BE3E
0x18003be39  call    DeleteFileEx2
0x18003be3e  cmp     eax, r15d
0x18003be41  jnz     short loc_18003BE4E
0x18003be43  jmp     short loc_18003BE5E
0x18003be45  xor     r15d, r15d
0x18003be48  jmp     short loc_18003BE4E
0x18003be4a  test    esi, esi
0x18003be4c  jnz     short loc_18003BE5E
0x18003be4e  inc     dword ptr [rbx+4]
0x18003be51  cmp     dword ptr [rbx], 0
0x18003be54  jnz     short loc_18003BE5E
0x18003be56  call    cs:__imp_GetLastError
0x18003be5c  mov     [rbx], eax
0x18003be5e  mov     eax, r15d
0x18003be61  add     rsp, 60h
0x18003be65  pop     r15
0x18003be67  pop     r14
0x18003be69  pop     r13
0x18003be6b  pop     rdi
0x18003be6c  pop     rsi
0x18003be6d  pop     rbx
0x18003be6e  pop     rbp
0x18003be6f  retn
```
