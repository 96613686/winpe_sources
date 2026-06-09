# DMConfigAddProfileToMap(WWAN_PROFILE &,int,int,WWAN_PROFILE_INVALID_REASON *,ushort const * const,ushort const * const)

- ea: `0x18009f9f0`
- end: `0x1800a009a`
- name: `?DMConfigAddProfileToMap@@YAKAEAUWWAN_PROFILE@@HHPEAW4WWAN_PROFILE_INVALID_REASON@@QEBG2@Z`
- size: `1706`
- prototype: `unsigned int __usercall@<eax>(struct WWAN_PROFILE *@<rcx>, int@<edx>, int@<r8d>, enum WWAN_PROFILE_INVALID_REASON *@<r9>, const unsigned __int16 *const, const unsigned __int16 *const)`
- caller_count: `3`
- callee_count: `36`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x1800a083c`
- `0x1800a0f20`
- `0x1800a22f0`

## callees

- `0x1800085d0`
- `0x180008abc`
- `0x1800094dc`
- `0x1800094f4`
- `0x180009f78`
- `0x18000f0f4`
- `0x180011554`
- `0x180011aec`
- `0x180012300`
- `0x180013588`
- `0x180014154`
- `0x180016c50`
- `0x180018abc`
- `0x180021a04`
- `0x180021df8`
- `0x18003aa14`
- `0x18004122c`
- `0x180047f38`
- `0x180074758`
- `0x180074cec`
- `0x18009efd4`
- `0x18009f0a0`
- `0x18009f368`
- `0x18009f3d4`
- `0x18009f9f0`
- `0x1800a00a0`
- `0x1800a0aa0`
- `0x1800a0b8c`
- `0x1800a0c04`
- `0x1800a0c54`
- `0x1800a0cac`
- `0x1800a2f68`
- `0x1800a3480`
- `0x1800a431c`
- `0x1800a5b90`
- `0x1800a5c58`

## import_xrefs

- `WwanPrfl!WwanProfileCleanup` at `0x18009fc73`
- `WwanPrfl!WwanProfileCleanup` at `0x18009fc73`
- `WwanPrfl!WwanProfileGenerateFile` at `0x18009fdca`
- `WwanPrfl!WwanProfileGenerateFile` at `0x18009fdca`

## string_xrefs

- `0x18009fa3e`: `DMConfigAddProfileToMap`
- `0x18009fa92`: `DMConfigAddProfileToMap`
- `0x18009fd1e`: `DMConfigAddProfileToMap`
- `0x18009fd2a`: `DMConfigAddProfileToMap`
- `0x18009fde6`: `DMConfigAddProfileToMap`
- `0x18009fe2e`: `DMConfigAddProfileToMap`
- `0x18009feed`: `DMConfigAddProfileToMap`
- `0x18009ff2f`: `DMConfigAddProfileToMap`
- `0x18009ff3b`: `DMConfigAddProfileToMap`
- `0x1800a0022`: `DMConfigAddProfileToMap`
- `0x1800a002e`: `DMConfigAddProfileToMap`
- `0x18009fb7b`: `failed to create KeyNode, errCode (0x%8x)`
- `0x18009fabb`: `DMConfigProfileValidation failed, errCode (0x%8x)`
- `0x18009fcef`: `failed to create ProfileNode, errCode (0x%8x)`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall DMConfigAddProfileToMap(
        struct WWAN_PROFILE *a1,
        int a2,
        int a3,
        enum WWAN_PROFILE_INVALID_REASON *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6)
{
  unsigned int v10; // ebx
  const unsigned __int16 *v11; // r8
  unsigned int v12; // eax
  const unsigned __int16 *v13; // r12
  __int64 v14; // rax
  __int64 v15; // rcx
  _QWORD *v16; // rax
  const WCHAR *v17; // r14
  char *v18; // rbx
  unsigned __int64 v19; // rdx
  unsigned int v20; // eax
  __int64 CreationTypeIndex; // rbx
  __int64 v22; // rax
  _QWORD *v23; // rbx
  _QWORD *v24; // rax
  char v25; // r15
  std::_Ref_count_base *v26; // rsi
  std::_Ref_count_base *v27; // rcx
  __int64 v28; // rax
  unsigned __int64 v29; // rdx
  OLECHAR *v30; // rcx
  unsigned int v31; // eax
  __int64 v32; // rcx
  _BYTE *v33; // rax
  unsigned int File; // eax
  unsigned int inserted; // eax
  char *v36; // rbx
  __int64 v37; // r8
  const unsigned __int16 *v38; // r8
  __int64 v39; // r8
  __int64 v40; // rcx
  int v42; // eax
  void (*v43)(void *); // [rsp+20h] [rbp-E0h]
  char v44; // [rsp+30h] [rbp-D0h]
  std::_Ref_count_base *v45[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v46; // [rsp+48h] [rbp-B8h] BYREF
  LPOLESTR lpsz[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v48; // [rsp+60h] [rbp-A0h]
  _BYTE v49[8]; // [rsp+68h] [rbp-98h] BYREF
  std::_Ref_count_base *v50; // [rsp+70h] [rbp-90h]
  __int128 v51; // [rsp+88h] [rbp-78h] BYREF
  __int64 v52; // [rsp+98h] [rbp-68h]
  __int64 v53; // [rsp+A0h] [rbp-60h]
  __int128 v54; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v55; // [rsp+B8h] [rbp-48h]
  __int64 v56; // [rsp+C0h] [rbp-40h]
  _BYTE v57[32]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v58[24]; // [rsp+E8h] [rbp-18h] BYREF
  int v59; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v60[256]; // [rsp+104h] [rbp+4h] BYREF
  __int128 v61; // [rsp+304h] [rbp+204h]
  int v62; // [rsp+314h] [rbp+214h]

  v48 = a6;
  WwanLog::Enter("DMConfigAddProfileToMap");
  *(_OWORD *)lpsz = 0;
  *(_OWORD *)v45 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 7;
  LOWORD(v54) = 0;
  v51 = 0;
  v52 = 0;
  v53 = 7;
  LOWORD(v51) = 0;
  if ( !a4 )
  {
    v10 = 87;
    v11 = L"pReason is NULL (0x%8x)";
LABEL_3:
    WwanLog::Error("DMConfigAddProfileToMap", 0, v11, v10);
    goto LABEL_52;
  }
  *(_DWORD *)a4 = 0;
  v12 = DMConfigProfileValidation(a1, a2, a4);
  v10 = v12;
  if ( v12 )
  {
    WwanLog::Error("DMConfigAddProfileToMap", 0, L"DMConfigProfileValidation failed, errCode (0x%8x)", v12);
LABEL_52:
    WwanLog::Verbose("DMConfigAddProfileToMap", 0, L"errCode (0x%8x)", v10);
    WwanLog::Exit("DMConfigAddProfileToMap");
    std::wstring::_Tidy_deallocate(&v51);
    std::wstring::_Tidy_deallocate(&v54);
    if ( v45[1] )
      std::_Ref_count_base::_Decref(v45[1]);
    if ( lpsz[1] )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)lpsz[1]);
    return v10;
  }
  v13 = (const unsigned __int16 *)((char *)a1 + 3112);
  v14 = std::wstring::wstring(v49, (char *)a1 + 3112);
  std::wstring::operator=(&v51, v14);
  std::wstring::_Tidy_deallocate(v49);
  v16 = (_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<KEY_NODE>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<KEY_NODE>>>,0>>::find(
                    v15,
                    &v46,
                    &v51);
  if ( (_QWORD)xmmword_1801527E0 == *v16 )
  {
    v18 = (char *)operator new(0xA0u);
    v46 = (__int64)v18;
    `eh vector constructor iterator'(
      v18 + 80,
      0x10u,
      5u,
      std::map<std::wstring,std::shared_ptr<PROFILE_NODE>>::map<std::wstring,std::shared_ptr<PROFILE_NODE>>,
      std::map<std::wstring,std::shared_ptr<PROFILE_NODE>>::~map<std::wstring,std::shared_ptr<PROFILE_NODE>>);
    std::shared_ptr<KEY_NODE>::reset<KEY_NODE,0>(lpsz, v18);
    v17 = lpsz[0];
    if ( !lpsz[0] )
    {
      v10 = 8;
      WwanLog::Error("DMConfigAddProfileToMap", 0, L"failed to create KeyNode, errCode (0x%8x)", 8);
      goto LABEL_52;
    }
    if ( a3 )
    {
      v20 = WpKeyAllocGuid(lpsz[0], v19);
      v10 = v20;
      if ( v20 )
      {
        WwanLog::Error("DMConfigAddProfileToMap", 0, L"WpKeyAllocGuid failed, errCode (0x%8x)", v20);
        goto LABEL_52;
      }
    }
    else
    {
      StringCchCopyNW(lpsz[0], 0x27u, a5, 0x27u);
    }
    v44 = 1;
  }
  else
  {
    v44 = 0;
    std::shared_ptr<ProfileHandler>::operator=(lpsz, *v16 + 64LL);
    v17 = lpsz[0];
  }
  CreationTypeIndex = (unsigned int)getCreationTypeIndex(*((unsigned int *)a1 + 769));
  v22 = std::wstring::wstring(v49, a1);
  std::wstring::operator=(&v54, v22);
  std::wstring::_Tidy_deallocate(v49);
  v46 = 16 * (CreationTypeIndex + 5);
  v23 = (_QWORD *)((char *)v17 + v46);
  v24 = (_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<PROFILE_NODE>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<PROFILE_NODE>>>,0>>::find(
                    (char *)v17 + v46,
                    v49,
                    &v54);
  if ( *v23 == *v24 )
  {
    if ( *((_DWORD *)a1 + 801) == 1 )
    {
      *(_DWORD *)a4 = 3;
      v10 = 1206;
      v11 = L"Profile has ignorePassword enabled, but there's no exist profile. errCode (0x%8x)";
      goto LABEL_3;
    }
    v28 = std::make_shared<PROFILE_NODE,>(v49);
    std::shared_ptr<ProfileHolder>::operator=(v45, v28);
    if ( v50 )
      std::_Ref_count_base::_Decref(v50);
    v26 = v45[0];
    if ( !v45[0] )
    {
      v10 = 8;
      WwanLog::Error("DMConfigAddProfileToMap", 0, L"failed to create ProfileNode, errCode (0x%8x)", 8);
      goto LABEL_52;
    }
    v30 = (OLECHAR *)((char *)v45[0] + 6320);
    if ( a3 )
    {
      v31 = WpKeyAllocGuid(v30, v29);
      v10 = v31;
      if ( v31 )
      {
        WwanLog::Error("DMConfigAddProfileToMap", 0, L"WpKeyAllocGuid failed, errCode (0x%8x)", v31);
        WwanLog::Exit("DMConfigAddProfileToMap");
        goto LABEL_52;
      }
    }
    else
    {
      StringCchCopyNW(v30, 0x27u, v48, 0x27u);
    }
    memcpy_0(v26, a1, 0x18B0u);
    *((_QWORD *)a1 + 557) = 0;
    if ( a3 )
    {
      v32 = 512;
      v33 = (char *)v26 + 3928;
      do
      {
        *v33++ = 0;
        --v32;
      }
      while ( v32 );
      *((_DWORD *)v26 + 981) = 1;
    }
    v25 = 1;
  }
  else
  {
    v25 = 0;
    std::shared_ptr<ProfileHandler>::operator=(v45, *v24 + 64LL);
    v26 = v45[0];
    v27 = v45[0];
    if ( *((_DWORD *)a1 + 801) == 1 )
    {
      *((_QWORD *)a1 + 557) = *((_QWORD *)v45[0] + 557);
      *((_DWORD *)a1 + 1112) = *((_DWORD *)v26 + 1112);
      *((_DWORD *)a1 + 800) |= 4u;
      *((_DWORD *)a1 + 981) = 1;
      *((_DWORD *)a1 + 801) = 0;
    }
    else
    {
      WwanProfileCleanup(v45[0]);
      v27 = v26;
    }
    memcpy_0(v27, a1, 0x18B0u);
    *((_QWORD *)a1 + 557) = 0;
  }
  if ( a3 )
  {
    if ( !v25 )
      WwanFsDeleteFile((const unsigned __int16 *)v26 + 3160, 1u);
    File = WwanProfileGenerateFile(v26, (char *)v26 + 6320, 1);
    v10 = File;
    if ( File )
    {
      LODWORD(v43) = File;
      WwanLog::Error(
        "DMConfigAddProfileToMap",
        0,
        L"WwanProfileGenerateFile failed (name %s), errCode (0x%8x)",
        (char *)v26 + 6320,
        v43);
      WwanFsDiagnoseDirectory(v10, 1);
      goto LABEL_52;
    }
    inserted = WwanRegInsertProfile(v17, (WCHAR *)v26 + 3160, 0, 0, 1);
    v10 = inserted;
    if ( inserted )
    {
      WwanLog::Error("DMConfigAddProfileToMap", 0, L"WwanRegInsertProfile failed, errCode (0x%8x)", inserted);
LABEL_51:
      WwanFsDeleteFile((const unsigned __int16 *)v26 + 3160, 1u);
      goto LABEL_52;
    }
    v13 = (const unsigned __int16 *)((char *)a1 + 3112);
  }
  if ( v25 )
  {
    v36 = (char *)v17 + v46;
    std::wstring::wstring(v57, &v54);
    std::shared_ptr<ProfileHandler>::shared_ptr<ProfileHandler>(v58, v45, v37);
    std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<PROFILE_NODE>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<PROFILE_NODE>>>,0>>::_Emplace<std::pair<std::wstring,std::shared_ptr<PROFILE_NODE>>>(
      v36,
      v49,
      v57);
    std::pair<std::wstring,std::shared_ptr<ProfileHolder>>::~pair<std::wstring,std::shared_ptr<ProfileHolder>>(v57);
    if ( !(_BYTE)v50 )
    {
      v38 = L" Failed to insert profilenode into map [0x%8x]";
LABEL_50:
      v10 = 14;
      WwanLog::Error("DMConfigAddProfileToMap", 0, v38, 14);
      WwanRegRemoveProfile(v17, (LPCWSTR)v26 + 3160, 1);
      goto LABEL_51;
    }
  }
  if ( v44 )
  {
    std::wstring::wstring(v57, &v51);
    std::shared_ptr<ProfileHandler>::shared_ptr<ProfileHandler>(v58, lpsz, v39);
    std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<KEY_NODE>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<KEY_NODE>>>,0>>::_Emplace<std::pair<std::wstring,std::shared_ptr<KEY_NODE>>>(
      v40,
      v49,
      v57);
    std::pair<std::wstring,std::shared_ptr<ProfileHolder>>::~pair<std::wstring,std::shared_ptr<ProfileHolder>>(v57);
    if ( !(_BYTE)v50 )
    {
      v38 = L" Failed to insert KeyNode into map [0x%8x]";
      goto LABEL_50;
    }
  }
  if ( a3 )
  {
    memset_0(v60, 0, 0x210u);
    v59 = 0;
    StringCchCopyW(v60, 0x100u, (const unsigned __int16 *)a1);
    v61 = *((_OWORD *)a1 + 294);
    v42 = *((_DWORD *)a1 + 769);
    if ( v42 == 4 || !v42 && !*((_DWORD *)a1 + 1174) && v25 == 1 )
    {
      v62 = 0;
    }
    else
    {
      v62 = 1;
      if ( (*((_DWORD *)a1 + 1384) & 0x4000) != 0 )
        _notifyLTEAttachProfileUpdate(v13);
    }
    _notifyDMConfigProfileUpdate(v13, (struct WWAN_DMPROFILE_UPDATE_INFO *)&v59);
  }
  WwanLog::Verbose("DMConfigAddProfileToMap", 0, L"errCode (0x%8x)", 0);
  WwanLog::Exit("DMConfigAddProfileToMap");
  std::wstring::_Tidy_deallocate(&v51);
  std::wstring::_Tidy_deallocate(&v54);
  if ( v45[1] )
    std::_Ref_count_base::_Decref(v45[1]);
  if ( lpsz[1] )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)lpsz[1]);
  return 0;
}

```

## disassembly

```asm
0x18009f9f0  mov     [rsp-8+arg_10], rbx
0x18009f9f5  push    rbp
0x18009f9f6  push    rsi
0x18009f9f7  push    rdi
0x18009f9f8  push    r12
0x18009f9fa  push    r13
0x18009f9fc  push    r14
0x18009f9fe  push    r15
0x18009fa00  lea     rbp, [rsp-230h]
0x18009fa08  sub     rsp, 330h
0x18009fa0f  mov     rax, cs:__security_cookie
0x18009fa16  xor     rax, rsp
0x18009fa19  mov     [rbp+260h+var_40], rax
0x18009fa20  mov     rsi, r9
0x18009fa23  mov     r13d, r8d
0x18009fa26  mov     ebx, edx
0x18009fa28  mov     rdi, rcx
0x18009fa2b  mov     r15, [rbp+260h+arg_20]
0x18009fa32  mov     rax, [rbp+260h+arg_28]
0x18009fa39  mov     [rsp+360h+var_300], rax
0x18009fa3e  lea     rcx, aDmconfigaddpro; "DMConfigAddProfileToMap"
0x18009fa45  call    ?Enter@WwanLog@@SAXPEBD@Z; WwanLog::Enter(char const *)
0x18009fa4a  xorps   xmm0, xmm0
0x18009fa4d  movdqu  xmmword ptr [rsp+360h+lpsz], xmm0
0x18009fa53  movdqu  xmmword ptr [rsp+360h+var_328], xmm0
0x18009fa59  movups  [rbp+260h+var_2B8], xmm0
0x18009fa5d  xor     edx, edx
0x18009fa5f  mov     [rbp+260h+var_2A8], rdx
0x18009fa63  lea     ecx, [rdx+7]
0x18009fa66  mov     [rbp+260h+var_2A0], rcx
0x18009fa6a  mov     word ptr [rbp+260h+var_2B8], dx
0x18009fa6e  movups  [rbp+260h+var_2D8], xmm0
0x18009fa72  mov     [rbp+260h+var_2C8], rdx
0x18009fa76  mov     [rbp+260h+var_2C0], rcx
0x18009fa7a  mov     word ptr [rbp+260h+var_2D8], dx
0x18009fa7e  test    rsi, rsi
0x18009fa81  jnz     short loc_18009FAA3
0x18009fa83  lea     ebx, [rdx+57h]
0x18009fa86  lea     r8, aPreasonIsNull0; "pReason is NULL (0x%8x)"
0x18009fa8d  mov     r9d, ebx
0x18009fa90  xor     edx, edx; struct _GUID *
0x18009fa92  lea     rcx, aDmconfigaddpro; "DMConfigAddProfileToMap"
0x18009fa99  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18009fa9e  jmp     loc_18009FF23
0x18009faa3  mov     [rsi], edx
0x18009faa5  mov     r8, rsi; enum WWAN_PROFILE_INVALID_REASON *
0x18009faa8  mov     edx, ebx; int
0x18009faaa  mov     rcx, rdi; struct WWAN_PROFILE *
0x18009faad  call    ?DMConfigProfileValidation@@YAKAEAUWWAN_PROFILE@@HPEAW4WWAN_PROFILE_INVALID_REASON@@@Z; DMConfigProfileValidation(WWAN_PROFILE &,int,WWAN_PROFILE_INVALID_REASON *)
0x18009fab2  mov     ebx, eax
0x18009fab4  test    eax, eax
0x18009fab6  jz      short loc_18009FAC4
0x18009fab8  mov     r9d, eax
0x18009fabb  lea     r8, aDmconfigprofil; "DMConfigProfileValidation failed, errCo"...
0x18009fac2  jmp     short loc_18009FA90
0x18009fac4  lea     r12, [rdi+0C28h]
0x18009facb  mov     rdx, r12
0x18009face  lea     rcx, [rsp+360h+var_2F8]
0x18009fad3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009fad8  mov     rdx, rax
0x18009fadb  lea     rcx, [rbp+260h+var_2D8]
0x18009fadf  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18009fae4  lea     rcx, [rsp+360h+var_2F8]
0x18009fae9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009faee  lea     r8, [rbp+260h+var_2D8]
0x18009faf2  lea     rdx, [rsp+360h+var_318]
0x18009faf7  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UKEY_NODE@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UKEY_NODE@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UKEY_NODE@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<KEY_NODE>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<KEY_NODE>>>,0>>::find(std::wstring const &)
0x18009fafc  mov     rdx, [rax]
0x18009faff  cmp     qword ptr cs:xmmword_1801527E0, rdx
0x18009fb06  jz      short loc_18009FB25
0x18009fb08  mov     [rsp+360h+var_330], 0
0x18009fb0d  add     rdx, 40h ; '@'
0x18009fb11  lea     rcx, [rsp+360h+lpsz]
0x18009fb16  call    ??4?$shared_ptr@VProfileHandler@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ProfileHandler>::operator=(std::shared_ptr<ProfileHandler> const &)
0x18009fb1b  mov     r14, [rsp+360h+lpsz]
0x18009fb20  jmp     loc_18009FBC0
0x18009fb25  mov     ecx, 0A0h; Size
0x18009fb2a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009fb2f  mov     rbx, rax
0x18009fb32  mov     [rsp+360h+var_318], rax
0x18009fb37  lea     rcx, [rax+50h]; void *
0x18009fb3b  lea     rax, ??1?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UPROFILE_NODE@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UPROFILE_NODE@@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::shared_ptr<PROFILE_NODE>>::~map<std::wstring,std::shared_ptr<PROFILE_NODE>>(void)
0x18009fb42  mov     [rsp+360h+var_340], rax; void (*)(void *)
0x18009fb47  lea     r9, ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UPROFILE_NODE@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UPROFILE_NODE@@@2@@std@@@2@@std@@QEAA@XZ; void (*)(void *)
0x18009fb4e  mov     edx, 10h; unsigned __int64
0x18009fb53  lea     r8d, [rdx-0Bh]; unsigned __int64
0x18009fb57  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18009fb5c  nop
0x18009fb5d  mov     rdx, rbx
0x18009fb60  lea     rcx, [rsp+360h+lpsz]
0x18009fb65  call    ??$reset@UKEY_NODE@@$0A@@?$shared_ptr@UKEY_NODE@@@std@@QEAAXPEAUKEY_NODE@@@Z; std::shared_ptr<KEY_NODE>::reset<KEY_NODE,0>(KEY_NODE *)
0x18009fb6a  mov     r14, [rsp+360h+lpsz]
0x18009fb6f  test    r14, r14
0x18009fb72  jnz     short loc_18009FB87
0x18009fb74  lea     r9d, [r14+8]
0x18009fb78  mov     ebx, r9d
0x18009fb7b  lea     r8, aFailedToCreate; "failed to create KeyNode, errCode (0x%8"...
0x18009fb82  jmp     loc_18009FA90
0x18009fb87  mov     rcx, r14; unsigned __int16 *
0x18009fb8a  test    r13d, r13d
0x18009fb8d  jz      short loc_18009FBA9
0x18009fb8f  call    ?WpKeyAllocGuid@@YAKPEAG_K@Z; WpKeyAllocGuid(ushort *,unsigned __int64)
0x18009fb94  mov     ebx, eax
0x18009fb96  test    eax, eax
0x18009fb98  jz      short loc_18009FBBB
0x18009fb9a  mov     r9d, eax
0x18009fb9d  lea     r8, aWpkeyallocguid; "WpKeyAllocGuid failed, errCode (0x%8x)"
0x18009fba4  jmp     loc_18009FA90
0x18009fba9  mov     eax, 27h ; '''
0x18009fbae  mov     r9d, eax; unsigned __int64
0x18009fbb1  mov     r8, r15; unsigned __int16 *
0x18009fbb4  mov     edx, eax; unsigned __int64
0x18009fbb6  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18009fbbb  mov     [rsp+360h+var_330], 1
0x18009fbc0  mov     ecx, [rdi+0C04h]
0x18009fbc6  call    ?getCreationTypeIndex@@YAKW4WWAN_PROFILE_CREATION_TYPE@@@Z; getCreationTypeIndex(WWAN_PROFILE_CREATION_TYPE)
0x18009fbcb  mov     ebx, eax
0x18009fbcd  mov     rdx, rdi
0x18009fbd0  lea     rcx, [rsp+360h+var_2F8]
0x18009fbd5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009fbda  mov     rdx, rax
0x18009fbdd  lea     rcx, [rbp+260h+var_2B8]
0x18009fbe1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18009fbe6  lea     rcx, [rsp+360h+var_2F8]
0x18009fbeb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009fbf0  lea     rax, [rbx+5]
0x18009fbf4  shl     rax, 4
0x18009fbf8  mov     [rsp+360h+var_318], rax
0x18009fbfd  lea     rbx, [r14+rax]
0x18009fc01  lea     r8, [rbp+260h+var_2B8]
0x18009fc05  lea     rdx, [rsp+360h+var_2F8]
0x18009fc0a  mov     rcx, rbx
0x18009fc0d  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UPROFILE_NODE@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UPROFILE_NODE@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UPROFILE_NODE@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<PROFILE_NODE>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<PROFILE_NODE>>>,0>>::find(std::wstring const &)
0x18009fc12  mov     rdx, [rax]
0x18009fc15  cmp     [rbx], rdx
0x18009fc18  jz      short loc_18009FC98
0x18009fc1a  xor     r15b, r15b
0x18009fc1d  add     rdx, 40h ; '@'
0x18009fc21  lea     rcx, [rsp+360h+var_328]
0x18009fc26  call    ??4?$shared_ptr@VProfileHandler@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ProfileHandler>::operator=(std::shared_ptr<ProfileHandler> const &)
0x18009fc2b  mov     rsi, [rsp+360h+var_328]
0x18009fc30  mov     rcx, rsi
0x18009fc33  cmp     dword ptr [rdi+0C84h], 1
0x18009fc3a  jnz     short loc_18009FC73
0x18009fc3c  mov     rax, [rsi+1168h]
0x18009fc43  mov     [rdi+1168h], rax
0x18009fc4a  mov     eax, [rsi+1160h]
0x18009fc50  mov     [rdi+1160h], eax
0x18009fc56  or      dword ptr [rdi+0C80h], 4
0x18009fc5d  mov     dword ptr [rdi+0F54h], 1
0x18009fc67  mov     dword ptr [rdi+0C84h], 0
0x18009fc71  jmp     short loc_18009FC7C
0x18009fc73  call    cs:__imp_WwanProfileCleanup
0x18009fc79  mov     rcx, rsi; void *
0x18009fc7c  mov     r8d, 18B0h; Size
0x18009fc82  mov     rdx, rdi; Src
0x18009fc85  call    memcpy_0
0x18009fc8a  xor     eax, eax
0x18009fc8c  mov     [rdi+1168h], rax
0x18009fc93  jmp     loc_18009FD95
0x18009fc98  cmp     dword ptr [rdi+0C84h], 1
0x18009fc9f  jnz     short loc_18009FCB8
0x18009fca1  mov     dword ptr [rsi], 3
0x18009fca7  mov     ebx, 4B6h
0x18009fcac  lea     r8, aProfileHasIgno; "Profile has ignorePassword enabled, but"...
0x18009fcb3  jmp     loc_18009FA8D
0x18009fcb8  lea     rcx, [rsp+360h+var_2F8]
0x18009fcbd  call    ??$make_shared@UPROFILE_NODE@@$$V@std@@YA?AV?$shared_ptr@UPROFILE_NODE@@@0@XZ; std::make_shared<PROFILE_NODE,>(void)
0x18009fcc2  mov     rdx, rax
0x18009fcc5  lea     rcx, [rsp+360h+var_328]
0x18009fcca  call    ??4?$shared_ptr@VProfileHolder@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ProfileHolder>::operator=(std::shared_ptr<ProfileHolder> &&)
0x18009fccf  mov     rcx, [rsp+360h+var_2F0]; this
0x18009fcd4  test    rcx, rcx
0x18009fcd7  jz      short loc_18009FCDE
0x18009fcd9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18009fcde  mov     rsi, [rsp+360h+var_328]
0x18009fce3  test    rsi, rsi
0x18009fce6  jnz     short loc_18009FCFB
0x18009fce8  lea     r9d, [rsi+8]
0x18009fcec  mov     ebx, r9d
0x18009fcef  lea     r8, aFailedToCreate_2; "failed to create ProfileNode, errCode ("...
0x18009fcf6  jmp     loc_18009FA90
0x18009fcfb  lea     rcx, [rsi+18B0h]; unsigned __int16 *
0x18009fd02  test    r13d, r13d
0x18009fd05  jz      short loc_18009FD3B
0x18009fd07  call    ?WpKeyAllocGuid@@YAKPEAG_K@Z; WpKeyAllocGuid(ushort *,unsigned __int64)
0x18009fd0c  mov     ebx, eax
0x18009fd0e  test    eax, eax
0x18009fd10  jz      short loc_18009FD4F
0x18009fd12  mov     r9d, eax
0x18009fd15  lea     r8, aWpkeyallocguid; "WpKeyAllocGuid failed, errCode (0x%8x)"
0x18009fd1c  xor     edx, edx; struct _GUID *
0x18009fd1e  lea     rcx, aDmconfigaddpro; "DMConfigAddProfileToMap"
0x18009fd25  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18009fd2a  lea     rcx, aDmconfigaddpro; "DMConfigAddProfileToMap"
0x18009fd31  call    ?Exit@WwanLog@@SAXPEBD@Z; WwanLog::Exit(char const *)
0x18009fd36  jmp     loc_18009FF23
0x18009fd3b  mov     eax, 27h ; '''
0x18009fd40  mov     r9d, eax; unsigned __int64
0x18009fd43  mov     r8, [rsp+360h+var_300]; unsigned __int16 *
0x18009fd48  mov     edx, eax; unsigned __int64
0x18009fd4a  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18009fd4f  mov     r8d, 18B0h; Size
0x18009fd55  mov     rdx, rdi; Src
0x18009fd58  mov     rcx, rsi; void *
0x18009fd5b  call    memcpy_0
0x18009fd60  mov     qword ptr [rdi+1168h], 0
0x18009fd6b  test    r13d, r13d
0x18009fd6e  jz      short loc_18009FD92
0x18009fd70  mov     ecx, 200h
0x18009fd75  lea     rax, [rsi+0F58h]
0x18009fd7c  mov     byte ptr [rax], 0
0x18009fd7f  inc     rax
0x18009fd82  sub     rcx, 1
0x18009fd86  jnz     short loc_18009FD7C
0x18009fd88  mov     dword ptr [rsi+0F54h], 1
0x18009fd92  mov     r15b, 1
0x18009fd95  test    r13d, r13d
0x18009fd98  jz      loc_18009FE46
0x18009fd9e  test    r15b, r15b
0x18009fda1  jnz     short loc_18009FDB4
0x18009fda3  lea     rcx, [rsi+18B0h]; unsigned __int16 *
0x18009fdaa  mov     edx, 1; int
0x18009fdaf  call    ?WwanFsDeleteFile@@YAKPEBGH@Z; WwanFsDeleteFile(ushort const *,int)
0x18009fdb4  lea     r12, [rsi+18B0h]
0x18009fdbb  mov     r9d, 1
0x18009fdc1  mov     r8d, r9d
0x18009fdc4  mov     rdx, r12
0x18009fdc7  mov     rcx, rsi
0x18009fdca  call    cs:__imp_WwanProfileGenerateFile
0x18009fdd0  mov     ebx, eax
0x18009fdd2  test    eax, eax
0x18009fdd4  jz      short loc_18009FE03
0x18009fdd6  mov     dword ptr [rsp+360h+var_340], eax
0x18009fdda  mov     r9, r12
0x18009fddd  lea     r8, aWwanprofilegen_0; "WwanProfileGenerateFile failed (name %s"...
0x18009fde4  xor     edx, edx; struct _GUID *
0x18009fde6  lea     rcx, aDmconfigaddpro; "DMConfigAddProfileToMap"
0x18009fded  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18009fdf2  mov     edx, 1; int
0x18009fdf7  mov     ecx, ebx; unsigned int
0x18009fdf9  call    ?WwanFsDiagnoseDirectory@@YAXKH@Z; WwanFsDiagnoseDirectory(ulong,int)
0x18009fdfe  jmp     loc_18009FF23
0x18009fe03  mov     dword ptr [rsp+360h+var_340], 1; int
0x18009fe0b  xor     r9d, r9d; unsigned int
0x18009fe0e  xor     r8d, r8d; unsigned int
0x18009fe11  mov     rdx, r12; Src
0x18009fe14  mov     rcx, r14; lpSubKey
0x18009fe17  call    ?WwanRegInsertProfile@@YAKPEBG0KKH@Z; WwanRegInsertProfile(ushort const *,ushort const *,ulong,ulong,int)
0x18009fe1c  mov     ebx, eax
0x18009fe1e  test    eax, eax
0x18009fe20  jz      short loc_18009FE3F
0x18009fe22  mov     r9d, eax
0x18009fe25  lea     r8, aWwanreginsertp; "WwanRegInsertProfile failed, errCode (0"...
0x18009fe2c  xor     edx, edx; struct _GUID *
0x18009fe2e  lea     rcx, aDmconfigaddpro; "DMConfigAddProfileToMap"
0x18009fe35  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18009fe3a  jmp     loc_18009FF12
0x18009fe3f  lea     r12, [rdi+0C28h]
0x18009fe46  test    r15b, r15b
0x18009fe49  jz      short loc_18009FE9A
0x18009fe4b  mov     rbx, [rsp+360h+var_318]
0x18009fe50  add     rbx, r14
0x18009fe53  lea     rdx, [rbp+260h+var_2B8]
0x18009fe57  lea     rcx, [rbp+260h+var_298]
0x18009fe5b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18009fe60  lea     rdx, [rsp+360h+var_328]
0x18009fe65  lea     rcx, [rbp+260h+var_278]
0x18009fe69  call    ??0?$shared_ptr@VProfileHandler@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ProfileHandler>::shared_ptr<ProfileHandler>(std::shared_ptr<ProfileHandler> const &)
0x18009fe6e  nop
0x18009fe6f  lea     r8, [rbp+260h+var_298]
0x18009fe73  lea     rdx, [rsp+360h+var_2F8]
0x18009fe78  mov     rcx, rbx
0x18009fe7b  call    ??$_Emplace@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UPROFILE_NODE@@@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UPROFILE_NODE@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UPROFILE_NODE@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UPROFILE_NODE@@@2@@std@@PEAX@std@@_N@1@$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UPROFILE_NODE@@@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<PROFILE_NODE>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<PROFILE_NODE>>>,0>>::_Emplace<std::pair<std::wstring,std::shared_ptr<PROFILE_NODE>>>(std::pair<std::wstring,std::shared_ptr<PROFILE_NODE>> &&)
0x18009fe80  nop
0x18009fe81  lea     rcx, [rbp+260h+var_298]
0x18009fe85  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VProfileHolder@@@2@@std@@QEAA@XZ; std::pair<std::wstring,std::shared_ptr<ProfileHolder>>::~pair<std::wstring,std::shared_ptr<ProfileHolder>>(void)
0x18009fe8a  cmp     byte ptr [rsp+360h+var_2F0], 0
0x18009fe8f  jnz     short loc_18009FE9A
0x18009fe91  lea     r8, aFailedToInsert_4; " Failed to insert profilenode into map "...
0x18009fe98  jmp     short loc_18009FEEB
0x18009fe9a  cmp     [rsp+360h+var_330], 0
0x18009fe9f  jz      loc_18009FF82
0x18009fea5  lea     rdx, [rbp+260h+var_2D8]
0x18009fea9  lea     rcx, [rbp+260h+var_298]
0x18009fead  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18009feb2  lea     rdx, [rsp+360h+lpsz]
0x18009feb7  lea     rcx, [rbp+260h+var_278]
0x18009febb  call    ??0?$shared_ptr@VProfileHandler@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ProfileHandler>::shared_ptr<ProfileHandler>(std::shared_ptr<ProfileHandler> const &)
0x18009fec0  nop
0x18009fec1  lea     r8, [rbp+260h+var_298]
0x18009fec5  lea     rdx, [rsp+360h+var_2F8]
0x18009feca  call    ??$_Emplace@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UKEY_NODE@@@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UKEY_NODE@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UKEY_NODE@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UKEY_NODE@@@2@@std@@PEAX@std@@_N@1@$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UKEY_NODE@@@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<KEY_NODE>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<KEY_NODE>>>,0>>::_Emplace<std::pair<std::wstring,std::shared_ptr<KEY_NODE>>>(std::pair<std::wstring,std::shared_ptr<KEY_NODE>> &&)
0x18009fecf  nop
0x18009fed0  lea     rcx, [rbp+260h+var_298]
0x18009fed4  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VProfileHolder@@@2@@std@@QEAA@XZ; std::pair<std::wstring,std::shared_ptr<ProfileHolder>>::~pair<std::wstring,std::shared_ptr<ProfileHolder>>(void)
0x18009fed9  cmp     byte ptr [rsp+360h+var_2F0], 0
0x18009fede  jnz     loc_18009FF82
0x18009fee4  lea     r8, aFailedToInsert; " Failed to insert KeyNode into map [0x%"...
0x18009feeb  xor     edx, edx; struct _GUID *
  ... truncated ...
```
