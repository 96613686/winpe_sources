# CNetworkItem::GetPropertyStore(IPropertyStore * *)

- ea: `0x1800027b0`
- end: `0x180002a23`
- name: `?GetPropertyStore@CNetworkItem@@UEAAJPEAPEAUIPropertyStore@@@Z`
- size: `627`
- prototype: `__int64 __fastcall(CNetworkItem *__hidden this, struct IPropertyStore **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800027b0`
- `0x180002a78`
- `0x18000b010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1800028ce`
- `KERNEL32!CompareStringW` at `0x1800028ce`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800027dc`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800027dc`

## pseudocode

```c
__int64 __fastcall CNetworkItem::GetPropertyStore(CNetworkItem *this, struct IPropertyStore **a2)
{
  HRESULT v4; // ebx
  const unsigned __int16 *v5; // r8
  const unsigned __int16 *v6; // r8
  __int64 v7; // rax
  const unsigned __int16 *v8; // r8
  const WCHAR *v9; // r8
  int v10; // eax
  const unsigned __int16 *v11; // r8
  __int128 v13; // [rsp+30h] [rbp-28h] BYREF
  __int64 v14; // [rsp+40h] [rbp-18h]
  void *ppv; // [rsp+88h] [rbp+30h] BYREF

  *a2 = 0;
  ppv = 0;
  v4 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
  if ( v4 >= 0 )
  {
    v5 = (const unsigned __int16 *)*((_QWORD *)this + 4);
    if ( v5 )
    {
      v4 = IPropertyStore_SetString((struct IPropertyStore *)ppv, &stru_18000E108, v5);
      if ( v4 < 0 )
        goto LABEL_22;
    }
    v6 = (const unsigned __int16 *)*((_QWORD *)this + 3);
    if ( v6 )
    {
      v4 = IPropertyStore_SetString((struct IPropertyStore *)ppv, &PKEY_ItemNameDisplay, v6);
      if ( v4 < 0 )
        goto LABEL_22;
    }
    v14 = 0;
    v13 = 0;
    LOWORD(v13) = 11;
    v7 = *(_QWORD *)ppv;
    WORD4(v13) = -(*((_DWORD *)this + 10) != 0);
    v4 = (*(__int64 (__fastcall **)(void *, __int64 *, __int128 *))(v7 + 48))(ppv, qword_18000E0F0, &v13);
    if ( v4 < 0 )
      goto LABEL_22;
    if ( *((_DWORD *)this + 10) )
    {
      v8 = (const unsigned __int16 *)*((_QWORD *)this + 6);
      if ( v8 )
      {
        v4 = IPropertyStore_SetString((struct IPropertyStore *)ppv, &PKEY_Computer_Workgroup, v8);
        if ( v4 < 0 )
          goto LABEL_22;
      }
      v9 = (const WCHAR *)*((_QWORD *)this + 27);
      if ( v9 )
      {
        if ( CompareStringW(0x7Fu, 1u, v9, -1, L"Microsoft Windows Network", -1) != 2 )
        {
          v4 = IPropertyStore_SetString(
                 (struct IPropertyStore *)ppv,
                 &PKEY_NetworkProvider,
                 *((const unsigned __int16 **)this + 27));
          if ( v4 < 0 )
            goto LABEL_22;
        }
      }
      v14 = 0;
      v13 = 0;
      LOWORD(v13) = 19;
      DWORD2(v13) = *((_DWORD *)this + 56);
      v10 = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, __int128 *))(*(_QWORD *)ppv + 48LL))(
              ppv,
              &PKEY_WNET_DisplayType,
              &v13);
    }
    else
    {
      v4 = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, char *))(*(_QWORD *)ppv + 48LL))(
             ppv,
             &PKEY_PNPX_CompatibleTypes,
             (char *)this + 152);
      if ( v4 < 0 )
        goto LABEL_22;
      v4 = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, char *))(*(_QWORD *)ppv + 48LL))(
             ppv,
             &PKEY_PNPX_DeviceCategory,
             (char *)this + 192);
      if ( v4 < 0 )
        goto LABEL_22;
      v11 = (const unsigned __int16 *)*((_QWORD *)this + 35);
      if ( !v11 )
      {
LABEL_19:
        v4 = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, char *))(*(_QWORD *)ppv + 48LL))(
               ppv,
               &PKEY_Category,
               (char *)this + 72);
        if ( v4 >= 0 )
        {
          v4 = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, char *))(*(_QWORD *)ppv + 48LL))(
                 ppv,
                 &PKEY_PNPX_IpAddress,
                 (char *)this + 232);
          if ( v4 >= 0 )
            v4 = (**(__int64 (__fastcall ***)(void *, GUID *, struct IPropertyStore **))ppv)(
                   ppv,
                   &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                   a2);
        }
        goto LABEL_22;
      }
      v10 = IPropertyStore_SetString((struct IPropertyStore *)ppv, &PKEY_PNPX_PresentationUrl, v11);
    }
    v4 = v10;
    if ( v10 >= 0 )
      goto LABEL_19;
LABEL_22:
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800027b0  push    rbp
0x1800027b2  push    rbx
0x1800027b3  push    rsi
0x1800027b4  push    rdi
0x1800027b5  mov     rbp, rsp
0x1800027b8  sub     rsp, 58h
0x1800027bc  mov     rsi, rdx
0x1800027bf  mov     qword ptr [rdx], 0
0x1800027c6  mov     rdi, rcx
0x1800027c9  mov     [rbp+ppv], 0
0x1800027d1  lea     rdx, [rbp+ppv]; ppv
0x1800027d5  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x1800027dc  call    cs:__imp_PSCreateMemoryPropertyStore
0x1800027e2  mov     ebx, eax
0x1800027e4  test    eax, eax
0x1800027e6  js      loc_180002A18
0x1800027ec  mov     r8, [rdi+20h]; unsigned __int16 *
0x1800027f0  test    r8, r8
0x1800027f3  jz      short loc_18000280F
0x1800027f5  mov     rcx, [rbp+ppv]; struct IPropertyStore *
0x1800027f9  lea     rdx, stru_18000E108; struct _tagpropertykey *
0x180002800  call    ?IPropertyStore_SetString@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEBG@Z; IPropertyStore_SetString(IPropertyStore *,_tagpropertykey const &,ushort const *)
0x180002805  mov     ebx, eax
0x180002807  test    eax, eax
0x180002809  js      loc_180002A08
0x18000280f  mov     r8, [rdi+18h]; unsigned __int16 *
0x180002813  test    r8, r8
0x180002816  jz      short loc_180002832
0x180002818  mov     rcx, [rbp+ppv]; struct IPropertyStore *
0x18000281c  lea     rdx, PKEY_ItemNameDisplay; struct _tagpropertykey *
0x180002823  call    ?IPropertyStore_SetString@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEBG@Z; IPropertyStore_SetString(IPropertyStore *,_tagpropertykey const &,ushort const *)
0x180002828  mov     ebx, eax
0x18000282a  test    eax, eax
0x18000282c  js      loc_180002A08
0x180002832  mov     rcx, [rbp+ppv]
0x180002836  lea     r8, [rbp+var_28]
0x18000283a  xor     eax, eax
0x18000283c  xorps   xmm0, xmm0
0x18000283f  mov     [rbp+var_18], rax
0x180002843  mov     eax, 0Bh
0x180002848  movups  [rbp+var_28], xmm0
0x18000284c  mov     word ptr [rbp+var_28], ax
0x180002850  mov     eax, [rdi+28h]
0x180002853  neg     eax
0x180002855  mov     rax, [rcx]
0x180002858  sbb     dx, dx
0x18000285b  mov     word ptr [rbp+var_28+8], dx
0x18000285f  lea     rdx, qword_18000E0F0
0x180002866  mov     rax, [rax+30h]
0x18000286a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000286f  mov     ebx, eax
0x180002871  test    eax, eax
0x180002873  js      loc_180002A08
0x180002879  cmp     dword ptr [rdi+28h], 0
0x18000287d  jz      loc_180002936
0x180002883  mov     r8, [rdi+30h]; unsigned __int16 *
0x180002887  test    r8, r8
0x18000288a  jz      short loc_1800028A6
0x18000288c  mov     rcx, [rbp+ppv]; struct IPropertyStore *
0x180002890  lea     rdx, PKEY_Computer_Workgroup; struct _tagpropertykey *
0x180002897  call    ?IPropertyStore_SetString@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEBG@Z; IPropertyStore_SetString(IPropertyStore *,_tagpropertykey const &,ushort const *)
0x18000289c  mov     ebx, eax
0x18000289e  test    eax, eax
0x1800028a0  js      loc_180002A08
0x1800028a6  mov     r8, [rdi+0D8h]; lpString1
0x1800028ad  test    r8, r8
0x1800028b0  jz      short loc_1800028FA
0x1800028b2  or      r9d, 0FFFFFFFFh; cchCount1
0x1800028b6  lea     rax, String2; "Microsoft Windows Network"
0x1800028bd  mov     [rsp+58h+cchCount2], r9d; cchCount2
0x1800028c2  mov     [rsp+58h+lpString2], rax; lpString2
0x1800028c7  lea     edx, [r9+2]; dwCmpFlags
0x1800028cb  lea     ecx, [rdx+7Eh]; Locale
0x1800028ce  call    cs:__imp_CompareStringW
0x1800028d4  cmp     eax, 2
0x1800028d7  jz      short loc_1800028FA
0x1800028d9  mov     r8, [rdi+0D8h]; unsigned __int16 *
0x1800028e0  lea     rdx, PKEY_NetworkProvider; struct _tagpropertykey *
0x1800028e7  mov     rcx, [rbp+ppv]; struct IPropertyStore *
0x1800028eb  call    ?IPropertyStore_SetString@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEBG@Z; IPropertyStore_SetString(IPropertyStore *,_tagpropertykey const &,ushort const *)
0x1800028f0  mov     ebx, eax
0x1800028f2  test    eax, eax
0x1800028f4  js      loc_180002A08
0x1800028fa  mov     rcx, [rbp+ppv]
0x1800028fe  lea     r8, [rbp+var_28]
0x180002902  xor     eax, eax
0x180002904  lea     rdx, PKEY_WNET_DisplayType
0x18000290b  mov     [rbp+var_18], rax
0x18000290f  xorps   xmm0, xmm0
0x180002912  mov     eax, 13h
0x180002917  movups  [rbp+var_28], xmm0
0x18000291b  mov     word ptr [rbp+var_28], ax
0x18000291f  mov     eax, [rdi+0E0h]
0x180002925  mov     dword ptr [rbp+var_28+8], eax
0x180002928  mov     rax, [rcx]
0x18000292b  mov     rax, [rax+30h]
0x18000292f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002934  jmp     short loc_1800029A2
0x180002936  mov     rcx, [rbp+ppv]
0x18000293a  lea     r8, [rdi+98h]
0x180002941  lea     rdx, PKEY_PNPX_CompatibleTypes
0x180002948  mov     rax, [rcx]
0x18000294b  mov     rax, [rax+30h]
0x18000294f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002954  mov     ebx, eax
0x180002956  test    eax, eax
0x180002958  js      loc_180002A08
0x18000295e  mov     rcx, [rbp+ppv]
0x180002962  lea     r8, [rdi+0C0h]
0x180002969  lea     rdx, PKEY_PNPX_DeviceCategory
0x180002970  mov     rax, [rcx]
0x180002973  mov     rax, [rax+30h]
0x180002977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000297c  mov     ebx, eax
0x18000297e  test    eax, eax
0x180002980  js      loc_180002A08
0x180002986  mov     r8, [rdi+118h]; unsigned __int16 *
0x18000298d  test    r8, r8
0x180002990  jz      short loc_1800029A8
0x180002992  mov     rcx, [rbp+ppv]; struct IPropertyStore *
0x180002996  lea     rdx, PKEY_PNPX_PresentationUrl; struct _tagpropertykey *
0x18000299d  call    ?IPropertyStore_SetString@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEBG@Z; IPropertyStore_SetString(IPropertyStore *,_tagpropertykey const &,ushort const *)
0x1800029a2  mov     ebx, eax
0x1800029a4  test    eax, eax
0x1800029a6  js      short loc_180002A08
0x1800029a8  mov     rcx, [rbp+ppv]
0x1800029ac  lea     r8, [rdi+48h]
0x1800029b0  lea     rdx, PKEY_Category
0x1800029b7  mov     rax, [rcx]
0x1800029ba  mov     rax, [rax+30h]
0x1800029be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029c3  mov     ebx, eax
0x1800029c5  test    eax, eax
0x1800029c7  js      short loc_180002A08
0x1800029c9  mov     rcx, [rbp+ppv]
0x1800029cd  lea     r8, [rdi+0E8h]
0x1800029d4  lea     rdx, PKEY_PNPX_IpAddress
0x1800029db  mov     rax, [rcx]
0x1800029de  mov     rax, [rax+30h]
0x1800029e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029e7  mov     ebx, eax
0x1800029e9  test    eax, eax
0x1800029eb  js      short loc_180002A08
0x1800029ed  mov     rcx, [rbp+ppv]
0x1800029f1  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x1800029f8  mov     r8, rsi
0x1800029fb  mov     rax, [rcx]
0x1800029fe  mov     rax, [rax]
0x180002a01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a06  mov     ebx, eax
0x180002a08  mov     rcx, [rbp+ppv]
0x180002a0c  mov     rax, [rcx]
0x180002a0f  mov     rax, [rax+10h]
0x180002a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a18  mov     eax, ebx
0x180002a1a  add     rsp, 58h
0x180002a1e  pop     rdi
0x180002a1f  pop     rsi
0x180002a20  pop     rbx
0x180002a21  pop     rbp
0x180002a22  retn
```
