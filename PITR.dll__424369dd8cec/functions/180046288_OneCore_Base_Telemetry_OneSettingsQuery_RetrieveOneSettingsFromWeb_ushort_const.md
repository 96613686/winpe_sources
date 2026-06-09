# OneCore::Base::Telemetry::OneSettingsQuery::RetrieveOneSettingsFromWeb(ushort const *)

- ea: `0x180046288`
- end: `0x1800464f2`
- name: `?RetrieveOneSettingsFromWeb@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBG@Z`
- size: `618`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180041594`

## callees

- `0x1800411a4`
- `0x1800444a0`
- `0x180046288`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004639c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046409`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004646c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800464d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004639c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046409`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004646c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800464d0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800463ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004641a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800463ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004641a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004647a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800464df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004647a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800464df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800462f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004638a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046441`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800462f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004638a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046441`
- `WINHTTP!WinHttpReadData` at `0x180046437`
- `WINHTTP!WinHttpReadData` at `0x180046437`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800463f6`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800463f6`
- `WINHTTP!WinHttpQueryHeaders` at `0x180046346`
- `WINHTTP!WinHttpQueryHeaders` at `0x180046380`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800463e0`
- `WINHTTP!WinHttpQueryHeaders` at `0x180046346`
- `WINHTTP!WinHttpQueryHeaders` at `0x180046380`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800463e0`
- `WINHTTP!WinHttpReceiveResponse` at `0x180046317`
- `WINHTTP!WinHttpReceiveResponse` at `0x180046317`
- `WINHTTP!WinHttpSendRequest` at `0x1800462e9`
- `WINHTTP!WinHttpSendRequest` at `0x1800462e9`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x1800464a7`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x1800464a7`

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
0x180046288  mov     qword ptr [rsp-28h+dwBufferLength], rdx
0x18004628d  push    rbp
0x18004628e  push    rbx
0x18004628f  push    rsi
0x180046290  push    rdi
0x180046291  push    r15
0x180046293  mov     rbp, rsp
0x180046296  sub     rsp, 50h
0x18004629a  xor     r15d, r15d
0x18004629d  lea     r8, [rbp+lpszHeaders]; unsigned __int16 **
0x1800462a1  mov     [rbp+lpszHeaders], r15
0x1800462a5  mov     rdi, rcx
0x1800462a8  mov     [rbp+Buffer], r15d
0x1800462ac  mov     [rbp+dwBufferLength], r15d
0x1800462b0  mov     [rbp+dwSupportedSchemes], r15d
0x1800462b4  mov     [rbp+dwFirstScheme], r15d
0x1800462b8  mov     [rbp+pdwAuthTarget], r15d
0x1800462bc  call    ?CreateHeaders@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBGPEAPEAG@Z; OneCore::Base::Telemetry::OneSettingsQuery::CreateHeaders(ushort const *,ushort * *)
0x1800462c1  mov     ebx, eax
0x1800462c3  test    eax, eax
0x1800462c5  js      loc_1800464CA
0x1800462cb  mov     rdx, [rbp+lpszHeaders]; lpszHeaders
0x1800462cf  xor     r9d, r9d; lpOptional
0x1800462d2  mov     rcx, [rdi+10h]; hRequest
0x1800462d6  or      r8d, 0FFFFFFFFh; dwHeadersLength
0x1800462da  mov     [rsp+50h+dwContext], r15; dwContext
0x1800462df  mov     [rsp+50h+dwTotalLength], r15d; dwTotalLength
0x1800462e4  mov     [rsp+50h+dwOptionalLength], r15d; dwOptionalLength
0x1800462e9  call    cs:__imp_WinHttpSendRequest
0x1800462ef  test    eax, eax
0x1800462f1  jnz     short loc_180046311
0x1800462f3  call    cs:__imp_GetLastError
0x1800462f9  mov     ebx, eax
0x1800462fb  test    eax, eax
0x1800462fd  jle     loc_1800464CA
0x180046303  movzx   ebx, ax
0x180046306  or      ebx, 80070000h
0x18004630c  jmp     loc_1800464CA
0x180046311  mov     rcx, [rdi+10h]; hRequest
0x180046315  xor     edx, edx; lpReserved
0x180046317  call    cs:__imp_WinHttpReceiveResponse
0x18004631d  test    eax, eax
0x18004631f  jz      short loc_1800462F3
0x180046321  mov     rcx, [rdi+10h]; hRequest
0x180046325  lea     rax, [rbp+dwBufferLength]
0x180046329  mov     qword ptr [rsp+50h+dwTotalLength], r15; lpdwIndex
0x18004632e  lea     r9, [rbp+Buffer]; lpBuffer
0x180046332  xor     r8d, r8d; pwszName
0x180046335  mov     qword ptr [rsp+50h+dwOptionalLength], rax; lpdwBufferLength
0x18004633a  mov     edx, 20000013h; dwInfoLevel
0x18004633f  mov     [rbp+dwBufferLength], 4
0x180046346  call    cs:__imp_WinHttpQueryHeaders
0x18004634c  test    eax, eax
0x18004634e  jz      short loc_1800462F3
0x180046350  mov     eax, [rbp+Buffer]
0x180046353  cmp     eax, 0C8h
0x180046358  jnz     loc_180046482
0x18004635e  mov     rcx, [rdi+10h]; hRequest
0x180046362  lea     rax, [rbp+dwBufferLength]
0x180046366  xor     r9d, r9d; lpBuffer
0x180046369  mov     qword ptr [rsp+50h+dwTotalLength], r15; lpdwIndex
0x18004636e  xor     r8d, r8d; pwszName
0x180046371  mov     [rbp+dwBufferLength], r15d
0x180046375  mov     qword ptr [rsp+50h+dwOptionalLength], rax; lpdwBufferLength
0x18004637a  lea     esi, [r9+36h]
0x18004637e  mov     edx, esi; dwInfoLevel
0x180046380  call    cs:__imp_WinHttpQueryHeaders
0x180046386  test    eax, eax
0x180046388  jnz     short loc_180046399
0x18004638a  call    cs:__imp_GetLastError
0x180046390  cmp     eax, 7Ah ; 'z'
0x180046393  jnz     loc_1800462F3
0x180046399  mov     ebx, [rbp+dwBufferLength]
0x18004639c  call    cs:__imp_GetProcessHeap
0x1800463a2  mov     r8d, ebx; dwBytes
0x1800463a5  mov     edx, 8; dwFlags
0x1800463aa  mov     rcx, rax; hHeap
0x1800463ad  call    cs:__imp_HeapAlloc
0x1800463b3  mov     [rdi+20h], rax
0x1800463b7  test    rax, rax
0x1800463ba  jnz     short loc_1800463C6
0x1800463bc  mov     ebx, 8007000Eh
0x1800463c1  jmp     loc_1800464CA
0x1800463c6  lea     rcx, [rbp+dwBufferLength]
0x1800463ca  mov     qword ptr [rsp+50h+dwTotalLength], r15; lpdwIndex
0x1800463cf  mov     qword ptr [rsp+50h+dwOptionalLength], rcx; lpdwBufferLength
0x1800463d4  mov     r9, rax; lpBuffer
0x1800463d7  mov     rcx, [rdi+10h]; hRequest
0x1800463db  xor     r8d, r8d; pwszName
0x1800463de  mov     edx, esi; dwInfoLevel
0x1800463e0  call    cs:__imp_WinHttpQueryHeaders
0x1800463e6  test    eax, eax
0x1800463e8  jz      loc_1800462F3
0x1800463ee  mov     rcx, [rdi+10h]; hRequest
0x1800463f2  lea     rdx, [rbp+dwBufferLength]; lpdwNumberOfBytesAvailable
0x1800463f6  call    cs:__imp_WinHttpQueryDataAvailable
0x1800463fc  test    eax, eax
0x1800463fe  jz      loc_1800462F3
0x180046404  mov     ebx, [rbp+dwBufferLength]
0x180046407  inc     ebx
0x180046409  call    cs:__imp_GetProcessHeap
0x18004640f  mov     r8d, ebx; dwBytes
0x180046412  mov     edx, 8; dwFlags
0x180046417  mov     rcx, rax; hHeap
0x18004641a  call    cs:__imp_HeapAlloc
0x180046420  mov     rsi, rax
0x180046423  test    rax, rax
0x180046426  jz      short loc_1800463BC
0x180046428  mov     r8d, [rbp+dwBufferLength]; dwNumberOfBytesToRead
0x18004642c  lea     r9, [rbp+dwBufferLength]; lpdwNumberOfBytesRead
0x180046430  mov     rcx, [rdi+10h]; hRequest
0x180046434  mov     rdx, rax; lpBuffer
0x180046437  call    cs:__imp_WinHttpReadData
0x18004643d  test    eax, eax
0x18004643f  jnz     short loc_180046458
0x180046441  call    cs:__imp_GetLastError
0x180046447  mov     ebx, eax
0x180046449  test    eax, eax
0x18004644b  jle     short loc_18004646C
0x18004644d  movzx   ebx, ax
0x180046450  or      ebx, 80070000h
0x180046456  jmp     short loc_18004646C
0x180046458  mov     eax, [rbp+dwBufferLength]
0x18004645b  mov     rdx, rsi; char *
0x18004645e  mov     rcx, rdi; this
0x180046461  mov     [rax+rsi], r15b
0x180046465  call    ?ParseJsonResult@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAD@Z; OneCore::Base::Telemetry::OneSettingsQuery::ParseJsonResult(char *)
0x18004646a  mov     ebx, eax
0x18004646c  call    cs:__imp_GetProcessHeap
0x180046472  mov     r8, rsi; lpMem
0x180046475  xor     edx, edx; dwFlags
0x180046477  mov     rcx, rax; hHeap
0x18004647a  call    cs:__imp_HeapFree
0x180046480  jmp     short loc_1800464CA
0x180046482  cmp     eax, 130h
0x180046487  jnz     short loc_180046490
0x180046489  mov     ebx, 1
0x18004648e  jmp     short loc_1800464CA
0x180046490  cmp     eax, 197h
0x180046495  jnz     short loc_1800464C5
0x180046497  mov     rcx, [rdi+10h]; hRequest
0x18004649b  lea     r9, [rbp+pdwAuthTarget]; pdwAuthTarget
0x18004649f  lea     r8, [rbp+dwFirstScheme]; lpdwFirstScheme
0x1800464a3  lea     rdx, [rbp+dwSupportedSchemes]; lpdwSupportedSchemes
0x1800464a7  call    cs:__imp_WinHttpQueryAuthSchemes
0x1800464ad  mov     eax, [rbp+dwSupportedSchemes]
0x1800464b0  mov     ebx, 1
0x1800464b5  and     eax, ebx
0x1800464b7  test    al, al
0x1800464b9  jz      short loc_1800464C5
0x1800464bb  cmp     [rbp+pdwAuthTarget], ebx
0x1800464be  mov     ebx, 80070005h
0x1800464c3  jz      short loc_1800464CA
0x1800464c5  mov     ebx, 80004005h
0x1800464ca  cmp     [rbp+lpszHeaders], r15
0x1800464ce  jz      short loc_1800464E5
0x1800464d0  call    cs:__imp_GetProcessHeap
0x1800464d6  mov     r8, [rbp+lpszHeaders]; lpMem
0x1800464da  xor     edx, edx; dwFlags
0x1800464dc  mov     rcx, rax; hHeap
0x1800464df  call    cs:__imp_HeapFree
0x1800464e5  mov     eax, ebx
0x1800464e7  add     rsp, 50h
0x1800464eb  pop     r15
0x1800464ed  pop     rdi
0x1800464ee  pop     rsi
0x1800464ef  pop     rbx
0x1800464f0  pop     rbp
0x1800464f1  retn
```
