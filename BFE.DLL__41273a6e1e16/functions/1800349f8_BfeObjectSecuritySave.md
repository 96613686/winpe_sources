# BfeObjectSecuritySave

- ea: `0x1800349f8`
- end: `0x180034aa8`
- name: `BfeObjectSecuritySave`
- size: `176`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `6`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180040dcc`
- `0x180057ac0`
- `0x1800590dc`
- `0x18006b460`
- `0x18006bf70`
- `0x18006c100`

## callees

- `0x180004810`
- `0x180005238`
- `0x1800197d0`
- `0x1800349f8`
- `0x180034ab0`
- `0x18005aa60`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x180034a2a`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180034a2a`

## string_xrefs

- `0x180034a55`: `System\CurrentControlSet\Services\BFE\Parameters\Policy\Security`
- `0x180034a97`: `BfeObjectSecuritySave`

## pseudocode

```c
__int64 __fastcall BfeObjectSecuritySave(PSECURITY_DESCRIPTOR SecurityDescriptor, __int64 a2)
{
  __int64 v4; // rdi
  ULONG v5; // ebx
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rbx
  _BYTE v10[80]; // [rsp+30h] [rbp-78h] BYREF

  v4 = BfeCallGetSysTxn();
  v5 = RtlLengthSecurityDescriptor(SecurityDescriptor);
  v6 = BfeGuidToString(a2, v10);
  v7 = BfeRegSetBinary(
         -2147483646,
         L"System\\CurrentControlSet\\Services\\BFE\\Parameters\\Policy\\Security",
         v6,
         v5,
         SecurityDescriptor,
         v4);
  v8 = v7;
  if ( v7 )
    WfpReportError(v7, "BfeObjectSecuritySave");
  return v8;
}

```

## disassembly

```asm
0x1800349f8  mov     [rsp+arg_10], rbx
0x1800349fd  push    rbp
0x1800349fe  push    rsi
0x1800349ff  push    rdi
0x180034a00  sub     rsp, 90h
0x180034a07  mov     rax, cs:__security_cookie
0x180034a0e  xor     rax, rsp
0x180034a11  mov     [rsp+0A8h+var_28], rax
0x180034a19  mov     rsi, rdx
0x180034a1c  mov     rbp, rcx
0x180034a1f  call    BfeCallGetSysTxn
0x180034a24  mov     rcx, rbp; SecurityDescriptor
0x180034a27  mov     rdi, rax
0x180034a2a  call    cs:__imp_RtlLengthSecurityDescriptor
0x180034a31  nop     dword ptr [rax+rax+00h]
0x180034a36  lea     rdx, [rsp+0A8h+var_78]
0x180034a3b  mov     rcx, rsi
0x180034a3e  mov     ebx, eax
0x180034a40  call    BfeGuidToString
0x180034a45  mov     r8, rax
0x180034a48  mov     [rsp+0A8h+var_80], rdi
0x180034a4d  mov     r9d, ebx
0x180034a50  mov     [rsp+0A8h+var_88], rbp
0x180034a55  lea     rdx, BFE_SECURITY_POLICY_KEY; "System\\CurrentControlSet\\Services\\BF"...
0x180034a5c  mov     rcx, 0FFFFFFFF80000002h
0x180034a63  call    BfeRegSetBinary
0x180034a68  mov     rbx, rax
0x180034a6b  test    rax, rax
0x180034a6e  jnz     short loc_180034A97
0x180034a70  mov     rax, rbx
0x180034a73  mov     rcx, [rsp+0A8h+var_28]
0x180034a7b  xor     rcx, rsp; StackCookie
0x180034a7e  call    __security_check_cookie
0x180034a83  mov     rbx, [rsp+0A8h+arg_10]
0x180034a8b  add     rsp, 90h
0x180034a92  pop     rdi
0x180034a93  pop     rsi
0x180034a94  pop     rbp
0x180034a95  retn
0x180034a97  lea     rdx, aBfeobjectsecur_0; "BfeObjectSecuritySave"
0x180034a9e  mov     rcx, rbx
0x180034aa1  call    WfpReportError
0x180034aa6  jmp     short loc_180034A70
```
