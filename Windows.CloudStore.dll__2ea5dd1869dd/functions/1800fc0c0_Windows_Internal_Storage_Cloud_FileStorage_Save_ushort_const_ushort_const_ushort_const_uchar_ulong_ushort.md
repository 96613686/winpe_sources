# Windows::Internal::Storage::Cloud::FileStorage::Save(ushort const *,ushort const *,ushort const *,uchar *,ulong,ushort * *)

- ea: `0x1800fc0c0`
- end: `0x1800fc313`
- name: `?Save@FileStorage@Cloud@Storage@Internal@Windows@@UEAAJPEBG00PEAEKPEAPEAG@Z`
- size: `595`
- prototype: `__int64 __fastcall(wil **this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800320d4`
- `0x18003b488`
- `0x18003bb30`
- `0x18004436c`
- `0x18007ae70`
- `0x1800c8458`
- `0x1800fc0c0`
- `0x1800fc644`
- `0x1801201a0`
- `0x1801a8e60`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800fc22d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800fc22d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800fc272`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800fc272`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800fc115`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800fc115`

## string_xrefs

- `0x1800fc126`: `onecoreuap\shell\cloudstore\store\cache\src\filestorage.cpp`
- `0x1800fc27f`: `onecoreuap\shell\cloudstore\store\cache\src\filestorage.cpp`
- `0x1800fc2a9`: `onecoreuap\shell\cloudstore\store\cache\src\filestorage.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Storage::Cloud::FileStorage::Save(
        wil **this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        LPCVOID lpBuffer,
        DWORD nNumberOfBytesToWrite,
        unsigned __int16 **a7)
{
  HRESULT DirectoryDeepNoThrow; // ebx
  __int64 v9; // rdx
  const unsigned __int16 *v10; // rdx
  unsigned __int64 v11; // r9
  HANDLE FileW; // rax
  const char *v13; // r9
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r9
  __int64 v18; // rdx
  int v19; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  DWORD NumberOfBytesWritten; // [rsp+70h] [rbp-90h] BYREF
  HANDLE hFile; // [rsp+78h] [rbp-88h] BYREF
  GUID pguid; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v26[40]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR FileName[264]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+228h]

  *a7 = 0;
  pguid = 0;
  DirectoryDeepNoThrow = CoCreateGuid(&pguid);
  if ( DirectoryDeepNoThrow >= 0 )
  {
    dwCreationDisposition = pguid.Data2;
    DirectoryDeepNoThrow = StringCchPrintfW(v26, 0x28u, L"%08X%04X%04X%02X%02X%02X%02X%02X%02X%02X%02X", pguid.Data1);
    if ( DirectoryDeepNoThrow < 0 )
    {
      v9 = 107;
      goto LABEL_3;
    }
    DirectoryDeepNoThrow = wil::CreateDirectoryDeepNoThrow(this[2], v10);
    if ( DirectoryDeepNoThrow < 0 )
    {
      v9 = 109;
      goto LABEL_3;
    }
    DirectoryDeepNoThrow = Windows::Internal::Storage::Cloud::FileStorage::GetFileName(
                             (Windows::Internal::Storage::Cloud::FileStorage *)this,
                             v26,
                             FileName,
                             v11);
    if ( DirectoryDeepNoThrow < 0 )
    {
      v9 = 112;
      goto LABEL_3;
    }
    hFile = (HANDLE)-1LL;
    FileW = CreateFileW(FileName, 0x40000000u, 2u, 0, 1u, 0x80u, 0);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hFile,
      FileW);
    if ( hFile == (HANDLE)-1LL )
    {
      v14 = 123;
    }
    else
    {
      NumberOfBytesWritten = 0;
      if ( WriteFile(hFile, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
      {
        if ( NumberOfBytesWritten == nNumberOfBytesToWrite )
        {
          v19 = _AllocString<CTCoAllocPolicy>(v16, v15, v26, a7);
          DirectoryDeepNoThrow = v19;
          if ( v19 >= 0 )
          {
            DirectoryDeepNoThrow = 0;
            goto LABEL_21;
          }
          v17 = (unsigned int)v19;
          v18 = 129;
        }
        else
        {
          DirectoryDeepNoThrow = -2147467259;
          v17 = 2147500037LL;
          v18 = 127;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\filestorage.cpp",
          (const char *)v17,
          dwCreationDispositiona);
LABEL_21:
        std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>(&hFile);
        return (unsigned int)DirectoryDeepNoThrow;
      }
      v14 = 126;
    }
    DirectoryDeepNoThrow = wil::details::in1diag3::Return_GetLastError(
                             retaddr,
                             (void *)v14,
                             (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\filestorage.cpp",
                             v13);
    goto LABEL_21;
  }
  v9 = 100;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\filestorage.cpp",
    (const char *)(unsigned int)DirectoryDeepNoThrow,
    dwCreationDisposition);
  return (unsigned int)DirectoryDeepNoThrow;
}

```

## disassembly

```asm
0x1800fc0c0  mov     [rsp-8+arg_8], rbx
0x1800fc0c5  mov     [rsp-8+arg_10], rsi
0x1800fc0ca  push    rbp
0x1800fc0cb  push    rdi
0x1800fc0cc  push    r12
0x1800fc0ce  push    r14
0x1800fc0d0  push    r15
0x1800fc0d2  lea     rbp, [rsp-200h]
0x1800fc0da  sub     rsp, 300h
0x1800fc0e1  mov     rax, cs:__security_cookie
0x1800fc0e8  xor     rax, rsp
0x1800fc0eb  mov     [rbp+220h+var_30], rax
0x1800fc0f2  mov     r14, rcx
0x1800fc0f5  mov     r12, [rbp+220h+lpBuffer]
0x1800fc0fc  mov     r15, [rbp+220h+arg_30]
0x1800fc103  mov     qword ptr [r15], 0
0x1800fc10a  xorps   xmm0, xmm0
0x1800fc10d  movups  xmmword ptr [rbp+220h+pguid.Data1], xmm0
0x1800fc111  lea     rcx, [rbp+220h+pguid]; pguid
0x1800fc115  call    cs:__imp_CoCreateGuid
0x1800fc11b  mov     ebx, eax
0x1800fc11d  test    eax, eax
0x1800fc11f  jns     short loc_1800FC141
0x1800fc121  mov     edx, 64h ; 'd'; void *
0x1800fc126  lea     r8, aOnecoreuapShel_103; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1800fc12d  mov     r9d, ebx; char *
0x1800fc130  mov     rcx, [rbp+228h]; this
0x1800fc137  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fc13c  jmp     loc_1800FC2E6
0x1800fc141  movzx   eax, [rbp+220h+pguid.Data4+7]
0x1800fc145  movzx   ecx, [rbp+220h+pguid.Data4+6]
0x1800fc149  movzx   edx, [rbp+220h+pguid.Data4+5]
0x1800fc14d  movzx   r8d, [rbp+220h+pguid.Data4+4]
0x1800fc152  movzx   r9d, [rbp+220h+pguid.Data4+3]
0x1800fc157  movzx   r10d, [rbp+220h+pguid.Data4+2]
0x1800fc15c  movzx   r11d, [rbp+220h+pguid.Data4+1]
0x1800fc161  movzx   ebx, [rbp+220h+pguid.Data4]
0x1800fc165  movzx   edi, [rbp+220h+pguid.Data3]
0x1800fc169  movzx   esi, [rbp+220h+pguid.Data2]
0x1800fc16d  mov     [rsp+320h+var_2B8], eax
0x1800fc171  mov     [rsp+320h+var_2C0], ecx
0x1800fc175  mov     [rsp+320h+var_2C8], edx
0x1800fc179  mov     [rsp+320h+var_2D0], r8d
0x1800fc17e  mov     [rsp+320h+var_2D8], r9d
0x1800fc183  mov     [rsp+320h+var_2E0], r10d
0x1800fc188  mov     [rsp+320h+var_2E8], r11d
0x1800fc18d  mov     dword ptr [rsp+320h+hTemplateFile], ebx
0x1800fc191  mov     [rsp+320h+dwFlagsAndAttributes], edi
0x1800fc195  mov     [rsp+320h+dwCreationDisposition], esi
0x1800fc199  mov     r9d, [rbp+220h+pguid.Data1]
0x1800fc19d  lea     r8, a08x04x04x02x02; "%08X%04X%04X%02X%02X%02X%02X%02X%02X%02"...
0x1800fc1a4  mov     edx, 28h ; '('; unsigned __int64
0x1800fc1a9  lea     rcx, [rbp+220h+var_290]; unsigned __int16 *
0x1800fc1ad  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800fc1b2  mov     ebx, eax
0x1800fc1b4  test    eax, eax
0x1800fc1b6  jns     short loc_1800FC1C2
0x1800fc1b8  mov     edx, 6Bh ; 'k'
0x1800fc1bd  jmp     loc_1800FC126
0x1800fc1c2  mov     rcx, [r14+10h]; this
0x1800fc1c6  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x1800fc1cb  mov     ebx, eax
0x1800fc1cd  test    eax, eax
0x1800fc1cf  jns     short loc_1800FC1DB
0x1800fc1d1  mov     edx, 6Dh ; 'm'
0x1800fc1d6  jmp     loc_1800FC126
0x1800fc1db  lea     r8, [rbp+220h+FileName]; unsigned __int16 *
0x1800fc1df  lea     rdx, [rbp+220h+var_290]; unsigned __int16 *
0x1800fc1e3  mov     rcx, r14; this
0x1800fc1e6  call    ?GetFileName@FileStorage@Cloud@Storage@Internal@Windows@@AEAAJPEBGPEAG_K@Z; Windows::Internal::Storage::Cloud::FileStorage::GetFileName(ushort const *,ushort *,unsigned __int64)
0x1800fc1eb  mov     ebx, eax
0x1800fc1ed  test    eax, eax
0x1800fc1ef  jns     short loc_1800FC1FB
0x1800fc1f1  mov     edx, 70h ; 'p'
0x1800fc1f6  jmp     loc_1800FC126
0x1800fc1fb  mov     [rsp+320h+hFile], 0FFFFFFFFFFFFFFFFh
0x1800fc204  mov     [rsp+320h+hTemplateFile], 0; hTemplateFile
0x1800fc20d  mov     [rsp+320h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800fc215  mov     [rsp+320h+dwCreationDisposition], 1; dwCreationDisposition
0x1800fc21d  xor     r9d, r9d; lpSecurityAttributes
0x1800fc220  mov     edx, 40000000h; dwDesiredAccess
0x1800fc225  lea     r8d, [r9+2]; dwShareMode
0x1800fc229  lea     rcx, [rbp+220h+FileName]; lpFileName
0x1800fc22d  call    cs:__imp_CreateFileW
0x1800fc233  mov     rdx, rax
0x1800fc236  lea     rcx, [rsp+320h+hFile]
0x1800fc23b  call    ?reset@?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800fc240  mov     rcx, [rsp+320h+hFile]; hFile
0x1800fc245  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800fc249  jnz     short loc_1800FC250
0x1800fc24b  lea     edx, [rcx+7Ch]
0x1800fc24e  jmp     short loc_1800FC27F
0x1800fc250  mov     [rsp+320h+NumberOfBytesWritten], 0
0x1800fc258  mov     qword ptr [rsp+320h+dwCreationDisposition], 0; int
0x1800fc261  lea     r9, [rsp+320h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800fc266  mov     ebx, [rbp+220h+nNumberOfBytesToWrite]
0x1800fc26c  mov     r8d, ebx; nNumberOfBytesToWrite
0x1800fc26f  mov     rdx, r12; lpBuffer
0x1800fc272  call    cs:__imp_WriteFile
0x1800fc278  test    eax, eax
0x1800fc27a  jnz     short loc_1800FC296
0x1800fc27c  lea     edx, [rax+7Eh]; void *
0x1800fc27f  lea     r8, aOnecoreuapShel_103; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1800fc286  mov     rcx, [rbp+228h]; this
0x1800fc28d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800fc292  mov     ebx, eax
0x1800fc294  jmp     short loc_1800FC2DC
0x1800fc296  cmp     [rsp+320h+NumberOfBytesWritten], ebx
0x1800fc29a  jz      short loc_1800FC2BE
0x1800fc29c  mov     ebx, 80004005h
0x1800fc2a1  mov     r9d, ebx; char *
0x1800fc2a4  mov     edx, 7Fh; void *
0x1800fc2a9  lea     r8, aOnecoreuapShel_103; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1800fc2b0  mov     rcx, [rbp+228h]; this
0x1800fc2b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fc2bc  jmp     short loc_1800FC2DC
0x1800fc2be  mov     r9, r15
0x1800fc2c1  lea     r8, [rbp+220h+var_290]
0x1800fc2c5  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800fc2ca  mov     ebx, eax
0x1800fc2cc  test    eax, eax
0x1800fc2ce  jns     short loc_1800FC2DA
0x1800fc2d0  mov     r9d, eax
0x1800fc2d3  mov     edx, 81h
0x1800fc2d8  jmp     short loc_1800FC2A9
0x1800fc2da  xor     ebx, ebx
0x1800fc2dc  lea     rcx, [rsp+320h+hFile]
0x1800fc2e1  call    ??1?$pair@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@_N@std@@QEAA@XZ; std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,bool>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,bool>(void)
0x1800fc2e6  mov     eax, ebx
0x1800fc2e8  mov     rcx, [rbp+220h+var_30]
0x1800fc2ef  xor     rcx, rsp; StackCookie
0x1800fc2f2  call    __security_check_cookie
0x1800fc2f7  lea     r11, [rsp+320h+var_20]
0x1800fc2ff  mov     rbx, [r11+38h]
0x1800fc303  mov     rsi, [r11+40h]
0x1800fc307  mov     rsp, r11
0x1800fc30a  pop     r15
0x1800fc30c  pop     r14
0x1800fc30e  pop     r12
0x1800fc310  pop     rdi
0x1800fc311  pop     rbp
0x1800fc312  retn
```
