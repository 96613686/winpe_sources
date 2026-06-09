# _Windows::WCP::Implementation::Rtl::GetSystemSid_::_5_::_lambda_1_::operator()

- ea: `0x140025f7c`
- end: `0x140025fcf`
- name: `_Windows::WCP::Implementation::Rtl::GetSystemSid_::_5_::_lambda_1_::operator()`
- size: `83`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x140026ad4`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x140025fba`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140025fba`

## pseudocode

```c
PVOID *Windows::WCP::Implementation::Rtl::GetSystemSid_::_5_::_lambda_1_::operator()()
{
  qword_1400538D8 = 0;
  dword_14005378C = RtlAllocateAndInitializeSid(
                      (PSID_IDENTIFIER_AUTHORITY)&IdentifierAuthority,
                      1u,
                      0x12u,
                      0,
                      0,
                      0,
                      0,
                      0,
                      0,
                      0,
                      &qword_1400538D8);
  return &qword_1400538D8;
}

```

## disassembly

```asm
0x140025f7c  mov     rax, rsp
0x140025f7f  push    rbx
0x140025f80  sub     rsp, 60h
0x140025f84  xor     ecx, ecx
0x140025f86  lea     rbx, qword_1400538D8
0x140025f8d  mov     [rax-18h], rbx
0x140025f91  xor     r9d, r9d; SubAuthority1
0x140025f94  mov     [rax-20h], ecx
0x140025f97  mov     dl, 1; SubAuthorityCount
0x140025f99  mov     [rax-28h], ecx
0x140025f9c  mov     [rax-30h], ecx
0x140025f9f  lea     r8d, [rcx+12h]; SubAuthority0
0x140025fa3  mov     [rax-38h], ecx
0x140025fa6  mov     [rax-40h], ecx
0x140025fa9  mov     [rax-48h], ecx
0x140025fac  mov     cs:qword_1400538D8, rcx
0x140025fb3  lea     rcx, IdentifierAuthority; IdentifierAuthority
0x140025fba  call    cs:__imp_RtlAllocateAndInitializeSid
0x140025fc0  mov     cs:dword_14005378C, eax
0x140025fc6  mov     rax, rbx
0x140025fc9  add     rsp, 60h
0x140025fcd  pop     rbx
0x140025fce  retn
```
