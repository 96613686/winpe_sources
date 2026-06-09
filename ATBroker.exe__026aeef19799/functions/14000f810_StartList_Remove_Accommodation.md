# StartList::Remove(Accommodation *)

- ea: `0x14000f810`
- end: `0x14000f904`
- name: `?Remove@StartList@@QEAAJPEAVAccommodation@@@Z`
- size: `244`
- prototype: `__int64 __fastcall(StartList *__hidden this, struct Accommodation *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140009264`
- `0x14000c8b4`

## callees

- `0x1400053cc`
- `0x14000c420`
- `0x14000c864`
- `0x14000ee8c`
- `0x14000f810`
- `0x14000fd08`
- `0x140015ace`
- `0x140017010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StartList::Remove(StartList *this, const wchar_t **a2)
{
  __int64 result; // rax
  int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rdi
  volatile signed __int32 *v9; // r11
  StartList *v10; // rcx
  __int64 v11; // rax
  volatile signed __int32 *v12; // r11

  if ( !a2 )
    return 2147942487LL;
  result = StartList::LoadSettings(this);
  if ( (int)result >= 0 )
  {
    v5 = wcscmp_0(a2[5], L"SystemSetting");
    v6 = (__int64)(*a2 - 12);
    if ( v5 )
    {
      v7 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v6);
      v8 = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
             this,
             v7 + 24);
      if ( _InterlockedExchangeAdd(v9 + 4, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v9 + 8LL))(*(_QWORD *)v9, v9);
      if ( !v8 )
        return StartList::SaveSettings(this);
      v10 = this;
    }
    else
    {
      v11 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v6);
      v8 = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
             (char *)this + 144,
             v11 + 24);
      if ( _InterlockedExchangeAdd(v12 + 4, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v12 + 8LL))(*(_QWORD *)v12, v12);
      if ( !v8 )
        return StartList::SaveSettings(this);
      v10 = (StartList *)((char *)this + 144);
    }
    ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAt(
      v10,
      v8);
    return StartList::SaveSettings(this);
  }
  return result;
}

```

## disassembly

```asm
0x14000f810  mov     [rsp+arg_0], rbx
0x14000f815  mov     [rsp+arg_8], rsi
0x14000f81a  push    rdi
0x14000f81b  sub     rsp, 20h
0x14000f81f  mov     rdi, rdx
0x14000f822  mov     rbx, rcx
0x14000f825  test    rdx, rdx
0x14000f828  jnz     short loc_14000F834
0x14000f82a  mov     eax, 80070057h
0x14000f82f  jmp     loc_14000F8F4
0x14000f834  call    ?LoadSettings@StartList@@AEAAJXZ; StartList::LoadSettings(void)
0x14000f839  test    eax, eax
0x14000f83b  js      loc_14000F8F4
0x14000f841  lea     rdx, aSystemsetting; "SystemSetting"
0x14000f848  mov     rcx, [rdi+28h]; String1
0x14000f84c  call    wcscmp_0
0x14000f851  nop
0x14000f852  mov     rcx, [rdi]
0x14000f855  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14000f859  test    eax, eax
0x14000f85b  jz      short loc_14000F89E
0x14000f85d  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14000f862  mov     r11, rax
0x14000f865  lea     rdx, [rax+18h]
0x14000f869  mov     rcx, rbx
0x14000f86c  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x14000f871  mov     rdi, rax
0x14000f874  or      ecx, 0FFFFFFFFh
0x14000f877  lock xadd [r11+10h], ecx
0x14000f87d  sub     ecx, 1
0x14000f880  jg      short loc_14000F894
0x14000f882  mov     rcx, [r11]
0x14000f885  mov     rdx, [rcx]
0x14000f888  mov     rax, [rdx+8]
0x14000f88c  mov     rdx, r11
0x14000f88f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f894  test    rdi, rdi
0x14000f897  jz      short loc_14000F8EC
0x14000f899  mov     rcx, rbx
0x14000f89c  jmp     short loc_14000F8E4
0x14000f89e  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14000f8a3  mov     r11, rax
0x14000f8a6  lea     rdx, [rax+18h]
0x14000f8aa  lea     rsi, [rbx+90h]
0x14000f8b1  mov     rcx, rsi
0x14000f8b4  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x14000f8b9  mov     rdi, rax
0x14000f8bc  or      ecx, 0FFFFFFFFh
0x14000f8bf  lock xadd [r11+10h], ecx
0x14000f8c5  sub     ecx, 1
0x14000f8c8  jg      short loc_14000F8DC
0x14000f8ca  mov     rcx, [r11]
0x14000f8cd  mov     rdx, [rcx]
0x14000f8d0  mov     rax, [rdx+8]
0x14000f8d4  mov     rdx, r11
0x14000f8d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f8dc  test    rdi, rdi
0x14000f8df  jz      short loc_14000F8EC
0x14000f8e1  mov     rcx, rsi
0x14000f8e4  mov     rdx, rdi
0x14000f8e7  call    ?RemoveAt@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXPEAU__POSITION@@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAt(__POSITION *)
0x14000f8ec  mov     rcx, rbx; this
0x14000f8ef  call    ?SaveSettings@StartList@@AEAAJXZ; StartList::SaveSettings(void)
0x14000f8f4  mov     rbx, [rsp+28h+arg_0]
0x14000f8f9  mov     rsi, [rsp+28h+arg_8]
0x14000f8fe  add     rsp, 20h
0x14000f902  pop     rdi
0x14000f903  retn
```
