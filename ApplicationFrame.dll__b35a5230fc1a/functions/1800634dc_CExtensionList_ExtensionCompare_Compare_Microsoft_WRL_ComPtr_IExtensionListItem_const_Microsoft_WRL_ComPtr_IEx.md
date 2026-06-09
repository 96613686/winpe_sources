# CExtensionList::ExtensionCompare::Compare(Microsoft::WRL::ComPtr<IExtensionListItem> const &,Microsoft::WRL::ComPtr<IExtensionListItem> const &)

- ea: `0x1800634dc`
- end: `0x18006367c`
- name: `?Compare@ExtensionCompare@CExtensionList@@QEBAHAEBV?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@0@Z`
- size: `416`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006229c`
- `0x1800624cc`

## callees

- `0x180004c98`
- `0x18003f150`
- `0x180061ce4`
- `0x1800634dc`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180063627`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180063631`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180063627`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180063631`
- `PROPSYS!PropVariantCompareEx` at `0x180063613`
- `PROPSYS!PropVariantCompareEx` at `0x180063613`

## pseudocode

```c
__int64 __fastcall CExtensionList::ExtensionCompare::Compare(__int64 *a1, __int64 a2, __int64 a3)
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
  if ( (int)Microsoft::WRL::ComPtr<IExtensionListItem>::As<IObjectWithPropertyStore>(a2, &v16) >= 0
    && (int)Microsoft::WRL::ComPtr<IExtensionListItem>::As<IObjectWithPropertyStore>(a3, &v15) >= 0 )
  {
    v6 = v16;
    v14 = 0;
    v21 = 0;
    v7 = *(int (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v16 + 24LL);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v14);
    if ( v7(v6, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &v14) >= 0 )
    {
      v8 = v15;
      v9 = *(int (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v15 + 24LL);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v21);
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
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v21);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v14);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(&v15);
  Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(&v16);
  return v4;
}

```

## disassembly

```asm
0x1800634dc  mov     [rsp-18h+arg_0], rbx
0x1800634e1  mov     [rsp-18h+arg_8], rsi
0x1800634e6  push    rbp
0x1800634e7  push    rdi
0x1800634e8  push    r14
0x1800634ea  mov     rbp, rsp
0x1800634ed  sub     rsp, 70h
0x1800634f1  mov     rax, rdx
0x1800634f4  mov     r14, rcx
0x1800634f7  xor     esi, esi
0x1800634f9  lea     rdx, [rbp+var_40]
0x1800634fd  mov     rcx, rax
0x180063500  mov     [rbp+var_40], rsi
0x180063504  mov     rbx, r8
0x180063507  mov     [rbp+var_48], rsi
0x18006350b  call    ??$As@UIObjectWithPropertyStore@@@?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIObjectWithPropertyStore@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IExtensionListItem>::As<IObjectWithPropertyStore>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IObjectWithPropertyStore>>)
0x180063510  test    eax, eax
0x180063512  js      loc_180063653
0x180063518  lea     rdx, [rbp+var_48]
0x18006351c  mov     rcx, rbx
0x18006351f  call    ??$As@UIObjectWithPropertyStore@@@?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIObjectWithPropertyStore@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IExtensionListItem>::As<IObjectWithPropertyStore>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IObjectWithPropertyStore>>)
0x180063524  test    eax, eax
0x180063526  js      loc_180063653
0x18006352c  mov     rdi, [rbp+var_40]
0x180063530  lea     rcx, [rbp+var_50]
0x180063534  mov     [rbp+var_50], rsi
0x180063538  mov     [rbp+arg_18], rsi
0x18006353c  mov     rax, [rdi]
0x18006353f  mov     rbx, [rax+18h]
0x180063543  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180063548  lea     r8, [rbp+var_50]
0x18006354c  mov     rcx, rdi
0x18006354f  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180063556  mov     rax, rbx
0x180063559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006355e  test    eax, eax
0x180063560  js      loc_180063641
0x180063566  mov     rdi, [rbp+var_48]
0x18006356a  lea     rcx, [rbp+arg_18]
0x18006356e  mov     rax, [rdi]
0x180063571  mov     rbx, [rax+18h]
0x180063575  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18006357a  lea     r8, [rbp+arg_18]
0x18006357e  mov     rcx, rdi
0x180063581  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180063588  mov     rax, rbx
0x18006358b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063590  test    eax, eax
0x180063592  js      loc_180063641
0x180063598  xor     edi, edi
0x18006359a  cmp     edi, [r14+8]
0x18006359e  jnb     loc_180063641
0x1800635a4  mov     rcx, [rbp+var_50]
0x1800635a8  lea     rbx, [rdi+rdi*2]
0x1800635ac  xor     eax, eax
0x1800635ae  xorps   xmm0, xmm0
0x1800635b1  mov     [rbp+var_10], rax
0x1800635b5  xorps   xmm1, xmm1
0x1800635b8  mov     [rbp+var_28], rax
0x1800635bc  mov     rax, [r14]
0x1800635bf  movups  xmmword ptr [rbp+propvar1], xmm0
0x1800635c3  movups  xmmword ptr [rbp+propvar2], xmm1
0x1800635c7  mov     r8, [rcx]
0x1800635ca  lea     rdx, [rax+rbx*8]
0x1800635ce  mov     rax, [r8+28h]
0x1800635d2  lea     r8, [rbp+propvar1]
0x1800635d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800635db  test    eax, eax
0x1800635dd  js      short loc_180063623
0x1800635df  mov     rax, [r14]
0x1800635e2  mov     rcx, [rbp+arg_18]
0x1800635e6  lea     rdx, [rax+rbx*8]
0x1800635ea  mov     r8, [rcx]
0x1800635ed  mov     rax, [r8+28h]
0x1800635f1  lea     r8, [rbp+propvar2]
0x1800635f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800635fa  test    eax, eax
0x1800635fc  js      short loc_180063623
0x1800635fe  mov     rax, [r14]
0x180063601  lea     rdx, [rbp+propvar2]; propvar2
0x180063605  xor     r9d, r9d; flags
0x180063608  lea     rcx, [rbp+propvar1]; propvar1
0x18006360c  xor     r8d, r8d; unit
0x18006360f  mov     ebx, [rax+rbx*8+14h]
0x180063613  call    cs:__imp_PropVariantCompareEx
0x180063619  mov     esi, eax
0x18006361b  neg     eax
0x18006361d  cmp     ebx, 1
0x180063620  cmovnz  esi, eax
0x180063623  lea     rcx, [rbp+propvar2]; pvar
0x180063627  call    cs:__imp_PropVariantClear
0x18006362d  lea     rcx, [rbp+propvar1]; pvar
0x180063631  call    cs:__imp_PropVariantClear
0x180063637  inc     edi
0x180063639  test    esi, esi
0x18006363b  jz      loc_18006359A
0x180063641  lea     rcx, [rbp+arg_18]
0x180063645  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18006364a  lea     rcx, [rbp+var_50]
0x18006364e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180063653  lea     rcx, [rbp+var_48]
0x180063657  call    ?InternalRelease@?$ComPtr@UIExtensionRegistration@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(void)
0x18006365c  lea     rcx, [rbp+var_40]
0x180063660  call    ?InternalRelease@?$ComPtr@UIExtensionRegistration@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(void)
0x180063665  lea     r11, [rsp+70h+var_s0]
0x18006366a  mov     eax, esi
0x18006366c  mov     rbx, [r11+20h]
0x180063670  mov     rsi, [r11+28h]
0x180063674  mov     rsp, r11
0x180063677  pop     r14
0x180063679  pop     rdi
0x18006367a  pop     rbp
0x18006367b  retn
```
