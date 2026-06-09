# wpc::AppLimits::AppInventory::AppInventoryStorage::WriteAppInfoForUser(Sid const &,wpc::AppLimits::AppInventory::AppInfo const &)

- ea: `0x180018d94`
- end: `0x180019292`
- name: `?WriteAppInfoForUser@AppInventoryStorage@AppInventory@AppLimits@wpc@@SAXAEBVSid@@AEBUAppInfo@234@@Z`
- size: `1278`
- prototype: `void __fastcall(const struct Sid *, const struct wpc::AppLimits::AppInventory::AppInfo *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x180016974`

## callees

- `0x1800032a0`
- `0x180005950`
- `0x180005a04`
- `0x180005f9c`
- `0x180018d94`
- `0x180024fa4`
- `0x18002c010`

## string_xrefs

- `0x1800191ac`: `LastUpdatedTime`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
void __fastcall wpc::AppLimits::AppInventory::AppInventoryStorage::WriteAppInfoForUser(
        const struct Sid *a1,
        const struct wpc::AppLimits::AppInventory::AppInfo *a2)
{
  _QWORD *v4; // rbx
  __int64 (__fastcall *v5)(_QWORD *, __int64 *, __int128 *); // rdi
  unsigned __int64 v6; // r8
  _QWORD *v7; // rax
  __int64 (__fastcall ****v8)(_QWORD, __int64 *, char **); // rax
  __int64 (__fastcall ***v9)(_QWORD, __int64 *, char **); // rdi
  __int64 (__fastcall *v10)(_QWORD, __int64 *, char **); // rbx
  _QWORD *v11; // rax
  void (__fastcall ***v12)(_QWORD, __int64); // rcx
  void (__fastcall ***v13)(_QWORD, __int64); // rcx
  void (__fastcall ***v14)(_QWORD, __int64); // rcx
  volatile signed __int32 *v15; // rbx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64 *, char **); // rbx
  _QWORD *v18; // rax
  void (__fastcall ***v19)(_QWORD, __int64); // rcx
  char *v20; // rdi
  __int64 (__fastcall *v21)(char *, __int64 *, __int128 *); // rbx
  _QWORD *v22; // rax
  void (__fastcall ***v23)(_QWORD, __int64); // rcx
  char *v24; // rdi
  __int64 (__fastcall *v25)(char *, __int64 *, __int128 *); // rbx
  _QWORD *v26; // rax
  void (__fastcall ***v27)(_QWORD, __int64); // rcx
  char *v28; // rdi
  __int64 (__fastcall *v29)(char *, __int64 *, __int128 *); // rbx
  _QWORD *v30; // rax
  void (__fastcall ***v31)(_QWORD, __int64); // rcx
  char *v32; // rdi
  __int64 (__fastcall *v33)(char *, __int64 *, __int128 *); // rbx
  _QWORD *v34; // rax
  void (__fastcall ***v35)(_QWORD, __int64); // rcx
  char *v36; // rcx
  void (__fastcall ***v37)(_QWORD, __int64); // rcx
  __int64 v38; // [rsp+20h] [rbp-99h] BYREF
  char *v39; // [rsp+28h] [rbp-91h] BYREF
  __int64 v40; // [rsp+30h] [rbp-89h] BYREF
  __int64 v41; // [rsp+38h] [rbp-81h] BYREF
  __int64 v42; // [rsp+40h] [rbp-79h] BYREF
  __int64 v43; // [rsp+48h] [rbp-71h] BYREF
  __int64 v44[3]; // [rsp+50h] [rbp-69h] BYREF
  volatile signed __int32 *v45; // [rsp+68h] [rbp-51h]
  void **v46; // [rsp+80h] [rbp-39h]
  __int128 v47; // [rsp+88h] [rbp-31h] BYREF
  __int128 v48; // [rsp+98h] [rbp-21h]
  char *v49[4]; // [rsp+A8h] [rbp-11h] BYREF
  char *v50[4]; // [rsp+C8h] [rbp+Fh] BYREF

  v4 = RegistryT<256>::RegistryT<256>(v44);
  v5 = *(__int64 (__fastcall **)(_QWORD *, __int64 *, __int128 *))*v4;
  v47 = 0;
  v48 = 0;
  v6 = -1;
  do
    ++v6;
  while ( aAppinventory[v6] );
  std::wstring::_Construct<1,unsigned short const *>(&v47, L"AppInventory", v6);
  v7 = (_QWORD *)v5(v4, &v38, &v47);
  v8 = (__int64 (__fastcall ****)(_QWORD, __int64 *, char **))(*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v7 + 48LL))(
                                                                *v7,
                                                                &v42);
  v9 = *v8;
  v10 = ***v8;
  std::wstring::wstring((__int64)v49, (__int64)a1 + 72);
  v11 = (_QWORD *)v10(v9, &v41, v49);
  (*(void (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v11 + 48LL))(*v11, &v40);
  if ( v41 )
  {
    v12 = (void (__fastcall ***)(_QWORD, __int64))(v41 + *(int *)(*(_QWORD *)(v41 + 8) + 4LL) + 8LL);
    (**v12)(v12, 1);
  }
  std::wstring::~wstring(v49);
  if ( v42 )
  {
    v13 = (void (__fastcall ***)(_QWORD, __int64))(v42 + *(int *)(*(_QWORD *)(v42 + 8) + 4LL) + 8LL);
    (**v13)(v13, 1);
  }
  if ( v38 )
  {
    v14 = (void (__fastcall ***)(_QWORD, __int64))(v38 + *(int *)(*(_QWORD *)(v38 + 8) + 4LL) + 8LL);
    (**v14)(v14, 1);
  }
  std::wstring::~wstring((char **)&v47);
  v15 = v45;
  if ( v45 )
  {
    if ( _InterlockedExchangeAdd(v45 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
  v46 = &IConstHierarchicalStorage::`vftable';
  v16 = v40;
  v17 = **(__int64 (__fastcall ***)(__int64, __int64 *, char **))v40;
  std::wstring::wstring((__int64)v50, (__int64)a2 + 48);
  v18 = (_QWORD *)v17(v16, &v43, v50);
  (*(void (__fastcall **)(_QWORD, char **))(*(_QWORD *)*v18 + 48LL))(*v18, &v39);
  if ( v43 )
  {
    v19 = (void (__fastcall ***)(_QWORD, __int64))(v43 + *(int *)(*(_QWORD *)(v43 + 8) + 4LL) + 8LL);
    (**v19)(v19, 1);
  }
  std::wstring::~wstring(v50);
  v20 = v39;
  v21 = **(__int64 (__fastcall ***)(char *, __int64 *, __int128 *))v39;
  v47 = 0;
  v48 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v47, L"DisplayName", 0xBu);
  v22 = (_QWORD *)v21(v20, &v38, &v47);
  (*(void (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v22 + 32LL))(*v22, (char *)a2 + 80);
  if ( v38 )
  {
    v23 = (void (__fastcall ***)(_QWORD, __int64))(v38 + *(int *)(*(_QWORD *)(v38 + 8) + 4LL) + 8LL);
    (**v23)(v23, 1);
  }
  std::wstring::~wstring((char **)&v47);
  if ( *((_BYTE *)a2 + 144) )
  {
    v24 = v39;
    v25 = **(__int64 (__fastcall ***)(char *, __int64 *, __int128 *))v39;
    v47 = 0;
    v48 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v47, L"FirstUsedTime", 0xDu);
    v26 = (_QWORD *)v25(v24, &v38, &v47);
    (*(void (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v26 + 32LL))(*v26, (char *)a2 + 112);
    if ( v38 )
    {
      v27 = (void (__fastcall ***)(_QWORD, __int64))(v38 + *(int *)(*(_QWORD *)(v38 + 8) + 4LL) + 8LL);
      (**v27)(v27, 1);
    }
    std::wstring::~wstring((char **)&v47);
  }
  if ( *((_BYTE *)a2 + 184) )
  {
    v28 = v39;
    v29 = **(__int64 (__fastcall ***)(char *, __int64 *, __int128 *))v39;
    v47 = 0;
    v48 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v47, L"LastUsedTime", 0xCu);
    v30 = (_QWORD *)v29(v28, &v38, &v47);
    (*(void (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v30 + 32LL))(*v30, (char *)a2 + 152);
    if ( v38 )
    {
      v31 = (void (__fastcall ***)(_QWORD, __int64))(v38 + *(int *)(*(_QWORD *)(v38 + 8) + 4LL) + 8LL);
      (**v31)(v31, 1);
    }
    std::wstring::~wstring((char **)&v47);
  }
  if ( *((_BYTE *)a2 + 224) )
  {
    v32 = v39;
    v33 = **(__int64 (__fastcall ***)(char *, __int64 *, __int128 *))v39;
    v47 = 0;
    v48 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v47, L"LastUpdatedTime", 0xFu);
    v34 = (_QWORD *)v33(v32, &v38, &v47);
    (*(void (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v34 + 32LL))(*v34, (char *)a2 + 192);
    if ( v38 )
    {
      v35 = (void (__fastcall ***)(_QWORD, __int64))(v38 + *(int *)(*(_QWORD *)(v38 + 8) + 4LL) + 8LL);
      (**v35)(v35, 1);
    }
    std::wstring::~wstring((char **)&v47);
  }
  if ( v39 )
  {
    v36 = &v39[*(int *)(*((_QWORD *)v39 + 1) + 4LL) + 8];
    (**(void (__fastcall ***)(char *, __int64))v36)(v36, 1);
  }
  if ( v40 )
  {
    v37 = (void (__fastcall ***)(_QWORD, __int64))(v40 + 8 + *(int *)(*(_QWORD *)(v40 + 8) + 4LL));
    (**v37)(v37, 1);
  }
}

```

## disassembly

```asm
0x180018d94  mov     [rsp-8+arg_10], rbx
0x180018d99  mov     [rsp-8+arg_18], rsi
0x180018d9e  push    rbp
0x180018d9f  push    rdi
0x180018da0  push    r12
0x180018da2  push    r14
0x180018da4  push    r15
0x180018da6  lea     rbp, [rsp-37h]
0x180018dab  sub     rsp, 0F0h
0x180018db2  mov     rax, cs:__security_cookie
0x180018db9  xor     rax, rsp
0x180018dbc  mov     [rbp+57h+var_28], rax
0x180018dc0  mov     rsi, rdx
0x180018dc3  mov     r14, rcx
0x180018dc6  xor     r15d, r15d
0x180018dc9  lea     rcx, [rbp+57h+var_C0]
0x180018dcd  call    ??0?$RegistryT@$0BAA@@@QEAA@PEBG@Z; RegistryT<256>::RegistryT<256>(ushort const *)
0x180018dd2  mov     rbx, rax
0x180018dd5  mov     rcx, [rax]
0x180018dd8  mov     rdi, [rcx]
0x180018ddb  mov     rdx, cs:off_180030A80; "AppInventory"
0x180018de2  xorps   xmm0, xmm0
0x180018de5  movups  [rbp+57h+var_88], xmm0
0x180018de9  xorps   xmm1, xmm1
0x180018dec  movdqu  [rbp+57h+var_78], xmm1
0x180018df1  or      r8, 0FFFFFFFFFFFFFFFFh
0x180018df5  inc     r8
0x180018df8  cmp     [rdx+r8*2], r15w
0x180018dfd  jnz     short loc_180018DF5
0x180018dff  lea     rcx, [rbp+57h+var_88]
0x180018e03  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180018e08  nop
0x180018e09  lea     r8, [rbp+57h+var_88]
0x180018e0d  lea     rdx, [rsp+110h+var_F0]
0x180018e12  mov     rcx, rbx
0x180018e15  mov     rax, rdi
0x180018e18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e1d  nop
0x180018e1e  mov     rcx, [rax]
0x180018e21  mov     rax, [rcx]
0x180018e24  lea     rdx, [rbp+57h+var_D0]
0x180018e28  mov     rax, [rax+30h]
0x180018e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e31  nop
0x180018e32  mov     rdi, [rax]
0x180018e35  mov     rax, [rdi]
0x180018e38  mov     rbx, [rax]
0x180018e3b  lea     rdx, [r14+48h]
0x180018e3f  lea     rcx, [rbp+57h+var_68]
0x180018e43  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180018e48  nop
0x180018e49  lea     r8, [rbp+57h+var_68]
0x180018e4d  lea     rdx, [rsp+110h+var_D8]
0x180018e52  mov     rcx, rdi
0x180018e55  mov     rax, rbx
0x180018e58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e5d  nop
0x180018e5e  mov     rcx, [rax]
0x180018e61  mov     rax, [rcx]
0x180018e64  lea     rdx, [rsp+110h+var_E0]
0x180018e69  mov     rax, [rax+30h]
0x180018e6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e72  nop
0x180018e73  mov     r12d, 1
0x180018e79  mov     rdx, [rsp+110h+var_D8]
0x180018e7e  test    rdx, rdx
0x180018e81  jz      short loc_180018EA1
0x180018e83  mov     rax, [rdx+8]
0x180018e87  movsxd  rcx, dword ptr [rax+4]
0x180018e8b  add     rcx, 8
0x180018e8f  add     rcx, rdx
0x180018e92  mov     rax, [rcx]
0x180018e95  mov     edx, r12d
0x180018e98  mov     rax, [rax]
0x180018e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ea0  nop
0x180018ea1  lea     rcx, [rbp+57h+var_68]
0x180018ea5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018eaa  nop
0x180018eab  mov     rdx, [rbp+57h+var_D0]
0x180018eaf  test    rdx, rdx
0x180018eb2  jz      short loc_180018ED2
0x180018eb4  mov     rax, [rdx+8]
0x180018eb8  movsxd  rcx, dword ptr [rax+4]
0x180018ebc  add     rcx, 8
0x180018ec0  add     rcx, rdx
0x180018ec3  mov     rax, [rcx]
0x180018ec6  mov     edx, r12d
0x180018ec9  mov     rax, [rax]
0x180018ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ed1  nop
0x180018ed2  mov     rdx, [rsp+110h+var_F0]
0x180018ed7  test    rdx, rdx
0x180018eda  jz      short loc_180018EFA
0x180018edc  mov     rax, [rdx+8]
0x180018ee0  movsxd  rcx, dword ptr [rax+4]
0x180018ee4  add     rcx, 8
0x180018ee8  add     rcx, rdx
0x180018eeb  mov     rax, [rcx]
0x180018eee  mov     edx, r12d
0x180018ef1  mov     rax, [rax]
0x180018ef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ef9  nop
0x180018efa  lea     rcx, [rbp+57h+var_88]
0x180018efe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018f03  nop
0x180018f04  mov     rbx, [rbp+57h+var_A8]
0x180018f08  test    rbx, rbx
0x180018f0b  jz      short loc_180018F44
0x180018f0d  or      eax, 0FFFFFFFFh
0x180018f10  lock xadd [rbx+8], eax
0x180018f15  cmp     eax, 1
0x180018f18  jnz     short loc_180018F44
0x180018f1a  mov     rax, [rbx]
0x180018f1d  mov     rcx, rbx
0x180018f20  mov     rax, [rax]
0x180018f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f28  or      eax, 0FFFFFFFFh
0x180018f2b  lock xadd [rbx+0Ch], eax
0x180018f30  cmp     eax, 1
0x180018f33  jnz     short loc_180018F44
0x180018f35  mov     rax, [rbx]
0x180018f38  mov     rcx, rbx
0x180018f3b  mov     rax, [rax+8]
0x180018f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f44  lea     rax, ??_7IConstHierarchicalStorage@@6B@; const IConstHierarchicalStorage::`vftable'
0x180018f4b  mov     [rbp+57h+var_90], rax
0x180018f4f  mov     rdi, [rsp+110h+var_E0]
0x180018f54  mov     rax, [rdi]
0x180018f57  mov     rbx, [rax]
0x180018f5a  lea     rdx, [rsi+30h]
0x180018f5e  lea     rcx, [rbp+57h+var_48]
0x180018f62  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180018f67  nop
0x180018f68  lea     r8, [rbp+57h+var_48]
0x180018f6c  lea     rdx, [rbp+57h+var_C8]
0x180018f70  mov     rcx, rdi
0x180018f73  mov     rax, rbx
0x180018f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f7b  nop
0x180018f7c  mov     rcx, [rax]
0x180018f7f  mov     rax, [rcx]
0x180018f82  lea     rdx, [rsp+110h+var_E8]
0x180018f87  mov     rax, [rax+30h]
0x180018f8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f90  nop
0x180018f91  mov     rdx, [rbp+57h+var_C8]
0x180018f95  test    rdx, rdx
0x180018f98  jz      short loc_180018FB8
0x180018f9a  mov     rax, [rdx+8]
0x180018f9e  movsxd  rcx, dword ptr [rax+4]
0x180018fa2  add     rcx, 8
0x180018fa6  add     rcx, rdx
0x180018fa9  mov     rax, [rcx]
0x180018fac  mov     edx, r12d
0x180018faf  mov     rax, [rax]
0x180018fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fb7  nop
0x180018fb8  lea     rcx, [rbp+57h+var_48]
0x180018fbc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018fc1  mov     rdi, [rsp+110h+var_E8]
0x180018fc6  mov     rax, [rdi]
0x180018fc9  mov     rbx, [rax]
0x180018fcc  xorps   xmm0, xmm0
0x180018fcf  movups  [rbp+57h+var_88], xmm0
0x180018fd3  xorps   xmm1, xmm1
0x180018fd6  movdqu  [rbp+57h+var_78], xmm1
0x180018fdb  mov     r8d, 0Bh
0x180018fe1  lea     rdx, aDisplayname; "DisplayName"
0x180018fe8  lea     rcx, [rbp+57h+var_88]
0x180018fec  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180018ff1  nop
0x180018ff2  lea     r8, [rbp+57h+var_88]
0x180018ff6  lea     rdx, [rsp+110h+var_F0]
0x180018ffb  mov     rcx, rdi
0x180018ffe  mov     rax, rbx
0x180019001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019006  nop
0x180019007  mov     rcx, [rax]
0x18001900a  mov     rax, [rcx]
0x18001900d  lea     rdx, [rsi+50h]
0x180019011  mov     rax, [rax+20h]
0x180019015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001901a  nop
0x18001901b  mov     rdx, [rsp+110h+var_F0]
0x180019020  test    rdx, rdx
0x180019023  jz      short loc_180019043
0x180019025  mov     rax, [rdx+8]
0x180019029  movsxd  rcx, dword ptr [rax+4]
0x18001902d  add     rcx, 8
0x180019031  add     rcx, rdx
0x180019034  mov     rax, [rcx]
0x180019037  mov     edx, r12d
0x18001903a  mov     rax, [rax]
0x18001903d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019042  nop
0x180019043  lea     rcx, [rbp+57h+var_88]
0x180019047  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001904c  cmp     [rsi+90h], r15b
0x180019053  jz      loc_1800190E4
0x180019059  mov     rdi, [rsp+110h+var_E8]
0x18001905e  mov     rax, [rdi]
0x180019061  mov     rbx, [rax]
0x180019064  xorps   xmm0, xmm0
0x180019067  movups  [rbp+57h+var_88], xmm0
0x18001906b  xorps   xmm1, xmm1
0x18001906e  movdqu  [rbp+57h+var_78], xmm1
0x180019073  mov     r8d, 0Dh
0x180019079  lea     rdx, aFirstusedtime; "FirstUsedTime"
0x180019080  lea     rcx, [rbp+57h+var_88]
0x180019084  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180019089  nop
0x18001908a  lea     r8, [rbp+57h+var_88]
0x18001908e  lea     rdx, [rsp+110h+var_F0]
0x180019093  mov     rcx, rdi
0x180019096  mov     rax, rbx
0x180019099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001909e  nop
0x18001909f  mov     rcx, [rax]
0x1800190a2  mov     rax, [rcx]
0x1800190a5  lea     rdx, [rsi+70h]
0x1800190a9  mov     rax, [rax+20h]
0x1800190ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190b2  nop
0x1800190b3  mov     rdx, [rsp+110h+var_F0]
0x1800190b8  test    rdx, rdx
0x1800190bb  jz      short loc_1800190DB
0x1800190bd  mov     rax, [rdx+8]
0x1800190c1  movsxd  rcx, dword ptr [rax+4]
0x1800190c5  add     rcx, 8
0x1800190c9  add     rcx, rdx
0x1800190cc  mov     rax, [rcx]
0x1800190cf  mov     edx, r12d
0x1800190d2  mov     rax, [rax]
0x1800190d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190da  nop
0x1800190db  lea     rcx, [rbp+57h+var_88]
0x1800190df  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800190e4  lea     r14, [rsi+98h]
0x1800190eb  cmp     [r14+20h], r15b
0x1800190ef  jz      loc_18001917F
0x1800190f5  mov     rdi, [rsp+110h+var_E8]
0x1800190fa  mov     rax, [rdi]
0x1800190fd  mov     rbx, [rax]
0x180019100  xorps   xmm0, xmm0
0x180019103  movups  [rbp+57h+var_88], xmm0
0x180019107  xorps   xmm1, xmm1
0x18001910a  movdqu  [rbp+57h+var_78], xmm1
0x18001910f  mov     r8d, 0Ch
0x180019115  lea     rdx, aLastusedtime; "LastUsedTime"
0x18001911c  lea     rcx, [rbp+57h+var_88]
0x180019120  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180019125  nop
0x180019126  lea     r8, [rbp+57h+var_88]
0x18001912a  lea     rdx, [rsp+110h+var_F0]
0x18001912f  mov     rcx, rdi
0x180019132  mov     rax, rbx
0x180019135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001913a  nop
0x18001913b  mov     rcx, [rax]
0x18001913e  mov     rax, [rcx]
0x180019141  mov     rdx, r14
0x180019144  mov     rax, [rax+20h]
0x180019148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001914d  nop
0x18001914e  mov     rdx, [rsp+110h+var_F0]
0x180019153  test    rdx, rdx
0x180019156  jz      short loc_180019176
0x180019158  mov     rax, [rdx+8]
0x18001915c  movsxd  rcx, dword ptr [rax+4]
0x180019160  add     rcx, 8
0x180019164  add     rcx, rdx
0x180019167  mov     rax, [rcx]
0x18001916a  mov     edx, r12d
0x18001916d  mov     rax, [rax]
0x180019170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019175  nop
0x180019176  lea     rcx, [rbp+57h+var_88]
0x18001917a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001917f  cmp     [rsi+0E0h], r15b
0x180019186  jz      loc_18001921B
0x18001918c  mov     rdi, [rsp+110h+var_E8]
0x180019191  mov     rax, [rdi]
0x180019194  mov     rbx, [rax]
0x180019197  xorps   xmm0, xmm0
0x18001919a  movups  [rbp+57h+var_88], xmm0
0x18001919e  xorps   xmm1, xmm1
0x1800191a1  movdqu  [rbp+57h+var_78], xmm1
0x1800191a6  mov     r8d, 0Fh
0x1800191ac  lea     rdx, aLastupdatedtim; "LastUpdatedTime"
0x1800191b3  lea     rcx, [rbp+57h+var_88]
0x1800191b7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800191bc  nop
0x1800191bd  lea     r8, [rbp+57h+var_88]
0x1800191c1  lea     rdx, [rsp+110h+var_F0]
0x1800191c6  mov     rcx, rdi
0x1800191c9  mov     rax, rbx
0x1800191cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191d1  nop
0x1800191d2  mov     rcx, [rax]
  ... truncated ...
```
