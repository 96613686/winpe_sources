# AccessListReadCache::CacheItem::Initialize(ushort const *)

- ea: `0x18000e2fc`
- end: `0x18000e445`
- name: `?Initialize@CacheItem@AccessListReadCache@@QEAAJPEBG@Z`
- size: `329`
- prototype: `int(AccessListReadCache::CacheItem *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x1800102cc`

## callees

- `0x180007fac`
- `0x18000c0c4`
- `0x18000c1d8`
- `0x18000d504`
- `0x18000d524`
- `0x18000e2fc`
- `0x18000f5c0`
- `0x18000f5cc`
- `0x1800110b0`
- `0x180011174`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e3c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e3e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e3c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e3e7`

## string_xrefs

- `0x18000e352`: `onecore\base\windows.storage\src\accesslistreadcache.cpp`
- `0x18000e39e`: `onecore\base\windows.storage\src\accesslistreadcache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AccessListReadCache::CacheItem::Initialize(
        AccessListReadCache::CacheItem *this,
        const unsigned __int16 *a2)
{
  int v3; // eax
  __int64 v4; // rdx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  const struct _FILETIME *v7; // rdx
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r9
  _QWORD *v12; // rbx
  const unsigned __int16 *v13; // rdx
  __int64 v15; // [rsp+20h] [rbp-10h] BYREF
  HSTRING string; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  const WCHAR *v18; // [rsp+50h] [rbp+20h] BYREF
  HKEY hkey; // [rsp+58h] [rbp+28h] BYREF

  hkey = 0;
  v3 = WindowsStorage::Utilities::registry_open_key_nothrow(a2);
  v5 = v3;
  if ( v3 >= 0 )
  {
    v15 = 0;
    v3 = WindowsStorage::Utilities::registry_value_data_nothrow<_FILETIME,void>(hkey, v4, &v15);
    v5 = v3;
    if ( v3 < 0 )
    {
      v6 = 208;
      goto LABEL_5;
    }
    *((_QWORD *)this + 1) = wil::FileTime::ToInt64((wil::FileTime *)&v15, v7);
    v18 = 0;
    v9 = WindowsStorage::Utilities::registry_value_data_nothrow<unsigned short const *,void>(hkey, v8, (PVOID *)&v18);
    v5 = v9;
    if ( v9 >= 0 )
    {
      v12 = WindowsStorage::Utilities::NtObjectPath::TryFromFileName(&string, v18);
      WindowsDeleteString(*(HSTRING *)this);
      *(_QWORD *)this = 0;
      *(_QWORD *)this = *v12;
      *v12 = 0;
      WindowsDeleteString(string);
      if ( !*(_QWORD *)this )
      {
        v5 = -2147024894;
        v11 = 2147942402LL;
        v10 = 215;
        goto LABEL_9;
      }
      v9 = registry_value_data_nothrow(hkey, v13, (AccessListReadCache::CacheItem *)((char *)this + 16));
      v5 = v9;
      if ( v9 >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v18);
        v5 = 0;
        goto LABEL_15;
      }
      v10 = 217;
    }
    else
    {
      v10 = 212;
    }
    v11 = (unsigned int)v9;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\windows.storage\\src\\accesslistreadcache.cpp",
      (const char *)v11,
      v15);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v18);
    goto LABEL_15;
  }
  v6 = 205;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecore\\base\\windows.storage\\src\\accesslistreadcache.cpp",
    (const char *)(unsigned int)v3,
    v15);
LABEL_15:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return v5;
}

```

## disassembly

```asm
0x18000e2fc  mov     [rsp-8+arg_0], rbx
0x18000e301  mov     [rsp-8+arg_8], rdi
0x18000e306  push    rbp
0x18000e307  mov     rbp, rsp
0x18000e30a  sub     rsp, 30h
0x18000e30e  mov     rdi, rcx
0x18000e311  mov     [rbp+hkey], 0
0x18000e319  lea     r8, [rbp+hkey]
0x18000e31d  mov     rcx, rdx; SourceString
0x18000e320  call    ?registry_open_key_nothrow@Utilities@WindowsStorage@@YAJPEBGKAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; WindowsStorage::Utilities::registry_open_key_nothrow(ushort const *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)
0x18000e325  mov     ebx, eax
0x18000e327  test    eax, eax
0x18000e329  jns     short loc_18000E332
0x18000e32b  mov     edx, 0CDh
0x18000e330  jmp     short loc_18000E352
0x18000e332  mov     [rbp+var_10], 0
0x18000e33a  lea     r8, [rbp+var_10]
0x18000e33e  mov     rcx, [rbp+hkey]
0x18000e342  call    ??$registry_value_data_nothrow@U_FILETIME@@X@Utilities@WindowsStorage@@YAJPEAUHKEY__@@PEBGPEAU_FILETIME@@@Z; WindowsStorage::Utilities::registry_value_data_nothrow<_FILETIME,void>(HKEY__ *,ushort const *,_FILETIME *)
0x18000e347  mov     ebx, eax
0x18000e349  test    eax, eax
0x18000e34b  jns     short loc_18000E36A
0x18000e34d  mov     edx, 0D0h; void *
0x18000e352  lea     r8, aOnecoreBaseWin_6; "onecore\\base\\windows.storage\\src\\ac"...
0x18000e359  mov     r9d, eax; char *
0x18000e35c  mov     rcx, [rbp+8]; this
0x18000e360  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e365  jmp     loc_18000E42A
0x18000e36a  lea     rcx, [rbp+var_10]; this
0x18000e36e  call    ?ToInt64@FileTime@wil@@YA_KAEBU_FILETIME@@@Z; wil::FileTime::ToInt64(_FILETIME const &)
0x18000e373  mov     [rdi+8], rax
0x18000e377  mov     [rbp+arg_10], 0
0x18000e37f  lea     r8, [rbp+arg_10]
0x18000e383  mov     rcx, [rbp+hkey]; hkey
0x18000e387  call    ??$registry_value_data_nothrow@PEBGX@Utilities@WindowsStorage@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; WindowsStorage::Utilities::registry_value_data_nothrow<ushort const *,void>(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18000e38c  mov     ebx, eax
0x18000e38e  test    eax, eax
0x18000e390  jns     short loc_18000E3B6
0x18000e392  mov     edx, 0D4h; void *
0x18000e397  mov     r9d, eax; char *
0x18000e39a  mov     rcx, [rbp+8]; this
0x18000e39e  lea     r8, aOnecoreBaseWin_6; "onecore\\base\\windows.storage\\src\\ac"...
0x18000e3a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e3aa  nop
0x18000e3ab  lea     rcx, [rbp+arg_10]
0x18000e3af  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000e3b4  jmp     short loc_18000E42A
0x18000e3b6  mov     rdx, [rbp+arg_10]
0x18000e3ba  lea     rcx, [rbp+string]
0x18000e3be  call    ?TryFromFileName@NtObjectPath@Utilities@WindowsStorage@@SA?AV123@PEBG@Z; WindowsStorage::Utilities::NtObjectPath::TryFromFileName(ushort const *)
0x18000e3c3  mov     rbx, rax
0x18000e3c6  mov     rcx, [rdi]; string
0x18000e3c9  call    cs:__imp_WindowsDeleteString
0x18000e3cf  mov     qword ptr [rdi], 0
0x18000e3d6  mov     rcx, [rbx]
0x18000e3d9  mov     [rdi], rcx
0x18000e3dc  mov     qword ptr [rbx], 0
0x18000e3e3  mov     rcx, [rbp+string]; string
0x18000e3e7  call    cs:__imp_WindowsDeleteString
0x18000e3ed  cmp     qword ptr [rdi], 0
0x18000e3f1  jnz     short loc_18000E402
0x18000e3f3  mov     ebx, 80070002h
0x18000e3f8  mov     r9d, ebx
0x18000e3fb  mov     edx, 0D7h
0x18000e400  jmp     short loc_18000E39A
0x18000e402  lea     r8, [rdi+10h]; enum SicfFlags *
0x18000e406  mov     rcx, [rbp+hkey]; HKEY
0x18000e40a  call    ?registry_value_data_nothrow@@YAJPEAUHKEY__@@PEBGPEAW4SicfFlags@@@Z; registry_value_data_nothrow(HKEY__ *,ushort const *,SicfFlags *)
0x18000e40f  mov     ebx, eax
0x18000e411  test    eax, eax
0x18000e413  jns     short loc_18000E41F
0x18000e415  mov     edx, 0D9h
0x18000e41a  jmp     loc_18000E397
0x18000e41f  lea     rcx, [rbp+arg_10]
0x18000e423  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000e428  xor     ebx, ebx
0x18000e42a  lea     rcx, [rbp+hkey]
0x18000e42e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000e433  mov     eax, ebx
0x18000e435  mov     rbx, [rsp+30h+arg_0]
0x18000e43a  mov     rdi, [rsp+30h+arg_8]
0x18000e43f  add     rsp, 30h
0x18000e443  pop     rbp
0x18000e444  retn
```
