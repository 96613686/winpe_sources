# BfeObjectSecuritySave

- ea: `0x180034ae0`
- end: `0x180034b89`
- name: `BfeObjectSecuritySave`
- size: `169`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `6`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003fa78`
- `0x180055c6c`
- `0x1800573b8`
- `0x180068ec8`
- `0x18006999c`
- `0x180069b1c`

## callees

- `0x1800047b8`
- `0x1800049f8`
- `0x180018b74`
- `0x180034ae0`
- `0x180034b90`
- `0x180058b30`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x180034b12`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180034b12`

## string_xrefs

- `0x180034b37`: `System\CurrentControlSet\Services\BFE\Parameters\Policy\Security`
- `0x180034b78`: `BfeObjectSecuritySave`

## pseudocode

```c
__int64 __fastcall BfeObjectSecuritySave(PSECURITY_DESCRIPTOR SecurityDescriptor, __int64 a2)
{
  void *v4; // rdi
  DWORD v5; // ebx
  const WCHAR *v6; // rax
  __int64 v7; // rax
  __int64 v8; // rbx
  _BYTE v10[80]; // [rsp+30h] [rbp-78h] BYREF

  v4 = (void *)BfeCallGetSysTxn();
  v5 = RtlLengthSecurityDescriptor(SecurityDescriptor);
  v6 = (const WCHAR *)BfeGuidToString(a2, v10);
  v7 = BfeRegSetBinary(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\BFE\\Parameters\\Policy\\Security",
         v6,
         v5,
         (BYTE *)SecurityDescriptor,
         v4);
  v8 = v7;
  if ( v7 )
    WfpReportError(v7, "BfeObjectSecuritySave");
  return v8;
}

```

## disassembly

```asm
0x180034ae0  mov     [rsp+arg_10], rbx
0x180034ae5  push    rbp
0x180034ae6  push    rsi
0x180034ae7  push    rdi
0x180034ae8  sub     rsp, 90h
0x180034aef  mov     rax, cs:__security_cookie
0x180034af6  xor     rax, rsp
0x180034af9  mov     [rsp+0A8h+var_28], rax
0x180034b01  mov     rsi, rdx
0x180034b04  mov     rbp, rcx
0x180034b07  call    BfeCallGetSysTxn
0x180034b0c  mov     rcx, rbp; SecurityDescriptor
0x180034b0f  mov     rdi, rax
0x180034b12  call    cs:__imp_RtlLengthSecurityDescriptor
0x180034b18  lea     rdx, [rsp+0A8h+var_78]
0x180034b1d  mov     rcx, rsi
0x180034b20  mov     ebx, eax
0x180034b22  call    BfeGuidToString
0x180034b27  mov     r8, rax
0x180034b2a  mov     [rsp+0A8h+var_80], rdi
0x180034b2f  mov     r9d, ebx
0x180034b32  mov     [rsp+0A8h+var_88], rbp
0x180034b37  lea     rdx, BFE_SECURITY_POLICY_KEY; "System\\CurrentControlSet\\Services\\BF"...
0x180034b3e  mov     rcx, 0FFFFFFFF80000002h
0x180034b45  call    BfeRegSetBinary
0x180034b4a  mov     rbx, rax
0x180034b4d  test    rax, rax
0x180034b50  jnz     short loc_180034B78
0x180034b52  mov     rax, rbx
0x180034b55  mov     rcx, [rsp+0A8h+var_28]
0x180034b5d  xor     rcx, rsp; StackCookie
0x180034b60  call    __security_check_cookie
0x180034b65  mov     rbx, [rsp+0A8h+arg_10]
0x180034b6d  add     rsp, 90h
0x180034b74  pop     rdi
0x180034b75  pop     rsi
0x180034b76  pop     rbp
0x180034b77  retn
0x180034b78  lea     rdx, aBfeobjectsecur_0; "BfeObjectSecuritySave"
0x180034b7f  mov     rcx, rbx
0x180034b82  call    WfpReportError
0x180034b87  jmp     short loc_180034B52
```
