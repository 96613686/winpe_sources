# MdmHttpRequest::ReadDataGreaterThan1KB(ulong,uchar *)

- ea: `0x18001b13c`
- end: `0x18001b33c`
- name: `?ReadDataGreaterThan1KB@MdmHttpRequest@@AEAAJKPEAE@Z`
- size: `512`
- prototype: `__int64 __fastcall(HINTERNET *this, DWORD, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001af58`

## callees

- `0x180001544`
- `0x1800015b8`
- `0x180001f6a`
- `0x180001fd4`
- `0x180006548`
- `0x18001b13c`
- `0x18001d510`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001b271`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001b27f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001b271`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001b27f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b2e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b2e8`
- `WINHTTP!WinHttpReadData` at `0x18001b1e7`
- `WINHTTP!WinHttpReadData` at `0x18001b1e7`

## string_xrefs

- `0x18001b180`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001b31d`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001b306`: `CBR(::WinHttpReadData( m_hRequest, pstrBuffer, c_cbBufferSize, &cbWinHttpRead))`
- `0x18001b2ce`: `CBR(cbRemainingBufferSize >= cbWinHttpRead)`
- `0x18001b2a6`: `CBR(0 == memcpy_s(pbIndexPtr, cbRemainingBufferSize, pstrBuffer, cbWinHttpRead))`

## pseudocode

```c
__int64 __fastcall MdmHttpRequest::ReadDataGreaterThan1KB(HINTERNET *this, DWORD a2, unsigned __int8 *a3)
{
  unsigned __int8 *v3; // rdi
  DWORD v4; // ebx
  unsigned int v6; // ebx
  int v7; // edx
  int v8; // ecx
  void *v9; // rsi
  __int64 v10; // rdx
  DWORD v11; // ecx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  int v15; // edx
  int v16; // ecx
  signed int LastError; // eax
  char v19; // [rsp+20h] [rbp-38h]
  const char *v20; // [rsp+28h] [rbp-30h]
  DWORD dwNumberOfBytesRead; // [rsp+68h] [rbp+10h] BYREF

  dwNumberOfBytesRead = 0;
  v3 = a3;
  v4 = a2;
  if ( a3 )
  {
    v9 = operator new[](0x2000u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v9 )
    {
      while ( WinHttpReadData(this[4], v9, 0x2000u, &dwNumberOfBytesRead) )
      {
        v11 = dwNumberOfBytesRead;
        if ( !dwNumberOfBytesRead )
          goto LABEL_18;
        if ( v4 < dwNumberOfBytesRead )
        {
          v6 = -2147467259;
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              dwNumberOfBytesRead,
              v10,
              -2147467259,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
              205,
              "CBR(cbRemainingBufferSize >= cbWinHttpRead)");
          goto LABEL_33;
        }
        if ( dwNumberOfBytesRead )
        {
          if ( !v3 )
          {
            *(_DWORD *)_o__errno(dwNumberOfBytesRead, v10, dwNumberOfBytesRead) = 22;
LABEL_23:
            invalid_parameter_noinfo();
            v6 = -2147467259;
            if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
              McTemplateU0dsqs_EventWriteTransfer(
                v16,
                v15,
                -2147467259,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
                206,
                "CBR(0 == memcpy_s(pbIndexPtr, cbRemainingBufferSize, pstrBuffer, cbWinHttpRead))");
            goto LABEL_33;
          }
          if ( v4 < (unsigned __int64)dwNumberOfBytesRead )
          {
            memset_0(v3, 0, v4);
            *(_DWORD *)_o__errno(v13, v12, v14) = 34;
            goto LABEL_23;
          }
          memcpy_0(v3, v9, dwNumberOfBytesRead);
          v11 = dwNumberOfBytesRead;
        }
        v4 -= v11;
        if ( v4 )
          v3 += v11;
        if ( !v11 )
        {
LABEL_18:
          if ( !v4 )
          {
            v6 = 0;
            goto LABEL_33;
          }
          v6 = -2147024883;
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
            goto LABEL_33;
          v20 = "CBR(cbRemainingBufferSize == 0)";
          v19 = -35;
          goto LABEL_32;
        }
      }
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        v20 = "CBR(::WinHttpReadData( m_hRequest, pstrBuffer, c_cbBufferSize, &cbWinHttpRead))";
        v19 = -55;
LABEL_32:
        McTemplateU0dsqs_EventWriteTransfer(
          v11,
          v10,
          v6,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
          v19,
          v20);
      }
LABEL_33:
      operator delete(v9);
    }
    else
    {
      v6 = -2147024882;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v8,
          v7,
          -2147024882,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
          191,
          "CBR(pstrBuffer != nullptr)");
    }
  }
  else
  {
    v6 = -2147467261;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)this,
        a2,
        -2147467261,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
        188,
        "CBR(pbBuffer != nullptr)");
  }
  return v6;
}

```

## disassembly

```asm
0x18001b13c  push    rbx
0x18001b13e  push    rbp
0x18001b13f  push    rsi
0x18001b140  push    rdi
0x18001b141  sub     rsp, 38h
0x18001b145  mov     [rsp+58h+dwNumberOfBytesRead], 0
0x18001b14d  mov     rdi, r8
0x18001b150  mov     ebx, edx
0x18001b152  mov     rbp, rcx
0x18001b155  test    r8, r8
0x18001b158  jnz     short loc_18001B194
0x18001b15a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b161  mov     ebx, 80004003h
0x18001b166  jz      loc_18001B331
0x18001b16c  lea     rax, aCbrPbbufferNul; "CBR(pbBuffer != nullptr)"
0x18001b173  mov     [rsp+58h+var_30], rax
0x18001b178  mov     dword ptr [rsp+58h+var_38], 2BCh
0x18001b180  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001b187  mov     r8d, ebx
0x18001b18a  call    McTemplateU0dsqs_EventWriteTransfer
0x18001b18f  jmp     loc_18001B331
0x18001b194  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001b19b  mov     ecx, 2000h; unsigned __int64
0x18001b1a0  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001b1a5  mov     rsi, rax
0x18001b1a8  test    rax, rax
0x18001b1ab  jnz     short loc_18001B1D5
0x18001b1ad  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b1b4  mov     ebx, 8007000Eh
0x18001b1b9  jz      loc_18001B331
0x18001b1bf  lea     rax, aCbrPstrbufferN; "CBR(pstrBuffer != nullptr)"
0x18001b1c6  mov     [rsp+58h+var_30], rax
0x18001b1cb  mov     dword ptr [rsp+58h+var_38], 2BFh
0x18001b1d3  jmp     short loc_18001B180
0x18001b1d5  mov     rcx, [rbp+20h]; hRequest
0x18001b1d9  lea     r9, [rsp+58h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x18001b1de  mov     r8d, 2000h; dwNumberOfBytesToRead
0x18001b1e4  mov     rdx, rsi; lpBuffer
0x18001b1e7  call    cs:__imp_WinHttpReadData
0x18001b1ed  test    eax, eax
0x18001b1ef  jz      loc_18001B2E8
0x18001b1f5  mov     ecx, [rsp+58h+dwNumberOfBytesRead]
0x18001b1f9  test    ecx, ecx
0x18001b1fb  jz      short loc_18001B234
0x18001b1fd  cmp     ebx, ecx
0x18001b1ff  jb      loc_18001B2BC
0x18001b205  mov     r8d, ecx; Size
0x18001b208  test    ecx, ecx
0x18001b20a  jz      short loc_18001B227
0x18001b20c  test    rdi, rdi
0x18001b20f  jz      short loc_18001B27F
0x18001b211  mov     eax, ebx
0x18001b213  mov     rcx, rdi; void *
0x18001b216  cmp     rax, r8
0x18001b219  jb      short loc_18001B267
0x18001b21b  mov     rdx, rsi; Src
0x18001b21e  call    memcpy_0
0x18001b223  mov     ecx, [rsp+58h+dwNumberOfBytesRead]
0x18001b227  sub     ebx, ecx
0x18001b229  jz      short loc_18001B230
0x18001b22b  mov     eax, ecx
0x18001b22d  add     rdi, rax
0x18001b230  test    ecx, ecx
0x18001b232  jnz     short loc_18001B1D5
0x18001b234  test    ebx, ebx
0x18001b236  jz      loc_18001B2E4
0x18001b23c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b243  mov     ebx, 8007000Dh
0x18001b248  jz      loc_18001B329
0x18001b24e  lea     rax, aCbrCbremaining; "CBR(cbRemainingBufferSize == 0)"
0x18001b255  mov     [rsp+58h+var_30], rax
0x18001b25a  mov     dword ptr [rsp+58h+var_38], 2DDh
0x18001b262  jmp     loc_18001B31A
0x18001b267  mov     r8, rax; Size
0x18001b26a  xor     edx, edx; Val
0x18001b26c  call    memset_0
0x18001b271  call    cs:__imp__o__errno
0x18001b277  mov     dword ptr [rax], 22h ; '"'
0x18001b27d  jmp     short loc_18001B28B
0x18001b27f  call    cs:__imp__o__errno
0x18001b285  mov     dword ptr [rax], 16h
0x18001b28b  call    _invalid_parameter_noinfo
0x18001b290  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b297  mov     r8d, 80004005h
0x18001b29d  mov     ebx, r8d
0x18001b2a0  jz      loc_18001B329
0x18001b2a6  lea     rax, aCbr0MemcpySPbi; "CBR(0 == memcpy_s(pbIndexPtr, cbRemaini"...
0x18001b2ad  mov     [rsp+58h+var_30], rax
0x18001b2b2  mov     dword ptr [rsp+58h+var_38], 2CEh
0x18001b2ba  jmp     short loc_18001B31D
0x18001b2bc  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b2c3  mov     r8d, 80004005h
0x18001b2c9  mov     ebx, r8d
0x18001b2cc  jz      short loc_18001B329
0x18001b2ce  lea     rax, aCbrCbremaining_0; "CBR(cbRemainingBufferSize >= cbWinHttpR"...
0x18001b2d5  mov     [rsp+58h+var_30], rax
0x18001b2da  mov     dword ptr [rsp+58h+var_38], 2CDh
0x18001b2e2  jmp     short loc_18001B31D
0x18001b2e4  xor     ebx, ebx
0x18001b2e6  jmp     short loc_18001B329
0x18001b2e8  call    cs:__imp_GetLastError
0x18001b2ee  mov     ebx, eax
0x18001b2f0  test    eax, eax
0x18001b2f2  jle     short loc_18001B2FD
0x18001b2f4  movzx   ebx, ax
0x18001b2f7  or      ebx, 80070000h
0x18001b2fd  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b304  jz      short loc_18001B329
0x18001b306  lea     rax, aCbrWinhttpread_0; "CBR(::WinHttpReadData( m_hRequest, pstr"...
0x18001b30d  mov     [rsp+58h+var_30], rax
0x18001b312  mov     dword ptr [rsp+58h+var_38], 2C9h
0x18001b31a  mov     r8d, ebx
0x18001b31d  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001b324  call    McTemplateU0dsqs_EventWriteTransfer
0x18001b329  mov     rcx, rsi; void *
0x18001b32c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b331  mov     eax, ebx
0x18001b333  add     rsp, 38h
0x18001b337  pop     rdi
0x18001b338  pop     rsi
0x18001b339  pop     rbp
0x18001b33a  pop     rbx
0x18001b33b  retn
```
