# CreateLanguageMigrationTaskManager(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>)

- ea: `0x180043550`
- end: `0x1800438c4`
- name: `?CreateLanguageMigrationTaskManager@@YA?AV?$unique_ptr@VLanguageMigrationTaskManager@@U?$default_delete@VLanguageMigrationTaskManager@@@std@@@std@@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z`
- size: `884`
- prototype: `__int64 *__fastcall(__int64 *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180019910`

## callees

- `0x180005db4`
- `0x180027818`
- `0x18003fff4`
- `0x180043550`
- `0x1800438cc`
- `0x18005e9b0`
- `0x18006a010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800436e4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800436e4`

## string_xrefs

- `0x180043744`: `SystemPreferredUILanguages`
- `0x1800437ac`: `LocalSystemPreferredUILanguages`

## pseudocode

```c
__int64 *__fastcall CreateLanguageMigrationTaskManager(__int64 *a1, __int64 a2)
{
  __int128 *v4; // rsi
  __int64 v5; // rax
  __int64 *v6; // rcx
  __int64 v7; // rdx
  _QWORD *v8; // rdi
  __int64 v9; // rax
  void *v10; // rcx
  unsigned __int64 UserSidHash; // rax
  volatile signed __int32 *v12; // rbx
  volatile signed __int32 *v13; // rbx
  __int64 v14; // rbx
  __int128 *v15; // rax
  __int64 v16; // rbx
  __int128 *v17; // rax
  __int64 v18; // rbx
  __int128 *v19; // rax
  volatile signed __int32 *v20; // rbx
  _QWORD v22[3]; // [rsp+28h] [rbp-50h] BYREF
  __int128 *v23; // [rsp+40h] [rbp-38h]
  __int128 v24; // [rsp+50h] [rbp-28h] BYREF
  __int128 v25; // [rsp+60h] [rbp-18h] BYREF
  __int128 *v26; // [rsp+D0h] [rbp+58h] BYREF
  _QWORD *v27; // [rsp+D8h] [rbp+60h] BYREF

  v4 = (__int128 *)operator new(0x18u);
  v26 = v4;
  *(_QWORD *)v4 = 0;
  *((_QWORD *)v4 + 1) = 0;
  *((_QWORD *)v4 + 2) = 0;
  *a1 = (__int64)v4;
  v25 = 0;
  v5 = *(_QWORD *)(a2 + 8);
  if ( v5 )
    _InterlockedAdd((volatile signed __int32 *)(v5 + 8), 1u);
  v6 = *(__int64 **)a2;
  *(_QWORD *)&v25 = v6;
  *((_QWORD *)&v25 + 1) = *(_QWORD *)(a2 + 8);
  v22[1] = &v25;
  if ( v6 )
    v7 = *v6;
  else
    v7 = 0;
  raii::ImpersonateLoggedOnUser(&v26, v7);
  *(_QWORD *)&v24 = L"UserPreferredUILanguages";
  *((_QWORD *)&v24 + 1) = 24;
  CreateDeprecatedLanguageMigrationExecutionPolicy(v22, 1, &v24);
  v8 = operator new(0x28u);
  v22[2] = v8;
  v24 = 0;
  v9 = *((_QWORD *)&v25 + 1);
  if ( *((_QWORD *)&v25 + 1) )
  {
    _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v25 + 1) + 8LL), 1u);
    v9 = *((_QWORD *)&v25 + 1);
  }
  *(_QWORD *)&v24 = v25;
  *((_QWORD *)&v24 + 1) = v9;
  v23 = &v24;
  if ( (_QWORD)v25 )
    v10 = *(void **)v25;
  else
    v10 = 0;
  UserSidHash = GetUserSidHash(v10);
  v8[1] = v22[0];
  v8[2] = UserSidHash;
  *v8 = &UserPreferredUILanguagesDeprecatedLanguageMigrationTask::`vftable';
  v8[3] = 0;
  v8[4] = 0;
  if ( *((_QWORD *)&v24 + 1) )
    _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v24 + 1) + 8LL), 1u);
  *(_OWORD *)(v8 + 3) = v24;
  v12 = (volatile signed __int32 *)*((_QWORD *)&v24 + 1);
  if ( *((_QWORD *)&v24 + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v24 + 1) + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( !_InterlockedDecrement(v12 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  if ( (_BYTE)v26 )
    RevertToSelf();
  v13 = (volatile signed __int32 *)*((_QWORD *)&v25 + 1);
  if ( *((_QWORD *)&v25 + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v25 + 1) + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      if ( !_InterlockedDecrement(v13 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
  }
  v26 = 0;
  v27 = v8;
  LanguageMigrationTaskManager::RegisterTask(v4, &v27);
  v14 = *a1;
  *(_QWORD *)&v25 = L"SystemPreferredUILanguages";
  *((_QWORD *)&v25 + 1) = 26;
  CreateDeprecatedLanguageMigrationExecutionPolicy(&v27, 0, &v25);
  v15 = (__int128 *)operator new(0x18u);
  v23 = v15;
  *((_QWORD *)v15 + 1) = v27;
  *((_QWORD *)v15 + 2) = 0;
  *(_QWORD *)v15 = &SystemPreferredUILanguagesDeprecatedLanguageMigrationTask::`vftable';
  v27 = 0;
  v26 = v15;
  LanguageMigrationTaskManager::RegisterTask(v14, &v26);
  v16 = *a1;
  *(_QWORD *)&v25 = L"LocalSystemPreferredUILanguages";
  *((_QWORD *)&v25 + 1) = 31;
  CreateDeprecatedLanguageMigrationExecutionPolicy(&v27, 0, &v25);
  v17 = (__int128 *)operator new(0x18u);
  v23 = v17;
  *((_QWORD *)v17 + 1) = v27;
  *((_QWORD *)v17 + 2) = 0;
  *(_QWORD *)v17 = &LocalSystemPreferredUILanguageDeprecatedLanguageMigrationTask::`vftable';
  v27 = 0;
  v26 = v17;
  LanguageMigrationTaskManager::RegisterTask(v16, &v26);
  v18 = *a1;
  *(_QWORD *)&v25 = L"NewUserPreferredUILanguages";
  *((_QWORD *)&v25 + 1) = 27;
  CreateDeprecatedLanguageMigrationExecutionPolicy(&v27, 0, &v25);
  v19 = (__int128 *)operator new(0x18u);
  v23 = v19;
  *((_QWORD *)v19 + 1) = v27;
  *((_QWORD *)v19 + 2) = 0;
  *(_QWORD *)v19 = &NewUserPreferredUILanguageDeprecatedLanguageMigrationTask::`vftable';
  v27 = 0;
  v26 = v19;
  LanguageMigrationTaskManager::RegisterTask(v18, &v26);
  v20 = *(volatile signed __int32 **)(a2 + 8);
  if ( v20 )
  {
    if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
      if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180043550  mov     [rsp-40h+arg_8], rdx
0x180043555  mov     [rsp-40h+arg_0], rcx
0x18004355a  push    rbp
0x18004355b  push    rbx
0x18004355c  push    rsi
0x18004355d  push    rdi
0x18004355e  push    r12
0x180043560  push    r13
0x180043562  push    r14
0x180043564  push    r15
0x180043566  mov     rbp, rsp
0x180043569  sub     rsp, 78h
0x18004356d  mov     r14, rdx
0x180043570  mov     r15, rcx
0x180043573  xor     r12d, r12d
0x180043576  mov     [rbp+var_58], r12d
0x18004357a  lea     edi, [r12+18h]
0x18004357f  mov     ecx, edi; Size
0x180043581  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180043586  mov     rsi, rax
0x180043589  mov     [rbp+arg_10], rax
0x18004358d  mov     [rax], r12
0x180043590  mov     [rax+8], r12
0x180043594  mov     [rax+10h], r12
0x180043598  mov     [r15], rax
0x18004359b  mov     [rbp+var_58], 3
0x1800435a2  xorps   xmm0, xmm0
0x1800435a5  movdqu  [rbp+var_18], xmm0
0x1800435aa  mov     rax, [r14+8]
0x1800435ae  lea     ebx, [rdi-17h]
0x1800435b1  test    rax, rax
0x1800435b4  jz      short loc_1800435BA
0x1800435b6  lock add [rax+8], ebx
0x1800435ba  mov     rcx, [r14]
0x1800435bd  mov     qword ptr [rbp+var_18], rcx
0x1800435c1  mov     rax, [r14+8]
0x1800435c5  mov     qword ptr [rbp+var_18+8], rax
0x1800435c9  lea     rax, [rbp+var_18]
0x1800435cd  mov     [rbp+var_48], rax
0x1800435d1  test    rcx, rcx
0x1800435d4  jz      short loc_1800435DB
0x1800435d6  mov     rdx, [rcx]
0x1800435d9  jmp     short loc_1800435DE
0x1800435db  mov     rdx, r12
0x1800435de  lea     rcx, [rbp+arg_10]
0x1800435e2  call    ?ImpersonateLoggedOnUser@raii@@YA?AV?$unique_call@P6AHXZ$1?RevertToSelf@@YAHXZ$00@wil@@PEAX@Z; raii::ImpersonateLoggedOnUser(void *)
0x1800435e7  nop
0x1800435e8  lea     rax, aUserpreferredu; "UserPreferredUILanguages"
0x1800435ef  mov     qword ptr [rbp+var_28], rax
0x1800435f3  mov     qword ptr [rbp+var_28+8], rdi
0x1800435f7  lea     r8, [rbp+var_28]
0x1800435fb  mov     edx, ebx
0x1800435fd  lea     rcx, [rbp+var_50]
0x180043601  call    ?CreateDeprecatedLanguageMigrationExecutionPolicy@@YA?AV?$unique_ptr@UILanguageMigrationExecutionPolicy@@U?$default_delete@UILanguageMigrationExecutionPolicy@@@std@@@std@@W4LanguageOverlayHive@@V?$basic_string_view@GU?$char_traits@G@std@@@2@@Z; CreateDeprecatedLanguageMigrationExecutionPolicy(LanguageOverlayHive,std::basic_string_view<ushort>)
0x180043606  nop
0x180043607  mov     ecx, 28h ; '('; Size
0x18004360c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180043611  mov     rdi, rax
0x180043614  mov     [rbp+var_40], rax
0x180043618  xorps   xmm0, xmm0
0x18004361b  movdqu  [rbp+var_28], xmm0
0x180043620  mov     rax, qword ptr [rbp+var_18+8]
0x180043624  test    rax, rax
0x180043627  jz      short loc_180043631
0x180043629  lock add [rax+8], ebx
0x18004362d  mov     rax, qword ptr [rbp+var_18+8]
0x180043631  mov     rcx, qword ptr [rbp+var_18]
0x180043635  mov     qword ptr [rbp+var_28], rcx
0x180043639  mov     qword ptr [rbp+var_28+8], rax
0x18004363d  lea     rax, [rbp+var_28]
0x180043641  mov     [rbp+var_38], rax
0x180043645  test    rcx, rcx
0x180043648  jz      short loc_18004364F
0x18004364a  mov     rcx, [rcx]
0x18004364d  jmp     short loc_180043652
0x18004364f  mov     rcx, r12; void *
0x180043652  call    ?GetUserSidHash@@YA_KPEAX@Z; GetUserSidHash(void *)
0x180043657  mov     rcx, [rbp+var_50]
0x18004365b  mov     [rdi+8], rcx
0x18004365f  mov     [rdi+10h], rax
0x180043663  lea     rax, ??_7UserPreferredUILanguagesDeprecatedLanguageMigrationTask@@6B@; const UserPreferredUILanguagesDeprecatedLanguageMigrationTask::`vftable'
0x18004366a  mov     [rdi], rax
0x18004366d  mov     [rdi+18h], r12
0x180043671  mov     [rdi+20h], r12
0x180043675  mov     rax, qword ptr [rbp+var_28+8]
0x180043679  test    rax, rax
0x18004367c  jz      short loc_180043682
0x18004367e  lock add [rax+8], ebx
0x180043682  mov     rax, qword ptr [rbp+var_28]
0x180043686  mov     [rdi+18h], rax
0x18004368a  mov     rax, qword ptr [rbp+var_28+8]
0x18004368e  mov     [rdi+20h], rax
0x180043692  mov     rbx, qword ptr [rbp+var_28+8]
0x180043696  or      r13d, 0FFFFFFFFh
0x18004369a  test    rbx, rbx
0x18004369d  jz      short loc_1800436D7
0x18004369f  mov     eax, r13d
0x1800436a2  lock xadd [rbx+8], eax
0x1800436a7  add     eax, r13d
0x1800436aa  jnz     short loc_1800436D7
0x1800436ac  mov     rax, [rbx]
0x1800436af  mov     rcx, rbx
0x1800436b2  mov     rax, [rax]
0x1800436b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800436ba  mov     eax, r13d
0x1800436bd  lock xadd [rbx+0Ch], eax
0x1800436c2  add     eax, r13d
0x1800436c5  jnz     short loc_1800436D7
0x1800436c7  mov     rax, [rbx]
0x1800436ca  mov     rcx, rbx
0x1800436cd  mov     rax, [rax+8]
0x1800436d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800436d6  nop
0x1800436d7  mov     [rbp+var_58], 0Fh
0x1800436de  cmp     byte ptr [rbp+arg_10], r12b
0x1800436e2  jz      short loc_1800436EB
0x1800436e4  call    cs:__imp_RevertToSelf
0x1800436ea  nop
0x1800436eb  mov     rbx, qword ptr [rbp+var_18+8]
0x1800436ef  test    rbx, rbx
0x1800436f2  jz      short loc_18004372C
0x1800436f4  mov     eax, r13d
0x1800436f7  lock xadd [rbx+8], eax
0x1800436fc  add     eax, r13d
0x1800436ff  jnz     short loc_18004372C
0x180043701  mov     rax, [rbx]
0x180043704  mov     rcx, rbx
0x180043707  mov     rax, [rax]
0x18004370a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004370f  mov     eax, r13d
0x180043712  lock xadd [rbx+0Ch], eax
0x180043717  add     eax, r13d
0x18004371a  jnz     short loc_18004372C
0x18004371c  mov     rax, [rbx]
0x18004371f  mov     rcx, rbx
0x180043722  mov     rax, [rax+8]
0x180043726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004372b  nop
0x18004372c  mov     [rbp+arg_10], r12
0x180043730  mov     [rbp+arg_18], rdi
0x180043734  lea     rdx, [rbp+arg_18]
0x180043738  mov     rcx, rsi
0x18004373b  call    ?RegisterTask@LanguageMigrationTaskManager@@QEAAXV?$unique_ptr@UILanguageMigrationTask@@U?$default_delete@UILanguageMigrationTask@@@std@@@std@@@Z; LanguageMigrationTaskManager::RegisterTask(std::unique_ptr<ILanguageMigrationTask>)
0x180043740  nop
0x180043741  mov     rbx, [r15]
0x180043744  lea     rax, aSystempreferre; "SystemPreferredUILanguages"
0x18004374b  mov     qword ptr [rbp+var_18], rax
0x18004374f  mov     qword ptr [rbp+var_18+8], 1Ah
0x180043757  lea     r8, [rbp+var_18]
0x18004375b  xor     edx, edx
0x18004375d  lea     rcx, [rbp+arg_18]
0x180043761  call    ?CreateDeprecatedLanguageMigrationExecutionPolicy@@YA?AV?$unique_ptr@UILanguageMigrationExecutionPolicy@@U?$default_delete@UILanguageMigrationExecutionPolicy@@@std@@@std@@W4LanguageOverlayHive@@V?$basic_string_view@GU?$char_traits@G@std@@@2@@Z; CreateDeprecatedLanguageMigrationExecutionPolicy(LanguageOverlayHive,std::basic_string_view<ushort>)
0x180043766  nop
0x180043767  mov     edi, 18h
0x18004376c  mov     ecx, edi; Size
0x18004376e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180043773  mov     [rbp+var_38], rax
0x180043777  mov     rdx, [rbp+arg_18]
0x18004377b  mov     [rax+8], rdx
0x18004377f  mov     [rax+10h], r12
0x180043783  lea     rcx, ??_7SystemPreferredUILanguagesDeprecatedLanguageMigrationTask@@6B@; const SystemPreferredUILanguagesDeprecatedLanguageMigrationTask::`vftable'
0x18004378a  mov     [rax], rcx
0x18004378d  mov     [rbp+var_58], 3Fh ; '?'
0x180043794  mov     [rbp+arg_18], r12
0x180043798  mov     [rbp+arg_10], rax
0x18004379c  lea     rdx, [rbp+arg_10]
0x1800437a0  mov     rcx, rbx
0x1800437a3  call    ?RegisterTask@LanguageMigrationTaskManager@@QEAAXV?$unique_ptr@UILanguageMigrationTask@@U?$default_delete@UILanguageMigrationTask@@@std@@@std@@@Z; LanguageMigrationTaskManager::RegisterTask(std::unique_ptr<ILanguageMigrationTask>)
0x1800437a8  nop
0x1800437a9  mov     rbx, [r15]
0x1800437ac  lea     rax, aLocalsystempre; "LocalSystemPreferredUILanguages"
0x1800437b3  mov     qword ptr [rbp+var_18], rax
0x1800437b7  mov     qword ptr [rbp+var_18+8], 1Fh
0x1800437bf  lea     r8, [rbp+var_18]
0x1800437c3  xor     edx, edx
0x1800437c5  lea     rcx, [rbp+arg_18]
0x1800437c9  call    ?CreateDeprecatedLanguageMigrationExecutionPolicy@@YA?AV?$unique_ptr@UILanguageMigrationExecutionPolicy@@U?$default_delete@UILanguageMigrationExecutionPolicy@@@std@@@std@@W4LanguageOverlayHive@@V?$basic_string_view@GU?$char_traits@G@std@@@2@@Z; CreateDeprecatedLanguageMigrationExecutionPolicy(LanguageOverlayHive,std::basic_string_view<ushort>)
0x1800437ce  nop
0x1800437cf  mov     ecx, edi; Size
0x1800437d1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800437d6  mov     [rbp+var_38], rax
0x1800437da  mov     rdx, [rbp+arg_18]
0x1800437de  mov     [rax+8], rdx
0x1800437e2  mov     [rax+10h], r12
0x1800437e6  lea     rcx, ??_7LocalSystemPreferredUILanguageDeprecatedLanguageMigrationTask@@6B@; const LocalSystemPreferredUILanguageDeprecatedLanguageMigrationTask::`vftable'
0x1800437ed  mov     [rax], rcx
0x1800437f0  mov     [rbp+var_58], 0FFh
0x1800437f7  mov     [rbp+arg_18], r12
0x1800437fb  mov     [rbp+arg_10], rax
0x1800437ff  lea     rdx, [rbp+arg_10]
0x180043803  mov     rcx, rbx
0x180043806  call    ?RegisterTask@LanguageMigrationTaskManager@@QEAAXV?$unique_ptr@UILanguageMigrationTask@@U?$default_delete@UILanguageMigrationTask@@@std@@@std@@@Z; LanguageMigrationTaskManager::RegisterTask(std::unique_ptr<ILanguageMigrationTask>)
0x18004380b  nop
0x18004380c  mov     rbx, [r15]
0x18004380f  lea     rax, aNewuserpreferr; "NewUserPreferredUILanguages"
0x180043816  mov     qword ptr [rbp+var_18], rax
0x18004381a  mov     qword ptr [rbp+var_18+8], 1Bh
0x180043822  lea     r8, [rbp+var_18]
0x180043826  xor     edx, edx
0x180043828  lea     rcx, [rbp+arg_18]
0x18004382c  call    ?CreateDeprecatedLanguageMigrationExecutionPolicy@@YA?AV?$unique_ptr@UILanguageMigrationExecutionPolicy@@U?$default_delete@UILanguageMigrationExecutionPolicy@@@std@@@std@@W4LanguageOverlayHive@@V?$basic_string_view@GU?$char_traits@G@std@@@2@@Z; CreateDeprecatedLanguageMigrationExecutionPolicy(LanguageOverlayHive,std::basic_string_view<ushort>)
0x180043831  nop
0x180043832  mov     ecx, edi; Size
0x180043834  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180043839  mov     [rbp+var_38], rax
0x18004383d  mov     rdx, [rbp+arg_18]
0x180043841  mov     [rax+8], rdx
0x180043845  mov     [rax+10h], r12
0x180043849  lea     rcx, ??_7NewUserPreferredUILanguageDeprecatedLanguageMigrationTask@@6B@; const NewUserPreferredUILanguageDeprecatedLanguageMigrationTask::`vftable'
0x180043850  mov     [rax], rcx
0x180043853  mov     [rbp+var_58], 3FFh
0x18004385a  mov     [rbp+arg_18], r12
0x18004385e  mov     [rbp+arg_10], rax
0x180043862  lea     rdx, [rbp+arg_10]
0x180043866  mov     rcx, rbx
0x180043869  call    ?RegisterTask@LanguageMigrationTaskManager@@QEAAXV?$unique_ptr@UILanguageMigrationTask@@U?$default_delete@UILanguageMigrationTask@@@std@@@std@@@Z; LanguageMigrationTaskManager::RegisterTask(std::unique_ptr<ILanguageMigrationTask>)
0x18004386e  nop
0x18004386f  mov     rbx, [r14+8]
0x180043873  test    rbx, rbx
0x180043876  jz      short loc_1800438AF
0x180043878  mov     eax, r13d
0x18004387b  lock xadd [rbx+8], eax
0x180043880  add     eax, r13d
0x180043883  jnz     short loc_1800438AF
0x180043885  mov     rax, [rbx]
0x180043888  mov     rcx, rbx
0x18004388b  mov     rax, [rax]
0x18004388e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043893  mov     eax, r13d
0x180043896  lock xadd [rbx+0Ch], eax
0x18004389b  add     eax, r13d
0x18004389e  jnz     short loc_1800438AF
0x1800438a0  mov     rax, [rbx]
0x1800438a3  mov     rcx, rbx
0x1800438a6  mov     rax, [rax+8]
0x1800438aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800438af  mov     rax, r15
0x1800438b2  add     rsp, 78h
0x1800438b6  pop     r15
0x1800438b8  pop     r14
0x1800438ba  pop     r13
0x1800438bc  pop     r12
0x1800438be  pop     rdi
0x1800438bf  pop     rsi
0x1800438c0  pop     rbx
0x1800438c1  pop     rbp
0x1800438c2  retn
```
