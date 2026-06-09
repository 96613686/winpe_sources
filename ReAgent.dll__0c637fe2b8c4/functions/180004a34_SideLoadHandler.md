# SideLoadHandler

- ea: `0x180004a34`
- end: `0x180004c85`
- name: `SideLoadHandler`
- size: `593`
- prototype: `HMODULE __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180004a14`

## callees

- `0x180004a34`
- `0x1800057b0`
- `0x18005cf30`

## import_xrefs

- `msvcrt!strcpy_s` at `0x180004c41`
- `msvcrt!strcpy_s` at `0x180004c41`
- `msvcrt!strncpy_s` at `0x180004b92`
- `msvcrt!strncpy_s` at `0x180004b92`
- `msvcrt!strrchr` at `0x180004b3f`
- `msvcrt!strrchr` at `0x180004b3f`
- `msvcrt!_stricmp` at `0x180004a5e`
- `msvcrt!_stricmp` at `0x180004a5e`
- `KERNEL32!GetModuleHandleExA` at `0x180004aa7`
- `KERNEL32!GetModuleHandleExA` at `0x180004ace`
- `KERNEL32!GetModuleHandleExA` at `0x180004aa7`
- `KERNEL32!GetModuleHandleExA` at `0x180004ace`
- `KERNEL32!GetLastError` at `0x180004ad8`
- `KERNEL32!GetLastError` at `0x180004b1e`
- `KERNEL32!GetLastError` at `0x180004bb6`
- `KERNEL32!GetLastError` at `0x180004c60`
- `KERNEL32!GetLastError` at `0x180004ad8`
- `KERNEL32!GetLastError` at `0x180004b1e`
- `KERNEL32!GetLastError` at `0x180004bb6`
- `KERNEL32!GetLastError` at `0x180004c60`
- `KERNEL32!GetModuleFileNameA` at `0x180004b14`
- `KERNEL32!GetModuleFileNameA` at `0x180004b14`
- `KERNEL32!GetFileAttributesA` at `0x180004bab`
- `KERNEL32!GetFileAttributesA` at `0x180004bab`
- `KERNEL32!LoadLibraryExA` at `0x180004c1e`
- `KERNEL32!LoadLibraryExA` at `0x180004c1e`

## string_xrefs

- `0x180004ade`: `SideLoadHandler: Failed to get this module handle; GLE = %u.`
- `0x180004b24`: `SideLoadHandler: Failed to get this module path; GLE = %u.`
- `0x180004b68`: `SideLoadHandler: Unexpected DLL path %s.`
- `0x180004b9c`: `SideLoadHandler: Failed to copy DLL name to path buffer; errno_t = %u.`
- `0x180004bbf`: `SideLoadHandler: Expected DLL %s does not exist; GLE = %u.`
- `0x180004bdc`: `SideLoadHandler: Expected DLL %s is a directory.`
- `0x180004c4a`: `SideLoadHandler: Side-loaded %s (DLL name %s).`
- `0x180004c69`: `SideLoadHandler: Failed to side-load %s as desired; GLE = %u.`
- `0x180004bf6`: `SideLoadHandler: Unable to side-load %s.`
- `0x180004a50`: `ServicingCommon.dll`

## pseudocode

```c
HMODULE __fastcall SideLoadHandler(__int64 a1)
{
  char *v2; // rbx
  HMODULE v4; // rcx
  DWORD LastError; // eax
  DWORD v6; // eax
  char *v7; // rcx
  char *v8; // rax
  unsigned int v9; // eax
  DWORD FileAttributesA; // eax
  DWORD v11; // eax
  HMODULE Library; // rdi
  DWORD v13; // eax
  HMODULE phModule; // [rsp+20h] [rbp-38h] BYREF

  v2 = szDll;
  while ( _stricmp(*(const char **)(a1 + 24), v2) )
  {
    v2 += 40;
    if ( v2 == (char *)&g_TlsIndex )
      return 0;
  }
  phModule = 0;
  if ( GetModuleHandleExA(2u, v2, &phModule) )
    return 0;
  v4 = hModule;
  if ( !hModule )
  {
    if ( !GetModuleHandleExA(6u, _ImageBase, &hModule) )
    {
      LastError = GetLastError();
      UnattendLogA(0x2000000, "SideLoadHandler: Failed to get this module handle; GLE = %u.", LastError);
      return 0;
    }
    v4 = hModule;
  }
  if ( !LibFileName && !GetModuleFileNameA(v4, &LibFileName, 0x104u) )
  {
    v6 = GetLastError();
    UnattendLogA(0x2000000, "SideLoadHandler: Failed to get this module path; GLE = %u.", v6);
    return 0;
  }
  v7 = (char *)qword_1800ADA80;
  if ( !qword_1800ADA80 )
  {
    v8 = strrchr(&LibFileName, 92);
    qword_1800ADA80 = (__int64)v8;
    if ( !v8 )
      return 0;
    v7 = v8 + 1;
    qword_1800ADA80 = (__int64)(v8 + 1);
  }
  if ( !*v7 )
  {
    UnattendLogA(0x2000000, "SideLoadHandler: Unexpected DLL path %s.", &LibFileName);
    return 0;
  }
  *v7 = 0;
  v9 = strncpy_s(v7, (char *)&dword_1800ADB94 - v7, v2, *((_QWORD *)v2 + 3));
  if ( v9 )
  {
    UnattendLogA(0x2000000, "SideLoadHandler: Failed to copy DLL name to path buffer; errno_t = %u.", v9);
    return 0;
  }
  FileAttributesA = GetFileAttributesA(&LibFileName);
  if ( FileAttributesA == -1 )
  {
    v11 = GetLastError();
    UnattendLogA(0x2000000, "SideLoadHandler: Expected DLL %s does not exist; GLE = %u.", &LibFileName, v11);
  }
  else
  {
    if ( (FileAttributesA & 0x10) == 0 )
      goto LABEL_27;
    UnattendLogA(0x2000000, "SideLoadHandler: Expected DLL %s is a directory.", &LibFileName);
  }
  if ( v2[32] )
  {
    UnattendLogA(0x2000000, "SideLoadHandler: Unable to side-load %s.", &LibFileName);
    return hModule;
  }
LABEL_27:
  Library = LoadLibraryExA(&LibFileName, 0, 0x1100u);
  v2[33] = Library != 0;
  if ( Library )
  {
    strcpy_s(v2, 0x15u, *(const char **)(a1 + 24));
    UnattendLogA(0x4000000, "SideLoadHandler: Side-loaded %s (DLL name %s).", &LibFileName, v2);
  }
  else
  {
    v13 = GetLastError();
    UnattendLogA(0x2000000, "SideLoadHandler: Failed to side-load %s as desired; GLE = %u.", &LibFileName, v13);
  }
  return Library;
}

```

## disassembly

```asm
0x180004a34  push    rbx
0x180004a36  push    rsi
0x180004a37  push    rdi
0x180004a38  push    r14
0x180004a3a  sub     rsp, 38h
0x180004a3e  mov     rax, cs:__security_cookie
0x180004a45  xor     rax, rsp
0x180004a48  mov     [rsp+58h+var_30], rax
0x180004a4d  mov     rsi, rcx
0x180004a50  lea     rbx, szDll; "ServicingCommon.dll"
0x180004a57  mov     rcx, [rsi+18h]; String1
0x180004a5b  mov     rdx, rbx; String2
0x180004a5e  call    cs:__imp__stricmp
0x180004a64  test    eax, eax
0x180004a66  jz      short loc_180004A91
0x180004a68  add     rbx, 28h ; '('
0x180004a6c  lea     rax, g_TlsIndex
0x180004a73  cmp     rbx, rax
0x180004a76  jnz     short loc_180004A57
0x180004a78  xor     eax, eax
0x180004a7a  mov     rcx, [rsp+58h+var_30]
0x180004a7f  xor     rcx, rsp; StackCookie
0x180004a82  call    __security_check_cookie
0x180004a87  add     rsp, 38h
0x180004a8b  pop     r14
0x180004a8d  pop     rdi
0x180004a8e  pop     rsi
0x180004a8f  pop     rbx
0x180004a90  retn
0x180004a91  lea     r8, [rsp+58h+phModule]; phModule
0x180004a96  mov     [rsp+58h+phModule], 0
0x180004a9f  mov     rdx, rbx; lpModuleName
0x180004aa2  mov     ecx, 2; dwFlags
0x180004aa7  call    cs:__imp_GetModuleHandleExA
0x180004aad  test    eax, eax
0x180004aaf  jnz     short loc_180004A78
0x180004ab1  mov     rcx, cs:hModule
0x180004ab8  test    rcx, rcx
0x180004abb  jnz     short loc_180004AFB
0x180004abd  lea     r8, hModule; phModule
0x180004ac4  lea     rdx, __ImageBase; lpModuleName
0x180004acb  lea     ecx, [rax+6]; dwFlags
0x180004ace  call    cs:__imp_GetModuleHandleExA
0x180004ad4  test    eax, eax
0x180004ad6  jnz     short loc_180004AF4
0x180004ad8  call    cs:__imp_GetLastError
0x180004ade  lea     rdx, aSideloadhandle_3; "SideLoadHandler: Failed to get this mod"...
0x180004ae5  mov     r8d, eax
0x180004ae8  mov     ecx, 2000000h
0x180004aed  call    UnattendLogA
0x180004af2  jmp     short loc_180004A78
0x180004af4  mov     rcx, cs:hModule; hModule
0x180004afb  cmp     cs:LibFileName, 0
0x180004b02  lea     r14, LibFileName
0x180004b09  jnz     short loc_180004B2D
0x180004b0b  mov     r8d, 104h; nSize
0x180004b11  mov     rdx, r14; lpFilename
0x180004b14  call    cs:__imp_GetModuleFileNameA
0x180004b1a  test    eax, eax
0x180004b1c  jnz     short loc_180004B2D
0x180004b1e  call    cs:__imp_GetLastError
0x180004b24  lea     rdx, aSideloadhandle_4; "SideLoadHandler: Failed to get this mod"...
0x180004b2b  jmp     short loc_180004AE5
0x180004b2d  mov     rcx, cs:qword_1800ADA80
0x180004b34  test    rcx, rcx
0x180004b37  jnz     short loc_180004B60
0x180004b39  lea     edx, [rcx+5Ch]; Ch
0x180004b3c  mov     rcx, r14; Str
0x180004b3f  call    cs:__imp_strrchr
0x180004b45  mov     cs:qword_1800ADA80, rax
0x180004b4c  test    rax, rax
0x180004b4f  jz      loc_180004A78
0x180004b55  lea     rcx, [rax+1]; Destination
0x180004b59  mov     cs:qword_1800ADA80, rcx
0x180004b60  cmp     byte ptr [rcx], 0
0x180004b63  jnz     short loc_180004B7E
0x180004b65  mov     r8, r14
0x180004b68  lea     rdx, aSideloadhandle; "SideLoadHandler: Unexpected DLL path %s"...
0x180004b6f  mov     ecx, 2000000h
0x180004b74  call    UnattendLogA
0x180004b79  jmp     loc_180004A78
0x180004b7e  mov     byte ptr [rcx], 0
0x180004b81  lea     rdx, dword_1800ADB94
0x180004b88  mov     r9, [rbx+18h]; MaxCount
0x180004b8c  sub     rdx, rcx; SizeInBytes
0x180004b8f  mov     r8, rbx; Source
0x180004b92  call    cs:__imp_strncpy_s
0x180004b98  test    eax, eax
0x180004b9a  jz      short loc_180004BA8
0x180004b9c  lea     rdx, aSideloadhandle_2; "SideLoadHandler: Failed to copy DLL nam"...
0x180004ba3  jmp     loc_180004AE5
0x180004ba8  mov     rcx, r14; lpFileName
0x180004bab  call    cs:__imp_GetFileAttributesA
0x180004bb1  cmp     eax, 0FFFFFFFFh
0x180004bb4  jnz     short loc_180004BD5
0x180004bb6  call    cs:__imp_GetLastError
0x180004bbc  mov     r8, r14
0x180004bbf  lea     rdx, aSideloadhandle_5; "SideLoadHandler: Expected DLL %s does n"...
0x180004bc6  mov     r9d, eax
0x180004bc9  mov     ecx, 2000000h
0x180004bce  call    UnattendLogA
0x180004bd3  jmp     short loc_180004BED
0x180004bd5  test    al, 10h
0x180004bd7  jz      short loc_180004C13
0x180004bd9  mov     r8, r14
0x180004bdc  lea     rdx, aSideloadhandle_1; "SideLoadHandler: Expected DLL %s is a d"...
0x180004be3  mov     ecx, 2000000h
0x180004be8  call    UnattendLogA
0x180004bed  cmp     byte ptr [rbx+20h], 0
0x180004bf1  jz      short loc_180004C13
0x180004bf3  mov     r8, r14
0x180004bf6  lea     rdx, aSideloadhandle_6; "SideLoadHandler: Unable to side-load %s"...
0x180004bfd  mov     ecx, 2000000h
0x180004c02  call    UnattendLogA
0x180004c07  mov     rax, cs:hModule
0x180004c0e  jmp     loc_180004A7A
0x180004c13  xor     edx, edx; hFile
0x180004c15  mov     r8d, 1100h; dwFlags
0x180004c1b  mov     rcx, r14; lpLibFileName
0x180004c1e  call    cs:__imp_LoadLibraryExA
0x180004c24  test    rax, rax
0x180004c27  mov     rdi, rax
0x180004c2a  setnz   cl
0x180004c2d  mov     [rbx+21h], cl
0x180004c30  test    rax, rax
0x180004c33  jz      short loc_180004C60
0x180004c35  mov     r8, [rsi+18h]; Source
0x180004c39  mov     edx, 15h; SizeInBytes
0x180004c3e  mov     rcx, rbx; Destination
0x180004c41  call    cs:__imp_strcpy_s
0x180004c47  mov     r9, rbx
0x180004c4a  lea     rdx, aSideloadhandle_0; "SideLoadHandler: Side-loaded %s (DLL na"...
0x180004c51  mov     r8, r14
0x180004c54  mov     ecx, 4000000h
0x180004c59  call    UnattendLogA
0x180004c5e  jmp     short loc_180004C7D
0x180004c60  call    cs:__imp_GetLastError
0x180004c66  mov     r8, r14
0x180004c69  lea     rdx, aSideloadhandle_7; "SideLoadHandler: Failed to side-load %s"...
0x180004c70  mov     r9d, eax
0x180004c73  mov     ecx, 2000000h
0x180004c78  call    UnattendLogA
0x180004c7d  mov     rax, rdi
0x180004c80  jmp     loc_180004A7A
```
