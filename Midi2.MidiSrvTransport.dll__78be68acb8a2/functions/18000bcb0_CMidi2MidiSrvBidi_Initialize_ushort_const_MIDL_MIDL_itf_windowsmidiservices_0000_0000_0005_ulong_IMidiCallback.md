# CMidi2MidiSrvBidi::Initialize(ushort const *,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005 *,ulong *,IMidiCallback *,__int64,_GUID)

- ea: `0x18000bcb0`
- end: `0x18000bea1`
- name: `?Initialize@CMidi2MidiSrvBidi@@UEAAJPEBGPEAU__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005@@PEAKPEAUIMidiCallback@@_JU_GUID@@@Z`
- size: `497`
- prototype: `int(CMidi2MidiSrvBidi *__hidden this, const unsigned __int16 *, struct __MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005 *, unsigned int *, struct IMidiCallback *, __int64, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task`

## callees

- `0x1800017d0`
- `0x180002494`
- `0x1800028ec`
- `0x180007e24`
- `0x180009bf8`
- `0x18000bcb0`
- `0x18000d190`
- `0x180012b04`

## pseudocode

```c
__int64 __fastcall CMidi2MidiSrvBidi::Initialize(
        CMidi2MidiSrvBidi *this,
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
      (unsigned int)"avcore\\midi2\\transport\\midisrvtransport\\midi2.midisrvbidi.cpp",
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
    *(_QWORD *)v30 = "CMidi2MidiSrvBidi::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (__int64)v14,
      (unsigned __int8 *)&word_18001A016,
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
    v13 = 38;
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
  v22 = CMidi2MidiSrv::Initialize(v17, (__int64 *)a2, 2, (__int64)a3, a4, (__int64)v7, v21, (__int64)v30);
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
      (void *)0x28,
      (unsigned int)"avcore\\midi2\\transport\\midisrvtransport\\midi2.midisrvbidi.cpp",
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
0x18000bcb0  push    rbx
0x18000bcb2  push    rbp
0x18000bcb3  push    rsi
0x18000bcb4  push    rdi
0x18000bcb5  push    r13
0x18000bcb7  push    r14
0x18000bcb9  push    r15
0x18000bcbb  sub     rsp, 50h
0x18000bcbf  mov     r15, [rsp+88h+arg_20]
0x18000bcc7  mov     rdi, r9
0x18000bcca  mov     rbp, r8
0x18000bccd  mov     r14, rdx
0x18000bcd0  mov     rsi, rcx
0x18000bcd3  test    r15, r15
0x18000bcd6  jnz     short loc_18000BCE6
0x18000bcd8  mov     ebx, 80070057h
0x18000bcdd  lea     edx, [r15+17h]
0x18000bce1  jmp     loc_18000BE79
0x18000bce6  test    r14, r14
0x18000bce9  jnz     short loc_18000BCF9
0x18000bceb  mov     ebx, 80070057h
0x18000bcf0  lea     edx, [r14+18h]
0x18000bcf4  jmp     loc_18000BE79
0x18000bcf9  test    rdi, rdi
0x18000bcfc  jnz     short loc_18000BD0B
0x18000bcfe  mov     ebx, 80070057h
0x18000bd03  lea     edx, [rdi+19h]
0x18000bd06  jmp     loc_18000BE79
0x18000bd0b  test    rbp, rbp
0x18000bd0e  jnz     short loc_18000BD1D
0x18000bd10  mov     ebx, 80070057h
0x18000bd15  lea     edx, [rbp+1Ah]
0x18000bd18  jmp     loc_18000BE79
0x18000bd1d  call    ?Instance@MidiSrvTransportTelemetryProvider@@KAPEAV1@XZ; MidiSrvTransportTelemetryProvider::Instance(void)
0x18000bd22  mov     rcx, [rax+8]
0x18000bd26  mov     eax, [rcx]
0x18000bd28  cmp     eax, 4
0x18000bd2b  jbe     short loc_18000BD64
0x18000bd2d  lea     rax, aCmidi2midisrvb; "CMidi2MidiSrvBidi::Initialize"
0x18000bd34  mov     [rsp+88h+arg_20], rsi
0x18000bd3c  mov     qword ptr [rsp+88h+var_48], rax
0x18000bd41  lea     rdx, word_18001A016
0x18000bd48  lea     rax, [rsp+88h+arg_20]
0x18000bd50  mov     [rsp+88h+var_60], rax
0x18000bd55  lea     rax, [rsp+88h+var_48]
0x18000bd5a  mov     qword ptr [rsp+88h+var_68], rax; int
0x18000bd5f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000bd64  mov     r13d, 20h ; ' '
0x18000bd6a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000bd71  mov     ecx, r13d; unsigned __int64
0x18000bd74  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000bd79  mov     rbx, rax
0x18000bd7c  test    rax, rax
0x18000bd7f  jz      loc_18000BE6F
0x18000bd85  mov     rcx, [rsp+88h+arg_30]
0x18000bd8d  lea     r8d, [r13-1Eh]
0x18000bd91  mov     qword ptr [rax+18h], 0
0x18000bd99  mov     r9, rbp
0x18000bd9c  mov     qword ptr [rax], 0
0x18000bda3  mov     rdx, r14
0x18000bda6  mov     qword ptr [rax+8], 0
0x18000bdae  movups  xmm0, xmmword ptr [rcx]
0x18000bdb1  mov     rcx, [rsp+88h+arg_28]
0x18000bdb9  mov     qword ptr [rax+10h], 0
0x18000bdc1  lea     rax, [rsp+88h+var_48]
0x18000bdc6  mov     [rsp+88h+var_50], rax
0x18000bdcb  mov     [rsp+88h+var_58], rcx
0x18000bdd0  mov     rcx, rbx
0x18000bdd3  mov     [rsp+88h+var_60], r15
0x18000bdd8  mov     qword ptr [rsp+88h+var_68], rdi; int
0x18000bddd  movdqu  xmmword ptr [rsp+88h+var_48], xmm0
0x18000bde3  call    ?Initialize@CMidi2MidiSrv@@QEAAJPEBGW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@PEAU__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005@@PEAKPEAUIMidiCallback@@_JU_GUID@@@Z; CMidi2MidiSrv::Initialize(ushort const *,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005 *,ulong *,IMidiCallback *,__int64,_GUID)
0x18000bde8  mov     ebp, eax
0x18000bdea  test    eax, eax
0x18000bdec  jns     short loc_18000BE35
0x18000bdee  mov     rcx, [rsp+88h]; this
0x18000bdf6  lea     r8, aAvcoreMidi2Tra_1; "avcore\\midi2\\transport\\midisrvtransp"...
0x18000bdfd  mov     r9d, eax; char *
0x18000be00  lea     edx, [r13+8]; void *
0x18000be04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000be09  mov     rdi, [rbx+10h]
0x18000be0d  test    rdi, rdi
0x18000be10  jz      short loc_18000BE26
0x18000be12  mov     rcx, rdi; this
0x18000be15  call    ??1CMidiXProc@@QEAA@XZ; CMidiXProc::~CMidiXProc(void)
0x18000be1a  lea     edx, [r13+70h]
0x18000be1e  mov     rcx, rdi; Block
0x18000be21  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000be26  mov     rdx, r13
0x18000be29  mov     rcx, rbx; Block
0x18000be2c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000be31  mov     eax, ebp
0x18000be33  jmp     short loc_18000BE92
0x18000be35  mov     rdi, [rsi+10h]
0x18000be39  mov     [rsi+10h], rbx
0x18000be3d  test    rdi, rdi
0x18000be40  jz      short loc_18000BE6B
0x18000be42  mov     rbx, [rdi+10h]
0x18000be46  test    rbx, rbx
0x18000be49  jz      short loc_18000BE60
0x18000be4b  mov     rcx, rbx; this
0x18000be4e  call    ??1CMidiXProc@@QEAA@XZ; CMidiXProc::~CMidiXProc(void)
0x18000be53  mov     edx, 90h
0x18000be58  mov     rcx, rbx; Block
0x18000be5b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000be60  mov     rdx, r13
0x18000be63  mov     rcx, rdi; Block
0x18000be66  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000be6b  xor     eax, eax
0x18000be6d  jmp     short loc_18000BE92
0x18000be6f  mov     ebx, 8007000Eh
0x18000be74  mov     edx, 26h ; '&'; void *
0x18000be79  mov     rcx, [rsp+88h]; this
0x18000be81  lea     r8, aAvcoreMidi2Tra_1; "avcore\\midi2\\transport\\midisrvtransp"...
0x18000be88  mov     r9d, ebx; char *
0x18000be8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000be90  mov     eax, ebx
0x18000be92  add     rsp, 50h
0x18000be96  pop     r15
0x18000be98  pop     r14
0x18000be9a  pop     r13
0x18000be9c  pop     rdi
0x18000be9d  pop     rsi
0x18000be9e  pop     rbp
0x18000be9f  pop     rbx
0x18000bea0  retn
```
