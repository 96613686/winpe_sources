# MdmHttpRequest::GetContentSize(ulong *)

- ea: `0x18001b394`
- end: `0x18001b4d0`
- name: `?GetContentSize@MdmHttpRequest@@AEAAJPEAK@Z`
- size: `316`
- prototype: `__int64 __fastcall(MdmHttpRequest *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001be50`

## callees

- `0x1800065c0`
- `0x18001b324`
- `0x18001b394`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b460`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b460`
- `WINHTTP!WinHttpQueryHeaders` at `0x18001b450`
- `WINHTTP!WinHttpQueryHeaders` at `0x18001b450`

## string_xrefs

- `0x18001b3e3`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001b493`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`

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
0x18001b394  mov     rax, rsp
0x18001b397  mov     [rax+8], rbx
0x18001b39b  mov     [rax+20h], rsi
0x18001b39f  push    rdi
0x18001b3a0  sub     rsp, 30h
0x18001b3a4  mov     dword ptr [rax+10h], 0
0x18001b3ab  mov     rdi, rdx
0x18001b3ae  mov     dword ptr [rax+18h], 0
0x18001b3b5  mov     rsi, rcx
0x18001b3b8  test    rdx, rdx
0x18001b3bb  jnz     short loc_18001B3F7
0x18001b3bd  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b3c4  mov     ebx, 80004003h
0x18001b3c9  jz      loc_18001B4AB
0x18001b3cf  lea     rax, aCbrPcbcontents; "CBR(pcbContentSize != nullptr)"
0x18001b3d6  mov     [rsp+38h+lpdwIndex], rax
0x18001b3db  mov     dword ptr [rsp+38h+lpdwBufferLength], 280h
0x18001b3e3  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001b3ea  mov     r8d, ebx
0x18001b3ed  call    McTemplateU0dsqs_EventWriteTransfer
0x18001b3f2  jmp     loc_18001B4AB
0x18001b3f7  mov     rcx, [rcx+20h]; hRequest
0x18001b3fb  test    rcx, rcx
0x18001b3fe  jnz     short loc_18001B428
0x18001b400  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b407  mov     ebx, 80004005h
0x18001b40c  jz      loc_18001B4AB
0x18001b412  lea     rax, aCbrMHrequestNu; "CBR(m_hRequest != nullptr)"
0x18001b419  mov     [rsp+38h+lpdwIndex], rax
0x18001b41e  mov     dword ptr [rsp+38h+lpdwBufferLength], 281h
0x18001b426  jmp     short loc_18001B3E3
0x18001b428  lea     rax, [rsp+38h+dwBufferLength]
0x18001b42d  mov     [rsp+38h+lpdwIndex], 0; lpdwIndex
0x18001b436  lea     r9, [rsp+38h+Buffer]; lpBuffer
0x18001b43b  mov     [rsp+38h+lpdwBufferLength], rax; lpdwBufferLength
0x18001b440  xor     r8d, r8d; pwszName
0x18001b443  mov     [rsp+38h+dwBufferLength], 4
0x18001b44b  mov     edx, 20000005h; dwInfoLevel
0x18001b450  call    cs:__imp_WinHttpQueryHeaders
0x18001b457  nop     dword ptr [rax+rax+00h]
0x18001b45c  test    eax, eax
0x18001b45e  jnz     short loc_18001B4B5
0x18001b460  call    cs:__imp_GetLastError
0x18001b467  nop     dword ptr [rax+rax+00h]
0x18001b46c  mov     ebx, eax
0x18001b46e  test    eax, eax
0x18001b470  jle     short loc_18001B47B
0x18001b472  movzx   ebx, ax
0x18001b475  or      ebx, 80070000h
0x18001b47b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b482  jz      short loc_18001B4A7
0x18001b484  lea     rax, aCbrWinhttpquer; "CBR(::WinHttpQueryHeaders( m_hRequest, "...
0x18001b48b  mov     r8d, ebx
0x18001b48e  mov     [rsp+38h+lpdwIndex], rax
0x18001b493  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001b49a  mov     dword ptr [rsp+38h+lpdwBufferLength], 28Ch
0x18001b4a2  call    McTemplateU0dsqs_EventWriteTransfer
0x18001b4a7  test    ebx, ebx
0x18001b4a9  jns     short loc_18001B4BD
0x18001b4ab  mov     rcx, rsi; this
0x18001b4ae  call    ?CloseHandle@MdmHttpRequest@@AEAAJXZ; MdmHttpRequest::CloseHandle(void)
0x18001b4b3  jmp     short loc_18001B4BD
0x18001b4b5  mov     ecx, [rsp+38h+Buffer]
0x18001b4b9  xor     ebx, ebx
0x18001b4bb  mov     [rdi], ecx
0x18001b4bd  mov     rsi, [rsp+38h+arg_18]
0x18001b4c2  mov     eax, ebx
0x18001b4c4  mov     rbx, [rsp+38h+arg_0]
0x18001b4c9  add     rsp, 30h
0x18001b4cd  pop     rdi
0x18001b4ce  retn
```
