# DeletePathDirectoryCallback

- ea: `0x140025c80`
- end: `0x140025f87`
- name: `DeletePathDirectoryCallback`
- size: `775`
- prototype: `__int64 __fastcall(__int64, __int64 (__fastcall *)(DWORD *, __int64), __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, reparse_path`

## callees

- `0x140022960`
- `0x140023dcc`
- `0x140024cac`
- `0x140025c80`
- `0x140026684`
- `0x14002732c`
- `0x1400273e4`
- `0x14002840c`
- `0x140082010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140025e44`
- `KERNEL32!CloseHandle` at `0x140025e44`
- `KERNEL32!HeapFree` at `0x140025ee7`
- `KERNEL32!HeapFree` at `0x140025ee7`
- `KERNEL32!GetProcessHeap` at `0x140025ed3`
- `KERNEL32!GetProcessHeap` at `0x140025ed3`
- `KERNEL32!GetLastError` at `0x140025cdb`
- `KERNEL32!GetLastError` at `0x140025d07`
- `KERNEL32!GetLastError` at `0x140025e31`
- `KERNEL32!GetLastError` at `0x140025e5f`
- `KERNEL32!GetLastError` at `0x140025cdb`
- `KERNEL32!GetLastError` at `0x140025d07`
- `KERNEL32!GetLastError` at `0x140025e31`
- `KERNEL32!GetLastError` at `0x140025e5f`
- `KERNEL32!CreateFileW` at `0x140025e03`
- `KERNEL32!CreateFileW` at `0x140025e03`
- `KERNEL32!SetLastError` at `0x140025caf`
- `KERNEL32!SetLastError` at `0x140025cf2`
- `KERNEL32!SetLastError` at `0x140025d7f`
- `KERNEL32!SetLastError` at `0x140025e70`
- `KERNEL32!SetLastError` at `0x140025ebd`
- `KERNEL32!SetLastError` at `0x140025f3a`
- `KERNEL32!SetLastError` at `0x140025caf`
- `KERNEL32!SetLastError` at `0x140025cf2`
- `KERNEL32!SetLastError` at `0x140025d7f`
- `KERNEL32!SetLastError` at `0x140025e70`
- `KERNEL32!SetLastError` at `0x140025ebd`
- `KERNEL32!SetLastError` at `0x140025f3a`

## string_xrefs

- `0x140025e92`: `DeletePathDirectoryCallback: Spoofing detected deleting [%s] -> [%s]`

## pseudocode

```c
__int64 __fastcall DeletePathDirectoryCallback(__int64 a1, __int64 (__fastcall *a2)(DWORD *, __int64), __int64 a3)
{
  int v3; // r14d
  __int64 (__fastcall *v5)(DWORD *, __int64); // r13
  unsigned int v7; // edi
  __int64 (__fastcall *v9)(_QWORD, _QWORD); // rax
  DWORD v10; // ecx
  __int64 v11; // rcx
  DWORD v12; // esi
  int v13; // eax
  int v14; // eax
  __int64 v15; // rcx
  int v16; // edx
  int v17; // eax
  const WCHAR *v18; // rcx
  void *v19; // r13
  HANDLE FileW; // rax
  DWORD LastError; // eax
  int v22; // eax
  HANDLE ProcessHeap; // rax
  __int64 v24; // rcx
  int v25; // edx
  int v26; // eax
  int v27; // [rsp+40h] [rbp-20h]
  LPVOID lpMem; // [rsp+48h] [rbp-18h] BYREF
  const WCHAR *v29; // [rsp+50h] [rbp-10h]
  HANDLE hObject; // [rsp+58h] [rbp-8h]
  DWORD dwErrCode; // [rsp+B0h] [rbp+50h] BYREF
  int v33; // [rsp+B8h] [rbp+58h] BYREF

  v3 = 0;
  v5 = a2;
  v7 = 1;
  if ( !a3 )
  {
    SetLastError(0x57u);
    return 0;
  }
  v9 = *(__int64 (__fastcall **)(_QWORD, _QWORD))(a3 + 16);
  if ( v9 )
  {
    v7 = v9(*(_QWORD *)(a1 + 40), *(_QWORD *)(a3 + 24));
    if ( !v7 )
    {
      if ( GetLastError() )
        goto LABEL_8;
      v10 = 1223;
      goto LABEL_7;
    }
  }
  v11 = *(_QWORD *)(a1 + 40);
  dwErrCode = 0;
  v12 = 1;
  if ( (unsigned int)ReparsePointExists(v11, &dwErrCode) )
  {
    if ( dwErrCode )
    {
      v13 = *(_DWORD *)(a3 + 8);
      v12 = 0;
      dwErrCode = 0;
      if ( (v13 & 2) != 0
        || (v14 = ShouldEnumerateReparsePoint(*(_QWORD *)(a1 + 40), &dwErrCode), v12 = dwErrCode, !v14)
        || !dwErrCode )
      {
        v15 = *(_QWORD *)(a1 + 40);
        if ( v15 )
        {
          v16 = *(_DWORD *)(a3 + 12) & 0x21;
          v17 = v16 ? DeleteFileEx2(v15, v16) : WdsRemoveDirectory(v15);
          v3 = v17;
        }
        else
        {
          SetLastError(0x57u);
          v3 = 0;
        }
        if ( !v12 )
          goto LABEL_50;
      }
    }
  }
  if ( (*(_DWORD *)(a3 + 12) & 0x20) != 0 )
  {
    v18 = *(const WCHAR **)(a1 + 40);
    v19 = 0;
    v27 = 0;
    v33 = 0;
    lpMem = 0;
    v29 = v18;
    dwErrCode = 0;
    if ( v18 && *v18 )
    {
      FileW = CreateFileW(v18, 0, 7u, 0, 3u, 0x2200000u, 0);
      hObject = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        dwErrCode = LastError;
      }
      else
      {
        if ( !(unsigned int)VerifyPathRedirectionByHandle(FileW, v29, &v33, &lpMem) )
          dwErrCode = GetLastError();
        CloseHandle(hObject);
        v19 = lpMem;
        v27 = v33;
        LastError = dwErrCode;
      }
      SetLastError(LastError);
      if ( !dwErrCode )
      {
        v22 = v27;
LABEL_33:
        if ( !v22 )
        {
          LibLog(
            &g_WdsLibLog,
            50331648,
            L"DeletePathDirectoryCallback: Spoofing detected deleting [%s] -> [%s]",
            *(_QWORD *)(a1 + 40),
            v19);
          v12 = 0;
          v7 = 0;
          SetLastError(0x2A9u);
          v3 = 0;
        }
        if ( v19 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v19);
        }
        v5 = a2;
        goto LABEL_38;
      }
    }
    else
    {
      SetLastError(0x57u);
    }
    v22 = 1;
    goto LABEL_33;
  }
LABEL_38:
  if ( v12 )
  {
    if ( (unsigned int)EnumeratePathEx(
                         *(LPCWSTR *)(a1 + 40),
                         (__int64 (__fastcall *)(DWORD *, __int64 (__fastcall *)(_QWORD, _QWORD), __int64))DeletePathDirectoryCallback,
                         v5,
                         a3,
                         *(_DWORD *)(a3 + 8)) == 1 )
    {
      v24 = *(_QWORD *)(a1 + 40);
      v7 = 1;
      if ( v24 )
      {
        v25 = *(_DWORD *)(a3 + 12) & 0x21;
        if ( v25 )
          v26 = DeleteFileEx2(v24, v25);
        else
          v26 = WdsRemoveDirectory(v24);
        if ( v26 == 1 )
          return v7;
        goto LABEL_8;
      }
      v10 = 87;
LABEL_7:
      SetLastError(v10);
      goto LABEL_8;
    }
    v7 = 0;
LABEL_8:
    ++*(_DWORD *)(a3 + 4);
    if ( !*(_DWORD *)a3 )
      *(_DWORD *)a3 = GetLastError();
    return v7;
  }
LABEL_50:
  if ( !v3 )
    goto LABEL_8;
  return v7;
}

```

## disassembly

```asm
0x140025c80  mov     [rsp-38h+arg_8], rdx
0x140025c85  push    rbp
0x140025c86  push    rbx
0x140025c87  push    rsi
0x140025c88  push    rdi
0x140025c89  push    r13
0x140025c8b  push    r14
0x140025c8d  push    r15
0x140025c8f  mov     rbp, rsp
0x140025c92  sub     rsp, 60h
0x140025c96  xor     r14d, r14d
0x140025c99  mov     rbx, r8
0x140025c9c  mov     r13, rdx
0x140025c9f  mov     r15, rcx
0x140025ca2  mov     edi, 1
0x140025ca7  test    r8, r8
0x140025caa  jnz     short loc_140025CBF
0x140025cac  lea     ecx, [rdi+56h]; dwErrCode
0x140025caf  call    cs:__imp_SetLastError
0x140025cb6  nop     dword ptr [rax+rax+00h]
0x140025cbb  xor     eax, eax
0x140025cbd  jmp     short loc_140025D17
0x140025cbf  mov     rax, [r8+10h]
0x140025cc3  test    rax, rax
0x140025cc6  jz      short loc_140025D27
0x140025cc8  mov     rdx, [r8+18h]
0x140025ccc  mov     rcx, [rcx+28h]
0x140025cd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025cd5  mov     edi, eax
0x140025cd7  test    eax, eax
0x140025cd9  jnz     short loc_140025D27
0x140025cdb  call    cs:__imp_GetLastError
0x140025ce2  nop     dword ptr [rax+rax+00h]
0x140025ce7  xor     edx, edx
0x140025ce9  test    eax, eax
0x140025ceb  jnz     short loc_140025D00
0x140025ced  mov     ecx, 4C7h; dwErrCode
0x140025cf2  call    cs:__imp_SetLastError
0x140025cf9  nop     dword ptr [rax+rax+00h]
0x140025cfe  xor     edx, edx
0x140025d00  inc     dword ptr [rbx+4]
0x140025d03  cmp     [rbx], edx
0x140025d05  jnz     short loc_140025D15
0x140025d07  call    cs:__imp_GetLastError
0x140025d0e  nop     dword ptr [rax+rax+00h]
0x140025d13  mov     [rbx], eax
0x140025d15  mov     eax, edi
0x140025d17  add     rsp, 60h
0x140025d1b  pop     r15
0x140025d1d  pop     r14
0x140025d1f  pop     r13
0x140025d21  pop     rdi
0x140025d22  pop     rsi
0x140025d23  pop     rbx
0x140025d24  pop     rbp
0x140025d25  retn
0x140025d27  mov     rcx, [r15+28h]
0x140025d2b  lea     rdx, [rbp+dwErrCode]
0x140025d2f  mov     [rbp+dwErrCode], r14d
0x140025d33  mov     esi, 1
0x140025d38  call    ReparsePointExists
0x140025d3d  xor     edx, edx
0x140025d3f  test    eax, eax
0x140025d41  jz      short loc_140025DB0
0x140025d43  cmp     [rbp+dwErrCode], edx
0x140025d46  jz      short loc_140025DB0
0x140025d48  mov     eax, [rbx+8]
0x140025d4b  mov     esi, edx
0x140025d4d  mov     [rbp+dwErrCode], edx
0x140025d50  test    al, 2
0x140025d52  jnz     short loc_140025D6E
0x140025d54  mov     rcx, [r15+28h]
0x140025d58  lea     rdx, [rbp+dwErrCode]
0x140025d5c  call    ShouldEnumerateReparsePoint
0x140025d61  mov     esi, [rbp+dwErrCode]
0x140025d64  xor     edx, edx
0x140025d66  test    eax, eax
0x140025d68  jz      short loc_140025D6E
0x140025d6a  test    esi, esi
0x140025d6c  jnz     short loc_140025DB0
0x140025d6e  mov     rcx, [r15+28h]
0x140025d72  mov     edx, [rbx+0Ch]
0x140025d75  test    rcx, rcx
0x140025d78  jnz     short loc_140025D92
0x140025d7a  mov     ecx, 57h ; 'W'; dwErrCode
0x140025d7f  call    cs:__imp_SetLastError
0x140025d86  nop     dword ptr [rax+rax+00h]
0x140025d8b  xor     edx, edx
0x140025d8d  mov     r14d, edx
0x140025d90  jmp     short loc_140025DA8
0x140025d92  and     edx, 21h
0x140025d95  jnz     short loc_140025D9E
0x140025d97  call    WdsRemoveDirectory
0x140025d9c  jmp     short loc_140025DA3
0x140025d9e  call    DeleteFileEx2
0x140025da3  mov     r14d, eax
0x140025da6  xor     edx, edx
0x140025da8  test    esi, esi
0x140025daa  jz      loc_140025F79
0x140025db0  mov     eax, [rbx+0Ch]
0x140025db3  test    al, 20h
0x140025db5  jz      loc_140025EF9
0x140025dbb  mov     rcx, [r15+28h]; lpFileName
0x140025dbf  mov     r13, rdx
0x140025dc2  mov     [rbp+var_20], edx
0x140025dc5  mov     [rbp+arg_18], edx
0x140025dc8  mov     [rbp+lpMem], rdx
0x140025dcc  mov     [rbp+var_10], rcx
0x140025dd0  mov     [rbp+dwErrCode], edx
0x140025dd3  test    rcx, rcx
0x140025dd6  jz      loc_140025F35
0x140025ddc  cmp     dx, [rcx]
0x140025ddf  jz      loc_140025F35
0x140025de5  mov     [rsp+60h+hTemplateFile], rdx; hTemplateFile
0x140025dea  xor     r9d, r9d; lpSecurityAttributes
0x140025ded  mov     [rsp+60h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x140025df5  xor     edx, edx; dwDesiredAccess
0x140025df7  mov     [rsp+60h+dwCreationDisposition], 3; dwCreationDisposition
0x140025dff  lea     r8d, [r9+7]; dwShareMode
0x140025e03  call    cs:__imp_CreateFileW
0x140025e0a  nop     dword ptr [rax+rax+00h]
0x140025e0f  mov     [rbp+hObject], rax
0x140025e13  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140025e17  jz      short loc_140025E5F
0x140025e19  mov     rdx, [rbp+var_10]
0x140025e1d  lea     r9, [rbp+lpMem]
0x140025e21  lea     r8, [rbp+arg_18]
0x140025e25  mov     rcx, rax
0x140025e28  call    VerifyPathRedirectionByHandle
0x140025e2d  test    eax, eax
0x140025e2f  jnz     short loc_140025E40
0x140025e31  call    cs:__imp_GetLastError
0x140025e38  nop     dword ptr [rax+rax+00h]
0x140025e3d  mov     [rbp+dwErrCode], eax
0x140025e40  mov     rcx, [rbp+hObject]; hObject
0x140025e44  call    cs:__imp_CloseHandle
0x140025e4b  nop     dword ptr [rax+rax+00h]
0x140025e50  mov     eax, [rbp+arg_18]
0x140025e53  mov     r13, [rbp+lpMem]
0x140025e57  mov     [rbp+var_20], eax
0x140025e5a  mov     eax, [rbp+dwErrCode]
0x140025e5d  jmp     short loc_140025E6E
0x140025e5f  call    cs:__imp_GetLastError
0x140025e66  nop     dword ptr [rax+rax+00h]
0x140025e6b  mov     [rbp+dwErrCode], eax
0x140025e6e  mov     ecx, eax; dwErrCode
0x140025e70  call    cs:__imp_SetLastError
0x140025e77  nop     dword ptr [rax+rax+00h]
0x140025e7c  xor     edx, edx
0x140025e7e  cmp     [rbp+dwErrCode], edx
0x140025e81  jnz     loc_140025F48
0x140025e87  mov     eax, [rbp+var_20]
0x140025e8a  test    eax, eax
0x140025e8c  jnz     short loc_140025ECE
0x140025e8e  mov     r9, [r15+28h]
0x140025e92  lea     r8, aDeletepathdire; "DeletePathDirectoryCallback: Spoofing d"...
0x140025e99  mov     edx, 3000000h
0x140025e9e  mov     qword ptr [rsp+60h+dwCreationDisposition], r13
0x140025ea3  lea     rcx, g_WdsLibLog
0x140025eaa  call    LibLog
0x140025eaf  xor     r8d, r8d
0x140025eb2  mov     ecx, 2A9h; dwErrCode
0x140025eb7  mov     esi, r8d
0x140025eba  mov     edi, r8d
0x140025ebd  call    cs:__imp_SetLastError
0x140025ec4  nop     dword ptr [rax+rax+00h]
0x140025ec9  xor     edx, edx
0x140025ecb  mov     r14d, edx
0x140025ece  test    r13, r13
0x140025ed1  jz      short loc_140025EF5
0x140025ed3  call    cs:__imp_GetProcessHeap
0x140025eda  nop     dword ptr [rax+rax+00h]
0x140025edf  mov     r8, r13; lpMem
0x140025ee2  xor     edx, edx; dwFlags
0x140025ee4  mov     rcx, rax; hHeap
0x140025ee7  call    cs:__imp_HeapFree
0x140025eee  nop     dword ptr [rax+rax+00h]
0x140025ef3  xor     edx, edx
0x140025ef5  mov     r13, [rbp+arg_8]
0x140025ef9  test    esi, esi
0x140025efb  jz      short loc_140025F79
0x140025efd  mov     eax, [rbx+8]
0x140025f00  lea     rdx, DeletePathDirectoryCallback
0x140025f07  mov     rcx, [r15+28h]; lpFileName
0x140025f0b  mov     r9, rbx
0x140025f0e  mov     r8, r13
0x140025f11  mov     [rsp+60h+dwCreationDisposition], eax; int
0x140025f15  call    EnumeratePathEx
0x140025f1a  cmp     eax, 1
0x140025f1d  jnz     short loc_140025F70
0x140025f1f  mov     rcx, [r15+28h]
0x140025f23  mov     edi, eax
0x140025f25  mov     edx, [rbx+0Ch]
0x140025f28  test    rcx, rcx
0x140025f2b  jnz     short loc_140025F52
0x140025f2d  lea     ecx, [rax+56h]
0x140025f30  jmp     loc_140025CF2
0x140025f35  mov     ecx, 57h ; 'W'; dwErrCode
0x140025f3a  call    cs:__imp_SetLastError
0x140025f41  nop     dword ptr [rax+rax+00h]
0x140025f46  xor     edx, edx
0x140025f48  mov     eax, 1
0x140025f4d  jmp     loc_140025E8A
0x140025f52  and     edx, 21h
0x140025f55  jnz     short loc_140025F5E
0x140025f57  call    WdsRemoveDirectory
0x140025f5c  jmp     short loc_140025F63
0x140025f5e  call    DeleteFileEx2
0x140025f63  cmp     eax, edi
0x140025f65  jnz     loc_140025CFE
0x140025f6b  jmp     loc_140025D15
0x140025f70  xor     edx, edx
0x140025f72  mov     edi, edx
0x140025f74  jmp     loc_140025D00
0x140025f79  test    r14d, r14d
0x140025f7c  jnz     loc_140025D15
0x140025f82  jmp     loc_140025D00
```
