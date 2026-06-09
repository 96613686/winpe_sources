# GetTokenSids(void *,void * *)

- ea: `0x18012bb7c`
- end: `0x18012bc7d`
- name: `?GetTokenSids@@YAJPEAXPEAPEAX@Z`
- size: `257`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18012bf94`

## callees

- `0x18012bb7c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18012bc54`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18012bc5c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18012bc6c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18012bc54`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18012bc5c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18012bc6c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18012bbd2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18012bc1a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18012bbd2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18012bc1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bbbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bc3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bbbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bc3c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18012bc32`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18012bc32`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18012bbb7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18012bc01`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18012bbb7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18012bc01`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18012bc0e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18012bc0e`

## pseudocode

```c
__int64 __fastcall GetTokenSids(HANDLE TokenHandle, void **a2)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  PSID *v6; // rdi
  void *v7; // rax
  void *v8; // rbx
  DWORD TokenInformationLength; // [rsp+68h] [rbp+10h] BYREF

  TokenInformationLength = 0;
  if ( a2 )
  {
    *a2 = 0;
    GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError != 122 )
    {
      v6 = 0;
      goto LABEL_10;
    }
    v6 = (PSID *)malloc(TokenInformationLength);
    if ( !v6 )
    {
LABEL_5:
      v5 = -2147024882;
LABEL_12:
      free(v6);
      free(0);
      return v5;
    }
    if ( !GetTokenInformation(TokenHandle, TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_9;
    TokenInformationLength = GetLengthSid(*v6);
    v7 = malloc(TokenInformationLength);
    v8 = v7;
    if ( !v7 )
      goto LABEL_5;
    if ( !CopySid(TokenInformationLength, v7, *v6) )
    {
LABEL_9:
      LastError = GetLastError();
      v5 = LastError;
LABEL_10:
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_12;
    }
    *a2 = v8;
    free(v6);
  }
  return 0;
}

```

## disassembly

```asm
0x18012bb7c  push    rbx
0x18012bb7e  push    rbp
0x18012bb7f  push    rsi
0x18012bb80  push    rdi
0x18012bb81  sub     rsp, 38h
0x18012bb85  mov     [rsp+58h+TokenInformationLength], 0
0x18012bb8d  mov     rsi, rdx
0x18012bb90  mov     rbp, rcx
0x18012bb93  test    rdx, rdx
0x18012bb96  jz      loc_18012BC72
0x18012bb9c  xor     r9d, r9d; TokenInformationLength
0x18012bb9f  mov     qword ptr [rdx], 0
0x18012bba6  lea     rax, [rsp+58h+TokenInformationLength]
0x18012bbab  xor     r8d, r8d; TokenInformation
0x18012bbae  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18012bbb3  lea     edx, [r9+1]; TokenInformationClass
0x18012bbb7  call    cs:__imp_GetTokenInformation
0x18012bbbd  call    cs:__imp_GetLastError
0x18012bbc3  mov     ebx, eax
0x18012bbc5  cmp     eax, 7Ah ; 'z'
0x18012bbc8  jz      short loc_18012BBCE
0x18012bbca  xor     edi, edi
0x18012bbcc  jmp     short loc_18012BC44
0x18012bbce  mov     ecx, [rsp+58h+TokenInformationLength]; Size
0x18012bbd2  call    cs:__imp_malloc
0x18012bbd8  mov     rdi, rax
0x18012bbdb  test    rax, rax
0x18012bbde  jnz     short loc_18012BBE7
0x18012bbe0  mov     ebx, 8007000Eh
0x18012bbe5  jmp     short loc_18012BC51
0x18012bbe7  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18012bbec  lea     rax, [rsp+58h+TokenInformationLength]
0x18012bbf1  mov     r8, rdi; TokenInformation
0x18012bbf4  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18012bbf9  mov     edx, 1; TokenInformationClass
0x18012bbfe  mov     rcx, rbp; TokenHandle
0x18012bc01  call    cs:__imp_GetTokenInformation
0x18012bc07  test    eax, eax
0x18012bc09  jz      short loc_18012BC3C
0x18012bc0b  mov     rcx, [rdi]; pSid
0x18012bc0e  call    cs:__imp_GetLengthSid
0x18012bc14  mov     ecx, eax; Size
0x18012bc16  mov     [rsp+58h+TokenInformationLength], ecx
0x18012bc1a  call    cs:__imp_malloc
0x18012bc20  mov     rbx, rax
0x18012bc23  test    rax, rax
0x18012bc26  jz      short loc_18012BBE0
0x18012bc28  mov     r8, [rdi]; pSourceSid
0x18012bc2b  mov     rdx, rax; pDestinationSid
0x18012bc2e  mov     ecx, [rsp+58h+TokenInformationLength]; nDestinationSidLength
0x18012bc32  call    cs:__imp_CopySid
0x18012bc38  test    eax, eax
0x18012bc3a  jnz     short loc_18012BC66
0x18012bc3c  call    cs:__imp_GetLastError
0x18012bc42  mov     ebx, eax
0x18012bc44  test    eax, eax
0x18012bc46  jle     short loc_18012BC51
0x18012bc48  movzx   ebx, ax
0x18012bc4b  or      ebx, 80070000h
0x18012bc51  mov     rcx, rdi; Block
0x18012bc54  call    cs:__imp_free
0x18012bc5a  xor     ecx, ecx; Block
0x18012bc5c  call    cs:__imp_free
0x18012bc62  mov     eax, ebx
0x18012bc64  jmp     short loc_18012BC74
0x18012bc66  mov     rcx, rdi; Block
0x18012bc69  mov     [rsi], rbx
0x18012bc6c  call    cs:__imp_free
0x18012bc72  xor     eax, eax
0x18012bc74  add     rsp, 38h
0x18012bc78  pop     rdi
0x18012bc79  pop     rsi
0x18012bc7a  pop     rbp
0x18012bc7b  pop     rbx
0x18012bc7c  retn
```
