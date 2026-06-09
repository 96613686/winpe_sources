# XPerfCore::CFileMapping::MapExistingFileReadOnly2(ushort const *,bool,XPerfCore::IErrorMessage *)

- ea: `0x18002ca20`
- end: `0x18002cc94`
- name: `?MapExistingFileReadOnly2@CFileMapping@XPerfCore@@QEAAJPEBG_NPEAVIErrorMessage@2@@Z`
- size: `628`
- prototype: `signed int __fastcall(XPerfCore::CFileMapping *this, LPCWSTR lpFileName, char, struct XPerfCore::IErrorMessage *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180027e60`
- `0x180082a38`

## callees

- `0x18002ca20`
- `0x18002cca0`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cbb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cbb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002ca71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002ca71`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002cab3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002cab3`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18002ca7f`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18002ca7f`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x18002cbf3`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x18002cbf3`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x18002cbd7`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x18002cbd7`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002caf3`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002caf3`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18002cb1e`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18002cb1e`

## string_xrefs

- `0x18002cc13`: `CreateFile failed: %d`
- `0x18002cc3d`: `CreateFileMapping failed: %d`

## pseudocode

```c
signed int __fastcall XPerfCore::CFileMapping::MapExistingFileReadOnly2(
        XPerfCore::CFileMapping *this,
        LPCWSTR lpFileName,
        char a3,
        struct XPerfCore::IErrorMessage *a4)
{
  HANDLE CurrentProcess; // rax
  DWORD v9; // r8d
  HANDLE FileMappingW; // rax
  unsigned int *v11; // rcx
  char *v12; // rdx
  signed int result; // eax
  __int64 v14; // rax
  unsigned int v15; // r8d
  __int16 v16; // ax
  void (*v17)(struct XPerfCore::IErrorMessage *, const wchar_t *, ...); // rbx
  __int64 LastError; // r8
  void (__fastcall *v19)(struct XPerfCore::IErrorMessage *, const wchar_t *, _QWORD); // rdi
  DWORD v20; // eax
  const wchar_t *v21; // rdx
  PVOID OldValue[5]; // [rsp+40h] [rbp-28h] BYREF
  WINBOOL Wow64Process; // [rsp+70h] [rbp+8h] BYREF

  OldValue[1] = (PVOID)-2LL;
  if ( *(_OWORD *)this != 0xFFFFFFFFFFFFFFFFuLL || *((_QWORD *)this + 2) )
    return -2147483634;
  Wow64Process = 0;
  OldValue[0] = 0;
  CurrentProcess = GetCurrentProcess();
  if ( IsWow64Process(CurrentProcess, &Wow64Process) && Wow64Process == 1 )
    Wow64Process = Wow64DisableWow64FsRedirection(OldValue);
  *(_QWORD *)this = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( Wow64Process )
    Wow64RevertWow64FsRedirection(OldValue[0]);
  if ( *(_QWORD *)this == -1 )
  {
    if ( a4 )
    {
      v17 = *(void (**)(struct XPerfCore::IErrorMessage *, const wchar_t *, ...))(*(_QWORD *)a4 + 8LL);
      LastError = GetLastError();
      v17(a4, L"CreateFile failed: %d", LastError);
    }
    goto LABEL_24;
  }
  v9 = 285212674;
  if ( !a3 )
    v9 = 2;
  FileMappingW = CreateFileMappingW(*(HANDLE *)this, 0, v9, 0, 0, 0);
  *((_QWORD *)this + 1) = FileMappingW;
  if ( FileMappingW )
  {
    v11 = (unsigned int *)MapViewOfFileEx(FileMappingW, 4u, 0, 0, 0, 0);
    *((_QWORD *)this + 2) = v11;
    if ( v11 )
    {
      if ( *(_WORD *)v11 == 23117 )
      {
        v14 = v11[15];
        if ( (v14 & 3) == 0 && (_DWORD)v14 != -1 )
        {
          v15 = ~(_DWORD)v14;
          if ( (unsigned int)~(_DWORD)v14 >= 0x1B )
          {
            v12 = (char *)v11 + v14;
            if ( *(unsigned int *)((char *)v11 + v14) == 17744 )
            {
              v16 = *((_WORD *)v12 + 12);
              if ( v16 == 267 )
              {
                if ( v15 > 0xF8 )
                  goto LABEL_13;
              }
              else if ( v16 == 523 && v15 > 0x108 )
              {
                goto LABEL_13;
              }
            }
          }
        }
      }
      v12 = 0;
LABEL_13:
      *((_QWORD *)this + 3) = *((unsigned int *)v12 + 20);
      return 0;
    }
    if ( !a4 )
      goto LABEL_23;
    v19 = *(void (__fastcall **)(struct XPerfCore::IErrorMessage *, const wchar_t *, _QWORD))(*(_QWORD *)a4 + 8LL);
    v20 = GetLastError();
    v21 = L"MapViewOfFileEx failed: %d";
    goto LABEL_32;
  }
  if ( a4 )
  {
    v19 = *(void (__fastcall **)(struct XPerfCore::IErrorMessage *, const wchar_t *, _QWORD))(*(_QWORD *)a4 + 8LL);
    v20 = GetLastError();
    v21 = L"CreateFileMapping failed: %d";
LABEL_32:
    v19(a4, v21, v20);
  }
LABEL_23:
  XPerfCore::CFileMapping::Cleanup(this);
LABEL_24:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18002ca20  mov     rax, rsp
0x18002ca23  push    rsi
0x18002ca24  push    rdi
0x18002ca25  push    r14
0x18002ca27  sub     rsp, 50h
0x18002ca2b  mov     qword ptr [rax-20h], 0FFFFFFFFFFFFFFFEh
0x18002ca33  mov     [rax+10h], rbx
0x18002ca37  mov     [rax+18h], rbp
0x18002ca3b  mov     r14, r9
0x18002ca3e  movzx   esi, r8b
0x18002ca42  mov     rdi, rdx
0x18002ca45  mov     rbx, rcx
0x18002ca48  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x18002ca4c  jnz     loc_18002CC8A
0x18002ca52  cmp     qword ptr [rcx+8], 0
0x18002ca57  jnz     loc_18002CC8A
0x18002ca5d  cmp     qword ptr [rcx+10h], 0
0x18002ca62  jnz     loc_18002CC8A
0x18002ca68  xor     ebp, ebp
0x18002ca6a  mov     [rax+8], ebp
0x18002ca6d  mov     [rax-28h], rbp
0x18002ca71  call    cs:__imp_GetCurrentProcess
0x18002ca77  mov     rcx, rax; hProcess
0x18002ca7a  lea     rdx, [rsp+68h+Wow64Process]; Wow64Process
0x18002ca7f  call    cs:__imp_IsWow64Process
0x18002ca85  test    eax, eax
0x18002ca87  jnz     loc_18002CBC7
0x18002ca8d  mov     [rsp+68h+hTemplateFile], rbp; hTemplateFile
0x18002ca92  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002ca9a  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18002caa2  xor     r9d, r9d; lpSecurityAttributes
0x18002caa5  mov     edx, 80000000h; dwDesiredAccess
0x18002caaa  mov     r8d, 1; dwShareMode
0x18002cab0  mov     rcx, rdi; lpFileName
0x18002cab3  call    cs:__imp_CreateFileW
0x18002cab9  mov     [rbx], rax
0x18002cabc  cmp     [rsp+68h+Wow64Process], ebp
0x18002cac0  jnz     loc_18002CBEE
0x18002cac6  mov     rcx, [rbx]; hFile
0x18002cac9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002cacd  jz      loc_18002CBFE
0x18002cad3  mov     eax, 2
0x18002cad8  mov     r8d, 11000002h
0x18002cade  test    sil, sil
0x18002cae1  cmovz   r8d, eax; flProtect
0x18002cae5  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rbp; lpName
0x18002caea  mov     [rsp+68h+dwCreationDisposition], ebp; dwMaximumSizeLow
0x18002caee  xor     r9d, r9d; dwMaximumSizeHigh
0x18002caf1  xor     edx, edx; lpFileMappingAttributes
0x18002caf3  call    cs:__imp_CreateFileMappingW
0x18002caf9  mov     [rbx+8], rax
0x18002cafd  test    rax, rax
0x18002cb00  jz      loc_18002CC27
0x18002cb06  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rbp; lpBaseAddress
0x18002cb0b  mov     qword ptr [rsp+68h+dwCreationDisposition], rbp; dwNumberOfBytesToMap
0x18002cb10  xor     r9d, r9d; dwFileOffsetLow
0x18002cb13  xor     r8d, r8d; dwFileOffsetHigh
0x18002cb16  mov     edx, 4; dwDesiredAccess
0x18002cb1b  mov     rcx, rax; hFileMappingObject
0x18002cb1e  call    cs:__imp_MapViewOfFileEx
0x18002cb24  mov     rcx, rax
0x18002cb27  mov     [rbx+10h], rax
0x18002cb2b  test    rax, rax
0x18002cb2e  jz      loc_18002CC6D
0x18002cb34  mov     eax, 5A4Dh
0x18002cb39  cmp     [rcx], ax
0x18002cb3c  jz      short loc_18002CB60
0x18002cb3e  mov     rdx, rbp
0x18002cb41  mov     eax, [rdx+50h]
0x18002cb44  mov     [rbx+18h], rax
0x18002cb48  xor     eax, eax
0x18002cb4a  mov     rbx, [rsp+68h+arg_8]
0x18002cb4f  mov     rbp, [rsp+68h+arg_10]
0x18002cb57  add     rsp, 50h
0x18002cb5b  pop     r14
0x18002cb5d  pop     rdi
0x18002cb5e  pop     rsi
0x18002cb5f  retn
0x18002cb60  mov     eax, [rcx+3Ch]
0x18002cb63  test    al, 3
0x18002cb65  jnz     short loc_18002CB3E
0x18002cb67  cmp     eax, 0FFFFFFFFh
0x18002cb6a  jnb     short loc_18002CB3E
0x18002cb6c  mov     r8d, eax
0x18002cb6f  not     r8d
0x18002cb72  cmp     r8d, 1Bh
0x18002cb76  jb      short loc_18002CB3E
0x18002cb78  lea     rdx, [rcx+rax]
0x18002cb7c  cmp     dword ptr [rdx], 4550h
0x18002cb82  jnz     short loc_18002CB3E
0x18002cb84  movzx   eax, word ptr [rdx+18h]
0x18002cb88  mov     ecx, 10Bh
0x18002cb8d  cmp     ax, cx
0x18002cb90  jz      loc_18002CC78
0x18002cb96  mov     ecx, 20Bh
0x18002cb9b  cmp     ax, cx
0x18002cb9e  jnz     short loc_18002CB3E
0x18002cba0  cmp     r8d, 108h
0x18002cba7  jbe     short loc_18002CB3E
0x18002cba9  jmp     short loc_18002CB41
0x18002cbab  mov     rcx, rbx; this
0x18002cbae  call    ?Cleanup@CFileMapping@XPerfCore@@AEAAXXZ; XPerfCore::CFileMapping::Cleanup(void)
0x18002cbb3  call    cs:__imp_GetLastError
0x18002cbb9  test    eax, eax
0x18002cbbb  jle     short loc_18002CB4A
0x18002cbbd  movzx   eax, ax
0x18002cbc0  or      eax, 80070000h
0x18002cbc5  jmp     short loc_18002CB4A
0x18002cbc7  cmp     [rsp+68h+Wow64Process], 1
0x18002cbcc  jnz     loc_18002CA8D
0x18002cbd2  lea     rcx, [rsp+68h+OldValue]; OldValue
0x18002cbd7  call    cs:__imp_Wow64DisableWow64FsRedirection
0x18002cbdd  test    eax, eax
0x18002cbdf  jnz     loc_18002CA8D
0x18002cbe5  mov     [rsp+68h+Wow64Process], ebp
0x18002cbe9  jmp     loc_18002CA8D
0x18002cbee  mov     rcx, [rsp+68h+OldValue]; OlValue
0x18002cbf3  call    cs:__imp_Wow64RevertWow64FsRedirection
0x18002cbf9  jmp     loc_18002CAC6
0x18002cbfe  test    r14, r14
0x18002cc01  jz      short loc_18002CBB3
0x18002cc03  mov     rax, [r14]
0x18002cc06  mov     rbx, [rax+8]
0x18002cc0a  call    cs:__imp_GetLastError
0x18002cc10  mov     r8d, eax
0x18002cc13  lea     rdx, aCreatefileFail; "CreateFile failed: %d"
0x18002cc1a  mov     rcx, r14
0x18002cc1d  mov     rax, rbx
0x18002cc20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc25  jmp     short loc_18002CBB3
0x18002cc27  test    r14, r14
0x18002cc2a  jz      loc_18002CBAB
0x18002cc30  mov     rax, [r14]
0x18002cc33  mov     rdi, [rax+8]
0x18002cc37  call    cs:__imp_GetLastError
0x18002cc3d  lea     rdx, aCreatefilemapp; "CreateFileMapping failed: %d"
0x18002cc44  jmp     short loc_18002CC5A
0x18002cc46  mov     rax, [r14]
0x18002cc49  mov     rdi, [rax+8]
0x18002cc4d  call    cs:__imp_GetLastError
0x18002cc53  lea     rdx, aMapviewoffilee; "MapViewOfFileEx failed: %d"
0x18002cc5a  mov     r8d, eax
0x18002cc5d  mov     rcx, r14
0x18002cc60  mov     rax, rdi
0x18002cc63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc68  jmp     loc_18002CBAB
0x18002cc6d  test    r14, r14
0x18002cc70  jz      loc_18002CBAB
0x18002cc76  jmp     short loc_18002CC46
0x18002cc78  cmp     r8d, 0F8h
0x18002cc7f  ja      loc_18002CB41
0x18002cc85  jmp     loc_18002CB3E
0x18002cc8a  mov     eax, 8000000Eh
0x18002cc8f  jmp     loc_18002CB4A
```
