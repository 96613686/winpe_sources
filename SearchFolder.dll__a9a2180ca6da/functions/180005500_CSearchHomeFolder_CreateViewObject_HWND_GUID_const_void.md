# CSearchHomeFolder::CreateViewObject(HWND__ *,_GUID const &,void * *)

- ea: `0x180005500`
- end: `0x180005641`
- name: `?CreateViewObject@CSearchHomeFolder@@UEAAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z`
- size: `321`
- prototype: `int(CSearchHomeFolder *__hidden this, HWND, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180005500`
- `0x18002578c`
- `0x18002656c`
- `0x180051010`

## import_xrefs

- `SHELL32!__imp_SHCreateShellFolderView` at `0x180005605`
- `SHELL32!__imp_SHCreateShellFolderView` at `0x180005605`
- `SHLWAPI!__imp_QISearch` at `0x1800055a8`
- `SHLWAPI!__imp_QISearch` at `0x1800055dd`
- `SHLWAPI!__imp_QISearch` at `0x1800055a8`
- `SHLWAPI!__imp_QISearch` at `0x1800055dd`

## pseudocode

```c
__int64 __fastcall CSearchHomeFolder::CreateViewObject(
        const struct _ITEMIDLIST_ABSOLUTE **this,
        HWND a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  HRESULT Instance; // ebx
  __int64 v10; // rax
  const struct _GUID *v12; // rdx
  SFV_CREATE pcsfv; // [rsp+20h] [rbp-28h] BYREF

  *a4 = 0;
  v6 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IShellView.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IShellView.Data1 )
    v6 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IShellView.Data4;
  if ( v6 )
  {
    v7 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_dc0ac42a_141e_4876_9c43_824829440de0.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_dc0ac42a_141e_4876_9c43_824829440de0.Data1 )
      v7 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_dc0ac42a_141e_4876_9c43_824829440de0.Data4;
    if ( !v7 )
      return (unsigned int)QISearch(this, &`CSearchHomeFolder::QueryInterface'::`2'::qit, a3, a4);
    v8 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IFilterSupport.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IFilterSupport.Data1 )
      v8 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IFilterSupport.Data4;
    if ( !v8 )
      return (unsigned int)QISearch(this, &`CSearchHomeFolder::QueryInterface'::`2'::qit, a3, a4);
    Instance = -2147024809;
    v10 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IFrameLayoutDefinition.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IFrameLayoutDefinition.Data1 )
      v10 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IFrameLayoutDefinition.Data4;
    if ( !v10 )
      return (unsigned int)CreateCommonFrame(this, a2);
  }
  else
  {
    *(_QWORD *)&pcsfv.cbSize = 32;
    memset(&pcsfv.pshf, 0, 24);
    Instance = QISearch(
                 this,
                 &`CSearchHomeFolder::QueryInterface'::`2'::qit,
                 &GUID_000214e6_0000_0000_c000_000000000046,
                 (void **)&pcsfv.pshf);
    if ( Instance >= 0 )
    {
      Instance = CSearchHomeFolderViewCB::s_CreateInstance(this[10], v12, (void **)&pcsfv.psfvcb);
      if ( Instance >= 0 )
      {
        Instance = SHCreateShellFolderView(&pcsfv, (IShellView **)a4);
        ((void (__fastcall *)(IShellFolderViewCB *))pcsfv.psfvcb->lpVtbl[2].MessageSFVCB)(pcsfv.psfvcb);
      }
      ((void (__fastcall *)(IShellFolder *))pcsfv.pshf->lpVtbl->Release)(pcsfv.pshf);
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180005500  mov     [rsp+arg_0], rbx
0x180005505  mov     [rsp+arg_8], rsi
0x18000550a  push    rdi
0x18000550b  sub     rsp, 40h
0x18000550f  mov     qword ptr [r9], 0
0x180005516  mov     rdi, r9
0x180005519  mov     rax, [r8]
0x18000551c  mov     rsi, rcx
0x18000551f  sub     rax, qword ptr cs:IID_IShellView.Data1
0x180005526  jnz     short loc_180005533
0x180005528  mov     rax, [r8+8]
0x18000552c  sub     rax, qword ptr cs:IID_IShellView.Data4
0x180005533  test    rax, rax
0x180005536  jz      short loc_1800055B0
0x180005538  mov     rax, [r8]
0x18000553b  sub     rax, qword ptr cs:_GUID_dc0ac42a_141e_4876_9c43_824829440de0.Data1
0x180005542  jnz     short loc_18000554F
0x180005544  mov     rax, [r8+8]
0x180005548  sub     rax, qword ptr cs:_GUID_dc0ac42a_141e_4876_9c43_824829440de0.Data4
0x18000554f  test    rax, rax
0x180005552  jz      short loc_1800055A1
0x180005554  mov     rax, [r8]
0x180005557  sub     rax, qword ptr cs:IID_IFilterSupport.Data1
0x18000555e  jnz     short loc_18000556B
0x180005560  mov     rax, [r8+8]
0x180005564  sub     rax, qword ptr cs:IID_IFilterSupport.Data4
0x18000556b  test    rax, rax
0x18000556e  jz      short loc_1800055A1
0x180005570  mov     rax, [r8]
0x180005573  mov     ebx, 80070057h
0x180005578  sub     rax, qword ptr cs:IID_IFrameLayoutDefinition.Data1
0x18000557f  jnz     short loc_18000558C
0x180005581  mov     rax, [r8+8]
0x180005585  sub     rax, qword ptr cs:IID_IFrameLayoutDefinition.Data4
0x18000558c  test    rax, rax
0x18000558f  jnz     loc_18000562F
0x180005595  call    ?CreateCommonFrame@@YAJPEAUIShellFolder@@W4tagLAYOUTTYPE@@AEBU_GUID@@PEAPEAX@Z; CreateCommonFrame(IShellFolder *,tagLAYOUTTYPE,_GUID const &,void * *)
0x18000559a  mov     ebx, eax
0x18000559c  jmp     loc_18000562F
0x1800055a1  lea     rdx, ?qit@?1??QueryInterface@CSearchHomeFolder@@UEAAJAEBU_GUID@@PEAPEAX@Z@4QBUQITAB@@B; pqit
0x1800055a8  call    cs:__imp_QISearch
0x1800055ae  jmp     short loc_18000559A
0x1800055b0  xorps   xmm0, xmm0
0x1800055b3  mov     qword ptr [rsp+48h+pcsfv.cbSize], 20h ; ' '
0x1800055bc  lea     r9, [rsp+48h+pcsfv.pshf]; ppv
0x1800055c1  mov     [rsp+48h+pcsfv.pshf], 0
0x1800055ca  lea     r8, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x1800055d1  lea     rdx, ?qit@?1??QueryInterface@CSearchHomeFolder@@UEAAJAEBU_GUID@@PEAPEAX@Z@4QBUQITAB@@B; pqit
0x1800055d8  movups  xmmword ptr [rsp+48h+pcsfv.psvOuter], xmm0
0x1800055dd  call    cs:__imp_QISearch
0x1800055e3  mov     ebx, eax
0x1800055e5  test    eax, eax
0x1800055e7  js      short loc_18000562F
0x1800055e9  mov     rcx, [rsi+50h]; struct _ITEMIDLIST_ABSOLUTE *
0x1800055ed  lea     r8, [rsp+48h+pcsfv.psfvcb]; void **
0x1800055f2  call    ?s_CreateInstance@CSearchHomeFolderViewCB@@SAJPEBU_ITEMIDLIST_ABSOLUTE@@AEBU_GUID@@PEAPEAX@Z; CSearchHomeFolderViewCB::s_CreateInstance(_ITEMIDLIST_ABSOLUTE const *,_GUID const &,void * *)
0x1800055f7  mov     ebx, eax
0x1800055f9  test    eax, eax
0x1800055fb  js      short loc_18000561E
0x1800055fd  mov     rdx, rdi; ppsv
0x180005600  lea     rcx, [rsp+48h+pcsfv]; pcsfv
0x180005605  call    cs:__imp_SHCreateShellFolderView
0x18000560b  mov     rcx, [rsp+48h+pcsfv.psfvcb]
0x180005610  mov     ebx, eax
0x180005612  mov     rax, [rcx]
0x180005615  mov     rax, [rax+10h]
0x180005619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000561e  mov     rcx, [rsp+48h+pcsfv.pshf]
0x180005623  mov     rax, [rcx]
0x180005626  mov     rax, [rax+10h]
0x18000562a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000562f  mov     rsi, [rsp+48h+arg_8]
0x180005634  mov     eax, ebx
0x180005636  mov     rbx, [rsp+48h+arg_0]
0x18000563b  add     rsp, 40h
0x18000563f  pop     rdi
0x180005640  retn
```
