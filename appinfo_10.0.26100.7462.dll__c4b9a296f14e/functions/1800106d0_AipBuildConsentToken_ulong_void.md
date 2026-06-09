# AipBuildConsentToken(ulong,void * *)

- ea: `0x1800106d0`
- end: `0x180010843`
- name: `?AipBuildConsentToken@@YAKKPEAPEAX@Z`
- size: `371`
- prototype: `unsigned int __fastcall(unsigned int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180024a98`

## callees

- `0x1800106d0`
- `0x180044a20`

## import_xrefs

- `ntdll!NtClose` at `0x1800107f3`
- `ntdll!NtClose` at `0x180010815`
- `ntdll!NtClose` at `0x1800107f3`
- `ntdll!NtClose` at `0x180010815`
- `ntdll!RtlNtStatusToDosError` at `0x1800107dc`
- `ntdll!RtlNtStatusToDosError` at `0x1800107dc`
- `ntdll!RtlRemovePrivileges` at `0x1800107ca`
- `ntdll!RtlRemovePrivileges` at `0x1800107ca`
- `ntdll!NtDuplicateToken` at `0x18001078f`
- `ntdll!NtDuplicateToken` at `0x18001078f`
- `ntdll!NtOpenProcessToken` at `0x180010743`
- `ntdll!NtOpenProcessToken` at `0x180010743`
- `ntdll!NtSetInformationToken` at `0x1800107ae`
- `ntdll!NtSetInformationToken` at `0x1800107ae`

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
0x1800106d0  mov     [rsp-8+arg_10], rbx
0x1800106d5  push    rbp
0x1800106d6  push    rsi
0x1800106d7  push    rdi
0x1800106d8  lea     rbp, [rsp-47h]
0x1800106dd  sub     rsp, 0A0h
0x1800106e4  mov     rax, cs:__security_cookie
0x1800106eb  xor     rax, rsp
0x1800106ee  mov     [rbp+57h+var_20], rax
0x1800106f2  xor     esi, esi
0x1800106f4  mov     [rbp+57h+TokenInformation], ecx
0x1800106f7  xorps   xmm0, xmm0
0x1800106fa  mov     [rbp+57h+TokenHandle], rsi
0x1800106fe  mov     rdi, rdx
0x180010701  mov     [rbp+57h+Handle], rsi
0x180010705  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180010709  mov     [rbp+57h+var_38], 7
0x180010710  lea     rcx, [rsi-1]; ProcessHandle
0x180010714  mov     [rbp+57h+var_34], 11h
0x18001071b  mov     edx, 1ABh; DesiredAccess
0x180010720  mov     [rbp+57h+var_30], 12h
0x180010727  mov     ebx, esi
0x180010729  mov     [rbp+57h+var_2C], 17h
0x180010730  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180010734  mov     [rbp+57h+var_28], 1Dh
0x18001073b  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18001073f  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180010743  call    cs:__imp_NtOpenProcessToken
0x18001074a  nop     dword ptr [rax+rax+00h]
0x18001074f  test    eax, eax
0x180010751  js      loc_1800107DA
0x180010757  mov     rcx, [rbp+57h+TokenHandle]; ExistingTokenHandle
0x18001075b  lea     rax, [rbp+57h+Handle]
0x18001075f  xorps   xmm0, xmm0
0x180010762  mov     [rsp+0B0h+NewTokenHandle], rax; NewTokenHandle
0x180010767  xor     r9d, r9d; EffectiveOnly
0x18001076a  mov     [rsp+0B0h+TokenType], 1; TokenType
0x180010772  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180010776  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001077d  xor     edx, edx; DesiredAccess
0x18001077f  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x180010783  mov     [rbp+57h+ObjectAttributes.Attributes], esi
0x180010786  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x18001078a  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001078f  call    cs:__imp_NtDuplicateToken
0x180010796  nop     dword ptr [rax+rax+00h]
0x18001079b  test    eax, eax
0x18001079d  js      short loc_1800107DA
0x18001079f  mov     rcx, [rbp+57h+Handle]; TokenHandle
0x1800107a3  lea     r9d, [rsi+4]; TokenInformationLength
0x1800107a7  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800107ab  lea     edx, [rsi+0Ch]; TokenInformationClass
0x1800107ae  call    cs:__imp_NtSetInformationToken
0x1800107b5  nop     dword ptr [rax+rax+00h]
0x1800107ba  test    eax, eax
0x1800107bc  js      short loc_1800107DA
0x1800107be  mov     rcx, [rbp+57h+Handle]
0x1800107c2  lea     r8d, [rsi+5]
0x1800107c6  lea     rdx, [rbp+57h+var_38]
0x1800107ca  call    cs:__imp_RtlRemovePrivileges
0x1800107d1  nop     dword ptr [rax+rax+00h]
0x1800107d6  test    eax, eax
0x1800107d8  jns     short loc_180010801
0x1800107da  mov     ecx, eax; Status
0x1800107dc  call    cs:__imp_RtlNtStatusToDosError
0x1800107e3  nop     dword ptr [rax+rax+00h]
0x1800107e8  mov     ebx, eax
0x1800107ea  mov     rcx, [rbp+57h+Handle]; Handle
0x1800107ee  test    rcx, rcx
0x1800107f1  jz      short loc_18001080C
0x1800107f3  call    cs:__imp_NtClose
0x1800107fa  nop     dword ptr [rax+rax+00h]
0x1800107ff  jmp     short loc_180010808
0x180010801  mov     rax, [rbp+57h+Handle]
0x180010805  mov     [rdi], rax
0x180010808  mov     [rbp+57h+Handle], rsi
0x18001080c  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x180010810  test    rcx, rcx
0x180010813  jz      short loc_180010821
0x180010815  call    cs:__imp_NtClose
0x18001081c  nop     dword ptr [rax+rax+00h]
0x180010821  mov     eax, ebx
0x180010823  mov     rcx, [rbp+57h+var_20]
0x180010827  xor     rcx, rsp; StackCookie
0x18001082a  call    __security_check_cookie
0x18001082f  mov     rbx, [rsp+0B0h+arg_10]
0x180010837  add     rsp, 0A0h
0x18001083e  pop     rdi
0x18001083f  pop     rsi
0x180010840  pop     rbp
0x180010841  retn
```
