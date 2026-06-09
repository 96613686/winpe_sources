# StructuredQuery1::CSchemaFromPropertySystem::ProcessSemanticType(ISemanticType *)

- ea: `0x180019d20`
- end: `0x18001a0d8`
- name: `?ProcessSemanticType@CSchemaFromPropertySystem@StructuredQuery1@@AEAAJPEAUISemanticType@@@Z`
- size: `952`
- prototype: `__int64 __fastcall(StructuredQuery1::CSchemaFromPropertySystem *__hidden this, struct ISemanticType *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001b4a0`

## callees

- `0x180012148`
- `0x180012310`
- `0x180019d20`
- `0x18001c5b4`
- `0x18001dd8c`
- `0x18001e110`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019ff1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019ffe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a037`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a08b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a0b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019ff1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019ffe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a037`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a08b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a0b5`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::CSchemaFromPropertySystem::ProcessSemanticType(
        StructuredQuery1::CSchemaFromPropertySystem *this,
        struct ISemanticType *a2)
{
  __int64 v2; // rax
  const struct _GUID *v5; // rdx
  int NamedEntityCanonicalName; // ebx
  __int64 v7; // rcx
  void *v8; // r12
  __int64 v9; // rax
  const struct _GUID *v10; // rdx
  __int64 v11; // rcx
  void *v12; // r13
  __int64 v13; // rax
  unsigned int i; // esi
  int v15; // edx
  const struct _GUID *v16; // r8
  void *v17; // rdi
  wchar_t **v18; // r9
  void *v19; // r14
  __int64 v21; // [rsp+30h] [rbp-50h] BYREF
  __int64 v22; // [rsp+38h] [rbp-48h] BYREF
  wchar_t *v23; // [rsp+40h] [rbp-40h] BYREF
  wchar_t *v24; // [rsp+48h] [rbp-38h] BYREF
  __int64 v25; // [rsp+50h] [rbp-30h] BYREF
  wchar_t *v26; // [rsp+58h] [rbp-28h] BYREF
  __int64 v27; // [rsp+60h] [rbp-20h] BYREF
  __int64 v28; // [rsp+68h] [rbp-18h] BYREF
  wchar_t *v29; // [rsp+70h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-8h] BYREF
  void *v31; // [rsp+C8h] [rbp+48h] BYREF
  void *v32; // [rsp+D0h] [rbp+50h] BYREF
  __int64 v33; // [rsp+D8h] [rbp+58h] BYREF

  v2 = *(_QWORD *)a2;
  v29 = 0;
  NamedEntityCanonicalName = (*(__int64 (__fastcall **)(struct ISemanticType *, wchar_t **))(v2 + 32))(a2, &v29);
  if ( NamedEntityCanonicalName >= 0 )
  {
    v31 = 0;
    NamedEntityCanonicalName = StructuredQuery1::ConstantString::CreateInstance(v29, v5, &v31);
    if ( NamedEntityCanonicalName >= 0 )
    {
      v7 = *((_QWORD *)this + 5);
      v8 = v31;
      v28 = 0;
      NamedEntityCanonicalName = (*(__int64 (__fastcall **)(__int64, void *, GUID *, __int64 *))(*(_QWORD *)v7 + 32LL))(
                                   v7,
                                   v31,
                                   &GUID_e90f2096_c488_49bf_a9dd_62d7c84755e5,
                                   &v28);
      if ( NamedEntityCanonicalName >= 0 )
      {
        v9 = *(_QWORD *)a2;
        v23 = 0;
        NamedEntityCanonicalName = (*(__int64 (__fastcall **)(struct ISemanticType *, wchar_t **))(v9 + 24))(a2, &v23);
        if ( NamedEntityCanonicalName >= 0 )
        {
          v31 = 0;
          NamedEntityCanonicalName = StructuredQuery1::ConstantString::CreateInstance(v23, v10, &v31);
          if ( NamedEntityCanonicalName >= 0 )
          {
            v11 = *((_QWORD *)this + 5);
            v12 = v31;
            v27 = 0;
            NamedEntityCanonicalName = (*(__int64 (__fastcall **)(__int64, void *, __int64, GUID *, __int64 *))(*(_QWORD *)v11 + 40LL))(
                                         v11,
                                         v31,
                                         v28,
                                         &GUID_e90f2096_c488_49bf_a9dd_62d7c84755e5,
                                         &v27);
            if ( NamedEntityCanonicalName >= 0 )
            {
              v13 = *(_QWORD *)a2;
              v22 = 0;
              NamedEntityCanonicalName = (*(__int64 (__fastcall **)(struct ISemanticType *, GUID *, __int64 *))(v13 + 48))(
                                           a2,
                                           &GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9,
                                           &v22);
              if ( NamedEntityCanonicalName >= 0 )
              {
                LODWORD(v31) = 0;
                NamedEntityCanonicalName = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v22 + 24LL))(
                                             v22,
                                             &v31);
                for ( i = 0; NamedEntityCanonicalName >= 0; ++i )
                {
                  if ( i >= (unsigned int)v31 )
                    break;
                  v33 = 0;
                  NamedEntityCanonicalName = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v22 + 32LL))(
                                               v22,
                                               i,
                                               &GUID_a3025981_c987_46f3_80f4_f838b51d4fe4,
                                               &v33);
                  if ( NamedEntityCanonicalName >= 0 )
                  {
                    v26 = 0;
                    NamedEntityCanonicalName = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v33 + 32LL))(
                                                 v33,
                                                 &v26);
                    if ( NamedEntityCanonicalName >= 0 )
                    {
                      v32 = 0;
                      NamedEntityCanonicalName = StructuredQuery1::RestrictionInfo::CreateInstance(v26, v15, v16, &v32);
                      if ( NamedEntityCanonicalName >= 0 )
                      {
                        v17 = v32;
                        v21 = 0;
                        NamedEntityCanonicalName = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))v32)(
                                                     v32,
                                                     &GUID_0d5f4564_b150_41f9_927d_97b1e3c8e1b0,
                                                     &v21);
                        if ( NamedEntityCanonicalName >= 0 )
                        {
                          v25 = 0;
                          NamedEntityCanonicalName = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v33 + 40LL))(
                                                       v33,
                                                       &GUID_d6d9aabf_5336_425a_a4b1_d0ff94bddf75,
                                                       &v25);
                          if ( NamedEntityCanonicalName >= 0 )
                          {
                            v24 = 0;
                            NamedEntityCanonicalName = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v33 + 24LL))(
                                                         v33,
                                                         &v24);
                            if ( NamedEntityCanonicalName >= 0 )
                            {
                              LODWORD(v32) = 0;
                              NamedEntityCanonicalName = StructuredQuery1::CSchemaFromPropertySystem::ProcessMnemonics(
                                                           this,
                                                           v25,
                                                           &v32,
                                                           0);
                              if ( NamedEntityCanonicalName >= 0 )
                              {
                                pv = 0;
                                NamedEntityCanonicalName = StructuredQuery1::MakeNamedEntityCanonicalName(
                                                             (StructuredQuery1 *)v23,
                                                             v24,
                                                             (const wchar_t *)&pv,
                                                             v18);
                                if ( NamedEntityCanonicalName >= 0 )
                                {
                                  v19 = pv;
                                  NamedEntityCanonicalName = (*(__int64 (__fastcall **)(void *, LPVOID))(*(_QWORD *)v17 + 40LL))(
                                                               v17,
                                                               pv);
                                  if ( NamedEntityCanonicalName >= 0 )
                                  {
                                    NamedEntityCanonicalName = StructuredQuery1::CSchemaFromPropertySystem::ProcessMnemonic(
                                                                 this,
                                                                 v19,
                                                                 &v32,
                                                                 2,
                                                                 v21);
                                    if ( NamedEntityCanonicalName >= 0 )
                                      NamedEntityCanonicalName = (*(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)v27 + 112LL))(
                                                                   v27,
                                                                   v17);
                                  }
                                  CoTaskMemFree(v19);
                                }
                              }
                              CoTaskMemFree(v24);
                            }
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
                          }
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
                        }
                        (*(void (__fastcall **)(void *))(*(_QWORD *)v17 + 16LL))(v17);
                      }
                      CoTaskMemFree(v26);
                    }
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
                  }
                }
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
            }
            (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
          }
          CoTaskMemFree(v23);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 16LL))(v8);
    }
    CoTaskMemFree(v29);
  }
  return (unsigned int)NamedEntityCanonicalName;
}

```

## disassembly

```asm
0x180019d20  mov     [rsp-38h+arg_0], rbx
0x180019d25  push    rbp
0x180019d26  push    rsi
0x180019d27  push    rdi
0x180019d28  push    r12
0x180019d2a  push    r13
0x180019d2c  push    r14
0x180019d2e  push    r15
0x180019d30  mov     rbp, rsp
0x180019d33  sub     rsp, 80h
0x180019d3a  mov     rax, [rdx]
0x180019d3d  mov     rdi, rdx
0x180019d40  mov     r15, rcx
0x180019d43  lea     rdx, [rbp+var_10]
0x180019d47  xor     r14d, r14d
0x180019d4a  mov     rcx, rdi
0x180019d4d  mov     [rbp+var_10], r14
0x180019d51  mov     rax, [rax+20h]
0x180019d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d5a  mov     ebx, eax
0x180019d5c  test    eax, eax
0x180019d5e  js      loc_18001A0BB
0x180019d64  mov     rcx, [rbp+var_10]; wchar_t *
0x180019d68  lea     r8, [rbp+arg_8]; void **
0x180019d6c  mov     [rbp+arg_8], r14
0x180019d70  call    ?CreateInstance@ConstantString@StructuredQuery1@@SAJPEB_WAEBU_GUID@@PEAPEAX@Z; StructuredQuery1::ConstantString::CreateInstance(wchar_t const *,_GUID const &,void * *)
0x180019d75  mov     ebx, eax
0x180019d77  test    eax, eax
0x180019d79  js      loc_18001A0B1
0x180019d7f  mov     rcx, [r15+28h]
0x180019d83  lea     r9, [rbp+var_18]
0x180019d87  mov     r12, [rbp+arg_8]
0x180019d8b  lea     r8, _GUID_e90f2096_c488_49bf_a9dd_62d7c84755e5
0x180019d92  mov     [rbp+var_18], r14
0x180019d96  mov     rdx, r12
0x180019d99  mov     rax, [rcx]
0x180019d9c  mov     rax, [rax+20h]
0x180019da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019da5  mov     ebx, eax
0x180019da7  test    eax, eax
0x180019da9  js      loc_18001A0A1
0x180019daf  mov     rax, [rdi]
0x180019db2  lea     rdx, [rbp+var_40]
0x180019db6  mov     rcx, rdi
0x180019db9  mov     [rbp+var_40], r14
0x180019dbd  mov     rax, [rax+18h]
0x180019dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019dc6  mov     ebx, eax
0x180019dc8  test    eax, eax
0x180019dca  js      loc_18001A091
0x180019dd0  mov     rcx, [rbp+var_40]; wchar_t *
0x180019dd4  lea     r8, [rbp+arg_8]; void **
0x180019dd8  mov     [rbp+arg_8], r14
0x180019ddc  call    ?CreateInstance@ConstantString@StructuredQuery1@@SAJPEB_WAEBU_GUID@@PEAPEAX@Z; StructuredQuery1::ConstantString::CreateInstance(wchar_t const *,_GUID const &,void * *)
0x180019de1  mov     ebx, eax
0x180019de3  test    eax, eax
0x180019de5  js      loc_18001A087
0x180019deb  mov     rcx, [r15+28h]
0x180019def  lea     rdx, [rbp+var_20]
0x180019df3  mov     r13, [rbp+arg_8]
0x180019df7  lea     r9, _GUID_e90f2096_c488_49bf_a9dd_62d7c84755e5
0x180019dfe  mov     r8, [rbp+var_18]
0x180019e02  mov     [rbp+var_20], r14
0x180019e06  mov     rax, [rcx]
0x180019e09  mov     [rsp+80h+var_60], rdx
0x180019e0e  mov     rdx, r13
0x180019e11  mov     rax, [rax+28h]
0x180019e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e1a  mov     ebx, eax
0x180019e1c  test    eax, eax
0x180019e1e  js      loc_18001A077
0x180019e24  mov     rax, [rdi]
0x180019e27  lea     r8, [rbp+var_48]
0x180019e2b  lea     rdx, _GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9
0x180019e32  mov     [rbp+var_48], r14
0x180019e36  mov     rcx, rdi
0x180019e39  mov     rax, [rax+30h]
0x180019e3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e42  mov     ebx, eax
0x180019e44  test    eax, eax
0x180019e46  js      loc_18001A067
0x180019e4c  mov     rcx, [rbp+var_48]
0x180019e50  lea     rdx, [rbp+arg_8]
0x180019e54  mov     dword ptr [rbp+arg_8], r14d
0x180019e58  mov     rax, [rcx]
0x180019e5b  mov     rax, [rax+18h]
0x180019e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e64  mov     ebx, eax
0x180019e66  mov     esi, r14d
0x180019e69  test    eax, eax
0x180019e6b  js      loc_18001A057
0x180019e71  cmp     esi, dword ptr [rbp+arg_8]
0x180019e74  jnb     loc_18001A057
0x180019e7a  mov     rcx, [rbp+var_48]
0x180019e7e  lea     r9, [rbp+arg_18]
0x180019e82  mov     [rbp+arg_18], r14
0x180019e86  lea     r8, _GUID_a3025981_c987_46f3_80f4_f838b51d4fe4
0x180019e8d  mov     edx, esi
0x180019e8f  mov     rax, [rcx]
0x180019e92  mov     rax, [rax+20h]
0x180019e96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e9b  mov     ebx, eax
0x180019e9d  test    eax, eax
0x180019e9f  js      loc_18001A04D
0x180019ea5  mov     rcx, [rbp+arg_18]
0x180019ea9  lea     rdx, [rbp+var_28]
0x180019ead  mov     [rbp+var_28], r14
0x180019eb1  mov     rax, [rcx]
0x180019eb4  mov     rax, [rax+20h]
0x180019eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ebd  mov     ebx, eax
0x180019ebf  test    eax, eax
0x180019ec1  js      loc_18001A03D
0x180019ec7  mov     rcx, [rbp+var_28]; wchar_t *
0x180019ecb  lea     r9, [rbp+arg_10]; void **
0x180019ecf  mov     [rbp+arg_10], r14
0x180019ed3  call    ?CreateInstance@RestrictionInfo@StructuredQuery1@@SAJPEB_WHAEBU_GUID@@PEAPEAX@Z; StructuredQuery1::RestrictionInfo::CreateInstance(wchar_t const *,int,_GUID const &,void * *)
0x180019ed8  mov     ebx, eax
0x180019eda  test    eax, eax
0x180019edc  js      loc_18001A033
0x180019ee2  mov     rdi, [rbp+arg_10]
0x180019ee6  lea     r8, [rbp+var_50]
0x180019eea  mov     [rbp+var_50], r14
0x180019eee  lea     rdx, _GUID_0d5f4564_b150_41f9_927d_97b1e3c8e1b0
0x180019ef5  mov     rcx, rdi
0x180019ef8  mov     rax, [rdi]
0x180019efb  mov     rax, [rax]
0x180019efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f03  mov     ebx, eax
0x180019f05  test    eax, eax
0x180019f07  js      loc_18001A024
0x180019f0d  mov     rcx, [rbp+arg_18]
0x180019f11  lea     r8, [rbp+var_30]
0x180019f15  mov     [rbp+var_30], r14
0x180019f19  lea     rdx, _GUID_d6d9aabf_5336_425a_a4b1_d0ff94bddf75
0x180019f20  mov     rax, [rcx]
0x180019f23  mov     rax, [rax+28h]
0x180019f27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f2c  mov     ebx, eax
0x180019f2e  test    eax, eax
0x180019f30  js      loc_18001A014
0x180019f36  mov     rcx, [rbp+arg_18]
0x180019f3a  lea     rdx, [rbp+var_38]
0x180019f3e  mov     [rbp+var_38], r14
0x180019f42  mov     rax, [rcx]
0x180019f45  mov     rax, [rax+18h]
0x180019f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f4e  mov     ebx, eax
0x180019f50  test    eax, eax
0x180019f52  js      loc_18001A004
0x180019f58  mov     rax, [rbp+var_50]
0x180019f5c  lea     r8, [rbp+arg_10]
0x180019f60  mov     rdx, [rbp+var_30]
0x180019f64  xor     r9d, r9d
0x180019f67  mov     rcx, r15
0x180019f6a  mov     [rsp+80h+var_58], rax
0x180019f6f  mov     dword ptr [rbp+arg_10], r14d
0x180019f73  call    ?ProcessMnemonics@CSchemaFromPropertySystem@StructuredQuery1@@AEAAJPEAUIMnemonics@@PEAH1W4KEYWORD_PREPARATION_OPTIONS@@PEAUIIndicatorAccumulator@2@@Z; StructuredQuery1::CSchemaFromPropertySystem::ProcessMnemonics(IMnemonics *,int *,int *,KEYWORD_PREPARATION_OPTIONS,StructuredQuery1::IIndicatorAccumulator *)
0x180019f78  mov     ebx, eax
0x180019f7a  test    eax, eax
0x180019f7c  js      short loc_180019FFA
0x180019f7e  mov     rdx, [rbp+var_38]; wchar_t *
0x180019f82  lea     r8, [rbp+pv]; wchar_t *
0x180019f86  mov     rcx, [rbp+var_40]; this
0x180019f8a  mov     [rbp+pv], r14
0x180019f8e  call    ?MakeNamedEntityCanonicalName@StructuredQuery1@@YAJPEB_W0PEAPEA_W@Z; StructuredQuery1::MakeNamedEntityCanonicalName(wchar_t const *,wchar_t const *,wchar_t * *)
0x180019f93  mov     ebx, eax
0x180019f95  test    eax, eax
0x180019f97  js      short loc_180019FFA
0x180019f99  mov     rax, [rdi]
0x180019f9c  mov     rcx, rdi
0x180019f9f  mov     r14, [rbp+pv]
0x180019fa3  mov     rdx, r14
0x180019fa6  mov     rax, [rax+28h]
0x180019faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019faf  mov     ebx, eax
0x180019fb1  test    eax, eax
0x180019fb3  js      short loc_180019FEE
0x180019fb5  mov     rax, [rbp+var_50]
0x180019fb9  lea     r8, [rbp+arg_10]
0x180019fbd  mov     r9d, 2
0x180019fc3  mov     [rsp+80h+var_60], rax
0x180019fc8  mov     rdx, r14
0x180019fcb  mov     rcx, r15
0x180019fce  call    ?ProcessMnemonic@CSchemaFromPropertySystem@StructuredQuery1@@AEAAJPEB_WPEAHW4KEYWORD_PREPARATION_OPTIONS@@PEAUIIndicatorAccumulator@2@@Z; StructuredQuery1::CSchemaFromPropertySystem::ProcessMnemonic(wchar_t const *,int *,KEYWORD_PREPARATION_OPTIONS,StructuredQuery1::IIndicatorAccumulator *)
0x180019fd3  mov     ebx, eax
0x180019fd5  test    eax, eax
0x180019fd7  js      short loc_180019FEE
0x180019fd9  mov     rcx, [rbp+var_20]
0x180019fdd  mov     rdx, rdi
0x180019fe0  mov     rax, [rcx]
0x180019fe3  mov     rax, [rax+70h]
0x180019fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fec  mov     ebx, eax
0x180019fee  mov     rcx, r14; pv
0x180019ff1  call    cs:__imp_CoTaskMemFree
0x180019ff7  xor     r14d, r14d
0x180019ffa  mov     rcx, [rbp+var_38]; pv
0x180019ffe  call    cs:__imp_CoTaskMemFree
0x18001a004  mov     rcx, [rbp+var_30]
0x18001a008  mov     rax, [rcx]
0x18001a00b  mov     rax, [rax+10h]
0x18001a00f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a014  mov     rcx, [rbp+var_50]
0x18001a018  mov     rax, [rcx]
0x18001a01b  mov     rax, [rax+10h]
0x18001a01f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a024  mov     rax, [rdi]
0x18001a027  mov     rcx, rdi
0x18001a02a  mov     rax, [rax+10h]
0x18001a02e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a033  mov     rcx, [rbp+var_28]; pv
0x18001a037  call    cs:__imp_CoTaskMemFree
0x18001a03d  mov     rcx, [rbp+arg_18]
0x18001a041  mov     rax, [rcx]
0x18001a044  mov     rax, [rax+10h]
0x18001a048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a04d  inc     esi
0x18001a04f  test    ebx, ebx
0x18001a051  jns     loc_180019E71
0x18001a057  mov     rcx, [rbp+var_48]
0x18001a05b  mov     rax, [rcx]
0x18001a05e  mov     rax, [rax+10h]
0x18001a062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a067  mov     rcx, [rbp+var_20]
0x18001a06b  mov     rax, [rcx]
0x18001a06e  mov     rax, [rax+10h]
0x18001a072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a077  mov     rax, [r13+0]
0x18001a07b  mov     rcx, r13
0x18001a07e  mov     rax, [rax+10h]
0x18001a082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a087  mov     rcx, [rbp+var_40]; pv
0x18001a08b  call    cs:__imp_CoTaskMemFree
0x18001a091  mov     rcx, [rbp+var_18]
0x18001a095  mov     rax, [rcx]
0x18001a098  mov     rax, [rax+10h]
0x18001a09c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0a1  mov     rax, [r12]
0x18001a0a5  mov     rcx, r12
0x18001a0a8  mov     rax, [rax+10h]
0x18001a0ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0b1  mov     rcx, [rbp+var_10]; pv
0x18001a0b5  call    cs:__imp_CoTaskMemFree
0x18001a0bb  mov     eax, ebx
0x18001a0bd  mov     rbx, [rsp+80h+arg_0]
0x18001a0c5  add     rsp, 80h
0x18001a0cc  pop     r15
0x18001a0ce  pop     r14
0x18001a0d0  pop     r13
0x18001a0d2  pop     r12
0x18001a0d4  pop     rdi
0x18001a0d5  pop     rsi
0x18001a0d6  pop     rbp
0x18001a0d7  retn
```
