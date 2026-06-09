# RtlMicrodomUpdateInsertMicrodomNodeEx

- ea: `0x18005c940`
- end: `0x18005cc1c`
- name: `RtlMicrodomUpdateInsertMicrodomNodeEx`
- size: `732`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005b7d0`

## callees

- `0x18001f4ac`
- `0x1800293a0`
- `0x18005b680`
- `0x18005b7d0`
- `0x18005bb08`
- `0x18005c940`
- `0x1800a0020`

## string_xrefs

- `0x18005c99b`: `onecore\base\xml\udom_modify.cpp`
- `0x18005c9ca`: `onecore\base\xml\udom_modify.cpp`
- `0x18005c9f9`: `onecore\base\xml\udom_modify.cpp`
- `0x18005ca41`: `onecore\base\xml\udom_modify.cpp`
- `0x18005ca71`: `onecore\base\xml\udom_modify.cpp`
- `0x18005cbc5`: `onecore\base\xml\udom_modify.cpp`
- `0x18005c9b9`: `RtlIsMicrodomUpdateContextValid(HostUpdate)`
- `0x18005c9ae`: `Windows::uDom::Rtl::RtlMicrodomUpdateInsertMicrodomNodeEx`
- `0x18005c9dd`: `Windows::uDom::Rtl::RtlMicrodomUpdateInsertMicrodomNodeEx`
- `0x18005ca10`: `Windows::uDom::Rtl::RtlMicrodomUpdateInsertMicrodomNodeEx`
- `0x18005ca54`: `Windows::uDom::Rtl::RtlMicrodomUpdateInsertMicrodomNodeEx`
- `0x18005ca84`: `Windows::uDom::Rtl::RtlMicrodomUpdateInsertMicrodomNodeEx`
- `0x18005cbd8`: `Windows::uDom::Rtl::RtlMicrodomUpdateInsertMicrodomNodeEx`

## pseudocode

```c
__int64 __fastcall RtlMicrodomUpdateInsertMicrodomNodeEx(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        __int128 *a6,
        _QWORD *a7)
{
  const char *v11; // rax
  __int64 result; // rax
  __int64 (__fastcall *v13)(__int64, __int128 *, __int128 *); // rax
  int updated; // eax
  __int64 (__fastcall *v15)(__int64, __int128 *, __int128 *); // rax
  __int64 (__fastcall *v16)(__int64, __int128 *, __int128 *); // rax
  unsigned int v17; // ecx
  __int128 v18; // [rsp+40h] [rbp-71h] BYREF
  __int64 v19; // [rsp+50h] [rbp-61h]
  const char *v20; // [rsp+58h] [rbp-59h]
  _DWORD v21[4]; // [rsp+60h] [rbp-51h] BYREF
  __int128 v22; // [rsp+70h] [rbp-41h] BYREF
  __int128 v23; // [rsp+80h] [rbp-31h] BYREF
  __int128 v24; // [rsp+90h] [rbp-21h] BYREF

  v21[0] = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  if ( !a1 )
  {
    v19 = 2064;
    *(_QWORD *)&v18 = "onecore\\base\\xml\\udom_modify.cpp";
    *((_QWORD *)&v18 + 1) = "Windows::uDom::Rtl::RtlMicrodomUpdateInsertMicrodomNodeEx";
    v11 = "RtlIsMicrodomUpdateContextValid(HostUpdate)";
LABEL_26:
    v20 = v11;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             v21,
             &v18);
  }
  if ( !a5 )
  {
    v19 = 2065;
    *(_QWORD *)&v18 = "onecore\\base\\xml\\udom_modify.cpp";
    *((_QWORD *)&v18 + 1) = "Windows::uDom::Rtl::RtlMicrodomUpdateInsertMicrodomNodeEx";
    v11 = "Dom != 0";
    goto LABEL_26;
  }
  if ( !a4 )
  {
    v19 = 2066;
    *(_QWORD *)&v18 = "onecore\\base\\xml\\udom_modify.cpp";
    *((_QWORD *)&v18 + 1) = "Windows::uDom::Rtl::RtlMicrodomUpdateInsertMicrodomNodeEx";
    v20 = "Not-null check failed: pToInsertInto";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             v21,
             &v18);
  }
  if ( (((a2 & 1) - 1) & a2 & 1) != 0 )
  {
    v19 = 2067;
    *(_QWORD *)&v18 = "onecore\\base\\xml\\udom_modify.cpp";
    *((_QWORD *)&v18 + 1) = "Windows::uDom::Rtl::RtlMicrodomUpdateInsertMicrodomNodeEx";
    v11 = "No more than one flag set check failed: Flags";
    goto LABEL_26;
  }
  if ( !*(_QWORD *)(a4 + 40) )
  {
    v19 = 2068;
    *(_QWORD *)&v18 = "onecore\\base\\xml\\udom_modify.cpp";
    *((_QWORD *)&v18 + 1) = "Windows::uDom::Rtl::RtlMicrodomUpdateInsertMicrodomNodeEx";
    v11 = "pToInsertInto->Element != 0";
    goto LABEL_26;
  }
  if ( a7 )
    *a7 = 0;
  v13 = *(__int64 (__fastcall **)(__int64, __int128 *, __int128 *))(*(_QWORD *)a5 + 88LL);
  v18 = *a6;
  result = v13(a5, &v18, &v22);
  if ( (int)result >= 0 )
  {
    if ( DWORD2(v22) == -1 )
    {
      v15 = *(__int64 (__fastcall **)(__int64, __int128 *, __int128 *))(*(_QWORD *)a5 + 56LL);
      v18 = *a6;
      result = v15(a5, &v18, &v23);
      if ( (int)result < 0 )
        return result;
      if ( DWORD2(v23) == -1 )
      {
        v16 = *(__int64 (__fastcall **)(__int64, __int128 *, __int128 *))(*(_QWORD *)a5 + 64LL);
        v18 = *a6;
        result = v16(a5, &v18, &v24);
        if ( (int)result < 0 )
          return result;
        if ( DWORD2(v24) == -1 )
        {
          v19 = 2102;
          *(_QWORD *)&v18 = "onecore\\base\\xml\\udom_modify.cpp";
          *((_QWORD *)&v18 + 1) = "Windows::uDom::Rtl::RtlMicrodomUpdateInsertMicrodomNodeEx";
          v11 = "false";
          goto LABEL_26;
        }
        v18 = v24;
        updated = RtlMicrodomUpdateInsertMicrodomTextual(a1, a2, a3, a4, a5, &v18, a7);
      }
      else
      {
        v18 = v23;
        updated = RtlMicrodomUpdateInsertMicrodomAttribute(a1, a2, a3, a4, a5, &v18, a7);
      }
    }
    else
    {
      v18 = v22;
      updated = RtlMicrodomUpdateInsertMicrodomElement(a1, a2, a3, a4, a5, &v18, a7);
    }
    v17 = 0;
    if ( updated < 0 )
      return (unsigned int)updated;
    return v17;
  }
  return result;
}

```

## disassembly

```asm
0x18005c940  push    rbp
0x18005c942  push    rbx
0x18005c943  push    rsi
0x18005c944  push    rdi
0x18005c945  push    r12
0x18005c947  push    r13
0x18005c949  push    r14
0x18005c94b  push    r15
0x18005c94d  lea     rbp, [rsp-7]
0x18005c952  sub     rsp, 0B8h
0x18005c959  mov     rax, cs:__security_cookie
0x18005c960  xor     rax, rsp
0x18005c963  mov     [rbp+3Fh+var_50], rax
0x18005c967  mov     rsi, [rbp+3Fh+arg_20]
0x18005c96b  xorps   xmm0, xmm0
0x18005c96e  mov     r12, [rbp+3Fh+arg_28]
0x18005c972  mov     r15d, edx
0x18005c975  mov     r14, [rbp+3Fh+arg_30]
0x18005c979  xor     edx, edx
0x18005c97b  mov     [rbp+3Fh+var_90], edx
0x18005c97e  xorps   xmm1, xmm1
0x18005c981  mov     rbx, r9
0x18005c984  mov     r13d, r8d
0x18005c987  mov     rdi, rcx
0x18005c98a  movups  [rbp+3Fh+var_80], xmm0
0x18005c98e  movups  [rbp+3Fh+var_70], xmm1
0x18005c992  movups  [rbp+3Fh+var_60], xmm0
0x18005c996  test    rcx, rcx
0x18005c999  jnz     short loc_18005C9C5
0x18005c99b  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005c9a2  mov     [rbp+3Fh+var_A0], 810h
0x18005c9aa  mov     qword ptr [rbp+3Fh+var_B0], rax
0x18005c9ae  lea     rax, aWindowsUdomRtl_3; "Windows::uDom::Rtl::RtlMicrodomUpdateIn"...
0x18005c9b5  mov     qword ptr [rbp+3Fh+var_B0+8], rax
0x18005c9b9  lea     rax, aRtlismicrodomu_0; "RtlIsMicrodomUpdateContextValid(HostUpd"...
0x18005c9c0  jmp     loc_18005CBEA
0x18005c9c5  test    rsi, rsi
0x18005c9c8  jnz     short loc_18005C9F4
0x18005c9ca  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005c9d1  mov     [rbp+3Fh+var_A0], 811h
0x18005c9d9  mov     qword ptr [rbp+3Fh+var_B0], rax
0x18005c9dd  lea     rax, aWindowsUdomRtl_3; "Windows::uDom::Rtl::RtlMicrodomUpdateIn"...
0x18005c9e4  mov     qword ptr [rbp+3Fh+var_B0+8], rax
0x18005c9e8  lea     rax, aDom0; "Dom != 0"
0x18005c9ef  jmp     loc_18005CBEA
0x18005c9f4  test    rbx, rbx
0x18005c9f7  jnz     short loc_18005CA34
0x18005c9f9  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005ca00  mov     [rbp+3Fh+var_A0], 812h
0x18005ca08  mov     qword ptr [rbp+3Fh+var_B0], rax
0x18005ca0c  lea     rdx, [rbp+3Fh+var_B0]
0x18005ca10  lea     rax, aWindowsUdomRtl_3; "Windows::uDom::Rtl::RtlMicrodomUpdateIn"...
0x18005ca17  mov     qword ptr [rbp+3Fh+var_B0+8], rax
0x18005ca1b  lea     rcx, [rbp+3Fh+var_90]
0x18005ca1f  lea     rax, aNotNullCheckFa_123; "Not-null check failed: pToInsertInto"
0x18005ca26  mov     [rbp+3Fh+var_98], rax
0x18005ca2a  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005ca2f  jmp     loc_18005CBFB
0x18005ca34  mov     ecx, r15d
0x18005ca37  and     ecx, 1
0x18005ca3a  lea     eax, [rcx-1]
0x18005ca3d  test    ecx, eax
0x18005ca3f  jz      short loc_18005CA6B
0x18005ca41  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005ca48  mov     [rbp+3Fh+var_A0], 813h
0x18005ca50  mov     qword ptr [rbp+3Fh+var_B0], rax
0x18005ca54  lea     rax, aWindowsUdomRtl_3; "Windows::uDom::Rtl::RtlMicrodomUpdateIn"...
0x18005ca5b  mov     qword ptr [rbp+3Fh+var_B0+8], rax
0x18005ca5f  lea     rax, aNoMoreThanOneF_0; "No more than one flag set check failed:"...
0x18005ca66  jmp     loc_18005CBEA
0x18005ca6b  cmp     [r9+28h], rdx
0x18005ca6f  jnz     short loc_18005CA9B
0x18005ca71  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005ca78  mov     [rbp+3Fh+var_A0], 814h
0x18005ca80  mov     qword ptr [rbp+3Fh+var_B0], rax
0x18005ca84  lea     rax, aWindowsUdomRtl_3; "Windows::uDom::Rtl::RtlMicrodomUpdateIn"...
0x18005ca8b  mov     qword ptr [rbp+3Fh+var_B0+8], rax
0x18005ca8f  lea     rax, aPtoinsertintoE; "pToInsertInto->Element != 0"
0x18005ca96  jmp     loc_18005CBEA
0x18005ca9b  test    r14, r14
0x18005ca9e  jz      short loc_18005CAA3
0x18005caa0  mov     [r14], rdx
0x18005caa3  mov     rax, [rsi]
0x18005caa6  lea     r8, [rbp+3Fh+var_80]
0x18005caaa  movups  xmm0, xmmword ptr [r12]
0x18005caaf  lea     rdx, [rbp+3Fh+var_B0]
0x18005cab3  mov     rcx, rsi
0x18005cab6  mov     rax, [rax+58h]
0x18005caba  movdqu  [rbp+3Fh+var_B0], xmm0
0x18005cabf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cac4  test    eax, eax
0x18005cac6  js      loc_18005CBFB
0x18005cacc  cmp     dword ptr [rbp+3Fh+var_80+8], 0FFFFFFFFh
0x18005cad0  jz      short loc_18005CB04
0x18005cad2  movaps  xmm0, [rbp+3Fh+var_80]
0x18005cad6  lea     rax, [rbp+3Fh+var_B0]
0x18005cada  mov     [rsp+0F0h+var_C0], r14
0x18005cadf  mov     r9, rbx
0x18005cae2  mov     [rsp+0F0h+var_C8], rax
0x18005cae7  mov     r8d, r13d
0x18005caea  mov     edx, r15d
0x18005caed  mov     [rsp+0F0h+var_D0], rsi
0x18005caf2  mov     rcx, rdi
0x18005caf5  movdqa  [rbp+3Fh+var_B0], xmm0
0x18005cafa  call    RtlMicrodomUpdateInsertMicrodomElement
0x18005caff  jmp     loc_18005CBBA
0x18005cb04  mov     rax, [rsi]
0x18005cb07  lea     r8, [rbp+3Fh+var_70]
0x18005cb0b  movups  xmm0, xmmword ptr [r12]
0x18005cb10  lea     rdx, [rbp+3Fh+var_B0]
0x18005cb14  mov     rcx, rsi
0x18005cb17  mov     rax, [rax+38h]
0x18005cb1b  movdqu  [rbp+3Fh+var_B0], xmm0
0x18005cb20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cb25  test    eax, eax
0x18005cb27  js      loc_18005CBFB
0x18005cb2d  cmp     dword ptr [rbp+3Fh+var_70+8], 0FFFFFFFFh
0x18005cb31  jz      short loc_18005CB62
0x18005cb33  movaps  xmm0, [rbp+3Fh+var_70]
0x18005cb37  lea     rax, [rbp+3Fh+var_B0]
0x18005cb3b  mov     [rsp+0F0h+var_C0], r14
0x18005cb40  mov     r9, rbx
0x18005cb43  mov     [rsp+0F0h+var_C8], rax
0x18005cb48  mov     r8d, r13d
0x18005cb4b  mov     edx, r15d
0x18005cb4e  mov     [rsp+0F0h+var_D0], rsi
0x18005cb53  mov     rcx, rdi
0x18005cb56  movdqa  [rbp+3Fh+var_B0], xmm0
0x18005cb5b  call    RtlMicrodomUpdateInsertMicrodomAttribute
0x18005cb60  jmp     short loc_18005CBBA
0x18005cb62  mov     rax, [rsi]
0x18005cb65  lea     r8, [rbp+3Fh+var_60]
0x18005cb69  movups  xmm0, xmmword ptr [r12]
0x18005cb6e  lea     rdx, [rbp+3Fh+var_B0]
0x18005cb72  mov     rcx, rsi
0x18005cb75  mov     rax, [rax+40h]
0x18005cb79  movdqu  [rbp+3Fh+var_B0], xmm0
0x18005cb7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cb83  test    eax, eax
0x18005cb85  js      short loc_18005CBFB
0x18005cb87  cmp     dword ptr [rbp+3Fh+var_60+8], 0FFFFFFFFh
0x18005cb8b  jz      short loc_18005CBC5
0x18005cb8d  movaps  xmm0, [rbp+3Fh+var_60]
0x18005cb91  lea     rax, [rbp+3Fh+var_B0]
0x18005cb95  mov     [rsp+0F0h+var_C0], r14
0x18005cb9a  mov     r9, rbx
0x18005cb9d  mov     [rsp+0F0h+var_C8], rax
0x18005cba2  mov     r8d, r13d
0x18005cba5  mov     edx, r15d
0x18005cba8  mov     [rsp+0F0h+var_D0], rsi
0x18005cbad  mov     rcx, rdi
0x18005cbb0  movdqa  [rbp+3Fh+var_B0], xmm0
0x18005cbb5  call    RtlMicrodomUpdateInsertMicrodomTextual
0x18005cbba  xor     ecx, ecx
0x18005cbbc  test    eax, eax
0x18005cbbe  cmovs   ecx, eax
0x18005cbc1  mov     eax, ecx
0x18005cbc3  jmp     short loc_18005CBFB
0x18005cbc5  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005cbcc  mov     [rbp+3Fh+var_A0], 836h
0x18005cbd4  mov     qword ptr [rbp+3Fh+var_B0], rax
0x18005cbd8  lea     rax, aWindowsUdomRtl_3; "Windows::uDom::Rtl::RtlMicrodomUpdateIn"...
0x18005cbdf  mov     qword ptr [rbp+3Fh+var_B0+8], rax
0x18005cbe3  lea     rax, aFalse; "false"
0x18005cbea  lea     rdx, [rbp+3Fh+var_B0]
0x18005cbee  mov     [rbp+3Fh+var_98], rax
0x18005cbf2  lea     rcx, [rbp+3Fh+var_90]
0x18005cbf6  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005cbfb  mov     rcx, [rbp+3Fh+var_50]
0x18005cbff  xor     rcx, rsp; StackCookie
0x18005cc02  call    __security_check_cookie
0x18005cc07  add     rsp, 0B8h
0x18005cc0e  pop     r15
0x18005cc10  pop     r14
0x18005cc12  pop     r13
0x18005cc14  pop     r12
0x18005cc16  pop     rdi
0x18005cc17  pop     rsi
0x18005cc18  pop     rbx
0x18005cc19  pop     rbp
0x18005cc1a  retn
```
