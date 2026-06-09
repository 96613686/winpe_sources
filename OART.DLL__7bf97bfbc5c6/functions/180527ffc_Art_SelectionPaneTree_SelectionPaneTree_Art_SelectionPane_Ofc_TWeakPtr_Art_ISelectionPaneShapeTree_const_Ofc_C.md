# Art::SelectionPaneTree::SelectionPaneTree(Art::SelectionPane &,Ofc::TWeakPtr<Art::ISelectionPaneShapeTree> const &,Ofc::CStr const &)

- ea: `0x180527ffc`
- end: `0x1805285d8`
- name: `??0SelectionPaneTree@Art@@QEAA@AEAVSelectionPane@1@AEBV?$TWeakPtr@VISelectionPaneShapeTree@Art@@@Ofc@@AEBVCStr@4@@Z`
- size: `1500`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, installer_update`

## callers

- `0x180529a74`

## callees

- `0x18001e0f0`
- `0x1800659a0`
- `0x18006c150`
- `0x180071720`
- `0x1800c9d10`
- `0x18026e0d0`
- `0x18036ba6c`
- `0x1803f5b88`
- `0x180527508`
- `0x180527ffc`
- `0x1805285d8`
- `0x1806a5054`
- `0x1806a5084`
- `0x1806a51d0`
- `0x1806a57c4`
- `0x1806a59d4`
- `0x1806a5c90`
- `0x1806bd50c`
- `0x1806bd790`

## import_xrefs

- `KERNEL32!EncodePointer` at `0x1805284bf`
- `KERNEL32!EncodePointer` at `0x1805284bf`
- `Mso98Win32Client!__imp_?MsoCreateFlexDataSource@FlexUI@@YA_NHIPEAPEAUIDataSource@1@@Z` at `0x1805280a9`
- `Mso98Win32Client!__imp_?MsoCreateFlexDataSource@FlexUI@@YA_NHIPEAPEAUIDataSource@1@@Z` at `0x1805280a9`
- `mso40uiWin32Client!__imp_?Create@FlexList@FlexUI@@SA_NIPEAPEAV12@@Z` at `0x180528293`
- `mso40uiWin32Client!__imp_?Create@FlexList@FlexUI@@SA_NIPEAPEAV12@@Z` at `0x180528293`
- `mso40uiWin32Client!__imp_?CreateList@FlexValue@FlexUI@@SA_NPEAUIFlexList@2@AEAVFlexValueSP@2@@Z` at `0x1805282cc`
- `mso40uiWin32Client!__imp_?CreateList@FlexValue@FlexUI@@SA_NPEAUIFlexList@2@AEAVFlexValueSP@2@@Z` at `0x1805282cc`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x1805281a3`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x1805281a3`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x18052811b`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1805281d1`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1805282c0`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180528322`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180528388`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x18052811b`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1805281d1`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1805282c0`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180528322`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180528388`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x1805280eb`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x1805280eb`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1805280d1`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180528191`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18052827c`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180528332`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180528352`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1805285c5`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1805280d1`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180528191`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18052827c`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180528332`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180528352`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1805285c5`

## pseudocode

```c
__int64 __fastcall Art::SelectionPaneTree::SelectionPaneTree(__int64 a1, __int64 a2, __int64 *a3, const wchar_t **a4)
{
  struct IDataSource **v8; // r9
  __int64 v9; // rcx
  _QWORD *v10; // rbx
  __int64 v11; // rax
  int *v12; // rsi
  __int64 v13; // r14
  void *Checked; // rax
  __int64 v15; // r14
  void *v16; // rax
  void *v17; // rax
  unsigned __int64 v18; // rdx
  unsigned int v19; // r8d
  __int64 v20; // r14
  bool v21; // al
  struct Ofc::CProxyPtrImpl *v22; // rcx
  char v23; // r14
  struct Ofc::CProxyPtrImpl *v24; // rcx
  __int64 v25; // rcx
  struct Ofc::CProxyPtrImpl *v26; // rbx
  __int64 *v27; // rcx
  struct Ofc::CProxyPtrImpl **ItemAddr; // rax
  unsigned __int64 v29; // rdx
  unsigned int v30; // r8d
  NetUI::BaseValue *v31; // rax
  __int64 v32; // rdx
  struct IDataSource **v33; // r9
  _QWORD *v34; // r14
  _QWORD *v35; // rax
  _QWORD *v36; // rbx
  void *v37; // rax
  unsigned __int64 v38; // rdx
  unsigned int v39; // r8d
  Art::SelectionPaneBaseListener *v40; // rax
  Art::SelectionPaneBaseListener *v41; // rbx
  Art::SelectionPaneBaseListener *v42; // rcx
  __int64 *i; // rbx
  unsigned int j; // esi
  int v46; // [rsp+20h] [rbp-50h]
  int v47; // [rsp+20h] [rbp-50h]
  int v48; // [rsp+20h] [rbp-50h]
  Ofc::CProxyPtrImpl *v49; // [rsp+30h] [rbp-40h] BYREF
  struct Ofc::CProxyPtrImpl *v50; // [rsp+38h] [rbp-38h] BYREF
  __int64 *v51; // [rsp+40h] [rbp-30h] BYREF
  __int64 v52; // [rsp+48h] [rbp-28h]
  __int64 **v53; // [rsp+50h] [rbp-20h] BYREF
  __int64 v54; // [rsp+58h] [rbp-18h]
  __int64 *v55; // [rsp+60h] [rbp-10h]
  int v56; // [rsp+68h] [rbp-8h]
  int v57; // [rsp+6Ch] [rbp-4h]
  struct Ofc::CProxyPtrImpl *v58; // [rsp+B8h] [rbp+48h] BYREF
  NetUI::BaseValue *v59; // [rsp+C0h] [rbp+50h] BYREF

  *(_QWORD *)(a1 + 24) = a1;
  Ofc::CProxyPtrImpl::InitAsTWeakPtrThisProxy((Ofc::CProxyPtrImpl *)a1);
  *(_QWORD *)(a1 + 32) = a2;
  v9 = *a3;
  if ( *(_DWORD *)(*a3 + 4) != 0x80000000 )
    _InterlockedIncrement((volatile signed __int32 *)(v9 + 4));
  *(_QWORD *)(a1 + 40) = v9;
  v10 = (_QWORD *)(a1 + 48);
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  v11 = 2;
  do
  {
    *(_QWORD *)(a1 + 64) = 0;
    *(_QWORD *)(a1 + 72) = 0;
    --v11;
  }
  while ( v11 );
  v12 = &`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
  *(_QWORD *)(a1 + 80) = &`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
  if ( !*(_QWORD *)(*a3 + 16) )
    goto LABEL_77;
  if ( *v10 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 16LL))(*v10);
  *v10 = 0;
  if ( !FlexUI::MsoCreateFlexDataSource((FlexUI *)0x13C9, 134221568, a1 + 48, v8) )
  {
LABEL_77:
    MsoShipAssertTagProc(591938319);
    Ofc::CAbortException::ThrowTag(0, 591938318);
    __debugbreak();
  }
  v49 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*(struct Ofc::CProxyPtrImpl **)(a1 + 40));
  v13 = *v10;
  if ( *v10 )
  {
    v58 = 0;
    FlexUI::FlexValue::CreateString(*a4, (struct FlexUI::FlexValueSP *)&v58);
    if ( v58 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v13 + 48LL))(v13, 0, 0);
      if ( v58 )
        NetUI::BaseValue::Release(v58);
    }
  }
  else
  {
    MsoShipAssertTagProc(7997248);
  }
  Checked = Ofc::CProxyPtrImpl::GetChecked(v49);
  if ( (*(unsigned __int8 (__fastcall **)(void *))(*(_QWORD *)Checked + 136LL))(Checked) )
  {
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64, __int64, char))(*(_QWORD *)*v10 + 64LL))(*v10, 0, 5, 1, 1);
    LOBYTE(v47) = 1;
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64, __int64, int))(*(_QWORD *)*v10 + 64LL))(*v10, 0, 6, 1, v47);
  }
  else
  {
    v15 = *v10;
    if ( *v10 )
    {
      v58 = 0;
      FlexUI::FlexValue::CreateBoolean(1, (struct FlexUI::FlexValueSP *)&v58);
      if ( v58 )
      {
        (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v15 + 48LL))(v15, 0, 2);
        if ( v58 )
          NetUI::BaseValue::Release(v58);
      }
    }
    else
    {
      MsoShipAssertTagProc(7997248);
    }
  }
  v16 = Ofc::CProxyPtrImpl::GetChecked(v49);
  if ( (*(unsigned __int8 (__fastcall **)(void *))(*(_QWORD *)v16 + 144LL))(v16) )
  {
    LOBYTE(v46) = 1;
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64, __int64, int))(*(_QWORD *)*v10 + 64LL))(*v10, 0, 3, 1, v46);
    LOBYTE(v48) = 1;
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64, __int64, int))(*(_QWORD *)*v10 + 64LL))(*v10, 0, 4, 1, v48);
  }
  v51 = 0;
  v52 = 0;
  v17 = Ofc::CProxyPtrImpl::GetChecked(v49);
  (*(void (__fastcall **)(void *, __int64 **))(*(_QWORD *)v17 + 8LL))(v17, &v51);
  if ( (int)v52 <= 0 )
    goto LABEL_59;
  v20 = *v10;
  if ( !*v10 )
  {
    MsoShipAssertTagProc(7997250);
    goto LABEL_39;
  }
  v59 = 0;
  v58 = 0;
  v21 = FlexUI::FlexList::Create(v52, &v58);
  v22 = v58;
  if ( !v21 )
  {
    if ( !v58 )
      goto LABEL_29;
    goto LABEL_28;
  }
  FlexUI::FlexValue::CreateList(v58, (struct FlexUI::FlexValueSP *)&v59);
  if ( !v59 )
  {
    v22 = v58;
    if ( !v58 )
      goto LABEL_39;
LABEL_28:
    v58 = 0;
    (*(void (__fastcall **)(struct Ofc::CProxyPtrImpl *))(*(_QWORD *)v22 + 16LL))(v22);
LABEL_29:
    if ( v59 )
      NetUI::BaseValue::Release(v59);
    goto LABEL_39;
  }
  v23 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v20 + 48LL))(v20, 0, 1);
  v24 = v58;
  if ( v58 )
  {
    v58 = 0;
    (*(void (__fastcall **)(struct Ofc::CProxyPtrImpl *))(*(_QWORD *)v24 + 16LL))(v24);
  }
  if ( v59 )
    NetUI::BaseValue::Release(v59);
  if ( !v23 )
  {
LABEL_39:
    MsoShipAssertTagProc(591938317);
    Ofc::CAbortException::ThrowTag(0, 591938316);
    __debugbreak();
  }
  v25 = *v10;
  if ( !*v10 )
  {
    MsoShipAssertTagProc(7997216);
LABEL_42:
    v26 = 0;
    v58 = 0;
    goto LABEL_46;
  }
  v58 = 0;
  (*(void (__fastcall **)(__int64, __int64, struct Ofc::CProxyPtrImpl **))(*(_QWORD *)v25 + 40LL))(v25, 1, &v58);
  if ( !v58 )
    goto LABEL_42;
  v26 = (struct Ofc::CProxyPtrImpl *)*((_QWORD *)v58 + 1);
  NetUI::BaseValue::Release(v58);
  v58 = v26;
  if ( v26 )
    (*(void (__fastcall **)(struct Ofc::CProxyPtrImpl *))(*(_QWORD *)v26 + 8LL))(v26);
LABEL_46:
  v53 = &v51;
  v54 = 0;
  v27 = v51;
  v57 = HIDWORD(v52);
  while ( 1 )
  {
    v56 = 0;
    v55 = v27;
    if ( !v27 )
      break;
    if ( *((_DWORD *)v27 + 4) )
    {
      v54 = v27[3];
      break;
    }
    v27 = (__int64 *)*v27;
  }
  v50 = (struct Ofc::CProxyPtrImpl *)&`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
  while ( 1 )
  {
    ItemAddr = (struct Ofc::CProxyPtrImpl **)Ofc::CListIterImpl::NextItemAddr((Ofc::CListIterImpl *)&v53);
    if ( !ItemAddr )
      break;
    Ofc::CProxyPtrImpl::WeakAssign(&v50, *ItemAddr);
    v31 = (NetUI::BaseValue *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x40, v29, v30);
    v59 = v31;
    if ( v31 )
      v34 = (_QWORD *)Art::SelectionPaneNode::SelectionPaneNode(
                        (__int64)v31,
                        *(_QWORD *)(a1 + 32),
                        (__int64 *)&v50,
                        v33);
    else
      v34 = 0;
    FlexUI::RefCountTypeListSP<FlexUI::IDataSource,FlexUI::TypeTraits<FlexUI::IDataSource *>>::Add(&v58, v32, v34[2]);
    *Ofc::CListImpl::NewTail((Ofc::CListImpl *)(a1 + 64)) = v34;
  }
  v58 = (struct Ofc::CProxyPtrImpl *)&`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
  Ofc::CProxyPtrImpl::WeakMoveAssign(&v50, &v58);
  Ofc::CProxyPtrImpl::DtorWeakRelease(&v58);
  Ofc::CProxyPtrImpl::DtorWeakRelease(&v50);
  if ( v26 )
    (*(void (__fastcall **)(struct Ofc::CProxyPtrImpl *))(*(_QWORD *)v26 + 16LL))(v26);
LABEL_59:
  v35 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x30, v18, v19);
  v36 = v35;
  if ( v35 )
  {
    v35[4] = v35 + 1;
    Ofc::CProxyPtrImpl::InitAsTWeakPtrThisProxy((Ofc::CProxyPtrImpl *)(v35 + 1));
    *v36 = &Art::SelectionPaneUpdater<Art::SelectionPaneTree>::`vftable';
    v36[5] = a1;
  }
  else
  {
    v36 = 0;
  }
  if ( v36 )
  {
    v12 = (int *)v36[4];
    _InterlockedExchange(v12, 1);
    *((_QWORD *)v12 + 1) = EncodePointer(Ofc::TDestructFromProxy<Dr::ScrapOwningCutCopyHandler const>);
    *((_QWORD *)v12 + 2) = v36;
  }
  v58 = (struct Ofc::CProxyPtrImpl *)v12;
  Ofc::CProxyPtrImpl::StrongMoveAssign((struct Ofc::CProxyPtrImpl **)(a1 + 80), &v58);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v58);
  v37 = Ofc::CProxyPtrImpl::GetChecked(v49);
  (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)v37 + 24LL))(v37, a1 + 80);
  v40 = (Art::SelectionPaneBaseListener *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x18, v38, v39);
  v41 = v40;
  if ( v40 )
  {
    *((_BYTE *)v40 + 8) = 0;
    *((_DWORD *)v40 + 3) = 1;
    *(_QWORD *)v40 = &Art::SelectionPaneTreeListener::`vftable';
    *((_QWORD *)v40 + 2) = a1;
  }
  else
  {
    v41 = 0;
  }
  v42 = *(Art::SelectionPaneBaseListener **)(a1 + 56);
  if ( v42 != v41 )
  {
    if ( v42 )
      (*(void (__fastcall **)(Art::SelectionPaneBaseListener *))(*(_QWORD *)v42 + 16LL))(v42);
    *(_QWORD *)(a1 + 56) = v41;
    v42 = v41;
  }
  Art::SelectionPaneBaseListener::Connect(v42);
  for ( i = v51; i; i = (__int64 *)*i )
  {
    for ( j = 0; j < *((_DWORD *)i + 4); ++j )
      Ofc::TWeakPtr<Art::SelectionHandleViewElement>::~TWeakPtr<Art::SelectionHandleViewElement>((void *const *)&i[j + 3]);
  }
  Ofc::CListImpl::Reset((Ofc::CListImpl *)&v51);
  Ofc::CListImpl::Reset((Ofc::CListImpl *)&v51);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v49);
  return a1;
}

```

## disassembly

```asm
0x180527ffc  mov     [rsp-38h+arg_18], rbx
0x180528001  mov     [rsp-38h+arg_0], rcx
0x180528006  push    rbp
0x180528007  push    rsi
0x180528008  push    rdi
0x180528009  push    r12
0x18052800b  push    r13
0x18052800d  push    r14
0x18052800f  push    r15
0x180528011  mov     rbp, rsp
0x180528014  sub     rsp, 70h
0x180528018  mov     r15, r9
0x18052801b  mov     r14, r8
0x18052801e  mov     rbx, rdx
0x180528021  mov     rdi, rcx
0x180528024  mov     [rcx+18h], rcx
0x180528028  call    ?InitAsTWeakPtrThisProxy@CProxyPtrImpl@Ofc@@IEAAXXZ; Ofc::CProxyPtrImpl::InitAsTWeakPtrThisProxy(void)
0x18052802d  mov     [rdi+20h], rbx
0x180528031  mov     rcx, [r14]
0x180528034  mov     eax, [rcx+4]
0x180528037  cmp     eax, 80000000h
0x18052803c  jz      short loc_180528044
0x18052803e  xchg    ax, ax
0x180528040  lock inc dword ptr [rcx+4]
0x180528044  mov     [rdi+28h], rcx
0x180528048  lea     rbx, [rdi+30h]
0x18052804c  xor     edx, edx
0x18052804e  mov     [rbx], rdx
0x180528051  mov     [rdi+38h], rdx
0x180528055  lea     eax, [rdx+2]
0x180528058  mov     [rdi+40h], rdx
0x18052805c  mov     [rdi+48h], rdx
0x180528060  sub     rax, 1
0x180528064  jnz     short loc_180528058
0x180528066  lea     r13, [rdi+50h]
0x18052806a  lea     rsi, ?s_proxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4UProxyPtrSentinel@?1??123@KAAEBQEAV23@XZ@B; `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::ProxyPtrSentinel const `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_proxyPtrSentinel
0x180528071  mov     [r13+0], rsi
0x180528075  mov     rax, [r14]
0x180528078  cmp     [rax+10h], rdx
0x18052807c  jz      loc_1805285C0
0x180528082  mov     rcx, [rbx]
0x180528085  test    rcx, rcx
0x180528088  jz      short loc_180528099
0x18052808a  mov     rax, [rcx]
0x18052808d  mov     rax, [rax+10h]
0x180528091  call    cs:__guard_dispatch_icall_fptr
0x180528097  xor     edx, edx
0x180528099  mov     [rbx], rdx
0x18052809c  mov     r8, rbx
0x18052809f  mov     edx, 8000F00h
0x1805280a4  mov     ecx, 13C9h
0x1805280a9  call    cs:__imp_?MsoCreateFlexDataSource@FlexUI@@YA_NHIPEAPEAUIDataSource@1@@Z; FlexUI::MsoCreateFlexDataSource(int,uint,FlexUI::IDataSource * *)
0x1805280af  test    al, al
0x1805280b1  jz      loc_1805285C0
0x1805280b7  mov     rcx, [rdi+28h]; struct Ofc::CProxyPtrImpl *
0x1805280bb  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1805280c0  mov     [rbp+var_40], rax
0x1805280c4  mov     r14, [rbx]
0x1805280c7  test    r14, r14
0x1805280ca  jnz     short loc_1805280DC
0x1805280cc  mov     ecx, 7A0740h
0x1805280d1  call    cs:__imp_MsoShipAssertTagProc
0x1805280d7  xor     r15d, r15d
0x1805280da  jmp     short loc_180528121
0x1805280dc  mov     [rbp+arg_8], 0
0x1805280e4  lea     rdx, [rbp+arg_8]
0x1805280e8  mov     rcx, [r15]
0x1805280eb  call    cs:__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateString(wchar_t const *,FlexUI::FlexValueSP &)
0x1805280f1  mov     r9, [rbp+arg_8]
0x1805280f5  xor     r15d, r15d
0x1805280f8  test    r9, r9
0x1805280fb  jz      short loc_180528121
0x1805280fd  mov     rax, [r14]
0x180528100  xor     r8d, r8d
0x180528103  xor     edx, edx
0x180528105  mov     rcx, r14
0x180528108  mov     rax, [rax+30h]
0x18052810c  call    cs:__guard_dispatch_icall_fptr
0x180528112  mov     rcx, [rbp+arg_8]
0x180528116  test    rcx, rcx
0x180528119  jz      short loc_180528121
0x18052811b  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x180528121  mov     rcx, [rbp+var_40]; this
0x180528125  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18052812a  mov     rdx, rax
0x18052812d  mov     rcx, [rax]
0x180528130  mov     rax, [rcx+88h]
0x180528137  mov     rcx, rdx
0x18052813a  call    cs:__guard_dispatch_icall_fptr
0x180528140  test    al, al
0x180528142  jz      short loc_180528184
0x180528144  mov     rcx, [rbx]
0x180528147  mov     rax, [rcx]
0x18052814a  mov     byte ptr [rsp+70h+var_50], 1
0x18052814f  xor     edx, edx
0x180528151  lea     r9d, [rdx+1]
0x180528155  lea     r8d, [rdx+5]
0x180528159  mov     rax, [rax+40h]
0x18052815d  call    cs:__guard_dispatch_icall_fptr
0x180528163  mov     rcx, [rbx]
0x180528166  mov     rax, [rcx]
0x180528169  mov     byte ptr [rsp+70h+var_50], 1
0x18052816e  xor     edx, edx
0x180528170  lea     r9d, [rdx+1]
0x180528174  lea     r8d, [rdx+6]
0x180528178  mov     rax, [rax+40h]
0x18052817c  call    cs:__guard_dispatch_icall_fptr
0x180528182  jmp     short loc_1805281D7
0x180528184  mov     r14, [rbx]
0x180528187  test    r14, r14
0x18052818a  jnz     short loc_180528199
0x18052818c  mov     ecx, 7A0740h
0x180528191  call    cs:__imp_MsoShipAssertTagProc
0x180528197  jmp     short loc_1805281D7
0x180528199  mov     [rbp+arg_8], r15
0x18052819d  lea     rdx, [rbp+arg_8]
0x1805281a1  mov     cl, 1
0x1805281a3  call    cs:__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateBoolean(bool,FlexUI::FlexValueSP &)
0x1805281a9  mov     r9, [rbp+arg_8]
0x1805281ad  test    r9, r9
0x1805281b0  jz      short loc_1805281D7
0x1805281b2  mov     rax, [r14]
0x1805281b5  xor     edx, edx
0x1805281b7  lea     r8d, [rdx+2]
0x1805281bb  mov     rcx, r14
0x1805281be  mov     rax, [rax+30h]
0x1805281c2  call    cs:__guard_dispatch_icall_fptr
0x1805281c8  mov     rcx, [rbp+arg_8]
0x1805281cc  test    rcx, rcx
0x1805281cf  jz      short loc_1805281D7
0x1805281d1  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1805281d7  mov     rcx, [rbp+var_40]; this
0x1805281db  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1805281e0  mov     rdx, rax
0x1805281e3  mov     rcx, [rax]
0x1805281e6  mov     rax, [rcx+90h]
0x1805281ed  mov     rcx, rdx
0x1805281f0  call    cs:__guard_dispatch_icall_fptr
0x1805281f6  test    al, al
0x1805281f8  jz      short loc_180528238
0x1805281fa  mov     rcx, [rbx]
0x1805281fd  mov     rax, [rcx]
0x180528200  mov     byte ptr [rsp+70h+var_50], 1
0x180528205  xor     edx, edx
0x180528207  lea     r9d, [rdx+1]
0x18052820b  lea     r8d, [rdx+3]
0x18052820f  mov     rax, [rax+40h]
0x180528213  call    cs:__guard_dispatch_icall_fptr
0x180528219  mov     rcx, [rbx]
0x18052821c  mov     rax, [rcx]
0x18052821f  mov     byte ptr [rsp+70h+var_50], 1
0x180528224  xor     edx, edx
0x180528226  lea     r9d, [rdx+1]
0x18052822a  lea     r8d, [rdx+4]
0x18052822e  mov     rax, [rax+40h]
0x180528232  call    cs:__guard_dispatch_icall_fptr
0x180528238  mov     [rbp+var_30], r15
0x18052823c  mov     [rbp+var_28], 0
0x180528244  mov     rcx, [rbp+var_40]; this
0x180528248  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18052824d  mov     r8, rax
0x180528250  mov     rcx, [rax]
0x180528253  mov     rax, [rcx+8]
0x180528257  lea     rdx, [rbp+var_30]
0x18052825b  mov     rcx, r8
0x18052825e  call    cs:__guard_dispatch_icall_fptr
0x180528264  mov     ecx, dword ptr [rbp+var_28]
0x180528267  test    ecx, ecx
0x180528269  jle     loc_180528476
0x18052826f  mov     r14, [rbx]
0x180528272  test    r14, r14
0x180528275  jnz     short loc_180528287
0x180528277  mov     ecx, 7A0742h
0x18052827c  call    cs:__imp_MsoShipAssertTagProc
0x180528282  jmp     loc_18052832D
0x180528287  mov     [rbp+arg_10], r15
0x18052828b  mov     [rbp+arg_8], r15
0x18052828f  lea     rdx, [rbp+arg_8]
0x180528293  call    cs:__imp_?Create@FlexList@FlexUI@@SA_NIPEAPEAV12@@Z; FlexUI::FlexList::Create(uint,FlexUI::FlexList * *)
0x180528299  mov     rcx, [rbp+arg_8]
0x18052829d  test    al, al
0x18052829f  jnz     short loc_1805282C8
0x1805282a1  test    rcx, rcx
0x1805282a4  jz      short loc_1805282B7
0x1805282a6  mov     [rbp+arg_8], r15
0x1805282aa  mov     rax, [rcx]
0x1805282ad  mov     rax, [rax+10h]
0x1805282b1  call    cs:__guard_dispatch_icall_fptr
0x1805282b7  mov     rcx, [rbp+arg_10]
0x1805282bb  test    rcx, rcx
0x1805282be  jz      short loc_18052832D
0x1805282c0  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1805282c6  jmp     short loc_18052832D
0x1805282c8  lea     rdx, [rbp+arg_10]
0x1805282cc  call    cs:__imp_?CreateList@FlexValue@FlexUI@@SA_NPEAUIFlexList@2@AEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateList(FlexUI::IFlexList *,FlexUI::FlexValueSP &)
0x1805282d2  mov     r9, [rbp+arg_10]
0x1805282d6  test    r9, r9
0x1805282d9  jnz     short loc_1805282E6
0x1805282db  mov     rcx, [rbp+arg_8]
0x1805282df  test    rcx, rcx
0x1805282e2  jz      short loc_18052832D
0x1805282e4  jmp     short loc_1805282A6
0x1805282e6  mov     rax, [r14]
0x1805282e9  xor     edx, edx
0x1805282eb  lea     r8d, [rdx+1]
0x1805282ef  mov     rcx, r14
0x1805282f2  mov     rax, [rax+30h]
0x1805282f6  call    cs:__guard_dispatch_icall_fptr
0x1805282fc  mov     r14b, al
0x1805282ff  mov     rcx, [rbp+arg_8]
0x180528303  test    rcx, rcx
0x180528306  jz      short loc_180528319
0x180528308  mov     [rbp+arg_8], r15
0x18052830c  mov     rdx, [rcx]
0x18052830f  mov     rax, [rdx+10h]
0x180528313  call    cs:__guard_dispatch_icall_fptr
0x180528319  mov     rcx, [rbp+arg_10]
0x18052831d  test    rcx, rcx
0x180528320  jz      short loc_180528328
0x180528322  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x180528328  test    r14b, r14b
0x18052832b  jnz     short loc_180528345
0x18052832d  mov     ecx, 2348430Dh
0x180528332  call    cs:__imp_MsoShipAssertTagProc
0x180528338  mov     edx, 2348430Ch
0x18052833d  xor     ecx, ecx
0x18052833f  call    ?ThrowTag@CAbortException@Ofc@@SAXW4ExcAbortStrategy@2@K@Z; Ofc::CAbortException::ThrowTag(Ofc::ExcAbortStrategy,ulong)
0x180528344  int     3; Trap to Debugger
0x180528345  mov     rcx, [rbx]
0x180528348  test    rcx, rcx
0x18052834b  jnz     short loc_180528361
0x18052834d  mov     ecx, 7A0720h
0x180528352  call    cs:__imp_MsoShipAssertTagProc
0x180528358  mov     rbx, r15
0x18052835b  mov     [rbp+arg_8], rbx
0x18052835f  jmp     short loc_1805283A8
0x180528361  mov     [rbp+arg_8], r15
0x180528365  mov     rax, [rcx]
0x180528368  lea     r8, [rbp+arg_8]
0x18052836c  mov     edx, 1
0x180528371  mov     rax, [rax+28h]
0x180528375  call    cs:__guard_dispatch_icall_fptr
0x18052837b  mov     rcx, [rbp+arg_8]
0x18052837f  test    rcx, rcx
0x180528382  jz      short loc_180528358
0x180528384  mov     rbx, [rcx+8]
0x180528388  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x18052838e  mov     [rbp+arg_8], rbx
0x180528392  test    rbx, rbx
0x180528395  jz      short loc_1805283A8
0x180528397  mov     rax, [rbx]
0x18052839a  mov     rcx, rbx
0x18052839d  mov     rax, [rax+8]
0x1805283a1  call    cs:__guard_dispatch_icall_fptr
0x1805283a7  nop
0x1805283a8  lea     rax, [rbp+var_30]
0x1805283ac  mov     [rbp+var_20], rax
0x1805283b0  mov     [rbp+var_18], r15
0x1805283b4  mov     rcx, [rbp+var_30]
0x1805283b8  mov     eax, dword ptr [rbp+var_28+4]
0x1805283bb  mov     [rbp+var_4], eax
0x1805283be  mov     [rbp+var_8], r15d
0x1805283c2  mov     [rbp+var_10], rcx
0x1805283c6  test    rcx, rcx
0x1805283c9  jz      short loc_1805283DE
0x1805283cb  cmp     [rcx+10h], r15d
0x1805283cf  ja      short loc_1805283D6
0x1805283d1  mov     rcx, [rcx]
0x1805283d4  jmp     short loc_1805283BE
0x1805283d6  mov     rax, [rcx+18h]
0x1805283da  mov     [rbp+var_18], rax
0x1805283de  mov     [rbp+var_38], rsi
0x1805283e2  lea     rcx, [rbp+var_20]; this
0x1805283e6  call    ?NextItemAddr@CListIterImpl@Ofc@@IEAAPEBQEAXXZ; Ofc::CListIterImpl::NextItemAddr(void)
0x1805283eb  lea     rcx, [rbp+var_38]; struct Ofc::CProxyPtrImpl **
0x1805283ef  test    rax, rax
0x1805283f2  jz      short loc_180528442
0x1805283f4  mov     rdx, [rax]; struct Ofc::CProxyPtrImpl *
0x1805283f7  call    ?WeakAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::WeakAssign(Ofc::CProxyPtrImpl * *,Ofc::CProxyPtrImpl *)
0x1805283fc  mov     ecx, 40h ; '@'; this
0x180528401  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x180528406  mov     [rbp+arg_10], rax
0x18052840a  test    rax, rax
0x18052840d  jz      short loc_180528424
0x18052840f  lea     r8, [rbp+var_38]
0x180528413  mov     rdx, [rdi+20h]
0x180528417  mov     rcx, rax
0x18052841a  call    ??0SelectionPaneNode@Art@@QEAA@AEAVSelectionPane@1@AEBV?$TWeakPtr@VISelectionPaneShapeTreeNode@Art@@@Ofc@@@Z; Art::SelectionPaneNode::SelectionPaneNode(Art::SelectionPane &,Ofc::TWeakPtr<Art::ISelectionPaneShapeTreeNode> const &)
0x18052841f  mov     r14, rax
0x180528422  jmp     short loc_180528427
0x180528424  mov     r14, r15
0x180528427  mov     r8, [r14+10h]
0x18052842b  lea     rcx, [rbp+arg_8]
0x18052842f  call    ?Add@?$RefCountTypeListSP@UIDataSource@FlexUI@@V?$TypeTraits@PEAUIDataSource@FlexUI@@@2@@FlexUI@@QEAA_NPEAXPEAUIDataSource@2@@Z; FlexUI::RefCountTypeListSP<FlexUI::IDataSource,FlexUI::TypeTraits<FlexUI::IDataSource *>>::Add(void *,FlexUI::IDataSource *)
0x180528434  lea     rcx, [rdi+40h]; this
0x180528438  call    ?NewTail@CListImpl@Ofc@@IEAAPEAPEAXXZ; Ofc::CListImpl::NewTail(void)
0x18052843d  mov     [rax], r14
0x180528440  jmp     short loc_1805283E2
0x180528442  mov     [rbp+arg_8], rsi
0x180528446  lea     rdx, [rbp+arg_8]; struct Ofc::CProxyPtrImpl **
  ... truncated ...
```
