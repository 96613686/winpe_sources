# GetUserSid

- ea: `0x18005f314`
- end: `0x18005f40c`
- name: `GetUserSid`
- size: `248`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180053ae4`

## callees

- `0x18005f314`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f34f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f3c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f3cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f34f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f3c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f3cf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005f37e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005f37e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f3ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f3ed`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005f33f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005f3b3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005f33f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005f3b3`

## pseudocode

```c
__int64 __fastcall GetUserSid(HANDLE TokenHandle, _QWORD *a2)
{
  signed int v4; // eax
  unsigned int v5; // ebx
  HLOCAL v6; // rdi
  signed int LastError; // eax
  DWORD TokenInformationLength; // [rsp+70h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength)
    || (v4 = GetLastError(), v5 = v4, v4 == 122) )
  {
    v6 = LocalAlloc(0, TokenInformationLength);
    if ( v6 )
    {
      if ( GetTokenInformation(TokenHandle, TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
      {
        v5 = 0;
        *a2 = v6;
      }
      else
      {
        GetLastError();
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        LocalFree(v6);
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else if ( v4 > 0 )
  {
    return (unsigned __int16)v4 | 0x80070000;
  }
  return v5;
}

```

## disassembly

```asm
0x18005f314  push    rbx
0x18005f316  push    rbp
0x18005f317  push    rsi
0x18005f318  push    rdi
0x18005f319  sub     rsp, 38h
0x18005f31d  xor     r9d, r9d; TokenInformationLength
0x18005f320  mov     [rsp+58h+TokenInformationLength], 0
0x18005f328  mov     rsi, rdx
0x18005f32b  lea     rax, [rsp+58h+TokenInformationLength]
0x18005f330  xor     r8d, r8d; TokenInformation
0x18005f333  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18005f338  mov     rbp, rcx
0x18005f33b  lea     edx, [r9+1]; TokenInformationClass
0x18005f33f  call    cs:__imp_GetTokenInformation
0x18005f346  nop     dword ptr [rax+rax+00h]
0x18005f34b  test    eax, eax
0x18005f34d  jnz     short loc_18005F378
0x18005f34f  call    cs:__imp_GetLastError
0x18005f356  nop     dword ptr [rax+rax+00h]
0x18005f35b  mov     ebx, eax
0x18005f35d  cmp     eax, 7Ah ; 'z'
0x18005f360  jz      short loc_18005F378
0x18005f362  test    eax, eax
0x18005f364  jle     loc_18005F400
0x18005f36a  movzx   ebx, ax
0x18005f36d  or      ebx, 80070000h
0x18005f373  jmp     loc_18005F400
0x18005f378  mov     edx, [rsp+58h+TokenInformationLength]; uBytes
0x18005f37c  xor     ecx, ecx; uFlags
0x18005f37e  call    cs:__imp_LocalAlloc
0x18005f385  nop     dword ptr [rax+rax+00h]
0x18005f38a  mov     rdi, rax
0x18005f38d  test    rax, rax
0x18005f390  jnz     short loc_18005F399
0x18005f392  mov     ebx, 8007000Eh
0x18005f397  jmp     short loc_18005F400
0x18005f399  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18005f39e  lea     rax, [rsp+58h+TokenInformationLength]
0x18005f3a3  mov     r8, rdi; TokenInformation
0x18005f3a6  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18005f3ab  mov     edx, 1; TokenInformationClass
0x18005f3b0  mov     rcx, rbp; TokenHandle
0x18005f3b3  call    cs:__imp_GetTokenInformation
0x18005f3ba  nop     dword ptr [rax+rax+00h]
0x18005f3bf  test    eax, eax
0x18005f3c1  jnz     short loc_18005F3FB
0x18005f3c3  call    cs:__imp_GetLastError
0x18005f3ca  nop     dword ptr [rax+rax+00h]
0x18005f3cf  call    cs:__imp_GetLastError
0x18005f3d6  nop     dword ptr [rax+rax+00h]
0x18005f3db  mov     ebx, eax
0x18005f3dd  test    eax, eax
0x18005f3df  jle     short loc_18005F3EA
0x18005f3e1  movzx   ebx, ax
0x18005f3e4  or      ebx, 80070000h
0x18005f3ea  mov     rcx, rdi; hMem
0x18005f3ed  call    cs:__imp_LocalFree
0x18005f3f4  nop     dword ptr [rax+rax+00h]
0x18005f3f9  jmp     short loc_18005F400
0x18005f3fb  xor     ebx, ebx
0x18005f3fd  mov     [rsi], rdi
0x18005f400  mov     eax, ebx
0x18005f402  add     rsp, 38h
0x18005f406  pop     rdi
0x18005f407  pop     rsi
0x18005f408  pop     rbp
0x18005f409  pop     rbx
0x18005f40a  retn
```
