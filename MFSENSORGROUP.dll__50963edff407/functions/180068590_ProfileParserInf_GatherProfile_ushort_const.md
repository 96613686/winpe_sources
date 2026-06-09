# ProfileParserInf::GatherProfile(ushort const *)

- ea: `0x180068590`
- end: `0x180068a03`
- name: `?GatherProfile@ProfileParserInf@@UEAAJPEBG@Z`
- size: `1139`
- prototype: `int(ProfileParserInf *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180005fa0`
- `0x18002d02c`
- `0x18002f81c`
- `0x180041074`
- `0x180044adc`
- `0x180044f30`
- `0x180045900`
- `0x180067fb4`
- `0x180068590`
- `0x18006978c`
- `0x18006aefc`
- `0x18006b11c`
- `0x18006d7f4`
- `0x180077010`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x18006864f`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x18006864f`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18006868c`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18006868c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006862b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006862b`
- `MFPlat!MFTraceError` at `0x180068942`
- `MFPlat!MFTraceError` at `0x180068942`

## string_xrefs

- `0x1800686b0`: `failed to open device interface (%S) key!`

## pseudocode

```c
__int64 __fastcall ProfileParserInf::GatherProfile(ProfileParserInf *this, const unsigned __int16 *a2)
{
  __int64 v4; // rax
  HKEY *v5; // r12
  HKEY v6; // rcx
  CONFIGRET v7; // esi
  signed int v8; // eax
  unsigned int v9; // esi
  __int64 v10; // rax
  int ProfileIdFromString; // eax
  int v12; // esi
  ProfileEntryInf *v13; // rbx
  __int64 v14; // rdx
  int Value; // esi
  int v16; // r9d
  __int64 v17; // rax
  __int64 v18; // rax
  const unsigned __int16 *v19; // rbp
  unsigned int v20; // r13d
  const unsigned __int16 *v21; // r14
  unsigned __int16 v22; // r15
  ProfileEntryInf *v23; // rax
  ProfileEntryInf *v24; // rax
  unsigned int v26; // [rsp+30h] [rbp-278h] BYREF
  GUID pclsid; // [rsp+38h] [rbp-270h] BYREF
  unsigned __int16 v28[264]; // [rsp+50h] [rbp-258h] BYREF

  if ( (unsigned __int8)byte_18008D62F >= 0x10u )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 37), 116, &WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids, a2);
  v4 = (*(__int64 (__fastcall **)(ProfileParserInf *))(*(_QWORD *)this + 96LL))(this);
  MFTraceValidation(v4, 0, 0, "checking OEM INF defined profiles for %S", a2);
  v5 = (HKEY *)((char *)this + 88);
  v6 = (HKEY)*((_QWORD *)this + 11);
  if ( (unsigned __int64)v6 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(v6);
    *v5 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  }
  v7 = CM_Open_Device_Interface_KeyW(a2, 0x20019u, 1u, (PHKEY)this + 11, 0);
  if ( v7 )
  {
    if ( byte_18008D62F )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 37), 117, &WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids, a2);
    v8 = CM_MapCrToWin32Err(v7, 0xDu);
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    v10 = (*(__int64 (__fastcall **)(ProfileParserInf *))(*(_QWORD *)this + 96LL))(this);
    ProfileIdFromString = MFTraceValidation(v10, 4, v9, "failed to open device interface (%S) key!", a2);
    v12 = ProfileIdFromString;
    if ( ProfileIdFromString < 0 )
    {
      v13 = 0;
      if ( g_wppLevels )
      {
        v14 = 118;
LABEL_44:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v14,
          &WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids,
          this,
          ProfileIdFromString);
      }
LABEL_48:
      (*(void (__fastcall **)(ProfileParserInf *))(*(_QWORD *)this + 80LL))(this);
      if ( v13 )
        (*(void (__fastcall **)(ProfileEntryInf *))(*(_QWORD *)v13 + 16LL))(v13);
      return (unsigned int)v12;
    }
    *v5 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  }
  Value = ProfileRegReadValue(*v5, L"OEMCameraProfiles", (unsigned __int16 **)this + 12, (int *)this + 26);
  if ( Value >= 0 )
  {
    v12 = ProfileRegReadValue(*v5, L"ReferenceGUID", (unsigned __int16 *)this + 54, v16);
    if ( v12 < 0 )
    {
      if ( (unsigned __int8)byte_18008D62F >= 0x10u )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 37), 120, &WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids, a2);
      v18 = (*(__int64 (__fastcall **)(ProfileParserInf *))(*(_QWORD *)this + 96LL))(this);
      MFTraceValidation(v18, 1, (unsigned int)v12, "reference guid entry does not exist for %S", a2);
      v12 = 0;
    }
    v19 = (const unsigned __int16 *)*((_QWORD *)this + 12);
    v20 = 0;
LABEL_23:
    v21 = v19;
    while ( 1 )
    {
      v13 = 0;
      if ( !*v19 )
        break;
      v22 = *v21;
      v13 = 0;
      if ( !*v21 )
        break;
      memset_0(v28, 0, 0x208u);
      v26 = 0;
      pclsid = GUID_00000000_0000_0000_0000_000000000000;
      do
      {
        if ( v22 == 59 )
          break;
        v22 = *++v21;
      }
      while ( *v21 );
      StringCchCopyNW(v28, 0x104u, v19, v21 - v19);
      ProfileIdFromString = GetProfileIdFromString(v28, &pclsid, &v26);
      v12 = ProfileIdFromString;
      if ( ProfileIdFromString < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_48;
        v14 = 121;
        goto LABEL_44;
      }
      v23 = (ProfileEntryInf *)operator new(0x2E8u);
      if ( !v23
        || (v24 = ProfileEntryInf::ProfileEntryInf(v23, *((struct IMFCameraProfileValidation **)this + 10)),
            (v13 = v24) == 0) )
      {
        ProfileIdFromString = -2147024882;
        v12 = -2147024882;
        if ( !g_wppLevels )
          goto LABEL_48;
        v14 = 122;
        goto LABEL_44;
      }
      (*(void (__fastcall **)(ProfileEntryInf *))(*(_QWORD *)v24 + 8LL))(v24);
      ProfileIdFromString = (*(__int64 (__fastcall **)(ProfileEntryInf *, HKEY, unsigned __int16 *, GUID *, unsigned int))(*(_QWORD *)v13 + 104LL))(
                              v13,
                              *v5,
                              v28,
                              &pclsid,
                              v26);
      v12 = ProfileIdFromString;
      if ( ProfileIdFromString < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_48;
        v14 = 123;
        goto LABEL_44;
      }
      ProfileIdFromString = (*(__int64 (__fastcall **)(ProfileEntryInf *))(*(_QWORD *)v13 + 120LL))(v13);
      v12 = ProfileIdFromString;
      if ( ProfileIdFromString < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_48;
        v14 = 124;
        goto LABEL_44;
      }
      if ( !(unsigned int)CTUnkArray<ProfileEntry>::SetAtGrow((char *)this + 56, v20, v13) )
      {
        v12 = -2147024882;
        MFTraceError(
          "avcore\\mf\\core\\mediasource\\profiles\\profileparser.cpp",
          1272,
          "ProfileParserInf::GatherProfile",
          this,
          -2147024882,
          1);
        goto LABEL_48;
      }
      ++v20;
      if ( *v21 )
      {
        v19 = v21 + 1;
        goto LABEL_23;
      }
    }
    if ( v12 >= 0 )
      return (unsigned int)v12;
    goto LABEL_48;
  }
  if ( (unsigned __int8)byte_18008D62F >= 0x10u )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 37), 119, &WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids, a2);
  v17 = (*(__int64 (__fastcall **)(ProfileParserInf *))(*(_QWORD *)this + 96LL))(this);
  MFTraceValidation(v17, 1, (unsigned int)Value, "OEM INF entry does not exist for %S", a2);
  return 0;
}

```

## disassembly

```asm
0x180068590  mov     [rsp+arg_10], rbx
0x180068595  push    rbp
0x180068596  push    rsi
0x180068597  push    rdi
0x180068598  push    r12
0x18006859a  push    r13
0x18006859c  push    r14
0x18006859e  push    r15
0x1800685a0  sub     rsp, 270h
0x1800685a7  mov     rax, cs:__security_cookie
0x1800685ae  xor     rax, rsp
0x1800685b1  mov     [rsp+2A8h+var_48], rax
0x1800685b9  mov     rbx, rdx
0x1800685bc  mov     rdi, rcx
0x1800685bf  cmp     cs:byte_18008D62F, 10h
0x1800685c6  lea     r13, WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids
0x1800685cd  jb      short loc_1800685ED
0x1800685cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800685d6  mov     edx, 74h ; 't'
0x1800685db  mov     r9, rbx
0x1800685de  mov     r8, r13
0x1800685e1  mov     rcx, [rcx+128h]
0x1800685e8  call    WPP_SF_S
0x1800685ed  mov     rax, [rdi]
0x1800685f0  mov     rcx, rdi
0x1800685f3  mov     rax, [rax+60h]
0x1800685f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800685fc  mov     rcx, rax
0x1800685ff  mov     qword ptr [rsp+2A8h+ulFlags], rbx
0x180068604  lea     r9, aCheckingOemInf; "checking OEM INF defined profiles for %"...
0x18006860b  xor     r8d, r8d
0x18006860e  xor     edx, edx
0x180068610  call    ?MFTraceValidation@@YAJPEAUIMFCameraProfileValidation@@W4MF_CAMERA_PROFILE_VALIDATIONSTATE@@JPEBDZZ; MFTraceValidation(IMFCameraProfileValidation *,MF_CAMERA_PROFILE_VALIDATIONSTATE,long,char const *,...)
0x180068615  lea     r12, [rdi+58h]
0x180068619  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18006861d  mov     rcx, [r12]; hKey
0x180068621  lea     rax, [rcx-1]
0x180068625  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180068629  ja      short loc_180068635
0x18006862b  call    cs:__imp_RegCloseKey
0x180068631  mov     [r12], rbp
0x180068635  xor     r15d, r15d
0x180068638  mov     r9, r12; phkDeviceInterface
0x18006863b  mov     edx, 20019h; samDesired
0x180068640  mov     [rsp+2A8h+ulFlags], r15d; ulFlags
0x180068645  mov     rcx, rbx; pszDeviceInterface
0x180068648  lea     r14d, [r15+1]
0x18006864c  mov     r8d, r14d; Disposition
0x18006864f  call    cs:__imp_CM_Open_Device_Interface_KeyW
0x180068655  mov     esi, eax
0x180068657  test    eax, eax
0x180068659  jz      loc_1800686F3
0x18006865f  cmp     cs:byte_18008D62F, r14b
0x180068666  jb      short loc_180068685
0x180068668  mov     rcx, cs:WPP_GLOBAL_Control
0x18006866f  lea     edx, [r15+75h]
0x180068673  mov     r9, rbx
0x180068676  mov     r8, r13
0x180068679  mov     rcx, [rcx+128h]
0x180068680  call    WPP_SF_S
0x180068685  mov     edx, 0Dh; DefaultErr
0x18006868a  mov     ecx, esi; CmReturnCode
0x18006868c  call    cs:__imp_CM_MapCrToWin32Err
0x180068692  mov     esi, eax
0x180068694  test    eax, eax
0x180068696  jle     short loc_1800686A1
0x180068698  movzx   esi, ax
0x18006869b  or      esi, 80070000h
0x1800686a1  mov     rax, [rdi]
0x1800686a4  mov     rcx, rdi
0x1800686a7  mov     rax, [rax+60h]
0x1800686ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800686b0  lea     r9, aFailedToOpenDe; "failed to open device interface (%S) ke"...
0x1800686b7  mov     qword ptr [rsp+2A8h+ulFlags], rbx
0x1800686bc  mov     r8d, esi
0x1800686bf  mov     edx, 4
0x1800686c4  mov     rcx, rax
0x1800686c7  call    ?MFTraceValidation@@YAJPEAUIMFCameraProfileValidation@@W4MF_CAMERA_PROFILE_VALIDATIONSTATE@@JPEBDZZ; MFTraceValidation(IMFCameraProfileValidation *,MF_CAMERA_PROFILE_VALIDATIONSTATE,long,char const *,...)
0x1800686cc  mov     esi, eax
0x1800686ce  test    eax, eax
0x1800686d0  jns     short loc_1800686EF
0x1800686d2  mov     rbx, r15
0x1800686d5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1800686dc  jb      loc_1800689B3
0x1800686e2  mov     edx, 76h ; 'v'
0x1800686e7  mov     r8, r13
0x1800686ea  jmp     loc_180068986
0x1800686ef  mov     [r12], rbp
0x1800686f3  mov     rcx, [r12]; hkey
0x1800686f7  lea     r9, [rdi+68h]; int *
0x1800686fb  lea     r8, [rdi+60h]; unsigned __int16 **
0x1800686ff  lea     rdx, aOemcameraprofi; "OEMCameraProfiles"
0x180068706  call    ?ProfileRegReadValue@@YAJPEAUHKEY__@@PEBGPEAPEAGPEAH@Z; ProfileRegReadValue(HKEY__ *,ushort const *,ushort * *,int *)
0x18006870b  mov     esi, eax
0x18006870d  test    eax, eax
0x18006870f  jns     short loc_180068769
0x180068711  cmp     cs:byte_18008D62F, 10h
0x180068718  jb      short loc_180068738
0x18006871a  mov     rcx, cs:WPP_GLOBAL_Control
0x180068721  mov     edx, 77h ; 'w'
0x180068726  mov     r9, rbx
0x180068729  mov     r8, r13
0x18006872c  mov     rcx, [rcx+128h]
0x180068733  call    WPP_SF_S
0x180068738  mov     rax, [rdi]
0x18006873b  mov     rcx, rdi
0x18006873e  mov     rax, [rax+60h]
0x180068742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068747  mov     rcx, rax
0x18006874a  mov     qword ptr [rsp+2A8h+ulFlags], rbx
0x18006874f  lea     r9, aOemInfEntryDoe; "OEM INF entry does not exist for %S"
0x180068756  mov     r8d, esi
0x180068759  mov     edx, r14d
0x18006875c  call    ?MFTraceValidation@@YAJPEAUIMFCameraProfileValidation@@W4MF_CAMERA_PROFILE_VALIDATIONSTATE@@JPEBDZZ; MFTraceValidation(IMFCameraProfileValidation *,MF_CAMERA_PROFILE_VALIDATIONSTATE,long,char const *,...)
0x180068761  mov     esi, r15d
0x180068764  jmp     loc_1800689D6
0x180068769  mov     rcx, [r12]; HKEY
0x18006876d  lea     r8, [rdi+6Ch]; unsigned __int16 *
0x180068771  lea     rdx, aReferenceguid; "ReferenceGUID"
0x180068778  call    ?ProfileRegReadValue@@YAJPEAUHKEY__@@PEBGPEAGH@Z; ProfileRegReadValue(HKEY__ *,ushort const *,ushort *,int)
0x18006877d  mov     esi, eax
0x18006877f  test    eax, eax
0x180068781  jns     short loc_1800687D6
0x180068783  cmp     cs:byte_18008D62F, 10h
0x18006878a  jb      short loc_1800687AA
0x18006878c  mov     rcx, cs:WPP_GLOBAL_Control
0x180068793  mov     edx, 78h ; 'x'
0x180068798  mov     r9, rbx
0x18006879b  mov     r8, r13
0x18006879e  mov     rcx, [rcx+128h]
0x1800687a5  call    WPP_SF_S
0x1800687aa  mov     rax, [rdi]
0x1800687ad  mov     rcx, rdi
0x1800687b0  mov     rax, [rax+60h]
0x1800687b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800687b9  mov     rcx, rax
0x1800687bc  mov     qword ptr [rsp+2A8h+ulFlags], rbx
0x1800687c1  lea     r9, aReferenceGuidE; "reference guid entry does not exist for"...
0x1800687c8  mov     r8d, esi
0x1800687cb  mov     edx, r14d
0x1800687ce  call    ?MFTraceValidation@@YAJPEAUIMFCameraProfileValidation@@W4MF_CAMERA_PROFILE_VALIDATIONSTATE@@JPEBDZZ; MFTraceValidation(IMFCameraProfileValidation *,MF_CAMERA_PROFILE_VALIDATIONSTATE,long,char const *,...)
0x1800687d3  mov     esi, r15d
0x1800687d6  mov     rbp, [rdi+60h]
0x1800687da  mov     r13d, r15d
0x1800687dd  mov     r14, rbp
0x1800687e0  mov     rbx, r15
0x1800687e3  cmp     [rbp+0], r15w
0x1800687e8  jz      loc_1800689AF
0x1800687ee  movzx   r15d, word ptr [r14]
0x1800687f2  xor     eax, eax
0x1800687f4  mov     ebx, eax
0x1800687f6  test    r15w, r15w
0x1800687fa  jz      loc_1800689AF
0x180068800  xor     edx, edx; Val
0x180068802  lea     rcx, [rsp+2A8h+var_258]; void *
0x180068807  mov     r8d, 208h; Size
0x18006880d  call    memset_0
0x180068812  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180068819  xor     eax, eax
0x18006881b  mov     [rsp+2A8h+var_278], eax
0x18006881f  movdqu  xmmword ptr [rsp+2A8h+pclsid.Data1], xmm0
0x180068825  cmp     r15w, 3Bh ; ';'
0x18006882a  jz      short loc_18006883A
0x18006882c  add     r14, 2
0x180068830  movzx   r15d, word ptr [r14]
0x180068834  test    r15w, r15w
0x180068838  jnz     short loc_180068825
0x18006883a  mov     r9, r14
0x18006883d  lea     rcx, [rsp+2A8h+var_258]; unsigned __int16 *
0x180068842  sub     r9, rbp
0x180068845  mov     r8, rbp; unsigned __int16 *
0x180068848  sar     r9, 1; unsigned __int64
0x18006884b  mov     edx, 104h; unsigned __int64
0x180068850  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180068855  lea     r8, [rsp+2A8h+var_278]; unsigned int *
0x18006885a  lea     rdx, [rsp+2A8h+pclsid]; pclsid
0x18006885f  lea     rcx, [rsp+2A8h+var_258]; unsigned __int16 *
0x180068864  call    ?GetProfileIdFromString@@YAJPEBGPEAU_GUID@@PEAI@Z; GetProfileIdFromString(ushort const *,_GUID *,uint *)
0x180068869  xor     r15d, r15d
0x18006886c  mov     esi, eax
0x18006886e  test    eax, eax
0x180068870  js      loc_18006899F
0x180068876  mov     ecx, 2E8h; Size
0x18006887b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180068880  test    rax, rax
0x180068883  jz      loc_18006896A
0x180068889  mov     rdx, [rdi+50h]; struct IMFCameraProfileValidation *
0x18006888d  mov     rcx, rax; this
0x180068890  call    ??0ProfileEntryInf@@QEAA@PEAUIMFCameraProfileValidation@@@Z; ProfileEntryInf::ProfileEntryInf(IMFCameraProfileValidation *)
0x180068895  mov     rbx, rax
0x180068898  test    rax, rax
0x18006889b  jz      loc_18006896A
0x1800688a1  mov     rax, [rax]
0x1800688a4  mov     rcx, rbx
0x1800688a7  mov     rax, [rax+8]
0x1800688ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800688b0  mov     rax, [rbx]
0x1800688b3  lea     r9, [rsp+2A8h+pclsid]
0x1800688b8  mov     ecx, [rsp+2A8h+var_278]
0x1800688bc  lea     r8, [rsp+2A8h+var_258]
0x1800688c1  mov     rdx, [r12]
0x1800688c5  mov     [rsp+2A8h+ulFlags], ecx
0x1800688c9  mov     rcx, rbx
0x1800688cc  mov     rax, [rax+68h]
0x1800688d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800688d5  mov     esi, eax
0x1800688d7  test    eax, eax
0x1800688d9  js      short loc_18006895A
0x1800688db  mov     rax, [rbx]
0x1800688de  mov     rcx, rbx
0x1800688e1  mov     rax, [rax+78h]
0x1800688e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800688ea  mov     esi, eax
0x1800688ec  test    eax, eax
0x1800688ee  js      short loc_18006894A
0x1800688f0  lea     rcx, [rdi+38h]
0x1800688f4  mov     r8, rbx
0x1800688f7  mov     edx, r13d
0x1800688fa  call    ?SetAtGrow@?$CTUnkArray@VProfileEntry@@@@QEAAHKPEAVProfileEntry@@@Z; CTUnkArray<ProfileEntry>::SetAtGrow(ulong,ProfileEntry *)
0x1800688ff  test    eax, eax
0x180068901  jz      short loc_180068919
0x180068903  inc     r13d
0x180068906  cmp     [r14], r15w
0x18006890a  jz      loc_1800687E0
0x180068910  lea     rbp, [r14+2]
0x180068914  jmp     loc_1800687DD
0x180068919  mov     eax, 8007000Eh
0x18006891e  mov     [rsp+2A8h+var_280], 1
0x180068926  mov     r9, rdi
0x180068929  mov     [rsp+2A8h+ulFlags], eax
0x18006892d  lea     r8, aProfileparseri; "ProfileParserInf::GatherProfile"
0x180068934  mov     edx, 4F8h
0x180068939  lea     rcx, aAvcoreMfCoreMe; "avcore\\mf\\core\\mediasource\\profiles"...
0x180068940  mov     esi, eax
0x180068942  call    cs:__imp_MFTraceError
0x180068948  jmp     short loc_1800689B3
0x18006894a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180068951  jb      short loc_1800689B3
0x180068953  mov     edx, 7Ch ; '|'
0x180068958  jmp     short loc_18006897F
0x18006895a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180068961  jb      short loc_1800689B3
0x180068963  mov     edx, 7Bh ; '{'
0x180068968  jmp     short loc_18006897F
0x18006896a  mov     eax, 8007000Eh
0x18006896f  mov     esi, eax
0x180068971  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180068978  jb      short loc_1800689B3
0x18006897a  mov     edx, 7Ah ; 'z'
0x18006897f  lea     r8, WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids
0x180068986  mov     rcx, cs:WPP_GLOBAL_Control
0x18006898d  mov     r9, rdi
0x180068990  mov     [rsp+2A8h+ulFlags], eax
0x180068994  mov     rcx, [rcx+10h]
0x180068998  call    WPP_SF_qD
0x18006899d  jmp     short loc_1800689B3
0x18006899f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800689a6  jb      short loc_1800689B3
0x1800689a8  mov     edx, 79h ; 'y'
0x1800689ad  jmp     short loc_18006897F
0x1800689af  test    esi, esi
0x1800689b1  jns     short loc_1800689D6
0x1800689b3  mov     rax, [rdi]
0x1800689b6  mov     rcx, rdi
0x1800689b9  mov     rax, [rax+50h]
0x1800689bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800689c2  test    rbx, rbx
0x1800689c5  jz      short loc_1800689D6
0x1800689c7  mov     rax, [rbx]
0x1800689ca  mov     rcx, rbx
0x1800689cd  mov     rax, [rax+10h]
0x1800689d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800689d6  mov     eax, esi
0x1800689d8  mov     rcx, [rsp+2A8h+var_48]
0x1800689e0  xor     rcx, rsp; StackCookie
0x1800689e3  call    __security_check_cookie
0x1800689e8  mov     rbx, [rsp+2A8h+arg_10]
0x1800689f0  add     rsp, 270h
0x1800689f7  pop     r15
0x1800689f9  pop     r14
0x1800689fb  pop     r13
0x1800689fd  pop     r12
0x1800689ff  pop     rdi
0x180068a00  pop     rsi
0x180068a01  pop     rbp
0x180068a02  retn
```
