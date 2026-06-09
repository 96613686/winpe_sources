# wpc::AppLimits::AppInventory::AppInventoryStorage::LoadAppInventoryLocalCache(void)

- ea: `0x18001757c`
- end: `0x180017e9e`
- name: `?LoadAppInventoryLocalCache@AppInventoryStorage@AppInventory@AppLimits@wpc@@SA?AV?$map@VSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@U?$less@VSid@@@3@V?$allocator@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@@3@@std@@XZ`
- size: `2338`
- prototype: `__int64 *__fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180015dfc`

## callees

- `0x1800032a0`
- `0x1800032c4`
- `0x180005950`
- `0x180005a04`
- `0x180005f9c`
- `0x18000f100`
- `0x180010488`
- `0x180015728`
- `0x180015888`
- `0x180015a54`
- `0x180015d60`
- `0x1800160ac`
- `0x180016574`
- `0x180016804`
- `0x18001757c`
- `0x18001938c`
- `0x18001941c`
- `0x180026734`
- `0x1800286e8`
- `0x18002c010`

## string_xrefs

- `0x180017b26`: `LastUpdatedTime`

## pseudocode

```c
__int64 *__fastcall wpc::AppLimits::AppInventory::AppInventoryStorage::LoadAppInventoryLocalCache(__int64 *a1)
{
  _QWORD *v2; // rax
  int v3; // r14d
  __int64 v4; // r8
  __int64 v5; // rbx
  __int64 (__fastcall *v6)(__int64, void (__fastcall ****)(_QWORD, __int64), __int128 *); // rdi
  unsigned __int64 v7; // r8
  _QWORD *v8; // rax
  void (__fastcall ***v9)(_QWORD, __int64); // rcx
  __int64 v10; // rcx
  _QWORD *v11; // rax
  _QWORD *v12; // rbx
  __int64 v13; // rdx
  _QWORD *v14; // rax
  void (__fastcall ***v15)(_QWORD, __int64); // rcx
  _QWORD *v16; // rax
  __int64 v17; // rcx
  _QWORD *v18; // rax
  _QWORD *v19; // rbx
  _QWORD *v20; // rax
  void (__fastcall ***v21)(_QWORD, __int64); // rdi
  void (__fastcall *v22)(_QWORD, __int64); // rbx
  _QWORD *v23; // rax
  char **v24; // rcx
  __int64 v25; // rbx
  appids::AnyRuntimeApp *v26; // rax
  void (__fastcall ***v27)(_QWORD, __int64); // rdi
  void (__fastcall *v28)(_QWORD, __int64); // rbx
  _QWORD *v29; // rax
  char **v30; // rcx
  void (__fastcall ***v31)(_QWORD, __int64); // rdi
  void (__fastcall *v32)(_QWORD, __int64); // rbx
  _QWORD *v33; // rax
  char **v34; // rcx
  void (__fastcall ***v35)(_QWORD, __int64); // rdi
  void (__fastcall *v36)(_QWORD, __int64); // rbx
  _QWORD *v37; // rax
  char **v38; // rcx
  volatile signed __int32 *v39; // rbx
  volatile signed __int32 *v40; // rbx
  volatile signed __int32 *v41; // rbx
  volatile signed __int32 *v42; // rbx
  volatile signed __int32 *v43; // rbx
  volatile signed __int32 *v44; // rbx
  void (__fastcall ***v45)(_QWORD, _QWORD); // rcx
  __int64 v47; // [rsp+20h] [rbp-E0h]
  void (__fastcall ***v48)(_QWORD, __int64); // [rsp+28h] [rbp-D8h] BYREF
  void (__fastcall ***v49)(_QWORD, __int64); // [rsp+30h] [rbp-D0h] BYREF
  void (__fastcall ***v50)(_QWORD, __int64); // [rsp+38h] [rbp-C8h] BYREF
  void *v51[2]; // [rsp+40h] [rbp-C0h] BYREF
  void (__fastcall ***v52)(_QWORD, __int64); // [rsp+50h] [rbp-B0h] BYREF
  void (__fastcall ***v53)(_QWORD, __int64); // [rsp+58h] [rbp-A8h] BYREF
  void (__fastcall ***v54)(_QWORD, __int64); // [rsp+60h] [rbp-A0h] BYREF
  void (__fastcall ***v55)(_QWORD, __int64); // [rsp+68h] [rbp-98h] BYREF
  void (__fastcall ***v56)(_QWORD, __int64); // [rsp+70h] [rbp-90h] BYREF
  void (__fastcall ***v57)(_QWORD, __int64); // [rsp+78h] [rbp-88h] BYREF
  __int64 v58; // [rsp+80h] [rbp-80h] BYREF
  volatile signed __int32 *v59; // [rsp+88h] [rbp-78h]
  __int64 v60; // [rsp+90h] [rbp-70h] BYREF
  volatile signed __int32 *v61; // [rsp+98h] [rbp-68h]
  char v62[8]; // [rsp+A0h] [rbp-60h] BYREF
  volatile signed __int32 *v63; // [rsp+A8h] [rbp-58h]
  __int64 v64; // [rsp+B0h] [rbp-50h] BYREF
  volatile signed __int32 *v65; // [rsp+B8h] [rbp-48h]
  char v66[8]; // [rsp+C0h] [rbp-40h] BYREF
  volatile signed __int32 *v67; // [rsp+C8h] [rbp-38h]
  _QWORD v68[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v69; // [rsp+E0h] [rbp-20h] BYREF
  volatile signed __int32 *v70; // [rsp+E8h] [rbp-18h]
  __int64 *v71; // [rsp+F0h] [rbp-10h]
  _BYTE *v72; // [rsp+F8h] [rbp-8h]
  _BYTE v73[40]; // [rsp+108h] [rbp+8h] BYREF
  char v74[16]; // [rsp+130h] [rbp+30h] BYREF
  char v75[80]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v76; // [rsp+190h] [rbp+90h] BYREF
  __int64 v77; // [rsp+1A0h] [rbp+A0h]
  __int64 v78; // [rsp+1A8h] [rbp+A8h]
  _BYTE v79[40]; // [rsp+1B0h] [rbp+B0h] BYREF
  char **v80; // [rsp+1D8h] [rbp+D8h]
  __int128 v81; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v82; // [rsp+1F0h] [rbp+F0h]
  __int64 v83; // [rsp+1F8h] [rbp+F8h]
  __int128 v84; // [rsp+200h] [rbp+100h] BYREF
  __int64 v85; // [rsp+210h] [rbp+110h]
  __int64 v86; // [rsp+218h] [rbp+118h]
  char v87[8]; // [rsp+220h] [rbp+120h] BYREF
  char *v88; // [rsp+228h] [rbp+128h] BYREF
  char v89; // [rsp+248h] [rbp+148h]
  char *v90; // [rsp+250h] [rbp+150h] BYREF
  char v91[48]; // [rsp+270h] [rbp+170h] BYREF
  __int64 v92; // [rsp+2A0h] [rbp+1A0h]
  char *v93[14]; // [rsp+2B0h] [rbp+1B0h] BYREF
  _BYTE v94[32]; // [rsp+320h] [rbp+220h] BYREF
  char v95; // [rsp+340h] [rbp+240h]
  _BYTE v96[32]; // [rsp+348h] [rbp+248h] BYREF
  char v97; // [rsp+368h] [rbp+268h]
  _BYTE v98[32]; // [rsp+370h] [rbp+270h] BYREF
  char v99; // [rsp+390h] [rbp+290h]
  char v100[40]; // [rsp+3A0h] [rbp+2A0h] BYREF
  char **v101; // [rsp+3C8h] [rbp+2C8h]
  _BYTE v102[72]; // [rsp+3D0h] [rbp+2D0h] BYREF
  char *v103; // [rsp+418h] [rbp+318h] BYREF

  v71 = a1;
  *a1 = 0;
  a1[1] = 0;
  v2 = operator new(0x98u);
  *v2 = v2;
  v2[1] = v2;
  v2[2] = v2;
  *((_WORD *)v2 + 12) = 257;
  *a1 = (__int64)v2;
  ReadRegistryT<256>::TryOpen(v91, -2147483646, L"Software\\Microsoft\\Windows\\CurrentVersion\\Parental Controls");
  v3 = 3;
  v4 = v92;
  if ( v92 )
  {
    v5 = v92 + *(int *)(*(_QWORD *)(v92 + 16) + 4LL);
    v6 = *(__int64 (__fastcall **)(__int64, void (__fastcall ****)(_QWORD, __int64), __int128 *))(*(_QWORD *)(v5 + 16)
                                                                                                + 24LL);
    v81 = 0;
    v82 = 0;
    v83 = 0;
    v7 = -1;
    do
      ++v7;
    while ( aAppinventory[v7] );
    std::wstring::_Construct<1,unsigned short const *>(&v81, L"AppInventory", v7);
    v8 = (_QWORD *)v6(v5 + 16, &v49, &v81);
    (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*v8 + 56LL))(*v8, &v50);
    if ( v49 )
      (**v49)(v49, 1);
    std::wstring::~wstring((char **)&v81);
    v9 = v50;
    if ( v50 )
    {
      (*v50)[1](v50, (__int64)v66);
      Collections::Enumerable<std::wstring>::begin(v66, &v60);
      Collections::Enumerable<std::wstring>::end(v10, &v64);
      while ( v60 != v64 )
      {
        v11 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
        v12 = v11;
        if ( v11[3] <= 7u )
          LODWORD(v13) = (_DWORD)v11;
        else
          v13 = *v11;
        Sid::FromString((__int64)v102, v13);
        v3 |= 4u;
        LODWORD(v47) = v3;
        v14 = (_QWORD *)((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, __int64), void (__fastcall ****)(_QWORD, __int64), _QWORD *))(*v50)[3])(
                          v50,
                          &v52,
                          v12);
        (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*v14 + 56LL))(*v14, &v49);
        if ( v52 )
          (**v52)(v52, 1);
        v15 = v49;
        if ( v49 )
        {
          v51[0] = 0;
          v51[1] = 0;
          v16 = operator new(0x158u);
          *v16 = v16;
          v16[1] = v16;
          v16[2] = v16;
          *((_WORD *)v16 + 12) = 257;
          v51[0] = v16;
          (*v49)[1](v49, (__int64)v62);
          Collections::Enumerable<std::wstring>::begin(v62, &v58);
          Collections::Enumerable<std::wstring>::end(v17, &v69);
          while ( v58 != v69 )
          {
            v18 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
            v19 = v18;
            if ( v18[3] > 7u )
              v18 = (_QWORD *)*v18;
            v68[0] = v18;
            v68[1] = v19[2];
            appids::FromPlatformIndependentString(v87, v68);
            v20 = (_QWORD *)((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, __int64), void (__fastcall ****)(_QWORD, __int64), _QWORD *))(*v49)[3])(
                              v49,
                              &v53,
                              v19);
            (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*v20 + 56LL))(*v20, &v48);
            if ( v53 )
              (**v53)(v53, 1);
            v21 = v48;
            if ( v48 )
            {
              v22 = (*v48)[3];
              v84 = 0;
              v85 = 0;
              v86 = 0;
              std::wstring::_Construct<1,unsigned short const *>(&v84, L"DisplayName", 0xBu);
              v23 = (_QWORD *)((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, __int64), void (__fastcall ****)(_QWORD, __int64), __int128 *))v22)(
                                v21,
                                &v54,
                                &v84);
              (*(void (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v23 + 40LL))(*v23, v100);
              if ( v54 )
                (**v54)(v54, 1);
              std::wstring::~wstring((char **)&v84);
              v24 = v101;
              if ( v101 )
              {
                v72 = v73;
                v25 = std::wstring::wstring((__int64)v73, (__int64)v101);
                v26 = appids::AnyRuntimeApp::AnyRuntimeApp(
                        (appids::AnyRuntimeApp *)v75,
                        (const struct appids::AnyRuntimeApp *)v87);
                wpc::AppLimits::AppInventory::AppInfo::AppInfo(v93, v26, v25);
                v27 = v48;
                v28 = (*v48)[3];
                v76 = 0;
                v77 = 0;
                v78 = 0;
                std::wstring::_Construct<1,unsigned short const *>(&v76, L"FirstUsedTime", 0xDu);
                v29 = (_QWORD *)((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, __int64), void (__fastcall ****)(_QWORD, __int64), __int128 *))v28)(
                                  v27,
                                  &v55,
                                  &v76);
                (*(void (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v29 + 40LL))(*v29, v79);
                if ( v55 )
                  (**v55)(v55, 1);
                std::wstring::~wstring((char **)&v76);
                v30 = v80;
                if ( v80 )
                {
                  if ( v95 )
                  {
                    std::wstring::operator=(v94, v80);
                  }
                  else
                  {
                    std::wstring::wstring((__int64)v94, (__int64)v80);
                    v95 = 1;
                  }
                  v30 = v80;
                }
                if ( v30 )
                  std::wstring::~wstring(v30);
                v31 = v48;
                v32 = (*v48)[3];
                v76 = 0;
                v77 = 0;
                v78 = 0;
                std::wstring::_Construct<1,unsigned short const *>(&v76, L"LastUsedTime", 0xCu);
                v33 = (_QWORD *)((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, __int64), void (__fastcall ****)(_QWORD, __int64), __int128 *))v32)(
                                  v31,
                                  &v56,
                                  &v76);
                (*(void (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v33 + 40LL))(*v33, v79);
                if ( v56 )
                  (**v56)(v56, 1);
                std::wstring::~wstring((char **)&v76);
                v34 = v80;
                if ( v80 )
                {
                  if ( v97 )
                  {
                    std::wstring::operator=(v96, v80);
                  }
                  else
                  {
                    std::wstring::wstring((__int64)v96, (__int64)v80);
                    v97 = 1;
                  }
                  v34 = v80;
                }
                if ( v34 )
                  std::wstring::~wstring(v34);
                v35 = v48;
                v36 = (*v48)[3];
                v76 = 0;
                v77 = 0;
                v78 = 0;
                std::wstring::_Construct<1,unsigned short const *>(&v76, L"LastUpdatedTime", 0xFu);
                v37 = (_QWORD *)((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, __int64), void (__fastcall ****)(_QWORD, __int64), __int128 *))v36)(
                                  v35,
                                  &v57,
                                  &v76);
                (*(void (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v37 + 40LL))(*v37, v79);
                if ( v57 )
                  (**v57)(v57, 1);
                std::wstring::~wstring((char **)&v76);
                v38 = v80;
                if ( v80 )
                {
                  if ( v99 )
                  {
                    std::wstring::operator=(v98, v80);
                  }
                  else
                  {
                    std::wstring::wstring((__int64)v98, (__int64)v80);
                    v99 = 1;
                  }
                  v38 = v80;
                }
                if ( v38 )
                  std::wstring::~wstring(v38);
                std::_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>,0>>::emplace<appids::AnyRuntimeApp const &,wpc::AppLimits::AppInventory::AppInfo &>(
                  v51,
                  v74,
                  v87,
                  v93,
                  v47);
                wpc::AppLimits::AppInventory::AppInfo::~AppInfo(v93);
                v24 = v101;
              }
              if ( v24 )
                std::wstring::~wstring(v24);
              v21 = v48;
            }
            if ( v21 )
              (**v21)(v21, 1);
            std::wstring::~wstring(&v90);
            if ( v89 != -1 )
              std::wstring::~wstring(&v88);
            Collections::Private::EnumerableIterator<std::wstring>::operator++(&v58);
          }
          v39 = v70;
          if ( v70 )
          {
            if ( _InterlockedExchangeAdd(v70 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v39)(v39);
              if ( _InterlockedExchangeAdd(v39 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
            }
          }
          v40 = v59;
          if ( v59 )
          {
            if ( _InterlockedExchangeAdd(v59 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v40)(v40);
              if ( _InterlockedExchangeAdd(v40 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v40 + 8LL))(v40);
            }
          }
          v41 = v63;
          if ( v63 )
          {
            if ( _InterlockedExchangeAdd(v63 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v41)(v41);
              if ( _InterlockedExchangeAdd(v41 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v41 + 8LL))(v41);
            }
          }
          std::_Tree<std::_Tmap_traits<Sid,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>,std::less<Sid>,std::allocator<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>>,0>>::emplace<Sid const &,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo> &>(
            a1,
            (__int64)&v81,
            (__int64)v102,
            v51);
          std::_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>,0>>::~_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>,0>>(v51);
          v15 = v49;
        }
        if ( v15 )
          (**v15)(v15, 1);
        std::wstring::~wstring(&v103);
        Collections::Private::EnumerableIterator<std::wstring>::operator++(&v60);
      }
      v42 = v65;
      if ( v65 )
      {
        if ( _InterlockedExchangeAdd(v65 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v42)(v42);
          if ( _InterlockedExchangeAdd(v42 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v42 + 8LL))(v42);
        }
      }
      v43 = v61;
      if ( v61 )
      {
        if ( _InterlockedExchangeAdd(v61 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v43)(v43);
          if ( _InterlockedExchangeAdd(v43 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v43 + 8LL))(v43);
        }
      }
      v44 = v67;
      if ( v67 )
      {
        if ( _InterlockedExchangeAdd(v67 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v44)(v44);
          if ( _InterlockedExchangeAdd(v44 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v44 + 8LL))(v44);
        }
      }
      v9 = v50;
    }
    if ( v9 )
      (**v9)(v9, 1);
    v4 = v92;
  }
  if ( v4 )
  {
    v45 = (void (__fastcall ***)(_QWORD, _QWORD))(v4 + 16 + *(int *)(*(_QWORD *)(v4 + 16) + 4LL));
    (**v45)(v45, 0);
  }
  return a1;
}

```

## disassembly

```asm
0x18001757c  push    rbp
0x18001757e  push    rbx
0x18001757f  push    rsi
0x180017580  push    rdi
0x180017581  push    r12
0x180017583  push    r13
0x180017585  push    r14
0x180017587  push    r15
0x180017589  lea     rbp, [rsp-358h]
0x180017591  sub     rsp, 458h
0x180017598  mov     rax, cs:__security_cookie
0x18001759f  xor     rax, rsp
0x1800175a2  mov     [rbp+390h+var_50], rax
0x1800175a9  mov     rsi, rcx
0x1800175ac  mov     [rbp+390h+var_3A0], rcx
0x1800175b0  xor     r15d, r15d
0x1800175b3  mov     dword ptr [rsp+490h+var_470], r15d
0x1800175b8  mov     [rcx], r15
0x1800175bb  mov     [rcx+8], r15
0x1800175bf  mov     ecx, 98h; Size
0x1800175c4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800175c9  mov     [rax], rax
0x1800175cc  mov     [rax+8], rax
0x1800175d0  mov     [rax+10h], rax
0x1800175d4  lea     r13d, [r15+1]
0x1800175d8  mov     word ptr [rax+18h], 101h
0x1800175de  mov     [rsi], rax
0x1800175e1  mov     dword ptr [rsp+490h+var_470], r13d
0x1800175e6  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800175ed  mov     rdx, 0FFFFFFFF80000002h
0x1800175f4  lea     rcx, [rbp+390h+var_220]
0x1800175fb  call    ?TryOpen@?$ReadRegistryT@$0BAA@@@SA?AV?$Optional@V?$ReadRegistryT@$0BAA@@@@@PEAUHKEY__@@PEBG@Z; ReadRegistryT<256>::TryOpen(HKEY__ *,ushort const *)
0x180017600  lea     r14d, [r15+3]
0x180017604  mov     dword ptr [rsp+490h+var_470], r14d
0x180017609  mov     r8, [rbp+390h+var_1F0]
0x180017610  test    r8, r8
0x180017613  jz      loc_180017E56
0x180017619  mov     rax, [r8+10h]
0x18001761d  movsxd  rbx, dword ptr [rax+4]
0x180017621  add     rbx, r8
0x180017624  mov     rax, [rbx+10h]
0x180017628  mov     rdi, [rax+18h]
0x18001762c  mov     rdx, cs:off_180030A80; "AppInventory"
0x180017633  xorps   xmm0, xmm0
0x180017636  movups  [rbp+390h+var_2B0], xmm0
0x18001763d  mov     [rbp+390h+var_2A0], r15
0x180017644  mov     [rbp+390h+var_298], r15
0x18001764b  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001764f  mov     r8, r12
0x180017652  inc     r8
0x180017655  cmp     [rdx+r8*2], r15w
0x18001765a  jnz     short loc_180017652
0x18001765c  lea     rcx, [rbp+390h+var_2B0]
0x180017663  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180017668  nop
0x180017669  lea     r8, [rbp+390h+var_2B0]
0x180017670  lea     rdx, [rsp+490h+var_460]
0x180017675  lea     rcx, [rbx+10h]
0x180017679  mov     rax, rdi
0x18001767c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017681  nop
0x180017682  mov     rcx, [rax]
0x180017685  mov     rax, [rcx]
0x180017688  lea     rdx, [rsp+490h+var_458]
0x18001768d  mov     rax, [rax+38h]
0x180017691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017696  nop
0x180017697  mov     rcx, [rsp+490h+var_460]
0x18001769c  test    rcx, rcx
0x18001769f  jz      short loc_1800176B0
0x1800176a1  mov     rax, [rcx]
0x1800176a4  mov     edx, r13d
0x1800176a7  mov     rax, [rax]
0x1800176aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176af  nop
0x1800176b0  lea     rcx, [rbp+390h+var_2B0]
0x1800176b7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800176bc  mov     rcx, [rsp+490h+var_458]
0x1800176c1  test    rcx, rcx
0x1800176c4  jz      loc_180017E3C
0x1800176ca  mov     rax, [rcx]
0x1800176cd  lea     rdx, [rbp+390h+var_3D0]
0x1800176d1  mov     rax, [rax+8]
0x1800176d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176da  nop
0x1800176db  lea     rdx, [rbp+390h+var_400]
0x1800176df  lea     rcx, [rbp+390h+var_3D0]
0x1800176e3  call    ?begin@?$Enumerable@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Collections@@QEBA?AV?$EnumerableIterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Private@2@XZ; Collections::Enumerable<std::wstring>::begin(void)
0x1800176e8  nop
0x1800176e9  lea     rdx, [rbp+390h+var_3E0]
0x1800176ed  call    ?end@?$Enumerable@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Collections@@QEBA?AV?$EnumerableIterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Private@2@XZ; Collections::Enumerable<std::wstring>::end(void)
0x1800176f2  nop
0x1800176f3  mov     rcx, [rbp+390h+var_400]
0x1800176f7  cmp     rcx, [rbp+390h+var_3E0]
0x1800176fb  jz      loc_180017D75
0x180017701  mov     rax, [rcx]
0x180017704  mov     rax, [rax+10h]
0x180017708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001770d  mov     rbx, rax
0x180017710  cmp     qword ptr [rax+18h], 7
0x180017715  jbe     short loc_18001771C
0x180017717  mov     rdx, [rax]
0x18001771a  jmp     short loc_18001771F
0x18001771c  mov     rdx, rbx
0x18001771f  lea     rcx, [rbp+390h+var_C0]
0x180017726  call    ?FromString@Sid@@SA?AV1@PEBG@Z; Sid::FromString(ushort const *)
0x18001772b  or      r14d, 4
0x18001772f  mov     dword ptr [rsp+490h+var_470], r14d
0x180017734  mov     rcx, [rsp+490h+var_458]
0x180017739  mov     rax, [rcx]
0x18001773c  mov     r8, rbx
0x18001773f  lea     rdx, [rsp+490h+var_440]
0x180017744  mov     rax, [rax+18h]
0x180017748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001774d  nop
0x18001774e  mov     rcx, [rax]
0x180017751  mov     rax, [rcx]
0x180017754  lea     rdx, [rsp+490h+var_460]
0x180017759  mov     rax, [rax+38h]
0x18001775d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017762  nop
0x180017763  mov     rcx, [rsp+490h+var_440]
0x180017768  test    rcx, rcx
0x18001776b  jz      short loc_18001777B
0x18001776d  mov     rax, [rcx]
0x180017770  mov     edx, r13d
0x180017773  mov     rax, [rax]
0x180017776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001777b  mov     rcx, [rsp+490h+var_460]
0x180017780  test    rcx, rcx
0x180017783  jz      loc_180017D47
0x180017789  mov     [rsp+490h+var_450], r15
0x18001778e  mov     [rsp+490h+var_448], r15
0x180017793  mov     ecx, 158h; Size
0x180017798  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001779d  mov     [rax], rax
0x1800177a0  mov     [rax+8], rax
0x1800177a4  mov     [rax+10h], rax
0x1800177a8  mov     word ptr [rax+18h], 101h
0x1800177ae  mov     [rsp+490h+var_450], rax
0x1800177b3  mov     rcx, [rsp+490h+var_460]
0x1800177b8  mov     rax, [rcx]
0x1800177bb  lea     rdx, [rbp+390h+var_3F0]
0x1800177bf  mov     rax, [rax+8]
0x1800177c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800177c8  nop
0x1800177c9  lea     rdx, [rbp+390h+var_410]
0x1800177cd  lea     rcx, [rbp+390h+var_3F0]
0x1800177d1  call    ?begin@?$Enumerable@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Collections@@QEBA?AV?$EnumerableIterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Private@2@XZ; Collections::Enumerable<std::wstring>::begin(void)
0x1800177d6  nop
0x1800177d7  lea     rdx, [rbp+390h+var_3B0]
0x1800177db  call    ?end@?$Enumerable@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Collections@@QEBA?AV?$EnumerableIterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Private@2@XZ; Collections::Enumerable<std::wstring>::end(void)
0x1800177e0  nop
0x1800177e1  mov     rcx, [rbp+390h+var_410]
0x1800177e5  cmp     rcx, [rbp+390h+var_3B0]
0x1800177e9  jz      loc_180017C5A
0x1800177ef  mov     rax, [rcx]
0x1800177f2  mov     rax, [rax+10h]
0x1800177f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800177fb  mov     rbx, rax
0x1800177fe  cmp     qword ptr [rax+18h], 7
0x180017803  jbe     short loc_180017808
0x180017805  mov     rax, [rax]
0x180017808  mov     [rbp+390h+var_3C0], rax
0x18001780c  mov     rax, [rbx+10h]
0x180017810  mov     [rbp+390h+var_3B8], rax
0x180017814  lea     rdx, [rbp+390h+var_3C0]
0x180017818  lea     rcx, [rbp+390h+var_270]
0x18001781f  call    ?FromPlatformIndependentString@appids@@YA?AVAnyRuntimeApp@1@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; appids::FromPlatformIndependentString(std::basic_string_view<ushort>)
0x180017824  nop
0x180017825  mov     rcx, [rsp+490h+var_460]
0x18001782a  mov     rax, [rcx]
0x18001782d  mov     r8, rbx
0x180017830  lea     rdx, [rsp+490h+var_438]
0x180017835  mov     rax, [rax+18h]
0x180017839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001783e  nop
0x18001783f  mov     rcx, [rax]
0x180017842  mov     rax, [rcx]
0x180017845  lea     rdx, [rsp+490h+var_468]
0x18001784a  mov     rax, [rax+38h]
0x18001784e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017853  nop
0x180017854  mov     rcx, [rsp+490h+var_438]
0x180017859  test    rcx, rcx
0x18001785c  jz      short loc_18001786C
0x18001785e  mov     rax, [rcx]
0x180017861  mov     edx, r13d
0x180017864  mov     rax, [rax]
0x180017867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001786c  mov     rdi, [rsp+490h+var_468]
0x180017871  test    rdi, rdi
0x180017874  jz      loc_180017C10
0x18001787a  mov     rax, [rdi]
0x18001787d  mov     rbx, [rax+18h]
0x180017881  xorps   xmm0, xmm0
0x180017884  movups  [rbp+390h+var_290], xmm0
0x18001788b  mov     [rbp+390h+var_280], r15
0x180017892  mov     [rbp+390h+var_278], r15
0x180017899  mov     r8d, 0Bh
0x18001789f  lea     rdx, aDisplayname; "DisplayName"
0x1800178a6  lea     rcx, [rbp+390h+var_290]
0x1800178ad  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800178b2  nop
0x1800178b3  lea     r8, [rbp+390h+var_290]
0x1800178ba  lea     rdx, [rsp+490h+var_430]
0x1800178bf  mov     rcx, rdi
0x1800178c2  mov     rax, rbx
0x1800178c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178ca  nop
0x1800178cb  mov     rcx, [rax]
0x1800178ce  mov     rax, [rcx]
0x1800178d1  lea     rdx, [rbp+390h+var_F0]
0x1800178d8  mov     rax, [rax+28h]
0x1800178dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178e1  nop
0x1800178e2  mov     rcx, [rsp+490h+var_430]
0x1800178e7  test    rcx, rcx
0x1800178ea  jz      short loc_1800178FB
0x1800178ec  mov     rax, [rcx]
0x1800178ef  mov     edx, r13d
0x1800178f2  mov     rax, [rax]
0x1800178f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178fa  nop
0x1800178fb  lea     rcx, [rbp+390h+var_290]
0x180017902  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017907  mov     rcx, [rbp+390h+var_C8]
0x18001790e  test    rcx, rcx
0x180017911  jz      loc_180017C01
0x180017917  lea     rax, [rbp+390h+var_388]
0x18001791b  mov     [rbp+390h+var_398], rax
0x18001791f  mov     rdx, rcx
0x180017922  lea     rcx, [rbp+390h+var_388]
0x180017926  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001792b  mov     rbx, rax
0x18001792e  lea     rdx, [rbp+390h+var_270]; struct appids::AnyRuntimeApp *
0x180017935  lea     rcx, [rbp+390h+var_350]; this
0x180017939  call    ??0AnyRuntimeApp@appids@@QEAA@AEBV01@@Z; appids::AnyRuntimeApp::AnyRuntimeApp(appids::AnyRuntimeApp const &)
0x18001793e  nop
0x18001793f  mov     r8, rbx
0x180017942  mov     rdx, rax
0x180017945  lea     rcx, [rbp+390h+var_1E0]
0x18001794c  call    ??0AppInfo@AppInventory@AppLimits@wpc@@QEAA@VAnyRuntimeApp@appids@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; wpc::AppLimits::AppInventory::AppInfo::AppInfo(appids::AnyRuntimeApp,std::wstring)
0x180017951  nop
0x180017952  mov     rdi, [rsp+490h+var_468]
0x180017957  mov     rax, [rdi]
0x18001795a  mov     rbx, [rax+18h]
0x18001795e  xorps   xmm0, xmm0
0x180017961  movups  [rbp+390h+var_300], xmm0
0x180017968  mov     [rbp+390h+var_2F0], r15
0x18001796f  mov     [rbp+390h+var_2E8], r15
0x180017976  mov     r8d, 0Dh
0x18001797c  lea     rdx, aFirstusedtime; "FirstUsedTime"
0x180017983  lea     rcx, [rbp+390h+var_300]
0x18001798a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001798f  nop
0x180017990  lea     r8, [rbp+390h+var_300]
0x180017997  lea     rdx, [rsp+490h+var_428]
0x18001799c  mov     rcx, rdi
0x18001799f  mov     rax, rbx
0x1800179a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179a7  nop
0x1800179a8  mov     rcx, [rax]
0x1800179ab  mov     rax, [rcx]
0x1800179ae  lea     rdx, [rbp+390h+var_2E0]
0x1800179b5  mov     rax, [rax+28h]
0x1800179b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179be  nop
0x1800179bf  mov     rcx, [rsp+490h+var_428]
0x1800179c4  test    rcx, rcx
0x1800179c7  jz      short loc_1800179D8
0x1800179c9  mov     rax, [rcx]
0x1800179cc  mov     edx, r13d
0x1800179cf  mov     rax, [rax]
0x1800179d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179d7  nop
0x1800179d8  lea     rcx, [rbp+390h+var_300]
0x1800179df  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800179e4  mov     rcx, [rbp+390h+var_2B8]
0x1800179eb  test    rcx, rcx
0x1800179ee  jz      short loc_180017A1D
0x1800179f0  mov     rdx, rcx
0x1800179f3  lea     rcx, [rbp+390h+var_170]
0x1800179fa  cmp     [rbp+390h+var_150], r15b
0x180017a01  jz      short loc_180017A0A
0x180017a03  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180017a08  jmp     short loc_180017A16
0x180017a0a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180017a0f  mov     [rbp+390h+var_150], r13b
0x180017a16  mov     rcx, [rbp+390h+var_2B8]
0x180017a1d  test    rcx, rcx
0x180017a20  jz      short loc_180017A27
0x180017a22  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017a27  mov     rdi, [rsp+490h+var_468]
0x180017a2c  mov     rax, [rdi]
0x180017a2f  mov     rbx, [rax+18h]
0x180017a33  xorps   xmm0, xmm0
0x180017a36  movups  [rbp+390h+var_300], xmm0
0x180017a3d  mov     [rbp+390h+var_2F0], r15
0x180017a44  mov     [rbp+390h+var_2E8], r15
  ... truncated ...
```
