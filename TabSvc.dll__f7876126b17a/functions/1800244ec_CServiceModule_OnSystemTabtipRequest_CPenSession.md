# CServiceModule::OnSystemTabtipRequest(CPenSession *)

- ea: `0x1800244ec`
- end: `0x1800245f6`
- name: `?OnSystemTabtipRequest@CServiceModule@@QEAAXPEAVCPenSession@@@Z`
- size: `266`
- prototype: `void __fastcall(CServiceModule *__hidden this, struct CPenSession *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18000ed70`

## callees

- `0x1800010f8`
- `0x180015630`
- `0x1800244ec`
- `0x18002718c`
- `0x1800285c8`
- `0x18002b3a8`
- `0x18002b404`

## string_xrefs

- `0x180024543`: `PENSERVICE_CServiceModule::OnSystemTabtipRequest`
- `0x1800245d1`: `PENSERVICE_CServiceModule::OnSystemTabtipRequest`

## pseudocode

```c
void __fastcall CServiceModule::OnSystemTabtipRequest(CServiceModule *this, struct CPenSession *a2)
{
  __int64 v4; // rcx
  CServiceModule *v5; // rcx
  unsigned int v6; // edx
  bool v7; // zf
  int v8; // eax
  __int128 v9; // [rsp+30h] [rbp-48h] BYREF
  __int64 v10; // [rsp+40h] [rbp-38h]

  if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v4,
      (int)&byte_18003AABF);
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_sd(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      114,
      (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      (unsigned int)"PENSERVICE_CServiceModule::OnSystemTabtipRequest",
      *((_DWORD *)a2 + 1));
  v5 = (CServiceModule *)*((_QWORD *)this + 72);
  v6 = *((_DWORD *)a2 + 1);
  v9 = 0;
  v10 = 1;
  v7 = *((_DWORD *)v5 + 3) == 0;
  v8 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 4));
  LODWORD(v9) = 1;
  DWORD2(v9) = 1;
  if ( v7 )
    v8 = 1;
  DWORD1(v9) = v8;
  if ( !CServiceModule::_IsRailSession(v5, v6) )
    CServiceModule::StartPenProcessAsSystem(
      this,
      *((const struct CPenProcessInfo **)this + 72),
      a2,
      (const struct CPenProcessStartInfo *)&v9);
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      115,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::OnSystemTabtipRequest");
  *((_BYTE *)a2 + 9) = 1;
}

```

## disassembly

```asm
0x1800244ec  push    rbx
0x1800244ee  push    rbp
0x1800244ef  push    rsi
0x1800244f0  push    rdi
0x1800244f1  sub     rsp, 58h
0x1800244f5  mov     eax, cs:dword_1800411A8
0x1800244fb  mov     rbx, rdx
0x1800244fe  mov     rdi, rcx
0x180024501  cmp     eax, 5
0x180024504  jbe     short loc_180024527
0x180024506  mov     edx, 4000000h
0x18002450b  lea     rcx, dword_1800411A8
0x180024512  call    _tlgKeywordOn
0x180024517  test    al, al
0x180024519  jz      short loc_180024527
0x18002451b  lea     rdx, byte_18003AABF
0x180024522  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180024527  mov     rcx, cs:WPP_GLOBAL_Control
0x18002452e  lea     rbp, WPP_GLOBAL_Control
0x180024535  cmp     rcx, rbp
0x180024538  jz      short loc_180024563
0x18002453a  test    byte ptr [rcx+1Ch], 10h
0x18002453e  jz      short loc_180024563
0x180024540  mov     eax, [rbx+4]
0x180024543  lea     r9, aPenserviceCser_33; "PENSERVICE_CServiceModule::OnSystemTabt"...
0x18002454a  mov     rcx, [rcx+10h]
0x18002454e  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180024555  mov     edx, 72h ; 'r'
0x18002455a  mov     [rsp+78h+var_58], eax
0x18002455e  call    WPP_SF_sd
0x180024563  mov     rcx, [rdi+240h]; this
0x18002456a  mov     esi, 1
0x18002456f  mov     edx, [rbx+4]; unsigned int
0x180024572  xorps   xmm0, xmm0
0x180024575  movups  [rsp+78h+var_48], xmm0
0x18002457a  mov     [rsp+78h+var_38], rsi
0x18002457f  cmp     dword ptr [rcx+0Ch], 0
0x180024583  psrldq  xmm0, 4
0x180024588  movd    eax, xmm0
0x18002458c  mov     dword ptr [rsp+78h+var_48], esi
0x180024590  mov     dword ptr [rsp+78h+var_48+8], esi
0x180024594  cmovz   eax, esi
0x180024597  mov     dword ptr [rsp+78h+var_48+4], eax
0x18002459b  call    ?_IsRailSession@CServiceModule@@AEAA_NK@Z; CServiceModule::_IsRailSession(ulong)
0x1800245a0  test    al, al
0x1800245a2  jnz     short loc_1800245BB
0x1800245a4  mov     rdx, [rdi+240h]; struct CPenProcessInfo *
0x1800245ab  lea     r9, [rsp+78h+var_48]; struct CPenProcessStartInfo *
0x1800245b0  mov     r8, rbx; struct CPenSession *
0x1800245b3  mov     rcx, rdi; this
0x1800245b6  call    ?StartPenProcessAsSystem@CServiceModule@@QEAAXPEBVCPenProcessInfo@@PEAVCPenSession@@PEBUCPenProcessStartInfo@@@Z; CServiceModule::StartPenProcessAsSystem(CPenProcessInfo const *,CPenSession *,CPenProcessStartInfo const *)
0x1800245bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800245c2  cmp     rcx, rbp
0x1800245c5  jz      short loc_1800245E9
0x1800245c7  test    byte ptr [rcx+1Ch], 10h
0x1800245cb  jz      short loc_1800245E9
0x1800245cd  mov     rcx, [rcx+10h]
0x1800245d1  lea     r9, aPenserviceCser_33; "PENSERVICE_CServiceModule::OnSystemTabt"...
0x1800245d8  mov     edx, 73h ; 's'
0x1800245dd  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x1800245e4  call    WPP_SF_s
0x1800245e9  mov     [rbx+9], sil
0x1800245ed  add     rsp, 58h
0x1800245f1  pop     rdi
0x1800245f2  pop     rsi
0x1800245f3  pop     rbp
0x1800245f4  pop     rbx
0x1800245f5  retn
```
