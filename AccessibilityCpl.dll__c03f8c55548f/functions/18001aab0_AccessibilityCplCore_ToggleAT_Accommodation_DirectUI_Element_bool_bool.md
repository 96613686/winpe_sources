# AccessibilityCplCore::ToggleAT(Accommodation *,DirectUI::Element *,bool,bool)

- ea: `0x18001aab0`
- end: `0x18001abc4`
- name: `?ToggleAT@AccessibilityCplCore@@AEAAJPEAVAccommodation@@PEAVElement@DirectUI@@_N2@Z`
- size: `276`
- prototype: `__int64 __usercall@<rax>(AccessibilityCplCore *__hidden this@<rcx>, struct Accommodation *@<rdx>, struct DirectUI::Element *@<r8>, bool@<r9b>, bool)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180015dd0`
- `0x180016570`
- `0x180017360`

## callees

- `0x180005fec`
- `0x18001aab0`
- `0x180021610`
- `0x1800237e8`
- `0x1800241b0`
- `0x1800245c8`
- `0x18002d1fa`

## import_xrefs

- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x18001aad0`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x18001aad0`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x18001ab56`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x18001ab56`

## pseudocode

```c
__int64 __fastcall AccessibilityCplCore::ToggleAT(
        AccessibilityCplCore *this,
        const wchar_t **a2,
        struct DirectUI::Element *a3,
        char a4,
        bool a5)
{
  int v9; // ebx
  Start **v10; // rdi
  bool Selected; // bp
  int v12; // eax
  int v13; // eax

  v9 = 0;
  v10 = (Start **)((char *)this + 88);
  Selected = DirectUI::Element::GetSelected(a3);
  if ( Selected )
  {
    if ( !a4 || (v9 = StartList::Add(*v10, (struct Accommodation *)a2), v9 >= 0) )
    {
      if ( a5 )
      {
        v12 = (unsigned int)StartList::Start(*v10, a2, 0, 0, 0);
        v9 = v12;
        if ( v12 < 0 )
        {
          AccessibilityCplCore::ErrorMessage(this, 0x1784u, v12);
          if ( a4 )
            StartList::Remove(*v10, (struct Accommodation *)a2);
          DirectUI::Element::SetSelected(a3, !Selected);
        }
      }
    }
  }
  else if ( !a4 || (v9 = StartList::Remove(*v10, (struct Accommodation *)a2), v9 >= 0) )
  {
    if ( a5 && !wcscmp_0(a2[5], L"SystemSetting") )
    {
      v13 = StartList::Stop(*v10, a2);
      v9 = v13;
      if ( v13 < 0 )
        AccessibilityCplCore::ErrorMessage(this, 0x1785u, v13);
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001aab0  push    rbx
0x18001aab2  push    rbp
0x18001aab3  push    rsi
0x18001aab4  push    rdi
0x18001aab5  push    r12
0x18001aab7  push    r14
0x18001aab9  push    r15
0x18001aabb  sub     rsp, 30h
0x18001aabf  mov     r15, rcx
0x18001aac2  mov     r14b, r9b
0x18001aac5  mov     rcx, r8
0x18001aac8  mov     r12, r8
0x18001aacb  mov     rsi, rdx
0x18001aace  xor     ebx, ebx
0x18001aad0  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x18001aad6  lea     rdi, [r15+58h]
0x18001aada  mov     bpl, al
0x18001aadd  test    al, al
0x18001aadf  jz      short loc_18001AB5E
0x18001aae1  test    r14b, r14b
0x18001aae4  jz      short loc_18001AAFB
0x18001aae6  mov     rcx, [rdi]; this
0x18001aae9  mov     rdx, rsi; struct Accommodation *
0x18001aaec  call    ?Add@StartList@@QEAAJPEAVAccommodation@@@Z; StartList::Add(Accommodation *)
0x18001aaf1  mov     ebx, eax
0x18001aaf3  test    eax, eax
0x18001aaf5  js      loc_18001ABB3
0x18001aafb  cmp     [rsp+68h+arg_20], 0
0x18001ab03  jz      loc_18001ABB3
0x18001ab09  mov     rcx, [rdi]; this
0x18001ab0c  xor     r9d, r9d; int
0x18001ab0f  xor     r8d, r8d; void *
0x18001ab12  mov     [rsp+68h+var_48], 0; int
0x18001ab1a  mov     rdx, rsi; struct Accommodation *
0x18001ab1d  call    ?Start@StartList@@QEAAJPEAVAccommodation@@PEAXHH@Z; StartList::Start(Accommodation *,void *,int,int)
0x18001ab22  mov     ebx, eax
0x18001ab24  test    eax, eax
0x18001ab26  jns     loc_18001ABB3
0x18001ab2c  mov     r8d, eax; int
0x18001ab2f  mov     edx, 1784h; unsigned int
0x18001ab34  mov     rcx, r15; this
0x18001ab37  call    ?ErrorMessage@AccessibilityCplCore@@AEAAXIJ@Z; AccessibilityCplCore::ErrorMessage(uint,long)
0x18001ab3c  test    r14b, r14b
0x18001ab3f  jz      short loc_18001AB4C
0x18001ab41  mov     rcx, [rdi]; this
0x18001ab44  mov     rdx, rsi; struct Accommodation *
0x18001ab47  call    ?Remove@StartList@@QEAAJPEAVAccommodation@@@Z; StartList::Remove(Accommodation *)
0x18001ab4c  xor     bpl, 1
0x18001ab50  mov     rcx, r12
0x18001ab53  mov     dl, bpl
0x18001ab56  call    cs:__imp_?SetSelected@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetSelected(bool)
0x18001ab5c  jmp     short loc_18001ABB3
0x18001ab5e  test    r14b, r14b
0x18001ab61  jz      short loc_18001AB74
0x18001ab63  mov     rcx, [rdi]; this
0x18001ab66  mov     rdx, rsi; struct Accommodation *
0x18001ab69  call    ?Remove@StartList@@QEAAJPEAVAccommodation@@@Z; StartList::Remove(Accommodation *)
0x18001ab6e  mov     ebx, eax
0x18001ab70  test    eax, eax
0x18001ab72  js      short loc_18001ABB3
0x18001ab74  cmp     [rsp+68h+arg_20], 0
0x18001ab7c  jz      short loc_18001ABB3
0x18001ab7e  mov     rcx, [rsi+28h]; String1
0x18001ab82  lea     rdx, aSystemsetting; "SystemSetting"
0x18001ab89  call    wcscmp_0
0x18001ab8e  test    eax, eax
0x18001ab90  jnz     short loc_18001ABB3
0x18001ab92  mov     rcx, [rdi]; this
0x18001ab95  mov     rdx, rsi; struct Accommodation *
0x18001ab98  call    ?Stop@StartList@@QEAAJPEAVAccommodation@@@Z; StartList::Stop(Accommodation *)
0x18001ab9d  mov     ebx, eax
0x18001ab9f  test    eax, eax
0x18001aba1  jns     short loc_18001ABB3
0x18001aba3  mov     r8d, eax; int
0x18001aba6  mov     edx, 1785h; unsigned int
0x18001abab  mov     rcx, r15; this
0x18001abae  call    ?ErrorMessage@AccessibilityCplCore@@AEAAXIJ@Z; AccessibilityCplCore::ErrorMessage(uint,long)
0x18001abb3  mov     eax, ebx
0x18001abb5  add     rsp, 30h
0x18001abb9  pop     r15
0x18001abbb  pop     r14
0x18001abbd  pop     r12
0x18001abbf  pop     rdi
0x18001abc0  pop     rsi
0x18001abc1  pop     rbp
0x18001abc2  pop     rbx
0x18001abc3  retn
```
