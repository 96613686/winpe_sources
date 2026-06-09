# CLocationProviderComposite::GetAcquireTypeForRequest(LOCATIONREQUEST,ushort *,__MIDL___MIDL_itf_locationframework_0000_0000_0001 *)

- ea: `0x180027ca8`
- end: `0x180028126`
- name: `?GetAcquireTypeForRequest@CLocationProviderComposite@@AEAAJULOCATIONREQUEST@@PEAGPEAW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@@Z`
- size: `1150`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180027860`

## callees

- `0x18001a08c`
- `0x18001be08`
- `0x18001e858`
- `0x18001efe0`
- `0x18001f334`
- `0x1800208b0`
- `0x1800208d4`
- `0x180020994`
- `0x180020c64`
- `0x180021450`
- `0x180027834`
- `0x180027ca8`
- `0x180028434`
- `0x180063d0c`
- `0x180087f08`
- `0x18008f888`
- `0x18009c310`
- `0x1800a98c0`
- `0x1800aa5ac`
- `0x18010d91c`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027d22`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027d7c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027f35`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027d22`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027d7c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027f35`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027d08`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027d32`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027d08`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027d32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027e27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027f25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027e27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027f25`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180027e0e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180027e0e`

## string_xrefs

- `0x180027fd0`: `onecoreuap\drivers\mobilepc\location\product\core\pe\composite\locationprovidercpe.cpp`
- `0x180028016`: `onecoreuap\drivers\mobilepc\location\product\core\pe\composite\locationprovidercpe.cpp`
- `0x18002810e`: `onecoreuap\drivers\mobilepc\location\product\core\pe\composite\locationprovidercpe.cpp`
- `0x180027fc9`: `CLocationProviderComposite::GetAcquireSupportForRequest`
- `0x18002800f`: `CLocationProviderComposite::GetAcquireSupportForRequest`
- `0x180028107`: `CLocationProviderComposite::GetAcquireTypeForRequest`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CLocationProviderComposite::GetAcquireTypeForRequest(
        __int64 a1,
        __int128 *a2,
        __int64 a3,
        unsigned int *a4)
{
  char v8; // r12
  __m128i si128; // xmm6
  std::_Ref_count_base *v10; // rdi
  __m128i v11; // xmm7
  __int64 v12; // rax
  __int64 v13; // rdx
  const WCHAR *v14; // rax
  wil::details *v15; // rcx
  const unsigned __int16 *v16; // r8
  int LastErrorFailHr; // esi
  std::_Ref_count_base *v18; // rcx
  unsigned int v19; // edi
  __int64 result; // rax
  int v21; // eax
  int v22; // eax
  wil::details *v23; // [rsp+28h] [rbp-D8h]
  int v24[4]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v25; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v26; // [rsp+50h] [rbp-B0h]
  int v27; // [rsp+60h] [rbp-A0h]
  __int128 v28; // [rsp+70h] [rbp-90h] BYREF
  __m128i v29; // [rsp+80h] [rbp-80h]
  PSID Sid; // [rsp+90h] [rbp-70h] BYREF
  int v31; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v32[128]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+198h] [rbp+98h]

  if ( !a4 )
    return 2147942487LL;
  LOBYTE(v24[0]) = 0;
  v8 = 0;
  v28 = 0;
  EnterCriticalSection(&stru_1801E4420);
  Sid = &stru_1801E4420;
  if ( !dword_1801E4448 )
    CLocationObjectManager::Start();
  LeaveCriticalSection(&stru_1801E4420);
  EnterCriticalSection(&stru_1801E4420);
  si128 = 0;
  v28 = 0;
  if ( dword_1801E4448 == 1 )
  {
    v10 = (std::_Ref_count_base *)*((_QWORD *)&xmmword_1801E43C8 + 1);
    if ( *((_QWORD *)&xmmword_1801E43C8 + 1) )
    {
      v28 = xmmword_1801E43C8;
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&xmmword_1801E43C8 + 1) + 12LL));
      si128 = _mm_load_si128((const __m128i *)&v28);
    }
    else
    {
      v10 = (std::_Ref_count_base *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    }
    LeaveCriticalSection(&stru_1801E4420);
  }
  else
  {
    LeaveCriticalSection(&stru_1801E4420);
    v10 = (std::_Ref_count_base *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  }
  v11 = 0;
  v29 = 0;
  if ( v10 && std::_Ref_count_base::_Incref_nz(v10) )
  {
    v11 = si128;
    v29 = si128;
  }
  if ( v11.m128i_i64[0] )
  {
    memset_0(v32, 0, 0x78u);
    ATL::CSid::CSid((ATL::CSid *)v32);
    v25 = 0;
    v26 = 0;
    v12 = std::_WChar_traits<unsigned short>::length(a3);
    std::wstring::_Construct<1,unsigned short const *>(&v25, a3, v12);
    Sid = 0;
    v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v25, v13);
    if ( ConvertStringSidToSidW(v14, &Sid) && ATL::CSid::LoadAccount((ATL::CSid *)v32, (struct _SID *)Sid, v16) )
    {
      LocalFree(Sid);
      LastErrorFailHr = 0;
    }
    else
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v15);
      LocalFree(Sid);
    }
    std::wstring::_Tidy_deallocate(&v25);
    if ( LastErrorFailHr >= 0 )
      v8 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v11.m128i_i64[0] + 24LL))(v11.m128i_i64[0], v32);
    ATL::CSid::~CSid((ATL::CSid *)v32);
  }
  v18 = (std::_Ref_count_base *)_mm_srli_si128(v11, 8).m128i_u64[0];
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  if ( v10 )
    std::_Ref_count_base::_Decwref(v10);
  if ( v8 || (unsigned __int8)CLocationAcquireOverrideCpe::GetOverrideMode_::_1_::_lambda_1_::operator()() )
  {
    v19 = 21;
    goto LABEL_32;
  }
  v19 = *((_DWORD *)a2 + 6);
  if ( v19 - 17 > 2 )
  {
    v31 = 0;
    LODWORD(Sid) = 0;
    if ( *(_DWORD *)a2 == 1 || (unsigned int)(*(_DWORD *)a2 - 2) <= 1 )
    {
      v21 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a1 + 80LL))(a1, &v31);
      if ( v21 < 0 )
      {
        LODWORD(v23) = v21;
        wil::details::in1diag5::_Log_Hr(
          retaddr,
          (void *)0x17A,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\pe\\composite\\locationprovidercpe.cpp",
          "CLocationProviderComposite::GetAcquireSupportForRequest",
          "get_SupportsNativeDistanceTracking(&supportsNativeDT)",
          (const char *)v23,
          v24[0]);
      }
      v22 = (*(__int64 (__fastcall **)(__int64, PSID *))(*(_QWORD *)a1 + 88LL))(a1, &Sid);
      if ( v22 < 0 )
      {
        LODWORD(v23) = v22;
        wil::details::in1diag5::_Log_Hr(
          retaddr,
          (void *)0x17B,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\pe\\composite\\locationprovidercpe.cpp",
          "CLocationProviderComposite::GetAcquireSupportForRequest",
          "get_SupportsNativePeriodicTracking(&supportsNativePT)",
          (const char *)v23,
          v24[0]);
      }
      if ( *(_DWORD *)a2 == 1 )
      {
        v19 = 17;
        goto LABEL_32;
      }
    }
    v25 = *a2;
    v26 = a2[1];
    v27 = *((_DWORD *)a2 + 8);
    v19 = 19;
    if ( (int)CLocationProviderComposite::GetAcquireSupportForRequest(a1, 19, &v25, v24) >= 0 && LOBYTE(v24[0]) )
      goto LABEL_32;
    v25 = *a2;
    v26 = a2[1];
    v27 = *((_DWORD *)a2 + 8);
    v19 = 18;
    if ( (int)CLocationProviderComposite::GetAcquireSupportForRequest(a1, 18, &v25, v24) >= 0 )
    {
      if ( LOBYTE(v24[0]) )
      {
        v25 = *a2;
        v26 = a2[1];
        v27 = *((_DWORD *)a2 + 8);
        if ( !(unsigned __int8)CpeHelper::IsHighAccuracyOrHighFrequencyTrackingSession(&v25) )
          goto LABEL_32;
      }
    }
    return 2147942487LL;
  }
  v25 = *a2;
  v26 = a2[1];
  v27 = *((_DWORD *)a2 + 8);
  result = CLocationProviderComposite::GetAcquireSupportForRequest(a1, v19, &v25, v24);
  if ( (int)result >= 0 )
  {
    if ( !LOBYTE(v24[0]) )
    {
      LODWORD(v23) = -2147023537;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x1D0,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\pe\\composite\\locationprovidercpe.cpp",
        "CLocationProviderComposite::GetAcquireTypeForRequest",
        "!(wil::verify_bool(supportsRequest))",
        v23,
        v24[0]);
      return 2147943759LL;
    }
LABEL_32:
    *a4 = v19;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180027ca8  mov     rax, rsp
0x180027cab  push    rbp
0x180027cac  push    rbx
0x180027cad  push    rsi
0x180027cae  push    rdi
0x180027caf  push    r12
0x180027cb1  push    r13
0x180027cb3  push    r14
0x180027cb5  push    r15
0x180027cb7  lea     rbp, [rsp-58h]
0x180027cbc  sub     rsp, 158h
0x180027cc3  movaps  xmmword ptr [rax-58h], xmm6
0x180027cc7  movaps  xmmword ptr [rax-68h], xmm7
0x180027ccb  mov     rax, cs:__security_cookie
0x180027cd2  xor     rax, rsp
0x180027cd5  mov     [rbp+90h+var_70], rax
0x180027cd9  mov     r13, r9
0x180027cdc  mov     rsi, r8
0x180027cdf  mov     rbx, rdx
0x180027ce2  mov     r14, rcx
0x180027ce5  test    r9, r9
0x180027ce8  jz      loc_1800280D6
0x180027cee  mov     byte ptr [rsp+190h+var_160], 0; int
0x180027cf3  xor     r12b, r12b
0x180027cf6  xorps   xmm0, xmm0
0x180027cf9  movups  [rsp+190h+var_120], xmm0
0x180027cfe  lea     rdi, stru_1801E4420
0x180027d05  mov     rcx, rdi; lpCriticalSection
0x180027d08  call    cs:__imp_EnterCriticalSection
0x180027d0e  mov     [rbp+90h+Sid], rdi
0x180027d12  cmp     cs:dword_1801E4448, 0
0x180027d19  jz      loc_180027F5F
0x180027d1f  mov     rcx, rdi; lpCriticalSection
0x180027d22  call    cs:__imp_LeaveCriticalSection
0x180027d28  lea     r15, stru_1801E4420
0x180027d2f  mov     rcx, r15; lpCriticalSection
0x180027d32  call    cs:__imp_EnterCriticalSection
0x180027d38  xorps   xmm6, xmm6
0x180027d3b  movdqa  [rsp+190h+var_120], xmm6
0x180027d41  cmp     cs:dword_1801E4448, 1
0x180027d48  jnz     loc_180027F32
0x180027d4e  mov     rdi, qword ptr cs:xmmword_1801E43C8+8
0x180027d55  test    rdi, rdi
0x180027d58  jz      loc_180027F4D
0x180027d5e  mov     rax, qword ptr cs:xmmword_1801E43C8
0x180027d65  mov     qword ptr [rsp+190h+var_120], rax
0x180027d6a  mov     qword ptr [rsp+190h+var_120+8], rdi
0x180027d6f  lock inc dword ptr [rdi+0Ch]
0x180027d73  movdqa  xmm6, [rsp+190h+var_120]
0x180027d79  mov     rcx, r15; lpCriticalSection
0x180027d7c  call    cs:__imp_LeaveCriticalSection
0x180027d82  nop
0x180027d83  xorps   xmm7, xmm7
0x180027d86  movdqa  [rbp+90h+var_110], xmm7
0x180027d8b  test    rdi, rdi
0x180027d8e  jz      short loc_180027DA4
0x180027d90  mov     rcx, rdi; this
0x180027d93  call    ?_Incref_nz@_Ref_count_base@std@@QEAA_NXZ; std::_Ref_count_base::_Incref_nz(void)
0x180027d98  test    al, al
0x180027d9a  jz      short loc_180027DA4
0x180027d9c  movaps  xmm7, xmm6
0x180027d9f  movdqa  [rbp+90h+var_110], xmm6
0x180027da4  movq    r15, xmm7
0x180027da9  test    r15, r15
0x180027dac  jz      loc_180027E61
0x180027db2  xor     edx, edx; Val
0x180027db4  lea     r8d, [rdx+78h]; Size
0x180027db8  lea     rcx, [rbp+90h+var_F0]; void *
0x180027dbc  call    memset_0
0x180027dc1  lea     rcx, [rbp+90h+var_F0]; this
0x180027dc5  call    ??0CSid@ATL@@QEAA@XZ; ATL::CSid::CSid(void)
0x180027dca  nop
0x180027dcb  xorps   xmm0, xmm0
0x180027dce  movups  [rsp+190h+var_150], xmm0
0x180027dd3  xorps   xmm1, xmm1
0x180027dd6  movdqu  [rsp+190h+var_140], xmm1
0x180027ddc  mov     rcx, rsi
0x180027ddf  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180027de4  mov     r8, rax
0x180027de7  mov     rdx, rsi
0x180027dea  lea     rcx, [rsp+190h+var_150]
0x180027def  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180027df4  nop
0x180027df5  mov     [rbp+90h+Sid], 0
0x180027dfd  lea     rcx, [rsp+190h+var_150]
0x180027e02  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180027e07  mov     rcx, rax; StringSid
0x180027e0a  lea     rdx, [rbp+90h+Sid]; Sid
0x180027e0e  call    cs:__imp_ConvertStringSidToSidW
0x180027e14  test    eax, eax
0x180027e16  jnz     loc_180027F0C
0x180027e1c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180027e21  mov     esi, eax
0x180027e23  mov     rcx, [rbp+90h+Sid]; hMem
0x180027e27  call    cs:__imp_LocalFree
0x180027e2d  nop
0x180027e2e  lea     rcx, [rsp+190h+var_150]
0x180027e33  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027e38  shr     esi, 1Fh
0x180027e3b  xor     sil, 1
0x180027e3f  jz      short loc_180027E57
0x180027e41  mov     rax, [r15]
0x180027e44  lea     rdx, [rbp+90h+var_F0]
0x180027e48  mov     rcx, r15
0x180027e4b  mov     rax, [rax+18h]
0x180027e4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e54  mov     r12b, al
0x180027e57  lea     rcx, [rbp+90h+var_F0]; this
0x180027e5b  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x180027e60  nop
0x180027e61  psrldq  xmm7, 8
0x180027e66  movq    rcx, xmm7; this
0x180027e6b  xor     esi, esi
0x180027e6d  test    rcx, rcx
0x180027e70  jz      short loc_180027E78
0x180027e72  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180027e77  nop
0x180027e78  test    rdi, rdi
0x180027e7b  jz      short loc_180027E85
0x180027e7d  mov     rcx, rdi; this
0x180027e80  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180027e85  test    r12b, r12b
0x180027e88  jnz     loc_180027F69
0x180027e8e  call    _CLocationAcquireOverrideCpe__GetOverrideMode____1____lambda_1___operator__
0x180027e93  test    al, al
0x180027e95  jnz     loc_180027F69
0x180027e9b  mov     edi, [rbx+18h]
0x180027e9e  lea     eax, [rdi-11h]
0x180027ea1  cmp     eax, 2
0x180027ea4  ja      loc_180027F80
0x180027eaa  movaps  xmm0, xmmword ptr [rbx]
0x180027ead  movaps  [rsp+190h+var_150], xmm0
0x180027eb2  movaps  xmm1, xmmword ptr [rbx+10h]
0x180027eb6  movaps  [rsp+190h+var_140], xmm1
0x180027ebb  mov     eax, [rbx+20h]
0x180027ebe  mov     [rsp+190h+var_130], eax
0x180027ec2  lea     r9, [rsp+190h+var_160]
0x180027ec7  lea     r8, [rsp+190h+var_150]
0x180027ecc  mov     edx, edi
0x180027ece  mov     rcx, r14
0x180027ed1  call    ?GetAcquireSupportForRequest@CLocationProviderComposite@@AEAAJW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@ULOCATIONREQUEST@@PEA_N@Z; CLocationProviderComposite::GetAcquireSupportForRequest(__MIDL___MIDL_itf_locationframework_0000_0000_0001,LOCATIONREQUEST,bool *)
0x180027ed6  test    eax, eax
0x180027ed8  jns     loc_1800280E0
0x180027ede  mov     rcx, [rbp+90h+var_70]
0x180027ee2  xor     rcx, rsp; StackCookie
0x180027ee5  call    __security_check_cookie
0x180027eea  lea     r11, [rsp+190h+var_38]
0x180027ef2  movaps  xmm6, xmmword ptr [r11-18h]
0x180027ef7  movaps  xmm7, xmmword ptr [r11-28h]
0x180027efc  mov     rsp, r11
0x180027eff  pop     r15
0x180027f01  pop     r14
0x180027f03  pop     r13
0x180027f05  pop     r12
0x180027f07  pop     rdi
0x180027f08  pop     rsi
0x180027f09  pop     rbx
0x180027f0a  pop     rbp
0x180027f0b  retn
0x180027f0c  mov     rdx, [rbp+90h+Sid]; struct _SID *
0x180027f10  lea     rcx, [rbp+90h+var_F0]; this
0x180027f14  call    ?LoadAccount@CSid@ATL@@QEAA_NPEBU_SID@@PEBG@Z; ATL::CSid::LoadAccount(_SID const *,ushort const *)
0x180027f19  test    al, al
0x180027f1b  jz      loc_180027E1C
0x180027f21  mov     rcx, [rbp+90h+Sid]; hMem
0x180027f25  call    cs:__imp_LocalFree
0x180027f2b  xor     esi, esi
0x180027f2d  jmp     loc_180027E2E
0x180027f32  mov     rcx, r15; lpCriticalSection
0x180027f35  call    cs:__imp_LeaveCriticalSection
0x180027f3b  xorps   xmm0, xmm0
0x180027f3e  psrldq  xmm0, 8
0x180027f43  movq    rdi, xmm0
0x180027f48  jmp     loc_180027D83
0x180027f4d  xorps   xmm0, xmm0
0x180027f50  psrldq  xmm0, 8
0x180027f55  movq    rdi, xmm0
0x180027f5a  jmp     loc_180027D79
0x180027f5f  call    ?Start@CLocationObjectManager@@KAJXZ; CLocationObjectManager::Start(void)
0x180027f64  jmp     loc_180027D1F
0x180027f69  mov     edi, 15h
0x180027f6e  jmp     short loc_180027F75
0x180027f70  mov     edi, 11h
0x180027f75  mov     [r13+0], edi
0x180027f79  xor     eax, eax
0x180027f7b  jmp     loc_180027EDE
0x180027f80  mov     [rbp+90h+var_F8], esi
0x180027f83  mov     dword ptr [rbp+90h+Sid], esi
0x180027f86  mov     ecx, [rbx]
0x180027f88  sub     ecx, 1
0x180027f8b  jz      short loc_180027F9B
0x180027f8d  sub     ecx, 1
0x180027f90  jz      short loc_180027F9B
0x180027f92  cmp     ecx, 1
0x180027f95  jnz     loc_180028030
0x180027f9b  mov     rax, [r14]
0x180027f9e  lea     rdx, [rbp+90h+var_F8]
0x180027fa2  mov     rcx, r14
0x180027fa5  mov     rax, [rax+50h]
0x180027fa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027fae  test    eax, eax
0x180027fb0  jns     short loc_180027FE1
0x180027fb2  mov     rcx, [rbp+98h]; this
0x180027fb9  mov     dword ptr [rsp+190h+var_168], eax; char *
0x180027fbd  lea     rax, aGetSupportsnat; "get_SupportsNativeDistanceTracking(&sup"...
0x180027fc4  mov     [rsp+190h+var_170], rax; char *
0x180027fc9  lea     r9, aClocationprovi_7; "CLocationProviderComposite::GetAcquireS"...
0x180027fd0  lea     r8, aOnecoreuapDriv_53; "onecoreuap\\drivers\\mobilepc\\location"...
0x180027fd7  mov     edx, 17Ah; void *
0x180027fdc  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x180027fe1  mov     rax, [r14]
0x180027fe4  lea     rdx, [rbp+90h+Sid]
0x180027fe8  mov     rcx, r14
0x180027feb  mov     rax, [rax+58h]
0x180027fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ff4  test    eax, eax
0x180027ff6  jns     short loc_180028027
0x180027ff8  mov     rcx, [rbp+98h]; this
0x180027fff  mov     dword ptr [rsp+190h+var_168], eax; char *
0x180028003  lea     rax, aGetSupportsnat_0; "get_SupportsNativePeriodicTracking(&sup"...
0x18002800a  mov     [rsp+190h+var_170], rax; char *
0x18002800f  lea     r9, aClocationprovi_7; "CLocationProviderComposite::GetAcquireS"...
0x180028016  lea     r8, aOnecoreuapDriv_53; "onecoreuap\\drivers\\mobilepc\\location"...
0x18002801d  mov     edx, 17Bh; void *
0x180028022  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x180028027  cmp     dword ptr [rbx], 1
0x18002802a  jz      loc_180027F70
0x180028030  movaps  xmm0, xmmword ptr [rbx]
0x180028033  movaps  [rsp+190h+var_150], xmm0
0x180028038  movaps  xmm1, xmmword ptr [rbx+10h]
0x18002803c  movaps  [rsp+190h+var_140], xmm1
0x180028041  mov     eax, [rbx+20h]
0x180028044  mov     [rsp+190h+var_130], eax
0x180028048  lea     r9, [rsp+190h+var_160]
0x18002804d  lea     r8, [rsp+190h+var_150]
0x180028052  mov     edi, 13h
0x180028057  mov     edx, edi
0x180028059  mov     rcx, r14
0x18002805c  call    ?GetAcquireSupportForRequest@CLocationProviderComposite@@AEAAJW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@ULOCATIONREQUEST@@PEA_N@Z; CLocationProviderComposite::GetAcquireSupportForRequest(__MIDL___MIDL_itf_locationframework_0000_0000_0001,LOCATIONREQUEST,bool *)
0x180028061  test    eax, eax
0x180028063  js      short loc_180028070
0x180028065  cmp     byte ptr [rsp+190h+var_160], sil
0x18002806a  jnz     loc_180027F75
0x180028070  movaps  xmm0, xmmword ptr [rbx]
0x180028073  movaps  [rsp+190h+var_150], xmm0
0x180028078  movaps  xmm1, xmmword ptr [rbx+10h]
0x18002807c  movaps  [rsp+190h+var_140], xmm1
0x180028081  mov     eax, [rbx+20h]
0x180028084  mov     [rsp+190h+var_130], eax
0x180028088  lea     r9, [rsp+190h+var_160]
0x18002808d  lea     r8, [rsp+190h+var_150]
0x180028092  mov     edi, 12h
0x180028097  mov     edx, edi
0x180028099  mov     rcx, r14
0x18002809c  call    ?GetAcquireSupportForRequest@CLocationProviderComposite@@AEAAJW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@ULOCATIONREQUEST@@PEA_N@Z; CLocationProviderComposite::GetAcquireSupportForRequest(__MIDL___MIDL_itf_locationframework_0000_0000_0001,LOCATIONREQUEST,bool *)
0x1800280a1  test    eax, eax
0x1800280a3  js      short loc_1800280D6
0x1800280a5  cmp     byte ptr [rsp+190h+var_160], sil
0x1800280aa  jz      short loc_1800280D6
0x1800280ac  movaps  xmm0, xmmword ptr [rbx]
0x1800280af  movaps  [rsp+190h+var_150], xmm0
0x1800280b4  movaps  xmm1, xmmword ptr [rbx+10h]
0x1800280b8  movaps  [rsp+190h+var_140], xmm1
0x1800280bd  mov     eax, [rbx+20h]
0x1800280c0  mov     [rsp+190h+var_130], eax
0x1800280c4  lea     rcx, [rsp+190h+var_150]
0x1800280c9  call    ?IsHighAccuracyOrHighFrequencyTrackingSession@CpeHelper@@SA_NULOCATIONREQUEST@@@Z; CpeHelper::IsHighAccuracyOrHighFrequencyTrackingSession(LOCATIONREQUEST)
0x1800280ce  test    al, al
0x1800280d0  jz      loc_180027F75
0x1800280d6  mov     eax, 80070057h
0x1800280db  jmp     loc_180027EDE
0x1800280e0  cmp     byte ptr [rsp+190h+var_160], sil
0x1800280e5  jnz     loc_180027F75
0x1800280eb  mov     rcx, [rbp+98h]; this
0x1800280f2  mov     ebx, 8007054Fh
0x1800280f7  mov     dword ptr [rsp+190h+var_168], ebx; wil::details *
0x1800280fb  lea     rdx, aWilVerifyBoolS_2; "!(wil::verify_bool(supportsRequest))"
0x180028102  mov     [rsp+190h+var_170], rdx; char *
0x180028107  lea     r9, aClocationprovi_6; "CLocationProviderComposite::GetAcquireT"...
0x18002810e  lea     r8, aOnecoreuapDriv_53; "onecoreuap\\drivers\\mobilepc\\location"...
0x180028115  mov     edx, 1D0h; void *
0x18002811a  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18002811f  mov     eax, ebx
0x180028121  jmp     loc_180027EDE
```
