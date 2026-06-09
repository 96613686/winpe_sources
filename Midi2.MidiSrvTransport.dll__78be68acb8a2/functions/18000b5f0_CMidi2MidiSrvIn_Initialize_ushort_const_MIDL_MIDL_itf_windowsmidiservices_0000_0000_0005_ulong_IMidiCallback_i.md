# CMidi2MidiSrvIn::Initialize(ushort const *,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005 *,ulong *,IMidiCallback *,__int64,_GUID)

- ea: `0x18000b5f0`
- end: `0x18000b7e0`
- name: `?Initialize@CMidi2MidiSrvIn@@UEAAJPEBGPEAU__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005@@PEAKPEAUIMidiCallback@@_JU_GUID@@@Z`
- size: `496`
- prototype: `int(CMidi2MidiSrvIn *__hidden this, const unsigned __int16 *, struct __MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005 *, unsigned int *, struct IMidiCallback *, __int64, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task`

## callees

- `0x1800017d0`
- `0x180002494`
- `0x1800028ec`
- `0x180007e24`
- `0x180009bf8`
- `0x18000b5f0`
- `0x18000d190`
- `0x180012b04`

## pseudocode

```c
__int64 __fastcall CMidi2MidiSrvIn::Initialize(
        CMidi2MidiSrvIn *this,
        unsigned __int16 *a2,
        struct __MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005 *a3,
        unsigned int *a4,
        struct IMidiCallback *a5,
        __int64 a6,
        struct _GUID *a7)
{
  struct IMidiCallback *v7; // r15
  unsigned int v12; // ebx
  __int64 v13; // rdx
  _DWORD *v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  CMidiXProc **v17; // rax
  CMidiXProc **v18; // rbx
  struct _GUID *v19; // rcx
  struct _GUID v20; // xmm0
  __int64 v21; // rcx
  int v22; // eax
  unsigned int v23; // ebp
  CMidiXProc *v24; // rdi
  CMidiXProc **v26; // rdi
  CMidiXProc *v27; // rbx
  int v28; // [rsp+20h] [rbp-68h]
  int v29; // [rsp+20h] [rbp-68h]
  int v30[4]; // [rsp+40h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v7 = a5;
  if ( !a5 )
  {
    v12 = -2147024809;
    v13 = 23;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"avcore\\midi2\\transport\\midisrvtransport\\midi2.midisrvin.cpp",
      (const char *)v12,
      v28);
    return v12;
  }
  if ( !a2 )
  {
    v12 = -2147024809;
    v13 = 24;
    goto LABEL_22;
  }
  if ( !a4 )
  {
    v12 = -2147024809;
    v13 = 25;
    goto LABEL_22;
  }
  if ( !a3 )
  {
    v12 = -2147024809;
    v13 = 26;
    goto LABEL_22;
  }
  v14 = (_DWORD *)*((_QWORD *)MidiSrvTransportTelemetryProvider::Instance() + 1);
  if ( *v14 > 4u )
  {
    a5 = this;
    *(_QWORD *)v30 = "CMidi2MidiSrvIn::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (__int64)v14,
      (unsigned __int8 *)&word_180019E96,
      v15,
      v16,
      (const unsigned __int16 **)v30,
      (__int64)&a5);
  }
  v17 = (CMidiXProc **)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v18 = v17;
  if ( !v17 )
  {
    v12 = -2147024882;
    v13 = 37;
    goto LABEL_22;
  }
  v19 = a7;
  v17[3] = 0;
  *v17 = 0;
  v17[1] = 0;
  v20 = *v19;
  v21 = a6;
  v17[2] = 0;
  *(struct _GUID *)v30 = v20;
  v22 = CMidi2MidiSrv::Initialize(v17, (__int64 *)a2, 0, (__int64)a3, a4, (__int64)v7, v21, (__int64)v30);
  v23 = v22;
  if ( v22 >= 0 )
  {
    v26 = (CMidiXProc **)*((_QWORD *)this + 2);
    *((_QWORD *)this + 2) = v18;
    if ( v26 )
    {
      v27 = v26[2];
      if ( v27 )
      {
        CMidiXProc::~CMidiXProc(v26[2]);
        operator delete(v27);
      }
      operator delete(v26);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"avcore\\midi2\\transport\\midisrvtransport\\midi2.midisrvin.cpp",
      (const char *)(unsigned int)v22,
      v29);
    v24 = v18[2];
    if ( v24 )
    {
      CMidiXProc::~CMidiXProc(v18[2]);
      operator delete(v24);
    }
    operator delete(v18);
    return v23;
  }
}

```

## disassembly

```asm
0x18000b5f0  push    rbx
0x18000b5f2  push    rbp
0x18000b5f3  push    rsi
0x18000b5f4  push    rdi
0x18000b5f5  push    r13
0x18000b5f7  push    r14
0x18000b5f9  push    r15
0x18000b5fb  sub     rsp, 50h
0x18000b5ff  mov     r15, [rsp+88h+arg_20]
0x18000b607  mov     rdi, r9
0x18000b60a  mov     rbp, r8
0x18000b60d  mov     r14, rdx
0x18000b610  mov     rsi, rcx
0x18000b613  test    r15, r15
0x18000b616  jnz     short loc_18000B626
0x18000b618  mov     ebx, 80070057h
0x18000b61d  lea     edx, [r15+17h]
0x18000b621  jmp     loc_18000B7B8
0x18000b626  test    r14, r14
0x18000b629  jnz     short loc_18000B639
0x18000b62b  mov     ebx, 80070057h
0x18000b630  lea     edx, [r14+18h]
0x18000b634  jmp     loc_18000B7B8
0x18000b639  test    rdi, rdi
0x18000b63c  jnz     short loc_18000B64B
0x18000b63e  mov     ebx, 80070057h
0x18000b643  lea     edx, [rdi+19h]
0x18000b646  jmp     loc_18000B7B8
0x18000b64b  test    rbp, rbp
0x18000b64e  jnz     short loc_18000B65D
0x18000b650  mov     ebx, 80070057h
0x18000b655  lea     edx, [rbp+1Ah]
0x18000b658  jmp     loc_18000B7B8
0x18000b65d  call    ?Instance@MidiSrvTransportTelemetryProvider@@KAPEAV1@XZ; MidiSrvTransportTelemetryProvider::Instance(void)
0x18000b662  mov     rcx, [rax+8]
0x18000b666  mov     eax, [rcx]
0x18000b668  cmp     eax, 4
0x18000b66b  jbe     short loc_18000B6A4
0x18000b66d  lea     rax, aCmidi2midisrvi; "CMidi2MidiSrvIn::Initialize"
0x18000b674  mov     [rsp+88h+arg_20], rsi
0x18000b67c  mov     qword ptr [rsp+88h+var_48], rax
0x18000b681  lea     rdx, word_180019E96
0x18000b688  lea     rax, [rsp+88h+arg_20]
0x18000b690  mov     [rsp+88h+var_60], rax
0x18000b695  lea     rax, [rsp+88h+var_48]
0x18000b69a  mov     qword ptr [rsp+88h+var_68], rax; int
0x18000b69f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000b6a4  mov     r13d, 20h ; ' '
0x18000b6aa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b6b1  mov     ecx, r13d; unsigned __int64
0x18000b6b4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b6b9  mov     rbx, rax
0x18000b6bc  test    rax, rax
0x18000b6bf  jz      loc_18000B7AE
0x18000b6c5  mov     rcx, [rsp+88h+arg_30]
0x18000b6cd  mov     r9, rbp
0x18000b6d0  mov     qword ptr [rax+18h], 0
0x18000b6d8  xor     r8d, r8d
0x18000b6db  mov     qword ptr [rax], 0
0x18000b6e2  mov     rdx, r14
0x18000b6e5  mov     qword ptr [rax+8], 0
0x18000b6ed  movups  xmm0, xmmword ptr [rcx]
0x18000b6f0  mov     rcx, [rsp+88h+arg_28]
0x18000b6f8  mov     qword ptr [rax+10h], 0
0x18000b700  lea     rax, [rsp+88h+var_48]
0x18000b705  mov     [rsp+88h+var_50], rax
0x18000b70a  mov     [rsp+88h+var_58], rcx
0x18000b70f  mov     rcx, rbx
0x18000b712  mov     [rsp+88h+var_60], r15
0x18000b717  mov     qword ptr [rsp+88h+var_68], rdi; int
0x18000b71c  movdqu  xmmword ptr [rsp+88h+var_48], xmm0
0x18000b722  call    ?Initialize@CMidi2MidiSrv@@QEAAJPEBGW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@PEAU__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005@@PEAKPEAUIMidiCallback@@_JU_GUID@@@Z; CMidi2MidiSrv::Initialize(ushort const *,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005 *,ulong *,IMidiCallback *,__int64,_GUID)
0x18000b727  mov     ebp, eax
0x18000b729  test    eax, eax
0x18000b72b  jns     short loc_18000B774
0x18000b72d  mov     rcx, [rsp+88h]; this
0x18000b735  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\midisrvtransp"...
0x18000b73c  mov     r9d, eax; char *
0x18000b73f  lea     edx, [r13+7]; void *
0x18000b743  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b748  mov     rdi, [rbx+10h]
0x18000b74c  test    rdi, rdi
0x18000b74f  jz      short loc_18000B765
0x18000b751  mov     rcx, rdi; this
0x18000b754  call    ??1CMidiXProc@@QEAA@XZ; CMidiXProc::~CMidiXProc(void)
0x18000b759  lea     edx, [r13+70h]
0x18000b75d  mov     rcx, rdi; Block
0x18000b760  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b765  mov     rdx, r13
0x18000b768  mov     rcx, rbx; Block
0x18000b76b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b770  mov     eax, ebp
0x18000b772  jmp     short loc_18000B7D1
0x18000b774  mov     rdi, [rsi+10h]
0x18000b778  mov     [rsi+10h], rbx
0x18000b77c  test    rdi, rdi
0x18000b77f  jz      short loc_18000B7AA
0x18000b781  mov     rbx, [rdi+10h]
0x18000b785  test    rbx, rbx
0x18000b788  jz      short loc_18000B79F
0x18000b78a  mov     rcx, rbx; this
0x18000b78d  call    ??1CMidiXProc@@QEAA@XZ; CMidiXProc::~CMidiXProc(void)
0x18000b792  mov     edx, 90h
0x18000b797  mov     rcx, rbx; Block
0x18000b79a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b79f  mov     rdx, r13
0x18000b7a2  mov     rcx, rdi; Block
0x18000b7a5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b7aa  xor     eax, eax
0x18000b7ac  jmp     short loc_18000B7D1
0x18000b7ae  mov     ebx, 8007000Eh
0x18000b7b3  mov     edx, 25h ; '%'; void *
0x18000b7b8  mov     rcx, [rsp+88h]; this
0x18000b7c0  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\midisrvtransp"...
0x18000b7c7  mov     r9d, ebx; char *
0x18000b7ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b7cf  mov     eax, ebx
0x18000b7d1  add     rsp, 50h
0x18000b7d5  pop     r15
0x18000b7d7  pop     r14
0x18000b7d9  pop     r13
0x18000b7db  pop     rdi
0x18000b7dc  pop     rsi
0x18000b7dd  pop     rbp
0x18000b7de  pop     rbx
0x18000b7df  retn
```
