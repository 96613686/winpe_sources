# CExtensionListItem::_EnsurePropertyStore(void)

- ea: `0x180067f84`
- end: `0x1800681f0`
- name: `?_EnsurePropertyStore@CExtensionListItem@@AEAAJXZ`
- size: `620`
- prototype: `__int64 __fastcall(CExtensionListItem *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180064d60`

## callees

- `0x180003e30`
- `0x180004c98`
- `0x1800332f0`
- `0x180061b4c`
- `0x180067f84`
- `0x1800685e4`
- `0x1800689d8`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006817d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006817d`
- `PROPSYS!InitPropVariantFromStringAsVector` at `0x180068152`
- `PROPSYS!InitPropVariantFromStringAsVector` at `0x180068152`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180067fe8`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180067fe8`

## pseudocode

```c
__int64 __fastcall CExtensionListItem::_EnsurePropertyStore(CExtensionListItem *this)
{
  char *v2; // r15
  HRESULT MFURank; // ebx
  bool v4; // zf
  unsigned __int64 v5; // rdi
  void *v6; // rdi
  __int64 (__fastcall *v7)(void *, GUID *, char *); // rbx
  PROPVARIANT ppropvar[2]; // [rsp+20h] [rbp-20h] BYREF
  __int64 v10; // [rsp+30h] [rbp-10h]
  void *ppv; // [rsp+70h] [rbp+30h] BYREF
  PCWSTR psz; // [rsp+78h] [rbp+38h] BYREF

  if ( *((_QWORD *)this + 4) )
  {
    v2 = (char *)this + 48;
    if ( !*((_QWORD *)this + 6) || (MFURank = 0, *((_BYTE *)this + 584)) )
    {
      ppv = 0;
      Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(&ppv);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&ppv);
      MFURank = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
      if ( MFURank >= 0 )
      {
        v4 = (*((_BYTE *)this + 576) & 1) == 0;
        LOWORD(ppropvar[0]) = 11;
        LOWORD(ppropvar[1]) = v4 ? 0 : -1;
        MFURank = (*(__int64 (__fastcall **)(void *, __int64 *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                    ppv,
                    PKEY_AppContract_Pinned,
                    ppropvar);
        if ( MFURank >= 0 )
        {
          v4 = (*((_BYTE *)this + 576) & 2) == 0;
          LOWORD(ppropvar[0]) = 11;
          LOWORD(ppropvar[1]) = v4 ? 0 : -1;
          MFURank = (*(__int64 (__fastcall **)(void *, __int64 *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                      ppv,
                      PKEY_AppContract_Hidden,
                      ppropvar);
          if ( MFURank >= 0 )
          {
            LOWORD(ppropvar[0]) = 19;
            LODWORD(ppropvar[1]) = *((_DWORD *)this + 145);
            MFURank = (*(__int64 (__fastcall **)(void *, __int64 *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                        ppv,
                        PKEY_AppContract_PinnedOrder,
                        ppropvar);
            if ( MFURank >= 0 )
            {
              psz = 0;
              MFURank = CExtensionListItem::_GetMFURank(this, (double *)&psz);
              if ( MFURank >= 0 )
              {
                ppropvar[1] = (PROPVARIANT)psz;
                LOWORD(ppropvar[0]) = 5;
                MFURank = (*(__int64 (__fastcall **)(void *, __int64 *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                            ppv,
                            PKEY_AppContract_Relevance,
                            ppropvar);
                if ( MFURank >= 0 )
                {
                  v5 = 0;
                  while ( v5 < 4 )
                  {
                    psz = 0;
                    if ( CExtensionListItem::_GetCustomStringProperty(
                           this,
                           (&off_180091220)[2 * v5],
                           (unsigned __int16 **)&psz) >= 0 )
                    {
                      *(_OWORD *)ppropvar = 0;
                      v10 = 0;
                      MFURank = InitPropVariantFromStringAsVector(psz, ppropvar);
                      if ( MFURank >= 0 )
                      {
                        MFURank = (*(__int64 (__fastcall **)(void *, _QWORD, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                                    ppv,
                                    *(&off_180091220 + 2 * v5 + 1),
                                    ppropvar);
                        PropVariantClear(ppropvar);
                      }
                    }
                    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&psz);
                    ++v5;
                    if ( MFURank < 0 )
                      goto LABEL_24;
                  }
                  v6 = ppv;
                  v7 = **(__int64 (__fastcall ***)(void *, GUID *, char *))ppv;
                  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v2);
                  MFURank = v7(v6, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, v2);
                  *((_BYTE *)this + 584) = 0;
                }
              }
            }
          }
        }
      }
LABEL_24:
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(&ppv);
    }
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return (unsigned int)MFURank;
}

```

## disassembly

```asm
0x180067f84  mov     [rsp-28h+arg_10], rbx
0x180067f89  mov     [rsp-28h+arg_18], rsi
0x180067f8e  push    rbp
0x180067f8f  push    rdi
0x180067f90  push    r13
0x180067f92  push    r14
0x180067f94  push    r15
0x180067f96  mov     rbp, rsp
0x180067f99  sub     rsp, 40h
0x180067f9d  cmp     qword ptr [rcx+20h], 0
0x180067fa2  mov     rsi, rcx
0x180067fa5  jz      loc_1800681D0
0x180067fab  lea     r15, [rcx+30h]
0x180067faf  cmp     qword ptr [r15], 0
0x180067fb3  jz      short loc_180067FC3
0x180067fb5  xor     ebx, ebx
0x180067fb7  cmp     [rcx+248h], bl
0x180067fbd  jz      loc_1800681D5
0x180067fc3  lea     rcx, [rbp+ppv]
0x180067fc7  mov     [rbp+ppv], 0
0x180067fcf  call    ?InternalAddRef@?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(void)
0x180067fd4  lea     rcx, [rbp+ppv]
0x180067fd8  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180067fdd  lea     rdx, [rbp+ppv]; ppv
0x180067fe1  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180067fe8  call    cs:__imp_PSCreateMemoryPropertyStore
0x180067fee  mov     ebx, eax
0x180067ff0  test    eax, eax
0x180067ff2  js      loc_1800681C5
0x180067ff8  or      r14d, 0FFFFFFFFh
0x180067ffc  test    byte ptr [rsi+240h], 1
0x180068003  lea     edi, [r14+0Ch]
0x180068007  mov     word ptr [rbp+ppropvar], di
0x18006800b  jz      short loc_180068014
0x18006800d  mov     word ptr [rbp+ppropvar+8], r14w
0x180068012  jmp     short loc_18006801A
0x180068014  xor     eax, eax
0x180068016  mov     word ptr [rbp+ppropvar+8], ax
0x18006801a  mov     rcx, [rbp+ppv]
0x18006801e  lea     r8, [rbp+ppropvar]
0x180068022  lea     rdx, PKEY_AppContract_Pinned
0x180068029  mov     rax, [rcx]
0x18006802c  mov     rax, [rax+30h]
0x180068030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068035  mov     ebx, eax
0x180068037  test    eax, eax
0x180068039  js      loc_1800681C5
0x18006803f  test    byte ptr [rsi+240h], 2
0x180068046  mov     word ptr [rbp+ppropvar], di
0x18006804a  jz      short loc_180068053
0x18006804c  mov     word ptr [rbp+ppropvar+8], r14w
0x180068051  jmp     short loc_180068059
0x180068053  xor     eax, eax
0x180068055  mov     word ptr [rbp+ppropvar+8], ax
0x180068059  mov     rcx, [rbp+ppv]
0x18006805d  lea     r8, [rbp+ppropvar]
0x180068061  lea     rdx, PKEY_AppContract_Hidden
0x180068068  mov     rax, [rcx]
0x18006806b  mov     rax, [rax+30h]
0x18006806f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068074  mov     ebx, eax
0x180068076  test    eax, eax
0x180068078  js      loc_1800681C5
0x18006807e  mov     rcx, [rbp+ppv]
0x180068082  lea     r8, [rbp+ppropvar]
0x180068086  mov     eax, 13h
0x18006808b  lea     rdx, PKEY_AppContract_PinnedOrder
0x180068092  mov     word ptr [rbp+ppropvar], ax
0x180068096  mov     eax, [rsi+244h]
0x18006809c  mov     dword ptr [rbp+ppropvar+8], eax
0x18006809f  mov     rax, [rcx]
0x1800680a2  mov     rax, [rax+30h]
0x1800680a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800680ab  mov     ebx, eax
0x1800680ad  test    eax, eax
0x1800680af  js      loc_1800681C5
0x1800680b5  xorps   xmm0, xmm0
0x1800680b8  lea     rdx, [rbp+psz]; double *
0x1800680bc  mov     rcx, rsi; this
0x1800680bf  movsd   [rbp+psz], xmm0
0x1800680c4  call    ?_GetMFURank@CExtensionListItem@@AEAAJPEAN@Z; CExtensionListItem::_GetMFURank(double *)
0x1800680c9  mov     ebx, eax
0x1800680cb  test    eax, eax
0x1800680cd  js      loc_1800681C5
0x1800680d3  mov     rcx, [rbp+ppv]
0x1800680d7  lea     r8, [rbp+ppropvar]
0x1800680db  movsd   xmm0, [rbp+psz]
0x1800680e0  lea     rdx, PKEY_AppContract_Relevance
0x1800680e7  mov     eax, 5
0x1800680ec  movsd   [rbp+ppropvar+8], xmm0
0x1800680f1  mov     word ptr [rbp+ppropvar], ax
0x1800680f5  mov     rax, [rcx]
0x1800680f8  mov     rax, [rax+30h]
0x1800680fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068101  mov     ebx, eax
0x180068103  test    eax, eax
0x180068105  js      loc_1800681C5
0x18006810b  xor     edi, edi
0x18006810d  lea     r13, off_180091220; "ApplicationCategories"
0x180068114  cmp     rdi, 4
0x180068118  jnb     short loc_180068195
0x18006811a  mov     r14, rdi
0x18006811d  mov     [rbp+psz], 0
0x180068125  add     r14, r14
0x180068128  lea     r8, [rbp+psz]; unsigned __int16 **
0x18006812c  mov     rcx, rsi; this
0x18006812f  mov     rdx, [r13+r14*8+0]; unsigned __int16 *
0x180068134  call    ?_GetCustomStringProperty@CExtensionListItem@@AEAAJPEBGPEAPEAG@Z; CExtensionListItem::_GetCustomStringProperty(ushort const *,ushort * *)
0x180068139  test    eax, eax
0x18006813b  js      short loc_180068183
0x18006813d  mov     rcx, [rbp+psz]; psz
0x180068141  lea     rdx, [rbp+ppropvar]; ppropvar
0x180068145  xorps   xmm0, xmm0
0x180068148  xor     eax, eax
0x18006814a  movups  xmmword ptr [rbp+ppropvar], xmm0
0x18006814e  mov     [rbp+var_10], rax
0x180068152  call    cs:__imp_InitPropVariantFromStringAsVector
0x180068158  mov     ebx, eax
0x18006815a  test    eax, eax
0x18006815c  js      short loc_180068183
0x18006815e  mov     rcx, [rbp+ppv]
0x180068162  lea     r8, [rbp+ppropvar]
0x180068166  mov     rdx, [r13+r14*8+8]
0x18006816b  mov     rax, [rcx]
0x18006816e  mov     rax, [rax+30h]
0x180068172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068177  lea     rcx, [rbp+ppropvar]; pvar
0x18006817b  mov     ebx, eax
0x18006817d  call    cs:__imp_PropVariantClear
0x180068183  lea     rcx, [rbp+psz]
0x180068187  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18006818c  inc     rdi
0x18006818f  test    ebx, ebx
0x180068191  jns     short loc_180068114
0x180068193  jmp     short loc_1800681C5
0x180068195  mov     rdi, [rbp+ppv]
0x180068199  mov     rcx, r15
0x18006819c  mov     rax, [rdi]
0x18006819f  mov     rbx, [rax]
0x1800681a2  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800681a7  mov     r8, r15
0x1800681aa  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x1800681b1  mov     rcx, rdi
0x1800681b4  mov     rax, rbx
0x1800681b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800681bc  mov     ebx, eax
0x1800681be  mov     byte ptr [rsi+248h], 0
0x1800681c5  lea     rcx, [rbp+ppv]; void *
0x1800681c9  call    ??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(void)
0x1800681ce  jmp     short loc_1800681D5
0x1800681d0  mov     ebx, 8000FFFFh
0x1800681d5  lea     r11, [rsp+40h+var_s0]
0x1800681da  mov     eax, ebx
0x1800681dc  mov     rbx, [r11+40h]
0x1800681e0  mov     rsi, [r11+48h]
0x1800681e4  mov     rsp, r11
0x1800681e7  pop     r15
0x1800681e9  pop     r14
0x1800681eb  pop     r13
0x1800681ed  pop     rdi
0x1800681ee  pop     rbp
0x1800681ef  retn
```
