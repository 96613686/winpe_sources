# CWinUriLegacy::GetHost(uint *,ushort *)

- ea: `0x18074c600`
- end: `0x18074c81c`
- name: `?GetHost@CWinUriLegacy@@UEBAJPEAIPEAG@Z`
- size: `540`
- prototype: `HRESULT __fastcall(CWinUriLegacy *this, unsigned int *pBufferLength, wchar_t *pszBuffer)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18074c600`

## callees

- `0x180004bc0`
- `0x180687a78`
- `0x18069f6ac`
- `0x1806c06e8`
- `0x18074c600`
- `0x18076e110`
- `0x18076f08c`
- `0x180c010f0`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18074c666`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18074c666`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18074c7f3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18074c7f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18074c6a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18074c6a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18074c674`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18074c6e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18074c674`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18074c6e6`
- `OLEAUT32!__imp_SysFreeString` at `0x18074c7e5`
- `OLEAUT32!__imp_SysFreeString` at `0x18074c7e5`
- `OLEAUT32!__imp_SysStringLen` at `0x18074c765`
- `OLEAUT32!__imp_SysStringLen` at `0x18074c765`
- `WININET!InternetCreateUrlW` at `0x18074c6dc`
- `WININET!InternetCreateUrlW` at `0x18074c6dc`

## string_xrefs

- `0x18074c65f`: `urlmon.dll`
- `0x18074c69f`: `CreateUri`

## pseudocode

```c
__int64 __fastcall CWinUriLegacy::GetHost(CWinUriLegacy *this, unsigned int *pBufferLength, wchar_t *pszBuffer)
{
  unsigned int v3; // r12d
  HMODULE Library; // rax
  HMODULE v8; // r14
  signed int v9; // eax
  HRESULT Host; // edi
  FARPROC ProcAddress; // rbx
  signed int LastError; // eax
  HRESULT v13; // eax
  UINT v14; // eax
  __int64 v15; // rbx
  IUri *pIUri; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *bstrPunycodeHost; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cTempUrl[4]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszTempUrl[2088]; // [rsp+50h] [rbp-B0h] BYREF

  v3 = *pBufferLength;
  cTempUrl[0] = 2085;
  bstrPunycodeHost = 0;
  pIUri = 0;
  Library = LoadLibraryExW(L"urlmon.dll", 0, 0x800u);
  v8 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "CreateUri");
    if ( ProcAddress )
    {
      if ( InternetCreateUrlW(&this->m_uc, 0, pszTempUrl, cTempUrl) )
      {
        v13 = ((__int64 (__fastcall *)(wchar_t *, __int64, _QWORD, IUri **))ProcAddress)(pszTempUrl, 19264, 0, &pIUri);
        Host = v13;
        if ( v13 < 0
          || (v13 = ((__int64 (__fastcall *)(IUri *, __int64, wchar_t **))pIUri->GetPropertyBSTR)(
                      pIUri,
                      6,
                      &bstrPunycodeHost),
              Host = v13,
              v13 < 0) )
        {
          OnFailure_2990_(v13);
        }
        else if ( bstrPunycodeHost )
        {
          v14 = SysStringLen(bstrPunycodeHost);
          *pBufferLength = v14;
          if ( pszBuffer )
          {
            if ( v3 >= v14 + 1 )
            {
              v15 = v14;
              memcpy_0(pszBuffer, bstrPunycodeHost, v15 * 2);
              pszBuffer[v15] = 0;
            }
            else
            {
              Host = -2147467259;
              OnFailure_977_(v14 + 1);
            }
          }
        }
        else
        {
          Host = -2147418113;
          OnNewFailure_2955_(0);
        }
      }
      else
      {
        LastError = GetLastError();
        Host = LastError;
        if ( LastError > 0 )
          Host = (unsigned __int16)LastError | 0x80070000;
        if ( Host >= 0 )
          Host = -2147467259;
        OnNewFailure_3049_(Host);
      }
    }
    else
    {
      Host = CWinUriLegacy::GetHost(this, pBufferLength, pszBuffer);
    }
  }
  else
  {
    v9 = GetLastError();
    Host = v9;
    if ( v9 > 0 )
      Host = (unsigned __int16)v9 | 0x80070000;
    if ( Host >= 0 )
      Host = -2147467259;
    OnNewFailure_3049_(Host);
  }
  if ( pIUri )
  {
    pIUri->Release(pIUri);
    pIUri = 0;
  }
  SysFreeString(bstrPunycodeHost);
  if ( v8 )
    FreeLibrary(v8);
  return (unsigned int)Host;
}

```

## disassembly

```asm
0x18074c600  push    rbp
0x18074c602  push    rbx
0x18074c603  push    rsi
0x18074c604  push    rdi
0x18074c605  push    r12
0x18074c607  push    r14
0x18074c609  push    r15
0x18074c60b  lea     rbp, [rsp-0FB0h]
0x18074c613  mov     eax, 10B0h
0x18074c618  call    _alloca_probe
0x18074c61d  sub     rsp, rax
0x18074c620  mov     rax, cs:__security_cookie
0x18074c627  xor     rax, rsp
0x18074c62a  mov     [rbp+0FE0h+var_40], rax
0x18074c631  mov     r12d, [pBufferLength]
0x18074c634  mov     rsi, pszBuffer
0x18074c637  mov     r15, pBufferLength
0x18074c63a  mov     [rsp+10E0h+cTempUrl], 825h
0x18074c642  mov     rdi, this
0x18074c645  mov     [rsp+10E0h+bstrPunycodeHost], 0
0x18074c64e  xor     edx, edx; hFile
0x18074c650  mov     [rsp+10E0h+pIUri], 0
0x18074c659  mov     r8d, 800h; dwFlags
0x18074c65f  lea     this, aUrlmonDll_0; "urlmon.dll"
0x18074c666  call    cs:__imp_LoadLibraryExW
0x18074c66c  mov     r14, rax
0x18074c66f  test    rax, rax
0x18074c672  jnz     short loc_18074C69F
0x18074c674  call    cs:__imp_GetLastError
0x18074c67a  mov     edi, eax
0x18074c67c  test    eax, eax
0x18074c67e  jle     short loc_18074C689
0x18074c680  movzx   edi, ax
0x18074c683  or      edi, 80070000h
0x18074c689  test    edi, edi
0x18074c68b  mov     eax, 80004005h
0x18074c690  cmovns  edi, eax
0x18074c693  mov     ecx, edi; failedFrameHR
0x18074c695  call    OnNewFailure_3049_
0x18074c69a  jmp     $Cleanup_6706
0x18074c69f  lea     pBufferLength, aCreateuri_0; "CreateUri"
0x18074c6a6  mov     this, r14; hModule
0x18074c6a9  call    cs:__imp_GetProcAddress
0x18074c6af  mov     rbx, rax
0x18074c6b2  test    rax, rax
0x18074c6b5  jnz     short loc_18074C6CC
0x18074c6b7  mov     pszBuffer, rsi; pszBuffer
0x18074c6ba  mov     pBufferLength, r15; pBufferLength
0x18074c6bd  mov     this, rdi; this
0x18074c6c0  call    ?GetHost@CWinUriLegacy@@UEBAJPEAIPEAG@Z; CWinUriLegacy::GetHost(uint *,ushort *)
0x18074c6c5  mov     edi, eax
0x18074c6c7  jmp     $Cleanup_6706
0x18074c6cc  lea     this, [rdi+18h]; lpUrlComponents
0x18074c6d0  xor     edx, edx; dwFlags
0x18074c6d2  lea     r9, [rsp+10E0h+cTempUrl]; lpdwUrlLength
0x18074c6d7  lea     pszBuffer, [rsp+10E0h+pszTempUrl]; lpszUrl
0x18074c6dc  call    cs:__imp_InternetCreateUrlW
0x18074c6e2  test    eax, eax
0x18074c6e4  jnz     short loc_18074C711
0x18074c6e6  call    cs:__imp_GetLastError
0x18074c6ec  mov     edi, eax
0x18074c6ee  test    eax, eax
0x18074c6f0  jle     short loc_18074C6FB
0x18074c6f2  movzx   edi, ax
0x18074c6f5  or      edi, 80070000h
0x18074c6fb  test    edi, edi
0x18074c6fd  mov     eax, 80004005h
0x18074c702  cmovns  edi, eax
0x18074c705  mov     ecx, edi; failedFrameHR
0x18074c707  call    OnNewFailure_3049_
0x18074c70c  jmp     $Cleanup_6706
0x18074c711  lea     r9, [rsp+10E0h+pIUri]
0x18074c716  xor     r8d, r8d
0x18074c719  mov     edx, 4B40h
0x18074c71e  lea     this, [rsp+10E0h+pszTempUrl]
0x18074c723  mov     rax, rbx
0x18074c726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18074c72b  mov     edi, eax
0x18074c72d  test    eax, eax
0x18074c72f  js      loc_18074C7BA
0x18074c735  mov     this, [rsp+10E0h+pIUri]
0x18074c73a  lea     pszBuffer, [rsp+10E0h+bstrPunycodeHost]
0x18074c73f  mov     r9d, 4
0x18074c745  mov     rax, [this]
0x18074c748  lea     edx, [r9+2]
0x18074c74c  mov     rax, [rax+18h]
0x18074c750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18074c755  mov     edi, eax
0x18074c757  test    eax, eax
0x18074c759  js      short loc_18074C7B1
0x18074c75b  mov     this, [rsp+10E0h+bstrPunycodeHost]; failedFrameHR
0x18074c760  test    this, this
0x18074c763  jz      short loc_18074C7A5
0x18074c765  call    cs:__imp_SysStringLen
0x18074c76b  mov     [r15], eax
0x18074c76e  test    rsi, rsi
0x18074c771  jz      short $Cleanup_6706
0x18074c773  lea     ecx, [rax+1]; failedFrameHR
0x18074c776  cmp     r12d, ecx
0x18074c779  jnb     short loc_18074C787
0x18074c77b  mov     edi, 80004005h
0x18074c780  call    OnFailure_977_
0x18074c785  jmp     short $Cleanup_6706
0x18074c787  mov     pBufferLength, [rsp+10E0h+bstrPunycodeHost]; Src
0x18074c78c  mov     this, rsi; void *
0x18074c78f  mov     eax, eax
0x18074c791  lea     rbx, [rax+rax]
0x18074c795  mov     pszBuffer, rbx; Size
0x18074c798  call    memcpy_0
0x18074c79d  xor     eax, eax
0x18074c79f  mov     [rbx+rsi], ax
0x18074c7a3  jmp     short $Cleanup_6706
0x18074c7a5  mov     edi, 8000FFFFh
0x18074c7aa  call    OnNewFailure_2955_
0x18074c7af  jmp     short $Cleanup_6706
0x18074c7b1  mov     ecx, eax; failedFrameHR
0x18074c7b3  call    OnFailure_2990_
0x18074c7b8  jmp     short $Cleanup_6706
0x18074c7ba  mov     ecx, eax; failedFrameHR
0x18074c7bc  call    OnFailure_2990_
0x18074c7c1  mov     this, [rsp+10E0h+pIUri]
0x18074c7c6  test    this, this
0x18074c7c9  jz      short loc_18074C7E0
0x18074c7cb  mov     rax, [this]
0x18074c7ce  mov     rax, [rax+10h]
0x18074c7d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18074c7d7  mov     [rsp+10E0h+pIUri], 0
0x18074c7e0  mov     this, [rsp+10E0h+bstrPunycodeHost]; bstrString
0x18074c7e5  call    cs:__imp_SysFreeString
0x18074c7eb  test    r14, r14
0x18074c7ee  jz      short loc_18074C7F9
0x18074c7f0  mov     this, r14; hLibModule
0x18074c7f3  call    cs:__imp_FreeLibrary
0x18074c7f9  mov     eax, edi
0x18074c7fb  mov     this, [rbp+0FE0h+var_40]
0x18074c802  xor     this, rsp; StackCookie
0x18074c805  call    __security_check_cookie
0x18074c80a  add     rsp, 10B0h
0x18074c811  pop     r15
0x18074c813  pop     r14
0x18074c815  pop     r12
0x18074c817  pop     rdi
0x18074c818  pop     rsi
0x18074c819  pop     rbx
0x18074c81a  pop     rbp
0x18074c81b  retn
```
