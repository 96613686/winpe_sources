# OneCore::Base::Telemetry::OneSettingsQuery::RetrieveOneSettingsFromWeb(ushort const *)

- ea: `0x180021ca8`
- end: `0x180021f12`
- name: `?RetrieveOneSettingsFromWeb@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBG@Z`
- size: `618`
- prototype: `__int64 __fastcall(HINTERNET *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001acb4`

## callees

- `0x18001a878`
- `0x18001ec50`
- `0x180021ca8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021d13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021daa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021e61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021d13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021daa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021e61`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021dcd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021e3a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021dcd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021e3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021dbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021e29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021e8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021ef0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021dbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021e29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021e8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021ef0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021e9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021eff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021e9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021eff`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x180021ec7`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x180021ec7`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x180021e16`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x180021e16`
- `WINHTTP!WinHttpReadData` at `0x180021e57`
- `WINHTTP!WinHttpReadData` at `0x180021e57`
- `WINHTTP!WinHttpSendRequest` at `0x180021d09`
- `WINHTTP!WinHttpSendRequest` at `0x180021d09`
- `WINHTTP!WinHttpReceiveResponse` at `0x180021d37`
- `WINHTTP!WinHttpReceiveResponse` at `0x180021d37`
- `WINHTTP!WinHttpQueryHeaders` at `0x180021d66`
- `WINHTTP!WinHttpQueryHeaders` at `0x180021da0`
- `WINHTTP!WinHttpQueryHeaders` at `0x180021e00`
- `WINHTTP!WinHttpQueryHeaders` at `0x180021d66`
- `WINHTTP!WinHttpQueryHeaders` at `0x180021da0`
- `WINHTTP!WinHttpQueryHeaders` at `0x180021e00`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::RetrieveOneSettingsFromWeb(
        HINTERNET *this,
        const unsigned __int16 *a2)
{
  int Headers; // ebx
  signed int LastError; // eax
  void *v5; // rcx
  void *v6; // rcx
  DWORD v7; // ebx
  HANDLE ProcessHeap; // rax
  void *v9; // rax
  DWORD v10; // ebx
  HANDLE v11; // rax
  char *v12; // rax
  char *v13; // rsi
  signed int v14; // eax
  HANDLE v15; // rax
  HANDLE v16; // rax
  DWORD pdwAuthTarget; // [rsp+40h] [rbp-10h] BYREF
  DWORD dwFirstScheme; // [rsp+44h] [rbp-Ch] BYREF
  LPCWSTR lpszHeaders; // [rsp+48h] [rbp-8h] BYREF
  DWORD dwBufferLength; // [rsp+88h] [rbp+38h] BYREF
  int v22; // [rsp+8Ch] [rbp+3Ch]
  int Buffer; // [rsp+90h] [rbp+40h] BYREF
  DWORD dwSupportedSchemes; // [rsp+98h] [rbp+48h] BYREF

  v22 = HIDWORD(a2);
  lpszHeaders = 0;
  Buffer = 0;
  dwBufferLength = 0;
  dwSupportedSchemes = 0;
  dwFirstScheme = 0;
  pdwAuthTarget = 0;
  Headers = OneCore::Base::Telemetry::OneSettingsQuery::CreateHeaders(
              (OneCore::Base::Telemetry::OneSettingsQuery *)this,
              a2,
              (unsigned __int16 **)&lpszHeaders);
  if ( Headers < 0 )
    goto LABEL_26;
  if ( !WinHttpSendRequest(this[2], lpszHeaders, 0xFFFFFFFF, 0, 0, 0, 0) )
    goto LABEL_3;
  if ( !WinHttpReceiveResponse(this[2], 0) )
    goto LABEL_3;
  v5 = this[2];
  dwBufferLength = 4;
  if ( !WinHttpQueryHeaders(v5, 0x20000013u, 0, &Buffer, &dwBufferLength, 0) )
    goto LABEL_3;
  if ( Buffer != 200 )
  {
    if ( Buffer == 304 )
    {
      Headers = 1;
    }
    else if ( Buffer != 407
           || (WinHttpQueryAuthSchemes(this[2], &dwSupportedSchemes, &dwFirstScheme, &pdwAuthTarget),
               (dwSupportedSchemes & 1) == 0)
           || (Headers = -2147024891, pdwAuthTarget != 1) )
    {
      Headers = -2147467259;
    }
    goto LABEL_26;
  }
  v6 = this[2];
  dwBufferLength = 0;
  if ( !WinHttpQueryHeaders(v6, 0x36u, 0, 0, &dwBufferLength, 0) && GetLastError() != 122 )
    goto LABEL_3;
  v7 = dwBufferLength;
  ProcessHeap = GetProcessHeap();
  v9 = HeapAlloc(ProcessHeap, 8u, v7);
  this[4] = v9;
  if ( !v9 )
  {
LABEL_11:
    Headers = -2147024882;
    goto LABEL_26;
  }
  if ( !WinHttpQueryHeaders(this[2], 0x36u, 0, v9, &dwBufferLength, 0)
    || !WinHttpQueryDataAvailable(this[2], &dwBufferLength) )
  {
LABEL_3:
    LastError = GetLastError();
    Headers = LastError;
    if ( LastError > 0 )
      Headers = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_26;
  }
  v10 = dwBufferLength + 1;
  v11 = GetProcessHeap();
  v12 = (char *)HeapAlloc(v11, 8u, v10);
  v13 = v12;
  if ( !v12 )
    goto LABEL_11;
  if ( WinHttpReadData(this[2], v12, dwBufferLength, &dwBufferLength) )
  {
    v13[dwBufferLength] = 0;
    Headers = OneCore::Base::Telemetry::OneSettingsQuery::ParseJsonResult(
                (OneCore::Base::Telemetry::OneSettingsQuery *)this,
                v13);
  }
  else
  {
    v14 = GetLastError();
    Headers = v14;
    if ( v14 > 0 )
      Headers = (unsigned __int16)v14 | 0x80070000;
  }
  v15 = GetProcessHeap();
  HeapFree(v15, 0, v13);
LABEL_26:
  if ( lpszHeaders )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, (LPVOID)lpszHeaders);
  }
  return (unsigned int)Headers;
}

```

## disassembly

```asm
0x180021ca8  mov     qword ptr [rsp-28h+dwBufferLength], rdx
0x180021cad  push    rbp
0x180021cae  push    rbx
0x180021caf  push    rsi
0x180021cb0  push    rdi
0x180021cb1  push    r15
0x180021cb3  mov     rbp, rsp
0x180021cb6  sub     rsp, 50h
0x180021cba  xor     r15d, r15d
0x180021cbd  lea     r8, [rbp+lpszHeaders]; unsigned __int16 **
0x180021cc1  mov     [rbp+lpszHeaders], r15
0x180021cc5  mov     rdi, rcx
0x180021cc8  mov     [rbp+Buffer], r15d
0x180021ccc  mov     [rbp+dwBufferLength], r15d
0x180021cd0  mov     [rbp+dwSupportedSchemes], r15d
0x180021cd4  mov     [rbp+dwFirstScheme], r15d
0x180021cd8  mov     [rbp+pdwAuthTarget], r15d
0x180021cdc  call    ?CreateHeaders@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBGPEAPEAG@Z; OneCore::Base::Telemetry::OneSettingsQuery::CreateHeaders(ushort const *,ushort * *)
0x180021ce1  mov     ebx, eax
0x180021ce3  test    eax, eax
0x180021ce5  js      loc_180021EEA
0x180021ceb  mov     rdx, [rbp+lpszHeaders]; lpszHeaders
0x180021cef  xor     r9d, r9d; lpOptional
0x180021cf2  mov     rcx, [rdi+10h]; hRequest
0x180021cf6  or      r8d, 0FFFFFFFFh; dwHeadersLength
0x180021cfa  mov     [rsp+50h+dwContext], r15; dwContext
0x180021cff  mov     [rsp+50h+dwTotalLength], r15d; dwTotalLength
0x180021d04  mov     [rsp+50h+dwOptionalLength], r15d; dwOptionalLength
0x180021d09  call    cs:__imp_WinHttpSendRequest
0x180021d0f  test    eax, eax
0x180021d11  jnz     short loc_180021D31
0x180021d13  call    cs:__imp_GetLastError
0x180021d19  mov     ebx, eax
0x180021d1b  test    eax, eax
0x180021d1d  jle     loc_180021EEA
0x180021d23  movzx   ebx, ax
0x180021d26  or      ebx, 80070000h
0x180021d2c  jmp     loc_180021EEA
0x180021d31  mov     rcx, [rdi+10h]; hRequest
0x180021d35  xor     edx, edx; lpReserved
0x180021d37  call    cs:__imp_WinHttpReceiveResponse
0x180021d3d  test    eax, eax
0x180021d3f  jz      short loc_180021D13
0x180021d41  mov     rcx, [rdi+10h]; hRequest
0x180021d45  lea     rax, [rbp+dwBufferLength]
0x180021d49  mov     qword ptr [rsp+50h+dwTotalLength], r15; lpdwIndex
0x180021d4e  lea     r9, [rbp+Buffer]; lpBuffer
0x180021d52  xor     r8d, r8d; pwszName
0x180021d55  mov     qword ptr [rsp+50h+dwOptionalLength], rax; lpdwBufferLength
0x180021d5a  mov     edx, 20000013h; dwInfoLevel
0x180021d5f  mov     [rbp+dwBufferLength], 4
0x180021d66  call    cs:__imp_WinHttpQueryHeaders
0x180021d6c  test    eax, eax
0x180021d6e  jz      short loc_180021D13
0x180021d70  mov     eax, [rbp+Buffer]
0x180021d73  cmp     eax, 0C8h
0x180021d78  jnz     loc_180021EA2
0x180021d7e  mov     rcx, [rdi+10h]; hRequest
0x180021d82  lea     rax, [rbp+dwBufferLength]
0x180021d86  xor     r9d, r9d; lpBuffer
0x180021d89  mov     qword ptr [rsp+50h+dwTotalLength], r15; lpdwIndex
0x180021d8e  xor     r8d, r8d; pwszName
0x180021d91  mov     [rbp+dwBufferLength], r15d
0x180021d95  mov     qword ptr [rsp+50h+dwOptionalLength], rax; lpdwBufferLength
0x180021d9a  lea     esi, [r9+36h]
0x180021d9e  mov     edx, esi; dwInfoLevel
0x180021da0  call    cs:__imp_WinHttpQueryHeaders
0x180021da6  test    eax, eax
0x180021da8  jnz     short loc_180021DB9
0x180021daa  call    cs:__imp_GetLastError
0x180021db0  cmp     eax, 7Ah ; 'z'
0x180021db3  jnz     loc_180021D13
0x180021db9  mov     ebx, [rbp+dwBufferLength]
0x180021dbc  call    cs:__imp_GetProcessHeap
0x180021dc2  mov     r8d, ebx; dwBytes
0x180021dc5  mov     edx, 8; dwFlags
0x180021dca  mov     rcx, rax; hHeap
0x180021dcd  call    cs:__imp_HeapAlloc
0x180021dd3  mov     [rdi+20h], rax
0x180021dd7  test    rax, rax
0x180021dda  jnz     short loc_180021DE6
0x180021ddc  mov     ebx, 8007000Eh
0x180021de1  jmp     loc_180021EEA
0x180021de6  lea     rcx, [rbp+dwBufferLength]
0x180021dea  mov     qword ptr [rsp+50h+dwTotalLength], r15; lpdwIndex
0x180021def  mov     qword ptr [rsp+50h+dwOptionalLength], rcx; lpdwBufferLength
0x180021df4  mov     r9, rax; lpBuffer
0x180021df7  mov     rcx, [rdi+10h]; hRequest
0x180021dfb  xor     r8d, r8d; pwszName
0x180021dfe  mov     edx, esi; dwInfoLevel
0x180021e00  call    cs:__imp_WinHttpQueryHeaders
0x180021e06  test    eax, eax
0x180021e08  jz      loc_180021D13
0x180021e0e  mov     rcx, [rdi+10h]; hRequest
0x180021e12  lea     rdx, [rbp+dwBufferLength]; lpdwNumberOfBytesAvailable
0x180021e16  call    cs:__imp_WinHttpQueryDataAvailable
0x180021e1c  test    eax, eax
0x180021e1e  jz      loc_180021D13
0x180021e24  mov     ebx, [rbp+dwBufferLength]
0x180021e27  inc     ebx
0x180021e29  call    cs:__imp_GetProcessHeap
0x180021e2f  mov     r8d, ebx; dwBytes
0x180021e32  mov     edx, 8; dwFlags
0x180021e37  mov     rcx, rax; hHeap
0x180021e3a  call    cs:__imp_HeapAlloc
0x180021e40  mov     rsi, rax
0x180021e43  test    rax, rax
0x180021e46  jz      short loc_180021DDC
0x180021e48  mov     r8d, [rbp+dwBufferLength]; dwNumberOfBytesToRead
0x180021e4c  lea     r9, [rbp+dwBufferLength]; lpdwNumberOfBytesRead
0x180021e50  mov     rcx, [rdi+10h]; hRequest
0x180021e54  mov     rdx, rax; lpBuffer
0x180021e57  call    cs:__imp_WinHttpReadData
0x180021e5d  test    eax, eax
0x180021e5f  jnz     short loc_180021E78
0x180021e61  call    cs:__imp_GetLastError
0x180021e67  mov     ebx, eax
0x180021e69  test    eax, eax
0x180021e6b  jle     short loc_180021E8C
0x180021e6d  movzx   ebx, ax
0x180021e70  or      ebx, 80070000h
0x180021e76  jmp     short loc_180021E8C
0x180021e78  mov     eax, [rbp+dwBufferLength]
0x180021e7b  mov     rdx, rsi; char *
0x180021e7e  mov     rcx, rdi; this
0x180021e81  mov     [rax+rsi], r15b
0x180021e85  call    ?ParseJsonResult@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAD@Z; OneCore::Base::Telemetry::OneSettingsQuery::ParseJsonResult(char *)
0x180021e8a  mov     ebx, eax
0x180021e8c  call    cs:__imp_GetProcessHeap
0x180021e92  mov     r8, rsi; lpMem
0x180021e95  xor     edx, edx; dwFlags
0x180021e97  mov     rcx, rax; hHeap
0x180021e9a  call    cs:__imp_HeapFree
0x180021ea0  jmp     short loc_180021EEA
0x180021ea2  cmp     eax, 130h
0x180021ea7  jnz     short loc_180021EB0
0x180021ea9  mov     ebx, 1
0x180021eae  jmp     short loc_180021EEA
0x180021eb0  cmp     eax, 197h
0x180021eb5  jnz     short loc_180021EE5
0x180021eb7  mov     rcx, [rdi+10h]; hRequest
0x180021ebb  lea     r9, [rbp+pdwAuthTarget]; pdwAuthTarget
0x180021ebf  lea     r8, [rbp+dwFirstScheme]; lpdwFirstScheme
0x180021ec3  lea     rdx, [rbp+dwSupportedSchemes]; lpdwSupportedSchemes
0x180021ec7  call    cs:__imp_WinHttpQueryAuthSchemes
0x180021ecd  mov     eax, [rbp+dwSupportedSchemes]
0x180021ed0  mov     ebx, 1
0x180021ed5  and     eax, ebx
0x180021ed7  test    al, al
0x180021ed9  jz      short loc_180021EE5
0x180021edb  cmp     [rbp+pdwAuthTarget], ebx
0x180021ede  mov     ebx, 80070005h
0x180021ee3  jz      short loc_180021EEA
0x180021ee5  mov     ebx, 80004005h
0x180021eea  cmp     [rbp+lpszHeaders], r15
0x180021eee  jz      short loc_180021F05
0x180021ef0  call    cs:__imp_GetProcessHeap
0x180021ef6  mov     r8, [rbp+lpszHeaders]; lpMem
0x180021efa  xor     edx, edx; dwFlags
0x180021efc  mov     rcx, rax; hHeap
0x180021eff  call    cs:__imp_HeapFree
0x180021f05  mov     eax, ebx
0x180021f07  add     rsp, 50h
0x180021f0b  pop     r15
0x180021f0d  pop     rdi
0x180021f0e  pop     rsi
0x180021f0f  pop     rbx
0x180021f10  pop     rbp
0x180021f11  retn
```
