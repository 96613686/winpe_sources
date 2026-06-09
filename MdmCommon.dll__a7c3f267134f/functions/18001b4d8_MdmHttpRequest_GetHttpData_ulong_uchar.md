# MdmHttpRequest::GetHttpData(ulong,uchar *)

- ea: `0x18001b4d8`
- end: `0x18001b649`
- name: `?GetHttpData@MdmHttpRequest@@AEAAJKPEAE@Z`
- size: `369`
- prototype: `int(MdmHttpRequest *__hidden this, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001be50`

## callees

- `0x1800065c0`
- `0x18001b4d8`
- `0x18001b6c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b58c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b58c`
- `WINHTTP!WinHttpReadData` at `0x18001b57c`
- `WINHTTP!WinHttpReadData` at `0x18001b57c`

## string_xrefs

- `0x18001b522`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001b5bf`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001b605`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001b50b`: `CHR(ReadDataGreaterThan1KB( cbBuffer, pbBuffer))`
- `0x18001b61d`: `CHR(ReadData( cbBuffer, pbBuffer))`
- `0x18001b5b0`: `CBR(::WinHttpReadData( m_hRequest, pbBuffer, cbBuffer, &cbWinHttpRead))`
- `0x18001b5f1`: `CBR(cbBuffer == cbWinHttpRead)`

## pseudocode

```c
__int64 __fastcall MdmHttpRequest::GetHttpData(HINTERNET *this, unsigned int a2, unsigned __int8 *a3)
{
  int v4; // edx
  int v5; // ecx
  signed int DataGreaterThan1KB; // ebx
  int v7; // edi
  int v8; // edx
  int v9; // ecx
  int v10; // edx
  int v11; // ecx
  signed int LastError; // eax
  DWORD dwNumberOfBytesRead; // [rsp+48h] [rbp+10h] BYREF

  if ( a2 > 0x400 )
  {
    DataGreaterThan1KB = MdmHttpRequest::ReadDataGreaterThan1KB((MdmHttpRequest *)this, a2, a3);
    if ( DataGreaterThan1KB < 0 && (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v5,
        v4,
        DataGreaterThan1KB,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
        47,
        "CHR(ReadDataGreaterThan1KB( cbBuffer, pbBuffer))");
    return (unsigned int)DataGreaterThan1KB;
  }
  dwNumberOfBytesRead = 0;
  if ( !a3 )
  {
    DataGreaterThan1KB = -2147467261;
    v7 = -2147467261;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      return (unsigned int)DataGreaterThan1KB;
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)this,
      a2,
      -2147467261,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
      160,
      "CBR(pbBuffer != nullptr)");
    goto LABEL_19;
  }
  if ( WinHttpReadData(this[4], a3, a2, &dwNumberOfBytesRead) )
  {
    if ( a2 == dwNumberOfBytesRead )
      return 0;
    DataGreaterThan1KB = -2147024883;
    v7 = -2147024883;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v11,
        v10,
        -2147024883,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
        170,
        "CBR(cbBuffer == cbWinHttpRead)");
LABEL_19:
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v9,
          v8,
          v7,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
          53,
          "CHR(ReadData( cbBuffer, pbBuffer))");
    }
  }
  else
  {
    LastError = GetLastError();
    DataGreaterThan1KB = LastError;
    if ( LastError > 0 )
      DataGreaterThan1KB = (unsigned __int16)LastError | 0x80070000;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v9,
        v8,
        DataGreaterThan1KB,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
        167,
        "CBR(::WinHttpReadData( m_hRequest, pbBuffer, cbBuffer, &cbWinHttpRead))");
    if ( DataGreaterThan1KB < 0 )
    {
      v7 = DataGreaterThan1KB;
      goto LABEL_19;
    }
  }
  return (unsigned int)DataGreaterThan1KB;
}

```

## disassembly

```asm
0x18001b4d8  mov     [rsp+arg_0], rbx
0x18001b4dd  push    rdi
0x18001b4de  sub     rsp, 30h
0x18001b4e2  mov     rax, r8
0x18001b4e5  mov     ebx, edx
0x18001b4e7  cmp     edx, 400h
0x18001b4ed  jbe     short loc_18001B533
0x18001b4ef  call    ?ReadDataGreaterThan1KB@MdmHttpRequest@@AEAAJKPEAE@Z; MdmHttpRequest::ReadDataGreaterThan1KB(ulong,uchar *)
0x18001b4f4  mov     ebx, eax
0x18001b4f6  test    eax, eax
0x18001b4f8  jns     loc_18001B63B
0x18001b4fe  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b505  jz      loc_18001B63B
0x18001b50b  lea     rax, aChrReaddatagre; "CHR(ReadDataGreaterThan1KB( cbBuffer, p"...
0x18001b512  mov     r8d, ebx
0x18001b515  mov     [rsp+38h+var_10], rax
0x18001b51a  mov     [rsp+38h+var_18], 22Fh
0x18001b522  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001b529  call    McTemplateU0dsqs_EventWriteTransfer
0x18001b52e  jmp     loc_18001B63B
0x18001b533  mov     [rsp+38h+dwNumberOfBytesRead], 0
0x18001b53b  test    rax, rax
0x18001b53e  jnz     short loc_18001B56D
0x18001b540  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b547  mov     ebx, 80004003h
0x18001b54c  mov     edi, ebx
0x18001b54e  jz      loc_18001B63B
0x18001b554  lea     rax, aCbrPbbufferNul; "CBR(pbBuffer != nullptr)"
0x18001b55b  mov     [rsp+38h+var_10], rax
0x18001b560  mov     [rsp+38h+var_18], 2A0h
0x18001b568  jmp     loc_18001B605
0x18001b56d  mov     rcx, [rcx+20h]; hRequest
0x18001b571  lea     r9, [rsp+38h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x18001b576  mov     r8d, ebx; dwNumberOfBytesToRead
0x18001b579  mov     rdx, rax; lpBuffer
0x18001b57c  call    cs:__imp_WinHttpReadData
0x18001b583  nop     dword ptr [rax+rax+00h]
0x18001b588  test    eax, eax
0x18001b58a  jnz     short loc_18001B5DB
0x18001b58c  call    cs:__imp_GetLastError
0x18001b593  nop     dword ptr [rax+rax+00h]
0x18001b598  mov     ebx, eax
0x18001b59a  test    eax, eax
0x18001b59c  jle     short loc_18001B5A7
0x18001b59e  movzx   ebx, ax
0x18001b5a1  or      ebx, 80070000h
0x18001b5a7  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b5ae  jz      short loc_18001B5D3
0x18001b5b0  lea     rax, aCbrWinhttpread; "CBR(::WinHttpReadData( m_hRequest, pbBu"...
0x18001b5b7  mov     r8d, ebx
0x18001b5ba  mov     [rsp+38h+var_10], rax
0x18001b5bf  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001b5c6  mov     [rsp+38h+var_18], 2A7h
0x18001b5ce  call    McTemplateU0dsqs_EventWriteTransfer
0x18001b5d3  test    ebx, ebx
0x18001b5d5  jns     short loc_18001B63B
0x18001b5d7  mov     edi, ebx
0x18001b5d9  jmp     short loc_18001B614
0x18001b5db  cmp     ebx, [rsp+38h+dwNumberOfBytesRead]
0x18001b5df  jz      short loc_18001B639
0x18001b5e1  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b5e8  mov     ebx, 8007000Dh
0x18001b5ed  mov     edi, ebx
0x18001b5ef  jz      short loc_18001B63B
0x18001b5f1  lea     rax, aCbrCbbufferCbw; "CBR(cbBuffer == cbWinHttpRead)"
0x18001b5f8  mov     [rsp+38h+var_10], rax
0x18001b5fd  mov     [rsp+38h+var_18], 2AAh
0x18001b605  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001b60c  mov     r8d, ebx
0x18001b60f  call    McTemplateU0dsqs_EventWriteTransfer
0x18001b614  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b61b  jz      short loc_18001B63B
0x18001b61d  lea     rax, aChrReaddataCbb; "CHR(ReadData( cbBuffer, pbBuffer))"
0x18001b624  mov     r8d, edi
0x18001b627  mov     [rsp+38h+var_10], rax
0x18001b62c  mov     [rsp+38h+var_18], 235h
0x18001b634  jmp     loc_18001B522
0x18001b639  xor     ebx, ebx
0x18001b63b  mov     eax, ebx
0x18001b63d  mov     rbx, [rsp+38h+arg_0]
0x18001b642  add     rsp, 30h
0x18001b646  pop     rdi
0x18001b647  retn
```
