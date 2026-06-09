# Windows::Networking::UX::Internal::MBCategory::tp_UpdateWwanProfile(WWAN_PROFILE const &,_WWAN_ACTIVATION_STATE,bool,bool)

- ea: `0x18000a460`
- end: `0x18000ad15`
- name: `?tp_UpdateWwanProfile@MBCategory@Internal@UX@Networking@Windows@@AEAAXAEBUWWAN_PROFILE@@W4_WWAN_ACTIVATION_STATE@@_N2@Z`
- size: `2229`
- prototype: ``
- caller_count: `6`
- callee_count: `28`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800075a8`
- `0x180008880`
- `0x18001803c`
- `0x18003b5f8`
- `0x180043f30`
- `0x180044040`

## callees

- `0x180002150`
- `0x18000735c`
- `0x18000a460`
- `0x18000ad20`
- `0x18000b198`
- `0x18000b270`
- `0x18000bde0`
- `0x180014978`
- `0x180014a28`
- `0x180014b54`
- `0x180014ce4`
- `0x180016060`
- `0x1800171b0`
- `0x180017b70`
- `0x180018750`
- `0x180018b34`
- `0x18001bdb8`
- `0x18001f47c`
- `0x180023018`
- `0x180023d64`
- `0x1800268c4`
- `0x18002cd20`
- `0x18002d20c`
- `0x18002d6a0`
- `0x18003a334`
- `0x1800441f8`
- `0x180044ae8`
- `0x180059010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000abd3`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000abd3`

## string_xrefs

- `0x18000a55e`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdateWwanProfile`
- `0x18000a820`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdateWwanProfile`
- `0x18000a958`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdateWwanProfile`
- `0x18000aa39`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdateWwanProfile`
- `0x18000aabe`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdateWwanProfile`
- `0x18000aade`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdateWwanProfile`
- `0x18000ab08`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdateWwanProfile`
- `0x18000aba3`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdateWwanProfile`
- `0x18000ac93`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdateWwanProfile`
- `0x18000a94c`: `No profile update. profileName=%ls`
- `0x18000a7f4`: `[InternetProfile] Profile updated. profileName=%ls, description=%ls, iccid=%ls, apn=%ls, username=%ls, hasPassword=%hs, isAdminEnabled=%hs, authProtocol=%d, ipType=%d, activationState=%d, isPurchase=%hs, creationType=%d`
- `0x18000aa9d`: `[DmConfigProfile] Profile removed. profileName=%ls`
- `0x18000aa2d`: `Profile skipped due to IMSI mismatch. profileName=%ls, simIccId=%ls, imsi=%ls, expected imsi=%ls`
- `0x18000aa96`: `[InternetProfile] Profile removed. profileName=%ls`
- `0x18000aad2`: `ICCID is not ready. Skip all profile information. profileName=%ls`
- `0x18000aafc`: `IMSI is not ready. Skip the profile that is conditioned on IMSI. profileName=%ls, simIccId=%ls, expected imsi=%ls`
- `0x18000ac87`: `Profile to remove not found in the profileMap. profileName=%ls`
- `0x18000ac53`: `[DmConfigProfile] Profile updated. profileName=%ls, description=%ls, iccid=%ls, apn=%ls, username=%ls, hasPassword=%hs, isAdminEnabled=%hs, authProtocol=%d, ipType=%d, activationState=%d, isPurchase=%hs, creationType=%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall Windows::Networking::UX::Internal::MBCategory::tp_UpdateWwanProfile(
        _QWORD *a1,
        const wchar_t *a2,
        int a3,
        unsigned __int8 a4,
        char a5)
{
  const wchar_t *v6; // rdi
  const wchar_t *v8; // r9
  unsigned __int64 v9; // r11
  const wchar_t *v10; // r8
  const wchar_t *v11; // r14
  unsigned __int16 *v12; // rax
  signed __int64 v13; // r8
  int v14; // ecx
  int v15; // edx
  __int64 v16; // r12
  __int64 v17; // rax
  int v18; // edx
  unsigned int v19; // esi
  _QWORD *v20; // r15
  Windows::Networking::UX::Internal::MbConnectionProfileServer *v21; // rax
  __int64 v22; // rdi
  int v23; // ebx
  wchar_t **v24; // rax
  _QWORD *v25; // rsi
  __int64 *v26; // r12
  __int64 v27; // rdi
  __int64 *v28; // rbx
  __int64 inserted; // rdi
  __int64 v30; // rbx
  __int64 v31; // rsi
  __int64 *v32; // rdi
  int v33; // r10d
  int v34; // esi
  int v35; // ecx
  int v36; // eax
  const char *v37; // r8
  const char *v38; // r9
  const char *v39; // r10
  const WCHAR *v40; // rdx
  const wchar_t *v41; // rcx
  size_t v42; // r13
  const wchar_t *v43; // rdx
  size_t v44; // rsi
  size_t v45; // r8
  int v46; // eax
  _QWORD *v47; // rcx
  wchar_t **v48; // r8
  __int64 v49; // rax
  const wchar_t *v50; // rcx
  unsigned __int64 v51; // r11
  __int64 v52; // r8
  unsigned __int16 *v53; // rdx
  __int64 v54; // r8
  int v55; // r10d
  int v56; // r9d
  _QWORD *v57; // rax
  __int64 v58; // rdx
  const char *v59; // r8
  const char *v60; // r10
  const WCHAR *v61; // rdx
  const wchar_t *v62; // r9
  int v63; // [rsp+20h] [rbp-E0h]
  char v65[7]; // [rsp+81h] [rbp-7Fh] BYREF
  _QWORD *v66; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v67; // [rsp+90h] [rbp-70h] BYREF
  const wchar_t *v68; // [rsp+98h] [rbp-68h]
  int v69; // [rsp+A0h] [rbp-60h]
  __int128 v70; // [rsp+A8h] [rbp-58h] BYREF
  _OWORD v71[2]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t *S2[2]; // [rsp+E0h] [rbp-20h] BYREF
  size_t N; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v74; // [rsp+F8h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v69 = a3;
  v6 = a2;
  v68 = a2;
  v67 = a1;
  if ( !a1[48] )
  {
    MBSettingUXLogging::Warn(
      "Windows::Networking::UX::Internal::MBCategory::tp_UpdateWwanProfile",
      0xFC5u,
      "ICCID is not ready. Skip all profile information. profileName=%ls",
      a2);
    return;
  }
  v8 = (const wchar_t *)(a1 + 46);
  v9 = a1[49];
  if ( v9 <= 7 )
    v10 = (const wchar_t *)(a1 + 46);
  else
    v10 = *(const wchar_t **)v8;
  v11 = a2 + 1556;
  v12 = (unsigned __int16 *)(a2 + 1556);
  v13 = (char *)v10 - (char *)(a2 + 1556);
  do
  {
    v14 = *(unsigned __int16 *)((char *)v12 + v13);
    v15 = *v12 - v14;
    if ( v15 )
      break;
    ++v12;
  }
  while ( v14 );
  v16 = -1;
  if ( v15 )
  {
    v17 = -1;
    do
    {
      v18 = v11[v17 + 1] - aIccidany[v17 + 1];
      if ( v18 )
        break;
      v17 += 2;
      if ( v17 == 9 )
        break;
      v18 = v11[v17] - aIccidany[v17];
    }
    while ( !v18 );
    if ( v18 )
    {
      if ( v9 > 7 )
        v8 = *(const wchar_t **)v8;
      MBSettingUXLogging::Info(
        "Windows::Networking::UX::Internal::MBCategory::tp_UpdateWwanProfile",
        0xFCFu,
        "Profile skipped due to ICCID mismatch. profileName=%ls, simIccId=%ls, expected simIccId=%ls",
        v6,
        v8,
        v11);
      return;
    }
  }
  if ( !v6[2324] )
    goto LABEL_18;
  if ( !a1[52] )
  {
    MBSettingUXLogging::Warn(
      "Windows::Networking::UX::Internal::MBCategory::tp_UpdateWwanProfile",
      0xFDBu,
      "IMSI is not ready. Skip the profile that is conditioned on IMSI. profileName=%ls, simIccId=%ls, expected imsi=%ls",
      v6,
      v11,
      v6 + 2324);
    return;
  }
  v50 = (const wchar_t *)(a1 + 50);
  v51 = a1[53];
  v52 = v51 <= 7 ? (__int64)(a1 + 50) : *(_QWORD *)v50;
  v53 = (unsigned __int16 *)(v6 + 2324);
  v54 = v52 - (_QWORD)(v6 + 2324);
  do
  {
    v55 = *(unsigned __int16 *)((char *)v53 + v54);
    v56 = *v53 - v55;
    if ( v56 )
      break;
    ++v53;
  }
  while ( v55 );
  if ( !v56 )
  {
LABEL_18:
    switch ( a3 )
    {
      case 3:
        v19 = 3;
        break;
      case 1:
        v19 = 1;
        break;
      case 2:
        v19 = 2;
        break;
      case 4:
        v19 = 4;
        break;
      default:
        v19 = 0;
        break;
    }
    v20 = 0;
    v66 = 0;
    v21 = (Windows::Networking::UX::Internal::MbConnectionProfileServer *)operator new(
                                                                            0x100u,
                                                                            (const struct std::nothrow_t *)&std::nothrow);
    if ( v21 )
    {
      v22 = Windows::Networking::UX::Internal::MbConnectionProfileServer::MbConnectionProfileServer(v21);
      *(_QWORD *)&v70 = v22;
      *(_QWORD *)&v71[0] = 0;
      LOBYTE(v63) = a5;
      v23 = Windows::Networking::UX::Internal::MbConnectionProfileServer::RuntimeClassInitialize(v22, v68, a4, v19);
      if ( v23 >= 0 )
      {
        v23 = Microsoft::WRL::Details::RuntimeClassBaseT<1>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IMbConnectionProfile>>(
                v22,
                &GUID_b1b90ba5_86e9_5ff6_94da_e301912a6510,
                &v66);
        Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::MbConnectionProfileServer>::InternalRelease(&v70);
        v20 = v66;
      }
      else if ( v22 )
      {
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IMbConnectionProfile>::Release(v22);
      }
      v6 = v68;
    }
    else
    {
      v23 = -2147024882;
    }
    if ( v23 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1006,
        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
        (const char *)(unsigned int)v23,
        v63);
LABEL_57:
      if ( v20 )
        (*(void (__fastcall **)(_QWORD *))(*v20 + 16LL))(v20);
      return;
    }
    if ( !v20 )
    {
      MBSettingUXLogging::Info(
        "Windows::Networking::UX::Internal::MBCategory::tp_UpdateWwanProfile",
        0x100Du,
        "spConnectionProfile is nullptr.");
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v66);
      return;
    }
    *(_OWORD *)S2 = 0;
    N = 0;
    v74 = 0;
    do
      ++v16;
    while ( v6[v16] );
    std::wstring::_Construct<1,unsigned short const *>(S2, v6, v16);
    v24 = S2;
    if ( v74 > 7 )
      v24 = (wchar_t **)S2[0];
    if ( !*(_WORD *)v24 )
      goto LABEL_83;
    v25 = v67;
    v26 = &v67[2 * a4 + 116];
    v27 = *v26;
    v28 = *(__int64 **)(*v26 + 8);
    for ( HIDWORD(v71[0]) = 0; !*((_BYTE *)v28 + 25); v28 = (__int64 *)*v28 )
    {
      v47 = v28 + 4;
      v48 = S2;
      if ( v74 > 7 )
        v48 = (wchar_t **)S2[0];
      if ( (unsigned __int64)v28[7] > 7 )
        v47 = (_QWORD *)*v47;
      if ( (int)std::_Traits_compare<std::char_traits<unsigned short>>(v47, v28[6], v48, N) >= 0 )
        v27 = (__int64)v28;
      else
        v28 += 2;
    }
    if ( !*(_BYTE *)(v27 + 25) && (int)std::wstring::compare(S2, v27 + 32) >= 0 )
    {
      v65[0] = 1;
      v49 = std::map<std::wstring,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>::_Try_emplace<std::wstring const &,>(
              v26,
              v71,
              S2);
      (*(void (__fastcall **)(_QWORD, _QWORD *, char *))(**(_QWORD **)(*(_QWORD *)v49 + 64LL) + 280LL))(
        *(_QWORD *)(*(_QWORD *)v49 + 64LL),
        v20,
        v65);
      if ( v65[0] )
      {
        v6 = v68;
LABEL_83:
        MBSettingUXLogging::Info(
          "Windows::Networking::UX::Internal::MBCategory::tp_UpdateWwanProfile",
          0x107Du,
          "No profile update. profileName=%ls",
          v6);
LABEL_54:
        if ( v74 > 7 )
          std::_Deallocate<16>(S2[0], 2 * v74 + 2);
        N = 0;
        v74 = 7;
        LOWORD(S2[0]) = 0;
        goto LABEL_57;
      }
    }
    if ( a5 )
    {
      if ( std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>>,0>>::count(
             v26,
             S2) )
      {
        v57 = (_QWORD *)std::map<std::wstring,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>::_Try_emplace<std::wstring const &,>(
                          v26,
                          v71,
                          S2);
        Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>::operator=(&v66, *v57 + 64LL);
        v20 = v66;
        if ( v66 )
        {
          LOBYTE(v58) = 1;
          (*(void (__fastcall **)(_QWORD *, __int64))(*v66 + 272LL))(v66, v58);
          v71[0] = *(_OWORD *)std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Eqrange<std::wstring>(
                                v26,
                                &v70,
                                S2);
          std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>>,0>>::_Erase(
            v26,
            v71);
        }
      }
      else
      {
        v62 = (const wchar_t *)S2;
        if ( v74 > 7 )
          v62 = S2[0];
        MBSettingUXLogging::Warn(
          "Windows::Networking::UX::Internal::MBCategory::tp_UpdateWwanProfile",
          0x103Du,
          "Profile to remove not found in the profileMap. profileName=%ls",
          v62);
      }
      v59 = "[DmConfigProfile] Profile removed. profileName=%ls";
      if ( !a4 )
        v59 = "[InternetProfile] Profile removed. profileName=%ls";
      MBSettingUXLogging::Info(
        "Windows::Networking::UX::Internal::MBCategory::tp_UpdateWwanProfile",
        4 * (a4 ^ 1) + 4165,
        v59,
        v68);
      goto LABEL_52;
    }
    inserted = *v26;
    v30 = *(_QWORD *)(*v26 + 8);
    v70 = (unsigned __int64)v30;
    if ( *(_BYTE *)(v30 + 25) )
    {
LABEL_36:
      if ( *(_BYTE *)(inserted + 25) || (int)std::wstring::compare(S2, inserted + 32) < 0 )
      {
        if ( v26[1] == 0x38E38E38E38E38ELL )
          std::_Xlength_error("map/set too long");
        v31 = *v26;
        v71[0] = (unsigned __int64)v26;
        v32 = (__int64 *)operator new(0x48u);
        *((_QWORD *)&v71[0] + 1) = v32;
        std::wstring::wstring(v32 + 4, S2);
        v32[8] = 0;
        *v32 = v31;
        v32[1] = v31;
        v32[2] = v31;
        *((_WORD *)v32 + 12) = 0;
        v71[0] = v70;
        inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>>>::_Insert_node(
                     v26,
                     v71,
                     v32);
      }
      if ( *(_QWORD **)(inserted + 64) != v20 )
      {
        v66 = v20;
        Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(&v66);
        v66 = *(_QWORD **)(inserted + 64);
        *(_QWORD *)(inserted + 64) = v20;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v66);
      }
      v33 = *((_DWORD *)v68 + 1120);
      v34 = *((_DWORD *)v68 + 1174);
      v35 = *((_DWORD *)v68 + 800) & 4;
      v36 = *((_DWORD *)v68 + 800) & 2;
      v37 = "true";
      v38 = "true";
      if ( a4 )
      {
        if ( !v33 )
          v38 = "false";
        v60 = "true";
        if ( !v34 )
          v60 = "false";
        if ( !v35 )
          v37 = "false";
        v61 = v68 + 1705;
        if ( !v36 )
          v61 = &sourceString;
        MBSettingUXLogging::Info(
          "Windows::Networking::UX::Internal::MBCategory::tp_UpdateWwanProfile",
          0x105Fu,
          "[DmConfigProfile] Profile updated. profileName=%ls, description=%ls, iccid=%ls, apn=%ls, username=%ls, hasPass"
          "word=%hs, isAdminEnabled=%hs, authProtocol=%d, ipType=%d, activationState=%d, isPurchase=%hs, creationType=%d",
          v68,
          v68 + 256,
          v11,
          v68 + 1604,
          v61,
          v37,
          v60,
          *((_DWORD *)v68 + 1111),
          *((_DWORD *)v68 + 1116),
          v69,
          v38,
          *((_DWORD *)v68 + 769));
      }
      else
      {
        if ( !v33 )
          v38 = "false";
        v39 = "true";
        if ( !v34 )
          v39 = "false";
        if ( !v35 )
          v37 = "false";
        v40 = v68 + 1705;
        if ( !v36 )
          v40 = &sourceString;
        MBSettingUXLogging::Info(
          "Windows::Networking::UX::Internal::MBCategory::tp_UpdateWwanProfile",
          0x1072u,
          "[InternetProfile] Profile updated. profileName=%ls, description=%ls, iccid=%ls, apn=%ls, username=%ls, hasPass"
          "word=%hs, isAdminEnabled=%hs, authProtocol=%d, ipType=%d, activationState=%d, isPurchase=%hs, creationType=%d",
          v68,
          v68 + 256,
          v11,
          v68 + 1604,
          v40,
          v37,
          v39,
          *((_DWORD *)v68 + 1111),
          *((_DWORD *)v68 + 1116),
          v69,
          v38,
          *((_DWORD *)v68 + 769));
      }
      v25 = v67;
LABEL_52:
      if ( v20 )
      {
        v67 = v20;
        Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(&v67);
        Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke(v25, &v67);
      }
      goto LABEL_54;
    }
    while ( 1 )
    {
      *(_QWORD *)&v70 = v30;
      v41 = (const wchar_t *)(v30 + 32);
      v42 = N;
      v43 = (const wchar_t *)S2;
      if ( v74 > 7 )
        v43 = S2[0];
      v44 = *(_QWORD *)(v30 + 48);
      if ( *(_QWORD *)(v30 + 56) > 7u )
        v41 = *(const wchar_t **)v41;
      v45 = *(_QWORD *)(v30 + 48);
      if ( N < v44 )
        v45 = N;
      v46 = wmemcmp(v41, v43, v45);
      if ( v46 )
      {
        if ( v46 >= 0 )
          goto LABEL_73;
      }
      else if ( v44 >= v42 )
      {
LABEL_73:
        DWORD2(v70) = 1;
        inserted = v30;
        goto LABEL_71;
      }
      DWORD2(v70) = 0;
      v30 += 16;
LABEL_71:
      v30 = *(_QWORD *)v30;
      if ( *(_BYTE *)(v30 + 25) )
        goto LABEL_36;
    }
  }
  if ( v51 > 7 )
    v50 = *(const wchar_t **)v50;
  MBSettingUXLogging::Warn(
    "Windows::Networking::UX::Internal::MBCategory::tp_UpdateWwanProfile",
    0xFE6u,
    "Profile skipped due to IMSI mismatch. profileName=%ls, simIccId=%ls, imsi=%ls, expected imsi=%ls",
    v6,
    v11,
    v50,
    v6 + 2324);
}

```

## disassembly

```asm
0x18000a460  mov     [rsp-8+arg_18], rbx
0x18000a465  push    rbp
0x18000a466  push    rsi
0x18000a467  push    rdi
0x18000a468  push    r12
0x18000a46a  push    r13
0x18000a46c  push    r14
0x18000a46e  push    r15
0x18000a470  lea     rbp, [rsp-10h]
0x18000a475  sub     rsp, 110h
0x18000a47c  mov     rax, cs:__security_cookie
0x18000a483  xor     rax, rsp
0x18000a486  mov     [rbp+40h+var_40], rax
0x18000a48a  mov     [rbp+40h+var_C0], r9b
0x18000a48e  mov     ebx, r8d
0x18000a491  mov     [rbp+40h+var_A0], ebx
0x18000a494  mov     rdi, rdx
0x18000a497  mov     [rbp+40h+var_A8], rdx
0x18000a49b  mov     r10, rcx
0x18000a49e  mov     [rbp+40h+var_B0], rcx
0x18000a4a2  cmp     qword ptr [rcx+180h], 0
0x18000a4aa  jz      loc_18000AACF
0x18000a4b0  lea     r9, [rcx+170h]
0x18000a4b7  mov     r11, [r9+18h]
0x18000a4bb  cmp     r11, 7
0x18000a4bf  jbe     loc_18000A591
0x18000a4c5  mov     r8, [r9]
0x18000a4c8  lea     r14, [rdx+0C28h]
0x18000a4cf  mov     rax, r14
0x18000a4d2  sub     r8, r14
0x18000a4d5  nop     word ptr [rax+rax+00000000h]
0x18000a4e0  movzx   edx, word ptr [rax]
0x18000a4e3  movzx   ecx, word ptr [rax+r8]
0x18000a4e8  sub     edx, ecx
0x18000a4ea  jnz     short loc_18000A4F4
0x18000a4ec  add     rax, 2
0x18000a4f0  test    ecx, ecx
0x18000a4f2  jnz     short loc_18000A4E0
0x18000a4f4  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18000a4fb  test    edx, edx
0x18000a4fd  jz      loc_18000A599
0x18000a503  lea     r8, aIccidany; "IccidAny"
0x18000a50a  mov     rax, r12
0x18000a50d  nop     dword ptr [rax]
0x18000a510  movzx   edx, word ptr [r14+rax*2+2]
0x18000a516  movzx   ecx, word ptr [r8+rax*2+2]
0x18000a51c  sub     edx, ecx
0x18000a51e  jnz     short loc_18000A538
0x18000a520  add     rax, 2
0x18000a524  cmp     rax, 9
0x18000a528  jz      short loc_18000A538
0x18000a52a  movzx   edx, word ptr [r14+rax*2]
0x18000a52f  movzx   ecx, word ptr [r8+rax*2]
0x18000a534  sub     edx, ecx
0x18000a536  jz      short loc_18000A510
0x18000a538  test    edx, edx
0x18000a53a  jz      short loc_18000A599
0x18000a53c  cmp     r11, 7
0x18000a540  jbe     short loc_18000A545
0x18000a542  mov     r9, [r9]
0x18000a545  mov     [rsp+140h+var_118], r14
0x18000a54a  mov     qword ptr [rsp+140h+var_120], r9
0x18000a54f  mov     r9, rdi
0x18000a552  lea     r8, aProfileSkipped_0; "Profile skipped due to ICCID mismatch. "...
0x18000a559  mov     edx, 0FCFh; unsigned int
0x18000a55e  lea     rcx, aWindowsNetwork_125; "Windows::Networking::UX::Internal::MBCa"...
0x18000a565  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18000a56a  mov     rcx, [rbp+40h+var_40]
0x18000a56e  xor     rcx, rsp; StackCookie
0x18000a571  call    __security_check_cookie
0x18000a576  mov     rbx, [rsp+140h+arg_18]
0x18000a57e  add     rsp, 110h
0x18000a585  pop     r15
0x18000a587  pop     r14
0x18000a589  pop     r13
0x18000a58b  pop     r12
0x18000a58d  pop     rdi
0x18000a58e  pop     rsi
0x18000a58f  pop     rbp
0x18000a590  retn
0x18000a591  mov     r8, r9
0x18000a594  jmp     loc_18000A4C8
0x18000a599  lea     rax, [rdi+1228h]
0x18000a5a0  cmp     word ptr [rax], 0
0x18000a5a4  jnz     loc_18000A9CA
0x18000a5aa  cmp     ebx, 3
0x18000a5ad  jnz     loc_18000A877
0x18000a5b3  mov     esi, ebx
0x18000a5b5  xor     r15d, r15d
0x18000a5b8  mov     [rbp+40h+var_B8], r15
0x18000a5bc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a5c3  mov     ecx, 100h; unsigned __int64
0x18000a5c8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a5cd  movzx   r13d, [rbp+40h+arg_20]
0x18000a5d2  test    rax, rax
0x18000a5d5  jz      loc_18000AB3E
0x18000a5db  movzx   ebx, [rbp+40h+var_C0]
0x18000a5df  mov     rcx, rax; this
0x18000a5e2  call    ??0MbConnectionProfileServer@Internal@UX@Networking@Windows@@QEAA@XZ; Windows::Networking::UX::Internal::MbConnectionProfileServer::MbConnectionProfileServer(void)
0x18000a5e7  mov     rdi, rax
0x18000a5ea  mov     qword ptr [rbp+40h+var_98], rax
0x18000a5ee  mov     qword ptr [rbp+40h+var_80], r15
0x18000a5f2  mov     byte ptr [rsp+140h+var_120], r13b; int
0x18000a5f7  mov     r9d, esi
0x18000a5fa  mov     r8d, ebx
0x18000a5fd  mov     rdx, [rbp+40h+var_A8]
0x18000a601  mov     rcx, rax
0x18000a604  call    ?RuntimeClassInitialize@MbConnectionProfileServer@Internal@UX@Networking@Windows@@QEAAJPEBUWWAN_PROFILE@@W4MbConnectionProfileType@345@W4MbActivationState@345@_N@Z; Windows::Networking::UX::Internal::MbConnectionProfileServer::RuntimeClassInitialize(WWAN_PROFILE const *,Windows::Networking::UX::MbConnectionProfileType,Windows::Networking::UX::MbActivationState,bool)
0x18000a609  mov     ebx, eax
0x18000a60b  test    eax, eax
0x18000a60d  jns     loc_18000AB55
0x18000a613  test    rdi, rdi
0x18000a616  jnz     loc_18000AB48
0x18000a61c  mov     rdi, [rbp+40h+var_A8]
0x18000a620  mov     rcx, [rbp+48h]; this
0x18000a624  test    ebx, ebx
0x18000a626  js      loc_18000AB7D
0x18000a62c  test    r15, r15
0x18000a62f  jz      loc_18000AB97
0x18000a635  xorps   xmm0, xmm0
0x18000a638  movups  xmmword ptr [rbp+40h+S2], xmm0
0x18000a63c  xor     eax, eax
0x18000a63e  mov     [rbp+40h+N], rax
0x18000a642  mov     [rbp+40h+var_48], rax
0x18000a646  inc     r12
0x18000a649  cmp     [rdi+r12*2], ax
0x18000a64e  jnz     short loc_18000A646
0x18000a650  mov     r8, r12
0x18000a653  mov     rdx, rdi
0x18000a656  lea     rcx, [rbp+40h+S2]
0x18000a65a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000a65f  nop
0x18000a660  lea     rax, [rbp+40h+S2]
0x18000a664  cmp     [rbp+40h+var_48], 7
0x18000a669  cmova   rax, [rbp+40h+S2]
0x18000a66e  cmp     word ptr [rax], 0
0x18000a672  jz      loc_18000A949
0x18000a678  movzx   r12d, [rbp+40h+var_C0]
0x18000a67d  add     r12, 3Ah ; ':'
0x18000a681  shl     r12, 4
0x18000a685  mov     rsi, [rbp+40h+var_B0]
0x18000a689  add     r12, rsi
0x18000a68c  mov     rdi, [r12]
0x18000a690  mov     rbx, [rdi+8]
0x18000a694  xor     eax, eax
0x18000a696  mov     dword ptr [rbp+40h+var_80+0Ch], eax
0x18000a699  cmp     [rbx+19h], al
0x18000a69c  jz      loc_18000A900
0x18000a6a2  cmp     byte ptr [rdi+19h], 0
0x18000a6a6  jz      loc_18000A975
0x18000a6ac  test    r13b, r13b
0x18000a6af  jnz     loc_18000AC64
0x18000a6b5  mov     rdi, [r12]
0x18000a6b9  mov     rbx, [rdi+8]
0x18000a6bd  mov     qword ptr [rbp+40h+var_98], rbx
0x18000a6c1  xor     r13d, r13d
0x18000a6c4  mov     qword ptr [rbp+40h+var_98+8], r13
0x18000a6c8  cmp     [rbx+19h], r13b
0x18000a6cc  jz      loc_18000A890
0x18000a6d2  cmp     byte ptr [rdi+19h], 0
0x18000a6d6  jz      loc_18000AA4F
0x18000a6dc  mov     rax, 38E38E38E38E38Eh
0x18000a6e6  cmp     [r12+8], rax
0x18000a6eb  jz      loc_18000ABCC
0x18000a6f1  mov     rsi, [r12]
0x18000a6f5  mov     qword ptr [rbp+40h+var_80], r12
0x18000a6f9  mov     [rbp-38h], r13
0x18000a6fd  mov     ecx, 48h ; 'H'; Size
0x18000a702  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a707  mov     rdi, rax
0x18000a70a  mov     [rbp-38h], rax
0x18000a70e  lea     rdx, [rbp+40h+S2]
0x18000a712  lea     rcx, [rax+20h]
0x18000a716  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000a71b  mov     [rdi+40h], r13
0x18000a71f  mov     [rdi], rsi
0x18000a722  mov     [rdi+8], rsi
0x18000a726  mov     [rdi+10h], rsi
0x18000a72a  mov     word ptr [rdi+18h], 0
0x18000a730  movups  xmm0, [rbp+40h+var_98]
0x18000a734  movaps  [rbp+40h+var_80], xmm0
0x18000a738  mov     r8, rdi
0x18000a73b  lea     rdx, [rbp+40h+var_80]
0x18000a73f  mov     rcx, r12
0x18000a742  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>,void *> *>,std::_Tree_node<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>,void *> * const)
0x18000a747  mov     rdi, rax
0x18000a74a  cmp     [rdi+40h], r15
0x18000a74e  jnz     loc_18000ABDA
0x18000a754  mov     r13, [rbp+40h+var_A8]
0x18000a758  mov     r11d, [r13+0C04h]
0x18000a75f  mov     r10d, [r13+1180h]
0x18000a766  mov     ebx, [r13+1170h]
0x18000a76d  mov     edi, [r13+115Ch]
0x18000a774  mov     esi, [r13+1258h]
0x18000a77b  mov     eax, [r13+0C80h]
0x18000a782  mov     ecx, eax
0x18000a784  and     ecx, 4
0x18000a787  and     eax, 2
0x18000a78a  lea     rdx, aFalse; "false"
0x18000a791  lea     r8, aTrue; "true"
0x18000a798  mov     r9, r8
0x18000a79b  cmp     [rbp+40h+var_C0], 0
0x18000a79f  jnz     loc_18000AC01
0x18000a7a5  test    r10d, r10d
0x18000a7a8  cmovz   r9, rdx
0x18000a7ac  mov     r10, r8
0x18000a7af  test    esi, esi
0x18000a7b1  cmovz   r10, rdx
0x18000a7b5  test    ecx, ecx
0x18000a7b7  cmovz   r8, rdx
0x18000a7bb  test    eax, eax
0x18000a7bd  lea     rdx, [r13+0D52h]
0x18000a7c4  jz      loc_18000A969
0x18000a7ca  mov     [rsp+140h+var_D0], r11d
0x18000a7cf  mov     [rsp+140h+var_D8], r9
0x18000a7d4  mov     r9d, [rbp+40h+var_A0]
0x18000a7d8  mov     [rsp+140h+var_E0], r9d
0x18000a7dd  mov     [rsp+140h+var_E8], ebx
0x18000a7e1  mov     [rsp+140h+var_F0], edi
0x18000a7e5  mov     [rsp+140h+var_F8], r10
0x18000a7ea  mov     [rsp+140h+var_100], r8
0x18000a7ef  mov     [rsp+140h+var_108], rdx
0x18000a7f4  lea     r8, aInternetprofil; "[InternetProfile] Profile updated. prof"...
0x18000a7fb  mov     edx, 1072h; unsigned int
0x18000a800  lea     rax, [r13+0C88h]
0x18000a807  mov     [rsp+140h+var_110], rax
0x18000a80c  mov     [rsp+140h+var_118], r14
0x18000a811  lea     rcx, [r13+200h]
0x18000a818  mov     r9, r13
0x18000a81b  mov     qword ptr [rsp+140h+var_120], rcx
0x18000a820  lea     rcx, aWindowsNetwork_125; "Windows::Networking::UX::Internal::MBCa"...
0x18000a827  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18000a82c  mov     rsi, [rbp+40h+var_B0]
0x18000a830  test    r15, r15
0x18000a833  jnz     loc_18000ACE0
0x18000a839  mov     rdx, [rbp+40h+var_48]
0x18000a83d  cmp     rdx, 7
0x18000a841  ja      loc_18000ACFE
0x18000a847  mov     [rbp+40h+N], 0
0x18000a84f  mov     [rbp+40h+var_48], 7
0x18000a857  xor     eax, eax
0x18000a859  mov     word ptr [rbp+40h+S2], ax
0x18000a85d  test    r15, r15
0x18000a860  jz      short loc_18000A872
0x18000a862  mov     rax, [r15]
0x18000a865  mov     rcx, r15
0x18000a868  mov     rax, [rax+10h]
0x18000a86c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a871  nop
0x18000a872  jmp     loc_18000A56A
0x18000a877  mov     ecx, ebx
0x18000a879  sub     ecx, 1
0x18000a87c  jnz     loc_18000AB19
0x18000a882  mov     esi, 1
0x18000a887  jmp     loc_18000A5B5
0x18000a890  mov     qword ptr [rbp+40h+var_98], rbx
0x18000a894  lea     rcx, [rbx+20h]
0x18000a898  mov     r13, [rbp+40h+N]
0x18000a89c  lea     rdx, [rbp+40h+S2]
0x18000a8a0  cmp     [rbp+40h+var_48], 7
0x18000a8a5  cmova   rdx, [rbp+40h+S2]; S2
0x18000a8aa  mov     rsi, [rbx+30h]
0x18000a8ae  cmp     qword ptr [rcx+18h], 7
0x18000a8b3  jbe     short loc_18000A8B8
0x18000a8b5  mov     rcx, [rcx]; S1
0x18000a8b8  mov     r8, rsi
0x18000a8bb  cmp     r13, rsi
0x18000a8be  cmovb   r8, r13; N
0x18000a8c2  call    wmemcmp
0x18000a8c7  test    eax, eax
0x18000a8c9  jz      loc_18000ABBE
0x18000a8cf  jns     short loc_18000A8EB
0x18000a8d1  xor     r13d, r13d
0x18000a8d4  mov     dword ptr [rbp+40h+var_98+8], r13d
0x18000a8d8  add     rbx, 10h
0x18000a8dc  mov     rbx, [rbx]
0x18000a8df  cmp     byte ptr [rbx+19h], 0
0x18000a8e3  jnz     loc_18000A6D2
0x18000a8e9  jmp     short loc_18000A890
0x18000a8eb  mov     dword ptr [rbp+40h+var_98+8], 1
0x18000a8f2  mov     rdi, rbx
0x18000a8f5  xor     r13d, r13d
0x18000a8f8  jmp     short loc_18000A8DC
0x18000a900  lea     rcx, [rbx+20h]
0x18000a904  lea     r8, [rbp+40h+S2]
0x18000a908  cmp     [rbp+40h+var_48], 7
0x18000a90d  cmova   r8, [rbp+40h+S2]
0x18000a912  cmp     qword ptr [rcx+18h], 7
0x18000a917  jbe     short loc_18000A91C
0x18000a919  mov     rcx, [rcx]
0x18000a91c  mov     r9, [rbp+40h+N]
0x18000a920  mov     rdx, [rbx+30h]
0x18000a924  call    ??$_Traits_compare@U?$char_traits@G@std@@@std@@YAHQEBG_K01@Z; std::_Traits_compare<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18000a929  test    eax, eax
0x18000a92b  jns     short loc_18000A940
0x18000a92d  add     rbx, 10h
0x18000a931  mov     rbx, [rbx]
0x18000a934  cmp     byte ptr [rbx+19h], 0
0x18000a938  jnz     loc_18000A6A2
0x18000a93e  jmp     short loc_18000A900
  ... truncated ...
```
