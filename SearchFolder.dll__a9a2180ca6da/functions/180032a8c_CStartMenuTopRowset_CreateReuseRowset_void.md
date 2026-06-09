# CStartMenuTopRowset::_CreateReuseRowset(void)

- ea: `0x180032a8c`
- end: `0x180032cc8`
- name: `?_CreateReuseRowset@CStartMenuTopRowset@@AEAAJXZ`
- size: `572`
- prototype: `__int64 __fastcall(CStartMenuTopRowset *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180030e58`

## callees

- `0x1800054b0`
- `0x180005c88`
- `0x180006900`
- `0x1800129ec`
- `0x180021e64`
- `0x18002850c`
- `0x18002f49c`
- `0x180032a8c`
- `0x180038bc0`
- `0x180051010`

## import_xrefs

- `SHELL32!SHCreateItemFromParsingName` at `0x180032b84`
- `SHELL32!SHCreateItemFromParsingName` at `0x180032b84`
- `api-ms-win-winrt-search-folder-l1-1-0!CreateResultSetFactory` at `0x180032bb4`
- `api-ms-win-winrt-search-folder-l1-1-0!CreateResultSetFactory` at `0x180032bb4`
- `api-ms-win-winrt-search-folder-l1-1-0!CreateDefaultProviderResolver` at `0x180032b0f`
- `api-ms-win-winrt-search-folder-l1-1-0!CreateDefaultProviderResolver` at `0x180032b0f`

## pseudocode

```c
__int64 __fastcall CStartMenuTopRowset::_CreateReuseRowset(CStartMenuTopRowset *this)
{
  HRESULT v2; // ebx
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  __int64 v9; // rax
  void (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v11; // rax
  __int64 v13; // [rsp+40h] [rbp-40h] BYREF
  __int64 v14; // [rsp+48h] [rbp-38h] BYREF
  __int64 v15; // [rsp+50h] [rbp-30h] BYREF
  __int64 v16; // [rsp+58h] [rbp-28h] BYREF
  void *ppv[2]; // [rsp+60h] [rbp-20h] BYREF

  v2 = 0;
  if ( ATL::CComPtrBase<IResultSetManager>::operator!((_QWORD *)this + 16)
    && ATL::CComPtrBase<IResultSetManager>::operator!((_QWORD *)this + 7) )
  {
    if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(
        v3,
        (unsigned int)SearchFolder_StartMenu_BaseQuery_Start,
        v4,
        v5,
        (__int64)ppv);
    ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v16);
    v2 = CreateDefaultProviderResolver(&GUID_1d201ab1_7c6e_4d76_9ac4_f09a1e462a00, &v16);
    if ( v2 >= 0 )
    {
      ATL::CComPtrBase<IPropertyStoreCache>::Release((char *)this + 64);
      v9 = ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->((__int64)&v16);
      v2 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, GUID *, char *))(*(_QWORD *)v9 + 24LL))(
             v9,
             *((_QWORD *)this + 11),
             1,
             &GUID_b445e1e5_d442_4865_9faf_36a64be62b09,
             (char *)this + 64);
      if ( v2 >= 0 )
      {
        ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(ppv);
        v2 = SHCreateItemFromParsingName(
               L"shell:::{daf95313-e44d-46af-be1b-cbacea2c3065}",
               0,
               &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
               ppv);
        if ( v2 >= 0 )
        {
          ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v15);
          v2 = CreateResultSetFactory(
                 ppv[0],
                 PKEY_StartMenu_ResultSourceId,
                 &GUID_aa64c263_b6df_4050_b3b9_38e1b89e2998,
                 &v15);
          if ( v2 >= 0 )
          {
            ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v14);
            v2 = s_CreateChildShape(*((_QWORD *)this + 9), &v14);
            if ( v2 >= 0 )
            {
              ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v13);
              v10 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 4);
              if ( v10 )
                (**v10)(v10, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, &v13);
              ATL::CComPtrBase<IPropertyStoreCache>::Release((char *)this + 56);
              v11 = ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->((__int64)&v15);
              v2 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, __int64, GUID *, char *))(*(_QWORD *)v11 + 24LL))(
                     v11,
                     *((_QWORD *)this + 8),
                     v14,
                     0,
                     v13,
                     &GUID_0c733a7c_2a1c_11ce_ade5_00aa0044773d,
                     (char *)this + 56);
              ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v13);
            }
            ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v14);
          }
          ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v15);
        }
        ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)ppv);
      }
    }
    if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(
        v6,
        (unsigned int)SearchFolder_StartMenu_BaseQuery_Stop,
        v7,
        v8,
        (__int64)ppv);
    ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v16);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180032a8c  mov     [rsp-18h+arg_8], rbx
0x180032a91  mov     [rsp-18h+arg_10], rsi
0x180032a96  push    rbp
0x180032a97  push    rdi
0x180032a98  push    r14
0x180032a9a  mov     rbp, rsp
0x180032a9d  sub     rsp, 80h
0x180032aa4  mov     rax, cs:__security_cookie
0x180032aab  xor     rax, rsp
0x180032aae  mov     [rbp+var_10], rax
0x180032ab2  mov     rdi, rcx
0x180032ab5  xor     ebx, ebx
0x180032ab7  sub     rcx, 0FFFFFFFFFFFFFF80h
0x180032abb  call    ??7?$CComPtrBase@UIResultSetManager@@@ATL@@QEBA_NXZ; ATL::CComPtrBase<IResultSetManager>::operator!(void)
0x180032ac0  test    al, al
0x180032ac2  jz      loc_180032CA2
0x180032ac8  lea     rsi, [rdi+38h]
0x180032acc  mov     rcx, rsi
0x180032acf  call    ??7?$CComPtrBase@UIResultSetManager@@@ATL@@QEBA_NXZ; ATL::CComPtrBase<IResultSetManager>::operator!(void)
0x180032ad4  test    al, al
0x180032ad6  jz      loc_180032CA2
0x180032adc  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180032ae3  jz      short loc_180032AFA
0x180032ae5  lea     rax, [rbp+ppv]
0x180032ae9  mov     [rsp+80h+var_60], rax
0x180032aee  lea     rdx, SearchFolder_StartMenu_BaseQuery_Start
0x180032af5  call    McGenEventWrite_EtwEventWriteTransfer
0x180032afa  lea     rcx, [rbp+var_28]; void *
0x180032afe  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180032b03  nop
0x180032b04  lea     rdx, [rbp+var_28]
0x180032b08  lea     rcx, _GUID_1d201ab1_7c6e_4d76_9ac4_f09a1e462a00
0x180032b0f  call    cs:__imp_CreateDefaultProviderResolver
0x180032b15  mov     ebx, eax
0x180032b17  test    eax, eax
0x180032b19  js      loc_180032C7A
0x180032b1f  lea     r14, [rdi+40h]
0x180032b23  mov     rcx, r14
0x180032b26  call    ?Release@?$CComPtrBase@UIPropertyStoreCache@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPropertyStoreCache>::Release(void)
0x180032b2b  lea     rcx, [rbp+var_28]
0x180032b2f  call    ??C?$CComPtrBase@UIStartMenuResultSetInternal@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIStartMenuResultSetInternal@@@1@XZ; ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->(void)
0x180032b34  mov     r10, rax
0x180032b37  mov     rcx, [rax]
0x180032b3a  mov     rax, [rcx+18h]
0x180032b3e  mov     [rsp+80h+var_60], r14
0x180032b43  lea     r9, _GUID_b445e1e5_d442_4865_9faf_36a64be62b09
0x180032b4a  mov     r8d, 1
0x180032b50  mov     rdx, [rdi+58h]
0x180032b54  mov     rcx, r10
0x180032b57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b5c  mov     ebx, eax
0x180032b5e  test    eax, eax
0x180032b60  js      loc_180032C7A
0x180032b66  lea     rcx, [rbp+ppv]; void *
0x180032b6a  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180032b6f  nop
0x180032b70  lea     r9, [rbp+ppv]; ppv
0x180032b74  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180032b7b  xor     edx, edx; pbc
0x180032b7d  lea     rcx, pszPath; "shell:::{daf95313-e44d-46af-be1b-cbacea"...
0x180032b84  call    cs:__imp_SHCreateItemFromParsingName
0x180032b8a  mov     ebx, eax
0x180032b8c  test    eax, eax
0x180032b8e  js      loc_180032C71
0x180032b94  lea     rcx, [rbp+var_30]; void *
0x180032b98  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180032b9d  nop
0x180032b9e  lea     r9, [rbp+var_30]
0x180032ba2  lea     r8, _GUID_aa64c263_b6df_4050_b3b9_38e1b89e2998
0x180032ba9  lea     rdx, PKEY_StartMenu_ResultSourceId
0x180032bb0  mov     rcx, [rbp+ppv]
0x180032bb4  call    cs:__imp_CreateResultSetFactory
0x180032bba  mov     ebx, eax
0x180032bbc  test    eax, eax
0x180032bbe  js      loc_180032C67
0x180032bc4  lea     rcx, [rbp+var_38]; void *
0x180032bc8  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180032bcd  nop
0x180032bce  lea     rdx, [rbp+var_38]
0x180032bd2  mov     rcx, [rdi+48h]
0x180032bd6  call    s_CreateChildShape
0x180032bdb  mov     ebx, eax
0x180032bdd  test    eax, eax
0x180032bdf  js      short loc_180032C5D
0x180032be1  lea     rcx, [rbp+var_40]; void *
0x180032be5  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180032bea  nop
0x180032beb  mov     rcx, [rdi+20h]
0x180032bef  test    rcx, rcx
0x180032bf2  jz      short loc_180032C0A
0x180032bf4  mov     rax, [rcx]
0x180032bf7  lea     r8, [rbp+var_40]
0x180032bfb  lea     rdx, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa
0x180032c02  mov     rax, [rax]
0x180032c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032c0a  mov     rcx, rsi
0x180032c0d  call    ?Release@?$CComPtrBase@UIPropertyStoreCache@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPropertyStoreCache>::Release(void)
0x180032c12  lea     rcx, [rbp+var_30]
0x180032c16  call    ??C?$CComPtrBase@UIStartMenuResultSetInternal@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIStartMenuResultSetInternal@@@1@XZ; ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->(void)
0x180032c1b  mov     r10, rax
0x180032c1e  mov     r9, [rbp+var_40]
0x180032c22  mov     rcx, [rax]
0x180032c25  mov     rax, [rcx+18h]
0x180032c29  mov     [rsp+80h+var_50], rsi
0x180032c2e  lea     rcx, _GUID_0c733a7c_2a1c_11ce_ade5_00aa0044773d
0x180032c35  mov     [rsp+80h+var_58], rcx
0x180032c3a  mov     [rsp+80h+var_60], r9
0x180032c3f  xor     r9d, r9d
0x180032c42  mov     r8, [rbp+var_38]
0x180032c46  mov     rdx, [r14]
0x180032c49  mov     rcx, r10
0x180032c4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032c51  mov     ebx, eax
0x180032c53  lea     rcx, [rbp+var_40]
0x180032c57  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180032c5c  nop
0x180032c5d  lea     rcx, [rbp+var_38]
0x180032c61  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180032c66  nop
0x180032c67  lea     rcx, [rbp+var_30]
0x180032c6b  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180032c70  nop
0x180032c71  lea     rcx, [rbp+ppv]
0x180032c75  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180032c7a  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180032c81  jz      short loc_180032C99
0x180032c83  lea     rax, [rbp+ppv]
0x180032c87  mov     [rsp+80h+var_60], rax
0x180032c8c  lea     rdx, SearchFolder_StartMenu_BaseQuery_Stop
0x180032c93  call    McGenEventWrite_EtwEventWriteTransfer
0x180032c98  nop
0x180032c99  lea     rcx, [rbp+var_28]
0x180032c9d  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180032ca2  mov     eax, ebx
0x180032ca4  mov     rcx, [rbp+var_10]
0x180032ca8  xor     rcx, rsp; StackCookie
0x180032cab  call    __security_check_cookie
0x180032cb0  lea     r11, [rsp+80h+var_s0]
0x180032cb8  mov     rbx, [r11+28h]
0x180032cbc  mov     rsi, [r11+30h]
0x180032cc0  mov     rsp, r11
0x180032cc3  pop     r14
0x180032cc5  pop     rdi
0x180032cc6  pop     rbp
0x180032cc7  retn
```
