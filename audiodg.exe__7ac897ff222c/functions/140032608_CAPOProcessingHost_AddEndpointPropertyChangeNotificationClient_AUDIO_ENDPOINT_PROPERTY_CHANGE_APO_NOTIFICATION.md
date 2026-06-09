# CAPOProcessingHost::AddEndpointPropertyChangeNotificationClient(AUDIO_ENDPOINT_PROPERTY_CHANGE_APO_NOTIFICATION_DESCRIPTOR *,CAPOProcessingHostObject *)

- ea: `0x140032608`
- end: `0x1400327a1`
- name: `?AddEndpointPropertyChangeNotificationClient@CAPOProcessingHost@@AEAAJPEAUAUDIO_ENDPOINT_PROPERTY_CHANGE_APO_NOTIFICATION_DESCRIPTOR@@PEAVCAPOProcessingHostObject@@@Z`
- size: `409`
- prototype: `int(CAPOProcessingHost *__hidden this, struct AUDIO_ENDPOINT_PROPERTY_CHANGE_APO_NOTIFICATION_DESCRIPTOR *, struct CAPOProcessingHostObject *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14003d3b0`

## callees

- `0x140008124`
- `0x14000c33c`
- `0x14002268c`
- `0x140032608`
- `0x140034efc`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140032716`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140032764`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003277a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140032716`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140032764`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003277a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140032696`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140032696`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400326e8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400326e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CAPOProcessingHost::AddEndpointPropertyChangeNotificationClient(
        CAPOProcessingHost *this,
        struct IMMDevice **a2,
        struct CAPOProcessingHostObject *a3)
{
  struct IMMDevice *v5; // rdx
  unsigned int v6; // ebx
  int EndpointNotificationHandler; // eax
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  _BYTE *v9; // r14
  __int64 v10; // rcx
  HRESULT Instance; // eax
  HRESULT v12; // ebp
  int v13; // eax
  unsigned int v14; // edi
  int ppv; // [rsp+20h] [rbp-28h]
  int ppva; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  CAPOEndpointNotificationsHandler *v19; // [rsp+58h] [rbp+10h] BYREF
  char *v20; // [rsp+68h] [rbp+20h]

  v5 = *a2;
  if ( v5 )
  {
    v19 = 0;
    EndpointNotificationHandler = CAPOProcessingHost::GetEndpointNotificationHandler(this, v5, &v19);
    v6 = EndpointNotificationHandler;
    if ( EndpointNotificationHandler < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAD,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoprocessinghost.cpp",
        (const char *)(unsigned int)EndpointNotificationHandler,
        ppv);
LABEL_20:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
      return v6;
    }
    CAPOEndpointNotificationsHandler::AddEndpointPropertyChangeNotificationClient(v19, a3);
    v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    v20 = (char *)this + 32;
    v9 = (char *)this + 72;
    if ( !*((_BYTE *)this + 72) )
    {
      v10 = *((_QWORD *)this + 3);
      *((_QWORD *)this + 3) = 0;
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      Instance = CoCreateInstance(
                   &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
                   0,
                   0x17u,
                   &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
                   (LPVOID *)this + 3);
      v12 = Instance;
      if ( Instance < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB4,
          (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoprocessinghost.cpp",
          (const char *)(unsigned int)Instance,
          ppva);
        if ( this != (CAPOProcessingHost *)-32LL )
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
        v6 = v12;
        goto LABEL_20;
      }
      v13 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**((_QWORD **)this + 3) + 48LL))(
              *((_QWORD *)this + 3),
              ((unsigned __int64)this + 8) & -(__int64)(this != 0));
      v14 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB5,
          (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoprocessinghost.cpp",
          (const char *)(unsigned int)v13,
          ppva);
        if ( v8 )
          LeaveCriticalSection(v8);
        v6 = v14;
        goto LABEL_20;
      }
      *v9 = 1;
    }
    if ( v8 )
      LeaveCriticalSection(v8);
    v6 = 0;
    goto LABEL_20;
  }
  v6 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xAA,
    (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoprocessinghost.cpp",
    (const char *)0x80004003LL,
    ppv);
  return v6;
}

```

## disassembly

```asm
0x140032608  mov     [rsp+arg_0], rbx
0x14003260d  mov     [rsp+arg_10], rbp
0x140032612  push    rsi
0x140032613  push    rdi
0x140032614  push    r14
0x140032616  sub     rsp, 30h
0x14003261a  mov     rsi, r8
0x14003261d  mov     rdi, rcx
0x140032620  mov     rdx, [rdx]; struct IMMDevice *
0x140032623  test    rdx, rdx
0x140032626  jnz     short loc_14003264B
0x140032628  mov     rcx, [rsp+48h]; this
0x14003262d  mov     ebx, 80004003h
0x140032632  mov     r9d, ebx; char *
0x140032635  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14003263c  mov     edx, 0AAh; void *
0x140032641  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140032646  jmp     loc_14003278C
0x14003264b  mov     [rsp+48h+arg_8], 0
0x140032654  lea     r8, [rsp+48h+arg_8]; struct CAPOEndpointNotificationsHandler **
0x140032659  call    ?GetEndpointNotificationHandler@CAPOProcessingHost@@AEAAJPEAUIMMDevice@@PEAPEAVCAPOEndpointNotificationsHandler@@@Z; CAPOProcessingHost::GetEndpointNotificationHandler(IMMDevice *,CAPOEndpointNotificationsHandler * *)
0x14003265e  mov     ebx, eax
0x140032660  test    eax, eax
0x140032662  jns     short loc_140032682
0x140032664  mov     rcx, [rsp+48h]; this
0x140032669  mov     r9d, eax; char *
0x14003266c  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140032673  mov     edx, 0ADh; void *
0x140032678  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003267d  jmp     loc_140032782
0x140032682  mov     rdx, rsi; struct CAPOProcessingHostObject *
0x140032685  mov     rcx, [rsp+48h+arg_8]; this
0x14003268a  call    ?AddEndpointPropertyChangeNotificationClient@CAPOEndpointNotificationsHandler@@QEAAXPEAVCAPOProcessingHostObject@@@Z; CAPOEndpointNotificationsHandler::AddEndpointPropertyChangeNotificationClient(CAPOProcessingHostObject *)
0x14003268f  lea     rbx, [rdi+20h]
0x140032693  mov     rcx, rbx; lpCriticalSection
0x140032696  call    cs:__imp_EnterCriticalSection
0x14003269c  mov     [rsp+48h+arg_18], rbx
0x1400326a1  lea     r14, [rdi+48h]
0x1400326a5  cmp     byte ptr [r14], 0
0x1400326a9  jnz     loc_140032772
0x1400326af  lea     rsi, [rdi+18h]
0x1400326b3  mov     rcx, [rsi]
0x1400326b6  mov     qword ptr [rsi], 0
0x1400326bd  test    rcx, rcx
0x1400326c0  jz      short loc_1400326CF
0x1400326c2  mov     rax, [rcx]
0x1400326c5  mov     rax, [rax+10h]
0x1400326c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400326ce  nop
0x1400326cf  mov     qword ptr [rsp+48h+ppv], rsi; int
0x1400326d4  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x1400326db  xor     edx, edx; pUnkOuter
0x1400326dd  lea     r8d, [rdx+17h]; dwClsContext
0x1400326e1  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x1400326e8  call    cs:__imp_CoCreateInstance
0x1400326ee  mov     ebp, eax
0x1400326f0  test    eax, eax
0x1400326f2  jns     short loc_140032720
0x1400326f4  mov     rcx, [rsp+48h]; this
0x1400326f9  mov     r9d, eax; char *
0x1400326fc  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140032703  mov     edx, 0B4h; void *
0x140032708  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003270d  nop
0x14003270e  test    rbx, rbx
0x140032711  jz      short loc_14003271C
0x140032713  mov     rcx, rbx; lpCriticalSection
0x140032716  call    cs:__imp_LeaveCriticalSection
0x14003271c  mov     ebx, ebp
0x14003271e  jmp     short loc_140032782
0x140032720  mov     rcx, [rsi]
0x140032723  mov     r8, [rcx]
0x140032726  lea     rax, [rdi+8]
0x14003272a  neg     rdi
0x14003272d  sbb     rdx, rdx
0x140032730  and     rdx, rax
0x140032733  mov     rax, [r8+30h]
0x140032737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003273c  mov     edi, eax
0x14003273e  test    eax, eax
0x140032740  jns     short loc_14003276E
0x140032742  mov     rcx, [rsp+48h]; this
0x140032747  mov     r9d, eax; char *
0x14003274a  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140032751  mov     edx, 0B5h; void *
0x140032756  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003275b  nop
0x14003275c  test    rbx, rbx
0x14003275f  jz      short loc_14003276A
0x140032761  mov     rcx, rbx; lpCriticalSection
0x140032764  call    cs:__imp_LeaveCriticalSection
0x14003276a  mov     ebx, edi
0x14003276c  jmp     short loc_140032782
0x14003276e  mov     byte ptr [r14], 1
0x140032772  test    rbx, rbx
0x140032775  jz      short loc_140032780
0x140032777  mov     rcx, rbx; lpCriticalSection
0x14003277a  call    cs:__imp_LeaveCriticalSection
0x140032780  xor     ebx, ebx
0x140032782  lea     rcx, [rsp+48h+arg_8]
0x140032787  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14003278c  mov     eax, ebx
0x14003278e  mov     rbx, [rsp+48h+arg_0]
0x140032793  mov     rbp, [rsp+48h+arg_10]
0x140032798  add     rsp, 30h
0x14003279c  pop     r14
0x14003279e  pop     rdi
0x14003279f  pop     rsi
0x1400327a0  retn
```
