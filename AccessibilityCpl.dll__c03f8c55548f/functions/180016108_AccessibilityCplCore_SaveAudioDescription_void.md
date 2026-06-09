# AccessibilityCplCore::SaveAudioDescription(void)

- ea: `0x180016108`
- end: `0x1800161ea`
- name: `?SaveAudioDescription@AccessibilityCplCore@@AEAAJXZ`
- size: `226`
- prototype: `__int64 __fastcall(AccessibilityCplCore *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800134a0`

## callees

- `0x180004f78`
- `0x180016108`
- `0x18001af04`
- `0x180020edc`
- `0x1800241b0`
- `0x18002d220`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1800161a6`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1800161a6`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x180016151`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x180016151`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x18001615e`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180016195`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x18001615e`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180016195`
- `DUI70!StrToID` at `0x180016130`
- `DUI70!StrToID` at `0x180016130`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001613c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001613c`

## pseudocode

```c
__int64 __fastcall AccessibilityCplCore::SaveAudioDescription(AccessibilityCplCore *this)
{
  DirectUI::Element *v1; // rbx
  unsigned int v3; // esi
  unsigned __int16 v4; // ax
  DirectUI::Element *Descendent; // rax
  DirectUI::Element *v6; // rdi
  const wchar_t **v7; // rbx
  LCID UserDefaultLCID; // eax
  Start *v9; // rcx
  UINT v11[2]; // [rsp+30h] [rbp-48h] BYREF
  LCID v12; // [rsp+38h] [rbp-40h]

  v1 = (DirectUI::Element *)*((_QWORD *)this + 12);
  v3 = 0;
  v4 = StrToID(L"audiodescription");
  Descendent = DirectUI::Element::FindDescendent(v1, v4);
  v6 = Descendent;
  if ( Descendent )
  {
    if ( DirectUI::Element::GetVisible(Descendent) )
    {
      DirectUI::Element::GetSelected(v6);
      AccessibilityCplCore::VisitBOOLSetting(this);
      v7 = (const wchar_t **)Accommodation::Open(L"audiodescription");
      if ( v7 )
      {
        v11[0] = 0;
        v12 = 0;
        v11[1] = DirectUI::Element::GetSelected(v6);
        UserDefaultLCID = GetUserDefaultLCID();
        v9 = (Start *)*((_QWORD *)this + 11);
        v12 = UserDefaultLCID;
        v3 = (unsigned int)StartList::Start(v9, v7, v11, 0, 0);
        Accommodation::`scalar deleting destructor'((Accommodation *)v7);
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180016108  push    rbx
0x18001610a  push    rbp
0x18001610b  push    rsi
0x18001610c  push    rdi
0x18001610d  sub     rsp, 58h
0x180016111  mov     rax, cs:__security_cookie
0x180016118  xor     rax, rsp
0x18001611b  mov     [rsp+78h+var_38], rax
0x180016120  mov     rbx, [rcx+60h]
0x180016124  mov     rbp, rcx
0x180016127  lea     rcx, aAudiodescripti; "audiodescription"
0x18001612e  xor     esi, esi
0x180016130  call    cs:__imp_StrToID
0x180016136  movzx   edx, ax
0x180016139  mov     rcx, rbx
0x18001613c  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180016142  mov     rdi, rax
0x180016145  test    rax, rax
0x180016148  jz      loc_1800161D2
0x18001614e  mov     rcx, rax
0x180016151  call    cs:__imp_?GetVisible@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetVisible(void)
0x180016157  test    al, al
0x180016159  jz      short loc_1800161D2
0x18001615b  mov     rcx, rdi
0x18001615e  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x180016164  movzx   r8d, al; int
0x180016168  lea     edx, [rsi+5]; unsigned int
0x18001616b  mov     rcx, rbp; this
0x18001616e  call    ?VisitBOOLSetting@AccessibilityCplCore@@AEAAXKH@Z; AccessibilityCplCore::VisitBOOLSetting(ulong,int)
0x180016173  lea     rcx, aAudiodescripti; "audiodescription"
0x18001617a  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x18001617f  mov     rbx, rax
0x180016182  test    rax, rax
0x180016185  jz      short loc_1800161D2
0x180016187  xor     eax, eax
0x180016189  mov     rcx, rdi
0x18001618c  mov     [rsp+78h+var_48], rax
0x180016191  mov     [rsp+78h+var_40], eax
0x180016195  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x18001619b  xor     edx, edx
0x18001619d  test    al, al
0x18001619f  setnz   dl
0x1800161a2  mov     dword ptr [rsp+78h+var_48+4], edx
0x1800161a6  call    cs:__imp_GetUserDefaultLCID
0x1800161ac  mov     rcx, [rbp+58h]; this
0x1800161b0  lea     r8, [rsp+78h+var_48]; void *
0x1800161b5  xor     r9d, r9d; int
0x1800161b8  mov     [rsp+78h+var_40], eax
0x1800161bc  mov     rdx, rbx; struct Accommodation *
0x1800161bf  mov     [rsp+78h+var_58], esi; int
0x1800161c3  call    ?Start@StartList@@QEAAJPEAVAccommodation@@PEAXHH@Z; StartList::Start(Accommodation *,void *,int,int)
0x1800161c8  mov     rcx, rbx; this
0x1800161cb  mov     esi, eax
0x1800161cd  call    ??_GAccommodation@@QEAAPEAXI@Z; Accommodation::`scalar deleting destructor'(uint)
0x1800161d2  mov     eax, esi
0x1800161d4  mov     rcx, [rsp+78h+var_38]
0x1800161d9  xor     rcx, rsp; StackCookie
0x1800161dc  call    __security_check_cookie
0x1800161e1  add     rsp, 58h
0x1800161e5  pop     rdi
0x1800161e6  pop     rsi
0x1800161e7  pop     rbp
0x1800161e8  pop     rbx
0x1800161e9  retn
```
