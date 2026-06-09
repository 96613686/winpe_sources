# Broker::RpcClientToken::GetAppId(ushort const *,bool)

- ea: `0x180007350`
- end: `0x1800074c6`
- name: `?GetAppId@RpcClientToken@Broker@@QEAA?AUApplicationIdentity@2@PEBG_N@Z`
- size: `374`
- prototype: `struct Broker::ApplicationIdentity __high(const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001ab8c`

## callees

- `0x180004e38`
- `0x180006b30`
- `0x180007350`
- `0x1800074d0`
- `0x180007708`
- `0x18001177c`
- `0x180014898`
- `0x180015af0`
- `0x180015b58`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void *__fastcall Broker::RpcClientToken::GetAppId(__int64 a1, void *a2)
{
  __m128i *PackageFullName; // rbx
  const unsigned __int16 *v5; // rbx
  void **UserSid; // rax
  void *v7; // rcx
  void *v9; // [rsp+20h] [rbp-29h] BYREF
  unsigned __int64 v10; // [rsp+30h] [rbp-19h] BYREF
  unsigned __int16 *v11[2]; // [rsp+40h] [rbp-9h] BYREF
  __m128i si128; // [rsp+50h] [rbp+7h]
  void *v13[2]; // [rsp+60h] [rbp+17h] BYREF
  __int64 v14; // [rsp+70h] [rbp+27h]
  unsigned __int64 v15; // [rsp+78h] [rbp+2Fh]

  v9 = a2;
  *(_OWORD *)v11 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v11[0]) = 0;
  PackageFullName = (__m128i *)Broker::RpcClientToken::GetPackageFullName(a1, v13);
  if ( v11 != (unsigned __int16 **)PackageFullName )
  {
    std::wstring::_Tidy_deallocate(v11);
    *(__m128i *)v11 = *PackageFullName;
    si128 = PackageFullName[1];
    PackageFullName[1].m128i_i64[0] = 0;
    PackageFullName[1].m128i_i64[1] = 7;
    PackageFullName->m128i_i16[0] = 0;
  }
  if ( v15 > 7 )
    std::_Deallocate<16>(v13[0], 2 * v15 + 2);
  if ( si128.m128i_i64[0] )
  {
    v5 = (const unsigned __int16 *)v11;
    if ( si128.m128i_i64[1] > 7uLL )
      v5 = v11[0];
  }
  else
  {
    v5 = 0;
  }
  UserSid = (void **)Broker::RpcClientToken::GetUserSid(a1, v13);
  Broker::ApplicationIdentity::ApplicationIdentity((Broker::ApplicationIdentity *)a2, *UserSid, v5);
  v7 = v13[0];
  if ( v13[0] )
  {
    v10 = v14 - (unsigned __int64)v13[0];
    v9 = v13[0];
    if ( v14 - (unsigned __int64)v13[0] >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v9, &v10);
      v7 = v9;
    }
    operator delete(v7);
  }
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v11[0], 2 * si128.m128i_i64[1] + 2);
  return a2;
}

```

## disassembly

```asm
0x180007350  mov     [rsp-8+arg_10], rbx
0x180007355  push    rbp
0x180007356  push    rsi
0x180007357  push    rdi
0x180007358  lea     rbp, [rsp-47h]
0x18000735d  sub     rsp, 90h
0x180007364  mov     rax, cs:__security_cookie
0x18000736b  xor     rax, rsp
0x18000736e  mov     [rbp+57h+var_20], rax
0x180007372  mov     rdi, rdx
0x180007375  mov     rsi, rcx
0x180007378  mov     [rbp+57h+var_80], rdx
0x18000737c  xorps   xmm0, xmm0
0x18000737f  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x180007383  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000738b  movdqu  [rbp+57h+var_50], xmm1
0x180007390  xor     eax, eax
0x180007392  mov     word ptr [rbp+57h+var_60], ax
0x180007396  lea     rdx, [rbp+57h+var_40]
0x18000739a  call    ?GetPackageFullName@RpcClientToken@Broker@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Broker::RpcClientToken::GetPackageFullName(void)
0x18000739f  mov     rbx, rax
0x1800073a2  lea     rax, [rbp+57h+var_60]
0x1800073a6  cmp     rax, rbx
0x1800073a9  jnz     loc_180007479
0x1800073af  mov     rdx, [rbp+57h+var_28]
0x1800073b3  cmp     rdx, 7
0x1800073b7  ja      loc_180007449
0x1800073bd  cmp     qword ptr [rbp+57h+var_50], 0
0x1800073c2  jz      loc_180007472
0x1800073c8  lea     rbx, [rbp+57h+var_60]
0x1800073cc  cmp     qword ptr [rbp+57h+var_50+8], 7
0x1800073d1  cmova   rbx, [rbp+57h+var_60]
0x1800073d6  lea     rdx, [rbp+57h+var_40]
0x1800073da  mov     rcx, rsi
0x1800073dd  call    ?GetUserSid@RpcClientToken@Broker@@AEAA?AV?$vector@EV?$allocator@E@std@@@std@@XZ; Broker::RpcClientToken::GetUserSid(void)
0x1800073e2  nop
0x1800073e3  mov     r8, rbx; unsigned __int16 *
0x1800073e6  mov     rdx, [rax]; void *
0x1800073e9  mov     rcx, rdi; this
0x1800073ec  call    ??0ApplicationIdentity@Broker@@QEAA@PEAXQEBG@Z; Broker::ApplicationIdentity::ApplicationIdentity(void *,ushort const * const)
0x1800073f1  nop
0x1800073f2  mov     rcx, [rbp+57h+var_40]; void *
0x1800073f6  test    rcx, rcx
0x1800073f9  jz      short loc_18000741D
0x1800073fb  mov     rdx, [rbp+57h+var_30]
0x1800073ff  sub     rdx, rcx; unsigned __int64
0x180007402  mov     [rbp+57h+var_70], rdx
0x180007406  mov     [rbp+57h+var_80], rcx
0x18000740a  cmp     rdx, 1000h
0x180007411  jnb     loc_1800074AB
0x180007417  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000741c  nop
0x18000741d  mov     rdx, qword ptr [rbp+57h+var_50+8]
0x180007421  cmp     rdx, 7
0x180007425  ja      short loc_18000745F
0x180007427  mov     rax, rdi
0x18000742a  mov     rcx, [rbp+57h+var_20]
0x18000742e  xor     rcx, rsp; StackCookie
0x180007431  call    __security_check_cookie
0x180007436  mov     rbx, [rsp+0A0h+arg_10]
0x18000743e  add     rsp, 90h
0x180007445  pop     rdi
0x180007446  pop     rsi
0x180007447  pop     rbp
0x180007448  retn
0x180007449  lea     rdx, ds:2[rdx*2]
0x180007451  mov     rcx, [rbp+57h+var_40]
0x180007455  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000745a  jmp     loc_1800073BD
0x18000745f  lea     rdx, ds:2[rdx*2]
0x180007467  mov     rcx, [rbp+57h+var_60]
0x18000746b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180007470  jmp     short loc_180007427
0x180007472  xor     ebx, ebx
0x180007474  jmp     loc_1800073D6
0x180007479  lea     rcx, [rbp+57h+var_60]
0x18000747d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180007482  movups  xmm0, xmmword ptr [rbx]
0x180007485  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x180007489  movups  xmm1, xmmword ptr [rbx+10h]
0x18000748d  movups  [rbp+57h+var_50], xmm1
0x180007491  mov     qword ptr [rbx+10h], 0
0x180007499  mov     qword ptr [rbx+18h], 7
0x1800074a1  xor     eax, eax
0x1800074a3  mov     [rbx], ax
0x1800074a6  jmp     loc_1800073AF
0x1800074ab  lea     rdx, [rbp+57h+var_70]; unsigned __int64 *
0x1800074af  lea     rcx, [rbp+57h+var_80]; void **
0x1800074b3  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x1800074b8  mov     rdx, [rbp+57h+var_70]
0x1800074bc  mov     rcx, [rbp+57h+var_80]
0x1800074c0  jmp     loc_180007417
```
