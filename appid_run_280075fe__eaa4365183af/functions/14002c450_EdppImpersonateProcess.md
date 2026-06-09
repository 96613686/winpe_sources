# EdppImpersonateProcess

- ea: `0x14002c450`
- end: `0x14002c51c`
- name: `EdppImpersonateProcess`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14002cd1c`

## callees

- `0x140006a20`
- `0x14002c450`

## import_xrefs

- `ntoskrnl!ZwDuplicateToken` at `0x14002c4d5`
- `ntoskrnl!ZwDuplicateToken` at `0x14002c4d5`
- `ntoskrnl!ZwSetInformationThread` at `0x14002c4fa`
- `ntoskrnl!ZwSetInformationThread` at `0x14002c4fa`

## pseudocode

```c
int __fastcall EdppImpersonateProcess(__int64 a1)
{
  void *v1; // rcx
  int result; // eax
  void *ThreadInformation; // [rsp+30h] [rbp-50h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-48h] BYREF
  _DWORD v5[4]; // [rsp+68h] [rbp-18h] BYREF

  v1 = *(void **)(a1 + 48);
  ObjectAttributes.SecurityQualityOfService = v5;
  v5[1] = 2;
  v5[2] = 1;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  ThreadInformation = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  ObjectAttributes.SecurityDescriptor = 0;
  v5[0] = 12;
  result = ZwDuplicateToken(v1, 0x8Cu, &ObjectAttributes, 0, TokenImpersonation, &ThreadInformation);
  if ( result >= 0 )
    return ZwSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
  return result;
}

```

## disassembly

```asm
0x14002c450  push    rbp
0x14002c452  mov     rbp, rsp
0x14002c455  sub     rsp, 80h
0x14002c45c  mov     rax, cs:__security_cookie
0x14002c463  xor     rax, rsp
0x14002c466  mov     [rbp+var_8], rax
0x14002c46a  mov     rcx, [rcx+30h]; ExistingTokenHandle
0x14002c46e  lea     rax, [rbp+var_18]
0x14002c472  mov     edx, 2
0x14002c477  mov     [rbp+ObjectAttributes.SecurityQualityOfService], rax
0x14002c47b  lea     rax, [rbp+ThreadInformation]
0x14002c47f  mov     [rbp+var_14], edx
0x14002c482  mov     [rsp+80h+NewTokenHandle], rax; NewTokenHandle
0x14002c487  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14002c48b  mov     [rsp+80h+TokenType], edx; TokenType
0x14002c48f  xor     r9d, r9d; EffectiveOnly
0x14002c492  mov     edx, 8Ch; DesiredAccess
0x14002c497  mov     [rbp+var_10], 1
0x14002c49e  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14002c4a6  mov     qword ptr [rbp+ObjectAttributes.Attributes], 200h
0x14002c4ae  mov     [rbp+ThreadInformation], 0
0x14002c4b6  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14002c4be  mov     [rbp+ObjectAttributes.ObjectName], 0
0x14002c4c6  mov     [rbp+ObjectAttributes.SecurityDescriptor], 0
0x14002c4ce  mov     [rbp+var_18], 0Ch
0x14002c4d5  call    cs:__imp_ZwDuplicateToken
0x14002c4dc  nop     dword ptr [rax+rax+00h]
0x14002c4e1  test    eax, eax
0x14002c4e3  js      short loc_14002C506
0x14002c4e5  mov     r9d, 8; ThreadInformationLength
0x14002c4eb  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x14002c4ef  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x14002c4f6  lea     edx, [r9-3]; ThreadInformationClass
0x14002c4fa  call    cs:__imp_ZwSetInformationThread
0x14002c501  nop     dword ptr [rax+rax+00h]
0x14002c506  mov     rcx, [rbp+var_8]
0x14002c50a  xor     rcx, rsp; StackCookie
0x14002c50d  call    __security_check_cookie
0x14002c512  add     rsp, 80h
0x14002c519  pop     rbp
0x14002c51a  retn
```
