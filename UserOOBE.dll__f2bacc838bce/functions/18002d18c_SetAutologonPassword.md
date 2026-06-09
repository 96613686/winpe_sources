# _SetAutologonPassword

- ea: `0x18002d18c`
- end: `0x18002d253`
- name: `_SetAutologonPassword`
- size: `199`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002c45c`
- `0x18002c4f8`

## callees

- `0x180007134`
- `0x18002c43c`
- `0x18002d18c`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18002d1c8`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18002d1c8`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x18002d22a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x18002d22a`
- `ntdll!RtlInitUnicodeString` at `0x18002d20b`
- `ntdll!RtlInitUnicodeString` at `0x18002d218`
- `ntdll!RtlInitUnicodeString` at `0x18002d20b`
- `ntdll!RtlInitUnicodeString` at `0x18002d218`

## string_xrefs

- `0x18002d1dc`: `shell\oobe\common\lib\autologon.cpp`

## pseudocode

```c
__int64 __fastcall SetAutologonPassword(PCWSTR SourceString)
{
  NTSTATUS v2; // eax
  unsigned int v3; // ebx
  struct _UNICODE_STRING v5; // [rsp+20h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]
  PVOID PolicyHandle; // [rsp+88h] [rbp+18h] BYREF

  PolicyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v2 = LsaOpenPolicy(0, &ObjectAttributes, 0x20u, &PolicyHandle);
  v3 = v2 | 0x10000000;
  if ( v2 >= 0 )
  {
    DestinationString = 0;
    v5 = 0;
    RtlInitUnicodeString(&DestinationString, L"DefaultPassword");
    RtlInitUnicodeString(&v5, SourceString);
    v3 = LsaStorePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)&DestinationString, (PLSA_UNICODE_STRING)&v5)
       | 0x10000000;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
      (const char *)v3,
      *(int *)&v5.Length);
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&PolicyHandle);
  return v3;
}

```

## disassembly

```asm
0x18002d18c  mov     [rsp-8+arg_0], rbx
0x18002d191  mov     [rsp-8+arg_10], rdi
0x18002d196  push    rbp
0x18002d197  mov     rbp, rsp
0x18002d19a  sub     rsp, 70h
0x18002d19e  xorps   xmm0, xmm0
0x18002d1a1  mov     [rbp+PolicyHandle], 0
0x18002d1a9  mov     rdi, rcx
0x18002d1ac  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x18002d1b0  xor     ecx, ecx; SystemName
0x18002d1b2  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x18002d1b6  mov     r8d, 20h ; ' '; DesiredAccess
0x18002d1bc  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18002d1c0  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18002d1c4  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18002d1c8  call    cs:__imp_LsaOpenPolicy
0x18002d1ce  mov     ebx, eax
0x18002d1d0  or      ebx, 10000000h
0x18002d1d6  jge     short loc_18002D1F2
0x18002d1d8  mov     rcx, [rbp+8]; this
0x18002d1dc  lea     r8, aShellOobeCommo; "shell\\oobe\\common\\lib\\autologon.cpp"
0x18002d1e3  mov     r9d, ebx; char *
0x18002d1e6  mov     edx, 1Eh; void *
0x18002d1eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d1f0  jmp     short loc_18002D236
0x18002d1f2  xorps   xmm0, xmm0
0x18002d1f5  lea     rdx, aDefaultpasswor; "DefaultPassword"
0x18002d1fc  xorps   xmm1, xmm1
0x18002d1ff  lea     rcx, [rbp+DestinationString]; DestinationString
0x18002d203  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18002d207  movups  xmmword ptr [rbp+var_50.Length], xmm1
0x18002d20b  call    cs:__imp_RtlInitUnicodeString
0x18002d211  mov     rdx, rdi; SourceString
0x18002d214  lea     rcx, [rbp+var_50]; DestinationString
0x18002d218  call    cs:__imp_RtlInitUnicodeString
0x18002d21e  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18002d222  lea     r8, [rbp+var_50]; PrivateData
0x18002d226  lea     rdx, [rbp+DestinationString]; KeyName
0x18002d22a  call    cs:__imp_LsaStorePrivateData
0x18002d230  mov     ebx, eax
0x18002d232  bts     ebx, 1Ch
0x18002d236  lea     rcx, [rbp+PolicyHandle]
0x18002d23a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002d23f  lea     r11, [rsp+70h+var_s0]
0x18002d244  mov     eax, ebx
0x18002d246  mov     rbx, [r11+10h]
0x18002d24a  mov     rdi, [r11+20h]
0x18002d24e  mov     rsp, r11
0x18002d251  pop     rbp
0x18002d252  retn
```
