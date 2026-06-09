# LUAIsElevatedTokenEx

- ea: `0x18000b3d8`
- end: `0x18000b5df`
- name: `LUAIsElevatedTokenEx`
- size: `519`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, _DWORD *, _DWORD *, _DWORD *, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003efc`

## callees

- `0x18000b32c`
- `0x18000b3d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b47f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b47f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b5c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b5c6`
- `ntdll!NtQueryInformationToken` at `0x18000b460`
- `ntdll!NtQueryInformationToken` at `0x18000b4b5`
- `ntdll!NtQueryInformationToken` at `0x18000b460`
- `ntdll!NtQueryInformationToken` at `0x18000b4b5`
- `ntdll!RtlCompareUnicodeString` at `0x18000b4f9`
- `ntdll!RtlCompareUnicodeString` at `0x18000b521`
- `ntdll!RtlCompareUnicodeString` at `0x18000b545`
- `ntdll!RtlCompareUnicodeString` at `0x18000b575`
- `ntdll!RtlCompareUnicodeString` at `0x18000b4f9`
- `ntdll!RtlCompareUnicodeString` at `0x18000b521`
- `ntdll!RtlCompareUnicodeString` at `0x18000b545`
- `ntdll!RtlCompareUnicodeString` at `0x18000b575`

## pseudocode

```c
__int64 __fastcall LUAIsElevatedTokenEx(HANDLE TokenHandle, _DWORD *a2, _DWORD *a3, _DWORD *a4, __int64 a5, _DWORD *a6)
{
  _DWORD *v6; // r14
  int v7; // r13d
  _DWORD *v12; // rsi
  NTSTATUS v13; // ebx
  HLOCAL v14; // rdi
  __int64 v15; // rbp
  int v16; // r12d
  __int64 v17; // rax
  ULONG TokenInformationLength; // [rsp+98h] [rbp+20h] BYREF

  v6 = (_DWORD *)a5;
  v7 = 0;
  TokenInformationLength = 0;
  *a4 = 0;
  if ( v6 )
    *v6 = 0;
  v12 = a6;
  if ( a6 )
    *a6 = 0;
  v13 = LUAIsElevatedToken(TokenHandle);
  if ( v13 >= 0 )
  {
    if ( *a2 )
    {
      if ( *a3 )
      {
        v13 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, 0, 0, &TokenInformationLength);
        if ( v13 == -1073741789 )
        {
          v14 = LocalAlloc(0x40u, TokenInformationLength);
          if ( v14 )
          {
            v13 = NtQueryInformationToken(
                    TokenHandle,
                    TokenSecurityAttributes,
                    v14,
                    TokenInformationLength,
                    &TokenInformationLength);
            if ( v13 >= 0 )
            {
              v15 = 0;
              v16 = 0;
              while ( (unsigned int)v15 < *((_DWORD *)v14 + 1) )
              {
                v17 = *((_QWORD *)v14 + 1);
                a5 = 5 * v15;
                if ( !RtlCompareUnicodeString(&String1, (PCUNICODE_STRING)(v17 + 40 * v15), 1u) )
                {
                  v7 = 1;
LABEL_23:
                  *a4 = 1;
                  break;
                }
                if ( !RtlCompareUnicodeString(&stru_18000DC18, (PCUNICODE_STRING)(*((_QWORD *)v14 + 1) + 8 * a5), 1u) )
                  goto LABEL_23;
                if ( RtlCompareUnicodeString(&stru_18000DBF8, (PCUNICODE_STRING)(*((_QWORD *)v14 + 1) + 8 * a5), 1u) )
                {
                  if ( !RtlCompareUnicodeString(&stru_18000DC08, (PCUNICODE_STRING)(*((_QWORD *)v14 + 1) + 8 * a5), 1u) )
                    v16 = 1;
                }
                else
                {
                  v7 = 1;
                  v16 = 1;
                }
                v15 = (unsigned int)(v15 + 1);
              }
              if ( v6 && v16 && !*a4 )
                *v6 = 1;
              if ( v12 && v7 )
                *v12 = 1;
            }
            LocalFree(v14);
          }
          else
          {
            return (unsigned int)-1073741801;
          }
        }
      }
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000b3d8  mov     rax, rsp
0x18000b3db  push    rbx
0x18000b3dc  push    rbp
0x18000b3dd  push    rsi
0x18000b3de  push    rdi
0x18000b3df  push    r12
0x18000b3e1  push    r13
0x18000b3e3  push    r14
0x18000b3e5  push    r15
0x18000b3e7  sub     rsp, 38h
0x18000b3eb  mov     r14, [rsp+78h+arg_20]
0x18000b3f3  xor     r13d, r13d
0x18000b3f6  mov     [rax+20h], r13d
0x18000b3fa  mov     r15, r9
0x18000b3fd  mov     [r9], r13d
0x18000b400  mov     rdi, r8
0x18000b403  mov     r12, rdx
0x18000b406  mov     rbp, rcx
0x18000b409  test    r14, r14
0x18000b40c  jz      short loc_18000B411
0x18000b40e  mov     [r14], r13d
0x18000b411  mov     rsi, [rsp+78h+arg_28]
0x18000b419  test    rsi, rsi
0x18000b41c  jz      short loc_18000B421
0x18000b41e  mov     [rsi], r13d
0x18000b421  call    LUAIsElevatedToken
0x18000b426  mov     ebx, eax
0x18000b428  test    eax, eax
0x18000b42a  js      loc_18000B5CC
0x18000b430  cmp     [r12], r13d
0x18000b434  jz      loc_18000B5CC
0x18000b43a  cmp     [rdi], r13d
0x18000b43d  jz      loc_18000B5CC
0x18000b443  xor     r9d, r9d; TokenInformationLength
0x18000b446  lea     rax, [rsp+78h+TokenInformationLength]
0x18000b44e  xor     r8d, r8d; TokenInformation
0x18000b451  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x18000b456  mov     rcx, rbp; TokenHandle
0x18000b459  lea     r12d, [r9+27h]
0x18000b45d  mov     edx, r12d; TokenInformationClass
0x18000b460  call    cs:__imp_NtQueryInformationToken
0x18000b466  mov     ebx, eax
0x18000b468  cmp     eax, 0C0000023h
0x18000b46d  jnz     loc_18000B5CC
0x18000b473  mov     edx, [rsp+78h+TokenInformationLength]; uBytes
0x18000b47a  lea     ecx, [r12+19h]; uFlags
0x18000b47f  call    cs:__imp_LocalAlloc
0x18000b485  mov     rdi, rax
0x18000b488  test    rax, rax
0x18000b48b  jnz     short loc_18000B497
0x18000b48d  mov     ebx, 0C0000017h
0x18000b492  jmp     loc_18000B5CC
0x18000b497  mov     r9d, [rsp+78h+TokenInformationLength]; TokenInformationLength
0x18000b49f  lea     rax, [rsp+78h+TokenInformationLength]
0x18000b4a7  mov     r8, rdi; TokenInformation
0x18000b4aa  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x18000b4af  mov     edx, r12d; TokenInformationClass
0x18000b4b2  mov     rcx, rbp; TokenHandle
0x18000b4b5  call    cs:__imp_NtQueryInformationToken
0x18000b4bb  mov     ebx, eax
0x18000b4bd  test    eax, eax
0x18000b4bf  js      loc_18000B5C3
0x18000b4c5  xor     ebp, ebp
0x18000b4c7  mov     r12d, r13d
0x18000b4ca  lea     r8d, [rbp+1]; CaseInsensitive
0x18000b4ce  cmp     ebp, [rdi+4]
0x18000b4d1  jnb     loc_18000B5A3
0x18000b4d7  mov     rax, [rdi+8]
0x18000b4db  lea     rcx, ds:0[rbp*4]
0x18000b4e3  add     rcx, rbp
0x18000b4e6  mov     [rsp+78h+arg_20], rcx
0x18000b4ee  lea     rdx, [rax+rcx*8]; String2
0x18000b4f2  lea     rcx, String1; String1
0x18000b4f9  call    cs:__imp_RtlCompareUnicodeString
0x18000b4ff  test    eax, eax
0x18000b501  jz      loc_18000B597
0x18000b507  mov     rax, [rdi+8]
0x18000b50b  mov     r8b, 1; CaseInsensitive
0x18000b50e  mov     rcx, [rsp+78h+arg_20]
0x18000b516  lea     rdx, [rax+rcx*8]; String2
0x18000b51a  lea     rcx, stru_18000DC18; String1
0x18000b521  call    cs:__imp_RtlCompareUnicodeString
0x18000b527  test    eax, eax
0x18000b529  jz      short loc_18000B58F
0x18000b52b  mov     rax, [rdi+8]
0x18000b52f  mov     r8b, 1; CaseInsensitive
0x18000b532  mov     rcx, [rsp+78h+arg_20]
0x18000b53a  lea     rdx, [rax+rcx*8]; String2
0x18000b53e  lea     rcx, stru_18000DBF8; String1
0x18000b545  call    cs:__imp_RtlCompareUnicodeString
0x18000b54b  test    eax, eax
0x18000b54d  jnz     short loc_18000B55B
0x18000b54f  lea     r8d, [rax+1]
0x18000b553  mov     r13d, r8d
0x18000b556  mov     r12d, r8d
0x18000b559  jmp     short loc_18000B587
0x18000b55b  mov     rax, [rdi+8]
0x18000b55f  mov     r8b, 1; CaseInsensitive
0x18000b562  mov     rcx, [rsp+78h+arg_20]
0x18000b56a  lea     rdx, [rax+rcx*8]; String2
0x18000b56e  lea     rcx, stru_18000DC08; String1
0x18000b575  call    cs:__imp_RtlCompareUnicodeString
0x18000b57b  test    eax, eax
0x18000b57d  mov     r8d, 1
0x18000b583  cmovz   r12d, r8d
0x18000b587  add     ebp, r8d
0x18000b58a  jmp     loc_18000B4CE
0x18000b58f  mov     r8d, 1
0x18000b595  jmp     short loc_18000B5A0
0x18000b597  mov     r8d, 1
0x18000b59d  mov     r13d, r8d
0x18000b5a0  mov     [r15], r8d
0x18000b5a3  test    r14, r14
0x18000b5a6  jz      short loc_18000B5B6
0x18000b5a8  test    r12d, r12d
0x18000b5ab  jz      short loc_18000B5B6
0x18000b5ad  cmp     dword ptr [r15], 0
0x18000b5b1  jnz     short loc_18000B5B6
0x18000b5b3  mov     [r14], r8d
0x18000b5b6  test    rsi, rsi
0x18000b5b9  jz      short loc_18000B5C3
0x18000b5bb  test    r13d, r13d
0x18000b5be  jz      short loc_18000B5C3
0x18000b5c0  mov     [rsi], r8d
0x18000b5c3  mov     rcx, rdi; hMem
0x18000b5c6  call    cs:__imp_LocalFree
0x18000b5cc  mov     eax, ebx
0x18000b5ce  add     rsp, 38h
0x18000b5d2  pop     r15
0x18000b5d4  pop     r14
0x18000b5d6  pop     r13
0x18000b5d8  pop     r12
0x18000b5da  pop     rdi
0x18000b5db  pop     rsi
0x18000b5dc  pop     rbp
0x18000b5dd  pop     rbx
0x18000b5de  retn
```
