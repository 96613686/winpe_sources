# MdmHttpRequest::ReadDataGreaterThan1KB(ulong,uchar *)

- ea: `0x18001b6c0`
- end: `0x18001b8d9`
- name: `?ReadDataGreaterThan1KB@MdmHttpRequest@@AEAAJKPEAE@Z`
- size: `537`
- prototype: `int(MdmHttpRequest *__hidden this, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001b4d8`

## callees

- `0x180001544`
- `0x1800015b8`
- `0x180001f6a`
- `0x180001fd4`
- `0x1800065c0`
- `0x18001b6c0`
- `0x18001dbf0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001b7fb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001b80f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001b7fb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001b80f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b87e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b87e`
- `WINHTTP!WinHttpReadData` at `0x18001b76b`
- `WINHTTP!WinHttpReadData` at `0x18001b76b`

## string_xrefs

- `0x18001b704`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001b8b9`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001b8a2`: `CBR(::WinHttpReadData( m_hRequest, pstrBuffer, c_cbBufferSize, &cbWinHttpRead))`
- `0x18001b864`: `CBR(cbRemainingBufferSize >= cbWinHttpRead)`
- `0x18001b83c`: `CBR(0 == memcpy_s(pbIndexPtr, cbRemainingBufferSize, pstrBuffer, cbWinHttpRead))`

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
  unsigned __int64 v10; // rdx
  DWORD v11; // ecx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  int v15; // ecx
  signed int LastError; // eax
  char v18; // [rsp+20h] [rbp-38h]
  const char *v19; // [rsp+28h] [rbp-30h]
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
                v15,
                v10,
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
          v19 = "CBR(cbRemainingBufferSize == 0)";
          v18 = -35;
          goto LABEL_32;
        }
      }
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        v19 = "CBR(::WinHttpReadData( m_hRequest, pstrBuffer, c_cbBufferSize, &cbWinHttpRead))";
        v18 = -55;
LABEL_32:
        McTemplateU0dsqs_EventWriteTransfer(
          v11,
          v10,
          v6,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
          v18,
          v19);
      }
LABEL_33:
      operator delete(v9, v10);
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
0x18001b6c0  push    rbx
0x18001b6c2  push    rbp
0x18001b6c3  push    rsi
0x18001b6c4  push    rdi
0x18001b6c5  sub     rsp, 38h
0x18001b6c9  mov     [rsp+58h+dwNumberOfBytesRead], 0
0x18001b6d1  mov     rdi, r8
0x18001b6d4  mov     ebx, edx
0x18001b6d6  mov     rbp, rcx
0x18001b6d9  test    r8, r8
0x18001b6dc  jnz     short loc_18001B718
0x18001b6de  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b6e5  mov     ebx, 80004003h
0x18001b6ea  jz      loc_18001B8CD
0x18001b6f0  lea     rax, aCbrPbbufferNul; "CBR(pbBuffer != nullptr)"
0x18001b6f7  mov     [rsp+58h+var_30], rax
0x18001b6fc  mov     dword ptr [rsp+58h+var_38], 2BCh
0x18001b704  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001b70b  mov     r8d, ebx
0x18001b70e  call    McTemplateU0dsqs_EventWriteTransfer
0x18001b713  jmp     loc_18001B8CD
0x18001b718  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001b71f  mov     ecx, 2000h; unsigned __int64
0x18001b724  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001b729  mov     rsi, rax
0x18001b72c  test    rax, rax
0x18001b72f  jnz     short loc_18001B759
0x18001b731  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b738  mov     ebx, 8007000Eh
0x18001b73d  jz      loc_18001B8CD
0x18001b743  lea     rax, aCbrPstrbufferN; "CBR(pstrBuffer != nullptr)"
0x18001b74a  mov     [rsp+58h+var_30], rax
0x18001b74f  mov     dword ptr [rsp+58h+var_38], 2BFh
0x18001b757  jmp     short loc_18001B704
0x18001b759  mov     rcx, [rbp+20h]; hRequest
0x18001b75d  lea     r9, [rsp+58h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x18001b762  mov     r8d, 2000h; dwNumberOfBytesToRead
0x18001b768  mov     rdx, rsi; lpBuffer
0x18001b76b  call    cs:__imp_WinHttpReadData
0x18001b772  nop     dword ptr [rax+rax+00h]
0x18001b777  test    eax, eax
0x18001b779  jz      loc_18001B87E
0x18001b77f  mov     ecx, [rsp+58h+dwNumberOfBytesRead]
0x18001b783  test    ecx, ecx
0x18001b785  jz      short loc_18001B7BE
0x18001b787  cmp     ebx, ecx
0x18001b789  jb      loc_18001B852
0x18001b78f  mov     r8d, ecx; Size
0x18001b792  test    ecx, ecx
0x18001b794  jz      short loc_18001B7B1
0x18001b796  test    rdi, rdi
0x18001b799  jz      short loc_18001B80F
0x18001b79b  mov     eax, ebx
0x18001b79d  mov     rcx, rdi; void *
0x18001b7a0  cmp     rax, r8
0x18001b7a3  jb      short loc_18001B7F1
0x18001b7a5  mov     rdx, rsi; Src
0x18001b7a8  call    memcpy_0
0x18001b7ad  mov     ecx, [rsp+58h+dwNumberOfBytesRead]
0x18001b7b1  sub     ebx, ecx
0x18001b7b3  jz      short loc_18001B7BA
0x18001b7b5  mov     eax, ecx
0x18001b7b7  add     rdi, rax
0x18001b7ba  test    ecx, ecx
0x18001b7bc  jnz     short loc_18001B759
0x18001b7be  test    ebx, ebx
0x18001b7c0  jz      loc_18001B87A
0x18001b7c6  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b7cd  mov     ebx, 8007000Dh
0x18001b7d2  jz      loc_18001B8C5
0x18001b7d8  lea     rax, aCbrCbremaining; "CBR(cbRemainingBufferSize == 0)"
0x18001b7df  mov     [rsp+58h+var_30], rax
0x18001b7e4  mov     dword ptr [rsp+58h+var_38], 2DDh
0x18001b7ec  jmp     loc_18001B8B6
0x18001b7f1  mov     r8, rax; Size
0x18001b7f4  xor     edx, edx; Val
0x18001b7f6  call    memset_0
0x18001b7fb  call    cs:__imp__o__errno
0x18001b802  nop     dword ptr [rax+rax+00h]
0x18001b807  mov     dword ptr [rax], 22h ; '"'
0x18001b80d  jmp     short loc_18001B821
0x18001b80f  call    cs:__imp__o__errno
0x18001b816  nop     dword ptr [rax+rax+00h]
0x18001b81b  mov     dword ptr [rax], 16h
0x18001b821  call    _invalid_parameter_noinfo
0x18001b826  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b82d  mov     r8d, 80004005h
0x18001b833  mov     ebx, r8d
0x18001b836  jz      loc_18001B8C5
0x18001b83c  lea     rax, aCbr0MemcpySPbi; "CBR(0 == memcpy_s(pbIndexPtr, cbRemaini"...
0x18001b843  mov     [rsp+58h+var_30], rax
0x18001b848  mov     dword ptr [rsp+58h+var_38], 2CEh
0x18001b850  jmp     short loc_18001B8B9
0x18001b852  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b859  mov     r8d, 80004005h
0x18001b85f  mov     ebx, r8d
0x18001b862  jz      short loc_18001B8C5
0x18001b864  lea     rax, aCbrCbremaining_0; "CBR(cbRemainingBufferSize >= cbWinHttpR"...
0x18001b86b  mov     [rsp+58h+var_30], rax
0x18001b870  mov     dword ptr [rsp+58h+var_38], 2CDh
0x18001b878  jmp     short loc_18001B8B9
0x18001b87a  xor     ebx, ebx
0x18001b87c  jmp     short loc_18001B8C5
0x18001b87e  call    cs:__imp_GetLastError
0x18001b885  nop     dword ptr [rax+rax+00h]
0x18001b88a  mov     ebx, eax
0x18001b88c  test    eax, eax
0x18001b88e  jle     short loc_18001B899
0x18001b890  movzx   ebx, ax
0x18001b893  or      ebx, 80070000h
0x18001b899  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b8a0  jz      short loc_18001B8C5
0x18001b8a2  lea     rax, aCbrWinhttpread_0; "CBR(::WinHttpReadData( m_hRequest, pstr"...
0x18001b8a9  mov     [rsp+58h+var_30], rax
0x18001b8ae  mov     dword ptr [rsp+58h+var_38], 2C9h
0x18001b8b6  mov     r8d, ebx
0x18001b8b9  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001b8c0  call    McTemplateU0dsqs_EventWriteTransfer
0x18001b8c5  mov     rcx, rsi; void *
0x18001b8c8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b8cd  mov     eax, ebx
0x18001b8cf  add     rsp, 38h
0x18001b8d3  pop     rdi
0x18001b8d4  pop     rsi
0x18001b8d5  pop     rbp
0x18001b8d6  pop     rbx
0x18001b8d7  retn
```
