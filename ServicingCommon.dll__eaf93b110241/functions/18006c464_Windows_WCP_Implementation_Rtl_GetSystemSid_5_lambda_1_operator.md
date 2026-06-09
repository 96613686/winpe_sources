# _Windows::WCP::Implementation::Rtl::GetSystemSid_::_5_::_lambda_1_::operator()

- ea: `0x18006c464`
- end: `0x18006c4be`
- name: `_Windows::WCP::Implementation::Rtl::GetSystemSid_::_5_::_lambda_1_::operator()`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18006d18c`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x18006c4a2`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18006c4a2`

## pseudocode

```c
PVOID *Windows::WCP::Implementation::Rtl::GetSystemSid_::_5_::_lambda_1_::operator()()
{
  qword_1800D4E90 = 0;
  dword_1800D4CEC = RtlAllocateAndInitializeSid(
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
                      &qword_1800D4E90);
  return &qword_1800D4E90;
}

```

## disassembly

```asm
0x18006c464  mov     rax, rsp
0x18006c467  push    rbx
0x18006c468  sub     rsp, 60h
0x18006c46c  xor     ecx, ecx
0x18006c46e  lea     rbx, qword_1800D4E90
0x18006c475  mov     [rax-18h], rbx
0x18006c479  xor     r9d, r9d; SubAuthority1
0x18006c47c  mov     [rax-20h], ecx
0x18006c47f  mov     dl, 1; SubAuthorityCount
0x18006c481  mov     [rax-28h], ecx
0x18006c484  mov     [rax-30h], ecx
0x18006c487  lea     r8d, [rcx+12h]; SubAuthority0
0x18006c48b  mov     [rax-38h], ecx
0x18006c48e  mov     [rax-40h], ecx
0x18006c491  mov     [rax-48h], ecx
0x18006c494  mov     cs:qword_1800D4E90, rcx
0x18006c49b  lea     rcx, IdentifierAuthority; IdentifierAuthority
0x18006c4a2  call    cs:__imp_RtlAllocateAndInitializeSid
0x18006c4a9  nop     dword ptr [rax+rax+00h]
0x18006c4ae  mov     cs:dword_1800D4CEC, eax
0x18006c4b4  mov     rax, rbx
0x18006c4b7  add     rsp, 60h
0x18006c4bb  pop     rbx
0x18006c4bc  retn
```
