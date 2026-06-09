# BoxCabCallback(FDINOTIFICATIONTYPE,FDINOTIFICATION *)

- ea: `0x140054c20`
- end: `0x140054eb8`
- name: `?BoxCabCallback@@YA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z`
- size: `664`
- prototype: `INT_PTR __fastcall(FDINOTIFICATIONTYPE fdint, PFDINOTIFICATION pfdin)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x140052ad4`
- `0x140052f24`
- `0x140053304`
- `0x140054c20`
- `0x140080b04`
- `0x140082010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140054cc5`
- `KERNEL32!CloseHandle` at `0x140054cc5`
- `KERNEL32!DosDateTimeToFileTime` at `0x140054c7b`
- `KERNEL32!DosDateTimeToFileTime` at `0x140054c7b`
- `KERNEL32!GetLastError` at `0x140054e4d`
- `KERNEL32!GetLastError` at `0x140054e66`
- `KERNEL32!GetLastError` at `0x140054e4d`
- `KERNEL32!GetLastError` at `0x140054e66`
- `KERNEL32!LocalFileTimeToFileTime` at `0x140054c97`
- `KERNEL32!LocalFileTimeToFileTime` at `0x140054c97`
- `KERNEL32!CreateFileW` at `0x140054e03`
- `KERNEL32!CreateFileW` at `0x140054e03`
- `KERNEL32!SetEndOfFile` at `0x140054e31`
- `KERNEL32!SetEndOfFile` at `0x140054e31`
- `KERNEL32!SetFilePointer` at `0x140054e1e`
- `KERNEL32!SetFilePointer` at `0x140054e9b`
- `KERNEL32!SetFilePointer` at `0x140054e1e`
- `KERNEL32!SetFilePointer` at `0x140054e9b`
- `KERNEL32!SetFileTime` at `0x140054cb6`
- `KERNEL32!SetFileTime` at `0x140054cb6`

## pseudocode

```c
INT_PTR __fastcall BoxCabCallback(FDINOTIFICATIONTYPE fdint, PFDINOTIFICATION pfdin)
{
  _QWORD *pv; // rdi
  __int64 v4; // r13
  WCHAR *v5; // rsi
  int v6; // ecx
  int v7; // ecx
  void *hf; // rbx
  USHORT time; // dx
  USHORT date; // cx
  signed int v11; // ebx
  signed int v12; // eax
  INT_PTR result; // rax
  __int64 (__fastcall *v14)(_QWORD, LPCWSTR, _QWORD, _QWORD); // rax
  __int16 v15; // r12
  const WCHAR *v16; // rcx
  __int16 *v17; // r15
  HANDLE FileW; // rbx
  signed int LastError; // eax
  signed int v20; // eax
  LPCWSTR lpFileName; // [rsp+88h] [rbp+48h] BYREF
  FILETIME CreationTime; // [rsp+90h] [rbp+50h] BYREF
  struct _FILETIME FileTime; // [rsp+98h] [rbp+58h] BYREF

  pv = pfdin->pv;
  lpFileName = 0;
  v4 = 0;
  v5 = 0;
  v6 = fdint - 1;
  if ( !v6 )
    goto LABEL_11;
  v7 = v6 - 1;
  if ( v7 )
  {
    if ( v7 != 1 )
    {
LABEL_11:
      v11 = 0;
      goto LABEL_12;
    }
    hf = (void *)pfdin->hf;
    time = pfdin->time;
    date = pfdin->date;
    FileTime = 0;
    if ( DosDateTimeToFileTime(date, time, &FileTime) )
    {
      CreationTime = 0;
      if ( LocalFileTimeToFileTime(&FileTime, &CreationTime) )
        SetFileTime(hf, &CreationTime, &CreationTime, &CreationTime);
    }
    CloseHandle(hf);
    pfdin->hf = 0;
    if ( !pv[1] )
    {
LABEL_10:
      v4 = 1;
      goto LABEL_11;
    }
    v11 = StrAllocFormatted(&lpFileName, L"%s%S", *pv, pfdin->psz1);
    if ( v11 >= 0 )
    {
      v5 = (WCHAR *)lpFileName;
      v12 = ((__int64 (__fastcall *)(__int64, LPCWSTR, _QWORD, _QWORD))pv[1])(2, lpFileName, 0, pv[2]);
      v11 = v12;
      if ( !v12 )
        goto LABEL_10;
      goto LABEL_20;
    }
    goto LABEL_38;
  }
  v11 = StrAllocFormatted(&lpFileName, L"%s%S", *pv, pfdin->psz1);
  if ( v11 < 0 )
  {
LABEL_38:
    v5 = (WCHAR *)lpFileName;
    goto LABEL_12;
  }
  v14 = (__int64 (__fastcall *)(_QWORD, LPCWSTR, _QWORD, _QWORD))pv[1];
  v5 = (WCHAR *)lpFileName;
  if ( v14 )
  {
    v12 = v14(0, lpFileName, pfdin->cb, pv[2]);
    v11 = v12;
    if ( v12 )
    {
LABEL_20:
      *((_DWORD *)pv + 6) = v12;
      goto LABEL_12;
    }
  }
  v15 = 0;
  v17 = (__int16 *)PathFile(v5);
  if ( v17 )
  {
    v15 = *v17;
    *v17 = 0;
  }
  v11 = DirEnsureExists(v16);
  if ( v11 >= 0 )
  {
    if ( v17 && v15 )
      *v17 = v15;
    FileW = CreateFileW(v5, 0x40000000u, 1u, 0, 2u, 0x8000080u, 0);
    if ( SetFilePointer(FileW, pfdin->cb, 0, 0) && SetEndOfFile(FileW) )
    {
      SetFilePointer(FileW, 0, 0, 0);
      v4 = (__int64)FileW;
      goto LABEL_11;
    }
    if ( !*((_DWORD *)pv + 6) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      *((_DWORD *)pv + 6) = LastError;
    }
    v20 = GetLastError();
    v11 = v20;
    if ( v20 > 0 )
      v11 = (unsigned __int16)v20 | 0x80070000;
    if ( v11 >= 0 )
      v11 = -2147467259;
  }
LABEL_12:
  if ( v5 )
    MemFree(v5);
  result = -1;
  if ( !v11 )
    return v4;
  return result;
}

```

## disassembly

```asm
0x140054c20  mov     [rsp-38h+arg_0], rbx
0x140054c25  push    rbp
0x140054c26  push    rsi
0x140054c27  push    rdi
0x140054c28  push    r12
0x140054c2a  push    r13
0x140054c2c  push    r14
0x140054c2e  push    r15
0x140054c30  mov     rbp, rsp
0x140054c33  sub     rsp, 40h
0x140054c37  mov     rdi, [rdx+20h]
0x140054c3b  xor     r15d, r15d
0x140054c3e  mov     [rbp+lpFileName], r15
0x140054c42  mov     r14, rdx
0x140054c45  mov     r13d, r15d
0x140054c48  mov     esi, r15d
0x140054c4b  sub     ecx, 1
0x140054c4e  jz      loc_140054D23
0x140054c54  sub     ecx, 1
0x140054c57  jz      loc_140054D56
0x140054c5d  sub     ecx, 1
0x140054c60  jnz     loc_140054D23
0x140054c66  mov     rbx, [rdx+28h]
0x140054c6a  lea     r8, [rbp+FileTime]; lpFileTime
0x140054c6e  movzx   edx, word ptr [rdx+32h]; wFatTime
0x140054c72  movzx   ecx, word ptr [r14+30h]; wFatDate
0x140054c77  mov     qword ptr [rbp+FileTime.dwLowDateTime], r15
0x140054c7b  call    cs:__imp_DosDateTimeToFileTime
0x140054c82  nop     dword ptr [rax+rax+00h]
0x140054c87  test    eax, eax
0x140054c89  jz      short loc_140054CC2
0x140054c8b  lea     rdx, [rbp+CreationTime]; lpFileTime
0x140054c8f  mov     qword ptr [rbp+CreationTime.dwLowDateTime], r15
0x140054c93  lea     rcx, [rbp+FileTime]; lpLocalFileTime
0x140054c97  call    cs:__imp_LocalFileTimeToFileTime
0x140054c9e  nop     dword ptr [rax+rax+00h]
0x140054ca3  test    eax, eax
0x140054ca5  jz      short loc_140054CC2
0x140054ca7  lea     r9, [rbp+CreationTime]; lpLastWriteTime
0x140054cab  mov     rcx, rbx; hFile
0x140054cae  lea     r8, [rbp+CreationTime]; lpLastAccessTime
0x140054cb2  lea     rdx, [rbp+CreationTime]; lpCreationTime
0x140054cb6  call    cs:__imp_SetFileTime
0x140054cbd  nop     dword ptr [rax+rax+00h]
0x140054cc2  mov     rcx, rbx; hObject
0x140054cc5  call    cs:__imp_CloseHandle
0x140054ccc  nop     dword ptr [rax+rax+00h]
0x140054cd1  mov     [r14+28h], r15
0x140054cd5  cmp     [rdi+8], r15
0x140054cd9  jz      short loc_140054D1D
0x140054cdb  mov     r9, [r14+8]
0x140054cdf  lea     rdx, aSS_1; "%s%S"
0x140054ce6  mov     r8, [rdi]
0x140054ce9  lea     rcx, [rbp+lpFileName]
0x140054ced  call    StrAllocFormatted
0x140054cf2  mov     ebx, eax
0x140054cf4  test    eax, eax
0x140054cf6  js      loc_140054EAF
0x140054cfc  mov     rsi, [rbp+lpFileName]
0x140054d00  xor     r8d, r8d
0x140054d03  mov     r9, [rdi+10h]
0x140054d07  mov     rdx, rsi
0x140054d0a  mov     rax, [rdi+8]
0x140054d0e  lea     ecx, [r8+2]
0x140054d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054d17  mov     ebx, eax
0x140054d19  test    eax, eax
0x140054d1b  jnz     short loc_140054D9B
0x140054d1d  mov     r13d, 1
0x140054d23  mov     ebx, r15d
0x140054d26  test    rsi, rsi
0x140054d29  jz      short loc_140054D33
0x140054d2b  mov     rcx, rsi; lpMem
0x140054d2e  call    MemFree
0x140054d33  or      rax, 0FFFFFFFFFFFFFFFFh
0x140054d37  test    ebx, ebx
0x140054d39  mov     rbx, [rsp+40h+arg_0]
0x140054d41  cmovz   rax, r13
0x140054d45  add     rsp, 40h
0x140054d49  pop     r15
0x140054d4b  pop     r14
0x140054d4d  pop     r13
0x140054d4f  pop     r12
0x140054d51  pop     rdi
0x140054d52  pop     rsi
0x140054d53  pop     rbp
0x140054d54  retn
0x140054d56  mov     r9, [rdx+8]
0x140054d5a  lea     rcx, [rbp+lpFileName]
0x140054d5e  mov     r8, [rdi]
0x140054d61  lea     rdx, aSS_1; "%s%S"
0x140054d68  call    StrAllocFormatted
0x140054d6d  mov     ebx, eax
0x140054d6f  test    eax, eax
0x140054d71  js      loc_140054EAF
0x140054d77  mov     rax, [rdi+8]
0x140054d7b  mov     rsi, [rbp+lpFileName]
0x140054d7f  test    rax, rax
0x140054d82  jz      short loc_140054DA0
0x140054d84  movsxd  r8, dword ptr [r14]
0x140054d87  mov     rdx, rsi
0x140054d8a  mov     r9, [rdi+10h]
0x140054d8e  xor     ecx, ecx
0x140054d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054d95  mov     ebx, eax
0x140054d97  test    eax, eax
0x140054d99  jz      short loc_140054DA0
0x140054d9b  mov     [rdi+18h], eax
0x140054d9e  jmp     short loc_140054D26
0x140054da0  mov     rcx, rsi
0x140054da3  movzx   r12d, r15w
0x140054da7  call    PathFile
0x140054dac  mov     r15, rax
0x140054daf  xor     eax, eax
0x140054db1  test    r15, r15
0x140054db4  jz      short loc_140054DBE
0x140054db6  movzx   r12d, word ptr [r15]
0x140054dba  mov     [r15], ax
0x140054dbe  call    DirEnsureExists
0x140054dc3  mov     ebx, eax
0x140054dc5  test    eax, eax
0x140054dc7  js      loc_140054D26
0x140054dcd  test    r15, r15
0x140054dd0  jz      short loc_140054DDC
0x140054dd2  test    r12w, r12w
0x140054dd6  jz      short loc_140054DDC
0x140054dd8  mov     [r15], r12w
0x140054ddc  xor     r15d, r15d
0x140054ddf  xor     r9d, r9d; lpSecurityAttributes
0x140054de2  mov     [rsp+40h+hTemplateFile], r15; hTemplateFile
0x140054de7  mov     edx, 40000000h; dwDesiredAccess
0x140054dec  mov     [rsp+40h+dwFlagsAndAttributes], 8000080h; dwFlagsAndAttributes
0x140054df4  mov     rcx, rsi; lpFileName
0x140054df7  mov     [rsp+40h+dwCreationDisposition], 2; dwCreationDisposition
0x140054dff  lea     r8d, [r15+1]; dwShareMode
0x140054e03  call    cs:__imp_CreateFileW
0x140054e0a  nop     dword ptr [rax+rax+00h]
0x140054e0f  mov     edx, [r14]; lDistanceToMove
0x140054e12  xor     r9d, r9d; dwMoveMethod
0x140054e15  mov     rcx, rax; hFile
0x140054e18  xor     r8d, r8d; lpDistanceToMoveHigh
0x140054e1b  mov     rbx, rax
0x140054e1e  call    cs:__imp_SetFilePointer
0x140054e25  nop     dword ptr [rax+rax+00h]
0x140054e2a  test    eax, eax
0x140054e2c  jz      short loc_140054E41
0x140054e2e  mov     rcx, rbx; hFile
0x140054e31  call    cs:__imp_SetEndOfFile
0x140054e38  nop     dword ptr [rax+rax+00h]
0x140054e3d  test    eax, eax
0x140054e3f  jnz     short loc_140054E90
0x140054e41  mov     r14d, 80070000h
0x140054e47  cmp     [rdi+18h], r15d
0x140054e4b  jnz     short loc_140054E66
0x140054e4d  call    cs:__imp_GetLastError
0x140054e54  nop     dword ptr [rax+rax+00h]
0x140054e59  test    eax, eax
0x140054e5b  jle     short loc_140054E63
0x140054e5d  movzx   eax, ax
0x140054e60  or      eax, r14d
0x140054e63  mov     [rdi+18h], eax
0x140054e66  call    cs:__imp_GetLastError
0x140054e6d  nop     dword ptr [rax+rax+00h]
0x140054e72  mov     ebx, eax
0x140054e74  test    eax, eax
0x140054e76  jle     short loc_140054E7E
0x140054e78  movzx   ebx, ax
0x140054e7b  or      ebx, r14d
0x140054e7e  test    ebx, ebx
0x140054e80  js      loc_140054D26
0x140054e86  mov     ebx, 80004005h
0x140054e8b  jmp     loc_140054D26
0x140054e90  xor     r9d, r9d; dwMoveMethod
0x140054e93  xor     r8d, r8d; lpDistanceToMoveHigh
0x140054e96  xor     edx, edx; lDistanceToMove
0x140054e98  mov     rcx, rbx; hFile
0x140054e9b  call    cs:__imp_SetFilePointer
0x140054ea2  nop     dword ptr [rax+rax+00h]
0x140054ea7  mov     r13, rbx
0x140054eaa  jmp     loc_140054D23
0x140054eaf  mov     rsi, [rbp+lpFileName]
0x140054eb3  jmp     loc_140054D26
```
