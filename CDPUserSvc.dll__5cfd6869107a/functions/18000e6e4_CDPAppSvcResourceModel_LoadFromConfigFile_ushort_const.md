# CDPAppSvcResourceModel::LoadFromConfigFile(ushort const *)

- ea: `0x18000e6e4`
- end: `0x18000e92b`
- name: `?LoadFromConfigFile@CDPAppSvcResourceModel@@SA?AU1@PEBG@Z`
- size: `583`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000e2d0`

## callees

- `0x180004a58`
- `0x18000e6e4`
- `0x18000e934`
- `0x18000eb48`
- `0x18000ecb8`
- `0x1800253f4`
- `0x180026060`
- `0x18002c570`
- `0x180041054`
- `0x1800427b0`
- `0x180042b6c`
- `0x180042c08`
- `0x1800430e4`
- `0x1800433ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e8d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e8d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e8f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e8f9`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000e847`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000e847`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e786`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e786`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000e7ab`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000e7ab`

## string_xrefs

- `0x18000e745`: `..\appsvcresourcemodelconfig.cpp`
- `0x18000e80e`: `..\appsvcresourcemodelconfig.cpp`
- `0x18000e851`: `..\appsvcresourcemodelconfig.cpp`
- `0x18000e878`: `..\appsvcresourcemodelconfig.cpp`
- `0x18000e8dc`: `{"text":"Invalid config file. File empty or greater than allowed limit."}`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
unsigned __int64 __fastcall CDPAppSvcResourceModel::LoadFromConfigFile(unsigned __int64 a1, _WORD *a2)
{
  char v3; // al
  LPCWSTR v4; // r10
  char *FileW; // rbx
  __int64 FileSize; // rsi
  int v7; // eax
  void *v8; // rcx
  _BYTE *v9; // r15
  const char *v10; // r9
  __int64 v11; // rax
  void *v12; // rcx
  int dwCreationDisposition; // [rsp+20h] [rbp-59h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-59h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-59h]
  DWORD FileSizeHigh; // [rsp+40h] [rbp-39h] BYREF
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-35h] BYREF
  LPVOID lpBuffer; // [rsp+48h] [rbp-31h] BYREF
  int v20; // [rsp+50h] [rbp-29h]
  LPVOID *p_lpBuffer; // [rsp+58h] [rbp-21h] BYREF
  void *v22; // [rsp+60h] [rbp-19h] BYREF
  char v23; // [rsp+68h] [rbp-11h]
  unsigned __int64 v24[3]; // [rsp+70h] [rbp-9h] BYREF
  _BYTE v25[32]; // [rsp+88h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v24[1] = a1;
  v20 = 0;
  if ( !a2 || (v3 = 1, !*a2) )
    v3 = 0;
  if ( !v3 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"..\\appsvcresourcemodelconfig.cpp",
      (const char *)0x8000FFFFLL,
      dwCreationDisposition);
  std::vector<ConnectedDevices::Exception::StackFrame>::vector<ConnectedDevices::Exception::StackFrame>(a1);
  v20 = 1;
  FileW = (char *)CreateFileW(v4, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
  v24[2] = (unsigned __int64)FileW;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    FileSizeHigh = 0;
    FileSize = GetFileSize(FileW, &FileSizeHigh);
    if ( FileSizeHigh || (unsigned int)(FileSize - 1) > 0xFFFFE )
    {
      Log<>(1u, "{\"text\":\"Invalid config file. File empty or greater than allowed limit.\"}");
    }
    else
    {
      lpBuffer = 0;
      p_lpBuffer = &lpBuffer;
      v23 = 1;
      v22 = 0;
      v7 = ULongLongMult((unsigned int)(FileSize + 1), 1u, v24);
      if ( v7 >= 0 )
        v7 = CTCoAllocPolicy::Alloc(v8, 1u, v24[0], &v22);
      if ( v7 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x44,
          (unsigned int)"..\\appsvcresourcemodelconfig.cpp",
          (const char *)(unsigned int)v7,
          dwCreationDispositiona);
      wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_lpBuffer);
      v9 = lpBuffer;
      NumberOfBytesRead = 0;
      if ( !ReadFile(FileW, lpBuffer, FileSize, &NumberOfBytesRead, 0) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x49,
          (unsigned int)"..\\appsvcresourcemodelconfig.cpp",
          v10);
      if ( (_DWORD)FileSize != NumberOfBytesRead )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x4A,
          (unsigned int)"..\\appsvcresourcemodelconfig.cpp",
          (const char *)0x8000FFFFLL,
          dwCreationDispositionb);
      v9[FileSize] = 0;
      std::string::string((__int64)v25, (__int64)v9);
      v11 = cdp::JsonSerializer<CDPAppSvcResourceModel>::Deserialize(&p_lpBuffer, v25);
      std::vector<CDPAppSvcApplication>::operator=(a1, v11);
      std::vector<CDPAppSvcApplication>::_Tidy(&p_lpBuffer);
      std::string::_Tidy_deallocate(v25);
      v12 = lpBuffer;
      lpBuffer = 0;
      if ( v12 )
        CoTaskMemFree(v12);
    }
  }
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  return a1;
}

```

## disassembly

```asm
0x18000e6e4  mov     [rsp-8+arg_10], rbx
0x18000e6e9  mov     [rsp-8+arg_18], rsi
0x18000e6ee  push    rbp
0x18000e6ef  push    rdi
0x18000e6f0  push    r12
0x18000e6f2  push    r14
0x18000e6f4  push    r15
0x18000e6f6  lea     rbp, [rsp-37h]
0x18000e6fb  sub     rsp, 0B0h
0x18000e702  mov     rax, cs:__security_cookie
0x18000e709  xor     rax, rsp
0x18000e70c  mov     [rbp+57h+var_28], rax
0x18000e710  mov     r10, rdx
0x18000e713  mov     rdi, rcx
0x18000e716  mov     [rbp+57h+var_58], rcx
0x18000e71a  xor     r12d, r12d
0x18000e71d  mov     [rbp+57h+var_80], r12d
0x18000e721  lea     r14d, [r12+1]
0x18000e726  test    rdx, rdx
0x18000e729  jz      short loc_18000E734
0x18000e72b  cmp     [rdx], r12w
0x18000e72f  mov     al, r14b
0x18000e732  jnz     short loc_18000E737
0x18000e734  mov     al, r12b
0x18000e737  mov     rcx, [rbp+5Fh]; this
0x18000e73b  test    al, al
0x18000e73d  jnz     short loc_18000E757
0x18000e73f  mov     r9d, 8000FFFFh; char *
0x18000e745  lea     r8, aAppsvcresource_0; "..\\appsvcresourcemodelconfig.cpp"
0x18000e74c  mov     edx, 31h ; '1'; void *
0x18000e751  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000e757  mov     rcx, rdi
0x18000e75a  call    ??0?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@QEAA@XZ; std::vector<ConnectedDevices::Exception::StackFrame>::vector<ConnectedDevices::Exception::StackFrame>(void)
0x18000e75f  mov     [rbp+57h+var_80], r14d
0x18000e763  mov     [rsp+0D0h+hTemplateFile], r12; hTemplateFile
0x18000e768  mov     [rsp+0D0h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x18000e770  mov     [rsp+0D0h+dwCreationDisposition], 3; int
0x18000e778  xor     r9d, r9d; lpSecurityAttributes
0x18000e77b  mov     r8d, r14d; dwShareMode
0x18000e77e  mov     edx, 80000000h; dwDesiredAccess
0x18000e783  mov     rcx, r10; lpFileName
0x18000e786  call    cs:__imp_CreateFileW
0x18000e78c  mov     rbx, rax
0x18000e78f  mov     [rbp+57h+var_50], rax
0x18000e793  dec     rax
0x18000e796  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e79a  ja      loc_18000E8EC
0x18000e7a0  mov     [rbp+57h+FileSizeHigh], r12d
0x18000e7a4  lea     rdx, [rbp+57h+FileSizeHigh]; lpFileSizeHigh
0x18000e7a8  mov     rcx, rbx; hFile
0x18000e7ab  call    cs:__imp_GetFileSize
0x18000e7b1  mov     esi, eax
0x18000e7b3  cmp     [rbp+57h+FileSizeHigh], r12d
0x18000e7b7  ja      loc_18000E8DC
0x18000e7bd  lea     ecx, [rsi-1]
0x18000e7c0  cmp     ecx, 0FFFFEh
0x18000e7c6  ja      loc_18000E8DC
0x18000e7cc  mov     [rbp+57h+lpBuffer], r12
0x18000e7d0  lea     rax, [rbp+57h+lpBuffer]
0x18000e7d4  mov     [rbp+57h+var_78], rax
0x18000e7d8  mov     [rbp+57h+var_68], r14b
0x18000e7dc  mov     [rbp+57h+var_70], r12
0x18000e7e0  lea     ecx, [rsi+1]; unsigned __int64
0x18000e7e3  lea     r8, [rbp+57h+var_60]; unsigned __int64 *
0x18000e7e7  mov     rdx, r14; unsigned __int64
0x18000e7ea  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000e7ef  test    eax, eax
0x18000e7f1  js      short loc_18000E803
0x18000e7f3  lea     r9, [rbp+57h+var_70]; void **
0x18000e7f7  mov     r8, [rbp+57h+var_60]; unsigned __int64
0x18000e7fb  mov     edx, r14d; unsigned int
0x18000e7fe  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18000e803  mov     rcx, [rbp+5Fh]; this
0x18000e807  test    eax, eax
0x18000e809  jns     short loc_18000E820
0x18000e80b  mov     r9d, eax; char *
0x18000e80e  lea     r8, aAppsvcresource_0; "..\\appsvcresourcemodelconfig.cpp"
0x18000e815  mov     edx, 44h ; 'D'; void *
0x18000e81a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000e820  lea     rcx, [rbp+57h+var_78]
0x18000e824  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18000e829  mov     r15, [rbp+57h+lpBuffer]
0x18000e82d  mov     [rbp+57h+NumberOfBytesRead], r12d
0x18000e831  mov     r14, [rbp+5Fh]
0x18000e835  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r12; int
0x18000e83a  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000e83e  mov     r8d, esi; nNumberOfBytesToRead
0x18000e841  mov     rdx, r15; lpBuffer
0x18000e844  mov     rcx, rbx; hFile
0x18000e847  call    cs:__imp_ReadFile
0x18000e84d  test    eax, eax
0x18000e84f  jnz     short loc_18000E864
0x18000e851  lea     r8, aAppsvcresource_0; "..\\appsvcresourcemodelconfig.cpp"
0x18000e858  lea     edx, [rax+49h]; void *
0x18000e85b  mov     rcx, r14; this
0x18000e85e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000e864  cmp     esi, [rbp+57h+NumberOfBytesRead]
0x18000e867  setz    al
0x18000e86a  mov     rcx, [rbp+5Fh]; this
0x18000e86e  test    al, al
0x18000e870  jnz     short loc_18000E88A
0x18000e872  mov     r9d, 8000FFFFh; char *
0x18000e878  lea     r8, aAppsvcresource_0; "..\\appsvcresourcemodelconfig.cpp"
0x18000e87f  mov     edx, 4Ah ; 'J'; void *
0x18000e884  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000e88a  mov     [rsi+r15], r12b
0x18000e88e  mov     rdx, r15
0x18000e891  lea     rcx, [rbp+57h+var_48]
0x18000e895  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18000e89a  nop
0x18000e89b  lea     rdx, [rbp+57h+var_48]
0x18000e89f  lea     rcx, [rbp+57h+var_78]
0x18000e8a3  call    ?Deserialize@?$JsonSerializer@UCDPAppSvcResourceModel@@@cdp@@SA?AUCDPAppSvcResourceModel@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4DeserializationFlags@2@@Z; cdp::JsonSerializer<CDPAppSvcResourceModel>::Deserialize(std::string const &,cdp::DeserializationFlags)
0x18000e8a8  mov     rdx, rax
0x18000e8ab  mov     rcx, rdi
0x18000e8ae  call    ??4?$vector@UCDPAppSvcApplication@@V?$allocator@UCDPAppSvcApplication@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<CDPAppSvcApplication>::operator=(std::vector<CDPAppSvcApplication> &&)
0x18000e8b3  lea     rcx, [rbp+57h+var_78]
0x18000e8b7  call    ?_Tidy@?$vector@UCDPAppSvcApplication@@V?$allocator@UCDPAppSvcApplication@@@std@@@std@@AEAAXXZ; std::vector<CDPAppSvcApplication>::_Tidy(void)
0x18000e8bc  nop
0x18000e8bd  lea     rcx, [rbp+57h+var_48]
0x18000e8c1  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18000e8c6  nop
0x18000e8c7  mov     rcx, [rbp+57h+lpBuffer]; pv
0x18000e8cb  mov     [rbp+57h+lpBuffer], r12
0x18000e8cf  test    rcx, rcx
0x18000e8d2  jz      short loc_18000E8EC
0x18000e8d4  call    cs:__imp_CoTaskMemFree
0x18000e8da  jmp     short loc_18000E8EC
0x18000e8dc  lea     rdx, aTextInvalidCon; "{\"text\":\"Invalid config file. File e"...
0x18000e8e3  mov     ecx, r14d
0x18000e8e6  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x18000e8eb  nop
0x18000e8ec  lea     rcx, [rbx-1]
0x18000e8f0  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000e8f4  ja      short loc_18000E8FF
0x18000e8f6  mov     rcx, rbx; hObject
0x18000e8f9  call    cs:__imp_CloseHandle
0x18000e8ff  mov     rax, rdi
0x18000e902  mov     rcx, [rbp+57h+var_28]
0x18000e906  xor     rcx, rsp; StackCookie
0x18000e909  call    __security_check_cookie
0x18000e90e  lea     r11, [rsp+0D0h+var_20]
0x18000e916  mov     rbx, [r11+40h]
0x18000e91a  mov     rsi, [r11+48h]
0x18000e91e  mov     rsp, r11
0x18000e921  pop     r15
0x18000e923  pop     r14
0x18000e925  pop     r12
0x18000e927  pop     rdi
0x18000e928  pop     rbp
0x18000e929  retn
```
