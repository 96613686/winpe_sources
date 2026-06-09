# SystemSettings::DataModel::CopyCurrentUserSettings::IntlRegOpenCurrentUser(void)

- ea: `0x140044190`
- end: `0x14004427e`
- name: `?IntlRegOpenCurrentUser@CopyCurrentUserSettings@DataModel@SystemSettings@@CAPEAUHKEY__@@XZ`
- size: `238`
- prototype: `HKEY(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1400437e4`

## callees

- `0x140005f30`
- `0x14000ed38`
- `0x14002c070`
- `0x14002c2d4`
- `0x140044190`
- `0x14007d010`

## import_xrefs

- `KERNEL32!RegOpenCurrentUser` at `0x14004420c`
- `KERNEL32!RegOpenCurrentUser` at `0x14004420c`
- `ole32!CoGetCallContext` at `0x1400441c9`
- `ole32!CoGetCallContext` at `0x1400441c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HKEY SystemSettings::DataModel::CopyCurrentUserSettings::IntlRegOpenCurrentUser(void)
{
  HKEY *v0; // rax
  HKEY v1; // rbx
  __int64 v3; // [rsp+20h] [rbp-20h] BYREF
  void *ppInterface; // [rsp+28h] [rbp-18h] BYREF

  v3 = -2147483647;
  ppInterface = 0;
  if ( CoGetCallContext(&GUID_0000013e_0000_0000_c000_000000000046, &ppInterface) >= 0 )
  {
    if ( !(*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppInterface + 48LL))(ppInterface)
      && (*(int (__fastcall **)(void *))(*(_QWORD *)ppInterface + 32LL))(ppInterface) >= 0 )
    {
      v0 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v3);
      if ( RegOpenCurrentUser(0x20019u, v0) )
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &v3,
          -2147483647);
    }
    if ( ppInterface )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 40LL))(ppInterface);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 16LL))(ppInterface);
      ppInterface = 0;
    }
  }
  v1 = (HKEY)v3;
  v3 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>((HKEY *)&v3);
  return v1;
}

```

## disassembly

```asm
0x140044190  mov     [rsp-8+arg_0], rbx
0x140044195  push    rbp
0x140044196  mov     rbp, rsp
0x140044199  sub     rsp, 40h
0x14004419d  mov     rax, cs:__security_cookie
0x1400441a4  xor     rax, rsp
0x1400441a7  mov     [rbp+var_10], rax
0x1400441ab  mov     rbx, 0FFFFFFFF80000001h
0x1400441b2  mov     [rbp+var_20], rbx
0x1400441b6  mov     [rbp+ppInterface], 0
0x1400441be  lea     rdx, [rbp+ppInterface]; ppInterface
0x1400441c2  lea     rcx, _GUID_0000013e_0000_0000_c000_000000000046; riid
0x1400441c9  call    cs:__imp_CoGetCallContext
0x1400441cf  test    eax, eax
0x1400441d1  js      short loc_14004424F
0x1400441d3  mov     rcx, [rbp+ppInterface]
0x1400441d7  mov     rax, [rcx]
0x1400441da  mov     rax, [rax+30h]
0x1400441de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400441e3  test    eax, eax
0x1400441e5  jnz     short loc_140044222
0x1400441e7  mov     rcx, [rbp+ppInterface]
0x1400441eb  mov     rax, [rcx]
0x1400441ee  mov     rax, [rax+20h]
0x1400441f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400441f7  test    eax, eax
0x1400441f9  js      short loc_140044222
0x1400441fb  lea     rcx, [rbp+var_20]
0x1400441ff  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x140044204  mov     rdx, rax; phkResult
0x140044207  mov     ecx, 20019h; samDesired
0x14004420c  call    cs:__imp_RegOpenCurrentUser
0x140044212  test    eax, eax
0x140044214  jz      short loc_140044222
0x140044216  mov     rdx, rbx
0x140044219  lea     rcx, [rbp+var_20]
0x14004421d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x140044222  mov     rcx, [rbp+ppInterface]
0x140044226  test    rcx, rcx
0x140044229  jz      short loc_14004424F
0x14004422b  mov     rax, [rcx]
0x14004422e  mov     rax, [rax+28h]
0x140044232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044237  mov     rcx, [rbp+ppInterface]
0x14004423b  mov     rax, [rcx]
0x14004423e  mov     rax, [rax+10h]
0x140044242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044247  mov     [rbp+ppInterface], 0
0x14004424f  mov     rbx, [rbp+var_20]
0x140044253  mov     [rbp+var_20], 0
0x14004425b  lea     rcx, [rbp+var_20]
0x14004425f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140044264  mov     rax, rbx
0x140044267  mov     rcx, [rbp+var_10]
0x14004426b  xor     rcx, rsp; StackCookie
0x14004426e  call    __security_check_cookie
0x140044273  mov     rbx, [rsp+40h+arg_0]
0x140044278  add     rsp, 40h
0x14004427c  pop     rbp
0x14004427d  retn
```
