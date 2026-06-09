# InitializeProcessingContext(_PROCESSING_CONTEXT *)

- ea: `0x18008c52c`
- end: `0x18008c66c`
- name: `?InitializeProcessingContext@@YAKPEAU_PROCESSING_CONTEXT@@@Z`
- size: `320`
- prototype: `unsigned int __fastcall(struct _PROCESSING_CONTEXT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18008c100`

## callees

- `0x18008c52c`
- `0x1800992a0`
- `0x180099e38`
- `0x18009d3c4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008c5fb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008c61b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008c5fb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008c61b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008c639`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008c639`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18008c5ba`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18008c5ba`

## string_xrefs

- `0x18008c612`: `tdh.dll`
- `0x18008c5f2`: `api-ms-win-eventing-tdh-l1-1-0.dll`

## pseudocode

```c
__int64 __fastcall InitializeProcessingContext(struct _PROCESSING_CONTEXT *a1)
{
  unsigned int v2; // eax
  HMODULE *v3; // rdi
  FARPROC *v4; // rbx
  HMODULE Library; // rax
  _OSVERSIONINFOW VersionInformation; // [rsp+20h] [rbp-138h] BYREF

  if ( *((_DWORD *)a1 + 2) )
    *(_QWORD *)a1 = operator new[](*((unsigned int *)a1 + 2));
  if ( *((_DWORD *)a1 + 6) )
    *((_QWORD *)a1 + 2) = operator new[](*((unsigned int *)a1 + 6));
  if ( *((_DWORD *)a1 + 10) )
    *((_QWORD *)a1 + 4) = operator new[](*((unsigned int *)a1 + 10));
  v2 = *((_DWORD *)a1 + 34);
  if ( v2 )
    *((_QWORD *)a1 + 16) = operator new[](v2);
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
  VersionInformation.dwOSVersionInfoSize = 276;
  if ( !GetVersionExW(&VersionInformation)
    || VersionInformation.dwMajorVersion >= 6
    && (VersionInformation.dwMajorVersion != 6 || VersionInformation.dwMinorVersion) )
  {
    v3 = (HMODULE *)((char *)a1 + 144);
    if ( a1 != (struct _PROCESSING_CONTEXT *)-144LL )
    {
      v4 = (FARPROC *)((char *)a1 + 152);
      if ( v4 )
      {
        Library = LoadLibraryExW(L"api-ms-win-eventing-tdh-l1-1-0.dll", 0, 0);
        *v3 = Library;
        if ( Library || (Library = LoadLibraryExW(L"tdh.dll", 0, 0), (*v3 = Library) != 0) )
          *v4 = GetProcAddress(Library, "TdhFormatProperty");
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18008c52c  mov     [rsp+arg_8], rbx
0x18008c531  push    rdi
0x18008c532  sub     rsp, 150h
0x18008c539  mov     rax, cs:__security_cookie
0x18008c540  xor     rax, rsp
0x18008c543  mov     [rsp+158h+var_18], rax
0x18008c54b  cmp     dword ptr [rcx+8], 0
0x18008c54f  mov     rbx, rcx
0x18008c552  jbe     short loc_18008C55F
0x18008c554  mov     ecx, [rcx+8]; unsigned __int64
0x18008c557  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18008c55c  mov     [rbx], rax
0x18008c55f  cmp     dword ptr [rbx+18h], 0
0x18008c563  jbe     short loc_18008C571
0x18008c565  mov     ecx, [rbx+18h]; unsigned __int64
0x18008c568  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18008c56d  mov     [rbx+10h], rax
0x18008c571  cmp     dword ptr [rbx+28h], 0
0x18008c575  jbe     short loc_18008C583
0x18008c577  mov     ecx, [rbx+28h]; unsigned __int64
0x18008c57a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18008c57f  mov     [rbx+20h], rax
0x18008c583  mov     eax, [rbx+88h]
0x18008c589  test    eax, eax
0x18008c58b  jz      short loc_18008C59B
0x18008c58d  mov     ecx, eax; unsigned __int64
0x18008c58f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18008c594  mov     [rbx+80h], rax
0x18008c59b  xor     edx, edx; Val
0x18008c59d  lea     rcx, [rsp+158h+VersionInformation.dwMajorVersion]; void *
0x18008c5a2  mov     r8d, 110h; Size
0x18008c5a8  call    memset_0
0x18008c5ad  lea     rcx, [rsp+158h+VersionInformation]; lpVersionInformation
0x18008c5b2  mov     [rsp+158h+VersionInformation.dwOSVersionInfoSize], 114h
0x18008c5ba  call    cs:__imp_GetVersionExW
0x18008c5c1  nop     dword ptr [rax+rax+00h]
0x18008c5c6  test    eax, eax
0x18008c5c8  jz      short loc_18008C5DA
0x18008c5ca  cmp     [rsp+158h+VersionInformation.dwMajorVersion], 6
0x18008c5cf  jb      short loc_18008C648
0x18008c5d1  jnz     short loc_18008C5DA
0x18008c5d3  cmp     [rsp+158h+VersionInformation.dwMinorVersion], 1
0x18008c5d8  jb      short loc_18008C648
0x18008c5da  lea     rdi, [rbx+90h]
0x18008c5e1  test    rdi, rdi
0x18008c5e4  jz      short loc_18008C648
0x18008c5e6  add     rbx, 98h
0x18008c5ed  jz      short loc_18008C648
0x18008c5ef  xor     r8d, r8d; dwFlags
0x18008c5f2  lea     rcx, aApiMsWinEventi_1; "api-ms-win-eventing-tdh-l1-1-0.dll"
0x18008c5f9  xor     edx, edx; hFile
0x18008c5fb  call    cs:__imp_LoadLibraryExW
0x18008c602  nop     dword ptr [rax+rax+00h]
0x18008c607  mov     [rdi], rax
0x18008c60a  test    rax, rax
0x18008c60d  jnz     short loc_18008C62F
0x18008c60f  xor     r8d, r8d; dwFlags
0x18008c612  lea     rcx, aTdhDll; "tdh.dll"
0x18008c619  xor     edx, edx; hFile
0x18008c61b  call    cs:__imp_LoadLibraryExW
0x18008c622  nop     dword ptr [rax+rax+00h]
0x18008c627  mov     [rdi], rax
0x18008c62a  test    rax, rax
0x18008c62d  jz      short loc_18008C648
0x18008c62f  lea     rdx, aTdhformatprope; "TdhFormatProperty"
0x18008c636  mov     rcx, rax; hModule
0x18008c639  call    cs:__imp_GetProcAddress
0x18008c640  nop     dword ptr [rax+rax+00h]
0x18008c645  mov     [rbx], rax
0x18008c648  xor     eax, eax
0x18008c64a  mov     rcx, [rsp+158h+var_18]
0x18008c652  xor     rcx, rsp; StackCookie
0x18008c655  call    __security_check_cookie
0x18008c65a  mov     rbx, [rsp+158h+arg_8]
0x18008c662  add     rsp, 150h
0x18008c669  pop     rdi
0x18008c66a  retn
```
