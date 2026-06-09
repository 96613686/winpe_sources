# MpWatchDog::CMpWdEcsRemediationManager::HandleRemediationPayload(char const *,wchar_t const *,wchar_t const *,bool)

- ea: `0x1400c38c4`
- end: `0x1400c4374`
- name: `?HandleRemediationPayload@CMpWdEcsRemediationManager@MpWatchDog@@QEAAJPEBDPEB_W1_N@Z`
- size: `2736`
- prototype: `__int64 __fastcall(MpWatchDog::CMpWdEcsRemediationManager *this, const char *, wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `35`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14009e52c`

## callees

- `0x140017a98`
- `0x14001cd4c`
- `0x14001cd94`
- `0x14001cdc0`
- `0x14001d200`
- `0x14003a5c0`
- `0x14007d1e0`
- `0x14007d210`
- `0x14007e088`
- `0x140081fc8`
- `0x1400833d4`
- `0x140084a18`
- `0x140084a8c`
- `0x140085218`
- `0x140085d38`
- `0x140085d94`
- `0x14008d1fc`
- `0x14008d34c`
- `0x14008f950`
- `0x14009d4d0`
- `0x1400b6174`
- `0x1400b75d0`
- `0x1400be154`
- `0x1400c205c`
- `0x1400c38c4`
- `0x1400c52d0`
- `0x1400c5d60`
- `0x1400c6120`
- `0x1400cdfa0`
- `0x1400f9e78`
- `0x1400fab00`
- `0x1400fb44c`
- `0x1400fd420`
- `0x140166250`
- `0x140166990`

## import_xrefs

- `KERNEL32!DebugBreak` at `0x1400c3996`
- `KERNEL32!DebugBreak` at `0x1400c3996`

## string_xrefs

- `0x1400c3eab`: `SOFTWARE\Microsoft\Windows Defender\CoreService\Remediations`
- `0x1400c41a4`: `SOFTWARE\Microsoft\Windows Defender\CoreService\Remediations`
- `0x1400c3f14`: `LastUpdateTimeUTC`
- `0x1400c420d`: `LastUpdateTimeUTC`
- `0x1400c432c`: `Left-over characters in stream after parsing a JSON value`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall MpWatchDog::CMpWdEcsRemediationManager::HandleRemediationPayload(
        MpWatchDog::CMpWdEcsRemediationManager *this,
        const char *a2,
        wchar_t *a3,
        wchar_t *a4)
{
  int v6; // r12d
  __int64 v8; // r8
  unsigned int v9; // r8d
  MpWatchDog *v10; // rcx
  __int64 v11; // rbx
  __int64 v12; // rdi
  char **v13; // rax
  __int64 v14; // rcx
  unsigned int v15; // edi
  const char *v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rdx
  char **v19; // rcx
  __int64 *v20; // rax
  __int64 v21; // rbx
  int v22; // r12d
  unsigned int v23; // r12d
  char ***v24; // rax
  char **v25; // rdi
  _QWORD *v26; // r8
  wchar_t *v27; // rax
  MpWatchDog::CMpWdEcsRemediationManager *v28; // rcx
  int v29; // eax
  unsigned int v30; // r12d
  int updated; // eax
  _Mtx_t v32; // r12
  __int64 v33; // r8
  wchar_t *v34; // r12
  __int64 v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rdx
  bool v41; // [rsp+30h] [rbp-318h] BYREF
  int v42; // [rsp+34h] [rbp-314h]
  int v43; // [rsp+38h] [rbp-310h]
  int v44; // [rsp+3Ch] [rbp-30Ch]
  int v45; // [rsp+40h] [rbp-308h]
  int v46; // [rsp+44h] [rbp-304h]
  int v47; // [rsp+48h] [rbp-300h]
  wchar_t *v48; // [rsp+50h] [rbp-2F8h]
  __int64 v49; // [rsp+58h] [rbp-2F0h]
  _Mtx_t v50; // [rsp+60h] [rbp-2E8h]
  MpWatchDog::CMpWdEcsRemediationManager *v51; // [rsp+68h] [rbp-2E0h]
  char *v52; // [rsp+70h] [rbp-2D8h]
  char **v53; // [rsp+78h] [rbp-2D0h]
  MpWatchDog::CMpWdEcsRemediationManager *v54; // [rsp+80h] [rbp-2C8h]
  __int64 v55; // [rsp+88h] [rbp-2C0h]
  _Mtx_t v56; // [rsp+90h] [rbp-2B8h]
  _BYTE v57[16]; // [rsp+A8h] [rbp-2A0h] BYREF
  unsigned int v58; // [rsp+B8h] [rbp-290h] BYREF
  char **v59; // [rsp+C0h] [rbp-288h] BYREF
  wchar_t *v60; // [rsp+C8h] [rbp-280h] BYREF
  char *v61[2]; // [rsp+D0h] [rbp-278h] BYREF
  __int128 v62; // [rsp+E0h] [rbp-268h]
  void **v63; // [rsp+F0h] [rbp-258h] BYREF
  __int64 v64; // [rsp+F8h] [rbp-250h]
  __int64 v65; // [rsp+100h] [rbp-248h]
  const wchar_t *v66; // [rsp+108h] [rbp-240h]
  const wchar_t *v67; // [rsp+110h] [rbp-238h]
  const wchar_t *v68; // [rsp+118h] [rbp-230h]
  const wchar_t *v69; // [rsp+120h] [rbp-228h]
  const wchar_t *v70; // [rsp+128h] [rbp-220h]
  const wchar_t *v71; // [rsp+130h] [rbp-218h]
  const wchar_t *v72; // [rsp+138h] [rbp-210h]
  _OWORD v73[2]; // [rsp+140h] [rbp-208h] BYREF
  _QWORD v74[4]; // [rsp+160h] [rbp-1E8h] BYREF
  int v75; // [rsp+180h] [rbp-1C8h] BYREF
  __int128 v76; // [rsp+188h] [rbp-1C0h] BYREF
  __int64 v77; // [rsp+198h] [rbp-1B0h]
  __int64 v78; // [rsp+1A0h] [rbp-1A8h]
  int v79; // [rsp+1C8h] [rbp-180h] BYREF
  void ***v80; // [rsp+1D0h] [rbp-178h]
  _QWORD v81[38]; // [rsp+1E0h] [rbp-168h] BYREF

  v48 = a4;
  v60 = a3;
  v50 = this;
  v54 = this;
  v51 = this;
  v6 = 0;
  v43 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 21, &WPP_5083a01b0eaf30ea0f7f8169c36bccb6_Traceguids);
  if ( !a2 )
    return 2147942487LL;
  *(_OWORD *)v61 = 0;
  v62 = 0;
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  std::string::_Construct<1,char const *>(v61, a2);
  if ( MpWatchDog::GetMiscConfigDword((HKEY)&stru_14019B1D0, 0, v9) == 1 )
    DebugBreak();
  v55 = 0;
  if ( MpWatchDog::MpIsCoreSvcInDevMode(v10) )
  {
    v11 = *((_QWORD *)this + 21);
    v12 = *((_QWORD *)this + 22);
    while ( v11 != v12 )
    {
      v13 = v61;
      if ( *((_QWORD *)&v62 + 1) > 0xFu )
        v13 = (char **)v61[0];
      v59 = v13;
      v14 = *(_QWORD *)(v11 + 56);
      if ( !v14 )
        std::_Xbad_function_call();
      (*(void (__fastcall **)(__int64, _OWORD *, char ***))(*(_QWORD *)v14 + 16LL))(v14, v73, &v59);
      v6 |= 1u;
      v43 = v6;
      std::string::operator=(v61);
      std::string::_Tidy_deallocate(v73);
      v11 += 64;
    }
  }
  if ( (unsigned __int64)v62 < 3 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 23, &WPP_5083a01b0eaf30ea0f7f8169c36bccb6_Traceguids);
    v15 = -2147024883;
    goto LABEL_47;
  }
  if ( (unsigned __int8)MpWatchDog::WdConfigManager::IsKillbitGatedFeatureEnabled(MpWatchDog::gMpWdConfigManager, 224) )
  {
    v16 = (const char *)v61;
    if ( *((_QWORD *)&v62 + 1) > 0xFu )
      v16 = v61[0];
    if ( !MpWatchDog::CMpWdEcsRemediationManager::ValidatePayloadSignature(v16, v60, v48) )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 24, &WPP_5083a01b0eaf30ea0f7f8169c36bccb6_Traceguids);
      v15 = -2146893041;
      goto LABEL_47;
    }
    v17 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
      goto LABEL_37;
    v18 = 25;
  }
  else
  {
    v17 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
      goto LABEL_37;
    v18 = 26;
  }
  WPP_SF_(*(_QWORD *)(v17 + 16), v18, &WPP_5083a01b0eaf30ea0f7f8169c36bccb6_Traceguids);
LABEL_37:
  v42 = 0;
  v46 = 0;
  v49 = 0;
  v64 = 1;
  v65 = 1;
  v66 = 0;
  v63 = &web::json::details::JSON_StringParser<char>::`vftable';
  v19 = v61;
  if ( *((_QWORD *)&v62 + 1) > 0xFu )
    v19 = (char **)v61[0];
  v67 = (const wchar_t *)v19;
  v68 = (const wchar_t *)v19;
  v69 = (const wchar_t *)((char *)v19 + v62);
  v75 = 0;
  v76 = 0;
  v77 = 0;
  v78 = 15;
  LOBYTE(v76) = 0;
  v79 = 0;
  v80 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  web::json::details::JSON_Parser<char>::GetNextToken(&v63, &v75);
  if ( v79 )
  {
    v37 = std::error_code::message(&v79, v73);
    v38 = utility::conversions::to_string_t(v74, v37);
    web::json::details::CreateException<web::json::details::JSON_Parser<char>::Token>(&v75, v38);
  }
  v49 = 0;
  v20 = (__int64 *)web::json::details::JSON_Parser<char>::_ParseValue(&v63, &v59, &v75);
  v21 = *v20;
  *v20 = 0;
  v49 = v21;
  v22 = v6 | 0xC;
  v43 = v22;
  if ( v79 )
  {
    v39 = std::error_code::message(&v79, v73);
    v40 = utility::conversions::to_string_t(v74, v39);
    web::json::details::CreateException<web::json::details::JSON_Parser<char>::Token>(&v75, v40);
  }
  if ( v75 )
  {
    std::wstring::wstring(v73, L"Left-over characters in stream after parsing a JSON value");
    web::json::details::CreateException<web::json::details::JSON_Parser<char>::Token>(&v75, v73);
  }
  std::string::_Tidy_deallocate(&v76);
  v23 = v22 & 0xFFFFFFF9 | 2;
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v21 + 88LL))(v21) != 4 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 27, &WPP_5083a01b0eaf30ea0f7f8169c36bccb6_Traceguids);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 192LL))(v21, 1);
    std::string::_Tidy_deallocate(v61);
    return 2147942413LL;
  }
  v24 = (char ***)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 152LL))(v21);
  v25 = *v24;
  v53 = v24[1];
  while ( 1 )
  {
    v59 = v25;
    if ( v25 == v53 )
      break;
    v60 = 0;
    (**(void (__fastcall ***)(char *, wchar_t **))*v25)(*v25, &v60);
    v47 = ++v42;
    (*(void (__fastcall **)(wchar_t *, _QWORD *))(*(_QWORD *)v60 + 80LL))(v60, v74);
    v45 = v23 | 0x10;
    v43 = v23 | 0x10;
    v58 = 0;
    v26 = v74;
    if ( v74[3] > 7u )
      v26 = (_QWORD *)v74[0];
    MpHashCrc32(&v58, 2LL * v74[2], v26);
    v41 = 0;
    v44 = 0;
    memset(v81, 0, sizeof(v81));
    MpWatchDog::RemediationPayload::from_json(v81, &v60, v58);
    v27 = (wchar_t *)v81;
    if ( v81[3] > 7u )
      v27 = (wchar_t *)v81[0];
    v48 = v27;
    v28 = (MpWatchDog::CMpWdEcsRemediationManager *)WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 28, &WPP_5083a01b0eaf30ea0f7f8169c36bccb6_Traceguids, v27);
    v29 = MpWatchDog::CMpWdEcsRemediationManager::SecuritySanityCheck(
            v28,
            (const struct MpWatchDog::RemediationPayload *)v81);
    v30 = v29;
    v44 = v29;
    if ( v29 >= 0 )
    {
      v63 = (void **)L"Remediations";
      v64 = (__int64)&stru_1401976A0;
      v65 = (__int64)L"SOFTWARE\\Microsoft\\Windows Defender\\CoreService\\Remediations";
      v66 = L"RawContents";
      v67 = L"ScenarioName";
      v68 = L"ExecutionResult";
      v69 = L"ExpiryTimeUTC";
      v70 = L"CreationTimeUTC";
      v71 = L"FirstSeenTimeUTC";
      v72 = L"LastUpdateTimeUTC";
      updated = MpWatchDog::RemediationPayloadMetaStoreManager::UpdateInsertRemediationPayloadMetadata(
                  (MpWatchDog::RemediationPayloadMetaStoreManager *)&v63,
                  (const struct MpWatchDog::RemediationPayload *)v81,
                  &v41);
      v30 = updated;
      v44 = updated;
      if ( updated >= 0 )
      {
        v32 = v50;
        v56 = v50;
        if ( Mtx_lock(v50) )
          std::_Throw_Cpp_error(5);
        if ( *((_DWORD *)v54 + 19) == 0x7FFFFFFF )
        {
          *((_DWORD *)v54 + 19) = 2147483646;
          std::_Throw_Cpp_error(6);
        }
        v52 = (char *)v32 + 80;
        memset(v73, 0, sizeof(v73));
        v33 = -1;
        v34 = v48;
        do
          ++v33;
        while ( v48[v33] );
        std::wstring::_Construct<1,wchar_t const *>(v73, v48, v33);
        std::unordered_map<std::wstring,MpWatchDog::RemediationPayload>::_Insert_or_assign<std::wstring,MpWatchDog::RemediationPayload &>(
          v52,
          v57,
          v73,
          v81);
        std::wstring::_Tidy_deallocate(v73);
        if ( v57[8] )
        {
          v35 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
          {
            v36 = 31;
            goto LABEL_76;
          }
        }
        else
        {
          v35 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
          {
            v36 = 32;
LABEL_76:
            WPP_SF_S(*(_QWORD *)(v35 + 16), v36, &WPP_5083a01b0eaf30ea0f7f8169c36bccb6_Traceguids, v34);
          }
        }
        ++v46;
        v44 = 0;
        Mtx_unlock(v50);
        std::vector<MpWatchDog::RemediationAction>::_Tidy(&v81[34]);
        std::_Optional_destruct_base<MpWatchDog::RemediationFilter,0>::~_Optional_destruct_base<MpWatchDog::RemediationFilter,0>(&v81[6]);
        std::wstring::_Tidy_deallocate(v81);
        goto LABEL_78;
      }
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_Sd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          30,
          (unsigned int)&WPP_5083a01b0eaf30ea0f7f8169c36bccb6_Traceguids,
          (_DWORD)v48,
          updated);
    }
    else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_Sd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        29,
        (unsigned int)&WPP_5083a01b0eaf30ea0f7f8169c36bccb6_Traceguids,
        (_DWORD)v48,
        v29);
    }
    std::vector<MpWatchDog::RemediationAction>::_Tidy(&v81[34]);
    std::_Optional_destruct_base<MpWatchDog::RemediationFilter,0>::~_Optional_destruct_base<MpWatchDog::RemediationFilter,0>(&v81[6]);
    std::wstring::_Tidy_deallocate(v81);
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 36, &WPP_5083a01b0eaf30ea0f7f8169c36bccb6_Traceguids, v30);
    if ( v41 )
    {
      v63 = (void **)L"Remediations";
      v64 = (__int64)&stru_1401976A0;
      v65 = (__int64)L"SOFTWARE\\Microsoft\\Windows Defender\\CoreService\\Remediations";
      v66 = L"RawContents";
      v67 = L"ScenarioName";
      v68 = L"ExecutionResult";
      v69 = L"ExpiryTimeUTC";
      v70 = L"CreationTimeUTC";
      v71 = L"FirstSeenTimeUTC";
      v72 = L"LastUpdateTimeUTC";
      MpWatchDog::RemediationPayloadMetaStoreManager::DiscardRemediationPayloadMetadata(
        (MpWatchDog::RemediationPayloadMetaStoreManager *)&v63,
        v58);
    }
LABEL_78:
    v23 = v45;
    std::wstring::_Tidy_deallocate(v74);
    if ( v60 )
      (*(void (__fastcall **)(wchar_t *, __int64))(*(_QWORD *)v60 + 192LL))(v60, 1);
    ++v25;
  }
  v15 = v46 != v42;
  if ( v21 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 192LL))(v21, 1);
LABEL_47:
  std::string::_Tidy_deallocate(v61);
  return v15;
}

```

## disassembly

```asm
0x1400c38c4  push    rbx
0x1400c38c6  push    rsi
0x1400c38c7  push    rdi
0x1400c38c8  push    r12
0x1400c38ca  push    r13
0x1400c38cc  sub     rsp, 320h
0x1400c38d3  mov     rax, cs:__security_cookie
0x1400c38da  xor     rax, rsp
0x1400c38dd  mov     [rsp+348h+var_38], rax
0x1400c38e5  mov     [rsp+348h+var_2F8], r9
0x1400c38ea  mov     [rsp+348h+var_280], r8
0x1400c38f2  mov     rbx, rdx
0x1400c38f5  mov     rdi, rcx
0x1400c38f8  mov     [rsp+348h+var_2E8], rcx
0x1400c38fd  mov     [rsp+348h+var_2C8], rcx
0x1400c3905  mov     [rsp+348h+var_2E0], rcx
0x1400c390a  xor     esi, esi
0x1400c390c  mov     r12d, esi
0x1400c390f  mov     [rsp+348h+var_310], esi
0x1400c3913  lea     r13, WPP_GLOBAL_Control
0x1400c391a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c3921  cmp     rcx, r13
0x1400c3924  jz      short loc_1400C393F
0x1400c3926  test    byte ptr [rcx+1Ch], 4
0x1400c392a  jz      short loc_1400C393F
0x1400c392c  lea     edx, [rsi+15h]
0x1400c392f  lea     r8, WPP_5083a01b0eaf30ea0f7f8169c36bccb6_Traceguids
0x1400c3936  mov     rcx, [rcx+10h]
0x1400c393a  call    WPP_SF_
0x1400c393f  test    rbx, rbx
0x1400c3942  jnz     short loc_1400C394E
0x1400c3944  mov     eax, 80070057h
0x1400c3949  jmp     loc_1400C4297
0x1400c394e  xorps   xmm0, xmm0
0x1400c3951  movups  xmmword ptr [rsp+348h+var_278], xmm0
0x1400c3959  xorps   xmm1, xmm1
0x1400c395c  movdqu  [rsp+348h+var_268], xmm1
0x1400c3965  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400c3969  inc     r8
0x1400c396c  cmp     [rbx+r8], sil
0x1400c3970  jnz     short loc_1400C3969
0x1400c3972  mov     rdx, rbx
0x1400c3975  lea     rcx, [rsp+348h+var_278]
0x1400c397d  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1400c3982  nop
0x1400c3983  xor     edx, edx; wchar_t *
0x1400c3985  lea     rcx, stru_14019B1D0; this
0x1400c398c  call    ?GetMiscConfigDword@MpWatchDog@@YAKPEB_WK@Z; MpWatchDog::GetMiscConfigDword(wchar_t const *,ulong)
0x1400c3991  cmp     eax, 1
0x1400c3994  jnz     short loc_1400C399C
0x1400c3996  call    cs:__imp_DebugBreak
0x1400c399c  mov     [rsp+348h+var_2C0], rsi
0x1400c39a4  call    ?MpIsCoreSvcInDevMode@MpWatchDog@@YA_NXZ; MpWatchDog::MpIsCoreSvcInDevMode(void)
0x1400c39a9  test    al, al
0x1400c39ab  jz      loc_1400C3A46
0x1400c39b1  mov     rbx, [rdi+0A8h]
0x1400c39b8  mov     rdi, [rdi+0B0h]
0x1400c39bf  jmp     short loc_1400C3A3D
0x1400c39c1  lea     rax, [rsp+348h+var_278]
0x1400c39c9  cmp     qword ptr [rsp+348h+var_268+8], 0Fh
0x1400c39d2  cmova   rax, [rsp+348h+var_278]
0x1400c39db  mov     [rsp+348h+var_288], rax
0x1400c39e3  mov     rcx, [rbx+38h]
0x1400c39e7  test    rcx, rcx
0x1400c39ea  jz      loc_1400C42B6
0x1400c39f0  mov     rax, [rcx]
0x1400c39f3  lea     r8, [rsp+348h+var_288]
0x1400c39fb  lea     rdx, [rsp+348h+var_208]
0x1400c3a03  mov     rax, [rax+10h]
0x1400c3a07  call    cs:__guard_dispatch_icall_fptr
0x1400c3a0d  or      r12d, 1
0x1400c3a11  mov     [rsp+348h+var_310], r12d
0x1400c3a16  lea     rdx, [rsp+348h+var_208]
0x1400c3a1e  lea     rcx, [rsp+348h+var_278]; void *
0x1400c3a26  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator=(std::string const &)
0x1400c3a2b  nop
0x1400c3a2c  lea     rcx, [rsp+348h+var_208]
0x1400c3a34  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1400c3a39  add     rbx, 40h ; '@'
0x1400c3a3d  cmp     rbx, rdi
0x1400c3a40  jnz     loc_1400C39C1
0x1400c3a46  cmp     qword ptr [rsp+348h+var_268], 3
0x1400c3a4f  jnb     short loc_1400C3A82
0x1400c3a51  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c3a58  cmp     rcx, r13
0x1400c3a5b  jz      short loc_1400C3A78
0x1400c3a5d  test    byte ptr [rcx+1Ch], 4
0x1400c3a61  jz      short loc_1400C3A78
0x1400c3a63  mov     edx, 17h
0x1400c3a68  lea     r8, WPP_5083a01b0eaf30ea0f7f8169c36bccb6_Traceguids
0x1400c3a6f  mov     rcx, [rcx+10h]
0x1400c3a73  call    WPP_SF_
0x1400c3a78  mov     edi, 8007000Dh
0x1400c3a7d  jmp     loc_1400C3CEC
0x1400c3a82  mov     edx, 0E0h
0x1400c3a87  mov     rcx, cs:?gMpWdConfigManager@MpWatchDog@@3PEAVWdConfigManager@1@EA; MpWatchDog::WdConfigManager * MpWatchDog::gMpWdConfigManager
0x1400c3a8e  call    ?IsKillbitGatedFeatureEnabled@WdConfigManager@MpWatchDog@@QEBA_NW4FeatureControlEnum@@@Z; MpWatchDog::WdConfigManager::IsKillbitGatedFeatureEnabled(FeatureControlEnum)
0x1400c3a93  test    al, al
0x1400c3a95  jz      short loc_1400C3B11
0x1400c3a97  lea     rcx, [rsp+348h+var_278]
0x1400c3a9f  cmp     qword ptr [rsp+348h+var_268+8], 0Fh
0x1400c3aa8  cmova   rcx, [rsp+348h+var_278]; char *
0x1400c3ab1  mov     r8, [rsp+348h+var_2F8]; wchar_t *
0x1400c3ab6  mov     rdx, [rsp+348h+var_280]; wchar_t *
0x1400c3abe  call    ?ValidatePayloadSignature@CMpWdEcsRemediationManager@MpWatchDog@@SA_NPEBDPEB_W1@Z; MpWatchDog::CMpWdEcsRemediationManager::ValidatePayloadSignature(char const *,wchar_t const *,wchar_t const *)
0x1400c3ac3  test    al, al
0x1400c3ac5  jnz     short loc_1400C3AF8
0x1400c3ac7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c3ace  cmp     rcx, r13
0x1400c3ad1  jz      short loc_1400C3AEE
0x1400c3ad3  test    byte ptr [rcx+1Ch], 1
0x1400c3ad7  jz      short loc_1400C3AEE
0x1400c3ad9  mov     edx, 18h
0x1400c3ade  lea     r8, WPP_5083a01b0eaf30ea0f7f8169c36bccb6_Traceguids
0x1400c3ae5  mov     rcx, [rcx+10h]
0x1400c3ae9  call    WPP_SF_
0x1400c3aee  mov     edi, 8009030Fh
0x1400c3af3  jmp     loc_1400C3CEC
0x1400c3af8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c3aff  cmp     rcx, r13
0x1400c3b02  jz      short loc_1400C3B38
0x1400c3b04  test    byte ptr [rcx+1Ch], 4
0x1400c3b08  jz      short loc_1400C3B38
0x1400c3b0a  mov     edx, 19h
0x1400c3b0f  jmp     short loc_1400C3B28
0x1400c3b11  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c3b18  cmp     rcx, r13
0x1400c3b1b  jz      short loc_1400C3B38
0x1400c3b1d  test    byte ptr [rcx+1Ch], 2
0x1400c3b21  jz      short loc_1400C3B38
0x1400c3b23  mov     edx, 1Ah
0x1400c3b28  lea     r8, WPP_5083a01b0eaf30ea0f7f8169c36bccb6_Traceguids
0x1400c3b2f  mov     rcx, [rcx+10h]
0x1400c3b33  call    WPP_SF_
0x1400c3b38  mov     [rsp+348h+var_314], esi
0x1400c3b3c  mov     [rsp+348h+var_304], esi
0x1400c3b40  mov     [rsp+348h+var_2F0], rsi
0x1400c3b45  mov     [rsp+348h+var_250], 1
0x1400c3b51  mov     [rsp+348h+var_248], 1
0x1400c3b5d  mov     [rsp+348h+var_240], rsi
0x1400c3b65  lea     rax, ??_7?$JSON_StringParser@D@details@json@web@@6B@; const web::json::details::JSON_StringParser<char>::`vftable'
0x1400c3b6c  mov     [rsp+348h+var_258], rax
0x1400c3b74  lea     rcx, [rsp+348h+var_278]
0x1400c3b7c  cmp     qword ptr [rsp+348h+var_268+8], 0Fh
0x1400c3b85  cmova   rcx, [rsp+348h+var_278]
0x1400c3b8e  mov     [rsp+348h+var_238], rcx
0x1400c3b96  mov     [rsp+348h+var_230], rcx
0x1400c3b9e  add     rcx, qword ptr [rsp+348h+var_268]
0x1400c3ba6  mov     [rsp+348h+var_228], rcx
0x1400c3bae  mov     [rsp+348h+var_1C8], esi
0x1400c3bb5  xorps   xmm0, xmm0
0x1400c3bb8  movups  [rsp+348h+var_1C0], xmm0
0x1400c3bc0  mov     [rsp+348h+var_1B0], rsi
0x1400c3bc8  mov     [rsp+348h+var_1A8], 0Fh
0x1400c3bd4  mov     byte ptr [rsp+348h+var_1C0], sil
0x1400c3bdc  mov     [rsp+348h+var_180], esi
0x1400c3be3  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x1400c3bea  mov     [rsp+348h+var_178], rax
0x1400c3bf2  lea     rdx, [rsp+348h+var_1C8]
0x1400c3bfa  lea     rcx, [rsp+348h+var_258]
0x1400c3c02  call    ?GetNextToken@?$JSON_Parser@D@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<char>::GetNextToken(web::json::details::JSON_Parser<char>::Token &)
0x1400c3c07  cmp     [rsp+348h+var_180], esi
0x1400c3c0e  jnz     loc_1400C42BC
0x1400c3c14  mov     [rsp+348h+var_2F0], rsi
0x1400c3c19  lea     r8, [rsp+348h+var_1C8]
0x1400c3c21  lea     rdx, [rsp+348h+var_288]
0x1400c3c29  lea     rcx, [rsp+348h+var_258]
0x1400c3c31  call    ?_ParseValue@?$JSON_Parser@D@details@json@web@@AEAA?AV?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@AEAUToken@1234@@Z; web::json::details::JSON_Parser<char>::_ParseValue(web::json::details::JSON_Parser<char>::Token &)
0x1400c3c36  mov     rbx, [rax]
0x1400c3c39  mov     [rax], rsi
0x1400c3c3c  mov     [rsp+348h+var_2F0], rbx
0x1400c3c41  or      r12d, 0Ch
0x1400c3c45  mov     [rsp+348h+var_310], r12d
0x1400c3c4a  cmp     [rsp+348h+var_180], esi
0x1400c3c51  jnz     loc_1400C42F4
0x1400c3c57  cmp     [rsp+348h+var_1C8], esi
0x1400c3c5e  jnz     loc_1400C432C
0x1400c3c64  lea     rcx, [rsp+348h+var_1C0]
0x1400c3c6c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1400c3c71  and     r12d, 0FFFFFFFBh
0x1400c3c75  or      r12d, 2
0x1400c3c79  mov     rax, [rbx]
0x1400c3c7c  mov     rcx, rbx
0x1400c3c7f  mov     rax, [rax+58h]
0x1400c3c83  call    cs:__guard_dispatch_icall_fptr
0x1400c3c89  cmp     eax, 4
0x1400c3c8c  jnz     loc_1400C4244
0x1400c3c92  mov     rax, [rbx]
0x1400c3c95  mov     rcx, rbx
0x1400c3c98  mov     rax, [rax+98h]
0x1400c3c9f  call    cs:__guard_dispatch_icall_fptr
0x1400c3ca5  mov     rdi, [rax]
0x1400c3ca8  mov     rax, [rax+8]
0x1400c3cac  mov     [rsp+348h+var_2D0], rax
0x1400c3cb1  mov     [rsp+348h+var_288], rdi
0x1400c3cb9  cmp     rdi, [rsp+348h+var_2D0]
0x1400c3cbe  jnz     short loc_1400C3D00
0x1400c3cc0  mov     edi, esi
0x1400c3cc2  mov     eax, [rsp+348h+var_314]
0x1400c3cc6  cmp     [rsp+348h+var_304], eax
0x1400c3cca  setnz   dil
0x1400c3cce  test    rbx, rbx
0x1400c3cd1  jz      short loc_1400C3CEC
0x1400c3cd3  mov     rax, [rbx]
0x1400c3cd6  mov     edx, 1
0x1400c3cdb  mov     rcx, rbx
0x1400c3cde  mov     rax, [rax+0C0h]
0x1400c3ce5  call    cs:__guard_dispatch_icall_fptr
0x1400c3ceb  nop
0x1400c3cec  lea     rcx, [rsp+348h+var_278]
0x1400c3cf4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1400c3cf9  mov     eax, edi
0x1400c3cfb  jmp     loc_1400C4297
0x1400c3d00  mov     [rsp+348h+var_280], rsi
0x1400c3d08  mov     rcx, [rdi]
0x1400c3d0b  mov     rax, [rcx]
0x1400c3d0e  lea     rdx, [rsp+348h+var_280]
0x1400c3d16  mov     rax, [rax]
0x1400c3d19  call    cs:__guard_dispatch_icall_fptr
0x1400c3d1f  nop
0x1400c3d20  mov     eax, [rsp+348h+var_314]
0x1400c3d24  inc     eax
0x1400c3d26  mov     [rsp+348h+var_314], eax
0x1400c3d2a  mov     [rsp+348h+var_300], eax
0x1400c3d2e  mov     rcx, [rsp+348h+var_280]
0x1400c3d36  mov     rax, [rcx]
0x1400c3d39  lea     rdx, [rsp+348h+var_1E8]
0x1400c3d41  mov     rax, [rax+50h]
0x1400c3d45  call    cs:__guard_dispatch_icall_fptr
0x1400c3d4b  or      r12d, 10h
0x1400c3d4f  mov     [rsp+348h+var_308], r12d
0x1400c3d54  mov     [rsp+348h+var_310], r12d
0x1400c3d59  mov     [rsp+348h+var_290], esi
0x1400c3d60  lea     r8, [rsp+348h+var_1E8]
0x1400c3d68  cmp     [rsp+348h+var_1D0], 7
0x1400c3d71  cmova   r8, [rsp+348h+var_1E8]
0x1400c3d7a  mov     rdx, [rsp+348h+var_1D8]
0x1400c3d82  add     rdx, rdx
0x1400c3d85  lea     rcx, [rsp+348h+var_290]
0x1400c3d8d  call    MpHashCrc32
0x1400c3d92  mov     [rsp+348h+var_318], sil
0x1400c3d97  mov     [rsp+348h+var_30C], esi
0x1400c3d9b  xor     edx, edx; Val
0x1400c3d9d  mov     r8d, 130h; Size
0x1400c3da3  lea     rcx, [rsp+348h+var_168]; void *
0x1400c3dab  call    memset
0x1400c3db0  mov     r8d, [rsp+348h+var_290]
0x1400c3db8  lea     rdx, [rsp+348h+var_280]
0x1400c3dc0  lea     rcx, [rsp+348h+var_168]
0x1400c3dc8  call    ?from_json@RemediationPayload@MpWatchDog@@SA?AV12@AEBVvalue@json@web@@K@Z; MpWatchDog::RemediationPayload::from_json(web::json::value const &,ulong)
0x1400c3dcd  nop
0x1400c3dce  lea     rax, [rsp+348h+var_168]
0x1400c3dd6  cmp     [rsp+348h+var_150], 7
0x1400c3ddf  cmova   rax, [rsp+348h+var_168]
0x1400c3de8  mov     [rsp+348h+var_2F8], rax
0x1400c3ded  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c3df4  cmp     rcx, r13
0x1400c3df7  jz      short loc_1400C3E17
0x1400c3df9  test    byte ptr [rcx+1Ch], 2
0x1400c3dfd  jz      short loc_1400C3E17
0x1400c3dff  mov     edx, 1Ch
0x1400c3e04  mov     r9, rax
0x1400c3e07  lea     r8, WPP_5083a01b0eaf30ea0f7f8169c36bccb6_Traceguids
0x1400c3e0e  mov     rcx, [rcx+10h]
0x1400c3e12  call    WPP_SF_S
0x1400c3e17  lea     rdx, [rsp+348h+var_168]; struct MpWatchDog::RemediationPayload *
0x1400c3e1f  call    ?SecuritySanityCheck@CMpWdEcsRemediationManager@MpWatchDog@@AEAAJAEBVRemediationPayload@2@@Z; MpWatchDog::CMpWdEcsRemediationManager::SecuritySanityCheck(MpWatchDog::RemediationPayload const &)
0x1400c3e24  mov     r12d, eax
0x1400c3e27  mov     [rsp+348h+var_30C], eax
0x1400c3e2b  test    eax, eax
0x1400c3e2d  jns     short loc_1400C3E8D
0x1400c3e2f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c3e36  cmp     rcx, r13
0x1400c3e39  jz      short loc_1400C3E60
0x1400c3e3b  test    byte ptr [rcx+1Ch], 1
0x1400c3e3f  jz      short loc_1400C3E60
0x1400c3e41  mov     edx, 1Dh
0x1400c3e46  mov     [rsp+348h+var_328], eax
0x1400c3e4a  mov     r9, [rsp+348h+var_2F8]
0x1400c3e4f  lea     r8, WPP_5083a01b0eaf30ea0f7f8169c36bccb6_Traceguids
0x1400c3e56  mov     rcx, [rcx+10h]
0x1400c3e5a  call    WPP_SF_Sd
0x1400c3e5f  nop
0x1400c3e60  lea     rcx, [rsp+348h+var_58]
0x1400c3e68  call    ?_Tidy@?$vector@VRemediationAction@MpWatchDog@@V?$allocator@VRemediationAction@MpWatchDog@@@std@@@std@@AEAAXXZ; std::vector<MpWatchDog::RemediationAction>::_Tidy(void)
0x1400c3e6d  lea     rcx, [rsp+348h+var_138]
0x1400c3e75  call    ??1?$_Optional_destruct_base@VRemediationFilter@MpWatchDog@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<MpWatchDog::RemediationFilter,0>::~_Optional_destruct_base<MpWatchDog::RemediationFilter,0>(void)
0x1400c3e7a  lea     rcx, [rsp+348h+var_168]
0x1400c3e82  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400c3e87  nop
0x1400c3e88  jmp     loc_1400C4151
0x1400c3e8d  lea     rax, aRemediations; "Remediations"
0x1400c3e94  mov     [rsp+348h+var_258], rax
0x1400c3e9c  lea     rax, stru_1401976A0
0x1400c3ea3  mov     [rsp+348h+var_250], rax
0x1400c3eab  lea     rax, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows Defender\\"...
0x1400c3eb2  mov     [rsp+348h+var_248], rax
0x1400c3eba  lea     rax, aRawcontents; "RawContents"
0x1400c3ec1  mov     [rsp+348h+var_240], rax
0x1400c3ec9  lea     rax, aScenarioname; "ScenarioName"
  ... truncated ...
```
