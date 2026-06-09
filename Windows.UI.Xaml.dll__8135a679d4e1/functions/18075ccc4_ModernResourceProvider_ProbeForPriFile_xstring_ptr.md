# ModernResourceProvider::ProbeForPriFile(xstring_ptr *)

- ea: `0x18075ccc4`
- end: `0x18075cee6`
- name: `?ProbeForPriFile@ModernResourceProvider@@CAJPEAVxstring_ptr@@@Z`
- size: `546`
- prototype: `HRESULT __fastcall(xstring_ptr *pstrPriPath)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x1804fff94`

## callees

- `0x180004bc0`
- `0x180091d20`
- `0x1800af8e0`
- `0x1800d5330`
- `0x1800fe130`
- `0x1801800b8`
- `0x1801e2980`
- `0x1806c06e8`
- `0x18075ccc4`
- `0x18076e110`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18075cdb5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18075cdb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18075cd7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18075cdbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18075cdfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18075ce44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18075ce7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18075cd7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18075cdbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18075cdfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18075ce44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18075ce7c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineW` at `0x18075cd6c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineW` at `0x18075ce39`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineW` at `0x18075cd6c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineW` at `0x18075ce39`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18075cdf1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18075cdf1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18075ce71`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18075ce71`

## pseudocode

```c
__int64 __fastcall ModernResourceProvider::ProbeForPriFile(xruntime_string_ptr *pstrPriPath)
{
  HRESULT v2; // eax
  HRESULT v3; // ebx
  const wchar_t *BufferAndCount; // rax
  const WCHAR *Buffer; // rax
  signed int LastError; // eax
  signed int v7; // eax
  signed int v8; // eax
  signed int v9; // eax
  unsigned int v10; // eax
  HRESULT v11; // eax
  unsigned int pCount; // [rsp+20h] [rbp-E0h] BYREF
  xstring_ptr strPackagePath; // [rsp+28h] [rbp-D8h] BYREF
  wchar_t wszPriPath[264]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t wszExePath[264]; // [rsp+240h] [rbp+140h] BYREF

  strPackagePath.m_encodedStorage.Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
  xencoded_string_ptr::Reset(pstrPriPath);
  v2 = gps.m_pTarget->GetProcessPackagePath(&gps.m_pTarget->IPALProcessCharacteristics, &strPackagePath);
  v3 = v2;
  if ( v2 < 0 )
  {
    OnFailure_2990_(v2);
    goto $Cleanup_6738;
  }
  pCount = 0;
  BufferAndCount = xencoded_string_ptr::GetBufferAndCount(&strPackagePath.m_encodedStorage, &pCount);
  if ( BufferAndCount && pCount && *BufferAndCount )
  {
    Buffer = xstring_ptr_view::GetBuffer(&strPackagePath);
    if ( !PathCombineW(wszPriPath, Buffer, L"resources.pri") )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( v3 >= 0 )
        v3 = -2147467259;
LABEL_28:
      OnNewFailure_3049_(v3);
      goto $Cleanup_6738;
    }
  }
  else
  {
    if ( !GetModuleFileNameW(0, wszExePath, 0x104u) )
    {
      v7 = GetLastError();
      v3 = v7;
      if ( v7 > 0 )
        v3 = (unsigned __int16)v7 | 0x80070000;
      if ( v3 >= 0 )
        v3 = -2147467259;
      goto LABEL_28;
    }
    if ( !PathRemoveFileSpecW(wszExePath) )
    {
      v8 = GetLastError();
      v3 = v8;
      if ( v8 > 0 )
        v3 = (unsigned __int16)v8 | 0x80070000;
      if ( v3 >= 0 )
        v3 = -2147467259;
      goto LABEL_28;
    }
    if ( !PathCombineW(wszPriPath, wszExePath, L"resources.pri") )
    {
      v9 = GetLastError();
      v3 = v9;
      if ( v9 > 0 )
        v3 = (unsigned __int16)v9 | 0x80070000;
      if ( v3 >= 0 )
        v3 = -2147467259;
      goto LABEL_28;
    }
  }
  if ( GetFileAttributesW(wszPriPath) != -1 || GetLastError() != 2 )
  {
    v10 = xstrlen(wszPriPath);
    v11 = xstring_ptr::CloneBuffer(wszPriPath, v10, (xstring_ptr *)pstrPriPath);
    v3 = v11;
    if ( v11 < 0 )
      OnFailure_2990_(v11);
  }
$Cleanup_6738:
  xstring_ptr::~xstring_ptr(&strPackagePath);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18075ccc4  mov     [rsp-8+arg_8], rbx
0x18075ccc9  mov     [rsp-8+arg_10], rdi
0x18075ccce  push    rbp
0x18075cccf  lea     rbp, [rsp-360h]
0x18075ccd7  sub     rsp, 460h
0x18075ccde  mov     rax, cs:__security_cookie
0x18075cce5  xor     rax, rsp
0x18075cce8  mov     [rbp+360h+var_10], rax
0x18075ccef  mov     rax, qword ptr cs:?c_xencoded_string_ptr_null@xstring_ptr_constants@@2Uxencoded_string_ptr@@B.___u0; xencoded_string_ptr const xstring_ptr_constants::c_xencoded_string_ptr_null ...
0x18075ccf6  mov     rdi, pstrPriPath
0x18075ccf9  mov     qword ptr [rsp+460h+strPackagePath.m_encodedStorage.___u0], rax
0x18075ccfe  call    ?Reset@xencoded_string_ptr@@QEAAXXZ; xencoded_string_ptr::Reset(void)
0x18075cd03  mov     pstrPriPath, cs:?gps@@3V?$EncodedPtr@UIPlatformServices@@@@A.m_pTarget; EncodedPtr<IPlatformServices> gps ...
0x18075cd0a  lea     rdx, [rsp+460h+strPackagePath]
0x18075cd0f  add     pstrPriPath, 68h ; 'h'
0x18075cd13  mov     rax, [pstrPriPath]
0x18075cd16  mov     rax, [rax+18h]
0x18075cd1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18075cd1f  mov     ebx, eax
0x18075cd21  test    eax, eax
0x18075cd23  js      loc_18075CEAF
0x18075cd29  lea     rdx, [rsp+460h+pCount]; pCount
0x18075cd2e  mov     [rsp+460h+pCount], 0
0x18075cd36  lea     pstrPriPath, [rsp+460h+strPackagePath]; this
0x18075cd3b  call    ?GetBufferAndCount@xencoded_string_ptr@@QEBAPEBGPEAI@Z; xencoded_string_ptr::GetBufferAndCount(uint *)
0x18075cd40  test    rax, rax
0x18075cd43  jz      short loc_18075CDA6
0x18075cd45  cmp     [rsp+460h+pCount], 0
0x18075cd4a  jz      short loc_18075CDA6
0x18075cd4c  xor     ecx, ecx
0x18075cd4e  cmp     cx, [rax]
0x18075cd51  jz      short loc_18075CDA6
0x18075cd53  lea     pstrPriPath, [rsp+460h+strPackagePath]; this
0x18075cd58  call    ?GetBuffer@xstring_ptr_view@@QEBAPEBGXZ; xstring_ptr_view::GetBuffer(void)
0x18075cd5d  mov     rdx, rax; pszDir
0x18075cd60  lea     r8, pszFile; "resources.pri"
0x18075cd67  lea     pstrPriPath, [rsp+460h+wszPriPath]; pszDest
0x18075cd6c  call    cs:__imp_PathCombineW
0x18075cd72  test    rax, rax
0x18075cd75  jnz     loc_18075CE6C
0x18075cd7b  call    cs:__imp_GetLastError
0x18075cd81  mov     ebx, eax
0x18075cd83  test    eax, eax
0x18075cd85  jle     short loc_18075CD90
0x18075cd87  movzx   ebx, ax
0x18075cd8a  or      ebx, 80070000h
0x18075cd90  test    ebx, ebx
0x18075cd92  mov     eax, 80004005h
0x18075cd97  cmovns  ebx, eax
0x18075cd9a  mov     ecx, ebx; failedFrameHR
0x18075cd9c  call    OnNewFailure_3049_
0x18075cda1  jmp     $Cleanup_6738
0x18075cda6  mov     r8d, 104h; nSize
0x18075cdac  lea     rdx, [rbp+360h+wszExePath]; lpFilename
0x18075cdb3  xor     ecx, ecx; hModule
0x18075cdb5  call    cs:__imp_GetModuleFileNameW
0x18075cdbb  test    eax, eax
0x18075cdbd  jnz     short loc_18075CDEA
0x18075cdbf  call    cs:__imp_GetLastError
0x18075cdc5  mov     ebx, eax
0x18075cdc7  test    eax, eax
0x18075cdc9  jle     short loc_18075CDD4
0x18075cdcb  movzx   ebx, ax
0x18075cdce  or      ebx, 80070000h
0x18075cdd4  test    ebx, ebx
0x18075cdd6  mov     eax, 80004005h
0x18075cddb  cmovns  ebx, eax
0x18075cdde  mov     ecx, ebx; failedFrameHR
0x18075cde0  call    OnNewFailure_3049_
0x18075cde5  jmp     $Cleanup_6738
0x18075cdea  lea     pstrPriPath, [rbp+360h+wszExePath]; pszPath
0x18075cdf1  call    cs:__imp_PathRemoveFileSpecW
0x18075cdf7  test    eax, eax
0x18075cdf9  jnz     short loc_18075CE26
0x18075cdfb  call    cs:__imp_GetLastError
0x18075ce01  mov     ebx, eax
0x18075ce03  test    eax, eax
0x18075ce05  jle     short loc_18075CE10
0x18075ce07  movzx   ebx, ax
0x18075ce0a  or      ebx, 80070000h
0x18075ce10  test    ebx, ebx
0x18075ce12  mov     eax, 80004005h
0x18075ce17  cmovns  ebx, eax
0x18075ce1a  mov     ecx, ebx; failedFrameHR
0x18075ce1c  call    OnNewFailure_3049_
0x18075ce21  jmp     $Cleanup_6738
0x18075ce26  lea     r8, pszFile; "resources.pri"
0x18075ce2d  lea     rdx, [rbp+360h+wszExePath]; pszDir
0x18075ce34  lea     pstrPriPath, [rsp+460h+wszPriPath]; pszDest
0x18075ce39  call    cs:__imp_PathCombineW
0x18075ce3f  test    rax, rax
0x18075ce42  jnz     short loc_18075CE6C
0x18075ce44  call    cs:__imp_GetLastError
0x18075ce4a  mov     ebx, eax
0x18075ce4c  test    eax, eax
0x18075ce4e  jle     short loc_18075CE59
0x18075ce50  movzx   ebx, ax
0x18075ce53  or      ebx, 80070000h
0x18075ce59  test    ebx, ebx
0x18075ce5b  mov     eax, 80004005h
0x18075ce60  cmovns  ebx, eax
0x18075ce63  mov     ecx, ebx; failedFrameHR
0x18075ce65  call    OnNewFailure_3049_
0x18075ce6a  jmp     short $Cleanup_6738
0x18075ce6c  lea     pstrPriPath, [rsp+460h+wszPriPath]; lpFileName
0x18075ce71  call    cs:__imp_GetFileAttributesW
0x18075ce77  cmp     eax, 0FFFFFFFFh
0x18075ce7a  jnz     short loc_18075CE87
0x18075ce7c  call    cs:__imp_GetLastError
0x18075ce82  cmp     eax, 2
0x18075ce85  jz      short $Cleanup_6738
0x18075ce87  lea     pstrPriPath, [rsp+460h+wszPriPath]; pString
0x18075ce8c  call    ?xstrlen@@YAIPEBG@Z; xstrlen(ushort const *)
0x18075ce91  mov     edx, eax; count
0x18075ce93  lea     pstrPriPath, [rsp+460h+wszPriPath]; buffer
0x18075ce98  mov     r8, rdi; pstrCloned
0x18075ce9b  call    ?CloneBuffer@xstring_ptr@@SAJPEBGIPEAV1@@Z; xstring_ptr::CloneBuffer(ushort const *,uint,xstring_ptr *)
0x18075cea0  mov     ebx, eax
0x18075cea2  test    eax, eax
0x18075cea4  jns     short $Cleanup_6738
0x18075cea6  mov     ecx, eax; failedFrameHR
0x18075cea8  call    OnFailure_2990_
0x18075cead  jmp     short $Cleanup_6738
0x18075ceaf  mov     ecx, eax; failedFrameHR
0x18075ceb1  call    OnFailure_2990_
0x18075ceb6  lea     pstrPriPath, [rsp+460h+strPackagePath]; this
0x18075cebb  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x18075cec0  mov     eax, ebx
0x18075cec2  mov     pstrPriPath, [rbp+360h+var_10]
0x18075cec9  xor     pstrPriPath, rsp; StackCookie
0x18075cecc  call    __security_check_cookie
0x18075ced1  lea     r11, [rsp+460h+var_s0]
0x18075ced9  mov     rbx, [r11+18h]
0x18075cedd  mov     rdi, [r11+20h]
0x18075cee1  mov     rsp, r11
0x18075cee4  pop     rbp
0x18075cee5  retn
```
