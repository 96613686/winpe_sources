# _Windows::WCP::Implementation::Rtl::GetSystemSid_::_5_::_lambda_1_::operator()

- ea: `0x140026220`
- end: `0x140026273`
- name: `_Windows::WCP::Implementation::Rtl::GetSystemSid_::_5_::_lambda_1_::operator()`
- size: `83`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x1400268c8`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x14002625e`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14002625e`

## pseudocode

```c
PVOID *Windows::WCP::Implementation::Rtl::GetSystemSid_::_5_::_lambda_1_::operator()()
{
  qword_140040A30 = 0;
  dword_1400408DC = RtlAllocateAndInitializeSid(
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
                      &qword_140040A30);
  return &qword_140040A30;
}

```

## disassembly

```asm
0x140026220  mov     rax, rsp
0x140026223  push    rbx
0x140026224  sub     rsp, 60h
0x140026228  xor     ecx, ecx
0x14002622a  lea     rbx, qword_140040A30
0x140026231  mov     [rax-18h], rbx
0x140026235  xor     r9d, r9d; SubAuthority1
0x140026238  mov     [rax-20h], ecx
0x14002623b  mov     dl, 1; SubAuthorityCount
0x14002623d  mov     [rax-28h], ecx
0x140026240  mov     [rax-30h], ecx
0x140026243  lea     r8d, [rcx+12h]; SubAuthority0
0x140026247  mov     [rax-38h], ecx
0x14002624a  mov     [rax-40h], ecx
0x14002624d  mov     [rax-48h], ecx
0x140026250  mov     cs:qword_140040A30, rcx
0x140026257  lea     rcx, IdentifierAuthority; IdentifierAuthority
0x14002625e  call    cs:__imp_RtlAllocateAndInitializeSid
0x140026264  mov     cs:dword_1400408DC, eax
0x14002626a  mov     rax, rbx
0x14002626d  add     rsp, 60h
0x140026271  pop     rbx
0x140026272  retn
```
