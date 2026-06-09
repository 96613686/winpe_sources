# AccessibilityCplCore::SetupTouch(void)

- ea: `0x18001a210`
- end: `0x18001a339`
- name: `?SetupTouch@AccessibilityCplCore@@AEAAXXZ`
- size: `297`
- prototype: `void __fastcall(AccessibilityCplCore *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180007a70`

## callees

- `0x1800043d4`
- `0x180012a88`
- `0x180015780`
- `0x18001a210`
- `0x1800256a0`
- `0x18002d1ee`
- `0x18002d220`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a2ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a2ef`
- `DUI70!?SetSelection@Combobox@DirectUI@@QEAAJH@Z` at `0x18001a306`
- `DUI70!?SetSelection@Combobox@DirectUI@@QEAAJH@Z` at `0x18001a306`
- `DUI70!?AddString@Combobox@DirectUI@@QEAAHPEBG@Z` at `0x18001a290`
- `DUI70!?AddString@Combobox@DirectUI@@QEAAHPEBG@Z` at `0x18001a2e6`
- `DUI70!?AddString@Combobox@DirectUI@@QEAAHPEBG@Z` at `0x18001a290`
- `DUI70!?AddString@Combobox@DirectUI@@QEAAHPEBG@Z` at `0x18001a2e6`
- `DUI70!StrToID` at `0x18001a26c`
- `DUI70!StrToID` at `0x18001a26c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001a278`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001a278`

## string_xrefs

- `0x18001a265`: `slatelaunchcombobox`

## pseudocode

```c
void __fastcall AccessibilityCplCore::SetupTouch(AccessibilityCplCore *this)
{
  int StringW; // eax
  const unsigned __int16 *v3; // rbx
  DirectUI::Element *v4; // rdi
  unsigned __int16 v5; // ax
  DirectUI::Combobox *Descendent; // rax
  DirectUI::Combobox *v7; // r14
  int v8; // ecx
  int i; // esi
  unsigned __int16 *v10; // rdi
  int v11; // [rsp+20h] [rbp-E0h] BYREF
  int v12[2]; // [rsp+28h] [rbp-D8h] BYREF
  LPVOID pv[32]; // [rsp+30h] [rbp-D0h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v12);
  StringW = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
              v12,
              87);
  v3 = *(const unsigned __int16 **)v12;
  if ( StringW )
  {
    v4 = (DirectUI::Element *)*((_QWORD *)this + 12);
    v5 = StrToID(L"slatelaunchcombobox");
    Descendent = DirectUI::Element::FindDescendent(v4, v5);
    v7 = Descendent;
    if ( Descendent )
    {
      DirectUI::Combobox::AddString(Descendent, v3);
      memset_0(pv, 0, sizeof(pv));
      v11 = 0;
      v12[0] = 0;
      if ( (int)GetSlateATList(v8, (unsigned __int16 **)pv, &v11, v12) >= 0 )
      {
        for ( i = 0; i < v11; ++i )
        {
          v10 = (unsigned __int16 *)pv[i];
          DirectUI::Combobox::AddString(v7, v10);
          CoTaskMemFree(v10);
        }
      }
      DirectUI::Combobox::SetSelection(v7, v12[0] + 1);
    }
  }
  ATL::CStringData::Release((ATL::CStringData *)(v3 - 12));
}

```

## disassembly

```asm
0x18001a210  mov     [rsp-8+arg_8], rbx
0x18001a215  mov     [rsp-8+arg_10], rsi
0x18001a21a  push    rbp
0x18001a21b  push    rdi
0x18001a21c  push    r14
0x18001a21e  lea     rbp, [rsp-40h]
0x18001a223  sub     rsp, 140h
0x18001a22a  mov     rax, cs:__security_cookie
0x18001a231  xor     rax, rsp
0x18001a234  mov     [rbp+50h+var_20], rax
0x18001a238  mov     rdi, rcx
0x18001a23b  lea     rcx, [rsp+150h+var_128]
0x18001a240  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001a245  mov     edx, 57h ; 'W'
0x18001a24a  lea     rcx, [rsp+150h+var_128]
0x18001a24f  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHI@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(uint)
0x18001a254  mov     rbx, qword ptr [rsp+150h+var_128]
0x18001a259  test    eax, eax
0x18001a25b  jz      loc_18001A30C
0x18001a261  mov     rdi, [rdi+60h]
0x18001a265  lea     rcx, aSlatelaunchcom; "slatelaunchcombobox"
0x18001a26c  call    cs:__imp_StrToID
0x18001a272  movzx   edx, ax
0x18001a275  mov     rcx, rdi
0x18001a278  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001a27e  mov     r14, rax
0x18001a281  test    rax, rax
0x18001a284  jz      loc_18001A30C
0x18001a28a  mov     rdx, rbx
0x18001a28d  mov     rcx, rax
0x18001a290  call    cs:__imp_?AddString@Combobox@DirectUI@@QEAAHPEBG@Z; DirectUI::Combobox::AddString(ushort const *)
0x18001a296  xor     edx, edx; Val
0x18001a298  lea     rcx, [rsp+150h+pv]; void *
0x18001a29d  mov     r8d, 100h; Size
0x18001a2a3  call    memset_0
0x18001a2a8  lea     r9, [rsp+150h+var_128]; int *
0x18001a2ad  mov     [rsp+150h+var_130], 0
0x18001a2b5  lea     r8, [rsp+150h+var_130]; int *
0x18001a2ba  mov     [rsp+150h+var_128], 0
0x18001a2c2  lea     rdx, [rsp+150h+pv]; unsigned __int16 **
0x18001a2c7  call    ?GetSlateATList@@YAJHPEAPEAGPEAH1@Z; GetSlateATList(int,ushort * *,int *,int *)
0x18001a2cc  test    eax, eax
0x18001a2ce  js      short loc_18001A2FD
0x18001a2d0  xor     esi, esi
0x18001a2d2  cmp     [rsp+150h+var_130], esi
0x18001a2d6  jle     short loc_18001A2FD
0x18001a2d8  movsxd  rax, esi
0x18001a2db  mov     rcx, r14
0x18001a2de  mov     rdi, [rsp+rax*8+150h+pv]
0x18001a2e3  mov     rdx, rdi
0x18001a2e6  call    cs:__imp_?AddString@Combobox@DirectUI@@QEAAHPEBG@Z; DirectUI::Combobox::AddString(ushort const *)
0x18001a2ec  mov     rcx, rdi; pv
0x18001a2ef  call    cs:__imp_CoTaskMemFree
0x18001a2f5  inc     esi
0x18001a2f7  cmp     esi, [rsp+150h+var_130]
0x18001a2fb  jl      short loc_18001A2D8
0x18001a2fd  mov     edx, [rsp+150h+var_128]
0x18001a301  mov     rcx, r14
0x18001a304  inc     edx
0x18001a306  call    cs:__imp_?SetSelection@Combobox@DirectUI@@QEAAJH@Z; DirectUI::Combobox::SetSelection(int)
0x18001a30c  lea     rcx, [rbx-18h]; this
0x18001a310  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001a315  mov     rcx, [rbp+50h+var_20]
0x18001a319  xor     rcx, rsp; StackCookie
0x18001a31c  call    __security_check_cookie
0x18001a321  lea     r11, [rsp+150h+var_10]
0x18001a329  mov     rbx, [r11+28h]
0x18001a32d  mov     rsi, [r11+30h]
0x18001a331  mov     rsp, r11
0x18001a334  pop     r14
0x18001a336  pop     rdi
0x18001a337  pop     rbp
0x18001a338  retn
```
