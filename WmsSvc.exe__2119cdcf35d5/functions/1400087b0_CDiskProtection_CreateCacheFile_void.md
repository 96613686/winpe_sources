# CDiskProtection::CreateCacheFile(void)

- ea: `0x1400087b0`
- end: `0x140008a29`
- name: `?CreateCacheFile@CDiskProtection@@IEAAJXZ`
- size: `633`
- prototype: `__int64 __fastcall(CDiskProtection *__hidden this)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, registry_config`

## callers

- `0x140009af0`
- `0x14000b700`

## callees

- `0x1400016b8`
- `0x140008510`
- `0x1400087b0`
- `0x14000c5e8`
- `0x14000c87c`
- `0x14000ce14`
- `0x140015874`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000891b`
- `KERNEL32!CloseHandle` at `0x1400089eb`
- `KERNEL32!CloseHandle` at `0x14000891b`
- `KERNEL32!CloseHandle` at `0x1400089eb`
- `KERNEL32!SetFileAttributesW` at `0x140008933`
- `KERNEL32!SetFileAttributesW` at `0x140008933`
- `KERNEL32!GetLastError` at `0x140008941`
- `KERNEL32!GetLastError` at `0x140008941`
- `KERNEL32!IsDebuggerPresent` at `0x140008853`
- `KERNEL32!IsDebuggerPresent` at `0x140008998`
- `KERNEL32!IsDebuggerPresent` at `0x140008853`
- `KERNEL32!IsDebuggerPresent` at `0x140008998`
- `ole32!CoCreateGuid` at `0x14000880f`
- `ole32!CoCreateGuid` at `0x14000880f`

## string_xrefs

- `0x1400087ff`: `CDiskProtection::CreateCacheFile\n`
- `0x140008826`: `CDiskProtection::CreateCacheFile`
- `0x140008964`: `CDiskProtection::CreateCacheFile`
- `0x1400089fc`: `CDiskProtection::CreateCacheFile - Exiting, hr = 0x%08X\n`

## pseudocode

```c
__int64 __fastcall CDiskProtection::CreateCacheFile(CDiskProtection *this)
{
  HRESULT v2; // eax
  unsigned __int64 v3; // rdx
  signed int CacheFilePath; // ebx
  const unsigned __int16 *v5; // r12
  const unsigned __int16 *v6; // r15
  __int64 v7; // r9
  __int64 v8; // r8
  CDiskProtection *v9; // rcx
  CDiskProtection *v10; // rcx
  signed int LastError; // eax
  signed int v13; // [rsp+30h] [rbp-D0h]
  signed int v14; // [rsp+38h] [rbp-C8h]
  HANDLE hObject[23]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v16; // [rsp+F8h] [rbp-8h] BYREF
  GUID pguid; // [rsp+10Ch] [rbp+Ch] BYREF
  WCHAR FileName[264]; // [rsp+130h] [rbp+30h] BYREF

  memset_0(FileName, 0, 0x208u);
  memset_0(hObject, 0, 0xE8u);
  DEBUGMSG(L"CDiskProtection::CreateCacheFile\n");
  v2 = CoCreateGuid(&pguid);
  CacheFilePath = v2;
  if ( v2 < 0 )
  {
    v5 = L"CHRA";
    v6 = L"hr";
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      0x1063u,
      L"CDiskProtection::CreateCacheFile",
      L"CHRA",
      L"hr",
      v2);
    if ( IsDebuggerPresent() )
    {
      v7 = 4195;
LABEL_4:
      v14 = CacheFilePath;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        v7,
        L"CDiskProtection::CreateCacheFile",
        v5,
        v6,
        v14);
      goto LABEL_22;
    }
    v8 = 4195;
LABEL_21:
    v13 = CacheFilePath;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      v8,
      L"CDiskProtection::CreateCacheFile",
      v5,
      v6,
      v13);
    goto LABEL_22;
  }
  CacheFilePath = CDiskProtection::s_VcfGetCacheFilePath(FileName, v3);
  if ( CacheFilePath >= 0 )
  {
    hObject[21] = FileName;
    CacheFilePath = CDiskProtection::CalculateCacheFileSize(v9, 0, &v16);
    if ( CacheFilePath >= 0 )
    {
      CacheFilePath = CDiskProtection::VcfGenerateFile(this, (struct CDiskProtection::SCacheFileData *)hObject);
      if ( CacheFilePath >= 0 )
      {
        CacheFilePath = CDiskProtection::VcfFormatFile(this, (struct CDiskProtection::SCacheFileData *)hObject);
        if ( CacheFilePath >= 0 )
        {
          CacheFilePath = CDiskProtection::VcfCreateRegistryKey(
                            v10,
                            (const struct CDiskProtection::SCacheFileData *)hObject);
          if ( CacheFilePath >= 0 )
          {
            if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
            {
              CloseHandle(hObject[0]);
              hObject[0] = 0;
            }
            if ( !SetFileAttributesW(FileName, 6u) )
            {
              LastError = GetLastError();
              CacheFilePath = LastError;
              if ( LastError > 0 )
                CacheFilePath = (unsigned __int16)LastError | 0x80070000;
              v5 = L"CBRAEx";
              if ( CacheFilePath >= 0 )
                CacheFilePath = -2147467259;
              v6 = L"fSuccess";
              LOGASSERTHR(
                L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
                0x1096u,
                L"CDiskProtection::CreateCacheFile",
                L"CBRAEx",
                L"fSuccess",
                CacheFilePath);
              if ( IsDebuggerPresent() )
              {
                v7 = 4246;
                goto LABEL_4;
              }
              v8 = 4246;
              goto LABEL_21;
            }
          }
        }
      }
    }
  }
LABEL_22:
  operator delete(hObject[18]);
  if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(hObject[0]);
    hObject[0] = 0;
  }
  DEBUGMSG(L"CDiskProtection::CreateCacheFile - Exiting, hr = 0x%08X\n", (unsigned int)CacheFilePath);
  return (unsigned int)CacheFilePath;
}

```

## disassembly

```asm
0x1400087b0  push    rbp
0x1400087b2  push    rbx
0x1400087b3  push    rsi
0x1400087b4  push    rdi
0x1400087b5  push    r12
0x1400087b7  push    r15
0x1400087b9  lea     rbp, [rsp-258h]
0x1400087c1  sub     rsp, 358h
0x1400087c8  mov     rax, cs:__security_cookie
0x1400087cf  xor     rax, rsp
0x1400087d2  mov     [rbp+280h+var_40], rax
0x1400087d9  mov     rdi, rcx
0x1400087dc  xor     edx, edx; Val
0x1400087de  lea     rcx, [rbp+280h+FileName]; void *
0x1400087e2  mov     r8d, 208h; Size
0x1400087e8  call    memset_0
0x1400087ed  xor     edx, edx; Val
0x1400087ef  lea     rcx, [rsp+380h+hObject]; void *
0x1400087f4  mov     r8d, 0E8h; Size
0x1400087fa  call    memset_0
0x1400087ff  lea     rcx, aCdiskprotectio_105; "CDiskProtection::CreateCacheFile\n"
0x140008806  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14000880b  lea     rcx, [rbp+280h+pguid]; pguid
0x14000880f  call    cs:__imp_CoCreateGuid
0x140008815  mov     ebx, eax
0x140008817  test    eax, eax
0x140008819  jns     short loc_14000889A
0x14000881b  mov     [rsp+380h+var_358], eax; int
0x14000881f  lea     r12, aChra; "CHRA"
0x140008826  lea     rsi, aCdiskprotectio_63; "CDiskProtection::CreateCacheFile"
0x14000882d  mov     r9, r12; unsigned __int16 *
0x140008830  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140008837  mov     r8, rsi; unsigned __int16 *
0x14000883a  lea     r15, aHr; "hr"
0x140008841  mov     rcx, rdi; unsigned __int16 *
0x140008844  mov     edx, 1063h; unsigned int
0x140008849  mov     [rsp+380h+var_360], r15; unsigned __int16 *
0x14000884e  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140008853  call    cs:__imp_IsDebuggerPresent
0x140008859  test    eax, eax
0x14000885b  jz      short loc_14000888F
0x14000885d  mov     r9d, 1063h
0x140008863  mov     [rsp+380h+var_348], ebx
0x140008867  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000886e  mov     [rsp+380h+var_350], r15
0x140008873  mov     r8, rdi
0x140008876  mov     qword ptr [rsp+380h+var_358], r12
0x14000887b  mov     ecx, 2; unsigned __int8
0x140008880  mov     [rsp+380h+var_360], rsi
0x140008885  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000888a  jmp     loc_1400089D3
0x14000888f  mov     r8d, 1063h
0x140008895  jmp     loc_1400089B3
0x14000889a  lea     rcx, [rbp+280h+FileName]; unsigned __int16 *
0x14000889e  call    ?s_VcfGetCacheFilePath@CDiskProtection@@KAJPEAG_K@Z; CDiskProtection::s_VcfGetCacheFilePath(ushort *,unsigned __int64)
0x1400088a3  mov     ebx, eax
0x1400088a5  test    eax, eax
0x1400088a7  js      loc_1400089D3
0x1400088ad  lea     rax, [rbp+280h+FileName]
0x1400088b1  xor     edx, edx; unsigned __int64
0x1400088b3  lea     r8, [rbp+280h+var_288]; unsigned __int64 *
0x1400088b7  mov     [rbp+280h+var_298], rax
0x1400088bb  call    ?CalculateCacheFileSize@CDiskProtection@@IEAAJ_KPEA_K@Z; CDiskProtection::CalculateCacheFileSize(unsigned __int64,unsigned __int64 *)
0x1400088c0  mov     ebx, eax
0x1400088c2  test    eax, eax
0x1400088c4  js      loc_1400089D3
0x1400088ca  lea     rdx, [rsp+380h+hObject]; struct CDiskProtection::SCacheFileData *
0x1400088cf  mov     rcx, rdi; this
0x1400088d2  call    ?VcfGenerateFile@CDiskProtection@@IEAAJPEAUSCacheFileData@1@@Z; CDiskProtection::VcfGenerateFile(CDiskProtection::SCacheFileData *)
0x1400088d7  mov     ebx, eax
0x1400088d9  test    eax, eax
0x1400088db  js      loc_1400089D3
0x1400088e1  lea     rdx, [rsp+380h+hObject]; struct CDiskProtection::SCacheFileData *
0x1400088e6  mov     rcx, rdi; this
0x1400088e9  call    ?VcfFormatFile@CDiskProtection@@IEAAJPEAUSCacheFileData@1@@Z; CDiskProtection::VcfFormatFile(CDiskProtection::SCacheFileData *)
0x1400088ee  mov     ebx, eax
0x1400088f0  test    eax, eax
0x1400088f2  js      loc_1400089D3
0x1400088f8  lea     rdx, [rsp+380h+hObject]; struct CDiskProtection::SCacheFileData *
0x1400088fd  call    ?VcfCreateRegistryKey@CDiskProtection@@IEAAJPEBUSCacheFileData@1@@Z; CDiskProtection::VcfCreateRegistryKey(CDiskProtection::SCacheFileData const *)
0x140008902  mov     ebx, eax
0x140008904  test    eax, eax
0x140008906  js      loc_1400089D3
0x14000890c  mov     rcx, [rsp+380h+hObject]; hObject
0x140008911  lea     rax, [rcx-1]
0x140008915  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140008919  ja      short loc_14000892A
0x14000891b  call    cs:__imp_CloseHandle
0x140008921  mov     [rsp+380h+hObject], 0
0x14000892a  mov     edx, 6; dwFileAttributes
0x14000892f  lea     rcx, [rbp+280h+FileName]; lpFileName
0x140008933  call    cs:__imp_SetFileAttributesW
0x140008939  test    eax, eax
0x14000893b  jnz     loc_1400089D3
0x140008941  call    cs:__imp_GetLastError
0x140008947  mov     ebx, eax
0x140008949  test    eax, eax
0x14000894b  jle     short loc_140008956
0x14000894d  movzx   ebx, ax
0x140008950  or      ebx, 80070000h
0x140008956  mov     eax, 80004005h
0x14000895b  lea     r12, aCbraex; "CBRAEx"
0x140008962  test    ebx, ebx
0x140008964  lea     rsi, aCdiskprotectio_63; "CDiskProtection::CreateCacheFile"
0x14000896b  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140008972  mov     r9, r12; unsigned __int16 *
0x140008975  cmovns  ebx, eax
0x140008978  lea     r15, aFsuccess; "fSuccess"
0x14000897f  mov     [rsp+380h+var_358], ebx; int
0x140008983  mov     r8, rsi; unsigned __int16 *
0x140008986  mov     edx, 1096h; unsigned int
0x14000898b  mov     [rsp+380h+var_360], r15; unsigned __int16 *
0x140008990  mov     rcx, rdi; unsigned __int16 *
0x140008993  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140008998  call    cs:__imp_IsDebuggerPresent
0x14000899e  test    eax, eax
0x1400089a0  jz      short loc_1400089AD
0x1400089a2  mov     r9d, 1096h
0x1400089a8  jmp     loc_140008863
0x1400089ad  mov     r8d, 1096h
0x1400089b3  mov     dword ptr [rsp+380h+var_350], ebx
0x1400089b7  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400089be  mov     qword ptr [rsp+380h+var_358], r15
0x1400089c3  mov     r9, rsi
0x1400089c6  mov     rdx, rdi
0x1400089c9  mov     [rsp+380h+var_360], r12
0x1400089ce  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400089d3  mov     rcx, [rbp+280h+Block]; Block
0x1400089d7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400089dc  mov     rcx, [rsp+380h+hObject]; hObject
0x1400089e1  lea     rax, [rcx-1]
0x1400089e5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400089e9  ja      short loc_1400089FA
0x1400089eb  call    cs:__imp_CloseHandle
0x1400089f1  mov     [rsp+380h+hObject], 0
0x1400089fa  mov     edx, ebx
0x1400089fc  lea     rcx, aCdiskprotectio_91; "CDiskProtection::CreateCacheFile - Exit"...
0x140008a03  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140008a08  mov     eax, ebx
0x140008a0a  mov     rcx, [rbp+280h+var_40]
0x140008a11  xor     rcx, rsp; StackCookie
0x140008a14  call    __security_check_cookie
0x140008a19  add     rsp, 358h
0x140008a20  pop     r15
0x140008a22  pop     r12
0x140008a24  pop     rdi
0x140008a25  pop     rsi
0x140008a26  pop     rbx
0x140008a27  pop     rbp
0x140008a28  retn
```
