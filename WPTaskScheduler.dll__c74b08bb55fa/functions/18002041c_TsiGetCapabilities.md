# TsiGetCapabilities

- ea: `0x18002041c`
- end: `0x1800204f5`
- name: `TsiGetCapabilities`
- size: `217`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004db0`

## callees

- `0x180010208`
- `0x18002041c`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800204bf`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800204bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020469`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800204ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020469`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800204ce`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002045f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800204ad`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002045f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800204ad`

## pseudocode

```c
__int64 __fastcall TsiGetCapabilities(_QWORD *a1, void *a2)
{
  unsigned int v4; // ebx
  void *v5; // rdi
  signed int LastError; // eax
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF

  TokenInformationLength = 0;
  if ( a1 )
  {
    if ( GetTokenInformation(a2, TokenCapabilities, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v5 = operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
      if ( v5 )
      {
        if ( GetTokenInformation(a2, TokenCapabilities, v5, TokenInformationLength, &TokenInformationLength) )
        {
          *a1 = v5;
          return 0;
        }
        else
        {
          v4 = -2147467259;
          operator delete[](v5);
        }
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v4;
}

```

## disassembly

```asm
0x18002041c  mov     [rsp+arg_8], rbx
0x180020421  mov     [rsp+arg_10], rsi
0x180020426  push    rdi
0x180020427  sub     rsp, 30h
0x18002042b  mov     [rsp+38h+TokenInformationLength], 0
0x180020433  mov     rsi, rdx
0x180020436  mov     rbx, rcx
0x180020439  test    rcx, rcx
0x18002043c  jnz     short loc_180020448
0x18002043e  mov     ebx, 80004003h
0x180020443  jmp     loc_1800204E3
0x180020448  xor     r9d, r9d; TokenInformationLength
0x18002044b  lea     rax, [rsp+38h+TokenInformationLength]
0x180020450  xor     r8d, r8d; TokenInformation
0x180020453  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180020458  mov     rcx, rsi; TokenHandle
0x18002045b  lea     edx, [r9+1Eh]; TokenInformationClass
0x18002045f  call    cs:__imp_GetTokenInformation
0x180020465  test    eax, eax
0x180020467  jnz     short loc_1800204CE
0x180020469  call    cs:__imp_GetLastError
0x18002046f  cmp     eax, 7Ah ; 'z'
0x180020472  jnz     short loc_1800204CE
0x180020474  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x180020478  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002047f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180020484  mov     rdi, rax
0x180020487  test    rax, rax
0x18002048a  jnz     short loc_180020493
0x18002048c  mov     ebx, 8007000Eh
0x180020491  jmp     short loc_1800204E3
0x180020493  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180020498  lea     rax, [rsp+38h+TokenInformationLength]
0x18002049d  mov     r8, rdi; TokenInformation
0x1800204a0  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800204a5  mov     edx, 1Eh; TokenInformationClass
0x1800204aa  mov     rcx, rsi; TokenHandle
0x1800204ad  call    cs:__imp_GetTokenInformation
0x1800204b3  test    eax, eax
0x1800204b5  jnz     short loc_1800204C7
0x1800204b7  mov     rcx, rdi
0x1800204ba  mov     ebx, 80004005h
0x1800204bf  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800204c5  jmp     short loc_1800204E3
0x1800204c7  mov     [rbx], rdi
0x1800204ca  xor     ebx, ebx
0x1800204cc  jmp     short loc_1800204E3
0x1800204ce  call    cs:__imp_GetLastError
0x1800204d4  mov     ebx, eax
0x1800204d6  test    eax, eax
0x1800204d8  jle     short loc_1800204E3
0x1800204da  movzx   ebx, ax
0x1800204dd  or      ebx, 80070000h
0x1800204e3  mov     rsi, [rsp+38h+arg_10]
0x1800204e8  mov     eax, ebx
0x1800204ea  mov     rbx, [rsp+38h+arg_8]
0x1800204ef  add     rsp, 30h
0x1800204f3  pop     rdi
0x1800204f4  retn
```
