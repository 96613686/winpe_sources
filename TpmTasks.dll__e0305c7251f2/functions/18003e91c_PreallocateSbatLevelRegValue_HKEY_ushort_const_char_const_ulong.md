# PreallocateSbatLevelRegValue(HKEY__ *,ushort const *,char const *,ulong)

- ea: `0x18003e91c`
- end: `0x18003eac0`
- name: `?PreallocateSbatLevelRegValue@@YAJPEAUHKEY__@@PEBGPEBDK@Z`
- size: `420`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpFileName, const char *Source, rsize_t SourceSize)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18003e6ac`

## callees

- `0x1800085d4`
- `0x180011400`
- `0x18001a42c`
- `0x18001a450`
- `0x180025de0`
- `0x18002b4c0`
- `0x18003e91c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18003e985`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18003e985`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003e95f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003e95f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e9c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e9c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003e9d2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003e9d2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ea46`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ea46`

## pseudocode

```c
__int64 __fastcall PreallocateSbatLevelRegValue(HKEY hKey, LPCWSTR lpFileName, const char *Source, rsize_t SourceSize)
{
  rsize_t v4; // rbp
  char *FileW; // rax
  DWORD LowPart; // eax
  DWORD v9; // esi
  __int64 v10; // rdx
  HANDLE ProcessHeap; // rax
  void *v12; // rdi
  unsigned int v13; // ebx
  void *v14; // rdx
  unsigned int v15; // eax
  void *v16; // rdx
  void *v17; // rdx
  int dwCreationDisposition; // [rsp+20h] [rbp-68h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-68h]
  union _LARGE_INTEGER FileSize; // [rsp+40h] [rbp-48h] BYREF
  char *v22; // [rsp+48h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v4 = (unsigned int)SourceSize;
  FileW = (char *)CreateFileW(lpFileName, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  v22 = FileW;
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    goto LABEL_8;
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(FileW, &FileSize) )
    goto LABEL_8;
  LowPart = FileSize.LowPart;
  if ( FileSize.QuadPart > 0x4000 )
    LowPart = 0x4000;
  if ( LowPart > (unsigned int)v4 )
  {
    v9 = LowPart + 20;
    if ( LowPart >= 0xFFFFFFEC )
    {
      v10 = 228;
LABEL_17:
      v13 = -2147024362;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\base\\secureboot\\servicing\\lib\\sbatservicing.cpp",
        (const char *)0x80070216LL,
        dwCreationDisposition);
      goto LABEL_18;
    }
  }
  else
  {
LABEL_8:
    v9 = v4 + 20;
    if ( (unsigned int)v4 >= 0xFFFFFFEC )
    {
      v10 = 232;
      goto LABEL_17;
    }
  }
  ProcessHeap = GetProcessHeap();
  v12 = HeapAlloc(ProcessHeap, 8u, v9);
  if ( v12 )
  {
    memset_0(v12, 32, v9 - 1);
    if ( memcpy_s(v12, v9 - 1, Source, v4) )
    {
      wil::details::FreeProcessHeap((wil::details *)v12, v14);
      v13 = -2147467259;
    }
    else
    {
      *((_BYTE *)v12 + v4) = 32;
      v15 = RegSetValueExW(hKey, L"SbatLevel", 0, 3u, (const BYTE *)v12, v9);
      if ( v15 )
      {
        v13 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0xFD,
                (unsigned int)"onecore\\base\\secureboot\\servicing\\lib\\sbatservicing.cpp",
                (const char *)v15,
                dwCreationDispositiona);
        wil::details::FreeProcessHeap((wil::details *)v12, v17);
      }
      else
      {
        wil::details::FreeProcessHeap((wil::details *)v12, v16);
        v13 = 0;
      }
    }
  }
  else
  {
    v13 = -2147024882;
  }
LABEL_18:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v22);
  return v13;
}

```

## disassembly

```asm
0x18003e91c  push    rbx
0x18003e91e  push    rbp
0x18003e91f  push    rsi
0x18003e920  push    rdi
0x18003e921  push    r12
0x18003e923  push    r14
0x18003e925  push    r15
0x18003e927  sub     rsp, 50h
0x18003e92b  mov     rax, rdx
0x18003e92e  mov     ebp, r9d
0x18003e931  xor     r9d, r9d; lpSecurityAttributes
0x18003e934  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x18003e93d  mov     r12, r8
0x18003e940  mov     [rsp+88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003e948  mov     r15, rcx
0x18003e94b  mov     [rsp+88h+dwCreationDisposition], 3; int
0x18003e953  mov     edx, 80000000h; dwDesiredAccess
0x18003e958  mov     rcx, rax; lpFileName
0x18003e95b  lea     r8d, [r9+7]; dwShareMode
0x18003e95f  call    cs:__imp_CreateFileW
0x18003e965  mov     [rsp+88h+var_40], rax
0x18003e96a  lea     rcx, [rax-1]
0x18003e96e  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18003e972  ja      short loc_18003E9B5
0x18003e974  lea     rdx, [rsp+88h+FileSize]; lpFileSize
0x18003e979  mov     qword ptr [rsp+88h+FileSize], 0
0x18003e982  mov     rcx, rax; hFile
0x18003e985  call    cs:__imp_GetFileSizeEx
0x18003e98b  test    eax, eax
0x18003e98d  jz      short loc_18003E9B5
0x18003e98f  mov     rax, qword ptr [rsp+88h+FileSize]
0x18003e994  mov     ecx, 4000h
0x18003e999  cmp     rax, rcx
0x18003e99c  cmovg   eax, ecx
0x18003e99f  cmp     eax, ebp
0x18003e9a1  jbe     short loc_18003E9B5
0x18003e9a3  lea     esi, [rax+14h]
0x18003e9a6  cmp     esi, 14h
0x18003e9a9  jnb     short loc_18003E9C1
0x18003e9ab  mov     edx, 0E4h
0x18003e9b0  jmp     loc_18003EA89
0x18003e9b5  lea     esi, [rbp+14h]
0x18003e9b8  cmp     esi, 14h
0x18003e9bb  jb      loc_18003EA84
0x18003e9c1  call    cs:__imp_GetProcessHeap
0x18003e9c7  mov     r8d, esi; dwBytes
0x18003e9ca  mov     edx, 8; dwFlags
0x18003e9cf  mov     rcx, rax; hHeap
0x18003e9d2  call    cs:__imp_HeapAlloc
0x18003e9d8  mov     rdi, rax
0x18003e9db  test    rax, rax
0x18003e9de  jnz     short loc_18003E9EA
0x18003e9e0  mov     ebx, 8007000Eh
0x18003e9e5  jmp     loc_18003EAA5
0x18003e9ea  lea     eax, [rsi-1]
0x18003e9ed  mov     edx, 20h ; ' '; Val
0x18003e9f2  mov     r8d, eax; Size
0x18003e9f5  mov     rcx, rdi; void *
0x18003e9f8  mov     ebx, eax
0x18003e9fa  call    memset_0
0x18003e9ff  mov     r9, rbp; SourceSize
0x18003ea02  mov     r8, r12; Source
0x18003ea05  mov     edx, ebx; DestinationSize
0x18003ea07  mov     rcx, rdi; Destination
0x18003ea0a  call    memcpy_s
0x18003ea0f  test    eax, eax
0x18003ea11  jz      short loc_18003EA25
0x18003ea13  mov     rcx, rdi; this
0x18003ea16  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18003ea1b  mov     ebx, 80004005h
0x18003ea20  jmp     loc_18003EAA5
0x18003ea25  mov     [rsp+88h+dwFlagsAndAttributes], esi; cbData
0x18003ea29  lea     rdx, aSbatlevel; "SbatLevel"
0x18003ea30  mov     r9d, 3; dwType
0x18003ea36  mov     qword ptr [rsp+88h+dwCreationDisposition], rdi; unsigned int
0x18003ea3b  xor     r8d, r8d; Reserved
0x18003ea3e  mov     byte ptr [rbp+rdi+0], 20h ; ' '
0x18003ea43  mov     rcx, r15; hKey
0x18003ea46  call    cs:__imp_RegSetValueExW
0x18003ea4c  test    eax, eax
0x18003ea4e  jz      short loc_18003EA78
0x18003ea50  mov     rcx, [rsp+88h]; this
0x18003ea58  lea     r8, aOnecoreBaseSec_3; "onecore\\base\\secureboot\\servicing\\l"...
0x18003ea5f  mov     r9d, eax; char *
0x18003ea62  mov     edx, 0FDh; void *
0x18003ea67  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003ea6c  mov     rcx, rdi; this
0x18003ea6f  mov     ebx, eax
0x18003ea71  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18003ea76  jmp     short loc_18003EAA5
0x18003ea78  mov     rcx, rdi; this
0x18003ea7b  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18003ea80  xor     ebx, ebx
0x18003ea82  jmp     short loc_18003EAA5
0x18003ea84  mov     edx, 0E8h; void *
0x18003ea89  mov     rcx, [rsp+88h]; this
0x18003ea91  lea     r8, aOnecoreBaseSec_3; "onecore\\base\\secureboot\\servicing\\l"...
0x18003ea98  mov     ebx, 80070216h
0x18003ea9d  mov     r9d, ebx; char *
0x18003eaa0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003eaa5  lea     rcx, [rsp+88h+var_40]
0x18003eaaa  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003eaaf  mov     eax, ebx
0x18003eab1  add     rsp, 50h
0x18003eab5  pop     r15
0x18003eab7  pop     r14
0x18003eab9  pop     r12
0x18003eabb  pop     rdi
0x18003eabc  pop     rsi
0x18003eabd  pop     rbp
0x18003eabe  pop     rbx
0x18003eabf  retn
```
