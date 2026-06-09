# CServiceModule::OnSecureDesktopSwitch(CPenSession *)

- ea: `0x18000f428`
- end: `0x18000f55c`
- name: `?OnSecureDesktopSwitch@CServiceModule@@QEAAXPEAVCPenSession@@@Z`
- size: `308`
- prototype: `void __fastcall(CServiceModule *__hidden this, struct CPenSession *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18000ed70`

## callees

- `0x1800010f8`
- `0x18000f428`
- `0x18001506c`
- `0x180015630`
- `0x1800286b0`
- `0x18002b3a8`
- `0x18002b404`

## string_xrefs

- `0x18000f45a`: `PENSERVICE_CServiceModule::OnSecureDesktopSwitch`
- `0x18000f4bb`: `PENSERVICE_CServiceModule::OnSecureDesktopSwitch`
- `0x18000f533`: `PENSERVICE_CServiceModule::OnSecureDesktopSwitch`

## pseudocode

```c
void __fastcall CServiceModule::OnSecureDesktopSwitch(CServiceModule *this, struct CPenSession *a2)
{
  __int64 v4; // rcx
  unsigned int v5; // edx

  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_sd(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      118,
      (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      (unsigned int)"PENSERVICE_CServiceModule::OnSecureDesktopSwitch",
      *((_DWORD *)a2 + 1));
  if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v4,
      (int)&dword_180039CA4);
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_sd(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      119,
      (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      (unsigned int)"PENSERVICE_CServiceModule::OnSecureDesktopSwitch",
      *((_DWORD *)a2 + 1));
  CServiceModule::_RemovePenProcessesWorker(this, 1, 0x28u, *((_DWORD *)a2 + 1));
  v5 = *((_DWORD *)a2 + 1);
  *((_BYTE *)a2 + 9) = 0;
  CServiceModule::_StartPenProcessesWorker(this, v5, 0, 0, 1, 0);
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      120,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::OnSecureDesktopSwitch");
}

```

## disassembly

```asm
0x18000f428  mov     [rsp+arg_0], rbx
0x18000f42d  mov     [rsp+arg_8], rdi
0x18000f432  push    r12
0x18000f434  sub     rsp, 40h
0x18000f438  mov     rbx, rdx
0x18000f43b  mov     rdi, rcx
0x18000f43e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f445  lea     r12, WPP_GLOBAL_Control
0x18000f44c  cmp     rcx, r12
0x18000f44f  jz      short loc_18000F47A
0x18000f451  test    byte ptr [rcx+1Ch], 10h
0x18000f455  jz      short loc_18000F47A
0x18000f457  mov     eax, [rbx+4]
0x18000f45a  lea     r9, aPenserviceCser_19; "PENSERVICE_CServiceModule::OnSecureDesk"...
0x18000f461  mov     rcx, [rcx+10h]
0x18000f465  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18000f46c  mov     edx, 76h ; 'v'
0x18000f471  mov     [rsp+48h+var_28], eax
0x18000f475  call    WPP_SF_sd
0x18000f47a  mov     eax, cs:dword_1800411A8
0x18000f480  cmp     eax, 5
0x18000f483  jbe     short loc_18000F4A6
0x18000f485  mov     edx, 4000000h
0x18000f48a  lea     rcx, dword_1800411A8
0x18000f491  call    _tlgKeywordOn
0x18000f496  test    al, al
0x18000f498  jz      short loc_18000F4A6
0x18000f49a  lea     rdx, dword_180039CA4
0x18000f4a1  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18000f4a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f4ad  cmp     rcx, r12
0x18000f4b0  jz      short loc_18000F4DB
0x18000f4b2  test    byte ptr [rcx+1Ch], 10h
0x18000f4b6  jz      short loc_18000F4DB
0x18000f4b8  mov     eax, [rbx+4]
0x18000f4bb  lea     r9, aPenserviceCser_19; "PENSERVICE_CServiceModule::OnSecureDesk"...
0x18000f4c2  mov     rcx, [rcx+10h]
0x18000f4c6  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18000f4cd  mov     edx, 77h ; 'w'
0x18000f4d2  mov     [rsp+48h+var_28], eax
0x18000f4d6  call    WPP_SF_sd
0x18000f4db  mov     r9d, [rbx+4]; unsigned int
0x18000f4df  mov     edx, 1; unsigned int
0x18000f4e4  mov     rcx, rdi; this
0x18000f4e7  lea     r8d, [rdx+27h]; unsigned int
0x18000f4eb  call    ?_RemovePenProcessesWorker@CServiceModule@@AEAAXKKK@Z; CServiceModule::_RemovePenProcessesWorker(ulong,ulong,ulong)
0x18000f4f0  mov     edx, [rbx+4]; unsigned int
0x18000f4f3  xor     r9d, r9d; int
0x18000f4f6  mov     [rsp+48h+var_18], 0; int
0x18000f4fe  xor     r8d, r8d; enum _WTS_CONNECTSTATE_CLASS
0x18000f501  mov     [rsp+48h+var_20], 0; int
0x18000f509  mov     rcx, rdi; Context
0x18000f50c  mov     [rsp+48h+var_28], 1; int
0x18000f514  mov     byte ptr [rbx+9], 0
0x18000f518  call    ?_StartPenProcessesWorker@CServiceModule@@AEAAXKW4_WTS_CONNECTSTATE_CLASS@@HHHH@Z; CServiceModule::_StartPenProcessesWorker(ulong,_WTS_CONNECTSTATE_CLASS,int,int,int,int)
0x18000f51d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f524  cmp     rcx, r12
0x18000f527  jz      short loc_18000F54B
0x18000f529  test    byte ptr [rcx+1Ch], 10h
0x18000f52d  jz      short loc_18000F54B
0x18000f52f  mov     rcx, [rcx+10h]
0x18000f533  lea     r9, aPenserviceCser_19; "PENSERVICE_CServiceModule::OnSecureDesk"...
0x18000f53a  mov     edx, 78h ; 'x'
0x18000f53f  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18000f546  call    WPP_SF_s
0x18000f54b  mov     rbx, [rsp+48h+arg_0]
0x18000f550  mov     rdi, [rsp+48h+arg_8]
0x18000f555  add     rsp, 40h
0x18000f559  pop     r12
0x18000f55b  retn
```
