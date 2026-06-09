# Windows::Networking::UX::Internal::MBCategory::tp_UpdateReadyState(Windows::Networking::UX::MbCategoryReadyState)

- ea: `0x18000ead4`
- end: `0x18000ecb5`
- name: `?tp_UpdateReadyState@MBCategory@Internal@UX@Networking@Windows@@AEAAXW4MbCategoryReadyState@345@@Z`
- size: `481`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x18001a048`
- `0x18001dc70`
- `0x180046e14`

## callees

- `0x180008c84`
- `0x18000ad20`
- `0x18000ead4`
- `0x18000ecbc`
- `0x18000efa4`
- `0x18001a494`
- `0x18001a6e8`
- `0x18001bd80`
- `0x18001bdb8`
- `0x180024378`
- `0x18002d20c`
- `0x180059010`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18000eb37`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18000eb89`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18000eb37`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18000eb89`

## string_xrefs

- `0x18000eb67`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdateReadyState`
- `0x18000ebab`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdateReadyState`
- `0x18000ebda`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdateReadyState`
- `0x18000eb9f`: `old _readyState=%d, new _readyState=%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Networking::UX::Internal::MBCategory::tp_UpdateReadyState(__int64 a1, int a2)
{
  int v2; // ebx
  int WwanInterfaceObject; // ebx
  struct WWAN_INTERFACE_OBJECT *v5; // rcx
  struct WWAN_INTERFACE_OBJECT *v6; // rcx
  int v7; // r9d
  struct WWAN_INTERFACE_OBJECT *v8; // rax
  struct WWAN_INTERFACE_OBJECT *v9; // rdx
  __int64 *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  int v13; // [rsp+20h] [rbp-30h]
  struct WWAN_INTERFACE_OBJECT *v14; // [rsp+38h] [rbp-18h] BYREF
  char v15; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  struct WWAN_INTERFACE_OBJECT *v17; // [rsp+60h] [rbp+10h] BYREF
  struct WWAN_INTERFACE_OBJECT *v18; // [rsp+70h] [rbp+20h] BYREF

  v2 = a2;
  if ( (unsigned int)(a2 - 6) <= 1 )
  {
    v17 = 0;
    v14 = 0;
    v15 = 1;
    WwanInterfaceObject = Windows::Networking::UX::Internal::MBCategory::_GetWwanInterfaceObject(
                            (Windows::Networking::UX::Internal::MBCategory *)a1,
                            &v14);
    if ( v15 )
    {
      v5 = v17;
      v17 = v14;
      if ( v5 )
        WwanFreeMemory(v5);
    }
    if ( WwanInterfaceObject >= 0 && (v6 = v17) != 0 )
    {
      v2 = (*((_DWORD *)v17 + 258) != 0) + 6;
    }
    else
    {
      MBSettingUXLogging::Error(
        "Windows::Networking::UX::Internal::MBCategory::tp_UpdateReadyState",
        0xE41u,
        "Failed to do GetWwanInterfaceObject");
      v2 = 6;
      v6 = v17;
    }
    v17 = 0;
    if ( v6 )
      WwanFreeMemory(v6);
  }
  v7 = *(_DWORD *)(a1 + 604);
  if ( v7 != v2 )
  {
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MBCategory::tp_UpdateReadyState",
      3669,
      "old _readyState=%d, new _readyState=%d",
      v7,
      v2);
    *(_DWORD *)(a1 + 604) = v2;
    Windows::Networking::UX::Internal::MBCategory::tp_TryInitMbae((Windows::Networking::UX::Internal::MBCategory *)a1);
    if ( *(_DWORD *)(a1 + 604) == 3 )
    {
      MBSettingUXLogging::Info(
        "Windows::Networking::UX::Internal::MBCategory::tp_UpdateReadyState",
        3680,
        "Query PinState");
      Windows::Networking::UX::Internal::MBCategory::tp_GetPinState((Windows::Networking::UX::Internal::MBCategory *)a1);
    }
    Windows::Networking::UX::Internal::MBCategory::tp_RefreshInterface((HSTRING *)a1);
  }
  if ( *(_QWORD *)(a1 + 352) )
  {
    v8 = (struct WWAN_INTERFACE_OBJECT *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
    v9 = v8;
    v17 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 2;
      *(_QWORD *)v8 = &Windows::Networking::UX::Internal::MBReadyStateChangeEvent::`vftable';
    }
    else
    {
      v9 = 0;
    }
    v18 = v9;
    if ( v9 )
    {
      v10 = *(__int64 **)(a1 + 352);
      v11 = *v10;
      v18 = 0;
      v17 = v9;
      v12 = (*(__int64 (__fastcall **)(__int64 *, struct WWAN_INTERFACE_OBJECT **))(v11 + 72))(v10, &v17);
      if ( v12 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xE6D,
          (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
          (const char *)(unsigned int)v12,
          v13);
    }
    else
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0xE71,
        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
        (const char *)0x8007000ELL,
        v13);
    }
    std::unique_ptr<Windows::Networking::UX::Internal::MBStateMachineEvent>::~unique_ptr<Windows::Networking::UX::Internal::MBStateMachineEvent>(&v18);
  }
}

```

## disassembly

```asm
0x18000ead4  mov     [rsp-8+arg_8], rbx
0x18000ead9  mov     [rsp-8+arg_18], rdi
0x18000eade  push    rbp
0x18000eadf  mov     rbp, rsp
0x18000eae2  sub     rsp, 50h
0x18000eae6  mov     ebx, edx
0x18000eae8  mov     rdi, rcx
0x18000eaeb  lea     eax, [rdx-6]
0x18000eaee  cmp     eax, 1
0x18000eaf1  ja      loc_18000EB8F
0x18000eaf7  mov     [rbp+arg_0], 0
0x18000eaff  lea     rax, [rbp+arg_0]
0x18000eb03  mov     [rbp+var_20], rax
0x18000eb07  mov     [rbp+var_18], 0
0x18000eb0f  mov     [rbp+var_10], 1
0x18000eb13  lea     rdx, [rbp+var_18]; struct WWAN_INTERFACE_OBJECT **
0x18000eb17  call    ?_GetWwanInterfaceObject@MBCategory@Internal@UX@Networking@Windows@@AEAAJPEAPEAUWWAN_INTERFACE_OBJECT@@@Z; Windows::Networking::UX::Internal::MBCategory::_GetWwanInterfaceObject(WWAN_INTERFACE_OBJECT * *)
0x18000eb1c  mov     ebx, eax
0x18000eb1e  cmp     [rbp+var_10], 0
0x18000eb22  jz      short loc_18000EB3D
0x18000eb24  mov     r8, [rbp+var_20]
0x18000eb28  mov     rcx, [r8]
0x18000eb2b  mov     rdx, [rbp+var_18]
0x18000eb2f  mov     [r8], rdx
0x18000eb32  test    rcx, rcx
0x18000eb35  jz      short loc_18000EB3D
0x18000eb37  call    cs:__imp_WwanFreeMemory
0x18000eb3d  test    ebx, ebx
0x18000eb3f  js      short loc_18000EB5B
0x18000eb41  mov     rcx, [rbp+arg_0]
0x18000eb45  test    rcx, rcx
0x18000eb48  jz      short loc_18000EB5B
0x18000eb4a  mov     eax, [rcx+408h]
0x18000eb50  neg     eax
0x18000eb52  sbb     ebx, ebx
0x18000eb54  neg     ebx
0x18000eb56  add     ebx, 6
0x18000eb59  jmp     short loc_18000EB7C
0x18000eb5b  lea     r8, aFailedToDoGetw; "Failed to do GetWwanInterfaceObject"
0x18000eb62  mov     edx, 0E41h; unsigned int
0x18000eb67  lea     rcx, aWindowsNetwork_288; "Windows::Networking::UX::Internal::MBCa"...
0x18000eb6e  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x18000eb73  mov     ebx, 6
0x18000eb78  mov     rcx, [rbp+arg_0]
0x18000eb7c  mov     [rbp+arg_0], 0
0x18000eb84  test    rcx, rcx
0x18000eb87  jz      short loc_18000EB8F
0x18000eb89  call    cs:__imp_WwanFreeMemory
0x18000eb8f  mov     r9d, [rdi+25Ch]
0x18000eb96  cmp     r9d, ebx
0x18000eb99  jz      short loc_18000EBF6
0x18000eb9b  mov     [rsp+50h+var_30], ebx; int
0x18000eb9f  lea     r8, aOldReadystateD; "old _readyState=%d, new _readyState=%d"
0x18000eba6  mov     edx, 0E55h; unsigned int
0x18000ebab  lea     rcx, aWindowsNetwork_288; "Windows::Networking::UX::Internal::MBCa"...
0x18000ebb2  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18000ebb7  mov     [rdi+25Ch], ebx
0x18000ebbd  mov     rcx, rdi; this
0x18000ebc0  call    ?tp_TryInitMbae@MBCategory@Internal@UX@Networking@Windows@@AEAA_NXZ; Windows::Networking::UX::Internal::MBCategory::tp_TryInitMbae(void)
0x18000ebc5  cmp     dword ptr [rdi+25Ch], 3
0x18000ebcc  jnz     short loc_18000EBEE
0x18000ebce  lea     r8, aQueryPinstate; "Query PinState"
0x18000ebd5  mov     edx, 0E60h; unsigned int
0x18000ebda  lea     rcx, aWindowsNetwork_288; "Windows::Networking::UX::Internal::MBCa"...
0x18000ebe1  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18000ebe6  mov     rcx, rdi; this
0x18000ebe9  call    ?tp_GetPinState@MBCategory@Internal@UX@Networking@Windows@@AEAAXXZ; Windows::Networking::UX::Internal::MBCategory::tp_GetPinState(void)
0x18000ebee  mov     rcx, rdi; this
0x18000ebf1  call    ?tp_RefreshInterface@MBCategory@Internal@UX@Networking@Windows@@AEAAXXZ; Windows::Networking::UX::Internal::MBCategory::tp_RefreshInterface(void)
0x18000ebf6  cmp     qword ptr [rdi+160h], 0
0x18000ebfe  jz      loc_18000ECA5
0x18000ec04  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ec0b  mov     ecx, 10h; unsigned __int64
0x18000ec10  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ec15  mov     rdx, rax
0x18000ec18  mov     [rbp+arg_0], rax
0x18000ec1c  test    rax, rax
0x18000ec1f  jz      short loc_18000EC34
0x18000ec21  mov     dword ptr [rax+8], 2
0x18000ec28  lea     rax, ??_7MBReadyStateChangeEvent@Internal@UX@Networking@Windows@@6B@; const Windows::Networking::UX::Internal::MBReadyStateChangeEvent::`vftable'
0x18000ec2f  mov     [rdx], rax
0x18000ec32  jmp     short loc_18000EC36
0x18000ec34  xor     edx, edx
0x18000ec36  mov     [rbp+arg_10], rdx
0x18000ec3a  test    rdx, rdx
0x18000ec3d  jz      short loc_18000EC80
0x18000ec3f  mov     rcx, [rdi+160h]
0x18000ec46  mov     rax, [rcx]
0x18000ec49  mov     [rbp+arg_10], 0
0x18000ec51  mov     [rbp+arg_0], rdx
0x18000ec55  lea     rdx, [rbp+arg_0]
0x18000ec59  mov     rax, [rax+48h]
0x18000ec5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec62  mov     rcx, [rbp+8]; this
0x18000ec66  test    eax, eax
0x18000ec68  jns     short loc_18000EC9C
0x18000ec6a  mov     r9d, eax; char *
0x18000ec6d  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18000ec74  mov     edx, 0E6Dh; void *
0x18000ec79  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000ec7e  jmp     short loc_18000EC9C
0x18000ec80  mov     rcx, [rbp+8]; this
0x18000ec84  mov     r9d, 8007000Eh; char *
0x18000ec8a  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18000ec91  mov     edx, 0E71h; void *
0x18000ec96  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000ec9b  nop
0x18000ec9c  lea     rcx, [rbp+arg_10]
0x18000eca0  call    ??1?$unique_ptr@UMBStateMachineEvent@Internal@UX@Networking@Windows@@U?$default_delete@UMBStateMachineEvent@Internal@UX@Networking@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Networking::UX::Internal::MBStateMachineEvent>::~unique_ptr<Windows::Networking::UX::Internal::MBStateMachineEvent>(void)
0x18000eca5  mov     rbx, [rsp+50h+arg_8]
0x18000ecaa  mov     rdi, [rsp+50h+arg_18]
0x18000ecaf  add     rsp, 50h
0x18000ecb3  pop     rbp
0x18000ecb4  retn
```
