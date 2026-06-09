# Broker::TimeBroker::OnCreateEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,_BR_EVENT_PARAMETERS *,ushort const *,void *,void *,void *,void * *,ulong *,_BR_NEW_EVENT_INFORMATION *)

- ea: `0x18000ef50`
- end: `0x18000f6e5`
- name: `?OnCreateEvent@TimeBroker@Broker@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAU_BR_EVENT_PARAMETERS@@PEBGPEAX55PEAPEAXPEAKPEAU_BR_NEW_EVENT_INFORMATION@@@Z`
- size: `1941`
- prototype: `__int64 __fastcall(int, struct _BROKER *, __int64, struct _BR_EVENT_PARAMETERS *, _DWORD *, __int64, __int64, __int64, _QWORD *, _DWORD *, __int64)`
- caller_count: `0`
- callee_count: `29`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800010e8`
- `0x180002500`
- `0x180003800`
- `0x180003840`
- `0x180004000`
- `0x180004218`
- `0x1800042b8`
- `0x1800042e8`
- `0x180004e18`
- `0x180005b30`
- `0x18000a698`
- `0x18000aa90`
- `0x18000bd30`
- `0x18000c580`
- `0x18000c630`
- `0x18000c69c`
- `0x18000d388`
- `0x18000ee60`
- `0x18000ef50`
- `0x180011390`
- `0x180011858`
- `0x1800118ac`
- `0x180012dd0`
- `0x180012df4`
- `0x1800131e4`
- `0x18001396c`
- `0x180013978`
- `0x180015994`
- `0x180016740`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000f52e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000f52e`

## pseudocode

```c
__int64 __fastcall Broker::TimeBroker::OnCreateEvent(
        int a1,
        struct _BROKER *a2,
        __int64 a3,
        struct _BR_EVENT_PARAMETERS *a4,
        _DWORD *a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        _QWORD *a9,
        _DWORD *a10,
        __int64 a11)
{
  _QWORD *v13; // rsi
  char v14; // bl
  _BYTE *v15; // rdx
  __int64 Instance; // rax
  Broker::TimeBroker *v17; // r14
  unsigned int v18; // edi
  bool v19; // r15
  DWORD v20; // eax
  int v21; // r8d
  unsigned int v22; // esi
  Broker::TimeBroker *v23; // rcx
  bool v24; // r9
  int v25; // r9d
  char v26; // r8
  int v27; // eax
  int v28; // eax
  _BYTE *v29; // rdx
  int v30; // r8d
  __int64 v31; // rax
  __int64 v32; // rax
  unsigned int v33; // ecx
  int v34; // r8d
  int v35; // r9d
  Broker::ApplicationIdentity *AppId; // rax
  const unsigned __int16 *PackageFullNameStr; // rdi
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // r8
  _BYTE v42[32]; // [rsp+0h] [rbp-308h] BYREF
  bool IsAppContainer; // [rsp+60h] [rbp-2A8h]
  ULONG v44; // [rsp+64h] [rbp-2A4h] BYREF
  struct _FILETIME FileTime; // [rsp+68h] [rbp-2A0h] BYREF
  int v46[2]; // [rsp+70h] [rbp-298h] BYREF
  struct _FILETIME v47; // [rsp+78h] [rbp-290h] BYREF
  std::_Ref_count_base *v48; // [rsp+80h] [rbp-288h]
  _QWORD *v49; // [rsp+88h] [rbp-280h] BYREF
  _DWORD *v50; // [rsp+90h] [rbp-278h] BYREF
  __int64 v51; // [rsp+98h] [rbp-270h] BYREF
  __int64 v52; // [rsp+A0h] [rbp-268h] BYREF
  __int64 v53; // [rsp+A8h] [rbp-260h] BYREF
  Broker::TimeBroker *v54[2]; // [rsp+B0h] [rbp-258h] BYREF
  Broker::BILayer::Failure *v55; // [rsp+C0h] [rbp-248h] BYREF
  Broker::Win32Error *v56; // [rsp+C8h] [rbp-240h] BYREF
  Broker::BrokerCommonException *v57; // [rsp+D0h] [rbp-238h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+D8h] [rbp-230h] BYREF
  int v59; // [rsp+100h] [rbp-208h] BYREF
  SYSTEMTIME SystemTime; // [rsp+108h] [rbp-200h] BYREF
  unsigned int v61; // [rsp+118h] [rbp-1F0h]
  int v62; // [rsp+120h] [rbp-1E8h]
  char v63; // [rsp+135h] [rbp-1D3h]
  int v64; // [rsp+138h] [rbp-1D0h]
  void *v65; // [rsp+140h] [rbp-1C8h]
  int v66; // [rsp+15Ch] [rbp-1ACh]
  int v67; // [rsp+164h] [rbp-1A4h]
  int v68; // [rsp+168h] [rbp-1A0h]
  int v69; // [rsp+16Ch] [rbp-19Ch]
  int v70; // [rsp+170h] [rbp-198h]
  _BYTE v71[96]; // [rsp+200h] [rbp-108h] BYREF
  _BYTE v72[96]; // [rsp+260h] [rbp-A8h] BYREF

  v13 = a9;
  v49 = a9;
  v50 = a10;
  v14 = 0;
  v44 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
  IsAppContainer = 0;
  *(_OWORD *)v54 = 0;
  memset_0(&v59, 0, 0xF8u);
  FileTime.dwLowDateTime = 8;
  if ( !a2 || !a3 || !a4 || !a9 || !a11 || !a10 )
  {
    v18 = 87;
    goto LABEL_132;
  }
  *(_OWORD *)a11 = 0;
  *(_OWORD *)(a11 + 16) = 0;
  Instance = Broker::TimeBroker::GetInstance(&v47);
  std::shared_ptr<Broker::SystemTimer>::operator=(v54, Instance);
  if ( v48 )
    std::_Ref_count_base::_Decref(v48);
  *a9 = 0;
  v17 = v54[0];
  if ( !v54[0] )
  {
    v18 = 21;
    goto LABEL_132;
  }
  v19 = 0;
  if ( *((struct _BROKER **)v54[0] + 24) != a2 )
  {
    v18 = 5;
    goto LABEL_132;
  }
  try
  {
    Broker::TimeBroker::UnpackRpcParameters(a4, (struct _TbiTimeEventCreationParameters *)&v59);
    v20 = v59;
    FileTime.dwLowDateTime = v59;
    if ( v59 == 2 )
    {
      if ( (v62 & 2) != 0 )
      {
        FileTime.dwLowDateTime = 6;
      }
      else
      {
        if ( (v62 & 4) != 0 )
          v20 = 7;
        FileTime.dwLowDateTime = v20;
      }
    }
    if ( a1 != 1 )
    {
      v23 = v17;
      IsAppContainer = 0;
      v19 = 0;
      v24 = 1;
      if ( a1 == 2 )
        goto LABEL_36;
      goto LABEL_35;
    }
    Broker::RpcClientToken::RpcClientToken((Broker::RpcClientToken *)&v47);
    IsAppContainer = Broker::RpcClientToken::IsAppContainer((Broker::RpcClientToken *)&v47);
    if ( !IsAppContainer )
    {
LABEL_33:
      Broker::RpcClientToken::~RpcClientToken((Broker::RpcClientToken *)&v47);
      v23 = v17;
LABEL_35:
      v24 = 0;
LABEL_36:
      Broker::TimeBroker::ValidateCreationParameters(
        v23,
        (const struct _TbiTimeEventCreationParameters *)&v59,
        IsAppContainer,
        v24);
      LOBYTE(v25) = v19;
      Broker::TimeBroker::ConstructEventObject((int)v17, (int)v46, (int)&v59, v25, a2, (struct _BROKERED_EVENT *)a3);
      if ( (v59 || v61) && (v59 != 1 || v61) )
      {
        v26 = v62;
        if ( (v59 != 2 || (v62 & 1) == 0) && (v59 != 3 || *(_DWORD *)&SystemTime.wYear) && (v59 != 4 || v61) )
        {
          v27 = 0;
          if ( v59 != 5 )
          {
LABEL_50:
            if ( !v59 )
            {
              if ( !v64 )
                v27 |= 0x200u;
              if ( !v66 )
                goto LABEL_65;
              v27 |= 0x10000000u;
            }
            if ( v59 == 2 )
            {
              if ( !v64 )
                v27 |= 0x200u;
              if ( (v26 & 2) != 0 )
                v27 |= 0x100u;
              if ( (v26 & 8) == 0 )
                goto LABEL_65;
              v27 |= 0x400000u;
            }
            if ( v59 == 3 )
            {
              v28 = v27 | 0x408A;
              goto LABEL_66;
            }
LABEL_65:
            v28 = v27 | 0x400;
LABEL_66:
            *(_DWORD *)(a11 + 8) = v28;
            *v50 = 1;
            *(_DWORD *)a11 = FileTime.dwLowDateTime;
            *(_DWORD *)(a11 + 16) = v68;
            *(_DWORD *)(a11 + 12) = v67;
            *(_DWORD *)(a11 + 20) = v69;
            *(_DWORD *)(a11 + 24) = v70;
            v47 = (struct _FILETIME)operator new(0x10u);
            v29 = *(_BYTE **)v46;
            *(_QWORD *)v46 = 0;
            *v13 = ((__int64 (__fastcall *)(_QWORD, _QWORD))std::shared_ptr<Broker::TimeEvent>::shared_ptr<Broker::TimeEvent>)(
                     v47,
                     v29);
            v18 = 0;
            v15 = *(_BYTE **)v46;
            if ( *(_QWORD *)v46 )
              std::default_delete<Broker::TimeEvent>::operator()();
            goto LABEL_132;
          }
          if ( v61 )
          {
            v27 = 0;
            goto LABEL_65;
          }
        }
      }
      else
      {
        v26 = v62;
      }
      v27 = 4;
      goto LABEL_50;
    }
    if ( v59 == 3 )
    {
      v22 = 2;
      v19 = Broker::RpcClientToken::CheckCapability((Broker::RpcClientToken *)&v47, 0x20u, v21);
LABEL_31:
      if ( !Broker::RpcClientToken::CheckCapability((Broker::RpcClientToken *)&v47, v22, v21) )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          AppId = (Broker::ApplicationIdentity *)Broker::RpcClientToken::GetAppId(&v47, v72, 0);
          v44 = 1;
          PackageFullNameStr = Broker::ApplicationIdentity::GetPackageFullNameStr(AppId);
          v39 = Broker::RpcClientToken::GetAppId(&v47, v71, 0);
          v14 = 3;
          std::vector<unsigned char>::data(v39);
          WPP_SF__sid_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)PackageFullNameStr, v22);
        }
        if ( (v14 & 2) != 0 )
        {
          v14 &= ~2u;
          Broker::ApplicationIdentity::~ApplicationIdentity((Broker::ApplicationIdentity *)v71);
        }
        if ( (v14 & 1) != 0 )
          Broker::ApplicationIdentity::~ApplicationIdentity((Broker::ApplicationIdentity *)v72);
        Broker::AccessDenied::AccessDenied((Broker::AccessDenied *)pExceptionObject);
        throw (Broker::AccessDenied *)pExceptionObject;
      }
      v13 = v49;
      goto LABEL_33;
    }
    if ( v59 == 2 )
    {
      if ( (v62 & 2) != 0 )
      {
        v22 = 12;
        goto LABEL_31;
      }
      v22 = 0x10000;
      if ( (v62 & 8) != 0 )
        goto LABEL_31;
    }
    v22 = 8;
    goto LABEL_31;
  }
  catch ( std::bad_alloc )
  {
    v15 = v42;
    v44 = 14;
    v18 = 14;
  }
  catch ( Broker::ApplicationLimitsExceeded )
  {
    v15 = v42;
    v44 = 1816;
    v18 = 1816;
  }
  catch ( Broker::AccessDenied )
  {
    v15 = v42;
    v44 = 5;
    v18 = 5;
  }
  catch ( Broker::BILayer::Failure *v55 )
  {
    v44 = RtlNtStatusToDosError(*((_DWORD *)v55 + 8));
    v18 = v44;
  }
  catch ( Broker::Win32Error *v56 )
  {
    v15 = v42;
    v44 = *((_DWORD *)v56 + 8);
    v18 = v44;
  }
  catch ( Broker::InvalidParameter )
  {
    v15 = v42;
    v44 = 87;
    v18 = 87;
  }
  catch ( Broker::MissingLockScreenCapability )
  {
    v15 = v42;
    v44 = 5;
    v18 = 5;
  }
  catch ( Broker::BrokerCommonException *v57 )
  {
    v15 = v42;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v40 = (*(__int64 (__fastcall **)(Broker::BrokerCommonException *))(*(_QWORD *)v57 + 8LL))(v57);
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, v41, v40);
    }
    v44 = 1359;
    v18 = 1359;
  }
  catch ( ... )
  {
    v15 = v42;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
    v44 = 1359;
    v18 = 1359;
  }
LABEL_132:
  if ( v65 )
    operator delete(v65, (unsigned __int64)v15);
  if ( a1 != 2 )
  {
    if ( (unsigned int)dword_180026058 <= 5 || !(unsigned __int8)tlgKeywordOn(&dword_180026058, 0x400000000000LL) )
      goto LABEL_108;
    v44 = IsAppContainer;
    v50 = a5;
    v46[0] = v18;
    v49 = 0;
    if ( (unsigned int)v59 < 2 )
      goto LABEL_79;
    if ( v59 != 2 )
    {
      if ( v59 == 3 )
      {
LABEL_80:
        v31 = 1;
        goto LABEL_82;
      }
      if ( (unsigned int)(v59 - 4) <= 1 )
      {
LABEL_79:
        if ( v63 )
          goto LABEL_80;
      }
    }
    v31 = 0;
LABEL_82:
    v53 = v31;
    if ( v59 )
    {
      switch ( v59 )
      {
        case 1:
          v33 = v61;
          v32 = 86400 * v61;
          goto LABEL_93;
        case 2:
          v33 = v61;
          v32 = 60 * v61;
          goto LABEL_93;
        case 3:
          v32 = *(unsigned int *)&SystemTime.wYear;
          goto LABEL_89;
      }
      if ( (unsigned int)(v59 - 4) >= 2 )
      {
        v32 = 0;
LABEL_89:
        v33 = v61;
LABEL_93:
        v51 = v32;
        if ( v59 )
        {
          switch ( v59 )
          {
            case 1:
              v33 *= 86400;
              break;
            case 2:
              v33 *= 60;
              break;
            case 3:
              v33 = *(_DWORD *)&SystemTime.wYear;
              break;
            default:
              if ( (unsigned int)(v59 - 4) >= 2 )
                v33 = 0;
              break;
          }
        }
        v52 = v33;
        v47 = (struct _FILETIME)1LL;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v33,
          (unsigned int)&word_180020766,
          v30,
          (unsigned int)&v47,
          (__int64)&v52,
          (__int64)&v51,
          (__int64)&v53,
          (__int64)&v49,
          (__int64)v46,
          (__int64)&v50,
          (__int64)&FileTime,
          (__int64)&v44);
        goto LABEL_108;
      }
    }
    v33 = v61;
    v32 = v61;
    goto LABEL_93;
  }
  if ( !v59 )
  {
    if ( v18 )
    {
      FileTime = 0;
      SystemTimeToFileTime(&SystemTime, &FileTime);
      if ( (unsigned int)dword_180026058 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_180026058, 0x400000000000LL) )
        {
          v46[0] = v18;
          v47 = FileTime;
          v52 = *(_QWORD *)(a3 + 24);
          v51 = a3;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
            a3,
            (unsigned int)word_18002089A,
            v34,
            v35,
            (__int64)&v51,
            (__int64)&v52,
            (__int64)&v47,
            (__int64)v46);
        }
      }
    }
  }
LABEL_108:
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v18);
  if ( v54[1] )
    std::_Ref_count_base::_Decref(v54[1]);
  return v18;
}

```

## disassembly

```asm
0x18000ef50  mov     [rsp+arg_10], r8
0x18000ef55  mov     [rsp+arg_0], ecx
0x18000ef59  push    rbx
0x18000ef5a  push    rsi
0x18000ef5b  push    rdi
0x18000ef5c  push    r12
0x18000ef5e  push    r13
0x18000ef60  push    r14
0x18000ef62  push    r15
0x18000ef64  sub     rsp, 2D0h
0x18000ef6b  mov     rax, cs:__security_cookie
0x18000ef72  xor     rax, rsp
0x18000ef75  mov     [rsp+308h+var_48], rax
0x18000ef7d  mov     rdi, r9
0x18000ef80  mov     r12, rdx
0x18000ef83  mov     rsi, [rsp+308h+arg_40]
0x18000ef8b  mov     [rsp+308h+var_280], rsi
0x18000ef93  mov     r14, [rsp+308h+arg_48]
0x18000ef9b  mov     [rsp+308h+var_278], r14
0x18000efa3  mov     r13, [rsp+308h+arg_50]
0x18000efab  xor     ebx, ebx
0x18000efad  mov     [rsp+308h+var_2A4], ebx
0x18000efb1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000efb8  test    byte ptr [rcx+1Ch], 1
0x18000efbc  jz      short loc_18000EFD7
0x18000efbe  cmp     byte ptr [rcx+19h], 4
0x18000efc2  jb      short loc_18000EFD7
0x18000efc4  lea     edx, [rbx+63h]
0x18000efc7  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x18000efce  mov     rcx, [rcx+10h]
0x18000efd2  call    WPP_SF_
0x18000efd7  mov     [rsp+308h+var_2A8], bl
0x18000efdb  xorps   xmm0, xmm0
0x18000efde  movdqu  xmmword ptr [rsp+308h+var_258], xmm0
0x18000efe7  xor     edx, edx; Val
0x18000efe9  mov     r8d, 0F8h; Size
0x18000efef  lea     rcx, [rsp+308h+var_208]; void *
0x18000eff7  call    memset_0
0x18000effc  mov     [rsp+308h+FileTime.dwLowDateTime], 8
0x18000f004  test    r12, r12
0x18000f007  jz      loc_18000F328
0x18000f00d  cmp     [rsp+308h+arg_10], rbx
0x18000f015  jz      loc_18000F328
0x18000f01b  test    rdi, rdi
0x18000f01e  jz      loc_18000F328
0x18000f024  test    rsi, rsi
0x18000f027  jz      loc_18000F328
0x18000f02d  test    r13, r13
0x18000f030  jz      loc_18000F328
0x18000f036  test    r14, r14
0x18000f039  jz      loc_18000F328
0x18000f03f  xorps   xmm0, xmm0
0x18000f042  movups  xmmword ptr [r13+0], xmm0
0x18000f047  movups  xmmword ptr [r13+10h], xmm0
0x18000f04c  lea     rcx, [rsp+308h+var_290]
0x18000f051  call    ?GetInstance@TimeBroker@Broker@@SA?AV?$shared_ptr@VTimeBroker@Broker@@@std@@XZ; Broker::TimeBroker::GetInstance(void)
0x18000f056  mov     rdx, rax
0x18000f059  lea     rcx, [rsp+308h+var_258]
0x18000f061  call    ??4?$shared_ptr@VSystemTimer@Broker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Broker::SystemTimer>::operator=(std::shared_ptr<Broker::SystemTimer> &&)
0x18000f066  mov     rcx, [rsp+308h+var_288]; this
0x18000f06e  test    rcx, rcx
0x18000f071  jz      short loc_18000F078
0x18000f073  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000f078  mov     [rsi], rbx
0x18000f07b  mov     r14, [rsp+308h+var_258]
0x18000f083  test    r14, r14
0x18000f086  jnz     short loc_18000F091
0x18000f088  lea     edi, [r14+15h]
0x18000f08c  jmp     loc_18000F32D
0x18000f091  mov     r15b, bl
0x18000f094  cmp     [r14+0C0h], r12
0x18000f09b  jz      short loc_18000F0A7
0x18000f09d  mov     edi, 5
0x18000f0a2  jmp     loc_18000F32D
0x18000f0a7  lea     rdx, [rsp+308h+var_208]; struct _TbiTimeEventCreationParameters *
0x18000f0af  mov     rcx, rdi; struct _BR_EVENT_PARAMETERS *
0x18000f0b2  call    ?UnpackRpcParameters@TimeBroker@Broker@@CAXPEAU_BR_EVENT_PARAMETERS@@AEAU_TbiTimeEventCreationParameters@@@Z; Broker::TimeBroker::UnpackRpcParameters(_BR_EVENT_PARAMETERS *,_TbiTimeEventCreationParameters &)
0x18000f0b7  mov     eax, [rsp+308h+var_208]
0x18000f0be  mov     [rsp+308h+FileTime.dwLowDateTime], eax
0x18000f0c2  cmp     eax, 2
0x18000f0c5  jnz     short loc_18000F0EE
0x18000f0c7  test    byte ptr [rsp+308h+var_1E8], al
0x18000f0ce  jz      short loc_18000F0DA
0x18000f0d0  mov     [rsp+308h+FileTime.dwLowDateTime], 6
0x18000f0d8  jmp     short loc_18000F0EE
0x18000f0da  test    byte ptr [rsp+308h+var_1E8], 4
0x18000f0e2  mov     ecx, 7
0x18000f0e7  cmovnz  eax, ecx
0x18000f0ea  mov     [rsp+308h+FileTime.dwLowDateTime], eax
0x18000f0ee  cmp     [rsp+308h+arg_0], 1
0x18000f0f6  jnz     loc_18000F194
0x18000f0fc  lea     rcx, [rsp+308h+var_290]; this
0x18000f101  call    ??0RpcClientToken@Broker@@QEAA@XZ; Broker::RpcClientToken::RpcClientToken(void)
0x18000f106  nop
0x18000f107  lea     rcx, [rsp+308h+var_290]; this
0x18000f10c  call    ?IsAppContainer@RpcClientToken@Broker@@QEAA_NXZ; Broker::RpcClientToken::IsAppContainer(void)
0x18000f111  mov     [rsp+308h+var_2A8], al
0x18000f115  test    al, al
0x18000f117  jz      short loc_18000F185
0x18000f119  cmp     [rsp+308h+var_208], 3
0x18000f121  jnz     short loc_18000F13A
0x18000f123  mov     esi, 2
0x18000f128  lea     edx, [rsi+1Eh]; unsigned int
0x18000f12b  lea     rcx, [rsp+308h+var_290]; this
0x18000f130  call    ?CheckCapability@RpcClientToken@Broker@@QEAA_NKH@Z; Broker::RpcClientToken::CheckCapability(ulong,int)
0x18000f135  mov     r15b, al
0x18000f138  jmp     short loc_18000F169
0x18000f13a  cmp     [rsp+308h+var_208], 2
0x18000f142  jnz     short loc_18000F164
0x18000f144  test    byte ptr [rsp+308h+var_1E8], 2
0x18000f14c  jz      short loc_18000F155
0x18000f14e  mov     esi, 0Ch
0x18000f153  jmp     short loc_18000F169
0x18000f155  test    byte ptr [rsp+308h+var_1E8], 8
0x18000f15d  mov     esi, 10000h
0x18000f162  jnz     short loc_18000F169
0x18000f164  mov     esi, 8
0x18000f169  mov     edx, esi; unsigned int
0x18000f16b  lea     rcx, [rsp+308h+var_290]; this
0x18000f170  call    ?CheckCapability@RpcClientToken@Broker@@QEAA_NKH@Z; Broker::RpcClientToken::CheckCapability(ulong,int)
0x18000f175  test    al, al
0x18000f177  jz      loc_18000F620
0x18000f17d  mov     rsi, [rsp+308h+var_280]
0x18000f185  lea     rcx, [rsp+308h+var_290]; this
0x18000f18a  call    ??1RpcClientToken@Broker@@QEAA@XZ; Broker::RpcClientToken::~RpcClientToken(void)
0x18000f18f  mov     rcx, r14
0x18000f192  jmp     short loc_18000F1AB
0x18000f194  mov     rcx, r14; this
0x18000f197  mov     [rsp+308h+var_2A8], bl
0x18000f19b  mov     r15b, bl
0x18000f19e  cmp     [rsp+308h+arg_0], 2
0x18000f1a6  mov     r9b, 1
0x18000f1a9  jz      short loc_18000F1AE
0x18000f1ab  mov     r9b, bl; bool
0x18000f1ae  mov     r8b, [rsp+308h+var_2A8]; bool
0x18000f1b3  lea     rdx, [rsp+308h+var_208]; struct _TbiTimeEventCreationParameters *
0x18000f1bb  call    ?ValidateCreationParameters@TimeBroker@Broker@@AEAAXAEBU_TbiTimeEventCreationParameters@@_N1@Z; Broker::TimeBroker::ValidateCreationParameters(_TbiTimeEventCreationParameters const &,bool,bool)
0x18000f1c0  mov     rax, [rsp+308h+arg_10]
0x18000f1c8  mov     [rsp+308h+var_2E0], rax; struct _BROKERED_EVENT *
0x18000f1cd  mov     [rsp+308h+var_2E8], r12; struct _BROKER *
0x18000f1d2  mov     r9b, r15b; int
0x18000f1d5  lea     r8, [rsp+308h+var_208]; int
0x18000f1dd  lea     rdx, [rsp+308h+var_298]; int
0x18000f1e2  mov     rcx, r14; int
0x18000f1e5  call    ?ConstructEventObject@TimeBroker@Broker@@AEAA?AV?$unique_ptr@VTimeEvent@Broker@@U?$default_delete@VTimeEvent@Broker@@@std@@@std@@AEBU_TbiTimeEventCreationParameters@@_NPEAU_BROKER@@PEAU_BROKERED_EVENT@@@Z; Broker::TimeBroker::ConstructEventObject(_TbiTimeEventCreationParameters const &,bool,_BROKER *,_BROKERED_EVENT *)
0x18000f1ea  nop
0x18000f1eb  mov     edx, [rsp+308h+var_208]
0x18000f1f2  mov     ecx, [rsp+308h+var_1F0]
0x18000f1f9  test    edx, edx
0x18000f1fb  jnz     short loc_18000F201
0x18000f1fd  test    ecx, ecx
0x18000f1ff  jz      short loc_18000F20A
0x18000f201  cmp     edx, 1
0x18000f204  jnz     short loc_18000F214
0x18000f206  test    ecx, ecx
0x18000f208  jnz     short loc_18000F214
0x18000f20a  mov     r8d, [rsp+308h+var_1E8]
0x18000f212  jmp     short loc_18000F249
0x18000f214  mov     r8d, [rsp+308h+var_1E8]
0x18000f21c  cmp     edx, 2
0x18000f21f  jnz     short loc_18000F227
0x18000f221  test    r8b, 1
0x18000f225  jnz     short loc_18000F249
0x18000f227  cmp     edx, 3
0x18000f22a  jnz     short loc_18000F235
0x18000f22c  cmp     dword ptr [rsp+308h+SystemTime.wYear], ebx
0x18000f233  jz      short loc_18000F249
0x18000f235  cmp     edx, 4
0x18000f238  jnz     short loc_18000F23E
0x18000f23a  test    ecx, ecx
0x18000f23c  jz      short loc_18000F249
0x18000f23e  mov     eax, ebx
0x18000f240  cmp     edx, 5
0x18000f243  jnz     short loc_18000F24E
0x18000f245  test    ecx, ecx
0x18000f247  jnz     short loc_18000F29B
0x18000f249  mov     eax, 4
0x18000f24e  mov     ecx, [rsp+308h+var_1D0]
0x18000f255  test    edx, edx
0x18000f257  jnz     short loc_18000F26E
0x18000f259  test    ecx, ecx
0x18000f25b  jnz     short loc_18000F261
0x18000f25d  bts     eax, 9
0x18000f261  cmp     [rsp+308h+var_1AC], ebx
0x18000f268  jz      short loc_18000F29D
0x18000f26a  bts     eax, 1Ch
0x18000f26e  cmp     edx, 2
0x18000f271  jnz     short loc_18000F28F
0x18000f273  test    ecx, ecx
0x18000f275  jnz     short loc_18000F27B
0x18000f277  bts     eax, 9
0x18000f27b  test    r8b, 2
0x18000f27f  jz      short loc_18000F285
0x18000f281  bts     eax, 8
0x18000f285  test    r8b, 8
0x18000f289  jz      short loc_18000F29D
0x18000f28b  bts     eax, 16h
0x18000f28f  cmp     edx, 3
0x18000f292  jnz     short loc_18000F29D
0x18000f294  or      eax, 408Ah
0x18000f299  jmp     short loc_18000F2A1
0x18000f29b  mov     eax, ebx
0x18000f29d  bts     eax, 0Ah
0x18000f2a1  mov     [r13+8], eax
0x18000f2a5  mov     rax, [rsp+308h+var_278]
0x18000f2ad  mov     dword ptr [rax], 1
0x18000f2b3  mov     eax, [rsp+308h+FileTime.dwLowDateTime]
0x18000f2b7  mov     [r13+0], eax
0x18000f2bb  mov     eax, [rsp+308h+var_1A0]
0x18000f2c2  mov     [r13+10h], eax
0x18000f2c6  mov     eax, [rsp+308h+var_1A4]
0x18000f2cd  mov     [r13+0Ch], eax
0x18000f2d1  mov     eax, [rsp+308h+var_19C]
0x18000f2d8  mov     [r13+14h], eax
0x18000f2dc  mov     eax, [rsp+308h+var_198]
0x18000f2e3  mov     [r13+18h], eax
0x18000f2e7  mov     ecx, 10h; Size
0x18000f2ec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f2f1  mov     [rsp+308h+var_290], rax
0x18000f2f6  mov     rdx, qword ptr [rsp+308h+var_298]
0x18000f2fb  mov     qword ptr [rsp+308h+var_298], rbx
0x18000f300  mov     rcx, rax
0x18000f303  call    ??$?0VTimeEvent@Broker@@$0A@@?$shared_ptr@VTimeEvent@Broker@@@std@@QEAA@PEAVTimeEvent@Broker@@@Z; std::shared_ptr<Broker::TimeEvent>::shared_ptr<Broker::TimeEvent>(Broker::TimeEvent *)
0x18000f308  nop
0x18000f309  mov     [rsi], rax
0x18000f30c  mov     edi, ebx
0x18000f30e  mov     rdx, qword ptr [rsp+308h+var_298]
0x18000f313  test    rdx, rdx
0x18000f316  jz      short loc_18000F31E
0x18000f318  call    ??R?$default_delete@VTimeEvent@Broker@@@std@@QEBAXPEAVTimeEvent@Broker@@@Z; std::default_delete<Broker::TimeEvent>::operator()(Broker::TimeEvent *)
0x18000f31d  nop
0x18000f31e  jmp     short loc_18000F32D
0x18000f320  xor     ebx, ebx
0x18000f322  mov     edi, [rsp+308h+var_2A4]
0x18000f326  jmp     short loc_18000F32D
0x18000f328  mov     edi, 57h ; 'W'
0x18000f32d  mov     rcx, [rsp+308h+var_1C8]; void *
0x18000f335  test    rcx, rcx
0x18000f338  jz      short loc_18000F33F
0x18000f33a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f33f  cmp     [rsp+308h+arg_0], 2
0x18000f347  jz      loc_18000F507
0x18000f34d  mov     eax, cs:dword_180026058
0x18000f353  cmp     eax, 5
0x18000f356  jbe     loc_18000F5BD
0x18000f35c  mov     rdx, 400000000000h
0x18000f366  lea     rcx, dword_180026058
0x18000f36d  call    _tlgKeywordOn
0x18000f372  test    al, al
0x18000f374  jz      loc_18000F5BD
0x18000f37a  movzx   eax, [rsp+308h+var_2A8]
0x18000f37f  mov     [rsp+308h+var_2A4], eax
0x18000f383  mov     eax, [rsp+308h+FileTime.dwLowDateTime]
0x18000f387  mov     [rsp+308h+FileTime.dwLowDateTime], eax
0x18000f38b  mov     rax, [rsp+308h+arg_20]
0x18000f393  mov     [rsp+308h+var_278], rax
0x18000f39b  mov     [rsp+308h+var_298], edi
0x18000f39f  mov     [rsp+308h+var_280], rbx
0x18000f3a7  mov     edx, [rsp+308h+var_208]
0x18000f3ae  mov     ecx, edx
0x18000f3b0  test    edx, edx
0x18000f3b2  jz      short loc_18000F3CD
0x18000f3b4  sub     ecx, 1
0x18000f3b7  jz      short loc_18000F3CD
0x18000f3b9  sub     ecx, 1
0x18000f3bc  jz      short loc_18000F3E0
0x18000f3be  sub     ecx, 1
0x18000f3c1  jz      short loc_18000F3D9
0x18000f3c3  sub     ecx, 1
0x18000f3c6  jz      short loc_18000F3CD
0x18000f3c8  cmp     ecx, 1
0x18000f3cb  jnz     short loc_18000F3E0
0x18000f3cd  movzx   eax, [rsp+308h+var_1D3]
0x18000f3d5  test    eax, eax
0x18000f3d7  jz      short loc_18000F3E0
0x18000f3d9  mov     eax, 1
0x18000f3de  jmp     short loc_18000F3E3
0x18000f3e0  mov     rax, rbx
0x18000f3e3  mov     [rsp+308h+var_260], rax
0x18000f3eb  mov     ecx, edx
0x18000f3ed  test    edx, edx
0x18000f3ef  jz      short loc_18000F439
0x18000f3f1  sub     ecx, 1
0x18000f3f4  jz      short loc_18000F42A
0x18000f3f6  sub     ecx, 1
0x18000f3f9  jz      short loc_18000F41E
0x18000f3fb  sub     ecx, 1
0x18000f3fe  jz      short loc_18000F40E
0x18000f400  sub     ecx, 1
0x18000f403  jz      short loc_18000F439
0x18000f405  cmp     ecx, 1
0x18000f408  jz      short loc_18000F439
0x18000f40a  mov     eax, ebx
0x18000f40c  jmp     short loc_18000F415
0x18000f40e  mov     eax, dword ptr [rsp+308h+SystemTime.wYear]
0x18000f415  mov     ecx, [rsp+308h+var_1F0]
0x18000f41c  jmp     short loc_18000F442
0x18000f41e  mov     ecx, [rsp+308h+var_1F0]
0x18000f425  imul    eax, ecx, 3Ch ; '<'
0x18000f428  jmp     short loc_18000F442
  ... truncated ...
```
