# ipx::mtf::CMtfSuggestionClient::RequestSuggestion(int,uchar *,ulong,_MTF_QUERY_PROP *,ushort *)

- ea: `0x18001a450`
- end: `0x18001a7f4`
- name: `?RequestSuggestion@CMtfSuggestionClient@mtf@ipx@@UEAAJHPEAEKPEAU_MTF_QUERY_PROP@@PEAG@Z`
- size: `932`
- prototype: `__int64 __usercall@<rax>(ipx::mtf::CMtfSuggestionClient *__hidden this@<rcx>, int@<edx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, struct _MTF_QUERY_PROP *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update`

## callees

- `0x180006074`
- `0x180014014`
- `0x180014258`
- `0x180016a08`
- `0x180019a28`
- `0x18001a450`
- `0x18001b314`
- `0x18001b8f4`
- `0x18001d1f4`
- `0x18001dbb4`
- `0x18002bca0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a5c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a697`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a747`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a7c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a5c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a697`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a747`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a7c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a4d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a4d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a49c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a49c`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall ipx::mtf::CMtfSuggestionClient::RequestSuggestion(
        ipx::mtf::CMtfSuggestionClient *this,
        int a2,
        unsigned __int8 *a3,
        unsigned int a4,
        struct _MTF_QUERY_PROP *a5,
        unsigned __int16 *a6)
{
  int v10; // ebx
  struct _RTL_CRITICAL_SECTION *v12; // rdi
  int v13; // eax
  unsigned int v14; // ebx
  struct IMtfSuggestionInputQuery *v15; // rbx
  int v16; // eax
  unsigned int v17; // r14d
  struct IMtfPropertyBag *v18; // rcx
  unsigned __int16 v19; // dx
  int v20; // eax
  unsigned int v21; // esi
  struct IMtfPropertyBag *v22; // rcx
  struct IMtfPropertyBag *v23; // rcx
  unsigned int v24; // [rsp+20h] [rbp-1F8h]
  unsigned int v25; // [rsp+20h] [rbp-1F8h]
  unsigned int v26; // [rsp+20h] [rbp-1F8h]
  unsigned int v27; // [rsp+50h] [rbp-1C8h] BYREF
  struct IMtfPropertyBag *v28; // [rsp+58h] [rbp-1C0h] BYREF
  struct IMtfSuggestionInputQuery *v29; // [rsp+60h] [rbp-1B8h] BYREF
  struct _MTF_QUERY_PROP *v30; // [rsp+68h] [rbp-1B0h]
  char *v31; // [rsp+70h] [rbp-1A8h]
  _QWORD v32[42]; // [rsp+80h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+0h]

  v30 = a5;
  v10 = *((_DWORD *)this + 50);
  if ( v10 == GetCurrentThreadId() )
  {
    v12 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
    v31 = (char *)this + 64;
    wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
      v32,
      "RequestSuggestion");
    v32[0] = &MtfPlatformTelemetry::RequestSuggestion::`vftable';
    MtfPlatformTelemetry::RequestSuggestion::StartActivity((MtfPlatformTelemetry::RequestSuggestion *)v32);
    v27 = 4;
    v29 = 0;
    v13 = ipx::mtf::CMtfSuggestionClient::_CreateSuggestionInputQuery(0, a2 != 0, v30, a3, a4, 0, 0, &v29, &v27);
    v14 = v13;
    if ( v13 >= 0 )
    {
      v28 = 0;
      v15 = v29;
      v16 = ipx::mtf::CMtfSuggestionClient::_CreateRequestBag(this, v27, 0, 0, 0, 0, 0, v29, &v28);
      v17 = v16;
      if ( v16 >= 0 )
      {
        v19 = *((_WORD *)this + 102);
        *a6 = v19;
        v20 = ipx::mtf::CMtfSuggestionClient::RepairAndRequest(this, v19, v28);
        v21 = v20;
        if ( v20 >= 0 )
        {
          wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v32);
          v23 = v28;
          if ( v28 )
          {
            v28 = 0;
            (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v23 + 16LL))(v23);
          }
          if ( v15 )
            (*(void (__fastcall **)(struct IMtfSuggestionInputQuery *))(*(_QWORD *)v15 + 16LL))(v15);
          v32[0] = &MtfPlatformTelemetry::RequestSuggestion::`vftable';
          wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v32);
          wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v32);
          if ( v12 )
            LeaveCriticalSection(v12);
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x249,
            (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
            (const char *)(unsigned int)v20,
            v26);
          v22 = v28;
          if ( v28 )
          {
            v28 = 0;
            (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v22 + 16LL))(v22);
          }
          if ( v15 )
            (*(void (__fastcall **)(struct IMtfSuggestionInputQuery *))(*(_QWORD *)v15 + 16LL))(v15);
          v32[0] = &MtfPlatformTelemetry::RequestSuggestion::`vftable';
          wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v32);
          wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v32);
          if ( v12 )
            LeaveCriticalSection(v12);
          return v21;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x246,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
          (const char *)(unsigned int)v16,
          v26);
        v18 = v28;
        if ( v28 )
        {
          v28 = 0;
          (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v18 + 16LL))(v18);
        }
        if ( v15 )
          (*(void (__fastcall **)(struct IMtfSuggestionInputQuery *))(*(_QWORD *)v15 + 16LL))(v15);
        v32[0] = &MtfPlatformTelemetry::RequestSuggestion::`vftable';
        wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v32);
        wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v32);
        if ( this != (ipx::mtf::CMtfSuggestionClient *)-64LL )
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
        return v17;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x23D,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
        (const char *)(unsigned int)v13,
        v25);
      if ( v29 )
        (*(void (__fastcall **)(struct IMtfSuggestionInputQuery *))(*(_QWORD *)v29 + 16LL))(v29);
      v32[0] = &MtfPlatformTelemetry::RequestSuggestion::`vftable';
      wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v32);
      wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v32);
      if ( this != (ipx::mtf::CMtfSuggestionClient *)-64LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
      return v14;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22E,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)0x8001010ELL,
      v24);
    return 2147549454LL;
  }
}

```

## disassembly

```asm
0x18001a450  push    rbx
0x18001a452  push    rsi
0x18001a453  push    rdi
0x18001a454  push    r12
0x18001a456  push    r13
0x18001a458  push    r14
0x18001a45a  push    r15
0x18001a45c  sub     rsp, 1E0h
0x18001a463  mov     rax, cs:__security_cookie
0x18001a46a  xor     rax, rsp
0x18001a46d  mov     [rsp+218h+var_48], rax
0x18001a475  mov     r13d, r9d
0x18001a478  mov     r12, r8
0x18001a47b  mov     r14d, edx
0x18001a47e  mov     rsi, rcx
0x18001a481  mov     rax, [rsp+218h+arg_20]
0x18001a489  mov     [rsp+218h+var_1B0], rax
0x18001a48e  mov     r15, [rsp+218h+arg_28]
0x18001a496  mov     ebx, [rcx+0C8h]
0x18001a49c  call    cs:__imp_GetCurrentThreadId
0x18001a4a2  cmp     ebx, eax
0x18001a4a4  jz      short loc_18001A4CE
0x18001a4a6  mov     rcx, [rsp+218h]; this
0x18001a4ae  mov     ebx, 8001010Eh
0x18001a4b3  mov     r9d, ebx; char *
0x18001a4b6  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001a4bd  mov     edx, 22Eh; void *
0x18001a4c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a4c7  mov     eax, ebx
0x18001a4c9  jmp     loc_18001A7D0
0x18001a4ce  lea     rdi, [rsi+40h]
0x18001a4d2  mov     rcx, rdi; lpCriticalSection
0x18001a4d5  call    cs:__imp_EnterCriticalSection
0x18001a4db  mov     [rsp+218h+var_1A8], rdi
0x18001a4e0  lea     rdx, aRequestsuggest; "RequestSuggestion"
0x18001a4e7  lea     rcx, [rsp+218h+var_198]
0x18001a4ef  call    ??0?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001a4f4  lea     rax, ??_7RequestSuggestion@MtfPlatformTelemetry@@6B@; const MtfPlatformTelemetry::RequestSuggestion::`vftable'
0x18001a4fb  mov     [rsp+218h+var_198], rax
0x18001a503  lea     rcx, [rsp+218h+var_198]; this
0x18001a50b  call    ?StartActivity@RequestSuggestion@MtfPlatformTelemetry@@QEAAXXZ; MtfPlatformTelemetry::RequestSuggestion::StartActivity(void)
0x18001a510  nop
0x18001a511  mov     [rsp+218h+var_1C8], 4
0x18001a519  xor     ecx, ecx; this
0x18001a51b  mov     [rsp+218h+var_1B8], rcx
0x18001a520  test    r14d, r14d
0x18001a523  setnz   dl; bool
0x18001a526  lea     rax, [rsp+218h+var_1C8]
0x18001a52b  mov     [rsp+218h+var_1D8], rax; unsigned int *
0x18001a530  lea     rax, [rsp+218h+var_1B8]
0x18001a535  mov     [rsp+218h+var_1E0], rax; struct IMtfSuggestionInputQuery **
0x18001a53a  mov     [rsp+218h+var_1E8], rcx; struct IMtfPropertyBag *
0x18001a53f  mov     [rsp+218h+var_1F0], rcx; struct IMtfLattice *
0x18001a544  mov     [rsp+218h+var_1F8], r13d; int
0x18001a549  mov     r9, r12; unsigned __int8 *
0x18001a54c  mov     r8, [rsp+218h+var_1B0]; struct _MTF_QUERY_PROP *
0x18001a551  call    ?_CreateSuggestionInputQuery@CMtfSuggestionClient@mtf@ipx@@IEAAJ_NPEBU_MTF_QUERY_PROP@@PEAEKPEAUIMtfLattice@@PEAUIMtfPropertyBag@@PEAPEAUIMtfSuggestionInputQuery@@PEAK@Z; ipx::mtf::CMtfSuggestionClient::_CreateSuggestionInputQuery(bool,_MTF_QUERY_PROP const *,uchar *,ulong,IMtfLattice *,IMtfPropertyBag *,IMtfSuggestionInputQuery * *,ulong *)
0x18001a556  mov     ebx, eax
0x18001a558  xor     r12d, r12d
0x18001a55b  test    eax, eax
0x18001a55d  jns     short loc_18001A5D2
0x18001a55f  mov     rcx, [rsp+218h]; this
0x18001a567  mov     r9d, eax; char *
0x18001a56a  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001a571  mov     edx, 23Dh; void *
0x18001a576  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a57b  nop
0x18001a57c  mov     rcx, [rsp+218h+var_1B8]
0x18001a581  test    rcx, rcx
0x18001a584  jz      short loc_18001A593
0x18001a586  mov     rax, [rcx]
0x18001a589  mov     rax, [rax+10h]
0x18001a58d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a592  nop
0x18001a593  lea     rax, ??_7RequestSuggestion@MtfPlatformTelemetry@@6B@; const MtfPlatformTelemetry::RequestSuggestion::`vftable'
0x18001a59a  mov     [rsp+218h+var_198], rax
0x18001a5a2  lea     rcx, [rsp+218h+var_198]
0x18001a5aa  call    ?Destroy@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001a5af  lea     rcx, [rsp+218h+var_198]
0x18001a5b7  call    ??1?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001a5bc  nop
0x18001a5bd  test    rdi, rdi
0x18001a5c0  jz      short loc_18001A5CB
0x18001a5c2  mov     rcx, rdi; lpCriticalSection
0x18001a5c5  call    cs:__imp_LeaveCriticalSection
0x18001a5cb  mov     eax, ebx
0x18001a5cd  jmp     loc_18001A7D0
0x18001a5d2  mov     [rsp+218h+var_1C0], r12
0x18001a5d7  lea     rax, [rsp+218h+var_1C0]
0x18001a5dc  mov     [rsp+218h+var_1D8], rax; struct IMtfPropertyBag **
0x18001a5e1  mov     rbx, [rsp+218h+var_1B8]
0x18001a5e6  mov     [rsp+218h+var_1E0], rbx; struct IMtfSuggestionInputQuery *
0x18001a5eb  mov     [rsp+218h+var_1E8], r12; struct IMtfSuggestionContextProperty *
0x18001a5f0  mov     [rsp+218h+var_1F0], r12; struct IMtfSuggestionCandidatePrimitive *
0x18001a5f5  mov     [rsp+218h+var_1F8], r12d; int
0x18001a5fa  xor     r9d, r9d; unsigned __int8 *
0x18001a5fd  xor     r8d, r8d; struct MTFCORE_SIMPLEPARAM *
0x18001a600  mov     edx, [rsp+218h+var_1C8]; unsigned int
0x18001a604  mov     rcx, rsi; this
0x18001a607  call    ?_CreateRequestBag@CMtfSuggestionClient@mtf@ipx@@IEAAJKPEBUMTFCORE_SIMPLEPARAM@@PEBEKPEAUIMtfSuggestionCandidatePrimitive@@PEAUIMtfSuggestionContextProperty@@PEAUIMtfSuggestionInputQuery@@PEAPEAUIMtfPropertyBag@@@Z; ipx::mtf::CMtfSuggestionClient::_CreateRequestBag(ulong,MTFCORE_SIMPLEPARAM const *,uchar const *,ulong,IMtfSuggestionCandidatePrimitive *,IMtfSuggestionContextProperty *,IMtfSuggestionInputQuery *,IMtfPropertyBag * *)
0x18001a60c  mov     r14d, eax
0x18001a60f  test    eax, eax
0x18001a611  jns     loc_18001A6A5
0x18001a617  mov     rcx, [rsp+218h]; this
0x18001a61f  mov     r9d, eax; char *
0x18001a622  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001a629  mov     edx, 246h; void *
0x18001a62e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a633  nop
0x18001a634  mov     rcx, [rsp+218h+var_1C0]
0x18001a639  test    rcx, rcx
0x18001a63c  jz      short loc_18001A650
0x18001a63e  mov     [rsp+218h+var_1C0], r12
0x18001a643  mov     rax, [rcx]
0x18001a646  mov     rax, [rax+10h]
0x18001a64a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a64f  nop
0x18001a650  test    rbx, rbx
0x18001a653  jz      short loc_18001A665
0x18001a655  mov     rax, [rbx]
0x18001a658  mov     rcx, rbx
0x18001a65b  mov     rax, [rax+10h]
0x18001a65f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a664  nop
0x18001a665  lea     rax, ??_7RequestSuggestion@MtfPlatformTelemetry@@6B@; const MtfPlatformTelemetry::RequestSuggestion::`vftable'
0x18001a66c  mov     [rsp+218h+var_198], rax
0x18001a674  lea     rcx, [rsp+218h+var_198]
0x18001a67c  call    ?Destroy@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001a681  lea     rcx, [rsp+218h+var_198]
0x18001a689  call    ??1?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001a68e  nop
0x18001a68f  test    rdi, rdi
0x18001a692  jz      short loc_18001A69D
0x18001a694  mov     rcx, rdi; lpCriticalSection
0x18001a697  call    cs:__imp_LeaveCriticalSection
0x18001a69d  mov     eax, r14d
0x18001a6a0  jmp     loc_18001A7D0
0x18001a6a5  movzx   edx, word ptr [rsi+0CCh]; unsigned __int16
0x18001a6ac  mov     [r15], dx
0x18001a6b0  mov     r8, [rsp+218h+var_1C0]; struct IMtfPropertyBag *
0x18001a6b5  mov     rcx, rsi; this
0x18001a6b8  call    ?RepairAndRequest@CMtfSuggestionClient@mtf@ipx@@IEAAJGPEAUIMtfPropertyBag@@@Z; ipx::mtf::CMtfSuggestionClient::RepairAndRequest(ushort,IMtfPropertyBag *)
0x18001a6bd  mov     esi, eax
0x18001a6bf  test    eax, eax
0x18001a6c1  jns     loc_18001A751
0x18001a6c7  mov     rcx, [rsp+218h]; this
0x18001a6cf  mov     r9d, eax; char *
0x18001a6d2  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001a6d9  mov     edx, 249h; void *
0x18001a6de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a6e3  nop
0x18001a6e4  mov     rcx, [rsp+218h+var_1C0]
0x18001a6e9  test    rcx, rcx
0x18001a6ec  jz      short loc_18001A700
0x18001a6ee  mov     [rsp+218h+var_1C0], r12
0x18001a6f3  mov     rax, [rcx]
0x18001a6f6  mov     rax, [rax+10h]
0x18001a6fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6ff  nop
0x18001a700  test    rbx, rbx
0x18001a703  jz      short loc_18001A715
0x18001a705  mov     rax, [rbx]
0x18001a708  mov     rcx, rbx
0x18001a70b  mov     rax, [rax+10h]
0x18001a70f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a714  nop
0x18001a715  lea     rax, ??_7RequestSuggestion@MtfPlatformTelemetry@@6B@; const MtfPlatformTelemetry::RequestSuggestion::`vftable'
0x18001a71c  mov     [rsp+218h+var_198], rax
0x18001a724  lea     rcx, [rsp+218h+var_198]
0x18001a72c  call    ?Destroy@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001a731  lea     rcx, [rsp+218h+var_198]
0x18001a739  call    ??1?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001a73e  nop
0x18001a73f  test    rdi, rdi
0x18001a742  jz      short loc_18001A74D
0x18001a744  mov     rcx, rdi; lpCriticalSection
0x18001a747  call    cs:__imp_LeaveCriticalSection
0x18001a74d  mov     eax, esi
0x18001a74f  jmp     short loc_18001A7D0
0x18001a751  lea     rcx, [rsp+218h+var_198]
0x18001a759  call    ?Stop@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001a75e  nop
0x18001a75f  mov     rcx, [rsp+218h+var_1C0]
0x18001a764  test    rcx, rcx
0x18001a767  jz      short loc_18001A77B
0x18001a769  mov     [rsp+218h+var_1C0], r12
0x18001a76e  mov     rax, [rcx]
0x18001a771  mov     rax, [rax+10h]
0x18001a775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a77a  nop
0x18001a77b  test    rbx, rbx
0x18001a77e  jz      short loc_18001A790
0x18001a780  mov     rax, [rbx]
0x18001a783  mov     rcx, rbx
0x18001a786  mov     rax, [rax+10h]
0x18001a78a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a78f  nop
0x18001a790  lea     rax, ??_7RequestSuggestion@MtfPlatformTelemetry@@6B@; const MtfPlatformTelemetry::RequestSuggestion::`vftable'
0x18001a797  mov     [rsp+218h+var_198], rax
0x18001a79f  lea     rcx, [rsp+218h+var_198]
0x18001a7a7  call    ?Destroy@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001a7ac  lea     rcx, [rsp+218h+var_198]
0x18001a7b4  call    ??1?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001a7b9  nop
0x18001a7ba  test    rdi, rdi
0x18001a7bd  jz      short loc_18001A7C8
0x18001a7bf  mov     rcx, rdi; lpCriticalSection
0x18001a7c2  call    cs:__imp_LeaveCriticalSection
0x18001a7c8  xor     eax, eax
0x18001a7ca  jmp     short loc_18001A7D0
0x18001a7cc  mov     eax, [rsp+218h+var_1C8]
0x18001a7d0  mov     rcx, [rsp+218h+var_48]
0x18001a7d8  xor     rcx, rsp; StackCookie
0x18001a7db  call    __security_check_cookie
0x18001a7e0  add     rsp, 1E0h
0x18001a7e7  pop     r15
0x18001a7e9  pop     r14
0x18001a7eb  pop     r13
0x18001a7ed  pop     r12
0x18001a7ef  pop     rdi
0x18001a7f0  pop     rsi
0x18001a7f1  pop     rbx
0x18001a7f2  retn
```
