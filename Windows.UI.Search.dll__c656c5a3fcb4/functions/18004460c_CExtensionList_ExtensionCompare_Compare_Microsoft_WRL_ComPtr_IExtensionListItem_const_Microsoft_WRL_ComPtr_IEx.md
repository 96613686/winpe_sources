# CExtensionList::ExtensionCompare::Compare(Microsoft::WRL::ComPtr<IExtensionListItem> const &,Microsoft::WRL::ComPtr<IExtensionListItem> const &)

- ea: `0x18004460c`
- end: `0x1800447ac`
- name: `?Compare@ExtensionCompare@CExtensionList@@QEBAHAEBV?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@0@Z`
- size: `416`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180043704`
- `0x180043934`

## callees

- `0x180007b3c`
- `0x18003e0d4`
- `0x180043014`
- `0x18004460c`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180044757`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180044761`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180044757`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180044761`
- `PROPSYS!PropVariantCompareEx` at `0x180044743`
- `PROPSYS!PropVariantCompareEx` at `0x180044743`

## pseudocode

```c
__int64 __fastcall CExtensionList::ExtensionCompare::Compare(
        __int64 *a1,
        __int64 (__fastcall ****a2)(_QWORD, GUID *, __int64),
        __int64 (__fastcall ****a3)(_QWORD, GUID *, __int64))
{
  unsigned int v4; // esi
  __int64 v6; // rdi
  int (__fastcall *v7)(__int64, GUID *, __int64 *); // rbx
  __int64 v8; // rdi
  int (__fastcall *v9)(__int64, GUID *, __int64 *); // rbx
  __int64 v10; // rdi
  __int64 v11; // rax
  int v12; // ebx
  __int64 v14; // [rsp+20h] [rbp-50h] BYREF
  __int64 v15; // [rsp+28h] [rbp-48h] BYREF
  __int64 v16; // [rsp+30h] [rbp-40h] BYREF
  PROPVARIANT propvar2[2]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v18; // [rsp+48h] [rbp-28h]
  PROPVARIANT propvar1[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v20; // [rsp+60h] [rbp-10h]
  __int64 v21; // [rsp+A8h] [rbp+38h] BYREF

  v4 = 0;
  v16 = 0;
  v15 = 0;
  if ( (int)Microsoft::WRL::ComPtr<IExtensionListItem>::As<IObjectWithPropertyStore>(a2, (__int64)&v16) >= 0
    && (int)Microsoft::WRL::ComPtr<IExtensionListItem>::As<IObjectWithPropertyStore>(a3, (__int64)&v15) >= 0 )
  {
    v6 = v16;
    v14 = 0;
    v21 = 0;
    v7 = *(int (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v16 + 24LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v14);
    if ( v7(v6, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &v14) >= 0 )
    {
      v8 = v15;
      v9 = *(int (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v15 + 24LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v21);
      if ( v9(v8, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &v21) >= 0 )
      {
        v10 = 0;
        do
        {
          if ( (unsigned int)v10 >= *((_DWORD *)a1 + 2) )
            break;
          v20 = 0;
          v18 = 0;
          v11 = *a1;
          *(_OWORD *)propvar1 = 0;
          *(_OWORD *)propvar2 = 0;
          if ( (*(int (__fastcall **)(__int64, __int64, PROPVARIANT *))(*(_QWORD *)v14 + 40LL))(
                 v14,
                 v11 + 24 * v10,
                 propvar1) >= 0
            && (*(int (__fastcall **)(__int64, __int64, PROPVARIANT *))(*(_QWORD *)v21 + 40LL))(
                 v21,
                 *a1 + 24 * v10,
                 propvar2) >= 0 )
          {
            v12 = *(_DWORD *)(*a1 + 24 * v10 + 20);
            v4 = PropVariantCompareEx(propvar1, propvar2, PVCU_DEFAULT, 0);
            if ( v12 != 1 )
              v4 = -v4;
          }
          PropVariantClear(propvar2);
          PropVariantClear(propvar1);
          v10 = (unsigned int)(v10 + 1);
        }
        while ( !v4 );
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v21);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v14);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(&v15);
  Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(&v16);
  return v4;
}

```

## disassembly

```asm
0x18004460c  mov     [rsp-18h+arg_0], rbx
0x180044611  mov     [rsp-18h+arg_8], rsi
0x180044616  push    rbp
0x180044617  push    rdi
0x180044618  push    r14
0x18004461a  mov     rbp, rsp
0x18004461d  sub     rsp, 70h
0x180044621  mov     rax, rdx
0x180044624  mov     r14, rcx
0x180044627  xor     esi, esi
0x180044629  lea     rdx, [rbp+var_40]
0x18004462d  mov     rcx, rax
0x180044630  mov     [rbp+var_40], rsi
0x180044634  mov     rbx, r8
0x180044637  mov     [rbp+var_48], rsi
0x18004463b  call    ??$As@UIObjectWithPropertyStore@@@?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIObjectWithPropertyStore@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IExtensionListItem>::As<IObjectWithPropertyStore>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IObjectWithPropertyStore>>)
0x180044640  test    eax, eax
0x180044642  js      loc_180044783
0x180044648  lea     rdx, [rbp+var_48]
0x18004464c  mov     rcx, rbx
0x18004464f  call    ??$As@UIObjectWithPropertyStore@@@?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIObjectWithPropertyStore@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IExtensionListItem>::As<IObjectWithPropertyStore>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IObjectWithPropertyStore>>)
0x180044654  test    eax, eax
0x180044656  js      loc_180044783
0x18004465c  mov     rdi, [rbp+var_40]
0x180044660  lea     rcx, [rbp+var_50]
0x180044664  mov     [rbp+var_50], rsi
0x180044668  mov     [rbp+arg_18], rsi
0x18004466c  mov     rax, [rdi]
0x18004466f  mov     rbx, [rax+18h]
0x180044673  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180044678  lea     r8, [rbp+var_50]
0x18004467c  mov     rcx, rdi
0x18004467f  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180044686  mov     rax, rbx
0x180044689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004468e  test    eax, eax
0x180044690  js      loc_180044771
0x180044696  mov     rdi, [rbp+var_48]
0x18004469a  lea     rcx, [rbp+arg_18]
0x18004469e  mov     rax, [rdi]
0x1800446a1  mov     rbx, [rax+18h]
0x1800446a5  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800446aa  lea     r8, [rbp+arg_18]
0x1800446ae  mov     rcx, rdi
0x1800446b1  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x1800446b8  mov     rax, rbx
0x1800446bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800446c0  test    eax, eax
0x1800446c2  js      loc_180044771
0x1800446c8  xor     edi, edi
0x1800446ca  cmp     edi, [r14+8]
0x1800446ce  jnb     loc_180044771
0x1800446d4  mov     rcx, [rbp+var_50]
0x1800446d8  lea     rbx, [rdi+rdi*2]
0x1800446dc  xor     eax, eax
0x1800446de  xorps   xmm0, xmm0
0x1800446e1  mov     [rbp+var_10], rax
0x1800446e5  xorps   xmm1, xmm1
0x1800446e8  mov     [rbp+var_28], rax
0x1800446ec  mov     rax, [r14]
0x1800446ef  movups  xmmword ptr [rbp+propvar1], xmm0
0x1800446f3  movups  xmmword ptr [rbp+propvar2], xmm1
0x1800446f7  mov     r8, [rcx]
0x1800446fa  lea     rdx, [rax+rbx*8]
0x1800446fe  mov     rax, [r8+28h]
0x180044702  lea     r8, [rbp+propvar1]
0x180044706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004470b  test    eax, eax
0x18004470d  js      short loc_180044753
0x18004470f  mov     rax, [r14]
0x180044712  mov     rcx, [rbp+arg_18]
0x180044716  lea     rdx, [rax+rbx*8]
0x18004471a  mov     r8, [rcx]
0x18004471d  mov     rax, [r8+28h]
0x180044721  lea     r8, [rbp+propvar2]
0x180044725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004472a  test    eax, eax
0x18004472c  js      short loc_180044753
0x18004472e  mov     rax, [r14]
0x180044731  lea     rdx, [rbp+propvar2]; propvar2
0x180044735  xor     r9d, r9d; flags
0x180044738  lea     rcx, [rbp+propvar1]; propvar1
0x18004473c  xor     r8d, r8d; unit
0x18004473f  mov     ebx, [rax+rbx*8+14h]
0x180044743  call    cs:__imp_PropVariantCompareEx
0x180044749  mov     esi, eax
0x18004474b  neg     eax
0x18004474d  cmp     ebx, 1
0x180044750  cmovnz  esi, eax
0x180044753  lea     rcx, [rbp+propvar2]; pvar
0x180044757  call    cs:__imp_PropVariantClear
0x18004475d  lea     rcx, [rbp+propvar1]; pvar
0x180044761  call    cs:__imp_PropVariantClear
0x180044767  inc     edi
0x180044769  test    esi, esi
0x18004476b  jz      loc_1800446CA
0x180044771  lea     rcx, [rbp+arg_18]
0x180044775  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18004477a  lea     rcx, [rbp+var_50]
0x18004477e  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180044783  lea     rcx, [rbp+var_48]
0x180044787  call    ?InternalRelease@?$ComPtr@UIExtensionRegistration@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(void)
0x18004478c  lea     rcx, [rbp+var_40]
0x180044790  call    ?InternalRelease@?$ComPtr@UIExtensionRegistration@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(void)
0x180044795  lea     r11, [rsp+70h+var_s0]
0x18004479a  mov     eax, esi
0x18004479c  mov     rbx, [r11+20h]
0x1800447a0  mov     rsi, [r11+28h]
0x1800447a4  mov     rsp, r11
0x1800447a7  pop     r14
0x1800447a9  pop     rdi
0x1800447aa  pop     rbp
0x1800447ab  retn
```
