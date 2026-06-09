# StartList::SaveSettings(void)

- ea: `0x180023de8`
- end: `0x180023ef2`
- name: `?SaveSettings@StartList@@AEAAJXZ`
- size: `266`
- prototype: `__int64 __fastcall(StartList *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021610`
- `0x1800237e8`

## callees

- `0x1800043d4`
- `0x180015780`
- `0x1800218bc`
- `0x180023de8`
- `0x18002486c`
- `0x1800255ac`
- `0x18002561c`
- `0x1800295d4`
- `0x1800295f4`

## string_xrefs

- `0x180023e6f`: `SettingConfiguration`
- `0x180023eb1`: `Configuration`
- `0x180023e45`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\OOBE`
- `0x180023e4c`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility`
- `0x180023eb8`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StartList::SaveSettings(StartList *this)
{
  bool IsDesktopOOBEUserSessionActive; // bp
  int IsInteractiveUser; // edi
  const WCHAR *v4; // rdx
  unsigned __int16 *v5; // rbx
  StartList *v6; // rdx
  unsigned __int16 *v7; // rbx
  unsigned int v8; // ebx
  _BYTE v10[40]; // [rsp+20h] [rbp-28h] BYREF
  unsigned int v11; // [rsp+58h] [rbp+10h] BYREF
  unsigned __int16 *v12; // [rsp+60h] [rbp+18h] BYREF

  v11 = 0;
  _Trace::_Trace((_Trace *)v10, L"StartList::SaveSettings", (int *)&v11);
  IsDesktopOOBEUserSessionActive = CATUtils::IsDesktopOOBEUserSessionActive();
  IsInteractiveUser = CATUtils::IsInteractiveUser();
  if ( IsDesktopOOBEUserSessionActive )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v12);
    StartList::BuildConfigString(&v12, (char *)this + 144);
    v4 = StartList::_accessibilityKeyString;
    if ( !IsInteractiveUser )
      v4 = StartList::_oobeAccessibilityKeyString;
    v5 = v12;
    anonymous_namespace_::WriteAccessibilityConfigStringListToRegistry(
      (HKEY)(-(__int64)(IsInteractiveUser != 0) - 2147483646),
      v4,
      StartList::_settingConfiguration,
      v12);
    ATL::CStringData::Release((ATL::CStringData *)(v5 - 12));
  }
  if ( IsInteractiveUser )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v12);
    v6 = (StartList *)((char *)this + 48);
    if ( !IsDesktopOOBEUserSessionActive )
      v6 = this;
    StartList::BuildConfigString(&v12, v6);
    v7 = v12;
    anonymous_namespace_::WriteAccessibilityConfigStringListToRegistry(
      HKEY_CURRENT_USER,
      StartList::_accessibilityKeyString,
      StartList::_configuration,
      v12);
    ATL::CStringData::Release((ATL::CStringData *)(v7 - 12));
  }
  v8 = v11;
  _Trace::~_Trace((_Trace *)v10);
  return v8;
}

```

## disassembly

```asm
0x180023de8  mov     rax, rsp
0x180023deb  mov     [rax+8], rbx
0x180023def  push    rbp
0x180023df0  push    rsi
0x180023df1  push    rdi
0x180023df2  sub     rsp, 30h
0x180023df6  mov     rsi, rcx
0x180023df9  mov     dword ptr [rax+10h], 0
0x180023e00  lea     r8, [rax+10h]; int *
0x180023e04  lea     rdx, aStartlistSaves_0; "StartList::SaveSettings"
0x180023e0b  lea     rcx, [rax-28h]; this
0x180023e0f  call    ??0_Trace@@QEAA@PEBGPEAJ@Z; _Trace::_Trace(ushort const *,long *)
0x180023e14  nop
0x180023e15  call    ?IsDesktopOOBEUserSessionActive@CATUtils@@SA_NXZ; CATUtils::IsDesktopOOBEUserSessionActive(void)
0x180023e1a  mov     bpl, al
0x180023e1d  call    ?IsInteractiveUser@CATUtils@@SAHXZ; CATUtils::IsInteractiveUser(void)
0x180023e22  mov     edi, eax
0x180023e24  test    bpl, bpl
0x180023e27  jz      short loc_180023E85
0x180023e29  lea     rcx, [rsp+48h+arg_10]
0x180023e2e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180023e33  nop
0x180023e34  lea     rdx, [rsi+90h]
0x180023e3b  lea     rcx, [rsp+48h+arg_10]
0x180023e40  call    ?BuildConfigString@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &)
0x180023e45  lea     rax, ?_oobeAccessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180023e4c  lea     rdx, ?_accessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180023e53  test    edi, edi
0x180023e55  cmovz   rdx, rax; lpSubKey
0x180023e59  mov     eax, edi
0x180023e5b  neg     eax
0x180023e5d  sbb     rcx, rcx
0x180023e60  add     rcx, 0FFFFFFFF80000002h; hKey
0x180023e67  mov     rbx, [rsp+48h+arg_10]
0x180023e6c  mov     r9, rbx; unsigned __int16 *
0x180023e6f  lea     r8, ?_settingConfiguration@StartList@@0PAGA; "SettingConfiguration"
0x180023e76  call    _anonymous_namespace___WriteAccessibilityConfigStringListToRegistry
0x180023e7b  nop
0x180023e7c  lea     rcx, [rbx-18h]; this
0x180023e80  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180023e85  test    edi, edi
0x180023e87  jz      short loc_180023ED5
0x180023e89  lea     rcx, [rsp+48h+arg_10]
0x180023e8e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180023e93  nop
0x180023e94  lea     rdx, [rsi+30h]
0x180023e98  test    bpl, bpl
0x180023e9b  cmovz   rdx, rsi
0x180023e9f  lea     rcx, [rsp+48h+arg_10]
0x180023ea4  call    ?BuildConfigString@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &)
0x180023ea9  mov     rbx, [rsp+48h+arg_10]
0x180023eae  mov     r9, rbx; unsigned __int16 *
0x180023eb1  lea     r8, ?_configuration@StartList@@0PAGA; "Configuration"
0x180023eb8  lea     rdx, ?_accessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180023ebf  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180023ec6  call    _anonymous_namespace___WriteAccessibilityConfigStringListToRegistry
0x180023ecb  nop
0x180023ecc  lea     rcx, [rbx-18h]; this
0x180023ed0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180023ed5  mov     ebx, [rsp+48h+arg_8]
0x180023ed9  lea     rcx, [rsp+48h+var_28]; this
0x180023ede  call    ??1_Trace@@QEAA@XZ; _Trace::~_Trace(void)
0x180023ee3  mov     eax, ebx
0x180023ee5  mov     rbx, [rsp+48h+arg_0]
0x180023eea  add     rsp, 30h
0x180023eee  pop     rdi
0x180023eef  pop     rsi
0x180023ef0  pop     rbp
0x180023ef1  retn
```
