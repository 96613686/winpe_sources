# StateRepository::Globals::Initialize(long (*)(StateRepository::Partition,ushort * *),ushort const *,ushort const *,ushort const *,StateRepository::Globals::Flags)

- ea: `0x180023ba8`
- end: `0x180023cc5`
- name: `?Initialize@Globals@StateRepository@@YAJP6AJW4Partition@2@PEAPEAG@ZPEBG33W4Flags@12@@Z`
- size: `285`
- prototype: `int __high(int (__high *)(enum StateRepository::Partition, unsigned __int16 **), const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, enum StateRepository::Globals::Flags)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180016dcc`

## callees

- `0x18000a3c0`
- `0x18000f3e8`
- `0x18000f6e0`
- `0x1800156d4`
- `0x18002319c`
- `0x180023ba8`
- `0x1800242dc`

## string_xrefs

- `0x180023bc2`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180023be0`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`

## pseudocode

```c
__int64 StateRepository::Globals::Initialize(StateRepository::Security *a1, void *a2, __int64 a3, ...)
{
  int DefaultAccountSid; // eax
  int Settings; // ebx
  __int64 v5; // rdx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v9; // [rsp+48h] [rbp+20h] BYREF
  va_list va; // [rsp+48h] [rbp+20h]
  __int64 v11; // [rsp+50h] [rbp+28h]
  va_list va1; // [rsp+58h] [rbp+30h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v9 = va_arg(va1, _QWORD);
  v11 = va_arg(va1, _QWORD);
  DefaultAccountSid = StateRepository::Security::CreateDefaultAccountSid(a1, a2);
  Settings = DefaultAccountSid;
  if ( DefaultAccountSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC0,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)(unsigned int)DefaultAccountSid,
      v7);
    v5 = 203;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)(unsigned int)Settings,
      v7);
    return (unsigned int)Settings;
  }
  qword_18004C170 = (__int64)&StateRepository::GetPartitionDatabaseFilename;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    (__int64 *)va,
    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AppModel\\StateRepository");
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    &lpSubKey,
    (__int64 *)va);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((__int64 *)va);
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    (__int64 *)va,
    L"StateRepositoryStatus");
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    &qword_18004C158,
    (__int64 *)va);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((__int64 *)va);
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    (__int64 *)va,
    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AppModel\\StateRepositoryStatus");
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    &qword_18004C160,
    (__int64 *)va);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((__int64 *)va);
  qword_18004BF48 = qword_18004C158;
  qword_18004BF50 = qword_18004C160;
  Settings = StateRepository::Globals::LoadSettings(v11);
  if ( Settings < 0 )
  {
    v5 = 211;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180023ba8  mov     [rsp+arg_18], r9
0x180023bad  push    rbx; int
0x180023bae  sub     rsp, 20h
0x180023bb2  call    ?CreateDefaultAccountSid@Security@StateRepository@@YAJPEAXK@Z; StateRepository::Security::CreateDefaultAccountSid(void *,ulong)
0x180023bb7  mov     ebx, eax
0x180023bb9  test    eax, eax
0x180023bbb  jns     short loc_180023BF6
0x180023bbd  mov     rcx, [rsp+28h]; this
0x180023bc2  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appmodel\\staterepositor"...
0x180023bc9  mov     r9d, eax; char *
0x180023bcc  mov     edx, 0C0h; void *
0x180023bd1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023bd6  mov     edx, 0CBh; void *
0x180023bdb  mov     rcx, [rsp+28h]; this
0x180023be0  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appmodel\\staterepositor"...
0x180023be7  mov     r9d, ebx; char *
0x180023bea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023bef  mov     eax, ebx
0x180023bf1  jmp     loc_180023CBF
0x180023bf6  lea     rax, ?GetPartitionDatabaseFilename@StateRepository@@YAJW4Partition@1@PEAPEAG@Z; StateRepository::GetPartitionDatabaseFilename(StateRepository::Partition,ushort * *)
0x180023bfd  lea     rdx, ?stateRepositoryRegistrySubkey@StateRepository@@3QBGB; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180023c04  mov     cs:qword_18004C170, rax
0x180023c0b  lea     rcx, [rsp+28h+arg_18]
0x180023c10  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180023c15  lea     rdx, [rsp+28h+arg_18]
0x180023c1a  lea     rcx, lpSubKey
0x180023c21  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180023c26  lea     rcx, [rsp+28h+arg_18]
0x180023c2b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180023c30  lea     rdx, ?stateRepositoryRegistryStatusStateSeparationId@StateRepository@@3QBGB; "StateRepositoryStatus"
0x180023c37  lea     rcx, [rsp+28h+arg_18]
0x180023c3c  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180023c41  lea     rdx, [rsp+28h+arg_18]
0x180023c46  lea     rcx, qword_18004C158
0x180023c4d  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180023c52  lea     rcx, [rsp+28h+arg_18]
0x180023c57  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180023c5c  lea     rdx, ?stateRepositoryRegistryStatusStateSeparationDefaultSubkey@StateRepository@@3QBGB; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180023c63  lea     rcx, [rsp+28h+arg_18]
0x180023c68  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180023c6d  lea     rdx, [rsp+28h+arg_18]
0x180023c72  lea     rcx, qword_18004C160
0x180023c79  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180023c7e  lea     rcx, [rsp+28h+arg_18]
0x180023c83  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180023c88  mov     rax, cs:qword_18004C158
0x180023c8f  mov     ecx, dword ptr [rsp+28h+arg_20]
0x180023c93  mov     cs:qword_18004BF48, rax
0x180023c9a  mov     rax, cs:qword_18004C160
0x180023ca1  mov     cs:qword_18004BF50, rax
0x180023ca8  call    ?LoadSettings@Globals@StateRepository@@YAJW4Flags@12@@Z; StateRepository::Globals::LoadSettings(StateRepository::Globals::Flags)
0x180023cad  mov     ebx, eax
0x180023caf  test    eax, eax
0x180023cb1  jns     short loc_180023CBD
0x180023cb3  mov     edx, 0D3h
0x180023cb8  jmp     loc_180023BDB
0x180023cbd  xor     eax, eax
0x180023cbf  add     rsp, 20h
0x180023cc3  pop     rbx
0x180023cc4  retn
```
