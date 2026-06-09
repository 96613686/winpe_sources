# MicrodomImplementation::CStringpoolCache::AttachToStringPool(_MICRODOM_STRINGPOOL_HEADER const *)

- ea: `0x1800569dc`
- end: `0x180056b2a`
- name: `?AttachToStringPool@CStringpoolCache@MicrodomImplementation@@QEAAJPEBU_MICRODOM_STRINGPOOL_HEADER@@@Z`
- size: `334`
- prototype: `__int64 __fastcall(MicrodomImplementation::CStringpoolCache *__hidden this, const struct _MICRODOM_STRINGPOOL_HEADER *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180058efc`

## callees

- `0x18001f1d8`
- `0x1800217cc`
- `0x18002d2b0`
- `0x180056710`
- `0x1800569dc`

## string_xrefs

- `0x180056a0e`: `onecore\base\xml\udom_microdom.cpp`
- `0x180056a51`: `onecore\base\xml\udom_microdom.cpp`
- `0x180056a85`: `onecore\base\xml\udom_microdom.cpp`
- `0x180056a21`: `MicrodomImplementation::CStringpoolCache::AttachToStringPool`
- `0x180056a64`: `MicrodomImplementation::CStringpoolCache::AttachToStringPool`
- `0x180056a9c`: `MicrodomImplementation::CStringpoolCache::AttachToStringPool`

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
0x1800569dc  mov     [rsp-8+arg_10], rbx
0x1800569e1  mov     [rsp-8+arg_18], rdi
0x1800569e6  push    rbp
0x1800569e7  mov     rbp, rsp
0x1800569ea  sub     rsp, 50h
0x1800569ee  mov     rax, cs:__security_cookie
0x1800569f5  xor     rax, rsp
0x1800569f8  mov     [rbp+var_8], rax
0x1800569fc  mov     [rbp+var_10], 0
0x180056a03  mov     rbx, rdx
0x180056a06  mov     rdi, rcx
0x180056a09  test    rdx, rdx
0x180056a0c  jnz     short loc_180056A49
0x180056a0e  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180056a15  mov     [rbp+var_20], 0FB7h
0x180056a1d  mov     [rbp+var_30], rax
0x180056a21  lea     rax, aMicrodomimplem_16; "MicrodomImplementation::CStringpoolCach"...
0x180056a28  mov     [rbp+var_28], rax
0x180056a2c  lea     rax, aPoolheader0; "PoolHeader != 0"
0x180056a33  lea     rdx, [rbp+var_30]
0x180056a37  mov     [rbp+var_18], rax
0x180056a3b  lea     rcx, [rbp+var_10]
0x180056a3f  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180056a44  jmp     loc_180056B0D
0x180056a49  cmp     dword ptr [rdx], 7053644Dh
0x180056a4f  jz      short loc_180056A78
0x180056a51  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180056a58  mov     [rbp+var_20], 0FB8h
0x180056a60  mov     [rbp+var_30], rax
0x180056a64  lea     rax, aMicrodomimplem_16; "MicrodomImplementation::CStringpoolCach"...
0x180056a6b  mov     [rbp+var_28], rax
0x180056a6f  lea     rax, aPoolheaderSign; "PoolHeader->Signature == ('pSdM')"
0x180056a76  jmp     short loc_180056A33
0x180056a78  mov     edx, [rdx+8]
0x180056a7b  call    ?Allocate@?$AutoVectorBase@V?$VectorTraits@U_LUTF8_STRING@@@Windows@@V?$Auto@U?$Vector@U_LUTF8_STRING@@@Windows@@@2@@Windows@@QEAAPEAU_LUTF8_STRING@@_K@Z; Windows::AutoVectorBase<Windows::VectorTraits<_LUTF8_STRING>,Windows::Auto<Windows::Vector<_LUTF8_STRING>>>::Allocate(unsigned __int64)
0x180056a80  test    rax, rax
0x180056a83  jnz     short loc_180056ABD
0x180056a85  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180056a8c  mov     [rbp+var_20], 0FBAh
0x180056a94  mov     [rbp+var_30], rax
0x180056a98  lea     rdx, [rbp+var_30]
0x180056a9c  lea     rax, aMicrodomimplem_16; "MicrodomImplementation::CStringpoolCach"...
0x180056aa3  mov     [rbp+var_28], rax
0x180056aa7  lea     rcx, [rbp+var_10]
0x180056aab  lea     rax, aMEntriesAlloca; "m_Entries.Allocate(PoolHeader->TotalCou"...
0x180056ab2  mov     [rbp+var_18], rax
0x180056ab6  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180056abb  jmp     short loc_180056B0D
0x180056abd  mov     r8d, [rbx+4]
0x180056ac1  lea     rdx, [rbx+0Ch]
0x180056ac5  add     r8, rbx
0x180056ac8  mov     r11, rdx
0x180056acb  xor     r9d, r9d
0x180056ace  jmp     short loc_180056B06
0x180056ad0  cmp     r9, [rdi+8]
0x180056ad4  jnb     short loc_180056B0B
0x180056ad6  cmp     byte ptr [rdx], 0
0x180056ad9  lea     r10, [rdx+1]
0x180056add  jnz     short loc_180056B03
0x180056adf  mov     rax, [rdi]
0x180056ae2  lea     rcx, [r9+r9*2]
0x180056ae6  sub     rdx, r11
0x180056ae9  inc     r9
0x180056aec  mov     [rax+rcx*8+10h], r11
0x180056af1  mov     r11, r10
0x180056af4  mov     rax, [rdi]
0x180056af7  mov     [rax+rcx*8], rdx
0x180056afb  mov     rax, [rdi]
0x180056afe  mov     [rax+rcx*8+8], rdx
0x180056b03  mov     rdx, r10
0x180056b06  cmp     rdx, r8
0x180056b09  jb      short loc_180056AD0
0x180056b0b  xor     eax, eax
0x180056b0d  mov     rcx, [rbp+var_8]
0x180056b11  xor     rcx, rsp; StackCookie
0x180056b14  call    __security_check_cookie
0x180056b19  mov     rbx, [rsp+50h+arg_10]
0x180056b1e  mov     rdi, [rsp+50h+arg_18]
0x180056b23  add     rsp, 50h
0x180056b27  pop     rbp
0x180056b28  retn
```
