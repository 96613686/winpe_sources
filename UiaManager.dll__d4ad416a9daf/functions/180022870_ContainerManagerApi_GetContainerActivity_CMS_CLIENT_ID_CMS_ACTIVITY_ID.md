# ContainerManagerApi::GetContainerActivity(_CMS_CLIENT_ID,_CMS_ACTIVITY_ID)

- ea: `0x180022870`
- end: `0x18002299e`
- name: `?GetContainerActivity@ContainerManagerApi@@QEAA?AVContainerActivityGuard@1@W4_CMS_CLIENT_ID@@W4_CMS_ACTIVITY_ID@@@Z`
- size: `302`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180021c80`
- `0x180021e50`
- `0x180022484`

## callees

- `0x180022870`
- `0x1800229a4`
- `0x1800229cc`
- `0x1800229f4`
- `0x180022a44`
- `0x180031540`

## import_xrefs

- `api-ms-win-containers-cmclient-l1-2-0!CmsRegisterForContainerNotifications` at `0x1800228da`
- `api-ms-win-containers-cmclient-l1-2-0!CmsRegisterForContainerNotifications` at `0x1800228da`
- `api-ms-win-containers-cmclient-l1-2-0!CmsCreateActivity` at `0x18002291a`
- `api-ms-win-containers-cmclient-l1-2-0!CmsCreateActivity` at `0x18002291a`
- `api-ms-win-containers-cmclient-l1-5-0!CmsOpenContainer` at `0x1800228a9`
- `api-ms-win-containers-cmclient-l1-5-0!CmsOpenContainer` at `0x1800228a9`

## string_xrefs

- `0x1800228ba`: `onecore\windows\accessibletech\common\containermanagerapi.cpp`
- `0x1800228eb`: `onecore\windows\accessibletech\common\containermanagerapi.cpp`
- `0x18002292b`: `onecore\windows\accessibletech\common\containermanagerapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall ContainerManagerApi::GetContainerActivity(__int64 a1, _QWORD *a2, __int64 a3, unsigned int a4)
{
  int v7; // eax
  int v8; // eax
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rax
  int v13; // [rsp+20h] [rbp-28h]
  __int64 v14; // [rsp+28h] [rbp-20h] BYREF
  __int64 v15; // [rsp+30h] [rbp-18h] BYREF
  __int64 v16; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  __int64 v18; // [rsp+70h] [rbp+28h] BYREF

  v18 = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void * &),&void CloseCmsContainer(void * &),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &v18,
    0);
  v7 = CmsOpenContainer(a1 + 8, 10, 97, &v18);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x181,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\containermanagerapi.cpp",
      (const char *)(unsigned int)v7,
      v13);
  v8 = CmsRegisterForContainerNotifications(
         v18,
         std::_Ref_count_obj2<HrResponse<GetHwndParentService::ResponsePayload>>::_Destroy,
         0);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x191,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\containermanagerapi.cpp",
      (const char *)(unsigned int)v8,
      v13);
  v14 = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void * &),&void CloseCmsActivity(void * &),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &v14,
    0);
  v9 = CmsCreateActivity(v18, a4, &v14);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x198,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\containermanagerapi.cpp",
      (const char *)(unsigned int)v9,
      v13);
  v10 = v14;
  v14 = 0;
  v11 = v18;
  v18 = 0;
  *a2 = v11;
  v15 = 0;
  a2[1] = v10;
  v16 = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void * &),&void CloseCmsContainer(void * &),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void * &),&void CloseCmsContainer(void * &),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v15);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void * &),&void CloseCmsActivity(void * &),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void * &),&void CloseCmsActivity(void * &),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v16);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void * &),&void CloseCmsActivity(void * &),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void * &),&void CloseCmsActivity(void * &),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v14);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void * &),&void CloseCmsContainer(void * &),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void * &),&void CloseCmsContainer(void * &),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v18);
  return a2;
}

```

## disassembly

```asm
0x180022870  push    rbp
0x180022872  push    rbx
0x180022873  push    rsi
0x180022874  push    rdi
0x180022875  mov     rbp, rsp
0x180022878  sub     rsp, 48h
0x18002287c  mov     esi, r9d
0x18002287f  mov     rdi, rdx
0x180022882  mov     rbx, rcx
0x180022885  mov     [rbp+arg_0], 0
0x18002288d  xor     edx, edx
0x18002288f  lea     rcx, [rbp+arg_0]
0x180022893  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXAEAPEAX@Z$1?CloseCmsContainer@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void * &),&CloseCmsContainer(void * &),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180022898  lea     rcx, [rbx+8]
0x18002289c  lea     r9, [rbp+arg_0]
0x1800228a0  mov     edx, 0Ah
0x1800228a5  lea     r8d, [rdx+57h]
0x1800228a9  call    cs:__imp_CmsOpenContainer
0x1800228af  mov     rcx, [rbp+20h]; this
0x1800228b3  test    eax, eax
0x1800228b5  jns     short loc_1800228CC
0x1800228b7  mov     r9d, eax; char *
0x1800228ba  lea     r8, aOnecoreWindows_19; "onecore\\windows\\accessibletech\\commo"...
0x1800228c1  mov     edx, 181h; void *
0x1800228c6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800228cc  xor     r8d, r8d
0x1800228cf  lea     rdx, ?_Destroy@?$_Ref_count_obj2@U?$HrResponse@UResponsePayload@GetHwndParentService@@@@@std@@EEAAXXZ; std::_Ref_count_obj2<HrResponse<GetHwndParentService::ResponsePayload>>::_Destroy(void)
0x1800228d6  mov     rcx, [rbp+arg_0]
0x1800228da  call    cs:__imp_CmsRegisterForContainerNotifications
0x1800228e0  mov     rcx, [rbp+20h]; this
0x1800228e4  test    eax, eax
0x1800228e6  jns     short loc_1800228FD
0x1800228e8  mov     r9d, eax; char *
0x1800228eb  lea     r8, aOnecoreWindows_19; "onecore\\windows\\accessibletech\\commo"...
0x1800228f2  mov     edx, 191h; void *
0x1800228f7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800228fd  mov     [rbp+var_20], 0
0x180022905  xor     edx, edx
0x180022907  lea     rcx, [rbp+var_20]
0x18002290b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXAEAPEAX@Z$1?CloseCmsActivity@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void * &),&CloseCmsActivity(void * &),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180022910  lea     r8, [rbp+var_20]
0x180022914  mov     edx, esi
0x180022916  mov     rcx, [rbp+arg_0]
0x18002291a  call    cs:__imp_CmsCreateActivity
0x180022920  mov     rcx, [rbp+20h]; this
0x180022924  test    eax, eax
0x180022926  jns     short loc_18002293D
0x180022928  mov     r9d, eax; char *
0x18002292b  lea     r8, aOnecoreWindows_19; "onecore\\windows\\accessibletech\\commo"...
0x180022932  mov     edx, 198h; void *
0x180022937  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002293d  mov     rcx, [rbp+var_20]
0x180022941  mov     [rbp+var_20], 0
0x180022949  mov     rax, [rbp+arg_0]
0x18002294d  mov     [rbp+arg_0], 0
0x180022955  mov     [rdi], rax
0x180022958  mov     [rbp+var_18], 0
0x180022960  mov     [rdi+8], rcx
0x180022964  mov     [rbp+var_10], 0
0x18002296c  lea     rcx, [rbp+var_18]
0x180022970  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXAEAPEAX@Z$1?CloseCmsContainer@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void * &),&CloseCmsContainer(void * &),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void * &),&CloseCmsContainer(void * &),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180022975  lea     rcx, [rbp+var_10]
0x180022979  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXAEAPEAX@Z$1?CloseCmsActivity@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void * &),&CloseCmsActivity(void * &),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void * &),&CloseCmsActivity(void * &),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002297e  nop
0x18002297f  lea     rcx, [rbp+var_20]
0x180022983  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXAEAPEAX@Z$1?CloseCmsActivity@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void * &),&CloseCmsActivity(void * &),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void * &),&CloseCmsActivity(void * &),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180022988  nop
0x180022989  lea     rcx, [rbp+arg_0]
0x18002298d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXAEAPEAX@Z$1?CloseCmsContainer@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void * &),&CloseCmsContainer(void * &),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void * &),&CloseCmsContainer(void * &),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180022992  mov     rax, rdi
0x180022995  add     rsp, 48h
0x180022999  pop     rdi
0x18002299a  pop     rsi
0x18002299b  pop     rbx
0x18002299c  pop     rbp
0x18002299d  retn
```
