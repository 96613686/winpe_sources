# AccessibilityCplCore::SaveToggleKeys(void)

- ea: `0x180017670`
- end: `0x1800177c8`
- name: `?SaveToggleKeys@AccessibilityCplCore@@AEAAJXZ`
- size: `344`
- prototype: `__int64 __fastcall(AccessibilityCplCore *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800134a0`

## callees

- `0x180004f78`
- `0x180017670`
- `0x18001af04`
- `0x180020d64`
- `0x180020edc`
- `0x180021610`
- `0x1800237e8`
- `0x1800241b0`

## import_xrefs

- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x1800176d3`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x1800176d3`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800176ed`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180017705`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180017747`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180017777`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800176ed`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180017705`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180017747`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180017777`
- `DUI70!StrToID` at `0x180017692`
- `DUI70!StrToID` at `0x1800176b2`
- `DUI70!StrToID` at `0x180017692`
- `DUI70!StrToID` at `0x1800176b2`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001769e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800176be`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001769e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800176be`

## pseudocode

```c
__int64 __fastcall AccessibilityCplCore::SaveToggleKeys(AccessibilityCplCore *this)
{
  DirectUI::Element *v1; // rbx
  unsigned int v3; // edi
  unsigned __int16 v4; // ax
  struct DirectUI::Element *Descendent; // rax
  DirectUI::Element *v6; // rbx
  DirectUI::Element *v7; // rbp
  unsigned __int16 v8; // ax
  DirectUI::Element *v9; // r14
  const wchar_t **v10; // rax
  struct Accommodation *v11; // rbx
  bool Selected; // al
  StartList *v13; // rcx
  int v14; // eax
  __int64 v16; // [rsp+50h] [rbp+8h] BYREF

  v1 = (DirectUI::Element *)*((_QWORD *)this + 12);
  v3 = 0;
  v4 = StrToID(L"togglekeys");
  Descendent = DirectUI::Element::FindDescendent(v1, v4);
  v6 = (DirectUI::Element *)*((_QWORD *)this + 12);
  v7 = Descendent;
  v8 = StrToID(L"togglekeysShortcut");
  v9 = DirectUI::Element::FindDescendent(v6, v8);
  if ( v7 )
  {
    if ( DirectUI::Element::GetVisible(v7) )
    {
      if ( v9 )
      {
        DirectUI::Element::GetSelected(v7);
        AccessibilityCplCore::VisitBOOLSetting(this);
        DirectUI::Element::GetSelected(v9);
        AccessibilityCplCore::VisitBOOLSetting(this);
        v10 = (const wchar_t **)Accommodation::Open(L"togglekeys");
        v11 = (struct Accommodation *)v10;
        if ( v10 )
        {
          v16 = 0;
          Accommodation::GetData(v10, &v16);
          Selected = DirectUI::Element::GetSelected(v7);
          v13 = (StartList *)*((_QWORD *)this + 11);
          if ( Selected )
          {
            HIDWORD(v16) |= 1u;
            v14 = StartList::Add(v13, v11);
          }
          else
          {
            HIDWORD(v16) &= ~1u;
            v14 = StartList::Remove(v13, v11);
          }
          v3 = v14;
          if ( v14 >= 0 )
          {
            if ( DirectUI::Element::GetSelected(v9) )
              HIDWORD(v16) |= 4u;
            else
              HIDWORD(v16) &= ~4u;
            v3 = (unsigned int)StartList::Start(*((Start **)this + 11), (const wchar_t **)v11, (UINT *)&v16, 0, 0);
          }
          Accommodation::`scalar deleting destructor'(v11);
        }
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180017670  mov     [rsp+arg_8], rbx
0x180017675  mov     [rsp+arg_10], rbp
0x18001767a  push    rsi
0x18001767b  push    rdi
0x18001767c  push    r14
0x18001767e  sub     rsp, 30h
0x180017682  mov     rbx, [rcx+60h]
0x180017686  mov     rsi, rcx
0x180017689  lea     rcx, aTogglekeys; "togglekeys"
0x180017690  xor     edi, edi
0x180017692  call    cs:__imp_StrToID
0x180017698  movzx   edx, ax
0x18001769b  mov     rcx, rbx
0x18001769e  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800176a4  mov     rbx, [rsi+60h]
0x1800176a8  lea     rcx, aTogglekeysshor; "togglekeysShortcut"
0x1800176af  mov     rbp, rax
0x1800176b2  call    cs:__imp_StrToID
0x1800176b8  movzx   edx, ax
0x1800176bb  mov     rcx, rbx
0x1800176be  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800176c4  mov     r14, rax
0x1800176c7  test    rbp, rbp
0x1800176ca  jz      loc_1800177B3
0x1800176d0  mov     rcx, rbp
0x1800176d3  call    cs:__imp_?GetVisible@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetVisible(void)
0x1800176d9  test    al, al
0x1800176db  jz      loc_1800177B3
0x1800176e1  test    r14, r14
0x1800176e4  jz      loc_1800177B3
0x1800176ea  mov     rcx, rbp
0x1800176ed  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x1800176f3  movzx   r8d, al; int
0x1800176f7  lea     edx, [rdi+6]; unsigned int
0x1800176fa  mov     rcx, rsi; this
0x1800176fd  call    ?VisitBOOLSetting@AccessibilityCplCore@@AEAAXKH@Z; AccessibilityCplCore::VisitBOOLSetting(ulong,int)
0x180017702  mov     rcx, r14
0x180017705  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x18001770b  movzx   r8d, al; int
0x18001770f  lea     edx, [rdi+7]; unsigned int
0x180017712  mov     rcx, rsi; this
0x180017715  call    ?VisitBOOLSetting@AccessibilityCplCore@@AEAAXKH@Z; AccessibilityCplCore::VisitBOOLSetting(ulong,int)
0x18001771a  lea     rcx, aTogglekeys; "togglekeys"
0x180017721  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x180017726  mov     rbx, rax
0x180017729  test    rax, rax
0x18001772c  jz      loc_1800177B3
0x180017732  lea     rdx, [rsp+48h+arg_0]; void *
0x180017737  mov     [rsp+48h+arg_0], rdi
0x18001773c  mov     rcx, rax; this
0x18001773f  call    ?GetData@Accommodation@@QEAAXPEAX@Z; Accommodation::GetData(void *)
0x180017744  mov     rcx, rbp
0x180017747  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x18001774d  mov     rcx, [rsi+58h]; this
0x180017751  mov     rdx, rbx; struct Accommodation *
0x180017754  test    al, al
0x180017756  jz      short loc_180017764
0x180017758  or      dword ptr [rsp+48h+arg_0+4], 1
0x18001775d  call    ?Add@StartList@@QEAAJPEAVAccommodation@@@Z; StartList::Add(Accommodation *)
0x180017762  jmp     short loc_18001776E
0x180017764  and     dword ptr [rsp+48h+arg_0+4], 0FFFFFFFEh
0x180017769  call    ?Remove@StartList@@QEAAJPEAVAccommodation@@@Z; StartList::Remove(Accommodation *)
0x18001776e  mov     edi, eax
0x180017770  test    eax, eax
0x180017772  js      short loc_1800177AB
0x180017774  mov     rcx, r14
0x180017777  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x18001777d  test    al, al
0x18001777f  jz      short loc_180017788
0x180017781  or      dword ptr [rsp+48h+arg_0+4], 4
0x180017786  jmp     short loc_18001778D
0x180017788  and     dword ptr [rsp+48h+arg_0+4], 0FFFFFFFBh
0x18001778d  mov     rcx, [rsi+58h]; this
0x180017791  lea     r8, [rsp+48h+arg_0]; void *
0x180017796  xor     r9d, r9d; int
0x180017799  mov     [rsp+48h+var_28], 0; int
0x1800177a1  mov     rdx, rbx; struct Accommodation *
0x1800177a4  call    ?Start@StartList@@QEAAJPEAVAccommodation@@PEAXHH@Z; StartList::Start(Accommodation *,void *,int,int)
0x1800177a9  mov     edi, eax
0x1800177ab  mov     rcx, rbx; this
0x1800177ae  call    ??_GAccommodation@@QEAAPEAXI@Z; Accommodation::`scalar deleting destructor'(uint)
0x1800177b3  mov     rbx, [rsp+48h+arg_8]
0x1800177b8  mov     eax, edi
0x1800177ba  mov     rbp, [rsp+48h+arg_10]
0x1800177bf  add     rsp, 30h
0x1800177c3  pop     r14
0x1800177c5  pop     rdi
0x1800177c6  pop     rsi
0x1800177c7  retn
```
