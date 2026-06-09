# CEnhancedStorageEnumerator::Next(ulong,_ITEMIDLIST * *,ulong *)

- ea: `0x180002610`
- end: `0x180002c4d`
- name: `?Next@CEnhancedStorageEnumerator@@UEAAJKPEAPEFAU_ITEMIDLIST@@PEAK@Z`
- size: `1597`
- prototype: `_BOOL8 __fastcall(CEnhancedStorageEnumerator *this, unsigned int, struct _ITEMIDLIST **, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002610`
- `0x180002c60`
- `0x18000453c`
- `0x1800061ec`
- `0x1800064cc`
- `0x1800066c0`
- `0x18000684c`
- `0x18000b5fe`
- `0x18000b630`
- `0x18000c010`

## import_xrefs

- `USER32!LoadStringW` at `0x1800028b7`
- `USER32!LoadStringW` at `0x1800028b7`
- `ole32!CoTaskMemFree` at `0x180002927`
- `ole32!CoTaskMemFree` at `0x180002b84`
- `ole32!CoTaskMemFree` at `0x180002927`
- `ole32!CoTaskMemFree` at `0x180002b84`

## pseudocode

```c
_BOOL8 __fastcall CEnhancedStorageEnumerator::Next(
        CEnhancedStorageEnumerator *this,
        unsigned int a2,
        struct _ITEMIDLIST **a3,
        unsigned int *a4)
{
  __int64 v6; // rsi
  int v8; // r15d
  __int64 v9; // r9
  _DWORD *v10; // rbx
  __int64 v11; // rcx
  PVOID *v12; // rax
  __int64 v14; // rax
  int (__fastcall ***v15)(_QWORD, GUID *, struct IUnknown **); // rcx
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  BOOL v20; // r13d
  __int64 v21; // rcx
  int v22; // r13d
  PVOID *v23; // rax
  __int64 v24; // r9
  int v25; // r13d
  _QWORD *v26; // rcx
  int ItemFromData; // edi
  __int64 v28; // rdx
  struct IUnknown *v29; // [rsp+40h] [rbp-C0h] BYREF
  struct IUnknown *v30; // [rsp+48h] [rbp-B8h] BYREF
  int v31; // [rsp+50h] [rbp-B0h] BYREF
  int v32; // [rsp+54h] [rbp-ACh] BYREF
  unsigned __int16 *v33; // [rsp+58h] [rbp-A8h] BYREF
  int v34; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  int v36; // [rsp+70h] [rbp-90h]
  WCHAR Buffer[256]; // [rsp+80h] [rbp-80h] BYREF

  v6 = a2;
  v34 = 0;
  v31 = 1;
  pv = 0;
  v8 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_6cd5398725ca392462ef447cc6ada768_Traceguids, a4);
  memset_0(a3, 0, 8 * v6);
  v10 = (_DWORD *)((char *)this + 24);
  while ( 1 )
  {
    v11 = *((_QWORD *)this + 4);
    if ( !v11
      || (v10 = (_DWORD *)((char *)this + 24),
          v14 = *((unsigned int *)this + 6),
          (unsigned int)v14 >= *((_DWORD *)this + 7)) )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_8;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        &WPP_6cd5398725ca392462ef447cc6ada768_Traceguids,
        (unsigned int)*v10);
LABEL_45:
      v12 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_8;
    }
    v29 = 0;
    v30 = 0;
    if ( (***(int (__fastcall ****)(_QWORD, GUID *, struct IUnknown **))(v11 + 8 * v14))(
           *(_QWORD *)(v11 + 8 * v14),
           &GUID_4da57d2e_8eb3_41f6_a07e_98b52b88242b,
           &v29) < 0
      && v29 )
    {
      ATL::AtlComPtrAssign(&v29, 0);
    }
    v15 = *(int (__fastcall ****)(_QWORD, GUID *, struct IUnknown **))(*((_QWORD *)this + 4) + 8LL * (unsigned int)*v10);
    if ( (**v15)(v15, &GUID_022150a1_113d_11df_bb61_001aa01bbc58, &v30) < 0 && v30 )
      ATL::AtlComPtrAssign(&v30, 0);
    v16 = *(_QWORD *)(*((_QWORD *)this + 4) + 8LL * (unsigned int)*v10);
    v17 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v16 + 40LL))(v16, &v34);
    v9 = (unsigned int)v17;
    if ( v17 < 0 )
      break;
    v20 = v34 == 1;
    if ( v30
      && ((int (__fastcall *)(struct IUnknown *, int *, __int64, _QWORD))v30->lpVtbl[4].AddRef)(
           v30,
           &v31,
           v19,
           (unsigned int)v17) < 0 )
    {
      v31 = 1;
    }
    else if ( !v31 )
    {
      goto LABEL_18;
    }
    if ( !v20 )
    {
      v21 = *(_QWORD *)(*((_QWORD *)this + 4) + 8LL * (unsigned int)*v10);
      v22 = (*(__int64 (__fastcall **)(__int64, LPVOID *, __int64, __int64))(*(_QWORD *)v21 + 56LL))(v21, &pv, v19, v9);
      if ( v22 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19,
            &WPP_6cd5398725ca392462ef447cc6ada768_Traceguids,
            (unsigned int)v22);
      }
      else
      {
        v23 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_6cd5398725ca392462ef447cc6ada768_Traceguids, pv);
          v23 = (PVOID *)WPP_GLOBAL_Control;
        }
        v33 = 0;
        if ( v29 )
        {
          if ( ((int (__fastcall *)(struct IUnknown *, unsigned __int16 **))v29->lpVtbl[3].QueryInterface)(v29, &v33) < 0 )
          {
            v23 = (PVOID *)WPP_GLOBAL_Control;
            goto LABEL_30;
          }
          v25 = 1;
        }
        else
        {
LABEL_30:
          v36 = 0;
          if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 0x20) != 0 )
            WPP_SF_d(v23[2], 21, &WPP_6cd5398725ca392462ef447cc6ada768_Traceguids, (unsigned int)v22);
          LoadStringW(g_hInst, 0x65u, Buffer, 256);
          v33 = Buffer;
          v25 = v36;
        }
        v32 = 1;
        if ( !v29 || (((void (__fastcall *)(struct IUnknown *, int *))v29->lpVtbl[3].AddRef)(v29, &v32), v32) )
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
          {
            v28 = 22;
LABEL_73:
            WPP_SF_S(v26[2], v28, &WPP_6cd5398725ca392462ef447cc6ada768_Traceguids, v33);
          }
        }
        else
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
          {
            v28 = 23;
            goto LABEL_73;
          }
        }
        ItemFromData = CEnhancedStorageFolder::CreateItemFromData(
                         *((CEnhancedStorageFolder **)this + 2),
                         (const unsigned __int16 *)pv,
                         v33,
                         v24,
                         0,
                         v32,
                         a3);
        CoTaskMemFree(pv);
        pv = 0;
        if ( v25 )
        {
          CoTaskMemFree(v33);
          v33 = 0;
        }
        if ( ItemFromData >= 0 )
        {
          v8 = 1;
          ++*v10;
          if ( a4 )
            *a4 = 1;
          if ( v30 )
            ((void (__fastcall *)(struct IUnknown *))v30->lpVtbl->Release)(v30);
          if ( v29 )
            ((void (__fastcall *)(struct IUnknown *))v29->lpVtbl->Release)(v29);
          goto LABEL_45;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            24,
            &WPP_6cd5398725ca392462ef447cc6ada768_Traceguids,
            (unsigned int)ItemFromData);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
      goto LABEL_45;
    }
LABEL_18:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_6cd5398725ca392462ef447cc6ada768_Traceguids, v9);
    (*(void (__fastcall **)(CEnhancedStorageEnumerator *, __int64, __int64, __int64))(*(_QWORD *)this + 32LL))(
      this,
      1,
      v19,
      v9);
    if ( v30 )
      ((void (__fastcall *)(struct IUnknown *))v30->lpVtbl->Release)(v30);
    if ( v29 )
      ((void (__fastcall *)(struct IUnknown *))v29->lpVtbl->Release)(v29);
  }
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_6cd5398725ca392462ef447cc6ada768_Traceguids, v9);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v30 )
  {
    ((void (__fastcall *)(struct IUnknown *, __int64, __int64, __int64))v30->lpVtbl->Release)(v30, v18, v19, v9);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v29 )
  {
    ((void (__fastcall *)(struct IUnknown *, __int64, __int64, __int64))v29->lpVtbl->Release)(v29, v18, v19, v9);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_8:
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 0x20) != 0 )
    WPP_SF_(v12[2], 26, &WPP_6cd5398725ca392462ef447cc6ada768_Traceguids, v9);
  return v8 != (_DWORD)v6;
}

```

## disassembly

```asm
0x180002610  push    rbp
0x180002612  push    rbx
0x180002613  push    rsi
0x180002614  push    rdi
0x180002615  push    r12
0x180002617  push    r13
0x180002619  push    r14
0x18000261b  push    r15
0x18000261d  lea     rbp, [rsp-198h]
0x180002625  sub     rsp, 298h
0x18000262c  mov     rax, cs:__security_cookie
0x180002633  xor     rax, rsp
0x180002636  mov     [rbp+1D0h+var_50], rax
0x18000263d  mov     r12, r9
0x180002640  mov     r14, r8
0x180002643  mov     esi, edx
0x180002645  mov     rdi, rcx
0x180002648  xor     eax, eax
0x18000264a  mov     [rsp+2D0h+var_270], eax
0x18000264e  mov     [rsp+2D0h+var_280], 1
0x180002656  mov     [rsp+2D0h+pv], rax
0x18000265b  mov     r15d, eax
0x18000265e  lea     r13, WPP_GLOBAL_Control
0x180002665  mov     rcx, cs:WPP_GLOBAL_Control
0x18000266c  cmp     rcx, r13
0x18000266f  jz      short loc_18000267B
0x180002671  test    byte ptr [rcx+1Ch], 20h
0x180002675  jnz     loc_180002A22
0x18000267b  mov     r8, rsi
0x18000267e  shl     r8, 3; Size
0x180002682  xor     edx, edx; Val
0x180002684  mov     rcx, r14; void *
0x180002687  call    memset_0
0x18000268c  lea     rbx, [rdi+18h]
0x180002690  mov     rcx, [rdi+20h]
0x180002694  test    rcx, rcx
0x180002697  jnz     short loc_1800026EB
0x180002699  mov     rax, cs:WPP_GLOBAL_Control
0x1800026a0  cmp     rax, r13
0x1800026a3  jz      short loc_1800026AF
0x1800026a5  test    byte ptr [rax+1Ch], 2
0x1800026a9  jnz     loc_180002C16
0x1800026af  xor     ebx, ebx
0x1800026b1  cmp     r15d, esi
0x1800026b4  setnz   bl
0x1800026b7  cmp     rax, r13
0x1800026ba  jz      short loc_1800026C6
0x1800026bc  test    byte ptr [rax+1Ch], 20h
0x1800026c0  jnz     loc_180002C33
0x1800026c6  mov     eax, ebx
0x1800026c8  mov     rcx, [rbp+1D0h+var_50]
0x1800026cf  xor     rcx, rsp; StackCookie
0x1800026d2  call    __security_check_cookie
0x1800026d7  add     rsp, 298h
0x1800026de  pop     r15
0x1800026e0  pop     r14
0x1800026e2  pop     r13
0x1800026e4  pop     r12
0x1800026e6  pop     rdi
0x1800026e7  pop     rsi
0x1800026e8  pop     rbx
0x1800026e9  pop     rbp
0x1800026ea  retn
0x1800026eb  lea     rbx, [rdi+18h]
0x1800026ef  mov     eax, [rbx]
0x1800026f1  cmp     eax, [rdi+1Ch]
0x1800026f4  jnb     short loc_180002699
0x1800026f6  mov     [rsp+2D0h+var_290], 0
0x1800026ff  mov     [rsp+2D0h+var_288], 0
0x180002708  mov     rcx, [rcx+rax*8]
0x18000270c  mov     rax, [rcx]
0x18000270f  lea     r8, [rsp+2D0h+var_290]
0x180002714  lea     rdx, _GUID_4da57d2e_8eb3_41f6_a07e_98b52b88242b
0x18000271b  mov     rax, [rax]
0x18000271e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002723  test    eax, eax
0x180002725  js      loc_1800029E8
0x18000272b  mov     ecx, [rbx]
0x18000272d  mov     rax, [rdi+20h]
0x180002731  mov     rcx, [rax+rcx*8]
0x180002735  mov     rax, [rcx]
0x180002738  lea     r8, [rsp+2D0h+var_288]
0x18000273d  lea     rdx, _GUID_022150a1_113d_11df_bb61_001aa01bbc58
0x180002744  mov     rax, [rax]
0x180002747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000274c  test    eax, eax
0x18000274e  js      loc_180002A05
0x180002754  mov     ecx, [rbx]
0x180002756  mov     rax, [rdi+20h]
0x18000275a  mov     rcx, [rax+rcx*8]
0x18000275e  mov     rax, [rcx]
0x180002761  lea     rdx, [rsp+2D0h+var_270]
0x180002766  mov     rax, [rax+28h]
0x18000276a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000276f  mov     r9d, eax
0x180002772  test    eax, eax
0x180002774  js      loc_180002999
0x18000277a  xor     r13d, r13d
0x18000277d  cmp     [rsp+2D0h+var_270], 1
0x180002782  setz    r13b
0x180002786  mov     rcx, [rsp+2D0h+var_288]
0x18000278b  test    rcx, rcx
0x18000278e  jnz     loc_180002A3C
0x180002794  cmp     [rsp+2D0h+var_280], 0
0x180002799  jnz     short loc_1800027FA
0x18000279b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800027a2  lea     r13, WPP_GLOBAL_Control
0x1800027a9  cmp     rcx, r13
0x1800027ac  jnz     loc_180002A62
0x1800027b2  mov     rax, [rdi]
0x1800027b5  mov     edx, 1
0x1800027ba  mov     rcx, rdi
0x1800027bd  mov     rax, [rax+20h]
0x1800027c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027c6  nop
0x1800027c7  mov     rcx, [rsp+2D0h+var_288]
0x1800027cc  test    rcx, rcx
0x1800027cf  jz      short loc_1800027DE
0x1800027d1  mov     rax, [rcx]
0x1800027d4  mov     rax, [rax+10h]
0x1800027d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027dd  nop
0x1800027de  mov     rcx, [rsp+2D0h+var_290]
0x1800027e3  test    rcx, rcx
0x1800027e6  jz      short loc_1800027F5
0x1800027e8  mov     rax, [rcx]
0x1800027eb  mov     rax, [rax+10h]
0x1800027ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027f4  nop
0x1800027f5  jmp     loc_180002690
0x1800027fa  test    r13d, r13d
0x1800027fd  jnz     short loc_18000279B
0x1800027ff  mov     ecx, [rbx]
0x180002801  mov     rax, [rdi+20h]
0x180002805  mov     rcx, [rax+rcx*8]
0x180002809  mov     rax, [rcx]
0x18000280c  lea     rdx, [rsp+2D0h+pv]
0x180002811  mov     rax, [rax+38h]
0x180002815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000281a  mov     r13d, eax
0x18000281d  test    eax, eax
0x18000281f  js      loc_180002A86
0x180002825  mov     rax, cs:WPP_GLOBAL_Control
0x18000282c  lea     rcx, WPP_GLOBAL_Control
0x180002833  cmp     rax, rcx
0x180002836  jnz     loc_180002AD7
0x18000283c  mov     [rsp+2D0h+var_278], 0
0x180002845  mov     rcx, [rsp+2D0h+var_290]
0x18000284a  test    rcx, rcx
0x18000284d  jz      short loc_18000286F
0x18000284f  mov     rax, [rcx]
0x180002852  lea     rdx, [rsp+2D0h+var_278]
0x180002857  mov     rax, [rax+48h]
0x18000285b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002860  test    eax, eax
0x180002862  jns     loc_180002B07
0x180002868  mov     rax, cs:WPP_GLOBAL_Control
0x18000286f  mov     [rsp+2D0h+var_260], 0
0x180002877  lea     rcx, WPP_GLOBAL_Control
0x18000287e  cmp     rax, rcx
0x180002881  jz      short loc_1800028A1
0x180002883  test    byte ptr [rax+1Ch], 20h
0x180002887  jz      short loc_1800028A1
0x180002889  mov     edx, 15h
0x18000288e  mov     r9d, r13d
0x180002891  lea     r8, WPP_6cd5398725ca392462ef447cc6ada768_Traceguids
0x180002898  mov     rcx, [rax+10h]
0x18000289c  call    WPP_SF_d
0x1800028a1  mov     r9d, 100h; cchBufferMax
0x1800028a7  lea     r8, [rbp+1D0h+Buffer]; lpBuffer
0x1800028ab  mov     edx, 65h ; 'e'; uID
0x1800028b0  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hInstance
0x1800028b7  call    cs:__imp_LoadStringW
0x1800028bd  lea     rax, [rbp+1D0h+Buffer]
0x1800028c1  mov     [rsp+2D0h+var_278], rax
0x1800028c6  mov     r13d, [rsp+2D0h+var_260]
0x1800028cb  mov     [rsp+2D0h+var_27C], 1
0x1800028d3  mov     rcx, [rsp+2D0h+var_290]
0x1800028d8  test    rcx, rcx
0x1800028db  jnz     loc_180002B12
0x1800028e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800028e8  lea     rax, WPP_GLOBAL_Control
0x1800028ef  cmp     rcx, rax
0x1800028f2  jnz     loc_180002B56
0x1800028f8  mov     [rsp+2D0h+var_2A0], r14; struct _ITEMIDLIST **
0x1800028fd  mov     eax, [rsp+2D0h+var_27C]
0x180002901  mov     [rsp+2D0h+var_2A8], eax; int
0x180002905  mov     [rsp+2D0h+var_2B0], 0; int
0x18000290d  mov     r8, [rsp+2D0h+var_278]; unsigned __int16 *
0x180002912  mov     rdx, [rsp+2D0h+pv]; unsigned __int16 *
0x180002917  mov     rcx, [rdi+10h]; this
0x18000291b  call    ?CreateItemFromData@CEnhancedStorageFolder@@QEAAJPEBG0KHHPEAPEFAU_ITEMIDLIST@@@Z; CEnhancedStorageFolder::CreateItemFromData(ushort const *,ushort const *,ulong,int,int,_ITEMIDLIST * *)
0x180002920  mov     edi, eax
0x180002922  mov     rcx, [rsp+2D0h+pv]; pv
0x180002927  call    cs:__imp_CoTaskMemFree
0x18000292d  mov     [rsp+2D0h+pv], 0
0x180002936  test    r13d, r13d
0x180002939  jnz     loc_180002B7F
0x18000293f  test    edi, edi
0x180002941  js      loc_180002B98
0x180002947  mov     r15d, 1
0x18000294d  inc     dword ptr [rbx]
0x18000294f  test    r12, r12
0x180002952  jnz     loc_180002BE2
0x180002958  mov     rcx, [rsp+2D0h+var_288]
0x18000295d  test    rcx, rcx
0x180002960  jz      short loc_18000296F
0x180002962  mov     rax, [rcx]
0x180002965  mov     rax, [rax+10h]
0x180002969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000296e  nop
0x18000296f  mov     rcx, [rsp+2D0h+var_290]
0x180002974  test    rcx, rcx
0x180002977  jz      short loc_180002986
0x180002979  mov     rax, [rcx]
0x18000297c  mov     rax, [rax+10h]
0x180002980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002985  nop
0x180002986  lea     r13, WPP_GLOBAL_Control
0x18000298d  mov     rax, cs:WPP_GLOBAL_Control
0x180002994  jmp     loc_1800026AF
0x180002999  mov     rax, cs:WPP_GLOBAL_Control
0x1800029a0  cmp     rax, r13
0x1800029a3  jnz     loc_180002BEB
0x1800029a9  mov     rcx, [rsp+2D0h+var_288]
0x1800029ae  test    rcx, rcx
0x1800029b1  jz      short loc_1800029C6
0x1800029b3  mov     rax, [rcx]
0x1800029b6  mov     rax, [rax+10h]
0x1800029ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029bf  mov     rax, cs:WPP_GLOBAL_Control
0x1800029c6  mov     rcx, [rsp+2D0h+var_290]
0x1800029cb  test    rcx, rcx
0x1800029ce  jz      short loc_1800029E3
0x1800029d0  mov     rax, [rcx]
0x1800029d3  mov     rax, [rax+10h]
0x1800029d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029dc  mov     rax, cs:WPP_GLOBAL_Control
0x1800029e3  jmp     loc_1800026AF
0x1800029e8  cmp     [rsp+2D0h+var_290], 0
0x1800029ee  jz      loc_18000272B
0x1800029f4  xor     edx, edx; struct IUnknown *
0x1800029f6  lea     rcx, [rsp+2D0h+var_290]; struct IUnknown **
0x1800029fb  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180002a00  jmp     loc_18000272B
0x180002a05  cmp     [rsp+2D0h+var_288], 0
0x180002a0b  jz      loc_180002754
0x180002a11  xor     edx, edx; struct IUnknown *
0x180002a13  lea     rcx, [rsp+2D0h+var_288]; struct IUnknown **
0x180002a18  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180002a1d  jmp     loc_180002754
0x180002a22  mov     edx, 10h
0x180002a27  lea     r8, WPP_6cd5398725ca392462ef447cc6ada768_Traceguids
0x180002a2e  mov     rcx, [rcx+10h]
0x180002a32  call    WPP_SF_
0x180002a37  jmp     loc_18000267B
0x180002a3c  mov     rax, [rcx]
0x180002a3f  lea     rdx, [rsp+2D0h+var_280]
0x180002a44  mov     rax, [rax+68h]
0x180002a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a4d  test    eax, eax
0x180002a4f  jns     loc_180002794
0x180002a55  mov     [rsp+2D0h+var_280], 1
0x180002a5d  jmp     loc_1800027FA
0x180002a62  test    byte ptr [rcx+1Ch], 20h
0x180002a66  jz      loc_1800027B2
0x180002a6c  mov     edx, 12h
0x180002a71  lea     r8, WPP_6cd5398725ca392462ef447cc6ada768_Traceguids
0x180002a78  mov     rcx, [rcx+10h]
0x180002a7c  call    WPP_SF_
0x180002a81  jmp     loc_1800027B2
0x180002a86  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a8d  lea     rax, WPP_GLOBAL_Control
0x180002a94  cmp     rcx, rax
0x180002a97  jz      short loc_180002AB7
0x180002a99  test    byte ptr [rcx+1Ch], 2
0x180002a9d  jz      short loc_180002AB7
0x180002a9f  mov     edx, 13h
0x180002aa4  mov     r9d, r13d
0x180002aa7  lea     r8, WPP_6cd5398725ca392462ef447cc6ada768_Traceguids
0x180002aae  mov     rcx, [rcx+10h]
0x180002ab2  call    WPP_SF_d
0x180002ab7  lea     rcx, [rsp+2D0h+var_288]
0x180002abc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180002ac1  lea     rcx, [rsp+2D0h+var_290]
0x180002ac6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180002acb  lea     r13, WPP_GLOBAL_Control
0x180002ad2  jmp     loc_18000298D
0x180002ad7  test    byte ptr [rax+1Ch], 20h
0x180002adb  jz      loc_18000283C
0x180002ae1  mov     edx, 14h
0x180002ae6  mov     r9, [rsp+2D0h+pv]
0x180002aeb  lea     r8, WPP_6cd5398725ca392462ef447cc6ada768_Traceguids
0x180002af2  mov     rcx, [rax+10h]
0x180002af6  call    WPP_SF_S
0x180002afb  mov     rax, cs:WPP_GLOBAL_Control
0x180002b02  jmp     loc_18000283C
0x180002b07  mov     r13d, 1
0x180002b0d  jmp     loc_1800028CB
0x180002b12  mov     rax, [rcx]
  ... truncated ...
```
