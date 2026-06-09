# MoveAndSecureFile(wchar_t const *,wchar_t const *,int,int)

- ea: `0x140044018`
- end: `0x1400442ce`
- name: `?MoveAndSecureFile@@YAJPEB_W0HH@Z`
- size: `694`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14003cf94`

## callees

- `0x14000fa08`
- `0x140034d9c`
- `0x140044018`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400440c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004415c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400441d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400440c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004415c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400441d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400441b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400441b1`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x140044090`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x14004426c`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x140044090`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x14004426c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14004414c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14004414c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14004422e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14004422e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400440bf`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400440bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400440a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400442b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400440a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400442b1`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1400441c3`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1400441c3`

## string_xrefs

- `0x1400440ec`: `ConvertStringSecurityDescriptorToSecurityDescriptor failed`
- `0x1400440fc`: `MoveAndSecureFile`
- `0x140044194`: `MoveAndSecureFile`
- `0x14004420e`: `MoveAndSecureFile`
- `0x14004424d`: `MoveAndSecureFile`
- `0x140044290`: `MoveAndSecureFile`
- `0x140044075`: `Overwrite is false and file exists`
- `0x140044184`: `Failed to create the file %ws for write`
- `0x1400441fe`: `MoveFileExW from %ws to %ws failed`
- `0x14004423d`: `Temporary dest file %ws deleted due to error in MoveAndSecureFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MoveAndSecureFile(const wchar_t *a1, const wchar_t *a2, int a3)
{
  bool v6; // al
  bool v7; // si
  signed int v8; // ebx
  const char *v9; // rax
  __int64 v10; // rdx
  HLOCAL v11; // rcx
  signed int v12; // eax
  HANDLE v13; // rax
  signed int v14; // eax
  signed int LastError; // eax
  wil::details *dwCreationDisposition; // [rsp+20h] [rbp-40h]
  wil::details *dwCreationDispositiona; // [rsp+20h] [rbp-40h]
  wil::details *dwCreationDispositionb; // [rsp+20h] [rbp-40h]
  const char *hTemplateFile; // [rsp+30h] [rbp-30h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+78h] [rbp+18h]
  HLOCAL hMem; // [rsp+80h] [rbp+20h] BYREF

  hMem = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( !a1 || !a2 )
  {
    v9 = "Invalid params";
    v8 = -2147024809;
    v10 = 68;
    goto LABEL_30;
  }
  v6 = UtilFileExists(a2);
  v7 = v6;
  if ( !a3 && v6 )
  {
    v8 = -2147024713;
    v9 = "Overwrite is false and file exists";
    v10 = 77;
LABEL_30:
    LODWORD(dwCreationDisposition) = v8;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelhelper.cpp",
      "MoveAndSecureFile",
      dwCreationDisposition,
      (int)v9,
      hTemplateFile);
    goto LABEL_31;
  }
  SetFileAttributesW(a2, 0x80u);
  v11 = hMem;
  hMem = 0;
  if ( v11 )
    LocalFree(v11);
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:P(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)", 1u, &hMem, 0) )
  {
    SecurityAttributes.nLength = 24;
    SecurityAttributes.lpSecurityDescriptor = hMem;
    v13 = CreateFileW(a2, 0x40040000u, 0, &SecurityAttributes, 2u, 0x80u, 0);
    if ( (unsigned __int64)v13 + 1 > 1 )
    {
      CloseHandle(v13);
      if ( MoveFileExW(a1, a2, 0xBu) )
      {
        SetFileAttributesW(a2, 0x80u);
        v8 = 0;
        goto LABEL_31;
      }
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( v8 >= 0 )
        v8 = -2147467259;
      LODWORD(dwCreationDispositionb) = v8;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0x82,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelhelper.cpp",
        "MoveAndSecureFile",
        dwCreationDispositionb,
        (int)"MoveFileExW from %ws to %ws failed",
        (const char *)a1,
        a2);
    }
    else
    {
      v14 = GetLastError();
      v8 = v14;
      if ( v14 > 0 )
        v8 = (unsigned __int16)v14 | 0x80070000;
      if ( v8 >= 0 )
        v8 = -2147467259;
      LODWORD(dwCreationDispositionb) = v8;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0x77,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelhelper.cpp",
        "MoveAndSecureFile",
        dwCreationDispositionb,
        (int)"Failed to create the file %ws for write",
        (const char *)a2);
    }
  }
  else
  {
    v12 = GetLastError();
    v8 = v12;
    if ( v12 > 0 )
      v8 = (unsigned __int16)v12 | 0x80070000;
    if ( v8 >= 0 )
      v8 = -2147467259;
    LODWORD(dwCreationDisposition) = v8;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelhelper.cpp",
      "MoveAndSecureFile",
      dwCreationDisposition,
      (int)"ConvertStringSecurityDescriptorToSecurityDescriptor failed",
      hTemplateFile);
  }
  if ( !v7 )
  {
    DeleteFileW(a2);
    LODWORD(dwCreationDispositiona) = v8;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x98,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelhelper.cpp",
      "MoveAndSecureFile",
      dwCreationDispositiona,
      (int)"Temporary dest file %ws deleted due to error in MoveAndSecureFile",
      (const char *)a2);
  }
LABEL_31:
  if ( hMem )
    LocalFree(hMem);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140044018  mov     [rsp-18h+arg_8], rbx
0x14004401d  mov     [rsp-18h+arg_10], rsi
0x140044022  push    rbp
0x140044023  push    rdi
0x140044024  push    r14
0x140044026  mov     rbp, rsp
0x140044029  sub     rsp, 60h
0x14004402d  mov     ebx, r8d
0x140044030  mov     rdi, rdx
0x140044033  mov     r14, rcx
0x140044036  mov     [rbp+hMem], 0
0x14004403e  xorps   xmm0, xmm0
0x140044041  xor     eax, eax
0x140044043  movups  xmmword ptr [rbp+SecurityAttributes.nLength], xmm0
0x140044047  mov     qword ptr [rbp+SecurityAttributes.bInheritHandle], rax
0x14004404b  test    rcx, rcx
0x14004404e  jz      loc_140044276
0x140044054  test    rdx, rdx
0x140044057  jz      loc_140044276
0x14004405d  mov     rcx, rdx; wchar_t *
0x140044060  call    ?UtilFileExists@@YA_NPEB_W@Z; UtilFileExists(wchar_t const *)
0x140044065  mov     sil, al
0x140044068  test    ebx, ebx
0x14004406a  jnz     short loc_140044086
0x14004406c  test    al, al
0x14004406e  jz      short loc_140044086
0x140044070  mov     ebx, 800700B7h
0x140044075  lea     rax, aOverwriteIsFal; "Overwrite is false and file exists"
0x14004407c  mov     edx, 4Dh ; 'M'
0x140044081  jmp     loc_140044287
0x140044086  mov     ebx, 80h
0x14004408b  mov     edx, ebx; dwFileAttributes
0x14004408d  mov     rcx, rdi; lpFileName
0x140044090  call    cs:__imp_SetFileAttributesW
0x140044096  mov     rcx, [rbp+hMem]; hMem
0x14004409a  mov     [rbp+hMem], 0
0x1400440a2  test    rcx, rcx
0x1400440a5  jz      short loc_1400440AD
0x1400440a7  call    cs:__imp_LocalFree
0x1400440ad  xor     r9d, r9d; SecurityDescriptorSize
0x1400440b0  lea     r8, [rbp+hMem]; SecurityDescriptor
0x1400440b4  lea     edx, [r9+1]; StringSDRevision
0x1400440b8  lea     rcx, StringSecurityDescriptor; "D:P(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)"
0x1400440bf  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1400440c5  test    eax, eax
0x1400440c7  jnz     short loc_140044119
0x1400440c9  call    cs:__imp_GetLastError
0x1400440cf  mov     ebx, eax
0x1400440d1  test    eax, eax
0x1400440d3  jle     short loc_1400440DE
0x1400440d5  movzx   ebx, ax
0x1400440d8  or      ebx, 80070000h
0x1400440de  mov     eax, 80004005h
0x1400440e3  test    ebx, ebx
0x1400440e5  cmovns  ebx, eax
0x1400440e8  mov     rcx, [rbp+18h]; this
0x1400440ec  lea     rax, aConvertstrings; "ConvertStringSecurityDescriptorToSecuri"...
0x1400440f3  mov     qword ptr [rsp+60h+dwFlagsAndAttributes], rax; int
0x1400440f8  mov     dword ptr [rsp+60h+dwCreationDisposition], ebx; wil::details *
0x1400440fc  lea     r9, aMoveandsecuref_0; "MoveAndSecureFile"
0x140044103  lea     r8, aOnecoreWindows_3; "onecore\\windows\\feedback\\core\\werfa"...
0x14004410a  mov     edx, 64h ; 'd'; void *
0x14004410f  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140044114  jmp     loc_140044226
0x140044119  mov     [rbp+SecurityAttributes.nLength], 18h
0x140044120  mov     rax, [rbp+hMem]
0x140044124  mov     [rbp+SecurityAttributes.lpSecurityDescriptor], rax
0x140044128  mov     [rsp+60h+hTemplateFile], 0; hTemplateFile
0x140044131  mov     [rsp+60h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x140044135  mov     dword ptr [rsp+60h+dwCreationDisposition], 2; dwCreationDisposition
0x14004413d  lea     r9, [rbp+SecurityAttributes]; lpSecurityAttributes
0x140044141  xor     r8d, r8d; dwShareMode
0x140044144  mov     edx, 40040000h; dwDesiredAccess
0x140044149  mov     rcx, rdi; lpFileName
0x14004414c  call    cs:__imp_CreateFileW
0x140044152  lea     rcx, [rax+1]
0x140044156  cmp     rcx, 1
0x14004415a  ja      short loc_1400441AE
0x14004415c  call    cs:__imp_GetLastError
0x140044162  mov     ebx, eax
0x140044164  test    eax, eax
0x140044166  jle     short loc_140044171
0x140044168  movzx   ebx, ax
0x14004416b  or      ebx, 80070000h
0x140044171  mov     eax, 80004005h
0x140044176  test    ebx, ebx
0x140044178  cmovns  ebx, eax
0x14004417b  mov     rcx, [rbp+18h]; this
0x14004417f  mov     [rsp+60h+hTemplateFile], rdi; char *
0x140044184  lea     rax, aFailedToCreate; "Failed to create the file %ws for write"
0x14004418b  mov     qword ptr [rsp+60h+dwFlagsAndAttributes], rax; int
0x140044190  mov     dword ptr [rsp+60h+dwCreationDisposition], ebx; wil::details *
0x140044194  lea     r9, aMoveandsecuref_0; "MoveAndSecureFile"
0x14004419b  lea     r8, aOnecoreWindows_3; "onecore\\windows\\feedback\\core\\werfa"...
0x1400441a2  mov     edx, 77h ; 'w'; void *
0x1400441a7  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400441ac  jmp     short loc_140044226
0x1400441ae  mov     rcx, rax; hObject
0x1400441b1  call    cs:__imp_CloseHandle
0x1400441b7  mov     r8d, 0Bh; dwFlags
0x1400441bd  mov     rdx, rdi; lpNewFileName
0x1400441c0  mov     rcx, r14; lpExistingFileName
0x1400441c3  call    cs:__imp_MoveFileExW
0x1400441c9  test    eax, eax
0x1400441cb  jnz     loc_140044267
0x1400441d1  call    cs:__imp_GetLastError
0x1400441d7  mov     ebx, eax
0x1400441d9  test    eax, eax
0x1400441db  jle     short loc_1400441E6
0x1400441dd  movzx   ebx, ax
0x1400441e0  or      ebx, 80070000h
0x1400441e6  mov     eax, 80004005h
0x1400441eb  test    ebx, ebx
0x1400441ed  cmovns  ebx, eax
0x1400441f0  mov     rcx, [rbp+18h]; this
0x1400441f4  mov     [rsp+60h+var_28], rdi
0x1400441f9  mov     [rsp+60h+hTemplateFile], r14; char *
0x1400441fe  lea     rax, aMovefileexwFro; "MoveFileExW from %ws to %ws failed"
0x140044205  mov     qword ptr [rsp+60h+dwFlagsAndAttributes], rax; int
0x14004420a  mov     dword ptr [rsp+60h+dwCreationDisposition], ebx; wil::details *
0x14004420e  lea     r9, aMoveandsecuref_0; "MoveAndSecureFile"
0x140044215  lea     r8, aOnecoreWindows_3; "onecore\\windows\\feedback\\core\\werfa"...
0x14004421c  mov     edx, 82h; void *
0x140044221  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140044226  test    sil, sil
0x140044229  jnz     short loc_1400442A8
0x14004422b  mov     rcx, rdi; lpFileName
0x14004422e  call    cs:__imp_DeleteFileW
0x140044234  mov     rcx, [rbp+18h]; this
0x140044238  mov     [rsp+60h+hTemplateFile], rdi; char *
0x14004423d  lea     rax, aTemporaryDestF; "Temporary dest file %ws deleted due to "...
0x140044244  mov     qword ptr [rsp+60h+dwFlagsAndAttributes], rax; int
0x140044249  mov     dword ptr [rsp+60h+dwCreationDisposition], ebx; wil::details *
0x14004424d  lea     r9, aMoveandsecuref_0; "MoveAndSecureFile"
0x140044254  lea     r8, aOnecoreWindows_3; "onecore\\windows\\feedback\\core\\werfa"...
0x14004425b  mov     edx, 98h; void *
0x140044260  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140044265  jmp     short loc_1400442A8
0x140044267  mov     edx, ebx; dwFileAttributes
0x140044269  mov     rcx, rdi; lpFileName
0x14004426c  call    cs:__imp_SetFileAttributesW
0x140044272  xor     ebx, ebx
0x140044274  jmp     short loc_1400442A8
0x140044276  lea     rax, aInvalidParams; "Invalid params"
0x14004427d  mov     ebx, 80070057h
0x140044282  mov     edx, 44h ; 'D'; void *
0x140044287  mov     qword ptr [rsp+60h+dwFlagsAndAttributes], rax; int
0x14004428c  mov     dword ptr [rsp+60h+dwCreationDisposition], ebx; wil::details *
0x140044290  lea     r9, aMoveandsecuref_0; "MoveAndSecureFile"
0x140044297  lea     r8, aOnecoreWindows_3; "onecore\\windows\\feedback\\core\\werfa"...
0x14004429e  mov     rcx, [rbp+18h]; this
0x1400442a2  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400442a7  nop
0x1400442a8  mov     rcx, [rbp+hMem]; hMem
0x1400442ac  test    rcx, rcx
0x1400442af  jz      short loc_1400442B7
0x1400442b1  call    cs:__imp_LocalFree
0x1400442b7  mov     eax, ebx
0x1400442b9  lea     r11, [rsp+60h+var_s0]
0x1400442be  mov     rbx, [r11+28h]
0x1400442c2  mov     rsi, [r11+30h]
0x1400442c6  mov     rsp, r11
0x1400442c9  pop     r14
0x1400442cb  pop     rdi
0x1400442cc  pop     rbp
0x1400442cd  retn
```
