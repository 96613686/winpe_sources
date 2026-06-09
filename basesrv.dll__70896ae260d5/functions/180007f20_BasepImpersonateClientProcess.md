# BasepImpersonateClientProcess

- ea: `0x180007f20`
- end: `0x180008032`
- name: `BasepImpersonateClientProcess`
- size: `274`
- prototype: `NTSTATUS __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000ba38`

## callees

- `0x180007f20`
- `0x18000d730`

## import_xrefs

- `ntdll!NtClose` at `0x180007fd1`
- `ntdll!NtClose` at `0x180008002`
- `ntdll!NtClose` at `0x180007fd1`
- `ntdll!NtClose` at `0x180008002`
- `ntdll!NtOpenProcessToken` at `0x180007f62`
- `ntdll!NtOpenProcessToken` at `0x180007f62`
- `ntdll!NtDuplicateToken` at `0x180007fbf`
- `ntdll!NtDuplicateToken` at `0x180007fbf`
- `ntdll!NtSetInformationThread` at `0x180007ff0`
- `ntdll!NtSetInformationThread` at `0x180007ff0`

## pseudocode

```c
NTSTATUS __fastcall BasepImpersonateClientProcess(void *a1)
{
  NTSTATUS result; // eax
  NTSTATUS v2; // ebx
  void *TokenHandle; // [rsp+30h] [rbp-9h] BYREF
  void *ThreadInformation; // [rsp+38h] [rbp-1h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp+7h] BYREF
  _DWORD v6[2]; // [rsp+70h] [rbp+37h] BYREF
  __int16 v7; // [rsp+78h] [rbp+3Fh]
  __int16 v8; // [rsp+7Ah] [rbp+41h]

  TokenHandle = 0;
  ThreadInformation = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  v8 = 0;
  result = NtOpenProcessToken(a1, 2u, &TokenHandle);
  if ( result >= 0 )
  {
    ObjectAttributes.SecurityQualityOfService = v6;
    ObjectAttributes.Length = 48;
    memset(&ObjectAttributes.RootDirectory, 0, 20);
    ObjectAttributes.SecurityDescriptor = 0;
    v6[0] = 12;
    v6[1] = 2;
    v7 = 257;
    v2 = NtDuplicateToken(TokenHandle, 4u, &ObjectAttributes, 1u, TokenImpersonation, &ThreadInformation);
    NtClose(TokenHandle);
    if ( v2 >= 0 )
    {
      v2 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
      NtClose(ThreadInformation);
    }
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x180007f20  mov     [rsp-8+arg_8], rbx
0x180007f25  mov     [rsp-8+arg_10], rdi
0x180007f2a  push    rbp
0x180007f2b  lea     rbp, [rsp-57h]
0x180007f30  sub     rsp, 90h
0x180007f37  mov     rax, cs:__security_cookie
0x180007f3e  xor     rax, rsp
0x180007f41  mov     [rbp+57h+var_10], rax
0x180007f45  xor     edi, edi
0x180007f47  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180007f4b  mov     [rbp+57h+TokenHandle], rdi
0x180007f4f  mov     [rbp+57h+ThreadInformation], rdi
0x180007f53  mov     dword ptr [rbp+57h+ObjectAttributes+4], edi
0x180007f56  lea     ebx, [rdi+2]
0x180007f59  mov     dword ptr [rbp+57h+ObjectAttributes+1Ch], edi
0x180007f5c  mov     edx, ebx; DesiredAccess
0x180007f5e  mov     [rbp+57h+var_16], di
0x180007f62  call    cs:__imp_NtOpenProcessToken
0x180007f69  nop     dword ptr [rax+rax+00h]
0x180007f6e  test    eax, eax
0x180007f70  js      loc_180008010
0x180007f76  mov     rcx, [rbp+57h+TokenHandle]; ExistingTokenHandle
0x180007f7a  lea     rax, [rbp+57h+var_20]
0x180007f7e  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x180007f82  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180007f86  lea     rax, [rbp+57h+ThreadInformation]
0x180007f8a  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180007f91  mov     [rsp+90h+NewTokenHandle], rax; NewTokenHandle
0x180007f96  lea     edx, [rdi+4]; DesiredAccess
0x180007f99  mov     r9b, 1; EffectiveOnly
0x180007f9c  mov     [rsp+90h+TokenType], ebx; TokenType
0x180007fa0  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x180007fa4  mov     [rbp+57h+ObjectAttributes.Attributes], edi
0x180007fa7  mov     [rbp+57h+ObjectAttributes.ObjectName], rdi
0x180007fab  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rdi
0x180007faf  mov     [rbp+57h+var_20], 0Ch
0x180007fb6  mov     [rbp+57h+var_1C], ebx
0x180007fb9  mov     [rbp+57h+var_18], 101h
0x180007fbf  call    cs:__imp_NtDuplicateToken
0x180007fc6  nop     dword ptr [rax+rax+00h]
0x180007fcb  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x180007fcf  mov     ebx, eax
0x180007fd1  call    cs:__imp_NtClose
0x180007fd8  nop     dword ptr [rax+rax+00h]
0x180007fdd  test    ebx, ebx
0x180007fdf  js      short loc_18000800E
0x180007fe1  lea     r9d, [rdi+8]; ThreadInformationLength
0x180007fe5  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x180007fe9  lea     edx, [rdi+5]; ThreadInformationClass
0x180007fec  lea     rcx, [rdi-2]; ThreadHandle
0x180007ff0  call    cs:__imp_NtSetInformationThread
0x180007ff7  nop     dword ptr [rax+rax+00h]
0x180007ffc  mov     rcx, [rbp+57h+ThreadInformation]; Handle
0x180008000  mov     ebx, eax
0x180008002  call    cs:__imp_NtClose
0x180008009  nop     dword ptr [rax+rax+00h]
0x18000800e  mov     eax, ebx
0x180008010  mov     rcx, [rbp+57h+var_10]
0x180008014  xor     rcx, rsp; StackCookie
0x180008017  call    __security_check_cookie
0x18000801c  lea     r11, [rsp+90h+var_s0]
0x180008024  mov     rbx, [r11+18h]
0x180008028  mov     rdi, [r11+20h]
0x18000802c  mov     rsp, r11
0x18000802f  pop     rbp
0x180008030  retn
```
