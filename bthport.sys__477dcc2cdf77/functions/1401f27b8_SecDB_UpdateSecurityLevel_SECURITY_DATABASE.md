# SecDB_UpdateSecurityLevel(_SECURITY_DATABASE *)

- ea: `0x1401f27b8`
- end: `0x1401f2878`
- name: `?SecDB_UpdateSecurityLevel@@YA?AW4_BTH_SECURITY_LEVEL@@PEAU_SECURITY_DATABASE@@@Z`
- size: `192`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140075de0`
- `0x1401d0b60`
- `0x1401f2694`

## callees

- `0x14000f27c`
- `0x14000fab4`
- `0x1401f27b8`
- `0x1402091b8`
- `0x1402093a8`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x1401f2857`
- `ntoskrnl!ZwSetValueKey` at `0x1401f2857`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401f2825`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401f2825`

## string_xrefs

- `0x1401f27f3`: `SecurityLevel`
- `0x1401f2814`: `SecurityLevel`

## pseudocode

```c
__int64 __fastcall SecDB_UpdateSecurityLevel(__int64 a1)
{
  _QWORD *v2; // rax
  int *Data; // rbx
  HANDLE v4; // rcx
  unsigned int v5; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF
  HANDLE KeyHandle; // [rsp+50h] [rbp+8h] BYREF

  KeyHandle = 0;
  v2 = (_QWORD *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(&KeyHandle);
  Data = (int *)(a1 + 4);
  if ( (int)BthOpenKeyBthPortParams(0, v2) >= 0 )
  {
    if ( (int)BthQueryKeyValue(KeyHandle) < 0 || *Data >= 3 )
    {
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, L"SecurityLevel");
      v4 = KeyHandle;
      *Data = 1;
      ZwSetValueKey(v4, &DestinationString, 0, 4u, Data, 4u);
    }
  }
  else
  {
    *Data = 1;
  }
  v5 = *Data;
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&KeyHandle);
  return v5;
}

```

## disassembly

```asm
0x1401f27b8  push    rbx
0x1401f27ba  sub     rsp, 40h
0x1401f27be  mov     rbx, rcx
0x1401f27c1  mov     [rsp+48h+KeyHandle], 0
0x1401f27ca  lea     rcx, [rsp+48h+KeyHandle]
0x1401f27cf  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(void)
0x1401f27d4  mov     rdx, rax
0x1401f27d7  xor     ecx, ecx
0x1401f27d9  add     rbx, 4
0x1401f27dd  call    BthOpenKeyBthPortParams
0x1401f27e2  test    eax, eax
0x1401f27e4  jns     short loc_1401F27EE
0x1401f27e6  mov     dword ptr [rbx], 1
0x1401f27ec  jmp     short loc_1401F2863
0x1401f27ee  mov     rcx, [rsp+48h+KeyHandle]; KeyHandle
0x1401f27f3  lea     rdx, aSecuritylevel; "SecurityLevel"
0x1401f27fa  mov     r9d, 4
0x1401f2800  mov     r8, rbx
0x1401f2803  call    BthQueryKeyValue
0x1401f2808  test    eax, eax
0x1401f280a  js      short loc_1401F2811
0x1401f280c  cmp     dword ptr [rbx], 3
0x1401f280f  jl      short loc_1401F2863
0x1401f2811  xorps   xmm0, xmm0
0x1401f2814  lea     rdx, aSecuritylevel; "SecurityLevel"
0x1401f281b  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x1401f2820  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x1401f2825  call    cs:__imp_RtlInitUnicodeString
0x1401f282c  nop     dword ptr [rax+rax+00h]
0x1401f2831  mov     rcx, [rsp+48h+KeyHandle]; KeyHandle
0x1401f2836  lea     rdx, [rsp+48h+DestinationString]; ValueName
0x1401f283b  mov     r9d, 4; Type
0x1401f2841  mov     [rsp+48h+DataSize], 4; DataSize
0x1401f2849  xor     r8d, r8d; TitleIndex
0x1401f284c  mov     dword ptr [rbx], 1
0x1401f2852  mov     [rsp+48h+Data], rbx; Data
0x1401f2857  call    cs:__imp_ZwSetValueKey
0x1401f285e  nop     dword ptr [rax+rax+00h]
0x1401f2863  mov     ebx, [rbx]
0x1401f2865  lea     rcx, [rsp+48h+KeyHandle]
0x1401f286a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1401f286f  mov     eax, ebx
0x1401f2871  add     rsp, 40h
0x1401f2875  pop     rbx
0x1401f2876  retn
```
