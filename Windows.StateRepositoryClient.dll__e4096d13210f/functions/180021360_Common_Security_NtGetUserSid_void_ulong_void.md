# Common::Security::NtGetUserSid(void *,ulong *,void *)

- ea: `0x180021360`
- end: `0x1800213fb`
- name: `?NtGetUserSid@Security@Common@@YAJPEAXPEAK0@Z`
- size: `155`
- prototype: `int(Common::Security *__hidden this, void *, unsigned int *, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180021404`

## callees

- `0x180002980`
- `0x180021360`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x1800213b2`
- `ntdll!NtQueryInformationToken` at `0x1800213b2`
- `ntdll!RtlLengthSid` at `0x1800213d6`
- `ntdll!RtlLengthSid` at `0x1800213d6`
- `ntdll!RtlCopySid` at `0x1800213c9`
- `ntdll!RtlCopySid` at `0x1800213c9`

## pseudocode

```c
NTSTATUS __fastcall Common::Security::NtGetUserSid(__int64 this, ULONG *a2, unsigned int *a3, void *a4)
{
  NTSTATUS result; // eax
  PSID v7; // rbx
  ULONG ReturnLength[4]; // [rsp+30h] [rbp-98h] BYREF
  PSID TokenInformation[12]; // [rsp+40h] [rbp-88h] BYREF

  ReturnLength[0] = 0;
  if ( !this )
    this = -6;
  result = NtQueryInformationToken((HANDLE)this, TokenUser, TokenInformation, 0x54u, ReturnLength);
  if ( result >= 0 )
  {
    v7 = TokenInformation[0];
    result = RtlCopySid(*a2, a3, TokenInformation[0]);
    if ( result >= 0 )
    {
      *a2 = RtlLengthSid(v7);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180021360  push    rbx
0x180021362  push    rsi
0x180021363  push    rdi
0x180021364  sub     rsp, 0B0h
0x18002136b  mov     rax, cs:__security_cookie
0x180021372  xor     rax, rsp
0x180021375  mov     [rsp+0C8h+var_28], rax
0x18002137d  test    rcx, rcx
0x180021380  mov     [rsp+0C8h+var_98], 0
0x180021388  mov     r9d, 54h ; 'T'; TokenInformationLength
0x18002138e  mov     rax, 0FFFFFFFFFFFFFFFAh
0x180021395  cmovz   rcx, rax; TokenHandle
0x180021399  mov     rsi, r8
0x18002139c  lea     rax, [rsp+0C8h+var_98]
0x1800213a1  mov     rdi, rdx
0x1800213a4  lea     r8, [rsp+0C8h+TokenInformation]; TokenInformation
0x1800213a9  mov     [rsp+0C8h+ReturnLength], rax; ReturnLength
0x1800213ae  lea     edx, [r9-53h]; TokenInformationClass
0x1800213b2  call    cs:__imp_NtQueryInformationToken
0x1800213b8  test    eax, eax
0x1800213ba  js      short loc_1800213E0
0x1800213bc  mov     rbx, [rsp+0C8h+TokenInformation]
0x1800213c1  mov     rdx, rsi; DestinationSid
0x1800213c4  mov     ecx, [rdi]; DestinationSidLength
0x1800213c6  mov     r8, rbx; SourceSid
0x1800213c9  call    cs:__imp_RtlCopySid
0x1800213cf  test    eax, eax
0x1800213d1  js      short loc_1800213E0
0x1800213d3  mov     rcx, rbx; Sid
0x1800213d6  call    cs:__imp_RtlLengthSid
0x1800213dc  mov     [rdi], eax
0x1800213de  xor     eax, eax
0x1800213e0  mov     rcx, [rsp+0C8h+var_28]
0x1800213e8  xor     rcx, rsp; StackCookie
0x1800213eb  call    __security_check_cookie
0x1800213f0  add     rsp, 0B0h
0x1800213f7  pop     rdi
0x1800213f8  pop     rsi
0x1800213f9  pop     rbx
0x1800213fa  retn
```
