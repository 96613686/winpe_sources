# StartList::SaveSettings(void)

- ea: `0x14000fd08`
- end: `0x14000fe6e`
- name: `?SaveSettings@StartList@@AEAAJXZ`
- size: `358`
- prototype: `__int64 __fastcall(StartList *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000cfd0`
- `0x14000f810`

## callees

- `0x140006a78`
- `0x14000c220`
- `0x14000c2bc`
- `0x14000d334`
- `0x14000fd08`
- `0x140010e44`
- `0x1400157f8`
- `0x140017010`

## string_xrefs

- `0x14000fda8`: `SettingConfiguration`
- `0x14000fe16`: `Configuration`
- `0x14000fd7e`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\OOBE`
- `0x14000fd85`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility`
- `0x14000fe1d`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility`

## pseudocode

```c
__int64 __fastcall StartList::SaveSettings(StartList *this)
{
  bool IsDesktopOOBEUserSessionActive; // si
  int v3; // edi
  const WCHAR *v4; // rdx
  BYTE *v5; // rbx
  StartList *v6; // rdx
  BYTE *v7; // rbx
  unsigned int v8; // ebx
  _BYTE v10[40]; // [rsp+20h] [rbp-28h] BYREF
  unsigned int v11; // [rsp+58h] [rbp+10h] BYREF
  BYTE *lpData; // [rsp+60h] [rbp+18h] BYREF

  v11 = 0;
  _Trace::_Trace((_Trace *)v10, L"StartList::SaveSettings", (int *)&v11);
  IsDesktopOOBEUserSessionActive = CATUtils::IsDesktopOOBEUserSessionActive();
  v3 = IsInteractiveUser();
  if ( IsDesktopOOBEUserSessionActive )
  {
    lpData = (BYTE *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    StartList::BuildConfigString(&lpData, (char *)this + 144);
    v4 = StartList::_accessibilityKeyString;
    if ( !v3 )
      v4 = StartList::_oobeAccessibilityKeyString;
    v5 = lpData;
    anonymous_namespace_::WriteAccessibilityConfigStringListToRegistry(
      (HKEY)(-(__int64)(v3 != 0) - 2147483646),
      v4,
      StartList::_settingConfiguration,
      lpData);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v5 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v5 - 3) + 8LL))(*((_QWORD *)v5 - 3));
  }
  if ( v3 )
  {
    lpData = (BYTE *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    v6 = (StartList *)((char *)this + 48);
    if ( !IsDesktopOOBEUserSessionActive )
      v6 = this;
    StartList::BuildConfigString(&lpData, v6);
    v7 = lpData;
    anonymous_namespace_::WriteAccessibilityConfigStringListToRegistry(
      HKEY_CURRENT_USER,
      StartList::_accessibilityKeyString,
      StartList::_configuration,
      lpData);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v7 - 3) + 8LL))(*((_QWORD *)v7 - 3));
  }
  v8 = v11;
  _Trace::~_Trace((_Trace *)v10);
  return v8;
}

```

## disassembly

```asm
0x14000fd08  mov     rax, rsp
0x14000fd0b  mov     [rax+8], rbx
0x14000fd0f  push    rbp
0x14000fd10  push    rsi
0x14000fd11  push    rdi
0x14000fd12  sub     rsp, 30h
0x14000fd16  mov     rbp, rcx
0x14000fd19  mov     dword ptr [rax+10h], 0
0x14000fd20  lea     r8, [rax+10h]; int *
0x14000fd24  lea     rdx, aStartlistSaves_0; "StartList::SaveSettings"
0x14000fd2b  lea     rcx, [rax-28h]; this
0x14000fd2f  call    ??0_Trace@@QEAA@PEBGPEAJ@Z; _Trace::_Trace(ushort const *,long *)
0x14000fd34  nop
0x14000fd35  call    ?IsDesktopOOBEUserSessionActive@CATUtils@@SA_NXZ; CATUtils::IsDesktopOOBEUserSessionActive(void)
0x14000fd3a  mov     sil, al
0x14000fd3d  call    ?IsInteractiveUser@@YAHXZ; IsInteractiveUser(void)
0x14000fd42  mov     edi, eax
0x14000fd44  test    sil, sil
0x14000fd47  jz      loc_14000FDD5
0x14000fd4d  mov     rcx, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000fd54  mov     rax, [rcx+18h]
0x14000fd58  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000fd5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fd64  add     rax, 18h
0x14000fd68  mov     [rsp+48h+lpData], rax
0x14000fd6d  lea     rdx, [rbp+90h]
0x14000fd74  lea     rcx, [rsp+48h+lpData]
0x14000fd79  call    ?BuildConfigString@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &)
0x14000fd7e  lea     rax, ?_oobeAccessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14000fd85  lea     rdx, ?_accessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14000fd8c  test    edi, edi
0x14000fd8e  cmovz   rdx, rax; lpSubKey
0x14000fd92  mov     eax, edi
0x14000fd94  neg     eax
0x14000fd96  sbb     rcx, rcx
0x14000fd99  add     rcx, 0FFFFFFFF80000002h; hKey
0x14000fda0  mov     rbx, [rsp+48h+lpData]
0x14000fda5  mov     r9, rbx; lpData
0x14000fda8  lea     r8, ?_settingConfiguration@StartList@@0PAGA; "SettingConfiguration"
0x14000fdaf  call    _anonymous_namespace___WriteAccessibilityConfigStringListToRegistry
0x14000fdb4  nop
0x14000fdb5  lea     rdx, [rbx-18h]
0x14000fdb9  or      eax, 0FFFFFFFFh
0x14000fdbc  lock xadd [rdx+10h], eax
0x14000fdc1  sub     eax, 1
0x14000fdc4  jg      short loc_14000FDD5
0x14000fdc6  mov     rcx, [rdx]
0x14000fdc9  mov     rax, [rcx]
0x14000fdcc  mov     rax, [rax+8]
0x14000fdd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fdd5  test    edi, edi
0x14000fdd7  jz      short loc_14000FE51
0x14000fdd9  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000fde0  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000fde7  mov     rax, [rax+18h]
0x14000fdeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fdf0  add     rax, 18h
0x14000fdf4  mov     [rsp+48h+lpData], rax
0x14000fdf9  lea     rdx, [rbp+30h]
0x14000fdfd  test    sil, sil
0x14000fe00  cmovz   rdx, rbp
0x14000fe04  lea     rcx, [rsp+48h+lpData]
0x14000fe09  call    ?BuildConfigString@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &)
0x14000fe0e  mov     rbx, [rsp+48h+lpData]
0x14000fe13  mov     r9, rbx; lpData
0x14000fe16  lea     r8, ?_configuration@StartList@@0PAGA; "Configuration"
0x14000fe1d  lea     rdx, ?_accessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14000fe24  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14000fe2b  call    _anonymous_namespace___WriteAccessibilityConfigStringListToRegistry
0x14000fe30  nop
0x14000fe31  lea     rdx, [rbx-18h]
0x14000fe35  or      eax, 0FFFFFFFFh
0x14000fe38  lock xadd [rdx+10h], eax
0x14000fe3d  sub     eax, 1
0x14000fe40  jg      short loc_14000FE51
0x14000fe42  mov     rcx, [rdx]
0x14000fe45  mov     rax, [rcx]
0x14000fe48  mov     rax, [rax+8]
0x14000fe4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fe51  mov     ebx, [rsp+48h+arg_8]
0x14000fe55  lea     rcx, [rsp+48h+var_28]; this
0x14000fe5a  call    ??1_Trace@@QEAA@XZ; _Trace::~_Trace(void)
0x14000fe5f  mov     eax, ebx
0x14000fe61  mov     rbx, [rsp+48h+arg_0]
0x14000fe66  add     rsp, 30h
0x14000fe6a  pop     rdi
0x14000fe6b  pop     rsi
0x14000fe6c  pop     rbp
0x14000fe6d  retn
```
