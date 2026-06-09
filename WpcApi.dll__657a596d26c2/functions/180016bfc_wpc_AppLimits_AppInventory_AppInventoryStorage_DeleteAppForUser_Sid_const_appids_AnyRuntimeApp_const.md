# wpc::AppLimits::AppInventory::AppInventoryStorage::DeleteAppForUser(Sid const &,appids::AnyRuntimeApp const &)

- ea: `0x180016bfc`
- end: `0x180017172`
- name: `?DeleteAppForUser@AppInventoryStorage@AppInventory@AppLimits@wpc@@SAXAEBVSid@@AEBVAnyRuntimeApp@appids@@@Z`
- size: `1398`
- prototype: `void __fastcall(const struct Sid *, const struct appids::AnyRuntimeApp *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180017ee0`

## callees

- `0x1800032a0`
- `0x180005950`
- `0x180005a04`
- `0x180005f9c`
- `0x180016bfc`
- `0x1800174b4`
- `0x180024fa4`
- `0x180026734`
- `0x18002c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wpc::AppLimits::AppInventory::AppInventoryStorage::DeleteAppForUser(
        const struct Sid *a1,
        const struct appids::AnyRuntimeApp *a2)
{
  __int64 v3; // rdx
  __int64 v4; // rbx
  __int64 (__fastcall *v5)(__int64, _QWORD **, _OWORD *); // rdi
  unsigned __int64 v6; // r8
  _QWORD *v7; // rax
  void (__fastcall ***v8)(_QWORD, __int64); // rcx
  _QWORD *v9; // rax
  void (__fastcall ***v10)(_QWORD, __int64); // rcx
  _QWORD *v11; // rax
  __int64 v12; // rbx
  _QWORD *v13; // rbx
  __int64 (__fastcall *v14)(_QWORD *, _OWORD *, __int128 *); // rdi
  unsigned __int64 v15; // r8
  _QWORD *v16; // rax
  _QWORD *v17; // rax
  _QWORD *v18; // rax
  void (__fastcall ***v19)(_QWORD, __int64); // rcx
  void (__fastcall ***v20)(_QWORD, __int64); // rcx
  void (__fastcall ***v21)(_QWORD, __int64); // rcx
  volatile signed __int32 *v22; // rbx
  void (__fastcall ***v23)(_QWORD, __int64); // rcx
  __int64 v24; // rax
  char IsEmpty; // di
  volatile signed __int32 *v26; // rbx
  _QWORD *v27; // rbx
  __int64 (__fastcall *v28)(_QWORD *, __int64 *, __int128 *); // rdi
  unsigned __int64 v29; // r8
  _QWORD *v30; // rax
  _QWORD *v31; // rax
  void (__fastcall ***v32)(_QWORD, __int64); // rcx
  void (__fastcall ***v33)(_QWORD, __int64); // rcx
  volatile signed __int32 *v34; // rbx
  void (__fastcall ***v35)(_QWORD, _QWORD); // rcx
  _QWORD *v36; // [rsp+20h] [rbp-E0h] BYREF
  void (__fastcall ***v37)(_QWORD, __int64); // [rsp+28h] [rbp-D8h] BYREF
  void (__fastcall ***v38)(_QWORD, __int64); // [rsp+30h] [rbp-D0h] BYREF
  __int64 v39; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v40; // [rsp+40h] [rbp-C0h] BYREF
  void (__fastcall ***v41)(_QWORD, __int64); // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v42[3]; // [rsp+50h] [rbp-B0h] BYREF
  volatile signed __int32 *v43; // [rsp+68h] [rbp-98h]
  void **v44; // [rsp+80h] [rbp-80h]
  _OWORD v45[2]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v46; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v47; // [rsp+B8h] [rbp-48h]
  char *v48[4]; // [rsp+C8h] [rbp-38h] BYREF
  char *v49[4]; // [rsp+E8h] [rbp-18h] BYREF
  char v50[48]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v51; // [rsp+138h] [rbp+38h]

  std::wstring::wstring((__int64)v48, (__int64)a1 + 72);
  std::wstring::wstring((__int64)v49, (__int64)a2 + 48);
  ReadRegistryT<256>::TryOpen(v50, -2147483646, L"Software\\Microsoft\\Windows\\CurrentVersion\\Parental Controls");
  v3 = v51;
  if ( v51 )
  {
    v4 = v51 + *(int *)(*(_QWORD *)(v51 + 16) + 4LL);
    v5 = *(__int64 (__fastcall **)(__int64, _QWORD **, _OWORD *))(*(_QWORD *)(v4 + 16) + 24LL);
    memset(v45, 0, sizeof(v45));
    v6 = -1;
    do
      ++v6;
    while ( aAppinventory[v6] );
    std::wstring::_Construct<1,unsigned short const *>(v45, L"AppInventory", v6);
    v7 = (_QWORD *)v5(v4 + 16, &v36, v45);
    (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*v7 + 56LL))(*v7, &v38);
    if ( v36 )
      (*(void (__fastcall **)(_QWORD *, __int64))*v36)(v36, 1);
    std::wstring::~wstring((char **)v45);
    v8 = v38;
    if ( v38 )
    {
      v9 = (_QWORD *)((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, __int64), void (__fastcall ****)(_QWORD, __int64), char **))(*v38)[3])(
                       v38,
                       &v41,
                       v48);
      (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*v9 + 56LL))(*v9, &v37);
      if ( v41 )
        (**v41)(v41, 1);
      v10 = v37;
      if ( v37 )
      {
        v11 = (_QWORD *)((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, __int64), __int64 *, char **))(*v37)[3])(
                          v37,
                          &v39,
                          v49);
        v12 = *(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD **))(*(_QWORD *)*v11 + 56LL))(*v11, &v36);
        if ( v36 )
          (*(void (__fastcall **)(_QWORD *, __int64))*v36)(v36, 1);
        if ( v39 )
          (**(void (__fastcall ***)(__int64, __int64))v39)(v39, 1);
        if ( v12 )
        {
          v13 = RegistryT<256>::RegistryT<256>(v42);
          v14 = *(__int64 (__fastcall **)(_QWORD *, _OWORD *, __int128 *))*v13;
          v46 = 0;
          v47 = 0;
          v15 = -1;
          do
            ++v15;
          while ( aAppinventory[v15] );
          std::wstring::_Construct<1,unsigned short const *>(&v46, L"AppInventory", v15);
          v16 = (_QWORD *)v14(v13, v45, &v46);
          v17 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v16 + 48LL))(*v16, &v40);
          v18 = (_QWORD *)(**(__int64 (__fastcall ***)(_QWORD, __int64 *, char **))*v17)(*v17, &v39, v48);
          (*(void (__fastcall **)(_QWORD, _QWORD **))(*(_QWORD *)*v18 + 48LL))(*v18, &v36);
          if ( v39 )
          {
            v19 = (void (__fastcall ***)(_QWORD, __int64))(v39 + *(int *)(*(_QWORD *)(v39 + 8) + 4LL) + 8LL);
            (**v19)(v19, 1);
          }
          if ( v40 )
          {
            v20 = (void (__fastcall ***)(_QWORD, __int64))(v40 + *(int *)(*(_QWORD *)(v40 + 8) + 4LL) + 8LL);
            (**v20)(v20, 1);
          }
          if ( *(_QWORD *)&v45[0] )
          {
            v21 = (void (__fastcall ***)(_QWORD, __int64))(*(_QWORD *)&v45[0]
                                                         + *(int *)(*(_QWORD *)(*(_QWORD *)&v45[0] + 8LL) + 4LL)
                                                         + 8LL);
            (**v21)(v21, 1);
          }
          std::wstring::~wstring((char **)&v46);
          v22 = v43;
          if ( v43 )
          {
            if ( _InterlockedExchangeAdd(v43 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
              if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
            }
          }
          v44 = &IConstHierarchicalStorage::`vftable';
          (*(void (__fastcall **)(_QWORD *, char **))(*v36 + 8LL))(v36, v49);
          if ( v36 )
          {
            v23 = (void (__fastcall ***)(_QWORD, __int64))((char *)v36 + *(int *)(v36[1] + 4LL) + 8);
            (**v23)(v23, 1);
          }
        }
        v24 = ((__int64 (__fastcall *)(_QWORD, _OWORD *))(*v37)[1])(v37, v45);
        IsEmpty = Collections::Enumerable<std::wstring>::IsEmpty(v24);
        v26 = (volatile signed __int32 *)*((_QWORD *)&v45[0] + 1);
        if ( *((_QWORD *)&v45[0] + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v45[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
            if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
          }
        }
        if ( IsEmpty )
        {
          v27 = RegistryT<256>::RegistryT<256>(v42);
          v28 = *(__int64 (__fastcall **)(_QWORD *, __int64 *, __int128 *))*v27;
          v46 = 0;
          v47 = 0;
          v29 = -1;
          do
            ++v29;
          while ( aAppinventory[v29] );
          std::wstring::_Construct<1,unsigned short const *>(&v46, L"AppInventory", v29);
          v30 = (_QWORD *)v28(v27, &v40, &v46);
          v31 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _OWORD *))(*(_QWORD *)*v30 + 48LL))(*v30, v45);
          (*(void (__fastcall **)(_QWORD, char **))(*(_QWORD *)*v31 + 8LL))(*v31, v48);
          if ( *(_QWORD *)&v45[0] )
          {
            v32 = (void (__fastcall ***)(_QWORD, __int64))(*(_QWORD *)&v45[0]
                                                         + *(int *)(*(_QWORD *)(*(_QWORD *)&v45[0] + 8LL) + 4LL)
                                                         + 8LL);
            (**v32)(v32, 1);
          }
          if ( v40 )
          {
            v33 = (void (__fastcall ***)(_QWORD, __int64))(v40 + *(int *)(*(_QWORD *)(v40 + 8) + 4LL) + 8LL);
            (**v33)(v33, 1);
          }
          std::wstring::~wstring((char **)&v46);
          v34 = v43;
          if ( v43 )
          {
            if ( _InterlockedExchangeAdd(v43 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
              if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
            }
          }
        }
        v10 = v37;
      }
      if ( v10 )
        (**v10)(v10, 1);
      v8 = v38;
    }
    if ( v8 )
      (**v8)(v8, 1);
    v3 = v51;
  }
  if ( v3 )
  {
    v35 = (void (__fastcall ***)(_QWORD, _QWORD))(v3 + *(int *)(*(_QWORD *)(v3 + 16) + 4LL) + 16LL);
    (**v35)(v35, 0);
  }
  std::wstring::~wstring(v49);
  std::wstring::~wstring(v48);
}

```

## disassembly

```asm
0x180016bfc  mov     [rsp-8+arg_10], rbx
0x180016c01  push    rbp
0x180016c02  push    rsi
0x180016c03  push    rdi
0x180016c04  push    r14
0x180016c06  push    r15
0x180016c08  lea     rbp, [rsp-50h]
0x180016c0d  sub     rsp, 150h
0x180016c14  mov     rax, cs:__security_cookie
0x180016c1b  xor     rax, rsp
0x180016c1e  mov     [rbp+70h+var_30], rax
0x180016c22  mov     rbx, rdx
0x180016c25  xor     esi, esi
0x180016c27  lea     rdx, [rcx+48h]
0x180016c2b  lea     rcx, [rbp+70h+var_A8]
0x180016c2f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180016c34  nop
0x180016c35  lea     rdx, [rbx+30h]
0x180016c39  lea     rcx, [rbp+70h+var_88]
0x180016c3d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180016c42  nop
0x180016c43  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180016c4a  mov     rdx, 0FFFFFFFF80000002h
0x180016c51  lea     rcx, [rbp+70h+var_68]
0x180016c55  call    ?TryOpen@?$ReadRegistryT@$0BAA@@@SA?AV?$Optional@V?$ReadRegistryT@$0BAA@@@@@PEAUHKEY__@@PEBG@Z; ReadRegistryT<256>::TryOpen(HKEY__ *,ushort const *)
0x180016c5a  nop
0x180016c5b  mov     rdx, [rbp+70h+var_38]
0x180016c5f  test    rdx, rdx
0x180016c62  jz      loc_18001711A
0x180016c68  mov     rax, [rdx+10h]
0x180016c6c  movsxd  rbx, dword ptr [rax+4]
0x180016c70  add     rbx, rdx
0x180016c73  mov     rax, [rbx+10h]
0x180016c77  mov     rdi, [rax+18h]
0x180016c7b  mov     rdx, cs:off_180030A80; "AppInventory"
0x180016c82  xorps   xmm0, xmm0
0x180016c85  movups  [rbp+70h+var_E8], xmm0
0x180016c89  xorps   xmm1, xmm1
0x180016c8c  movdqu  [rbp+70h+var_D8], xmm1
0x180016c91  or      r14, 0FFFFFFFFFFFFFFFFh
0x180016c95  mov     r8, r14
0x180016c98  inc     r8
0x180016c9b  cmp     [rdx+r8*2], si
0x180016ca0  jnz     short loc_180016C98
0x180016ca2  lea     rcx, [rbp+70h+var_E8]
0x180016ca6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180016cab  nop
0x180016cac  lea     r8, [rbp+70h+var_E8]
0x180016cb0  lea     rdx, [rsp+170h+var_150]
0x180016cb5  lea     rcx, [rbx+10h]
0x180016cb9  mov     rax, rdi
0x180016cbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cc1  nop
0x180016cc2  mov     rcx, [rax]
0x180016cc5  mov     rax, [rcx]
0x180016cc8  lea     rdx, [rsp+170h+var_140]
0x180016ccd  mov     rax, [rax+38h]
0x180016cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cd6  nop
0x180016cd7  mov     r15d, 1
0x180016cdd  mov     rcx, [rsp+170h+var_150]
0x180016ce2  test    rcx, rcx
0x180016ce5  jz      short loc_180016CF6
0x180016ce7  mov     rax, [rcx]
0x180016cea  mov     edx, r15d
0x180016ced  mov     rax, [rax]
0x180016cf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cf5  nop
0x180016cf6  lea     rcx, [rbp+70h+var_E8]
0x180016cfa  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016cff  mov     rcx, [rsp+170h+var_140]
0x180016d04  test    rcx, rcx
0x180016d07  jz      loc_180017103
0x180016d0d  mov     rax, [rcx]
0x180016d10  lea     r8, [rbp+70h+var_A8]
0x180016d14  lea     rdx, [rsp+170h+var_128]
0x180016d19  mov     rax, [rax+18h]
0x180016d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d22  nop
0x180016d23  mov     rcx, [rax]
0x180016d26  mov     rax, [rcx]
0x180016d29  lea     rdx, [rsp+170h+var_148]
0x180016d2e  mov     rax, [rax+38h]
0x180016d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d37  nop
0x180016d38  mov     rcx, [rsp+170h+var_128]
0x180016d3d  test    rcx, rcx
0x180016d40  jz      short loc_180016D50
0x180016d42  mov     rax, [rcx]
0x180016d45  mov     edx, r15d
0x180016d48  mov     rax, [rax]
0x180016d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d50  mov     rcx, [rsp+170h+var_148]
0x180016d55  test    rcx, rcx
0x180016d58  jz      loc_1800170EB
0x180016d5e  mov     rax, [rcx]
0x180016d61  lea     r8, [rbp+70h+var_88]
0x180016d65  lea     rdx, [rsp+170h+var_138]
0x180016d6a  mov     rax, [rax+18h]
0x180016d6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d73  nop
0x180016d74  mov     rcx, [rax]
0x180016d77  mov     rax, [rcx]
0x180016d7a  lea     rdx, [rsp+170h+var_150]
0x180016d7f  mov     rax, [rax+38h]
0x180016d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d88  mov     rbx, [rax]
0x180016d8b  mov     rcx, [rsp+170h+var_150]
0x180016d90  test    rcx, rcx
0x180016d93  jz      short loc_180016DA4
0x180016d95  mov     rax, [rcx]
0x180016d98  mov     edx, r15d
0x180016d9b  mov     rax, [rax]
0x180016d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016da3  nop
0x180016da4  mov     rcx, [rsp+170h+var_138]
0x180016da9  test    rcx, rcx
0x180016dac  jz      short loc_180016DBC
0x180016dae  mov     rax, [rcx]
0x180016db1  mov     edx, r15d
0x180016db4  mov     rax, [rax]
0x180016db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016dbc  test    rbx, rbx
0x180016dbf  jz      loc_180016F65
0x180016dc5  lea     rcx, [rsp+170h+var_120]
0x180016dca  call    ??0?$RegistryT@$0BAA@@@QEAA@PEBG@Z; RegistryT<256>::RegistryT<256>(ushort const *)
0x180016dcf  mov     rbx, rax
0x180016dd2  mov     rcx, [rax]
0x180016dd5  mov     rdi, [rcx]
0x180016dd8  mov     rdx, cs:off_180030A80; "AppInventory"
0x180016ddf  xorps   xmm0, xmm0
0x180016de2  movups  [rbp+70h+var_C8], xmm0
0x180016de6  xorps   xmm1, xmm1
0x180016de9  movdqu  [rbp+70h+var_B8], xmm1
0x180016dee  mov     r8, r14
0x180016df1  inc     r8
0x180016df4  cmp     [rdx+r8*2], si
0x180016df9  jnz     short loc_180016DF1
0x180016dfb  lea     rcx, [rbp+70h+var_C8]
0x180016dff  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180016e04  nop
0x180016e05  lea     r8, [rbp+70h+var_C8]
0x180016e09  lea     rdx, [rbp+70h+var_E8]
0x180016e0d  mov     rcx, rbx
0x180016e10  mov     rax, rdi
0x180016e13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e18  nop
0x180016e19  mov     rcx, [rax]
0x180016e1c  mov     rax, [rcx]
0x180016e1f  lea     rdx, [rsp+170h+var_130]
0x180016e24  mov     rax, [rax+30h]
0x180016e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e2d  nop
0x180016e2e  mov     rcx, [rax]
0x180016e31  mov     rax, [rcx]
0x180016e34  lea     r8, [rbp+70h+var_A8]
0x180016e38  lea     rdx, [rsp+170h+var_138]
0x180016e3d  mov     rax, [rax]
0x180016e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e45  nop
0x180016e46  mov     rcx, [rax]
0x180016e49  mov     rax, [rcx]
0x180016e4c  lea     rdx, [rsp+170h+var_150]
0x180016e51  mov     rax, [rax+30h]
0x180016e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e5a  nop
0x180016e5b  mov     rdx, [rsp+170h+var_138]
0x180016e60  test    rdx, rdx
0x180016e63  jz      short loc_180016E83
0x180016e65  mov     rax, [rdx+8]
0x180016e69  movsxd  rcx, dword ptr [rax+4]
0x180016e6d  add     rcx, 8
0x180016e71  add     rcx, rdx
0x180016e74  mov     rax, [rcx]
0x180016e77  mov     edx, r15d
0x180016e7a  mov     rax, [rax]
0x180016e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e82  nop
0x180016e83  mov     rdx, [rsp+170h+var_130]
0x180016e88  test    rdx, rdx
0x180016e8b  jz      short loc_180016EAB
0x180016e8d  mov     rax, [rdx+8]
0x180016e91  movsxd  rcx, dword ptr [rax+4]
0x180016e95  add     rcx, 8
0x180016e99  add     rcx, rdx
0x180016e9c  mov     rax, [rcx]
0x180016e9f  mov     edx, r15d
0x180016ea2  mov     rax, [rax]
0x180016ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016eaa  nop
0x180016eab  mov     rdx, qword ptr [rbp+70h+var_E8]
0x180016eaf  test    rdx, rdx
0x180016eb2  jz      short loc_180016ED2
0x180016eb4  mov     rax, [rdx+8]
0x180016eb8  movsxd  rcx, dword ptr [rax+4]
0x180016ebc  add     rcx, 8
0x180016ec0  add     rcx, rdx
0x180016ec3  mov     rax, [rcx]
0x180016ec6  mov     edx, r15d
0x180016ec9  mov     rax, [rax]
0x180016ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ed1  nop
0x180016ed2  lea     rcx, [rbp+70h+var_C8]
0x180016ed6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016edb  nop
0x180016edc  mov     rbx, [rsp+170h+var_108]
0x180016ee1  test    rbx, rbx
0x180016ee4  jz      short loc_180016F1D
0x180016ee6  mov     eax, r14d
0x180016ee9  lock xadd [rbx+8], eax
0x180016eee  add     eax, r14d
0x180016ef1  jnz     short loc_180016F1D
0x180016ef3  mov     rax, [rbx]
0x180016ef6  mov     rcx, rbx
0x180016ef9  mov     rax, [rax]
0x180016efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f01  mov     eax, r14d
0x180016f04  lock xadd [rbx+0Ch], eax
0x180016f09  add     eax, r14d
0x180016f0c  jnz     short loc_180016F1D
0x180016f0e  mov     rax, [rbx]
0x180016f11  mov     rcx, rbx
0x180016f14  mov     rax, [rax+8]
0x180016f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f1d  lea     rax, ??_7IConstHierarchicalStorage@@6B@; const IConstHierarchicalStorage::`vftable'
0x180016f24  mov     [rbp+70h+var_F0], rax
0x180016f28  mov     rcx, [rsp+170h+var_150]
0x180016f2d  mov     rax, [rcx]
0x180016f30  lea     rdx, [rbp+70h+var_88]
0x180016f34  mov     rax, [rax+8]
0x180016f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f3d  nop
0x180016f3e  mov     rdx, [rsp+170h+var_150]
0x180016f43  test    rdx, rdx
0x180016f46  jz      short loc_180016F65
0x180016f48  mov     rax, [rdx+8]
0x180016f4c  movsxd  rcx, dword ptr [rax+4]
0x180016f50  add     rcx, 8
0x180016f54  add     rcx, rdx
0x180016f57  mov     rax, [rcx]
0x180016f5a  mov     edx, r15d
0x180016f5d  mov     rax, [rax]
0x180016f60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f65  mov     rcx, [rsp+170h+var_148]
0x180016f6a  mov     rax, [rcx]
0x180016f6d  lea     rdx, [rbp+70h+var_E8]
0x180016f71  mov     rax, [rax+8]
0x180016f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f7a  nop
0x180016f7b  mov     rcx, rax
0x180016f7e  call    ?IsEmpty@?$Enumerable@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Collections@@QEBA_NXZ; Collections::Enumerable<std::wstring>::IsEmpty(void)
0x180016f83  mov     dil, al
0x180016f86  mov     rbx, qword ptr [rbp+70h+var_E8+8]
0x180016f8a  test    rbx, rbx
0x180016f8d  jz      short loc_180016FC6
0x180016f8f  mov     ecx, r14d
0x180016f92  lock xadd [rbx+8], ecx
0x180016f97  add     ecx, r14d
0x180016f9a  jnz     short loc_180016FC6
0x180016f9c  mov     rdx, [rbx]
0x180016f9f  mov     rcx, rbx
0x180016fa2  mov     rax, [rdx]
0x180016fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016faa  mov     eax, r14d
0x180016fad  lock xadd [rbx+0Ch], eax
0x180016fb2  add     eax, r14d
0x180016fb5  jnz     short loc_180016FC6
0x180016fb7  mov     rax, [rbx]
0x180016fba  mov     rcx, rbx
0x180016fbd  mov     rax, [rax+8]
0x180016fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fc6  test    dil, dil
0x180016fc9  jz      loc_1800170E6
0x180016fcf  lea     rcx, [rsp+170h+var_120]
0x180016fd4  call    ??0?$RegistryT@$0BAA@@@QEAA@PEBG@Z; RegistryT<256>::RegistryT<256>(ushort const *)
0x180016fd9  mov     rbx, rax
0x180016fdc  mov     rcx, [rax]
0x180016fdf  mov     rdi, [rcx]
0x180016fe2  mov     rdx, cs:off_180030A80; "AppInventory"
0x180016fe9  xorps   xmm0, xmm0
0x180016fec  movups  [rbp+70h+var_C8], xmm0
0x180016ff0  xorps   xmm1, xmm1
0x180016ff3  movdqu  [rbp+70h+var_B8], xmm1
0x180016ff8  mov     r8, r14
0x180016ffb  inc     r8
0x180016ffe  cmp     [rdx+r8*2], si
0x180017003  jnz     short loc_180016FFB
0x180017005  lea     rcx, [rbp+70h+var_C8]
0x180017009  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001700e  nop
0x18001700f  lea     r8, [rbp+70h+var_C8]
0x180017013  lea     rdx, [rsp+170h+var_130]
0x180017018  mov     rcx, rbx
0x18001701b  mov     rax, rdi
0x18001701e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017023  nop
0x180017024  mov     rcx, [rax]
0x180017027  mov     rax, [rcx]
0x18001702a  lea     rdx, [rbp+70h+var_E8]
0x18001702e  mov     rax, [rax+30h]
  ... truncated ...
```
