# CExtensionListItem::_EnsurePropertyStore(void)

- ea: `0x1800491a8`
- end: `0x18004940d`
- name: `?_EnsurePropertyStore@CExtensionListItem@@AEAAJXZ`
- size: `613`
- prototype: `__int64 __fastcall(CExtensionListItem *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180046010`

## callees

- `0x180007b3c`
- `0x180014f58`
- `0x18003e3a8`
- `0x1800491a8`
- `0x1800496b4`
- `0x18004992c`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180049399`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180049399`
- `PROPSYS!InitPropVariantFromStringAsVector` at `0x18004936e`
- `PROPSYS!InitPropVariantFromStringAsVector` at `0x18004936e`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180049204`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180049204`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CExtensionListItem::_EnsurePropertyStore(CExtensionListItem *this, struct IPropertyStore *a2)
{
  char *v3; // r15
  HRESULT MFURank; // ebx
  unsigned __int64 v5; // rdi
  void *v6; // rdi
  __int64 (__fastcall *v7)(void *, GUID *, char *); // rbx
  PROPVARIANT ppropvar[2]; // [rsp+20h] [rbp-20h] BYREF
  __int64 v10; // [rsp+30h] [rbp-10h]
  void *ppv; // [rsp+70h] [rbp+30h] BYREF
  PCWSTR psz; // [rsp+78h] [rbp+38h] BYREF

  if ( *((_QWORD *)this + 4) )
  {
    v3 = (char *)this + 48;
    if ( !*((_QWORD *)this + 6) || (MFURank = 0, *((_BYTE *)this + 584)) )
    {
      wil::PropertyStoreHelper::PropertyStoreHelper((wil::PropertyStoreHelper *)&ppv, a2);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
      MFURank = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
      if ( MFURank >= 0 )
      {
        LOWORD(ppropvar[0]) = 11;
        LOWORD(ppropvar[1]) = (*((_BYTE *)this + 576) & 1) != 0 ? -1 : 0;
        MFURank = (*(__int64 (__fastcall **)(void *, __int64 *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                    ppv,
                    PKEY_AppContract_Pinned,
                    ppropvar);
        if ( MFURank >= 0 )
        {
          LOWORD(ppropvar[0]) = 11;
          LOWORD(ppropvar[1]) = (*((_BYTE *)this + 576) & 2) != 0 ? -1 : 0;
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
                LOWORD(ppropvar[0]) = 5;
                ppropvar[1] = (PROPVARIANT)psz;
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
                    if ( (int)CExtensionListItem::_GetCustomStringProperty(
                                this,
                                (&off_1800A92E0)[2 * v5],
                                (unsigned __int16 **)&psz) >= 0 )
                    {
                      *(_OWORD *)ppropvar = 0;
                      v10 = 0;
                      MFURank = InitPropVariantFromStringAsVector(psz, ppropvar);
                      if ( MFURank >= 0 )
                      {
                        MFURank = (*(__int64 (__fastcall **)(void *, _QWORD, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                                    ppv,
                                    *(&off_1800A92E0 + 2 * v5 + 1),
                                    ppropvar);
                        PropVariantClear(ppropvar);
                      }
                    }
                    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>((void **)&psz);
                    ++v5;
                    if ( MFURank < 0 )
                      goto LABEL_24;
                  }
                  v6 = ppv;
                  v7 = **(__int64 (__fastcall ***)(void *, GUID *, char *))ppv;
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(v3);
                  MFURank = v7(v6, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, v3);
                  *((_BYTE *)this + 584) = 0;
                }
              }
            }
          }
        }
      }
LABEL_24:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
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
0x1800491a8  mov     [rsp-28h+arg_10], rbx
0x1800491ad  mov     [rsp-28h+arg_18], rsi
0x1800491b2  push    rbp
0x1800491b3  push    rdi
0x1800491b4  push    r13
0x1800491b6  push    r14
0x1800491b8  push    r15
0x1800491ba  mov     rbp, rsp
0x1800491bd  sub     rsp, 40h
0x1800491c1  mov     rsi, rcx
0x1800491c4  cmp     qword ptr [rcx+20h], 0
0x1800491c9  jz      loc_1800493ED
0x1800491cf  lea     r15, [rcx+30h]
0x1800491d3  cmp     qword ptr [r15], 0
0x1800491d7  jz      short loc_1800491E7
0x1800491d9  xor     ebx, ebx
0x1800491db  cmp     [rcx+248h], bl
0x1800491e1  jz      loc_1800493F2
0x1800491e7  lea     rcx, [rbp+ppv]; this
0x1800491eb  call    ??0PropertyStoreHelper@wil@@QEAA@PEAUIPropertyStore@@@Z; wil::PropertyStoreHelper::PropertyStoreHelper(IPropertyStore *)
0x1800491f0  lea     rcx, [rbp+ppv]
0x1800491f4  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800491f9  lea     rdx, [rbp+ppv]; ppv
0x1800491fd  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180049204  call    cs:__imp_PSCreateMemoryPropertyStore
0x18004920a  mov     ebx, eax
0x18004920c  test    eax, eax
0x18004920e  js      loc_1800493E1
0x180049214  or      r14d, 0FFFFFFFFh
0x180049218  lea     edi, [r14+0Ch]
0x18004921c  mov     word ptr [rbp+ppropvar], di
0x180049220  test    byte ptr [rsi+240h], 1
0x180049227  jz      short loc_180049230
0x180049229  mov     word ptr [rbp+ppropvar+8], r14w
0x18004922e  jmp     short loc_180049236
0x180049230  xor     eax, eax
0x180049232  mov     word ptr [rbp+ppropvar+8], ax
0x180049236  mov     rcx, [rbp+ppv]
0x18004923a  mov     rax, [rcx]
0x18004923d  lea     r8, [rbp+ppropvar]
0x180049241  lea     rdx, PKEY_AppContract_Pinned
0x180049248  mov     rax, [rax+30h]
0x18004924c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049251  mov     ebx, eax
0x180049253  test    eax, eax
0x180049255  js      loc_1800493E1
0x18004925b  mov     word ptr [rbp+ppropvar], di
0x18004925f  test    byte ptr [rsi+240h], 2
0x180049266  jz      short loc_18004926F
0x180049268  mov     word ptr [rbp+ppropvar+8], r14w
0x18004926d  jmp     short loc_180049275
0x18004926f  xor     eax, eax
0x180049271  mov     word ptr [rbp+ppropvar+8], ax
0x180049275  mov     rcx, [rbp+ppv]
0x180049279  mov     rax, [rcx]
0x18004927c  lea     r8, [rbp+ppropvar]
0x180049280  lea     rdx, PKEY_AppContract_Hidden
0x180049287  mov     rax, [rax+30h]
0x18004928b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049290  mov     ebx, eax
0x180049292  test    eax, eax
0x180049294  js      loc_1800493E1
0x18004929a  mov     eax, 13h
0x18004929f  mov     word ptr [rbp+ppropvar], ax
0x1800492a3  mov     eax, [rsi+244h]
0x1800492a9  mov     dword ptr [rbp+ppropvar+8], eax
0x1800492ac  mov     rcx, [rbp+ppv]
0x1800492b0  mov     rax, [rcx]
0x1800492b3  lea     r8, [rbp+ppropvar]
0x1800492b7  lea     rdx, PKEY_AppContract_PinnedOrder
0x1800492be  mov     rax, [rax+30h]
0x1800492c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800492c7  mov     ebx, eax
0x1800492c9  test    eax, eax
0x1800492cb  js      loc_1800493E1
0x1800492d1  xorps   xmm0, xmm0
0x1800492d4  movsd   [rbp+psz], xmm0
0x1800492d9  lea     rdx, [rbp+psz]; double *
0x1800492dd  mov     rcx, rsi; this
0x1800492e0  call    ?_GetMFURank@CExtensionListItem@@AEAAJPEAN@Z; CExtensionListItem::_GetMFURank(double *)
0x1800492e5  mov     ebx, eax
0x1800492e7  test    eax, eax
0x1800492e9  js      loc_1800493E1
0x1800492ef  mov     eax, 5
0x1800492f4  mov     word ptr [rbp+ppropvar], ax
0x1800492f8  movsd   xmm0, [rbp+psz]
0x1800492fd  movsd   [rbp+ppropvar+8], xmm0
0x180049302  mov     rcx, [rbp+ppv]
0x180049306  mov     rax, [rcx]
0x180049309  lea     r8, [rbp+ppropvar]
0x18004930d  lea     rdx, PKEY_AppContract_Relevance
0x180049314  mov     rax, [rax+30h]
0x180049318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004931d  mov     ebx, eax
0x18004931f  test    eax, eax
0x180049321  js      loc_1800493E1
0x180049327  xor     edi, edi
0x180049329  lea     r13, off_1800A92E0; "ApplicationCategories"
0x180049330  cmp     rdi, 4
0x180049334  jnb     short loc_1800493B1
0x180049336  mov     [rbp+psz], 0
0x18004933e  mov     r14, rdi
0x180049341  add     r14, r14
0x180049344  lea     r8, [rbp+psz]; unsigned __int16 **
0x180049348  mov     rdx, [r13+r14*8+0]; unsigned __int16 *
0x18004934d  mov     rcx, rsi; this
0x180049350  call    ?_GetCustomStringProperty@CExtensionListItem@@AEAAJPEBGPEAPEAG@Z; CExtensionListItem::_GetCustomStringProperty(ushort const *,ushort * *)
0x180049355  test    eax, eax
0x180049357  js      short loc_18004939F
0x180049359  xorps   xmm0, xmm0
0x18004935c  xor     eax, eax
0x18004935e  movups  xmmword ptr [rbp+ppropvar], xmm0
0x180049362  mov     [rbp+var_10], rax
0x180049366  lea     rdx, [rbp+ppropvar]; ppropvar
0x18004936a  mov     rcx, [rbp+psz]; psz
0x18004936e  call    cs:__imp_InitPropVariantFromStringAsVector
0x180049374  mov     ebx, eax
0x180049376  test    eax, eax
0x180049378  js      short loc_18004939F
0x18004937a  mov     rcx, [rbp+ppv]
0x18004937e  mov     rax, [rcx]
0x180049381  lea     r8, [rbp+ppropvar]
0x180049385  mov     rdx, [r13+r14*8+8]
0x18004938a  mov     rax, [rax+30h]
0x18004938e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049393  mov     ebx, eax
0x180049395  lea     rcx, [rbp+ppropvar]; pvar
0x180049399  call    cs:__imp_PropVariantClear
0x18004939f  lea     rcx, [rbp+psz]
0x1800493a3  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800493a8  inc     rdi
0x1800493ab  test    ebx, ebx
0x1800493ad  jns     short loc_180049330
0x1800493af  jmp     short loc_1800493E1
0x1800493b1  mov     rdi, [rbp+ppv]
0x1800493b5  mov     rax, [rdi]
0x1800493b8  mov     rbx, [rax]
0x1800493bb  mov     rcx, r15
0x1800493be  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800493c3  mov     r8, r15
0x1800493c6  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x1800493cd  mov     rcx, rdi
0x1800493d0  mov     rax, rbx
0x1800493d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800493d8  mov     ebx, eax
0x1800493da  mov     byte ptr [rsi+248h], 0
0x1800493e1  lea     rcx, [rbp+ppv]
0x1800493e5  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800493ea  nop
0x1800493eb  jmp     short loc_1800493F2
0x1800493ed  mov     ebx, 8000FFFFh
0x1800493f2  mov     eax, ebx
0x1800493f4  lea     r11, [rsp+40h+var_s0]
0x1800493f9  mov     rbx, [r11+40h]
0x1800493fd  mov     rsi, [r11+48h]
0x180049401  mov     rsp, r11
0x180049404  pop     r15
0x180049406  pop     r14
0x180049408  pop     r13
0x18004940a  pop     rdi
0x18004940b  pop     rbp
0x18004940c  retn
```
