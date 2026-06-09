# MicrodomImplementation::CDomPositionCache::AttachToPositionList(_MICRODOM_LOCATION_HEADER const *)

- ea: `0x180056824`
- end: `0x1800569d5`
- name: `?AttachToPositionList@CDomPositionCache@MicrodomImplementation@@QEAAJPEBU_MICRODOM_LOCATION_HEADER@@@Z`
- size: `433`
- prototype: `__int64 __fastcall(MicrodomImplementation::CDomPositionCache *__hidden this, const struct _MICRODOM_LOCATION_HEADER *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180058efc`

## callees

- `0x18001b1d4`
- `0x18001f1d8`
- `0x1800217cc`
- `0x180026dc0`
- `0x18002d2b0`
- `0x180056824`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x1800568f6`
- `ntdll!RtlRaiseStatus` at `0x1800568f6`

## string_xrefs

- `0x180056850`: `onecore\base\xml\udom_microdom.cpp`
- `0x180056893`: `onecore\base\xml\udom_microdom.cpp`
- `0x1800568c3`: `onecore\base\xml\udom_microdom.cpp`
- `0x180056982`: `onecore\base\xml\udom_microdom.cpp`
- `0x180056863`: `MicrodomImplementation::CDomPositionCache::AttachToPositionList`
- `0x1800568a6`: `MicrodomImplementation::CDomPositionCache::AttachToPositionList`
- `0x1800568d6`: `MicrodomImplementation::CDomPositionCache::AttachToPositionList`
- `0x180056999`: `MicrodomImplementation::CDomPositionCache::AttachToPositionList`

## pseudocode

```c
__int64 __fastcall MicrodomImplementation::CDomPositionCache::AttachToPositionList(
        MicrodomImplementation::CDomPositionCache *this,
        const struct _MICRODOM_LOCATION_HEADER *a2)
{
  const char *v3; // rax
  unsigned __int64 v5; // rsi
  void *v6; // rax
  void *v7; // rbx
  const char *v8; // [rsp+20h] [rbp-30h] BYREF
  const char *v9; // [rsp+28h] [rbp-28h]
  __int64 v10; // [rsp+30h] [rbp-20h]
  const char *v11; // [rsp+38h] [rbp-18h]
  int v12; // [rsp+40h] [rbp-10h] BYREF

  v12 = 0;
  if ( !a2 )
  {
    v10 = 3576;
    v8 = "onecore\\base\\xml\\udom_microdom.cpp";
    v9 = "MicrodomImplementation::CDomPositionCache::AttachToPositionList";
    v3 = "LocationHeader != 0";
LABEL_3:
    v11 = v3;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v12,
             &v8);
  }
  if ( *(_DWORD *)a2 != 1665950797 )
  {
    v10 = 3577;
    v8 = "onecore\\base\\xml\\udom_microdom.cpp";
    v9 = "MicrodomImplementation::CDomPositionCache::AttachToPositionList";
    v3 = "LocationHeader->Signature == ('cLdM')";
    goto LABEL_3;
  }
  if ( (*((_DWORD *)a2 + 1) & 0xFFFFFFFC) != 0 )
  {
    v10 = 3578;
    v8 = "onecore\\base\\xml\\udom_microdom.cpp";
    v9 = "MicrodomImplementation::CDomPositionCache::AttachToPositionList";
    v3 = "(LocationHeader->ulFlags & ~((0x00000001) | (0x00000002) | (0x00000003))) == 0";
    goto LABEL_3;
  }
  if ( *((_QWORD *)this + 4) )
    RtlRaiseStatus(-1073741595);
  *(_QWORD *)this = a2;
  *((_QWORD *)this + 4) = (char *)a2 + 12;
  *((_DWORD *)this + 7) = *((_DWORD *)a2 + 1) & 3;
  if ( !*((_QWORD *)this + 1) )
  {
    if ( !*((_DWORD *)a2 + 2) )
      return 0;
    v5 = *((unsigned int *)a2 + 2);
    v6 = operator new(saturated_mul(v5, 8u));
    v7 = v6;
    if ( v6 )
      `vector constructor iterator'(
        v6,
        8u,
        (unsigned int)v5,
        (void *(*)(void *))MicrodomImplementation::CDomPositionCache::CPositionSlot::CPositionSlot);
    else
      v7 = 0;
    if ( v7 )
    {
      *((_QWORD *)this + 1) = v7;
      *((_QWORD *)this + 2) = v5;
      return 0;
    }
  }
  v10 = 3586;
  v8 = "onecore\\base\\xml\\udom_microdom.cpp";
  v9 = "MicrodomImplementation::CDomPositionCache::AttachToPositionList";
  v11 = "this->m_PositionList.Allocate(LocationHeader->ulItemCount)";
  return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(
           &v12,
           &v8);
}

```

## disassembly

```asm
0x180056824  mov     [rsp-18h+arg_10], rbx
0x180056829  push    rbp
0x18005682a  push    rsi
0x18005682b  push    rdi
0x18005682c  mov     rbp, rsp
0x18005682f  sub     rsp, 50h
0x180056833  mov     rax, cs:__security_cookie
0x18005683a  xor     rax, rsp
0x18005683d  mov     [rbp+var_8], rax
0x180056841  mov     [rbp+var_10], 0
0x180056848  mov     rdi, rcx
0x18005684b  test    rdx, rdx
0x18005684e  jnz     short loc_18005688B
0x180056850  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180056857  mov     [rbp+var_20], 0DF8h
0x18005685f  mov     [rbp+var_30], rax
0x180056863  lea     rax, aMicrodomimplem_13; "MicrodomImplementation::CDomPositionCac"...
0x18005686a  mov     [rbp+var_28], rax
0x18005686e  lea     rax, aLocationheader; "LocationHeader != 0"
0x180056875  lea     rdx, [rbp+var_30]
0x180056879  mov     [rbp+var_18], rax
0x18005687d  lea     rcx, [rbp+var_10]
0x180056881  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180056886  jmp     loc_1800569B8
0x18005688b  cmp     dword ptr [rdx], 634C644Dh
0x180056891  jz      short loc_1800568BA
0x180056893  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x18005689a  mov     [rbp+var_20], 0DF9h
0x1800568a2  mov     [rbp+var_30], rax
0x1800568a6  lea     rax, aMicrodomimplem_13; "MicrodomImplementation::CDomPositionCac"...
0x1800568ad  mov     [rbp+var_28], rax
0x1800568b1  lea     rax, aLocationheader_1; "LocationHeader->Signature == ('cLdM')"
0x1800568b8  jmp     short loc_180056875
0x1800568ba  test    dword ptr [rdx+4], 0FFFFFFFCh
0x1800568c1  jz      short loc_1800568EA
0x1800568c3  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x1800568ca  mov     [rbp+var_20], 0DFAh
0x1800568d2  mov     [rbp+var_30], rax
0x1800568d6  lea     rax, aMicrodomimplem_13; "MicrodomImplementation::CDomPositionCac"...
0x1800568dd  mov     [rbp+var_28], rax
0x1800568e1  lea     rax, aLocationheader_0; "(LocationHeader->ulFlags & ~((0x0000000"...
0x1800568e8  jmp     short loc_180056875
0x1800568ea  cmp     qword ptr [rcx+20h], 0
0x1800568ef  jz      short loc_180056903
0x1800568f1  mov     ecx, 0C00000E5h; Status
0x1800568f6  call    cs:__imp_RtlRaiseStatus
0x1800568fd  nop     dword ptr [rax+rax+00h]
0x180056902  int     3; Trap to Debugger
0x180056903  lea     rax, [rdx+0Ch]
0x180056907  mov     [rcx], rdx
0x18005690a  mov     [rcx+20h], rax
0x18005690e  mov     eax, [rdx+4]
0x180056911  and     eax, 3
0x180056914  mov     [rcx+1Ch], eax
0x180056917  cmp     qword ptr [rcx+8], 0
0x18005691c  jnz     short loc_180056982
0x18005691e  cmp     dword ptr [rdx+8], 0
0x180056922  jz      short loc_180056974
0x180056924  mov     esi, [rdx+8]
0x180056927  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18005692e  mov     eax, 8
0x180056933  mul     rsi
0x180056936  cmovb   rax, rcx
0x18005693a  mov     rcx, rax; Size
0x18005693d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180056942  mov     rbx, rax
0x180056945  test    rax, rax
0x180056948  jz      short loc_180056963
0x18005694a  lea     r9, ??0CPositionSlot@CDomPositionCache@MicrodomImplementation@@QEAA@XZ; void *(*)(void *)
0x180056951  mov     r8d, esi; unsigned __int64
0x180056954  mov     edx, 8; unsigned __int64
0x180056959  mov     rcx, rax; void *
0x18005695c  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180056961  jmp     short loc_180056965
0x180056963  xor     ebx, ebx
0x180056965  test    rbx, rbx
0x180056968  jz      short loc_180056982
0x18005696a  mov     [rdi+8], rbx
0x18005696e  mov     [rdi+10h], rsi
0x180056972  jmp     short loc_180056979
0x180056974  mov     ebx, 4
0x180056979  test    rbx, rbx
0x18005697c  jz      short loc_180056982
0x18005697e  xor     eax, eax
0x180056980  jmp     short loc_1800569B8
0x180056982  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180056989  mov     [rbp+var_20], 0E02h
0x180056991  mov     [rbp+var_30], rax
0x180056995  lea     rdx, [rbp+var_30]
0x180056999  lea     rax, aMicrodomimplem_13; "MicrodomImplementation::CDomPositionCac"...
0x1800569a0  mov     [rbp+var_28], rax
0x1800569a4  lea     rcx, [rbp+var_10]
0x1800569a8  lea     rax, aThisMPositionl; "this->m_PositionList.Allocate(LocationH"...
0x1800569af  mov     [rbp+var_18], rax
0x1800569b3  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800569b8  mov     rcx, [rbp+var_8]
0x1800569bc  xor     rcx, rsp; StackCookie
0x1800569bf  call    __security_check_cookie
0x1800569c4  mov     rbx, [rsp+50h+arg_10]
0x1800569cc  add     rsp, 50h
0x1800569d0  pop     rdi
0x1800569d1  pop     rsi
0x1800569d2  pop     rbp
0x1800569d3  retn
```
