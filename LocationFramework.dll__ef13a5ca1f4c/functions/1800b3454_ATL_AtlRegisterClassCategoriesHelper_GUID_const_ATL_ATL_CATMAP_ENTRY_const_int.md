# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x1800b3454`
- end: `0x1800b378c`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `824`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800bb7b4`
- `0x1800bd064`

## callees

- `0x180012398`
- `0x180018d78`
- `0x18002d4b0`
- `0x18004b560`
- `0x18004ec04`
- `0x18005013c`
- `0x1800a98c0`
- `0x1800b3454`
- `0x1800b7ef0`
- `0x18015e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800b3596`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800b35b0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800b3693`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800b36ae`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800b3596`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800b35b0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800b3693`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800b36ae`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800b357c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800b3678`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800b357c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800b3678`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800b363b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800b370c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800b363b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800b370c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b34da`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b34da`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800b3560`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800b3560`

## string_xrefs

- `0x1800b3571`: `CLSID\`
- `0x1800b366a`: `CLSID\`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *a2, int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // edi
  int v9; // eax
  int v10; // eax
  int v11; // eax
  HKEY v12; // rdi
  LSTATUS v13; // ebx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  LSTATUS v17; // ebx
  HKEY hKey[3]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v20[3]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v21; // [rsp+90h] [rbp-70h] BYREF
  DWORD cSubKeys; // [rsp+98h] [rbp-68h] BYREF
  LPVOID ppv; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v24; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 v25[128]; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR sz[64]; // [rsp+1C0h] [rbp+C0h] BYREF

  ppv = 0;
  v4 = a2;
  v24 = 0;
  if ( a2
    && !(unsigned int)InlineIsEqualGUID(rguid, &GUID_NULL)
    && CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &GUID_0002e012_0000_0000_c000_000000000046, &ppv) >= 0 )
  {
    while ( *(_DWORD *)v4 )
    {
      v24 = *(_OWORD *)*((_QWORD *)v4 + 1);
      v6 = *(_QWORD *)ppv;
      if ( a3 )
      {
        if ( *(_DWORD *)v4 == 1 )
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 40))(ppv, rguid, 1, &v24);
        else
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 56))(ppv, rguid, 1, &v24);
        v8 = v7;
        if ( v7 < 0 )
          goto LABEL_26;
      }
      else if ( *(_DWORD *)v4 == 1 )
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 48))(ppv, rguid, 1, &v24);
      }
      else
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 64))(ppv, rguid, 1, &v24);
      }
      v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
    }
    if ( !a3 )
    {
      StringFromGUID2(rguid, sz, 64);
      v21 = 0;
      v9 = _o_wcscpy_s(v25, 128, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v9);
      v10 = _o_wcscat_s(v25, 128, sz);
      ATL::AtlCrtErrorCheck(v10);
      v11 = _o_wcscat_s(v25, 128, L"\\Required Categories");
      ATL::AtlCrtErrorCheck(v11);
      v12 = HKEY_CLASSES_ROOT;
      v20[1] = 0;
      v20[0] = 0xFFFFFFFF80000000uLL;
      v20[2] = 0;
      memset(hKey, 0, sizeof(hKey));
      cSubKeys = 0;
      if ( !ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, v25, 0x20019u) )
      {
        v13 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v13 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v20, v25);
          v12 = (HKEY)v20[0];
        }
      }
      v14 = _o_wcscpy_s(v25, 128, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v14);
      v15 = _o_wcscat_s(v25, 128, sz);
      ATL::AtlCrtErrorCheck(v15);
      v16 = _o_wcscat_s(v25, 128, L"\\Implemented Categories");
      ATL::AtlCrtErrorCheck(v16);
      if ( !ATL::CRegKey::Open((ATL::CRegKey *)hKey, v12, v25, 0x20019u) )
      {
        v17 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v17 && !cSubKeys )
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v20, v25);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
      ATL::CRegKey::Close((ATL::CRegKey *)v20);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v21);
    }
  }
  v8 = 0;
LABEL_26:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return v8;
}

```

## disassembly

```asm
0x1800b3454  mov     [rsp-8+arg_10], rbx
0x1800b3459  mov     [rsp-8+arg_18], rsi
0x1800b345e  push    rbp
0x1800b345f  push    rdi
0x1800b3460  push    r12
0x1800b3462  push    r14
0x1800b3464  push    r15
0x1800b3466  lea     rbp, [rsp-150h]
0x1800b346e  sub     rsp, 250h
0x1800b3475  mov     rax, cs:__security_cookie
0x1800b347c  xor     rax, rsp
0x1800b347f  mov     [rbp+170h+var_30], rax
0x1800b3486  xor     r15d, r15d
0x1800b3489  xorps   xmm0, xmm0
0x1800b348c  mov     [rbp+170h+var_1D0], r15
0x1800b3490  mov     r14d, r8d
0x1800b3493  mov     rbx, rdx
0x1800b3496  mov     rsi, rcx
0x1800b3499  movups  [rbp+170h+var_1C8], xmm0
0x1800b349d  test    rdx, rdx
0x1800b34a0  jz      loc_1800B3753
0x1800b34a6  lea     rdx, GUID_NULL; struct _GUID *
0x1800b34ad  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x1800b34b2  test    eax, eax
0x1800b34b4  jnz     loc_1800B3753
0x1800b34ba  lea     rax, [rbp+170h+var_1D0]
0x1800b34be  xor     edx, edx; pUnkOuter
0x1800b34c0  lea     r12d, [r15+1]
0x1800b34c4  mov     [rsp+270h+ppv], rax; ppv
0x1800b34c9  mov     r8d, r12d; dwClsContext
0x1800b34cc  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x1800b34d3  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x1800b34da  call    cs:__imp_CoCreateInstance
0x1800b34e0  test    eax, eax
0x1800b34e2  js      loc_1800B3753
0x1800b34e8  cmp     [rbx], r15d
0x1800b34eb  jz      short loc_1800B3549
0x1800b34ed  mov     rax, [rbx+8]
0x1800b34f1  lea     r9, [rbp+170h+var_1C8]
0x1800b34f5  mov     rcx, [rbp+170h+var_1D0]
0x1800b34f9  mov     r8d, r12d
0x1800b34fc  mov     rdx, rsi
0x1800b34ff  movups  xmm0, xmmword ptr [rax]
0x1800b3502  movdqu  [rbp+170h+var_1C8], xmm0
0x1800b3507  mov     rax, [rcx]
0x1800b350a  test    r14d, r14d
0x1800b350d  jz      short loc_1800B352F
0x1800b350f  cmp     [rbx], r12d
0x1800b3512  jnz     short loc_1800B351A
0x1800b3514  mov     rax, [rax+28h]
0x1800b3518  jmp     short loc_1800B351E
0x1800b351a  mov     rax, [rax+38h]
0x1800b351e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3523  mov     edi, eax
0x1800b3525  test    eax, eax
0x1800b3527  js      loc_1800B3756
0x1800b352d  jmp     short loc_1800B3543
0x1800b352f  cmp     [rbx], r12d
0x1800b3532  jnz     short loc_1800B353A
0x1800b3534  mov     rax, [rax+30h]
0x1800b3538  jmp     short loc_1800B353E
0x1800b353a  mov     rax, [rax+40h]
0x1800b353e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3543  add     rbx, 10h
0x1800b3547  jmp     short loc_1800B34E8
0x1800b3549  test    r14d, r14d
0x1800b354c  jnz     loc_1800B3753
0x1800b3552  lea     r8d, [r14+40h]; cchMax
0x1800b3556  mov     rcx, rsi; rguid
0x1800b3559  lea     rdx, [rbp+170h+sz]; lpsz
0x1800b3560  call    cs:__imp_StringFromGUID2
0x1800b3566  mov     esi, 80h
0x1800b356b  mov     [rbp+170h+var_1E0], r15
0x1800b356f  mov     edx, esi
0x1800b3571  lea     r8, aClsid; "CLSID\\"
0x1800b3578  lea     rcx, [rbp+170h+var_1B0]
0x1800b357c  call    cs:__imp__o_wcscpy_s
0x1800b3582  mov     ecx, eax; int
0x1800b3584  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800b3589  lea     r8, [rbp+170h+sz]
0x1800b3590  mov     edx, esi
0x1800b3592  lea     rcx, [rbp+170h+var_1B0]
0x1800b3596  call    cs:__imp__o_wcscat_s
0x1800b359c  mov     ecx, eax; int
0x1800b359e  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800b35a3  lea     r8, aRequiredCatego; "\\Required Categories"
0x1800b35aa  mov     edx, esi
0x1800b35ac  lea     rcx, [rbp+170h+var_1B0]
0x1800b35b0  call    cs:__imp__o_wcscat_s
0x1800b35b6  mov     ecx, eax; int
0x1800b35b8  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800b35bd  mov     rdi, 0FFFFFFFF80000000h
0x1800b35c4  mov     [rbp+170h+var_1F0], r15
0x1800b35c8  mov     r14d, 20019h
0x1800b35ce  mov     [rsp+270h+var_1F8], rdi
0x1800b35d3  mov     r9d, r14d; unsigned int
0x1800b35d6  mov     [rbp+170h+var_1E8], r15
0x1800b35da  mov     rdx, rdi; HKEY
0x1800b35dd  mov     [rsp+270h+hKey], r15
0x1800b35e2  lea     r8, [rbp+170h+var_1B0]; unsigned __int16 *
0x1800b35e6  mov     [rsp+270h+var_208], r15
0x1800b35eb  lea     rcx, [rsp+270h+hKey]; this
0x1800b35f0  mov     [rsp+270h+var_200], r15
0x1800b35f5  mov     [rbp+170h+cSubKeys], r15d
0x1800b35f9  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800b35fe  test    eax, eax
0x1800b3600  jnz     short loc_1800B366A
0x1800b3602  mov     rcx, [rsp+270h+hKey]; hKey
0x1800b3607  lea     rax, [rbp+170h+cSubKeys]
0x1800b360b  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800b3610  xor     r9d, r9d; lpReserved
0x1800b3613  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800b3618  xor     r8d, r8d; lpcchClass
0x1800b361b  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800b3620  xor     edx, edx; lpClass
0x1800b3622  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800b3627  mov     [rsp+270h+lpcValues], r15; lpcValues
0x1800b362c  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800b3631  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800b3636  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x1800b363b  call    cs:__imp_RegQueryInfoKeyW
0x1800b3641  lea     rcx, [rsp+270h+hKey]; this
0x1800b3646  mov     ebx, eax
0x1800b3648  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800b364d  test    ebx, ebx
0x1800b364f  jnz     short loc_1800B366A
0x1800b3651  cmp     [rbp+170h+cSubKeys], r15d
0x1800b3655  jnz     short loc_1800B366A
0x1800b3657  lea     rdx, [rbp+170h+var_1B0]; unsigned __int16 *
0x1800b365b  lea     rcx, [rsp+270h+var_1F8]; this
0x1800b3660  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800b3665  mov     rdi, [rsp+270h+var_1F8]
0x1800b366a  lea     r8, aClsid; "CLSID\\"
0x1800b3671  mov     rdx, rsi
0x1800b3674  lea     rcx, [rbp+170h+var_1B0]
0x1800b3678  call    cs:__imp__o_wcscpy_s
0x1800b367e  mov     ecx, eax; int
0x1800b3680  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800b3685  lea     r8, [rbp+170h+sz]
0x1800b368c  mov     rdx, rsi
0x1800b368f  lea     rcx, [rbp+170h+var_1B0]
0x1800b3693  call    cs:__imp__o_wcscat_s
0x1800b3699  mov     ecx, eax; int
0x1800b369b  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800b36a0  lea     r8, aImplementedCat; "\\Implemented Categories"
0x1800b36a7  mov     rdx, rsi
0x1800b36aa  lea     rcx, [rbp+170h+var_1B0]
0x1800b36ae  call    cs:__imp__o_wcscat_s
0x1800b36b4  mov     ecx, eax; int
0x1800b36b6  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800b36bb  mov     r9d, r14d; unsigned int
0x1800b36be  lea     r8, [rbp+170h+var_1B0]; unsigned __int16 *
0x1800b36c2  mov     rdx, rdi; HKEY
0x1800b36c5  lea     rcx, [rsp+270h+hKey]; this
0x1800b36ca  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800b36cf  test    eax, eax
0x1800b36d1  jnz     short loc_1800B3736
0x1800b36d3  mov     rcx, [rsp+270h+hKey]; hKey
0x1800b36d8  lea     rax, [rbp+170h+cSubKeys]
0x1800b36dc  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800b36e1  xor     r9d, r9d; lpReserved
0x1800b36e4  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800b36e9  xor     r8d, r8d; lpcchClass
0x1800b36ec  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800b36f1  xor     edx, edx; lpClass
0x1800b36f3  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800b36f8  mov     [rsp+270h+lpcValues], r15; lpcValues
0x1800b36fd  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800b3702  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800b3707  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x1800b370c  call    cs:__imp_RegQueryInfoKeyW
0x1800b3712  lea     rcx, [rsp+270h+hKey]; this
0x1800b3717  mov     ebx, eax
0x1800b3719  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800b371e  test    ebx, ebx
0x1800b3720  jnz     short loc_1800B3736
0x1800b3722  cmp     [rbp+170h+cSubKeys], r15d
0x1800b3726  jnz     short loc_1800B3736
0x1800b3728  lea     rdx, [rbp+170h+var_1B0]; unsigned __int16 *
0x1800b372c  lea     rcx, [rsp+270h+var_1F8]; this
0x1800b3731  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800b3736  lea     rcx, [rsp+270h+hKey]; this
0x1800b373b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800b3740  lea     rcx, [rsp+270h+var_1F8]; this
0x1800b3745  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800b374a  lea     rcx, [rbp+170h+var_1E0]
0x1800b374e  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800b3753  mov     edi, r15d
0x1800b3756  lea     rcx, [rbp+170h+var_1D0]
0x1800b375a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800b375f  mov     eax, edi
0x1800b3761  mov     rcx, [rbp+170h+var_30]
0x1800b3768  xor     rcx, rsp; StackCookie
0x1800b376b  call    __security_check_cookie
0x1800b3770  lea     r11, [rsp+270h+var_20]
0x1800b3778  mov     rbx, [r11+40h]
0x1800b377c  mov     rsi, [r11+48h]
0x1800b3780  mov     rsp, r11
0x1800b3783  pop     r15
0x1800b3785  pop     r14
0x1800b3787  pop     r12
0x1800b3789  pop     rdi
0x1800b378a  pop     rbp
0x1800b378b  retn
```
