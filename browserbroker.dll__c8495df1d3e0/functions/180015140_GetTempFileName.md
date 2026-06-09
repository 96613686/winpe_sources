# _GetTempFileName

- ea: `0x180015140`
- end: `0x1800152a5`
- name: `_GetTempFileName`
- size: `357`
- prototype: `__int64 __fastcall(LPCWSTR pszPath)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014c9c`

## callees

- `0x180002ce0`
- `0x1800037ac`
- `0x180006c90`
- `0x18000dc94`
- `0x180015140`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800151d2`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800151d2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800151a4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800151a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800151f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800151f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800151ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800151ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015245`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015266`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015245`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015266`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18001522f`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18001522f`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180015193`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180015193`

## string_xrefs

- `0x1800151e2`: `BrokerDownloadToTempFile`
- `0x180015211`: `onecoreuap\inetcore\spartan\desktopbroker\downloadtotempfile.cpp`

## pseudocode

```c
__int64 __fastcall GetTempFileName(LPCWSTR pszPath, _QWORD *a2)
{
  const WCHAR *FileNameW; // rax
  const WCHAR *v5; // rbx
  unsigned __int64 v6; // rsi
  unsigned __int64 i; // rdi
  void *v8; // rdi
  const char *v9; // r9
  unsigned int v10; // ebx
  signed int LastError; // eax
  signed int v12; // eax
  void *v14; // [rsp+20h] [rbp-248h] BYREF
  WCHAR Buffer; // [rsp+30h] [rbp-238h] BYREF
  _BYTE v16[526]; // [rsp+32h] [rbp-236h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  *a2 = 0;
  Buffer = 0;
  memset_0(v16, 0, 0x208u);
  if ( GetTempPathW(0x105u, &Buffer) )
  {
    FileNameW = PathFindFileNameW(pszPath);
    v5 = FileNameW;
    if ( FileNameW == pszPath )
    {
LABEL_9:
      v5 = L"BrokerDownloadToTempFile";
    }
    else
    {
      v6 = -1;
      do
        ++v6;
      while ( FileNameW[v6] );
      for ( i = 0; i < v6; ++i )
      {
        if ( wcschr(L"?<>:\"|*\\/", v5[i]) )
          goto LABEL_9;
      }
    }
    v8 = CoTaskMemAlloc(0x208u);
    CoTaskMemFree(0);
    v14 = v8;
    if ( !v8 )
      wil::details::in1diag3::_FailFast_NullAlloc(
        retaddr,
        (void *)0x2F,
        (int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\downloadtotempfile.cpp",
        v9);
    if ( GetTempFileNameW(&Buffer, v5, 0, (LPWSTR)v8) )
    {
      v10 = 0;
      v14 = 0;
      *a2 = v8;
    }
    else
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
    }
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v14);
  }
  else
  {
    v12 = GetLastError();
    v10 = v12;
    if ( v12 > 0 )
      return (unsigned __int16)v12 | 0x80070000;
  }
  return v10;
}

```

## disassembly

```asm
0x180015140  mov     [rsp+arg_10], rbx
0x180015145  mov     [rsp+arg_18], rbp
0x18001514a  push    rsi
0x18001514b  push    rdi
0x18001514c  push    r14
0x18001514e  sub     rsp, 250h
0x180015155  mov     rax, cs:__security_cookie
0x18001515c  xor     rax, rsp
0x18001515f  mov     [rsp+268h+var_28], rax
0x180015167  xor     ebp, ebp
0x180015169  mov     r14, rdx
0x18001516c  mov     [rdx], rbp
0x18001516f  mov     rdi, rcx
0x180015172  xor     edx, edx; Val
0x180015174  mov     [rsp+268h+Buffer], bp
0x180015179  mov     r8d, 208h; Size
0x18001517f  lea     rcx, [rsp+268h+var_236]; void *
0x180015184  call    memset_0
0x180015189  lea     rdx, [rsp+268h+Buffer]; lpBuffer
0x18001518e  mov     ecx, 105h; nBufferLength
0x180015193  call    cs:__imp_GetTempPathW
0x180015199  test    eax, eax
0x18001519b  jz      loc_180015266
0x1800151a1  mov     rcx, rdi; pszPath
0x1800151a4  call    cs:__imp_PathFindFileNameW
0x1800151aa  mov     rbx, rax
0x1800151ad  cmp     rax, rdi
0x1800151b0  jz      short loc_1800151E2
0x1800151b2  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800151b6  inc     rsi
0x1800151b9  cmp     [rax+rsi*2], bp
0x1800151bd  jnz     short loc_1800151B6
0x1800151bf  mov     rdi, rbp
0x1800151c2  cmp     rdi, rsi
0x1800151c5  jnb     short loc_1800151E9
0x1800151c7  movzx   edx, word ptr [rbx+rdi*2]; Ch
0x1800151cb  lea     rcx, Str; "?<>:\"|*\\/"
0x1800151d2  call    cs:__imp_wcschr
0x1800151d8  test    rax, rax
0x1800151db  jnz     short loc_1800151E2
0x1800151dd  inc     rdi
0x1800151e0  jmp     short loc_1800151C2
0x1800151e2  lea     rbx, aBrokerdownload; "BrokerDownloadToTempFile"
0x1800151e9  mov     ecx, 208h; cb
0x1800151ee  call    cs:__imp_CoTaskMemAlloc
0x1800151f4  xor     ecx, ecx; pv
0x1800151f6  mov     rdi, rax
0x1800151f9  call    cs:__imp_CoTaskMemFree
0x1800151ff  mov     [rsp+268h+var_248], rdi
0x180015204  test    rdi, rdi
0x180015207  jnz     short loc_180015221
0x180015209  mov     rcx, [rsp+268h]; this
0x180015211  lea     r8, aOnecoreuapInet; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x180015218  lea     edx, [rdi+2Fh]; void *
0x18001521b  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x180015221  mov     r9, rdi; lpTempFileName
0x180015224  lea     rcx, [rsp+268h+Buffer]; lpPathName
0x180015229  xor     r8d, r8d; uUnique
0x18001522c  mov     rdx, rbx; lpPrefixString
0x18001522f  call    cs:__imp_GetTempFileNameW
0x180015235  test    eax, eax
0x180015237  jz      short loc_180015245
0x180015239  mov     ebx, ebp
0x18001523b  mov     [rsp+268h+var_248], rbp
0x180015240  mov     [r14], rdi
0x180015243  jmp     short loc_18001525A
0x180015245  call    cs:__imp_GetLastError
0x18001524b  mov     ebx, eax
0x18001524d  test    eax, eax
0x18001524f  jle     short loc_18001525A
0x180015251  movzx   ebx, ax
0x180015254  or      ebx, 80070000h
0x18001525a  lea     rcx, [rsp+268h+var_248]
0x18001525f  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180015264  jmp     short loc_18001527B
0x180015266  call    cs:__imp_GetLastError
0x18001526c  mov     ebx, eax
0x18001526e  test    eax, eax
0x180015270  jle     short loc_18001527B
0x180015272  movzx   ebx, ax
0x180015275  or      ebx, 80070000h
0x18001527b  mov     eax, ebx
0x18001527d  mov     rcx, [rsp+268h+var_28]
0x180015285  xor     rcx, rsp; StackCookie
0x180015288  call    __security_check_cookie
0x18001528d  lea     r11, [rsp+268h+var_18]
0x180015295  mov     rbx, [r11+30h]
0x180015299  mov     rbp, [r11+38h]
0x18001529d  mov     rsp, r11
0x1800152a0  pop     r14
0x1800152a2  pop     rdi
0x1800152a3  pop     rsi
0x1800152a4  retn
```
