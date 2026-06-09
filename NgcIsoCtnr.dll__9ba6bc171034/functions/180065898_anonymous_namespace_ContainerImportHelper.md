# _anonymous_namespace_::ContainerImportHelper

- ea: `0x180065898`
- end: `0x180065ac4`
- name: `_anonymous_namespace_::ContainerImportHelper`
- size: `556`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180068294`
- `0x180068340`
- `0x180068410`

## callees

- `0x18000d62c`
- `0x18005c1c4`
- `0x18005c3a8`
- `0x18005cd48`
- `0x180064784`
- `0x1800647a4`
- `0x180065898`
- `0x180068998`

## string_xrefs

- `0x1800658d1`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\client\ngcisotrustlet.cpp`
- `0x180065914`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\client\ngcisotrustlet.cpp`
- `0x18006592c`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\client\ngcisotrustlet.cpp`
- `0x1800659be`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\client\ngcisotrustlet.cpp`
- `0x180065a40`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\client\ngcisotrustlet.cpp`
- `0x180065a72`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\client\ngcisotrustlet.cpp`
- `0x180065a8a`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\client\ngcisotrustlet.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall anonymous_namespace_::ContainerImportHelper(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7)
{
  unsigned int v7; // edi
  unsigned int v11; // ebx
  int v12; // eax
  int v13; // ecx
  unsigned int v14; // ebx
  int v15; // esi
  int v16; // eax
  unsigned int v17; // edi
  int v18; // eax
  int v19; // ecx
  unsigned __int64 v20; // r9
  __int64 v21; // rdx
  int v22; // eax
  int v24; // [rsp+20h] [rbp-60h]
  int v25; // [rsp+20h] [rbp-60h]
  int v26; // [rsp+20h] [rbp-60h]
  int v27; // [rsp+20h] [rbp-60h]
  int v28; // [rsp+20h] [rbp-60h]
  int v29; // [rsp+40h] [rbp-40h] BYREF
  int v30[2]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v31; // [rsp+50h] [rbp-30h] BYREF
  __int64 v32; // [rsp+58h] [rbp-28h] BYREF
  __int64 v33; // [rsp+60h] [rbp-20h] BYREF
  __int64 v34; // [rsp+68h] [rbp-18h] BYREF
  __int64 v35; // [rsp+70h] [rbp-10h] BYREF
  __int64 v36; // [rsp+78h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  unsigned int v38; // [rsp+C8h] [rbp+48h] BYREF

  v7 = a4;
  if ( a4 )
  {
    v32 = 0;
    *(_QWORD *)v30 = &v32;
    v29 = a4;
    v12 = RpcCallWithBind<long (&)(void *,unsigned long,unsigned char * *),unsigned long &,unsigned char * * &>(
            a1,
            &v29,
            v30);
    v11 = v12;
    if ( v12 >= 0 )
    {
      v14 = 0;
      v38 = v7;
      while ( 1 )
      {
        v15 = 60000;
        if ( v7 < 0xEA60 )
          v15 = v7;
        *(_QWORD *)v30 = &v38;
        v33 = a3 + v14;
        v29 = v15;
        v34 = v32;
        v16 = RpcCallWithBind<long (&)(void *,unsigned char *,unsigned long,unsigned char const *,unsigned long *),unsigned char * &,unsigned long &,unsigned char const * &,unsigned long * &>(
                v13,
                (unsigned int)&v34,
                (unsigned int)&v29,
                (unsigned int)&v33,
                (__int64)v30);
        v17 = v16;
        if ( v16 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x89,
            (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\client\\ngcisotrustlet.cpp",
            (const char *)(unsigned int)v16,
            v26);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x45A,
            (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\client\\ngcisotrustlet.cpp",
            (const char *)v17,
            v28);
          v11 = v17;
          goto LABEL_18;
        }
        v7 = v38;
        if ( !v38 )
          break;
        v14 += v15;
      }
      v31 = 0;
      v18 = anonymous_namespace_::NgcIsoOpenContainer(a1, &v31);
      v11 = v18;
      if ( v18 < 0 )
      {
        v20 = (unsigned int)v18;
        v21 = 1119;
LABEL_13:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v21,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\client\\ngcisotrustlet.cpp",
          (const char *)v20,
          v26);
        wil::details::unique_storage_wil::details::resource_policy_unsigned_char___long____cdecl___unsigned_char______anonymous_namespace_::NgcIsoCloseContainer_wistd::integral_constant_unsigned___int64_0__unsigned_char___unsigned_char___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_unsigned_char___long____cdecl___unsigned_char______anonymous_namespace_::NgcIsoCloseContainer_wistd::integral_constant_unsigned___int64_0__unsigned_char___unsigned_char___0_std::nullptr_t___(&v31);
        goto LABEL_18;
      }
      v35 = v32;
      v36 = v31;
      v34 = a7;
      v33 = a5;
      v29 = a6;
      v30[0] = a2;
      v22 = RpcCallWithBind<long (&)(void *,unsigned char *,unsigned char *,enum __MIDL___MIDL_itf_ngcisorpc_0000_0000_0001,unsigned long,unsigned char const *,int *),unsigned char * &,unsigned char * &,enum __MIDL___MIDL_itf_ngcisorpc_0000_0000_0001 &,unsigned long &,unsigned char const * &,int * &>(
              v19,
              (unsigned int)&v36,
              (unsigned int)&v35,
              (unsigned int)v30,
              (__int64)&v29,
              (__int64)&v33,
              (__int64)&v34);
      v11 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9C,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\client\\ngcisotrustlet.cpp",
          (const char *)(unsigned int)v22,
          v27);
        v20 = v11;
        v21 = 1127;
        goto LABEL_13;
      }
      wil::details::unique_storage_wil::details::resource_policy_unsigned_char___long____cdecl___unsigned_char______anonymous_namespace_::NgcIsoCloseContainer_wistd::integral_constant_unsigned___int64_0__unsigned_char___unsigned_char___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_unsigned_char___long____cdecl___unsigned_char______anonymous_namespace_::NgcIsoCloseContainer_wistd::integral_constant_unsigned___int64_0__unsigned_char___unsigned_char___0_std::nullptr_t___(&v31);
      v11 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7A,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\client\\ngcisotrustlet.cpp",
        (const char *)(unsigned int)v12,
        v24);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x44D,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\client\\ngcisotrustlet.cpp",
        (const char *)v11,
        v25);
    }
LABEL_18:
    wil::details::unique_storage_wil::details::resource_policy_unsigned_char___long____cdecl___unsigned_char______anonymous_namespace_::NgcIsoCloseBuffer_wistd::integral_constant_unsigned___int64_0__unsigned_char___unsigned_char___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_unsigned_char___long____cdecl___unsigned_char______anonymous_namespace_::NgcIsoCloseBuffer_wistd::integral_constant_unsigned___int64_0__unsigned_char___unsigned_char___0_std::nullptr_t___(&v32);
  }
  else
  {
    v11 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x44A,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\client\\ngcisotrustlet.cpp",
      (const char *)0x80070057LL,
      v24);
  }
  return v11;
}

```

## disassembly

```asm
0x180065898  mov     [rsp-28h+arg_0], rbx
0x18006589d  mov     [rsp-28h+arg_8], rsi
0x1800658a2  push    rbp
0x1800658a3  push    rdi
0x1800658a4  push    r12
0x1800658a6  push    r14
0x1800658a8  push    r15
0x1800658aa  mov     rbp, rsp
0x1800658ad  sub     rsp, 80h
0x1800658b4  mov     rdi, r9
0x1800658b7  mov     r12, r8
0x1800658ba  mov     r15d, edx
0x1800658bd  mov     r14, rcx
0x1800658c0  test    r9, r9
0x1800658c3  jnz     short loc_1800658E7
0x1800658c5  mov     rcx, [rbp+28h]; this
0x1800658c9  mov     ebx, 80070057h
0x1800658ce  mov     r9d, ebx; char *
0x1800658d1  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1800658d8  mov     edx, 44Ah; void *
0x1800658dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800658e2  jmp     loc_180065AA6
0x1800658e7  mov     [rbp+var_28], 0
0x1800658ef  lea     rax, [rbp+var_28]
0x1800658f3  mov     qword ptr [rbp+var_38], rax
0x1800658f7  mov     [rbp+var_40], edi
0x1800658fa  lea     r8, [rbp+var_38]
0x1800658fe  lea     rdx, [rbp+var_40]
0x180065902  call    ??$RpcCallWithBind@A6AJPEAXKPEAPEAE@ZAEAKAEAPEAPEAE@@YAJA6AJPEAXKPEAPEAE@ZAEAKAEAPEAPEAE@Z; RpcCallWithBind<long (&)(void *,ulong,uchar * *),ulong &,uchar * * &>(long (&)(void *,ulong,uchar * *),ulong &,uchar * * &)
0x180065907  mov     ebx, eax
0x180065909  test    eax, eax
0x18006590b  jns     short loc_180065942
0x18006590d  mov     rcx, [rbp+28h]; this
0x180065911  mov     r9d, eax; char *
0x180065914  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18006591b  mov     edx, 7Ah ; 'z'; void *
0x180065920  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065925  mov     rcx, [rbp+28h]; this
0x180065929  mov     r9d, ebx; char *
0x18006592c  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180065933  mov     edx, 44Dh; void *
0x180065938  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006593d  jmp     loc_180065A9D
0x180065942  xor     ebx, ebx
0x180065944  mov     [rbp+arg_18], edi
0x180065947  mov     esi, 0EA60h
0x18006594c  cmp     edi, esi
0x18006594e  cmovb   esi, edi
0x180065951  lea     rax, [rbp+arg_18]
0x180065955  mov     qword ptr [rbp+var_38], rax
0x180065959  mov     eax, ebx
0x18006595b  add     rax, r12
0x18006595e  mov     [rbp+var_20], rax
0x180065962  mov     [rbp+var_40], esi
0x180065965  mov     rax, [rbp+var_28]
0x180065969  mov     [rbp+var_18], rax
0x18006596d  lea     rax, [rbp+var_38]
0x180065971  mov     qword ptr [rsp+80h+var_60], rax; int
0x180065976  lea     r9, [rbp+var_20]
0x18006597a  lea     r8, [rbp+var_40]
0x18006597e  lea     rdx, [rbp+var_18]
0x180065982  call    ??$RpcCallWithBind@A6AJPEAXPEAEKPEBEPEAK@ZAEAPEAEAEAKAEAPEBEAEAPEAK@@YAJA6AJPEAXPEAEKPEBEPEAK@ZAEAPEAEAEAKAEAPEBEAEAPEAK@Z; RpcCallWithBind<long (&)(void *,uchar *,ulong,uchar const *,ulong *),uchar * &,ulong &,uchar const * &,ulong * &>(long (&)(void *,uchar *,ulong,uchar const *,ulong *),uchar * &,ulong &,uchar const * &,ulong * &)
0x180065987  mov     edi, eax
0x180065989  test    eax, eax
0x18006598b  js      loc_180065A6B
0x180065991  mov     edi, [rbp+arg_18]
0x180065994  test    edi, edi
0x180065996  jz      short loc_18006599C
0x180065998  add     ebx, esi
0x18006599a  jmp     short loc_180065947
0x18006599c  mov     [rbp+var_30], 0
0x1800659a4  lea     rdx, [rbp+var_30]
0x1800659a8  mov     rcx, r14
0x1800659ab  call    _anonymous_namespace___NgcIsoOpenContainer
0x1800659b0  mov     ebx, eax
0x1800659b2  test    eax, eax
0x1800659b4  jns     short loc_1800659DD
0x1800659b6  mov     r9d, eax; char *
0x1800659b9  mov     edx, 45Fh; void *
0x1800659be  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1800659c5  mov     rcx, [rbp+28h]; this
0x1800659c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800659ce  nop
0x1800659cf  lea     rcx, [rbp+var_30]
0x1800659d3  call    wil__details__unique_storage_wil__details__resource_policy_unsigned_char___long____cdecl___unsigned_char______anonymous_namespace___NgcIsoCloseContainer_wistd__integral_constant_unsigned___int64_0__unsigned_char___unsigned_char___0_std__nullptr_t______unique_storage_wil__details__resource_policy_unsigned_char___long____cdecl___unsigned_char______anonymous_namespace___NgcIsoCloseContainer_wistd__integral_constant_unsigned___int64_0__unsigned_char___unsigned_char___0_std__nullptr_t___
0x1800659d8  jmp     loc_180065A9D
0x1800659dd  mov     rax, [rbp+var_28]
0x1800659e1  mov     [rbp+var_10], rax
0x1800659e5  mov     rax, [rbp+var_30]
0x1800659e9  mov     [rbp+var_8], rax
0x1800659ed  mov     rax, [rbp+arg_30]
0x1800659f1  mov     [rbp+var_18], rax
0x1800659f5  mov     rax, [rbp+arg_20]
0x1800659f9  mov     [rbp+var_20], rax
0x1800659fd  mov     eax, [rbp+arg_28]
0x180065a00  mov     [rbp+var_40], eax
0x180065a03  mov     [rbp+var_38], r15d
0x180065a07  lea     rax, [rbp+var_18]
0x180065a0b  mov     [rsp+80h+var_50], rax
0x180065a10  lea     rax, [rbp+var_20]
0x180065a14  mov     [rsp+80h+var_58], rax
0x180065a19  lea     rax, [rbp+var_40]
0x180065a1d  mov     qword ptr [rsp+80h+var_60], rax; int
0x180065a22  lea     r9, [rbp+var_38]
0x180065a26  lea     r8, [rbp+var_10]
0x180065a2a  lea     rdx, [rbp+var_8]
0x180065a2e  call    ??$RpcCallWithBind@A6AJPEAXPEAE1W4__MIDL___MIDL_itf_ngcisorpc_0000_0000_0001@@KPEBEPEAH@ZAEAPEAEAEAPEAEAEAW41@AEAKAEAPEBEAEAPEAH@@YAJA6AJPEAXPEAE1W4__MIDL___MIDL_itf_ngcisorpc_0000_0000_0001@@KPEBEPEAH@ZAEAPEAE6AEAW40@AEAKAEAPEBEAEAPEAH@Z; RpcCallWithBind<long (&)(void *,uchar *,uchar *,__MIDL___MIDL_itf_ngcisorpc_0000_0000_0001,ulong,uchar const *,int *),uchar * &,uchar * &,__MIDL___MIDL_itf_ngcisorpc_0000_0000_0001 &,ulong &,uchar const * &,int * &>(long (&)(void *,uchar *,uchar *,__MIDL___MIDL_itf_ngcisorpc_0000_0000_0001,ulong,uchar const *,int *),uchar * &,uchar * &,__MIDL___MIDL_itf_ngcisorpc_0000_0000_0001 &,ulong &,uchar const * &,int * &)
0x180065a33  mov     ebx, eax
0x180065a35  test    eax, eax
0x180065a37  jns     short loc_180065A5E
0x180065a39  mov     rcx, [rbp+28h]; this
0x180065a3d  mov     r9d, eax; char *
0x180065a40  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180065a47  mov     edx, 9Ch; void *
0x180065a4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065a51  mov     r9d, ebx
0x180065a54  mov     edx, 467h
0x180065a59  jmp     loc_1800659BE
0x180065a5e  lea     rcx, [rbp+var_30]
0x180065a62  call    wil__details__unique_storage_wil__details__resource_policy_unsigned_char___long____cdecl___unsigned_char______anonymous_namespace___NgcIsoCloseContainer_wistd__integral_constant_unsigned___int64_0__unsigned_char___unsigned_char___0_std__nullptr_t______unique_storage_wil__details__resource_policy_unsigned_char___long____cdecl___unsigned_char______anonymous_namespace___NgcIsoCloseContainer_wistd__integral_constant_unsigned___int64_0__unsigned_char___unsigned_char___0_std__nullptr_t___
0x180065a67  xor     ebx, ebx
0x180065a69  jmp     short loc_180065A9D
0x180065a6b  mov     rcx, [rbp+28h]; this
0x180065a6f  mov     r9d, edi; char *
0x180065a72  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180065a79  mov     edx, 89h; void *
0x180065a7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065a83  mov     rcx, [rbp+28h]; this
0x180065a87  mov     r9d, edi; char *
0x180065a8a  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180065a91  mov     edx, 45Ah; void *
0x180065a96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065a9b  mov     ebx, edi
0x180065a9d  lea     rcx, [rbp+var_28]
0x180065aa1  call    wil__details__unique_storage_wil__details__resource_policy_unsigned_char___long____cdecl___unsigned_char______anonymous_namespace___NgcIsoCloseBuffer_wistd__integral_constant_unsigned___int64_0__unsigned_char___unsigned_char___0_std__nullptr_t______unique_storage_wil__details__resource_policy_unsigned_char___long____cdecl___unsigned_char______anonymous_namespace___NgcIsoCloseBuffer_wistd__integral_constant_unsigned___int64_0__unsigned_char___unsigned_char___0_std__nullptr_t___
0x180065aa6  mov     eax, ebx
0x180065aa8  lea     r11, [rsp+80h+var_s0]
0x180065ab0  mov     rbx, [r11+30h]
0x180065ab4  mov     rsi, [r11+38h]
0x180065ab8  mov     rsp, r11
0x180065abb  pop     r15
0x180065abd  pop     r14
0x180065abf  pop     r12
0x180065ac1  pop     rdi
0x180065ac2  pop     rbp
0x180065ac3  retn
```
