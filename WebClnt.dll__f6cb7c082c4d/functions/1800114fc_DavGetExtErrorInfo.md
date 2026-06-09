# DavGetExtErrorInfo

- ea: `0x1800114fc`
- end: `0x180011715`
- name: `DavGetExtErrorInfo`
- size: `537`
- prototype: `__int64 __fastcall(HINTERNET hRequest, _QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d9e4`
- `0x180013c08`
- `0x18001456c`
- `0x1800146fc`

## callees

- `0x18000b7dc`
- `0x1800114fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011548`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011603`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001165a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011548`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011603`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001165a`
- `DAVHLPR!DavUrlDecodeUtf8` at `0x1800116c6`
- `DAVHLPR!DavUrlDecodeUtf8` at `0x1800116c6`
- `KERNEL32!LocalFree` at `0x18001170a`
- `KERNEL32!LocalFree` at `0x18001170a`
- `KERNEL32!LocalAlloc` at `0x1800115f5`
- `KERNEL32!LocalAlloc` at `0x1800115f5`
- `WINHTTP!WinHttpQueryHeaders` at `0x180011538`
- `WINHTTP!WinHttpQueryHeaders` at `0x180011650`
- `WINHTTP!WinHttpQueryHeaders` at `0x180011538`
- `WINHTTP!WinHttpQueryHeaders` at `0x180011650`

## pseudocode

```c
__int64 __fastcall DavGetExtErrorInfo(HINTERNET hRequest, _QWORD *a2)
{
  HLOCAL v4; // rdi
  DWORD LastError; // ebx
  DWORD v7; // ecx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  unsigned __int64 v10; // rdx
  DWORD dwBufferLength; // [rsp+60h] [rbp+18h] BYREF
  unsigned __int64 v12; // [rsp+68h] [rbp+20h] BYREF

  dwBufferLength = 0;
  if ( WinHttpQueryHeaders(hRequest, 0xFFFFu, L"X-MSDAVEXT_Error", 0, &dwBufferLength, 0) )
  {
    v7 = dwBufferLength;
LABEL_16:
    v4 = LocalAlloc(0x40u, v7);
    if ( v4 )
    {
      if ( WinHttpQueryHeaders(hRequest, 0xFFFFu, L"X-MSDAVEXT_Error", v4, &dwBufferLength, 0) )
      {
        v10 = (unsigned __int64)(dwBufferLength + 2) >> 1;
        v12 = v10;
        dwBufferLength += 2;
        LastError = DavUrlDecodeUtf8(v4, v10, v4, &v12);
        if ( !LastError )
          goto LABEL_4;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 165, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, LastError);
        goto LABEL_32;
      }
      LastError = GetLastError();
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_25:
        if ( !LastError )
          goto LABEL_4;
        if ( !v4 )
          return LastError;
LABEL_32:
        LocalFree(v4);
        return LastError;
      }
      v9 = 164;
    }
    else
    {
      LastError = GetLastError();
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_25;
      v9 = 163;
    }
LABEL_24:
    WPP_SF_d(v8[2], v9, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, LastError);
    goto LABEL_25;
  }
  v4 = 0;
  LastError = GetLastError();
  if ( LastError == 12150 )
  {
    LastError = 0;
LABEL_4:
    *a2 = v4;
    return LastError;
  }
  if ( LastError != 122 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_25;
    v9 = 162;
    goto LABEL_24;
  }
  if ( dwBufferLength - 1 <= 0x7FD )
  {
    v7 = dwBufferLength + 2;
    dwBufferLength += 2;
    goto LABEL_16;
  }
  LastError = 58;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 161, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, dwBufferLength);
  return LastError;
}

```

## disassembly

```asm
0x1800114fc  mov     rax, rsp
0x1800114ff  mov     [rax+8], rbx
0x180011503  push    rsi
0x180011504  push    rdi
0x180011505  push    r14
0x180011507  sub     rsp, 30h
0x18001150b  mov     qword ptr [rax-20h], 0
0x180011513  mov     r14, rdx
0x180011516  mov     dword ptr [rax+18h], 0
0x18001151d  lea     rax, [rax+18h]
0x180011521  xor     r9d, r9d; lpBuffer
0x180011524  mov     [rsp+48h+lpdwBufferLength], rax; lpdwBufferLength
0x180011529  lea     r8, pwszName; "X-MSDAVEXT_Error"
0x180011530  mov     edx, 0FFFFh; dwInfoLevel
0x180011535  mov     rsi, rcx
0x180011538  call    cs:__imp_WinHttpQueryHeaders
0x18001153e  test    eax, eax
0x180011540  jnz     loc_1800115EA
0x180011546  xor     edi, edi
0x180011548  call    cs:__imp_GetLastError
0x18001154e  mov     ebx, eax
0x180011550  cmp     eax, 2F76h
0x180011555  jnz     short loc_18001156C
0x180011557  xor     ebx, ebx
0x180011559  mov     [r14], rdi
0x18001155c  mov     eax, ebx
0x18001155e  mov     rbx, [rsp+48h+arg_0]
0x180011563  add     rsp, 30h
0x180011567  pop     r14
0x180011569  pop     rdi
0x18001156a  pop     rsi
0x18001156b  retn
0x18001156c  cmp     ebx, 7Ah ; 'z'
0x18001156f  jnz     short loc_1800115BF
0x180011571  mov     ecx, [rsp+48h+dwBufferLength]
0x180011575  lea     eax, [rcx-1]
0x180011578  cmp     eax, 7FDh
0x18001157d  ja      short loc_180011588
0x18001157f  add     ecx, 2
0x180011582  mov     [rsp+48h+dwBufferLength], ecx
0x180011586  jmp     short loc_1800115EE
0x180011588  mov     ebx, 3Ah ; ':'
0x18001158d  mov     r10, cs:WPP_GLOBAL_Control
0x180011594  lea     rax, WPP_GLOBAL_Control
0x18001159b  cmp     r10, rax
0x18001159e  jz      short loc_18001155C
0x1800115a0  test    byte ptr [r10+1Ch], 1
0x1800115a5  jz      short loc_18001155C
0x1800115a7  mov     r9d, ecx
0x1800115aa  lea     edx, [rbx+67h]
0x1800115ad  mov     rcx, [r10+10h]
0x1800115b1  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x1800115b8  call    WPP_SF_d
0x1800115bd  jmp     short loc_18001155C
0x1800115bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800115c6  lea     rax, WPP_GLOBAL_Control
0x1800115cd  cmp     rcx, rax
0x1800115d0  jz      loc_180011693
0x1800115d6  test    byte ptr [rcx+1Ch], 1
0x1800115da  jz      loc_180011693
0x1800115e0  mov     edx, 0A2h
0x1800115e5  jmp     loc_180011680
0x1800115ea  mov     ecx, [rsp+48h+dwBufferLength]
0x1800115ee  mov     edx, ecx; uBytes
0x1800115f0  mov     ecx, 40h ; '@'; uFlags
0x1800115f5  call    cs:__imp_LocalAlloc
0x1800115fb  mov     rdi, rax
0x1800115fe  test    rax, rax
0x180011601  jnz     short loc_18001162B
0x180011603  call    cs:__imp_GetLastError
0x180011609  mov     ebx, eax
0x18001160b  mov     rcx, cs:WPP_GLOBAL_Control
0x180011612  lea     rax, WPP_GLOBAL_Control
0x180011619  cmp     rcx, rax
0x18001161c  jz      short loc_180011693
0x18001161e  test    byte ptr [rcx+1Ch], 1
0x180011622  jz      short loc_180011693
0x180011624  mov     edx, 0A3h
0x180011629  jmp     short loc_180011680
0x18001162b  lea     rax, [rsp+48h+dwBufferLength]
0x180011630  mov     [rsp+48h+lpdwIndex], 0; lpdwIndex
0x180011639  mov     r9, rdi; lpBuffer
0x18001163c  mov     [rsp+48h+lpdwBufferLength], rax; lpdwBufferLength
0x180011641  lea     r8, pwszName; "X-MSDAVEXT_Error"
0x180011648  mov     edx, 0FFFFh; dwInfoLevel
0x18001164d  mov     rcx, rsi; hRequest
0x180011650  call    cs:__imp_WinHttpQueryHeaders
0x180011656  test    eax, eax
0x180011658  jnz     short loc_1800116A6
0x18001165a  call    cs:__imp_GetLastError
0x180011660  mov     ebx, eax
0x180011662  mov     rcx, cs:WPP_GLOBAL_Control
0x180011669  lea     rax, WPP_GLOBAL_Control
0x180011670  cmp     rcx, rax
0x180011673  jz      short loc_180011693
0x180011675  test    byte ptr [rcx+1Ch], 1
0x180011679  jz      short loc_180011693
0x18001167b  mov     edx, 0A4h
0x180011680  mov     rcx, [rcx+10h]
0x180011684  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x18001168b  mov     r9d, ebx
0x18001168e  call    WPP_SF_d
0x180011693  test    ebx, ebx
0x180011695  jz      loc_180011559
0x18001169b  test    rdi, rdi
0x18001169e  jz      loc_18001155C
0x1800116a4  jmp     short loc_180011707
0x1800116a6  mov     eax, [rsp+48h+dwBufferLength]
0x1800116aa  lea     r9, [rsp+48h+arg_18]
0x1800116af  add     eax, 2
0x1800116b2  mov     r8, rdi
0x1800116b5  mov     edx, eax
0x1800116b7  mov     rcx, rdi
0x1800116ba  shr     rdx, 1
0x1800116bd  mov     [rsp+48h+arg_18], rdx
0x1800116c2  mov     [rsp+48h+dwBufferLength], eax
0x1800116c6  call    cs:__imp_DavUrlDecodeUtf8
0x1800116cc  mov     ebx, eax
0x1800116ce  test    eax, eax
0x1800116d0  jz      loc_180011559
0x1800116d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800116dd  lea     rax, WPP_GLOBAL_Control
0x1800116e4  cmp     rcx, rax
0x1800116e7  jz      short loc_180011707
0x1800116e9  test    byte ptr [rcx+1Ch], 1
0x1800116ed  jz      short loc_180011707
0x1800116ef  mov     rcx, [rcx+10h]
0x1800116f3  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x1800116fa  mov     edx, 0A5h
0x1800116ff  mov     r9d, ebx
0x180011702  call    WPP_SF_d
0x180011707  mov     rcx, rdi; hMem
0x18001170a  call    cs:__imp_LocalFree
0x180011710  jmp     loc_18001155C
```
