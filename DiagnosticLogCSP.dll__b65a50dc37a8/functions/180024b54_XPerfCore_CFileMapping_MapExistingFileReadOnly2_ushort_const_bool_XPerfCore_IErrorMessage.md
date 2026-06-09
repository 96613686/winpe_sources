# XPerfCore::CFileMapping::MapExistingFileReadOnly2(ushort const *,bool,XPerfCore::IErrorMessage *)

- ea: `0x180024b54`
- end: `0x180024e12`
- name: `?MapExistingFileReadOnly2@CFileMapping@XPerfCore@@QEAAJPEBG_NPEAVIErrorMessage@2@@Z`
- size: `702`
- prototype: `int(XPerfCore::CFileMapping *__hidden this, const unsigned __int16 *, bool, struct XPerfCore::IErrorMessage *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180021250`
- `0x180035e28`

## callees

- `0x180024b54`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180024b9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180024b9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024cc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024d7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024cc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024d7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024d0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024d28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024d0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024d28`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024c05`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024c05`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180024cf2`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180024cf2`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x180024d57`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x180024d57`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180024ca3`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180024ca3`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x180024c20`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x180024c20`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180024bb0`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180024bb0`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x180024bcc`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x180024bcc`

## string_xrefs

- `0x180024c4d`: `CreateFile failed: %d`
- `0x180024cd4`: `CreateFileMapping failed: %d`

## pseudocode

```c
int __fastcall XPerfCore::CFileMapping::MapExistingFileReadOnly2(
        XPerfCore::CFileMapping *this,
        const unsigned __int16 *a2,
        char a3,
        struct XPerfCore::IErrorMessage *a4)
{
  HANDLE CurrentProcess; // rax
  void (*v9)(struct XPerfCore::IErrorMessage *, const wchar_t *, ...); // rbx
  DWORD v10; // eax
  int result; // eax
  HANDLE FileMappingW; // rax
  void (__fastcall *v13)(struct XPerfCore::IErrorMessage *, const wchar_t *, _QWORD); // rbx
  DWORD LastError; // eax
  const void *v15; // rcx
  void *v16; // rcx
  unsigned int *v17; // rcx
  void (__fastcall *v18)(struct XPerfCore::IErrorMessage *, const wchar_t *, _QWORD); // rbx
  DWORD v19; // eax
  __int64 v20; // rax
  unsigned int v21; // edx
  char *v22; // rcx
  PVOID OldValue; // [rsp+40h] [rbp-28h] BYREF
  WINBOOL Wow64Process; // [rsp+70h] [rbp+8h] BYREF

  if ( *(_OWORD *)this != 0xFFFFFFFFFFFFFFFFuLL || *((_QWORD *)this + 2) )
    return -2147483634;
  Wow64Process = 0;
  OldValue = 0;
  CurrentProcess = GetCurrentProcess();
  if ( IsWow64Process(CurrentProcess, &Wow64Process) && Wow64Process == 1 )
    Wow64Process = Wow64DisableWow64FsRedirection(&OldValue);
  *(_QWORD *)this = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( Wow64Process )
    Wow64RevertWow64FsRedirection(OldValue);
  if ( *(_QWORD *)this != -1 )
  {
    FileMappingW = CreateFileMappingW(*(HANDLE *)this, 0, a3 != 0 ? 285212674 : 2, 0, 0, 0);
    *((_QWORD *)this + 1) = FileMappingW;
    if ( !FileMappingW )
    {
      if ( a4 )
      {
        v13 = *(void (__fastcall **)(struct XPerfCore::IErrorMessage *, const wchar_t *, _QWORD))(*(_QWORD *)a4 + 8LL);
        LastError = GetLastError();
        v13(a4, L"CreateFileMapping failed: %d", LastError);
      }
LABEL_16:
      v15 = (const void *)*((_QWORD *)this + 2);
      if ( v15 )
      {
        UnmapViewOfFile(v15);
        *((_QWORD *)this + 2) = 0;
      }
      v16 = (void *)*((_QWORD *)this + 1);
      if ( v16 )
      {
        CloseHandle(v16);
        *((_QWORD *)this + 1) = 0;
      }
      if ( *(_QWORD *)this != -1 )
      {
        CloseHandle(*(HANDLE *)this);
        *(_QWORD *)this = -1;
      }
      goto LABEL_11;
    }
    v17 = (unsigned int *)MapViewOfFileEx(FileMappingW, 4u, 0, 0, 0, 0);
    *((_QWORD *)this + 2) = v17;
    if ( !v17 )
    {
      if ( a4 )
      {
        v18 = *(void (__fastcall **)(struct XPerfCore::IErrorMessage *, const wchar_t *, _QWORD))(*(_QWORD *)a4 + 8LL);
        v19 = GetLastError();
        v18(a4, L"MapViewOfFileEx failed: %d", v19);
      }
      goto LABEL_16;
    }
    if ( *(_WORD *)v17 == 23117 )
    {
      v20 = v17[15];
      if ( (v20 & 3) == 0 && (_DWORD)v20 != -1 )
      {
        v21 = ~(_DWORD)v20;
        if ( (unsigned int)~(_DWORD)v20 >= 0x1B )
        {
          v22 = (char *)v17 + v20;
          if ( *(_DWORD *)v22 == 17744 )
          {
            if ( *((_WORD *)v22 + 12) == 267 )
            {
              if ( v21 > 0xF8 )
              {
LABEL_36:
                *((_QWORD *)this + 3) = *((unsigned int *)v22 + 20);
                return 0;
              }
            }
            else if ( *((_WORD *)v22 + 12) == 523 && v21 > 0x108 )
            {
              goto LABEL_36;
            }
          }
        }
      }
    }
    v22 = 0;
    goto LABEL_36;
  }
  if ( a4 )
  {
    v9 = *(void (**)(struct XPerfCore::IErrorMessage *, const wchar_t *, ...))(*(_QWORD *)a4 + 8LL);
    v10 = GetLastError();
    v9(a4, L"CreateFile failed: %d", v10);
  }
LABEL_11:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180024b54  mov     rax, rsp
0x180024b57  mov     [rax+10h], rbx
0x180024b5b  mov     [rax+18h], rbp
0x180024b5f  push    rsi
0x180024b60  push    rdi
0x180024b61  push    r14
0x180024b63  sub     rsp, 50h
0x180024b67  mov     rsi, r9
0x180024b6a  mov     bpl, r8b
0x180024b6d  mov     rbx, rdx
0x180024b70  mov     rdi, rcx
0x180024b73  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x180024b77  jnz     loc_180024DF7
0x180024b7d  xor     r14d, r14d
0x180024b80  cmp     [rcx+8], r14
0x180024b84  jnz     loc_180024DF7
0x180024b8a  cmp     [rcx+10h], r14
0x180024b8e  jnz     loc_180024DF7
0x180024b94  mov     [rax+8], r14d
0x180024b98  mov     [rax-28h], r14
0x180024b9c  call    cs:__imp_GetCurrentProcess
0x180024ba3  nop     dword ptr [rax+rax+00h]
0x180024ba8  mov     rcx, rax; hProcess
0x180024bab  lea     rdx, [rsp+68h+Wow64Process]; Wow64Process
0x180024bb0  call    cs:__imp_IsWow64Process
0x180024bb7  nop     dword ptr [rax+rax+00h]
0x180024bbc  test    eax, eax
0x180024bbe  jz      short loc_180024BE1
0x180024bc0  cmp     [rsp+68h+Wow64Process], 1
0x180024bc5  jnz     short loc_180024BE1
0x180024bc7  lea     rcx, [rsp+68h+OldValue]; OldValue
0x180024bcc  call    cs:__imp_Wow64DisableWow64FsRedirection
0x180024bd3  nop     dword ptr [rax+rax+00h]
0x180024bd8  test    eax, eax
0x180024bda  jnz     short loc_180024BE1
0x180024bdc  mov     [rsp+68h+Wow64Process], r14d
0x180024be1  mov     [rsp+68h+hTemplateFile], r14; hTemplateFile
0x180024be6  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180024bee  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180024bf6  xor     r9d, r9d; lpSecurityAttributes
0x180024bf9  mov     edx, 80000000h; dwDesiredAccess
0x180024bfe  lea     r8d, [r9+1]; dwShareMode
0x180024c02  mov     rcx, rbx; lpFileName
0x180024c05  call    cs:__imp_CreateFileW
0x180024c0c  nop     dword ptr [rax+rax+00h]
0x180024c11  mov     [rdi], rax
0x180024c14  cmp     [rsp+68h+Wow64Process], r14d
0x180024c19  jz      short loc_180024C2C
0x180024c1b  mov     rcx, [rsp+68h+OldValue]; OlValue
0x180024c20  call    cs:__imp_Wow64RevertWow64FsRedirection
0x180024c27  nop     dword ptr [rax+rax+00h]
0x180024c2c  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180024c30  jnz     short loc_180024C80
0x180024c32  test    rsi, rsi
0x180024c35  jz      short loc_180024C5F
0x180024c37  mov     rax, [rsi]
0x180024c3a  mov     rbx, [rax+8]
0x180024c3e  call    cs:__imp_GetLastError
0x180024c45  nop     dword ptr [rax+rax+00h]
0x180024c4a  mov     r8d, eax
0x180024c4d  lea     rdx, aCreatefileFail; "CreateFile failed: %d"
0x180024c54  mov     rcx, rsi
0x180024c57  mov     rax, rbx
0x180024c5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c5f  call    cs:__imp_GetLastError
0x180024c66  nop     dword ptr [rax+rax+00h]
0x180024c6b  test    eax, eax
0x180024c6d  jle     loc_180024DFC
0x180024c73  movzx   eax, ax
0x180024c76  or      eax, 80070000h
0x180024c7b  jmp     loc_180024DFC
0x180024c80  neg     bpl
0x180024c83  sbb     r8d, r8d
0x180024c86  and     r8d, 11000000h
0x180024c8d  add     r8d, 2; flProtect
0x180024c91  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], r14; lpName
0x180024c96  mov     [rsp+68h+dwCreationDisposition], r14d; dwMaximumSizeLow
0x180024c9b  xor     r9d, r9d; dwMaximumSizeHigh
0x180024c9e  xor     edx, edx; lpFileMappingAttributes
0x180024ca0  mov     rcx, [rdi]; hFile
0x180024ca3  call    cs:__imp_CreateFileMappingW
0x180024caa  nop     dword ptr [rax+rax+00h]
0x180024caf  mov     [rdi+8], rax
0x180024cb3  test    rax, rax
0x180024cb6  jnz     loc_180024D40
0x180024cbc  test    rsi, rsi
0x180024cbf  jz      short loc_180024CE9
0x180024cc1  mov     rax, [rsi]
0x180024cc4  mov     rbx, [rax+8]
0x180024cc8  call    cs:__imp_GetLastError
0x180024ccf  nop     dword ptr [rax+rax+00h]
0x180024cd4  lea     rdx, aCreatefilemapp; "CreateFileMapping failed: %d"
0x180024cdb  mov     r8d, eax
0x180024cde  mov     rcx, rsi
0x180024ce1  mov     rax, rbx
0x180024ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ce9  mov     rcx, [rdi+10h]; lpBaseAddress
0x180024ced  test    rcx, rcx
0x180024cf0  jz      short loc_180024D02
0x180024cf2  call    cs:__imp_UnmapViewOfFile
0x180024cf9  nop     dword ptr [rax+rax+00h]
0x180024cfe  mov     [rdi+10h], r14
0x180024d02  mov     rcx, [rdi+8]; hObject
0x180024d06  test    rcx, rcx
0x180024d09  jz      short loc_180024D1B
0x180024d0b  call    cs:__imp_CloseHandle
0x180024d12  nop     dword ptr [rax+rax+00h]
0x180024d17  mov     [rdi+8], r14
0x180024d1b  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180024d1f  jz      loc_180024C5F
0x180024d25  mov     rcx, [rdi]; hObject
0x180024d28  call    cs:__imp_CloseHandle
0x180024d2f  nop     dword ptr [rax+rax+00h]
0x180024d34  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180024d3b  jmp     loc_180024C5F
0x180024d40  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], r14; lpBaseAddress
0x180024d45  mov     qword ptr [rsp+68h+dwCreationDisposition], r14; dwNumberOfBytesToMap
0x180024d4a  xor     r9d, r9d; dwFileOffsetLow
0x180024d4d  xor     r8d, r8d; dwFileOffsetHigh
0x180024d50  lea     edx, [r9+4]; dwDesiredAccess
0x180024d54  mov     rcx, rax; hFileMappingObject
0x180024d57  call    cs:__imp_MapViewOfFileEx
0x180024d5e  nop     dword ptr [rax+rax+00h]
0x180024d63  mov     rcx, rax
0x180024d66  mov     [rdi+10h], rax
0x180024d6a  test    rax, rax
0x180024d6d  jnz     short loc_180024D97
0x180024d6f  test    rsi, rsi
0x180024d72  jz      loc_180024CE9
0x180024d78  mov     rax, [rsi]
0x180024d7b  mov     rbx, [rax+8]
0x180024d7f  call    cs:__imp_GetLastError
0x180024d86  nop     dword ptr [rax+rax+00h]
0x180024d8b  lea     rdx, aMapviewoffilee; "MapViewOfFileEx failed: %d"
0x180024d92  jmp     loc_180024CDB
0x180024d97  mov     eax, 5A4Dh
0x180024d9c  cmp     [rcx], ax
0x180024d9f  jnz     short loc_180024DE9
0x180024da1  mov     eax, [rcx+3Ch]
0x180024da4  test    al, 3
0x180024da6  jnz     short loc_180024DE9
0x180024da8  cmp     eax, 0FFFFFFFFh
0x180024dab  jnb     short loc_180024DE9
0x180024dad  mov     edx, eax
0x180024daf  not     edx
0x180024db1  cmp     edx, 1Bh
0x180024db4  jb      short loc_180024DE9
0x180024db6  add     rcx, rax
0x180024db9  cmp     dword ptr [rcx], 4550h
0x180024dbf  jnz     short loc_180024DE9
0x180024dc1  mov     eax, 10Bh
0x180024dc6  cmp     [rcx+18h], ax
0x180024dca  jz      short loc_180024DE1
0x180024dcc  mov     eax, 20Bh
0x180024dd1  cmp     [rcx+18h], ax
0x180024dd5  jnz     short loc_180024DE9
0x180024dd7  cmp     edx, 108h
0x180024ddd  jbe     short loc_180024DE9
0x180024ddf  jmp     short loc_180024DEC
0x180024de1  cmp     edx, 0F8h
0x180024de7  ja      short loc_180024DEC
0x180024de9  mov     rcx, r14
0x180024dec  mov     eax, [rcx+50h]
0x180024def  mov     [rdi+18h], rax
0x180024df3  xor     eax, eax
0x180024df5  jmp     short loc_180024DFC
0x180024df7  mov     eax, 8000000Eh
0x180024dfc  lea     r11, [rsp+68h+var_18]
0x180024e01  mov     rbx, [r11+28h]
0x180024e05  mov     rbp, [r11+30h]
0x180024e09  mov     rsp, r11
0x180024e0c  pop     r14
0x180024e0e  pop     rdi
0x180024e0f  pop     rsi
0x180024e10  retn
```
