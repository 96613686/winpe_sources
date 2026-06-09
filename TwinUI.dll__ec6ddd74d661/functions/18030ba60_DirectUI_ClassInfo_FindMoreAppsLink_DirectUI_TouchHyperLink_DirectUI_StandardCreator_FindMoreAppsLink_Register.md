# DirectUI::ClassInfo<FindMoreAppsLink,DirectUI::TouchHyperLink,DirectUI::StandardCreator<FindMoreAppsLink>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)

- ea: `0x18030ba60`
- end: `0x18030bbb6`
- name: `?Register@?$ClassInfo@VFindMoreAppsLink@@VTouchHyperLink@DirectUI@@V?$StandardCreator@VFindMoreAppsLink@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z`
- size: `342`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18030c400`

## callees

- `0x180309cd8`
- `0x18030ba60`
- `0x1803bb010`

## import_xrefs

- `DUI70!?Register@TouchHyperLink@DirectUI@@SAJXZ` at `0x18030ba89`
- `DUI70!?Register@TouchHyperLink@DirectUI@@SAJXZ` at `0x18030ba89`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x18030ba78`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x18030baa0`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x18030bae6`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x18030ba78`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x18030baa0`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x18030bae6`
- `DUI70!??0CritSecLock@DirectUI@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18030bad1`
- `DUI70!??0CritSecLock@DirectUI@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18030bad1`
- `DUI70!?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ` at `0x18030babd`
- `DUI70!?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ` at `0x18030babd`
- `DUI70!??1CritSecLock@DirectUI@@QEAA@XZ` at `0x18030bb9c`
- `DUI70!??1CritSecLock@DirectUI@@QEAA@XZ` at `0x18030bb9c`
- `DUI70!?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z` at `0x18030bb1c`
- `DUI70!?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z` at `0x18030bb1c`
- `DUI70!?Register@ClassInfoBase@DirectUI@@QEAAJXZ` at `0x18030bb5d`
- `DUI70!?Register@ClassInfoBase@DirectUI@@QEAAJXZ` at `0x18030bb5d`

## string_xrefs

- `0x18030baf2`: `FindMoreAppsLink`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<FindMoreAppsLink,DirectUI::TouchHyperLink,DirectUI::StandardCreator<FindMoreAppsLink>>::Register(
        __int64 a1,
        struct DirectUI::IClassInfo *a2,
        DirectUI::ClassInfoBase *a3)
{
  int v3; // ebx
  void (__fastcall ***ClassInfoPtr)(_QWORD); // rax
  struct _RTL_CRITICAL_SECTION *FactoryLock; // rax
  struct DirectUI::IClassInfo *v6; // rax
  int v7; // edx
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  struct DirectUI::IClassInfo *v11; // rdi
  int v13; // [rsp+20h] [rbp-28h]
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF
  struct DirectUI::IClassInfo *v15; // [rsp+58h] [rbp+10h] BYREF
  DirectUI::ClassInfoBase *v16; // [rsp+60h] [rbp+18h] BYREF

  v16 = a3;
  v15 = a2;
  v14 = a1;
  if ( DirectUI::TouchHyperLink::GetClassInfoPtr() )
  {
    ClassInfoPtr = (void (__fastcall ***)(_QWORD))DirectUI::TouchHyperLink::GetClassInfoPtr();
    (**ClassInfoPtr)(ClassInfoPtr);
  }
  else
  {
    v3 = DirectUI::TouchHyperLink::Register();
    if ( v3 < 0 )
      return (unsigned int)v3;
  }
  FactoryLock = (struct _RTL_CRITICAL_SECTION *)DirectUI::Element::GetFactoryLock();
  DirectUI::CritSecLock::CritSecLock((DirectUI::CritSecLock *)&v14, FactoryLock);
  v15 = 0;
  v6 = (struct DirectUI::IClassInfo *)DirectUI::TouchHyperLink::GetClassInfoPtr();
  if ( DirectUI::ClassInfoBase::ClassExist(&v15, 0, 0, v6, (HINSTANCE)&_ImageBase, L"FindMoreAppsLink", 0) )
  {
    v3 = 0;
    FindMoreAppsLink::s_pClassInfo = v15;
  }
  else
  {
    FindMoreAppsLink::s_pClassInfo = 0;
    v16 = 0;
    v3 = DirectUI::ClassInfo<FindMoreAppsLink,DirectUI::TouchHyperLink,DirectUI::StandardCreator<FindMoreAppsLink>>::Create(
           v8,
           v7,
           v9,
           v10,
           v13,
           (__int64)&v16);
    if ( v3 >= 0 )
    {
      v11 = v16;
      v3 = DirectUI::ClassInfoBase::Register(v16);
      if ( v3 < 0 )
        (*(void (__fastcall **)(struct DirectUI::IClassInfo *))(*(_QWORD *)v11 + 88LL))(v11);
      else
        FindMoreAppsLink::s_pClassInfo = v11;
    }
  }
  DirectUI::CritSecLock::~CritSecLock((DirectUI::CritSecLock *)&v14);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18030ba60  mov     rax, rsp
0x18030ba63  mov     [rax+20h], rbx
0x18030ba67  mov     [rax+18h], r8
0x18030ba6b  mov     [rax+10h], rdx
0x18030ba6f  mov     [rax+8], rcx
0x18030ba73  push    rdi
0x18030ba74  sub     rsp, 40h
0x18030ba78  call    cs:__imp_?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::TouchHyperLink::GetClassInfoPtr(void)
0x18030ba7f  nop     dword ptr [rax+rax+00h]
0x18030ba84  test    rax, rax
0x18030ba87  jnz     short loc_18030BAA0
0x18030ba89  call    cs:__imp_?Register@TouchHyperLink@DirectUI@@SAJXZ; DirectUI::TouchHyperLink::Register(void)
0x18030ba90  nop     dword ptr [rax+rax+00h]
0x18030ba95  mov     ebx, eax
0x18030ba97  test    eax, eax
0x18030ba99  jns     short loc_18030BABD
0x18030ba9b  jmp     loc_18030BBA8
0x18030baa0  call    cs:__imp_?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::TouchHyperLink::GetClassInfoPtr(void)
0x18030baa7  nop     dword ptr [rax+rax+00h]
0x18030baac  mov     rdx, rax
0x18030baaf  mov     rcx, [rax]
0x18030bab2  mov     rax, [rcx]
0x18030bab5  mov     rcx, rdx
0x18030bab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18030babd  call    cs:__imp_?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ; DirectUI::Element::GetFactoryLock(void)
0x18030bac4  nop     dword ptr [rax+rax+00h]
0x18030bac9  mov     rdx, rax
0x18030bacc  lea     rcx, [rsp+48h+arg_0]
0x18030bad1  call    cs:__imp_??0CritSecLock@DirectUI@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; DirectUI::CritSecLock::CritSecLock(_RTL_CRITICAL_SECTION *)
0x18030bad8  nop     dword ptr [rax+rax+00h]
0x18030badd  mov     [rsp+48h+arg_8], 0
0x18030bae6  call    cs:__imp_?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::TouchHyperLink::GetClassInfoPtr(void)
0x18030baed  nop     dword ptr [rax+rax+00h]
0x18030baf2  lea     rcx, aFindmoreappsli; "FindMoreAppsLink"
0x18030baf9  mov     [rsp+48h+var_18], 0
0x18030bafe  mov     [rsp+48h+var_20], rcx
0x18030bb03  mov     r9, rax
0x18030bb06  lea     rcx, __ImageBase
0x18030bb0d  xor     r8d, r8d
0x18030bb10  mov     [rsp+48h+var_28], rcx
0x18030bb15  xor     edx, edx
0x18030bb17  lea     rcx, [rsp+48h+arg_8]
0x18030bb1c  call    cs:__imp_?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z; DirectUI::ClassInfoBase::ClassExist(DirectUI::IClassInfo * *,DirectUI::PropertyInfo const * const *,uint,DirectUI::IClassInfo *,HINSTANCE__ *,ushort const *,bool)
0x18030bb23  nop     dword ptr [rax+rax+00h]
0x18030bb28  test    al, al
0x18030bb2a  jnz     short loc_18030BB89
0x18030bb2c  lea     rax, [rsp+48h+arg_10]
0x18030bb31  mov     cs:?s_pClassInfo@FindMoreAppsLink@@0PEAUIClassInfo@DirectUI@@EA, 0; DirectUI::IClassInfo * FindMoreAppsLink::s_pClassInfo
0x18030bb3c  mov     [rsp+48h+var_20], rax
0x18030bb41  mov     [rsp+48h+arg_10], 0
0x18030bb4a  call    ?Create@?$ClassInfo@VFindMoreAppsLink@@VTouchHyperLink@DirectUI@@V?$StandardCreator@VFindMoreAppsLink@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@IPEAPEAV12@@Z; DirectUI::ClassInfo<FindMoreAppsLink,DirectUI::TouchHyperLink,DirectUI::StandardCreator<FindMoreAppsLink>>::Create(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint,DirectUI::ClassInfo<FindMoreAppsLink,DirectUI::TouchHyperLink,DirectUI::StandardCreator<FindMoreAppsLink>> * *)
0x18030bb4f  mov     ebx, eax
0x18030bb51  test    eax, eax
0x18030bb53  js      short loc_18030BB97
0x18030bb55  mov     rdi, [rsp+48h+arg_10]
0x18030bb5a  mov     rcx, rdi
0x18030bb5d  call    cs:__imp_?Register@ClassInfoBase@DirectUI@@QEAAJXZ; DirectUI::ClassInfoBase::Register(void)
0x18030bb64  nop     dword ptr [rax+rax+00h]
0x18030bb69  mov     ebx, eax
0x18030bb6b  test    eax, eax
0x18030bb6d  js      short loc_18030BB78
0x18030bb6f  mov     cs:?s_pClassInfo@FindMoreAppsLink@@0PEAUIClassInfo@DirectUI@@EA, rdi; DirectUI::IClassInfo * FindMoreAppsLink::s_pClassInfo
0x18030bb76  jmp     short loc_18030BB97
0x18030bb78  mov     rax, [rdi]
0x18030bb7b  mov     rcx, rdi
0x18030bb7e  mov     rax, [rax+58h]
0x18030bb82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18030bb87  jmp     short loc_18030BB97
0x18030bb89  mov     rax, [rsp+48h+arg_8]
0x18030bb8e  xor     ebx, ebx
0x18030bb90  mov     cs:?s_pClassInfo@FindMoreAppsLink@@0PEAUIClassInfo@DirectUI@@EA, rax; DirectUI::IClassInfo * FindMoreAppsLink::s_pClassInfo
0x18030bb97  lea     rcx, [rsp+48h+arg_0]
0x18030bb9c  call    cs:__imp_??1CritSecLock@DirectUI@@QEAA@XZ; DirectUI::CritSecLock::~CritSecLock(void)
0x18030bba3  nop     dword ptr [rax+rax+00h]
0x18030bba8  mov     eax, ebx
0x18030bbaa  mov     rbx, [rsp+48h+arg_18]
0x18030bbaf  add     rsp, 40h
0x18030bbb3  pop     rdi
0x18030bbb4  retn
```
