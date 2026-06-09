# MdmHttpRequest::GetHttpData(ulong,uchar *)

- ea: `0x18001af58`
- end: `0x18001b0bc`
- name: `?GetHttpData@MdmHttpRequest@@AEAAJKPEAE@Z`
- size: `356`
- prototype: `__int64 __fastcall(HINTERNET *this, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001b8b0`

## callees

- `0x180006548`
- `0x18001af58`
- `0x18001b13c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b006`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b006`
- `WINHTTP!WinHttpReadData` at `0x18001affc`
- `WINHTTP!WinHttpReadData` at `0x18001affc`

## string_xrefs

- `0x18001afa2`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001b033`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001b079`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001af8b`: `CHR(ReadDataGreaterThan1KB( cbBuffer, pbBuffer))`
- `0x18001b091`: `CHR(ReadData( cbBuffer, pbBuffer))`
- `0x18001b024`: `CBR(::WinHttpReadData( m_hRequest, pbBuffer, cbBuffer, &cbWinHttpRead))`
- `0x18001b065`: `CBR(cbBuffer == cbWinHttpRead)`

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
0x18001af58  mov     [rsp+arg_0], rbx
0x18001af5d  push    rdi
0x18001af5e  sub     rsp, 30h
0x18001af62  mov     rax, r8
0x18001af65  mov     ebx, edx
0x18001af67  cmp     edx, 400h
0x18001af6d  jbe     short loc_18001AFB3
0x18001af6f  call    ?ReadDataGreaterThan1KB@MdmHttpRequest@@AEAAJKPEAE@Z; MdmHttpRequest::ReadDataGreaterThan1KB(ulong,uchar *)
0x18001af74  mov     ebx, eax
0x18001af76  test    eax, eax
0x18001af78  jns     loc_18001B0AF
0x18001af7e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001af85  jz      loc_18001B0AF
0x18001af8b  lea     rax, aChrReaddatagre; "CHR(ReadDataGreaterThan1KB( cbBuffer, p"...
0x18001af92  mov     r8d, ebx
0x18001af95  mov     [rsp+38h+var_10], rax
0x18001af9a  mov     [rsp+38h+var_18], 22Fh
0x18001afa2  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001afa9  call    McTemplateU0dsqs_EventWriteTransfer
0x18001afae  jmp     loc_18001B0AF
0x18001afb3  mov     [rsp+38h+dwNumberOfBytesRead], 0
0x18001afbb  test    rax, rax
0x18001afbe  jnz     short loc_18001AFED
0x18001afc0  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001afc7  mov     ebx, 80004003h
0x18001afcc  mov     edi, ebx
0x18001afce  jz      loc_18001B0AF
0x18001afd4  lea     rax, aCbrPbbufferNul; "CBR(pbBuffer != nullptr)"
0x18001afdb  mov     [rsp+38h+var_10], rax
0x18001afe0  mov     [rsp+38h+var_18], 2A0h
0x18001afe8  jmp     loc_18001B079
0x18001afed  mov     rcx, [rcx+20h]; hRequest
0x18001aff1  lea     r9, [rsp+38h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x18001aff6  mov     r8d, ebx; dwNumberOfBytesToRead
0x18001aff9  mov     rdx, rax; lpBuffer
0x18001affc  call    cs:__imp_WinHttpReadData
0x18001b002  test    eax, eax
0x18001b004  jnz     short loc_18001B04F
0x18001b006  call    cs:__imp_GetLastError
0x18001b00c  mov     ebx, eax
0x18001b00e  test    eax, eax
0x18001b010  jle     short loc_18001B01B
0x18001b012  movzx   ebx, ax
0x18001b015  or      ebx, 80070000h
0x18001b01b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b022  jz      short loc_18001B047
0x18001b024  lea     rax, aCbrWinhttpread; "CBR(::WinHttpReadData( m_hRequest, pbBu"...
0x18001b02b  mov     r8d, ebx
0x18001b02e  mov     [rsp+38h+var_10], rax
0x18001b033  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001b03a  mov     [rsp+38h+var_18], 2A7h
0x18001b042  call    McTemplateU0dsqs_EventWriteTransfer
0x18001b047  test    ebx, ebx
0x18001b049  jns     short loc_18001B0AF
0x18001b04b  mov     edi, ebx
0x18001b04d  jmp     short loc_18001B088
0x18001b04f  cmp     ebx, [rsp+38h+dwNumberOfBytesRead]
0x18001b053  jz      short loc_18001B0AD
0x18001b055  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b05c  mov     ebx, 8007000Dh
0x18001b061  mov     edi, ebx
0x18001b063  jz      short loc_18001B0AF
0x18001b065  lea     rax, aCbrCbbufferCbw; "CBR(cbBuffer == cbWinHttpRead)"
0x18001b06c  mov     [rsp+38h+var_10], rax
0x18001b071  mov     [rsp+38h+var_18], 2AAh
0x18001b079  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001b080  mov     r8d, ebx
0x18001b083  call    McTemplateU0dsqs_EventWriteTransfer
0x18001b088  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b08f  jz      short loc_18001B0AF
0x18001b091  lea     rax, aChrReaddataCbb; "CHR(ReadData( cbBuffer, pbBuffer))"
0x18001b098  mov     r8d, edi
0x18001b09b  mov     [rsp+38h+var_10], rax
0x18001b0a0  mov     [rsp+38h+var_18], 235h
0x18001b0a8  jmp     loc_18001AFA2
0x18001b0ad  xor     ebx, ebx
0x18001b0af  mov     eax, ebx
0x18001b0b1  mov     rbx, [rsp+38h+arg_0]
0x18001b0b6  add     rsp, 30h
0x18001b0ba  pop     rdi
0x18001b0bb  retn
```
