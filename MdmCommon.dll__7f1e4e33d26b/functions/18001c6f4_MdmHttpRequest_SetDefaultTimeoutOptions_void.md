# MdmHttpRequest::SetDefaultTimeoutOptions(void)

- ea: `0x18001c6f4`
- end: `0x18001c849`
- name: `?SetDefaultTimeoutOptions@MdmHttpRequest@@AEAAJXZ`
- size: `341`
- prototype: `__int64 __fastcall(MdmHttpRequest *this, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001b8b0`

## callees

- `0x180006548`
- `0x18001c6f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c75b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c7b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c808`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c75b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c7b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c808`
- `WINHTTP!WinHttpSetOption` at `0x18001c751`
- `WINHTTP!WinHttpSetOption` at `0x18001c7a8`
- `WINHTTP!WinHttpSetOption` at `0x18001c7fe`
- `WINHTTP!WinHttpSetOption` at `0x18001c751`
- `WINHTTP!WinHttpSetOption` at `0x18001c7a8`
- `WINHTTP!WinHttpSetOption` at `0x18001c7fe`

## string_xrefs

- `0x18001c72c`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`

## pseudocode

```c
__int64 __fastcall MdmHttpRequest::SetDefaultTimeoutOptions(MdmHttpRequest *this, int a2)
{
  void *v3; // rcx
  unsigned int v4; // ebx
  signed int v5; // eax
  int v6; // edx
  int v7; // ecx
  signed int v8; // eax
  int v9; // edx
  int v10; // ecx
  signed int LastError; // eax
  int v12; // edx
  int v13; // ecx

  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 )
  {
    if ( WinHttpSetOption(v3, 3u, byte_1800301C0, 4u) )
    {
      if ( WinHttpSetOption(*((HINTERNET *)this + 3), 6u, &dword_1800301BC, 4u) )
      {
        if ( WinHttpSetOption(*((HINTERNET *)this + 3), 5u, byte_1800301B8, 4u) )
        {
          return 0;
        }
        else
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v13,
              v12,
              v4,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
              115,
              "CBR(::WinHttpSetOption( m_hSession, 5, &c_dwSendTimeout, sizeof(c_dwSendTimeout)))");
        }
      }
      else
      {
        v8 = GetLastError();
        v4 = v8;
        if ( v8 > 0 )
          v4 = (unsigned __int16)v8 | 0x80070000;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v10,
            v9,
            v4,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
            107,
            "CBR(::WinHttpSetOption( m_hSession, 6, &c_dwReceiveTimeout, sizeof(c_dwReceiveTimeout)))");
      }
    }
    else
    {
      v5 = GetLastError();
      v4 = v5;
      if ( v5 > 0 )
        v4 = (unsigned __int16)v5 | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v7,
          v6,
          v4,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
          99,
          "CBR(::WinHttpSetOption( m_hSession, 3, &c_dwConnectTimeout, sizeof(c_dwConnectTimeout)))");
    }
  }
  else
  {
    v4 = -2147418113;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        a2,
        -2147418113,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
        91,
        "CBR(m_hSession != nullptr)");
  }
  return v4;
}

```

## disassembly

```asm
0x18001c6f4  push    rbx
0x18001c6f6  sub     rsp, 30h
0x18001c6fa  mov     rbx, rcx
0x18001c6fd  mov     rcx, [rcx+18h]; hInternet
0x18001c701  test    rcx, rcx
0x18001c704  jnz     short loc_18001C740
0x18001c706  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001c70d  mov     ebx, 8000FFFFh
0x18001c712  jz      loc_18001C841
0x18001c718  lea     rax, aCbrMHsessionNu; "CBR(m_hSession != nullptr)"
0x18001c71f  mov     [rsp+38h+var_10], rax
0x18001c724  mov     [rsp+38h+var_18], 25Bh
0x18001c72c  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001c733  mov     r8d, ebx
0x18001c736  call    McTemplateU0dsqs_EventWriteTransfer
0x18001c73b  jmp     loc_18001C841
0x18001c740  mov     r9d, 4; dwBufferLength
0x18001c746  lea     r8, byte_1800301C0; lpBuffer
0x18001c74d  lea     edx, [r9-1]; dwOption
0x18001c751  call    cs:__imp_WinHttpSetOption
0x18001c757  test    eax, eax
0x18001c759  jnz     short loc_18001C793
0x18001c75b  call    cs:__imp_GetLastError
0x18001c761  mov     ebx, eax
0x18001c763  test    eax, eax
0x18001c765  jle     short loc_18001C770
0x18001c767  movzx   ebx, ax
0x18001c76a  or      ebx, 80070000h
0x18001c770  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001c777  jz      loc_18001C841
0x18001c77d  lea     rax, aCbrWinhttpseto_0; "CBR(::WinHttpSetOption( m_hSession, 3, "...
0x18001c784  mov     [rsp+38h+var_10], rax
0x18001c789  mov     [rsp+38h+var_18], 263h
0x18001c791  jmp     short loc_18001C72C
0x18001c793  mov     rcx, [rbx+18h]; hInternet
0x18001c797  lea     r8, dword_1800301BC; lpBuffer
0x18001c79e  mov     r9d, 4; dwBufferLength
0x18001c7a4  lea     edx, [r9+2]; dwOption
0x18001c7a8  call    cs:__imp_WinHttpSetOption
0x18001c7ae  test    eax, eax
0x18001c7b0  jnz     short loc_18001C7E9
0x18001c7b2  call    cs:__imp_GetLastError
0x18001c7b8  mov     ebx, eax
0x18001c7ba  test    eax, eax
0x18001c7bc  jle     short loc_18001C7C7
0x18001c7be  movzx   ebx, ax
0x18001c7c1  or      ebx, 80070000h
0x18001c7c7  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001c7ce  jz      short loc_18001C841
0x18001c7d0  lea     rax, aCbrWinhttpseto; "CBR(::WinHttpSetOption( m_hSession, 6, "...
0x18001c7d7  mov     [rsp+38h+var_10], rax
0x18001c7dc  mov     [rsp+38h+var_18], 26Bh
0x18001c7e4  jmp     loc_18001C72C
0x18001c7e9  mov     rcx, [rbx+18h]; hInternet
0x18001c7ed  lea     r8, byte_1800301B8; lpBuffer
0x18001c7f4  mov     r9d, 4; dwBufferLength
0x18001c7fa  lea     edx, [r9+1]; dwOption
0x18001c7fe  call    cs:__imp_WinHttpSetOption
0x18001c804  test    eax, eax
0x18001c806  jnz     short loc_18001C83F
0x18001c808  call    cs:__imp_GetLastError
0x18001c80e  mov     ebx, eax
0x18001c810  test    eax, eax
0x18001c812  jle     short loc_18001C81D
0x18001c814  movzx   ebx, ax
0x18001c817  or      ebx, 80070000h
0x18001c81d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001c824  jz      short loc_18001C841
0x18001c826  lea     rax, aCbrWinhttpseto_1; "CBR(::WinHttpSetOption( m_hSession, 5, "...
0x18001c82d  mov     [rsp+38h+var_10], rax
0x18001c832  mov     [rsp+38h+var_18], 273h
0x18001c83a  jmp     loc_18001C72C
0x18001c83f  xor     ebx, ebx
0x18001c841  mov     eax, ebx
0x18001c843  add     rsp, 30h
0x18001c847  pop     rbx
0x18001c848  retn
```
