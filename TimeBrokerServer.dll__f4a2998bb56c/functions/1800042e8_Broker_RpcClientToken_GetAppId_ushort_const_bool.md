# Broker::RpcClientToken::GetAppId(ushort const *,bool)

- ea: `0x1800042e8`
- end: `0x180004480`
- name: `?GetAppId@RpcClientToken@Broker@@QEAA?AUApplicationIdentity@2@PEBG_N@Z`
- size: `408`
- prototype: `Broker::ApplicationIdentity *__fastcall(__int64, Broker::ApplicationIdentity *, const unsigned __int16 *)`
- caller_count: `8`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003700`
- `0x180003ac0`
- `0x180004be0`
- `0x18000ef50`
- `0x1800118e0`
- `0x180011c20`
- `0x1800147b0`
- `0x1800149d0`

## callees

- `0x1800042e8`
- `0x180004488`
- `0x1800044a0`
- `0x18000461c`
- `0x180004818`
- `0x180004b70`
- `0x18000ca68`
- `0x180010b34`
- `0x18001154c`
- `0x18001157c`
- `0x180012dd0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800043d4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800043d4`

## pseudocode

```c
Broker::ApplicationIdentity *__fastcall Broker::RpcClientToken::GetAppId(
        __int64 a1,
        Broker::ApplicationIdentity *a2,
        const unsigned __int16 *a3)
{
  __int64 PackageFullName; // rsi
  void *v7; // rsi
  DWORD LengthSid; // eax
  __int128 v10; // [rsp+40h] [rbp-19h] BYREF
  __m128i si128; // [rsp+50h] [rbp-9h]
  _QWORD v12[3]; // [rsp+60h] [rbp+7h] BYREF
  unsigned __int64 v13; // [rsp+78h] [rbp+1Fh]

  v10 = 0;
  si128 = 0;
  std::wstring::_Construct_empty(&v10);
  PackageFullName = Broker::RpcClientToken::GetPackageFullName(a1, v12);
  if ( &v10 != (__int128 *)PackageFullName )
  {
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(v10, 2 * si128.m128i_i64[1] + 2);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v10) = 0;
    v10 = *(_OWORD *)PackageFullName;
    si128 = *(__m128i *)(PackageFullName + 16);
    *(_QWORD *)(PackageFullName + 16) = 0;
    *(_QWORD *)(PackageFullName + 24) = 7;
    *(_WORD *)PackageFullName = 0;
  }
  if ( v13 > 7 )
    std::_Deallocate<16>(v12[0], 2 * v13 + 2);
  if ( si128.m128i_i64[0] )
  {
    a3 = (const unsigned __int16 *)&v10;
    if ( si128.m128i_i64[1] > 7uLL )
      a3 = (const unsigned __int16 *)v10;
  }
  v7 = *(void **)Broker::RpcClientToken::GetUserSid(a1, v12);
  std::vector<_GUID>::vector<_GUID>(a2);
  std::wstring::wstring((char *)a2 + 24);
  std::wstring::wstring((char *)a2 + 56);
  if ( v7 )
  {
    LengthSid = GetLengthSid(v7);
    std::vector<unsigned char>::_Insert_counted_range<unsigned char *>(a2, *(_QWORD *)a2, v7, LengthSid);
  }
  if ( a3 )
    Broker::ApplicationIdentity::SetPackageFullName(a2, a3);
  std::vector<unsigned char>::_Tidy(v12);
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v10, 2 * si128.m128i_i64[1] + 2);
  return a2;
}

```

## disassembly

```asm
0x1800042e8  push    rbp
0x1800042ea  push    rbx
0x1800042eb  push    rsi
0x1800042ec  push    rdi
0x1800042ed  push    r14
0x1800042ef  lea     rbp, [rsp-37h]
0x1800042f4  sub     rsp, 90h
0x1800042fb  mov     rax, cs:__security_cookie
0x180004302  xor     rax, rsp
0x180004305  mov     [rbp+57h+var_30], rax
0x180004309  mov     rdi, r8
0x18000430c  mov     rbx, rdx
0x18000430f  mov     r14, rcx
0x180004312  mov     [rbp+57h+var_80], rdx
0x180004316  xorps   xmm0, xmm0
0x180004319  movups  [rbp+57h+var_70], xmm0
0x18000431d  xorps   xmm1, xmm1
0x180004320  movdqu  [rbp+57h+var_60], xmm1
0x180004325  lea     rcx, [rbp+57h+var_70]
0x180004329  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000432e  nop
0x18000432f  lea     rdx, [rbp+57h+var_50]
0x180004333  mov     rcx, r14
0x180004336  call    ?GetPackageFullName@RpcClientToken@Broker@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Broker::RpcClientToken::GetPackageFullName(void)
0x18000433b  mov     rsi, rax
0x18000433e  lea     rax, [rbp+57h+var_70]
0x180004342  cmp     rax, rsi
0x180004345  jz      short loc_180004386
0x180004347  mov     rdx, qword ptr [rbp+57h+var_60+8]
0x18000434b  cmp     rdx, 7
0x18000434f  ja      loc_180004441
0x180004355  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18000435d  movdqu  [rbp+57h+var_60], xmm0
0x180004362  xor     eax, eax
0x180004364  mov     word ptr [rbp+57h+var_70], ax
0x180004368  movups  xmm0, xmmword ptr [rsi]
0x18000436b  movups  [rbp+57h+var_70], xmm0
0x18000436f  movups  xmm1, xmmword ptr [rsi+10h]
0x180004373  movups  [rbp+57h+var_60], xmm1
0x180004377  mov     [rsi+10h], rax
0x18000437b  mov     qword ptr [rsi+18h], 7
0x180004383  mov     [rsi], ax
0x180004386  mov     rdx, [rbp+57h+var_38]
0x18000438a  cmp     rdx, 7
0x18000438e  ja      loc_180004457
0x180004394  cmp     qword ptr [rbp+57h+var_60], 0
0x180004399  jnz     loc_18000442E
0x18000439f  lea     rdx, [rbp+57h+var_50]
0x1800043a3  mov     rcx, r14
0x1800043a6  call    ?GetUserSid@RpcClientToken@Broker@@AEAA?AV?$vector@EV?$allocator@E@std@@@std@@XZ; Broker::RpcClientToken::GetUserSid(void)
0x1800043ab  nop
0x1800043ac  mov     rsi, [rax]
0x1800043af  mov     rcx, rbx
0x1800043b2  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x1800043b7  nop
0x1800043b8  lea     rcx, [rbx+18h]
0x1800043bc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800043c1  nop
0x1800043c2  lea     rcx, [rbx+38h]
0x1800043c6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800043cb  nop
0x1800043cc  test    rsi, rsi
0x1800043cf  jz      short loc_1800043EB
0x1800043d1  mov     rcx, rsi; pSid
0x1800043d4  call    cs:__imp_GetLengthSid
0x1800043da  mov     r9d, eax
0x1800043dd  mov     r8, rsi
0x1800043e0  mov     rdx, [rbx]
0x1800043e3  mov     rcx, rbx
0x1800043e6  call    ??$_Insert_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEAE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,unsigned __int64)
0x1800043eb  test    rdi, rdi
0x1800043ee  jnz     short loc_180004421
0x1800043f0  lea     rcx, [rbp+57h+var_50]
0x1800043f4  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800043f9  nop
0x1800043fa  mov     rdx, qword ptr [rbp+57h+var_60+8]
0x1800043fe  cmp     rdx, 7
0x180004402  ja      short loc_18000446D
0x180004404  mov     rax, rbx
0x180004407  mov     rcx, [rbp+57h+var_30]
0x18000440b  xor     rcx, rsp; StackCookie
0x18000440e  call    __security_check_cookie
0x180004413  add     rsp, 90h
0x18000441a  pop     r14
0x18000441c  pop     rdi
0x18000441d  pop     rsi
0x18000441e  pop     rbx
0x18000441f  pop     rbp
0x180004420  retn
0x180004421  mov     rdx, rdi; unsigned __int16 *
0x180004424  mov     rcx, rbx; this
0x180004427  call    ?SetPackageFullName@ApplicationIdentity@Broker@@QEAAXQEBG@Z; Broker::ApplicationIdentity::SetPackageFullName(ushort const * const)
0x18000442c  jmp     short loc_1800043F0
0x18000442e  lea     rdi, [rbp+57h+var_70]
0x180004432  cmp     qword ptr [rbp+57h+var_60+8], 7
0x180004437  cmova   rdi, qword ptr [rbp+57h+var_70]
0x18000443c  jmp     loc_18000439F
0x180004441  lea     rdx, ds:2[rdx*2]
0x180004449  mov     rcx, qword ptr [rbp+57h+var_70]
0x18000444d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180004452  jmp     loc_180004355
0x180004457  lea     rdx, ds:2[rdx*2]
0x18000445f  mov     rcx, [rbp+57h+var_50]
0x180004463  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180004468  jmp     loc_180004394
0x18000446d  lea     rdx, ds:2[rdx*2]
0x180004475  mov     rcx, qword ptr [rbp+57h+var_70]
0x180004479  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000447e  jmp     short loc_180004404
```
