# DirectUI::ClassInfo<PreviousShareLink,DirectUI::TouchHyperLink,DirectUI::StandardCreator<PreviousShareLink>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)

- ea: `0x18030bbbc`
- end: `0x18030bd12`
- name: `?Register@?$ClassInfo@VPreviousShareLink@@VTouchHyperLink@DirectUI@@V?$StandardCreator@VPreviousShareLink@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z`
- size: `342`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18030c420`

## callees

- `0x180309d84`
- `0x18030bbbc`
- `0x1803bb010`

## import_xrefs

- `DUI70!?Register@TouchHyperLink@DirectUI@@SAJXZ` at `0x18030bbe5`
- `DUI70!?Register@TouchHyperLink@DirectUI@@SAJXZ` at `0x18030bbe5`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x18030bbd4`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x18030bbfc`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x18030bc42`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x18030bbd4`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x18030bbfc`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x18030bc42`
- `DUI70!??0CritSecLock@DirectUI@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18030bc2d`
- `DUI70!??0CritSecLock@DirectUI@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18030bc2d`
- `DUI70!?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ` at `0x18030bc19`
- `DUI70!?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ` at `0x18030bc19`
- `DUI70!??1CritSecLock@DirectUI@@QEAA@XZ` at `0x18030bcf8`
- `DUI70!??1CritSecLock@DirectUI@@QEAA@XZ` at `0x18030bcf8`
- `DUI70!?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z` at `0x18030bc78`
- `DUI70!?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z` at `0x18030bc78`
- `DUI70!?Register@ClassInfoBase@DirectUI@@QEAAJXZ` at `0x18030bcb9`
- `DUI70!?Register@ClassInfoBase@DirectUI@@QEAAJXZ` at `0x18030bcb9`

## string_xrefs

- `0x18030bc4e`: `PreviousShareLink`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<PreviousShareLink,DirectUI::TouchHyperLink,DirectUI::StandardCreator<PreviousShareLink>>::Register(
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
  if ( DirectUI::ClassInfoBase::ClassExist(&v15, 0, 0, v6, (HINSTANCE)&_ImageBase, L"PreviousShareLink", 0) )
  {
    v3 = 0;
    PreviousShareLink::s_pClassInfo = v15;
  }
  else
  {
    PreviousShareLink::s_pClassInfo = 0;
    v16 = 0;
    v3 = DirectUI::ClassInfo<PreviousShareLink,DirectUI::TouchHyperLink,DirectUI::StandardCreator<PreviousShareLink>>::Create(
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
        PreviousShareLink::s_pClassInfo = v11;
    }
  }
  DirectUI::CritSecLock::~CritSecLock((DirectUI::CritSecLock *)&v14);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18030bbbc  mov     rax, rsp
0x18030bbbf  mov     [rax+20h], rbx
0x18030bbc3  mov     [rax+18h], r8
0x18030bbc7  mov     [rax+10h], rdx
0x18030bbcb  mov     [rax+8], rcx
0x18030bbcf  push    rdi
0x18030bbd0  sub     rsp, 40h
0x18030bbd4  call    cs:__imp_?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::TouchHyperLink::GetClassInfoPtr(void)
0x18030bbdb  nop     dword ptr [rax+rax+00h]
0x18030bbe0  test    rax, rax
0x18030bbe3  jnz     short loc_18030BBFC
0x18030bbe5  call    cs:__imp_?Register@TouchHyperLink@DirectUI@@SAJXZ; DirectUI::TouchHyperLink::Register(void)
0x18030bbec  nop     dword ptr [rax+rax+00h]
0x18030bbf1  mov     ebx, eax
0x18030bbf3  test    eax, eax
0x18030bbf5  jns     short loc_18030BC19
0x18030bbf7  jmp     loc_18030BD04
0x18030bbfc  call    cs:__imp_?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::TouchHyperLink::GetClassInfoPtr(void)
0x18030bc03  nop     dword ptr [rax+rax+00h]
0x18030bc08  mov     rdx, rax
0x18030bc0b  mov     rcx, [rax]
0x18030bc0e  mov     rax, [rcx]
0x18030bc11  mov     rcx, rdx
0x18030bc14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18030bc19  call    cs:__imp_?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ; DirectUI::Element::GetFactoryLock(void)
0x18030bc20  nop     dword ptr [rax+rax+00h]
0x18030bc25  mov     rdx, rax
0x18030bc28  lea     rcx, [rsp+48h+arg_0]
0x18030bc2d  call    cs:__imp_??0CritSecLock@DirectUI@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; DirectUI::CritSecLock::CritSecLock(_RTL_CRITICAL_SECTION *)
0x18030bc34  nop     dword ptr [rax+rax+00h]
0x18030bc39  mov     [rsp+48h+arg_8], 0
0x18030bc42  call    cs:__imp_?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::TouchHyperLink::GetClassInfoPtr(void)
0x18030bc49  nop     dword ptr [rax+rax+00h]
0x18030bc4e  lea     rcx, aPrevioussharel; "PreviousShareLink"
0x18030bc55  mov     [rsp+48h+var_18], 0
0x18030bc5a  mov     [rsp+48h+var_20], rcx
0x18030bc5f  mov     r9, rax
0x18030bc62  lea     rcx, __ImageBase
0x18030bc69  xor     r8d, r8d
0x18030bc6c  mov     [rsp+48h+var_28], rcx
0x18030bc71  xor     edx, edx
0x18030bc73  lea     rcx, [rsp+48h+arg_8]
0x18030bc78  call    cs:__imp_?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z; DirectUI::ClassInfoBase::ClassExist(DirectUI::IClassInfo * *,DirectUI::PropertyInfo const * const *,uint,DirectUI::IClassInfo *,HINSTANCE__ *,ushort const *,bool)
0x18030bc7f  nop     dword ptr [rax+rax+00h]
0x18030bc84  test    al, al
0x18030bc86  jnz     short loc_18030BCE5
0x18030bc88  lea     rax, [rsp+48h+arg_10]
0x18030bc8d  mov     cs:?s_pClassInfo@PreviousShareLink@@0PEAUIClassInfo@DirectUI@@EA, 0; DirectUI::IClassInfo * PreviousShareLink::s_pClassInfo
0x18030bc98  mov     [rsp+48h+var_20], rax
0x18030bc9d  mov     [rsp+48h+arg_10], 0
0x18030bca6  call    ?Create@?$ClassInfo@VPreviousShareLink@@VTouchHyperLink@DirectUI@@V?$StandardCreator@VPreviousShareLink@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@IPEAPEAV12@@Z; DirectUI::ClassInfo<PreviousShareLink,DirectUI::TouchHyperLink,DirectUI::StandardCreator<PreviousShareLink>>::Create(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint,DirectUI::ClassInfo<PreviousShareLink,DirectUI::TouchHyperLink,DirectUI::StandardCreator<PreviousShareLink>> * *)
0x18030bcab  mov     ebx, eax
0x18030bcad  test    eax, eax
0x18030bcaf  js      short loc_18030BCF3
0x18030bcb1  mov     rdi, [rsp+48h+arg_10]
0x18030bcb6  mov     rcx, rdi
0x18030bcb9  call    cs:__imp_?Register@ClassInfoBase@DirectUI@@QEAAJXZ; DirectUI::ClassInfoBase::Register(void)
0x18030bcc0  nop     dword ptr [rax+rax+00h]
0x18030bcc5  mov     ebx, eax
0x18030bcc7  test    eax, eax
0x18030bcc9  js      short loc_18030BCD4
0x18030bccb  mov     cs:?s_pClassInfo@PreviousShareLink@@0PEAUIClassInfo@DirectUI@@EA, rdi; DirectUI::IClassInfo * PreviousShareLink::s_pClassInfo
0x18030bcd2  jmp     short loc_18030BCF3
0x18030bcd4  mov     rax, [rdi]
0x18030bcd7  mov     rcx, rdi
0x18030bcda  mov     rax, [rax+58h]
0x18030bcde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18030bce3  jmp     short loc_18030BCF3
0x18030bce5  mov     rax, [rsp+48h+arg_8]
0x18030bcea  xor     ebx, ebx
0x18030bcec  mov     cs:?s_pClassInfo@PreviousShareLink@@0PEAUIClassInfo@DirectUI@@EA, rax; DirectUI::IClassInfo * PreviousShareLink::s_pClassInfo
0x18030bcf3  lea     rcx, [rsp+48h+arg_0]
0x18030bcf8  call    cs:__imp_??1CritSecLock@DirectUI@@QEAA@XZ; DirectUI::CritSecLock::~CritSecLock(void)
0x18030bcff  nop     dword ptr [rax+rax+00h]
0x18030bd04  mov     eax, ebx
0x18030bd06  mov     rbx, [rsp+48h+arg_18]
0x18030bd0b  add     rsp, 40h
0x18030bd0f  pop     rdi
0x18030bd10  retn
```
