# CStorageProviderRootsCache::_InitializeUserRoots(HKEY__ *)

- ea: `0x18000b178`
- end: `0x18000b6ca`
- name: `?_InitializeUserRoots@CStorageProviderRootsCache@@AEAAJPEAUHKEY__@@@Z`
- size: `1362`
- prototype: `int(CStorageProviderRootsCache *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180016fe8`

## callees

- `0x18000b178`
- `0x18000b9b0`
- `0x18000b9e4`
- `0x18000ba10`
- `0x18000bc30`
- `0x18000c6d8`
- `0x18000c7b8`
- `0x180019680`
- `0x180037780`
- `0x180037ca0`
- `0x180038708`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b53d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b53d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b465`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b465`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b472`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b472`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b1f0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b1f0`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000b316`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000b316`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000b252`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000b252`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CStorageProviderRootsCache::_InitializeUserRoots(CStorageProviderRootsCache *this, HKEY a2)
{
  HKEY v2; // rax
  CStorageProviderRootsCache *v3; // rsi
  signed int v4; // ebx
  unsigned int i; // r12d
  int v6; // eax
  bool v7; // sf
  LSTATUS v8; // eax
  int v9; // edx
  int v10; // ecx
  DWORD v11; // edi
  DWORD v12; // r14d
  DWORD v13; // r13d
  BYTE *v14; // r15
  LSTATUS v15; // eax
  __int64 v16; // rdx
  CStorageProviderRootsCache::USER_SYNC_ROOT_INFO *v17; // rax
  CStorageProviderRootsCache::USER_SYNC_ROOT_INFO *v18; // rdi
  __int64 v19; // r9
  WCHAR *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rcx
  unsigned __int128 v23; // rax
  _QWORD *v24; // rsi
  __int64 v25; // rdx
  unsigned __int64 v27; // r14
  unsigned __int64 v28; // rsi
  WCHAR *v29; // rcx
  unsigned __int64 v30; // r8
  WCHAR *v31; // rax
  __int64 v32; // r10
  WCHAR v33; // r9
  __int64 v34; // rsi
  bool v35; // cf
  unsigned __int64 j; // rdi
  __int64 v37; // rbx
  __int64 v38; // rdx
  __int64 v39; // rcx
  int phkResult; // [rsp+20h] [rbp-E0h]
  DWORD cbMaxValueLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cValues; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD Type; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbData[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v45; // [rsp+78h] [rbp-88h]
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  DWORD cchValueName; // [rsp+88h] [rbp-78h] BYREF
  CStorageProviderRootsCache *v48; // [rsp+90h] [rbp-70h]
  __int64 v49; // [rsp+98h] [rbp-68h]
  HKEY v50; // [rsp+A0h] [rbp-60h]
  LPBYTE lpData; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v52; // [rsp+B0h] [rbp-50h]
  __int64 v53; // [rsp+B8h] [rbp-48h]
  WCHAR ValueName[184]; // [rsp+C0h] [rbp-40h] BYREF

  v2 = a2;
  v50 = a2;
  v3 = this;
  v48 = this;
  v4 = 0;
  for ( i = 0; i < 2; ++i )
  {
    hKey = 0;
    v6 = RegOpenKeyExW(v2, (LPCWSTR)(&CStorageProviderRootsCache::s_rgUserRootsRegistryKey)[i], 0, 0x20119u, &hKey);
    v7 = v6 < 0;
    if ( v6 > 0 )
    {
      v6 = (unsigned __int16)v6 | 0x80070000;
      v7 = v6 < 0;
    }
    if ( v7 )
    {
      v4 = HResultIgnoreNotFound(v6);
    }
    else
    {
      cValues = 0;
      cbMaxValueLen = 0;
      v8 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, &cbMaxValueLen, 0, 0);
      v4 = v8;
      if ( v8 > 0 )
        v4 = (unsigned __int16)v8 | 0x80070000;
      if ( v4 >= 0 )
      {
        v11 = cbMaxValueLen >> 1;
        v45 = cbMaxValueLen >> 1;
        v12 = cbMaxValueLen >> 1;
        v49 = v45;
        lpData = 0;
        v52 = -1;
        v53 = -1;
        v4 = _AllocStringWorker<CTCoAllocPolicy>(v10, v9, 0, cbMaxValueLen >> 1, phkResult, (__int64)&lpData);
        v13 = 0;
        v14 = lpData;
        if ( v4 >= 0 )
        {
          while ( 1 )
          {
            if ( v13 >= cValues )
              goto LABEL_36;
            cchValueName = 184;
            Type = 0;
            if ( !v11 )
            {
              v4 = -2147024809;
              goto LABEL_33;
            }
            cbData[0] = 2 * v12;
            v15 = RegEnumValueW(hKey, v13, ValueName, &cchValueName, 0, &Type, v14, cbData);
            v4 = v15;
            if ( v15 > 0 )
              v4 = (unsigned __int16)v15 | 0x80070000;
            if ( v4 < 0 )
              goto LABEL_33;
            if ( ((Type - 1) & 0xFFFFFFFA) != 0 || Type == 5 )
            {
              v4 = -2147023266;
              goto LABEL_33;
            }
            v16 = cbData[0] >> 1;
            if ( *(_WORD *)&v14[2 * (unsigned int)(v16 - 1)] )
            {
              if ( (int)v16 + 1 > v11 )
              {
                v4 = -2147024662;
                goto LABEL_33;
              }
              *(_WORD *)&v14[2 * v16] = 0;
            }
            v4 = 0;
            if ( i )
            {
              for ( j = 0; j < *((_QWORD *)v3 + 71); ++j )
              {
                if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                                     *(_QWORD *)(*((_QWORD *)v3 + 70) + 8 * j),
                                     ValueName,
                                     -1) == 2 )
                {
                  v37 = *(_QWORD *)(*((_QWORD *)v3 + 70) + 8 * j);
                  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v37 + 48);
                  *(_QWORD *)(v37 + 56) = -1;
                  *(_QWORD *)(v37 + 64) = -1;
                  v4 = _AllocString<CTCoAllocPolicy>(v39, v38, v14, v37 + 48);
                  goto LABEL_32;
                }
              }
              goto LABEL_32;
            }
            v17 = (CStorageProviderRootsCache::USER_SYNC_ROOT_INFO *)operator new(
                                                                       0x48u,
                                                                       (const struct std::nothrow_t *)&std::nothrow);
            v18 = v17;
            *(_QWORD *)cbData = v17;
            if ( v17 )
              break;
            v4 = -2147024882;
LABEL_32:
            v11 = v45;
LABEL_33:
            if ( v14 )
              *(_WORD *)v14 = 0;
            v52 = 0;
            ++v13;
            v3 = v48;
            v12 = v49;
            if ( v4 < 0 )
              goto LABEL_36;
          }
          memset_0(v17, 0, 0x48u);
          *(_QWORD *)v18 = 0;
          *((_QWORD *)v18 + 1) = 0;
          *((_QWORD *)v18 + 2) = 0;
          *((_QWORD *)v18 + 3) = 0;
          *((_QWORD *)v18 + 4) = 0;
          *((_QWORD *)v18 + 5) = 0;
          *((_QWORD *)v18 + 6) = 0;
          *((_QWORD *)v18 + 7) = 0;
          *((_QWORD *)v18 + 8) = 0;
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v18);
          *((_QWORD *)v18 + 1) = -1;
          *((_QWORD *)v18 + 2) = -1;
          v27 = -1;
          do
            ++v27;
          while ( ValueName[v27] );
          *(_QWORD *)v18 = 0;
          v28 = v27 + 1;
          if ( v27 + 1 >= v27 && (*(_QWORD *)cbData = 0, v23 = v28 * (unsigned __int128)2uLL, is_mul_ok(v28, 2u)) )
          {
            *((_QWORD *)&v23 + 1) = CoTaskMemAlloc(2 * v28);
            *(_QWORD *)v18 = *((_QWORD *)&v23 + 1);
            v4 = *((_QWORD *)&v23 + 1) == 0 ? 0x8007000E : 0;
            if ( *((_QWORD *)&v23 + 1) )
            {
              if ( v28 > 0x7FFFFFFF )
                goto LABEL_65;
              if ( v27 < 0x7FFFFFFF )
              {
                v29 = ValueName;
                v30 = v27 + 1;
                v31 = (WCHAR *)*((_QWORD *)&v23 + 1);
                v32 = 0;
                do
                {
                  if ( !v27 )
                    break;
                  v33 = *v29;
                  if ( !*v29 )
                    break;
                  ++v29;
                  *v31++ = v33;
                  --v27;
                  ++v32;
                  --v30;
                }
                while ( v30 );
                v19 = v32 - 1;
                if ( v30 )
                  v19 = v32;
                v20 = v31 - 1;
                if ( v30 )
                  v20 = v31;
                *v20 = 0;
                if ( v30 )
                {
                  v35 = v28 == v19;
                  v34 = v28 - v19;
                  if ( !v35 && v34 != 1 && (unsigned __int64)(2 * v34) > 2 )
                    memset_0((void *)(*((_QWORD *)&v23 + 1) + 2 * (v19 + 1)), 0, 2 * v34 - 2);
                }
                goto LABEL_26;
              }
              if ( v27 != -1 )
LABEL_65:
                **((_WORD **)&v23 + 1) = 0;
LABEL_26:
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)v18 + 24);
              *((_QWORD *)v18 + 4) = -1;
              *((_QWORD *)v18 + 5) = -1;
              v4 = _AllocString<CTCoAllocPolicy>(v22, v21, v14, (char *)v18 + 24);
              if ( v4 >= 0 )
              {
                v24 = (_QWORD *)((char *)v48 + 560);
                v4 = 0;
                v25 = *((_QWORD *)v48 + 71);
                if ( v25 != *((_QWORD *)v48 + 73)
                  || (v4 = CTSimpleArray<CStorageProviderRootsCache::USER_SYNC_ROOT_INFO *,4294967294,CTPolicyCoTaskMem<CStorageProviderRootsCache::USER_SYNC_ROOT_INFO *>,CSimpleArrayStandardCompareHelper<CStorageProviderRootsCache::USER_SYNC_ROOT_INFO *>,CSimpleArrayStandardMergeHelper<CStorageProviderRootsCache::USER_SYNC_ROOT_INFO *>>::_EnsureCapacity(
                             (char *)v48 + 560,
                             v25 + 1),
                      v4 >= 0) )
                {
                  *((_QWORD *)&v23 + 1) = *v24 + 8 * v24[1]++;
                  if ( *((_QWORD *)&v23 + 1) )
                    **((_QWORD **)&v23 + 1) = v18;
                }
                if ( v4 >= 0 )
                  goto LABEL_32;
              }
            }
          }
          else
          {
            v4 = -2147024362;
          }
          CStorageProviderRootsCache::USER_SYNC_ROOT_INFO::`scalar deleting destructor'(v18, DWORD2(v23));
          goto LABEL_32;
        }
LABEL_36:
        if ( v14 )
          CoTaskMemFree(v14);
      }
      RegCloseKey(hKey);
    }
    v2 = v50;
    if ( v4 < 0 )
      return (unsigned int)v4;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000b178  mov     [rsp-8+arg_10], rbx
0x18000b17d  push    rbp
0x18000b17e  push    rsi
0x18000b17f  push    rdi
0x18000b180  push    r12
0x18000b182  push    r13
0x18000b184  push    r14
0x18000b186  push    r15
0x18000b188  lea     rbp, [rsp-140h]
0x18000b190  sub     rsp, 240h
0x18000b197  mov     rax, cs:__security_cookie
0x18000b19e  xor     rax, rsp
0x18000b1a1  mov     [rbp+170h+var_40], rax
0x18000b1a8  mov     rax, rdx
0x18000b1ab  mov     [rbp+170h+var_1D0], rdx
0x18000b1af  mov     rsi, rcx
0x18000b1b2  mov     [rbp+170h+var_1E0], rcx
0x18000b1b6  xor     r15d, r15d
0x18000b1b9  mov     ebx, r15d
0x18000b1bc  mov     r12d, r15d
0x18000b1bf  cmp     r12d, 2
0x18000b1c3  jnb     loc_18000B487
0x18000b1c9  mov     [rbp+170h+hKey], r15
0x18000b1cd  mov     edx, r12d
0x18000b1d0  lea     r10, ?s_rgUserRootsRegistryKey@CStorageProviderRootsCache@@0QBQEBGB; ushort const * const near * const CStorageProviderRootsCache::s_rgUserRootsRegistryKey
0x18000b1d7  lea     rcx, [rbp+170h+hKey]
0x18000b1db  mov     [rsp+270h+phkResult], rcx; phkResult
0x18000b1e0  mov     r9d, 20119h; samDesired
0x18000b1e6  xor     r8d, r8d; ulOptions
0x18000b1e9  mov     rdx, [r10+rdx*8]; lpSubKey
0x18000b1ed  mov     rcx, rax; hKey
0x18000b1f0  call    cs:__imp_RegOpenKeyExW
0x18000b1f6  test    eax, eax
0x18000b1f8  jle     short loc_18000B204
0x18000b1fa  movzx   eax, ax
0x18000b1fd  or      eax, 80070000h
0x18000b202  test    eax, eax
0x18000b204  js      loc_18000B5DE
0x18000b20a  mov     [rsp+270h+cValues], r15d
0x18000b20f  mov     [rsp+270h+cbMaxValueLen], r15d
0x18000b214  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000b219  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000b21e  lea     rax, [rsp+270h+cbMaxValueLen]
0x18000b223  mov     [rsp+270h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18000b228  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000b22d  lea     rax, [rsp+270h+cValues]
0x18000b232  mov     [rsp+270h+lpcValues], rax; lpcValues
0x18000b237  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000b23c  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000b241  mov     [rsp+270h+phkResult], r15; lpcSubKeys
0x18000b246  xor     r9d, r9d; lpReserved
0x18000b249  xor     r8d, r8d; lpcchClass
0x18000b24c  xor     edx, edx; lpClass
0x18000b24e  mov     rcx, [rbp+170h+hKey]; hKey
0x18000b252  call    cs:__imp_RegQueryInfoKeyW
0x18000b258  mov     ebx, eax
0x18000b25a  test    eax, eax
0x18000b25c  jle     short loc_18000B267
0x18000b25e  movzx   ebx, ax
0x18000b261  or      ebx, 80070000h
0x18000b267  test    ebx, ebx
0x18000b269  js      loc_18000B46E
0x18000b26f  mov     eax, [rsp+270h+cbMaxValueLen]
0x18000b273  shr     eax, 1
0x18000b275  mov     edi, eax
0x18000b277  mov     [rsp+270h+var_1F8], rdi
0x18000b27c  mov     r14d, eax
0x18000b27f  mov     [rbp+170h+var_1D8], r14
0x18000b283  mov     [rbp+170h+lpData], r15
0x18000b287  mov     [rbp+170h+var_1C0], 0FFFFFFFFFFFFFFFFh
0x18000b28f  mov     [rbp+170h+var_1B8], 0FFFFFFFFFFFFFFFFh
0x18000b297  mov     r9d, eax
0x18000b29a  lea     rax, [rbp+170h+lpData]
0x18000b29e  mov     [rsp+270h+lpcbMaxSubKeyLen], rax
0x18000b2a3  xor     r8d, r8d
0x18000b2a6  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18000b2ab  mov     ebx, eax
0x18000b2ad  mov     r13d, r15d
0x18000b2b0  mov     r15, [rbp+170h+lpData]
0x18000b2b4  test    eax, eax
0x18000b2b6  js      loc_18000B45D
0x18000b2bc  cmp     r13d, [rsp+270h+cValues]
0x18000b2c1  jnb     loc_18000B45D
0x18000b2c7  mov     [rbp+170h+cchValueName], 0B8h
0x18000b2ce  mov     [rsp+270h+Type], 0
0x18000b2d6  test    edi, edi
0x18000b2d8  jz      loc_18000B5D4
0x18000b2de  lea     eax, [r14+r14]
0x18000b2e2  mov     [rsp+270h+cbData], eax
0x18000b2e6  lea     rax, [rsp+270h+cbData]
0x18000b2eb  mov     [rsp+270h+lpcValues], rax; lpcbData
0x18000b2f0  mov     [rsp+270h+lpcbMaxClassLen], r15; lpData
0x18000b2f5  lea     rax, [rsp+270h+Type]
0x18000b2fa  mov     [rsp+270h+lpcbMaxSubKeyLen], rax; lpType
0x18000b2ff  xor     r14d, r14d
0x18000b302  mov     [rsp+270h+phkResult], r14; lpReserved
0x18000b307  lea     r9, [rbp+170h+cchValueName]; lpcchValueName
0x18000b30b  lea     r8, [rbp+170h+ValueName]; lpValueName
0x18000b30f  mov     edx, r13d; dwIndex
0x18000b312  mov     rcx, [rbp+170h+hKey]; hKey
0x18000b316  call    cs:__imp_RegEnumValueW
0x18000b31c  mov     ebx, eax
0x18000b31e  test    eax, eax
0x18000b320  jle     short loc_18000B32B
0x18000b322  movzx   ebx, ax
0x18000b325  or      ebx, 80070000h
0x18000b32b  test    ebx, ebx
0x18000b32d  js      loc_18000B437
0x18000b333  mov     ecx, [rsp+270h+Type]
0x18000b337  lea     eax, [rcx-1]
0x18000b33a  test    eax, 0FFFFFFFAh
0x18000b33f  jnz     loc_18000B6BF
0x18000b345  cmp     ecx, 5
0x18000b348  jz      loc_18000B6BF
0x18000b34e  mov     edx, [rsp+270h+cbData]
0x18000b352  shr     edx, 1
0x18000b354  lea     eax, [rdx-1]
0x18000b357  cmp     [r15+rax*2], r14w
0x18000b35c  jnz     loc_18000B61E
0x18000b362  mov     ebx, r14d
0x18000b365  test    r12d, r12d
0x18000b368  jnz     loc_18000B65B
0x18000b36e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b375  lea     ebx, [r12+48h]
0x18000b37a  mov     ecx, ebx; unsigned __int64
0x18000b37c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b381  mov     rdi, rax
0x18000b384  mov     qword ptr [rsp+270h+cbData], rax
0x18000b389  test    rax, rax
0x18000b38c  jnz     loc_18000B4B3
0x18000b392  mov     ebx, 8007000Eh
0x18000b397  jmp     loc_18000B432
0x18000b39c  lea     r9, [r10-1]
0x18000b3a0  xor     r14d, r14d
0x18000b3a3  test    r8, r8
0x18000b3a6  cmovnz  r9, r10
0x18000b3aa  lea     rcx, [rax-2]
0x18000b3ae  cmovnz  rcx, rax
0x18000b3b2  mov     [rcx], r14w
0x18000b3b6  jnz     loc_18000B5EC
0x18000b3bc  lea     rcx, [rdi+18h]
0x18000b3c0  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000b3c5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b3c9  mov     [rdi+20h], rax
0x18000b3cd  mov     [rdi+28h], rax
0x18000b3d1  lea     r9, [rdi+18h]
0x18000b3d5  mov     r8, r15
0x18000b3d8  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18000b3dd  mov     ebx, eax
0x18000b3df  test    eax, eax
0x18000b3e1  js      loc_18000B5C7
0x18000b3e7  mov     rsi, [rbp+170h+var_1E0]
0x18000b3eb  add     rsi, 230h
0x18000b3f2  mov     ebx, r14d
0x18000b3f5  mov     rdx, [rsi+8]
0x18000b3f9  cmp     rdx, [rsi+18h]
0x18000b3fd  jnz     short loc_18000B410
0x18000b3ff  inc     rdx
0x18000b402  mov     rcx, rsi
0x18000b405  call    ?_EnsureCapacity@?$CTSimpleArray@PEAUUSER_SYNC_ROOT_INFO@CStorageProviderRootsCache@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAUUSER_SYNC_ROOT_INFO@CStorageProviderRootsCache@@@@V?$CSimpleArrayStandardCompareHelper@PEAUUSER_SYNC_ROOT_INFO@CStorageProviderRootsCache@@@@V?$CSimpleArrayStandardMergeHelper@PEAUUSER_SYNC_ROOT_INFO@CStorageProviderRootsCache@@@@@@QEAAJ_K0@Z; CTSimpleArray<CStorageProviderRootsCache::USER_SYNC_ROOT_INFO *,4294967294,CTPolicyCoTaskMem<CStorageProviderRootsCache::USER_SYNC_ROOT_INFO *>,CSimpleArrayStandardCompareHelper<CStorageProviderRootsCache::USER_SYNC_ROOT_INFO *>,CSimpleArrayStandardMergeHelper<CStorageProviderRootsCache::USER_SYNC_ROOT_INFO *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x18000b40a  mov     ebx, eax
0x18000b40c  test    eax, eax
0x18000b40e  js      short loc_18000B42A
0x18000b410  inc     qword ptr [rsi+8]
0x18000b414  mov     rdx, [rsi+8]
0x18000b418  mov     rax, [rsi]
0x18000b41b  dec     rdx
0x18000b41e  lea     rdx, [rax+rdx*8]
0x18000b422  test    rdx, rdx
0x18000b425  jz      short loc_18000B42A
0x18000b427  mov     [rdx], rdi
0x18000b42a  test    ebx, ebx
0x18000b42c  js      loc_18000B5C7
0x18000b432  mov     rdi, [rsp+270h+var_1F8]
0x18000b437  test    r15, r15
0x18000b43a  jz      short loc_18000B442
0x18000b43c  xor     eax, eax
0x18000b43e  mov     [r15], ax
0x18000b442  mov     [rbp+170h+var_1C0], 0
0x18000b44a  inc     r13d
0x18000b44d  test    ebx, ebx
0x18000b44f  mov     rsi, [rbp+170h+var_1E0]
0x18000b453  mov     r14, [rbp+170h+var_1D8]
0x18000b457  jns     loc_18000B2BC
0x18000b45d  test    r15, r15
0x18000b460  jz      short loc_18000B46B
0x18000b462  mov     rcx, r15; pv
0x18000b465  call    cs:__imp_CoTaskMemFree
0x18000b46b  xor     r15d, r15d
0x18000b46e  mov     rcx, [rbp+170h+hKey]; hKey
0x18000b472  call    cs:__imp_RegCloseKey
0x18000b478  inc     r12d
0x18000b47b  test    ebx, ebx
0x18000b47d  mov     rax, [rbp+170h+var_1D0]
0x18000b481  jns     loc_18000B1BF
0x18000b487  mov     eax, ebx
0x18000b489  mov     rcx, [rbp+170h+var_40]
0x18000b490  xor     rcx, rsp; StackCookie
0x18000b493  call    __security_check_cookie
0x18000b498  mov     rbx, [rsp+270h+arg_10]
0x18000b4a0  add     rsp, 240h
0x18000b4a7  pop     r15
0x18000b4a9  pop     r14
0x18000b4ab  pop     r13
0x18000b4ad  pop     r12
0x18000b4af  pop     rdi
0x18000b4b0  pop     rsi
0x18000b4b1  pop     rbp
0x18000b4b2  retn
0x18000b4b3  mov     r8, rbx; Size
0x18000b4b6  xor     edx, edx; Val
0x18000b4b8  mov     rcx, rdi; void *
0x18000b4bb  call    memset_0
0x18000b4c0  mov     [rdi], r14
0x18000b4c3  mov     [rdi+8], r14
0x18000b4c7  mov     [rdi+10h], r14
0x18000b4cb  mov     [rdi+18h], r14
0x18000b4cf  mov     [rdi+20h], r14
0x18000b4d3  mov     [rdi+28h], r14
0x18000b4d7  mov     [rdi+30h], r14
0x18000b4db  mov     [rdi+38h], r14
0x18000b4df  mov     [rdi+40h], r14
0x18000b4e3  test    rdi, rdi
0x18000b4e6  jz      loc_18000B392
0x18000b4ec  mov     rcx, rdi
0x18000b4ef  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000b4f4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000b4f8  mov     [rdi+8], rcx
0x18000b4fc  mov     [rdi+10h], rcx
0x18000b500  lea     rax, [rbp+170h+ValueName]
0x18000b504  mov     r14, rcx
0x18000b507  xor     r11d, r11d
0x18000b50a  inc     r14
0x18000b50d  cmp     [rax+r14*2], r11w
0x18000b512  jnz     short loc_18000B50A
0x18000b514  mov     [rdi], r11
0x18000b517  lea     rsi, [r14+1]
0x18000b51b  cmp     rsi, r14
0x18000b51e  jb      loc_18000B5C2
0x18000b524  mov     qword ptr [rsp+270h+cbData], r11
0x18000b529  mov     eax, 2
0x18000b52e  mul     rsi
0x18000b531  test    rdx, rdx
0x18000b534  jnz     loc_18000B5C2
0x18000b53a  mov     rcx, rax; cb
0x18000b53d  call    cs:__imp_CoTaskMemAlloc
0x18000b543  mov     rdx, rax
0x18000b546  mov     [rdi], rax
0x18000b549  mov     rcx, rax
0x18000b54c  neg     rcx
0x18000b54f  sbb     ebx, ebx
0x18000b551  not     ebx
0x18000b553  and     ebx, 8007000Eh
0x18000b559  xor     r11d, r11d
0x18000b55c  test    rax, rax
0x18000b55f  jz      short loc_18000B5C7
0x18000b561  mov     eax, 7FFFFFFFh
0x18000b566  cmp     rsi, rax
0x18000b569  ja      loc_18000B639
0x18000b56f  cmp     r14, rax
0x18000b572  jnb     loc_18000B63E
0x18000b578  test    rsi, rsi
0x18000b57b  jz      loc_18000B653
0x18000b581  lea     rcx, [rbp+170h+ValueName]
0x18000b585  mov     r8, rsi
0x18000b588  mov     rax, rdx
0x18000b58b  mov     r10d, r11d
0x18000b58e  test    r14, r14
0x18000b591  jz      loc_18000B39C
0x18000b597  movzx   r9d, word ptr [rcx]
0x18000b59b  test    r9w, r9w
0x18000b59f  jz      loc_18000B39C
0x18000b5a5  add     rcx, 2
0x18000b5a9  mov     [rax], r9w
0x18000b5ad  add     rax, 2
0x18000b5b1  dec     r14
0x18000b5b4  inc     r10
0x18000b5b7  sub     r8, 1
0x18000b5bb  jnz     short loc_18000B58E
0x18000b5bd  jmp     loc_18000B39C
0x18000b5c2  mov     ebx, 80070216h
0x18000b5c7  mov     rcx, rdi; this
0x18000b5ca  call    ??_GUSER_SYNC_ROOT_INFO@CStorageProviderRootsCache@@QEAAPEAXI@Z; CStorageProviderRootsCache::USER_SYNC_ROOT_INFO::`scalar deleting destructor'(uint)
0x18000b5cf  jmp     loc_18000B432
0x18000b5d4  mov     ebx, 80070057h
0x18000b5d9  jmp     loc_18000B437
0x18000b5de  mov     ecx, eax; int
0x18000b5e0  call    ?HResultIgnoreNotFound@@YAJJ@Z; HResultIgnoreNotFound(long)
0x18000b5e5  mov     ebx, eax
0x18000b5e7  jmp     loc_18000B478
0x18000b5ec  sub     rsi, r9
0x18000b5ef  cmp     rsi, 1
0x18000b5f3  jbe     loc_18000B3BC
0x18000b5f9  lea     r8, [rsi+rsi]
0x18000b5fd  cmp     r8, 2
0x18000b601  jbe     loc_18000B3BC
0x18000b607  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18000b60b  inc     r9
0x18000b60e  lea     rcx, [rdx+r9*2]; void *
0x18000b612  xor     edx, edx; Val
  ... truncated ...
```
