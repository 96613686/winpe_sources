# CStartMenuLibraryResultSetManager::s_AlterSortColumnsFromLibraryDescription(ILibraryDescription *,IResultShape *,IResultShape * *)

- ea: `0x180005728`
- end: `0x180005c6e`
- name: `?s_AlterSortColumnsFromLibraryDescription@CStartMenuLibraryResultSetManager@@SAJPEAUILibraryDescription@@PEAUIResultShape@@PEAPEAU3@@Z`
- size: `1350`
- prototype: `__int64 __fastcall(struct ILibraryDescription *, struct IResultShape *, struct IResultShape **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800392bc`

## callees

- `0x1800054b0`
- `0x180005728`
- `0x180005c74`
- `0x180005c88`
- `0x180006900`
- `0x1800129ec`
- `0x1800274b8`
- `0x1800284e0`
- `0x18004fb0c`
- `0x180051010`

## import_xrefs

- `SHELL32!__imp_SHCoCreateInstance` at `0x18000587d`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180005a61`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180005b06`
- `SHELL32!__imp_SHCoCreateInstance` at `0x18000587d`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180005a61`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180005b06`
- `SHELL32!__imp_SHGetFolderTypeDescription` at `0x1800057dd`
- `SHELL32!__imp_SHGetFolderTypeDescription` at `0x1800057dd`
- `SHELL32!__imp_SHGetFolderTypeFromCanonicalName` at `0x1800057b6`
- `SHELL32!__imp_SHGetFolderTypeFromCanonicalName` at `0x1800057b6`

## string_xrefs

- `0x1800057af`: `Communications.SearchResults`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall CStartMenuLibraryResultSetManager::s_AlterSortColumnsFromLibraryDescription(
        struct ILibraryDescription *a1,
        struct IResultShape *a2,
        struct IResultShape **a3)
{
  int v5; // edx
  __int64 v6; // rbx
  __int64 v7; // rax
  unsigned int v9; // [rsp+40h] [rbp-C0h] BYREF
  struct IUnknown *v10; // [rsp+48h] [rbp-B8h] BYREF
  void *v11; // [rsp+50h] [rbp-B0h] BYREF
  void *v12; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v13; // [rsp+60h] [rbp-A0h] BYREF
  void *ppv; // [rsp+68h] [rbp-98h] BYREF
  struct IUnknown *v15; // [rsp+70h] [rbp-90h] BYREF
  __int64 v16; // [rsp+78h] [rbp-88h] BYREF
  __int64 v17; // [rsp+80h] [rbp-80h] BYREF
  __int64 v18; // [rsp+88h] [rbp-78h] BYREF
  __int64 v19; // [rsp+90h] [rbp-70h] BYREF
  __int64 v20; // [rsp+98h] [rbp-68h] BYREF
  __int64 v21; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v22; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v23; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v24; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v25; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v26; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v27; // [rsp+D0h] [rbp-30h] BYREF
  PROPERTYKEY v28; // [rsp+D8h] [rbp-28h] BYREF
  __int128 Buf1; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v30; // [rsp+100h] [rbp+0h] BYREF
  GUID fmtid; // [rsp+110h] [rbp+10h] BYREF
  int v32; // [rsp+120h] [rbp+20h]
  _BYTE v33[96]; // [rsp+130h] [rbp+30h] BYREF

  *a3 = 0;
  Buf1 = 0;
  ATL::CComPtr<ICondition>::CComPtr<ICondition>(&v10, (__int64)a2);
  if ( (*(int (__fastcall **)(struct ILibraryDescription *, __int128 *))(*(_QWORD *)a1 + 56LL))(a1, &Buf1) >= 0
    && !memcmp_0(&Buf1, &FOLDERTYPEID_Communications, 0x10u) )
  {
    v30 = 0;
    if ( (int)SHGetFolderTypeFromCanonicalName(L"Communications.SearchResults", &v30) >= 0 )
    {
      ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v25);
      if ( (int)SHGetFolderTypeDescription(&v30, &GUID_e2ba9629_b18f_4e3a_aba5_42d879e79c80, &v25) >= 0 )
      {
        ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v24);
        if ( (*(int (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v25 + 152LL))(
               v25,
               &GUID_ae8c987d_8797_4ed3_be72_2a47dd938db0,
               &v24) >= 0 )
        {
          v9 = 0;
          if ( (*(int (__fastcall **)(__int64, _BYTE *, __int64, unsigned int *))(*(_QWORD *)v24 + 64LL))(
                 v24,
                 v33,
                 4,
                 &v9) >= 0 )
          {
            if ( v9 )
            {
              ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&ppv);
              if ( SHCoCreateInstance(0, &CLSID_SortColumnArray, 0, &GUID_e70c4a71_a5a1_40f2_84eb_9a9081e246a9, &ppv) >= 0
                && (*(int (__fastcall **)(void *, _QWORD, _BYTE *, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, 0, v33, v9) >= 0 )
              {
                ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v23);
                if ( (**(int (__fastcall ***)(void *, GUID *, __int64 *))ppv)(
                       ppv,
                       &GUID_6dfc60fb_f2e9_459b_beb5_288f1a7c7d54,
                       &v23) >= 0 )
                {
                  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v22);
                  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v21);
                  v28 = PKEY_Null;
                  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v13);
                  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v20);
                  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v19);
                  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v18);
                  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v17);
                  fmtid = PKEY_Null.fmtid;
                  v32 = v5;
                  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v27);
                  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v26);
                  if ( v10 )
                  {
                    ((void (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v10->lpVtbl[1].QueryInterface)(
                      v10,
                      &GUID_75bd59aa_f23b_4963_aba4_0b355752a91b,
                      &v22);
                    v6 = ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->((__int64)&v10);
                    (*(void (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v6 + 32LL))(
                      v6,
                      &GUID_75bd59aa_f23b_4963_aba4_0b355752a91b,
                      &v21);
                    (*(void (__fastcall **)(__int64, PROPERTYKEY *, GUID *, __int64 *))(*(_QWORD *)v6 + 56LL))(
                      v6,
                      &v28,
                      &GUID_6bc63938_8254_4965_9680_565933185060,
                      &v13);
                    (*(void (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v6 + 64LL))(
                      v6,
                      &GUID_00000000_0000_0000_c000_000000000046,
                      &v20);
                    (*(void (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v6 + 80LL))(
                      v6,
                      &GUID_6dfc60fb_f2e9_459b_beb5_288f1a7c7d54,
                      &v19);
                    if ( v13 )
                    {
                      (*(void (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v13 + 24LL))(
                        v13,
                        &GUID_75bd59aa_f23b_4963_aba4_0b355752a91b,
                        &v18);
                      v7 = ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->((__int64)&v13);
                      (*(void (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v7 + 32LL))(
                        v7,
                        &GUID_75bd59aa_f23b_4963_aba4_0b355752a91b,
                        &v17);
                    }
                  }
                  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v12);
                  if ( SHCoCreateInstance(0, &CLSID_ResultShape, 0, &GUID_42c9f529_ac7b_45d3_a320_c2f23f250b94, &v12) >= 0
                    && (*(int (__fastcall **)(void *, __int64, __int64, __int64, GUID *, __int64, __int64))(*(_QWORD *)v12 + 24LL))(
                         v12,
                         v18,
                         v17,
                         v23,
                         &fmtid,
                         v27,
                         v26) >= 0 )
                  {
                    ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v16);
                    if ( (**(int (__fastcall ***)(void *, GUID *, __int64 *))v12)(
                           v12,
                           &GUID_6bc63938_8254_4965_9680_565933185060,
                           &v16) >= 0 )
                    {
                      ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v11);
                      if ( SHCoCreateInstance(
                             0,
                             &CLSID_ResultShape,
                             0,
                             &GUID_42c9f529_ac7b_45d3_a320_c2f23f250b94,
                             &v11) >= 0
                        && (*(int (__fastcall **)(void *, __int64, __int64, __int64, PROPERTYKEY *, __int64, __int64))(*(_QWORD *)v11 + 24LL))(
                             v11,
                             v22,
                             v21,
                             v19,
                             &v28,
                             v16,
                             v20) >= 0 )
                      {
                        ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v15);
                        if ( (**(int (__fastcall ***)(void *, GUID *, struct IUnknown **))v11)(
                               v11,
                               &GUID_6bc63938_8254_4965_9680_565933185060,
                               &v15) >= 0 )
                          ATL::CComPtr<CPropertyMapPair>::operator=(&v10, &v15);
                        ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v15);
                      }
                      ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v11);
                    }
                    ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v16);
                  }
                  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v12);
                  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v26);
                  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v27);
                  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v17);
                  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v18);
                  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v19);
                  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v20);
                  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v13);
                  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v21);
                  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v22);
                }
                ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v23);
              }
              ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&ppv);
            }
          }
        }
        ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v24);
      }
      ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v25);
    }
  }
  *a3 = (struct IResultShape *)ATL::CComPtrBase<IScope>::Detach(&v10);
  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v10);
  return 0;
}

```

## disassembly

```asm
0x180005728  push    rbp
0x18000572a  push    rbx
0x18000572b  push    rdi
0x18000572c  lea     rbp, [rsp-0A0h]
0x180005734  sub     rsp, 1A0h
0x18000573b  mov     rax, cs:__security_cookie
0x180005742  xor     rax, rsp
0x180005745  mov     [rbp+0B0h+var_20], rax
0x18000574c  mov     rdi, r8
0x18000574f  mov     rbx, rcx
0x180005752  mov     qword ptr [r8], 0
0x180005759  xorps   xmm0, xmm0
0x18000575c  movups  [rbp+0B0h+Buf1], xmm0
0x180005760  lea     rcx, [rsp+1B0h+var_168]
0x180005765  call    ??0?$CComPtr@UICondition@@@ATL@@QEAA@PEAUICondition@@@Z; ATL::CComPtr<ICondition>::CComPtr<ICondition>(ICondition *)
0x18000576a  nop
0x18000576b  mov     rax, [rbx]
0x18000576e  lea     rdx, [rbp+0B0h+Buf1]
0x180005772  mov     rcx, rbx
0x180005775  mov     rax, [rax+38h]
0x180005779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000577e  test    eax, eax
0x180005780  js      loc_180005C3B
0x180005786  mov     r8d, 10h; Size
0x18000578c  lea     rdx, FOLDERTYPEID_Communications; Buf2
0x180005793  lea     rcx, [rbp+0B0h+Buf1]; Buf1
0x180005797  call    memcmp_0
0x18000579c  test    eax, eax
0x18000579e  jnz     loc_180005C3B
0x1800057a4  xorps   xmm0, xmm0
0x1800057a7  movups  [rbp+0B0h+var_B0], xmm0
0x1800057ab  lea     rdx, [rbp+0B0h+var_B0]
0x1800057af  lea     rcx, aCommunications; "Communications.SearchResults"
0x1800057b6  call    cs:__imp_SHGetFolderTypeFromCanonicalName
0x1800057bc  test    eax, eax
0x1800057be  js      loc_180005C3B
0x1800057c4  lea     rcx, [rbp+0B0h+var_F0]; void *
0x1800057c8  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x1800057cd  nop
0x1800057ce  lea     r8, [rbp+0B0h+var_F0]
0x1800057d2  lea     rdx, _GUID_e2ba9629_b18f_4e3a_aba5_42d879e79c80
0x1800057d9  lea     rcx, [rbp+0B0h+var_B0]
0x1800057dd  call    cs:__imp_SHGetFolderTypeDescription
0x1800057e3  test    eax, eax
0x1800057e5  js      loc_180005C32
0x1800057eb  lea     rcx, [rbp+0B0h+var_F8]; void *
0x1800057ef  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x1800057f4  nop
0x1800057f5  mov     rcx, [rbp+0B0h+var_F0]
0x1800057f9  mov     rax, [rcx]
0x1800057fc  lea     r8, [rbp+0B0h+var_F8]
0x180005800  lea     rdx, _GUID_ae8c987d_8797_4ed3_be72_2a47dd938db0
0x180005807  mov     rax, [rax+98h]
0x18000580e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005813  test    eax, eax
0x180005815  js      loc_180005C28
0x18000581b  mov     [rsp+1B0h+var_170], 0
0x180005823  mov     rcx, [rbp+0B0h+var_F8]
0x180005827  mov     rax, [rcx]
0x18000582a  lea     r9, [rsp+1B0h+var_170]
0x18000582f  mov     r8d, 4
0x180005835  lea     rdx, [rbp+0B0h+var_80]
0x180005839  mov     rax, [rax+40h]
0x18000583d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005842  test    eax, eax
0x180005844  js      loc_180005C28
0x18000584a  cmp     [rsp+1B0h+var_170], 0
0x18000584f  jz      loc_180005C28
0x180005855  lea     rcx, [rsp+1B0h+var_148]; void *
0x18000585a  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18000585f  nop
0x180005860  lea     rax, [rsp+1B0h+var_148]
0x180005865  mov     [rsp+1B0h+ppv], rax; ppv
0x18000586a  lea     r9, _GUID_e70c4a71_a5a1_40f2_84eb_9a9081e246a9; riid
0x180005871  xor     r8d, r8d; pUnkOuter
0x180005874  lea     rdx, CLSID_SortColumnArray; pclsid
0x18000587b  xor     ecx, ecx; pszCLSID
0x18000587d  call    cs:__imp_SHCoCreateInstance
0x180005883  test    eax, eax
0x180005885  js      loc_180005C1D
0x18000588b  mov     rcx, [rsp+1B0h+var_148]
0x180005890  mov     rax, [rcx]
0x180005893  mov     r9d, [rsp+1B0h+var_170]
0x180005898  lea     r8, [rbp+0B0h+var_80]
0x18000589c  xor     edx, edx
0x18000589e  mov     rax, [rax+18h]
0x1800058a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058a7  test    eax, eax
0x1800058a9  js      loc_180005C1D
0x1800058af  lea     rcx, [rbp+0B0h+var_100]; void *
0x1800058b3  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x1800058b8  nop
0x1800058b9  mov     rcx, [rsp+1B0h+var_148]
0x1800058be  mov     rax, [rcx]
0x1800058c1  lea     r8, [rbp+0B0h+var_100]
0x1800058c5  lea     rdx, _GUID_6dfc60fb_f2e9_459b_beb5_288f1a7c7d54
0x1800058cc  mov     rax, [rax]
0x1800058cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058d4  test    eax, eax
0x1800058d6  js      loc_180005C13
0x1800058dc  lea     rcx, [rbp+0B0h+var_108]; void *
0x1800058e0  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x1800058e5  nop
0x1800058e6  lea     rcx, [rbp+0B0h+var_110]; void *
0x1800058ea  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x1800058ef  nop
0x1800058f0  movups  xmm0, xmmword ptr cs:PKEY_Null.fmtid.Data1
0x1800058f7  movups  [rbp+0B0h+var_D8], xmm0
0x1800058fb  mov     edx, cs:PKEY_Null.pid
0x180005901  mov     [rbp+0B0h+var_C8], edx
0x180005904  lea     rcx, [rsp+1B0h+var_150]; void *
0x180005909  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18000590e  nop
0x18000590f  lea     rcx, [rbp+0B0h+var_118]; void *
0x180005913  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180005918  nop
0x180005919  lea     rcx, [rbp+0B0h+var_120]; void *
0x18000591d  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180005922  nop
0x180005923  lea     rcx, [rbp+0B0h+var_128]; void *
0x180005927  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18000592c  nop
0x18000592d  lea     rcx, [rbp+0B0h+var_130]; void *
0x180005931  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180005936  nop
0x180005937  movups  [rbp+0B0h+var_A0], xmm0
0x18000593b  mov     [rbp+0B0h+var_90], edx
0x18000593e  lea     rcx, [rbp+0B0h+var_E0]; void *
0x180005942  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180005947  nop
0x180005948  lea     rcx, [rbp+0B0h+var_E8]; void *
0x18000594c  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180005951  nop
0x180005952  mov     rcx, [rsp+1B0h+var_168]
0x180005957  test    rcx, rcx
0x18000595a  jz      loc_180005A39
0x180005960  mov     rax, [rcx]
0x180005963  lea     r8, [rbp+0B0h+var_108]
0x180005967  lea     rdx, _GUID_75bd59aa_f23b_4963_aba4_0b355752a91b
0x18000596e  mov     rax, [rax+18h]
0x180005972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005977  lea     rcx, [rsp+1B0h+var_168]
0x18000597c  call    ??C?$CComPtrBase@UIStartMenuResultSetInternal@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIStartMenuResultSetInternal@@@1@XZ; ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->(void)
0x180005981  mov     rbx, rax
0x180005984  mov     rcx, [rax]
0x180005987  mov     rax, [rcx+20h]
0x18000598b  lea     r8, [rbp+0B0h+var_110]
0x18000598f  lea     rdx, _GUID_75bd59aa_f23b_4963_aba4_0b355752a91b
0x180005996  mov     rcx, rbx
0x180005999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000599e  mov     rcx, [rbx]
0x1800059a1  mov     rax, [rcx+38h]
0x1800059a5  lea     r9, [rsp+1B0h+var_150]
0x1800059aa  lea     r8, _GUID_6bc63938_8254_4965_9680_565933185060
0x1800059b1  lea     rdx, [rbp+0B0h+var_D8]
0x1800059b5  mov     rcx, rbx
0x1800059b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059bd  mov     rax, [rbx]
0x1800059c0  lea     r8, [rbp+0B0h+var_118]
0x1800059c4  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800059cb  mov     rcx, rbx
0x1800059ce  mov     rax, [rax+40h]
0x1800059d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059d7  mov     rax, [rbx]
0x1800059da  lea     r8, [rbp+0B0h+var_120]
0x1800059de  lea     rdx, _GUID_6dfc60fb_f2e9_459b_beb5_288f1a7c7d54
0x1800059e5  mov     rcx, rbx
0x1800059e8  mov     rax, [rax+50h]
0x1800059ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059f1  mov     rcx, [rsp+1B0h+var_150]
0x1800059f6  test    rcx, rcx
0x1800059f9  jz      short loc_180005A39
0x1800059fb  mov     rax, [rcx]
0x1800059fe  lea     r8, [rbp+0B0h+var_128]
0x180005a02  lea     rdx, _GUID_75bd59aa_f23b_4963_aba4_0b355752a91b
0x180005a09  mov     rax, [rax+18h]
0x180005a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a12  lea     rcx, [rsp+1B0h+var_150]
0x180005a17  call    ??C?$CComPtrBase@UIStartMenuResultSetInternal@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIStartMenuResultSetInternal@@@1@XZ; ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->(void)
0x180005a1c  mov     r9, rax
0x180005a1f  mov     rcx, [rax]
0x180005a22  mov     rax, [rcx+20h]
0x180005a26  lea     r8, [rbp+0B0h+var_130]
0x180005a2a  lea     rdx, _GUID_75bd59aa_f23b_4963_aba4_0b355752a91b
0x180005a31  mov     rcx, r9
0x180005a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a39  lea     rcx, [rsp+1B0h+var_158]; void *
0x180005a3e  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180005a43  nop
0x180005a44  lea     rax, [rsp+1B0h+var_158]
0x180005a49  mov     [rsp+1B0h+ppv], rax; ppv
0x180005a4e  lea     r9, _GUID_42c9f529_ac7b_45d3_a320_c2f23f250b94; riid
0x180005a55  xor     r8d, r8d; pUnkOuter
0x180005a58  lea     rdx, CLSID_ResultShape; pclsid
0x180005a5f  xor     ecx, ecx; pszCLSID
0x180005a61  call    cs:__imp_SHCoCreateInstance
0x180005a67  test    eax, eax
0x180005a69  js      loc_180005BAD
0x180005a6f  mov     rcx, [rsp+1B0h+var_158]
0x180005a74  mov     rax, [rcx]
0x180005a77  mov     r10, [rbp+0B0h+var_E8]
0x180005a7b  mov     [rsp+1B0h+var_180], r10
0x180005a80  mov     r10, [rbp+0B0h+var_E0]
0x180005a84  mov     [rsp+1B0h+var_188], r10
0x180005a89  lea     rdx, [rbp+0B0h+var_A0]
0x180005a8d  mov     [rsp+1B0h+ppv], rdx
0x180005a92  mov     r9, [rbp+0B0h+var_100]
0x180005a96  mov     r8, [rbp+0B0h+var_130]
0x180005a9a  mov     rdx, [rbp+0B0h+var_128]
0x180005a9e  mov     rax, [rax+18h]
0x180005aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005aa7  test    eax, eax
0x180005aa9  js      loc_180005BAD
0x180005aaf  lea     rcx, [rsp+1B0h+var_138]; void *
0x180005ab4  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180005ab9  nop
0x180005aba  mov     rcx, [rsp+1B0h+var_158]
0x180005abf  mov     rax, [rcx]
0x180005ac2  lea     r8, [rsp+1B0h+var_138]
0x180005ac7  lea     rdx, _GUID_6bc63938_8254_4965_9680_565933185060
0x180005ace  mov     rax, [rax]
0x180005ad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ad6  test    eax, eax
0x180005ad8  js      loc_180005BA2
0x180005ade  lea     rcx, [rsp+1B0h+var_160]; void *
0x180005ae3  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180005ae8  nop
0x180005ae9  lea     rax, [rsp+1B0h+var_160]
0x180005aee  mov     [rsp+1B0h+ppv], rax; ppv
0x180005af3  lea     r9, _GUID_42c9f529_ac7b_45d3_a320_c2f23f250b94; riid
0x180005afa  xor     r8d, r8d; pUnkOuter
0x180005afd  lea     rdx, CLSID_ResultShape; pclsid
0x180005b04  xor     ecx, ecx; pszCLSID
0x180005b06  call    cs:__imp_SHCoCreateInstance
0x180005b0c  test    eax, eax
0x180005b0e  js      loc_180005B97
0x180005b14  mov     rcx, [rsp+1B0h+var_160]
0x180005b19  mov     r10, [rbp+0B0h+var_118]
0x180005b1d  mov     r11, [rsp+1B0h+var_138]
0x180005b22  mov     rax, [rcx]
0x180005b25  mov     [rsp+1B0h+var_180], r10
0x180005b2a  mov     [rsp+1B0h+var_188], r11
0x180005b2f  lea     rdx, [rbp+0B0h+var_D8]
0x180005b33  mov     [rsp+1B0h+ppv], rdx
0x180005b38  mov     r9, [rbp+0B0h+var_120]
0x180005b3c  mov     r8, [rbp+0B0h+var_110]
0x180005b40  mov     rdx, [rbp+0B0h+var_108]
0x180005b44  mov     rax, [rax+18h]
0x180005b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b4d  test    eax, eax
0x180005b4f  js      short loc_180005B97
0x180005b51  lea     rcx, [rsp+1B0h+var_140]; void *
0x180005b56  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180005b5b  nop
0x180005b5c  mov     rcx, [rsp+1B0h+var_160]
0x180005b61  mov     rax, [rcx]
0x180005b64  lea     r8, [rsp+1B0h+var_140]
0x180005b69  lea     rdx, _GUID_6bc63938_8254_4965_9680_565933185060
0x180005b70  mov     rax, [rax]
0x180005b73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b78  test    eax, eax
0x180005b7a  js      short loc_180005B8C
0x180005b7c  lea     rdx, [rsp+1B0h+var_140]
0x180005b81  lea     rcx, [rsp+1B0h+var_168]
0x180005b86  call    ??4?$CComPtr@VCPropertyMapPair@@@ATL@@QEAAPEAVCPropertyMapPair@@AEBV01@@Z; ATL::CComPtr<CPropertyMapPair>::operator=(ATL::CComPtr<CPropertyMapPair> const &)
0x180005b8b  nop
0x180005b8c  lea     rcx, [rsp+1B0h+var_140]
0x180005b91  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180005b96  nop
0x180005b97  lea     rcx, [rsp+1B0h+var_160]
0x180005b9c  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180005ba1  nop
0x180005ba2  lea     rcx, [rsp+1B0h+var_138]
0x180005ba7  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180005bac  nop
0x180005bad  lea     rcx, [rsp+1B0h+var_158]
0x180005bb2  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180005bb7  nop
0x180005bb8  lea     rcx, [rbp+0B0h+var_E8]
0x180005bbc  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180005bc1  nop
0x180005bc2  lea     rcx, [rbp+0B0h+var_E0]
0x180005bc6  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180005bcb  nop
0x180005bcc  lea     rcx, [rbp+0B0h+var_130]
0x180005bd0  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180005bd5  nop
0x180005bd6  lea     rcx, [rbp+0B0h+var_128]
0x180005bda  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180005bdf  nop
0x180005be0  lea     rcx, [rbp+0B0h+var_120]
0x180005be4  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180005be9  nop
0x180005bea  lea     rcx, [rbp+0B0h+var_118]
0x180005bee  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180005bf3  nop
0x180005bf4  lea     rcx, [rsp+1B0h+var_150]
0x180005bf9  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180005bfe  nop
0x180005bff  lea     rcx, [rbp+0B0h+var_110]
  ... truncated ...
```
