# WaasMedic::WaasDownloaderHelper::~WaasDownloaderHelper(void)

- ea: `0x18000bbe8`
- end: `0x18000bcd1`
- name: `??1WaasDownloaderHelper@WaasMedic@@QEAA@XZ`
- size: `233`
- prototype: `void __fastcall(WaasMedic::WaasDownloaderHelper *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x180016af0`
- `0x180060d49`

## callees

- `0x180003bb0`
- `0x1800042c0`
- `0x18000bbe8`
- `0x18002543c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000bc6e`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000bc6e`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000bc4a`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000bc4a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000bc21`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000bc8c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000bc21`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000bc8c`

## string_xrefs

- `0x18000bc2e`: `Failed to delete exe file: %s`
- `0x18000bc9b`: `Failed to delete .tmp file: %s`

## pseudocode

```c
void __fastcall WaasMedic::WaasDownloaderHelper::~WaasDownloaderHelper(WaasMedic::WaasDownloaderHelper *this)
{
  const WCHAR *v1; // rbx
  wchar_t *v2; // rax
  __int64 v3; // rdi
  unsigned __int64 v4; // rdi
  WCHAR FileName[264]; // [rsp+20h] [rbp-228h] BYREF

  v1 = (const WCHAR *)&WaasMedic::WaasDownloaderHelper::downloadedPath;
  if ( (unsigned __int64)qword_180098130 > 7 )
    v1 = WaasMedic::WaasDownloaderHelper::downloadedPath;
  if ( !DeleteFileW(v1) )
    LogLevelW(2u, L"Failed to delete exe file: %s", v1);
  if ( v1 )
  {
    v2 = wcsrchr(v1, 0x2Eu);
    if ( v2 )
    {
      v3 = v2 - v1;
      _o_wcsncpy_s(FileName, 260, v1, v3);
      v4 = v3;
      if ( v4 >= 260 )
        _report_rangecheckfailure();
      FileName[v4] = 0;
      if ( !DeleteFileW(FileName) )
        LogLevelW(2u, L"Failed to delete .tmp file: %s", FileName);
    }
  }
}

```

## disassembly

```asm
0x18000bbe8  mov     [rsp+arg_0], rbx
0x18000bbed  push    rdi
0x18000bbee  sub     rsp, 240h
0x18000bbf5  mov     rax, cs:__security_cookie
0x18000bbfc  xor     rax, rsp
0x18000bbff  mov     [rsp+248h+var_18], rax
0x18000bc07  cmp     cs:qword_180098130, 7
0x18000bc0f  lea     rbx, ?downloadedPath@WaasDownloaderHelper@WaasMedic@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring WaasMedic::WaasDownloaderHelper::downloadedPath
0x18000bc16  cmova   rbx, cs:?downloadedPath@WaasDownloaderHelper@WaasMedic@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring WaasMedic::WaasDownloaderHelper::downloadedPath
0x18000bc1e  mov     rcx, rbx; lpFileName
0x18000bc21  call    cs:__imp_DeleteFileW
0x18000bc27  test    eax, eax
0x18000bc29  jnz     short loc_18000BC3D
0x18000bc2b  mov     r8, rbx
0x18000bc2e  lea     rdx, aFailedToDelete_3; "Failed to delete exe file: %s"
0x18000bc35  lea     ecx, [rax+2]; unsigned __int8
0x18000bc38  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18000bc3d  test    rbx, rbx
0x18000bc40  jz      short loc_18000BCAA
0x18000bc42  mov     edx, 2Eh ; '.'; Ch
0x18000bc47  mov     rcx, rbx; Str
0x18000bc4a  call    cs:__imp_wcsrchr
0x18000bc50  mov     rdi, rax
0x18000bc53  test    rax, rax
0x18000bc56  jz      short loc_18000BCAA
0x18000bc58  sub     rdi, rbx
0x18000bc5b  lea     rcx, [rsp+248h+FileName]
0x18000bc60  sar     rdi, 1
0x18000bc63  mov     r8, rbx
0x18000bc66  mov     r9, rdi
0x18000bc69  mov     edx, 104h
0x18000bc6e  call    cs:__imp__o_wcsncpy_s
0x18000bc74  add     rdi, rdi
0x18000bc77  cmp     rdi, 208h
0x18000bc7e  jnb     short loc_18000BCCB
0x18000bc80  xor     eax, eax
0x18000bc82  lea     rcx, [rsp+248h+FileName]; lpFileName
0x18000bc87  mov     [rsp+rdi+248h+FileName], ax
0x18000bc8c  call    cs:__imp_DeleteFileW
0x18000bc92  test    eax, eax
0x18000bc94  jnz     short loc_18000BCAA
0x18000bc96  lea     r8, [rsp+248h+FileName]
0x18000bc9b  lea     rdx, aFailedToDelete; "Failed to delete .tmp file: %s"
0x18000bca2  lea     ecx, [rax+2]; unsigned __int8
0x18000bca5  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18000bcaa  mov     rcx, [rsp+248h+var_18]
0x18000bcb2  xor     rcx, rsp; StackCookie
0x18000bcb5  call    __security_check_cookie
0x18000bcba  mov     rbx, [rsp+248h+arg_0]
0x18000bcc2  add     rsp, 240h
0x18000bcc9  pop     rdi
0x18000bcca  retn
0x18000bccb  call    __report_rangecheckfailure
```
