# WindowsStorage::Utilities::registry_open_key_nothrow(ushort const *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)

- ea: `0x1800110b0`
- end: `0x18001116c`
- name: `?registry_open_key_nothrow@Utilities@WindowsStorage@@YAJPEBGKAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `188`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000e2fc`
- `0x18000fa4c`

## callees

- `0x18000d35c`
- `0x18000f01c`
- `0x1800110b0`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x1800110d1`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800110d1`
- `ntdll!NtOpenKey` at `0x18001113a`
- `ntdll!NtOpenKey` at `0x18001113a`

## string_xrefs

- `0x1800110e7`: `onecore\base\windows.storage\src\Registry.h`

## pseudocode

```c
int __fastcall WindowsStorage::Utilities::registry_open_key_nothrow(PCWSTR SourceString, __int64 a2, __int64 a3)
{
  NTSTATUS inited; // eax
  unsigned __int64 v5; // r9
  __int64 v6; // rdx
  NTSTATUS v8; // ebx
  _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-60h] BYREF
  __int64 v10; // [rsp+30h] [rbp-50h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-48h] BYREF
  char v12; // [rsp+40h] [rbp-40h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  DestinationString = 0;
  inited = RtlInitUnicodeStringEx(&DestinationString, SourceString);
  if ( inited < 0 )
  {
    v5 = (unsigned int)inited;
    v6 = 53;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v6,
             (unsigned int)"onecore\\base\\windows.storage\\src\\Registry.h",
             (const char *)v5,
             *(int *)&DestinationString.Length);
  }
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = 0;
  v10 = a3;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  KeyHandle = 0;
  v12 = 1;
  v8 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  wil::details::out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v10);
  if ( v8 < 0 )
  {
    v5 = (unsigned int)v8;
    v6 = 57;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v6,
             (unsigned int)"onecore\\base\\windows.storage\\src\\Registry.h",
             (const char *)v5,
             *(int *)&DestinationString.Length);
  }
  return 0;
}

```

## disassembly

```asm
0x1800110b0  mov     [rsp-8+arg_0], rbx
0x1800110b5  push    rbp
0x1800110b6  mov     rbp, rsp
0x1800110b9  sub     rsp, 80h
0x1800110c0  xorps   xmm0, xmm0
0x1800110c3  mov     rdx, rcx; SourceString
0x1800110c6  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800110ca  mov     rbx, r8
0x1800110cd  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800110d1  call    cs:__imp_RtlInitUnicodeStringEx
0x1800110d7  test    eax, eax
0x1800110d9  jns     short loc_1800110F5
0x1800110db  mov     r9d, eax; char *
0x1800110de  mov     edx, 35h ; '5'; void *
0x1800110e3  mov     rcx, [rbp+8]; this
0x1800110e7  lea     r8, aOnecoreBaseWin_7; "onecore\\base\\windows.storage\\src\\Re"...
0x1800110ee  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800110f3  jmp     short loc_18001115B
0x1800110f5  lea     rax, [rbp+DestinationString]
0x1800110f9  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x180011101  xorps   xmm0, xmm0
0x180011104  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180011108  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18001110c  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180011114  mov     edx, 20019h; DesiredAccess
0x180011119  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180011121  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180011125  mov     [rbp+var_50], rbx
0x180011129  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18001112e  mov     [rbp+KeyHandle], 0
0x180011136  mov     [rbp+var_40], 1
0x18001113a  call    cs:__imp_NtOpenKey
0x180011140  lea     rcx, [rbp+var_50]
0x180011144  mov     ebx, eax
0x180011146  call    ??1?$out_param_ptr_t@PEAPEAXV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18001114b  test    ebx, ebx
0x18001114d  jns     short loc_180011159
0x18001114f  mov     r9d, ebx
0x180011152  mov     edx, 39h ; '9'
0x180011157  jmp     short loc_1800110E3
0x180011159  xor     eax, eax
0x18001115b  mov     rbx, [rsp+80h+arg_0]
0x180011163  add     rsp, 80h
0x18001116a  pop     rbp
0x18001116b  retn
```
