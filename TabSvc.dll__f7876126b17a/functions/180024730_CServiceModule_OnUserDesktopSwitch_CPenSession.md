# CServiceModule::OnUserDesktopSwitch(CPenSession *)

- ea: `0x180024730`
- end: `0x180024857`
- name: `?OnUserDesktopSwitch@CServiceModule@@QEAAXPEAVCPenSession@@@Z`
- size: `295`
- prototype: `void __fastcall(PVOID Context, struct CPenSession *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18000ed70`

## callees

- `0x1800010f8`
- `0x180014a80`
- `0x180015630`
- `0x180024730`
- `0x1800285c8`
- `0x18002b3a8`
- `0x18002b404`

## string_xrefs

- `0x18002475f`: `PENSERVICE_CServiceModule::OnUserDesktopSwitch`
- `0x180024835`: `PENSERVICE_CServiceModule::OnUserDesktopSwitch`

## pseudocode

```c
void __fastcall CServiceModule::OnUserDesktopSwitch(const struct CPenProcessInfo **Context, struct CPenSession *a2)
{
  CServiceModule *v4; // rcx
  unsigned int v5; // edx
  const struct CPenProcessInfo *v6; // rdx
  __int64 v7; // [rsp+30h] [rbp-38h] BYREF
  int v8; // [rsp+38h] [rbp-30h]
  int v9; // [rsp+3Ch] [rbp-2Ch]
  __int64 v10; // [rsp+40h] [rbp-28h]
  __int64 v11; // [rsp+48h] [rbp-20h] BYREF
  int v12; // [rsp+50h] [rbp-18h]
  int v13; // [rsp+54h] [rbp-14h]
  __int64 v14; // [rsp+58h] [rbp-10h]

  v4 = (CServiceModule *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_sd(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      116,
      (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      (unsigned int)"PENSERVICE_CServiceModule::OnUserDesktopSwitch",
      *((_DWORD *)a2 + 1));
  if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)v4,
      (int)&dword_18003A42C);
  v5 = *((_DWORD *)a2 + 1);
  v7 = 0;
  v8 = 0;
  v10 = 0;
  v9 = 1;
  if ( !CServiceModule::_IsRailSession(v4, v5) )
    CServiceModule::StartPenProcessAsUser(Context, Context[70], a2, (const struct CPenProcessStartInfo *)&v7);
  v6 = Context[73];
  v11 = 0;
  v12 = 0;
  v14 = 0;
  v13 = 1;
  CServiceModule::StartPenProcessAsUser(Context, v6, a2, (const struct CPenProcessStartInfo *)&v11);
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      117,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::OnUserDesktopSwitch");
}

```

## disassembly

```asm
0x180024730  push    rbp
0x180024732  push    rbx
0x180024733  push    rdi
0x180024734  push    r15
0x180024736  mov     rbp, rsp
0x180024739  sub     rsp, 68h
0x18002473d  mov     rbx, rdx
0x180024740  mov     rdi, rcx
0x180024743  mov     rcx, cs:WPP_GLOBAL_Control
0x18002474a  lea     r15, WPP_GLOBAL_Control
0x180024751  cmp     rcx, r15
0x180024754  jz      short loc_18002477F
0x180024756  test    byte ptr [rcx+1Ch], 10h
0x18002475a  jz      short loc_18002477F
0x18002475c  mov     eax, [rbx+4]
0x18002475f  lea     r9, aPenserviceCser_23; "PENSERVICE_CServiceModule::OnUserDeskto"...
0x180024766  mov     rcx, [rcx+10h]
0x18002476a  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180024771  mov     edx, 74h ; 't'
0x180024776  mov     [rsp+68h+var_48], eax
0x18002477a  call    WPP_SF_sd
0x18002477f  mov     eax, cs:dword_1800411A8
0x180024785  cmp     eax, 5
0x180024788  jbe     short loc_1800247AB
0x18002478a  mov     edx, 4000000h
0x18002478f  lea     rcx, dword_1800411A8
0x180024796  call    _tlgKeywordOn
0x18002479b  test    al, al
0x18002479d  jz      short loc_1800247AB
0x18002479f  lea     rdx, dword_18003A42C
0x1800247a6  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800247ab  mov     edx, [rbx+4]; unsigned int
0x1800247ae  mov     [rbp+var_38], 0
0x1800247b6  mov     [rbp+var_30], 0
0x1800247bd  mov     [rbp+var_28], 0
0x1800247c5  mov     [rbp+var_2C], 1
0x1800247cc  call    ?_IsRailSession@CServiceModule@@AEAA_NK@Z; CServiceModule::_IsRailSession(ulong)
0x1800247d1  test    al, al
0x1800247d3  jnz     short loc_1800247EB
0x1800247d5  mov     rdx, [rdi+230h]; struct CPenProcessInfo *
0x1800247dc  lea     r9, [rbp+var_38]; struct CPenProcessStartInfo *
0x1800247e0  mov     r8, rbx; struct CPenSession *
0x1800247e3  mov     rcx, rdi; Context
0x1800247e6  call    ?StartPenProcessAsUser@CServiceModule@@QEAAXPEBVCPenProcessInfo@@PEAVCPenSession@@PEBUCPenProcessStartInfo@@@Z; CServiceModule::StartPenProcessAsUser(CPenProcessInfo const *,CPenSession *,CPenProcessStartInfo const *)
0x1800247eb  mov     rdx, [rdi+248h]; struct CPenProcessInfo *
0x1800247f2  lea     r9, [rbp+var_20]; struct CPenProcessStartInfo *
0x1800247f6  mov     r8, rbx; struct CPenSession *
0x1800247f9  mov     [rbp+var_20], 0
0x180024801  mov     rcx, rdi; Context
0x180024804  mov     [rbp+var_18], 0
0x18002480b  mov     [rbp+var_10], 0
0x180024813  mov     [rbp+var_14], 1
0x18002481a  call    ?StartPenProcessAsUser@CServiceModule@@QEAAXPEBVCPenProcessInfo@@PEAVCPenSession@@PEBUCPenProcessStartInfo@@@Z; CServiceModule::StartPenProcessAsUser(CPenProcessInfo const *,CPenSession *,CPenProcessStartInfo const *)
0x18002481f  mov     rcx, cs:WPP_GLOBAL_Control
0x180024826  cmp     rcx, r15
0x180024829  jz      short loc_18002484D
0x18002482b  test    byte ptr [rcx+1Ch], 10h
0x18002482f  jz      short loc_18002484D
0x180024831  mov     rcx, [rcx+10h]
0x180024835  lea     r9, aPenserviceCser_23; "PENSERVICE_CServiceModule::OnUserDeskto"...
0x18002483c  mov     edx, 75h ; 'u'
0x180024841  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180024848  call    WPP_SF_s
0x18002484d  add     rsp, 68h
0x180024851  pop     r15
0x180024853  pop     rdi
0x180024854  pop     rbx
0x180024855  pop     rbp
0x180024856  retn
```
