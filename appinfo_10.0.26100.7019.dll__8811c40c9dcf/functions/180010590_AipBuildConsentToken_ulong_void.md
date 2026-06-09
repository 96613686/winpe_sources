# AipBuildConsentToken(ulong,void * *)

- ea: `0x180010590`
- end: `0x180010703`
- name: `?AipBuildConsentToken@@YAKKPEAPEAX@Z`
- size: `371`
- prototype: `unsigned int __fastcall(unsigned int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800263a8`

## callees

- `0x180010590`
- `0x180042950`

## import_xrefs

- `ntdll!NtClose` at `0x1800106b3`
- `ntdll!NtClose` at `0x1800106d5`
- `ntdll!NtClose` at `0x1800106b3`
- `ntdll!NtClose` at `0x1800106d5`
- `ntdll!RtlNtStatusToDosError` at `0x18001069c`
- `ntdll!RtlNtStatusToDosError` at `0x18001069c`
- `ntdll!RtlRemovePrivileges` at `0x18001068a`
- `ntdll!RtlRemovePrivileges` at `0x18001068a`
- `ntdll!NtSetInformationToken` at `0x18001066e`
- `ntdll!NtSetInformationToken` at `0x18001066e`
- `ntdll!NtDuplicateToken` at `0x18001064f`
- `ntdll!NtDuplicateToken` at `0x18001064f`
- `ntdll!NtOpenProcessToken` at `0x180010603`
- `ntdll!NtOpenProcessToken` at `0x180010603`

## pseudocode

```c
__int64 __fastcall AipBuildConsentToken(int a1, void **a2)
{
  ULONG v3; // ebx
  int v4; // eax
  HANDLE Handle; // [rsp+30h] [rbp-29h] BYREF
  int TokenInformation; // [rsp+38h] [rbp-21h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-11h] BYREF
  _DWORD v10[6]; // [rsp+78h] [rbp+1Fh] BYREF

  TokenInformation = a1;
  TokenHandle = 0;
  Handle = 0;
  v10[0] = 7;
  v10[1] = 17;
  v10[2] = 18;
  v3 = 0;
  v10[3] = 23;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v10[4] = 29;
  v4 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x1ABu, &TokenHandle);
  if ( v4 >= 0
    && (ObjectAttributes.Length = 48,
        memset(&ObjectAttributes.RootDirectory, 0, 20),
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0,
        v4 = NtDuplicateToken(TokenHandle, 0, &ObjectAttributes, 0, TokenPrimary, &Handle),
        v4 >= 0)
    && (v4 = NtSetInformationToken(Handle, TokenSessionId, &TokenInformation, 4u), v4 >= 0)
    && (v4 = RtlRemovePrivileges(Handle, v10, 5), v4 >= 0) )
  {
    *a2 = Handle;
  }
  else
  {
    v3 = RtlNtStatusToDosError(v4);
    if ( !Handle )
      goto LABEL_9;
    NtClose(Handle);
  }
  Handle = 0;
LABEL_9:
  if ( TokenHandle )
    NtClose(TokenHandle);
  return v3;
}

```

## disassembly

```asm
0x180010590  mov     [rsp-8+arg_10], rbx
0x180010595  push    rbp
0x180010596  push    rsi
0x180010597  push    rdi
0x180010598  lea     rbp, [rsp-47h]
0x18001059d  sub     rsp, 0A0h
0x1800105a4  mov     rax, cs:__security_cookie
0x1800105ab  xor     rax, rsp
0x1800105ae  mov     [rbp+57h+var_20], rax
0x1800105b2  xor     esi, esi
0x1800105b4  mov     [rbp+57h+TokenInformation], ecx
0x1800105b7  xorps   xmm0, xmm0
0x1800105ba  mov     [rbp+57h+TokenHandle], rsi
0x1800105be  mov     rdi, rdx
0x1800105c1  mov     [rbp+57h+Handle], rsi
0x1800105c5  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x1800105c9  mov     [rbp+57h+var_38], 7
0x1800105d0  lea     rcx, [rsi-1]; ProcessHandle
0x1800105d4  mov     [rbp+57h+var_34], 11h
0x1800105db  mov     edx, 1ABh; DesiredAccess
0x1800105e0  mov     [rbp+57h+var_30], 12h
0x1800105e7  mov     ebx, esi
0x1800105e9  mov     [rbp+57h+var_2C], 17h
0x1800105f0  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800105f4  mov     [rbp+57h+var_28], 1Dh
0x1800105fb  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800105ff  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180010603  call    cs:__imp_NtOpenProcessToken
0x18001060a  nop     dword ptr [rax+rax+00h]
0x18001060f  test    eax, eax
0x180010611  js      loc_18001069A
0x180010617  mov     rcx, [rbp+57h+TokenHandle]; ExistingTokenHandle
0x18001061b  lea     rax, [rbp+57h+Handle]
0x18001061f  xorps   xmm0, xmm0
0x180010622  mov     [rsp+0B0h+NewTokenHandle], rax; NewTokenHandle
0x180010627  xor     r9d, r9d; EffectiveOnly
0x18001062a  mov     [rsp+0B0h+TokenType], 1; TokenType
0x180010632  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180010636  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001063d  xor     edx, edx; DesiredAccess
0x18001063f  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x180010643  mov     [rbp+57h+ObjectAttributes.Attributes], esi
0x180010646  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x18001064a  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001064f  call    cs:__imp_NtDuplicateToken
0x180010656  nop     dword ptr [rax+rax+00h]
0x18001065b  test    eax, eax
0x18001065d  js      short loc_18001069A
0x18001065f  mov     rcx, [rbp+57h+Handle]; TokenHandle
0x180010663  lea     r9d, [rsi+4]; TokenInformationLength
0x180010667  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18001066b  lea     edx, [rsi+0Ch]; TokenInformationClass
0x18001066e  call    cs:__imp_NtSetInformationToken
0x180010675  nop     dword ptr [rax+rax+00h]
0x18001067a  test    eax, eax
0x18001067c  js      short loc_18001069A
0x18001067e  mov     rcx, [rbp+57h+Handle]
0x180010682  lea     r8d, [rsi+5]
0x180010686  lea     rdx, [rbp+57h+var_38]
0x18001068a  call    cs:__imp_RtlRemovePrivileges
0x180010691  nop     dword ptr [rax+rax+00h]
0x180010696  test    eax, eax
0x180010698  jns     short loc_1800106C1
0x18001069a  mov     ecx, eax; Status
0x18001069c  call    cs:__imp_RtlNtStatusToDosError
0x1800106a3  nop     dword ptr [rax+rax+00h]
0x1800106a8  mov     ebx, eax
0x1800106aa  mov     rcx, [rbp+57h+Handle]; Handle
0x1800106ae  test    rcx, rcx
0x1800106b1  jz      short loc_1800106CC
0x1800106b3  call    cs:__imp_NtClose
0x1800106ba  nop     dword ptr [rax+rax+00h]
0x1800106bf  jmp     short loc_1800106C8
0x1800106c1  mov     rax, [rbp+57h+Handle]
0x1800106c5  mov     [rdi], rax
0x1800106c8  mov     [rbp+57h+Handle], rsi
0x1800106cc  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x1800106d0  test    rcx, rcx
0x1800106d3  jz      short loc_1800106E1
0x1800106d5  call    cs:__imp_NtClose
0x1800106dc  nop     dword ptr [rax+rax+00h]
0x1800106e1  mov     eax, ebx
0x1800106e3  mov     rcx, [rbp+57h+var_20]
0x1800106e7  xor     rcx, rsp; StackCookie
0x1800106ea  call    __security_check_cookie
0x1800106ef  mov     rbx, [rsp+0B0h+arg_10]
0x1800106f7  add     rsp, 0A0h
0x1800106fe  pop     rdi
0x1800106ff  pop     rsi
0x180010700  pop     rbp
0x180010701  retn
```
