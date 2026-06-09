# GetUserSid

- ea: `0x180025120`
- end: `0x180025216`
- name: `GetUserSid`
- size: `246`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180076a34`
- `0x1800aab28`

## callees

- `0x180025120`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025157`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800251e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800251e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025157`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800251e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800251e6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002514d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180025195`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002514d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180025195`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800251fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800251fe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002516d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002516d`

## pseudocode

```c
signed int __fastcall GetUserSid(HANDLE TokenHandle, _QWORD *a2)
{
  signed int result; // eax
  HLOCAL v5; // rbx
  signed int LastError; // eax
  unsigned int v7; // edi
  DWORD TokenInformationLength; // [rsp+50h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength)
    || (result = GetLastError(), result == 122) )
  {
    v5 = LocalAlloc(0, TokenInformationLength);
    if ( v5 )
    {
      if ( GetTokenInformation(TokenHandle, TokenUser, v5, TokenInformationLength, &TokenInformationLength) )
      {
        *a2 = v5;
        return 0;
      }
      else
      {
        GetLastError();
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        LocalFree(v5);
        return v7;
      }
    }
    else
    {
      return -2147024882;
    }
  }
  else if ( result > 0 )
  {
    return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180025120  mov     [rsp+arg_8], rsi
0x180025125  push    rdi
0x180025126  sub     rsp, 30h
0x18002512a  mov     rdi, rdx
0x18002512d  mov     [rsp+38h+TokenInformationLength], 0
0x180025135  lea     rax, [rsp+38h+TokenInformationLength]
0x18002513a  mov     edx, 1; TokenInformationClass
0x18002513f  xor     r9d, r9d; TokenInformationLength
0x180025142  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180025147  xor     r8d, r8d; TokenInformation
0x18002514a  mov     rsi, rcx
0x18002514d  call    cs:__imp_GetTokenInformation
0x180025153  test    eax, eax
0x180025155  jnz     short loc_180025162
0x180025157  call    cs:__imp_GetLastError
0x18002515d  cmp     eax, 7Ah ; 'z'
0x180025160  jnz     short loc_1800251C9
0x180025162  mov     edx, [rsp+38h+TokenInformationLength]; uBytes
0x180025166  xor     ecx, ecx; uFlags
0x180025168  mov     [rsp+38h+arg_0], rbx
0x18002516d  call    cs:__imp_LocalAlloc
0x180025173  mov     rbx, rax
0x180025176  test    rax, rax
0x180025179  jz      short loc_1800251B4
0x18002517b  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180025180  lea     rax, [rsp+38h+TokenInformationLength]
0x180025185  mov     r8, rbx; TokenInformation
0x180025188  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18002518d  mov     edx, 1; TokenInformationClass
0x180025192  mov     rcx, rsi; TokenHandle
0x180025195  call    cs:__imp_GetTokenInformation
0x18002519b  test    eax, eax
0x18002519d  jz      short loc_1800251E0
0x18002519f  mov     [rdi], rbx
0x1800251a2  xor     eax, eax
0x1800251a4  mov     rbx, [rsp+38h+arg_0]
0x1800251a9  mov     rsi, [rsp+38h+arg_8]
0x1800251ae  add     rsp, 30h
0x1800251b2  pop     rdi
0x1800251b3  retn
0x1800251b4  mov     rbx, [rsp+38h+arg_0]
0x1800251b9  mov     eax, 8007000Eh
0x1800251be  mov     rsi, [rsp+38h+arg_8]
0x1800251c3  add     rsp, 30h
0x1800251c7  pop     rdi
0x1800251c8  retn
0x1800251c9  test    eax, eax
0x1800251cb  jle     short loc_1800251A9
0x1800251cd  movzx   eax, ax
0x1800251d0  or      eax, 80070000h
0x1800251d5  mov     rsi, [rsp+38h+arg_8]
0x1800251da  add     rsp, 30h
0x1800251de  pop     rdi
0x1800251df  retn
0x1800251e0  call    cs:__imp_GetLastError
0x1800251e6  call    cs:__imp_GetLastError
0x1800251ec  mov     edi, eax
0x1800251ee  test    eax, eax
0x1800251f0  jle     short loc_1800251FB
0x1800251f2  movzx   edi, ax
0x1800251f5  or      edi, 80070000h
0x1800251fb  mov     rcx, rbx; hMem
0x1800251fe  call    cs:__imp_LocalFree
0x180025204  mov     rbx, [rsp+38h+arg_0]
0x180025209  mov     eax, edi
0x18002520b  mov     rsi, [rsp+38h+arg_8]
0x180025210  add     rsp, 30h
0x180025214  pop     rdi
0x180025215  retn
```
