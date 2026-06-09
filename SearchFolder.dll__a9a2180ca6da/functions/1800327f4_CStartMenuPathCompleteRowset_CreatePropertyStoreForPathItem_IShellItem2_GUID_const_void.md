# CStartMenuPathCompleteRowset::_CreatePropertyStoreForPathItem(IShellItem2 *,_GUID const &,void * *)

- ea: `0x1800327f4`
- end: `0x180032a85`
- name: `?_CreatePropertyStoreForPathItem@CStartMenuPathCompleteRowset@@AEAAJPEAUIShellItem2@@AEBU_GUID@@PEAPEAX@Z`
- size: `657`
- prototype: `__int64 __fastcall(CStartMenuPathCompleteRowset *__hidden this, struct IShellItem2 *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180037750`

## callees

- `0x180005460`
- `0x1800054b0`
- `0x180005c88`
- `0x180006900`
- `0x1800129c0`
- `0x1800129ec`
- `0x1800327f4`
- `0x1800347bc`
- `0x180041060`
- `0x180041618`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800329b1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800329b1`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800328b6`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800328b6`

## pseudocode

```c
__int64 __fastcall CStartMenuPathCompleteRowset::_CreatePropertyStoreForPathItem(
        CStartMenuPathCompleteRowset *this,
        struct IShellItem2 *a2,
        const struct _GUID *a3,
        void **a4)
{
  HRESULT v7; // ebx
  unsigned int v8; // esi
  __int64 v9; // rax
  int v11; // [rsp+30h] [rbp-49h] BYREF
  void *ppv; // [rsp+38h] [rbp-41h] BYREF
  void *v13; // [rsp+40h] [rbp-39h] BYREF
  __int64 v14; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int16 *v15; // [rsp+50h] [rbp-29h] BYREF
  PROPVARIANT pvar[2]; // [rsp+58h] [rbp-21h] BYREF
  __int64 v17; // [rsp+68h] [rbp-11h]
  __int128 v18; // [rsp+70h] [rbp-9h] BYREF
  int v19; // [rsp+80h] [rbp+7h]
  __int128 v20; // [rsp+88h] [rbp+Fh] BYREF
  int v21; // [rsp+98h] [rbp+1Fh]

  *a4 = 0;
  v15 = 0;
  v7 = ((__int64 (__fastcall *)(struct IShellItem2 *, __int64, unsigned __int16 **))a2->lpVtbl->GetDisplayName)(
         a2,
         2147991553LL,
         &v15);
  if ( v7 >= 0 )
  {
    if ( CStartMenuPathCompleteRowset::_FindDuplicatePath(this, v15) < 0 )
    {
      ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v14);
      v7 = ((__int64 (__fastcall *)(struct IShellItem2 *, __int64, GUID *, __int64 *))a2->lpVtbl->GetPropertyStore)(
             a2,
             8,
             &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
             &v14);
      if ( v7 >= 0 )
      {
        ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&ppv);
        v7 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
        if ( v7 >= 0 )
        {
          v11 = 0;
          v7 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 13) + 24LL))(
                 *((_QWORD *)this + 13),
                 &v11);
          if ( v7 >= 0 )
          {
            v8 = 0;
            if ( v11 <= 0 )
            {
LABEL_15:
              v13 = 0;
              v7 = ((__int64 (__fastcall *)(struct IShellItem2 *, __int64, void **))a2->lpVtbl->GetDisplayName)(
                     a2,
                     2147647488LL,
                     &v13);
              if ( v7 >= 0 )
                v7 = IPropertyStore_SetString(ppv, &PKEY_ParsingPath, v13);
              CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v13);
              if ( v7 >= 0 )
              {
                v7 = IPropertyStore_SetItem(ppv, PKEY_DelegateIDList, a2);
                if ( v7 >= 0 )
                  v7 = (**(__int64 (__fastcall ***)(void *, GUID *, void **))ppv)(
                         ppv,
                         &GUID_3017056d_9a91_4e90_937d_746c72abbf4f,
                         a4);
              }
            }
            else
            {
              while ( v7 >= 0 )
              {
                v18 = 0;
                v19 = 0;
                v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int128 *))(**((_QWORD **)this + 13) + 32LL))(
                       *((_QWORD *)this + 13),
                       v8,
                       &v18);
                if ( v7 >= 0 )
                {
                  v20 = v18;
                  v21 = v19;
                  if ( (unsigned int)operator==(&v20, &PKEY_ItemId) )
                  {
                    v7 = IPropertyStore_SetItem(ppv, &PKEY_ItemId, a2);
                  }
                  else
                  {
                    *(_OWORD *)pvar = 0;
                    v17 = 0;
                    (*(void (__fastcall **)(__int64, __int128 *, PROPVARIANT *))(*(_QWORD *)v14 + 40LL))(
                      v14,
                      &v20,
                      pvar);
                    v9 = ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->((__int64)&ppv);
                    v7 = (*(__int64 (__fastcall **)(__int64, __int128 *, PROPVARIANT *))(*(_QWORD *)v9 + 48LL))(
                           v9,
                           &v18,
                           pvar);
                    PropVariantClear(pvar);
                  }
                }
                if ( (int)++v8 >= v11 )
                {
                  if ( v7 < 0 )
                    break;
                  goto LABEL_15;
                }
              }
            }
          }
        }
        ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&ppv);
      }
      ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v14);
    }
    else
    {
      v7 = -2147467259;
    }
  }
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&v15);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800327f4  mov     [rsp-8+arg_10], rbx
0x1800327f9  push    rbp
0x1800327fa  push    rsi
0x1800327fb  push    rdi
0x1800327fc  push    r14
0x1800327fe  push    r15
0x180032800  lea     rbp, [rsp-37h]
0x180032805  sub     rsp, 0B0h
0x18003280c  mov     rax, cs:__security_cookie
0x180032813  xor     rax, rsp
0x180032816  mov     [rbp+57h+var_30], rax
0x18003281a  mov     r15, r9
0x18003281d  mov     rdi, rdx
0x180032820  mov     r14, rcx
0x180032823  mov     qword ptr [r9], 0
0x18003282a  mov     [rbp+57h+var_80], 0
0x180032832  mov     rax, [rdx]
0x180032835  lea     r8, [rbp+57h+var_80]
0x180032839  mov     edx, 8007C001h
0x18003283e  mov     rcx, rdi
0x180032841  mov     rax, [rax+28h]
0x180032845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003284a  mov     ebx, eax
0x18003284c  test    eax, eax
0x18003284e  js      loc_180032A57
0x180032854  mov     rdx, [rbp+57h+var_80]; unsigned __int16 *
0x180032858  mov     rcx, r14; this
0x18003285b  call    ?_FindDuplicatePath@CStartMenuPathCompleteRowset@@AEAAJPEBG@Z; CStartMenuPathCompleteRowset::_FindDuplicatePath(ushort const *)
0x180032860  test    eax, eax
0x180032862  js      short loc_18003286E
0x180032864  mov     ebx, 80004005h
0x180032869  jmp     loc_180032A57
0x18003286e  lea     rcx, [rbp+57h+var_88]; void *
0x180032872  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180032877  nop
0x180032878  mov     rax, [rdi]
0x18003287b  lea     r9, [rbp+57h+var_88]
0x18003287f  lea     r8, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180032886  mov     edx, 8
0x18003288b  mov     rcx, rdi
0x18003288e  mov     rax, [rax+40h]
0x180032892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032897  mov     ebx, eax
0x180032899  test    eax, eax
0x18003289b  js      loc_180032A4D
0x1800328a1  lea     rcx, [rbp+57h+ppv]; void *
0x1800328a5  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x1800328aa  nop
0x1800328ab  lea     rdx, [rbp+57h+ppv]; ppv
0x1800328af  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x1800328b6  call    cs:__imp_PSCreateMemoryPropertyStore
0x1800328bc  mov     ebx, eax
0x1800328be  test    eax, eax
0x1800328c0  js      loc_180032A43
0x1800328c6  mov     [rbp+57h+var_A0], 0
0x1800328cd  mov     rcx, [r14+68h]
0x1800328d1  mov     rax, [rcx]
0x1800328d4  lea     rdx, [rbp+57h+var_A0]
0x1800328d8  mov     rax, [rax+18h]
0x1800328dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800328e1  mov     ebx, eax
0x1800328e3  test    eax, eax
0x1800328e5  js      loc_180032A43
0x1800328eb  xor     esi, esi
0x1800328ed  cmp     [rbp+57h+var_A0], esi
0x1800328f0  jle     loc_1800329C6
0x1800328f6  test    ebx, ebx
0x1800328f8  js      loc_180032A43
0x1800328fe  xorps   xmm0, xmm0
0x180032901  xor     eax, eax
0x180032903  movups  [rbp+57h+var_60], xmm0
0x180032907  mov     [rbp+57h+var_50], eax
0x18003290a  mov     rcx, [r14+68h]
0x18003290e  mov     rax, [rcx]
0x180032911  lea     r8, [rbp+57h+var_60]
0x180032915  mov     edx, esi
0x180032917  mov     rax, [rax+20h]
0x18003291b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032920  mov     ebx, eax
0x180032922  test    eax, eax
0x180032924  js      loc_1800329B7
0x18003292a  movups  xmm0, [rbp+57h+var_60]
0x18003292e  movups  [rbp+57h+var_48], xmm0
0x180032932  mov     eax, [rbp+57h+var_50]
0x180032935  mov     [rbp+57h+var_38], eax
0x180032938  lea     rdx, PKEY_ItemId
0x18003293f  lea     rcx, [rbp+57h+var_48]
0x180032943  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x180032948  test    eax, eax
0x18003294a  jz      short loc_180032963
0x18003294c  mov     r8, rdi
0x18003294f  lea     rdx, PKEY_ItemId
0x180032956  mov     rcx, [rbp+57h+ppv]
0x18003295a  call    IPropertyStore_SetItem
0x18003295f  mov     ebx, eax
0x180032961  jmp     short loc_1800329B7
0x180032963  xorps   xmm0, xmm0
0x180032966  xor     eax, eax
0x180032968  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18003296c  mov     [rbp+57h+var_68], rax
0x180032970  mov     rcx, [rbp+57h+var_88]
0x180032974  mov     rax, [rcx]
0x180032977  lea     r8, [rbp+57h+pvar]
0x18003297b  lea     rdx, [rbp+57h+var_48]
0x18003297f  mov     rax, [rax+28h]
0x180032983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032988  lea     rcx, [rbp+57h+ppv]
0x18003298c  call    ??C?$CComPtrBase@UIStartMenuResultSetInternal@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIStartMenuResultSetInternal@@@1@XZ; ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->(void)
0x180032991  mov     r9, rax
0x180032994  mov     rcx, [rax]
0x180032997  mov     rax, [rcx+30h]
0x18003299b  lea     r8, [rbp+57h+pvar]
0x18003299f  lea     rdx, [rbp+57h+var_60]
0x1800329a3  mov     rcx, r9
0x1800329a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800329ab  mov     ebx, eax
0x1800329ad  lea     rcx, [rbp+57h+pvar]; pvar
0x1800329b1  call    cs:__imp_PropVariantClear
0x1800329b7  inc     esi
0x1800329b9  cmp     esi, [rbp+57h+var_A0]
0x1800329bc  jl      loc_1800328F6
0x1800329c2  test    ebx, ebx
0x1800329c4  js      short loc_180032A43
0x1800329c6  mov     [rbp+57h+var_90], 0
0x1800329ce  mov     rax, [rdi]
0x1800329d1  lea     r8, [rbp+57h+var_90]
0x1800329d5  mov     edx, 80028000h
0x1800329da  mov     rcx, rdi
0x1800329dd  mov     rax, [rax+28h]
0x1800329e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800329e6  mov     ebx, eax
0x1800329e8  test    eax, eax
0x1800329ea  js      short loc_180032A02
0x1800329ec  mov     r8, [rbp+57h+var_90]
0x1800329f0  lea     rdx, PKEY_ParsingPath
0x1800329f7  mov     rcx, [rbp+57h+ppv]
0x1800329fb  call    IPropertyStore_SetString
0x180032a00  mov     ebx, eax
0x180032a02  lea     rcx, [rbp+57h+var_90]; void *
0x180032a06  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180032a0b  test    ebx, ebx
0x180032a0d  js      short loc_180032A43
0x180032a0f  mov     r8, rdi
0x180032a12  lea     rdx, PKEY_DelegateIDList
0x180032a19  mov     rcx, [rbp+57h+ppv]
0x180032a1d  call    IPropertyStore_SetItem
0x180032a22  mov     ebx, eax
0x180032a24  test    eax, eax
0x180032a26  js      short loc_180032A43
0x180032a28  mov     rcx, [rbp+57h+ppv]
0x180032a2c  mov     rax, [rcx]
0x180032a2f  mov     r8, r15
0x180032a32  lea     rdx, _GUID_3017056d_9a91_4e90_937d_746c72abbf4f
0x180032a39  mov     rax, [rax]
0x180032a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a41  mov     ebx, eax
0x180032a43  lea     rcx, [rbp+57h+ppv]
0x180032a47  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180032a4c  nop
0x180032a4d  lea     rcx, [rbp+57h+var_88]
0x180032a51  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180032a56  nop
0x180032a57  lea     rcx, [rbp+57h+var_80]; void *
0x180032a5b  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180032a60  mov     eax, ebx
0x180032a62  mov     rcx, [rbp+57h+var_30]
0x180032a66  xor     rcx, rsp; StackCookie
0x180032a69  call    __security_check_cookie
0x180032a6e  mov     rbx, [rsp+0D0h+arg_10]
0x180032a76  add     rsp, 0B0h
0x180032a7d  pop     r15
0x180032a7f  pop     r14
0x180032a81  pop     rdi
0x180032a82  pop     rsi
0x180032a83  pop     rbp
0x180032a84  retn
```
