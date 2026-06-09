# _TbiQueryCEventTriggerTime

- ea: `0x180004be0`
- end: `0x180004dcb`
- name: `_TbiQueryCEventTriggerTime`
- size: `491`
- prototype: `__int64 __fastcall(__int64, __int64, struct _FILETIME *, struct _FILETIME *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003800`
- `0x180003840`
- `0x180003f6c`
- `0x180004000`
- `0x180004218`
- `0x180004274`
- `0x1800042e8`
- `0x180004b70`
- `0x180004be0`
- `0x180004e5c`
- `0x180005b30`
- `0x1800112d8`
- `0x180012dd0`
- `0x180013978`

## string_xrefs

- `0x180004cb4`: `Microsoft.ProcessID%x_1.0.0.1_neutral__8wekyb3d8bbwe`

## pseudocode

```c
__int64 __fastcall TbiQueryCEventTriggerTime(__int64 a1, __int64 a2, struct _FILETIME *a3, struct _FILETIME *a4)
{
  Broker::Win32Error *v6; // rbx
  Broker::TimeBroker *v7; // rdi
  Broker::ApplicationIdentity *AppId; // rax
  ULONG v10; // [rsp+30h] [rbp-1E8h]
  _DWORD v11[4]; // [rsp+38h] [rbp-1E0h] BYREF
  __int64 v12; // [rsp+48h] [rbp-1D0h] BYREF
  Broker::BILayer::Failure *v13; // [rsp+50h] [rbp-1C8h] BYREF
  Broker::Win32Error *v14[3]; // [rsp+58h] [rbp-1C0h] BYREF
  void **pExceptionObject; // [rsp+70h] [rbp-1A8h] BYREF
  __int128 v16; // [rsp+78h] [rbp-1A0h]
  int v17; // [rsp+88h] [rbp-190h]
  _BYTE v18[24]; // [rsp+90h] [rbp-188h] BYREF
  _BYTE v19[32]; // [rsp+A8h] [rbp-170h] BYREF
  _BYTE v20[40]; // [rsp+C8h] [rbp-150h] BYREF
  unsigned __int16 v21[128]; // [rsp+F0h] [rbp-128h] BYREF

  v12 = a2;
  v10 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_5a0d7e735cfa35da01a2c84fb47b9fbb_Traceguids);
  try
  {
    Broker::RpcClientToken::RpcClientToken((Broker::RpcClientToken *)v11);
    if ( (unsigned int)CTimeBrokerAccessCheck() )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_5a0d7e735cfa35da01a2c84fb47b9fbb_Traceguids, v11[0]);
      v16 = 0;
      v17 = 5;
      pExceptionObject = &Broker::AccessDenied::`vftable';
      throw (Broker::AccessDenied *)&pExceptionObject;
    }
    StringCchPrintfW(v21, 0x7Fu, L"Microsoft.ProcessID%x_1.0.0.1_neutral__8wekyb3d8bbwe", v11[0]);
    v6 = *(&Broker::TimeBroker::Instance + 1);
    if ( *(&Broker::TimeBroker::Instance + 1) )
    {
      _InterlockedIncrement((volatile signed __int32 *)*(&Broker::TimeBroker::Instance + 1) + 2);
      v6 = *(&Broker::TimeBroker::Instance + 1);
    }
    v7 = Broker::TimeBroker::Instance;
    v14[1] = Broker::TimeBroker::Instance;
    v14[2] = v6;
    AppId = Broker::RpcClientToken::GetAppId((__int64)v11, (Broker::ApplicationIdentity *)v18, v21);
    Broker::TimeBroker::QueryCTriggerTime(v7, AppId, (const struct _CBROKERED_EVENT_ID *)&v12, a3, a4);
    std::wstring::_Tidy_deallocate(v20);
    std::wstring::_Tidy_deallocate(v19);
    std::vector<unsigned char>::_Tidy(v18);
    if ( v6 )
      std::_Ref_count_base::_Decref(v6);
    Broker::RpcClientToken::~RpcClientToken((Broker::RpcClientToken *)v11);
  }
  catch ( std::bad_alloc )
  {
    v10 = 14;
  }
  catch ( Broker::NotFound )
  {
    v10 = 2;
  }
  catch ( Broker::AccessDenied )
  {
    v10 = 5;
  }
  catch ( Broker::BILayer::Failure *v13 )
  {
    v10 = RtlNtStatusToDosError(*((_DWORD *)v13 + 8));
  }
  catch ( Broker::Win32Error *v14 )
  {
    v10 = *((_DWORD *)v14[0] + 8);
  }
  catch ( ... )
  {
    v10 = 1359;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_5a0d7e735cfa35da01a2c84fb47b9fbb_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x180004be0  mov     [rsp+arg_0], rbx
0x180004be5  push    rsi
0x180004be6  push    rdi
0x180004be7  push    r14
0x180004be9  sub     rsp, 200h
0x180004bf0  mov     rax, cs:__security_cookie
0x180004bf7  xor     rax, rsp
0x180004bfa  mov     [rsp+218h+var_28], rax
0x180004c02  mov     r14, r9
0x180004c05  mov     rsi, r8
0x180004c08  mov     [rsp+218h+var_1D0], rdx
0x180004c0d  mov     [rsp+218h+var_1E8], 0
0x180004c15  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c1c  test    byte ptr [rcx+1Ch], 1
0x180004c20  jz      short loc_180004C3E
0x180004c22  cmp     byte ptr [rcx+19h], 4
0x180004c26  jb      short loc_180004C3E
0x180004c28  mov     edx, 0Ah
0x180004c2d  lea     r8, WPP_5a0d7e735cfa35da01a2c84fb47b9fbb_Traceguids
0x180004c34  mov     rcx, [rcx+10h]
0x180004c38  call    WPP_SF_
0x180004c3d  nop
0x180004c3e  lea     rcx, [rsp+218h+var_1E0]; this
0x180004c43  call    ??0RpcClientToken@Broker@@QEAA@XZ; Broker::RpcClientToken::RpcClientToken(void)
0x180004c48  nop
0x180004c49  call    ?CTimeBrokerAccessCheck@@YAJXZ; CTimeBrokerAccessCheck(void)
0x180004c4e  test    eax, eax
0x180004c50  jz      short loc_180004CAF
0x180004c52  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c59  test    byte ptr [rcx+1Ch], 20h
0x180004c5d  jz      short loc_180004C7F
0x180004c5f  cmp     byte ptr [rcx+19h], 2
0x180004c63  jb      short loc_180004C7F
0x180004c65  mov     edx, 0Bh
0x180004c6a  mov     r9d, [rsp+218h+var_1E0]
0x180004c6f  lea     r8, WPP_5a0d7e735cfa35da01a2c84fb47b9fbb_Traceguids
0x180004c76  mov     rcx, [rcx+10h]
0x180004c7a  call    WPP_SF_d
0x180004c7f  xorps   xmm0, xmm0
0x180004c82  movups  [rsp+218h+var_1A0], xmm0
0x180004c87  mov     [rsp+218h+var_190], 5
0x180004c92  lea     rax, ??_7AccessDenied@Broker@@6B@; const Broker::AccessDenied::`vftable'
0x180004c99  mov     [rsp+218h+pExceptionObject], rax
0x180004c9e  lea     rdx, _TI3?AUAccessDenied@Broker@@; pThrowInfo
0x180004ca5  lea     rcx, [rsp+218h+pExceptionObject]; pExceptionObject
0x180004caa  call    _CxxThrowException_0
0x180004caf  mov     r9d, [rsp+218h+var_1E0]
0x180004cb4  lea     r8, aMicrosoftProce; "Microsoft.ProcessID%x_1.0.0.1_neutral__"...
0x180004cbb  mov     edx, 7Fh; unsigned __int64
0x180004cc0  lea     rcx, [rsp+218h+var_128]; unsigned __int16 *
0x180004cc8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004ccd  mov     rbx, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x180004cd4  test    rbx, rbx
0x180004cd7  jz      short loc_180004CE4
0x180004cd9  lock inc dword ptr [rbx+8]
0x180004cdd  mov     rbx, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x180004ce4  mov     rdi, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x180004ceb  mov     [rsp+218h+var_1B8], rdi
0x180004cf0  mov     [rsp+218h+var_1B0], rbx
0x180004cf5  lea     r8, [rsp+218h+var_128]
0x180004cfd  lea     rdx, [rsp+218h+var_188]
0x180004d05  lea     rcx, [rsp+218h+var_1E0]
0x180004d0a  call    ?GetAppId@RpcClientToken@Broker@@QEAA?AUApplicationIdentity@2@PEBG_N@Z; Broker::RpcClientToken::GetAppId(ushort const *,bool)
0x180004d0f  nop
0x180004d10  mov     [rsp+218h+var_1F8], r14; struct _FILETIME *
0x180004d15  mov     r9, rsi; struct _FILETIME *
0x180004d18  lea     r8, [rsp+218h+var_1D0]; struct _CBROKERED_EVENT_ID *
0x180004d1d  mov     rdx, rax; struct Broker::ApplicationIdentity *
0x180004d20  mov     rcx, rdi; this
0x180004d23  call    ?QueryCTriggerTime@TimeBroker@Broker@@QEAAXAEBUApplicationIdentity@2@AEBU_CBROKERED_EVENT_ID@@AEAU_FILETIME@@2@Z; Broker::TimeBroker::QueryCTriggerTime(Broker::ApplicationIdentity const &,_CBROKERED_EVENT_ID const &,_FILETIME &,_FILETIME &)
0x180004d28  nop
0x180004d29  lea     rcx, [rsp+218h+var_150]
0x180004d31  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180004d36  lea     rcx, [rsp+218h+var_170]
0x180004d3e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180004d43  lea     rcx, [rsp+218h+var_188]
0x180004d4b  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180004d50  nop
0x180004d51  test    rbx, rbx
0x180004d54  jz      short loc_180004D5F
0x180004d56  mov     rcx, rbx; this
0x180004d59  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180004d5e  nop
0x180004d5f  lea     rcx, [rsp+218h+var_1E0]; this
0x180004d64  call    ??1RpcClientToken@Broker@@QEAA@XZ; Broker::RpcClientToken::~RpcClientToken(void)
0x180004d69  nop
0x180004d6a  jmp     short loc_180004D76
0x180004d6c  jmp     short loc_180004D76
0x180004d6e  jmp     short loc_180004D76
0x180004d70  jmp     short loc_180004D76
0x180004d72  jmp     short loc_180004D76
0x180004d74  jmp     short $+2
0x180004d76  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d7d  test    byte ptr [rcx+1Ch], 1
0x180004d81  jz      short loc_180004DA3
0x180004d83  cmp     byte ptr [rcx+19h], 4
0x180004d87  jb      short loc_180004DA3
0x180004d89  mov     edx, 0Ch
0x180004d8e  mov     r9d, [rsp+218h+var_1E8]
0x180004d93  lea     r8, WPP_5a0d7e735cfa35da01a2c84fb47b9fbb_Traceguids
0x180004d9a  mov     rcx, [rcx+10h]
0x180004d9e  call    WPP_SF_d
0x180004da3  mov     eax, [rsp+218h+var_1E8]
0x180004da7  mov     rcx, [rsp+218h+var_28]
0x180004daf  xor     rcx, rsp; StackCookie
0x180004db2  call    __security_check_cookie
0x180004db7  mov     rbx, [rsp+218h+arg_0]
0x180004dbf  add     rsp, 200h
0x180004dc6  pop     r14
0x180004dc8  pop     rdi
0x180004dc9  pop     rsi
0x180004dca  retn
```
