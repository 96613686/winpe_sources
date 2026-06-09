# BampQueryProcessUserSidString

- ea: `0x140012368`
- end: `0x140012413`
- name: `BampQueryProcessUserSidString`
- size: `171`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140001670`
- `0x140001730`
- `0x14001474c`

## callees

- `0x140012368`

## import_xrefs

- `ntoskrnl!PsReferencePrimaryToken` at `0x140012383`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140012383`
- `ntoskrnl!ObfDereferenceObject` at `0x1400123f4`
- `ntoskrnl!ObfDereferenceObject` at `0x1400123f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400123e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400123e0`
- `ntoskrnl!SeQueryInformationToken` at `0x14001239f`
- `ntoskrnl!SeQueryInformationToken` at `0x14001239f`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x1400123bf`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x1400123bf`

## pseudocode

```c
__int64 __fastcall BampQueryProcessUserSidString(struct _KPROCESS *a1, struct _UNICODE_STRING *a2)
{
  PACCESS_TOKEN v3; // rdi
  NTSTATUS v4; // ebx
  PVOID TokenInformation; // [rsp+40h] [rbp+18h] BYREF

  TokenInformation = 0;
  v3 = PsReferencePrimaryToken(a1);
  v4 = SeQueryInformationToken(v3, TokenUser, &TokenInformation);
  if ( v4 >= 0 )
  {
    v4 = RtlConvertSidToUnicodeString(a2, *(PSID *)TokenInformation, 0);
    if ( v4 >= 0 )
      v4 = 0;
  }
  if ( TokenInformation )
    ExFreePoolWithTag(TokenInformation, 0);
  if ( v3 )
    ObfDereferenceObject(v3);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140012368  mov     [rsp+arg_0], rbx
0x14001236d  mov     [rsp+arg_8], rsi
0x140012372  push    rdi
0x140012373  sub     rsp, 20h
0x140012377  mov     rsi, rdx
0x14001237a  mov     [rsp+28h+TokenInformation], 0
0x140012383  call    cs:__imp_PsReferencePrimaryToken
0x14001238a  nop     dword ptr [rax+rax+00h]
0x14001238f  lea     r8, [rsp+28h+TokenInformation]; TokenInformation
0x140012394  mov     edx, 1; TokenInformationClass
0x140012399  mov     rcx, rax; Token
0x14001239c  mov     rdi, rax
0x14001239f  call    cs:__imp_SeQueryInformationToken
0x1400123a6  nop     dword ptr [rax+rax+00h]
0x1400123ab  mov     ebx, eax
0x1400123ad  test    eax, eax
0x1400123af  js      short loc_1400123D4
0x1400123b1  mov     rdx, [rsp+28h+TokenInformation]
0x1400123b6  xor     r8d, r8d; AllocateDestinationString
0x1400123b9  mov     rcx, rsi; UnicodeString
0x1400123bc  mov     rdx, [rdx]; Sid
0x1400123bf  call    cs:__imp_RtlConvertSidToUnicodeString
0x1400123c6  nop     dword ptr [rax+rax+00h]
0x1400123cb  mov     ebx, eax
0x1400123cd  xor     eax, eax
0x1400123cf  test    ebx, ebx
0x1400123d1  cmovns  ebx, eax
0x1400123d4  mov     rcx, [rsp+28h+TokenInformation]; P
0x1400123d9  test    rcx, rcx
0x1400123dc  jz      short loc_1400123EC
0x1400123de  xor     edx, edx; Tag
0x1400123e0  call    cs:__imp_ExFreePoolWithTag
0x1400123e7  nop     dword ptr [rax+rax+00h]
0x1400123ec  test    rdi, rdi
0x1400123ef  jz      short loc_140012400
0x1400123f1  mov     rcx, rdi; Object
0x1400123f4  call    cs:__imp_ObfDereferenceObject
0x1400123fb  nop     dword ptr [rax+rax+00h]
0x140012400  mov     rsi, [rsp+28h+arg_8]
0x140012405  mov     eax, ebx
0x140012407  mov     rbx, [rsp+28h+arg_0]
0x14001240c  add     rsp, 20h
0x140012410  pop     rdi
0x140012411  retn
```
