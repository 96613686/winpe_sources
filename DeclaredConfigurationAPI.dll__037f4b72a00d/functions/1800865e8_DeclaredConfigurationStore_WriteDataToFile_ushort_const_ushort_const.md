# DeclaredConfigurationStore_WriteDataToFile(ushort const *,ushort const *)

- ea: `0x1800865e8`
- end: `0x1800869a8`
- name: `?DeclaredConfigurationStore_WriteDataToFile@@YAJPEBG0@Z`
- size: `960`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPCWCH lpWideCharStr)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config`

## callers

- `0x18007efa0`

## callees

- `0x18000b9e0`
- `0x1800117bc`
- `0x1800117dc`
- `0x18001438c`
- `0x1800143c8`
- `0x180018ac0`
- `0x18001dea8`
- `0x18004dc70`
- `0x180055898`
- `0x180057eec`
- `0x180058630`
- `0x18005e7dc`
- `0x1800865e8`
- `0x1800a0de4`
- `0x1800a1878`
- `0x1800a18b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800867e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086855`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800867e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086855`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800867d3`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18008684b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800867d3`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18008684b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180086742`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180086742`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800868af`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800868af`

## string_xrefs

- `0x180086701`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180086764`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180086794`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180086879`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x1800868c1`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall DeclaredConfigurationStore_WriteDataToFile(LPCWSTR lpFileName, LPCWCH lpWideCharStr)
{
  __int64 last_of; // rbx
  __int64 v5; // rax
  __int64 v6; // rax
  const unsigned __int16 *v7; // rdx
  wil *v8; // rcx
  unsigned int DirectoryDeepNoThrow; // ebx
  HANDLE FileW; // rax
  const char *v11; // r9
  __int64 v12; // rdi
  __int64 v13; // rdx
  int v14; // eax
  signed int LastError; // eax
  CHAR *v16; // rdx
  signed int v17; // eax
  LPSTR *v18; // rdx
  const char *v19; // r9
  __int64; // rax
  int dwCreationDisposition; // [rsp+20h] [rbp-E8h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E8h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-E8h]
  int dwCreationDispositionc; // [rsp+20h] [rbp-E8h]
  HANDLE hFile; // [rsp+40h] [rbp-C8h] BYREF
  LPSTR lpMultiByteStr[2]; // [rsp+48h] [rbp-C0h] BYREF
  int cbMultiByte; // [rsp+58h] [rbp-B0h]
  unsigned __int64 v28; // [rsp+60h] [rbp-A8h]
  wil *v29[4]; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v30[32]; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v31[32]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v32[32]; // [rsp+C8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  std::wstring::wstring((__int64)v30, (__int64)lpFileName);
  last_of = std::wstring::find_last_of(v30, L"\\");
  std::wstring::wstring((__int64)v29);
  std::wstring::wstring((__int64)v31);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v5 = std::wstring::substr(v30, v32, 0, last_of);
    std::wstring::operator=(v29, v5);
    std::wstring::_Tidy_deallocate(v32);
    v12 = -1;
    v6 = std::wstring::substr(v30, v32, last_of + 1, -1);
    std::wstring::operator=(v31, v6);
    std::wstring::_Tidy_deallocate(v32);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF45,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)0x8007000ELL,
        dwCreationDisposition);
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180086954);
      std::wstring::_Tidy_deallocate(v31);
      std::wstring::_Tidy_deallocate(v29);
      std::wstring::_Tidy_deallocate(v30);
       = 2147942414LL;
LABEL_40:
      ;
    }
  }
  v8 = (wil *)v29;
  if ( v29[3] > (wil *)7 )
    v8 = v29[0];
  DirectoryDeepNoThrow = wil::CreateDirectoryDeepNoThrow(v8, v7);
  if ( (int)(DirectoryDeepNoThrow + 0x80000000) >= 0 && DirectoryDeepNoThrow != -2147024713 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF4F,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)DirectoryDeepNoThrow,
      dwCreationDispositiona);
LABEL_31:
    std::wstring::_Tidy_deallocate(v31);
    std::wstring::_Tidy_deallocate(v29);
    std::wstring::_Tidy_deallocate(v30);
     = DirectoryDeepNoThrow;
    goto LABEL_40;
  }
  hFile = (HANDLE)-1LL;
  FileW = CreateFileW(lpFileName, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &hFile,
    FileW);
  if ( hFile == (HANDLE)-1LL )
  {
    DirectoryDeepNoThrow = wil::details::in1diag3::Return_GetLastError(
                             retaddr,
                             (void *)0xF5B,
                             (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\d"
                                           "eclaredconfigurationapi.cpp",
                             v11);
    goto LABEL_30;
  }
  do
    ++v12;
  while ( lpWideCharStr[v12] );
  if ( (_DWORD)v12 )
  {
    v14 = WideCharToMultiByte(0xFDE9u, 0, lpWideCharStr, v12, 0, 0, 0, 0);
    if ( v14 )
    {
      std::string::string(lpMultiByteStr, v14);
      std::string::resize(lpMultiByteStr);
      v16 = (CHAR *)lpMultiByteStr;
      if ( v28 > 0xF )
        v16 = lpMultiByteStr[0];
      if ( WideCharToMultiByte(0xFDE9u, 0, lpWideCharStr, v12, v16, cbMultiByte, 0, 0) )
      {
        v18 = lpMultiByteStr;
        if ( v28 > 0xF )
          v18 = (LPSTR *)lpMultiByteStr[0];
        if ( WriteFile(hFile, v18, cbMultiByte, 0, 0) )
        {
          std::string::~string(lpMultiByteStr);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
          std::wstring::_Tidy_deallocate(v31);
          std::wstring::_Tidy_deallocate(v29);
          std::wstring::_Tidy_deallocate(v30);
           = 0;
          goto LABEL_40;
        }
        DirectoryDeepNoThrow = wil::details::in1diag3::Return_GetLastError(
                                 retaddr,
                                 (void *)0xF79,
                                 (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\li"
                                               "b\\declaredconfigurationapi.cpp",
                                 v19);
      }
      else
      {
        v17 = GetLastError();
        DirectoryDeepNoThrow = v17;
        if ( v17 > 0 )
          DirectoryDeepNoThrow = (unsigned __int16)v17 | 0x80070000;
        if ( (DirectoryDeepNoThrow & 0x80000000) != 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xF70,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
            (const char *)DirectoryDeepNoThrow,
            dwCreationDispositionc);
      }
      std::string::~string(lpMultiByteStr);
      goto LABEL_30;
    }
    LastError = GetLastError();
    DirectoryDeepNoThrow = LastError;
    if ( LastError > 0 )
      DirectoryDeepNoThrow = (unsigned __int16)LastError | 0x80070000;
    if ( (DirectoryDeepNoThrow & 0x80000000) == 0 )
    {
LABEL_30:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
      goto LABEL_31;
    }
    v13 = 3943;
  }
  else
  {
    DirectoryDeepNoThrow = -2147024809;
    v13 = 3936;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v13,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
    (const char *)DirectoryDeepNoThrow,
    dwCreationDispositionb);
  goto LABEL_30;
}

```

## disassembly

```asm
0x1800865e8  mov     r11, rsp
0x1800865eb  mov     [r11+18h], rbx
0x1800865ef  mov     [r11+20h], rsi
0x1800865f3  push    rdi
0x1800865f4  push    r14
0x1800865f6  push    r15
0x1800865f8  sub     rsp, 0F0h
0x1800865ff  mov     rax, cs:__security_cookie
0x180086606  xor     rax, rsp
0x180086609  mov     [rsp+108h+var_20], rax
0x180086611  mov     rsi, rdx
0x180086614  mov     r14, rcx
0x180086617  mov     rdx, rcx
0x18008661a  lea     rcx, [r11-80h]
0x18008661e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180086623  nop
0x180086624  lea     rdx, StringValue; "\\"
0x18008662b  lea     rcx, [rsp+108h+var_80]
0x180086633  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find_last_of(ushort const * const,unsigned __int64)
0x180086638  mov     rbx, rax
0x18008663b  lea     rcx, [rsp+108h+var_A0]
0x180086640  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180086645  nop
0x180086646  lea     rcx, [rsp+108h+var_60]
0x18008664e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180086653  nop
0x180086654  mov     r9, rbx
0x180086657  xor     r8d, r8d
0x18008665a  lea     rdx, [rsp+108h+var_40]
0x180086662  lea     rcx, [rsp+108h+var_80]
0x18008666a  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18008666f  mov     rdx, rax
0x180086672  lea     rcx, [rsp+108h+var_A0]
0x180086677  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18008667c  lea     rcx, [rsp+108h+var_40]
0x180086684  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180086689  lea     r8, [rbx+1]
0x18008668d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180086691  mov     r9, rdi
0x180086694  lea     rdx, [rsp+108h+var_40]
0x18008669c  lea     rcx, [rsp+108h+var_80]
0x1800866a4  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800866a9  mov     rdx, rax
0x1800866ac  lea     rcx, [rsp+108h+var_60]
0x1800866b4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800866b9  lea     rcx, [rsp+108h+var_40]
0x1800866c1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800866c6  nop
0x1800866c7  lea     rcx, [rsp+108h+var_A0]
0x1800866cc  cmp     [rsp+108h+var_88], 7
0x1800866d5  cmova   rcx, [rsp+108h+var_A0]; this
0x1800866db  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x1800866e0  mov     ebx, eax
0x1800866e2  mov     eax, 80000000h
0x1800866e7  lea     ecx, [rbx+rax]
0x1800866ea  test    eax, ecx
0x1800866ec  jnz     short loc_180086717
0x1800866ee  cmp     ebx, 800700B7h
0x1800866f4  jz      short loc_180086717
0x1800866f6  mov     rcx, [rsp+108h]; this
0x1800866fe  mov     r9d, ebx; char *
0x180086701  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180086708  mov     edx, 0F4Fh; void *
0x18008670d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180086712  jmp     loc_1800868EA
0x180086717  mov     [rsp+108h+hFile], rdi
0x18008671c  xor     r15d, r15d
0x18008671f  mov     [rsp+108h+hTemplateFile], r15; hTemplateFile
0x180086724  mov     [rsp+108h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18008672c  mov     [rsp+108h+dwCreationDisposition], 2; int
0x180086734  xor     r9d, r9d; lpSecurityAttributes
0x180086737  xor     r8d, r8d; dwShareMode
0x18008673a  mov     edx, 40000000h; dwDesiredAccess
0x18008673f  mov     rcx, r14; lpFileName
0x180086742  call    cs:__imp_CreateFileW
0x180086748  mov     rdx, rax
0x18008674b  lea     rcx, [rsp+108h+hFile]
0x180086750  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180086755  cmp     [rsp+108h+hFile], rdi
0x18008675a  jnz     short loc_18008677C
0x18008675c  mov     rcx, [rsp+108h]; this
0x180086764  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18008676b  mov     edx, 0F5Bh; void *
0x180086770  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180086775  mov     ebx, eax
0x180086777  jmp     loc_1800868DF
0x18008677c  inc     rdi
0x18008677f  cmp     [rsi+rdi*2], r15w
0x180086784  jnz     short loc_18008677C
0x180086786  test    edi, edi
0x180086788  jnz     short loc_1800867B0
0x18008678a  mov     ebx, 80070057h
0x18008678f  mov     edx, 0F60h; void *
0x180086794  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18008679b  mov     r9d, ebx; char *
0x18008679e  mov     rcx, [rsp+108h]; this
0x1800867a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800867ab  jmp     loc_1800868DF
0x1800867b0  mov     [rsp+108h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x1800867b5  mov     [rsp+108h+hTemplateFile], r15; lpDefaultChar
0x1800867ba  mov     [rsp+108h+dwFlagsAndAttributes], r15d; cbMultiByte
0x1800867bf  mov     qword ptr [rsp+108h+dwCreationDisposition], r15; lpMultiByteStr
0x1800867c4  mov     r9d, edi; cchWideChar
0x1800867c7  mov     r8, rsi; lpWideCharStr
0x1800867ca  xor     edx, edx; dwFlags
0x1800867cc  mov     ebx, 0FDE9h
0x1800867d1  mov     ecx, ebx; CodePage
0x1800867d3  call    cs:__imp_WideCharToMultiByte
0x1800867d9  movsxd  rdx, eax
0x1800867dc  test    eax, eax
0x1800867de  jnz     short loc_180086804
0x1800867e0  call    cs:__imp_GetLastError
0x1800867e6  mov     ebx, eax
0x1800867e8  test    eax, eax
0x1800867ea  jle     short loc_1800867F5
0x1800867ec  movzx   ebx, ax
0x1800867ef  or      ebx, 80070000h
0x1800867f5  test    ebx, ebx
0x1800867f7  jns     loc_1800868DF
0x1800867fd  mov     edx, 0F67h
0x180086802  jmp     short loc_180086794
0x180086804  lea     rcx, [rsp+108h+lpMultiByteStr]
0x180086809  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18008680e  nop
0x18008680f  lea     rcx, [rsp+108h+lpMultiByteStr]
0x180086814  call    ?resize@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_KD@Z; std::string::resize(unsigned __int64,char)
0x180086819  mov     eax, [rsp+108h+cbMultiByte]
0x18008681d  lea     rdx, [rsp+108h+lpMultiByteStr]
0x180086822  cmp     [rsp+108h+var_A8], 0Fh
0x180086828  cmova   rdx, [rsp+108h+lpMultiByteStr]
0x18008682e  mov     [rsp+108h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x180086833  mov     [rsp+108h+hTemplateFile], r15; lpDefaultChar
0x180086838  mov     [rsp+108h+dwFlagsAndAttributes], eax; cbMultiByte
0x18008683c  mov     qword ptr [rsp+108h+dwCreationDisposition], rdx; int
0x180086841  mov     r9d, edi; cchWideChar
0x180086844  mov     r8, rsi; lpWideCharStr
0x180086847  xor     edx, edx; dwFlags
0x180086849  mov     ecx, ebx; CodePage
0x18008684b  call    cs:__imp_WideCharToMultiByte
0x180086851  test    eax, eax
0x180086853  jnz     short loc_18008688C
0x180086855  call    cs:__imp_GetLastError
0x18008685b  mov     ebx, eax
0x18008685d  test    eax, eax
0x18008685f  jle     short loc_18008686A
0x180086861  movzx   ebx, ax
0x180086864  or      ebx, 80070000h
0x18008686a  test    ebx, ebx
0x18008686c  jns     short loc_1800868D4
0x18008686e  mov     rcx, [rsp+108h]; this
0x180086876  mov     r9d, ebx; char *
0x180086879  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180086880  mov     edx, 0F70h; void *
0x180086885  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008688a  jmp     short loc_1800868D4
0x18008688c  lea     rdx, [rsp+108h+lpMultiByteStr]
0x180086891  cmp     [rsp+108h+var_A8], 0Fh
0x180086897  cmova   rdx, [rsp+108h+lpMultiByteStr]; lpBuffer
0x18008689d  mov     qword ptr [rsp+108h+dwCreationDisposition], r15; lpOverlapped
0x1800868a2  xor     r9d, r9d; lpNumberOfBytesWritten
0x1800868a5  mov     r8d, [rsp+108h+cbMultiByte]; nNumberOfBytesToWrite
0x1800868aa  mov     rcx, [rsp+108h+hFile]; hFile
0x1800868af  call    cs:__imp_WriteFile
0x1800868b5  test    eax, eax
0x1800868b7  jnz     short loc_180086914
0x1800868b9  mov     rcx, [rsp+108h]; this
0x1800868c1  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800868c8  mov     edx, 0F79h; void *
0x1800868cd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800868d2  mov     ebx, eax
0x1800868d4  lea     rcx, [rsp+108h+lpMultiByteStr]
0x1800868d9  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800868de  nop
0x1800868df  lea     rcx, [rsp+108h+hFile]
0x1800868e4  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800868e9  nop
0x1800868ea  lea     rcx, [rsp+108h+var_60]
0x1800868f2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800868f7  nop
0x1800868f8  lea     rcx, [rsp+108h+var_A0]
0x1800868fd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180086902  nop
0x180086903  lea     rcx, [rsp+108h+var_80]
0x18008690b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180086910  mov     eax, ebx
0x180086912  jmp     short loc_18008697F
0x180086914  lea     rcx, [rsp+108h+lpMultiByteStr]
0x180086919  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18008691e  nop
0x18008691f  lea     rcx, [rsp+108h+hFile]
0x180086924  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180086929  nop
0x18008692a  lea     rcx, [rsp+108h+var_60]
0x180086932  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180086937  nop
0x180086938  lea     rcx, [rsp+108h+var_A0]
0x18008693d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180086942  nop
0x180086943  lea     rcx, [rsp+108h+var_80]
0x18008694b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180086950  xor     eax, eax
0x180086952  jmp     short loc_18008697F
0x180086954  lea     rcx, [rsp+108h+var_60]
0x18008695c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180086961  nop
0x180086962  lea     rcx, [rsp+108h+var_A0]
0x180086967  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008696c  nop
0x18008696d  lea     rcx, [rsp+108h+var_80]
0x180086975  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008697a  mov     eax, 8007000Eh
0x18008697f  mov     rcx, [rsp+108h+var_20]
0x180086987  xor     rcx, rsp; StackCookie
0x18008698a  call    __security_check_cookie
0x18008698f  lea     r11, [rsp+108h+var_18]
0x180086997  mov     rbx, [r11+30h]
0x18008699b  mov     rsi, [r11+38h]
0x18008699f  mov     rsp, r11
0x1800869a2  pop     r15
0x1800869a4  pop     r14
0x1800869a6  pop     rdi
0x1800869a7  retn
```
