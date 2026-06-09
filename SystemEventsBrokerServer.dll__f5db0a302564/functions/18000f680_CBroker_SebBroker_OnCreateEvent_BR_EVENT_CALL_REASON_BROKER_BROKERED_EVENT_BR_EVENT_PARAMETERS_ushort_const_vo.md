# CBroker::SebBroker::OnCreateEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,_BR_EVENT_PARAMETERS *,ushort const *,void *,void *,void *,void * *,ulong *,_BR_NEW_EVENT_INFORMATION *)

- ea: `0x18000f680`
- end: `0x18000fb3b`
- name: `?OnCreateEvent@SebBroker@CBroker@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAU_BR_EVENT_PARAMETERS@@PEBGPEAX55PEAPEAXPEAKPEAU_BR_NEW_EVENT_INFORMATION@@@Z`
- size: `1211`
- prototype: `__int64 __fastcall(int, __int64 (__fastcall **)(_QWORD, __int64), __int64 (__fastcall **)(_QWORD, __int64), struct _BR_EVENT_PARAMETERS *, PCWSTR packageFullName, PSID pSid, __int64, __int64, CBroker::SebEvent **, _DWORD *, _DWORD *)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800030e0`
- `0x1800036f0`
- `0x180005a50`
- `0x1800076a0`
- `0x180007700`
- `0x180007c50`
- `0x18000b168`
- `0x18000beb4`
- `0x18000f370`
- `0x18000f680`
- `0x18000fb50`
- `0x18000fc10`
- `0x1800114f0`
- `0x18001ab34`
- `0x18001cf50`
- `0x18001d364`
- `0x18001e3bc`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000f78a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000f78a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000f79c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000f79c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000f8f4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000f8f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f790`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f790`
- `RPCRT4!RpcRevertToSelf` at `0x18000f890`
- `RPCRT4!RpcRevertToSelf` at `0x18000f890`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18000f962`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18000f962`

## pseudocode

```c
__int64 __fastcall CBroker::SebBroker::OnCreateEvent(
        int a1,
        __int64 (__fastcall **a2)(_QWORD, __int64),
        __int64 (__fastcall **a3)(_QWORD, __int64),
        struct _BR_EVENT_PARAMETERS *a4,
        PCWSTR packageFullName,
        PSID pSid,
        __int64 a7,
        __int64 a8,
        CBroker::SebEvent **a9,
        _DWORD *a10,
        _DWORD *a11)
{
  __int64 (__fastcall **v12)(_QWORD, __int64); // rax
  CBroker::SebEvent **v15; // r8
  _DWORD *v16; // rdx
  _QWORD *v17; // rcx
  CBroker::SebBroker *v18; // rbx
  char *v19; // rdi
  char v20; // bl
  __m128i v21; // xmm6
  std::_Ref_count_base *v22; // rcx
  std::_Ref_count_base *v23; // rcx
  __int64 v24; // rbx
  size_t LengthSid; // r9
  __int64 v26; // rbx
  __int64 v27; // r8
  char BIEventFlag; // al
  int v29; // ecx
  _DWORD *v30; // rbx
  CBroker::SebEvent *v31; // rax
  std::_Ref_count_base *v32; // rcx
  struct CBroker::_CustomData *v33; // rcx
  __int64 v35; // rax
  UINT32 packageFamilyNameLength; // [rsp+40h] [rbp-248h] BYREF
  char v37[4]; // [rsp+44h] [rbp-244h] BYREF
  struct CBroker::_CustomData *v38; // [rsp+48h] [rbp-240h] BYREF
  CBroker::SebEvent *v39; // [rsp+50h] [rbp-238h] BYREF
  __int64 (__fastcall **v40)(_QWORD, __int64); // [rsp+58h] [rbp-230h]
  _DWORD *v41; // [rsp+60h] [rbp-228h]
  CBroker::SebEvent **v42; // [rsp+68h] [rbp-220h]
  _DWORD *v43; // [rsp+70h] [rbp-218h]
  __m128i v44; // [rsp+78h] [rbp-210h]
  Broker::BILayer::Failure *v45; // [rsp+88h] [rbp-200h] BYREF
  Broker::Win32Error *v46; // [rsp+90h] [rbp-1F8h] BYREF
  Broker::BrokerCommonException *v47; // [rsp+98h] [rbp-1F0h] BYREF
  _OWORD v48[3]; // [rsp+A0h] [rbp-1E8h] BYREF
  __int64 v49; // [rsp+D0h] [rbp-1B8h]
  _BYTE *v50[3]; // [rsp+E0h] [rbp-1A8h] BYREF
  char *v51[4]; // [rsp+F8h] [rbp-190h] BYREF
  char *v52[5]; // [rsp+118h] [rbp-170h] BYREF
  WCHAR packageFamilyName[128]; // [rsp+140h] [rbp-148h] BYREF

  v12 = a3;
  v40 = a3;
  v43 = a11;
  v15 = a9;
  v42 = a9;
  v16 = a10;
  v41 = a10;
  v17 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids);
    v17 = WPP_GLOBAL_Control;
    v12 = v40;
    v16 = v41;
    v15 = v42;
  }
  v38 = 0;
  if ( a2 && v12 && a4 && v15 && a11 && v16 )
  {
    v18 = CBroker::SebBroker::Instance;
    if ( CBroker::SebBroker::Instance
      && (v19 = (char *)CBroker::SebBroker::Instance + 8,
          RtlAcquireSRWLockExclusive((char *)CBroker::SebBroker::Instance + 8),
          GetCurrentThreadId(),
          v20 = *(_BYTE *)v18,
          RtlReleaseSRWLockExclusive(v19),
          v20) )
    {
      if ( *(&CBroker::SebBroker::Instance + 1) )
        _InterlockedIncrement((volatile signed __int32 *)*(&CBroker::SebBroker::Instance + 1) + 2);
      v21 = *(__m128i *)&CBroker::SebBroker::Instance;
    }
    else
    {
      v21 = 0;
    }
    v44 = v21;
    memset(v48, 0, sizeof(v48));
    v49 = 0;
    if ( v21.m128i_i64[0] )
    {
      if ( *(__int64 (__fastcall ***)(_QWORD, __int64))(v21.m128i_i64[0] + 352) == a2 )
      {
        try
        {
          CBroker::SebBroker::UnpackRpcParameters(a4, (struct _CSebiSystemEventCreationParameter *)v48, &v38);
          CBroker::SebBroker::ValidateCreationParameters(
            (CBroker::SebBroker *)v21.m128i_i64[0],
            (const struct _CSebiSystemEventCreationParameter *)v48,
            v38);
          if ( a1 == 1 )
          {
            v24 = *(_QWORD *)&v48[0];
            Broker::RpcScopedImpersonation::RpcScopedImpersonation((Broker::RpcScopedImpersonation *)v37);
            ClientAccessCheck(v24);
            if ( RpcRevertToSelf() )
            {
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids);
            }
          }
          std::vector<_GUID>::vector<_GUID>(v50);
          std::wstring::wstring(v51);
          std::wstring::wstring(v52);
          if ( pSid )
          {
            LengthSid = GetLengthSid(pSid);
            std::vector<unsigned char>::_Insert_counted_range<unsigned char *>((__int64)v50, v50[0], pSid, LengthSid);
          }
          if ( packageFullName )
          {
            packageFamilyNameLength = 0;
            v26 = -1;
            v27 = -1;
            do
              ++v27;
            while ( packageFullName[v27] );
            std::wstring::_Assign<unsigned short>(v52, packageFullName, (char *)v27);
            packageFamilyNameLength = 128;
            if ( PackageFamilyNameFromFullName(packageFullName, &packageFamilyNameLength, packageFamilyName) )
            {
              do
                ++v26;
              while ( packageFullName[v26] );
              std::wstring::_Assign<unsigned short>(v51, packageFullName, (char *)v26);
            }
            else
            {
              do
                ++v26;
              while ( packageFamilyName[v26] );
              std::wstring::_Assign<unsigned short>(v51, packageFamilyName, (char *)v26);
            }
          }
          CBroker::SebBroker::ConstructEventObject(
            v21.m128i_i64[0],
            (__int64 *)&v39,
            v50,
            (__int64)v48,
            (__int64)v38,
            a2,
            v40);
          *v41 = 1;
          BIEventFlag = CBroker::SebEvent::GetBIEventFlag(v39);
          v29 = BIEventFlag & 1;
          if ( (BIEventFlag & 0x60) != 0 )
            v29 |= 2u;
          v30 = v43;
          v43[1] = v29;
          v30[2] = CBroker::SebEvent::GetBIEventFlag(v39);
          v31 = v39;
          *v30 = *((_DWORD *)v39 + 24) - 4096;
          v30[3] = *((_DWORD *)v31 + 56);
          v30[4] = *((_DWORD *)v31 + 57);
          v30[5] = *((_DWORD *)v31 + 58);
          v30[6] = *((_DWORD *)v31 + 59);
          v39 = 0;
          *v42 = v31;
          packageFamilyNameLength = 0;
          Broker::ApplicationIdentity::~ApplicationIdentity((Broker::ApplicationIdentity *)v50);
          v32 = (std::_Ref_count_base *)_mm_srli_si128(v21, 8).m128i_u64[0];
          if ( v32 )
            std::_Ref_count_base::_Decref(v32);
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
        catch ( Broker::BILayer::Failure *v45 )
        {
          packageFamilyNameLength = RtlNtStatusToDosError(*((_DWORD *)v45 + 8));
        }
        catch ( Broker::Win32Error *v46 )
        {
          packageFamilyNameLength = *((_DWORD *)v46 + 8);
        }
        catch ( Broker::InvalidParameter )
        {
          packageFamilyNameLength = 87;
        }
        catch ( Broker::MissingLockScreenCapability )
        {
          packageFamilyNameLength = 5;
        }
        catch ( Broker::BrokerCommonException *v47 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v35 = (*(__int64 (__fastcall **)(Broker::BrokerCommonException *))(*(_QWORD *)v47 + 8LL))(v47);
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids, v35);
          }
          packageFamilyNameLength = 1359;
        }
        catch ( ... )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids);
          packageFamilyNameLength = 1359;
        }
      }
      else
      {
        packageFamilyNameLength = 5;
        v23 = (std::_Ref_count_base *)_mm_srli_si128(v21, 8).m128i_u64[0];
        if ( v23 )
          std::_Ref_count_base::_Decref(v23);
      }
    }
    else
    {
      packageFamilyNameLength = 21;
      v22 = (std::_Ref_count_base *)_mm_srli_si128(v21, 8).m128i_u64[0];
      if ( v22 )
        std::_Ref_count_base::_Decref(v22);
    }
    v33 = v38;
    if ( v38 )
    {
      if ( *(_QWORD *)v38 )
      {
        operator delete(*(void **)v38);
        v33 = v38;
      }
      operator delete(v33);
    }
    v17 = WPP_GLOBAL_Control;
  }
  else
  {
    packageFamilyNameLength = 87;
  }
  if ( (*((_BYTE *)v17 + 28) & 8) != 0 && *((_BYTE *)v17 + 25) >= 4u )
    WPP_SF_d(v17[2], 49, &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids, packageFamilyNameLength);
  return packageFamilyNameLength;
}

```

## disassembly

```asm
0x18000f680  mov     [rsp+arg_0], rbx
0x18000f685  mov     [rsp+arg_8], rsi
0x18000f68a  push    rdi
0x18000f68b  push    r12
0x18000f68d  push    r13
0x18000f68f  push    r14
0x18000f691  push    r15
0x18000f693  sub     rsp, 260h
0x18000f69a  movaps  [rsp+288h+var_38], xmm6
0x18000f6a2  mov     rax, cs:__security_cookie
0x18000f6a9  xor     rax, rsp
0x18000f6ac  mov     [rsp+288h+var_48], rax
0x18000f6b4  mov     r14, r9
0x18000f6b7  mov     rax, r8
0x18000f6ba  mov     [rsp+288h+var_230], rax
0x18000f6bf  mov     r13, rdx
0x18000f6c2  mov     r15d, ecx
0x18000f6c5  mov     rbx, [rsp+288h+arg_50]
0x18000f6cd  mov     [rsp+288h+var_218], rbx
0x18000f6d2  mov     rsi, [rsp+288h+packageFullName]
0x18000f6da  mov     r12, [rsp+288h+pSid]
0x18000f6e2  mov     r8, [rsp+288h+arg_40]
0x18000f6ea  mov     [rsp+288h+var_220], r8
0x18000f6ef  mov     rdx, [rsp+288h+arg_48]
0x18000f6f7  mov     [rsp+288h+var_228], rdx
0x18000f6fc  xor     edi, edi
0x18000f6fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f705  test    byte ptr [rcx+1Ch], 8
0x18000f709  jz      short loc_18000F73C
0x18000f70b  cmp     byte ptr [rcx+19h], 4
0x18000f70f  jb      short loc_18000F73C
0x18000f711  mov     edx, 2Eh ; '.'
0x18000f716  lea     r8, WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids
0x18000f71d  mov     rcx, [rcx+10h]
0x18000f721  call    WPP_SF_
0x18000f726  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f72d  mov     rax, [rsp+288h+var_230]
0x18000f732  mov     rdx, [rsp+288h+var_228]
0x18000f737  mov     r8, [rsp+288h+var_220]
0x18000f73c  mov     [rsp+288h+var_240], rdi
0x18000f741  test    r13, r13
0x18000f744  jz      loc_18000FAD7
0x18000f74a  test    rax, rax
0x18000f74d  jz      loc_18000FAD7
0x18000f753  test    r14, r14
0x18000f756  jz      loc_18000FAD7
0x18000f75c  test    r8, r8
0x18000f75f  jz      loc_18000FAD7
0x18000f765  test    rbx, rbx
0x18000f768  jz      loc_18000FAD7
0x18000f76e  test    rdx, rdx
0x18000f771  jz      loc_18000FAD7
0x18000f777  mov     rbx, qword ptr cs:?Instance@SebBroker@CBroker@@0V?$shared_ptr@VSebBroker@CBroker@@@std@@A; std::shared_ptr<CBroker::SebBroker> CBroker::SebBroker::Instance
0x18000f77e  test    rbx, rbx
0x18000f781  jz      short loc_18000F7BF
0x18000f783  lea     rdi, [rbx+8]
0x18000f787  mov     rcx, rdi
0x18000f78a  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000f790  call    cs:__imp_GetCurrentThreadId
0x18000f796  movzx   ebx, byte ptr [rbx]
0x18000f799  mov     rcx, rdi
0x18000f79c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000f7a2  test    bl, bl
0x18000f7a4  jz      short loc_18000F7BF
0x18000f7a6  mov     rax, qword ptr cs:?Instance@SebBroker@CBroker@@0V?$shared_ptr@VSebBroker@CBroker@@@std@@A+8; std::shared_ptr<CBroker::SebBroker> CBroker::SebBroker::Instance
0x18000f7ad  test    rax, rax
0x18000f7b0  jz      short loc_18000F7B6
0x18000f7b2  lock inc dword ptr [rax+8]
0x18000f7b6  movups  xmm6, cs:?Instance@SebBroker@CBroker@@0V?$shared_ptr@VSebBroker@CBroker@@@std@@A; std::shared_ptr<CBroker::SebBroker> CBroker::SebBroker::Instance
0x18000f7bd  jmp     short loc_18000F7C2
0x18000f7bf  xorps   xmm6, xmm6
0x18000f7c2  movdqu  [rsp+288h+var_210], xmm6
0x18000f7c8  xorps   xmm0, xmm0
0x18000f7cb  xor     eax, eax
0x18000f7cd  movups  [rsp+288h+var_1E8], xmm0
0x18000f7d5  movups  [rsp+288h+var_1D8], xmm0
0x18000f7dd  movups  [rsp+288h+var_1C8], xmm0
0x18000f7e5  mov     [rsp+288h+var_1B8], rax
0x18000f7ed  movq    rdi, xmm6
0x18000f7f2  test    rdi, rdi
0x18000f7f5  jnz     short loc_18000F819
0x18000f7f7  mov     [rsp+288h+packageFamilyNameLength], 15h
0x18000f7ff  psrldq  xmm6, 8
0x18000f804  movq    rcx, xmm6; this
0x18000f809  test    rcx, rcx
0x18000f80c  jz      short loc_18000F814
0x18000f80e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000f813  nop
0x18000f814  jmp     loc_18000FAA5
0x18000f819  cmp     [rdi+160h], r13
0x18000f820  jz      short loc_18000F844
0x18000f822  mov     [rsp+288h+packageFamilyNameLength], 5
0x18000f82a  psrldq  xmm6, 8
0x18000f82f  movq    rcx, xmm6; this
0x18000f834  test    rcx, rcx
0x18000f837  jz      short loc_18000F83F
0x18000f839  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000f83e  nop
0x18000f83f  jmp     loc_18000FAA5
0x18000f844  lea     r8, [rsp+288h+var_240]; struct CBroker::_CustomData **
0x18000f849  lea     rdx, [rsp+288h+var_1E8]; struct _CSebiSystemEventCreationParameter *
0x18000f851  mov     rcx, r14; struct _BR_EVENT_PARAMETERS *
0x18000f854  call    ?UnpackRpcParameters@SebBroker@CBroker@@CAXPEAU_BR_EVENT_PARAMETERS@@AEAU_CSebiSystemEventCreationParameter@@PEAPEAU_CustomData@2@@Z; CBroker::SebBroker::UnpackRpcParameters(_BR_EVENT_PARAMETERS *,_CSebiSystemEventCreationParameter &,CBroker::_CustomData * *)
0x18000f859  mov     r8, [rsp+288h+var_240]; struct CBroker::_CustomData *
0x18000f85e  lea     rdx, [rsp+288h+var_1E8]; struct _CSebiSystemEventCreationParameter *
0x18000f866  mov     rcx, rdi; this
0x18000f869  call    ?ValidateCreationParameters@SebBroker@CBroker@@AEAAXAEBU_CSebiSystemEventCreationParameter@@PEBU_CustomData@2@@Z; CBroker::SebBroker::ValidateCreationParameters(_CSebiSystemEventCreationParameter const &,CBroker::_CustomData const *)
0x18000f86e  cmp     r15d, 1
0x18000f872  jnz     short loc_18000F8C2
0x18000f874  mov     rbx, qword ptr [rsp+288h+var_1E8]
0x18000f87c  lea     rcx, [rsp+288h+var_244]; this
0x18000f881  call    ??0RpcScopedImpersonation@Broker@@QEAA@XZ; Broker::RpcScopedImpersonation::RpcScopedImpersonation(void)
0x18000f886  nop
0x18000f887  mov     rcx, rbx
0x18000f88a  call    ClientAccessCheck
0x18000f88f  nop
0x18000f890  call    cs:__imp_RpcRevertToSelf
0x18000f896  test    eax, eax
0x18000f898  jz      short loc_18000F8C2
0x18000f89a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f8a1  test    byte ptr [rcx+1Ch], 8
0x18000f8a5  jz      short loc_18000F8C2
0x18000f8a7  cmp     byte ptr [rcx+19h], 2
0x18000f8ab  jb      short loc_18000F8C2
0x18000f8ad  mov     edx, 0Bh
0x18000f8b2  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x18000f8b9  mov     rcx, [rcx+10h]
0x18000f8bd  call    WPP_SF_
0x18000f8c2  lea     rcx, [rsp+288h+var_1A8]
0x18000f8ca  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x18000f8cf  nop
0x18000f8d0  lea     rcx, [rsp+288h+var_190]
0x18000f8d8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000f8dd  nop
0x18000f8de  lea     rcx, [rsp+288h+var_170]
0x18000f8e6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000f8eb  nop
0x18000f8ec  test    r12, r12
0x18000f8ef  jz      short loc_18000F915
0x18000f8f1  mov     rcx, r12; pSid
0x18000f8f4  call    cs:__imp_GetLengthSid
0x18000f8fa  mov     r9d, eax
0x18000f8fd  mov     r8, r12
0x18000f900  mov     rdx, [rsp+288h+var_1A8]
0x18000f908  lea     rcx, [rsp+288h+var_1A8]
0x18000f910  call    ??$_Insert_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEAE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,unsigned __int64)
0x18000f915  xor     r14d, r14d
0x18000f918  test    rsi, rsi
0x18000f91b  jz      loc_18000F9BE
0x18000f921  mov     [rsp+288h+packageFamilyNameLength], r14d
0x18000f926  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000f92d  mov     r8, rbx
0x18000f930  inc     r8
0x18000f933  cmp     [rsi+r8*2], r14w
0x18000f938  jnz     short loc_18000F930
0x18000f93a  mov     rdx, rsi
0x18000f93d  lea     rcx, [rsp+288h+var_170]
0x18000f945  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18000f94a  mov     [rsp+288h+packageFamilyNameLength], 80h
0x18000f952  lea     r8, [rsp+288h+packageFamilyName]; packageFamilyName
0x18000f95a  lea     rdx, [rsp+288h+packageFamilyNameLength]; packageFamilyNameLength
0x18000f95f  mov     rcx, rsi; packageFullName
0x18000f962  call    cs:__imp_PackageFamilyNameFromFullName
0x18000f968  test    eax, eax
0x18000f96a  jnz     short loc_18000F9A0
0x18000f96c  lea     rax, [rsp+288h+packageFamilyName]
0x18000f974  inc     rbx
0x18000f977  cmp     [rax+rbx*2], r14w
0x18000f97c  jnz     short loc_18000F974
0x18000f97e  mov     r8, rbx
0x18000f981  lea     rdx, [rsp+288h+packageFamilyName]
0x18000f989  lea     rcx, [rsp+288h+var_190]
0x18000f991  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18000f996  jmp     short loc_18000F9BE
0x18000f9a0  inc     rbx
0x18000f9a3  cmp     [rsi+rbx*2], r14w
0x18000f9a8  jnz     short loc_18000F9A0
0x18000f9aa  mov     r8, rbx
0x18000f9ad  mov     rdx, rsi
0x18000f9b0  lea     rcx, [rsp+288h+var_190]
0x18000f9b8  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18000f9bd  nop
0x18000f9be  mov     rax, [rsp+288h+var_230]
0x18000f9c3  mov     [rsp+288h+var_258], rax
0x18000f9c8  mov     [rsp+288h+var_260], r13
0x18000f9cd  mov     rax, [rsp+288h+var_240]
0x18000f9d2  mov     [rsp+288h+var_268], rax
0x18000f9d7  lea     r9, [rsp+288h+var_1E8]
0x18000f9df  lea     r8, [rsp+288h+var_1A8]
0x18000f9e7  lea     rdx, [rsp+288h+var_238]
0x18000f9ec  mov     rcx, rdi
0x18000f9ef  call    ?ConstructEventObject@SebBroker@CBroker@@AEAA?AV?$unique_ptr@VSebEvent@CBroker@@U?$default_delete@VSebEvent@CBroker@@@std@@@std@@AEBUApplicationIdentity@Broker@@AEBU_CSebiSystemEventCreationParameter@@PEBU_CustomData@2@PEAU_BROKER@@PEAU_BROKERED_EVENT@@@Z; CBroker::SebBroker::ConstructEventObject(Broker::ApplicationIdentity const &,_CSebiSystemEventCreationParameter const &,CBroker::_CustomData const *,_BROKER *,_BROKERED_EVENT *)
0x18000f9f4  mov     rax, [rsp+288h+var_228]
0x18000f9f9  mov     dword ptr [rax], 1
0x18000f9ff  mov     rcx, [rsp+288h+var_238]; this
0x18000fa04  call    ?GetBIEventFlag@SebEvent@CBroker@@QEAAKXZ; CBroker::SebEvent::GetBIEventFlag(void)
0x18000fa09  mov     ecx, eax
0x18000fa0b  and     ecx, 1
0x18000fa0e  test    al, 60h
0x18000fa10  jz      short loc_18000FA15
0x18000fa12  or      ecx, 2
0x18000fa15  mov     rbx, [rsp+288h+var_218]
0x18000fa1a  mov     [rbx+4], ecx
0x18000fa1d  mov     rcx, [rsp+288h+var_238]; this
0x18000fa22  call    ?GetBIEventFlag@SebEvent@CBroker@@QEAAKXZ; CBroker::SebEvent::GetBIEventFlag(void)
0x18000fa27  mov     [rbx+8], eax
0x18000fa2a  mov     rax, [rsp+288h+var_238]
0x18000fa2f  mov     ecx, [rax+60h]
0x18000fa32  sub     ecx, 1000h
0x18000fa38  mov     [rbx], ecx
0x18000fa3a  mov     ecx, [rax+0E0h]
0x18000fa40  mov     [rbx+0Ch], ecx
0x18000fa43  mov     ecx, [rax+0E4h]
0x18000fa49  mov     [rbx+10h], ecx
0x18000fa4c  mov     ecx, [rax+0E8h]
0x18000fa52  mov     [rbx+14h], ecx
0x18000fa55  mov     ecx, [rax+0ECh]
0x18000fa5b  mov     [rbx+18h], ecx
0x18000fa5e  mov     [rsp+288h+var_238], r14
0x18000fa63  mov     rcx, [rsp+288h+var_220]
0x18000fa68  mov     [rcx], rax
0x18000fa6b  mov     [rsp+288h+packageFamilyNameLength], r14d
0x18000fa70  lea     rcx, [rsp+288h+var_1A8]; this
0x18000fa78  call    ??1ApplicationIdentity@Broker@@QEAA@XZ; Broker::ApplicationIdentity::~ApplicationIdentity(void)
0x18000fa7d  nop
0x18000fa7e  psrldq  xmm6, 8
0x18000fa83  movq    rcx, xmm6; this
0x18000fa88  test    rcx, rcx
0x18000fa8b  jz      short loc_18000FA93
0x18000fa8d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000fa92  nop
0x18000fa93  jmp     short loc_18000FAA5
0x18000fa95  jmp     short loc_18000FAA5
0x18000fa97  jmp     short loc_18000FAA5
0x18000fa99  jmp     short loc_18000FAA5
0x18000fa9b  jmp     short loc_18000FAA5
0x18000fa9d  jmp     short loc_18000FAA5
0x18000fa9f  jmp     short loc_18000FAA5
0x18000faa1  jmp     short loc_18000FAA5
0x18000faa3  jmp     short $+2
0x18000faa5  mov     rcx, [rsp+288h+var_240]
0x18000faaa  test    rcx, rcx
0x18000faad  jz      short loc_18000FACE
0x18000faaf  mov     rax, [rcx]
0x18000fab2  test    rax, rax
0x18000fab5  jz      short loc_18000FAC4
0x18000fab7  mov     rcx, rax; void *
0x18000faba  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000fabf  mov     rcx, [rsp+288h+var_240]; void *
0x18000fac4  mov     edx, 10h; unsigned __int64
0x18000fac9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000face  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fad5  jmp     short loc_18000FADF
0x18000fad7  mov     [rsp+288h+packageFamilyNameLength], 57h ; 'W'
0x18000fadf  test    byte ptr [rcx+1Ch], 8
0x18000fae3  jz      short loc_18000FB05
0x18000fae5  cmp     byte ptr [rcx+19h], 4
0x18000fae9  jb      short loc_18000FB05
0x18000faeb  mov     edx, 31h ; '1'
0x18000faf0  mov     r9d, [rsp+288h+packageFamilyNameLength]
0x18000faf5  lea     r8, WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids
0x18000fafc  mov     rcx, [rcx+10h]
0x18000fb00  call    WPP_SF_d
0x18000fb05  mov     eax, [rsp+288h+packageFamilyNameLength]
0x18000fb09  mov     rcx, [rsp+288h+var_48]
0x18000fb11  xor     rcx, rsp; StackCookie
0x18000fb14  call    __security_check_cookie
0x18000fb19  lea     r11, [rsp+288h+var_28]
0x18000fb21  mov     rbx, [r11+30h]
0x18000fb25  mov     rsi, [r11+38h]
0x18000fb29  movaps  xmm6, xmmword ptr [r11-10h]
0x18000fb2e  mov     rsp, r11
0x18000fb31  pop     r15
0x18000fb33  pop     r14
0x18000fb35  pop     r13
0x18000fb37  pop     r12
0x18000fb39  pop     rdi
0x18000fb3a  retn
```
