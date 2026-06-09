# CCodecFactory::HrUpdateDisabledComponents(void)

- ea: `0x180043568`
- end: `0x180043f73`
- name: `?HrUpdateDisabledComponents@CCodecFactory@@SAJXZ`
- size: `2571`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800404fc`
- `0x1800c9504`

## callees

- `0x18002f260`
- `0x18002f820`
- `0x180043568`
- `0x180043f7c`
- `0x180043fa8`
- `0x1800442f0`
- `0x180044790`
- `0x180052a04`
- `0x180052ac8`
- `0x1800bb784`
- `0x1800e2b48`
- `0x1800e2f90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043891`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043891`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800435a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800435a0`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800439b8`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800439b8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180043996`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180043996`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004389f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043bb7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043bc8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043bdd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004389f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043bb7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043bc8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043bdd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004378d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043943`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004378d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043943`

## pseudocode

```c
__int64 CCodecFactory::HrUpdateDisabledComponents(void)
{
  HKEY v0; // rdi
  _QWORD *v1; // rax
  _DWORD *v2; // r14
  void *v3; // rbx
  void *v4; // r12
  _QWORD *v5; // rax
  _DWORD *v6; // r15
  _QWORD *v7; // rax
  _DWORD *v8; // r13
  _QWORD *v9; // rax
  int v10; // esi
  _QWORD *v11; // rax
  unsigned int v12; // r12d
  unsigned int i; // ebx
  unsigned int v14; // r12d
  unsigned int j; // ebx
  unsigned int v16; // r12d
  unsigned int k; // ebx
  _QWORD *v18; // rsi
  unsigned int v19; // r12d
  unsigned int m; // ebx
  _QWORD *v21; // rsi
  unsigned int v22; // r12d
  unsigned int n; // ebx
  int v24; // eax
  DWORD v25; // r12d
  WCHAR *v26; // rax
  HKEY v27; // rbx
  __int64 v28; // rdx
  __int64 v29; // r8
  const wchar_t *v30; // rcx
  __int64 v31; // rax
  WCHAR *v32; // r9
  __int64 v33; // rdx
  WCHAR *v34; // rcx
  HRESULT v36; // eax
  unsigned int v37; // edx
  int v38; // eax
  unsigned int v39; // r8d
  _OWORD *v40; // r9
  unsigned int v41; // r8d
  _OWORD *v42; // r9
  unsigned int v43; // r8d
  _OWORD *v44; // r9
  unsigned int v45; // r8d
  _OWORD *v46; // r9
  unsigned int v47; // r8d
  _OWORD *v48; // r9
  _QWORD *v49; // [rsp+40h] [rbp-C0h]
  _QWORD *v50; // [rsp+48h] [rbp-B8h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v53; // [rsp+60h] [rbp-A0h] BYREF
  GUID iid; // [rsp+68h] [rbp-98h] BYREF
  WCHAR SubKey[128]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Name[128]; // [rsp+180h] [rbp+80h] BYREF

  v0 = 0;
  EnterCriticalSection(&CCodecFactory::s_ComponentsLock);
  v1 = operator new(0x20u);
  v2 = v1;
  if ( !v1 )
  {
    v10 = -2147024882;
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(-2147024882);
    goto LABEL_47;
  }
  *v1 = 0;
  v3 = 0;
  v1[1] = 0;
  v4 = 0;
  v1[2] = 0;
  *((_DWORD *)v1 + 6) = 0;
  v5 = operator new(0x20u);
  v6 = v5;
  if ( !v5 )
  {
    v8 = 0;
    v10 = -2147024882;
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(-2147024882);
    v6 = 0;
    goto LABEL_39;
  }
  *v5 = 0;
  v5[1] = 0;
  v5[2] = 0;
  *((_DWORD *)v5 + 6) = 0;
  v7 = operator new(0x20u);
  v8 = v7;
  if ( !v7 )
  {
    v10 = -2147024882;
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(-2147024882);
    v8 = 0;
    goto LABEL_39;
  }
  *v7 = 0;
  v7[1] = 0;
  v7[2] = 0;
  *((_DWORD *)v7 + 6) = 0;
  v9 = operator new(0x20u);
  v49 = v9;
  v3 = v9;
  if ( !v9 )
  {
    v10 = -2147024882;
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(-2147024882);
    v3 = 0;
    goto LABEL_39;
  }
  *v9 = 0;
  v9[1] = 0;
  v9[2] = 0;
  *((_DWORD *)v9 + 6) = 0;
  v11 = operator new(0x20u);
  v50 = v11;
  if ( !v11 )
  {
    v10 = -2147024882;
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(-2147024882);
    goto LABEL_39;
  }
  *v11 = 0;
  v11[1] = 0;
  v11[2] = 0;
  *((_DWORD *)v11 + 6) = 0;
  CCodecInfo::PopulateDisabledBuiltInComponents(1, v2);
  v12 = v2[6];
  for ( i = 0; i < v12; ++i )
  {
    v47 = dword_180265FE8 + 1;
    if ( dword_180265FE8 + 1 < (unsigned int)dword_180265FE8 )
    {
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(-2147024362);
      v10 = -2147024362;
LABEL_160:
      if ( (_DWORD)g_doStackCaptures )
        goto LABEL_151;
      goto LABEL_38;
    }
    v48 = *(_OWORD **)(*(_QWORD *)v2 + 8LL * i);
    if ( v47 > dword_180265FE4 )
    {
      v10 = DynArrayImpl<0>::AddMultipleAndSet(&CCodecFactory::s_DisabledComponents, 16, 1, v48);
      if ( v10 < 0 )
      {
        if ( (_DWORD)g_doStackCaptures )
          DoStackCapture(v10);
        goto LABEL_160;
      }
    }
    else
    {
      *(_OWORD *)(CCodecFactory::s_DisabledComponents + 16LL * (unsigned int)dword_180265FE8) = *v48;
      dword_180265FE8 = v47;
    }
  }
  CCodecInfo::PopulateDisabledBuiltInComponents(2, v6);
  v14 = v6[6];
  for ( j = 0; j < v14; ++j )
  {
    v45 = dword_180265FE8 + 1;
    if ( dword_180265FE8 + 1 < (unsigned int)dword_180265FE8 )
    {
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(-2147024362);
      v10 = -2147024362;
LABEL_155:
      if ( (_DWORD)g_doStackCaptures )
        goto LABEL_151;
      goto LABEL_38;
    }
    v46 = *(_OWORD **)(*(_QWORD *)v6 + 8LL * j);
    if ( v45 > dword_180265FE4 )
    {
      v10 = DynArrayImpl<0>::AddMultipleAndSet(&CCodecFactory::s_DisabledComponents, 16, 1, v46);
      if ( v10 < 0 )
      {
        if ( (_DWORD)g_doStackCaptures )
          DoStackCapture(v10);
        goto LABEL_155;
      }
    }
    else
    {
      *(_OWORD *)(CCodecFactory::s_DisabledComponents + 16LL * (unsigned int)dword_180265FE8) = *v46;
      dword_180265FE8 = v45;
    }
  }
  CMetadataHandlerInfo::PopulateDisabledBuiltInComponents(8, v8);
  v16 = v8[6];
  for ( k = 0; k < v16; ++k )
  {
    v41 = dword_180265FE8 + 1;
    if ( dword_180265FE8 + 1 < (unsigned int)dword_180265FE8 )
    {
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(-2147024362);
      v10 = -2147024362;
LABEL_145:
      if ( (_DWORD)g_doStackCaptures )
        goto LABEL_151;
      goto LABEL_38;
    }
    v42 = *(_OWORD **)(*(_QWORD *)v8 + 8LL * k);
    if ( v41 > dword_180265FE4 )
    {
      v10 = DynArrayImpl<0>::AddMultipleAndSet(&CCodecFactory::s_DisabledComponents, 16, 1, v42);
      if ( v10 < 0 )
      {
        if ( (_DWORD)g_doStackCaptures )
          DoStackCapture(v10);
        goto LABEL_145;
      }
    }
    else
    {
      *(_OWORD *)(CCodecFactory::s_DisabledComponents + 16LL * (unsigned int)dword_180265FE8) = *v42;
      dword_180265FE8 = v41;
    }
  }
  v18 = v49;
  CMetadataHandlerInfo::PopulateDisabledBuiltInComponents(16, v49);
  v19 = *((_DWORD *)v49 + 6);
  for ( m = 0; m < v19; ++m )
  {
    v39 = dword_180265FE8 + 1;
    if ( dword_180265FE8 + 1 < (unsigned int)dword_180265FE8 )
    {
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(-2147024362);
      v10 = -2147024362;
LABEL_140:
      if ( (_DWORD)g_doStackCaptures )
        goto LABEL_151;
      goto LABEL_38;
    }
    v40 = *(_OWORD **)(*v18 + 8LL * m);
    if ( v39 > dword_180265FE4 )
    {
      v10 = DynArrayImpl<0>::AddMultipleAndSet(&CCodecFactory::s_DisabledComponents, 16, 1, v40);
      if ( v10 < 0 )
      {
        if ( (_DWORD)g_doStackCaptures )
          DoStackCapture(v10);
        goto LABEL_140;
      }
      v18 = v49;
    }
    else
    {
      *(_OWORD *)(CCodecFactory::s_DisabledComponents + 16LL * (unsigned int)dword_180265FE8) = *v40;
      dword_180265FE8 = v39;
    }
  }
  v21 = v50;
  CFormatConverterInfo::PopulateDisabledBuiltInComponents(v50);
  v22 = *((_DWORD *)v50 + 6);
  for ( n = 0; ; ++n )
  {
    if ( n >= v22 )
    {
      v24 = RegKey::BuildImagingCategoryKey(&CLSID_WICImagingCategories, SubKey, 0x80u);
      v25 = 0;
      v10 = v24;
      if ( v24 < 0 )
      {
        if ( !(_DWORD)g_doStackCaptures )
          goto LABEL_38;
      }
      else
      {
        hKey = 0;
        if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &hKey) )
          goto LABEL_38;
        v0 = hKey;
        v26 = SubKey;
        v27 = 0;
        v28 = 128;
        do
        {
          if ( !*v26 )
            break;
          ++v26;
          --v28;
        }
        while ( v28 );
        v10 = v28 == 0 ? 0x80070057 : 0;
        v29 = (128 - v28) & -(__int64)(v28 != 0);
        if ( v28 )
        {
          v30 = L"\\Disabled";
          v31 = 2147483646;
          v32 = &SubKey[v29];
          v33 = 128 - v29;
          if ( 128 != v29 )
          {
            do
            {
              if ( !v31 )
                break;
              if ( !*v30 )
                break;
              *v32++ = *v30++;
              --v31;
              --v33;
            }
            while ( v33 );
          }
          v34 = v32 - 1;
          v10 = v33 == 0 ? 0x8007007A : 0;
          v24 = v10;
          if ( v33 )
            v34 = v32;
          *v34 = 0;
          if ( v33 )
          {
LABEL_37:
            v10 = v24;
            if ( v24 >= 0 )
            {
              hKey = 0;
              if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &hKey) )
              {
                v27 = hKey;
                v53 = hKey;
                while ( 1 )
                {
                  ftLastWriteTime = 0;
                  LODWORD(hKey) = 128;
                  if ( RegEnumKeyExW(v27, v25, Name, (LPDWORD)&hKey, 0, 0, 0, &ftLastWriteTime) )
                    break;
                  iid = 0;
                  v36 = IIDFromString(Name, &iid);
                  v10 = v36;
                  if ( v36 < 0 )
                  {
                    if ( (_DWORD)g_doStackCaptures )
                      DoStackCapture(v36);
                    RegKey::Close((RegKey *)&v53);
                    goto LABEL_38;
                  }
                  v37 = dword_180265FE8 + 1;
                  if ( dword_180265FE8 + 1 < (unsigned int)dword_180265FE8 )
                  {
                    if ( (_DWORD)g_doStackCaptures )
                      DoStackCapture(-2147024362);
                    v10 = -2147024362;
LABEL_123:
                    if ( (_DWORD)g_doStackCaptures )
                      DoStackCapture(v10);
                    goto LABEL_83;
                  }
                  if ( v37 > dword_180265FE4 )
                  {
                    ftLastWriteTime = (struct _FILETIME)&iid;
                    v38 = DynArrayImpl<0>::Grow(
                            &CCodecFactory::s_DisabledComponents,
                            0x10u,
                            1,
                            0,
                            (unsigned __int64 *)&ftLastWriteTime);
                    v10 = v38;
                    if ( v38 < 0 )
                    {
                      if ( (_DWORD)g_doStackCaptures )
                        DoStackCapture(v38);
                    }
                    else
                    {
                      *(_OWORD *)((unsigned int)(16 * dword_180265FE8++) + CCodecFactory::s_DisabledComponents) = *(_OWORD *)*(_QWORD *)&ftLastWriteTime;
                    }
                    if ( v10 < 0 )
                      goto LABEL_123;
                  }
                  else
                  {
                    v10 = 0;
                    *(GUID *)(CCodecFactory::s_DisabledComponents + 16LL * (unsigned int)dword_180265FE8) = iid;
                    dword_180265FE8 = v37;
                  }
                  ++v25;
                }
                if ( v27 )
                {
                  RegCloseKey(v27);
                  v27 = 0;
                }
              }
              if ( v0 )
              {
                RegCloseKey(v0);
                v0 = 0;
              }
LABEL_83:
              if ( v27 )
                RegCloseKey(v27);
            }
            goto LABEL_38;
          }
        }
        else
        {
          v24 = -2147024809;
        }
        if ( !(_DWORD)g_doStackCaptures )
          goto LABEL_37;
      }
      DoStackCapture(v24);
      goto LABEL_38;
    }
    v43 = dword_180265FE8 + 1;
    if ( dword_180265FE8 + 1 < (unsigned int)dword_180265FE8 )
      break;
    v44 = *(_OWORD **)(*v21 + 8LL * n);
    if ( v43 > dword_180265FE4 )
    {
      v10 = DynArrayImpl<0>::AddMultipleAndSet(&CCodecFactory::s_DisabledComponents, 16, 1, v44);
      if ( v10 < 0 )
      {
        if ( (_DWORD)g_doStackCaptures )
          DoStackCapture(v10);
        goto LABEL_150;
      }
      v21 = v50;
    }
    else
    {
      *(_OWORD *)(CCodecFactory::s_DisabledComponents + 16LL * (unsigned int)dword_180265FE8) = *v44;
      dword_180265FE8 = v43;
    }
  }
  if ( (_DWORD)g_doStackCaptures )
    DoStackCapture(-2147024362);
  v10 = -2147024362;
LABEL_150:
  if ( (_DWORD)g_doStackCaptures )
LABEL_151:
    DoStackCapture(v10);
LABEL_38:
  v3 = v49;
  v4 = v50;
LABEL_39:
  DynArray<IWICMetadataReaderInfo *,0>::`scalar deleting destructor'(v2);
  if ( v6 )
    DynArray<IWICMetadataReaderInfo *,0>::`scalar deleting destructor'(v6);
  if ( v8 )
    DynArray<IWICMetadataReaderInfo *,0>::`scalar deleting destructor'(v8);
  if ( v3 )
    DynArray<IWICMetadataReaderInfo *,0>::`scalar deleting destructor'(v3);
  if ( v4 )
    DynArray<IWICMetadataReaderInfo *,0>::`scalar deleting destructor'(v4);
LABEL_47:
  LeaveCriticalSection(&CCodecFactory::s_ComponentsLock);
  if ( v0 )
    RegCloseKey(v0);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180043568  push    rbp
0x18004356a  push    rbx
0x18004356b  push    rsi
0x18004356c  push    rdi
0x18004356d  push    r12
0x18004356f  push    r13
0x180043571  push    r14
0x180043573  push    r15
0x180043575  lea     rbp, [rsp-198h]
0x18004357d  sub     rsp, 298h
0x180043584  mov     rax, cs:__security_cookie
0x18004358b  xor     rax, rsp
0x18004358e  mov     [rbp+1D0h+var_50], rax
0x180043595  xor     esi, esi
0x180043597  lea     rcx, ?s_ComponentsLock@CCodecFactory@@2VCCriticalSection@@A; lpCriticalSection
0x18004359e  mov     edi, esi
0x1800435a0  call    cs:__imp_EnterCriticalSection
0x1800435a6  lea     r13d, [rsi+20h]
0x1800435aa  mov     ecx, r13d; Size
0x1800435ad  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800435b2  mov     r14, rax
0x1800435b5  test    rax, rax
0x1800435b8  jz      loc_180043641
0x1800435be  mov     ecx, r13d; Size
0x1800435c1  mov     [rax], rsi
0x1800435c4  mov     ebx, esi
0x1800435c6  mov     [rax+8], rsi
0x1800435ca  mov     r12d, esi
0x1800435cd  mov     [rax+10h], rsi
0x1800435d1  mov     [rax+18h], esi
0x1800435d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800435d9  mov     r15, rax
0x1800435dc  test    rax, rax
0x1800435df  jz      loc_1800438F4
0x1800435e5  mov     ecx, r13d; Size
0x1800435e8  mov     [rax], rsi
0x1800435eb  mov     [rax+8], rsi
0x1800435ef  mov     [rax+10h], rsi
0x1800435f3  mov     [rax+18h], esi
0x1800435f6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800435fb  mov     r13, rax
0x1800435fe  test    rax, rax
0x180043601  jz      short loc_180043662
0x180043603  lea     ecx, [rsi+20h]; Size
0x180043606  mov     [rax], rsi
0x180043609  mov     [rax+8], rsi
0x18004360d  mov     [rax+10h], rsi
0x180043611  mov     [rax+18h], esi
0x180043614  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180043619  mov     [rsp+2D0h+var_290], rax
0x18004361e  mov     rbx, rax
0x180043621  test    rax, rax
0x180043624  jnz     short loc_18004367E
0x180043626  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x18004362c  mov     esi, 8007000Eh
0x180043631  jz      short loc_18004363A
0x180043633  mov     ecx, esi; int
0x180043635  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18004363a  xor     ebx, ebx
0x18004363c  jmp     loc_180043866
0x180043641  xor     r14d, r14d
0x180043644  mov     esi, 8007000Eh
0x180043649  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180043650  jz      loc_18004388A
0x180043656  mov     ecx, esi; int
0x180043658  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18004365d  jmp     loc_18004388A
0x180043662  cmp     cs:?g_doStackCaptures@@3HA, ebx; int g_doStackCaptures
0x180043668  mov     esi, 8007000Eh
0x18004366d  jz      short loc_180043676
0x18004366f  mov     ecx, esi; int
0x180043671  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180043676  xor     r13d, r13d
0x180043679  jmp     loc_180043866
0x18004367e  mov     ecx, 20h ; ' '; Size
0x180043683  mov     [rax], rsi
0x180043686  mov     [rax+8], rsi
0x18004368a  mov     [rax+10h], rsi
0x18004368e  mov     [rax+18h], esi
0x180043691  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180043696  mov     [rsp+2D0h+var_288], rax
0x18004369b  test    rax, rax
0x18004369e  jz      loc_1800438CA
0x1800436a4  mov     rdx, r14
0x1800436a7  mov     [rax], rsi
0x1800436aa  mov     ecx, 1
0x1800436af  mov     [rax+8], rsi
0x1800436b3  mov     [rax+10h], rsi
0x1800436b7  mov     [rax+18h], esi
0x1800436ba  call    ?PopulateDisabledBuiltInComponents@CCodecInfo@@SAJW4WICComponentType@@PEAV?$DynArray@PEBU_GUID@@$0A@@@@Z; CCodecInfo::PopulateDisabledBuiltInComponents(WICComponentType,DynArray<_GUID const *,0> *)
0x1800436bf  mov     r12d, [r14+18h]
0x1800436c3  mov     ebx, esi
0x1800436c5  cmp     ebx, r12d
0x1800436c8  jb      loc_180043BE8
0x1800436ce  mov     rdx, r15
0x1800436d1  mov     ecx, 2
0x1800436d6  call    ?PopulateDisabledBuiltInComponents@CCodecInfo@@SAJW4WICComponentType@@PEAV?$DynArray@PEBU_GUID@@$0A@@@@Z; CCodecInfo::PopulateDisabledBuiltInComponents(WICComponentType,DynArray<_GUID const *,0> *)
0x1800436db  mov     r12d, [r15+18h]
0x1800436df  mov     ebx, esi
0x1800436e1  cmp     ebx, r12d
0x1800436e4  jb      loc_180043B62
0x1800436ea  mov     rdx, r13
0x1800436ed  mov     ecx, 8
0x1800436f2  call    ?PopulateDisabledBuiltInComponents@CMetadataHandlerInfo@@SAJW4WICComponentType@@PEAV?$DynArray@PEBU_GUID@@$0A@@@@Z; CMetadataHandlerInfo::PopulateDisabledBuiltInComponents(WICComponentType,DynArray<_GUID const *,0> *)
0x1800436f7  mov     r12d, [r13+18h]
0x1800436fb  mov     ebx, esi
0x1800436fd  cmp     ebx, r12d
0x180043700  jb      loc_180043ACB
0x180043706  mov     rsi, [rsp+2D0h+var_290]
0x18004370b  mov     ecx, 10h
0x180043710  mov     rdx, rsi
0x180043713  call    ?PopulateDisabledBuiltInComponents@CMetadataHandlerInfo@@SAJW4WICComponentType@@PEAV?$DynArray@PEBU_GUID@@$0A@@@@Z; CMetadataHandlerInfo::PopulateDisabledBuiltInComponents(WICComponentType,DynArray<_GUID const *,0> *)
0x180043718  mov     r12d, [rsi+18h]
0x18004371c  xor     eax, eax
0x18004371e  mov     ebx, eax
0x180043720  cmp     ebx, r12d
0x180043723  jb      loc_180043A7D
0x180043729  mov     rsi, [rsp+2D0h+var_288]
0x18004372e  mov     rcx, rsi
0x180043731  call    ?PopulateDisabledBuiltInComponents@CFormatConverterInfo@@SAJPEAV?$DynArray@PEBU_GUID@@$0A@@@@Z; CFormatConverterInfo::PopulateDisabledBuiltInComponents(DynArray<_GUID const *,0> *)
0x180043736  mov     r12d, [rsi+18h]
0x18004373a  xor     eax, eax
0x18004373c  mov     ebx, eax
0x18004373e  cmp     ebx, r12d
0x180043741  jb      loc_180043B16
0x180043747  mov     r8d, 80h; unsigned int
0x18004374d  lea     rdx, [rbp+1D0h+SubKey]; unsigned __int16 *
0x180043751  lea     rcx, CLSID_WICImagingCategories; struct _GUID *
0x180043758  call    ?BuildImagingCategoryKey@RegKey@@SAJAEBU_GUID@@PEAGI@Z; RegKey::BuildImagingCategoryKey(_GUID const &,ushort *,uint)
0x18004375d  xor     r12d, r12d
0x180043760  mov     esi, eax
0x180043762  test    eax, eax
0x180043764  js      loc_180043CDD
0x18004376a  lea     rax, [rsp+2D0h+hKey]
0x18004376f  mov     [rsp+2D0h+hKey], r12
0x180043774  mov     r9d, 20019h; samDesired
0x18004377a  mov     [rsp+2D0h+phkResult], rax; phkResult
0x18004377f  xor     r8d, r8d; ulOptions
0x180043782  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x180043786  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18004378d  call    cs:__imp_RegOpenKeyExW
0x180043793  test    eax, eax
0x180043795  jnz     loc_18004385C
0x18004379b  mov     rdi, [rsp+2D0h+hKey]
0x1800437a0  lea     rax, [rbp+1D0h+SubKey]
0x1800437a4  mov     r9d, 80h
0x1800437aa  mov     rbx, r12
0x1800437ad  mov     edx, r9d
0x1800437b0  cmp     [rax], r12w
0x1800437b4  jz      short loc_1800437C0
0x1800437b6  add     rax, 2
0x1800437ba  sub     rdx, 1
0x1800437be  jnz     short loc_1800437B0
0x1800437c0  mov     rax, rdx
0x1800437c3  mov     rcx, r9
0x1800437c6  neg     rax
0x1800437c9  mov     rax, rdx
0x1800437cc  sbb     esi, esi
0x1800437ce  sub     rcx, rdx
0x1800437d1  not     esi
0x1800437d3  and     esi, 80070057h
0x1800437d9  neg     rax
0x1800437dc  sbb     r8, r8
0x1800437df  and     r8, rcx
0x1800437e2  test    rdx, rdx
0x1800437e5  jz      loc_180043CF6
0x1800437eb  mov     rdx, r9
0x1800437ee  lea     rcx, aDisabled; "\\Disabled"
0x1800437f5  lea     r9, [rbp+1D0h+SubKey]
0x1800437f9  mov     eax, 7FFFFFFEh
0x1800437fe  lea     r9, [r9+r8*2]
0x180043802  sub     rdx, r8
0x180043805  jz      short loc_18004382B
0x180043807  test    rax, rax
0x18004380a  jz      short loc_18004382B
0x18004380c  movzx   r8d, word ptr [rcx]
0x180043810  test    r8w, r8w
0x180043814  jz      short loc_18004382B
0x180043816  mov     [r9], r8w
0x18004381a  add     rcx, 2
0x18004381e  add     r9, 2
0x180043822  dec     rax
0x180043825  sub     rdx, 1
0x180043829  jnz     short loc_180043807
0x18004382b  mov     rax, rdx
0x18004382e  lea     rcx, [r9-2]
0x180043832  neg     rax
0x180043835  sbb     esi, esi
0x180043837  not     esi
0x180043839  and     esi, 8007007Ah
0x18004383f  test    rdx, rdx
0x180043842  mov     eax, esi
0x180043844  cmovnz  rcx, r9
0x180043848  mov     [rcx], r12w
0x18004384c  jz      loc_180043CF8
0x180043852  mov     esi, eax
0x180043854  test    eax, eax
0x180043856  jns     loc_180043920
0x18004385c  mov     rbx, [rsp+2D0h+var_290]
0x180043861  mov     r12, [rsp+2D0h+var_288]
0x180043866  mov     rcx, r14; Block
0x180043869  call    ??_G?$DynArray@PEAUIWICMetadataReaderInfo@@$0A@@@QEAAPEAXI@Z; DynArray<IWICMetadataReaderInfo *,0>::`scalar deleting destructor'(uint)
0x18004386e  test    r15, r15
0x180043871  jnz     loc_180043A05
0x180043877  test    r13, r13
0x18004387a  jnz     loc_180043913
0x180043880  test    rbx, rbx
0x180043883  jnz     short loc_1800438EA
0x180043885  test    r12, r12
0x180043888  jnz     short loc_1800438E0
0x18004388a  lea     rcx, ?s_ComponentsLock@CCodecFactory@@2VCCriticalSection@@A; lpCriticalSection
0x180043891  call    cs:__imp_LeaveCriticalSection
0x180043897  test    rdi, rdi
0x18004389a  jz      short loc_1800438A5
0x18004389c  mov     rcx, rdi; hKey
0x18004389f  call    cs:__imp_RegCloseKey
0x1800438a5  mov     eax, esi
0x1800438a7  mov     rcx, [rbp+1D0h+var_50]
0x1800438ae  xor     rcx, rsp; StackCookie
0x1800438b1  call    __security_check_cookie
0x1800438b6  add     rsp, 298h
0x1800438bd  pop     r15
0x1800438bf  pop     r14
0x1800438c1  pop     r13
0x1800438c3  pop     r12
0x1800438c5  pop     rdi
0x1800438c6  pop     rsi
0x1800438c7  pop     rbx
0x1800438c8  pop     rbp
0x1800438c9  retn
0x1800438ca  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800438d0  mov     esi, 8007000Eh
0x1800438d5  jz      short loc_180043866
0x1800438d7  mov     ecx, esi; int
0x1800438d9  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800438de  jmp     short loc_180043866
0x1800438e0  mov     rcx, r12; Block
0x1800438e3  call    ??_G?$DynArray@PEAUIWICMetadataReaderInfo@@$0A@@@QEAAPEAXI@Z; DynArray<IWICMetadataReaderInfo *,0>::`scalar deleting destructor'(uint)
0x1800438e8  jmp     short loc_18004388A
0x1800438ea  mov     rcx, rbx; Block
0x1800438ed  call    ??_G?$DynArray@PEAUIWICMetadataReaderInfo@@$0A@@@QEAAPEAXI@Z; DynArray<IWICMetadataReaderInfo *,0>::`scalar deleting destructor'(uint)
0x1800438f2  jmp     short loc_180043885
0x1800438f4  cmp     cs:?g_doStackCaptures@@3HA, ebx; int g_doStackCaptures
0x1800438fa  mov     r13, rsi
0x1800438fd  mov     esi, 8007000Eh
0x180043902  jz      short loc_18004390B
0x180043904  mov     ecx, esi; int
0x180043906  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18004390b  xor     r15d, r15d
0x18004390e  jmp     loc_180043866
0x180043913  mov     rcx, r13; Block
0x180043916  call    ??_G?$DynArray@PEAUIWICMetadataReaderInfo@@$0A@@@QEAAPEAXI@Z; DynArray<IWICMetadataReaderInfo *,0>::`scalar deleting destructor'(uint)
0x18004391b  jmp     loc_180043880
0x180043920  lea     rax, [rsp+2D0h+hKey]
0x180043925  mov     [rsp+2D0h+hKey], r12
0x18004392a  mov     r9d, 20019h; samDesired
0x180043930  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180043935  xor     r8d, r8d; ulOptions
0x180043938  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x18004393c  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180043943  call    cs:__imp_RegOpenKeyExW
0x180043949  test    eax, eax
0x18004394b  jnz     loc_180043BC0
0x180043951  mov     rbx, [rsp+2D0h+hKey]
0x180043956  xor     r8d, r8d
0x180043959  mov     [rsp+2D0h+var_270], rbx
0x18004395e  lea     rax, [rsp+2D0h+ftLastWriteTime]
0x180043963  mov     qword ptr [rsp+2D0h+ftLastWriteTime.dwLowDateTime], r8
0x180043968  mov     [rsp+2D0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18004396d  lea     r9, [rsp+2D0h+hKey]; lpcchName
0x180043972  mov     [rsp+2D0h+lpcchClass], r8; lpcchClass
0x180043977  mov     edx, r12d; dwIndex
0x18004397a  mov     [rsp+2D0h+lpClass], r8; lpClass
0x18004397f  mov     rcx, rbx; hKey
0x180043982  mov     [rsp+2D0h+phkResult], r8; lpReserved
0x180043987  lea     r8, [rbp+1D0h+Name]; lpName
0x18004398e  mov     dword ptr [rsp+2D0h+hKey], 80h
0x180043996  call    cs:__imp_RegEnumKeyExW
0x18004399c  test    eax, eax
0x18004399e  jnz     loc_180043BAC
0x1800439a4  xorps   xmm0, xmm0
0x1800439a7  lea     rdx, [rsp+2D0h+iid]; lpiid
0x1800439ac  lea     rcx, [rbp+1D0h+Name]; lpsz
0x1800439b3  movups  xmmword ptr [rsp+2D0h+iid.Data1], xmm0
0x1800439b8  call    cs:__imp_IIDFromString
0x1800439be  xor     r8d, r8d
0x1800439c1  mov     esi, eax
0x1800439c3  test    eax, eax
0x1800439c5  js      loc_180043D89
0x1800439cb  mov     eax, cs:dword_180265FE8
0x1800439d1  lea     edx, [rax+1]
0x1800439d4  cmp     edx, eax
0x1800439d6  jb      loc_180043D4E
0x1800439dc  cmp     edx, cs:dword_180265FE4
0x1800439e2  ja      short loc_180043A12
0x1800439e4  movups  xmm0, xmmword ptr [rsp+2D0h+iid.Data1]
0x1800439e9  mov     ecx, eax
0x1800439eb  mov     esi, r8d
0x1800439ee  mov     rax, cs:?s_DisabledComponents@CCodecFactory@@0V?$DynArray@U_GUID@@$0A@@@A; DynArray<_GUID,0> CCodecFactory::s_DisabledComponents
0x1800439f5  add     rcx, rcx
  ... truncated ...
```
