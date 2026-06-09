# MicrodomImplementation::CStringpoolCache::AttachToStringPool(_MICRODOM_STRINGPOOL_HEADER const *)

- ea: `0x180054598`
- end: `0x1800546e6`
- name: `?AttachToStringPool@CStringpoolCache@MicrodomImplementation@@QEAAJPEBU_MICRODOM_STRINGPOOL_HEADER@@@Z`
- size: `334`
- prototype: `__int64 __fastcall(MicrodomImplementation::CStringpoolCache *__hidden this, const struct _MICRODOM_STRINGPOOL_HEADER *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180057f58`

## callees

- `0x18001f4ac`
- `0x18001f554`
- `0x1800293a0`
- `0x1800542b0`
- `0x180054598`

## string_xrefs

- `0x1800545ca`: `onecore\base\xml\udom_microdom.cpp`
- `0x18005460d`: `onecore\base\xml\udom_microdom.cpp`
- `0x180054641`: `onecore\base\xml\udom_microdom.cpp`
- `0x1800545dd`: `MicrodomImplementation::CStringpoolCache::AttachToStringPool`
- `0x180054620`: `MicrodomImplementation::CStringpoolCache::AttachToStringPool`
- `0x180054658`: `MicrodomImplementation::CStringpoolCache::AttachToStringPool`

## pseudocode

```c
__int64 __fastcall MicrodomImplementation::CStringpoolCache::AttachToStringPool(
        MicrodomImplementation::CStringpoolCache *this,
        const struct _MICRODOM_STRINGPOOL_HEADER *a2)
{
  const char *v4; // rax
  char *v6; // rdx
  char *v7; // r8
  char *v8; // r11
  unsigned __int64 v9; // r9
  char *v10; // r10
  __int64 v11; // rcx
  __int64 v12; // rdx
  const char *v13; // [rsp+20h] [rbp-30h] BYREF
  const char *v14; // [rsp+28h] [rbp-28h]
  __int64 v15; // [rsp+30h] [rbp-20h]
  const char *v16; // [rsp+38h] [rbp-18h]
  int v17; // [rsp+40h] [rbp-10h] BYREF

  v17 = 0;
  if ( !a2 )
  {
    v15 = 4023;
    v13 = "onecore\\base\\xml\\udom_microdom.cpp";
    v14 = "MicrodomImplementation::CStringpoolCache::AttachToStringPool";
    v4 = "PoolHeader != 0";
LABEL_3:
    v16 = v4;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v17,
             &v13);
  }
  if ( *(_DWORD *)a2 != 1884513357 )
  {
    v15 = 4024;
    v13 = "onecore\\base\\xml\\udom_microdom.cpp";
    v14 = "MicrodomImplementation::CStringpoolCache::AttachToStringPool";
    v4 = "PoolHeader->Signature == ('pSdM')";
    goto LABEL_3;
  }
  if ( Windows::AutoVectorBase<Windows::VectorTraits<_LUTF8_STRING>,Windows::Auto<Windows::Vector<_LUTF8_STRING>>>::Allocate(
         this,
         *((unsigned int *)a2 + 2)) )
  {
    v6 = (char *)a2 + 12;
    v7 = (char *)a2 + *((unsigned int *)a2 + 1);
    v8 = (char *)a2 + 12;
    v9 = 0;
    while ( v6 < v7 && v9 < *((_QWORD *)this + 1) )
    {
      v10 = v6 + 1;
      if ( !*v6 )
      {
        v11 = 3 * v9;
        v12 = v6 - v8;
        ++v9;
        *(_QWORD *)(*(_QWORD *)this + 8 * v11 + 16) = v8;
        v8 = v10;
        *(_QWORD *)(*(_QWORD *)this + 8 * v11) = v12;
        *(_QWORD *)(*(_QWORD *)this + 8 * v11 + 8) = v12;
      }
      v6 = v10;
    }
    return 0;
  }
  else
  {
    v15 = 4026;
    v13 = "onecore\\base\\xml\\udom_microdom.cpp";
    v14 = "MicrodomImplementation::CStringpoolCache::AttachToStringPool";
    v16 = "m_Entries.Allocate(PoolHeader->TotalCount)";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(
             &v17,
             &v13);
  }
}

```

## disassembly

```asm
0x180054598  mov     [rsp-8+arg_10], rbx
0x18005459d  mov     [rsp-8+arg_18], rdi
0x1800545a2  push    rbp
0x1800545a3  mov     rbp, rsp
0x1800545a6  sub     rsp, 50h
0x1800545aa  mov     rax, cs:__security_cookie
0x1800545b1  xor     rax, rsp
0x1800545b4  mov     [rbp+var_8], rax
0x1800545b8  mov     [rbp+var_10], 0
0x1800545bf  mov     rbx, rdx
0x1800545c2  mov     rdi, rcx
0x1800545c5  test    rdx, rdx
0x1800545c8  jnz     short loc_180054605
0x1800545ca  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x1800545d1  mov     [rbp+var_20], 0FB7h
0x1800545d9  mov     [rbp+var_30], rax
0x1800545dd  lea     rax, aMicrodomimplem_16; "MicrodomImplementation::CStringpoolCach"...
0x1800545e4  mov     [rbp+var_28], rax
0x1800545e8  lea     rax, aPoolheader0; "PoolHeader != 0"
0x1800545ef  lea     rdx, [rbp+var_30]
0x1800545f3  mov     [rbp+var_18], rax
0x1800545f7  lea     rcx, [rbp+var_10]
0x1800545fb  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180054600  jmp     loc_1800546C9
0x180054605  cmp     dword ptr [rdx], 7053644Dh
0x18005460b  jz      short loc_180054634
0x18005460d  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180054614  mov     [rbp+var_20], 0FB8h
0x18005461c  mov     [rbp+var_30], rax
0x180054620  lea     rax, aMicrodomimplem_16; "MicrodomImplementation::CStringpoolCach"...
0x180054627  mov     [rbp+var_28], rax
0x18005462b  lea     rax, aPoolheaderSign; "PoolHeader->Signature == ('pSdM')"
0x180054632  jmp     short loc_1800545EF
0x180054634  mov     edx, [rdx+8]
0x180054637  call    ?Allocate@?$AutoVectorBase@V?$VectorTraits@U_LUTF8_STRING@@@Windows@@V?$Auto@U?$Vector@U_LUTF8_STRING@@@Windows@@@2@@Windows@@QEAAPEAU_LUTF8_STRING@@_K@Z; Windows::AutoVectorBase<Windows::VectorTraits<_LUTF8_STRING>,Windows::Auto<Windows::Vector<_LUTF8_STRING>>>::Allocate(unsigned __int64)
0x18005463c  test    rax, rax
0x18005463f  jnz     short loc_180054679
0x180054641  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180054648  mov     [rbp+var_20], 0FBAh
0x180054650  mov     [rbp+var_30], rax
0x180054654  lea     rdx, [rbp+var_30]
0x180054658  lea     rax, aMicrodomimplem_16; "MicrodomImplementation::CStringpoolCach"...
0x18005465f  mov     [rbp+var_28], rax
0x180054663  lea     rcx, [rbp+var_10]
0x180054667  lea     rax, aMEntriesAlloca; "m_Entries.Allocate(PoolHeader->TotalCou"...
0x18005466e  mov     [rbp+var_18], rax
0x180054672  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180054677  jmp     short loc_1800546C9
0x180054679  mov     r8d, [rbx+4]
0x18005467d  lea     rdx, [rbx+0Ch]
0x180054681  add     r8, rbx
0x180054684  mov     r11, rdx
0x180054687  xor     r9d, r9d
0x18005468a  jmp     short loc_1800546C2
0x18005468c  cmp     r9, [rdi+8]
0x180054690  jnb     short loc_1800546C7
0x180054692  cmp     byte ptr [rdx], 0
0x180054695  lea     r10, [rdx+1]
0x180054699  jnz     short loc_1800546BF
0x18005469b  mov     rax, [rdi]
0x18005469e  lea     rcx, [r9+r9*2]
0x1800546a2  sub     rdx, r11
0x1800546a5  inc     r9
0x1800546a8  mov     [rax+rcx*8+10h], r11
0x1800546ad  mov     r11, r10
0x1800546b0  mov     rax, [rdi]
0x1800546b3  mov     [rax+rcx*8], rdx
0x1800546b7  mov     rax, [rdi]
0x1800546ba  mov     [rax+rcx*8+8], rdx
0x1800546bf  mov     rdx, r10
0x1800546c2  cmp     rdx, r8
0x1800546c5  jb      short loc_18005468C
0x1800546c7  xor     eax, eax
0x1800546c9  mov     rcx, [rbp+var_8]
0x1800546cd  xor     rcx, rsp; StackCookie
0x1800546d0  call    __security_check_cookie
0x1800546d5  mov     rbx, [rsp+50h+arg_10]
0x1800546da  mov     rdi, [rsp+50h+arg_18]
0x1800546df  add     rsp, 50h
0x1800546e3  pop     rbp
0x1800546e4  retn
```
