# Windows::Internal::CPopupWindowImpl::SetTitle(ushort const *)

- ea: `0x180090580`
- end: `0x1800908ec`
- name: `?SetTitle@CPopupWindowImpl@Internal@Windows@@UEAAJPEBG@Z`
- size: `876`
- prototype: `int(Windows::Internal::CPopupWindowImpl *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000af94`
- `0x180026f48`
- `0x180044298`
- `0x18004b470`
- `0x18008e5c8`
- `0x180090580`
- `0x180091508`
- `0x180093508`
- `0x1800e5010`

## import_xrefs

- `USER32!SetWindowTextW` at `0x1800905ab`
- `USER32!SetWindowTextW` at `0x1800905fb`
- `USER32!SetWindowTextW` at `0x1800905ab`
- `USER32!SetWindowTextW` at `0x1800905fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009060b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009061b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009060b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009061b`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18009076b`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180090849`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18009085a`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18009076b`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180090849`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18009085a`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180090839`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180090839`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x18009059f`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x18009059f`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x180090639`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x180090811`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x180090639`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x180090811`
- `DUI70!?Insert@Element@DirectUI@@QEAAJPEAV12@I@Z` at `0x18009078f`
- `DUI70!?Insert@Element@DirectUI@@QEAAJPEAV12@I@Z` at `0x18009078f`
- `DUI70!?Create@RichText@DirectUI@@SAJPEAVElement@2@PEAKPEAPEAV32@@Z` at `0x1800906d4`
- `DUI70!?Create@RichText@DirectUI@@SAJPEAVElement@2@PEAKPEAPEAV32@@Z` at `0x1800906d4`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x18009077f`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x18009077f`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800907a3`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800907a3`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800907fe`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180090883`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800907fe`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180090883`
- `DUI70!?GetIndex@Element@DirectUI@@QEAAHXZ` at `0x180090774`
- `DUI70!?GetIndex@Element@DirectUI@@QEAAHXZ` at `0x180090774`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800907e7`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18009086c`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800907e7`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18009086c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180090655`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18009082d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180090655`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18009082d`
- `DUI70!StrToID` at `0x180090649`
- `DUI70!StrToID` at `0x180090821`
- `DUI70!StrToID` at `0x180090649`
- `DUI70!StrToID` at `0x180090821`

## pseudocode

```c
__int64 __fastcall Windows::Internal::CPopupWindowImpl::SetTitle(
        Windows::Internal::CPopupWindowImpl *this,
        const unsigned __int16 *a2)
{
  DirectUI::NativeHWNDHost *v2; // r15
  HWND HWND; // rax
  HWND v6; // rax
  const unsigned __int16 **v7; // r14
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // esi
  DirectUI::Element *Element; // rbx
  unsigned __int16 v12; // ax
  struct DirectUI::Element *Descendent; // rax
  __int64 v14; // rcx
  DirectUI::Element *v15; // rsi
  _DWORD *v16; // rcx
  __int64 v17; // rdx
  _DWORD *v18; // rcx
  struct DirectUI::Element *v19; // rbx
  unsigned int Index; // ebx
  DirectUI::Element *Parent; // rax
  DirectUI::Element *v22; // rbx
  unsigned __int16 v23; // ax
  DirectUI::Element *v24; // rax
  struct DirectUI::Element **savedregs; // [rsp+20h] [rbp+0h]
  struct DirectUI::Element *v27; // [rsp+60h] [rbp+40h] BYREF
  struct DirectUI::Element *v28; // [rsp+68h] [rbp+48h] BYREF
  DirectUI::Element **v29; // [rsp+70h] [rbp+50h] BYREF

  v2 = (Windows::Internal::CPopupWindowImpl *)((char *)this - 56);
  HWND = DirectUI::NativeHWNDHost::GetHWND((Windows::Internal::CPopupWindowImpl *)((char *)this - 56));
  SetWindowTextW(HWND, a2);
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 88LL))(*((_QWORD *)this + 5)) == 1 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 120LL))(*((_QWORD *)this + 5)) )
    {
      v6 = (HWND)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 128LL))(*((_QWORD *)this + 5));
      if ( v6 )
        SetWindowTextW(v6, a2);
    }
  }
  v7 = (const unsigned __int16 **)((char *)this + 432);
  CoTaskMemFree(*((LPVOID *)this + 54));
  *((_QWORD *)this + 54) = 0;
  if ( !a2 || (CoTaskMemFree(0), v10 = _AllocString<CTCoAllocPolicy>(v9, v8, a2, (_QWORD *)this + 54), v10 >= 0) )
  {
    Element = DirectUI::NativeHWNDHost::GetElement(v2);
    v12 = StrToID(L"Title");
    Descendent = DirectUI::Element::FindDescendent(Element, v12);
    v14 = *((_QWORD *)this + 5);
    v27 = Descendent;
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v14 + 88LL))(v14) != 2
      && (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 88LL))(*((_QWORD *)this + 5)) != 3 )
    {
      Windows::Internal::CPopupWindowImpl::_SetUpTransitionAnimation(v2);
      if ( (*(unsigned __int8 (__fastcall **)(Windows::Internal::CPopupWindowImpl *))(*(_QWORD *)this + 400LL))(this) )
      {
        if ( !*((_DWORD *)this + 38) )
        {
          v15 = v27;
          v27 = 0;
          v28 = 0;
          if ( (int)DirectUI::RichText::Create(0, 0, &v28) >= 0
            && (int)Windows::Internal::CreateNamedElementFromDUIFile(
                      (Windows::Internal *)L"title",
                      (const unsigned __int16 *)0x220F,
                      (int)v28,
                      (struct DirectUI::Element *)&v27,
                      savedregs) >= 0 )
          {
            v16 = (_DWORD *)*((_QWORD *)this + 18);
            if ( v16 && *((_QWORD *)this + 17) )
            {
              v17 = *v16 & 0xFFFFFFF;
              v29 = 0;
              if ( (int)DirectUI::DynamicArrayBase<DirectUI::Element *,DirectUI::DoubleAllocationPolicy<DirectUI::Element *>,1,0>::InsertPtr(
                          v16,
                          v17,
                          &v29) >= 0 )
                *v29 = v15;
              v18 = (_DWORD *)*((_QWORD *)this + 17);
              v19 = v27;
              v29 = 0;
              if ( (int)DirectUI::DynamicArrayBase<DirectUI::Element *,DirectUI::DoubleAllocationPolicy<DirectUI::Element *>,1,0>::InsertPtr(
                          v18,
                          *v18 & 0xFFFFFFF,
                          &v29) >= 0 )
                *v29 = v19;
              DirectUI::Element::SetLayoutPos(v15, -2);
            }
            Index = DirectUI::Element::GetIndex(v15);
            Parent = DirectUI::Element::GetParent(v15);
            if ( (int)DirectUI::Element::Insert(Parent, v27, Index) >= 0 )
              DirectUI::Element::SetID(v15, &Class);
          }
        }
      }
    }
    if ( !*v7
      || !**v7
      || (*((_DWORD *)this + 21) & 0x8000000) != 0
      || (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 88LL))(*((_QWORD *)this + 5)) == 2 )
    {
      v10 = DirectUI::Element::SetLayoutPos(v27, -3);
      if ( v10 >= 0 )
      {
        v10 = DirectUI::Element::SetVisible(v27, 0);
        if ( v10 >= 0 )
        {
          v10 = DirectUI::Element::SetContentString(v27, &Class);
          if ( v10 >= 0 )
          {
LABEL_32:
            if ( *((_QWORD *)this + 7) )
              v10 = Windows::Internal::CPopupWindowImpl::_EnsureProxy(v2, 1);
          }
        }
      }
    }
    else
    {
      v10 = DirectUI::Element::SetVisible(v27, 1);
      if ( v10 >= 0 )
      {
        v10 = DirectUI::Element::SetContentString(v27, *v7);
        if ( v10 >= 0 )
        {
          v22 = DirectUI::NativeHWNDHost::GetElement(v2);
          v23 = StrToID(L"TitleBar");
          v24 = DirectUI::Element::FindDescendent(v22, v23);
          DirectUI::Element::SetAccName(v24, *v7);
          DirectUI::Element::SetLayoutPos(v27, *((_DWORD *)this + 86));
          goto LABEL_32;
        }
      }
    }
    Windows::Internal::CPopupWindowImpl::_SetTitleBarLayout(v2);
    if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 88LL))(*((_QWORD *)this + 5)) != 2
      && (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 88LL))(*((_QWORD *)this + 5)) != 3 )
    {
      Windows::Internal::CPopupWindowImpl::_DoTransitionAnimation(v2);
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180090580  push    rbp
0x180090582  push    rbx
0x180090583  push    rsi
0x180090584  push    rdi
0x180090585  push    r12
0x180090587  push    r14
0x180090589  push    r15; struct DirectUI::Element **
0x18009058b  mov     rbp, rsp
0x18009058e  sub     rsp, 20h
0x180090592  lea     r15, [rcx-38h]
0x180090596  mov     rdi, rcx
0x180090599  mov     rcx, r15
0x18009059c  mov     rbx, rdx
0x18009059f  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x1800905a5  mov     rcx, rax; hWnd
0x1800905a8  mov     rdx, rbx; lpString
0x1800905ab  call    cs:__imp_SetWindowTextW
0x1800905b1  mov     rcx, [rdi+28h]
0x1800905b5  mov     rax, [rcx]
0x1800905b8  mov     rax, [rax+58h]
0x1800905bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800905c1  xor     r12d, r12d
0x1800905c4  cmp     eax, 1
0x1800905c7  jnz     short loc_180090601
0x1800905c9  mov     rcx, [rdi+28h]
0x1800905cd  mov     rax, [rcx]
0x1800905d0  mov     rax, [rax+78h]
0x1800905d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800905d9  test    al, al
0x1800905db  jz      short loc_180090601
0x1800905dd  mov     rcx, [rdi+28h]
0x1800905e1  mov     rax, [rcx]
0x1800905e4  mov     rax, [rax+80h]
0x1800905eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800905f0  test    rax, rax
0x1800905f3  jz      short loc_180090601
0x1800905f5  mov     rdx, rbx; lpString
0x1800905f8  mov     rcx, rax; hWnd
0x1800905fb  call    cs:__imp_SetWindowTextW
0x180090601  lea     r14, [rdi+1B0h]
0x180090608  mov     rcx, [r14]; pv
0x18009060b  call    cs:__imp_CoTaskMemFree
0x180090611  mov     [r14], r12
0x180090614  test    rbx, rbx
0x180090617  jz      short loc_180090636
0x180090619  xor     ecx, ecx; pv
0x18009061b  call    cs:__imp_CoTaskMemFree
0x180090621  mov     r9, r14
0x180090624  mov     r8, rbx
0x180090627  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18009062c  mov     esi, eax
0x18009062e  test    eax, eax
0x180090630  js      loc_1800908DB
0x180090636  mov     rcx, r15
0x180090639  call    cs:__imp_?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ; DirectUI::NativeHWNDHost::GetElement(void)
0x18009063f  lea     rcx, aTitle_0; "Title"
0x180090646  mov     rbx, rax
0x180090649  call    cs:__imp_StrToID
0x18009064f  movzx   edx, ax
0x180090652  mov     rcx, rbx
0x180090655  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18009065b  mov     rcx, [rdi+28h]
0x18009065f  mov     [rbp+arg_0], rax
0x180090663  mov     rax, [rcx]
0x180090666  mov     rax, [rax+58h]
0x18009066a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009066f  cmp     eax, 2
0x180090672  jz      loc_1800907A9
0x180090678  mov     rcx, [rdi+28h]
0x18009067c  mov     rax, [rcx]
0x18009067f  mov     rax, [rax+58h]
0x180090683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090688  cmp     eax, 3
0x18009068b  jz      loc_1800907A9
0x180090691  mov     rcx, r15; this
0x180090694  call    ?_SetUpTransitionAnimation@CPopupWindowImpl@Internal@Windows@@AEAAXXZ; Windows::Internal::CPopupWindowImpl::_SetUpTransitionAnimation(void)
0x180090699  mov     rax, [rdi]
0x18009069c  mov     rcx, rdi
0x18009069f  mov     rax, [rax+190h]
0x1800906a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800906ab  test    al, al
0x1800906ad  jz      loc_1800907A9
0x1800906b3  cmp     [rdi+98h], r12d
0x1800906ba  jnz     loc_1800907A9
0x1800906c0  mov     rsi, [rbp+arg_0]
0x1800906c4  lea     r8, [rbp+arg_8]
0x1800906c8  xor     edx, edx
0x1800906ca  mov     [rbp+arg_0], r12
0x1800906ce  xor     ecx, ecx
0x1800906d0  mov     [rbp+arg_8], r12
0x1800906d4  call    cs:__imp_?Create@RichText@DirectUI@@SAJPEAVElement@2@PEAKPEAPEAV32@@Z; DirectUI::RichText::Create(DirectUI::Element *,ulong *,DirectUI::Element * *)
0x1800906da  test    eax, eax
0x1800906dc  js      loc_1800907A9
0x1800906e2  mov     r8, [rbp+arg_8]; int
0x1800906e6  lea     r9, [rbp+arg_0]; struct DirectUI::Element *
0x1800906ea  mov     edx, 220Fh; unsigned __int16 *
0x1800906ef  lea     rcx, aTitle; "title"
0x1800906f6  call    ?CreateNamedElementFromDUIFile@Internal@Windows@@YAJPEBGHPEAVElement@DirectUI@@PEAPEAV34@@Z; Windows::Internal::CreateNamedElementFromDUIFile(ushort const *,int,DirectUI::Element *,DirectUI::Element * *)
0x1800906fb  test    eax, eax
0x1800906fd  js      loc_1800907A9
0x180090703  mov     rcx, [rdi+90h]
0x18009070a  test    rcx, rcx
0x18009070d  jz      short loc_180090771
0x18009070f  cmp     [rdi+88h], r12
0x180090716  jz      short loc_180090771
0x180090718  mov     edx, [rcx]
0x18009071a  lea     r8, [rbp+arg_10]
0x18009071e  and     edx, 0FFFFFFFh
0x180090724  mov     [rbp+arg_10], r12
0x180090728  call    ?InsertPtr@?$DynamicArrayBase@PEAVElement@DirectUI@@V?$DoubleAllocationPolicy@PEAVElement@DirectUI@@@2@$00$0A@@DirectUI@@QEAAJIPEAPEAPEAVElement@2@@Z; DirectUI::DynamicArrayBase<DirectUI::Element *,DirectUI::DoubleAllocationPolicy<DirectUI::Element *>,1,0>::InsertPtr(uint,DirectUI::Element * * *)
0x18009072d  test    eax, eax
0x18009072f  js      short loc_180090738
0x180090731  mov     rax, [rbp+arg_10]
0x180090735  mov     [rax], rsi
0x180090738  mov     rcx, [rdi+88h]
0x18009073f  lea     r8, [rbp+arg_10]
0x180090743  mov     rbx, [rbp+arg_0]
0x180090747  mov     [rbp+arg_10], r12
0x18009074b  mov     edx, [rcx]
0x18009074d  and     edx, 0FFFFFFFh
0x180090753  call    ?InsertPtr@?$DynamicArrayBase@PEAVElement@DirectUI@@V?$DoubleAllocationPolicy@PEAVElement@DirectUI@@@2@$00$0A@@DirectUI@@QEAAJIPEAPEAPEAVElement@2@@Z; DirectUI::DynamicArrayBase<DirectUI::Element *,DirectUI::DoubleAllocationPolicy<DirectUI::Element *>,1,0>::InsertPtr(uint,DirectUI::Element * * *)
0x180090758  test    eax, eax
0x18009075a  js      short loc_180090763
0x18009075c  mov     rax, [rbp+arg_10]
0x180090760  mov     [rax], rbx
0x180090763  mov     edx, 0FFFFFFFEh
0x180090768  mov     rcx, rsi
0x18009076b  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180090771  mov     rcx, rsi
0x180090774  call    cs:__imp_?GetIndex@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetIndex(void)
0x18009077a  mov     rcx, rsi
0x18009077d  mov     ebx, eax
0x18009077f  call    cs:__imp_?GetParent@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetParent(void)
0x180090785  mov     rdx, [rbp+arg_0]
0x180090789  mov     r8d, ebx
0x18009078c  mov     rcx, rax
0x18009078f  call    cs:__imp_?Insert@Element@DirectUI@@QEAAJPEAV12@I@Z; DirectUI::Element::Insert(DirectUI::Element *,uint)
0x180090795  test    eax, eax
0x180090797  js      short loc_1800907A9
0x180090799  lea     rdx, Class
0x1800907a0  mov     rcx, rsi
0x1800907a3  call    cs:__imp_?SetID@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetID(ushort const *)
0x1800907a9  mov     rax, [r14]
0x1800907ac  test    rax, rax
0x1800907af  jz      loc_180090851
0x1800907b5  cmp     [rax], r12w
0x1800907b9  jz      loc_180090851
0x1800907bf  test    dword ptr [rdi+54h], 8000000h
0x1800907c6  jnz     loc_180090851
0x1800907cc  mov     rcx, [rdi+28h]
0x1800907d0  mov     rax, [rcx]
0x1800907d3  mov     rax, [rax+58h]
0x1800907d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800907dc  cmp     eax, 2
0x1800907df  jz      short loc_180090851
0x1800907e1  mov     rcx, [rbp+arg_0]
0x1800907e5  mov     dl, 1
0x1800907e7  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x1800907ed  mov     esi, eax
0x1800907ef  test    eax, eax
0x1800907f1  js      loc_1800908A1
0x1800907f7  mov     rdx, [r14]
0x1800907fa  mov     rcx, [rbp+arg_0]
0x1800907fe  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180090804  mov     esi, eax
0x180090806  test    eax, eax
0x180090808  js      loc_1800908A1
0x18009080e  mov     rcx, r15
0x180090811  call    cs:__imp_?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ; DirectUI::NativeHWNDHost::GetElement(void)
0x180090817  lea     rcx, aTitlebar; "TitleBar"
0x18009081e  mov     rbx, rax
0x180090821  call    cs:__imp_StrToID
0x180090827  movzx   edx, ax
0x18009082a  mov     rcx, rbx
0x18009082d  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180090833  mov     rdx, [r14]
0x180090836  mov     rcx, rax
0x180090839  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x18009083f  mov     edx, [rdi+158h]
0x180090845  mov     rcx, [rbp+arg_0]
0x180090849  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18009084f  jmp     short loc_18009088F
0x180090851  mov     rcx, [rbp+arg_0]
0x180090855  mov     edx, 0FFFFFFFDh
0x18009085a  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180090860  mov     esi, eax
0x180090862  test    eax, eax
0x180090864  js      short loc_1800908A1
0x180090866  mov     rcx, [rbp+arg_0]
0x18009086a  xor     edx, edx
0x18009086c  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x180090872  mov     esi, eax
0x180090874  test    eax, eax
0x180090876  js      short loc_1800908A1
0x180090878  mov     rcx, [rbp+arg_0]
0x18009087c  lea     rdx, Class
0x180090883  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180090889  mov     esi, eax
0x18009088b  test    eax, eax
0x18009088d  js      short loc_1800908A1
0x18009088f  cmp     [rdi+38h], r12
0x180090893  jz      short loc_1800908A1
0x180090895  mov     dl, 1; bool
0x180090897  mov     rcx, r15; this
0x18009089a  call    ?_EnsureProxy@CPopupWindowImpl@Internal@Windows@@AEAAJ_N@Z; Windows::Internal::CPopupWindowImpl::_EnsureProxy(bool)
0x18009089f  mov     esi, eax
0x1800908a1  mov     rcx, r15; this
0x1800908a4  call    ?_SetTitleBarLayout@CPopupWindowImpl@Internal@Windows@@AEAAXXZ; Windows::Internal::CPopupWindowImpl::_SetTitleBarLayout(void)
0x1800908a9  mov     rcx, [rdi+28h]
0x1800908ad  mov     rax, [rcx]
0x1800908b0  mov     rax, [rax+58h]
0x1800908b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800908b9  cmp     eax, 2
0x1800908bc  jz      short loc_1800908DB
0x1800908be  mov     rcx, [rdi+28h]
0x1800908c2  mov     rax, [rcx]
0x1800908c5  mov     rax, [rax+58h]
0x1800908c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800908ce  cmp     eax, 3
0x1800908d1  jz      short loc_1800908DB
0x1800908d3  mov     rcx, r15; this
0x1800908d6  call    ?_DoTransitionAnimation@CPopupWindowImpl@Internal@Windows@@AEAAXXZ; Windows::Internal::CPopupWindowImpl::_DoTransitionAnimation(void)
0x1800908db  mov     eax, esi
0x1800908dd  add     rsp, 20h
0x1800908e1  pop     r15
0x1800908e3  pop     r14
0x1800908e5  pop     r12
0x1800908e7  pop     rdi
0x1800908e8  pop     rsi
0x1800908e9  pop     rbx
0x1800908ea  pop     rbp
0x1800908eb  retn
```
