# ProcessReceivedHttpRequest

- ea: `0x18000c788`
- end: `0x18000c8c9`
- name: `ProcessReceivedHttpRequest`
- size: `321`
- prototype: `__int64 __fastcall(__int64, _WORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000a620`

## callees

- `0x18000827c`
- `0x180008360`
- `0x18000c788`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `msvcrt!_strcmpi` at `0x18000c848`
- `msvcrt!_strcmpi` at `0x18000c848`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000c7e9`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000c7e9`

## pseudocode

```c
__int64 __fastcall ProcessReceivedHttpRequest(__int64 a1, _WORD *a2)
{
  const wchar_t *v4; // r8
  const char *v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // r8
  int Source2[4]; // [rsp+20h] [rbp-828h] BYREF
  int v10; // [rsp+30h] [rbp-818h] BYREF
  _BYTE v11[2044]; // [rsp+34h] [rbp-814h] BYREF

  Source2[0] = 65537;
  v10 = 0;
  memset_0(v11, 0, sizeof(v11));
  *a2 = 200;
  if ( RtlCompareMemory((const void *)(a1 + 32), Source2, 4u) != 4 )
  {
    if ( (byte_18002D803 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(
        (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceError,
        L"Version mismatch in the request");
    *a2 = 505;
    return 50;
  }
  if ( *(_DWORD *)(a1 + 36) != 1 )
  {
    if ( (byte_18002D803 & 8) == 0 )
    {
LABEL_14:
      *a2 = 400;
      return 50;
    }
    v4 = L"Verb not accepted";
LABEL_13:
    McTemplateU0z_EventWriteTransfer(
      (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceError,
      v4);
    goto LABEL_14;
  }
  v5 = *(const char **)(a1 + 48);
  if ( !v5 || (v6 = 0, _strcmpi(v5, "SSTP_DUPLEX_POST")) )
  {
    if ( (byte_18002D803 & 8) == 0 )
      goto LABEL_14;
    v7 = *(_QWORD *)(a1 + 48);
    LOWORD(v10) = 0;
    FormatRRASErrorString((wchar_t *)&v10, L"Received verb other than SSTP_POST - %hs", v7);
    if ( (byte_18002D803 & 8) == 0 )
      goto LABEL_14;
    v4 = (const wchar_t *)&v10;
    goto LABEL_13;
  }
  return v6;
}

```

## disassembly

```asm
0x18000c788  mov     [rsp+arg_10], rbx
0x18000c78d  mov     [rsp+arg_18], rsi
0x18000c792  push    rdi
0x18000c793  sub     rsp, 840h
0x18000c79a  mov     rax, cs:__security_cookie
0x18000c7a1  xor     rax, rsp
0x18000c7a4  mov     [rsp+848h+var_18], rax
0x18000c7ac  mov     rsi, rdx
0x18000c7af  mov     [rsp+848h+Source2], 10001h
0x18000c7b7  mov     rdi, rcx
0x18000c7ba  xor     eax, eax
0x18000c7bc  xor     edx, edx; Val
0x18000c7be  mov     [rsp+848h+var_818], eax
0x18000c7c2  lea     rcx, [rsp+848h+var_814]; void *
0x18000c7c7  mov     r8d, 7FCh; Size
0x18000c7cd  mov     ebx, 1
0x18000c7d2  call    memset_0
0x18000c7d7  lea     rcx, [rdi+20h]; Source1
0x18000c7db  mov     word ptr [rsi], 0C8h
0x18000c7e0  lea     r8d, [rbx+3]; Length
0x18000c7e4  lea     rdx, [rsp+848h+Source2]; Source2
0x18000c7e9  call    cs:__imp_RtlCompareMemory
0x18000c7ef  cmp     rax, 4
0x18000c7f3  jz      short loc_18000C81F
0x18000c7f5  test    cs:byte_18002D803, 8
0x18000c7fc  jz      short loc_18000C818
0x18000c7fe  lea     r8, aVersionMismatc; "Version mismatch in the request"
0x18000c805  lea     rdx, RasSSTPSvcTraceError
0x18000c80c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c813  call    McTemplateU0z_EventWriteTransfer
0x18000c818  mov     word ptr [rsi], 1F9h
0x18000c81d  jmp     short loc_18000C89D
0x18000c81f  cmp     [rdi+24h], ebx
0x18000c822  jz      short loc_18000C836
0x18000c824  test    cs:byte_18002D803, 8
0x18000c82b  jz      short loc_18000C898
0x18000c82d  lea     r8, aVerbNotAccepte; "Verb not accepted"
0x18000c834  jmp     short loc_18000C885
0x18000c836  mov     rcx, [rdi+30h]; String1
0x18000c83a  test    rcx, rcx
0x18000c83d  jz      short loc_18000C852
0x18000c83f  lea     rdx, aSstpDuplexPost; "SSTP_DUPLEX_POST"
0x18000c846  xor     ebx, ebx
0x18000c848  call    cs:__imp__strcmpi
0x18000c84e  test    eax, eax
0x18000c850  jz      short loc_18000C8A2
0x18000c852  test    cs:byte_18002D803, 8
0x18000c859  jz      short loc_18000C898
0x18000c85b  mov     r8, [rdi+30h]
0x18000c85f  lea     rdx, aReceivedVerbOt; "Received verb other than SSTP_POST - %h"...
0x18000c866  xor     eax, eax
0x18000c868  lea     rcx, [rsp+848h+var_818]
0x18000c86d  mov     word ptr [rsp+848h+var_818], ax
0x18000c872  call    FormatRRASErrorString
0x18000c877  test    cs:byte_18002D803, 8
0x18000c87e  jz      short loc_18000C898
0x18000c880  lea     r8, [rsp+848h+var_818]
0x18000c885  lea     rdx, RasSSTPSvcTraceError
0x18000c88c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c893  call    McTemplateU0z_EventWriteTransfer
0x18000c898  mov     word ptr [rsi], 190h
0x18000c89d  mov     ebx, 32h ; '2'
0x18000c8a2  mov     eax, ebx
0x18000c8a4  mov     rcx, [rsp+848h+var_18]
0x18000c8ac  xor     rcx, rsp; StackCookie
0x18000c8af  call    __security_check_cookie
0x18000c8b4  lea     r11, [rsp+848h+var_8]
0x18000c8bc  mov     rbx, [r11+20h]
0x18000c8c0  mov     rsi, [r11+28h]
0x18000c8c4  mov     rsp, r11
0x18000c8c7  pop     rdi
0x18000c8c8  retn
```
