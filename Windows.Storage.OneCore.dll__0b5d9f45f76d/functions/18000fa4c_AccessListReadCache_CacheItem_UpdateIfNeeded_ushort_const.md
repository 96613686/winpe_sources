# AccessListReadCache::CacheItem::UpdateIfNeeded(ushort const *)

- ea: `0x18000fa4c`
- end: `0x18000fb9f`
- name: `?UpdateIfNeeded@CacheItem@AccessListReadCache@@QEAAJPEBG@Z`
- size: `339`
- prototype: `int(AccessListReadCache::CacheItem *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000f680`

## callees

- `0x180007fac`
- `0x18000c0c4`
- `0x18000c1d8`
- `0x18000d504`
- `0x18000d524`
- `0x18000f5c0`
- `0x18000f5cc`
- `0x18000fa4c`
- `0x1800110b0`
- `0x180011174`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fb23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fb41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fb23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fb41`

## string_xrefs

- `0x18000faa2`: `onecore\base\windows.storage\src\accesslistreadcache.cpp`
- `0x18000faf8`: `onecore\base\windows.storage\src\accesslistreadcache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AccessListReadCache::CacheItem::UpdateIfNeeded(
        AccessListReadCache::CacheItem *this,
        const unsigned __int16 *a2)
{
  int v3; // eax
  __int64 v4; // rdx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  const struct _FILETIME *v7; // rdx
  unsigned __int64 v8; // rax
  __int64 v9; // rdx
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r9
  _QWORD *v13; // rbx
  const unsigned __int16 *v14; // rdx
  __int64 v16; // [rsp+20h] [rbp-10h] BYREF
  HSTRING string; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  const WCHAR *v19; // [rsp+50h] [rbp+20h] BYREF
  HKEY hkey; // [rsp+58h] [rbp+28h] BYREF

  hkey = 0;
  v3 = WindowsStorage::Utilities::registry_open_key_nothrow(a2);
  v5 = v3;
  if ( v3 >= 0 )
  {
    v16 = 0;
    v3 = WindowsStorage::Utilities::registry_value_data_nothrow<_FILETIME,void>(hkey, v4, &v16);
    v5 = v3;
    if ( v3 < 0 )
    {
      v6 = 228;
      goto LABEL_5;
    }
    v8 = wil::FileTime::ToInt64((wil::FileTime *)&v16, v7);
    if ( v8 > *((_QWORD *)this + 1) )
    {
      *((_QWORD *)this + 1) = v8;
      v19 = 0;
      v10 = WindowsStorage::Utilities::registry_value_data_nothrow<unsigned short const *,void>(hkey, v9, (PVOID *)&v19);
      v5 = v10;
      if ( v10 < 0 )
      {
        v11 = 236;
LABEL_9:
        v12 = (unsigned int)v10;
LABEL_10:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v11,
          (unsigned int)"onecore\\base\\windows.storage\\src\\accesslistreadcache.cpp",
          (const char *)v12,
          v16);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v19);
        goto LABEL_17;
      }
      v13 = WindowsStorage::Utilities::NtObjectPath::TryFromFileName(&string, v19);
      WindowsDeleteString(*(HSTRING *)this);
      *(_QWORD *)this = 0;
      *(_QWORD *)this = *v13;
      *v13 = 0;
      WindowsDeleteString(string);
      if ( !*(_QWORD *)this )
      {
        v5 = -2147024894;
        v12 = 2147942402LL;
        v11 = 239;
        goto LABEL_10;
      }
      v10 = registry_value_data_nothrow(hkey, v14, (AccessListReadCache::CacheItem *)((char *)this + 16));
      v5 = v10;
      if ( v10 < 0 )
      {
        v11 = 241;
        goto LABEL_9;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v19);
    }
    v5 = 0;
    goto LABEL_17;
  }
  v6 = 225;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecore\\base\\windows.storage\\src\\accesslistreadcache.cpp",
    (const char *)(unsigned int)v3,
    v16);
LABEL_17:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return v5;
}

```

## disassembly

```asm
0x18000fa4c  mov     [rsp-8+arg_0], rbx
0x18000fa51  mov     [rsp-8+arg_8], rdi
0x18000fa56  push    rbp
0x18000fa57  mov     rbp, rsp
0x18000fa5a  sub     rsp, 30h
0x18000fa5e  mov     rdi, rcx
0x18000fa61  mov     [rbp+hkey], 0
0x18000fa69  lea     r8, [rbp+hkey]
0x18000fa6d  mov     rcx, rdx; SourceString
0x18000fa70  call    ?registry_open_key_nothrow@Utilities@WindowsStorage@@YAJPEBGKAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; WindowsStorage::Utilities::registry_open_key_nothrow(ushort const *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)
0x18000fa75  mov     ebx, eax
0x18000fa77  test    eax, eax
0x18000fa79  jns     short loc_18000FA82
0x18000fa7b  mov     edx, 0E1h
0x18000fa80  jmp     short loc_18000FAA2
0x18000fa82  mov     [rbp+var_10], 0
0x18000fa8a  lea     r8, [rbp+var_10]
0x18000fa8e  mov     rcx, [rbp+hkey]
0x18000fa92  call    ??$registry_value_data_nothrow@U_FILETIME@@X@Utilities@WindowsStorage@@YAJPEAUHKEY__@@PEBGPEAU_FILETIME@@@Z; WindowsStorage::Utilities::registry_value_data_nothrow<_FILETIME,void>(HKEY__ *,ushort const *,_FILETIME *)
0x18000fa97  mov     ebx, eax
0x18000fa99  test    eax, eax
0x18000fa9b  jns     short loc_18000FABA
0x18000fa9d  mov     edx, 0E4h; void *
0x18000faa2  lea     r8, aOnecoreBaseWin_6; "onecore\\base\\windows.storage\\src\\ac"...
0x18000faa9  mov     r9d, eax; char *
0x18000faac  mov     rcx, [rbp+8]; this
0x18000fab0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fab5  jmp     loc_18000FB84
0x18000faba  lea     rcx, [rbp+var_10]; this
0x18000fabe  call    ?ToInt64@FileTime@wil@@YA_KAEBU_FILETIME@@@Z; wil::FileTime::ToInt64(_FILETIME const &)
0x18000fac3  cmp     rax, [rdi+8]
0x18000fac7  jbe     loc_18000FB82
0x18000facd  mov     [rdi+8], rax
0x18000fad1  mov     [rbp+arg_10], 0
0x18000fad9  lea     r8, [rbp+arg_10]
0x18000fadd  mov     rcx, [rbp+hkey]; hkey
0x18000fae1  call    ??$registry_value_data_nothrow@PEBGX@Utilities@WindowsStorage@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; WindowsStorage::Utilities::registry_value_data_nothrow<ushort const *,void>(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18000fae6  mov     ebx, eax
0x18000fae8  test    eax, eax
0x18000faea  jns     short loc_18000FB10
0x18000faec  mov     edx, 0ECh; void *
0x18000faf1  mov     r9d, eax; char *
0x18000faf4  mov     rcx, [rbp+8]; this
0x18000faf8  lea     r8, aOnecoreBaseWin_6; "onecore\\base\\windows.storage\\src\\ac"...
0x18000faff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fb04  nop
0x18000fb05  lea     rcx, [rbp+arg_10]
0x18000fb09  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000fb0e  jmp     short loc_18000FB84
0x18000fb10  mov     rdx, [rbp+arg_10]
0x18000fb14  lea     rcx, [rbp+string]
0x18000fb18  call    ?TryFromFileName@NtObjectPath@Utilities@WindowsStorage@@SA?AV123@PEBG@Z; WindowsStorage::Utilities::NtObjectPath::TryFromFileName(ushort const *)
0x18000fb1d  mov     rbx, rax
0x18000fb20  mov     rcx, [rdi]; string
0x18000fb23  call    cs:__imp_WindowsDeleteString
0x18000fb29  mov     qword ptr [rdi], 0
0x18000fb30  mov     rcx, [rbx]
0x18000fb33  mov     [rdi], rcx
0x18000fb36  mov     qword ptr [rbx], 0
0x18000fb3d  mov     rcx, [rbp+string]; string
0x18000fb41  call    cs:__imp_WindowsDeleteString
0x18000fb47  cmp     qword ptr [rdi], 0
0x18000fb4b  jnz     short loc_18000FB5C
0x18000fb4d  mov     ebx, 80070002h
0x18000fb52  mov     r9d, ebx
0x18000fb55  mov     edx, 0EFh
0x18000fb5a  jmp     short loc_18000FAF4
0x18000fb5c  lea     r8, [rdi+10h]; enum SicfFlags *
0x18000fb60  mov     rcx, [rbp+hkey]; HKEY
0x18000fb64  call    ?registry_value_data_nothrow@@YAJPEAUHKEY__@@PEBGPEAW4SicfFlags@@@Z; registry_value_data_nothrow(HKEY__ *,ushort const *,SicfFlags *)
0x18000fb69  mov     ebx, eax
0x18000fb6b  test    eax, eax
0x18000fb6d  jns     short loc_18000FB79
0x18000fb6f  mov     edx, 0F1h
0x18000fb74  jmp     loc_18000FAF1
0x18000fb79  lea     rcx, [rbp+arg_10]
0x18000fb7d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000fb82  xor     ebx, ebx
0x18000fb84  lea     rcx, [rbp+hkey]
0x18000fb88  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000fb8d  mov     eax, ebx
0x18000fb8f  mov     rbx, [rsp+30h+arg_0]
0x18000fb94  mov     rdi, [rsp+30h+arg_8]
0x18000fb99  add     rsp, 30h
0x18000fb9d  pop     rbp
0x18000fb9e  retn
```
