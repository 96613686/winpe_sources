# CDelegateFolderBaseNoUI::GetUIObjectOf(HWND__ *,uint,_ITEMID_CHILD const * const *,_GUID const &,uint *,void * *)

- ea: `0x180050350`
- end: `0x180050540`
- name: `?GetUIObjectOf@CDelegateFolderBaseNoUI@@UEAAJPEAUHWND__@@IPEBQEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAIPEAPEAX@Z`
- size: `496`
- prototype: `__int64 __fastcall(CDelegateFolderBaseNoUI *__hidden this, HWND, unsigned int, const struct _ITEMID_CHILD *const *, const struct _GUID *, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180007f44`
- `0x180050244`
- `0x180050350`
- `0x180052950`
- `0x180053010`

## import_xrefs

- `SHELL32!SHCreateDefaultExtractIcon` at `0x18005045f`
- `SHELL32!SHCreateDefaultExtractIcon` at `0x18005045f`
- `SHLWAPI!__imp_SHRegGetCLSIDKey` at `0x18005043c`
- `SHLWAPI!__imp_SHRegGetCLSIDKey` at `0x18005043c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050500`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050500`

## pseudocode

```c
__int64 __fastcall CDelegateFolderBaseNoUI::GetUIObjectOf(
        CDelegateFolderBaseNoUI *this,
        HWND a2,
        int a3,
        const struct _ITEMID_CHILD *const *a4,
        const struct _GUID *a5,
        unsigned int *a6,
        void **a7)
{
  __int64 v8; // rcx
  HRESULT PropertyStorageFromIDList; // ebx
  __int64 v10; // rax
  void *ppv; // [rsp+30h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-28h] BYREF
  __int64 v14; // [rsp+40h] [rbp-20h] BYREF
  __int128 v15; // [rsp+48h] [rbp-18h] BYREF

  *a7 = 0;
  if ( a3 == 1
    && (*(_QWORD *)&a5->Data1 == *(_QWORD *)&IID_IExtractIconA.Data1
     && *(_QWORD *)a5->Data4 == *(_QWORD *)IID_IExtractIconA.Data4
     || *(_QWORD *)&a5->Data1 == *(_QWORD *)&IID_IExtractIconW.Data1
     && *(_QWORD *)a5->Data4 == *(_QWORD *)IID_IExtractIconW.Data4) )
  {
    v8 = (__int64)*a4;
    v14 = 0;
    PropertyStorageFromIDList = CItemIDFactory<DELEGATEBASEITEM,597942229>::GetPropertyStorageFromIDList(
                                  v8,
                                  &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
                                  &v14);
    if ( PropertyStorageFromIDList >= 0 )
    {
      v10 = *((_QWORD *)this - 1);
      v15 = 0;
      PropertyStorageFromIDList = (*(__int64 (__fastcall **)(char *, __int128 *, __int64))(v10 + 48))(
                                    (char *)this - 8,
                                    &v15,
                                    v14);
      if ( PropertyStorageFromIDList >= 0 )
      {
        hKey = 0;
        PropertyStorageFromIDList = SHRegGetCLSIDKey(&v15, 0, 0, 0, 131097, &hKey);
        if ( PropertyStorageFromIDList >= 0 )
        {
          ppv = 0;
          PropertyStorageFromIDList = SHCreateDefaultExtractIcon(&GUID_41ded17d_d6b3_4261_997d_88c60e4b1d58, &ppv);
          if ( PropertyStorageFromIDList >= 0 )
          {
            PropertyStorageFromIDList = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 2);
            if ( PropertyStorageFromIDList >= 0 )
            {
              PropertyStorageFromIDList = (*(__int64 (__fastcall **)(void *, HKEY))(*(_QWORD *)ppv + 32LL))(ppv, hKey);
              if ( PropertyStorageFromIDList >= 0 )
              {
                PropertyStorageFromIDList = (*(__int64 (__fastcall **)(void *, _QWORD, __int64))(*(_QWORD *)ppv + 40LL))(
                                              ppv,
                                              0,
                                              3);
                if ( PropertyStorageFromIDList >= 0 )
                {
                  PropertyStorageFromIDList = (*(__int64 (__fastcall **)(void *, _QWORD, __int64))(*(_QWORD *)ppv + 48LL))(
                                                ppv,
                                                0,
                                                4);
                  if ( PropertyStorageFromIDList >= 0 )
                    PropertyStorageFromIDList = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, void **))ppv)(
                                                  ppv,
                                                  a5,
                                                  a7);
                }
              }
            }
          }
          SafeRelease<ISyncMgrSyncItemContainer>((__int64 *)&ppv);
          RegCloseKey(hKey);
        }
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
  }
  else
  {
    return (unsigned int)-2147467262;
  }
  return (unsigned int)PropertyStorageFromIDList;
}

```

## disassembly

```asm
0x180050350  mov     [rsp-18h+arg_8], rbx
0x180050355  mov     [rsp-18h+arg_10], rsi
0x18005035a  push    rbp
0x18005035b  push    rdi
0x18005035c  push    r14
0x18005035e  mov     rbp, rsp
0x180050361  sub     rsp, 60h
0x180050365  mov     rax, cs:__security_cookie
0x18005036c  xor     rax, rsp
0x18005036f  mov     [rbp+var_8], rax
0x180050373  mov     r14, [rbp+arg_30]
0x180050377  mov     rsi, rcx
0x18005037a  mov     rdi, [rbp+arg_20]
0x18005037e  mov     qword ptr [r14], 0
0x180050385  cmp     r8d, 1
0x180050389  jnz     loc_180050518
0x18005038f  mov     rax, [rdi]
0x180050392  cmp     rax, qword ptr cs:IID_IExtractIconA.Data1
0x180050399  jnz     short loc_1800503A8
0x18005039b  mov     rax, [rdi+8]
0x18005039f  cmp     rax, qword ptr cs:IID_IExtractIconA.Data4
0x1800503a6  jz      short loc_1800503C9
0x1800503a8  mov     rax, [rdi]
0x1800503ab  cmp     rax, qword ptr cs:IID_IExtractIconW.Data1
0x1800503b2  jnz     loc_180050518
0x1800503b8  mov     rax, [rdi+8]
0x1800503bc  cmp     rax, qword ptr cs:IID_IExtractIconW.Data4
0x1800503c3  jnz     loc_180050518
0x1800503c9  mov     rcx, [r9]
0x1800503cc  lea     r8, [rbp+var_20]
0x1800503d0  lea     rdx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851
0x1800503d7  mov     [rbp+var_20], 0
0x1800503df  call    ?GetPropertyStorageFromIDList@?$CItemIDFactory@UDELEGATEBASEITEM@@$0CDKDNPNF@@@SAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_GUID@@PEAPEAX@Z; CItemIDFactory<DELEGATEBASEITEM,597942229>::GetPropertyStorageFromIDList(_ITEMIDLIST_RELATIVE const *,_GUID const &,void * *)
0x1800503e4  mov     ebx, eax
0x1800503e6  test    eax, eax
0x1800503e8  js      loc_18005051D
0x1800503ee  mov     r8, [rbp+var_20]
0x1800503f2  lea     rcx, [rsi-8]
0x1800503f6  mov     rax, [rcx]
0x1800503f9  lea     rdx, [rbp+var_18]
0x1800503fd  xorps   xmm0, xmm0
0x180050400  movups  [rbp+var_18], xmm0
0x180050404  mov     rax, [rax+30h]
0x180050408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005040d  mov     ebx, eax
0x18005040f  test    eax, eax
0x180050411  js      loc_180050506
0x180050417  lea     rax, [rbp+hKey]
0x18005041b  mov     [rbp+hKey], 0
0x180050423  mov     [rsp+60h+var_38], rax
0x180050428  lea     rcx, [rbp+var_18]
0x18005042c  xor     r9d, r9d
0x18005042f  mov     [rsp+60h+var_40], 20019h
0x180050437  xor     r8d, r8d
0x18005043a  xor     edx, edx
0x18005043c  call    cs:__imp_SHRegGetCLSIDKey
0x180050442  mov     ebx, eax
0x180050444  test    eax, eax
0x180050446  js      loc_180050506
0x18005044c  lea     rdx, [rbp+ppv]; ppv
0x180050450  mov     [rbp+ppv], 0
0x180050458  lea     rcx, _GUID_41ded17d_d6b3_4261_997d_88c60e4b1d58; riid
0x18005045f  call    cs:__imp_SHCreateDefaultExtractIcon
0x180050465  mov     ebx, eax
0x180050467  test    eax, eax
0x180050469  js      loc_1800504F3
0x18005046f  mov     rcx, [rbp+ppv]
0x180050473  mov     edx, 2
0x180050478  mov     rax, [rcx]
0x18005047b  mov     rax, [rax+18h]
0x18005047f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050484  mov     ebx, eax
0x180050486  test    eax, eax
0x180050488  js      short loc_1800504F3
0x18005048a  mov     rcx, [rbp+ppv]
0x18005048e  mov     rdx, [rbp+hKey]
0x180050492  mov     rax, [rcx]
0x180050495  mov     rax, [rax+20h]
0x180050499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005049e  mov     ebx, eax
0x1800504a0  test    eax, eax
0x1800504a2  js      short loc_1800504F3
0x1800504a4  mov     rcx, [rbp+ppv]
0x1800504a8  xor     edx, edx
0x1800504aa  mov     rax, [rcx]
0x1800504ad  lea     r8d, [rdx+3]
0x1800504b1  mov     rax, [rax+28h]
0x1800504b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800504ba  mov     ebx, eax
0x1800504bc  test    eax, eax
0x1800504be  js      short loc_1800504F3
0x1800504c0  mov     rcx, [rbp+ppv]
0x1800504c4  xor     edx, edx
0x1800504c6  mov     rax, [rcx]
0x1800504c9  lea     r8d, [rdx+4]
0x1800504cd  mov     rax, [rax+30h]
0x1800504d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800504d6  mov     ebx, eax
0x1800504d8  test    eax, eax
0x1800504da  js      short loc_1800504F3
0x1800504dc  mov     rcx, [rbp+ppv]
0x1800504e0  mov     r8, r14
0x1800504e3  mov     rdx, rdi
0x1800504e6  mov     rax, [rcx]
0x1800504e9  mov     rax, [rax]
0x1800504ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800504f1  mov     ebx, eax
0x1800504f3  lea     rcx, [rbp+ppv]
0x1800504f7  call    ??$SafeRelease@UISyncMgrSyncItemContainer@@@@YAXPEAPEAUISyncMgrSyncItemContainer@@@Z; SafeRelease<ISyncMgrSyncItemContainer>(ISyncMgrSyncItemContainer * *)
0x1800504fc  mov     rcx, [rbp+hKey]; hKey
0x180050500  call    cs:__imp_RegCloseKey
0x180050506  mov     rcx, [rbp+var_20]
0x18005050a  mov     rax, [rcx]
0x18005050d  mov     rax, [rax+10h]
0x180050511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050516  jmp     short loc_18005051D
0x180050518  mov     ebx, 80004002h
0x18005051d  mov     eax, ebx
0x18005051f  mov     rcx, [rbp+var_8]
0x180050523  xor     rcx, rsp; StackCookie
0x180050526  call    __security_check_cookie
0x18005052b  lea     r11, [rsp+60h+var_s0]
0x180050530  mov     rbx, [r11+28h]
0x180050534  mov     rsi, [r11+30h]
0x180050538  mov     rsp, r11
0x18005053b  pop     r14
0x18005053d  pop     rdi
0x18005053e  pop     rbp
0x18005053f  retn
```
