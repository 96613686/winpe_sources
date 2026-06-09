# Uev::TemplateManager::FindTemplates(Uev::ProgramCharacteristics const &,bool)

- ea: `0x140035b48`
- end: `0x140036086`
- name: `?FindTemplates@TemplateManager@Uev@@AEBA?AV?$vector@V?$unique_ptr@VITemplate@Uev@@U?$default_delete@VITemplate@Uev@@@std@@@std@@V?$allocator@V?$unique_ptr@VITemplate@Uev@@U?$default_delete@VITemplate@Uev@@@std@@@std@@@2@@std@@AEBUProgramCharacteristics@2@_N@Z`
- size: `1342`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, const struct Uev::ProgramCharacteristics *, char)`
- caller_count: `3`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140035810`
- `0x140036090`
- `0x140036320`

## callees

- `0x140003e50`
- `0x14000ba60`
- `0x14000e30c`
- `0x140019748`
- `0x1400322b8`
- `0x1400336f8`
- `0x140033880`
- `0x140034c14`
- `0x140034db4`
- `0x140034f58`
- `0x1400353d4`
- `0x140035b48`
- `0x140036210`
- `0x140036358`
- `0x140036550`
- `0x1400380d4`
- `0x14003c630`
- `0x140041550`
- `0x140045788`
- `0x140045af8`
- `0x14009b010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x140035bd2`
- `KERNEL32!LoadLibraryExW` at `0x140035bd2`
- `KERNEL32!FreeLibrary` at `0x140036027`
- `KERNEL32!FreeLibrary` at `0x140036027`

## string_xrefs

- `0x140035bcb`: `msxml6`

## pseudocode

```c
_QWORD *__fastcall Uev::TemplateManager::FindTemplates(
        __int64 a1,
        _QWORD *a2,
        const struct Uev::ProgramCharacteristics *a3,
        char a4)
{
  char v4; // di
  __int64 i; // rbx
  __int64 TemplateFilenameForId; // rax
  __int64 v10; // r8
  __int64 v11; // rcx
  _QWORD *v12; // r8
  void (__fastcall ***v13)(_QWORD, __int64); // rcx
  Uev::Template *v14; // rsi
  Uev::Template *v15; // r14
  void (__fastcall ***v16)(_QWORD, __int64); // rax
  __int64 v17; // rcx
  _QWORD *v18; // r8
  void (__fastcall ***v19)(_QWORD, __int64); // rcx
  void (__fastcall ***v20)(_QWORD, __int64); // rdi
  Uev::Template *v21; // rcx
  Uev::Template **j; // rbx
  char v23; // al
  Uev::Template *v24; // rcx
  __int128 *v25; // rdx
  void (__fastcall ****k)(_QWORD, __int64); // rbx
  void (__fastcall ***v27)(_QWORD, __int64); // rcx
  _QWORD *v28; // rdi
  _QWORD *v29; // r14
  __int64 v30; // rsi
  __int64 v31; // rax
  size_t v32; // r13
  size_t v33; // r15
  size_t v34; // r8
  int v35; // esi
  _QWORD *v36; // rdx
  Uev::Template *v39; // [rsp+28h] [rbp-D8h] BYREF
  int v40; // [rsp+30h] [rbp-D0h]
  HMODULE hLibModule; // [rsp+38h] [rbp-C8h]
  _QWORD *v42; // [rsp+40h] [rbp-C0h]
  _BYTE Src[32]; // [rsp+48h] [rbp-B8h] BYREF
  char v44; // [rsp+68h] [rbp-98h] BYREF
  char v45[7]; // [rsp+69h] [rbp-97h] BYREF
  void (__fastcall ***v46)(_QWORD, __int64); // [rsp+70h] [rbp-90h] BYREF
  __int64 v47; // [rsp+78h] [rbp-88h] BYREF
  __int128 v48; // [rsp+80h] [rbp-80h] BYREF
  __int64 v49; // [rsp+90h] [rbp-70h]
  void (__fastcall ***v50)(_QWORD, __int64); // [rsp+98h] [rbp-68h] BYREF
  Uev::Template *v51; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v52; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v53; // [rsp+B8h] [rbp-48h]
  __int128 v54; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v55; // [rsp+D0h] [rbp-30h]
  __int128 v56; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v57; // [rsp+E8h] [rbp-18h]
  _QWORD v58[4]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v59[4]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v60[2]; // [rsp+130h] [rbp+30h] BYREF
  char v61[16]; // [rsp+140h] [rbp+40h] BYREF
  char v62[48]; // [rsp+150h] [rbp+50h] BYREF

  v4 = a4;
  v42 = a2;
  v40 = 0;
  Uev::TemplateIndex::TemplateIndex((Uev::TemplateIndex *)v60);
  Uev::TemplateIndex::LoadIndex((Uev::TemplateIndex *)v60);
  Uev::TemplateIndex::FindTemplateIDs(v60, v59, a3);
  v48 = 0;
  v49 = 0;
  hLibModule = LoadLibraryExW(L"msxml6", 0, 0x800u);
  for ( i = v59[0]; i != v59[1]; i += 32 )
  {
    TemplateFilenameForId = Uev::TemplateAdministrator::GetTemplateFilenameForId(Src);
    LOBYTE(v10) = v4;
    Uev::TemplateSuite::CreateTemplateSuite(&v46, TemplateFilenameForId, v10);
    std::wstring::_Tidy_deallocate(Src);
    v44 = 1;
    v47 = 0;
    if ( !(unsigned __int8)Uev::SettingGroup<bool>::Get(*(_QWORD *)(a1 + 8) + 3312LL, v46 + 1, &v44, &v47)
      && (Microsoft_User_Experience_Virtualization_App_AgentEnableBits & 4) != 0 )
    {
      v12 = v46 + 1;
      if ( (unsigned __int64)v46[4] > 7 )
        v12 = (_QWORD *)*v12;
      McTemplateU0zq_EventWriteTransfer(v11, TemplateMsg_CantGetTemplateEnabled, v12, (unsigned int)v47);
    }
    if ( !v44 )
    {
      v13 = v46;
      goto LABEL_35;
    }
    while ( 1 )
    {
      v13 = v46;
      if ( !v46[18] )
        break;
      Uev::TemplateSuite::PullNextApplicationTemplate(v46, &v51);
      v14 = v51;
      if ( Uev::Template::Matches(v51, a3) )
      {
        v15 = v14;
        (*(void (__fastcall **)(Uev::Template *, _QWORD *))(*(_QWORD *)v14 + 16LL))(v14, v58);
        v45[0] = 1;
        v16 = v46;
        if ( *((_BYTE *)v46 + 96) )
          goto LABEL_19;
        if ( !(unsigned __int8)Uev::SettingGroup<bool>::Get(*(_QWORD *)(a1 + 8) + 3312LL, v58, v45, &v47)
          && (Microsoft_User_Experience_Virtualization_App_AgentEnableBits & 4) != 0 )
        {
          v18 = v58;
          if ( v58[3] > 7u )
            v18 = (_QWORD *)v58[0];
          McTemplateU0zq_EventWriteTransfer(v17, TemplateMsg_CantGetTemplateEnabled, v18, (unsigned int)v47);
        }
        if ( v45[0] )
        {
          v16 = v46;
LABEL_19:
          v19 = (void (__fastcall ***)(_QWORD, __int64))v16[13];
          v16[13] = 0;
          v20 = v19;
          v50 = v19;
          if ( v19 )
          {
            if ( *((_QWORD *)&v48 + 1) == v49 )
            {
              std::vector<std::unique_ptr<Uev::ITemplate>>::_Emplace_reallocate<std::unique_ptr<Uev::ITemplate>>(
                &v48,
                *((_QWORD *)&v48 + 1),
                &v50);
              v20 = v50;
            }
            else
            {
              v20 = 0;
              v50 = 0;
              **((_QWORD **)&v48 + 1) = v19;
              *((_QWORD *)&v48 + 1) += 8LL;
            }
          }
          v14 = 0;
          v51 = 0;
          v39 = v15;
          if ( *((_QWORD *)&v48 + 1) == v49 )
          {
            std::vector<std::unique_ptr<Uev::ITemplate>>::_Emplace_reallocate<std::unique_ptr<Uev::ITemplate>>(
              &v48,
              *((_QWORD *)&v48 + 1),
              &v39);
            v21 = v39;
          }
          else
          {
            v21 = 0;
            **((_QWORD **)&v48 + 1) = v15;
            *((_QWORD *)&v48 + 1) += 8LL;
          }
          if ( v21 )
            (**(void (__fastcall ***)(Uev::Template *, __int64))v21)(v21, 1);
          if ( v20 )
            (**v20)(v20, 1);
        }
        std::wstring::_Tidy_deallocate(v58);
      }
      if ( v14 )
        (**(void (__fastcall ***)(Uev::Template *, __int64))v14)(v14, 1);
    }
    v4 = a4;
LABEL_35:
    if ( v13 )
      (**v13)(v13, 1);
  }
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v52 = 0;
  v53 = 0;
  for ( j = (Uev::Template **)v48; j != *((Uev::Template ***)&v48 + 1); ++j )
  {
    v23 = (*(__int64 (__fastcall **)(Uev::Template *))(*(_QWORD *)*j + 72LL))(*j);
    v24 = *j;
    *j = 0;
    v39 = v24;
    v25 = &v54;
    if ( !v23 )
      v25 = &v56;
    Uev::TemplateManager::AddProperTemplate(a1, v25, &v52, &v39);
  }
  std::vector<std::unique_ptr<Uev::ITemplate>>::_Insert_counted_range<std::move_iterator<std::unique_ptr<Uev::ITemplate> *>>(
    &v54,
    *((_QWORD *)&v54 + 1),
    v56,
    (__int64)(*((_QWORD *)&v56 + 1) - v56) >> 3);
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v40 = 1;
  for ( k = (void (__fastcall ****)(_QWORD, __int64))v54; k != *((void (__fastcall *****)(_QWORD, __int64))&v54 + 1); ++k )
  {
    v27 = *k;
    if ( *k )
    {
      *k = 0;
      v46 = v27;
      v29 = (_QWORD *)*((_QWORD *)&v52 + 1);
      v28 = (_QWORD *)v52;
      if ( (_QWORD)v52 == *((_QWORD *)&v52 + 1) )
        goto LABEL_60;
      do
      {
        v30 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*v28 + 16LL))(*v28, v58);
        v31 = ((__int64 (__fastcall *)(_QWORD, _BYTE *))(*v46)[2])(v46, Src);
        v32 = *(_QWORD *)(v31 + 16);
        if ( *(_QWORD *)(v31 + 24) > 7u )
          v31 = *(_QWORD *)v31;
        v33 = *(_QWORD *)(v30 + 16);
        if ( *(_QWORD *)(v30 + 24) > 7u )
          v30 = *(_QWORD *)v30;
        v34 = v32;
        if ( v32 >= v33 )
          v34 = v33;
        v35 = wmemcmp((const wchar_t *)v30, (const wchar_t *)v31, v34);
        if ( !v35 )
        {
          if ( v33 >= v32 )
            v35 = v33 > v32;
          else
            v35 = -1;
        }
        std::wstring::_Tidy_deallocate(Src);
        std::wstring::_Tidy_deallocate(v58);
        if ( !v35 )
          break;
        ++v28;
      }
      while ( v28 != v29 );
      v27 = v46;
      if ( v28 == *((_QWORD **)&v52 + 1) )
      {
LABEL_60:
        v36 = (_QWORD *)a2[1];
        if ( v36 == (_QWORD *)a2[2] )
        {
          std::vector<std::unique_ptr<Uev::ITemplate>>::_Emplace_reallocate<std::unique_ptr<Uev::ITemplate>>(
            a2,
            v36,
            &v46);
        }
        else
        {
          v46 = 0;
          *v36 = v27;
          a2[1] += 8LL;
        }
        v27 = v46;
      }
      if ( v27 )
        (**v27)(v27, 1);
    }
  }
  std::vector<std::unique_ptr<Uev::ITemplate>>::~vector<std::unique_ptr<Uev::ITemplate>>(&v52);
  std::vector<std::unique_ptr<Uev::ITemplate>>::~vector<std::unique_ptr<Uev::ITemplate>>(&v56);
  std::vector<std::unique_ptr<Uev::ITemplate>>::~vector<std::unique_ptr<Uev::ITemplate>>(&v54);
  if ( hLibModule )
    FreeLibrary(hLibModule);
  std::vector<std::unique_ptr<Uev::ITemplate>>::~vector<std::unique_ptr<Uev::ITemplate>>(&v48);
  std::vector<std::wstring>::_Tidy(v59);
  v60[0] = &Uev::TemplateIndex::`vftable';
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(v62);
  std::list<std::pair<std::wstring const,std::wstring>>::~list<std::pair<std::wstring const,std::wstring>>(v61);
  return a2;
}

```

## disassembly

```asm
0x140035b48  push    rbp
0x140035b4a  push    rbx
0x140035b4b  push    rsi
0x140035b4c  push    rdi
0x140035b4d  push    r12
0x140035b4f  push    r13
0x140035b51  push    r14
0x140035b53  push    r15
0x140035b55  lea     rbp, [rsp-98h]
0x140035b5d  sub     rsp, 198h
0x140035b64  mov     rax, cs:__security_cookie
0x140035b6b  xor     rax, rsp
0x140035b6e  mov     [rbp+0D0h+var_50], rax
0x140035b75  mov     dil, r9b
0x140035b78  mov     [rsp+1D0h+var_1B0], r9b
0x140035b7d  mov     r13, r8
0x140035b80  mov     r12, rdx
0x140035b83  mov     r15, rcx
0x140035b86  mov     [rsp+1D0h+var_190], rdx
0x140035b8b  xor     r14d, r14d
0x140035b8e  mov     [rsp+1D0h+var_1A0], r14d
0x140035b93  lea     rcx, [rbp+0D0h+var_A0]; this
0x140035b97  call    ??0TemplateIndex@Uev@@QEAA@XZ; Uev::TemplateIndex::TemplateIndex(void)
0x140035b9c  nop
0x140035b9d  lea     rcx, [rbp+0D0h+var_A0]; this
0x140035ba1  call    ?LoadIndex@TemplateIndex@Uev@@QEAAXXZ; Uev::TemplateIndex::LoadIndex(void)
0x140035ba6  mov     r8, r13
0x140035ba9  lea     rdx, [rbp+0D0h+var_C0]
0x140035bad  lea     rcx, [rbp+0D0h+var_A0]
0x140035bb1  call    ?FindTemplateIDs@TemplateIndex@Uev@@QEBA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Uev::TemplateIndex::FindTemplateIDs(std::wstring const &)
0x140035bb6  nop
0x140035bb7  xorps   xmm0, xmm0
0x140035bba  movdqu  [rbp+0D0h+var_150], xmm0
0x140035bbf  mov     [rbp+0D0h+var_140], r14
0x140035bc3  xor     edx, edx; hFile
0x140035bc5  mov     r8d, 800h; dwFlags
0x140035bcb  lea     rcx, LibFileName; "msxml6"
0x140035bd2  call    cs:__imp_LoadLibraryExW
0x140035bd8  mov     [rsp+1D0h+hLibModule], rax
0x140035bdd  mov     rbx, [rbp+0D0h+var_C0]
0x140035be1  cmp     rbx, [rbp+0D0h+var_B8]
0x140035be5  jz      loc_140035E32
0x140035beb  mov     rdx, rbx
0x140035bee  lea     rcx, [rsp+1D0h+Src]; Src
0x140035bf3  call    ?GetTemplateFilenameForId@TemplateAdministrator@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV34@@Z; Uev::TemplateAdministrator::GetTemplateFilenameForId(std::wstring const &)
0x140035bf8  nop
0x140035bf9  mov     r8b, dil
0x140035bfc  mov     rdx, rax
0x140035bff  lea     rcx, [rsp+1D0h+var_160]
0x140035c04  call    ?CreateTemplateSuite@TemplateSuite@Uev@@SA?AV?$unique_ptr@VTemplateSuite@Uev@@U?$default_delete@VTemplateSuite@Uev@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@_N@Z; Uev::TemplateSuite::CreateTemplateSuite(std::wstring const &,bool)
0x140035c09  nop
0x140035c0a  lea     rcx, [rsp+1D0h+Src]
0x140035c0f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140035c14  mov     [rsp+1D0h+var_168], 1
0x140035c19  mov     [rsp+1D0h+var_158], r14
0x140035c1e  mov     rdx, [rsp+1D0h+var_160]
0x140035c23  add     rdx, 8
0x140035c27  mov     rcx, [r15+8]
0x140035c2b  add     rcx, 0CF0h
0x140035c32  lea     r9, [rsp+1D0h+var_158]
0x140035c37  lea     r8, [rsp+1D0h+var_168]
0x140035c3c  call    ?Get@?$SettingGroup@_N@Uev@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEA_NAEAUSettingInfo@2@@Z; Uev::SettingGroup<bool>::Get(std::wstring const &,bool &,Uev::SettingInfo &)
0x140035c41  test    al, al
0x140035c43  jnz     short loc_140035C72
0x140035c45  test    cs:Microsoft_User_Experience_Virtualization_App_AgentEnableBits, 4
0x140035c4c  jz      short loc_140035C72
0x140035c4e  mov     r8, [rsp+1D0h+var_160]
0x140035c53  add     r8, 8
0x140035c57  cmp     qword ptr [r8+18h], 7
0x140035c5c  jbe     short loc_140035C61
0x140035c5e  mov     r8, [r8]
0x140035c61  mov     r9d, dword ptr [rsp+1D0h+var_158]
0x140035c66  lea     rdx, TemplateMsg_CantGetTemplateEnabled
0x140035c6d  call    McTemplateU0zq_EventWriteTransfer
0x140035c72  cmp     [rsp+1D0h+var_168], r14b
0x140035c77  jz      loc_140035E08
0x140035c7d  mov     rcx, [rsp+1D0h+var_160]
0x140035c82  cmp     [rcx+90h], r14
0x140035c89  jz      loc_140035E0F
0x140035c8f  lea     rdx, [rbp+0D0h+var_130]
0x140035c93  call    ?PullNextApplicationTemplate@TemplateSuite@Uev@@QEAA?AV?$unique_ptr@VTemplate@Uev@@U?$default_delete@VTemplate@Uev@@@std@@@std@@XZ; Uev::TemplateSuite::PullNextApplicationTemplate(void)
0x140035c98  nop
0x140035c99  mov     rdx, r13; struct Uev::ProgramCharacteristics *
0x140035c9c  mov     rsi, [rbp+0D0h+var_130]
0x140035ca0  mov     rcx, rsi; this
0x140035ca3  call    ?Matches@Template@Uev@@QEBA_NAEBUProgramCharacteristics@2@@Z; Uev::Template::Matches(Uev::ProgramCharacteristics const &)
0x140035ca8  test    al, al
0x140035caa  jz      loc_140035DE7
0x140035cb0  mov     r14, rsi
0x140035cb3  mov     rax, [rsi]
0x140035cb6  lea     rdx, [rbp+0D0h+var_E0]
0x140035cba  mov     rcx, rsi
0x140035cbd  mov     rax, [rax+10h]
0x140035cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035cc6  nop
0x140035cc7  mov     [rsp+1D0h+var_167], 1
0x140035ccc  mov     rax, [rsp+1D0h+var_160]
0x140035cd1  cmp     byte ptr [rax+60h], 0
0x140035cd5  jnz     short loc_140035D31
0x140035cd7  mov     rcx, [r15+8]
0x140035cdb  add     rcx, 0CF0h
0x140035ce2  lea     r9, [rsp+1D0h+var_158]
0x140035ce7  lea     r8, [rsp+1D0h+var_167]
0x140035cec  lea     rdx, [rbp+0D0h+var_E0]
0x140035cf0  call    ?Get@?$SettingGroup@_N@Uev@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEA_NAEAUSettingInfo@2@@Z; Uev::SettingGroup<bool>::Get(std::wstring const &,bool &,Uev::SettingInfo &)
0x140035cf5  test    al, al
0x140035cf7  jnz     short loc_140035D21
0x140035cf9  test    cs:Microsoft_User_Experience_Virtualization_App_AgentEnableBits, 4
0x140035d00  jz      short loc_140035D21
0x140035d02  lea     r8, [rbp+0D0h+var_E0]
0x140035d06  cmp     [rbp+0D0h+var_C8], 7
0x140035d0b  cmova   r8, [rbp+0D0h+var_E0]
0x140035d10  mov     r9d, dword ptr [rsp+1D0h+var_158]
0x140035d15  lea     rdx, TemplateMsg_CantGetTemplateEnabled
0x140035d1c  call    McTemplateU0zq_EventWriteTransfer
0x140035d21  cmp     [rsp+1D0h+var_167], 0
0x140035d26  jz      loc_140035DDA
0x140035d2c  mov     rax, [rsp+1D0h+var_160]
0x140035d31  mov     rcx, [rax+68h]
0x140035d35  mov     qword ptr [rax+68h], 0
0x140035d3d  mov     rdi, rcx
0x140035d40  mov     [rbp+0D0h+var_138], rcx
0x140035d44  test    rcx, rcx
0x140035d47  jz      short loc_140035D74
0x140035d49  mov     rdx, qword ptr [rbp+0D0h+var_150+8]
0x140035d4d  cmp     rdx, [rbp+0D0h+var_140]
0x140035d51  jz      short loc_140035D63
0x140035d53  xor     edi, edi
0x140035d55  mov     [rbp+0D0h+var_138], rdi
0x140035d59  mov     [rdx], rcx
0x140035d5c  add     qword ptr [rbp+0D0h+var_150+8], 8
0x140035d61  jmp     short loc_140035D74
0x140035d63  lea     r8, [rbp+0D0h+var_138]
0x140035d67  lea     rcx, [rbp+0D0h+var_150]
0x140035d6b  call    ??$_Emplace_reallocate@V?$unique_ptr@VITemplate@Uev@@U?$default_delete@VITemplate@Uev@@@std@@@std@@@?$vector@V?$unique_ptr@VITemplate@Uev@@U?$default_delete@VITemplate@Uev@@@std@@@std@@V?$allocator@V?$unique_ptr@VITemplate@Uev@@U?$default_delete@VITemplate@Uev@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VITemplate@Uev@@U?$default_delete@VITemplate@Uev@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<Uev::ITemplate>>::_Emplace_reallocate<std::unique_ptr<Uev::ITemplate>>(std::unique_ptr<Uev::ITemplate> * const,std::unique_ptr<Uev::ITemplate> &&)
0x140035d70  mov     rdi, [rbp+0D0h+var_138]
0x140035d74  xor     esi, esi
0x140035d76  mov     [rbp+0D0h+var_130], rsi
0x140035d7a  mov     [rsp+1D0h+var_1A8], r14
0x140035d7f  mov     rdx, qword ptr [rbp+0D0h+var_150+8]
0x140035d83  cmp     rdx, [rbp+0D0h+var_140]
0x140035d87  jz      short loc_140035D95
0x140035d89  xor     ecx, ecx
0x140035d8b  mov     [rdx], r14
0x140035d8e  add     qword ptr [rbp+0D0h+var_150+8], 8
0x140035d93  jmp     short loc_140035DA8
0x140035d95  lea     r8, [rsp+1D0h+var_1A8]
0x140035d9a  lea     rcx, [rbp+0D0h+var_150]
0x140035d9e  call    ??$_Emplace_reallocate@V?$unique_ptr@VITemplate@Uev@@U?$default_delete@VITemplate@Uev@@@std@@@std@@@?$vector@V?$unique_ptr@VITemplate@Uev@@U?$default_delete@VITemplate@Uev@@@std@@@std@@V?$allocator@V?$unique_ptr@VITemplate@Uev@@U?$default_delete@VITemplate@Uev@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VITemplate@Uev@@U?$default_delete@VITemplate@Uev@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<Uev::ITemplate>>::_Emplace_reallocate<std::unique_ptr<Uev::ITemplate>>(std::unique_ptr<Uev::ITemplate> * const,std::unique_ptr<Uev::ITemplate> &&)
0x140035da3  mov     rcx, [rsp+1D0h+var_1A8]
0x140035da8  xor     r14d, r14d
0x140035dab  test    rcx, rcx
0x140035dae  jz      short loc_140035DC0
0x140035db0  mov     rax, [rcx]
0x140035db3  lea     edx, [r14+1]
0x140035db7  mov     rax, [rax]
0x140035dba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035dbf  nop
0x140035dc0  test    rdi, rdi
0x140035dc3  jz      short loc_140035DDD
0x140035dc5  mov     rax, [rdi]
0x140035dc8  mov     edx, 1
0x140035dcd  mov     rcx, rdi
0x140035dd0  mov     rax, [rax]
0x140035dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035dd8  jmp     short loc_140035DDD
0x140035dda  xor     r14d, r14d
0x140035ddd  lea     rcx, [rbp+0D0h+var_E0]
0x140035de1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140035de6  nop
0x140035de7  test    rsi, rsi
0x140035dea  jz      loc_140035C7D
0x140035df0  mov     rax, [rsi]
0x140035df3  mov     edx, 1
0x140035df8  mov     rcx, rsi
0x140035dfb  mov     rax, [rax]
0x140035dfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035e03  jmp     loc_140035C7D
0x140035e08  mov     rcx, [rsp+1D0h+var_160]
0x140035e0d  jmp     short loc_140035E14
0x140035e0f  mov     dil, [rsp+1D0h+var_1B0]
0x140035e14  test    rcx, rcx
0x140035e17  jz      short loc_140035E29
0x140035e19  mov     rax, [rcx]
0x140035e1c  mov     edx, 1
0x140035e21  mov     rax, [rax]
0x140035e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035e29  add     rbx, 20h ; ' '
0x140035e2d  jmp     loc_140035BE1
0x140035e32  xorps   xmm0, xmm0
0x140035e35  movdqu  [rbp+0D0h+var_110], xmm0
0x140035e3a  mov     [rbp+0D0h+var_100], r14
0x140035e3e  movdqu  [rbp+0D0h+var_F8], xmm0
0x140035e43  mov     [rbp+0D0h+var_E8], r14
0x140035e47  movdqu  [rbp+0D0h+var_128], xmm0
0x140035e4c  mov     [rbp+0D0h+var_118], r14
0x140035e50  mov     rbx, qword ptr [rbp+0D0h+var_150]
0x140035e54  cmp     rbx, qword ptr [rbp+0D0h+var_150+8]
0x140035e58  jz      short loc_140035E97
0x140035e5a  mov     rcx, [rbx]
0x140035e5d  mov     rax, [rcx]
0x140035e60  mov     rax, [rax+48h]
0x140035e64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035e69  mov     rcx, [rbx]
0x140035e6c  mov     [rbx], r14
0x140035e6f  mov     [rsp+1D0h+var_1A8], rcx
0x140035e74  lea     r9, [rsp+1D0h+var_1A8]
0x140035e79  lea     r8, [rbp+0D0h+var_128]
0x140035e7d  mov     rcx, r15
0x140035e80  test    al, al
0x140035e82  lea     rdx, [rbp+0D0h+var_110]
0x140035e86  jnz     short loc_140035E8C
0x140035e88  lea     rdx, [rbp+0D0h+var_F8]
0x140035e8c  call    ?AddProperTemplate@TemplateManager@Uev@@AEBAXAEAV?$vector@V?$unique_ptr@VITemplate@Uev@@U?$default_delete@VITemplate@Uev@@@std@@@std@@V?$allocator@V?$unique_ptr@VITemplate@Uev@@U?$default_delete@VITemplate@Uev@@@std@@@std@@@2@@std@@0V?$unique_ptr@VITemplate@Uev@@U?$default_delete@VITemplate@Uev@@@std@@@4@@Z; Uev::TemplateManager::AddProperTemplate(std::vector<std::unique_ptr<Uev::ITemplate>> &,std::vector<std::unique_ptr<Uev::ITemplate>> &,std::unique_ptr<Uev::ITemplate>)
0x140035e91  add     rbx, 8
0x140035e95  jmp     short loc_140035E54
0x140035e97  mov     r8, qword ptr [rbp+0D0h+var_F8]
0x140035e9b  mov     r9, qword ptr [rbp+0D0h+var_F8+8]
0x140035e9f  sub     r9, r8
0x140035ea2  sar     r9, 3
0x140035ea6  mov     rdx, qword ptr [rbp+0D0h+var_110+8]
0x140035eaa  lea     rcx, [rbp+0D0h+var_110]
0x140035eae  call    ??$_Insert_counted_range@V?$move_iterator@PEAV?$unique_ptr@VITemplate@Uev@@U?$default_delete@VITemplate@Uev@@@std@@@std@@@std@@@?$vector@V?$unique_ptr@VITemplate@Uev@@U?$default_delete@VITemplate@Uev@@@std@@@std@@V?$allocator@V?$unique_ptr@VITemplate@Uev@@U?$default_delete@VITemplate@Uev@@@std@@@std@@@2@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$unique_ptr@VITemplate@Uev@@U?$default_delete@VITemplate@Uev@@@std@@@std@@@std@@@std@@@1@V?$move_iterator@PEAV?$unique_ptr@VITemplate@Uev@@U?$default_delete@VITemplate@Uev@@@std@@@std@@@1@_K@Z; std::vector<std::unique_ptr<Uev::ITemplate>>::_Insert_counted_range<std::move_iterator<std::unique_ptr<Uev::ITemplate> *>>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::unique_ptr<Uev::ITemplate>>>>,std::move_iterator<std::unique_ptr<Uev::ITemplate> *>,unsigned __int64)
0x140035eb3  mov     [r12], r14
0x140035eb7  mov     [r12+8], r14
0x140035ebc  mov     [r12+10h], r14
0x140035ec1  mov     [rsp+1D0h+var_1A0], 1
0x140035ec9  mov     rbx, qword ptr [rbp+0D0h+var_110]
0x140035ecd  cmp     rbx, qword ptr [rbp+0D0h+var_110+8]
0x140035ed1  jz      loc_140035FFC
0x140035ed7  mov     rcx, [rbx]
0x140035eda  test    rcx, rcx
0x140035edd  jz      loc_140035FF3
0x140035ee3  mov     [rbx], r14
0x140035ee6  mov     [rsp+1D0h+var_160], rcx
0x140035eeb  mov     rdi, qword ptr [rbp+0D0h+var_128]
0x140035eef  mov     r14, qword ptr [rbp+0D0h+var_128+8]
0x140035ef3  cmp     rdi, r14
0x140035ef6  jz      loc_140035FA5
0x140035efc  mov     rcx, [rdi]
0x140035eff  mov     rax, [rcx]
0x140035f02  lea     rdx, [rbp+0D0h+var_E0]
0x140035f06  mov     rax, [rax+10h]
0x140035f0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035f0f  mov     rsi, rax
0x140035f12  mov     rcx, [rsp+1D0h+var_160]
0x140035f17  mov     rax, [rcx]
0x140035f1a  lea     rdx, [rsp+1D0h+Src]
0x140035f1f  mov     rax, [rax+10h]
0x140035f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035f28  mov     r13, [rax+10h]
0x140035f2c  cmp     qword ptr [rax+18h], 7
0x140035f31  jbe     short loc_140035F36
0x140035f33  mov     rax, [rax]
0x140035f36  mov     r15, [rsi+10h]
0x140035f3a  cmp     qword ptr [rsi+18h], 7
0x140035f3f  jbe     short loc_140035F44
0x140035f41  mov     rsi, [rsi]
0x140035f44  mov     r8, r13
0x140035f47  cmp     r13, r15
0x140035f4a  cmovnb  r8, r15; N
0x140035f4e  mov     rdx, rax; S2
0x140035f51  mov     rcx, rsi; S1
0x140035f54  call    wmemcmp
0x140035f59  mov     esi, eax
0x140035f5b  test    eax, eax
0x140035f5d  jnz     short loc_140035F72
0x140035f5f  cmp     r15, r13
0x140035f62  jnb     short loc_140035F69
0x140035f64  or      esi, 0FFFFFFFFh
0x140035f67  jmp     short loc_140035F72
0x140035f69  xor     esi, esi
0x140035f6b  cmp     r15, r13
0x140035f6e  setnbe  sil
0x140035f72  lea     rcx, [rsp+1D0h+Src]
0x140035f77  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140035f7c  nop
0x140035f7d  lea     rcx, [rbp+0D0h+var_E0]
0x140035f81  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140035f86  test    esi, esi
0x140035f88  jz      short loc_140035F97
0x140035f8a  add     rdi, 8
0x140035f8e  cmp     rdi, r14
0x140035f91  jnz     loc_140035EFC
0x140035f97  mov     r14, qword ptr [rbp+0D0h+var_128+8]
0x140035f9b  mov     rcx, [rsp+1D0h+var_160]
0x140035fa0  cmp     rdi, r14
0x140035fa3  jnz     short loc_140035FDB
0x140035fa5  mov     rdx, [r12+8]
0x140035faa  cmp     rdx, [r12+10h]
0x140035faf  jz      short loc_140035FC9
0x140035fb1  xor     r14d, r14d
0x140035fb4  mov     [rsp+1D0h+var_160], r14
0x140035fb9  mov     [rdx], rcx
0x140035fbc  add     qword ptr [r12+8], 8
0x140035fc2  mov     rcx, [rsp+1D0h+var_160]
0x140035fc7  jmp     short loc_140035FDE
0x140035fc9  lea     r8, [rsp+1D0h+var_160]
0x140035fce  mov     rcx, r12
0x140035fd1  call    ??$_Emplace_reallocate@V?$unique_ptr@VITemplate@Uev@@U?$default_delete@VITemplate@Uev@@@std@@@std@@@?$vector@V?$unique_ptr@VITemplate@Uev@@U?$default_delete@VITemplate@Uev@@@std@@@std@@V?$allocator@V?$unique_ptr@VITemplate@Uev@@U?$default_delete@VITemplate@Uev@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VITemplate@Uev@@U?$default_delete@VITemplate@Uev@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<Uev::ITemplate>>::_Emplace_reallocate<std::unique_ptr<Uev::ITemplate>>(std::unique_ptr<Uev::ITemplate> * const,std::unique_ptr<Uev::ITemplate> &&)
  ... truncated ...
```
