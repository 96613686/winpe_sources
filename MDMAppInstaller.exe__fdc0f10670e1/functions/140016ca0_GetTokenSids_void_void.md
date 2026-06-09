# GetTokenSids(void *,void * *)

- ea: `0x140016ca0`
- end: `0x140016da1`
- name: `?GetTokenSids@@YAJPEAXPEAPEAX@Z`
- size: `257`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140017a88`

## callees

- `0x140016ca0`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x140016cdb`
- `ADVAPI32!GetTokenInformation` at `0x140016d25`
- `ADVAPI32!GetTokenInformation` at `0x140016cdb`
- `ADVAPI32!GetTokenInformation` at `0x140016d25`
- `ADVAPI32!GetLengthSid` at `0x140016d32`
- `ADVAPI32!GetLengthSid` at `0x140016d32`
- `ADVAPI32!CopySid` at `0x140016d56`
- `ADVAPI32!CopySid` at `0x140016d56`
- `KERNEL32!GetLastError` at `0x140016ce1`
- `KERNEL32!GetLastError` at `0x140016d60`
- `KERNEL32!GetLastError` at `0x140016ce1`
- `KERNEL32!GetLastError` at `0x140016d60`
- `msvcrt!free` at `0x140016d78`
- `msvcrt!free` at `0x140016d80`
- `msvcrt!free` at `0x140016d90`
- `msvcrt!free` at `0x140016d78`
- `msvcrt!free` at `0x140016d80`
- `msvcrt!free` at `0x140016d90`
- `msvcrt!malloc` at `0x140016cf6`
- `msvcrt!malloc` at `0x140016d40`
- `msvcrt!malloc` at `0x140016cf6`
- `msvcrt!malloc` at `0x140016d40`

## pseudocode

```c
__int64 __fastcall GetTokenSids(HANDLE TokenHandle, void **a2)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  PSID *v6; // rdi
  DWORD LengthSid; // ebp
  void *v8; // rax
  void *v9; // rbx
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
    LengthSid = GetLengthSid(*v6);
    TokenInformationLength = LengthSid;
    v8 = malloc(LengthSid);
    v9 = v8;
    if ( !v8 )
      goto LABEL_5;
    if ( !CopySid(LengthSid, v8, *v6) )
    {
LABEL_9:
      LastError = GetLastError();
      v5 = LastError;
LABEL_10:
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_12;
    }
    *a2 = v9;
    free(v6);
  }
  return 0;
}

```

## disassembly

```asm
0x140016ca0  push    rbx
0x140016ca2  push    rbp
0x140016ca3  push    rsi
0x140016ca4  push    rdi
0x140016ca5  sub     rsp, 38h
0x140016ca9  mov     [rsp+58h+TokenInformationLength], 0
0x140016cb1  mov     rsi, rdx
0x140016cb4  mov     rbp, rcx
0x140016cb7  test    rdx, rdx
0x140016cba  jz      loc_140016D96
0x140016cc0  xor     r9d, r9d; TokenInformationLength
0x140016cc3  mov     qword ptr [rdx], 0
0x140016cca  lea     rax, [rsp+58h+TokenInformationLength]
0x140016ccf  xor     r8d, r8d; TokenInformation
0x140016cd2  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x140016cd7  lea     edx, [r9+1]; TokenInformationClass
0x140016cdb  call    cs:__imp_GetTokenInformation
0x140016ce1  call    cs:__imp_GetLastError
0x140016ce7  mov     ebx, eax
0x140016ce9  cmp     eax, 7Ah ; 'z'
0x140016cec  jz      short loc_140016CF2
0x140016cee  xor     edi, edi
0x140016cf0  jmp     short loc_140016D68
0x140016cf2  mov     ecx, [rsp+58h+TokenInformationLength]; Size
0x140016cf6  call    cs:__imp_malloc
0x140016cfc  mov     rdi, rax
0x140016cff  test    rax, rax
0x140016d02  jnz     short loc_140016D0B
0x140016d04  mov     ebx, 8007000Eh
0x140016d09  jmp     short loc_140016D75
0x140016d0b  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x140016d10  lea     rax, [rsp+58h+TokenInformationLength]
0x140016d15  mov     r8, rdi; TokenInformation
0x140016d18  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x140016d1d  mov     edx, 1; TokenInformationClass
0x140016d22  mov     rcx, rbp; TokenHandle
0x140016d25  call    cs:__imp_GetTokenInformation
0x140016d2b  test    eax, eax
0x140016d2d  jz      short loc_140016D60
0x140016d2f  mov     rcx, [rdi]; pSid
0x140016d32  call    cs:__imp_GetLengthSid
0x140016d38  mov     ebp, eax
0x140016d3a  mov     ecx, eax; Size
0x140016d3c  mov     [rsp+58h+TokenInformationLength], ebp
0x140016d40  call    cs:__imp_malloc
0x140016d46  mov     rbx, rax
0x140016d49  test    rax, rax
0x140016d4c  jz      short loc_140016D04
0x140016d4e  mov     r8, [rdi]; pSourceSid
0x140016d51  mov     rdx, rax; pDestinationSid
0x140016d54  mov     ecx, ebp; nDestinationSidLength
0x140016d56  call    cs:__imp_CopySid
0x140016d5c  test    eax, eax
0x140016d5e  jnz     short loc_140016D8A
0x140016d60  call    cs:__imp_GetLastError
0x140016d66  mov     ebx, eax
0x140016d68  test    eax, eax
0x140016d6a  jle     short loc_140016D75
0x140016d6c  movzx   ebx, ax
0x140016d6f  or      ebx, 80070000h
0x140016d75  mov     rcx, rdi; Block
0x140016d78  call    cs:__imp_free
0x140016d7e  xor     ecx, ecx; Block
0x140016d80  call    cs:__imp_free
0x140016d86  mov     eax, ebx
0x140016d88  jmp     short loc_140016D98
0x140016d8a  mov     rcx, rdi; Block
0x140016d8d  mov     [rsi], rbx
0x140016d90  call    cs:__imp_free
0x140016d96  xor     eax, eax
0x140016d98  add     rsp, 38h
0x140016d9c  pop     rdi
0x140016d9d  pop     rsi
0x140016d9e  pop     rbp
0x140016d9f  pop     rbx
0x140016da0  retn
```
