# AccessibilityCplCore::SetupCaretWidth(void)

- ea: `0x180018878`
- end: `0x18001894c`
- name: `?SetupCaretWidth@AccessibilityCplCore@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(AccessibilityCplCore *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007a70`
- `0x1800198f4`

## callees

- `0x180004f78`
- `0x180018878`
- `0x180020d64`
- `0x180020edc`
- `0x18002d220`

## import_xrefs

- `msvcrt!_itow_s` at `0x1800188d9`
- `msvcrt!_itow_s` at `0x1800188d9`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x1800188b9`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x1800188b9`
- `DUI70!?SetSelection@Combobox@DirectUI@@QEAAJH@Z` at `0x180018926`
- `DUI70!?SetSelection@Combobox@DirectUI@@QEAAJH@Z` at `0x180018926`
- `DUI70!?AddString@Combobox@DirectUI@@QEAAHPEBG@Z` at `0x1800188e7`
- `DUI70!?AddString@Combobox@DirectUI@@QEAAHPEBG@Z` at `0x1800188e7`
- `DUI70!StrToID` at `0x18001889c`
- `DUI70!StrToID` at `0x18001889c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800188a8`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800188a8`

## pseudocode

```c
void __fastcall AccessibilityCplCore::SetupCaretWidth(AccessibilityCplCore *this)
{
  DirectUI::Element *v1; // rbx
  unsigned __int16 v2; // ax
  DirectUI::Element *Descendent; // rax
  DirectUI::Combobox *v4; // rdi
  unsigned int i; // ebx
  Accommodation *v6; // rax
  Accommodation *v7; // rbx
  unsigned int v8; // edx
  int v9; // [rsp+20h] [rbp-38h] BYREF
  wchar_t Buffer[12]; // [rsp+28h] [rbp-30h] BYREF

  v1 = (DirectUI::Element *)*((_QWORD *)this + 12);
  v2 = StrToID(L"caretwidth");
  Descendent = DirectUI::Element::FindDescendent(v1, v2);
  v4 = Descendent;
  if ( Descendent && DirectUI::Element::GetVisible(Descendent) )
  {
    for ( i = 1; i < 0x15; ++i )
    {
      _itow_s(i, Buffer, 0xCu, 10);
      DirectUI::Combobox::AddString(v4, Buffer);
    }
    v9 = 0;
    v6 = Accommodation::Open(L"caretwidth");
    v7 = v6;
    if ( v6 )
    {
      Accommodation::GetData(v6, &v9);
      DirectUI::Combobox::SetSelection(v4, v9 - 1);
      Accommodation::`scalar deleting destructor'(v7, v8);
    }
  }
}

```

## disassembly

```asm
0x180018878  mov     [rsp+arg_8], rbx
0x18001887d  push    rdi
0x18001887e  sub     rsp, 50h
0x180018882  mov     rax, cs:__security_cookie
0x180018889  xor     rax, rsp
0x18001888c  mov     [rsp+58h+var_18], rax
0x180018891  mov     rbx, [rcx+60h]
0x180018895  lea     rcx, aCaretwidth; "caretwidth"
0x18001889c  call    cs:__imp_StrToID
0x1800188a2  movzx   edx, ax
0x1800188a5  mov     rcx, rbx
0x1800188a8  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800188ae  mov     rdi, rax
0x1800188b1  test    rax, rax
0x1800188b4  jz      short loc_180018934
0x1800188b6  mov     rcx, rax
0x1800188b9  call    cs:__imp_?GetVisible@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetVisible(void)
0x1800188bf  test    al, al
0x1800188c1  jz      short loc_180018934
0x1800188c3  mov     ebx, 1
0x1800188c8  mov     r9d, 0Ah; Radix
0x1800188ce  lea     rdx, [rsp+58h+Buffer]; Buffer
0x1800188d3  mov     ecx, ebx; Value
0x1800188d5  lea     r8d, [r9+2]; BufferCount
0x1800188d9  call    cs:__imp__itow_s
0x1800188df  lea     rdx, [rsp+58h+Buffer]
0x1800188e4  mov     rcx, rdi
0x1800188e7  call    cs:__imp_?AddString@Combobox@DirectUI@@QEAAHPEBG@Z; DirectUI::Combobox::AddString(ushort const *)
0x1800188ed  inc     ebx
0x1800188ef  cmp     ebx, 15h
0x1800188f2  jb      short loc_1800188C8
0x1800188f4  lea     rcx, aCaretwidth; "caretwidth"
0x1800188fb  mov     [rsp+58h+var_38], 0
0x180018903  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x180018908  mov     rbx, rax
0x18001890b  test    rax, rax
0x18001890e  jz      short loc_180018934
0x180018910  lea     rdx, [rsp+58h+var_38]; void *
0x180018915  mov     rcx, rax; this
0x180018918  call    ?GetData@Accommodation@@QEAAXPEAX@Z; Accommodation::GetData(void *)
0x18001891d  mov     edx, [rsp+58h+var_38]
0x180018921  mov     rcx, rdi
0x180018924  dec     edx
0x180018926  call    cs:__imp_?SetSelection@Combobox@DirectUI@@QEAAJH@Z; DirectUI::Combobox::SetSelection(int)
0x18001892c  mov     rcx, rbx; this
0x18001892f  call    ??_GAccommodation@@QEAAPEAXI@Z; Accommodation::`scalar deleting destructor'(uint)
0x180018934  mov     rcx, [rsp+58h+var_18]
0x180018939  xor     rcx, rsp; StackCookie
0x18001893c  call    __security_check_cookie
0x180018941  mov     rbx, [rsp+58h+arg_8]
0x180018946  add     rsp, 50h
0x18001894a  pop     rdi
0x18001894b  retn
```
