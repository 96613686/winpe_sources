# CAudioProcessor::AddAPOOutputConnection(unsigned __int64,IAudioProcessingObject *,unsigned __int64)

- ea: `0x14006bde0`
- end: `0x14006c1bc`
- name: `?AddAPOOutputConnection@CAudioProcessor@@UEAAJ_KPEAUIAudioProcessingObject@@0@Z`
- size: `988`
- prototype: `__int64 __fastcall(CAudioProcessor *__hidden this, unsigned __int64, struct IAudioProcessingObject *, unsigned __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000ba54`
- `0x14000bafc`
- `0x14000c33c`
- `0x140010980`
- `0x140026374`
- `0x1400263a0`
- `0x140031a68`
- `0x1400543e8`
- `0x14006bde0`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006bfa0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006bff1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006c08b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006c124`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006c157`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006bfa0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006bff1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006c08b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006c124`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006c157`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14006be97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14006c011`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14006c0ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14006c144`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14006c173`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14006be97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14006c011`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14006c0ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14006c144`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14006c173`

## pseudocode

```c
__int64 __fastcall CAudioProcessor::AddAPOOutputConnection(
        CAudioProcessor *this,
        unsigned __int64 a2,
        struct IAudioProcessingObject *a3,
        __int64 a4)
{
  unsigned int v8; // ebx
  __int64 v9; // rdx
  struct IAudioProcessingObjectVtbl *lpVtbl; // rax
  bool v11; // r8
  void *v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rcx
  unsigned int **Next; // rax
  unsigned int *v17; // rbx
  __int64 v18; // rax
  unsigned int **v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rdi
  struct IAudioProcessingObject *v23; // r8
  void *v24; // rcx
  unsigned int j; // ecx
  int v27; // eax
  unsigned int v28; // esi
  void *v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rsi
  int v32; // eax
  unsigned int v33; // edi
  void *v34; // rcx
  void *v35; // rcx
  int v36; // [rsp+20h] [rbp-50h]
  bool v37; // [rsp+30h] [rbp-40h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+40h] [rbp-30h] BYREF
  __int64 *v39; // [rsp+48h] [rbp-28h] BYREF
  __int64 i; // [rsp+50h] [rbp-20h] BYREF
  LPVOID *p_pv; // [rsp+58h] [rbp-18h] BYREF
  __int64 v42; // [rsp+60h] [rbp-10h] BYREF
  char v43; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  LPVOID pv; // [rsp+B0h] [rbp+40h] BYREF

  if ( !a3 )
  {
    v8 = -2147024809;
    v9 = 2038;
LABEL_62:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audioprocessor.cpp",
      (const char *)v8,
      v36);
    return v8;
  }
  if ( (unsigned __int64)(a4 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v9 = 2039;
    goto LABEL_61;
  }
  if ( a2 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v9 = 2040;
LABEL_61:
    v8 = -2147024890;
    goto LABEL_62;
  }
  pv = 0;
  p_pv = &pv;
  lpVtbl = a3->lpVtbl;
  v42 = 0;
  v43 = 1;
  v8 = ((__int64 (__fastcall *)(struct IAudioProcessingObject *, __int64 *))lpVtbl->GetRegistrationProperties)(a3, &v42);
  wil::details::out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( (v8 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7FB,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audioprocessor.cpp",
      (const char *)v8,
      v36);
    goto LABEL_7;
  }
  ATL::CCritSecLock::CCritSecLock((ATL::CCritSecLock *)&p_pv, (struct _RTL_CRITICAL_SECTION *)((char *)this + 104), v11);
  v13 = CAudioProcessor::ValidateTransactionState(this, a2);
  v8 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x800,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audioprocessor.cpp",
      (const char *)(unsigned int)v13,
      v36);
LABEL_11:
    ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)&p_pv);
LABEL_7:
    v12 = pv;
    pv = 0;
    if ( v12 )
      CoTaskMemFree(v12);
    return v8;
  }
  v14 = *((_QWORD *)this + 101);
  v39 = 0;
  (*(void (__fastcall **)(__int64, LPCRITICAL_SECTION *, __int64 **))(*(_QWORD *)v14 + 24LL))(
    v14,
    &lpCriticalSection,
    &v39);
  v15 = *v39;
  for ( i = *v39; ; v15 = i )
  {
    if ( !v15 )
      goto LABEL_17;
    Next = (unsigned int **)ATL::CAtlList<CAPONode *,CAPONodeTraits>::GetNext(v15, &i);
    v17 = *Next;
    if ( *(struct IAudioProcessingObject **)*Next == a3 )
      break;
  }
  if ( !v17 )
  {
LABEL_17:
    v18 = *((_QWORD *)this + 24);
    i = v18;
    while ( v18 )
    {
      v19 = (unsigned int **)ATL::CAtlList<CAPONode *,CAPONodeTraits>::GetNext(v15, &i);
      v17 = *v19;
      if ( *(struct IAudioProcessingObject **)*v19 == a3 )
        goto LABEL_22;
      v18 = i;
    }
    v17 = 0;
LABEL_22:
    if ( !v17 )
    {
      v20 = 2061;
LABEL_30:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audioprocessor.cpp",
        (const char *)0x887C001ALL,
        v36);
      if ( lpCriticalSection )
      {
        LeaveCriticalSection(lpCriticalSection);
        lpCriticalSection = 0;
      }
      ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)&p_pv);
      v24 = pv;
      pv = 0;
      if ( v24 )
        CoTaskMemFree(v24);
      return 2289827866LL;
    }
  }
  if ( v17[20] == *((_DWORD *)pv + 266) )
  {
    v8 = -2005139429;
    v21 = 2064;
    goto LABEL_26;
  }
  v22 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 101) + 32LL))(*((_QWORD *)this + 101), a4);
  if ( !v22 )
  {
    v20 = 2068;
    goto LABEL_30;
  }
  for ( j = 0; j < v17[20]; ++j )
  {
    if ( *(_QWORD *)&v17[2 * j + 34] == v22 )
    {
      v8 = -2147024809;
      v21 = 2072;
      goto LABEL_26;
    }
  }
  v27 = CAudioProcessor::ValidateConnection(
          (CAudioProcessor *)(v17 + 30),
          (struct CConnectionNode *)v22,
          v23,
          (struct APO_REG_PROPERTIES *)pv,
          (struct CConnectionNode **)v17 + 15,
          v17[19],
          v37);
  v28 = v27;
  if ( v27 >= 0 )
  {
    v30 = v17[20];
    if ( (unsigned int)v30 >= 2 )
    {
      v8 = -2147418113;
      v21 = 2079;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audioprocessor.cpp",
        (const char *)v8,
        v36);
      if ( lpCriticalSection )
      {
        LeaveCriticalSection(lpCriticalSection);
        lpCriticalSection = 0;
      }
      goto LABEL_11;
    }
    v31 = v17[20];
    v17[20] = v30 + 1;
    *(_QWORD *)&v17[2 * v30 + 34] = v22;
    ++*(_DWORD *)(v22 + 108);
    *(_QWORD *)(v22 + 96) = this;
    v32 = CAudioProcessor::EvaluateConnectionOwnership(this, (struct CConnectionNode *)v22);
    v33 = v32;
    if ( v32 >= 0 )
    {
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
      ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)&p_pv);
      v35 = pv;
      pv = 0;
      if ( v35 )
        CoTaskMemFree(v35);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x828,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audioprocessor.cpp",
        (const char *)(unsigned int)v32,
        v36);
      *(_QWORD *)&v17[2 * v31 + 34] = 0;
      --v17[20];
      if ( lpCriticalSection )
      {
        LeaveCriticalSection(lpCriticalSection);
        lpCriticalSection = 0;
      }
      ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)&p_pv);
      v34 = pv;
      pv = 0;
      if ( v34 )
        CoTaskMemFree(v34);
      return v33;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x81C,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audioprocessor.cpp",
      (const char *)(unsigned int)v27,
      v36);
    if ( lpCriticalSection )
    {
      LeaveCriticalSection(lpCriticalSection);
      lpCriticalSection = 0;
    }
    ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)&p_pv);
    v29 = pv;
    pv = 0;
    if ( v29 )
      CoTaskMemFree(v29);
    return v28;
  }
}

```

## disassembly

```asm
0x14006bde0  mov     [rsp-28h+arg_0], rbx
0x14006bde5  mov     [rsp-28h+arg_8], rsi
0x14006bdea  push    rbp
0x14006bdeb  push    rdi
0x14006bdec  push    r12
0x14006bdee  push    r14
0x14006bdf0  push    r15
0x14006bdf2  mov     rbp, rsp
0x14006bdf5  sub     rsp, 70h
0x14006bdf9  xor     r12d, r12d
0x14006bdfc  mov     r15, r9
0x14006bdff  mov     rdi, r8
0x14006be02  mov     rsi, rdx
0x14006be05  mov     r14, rcx
0x14006be08  test    r8, r8
0x14006be0b  jnz     short loc_14006BE1C
0x14006be0d  mov     ebx, 80070057h
0x14006be12  mov     edx, 7F6h
0x14006be17  jmp     loc_14006C18E
0x14006be1c  lea     rax, [r9-1]
0x14006be20  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14006be24  ja      loc_14006C184
0x14006be2a  lea     rax, [rdx-1]
0x14006be2e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14006be32  ja      loc_14006C17D
0x14006be38  lea     rax, [rbp+pv]
0x14006be3c  mov     [rbp+pv], r12
0x14006be40  mov     [rbp+var_18], rax
0x14006be44  lea     rdx, [rbp+var_10]
0x14006be48  mov     rax, [r8]
0x14006be4b  mov     rcx, rdi
0x14006be4e  mov     [rbp+var_10], r12
0x14006be52  mov     [rbp+var_8], 1
0x14006be56  mov     rax, [rax+28h]
0x14006be5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006be5f  lea     rcx, [rbp+var_18]
0x14006be63  mov     ebx, eax
0x14006be65  call    ??1?$out_param_t@V?$unique_ptr@UAPO_REG_PROPERTIES@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x14006be6a  test    ebx, ebx
0x14006be6c  jns     short loc_14006BEA2
0x14006be6e  mov     rcx, [rbp+28h]; this
0x14006be72  lea     r8, aAvcoreAudiocor_83; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14006be79  mov     r9d, ebx; char *
0x14006be7c  mov     edx, 7FBh; void *
0x14006be81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006be86  mov     rcx, [rbp+pv]; pv
0x14006be8a  mov     [rbp+pv], r12
0x14006be8e  test    rcx, rcx
0x14006be91  jz      loc_14006C1A1
0x14006be97  call    cs:__imp_CoTaskMemFree
0x14006be9d  jmp     loc_14006C1A1
0x14006bea2  lea     rdx, [r14+68h]; struct _RTL_CRITICAL_SECTION *
0x14006bea6  lea     rcx, [rbp+var_18]; this
0x14006beaa  call    ??0CCritSecLock@ATL@@QEAA@AEAU_RTL_CRITICAL_SECTION@@_N@Z; ATL::CCritSecLock::CCritSecLock(_RTL_CRITICAL_SECTION &,bool)
0x14006beaf  mov     rdx, rsi; unsigned __int64
0x14006beb2  mov     rcx, r14; this
0x14006beb5  call    ?ValidateTransactionState@CAudioProcessor@@AEAAJ_K@Z; CAudioProcessor::ValidateTransactionState(unsigned __int64)
0x14006beba  mov     ebx, eax
0x14006bebc  test    eax, eax
0x14006bebe  jns     short loc_14006BEE3
0x14006bec0  mov     rcx, [rbp+28h]; this
0x14006bec4  lea     r8, aAvcoreAudiocor_83; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14006becb  mov     r9d, eax; char *
0x14006bece  mov     edx, 800h; void *
0x14006bed3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006bed8  lea     rcx, [rbp+var_18]; this
0x14006bedc  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x14006bee1  jmp     short loc_14006BE86
0x14006bee3  mov     rcx, [r14+328h]
0x14006beea  lea     r8, [rbp+var_28]
0x14006beee  mov     [rbp+var_28], r12
0x14006bef2  lea     rdx, [rbp+lpCriticalSection]
0x14006bef6  mov     rax, [rcx]
0x14006bef9  mov     rax, [rax+18h]
0x14006befd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006bf02  mov     rax, [rbp+var_28]
0x14006bf06  mov     rcx, [rax]
0x14006bf09  mov     [rbp+var_20], rcx
0x14006bf0d  test    rcx, rcx
0x14006bf10  jz      short loc_14006BF2E
0x14006bf12  lea     rdx, [rbp+var_20]
0x14006bf16  call    ?GetNext@?$CAtlList@PEAVCAPONode@@VCAPONodeTraits@@@ATL@@QEAAAEAPEAVCAPONode@@AEAPEAU__POSITION@@@Z; ATL::CAtlList<CAPONode *,CAPONodeTraits>::GetNext(__POSITION * &)
0x14006bf1b  mov     rbx, [rax]
0x14006bf1e  cmp     [rbx], rdi
0x14006bf21  jz      short loc_14006BF29
0x14006bf23  mov     rcx, [rbp+var_20]
0x14006bf27  jmp     short loc_14006BF0D
0x14006bf29  test    rbx, rbx
0x14006bf2c  jnz     short loc_14006BF64
0x14006bf2e  mov     rax, [r14+0C0h]
0x14006bf35  mov     [rbp+var_20], rax
0x14006bf39  test    rax, rax
0x14006bf3c  jz      short loc_14006BF55
0x14006bf3e  lea     rdx, [rbp+var_20]
0x14006bf42  call    ?GetNext@?$CAtlList@PEAVCAPONode@@VCAPONodeTraits@@@ATL@@QEAAAEAPEAVCAPONode@@AEAPEAU__POSITION@@@Z; ATL::CAtlList<CAPONode *,CAPONodeTraits>::GetNext(__POSITION * &)
0x14006bf47  mov     rbx, [rax]
0x14006bf4a  cmp     [rbx], rdi
0x14006bf4d  jz      short loc_14006BF58
0x14006bf4f  mov     rax, [rbp+var_20]
0x14006bf53  jmp     short loc_14006BF39
0x14006bf55  mov     rbx, r12
0x14006bf58  test    rbx, rbx
0x14006bf5b  jnz     short loc_14006BF64
0x14006bf5d  mov     edx, 80Dh
0x14006bf62  jmp     short loc_14006BFD2
0x14006bf64  mov     rax, [rbp+pv]
0x14006bf68  mov     rsi, rbx
0x14006bf6b  mov     ecx, [rax+428h]
0x14006bf71  cmp     [rbx+50h], ecx
0x14006bf74  jnz     short loc_14006BFAF
0x14006bf76  mov     ebx, 887C001Bh
0x14006bf7b  mov     edx, 810h; void *
0x14006bf80  mov     rcx, [rbp+28h]; this
0x14006bf84  lea     r8, aAvcoreAudiocor_83; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14006bf8b  mov     r9d, ebx; char *
0x14006bf8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006bf93  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x14006bf97  test    rcx, rcx
0x14006bf9a  jz      loc_14006BED8
0x14006bfa0  call    cs:__imp_LeaveCriticalSection
0x14006bfa6  mov     [rbp+lpCriticalSection], r12
0x14006bfaa  jmp     loc_14006BED8
0x14006bfaf  mov     rcx, [r14+328h]
0x14006bfb6  mov     rdx, r15
0x14006bfb9  mov     rax, [rcx]
0x14006bfbc  mov     rax, [rax+20h]
0x14006bfc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006bfc5  mov     rdi, rax
0x14006bfc8  test    rax, rax
0x14006bfcb  jnz     short loc_14006C021
0x14006bfcd  mov     edx, 814h; void *
0x14006bfd2  mov     rcx, [rbp+28h]; this
0x14006bfd6  lea     r8, aAvcoreAudiocor_83; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14006bfdd  mov     r9d, 887C001Ah; char *
0x14006bfe3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006bfe8  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x14006bfec  test    rcx, rcx
0x14006bfef  jz      short loc_14006BFFB
0x14006bff1  call    cs:__imp_LeaveCriticalSection
0x14006bff7  mov     [rbp+lpCriticalSection], r12
0x14006bffb  lea     rcx, [rbp+var_18]; this
0x14006bfff  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x14006c004  mov     rcx, [rbp+pv]; pv
0x14006c008  mov     [rbp+pv], r12
0x14006c00c  test    rcx, rcx
0x14006c00f  jz      short loc_14006C017
0x14006c011  call    cs:__imp_CoTaskMemFree
0x14006c017  mov     eax, 887C001Ah
0x14006c01c  jmp     loc_14006C1A3
0x14006c021  mov     ecx, r12d
0x14006c024  cmp     ecx, [rbx+50h]
0x14006c027  jnb     short loc_14006C048
0x14006c029  mov     eax, ecx
0x14006c02b  cmp     [rsi+rax*8+88h], rdi
0x14006c033  jz      short loc_14006C039
0x14006c035  inc     ecx
0x14006c037  jmp     short loc_14006C024
0x14006c039  mov     ebx, 80070057h
0x14006c03e  mov     edx, 818h
0x14006c043  jmp     loc_14006BF80
0x14006c048  mov     eax, [rbx+4Ch]
0x14006c04b  lea     rcx, [rbx+78h]; this
0x14006c04f  mov     r9, [rbp+pv]; struct APO_REG_PROPERTIES *
0x14006c053  mov     rdx, rdi; struct CConnectionNode *
0x14006c056  mov     [rsp+70h+var_48], eax; unsigned int
0x14006c05a  mov     [rsp+70h+var_50], rcx; int
0x14006c05f  call    ?ValidateConnection@CAudioProcessor@@IEAAJPEAVCConnectionNode@@PEAUIAudioProcessingObject@@PEAUAPO_REG_PROPERTIES@@PEAPEAV2@I_N@Z; CAudioProcessor::ValidateConnection(CConnectionNode *,IAudioProcessingObject *,APO_REG_PROPERTIES *,CConnectionNode * *,uint,bool)
0x14006c064  mov     esi, eax
0x14006c066  test    eax, eax
0x14006c068  jns     short loc_14006C0B8
0x14006c06a  mov     rcx, [rbp+28h]; this
0x14006c06e  lea     r8, aAvcoreAudiocor_83; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14006c075  mov     r9d, eax; char *
0x14006c078  mov     edx, 81Ch; void *
0x14006c07d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006c082  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x14006c086  test    rcx, rcx
0x14006c089  jz      short loc_14006C095
0x14006c08b  call    cs:__imp_LeaveCriticalSection
0x14006c091  mov     [rbp+lpCriticalSection], r12
0x14006c095  lea     rcx, [rbp+var_18]; this
0x14006c099  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x14006c09e  mov     rcx, [rbp+pv]; pv
0x14006c0a2  mov     [rbp+pv], r12
0x14006c0a6  test    rcx, rcx
0x14006c0a9  jz      short loc_14006C0B1
0x14006c0ab  call    cs:__imp_CoTaskMemFree
0x14006c0b1  mov     eax, esi
0x14006c0b3  jmp     loc_14006C1A3
0x14006c0b8  mov     ecx, [rbx+50h]
0x14006c0bb  cmp     ecx, 2
0x14006c0be  jb      short loc_14006C0CF
0x14006c0c0  mov     ebx, 8000FFFFh
0x14006c0c5  mov     edx, 81Fh
0x14006c0ca  jmp     loc_14006BF80
0x14006c0cf  lea     eax, [rcx+1]
0x14006c0d2  mov     rsi, rcx
0x14006c0d5  mov     [rbx+50h], eax
0x14006c0d8  mov     rdx, rdi; struct CConnectionNode *
0x14006c0db  mov     [rbx+rcx*8+88h], rdi
0x14006c0e3  mov     rcx, r14; this
0x14006c0e6  inc     dword ptr [rdi+6Ch]
0x14006c0e9  mov     [rdi+60h], r14
0x14006c0ed  call    ?EvaluateConnectionOwnership@CAudioProcessor@@AEAAJPEAVCConnectionNode@@@Z; CAudioProcessor::EvaluateConnectionOwnership(CConnectionNode *)
0x14006c0f2  mov     edi, eax
0x14006c0f4  test    eax, eax
0x14006c0f6  jns     short loc_14006C14E
0x14006c0f8  mov     rcx, [rbp+28h]; this
0x14006c0fc  lea     r8, aAvcoreAudiocor_83; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14006c103  mov     r9d, eax; char *
0x14006c106  mov     edx, 828h; void *
0x14006c10b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006c110  mov     [rbx+rsi*8+88h], r12
0x14006c118  dec     dword ptr [rbx+50h]
0x14006c11b  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x14006c11f  test    rcx, rcx
0x14006c122  jz      short loc_14006C12E
0x14006c124  call    cs:__imp_LeaveCriticalSection
0x14006c12a  mov     [rbp+lpCriticalSection], r12
0x14006c12e  lea     rcx, [rbp+var_18]; this
0x14006c132  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x14006c137  mov     rcx, [rbp+pv]; pv
0x14006c13b  mov     [rbp+pv], r12
0x14006c13f  test    rcx, rcx
0x14006c142  jz      short loc_14006C14A
0x14006c144  call    cs:__imp_CoTaskMemFree
0x14006c14a  mov     eax, edi
0x14006c14c  jmp     short loc_14006C1A3
0x14006c14e  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x14006c152  test    rcx, rcx
0x14006c155  jz      short loc_14006C15D
0x14006c157  call    cs:__imp_LeaveCriticalSection
0x14006c15d  lea     rcx, [rbp+var_18]; this
0x14006c161  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x14006c166  mov     rcx, [rbp+pv]; pv
0x14006c16a  mov     [rbp+pv], r12
0x14006c16e  test    rcx, rcx
0x14006c171  jz      short loc_14006C179
0x14006c173  call    cs:__imp_CoTaskMemFree
0x14006c179  xor     eax, eax
0x14006c17b  jmp     short loc_14006C1A3
0x14006c17d  mov     edx, 7F8h
0x14006c182  jmp     short loc_14006C189
0x14006c184  mov     edx, 7F7h; void *
0x14006c189  mov     ebx, 80070006h
0x14006c18e  mov     rcx, [rbp+28h]; this
0x14006c192  lea     r8, aAvcoreAudiocor_83; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14006c199  mov     r9d, ebx; char *
0x14006c19c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006c1a1  mov     eax, ebx
0x14006c1a3  lea     r11, [rsp+70h+var_s0]
0x14006c1a8  mov     rbx, [r11+30h]
0x14006c1ac  mov     rsi, [r11+38h]
0x14006c1b0  mov     rsp, r11
0x14006c1b3  pop     r15
0x14006c1b5  pop     r14
0x14006c1b7  pop     r12
0x14006c1b9  pop     rdi
0x14006c1ba  pop     rbp
0x14006c1bb  retn
```
