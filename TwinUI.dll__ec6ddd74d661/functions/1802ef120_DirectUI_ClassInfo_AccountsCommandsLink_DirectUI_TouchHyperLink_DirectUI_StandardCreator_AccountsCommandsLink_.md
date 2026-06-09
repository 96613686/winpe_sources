# DirectUI::ClassInfo<AccountsCommandsLink,DirectUI::TouchHyperLink,DirectUI::StandardCreator<AccountsCommandsLink>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)

- ea: `0x1802ef120`
- end: `0x1802ef276`
- name: `?Register@?$ClassInfo@VAccountsCommandsLink@@VTouchHyperLink@DirectUI@@V?$StandardCreator@VAccountsCommandsLink@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z`
- size: `342`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1802ef280`

## callees

- `0x1802eee9c`
- `0x1802ef120`
- `0x1803bb010`

## import_xrefs

- `DUI70!?Register@TouchHyperLink@DirectUI@@SAJXZ` at `0x1802ef149`
- `DUI70!?Register@TouchHyperLink@DirectUI@@SAJXZ` at `0x1802ef149`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x1802ef138`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x1802ef160`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x1802ef1a6`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x1802ef138`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x1802ef160`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x1802ef1a6`
- `DUI70!??0CritSecLock@DirectUI@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x1802ef191`
- `DUI70!??0CritSecLock@DirectUI@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x1802ef191`
- `DUI70!?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ` at `0x1802ef17d`
- `DUI70!?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ` at `0x1802ef17d`
- `DUI70!??1CritSecLock@DirectUI@@QEAA@XZ` at `0x1802ef25c`
- `DUI70!??1CritSecLock@DirectUI@@QEAA@XZ` at `0x1802ef25c`
- `DUI70!?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z` at `0x1802ef1dc`
- `DUI70!?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z` at `0x1802ef1dc`
- `DUI70!?Register@ClassInfoBase@DirectUI@@QEAAJXZ` at `0x1802ef21d`
- `DUI70!?Register@ClassInfoBase@DirectUI@@QEAAJXZ` at `0x1802ef21d`

## string_xrefs

- `0x1802ef1b2`: `AccountsCommandsLink`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<AccountsCommandsLink,DirectUI::TouchHyperLink,DirectUI::StandardCreator<AccountsCommandsLink>>::Register(
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
  if ( DirectUI::ClassInfoBase::ClassExist(&v15, 0, 0, v6, (HINSTANCE)&_ImageBase, L"AccountsCommandsLink", 0) )
  {
    v3 = 0;
    AccountsCommandsLink::Class = v15;
  }
  else
  {
    AccountsCommandsLink::Class = 0;
    v16 = 0;
    v3 = DirectUI::ClassInfo<AccountsCommandsLink,DirectUI::TouchHyperLink,DirectUI::StandardCreator<AccountsCommandsLink>>::Create(
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
        AccountsCommandsLink::Class = v11;
    }
  }
  DirectUI::CritSecLock::~CritSecLock((DirectUI::CritSecLock *)&v14);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1802ef120  mov     rax, rsp
0x1802ef123  mov     [rax+20h], rbx
0x1802ef127  mov     [rax+18h], r8
0x1802ef12b  mov     [rax+10h], rdx
0x1802ef12f  mov     [rax+8], rcx
0x1802ef133  push    rdi
0x1802ef134  sub     rsp, 40h
0x1802ef138  call    cs:__imp_?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::TouchHyperLink::GetClassInfoPtr(void)
0x1802ef13f  nop     dword ptr [rax+rax+00h]
0x1802ef144  test    rax, rax
0x1802ef147  jnz     short loc_1802EF160
0x1802ef149  call    cs:__imp_?Register@TouchHyperLink@DirectUI@@SAJXZ; DirectUI::TouchHyperLink::Register(void)
0x1802ef150  nop     dword ptr [rax+rax+00h]
0x1802ef155  mov     ebx, eax
0x1802ef157  test    eax, eax
0x1802ef159  jns     short loc_1802EF17D
0x1802ef15b  jmp     loc_1802EF268
0x1802ef160  call    cs:__imp_?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::TouchHyperLink::GetClassInfoPtr(void)
0x1802ef167  nop     dword ptr [rax+rax+00h]
0x1802ef16c  mov     rdx, rax
0x1802ef16f  mov     rcx, [rax]
0x1802ef172  mov     rax, [rcx]
0x1802ef175  mov     rcx, rdx
0x1802ef178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802ef17d  call    cs:__imp_?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ; DirectUI::Element::GetFactoryLock(void)
0x1802ef184  nop     dword ptr [rax+rax+00h]
0x1802ef189  mov     rdx, rax
0x1802ef18c  lea     rcx, [rsp+48h+arg_0]
0x1802ef191  call    cs:__imp_??0CritSecLock@DirectUI@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; DirectUI::CritSecLock::CritSecLock(_RTL_CRITICAL_SECTION *)
0x1802ef198  nop     dword ptr [rax+rax+00h]
0x1802ef19d  mov     [rsp+48h+arg_8], 0
0x1802ef1a6  call    cs:__imp_?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::TouchHyperLink::GetClassInfoPtr(void)
0x1802ef1ad  nop     dword ptr [rax+rax+00h]
0x1802ef1b2  lea     rcx, aAccountscomman_0; "AccountsCommandsLink"
0x1802ef1b9  mov     [rsp+48h+var_18], 0
0x1802ef1be  mov     [rsp+48h+var_20], rcx
0x1802ef1c3  mov     r9, rax
0x1802ef1c6  lea     rcx, __ImageBase
0x1802ef1cd  xor     r8d, r8d
0x1802ef1d0  mov     [rsp+48h+var_28], rcx
0x1802ef1d5  xor     edx, edx
0x1802ef1d7  lea     rcx, [rsp+48h+arg_8]
0x1802ef1dc  call    cs:__imp_?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z; DirectUI::ClassInfoBase::ClassExist(DirectUI::IClassInfo * *,DirectUI::PropertyInfo const * const *,uint,DirectUI::IClassInfo *,HINSTANCE__ *,ushort const *,bool)
0x1802ef1e3  nop     dword ptr [rax+rax+00h]
0x1802ef1e8  test    al, al
0x1802ef1ea  jnz     short loc_1802EF249
0x1802ef1ec  lea     rax, [rsp+48h+arg_10]
0x1802ef1f1  mov     cs:?Class@AccountsCommandsLink@@2PEAUIClassInfo@DirectUI@@EA, 0; DirectUI::IClassInfo * AccountsCommandsLink::Class
0x1802ef1fc  mov     [rsp+48h+var_20], rax
0x1802ef201  mov     [rsp+48h+arg_10], 0
0x1802ef20a  call    ?Create@?$ClassInfo@VAccountsCommandsLink@@VTouchHyperLink@DirectUI@@V?$StandardCreator@VAccountsCommandsLink@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@IPEAPEAV12@@Z; DirectUI::ClassInfo<AccountsCommandsLink,DirectUI::TouchHyperLink,DirectUI::StandardCreator<AccountsCommandsLink>>::Create(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint,DirectUI::ClassInfo<AccountsCommandsLink,DirectUI::TouchHyperLink,DirectUI::StandardCreator<AccountsCommandsLink>> * *)
0x1802ef20f  mov     ebx, eax
0x1802ef211  test    eax, eax
0x1802ef213  js      short loc_1802EF257
0x1802ef215  mov     rdi, [rsp+48h+arg_10]
0x1802ef21a  mov     rcx, rdi
0x1802ef21d  call    cs:__imp_?Register@ClassInfoBase@DirectUI@@QEAAJXZ; DirectUI::ClassInfoBase::Register(void)
0x1802ef224  nop     dword ptr [rax+rax+00h]
0x1802ef229  mov     ebx, eax
0x1802ef22b  test    eax, eax
0x1802ef22d  js      short loc_1802EF238
0x1802ef22f  mov     cs:?Class@AccountsCommandsLink@@2PEAUIClassInfo@DirectUI@@EA, rdi; DirectUI::IClassInfo * AccountsCommandsLink::Class
0x1802ef236  jmp     short loc_1802EF257
0x1802ef238  mov     rax, [rdi]
0x1802ef23b  mov     rcx, rdi
0x1802ef23e  mov     rax, [rax+58h]
0x1802ef242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802ef247  jmp     short loc_1802EF257
0x1802ef249  mov     rax, [rsp+48h+arg_8]
0x1802ef24e  xor     ebx, ebx
0x1802ef250  mov     cs:?Class@AccountsCommandsLink@@2PEAUIClassInfo@DirectUI@@EA, rax; DirectUI::IClassInfo * AccountsCommandsLink::Class
0x1802ef257  lea     rcx, [rsp+48h+arg_0]
0x1802ef25c  call    cs:__imp_??1CritSecLock@DirectUI@@QEAA@XZ; DirectUI::CritSecLock::~CritSecLock(void)
0x1802ef263  nop     dword ptr [rax+rax+00h]
0x1802ef268  mov     eax, ebx
0x1802ef26a  mov     rbx, [rsp+48h+arg_18]
0x1802ef26f  add     rsp, 40h
0x1802ef273  pop     rdi
0x1802ef274  retn
```
