# CDBFolderUI::_ReinitializeContextMenu(IContextMenu *,HWND__ *,_ITEMID_CHILD const *)

- ea: `0x180003400`
- end: `0x18000364b`
- name: `?_ReinitializeContextMenu@CDBFolderUI@@AEAAJPEAUIContextMenu@@PEAUHWND__@@PEFBU_ITEMID_CHILD@@@Z`
- size: `587`
- prototype: `__int64 __fastcall(CDBFolderUI *__hidden this, struct IContextMenu *, HWND, const struct _ITEMID_CHILD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001fd38`

## callees

- `0x1800033d0`
- `0x180003400`
- `0x180004a10`
- `0x1800054b0`
- `0x180005c88`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000358d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800035f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000358d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800035f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CDBFolderUI::_ReinitializeContextMenu(
        CDBFolderUI *this,
        struct IContextMenu *a2,
        HWND a3,
        const struct _ITEMID_CHILD *a4)
{
  int v7; // eax
  unsigned int v8; // r14d
  int v10; // eax
  unsigned int v11; // esi
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // eax
  void *v15; // rcx
  __int64 v16; // rbx
  LPVOID v17; // rsi
  void *v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // [rsp+20h] [rbp-40h]
  LPVOID pv; // [rsp+40h] [rbp-20h] BYREF
  __int64 v23; // [rsp+48h] [rbp-18h] BYREF
  __int64 v24; // [rsp+50h] [rbp-10h] BYREF
  __int64 v25; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  __int64 v27; // [rsp+90h] [rbp+30h] BYREF
  const struct _ITEMID_CHILD *v28; // [rsp+A8h] [rbp+48h] BYREF

  v28 = a4;
  v27 = 0;
  v7 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 3))(
         *((_QWORD *)this + 3),
         &GUID_7701b412_e63f_4666_92ee_334072c0a16d,
         &v27);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D0,
      (unsigned int)"shell\\searchfolder\\dbfolder_ui.cpp",
      (const char *)(unsigned int)v7,
      v21);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v27);
    return v8;
  }
  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v24);
  v10 = (*(__int64 (__fastcall **)(__int64, HWND, __int64, const struct _ITEMID_CHILD **))(*(_QWORD *)v27 + 40LL))(
          v27,
          a3,
          1,
          &v28);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D3,
      (unsigned int)"shell\\searchfolder\\dbfolder_ui.cpp",
      (const char *)(unsigned int)v10,
      (int)&GUID_0000010e_0000_0000_c000_000000000046);
    ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v24);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v27);
    return v11;
  }
  v23 = 0;
  v12 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 3))(
          *((_QWORD *)this + 3),
          &GUID_1ac3d9f0_175c_11d1_95be_00609797ea4f,
          &v23);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D6,
      (unsigned int)"shell\\searchfolder\\dbfolder_ui.cpp",
      (const char *)(unsigned int)v12,
      (int)&GUID_0000010e_0000_0000_c000_000000000046);
LABEL_7:
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v23);
    ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v24);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v27);
    return v13;
  }
  pv = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v23 + 40LL))(v23, &pv);
  v13 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D8,
      (unsigned int)"shell\\searchfolder\\dbfolder_ui.cpp",
      (const char *)(unsigned int)v14,
      (int)&GUID_0000010e_0000_0000_c000_000000000046);
    v15 = pv;
    pv = 0;
    CoTaskMemFree(v15);
    goto LABEL_7;
  }
  v16 = v24;
  v17 = pv;
  v25 = 0;
  if ( ((__int64 (__fastcall *)(struct IContextMenu *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_000214e8_0000_0000_c000_000000000046,
         &v25) >= 0 )
  {
    (*(void (__fastcall **)(__int64, LPVOID, __int64, _QWORD))(*(_QWORD *)v25 + 24LL))(v25, v17, v16, 0);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  v18 = pv;
  pv = 0;
  CoTaskMemFree(v18);
  v19 = v23;
  if ( v23 )
  {
    v23 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v24);
  v20 = v27;
  if ( v27 )
  {
    v27 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  return 0;
}

```

## disassembly

```asm
0x180003400  mov     [rsp-28h+arg_8], rbx
0x180003405  mov     [rsp-28h+arg_18], r9
0x18000340a  push    rbp
0x18000340b  push    rsi
0x18000340c  push    rdi
0x18000340d  push    r14
0x18000340f  push    r15
0x180003411  mov     rbp, rsp
0x180003414  sub     rsp, 60h
0x180003418  mov     rsi, r8
0x18000341b  mov     rdi, rdx
0x18000341e  mov     rbx, rcx
0x180003421  xor     r15d, r15d
0x180003424  mov     [rbp+arg_0], r15
0x180003428  mov     rcx, [rcx+18h]
0x18000342c  mov     rax, [rcx]
0x18000342f  lea     r8, [rbp+arg_0]
0x180003433  lea     rdx, _GUID_7701b412_e63f_4666_92ee_334072c0a16d
0x18000343a  mov     rax, [rax]
0x18000343d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003442  mov     r14d, eax
0x180003445  test    eax, eax
0x180003447  jns     short loc_180003473
0x180003449  mov     rcx, [rbp+28h]; this
0x18000344d  mov     r9d, eax; char *
0x180003450  lea     r8, aShellSearchfol_0; "shell\\searchfolder\\dbfolder_ui.cpp"
0x180003457  mov     edx, 5D0h; void *
0x18000345c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003461  nop
0x180003462  lea     rcx, [rbp+arg_0]
0x180003466  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18000346b  mov     eax, r14d
0x18000346e  jmp     loc_180003637
0x180003473  lea     rcx, [rbp+var_10]; void *
0x180003477  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18000347c  nop
0x18000347d  mov     rcx, [rbp+arg_0]
0x180003481  mov     rax, [rcx]
0x180003484  lea     rdx, [rbp+var_10]
0x180003488  mov     [rsp+60h+var_30], rdx
0x18000348d  mov     [rsp+60h+var_38], r15
0x180003492  lea     rdx, _GUID_0000010e_0000_0000_c000_000000000046
0x180003499  mov     qword ptr [rsp+60h+var_40], rdx; int
0x18000349e  lea     r9, [rbp+arg_18]
0x1800034a2  mov     r8d, 1
0x1800034a8  mov     rdx, rsi
0x1800034ab  mov     rax, [rax+28h]
0x1800034af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034b4  mov     esi, eax
0x1800034b6  test    eax, eax
0x1800034b8  jns     short loc_1800034ED
0x1800034ba  mov     rcx, [rbp+28h]; this
0x1800034be  mov     r9d, eax; char *
0x1800034c1  lea     r8, aShellSearchfol_0; "shell\\searchfolder\\dbfolder_ui.cpp"
0x1800034c8  mov     edx, 5D3h; void *
0x1800034cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800034d2  nop
0x1800034d3  lea     rcx, [rbp+var_10]
0x1800034d7  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x1800034dc  nop
0x1800034dd  lea     rcx, [rbp+arg_0]
0x1800034e1  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800034e6  mov     eax, esi
0x1800034e8  jmp     loc_180003637
0x1800034ed  mov     [rbp+var_18], r15
0x1800034f1  mov     rcx, [rbx+18h]
0x1800034f5  mov     rax, [rcx]
0x1800034f8  lea     r8, [rbp+var_18]
0x1800034fc  lea     rdx, _GUID_1ac3d9f0_175c_11d1_95be_00609797ea4f
0x180003503  mov     rax, [rax]
0x180003506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000350b  mov     ebx, eax
0x18000350d  test    eax, eax
0x18000350f  jns     short loc_18000354E
0x180003511  mov     rcx, [rbp+28h]; this
0x180003515  mov     r9d, eax; char *
0x180003518  lea     r8, aShellSearchfol_0; "shell\\searchfolder\\dbfolder_ui.cpp"
0x18000351f  mov     edx, 5D6h; void *
0x180003524  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003529  nop
0x18000352a  lea     rcx, [rbp+var_18]
0x18000352e  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180003533  nop
0x180003534  lea     rcx, [rbp+var_10]
0x180003538  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18000353d  nop
0x18000353e  lea     rcx, [rbp+arg_0]
0x180003542  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180003547  mov     eax, ebx
0x180003549  jmp     loc_180003637
0x18000354e  mov     [rbp+pv], r15
0x180003552  mov     rcx, [rbp+var_18]
0x180003556  mov     rax, [rcx]
0x180003559  lea     rdx, [rbp+pv]
0x18000355d  mov     rax, [rax+28h]
0x180003561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003566  mov     ebx, eax
0x180003568  test    eax, eax
0x18000356a  jns     short loc_180003595
0x18000356c  mov     rcx, [rbp+28h]; this
0x180003570  mov     r9d, eax; char *
0x180003573  lea     r8, aShellSearchfol_0; "shell\\searchfolder\\dbfolder_ui.cpp"
0x18000357a  mov     edx, 5D8h; void *
0x18000357f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003584  nop
0x180003585  mov     rcx, [rbp+pv]; pv
0x180003589  mov     [rbp+pv], r15
0x18000358d  call    cs:__imp_CoTaskMemFree
0x180003593  jmp     short loc_18000352A
0x180003595  mov     rbx, [rbp+var_10]
0x180003599  mov     rsi, [rbp+pv]
0x18000359d  mov     [rbp+var_8], r15
0x1800035a1  mov     rax, [rdi]
0x1800035a4  lea     r8, [rbp+var_8]
0x1800035a8  lea     rdx, _GUID_000214e8_0000_0000_c000_000000000046
0x1800035af  mov     rcx, rdi
0x1800035b2  mov     rax, [rax]
0x1800035b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035ba  test    eax, eax
0x1800035bc  js      short loc_1800035E8
0x1800035be  mov     rcx, [rbp+var_8]
0x1800035c2  mov     rax, [rcx]
0x1800035c5  xor     r9d, r9d
0x1800035c8  mov     r8, rbx
0x1800035cb  mov     rdx, rsi
0x1800035ce  mov     rax, [rax+18h]
0x1800035d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035d7  mov     rcx, [rbp+var_8]
0x1800035db  mov     rax, [rcx]
0x1800035de  mov     rax, [rax+10h]
0x1800035e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035e7  nop
0x1800035e8  mov     rcx, [rbp+pv]; pv
0x1800035ec  mov     [rbp+pv], r15
0x1800035f0  call    cs:__imp_CoTaskMemFree
0x1800035f6  nop
0x1800035f7  mov     rcx, [rbp+var_18]
0x1800035fb  test    rcx, rcx
0x1800035fe  jz      short loc_180003611
0x180003600  mov     [rbp+var_18], r15
0x180003604  mov     rax, [rcx]
0x180003607  mov     rax, [rax+10h]
0x18000360b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003610  nop
0x180003611  lea     rcx, [rbp+var_10]
0x180003615  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18000361a  nop
0x18000361b  mov     rcx, [rbp+arg_0]
0x18000361f  test    rcx, rcx
0x180003622  jz      short loc_180003635
0x180003624  mov     [rbp+arg_0], r15
0x180003628  mov     rax, [rcx]
0x18000362b  mov     rax, [rax+10h]
0x18000362f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003634  nop
0x180003635  xor     eax, eax
0x180003637  mov     rbx, [rsp+60h+arg_8]
0x18000363f  add     rsp, 60h
0x180003643  pop     r15
0x180003645  pop     r14
0x180003647  pop     rdi
0x180003648  pop     rsi
0x180003649  pop     rbp
0x18000364a  retn
```
