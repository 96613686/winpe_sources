# CMidi2MidiSrvConfigurationManager::Initialize(_GUID,IMidiDeviceManager *,IMidiServiceConfigurationManager *)

- ea: `0x18000c250`
- end: `0x18000c3aa`
- name: `?Initialize@CMidi2MidiSrvConfigurationManager@@UEAAJU_GUID@@PEAUIMidiDeviceManager@@PEAUIMidiServiceConfigurationManager@@@Z`
- size: `346`
- prototype: `__int64 __fastcall(CMidi2MidiSrvConfigurationManager *__hidden this, struct _GUID *__struct_ptr, struct IMidiDeviceManager *, struct IMidiServiceConfigurationManager *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task`

## callees

- `0x1800017d0`
- `0x180002494`
- `0x1800028ec`
- `0x180007e24`
- `0x180009bf8`
- `0x18000c250`
- `0x18000d190`
- `0x1800136c0`

## string_xrefs

- `0x18000c273`: `CMidi2MidiSrvConfigurationManager::Initialize`
- `0x18000c2ff`: `avcore\midi2\transport\midisrvtransport\midi2.midisrvconfigurationmanager.cpp`
- `0x18000c381`: `avcore\midi2\transport\midisrvtransport\midi2.midisrvconfigurationmanager.cpp`

## pseudocode

```c
__int64 __fastcall CMidi2MidiSrvConfigurationManager::Initialize(
        struct _GUID *this,
        struct _GUID *a2,
        struct IMidiDeviceManager *a3,
        struct IMidiServiceConfigurationManager *a4)
{
  _DWORD *v6; // rcx
  int v7; // r8d
  int v8; // r9d
  CMidiXProc **v9; // rax
  CMidiXProc **v10; // rbx
  int v11; // eax
  unsigned int v12; // esi
  CMidiXProc *v13; // rdi
  CMidiXProc **v15; // rsi
  CMidiXProc *v16; // rbx
  int v17; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  struct _GUID *v19; // [rsp+50h] [rbp+8h] BYREF
  const char *v20; // [rsp+58h] [rbp+10h] BYREF

  v6 = (_DWORD *)*((_QWORD *)MidiSrvTransportTelemetryProvider::Instance() + 1);
  if ( *v6 > 4u )
  {
    v19 = this;
    v20 = "CMidi2MidiSrvConfigurationManager::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v6,
      (unsigned int)byte_18001A10B,
      v7,
      v8,
      (__int64)&v20,
      (__int64)&v19);
  }
  this[2] = *a2;
  v9 = (CMidiXProc **)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v9;
  if ( v9 )
  {
    v9[3] = 0;
    *v9 = 0;
    v9[1] = 0;
    v9[2] = 0;
    v11 = CMidi2MidiSrv::Initialize((CMidi2MidiSrv *)v9);
    v12 = v11;
    if ( v11 >= 0 )
    {
      v15 = *(CMidiXProc ***)this[1].Data4;
      *(_QWORD *)this[1].Data4 = v10;
      if ( v15 )
      {
        v16 = v15[2];
        if ( v16 )
        {
          CMidiXProc::~CMidiXProc(v15[2]);
          operator delete(v16);
        }
        operator delete(v15);
      }
      LOBYTE(this[3].Data1) = 1;
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x24,
        (unsigned int)"avcore\\midi2\\transport\\midisrvtransport\\midi2.midisrvconfigurationmanager.cpp",
        (const char *)(unsigned int)v11,
        v17);
      v13 = v10[2];
      if ( v13 )
      {
        CMidiXProc::~CMidiXProc(v10[2]);
        operator delete(v13);
      }
      operator delete(v10);
      return v12;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"avcore\\midi2\\transport\\midisrvtransport\\midi2.midisrvconfigurationmanager.cpp",
      (const char *)0x8007000ELL,
      v17);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18000c250  mov     [rsp+arg_10], rbx
0x18000c255  push    rsi
0x18000c256  push    rdi
0x18000c257  push    r14
0x18000c259  sub     rsp, 30h
0x18000c25d  mov     rbx, rdx
0x18000c260  mov     rdi, rcx
0x18000c263  call    ?Instance@MidiSrvTransportTelemetryProvider@@KAPEAV1@XZ; MidiSrvTransportTelemetryProvider::Instance(void)
0x18000c268  mov     rcx, [rax+8]
0x18000c26c  mov     eax, [rcx]
0x18000c26e  cmp     eax, 4
0x18000c271  jbe     short loc_18000C2A4
0x18000c273  lea     rax, aCmidi2midisrvc; "CMidi2MidiSrvConfigurationManager::Init"...
0x18000c27a  mov     [rsp+48h+arg_0], rdi
0x18000c27f  mov     [rsp+48h+arg_8], rax
0x18000c284  lea     rdx, byte_18001A10B
0x18000c28b  lea     rax, [rsp+48h+arg_0]
0x18000c290  mov     [rsp+48h+var_20], rax
0x18000c295  lea     rax, [rsp+48h+arg_8]
0x18000c29a  mov     qword ptr [rsp+48h+var_28], rax; int
0x18000c29f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000c2a4  movups  xmm0, xmmword ptr [rbx]
0x18000c2a7  mov     r14d, 20h ; ' '
0x18000c2ad  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c2b4  mov     ecx, r14d; unsigned __int64
0x18000c2b7  movdqu  xmmword ptr [rdi+20h], xmm0
0x18000c2bc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c2c1  mov     rbx, rax
0x18000c2c4  test    rax, rax
0x18000c2c7  jz      loc_18000C37C
0x18000c2cd  mov     rcx, rax; this
0x18000c2d0  mov     qword ptr [rax+18h], 0
0x18000c2d8  mov     qword ptr [rax], 0
0x18000c2df  mov     qword ptr [rax+8], 0
0x18000c2e7  mov     qword ptr [rax+10h], 0
0x18000c2ef  call    ?Initialize@CMidi2MidiSrv@@QEAAJXZ; CMidi2MidiSrv::Initialize(void)
0x18000c2f4  mov     esi, eax
0x18000c2f6  test    eax, eax
0x18000c2f8  jns     short loc_18000C33E
0x18000c2fa  mov     rcx, [rsp+48h]; this
0x18000c2ff  lea     r8, aAvcoreMidi2Tra_2; "avcore\\midi2\\transport\\midisrvtransp"...
0x18000c306  mov     r9d, eax; char *
0x18000c309  lea     edx, [r14+4]; void *
0x18000c30d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c312  mov     rdi, [rbx+10h]
0x18000c316  test    rdi, rdi
0x18000c319  jz      short loc_18000C32F
0x18000c31b  mov     rcx, rdi; this
0x18000c31e  call    ??1CMidiXProc@@QEAA@XZ; CMidiXProc::~CMidiXProc(void)
0x18000c323  lea     edx, [r14+70h]
0x18000c327  mov     rcx, rdi; Block
0x18000c32a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c32f  mov     rdx, r14
0x18000c332  mov     rcx, rbx; Block
0x18000c335  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c33a  mov     eax, esi
0x18000c33c  jmp     short loc_18000C39C
0x18000c33e  mov     rsi, [rdi+18h]
0x18000c342  mov     [rdi+18h], rbx
0x18000c346  test    rsi, rsi
0x18000c349  jz      short loc_18000C374
0x18000c34b  mov     rbx, [rsi+10h]
0x18000c34f  test    rbx, rbx
0x18000c352  jz      short loc_18000C369
0x18000c354  mov     rcx, rbx; this
0x18000c357  call    ??1CMidiXProc@@QEAA@XZ; CMidiXProc::~CMidiXProc(void)
0x18000c35c  mov     edx, 90h
0x18000c361  mov     rcx, rbx; Block
0x18000c364  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c369  mov     rdx, r14
0x18000c36c  mov     rcx, rsi; Block
0x18000c36f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c374  mov     byte ptr [rdi+30h], 1
0x18000c378  xor     eax, eax
0x18000c37a  jmp     short loc_18000C39C
0x18000c37c  mov     rcx, [rsp+48h]; this
0x18000c381  lea     r8, aAvcoreMidi2Tra_2; "avcore\\midi2\\transport\\midisrvtransp"...
0x18000c388  mov     ebx, 8007000Eh
0x18000c38d  mov     edx, 22h ; '"'; void *
0x18000c392  mov     r9d, ebx; char *
0x18000c395  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c39a  mov     eax, ebx
0x18000c39c  mov     rbx, [rsp+48h+arg_10]
0x18000c3a1  add     rsp, 30h
0x18000c3a5  pop     r14
0x18000c3a7  pop     rdi
0x18000c3a8  pop     rsi
0x18000c3a9  retn
```
