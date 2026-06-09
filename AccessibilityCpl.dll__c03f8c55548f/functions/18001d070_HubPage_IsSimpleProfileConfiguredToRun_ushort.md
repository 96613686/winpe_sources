# HubPage::IsSimpleProfileConfiguredToRun(ushort *)

- ea: `0x18001d070`
- end: `0x18001d182`
- name: `?IsSimpleProfileConfiguredToRun@HubPage@@AEAAHPEAG@Z`
- size: `274`
- prototype: `int(HubPage *__hidden this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d6dc`
- `0x18001d978`

## callees

- `0x180005534`
- `0x1800063c0`
- `0x1800071c4`
- `0x180015780`
- `0x18001d070`
- `0x180023090`
- `0x18002501c`
- `0x180025068`
- `0x180025344`

## import_xrefs

- `msvcrt!wcsstr` at `0x18001d0d2`
- `msvcrt!wcsstr` at `0x18001d0d2`

## pseudocode

```c
__int64 __fastcall HubPage::IsSimpleProfileConfiguredToRun(HubPage *this, unsigned __int16 *a2)
{
  unsigned int v3; // edi
  HubPage *v4; // rcx
  __int64 Next; // rax
  _QWORD *v6; // rsi
  __int64 v7; // rax
  __int64 v8; // rbx
  ATL::CStringData *v9; // r11
  __int64 v10; // rax
  __int64 v11; // rbx
  ATL::CStringData *v12; // r11
  _BYTE v14[48]; // [rsp+20h] [rbp-178h] BYREF
  _BYTE v15[304]; // [rsp+50h] [rbp-148h] BYREF
  HubPage *v16; // [rsp+1A0h] [rbp+8h] BYREF

  v16 = this;
  v3 = 0;
  ATManager::ATManager((ATManager *)v14);
  v4 = *(HubPage **)ATManager::GetAccommodations((__int64)v14);
  v16 = v4;
  while ( v16 )
  {
    Next = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::GetNext(
             v4,
             &v16);
    v6 = *(_QWORD **)Next;
    if ( wcsstr(*(const wchar_t **)(*(_QWORD *)Next + 40LL), a2) )
    {
      StartList::LoadSettings((StartList *)v14);
      v7 = ATL::CSimpleStringT<unsigned short,0>::CloneData(*v6 - 24LL);
      v8 = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
             v14,
             v7 + 24);
      ATL::CStringData::Release(v9);
      if ( v8 )
        v3 = 1;
      StartList::LoadSettings((StartList *)v14);
      v10 = ATL::CSimpleStringT<unsigned short,0>::CloneData(*v6 - 24LL);
      v11 = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
              v15,
              v10 + 24);
      ATL::CStringData::Release(v12);
      if ( v11 )
        v3 = 1;
    }
  }
  ATManager::~ATManager((ATManager *)v14);
  return v3;
}

```

## disassembly

```asm
0x18001d070  mov     [rsp+arg_8], rbx
0x18001d075  mov     [rsp+arg_10], rbp
0x18001d07a  mov     [rsp+arg_0], rcx
0x18001d07f  push    rsi
0x18001d080  push    rdi
0x18001d081  push    r14
0x18001d083  sub     rsp, 180h
0x18001d08a  lea     rcx, [rsp+198h+var_178]; this
0x18001d08f  mov     rbp, rdx
0x18001d092  xor     edi, edi
0x18001d094  call    ??0ATManager@@QEAA@XZ; ATManager::ATManager(void)
0x18001d099  lea     rcx, [rsp+198h+var_178]
0x18001d09e  call    ?GetAccommodations@ATManager@@QEAAAEBV?$CAtlList@PEAVAccommodation@@V?$CElementTraits@PEAVAccommodation@@@ATL@@@ATL@@XZ; ATManager::GetAccommodations(void)
0x18001d0a3  mov     rcx, [rax]
0x18001d0a6  mov     [rsp+198h+arg_0], rcx
0x18001d0ae  test    rcx, rcx
0x18001d0b1  jz      loc_18001D15E
0x18001d0b7  lea     r14d, [rdi+1]
0x18001d0bb  lea     rdx, [rsp+198h+arg_0]
0x18001d0c3  call    ?GetNext@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAPEAU__POSITION@@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::GetNext(__POSITION * &)
0x18001d0c8  mov     rdx, rbp; SubStr
0x18001d0cb  mov     rsi, [rax]
0x18001d0ce  mov     rcx, [rsi+28h]; Str
0x18001d0d2  call    cs:__imp_wcsstr
0x18001d0d8  test    rax, rax
0x18001d0db  jz      short loc_18001D14F
0x18001d0dd  lea     rcx, [rsp+198h+var_178]; this
0x18001d0e2  call    ?LoadSettings@StartList@@AEAAJXZ; StartList::LoadSettings(void)
0x18001d0e7  mov     rcx, [rsi]
0x18001d0ea  sub     rcx, 18h
0x18001d0ee  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18001d0f3  lea     rcx, [rsp+198h+var_178]
0x18001d0f8  mov     r11, rax
0x18001d0fb  lea     rdx, [rax+18h]
0x18001d0ff  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x18001d104  mov     rcx, r11; this
0x18001d107  mov     rbx, rax
0x18001d10a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001d10f  test    rbx, rbx
0x18001d112  lea     rcx, [rsp+198h+var_178]; this
0x18001d117  cmovnz  edi, r14d
0x18001d11b  call    ?LoadSettings@StartList@@AEAAJXZ; StartList::LoadSettings(void)
0x18001d120  mov     rcx, [rsi]
0x18001d123  sub     rcx, 18h
0x18001d127  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18001d12c  lea     rcx, [rsp+198h+var_148]
0x18001d131  mov     r11, rax
0x18001d134  lea     rdx, [rax+18h]
0x18001d138  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x18001d13d  mov     rcx, r11; this
0x18001d140  mov     rbx, rax
0x18001d143  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001d148  test    rbx, rbx
0x18001d14b  cmovnz  edi, r14d
0x18001d14f  cmp     [rsp+198h+arg_0], 0
0x18001d158  jnz     loc_18001D0BB
0x18001d15e  lea     rcx, [rsp+198h+var_178]; this
0x18001d163  call    ??1ATManager@@QEAA@XZ; ATManager::~ATManager(void)
0x18001d168  lea     r11, [rsp+198h+var_18]
0x18001d170  mov     eax, edi
0x18001d172  mov     rbx, [r11+28h]
0x18001d176  mov     rbp, [r11+30h]
0x18001d17a  mov     rsp, r11
0x18001d17d  pop     r14
0x18001d17f  pop     rdi
0x18001d180  pop     rsi
0x18001d181  retn
```
