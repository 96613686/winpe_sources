# CDBFolderUI::CreateViewObject(HWND__ *,_GUID const &,void * *)

- ea: `0x180003090`
- end: `0x1800033c9`
- name: `?CreateViewObject@CDBFolderUI@@UEAAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z`
- size: `825`
- prototype: `int(CDBFolderUI *__hidden this, HWND, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003090`
- `0x1800033d0`
- `0x180004640`
- `0x180004a10`
- `0x18001eaa4`
- `0x180021b28`
- `0x180051010`

## import_xrefs

- `SHELL32!__imp_SHCreateShellFolderView` at `0x1800031bb`
- `SHELL32!__imp_SHCreateShellFolderView` at `0x1800031bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800031f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000323b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800032f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003344`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003360`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800031f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000323b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800032f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003344`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003360`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CDBFolderUI::CreateViewObject(CDBFolderUI *this, HWND a2, struct _GUID *a3, IShellView **a4)
{
  __int64 v7; // rax
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rcx
  int v11; // eax
  HRESULT v12; // eax
  __int64 v13; // rdx
  void *v14; // rcx
  void *v16; // rcx
  void **p_ppv; // rcx
  __int64 v18; // rax
  struct IShellFolder3 **v19; // r14
  int v20; // eax
  unsigned int v21; // esi
  int v22; // eax
  unsigned int v23; // esi
  void *v24; // rcx
  int Instance; // eax
  unsigned int v26; // ebx
  void *v27; // rcx
  void *v28; // rcx
  __int64 v29; // rax
  int BgContextMenu; // eax
  unsigned int v31; // ebx
  __int64 v32; // [rsp+20h] [rbp-38h] BYREF
  void *ppv; // [rsp+28h] [rbp-30h] BYREF
  SFV_CREATE pcsfv; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]
  LPVOID pv; // [rsp+A8h] [rbp+50h] BYREF

  *a4 = 0;
  v7 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IShellView.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IShellView.Data1 )
    v7 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IShellView.Data4;
  if ( !v7 )
  {
    v32 = 0;
    v8 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 3))(
           *((_QWORD *)this + 3),
           &GUID_1ac3d9f0_175c_11d1_95be_00609797ea4f,
           &v32);
    v9 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x57D,
        (unsigned int)"shell\\searchfolder\\dbfolder_ui.cpp",
        (const char *)(unsigned int)v8,
        v32);
      v10 = v32;
      if ( v32 )
      {
        v32 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      }
      goto LABEL_16;
    }
    pv = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v32 + 40LL))(v32, &pv);
    v9 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x57F,
        (unsigned int)"shell\\searchfolder\\dbfolder_ui.cpp",
        (const char *)(unsigned int)v11,
        v32);
LABEL_15:
      v14 = pv;
      pv = 0;
      CoTaskMemFree(v14);
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v32);
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x58E,
        (unsigned int)"shell\\searchfolder\\dbfolder_ui.cpp",
        (const char *)v9,
        v32);
      return v9;
    }
    ppv = 0;
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
    v12 = CDBFolderViewCB::s_CreateInstance(
            *((struct IShellFolder3 **)this + 3),
            (const struct _ITEMIDLIST_ABSOLUTE *)pv,
            &GUID_2047e320_f2a9_11ce_ae65_08002b2e1262,
            &ppv);
    v9 = v12;
    if ( v12 < 0 )
    {
      v13 = 1410;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"shell\\searchfolder\\dbfolder_ui.cpp",
        (const char *)(unsigned int)v12,
        v32);
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
      goto LABEL_15;
    }
    *(_QWORD *)&pcsfv.cbSize = 32;
    pcsfv.pshf = (IShellFolder *)*((_QWORD *)this + 3);
    pcsfv.psvOuter = 0;
    pcsfv.psfvcb = (IShellFolderViewCB *)ppv;
    v12 = SHCreateShellFolderView(&pcsfv, a4);
    v9 = v12;
    if ( v12 < 0 )
    {
      v13 = 1413;
      goto LABEL_14;
    }
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
    v16 = pv;
    pv = 0;
    CoTaskMemFree(v16);
    p_ppv = (void **)&v32;
    goto LABEL_18;
  }
  v18 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IShellFolderViewCB.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IShellFolderViewCB.Data1 )
    v18 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IShellFolderViewCB.Data4;
  if ( v18 )
  {
    v29 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IContextMenu.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IContextMenu.Data1 )
      v29 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IContextMenu.Data4;
    if ( v29 )
    {
      return 2147942487LL;
    }
    else
    {
      BgContextMenu = CDBFolderUI::_CreateBgContextMenu(this, a2, a3, (void **)a4);
      v31 = BgContextMenu;
      if ( BgContextMenu >= 0 )
        return 0;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x59B,
        (unsigned int)"shell\\searchfolder\\dbfolder_ui.cpp",
        (const char *)(unsigned int)BgContextMenu,
        v32);
      return v31;
    }
  }
  else
  {
    ppv = 0;
    v19 = (struct IShellFolder3 **)((char *)this + 24);
    v20 = Microsoft::WRL::ComPtr<IShellFolder3>::As<IPersistFolder2>(
            (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 3,
            (__int64 *)&ppv);
    v21 = v20;
    if ( v20 >= 0 )
    {
      pv = 0;
      v22 = (*(__int64 (__fastcall **)(void *, LPVOID *))(*(_QWORD *)ppv + 40LL))(ppv, &pv);
      v23 = v22;
      if ( v22 >= 0 )
      {
        Instance = CDBFolderViewCB::s_CreateInstance(*v19, (const struct _ITEMIDLIST_ABSOLUTE *)pv, a3, (void **)a4);
        v26 = Instance;
        if ( Instance >= 0 )
        {
          v28 = pv;
          pv = 0;
          CoTaskMemFree(v28);
          p_ppv = &ppv;
LABEL_18:
          Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(p_ppv);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x597,
          (unsigned int)"shell\\searchfolder\\dbfolder_ui.cpp",
          (const char *)(unsigned int)Instance,
          v32);
        v27 = pv;
        pv = 0;
        CoTaskMemFree(v27);
        Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
        return v26;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x595,
          (unsigned int)"shell\\searchfolder\\dbfolder_ui.cpp",
          (const char *)(unsigned int)v22,
          v32);
        v24 = pv;
        pv = 0;
        CoTaskMemFree(v24);
        Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
        return v23;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x593,
        (unsigned int)"shell\\searchfolder\\dbfolder_ui.cpp",
        (const char *)(unsigned int)v20,
        v32);
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
      return v21;
    }
  }
}

```

## disassembly

```asm
0x180003090  push    rbp
0x180003092  push    rbx
0x180003093  push    rsi
0x180003094  push    rdi
0x180003095  push    r14
0x180003097  push    r15
0x180003099  mov     rbp, rsp
0x18000309c  sub     rsp, 58h
0x1800030a0  mov     rdi, r9
0x1800030a3  mov     rbx, r8
0x1800030a6  mov     rsi, rcx
0x1800030a9  xor     r15d, r15d
0x1800030ac  mov     [r9], r15
0x1800030af  mov     rax, [r8]
0x1800030b2  sub     rax, qword ptr cs:IID_IShellView.Data1
0x1800030b9  jnz     short loc_1800030C6
0x1800030bb  mov     rax, [r8+8]
0x1800030bf  sub     rax, qword ptr cs:IID_IShellView.Data4
0x1800030c6  test    rax, rax
0x1800030c9  jnz     loc_180003252
0x1800030cf  mov     [rbp+var_38], r15
0x1800030d3  mov     rcx, [rcx+18h]
0x1800030d7  mov     rax, [rcx]
0x1800030da  lea     r8, [rbp+var_38]
0x1800030de  lea     rdx, _GUID_1ac3d9f0_175c_11d1_95be_00609797ea4f
0x1800030e5  mov     rax, [rax]
0x1800030e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030ed  mov     ebx, eax
0x1800030ef  test    eax, eax
0x1800030f1  jns     short loc_18000312B
0x1800030f3  mov     rcx, [rbp+30h]; this
0x1800030f7  mov     r9d, eax; char *
0x1800030fa  lea     r8, aShellSearchfol_0; "shell\\searchfolder\\dbfolder_ui.cpp"
0x180003101  mov     edx, 57Dh; void *
0x180003106  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000310b  nop
0x18000310c  mov     rcx, [rbp+var_38]
0x180003110  test    rcx, rcx
0x180003113  jz      short loc_180003126
0x180003115  mov     [rbp+var_38], r15
0x180003119  mov     rax, [rcx]
0x18000311c  mov     rax, [rax+10h]
0x180003120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003125  nop
0x180003126  jmp     loc_180003202
0x18000312b  mov     [rbp+pv], r15
0x18000312f  mov     rcx, [rbp+var_38]
0x180003133  mov     rax, [rcx]
0x180003136  lea     rdx, [rbp+pv]
0x18000313a  mov     rax, [rax+28h]
0x18000313e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003143  mov     ebx, eax
0x180003145  test    eax, eax
0x180003147  jns     short loc_180003166
0x180003149  mov     rcx, [rbp+30h]; this
0x18000314d  mov     r9d, eax; char *
0x180003150  lea     r8, aShellSearchfol_0; "shell\\searchfolder\\dbfolder_ui.cpp"
0x180003157  mov     edx, 57Fh; void *
0x18000315c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003161  jmp     loc_1800031EA
0x180003166  mov     [rbp+ppv], r15
0x18000316a  lea     rcx, [rbp+ppv]
0x18000316e  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180003173  lea     r9, [rbp+ppv]; ppv
0x180003177  lea     r8, _GUID_2047e320_f2a9_11ce_ae65_08002b2e1262; riid
0x18000317e  mov     rdx, [rbp+pv]; struct _ITEMIDLIST_ABSOLUTE *
0x180003182  mov     rcx, [rsi+18h]; struct IShellFolder3 *
0x180003186  call    ?s_CreateInstance@CDBFolderViewCB@@SAJPEAUIShellFolder3@@PEBU_ITEMIDLIST_ABSOLUTE@@AEBU_GUID@@PEAPEAX@Z; CDBFolderViewCB::s_CreateInstance(IShellFolder3 *,_ITEMIDLIST_ABSOLUTE const *,_GUID const &,void * *)
0x18000318b  mov     ebx, eax
0x18000318d  test    eax, eax
0x18000318f  jns     short loc_180003198
0x180003191  mov     edx, 582h
0x180003196  jmp     short loc_1800031CC
0x180003198  mov     qword ptr [rbp+pcsfv.cbSize], 20h ; ' '
0x1800031a0  mov     rax, [rsi+18h]
0x1800031a4  mov     [rbp+pcsfv.pshf], rax
0x1800031a8  mov     [rbp+pcsfv.psvOuter], r15
0x1800031ac  mov     rax, [rbp+ppv]
0x1800031b0  mov     [rbp+pcsfv.psfvcb], rax
0x1800031b4  mov     rdx, rdi; ppsv
0x1800031b7  lea     rcx, [rbp+pcsfv]; pcsfv
0x1800031bb  call    cs:__imp_SHCreateShellFolderView
0x1800031c1  mov     ebx, eax
0x1800031c3  test    eax, eax
0x1800031c5  jns     short loc_180003229
0x1800031c7  mov     edx, 585h; void *
0x1800031cc  mov     r9d, eax; char *
0x1800031cf  lea     r8, aShellSearchfol_0; "shell\\searchfolder\\dbfolder_ui.cpp"
0x1800031d6  mov     rcx, [rbp+30h]; this
0x1800031da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800031df  nop
0x1800031e0  lea     rcx, [rbp+ppv]
0x1800031e4  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800031e9  nop
0x1800031ea  mov     rcx, [rbp+pv]; pv
0x1800031ee  mov     [rbp+pv], r15
0x1800031f2  call    cs:__imp_CoTaskMemFree
0x1800031f8  nop
0x1800031f9  lea     rcx, [rbp+var_38]
0x1800031fd  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180003202  mov     rcx, [rbp+30h]; this
0x180003206  mov     r9d, ebx; char *
0x180003209  lea     r8, aShellSearchfol_0; "shell\\searchfolder\\dbfolder_ui.cpp"
0x180003210  mov     edx, 58Eh; void *
0x180003215  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000321a  mov     eax, ebx
0x18000321c  add     rsp, 58h
0x180003220  pop     r15
0x180003222  pop     r14
0x180003224  pop     rdi
0x180003225  pop     rsi
0x180003226  pop     rbx
0x180003227  pop     rbp
0x180003228  retn
0x180003229  lea     rcx, [rbp+ppv]
0x18000322d  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180003232  nop
0x180003233  mov     rcx, [rbp+pv]; pv
0x180003237  mov     [rbp+pv], r15
0x18000323b  call    cs:__imp_CoTaskMemFree
0x180003241  nop
0x180003242  lea     rcx, [rbp+var_38]
0x180003246  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18000324b  xor     eax, eax
0x18000324d  jmp     loc_1800033BC
0x180003252  mov     rax, [r8]
0x180003255  sub     rax, qword ptr cs:IID_IShellFolderViewCB.Data1
0x18000325c  jnz     short loc_180003269
0x18000325e  mov     rax, [r8+8]
0x180003262  sub     rax, qword ptr cs:IID_IShellFolderViewCB.Data4
0x180003269  test    rax, rax
0x18000326c  jnz     loc_180003370
0x180003272  mov     [rbp+ppv], r15
0x180003276  lea     r14, [rcx+18h]
0x18000327a  lea     rdx, [rbp+ppv]
0x18000327e  mov     rcx, r14
0x180003281  call    ??$As@UIPersistFolder2@@@?$ComPtr@UIShellFolder3@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPersistFolder2@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IShellFolder3>::As<IPersistFolder2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IPersistFolder2>>)
0x180003286  mov     esi, eax
0x180003288  test    eax, eax
0x18000328a  jns     short loc_1800032B5
0x18000328c  mov     rcx, [rbp+30h]; this
0x180003290  mov     r9d, eax; char *
0x180003293  lea     r8, aShellSearchfol_0; "shell\\searchfolder\\dbfolder_ui.cpp"
0x18000329a  mov     edx, 593h; void *
0x18000329f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800032a4  nop
0x1800032a5  lea     rcx, [rbp+ppv]
0x1800032a9  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800032ae  mov     eax, esi
0x1800032b0  jmp     loc_1800033BC
0x1800032b5  mov     [rbp+pv], r15
0x1800032b9  mov     rcx, [rbp+ppv]
0x1800032bd  mov     rax, [rcx]
0x1800032c0  lea     rdx, [rbp+pv]
0x1800032c4  mov     rax, [rax+28h]
0x1800032c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032cd  mov     esi, eax
0x1800032cf  test    eax, eax
0x1800032d1  jns     short loc_18000330B
0x1800032d3  mov     rcx, [rbp+30h]; this
0x1800032d7  mov     r9d, eax; char *
0x1800032da  lea     r8, aShellSearchfol_0; "shell\\searchfolder\\dbfolder_ui.cpp"
0x1800032e1  mov     edx, 595h; void *
0x1800032e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800032eb  nop
0x1800032ec  mov     rcx, [rbp+pv]; pv
0x1800032f0  mov     [rbp+pv], r15
0x1800032f4  call    cs:__imp_CoTaskMemFree
0x1800032fa  nop
0x1800032fb  lea     rcx, [rbp+ppv]
0x1800032ff  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180003304  mov     eax, esi
0x180003306  jmp     loc_1800033BC
0x18000330b  mov     r9, rdi; ppv
0x18000330e  mov     r8, rbx; riid
0x180003311  mov     rdx, [rbp+pv]; struct _ITEMIDLIST_ABSOLUTE *
0x180003315  mov     rcx, [r14]; struct IShellFolder3 *
0x180003318  call    ?s_CreateInstance@CDBFolderViewCB@@SAJPEAUIShellFolder3@@PEBU_ITEMIDLIST_ABSOLUTE@@AEBU_GUID@@PEAPEAX@Z; CDBFolderViewCB::s_CreateInstance(IShellFolder3 *,_ITEMIDLIST_ABSOLUTE const *,_GUID const &,void * *)
0x18000331d  mov     ebx, eax
0x18000331f  test    eax, eax
0x180003321  jns     short loc_180003358
0x180003323  mov     rcx, [rbp+30h]; this
0x180003327  mov     r9d, eax; char *
0x18000332a  lea     r8, aShellSearchfol_0; "shell\\searchfolder\\dbfolder_ui.cpp"
0x180003331  mov     edx, 597h; void *
0x180003336  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000333b  nop
0x18000333c  mov     rcx, [rbp+pv]; pv
0x180003340  mov     [rbp+pv], r15
0x180003344  call    cs:__imp_CoTaskMemFree
0x18000334a  nop
0x18000334b  lea     rcx, [rbp+ppv]
0x18000334f  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180003354  mov     eax, ebx
0x180003356  jmp     short loc_1800033BC
0x180003358  mov     rcx, [rbp+pv]; pv
0x18000335c  mov     [rbp+pv], r15
0x180003360  call    cs:__imp_CoTaskMemFree
0x180003366  nop
0x180003367  lea     rcx, [rbp+ppv]; this
0x18000336b  jmp     loc_180003246
0x180003370  mov     rax, [r8]
0x180003373  sub     rax, qword ptr cs:IID_IContextMenu.Data1
0x18000337a  jnz     short loc_180003387
0x18000337c  mov     rax, [r8+8]
0x180003380  sub     rax, qword ptr cs:IID_IContextMenu.Data4
0x180003387  test    rax, rax
0x18000338a  jnz     short loc_1800033B7
0x18000338c  call    ?_CreateBgContextMenu@CDBFolderUI@@AEAAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z; CDBFolderUI::_CreateBgContextMenu(HWND__ *,_GUID const &,void * *)
0x180003391  mov     ebx, eax
0x180003393  test    eax, eax
0x180003395  jns     loc_18000324B
0x18000339b  mov     rcx, [rbp+30h]; this
0x18000339f  mov     r9d, eax; char *
0x1800033a2  lea     r8, aShellSearchfol_0; "shell\\searchfolder\\dbfolder_ui.cpp"
0x1800033a9  mov     edx, 59Bh; void *
0x1800033ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800033b3  mov     eax, ebx
0x1800033b5  jmp     short loc_1800033BC
0x1800033b7  mov     eax, 80070057h
0x1800033bc  add     rsp, 58h
0x1800033c0  pop     r15
0x1800033c2  pop     r14
0x1800033c4  pop     rdi
0x1800033c5  pop     rsi
0x1800033c6  pop     rbx
0x1800033c7  pop     rbp
0x1800033c8  retn
```
