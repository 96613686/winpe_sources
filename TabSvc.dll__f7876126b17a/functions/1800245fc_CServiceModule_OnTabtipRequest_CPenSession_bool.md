# CServiceModule::OnTabtipRequest(CPenSession *,bool)

- ea: `0x1800245fc`
- end: `0x180024727`
- name: `?OnTabtipRequest@CServiceModule@@QEAAXPEAVCPenSession@@_N@Z`
- size: `299`
- prototype: `void __fastcall(PVOID Context, struct CPenSession *, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18000ed70`

## callees

- `0x180001ec0`
- `0x180014a80`
- `0x180015630`
- `0x1800245fc`
- `0x1800285c8`
- `0x18002b3a8`
- `0x18002b404`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800246ea`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800246ea`

## string_xrefs

- `0x18002462a`: `PENSERVICE_CServiceModule::OnTabtipRequest`
- `0x180024706`: `PENSERVICE_CServiceModule::OnTabtipRequest`

## pseudocode

```c
void __fastcall CServiceModule::OnTabtipRequest(PVOID Context, struct CPenSession *a2, char a3)
{
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  CServiceModule *v9; // rcx
  bool v10; // zf
  int v11; // eax
  unsigned int v12; // edx
  __int128 v13; // [rsp+30h] [rbp-48h] BYREF
  __int64 v14; // [rsp+40h] [rbp-38h]
  int v15; // [rsp+90h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_sd(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      110,
      (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      (unsigned int)"PENSERVICE_CServiceModule::OnTabtipRequest",
      *((_DWORD *)a2 + 1));
  if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
  {
    v15 = *((_DWORD *)a2 + 1);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v6,
      (int)&dword_18003973C,
      v7,
      v8,
      (__int64)&v15);
  }
  v9 = (CServiceModule *)*((_QWORD *)Context + 70);
  v14 = 1;
  v13 = 0;
  v10 = *((_DWORD *)v9 + 3) == 0;
  v11 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 4));
  DWORD2(v13) = 1;
  if ( v10 )
    v11 = 1;
  v12 = *((_DWORD *)a2 + 1);
  DWORD1(v13) = v11;
  if ( !CServiceModule::_IsRailSession(v9, v12) )
    CServiceModule::StartPenProcessAsUser(
      Context,
      *((const struct CPenProcessInfo **)Context + 70),
      a2,
      (const struct CPenProcessStartInfo *)&v13);
  if ( !a3 )
    SetEvent(*((HANDLE *)a2 + 3));
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      111,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::OnTabtipRequest");
}

```

## disassembly

```asm
0x1800245fc  push    rbx
0x1800245fe  push    rbp
0x1800245ff  push    rsi
0x180024600  push    rdi
0x180024601  sub     rsp, 58h
0x180024605  mov     sil, r8b
0x180024608  mov     rbx, rdx
0x18002460b  mov     rdi, rcx
0x18002460e  mov     rcx, cs:WPP_GLOBAL_Control
0x180024615  lea     rbp, WPP_GLOBAL_Control
0x18002461c  cmp     rcx, rbp
0x18002461f  jz      short loc_18002464A
0x180024621  test    byte ptr [rcx+1Ch], 10h
0x180024625  jz      short loc_18002464A
0x180024627  mov     eax, [rbx+4]
0x18002462a  lea     r9, aPenserviceCser_5; "PENSERVICE_CServiceModule::OnTabtipRequ"...
0x180024631  mov     rcx, [rcx+10h]
0x180024635  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18002463c  mov     edx, 6Eh ; 'n'
0x180024641  mov     dword ptr [rsp+78h+var_58], eax
0x180024645  call    WPP_SF_sd
0x18002464a  mov     eax, cs:dword_1800411A8
0x180024650  cmp     eax, 5
0x180024653  jbe     short loc_18002468D
0x180024655  mov     edx, 4000000h
0x18002465a  lea     rcx, dword_1800411A8
0x180024661  call    _tlgKeywordOn
0x180024666  test    al, al
0x180024668  jz      short loc_18002468D
0x18002466a  mov     eax, [rbx+4]
0x18002466d  lea     rdx, dword_18003973C
0x180024674  mov     [rsp+78h+arg_10], eax
0x18002467b  lea     rax, [rsp+78h+arg_10]
0x180024683  mov     [rsp+78h+var_58], rax
0x180024688  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18002468d  mov     rcx, [rdi+230h]; this
0x180024694  mov     edx, 1
0x180024699  xorps   xmm0, xmm0
0x18002469c  mov     [rsp+78h+var_38], rdx
0x1800246a1  movups  [rsp+78h+var_48], xmm0
0x1800246a6  cmp     dword ptr [rcx+0Ch], 0
0x1800246aa  psrldq  xmm0, 4
0x1800246af  movd    eax, xmm0
0x1800246b3  mov     dword ptr [rsp+78h+var_48+8], edx
0x1800246b7  cmovz   eax, edx
0x1800246ba  mov     edx, [rbx+4]; unsigned int
0x1800246bd  mov     dword ptr [rsp+78h+var_48+4], eax
0x1800246c1  call    ?_IsRailSession@CServiceModule@@AEAA_NK@Z; CServiceModule::_IsRailSession(ulong)
0x1800246c6  test    al, al
0x1800246c8  jnz     short loc_1800246E1
0x1800246ca  mov     rdx, [rdi+230h]; struct CPenProcessInfo *
0x1800246d1  lea     r9, [rsp+78h+var_48]; struct CPenProcessStartInfo *
0x1800246d6  mov     r8, rbx; struct CPenSession *
0x1800246d9  mov     rcx, rdi; Context
0x1800246dc  call    ?StartPenProcessAsUser@CServiceModule@@QEAAXPEBVCPenProcessInfo@@PEAVCPenSession@@PEBUCPenProcessStartInfo@@@Z; CServiceModule::StartPenProcessAsUser(CPenProcessInfo const *,CPenSession *,CPenProcessStartInfo const *)
0x1800246e1  test    sil, sil
0x1800246e4  jnz     short loc_1800246F0
0x1800246e6  mov     rcx, [rbx+18h]; hEvent
0x1800246ea  call    cs:__imp_SetEvent
0x1800246f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800246f7  cmp     rcx, rbp
0x1800246fa  jz      short loc_18002471E
0x1800246fc  test    byte ptr [rcx+1Ch], 10h
0x180024700  jz      short loc_18002471E
0x180024702  mov     rcx, [rcx+10h]
0x180024706  lea     r9, aPenserviceCser_5; "PENSERVICE_CServiceModule::OnTabtipRequ"...
0x18002470d  mov     edx, 6Fh ; 'o'
0x180024712  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180024719  call    WPP_SF_s
0x18002471e  add     rsp, 58h
0x180024722  pop     rdi
0x180024723  pop     rsi
0x180024724  pop     rbp
0x180024725  pop     rbx
0x180024726  retn
```
