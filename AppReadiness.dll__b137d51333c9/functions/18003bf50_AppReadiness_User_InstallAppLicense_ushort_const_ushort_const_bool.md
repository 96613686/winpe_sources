# AppReadiness::User::InstallAppLicense(ushort const *,ushort const *,bool)

- ea: `0x18003bf50`
- end: `0x18003c13e`
- name: `?InstallAppLicense@User@AppReadiness@@SAJPEBG0_N@Z`
- size: `494`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180010afc`

## callees

- `0x180015930`
- `0x180019570`
- `0x180030914`
- `0x180039eec`
- `0x18003bf50`
- `0x18003c144`
- `0x18003e210`
- `0x18003e234`
- `0x18003eaac`
- `0x18003eca8`
- `0x18005d490`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003c0c2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003c0c2`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18003c08c`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18003c08c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003c06f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003c06f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003c02e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003c02e`
- `OEMLicense!HrInstallClipLicense` at `0x18003c0e8`
- `OEMLicense!HrInstallClipLicense` at `0x18003c0e8`

## string_xrefs

- `0x18003bfad`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x18003c0fc`: `onecoreuap\shell\appreadiness\src\core\user.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AppReadiness::User::InstallAppLicense(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  int v3; // ebx
  __int64 v4; // rdx
  DWORD FileAttributesW; // eax
  HANDLE FileW; // rax
  void *v8; // rbx
  unsigned __int64 FileSize; // rdi
  void *v10; // rsi
  unsigned __int64 v11; // rdx
  unsigned int v12; // r8d
  const char *v13; // r9
  int v14; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v18[3]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR FileName[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  memset_0(FileName, 0, 0x208u);
  v3 = StringCchCopyW(FileName, 0x104u, L"P:\\AppData");
  if ( v3 < 0 )
  {
    v4 = 2892;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
      (const char *)(unsigned int)v3,
      dwCreationDisposition);
    return (unsigned int)v3;
  }
  v3 = StringCchCatW(FileName, 0x104u, L"\\");
  if ( v3 < 0 )
  {
    v4 = 2893;
    goto LABEL_3;
  }
  v3 = StringCchCatW(FileName, 0x104u, a1);
  if ( v3 < 0 )
  {
    v4 = 2894;
    goto LABEL_3;
  }
  v3 = StringCchCatW(FileName, 0x104u, L".xml");
  if ( v3 < 0 )
  {
    v4 = 2895;
    goto LABEL_3;
  }
  FileAttributesW = GetFileAttributesW(FileName);
  if ( FileAttributesW != -1 && (FileAttributesW & 0x10) == 0 )
  {
    FileW = CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    v8 = FileW;
    v18[0] = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      FileSize = GetFileSize(FileW, 0);
      v10 = operator new[](FileSize);
      v18[1] = v10;
      NumberOfBytesRead = 0;
      if ( !ReadFile(v8, v10, FileSize, &NumberOfBytesRead, 0) )
        wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0xB5F, v12, v13);
      if ( NumberOfBytesRead == (_DWORD)FileSize )
      {
        v14 = HrInstallClipLicense(FileSize, (const unsigned __int8 *)v10);
        if ( v14 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xB63,
            (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
            (const char *)(unsigned int)v14,
            dwCreationDispositiona);
      }
      operator delete(v10, v11);
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v18);
  }
  return 0;
}

```

## disassembly

```asm
0x18003bf50  push    rbp
0x18003bf52  push    rbx
0x18003bf53  push    rsi
0x18003bf54  push    rdi
0x18003bf55  lea     rbp, [rsp-188h]
0x18003bf5d  sub     rsp, 288h
0x18003bf64  mov     rax, cs:__security_cookie
0x18003bf6b  xor     rax, rsp
0x18003bf6e  mov     [rbp+1A0h+var_30], rax
0x18003bf75  mov     rdi, rcx
0x18003bf78  xor     edx, edx; Val
0x18003bf7a  mov     r8d, 208h; Size
0x18003bf80  lea     rcx, [rsp+2A0h+FileName]; void *
0x18003bf85  call    memset_0
0x18003bf8a  lea     r8, aPAppdata; "P:\\AppData"
0x18003bf91  mov     esi, 104h
0x18003bf96  mov     edx, esi; unsigned __int64
0x18003bf98  lea     rcx, [rsp+2A0h+FileName]; unsigned __int16 *
0x18003bf9d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003bfa2  mov     ebx, eax
0x18003bfa4  test    eax, eax
0x18003bfa6  jns     short loc_18003BFCA
0x18003bfa8  mov     edx, 0B4Ch; void *
0x18003bfad  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18003bfb4  mov     r9d, ebx; char *
0x18003bfb7  mov     rcx, [rbp+1A8h]; this
0x18003bfbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bfc3  mov     eax, ebx
0x18003bfc5  jmp     loc_18003C123
0x18003bfca  lea     r8, asc_1800858F8; "\\"
0x18003bfd1  mov     rdx, rsi; unsigned __int64
0x18003bfd4  lea     rcx, [rsp+2A0h+FileName]; unsigned __int16 *
0x18003bfd9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003bfde  mov     ebx, eax
0x18003bfe0  test    eax, eax
0x18003bfe2  jns     short loc_18003BFEB
0x18003bfe4  mov     edx, 0B4Dh
0x18003bfe9  jmp     short loc_18003BFAD
0x18003bfeb  mov     r8, rdi; unsigned __int16 *
0x18003bfee  mov     rdx, rsi; unsigned __int64
0x18003bff1  lea     rcx, [rsp+2A0h+FileName]; unsigned __int16 *
0x18003bff6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003bffb  mov     ebx, eax
0x18003bffd  test    eax, eax
0x18003bfff  jns     short loc_18003C008
0x18003c001  mov     edx, 0B4Eh
0x18003c006  jmp     short loc_18003BFAD
0x18003c008  lea     r8, aXml; ".xml"
0x18003c00f  mov     rdx, rsi; unsigned __int64
0x18003c012  lea     rcx, [rsp+2A0h+FileName]; unsigned __int16 *
0x18003c017  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003c01c  mov     ebx, eax
0x18003c01e  test    eax, eax
0x18003c020  jns     short loc_18003C029
0x18003c022  mov     edx, 0B4Fh
0x18003c027  jmp     short loc_18003BFAD
0x18003c029  lea     rcx, [rsp+2A0h+FileName]; lpFileName
0x18003c02e  call    cs:__imp_GetFileAttributesW
0x18003c034  cmp     eax, 0FFFFFFFFh
0x18003c037  jz      loc_18003C121
0x18003c03d  test    al, 10h
0x18003c03f  jnz     loc_18003C121
0x18003c045  mov     [rsp+2A0h+hTemplateFile], 0; hTemplateFile
0x18003c04e  mov     [rsp+2A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003c056  mov     [rsp+2A0h+dwCreationDisposition], 3; dwCreationDisposition
0x18003c05e  xor     r9d, r9d; lpSecurityAttributes
0x18003c061  mov     edx, 80000000h; dwDesiredAccess
0x18003c066  lea     r8d, [r9+1]; dwShareMode
0x18003c06a  lea     rcx, [rsp+2A0h+FileName]; lpFileName
0x18003c06f  call    cs:__imp_CreateFileW
0x18003c075  mov     rbx, rax
0x18003c078  mov     [rsp+2A0h+var_258], rax
0x18003c07d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003c081  jz      loc_18003C117
0x18003c087  xor     edx, edx; lpFileSizeHigh
0x18003c089  mov     rcx, rax; hFile
0x18003c08c  call    cs:__imp_GetFileSize
0x18003c092  mov     edi, eax
0x18003c094  mov     ecx, eax; unsigned __int64
0x18003c096  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003c09b  mov     rsi, rax
0x18003c09e  mov     [rsp+2A0h+var_250], rax
0x18003c0a3  mov     [rsp+2A0h+NumberOfBytesRead], 0
0x18003c0ab  mov     qword ptr [rsp+2A0h+dwCreationDisposition], 0; int
0x18003c0b4  lea     r9, [rsp+2A0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18003c0b9  mov     r8d, edi; nNumberOfBytesToRead
0x18003c0bc  mov     rdx, rax; lpBuffer
0x18003c0bf  mov     rcx, rbx; hFile
0x18003c0c2  call    cs:__imp_ReadFile
0x18003c0c8  mov     rcx, [rbp+1A8h]; this
0x18003c0cf  test    eax, eax
0x18003c0d1  jnz     short loc_18003C0DD
0x18003c0d3  mov     edx, 0B5Fh; void *
0x18003c0d8  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18003c0dd  cmp     [rsp+2A0h+NumberOfBytesRead], edi
0x18003c0e1  jnz     short loc_18003C10E
0x18003c0e3  mov     rdx, rsi
0x18003c0e6  mov     ecx, edi
0x18003c0e8  call    cs:__imp_?HrInstallClipLicense@@YAJIPEBE@Z; HrInstallClipLicense(uint,uchar const *)
0x18003c0ee  mov     rcx, [rbp+1A8h]; this
0x18003c0f5  test    eax, eax
0x18003c0f7  jns     short loc_18003C10E
0x18003c0f9  mov     r9d, eax; char *
0x18003c0fc  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18003c103  mov     edx, 0B63h; void *
0x18003c108  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003c10d  nop
0x18003c10e  mov     rcx, rsi; void *
0x18003c111  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003c116  nop
0x18003c117  lea     rcx, [rsp+2A0h+var_258]
0x18003c11c  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003c121  xor     eax, eax
0x18003c123  mov     rcx, [rbp+1A0h+var_30]
0x18003c12a  xor     rcx, rsp; StackCookie
0x18003c12d  call    __security_check_cookie
0x18003c132  add     rsp, 288h
0x18003c139  pop     rdi
0x18003c13a  pop     rsi
0x18003c13b  pop     rbx
0x18003c13c  pop     rbp
0x18003c13d  retn
```
