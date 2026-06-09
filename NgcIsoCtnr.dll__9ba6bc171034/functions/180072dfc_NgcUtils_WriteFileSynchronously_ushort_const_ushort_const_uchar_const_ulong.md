# NgcUtils::WriteFileSynchronously(ushort const *,ushort const *,uchar const *,ulong)

- ea: `0x180072dfc`
- end: `0x180073076`
- name: `?WriteFileSynchronously@NgcUtils@@YAJPEBG0PEBEK@Z`
- size: `634`
- prototype: `__int64 __fastcall(LPCWSTR lpNewFileName, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int8 *, unsigned int)`
- caller_count: `6`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003bf6c`
- `0x18003eee0`
- `0x18003f184`
- `0x18004852c`
- `0x180049e20`
- `0x18004a0e0`

## callees

- `0x180007670`
- `0x18000d60c`
- `0x18000d62c`
- `0x180010360`
- `0x180011c9c`
- `0x18001cbe8`
- `0x180070aec`
- `0x180072af0`
- `0x180072b14`
- `0x180072b54`
- `0x180072dfc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072e62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072e62`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180072f05`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180072f05`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180072f6c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180072f6c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180072e58`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180072e58`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18007301c`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18007301c`
- `ntdll!NtFlushBuffersFileEx` at `0x180072fbe`
- `ntdll!NtFlushBuffersFileEx` at `0x180072fbe`

## string_xrefs

- `0x180072e3e`: `onecore\ds\security\ngc\utils\common\lib\fileutils.cpp`
- `0x180072e71`: `onecore\ds\security\ngc\utils\common\lib\fileutils.cpp`
- `0x180072eb1`: `onecore\ds\security\ngc\utils\common\lib\fileutils.cpp`
- `0x180072f26`: `onecore\ds\security\ngc\utils\common\lib\fileutils.cpp`
- `0x180072f8e`: `onecore\ds\security\ngc\utils\common\lib\fileutils.cpp`
- `0x180072fcf`: `onecore\ds\security\ngc\utils\common\lib\fileutils.cpp`
- `0x180072fed`: `onecore\ds\security\ngc\utils\common\lib\fileutils.cpp`
- `0x18007302a`: `onecore\ds\security\ngc\utils\common\lib\fileutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcUtils::WriteFileSynchronously(
        LPCWSTR lpNewFileName,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int8 *a4)
{
  DWORD v4; // edi
  unsigned int LastError; // ebx
  const char *v8; // r9
  __int64 v10; // r8
  int TemporaryFilePath; // eax
  const WCHAR *v12; // rax
  HANDLE FileW; // rbx
  const char *v14; // r9
  __int64 v15; // rdx
  int v16; // eax
  const WCHAR *v17; // rax
  const char *v18; // r9
  int dwCreationDisposition; // [rsp+20h] [rbp-49h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-49h]
  char **dwCreationDispositionb; // [rsp+20h] [rbp-49h]
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-29h] BYREF
  HANDLE v23; // [rsp+48h] [rbp-21h] BYREF
  _BYTE *v24; // [rsp+50h] [rbp-19h] BYREF
  __int16 v25; // [rsp+58h] [rbp-11h]
  char *v26[2]; // [rsp+60h] [rbp-9h] BYREF
  _BYTE v27[32]; // [rsp+70h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v4 = (unsigned int)a4;
  if ( (unsigned int)a4 > 0x1E84800 )
  {
    LastError = -2147024673;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x96,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\fileutils.cpp",
      (const char *)0x800700DFLL,
      dwCreationDisposition);
    return LastError;
  }
  if ( (_DWORD)a4 )
  {
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v27);
    TemporaryFilePath = NgcUtils::GenerateTemporaryFilePath(v10, v27);
    LastError = TemporaryFilePath;
    if ( TemporaryFilePath < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAC,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\fileutils.cpp",
        (const char *)(unsigned int)TemporaryFilePath,
        dwCreationDisposition);
LABEL_26:
      std::wstring::_Tidy_deallocate(v27);
      return LastError;
    }
    v24 = v27;
    v25 = 256;
    v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27);
    FileW = CreateFileW(v12, 0x40000000u, 0, 0, 2u, 0x80u, 0);
    v23 = FileW;
    if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      NumberOfBytesWritten = 0;
      if ( WriteFile(FileW, a3, v4, &NumberOfBytesWritten, 0) )
      {
        if ( NumberOfBytesWritten == v4 )
        {
          *(_OWORD *)v26 = 0;
          dwCreationDispositionb = v26;
          v16 = NtFlushBuffersFileEx(FileW, 2, 0);
          if ( v16 < 0 )
            wil::details::in1diag3::_Log_NtStatus(
              retaddr,
              (void *)0xDE,
              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\fileutils.cpp",
              (const char *)(unsigned int)v16,
              (int)v26);
          if ( SLODWORD(v26[0]) < 0 )
            wil::details::in1diag3::_Log_NtStatus(
              retaddr,
              (void *)0xDF,
              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\fileutils.cpp",
              (const char *)LODWORD(v26[0]),
              (int)dwCreationDispositionb);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v23);
          v17 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27);
          if ( MoveFileExW(v17, lpNewFileName, 1u) )
          {
            HIBYTE(v25) = 0;
            wil::details::ScopeExitFnGuard__lambda_264642e826a098a243dd793cc2ac5100___::operator()(&v24);
            LastError = 0;
            goto LABEL_26;
          }
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0xE5,
                        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\fileutils.cpp",
                        v18);
          goto LABEL_14;
        }
        LastError = -2147024867;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD3,
          (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\fileutils.cpp",
          (const char *)0x8007001DLL,
          dwCreationDispositiona);
LABEL_13:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v23);
LABEL_14:
        wil::details::ScopeExitFnGuard__lambda_264642e826a098a243dd793cc2ac5100___::operator()(&v24);
        goto LABEL_26;
      }
      v15 = 207;
    }
    else
    {
      HIBYTE(v25) = 0;
      v15 = 198;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v15,
                  (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\fileutils.cpp",
                  v14);
    goto LABEL_13;
  }
  if ( DeleteFileW(lpNewFileName) || GetLastError() == 2 )
    return 0;
  else
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xA2,
             (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\fileutils.cpp",
             v8);
}

```

## disassembly

```asm
0x180072dfc  push    rbp
0x180072dfe  push    rbx
0x180072dff  push    rsi
0x180072e00  push    rdi
0x180072e01  push    r14
0x180072e03  lea     rbp, [rsp-37h]
0x180072e08  sub     rsp, 0A0h
0x180072e0f  mov     rax, cs:__security_cookie
0x180072e16  xor     rax, rsp
0x180072e19  mov     [rbp+57h+var_30], rax
0x180072e1d  mov     edi, r9d
0x180072e20  mov     r14, r8
0x180072e23  mov     r8, rdx
0x180072e26  mov     rsi, rcx
0x180072e29  cmp     r9d, 1E84800h
0x180072e30  jbe     short loc_180072E54
0x180072e32  mov     rcx, [rbp+5Fh]; this
0x180072e36  mov     ebx, 800700DFh
0x180072e3b  mov     r9d, ebx; char *
0x180072e3e  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180072e45  mov     edx, 96h; void *
0x180072e4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072e4f  jmp     loc_18007305A
0x180072e54  test    edi, edi
0x180072e56  jnz     short loc_180072E8E
0x180072e58  call    cs:__imp_DeleteFileW
0x180072e5e  test    eax, eax
0x180072e60  jnz     short loc_180072E87
0x180072e62  call    cs:__imp_GetLastError
0x180072e68  cmp     eax, 2
0x180072e6b  jz      short loc_180072E87
0x180072e6d  mov     rcx, [rbp+5Fh]; this
0x180072e71  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180072e78  mov     edx, 0A2h; void *
0x180072e7d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180072e82  jmp     loc_18007305C
0x180072e87  xor     eax, eax
0x180072e89  jmp     loc_18007305C
0x180072e8e  lea     rcx, [rbp+57h+var_50]
0x180072e92  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x180072e97  nop
0x180072e98  lea     rdx, [rbp+57h+var_50]
0x180072e9c  mov     rcx, r8
0x180072e9f  call    NgcUtils__GenerateTemporaryFilePath
0x180072ea4  mov     ebx, eax
0x180072ea6  test    eax, eax
0x180072ea8  jns     short loc_180072EC7
0x180072eaa  mov     rcx, [rbp+5Fh]; this
0x180072eae  mov     r9d, eax; char *
0x180072eb1  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180072eb8  mov     edx, 0ACh; void *
0x180072ebd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072ec2  jmp     loc_180073051
0x180072ec7  lea     rax, [rbp+57h+var_50]
0x180072ecb  mov     [rbp+57h+var_70], rax
0x180072ecf  mov     [rbp+57h+var_68], 100h
0x180072ed5  lea     rcx, [rbp+57h+var_50]
0x180072ed9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180072ede  mov     rcx, rax; lpFileName
0x180072ee1  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x180072eea  mov     [rsp+0C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180072ef2  mov     [rsp+0C0h+dwCreationDisposition], 2; dwCreationDisposition
0x180072efa  xor     r9d, r9d; lpSecurityAttributes
0x180072efd  xor     r8d, r8d; dwShareMode
0x180072f00  mov     edx, 40000000h; dwDesiredAccess
0x180072f05  call    cs:__imp_CreateFileW
0x180072f0b  mov     rbx, rax
0x180072f0e  mov     [rbp+57h+var_78], rax
0x180072f12  inc     rax
0x180072f15  test    rax, 0FFFFFFFFFFFFFFFEh
0x180072f1b  jnz     short loc_180072F4F
0x180072f1d  mov     byte ptr [rbp+57h+var_68+1], 0
0x180072f21  mov     edx, 0C6h; void *
0x180072f26  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180072f2d  mov     rcx, [rbp+5Fh]; this
0x180072f31  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180072f36  mov     ebx, eax
0x180072f38  lea     rcx, [rbp+57h+var_78]
0x180072f3c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180072f41  lea     rcx, [rbp+57h+var_70]
0x180072f45  call    wil__details__ScopeExitFnGuard__lambda_264642e826a098a243dd793cc2ac5100_____operator__
0x180072f4a  jmp     loc_180073051
0x180072f4f  mov     [rbp+57h+NumberOfBytesWritten], 0
0x180072f56  mov     qword ptr [rsp+0C0h+dwCreationDisposition], 0; int
0x180072f5f  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180072f63  mov     r8d, edi; nNumberOfBytesToWrite
0x180072f66  mov     rdx, r14; lpBuffer
0x180072f69  mov     rcx, rbx; hFile
0x180072f6c  call    cs:__imp_WriteFile
0x180072f72  test    eax, eax
0x180072f74  jnz     short loc_180072F7D
0x180072f76  mov     edx, 0CFh
0x180072f7b  jmp     short loc_180072F26
0x180072f7d  cmp     [rbp+57h+NumberOfBytesWritten], edi
0x180072f80  jz      short loc_180072FA1
0x180072f82  mov     rcx, [rbp+5Fh]; this
0x180072f86  mov     ebx, 8007001Dh
0x180072f8b  mov     r9d, ebx; char *
0x180072f8e  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180072f95  mov     edx, 0D3h; void *
0x180072f9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072f9f  jmp     short loc_180072F38
0x180072fa1  xorps   xmm0, xmm0
0x180072fa4  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x180072fa8  lea     rax, [rbp+57h+var_60]
0x180072fac  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax; int
0x180072fb1  xor     r9d, r9d
0x180072fb4  xor     r8d, r8d
0x180072fb7  lea     edx, [r9+2]
0x180072fbb  mov     rcx, rbx
0x180072fbe  call    cs:__imp_NtFlushBuffersFileEx
0x180072fc4  mov     rcx, [rbp+5Fh]; this
0x180072fc8  test    eax, eax
0x180072fca  jns     short loc_180072FE0
0x180072fcc  mov     r9d, eax; char *
0x180072fcf  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180072fd6  mov     edx, 0DEh; void *
0x180072fdb  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180072fe0  mov     r9d, dword ptr [rbp+57h+var_60]; char *
0x180072fe4  mov     rcx, [rbp+5Fh]; this
0x180072fe8  test    r9d, r9d
0x180072feb  jns     short loc_180072FFE
0x180072fed  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180072ff4  mov     edx, 0DFh; void *
0x180072ff9  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180072ffe  lea     rcx, [rbp+57h+var_78]
0x180073002  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180073007  lea     rcx, [rbp+57h+var_50]
0x18007300b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180073010  mov     rcx, rax; lpExistingFileName
0x180073013  mov     r8d, 1; dwFlags
0x180073019  mov     rdx, rsi; lpNewFileName
0x18007301c  call    cs:__imp_MoveFileExW
0x180073022  test    eax, eax
0x180073024  jnz     short loc_180073042
0x180073026  mov     rcx, [rbp+5Fh]; this
0x18007302a  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180073031  mov     edx, 0E5h; void *
0x180073036  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007303b  mov     ebx, eax
0x18007303d  jmp     loc_180072F41
0x180073042  mov     byte ptr [rbp+57h+var_68+1], 0
0x180073046  lea     rcx, [rbp+57h+var_70]
0x18007304a  call    wil__details__ScopeExitFnGuard__lambda_264642e826a098a243dd793cc2ac5100_____operator__
0x18007304f  xor     ebx, ebx
0x180073051  lea     rcx, [rbp+57h+var_50]
0x180073055  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007305a  mov     eax, ebx
0x18007305c  mov     rcx, [rbp+57h+var_30]
0x180073060  xor     rcx, rsp; StackCookie
0x180073063  call    __security_check_cookie
0x180073068  add     rsp, 0A0h
0x18007306f  pop     r14
0x180073071  pop     rdi
0x180073072  pop     rsi
0x180073073  pop     rbx
0x180073074  pop     rbp
0x180073075  retn
```
