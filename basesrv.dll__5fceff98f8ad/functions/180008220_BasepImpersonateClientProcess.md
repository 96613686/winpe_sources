# BasepImpersonateClientProcess

- ea: `0x180008220`
- end: `0x180008353`
- name: `BasepImpersonateClientProcess`
- size: `307`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000bcf8`

## callees

- `0x180008220`
- `0x18000db40`

## import_xrefs

- `ntdll!NtClose` at `0x1800082f0`
- `ntdll!NtClose` at `0x180008327`
- `ntdll!NtClose` at `0x1800082f0`
- `ntdll!NtClose` at `0x180008327`
- `ntdll!NtOpenProcessToken` at `0x180008271`
- `ntdll!NtOpenProcessToken` at `0x180008271`
- `ntdll!NtDuplicateToken` at `0x1800082de`
- `ntdll!NtDuplicateToken` at `0x1800082de`
- `ntdll!NtSetInformationThread` at `0x180008315`
- `ntdll!NtSetInformationThread` at `0x180008315`

## pseudocode

```c
NTSTATUS __fastcall BasepImpersonateClientProcess(void *a1)
{
  NTSTATUS result; // eax
  NTSTATUS v2; // ebx
  void *TokenHandle; // [rsp+30h] [rbp-9h] BYREF
  void *ThreadInformation; // [rsp+38h] [rbp-1h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp+7h] BYREF
  __int64 v6; // [rsp+70h] [rbp+37h] BYREF
  int v7; // [rsp+78h] [rbp+3Fh]

  TokenHandle = 0;
  ThreadInformation = 0;
  v6 = 0;
  v7 = 0;
  memset(&ObjectAttributes, 0, 44);
  result = NtOpenProcessToken(a1, 2u, &TokenHandle);
  if ( result >= 0 )
  {
    ObjectAttributes.SecurityQualityOfService = &v6;
    ObjectAttributes.Length = 48;
    memset(&ObjectAttributes.RootDirectory, 0, 20);
    ObjectAttributes.SecurityDescriptor = 0;
    v6 = 0x20000000CLL;
    LOWORD(v7) = 257;
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
0x180008220  mov     [rsp-8+arg_8], rbx
0x180008225  push    rbp
0x180008226  lea     rbp, [rsp-57h]
0x18000822b  sub     rsp, 90h
0x180008232  mov     rax, cs:__security_cookie
0x180008239  xor     rax, rsp
0x18000823c  mov     [rbp+57h+var_10], rax
0x180008240  xor     eax, eax
0x180008242  mov     [rbp+57h+TokenHandle], 0
0x18000824a  xorps   xmm0, xmm0
0x18000824d  mov     [rbp+57h+ThreadInformation], 0
0x180008255  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180008259  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18000825d  mov     [rbp+57h+var_20], rax
0x180008261  lea     ebx, [rax+2]
0x180008264  mov     [rbp+57h+var_18], eax
0x180008267  mov     edx, ebx; DesiredAccess
0x180008269  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18000826d  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180008271  call    cs:__imp_NtOpenProcessToken
0x180008278  nop     dword ptr [rax+rax+00h]
0x18000827d  test    eax, eax
0x18000827f  js      loc_180008335
0x180008285  mov     rcx, [rbp+57h+TokenHandle]; ExistingTokenHandle
0x180008289  lea     rax, [rbp+57h+var_20]
0x18000828d  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x180008291  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180008295  lea     rax, [rbp+57h+ThreadInformation]
0x180008299  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800082a0  mov     [rsp+90h+NewTokenHandle], rax; NewTokenHandle
0x1800082a5  lea     edx, [rbx+2]; DesiredAccess
0x1800082a8  mov     r9b, 1; EffectiveOnly
0x1800082ab  mov     [rsp+90h+TokenType], ebx; TokenType
0x1800082af  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1800082b7  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x1800082be  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x1800082c6  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], 0
0x1800082ce  mov     dword ptr [rbp+57h+var_20], 0Ch
0x1800082d5  mov     dword ptr [rbp+57h+var_20+4], ebx
0x1800082d8  mov     word ptr [rbp+57h+var_18], 101h
0x1800082de  call    cs:__imp_NtDuplicateToken
0x1800082e5  nop     dword ptr [rax+rax+00h]
0x1800082ea  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x1800082ee  mov     ebx, eax
0x1800082f0  call    cs:__imp_NtClose
0x1800082f7  nop     dword ptr [rax+rax+00h]
0x1800082fc  test    ebx, ebx
0x1800082fe  js      short loc_180008333
0x180008300  mov     r9d, 8; ThreadInformationLength
0x180008306  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x18000830a  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180008311  lea     edx, [r9-3]; ThreadInformationClass
0x180008315  call    cs:__imp_NtSetInformationThread
0x18000831c  nop     dword ptr [rax+rax+00h]
0x180008321  mov     rcx, [rbp+57h+ThreadInformation]; Handle
0x180008325  mov     ebx, eax
0x180008327  call    cs:__imp_NtClose
0x18000832e  nop     dword ptr [rax+rax+00h]
0x180008333  mov     eax, ebx
0x180008335  mov     rcx, [rbp+57h+var_10]
0x180008339  xor     rcx, rsp; StackCookie
0x18000833c  call    __security_check_cookie
0x180008341  mov     rbx, [rsp+90h+arg_8]
0x180008349  add     rsp, 90h
0x180008350  pop     rbp
0x180008351  retn
```
