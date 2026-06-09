# AiQueryUserSid

- ea: `0x140035b60`
- end: `0x140035c3c`
- name: `AiQueryUserSid`
- size: `220`
- prototype: `NTSTATUS __fastcall(HANDLE TokenHandle, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140031d90`
- `0x140032420`

## callees

- `0x140035b60`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140035b8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035c18`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035b8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035c18`
- `ntoskrnl!ExAllocatePool2` at `0x140035bb4`
- `ntoskrnl!ExAllocatePool2` at `0x140035bb4`
- `ntoskrnl!ZwQueryInformationToken` at `0x140035be2`
- `ntoskrnl!ZwQueryInformationToken` at `0x140035be2`

## pseudocode

```c
NTSTATUS __fastcall AiQueryUserSid(HANDLE TokenHandle, _QWORD *a2)
{
  void *Pool2; // rbx
  ULONG v3; // r9d
  NTSTATUS result; // eax
  NTSTATUS v7; // edi
  ULONG TokenInformationLength; // [rsp+50h] [rbp+18h] BYREF

  Pool2 = 0;
  v3 = 0;
  for ( TokenInformationLength = 0; ; v3 = TokenInformationLength )
  {
    if ( Pool2 )
    {
      ExFreePoolWithTag(Pool2, 0);
      v3 = TokenInformationLength;
      Pool2 = 0;
    }
    if ( v3 )
    {
      Pool2 = (void *)ExAllocatePool2(258, v3, 1145663553);
      if ( !Pool2 )
        return -1073741801;
      v3 = TokenInformationLength;
    }
    result = ZwQueryInformationToken(TokenHandle, TokenUser, Pool2, v3, &TokenInformationLength);
    v7 = result;
    if ( result != -1073741789 )
      break;
  }
  if ( result < 0 )
  {
    if ( Pool2 )
    {
      ExFreePoolWithTag(Pool2, 0);
      return v7;
    }
  }
  else
  {
    *a2 = Pool2;
  }
  return result;
}

```

## disassembly

```asm
0x140035b60  mov     [rsp+arg_8], rbx
0x140035b65  mov     [rsp+arg_18], rbp
0x140035b6a  push    rsi
0x140035b6b  sub     rsp, 30h
0x140035b6f  xor     ebx, ebx
0x140035b71  mov     [rsp+38h+arg_0], rdi
0x140035b76  xor     r9d, r9d
0x140035b79  mov     rsi, rdx
0x140035b7c  mov     [rsp+38h+TokenInformationLength], r9d
0x140035b81  mov     rbp, rcx
0x140035b84  test    rbx, rbx
0x140035b87  jz      short loc_140035BA1
0x140035b89  xor     edx, edx; Tag
0x140035b8b  mov     rcx, rbx; P
0x140035b8e  call    cs:__imp_ExFreePoolWithTag
0x140035b95  nop     dword ptr [rax+rax+00h]
0x140035b9a  mov     r9d, [rsp+38h+TokenInformationLength]
0x140035b9f  xor     ebx, ebx
0x140035ba1  test    r9d, r9d
0x140035ba4  jz      short loc_140035BCD
0x140035ba6  mov     edx, r9d
0x140035ba9  mov     ecx, 102h
0x140035bae  mov     r8d, 44497041h
0x140035bb4  call    cs:__imp_ExAllocatePool2
0x140035bbb  nop     dword ptr [rax+rax+00h]
0x140035bc0  mov     rbx, rax
0x140035bc3  test    rax, rax
0x140035bc6  jz      short loc_140035BFE
0x140035bc8  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x140035bcd  lea     rax, [rsp+38h+TokenInformationLength]
0x140035bd2  mov     r8, rbx; TokenInformation
0x140035bd5  mov     edx, 1; TokenInformationClass
0x140035bda  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x140035bdf  mov     rcx, rbp; TokenHandle
0x140035be2  call    cs:__imp_ZwQueryInformationToken
0x140035be9  nop     dword ptr [rax+rax+00h]
0x140035bee  mov     edi, eax
0x140035bf0  cmp     eax, 0C0000023h
0x140035bf5  jnz     short loc_140035C05
0x140035bf7  mov     r9d, [rsp+38h+TokenInformationLength]
0x140035bfc  jmp     short loc_140035B84
0x140035bfe  mov     eax, 0C0000017h
0x140035c03  jmp     short loc_140035C26
0x140035c05  test    edi, edi
0x140035c07  js      short loc_140035C0E
0x140035c09  mov     [rsi], rbx
0x140035c0c  jmp     short loc_140035C26
0x140035c0e  test    rbx, rbx
0x140035c11  jz      short loc_140035C26
0x140035c13  xor     edx, edx; Tag
0x140035c15  mov     rcx, rbx; P
0x140035c18  call    cs:__imp_ExFreePoolWithTag
0x140035c1f  nop     dword ptr [rax+rax+00h]
0x140035c24  mov     eax, edi
0x140035c26  mov     rdi, [rsp+38h+arg_0]
0x140035c2b  mov     rbx, [rsp+38h+arg_8]
0x140035c30  mov     rbp, [rsp+38h+arg_18]
0x140035c35  add     rsp, 30h
0x140035c39  pop     rsi
0x140035c3a  retn
```
