# _TbiUpdateCEvent

- ea: `0x180003ac0`
- end: `0x180003ca3`
- name: `_TbiUpdateCEvent`
- size: `483`
- prototype: `__int64 __fastcall(__int64, __int64, struct _TbiTimeEventCreationParameters *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180003800`
- `0x180003840`
- `0x180003868`
- `0x180003ac0`
- `0x180003f6c`
- `0x180004000`
- `0x180004218`
- `0x180004274`
- `0x1800042e8`
- `0x180004b70`
- `0x180005b30`
- `0x1800112d8`
- `0x180012dd0`
- `0x180013978`

## string_xrefs

- `0x180003b90`: `Microsoft.ProcessID%x_1.0.0.1_neutral__8wekyb3d8bbwe`

## pseudocode

```c
__int64 __fastcall TbiUpdateCEvent(__int64 a1, __int64 a2, struct _TbiTimeEventCreationParameters *a3)
{
  Broker::Win32Error *v4; // rbx
  Broker::TimeBroker *v5; // rdi
  Broker::ApplicationIdentity *AppId; // rax
  ULONG v8; // [rsp+20h] [rbp-1D8h]
  _DWORD v9[4]; // [rsp+28h] [rbp-1D0h] BYREF
  __int64 v10; // [rsp+38h] [rbp-1C0h] BYREF
  Broker::BILayer::Failure *v11; // [rsp+40h] [rbp-1B8h] BYREF
  Broker::Win32Error *v12[3]; // [rsp+48h] [rbp-1B0h] BYREF
  void **pExceptionObject; // [rsp+60h] [rbp-198h] BYREF
  __int128 v14; // [rsp+68h] [rbp-190h]
  int v15; // [rsp+78h] [rbp-180h]
  _BYTE v16[24]; // [rsp+80h] [rbp-178h] BYREF
  _BYTE v17[32]; // [rsp+98h] [rbp-160h] BYREF
  _BYTE v18[40]; // [rsp+B8h] [rbp-140h] BYREF
  unsigned __int16 v19[128]; // [rsp+E0h] [rbp-118h] BYREF

  v10 = a2;
  v8 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_5a0d7e735cfa35da01a2c84fb47b9fbb_Traceguids);
  try
  {
    Broker::RpcClientToken::RpcClientToken((Broker::RpcClientToken *)v9);
    if ( (unsigned int)CTimeBrokerAccessCheck() )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_5a0d7e735cfa35da01a2c84fb47b9fbb_Traceguids, v9[0]);
      v14 = 0;
      v15 = 5;
      pExceptionObject = &Broker::AccessDenied::`vftable';
      throw (Broker::AccessDenied *)&pExceptionObject;
    }
    StringCchPrintfW(v19, 0x7Fu, L"Microsoft.ProcessID%x_1.0.0.1_neutral__8wekyb3d8bbwe", v9[0]);
    v4 = *(&Broker::TimeBroker::Instance + 1);
    if ( *(&Broker::TimeBroker::Instance + 1) )
    {
      _InterlockedIncrement((volatile signed __int32 *)*(&Broker::TimeBroker::Instance + 1) + 2);
      v4 = *(&Broker::TimeBroker::Instance + 1);
    }
    v5 = Broker::TimeBroker::Instance;
    v12[1] = Broker::TimeBroker::Instance;
    v12[2] = v4;
    AppId = Broker::RpcClientToken::GetAppId((__int64)v9, (Broker::ApplicationIdentity *)v16, v19);
    Broker::TimeBroker::UpdateCEvent(v5, AppId, (const struct _CBROKERED_EVENT_ID *)&v10, a3);
    std::wstring::_Tidy_deallocate(v18);
    std::wstring::_Tidy_deallocate(v17);
    std::vector<unsigned char>::_Tidy(v16);
    if ( v4 )
      std::_Ref_count_base::_Decref(v4);
    Broker::RpcClientToken::~RpcClientToken((Broker::RpcClientToken *)v9);
  }
  catch ( std::bad_alloc )
  {
    v8 = 14;
  }
  catch ( Broker::NotFound )
  {
    v8 = 2;
  }
  catch ( Broker::AccessDenied )
  {
    v8 = 5;
  }
  catch ( Broker::BILayer::Failure *v11 )
  {
    v8 = RtlNtStatusToDosError(*((_DWORD *)v11 + 8));
  }
  catch ( Broker::Win32Error *v12 )
  {
    v8 = *((_DWORD *)v12[0] + 8);
  }
  catch ( ... )
  {
    v8 = 1359;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_5a0d7e735cfa35da01a2c84fb47b9fbb_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x180003ac0  mov     [rsp+arg_0], rbx
0x180003ac5  mov     [rsp+arg_18], rsi
0x180003aca  push    rdi
0x180003acb  sub     rsp, 1F0h
0x180003ad2  mov     rax, cs:__security_cookie
0x180003ad9  xor     rax, rsp
0x180003adc  mov     [rsp+1F8h+var_18], rax
0x180003ae4  mov     rsi, r8
0x180003ae7  mov     [rsp+1F8h+var_1C0], rdx
0x180003aec  mov     [rsp+1F8h+var_1D8], 0
0x180003af4  mov     rcx, cs:WPP_GLOBAL_Control
0x180003afb  test    byte ptr [rcx+1Ch], 1
0x180003aff  jz      short loc_180003B1D
0x180003b01  cmp     byte ptr [rcx+19h], 4
0x180003b05  jb      short loc_180003B1D
0x180003b07  mov     edx, 10h
0x180003b0c  lea     r8, WPP_5a0d7e735cfa35da01a2c84fb47b9fbb_Traceguids
0x180003b13  mov     rcx, [rcx+10h]
0x180003b17  call    WPP_SF_
0x180003b1c  nop
0x180003b1d  lea     rcx, [rsp+1F8h+var_1D0]; this
0x180003b22  call    ??0RpcClientToken@Broker@@QEAA@XZ; Broker::RpcClientToken::RpcClientToken(void)
0x180003b27  nop
0x180003b28  call    ?CTimeBrokerAccessCheck@@YAJXZ; CTimeBrokerAccessCheck(void)
0x180003b2d  test    eax, eax
0x180003b2f  jz      short loc_180003B8B
0x180003b31  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b38  test    byte ptr [rcx+1Ch], 20h
0x180003b3c  jz      short loc_180003B5E
0x180003b3e  cmp     byte ptr [rcx+19h], 2
0x180003b42  jb      short loc_180003B5E
0x180003b44  mov     edx, 11h
0x180003b49  mov     r9d, [rsp+1F8h+var_1D0]
0x180003b4e  lea     r8, WPP_5a0d7e735cfa35da01a2c84fb47b9fbb_Traceguids
0x180003b55  mov     rcx, [rcx+10h]
0x180003b59  call    WPP_SF_d
0x180003b5e  xorps   xmm0, xmm0
0x180003b61  movups  [rsp+1F8h+var_190], xmm0
0x180003b66  mov     [rsp+1F8h+var_180], 5
0x180003b6e  lea     rax, ??_7AccessDenied@Broker@@6B@; const Broker::AccessDenied::`vftable'
0x180003b75  mov     [rsp+1F8h+pExceptionObject], rax
0x180003b7a  lea     rdx, _TI3?AUAccessDenied@Broker@@; pThrowInfo
0x180003b81  lea     rcx, [rsp+1F8h+pExceptionObject]; pExceptionObject
0x180003b86  call    _CxxThrowException_0
0x180003b8b  mov     r9d, [rsp+1F8h+var_1D0]
0x180003b90  lea     r8, aMicrosoftProce; "Microsoft.ProcessID%x_1.0.0.1_neutral__"...
0x180003b97  mov     edx, 7Fh; unsigned __int64
0x180003b9c  lea     rcx, [rsp+1F8h+var_118]; unsigned __int16 *
0x180003ba4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003ba9  mov     rbx, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x180003bb0  test    rbx, rbx
0x180003bb3  jz      short loc_180003BC0
0x180003bb5  lock inc dword ptr [rbx+8]
0x180003bb9  mov     rbx, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x180003bc0  mov     rdi, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x180003bc7  mov     [rsp+1F8h+var_1A8], rdi
0x180003bcc  mov     [rsp+1F8h+var_1A0], rbx
0x180003bd1  lea     r8, [rsp+1F8h+var_118]
0x180003bd9  lea     rdx, [rsp+1F8h+var_178]
0x180003be1  lea     rcx, [rsp+1F8h+var_1D0]
0x180003be6  call    ?GetAppId@RpcClientToken@Broker@@QEAA?AUApplicationIdentity@2@PEBG_N@Z; Broker::RpcClientToken::GetAppId(ushort const *,bool)
0x180003beb  nop
0x180003bec  mov     r9, rsi; struct _TbiTimeEventCreationParameters *
0x180003bef  lea     r8, [rsp+1F8h+var_1C0]; struct _CBROKERED_EVENT_ID *
0x180003bf4  mov     rdx, rax; struct Broker::ApplicationIdentity *
0x180003bf7  mov     rcx, rdi; this
0x180003bfa  call    ?UpdateCEvent@TimeBroker@Broker@@QEAAXAEBUApplicationIdentity@2@AEBU_CBROKERED_EVENT_ID@@AEAU_TbiTimeEventCreationParameters@@@Z; Broker::TimeBroker::UpdateCEvent(Broker::ApplicationIdentity const &,_CBROKERED_EVENT_ID const &,_TbiTimeEventCreationParameters &)
0x180003bff  nop
0x180003c00  lea     rcx, [rsp+1F8h+var_140]
0x180003c08  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180003c0d  lea     rcx, [rsp+1F8h+var_160]
0x180003c15  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180003c1a  lea     rcx, [rsp+1F8h+var_178]
0x180003c22  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180003c27  nop
0x180003c28  test    rbx, rbx
0x180003c2b  jz      short loc_180003C36
0x180003c2d  mov     rcx, rbx; this
0x180003c30  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180003c35  nop
0x180003c36  lea     rcx, [rsp+1F8h+var_1D0]; this
0x180003c3b  call    ??1RpcClientToken@Broker@@QEAA@XZ; Broker::RpcClientToken::~RpcClientToken(void)
0x180003c40  nop
0x180003c41  jmp     short loc_180003C4D
0x180003c43  jmp     short loc_180003C4D
0x180003c45  jmp     short loc_180003C4D
0x180003c47  jmp     short loc_180003C4D
0x180003c49  jmp     short loc_180003C4D
0x180003c4b  jmp     short $+2
0x180003c4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c54  test    byte ptr [rcx+1Ch], 1
0x180003c58  jz      short loc_180003C7A
0x180003c5a  cmp     byte ptr [rcx+19h], 4
0x180003c5e  jb      short loc_180003C7A
0x180003c60  mov     edx, 12h
0x180003c65  mov     r9d, [rsp+1F8h+var_1D8]
0x180003c6a  lea     r8, WPP_5a0d7e735cfa35da01a2c84fb47b9fbb_Traceguids
0x180003c71  mov     rcx, [rcx+10h]
0x180003c75  call    WPP_SF_d
0x180003c7a  mov     eax, [rsp+1F8h+var_1D8]
0x180003c7e  mov     rcx, [rsp+1F8h+var_18]
0x180003c86  xor     rcx, rsp; StackCookie
0x180003c89  call    __security_check_cookie
0x180003c8e  lea     r11, [rsp+1F8h+var_8]
0x180003c96  mov     rbx, [r11+10h]
0x180003c9a  mov     rsi, [r11+28h]
0x180003c9e  mov     rsp, r11
0x180003ca1  pop     rdi
0x180003ca2  retn
```
