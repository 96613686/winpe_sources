# DirectUI::ClassInfo<AccessibilityCplPage,CElementWithSite,DirectUI::StandardCreator<AccessibilityCplPage>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)

- ea: `0x18001c914`
- end: `0x18001ca25`
- name: `?Register@?$ClassInfo@VAccessibilityCplPage@@VCElementWithSite@@V?$StandardCreator@VAccessibilityCplPage@@@DirectUI@@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001ea10`

## callees

- `0x18001c4a0`
- `0x18001c914`
- `0x18002c5fc`
- `0x18002e010`

## import_xrefs

- `DUI70!??0CritSecLock@DirectUI@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18001c961`
- `DUI70!??0CritSecLock@DirectUI@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18001c961`
- `DUI70!??1CritSecLock@DirectUI@@QEAA@XZ` at `0x18001ca12`
- `DUI70!??1CritSecLock@DirectUI@@QEAA@XZ` at `0x18001ca12`
- `DUI70!?Register@ClassInfoBase@DirectUI@@QEAAJXZ` at `0x18001c9d9`
- `DUI70!?Register@ClassInfoBase@DirectUI@@QEAAJXZ` at `0x18001c9d9`
- `DUI70!?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z` at `0x18001c99e`
- `DUI70!?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z` at `0x18001c99e`
- `DUI70!?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ` at `0x18001c953`
- `DUI70!?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ` at `0x18001c953`

## string_xrefs

- `0x18001c96e`: `AccessibilityCplPage`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<AccessibilityCplPage,CElementWithSite,DirectUI::StandardCreator<AccessibilityCplPage>>::Register(
        __int64 a1,
        struct DirectUI::IClassInfo *a2,
        DirectUI::ClassInfoBase *a3)
{
  int v3; // ebx
  struct _RTL_CRITICAL_SECTION *FactoryLock; // rax
  int v5; // edx
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  struct DirectUI::IClassInfo *v9; // rdi
  int v11; // [rsp+20h] [rbp-28h]
  __int64 v12; // [rsp+50h] [rbp+8h] BYREF
  struct DirectUI::IClassInfo *v13; // [rsp+58h] [rbp+10h] BYREF
  DirectUI::ClassInfoBase *v14; // [rsp+60h] [rbp+18h] BYREF

  v14 = a3;
  v13 = a2;
  v12 = a1;
  if ( CElementWithSite::Class )
  {
    (**(void (__fastcall ***)(struct DirectUI::IClassInfo *))CElementWithSite::Class)(CElementWithSite::Class);
  }
  else
  {
    v3 = CElementWithSite::Register();
    if ( v3 < 0 )
      return (unsigned int)v3;
  }
  FactoryLock = (struct _RTL_CRITICAL_SECTION *)DirectUI::Element::GetFactoryLock();
  DirectUI::CritSecLock::CritSecLock((DirectUI::CritSecLock *)&v12, FactoryLock);
  v13 = 0;
  if ( DirectUI::ClassInfoBase::ClassExist(&v13, 0, 0, CElementWithSite::Class, &_ImageBase, L"AccessibilityCplPage", 0) )
  {
    v3 = 0;
    AccessibilityCplPage::Class = v13;
  }
  else
  {
    AccessibilityCplPage::Class = 0;
    v14 = 0;
    v3 = DirectUI::ClassInfo<AccessibilityCplPage,CElementWithSite,DirectUI::StandardCreator<AccessibilityCplPage>>::Create(
           v6,
           v5,
           v7,
           v8,
           v11,
           (__int64)&v14);
    if ( v3 >= 0 )
    {
      v9 = v14;
      v3 = DirectUI::ClassInfoBase::Register(v14);
      if ( v3 < 0 )
        (*(void (__fastcall **)(struct DirectUI::IClassInfo *))(*(_QWORD *)v9 + 88LL))(v9);
      else
        AccessibilityCplPage::Class = v9;
    }
  }
  DirectUI::CritSecLock::~CritSecLock((DirectUI::CritSecLock *)&v12);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001c914  mov     rax, rsp
0x18001c917  mov     [rax+20h], rbx
0x18001c91b  mov     [rax+18h], r8
0x18001c91f  mov     [rax+10h], rdx
0x18001c923  mov     [rax+8], rcx
0x18001c927  push    rdi
0x18001c928  sub     rsp, 40h
0x18001c92c  mov     rcx, cs:?Class@CElementWithSite@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * CElementWithSite::Class
0x18001c933  test    rcx, rcx
0x18001c936  jnz     short loc_18001C948
0x18001c938  call    ?Register@CElementWithSite@@SAJXZ; CElementWithSite::Register(void)
0x18001c93d  mov     ebx, eax
0x18001c93f  test    eax, eax
0x18001c941  jns     short loc_18001C953
0x18001c943  jmp     loc_18001CA18
0x18001c948  mov     rax, [rcx]
0x18001c94b  mov     rax, [rax]
0x18001c94e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c953  call    cs:__imp_?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ; DirectUI::Element::GetFactoryLock(void)
0x18001c959  mov     rdx, rax
0x18001c95c  lea     rcx, [rsp+48h+arg_0]
0x18001c961  call    cs:__imp_??0CritSecLock@DirectUI@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; DirectUI::CritSecLock::CritSecLock(_RTL_CRITICAL_SECTION *)
0x18001c967  mov     r9, cs:?Class@CElementWithSite@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * CElementWithSite::Class
0x18001c96e  lea     rax, aAccessibilityc_1; "AccessibilityCplPage"
0x18001c975  mov     [rsp+48h+var_18], 0
0x18001c97a  lea     rcx, [rsp+48h+arg_8]
0x18001c97f  mov     [rsp+48h+var_20], rax
0x18001c984  xor     r8d, r8d
0x18001c987  lea     rax, __ImageBase
0x18001c98e  mov     [rsp+48h+arg_8], 0
0x18001c997  xor     edx, edx
0x18001c999  mov     [rsp+48h+var_28], rax
0x18001c99e  call    cs:__imp_?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z; DirectUI::ClassInfoBase::ClassExist(DirectUI::IClassInfo * *,DirectUI::PropertyInfo const * const *,uint,DirectUI::IClassInfo *,HINSTANCE__ *,ushort const *,bool)
0x18001c9a4  test    al, al
0x18001c9a6  jnz     short loc_18001C9FF
0x18001c9a8  lea     rax, [rsp+48h+arg_10]
0x18001c9ad  mov     cs:?Class@AccessibilityCplPage@@2PEAUIClassInfo@DirectUI@@EA, 0; DirectUI::IClassInfo * AccessibilityCplPage::Class
0x18001c9b8  mov     [rsp+48h+var_20], rax
0x18001c9bd  mov     [rsp+48h+arg_10], 0
0x18001c9c6  call    ?Create@?$ClassInfo@VAccessibilityCplPage@@VCElementWithSite@@V?$StandardCreator@VAccessibilityCplPage@@@DirectUI@@@DirectUI@@CAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@IPEAPEAV12@@Z; DirectUI::ClassInfo<AccessibilityCplPage,CElementWithSite,DirectUI::StandardCreator<AccessibilityCplPage>>::Create(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint,DirectUI::ClassInfo<AccessibilityCplPage,CElementWithSite,DirectUI::StandardCreator<AccessibilityCplPage>> * *)
0x18001c9cb  mov     ebx, eax
0x18001c9cd  test    eax, eax
0x18001c9cf  js      short loc_18001CA0D
0x18001c9d1  mov     rdi, [rsp+48h+arg_10]
0x18001c9d6  mov     rcx, rdi
0x18001c9d9  call    cs:__imp_?Register@ClassInfoBase@DirectUI@@QEAAJXZ; DirectUI::ClassInfoBase::Register(void)
0x18001c9df  mov     ebx, eax
0x18001c9e1  test    eax, eax
0x18001c9e3  js      short loc_18001C9EE
0x18001c9e5  mov     cs:?Class@AccessibilityCplPage@@2PEAUIClassInfo@DirectUI@@EA, rdi; DirectUI::IClassInfo * AccessibilityCplPage::Class
0x18001c9ec  jmp     short loc_18001CA0D
0x18001c9ee  mov     rax, [rdi]
0x18001c9f1  mov     rcx, rdi
0x18001c9f4  mov     rax, [rax+58h]
0x18001c9f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9fd  jmp     short loc_18001CA0D
0x18001c9ff  mov     rax, [rsp+48h+arg_8]
0x18001ca04  xor     ebx, ebx
0x18001ca06  mov     cs:?Class@AccessibilityCplPage@@2PEAUIClassInfo@DirectUI@@EA, rax; DirectUI::IClassInfo * AccessibilityCplPage::Class
0x18001ca0d  lea     rcx, [rsp+48h+arg_0]
0x18001ca12  call    cs:__imp_??1CritSecLock@DirectUI@@QEAA@XZ; DirectUI::CritSecLock::~CritSecLock(void)
0x18001ca18  mov     eax, ebx
0x18001ca1a  mov     rbx, [rsp+48h+arg_18]
0x18001ca1f  add     rsp, 40h
0x18001ca23  pop     rdi
0x18001ca24  retn
```
