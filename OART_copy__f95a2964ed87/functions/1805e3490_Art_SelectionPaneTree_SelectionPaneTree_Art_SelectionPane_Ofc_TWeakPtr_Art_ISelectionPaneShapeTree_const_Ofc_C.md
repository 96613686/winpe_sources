# Art::SelectionPaneTree::SelectionPaneTree(Art::SelectionPane &,Ofc::TWeakPtr<Art::ISelectionPaneShapeTree> const &,Ofc::CStr const &)

- ea: `0x1805e3490`
- end: `0x1805e3a48`
- name: `??0SelectionPaneTree@Art@@QEAA@AEAVSelectionPane@1@AEBV?$TWeakPtr@VISelectionPaneShapeTree@Art@@@Ofc@@AEBVCStr@4@@Z`
- size: `1464`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, installer_update`

## callers

- `0x180564744`

## callees

- `0x18000f870`
- `0x18002a690`
- `0x180074640`
- `0x1802503bc`
- `0x180278e50`
- `0x180279050`
- `0x1802a23d0`
- `0x1802a842c`
- `0x1805e3490`
- `0x180633870`
- `0x18069caa8`
- `0x1806bc2a8`
- `0x1806bc4f0`
- `0x1806bc6a8`
- `0x1806bc84c`
- `0x1806bcb10`
- `0x1806d19bc`
- `0x1806d20d8`
- `0x1806d235c`

## import_xrefs

- `KERNEL32!EncodePointer` at `0x1805e393f`
- `KERNEL32!EncodePointer` at `0x1805e393f`
- `Mso98Win32Client!__imp_?MsoCreateFlexDataSource@FlexUI@@YA_NHIPEAPEAUIDataSource@1@@Z` at `0x1805e3532`
- `Mso98Win32Client!__imp_?MsoCreateFlexDataSource@FlexUI@@YA_NHIPEAPEAUIDataSource@1@@Z` at `0x1805e3532`
- `mso40uiWin32Client!__imp_?Create@FlexList@FlexUI@@SA_NIPEAPEAV12@@Z` at `0x1805e3710`
- `mso40uiWin32Client!__imp_?Create@FlexList@FlexUI@@SA_NIPEAPEAV12@@Z` at `0x1805e3710`
- `mso40uiWin32Client!__imp_?CreateList@FlexValue@FlexUI@@SA_NPEAUIFlexList@2@AEAVFlexValueSP@2@@Z` at `0x1805e3750`
- `mso40uiWin32Client!__imp_?CreateList@FlexValue@FlexUI@@SA_NPEAUIFlexList@2@AEAVFlexValueSP@2@@Z` at `0x1805e3750`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x1805e362c`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x1805e362c`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1805e35a4`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1805e365a`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1805e3741`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1805e37aa`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1805e37fc`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1805e35a4`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1805e365a`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1805e3741`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1805e37aa`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1805e37fc`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x1805e3574`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x1805e3574`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1805e355a`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1805e361a`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1805e37c6`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1805e3a0f`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1805e3a2a`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1805e3a35`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1805e355a`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1805e361a`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1805e37c6`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1805e3a0f`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1805e3a2a`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1805e3a35`

## pseudocode

```c
__int64 __fastcall Art::SelectionPaneTree::SelectionPaneTree(
        __int64 a1,
        __int64 a2,
        struct Ofc::CProxyPtrImpl **a3,
        const wchar_t **a4)
{
  struct IDataSource **v8; // r9
  _QWORD *v9; // rbx
  __int64 v10; // rax
  int *v11; // rsi
  __int64 v12; // r14
  void *Checked; // rax
  __int64 v14; // r14
  void *v15; // rax
  void *v16; // rax
  unsigned __int64 v17; // rdx
  unsigned int v18; // r8d
  __int64 v19; // r14
  bool v20; // al
  struct Ofc::CProxyPtrImpl *v21; // rcx
  char v22; // r14
  struct Ofc::CProxyPtrImpl *v23; // rcx
  __int64 v24; // rcx
  struct Ofc::CProxyPtrImpl *v25; // rbx
  __int64 *v26; // rcx
  bool i; // zf
  struct Ofc::CProxyPtrImpl **ItemAddr; // rax
  unsigned __int64 v29; // rdx
  unsigned int v30; // r8d
  NetUI::BaseValue *v31; // rax
  __int64 v32; // rdx
  _QWORD *v33; // r14
  _QWORD *v34; // rax
  _QWORD *v35; // rbx
  void *v36; // rax
  unsigned __int64 v37; // rdx
  unsigned int v38; // r8d
  Art::SelectionPaneBaseListener *v39; // rax
  Art::SelectionPaneBaseListener *v40; // rbx
  Art::SelectionPaneBaseListener *v41; // rcx
  int v43; // [rsp+20h] [rbp-50h]
  int v44; // [rsp+20h] [rbp-50h]
  int v45; // [rsp+20h] [rbp-50h]
  Ofc::CProxyPtrImpl *v46; // [rsp+30h] [rbp-40h] BYREF
  struct Ofc::CProxyPtrImpl *v47; // [rsp+38h] [rbp-38h] BYREF
  __int64 *v48; // [rsp+40h] [rbp-30h] BYREF
  __int64 v49; // [rsp+48h] [rbp-28h]
  __int64 **v50; // [rsp+50h] [rbp-20h] BYREF
  __int64 v51; // [rsp+58h] [rbp-18h]
  __int64 *v52; // [rsp+60h] [rbp-10h]
  int v53; // [rsp+68h] [rbp-8h]
  int v54; // [rsp+6Ch] [rbp-4h]
  struct Ofc::CProxyPtrImpl *v55; // [rsp+B8h] [rbp+48h] BYREF
  NetUI::BaseValue *v56; // [rsp+C0h] [rbp+50h] BYREF

  *(_QWORD *)(a1 + 24) = a1;
  Ofc::CProxyPtrImpl::InitAsTWeakPtrThisProxy((Ofc::CProxyPtrImpl *)a1);
  *(_QWORD *)(a1 + 32) = a2;
  *(_QWORD *)(a1 + 40) = Ofc::CProxyPtrImpl::WeakAddRef(*a3);
  v9 = (_QWORD *)(a1 + 48);
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  v10 = 2;
  do
  {
    *(_QWORD *)(a1 + 64) = 0;
    *(_QWORD *)(a1 + 72) = 0;
    --v10;
  }
  while ( v10 );
  v11 = &`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
  *(_QWORD *)(a1 + 80) = &`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
  if ( !*((_QWORD *)*a3 + 2) )
    goto LABEL_69;
  if ( *v9 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 16LL))(*v9);
  *v9 = 0;
  if ( !FlexUI::MsoCreateFlexDataSource((FlexUI *)0x13C9, 134221568, a1 + 48, v8) )
  {
LABEL_69:
    MsoShipAssertTagProc(591938319);
    Ofc::CAbortException::ThrowTag(0, 591938318);
    goto LABEL_70;
  }
  v46 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*(struct Ofc::CProxyPtrImpl **)(a1 + 40));
  v12 = *v9;
  if ( *v9 )
  {
    v55 = 0;
    FlexUI::FlexValue::CreateString(*a4, (struct FlexUI::FlexValueSP *)&v55);
    if ( v55 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v12 + 48LL))(v12, 0, 0);
      if ( v55 )
        NetUI::BaseValue::Release(v55);
    }
  }
  else
  {
    MsoShipAssertTagProc(7997248);
  }
  Checked = Ofc::CProxyPtrImpl::GetChecked(v46);
  if ( (*(unsigned __int8 (__fastcall **)(void *))(*(_QWORD *)Checked + 136LL))(Checked) )
  {
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64, __int64, char))(*(_QWORD *)*v9 + 64LL))(*v9, 0, 5, 1, 1);
    LOBYTE(v44) = 1;
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64, __int64, int))(*(_QWORD *)*v9 + 64LL))(*v9, 0, 6, 1, v44);
  }
  else
  {
    v14 = *v9;
    if ( *v9 )
    {
      v55 = 0;
      FlexUI::FlexValue::CreateBoolean(1, (struct FlexUI::FlexValueSP *)&v55);
      if ( v55 )
      {
        (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v14 + 48LL))(v14, 0, 2);
        if ( v55 )
          NetUI::BaseValue::Release(v55);
      }
    }
    else
    {
      MsoShipAssertTagProc(7997248);
    }
  }
  v15 = Ofc::CProxyPtrImpl::GetChecked(v46);
  if ( (*(unsigned __int8 (__fastcall **)(void *))(*(_QWORD *)v15 + 144LL))(v15) )
  {
    LOBYTE(v43) = 1;
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64, __int64, int))(*(_QWORD *)*v9 + 64LL))(*v9, 0, 3, 1, v43);
    LOBYTE(v45) = 1;
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64, __int64, int))(*(_QWORD *)*v9 + 64LL))(*v9, 0, 4, 1, v45);
  }
  v48 = 0;
  v49 = 0;
  v16 = Ofc::CProxyPtrImpl::GetChecked(v46);
  (*(void (__fastcall **)(void *, __int64 **))(*(_QWORD *)v16 + 8LL))(v16, &v48);
  if ( (int)v49 <= 0 )
    goto LABEL_56;
  v19 = *v9;
  if ( !*v9 )
  {
LABEL_70:
    MsoShipAssertTagProc(7997250);
    goto LABEL_71;
  }
  v56 = 0;
  v55 = 0;
  v20 = FlexUI::FlexList::Create(v49, &v55);
  v21 = v55;
  if ( !v20 )
  {
    if ( !v55 )
      goto LABEL_26;
    goto LABEL_25;
  }
  FlexUI::FlexValue::CreateList(v55, (struct FlexUI::FlexValueSP *)&v56);
  if ( !v56 )
  {
    v21 = v55;
    if ( !v55 )
      goto LABEL_71;
LABEL_25:
    v55 = 0;
    (*(void (__fastcall **)(struct Ofc::CProxyPtrImpl *))(*(_QWORD *)v21 + 16LL))(v21);
LABEL_26:
    if ( v56 )
      NetUI::BaseValue::Release(v56);
    goto LABEL_71;
  }
  v22 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v19 + 48LL))(v19, 0, 1);
  v23 = v55;
  if ( v55 )
  {
    v55 = 0;
    (*(void (__fastcall **)(struct Ofc::CProxyPtrImpl *))(*(_QWORD *)v23 + 16LL))(v23);
  }
  if ( v56 )
    NetUI::BaseValue::Release(v56);
  if ( !v22 )
  {
LABEL_71:
    MsoShipAssertTagProc(591938317);
    Ofc::CAbortException::ThrowTag(0, 591938316);
    __debugbreak();
  }
  v24 = *v9;
  if ( !*v9 )
  {
    MsoShipAssertTagProc(7997216);
LABEL_38:
    v25 = 0;
    v55 = 0;
    goto LABEL_42;
  }
  v55 = 0;
  (*(void (__fastcall **)(__int64, __int64, struct Ofc::CProxyPtrImpl **))(*(_QWORD *)v24 + 40LL))(v24, 1, &v55);
  if ( !v55 )
    goto LABEL_38;
  v25 = (struct Ofc::CProxyPtrImpl *)*((_QWORD *)v55 + 1);
  NetUI::BaseValue::Release(v55);
  v55 = v25;
  if ( v25 )
    (*(void (__fastcall **)(struct Ofc::CProxyPtrImpl *))(*(_QWORD *)v25 + 8LL))(v25);
LABEL_42:
  v50 = &v48;
  v26 = v48;
  v52 = v48;
  v54 = HIDWORD(v49);
  for ( i = v48 == 0; ; i = v26 == 0 )
  {
    v53 = 0;
    if ( i )
    {
      v51 = 0;
      goto LABEL_47;
    }
    if ( *((_DWORD *)v26 + 4) )
      break;
    v26 = (__int64 *)*v26;
    v52 = v26;
  }
  v51 = v26[3];
LABEL_47:
  v47 = (struct Ofc::CProxyPtrImpl *)&`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
  while ( 1 )
  {
    ItemAddr = (struct Ofc::CProxyPtrImpl **)Ofc::CListIterImpl::NextItemAddr((Ofc::CListIterImpl *)&v50);
    if ( !ItemAddr )
      break;
    Ofc::CProxyPtrImpl::WeakAssign(&v47, *ItemAddr);
    v31 = (NetUI::BaseValue *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x40, v29, v30);
    v56 = v31;
    if ( v31 )
      v33 = (_QWORD *)Art::SelectionPaneNode::SelectionPaneNode((__int64)v31, *(_QWORD *)(a1 + 32), &v47);
    else
      v33 = 0;
    FlexUI::RefCountTypeListSP<FlexUI::IDataSource,FlexUI::TypeTraits<FlexUI::IDataSource *>>::Add(&v55, v32, v33[2]);
    *Ofc::CListImpl::NewTail((Ofc::CListImpl *)(a1 + 64)) = v33;
  }
  v55 = (struct Ofc::CProxyPtrImpl *)&`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
  Ofc::CProxyPtrImpl::WeakMoveAssign(&v47, &v55);
  Ofc::CProxyPtrImpl::DtorWeakRelease(&v55);
  Ofc::CProxyPtrImpl::DtorWeakRelease(&v47);
  if ( v25 )
    (*(void (__fastcall **)(struct Ofc::CProxyPtrImpl *))(*(_QWORD *)v25 + 16LL))(v25);
LABEL_56:
  v34 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x30, v17, v18);
  v35 = v34;
  if ( v34 )
  {
    v34[4] = v34 + 1;
    Ofc::CProxyPtrImpl::InitAsTWeakPtrThisProxy((Ofc::CProxyPtrImpl *)(v34 + 1));
    *v35 = &Art::SelectionPaneUpdater<Art::SelectionPaneTree>::`vftable';
    v35[5] = a1;
  }
  else
  {
    v35 = 0;
  }
  if ( v35 )
  {
    v11 = (int *)v35[4];
    _InterlockedExchange(v11, 1);
    *((_QWORD *)v11 + 1) = EncodePointer(Ofc::TDestructFromProxy<Dr::ScrapOwningCutCopyHandler const>);
    *((_QWORD *)v11 + 2) = v35;
  }
  v55 = (struct Ofc::CProxyPtrImpl *)v11;
  Ofc::CProxyPtrImpl::StrongMoveAssign((struct Ofc::CProxyPtrImpl **)(a1 + 80), &v55);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v55);
  v36 = Ofc::CProxyPtrImpl::GetChecked(v46);
  (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)v36 + 24LL))(v36, a1 + 80);
  v39 = (Art::SelectionPaneBaseListener *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x18, v37, v38);
  v40 = v39;
  if ( v39 )
  {
    *((_BYTE *)v39 + 8) = 0;
    *((_DWORD *)v39 + 3) = 1;
    *(_QWORD *)v39 = &Art::SelectionPaneTreeListener::`vftable';
    *((_QWORD *)v39 + 2) = a1;
  }
  else
  {
    v40 = 0;
  }
  v41 = *(Art::SelectionPaneBaseListener **)(a1 + 56);
  if ( v41 != v40 )
  {
    if ( v41 )
      (*(void (__fastcall **)(Art::SelectionPaneBaseListener *))(*(_QWORD *)v41 + 16LL))(v41);
    *(_QWORD *)(a1 + 56) = v40;
    v41 = v40;
  }
  Art::SelectionPaneBaseListener::Connect(v41);
  Ofc::TObjList<Ofc::TWeakPtr<Art::IAsyncDownloadUser>>::~TObjList<Ofc::TWeakPtr<Art::IAsyncDownloadUser>>((Ofc::CListImpl *)&v48);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v46);
  return a1;
}

```

## disassembly

```asm
0x1805e3490  mov     [rsp-38h+arg_18], rbx
0x1805e3495  mov     [rsp-38h+arg_0], rcx
0x1805e349a  push    rbp
0x1805e349b  push    rsi
0x1805e349c  push    rdi
0x1805e349d  push    r12
0x1805e349f  push    r13
0x1805e34a1  push    r14
0x1805e34a3  push    r15
0x1805e34a5  mov     rbp, rsp
0x1805e34a8  sub     rsp, 70h
0x1805e34ac  mov     r15, r9
0x1805e34af  mov     r14, r8
0x1805e34b2  mov     rbx, rdx
0x1805e34b5  mov     rdi, rcx
0x1805e34b8  mov     [rcx+18h], rcx
0x1805e34bc  call    ?InitAsTWeakPtrThisProxy@CProxyPtrImpl@Ofc@@IEAAXXZ; Ofc::CProxyPtrImpl::InitAsTWeakPtrThisProxy(void)
0x1805e34c1  mov     [rdi+20h], rbx
0x1805e34c5  mov     rcx, [r14]; struct Ofc::CProxyPtrImpl *
0x1805e34c8  call    ?WeakAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::WeakAddRef(Ofc::CProxyPtrImpl *)
0x1805e34cd  mov     [rdi+28h], rax
0x1805e34d1  lea     rbx, [rdi+30h]
0x1805e34d5  xor     edx, edx
0x1805e34d7  mov     [rbx], rdx
0x1805e34da  mov     [rdi+38h], rdx
0x1805e34de  lea     eax, [rdx+2]
0x1805e34e1  mov     [rdi+40h], rdx
0x1805e34e5  mov     [rdi+48h], rdx
0x1805e34e9  sub     rax, 1
0x1805e34ed  jnz     short loc_1805E34E1
0x1805e34ef  lea     r13, [rdi+50h]
0x1805e34f3  lea     rsi, ?s_proxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4UProxyPtrSentinel@?1??123@KAAEBQEAV23@XZ@B; `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::ProxyPtrSentinel const `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_proxyPtrSentinel
0x1805e34fa  mov     [r13+0], rsi
0x1805e34fe  mov     rax, [r14]
0x1805e3501  cmp     [rax+10h], rdx
0x1805e3505  jz      loc_1805E3A0A
0x1805e350b  mov     rcx, [rbx]
0x1805e350e  test    rcx, rcx
0x1805e3511  jz      short loc_1805E3522
0x1805e3513  mov     rax, [rcx]
0x1805e3516  mov     rax, [rax+10h]
0x1805e351a  call    cs:__guard_dispatch_icall_fptr
0x1805e3520  xor     edx, edx
0x1805e3522  mov     [rbx], rdx
0x1805e3525  mov     r8, rbx
0x1805e3528  mov     edx, 8000F00h
0x1805e352d  mov     ecx, 13C9h
0x1805e3532  call    cs:__imp_?MsoCreateFlexDataSource@FlexUI@@YA_NHIPEAPEAUIDataSource@1@@Z; FlexUI::MsoCreateFlexDataSource(int,uint,FlexUI::IDataSource * *)
0x1805e3538  test    al, al
0x1805e353a  jz      loc_1805E3A0A
0x1805e3540  mov     rcx, [rdi+28h]; struct Ofc::CProxyPtrImpl *
0x1805e3544  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1805e3549  mov     [rbp+var_40], rax
0x1805e354d  mov     r14, [rbx]
0x1805e3550  test    r14, r14
0x1805e3553  jnz     short loc_1805E3565
0x1805e3555  mov     ecx, 7A0740h
0x1805e355a  call    cs:__imp_MsoShipAssertTagProc
0x1805e3560  xor     r15d, r15d
0x1805e3563  jmp     short loc_1805E35AA
0x1805e3565  mov     [rbp+arg_8], 0
0x1805e356d  lea     rdx, [rbp+arg_8]
0x1805e3571  mov     rcx, [r15]
0x1805e3574  call    cs:__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateString(wchar_t const *,FlexUI::FlexValueSP &)
0x1805e357a  mov     r9, [rbp+arg_8]
0x1805e357e  xor     r15d, r15d
0x1805e3581  test    r9, r9
0x1805e3584  jz      short loc_1805E35AA
0x1805e3586  mov     rax, [r14]
0x1805e3589  xor     r8d, r8d
0x1805e358c  xor     edx, edx
0x1805e358e  mov     rcx, r14
0x1805e3591  mov     rax, [rax+30h]
0x1805e3595  call    cs:__guard_dispatch_icall_fptr
0x1805e359b  mov     rcx, [rbp+arg_8]
0x1805e359f  test    rcx, rcx
0x1805e35a2  jz      short loc_1805E35AA
0x1805e35a4  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1805e35aa  mov     rcx, [rbp+var_40]; this
0x1805e35ae  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1805e35b3  mov     rdx, rax
0x1805e35b6  mov     rcx, [rax]
0x1805e35b9  mov     rax, [rcx+88h]
0x1805e35c0  mov     rcx, rdx
0x1805e35c3  call    cs:__guard_dispatch_icall_fptr
0x1805e35c9  test    al, al
0x1805e35cb  jz      short loc_1805E360D
0x1805e35cd  mov     rcx, [rbx]
0x1805e35d0  mov     rax, [rcx]
0x1805e35d3  mov     byte ptr [rsp+70h+var_50], 1
0x1805e35d8  xor     edx, edx
0x1805e35da  lea     r9d, [rdx+1]
0x1805e35de  lea     r8d, [rdx+5]
0x1805e35e2  mov     rax, [rax+40h]
0x1805e35e6  call    cs:__guard_dispatch_icall_fptr
0x1805e35ec  mov     rcx, [rbx]
0x1805e35ef  mov     rax, [rcx]
0x1805e35f2  mov     byte ptr [rsp+70h+var_50], 1
0x1805e35f7  xor     edx, edx
0x1805e35f9  lea     r9d, [rdx+1]
0x1805e35fd  lea     r8d, [rdx+6]
0x1805e3601  mov     rax, [rax+40h]
0x1805e3605  call    cs:__guard_dispatch_icall_fptr
0x1805e360b  jmp     short loc_1805E3660
0x1805e360d  mov     r14, [rbx]
0x1805e3610  test    r14, r14
0x1805e3613  jnz     short loc_1805E3622
0x1805e3615  mov     ecx, 7A0740h
0x1805e361a  call    cs:__imp_MsoShipAssertTagProc
0x1805e3620  jmp     short loc_1805E3660
0x1805e3622  mov     [rbp+arg_8], r15
0x1805e3626  lea     rdx, [rbp+arg_8]
0x1805e362a  mov     cl, 1
0x1805e362c  call    cs:__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateBoolean(bool,FlexUI::FlexValueSP &)
0x1805e3632  mov     r9, [rbp+arg_8]
0x1805e3636  test    r9, r9
0x1805e3639  jz      short loc_1805E3660
0x1805e363b  mov     rax, [r14]
0x1805e363e  xor     edx, edx
0x1805e3640  lea     r8d, [rdx+2]
0x1805e3644  mov     rcx, r14
0x1805e3647  mov     rax, [rax+30h]
0x1805e364b  call    cs:__guard_dispatch_icall_fptr
0x1805e3651  mov     rcx, [rbp+arg_8]
0x1805e3655  test    rcx, rcx
0x1805e3658  jz      short loc_1805E3660
0x1805e365a  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1805e3660  mov     rcx, [rbp+var_40]; this
0x1805e3664  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1805e3669  mov     rdx, rax
0x1805e366c  mov     rcx, [rax]
0x1805e366f  mov     rax, [rcx+90h]
0x1805e3676  mov     rcx, rdx
0x1805e3679  call    cs:__guard_dispatch_icall_fptr
0x1805e367f  test    al, al
0x1805e3681  jz      short loc_1805E36C1
0x1805e3683  mov     rcx, [rbx]
0x1805e3686  mov     rax, [rcx]
0x1805e3689  mov     byte ptr [rsp+70h+var_50], 1
0x1805e368e  xor     edx, edx
0x1805e3690  lea     r9d, [rdx+1]
0x1805e3694  lea     r8d, [rdx+3]
0x1805e3698  mov     rax, [rax+40h]
0x1805e369c  call    cs:__guard_dispatch_icall_fptr
0x1805e36a2  mov     rcx, [rbx]
0x1805e36a5  mov     rax, [rcx]
0x1805e36a8  mov     byte ptr [rsp+70h+var_50], 1
0x1805e36ad  xor     edx, edx
0x1805e36af  lea     r9d, [rdx+1]
0x1805e36b3  lea     r8d, [rdx+4]
0x1805e36b7  mov     rax, [rax+40h]
0x1805e36bb  call    cs:__guard_dispatch_icall_fptr
0x1805e36c1  mov     [rbp+var_30], r15
0x1805e36c5  mov     [rbp+var_28], 0
0x1805e36cd  mov     rcx, [rbp+var_40]; this
0x1805e36d1  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1805e36d6  mov     r8, rax
0x1805e36d9  mov     rcx, [rax]
0x1805e36dc  mov     rax, [rcx+8]
0x1805e36e0  lea     rdx, [rbp+var_30]
0x1805e36e4  mov     rcx, r8
0x1805e36e7  call    cs:__guard_dispatch_icall_fptr
0x1805e36ed  mov     ecx, dword ptr [rbp+var_28]
0x1805e36f0  test    ecx, ecx
0x1805e36f2  jle     loc_1805E38F6
0x1805e36f8  mov     r14, [rbx]
0x1805e36fb  test    r14, r14
0x1805e36fe  jz      loc_1805E3A25
0x1805e3704  mov     [rbp+arg_10], r15
0x1805e3708  mov     [rbp+arg_8], r15
0x1805e370c  lea     rdx, [rbp+arg_8]
0x1805e3710  call    cs:__imp_?Create@FlexList@FlexUI@@SA_NIPEAPEAV12@@Z; FlexUI::FlexList::Create(uint,FlexUI::FlexList * *)
0x1805e3716  mov     rcx, [rbp+arg_8]
0x1805e371a  test    al, al
0x1805e371c  jnz     short loc_1805E374C
0x1805e371e  test    rcx, rcx
0x1805e3721  jz      short loc_1805E3734
0x1805e3723  mov     [rbp+arg_8], r15
0x1805e3727  mov     rax, [rcx]
0x1805e372a  mov     rax, [rax+10h]
0x1805e372e  call    cs:__guard_dispatch_icall_fptr
0x1805e3734  mov     rcx, [rbp+arg_10]
0x1805e3738  test    rcx, rcx
0x1805e373b  jz      loc_1805E3A30
0x1805e3741  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1805e3747  jmp     loc_1805E3A30
0x1805e374c  lea     rdx, [rbp+arg_10]
0x1805e3750  call    cs:__imp_?CreateList@FlexValue@FlexUI@@SA_NPEAUIFlexList@2@AEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateList(FlexUI::IFlexList *,FlexUI::FlexValueSP &)
0x1805e3756  mov     r9, [rbp+arg_10]
0x1805e375a  test    r9, r9
0x1805e375d  jnz     short loc_1805E376E
0x1805e375f  mov     rcx, [rbp+arg_8]
0x1805e3763  test    rcx, rcx
0x1805e3766  jz      loc_1805E3A30
0x1805e376c  jmp     short loc_1805E3723
0x1805e376e  mov     rax, [r14]
0x1805e3771  xor     edx, edx
0x1805e3773  lea     r8d, [rdx+1]
0x1805e3777  mov     rcx, r14
0x1805e377a  mov     rax, [rax+30h]
0x1805e377e  call    cs:__guard_dispatch_icall_fptr
0x1805e3784  mov     r14b, al
0x1805e3787  mov     rcx, [rbp+arg_8]
0x1805e378b  test    rcx, rcx
0x1805e378e  jz      short loc_1805E37A1
0x1805e3790  mov     [rbp+arg_8], r15
0x1805e3794  mov     rdx, [rcx]
0x1805e3797  mov     rax, [rdx+10h]
0x1805e379b  call    cs:__guard_dispatch_icall_fptr
0x1805e37a1  mov     rcx, [rbp+arg_10]
0x1805e37a5  test    rcx, rcx
0x1805e37a8  jz      short loc_1805E37B0
0x1805e37aa  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1805e37b0  test    r14b, r14b
0x1805e37b3  jz      loc_1805E3A30
0x1805e37b9  mov     rcx, [rbx]
0x1805e37bc  test    rcx, rcx
0x1805e37bf  jnz     short loc_1805E37D5
0x1805e37c1  mov     ecx, 7A0720h
0x1805e37c6  call    cs:__imp_MsoShipAssertTagProc
0x1805e37cc  mov     rbx, r15
0x1805e37cf  mov     [rbp+arg_8], rbx
0x1805e37d3  jmp     short loc_1805E381C
0x1805e37d5  mov     [rbp+arg_8], r15
0x1805e37d9  mov     rax, [rcx]
0x1805e37dc  lea     r8, [rbp+arg_8]
0x1805e37e0  mov     edx, 1
0x1805e37e5  mov     rax, [rax+28h]
0x1805e37e9  call    cs:__guard_dispatch_icall_fptr
0x1805e37ef  mov     rcx, [rbp+arg_8]
0x1805e37f3  test    rcx, rcx
0x1805e37f6  jz      short loc_1805E37CC
0x1805e37f8  mov     rbx, [rcx+8]
0x1805e37fc  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1805e3802  mov     [rbp+arg_8], rbx
0x1805e3806  test    rbx, rbx
0x1805e3809  jz      short loc_1805E381C
0x1805e380b  mov     rax, [rbx]
0x1805e380e  mov     rcx, rbx
0x1805e3811  mov     rax, [rax+8]
0x1805e3815  call    cs:__guard_dispatch_icall_fptr
0x1805e381b  nop
0x1805e381c  lea     rax, [rbp+var_30]
0x1805e3820  mov     [rbp+var_20], rax
0x1805e3824  mov     rcx, [rbp+var_30]
0x1805e3828  mov     [rbp+var_10], rcx
0x1805e382c  mov     eax, dword ptr [rbp+var_28+4]
0x1805e382f  mov     [rbp+var_4], eax
0x1805e3832  test    rcx, rcx
0x1805e3835  jmp     short loc_1805E384A
0x1805e3837  cmp     [rcx+10h], r15d
0x1805e383b  ja      short loc_1805E389A
0x1805e383d  mov     rax, [rcx]
0x1805e3840  mov     rcx, rax
0x1805e3843  mov     [rbp+var_10], rax
0x1805e3847  test    rax, rax
0x1805e384a  mov     [rbp+var_8], r15d
0x1805e384e  jnz     short loc_1805E3837
0x1805e3850  mov     [rbp+var_18], r15
0x1805e3854  mov     [rbp+var_38], rsi
0x1805e3858  lea     rcx, [rbp+var_20]; this
0x1805e385c  call    ?NextItemAddr@CListIterImpl@Ofc@@IEAAPEBQEAXXZ; Ofc::CListIterImpl::NextItemAddr(void)
0x1805e3861  lea     rcx, [rbp+var_38]; struct Ofc::CProxyPtrImpl **
0x1805e3865  test    rax, rax
0x1805e3868  jz      short loc_1805E38C2
0x1805e386a  mov     rdx, [rax]; struct Ofc::CProxyPtrImpl *
0x1805e386d  call    ?WeakAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::WeakAssign(Ofc::CProxyPtrImpl * *,Ofc::CProxyPtrImpl *)
0x1805e3872  mov     ecx, 40h ; '@'; this
0x1805e3877  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1805e387c  mov     [rbp+arg_10], rax
0x1805e3880  test    rax, rax
0x1805e3883  jz      short loc_1805E38A4
0x1805e3885  lea     r8, [rbp+var_38]
0x1805e3889  mov     rdx, [rdi+20h]
0x1805e388d  mov     rcx, rax
0x1805e3890  call    ??0SelectionPaneNode@Art@@QEAA@AEAVSelectionPane@1@AEBV?$TWeakPtr@VISelectionPaneShapeTreeNode@Art@@@Ofc@@@Z; Art::SelectionPaneNode::SelectionPaneNode(Art::SelectionPane &,Ofc::TWeakPtr<Art::ISelectionPaneShapeTreeNode> const &)
0x1805e3895  mov     r14, rax
0x1805e3898  jmp     short loc_1805E38A7
0x1805e389a  mov     rax, [rcx+18h]
0x1805e389e  mov     [rbp+var_18], rax
0x1805e38a2  jmp     short loc_1805E3854
0x1805e38a4  mov     r14, r15
0x1805e38a7  mov     r8, [r14+10h]
0x1805e38ab  lea     rcx, [rbp+arg_8]
0x1805e38af  call    ?Add@?$RefCountTypeListSP@UIDataSource@FlexUI@@V?$TypeTraits@PEAUIDataSource@FlexUI@@@2@@FlexUI@@QEAA_NPEAXPEAUIDataSource@2@@Z; FlexUI::RefCountTypeListSP<FlexUI::IDataSource,FlexUI::TypeTraits<FlexUI::IDataSource *>>::Add(void *,FlexUI::IDataSource *)
0x1805e38b4  lea     rcx, [rdi+40h]; this
0x1805e38b8  call    ?NewTail@CListImpl@Ofc@@IEAAPEAPEAXXZ; Ofc::CListImpl::NewTail(void)
0x1805e38bd  mov     [rax], r14
0x1805e38c0  jmp     short loc_1805E3858
0x1805e38c2  mov     [rbp+arg_8], rsi
0x1805e38c6  lea     rdx, [rbp+arg_8]; struct Ofc::CProxyPtrImpl **
0x1805e38ca  call    ?WeakMoveAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@0@Z; Ofc::CProxyPtrImpl::WeakMoveAssign(Ofc::CProxyPtrImpl * *,Ofc::CProxyPtrImpl * *)
0x1805e38cf  lea     rcx, [rbp+arg_8]; struct Ofc::CProxyPtrImpl **
0x1805e38d3  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x1805e38d8  lea     rcx, [rbp+var_38]; struct Ofc::CProxyPtrImpl **
0x1805e38dc  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x1805e38e1  test    rbx, rbx
0x1805e38e4  jz      short loc_1805E38F6
0x1805e38e6  mov     rax, [rbx]
0x1805e38e9  mov     rcx, rbx
  ... truncated ...
```
