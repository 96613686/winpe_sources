# MdmHttpRequest::GetContentSize(ulong *)

- ea: `0x18001ae20`
- end: `0x18001af4f`
- name: `?GetContentSize@MdmHttpRequest@@AEAAJPEAK@Z`
- size: `303`
- prototype: `__int64 __fastcall(MdmHttpRequest *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001b8b0`

## callees

- `0x180006548`
- `0x18001adc4`
- `0x18001ae20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aee6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aee6`
- `WINHTTP!WinHttpQueryHeaders` at `0x18001aedc`
- `WINHTTP!WinHttpQueryHeaders` at `0x18001aedc`

## string_xrefs

- `0x18001ae6f`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001af13`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`

## pseudocode

```c
__int64 __fastcall MdmHttpRequest::GetContentSize(MdmHttpRequest *this, unsigned int *a2)
{
  unsigned int v4; // ebx
  void *v5; // rcx
  signed int LastError; // eax
  int v7; // edx
  int v8; // ecx
  DWORD dwBufferLength; // [rsp+48h] [rbp+10h] BYREF
  unsigned int Buffer; // [rsp+50h] [rbp+18h] BYREF

  dwBufferLength = 0;
  Buffer = 0;
  if ( !a2 )
  {
    v4 = -2147467261;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)this,
        0,
        -2147467261,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
        128,
        "CBR(pcbContentSize != nullptr)");
LABEL_14:
    MdmHttpRequest::CloseHandle(this);
    return v4;
  }
  v5 = (void *)*((_QWORD *)this + 4);
  if ( !v5 )
  {
    v4 = -2147467259;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        (_DWORD)a2,
        -2147467259,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
        129,
        "CBR(m_hRequest != nullptr)");
    goto LABEL_14;
  }
  dwBufferLength = 4;
  if ( WinHttpQueryHeaders(v5, 0x20000005u, 0, &Buffer, &dwBufferLength, 0) )
  {
    v4 = 0;
    *a2 = Buffer;
    return v4;
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      v8,
      v7,
      v4,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
      140,
      "CBR(::WinHttpQueryHeaders( m_hRequest, 5 | 0x20000000, nullptr, (LPVOID)&cbContentLength, &cbSize, nullptr))");
  if ( (v4 & 0x80000000) != 0 )
    goto LABEL_14;
  return v4;
}

```

## disassembly

```asm
0x18001ae20  mov     rax, rsp
0x18001ae23  mov     [rax+8], rbx
0x18001ae27  mov     [rax+20h], rsi
0x18001ae2b  push    rdi
0x18001ae2c  sub     rsp, 30h
0x18001ae30  mov     dword ptr [rax+10h], 0
0x18001ae37  mov     rdi, rdx
0x18001ae3a  mov     dword ptr [rax+18h], 0
0x18001ae41  mov     rsi, rcx
0x18001ae44  test    rdx, rdx
0x18001ae47  jnz     short loc_18001AE83
0x18001ae49  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001ae50  mov     ebx, 80004003h
0x18001ae55  jz      loc_18001AF2B
0x18001ae5b  lea     rax, aCbrPcbcontents; "CBR(pcbContentSize != nullptr)"
0x18001ae62  mov     [rsp+38h+lpdwIndex], rax
0x18001ae67  mov     dword ptr [rsp+38h+lpdwBufferLength], 280h
0x18001ae6f  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001ae76  mov     r8d, ebx
0x18001ae79  call    McTemplateU0dsqs_EventWriteTransfer
0x18001ae7e  jmp     loc_18001AF2B
0x18001ae83  mov     rcx, [rcx+20h]; hRequest
0x18001ae87  test    rcx, rcx
0x18001ae8a  jnz     short loc_18001AEB4
0x18001ae8c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001ae93  mov     ebx, 80004005h
0x18001ae98  jz      loc_18001AF2B
0x18001ae9e  lea     rax, aCbrMHrequestNu; "CBR(m_hRequest != nullptr)"
0x18001aea5  mov     [rsp+38h+lpdwIndex], rax
0x18001aeaa  mov     dword ptr [rsp+38h+lpdwBufferLength], 281h
0x18001aeb2  jmp     short loc_18001AE6F
0x18001aeb4  lea     rax, [rsp+38h+dwBufferLength]
0x18001aeb9  mov     [rsp+38h+lpdwIndex], 0; lpdwIndex
0x18001aec2  lea     r9, [rsp+38h+Buffer]; lpBuffer
0x18001aec7  mov     [rsp+38h+lpdwBufferLength], rax; lpdwBufferLength
0x18001aecc  xor     r8d, r8d; pwszName
0x18001aecf  mov     [rsp+38h+dwBufferLength], 4
0x18001aed7  mov     edx, 20000005h; dwInfoLevel
0x18001aedc  call    cs:__imp_WinHttpQueryHeaders
0x18001aee2  test    eax, eax
0x18001aee4  jnz     short loc_18001AF35
0x18001aee6  call    cs:__imp_GetLastError
0x18001aeec  mov     ebx, eax
0x18001aeee  test    eax, eax
0x18001aef0  jle     short loc_18001AEFB
0x18001aef2  movzx   ebx, ax
0x18001aef5  or      ebx, 80070000h
0x18001aefb  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001af02  jz      short loc_18001AF27
0x18001af04  lea     rax, aCbrWinhttpquer; "CBR(::WinHttpQueryHeaders( m_hRequest, "...
0x18001af0b  mov     r8d, ebx
0x18001af0e  mov     [rsp+38h+lpdwIndex], rax
0x18001af13  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001af1a  mov     dword ptr [rsp+38h+lpdwBufferLength], 28Ch
0x18001af22  call    McTemplateU0dsqs_EventWriteTransfer
0x18001af27  test    ebx, ebx
0x18001af29  jns     short loc_18001AF3D
0x18001af2b  mov     rcx, rsi; this
0x18001af2e  call    ?CloseHandle@MdmHttpRequest@@AEAAJXZ; MdmHttpRequest::CloseHandle(void)
0x18001af33  jmp     short loc_18001AF3D
0x18001af35  mov     ecx, [rsp+38h+Buffer]
0x18001af39  xor     ebx, ebx
0x18001af3b  mov     [rdi], ecx
0x18001af3d  mov     rsi, [rsp+38h+arg_18]
0x18001af42  mov     eax, ebx
0x18001af44  mov     rbx, [rsp+38h+arg_0]
0x18001af49  add     rsp, 30h
0x18001af4d  pop     rdi
0x18001af4e  retn
```
