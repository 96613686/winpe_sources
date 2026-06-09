# UIItem::SetItem(IItem *)

- ea: `0x18002ee70`
- end: `0x18002f354`
- name: `?SetItem@UIItem@@UEAAJPEAUIItem@@@Z`
- size: `1252`
- prototype: `__int64 __fastcall(UIItem *__hidden this, struct IItem *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c6f0`
- `0x18002d5a4`

## callees

- `0x18001a1e0`
- `0x18001b8d0`
- `0x18001c560`
- `0x18002ee70`
- `0x18002f35c`
- `0x1800340a0`
- `0x18013fcac`
- `0x1801e2cec`
- `0x1801e4538`
- `0x180210010`

## import_xrefs

- `SHCORE!SHCreateThread` at `0x18002f33f`
- `SHCORE!SHCreateThread` at `0x18002f33f`
- `SHLWAPI!SHRegGetBoolUSValueW` at `0x18002f0e5`
- `SHLWAPI!SHRegGetBoolUSValueW` at `0x18002f0e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f0bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f1b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f0bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f1b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002f2d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002f2d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002f2cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002f2dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002f2cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002f2dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f349`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f349`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002f305`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002f305`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002f2c1`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002f2c1`
- `DUI70!?GetTopLevel@Element@DirectUI@@QEAAPEAV12@XZ` at `0x18002efe7`
- `DUI70!?GetTopLevel@Element@DirectUI@@QEAAPEAV12@XZ` at `0x18002efe7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UIItem::SetItem(UIItem *this, struct IItem *a2)
{
  unsigned int v4; // r15d
  struct IItem *v5; // rcx
  struct DirectUI::IClassInfo *v6; // rdi
  __int64 v7; // rcx
  struct DirectUI::IClassInfo *v8; // rdi
  struct DirectUI::Element *TopLevel; // rax
  struct DirectUI::Element *v10; // rdi
  __int64 v11; // rax
  int v12; // edi
  int v14; // eax
  _QWORD **v15; // rax
  _QWORD **v16; // r12
  _QWORD **v17; // r13
  __int64 v18; // rcx
  HANDLE CurrentProcess; // rsi
  HANDLE CurrentThread; // rdi
  HANDLE v21; // rax
  int lpData; // [rsp+20h] [rbp-50h]
  _QWORD pData[4]; // [rsp+40h] [rbp-30h] BYREF
  char v24; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  int Data; // [rsp+B0h] [rbp+40h] BYREF
  HANDLE TargetHandle; // [rsp+C0h] [rbp+50h] BYREF
  _QWORD *v28; // [rsp+C8h] [rbp+58h] BYREF

  *((_DWORD *)this + 64) = 0;
  if ( !*((_DWORD *)this + 62) )
  {
    Data = 0;
    *((_DWORD *)this + 62) = 1;
    pData[2] = this;
    pData[3] = &Data;
    v24 = 1;
    v4 = 1;
    v5 = (struct IItem *)*((_QWORD *)this + 27);
    if ( v5 && a2 )
    {
      if ( v5 == a2 )
        goto LABEL_20;
      TargetHandle = 0;
      v28 = 0;
      if ( (**(int (__fastcall ***)(struct IItem *, GUID *, HANDLE *))v5)(
             v5,
             &GUID_00000000_0000_0000_c000_000000000046,
             &TargetHandle) >= 0 )
      {
        if ( (**(int (__fastcall ***)(struct IItem *, GUID *, void **))a2)(
               a2,
               &GUID_00000000_0000_0000_c000_000000000046,
               (void **)&v28) < 0 )
        {
          (*(void (__fastcall **)(HANDLE))(*(_QWORD *)TargetHandle + 16LL))(TargetHandle);
        }
        else
        {
          (*(void (__fastcall **)(_QWORD *))(*v28 + 16LL))(v28);
          (*(void (__fastcall **)(HANDLE))(*(_QWORD *)TargetHandle + 16LL))(TargetHandle);
          if ( TargetHandle == v28 )
            goto LABEL_20;
        }
      }
    }
    if ( *((_QWORD *)this + 27) )
    {
      v6 = UIGroupItem::Class;
      if ( (struct DirectUI::IClassInfo *)(*(__int64 (__fastcall **)(UIItem *))(*(_QWORD *)this + 280LL))(this) != v6 )
      {
        v7 = *((_QWORD *)this + 28);
        if ( v7 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 40LL))(v7);
          *((_QWORD *)this + 28) = 0;
        }
      }
      ATL::CComPtr<IShellSearchTarget>::operator=((char *)this + 216, 0);
      if ( a2 )
      {
        v4 = 3;
LABEL_14:
        v8 = UIGroupItem::Class;
        if ( (struct DirectUI::IClassInfo *)(*(__int64 (__fastcall **)(UIItem *))(*(_QWORD *)this + 280LL))(this) != v8 )
        {
          *((_QWORD *)this + 28) = 0;
          TopLevel = DirectUI::Element::GetTopLevel(this);
          v10 = TopLevel;
          if ( !TopLevel
            || (v11 = (*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)TopLevel + 280LL))(TopLevel),
                !(*(unsigned __int8 (__fastcall **)(__int64, struct DirectUI::IClassInfo *))(*(_QWORD *)v11 + 80LL))(
                   v11,
                   UIItemsView::Class)) )
          {
            v12 = -2147418113;
LABEL_18:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1AF,
              (unsigned int)"shell\\explorerframe\\itemsview\\uiitem.cpp",
              (const char *)(unsigned int)v12,
              lpData);
            *((_DWORD *)this + 62) = Data;
            return (unsigned int)v12;
          }
          v28 = (_QWORD *)(*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)v10 + 360LL))(v10);
          ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(&TargetHandle);
          ATL::CComPtrBase<IEventQueue>::CopyTo((char *)v10 + 648, &TargetHandle);
          v15 = (_QWORD **)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
          v16 = v15;
          pData[0] = v15;
          if ( v15 )
          {
            *((_DWORD *)v15 + 14) = 1;
            ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(v15 + 8);
            *v16 = &CItemEventSinkWrapper::`vftable'{for `CSinkWrapperBase'};
            v17 = v16 + 9;
            v16[9] = &CItemEventSinkWrapper::`vftable'{for `IItemEventSink'};
            ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(v16 + 10);
            v16[12] = 0;
            ATL::CComPtr<IShellSearchTarget>::operator=(v18, a2);
            *((_DWORD *)v16 + 10) = GetCurrentThreadId();
            v16[4] = this;
            v16[2] = ClassDispositionWrapper<UIItem,ItemEventParams *,&public: long UIItem::GetEventActionCB(IUnknown *,int,ItemEventParams *,enum tagEVENTACTION *)>;
            v16[3] = ClassCallbackWrapper<UIItem,ItemEventParams *,&public: long UIItem::OnItemEventCB(IUnknown *,ItemEventParams *)>;
            v16[6] = v28;
            ATL::CComPtr<IShellSearchTarget>::operator=(v16 + 8, TargetHandle);
            v12 = -2147418113;
            if ( !*((_DWORD *)v16 + 2) )
            {
              if ( !v16 )
                v17 = 0;
              v12 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD **))(*v16[10] + 96LL))(v16[10], v17);
              if ( v12 >= 0 )
              {
                ((void (__fastcall *)(_QWORD **))(*v16)[1])(v16);
                *((_QWORD *)this + 28) = v16;
              }
            }
            ((void (__fastcall *)(_QWORD **))(*v16)[2])(v16);
          }
          else
          {
            v12 = -2147024882;
          }
          ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(&TargetHandle);
          if ( v12 < 0 )
            goto LABEL_18;
        }
        ATL::CComPtr<IShellSearchTarget>::operator=((char *)this + 216, a2);
      }
    }
    else if ( a2 )
    {
      goto LABEL_14;
    }
LABEL_20:
    if ( *((_QWORD *)this + 27) )
    {
      v14 = (*(__int64 (__fastcall **)(UIItem *, _QWORD))(*(_QWORD *)this + 472LL))(this, v4);
      if ( v14 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1B7,
          (unsigned int)"shell\\explorerframe\\itemsview\\uiitem.cpp",
          (const char *)(unsigned int)v14,
          lpData);
    }
    *((_DWORD *)this + 62) = Data;
    return 0;
  }
  g_dwReentrantThreadId = GetCurrentThreadId();
  g_ReentrantCheck = 5;
  if ( !SHRegGetBoolUSValueW(
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced",
          L"ShellViewReentered",
          0,
          0) )
  {
    Data = 1;
    RegSetKeyValueW(
      HKEY_CURRENT_USER,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced",
      L"ShellViewReentered",
      4u,
      &Data,
      4u);
    TargetHandle = 0;
    CurrentProcess = GetCurrentProcess();
    CurrentThread = GetCurrentThread();
    v21 = GetCurrentProcess();
    if ( DuplicateHandle(v21, CurrentThread, CurrentProcess, &TargetHandle, 0x1FFFFFu, 1, 0) )
    {
      pData[0] = TargetHandle;
      pData[1] = ComputeStackHash();
      SHCreateThread(
        DirectUI::PatternProvider<UIItemsViewScrollProvider,IScrollProvider,5>::GetProxyCreator,
        pData,
        0x200u,
        s_SendWERForReentrancy);
      CloseHandle(TargetHandle);
    }
  }
  *((_DWORD *)this + 63) = 1;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x18E,
    (unsigned int)"shell\\explorerframe\\itemsview\\uiitem.cpp",
    (const char *)0x8000FFFFLL,
    lpData);
  return 2147549183LL;
}

```

## disassembly

```asm
0x18002ee70  mov     [rsp-38h+arg_8], rbx
0x18002ee75  push    rbp
0x18002ee76  push    rsi
0x18002ee77  push    rdi
0x18002ee78  push    r12
0x18002ee7a  push    r13
0x18002ee7c  push    r14
0x18002ee7e  push    r15
0x18002ee80  mov     rbp, rsp
0x18002ee83  sub     rsp, 70h
0x18002ee87  mov     rsi, rdx
0x18002ee8a  mov     rbx, rcx
0x18002ee8d  xor     r12d, r12d
0x18002ee90  mov     [rcx+100h], r12d
0x18002ee97  mov     eax, [rcx+0F8h]
0x18002ee9d  test    eax, eax
0x18002ee9f  jnz     loc_18002F0BB
0x18002eea5  mov     [rbp+Data], eax
0x18002eea8  mov     dword ptr [rcx+0F8h], 1
0x18002eeb2  mov     [rbp+var_20], rcx
0x18002eeb6  lea     rax, [rbp+Data]
0x18002eeba  mov     [rbp+var_18], rax
0x18002eebe  mov     [rbp+var_10], 1
0x18002eec2  mov     r15d, 1
0x18002eec8  mov     rcx, [rcx+0D8h]
0x18002eecf  test    rcx, rcx
0x18002eed2  jz      short loc_18002EF53
0x18002eed4  test    rdx, rdx
0x18002eed7  jz      short loc_18002EF53
0x18002eed9  cmp     rcx, rdx
0x18002eedc  jz      loc_18002F05C
0x18002eee2  mov     [rbp+TargetHandle], r12
0x18002eee6  mov     [rbp+arg_18], r12
0x18002eeea  mov     rax, [rcx]
0x18002eeed  lea     r8, [rbp+TargetHandle]
0x18002eef1  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18002eef8  mov     rax, [rax]
0x18002eefb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef00  test    eax, eax
0x18002ef02  js      short loc_18002EF53
0x18002ef04  mov     rax, [rsi]
0x18002ef07  lea     r8, [rbp+arg_18]
0x18002ef0b  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18002ef12  mov     rcx, rsi
0x18002ef15  mov     rax, [rax]
0x18002ef18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef1d  test    eax, eax
0x18002ef1f  js      loc_18002F279
0x18002ef25  mov     rcx, [rbp+arg_18]
0x18002ef29  mov     rax, [rcx]
0x18002ef2c  mov     rax, [rax+10h]
0x18002ef30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef35  mov     rcx, [rbp+TargetHandle]
0x18002ef39  mov     rax, [rcx]
0x18002ef3c  mov     rax, [rax+10h]
0x18002ef40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef45  mov     rax, [rbp+arg_18]
0x18002ef49  cmp     [rbp+TargetHandle], rax
0x18002ef4d  jz      loc_18002F05C
0x18002ef53  cmp     qword ptr [rbx+0D8h], 0
0x18002ef5b  jz      loc_18002F053
0x18002ef61  mov     rdi, cs:?Class@UIGroupItem@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * UIGroupItem::Class
0x18002ef68  mov     rax, [rbx]
0x18002ef6b  mov     rcx, rbx
0x18002ef6e  mov     rax, [rax+118h]
0x18002ef75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef7a  cmp     rax, rdi
0x18002ef7d  jz      short loc_18002EF9E
0x18002ef7f  mov     rcx, [rbx+0E0h]
0x18002ef86  test    rcx, rcx
0x18002ef89  jz      short loc_18002EF9E
0x18002ef8b  mov     rax, [rcx]
0x18002ef8e  mov     rax, [rax+28h]
0x18002ef92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef97  mov     [rbx+0E0h], r12
0x18002ef9e  xor     edx, edx
0x18002efa0  lea     rcx, [rbx+0D8h]
0x18002efa7  call    ??4?$CComPtr@UIShellSearchTarget@@@ATL@@QEAAPEAUIShellSearchTarget@@PEAU2@@Z; ATL::CComPtr<IShellSearchTarget>::operator=(IShellSearchTarget *)
0x18002efac  test    rsi, rsi
0x18002efaf  jz      loc_18002F05C
0x18002efb5  mov     r15d, 3
0x18002efbb  mov     rdi, cs:?Class@UIGroupItem@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * UIGroupItem::Class
0x18002efc2  mov     rax, [rbx]
0x18002efc5  mov     rcx, rbx
0x18002efc8  mov     rax, [rax+118h]
0x18002efcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efd4  cmp     rax, rdi
0x18002efd7  jz      loc_18002F25E
0x18002efdd  mov     [rbx+0E0h], r12
0x18002efe4  mov     rcx, rbx
0x18002efe7  call    cs:__imp_?GetTopLevel@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetTopLevel(void)
0x18002efed  mov     rdi, rax
0x18002eff0  test    rax, rax
0x18002eff3  jz      short loc_18002F028
0x18002eff5  mov     rcx, [rax]
0x18002eff8  mov     rax, [rcx+118h]
0x18002efff  mov     rcx, rdi
0x18002f002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f007  mov     r8, rax
0x18002f00a  mov     rcx, [rax]
0x18002f00d  mov     rax, [rcx+50h]
0x18002f011  mov     rdx, cs:?Class@UIItemsView@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * UIItemsView::Class
0x18002f018  mov     rcx, r8
0x18002f01b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f020  test    al, al
0x18002f022  jnz     loc_18002F11E
0x18002f028  mov     edi, 8000FFFFh
0x18002f02d  mov     rcx, [rbp+38h]; this
0x18002f031  mov     r9d, edi; char *
0x18002f034  lea     r8, aShellExplorerf_8; "shell\\explorerframe\\itemsview\\uiitem"...
0x18002f03b  mov     edx, 1AFh; void *
0x18002f040  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f045  nop
0x18002f046  mov     ecx, [rbp+Data]
0x18002f049  mov     [rbx+0F8h], ecx
0x18002f04f  mov     eax, edi
0x18002f051  jmp     short loc_18002F0A3
0x18002f053  test    rsi, rsi
0x18002f056  jnz     loc_18002EFBB
0x18002f05c  cmp     qword ptr [rbx+0D8h], 0
0x18002f064  jz      short loc_18002F098
0x18002f066  mov     rax, [rbx]
0x18002f069  mov     edx, r15d
0x18002f06c  mov     rcx, rbx
0x18002f06f  mov     rax, [rax+1D8h]
0x18002f076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f07b  mov     rcx, [rbp+38h]; this
0x18002f07f  test    eax, eax
0x18002f081  jns     short loc_18002F098
0x18002f083  mov     r9d, eax; char *
0x18002f086  lea     r8, aShellExplorerf_8; "shell\\explorerframe\\itemsview\\uiitem"...
0x18002f08d  mov     edx, 1B7h; void *
0x18002f092  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002f097  nop
0x18002f098  mov     eax, [rbp+Data]
0x18002f09b  mov     [rbx+0F8h], eax
0x18002f0a1  xor     eax, eax
0x18002f0a3  mov     rbx, [rsp+70h+arg_8]
0x18002f0ab  add     rsp, 70h
0x18002f0af  pop     r15
0x18002f0b1  pop     r14
0x18002f0b3  pop     r13
0x18002f0b5  pop     r12
0x18002f0b7  pop     rdi
0x18002f0b8  pop     rsi
0x18002f0b9  pop     rbp
0x18002f0ba  retn
0x18002f0bb  call    cs:__imp_GetCurrentThreadId
0x18002f0c1  mov     cs:?g_dwReentrantThreadId@@3KC, eax; ulong volatile g_dwReentrantThreadId
0x18002f0c7  mov     cs:?g_ReentrantCheck@@3W4REENTRANCYCHECKTHATFAILED@@C, 5; REENTRANCYCHECKTHATFAILED volatile g_ReentrantCheck
0x18002f0d1  xor     r9d, r9d; fDefault
0x18002f0d4  xor     r8d, r8d; fIgnoreHKCU
0x18002f0d7  lea     rdx, ValueName; "ShellViewReentered"
0x18002f0de  lea     rcx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002f0e5  call    cs:__imp_SHRegGetBoolUSValueW
0x18002f0eb  test    eax, eax
0x18002f0ed  jz      loc_18002F28E
0x18002f0f3  mov     dword ptr [rbx+0FCh], 1
0x18002f0fd  mov     rcx, [rbp+38h]; this
0x18002f101  mov     edi, 8000FFFFh
0x18002f106  mov     r9d, edi; char *
0x18002f109  lea     r8, aShellExplorerf_8; "shell\\explorerframe\\itemsview\\uiitem"...
0x18002f110  mov     edx, 18Eh; void *
0x18002f115  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f11a  mov     eax, edi
0x18002f11c  jmp     short loc_18002F0A3
0x18002f11e  mov     rax, [rdi]
0x18002f121  mov     rcx, rdi
0x18002f124  mov     rax, [rax+168h]
0x18002f12b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f130  mov     [rbp+arg_18], rax
0x18002f134  lea     rcx, [rbp+TargetHandle]; void *
0x18002f138  call    ??0?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(void)
0x18002f13d  nop
0x18002f13e  lea     rcx, [rdi+288h]
0x18002f145  lea     rdx, [rbp+TargetHandle]
0x18002f149  call    ?CopyTo@?$CComPtrBase@VIEventQueue@@@ATL@@QEAAJPEAPEAVIEventQueue@@@Z; ATL::CComPtrBase<IEventQueue>::CopyTo(IEventQueue * *)
0x18002f14e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002f155  mov     ecx, 68h ; 'h'; unsigned __int64
0x18002f15a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002f15f  mov     r12, rax
0x18002f162  mov     [rbp+pData], rax
0x18002f166  test    rax, rax
0x18002f169  jz      loc_18002F272
0x18002f16f  mov     dword ptr [rax+38h], 1
0x18002f176  lea     rcx, [rax+40h]; void *
0x18002f17a  call    ??0?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(void)
0x18002f17f  lea     rcx, ??_7CItemEventSinkWrapper@@6BCSinkWrapperBase@@@; const CItemEventSinkWrapper::`vftable'{for `CSinkWrapperBase'}
0x18002f186  mov     [r12], rcx
0x18002f18a  lea     r13, [r12+48h]
0x18002f18f  lea     rax, ??_7CItemEventSinkWrapper@@6BIItemEventSink@@@; const CItemEventSinkWrapper::`vftable'{for `IItemEventSink'}
0x18002f196  mov     [r13+0], rax
0x18002f19a  lea     rcx, [r12+50h]; void *
0x18002f19f  call    ??0?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(void)
0x18002f1a4  xor     eax, eax
0x18002f1a6  mov     [r12+60h], rax
0x18002f1ab  mov     rdx, rsi
0x18002f1ae  call    ??4?$CComPtr@UIShellSearchTarget@@@ATL@@QEAAPEAUIShellSearchTarget@@PEAU2@@Z; ATL::CComPtr<IShellSearchTarget>::operator=(IShellSearchTarget *)
0x18002f1b3  call    cs:__imp_GetCurrentThreadId
0x18002f1b9  mov     [r12+28h], eax
0x18002f1be  mov     [r12+20h], rbx
0x18002f1c3  lea     rax, ??$ClassDispositionWrapper@VUIItem@@PEAUItemEventParams@@$1?GetEventActionCB@1@QEAAJPEAUIUnknown@@HPEAU2@PEAW4tagEVENTACTION@@@Z@@YAJPEAXPEAUIUnknown@@H0PEAW4tagEVENTACTION@@@Z; ClassDispositionWrapper<UIItem,ItemEventParams *,&UIItem::GetEventActionCB(IUnknown *,int,ItemEventParams *,tagEVENTACTION *)>(void *,IUnknown *,int,void *,tagEVENTACTION *)
0x18002f1ca  mov     [r12+10h], rax
0x18002f1cf  lea     rax, ??$ClassCallbackWrapper@VUIItem@@PEAUItemEventParams@@$1?OnItemEventCB@1@QEAAJPEAUIUnknown@@PEAU2@@Z@@YAJPEAXPEAUIUnknown@@0@Z; ClassCallbackWrapper<UIItem,ItemEventParams *,&UIItem::OnItemEventCB(IUnknown *,ItemEventParams *)>(void *,IUnknown *,void *)
0x18002f1d6  mov     [r12+18h], rax
0x18002f1db  mov     rax, [rbp+arg_18]
0x18002f1df  mov     [r12+30h], rax
0x18002f1e4  mov     rdx, [rbp+TargetHandle]
0x18002f1e8  lea     rcx, [r12+40h]
0x18002f1ed  call    ??4?$CComPtr@UIShellSearchTarget@@@ATL@@QEAAPEAUIShellSearchTarget@@PEAU2@@Z; ATL::CComPtr<IShellSearchTarget>::operator=(IShellSearchTarget *)
0x18002f1f2  mov     edi, 8000FFFFh
0x18002f1f7  lea     r8, [r12+8]
0x18002f1fc  cmp     dword ptr [r8], 0
0x18002f200  jnz     short loc_18002F23C
0x18002f202  mov     rcx, [r12+50h]
0x18002f207  mov     r9, [rcx]
0x18002f20a  xor     eax, eax
0x18002f20c  test    r12, r12
0x18002f20f  cmovz   r13, rax
0x18002f213  mov     rdx, r13
0x18002f216  mov     rax, [r9+60h]
0x18002f21a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f21f  mov     edi, eax
0x18002f221  test    eax, eax
0x18002f223  js      short loc_18002F23C
0x18002f225  mov     rax, [r12]
0x18002f229  mov     rcx, r12
0x18002f22c  mov     rax, [rax+8]
0x18002f230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f235  mov     [rbx+0E0h], r12
0x18002f23c  mov     rax, [r12]
0x18002f240  mov     rcx, r12
0x18002f243  mov     rax, [rax+10h]
0x18002f247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f24c  nop
0x18002f24d  lea     rcx, [rbp+TargetHandle]; void *
0x18002f251  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18002f256  test    edi, edi
0x18002f258  js      loc_18002F02D
0x18002f25e  mov     rdx, rsi
0x18002f261  lea     rcx, [rbx+0D8h]
0x18002f268  call    ??4?$CComPtr@UIShellSearchTarget@@@ATL@@QEAAPEAUIShellSearchTarget@@PEAU2@@Z; ATL::CComPtr<IShellSearchTarget>::operator=(IShellSearchTarget *)
0x18002f26d  jmp     loc_18002F05C
0x18002f272  mov     edi, 8007000Eh
0x18002f277  jmp     short loc_18002F24D
0x18002f279  mov     rcx, [rbp+TargetHandle]
0x18002f27d  mov     rax, [rcx]
0x18002f280  mov     rax, [rax+10h]
0x18002f284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f289  jmp     loc_18002EF53
0x18002f28e  mov     [rbp+Data], 1
0x18002f295  mov     [rsp+70h+cbData], 4; cbData
0x18002f29d  lea     rax, [rbp+Data]
0x18002f2a1  mov     [rsp+70h+lpData], rax; lpData
0x18002f2a6  mov     r9d, 4; dwType
0x18002f2ac  lea     r8, ValueName; "ShellViewReentered"
0x18002f2b3  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002f2ba  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002f2c1  call    cs:__imp_RegSetKeyValueW
0x18002f2c7  mov     [rbp+TargetHandle], r12
0x18002f2cb  call    cs:__imp_GetCurrentProcess
0x18002f2d1  mov     rsi, rax
0x18002f2d4  call    cs:__imp_GetCurrentThread
0x18002f2da  mov     rdi, rax
0x18002f2dd  call    cs:__imp_GetCurrentProcess
0x18002f2e3  mov     [rsp+70h+dwOptions], r12d; dwOptions
0x18002f2e8  mov     [rsp+70h+cbData], 1; bInheritHandle
0x18002f2f0  mov     dword ptr [rsp+70h+lpData], 1FFFFFh; dwDesiredAccess
0x18002f2f8  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x18002f2fc  mov     r8, rsi; hTargetProcessHandle
0x18002f2ff  mov     rdx, rdi; hSourceHandle
0x18002f302  mov     rcx, rax; hSourceProcessHandle
0x18002f305  call    cs:__imp_DuplicateHandle
0x18002f30b  test    eax, eax
0x18002f30d  jz      loc_18002F0F3
0x18002f313  mov     [rbp+var_28], r12
0x18002f317  mov     rax, [rbp+TargetHandle]
0x18002f31b  mov     [rbp+pData], rax
0x18002f31f  call    ?ComputeStackHash@@YAKXZ; ComputeStackHash(void)
0x18002f324  mov     dword ptr [rbp+var_28], eax
0x18002f327  lea     r9, ?s_SendWERForReentrancy@@YAKPEAX@Z; pfnCallback
0x18002f32e  mov     r8d, 200h; flags
0x18002f334  lea     rdx, [rbp+pData]; pData
0x18002f338  lea     rcx, ?GetProxyCreator@?$PatternProvider@VUIItemsViewScrollProvider@@UIScrollProvider@@$04@DirectUI@@UEAAP6APEAVProviderProxy@2@PEAVElement@2@@ZXZ; pfnThreadProc
0x18002f33f  call    cs:__imp_SHCreateThread
0x18002f345  mov     rcx, [rbp+TargetHandle]; hObject
0x18002f349  call    cs:__imp_CloseHandle
0x18002f34f  jmp     loc_18002F0F3
```
