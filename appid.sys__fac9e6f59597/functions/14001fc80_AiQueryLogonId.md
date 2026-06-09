# AiQueryLogonId

- ea: `0x14001fc80`
- end: `0x14001fd4f`
- name: `AiQueryLogonId`
- size: `207`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140031d90`

## callees

- `0x14001fc80`
- `0x140032a50`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001fcb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fd2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fcb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fd2b`
- `ntoskrnl!ZwQueryInformationToken` at `0x14001fcf3`
- `ntoskrnl!ZwQueryInformationToken` at `0x14001fcf3`

## pseudocode

```c
__int64 __fastcall AiQueryLogonId(HANDLE TokenHandle, _QWORD *a2)
{
  ULONG v2; // r9d
  _QWORD *v5; // rbx
  NTSTATUS v6; // ebp
  ULONG TokenInformationLength; // [rsp+50h] [rbp+18h] BYREF

  v2 = 56;
  TokenInformationLength = 56;
  v5 = 0;
  while ( 1 )
  {
    if ( v5 )
    {
      ExFreePoolWithTag(v5, 0);
      v2 = TokenInformationLength;
    }
    v5 = 0;
    if ( v2 )
    {
      v5 = (_QWORD *)AiAlloc(v2);
      if ( !v5 )
        return 3221225495LL;
      v2 = TokenInformationLength;
    }
    v6 = ZwQueryInformationToken(TokenHandle, TokenGroupsAndPrivileges, v5, v2, &TokenInformationLength);
    if ( v6 != -1073741789 )
      break;
    v2 = TokenInformationLength;
  }
  if ( v6 >= 0 )
    *a2 = v5[6];
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14001fc80  mov     [rsp+arg_8], rbx
0x14001fc85  mov     [rsp+arg_18], rsi
0x14001fc8a  push    rdi
0x14001fc8b  sub     rsp, 30h
0x14001fc8f  mov     r9d, 38h ; '8'
0x14001fc95  mov     [rsp+38h+arg_0], rbp
0x14001fc9a  mov     [rsp+38h+TokenInformationLength], r9d
0x14001fc9f  mov     rdi, rdx
0x14001fca2  mov     rsi, rcx
0x14001fca5  xor     ebx, ebx
0x14001fca7  test    rbx, rbx
0x14001fcaa  jz      short loc_14001FCC2
0x14001fcac  xor     edx, edx; Tag
0x14001fcae  mov     rcx, rbx; P
0x14001fcb1  call    cs:__imp_ExFreePoolWithTag
0x14001fcb8  nop     dword ptr [rax+rax+00h]
0x14001fcbd  mov     r9d, [rsp+38h+TokenInformationLength]
0x14001fcc2  xor     ebx, ebx
0x14001fcc4  test    r9d, r9d
0x14001fcc7  jz      short loc_14001FCDE
0x14001fcc9  mov     ecx, r9d
0x14001fccc  call    AiAlloc
0x14001fcd1  mov     rbx, rax
0x14001fcd4  test    rax, rax
0x14001fcd7  jz      short loc_14001FD0F
0x14001fcd9  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x14001fcde  lea     rax, [rsp+38h+TokenInformationLength]
0x14001fce3  mov     r8, rbx; TokenInformation
0x14001fce6  mov     edx, 0Dh; TokenInformationClass
0x14001fceb  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x14001fcf0  mov     rcx, rsi; TokenHandle
0x14001fcf3  call    cs:__imp_ZwQueryInformationToken
0x14001fcfa  nop     dword ptr [rax+rax+00h]
0x14001fcff  mov     ebp, eax
0x14001fd01  cmp     eax, 0C0000023h
0x14001fd06  jnz     short loc_14001FD16
0x14001fd08  mov     r9d, [rsp+38h+TokenInformationLength]
0x14001fd0d  jmp     short loc_14001FCA7
0x14001fd0f  mov     eax, 0C0000017h
0x14001fd14  jmp     short loc_14001FD39
0x14001fd16  test    ebp, ebp
0x14001fd18  js      short loc_14001FD21
0x14001fd1a  mov     rax, [rbx+30h]
0x14001fd1e  mov     [rdi], rax
0x14001fd21  test    rbx, rbx
0x14001fd24  jz      short loc_14001FD37
0x14001fd26  xor     edx, edx; Tag
0x14001fd28  mov     rcx, rbx; P
0x14001fd2b  call    cs:__imp_ExFreePoolWithTag
0x14001fd32  nop     dword ptr [rax+rax+00h]
0x14001fd37  mov     eax, ebp
0x14001fd39  mov     rbp, [rsp+38h+arg_0]
0x14001fd3e  mov     rbx, [rsp+38h+arg_8]
0x14001fd43  mov     rsi, [rsp+38h+arg_18]
0x14001fd48  add     rsp, 30h
0x14001fd4c  pop     rdi
0x14001fd4d  retn
```
