# GetUserSidFromToken

- ea: `0x18006c7c8`
- end: `0x18006c908`
- name: `GetUserSidFromToken`
- size: `320`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180069b30`
- `0x180069ef0`
- `0x18006a150`
- `0x18006a680`
- `0x18006c63c`
- `0x18006c910`

## callees

- `0x18006c7c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c811`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c811`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c822`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c8e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c8ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c8e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c8ef`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006c84c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006c8a6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006c84c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006c8a6`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18006c8c2`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18006c8c2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18006c894`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18006c894`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006c7f7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006c881`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006c7f7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006c881`

## pseudocode

```c
__int64 __fastcall GetUserSidFromToken(HANDLE TokenHandle, _QWORD *a2)
{
  PSID *v3; // rsi
  void *v5; // rdi
  unsigned int v6; // ebx
  signed int LastError; // eax
  DWORD LengthSid; // ebx
  HLOCAL v9; // rax
  DWORD TokenInformationLength; // [rsp+70h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  v3 = 0;
  v5 = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    v6 = -2147418113;
    goto LABEL_12;
  }
  if ( GetLastError() == 122 )
  {
    v3 = (PSID *)LocalAlloc(0, TokenInformationLength);
    if ( v3 )
    {
      if ( !GetTokenInformation(TokenHandle, TokenUser, v3, TokenInformationLength, &TokenInformationLength) )
        goto LABEL_4;
      LengthSid = GetLengthSid(*v3);
      v9 = LocalAlloc(0, LengthSid);
      v5 = v9;
      if ( v9 )
      {
        if ( CopySid(LengthSid, v9, *v3) )
        {
          v6 = 0;
          *a2 = v5;
          v5 = 0;
          goto LABEL_12;
        }
        goto LABEL_4;
      }
    }
    v6 = -2147024882;
    goto LABEL_12;
  }
LABEL_4:
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
LABEL_12:
  LocalFree(v5);
  LocalFree(v3);
  return v6;
}

```

## disassembly

```asm
0x18006c7c8  push    rbx
0x18006c7ca  push    rsi
0x18006c7cb  push    rdi
0x18006c7cc  push    r14
0x18006c7ce  sub     rsp, 38h
0x18006c7d2  mov     r14, rdx
0x18006c7d5  mov     [rsp+58h+TokenInformationLength], 0
0x18006c7dd  lea     rax, [rsp+58h+TokenInformationLength]
0x18006c7e2  xor     esi, esi
0x18006c7e4  xor     r9d, r9d; TokenInformationLength
0x18006c7e7  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18006c7ec  xor     r8d, r8d; TokenInformation
0x18006c7ef  mov     rbx, rcx
0x18006c7f2  xor     edi, edi
0x18006c7f4  lea     edx, [rsi+1]; TokenInformationClass
0x18006c7f7  call    cs:__imp_GetTokenInformation
0x18006c7fe  nop     dword ptr [rax+rax+00h]
0x18006c803  test    eax, eax
0x18006c805  jz      short loc_18006C811
0x18006c807  mov     ebx, 8000FFFFh
0x18006c80c  jmp     loc_18006C8DD
0x18006c811  call    cs:__imp_GetLastError
0x18006c818  nop     dword ptr [rax+rax+00h]
0x18006c81d  cmp     eax, 7Ah ; 'z'
0x18006c820  jz      short loc_18006C846
0x18006c822  call    cs:__imp_GetLastError
0x18006c829  nop     dword ptr [rax+rax+00h]
0x18006c82e  mov     ebx, eax
0x18006c830  test    eax, eax
0x18006c832  jle     loc_18006C8DD
0x18006c838  movzx   ebx, ax
0x18006c83b  or      ebx, 80070000h
0x18006c841  jmp     loc_18006C8DD
0x18006c846  mov     edx, [rsp+58h+TokenInformationLength]; uBytes
0x18006c84a  xor     ecx, ecx; uFlags
0x18006c84c  call    cs:__imp_LocalAlloc
0x18006c853  nop     dword ptr [rax+rax+00h]
0x18006c858  mov     rsi, rax
0x18006c85b  test    rax, rax
0x18006c85e  jnz     short loc_18006C867
0x18006c860  mov     ebx, 8007000Eh
0x18006c865  jmp     short loc_18006C8DD
0x18006c867  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18006c86c  lea     rax, [rsp+58h+TokenInformationLength]
0x18006c871  mov     r8, rsi; TokenInformation
0x18006c874  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18006c879  mov     edx, 1; TokenInformationClass
0x18006c87e  mov     rcx, rbx; TokenHandle
0x18006c881  call    cs:__imp_GetTokenInformation
0x18006c888  nop     dword ptr [rax+rax+00h]
0x18006c88d  test    eax, eax
0x18006c88f  jz      short loc_18006C822
0x18006c891  mov     rcx, [rsi]; pSid
0x18006c894  call    cs:__imp_GetLengthSid
0x18006c89b  nop     dword ptr [rax+rax+00h]
0x18006c8a0  mov     edx, eax; uBytes
0x18006c8a2  xor     ecx, ecx; uFlags
0x18006c8a4  mov     ebx, eax
0x18006c8a6  call    cs:__imp_LocalAlloc
0x18006c8ad  nop     dword ptr [rax+rax+00h]
0x18006c8b2  mov     rdi, rax
0x18006c8b5  test    rax, rax
0x18006c8b8  jz      short loc_18006C860
0x18006c8ba  mov     r8, [rsi]; pSourceSid
0x18006c8bd  mov     rdx, rax; pDestinationSid
0x18006c8c0  mov     ecx, ebx; nDestinationSidLength
0x18006c8c2  call    cs:__imp_CopySid
0x18006c8c9  nop     dword ptr [rax+rax+00h]
0x18006c8ce  test    eax, eax
0x18006c8d0  jz      loc_18006C822
0x18006c8d6  xor     ebx, ebx
0x18006c8d8  mov     [r14], rdi
0x18006c8db  xor     edi, edi
0x18006c8dd  mov     rcx, rdi; hMem
0x18006c8e0  call    cs:__imp_LocalFree
0x18006c8e7  nop     dword ptr [rax+rax+00h]
0x18006c8ec  mov     rcx, rsi; hMem
0x18006c8ef  call    cs:__imp_LocalFree
0x18006c8f6  nop     dword ptr [rax+rax+00h]
0x18006c8fb  mov     eax, ebx
0x18006c8fd  add     rsp, 38h
0x18006c901  pop     r14
0x18006c903  pop     rdi
0x18006c904  pop     rsi
0x18006c905  pop     rbx
0x18006c906  retn
```
