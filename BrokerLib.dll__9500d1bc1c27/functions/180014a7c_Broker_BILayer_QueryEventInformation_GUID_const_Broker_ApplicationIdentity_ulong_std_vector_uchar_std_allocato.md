# Broker::BILayer::QueryEventInformation(_GUID const &,Broker::ApplicationIdentity &,ulong &,std::vector<uchar,std::allocator<uchar>> &,ulong &)

- ea: `0x180014a7c`
- end: `0x180014d3a`
- name: `?QueryEventInformation@BILayer@Broker@@YAXAEBU_GUID@@AEAUApplicationIdentity@2@AEAKAEAV?$vector@EV?$allocator@E@std@@@std@@2@Z`
- size: `702`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800188c0`

## callees

- `0x180004d70`
- `0x180006b30`
- `0x180008340`
- `0x180009e94`
- `0x18000f210`
- `0x18001198c`
- `0x180014474`
- `0x180014a7c`
- `0x180014d40`
- `0x180015af0`
- `0x1800165da`
- `0x18001a070`
- `0x18001a7f0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180014bad`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180014bba`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180014bad`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180014bba`
- `api-ms-win-core-bicltapi-l1-1-6!BiQueryBrokeredEvent` at `0x180014ad3`
- `api-ms-win-core-bicltapi-l1-1-6!BiQueryBrokeredEvent` at `0x180014ad3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Broker::BILayer::QueryEventInformation(
        __int64 a1,
        Broker::ApplicationIdentity *a2,
        _DWORD *a3,
        _QWORD *a4,
        _DWORD *a5)
{
  int v7; // eax
  int v8; // ebx
  _DWORD *v9; // rax
  _DWORD *v10; // rsi
  __int64 v11; // r8
  char *v12; // rdi
  const unsigned __int16 *v13; // rbx
  __int64 v14; // r12
  __int64 v15; // r13
  Broker::ApplicationIdentity *v16; // rdi
  _QWORD *v17; // rbx
  __int64 v18; // r8
  _DWORD *v19; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD *v21; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD *v22; // [rsp+58h] [rbp-A8h]
  __int64 v23; // [rsp+60h] [rbp-A0h]
  void **pExceptionObject; // [rsp+68h] [rbp-98h] BYREF
  __int128 v25; // [rsp+70h] [rbp-90h]
  int v26; // [rsp+80h] [rbp-80h]
  int v27; // [rsp+88h] [rbp-78h]
  _BYTE v28[96]; // [rsp+90h] [rbp-70h] BYREF

  v21 = a3;
  v23 = a1;
  v22 = a5;
  v19 = 0;
  v20 = 0;
  v7 = BiQueryBrokeredEvent(a1, &v20, &v19);
  v8 = v7;
  if ( v7 < 0 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        &WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids,
        (unsigned int)v7);
    v25 = 0;
    v26 = 6;
    pExceptionObject = &Broker::BILayer::Failure::`vftable';
    v27 = v8;
    throw (Broker::BILayer::Failure *)&pExceptionObject;
  }
  v9 = v19;
  v10 = v19;
  v11 = (unsigned int)v19[10];
  v12 = (char *)v19 + v11;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      &WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids,
      (unsigned int)v19[9],
      v11);
    v9 = v19;
  }
  if ( v10[9] )
    v13 = (const unsigned __int16 *)((char *)v9 + (unsigned int)v10[9]);
  else
    v13 = &LocaleName;
  v14 = (__int64)v9 + (unsigned int)v10[11];
  v15 = (unsigned int)v10[12];
  *v22 = v10[13];
  if ( !IsValidSid(v12) )
  {
    if ( !IsValidSid(v12) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids, 3221225485LL);
    v25 = 0;
    v26 = 6;
    pExceptionObject = &Broker::BILayer::Failure::`vftable';
    v27 = -1073741811;
    throw (Broker::BILayer::Failure *)&pExceptionObject;
  }
  v16 = Broker::ApplicationIdentity::ApplicationIdentity((Broker::ApplicationIdentity *)v28, v12, v13);
  if ( a2 != v16 )
  {
    std::vector<unsigned char>::_Tidy(a2);
    *(_QWORD *)a2 = *(_QWORD *)v16;
    *((_QWORD *)a2 + 1) = *((_QWORD *)v16 + 1);
    *((_QWORD *)a2 + 2) = *((_QWORD *)v16 + 2);
    *(_QWORD *)v16 = 0;
    *((_QWORD *)v16 + 1) = 0;
    *((_QWORD *)v16 + 2) = 0;
  }
  std::wstring::operator=((char *)a2 + 24, (char *)v16 + 24);
  v17 = (_QWORD *)((char *)a2 + 56);
  std::wstring::operator=((char *)a2 + 56, (char *)v16 + 56);
  Broker::ApplicationIdentity::~ApplicationIdentity((Broker::ApplicationIdentity *)v28);
  *v21 = v10[8];
  v18 = *a4;
  if ( a4[1] != *a4 )
    a4[1] = v18;
  std::vector<unsigned char>::insert<unsigned char *,0>((_DWORD)a4, (unsigned int)&v21, v18, v14, v14 + v15);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    if ( *((_QWORD *)a2 + 10) > 7u )
      v17 = (_QWORD *)*v17;
    WPP_SF__guid__sid_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      *(PSID *)a2,
      (__int64)v17,
      *((_BYTE *)a4 + 8) - *(_BYTE *)a4);
  }
  Broker::BILayer::BiLayerMemory::~BiLayerMemory((Broker::BILayer::BiLayerMemory *)&v19);
}

```

## disassembly

```asm
0x180014a7c  push    rbp
0x180014a7e  push    rbx
0x180014a7f  push    rsi
0x180014a80  push    rdi
0x180014a81  push    r12
0x180014a83  push    r13
0x180014a85  push    r14
0x180014a87  push    r15
0x180014a89  lea     rbp, [rsp-8]
0x180014a8e  sub     rsp, 108h
0x180014a95  mov     rax, cs:__security_cookie
0x180014a9c  xor     rax, rsp
0x180014a9f  mov     [rbp+40h+var_50], rax
0x180014aa3  mov     r14, r9
0x180014aa6  mov     [rsp+140h+var_F0], r8
0x180014aab  mov     r15, rdx
0x180014aae  mov     [rsp+140h+var_E0], rcx
0x180014ab3  mov     rax, [rbp+40h+arg_20]
0x180014ab7  mov     [rsp+140h+var_E8], rax
0x180014abc  xor     r12d, r12d
0x180014abf  mov     [rsp+140h+var_100], r12
0x180014ac4  mov     [rsp+140h+var_F8], r12d
0x180014ac9  lea     r8, [rsp+140h+var_100]
0x180014ace  lea     rdx, [rsp+140h+var_F8]
0x180014ad3  call    cs:__imp_BiQueryBrokeredEvent
0x180014ad9  mov     ebx, eax
0x180014adb  test    eax, eax
0x180014add  jns     short loc_180014B3A
0x180014adf  mov     rcx, cs:WPP_GLOBAL_Control
0x180014ae6  test    byte ptr [rcx+1Ch], 1
0x180014aea  jz      short loc_180014B0A
0x180014aec  cmp     byte ptr [rcx+19h], 2
0x180014af0  jb      short loc_180014B0A
0x180014af2  lea     edx, [r12+10h]
0x180014af7  mov     r9d, eax
0x180014afa  lea     r8, WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids
0x180014b01  mov     rcx, [rcx+10h]
0x180014b05  call    WPP_SF_d
0x180014b0a  xorps   xmm0, xmm0
0x180014b0d  movups  [rsp+140h+var_D0], xmm0
0x180014b12  mov     [rbp+40h+var_C0], 6
0x180014b19  lea     rax, ??_7Failure@BILayer@Broker@@6B@; const Broker::BILayer::Failure::`vftable'
0x180014b20  mov     [rsp+140h+pExceptionObject], rax
0x180014b25  mov     [rbp+40h+var_B8], ebx
0x180014b28  lea     rdx, _TI3?AUFailure@BILayer@Broker@@; pThrowInfo
0x180014b2f  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x180014b34  call    _CxxThrowException_0
0x180014b3a  mov     rax, [rsp+140h+var_100]
0x180014b3f  mov     rsi, rax
0x180014b42  mov     r8d, [rax+28h]
0x180014b46  lea     rdi, [r8+rax]
0x180014b4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b51  test    byte ptr [rcx+1Ch], 1
0x180014b55  jz      short loc_180014B80
0x180014b57  cmp     byte ptr [rcx+19h], 4
0x180014b5b  jb      short loc_180014B80
0x180014b5d  mov     edx, 11h
0x180014b62  mov     dword ptr [rsp+140h+pSid], r8d
0x180014b67  mov     r9d, [rax+24h]
0x180014b6b  lea     r8, WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids
0x180014b72  mov     rcx, [rcx+10h]
0x180014b76  call    WPP_SF_dd
0x180014b7b  mov     rax, [rsp+140h+var_100]
0x180014b80  cmp     [rsi+24h], r12d
0x180014b84  jnz     short loc_180014B8F
0x180014b86  lea     rbx, LocaleName
0x180014b8d  jmp     short loc_180014B95
0x180014b8f  mov     ebx, [rsi+24h]
0x180014b92  add     rbx, rax
0x180014b95  mov     r12d, [rsi+2Ch]
0x180014b99  add     r12, rax
0x180014b9c  mov     r13d, [rsi+30h]
0x180014ba0  mov     eax, [rsi+34h]
0x180014ba3  mov     rcx, [rsp+140h+var_E8]
0x180014ba8  mov     [rcx], eax
0x180014baa  mov     rcx, rdi; pSid
0x180014bad  call    cs:__imp_IsValidSid
0x180014bb3  test    eax, eax
0x180014bb5  jnz     short loc_180014C29
0x180014bb7  mov     rcx, rdi; pSid
0x180014bba  call    cs:__imp_IsValidSid
0x180014bc0  test    eax, eax
0x180014bc2  jnz     short loc_180014BC9
0x180014bc4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180014bc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180014bd0  mov     ebx, 0C000000Dh
0x180014bd5  test    byte ptr [rcx+1Ch], 1
0x180014bd9  jz      short loc_180014BF9
0x180014bdb  cmp     byte ptr [rcx+19h], 2
0x180014bdf  jb      short loc_180014BF9
0x180014be1  mov     edx, 12h
0x180014be6  mov     r9d, ebx
0x180014be9  lea     r8, WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids
0x180014bf0  mov     rcx, [rcx+10h]
0x180014bf4  call    WPP_SF_d
0x180014bf9  xorps   xmm0, xmm0
0x180014bfc  movups  [rsp+140h+var_D0], xmm0
0x180014c01  mov     [rbp+40h+var_C0], 6
0x180014c08  lea     rax, ??_7Failure@BILayer@Broker@@6B@; const Broker::BILayer::Failure::`vftable'
0x180014c0f  mov     [rsp+140h+pExceptionObject], rax
0x180014c14  mov     [rbp+40h+var_B8], ebx
0x180014c17  lea     rdx, _TI3?AUFailure@BILayer@Broker@@; pThrowInfo
0x180014c1e  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x180014c23  call    _CxxThrowException_0
0x180014c29  mov     r8, rbx; unsigned __int16 *
0x180014c2c  mov     rdx, rdi; void *
0x180014c2f  lea     rcx, [rbp+40h+var_B0]; this
0x180014c33  call    ??0ApplicationIdentity@Broker@@QEAA@PEAXQEBG@Z; Broker::ApplicationIdentity::ApplicationIdentity(void *,ushort const * const)
0x180014c38  mov     rdi, rax
0x180014c3b  cmp     r15, rax
0x180014c3e  jz      short loc_180014C6B
0x180014c40  mov     rcx, r15
0x180014c43  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180014c48  mov     rcx, [rdi]
0x180014c4b  mov     [r15], rcx
0x180014c4e  mov     rcx, [rdi+8]
0x180014c52  mov     [r15+8], rcx
0x180014c56  mov     rcx, [rdi+10h]
0x180014c5a  mov     [r15+10h], rcx
0x180014c5e  xor     eax, eax
0x180014c60  mov     [rdi], rax
0x180014c63  mov     [rdi+8], rax
0x180014c67  mov     [rdi+10h], rax
0x180014c6b  lea     rdx, [rdi+18h]
0x180014c6f  lea     rcx, [r15+18h]
0x180014c73  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180014c78  lea     rbx, [r15+38h]
0x180014c7c  lea     rdx, [rdi+38h]
0x180014c80  mov     rcx, rbx
0x180014c83  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180014c88  lea     rcx, [rbp+40h+var_B0]; this
0x180014c8c  call    ??1ApplicationIdentity@Broker@@QEAA@XZ; Broker::ApplicationIdentity::~ApplicationIdentity(void)
0x180014c91  mov     eax, [rsi+20h]
0x180014c94  mov     rcx, [rsp+140h+var_F0]
0x180014c99  mov     [rcx], eax
0x180014c9b  mov     r8, [r14]
0x180014c9e  cmp     [r14+8], r8
0x180014ca2  jz      short loc_180014CA8
0x180014ca4  mov     [r14+8], r8
0x180014ca8  add     r13, r12
0x180014cab  mov     [rsp+140h+pSid], r13
0x180014cb0  mov     r9, r12
0x180014cb3  lea     rdx, [rsp+140h+var_F0]
0x180014cb8  mov     rcx, r14
0x180014cbb  call    ??$insert@PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEAE1@Z; std::vector<uchar>::insert<uchar *,0>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,uchar *)
0x180014cc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180014cc7  test    byte ptr [rcx+1Ch], 1
0x180014ccb  jz      short loc_180014D10
0x180014ccd  cmp     byte ptr [rcx+19h], 5
0x180014cd1  jb      short loc_180014D10
0x180014cd3  mov     eax, [r14+8]
0x180014cd7  sub     eax, [r14]
0x180014cda  cmp     qword ptr [rbx+18h], 7
0x180014cdf  jbe     short loc_180014CE4
0x180014ce1  mov     rbx, [rbx]
0x180014ce4  mov     edx, 13h
0x180014ce9  mov     dword ptr [rsp+140h+var_110], eax; char
0x180014ced  mov     [rsp+140h+var_118], rbx; __int64
0x180014cf2  mov     rax, [r15]
0x180014cf5  mov     [rsp+140h+pSid], rax; pSid
0x180014cfa  mov     r9, [rsp+140h+var_E0]
0x180014cff  lea     r8, WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids
0x180014d06  mov     rcx, [rcx+10h]; LoggerHandle
0x180014d0a  call    WPP_SF__guid__sid_Sd
0x180014d0f  nop
0x180014d10  lea     rcx, [rsp+140h+var_100]; this
0x180014d15  call    ??1BiLayerMemory@BILayer@Broker@@QEAA@XZ; Broker::BILayer::BiLayerMemory::~BiLayerMemory(void)
0x180014d1a  mov     rcx, [rbp+40h+var_50]
0x180014d1e  xor     rcx, rsp; StackCookie
0x180014d21  call    __security_check_cookie
0x180014d26  add     rsp, 108h
0x180014d2d  pop     r15
0x180014d2f  pop     r14
0x180014d31  pop     r13
0x180014d33  pop     r12
0x180014d35  pop     rdi
0x180014d36  pop     rsi
0x180014d37  pop     rbx
0x180014d38  pop     rbp
0x180014d39  retn
```
