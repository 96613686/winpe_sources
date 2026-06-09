# DuiVoice::OnListenedEvent(DirectUI::Element *,DirectUI::Event *)

- ea: `0x180029c40`
- end: `0x180029d17`
- name: `?OnListenedEvent@DuiVoice@@UEAAXPEAVElement@DirectUI@@PEAUEvent@3@@Z`
- size: `215`
- prototype: `void __fastcall(DuiVoice *__hidden this, struct DirectUI::Element *, struct DirectUI::Event *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004e1c`
- `0x180029930`
- `0x180029c40`
- `0x180029e88`
- `0x18002e010`

## import_xrefs

- `DUI70!?GetClassInfoPtr@TouchSwitch@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x180029ca7`
- `DUI70!?GetClassInfoPtr@TouchSwitch@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x180029ca7`
- `DUI70!?GetOnText@TouchSwitch@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x180029ce0`
- `DUI70!?GetOnText@TouchSwitch@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x180029ce0`
- `DUI70!?GetOffText@TouchSwitch@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x180029ce8`
- `DUI70!?GetOffText@TouchSwitch@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x180029ce8`
- `DUI70!?GetToggleValue@TouchSwitch@DirectUI@@QEAAHXZ` at `0x180029ccd`
- `DUI70!?GetToggleValue@TouchSwitch@DirectUI@@QEAAHXZ` at `0x180029ccd`
- `DUI70!?SliderUpdated@TouchSlider@DirectUI@@SA?AVUID@@XZ` at `0x180029c64`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DuiVoice::OnListenedEvent(DuiVoice *this, struct DirectUI::Element *a2, struct DirectUI::Event *a3)
{
  DirectUI::TouchSwitch *v5; // rsi
  __int64 v6; // rdi
  unsigned __int8 (__fastcall *v7)(__int64, __int64); // rbx
  __int64 ClassInfoPtr; // rax
  const unsigned __int16 *OffText; // rax
  struct DirectUI::Value *v10; // [rsp+40h] [rbp+8h] BYREF

  if ( *((_QWORD *)this + 2) )
  {
    v10 = (struct DirectUI::Value *)DirectUI::TouchSlider::SliderUpdated;
    if ( (unsigned __int8)operator==((char *)a3 + 8, &v10) )
    {
      v5 = 0;
      if ( a2 )
      {
        v6 = (*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)a2 + 280LL))(a2);
        v7 = *(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 80LL);
        ClassInfoPtr = DirectUI::TouchSwitch::GetClassInfoPtr();
        if ( v7(v6, ClassInfoPtr) )
          v5 = a2;
      }
      v10 = 0;
      if ( DirectUI::TouchSwitch::GetToggleValue(v5) == 1 )
        OffText = DirectUI::TouchSwitch::GetOnText(v5, &v10);
      else
        OffText = DirectUI::TouchSwitch::GetOffText(v5, &v10);
      DuiVoice::SafeSpeak(this, OffText);
      ATL::CComPtrBase<DirectUI::Value>::~CComPtrBase<DirectUI::Value>(&v10);
    }
  }
}

```

## disassembly

```asm
0x180029c40  mov     r11, rsp
0x180029c43  mov     [r11+10h], rbx
0x180029c47  mov     [r11+18h], rbp
0x180029c4b  push    rsi
0x180029c4c  push    rdi
0x180029c4d  push    r14
0x180029c4f  sub     rsp, 20h
0x180029c53  mov     r14, rdx
0x180029c56  mov     rbp, rcx
0x180029c59  cmp     qword ptr [rcx+10h], 0
0x180029c5e  jz      loc_180029D04
0x180029c64  mov     rax, cs:__imp_?SliderUpdated@TouchSlider@DirectUI@@SA?AVUID@@XZ; DirectUI::TouchSlider::SliderUpdated(void)
0x180029c6b  mov     [r11+8], rax
0x180029c6f  lea     rcx, [r8+8]
0x180029c73  lea     rdx, [r11+8]
0x180029c77  call    ??8@YA_NAEBVUID@@AEBQ6A?AV0@XZ@Z; operator==(UID const &,UID (*const &)(void))
0x180029c7c  test    al, al
0x180029c7e  jz      loc_180029D04
0x180029c84  xor     esi, esi
0x180029c86  test    r14, r14
0x180029c89  jz      short loc_180029CC1
0x180029c8b  mov     rax, [r14]
0x180029c8e  mov     rcx, r14
0x180029c91  mov     rax, [rax+118h]
0x180029c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c9d  mov     rdi, rax
0x180029ca0  mov     rcx, [rax]
0x180029ca3  mov     rbx, [rcx+50h]
0x180029ca7  call    cs:__imp_?GetClassInfoPtr@TouchSwitch@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::TouchSwitch::GetClassInfoPtr(void)
0x180029cad  mov     rdx, rax
0x180029cb0  mov     rcx, rdi
0x180029cb3  mov     rax, rbx
0x180029cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029cbb  test    al, al
0x180029cbd  cmovnz  rsi, r14
0x180029cc1  mov     [rsp+38h+arg_0], 0
0x180029cca  mov     rcx, rsi
0x180029ccd  call    cs:__imp_?GetToggleValue@TouchSwitch@DirectUI@@QEAAHXZ; DirectUI::TouchSwitch::GetToggleValue(void)
0x180029cd3  lea     rdx, [rsp+38h+arg_0]
0x180029cd8  mov     rcx, rsi
0x180029cdb  cmp     eax, 1
0x180029cde  jnz     short loc_180029CE8
0x180029ce0  call    cs:__imp_?GetOnText@TouchSwitch@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z; DirectUI::TouchSwitch::GetOnText(DirectUI::Value * *)
0x180029ce6  jmp     short loc_180029CEE
0x180029ce8  call    cs:__imp_?GetOffText@TouchSwitch@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z; DirectUI::TouchSwitch::GetOffText(DirectUI::Value * *)
0x180029cee  mov     rdx, rax; unsigned __int16 *
0x180029cf1  mov     rcx, rbp; this
0x180029cf4  call    ?SafeSpeak@DuiVoice@@AEAAXPEBG@Z; DuiVoice::SafeSpeak(ushort const *)
0x180029cf9  nop
0x180029cfa  lea     rcx, [rsp+38h+arg_0]
0x180029cff  call    ??1?$CComPtrBase@VValue@DirectUI@@@ATL@@QEAA@XZ; ATL::CComPtrBase<DirectUI::Value>::~CComPtrBase<DirectUI::Value>(void)
0x180029d04  mov     rbx, [rsp+38h+arg_8]
0x180029d09  mov     rbp, [rsp+38h+arg_10]
0x180029d0e  add     rsp, 20h
0x180029d12  pop     r14
0x180029d14  pop     rdi
0x180029d15  pop     rsi
0x180029d16  retn
```
