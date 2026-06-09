# AccessibilityCplCore::Save3rdPartyAT(DirectUI::Element *,ATData *)

- ea: `0x180015dd0`
- end: `0x180015ead`
- name: `?Save3rdPartyAT@AccessibilityCplCore@@AEAAJPEAVElement@DirectUI@@PEAVATData@@@Z`
- size: `221`
- prototype: `__int64 __fastcall(AccessibilityCplCore *__hidden this, struct DirectUI::Element *, struct ATData *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015eb4`

## callees

- `0x180004e48`
- `0x1800055c0`
- `0x180014828`
- `0x180015dd0`
- `0x18001aab0`
- `0x1800245c8`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180015e86`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180015e86`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180015e37`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180015e37`

## string_xrefs

- `0x180015e50`: `Software\Microsoft\Windows NT\CurrentVersion\AccessibilityTemp`

## pseudocode

```c
__int64 __fastcall AccessibilityCplCore::Save3rdPartyAT(
        StartList **this,
        struct DirectUI::Element *a2,
        struct ATData *a3)
{
  __int64 v5; // rax
  struct Accommodation *v6; // rbx
  int v8; // edi
  HKEY hKey[9]; // [rsp+30h] [rbp-48h] BYREF

  v5 = (*(__int64 (__fastcall **)(struct ATData *))(*(_QWORD *)a3 + 16LL))(a3);
  v6 = (struct Accommodation *)v5;
  if ( !v5 )
    return 2147500037LL;
  v8 = 0;
  if ( (unsigned __int8)ATL::operator!=(v5 + 40) )
  {
    v8 = AccessibilityCplCore::ToggleAT((AccessibilityCplCore *)this, v6, a2, *((_DWORD *)v6 + 20) != 1, 1);
    if ( v8 >= 0 && !DirectUI::Element::GetSelected(a2) )
    {
      memset(hKey, 0, 24);
      if ( !(unsigned int)ATL::CRegKey::Open(
                            (ATL::CRegKey *)hKey,
                            HKEY_CURRENT_USER,
                            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AccessibilityTemp",
                            0x20006u) )
        RegDeleteValueW(hKey[0], *(LPCWSTR *)v6);
      StartList::Stop(this[11], v6);
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180015dd0  push    rbx
0x180015dd2  push    rbp
0x180015dd3  push    rsi
0x180015dd4  push    rdi
0x180015dd5  sub     rsp, 58h
0x180015dd9  mov     rax, [r8]
0x180015ddc  mov     rbp, rcx
0x180015ddf  mov     rcx, r8
0x180015de2  mov     rsi, rdx
0x180015de5  mov     rax, [rax+10h]
0x180015de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015dee  mov     rbx, rax
0x180015df1  test    rax, rax
0x180015df4  jnz     short loc_180015E00
0x180015df6  mov     eax, 80004005h
0x180015dfb  jmp     loc_180015EA4
0x180015e00  lea     rcx, [rax+28h]
0x180015e04  xor     edi, edi
0x180015e06  call    ??9ATL@@YA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@PEBG@Z; ATL::operator!=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x180015e0b  test    al, al
0x180015e0d  jz      loc_180015EA2
0x180015e13  cmp     dword ptr [rbx+50h], 1
0x180015e17  mov     r8, rsi; struct DirectUI::Element *
0x180015e1a  mov     rdx, rbx; struct Accommodation *
0x180015e1d  mov     [rsp+78h+var_58], 1; bool
0x180015e22  setnz   r9b; bool
0x180015e26  mov     rcx, rbp; this
0x180015e29  call    ?ToggleAT@AccessibilityCplCore@@AEAAJPEAVAccommodation@@PEAVElement@DirectUI@@_N2@Z; AccessibilityCplCore::ToggleAT(Accommodation *,DirectUI::Element *,bool,bool)
0x180015e2e  mov     edi, eax
0x180015e30  test    eax, eax
0x180015e32  js      short loc_180015EA2
0x180015e34  mov     rcx, rsi
0x180015e37  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x180015e3d  test    al, al
0x180015e3f  jnz     short loc_180015EA2
0x180015e41  mov     r9d, 20006h; unsigned int
0x180015e47  mov     [rsp+78h+hKey], 0
0x180015e50  lea     r8, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x180015e57  mov     [rsp+78h+var_40], 0
0x180015e60  mov     rdx, 0FFFFFFFF80000001h; hKey
0x180015e67  mov     [rsp+78h+var_38], 0
0x180015e70  lea     rcx, [rsp+78h+hKey]; this
0x180015e75  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180015e7a  test    eax, eax
0x180015e7c  jnz     short loc_180015E8C
0x180015e7e  mov     rdx, [rbx]; lpValueName
0x180015e81  mov     rcx, [rsp+78h+hKey]; hKey
0x180015e86  call    cs:__imp_RegDeleteValueW
0x180015e8c  mov     rcx, [rbp+58h]; this
0x180015e90  mov     rdx, rbx; struct Accommodation *
0x180015e93  call    ?Stop@StartList@@QEAAJPEAVAccommodation@@@Z; StartList::Stop(Accommodation *)
0x180015e98  lea     rcx, [rsp+78h+hKey]; this
0x180015e9d  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180015ea2  mov     eax, edi
0x180015ea4  add     rsp, 58h
0x180015ea8  pop     rdi
0x180015ea9  pop     rsi
0x180015eaa  pop     rbp
0x180015eab  pop     rbx
0x180015eac  retn
```
