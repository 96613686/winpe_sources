# StartList::Add(Accommodation *)

- ea: `0x14000cfd0`
- end: `0x14000d110`
- name: `?Add@StartList@@QEAAJPEAVAccommodation@@@Z`
- size: `320`
- prototype: `__int64 __fastcall(StartList *__hidden this, struct Accommodation *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000c8b4`
- `0x140010244`

## callees

- `0x1400053cc`
- `0x14000c340`
- `0x14000c420`
- `0x14000cfd0`
- `0x14000ee8c`
- `0x14000fd08`
- `0x140015ace`
- `0x140017010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StartList::Add(StartList *this, const wchar_t **a2)
{
  __int64 result; // rax
  int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rbp
  volatile signed __int32 *v9; // r11
  volatile signed __int32 *v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rbp
  volatile signed __int32 *v13; // r11

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
      if ( v8 )
        return StartList::SaveSettings(this);
      v10 = (volatile signed __int32 *)ATL::CSimpleStringT<unsigned short,0>::CloneData(*a2 - 12);
      ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddTail(
        this,
        v10 + 6);
    }
    else
    {
      v11 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v6);
      v12 = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
              (char *)this + 144,
              v11 + 24);
      if ( _InterlockedExchangeAdd(v13 + 4, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v13 + 8LL))(*(_QWORD *)v13, v13);
      if ( v12 )
        return StartList::SaveSettings(this);
      v10 = (volatile signed __int32 *)ATL::CSimpleStringT<unsigned short,0>::CloneData(*a2 - 12);
      ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddTail(
        (char *)this + 144,
        v10 + 6);
    }
    if ( _InterlockedExchangeAdd(v10 + 4, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v10 + 8LL))(*(_QWORD *)v10, v10);
    return StartList::SaveSettings(this);
  }
  return result;
}

```

## disassembly

```asm
0x14000cfd0  push    rbx
0x14000cfd2  push    rbp
0x14000cfd3  push    rdi
0x14000cfd4  push    r14
0x14000cfd6  sub     rsp, 28h
0x14000cfda  mov     rbx, rdx
0x14000cfdd  mov     rdi, rcx
0x14000cfe0  test    rdx, rdx
0x14000cfe3  jnz     short loc_14000CFEF
0x14000cfe5  mov     eax, 80070057h
0x14000cfea  jmp     loc_14000D106
0x14000cfef  call    ?LoadSettings@StartList@@AEAAJXZ; StartList::LoadSettings(void)
0x14000cff4  test    eax, eax
0x14000cff6  js      loc_14000D106
0x14000cffc  lea     rdx, aSystemsetting; "SystemSetting"
0x14000d003  mov     rcx, [rbx+28h]; String1
0x14000d007  call    wcscmp_0
0x14000d00c  nop
0x14000d00d  mov     rcx, [rbx]
0x14000d010  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14000d014  test    eax, eax
0x14000d016  jz      short loc_14000D07B
0x14000d018  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14000d01d  mov     r11, rax
0x14000d020  lea     rdx, [rax+18h]
0x14000d024  mov     rcx, rdi
0x14000d027  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x14000d02c  mov     rbp, rax
0x14000d02f  or      ecx, 0FFFFFFFFh
0x14000d032  lock xadd [r11+10h], ecx
0x14000d038  sub     ecx, 1
0x14000d03b  jg      short loc_14000D04F
0x14000d03d  mov     rcx, [r11]
0x14000d040  mov     rdx, [rcx]
0x14000d043  mov     rax, [rdx+8]
0x14000d047  mov     rdx, r11
0x14000d04a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d04f  test    rbp, rbp
0x14000d052  jnz     loc_14000D0FE
0x14000d058  mov     rcx, [rbx]
0x14000d05b  sub     rcx, 18h
0x14000d05f  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14000d064  mov     rbx, rax
0x14000d067  lea     rdx, [rax+18h]
0x14000d06b  mov     [rsp+48h+arg_8], rdx
0x14000d070  mov     rcx, rdi
0x14000d073  call    ?AddTail@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddTail(ushort const *)
0x14000d078  nop
0x14000d079  jmp     short loc_14000D0DF
0x14000d07b  lea     r14, [rdi+90h]
0x14000d082  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14000d087  mov     r11, rax
0x14000d08a  lea     rdx, [rax+18h]
0x14000d08e  mov     rcx, r14
0x14000d091  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x14000d096  mov     rbp, rax
0x14000d099  or      ecx, 0FFFFFFFFh
0x14000d09c  lock xadd [r11+10h], ecx
0x14000d0a2  sub     ecx, 1
0x14000d0a5  jg      short loc_14000D0B9
0x14000d0a7  mov     rcx, [r11]
0x14000d0aa  mov     rdx, [rcx]
0x14000d0ad  mov     rax, [rdx+8]
0x14000d0b1  mov     rdx, r11
0x14000d0b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d0b9  test    rbp, rbp
0x14000d0bc  jnz     short loc_14000D0FE
0x14000d0be  mov     rcx, [rbx]
0x14000d0c1  sub     rcx, 18h
0x14000d0c5  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14000d0ca  mov     rbx, rax
0x14000d0cd  lea     rdx, [rax+18h]
0x14000d0d1  mov     [rsp+48h+arg_8], rdx
0x14000d0d6  mov     rcx, r14
0x14000d0d9  call    ?AddTail@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddTail(ushort const *)
0x14000d0de  nop
0x14000d0df  or      ecx, 0FFFFFFFFh
0x14000d0e2  lock xadd [rbx+10h], ecx
0x14000d0e7  sub     ecx, 1
0x14000d0ea  jg      short loc_14000D0FE
0x14000d0ec  mov     rcx, [rbx]
0x14000d0ef  mov     rax, [rcx]
0x14000d0f2  mov     rdx, rbx
0x14000d0f5  mov     rax, [rax+8]
0x14000d0f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d0fe  mov     rcx, rdi; this
0x14000d101  call    ?SaveSettings@StartList@@AEAAJXZ; StartList::SaveSettings(void)
0x14000d106  add     rsp, 28h
0x14000d10a  pop     r14
0x14000d10c  pop     rdi
0x14000d10d  pop     rbp
0x14000d10e  pop     rbx
0x14000d10f  retn
```
