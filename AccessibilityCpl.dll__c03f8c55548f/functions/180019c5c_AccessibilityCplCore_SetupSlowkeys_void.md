# AccessibilityCplCore::SetupSlowkeys(void)

- ea: `0x180019c5c`
- end: `0x180019e61`
- name: `?SetupSlowkeys@AccessibilityCplCore@@AEAAXXZ`
- size: `517`
- prototype: `void __fastcall(AccessibilityCplCore *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007a70`

## callees

- `0x180004f78`
- `0x1800052b0`
- `0x18000616c`
- `0x180019c5c`
- `0x180020d64`
- `0x180020edc`
- `0x18002d220`
- `0x18002e010`

## import_xrefs

- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x180019e32`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x180019e32`
- `DUI70!StrToID` at `0x180019ce9`
- `DUI70!StrToID` at `0x180019d09`
- `DUI70!StrToID` at `0x180019d29`
- `DUI70!StrToID` at `0x180019dd0`
- `DUI70!StrToID` at `0x180019e01`
- `DUI70!StrToID` at `0x180019ce9`
- `DUI70!StrToID` at `0x180019d09`
- `DUI70!StrToID` at `0x180019d29`
- `DUI70!StrToID` at `0x180019dd0`
- `DUI70!StrToID` at `0x180019e01`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019cf5`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019d15`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019d35`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019ddc`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019e0d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019cf5`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019d15`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019d35`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019ddc`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019e0d`

## pseudocode

```c
void __fastcall AccessibilityCplCore::SetupSlowkeys(AccessibilityCplCore *this)
{
  const wchar_t **v2; // rbx
  DirectUI::Element *v3; // rdi
  unsigned __int16 v4; // ax
  struct DirectUI::Element *Descendent; // rax
  DirectUI::Element *v6; // rdi
  struct DirectUI::Combobox *v7; // r15
  unsigned __int16 v8; // ax
  struct DirectUI::Element *v9; // rax
  DirectUI::Element *v10; // rdi
  struct DirectUI::Combobox *v11; // r14
  unsigned __int16 v12; // ax
  struct DirectUI::Element *v13; // rax
  struct DirectUI::Combobox *v14; // rdi
  AccessibilityCplCore *v15; // rcx
  AccessibilityCplCore *v16; // rcx
  DirectUI::Element *v17; // rdi
  unsigned __int16 v18; // ax
  struct DirectUI::Element *v19; // rax
  DirectUI::Element *v20; // rdi
  DirectUI::Element *v21; // rdi
  unsigned __int16 v22; // ax
  AccessibilityCplCore *v23[3]; // [rsp+30h] [rbp-28h] BYREF

  v2 = (const wchar_t **)Accommodation::Open(L"filterkeys");
  if ( v2 )
  {
    memset(v23, 0, sizeof(v23));
    Accommodation::GetData(v2, v23);
    Accommodation::GetData(v2, (_DWORD *)this + 51);
    if ( HIDWORD(v23[2]) )
    {
      v23[1] = *(AccessibilityCplCore **)((char *)this + 236);
      LODWORD(v23[2]) = *((_DWORD *)this + 61);
    }
    v3 = (DirectUI::Element *)*((_QWORD *)this + 12);
    v4 = StrToID(L"wait");
    Descendent = DirectUI::Element::FindDescendent(v3, v4);
    v6 = (DirectUI::Element *)*((_QWORD *)this + 12);
    v7 = Descendent;
    v8 = StrToID(L"delay");
    v9 = DirectUI::Element::FindDescendent(v6, v8);
    v10 = (DirectUI::Element *)*((_QWORD *)this + 12);
    v11 = v9;
    v12 = StrToID(L"repeat");
    v13 = DirectUI::Element::FindDescendent(v10, v12);
    v14 = v13;
    if ( v7 && v11 )
    {
      if ( v13 )
      {
        AccessibilityCplCore::FillAndSetCombo(
          (AccessibilityCplCore *)LODWORD(v23[1]),
          v7,
          &qword_180033830,
          0xAu,
          (unsigned int)v23[1],
          1);
        AccessibilityCplCore::FillAndSetCombo(v15, v11, &qword_1800338A0, 6u, HIDWORD(v23[1]), 1);
        AccessibilityCplCore::FillAndSetCombo(v16, v14, &qword_180033880, 6u, (unsigned int)v23[2], 1);
      }
    }
    if ( *(AccessibilityCplCore **)((char *)&v23[1] + 4) )
    {
      v21 = (DirectUI::Element *)*((_QWORD *)this + 12);
      v22 = StrToID(L"keyboardrepeat");
      v19 = DirectUI::Element::FindDescendent(v21, v22);
      v20 = v19;
      if ( v19 )
      {
LABEL_12:
        (*(void (__fastcall **)(DirectUI::Element *))(*(_QWORD *)v19 + 168LL))(v20);
        DirectUI::Element::SetSelected(v20, 1);
      }
    }
    else
    {
      v17 = (DirectUI::Element *)*((_QWORD *)this + 12);
      v18 = StrToID(L"nokeyboardrepeat");
      v19 = DirectUI::Element::FindDescendent(v17, v18);
      v20 = v19;
      if ( v19 )
        goto LABEL_12;
    }
    AccessibilityCplCore::AddA11yNameToFilterKeysTestElement(this);
    Accommodation::`scalar deleting destructor'((Accommodation *)v2);
  }
}

```

## disassembly

```asm
0x180019c5c  push    rbp
0x180019c5e  push    rbx
0x180019c5f  push    rsi
0x180019c60  push    rdi
0x180019c61  push    r14
0x180019c63  push    r15
0x180019c65  mov     rbp, rsp
0x180019c68  sub     rsp, 58h
0x180019c6c  mov     rax, cs:__security_cookie
0x180019c73  xor     rax, rsp
0x180019c76  mov     [rbp+var_10], rax
0x180019c7a  mov     rsi, rcx
0x180019c7d  lea     rcx, aFilterkeys; "filterkeys"
0x180019c84  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x180019c89  mov     rbx, rax
0x180019c8c  test    rax, rax
0x180019c8f  jz      loc_180019E48
0x180019c95  xorps   xmm0, xmm0
0x180019c98  lea     rdx, [rbp+var_28]; void *
0x180019c9c  xor     eax, eax
0x180019c9e  mov     rcx, rbx; this
0x180019ca1  movups  xmmword ptr [rbp+var_28], xmm0
0x180019ca5  mov     qword ptr [rbp+var_18], rax
0x180019ca9  call    ?GetData@Accommodation@@QEAAXPEAX@Z; Accommodation::GetData(void *)
0x180019cae  lea     rdx, [rsi+0CCh]; void *
0x180019cb5  mov     rcx, rbx; this
0x180019cb8  call    ?GetData@Accommodation@@QEAAXPEAX@Z; Accommodation::GetData(void *)
0x180019cbd  cmp     [rbp+var_18+4], 0
0x180019cc1  jz      short loc_180019CDE
0x180019cc3  mov     eax, [rsi+0ECh]
0x180019cc9  mov     dword ptr [rbp+var_28+8], eax
0x180019ccc  mov     eax, [rsi+0F0h]
0x180019cd2  mov     dword ptr [rbp+var_28+0Ch], eax
0x180019cd5  mov     eax, [rsi+0F4h]
0x180019cdb  mov     [rbp+var_18], eax
0x180019cde  mov     rdi, [rsi+60h]
0x180019ce2  lea     rcx, aWait_0; "wait"
0x180019ce9  call    cs:__imp_StrToID
0x180019cef  movzx   edx, ax
0x180019cf2  mov     rcx, rdi
0x180019cf5  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180019cfb  mov     rdi, [rsi+60h]
0x180019cff  lea     rcx, aDelay; "delay"
0x180019d06  mov     r15, rax
0x180019d09  call    cs:__imp_StrToID
0x180019d0f  movzx   edx, ax
0x180019d12  mov     rcx, rdi
0x180019d15  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180019d1b  mov     rdi, [rsi+60h]
0x180019d1f  lea     rcx, aRepeat; "repeat"
0x180019d26  mov     r14, rax
0x180019d29  call    cs:__imp_StrToID
0x180019d2f  movzx   edx, ax
0x180019d32  mov     rcx, rdi
0x180019d35  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180019d3b  mov     rdi, rax
0x180019d3e  test    r15, r15
0x180019d41  jz      short loc_180019DB9
0x180019d43  test    r14, r14
0x180019d46  jz      short loc_180019DB9
0x180019d48  test    rax, rax
0x180019d4b  jz      short loc_180019DB9
0x180019d4d  mov     ecx, dword ptr [rbp+var_28+8]; this
0x180019d50  lea     r8, qword_180033830; unsigned int *
0x180019d57  mov     [rsp+58h+var_30], 1; int
0x180019d5f  mov     r9d, 0Ah; unsigned int
0x180019d65  mov     rdx, r15; struct DirectUI::Combobox *
0x180019d68  mov     [rsp+58h+var_38], ecx; unsigned int
0x180019d6c  call    ?FillAndSetCombo@AccessibilityCplCore@@AEAAXPEAVCombobox@DirectUI@@PEBIIIH@Z; AccessibilityCplCore::FillAndSetCombo(DirectUI::Combobox *,uint const *,uint,uint,int)
0x180019d71  mov     eax, dword ptr [rbp+var_28+0Ch]
0x180019d74  lea     r8, qword_1800338A0; unsigned int *
0x180019d7b  mov     r15d, 6
0x180019d81  mov     [rsp+58h+var_30], 1; int
0x180019d89  mov     r9d, r15d; unsigned int
0x180019d8c  mov     [rsp+58h+var_38], eax; unsigned int
0x180019d90  mov     rdx, r14; struct DirectUI::Combobox *
0x180019d93  call    ?FillAndSetCombo@AccessibilityCplCore@@AEAAXPEAVCombobox@DirectUI@@PEBIIIH@Z; AccessibilityCplCore::FillAndSetCombo(DirectUI::Combobox *,uint const *,uint,uint,int)
0x180019d98  mov     eax, [rbp+var_18]
0x180019d9b  lea     r8, qword_180033880; unsigned int *
0x180019da2  mov     r9d, r15d; unsigned int
0x180019da5  mov     [rsp+58h+var_30], 1; int
0x180019dad  mov     rdx, rdi; struct DirectUI::Combobox *
0x180019db0  mov     [rsp+58h+var_38], eax; unsigned int
0x180019db4  call    ?FillAndSetCombo@AccessibilityCplCore@@AEAAXPEAVCombobox@DirectUI@@PEBIIIH@Z; AccessibilityCplCore::FillAndSetCombo(DirectUI::Combobox *,uint const *,uint,uint,int)
0x180019db9  cmp     dword ptr [rbp+var_28+0Ch], 0
0x180019dbd  jnz     short loc_180019DF6
0x180019dbf  cmp     [rbp+var_18], 0
0x180019dc3  jnz     short loc_180019DF6
0x180019dc5  mov     rdi, [rsi+60h]
0x180019dc9  lea     rcx, aNokeyboardrepe; "nokeyboardrepeat"
0x180019dd0  call    cs:__imp_StrToID
0x180019dd6  movzx   edx, ax
0x180019dd9  mov     rcx, rdi
0x180019ddc  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180019de2  mov     rdi, rax
0x180019de5  test    rax, rax
0x180019de8  jz      short loc_180019E38
0x180019dea  mov     rcx, [rax]
0x180019ded  mov     rax, [rcx+0A8h]
0x180019df4  jmp     short loc_180019E25
0x180019df6  mov     rdi, [rsi+60h]
0x180019dfa  lea     rcx, aKeyboardrepeat; "keyboardrepeat"
0x180019e01  call    cs:__imp_StrToID
0x180019e07  movzx   edx, ax
0x180019e0a  mov     rcx, rdi
0x180019e0d  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180019e13  mov     rdi, rax
0x180019e16  test    rax, rax
0x180019e19  jz      short loc_180019E38
0x180019e1b  mov     rdx, [rax]
0x180019e1e  mov     rax, [rdx+0A8h]
0x180019e25  mov     rcx, rdi
0x180019e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e2d  mov     dl, 1
0x180019e2f  mov     rcx, rdi
0x180019e32  call    cs:__imp_?SetSelected@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetSelected(bool)
0x180019e38  mov     rcx, rsi; this
0x180019e3b  call    ?AddA11yNameToFilterKeysTestElement@AccessibilityCplCore@@AEAAXXZ; AccessibilityCplCore::AddA11yNameToFilterKeysTestElement(void)
0x180019e40  mov     rcx, rbx; this
0x180019e43  call    ??_GAccommodation@@QEAAPEAXI@Z; Accommodation::`scalar deleting destructor'(uint)
0x180019e48  mov     rcx, [rbp+var_10]
0x180019e4c  xor     rcx, rsp; StackCookie
0x180019e4f  call    __security_check_cookie
0x180019e54  add     rsp, 58h
0x180019e58  pop     r15
0x180019e5a  pop     r14
0x180019e5c  pop     rdi
0x180019e5d  pop     rsi
0x180019e5e  pop     rbx
0x180019e5f  pop     rbp
0x180019e60  retn
```
