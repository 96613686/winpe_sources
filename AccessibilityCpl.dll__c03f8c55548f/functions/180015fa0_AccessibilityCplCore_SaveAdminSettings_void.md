# AccessibilityCplCore::SaveAdminSettings(void)

- ea: `0x180015fa0`
- end: `0x18001604e`
- name: `?SaveAdminSettings@AccessibilityCplCore@@AEAAJXZ`
- size: `174`
- prototype: `__int64 __fastcall(AccessibilityCplCore *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800134a0`

## callees

- `0x1800043d4`
- `0x18000466c`
- `0x1800068f8`
- `0x180015780`
- `0x180015fa0`
- `0x1800218bc`
- `0x18002e010`

## import_xrefs

- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180016007`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180016007`
- `DUI70!StrToID` at `0x180015fec`
- `DUI70!StrToID` at `0x180015fec`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180015ff9`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180015ff9`

## pseudocode

```c
__int64 __fastcall AccessibilityCplCore::SaveAdminSettings(DirectUI::Element **this)
{
  unsigned int v2; // edi
  BOOL Selected; // edi
  unsigned __int16 v4; // ax
  DirectUI::Element *Descendent; // rax
  __int64 v6; // rbx
  struct IAccessibilityCplAdmin *v8; // [rsp+38h] [rbp+10h] BYREF
  __int64 v9; // [rsp+40h] [rbp+18h] BYREF

  v8 = 0;
  if ( (int)AccessibilityCplCore::GetAdminObject((AccessibilityCplCore *)this, &v8) >= 0 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v9);
    StartList::BuildConfigString(&v9, this + 5);
    Selected = 0;
    v4 = StrToID(L"hardwarebuttonlaunchsave");
    Descendent = DirectUI::Element::FindDescendent(this[12], v4);
    if ( Descendent )
      Selected = DirectUI::Element::GetSelected(Descendent);
    v6 = v9;
    v2 = (*(__int64 (__fastcall **)(struct IAccessibilityCplAdmin *, __int64, BOOL))(*(_QWORD *)v8 + 32LL))(
           v8,
           v9,
           Selected);
    ATL::CStringData::Release((ATL::CStringData *)(v6 - 24));
  }
  else
  {
    v2 = -2147467259;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v8);
  return v2;
}

```

## disassembly

```asm
0x180015fa0  mov     [rsp+arg_0], rbx
0x180015fa5  push    rdi
0x180015fa6  sub     rsp, 20h
0x180015faa  lea     rdx, [rsp+28h+arg_8]; struct IAccessibilityCplAdmin **
0x180015faf  mov     [rsp+28h+arg_8], 0
0x180015fb8  mov     rbx, rcx
0x180015fbb  call    ?GetAdminObject@AccessibilityCplCore@@AEAAJPEAPEAUIAccessibilityCplAdmin@@@Z; AccessibilityCplCore::GetAdminObject(IAccessibilityCplAdmin * *)
0x180015fc0  test    eax, eax
0x180015fc2  jns     short loc_180015FCB
0x180015fc4  mov     edi, 80004005h
0x180015fc9  jmp     short loc_180016037
0x180015fcb  lea     rcx, [rsp+28h+arg_10]
0x180015fd0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180015fd5  lea     rdx, [rbx+28h]
0x180015fd9  lea     rcx, [rsp+28h+arg_10]
0x180015fde  call    ?BuildConfigString@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &)
0x180015fe3  lea     rcx, aHardwarebutton; "hardwarebuttonlaunchsave"
0x180015fea  xor     edi, edi
0x180015fec  call    cs:__imp_StrToID
0x180015ff2  mov     rcx, [rbx+60h]
0x180015ff6  movzx   edx, ax
0x180015ff9  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180015fff  test    rax, rax
0x180016002  jz      short loc_180016010
0x180016004  mov     rcx, rax
0x180016007  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x18001600d  movzx   edi, al
0x180016010  mov     rcx, [rsp+28h+arg_8]
0x180016015  mov     r8d, edi
0x180016018  mov     rbx, [rsp+28h+arg_10]
0x18001601d  mov     rdx, rbx
0x180016020  mov     rax, [rcx]
0x180016023  mov     rax, [rax+20h]
0x180016027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001602c  lea     rcx, [rbx-18h]; this
0x180016030  mov     edi, eax
0x180016032  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180016037  lea     rcx, [rsp+28h+arg_8]
0x18001603c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180016041  mov     rbx, [rsp+28h+arg_0]
0x180016046  mov     eax, edi
0x180016048  add     rsp, 20h
0x18001604c  pop     rdi
0x18001604d  retn
```
