# WriteTextLogFileHeader

- ea: `0x14000e7fc`
- end: `0x14000e92f`
- name: `WriteTextLogFileHeader`
- size: `307`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, service_task, installer_update`

## callers

- `0x14000da54`

## callees

- `0x14000cdc4`
- `0x14000e7fc`
- `0x140045eea`
- `0x140045f30`

## import_xrefs

- `ntdll!RtlGetVersion` at `0x14000e84c`
- `ntdll!RtlGetVersion` at `0x14000e863`
- `ntdll!RtlGetVersion` at `0x14000e84c`
- `ntdll!RtlGetVersion` at `0x14000e863`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000e909`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000e909`

## string_xrefs

- `0x14000e8c0`: `[Device Install Log]\n     OS Version = %d.%d.%d\n     Service Pack = %d.%d\n     Suite = 0x%04x\n     ProductType = %d\n     Architecture = %s\n\n[BeginLog]\n`

## pseudocode

```c
HRESULT __fastcall WriteTextLogFileHeader(HANDLE hFile)
{
  HRESULT result; // eax
  __int64 v3; // r8
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp-A0h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v6; // [rsp+184h] [rbp+84h]
  unsigned __int16 v7; // [rsp+186h] [rbp+86h]
  unsigned __int16 v8; // [rsp+188h] [rbp+88h]
  unsigned __int8 v9; // [rsp+18Ah] [rbp+8Ah]
  char pszDest[256]; // [rsp+190h] [rbp+90h] BYREF

  NumberOfBytesWritten = 0;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( RtlGetVersion(&VersionInformation) >= 0
    || (VersionInformation.dwOSVersionInfoSize = 276, result = RtlGetVersion(&VersionInformation), result >= 0) )
  {
    result = StringCchPrintfA(
               pszDest,
               0xFFu,
               "[Device Install Log]\r\n"
               "     OS Version = %d.%d.%d\r\n"
               "     Service Pack = %d.%d\r\n"
               "     Suite = 0x%04x\r\n"
               "     ProductType = %d\r\n"
               "     Architecture = %s\r\n"
               "\r\n"
               "[BeginLog]\r\n",
               VersionInformation.dwMajorVersion,
               VersionInformation.dwMinorVersion,
               VersionInformation.dwBuildNumber,
               v6,
               v7,
               v8,
               v9,
               "amd64");
    if ( result >= 0 )
    {
      v3 = -1;
      do
        ++v3;
      while ( pszDest[v3] );
      return WriteFile(hFile, pszDest, v3, &NumberOfBytesWritten, 0);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000e7fc  mov     [rsp-8+arg_8], rbx
0x14000e801  push    rbp
0x14000e802  lea     rbp, [rsp-1A0h]
0x14000e80a  sub     rsp, 2A0h
0x14000e811  mov     rax, cs:__security_cookie
0x14000e818  xor     rax, rsp
0x14000e81b  mov     [rbp+1A0h+var_10], rax
0x14000e822  mov     rbx, rcx
0x14000e825  mov     [rsp+2A0h+NumberOfBytesWritten], 0
0x14000e82d  lea     rcx, [rsp+2A0h+VersionInformation.dwMajorVersion]; void *
0x14000e832  xor     edx, edx; Val
0x14000e834  mov     r8d, 118h; Size
0x14000e83a  call    memset_0
0x14000e83f  lea     rcx, [rsp+2A0h+VersionInformation]; lpVersionInformation
0x14000e844  mov     [rsp+2A0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x14000e84c  call    cs:__imp_RtlGetVersion
0x14000e852  test    eax, eax
0x14000e854  jns     short loc_14000E871
0x14000e856  lea     rcx, [rsp+2A0h+VersionInformation]; lpVersionInformation
0x14000e85b  mov     [rsp+2A0h+VersionInformation.dwOSVersionInfoSize], 114h
0x14000e863  call    cs:__imp_RtlGetVersion
0x14000e869  test    eax, eax
0x14000e86b  js      loc_14000E90F
0x14000e871  movzx   eax, [rbp+1A0h+var_116]
0x14000e878  lea     r9, aAmd64; "amd64"
0x14000e87f  movzx   ecx, [rbp+1A0h+var_118]
0x14000e886  movzx   edx, [rbp+1A0h+var_11A]
0x14000e88d  movzx   r8d, [rbp+1A0h+var_11C]
0x14000e895  mov     [rsp+2A0h+var_250], r9
0x14000e89a  mov     r9d, [rsp+2A0h+VersionInformation.dwMajorVersion]
0x14000e89f  mov     [rsp+2A0h+var_258], eax
0x14000e8a3  mov     eax, [rsp+2A0h+VersionInformation.dwBuildNumber]
0x14000e8a7  mov     [rsp+2A0h+var_260], ecx
0x14000e8ab  lea     rcx, [rbp+1A0h+pszDest]; pszDest
0x14000e8b2  mov     [rsp+2A0h+var_268], edx
0x14000e8b6  mov     edx, 0FFh; cchDest
0x14000e8bb  mov     [rsp+2A0h+var_270], r8d
0x14000e8c0  lea     r8, aDeviceInstallL; "[Device Install Log]\r\n     OS Version"...
0x14000e8c7  mov     [rsp+2A0h+var_278], eax
0x14000e8cb  mov     eax, [rsp+2A0h+VersionInformation.dwMinorVersion]
0x14000e8cf  mov     dword ptr [rsp+2A0h+lpOverlapped], eax
0x14000e8d3  call    StringCchPrintfA
0x14000e8d8  test    eax, eax
0x14000e8da  js      short loc_14000E90F
0x14000e8dc  lea     rax, [rbp+1A0h+pszDest]
0x14000e8e3  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000e8e7  inc     r8; nNumberOfBytesToWrite
0x14000e8ea  cmp     byte ptr [rax+r8], 0
0x14000e8ef  jnz     short loc_14000E8E7
0x14000e8f1  lea     r9, [rsp+2A0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14000e8f6  mov     [rsp+2A0h+lpOverlapped], 0; lpOverlapped
0x14000e8ff  lea     rdx, [rbp+1A0h+pszDest]; lpBuffer
0x14000e906  mov     rcx, rbx; hFile
0x14000e909  call    cs:__imp_WriteFile
0x14000e90f  mov     rcx, [rbp+1A0h+var_10]
0x14000e916  xor     rcx, rsp; StackCookie
0x14000e919  call    __security_check_cookie
0x14000e91e  mov     rbx, [rsp+2A0h+arg_8]
0x14000e926  add     rsp, 2A0h
0x14000e92d  pop     rbp
0x14000e92e  retn
```
