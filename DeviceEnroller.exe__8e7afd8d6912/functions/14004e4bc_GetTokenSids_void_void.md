# GetTokenSids(void *,void * *)

- ea: `0x14004e4bc`
- end: `0x14004e5bd`
- name: `?GetTokenSids@@YAJPEAXPEAPEAX@Z`
- size: `257`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004e8d4`

## callees

- `0x14004e4bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14004e594`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14004e59c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14004e5ac`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14004e594`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14004e59c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14004e5ac`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14004e512`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14004e55a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14004e512`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14004e55a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e4fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e57c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e4fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e57c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14004e54e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14004e54e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14004e4f7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14004e541`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14004e4f7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14004e541`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14004e572`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14004e572`

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
0x14004e4bc  push    rbx
0x14004e4be  push    rbp
0x14004e4bf  push    rsi
0x14004e4c0  push    rdi
0x14004e4c1  sub     rsp, 38h
0x14004e4c5  mov     [rsp+58h+TokenInformationLength], 0
0x14004e4cd  mov     rsi, rdx
0x14004e4d0  mov     rbp, rcx
0x14004e4d3  test    rdx, rdx
0x14004e4d6  jz      loc_14004E5B2
0x14004e4dc  xor     r9d, r9d; TokenInformationLength
0x14004e4df  mov     qword ptr [rdx], 0
0x14004e4e6  lea     rax, [rsp+58h+TokenInformationLength]
0x14004e4eb  xor     r8d, r8d; TokenInformation
0x14004e4ee  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x14004e4f3  lea     edx, [r9+1]; TokenInformationClass
0x14004e4f7  call    cs:__imp_GetTokenInformation
0x14004e4fd  call    cs:__imp_GetLastError
0x14004e503  mov     ebx, eax
0x14004e505  cmp     eax, 7Ah ; 'z'
0x14004e508  jz      short loc_14004E50E
0x14004e50a  xor     edi, edi
0x14004e50c  jmp     short loc_14004E584
0x14004e50e  mov     ecx, [rsp+58h+TokenInformationLength]; Size
0x14004e512  call    cs:__imp_malloc
0x14004e518  mov     rdi, rax
0x14004e51b  test    rax, rax
0x14004e51e  jnz     short loc_14004E527
0x14004e520  mov     ebx, 8007000Eh
0x14004e525  jmp     short loc_14004E591
0x14004e527  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x14004e52c  lea     rax, [rsp+58h+TokenInformationLength]
0x14004e531  mov     r8, rdi; TokenInformation
0x14004e534  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x14004e539  mov     edx, 1; TokenInformationClass
0x14004e53e  mov     rcx, rbp; TokenHandle
0x14004e541  call    cs:__imp_GetTokenInformation
0x14004e547  test    eax, eax
0x14004e549  jz      short loc_14004E57C
0x14004e54b  mov     rcx, [rdi]; pSid
0x14004e54e  call    cs:__imp_GetLengthSid
0x14004e554  mov     ecx, eax; Size
0x14004e556  mov     [rsp+58h+TokenInformationLength], ecx
0x14004e55a  call    cs:__imp_malloc
0x14004e560  mov     rbx, rax
0x14004e563  test    rax, rax
0x14004e566  jz      short loc_14004E520
0x14004e568  mov     r8, [rdi]; pSourceSid
0x14004e56b  mov     rdx, rax; pDestinationSid
0x14004e56e  mov     ecx, [rsp+58h+TokenInformationLength]; nDestinationSidLength
0x14004e572  call    cs:__imp_CopySid
0x14004e578  test    eax, eax
0x14004e57a  jnz     short loc_14004E5A6
0x14004e57c  call    cs:__imp_GetLastError
0x14004e582  mov     ebx, eax
0x14004e584  test    eax, eax
0x14004e586  jle     short loc_14004E591
0x14004e588  movzx   ebx, ax
0x14004e58b  or      ebx, 80070000h
0x14004e591  mov     rcx, rdi; Block
0x14004e594  call    cs:__imp_free
0x14004e59a  xor     ecx, ecx; Block
0x14004e59c  call    cs:__imp_free
0x14004e5a2  mov     eax, ebx
0x14004e5a4  jmp     short loc_14004E5B4
0x14004e5a6  mov     rcx, rdi; Block
0x14004e5a9  mov     [rsi], rbx
0x14004e5ac  call    cs:__imp_free
0x14004e5b2  xor     eax, eax
0x14004e5b4  add     rsp, 38h
0x14004e5b8  pop     rdi
0x14004e5b9  pop     rsi
0x14004e5ba  pop     rbp
0x14004e5bb  pop     rbx
0x14004e5bc  retn
```
