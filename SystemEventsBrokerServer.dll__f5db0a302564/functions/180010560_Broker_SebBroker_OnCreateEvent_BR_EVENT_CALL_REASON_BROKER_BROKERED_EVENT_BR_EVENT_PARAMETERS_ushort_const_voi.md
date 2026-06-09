# Broker::SebBroker::OnCreateEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,_BR_EVENT_PARAMETERS *,ushort const *,void *,void *,void *,void * *,ulong *,_BR_NEW_EVENT_INFORMATION *)

- ea: `0x180010560`
- end: `0x180010ba7`
- name: `?OnCreateEvent@SebBroker@Broker@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAU_BR_EVENT_PARAMETERS@@PEBGPEAX55PEAPEAXPEAKPEAU_BR_NEW_EVENT_INFORMATION@@@Z`
- size: `1607`
- prototype: `__int64 __fastcall(int, _QWORD *, __int64, struct _BR_EVENT_PARAMETERS *, PCWSTR packageFullName, PSID pSid, __int64, __int64, _QWORD *, _DWORD *, __int64)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800030e0`
- `0x180004250`
- `0x180005a50`
- `0x1800076a0`
- `0x180009340`
- `0x18000b168`
- `0x18000beb4`
- `0x18000da40`
- `0x18000f370`
- `0x180010560`
- `0x180010bb0`
- `0x180010c20`
- `0x180010cd0`
- `0x180010e50`
- `0x180011190`
- `0x180014618`
- `0x18001a5dc`
- `0x18001ab34`
- `0x18001cf50`
- `0x18001cf74`
- `0x18001d9ac`
- `0x18001e3bc`
- `0x18001f3fc`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010877`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010877`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001085a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001085a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800108ce`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800108ce`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180010942`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180010942`

## pseudocode

```c
__int64 __fastcall Broker::SebBroker::OnCreateEvent(
        int a1,
        _QWORD *a2,
        __int64 a3,
        struct _BR_EVENT_PARAMETERS *a4,
        PCWSTR packageFullName,
        PSID pSid,
        __int64 a7,
        __int64 a8,
        _QWORD *a9,
        _DWORD *a10,
        __int64 a11)
{
  __int64 v12; // rax
  _QWORD *v14; // r9
  _DWORD *v15; // r8
  __int64 v16; // rdx
  char v17; // r14
  __m128i v18; // xmm0
  unsigned int v19; // r12d
  __int64 v20; // r13
  unsigned int v21; // edx
  _BYTE **AppId; // rax
  _QWORD *v23; // rbx
  DWORD LastError; // eax
  size_t LengthSid; // r9
  __int64 v26; // rbx
  __int64 v27; // r8
  __int64 v28; // rdx
  _QWORD *v29; // rax
  __int64 v31; // rax
  UINT32 packageFamilyNameLength; // [rsp+40h] [rbp-348h] BYREF
  int v33; // [rsp+44h] [rbp-344h]
  void (__fastcall ***v34)(_QWORD, __int64); // [rsp+48h] [rbp-340h] BYREF
  __int64 v35; // [rsp+50h] [rbp-338h]
  __int64 v36; // [rsp+58h] [rbp-330h]
  _DWORD *v37; // [rsp+60h] [rbp-328h]
  _QWORD *v38; // [rsp+68h] [rbp-320h]
  _QWORD *v39; // [rsp+70h] [rbp-318h]
  HANDLE v40[2]; // [rsp+78h] [rbp-310h] BYREF
  __int128 v41; // [rsp+88h] [rbp-300h] BYREF
  __int64 v42; // [rsp+98h] [rbp-2F0h]
  __int128 v43; // [rsp+A0h] [rbp-2E8h] BYREF
  __int64 v44; // [rsp+B0h] [rbp-2D8h]
  std::_Ref_count_base *v45[2]; // [rsp+C0h] [rbp-2C8h]
  Broker::BILayer::Failure *v46; // [rsp+D0h] [rbp-2B8h] BYREF
  Broker::Win32Error *v47; // [rsp+D8h] [rbp-2B0h] BYREF
  Broker::BrokerCommonException *v48; // [rsp+E0h] [rbp-2A8h] BYREF
  void **pExceptionObject; // [rsp+E8h] [rbp-2A0h] BYREF
  __int128 v50; // [rsp+F0h] [rbp-298h]
  int v51; // [rsp+100h] [rbp-288h]
  void **v52; // [rsp+108h] [rbp-280h] BYREF
  __int128 v53; // [rsp+110h] [rbp-278h]
  int v54; // [rsp+120h] [rbp-268h]
  _BYTE *v55[3]; // [rsp+130h] [rbp-258h] BYREF
  char *v56[4]; // [rsp+148h] [rbp-240h] BYREF
  char *v57[5]; // [rsp+168h] [rbp-220h] BYREF
  _BYTE *v58[12]; // [rsp+190h] [rbp-1F8h] BYREF
  _BYTE *v59[12]; // [rsp+1F0h] [rbp-198h] BYREF
  WCHAR packageFamilyName[128]; // [rsp+250h] [rbp-138h] BYREF

  v12 = a3;
  v35 = a3;
  v39 = a2;
  v33 = a1;
  v14 = a9;
  v38 = a9;
  v15 = a10;
  v37 = a10;
  v16 = a11;
  v36 = a11;
  v17 = 0;
  packageFamilyNameLength = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
    v12 = v35;
    v16 = v36;
    v15 = v37;
    v14 = v38;
  }
  v18 = 0;
  *(_OWORD *)v45 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  if ( a2 && v12 && a4 && v14 && v16 && v15 )
  {
    if ( Broker::SebBroker::Instance && *(_BYTE *)Broker::SebBroker::Instance )
    {
      if ( *(&Broker::SebBroker::Instance + 1) )
        _InterlockedIncrement((volatile signed __int32 *)*(&Broker::SebBroker::Instance + 1) + 2);
      v18 = *(__m128i *)&Broker::SebBroker::Instance;
    }
    v45[0] = (std::_Ref_count_base *)v18.m128i_i64[0];
    v45[1] = (std::_Ref_count_base *)_mm_srli_si128(v18, 8).m128i_u64[0];
    if ( v18.m128i_i64[0] )
    {
      if ( *(_QWORD **)(v18.m128i_i64[0] + 136) == a2 )
      {
        try
        {
          Broker::SebBroker::UnpackRpcParameters(
            a4,
            (struct _SebiSystemEventCreationParameter *)&v41,
            (struct _SebiSystemEventFilterParameter *)&v43);
          v19 = DWORD2(v41);
          v20 = 6LL * SDWORD2(v41);
          HIDWORD(v42) = *((_DWORD *)&Broker::EventPolicyTable + 12 * SDWORD2(v41) + 1);
          if ( v33 == 1 )
          {
            Broker::RpcClientToken::RpcClientToken((Broker::RpcClientToken *)v40);
            if ( Broker::RpcClientToken::IsAppContainer(v40) )
            {
              v21 = *((_DWORD *)&Broker::EventPolicyTable + 2 * v20 + 8);
              if ( v21 != -1 && !Broker::RpcClientToken::CheckCapability((Broker::RpcClientToken *)v40, v21, 0) )
              {
                if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  AppId = Broker::RpcClientToken::GetAppId((__int64)v40, v59, 0, 0);
                  packageFamilyNameLength = 1;
                  v23 = AppId + 7;
                  if ( (unsigned __int64)AppId[10] > 7 )
                    v23 = (_QWORD *)*v23;
                  Broker::RpcClientToken::GetAppId((__int64)v40, v58, 0, 0);
                  v17 = 3;
                  WPP_SF__sid_S(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v23);
                }
                if ( (v17 & 2) != 0 )
                {
                  v17 &= ~2u;
                  Broker::ApplicationIdentity::~ApplicationIdentity((Broker::ApplicationIdentity *)v58);
                }
                if ( (v17 & 1) != 0 )
                  Broker::ApplicationIdentity::~ApplicationIdentity((Broker::ApplicationIdentity *)v59);
                v50 = 0;
                v51 = 5;
                pExceptionObject = &Broker::AccessDenied::`vftable';
                throw (Broker::AccessDenied *)&pExceptionObject;
              }
            }
            if ( !CloseHandle(v40[1])
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              LastError = GetLastError();
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                18,
                WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids,
                LastError);
            }
          }
          std::vector<_GUID>::vector<_GUID>(v55);
          std::wstring::wstring(v56);
          std::wstring::wstring(v57);
          if ( pSid )
          {
            LengthSid = GetLengthSid(pSid);
            std::vector<unsigned char>::_Insert_counted_range<unsigned char *>((__int64)v55, v55[0], pSid, LengthSid);
          }
          if ( packageFullName )
          {
            packageFamilyNameLength = 0;
            v26 = -1;
            v27 = -1;
            do
              ++v27;
            while ( packageFullName[v27] );
            std::wstring::_Assign<unsigned short>(v57, packageFullName, (char *)v27);
            packageFamilyNameLength = 128;
            if ( PackageFamilyNameFromFullName(packageFullName, &packageFamilyNameLength, packageFamilyName) )
            {
              do
                ++v26;
              while ( packageFullName[v26] );
              std::wstring::_Assign<unsigned short>(v56, packageFullName, (char *)v26);
            }
            else
            {
              do
                ++v26;
              while ( packageFamilyName[v26] );
              std::wstring::_Assign<unsigned short>(v56, packageFamilyName, (char *)v26);
            }
          }
          Broker::SebBroker::ValidateCreationParameters(
            (Broker::SebBroker *)v18.m128i_i64[0],
            (const struct _SebiSystemEventCreationParameter *)&v41,
            v33 == 2);
          if ( (_DWORD)v43 )
          {
            Broker::SebBroker::ValidateFilterParameters(v19, &v43);
          }
          else if ( *((_DWORD *)&Broker::EventPolicyTable + 2 * v20 + 6) )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, v19);
            v53 = 0;
            v54 = 4;
            v52 = &Broker::InvalidParameter::`vftable';
            throw (Broker::InvalidParameter *)&v52;
          }
          Broker::SebBroker::ConstructEventObject(
            v18.m128i_i64[0],
            (__int64 *)&v34,
            v55,
            (__int64)&v41,
            (__int64)&v43,
            (__int64)v39,
            v35);
          v43 = v41;
          v44 = v42;
          Broker::SebBroker::SetBrokerEventInfoFromCreationParameters(&v43, v36);
          *v37 = 1;
          v39 = operator new(0x10u);
          v28 = (__int64)v34;
          v34 = 0;
          v29 = std::shared_ptr<Broker::SebEvent>::shared_ptr<Broker::SebEvent>(v39, v28);
          *v38 = v29;
          packageFamilyNameLength = 0;
          if ( v34 )
            (**v34)(v34, 1);
          Broker::ApplicationIdentity::~ApplicationIdentity((Broker::ApplicationIdentity *)v55);
        }
        catch ( std::bad_alloc )
        {
          packageFamilyNameLength = 14;
        }
        catch ( Broker::ApplicationLimitsExceeded )
        {
          packageFamilyNameLength = 1816;
        }
        catch ( Broker::AccessDenied )
        {
          packageFamilyNameLength = 5;
        }
        catch ( Broker::BILayer::Failure *v46 )
        {
          packageFamilyNameLength = RtlNtStatusToDosError(*((_DWORD *)v46 + 8));
        }
        catch ( Broker::Win32Error *v47 )
        {
          packageFamilyNameLength = *((_DWORD *)v47 + 8);
        }
        catch ( Broker::InvalidParameter )
        {
          packageFamilyNameLength = 87;
        }
        catch ( Broker::MissingLockScreenCapability )
        {
          packageFamilyNameLength = 5;
        }
        catch ( Broker::BrokerCommonException *v48 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v31 = (*(__int64 (__fastcall **)(Broker::BrokerCommonException *))(*(_QWORD *)v48 + 8LL))(v48);
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, v31);
          }
          packageFamilyNameLength = 1359;
        }
        catch ( ... )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
          packageFamilyNameLength = 1359;
        }
      }
      else
      {
        packageFamilyNameLength = 5;
      }
    }
    else
    {
      packageFamilyNameLength = 21;
    }
  }
  else
  {
    packageFamilyNameLength = 87;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      123,
      &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids,
      packageFamilyNameLength);
  if ( v45[1] )
    std::_Ref_count_base::_Decref(v45[1]);
  return packageFamilyNameLength;
}

```

## disassembly

```asm
0x180010560  mov     [rsp+arg_0], rbx
0x180010565  mov     [rsp+arg_8], rsi
0x18001056a  push    rdi
0x18001056b  push    r12
0x18001056d  push    r13
0x18001056f  push    r14
0x180010571  push    r15
0x180010573  sub     rsp, 360h
0x18001057a  mov     rax, cs:__security_cookie
0x180010581  xor     rax, rsp
0x180010584  mov     [rsp+388h+var_38], rax
0x18001058c  mov     rbx, r9
0x18001058f  mov     rax, r8
0x180010592  mov     [rsp+388h+var_338], rax
0x180010597  mov     r12, rdx
0x18001059a  mov     [rsp+388h+var_318], rdx
0x18001059f  mov     [rsp+388h+var_344], ecx
0x1800105a3  mov     rdi, [rsp+388h+packageFullName]
0x1800105ab  mov     rsi, [rsp+388h+pSid]
0x1800105b3  mov     r9, [rsp+388h+arg_40]
0x1800105bb  mov     [rsp+388h+var_320], r9
0x1800105c0  mov     r8, [rsp+388h+arg_48]
0x1800105c8  mov     [rsp+388h+var_328], r8
0x1800105cd  mov     rdx, [rsp+388h+arg_50]
0x1800105d5  mov     [rsp+388h+var_330], rdx
0x1800105da  xor     r14d, r14d
0x1800105dd  mov     [rsp+388h+packageFamilyNameLength], r14d
0x1800105e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800105e9  test    byte ptr [rcx+1Ch], 1
0x1800105ed  jz      short loc_18001061E
0x1800105ef  cmp     byte ptr [rcx+19h], 4
0x1800105f3  jb      short loc_18001061E
0x1800105f5  mov     edx, 76h ; 'v'
0x1800105fa  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x180010601  mov     rcx, [rcx+10h]
0x180010605  call    WPP_SF_
0x18001060a  mov     rax, [rsp+388h+var_338]
0x18001060f  mov     rdx, [rsp+388h+var_330]
0x180010614  mov     r8, [rsp+388h+var_328]
0x180010619  mov     r9, [rsp+388h+var_320]
0x18001061e  xorps   xmm0, xmm0
0x180010621  movdqu  xmmword ptr [rsp+388h+var_2C8], xmm0
0x18001062a  xor     ecx, ecx
0x18001062c  movups  [rsp+388h+var_300], xmm0
0x180010634  mov     [rsp+388h+var_2F0], rcx
0x18001063c  movups  [rsp+388h+var_2E8], xmm0
0x180010644  test    r12, r12
0x180010647  jz      loc_180010B2E
0x18001064d  test    rax, rax
0x180010650  jz      loc_180010B2E
0x180010656  test    rbx, rbx
0x180010659  jz      loc_180010B2E
0x18001065f  test    r9, r9
0x180010662  jz      loc_180010B2E
0x180010668  test    rdx, rdx
0x18001066b  jz      loc_180010B2E
0x180010671  test    r8, r8
0x180010674  jz      loc_180010B2E
0x18001067a  mov     rax, qword ptr cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x180010681  test    rax, rax
0x180010684  jz      short loc_1800106A1
0x180010686  cmp     [rax], cl
0x180010688  jz      short loc_1800106A1
0x18001068a  mov     rax, qword ptr cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x180010691  test    rax, rax
0x180010694  jz      short loc_18001069A
0x180010696  lock inc dword ptr [rax+8]
0x18001069a  movups  xmm0, cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x1800106a1  movq    r15, xmm0
0x1800106a6  psrldq  xmm0, 8
0x1800106ab  mov     [rsp+388h+var_2C8], r15
0x1800106b3  movq    [rsp+388h+var_2C8+8], xmm0
0x1800106bc  test    r15, r15
0x1800106bf  jnz     short loc_1800106CE
0x1800106c1  mov     [rsp+388h+packageFamilyNameLength], 15h
0x1800106c9  jmp     loc_180010B36
0x1800106ce  cmp     [r15+88h], r12
0x1800106d5  jz      short loc_1800106E4
0x1800106d7  mov     [rsp+388h+packageFamilyNameLength], 5
0x1800106df  jmp     loc_180010B36
0x1800106e4  lea     r8, [rsp+388h+var_2E8]; struct _SebiSystemEventFilterParameter *
0x1800106ec  lea     rdx, [rsp+388h+var_300]; struct _SebiSystemEventCreationParameter *
0x1800106f4  mov     rcx, rbx; struct _BR_EVENT_PARAMETERS *
0x1800106f7  call    ?UnpackRpcParameters@SebBroker@Broker@@CAXPEAU_BR_EVENT_PARAMETERS@@AEAU_SebiSystemEventCreationParameter@@AEAU_SebiSystemEventFilterParameter@@@Z; Broker::SebBroker::UnpackRpcParameters(_BR_EVENT_PARAMETERS *,_SebiSystemEventCreationParameter &,_SebiSystemEventFilterParameter &)
0x1800106fc  movsxd  r12, dword ptr [rsp+388h+var_300+8]
0x180010704  lea     r13, [r12+r12*2]
0x180010708  add     r13, r13
0x18001070b  lea     rbx, ?EventPolicyTable@Broker@@3PAU_EventPolicy@1@A; Broker::_EventPolicy near * Broker::EventPolicyTable
0x180010712  mov     eax, [rbx+r13*8+4]
0x180010717  mov     dword ptr [rsp+388h+var_2F0+4], eax
0x18001071e  cmp     [rsp+388h+var_344], 1
0x180010723  jnz     loc_18001089C
0x180010729  lea     rcx, [rsp+388h+var_310]; this
0x18001072e  call    ??0RpcClientToken@Broker@@QEAA@XZ; Broker::RpcClientToken::RpcClientToken(void)
0x180010733  nop
0x180010734  lea     rcx, [rsp+388h+var_310]; this
0x180010739  call    ?IsAppContainer@RpcClientToken@Broker@@QEAA_NXZ; Broker::RpcClientToken::IsAppContainer(void)
0x18001073e  test    al, al
0x180010740  jz      loc_180010852
0x180010746  mov     edx, [rbx+r13*8+20h]; unsigned int
0x18001074b  cmp     edx, 0FFFFFFFFh
0x18001074e  jz      loc_180010852
0x180010754  xor     r8d, r8d; int
0x180010757  lea     rcx, [rsp+388h+var_310]; this
0x18001075c  call    ?CheckCapability@RpcClientToken@Broker@@QEAA_NKH@Z; Broker::RpcClientToken::CheckCapability(ulong,int)
0x180010761  test    al, al
0x180010763  jnz     loc_180010852
0x180010769  mov     rax, cs:WPP_GLOBAL_Control
0x180010770  test    byte ptr [rax+1Ch], 1
0x180010774  jz      short loc_1800107ED
0x180010776  cmp     byte ptr [rax+19h], 2
0x18001077a  jb      short loc_1800107ED
0x18001077c  xor     r9d, r9d
0x18001077f  xor     r8d, r8d
0x180010782  lea     rdx, [rsp+388h+var_198]
0x18001078a  lea     rcx, [rsp+388h+var_310]
0x18001078f  call    ?GetAppId@RpcClientToken@Broker@@QEAA?AUApplicationIdentity@2@PEBG_N@Z; Broker::RpcClientToken::GetAppId(ushort const *,bool)
0x180010794  nop
0x180010795  mov     [rsp+388h+packageFamilyNameLength], 1
0x18001079d  lea     rbx, [rax+38h]
0x1800107a1  cmp     qword ptr [rbx+18h], 7
0x1800107a6  jbe     short loc_1800107AB
0x1800107a8  mov     rbx, [rbx]
0x1800107ab  xor     r9d, r9d
0x1800107ae  xor     r8d, r8d
0x1800107b1  lea     rdx, [rsp+388h+var_1F8]
0x1800107b9  lea     rcx, [rsp+388h+var_310]
0x1800107be  call    ?GetAppId@RpcClientToken@Broker@@QEAA?AUApplicationIdentity@2@PEBG_N@Z; Broker::RpcClientToken::GetAppId(ushort const *,bool)
0x1800107c3  mov     edx, 77h ; 'w'
0x1800107c8  mov     r14d, 3
0x1800107ce  mov     [rsp+388h+var_368], rbx; __int64
0x1800107d3  mov     r9, [rax]
0x1800107d6  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x1800107dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800107e4  mov     rcx, [rcx+10h]; LoggerHandle
0x1800107e8  call    WPP_SF__sid_S
0x1800107ed  test    r14b, 2
0x1800107f1  jz      short loc_180010805
0x1800107f3  and     r14d, 0FFFFFFFDh
0x1800107f7  lea     rcx, [rsp+388h+var_1F8]; this
0x1800107ff  call    ??1ApplicationIdentity@Broker@@QEAA@XZ; Broker::ApplicationIdentity::~ApplicationIdentity(void)
0x180010804  nop
0x180010805  test    r14b, 1
0x180010809  jz      short loc_180010818
0x18001080b  lea     rcx, [rsp+388h+var_198]; this
0x180010813  call    ??1ApplicationIdentity@Broker@@QEAA@XZ; Broker::ApplicationIdentity::~ApplicationIdentity(void)
0x180010818  xorps   xmm0, xmm0
0x18001081b  movups  [rsp+388h+var_298], xmm0
0x180010823  mov     [rsp+388h+var_288], 5
0x18001082e  lea     rax, ??_7AccessDenied@Broker@@6B@; const Broker::AccessDenied::`vftable'
0x180010835  mov     [rsp+388h+pExceptionObject], rax
0x18001083d  lea     rdx, _TI3?AUAccessDenied@Broker@@; pThrowInfo
0x180010844  lea     rcx, [rsp+388h+pExceptionObject]; pExceptionObject
0x18001084c  call    _CxxThrowException_0
0x180010852  mov     rcx, [rsp+388h+hObject]; hObject
0x18001085a  call    cs:__imp_CloseHandle
0x180010860  test    eax, eax
0x180010862  jnz     short loc_18001089C
0x180010864  mov     rax, cs:WPP_GLOBAL_Control
0x18001086b  test    byte ptr [rax+1Ch], 8
0x18001086f  jz      short loc_18001089C
0x180010871  cmp     byte ptr [rax+19h], 2
0x180010875  jb      short loc_18001089C
0x180010877  call    cs:__imp_GetLastError
0x18001087d  mov     edx, 12h
0x180010882  mov     r9d, eax
0x180010885  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x18001088c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010893  mov     rcx, [rcx+10h]
0x180010897  call    WPP_SF_d
0x18001089c  lea     rcx, [rsp+388h+var_258]
0x1800108a4  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x1800108a9  nop
0x1800108aa  lea     rcx, [rsp+388h+var_240]
0x1800108b2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800108b7  nop
0x1800108b8  lea     rcx, [rsp+388h+var_220]
0x1800108c0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800108c5  nop
0x1800108c6  test    rsi, rsi
0x1800108c9  jz      short loc_1800108EF
0x1800108cb  mov     rcx, rsi; pSid
0x1800108ce  call    cs:__imp_GetLengthSid
0x1800108d4  mov     r9d, eax
0x1800108d7  mov     r8, rsi
0x1800108da  mov     rdx, [rsp+388h+var_258]
0x1800108e2  lea     rcx, [rsp+388h+var_258]
0x1800108ea  call    ??$_Insert_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEAE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,unsigned __int64)
0x1800108ef  xor     esi, esi
0x1800108f1  test    rdi, rdi
0x1800108f4  jz      loc_18001099A
0x1800108fa  mov     [rsp+388h+packageFamilyNameLength], esi
0x1800108fe  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180010905  mov     r8, rbx
0x180010908  nop     dword ptr [rax+rax+00000000h]
0x180010910  inc     r8
0x180010913  cmp     [rdi+r8*2], si
0x180010918  jnz     short loc_180010910
0x18001091a  mov     rdx, rdi
0x18001091d  lea     rcx, [rsp+388h+var_220]
0x180010925  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001092a  mov     [rsp+388h+packageFamilyNameLength], 80h
0x180010932  lea     r8, [rsp+388h+packageFamilyName]; packageFamilyName
0x18001093a  lea     rdx, [rsp+388h+packageFamilyNameLength]; packageFamilyNameLength
0x18001093f  mov     rcx, rdi; packageFullName
0x180010942  call    cs:__imp_PackageFamilyNameFromFullName
0x180010948  test    eax, eax
0x18001094a  jnz     short loc_180010977
0x18001094c  lea     rax, [rsp+388h+packageFamilyName]
0x180010954  inc     rbx
0x180010957  cmp     [rax+rbx*2], si
0x18001095b  jnz     short loc_180010954
0x18001095d  mov     r8, rbx
0x180010960  lea     rdx, [rsp+388h+packageFamilyName]
0x180010968  lea     rcx, [rsp+388h+var_240]
0x180010970  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180010975  jmp     short loc_180010993
0x180010977  inc     rbx
0x18001097a  cmp     [rdi+rbx*2], si
0x18001097e  jnz     short loc_180010977
0x180010980  mov     r8, rbx
0x180010983  mov     rdx, rdi
0x180010986  lea     rcx, [rsp+388h+var_240]
0x18001098e  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180010993  lea     rbx, ?EventPolicyTable@Broker@@3PAU_EventPolicy@1@A; Broker::_EventPolicy near * Broker::EventPolicyTable
0x18001099a  cmp     [rsp+388h+var_344], 2
0x18001099f  setz    r8b; bool
0x1800109a3  lea     rdx, [rsp+388h+var_300]; struct _SebiSystemEventCreationParameter *
0x1800109ab  mov     rcx, r15; this
0x1800109ae  call    ?ValidateCreationParameters@SebBroker@Broker@@AEAAXAEBU_SebiSystemEventCreationParameter@@_N@Z; Broker::SebBroker::ValidateCreationParameters(_SebiSystemEventCreationParameter const &,bool)
0x1800109b3  cmp     dword ptr [rsp+388h+var_2E8], 0
0x1800109bb  jz      loc_180010AAB
0x1800109c1  lea     rdx, [rsp+388h+var_2E8]
0x1800109c9  mov     ecx, r12d
0x1800109cc  call    ?ValidateFilterParameters@SebBroker@Broker@@CAXW4_SebiEventType@@PEBU_SebiSystemEventFilterParameter@@@Z; Broker::SebBroker::ValidateFilterParameters(_SebiEventType,_SebiSystemEventFilterParameter const *)
0x1800109d1  mov     rax, [rsp+388h+var_338]
0x1800109d6  mov     [rsp+388h+var_358], rax
0x1800109db  mov     rax, [rsp+388h+var_318]
0x1800109e0  mov     [rsp+388h+var_360], rax
0x1800109e5  lea     rax, [rsp+388h+var_2E8]
0x1800109ed  mov     [rsp+388h+var_368], rax
0x1800109f2  lea     r9, [rsp+388h+var_300]
0x1800109fa  lea     r8, [rsp+388h+var_258]
0x180010a02  lea     rdx, [rsp+388h+var_340]
0x180010a07  mov     rcx, r15
0x180010a0a  call    ?ConstructEventObject@SebBroker@Broker@@AEAA?AV?$unique_ptr@VSebEvent@Broker@@U?$default_delete@VSebEvent@Broker@@@std@@@std@@AEBUApplicationIdentity@2@AEBU_SebiSystemEventCreationParameter@@PEBU_SebiSystemEventFilterParameter@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@@Z; Broker::SebBroker::ConstructEventObject(Broker::ApplicationIdentity const &,_SebiSystemEventCreationParameter const &,_SebiSystemEventFilterParameter const *,_BROKER *,_BROKERED_EVENT *)
0x180010a0f  nop
0x180010a10  movups  xmm0, [rsp+388h+var_300]
0x180010a18  movaps  [rsp+388h+var_2E8], xmm0
0x180010a20  movsd   xmm1, [rsp+388h+var_2F0]
0x180010a29  movsd   [rsp+388h+var_2D8], xmm1
0x180010a32  mov     rdx, [rsp+388h+var_330]
0x180010a37  lea     rcx, [rsp+388h+var_2E8]
0x180010a3f  call    ?SetBrokerEventInfoFromCreationParameters@SebBroker@Broker@@CAXU_SebiSystemEventCreationParameter@@PEAU_BR_NEW_EVENT_INFORMATION@@@Z; Broker::SebBroker::SetBrokerEventInfoFromCreationParameters(_SebiSystemEventCreationParameter,_BR_NEW_EVENT_INFORMATION *)
0x180010a44  mov     rax, [rsp+388h+var_328]
0x180010a49  mov     dword ptr [rax], 1
0x180010a4f  mov     ecx, 10h; Size
0x180010a54  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010a59  mov     [rsp+388h+var_318], rax
0x180010a5e  mov     rdx, [rsp+388h+var_340]
0x180010a63  mov     [rsp+388h+var_340], rsi
0x180010a68  mov     rcx, rax
0x180010a6b  call    ??$?0VSebEvent@Broker@@$0A@@?$shared_ptr@VSebEvent@Broker@@@std@@QEAA@PEAVSebEvent@Broker@@@Z; std::shared_ptr<Broker::SebEvent>::shared_ptr<Broker::SebEvent>(Broker::SebEvent *)
0x180010a70  nop
0x180010a71  mov     rcx, [rsp+388h+var_320]
0x180010a76  mov     [rcx], rax
0x180010a79  mov     [rsp+388h+packageFamilyNameLength], esi
0x180010a7d  mov     rcx, [rsp+388h+var_340]
0x180010a82  test    rcx, rcx
0x180010a85  jz      short loc_180010A98
0x180010a87  mov     rax, [rcx]
0x180010a8a  mov     edx, 1
0x180010a8f  mov     rax, [rax]
0x180010a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a97  nop
0x180010a98  lea     rcx, [rsp+388h+var_258]; this
0x180010aa0  call    ??1ApplicationIdentity@Broker@@QEAA@XZ; Broker::ApplicationIdentity::~ApplicationIdentity(void)
0x180010aa5  nop
0x180010aa6  jmp     loc_180010B36
0x180010aab  cmp     dword ptr [rbx+r13*8+18h], 0
0x180010ab1  jz      loc_1800109D1
0x180010ab7  mov     rcx, cs:WPP_GLOBAL_Control
0x180010abe  test    byte ptr [rcx+1Ch], 1
0x180010ac2  jz      short loc_180010AE2
0x180010ac4  cmp     byte ptr [rcx+19h], 2
0x180010ac8  jb      short loc_180010AE2
0x180010aca  mov     edx, 78h ; 'x'
0x180010acf  mov     r9d, r12d
0x180010ad2  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x180010ad9  mov     rcx, [rcx+10h]
0x180010add  call    WPP_SF_d
0x180010ae2  xorps   xmm0, xmm0
0x180010ae5  movups  [rsp+388h+var_278], xmm0
0x180010aed  mov     [rsp+388h+var_268], 4
0x180010af8  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x180010aff  mov     [rsp+388h+var_280], rax
0x180010b07  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x180010b0e  lea     rcx, [rsp+388h+var_280]; pExceptionObject
0x180010b16  call    _CxxThrowException_0
0x180010b1c  jmp     short loc_180010B36
  ... truncated ...
```
