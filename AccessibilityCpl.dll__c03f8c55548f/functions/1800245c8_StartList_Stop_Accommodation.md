# StartList::Stop(Accommodation *)

- ea: `0x1800245c8`
- end: `0x1800246a7`
- name: `?Stop@StartList@@QEAAJPEAVAccommodation@@@Z`
- size: `223`
- prototype: `__int64 __fastcall(StartList *__hidden this, struct Accommodation *)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180004a80`
- `0x180015dd0`
- `0x18001aab0`

## callees

- `0x1800063c0`
- `0x180015848`
- `0x180023090`
- `0x1800237e8`
- `0x180023bc0`
- `0x1800245c8`
- `0x180025eb4`
- `0x1800295d4`
- `0x1800295f4`
- `0x18002d1fa`

## import_xrefs

- `msvcrt!_wtoi` at `0x18002463a`
- `msvcrt!_wtoi` at `0x18002463a`

## pseudocode

```c
__int64 __fastcall StartList::Stop(StartList *this, const wchar_t **a2)
{
  __int64 result; // rax
  signed int v5; // edi
  unsigned int v6; // eax
  __int64 v7; // r8
  unsigned __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // r11

  if ( !a2 )
    return 2147942487LL;
  if ( CATUtils::IsDesktopOOBEUserSessionActive() && !wcscmp_0(a2[5], L"SystemSetting") )
    StartList::Remove(this, (struct Accommodation *)a2);
  result = StartList::LoadSettings(this);
  v5 = result;
  if ( (int)result >= 0 )
  {
    if ( !wcscmp_0(a2[5], L"SystemSetting") )
    {
      v6 = _wtoi(a2[3]);
      if ( v6 < 0x16 )
        v5 = SystemSettings::TurnOff(a2, v6, v7, *((_DWORD *)this + 73));
    }
    v8 = (-(__int64)((unsigned int)CATUtils::IsInteractiveUser() != 0) & 0xFFFFFFFFFFFFFFD0uLL) + 96;
    if ( v5 >= 0 )
    {
      v9 = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
             (char *)this + v8,
             *a2);
      if ( v9 )
        ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAt(
          v10,
          v9);
      StartList::SaveSessionKey(this);
    }
    return (unsigned int)v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800245c8  mov     [rsp+arg_0], rbx
0x1800245cd  mov     [rsp+arg_8], rsi
0x1800245d2  push    rdi
0x1800245d3  sub     rsp, 20h
0x1800245d7  mov     rbx, rdx
0x1800245da  mov     rsi, rcx
0x1800245dd  test    rdx, rdx
0x1800245e0  jnz     short loc_1800245EC
0x1800245e2  mov     eax, 80070057h
0x1800245e7  jmp     loc_180024697
0x1800245ec  call    ?IsDesktopOOBEUserSessionActive@CATUtils@@SA_NXZ; CATUtils::IsDesktopOOBEUserSessionActive(void)
0x1800245f1  test    al, al
0x1800245f3  jz      short loc_180024614
0x1800245f5  mov     rcx, [rbx+28h]; String1
0x1800245f9  lea     rdx, aSystemsetting; "SystemSetting"
0x180024600  call    wcscmp_0
0x180024605  test    eax, eax
0x180024607  jnz     short loc_180024614
0x180024609  mov     rdx, rbx; struct Accommodation *
0x18002460c  mov     rcx, rsi; this
0x18002460f  call    ?Remove@StartList@@QEAAJPEAVAccommodation@@@Z; StartList::Remove(Accommodation *)
0x180024614  mov     rcx, rsi; this
0x180024617  call    ?LoadSettings@StartList@@AEAAJXZ; StartList::LoadSettings(void)
0x18002461c  mov     edi, eax
0x18002461e  test    eax, eax
0x180024620  js      short loc_180024697
0x180024622  mov     rcx, [rbx+28h]; String1
0x180024626  lea     rdx, aSystemsetting; "SystemSetting"
0x18002462d  call    wcscmp_0
0x180024632  test    eax, eax
0x180024634  jnz     short loc_180024658
0x180024636  mov     rcx, [rbx+18h]; String
0x18002463a  call    cs:__imp__wtoi
0x180024640  cmp     eax, 16h
0x180024643  jnb     short loc_180024658
0x180024645  mov     r9d, [rsi+124h]
0x18002464c  mov     edx, eax
0x18002464e  mov     rcx, rbx
0x180024651  call    ?TurnOff@SystemSettings@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@IPEAXH@Z; SystemSettings::TurnOff(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,uint,void *,int)
0x180024656  mov     edi, eax
0x180024658  call    ?IsInteractiveUser@CATUtils@@SAHXZ; CATUtils::IsInteractiveUser(void)
0x18002465d  neg     eax
0x18002465f  sbb     rcx, rcx
0x180024662  and     rcx, 0FFFFFFFFFFFFFFD0h
0x180024666  add     rcx, 60h ; '`'
0x18002466a  test    edi, edi
0x18002466c  js      short loc_180024695
0x18002466e  mov     rdx, [rbx]
0x180024671  lea     r11, [rcx+rsi]
0x180024675  mov     rcx, r11
0x180024678  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x18002467d  test    rax, rax
0x180024680  jz      short loc_18002468D
0x180024682  mov     rdx, rax
0x180024685  mov     rcx, r11
0x180024688  call    ?RemoveAt@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXPEAU__POSITION@@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAt(__POSITION *)
0x18002468d  mov     rcx, rsi; this
0x180024690  call    ?SaveSessionKey@StartList@@AEAAXXZ; StartList::SaveSessionKey(void)
0x180024695  mov     eax, edi
0x180024697  mov     rbx, [rsp+28h+arg_0]
0x18002469c  mov     rsi, [rsp+28h+arg_8]
0x1800246a1  add     rsp, 20h
0x1800246a5  pop     rdi
0x1800246a6  retn
```
