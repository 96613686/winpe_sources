# CleanMgrHelper::InitializeWithType(ushort const *,CLEANMGR_TYPE,ulong)

- ea: `0x180071578`
- end: `0x180071bb2`
- name: `?InitializeWithType@CleanMgrHelper@@QEAAJPEBGW4CLEANMGR_TYPE@@K@Z`
- size: `1594`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180035580`

## callees

- `0x180001148`
- `0x180005bb4`
- `0x18000d030`
- `0x18000d560`
- `0x18000fe54`
- `0x180012c9c`
- `0x180071578`
- `0x180071bb8`
- `0x180071ed8`
- `0x18007d4e4`
- `0x18008a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180071701`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180071701`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800718c1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800718c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180071726`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180071726`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007184b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007184b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800716eb`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800716eb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180071687`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180071805`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180071687`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180071805`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800717a0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800717a0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007191b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007191b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18007186d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18007186d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071b40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071b4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071b5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071b40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071b4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071b5e`
- `ext-ms-win-com-ole32-l1-1-0!OleInitialize` at `0x180071609`
- `ext-ms-win-com-ole32-l1-1-0!OleInitialize` at `0x180071609`

## string_xrefs

- `0x180071679`: `Software\Microsoft\Windows\CurrentVersion\Explorer\VolumeCaches`
- `0x1800717b0`: `Thumbnail Cache`
- `0x1800717c8`: `Microsoft Office Temp Files`
- `0x18007188b`: `PluginType`

## pseudocode

```c
__int64 __fastcall CleanMgrHelper::InitializeWithType(__int64 a1, const wchar_t *a2, int a3)
{
  int Instance; // ebx
  _DWORD *v8; // rax
  LSTATUS InfoKeyW; // eax
  bool v10; // cc
  _DWORD *v11; // r15
  void *v12; // rax
  __int64 v13; // r14
  __int64 v14; // rsi
  __int64 v15; // rcx
  __int64 v16; // rcx
  LSTATUS ValueW; // eax
  unsigned int v18; // ecx
  __int64 v19; // rcx
  __int64 v20; // rax
  int v21; // eax
  __int64 v22; // rdx
  const struct _tlgProvider_t *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // rcx
  const struct _tlgProvider_t *v28; // rax
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // rcx
  unsigned int pvData; // [rsp+60h] [rbp-A0h] BYREF
  int v33; // [rsp+64h] [rbp-9Ch] BYREF
  int v34; // [rsp+68h] [rbp-98h] BYREF
  int v35; // [rsp+6Ch] [rbp-94h] BYREF
  int v36; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchName; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD cbData; // [rsp+78h] [rbp-88h] BYREF
  DWORD pcbData; // [rsp+7Ch] [rbp-84h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  DWORD Type; // [rsp+88h] [rbp-78h] BYREF
  __int64 v42; // [rsp+90h] [rbp-70h] BYREF
  LPVOID pv; // [rsp+98h] [rbp-68h] BYREF
  LPVOID v44; // [rsp+A0h] [rbp-60h] BYREF
  const WCHAR *v45; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR *v46; // [rsp+B0h] [rbp-50h] BYREF
  const WCHAR *v47; // [rsp+B8h] [rbp-48h] BYREF
  LPVOID v48[2]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR Name[264]; // [rsp+D0h] [rbp-30h] BYREF
  OLECHAR Data[264]; // [rsp+2E0h] [rbp+1E0h] BYREF

  hKey = 0;
  cchName = 0;
  cbData = 0;
  pvData = 0;
  pcbData = 0;
  Instance = StringCchCopyW((wchar_t *)(a1 + 32), 0x104u, a2);
  if ( Instance < 0 )
    goto LABEL_10;
  if ( !(unsigned __int8)IsOleInitializePresent() )
    return 2147942450LL;
  Instance = OleInitialize(0);
  if ( Instance < 0 )
    goto LABEL_10;
  *(_DWORD *)(a1 + 560) = 1;
  v8 = operator new(0x10u);
  *(_QWORD *)v8 = &CleanMgrEmptyCallBack::`vftable';
  v8[2] = 1;
  *(_QWORD *)(a1 + 552) = v8;
  Instance = (**(__int64 (__fastcall ***)(void *, GUID *, __int64))v8)(v8, &IID_IEmptyVolumeCacheCallBack, a1 + 24);
  if ( Instance < 0 )
    goto LABEL_10;
  InfoKeyW = RegOpenKeyExW(
               HKEY_LOCAL_MACHINE,
               L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\VolumeCaches",
               0,
               0x20019u,
               &hKey);
  Instance = InfoKeyW;
  v10 = InfoKeyW <= 0;
  if ( InfoKeyW
    || (v11 = (_DWORD *)(a1 + 16),
        InfoKeyW = RegQueryInfoKeyW(hKey, 0, 0, 0, (LPDWORD)(a1 + 16), 0, 0, 0, 0, 0, 0, 0),
        Instance = InfoKeyW,
        v10 = InfoKeyW <= 0,
        InfoKeyW) )
  {
LABEL_46:
    if ( !v10 )
      Instance = (unsigned __int16)InfoKeyW | 0x80070000;
    if ( Instance >= 0 )
      goto LABEL_11;
    goto LABEL_10;
  }
  v12 = calloc((unsigned int)*v11, 0x30u);
  *(_QWORD *)(a1 + 8) = v12;
  if ( v12 )
  {
    v13 = 0;
    if ( !*v11 )
    {
LABEL_45:
      Instance = 0;
      goto LABEL_11;
    }
    while ( 1 )
    {
      cchName = 261;
      InfoKeyW = RegEnumKeyExW(hKey, v13, Name, &cchName, 0, 0, 0, 0);
      Instance = InfoKeyW;
      v10 = InfoKeyW <= 0;
      if ( InfoKeyW )
        goto LABEL_46;
      if ( wcscmp_0(Name, L"Thumbnail Cache") && wcscmp_0(Name, L"Microsoft Office Temp Files") )
      {
        v14 = 48 * v13;
        InfoKeyW = RegOpenKeyExW(hKey, Name, 0, 0x20019u, (PHKEY)(48 * v13 + *(_QWORD *)(a1 + 8)));
        Instance = InfoKeyW;
        v10 = InfoKeyW <= 0;
        if ( InfoKeyW )
          goto LABEL_46;
        v15 = *(_QWORD *)(a1 + 8);
        cbData = 261;
        Type = 1;
        InfoKeyW = RegQueryValueExW(*(HKEY *)(v15 + 48 * v13), 0, 0, &Type, (LPBYTE)Data, &cbData);
        Instance = InfoKeyW;
        v10 = InfoKeyW <= 0;
        if ( InfoKeyW )
          goto LABEL_46;
        Instance = CLSIDFromString(Data, (LPCLSID)(v14 + *(_QWORD *)(a1 + 8) + 8LL));
        if ( Instance < 0 )
          goto LABEL_10;
        v16 = *(_QWORD *)(a1 + 8);
        pcbData = 4;
        pvData = 0;
        ValueW = RegGetValueW(*(HKEY *)(v16 + 48 * v13), 0, L"PluginType", 0x18u, 0, &pvData, &pcbData);
        v18 = pvData;
        if ( !ValueW && pvData <= 3 )
        {
          *(_DWORD *)(*(_QWORD *)(a1 + 8) + v14 + 40) = pvData;
          v18 = pvData;
        }
        if ( a3 == 4 || v18 == a3 )
        {
          v19 = *(_QWORD *)(a1 + 8);
          v33 = 128;
          Instance = CoCreateInstance(
                       (const IID *const)(v14 + v19 + 8),
                       0,
                       1u,
                       &IID_IEmptyVolumeCache,
                       (LPVOID *)(v14 + v19 + 24));
          if ( Instance < 0 )
            goto LABEL_10;
          v20 = *(_QWORD *)(a1 + 8);
          v42 = 0;
          v21 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v20 + v14 + 24))(
                  *(_QWORD *)(v20 + v14 + 24),
                  &IID_IEmptyVolumeCache2,
                  &v42);
          v22 = *(_QWORD *)(a1 + 8);
          pv = 0;
          v44 = 0;
          v48[0] = 0;
          if ( v21 < 0 )
          {
            Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, LPVOID *, LPVOID *, int *))(**(_QWORD **)(v22 + 48 * v13 + 24) + 24LL))(
                         *(_QWORD *)(v22 + 48 * v13 + 24),
                         *(_QWORD *)(v22 + 48 * v13),
                         a1 + 32,
                         &pv,
                         &v44,
                         &v33);
            v28 = StorageCleanmgrProvider::Provider();
            if ( *(_DWORD *)v28 > 5u && (unsigned __int8)tlgKeywordOn(v28, 0x400000000000LL) )
            {
              v31 = *(_QWORD *)(a1 + 8);
              v35 = v33;
              v47 = a2;
              v45 = (const WCHAR *)(v14 + v31 + 8);
              v46 = Name;
              v36 = Instance;
              v34 = v13;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
                v29,
                (__int64)qword_1800A9B98,
                v29,
                v30,
                (__int64 *)&v45,
                (const WCHAR **)&v46,
                (__int64)&v34,
                (__int64)&v35,
                (__int64)&v36,
                &v47);
            }
            if ( Instance < 0 )
              goto LABEL_10;
          }
          else
          {
            Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, WCHAR *, LPVOID *, LPVOID *, LPVOID *, int *))(*(_QWORD *)v42 + 64LL))(
                         v42,
                         *(_QWORD *)(v22 + 48 * v13),
                         a1 + 32,
                         Name,
                         &pv,
                         &v44,
                         v48,
                         &v33);
            v23 = StorageCleanmgrProvider::Provider();
            v25 = (__int64)v23;
            if ( *(_DWORD *)v23 > 5u && (unsigned __int8)tlgKeywordOn(v23, 0x400000000000LL) )
            {
              v27 = *(_QWORD *)(a1 + 8);
              v35 = v33;
              v45 = a2;
              v47 = (const WCHAR *)(v14 + v27 + 8);
              v46 = Name;
              v34 = Instance;
              v36 = v13;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
                v25,
                (__int64)byte_1800A9A53,
                v25,
                v26,
                (__int64 *)&v47,
                (const WCHAR **)&v46,
                (__int64)&v36,
                (__int64)&v35,
                (__int64)&v34,
                &v45);
            }
            if ( Instance < 0 )
              goto LABEL_10;
            (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v42 + 16LL))(v42, v24, v25);
          }
          if ( pv )
            CoTaskMemFree(pv);
          if ( v44 )
            CoTaskMemFree(v44);
          if ( v48[0] )
            CoTaskMemFree(v48[0]);
          (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(*(_QWORD *)(a1 + 8) + v14 + 24) + 32LL))(
            *(_QWORD *)(*(_QWORD *)(a1 + 8) + v14 + 24),
            v14 + *(_QWORD *)(a1 + 8) + 32LL,
            *(_QWORD *)(a1 + 24));
        }
      }
      v13 = (unsigned int)(v13 + 1);
      if ( (unsigned int)v13 >= *v11 )
        goto LABEL_45;
    }
  }
  Instance = -2147024882;
LABEL_10:
  CleanMgrHelper::_CleanupPlugins((CleanMgrHelper *)a1);
LABEL_11:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180071578  mov     [rsp-8+arg_10], rbx
0x18007157d  push    rbp
0x18007157e  push    rsi
0x18007157f  push    rdi
0x180071580  push    r12
0x180071582  push    r13
0x180071584  push    r14
0x180071586  push    r15
0x180071588  lea     rbp, [rsp-400h]
0x180071590  sub     rsp, 500h
0x180071597  mov     rax, cs:__security_cookie
0x18007159e  xor     rax, rsp
0x1800715a1  mov     [rbp+430h+var_40], rax
0x1800715a8  mov     r12d, r8d
0x1800715ab  mov     [rbp+430h+hKey], 0
0x1800715b3  mov     r8, rdx; wchar_t *
0x1800715b6  mov     [rsp+530h+cchName], 0
0x1800715be  mov     r13, rdx
0x1800715c1  mov     [rsp+530h+cbData], 0
0x1800715c9  mov     rdi, rcx
0x1800715cc  mov     [rsp+530h+pvData], 0
0x1800715d4  mov     edx, 104h; unsigned __int64
0x1800715d9  mov     [rsp+530h+pcbData], 0
0x1800715e1  add     rcx, 20h ; ' '; wchar_t *
0x1800715e5  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800715ea  mov     ebx, eax
0x1800715ec  test    eax, eax
0x1800715ee  js      loc_180071715
0x1800715f4  call    IsOleInitializePresent
0x1800715f9  test    al, al
0x1800715fb  jnz     short loc_180071607
0x1800715fd  mov     eax, 80070032h
0x180071602  jmp     loc_18007172E
0x180071607  xor     ecx, ecx; pvReserved
0x180071609  call    cs:__imp_OleInitialize
0x18007160f  mov     ebx, eax
0x180071611  test    eax, eax
0x180071613  js      loc_180071715
0x180071619  mov     ebx, 1
0x18007161e  mov     [rdi+230h], ebx
0x180071624  lea     ecx, [rbx+0Fh]; Size
0x180071627  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007162c  mov     r9, rax
0x18007162f  lea     r8, [rdi+18h]
0x180071633  lea     rax, ??_7CleanMgrEmptyCallBack@@6B@; const CleanMgrEmptyCallBack::`vftable'
0x18007163a  lea     rdx, IID_IEmptyVolumeCacheCallBack
0x180071641  mov     [r9], rax
0x180071644  mov     [r9+8], ebx
0x180071648  mov     [rdi+228h], r9
0x18007164f  mov     rcx, [r9]
0x180071652  mov     rax, [rcx]
0x180071655  mov     rcx, r9
0x180071658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007165d  mov     ebx, eax
0x18007165f  test    eax, eax
0x180071661  js      loc_180071715
0x180071667  lea     rax, [rbp+430h+hKey]
0x18007166b  mov     r9d, 20019h; samDesired
0x180071671  xor     r8d, r8d; ulOptions
0x180071674  mov     [rsp+530h+phkResult], rax; phkResult
0x180071679  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180071680  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180071687  call    cs:__imp_RegOpenKeyExW
0x18007168d  mov     ebx, eax
0x18007168f  test    eax, eax
0x180071691  jnz     loc_180071B9A
0x180071697  mov     rcx, [rbp+430h+hKey]; hKey
0x18007169b  lea     r15, [rdi+10h]
0x18007169f  mov     [rsp+530h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800716a8  xor     r9d, r9d; lpReserved
0x1800716ab  mov     [rsp+530h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x1800716b4  xor     r8d, r8d; lpcchClass
0x1800716b7  mov     [rsp+530h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x1800716c0  xor     edx, edx; lpClass
0x1800716c2  mov     [rsp+530h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x1800716cb  mov     [rsp+530h+lpcValues], 0; lpcValues
0x1800716d4  mov     [rsp+530h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x1800716dd  mov     [rsp+530h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x1800716e6  mov     [rsp+530h+phkResult], r15; lpcSubKeys
0x1800716eb  call    cs:__imp_RegQueryInfoKeyW
0x1800716f1  mov     ebx, eax
0x1800716f3  test    eax, eax
0x1800716f5  jnz     loc_180071B9A
0x1800716fb  mov     ecx, [r15]; Count
0x1800716fe  lea     edx, [rax+30h]; Size
0x180071701  call    cs:__imp_calloc
0x180071707  mov     [rdi+8], rax
0x18007170b  test    rax, rax
0x18007170e  jnz     short loc_180071758
0x180071710  mov     ebx, 8007000Eh
0x180071715  mov     rcx, rdi; this
0x180071718  call    ?_CleanupPlugins@CleanMgrHelper@@AEAAXXZ; CleanMgrHelper::_CleanupPlugins(void)
0x18007171d  mov     rcx, [rbp+430h+hKey]; hKey
0x180071721  test    rcx, rcx
0x180071724  jz      short loc_18007172C
0x180071726  call    cs:__imp_RegCloseKey
0x18007172c  mov     eax, ebx
0x18007172e  mov     rcx, [rbp+430h+var_40]
0x180071735  xor     rcx, rsp; StackCookie
0x180071738  call    __security_check_cookie
0x18007173d  mov     rbx, [rsp+530h+arg_10]
0x180071745  add     rsp, 500h
0x18007174c  pop     r15
0x18007174e  pop     r14
0x180071750  pop     r13
0x180071752  pop     r12
0x180071754  pop     rdi
0x180071755  pop     rsi
0x180071756  pop     rbp
0x180071757  retn
0x180071758  xor     r14d, r14d
0x18007175b  cmp     [r15], r14d
0x18007175e  jbe     loc_180071B93
0x180071764  mov     rcx, [rbp+430h+hKey]; hKey
0x180071768  lea     r9, [rsp+530h+cchName]; lpcchName
0x18007176d  mov     [rsp+530h+lpcValues], 0; lpftLastWriteTime
0x180071776  lea     r8, [rbp+430h+Name]; lpName
0x18007177a  mov     [rsp+530h+lpcbMaxClassLen], 0; lpcchClass
0x180071783  mov     edx, r14d; dwIndex
0x180071786  mov     [rsp+530h+lpcbMaxSubKeyLen], 0; lpClass
0x18007178f  mov     [rsp+530h+phkResult], 0; lpReserved
0x180071798  mov     [rsp+530h+cchName], 105h
0x1800717a0  call    cs:__imp_RegEnumKeyExW
0x1800717a6  mov     ebx, eax
0x1800717a8  test    eax, eax
0x1800717aa  jnz     loc_180071B9A
0x1800717b0  lea     rdx, aThumbnailCache; "Thumbnail Cache"
0x1800717b7  lea     rcx, [rbp+430h+Name]; String1
0x1800717bb  call    wcscmp_0
0x1800717c0  test    eax, eax
0x1800717c2  jz      loc_180071B87
0x1800717c8  lea     rdx, aMicrosoftOffic; "Microsoft Office Temp Files"
0x1800717cf  lea     rcx, [rbp+430h+Name]; String1
0x1800717d3  call    wcscmp_0
0x1800717d8  test    eax, eax
0x1800717da  jz      loc_180071B87
0x1800717e0  mov     rcx, [rdi+8]
0x1800717e4  lea     rsi, [r14+r14*2]
0x1800717e8  shl     rsi, 4
0x1800717ec  lea     rdx, [rbp+430h+Name]; lpSubKey
0x1800717f0  add     rcx, rsi
0x1800717f3  mov     r9d, 20019h; samDesired
0x1800717f9  mov     [rsp+530h+phkResult], rcx; phkResult
0x1800717fe  xor     r8d, r8d; ulOptions
0x180071801  mov     rcx, [rbp+430h+hKey]; hKey
0x180071805  call    cs:__imp_RegOpenKeyExW
0x18007180b  mov     ebx, eax
0x18007180d  test    eax, eax
0x18007180f  jnz     loc_180071B9A
0x180071815  mov     rcx, [rdi+8]
0x180071819  lea     rax, [rsp+530h+cbData]
0x18007181e  mov     [rsp+530h+lpcbMaxSubKeyLen], rax; lpcbData
0x180071823  lea     r9, [rbp+430h+Type]; lpType
0x180071827  mov     [rsp+530h+cbData], 105h
0x18007182f  lea     rax, [rbp+430h+Data]
0x180071836  mov     [rbp+430h+Type], 1
0x18007183d  xor     r8d, r8d; lpReserved
0x180071840  mov     rcx, [rcx+rsi]; hKey
0x180071844  xor     edx, edx; lpValueName
0x180071846  mov     [rsp+530h+phkResult], rax; lpData
0x18007184b  call    cs:__imp_RegQueryValueExW
0x180071851  mov     ebx, eax
0x180071853  test    eax, eax
0x180071855  jnz     loc_180071B9A
0x18007185b  mov     rdx, [rdi+8]
0x18007185f  lea     rcx, [rbp+430h+Data]; lpsz
0x180071866  add     rdx, 8
0x18007186a  add     rdx, rsi; pclsid
0x18007186d  call    cs:__imp_CLSIDFromString
0x180071873  mov     ebx, eax
0x180071875  test    eax, eax
0x180071877  js      loc_180071715
0x18007187d  mov     rcx, [rdi+8]
0x180071881  lea     rax, [rsp+530h+pcbData]
0x180071886  mov     [rsp+530h+lpcbMaxClassLen], rax; pcbData
0x18007188b  lea     r8, aPlugintype; "PluginType"
0x180071892  lea     rax, [rsp+530h+pvData]
0x180071897  mov     [rsp+530h+pcbData], 4
0x18007189f  mov     [rsp+530h+pvData], 0
0x1800718a7  mov     r9d, 18h; dwFlags
0x1800718ad  mov     rcx, [rcx+rsi]; hkey
0x1800718b1  xor     edx, edx; lpSubKey
0x1800718b3  mov     [rsp+530h+lpcbMaxSubKeyLen], rax; pvData
0x1800718b8  mov     [rsp+530h+phkResult], 0; pdwType
0x1800718c1  call    cs:__imp_RegGetValueW
0x1800718c7  mov     ecx, [rsp+530h+pvData]
0x1800718cb  test    eax, eax
0x1800718cd  jnz     short loc_1800718E0
0x1800718cf  cmp     ecx, 3
0x1800718d2  ja      short loc_1800718E0
0x1800718d4  mov     rax, [rdi+8]
0x1800718d8  mov     [rax+rsi+28h], ecx
0x1800718dc  mov     ecx, [rsp+530h+pvData]
0x1800718e0  cmp     r12d, 4
0x1800718e4  jz      short loc_1800718EF
0x1800718e6  cmp     ecx, r12d
0x1800718e9  jnz     loc_180071B87
0x1800718ef  mov     rcx, [rdi+8]
0x1800718f3  lea     r9, IID_IEmptyVolumeCache; riid
0x1800718fa  xor     edx, edx; pUnkOuter
0x1800718fc  mov     [rsp+530h+var_4CC], 80h
0x180071904  lea     rax, [rcx+18h]
0x180071908  add     rcx, 8
0x18007190c  add     rax, rsi
0x18007190f  lea     r8d, [rdx+1]; dwClsContext
0x180071913  add     rcx, rsi; rclsid
0x180071916  mov     [rsp+530h+phkResult], rax; ppv
0x18007191b  call    cs:__imp_CoCreateInstance
0x180071921  mov     ebx, eax
0x180071923  test    eax, eax
0x180071925  js      loc_180071715
0x18007192b  mov     rax, [rdi+8]
0x18007192f  lea     r8, [rbp+430h+var_4A0]
0x180071933  xor     ebx, ebx
0x180071935  lea     rdx, IID_IEmptyVolumeCache2
0x18007193c  mov     [rbp+430h+var_4A0], rbx
0x180071940  mov     rcx, [rax+rsi+18h]
0x180071945  mov     rax, [rcx]
0x180071948  mov     rax, [rax]
0x18007194b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071950  mov     rdx, [rdi+8]
0x180071954  lea     r8, [rsp+530h+var_4CC]
0x180071959  mov     [rbp+430h+pv], rbx
0x18007195d  mov     [rbp+430h+var_490], rbx
0x180071961  mov     [rbp+430h+var_470], rbx
0x180071965  test    eax, eax
0x180071967  js      loc_180071A65
0x18007196d  mov     rcx, [rbp+430h+var_4A0]
0x180071971  lea     r9, [rbp+430h+Name]
0x180071975  mov     rdx, [rdx+rsi]
0x180071979  mov     [rsp+530h+lpcValues], r8
0x18007197e  lea     r8, [rbp+430h+var_470]
0x180071982  mov     [rsp+530h+lpcbMaxClassLen], r8
0x180071987  lea     r8, [rbp+430h+var_490]
0x18007198b  mov     rax, [rcx]
0x18007198e  mov     [rsp+530h+lpcbMaxSubKeyLen], r8
0x180071993  lea     r8, [rbp+430h+pv]
0x180071997  mov     [rsp+530h+phkResult], r8
0x18007199c  lea     r8, [rdi+20h]
0x1800719a0  mov     rax, [rax+40h]
0x1800719a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800719a9  mov     ebx, eax
0x1800719ab  call    ?Provider@StorageCleanmgrProvider@@SAPEBU_tlgProvider_t@@XZ; StorageCleanmgrProvider::Provider(void)
0x1800719b0  mov     r8, rax
0x1800719b3  mov     ecx, [rax]
0x1800719b5  cmp     ecx, 5
0x1800719b8  jbe     loc_180071A48
0x1800719be  mov     rdx, 400000000000h
0x1800719c8  mov     rcx, rax
0x1800719cb  call    _tlgKeywordOn
0x1800719d0  test    al, al
0x1800719d2  jz      short loc_180071A48
0x1800719d4  mov     eax, [rsp+530h+var_4CC]
0x1800719d8  lea     rdx, byte_1800A9A53
0x1800719df  mov     rcx, [rdi+8]
0x1800719e3  mov     [rsp+530h+var_4C4], eax
0x1800719e7  add     rcx, 8
0x1800719eb  add     rcx, rsi
0x1800719ee  mov     [rbp+430h+var_488], r13
0x1800719f2  lea     rax, [rbp+430h+Name]
0x1800719f6  mov     [rbp+430h+var_478], rcx
0x1800719fa  mov     [rbp+430h+var_480], rax
0x1800719fe  mov     rcx, r8
0x180071a01  lea     rax, [rbp+430h+var_488]
0x180071a05  mov     [rsp+530h+var_4C8], ebx
0x180071a09  mov     [rsp+530h+lpcbMaxValueLen], rax
0x180071a0e  lea     rax, [rsp+530h+var_4C8]
0x180071a13  mov     [rsp+530h+lpcbMaxValueNameLen], rax
0x180071a18  lea     rax, [rsp+530h+var_4C4]
0x180071a1d  mov     [rsp+530h+lpcValues], rax
0x180071a22  lea     rax, [rsp+530h+var_4C0]
0x180071a27  mov     [rsp+530h+lpcbMaxClassLen], rax
0x180071a2c  lea     rax, [rbp+430h+var_480]
0x180071a30  mov     [rsp+530h+lpcbMaxSubKeyLen], rax
0x180071a35  lea     rax, [rbp+430h+var_478]
0x180071a39  mov     [rsp+530h+phkResult], rax
0x180071a3e  mov     [rsp+530h+var_4C0], r14d
0x180071a43  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@554@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180071a48  test    ebx, ebx
0x180071a4a  js      loc_180071715
0x180071a50  mov     rcx, [rbp+430h+var_4A0]
0x180071a54  mov     rax, [rcx]
0x180071a57  mov     rax, [rax+10h]
0x180071a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071a60  jmp     loc_180071B37
0x180071a65  mov     rcx, [rdx+rsi+18h]
0x180071a6a  lea     r9, [rbp+430h+pv]
0x180071a6e  mov     rdx, [rdx+rsi]
0x180071a72  mov     [rsp+530h+lpcbMaxSubKeyLen], r8
0x180071a77  lea     r8, [rbp+430h+var_490]
0x180071a7b  mov     [rsp+530h+phkResult], r8
0x180071a80  lea     r8, [rdi+20h]
0x180071a84  mov     rax, [rcx]
0x180071a87  mov     rax, [rax+18h]
0x180071a8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071a90  mov     ebx, eax
0x180071a92  call    ?Provider@StorageCleanmgrProvider@@SAPEBU_tlgProvider_t@@XZ; StorageCleanmgrProvider::Provider(void)
0x180071a97  mov     r8, rax
0x180071a9a  mov     ecx, [rax]
0x180071a9c  cmp     ecx, 5
  ... truncated ...
```
