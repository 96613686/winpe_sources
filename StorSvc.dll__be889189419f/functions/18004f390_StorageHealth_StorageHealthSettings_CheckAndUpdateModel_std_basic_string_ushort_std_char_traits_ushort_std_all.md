# StorageHealth::StorageHealthSettings::CheckAndUpdateModel(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18004f390`
- end: `0x18004f969`
- name: `?CheckAndUpdateModel@StorageHealthSettings@StorageHealth@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1497`
- prototype: `__int64 __fastcall(StorageHealth::StorageHealthSettings *this)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18004d8b8`

## callees

- `0x180001148`
- `0x180004180`
- `0x18000d030`
- `0x18000d560`
- `0x18001c130`
- `0x18001c208`
- `0x18001f634`
- `0x18002e740`
- `0x18002e854`
- `0x18002ebb4`
- `0x180034018`
- `0x1800343b4`
- `0x18004d530`
- `0x18004ec68`
- `0x18004ecf8`
- `0x18004eebc`
- `0x18004ef70`
- `0x18004f0b4`
- `0x18004f1f8`
- `0x18004f29c`
- `0x18004f390`
- `0x18004f970`
- `0x18004fb74`
- `0x180050098`
- `0x180050184`
- `0x1800505dc`
- `0x1800562d4`
- `0x18008a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x18004f48d`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x18004f510`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x18004f48d`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x18004f510`

## string_xrefs

- `0x18004f56c`: `SettingsPublishToRegistryFailed`
- `0x18004f829`: `SettingsPublishToRegistryFailed`
- `0x18004f565`: `SettingsGetFromRegistryFailed`
- `0x18004f832`: `SettingsUpdateModelSuccess`
- `0x18004f801`: `SettingsUpdateModelFailed`
- `0x18004f773`: `SettingsComparisonFailed`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall StorageHealth::StorageHealthSettings::CheckAndUpdateModel(
        StorageHealth::StorageHealthSettings *this,
        __int64 a2)
{
  int Value; // esi
  const char *v5; // rdi
  unsigned int MajorModelVersionOnDevice; // r13d
  __int64 v7; // rbx
  __int64 v8; // rax
  const wchar_t *v9; // rax
  int v10; // ebx
  __int64 v11; // rbx
  __int64 v12; // rax
  const wchar_t *v13; // rax
  const WCHAR *v14; // rax
  const WCHAR *v15; // rax
  __int64 v16; // r8
  int v17; // eax
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 i; // rbx
  __int64 v21; // rdi
  __int64 v22; // rax
  int v23; // edi
  int v24; // eax
  int v25; // r9d
  __int64 v26; // r14
  __int64 (__fastcall *v27)(__int64, __int64, __int64, __int128 *); // rsi
  __int64 v28; // rdi
  __int64 v29; // rax
  _QWORD *v30; // rax
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, __int64, _QWORD *); // rbx
  __int64 v33; // rax
  const WCHAR *v34; // rax
  __int64 v35; // r8
  __int64 v36; // rcx
  __int64 v37; // r8
  __int64 v38; // r9
  _BYTE v40[4]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v41; // [rsp+54h] [rbp-ACh] BYREF
  void *v42; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v43[2]; // [rsp+60h] [rbp-A0h] BYREF
  const char *v44; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v45; // [rsp+78h] [rbp-88h] BYREF
  __int64 v46; // [rsp+80h] [rbp-80h] BYREF
  std::_Ref_count_base *v47; // [rsp+88h] [rbp-78h]
  _QWORD v48[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v49; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v50; // [rsp+B0h] [rbp-50h]
  __int128 v51; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v52; // [rsp+C8h] [rbp-38h]
  const char *v53; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD *v54; // [rsp+E0h] [rbp-20h]
  _BYTE v55[32]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v56[32]; // [rsp+118h] [rbp+18h] BYREF
  __int64 v57; // [rsp+138h] [rbp+38h]
  _BYTE v58[32]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v59[32]; // [rsp+160h] [rbp+60h] BYREF
  __int128 v60; // [rsp+180h] [rbp+80h] BYREF
  __int64 v61; // [rsp+190h] [rbp+90h]
  __int64 v62; // [rsp+198h] [rbp+98h]
  __int128 v63; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v64; // [rsp+1B0h] [rbp+B0h]
  __int64 v65; // [rsp+1B8h] [rbp+B8h]

  v57 = a2;
  Value = 0;
  v5 = "SettingsGetDefaultSuccess";
  v63 = 0;
  v64 = 0;
  v65 = 7;
  LOWORD(v63) = 0;
  v60 = 0;
  v61 = 0;
  v62 = 7;
  LOWORD(v60) = 0;
  MajorModelVersionOnDevice = 0;
  v41 = 0;
  v45 = 0;
  if ( *((_BYTE *)this + 64) )
  {
    std::wstring::wstring((__int64)v59, (__int64)L"MajorModelVersion");
    v7 = *((_QWORD *)this + 7);
    v8 = std::wstring::wstring((__int64)&v51, (__int64)v59);
    if ( (int)StorageHealth::OneSettings::GetValue(v7, v8, (__int64)&v60) >= 0 )
    {
      v9 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v60);
      v10 = wcstol(v9, 0, 10);
      MajorModelVersionOnDevice = StorageHealth::StorageHealthSettings::GetMajorModelVersionOnDevice(this);
      if ( v10 == MajorModelVersionOnDevice )
      {
        std::wstring::wstring((__int64)v58, (__int64)L"MinorModelVersion");
        v11 = *((_QWORD *)this + 7);
        v12 = std::wstring::wstring((__int64)&v51, (__int64)v58);
        Value = StorageHealth::OneSettings::GetValue(v11, v12, (__int64)&v60);
        if ( Value >= 0 )
        {
          v13 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v60);
          v41 = wcstol(v13, 0, 10);
          v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v58);
          Value = QueryStorageRegSetting(
                    L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\StorageHealth",
                    v14,
                    4,
                    (BYTE *)&v45);
          if ( Value >= 0 )
          {
            if ( v41 > v45 )
            {
              v42 = operator new(1u);
              v18 = std::wstring::wstring((__int64)&v51, a2);
              StorageHealth::PredictorFactory::GetPredictor(v19, &v46, 1, v18);
              std::map<std::wstring,std::vector<double>>::map<std::wstring,std::vector<double>>(v43);
              Value = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v46 + 8LL))(v46, v43);
              if ( Value >= 0 )
              {
                v49 = 0;
                v50 = 0;
                Value = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v46 + 16LL))(v46, &v49);
                if ( Value >= 0 )
                {
                  for ( i = v49; i != *((_QWORD *)&v49 + 1); i += 32 )
                  {
                    std::wstring::operator=(&v63, i);
                    v21 = *((_QWORD *)this + 7);
                    v22 = std::wstring::wstring((__int64)&v53, (__int64)&v63);
                    Value = StorageHealth::OneSettings::GetValue(v21, v22, (__int64)&v60);
                    if ( Value < 0 )
                    {
                      v5 = "SettingsGetFromOnesettingsFailed";
                      goto LABEL_34;
                    }
                    v40[0] = 0;
                    v44 = v56;
                    v23 = std::wstring::wstring((__int64)v56, (__int64)&v60);
                    v24 = std::wstring::wstring((__int64)v55, (__int64)L"unchanged");
                    Value = StorageHealth::StorageHealthSettings::CompareSettings(
                              (unsigned int)v40,
                              v24,
                              v23,
                              v25,
                              (__int64)v40);
                    if ( Value < 0 )
                    {
                      v5 = "SettingsComparisonFailed";
                      goto LABEL_34;
                    }
                    if ( !v40[0] )
                    {
                      v51 = 0;
                      v52 = 0;
                      v26 = v46;
                      v27 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int128 *))(*(_QWORD *)v46 + 24LL);
                      v44 = v55;
                      v28 = std::wstring::wstring((__int64)v55, (__int64)&v60);
                      v29 = std::wstring::wstring((__int64)v56, (__int64)&v63);
                      Value = v27(v26, v29, v28, &v51);
                      if ( Value < 0 )
                      {
                        v5 = "SettingsParseModelParamsFailed";
                        std::vector<StorageHealth::Feature>::~vector<StorageHealth::Feature>(&v51);
                        goto LABEL_34;
                      }
                      v30 = (_QWORD *)std::map<std::wstring,std::vector<unsigned __int64>>::_Try_emplace<std::wstring const &,>(
                                        v43,
                                        v48,
                                        &v63);
                      std::vector<double>::operator=(*v30 + 64LL, &v51);
                      std::vector<StorageHealth::Feature>::~vector<StorageHealth::Feature>(&v51);
                    }
                  }
                  v31 = v46;
                  v32 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v46 + 40LL);
                  v44 = (const char *)v48;
                  v48[0] = 0;
                  v48[1] = 0;
                  v53 = (const char *)v48;
                  v54 = v48;
                  v48[0] = std::_Tree_node<std::pair<std::wstring const,std::vector<double>>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::vector<double>>,void *>>>();
                  std::_Tree<std::_Tmap_traits<std::wstring,std::vector<double>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::vector<double>>>,0>>::_Copy<0>(
                    v48,
                    v43);
                  v54 = 0;
                  std::_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::vector<double>>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::vector<double>>>>>::~_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::vector<double>>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::vector<double>>>>>(&v53);
                  v33 = std::wstring::wstring((__int64)v55, a2);
                  Value = v32(v31, v33, v48);
                  if ( Value >= 0 )
                  {
                    v34 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v58);
                    v5 = "SettingsPublishToRegistryFailed";
                    if ( (int)PublishStorageRegSetting(
                                L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\StorageHealth",
                                v34,
                                v35,
                                (const BYTE *)&v41) >= 0 )
                      v5 = "SettingsUpdateModelSuccess";
                  }
                  else
                  {
                    v5 = "SettingsUpdateModelFailed";
                  }
                }
                else
                {
                  v5 = "SettingsGetModelParamNamesFailed";
                }
LABEL_34:
                std::vector<std::wstring>::_Tidy(&v49);
              }
              else
              {
                v5 = "SettingsGetExistingModelFailed";
              }
              std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::vector<double>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::vector<double>>,void *>>>(
                v43,
                v43);
              if ( v47 )
                std::_Ref_count_base::_Decref(v47);
              std::unique_ptr<StorageHealth::SignalArchiver>::~unique_ptr<StorageHealth::SignalArchiver>(&v42);
            }
          }
          else
          {
            v15 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v58);
            v17 = PublishStorageRegSetting(
                    L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\StorageHealth",
                    v15,
                    v16,
                    (const BYTE *)&v41);
            if ( v17 < 0 )
              Value = v17;
            v5 = "SettingsPublishToRegistryFailed";
            if ( v17 >= 0 )
              v5 = "SettingsGetFromRegistryFailed";
          }
        }
        else
        {
          v5 = "SettingsGetFromOnesettingsFailed";
        }
        std::wstring::_Tidy_deallocate(v58);
      }
      else
      {
        Value = -2147023590;
        v5 = "SettingsModelVesionMismatch";
      }
    }
    else
    {
      Value = -2147023590;
      v5 = "SettingsGetFromOnesettingsFailed";
    }
    std::wstring::_Tidy_deallocate(v59);
  }
  if ( (unsigned int)dword_1800BF100 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800BF100, 0x400000000000LL) )
  {
    LODWORD(v42) = Value;
    v48[0] = v41;
    v46 = v45;
    v43[0] = MajorModelVersionOnDevice;
    v53 = v5;
    v44 = "ModelVersions";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v36,
      (__int64)byte_1800A85D9,
      v37,
      v38,
      (const unsigned __int16 **)&v44,
      (const unsigned __int16 **)&v53,
      (__int64)v43,
      (__int64)&v46,
      (__int64)v48,
      (__int64)&v42);
  }
  std::wstring::_Tidy_deallocate(&v60);
  std::wstring::_Tidy_deallocate(&v63);
  std::wstring::_Tidy_deallocate(a2);
  return (unsigned int)Value;
}

```

## disassembly

```asm
0x18004f390  mov     [rsp-8+arg_10], rbx
0x18004f395  push    rbp
0x18004f396  push    rsi
0x18004f397  push    rdi
0x18004f398  push    r12
0x18004f39a  push    r13
0x18004f39c  push    r14
0x18004f39e  push    r15
0x18004f3a0  lea     rbp, [rsp-0D0h]
0x18004f3a8  sub     rsp, 1D0h
0x18004f3af  mov     rax, cs:__security_cookie
0x18004f3b6  xor     rax, rsp
0x18004f3b9  mov     [rbp+100h+var_40], rax
0x18004f3c0  mov     r12, rdx
0x18004f3c3  mov     r15, rcx
0x18004f3c6  mov     [rbp+100h+var_C8], rdx
0x18004f3ca  xor     r14d, r14d
0x18004f3cd  mov     esi, r14d
0x18004f3d0  lea     rdi, aSettingsgetdef; "SettingsGetDefaultSuccess"
0x18004f3d7  xorps   xmm0, xmm0
0x18004f3da  movups  [rbp+100h+var_60], xmm0
0x18004f3e1  mov     [rbp+100h+var_50], r14
0x18004f3e8  lea     ecx, [r14+7]
0x18004f3ec  mov     [rbp+100h+var_48], rcx
0x18004f3f3  mov     word ptr [rbp+100h+var_60], r14w
0x18004f3fb  movups  [rbp+100h+var_80], xmm0
0x18004f402  mov     [rbp+100h+var_70], r14
0x18004f409  mov     [rbp+100h+var_68], rcx
0x18004f410  mov     word ptr [rbp+100h+var_80], r14w
0x18004f418  mov     r13d, r14d
0x18004f41b  mov     [rsp+200h+var_1AC], r14d
0x18004f420  mov     [rsp+200h+var_188], r14d
0x18004f425  cmp     [r15+40h], r14b
0x18004f429  jz      loc_18004F880
0x18004f42f  lea     rdx, aMajormodelvers; "MajorModelVersion"
0x18004f436  lea     rcx, [rbp+100h+var_A0]
0x18004f43a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004f43f  nop
0x18004f440  mov     rbx, [r15+38h]
0x18004f444  lea     rdx, [rbp+100h+var_A0]
0x18004f448  lea     rcx, [rbp+100h+var_148]
0x18004f44c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004f451  lea     r8, [rbp+100h+var_80]
0x18004f458  mov     rdx, rax
0x18004f45b  mov     rcx, rbx
0x18004f45e  call    ?GetValue@OneSettings@StorageHealth@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV34@@Z; StorageHealth::OneSettings::GetValue(std::wstring,std::wstring &)
0x18004f463  test    eax, eax
0x18004f465  jns     short loc_18004F478
0x18004f467  mov     esi, 8007051Ah
0x18004f46c  lea     rdi, aSettingsgetfro_0; "SettingsGetFromOnesettingsFailed"
0x18004f473  jmp     loc_18004F877
0x18004f478  lea     rcx, [rbp+100h+var_80]
0x18004f47f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004f484  mov     rcx, rax; String
0x18004f487  xor     edx, edx; EndPtr
0x18004f489  lea     r8d, [rdx+0Ah]; Radix
0x18004f48d  call    cs:__imp_wcstol
0x18004f493  mov     ebx, eax
0x18004f495  mov     rcx, r15; this
0x18004f498  call    ?GetMajorModelVersionOnDevice@StorageHealthSettings@StorageHealth@@QEAAKXZ; StorageHealth::StorageHealthSettings::GetMajorModelVersionOnDevice(void)
0x18004f49d  mov     r13d, eax
0x18004f4a0  cmp     ebx, eax
0x18004f4a2  jz      short loc_18004F4B5
0x18004f4a4  mov     esi, 8007051Ah
0x18004f4a9  lea     rdi, aSettingsmodelv; "SettingsModelVesionMismatch"
0x18004f4b0  jmp     loc_18004F877
0x18004f4b5  lea     rdx, aMinormodelvers; "MinorModelVersion"
0x18004f4bc  lea     rcx, [rbp+100h+var_C0]
0x18004f4c0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004f4c5  nop
0x18004f4c6  mov     rbx, [r15+38h]
0x18004f4ca  lea     rdx, [rbp+100h+var_C0]
0x18004f4ce  lea     rcx, [rbp+100h+var_148]
0x18004f4d2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004f4d7  lea     r8, [rbp+100h+var_80]
0x18004f4de  mov     rdx, rax
0x18004f4e1  mov     rcx, rbx
0x18004f4e4  call    ?GetValue@OneSettings@StorageHealth@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV34@@Z; StorageHealth::OneSettings::GetValue(std::wstring,std::wstring &)
0x18004f4e9  mov     esi, eax
0x18004f4eb  test    eax, eax
0x18004f4ed  jns     short loc_18004F4FB
0x18004f4ef  lea     rdi, aSettingsgetfro_0; "SettingsGetFromOnesettingsFailed"
0x18004f4f6  jmp     loc_18004F86D
0x18004f4fb  lea     rcx, [rbp+100h+var_80]
0x18004f502  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004f507  mov     rcx, rax; String
0x18004f50a  xor     edx, edx; EndPtr
0x18004f50c  lea     r8d, [rdx+0Ah]; Radix
0x18004f510  call    cs:__imp_wcstol
0x18004f516  mov     [rsp+200h+var_1AC], eax
0x18004f51a  lea     rcx, [rbp+100h+var_C0]
0x18004f51e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004f523  mov     rdx, rax; lpValueName
0x18004f526  lea     r9, [rsp+200h+var_188]; void *
0x18004f52b  mov     r8d, 4; unsigned int
0x18004f531  lea     rcx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004f538  call    ?QueryStorageRegSetting@@YAJPEBG0KPEAX@Z; QueryStorageRegSetting(ushort const *,ushort const *,ulong,void *)
0x18004f53d  mov     esi, eax
0x18004f53f  test    eax, eax
0x18004f541  jns     short loc_18004F57C
0x18004f543  lea     rcx, [rbp+100h+var_C0]
0x18004f547  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004f54c  mov     rdx, rax; lpValueName
0x18004f54f  lea     r9, [rsp+200h+var_1AC]; void *
0x18004f554  lea     rcx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004f55b  call    ?PublishStorageRegSetting@@YAJPEBG0KPEAXH@Z; PublishStorageRegSetting(ushort const *,ushort const *,ulong,void *,int)
0x18004f560  test    eax, eax
0x18004f562  cmovs   esi, eax
0x18004f565  lea     rcx, aSettingsgetfro_1; "SettingsGetFromRegistryFailed"
0x18004f56c  lea     rdi, aSettingspublis; "SettingsPublishToRegistryFailed"
0x18004f573  cmovns  rdi, rcx
0x18004f577  jmp     loc_18004F86D
0x18004f57c  mov     eax, [rsp+200h+var_188]
0x18004f580  cmp     [rsp+200h+var_1AC], eax
0x18004f584  jbe     loc_18004F86D
0x18004f58a  mov     ebx, 1
0x18004f58f  mov     ecx, ebx; Size
0x18004f591  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004f596  mov     [rsp+200h+var_1A8], rax
0x18004f59b  mov     rdx, r12
0x18004f59e  lea     rcx, [rbp+100h+var_148]
0x18004f5a2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004f5a7  mov     r9, rax
0x18004f5aa  mov     r8d, ebx
0x18004f5ad  lea     rdx, [rbp+100h+var_180]
0x18004f5b1  call    ?GetPredictor@PredictorFactory@StorageHealth@@QEAA?AV?$shared_ptr@UPredictor@StorageHealth@@@std@@W4PredictionModel@2@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; StorageHealth::PredictorFactory::GetPredictor(StorageHealth::PredictionModel,std::wstring)
0x18004f5b6  nop
0x18004f5b7  lea     rcx, [rsp+200h+var_1A0]
0x18004f5bc  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@NV?$allocator@N@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@NV?$allocator@N@std@@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::vector<double>>::map<std::wstring,std::vector<double>>(void)
0x18004f5c1  nop
0x18004f5c2  mov     rcx, [rbp+100h+var_180]
0x18004f5c6  mov     rax, [rcx]
0x18004f5c9  lea     rdx, [rsp+200h+var_1A0]
0x18004f5ce  mov     rax, [rax+8]
0x18004f5d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f5d7  mov     esi, eax
0x18004f5d9  test    eax, eax
0x18004f5db  jns     short loc_18004F5E9
0x18004f5dd  lea     rdi, aSettingsgetexi; "SettingsGetExistingModelFailed"
0x18004f5e4  jmp     loc_18004F843
0x18004f5e9  xorps   xmm0, xmm0
0x18004f5ec  movdqu  [rbp+100h+var_160], xmm0
0x18004f5f1  mov     [rbp+100h+var_150], r14
0x18004f5f5  mov     rcx, [rbp+100h+var_180]
0x18004f5f9  mov     rax, [rcx]
0x18004f5fc  lea     rdx, [rbp+100h+var_160]
0x18004f600  mov     rax, [rax+10h]
0x18004f604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f609  mov     esi, eax
0x18004f60b  test    eax, eax
0x18004f60d  jns     short loc_18004F61B
0x18004f60f  lea     rdi, aSettingsgetmod; "SettingsGetModelParamNamesFailed"
0x18004f616  jmp     loc_18004F839
0x18004f61b  mov     rbx, qword ptr [rbp+100h+var_160]
0x18004f61f  cmp     rbx, qword ptr [rbp+100h+var_160+8]
0x18004f623  jz      loc_18004F78B
0x18004f629  mov     rdx, rbx
0x18004f62c  lea     rcx, [rbp+100h+var_60]
0x18004f633  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004f638  mov     rdi, [r15+38h]
0x18004f63c  lea     rdx, [rbp+100h+var_60]
0x18004f643  lea     rcx, [rbp+100h+var_128]
0x18004f647  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004f64c  lea     r8, [rbp+100h+var_80]
0x18004f653  mov     rdx, rax
0x18004f656  mov     rcx, rdi
0x18004f659  call    ?GetValue@OneSettings@StorageHealth@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV34@@Z; StorageHealth::OneSettings::GetValue(std::wstring,std::wstring &)
0x18004f65e  mov     esi, eax
0x18004f660  test    eax, eax
0x18004f662  js      loc_18004F77F
0x18004f668  mov     [rsp+200h+var_1B0], r14b
0x18004f66d  lea     rax, [rbp+100h+var_E8]
0x18004f671  mov     [rsp+200h+var_190], rax
0x18004f676  lea     rdx, [rbp+100h+var_80]
0x18004f67d  lea     rcx, [rbp+100h+var_E8]
0x18004f681  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004f686  mov     rdi, rax
0x18004f689  lea     rdx, aUnchanged; "unchanged"
0x18004f690  lea     rcx, [rbp+100h+var_108]
0x18004f694  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004f699  nop
0x18004f69a  lea     rcx, [rsp+200h+var_1B0]
0x18004f69f  mov     [rsp+200h+var_1E0], rcx
0x18004f6a4  mov     r8, rdi
0x18004f6a7  mov     rdx, rax
0x18004f6aa  call    ?CompareSettings@StorageHealthSettings@StorageHealth@@AEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_NAEA_N@Z; StorageHealth::StorageHealthSettings::CompareSettings(std::wstring,std::wstring,bool,bool &)
0x18004f6af  mov     esi, eax
0x18004f6b1  test    eax, eax
0x18004f6b3  js      loc_18004F773
0x18004f6b9  cmp     [rsp+200h+var_1B0], r14b
0x18004f6be  jnz     loc_18004F755
0x18004f6c4  xorps   xmm0, xmm0
0x18004f6c7  movdqu  [rbp+100h+var_148], xmm0
0x18004f6cc  mov     [rbp+100h+var_138], r14
0x18004f6d0  mov     r14, [rbp+100h+var_180]
0x18004f6d4  mov     rax, [r14]
0x18004f6d7  mov     rsi, [rax+18h]
0x18004f6db  lea     rax, [rbp+100h+var_108]
0x18004f6df  mov     [rsp+200h+var_190], rax
0x18004f6e4  lea     rdx, [rbp+100h+var_80]
0x18004f6eb  lea     rcx, [rbp+100h+var_108]
0x18004f6ef  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004f6f4  mov     rdi, rax
0x18004f6f7  lea     rdx, [rbp+100h+var_60]
0x18004f6fe  lea     rcx, [rbp+100h+var_E8]
0x18004f702  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004f707  nop
0x18004f708  lea     r9, [rbp+100h+var_148]
0x18004f70c  mov     r8, rdi
0x18004f70f  mov     rdx, rax
0x18004f712  mov     rcx, r14
0x18004f715  mov     rax, rsi
0x18004f718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f71d  mov     esi, eax
0x18004f71f  xor     r14d, r14d
0x18004f722  test    eax, eax
0x18004f724  js      short loc_18004F75E
0x18004f726  lea     r8, [rbp+100h+var_60]
0x18004f72d  lea     rdx, [rbp+100h+var_170]
0x18004f731  lea     rcx, [rsp+200h+var_1A0]
0x18004f736  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@_KV?$allocator@_K@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@_KV?$allocator@_K@std@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@_KV?$allocator@_K@std@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::vector<unsigned __int64>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18004f73b  mov     rcx, [rax]
0x18004f73e  add     rcx, 40h ; '@'
0x18004f742  lea     rdx, [rbp+100h+var_148]
0x18004f746  call    ??4?$vector@NV?$allocator@N@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<double>::operator=(std::vector<double> const &)
0x18004f74b  nop
0x18004f74c  lea     rcx, [rbp+100h+var_148]
0x18004f750  call    ??1?$vector@UFeature@StorageHealth@@V?$allocator@UFeature@StorageHealth@@@std@@@std@@QEAA@XZ; std::vector<StorageHealth::Feature>::~vector<StorageHealth::Feature>(void)
0x18004f755  add     rbx, 20h ; ' '
0x18004f759  jmp     loc_18004F61F
0x18004f75e  lea     rdi, aSettingsparsem; "SettingsParseModelParamsFailed"
0x18004f765  lea     rcx, [rbp+100h+var_148]
0x18004f769  call    ??1?$vector@UFeature@StorageHealth@@V?$allocator@UFeature@StorageHealth@@@std@@@std@@QEAA@XZ; std::vector<StorageHealth::Feature>::~vector<StorageHealth::Feature>(void)
0x18004f76e  jmp     loc_18004F839
0x18004f773  lea     rdi, aSettingscompar; "SettingsComparisonFailed"
0x18004f77a  jmp     loc_18004F839
0x18004f77f  lea     rdi, aSettingsgetfro_0; "SettingsGetFromOnesettingsFailed"
0x18004f786  jmp     loc_18004F839
0x18004f78b  mov     rdi, [rbp+100h+var_180]
0x18004f78f  mov     rax, [rdi]
0x18004f792  mov     rbx, [rax+28h]
0x18004f796  lea     rax, [rbp+100h+var_170]
0x18004f79a  mov     [rsp+200h+var_190], rax
0x18004f79f  mov     [rbp+100h+var_170], r14
0x18004f7a3  mov     [rbp+100h+var_168], r14
0x18004f7a7  lea     rax, [rbp+100h+var_170]
0x18004f7ab  mov     [rbp+100h+var_128], rax
0x18004f7af  lea     rax, [rbp+100h+var_170]
0x18004f7b3  mov     [rbp+100h+var_120], rax
0x18004f7b7  call    ??$_Buyheadnode@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@NV?$allocator@N@std@@@2@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@NV?$allocator@N@std@@@2@@std@@PEAX@std@@SAPEAU01@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@NV?$allocator@N@std@@@2@@std@@PEAX@std@@@1@@Z; std::_Tree_node<std::pair<std::wstring const,std::vector<double>>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::vector<double>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::vector<double>>,void *>> &)
0x18004f7bc  mov     [rbp+100h+var_170], rax
0x18004f7c0  lea     rdx, [rsp+200h+var_1A0]
0x18004f7c5  lea     rcx, [rbp+100h+var_170]
0x18004f7c9  call    ??$_Copy@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@NV?$allocator@N@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@NV?$allocator@N@std@@@2@@std@@@2@$0A@@std@@@std@@IEAAXAEBV01@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::vector<double>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::vector<double>>>,0>>::_Copy<0>(std::_Tree<std::_Tmap_traits<std::wstring,std::vector<double>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::vector<double>>>,0>> const &)
0x18004f7ce  mov     [rbp+100h+var_120], r14
0x18004f7d2  lea     rcx, [rbp+100h+var_128]
0x18004f7d6  call    ??1?$_Tree_head_scoped_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@NV?$allocator@N@std@@@2@@std@@PEAX@std@@@std@@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@NV?$allocator@N@std@@@2@@std@@@std@@@2@@std@@QEAA@XZ; std::_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::vector<double>>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::vector<double>>>>>::~_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::vector<double>>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::vector<double>>>>>(void)
0x18004f7db  nop
0x18004f7dc  mov     rdx, r12
0x18004f7df  lea     rcx, [rbp+100h+var_108]
0x18004f7e3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004f7e8  nop
0x18004f7e9  lea     r8, [rbp+100h+var_170]
0x18004f7ed  mov     rdx, rax
0x18004f7f0  mov     rcx, rdi
0x18004f7f3  mov     rax, rbx
0x18004f7f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f7fb  mov     esi, eax
0x18004f7fd  test    eax, eax
0x18004f7ff  jns     short loc_18004F80A
0x18004f801  lea     rdi, aSettingsupdate_0; "SettingsUpdateModelFailed"
0x18004f808  jmp     short loc_18004F839
0x18004f80a  lea     rcx, [rbp+100h+var_C0]
0x18004f80e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004f813  mov     rdx, rax; lpValueName
0x18004f816  lea     r9, [rsp+200h+var_1AC]; void *
0x18004f81b  lea     rcx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004f822  call    ?PublishStorageRegSetting@@YAJPEBG0KPEAXH@Z; PublishStorageRegSetting(ushort const *,ushort const *,ulong,void *,int)
0x18004f827  test    eax, eax
0x18004f829  lea     rdi, aSettingspublis; "SettingsPublishToRegistryFailed"
0x18004f830  js      short loc_18004F839
0x18004f832  lea     rdi, aSettingsupdate; "SettingsUpdateModelSuccess"
0x18004f839  lea     rcx, [rbp+100h+var_160]
0x18004f83d  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18004f842  nop
0x18004f843  lea     rdx, [rsp+200h+var_1A0]
0x18004f848  lea     rcx, [rsp+200h+var_1A0]
0x18004f84d  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@NV?$allocator@N@std@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@NV?$allocator@N@std@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@NV?$allocator@N@std@@@2@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::vector<double>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::vector<double>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::vector<double>>,void *>> &)
0x18004f852  nop
0x18004f853  mov     rcx, [rbp+100h+var_178]; this
0x18004f857  test    rcx, rcx
0x18004f85a  jz      short loc_18004F862
0x18004f85c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004f861  nop
0x18004f862  lea     rcx, [rsp+200h+var_1A8]
0x18004f867  call    ??1?$unique_ptr@VSignalArchiver@StorageHealth@@U?$default_delete@VSignalArchiver@StorageHealth@@@std@@@std@@QEAA@XZ; std::unique_ptr<StorageHealth::SignalArchiver>::~unique_ptr<StorageHealth::SignalArchiver>(void)
0x18004f86c  nop
0x18004f86d  lea     rcx, [rbp+100h+var_C0]
0x18004f871  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004f876  nop
  ... truncated ...
```
