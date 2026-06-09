# _MoveLsaSecret(ushort const *,ushort const *)

- ea: `0x18002d020`
- end: `0x18002d184`
- name: `?_MoveLsaSecret@@YAJPEBG0@Z`
- size: `356`
- prototype: `__int64 __fastcall(PCWSTR SourceString, PCWSTR)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002ca58`

## callees

- `0x180007134`
- `0x18002c43c`
- `0x18002d020`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18002d065`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18002d065`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x18002d0a7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x18002d0a7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002d11a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002d159`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002d11a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002d159`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x18002d0f1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x18002d141`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x18002d0f1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x18002d141`
- `ntdll!RtlInitUnicodeString` at `0x18002d08d`
- `ntdll!RtlInitUnicodeString` at `0x18002d0df`
- `ntdll!RtlInitUnicodeString` at `0x18002d12f`
- `ntdll!RtlInitUnicodeString` at `0x18002d08d`
- `ntdll!RtlInitUnicodeString` at `0x18002d0df`
- `ntdll!RtlInitUnicodeString` at `0x18002d12f`

## string_xrefs

- `0x18002d0bd`: `shell\oobe\common\lib\autologon.cpp`
- `0x18002d107`: `shell\oobe\common\lib\autologon.cpp`

## pseudocode

```c
__int64 __fastcall _MoveLsaSecret(PCWSTR SourceString, PCWSTR a2)
{
  NTSTATUS v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  NTSTATUS v7; // eax
  NTSTATUS v8; // eax
  __int64 v9; // rdx
  NTSTATUS v10; // eax
  _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-60h] BYREF
  struct _UNICODE_STRING v13; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING v14; // [rsp+40h] [rbp-40h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  PLSA_UNICODE_STRING PrivateData; // [rsp+B0h] [rbp+30h] BYREF
  PVOID PolicyHandle; // [rsp+B8h] [rbp+38h] BYREF

  PolicyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v4 = LsaOpenPolicy(0, &ObjectAttributes, 0x24u, &PolicyHandle);
  v5 = v4 | 0x10000000;
  if ( v4 < 0 )
  {
    v6 = 138;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
      (const char *)v5,
      *(int *)&DestinationString.Length);
    goto LABEL_12;
  }
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  PrivateData = 0;
  v7 = LsaRetrievePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)&DestinationString, &PrivateData);
  v5 = v7 | 0x10000000;
  if ( v7 < 0 )
  {
    v6 = 145;
    goto LABEL_5;
  }
  v13 = 0;
  RtlInitUnicodeString(&v13, a2);
  v8 = LsaStorePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)&v13, PrivateData);
  v5 = v8 | 0x10000000;
  if ( v8 >= 0 )
  {
    v14 = 0;
    RtlInitUnicodeString(&v14, 0);
    v10 = LsaStorePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)&DestinationString, (PLSA_UNICODE_STRING)&v14);
    v5 = v10 | 0x10000000;
    if ( v10 >= 0 )
    {
      LsaFreeMemory(PrivateData);
      v5 = 0;
      goto LABEL_12;
    }
    v9 = 158;
  }
  else
  {
    v9 = 154;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
    (const char *)v5,
    *(int *)&DestinationString.Length);
  LsaFreeMemory(PrivateData);
LABEL_12:
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&PolicyHandle);
  return v5;
}

```

## disassembly

```asm
0x18002d020  mov     [rsp-18h+arg_0], rbx
0x18002d025  mov     [rsp-18h+arg_8], rsi
0x18002d02a  push    rbp
0x18002d02b  push    rdi
0x18002d02c  push    r14
0x18002d02e  mov     rbp, rsp
0x18002d031  sub     rsp, 80h
0x18002d038  xorps   xmm0, xmm0
0x18002d03b  mov     [rbp+PolicyHandle], 0
0x18002d043  mov     rsi, rdx
0x18002d046  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x18002d04a  mov     rdi, rcx
0x18002d04d  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x18002d051  xor     ecx, ecx; SystemName
0x18002d053  mov     r8d, 24h ; '$'; DesiredAccess
0x18002d059  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18002d05d  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18002d061  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18002d065  call    cs:__imp_LsaOpenPolicy
0x18002d06b  mov     ebx, eax
0x18002d06d  mov     r14d, 10000000h
0x18002d073  or      ebx, r14d
0x18002d076  jge     short loc_18002D07F
0x18002d078  mov     edx, 8Ah
0x18002d07d  jmp     short loc_18002D0B9
0x18002d07f  xorps   xmm0, xmm0
0x18002d082  lea     rcx, [rbp+DestinationString]; DestinationString
0x18002d086  mov     rdx, rdi; SourceString
0x18002d089  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18002d08d  call    cs:__imp_RtlInitUnicodeString
0x18002d093  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18002d097  lea     r8, [rbp+PrivateData]; PrivateData
0x18002d09b  lea     rdx, [rbp+DestinationString]; KeyName
0x18002d09f  mov     [rbp+PrivateData], 0
0x18002d0a7  call    cs:__imp_LsaRetrievePrivateData
0x18002d0ad  mov     ebx, eax
0x18002d0af  or      ebx, r14d
0x18002d0b2  jge     short loc_18002D0D1
0x18002d0b4  mov     edx, 91h; void *
0x18002d0b9  mov     rcx, [rbp+18h]; this
0x18002d0bd  lea     r8, aShellOobeCommo; "shell\\oobe\\common\\lib\\autologon.cpp"
0x18002d0c4  mov     r9d, ebx; char *
0x18002d0c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d0cc  jmp     loc_18002D161
0x18002d0d1  xorps   xmm0, xmm0
0x18002d0d4  lea     rcx, [rbp+var_50]; DestinationString
0x18002d0d8  mov     rdx, rsi; SourceString
0x18002d0db  movups  xmmword ptr [rbp+var_50.Length], xmm0
0x18002d0df  call    cs:__imp_RtlInitUnicodeString
0x18002d0e5  mov     r8, [rbp+PrivateData]; PrivateData
0x18002d0e9  lea     rdx, [rbp+var_50]; KeyName
0x18002d0ed  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18002d0f1  call    cs:__imp_LsaStorePrivateData
0x18002d0f7  mov     ebx, eax
0x18002d0f9  or      ebx, r14d
0x18002d0fc  jge     short loc_18002D122
0x18002d0fe  mov     edx, 9Ah; void *
0x18002d103  mov     rcx, [rbp+18h]; this
0x18002d107  lea     r8, aShellOobeCommo; "shell\\oobe\\common\\lib\\autologon.cpp"
0x18002d10e  mov     r9d, ebx; char *
0x18002d111  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d116  mov     rcx, [rbp+PrivateData]; Buffer
0x18002d11a  call    cs:__imp_LsaFreeMemory
0x18002d120  jmp     short loc_18002D161
0x18002d122  xorps   xmm0, xmm0
0x18002d125  lea     rcx, [rbp+var_40]; DestinationString
0x18002d129  xor     edx, edx; SourceString
0x18002d12b  movups  xmmword ptr [rbp+var_40.Length], xmm0
0x18002d12f  call    cs:__imp_RtlInitUnicodeString
0x18002d135  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18002d139  lea     r8, [rbp+var_40]; PrivateData
0x18002d13d  lea     rdx, [rbp+DestinationString]; KeyName
0x18002d141  call    cs:__imp_LsaStorePrivateData
0x18002d147  mov     ebx, eax
0x18002d149  or      ebx, r14d
0x18002d14c  jge     short loc_18002D155
0x18002d14e  mov     edx, 9Eh
0x18002d153  jmp     short loc_18002D103
0x18002d155  mov     rcx, [rbp+PrivateData]; Buffer
0x18002d159  call    cs:__imp_LsaFreeMemory
0x18002d15f  xor     ebx, ebx
0x18002d161  lea     rcx, [rbp+PolicyHandle]
0x18002d165  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002d16a  lea     r11, [rsp+80h+var_s0]
0x18002d172  mov     eax, ebx
0x18002d174  mov     rbx, [r11+20h]
0x18002d178  mov     rsi, [r11+28h]
0x18002d17c  mov     rsp, r11
0x18002d17f  pop     r14
0x18002d181  pop     rdi
0x18002d182  pop     rbp
0x18002d183  retn
```
