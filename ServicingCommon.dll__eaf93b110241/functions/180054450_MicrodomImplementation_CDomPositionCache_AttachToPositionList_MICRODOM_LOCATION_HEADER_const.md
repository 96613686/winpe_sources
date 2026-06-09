# MicrodomImplementation::CDomPositionCache::AttachToPositionList(_MICRODOM_LOCATION_HEADER const *)

- ea: `0x180054450`
- end: `0x180054591`
- name: `?AttachToPositionList@CDomPositionCache@MicrodomImplementation@@QEAAJPEBU_MICRODOM_LOCATION_HEADER@@@Z`
- size: `321`
- prototype: `__int64 __fastcall(MicrodomImplementation::CDomPositionCache *__hidden this, const struct _MICRODOM_LOCATION_HEADER *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180057f58`

## callees

- `0x18001f4ac`
- `0x18001f554`
- `0x18001fd10`
- `0x1800293a0`
- `0x180054328`
- `0x180054450`

## string_xrefs

- `0x180054473`: `onecore\base\xml\udom_microdom.cpp`
- `0x1800544b6`: `onecore\base\xml\udom_microdom.cpp`
- `0x1800544e6`: `onecore\base\xml\udom_microdom.cpp`
- `0x180054539`: `onecore\base\xml\udom_microdom.cpp`
- `0x180054486`: `MicrodomImplementation::CDomPositionCache::AttachToPositionList`
- `0x1800544c9`: `MicrodomImplementation::CDomPositionCache::AttachToPositionList`
- `0x1800544f9`: `MicrodomImplementation::CDomPositionCache::AttachToPositionList`
- `0x180054550`: `MicrodomImplementation::CDomPositionCache::AttachToPositionList`

## pseudocode

```c
__int64 __fastcall MicrodomImplementation::CDomPositionCache::AttachToPositionList(
        MicrodomImplementation::CDomPositionCache *this,
        const struct _MICRODOM_LOCATION_HEADER *a2)
{
  const char *v2; // rax
  const char *v4; // [rsp+20h] [rbp-30h] BYREF
  const char *v5; // [rsp+28h] [rbp-28h]
  __int64 v6; // [rsp+30h] [rbp-20h]
  const char *v7; // [rsp+38h] [rbp-18h]
  int v8; // [rsp+40h] [rbp-10h] BYREF

  v8 = 0;
  if ( !a2 )
  {
    v6 = 3576;
    v4 = "onecore\\base\\xml\\udom_microdom.cpp";
    v5 = "MicrodomImplementation::CDomPositionCache::AttachToPositionList";
    v2 = "LocationHeader != 0";
LABEL_3:
    v7 = v2;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v8,
             &v4);
  }
  if ( *(_DWORD *)a2 != 1665950797 )
  {
    v6 = 3577;
    v4 = "onecore\\base\\xml\\udom_microdom.cpp";
    v5 = "MicrodomImplementation::CDomPositionCache::AttachToPositionList";
    v2 = "LocationHeader->Signature == ('cLdM')";
    goto LABEL_3;
  }
  if ( (*((_DWORD *)a2 + 1) & 0xFFFFFFFC) != 0 )
  {
    v6 = 3578;
    v4 = "onecore\\base\\xml\\udom_microdom.cpp";
    v5 = "MicrodomImplementation::CDomPositionCache::AttachToPositionList";
    v2 = "(LocationHeader->ulFlags & ~((0x00000001) | (0x00000002) | (0x00000003))) == 0";
    goto LABEL_3;
  }
  if ( *((_QWORD *)this + 4) )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x180054590LL);
  }
  *(_QWORD *)this = a2;
  *((_QWORD *)this + 4) = (char *)a2 + 12;
  *((_DWORD *)this + 7) = *((_DWORD *)a2 + 1) & 3;
  if ( Windows::AutoVectorBase<Windows::VectorTraits<MicrodomImplementation::CDomPositionCache::CPositionSlot>,Windows::Auto<Windows::Vector<MicrodomImplementation::CDomPositionCache::CPositionSlot>>>::Allocate(
         (char *)this + 8,
         *((unsigned int *)a2 + 2)) )
  {
    return 0;
  }
  v6 = 3586;
  v4 = "onecore\\base\\xml\\udom_microdom.cpp";
  v5 = "MicrodomImplementation::CDomPositionCache::AttachToPositionList";
  v7 = "this->m_PositionList.Allocate(LocationHeader->ulItemCount)";
  return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(
           &v8,
           &v4);
}

```

## disassembly

```asm
0x180054450  push    rbp
0x180054452  mov     rbp, rsp
0x180054455  sub     rsp, 50h
0x180054459  mov     rax, cs:__security_cookie
0x180054460  xor     rax, rsp
0x180054463  mov     [rbp+var_8], rax
0x180054467  mov     [rbp+var_10], 0
0x18005446e  test    rdx, rdx
0x180054471  jnz     short loc_1800544AE
0x180054473  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x18005447a  mov     [rbp+var_20], 0DF8h
0x180054482  mov     [rbp+var_30], rax
0x180054486  lea     rax, aMicrodomimplem_13; "MicrodomImplementation::CDomPositionCac"...
0x18005448d  mov     [rbp+var_28], rax
0x180054491  lea     rax, aLocationheader; "LocationHeader != 0"
0x180054498  lea     rdx, [rbp+var_30]
0x18005449c  mov     [rbp+var_18], rax
0x1800544a0  lea     rcx, [rbp+var_10]
0x1800544a4  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800544a9  jmp     loc_180054573
0x1800544ae  cmp     dword ptr [rdx], 634C644Dh
0x1800544b4  jz      short loc_1800544DD
0x1800544b6  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x1800544bd  mov     [rbp+var_20], 0DF9h
0x1800544c5  mov     [rbp+var_30], rax
0x1800544c9  lea     rax, aMicrodomimplem_13; "MicrodomImplementation::CDomPositionCac"...
0x1800544d0  mov     [rbp+var_28], rax
0x1800544d4  lea     rax, aLocationheader_1; "LocationHeader->Signature == ('cLdM')"
0x1800544db  jmp     short loc_180054498
0x1800544dd  test    dword ptr [rdx+4], 0FFFFFFFCh
0x1800544e4  jz      short loc_18005450D
0x1800544e6  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x1800544ed  mov     [rbp+var_20], 0DFAh
0x1800544f5  mov     [rbp+var_30], rax
0x1800544f9  lea     rax, aMicrodomimplem_13; "MicrodomImplementation::CDomPositionCac"...
0x180054500  mov     [rbp+var_28], rax
0x180054504  lea     rax, aLocationheader_0; "(LocationHeader->ulFlags & ~((0x0000000"...
0x18005450b  jmp     short loc_180054498
0x18005450d  cmp     qword ptr [rcx+20h], 0
0x180054512  jnz     short loc_180054586
0x180054514  lea     rax, [rdx+0Ch]
0x180054518  mov     [rcx], rdx
0x18005451b  mov     [rcx+20h], rax
0x18005451f  mov     eax, [rdx+4]
0x180054522  and     eax, 3
0x180054525  mov     [rcx+1Ch], eax
0x180054528  add     rcx, 8
0x18005452c  mov     edx, [rdx+8]
0x18005452f  call    ?Allocate@?$AutoVectorBase@V?$VectorTraits@VCPositionSlot@CDomPositionCache@MicrodomImplementation@@@Windows@@V?$Auto@U?$Vector@VCPositionSlot@CDomPositionCache@MicrodomImplementation@@@Windows@@@2@@Windows@@QEAAPEAVCPositionSlot@CDomPositionCache@MicrodomImplementation@@_K@Z; Windows::AutoVectorBase<Windows::VectorTraits<MicrodomImplementation::CDomPositionCache::CPositionSlot>,Windows::Auto<Windows::Vector<MicrodomImplementation::CDomPositionCache::CPositionSlot>>>::Allocate(unsigned __int64)
0x180054534  test    rax, rax
0x180054537  jnz     short loc_180054571
0x180054539  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180054540  mov     [rbp+var_20], 0E02h
0x180054548  mov     [rbp+var_30], rax
0x18005454c  lea     rdx, [rbp+var_30]
0x180054550  lea     rax, aMicrodomimplem_13; "MicrodomImplementation::CDomPositionCac"...
0x180054557  mov     [rbp+var_28], rax
0x18005455b  lea     rcx, [rbp+var_10]
0x18005455f  lea     rax, aThisMPositionl; "this->m_PositionList.Allocate(LocationH"...
0x180054566  mov     [rbp+var_18], rax
0x18005456a  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005456f  jmp     short loc_180054573
0x180054571  xor     eax, eax
0x180054573  mov     rcx, [rbp+var_8]
0x180054577  xor     rcx, rsp; StackCookie
0x18005457a  call    __security_check_cookie
0x18005457f  add     rsp, 50h
0x180054583  pop     rbp
0x180054584  retn
0x180054586  mov     ecx, 0C00000E5h; int
0x18005458b  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
