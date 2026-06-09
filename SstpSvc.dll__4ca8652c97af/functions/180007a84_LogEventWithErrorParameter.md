# LogEventWithErrorParameter

- ea: `0x180007a84`
- end: `0x180007c2b`
- name: `LogEventWithErrorParameter`
- size: `423`
- prototype: `void __fastcall(DWORD dwMessageId, __int64, DWORD, __int64)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180001240`
- `0x18000d324`
- `0x18000df30`
- `0x18000e9a0`

## callees

- `0x180007a84`
- `0x18000827c`
- `0x180008360`
- `0x18000ec98`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007c03`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007c03`
- `rtutils!RouterLogEventW` at `0x180007bab`
- `rtutils!RouterLogEventW` at `0x180007bf8`
- `rtutils!RouterLogEventW` at `0x180007bab`
- `rtutils!RouterLogEventW` at `0x180007bf8`
- `rtutils!RouterGetErrorStringW` at `0x180007b1c`
- `rtutils!RouterGetErrorStringW` at `0x180007b1c`

## pseudocode

```c
void __fastcall LogEventWithErrorParameter(DWORD dwMessageId, __int64 a2, DWORD a3, __int64 a4)
{
  DWORD ErrorStringW; // eax
  void *v8; // rcx
  DWORD v9; // r9d
  LPWSTR *p_plpszSubStringArray; // rax
  LPWSTR lpwszErrorString; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR plpszSubStringArray; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v13; // [rsp+40h] [rbp-C0h]
  WCHAR WideCharStr[40]; // [rsp+50h] [rbp-B0h] BYREF
  int v15; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v16[2044]; // [rsp+A4h] [rbp-5Ch] BYREF

  if ( *((_QWORD *)SstpSvcGlobals + 9) )
  {
    lpwszErrorString = 0;
    v15 = 0;
    memset_0(v16, 0, sizeof(v16));
    ConvertCorrelationIdToWideChar(WideCharStr);
    plpszSubStringArray = WideCharStr;
    v13 = 0;
    ErrorStringW = RouterGetErrorStringW(a3, &lpwszErrorString);
    if ( ErrorStringW )
    {
      if ( (byte_18002D803 & 8) != 0 )
      {
        LOWORD(v15) = 0;
        FormatRRASErrorString((wchar_t *)&v15, L"Unable to get the error string for (%d): %d", a3, ErrorStringW);
        if ( (byte_18002D803 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v15);
      }
      v8 = (void *)*((_QWORD *)SstpSvcGlobals + 9);
      if ( a4 )
        RouterLogEventW(v8, 1u, dwMessageId, 1u, &plpszSubStringArray, a3);
      else
        RouterLogEventW(v8, 1u, dwMessageId, 0, 0, a3);
    }
    else
    {
      if ( a4 )
      {
        v9 = 2;
        *(_QWORD *)&v13 = lpwszErrorString;
        p_plpszSubStringArray = &plpszSubStringArray;
      }
      else
      {
        v9 = 1;
        p_plpszSubStringArray = &lpwszErrorString;
      }
      RouterLogEventW(*((HANDLE *)SstpSvcGlobals + 9), 1u, dwMessageId, v9, p_plpszSubStringArray, a3);
      LocalFree(lpwszErrorString);
    }
  }
}

```

## disassembly

```asm
0x180007a84  mov     [rsp-8+arg_8], rbx
0x180007a89  push    rbp
0x180007a8a  push    rsi
0x180007a8b  push    rdi
0x180007a8c  lea     rbp, [rsp-7B0h]
0x180007a94  sub     rsp, 8B0h
0x180007a9b  mov     rax, cs:__security_cookie
0x180007aa2  xor     rax, rsp
0x180007aa5  mov     [rbp+7C0h+var_20], rax
0x180007aac  mov     rax, cs:SstpSvcGlobals
0x180007ab3  mov     rsi, r9
0x180007ab6  mov     ebx, r8d
0x180007ab9  mov     edi, ecx
0x180007abb  cmp     qword ptr [rax+48h], 0
0x180007ac0  jz      loc_180007C09
0x180007ac6  xorps   xmm0, xmm0
0x180007ac9  mov     [rsp+8C0h+lpwszErrorString], 0
0x180007ad2  xor     eax, eax
0x180007ad4  mov     [rsp+8C0h+var_888], 0
0x180007add  xor     edx, edx; Val
0x180007adf  mov     [rbp+7C0h+var_820], eax
0x180007ae2  mov     r8d, 7FCh; Size
0x180007ae8  lea     rcx, [rbp+7C0h+var_81C]; void *
0x180007aec  movups  [rsp+8C0h+var_880], xmm0
0x180007af1  call    memset_0
0x180007af6  mov     r8, rsi
0x180007af9  lea     rcx, [rsp+8C0h+WideCharStr]; lpWideCharStr
0x180007afe  call    ConvertCorrelationIdToWideChar
0x180007b03  lea     rax, [rsp+8C0h+WideCharStr]
0x180007b08  xorps   xmm0, xmm0
0x180007b0b  lea     rdx, [rsp+8C0h+lpwszErrorString]; lplpwszErrorString
0x180007b10  mov     [rsp+8C0h+var_888], rax
0x180007b15  mov     ecx, ebx; dwErrorCode
0x180007b17  movups  [rsp+8C0h+var_880], xmm0
0x180007b1c  call    cs:__imp_RouterGetErrorStringW
0x180007b22  test    eax, eax
0x180007b24  jz      loc_180007BB3
0x180007b2a  test    cs:byte_18002D803, 8
0x180007b31  jz      short loc_180007B6F
0x180007b33  xor     ecx, ecx
0x180007b35  lea     rdx, aUnableToGetThe_0; "Unable to get the error string for (%d)"...
0x180007b3c  mov     word ptr [rbp+7C0h+var_820], cx
0x180007b40  mov     r9d, eax
0x180007b43  lea     rcx, [rbp+7C0h+var_820]
0x180007b47  mov     r8d, ebx
0x180007b4a  call    FormatRRASErrorString
0x180007b4f  test    cs:byte_18002D803, 8
0x180007b56  jz      short loc_180007B6F
0x180007b58  lea     r8, [rbp+7C0h+var_820]
0x180007b5c  lea     rdx, RasSSTPSvcTraceError
0x180007b63  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180007b6a  call    McTemplateU0z_EventWriteTransfer
0x180007b6f  mov     rcx, cs:SstpSvcGlobals
0x180007b76  mov     r8d, edi; dwMessageId
0x180007b79  mov     [rsp+8C0h+dwErrorCode], ebx; dwErrorCode
0x180007b7d  mov     rcx, [rcx+48h]; hLogHandle
0x180007b81  test    rsi, rsi
0x180007b84  jz      short loc_180007B9B
0x180007b86  lea     rax, [rsp+8C0h+var_888]
0x180007b8b  mov     r9d, 1
0x180007b91  mov     [rsp+8C0h+plpszSubStringArray], rax
0x180007b96  mov     edx, r9d
0x180007b99  jmp     short loc_180007BAB
0x180007b9b  xor     r9d, r9d; dwSubStringCount
0x180007b9e  mov     [rsp+8C0h+plpszSubStringArray], 0; plpszSubStringArray
0x180007ba7  lea     edx, [r9+1]; dwEventType
0x180007bab  call    cs:__imp_RouterLogEventW
0x180007bb1  jmp     short loc_180007C09
0x180007bb3  mov     rcx, cs:SstpSvcGlobals
0x180007bba  mov     r8d, edi; dwMessageId
0x180007bbd  mov     [rsp+8C0h+dwErrorCode], ebx; dwErrorCode
0x180007bc1  test    rsi, rsi
0x180007bc4  jz      short loc_180007BE1
0x180007bc6  mov     rax, [rsp+8C0h+lpwszErrorString]
0x180007bcb  mov     r9d, 2
0x180007bd1  mov     qword ptr [rsp+8C0h+var_880], rax
0x180007bd6  lea     rax, [rsp+8C0h+var_888]
0x180007bdb  lea     edx, [r9-1]
0x180007bdf  jmp     short loc_180007BEF
0x180007be1  mov     r9d, 1; dwSubStringCount
0x180007be7  lea     rax, [rsp+8C0h+lpwszErrorString]
0x180007bec  mov     edx, r9d; dwEventType
0x180007bef  mov     rcx, [rcx+48h]; hLogHandle
0x180007bf3  mov     [rsp+8C0h+plpszSubStringArray], rax; plpszSubStringArray
0x180007bf8  call    cs:__imp_RouterLogEventW
0x180007bfe  mov     rcx, [rsp+8C0h+lpwszErrorString]; hMem
0x180007c03  call    cs:__imp_LocalFree
0x180007c09  mov     rcx, [rbp+7C0h+var_20]
0x180007c10  xor     rcx, rsp; StackCookie
0x180007c13  call    __security_check_cookie
0x180007c18  mov     rbx, [rsp+8C0h+arg_8]
0x180007c20  add     rsp, 8B0h
0x180007c27  pop     rdi
0x180007c28  pop     rsi
0x180007c29  pop     rbp
0x180007c2a  retn
```
