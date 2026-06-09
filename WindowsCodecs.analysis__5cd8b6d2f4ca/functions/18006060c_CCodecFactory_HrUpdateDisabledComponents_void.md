# CCodecFactory::HrUpdateDisabledComponents(void)

- ea: `0x18006060c`
- end: `0x180061057`
- name: `?HrUpdateDisabledComponents@CCodecFactory@@SAJXZ`
- size: `2635`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180033260`
- `0x1800cb9ec`

## callees

- `0x180025cd8`
- `0x180025d9c`
- `0x18006060c`
- `0x180061060`
- `0x18006108c`
- `0x18006168c`
- `0x1800616c0`
- `0x180061a2c`
- `0x180061d70`
- `0x1800bd9d4`
- `0x1800e5a18`
- `0x1800e5e60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060941`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060941`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060644`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060644`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180060a84`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180060a84`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180060a5c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180060a5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060955`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060c89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060ca0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060cbb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060955`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060c89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060ca0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060cbb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060837`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060a03`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060837`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060a03`

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
    v47 = dword_18026A028 + 1;
    if ( dword_18026A028 + 1 < (unsigned int)dword_18026A028 )
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
    if ( v47 > dword_18026A024 )
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
      *(_OWORD *)(CCodecFactory::s_DisabledComponents + 16LL * (unsigned int)dword_18026A028) = *v48;
      dword_18026A028 = v47;
    }
  }
  CCodecInfo::PopulateDisabledBuiltInComponents(2, v6);
  v14 = v6[6];
  for ( j = 0; j < v14; ++j )
  {
    v45 = dword_18026A028 + 1;
    if ( dword_18026A028 + 1 < (unsigned int)dword_18026A028 )
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
    if ( v45 > dword_18026A024 )
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
      *(_OWORD *)(CCodecFactory::s_DisabledComponents + 16LL * (unsigned int)dword_18026A028) = *v46;
      dword_18026A028 = v45;
    }
  }
  CMetadataHandlerInfo::PopulateDisabledBuiltInComponents(8, v8);
  v16 = v8[6];
  for ( k = 0; k < v16; ++k )
  {
    v41 = dword_18026A028 + 1;
    if ( dword_18026A028 + 1 < (unsigned int)dword_18026A028 )
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
    if ( v41 > dword_18026A024 )
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
      *(_OWORD *)(CCodecFactory::s_DisabledComponents + 16LL * (unsigned int)dword_18026A028) = *v42;
      dword_18026A028 = v41;
    }
  }
  v18 = v49;
  CMetadataHandlerInfo::PopulateDisabledBuiltInComponents(16, v49);
  v19 = *((_DWORD *)v49 + 6);
  for ( m = 0; m < v19; ++m )
  {
    v39 = dword_18026A028 + 1;
    if ( dword_18026A028 + 1 < (unsigned int)dword_18026A028 )
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
    if ( v39 > dword_18026A024 )
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
      *(_OWORD *)(CCodecFactory::s_DisabledComponents + 16LL * (unsigned int)dword_18026A028) = *v40;
      dword_18026A028 = v39;
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
                  v37 = dword_18026A028 + 1;
                  if ( dword_18026A028 + 1 < (unsigned int)dword_18026A028 )
                  {
                    if ( (_DWORD)g_doStackCaptures )
                      DoStackCapture(-2147024362);
                    v10 = -2147024362;
LABEL_123:
                    if ( (_DWORD)g_doStackCaptures )
                      DoStackCapture(v10);
                    goto LABEL_83;
                  }
                  if ( v37 > dword_18026A024 )
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
                      *(_OWORD *)((unsigned int)(16 * dword_18026A028++) + CCodecFactory::s_DisabledComponents) = *(_OWORD *)*(_QWORD *)&ftLastWriteTime;
                    }
                    if ( v10 < 0 )
                      goto LABEL_123;
                  }
                  else
                  {
                    v10 = 0;
                    *(GUID *)(CCodecFactory::s_DisabledComponents + 16LL * (unsigned int)dword_18026A028) = iid;
                    dword_18026A028 = v37;
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
    v43 = dword_18026A028 + 1;
    if ( dword_18026A028 + 1 < (unsigned int)dword_18026A028 )
      break;
    v44 = *(_OWORD **)(*v21 + 8LL * n);
    if ( v43 > dword_18026A024 )
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
      *(_OWORD *)(CCodecFactory::s_DisabledComponents + 16LL * (unsigned int)dword_18026A028) = *v44;
      dword_18026A028 = v43;
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
0x18006060c  push    rbp
0x18006060e  push    rbx
0x18006060f  push    rsi
0x180060610  push    rdi
0x180060611  push    r12
0x180060613  push    r13
0x180060615  push    r14
0x180060617  push    r15
0x180060619  lea     rbp, [rsp-198h]
0x180060621  sub     rsp, 298h
0x180060628  mov     rax, cs:__security_cookie
0x18006062f  xor     rax, rsp
0x180060632  mov     [rbp+1D0h+var_50], rax
0x180060639  xor     esi, esi
0x18006063b  lea     rcx, ?s_ComponentsLock@CCodecFactory@@2VCCriticalSection@@A; lpCriticalSection
0x180060642  mov     edi, esi
0x180060644  call    cs:__imp_EnterCriticalSection
0x18006064b  nop     dword ptr [rax+rax+00h]
0x180060650  lea     r13d, [rsi+20h]
0x180060654  mov     ecx, r13d; Size
0x180060657  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006065c  mov     r14, rax
0x18006065f  test    rax, rax
0x180060662  jz      loc_1800606EB
0x180060668  mov     ecx, r13d; Size
0x18006066b  mov     [rax], rsi
0x18006066e  mov     ebx, esi
0x180060670  mov     [rax+8], rsi
0x180060674  mov     r12d, esi
0x180060677  mov     [rax+10h], rsi
0x18006067b  mov     [rax+18h], esi
0x18006067e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180060683  mov     r15, rax
0x180060686  test    rax, rax
0x180060689  jz      loc_1800609B4
0x18006068f  mov     ecx, r13d; Size
0x180060692  mov     [rax], rsi
0x180060695  mov     [rax+8], rsi
0x180060699  mov     [rax+10h], rsi
0x18006069d  mov     [rax+18h], esi
0x1800606a0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800606a5  mov     r13, rax
0x1800606a8  test    rax, rax
0x1800606ab  jz      short loc_18006070C
0x1800606ad  lea     ecx, [rsi+20h]; Size
0x1800606b0  mov     [rax], rsi
0x1800606b3  mov     [rax+8], rsi
0x1800606b7  mov     [rax+10h], rsi
0x1800606bb  mov     [rax+18h], esi
0x1800606be  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800606c3  mov     [rsp+2D0h+var_290], rax
0x1800606c8  mov     rbx, rax
0x1800606cb  test    rax, rax
0x1800606ce  jnz     short loc_180060728
0x1800606d0  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800606d6  mov     esi, 8007000Eh
0x1800606db  jz      short loc_1800606E4
0x1800606dd  mov     ecx, esi; int
0x1800606df  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800606e4  xor     ebx, ebx
0x1800606e6  jmp     loc_180060916
0x1800606eb  xor     r14d, r14d
0x1800606ee  mov     esi, 8007000Eh
0x1800606f3  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800606fa  jz      loc_18006093A
0x180060700  mov     ecx, esi; int
0x180060702  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180060707  jmp     loc_18006093A
0x18006070c  cmp     cs:?g_doStackCaptures@@3HA, ebx; int g_doStackCaptures
0x180060712  mov     esi, 8007000Eh
0x180060717  jz      short loc_180060720
0x180060719  mov     ecx, esi; int
0x18006071b  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180060720  xor     r13d, r13d
0x180060723  jmp     loc_180060916
0x180060728  mov     ecx, 20h ; ' '; Size
0x18006072d  mov     [rax], rsi
0x180060730  mov     [rax+8], rsi
0x180060734  mov     [rax+10h], rsi
0x180060738  mov     [rax+18h], esi
0x18006073b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180060740  mov     [rsp+2D0h+var_288], rax
0x180060745  test    rax, rax
0x180060748  jz      loc_180060987
0x18006074e  mov     rdx, r14
0x180060751  mov     [rax], rsi
0x180060754  mov     ecx, 1
0x180060759  mov     [rax+8], rsi
0x18006075d  mov     [rax+10h], rsi
0x180060761  mov     [rax+18h], esi
0x180060764  call    ?PopulateDisabledBuiltInComponents@CCodecInfo@@SAJW4WICComponentType@@PEAV?$DynArray@PEBU_GUID@@$0A@@@@Z; CCodecInfo::PopulateDisabledBuiltInComponents(WICComponentType,DynArray<_GUID const *,0> *)
0x180060769  mov     r12d, [r14+18h]
0x18006076d  mov     ebx, esi
0x18006076f  cmp     ebx, r12d
0x180060772  jb      loc_180060CCC
0x180060778  mov     rdx, r15
0x18006077b  mov     ecx, 2
0x180060780  call    ?PopulateDisabledBuiltInComponents@CCodecInfo@@SAJW4WICComponentType@@PEAV?$DynArray@PEBU_GUID@@$0A@@@@Z; CCodecInfo::PopulateDisabledBuiltInComponents(WICComponentType,DynArray<_GUID const *,0> *)
0x180060785  mov     r12d, [r15+18h]
0x180060789  mov     ebx, esi
0x18006078b  cmp     ebx, r12d
0x18006078e  jb      loc_180060C34
0x180060794  mov     rdx, r13
0x180060797  mov     ecx, 8
0x18006079c  call    ?PopulateDisabledBuiltInComponents@CMetadataHandlerInfo@@SAJW4WICComponentType@@PEAV?$DynArray@PEBU_GUID@@$0A@@@@Z; CMetadataHandlerInfo::PopulateDisabledBuiltInComponents(WICComponentType,DynArray<_GUID const *,0> *)
0x1800607a1  mov     r12d, [r13+18h]
0x1800607a5  mov     ebx, esi
0x1800607a7  cmp     ebx, r12d
0x1800607aa  jb      loc_180060B9D
0x1800607b0  mov     rsi, [rsp+2D0h+var_290]
0x1800607b5  mov     ecx, 10h
0x1800607ba  mov     rdx, rsi
0x1800607bd  call    ?PopulateDisabledBuiltInComponents@CMetadataHandlerInfo@@SAJW4WICComponentType@@PEAV?$DynArray@PEBU_GUID@@$0A@@@@Z; CMetadataHandlerInfo::PopulateDisabledBuiltInComponents(WICComponentType,DynArray<_GUID const *,0> *)
0x1800607c2  mov     r12d, [rsi+18h]
0x1800607c6  xor     eax, eax
0x1800607c8  mov     ebx, eax
0x1800607ca  cmp     ebx, r12d
0x1800607cd  jb      loc_180060B4F
0x1800607d3  mov     rsi, [rsp+2D0h+var_288]
0x1800607d8  mov     rcx, rsi
0x1800607db  call    ?PopulateDisabledBuiltInComponents@CFormatConverterInfo@@SAJPEAV?$DynArray@PEBU_GUID@@$0A@@@@Z; CFormatConverterInfo::PopulateDisabledBuiltInComponents(DynArray<_GUID const *,0> *)
0x1800607e0  mov     r12d, [rsi+18h]
0x1800607e4  xor     eax, eax
0x1800607e6  mov     ebx, eax
0x1800607e8  cmp     ebx, r12d
0x1800607eb  jb      loc_180060BE8
0x1800607f1  mov     r8d, 80h; unsigned int
0x1800607f7  lea     rdx, [rbp+1D0h+SubKey]; unsigned __int16 *
0x1800607fb  lea     rcx, CLSID_WICImagingCategories; struct _GUID *
0x180060802  call    ?BuildImagingCategoryKey@RegKey@@SAJAEBU_GUID@@PEAGI@Z; RegKey::BuildImagingCategoryKey(_GUID const &,ushort *,uint)
0x180060807  xor     r12d, r12d
0x18006080a  mov     esi, eax
0x18006080c  test    eax, eax
0x18006080e  js      loc_180060DC1
0x180060814  lea     rax, [rsp+2D0h+hKey]
0x180060819  mov     [rsp+2D0h+hKey], r12
0x18006081e  mov     r9d, 20019h; samDesired
0x180060824  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180060829  xor     r8d, r8d; ulOptions
0x18006082c  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x180060830  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180060837  call    cs:__imp_RegOpenKeyExW
0x18006083e  nop     dword ptr [rax+rax+00h]
0x180060843  test    eax, eax
0x180060845  jnz     loc_18006090C
0x18006084b  mov     rdi, [rsp+2D0h+hKey]
0x180060850  lea     rax, [rbp+1D0h+SubKey]
0x180060854  mov     r9d, 80h
0x18006085a  mov     rbx, r12
0x18006085d  mov     edx, r9d
0x180060860  cmp     [rax], r12w
0x180060864  jz      short loc_180060870
0x180060866  add     rax, 2
0x18006086a  sub     rdx, 1
0x18006086e  jnz     short loc_180060860
0x180060870  mov     rax, rdx
0x180060873  mov     rcx, r9
0x180060876  neg     rax
0x180060879  mov     rax, rdx
0x18006087c  sbb     esi, esi
0x18006087e  sub     rcx, rdx
0x180060881  not     esi
0x180060883  and     esi, 80070057h
0x180060889  neg     rax
0x18006088c  sbb     r8, r8
0x18006088f  and     r8, rcx
0x180060892  test    rdx, rdx
0x180060895  jz      loc_180060DDA
0x18006089b  mov     rdx, r9
0x18006089e  lea     rcx, aDisabled; "\\Disabled"
0x1800608a5  lea     r9, [rbp+1D0h+SubKey]
0x1800608a9  mov     eax, 7FFFFFFEh
0x1800608ae  lea     r9, [r9+r8*2]
0x1800608b2  sub     rdx, r8
0x1800608b5  jz      short loc_1800608DB
0x1800608b7  test    rax, rax
0x1800608ba  jz      short loc_1800608DB
0x1800608bc  movzx   r8d, word ptr [rcx]
0x1800608c0  test    r8w, r8w
0x1800608c4  jz      short loc_1800608DB
0x1800608c6  mov     [r9], r8w
0x1800608ca  add     rcx, 2
0x1800608ce  add     r9, 2
0x1800608d2  dec     rax
0x1800608d5  sub     rdx, 1
0x1800608d9  jnz     short loc_1800608B7
0x1800608db  mov     rax, rdx
0x1800608de  lea     rcx, [r9-2]
0x1800608e2  neg     rax
0x1800608e5  sbb     esi, esi
0x1800608e7  not     esi
0x1800608e9  and     esi, 8007007Ah
0x1800608ef  test    rdx, rdx
0x1800608f2  mov     eax, esi
0x1800608f4  cmovnz  rcx, r9
0x1800608f8  mov     [rcx], r12w
0x1800608fc  jz      loc_180060DDC
0x180060902  mov     esi, eax
0x180060904  test    eax, eax
0x180060906  jns     loc_1800609E0
0x18006090c  mov     rbx, [rsp+2D0h+var_290]
0x180060911  mov     r12, [rsp+2D0h+var_288]
0x180060916  mov     rcx, r14; Block
0x180060919  call    ??_G?$DynArray@PEAUIWICMetadataReaderInfo@@$0A@@@QEAAPEAXI@Z; DynArray<IWICMetadataReaderInfo *,0>::`scalar deleting destructor'(uint)
0x18006091e  test    r15, r15
0x180060921  jnz     loc_180060AD7
0x180060927  test    r13, r13
0x18006092a  jnz     loc_1800609D3
0x180060930  test    rbx, rbx
0x180060933  jnz     short loc_1800609AA
0x180060935  test    r12, r12
0x180060938  jnz     short loc_1800609A0
0x18006093a  lea     rcx, ?s_ComponentsLock@CCodecFactory@@2VCCriticalSection@@A; lpCriticalSection
0x180060941  call    cs:__imp_LeaveCriticalSection
0x180060948  nop     dword ptr [rax+rax+00h]
0x18006094d  test    rdi, rdi
0x180060950  jz      short loc_180060961
0x180060952  mov     rcx, rdi; hKey
0x180060955  call    cs:__imp_RegCloseKey
0x18006095c  nop     dword ptr [rax+rax+00h]
0x180060961  mov     eax, esi
0x180060963  mov     rcx, [rbp+1D0h+var_50]
0x18006096a  xor     rcx, rsp; StackCookie
0x18006096d  call    __security_check_cookie
0x180060972  add     rsp, 298h
0x180060979  pop     r15
0x18006097b  pop     r14
0x18006097d  pop     r13
0x18006097f  pop     r12
0x180060981  pop     rdi
0x180060982  pop     rsi
0x180060983  pop     rbx
0x180060984  pop     rbp
0x180060985  retn
0x180060987  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x18006098d  mov     esi, 8007000Eh
0x180060992  jz      short loc_180060916
0x180060994  mov     ecx, esi; int
0x180060996  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18006099b  jmp     loc_180060916
0x1800609a0  mov     rcx, r12; Block
0x1800609a3  call    ??_G?$DynArray@PEAUIWICMetadataReaderInfo@@$0A@@@QEAAPEAXI@Z; DynArray<IWICMetadataReaderInfo *,0>::`scalar deleting destructor'(uint)
0x1800609a8  jmp     short loc_18006093A
0x1800609aa  mov     rcx, rbx; Block
0x1800609ad  call    ??_G?$DynArray@PEAUIWICMetadataReaderInfo@@$0A@@@QEAAPEAXI@Z; DynArray<IWICMetadataReaderInfo *,0>::`scalar deleting destructor'(uint)
0x1800609b2  jmp     short loc_180060935
0x1800609b4  cmp     cs:?g_doStackCaptures@@3HA, ebx; int g_doStackCaptures
0x1800609ba  mov     r13, rsi
0x1800609bd  mov     esi, 8007000Eh
0x1800609c2  jz      short loc_1800609CB
0x1800609c4  mov     ecx, esi; int
0x1800609c6  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800609cb  xor     r15d, r15d
0x1800609ce  jmp     loc_180060916
0x1800609d3  mov     rcx, r13; Block
0x1800609d6  call    ??_G?$DynArray@PEAUIWICMetadataReaderInfo@@$0A@@@QEAAPEAXI@Z; DynArray<IWICMetadataReaderInfo *,0>::`scalar deleting destructor'(uint)
0x1800609db  jmp     loc_180060930
0x1800609e0  lea     rax, [rsp+2D0h+hKey]
0x1800609e5  mov     [rsp+2D0h+hKey], r12
0x1800609ea  mov     r9d, 20019h; samDesired
0x1800609f0  mov     [rsp+2D0h+phkResult], rax; phkResult
0x1800609f5  xor     r8d, r8d; ulOptions
0x1800609f8  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x1800609fc  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180060a03  call    cs:__imp_RegOpenKeyExW
0x180060a0a  nop     dword ptr [rax+rax+00h]
0x180060a0f  test    eax, eax
0x180060a11  jnz     loc_180060C98
0x180060a17  mov     rbx, [rsp+2D0h+hKey]
0x180060a1c  xor     r8d, r8d
0x180060a1f  mov     [rsp+2D0h+var_270], rbx
0x180060a24  lea     rax, [rsp+2D0h+ftLastWriteTime]
0x180060a29  mov     qword ptr [rsp+2D0h+ftLastWriteTime.dwLowDateTime], r8
0x180060a2e  mov     [rsp+2D0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180060a33  lea     r9, [rsp+2D0h+hKey]; lpcchName
0x180060a38  mov     [rsp+2D0h+lpcchClass], r8; lpcchClass
0x180060a3d  mov     edx, r12d; dwIndex
0x180060a40  mov     [rsp+2D0h+lpClass], r8; lpClass
0x180060a45  mov     rcx, rbx; hKey
0x180060a48  mov     [rsp+2D0h+phkResult], r8; lpReserved
0x180060a4d  lea     r8, [rbp+1D0h+Name]; lpName
0x180060a54  mov     dword ptr [rsp+2D0h+hKey], 80h
0x180060a5c  call    cs:__imp_RegEnumKeyExW
0x180060a63  nop     dword ptr [rax+rax+00h]
0x180060a68  test    eax, eax
0x180060a6a  jnz     loc_180060C7E
0x180060a70  xorps   xmm0, xmm0
0x180060a73  lea     rdx, [rsp+2D0h+iid]; lpiid
0x180060a78  lea     rcx, [rbp+1D0h+Name]; lpsz
0x180060a7f  movups  xmmword ptr [rsp+2D0h+iid.Data1], xmm0
0x180060a84  call    cs:__imp_IIDFromString
0x180060a8b  nop     dword ptr [rax+rax+00h]
0x180060a90  xor     r8d, r8d
0x180060a93  mov     esi, eax
0x180060a95  test    eax, eax
0x180060a97  js      loc_180060E6D
0x180060a9d  mov     eax, cs:dword_18026A028
0x180060aa3  lea     edx, [rax+1]
0x180060aa6  cmp     edx, eax
0x180060aa8  jb      loc_180060E32
  ... truncated ...
```
