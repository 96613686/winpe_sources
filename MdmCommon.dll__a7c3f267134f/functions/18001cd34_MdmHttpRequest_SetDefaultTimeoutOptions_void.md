# MdmHttpRequest::SetDefaultTimeoutOptions(void)

- ea: `0x18001cd34`
- end: `0x18001ceae`
- name: `?SetDefaultTimeoutOptions@MdmHttpRequest@@AEAAJXZ`
- size: `378`
- prototype: `__int64 __fastcall(MdmHttpRequest *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001be50`

## callees

- `0x1800065c0`
- `0x18001cd34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cda1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cda1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce66`
- `WINHTTP!WinHttpSetOption` at `0x18001cd91`
- `WINHTTP!WinHttpSetOption` at `0x18001cdf4`
- `WINHTTP!WinHttpSetOption` at `0x18001ce56`
- `WINHTTP!WinHttpSetOption` at `0x18001cd91`
- `WINHTTP!WinHttpSetOption` at `0x18001cdf4`
- `WINHTTP!WinHttpSetOption` at `0x18001ce56`

## string_xrefs

- `0x18001cd6c`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`

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
              "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
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
            "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
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
          "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
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
        "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
        91,
        "CBR(m_hSession != nullptr)");
  }
  return v4;
}

```

## disassembly

```asm
0x18001cd34  push    rbx
0x18001cd36  sub     rsp, 30h
0x18001cd3a  mov     rbx, rcx
0x18001cd3d  mov     rcx, [rcx+18h]; hInternet
0x18001cd41  test    rcx, rcx
0x18001cd44  jnz     short loc_18001CD80
0x18001cd46  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001cd4d  mov     ebx, 8000FFFFh
0x18001cd52  jz      loc_18001CEA5
0x18001cd58  lea     rax, aCbrMHsessionNu; "CBR(m_hSession != nullptr)"
0x18001cd5f  mov     [rsp+38h+var_10], rax
0x18001cd64  mov     [rsp+38h+var_18], 25Bh
0x18001cd6c  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001cd73  mov     r8d, ebx
0x18001cd76  call    McTemplateU0dsqs_EventWriteTransfer
0x18001cd7b  jmp     loc_18001CEA5
0x18001cd80  mov     r9d, 4; dwBufferLength
0x18001cd86  lea     r8, byte_1800301C0; lpBuffer
0x18001cd8d  lea     edx, [r9-1]; dwOption
0x18001cd91  call    cs:__imp_WinHttpSetOption
0x18001cd98  nop     dword ptr [rax+rax+00h]
0x18001cd9d  test    eax, eax
0x18001cd9f  jnz     short loc_18001CDDF
0x18001cda1  call    cs:__imp_GetLastError
0x18001cda8  nop     dword ptr [rax+rax+00h]
0x18001cdad  mov     ebx, eax
0x18001cdaf  test    eax, eax
0x18001cdb1  jle     short loc_18001CDBC
0x18001cdb3  movzx   ebx, ax
0x18001cdb6  or      ebx, 80070000h
0x18001cdbc  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001cdc3  jz      loc_18001CEA5
0x18001cdc9  lea     rax, aCbrWinhttpseto_0; "CBR(::WinHttpSetOption( m_hSession, 3, "...
0x18001cdd0  mov     [rsp+38h+var_10], rax
0x18001cdd5  mov     [rsp+38h+var_18], 263h
0x18001cddd  jmp     short loc_18001CD6C
0x18001cddf  mov     rcx, [rbx+18h]; hInternet
0x18001cde3  lea     r8, dword_1800301BC; lpBuffer
0x18001cdea  mov     r9d, 4; dwBufferLength
0x18001cdf0  lea     edx, [r9+2]; dwOption
0x18001cdf4  call    cs:__imp_WinHttpSetOption
0x18001cdfb  nop     dword ptr [rax+rax+00h]
0x18001ce00  test    eax, eax
0x18001ce02  jnz     short loc_18001CE41
0x18001ce04  call    cs:__imp_GetLastError
0x18001ce0b  nop     dword ptr [rax+rax+00h]
0x18001ce10  mov     ebx, eax
0x18001ce12  test    eax, eax
0x18001ce14  jle     short loc_18001CE1F
0x18001ce16  movzx   ebx, ax
0x18001ce19  or      ebx, 80070000h
0x18001ce1f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001ce26  jz      short loc_18001CEA5
0x18001ce28  lea     rax, aCbrWinhttpseto; "CBR(::WinHttpSetOption( m_hSession, 6, "...
0x18001ce2f  mov     [rsp+38h+var_10], rax
0x18001ce34  mov     [rsp+38h+var_18], 26Bh
0x18001ce3c  jmp     loc_18001CD6C
0x18001ce41  mov     rcx, [rbx+18h]; hInternet
0x18001ce45  lea     r8, byte_1800301B8; lpBuffer
0x18001ce4c  mov     r9d, 4; dwBufferLength
0x18001ce52  lea     edx, [r9+1]; dwOption
0x18001ce56  call    cs:__imp_WinHttpSetOption
0x18001ce5d  nop     dword ptr [rax+rax+00h]
0x18001ce62  test    eax, eax
0x18001ce64  jnz     short loc_18001CEA3
0x18001ce66  call    cs:__imp_GetLastError
0x18001ce6d  nop     dword ptr [rax+rax+00h]
0x18001ce72  mov     ebx, eax
0x18001ce74  test    eax, eax
0x18001ce76  jle     short loc_18001CE81
0x18001ce78  movzx   ebx, ax
0x18001ce7b  or      ebx, 80070000h
0x18001ce81  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001ce88  jz      short loc_18001CEA5
0x18001ce8a  lea     rax, aCbrWinhttpseto_1; "CBR(::WinHttpSetOption( m_hSession, 5, "...
0x18001ce91  mov     [rsp+38h+var_10], rax
0x18001ce96  mov     [rsp+38h+var_18], 273h
0x18001ce9e  jmp     loc_18001CD6C
0x18001cea3  xor     ebx, ebx
0x18001cea5  mov     eax, ebx
0x18001cea7  add     rsp, 30h
0x18001ceab  pop     rbx
0x18001ceac  retn
```
