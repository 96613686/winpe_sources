# CopyFileTimes

- ea: `0x18001fdd0`
- end: `0x18001ff16`
- name: `CopyFileTimes`
- size: `326`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPCWSTR)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x18001f6cc`

## callees

- `0x180003410`
- `0x180008e00`
- `0x18001fdd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fec4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fec4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001fe29`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001fe29`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18001fe7b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18001fe7b`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18001feba`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18001feba`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18001fe67`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18001fe67`

## string_xrefs

- `0x18001fe5e`: `CopyFileTimes`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CopyFileTimes(LPCWSTR lpFileName, LPCWSTR a2)
{
  HANDLE FileW; // rbx
  signed int LastError; // eax
  int v5; // r8d
  unsigned int v6; // ebx
  HANDLE v8; // [rsp+40h] [rbp-48h] BYREF
  __int128 FileInformation; // [rsp+48h] [rbp-40h] BYREF
  FILETIME LastWriteTime[2]; // [rsp+58h] [rbp-30h] BYREF
  int v11; // [rsp+68h] [rbp-20h]

  FileInformation = 0;
  *(_OWORD *)&LastWriteTime[0].dwLowDateTime = 0;
  v11 = 0;
  FileW = CreateFileW(a2, 0x100u, 1u, 0, 3u, 0x80u, 0);
  v8 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    v5 = 594;
  }
  else if ( GetFileAttributesExW(lpFileName, GetFileExInfoStandard, &FileInformation) )
  {
    if ( SetFileTime(
           FileW,
           (const FILETIME *)((char *)&FileInformation + 4),
           (const FILETIME *)((char *)&FileInformation + 12),
           (const FILETIME *)&LastWriteTime[0].dwHighDateTime) )
    {
      v6 = 0;
      goto LABEL_21;
    }
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    v5 = 597;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    v5 = 596;
  }
  v6 = ZTraceReportOriginationNoThis(LastError, "CopyFileTimes", v5);
LABEL_21:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v8);
  return v6;
}

```

## disassembly

```asm
0x18001fdd0  mov     [rsp+arg_10], rbx
0x18001fdd5  push    rdi
0x18001fdd6  sub     rsp, 80h
0x18001fddd  mov     rax, cs:__security_cookie
0x18001fde4  xor     rax, rsp
0x18001fde7  mov     [rsp+88h+var_18], rax
0x18001fdec  mov     rax, rdx
0x18001fdef  mov     rdi, rcx
0x18001fdf2  xorps   xmm0, xmm0
0x18001fdf5  xor     ecx, ecx
0x18001fdf7  movups  [rsp+88h+FileInformation], xmm0
0x18001fdfc  movups  xmmword ptr [rsp+88h+LastWriteTime.dwLowDateTime], xmm0
0x18001fe01  mov     [rsp+88h+var_20], ecx
0x18001fe05  mov     [rsp+88h+hTemplateFile], rcx; hTemplateFile
0x18001fe0a  mov     [rsp+88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001fe12  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x18001fe1a  xor     r9d, r9d; lpSecurityAttributes
0x18001fe1d  mov     edx, 100h; dwDesiredAccess
0x18001fe22  lea     r8d, [rcx+1]; dwShareMode
0x18001fe26  mov     rcx, rax; lpFileName
0x18001fe29  call    cs:__imp_CreateFileW
0x18001fe2f  mov     rbx, rax
0x18001fe32  mov     [rsp+88h+var_48], rax
0x18001fe37  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001fe3b  jnz     short loc_18001FE71
0x18001fe3d  call    cs:__imp_GetLastError
0x18001fe43  test    eax, eax
0x18001fe45  jz      short loc_18001FE53
0x18001fe47  jle     short loc_18001FE58
0x18001fe49  movzx   eax, ax
0x18001fe4c  or      eax, 80070000h
0x18001fe51  jmp     short loc_18001FE58
0x18001fe53  mov     eax, 80390004h
0x18001fe58  mov     r8d, 252h
0x18001fe5e  lea     rdx, aCopyfiletimes; "CopyFileTimes"
0x18001fe65  mov     ecx, eax
0x18001fe67  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18001fe6d  mov     ebx, eax
0x18001fe6f  jmp     short loc_18001FEEC
0x18001fe71  lea     r8, [rsp+88h+FileInformation]; lpFileInformation
0x18001fe76  xor     edx, edx; fInfoLevelId
0x18001fe78  mov     rcx, rdi; lpFileName
0x18001fe7b  call    cs:__imp_GetFileAttributesExW
0x18001fe81  test    eax, eax
0x18001fe83  jnz     short loc_18001FEA8
0x18001fe85  call    cs:__imp_GetLastError
0x18001fe8b  test    eax, eax
0x18001fe8d  jz      short loc_18001FE9B
0x18001fe8f  jle     short loc_18001FEA0
0x18001fe91  movzx   eax, ax
0x18001fe94  or      eax, 80070000h
0x18001fe99  jmp     short loc_18001FEA0
0x18001fe9b  mov     eax, 80390004h
0x18001fea0  mov     r8d, 254h
0x18001fea6  jmp     short loc_18001FE5E
0x18001fea8  lea     r9, [rsp+88h+LastWriteTime.dwHighDateTime]; lpLastWriteTime
0x18001fead  lea     r8, [rsp+88h+FileInformation+0Ch]; lpLastAccessTime
0x18001feb2  lea     rdx, [rsp+88h+FileInformation+4]; lpCreationTime
0x18001feb7  mov     rcx, rbx; hFile
0x18001feba  call    cs:__imp_SetFileTime
0x18001fec0  test    eax, eax
0x18001fec2  jnz     short loc_18001FEEA
0x18001fec4  call    cs:__imp_GetLastError
0x18001feca  test    eax, eax
0x18001fecc  jz      short loc_18001FEDA
0x18001fece  jle     short loc_18001FEDF
0x18001fed0  movzx   eax, ax
0x18001fed3  or      eax, 80070000h
0x18001fed8  jmp     short loc_18001FEDF
0x18001feda  mov     eax, 80390004h
0x18001fedf  mov     r8d, 255h
0x18001fee5  jmp     loc_18001FE5E
0x18001feea  xor     ebx, ebx
0x18001feec  lea     rcx, [rsp+88h+var_48]
0x18001fef1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001fef6  mov     eax, ebx
0x18001fef8  mov     rcx, [rsp+88h+var_18]
0x18001fefd  xor     rcx, rsp; StackCookie
0x18001ff00  call    __security_check_cookie
0x18001ff05  mov     rbx, [rsp+88h+arg_10]
0x18001ff0d  add     rsp, 80h
0x18001ff14  pop     rdi
0x18001ff15  retn
```
