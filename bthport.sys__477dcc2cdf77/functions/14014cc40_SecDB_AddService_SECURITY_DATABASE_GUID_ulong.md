# SecDB_AddService(_SECURITY_DATABASE *,_GUID *,ulong)

- ea: `0x14014cc40`
- end: `0x14014cd61`
- name: `?SecDB_AddService@@YAJPEAU_SECURITY_DATABASE@@PEAU_GUID@@K@Z`
- size: `289`
- prototype: `int(struct _SECURITY_DATABASE *, struct _GUID *, unsigned int)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140148d5c`
- `0x1401498ac`
- `0x14014a634`

## callees

- `0x14000f27c`
- `0x14000fab4`
- `0x14014cb98`
- `0x14014cc40`
- `0x140165540`
- `0x140165940`
- `0x14020909c`
- `0x1402091b8`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x14014cd27`
- `ntoskrnl!ZwSetValueKey` at `0x14014cd27`
- `ntoskrnl!RtlInitUnicodeString` at `0x14014ccfc`
- `ntoskrnl!RtlInitUnicodeString` at `0x14014ccfc`

## string_xrefs

- `0x14014cc97`: `Services`
- `0x14014cced`: `SecurityFlags`

## pseudocode

```c
__int64 __fastcall SecDB_AddService(struct _SECURITY_DATABASE *a1, struct _GUID *a2, int a3)
{
  _QWORD *v5; // rax
  int Key; // ebx
  void **v7; // rax
  int Data; // [rsp+30h] [rbp-59h] BYREF
  HANDLE KeyHandle; // [rsp+38h] [rbp-51h] BYREF
  void *v11; // [rsp+40h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-41h] BYREF
  struct _UNICODE_STRING SourceString[6]; // [rsp+60h] [rbp-29h] BYREF

  Data = a3;
  memset(SourceString, 0, sizeof(SourceString));
  GS_Init(&SourceString[0].Length, a2);
  v11 = 0;
  v5 = (_QWORD *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(&v11);
  Key = BthOpenKeyBthPortParams((__int64)L"Services", v5);
  if ( Key >= 0 )
  {
    KeyHandle = 0;
    v7 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(&KeyHandle);
    Key = BthCreateKeyExSdEnforced(v11, &SourceString[5], v7, 0, 0);
    if ( Key >= 0 )
    {
      if ( !Data )
        Data = *(_DWORD *)a1;
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, L"SecurityFlags");
      Key = ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, &Data, 4u);
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&KeyHandle);
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v11);
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x14014cc40  push    rbp
0x14014cc42  push    rbx
0x14014cc43  push    rdi
0x14014cc44  lea     rbp, [rsp-47h]
0x14014cc49  sub     rsp, 0D0h
0x14014cc50  mov     rax, cs:__security_cookie
0x14014cc57  xor     rax, rsp
0x14014cc5a  mov     [rbp+57h+var_20], rax
0x14014cc5e  mov     rbx, rdx
0x14014cc61  mov     [rbp+57h+var_B0], r8d
0x14014cc65  xor     edx, edx; Val
0x14014cc67  mov     rdi, rcx
0x14014cc6a  lea     rcx, [rbp+57h+SourceString]; void *
0x14014cc6e  lea     r8d, [rdx+60h]; Size
0x14014cc72  call    memset
0x14014cc77  mov     rdx, rbx; struct _GUID *
0x14014cc7a  lea     rcx, [rbp+57h+SourceString]; SourceString
0x14014cc7e  call    ?GS_Init@@YAXPEAU_GUID_STRING@@PEAU_GUID@@@Z; GS_Init(_GUID_STRING *,_GUID *)
0x14014cc83  lea     rcx, [rbp+57h+var_A0]
0x14014cc87  mov     [rbp+57h+var_A0], 0
0x14014cc8f  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(void)
0x14014cc94  mov     rdx, rax
0x14014cc97  lea     rcx, aServices; "Services"
0x14014cc9e  call    BthOpenKeyBthPortParams
0x14014cca3  mov     ebx, eax
0x14014cca5  test    eax, eax
0x14014cca7  js      loc_14014CD3E
0x14014ccad  lea     rcx, [rbp+57h+KeyHandle]
0x14014ccb1  mov     [rbp+57h+KeyHandle], 0
0x14014ccb9  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(void)
0x14014ccbe  mov     rcx, [rbp+57h+var_A0]
0x14014ccc2  lea     rdx, [rbp+57h+var_30]
0x14014ccc6  xor     r9d, r9d
0x14014ccc9  mov     dword ptr [rsp+0E0h+Data], 0
0x14014ccd1  mov     r8, rax
0x14014ccd4  call    BthCreateKeyExSdEnforced
0x14014ccd9  mov     ebx, eax
0x14014ccdb  test    eax, eax
0x14014ccdd  js      short loc_14014CD35
0x14014ccdf  cmp     [rbp+57h+var_B0], 0
0x14014cce3  jnz     short loc_14014CCEA
0x14014cce5  mov     eax, [rdi]
0x14014cce7  mov     [rbp+57h+var_B0], eax
0x14014ccea  xorps   xmm0, xmm0
0x14014cced  lea     rdx, aSecurityflags; "SecurityFlags"
0x14014ccf4  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14014ccf8  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14014ccfc  call    cs:__imp_RtlInitUnicodeString
0x14014cd03  nop     dword ptr [rax+rax+00h]
0x14014cd08  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14014cd0c  lea     rax, [rbp+57h+var_B0]
0x14014cd10  mov     r9d, 4; Type
0x14014cd16  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x14014cd1a  mov     [rsp+0E0h+DataSize], r9d; DataSize
0x14014cd1f  xor     r8d, r8d; TitleIndex
0x14014cd22  mov     [rsp+0E0h+Data], rax; Data
0x14014cd27  call    cs:__imp_ZwSetValueKey
0x14014cd2e  nop     dword ptr [rax+rax+00h]
0x14014cd33  mov     ebx, eax
0x14014cd35  lea     rcx, [rbp+57h+KeyHandle]
0x14014cd39  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14014cd3e  lea     rcx, [rbp+57h+var_A0]
0x14014cd42  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14014cd47  mov     eax, ebx
0x14014cd49  mov     rcx, [rbp+57h+var_20]
0x14014cd4d  xor     rcx, rsp; StackCookie
0x14014cd50  call    __security_check_cookie
0x14014cd55  add     rsp, 0D0h
0x14014cd5c  pop     rdi
0x14014cd5d  pop     rbx
0x14014cd5e  pop     rbp
0x14014cd5f  retn
```
