# CWwanModemProfileController::SetOperatorServiceEnablementForPhoneModemProfile(_WWAN_OPERATOR_SERVICE_ENABLEMENT const &,ulong *,ulong *)

- ea: `0x180037b00`
- end: `0x180037ea2`
- name: `?SetOperatorServiceEnablementForPhoneModemProfile@CWwanModemProfileController@@IEAAKAEBU_WWAN_OPERATOR_SERVICE_ENABLEMENT@@PEAK1@Z`
- size: `930`
- prototype: `unsigned int __fastcall(CWwanModemProfileController *__hidden this, GUID *rguid, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18002de74`

## callees

- `0x1800085d0`
- `0x1800094d0`
- `0x1800094f4`
- `0x18000f0f4`
- `0x180012300`
- `0x180013288`
- `0x180013588`
- `0x180014154`
- `0x180014f1c`
- `0x180019b1c`
- `0x180019d0c`
- `0x180033928`
- `0x180033994`
- `0x180034404`
- `0x1800364ac`
- `0x180037b00`
- `0x18003bc04`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180037dfd`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180037dfd`

## string_xrefs

- `0x180037b4c`: `service not found`
- `0x180037b53`: `CWwanModemProfileController::SetOperatorServiceEnablementForPhoneModemProfile`
- `0x180037b98`: `CWwanModemProfileController::SetOperatorServiceEnablementForPhoneModemProfile`
- `0x180037bd9`: `CWwanModemProfileController::SetOperatorServiceEnablementForPhoneModemProfile`
- `0x180037c21`: `CWwanModemProfileController::SetOperatorServiceEnablementForPhoneModemProfile`
- `0x180037c83`: `CWwanModemProfileController::SetOperatorServiceEnablementForPhoneModemProfile`
- `0x180037cfe`: `CWwanModemProfileController::SetOperatorServiceEnablementForPhoneModemProfile`
- `0x180037dd3`: `CWwanModemProfileController::SetOperatorServiceEnablementForPhoneModemProfile`
- `0x180037e26`: `CWwanModemProfileController::SetOperatorServiceEnablementForPhoneModemProfile`
- `0x180037e5c`: `CWwanModemProfileController::SetOperatorServiceEnablementForPhoneModemProfile`
- `0x180037b91`: ` service enablement policy set but without change: %d (type %d)`
- `0x180037c7a`: `Unable to malloc for DMConfigData`
- `0x180037cf2`: `StringCchCopy failed to copy PropertyGroup %d`
- `0x180037d7a`: `StringCchCopy failed to copy PropertyName %d`
- `0x180037dca`: `Function SendDmConfigBinarySet failed to set Apn Enablement %d`
- `0x180037e1d`: ` Function SendDmConfigBinarySet successfully sent Apn Enablement requestID : %llu ,                         return status : 0x%x , PurposeGUID :{%s} , Enablement value : %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWwanModemProfileController::SetOperatorServiceEnablementForPhoneModemProfile(
        CWwanDataExecutorState **this,
        GUID *rguid,
        unsigned int *a3,
        unsigned int *a4)
{
  int v6; // r12d
  unsigned int SupportedContextByPurpose; // eax
  const struct _GUID *v8; // rdx
  unsigned int v9; // r8d
  __int64 v11; // r13
  unsigned int ExecutorICCID; // eax
  unsigned int v13; // ebx
  int v14; // eax
  __int64 v15; // r14
  unsigned __int8 *v16; // rbx
  int v17; // eax
  CWwanModemProfileController *v18; // rcx
  const unsigned __int16 *v19; // rax
  int v20; // eax
  unsigned int *v21; // r15
  unsigned int *v22; // r14
  unsigned int v23; // eax
  unsigned int *v24; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v25; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int *v26; // [rsp+48h] [rbp-B8h]
  unsigned int *v27; // [rsp+50h] [rbp-B0h]
  struct _GUID Buf1; // [rsp+58h] [rbp-A8h] BYREF
  struct _GUID v29; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v30[16]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v31; // [rsp+90h] [rbp-70h]
  _DWORD v32[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v33; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 v34[21]; // [rsp+B8h] [rbp-48h] BYREF
  OLECHAR sz[40]; // [rsp+F0h] [rbp-10h] BYREF

  v26 = a4;
  v27 = a3;
  v6 = rguid[1].Data1 != 0;
  SupportedContextByPurpose = CWwanModemProfileController::FindSupportedContextByPurpose(
                                (CWwanModemProfileController *)this,
                                rguid);
  if ( SupportedContextByPurpose >= 3 )
  {
    WwanLog::Error(
      "CWwanModemProfileController::SetOperatorServiceEnablementForPhoneModemProfile",
      v8,
      L"service not found");
    return 87;
  }
  v11 = 230LL * SupportedContextByPurpose;
  if ( v6 == LODWORD(this[v11 + 436]) )
  {
    WwanLog::Info(
      "CWwanModemProfileController::SetOperatorServiceEnablementForPhoneModemProfile",
      v8,
      L" service enablement policy set but without change: %d (type %d)");
    return 0;
  }
  memset(v34, 0, sizeof(v34));
  ExecutorICCID = CWwanDataExecutorState::GetExecutorICCID(this[5], v34, v9);
  v13 = ExecutorICCID;
  if ( ExecutorICCID )
  {
    WwanLog::Error(
      "CWwanModemProfileController::SetOperatorServiceEnablementForPhoneModemProfile",
      0,
      L"failed to get ICCID %d",
      ExecutorICCID);
    return v13;
  }
  v33 = 0;
  v32[0] = 1;
  v32[1] = 24;
  v14 = IccidStringToBCD((const unsigned __int16 (*)[21])v34, (unsigned __int8 (*)[10])&v33);
  v13 = v14;
  if ( v14 < 0 )
  {
    WwanLog::Error(
      "CWwanModemProfileController::SetOperatorServiceEnablementForPhoneModemProfile",
      0,
      L"failed to convert ICCID [%u]",
      (unsigned int)v14);
    if ( (v13 & 0x1FFF0000) == 0x70000 )
      return (unsigned __int16)v13;
    return v13;
  }
  std::wstring::wstring(v30, L"APN_ENABLE");
  v15 = (unsigned int)(2 * v31 + 7);
  std::make_unique<unsigned char [0],0>(&v25, v15 + 568);
  v16 = v25;
  if ( !v25 )
  {
    WwanLog::Error(
      "CWwanModemProfileController::SetOperatorServiceEnablementForPhoneModemProfile",
      0,
      L"Unable to malloc for DMConfigData");
LABEL_13:
    std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v25);
    std::wstring::_Tidy_deallocate(v30);
    return 122;
  }
  memset_0(v25, 0, v15 + 568);
  *(_DWORD *)v16 = 1;
  *((_DWORD *)v16 + 1) = v15 + 568;
  *((_DWORD *)v16 + 134) = 1;
  v17 = StringCchCopyW((unsigned __int16 *)v16 + 4, 0x100u, L"GROUP_PROFILE_INFO");
  if ( v17 < 0 )
  {
    WwanLog::Error(
      "CWwanModemProfileController::SetOperatorServiceEnablementForPhoneModemProfile",
      0,
      L"StringCchCopy failed to copy PropertyGroup %d",
      (unsigned int)v17);
    goto LABEL_13;
  }
  v29 = *rguid;
  CWwanModemProfileController::GetOemConnIdFromPurpose(v18, &Buf1, &v29);
  if ( memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
  {
    *(struct _GUID *)(v16 + 520) = Buf1;
    *((_QWORD *)v16 + 68) = 1;
    v19 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30);
    v20 = StringCchCopyW((unsigned __int16 *)v16 + 284, v31 + 1, v19);
    if ( v20 >= 0 )
    {
      *((_DWORD *)v16 + 138) = 1;
      v16[560] = rguid[1].Data1 != 0;
      v21 = v26;
      v22 = v27;
      v23 = CWwanModemProfileController::SendDmConfigBinarySet(
              (CWwanModemProfileController *)this,
              (struct WWAN_SET_DM_CONFIG_BINARY_INFO *)v32,
              *((_DWORD *)v16 + 1),
              v16,
              v27,
              v26);
      v13 = v23;
      if ( v23 )
      {
        WwanLog::Error(
          "CWwanModemProfileController::SetOperatorServiceEnablementForPhoneModemProfile",
          0,
          L"Function SendDmConfigBinarySet failed to set Apn Enablement %d",
          v23);
      }
      else
      {
        memset_0(sz, 0, 0x4Au);
        StringFromGUID2(rguid, sz, 37);
        LODWORD(v24) = *v21;
        WwanLog::Info(
          "CWwanModemProfileController::SetOperatorServiceEnablementForPhoneModemProfile",
          0,
          L" Function SendDmConfigBinarySet successfully sent Apn Enablement requestID : %llu ,                         re"
           "turn status : 0x%x , PurposeGUID :{%s} , Enablement value : %d",
          *v22,
          v24,
          sz,
          rguid[1].Data1);
        LODWORD(this[v11 + 436]) = v6;
      }
      std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v25);
      std::wstring::_Tidy_deallocate(v30);
      return v13;
    }
    WwanLog::Error(
      "CWwanModemProfileController::SetOperatorServiceEnablementForPhoneModemProfile",
      0,
      L"StringCchCopy failed to copy PropertyName %d",
      (unsigned int)v20);
    goto LABEL_13;
  }
  WwanLog::Error(
    "CWwanModemProfileController::SetOperatorServiceEnablementForPhoneModemProfile",
    0,
    L"Profile Enablement policy does not apply for the requested purpose");
  std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v25);
  std::wstring::_Tidy_deallocate(v30);
  return 775;
}

```

## disassembly

```asm
0x180037b00  push    rbp
0x180037b02  push    rbx
0x180037b03  push    rsi
0x180037b04  push    rdi
0x180037b05  push    r12
0x180037b07  push    r13
0x180037b09  push    r14
0x180037b0b  push    r15
0x180037b0d  lea     rbp, [rsp-58h]
0x180037b12  sub     rsp, 158h
0x180037b19  mov     rax, cs:__security_cookie
0x180037b20  xor     rax, rsp
0x180037b23  mov     [rbp+90h+var_50], rax
0x180037b27  mov     [rsp+190h+var_148], r9
0x180037b2c  mov     [rsp+190h+var_140], r8
0x180037b31  mov     rdi, rdx
0x180037b34  mov     rsi, rcx
0x180037b37  xor     r12d, r12d
0x180037b3a  cmp     [rdx+10h], r12d
0x180037b3e  setnz   r12b
0x180037b42  call    ?FindSupportedContextByPurpose@CWwanModemProfileController@@AEAAKAEBU_GUID@@@Z; CWwanModemProfileController::FindSupportedContextByPurpose(_GUID const &)
0x180037b47  cmp     eax, 3
0x180037b4a  jb      short loc_180037B69
0x180037b4c  lea     r8, aServiceNotFoun; "service not found"
0x180037b53  lea     rcx, aCwwanmodemprof_1; "CWwanModemProfileController::SetOperato"...
0x180037b5a  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180037b5f  mov     eax, 57h ; 'W'
0x180037b64  jmp     loc_180037E82
0x180037b69  mov     eax, eax
0x180037b6b  imul    r13, rax, 730h
0x180037b72  mov     r9d, [rsi+r13+0DA0h]
0x180037b7a  cmp     r12d, r9d
0x180037b7d  jnz     short loc_180037BAB
0x180037b7f  lea     rax, [rax+rax*2]
0x180037b83  lea     rcx, ?m_s_contextTypePurposeList@CWwanModemProfileController@@0QBUWwanModemProfileTypePurposeMap@@B; WwanModemProfileTypePurposeMap const near * const CWwanModemProfileController::m_s_contextTypePurposeList
0x180037b8a  mov     eax, [rcx+rax*8]
0x180037b8d  mov     dword ptr [rsp+190h+var_170], eax
0x180037b91  lea     r8, aServiceEnablem_0; " service enablement policy set but with"...
0x180037b98  lea     rcx, aCwwanmodemprof_1; "CWwanModemProfileController::SetOperato"...
0x180037b9f  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180037ba4  xor     eax, eax
0x180037ba6  jmp     loc_180037E82
0x180037bab  xorps   xmm0, xmm0
0x180037bae  movups  xmmword ptr [rbp+90h+var_D8], xmm0
0x180037bb2  movups  xmmword ptr [rbp+90h+var_D8+10h], xmm0
0x180037bb6  movups  xmmword ptr [rbp+90h+var_D8+1Ah], xmm0
0x180037bba  lea     rdx, [rbp+90h+var_D8]; unsigned __int16 *
0x180037bbe  mov     rcx, [rsi+28h]; this
0x180037bc2  call    ?GetExecutorICCID@CWwanDataExecutorState@@QEAAKPEAGK@Z; CWwanDataExecutorState::GetExecutorICCID(ushort *,ulong)
0x180037bc7  mov     ebx, eax
0x180037bc9  test    eax, eax
0x180037bcb  jz      short loc_180037BEC
0x180037bcd  mov     r9d, eax
0x180037bd0  lea     r8, aFailedToGetIcc; "failed to get ICCID %d"
0x180037bd7  xor     edx, edx; struct _GUID *
0x180037bd9  lea     rcx, aCwwanmodemprof_1; "CWwanModemProfileController::SetOperato"...
0x180037be0  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180037be5  mov     eax, ebx
0x180037be7  jmp     loc_180037E82
0x180037bec  xorps   xmm0, xmm0
0x180037bef  movdqu  [rbp+90h+var_E8], xmm0
0x180037bf4  mov     [rbp+90h+var_F0], 1
0x180037bfb  mov     [rbp+90h+var_EC], 18h
0x180037c02  lea     rdx, [rbp+90h+var_E8]; unsigned __int8 (*)[10]
0x180037c06  lea     rcx, [rbp+90h+var_D8]; unsigned __int16 (*)[21]
0x180037c0a  call    ?IccidStringToBCD@@YAJAEAY0BF@$$CBGAEAY09E@Z; IccidStringToBCD(ushort const (&)[21],uchar (&)[10])
0x180037c0f  mov     ebx, eax
0x180037c11  test    eax, eax
0x180037c13  jns     short loc_180037C42
0x180037c15  mov     r9d, eax
0x180037c18  lea     r8, aFailedToConver; "failed to convert ICCID [%u]"
0x180037c1f  xor     edx, edx; struct _GUID *
0x180037c21  lea     rcx, aCwwanmodemprof_1; "CWwanModemProfileController::SetOperato"...
0x180037c28  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180037c2d  mov     ecx, ebx
0x180037c2f  and     ecx, 1FFF0000h
0x180037c35  cmp     ecx, 70000h
0x180037c3b  jnz     short loc_180037BE5
0x180037c3d  movzx   ebx, bx
0x180037c40  jmp     short loc_180037BE5
0x180037c42  lea     rdx, aApnEnable; "APN_ENABLE"
0x180037c49  lea     rcx, [rbp+90h+var_110]
0x180037c4d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180037c52  nop
0x180037c53  mov     eax, dword ptr [rbp+90h+var_100]
0x180037c56  lea     r14d, ds:7[rax*2]
0x180037c5e  lea     rdx, [r14+238h]
0x180037c65  lea     rcx, [rsp+190h+var_150]
0x180037c6a  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x180037c6f  nop
0x180037c70  mov     rbx, [rsp+190h+var_150]
0x180037c75  test    rbx, rbx
0x180037c78  jnz     short loc_180037CAE
0x180037c7a  lea     r8, aUnableToMalloc; "Unable to malloc for DMConfigData"
0x180037c81  xor     edx, edx; struct _GUID *
0x180037c83  lea     rcx, aCwwanmodemprof_1; "CWwanModemProfileController::SetOperato"...
0x180037c8a  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180037c8f  nop
0x180037c90  lea     rcx, [rsp+190h+var_150]
0x180037c95  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x180037c9a  nop
0x180037c9b  lea     rcx, [rbp+90h+var_110]
0x180037c9f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037ca4  mov     eax, 7Ah ; 'z'
0x180037ca9  jmp     loc_180037E82
0x180037cae  lea     r8, [r14+238h]; Size
0x180037cb5  xor     edx, edx; Val
0x180037cb7  mov     rcx, rbx; void *
0x180037cba  call    memset_0
0x180037cbf  mov     r15d, 1
0x180037cc5  mov     [rbx], r15d
0x180037cc8  lea     eax, [r14+238h]
0x180037ccf  mov     [rbx+4], eax
0x180037cd2  mov     [rbx+218h], r15d
0x180037cd9  lea     rcx, [rbx+8]; unsigned __int16 *
0x180037cdd  lea     r8, aGroupProfileIn; "GROUP_PROFILE_INFO"
0x180037ce4  mov     edx, 100h; unsigned __int64
0x180037ce9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180037cee  test    eax, eax
0x180037cf0  jns     short loc_180037D0C
0x180037cf2  lea     r8, aStringcchcopyF_2; "StringCchCopy failed to copy PropertyGr"...
0x180037cf9  mov     r9d, eax
0x180037cfc  xor     edx, edx; struct _GUID *
0x180037cfe  lea     rcx, aCwwanmodemprof_1; "CWwanModemProfileController::SetOperato"...
0x180037d05  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180037d0a  jmp     short loc_180037C90
0x180037d0c  movups  xmm0, xmmword ptr [rdi]
0x180037d0f  movdqu  xmmword ptr [rsp+190h+var_120.Data1], xmm0
0x180037d15  lea     r8, [rsp+190h+var_120]; struct _GUID
0x180037d1a  lea     rdx, [rsp+190h+Buf1]; retstr
0x180037d1f  call    ?GetOemConnIdFromPurpose@CWwanModemProfileController@@AEAA?AU_GUID@@U2@@Z; CWwanModemProfileController::GetOemConnIdFromPurpose(_GUID)
0x180037d24  mov     r8d, 10h; Size
0x180037d2a  lea     rdx, GUID_NULL; Buf2
0x180037d31  lea     rcx, [rsp+190h+Buf1]; Buf1
0x180037d36  call    memcmp_0
0x180037d3b  test    eax, eax
0x180037d3d  jz      loc_180037E53
0x180037d43  movups  xmm0, xmmword ptr [rsp+190h+Buf1.Data1]
0x180037d48  movdqu  xmmword ptr [rbx+208h], xmm0
0x180037d50  mov     [rbx+220h], r15
0x180037d57  lea     rcx, [rbp+90h+var_110]
0x180037d5b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180037d60  mov     r8, rax; unsigned __int16 *
0x180037d63  mov     rdx, [rbp+90h+var_100]
0x180037d67  inc     rdx; unsigned __int64
0x180037d6a  lea     rcx, [rbx+238h]; unsigned __int16 *
0x180037d71  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180037d76  test    eax, eax
0x180037d78  jns     short loc_180037D86
0x180037d7a  lea     r8, aStringcchcopyF_0; "StringCchCopy failed to copy PropertyNa"...
0x180037d81  jmp     loc_180037CF9
0x180037d86  mov     [rbx+228h], r15d
0x180037d8d  cmp     dword ptr [rdi+10h], 0
0x180037d91  setnz   al
0x180037d94  mov     [rbx+230h], al
0x180037d9a  mov     r15, [rsp+190h+var_148]
0x180037d9f  mov     [rsp+190h+var_168], r15; unsigned int *
0x180037da4  mov     r14, [rsp+190h+var_140]
0x180037da9  mov     [rsp+190h+var_170], r14; unsigned int *
0x180037dae  mov     r9, rbx; unsigned __int8 *
0x180037db1  mov     r8d, [rbx+4]; unsigned int
0x180037db5  lea     rdx, [rbp+90h+var_F0]; struct WWAN_SET_DM_CONFIG_BINARY_INFO *
0x180037db9  mov     rcx, rsi; this
0x180037dbc  call    ?SendDmConfigBinarySet@CWwanModemProfileController@@QEAAKPEAUWWAN_SET_DM_CONFIG_BINARY_INFO@@KPEAEPEAK2@Z; CWwanModemProfileController::SendDmConfigBinarySet(WWAN_SET_DM_CONFIG_BINARY_INFO *,ulong,uchar *,ulong *,ulong *)
0x180037dc1  mov     ebx, eax
0x180037dc3  test    eax, eax
0x180037dc5  jz      short loc_180037DE1
0x180037dc7  mov     r9d, eax
0x180037dca  lea     r8, aFunctionSenddm; "Function SendDmConfigBinarySet failed t"...
0x180037dd1  xor     edx, edx; struct _GUID *
0x180037dd3  lea     rcx, aCwwanmodemprof_1; "CWwanModemProfileController::SetOperato"...
0x180037dda  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180037ddf  jmp     short loc_180037E3A
0x180037de1  xor     edx, edx; Val
0x180037de3  lea     r8d, [rdx+4Ah]; Size
0x180037de7  lea     rcx, [rbp+90h+sz]; void *
0x180037deb  call    memset_0
0x180037df0  mov     r8d, 25h ; '%'; cchMax
0x180037df6  lea     rdx, [rbp+90h+sz]; lpsz
0x180037dfa  mov     rcx, rdi; rguid
0x180037dfd  call    cs:__imp_StringFromGUID2
0x180037e03  mov     eax, [rdi+10h]
0x180037e06  mov     [rsp+190h+var_160], eax
0x180037e0a  lea     rax, [rbp+90h+sz]
0x180037e0e  mov     [rsp+190h+var_168], rax
0x180037e13  mov     eax, [r15]
0x180037e16  mov     dword ptr [rsp+190h+var_170], eax
0x180037e1a  mov     r9d, [r14]
0x180037e1d  lea     r8, aFunctionSenddm_0; " Function SendDmConfigBinarySet success"...
0x180037e24  xor     edx, edx; struct _GUID *
0x180037e26  lea     rcx, aCwwanmodemprof_1; "CWwanModemProfileController::SetOperato"...
0x180037e2d  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180037e32  mov     [rsi+r13+0DA0h], r12d
0x180037e3a  lea     rcx, [rsp+190h+var_150]
0x180037e3f  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x180037e44  nop
0x180037e45  lea     rcx, [rbp+90h+var_110]
0x180037e49  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037e4e  jmp     loc_180037BE5
0x180037e53  lea     r8, aProfileEnablem; "Profile Enablement policy does not appl"...
0x180037e5a  xor     edx, edx; struct _GUID *
0x180037e5c  lea     rcx, aCwwanmodemprof_1; "CWwanModemProfileController::SetOperato"...
0x180037e63  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180037e68  nop
0x180037e69  lea     rcx, [rsp+190h+var_150]
0x180037e6e  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x180037e73  nop
0x180037e74  lea     rcx, [rbp+90h+var_110]
0x180037e78  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037e7d  mov     eax, 307h
0x180037e82  mov     rcx, [rbp+90h+var_50]
0x180037e86  xor     rcx, rsp; StackCookie
0x180037e89  call    __security_check_cookie
0x180037e8e  add     rsp, 158h
0x180037e95  pop     r15
0x180037e97  pop     r14
0x180037e99  pop     r13
0x180037e9b  pop     r12
0x180037e9d  pop     rdi
0x180037e9e  pop     rsi
0x180037e9f  pop     rbx
0x180037ea0  pop     rbp
0x180037ea1  retn
```
