# wpc::AppLimits::AppInventory::AppInventoryStorage::UpdateLastUsedTimeForUserApp(Sid const &,wpc::AppLimits::AppInventory::AppInfo &)

- ea: `0x1800184e8`
- end: `0x180018a69`
- name: `?UpdateLastUsedTimeForUserApp@AppInventoryStorage@AppInventory@AppLimits@wpc@@SAXAEBVSid@@AEAUAppInfo@234@@Z`
- size: `1409`
- prototype: `void __fastcall(const struct Sid *, struct wpc::AppLimits::AppInventory::AppInfo *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180018a70`

## callees

- `0x1800032a0`
- `0x180003d20`
- `0x180005950`
- `0x180005a04`
- `0x180005f9c`
- `0x18000ba1c`
- `0x18000bb84`
- `0x180016574`
- `0x1800184e8`
- `0x1800195c4`
- `0x18001ca8c`
- `0x18001cad0`
- `0x180024fa4`
- `0x180026734`
- `0x18002c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
void __fastcall wpc::AppLimits::AppInventory::AppInventoryStorage::UpdateLastUsedTimeForUserApp(
        const struct Sid *a1,
        struct wpc::AppLimits::AppInventory::AppInfo *a2)
{
  __int64 Current; // rax
  __int64 v5; // rbx
  __int64 (__fastcall *v6)(__int64, __int64 *, __int128 *); // rdi
  unsigned __int64 v7; // r8
  _QWORD *v8; // rax
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  __int64 v11; // rbx
  _QWORD *v12; // rbx
  __int64 (__fastcall *v13)(_QWORD *, _QWORD *, __int128 *); // rdi
  unsigned __int64 v14; // r8
  _QWORD *v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // rax
  void (__fastcall ***v18)(_QWORD, __int64); // rcx
  void (__fastcall ***v19)(_QWORD, __int64); // rcx
  void (__fastcall ***v20)(_QWORD, __int64); // rcx
  volatile signed __int32 *v21; // rbx
  _QWORD *v22; // rax
  void (__fastcall ***v23)(_QWORD, __int64); // rcx
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, _QWORD *, __int128 *); // rbx
  _QWORD *v26; // rax
  void (__fastcall ***v27)(_QWORD, __int64); // rcx
  char *v28; // rcx
  void (__fastcall ***v29)(_QWORD, __int64); // rcx
  void (__fastcall ***v30)(_QWORD, __int64); // rcx
  void (__fastcall ***v31)(_QWORD, _QWORD); // rcx
  __int64 v32; // [rsp+20h] [rbp-E0h] BYREF
  __int64 (__fastcall ***v33)(_QWORD, __int64); // [rsp+28h] [rbp-D8h] BYREF
  __int64 v34; // [rsp+30h] [rbp-D0h] BYREF
  __int64 (__fastcall ***v35)(_QWORD, __int64); // [rsp+38h] [rbp-C8h] BYREF
  __int64 v36; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v37[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v38; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v39; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v40[3]; // [rsp+68h] [rbp-98h] BYREF
  volatile signed __int32 *v41; // [rsp+80h] [rbp-80h]
  void **v42; // [rsp+98h] [rbp-68h]
  __int128 pExceptionObject; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v44; // [rsp+B0h] [rbp-50h]
  char *v45[4]; // [rsp+C8h] [rbp-38h] BYREF
  char *v46[4]; // [rsp+E8h] [rbp-18h] BYREF
  char *v47[4]; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v48[6]; // [rsp+128h] [rbp+28h] BYREF
  __int64 v49; // [rsp+158h] [rbp+58h]

  Current = DateTime::GetCurrent((__int64)v37);
  DateTime::Serialize(Current, v45);
  std::wstring::wstring((__int64)v47, (__int64)a1 + 72);
  std::wstring::wstring((__int64)v46, (__int64)a2 + 48);
  ReadRegistryT<256>::TryOpen(
    v48,
    HKEY_LOCAL_MACHINE,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\Parental Controls");
  if ( !v49 )
  {
LABEL_47:
    Optional<ReadRegistryT<256>>::~Optional<ReadRegistryT<256>>((__int64)v48);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, -2147024809);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  v5 = v49 + *(int *)(*(_QWORD *)(v49 + 16) + 4LL);
  v6 = *(__int64 (__fastcall **)(__int64, __int64 *, __int128 *))(*(_QWORD *)(v5 + 16) + 24LL);
  pExceptionObject = 0;
  v44 = 0;
  v7 = -1;
  do
    ++v7;
  while ( aAppinventory[v7] );
  std::wstring::_Construct<1,unsigned short const *>(&pExceptionObject, L"AppInventory", v7);
  v8 = (_QWORD *)v6(v5 + 16, &v32, &pExceptionObject);
  (*(void (__fastcall **)(_QWORD, __int64 (__fastcall ****)(_QWORD, __int64)))(*(_QWORD *)*v8 + 56LL))(*v8, &v35);
  if ( v32 )
    (**(void (__fastcall ***)(__int64, __int64))v32)(v32, 1);
  std::wstring::~wstring((char **)&pExceptionObject);
  if ( !v35 )
  {
LABEL_46:
    stdext::unique_ref<IConstStorageValue,std::default_delete<IConstStorageValue>>::~unique_ref<IConstStorageValue,std::default_delete<IConstStorageValue>>(&v35);
    goto LABEL_47;
  }
  v9 = (_QWORD *)((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64), __int64 *, char **))(*v35)[3])(
                   v35,
                   &v36,
                   v47);
  (*(void (__fastcall **)(_QWORD, __int64 (__fastcall ****)(_QWORD, __int64)))(*(_QWORD *)*v9 + 56LL))(*v9, &v33);
  if ( v36 )
    (**(void (__fastcall ***)(__int64, __int64))v36)(v36, 1);
  if ( !v33 )
    goto LABEL_45;
  v10 = (_QWORD *)((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64), __int64 *, char **))(*v33)[3])(
                    v33,
                    &v34,
                    v46);
  v11 = *(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v10 + 56LL))(*v10, &v32);
  if ( v32 )
    (**(void (__fastcall ***)(__int64, __int64))v32)(v32, 1);
  if ( v34 )
    (**(void (__fastcall ***)(__int64, __int64))v34)(v34, 1);
  if ( !v11 )
  {
LABEL_45:
    stdext::unique_ref<IConstStorageValue,std::default_delete<IConstStorageValue>>::~unique_ref<IConstStorageValue,std::default_delete<IConstStorageValue>>(&v33);
    goto LABEL_46;
  }
  v12 = RegistryT<256>::RegistryT<256>(v40);
  v13 = *(__int64 (__fastcall **)(_QWORD *, _QWORD *, __int128 *))*v12;
  pExceptionObject = 0;
  v44 = 0;
  v14 = -1;
  do
    ++v14;
  while ( aAppinventory[v14] );
  std::wstring::_Construct<1,unsigned short const *>(&pExceptionObject, L"AppInventory", v14);
  v15 = (_QWORD *)v13(v12, v37, &pExceptionObject);
  v16 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v15 + 48LL))(*v15, &v39);
  v17 = (_QWORD *)(**(__int64 (__fastcall ***)(_QWORD, __int64 *, char **))*v16)(*v16, &v38, v47);
  (*(void (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v17 + 48LL))(*v17, &v32);
  if ( v38 )
  {
    v18 = (void (__fastcall ***)(_QWORD, __int64))(v38 + *(int *)(*(_QWORD *)(v38 + 8) + 4LL) + 8LL);
    (**v18)(v18, 1);
  }
  if ( v39 )
  {
    v19 = (void (__fastcall ***)(_QWORD, __int64))(v39 + *(int *)(*(_QWORD *)(v39 + 8) + 4LL) + 8LL);
    (**v19)(v19, 1);
  }
  if ( v37[0] )
  {
    v20 = (void (__fastcall ***)(_QWORD, __int64))(v37[0] + *(int *)(*(_QWORD *)(v37[0] + 8LL) + 4LL) + 8LL);
    (**v20)(v20, 1);
  }
  std::wstring::~wstring((char **)&pExceptionObject);
  v21 = v41;
  if ( v41 )
  {
    if ( _InterlockedExchangeAdd(v41 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
      if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
    }
  }
  v42 = &IConstHierarchicalStorage::`vftable';
  v22 = (_QWORD *)(**(__int64 (__fastcall ***)(__int64, __int64 *, char **))v32)(v32, &v36, v46);
  (*(void (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v22 + 48LL))(*v22, &v34);
  if ( v36 )
  {
    v23 = (void (__fastcall ***)(_QWORD, __int64))(v36 + *(int *)(*(_QWORD *)(v36 + 8) + 4LL) + 8LL);
    (**v23)(v23, 1);
  }
  v24 = v34;
  v25 = **(__int64 (__fastcall ***)(__int64, _QWORD *, __int128 *))v34;
  pExceptionObject = 0;
  v44 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&pExceptionObject, L"LastUsedTime", 0xCu);
  v26 = (_QWORD *)v25(v24, v37, &pExceptionObject);
  (*(void (__fastcall **)(_QWORD, char **))(*(_QWORD *)*v26 + 32LL))(*v26, v45);
  if ( v37[0] )
  {
    v27 = (void (__fastcall ***)(_QWORD, __int64))(v37[0] + *(int *)(*(_QWORD *)(v37[0] + 8LL) + 4LL) + 8LL);
    (**v27)(v27, 1);
  }
  std::wstring::~wstring((char **)&pExceptionObject);
  v28 = (char *)a2 + 152;
  if ( *((_BYTE *)a2 + 184) )
  {
    std::wstring::operator=(v28, v45);
  }
  else
  {
    std::wstring::wstring((__int64)v28, (__int64)v45);
    *((_BYTE *)a2 + 184) = 1;
  }
  if ( v34 )
  {
    v29 = (void (__fastcall ***)(_QWORD, __int64))(v34 + *(int *)(*(_QWORD *)(v34 + 8) + 4LL) + 8LL);
    (**v29)(v29, 1);
  }
  if ( v32 )
  {
    v30 = (void (__fastcall ***)(_QWORD, __int64))(v32 + *(int *)(*(_QWORD *)(v32 + 8) + 4LL) + 8LL);
    (**v30)(v30, 1);
  }
  if ( v33 )
    (**v33)(v33, 1);
  if ( v35 )
    (**v35)(v35, 1);
  if ( v49 )
  {
    v31 = (void (__fastcall ***)(_QWORD, _QWORD))(v49 + *(int *)(*(_QWORD *)(v49 + 16) + 4LL) + 16LL);
    (**v31)(v31, 0);
    v49 = 0;
  }
  std::wstring::~wstring(v46);
  std::wstring::~wstring(v47);
  std::wstring::~wstring(v45);
}

```

## disassembly

```asm
0x1800184e8  mov     [rsp-8+arg_10], rbx
0x1800184ed  mov     [rsp-8+arg_18], rsi
0x1800184f2  push    rbp
0x1800184f3  push    rdi
0x1800184f4  push    r12
0x1800184f6  push    r14
0x1800184f8  push    r15
0x1800184fa  lea     rbp, [rsp-70h]
0x1800184ff  sub     rsp, 170h
0x180018506  mov     rax, cs:__security_cookie
0x18001850d  xor     rax, rsp
0x180018510  mov     [rbp+90h+var_30], rax
0x180018514  mov     rsi, rdx
0x180018517  mov     rbx, rcx
0x18001851a  xor     r14d, r14d
0x18001851d  lea     rcx, [rsp+190h+var_148]
0x180018522  call    ?GetCurrent@DateTime@@SA?AV1@XZ; DateTime::GetCurrent(void)
0x180018527  lea     rdx, [rbp+90h+var_C8]
0x18001852b  mov     rcx, rax
0x18001852e  call    ?Serialize@DateTime@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DateTime::Serialize(void)
0x180018533  nop
0x180018534  lea     rdx, [rbx+48h]
0x180018538  lea     rcx, [rbp+90h+var_88]
0x18001853c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180018541  nop
0x180018542  lea     rdx, [rsi+30h]
0x180018546  lea     rcx, [rbp+90h+var_A8]
0x18001854a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001854f  nop
0x180018550  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180018557  mov     rdx, 0FFFFFFFF80000002h
0x18001855e  lea     rcx, [rbp+90h+var_68]
0x180018562  call    ?TryOpen@?$ReadRegistryT@$0BAA@@@SA?AV?$Optional@V?$ReadRegistryT@$0BAA@@@@@PEAUHKEY__@@PEBG@Z; ReadRegistryT<256>::TryOpen(HKEY__ *,ushort const *)
0x180018567  nop
0x180018568  mov     rdx, [rbp+90h+var_38]
0x18001856c  test    rdx, rdx
0x18001856f  jz      loc_180018A41
0x180018575  mov     rax, [rdx+10h]
0x180018579  movsxd  rbx, dword ptr [rax+4]
0x18001857d  add     rbx, rdx
0x180018580  mov     rax, [rbx+10h]
0x180018584  mov     rdi, [rax+18h]
0x180018588  mov     rdx, cs:off_180030A80; "AppInventory"
0x18001858f  xorps   xmm0, xmm0
0x180018592  movups  [rbp+90h+pExceptionObject], xmm0
0x180018596  xorps   xmm1, xmm1
0x180018599  movdqu  [rbp+90h+var_E0], xmm1
0x18001859e  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800185a2  mov     r8, r12
0x1800185a5  inc     r8
0x1800185a8  cmp     [rdx+r8*2], r14w
0x1800185ad  jnz     short loc_1800185A5
0x1800185af  lea     rcx, [rbp+90h+pExceptionObject]
0x1800185b3  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800185b8  nop
0x1800185b9  lea     r8, [rbp+90h+pExceptionObject]
0x1800185bd  lea     rdx, [rsp+190h+var_170]
0x1800185c2  lea     rcx, [rbx+10h]
0x1800185c6  mov     rax, rdi
0x1800185c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185ce  nop
0x1800185cf  mov     rcx, [rax]
0x1800185d2  mov     rax, [rcx]
0x1800185d5  lea     rdx, [rsp+190h+var_158]
0x1800185da  mov     rax, [rax+38h]
0x1800185de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185e3  nop
0x1800185e4  mov     r15d, 1
0x1800185ea  mov     rcx, [rsp+190h+var_170]
0x1800185ef  test    rcx, rcx
0x1800185f2  jz      short loc_180018603
0x1800185f4  mov     rax, [rcx]
0x1800185f7  mov     edx, r15d
0x1800185fa  mov     rax, [rax]
0x1800185fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018602  nop
0x180018603  lea     rcx, [rbp+90h+pExceptionObject]
0x180018607  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001860c  mov     rcx, [rsp+190h+var_158]
0x180018611  test    rcx, rcx
0x180018614  jz      loc_180018A36
0x18001861a  mov     rax, [rcx]
0x18001861d  lea     r8, [rbp+90h+var_88]
0x180018621  lea     rdx, [rsp+190h+var_150]
0x180018626  mov     rax, [rax+18h]
0x18001862a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001862f  nop
0x180018630  mov     rcx, [rax]
0x180018633  mov     rax, [rcx]
0x180018636  lea     rdx, [rsp+190h+var_168]
0x18001863b  mov     rax, [rax+38h]
0x18001863f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018644  nop
0x180018645  mov     rcx, [rsp+190h+var_150]
0x18001864a  test    rcx, rcx
0x18001864d  jz      short loc_18001865D
0x18001864f  mov     rax, [rcx]
0x180018652  mov     edx, r15d
0x180018655  mov     rax, [rax]
0x180018658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001865d  mov     rcx, [rsp+190h+var_168]
0x180018662  test    rcx, rcx
0x180018665  jz      loc_180018A2B
0x18001866b  mov     rax, [rcx]
0x18001866e  lea     r8, [rbp+90h+var_A8]
0x180018672  lea     rdx, [rsp+190h+var_160]
0x180018677  mov     rax, [rax+18h]
0x18001867b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018680  nop
0x180018681  mov     rcx, [rax]
0x180018684  mov     rax, [rcx]
0x180018687  lea     rdx, [rsp+190h+var_170]
0x18001868c  mov     rax, [rax+38h]
0x180018690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018695  mov     rbx, [rax]
0x180018698  mov     rcx, [rsp+190h+var_170]
0x18001869d  test    rcx, rcx
0x1800186a0  jz      short loc_1800186B1
0x1800186a2  mov     rax, [rcx]
0x1800186a5  mov     edx, r15d
0x1800186a8  mov     rax, [rax]
0x1800186ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186b0  nop
0x1800186b1  mov     rcx, [rsp+190h+var_160]
0x1800186b6  test    rcx, rcx
0x1800186b9  jz      short loc_1800186C9
0x1800186bb  mov     rax, [rcx]
0x1800186be  mov     edx, r15d
0x1800186c1  mov     rax, [rax]
0x1800186c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186c9  test    rbx, rbx
0x1800186cc  jz      loc_180018A2B
0x1800186d2  lea     rcx, [rsp+190h+var_128]
0x1800186d7  call    ??0?$RegistryT@$0BAA@@@QEAA@PEBG@Z; RegistryT<256>::RegistryT<256>(ushort const *)
0x1800186dc  mov     rbx, rax
0x1800186df  mov     rcx, [rax]
0x1800186e2  mov     rdi, [rcx]
0x1800186e5  mov     rdx, cs:off_180030A80; "AppInventory"
0x1800186ec  xorps   xmm0, xmm0
0x1800186ef  movups  [rbp+90h+pExceptionObject], xmm0
0x1800186f3  xorps   xmm1, xmm1
0x1800186f6  movdqu  [rbp+90h+var_E0], xmm1
0x1800186fb  mov     r8, r12
0x1800186fe  inc     r8
0x180018701  cmp     [rdx+r8*2], r14w
0x180018706  jnz     short loc_1800186FE
0x180018708  lea     rcx, [rbp+90h+pExceptionObject]
0x18001870c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180018711  nop
0x180018712  lea     r8, [rbp+90h+pExceptionObject]
0x180018716  lea     rdx, [rsp+190h+var_148]
0x18001871b  mov     rcx, rbx
0x18001871e  mov     rax, rdi
0x180018721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018726  nop
0x180018727  mov     rcx, [rax]
0x18001872a  mov     rax, [rcx]
0x18001872d  lea     rdx, [rsp+190h+var_130]
0x180018732  mov     rax, [rax+30h]
0x180018736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001873b  nop
0x18001873c  mov     rcx, [rax]
0x18001873f  mov     rax, [rcx]
0x180018742  lea     r8, [rbp+90h+var_88]
0x180018746  lea     rdx, [rsp+190h+var_138]
0x18001874b  mov     rax, [rax]
0x18001874e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018753  nop
0x180018754  mov     rcx, [rax]
0x180018757  mov     rax, [rcx]
0x18001875a  lea     rdx, [rsp+190h+var_170]
0x18001875f  mov     rax, [rax+30h]
0x180018763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018768  nop
0x180018769  mov     rdx, [rsp+190h+var_138]
0x18001876e  test    rdx, rdx
0x180018771  jz      short loc_180018791
0x180018773  mov     rax, [rdx+8]
0x180018777  movsxd  rcx, dword ptr [rax+4]
0x18001877b  add     rcx, 8
0x18001877f  add     rcx, rdx
0x180018782  mov     rax, [rcx]
0x180018785  mov     edx, r15d
0x180018788  mov     rax, [rax]
0x18001878b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018790  nop
0x180018791  mov     rdx, [rsp+190h+var_130]
0x180018796  test    rdx, rdx
0x180018799  jz      short loc_1800187B9
0x18001879b  mov     rax, [rdx+8]
0x18001879f  movsxd  rcx, dword ptr [rax+4]
0x1800187a3  add     rcx, 8
0x1800187a7  add     rcx, rdx
0x1800187aa  mov     rax, [rcx]
0x1800187ad  mov     edx, r15d
0x1800187b0  mov     rax, [rax]
0x1800187b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187b8  nop
0x1800187b9  mov     rdx, [rsp+190h+var_148]
0x1800187be  test    rdx, rdx
0x1800187c1  jz      short loc_1800187E1
0x1800187c3  mov     rax, [rdx+8]
0x1800187c7  movsxd  rcx, dword ptr [rax+4]
0x1800187cb  add     rcx, 8
0x1800187cf  add     rcx, rdx
0x1800187d2  mov     rax, [rcx]
0x1800187d5  mov     edx, r15d
0x1800187d8  mov     rax, [rax]
0x1800187db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187e0  nop
0x1800187e1  lea     rcx, [rbp+90h+pExceptionObject]
0x1800187e5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800187ea  nop
0x1800187eb  mov     rbx, [rbp+90h+var_110]
0x1800187ef  test    rbx, rbx
0x1800187f2  jz      short loc_18001882B
0x1800187f4  mov     eax, r12d
0x1800187f7  lock xadd [rbx+8], eax
0x1800187fc  add     eax, r12d
0x1800187ff  jnz     short loc_18001882B
0x180018801  mov     rax, [rbx]
0x180018804  mov     rcx, rbx
0x180018807  mov     rax, [rax]
0x18001880a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001880f  mov     eax, r12d
0x180018812  lock xadd [rbx+0Ch], eax
0x180018817  add     eax, r12d
0x18001881a  jnz     short loc_18001882B
0x18001881c  mov     rax, [rbx]
0x18001881f  mov     rcx, rbx
0x180018822  mov     rax, [rax+8]
0x180018826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001882b  lea     rax, ??_7IConstHierarchicalStorage@@6B@; const IConstHierarchicalStorage::`vftable'
0x180018832  mov     [rbp+90h+var_F8], rax
0x180018836  mov     rcx, [rsp+190h+var_170]
0x18001883b  mov     rax, [rcx]
0x18001883e  lea     r8, [rbp+90h+var_A8]
0x180018842  lea     rdx, [rsp+190h+var_150]
0x180018847  mov     rax, [rax]
0x18001884a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001884f  nop
0x180018850  mov     rcx, [rax]
0x180018853  mov     rax, [rcx]
0x180018856  lea     rdx, [rsp+190h+var_160]
0x18001885b  mov     rax, [rax+30h]
0x18001885f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018864  nop
0x180018865  mov     rdx, [rsp+190h+var_150]
0x18001886a  test    rdx, rdx
0x18001886d  jz      short loc_18001888C
0x18001886f  mov     rax, [rdx+8]
0x180018873  movsxd  rcx, dword ptr [rax+4]
0x180018877  add     rcx, 8
0x18001887b  add     rcx, rdx
0x18001887e  mov     rax, [rcx]
0x180018881  mov     edx, r15d
0x180018884  mov     rax, [rax]
0x180018887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001888c  mov     rdi, [rsp+190h+var_160]
0x180018891  mov     rax, [rdi]
0x180018894  mov     rbx, [rax]
0x180018897  xorps   xmm0, xmm0
0x18001889a  movups  [rbp+90h+pExceptionObject], xmm0
0x18001889e  xorps   xmm1, xmm1
0x1800188a1  movdqu  [rbp+90h+var_E0], xmm1
0x1800188a6  mov     r8d, 0Ch
0x1800188ac  lea     rdx, aLastusedtime; "LastUsedTime"
0x1800188b3  lea     rcx, [rbp+90h+pExceptionObject]
0x1800188b7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800188bc  nop
0x1800188bd  lea     r8, [rbp+90h+pExceptionObject]
0x1800188c1  lea     rdx, [rsp+190h+var_148]
0x1800188c6  mov     rcx, rdi
0x1800188c9  mov     rax, rbx
0x1800188cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188d1  nop
0x1800188d2  mov     rcx, [rax]
0x1800188d5  mov     rax, [rcx]
0x1800188d8  lea     rdx, [rbp+90h+var_C8]
0x1800188dc  mov     rax, [rax+20h]
0x1800188e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188e5  nop
0x1800188e6  mov     rdx, [rsp+190h+var_148]
0x1800188eb  test    rdx, rdx
0x1800188ee  jz      short loc_18001890E
0x1800188f0  mov     rax, [rdx+8]
0x1800188f4  movsxd  rcx, dword ptr [rax+4]
0x1800188f8  add     rcx, 8
0x1800188fc  add     rcx, rdx
0x1800188ff  mov     rax, [rcx]
0x180018902  mov     edx, r15d
0x180018905  mov     rax, [rax]
0x180018908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001890d  nop
0x18001890e  lea     rcx, [rbp+90h+pExceptionObject]
0x180018912  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018917  lea     rbx, [rsi+98h]
0x18001891e  lea     rdx, [rbp+90h+var_C8]
0x180018922  mov     rcx, rbx
0x180018925  cmp     [rbx+20h], r14b
  ... truncated ...
```
