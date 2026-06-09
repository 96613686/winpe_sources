# DirectUI::ClassInfo<CElementWithIUnknown,DirectUI::Element,DirectUI::StandardCreator<CElementWithIUnknown>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)

- ea: `0x18000add0`
- end: `0x18000aeef`
- name: `?Register@?$ClassInfo@VCElementWithIUnknown@@VElement@DirectUI@@V?$StandardCreator@VCElementWithIUnknown@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z`
- size: `287`
- prototype: `__int64 __fastcall(__int64, struct DirectUI::IClassInfo *, DirectUI::ClassInfoBase *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000aef8`
- `0x18000b010`

## callees

- `0x18000ac30`
- `0x18000add0`
- `0x18000c010`

## import_xrefs

- `DUI70!?GetClassInfoPtr@Element@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x18000ade8`
- `DUI70!?GetClassInfoPtr@Element@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x18000ae04`
- `DUI70!?GetClassInfoPtr@Element@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x18000ae38`
- `DUI70!?GetClassInfoPtr@Element@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x18000ade8`
- `DUI70!?GetClassInfoPtr@Element@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x18000ae04`
- `DUI70!?GetClassInfoPtr@Element@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x18000ae38`
- `DUI70!?Register@Element@DirectUI@@SAJXZ` at `0x18000adf3`
- `DUI70!?Register@Element@DirectUI@@SAJXZ` at `0x18000adf3`
- `DUI70!??0CritSecLock@DirectUI@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18000ae29`
- `DUI70!??0CritSecLock@DirectUI@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18000ae29`
- `DUI70!?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ` at `0x18000ae1b`
- `DUI70!?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ` at `0x18000ae1b`
- `DUI70!??1CritSecLock@DirectUI@@QEAA@XZ` at `0x18000aedc`
- `DUI70!??1CritSecLock@DirectUI@@QEAA@XZ` at `0x18000aedc`
- `DUI70!?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z` at `0x18000ae68`
- `DUI70!?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z` at `0x18000ae68`
- `DUI70!?Register@ClassInfoBase@DirectUI@@QEAAJXZ` at `0x18000aea3`
- `DUI70!?Register@ClassInfoBase@DirectUI@@QEAAJXZ` at `0x18000aea3`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<CElementWithIUnknown,DirectUI::Element,DirectUI::StandardCreator<CElementWithIUnknown>>::Register(
        __int64 a1,
        struct DirectUI::IClassInfo *a2,
        DirectUI::ClassInfoBase *a3)
{
  int v3; // ebx
  void (__fastcall ***ClassInfoPtr)(_QWORD); // rax
  struct _RTL_CRITICAL_SECTION *FactoryLock; // rax
  struct DirectUI::IClassInfo *v6; // rax
  unsigned __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  struct DirectUI::IClassInfo *v11; // rdi
  int v13; // [rsp+20h] [rbp-28h]
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF
  struct DirectUI::IClassInfo *v15; // [rsp+58h] [rbp+10h] BYREF
  DirectUI::ClassInfoBase *v16; // [rsp+60h] [rbp+18h] BYREF

  v16 = a3;
  v15 = a2;
  v14 = a1;
  if ( DirectUI::Element::GetClassInfoPtr() )
  {
    ClassInfoPtr = (void (__fastcall ***)(_QWORD))DirectUI::Element::GetClassInfoPtr();
    (**ClassInfoPtr)(ClassInfoPtr);
  }
  else
  {
    v3 = DirectUI::Element::Register();
    if ( v3 < 0 )
      return (unsigned int)v3;
  }
  FactoryLock = (struct _RTL_CRITICAL_SECTION *)DirectUI::Element::GetFactoryLock();
  DirectUI::CritSecLock::CritSecLock((DirectUI::CritSecLock *)&v14, FactoryLock);
  v15 = 0;
  v6 = (struct DirectUI::IClassInfo *)DirectUI::Element::GetClassInfoPtr();
  if ( DirectUI::ClassInfoBase::ClassExist(&v15, 0, 0, v6, (HINSTANCE)&_ImageBase, L"CElementWithIUnknown", 0) )
  {
    v3 = 0;
    CElementWithIUnknown::Class = v15;
  }
  else
  {
    CElementWithIUnknown::Class = 0;
    v16 = 0;
    v3 = DirectUI::ClassInfo<CElementWithIUnknown,DirectUI::Element,DirectUI::StandardCreator<CElementWithIUnknown>>::Create(
           v8,
           v7,
           v9,
           v10,
           v13,
           &v16);
    if ( v3 >= 0 )
    {
      v11 = v16;
      v3 = DirectUI::ClassInfoBase::Register(v16);
      if ( v3 < 0 )
        (*(void (__fastcall **)(struct DirectUI::IClassInfo *))(*(_QWORD *)v11 + 88LL))(v11);
      else
        CElementWithIUnknown::Class = v11;
    }
  }
  DirectUI::CritSecLock::~CritSecLock((DirectUI::CritSecLock *)&v14);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000add0  mov     rax, rsp
0x18000add3  mov     [rax+20h], rbx
0x18000add7  mov     [rax+18h], r8
0x18000addb  mov     [rax+10h], rdx
0x18000addf  mov     [rax+8], rcx
0x18000ade3  push    rdi
0x18000ade4  sub     rsp, 40h
0x18000ade8  call    cs:__imp_?GetClassInfoPtr@Element@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::Element::GetClassInfoPtr(void)
0x18000adee  test    rax, rax
0x18000adf1  jnz     short loc_18000AE04
0x18000adf3  call    cs:__imp_?Register@Element@DirectUI@@SAJXZ; DirectUI::Element::Register(void)
0x18000adf9  mov     ebx, eax
0x18000adfb  test    eax, eax
0x18000adfd  jns     short loc_18000AE1B
0x18000adff  jmp     loc_18000AEE2
0x18000ae04  call    cs:__imp_?GetClassInfoPtr@Element@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::Element::GetClassInfoPtr(void)
0x18000ae0a  mov     rdx, rax
0x18000ae0d  mov     rcx, [rax]
0x18000ae10  mov     rax, [rcx]
0x18000ae13  mov     rcx, rdx
0x18000ae16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae1b  call    cs:__imp_?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ; DirectUI::Element::GetFactoryLock(void)
0x18000ae21  mov     rdx, rax
0x18000ae24  lea     rcx, [rsp+48h+arg_0]
0x18000ae29  call    cs:__imp_??0CritSecLock@DirectUI@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; DirectUI::CritSecLock::CritSecLock(_RTL_CRITICAL_SECTION *)
0x18000ae2f  mov     [rsp+48h+arg_8], 0
0x18000ae38  call    cs:__imp_?GetClassInfoPtr@Element@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::Element::GetClassInfoPtr(void)
0x18000ae3e  lea     rcx, aCelementwithiu; "CElementWithIUnknown"
0x18000ae45  mov     [rsp+48h+var_18], 0
0x18000ae4a  mov     [rsp+48h+var_20], rcx
0x18000ae4f  mov     r9, rax
0x18000ae52  lea     rcx, __ImageBase
0x18000ae59  xor     r8d, r8d
0x18000ae5c  mov     [rsp+48h+var_28], rcx
0x18000ae61  xor     edx, edx
0x18000ae63  lea     rcx, [rsp+48h+arg_8]
0x18000ae68  call    cs:__imp_?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z; DirectUI::ClassInfoBase::ClassExist(DirectUI::IClassInfo * *,DirectUI::PropertyInfo const * const *,uint,DirectUI::IClassInfo *,HINSTANCE__ *,ushort const *,bool)
0x18000ae6e  test    al, al
0x18000ae70  jnz     short loc_18000AEC9
0x18000ae72  lea     rax, [rsp+48h+arg_10]
0x18000ae77  mov     cs:?Class@CElementWithIUnknown@@2PEAUIClassInfo@DirectUI@@EA, 0; DirectUI::IClassInfo * CElementWithIUnknown::Class
0x18000ae82  mov     [rsp+48h+var_20], rax
0x18000ae87  mov     [rsp+48h+arg_10], 0
0x18000ae90  call    ?Create@?$ClassInfo@VCElementWithIUnknown@@VElement@DirectUI@@V?$StandardCreator@VCElementWithIUnknown@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@IPEAPEAV12@@Z; DirectUI::ClassInfo<CElementWithIUnknown,DirectUI::Element,DirectUI::StandardCreator<CElementWithIUnknown>>::Create(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint,DirectUI::ClassInfo<CElementWithIUnknown,DirectUI::Element,DirectUI::StandardCreator<CElementWithIUnknown>> * *)
0x18000ae95  mov     ebx, eax
0x18000ae97  test    eax, eax
0x18000ae99  js      short loc_18000AED7
0x18000ae9b  mov     rdi, [rsp+48h+arg_10]
0x18000aea0  mov     rcx, rdi
0x18000aea3  call    cs:__imp_?Register@ClassInfoBase@DirectUI@@QEAAJXZ; DirectUI::ClassInfoBase::Register(void)
0x18000aea9  mov     ebx, eax
0x18000aeab  test    eax, eax
0x18000aead  js      short loc_18000AEB8
0x18000aeaf  mov     cs:?Class@CElementWithIUnknown@@2PEAUIClassInfo@DirectUI@@EA, rdi; DirectUI::IClassInfo * CElementWithIUnknown::Class
0x18000aeb6  jmp     short loc_18000AED7
0x18000aeb8  mov     rax, [rdi]
0x18000aebb  mov     rcx, rdi
0x18000aebe  mov     rax, [rax+58h]
0x18000aec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aec7  jmp     short loc_18000AED7
0x18000aec9  mov     rax, [rsp+48h+arg_8]
0x18000aece  xor     ebx, ebx
0x18000aed0  mov     cs:?Class@CElementWithIUnknown@@2PEAUIClassInfo@DirectUI@@EA, rax; DirectUI::IClassInfo * CElementWithIUnknown::Class
0x18000aed7  lea     rcx, [rsp+48h+arg_0]
0x18000aedc  call    cs:__imp_??1CritSecLock@DirectUI@@QEAA@XZ; DirectUI::CritSecLock::~CritSecLock(void)
0x18000aee2  mov     eax, ebx
0x18000aee4  mov     rbx, [rsp+48h+arg_18]
0x18000aee9  add     rsp, 40h
0x18000aeed  pop     rdi
0x18000aeee  retn
```
