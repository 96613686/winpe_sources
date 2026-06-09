# ContainerManagerApi::AddNamedPipe(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong)

- ea: `0x180022360`
- end: `0x18002247e`
- name: `?AddNamedPipe@ContainerManagerApi@@UEAA?AW4AddNamedPipeResult@ICrossMachineCommunicationServices@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0K@Z`
- size: `286`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180021c80`
- `0x180021d9c`
- `0x180022360`
- `0x1800225a0`
- `0x1800225c8`
- `0x1800229f4`
- `0x180022a44`
- `0x180031540`

## import_xrefs

- `api-ms-win-containers-cmclient-l1-1-0!CmsMapNamedPipeToContainer` at `0x180022419`
- `api-ms-win-containers-cmclient-l1-1-0!CmsMapNamedPipeToContainer` at `0x180022419`

## string_xrefs

- `0x18002244b`: `onecore\windows\accessibletech\common\containermanagerapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ContainerManagerApi::AddNamedPipe(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  __int128 *started; // rbx
  _OWORD *v7; // rbx
  __int64 v8; // rcx
  int v9; // eax
  __int128 v11; // [rsp+20h] [rbp-29h] BYREF
  _BYTE v12[16]; // [rsp+30h] [rbp-19h] BYREF
  _BYTE v13[16]; // [rsp+40h] [rbp-9h] BYREF
  __int64 v14; // [rsp+50h] [rbp+7h]
  char v15; // [rsp+70h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v11 = 0;
  ThreadSafeMap<_GUID,ContainerManagerApi::ClientContainerActivityData>::GetValue((_Mtx_t)ContainerManagerApi::s_clientContainerActivities);
  if ( v15 )
  {
    v8 = *(_QWORD *)(v14 + 8);
  }
  else
  {
    started = (__int128 *)ContainerManagerApi::StartContainerActivitySynchronously(a1, v12);
    if ( &v11 != started )
    {
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void * &),&void CloseCmsContainer(void * &),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &v11,
        *(_QWORD *)started);
      *(_QWORD *)started = 0;
    }
    v7 = (__int128 *)((char *)started + 8);
    if ( (__int128 *)((char *)&v11 + 8) != v7 )
    {
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void * &),&void CloseCmsActivity(void * &),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        (char *)&v11 + 8,
        *(_QWORD *)v7);
      *(_QWORD *)v7 = 0;
    }
    ContainerManagerApi::ContainerActivityGuard::~ContainerActivityGuard((ContainerManagerApi::ContainerActivityGuard *)v12);
    v8 = *((_QWORD *)&v11 + 1);
  }
  if ( a3[3] > 7u )
    a3 = (_QWORD *)*a3;
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  v9 = CmsMapNamedPipeToContainer(v8, a2, a3);
  if ( v9 == -2147024713 )
  {
    std::_Optional_destruct_base<ContainerManagerApi::ClientContainerActivityData,0>::~_Optional_destruct_base<ContainerManagerApi::ClientContainerActivityData,0>(v13);
    ContainerManagerApi::ContainerActivityGuard::~ContainerActivityGuard((ContainerManagerApi::ContainerActivityGuard *)&v11);
    return 1;
  }
  else
  {
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x83,
        (unsigned int)"onecore\\windows\\accessibletech\\common\\containermanagerapi.cpp",
        (const char *)(unsigned int)v9,
        v11);
    std::_Optional_destruct_base<ContainerManagerApi::ClientContainerActivityData,0>::~_Optional_destruct_base<ContainerManagerApi::ClientContainerActivityData,0>(v13);
    ContainerManagerApi::ContainerActivityGuard::~ContainerActivityGuard((ContainerManagerApi::ContainerActivityGuard *)&v11);
    return 0;
  }
}

```

## disassembly

```asm
0x180022360  push    rbp
0x180022362  push    rbx
0x180022363  push    rsi
0x180022364  push    rdi
0x180022365  lea     rbp, [rsp-3Fh]
0x18002236a  sub     rsp, 88h
0x180022371  mov     rsi, r8
0x180022374  mov     rdi, rdx
0x180022377  mov     rbx, rcx
0x18002237a  xorps   xmm0, xmm0
0x18002237d  movdqu  [rbp+57h+var_80], xmm0
0x180022382  lea     r8, [rcx+8]
0x180022386  lea     rdx, [rbp+57h+var_60]
0x18002238a  lea     rcx, ?s_clientContainerActivities@ContainerManagerApi@@0V?$SmartLeak@V?$ThreadSafeMap@U_GUID@@UClientContainerActivityData@ContainerManagerApi@@@@@@A; _Mtx_t
0x180022391  call    ?GetValue@?$ThreadSafeMap@U_GUID@@UClientContainerActivityData@ContainerManagerApi@@@@QEBA?AV?$optional@UClientContainerActivityData@ContainerManagerApi@@@std@@AEBU_GUID@@@Z; ThreadSafeMap<_GUID,ContainerManagerApi::ClientContainerActivityData>::GetValue(_GUID const &)
0x180022396  nop
0x180022397  cmp     [rbp+57h+var_30], 0
0x18002239b  jnz     short loc_1800223F7
0x18002239d  lea     rdx, [rbp+57h+var_70]
0x1800223a1  mov     rcx, rbx
0x1800223a4  call    ?StartContainerActivitySynchronously@ContainerManagerApi@@QEAA?AVContainerActivityGuard@1@W4_CMS_CLIENT_ID@@W4_CMS_ACTIVITY_ID@@@Z; ContainerManagerApi::StartContainerActivitySynchronously(_CMS_CLIENT_ID,_CMS_ACTIVITY_ID)
0x1800223a9  mov     rbx, rax
0x1800223ac  lea     rax, [rbp+57h+var_80]
0x1800223b0  cmp     rax, rbx
0x1800223b3  jz      short loc_1800223C8
0x1800223b5  mov     rdx, [rbx]
0x1800223b8  lea     rcx, [rbp+57h+var_80]
0x1800223bc  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXAEAPEAX@Z$1?CloseCmsContainer@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void * &),&CloseCmsContainer(void * &),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800223c1  mov     qword ptr [rbx], 0
0x1800223c8  add     rbx, 8
0x1800223cc  lea     rax, [rbp+57h+var_80+8]
0x1800223d0  cmp     rax, rbx
0x1800223d3  jz      short loc_1800223E8
0x1800223d5  mov     rdx, [rbx]
0x1800223d8  lea     rcx, [rbp+57h+var_80+8]
0x1800223dc  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXAEAPEAX@Z$1?CloseCmsActivity@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void * &),&CloseCmsActivity(void * &),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800223e1  mov     qword ptr [rbx], 0
0x1800223e8  lea     rcx, [rbp+57h+var_70]; this
0x1800223ec  call    ??1ContainerActivityGuard@ContainerManagerApi@@QEAA@XZ; ContainerManagerApi::ContainerActivityGuard::~ContainerActivityGuard(void)
0x1800223f1  mov     rcx, qword ptr [rbp+57h+var_80+8]
0x1800223f5  jmp     short loc_1800223FF
0x1800223f7  mov     rax, [rbp+57h+var_50]
0x1800223fb  mov     rcx, [rax+8]
0x1800223ff  cmp     qword ptr [rsi+18h], 7
0x180022404  jbe     short loc_180022409
0x180022406  mov     rsi, [rsi]
0x180022409  cmp     qword ptr [rdi+18h], 7
0x18002240e  jbe     short loc_180022413
0x180022410  mov     rdi, [rdi]
0x180022413  mov     r8, rsi
0x180022416  mov     rdx, rdi
0x180022419  call    cs:__imp_CmsMapNamedPipeToContainer
0x18002241f  cmp     eax, 800700B7h
0x180022424  jnz     short loc_180022440
0x180022426  lea     rcx, [rbp+57h+var_60]
0x18002242a  call    ??1?$_Optional_destruct_base@UClientContainerActivityData@ContainerManagerApi@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<ContainerManagerApi::ClientContainerActivityData,0>::~_Optional_destruct_base<ContainerManagerApi::ClientContainerActivityData,0>(void)
0x18002242f  nop
0x180022430  lea     rcx, [rbp+57h+var_80]; this
0x180022434  call    ??1ContainerActivityGuard@ContainerManagerApi@@QEAA@XZ; ContainerManagerApi::ContainerActivityGuard::~ContainerActivityGuard(void)
0x180022439  mov     eax, 1
0x18002243e  jmp     short loc_180022472
0x180022440  mov     rcx, [rbp+5Fh]; this
0x180022444  test    eax, eax
0x180022446  jns     short loc_18002245D
0x180022448  mov     r9d, eax; char *
0x18002244b  lea     r8, aOnecoreWindows_19; "onecore\\windows\\accessibletech\\commo"...
0x180022452  mov     edx, 83h; void *
0x180022457  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002245d  lea     rcx, [rbp+57h+var_60]
0x180022461  call    ??1?$_Optional_destruct_base@UClientContainerActivityData@ContainerManagerApi@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<ContainerManagerApi::ClientContainerActivityData,0>::~_Optional_destruct_base<ContainerManagerApi::ClientContainerActivityData,0>(void)
0x180022466  nop
0x180022467  lea     rcx, [rbp+57h+var_80]; this
0x18002246b  call    ??1ContainerActivityGuard@ContainerManagerApi@@QEAA@XZ; ContainerManagerApi::ContainerActivityGuard::~ContainerActivityGuard(void)
0x180022470  xor     eax, eax
0x180022472  add     rsp, 88h
0x180022479  pop     rdi
0x18002247a  pop     rsi
0x18002247b  pop     rbx
0x18002247c  pop     rbp
0x18002247d  retn
```
