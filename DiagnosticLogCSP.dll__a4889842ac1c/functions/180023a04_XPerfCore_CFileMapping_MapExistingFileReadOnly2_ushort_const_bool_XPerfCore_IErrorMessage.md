# XPerfCore::CFileMapping::MapExistingFileReadOnly2(ushort const *,bool,XPerfCore::IErrorMessage *)

- ea: `0x180023a04`
- end: `0x180023c65`
- name: `?MapExistingFileReadOnly2@CFileMapping@XPerfCore@@QEAAJPEBG_NPEAVIErrorMessage@2@@Z`
- size: `609`
- prototype: `int(XPerfCore::CFileMapping *__hidden this, const unsigned __int16 *, bool, struct XPerfCore::IErrorMessage *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180020204`
- `0x1800347ec`

## callees

- `0x180023a04`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023a4c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023a4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ad0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023aeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023b44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023bd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ad0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023aeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023b44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023bd9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023b7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023b92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023b7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023b92`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180023aa3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180023aa3`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180023b68`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180023b68`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x180023bbb`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x180023bbb`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180023b29`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180023b29`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x180023ab8`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x180023ab8`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180023a5a`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180023a5a`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x180023a70`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x180023a70`

## string_xrefs

- `0x180023ad9`: `CreateFile failed: %d`
- `0x180023b4a`: `CreateFileMapping failed: %d`

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
0x180023a04  mov     rax, rsp
0x180023a07  mov     [rax+10h], rbx
0x180023a0b  mov     [rax+18h], rbp
0x180023a0f  push    rsi
0x180023a10  push    rdi
0x180023a11  push    r14
0x180023a13  sub     rsp, 50h
0x180023a17  mov     rsi, r9
0x180023a1a  mov     bpl, r8b
0x180023a1d  mov     rbx, rdx
0x180023a20  mov     rdi, rcx
0x180023a23  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x180023a27  jnz     loc_180023C4B
0x180023a2d  xor     r14d, r14d
0x180023a30  cmp     [rcx+8], r14
0x180023a34  jnz     loc_180023C4B
0x180023a3a  cmp     [rcx+10h], r14
0x180023a3e  jnz     loc_180023C4B
0x180023a44  mov     [rax+8], r14d
0x180023a48  mov     [rax-28h], r14
0x180023a4c  call    cs:__imp_GetCurrentProcess
0x180023a52  mov     rcx, rax; hProcess
0x180023a55  lea     rdx, [rsp+68h+Wow64Process]; Wow64Process
0x180023a5a  call    cs:__imp_IsWow64Process
0x180023a60  test    eax, eax
0x180023a62  jz      short loc_180023A7F
0x180023a64  cmp     [rsp+68h+Wow64Process], 1
0x180023a69  jnz     short loc_180023A7F
0x180023a6b  lea     rcx, [rsp+68h+OldValue]; OldValue
0x180023a70  call    cs:__imp_Wow64DisableWow64FsRedirection
0x180023a76  test    eax, eax
0x180023a78  jnz     short loc_180023A7F
0x180023a7a  mov     [rsp+68h+Wow64Process], r14d
0x180023a7f  mov     [rsp+68h+hTemplateFile], r14; hTemplateFile
0x180023a84  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180023a8c  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180023a94  xor     r9d, r9d; lpSecurityAttributes
0x180023a97  mov     edx, 80000000h; dwDesiredAccess
0x180023a9c  lea     r8d, [r9+1]; dwShareMode
0x180023aa0  mov     rcx, rbx; lpFileName
0x180023aa3  call    cs:__imp_CreateFileW
0x180023aa9  mov     [rdi], rax
0x180023aac  cmp     [rsp+68h+Wow64Process], r14d
0x180023ab1  jz      short loc_180023ABE
0x180023ab3  mov     rcx, [rsp+68h+OldValue]; OlValue
0x180023ab8  call    cs:__imp_Wow64RevertWow64FsRedirection
0x180023abe  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180023ac2  jnz     short loc_180023B06
0x180023ac4  test    rsi, rsi
0x180023ac7  jz      short loc_180023AEB
0x180023ac9  mov     rax, [rsi]
0x180023acc  mov     rbx, [rax+8]
0x180023ad0  call    cs:__imp_GetLastError
0x180023ad6  mov     r8d, eax
0x180023ad9  lea     rdx, aCreatefileFail; "CreateFile failed: %d"
0x180023ae0  mov     rcx, rsi
0x180023ae3  mov     rax, rbx
0x180023ae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023aeb  call    cs:__imp_GetLastError
0x180023af1  test    eax, eax
0x180023af3  jle     loc_180023C50
0x180023af9  movzx   eax, ax
0x180023afc  or      eax, 80070000h
0x180023b01  jmp     loc_180023C50
0x180023b06  neg     bpl
0x180023b09  sbb     r8d, r8d
0x180023b0c  and     r8d, 11000000h
0x180023b13  add     r8d, 2; flProtect
0x180023b17  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], r14; lpName
0x180023b1c  mov     [rsp+68h+dwCreationDisposition], r14d; dwMaximumSizeLow
0x180023b21  xor     r9d, r9d; dwMaximumSizeHigh
0x180023b24  xor     edx, edx; lpFileMappingAttributes
0x180023b26  mov     rcx, [rdi]; hFile
0x180023b29  call    cs:__imp_CreateFileMappingW
0x180023b2f  mov     [rdi+8], rax
0x180023b33  test    rax, rax
0x180023b36  jnz     short loc_180023BA4
0x180023b38  test    rsi, rsi
0x180023b3b  jz      short loc_180023B5F
0x180023b3d  mov     rax, [rsi]
0x180023b40  mov     rbx, [rax+8]
0x180023b44  call    cs:__imp_GetLastError
0x180023b4a  lea     rdx, aCreatefilemapp; "CreateFileMapping failed: %d"
0x180023b51  mov     r8d, eax
0x180023b54  mov     rcx, rsi
0x180023b57  mov     rax, rbx
0x180023b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b5f  mov     rcx, [rdi+10h]; lpBaseAddress
0x180023b63  test    rcx, rcx
0x180023b66  jz      short loc_180023B72
0x180023b68  call    cs:__imp_UnmapViewOfFile
0x180023b6e  mov     [rdi+10h], r14
0x180023b72  mov     rcx, [rdi+8]; hObject
0x180023b76  test    rcx, rcx
0x180023b79  jz      short loc_180023B85
0x180023b7b  call    cs:__imp_CloseHandle
0x180023b81  mov     [rdi+8], r14
0x180023b85  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180023b89  jz      loc_180023AEB
0x180023b8f  mov     rcx, [rdi]; hObject
0x180023b92  call    cs:__imp_CloseHandle
0x180023b98  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180023b9f  jmp     loc_180023AEB
0x180023ba4  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], r14; lpBaseAddress
0x180023ba9  mov     qword ptr [rsp+68h+dwCreationDisposition], r14; dwNumberOfBytesToMap
0x180023bae  xor     r9d, r9d; dwFileOffsetLow
0x180023bb1  xor     r8d, r8d; dwFileOffsetHigh
0x180023bb4  lea     edx, [r9+4]; dwDesiredAccess
0x180023bb8  mov     rcx, rax; hFileMappingObject
0x180023bbb  call    cs:__imp_MapViewOfFileEx
0x180023bc1  mov     rcx, rax
0x180023bc4  mov     [rdi+10h], rax
0x180023bc8  test    rax, rax
0x180023bcb  jnz     short loc_180023BEB
0x180023bcd  test    rsi, rsi
0x180023bd0  jz      short loc_180023B5F
0x180023bd2  mov     rax, [rsi]
0x180023bd5  mov     rbx, [rax+8]
0x180023bd9  call    cs:__imp_GetLastError
0x180023bdf  lea     rdx, aMapviewoffilee; "MapViewOfFileEx failed: %d"
0x180023be6  jmp     loc_180023B51
0x180023beb  mov     eax, 5A4Dh
0x180023bf0  cmp     [rcx], ax
0x180023bf3  jnz     short loc_180023C3D
0x180023bf5  mov     eax, [rcx+3Ch]
0x180023bf8  test    al, 3
0x180023bfa  jnz     short loc_180023C3D
0x180023bfc  cmp     eax, 0FFFFFFFFh
0x180023bff  jnb     short loc_180023C3D
0x180023c01  mov     edx, eax
0x180023c03  not     edx
0x180023c05  cmp     edx, 1Bh
0x180023c08  jb      short loc_180023C3D
0x180023c0a  add     rcx, rax
0x180023c0d  cmp     dword ptr [rcx], 4550h
0x180023c13  jnz     short loc_180023C3D
0x180023c15  mov     eax, 10Bh
0x180023c1a  cmp     [rcx+18h], ax
0x180023c1e  jz      short loc_180023C35
0x180023c20  mov     eax, 20Bh
0x180023c25  cmp     [rcx+18h], ax
0x180023c29  jnz     short loc_180023C3D
0x180023c2b  cmp     edx, 108h
0x180023c31  jbe     short loc_180023C3D
0x180023c33  jmp     short loc_180023C40
0x180023c35  cmp     edx, 0F8h
0x180023c3b  ja      short loc_180023C40
0x180023c3d  mov     rcx, r14
0x180023c40  mov     eax, [rcx+50h]
0x180023c43  mov     [rdi+18h], rax
0x180023c47  xor     eax, eax
0x180023c49  jmp     short loc_180023C50
0x180023c4b  mov     eax, 8000000Eh
0x180023c50  lea     r11, [rsp+68h+var_18]
0x180023c55  mov     rbx, [r11+28h]
0x180023c59  mov     rbp, [r11+30h]
0x180023c5d  mov     rsp, r11
0x180023c60  pop     r14
0x180023c62  pop     rdi
0x180023c63  pop     rsi
0x180023c64  retn
```
