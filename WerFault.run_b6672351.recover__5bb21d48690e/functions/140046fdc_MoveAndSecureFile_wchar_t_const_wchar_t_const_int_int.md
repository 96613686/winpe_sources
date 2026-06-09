# MoveAndSecureFile(wchar_t const *,wchar_t const *,int,int)

- ea: `0x140046fdc`
- end: `0x1400472da`
- name: `?MoveAndSecureFile@@YAJPEB_W0HH@Z`
- size: `766`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14003f95c`

## callees

- `0x140010034`
- `0x1400167a4`
- `0x1400372dc`
- `0x140046fdc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140047084`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004712e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400471bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140047084`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004712e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400471bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047190`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047190`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x14004704b`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x14004726f`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x14004704b`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x14004726f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140047118`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140047118`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140047227`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140047227`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140047074`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140047074`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400472c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400472c2`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1400471a8`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1400471a8`

## string_xrefs

- `0x1400470b1`: `ConvertStringSecurityDescriptorToSecurityDescriptor failed`
- `0x1400470c1`: `MoveAndSecureFile`
- `0x140047170`: `MoveAndSecureFile`
- `0x140047203`: `MoveAndSecureFile`
- `0x140047250`: `MoveAndSecureFile`
- `0x140047299`: `MoveAndSecureFile`
- `0x140047030`: `Overwrite is false and file exists`
- `0x140047160`: `Failed to create the file %ws for write`
- `0x1400471f3`: `MoveFileExW from %ws to %ws failed`
- `0x140047240`: `Temporary dest file %ws deleted due to error in MoveAndSecureFile`

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
  PSECURITY_DESCRIPTOR *v11; // rax
  signed int v12; // eax
  HANDLE v13; // rax
  signed int v14; // eax
  signed int LastError; // eax
  wil::details *dwCreationDisposition; // [rsp+20h] [rbp-68h]
  wil::details *dwCreationDispositiona; // [rsp+20h] [rbp-68h]
  wil::details *dwCreationDispositionb; // [rsp+20h] [rbp-68h]
  const char *hTemplateFile; // [rsp+30h] [rbp-58h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp-48h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+88h] [rbp+0h]
  HLOCAL hMem; // [rsp+90h] [rbp+8h] BYREF

  hMem = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( !a1 || !a2 )
  {
    v9 = "Invalid params";
    v8 = -2147024809;
    v10 = 68;
    goto LABEL_28;
  }
  v6 = UtilFileExists(a2);
  v7 = v6;
  if ( !a3 && v6 )
  {
    v8 = -2147024713;
    v9 = "Overwrite is false and file exists";
    v10 = 77;
LABEL_28:
    LODWORD(dwCreationDisposition) = v8;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelhelper.cpp",
      "MoveAndSecureFile",
      dwCreationDisposition,
      (int)v9,
      hTemplateFile);
    goto LABEL_29;
  }
  SetFileAttributesW(a2, 0x80u);
  v11 = (PSECURITY_DESCRIPTOR *)___replace_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___utl__YAPEAPEAXAEAV__unique_ptr_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___0__Z(&hMem);
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:P(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)", 1u, v11, 0) )
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
        goto LABEL_29;
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
LABEL_29:
  if ( hMem )
    LocalFree(hMem);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140046fdc  mov     r11, rsp
0x140046fdf  push    rbx
0x140046fe0  push    rbp
0x140046fe1  push    rsi
0x140046fe2  push    rdi
0x140046fe3  sub     rsp, 68h
0x140046fe7  mov     ebx, r8d
0x140046fea  mov     rdi, rdx
0x140046fed  mov     rbp, rcx
0x140046ff0  mov     qword ptr [r11+8], 0
0x140046ff8  xorps   xmm0, xmm0
0x140046ffb  xor     eax, eax
0x140046ffd  movups  xmmword ptr [rsp+88h+SecurityAttributes.nLength], xmm0
0x140047002  mov     [r11-38h], rax
0x140047006  test    rcx, rcx
0x140047009  jz      loc_14004727F
0x14004700f  test    rdx, rdx
0x140047012  jz      loc_14004727F
0x140047018  mov     rcx, rdx; wchar_t *
0x14004701b  call    ?UtilFileExists@@YA_NPEB_W@Z; UtilFileExists(wchar_t const *)
0x140047020  mov     sil, al
0x140047023  test    ebx, ebx
0x140047025  jnz     short loc_140047041
0x140047027  test    al, al
0x140047029  jz      short loc_140047041
0x14004702b  mov     ebx, 800700B7h
0x140047030  lea     rax, aOverwriteIsFal; "Overwrite is false and file exists"
0x140047037  mov     edx, 4Dh ; 'M'
0x14004703c  jmp     loc_140047290
0x140047041  mov     ebx, 80h
0x140047046  mov     edx, ebx; dwFileAttributes
0x140047048  mov     rcx, rdi; lpFileName
0x14004704b  call    cs:__imp_SetFileAttributesW
0x140047052  nop     dword ptr [rax+rax+00h]
0x140047057  lea     rcx, [rsp+88h+hMem]
0x14004705f  call    ??$replace@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@utl@@YAPEAPEAXAEAV?$unique_ptr@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@0@@Z
0x140047064  mov     r8, rax; SecurityDescriptor
0x140047067  xor     r9d, r9d; SecurityDescriptorSize
0x14004706a  lea     edx, [rbx-7Fh]; StringSDRevision
0x14004706d  lea     rcx, StringSecurityDescriptor; "D:P(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)"
0x140047074  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x14004707b  nop     dword ptr [rax+rax+00h]
0x140047080  test    eax, eax
0x140047082  jnz     short loc_1400470DE
0x140047084  call    cs:__imp_GetLastError
0x14004708b  nop     dword ptr [rax+rax+00h]
0x140047090  mov     ebx, eax
0x140047092  test    eax, eax
0x140047094  jle     short loc_14004709F
0x140047096  movzx   ebx, ax
0x140047099  or      ebx, 80070000h
0x14004709f  mov     eax, 80004005h
0x1400470a4  test    ebx, ebx
0x1400470a6  cmovns  ebx, eax
0x1400470a9  mov     rcx, [rsp+88h]; this
0x1400470b1  lea     rax, aConvertstrings; "ConvertStringSecurityDescriptorToSecuri"...
0x1400470b8  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], rax; int
0x1400470bd  mov     dword ptr [rsp+88h+dwCreationDisposition], ebx; wil::details *
0x1400470c1  lea     r9, aMoveandsecuref_0; "MoveAndSecureFile"
0x1400470c8  lea     r8, aOnecoreWindows_3; "onecore\\windows\\feedback\\core\\werfa"...
0x1400470cf  mov     edx, 64h ; 'd'; void *
0x1400470d4  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400470d9  jmp     loc_14004721B
0x1400470de  mov     [rsp+88h+SecurityAttributes.nLength], 18h
0x1400470e6  mov     rax, [rsp+88h+hMem]
0x1400470ee  mov     [rsp+88h+SecurityAttributes.lpSecurityDescriptor], rax
0x1400470f3  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x1400470fc  mov     [rsp+88h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x140047100  mov     dword ptr [rsp+88h+dwCreationDisposition], 2; dwCreationDisposition
0x140047108  lea     r9, [rsp+88h+SecurityAttributes]; lpSecurityAttributes
0x14004710d  xor     r8d, r8d; dwShareMode
0x140047110  mov     edx, 40040000h; dwDesiredAccess
0x140047115  mov     rcx, rdi; lpFileName
0x140047118  call    cs:__imp_CreateFileW
0x14004711f  nop     dword ptr [rax+rax+00h]
0x140047124  lea     rcx, [rax+1]
0x140047128  cmp     rcx, 1
0x14004712c  ja      short loc_14004718D
0x14004712e  call    cs:__imp_GetLastError
0x140047135  nop     dword ptr [rax+rax+00h]
0x14004713a  mov     ebx, eax
0x14004713c  test    eax, eax
0x14004713e  jle     short loc_140047149
0x140047140  movzx   ebx, ax
0x140047143  or      ebx, 80070000h
0x140047149  mov     eax, 80004005h
0x14004714e  test    ebx, ebx
0x140047150  cmovns  ebx, eax
0x140047153  mov     rcx, [rsp+88h]; this
0x14004715b  mov     [rsp+88h+hTemplateFile], rdi; char *
0x140047160  lea     rax, aFailedToCreate; "Failed to create the file %ws for write"
0x140047167  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], rax; int
0x14004716c  mov     dword ptr [rsp+88h+dwCreationDisposition], ebx; wil::details *
0x140047170  lea     r9, aMoveandsecuref_0; "MoveAndSecureFile"
0x140047177  lea     r8, aOnecoreWindows_3; "onecore\\windows\\feedback\\core\\werfa"...
0x14004717e  mov     edx, 77h ; 'w'; void *
0x140047183  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140047188  jmp     loc_14004721B
0x14004718d  mov     rcx, rax; hObject
0x140047190  call    cs:__imp_CloseHandle
0x140047197  nop     dword ptr [rax+rax+00h]
0x14004719c  mov     r8d, 0Bh; dwFlags
0x1400471a2  mov     rdx, rdi; lpNewFileName
0x1400471a5  mov     rcx, rbp; lpExistingFileName
0x1400471a8  call    cs:__imp_MoveFileExW
0x1400471af  nop     dword ptr [rax+rax+00h]
0x1400471b4  test    eax, eax
0x1400471b6  jnz     loc_14004726A
0x1400471bc  call    cs:__imp_GetLastError
0x1400471c3  nop     dword ptr [rax+rax+00h]
0x1400471c8  mov     ebx, eax
0x1400471ca  test    eax, eax
0x1400471cc  jle     short loc_1400471D7
0x1400471ce  movzx   ebx, ax
0x1400471d1  or      ebx, 80070000h
0x1400471d7  mov     eax, 80004005h
0x1400471dc  test    ebx, ebx
0x1400471de  cmovns  ebx, eax
0x1400471e1  mov     rcx, [rsp+88h]; this
0x1400471e9  mov     [rsp+88h+var_50], rdi
0x1400471ee  mov     [rsp+88h+hTemplateFile], rbp; char *
0x1400471f3  lea     rax, aMovefileexwFro; "MoveFileExW from %ws to %ws failed"
0x1400471fa  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], rax; int
0x1400471ff  mov     dword ptr [rsp+88h+dwCreationDisposition], ebx; wil::details *
0x140047203  lea     r9, aMoveandsecuref_0; "MoveAndSecureFile"
0x14004720a  lea     r8, aOnecoreWindows_3; "onecore\\windows\\feedback\\core\\werfa"...
0x140047211  mov     edx, 82h; void *
0x140047216  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14004721b  test    sil, sil
0x14004721e  jnz     loc_1400472B5
0x140047224  mov     rcx, rdi; lpFileName
0x140047227  call    cs:__imp_DeleteFileW
0x14004722e  nop     dword ptr [rax+rax+00h]
0x140047233  mov     rcx, [rsp+88h]; this
0x14004723b  mov     [rsp+88h+hTemplateFile], rdi; char *
0x140047240  lea     rax, aTemporaryDestF; "Temporary dest file %ws deleted due to "...
0x140047247  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], rax; int
0x14004724c  mov     dword ptr [rsp+88h+dwCreationDisposition], ebx; wil::details *
0x140047250  lea     r9, aMoveandsecuref_0; "MoveAndSecureFile"
0x140047257  lea     r8, aOnecoreWindows_3; "onecore\\windows\\feedback\\core\\werfa"...
0x14004725e  mov     edx, 98h; void *
0x140047263  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140047268  jmp     short loc_1400472B5
0x14004726a  mov     edx, ebx; dwFileAttributes
0x14004726c  mov     rcx, rdi; lpFileName
0x14004726f  call    cs:__imp_SetFileAttributesW
0x140047276  nop     dword ptr [rax+rax+00h]
0x14004727b  xor     ebx, ebx
0x14004727d  jmp     short loc_1400472B5
0x14004727f  lea     rax, aInvalidParams; "Invalid params"
0x140047286  mov     ebx, 80070057h
0x14004728b  mov     edx, 44h ; 'D'; void *
0x140047290  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], rax; int
0x140047295  mov     dword ptr [rsp+88h+dwCreationDisposition], ebx; wil::details *
0x140047299  lea     r9, aMoveandsecuref_0; "MoveAndSecureFile"
0x1400472a0  lea     r8, aOnecoreWindows_3; "onecore\\windows\\feedback\\core\\werfa"...
0x1400472a7  mov     rcx, [rsp+88h]; this
0x1400472af  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400472b4  nop
0x1400472b5  mov     rcx, [rsp+88h+hMem]; hMem
0x1400472bd  test    rcx, rcx
0x1400472c0  jz      short loc_1400472CE
0x1400472c2  call    cs:__imp_LocalFree
0x1400472c9  nop     dword ptr [rax+rax+00h]
0x1400472ce  mov     eax, ebx
0x1400472d0  add     rsp, 68h
0x1400472d4  pop     rdi
0x1400472d5  pop     rsi
0x1400472d6  pop     rbp
0x1400472d7  pop     rbx
0x1400472d8  retn
```
