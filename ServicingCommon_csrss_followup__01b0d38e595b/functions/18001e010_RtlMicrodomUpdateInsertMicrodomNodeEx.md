# RtlMicrodomUpdateInsertMicrodomNodeEx

- ea: `0x18001e010`
- end: `0x18001e2ec`
- name: `RtlMicrodomUpdateInsertMicrodomNodeEx`
- size: `732`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005c730`

## callees

- `0x18001e010`
- `0x18001f1d8`
- `0x18002d2b0`
- `0x18005c5e0`
- `0x18005c730`
- `0x18005ca5c`
- `0x18009e020`

## string_xrefs

- `0x18001e06b`: `onecore\base\xml\udom_modify.cpp`
- `0x18001e09a`: `onecore\base\xml\udom_modify.cpp`
- `0x18001e0c9`: `onecore\base\xml\udom_modify.cpp`
- `0x18001e111`: `onecore\base\xml\udom_modify.cpp`
- `0x18001e141`: `onecore\base\xml\udom_modify.cpp`
- `0x18001e295`: `onecore\base\xml\udom_modify.cpp`
- `0x18001e07e`: `Windows::uDom::Rtl::RtlMicrodomUpdateInsertMicrodomNodeEx`
- `0x18001e0ad`: `Windows::uDom::Rtl::RtlMicrodomUpdateInsertMicrodomNodeEx`
- `0x18001e0e0`: `Windows::uDom::Rtl::RtlMicrodomUpdateInsertMicrodomNodeEx`
- `0x18001e124`: `Windows::uDom::Rtl::RtlMicrodomUpdateInsertMicrodomNodeEx`
- `0x18001e154`: `Windows::uDom::Rtl::RtlMicrodomUpdateInsertMicrodomNodeEx`
- `0x18001e2a8`: `Windows::uDom::Rtl::RtlMicrodomUpdateInsertMicrodomNodeEx`
- `0x18001e089`: `RtlIsMicrodomUpdateContextValid(HostUpdate)`

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
0x18001e010  push    rbp
0x18001e012  push    rbx
0x18001e013  push    rsi
0x18001e014  push    rdi
0x18001e015  push    r12
0x18001e017  push    r13
0x18001e019  push    r14
0x18001e01b  push    r15
0x18001e01d  lea     rbp, [rsp-7]
0x18001e022  sub     rsp, 0B8h
0x18001e029  mov     rax, cs:__security_cookie
0x18001e030  xor     rax, rsp
0x18001e033  mov     [rbp+3Fh+var_50], rax
0x18001e037  mov     rsi, [rbp+3Fh+arg_20]
0x18001e03b  xorps   xmm0, xmm0
0x18001e03e  mov     r12, [rbp+3Fh+arg_28]
0x18001e042  mov     r15d, edx
0x18001e045  mov     r14, [rbp+3Fh+arg_30]
0x18001e049  xor     edx, edx
0x18001e04b  mov     [rbp+3Fh+var_90], edx
0x18001e04e  xorps   xmm1, xmm1
0x18001e051  mov     rbx, r9
0x18001e054  mov     r13d, r8d
0x18001e057  mov     rdi, rcx
0x18001e05a  movups  [rbp+3Fh+var_80], xmm0
0x18001e05e  movups  [rbp+3Fh+var_70], xmm1
0x18001e062  movups  [rbp+3Fh+var_60], xmm0
0x18001e066  test    rcx, rcx
0x18001e069  jnz     short loc_18001E095
0x18001e06b  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18001e072  mov     [rbp+3Fh+var_A0], 810h
0x18001e07a  mov     qword ptr [rbp+3Fh+var_B0], rax
0x18001e07e  lea     rax, aWindowsUdomRtl_3; "Windows::uDom::Rtl::RtlMicrodomUpdateIn"...
0x18001e085  mov     qword ptr [rbp+3Fh+var_B0+8], rax
0x18001e089  lea     rax, aRtlismicrodomu_0; "RtlIsMicrodomUpdateContextValid(HostUpd"...
0x18001e090  jmp     loc_18001E2BA
0x18001e095  test    rsi, rsi
0x18001e098  jnz     short loc_18001E0C4
0x18001e09a  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18001e0a1  mov     [rbp+3Fh+var_A0], 811h
0x18001e0a9  mov     qword ptr [rbp+3Fh+var_B0], rax
0x18001e0ad  lea     rax, aWindowsUdomRtl_3; "Windows::uDom::Rtl::RtlMicrodomUpdateIn"...
0x18001e0b4  mov     qword ptr [rbp+3Fh+var_B0+8], rax
0x18001e0b8  lea     rax, aDom0; "Dom != 0"
0x18001e0bf  jmp     loc_18001E2BA
0x18001e0c4  test    rbx, rbx
0x18001e0c7  jnz     short loc_18001E104
0x18001e0c9  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18001e0d0  mov     [rbp+3Fh+var_A0], 812h
0x18001e0d8  mov     qword ptr [rbp+3Fh+var_B0], rax
0x18001e0dc  lea     rdx, [rbp+3Fh+var_B0]
0x18001e0e0  lea     rax, aWindowsUdomRtl_3; "Windows::uDom::Rtl::RtlMicrodomUpdateIn"...
0x18001e0e7  mov     qword ptr [rbp+3Fh+var_B0+8], rax
0x18001e0eb  lea     rcx, [rbp+3Fh+var_90]
0x18001e0ef  lea     rax, aNotNullCheckFa_123; "Not-null check failed: pToInsertInto"
0x18001e0f6  mov     [rbp+3Fh+var_98], rax
0x18001e0fa  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18001e0ff  jmp     loc_18001E2CB
0x18001e104  mov     ecx, r15d
0x18001e107  and     ecx, 1
0x18001e10a  lea     eax, [rcx-1]
0x18001e10d  test    ecx, eax
0x18001e10f  jz      short loc_18001E13B
0x18001e111  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18001e118  mov     [rbp+3Fh+var_A0], 813h
0x18001e120  mov     qword ptr [rbp+3Fh+var_B0], rax
0x18001e124  lea     rax, aWindowsUdomRtl_3; "Windows::uDom::Rtl::RtlMicrodomUpdateIn"...
0x18001e12b  mov     qword ptr [rbp+3Fh+var_B0+8], rax
0x18001e12f  lea     rax, aNoMoreThanOneF_0; "No more than one flag set check failed:"...
0x18001e136  jmp     loc_18001E2BA
0x18001e13b  cmp     [r9+28h], rdx
0x18001e13f  jnz     short loc_18001E16B
0x18001e141  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18001e148  mov     [rbp+3Fh+var_A0], 814h
0x18001e150  mov     qword ptr [rbp+3Fh+var_B0], rax
0x18001e154  lea     rax, aWindowsUdomRtl_3; "Windows::uDom::Rtl::RtlMicrodomUpdateIn"...
0x18001e15b  mov     qword ptr [rbp+3Fh+var_B0+8], rax
0x18001e15f  lea     rax, aPtoinsertintoE; "pToInsertInto->Element != 0"
0x18001e166  jmp     loc_18001E2BA
0x18001e16b  test    r14, r14
0x18001e16e  jz      short loc_18001E173
0x18001e170  mov     [r14], rdx
0x18001e173  mov     rax, [rsi]
0x18001e176  lea     r8, [rbp+3Fh+var_80]
0x18001e17a  movups  xmm0, xmmword ptr [r12]
0x18001e17f  lea     rdx, [rbp+3Fh+var_B0]
0x18001e183  mov     rcx, rsi
0x18001e186  mov     rax, [rax+58h]
0x18001e18a  movdqu  [rbp+3Fh+var_B0], xmm0
0x18001e18f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e194  test    eax, eax
0x18001e196  js      loc_18001E2CB
0x18001e19c  cmp     dword ptr [rbp+3Fh+var_80+8], 0FFFFFFFFh
0x18001e1a0  jz      short loc_18001E1D4
0x18001e1a2  movaps  xmm0, [rbp+3Fh+var_80]
0x18001e1a6  lea     rax, [rbp+3Fh+var_B0]
0x18001e1aa  mov     [rsp+0F0h+var_C0], r14
0x18001e1af  mov     r9, rbx
0x18001e1b2  mov     [rsp+0F0h+var_C8], rax
0x18001e1b7  mov     r8d, r13d
0x18001e1ba  mov     edx, r15d
0x18001e1bd  mov     [rsp+0F0h+var_D0], rsi
0x18001e1c2  mov     rcx, rdi
0x18001e1c5  movdqa  [rbp+3Fh+var_B0], xmm0
0x18001e1ca  call    RtlMicrodomUpdateInsertMicrodomElement
0x18001e1cf  jmp     loc_18001E28A
0x18001e1d4  mov     rax, [rsi]
0x18001e1d7  lea     r8, [rbp+3Fh+var_70]
0x18001e1db  movups  xmm0, xmmword ptr [r12]
0x18001e1e0  lea     rdx, [rbp+3Fh+var_B0]
0x18001e1e4  mov     rcx, rsi
0x18001e1e7  mov     rax, [rax+38h]
0x18001e1eb  movdqu  [rbp+3Fh+var_B0], xmm0
0x18001e1f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1f5  test    eax, eax
0x18001e1f7  js      loc_18001E2CB
0x18001e1fd  cmp     dword ptr [rbp+3Fh+var_70+8], 0FFFFFFFFh
0x18001e201  jz      short loc_18001E232
0x18001e203  movaps  xmm0, [rbp+3Fh+var_70]
0x18001e207  lea     rax, [rbp+3Fh+var_B0]
0x18001e20b  mov     [rsp+0F0h+var_C0], r14
0x18001e210  mov     r9, rbx
0x18001e213  mov     [rsp+0F0h+var_C8], rax
0x18001e218  mov     r8d, r13d
0x18001e21b  mov     edx, r15d
0x18001e21e  mov     [rsp+0F0h+var_D0], rsi
0x18001e223  mov     rcx, rdi
0x18001e226  movdqa  [rbp+3Fh+var_B0], xmm0
0x18001e22b  call    RtlMicrodomUpdateInsertMicrodomAttribute
0x18001e230  jmp     short loc_18001E28A
0x18001e232  mov     rax, [rsi]
0x18001e235  lea     r8, [rbp+3Fh+var_60]
0x18001e239  movups  xmm0, xmmword ptr [r12]
0x18001e23e  lea     rdx, [rbp+3Fh+var_B0]
0x18001e242  mov     rcx, rsi
0x18001e245  mov     rax, [rax+40h]
0x18001e249  movdqu  [rbp+3Fh+var_B0], xmm0
0x18001e24e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e253  test    eax, eax
0x18001e255  js      short loc_18001E2CB
0x18001e257  cmp     dword ptr [rbp+3Fh+var_60+8], 0FFFFFFFFh
0x18001e25b  jz      short loc_18001E295
0x18001e25d  movaps  xmm0, [rbp+3Fh+var_60]
0x18001e261  lea     rax, [rbp+3Fh+var_B0]
0x18001e265  mov     [rsp+0F0h+var_C0], r14
0x18001e26a  mov     r9, rbx
0x18001e26d  mov     [rsp+0F0h+var_C8], rax
0x18001e272  mov     r8d, r13d
0x18001e275  mov     edx, r15d
0x18001e278  mov     [rsp+0F0h+var_D0], rsi
0x18001e27d  mov     rcx, rdi
0x18001e280  movdqa  [rbp+3Fh+var_B0], xmm0
0x18001e285  call    RtlMicrodomUpdateInsertMicrodomTextual
0x18001e28a  xor     ecx, ecx
0x18001e28c  test    eax, eax
0x18001e28e  cmovs   ecx, eax
0x18001e291  mov     eax, ecx
0x18001e293  jmp     short loc_18001E2CB
0x18001e295  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18001e29c  mov     [rbp+3Fh+var_A0], 836h
0x18001e2a4  mov     qword ptr [rbp+3Fh+var_B0], rax
0x18001e2a8  lea     rax, aWindowsUdomRtl_3; "Windows::uDom::Rtl::RtlMicrodomUpdateIn"...
0x18001e2af  mov     qword ptr [rbp+3Fh+var_B0+8], rax
0x18001e2b3  lea     rax, aFalse; "false"
0x18001e2ba  lea     rdx, [rbp+3Fh+var_B0]
0x18001e2be  mov     [rbp+3Fh+var_98], rax
0x18001e2c2  lea     rcx, [rbp+3Fh+var_90]
0x18001e2c6  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18001e2cb  mov     rcx, [rbp+3Fh+var_50]
0x18001e2cf  xor     rcx, rsp; StackCookie
0x18001e2d2  call    __security_check_cookie
0x18001e2d7  add     rsp, 0B8h
0x18001e2de  pop     r15
0x18001e2e0  pop     r14
0x18001e2e2  pop     r13
0x18001e2e4  pop     r12
0x18001e2e6  pop     rdi
0x18001e2e7  pop     rsi
0x18001e2e8  pop     rbx
0x18001e2e9  pop     rbp
0x18001e2ea  retn
```
