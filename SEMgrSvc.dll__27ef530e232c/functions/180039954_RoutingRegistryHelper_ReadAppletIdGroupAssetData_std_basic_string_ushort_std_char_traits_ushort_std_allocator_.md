# RoutingRegistryHelper::ReadAppletIdGroupAssetData(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,uint *,uchar * *)

- ea: `0x180039954`
- end: `0x180039af6`
- name: `?ReadAppletIdGroupAssetData@RoutingRegistryHelper@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAIPEAPEAE@Z`
- size: `418`
- prototype: `__int64 __fastcall(const WCHAR *, DWORD *, LPVOID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18003f990`

## callees

- `0x18000c944`
- `0x18000c964`
- `0x18003806c`
- `0x180039954`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039a95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039a95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800399fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039ae1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800399fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039ae1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180039998`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180039998`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800399d5`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800399d5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180039a5f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180039a5f`

## string_xrefs

- `0x1800399af`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingregistryhelper.cpp`
- `0x1800399e3`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingregistryhelper.cpp`
- `0x180039a21`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingregistryhelper.cpp`
- `0x180039a6d`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingregistryhelper.cpp`
- `0x180039ab5`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingregistryhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RoutingRegistryHelper::ReadAppletIdGroupAssetData(const WCHAR *a1, DWORD *a2, LPVOID *a3)
{
  HANDLE FileW; // rax
  const char *v6; // r9
  void *v7; // rbx
  const char *v9; // r9
  unsigned int LastError; // edi
  const char *v11; // r9
  void *v12; // rcx
  int dwCreationDisposition; // [rsp+20h] [rbp-30h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-30h]
  union _LARGE_INTEGER FileSize; // [rsp+40h] [rbp-10h] BYREF
  HANDLE v16; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  DWORD NumberOfBytesRead; // [rsp+70h] [rbp+20h] BYREF
  LPVOID lpBuffer; // [rsp+88h] [rbp+38h] BYREF

  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(const WCHAR **)a1;
  FileW = CreateFileW(a1, 0x120089u, 1u, 0, 3u, 0, 0);
  v7 = FileW;
  v16 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x424,
             (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingregistryhelper.cpp",
             v6);
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(FileW, &FileSize) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x427,
                  (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingregistryhelper.cpp",
                  v9);
LABEL_7:
    if ( v7 )
      CloseHandle(v7);
    return LastError;
  }
  if ( FileSize.QuadPart > 0x80000 )
  {
    LastError = -2147483637;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x428,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingregistryhelper.cpp",
      (const char *)0x8000000BLL,
      dwCreationDisposition);
    goto LABEL_7;
  }
  wil::make_unique_cotaskmem<unsigned char [0]>(&lpBuffer, FileSize.LowPart);
  NumberOfBytesRead = 0;
  if ( !ReadFile(v7, lpBuffer, FileSize.LowPart, &NumberOfBytesRead, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x42D,
                  (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingregistryhelper.cpp",
                  v11);
    goto LABEL_14;
  }
  if ( NumberOfBytesRead != FileSize.LowPart )
  {
    LastError = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42E,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingregistryhelper.cpp",
      (const char *)0x8000FFFFLL,
      dwCreationDispositiona);
LABEL_14:
    v12 = lpBuffer;
    lpBuffer = 0;
    if ( v12 )
      CoTaskMemFree(v12);
    goto LABEL_7;
  }
  *a2 = FileSize.LowPart;
  *a3 = lpBuffer;
  lpBuffer = 0;
  if ( v7 )
    CloseHandle(v7);
  return 0;
}

```

## disassembly

```asm
0x180039954  mov     [rsp-18h+arg_8], rbx
0x180039959  push    rbp
0x18003995a  push    rsi
0x18003995b  push    rdi
0x18003995c  mov     rbp, rsp
0x18003995f  sub     rsp, 50h
0x180039963  mov     rdi, r8
0x180039966  mov     rsi, rdx
0x180039969  cmp     qword ptr [rcx+18h], 7
0x18003996e  jbe     short loc_180039973
0x180039970  mov     rcx, [rcx]; lpFileName
0x180039973  mov     [rsp+50h+hTemplateFile], 0; hTemplateFile
0x18003997c  mov     [rsp+50h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180039984  mov     [rsp+50h+dwCreationDisposition], 3; int
0x18003998c  xor     r9d, r9d; lpSecurityAttributes
0x18003998f  mov     edx, 120089h; dwDesiredAccess
0x180039994  lea     r8d, [r9+1]; dwShareMode
0x180039998  call    cs:__imp_CreateFileW
0x18003999e  mov     rbx, rax
0x1800399a1  mov     [rbp+var_8], rax
0x1800399a5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800399a9  jnz     short loc_1800399C6
0x1800399ab  mov     rcx, [rbp+18h]; this
0x1800399af  lea     r8, aOnecoreuapDsNf_45; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x1800399b6  mov     edx, 424h; void *
0x1800399bb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800399c0  nop
0x1800399c1  jmp     loc_180039AE9
0x1800399c6  mov     qword ptr [rbp+FileSize], 0
0x1800399ce  lea     rdx, [rbp+FileSize]; lpFileSize
0x1800399d2  mov     rcx, rbx; hFile
0x1800399d5  call    cs:__imp_GetFileSizeEx
0x1800399db  test    eax, eax
0x1800399dd  jnz     short loc_180039A0B
0x1800399df  mov     rcx, [rbp+18h]; this
0x1800399e3  lea     r8, aOnecoreuapDsNf_45; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x1800399ea  mov     edx, 427h; void *
0x1800399ef  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800399f4  mov     edi, eax
0x1800399f6  test    rbx, rbx
0x1800399f9  jz      short loc_180039A04
0x1800399fb  mov     rcx, rbx; hObject
0x1800399fe  call    cs:__imp_CloseHandle
0x180039a04  mov     eax, edi
0x180039a06  jmp     loc_180039AE9
0x180039a0b  cmp     qword ptr [rbp+FileSize], 80000h
0x180039a13  jle     short loc_180039A34
0x180039a15  mov     rcx, [rbp+18h]; this
0x180039a19  mov     edi, 8000000Bh
0x180039a1e  mov     r9d, edi; char *
0x180039a21  lea     r8, aOnecoreuapDsNf_45; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x180039a28  mov     edx, 428h; void *
0x180039a2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039a32  jmp     short loc_1800399F6
0x180039a34  mov     edx, dword ptr [rbp+FileSize]
0x180039a37  lea     rcx, [rbp+lpBuffer]
0x180039a3b  call    ??$make_unique_cotaskmem@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<uchar [0]>(unsigned __int64)
0x180039a40  mov     [rbp+NumberOfBytesRead], 0
0x180039a47  mov     qword ptr [rsp+50h+dwCreationDisposition], 0; int
0x180039a50  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180039a54  mov     r8d, dword ptr [rbp+FileSize]; nNumberOfBytesToRead
0x180039a58  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x180039a5c  mov     rcx, rbx; hFile
0x180039a5f  call    cs:__imp_ReadFile
0x180039a65  test    eax, eax
0x180039a67  jnz     short loc_180039AA0
0x180039a69  mov     rcx, [rbp+18h]; this
0x180039a6d  lea     r8, aOnecoreuapDsNf_45; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x180039a74  mov     edx, 42Dh; void *
0x180039a79  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180039a7e  mov     edi, eax
0x180039a80  mov     rcx, [rbp+lpBuffer]; pv
0x180039a84  mov     [rbp+lpBuffer], 0
0x180039a8c  test    rcx, rcx
0x180039a8f  jz      loc_1800399F6
0x180039a95  call    cs:__imp_CoTaskMemFree
0x180039a9b  jmp     loc_1800399F6
0x180039aa0  mov     rax, qword ptr [rbp+FileSize]
0x180039aa4  cmp     [rbp+NumberOfBytesRead], eax
0x180039aa7  jz      short loc_180039AC8
0x180039aa9  mov     rcx, [rbp+18h]; this
0x180039aad  mov     edi, 8000FFFFh
0x180039ab2  mov     r9d, edi; char *
0x180039ab5  lea     r8, aOnecoreuapDsNf_45; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x180039abc  mov     edx, 42Eh; void *
0x180039ac1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039ac6  jmp     short loc_180039A80
0x180039ac8  mov     [rsi], eax
0x180039aca  mov     rax, [rbp+lpBuffer]
0x180039ace  mov     [rdi], rax
0x180039ad1  mov     [rbp+lpBuffer], 0
0x180039ad9  test    rbx, rbx
0x180039adc  jz      short loc_180039AE7
0x180039ade  mov     rcx, rbx; hObject
0x180039ae1  call    cs:__imp_CloseHandle
0x180039ae7  xor     eax, eax
0x180039ae9  mov     rbx, [rsp+50h+arg_8]
0x180039aee  add     rsp, 50h
0x180039af2  pop     rdi
0x180039af3  pop     rsi
0x180039af4  pop     rbp
0x180039af5  retn
```
