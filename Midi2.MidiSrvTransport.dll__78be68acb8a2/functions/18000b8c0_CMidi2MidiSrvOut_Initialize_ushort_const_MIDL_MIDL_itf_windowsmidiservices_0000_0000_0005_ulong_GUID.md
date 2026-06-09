# CMidi2MidiSrvOut::Initialize(ushort const *,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005 *,ulong *,_GUID)

- ea: `0x18000b8c0`
- end: `0x18000ba95`
- name: `?Initialize@CMidi2MidiSrvOut@@UEAAJPEBGPEAU__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005@@PEAKU_GUID@@@Z`
- size: `469`
- prototype: `int(CMidi2MidiSrvOut *__hidden this, const unsigned __int16 *, struct __MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005 *, unsigned int *, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task`

## callees

- `0x1800017d0`
- `0x180002494`
- `0x1800028ec`
- `0x180007e24`
- `0x180009bf8`
- `0x18000b8c0`
- `0x18000d190`
- `0x180012b04`

## pseudocode

```c
__int64 __fastcall CMidi2MidiSrvOut::Initialize(
        CMidiXProc ***this,
        unsigned __int16 *a2,
        struct __MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005 *a3,
        unsigned int *a4,
        struct _GUID *a5)
{
  unsigned int v9; // ebx
  __int64 v10; // rdx
  _DWORD *v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  CMidiXProc **v14; // rax
  CMidiXProc **v15; // rbx
  struct _GUID *v16; // rcx
  struct _GUID v17; // xmm0
  int v18; // eax
  unsigned int v19; // ebp
  CMidiXProc *v20; // rdi
  CMidiXProc **v22; // rdi
  CMidiXProc *v23; // rbx
  int v24; // [rsp+20h] [rbp-68h]
  int v25; // [rsp+20h] [rbp-68h]
  int v26[4]; // [rsp+40h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  CMidi2MidiSrvOut *v28; // [rsp+98h] [rbp+10h] BYREF

  if ( !a2 )
  {
    v9 = -2147024809;
    v10 = 21;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"avcore\\midi2\\transport\\midisrvtransport\\midi2.midisrvout.cpp",
      (const char *)v9,
      v24);
    return v9;
  }
  if ( !a4 )
  {
    v9 = -2147024809;
    v10 = 22;
    goto LABEL_20;
  }
  if ( !a3 )
  {
    v9 = -2147024809;
    v10 = 23;
    goto LABEL_20;
  }
  v11 = (_DWORD *)*((_QWORD *)MidiSrvTransportTelemetryProvider::Instance() + 1);
  if ( *v11 > 4u )
  {
    v28 = (CMidi2MidiSrvOut *)this;
    *(_QWORD *)v26 = "CMidi2MidiSrvOut::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (__int64)v11,
      (unsigned __int8 *)&word_180019F56,
      v12,
      v13,
      (const unsigned __int16 **)v26,
      (__int64)&v28);
  }
  v14 = (CMidiXProc **)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v15 = v14;
  if ( !v14 )
  {
    v9 = -2147024882;
    v10 = 34;
    goto LABEL_20;
  }
  v16 = a5;
  v14[3] = 0;
  *v14 = 0;
  v14[1] = 0;
  v17 = *v16;
  v14[2] = 0;
  *(struct _GUID *)v26 = v17;
  v18 = CMidi2MidiSrv::Initialize(v14, (__int64 *)a2, 1, (__int64)a3, a4, 0, 0, (__int64)v26);
  v19 = v18;
  if ( v18 >= 0 )
  {
    v22 = this[2];
    this[2] = v15;
    if ( v22 )
    {
      v23 = v22[2];
      if ( v23 )
      {
        CMidiXProc::~CMidiXProc(v22[2]);
        operator delete(v23);
      }
      operator delete(v22);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"avcore\\midi2\\transport\\midisrvtransport\\midi2.midisrvout.cpp",
      (const char *)(unsigned int)v18,
      v25);
    v20 = v15[2];
    if ( v20 )
    {
      CMidiXProc::~CMidiXProc(v15[2]);
      operator delete(v20);
    }
    operator delete(v15);
    return v19;
  }
}

```

## disassembly

```asm
0x18000b8c0  push    rbx
0x18000b8c2  push    rbp
0x18000b8c3  push    rsi
0x18000b8c4  push    rdi
0x18000b8c5  push    r12
0x18000b8c7  push    r14
0x18000b8c9  sub     rsp, 58h
0x18000b8cd  mov     rdi, r9
0x18000b8d0  mov     rbp, r8
0x18000b8d3  mov     r14, rdx
0x18000b8d6  mov     rsi, rcx
0x18000b8d9  test    rdx, rdx
0x18000b8dc  jnz     short loc_18000B8EC
0x18000b8de  mov     ebx, 80070057h
0x18000b8e3  lea     edx, [r14+15h]
0x18000b8e7  jmp     loc_18000BA6F
0x18000b8ec  test    rdi, rdi
0x18000b8ef  jnz     short loc_18000B8FE
0x18000b8f1  mov     ebx, 80070057h
0x18000b8f6  lea     edx, [rdi+16h]
0x18000b8f9  jmp     loc_18000BA6F
0x18000b8fe  test    rbp, rbp
0x18000b901  jnz     short loc_18000B910
0x18000b903  mov     ebx, 80070057h
0x18000b908  lea     edx, [rbp+17h]
0x18000b90b  jmp     loc_18000BA6F
0x18000b910  call    ?Instance@MidiSrvTransportTelemetryProvider@@KAPEAV1@XZ; MidiSrvTransportTelemetryProvider::Instance(void)
0x18000b915  mov     rcx, [rax+8]
0x18000b919  mov     eax, [rcx]
0x18000b91b  cmp     eax, 4
0x18000b91e  jbe     short loc_18000B957
0x18000b920  lea     rax, aCmidi2midisrvo_0; "CMidi2MidiSrvOut::Initialize"
0x18000b927  mov     [rsp+88h+arg_8], rsi
0x18000b92f  mov     qword ptr [rsp+88h+var_48], rax
0x18000b934  lea     rdx, word_180019F56
0x18000b93b  lea     rax, [rsp+88h+arg_8]
0x18000b943  mov     [rsp+88h+var_60], rax
0x18000b948  lea     rax, [rsp+88h+var_48]
0x18000b94d  mov     qword ptr [rsp+88h+var_68], rax; int
0x18000b952  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000b957  mov     r12d, 20h ; ' '
0x18000b95d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b964  mov     ecx, r12d; unsigned __int64
0x18000b967  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b96c  mov     rbx, rax
0x18000b96f  test    rax, rax
0x18000b972  jz      loc_18000BA65
0x18000b978  mov     rcx, [rsp+88h+arg_20]
0x18000b980  lea     r8d, [r12-1Fh]
0x18000b985  mov     qword ptr [rax+18h], 0
0x18000b98d  mov     r9, rbp
0x18000b990  mov     qword ptr [rax], 0
0x18000b997  mov     rdx, r14
0x18000b99a  mov     qword ptr [rax+8], 0
0x18000b9a2  movups  xmm0, xmmword ptr [rcx]
0x18000b9a5  mov     qword ptr [rax+10h], 0
0x18000b9ad  mov     rcx, rbx
0x18000b9b0  lea     rax, [rsp+88h+var_48]
0x18000b9b5  mov     [rsp+88h+var_50], rax
0x18000b9ba  mov     [rsp+88h+var_58], 0
0x18000b9c3  mov     [rsp+88h+var_60], 0
0x18000b9cc  movdqu  xmmword ptr [rsp+88h+var_48], xmm0
0x18000b9d2  mov     qword ptr [rsp+88h+var_68], rdi; int
0x18000b9d7  call    ?Initialize@CMidi2MidiSrv@@QEAAJPEBGW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@PEAU__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005@@PEAKPEAUIMidiCallback@@_JU_GUID@@@Z; CMidi2MidiSrv::Initialize(ushort const *,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005 *,ulong *,IMidiCallback *,__int64,_GUID)
0x18000b9dc  mov     ebp, eax
0x18000b9de  test    eax, eax
0x18000b9e0  jns     short loc_18000BA2B
0x18000b9e2  mov     rcx, [rsp+88h]; this
0x18000b9ea  lea     r8, aAvcoreMidi2Tra_0; "avcore\\midi2\\transport\\midisrvtransp"...
0x18000b9f1  mov     r9d, eax; char *
0x18000b9f4  lea     edx, [r12+4]; void *
0x18000b9f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b9fe  mov     rdi, [rbx+10h]
0x18000ba02  test    rdi, rdi
0x18000ba05  jz      short loc_18000BA1C
0x18000ba07  mov     rcx, rdi; this
0x18000ba0a  call    ??1CMidiXProc@@QEAA@XZ; CMidiXProc::~CMidiXProc(void)
0x18000ba0f  lea     edx, [r12+70h]
0x18000ba14  mov     rcx, rdi; Block
0x18000ba17  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ba1c  mov     rdx, r12
0x18000ba1f  mov     rcx, rbx; Block
0x18000ba22  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ba27  mov     eax, ebp
0x18000ba29  jmp     short loc_18000BA88
0x18000ba2b  mov     rdi, [rsi+10h]
0x18000ba2f  mov     [rsi+10h], rbx
0x18000ba33  test    rdi, rdi
0x18000ba36  jz      short loc_18000BA61
0x18000ba38  mov     rbx, [rdi+10h]
0x18000ba3c  test    rbx, rbx
0x18000ba3f  jz      short loc_18000BA56
0x18000ba41  mov     rcx, rbx; this
0x18000ba44  call    ??1CMidiXProc@@QEAA@XZ; CMidiXProc::~CMidiXProc(void)
0x18000ba49  mov     edx, 90h
0x18000ba4e  mov     rcx, rbx; Block
0x18000ba51  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ba56  mov     rdx, r12
0x18000ba59  mov     rcx, rdi; Block
0x18000ba5c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ba61  xor     eax, eax
0x18000ba63  jmp     short loc_18000BA88
0x18000ba65  mov     ebx, 8007000Eh
0x18000ba6a  mov     edx, 22h ; '"'; void *
0x18000ba6f  mov     rcx, [rsp+88h]; this
0x18000ba77  lea     r8, aAvcoreMidi2Tra_0; "avcore\\midi2\\transport\\midisrvtransp"...
0x18000ba7e  mov     r9d, ebx; char *
0x18000ba81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ba86  mov     eax, ebx
0x18000ba88  add     rsp, 58h
0x18000ba8c  pop     r14
0x18000ba8e  pop     r12
0x18000ba90  pop     rdi
0x18000ba91  pop     rsi
0x18000ba92  pop     rbp
0x18000ba93  pop     rbx
0x18000ba94  retn
```
