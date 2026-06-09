# CStorageProviderRootsCache::SetUserSyncRoot(ushort const *,ushort const *)

- ea: `0x180035010`
- end: `0x1800353d5`
- name: `?SetUserSyncRoot@CStorageProviderRootsCache@@QEAAJPEBG0@Z`
- size: `965`
- prototype: `int(CStorageProviderRootsCache *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180034524`

## callees

- `0x180003210`
- `0x18000b9b0`
- `0x18000b9e4`
- `0x18000bc30`
- `0x18000c6d8`
- `0x180019680`
- `0x180035010`
- `0x1800353dc`
- `0x1800356d8`
- `0x180035848`
- `0x180037780`
- `0x180037ca0`
- `0x180043c98`

## import_xrefs

- `SHCORE!SHDeleteValueW` at `0x18003517d`
- `SHCORE!SHDeleteValueW` at `0x18003517d`
- `SHCORE!__imp_SHGlobalCounterIncrement` at `0x1800351c5`
- `SHCORE!__imp_SHGlobalCounterIncrement` at `0x1800351c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035233`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035233`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003536c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003536c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035135`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035135`

## string_xrefs

- `0x18003515d`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x1800351aa`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x1800351de`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180035347`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180035380`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CStorageProviderRootsCache::SetUserSyncRoot(
        CStorageProviderRootsCache *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  signed int v8; // ebx
  unsigned __int64 v9; // r8
  char v10; // si
  __int64 v11; // rdi
  int SyncEngineRegPath; // eax
  wil::details::in1diag3 *v13; // rcx
  unsigned __int64 v14; // r9
  __int64 v15; // rdx
  LSTATUS v16; // eax
  int v17; // eax
  int updated; // eax
  CStorageProviderRootsCache *v19; // rcx
  _QWORD *v20; // rsi
  __int64 v21; // r15
  void *v22; // rcx
  CStorageProviderRootsCache::USER_SYNC_ROOT_INFO *v23; // rax
  CStorageProviderRootsCache::USER_SYNC_ROOT_INFO *v24; // rdi
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rdx
  CStorageProviderRootsCache::USER_SYNC_ROOT_INFO **v30; // rdx
  unsigned int v31; // edx
  int phkResult; // [rsp+20h] [rbp-E0h]
  HKEY hkey; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v35; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v36; // [rsp+40h] [rbp-C0h]
  __int64 v37; // [rsp+48h] [rbp-B8h]
  CStorageProviderRootsCache::USER_SYNC_ROOT_INFO *v38; // [rsp+50h] [rbp-B0h]
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF
  CStorageProviderRootsCache *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v35 = 0;
  v36 = 0;
  v37 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v35);
  v36 = -1;
  v37 = -1;
  v8 = _AllocString<CTCoAllocPolicy>(v7, v6, a3, &v35);
  if ( v8 >= 0 )
  {
    v10 = 0;
    v11 = 0;
    if ( !*((_QWORD *)this + 71) )
      goto LABEL_7;
    while ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                            *(_QWORD *)(*((_QWORD *)this + 70) + 8 * v11),
                            a2,
                            -1) != 2 )
    {
      v10 = 0;
      if ( (unsigned __int64)++v11 >= *((_QWORD *)this + 71) )
        goto LABEL_7;
    }
    v10 = 1;
    if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                         *(_QWORD *)(*((_QWORD *)this + 70) + 8 * v11) + 24LL,
                         a3,
                         -1) != 2 )
    {
LABEL_7:
      SyncEngineRegPath = CStorageProviderRootsCache::_GetSyncEngineRegPath(this, SubKey, v9);
      v8 = SyncEngineRegPath;
      v13 = retaddr;
      if ( SyncEngineRegPath < 0 )
      {
        v14 = (unsigned int)SyncEngineRegPath;
        v15 = 3402;
LABEL_13:
        wil::details::in1diag3::_Log_Hr(
          v13,
          (void *)v15,
          (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
          (const char *)v14,
          phkResult);
        goto LABEL_33;
      }
      hkey = 0;
      v16 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x2011Fu, &hkey);
      v8 = v16;
      if ( v16 > 0 )
        v8 = (unsigned __int16)v16 | 0x80070000;
      v13 = retaddr;
      if ( v8 < 0 )
      {
        v14 = (unsigned int)v8;
        v15 = 3406;
        goto LABEL_13;
      }
      SHDeleteValueW(hkey, L"PendingRedirectionSyncRoots", a2);
      v17 = SHRegSetString(hkey, L"UserSyncRoots", a2, a3);
      v8 = v17;
      if ( v17 >= 0 )
      {
        SHGlobalCounterIncrement(GLOBALCOUNTER_FOLDERDEFINITION_CACHE|GLOBALCOUNTER_OVERLAYMANAGER);
        updated = SetSyncRootManagerRegistryUpdateEvent();
        v19 = retaddr;
        if ( updated < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xD58,
            (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
            (const char *)(unsigned int)updated,
            phkResult);
        if ( v10 )
        {
          CStorageProviderRootsCache::_UpdateStorageProviderIdInExtrinsicPropertyStore(
            v19,
            *(const unsigned __int16 **)(*(_QWORD *)(*((_QWORD *)this + 70) + 8 * v11) + 24LL),
            0);
          v20 = *(_QWORD **)(*((_QWORD *)this + 70) + 8 * v11);
          v21 = v35;
          v35 = 0;
          v37 = 0;
          v36 = 0;
          v22 = (void *)v20[3];
          if ( v22 )
            CoTaskMemFree(v22);
          v20[3] = v21;
          v20[5] = -1;
          v20[4] = -1;
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(*(_QWORD *)(*((_QWORD *)this + 70) + 8 * v11) + 48LL);
        }
        else
        {
          v23 = (CStorageProviderRootsCache::USER_SYNC_ROOT_INFO *)operator new(
                                                                     0x48u,
                                                                     (const struct std::nothrow_t *)&std::nothrow);
          v24 = v23;
          v38 = v23;
          if ( v23 )
          {
            *(_QWORD *)v23 = 0;
            *((_QWORD *)v23 + 1) = 0;
            *((_QWORD *)v23 + 2) = 0;
            *((_QWORD *)v23 + 3) = 0;
            *((_QWORD *)v23 + 4) = 0;
            *((_QWORD *)v23 + 5) = 0;
            *((_QWORD *)v23 + 6) = 0;
            *((_QWORD *)v23 + 7) = 0;
            *((_QWORD *)v23 + 8) = 0;
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v23);
            *((_QWORD *)v24 + 1) = -1;
            *((_QWORD *)v24 + 2) = -1;
            v8 = _AllocString<CTCoAllocPolicy>(v26, v25, a2, v24);
            if ( v8 >= 0 )
            {
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)v24 + 24);
              *((_QWORD *)v24 + 4) = -1;
              *((_QWORD *)v24 + 5) = -1;
              v8 = _AllocString<CTCoAllocPolicy>(v28, v27, v35, (char *)v24 + 24);
              if ( v8 >= 0 )
              {
                v8 = 0;
                v29 = *((_QWORD *)this + 71);
                if ( v29 != *((_QWORD *)this + 73)
                  || (v8 = CTSimpleArray<CStorageProviderRootsCache::USER_SYNC_ROOT_INFO *,4294967294,CTPolicyCoTaskMem<CStorageProviderRootsCache::USER_SYNC_ROOT_INFO *>,CSimpleArrayStandardCompareHelper<CStorageProviderRootsCache::USER_SYNC_ROOT_INFO *>,CSimpleArrayStandardMergeHelper<CStorageProviderRootsCache::USER_SYNC_ROOT_INFO *>>::_EnsureCapacity(
                             (char *)this + 560,
                             v29 + 1),
                      v8 >= 0) )
                {
                  v30 = (CStorageProviderRootsCache::USER_SYNC_ROOT_INFO **)(*((_QWORD *)this + 70)
                                                                           + 8 * (*((_QWORD *)this + 71))++);
                  if ( v30 )
                    *v30 = v24;
                }
              }
            }
            if ( v8 < 0 )
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0xD70,
                (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
                (const char *)(unsigned int)v8,
                phkResult);
              CStorageProviderRootsCache::USER_SYNC_ROOT_INFO::`scalar deleting destructor'(v24, v31);
            }
          }
          else
          {
            v8 = -2147024882;
          }
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xD52,
          (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
          (const char *)(unsigned int)v17,
          phkResult);
      }
      RegCloseKey(hkey);
    }
  }
LABEL_33:
  if ( v8 >= 0 )
    CStorageProviderRootsCache::_UpdateStorageProviderIdInExtrinsicPropertyStore(
      retaddr,
      a3,
      *(const unsigned __int16 **)this);
  else
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xD7D,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)v8,
      phkResult);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v35);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180035010  mov     [rsp-8+arg_18], rbx
0x180035015  push    rbp
0x180035016  push    rsi
0x180035017  push    rdi
0x180035018  push    r12
0x18003501a  push    r13
0x18003501c  push    r14
0x18003501e  push    r15
0x180035020  lea     rbp, [rsp-180h]
0x180035028  sub     rsp, 280h
0x18003502f  mov     rax, cs:__security_cookie
0x180035036  xor     rax, rsp
0x180035039  mov     [rbp+1B0h+var_40], rax
0x180035040  mov     r12, r8
0x180035043  mov     r15, rdx
0x180035046  mov     r14, rcx
0x180035049  xor     r13d, r13d
0x18003504c  mov     [rsp+2B0h+var_278], r13
0x180035051  mov     [rsp+2B0h+var_270], r13
0x180035056  mov     [rsp+2B0h+var_268], r13
0x18003505b  lea     rcx, [rsp+2B0h+var_278]
0x180035060  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180035065  or      rax, 0FFFFFFFFFFFFFFFFh
0x180035069  mov     [rsp+2B0h+var_270], rax
0x18003506e  mov     [rsp+2B0h+var_268], rax
0x180035073  lea     r9, [rsp+2B0h+var_278]
0x180035078  mov     r8, r12
0x18003507b  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180035080  mov     ebx, eax
0x180035082  test    eax, eax
0x180035084  js      loc_180035372
0x18003508a  mov     sil, r13b
0x18003508d  mov     edi, r13d
0x180035090  cmp     [r14+238h], r13
0x180035097  jbe     short loc_1800350ED
0x180035099  mov     rcx, [r14+230h]
0x1800350a0  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800350a4  mov     rdx, r15
0x1800350a7  mov     rcx, [rcx+rdi*8]
0x1800350ab  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800350b0  cmp     eax, 2
0x1800350b3  jz      short loc_1800350C6
0x1800350b5  mov     sil, r13b
0x1800350b8  inc     rdi
0x1800350bb  cmp     rdi, [r14+238h]
0x1800350c2  jb      short loc_180035099
0x1800350c4  jmp     short loc_1800350ED
0x1800350c6  mov     sil, 1
0x1800350c9  mov     rax, [r14+230h]
0x1800350d0  mov     rcx, [rax+rdi*8]
0x1800350d4  add     rcx, 18h
0x1800350d8  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800350dc  mov     rdx, r12
0x1800350df  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800350e4  cmp     eax, 2
0x1800350e7  jz      loc_180035372
0x1800350ed  lea     rdx, [rsp+2B0h+SubKey]; unsigned __int16 *
0x1800350f2  mov     rcx, r14; this
0x1800350f5  call    ?_GetSyncEngineRegPath@CStorageProviderRootsCache@@AEBAJPEAG_K@Z; CStorageProviderRootsCache::_GetSyncEngineRegPath(ushort *,unsigned __int64)
0x1800350fa  mov     ebx, eax
0x1800350fc  mov     rcx, [rbp+1B8h]
0x180035103  test    eax, eax
0x180035105  jns     short loc_180035111
0x180035107  mov     r9d, eax
0x18003510a  mov     edx, 0D4Ah
0x18003510f  jmp     short loc_18003515D
0x180035111  mov     [rsp+2B0h+hkey], r13
0x180035116  lea     rax, [rsp+2B0h+hkey]
0x18003511b  mov     qword ptr [rsp+2B0h+phkResult], rax; int
0x180035120  mov     r9d, 2011Fh; samDesired
0x180035126  xor     r8d, r8d; ulOptions
0x180035129  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x18003512e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180035135  call    cs:__imp_RegOpenKeyExW
0x18003513b  mov     ebx, eax
0x18003513d  test    eax, eax
0x18003513f  jle     short loc_18003514A
0x180035141  movzx   ebx, ax
0x180035144  or      ebx, 80070000h
0x18003514a  mov     rcx, [rbp+1B8h]; this
0x180035151  test    ebx, ebx
0x180035153  jns     short loc_18003516E
0x180035155  mov     r9d, ebx; char *
0x180035158  mov     edx, 0D4Eh; void *
0x18003515d  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180035164  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035169  jmp     loc_180035372
0x18003516e  mov     r8, r15; pszValue
0x180035171  lea     rdx, pszSubKey; "PendingRedirectionSyncRoots"
0x180035178  mov     rcx, [rsp+2B0h+hkey]; hkey
0x18003517d  call    cs:__imp_SHDeleteValueW
0x180035183  mov     r9, r12; unsigned __int16 *
0x180035186  mov     r8, r15; unsigned __int16 *
0x180035189  lea     rdx, aUsersyncroots_0; "UserSyncRoots"
0x180035190  mov     rcx, [rsp+2B0h+hkey]; HKEY
0x180035195  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18003519a  mov     ebx, eax
0x18003519c  mov     rcx, [rbp+1B8h]; this
0x1800351a3  test    eax, eax
0x1800351a5  jns     short loc_1800351C0
0x1800351a7  mov     r9d, eax; char *
0x1800351aa  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x1800351b1  mov     edx, 0D52h; void *
0x1800351b6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800351bb  jmp     loc_180035367
0x1800351c0  mov     ecx, 39h ; '9'; id
0x1800351c5  call    cs:__imp_SHGlobalCounterIncrement
0x1800351cb  call    ?SetSyncRootManagerRegistryUpdateEvent@@YAJXZ; SetSyncRootManagerRegistryUpdateEvent(void)
0x1800351d0  mov     rcx, [rbp+1B8h]; this
0x1800351d7  test    eax, eax
0x1800351d9  jns     short loc_1800351EF
0x1800351db  mov     r9d, eax; char *
0x1800351de  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x1800351e5  mov     edx, 0D58h; void *
0x1800351ea  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800351ef  test    sil, sil
0x1800351f2  jz      short loc_180035262
0x1800351f4  mov     rax, [r14+230h]
0x1800351fb  mov     rdx, [rax+rdi*8]
0x1800351ff  xor     r8d, r8d; unsigned __int16 *
0x180035202  mov     rdx, [rdx+18h]; unsigned __int16 *
0x180035206  call    ?_UpdateStorageProviderIdInExtrinsicPropertyStore@CStorageProviderRootsCache@@AEAAXPEBG0@Z; CStorageProviderRootsCache::_UpdateStorageProviderIdInExtrinsicPropertyStore(ushort const *,ushort const *)
0x18003520b  mov     rax, [r14+230h]
0x180035212  mov     rsi, [rax+rdi*8]
0x180035216  mov     r15, [rsp+2B0h+var_278]
0x18003521b  mov     [rsp+2B0h+var_278], r13
0x180035220  mov     [rsp+2B0h+var_268], r13
0x180035225  mov     [rsp+2B0h+var_270], r13
0x18003522a  mov     rcx, [rsi+18h]; pv
0x18003522e  test    rcx, rcx
0x180035231  jz      short loc_180035239
0x180035233  call    cs:__imp_CoTaskMemFree
0x180035239  mov     [rsi+18h], r15
0x18003523d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180035241  mov     [rsi+28h], rax
0x180035245  mov     [rsi+20h], rax
0x180035249  mov     rax, [r14+230h]
0x180035250  mov     rcx, [rax+rdi*8]
0x180035254  add     rcx, 30h ; '0'
0x180035258  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003525d  jmp     loc_180035367
0x180035262  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180035269  mov     ecx, 48h ; 'H'; unsigned __int64
0x18003526e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180035273  mov     rdi, rax
0x180035276  mov     [rsp+2B0h+var_260], rax
0x18003527b  test    rax, rax
0x18003527e  jz      loc_180035362
0x180035284  mov     [rax], r13
0x180035287  mov     [rax+8], r13
0x18003528b  mov     [rax+10h], r13
0x18003528f  mov     [rax+18h], r13
0x180035293  mov     [rax+20h], r13
0x180035297  mov     [rax+28h], r13
0x18003529b  mov     [rax+30h], r13
0x18003529f  mov     [rax+38h], r13
0x1800352a3  mov     [rax+40h], r13
0x1800352a7  test    rax, rax
0x1800352aa  jz      loc_180035362
0x1800352b0  mov     rcx, rax
0x1800352b3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800352b8  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800352bc  mov     [rdi+8], rsi
0x1800352c0  mov     [rdi+10h], rsi
0x1800352c4  mov     r9, rdi
0x1800352c7  mov     r8, r15
0x1800352ca  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800352cf  mov     ebx, eax
0x1800352d1  test    eax, eax
0x1800352d3  js      short loc_180035339
0x1800352d5  lea     rcx, [rdi+18h]
0x1800352d9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800352de  mov     [rdi+20h], rsi
0x1800352e2  mov     [rdi+28h], rsi
0x1800352e6  lea     r9, [rdi+18h]
0x1800352ea  mov     r8, [rsp+2B0h+var_278]
0x1800352ef  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800352f4  mov     ebx, eax
0x1800352f6  test    eax, eax
0x1800352f8  js      short loc_180035339
0x1800352fa  lea     rsi, [r14+230h]
0x180035301  mov     ebx, r13d
0x180035304  mov     rdx, [rsi+8]
0x180035308  cmp     rdx, [rsi+18h]
0x18003530c  jnz     short loc_18003531F
0x18003530e  inc     rdx
0x180035311  mov     rcx, rsi
0x180035314  call    ?_EnsureCapacity@?$CTSimpleArray@PEAUUSER_SYNC_ROOT_INFO@CStorageProviderRootsCache@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAUUSER_SYNC_ROOT_INFO@CStorageProviderRootsCache@@@@V?$CSimpleArrayStandardCompareHelper@PEAUUSER_SYNC_ROOT_INFO@CStorageProviderRootsCache@@@@V?$CSimpleArrayStandardMergeHelper@PEAUUSER_SYNC_ROOT_INFO@CStorageProviderRootsCache@@@@@@QEAAJ_K0@Z; CTSimpleArray<CStorageProviderRootsCache::USER_SYNC_ROOT_INFO *,4294967294,CTPolicyCoTaskMem<CStorageProviderRootsCache::USER_SYNC_ROOT_INFO *>,CSimpleArrayStandardCompareHelper<CStorageProviderRootsCache::USER_SYNC_ROOT_INFO *>,CSimpleArrayStandardMergeHelper<CStorageProviderRootsCache::USER_SYNC_ROOT_INFO *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180035319  mov     ebx, eax
0x18003531b  test    eax, eax
0x18003531d  js      short loc_180035339
0x18003531f  inc     qword ptr [rsi+8]
0x180035323  mov     rdx, [rsi+8]
0x180035327  mov     rax, [rsi]
0x18003532a  dec     rdx
0x18003532d  lea     rdx, [rax+rdx*8]
0x180035331  test    rdx, rdx
0x180035334  jz      short loc_180035339
0x180035336  mov     [rdx], rdi
0x180035339  mov     rcx, [rbp+1B8h]; this
0x180035340  test    ebx, ebx
0x180035342  jns     short loc_180035367
0x180035344  mov     r9d, ebx; char *
0x180035347  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18003534e  mov     edx, 0D70h; void *
0x180035353  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035358  mov     rcx, rdi; this
0x18003535b  call    ??_GUSER_SYNC_ROOT_INFO@CStorageProviderRootsCache@@QEAAPEAXI@Z; CStorageProviderRootsCache::USER_SYNC_ROOT_INFO::`scalar deleting destructor'(uint)
0x180035360  jmp     short loc_180035367
0x180035362  mov     ebx, 8007000Eh
0x180035367  mov     rcx, [rsp+2B0h+hkey]; hKey
0x18003536c  call    cs:__imp_RegCloseKey
0x180035372  mov     rcx, [rbp+1B8h]; this
0x180035379  test    ebx, ebx
0x18003537b  jns     short loc_180035393
0x18003537d  mov     r9d, ebx; char *
0x180035380  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180035387  mov     edx, 0D7Dh; void *
0x18003538c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035391  jmp     short loc_18003539F
0x180035393  mov     r8, [r14]; unsigned __int16 *
0x180035396  mov     rdx, r12; unsigned __int16 *
0x180035399  call    ?_UpdateStorageProviderIdInExtrinsicPropertyStore@CStorageProviderRootsCache@@AEAAXPEBG0@Z; CStorageProviderRootsCache::_UpdateStorageProviderIdInExtrinsicPropertyStore(ushort const *,ushort const *)
0x18003539e  nop
0x18003539f  lea     rcx, [rsp+2B0h+var_278]
0x1800353a4  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800353a9  mov     eax, ebx
0x1800353ab  mov     rcx, [rbp+1B0h+var_40]
0x1800353b2  xor     rcx, rsp; StackCookie
0x1800353b5  call    __security_check_cookie
0x1800353ba  mov     rbx, [rsp+2B0h+arg_18]
0x1800353c2  add     rsp, 280h
0x1800353c9  pop     r15
0x1800353cb  pop     r14
0x1800353cd  pop     r13
0x1800353cf  pop     r12
0x1800353d1  pop     rdi
0x1800353d2  pop     rsi
0x1800353d3  pop     rbp
0x1800353d4  retn
```
