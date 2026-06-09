# Streaming::StrmGlobalData::~StrmGlobalData(void)

- ea: `0x140001104`
- end: `0x1400011fc`
- name: `??1StrmGlobalData@Streaming@@QEAA@XZ`
- size: `248`
- prototype: `void __fastcall(Streaming::StrmGlobalData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140013540`

## callees

- `0x140001044`
- `0x140001104`
- `0x1400016c4`
- `0x1400053a4`
- `0x140013a18`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400011be`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400011dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400011be`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400011dd`
- `FLTMGR!FltCloseCommunicationPort` at `0x14000112a`
- `FLTMGR!FltCloseCommunicationPort` at `0x140001156`
- `FLTMGR!FltCloseCommunicationPort` at `0x14000112a`
- `FLTMGR!FltCloseCommunicationPort` at `0x140001156`
- `FLTMGR!FltUnregisterFilter` at `0x140001172`
- `FLTMGR!FltUnregisterFilter` at `0x140001172`

## pseudocode

```c
void __fastcall Streaming::StrmGlobalData::~StrmGlobalData(Streaming::StrmGlobalData *this)
{
  PFLT_PORT *v1; // rdi
  PFLT_PORT *v3; // rdi
  struct _FLT_FILTER *v4; // rcx
  void *v5; // rdi
  void *v6; // rcx

  v1 = (PFLT_PORT *)*((_QWORD *)this + 4);
  if ( v1 )
  {
    Streaming::Messaging::UserCommunication::DisconnectClient(*((Streaming::Messaging::UserCommunication **)this + 4));
    if ( *v1 )
    {
      FltCloseCommunicationPort(*v1);
      *v1 = 0;
    }
  }
  v3 = (PFLT_PORT *)*((_QWORD *)this + 5);
  if ( v3 )
  {
    Streaming::Messaging::UserCommunication::DisconnectClient(*((Streaming::Messaging::UserCommunication **)this + 5));
    if ( *v3 )
    {
      FltCloseCommunicationPort(*v3);
      *v3 = 0;
    }
  }
  v4 = (struct _FLT_FILTER *)*((_QWORD *)this + 1);
  if ( v4 )
    FltUnregisterFilter(v4);
  McGenEventUnregister_EtwUnregister(PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context);
  McGenEventUnregister_EtwUnregister(PROVIDER_MICROSOFT_APPV_CLIENT_Context);
  appv::shared::kernel::auto_ptr<Streaming::Messaging::UserCommunication,Streaming::Messaging::UserCommunicationDelete>::~auto_ptr<Streaming::Messaging::UserCommunication,Streaming::Messaging::UserCommunicationDelete>((Streaming::Messaging::UserCommunication **)this + 5);
  appv::shared::kernel::auto_ptr<Streaming::Messaging::UserCommunication,Streaming::Messaging::UserCommunicationDelete>::~auto_ptr<Streaming::Messaging::UserCommunication,Streaming::Messaging::UserCommunicationDelete>((Streaming::Messaging::UserCommunication **)this + 4);
  v5 = (void *)*((_QWORD *)this + 3);
  if ( v5 )
  {
    Streaming::Messaging::UserCommunication::~UserCommunication(*((Streaming::Messaging::UserCommunication **)this + 3));
    ExFreePoolWithTag(v5, 0);
    *((_QWORD *)this + 3) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 2);
  if ( v6 )
  {
    ExFreePoolWithTag(v6, 0);
    *((_QWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x140001104  push    rbx
0x140001106  push    rsi
0x140001107  push    rdi
0x140001108  push    r14
0x14000110a  sub     rsp, 28h
0x14000110e  mov     rdi, [rcx+20h]
0x140001112  mov     rbx, rcx
0x140001115  test    rdi, rdi
0x140001118  jz      short loc_14000113D
0x14000111a  mov     rcx, rdi; this
0x14000111d  call    ?DisconnectClient@UserCommunication@Messaging@Streaming@@QEAAXXZ; Streaming::Messaging::UserCommunication::DisconnectClient(void)
0x140001122  mov     rcx, [rdi]; ServerPort
0x140001125  test    rcx, rcx
0x140001128  jz      short loc_14000113D
0x14000112a  call    cs:__imp_FltCloseCommunicationPort
0x140001131  nop     dword ptr [rax+rax+00h]
0x140001136  mov     qword ptr [rdi], 0
0x14000113d  mov     rdi, [rbx+28h]
0x140001141  test    rdi, rdi
0x140001144  jz      short loc_140001169
0x140001146  mov     rcx, rdi; this
0x140001149  call    ?DisconnectClient@UserCommunication@Messaging@Streaming@@QEAAXXZ; Streaming::Messaging::UserCommunication::DisconnectClient(void)
0x14000114e  mov     rcx, [rdi]; ServerPort
0x140001151  test    rcx, rcx
0x140001154  jz      short loc_140001169
0x140001156  call    cs:__imp_FltCloseCommunicationPort
0x14000115d  nop     dword ptr [rax+rax+00h]
0x140001162  mov     qword ptr [rdi], 0
0x140001169  mov     rcx, [rbx+8]; Filter
0x14000116d  test    rcx, rcx
0x140001170  jz      short loc_14000117E
0x140001172  call    cs:__imp_FltUnregisterFilter
0x140001179  nop     dword ptr [rax+rax+00h]
0x14000117e  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x140001185  call    McGenEventUnregister_EtwUnregister
0x14000118a  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_Context
0x140001191  call    McGenEventUnregister_EtwUnregister
0x140001196  lea     rcx, [rbx+28h]
0x14000119a  call    ??1?$auto_ptr@VUserCommunication@Messaging@Streaming@@UUserCommunicationDelete@23@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::auto_ptr<Streaming::Messaging::UserCommunication,Streaming::Messaging::UserCommunicationDelete>::~auto_ptr<Streaming::Messaging::UserCommunication,Streaming::Messaging::UserCommunicationDelete>(void)
0x14000119f  lea     rcx, [rbx+20h]
0x1400011a3  call    ??1?$auto_ptr@VUserCommunication@Messaging@Streaming@@UUserCommunicationDelete@23@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::auto_ptr<Streaming::Messaging::UserCommunication,Streaming::Messaging::UserCommunicationDelete>::~auto_ptr<Streaming::Messaging::UserCommunication,Streaming::Messaging::UserCommunicationDelete>(void)
0x1400011a8  mov     rdi, [rbx+18h]
0x1400011ac  test    rdi, rdi
0x1400011af  jz      short loc_1400011D2
0x1400011b1  mov     rcx, rdi; this
0x1400011b4  call    ??1UserCommunication@Messaging@Streaming@@QEAA@XZ; Streaming::Messaging::UserCommunication::~UserCommunication(void)
0x1400011b9  xor     edx, edx; Tag
0x1400011bb  mov     rcx, rdi; P
0x1400011be  call    cs:__imp_ExFreePoolWithTag
0x1400011c5  nop     dword ptr [rax+rax+00h]
0x1400011ca  mov     qword ptr [rbx+18h], 0
0x1400011d2  mov     rcx, [rbx+10h]; P
0x1400011d6  test    rcx, rcx
0x1400011d9  jz      short loc_1400011F1
0x1400011db  xor     edx, edx; Tag
0x1400011dd  call    cs:__imp_ExFreePoolWithTag
0x1400011e4  nop     dword ptr [rax+rax+00h]
0x1400011e9  mov     qword ptr [rbx+10h], 0
0x1400011f1  add     rsp, 28h
0x1400011f5  pop     r14
0x1400011f7  pop     rdi
0x1400011f8  pop     rsi
0x1400011f9  pop     rbx
0x1400011fa  retn
```
