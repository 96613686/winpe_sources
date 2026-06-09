# CServiceModule::Stop(void)

- ea: `0x180027420`
- end: `0x180027578`
- name: `?Stop@CServiceModule@@QEAAXXZ`
- size: `344`
- prototype: `void __fastcall(CServiceModule *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180025ae0`
- `0x1800265c0`

## callees

- `0x1800010f8`
- `0x180012dc0`
- `0x180015630`
- `0x18001f484`
- `0x180027420`
- `0x18002b3a8`

## import_xrefs

- `USER32!UnregisterDeviceNotification` at `0x180027529`
- `USER32!UnregisterDeviceNotification` at `0x180027529`

## string_xrefs

- `0x18002744a`: `PENSERVICE_CServiceModule::Stop`
- `0x180027556`: `PENSERVICE_CServiceModule::Stop`

## pseudocode

```c
void __fastcall CServiceModule::Stop(CServiceModule *this, unsigned int a2)
{
  __int64 v3; // rcx
  __int64 i; // rdi
  CPenSession *v5; // rcx
  void *v6; // rcx

  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      84,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::Stop");
  if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v3,
      (int)&byte_180039E97);
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 71); i = (unsigned int)(i + 1) )
  {
    v5 = *(CPenSession **)(*((_QWORD *)this + 34) + 8 * i);
    if ( v5 )
      CPenSession::`scalar deleting destructor'(v5, a2);
    *(_QWORD *)(*((_QWORD *)this + 34) + 8 * i) = 0;
  }
  SH<void *,SH_HANDLE>::Reset((char *)this + 128);
  SH<void *,SH_HANDLE>::Reset((char *)this + 144);
  SH<void *,SH_HANDLE>::Reset((char *)this + 136);
  SH<void *,SH_HANDLE>::Reset((char *)this + 152);
  SH<void *,SH_HANDLE>::Reset((char *)this + 168);
  SH<void *,SH_HANDLE>::Reset((char *)this + 176);
  SH<void *,SH_HANDLE>::Reset((char *)this + 120);
  SH<void *,SH_HANDLE>::Reset((char *)this + 96);
  v6 = (void *)*((_QWORD *)this + 7);
  if ( v6 )
  {
    UnregisterDeviceNotification(v6);
    *((_QWORD *)this + 7) = 0;
  }
  SH<void *,SH_HANDLE>::Reset((char *)this + 48);
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      85,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::Stop");
}

```

## disassembly

```asm
0x180027420  push    rbx
0x180027422  push    rsi
0x180027423  push    rdi
0x180027424  push    r14
0x180027426  sub     rsp, 28h
0x18002742a  mov     rbx, rcx
0x18002742d  mov     rcx, cs:WPP_GLOBAL_Control
0x180027434  lea     r14, WPP_GLOBAL_Control
0x18002743b  cmp     rcx, r14
0x18002743e  jz      short loc_180027462
0x180027440  test    byte ptr [rcx+1Ch], 10h
0x180027444  jz      short loc_180027462
0x180027446  mov     rcx, [rcx+10h]
0x18002744a  lea     r9, aPenserviceCser_21; "PENSERVICE_CServiceModule::Stop"
0x180027451  mov     edx, 54h ; 'T'
0x180027456  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18002745d  call    WPP_SF_s
0x180027462  mov     eax, cs:dword_1800411A8
0x180027468  cmp     eax, 5
0x18002746b  jbe     short loc_18002748E
0x18002746d  mov     edx, 4000000h
0x180027472  lea     rcx, dword_1800411A8
0x180027479  call    _tlgKeywordOn
0x18002747e  test    al, al
0x180027480  jz      short loc_18002748E
0x180027482  lea     rdx, byte_180039E97
0x180027489  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18002748e  xor     edi, edi
0x180027490  cmp     [rbx+11Ch], edi
0x180027496  jbe     short loc_1800274C6
0x180027498  mov     rax, [rbx+110h]
0x18002749f  mov     rcx, [rax+rdi*8]; this
0x1800274a3  test    rcx, rcx
0x1800274a6  jz      short loc_1800274AD
0x1800274a8  call    ??_GCPenSession@@QEAAPEAXI@Z; CPenSession::`scalar deleting destructor'(uint)
0x1800274ad  mov     rax, [rbx+110h]
0x1800274b4  mov     qword ptr [rax+rdi*8], 0
0x1800274bc  inc     edi
0x1800274be  cmp     edi, [rbx+11Ch]
0x1800274c4  jb      short loc_180027498
0x1800274c6  lea     rcx, [rbx+80h]
0x1800274cd  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x1800274d2  lea     rcx, [rbx+90h]
0x1800274d9  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x1800274de  lea     rcx, [rbx+88h]
0x1800274e5  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x1800274ea  lea     rcx, [rbx+98h]
0x1800274f1  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x1800274f6  lea     rcx, [rbx+0A8h]
0x1800274fd  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x180027502  lea     rcx, [rbx+0B0h]
0x180027509  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x18002750e  lea     rcx, [rbx+78h]
0x180027512  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x180027517  lea     rcx, [rbx+60h]
0x18002751b  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x180027520  mov     rcx, [rbx+38h]; Handle
0x180027524  test    rcx, rcx
0x180027527  jz      short loc_180027537
0x180027529  call    cs:__imp_UnregisterDeviceNotification
0x18002752f  mov     qword ptr [rbx+38h], 0
0x180027537  lea     rcx, [rbx+30h]
0x18002753b  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x180027540  mov     rcx, cs:WPP_GLOBAL_Control
0x180027547  cmp     rcx, r14
0x18002754a  jz      short loc_18002756E
0x18002754c  test    byte ptr [rcx+1Ch], 10h
0x180027550  jz      short loc_18002756E
0x180027552  mov     rcx, [rcx+10h]
0x180027556  lea     r9, aPenserviceCser_21; "PENSERVICE_CServiceModule::Stop"
0x18002755d  mov     edx, 55h ; 'U'
0x180027562  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180027569  call    WPP_SF_s
0x18002756e  add     rsp, 28h
0x180027572  pop     r14
0x180027574  pop     rdi
0x180027575  pop     rsi
0x180027576  pop     rbx
0x180027577  retn
```
