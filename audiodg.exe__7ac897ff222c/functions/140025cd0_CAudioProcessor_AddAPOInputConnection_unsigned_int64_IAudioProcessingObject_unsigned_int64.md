# CAudioProcessor::AddAPOInputConnection(unsigned __int64,IAudioProcessingObject *,unsigned __int64)

- ea: `0x140025cd0`
- end: `0x1400260ec`
- name: `?AddAPOInputConnection@CAudioProcessor@@UEAAJ_KPEAUIAudioProcessingObject@@0@Z`
- size: `1052`
- prototype: `__int64 __fastcall(CAudioProcessor *__hidden this, unsigned __int64, struct IAudioProcessingObject *, unsigned __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000ba54`
- `0x14000bb20`
- `0x14000c33c`
- `0x140010980`
- `0x140025cd0`
- `0x140026374`
- `0x1400263a0`
- `0x1400543e8`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140025e9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140025eed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140025f87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140025fe2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140025ffa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140026054`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140026087`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140025e9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140025eed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140025f87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140025fe2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140025ffa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140026054`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140026087`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140025d6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140025d9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140025f0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140025fa7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140026074`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400260a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140025d6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140025d9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140025f0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140025fa7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140026074`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400260a3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAudioProcessor::AddAPOInputConnection(
        CAudioProcessor *this,
        unsigned __int64 a2,
        struct IAudioProcessingObject *a3,
        __int64 a4)
{
  unsigned int v8; // ebx
  __int64 v9; // rdx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  void *v11; // rcx
  int v12; // eax
  _QWORD *i; // rcx
  struct IAudioProcessingObject **v14; // rbx
  __int64 v15; // rax
  struct IAudioProcessingObject ***Next; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rdi
  struct IAudioProcessingObject *v20; // r8
  void *v21; // rcx
  bool v22; // zf
  unsigned int j; // ecx
  int v25; // eax
  unsigned int v26; // esi
  void *v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rsi
  int v30; // eax
  unsigned int v31; // edi
  void *v32; // rcx
  void *v33; // rcx
  int v34; // [rsp+20h] [rbp-50h]
  int v35; // [rsp+20h] [rbp-50h]
  bool v36; // [rsp+30h] [rbp-40h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+40h] [rbp-30h] BYREF
  _QWORD *v38; // [rsp+48h] [rbp-28h] BYREF
  __int64 v39; // [rsp+50h] [rbp-20h] BYREF
  LPCRITICAL_SECTION p_pv; // [rsp+58h] [rbp-18h] BYREF
  struct _RTL_CRITICAL_SECTION_DEBUG *v41; // [rsp+60h] [rbp-10h] BYREF
  char v42; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  LPVOID pv; // [rsp+B0h] [rbp+40h] BYREF

  if ( !a3 )
  {
    v8 = -2147024809;
    v9 = 1844;
LABEL_67:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audioprocessor.cpp",
      (const char *)v8,
      v34);
    return v8;
  }
  if ( (unsigned __int64)(a4 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v9 = 1845;
    goto LABEL_66;
  }
  if ( a2 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v9 = 1846;
LABEL_66:
    v8 = -2147024890;
    goto LABEL_67;
  }
  pv = 0;
  p_pv = (LPCRITICAL_SECTION)&pv;
  v41 = 0;
  v42 = 1;
  v8 = ((__int64 (__fastcall *)(struct IAudioProcessingObject *, struct _RTL_CRITICAL_SECTION_DEBUG **))a3->lpVtbl->GetRegistrationProperties)(
         a3,
         &v41);
  if ( v42 )
  {
    DebugInfo = p_pv->DebugInfo;
    p_pv->DebugInfo = v41;
    if ( DebugInfo )
      CoTaskMemFree(DebugInfo);
  }
  if ( (v8 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x739,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audioprocessor.cpp",
      (const char *)v8,
      v34);
    goto LABEL_10;
  }
  p_pv = (LPCRITICAL_SECTION)((char *)this + 104);
  LOBYTE(v41) = 0;
  ATL::CCritSecLock::Lock((ATL::CCritSecLock *)&p_pv);
  v12 = CAudioProcessor::ValidateTransactionState(this, a2);
  v8 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x73E,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audioprocessor.cpp",
      (const char *)(unsigned int)v12,
      v34);
LABEL_14:
    ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)&p_pv);
LABEL_10:
    v11 = pv;
    pv = 0;
    if ( v11 )
      CoTaskMemFree(v11);
    return v8;
  }
  v38 = 0;
  (*(void (__fastcall **)(_QWORD, LPCRITICAL_SECTION *, _QWORD **))(**((_QWORD **)this + 101) + 24LL))(
    *((_QWORD *)this + 101),
    &lpCriticalSection,
    &v38);
  for ( i = (_QWORD *)*v38; i; i = (_QWORD *)*i )
  {
    v14 = (struct IAudioProcessingObject **)i[2];
    if ( *v14 == a3 )
      goto LABEL_26;
  }
  v15 = *((_QWORD *)this + 24);
  v39 = v15;
  while ( v15 )
  {
    Next = (struct IAudioProcessingObject ***)ATL::CAtlList<CAPONode *,CAPONodeTraits>::GetNext(i, &v39);
    v14 = *Next;
    if ( **Next == a3 )
      goto LABEL_24;
    v15 = v39;
  }
  v14 = 0;
LABEL_24:
  if ( !v14 )
  {
    v17 = 1867;
LABEL_32:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audioprocessor.cpp",
      (const char *)0x887C001ALL,
      v34);
    if ( lpCriticalSection )
    {
      LeaveCriticalSection(lpCriticalSection);
      lpCriticalSection = 0;
    }
    ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)&p_pv);
    v21 = pv;
    v22 = pv == 0;
    pv = 0;
    if ( !v22 )
      CoTaskMemFree(v21);
    return 2289827866LL;
  }
LABEL_26:
  if ( *((_DWORD *)v14 + 19) == *((_DWORD *)pv + 264) )
  {
    v8 = -2005139429;
    v18 = 1870;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audioprocessor.cpp",
      (const char *)v8,
      v34);
    if ( lpCriticalSection )
    {
      LeaveCriticalSection(lpCriticalSection);
      lpCriticalSection = 0;
    }
    goto LABEL_14;
  }
  v19 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 101) + 32LL))(*((_QWORD *)this + 101), a4);
  if ( !v19 )
  {
    v17 = 1874;
    goto LABEL_32;
  }
  for ( j = 0; j < *((_DWORD *)v14 + 19); ++j )
  {
    if ( v14[j + 15] == (struct IAudioProcessingObject *)v19 )
    {
      v8 = -2147024809;
      v18 = 1878;
      goto LABEL_28;
    }
  }
  v25 = CAudioProcessor::ValidateConnection(
          (CAudioProcessor *)(v14 + 17),
          (struct CConnectionNode *)v19,
          v20,
          (struct APO_REG_PROPERTIES *)pv,
          (struct CConnectionNode **)v14 + 17,
          *((_DWORD *)v14 + 20),
          v36);
  v26 = v25;
  if ( v25 >= 0 )
  {
    v28 = *((unsigned int *)v14 + 19);
    if ( (unsigned int)v28 >= 2 )
    {
      v8 = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x75D,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audioprocessor.cpp",
        (const char *)0x8000FFFFLL,
        v35);
      if ( lpCriticalSection )
      {
        LeaveCriticalSection(lpCriticalSection);
        lpCriticalSection = 0;
      }
      if ( (_BYTE)v41 )
        LeaveCriticalSection(p_pv);
      goto LABEL_10;
    }
    *((_DWORD *)v14 + 19) = v28 + 1;
    v29 = v28;
    v14[v28 + 15] = (struct IAudioProcessingObject *)v19;
    ++*(_DWORD *)(v19 + 108);
    *(_QWORD *)(v19 + 96) = this;
    v30 = CAudioProcessor::EvaluateConnectionOwnership(this, (struct CConnectionNode *)v19);
    v31 = v30;
    if ( v30 >= 0 )
    {
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
      ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)&p_pv);
      v33 = pv;
      pv = 0;
      if ( v33 )
        CoTaskMemFree(v33);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x767,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audioprocessor.cpp",
        (const char *)(unsigned int)v30,
        v35);
      v14[v29 + 15] = 0;
      --*((_DWORD *)v14 + 19);
      if ( lpCriticalSection )
      {
        LeaveCriticalSection(lpCriticalSection);
        lpCriticalSection = 0;
      }
      ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)&p_pv);
      v32 = pv;
      pv = 0;
      if ( v32 )
        CoTaskMemFree(v32);
      return v31;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x75A,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audioprocessor.cpp",
      (const char *)(unsigned int)v25,
      v35);
    if ( lpCriticalSection )
    {
      LeaveCriticalSection(lpCriticalSection);
      lpCriticalSection = 0;
    }
    ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)&p_pv);
    v27 = pv;
    pv = 0;
    if ( v27 )
      CoTaskMemFree(v27);
    return v26;
  }
}

```

## disassembly

```asm
0x140025cd0  mov     [rsp-28h+arg_0], rbx
0x140025cd5  mov     [rsp-28h+arg_8], rsi
0x140025cda  push    rbp
0x140025cdb  push    rdi
0x140025cdc  push    r12
0x140025cde  push    r14
0x140025ce0  push    r15
0x140025ce2  mov     rbp, rsp
0x140025ce5  sub     rsp, 70h
0x140025ce9  mov     r15, r9
0x140025cec  mov     rdi, r8
0x140025cef  mov     rsi, rdx
0x140025cf2  mov     r14, rcx
0x140025cf5  xor     r12d, r12d
0x140025cf8  test    r8, r8
0x140025cfb  jnz     short loc_140025D0C
0x140025cfd  mov     ebx, 80070057h
0x140025d02  mov     edx, 734h
0x140025d07  jmp     loc_1400260BE
0x140025d0c  lea     rax, [r9-1]
0x140025d10  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140025d14  ja      loc_1400260B4
0x140025d1a  lea     rax, [rdx-1]
0x140025d1e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140025d22  ja      loc_1400260AD
0x140025d28  mov     [rbp+pv], r12
0x140025d2c  lea     rax, [rbp+pv]
0x140025d30  mov     [rbp+var_18], rax
0x140025d34  mov     [rbp+var_10], r12
0x140025d38  mov     [rbp+var_8], 1
0x140025d3c  mov     rax, [r8]
0x140025d3f  lea     rdx, [rbp+var_10]
0x140025d43  mov     rcx, rdi
0x140025d46  mov     rax, [rax+28h]
0x140025d4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025d4f  mov     ebx, eax
0x140025d51  cmp     [rbp+var_8], r12b
0x140025d55  jz      short loc_140025D70
0x140025d57  mov     r8, [rbp+var_18]
0x140025d5b  mov     rcx, [r8]; pv
0x140025d5e  mov     rdx, [rbp+var_10]
0x140025d62  mov     [r8], rdx
0x140025d65  test    rcx, rcx
0x140025d68  jz      short loc_140025D70
0x140025d6a  call    cs:__imp_CoTaskMemFree
0x140025d70  test    ebx, ebx
0x140025d72  jns     short loc_140025DA8
0x140025d74  mov     rcx, [rbp+28h]; this
0x140025d78  mov     r9d, ebx; char *
0x140025d7b  lea     r8, aAvcoreAudiocor_83; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140025d82  mov     edx, 739h; void *
0x140025d87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140025d8c  mov     rcx, [rbp+pv]; pv
0x140025d90  mov     [rbp+pv], r12
0x140025d94  test    rcx, rcx
0x140025d97  jz      loc_1400260D1
0x140025d9d  call    cs:__imp_CoTaskMemFree
0x140025da3  jmp     loc_1400260D1
0x140025da8  lea     rax, [r14+68h]
0x140025dac  mov     [rbp+var_18], rax
0x140025db0  mov     byte ptr [rbp+var_10], r12b
0x140025db4  lea     rcx, [rbp+var_18]; this
0x140025db8  call    ?Lock@CCritSecLock@ATL@@QEAAXXZ; ATL::CCritSecLock::Lock(void)
0x140025dbd  mov     rdx, rsi; unsigned __int64
0x140025dc0  mov     rcx, r14; this
0x140025dc3  call    ?ValidateTransactionState@CAudioProcessor@@AEAAJ_K@Z; CAudioProcessor::ValidateTransactionState(unsigned __int64)
0x140025dc8  mov     ebx, eax
0x140025dca  test    eax, eax
0x140025dcc  jns     short loc_140025DF1
0x140025dce  mov     rcx, [rbp+28h]; this
0x140025dd2  mov     r9d, eax; char *
0x140025dd5  lea     r8, aAvcoreAudiocor_83; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140025ddc  mov     edx, 73Eh; void *
0x140025de1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140025de6  lea     rcx, [rbp+var_18]; this
0x140025dea  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x140025def  jmp     short loc_140025D8C
0x140025df1  mov     [rbp+var_28], r12
0x140025df5  mov     rcx, [r14+328h]
0x140025dfc  mov     rax, [rcx]
0x140025dff  lea     r8, [rbp+var_28]
0x140025e03  lea     rdx, [rbp+lpCriticalSection]
0x140025e07  mov     rax, [rax+18h]
0x140025e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025e10  mov     rax, [rbp+var_28]
0x140025e14  mov     rcx, [rax]
0x140025e17  test    rcx, rcx
0x140025e1a  jz      short loc_140025E2A
0x140025e1c  mov     rbx, [rcx+10h]
0x140025e20  cmp     [rbx], rdi
0x140025e23  jz      short loc_140025E60
0x140025e25  mov     rcx, [rcx]
0x140025e28  jmp     short loc_140025E17
0x140025e2a  mov     rax, [r14+0C0h]
0x140025e31  mov     [rbp+var_20], rax
0x140025e35  test    rax, rax
0x140025e38  jz      short loc_140025E51
0x140025e3a  lea     rdx, [rbp+var_20]
0x140025e3e  call    ?GetNext@?$CAtlList@PEAVCAPONode@@VCAPONodeTraits@@@ATL@@QEAAAEAPEAVCAPONode@@AEAPEAU__POSITION@@@Z; ATL::CAtlList<CAPONode *,CAPONodeTraits>::GetNext(__POSITION * &)
0x140025e43  mov     rbx, [rax]
0x140025e46  cmp     [rbx], rdi
0x140025e49  jz      short loc_140025E54
0x140025e4b  mov     rax, [rbp+var_20]
0x140025e4f  jmp     short loc_140025E35
0x140025e51  mov     rbx, r12
0x140025e54  test    rbx, rbx
0x140025e57  jnz     short loc_140025E60
0x140025e59  mov     edx, 74Bh
0x140025e5e  jmp     short loc_140025ECE
0x140025e60  mov     rsi, rbx
0x140025e63  mov     rax, [rbp+pv]
0x140025e67  mov     ecx, [rax+420h]
0x140025e6d  cmp     [rbx+4Ch], ecx
0x140025e70  jnz     short loc_140025EAB
0x140025e72  mov     ebx, 887C001Bh
0x140025e77  mov     edx, 74Eh; void *
0x140025e7c  lea     r8, aAvcoreAudiocor_83; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140025e83  mov     r9d, ebx; char *
0x140025e86  mov     rcx, [rbp+28h]; this
0x140025e8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140025e8f  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x140025e93  test    rcx, rcx
0x140025e96  jz      loc_140025DE6
0x140025e9c  call    cs:__imp_LeaveCriticalSection
0x140025ea2  mov     [rbp+lpCriticalSection], r12
0x140025ea6  jmp     loc_140025DE6
0x140025eab  mov     rcx, [r14+328h]
0x140025eb2  mov     rax, [rcx]
0x140025eb5  mov     rdx, r15
0x140025eb8  mov     rax, [rax+20h]
0x140025ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025ec1  mov     rdi, rax
0x140025ec4  test    rax, rax
0x140025ec7  jnz     short loc_140025F1D
0x140025ec9  mov     edx, 752h; void *
0x140025ece  mov     r9d, 887C001Ah; char *
0x140025ed4  lea     r8, aAvcoreAudiocor_83; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140025edb  mov     rcx, [rbp+28h]; this
0x140025edf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140025ee4  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x140025ee8  test    rcx, rcx
0x140025eeb  jz      short loc_140025EF7
0x140025eed  call    cs:__imp_LeaveCriticalSection
0x140025ef3  mov     [rbp+lpCriticalSection], r12
0x140025ef7  lea     rcx, [rbp+var_18]; this
0x140025efb  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x140025f00  mov     rcx, [rbp+pv]; pv
0x140025f04  test    rcx, rcx
0x140025f07  mov     [rbp+pv], r12
0x140025f0b  jz      short loc_140025F13
0x140025f0d  call    cs:__imp_CoTaskMemFree
0x140025f13  mov     eax, 887C001Ah
0x140025f18  jmp     loc_1400260D3
0x140025f1d  mov     ecx, r12d
0x140025f20  cmp     ecx, [rbx+4Ch]
0x140025f23  jnb     short loc_140025F41
0x140025f25  mov     eax, ecx
0x140025f27  cmp     [rsi+rax*8+78h], rdi
0x140025f2c  jz      short loc_140025F32
0x140025f2e  inc     ecx
0x140025f30  jmp     short loc_140025F20
0x140025f32  mov     ebx, 80070057h
0x140025f37  mov     edx, 756h
0x140025f3c  jmp     loc_140025E7C
0x140025f41  lea     rcx, [rbx+88h]; this
0x140025f48  mov     eax, [rbx+50h]
0x140025f4b  mov     [rsp+70h+var_48], eax; unsigned int
0x140025f4f  mov     [rsp+70h+var_50], rcx; int
0x140025f54  mov     r9, [rbp+pv]; struct APO_REG_PROPERTIES *
0x140025f58  mov     rdx, rdi; struct CConnectionNode *
0x140025f5b  call    ?ValidateConnection@CAudioProcessor@@IEAAJPEAVCConnectionNode@@PEAUIAudioProcessingObject@@PEAUAPO_REG_PROPERTIES@@PEAPEAV2@I_N@Z; CAudioProcessor::ValidateConnection(CConnectionNode *,IAudioProcessingObject *,APO_REG_PROPERTIES *,CConnectionNode * *,uint,bool)
0x140025f60  mov     esi, eax
0x140025f62  test    eax, eax
0x140025f64  jns     short loc_140025FB4
0x140025f66  mov     rcx, [rbp+28h]; this
0x140025f6a  mov     r9d, eax; char *
0x140025f6d  lea     r8, aAvcoreAudiocor_83; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140025f74  mov     edx, 75Ah; void *
0x140025f79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140025f7e  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x140025f82  test    rcx, rcx
0x140025f85  jz      short loc_140025F91
0x140025f87  call    cs:__imp_LeaveCriticalSection
0x140025f8d  mov     [rbp+lpCriticalSection], r12
0x140025f91  lea     rcx, [rbp+var_18]; this
0x140025f95  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x140025f9a  mov     rcx, [rbp+pv]; pv
0x140025f9e  mov     [rbp+pv], r12
0x140025fa2  test    rcx, rcx
0x140025fa5  jz      short loc_140025FAD
0x140025fa7  call    cs:__imp_CoTaskMemFree
0x140025fad  mov     eax, esi
0x140025faf  jmp     loc_1400260D3
0x140025fb4  mov     ecx, [rbx+4Ch]
0x140025fb7  cmp     ecx, 2
0x140025fba  jb      short loc_140026005
0x140025fbc  mov     rcx, [rbp+28h]; this
0x140025fc0  mov     ebx, 8000FFFFh
0x140025fc5  mov     r9d, ebx; char *
0x140025fc8  lea     r8, aAvcoreAudiocor_83; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140025fcf  mov     edx, 75Dh; void *
0x140025fd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140025fd9  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x140025fdd  test    rcx, rcx
0x140025fe0  jz      short loc_140025FEC
0x140025fe2  call    cs:__imp_LeaveCriticalSection
0x140025fe8  mov     [rbp+lpCriticalSection], r12
0x140025fec  cmp     byte ptr [rbp+var_10], r12b
0x140025ff0  jz      loc_140025D8C
0x140025ff6  mov     rcx, [rbp+var_18]; lpCriticalSection
0x140025ffa  call    cs:__imp_LeaveCriticalSection
0x140026000  jmp     loc_140025D8C
0x140026005  lea     eax, [rcx+1]
0x140026008  mov     [rbx+4Ch], eax
0x14002600b  mov     rsi, rcx
0x14002600e  mov     [rbx+rcx*8+78h], rdi
0x140026013  inc     dword ptr [rdi+6Ch]
0x140026016  mov     [rdi+60h], r14
0x14002601a  mov     rdx, rdi; struct CConnectionNode *
0x14002601d  mov     rcx, r14; this
0x140026020  call    ?EvaluateConnectionOwnership@CAudioProcessor@@AEAAJPEAVCConnectionNode@@@Z; CAudioProcessor::EvaluateConnectionOwnership(CConnectionNode *)
0x140026025  mov     edi, eax
0x140026027  test    eax, eax
0x140026029  jns     short loc_14002607E
0x14002602b  mov     rcx, [rbp+28h]; this
0x14002602f  mov     r9d, eax; char *
0x140026032  lea     r8, aAvcoreAudiocor_83; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140026039  mov     edx, 767h; void *
0x14002603e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140026043  mov     [rbx+rsi*8+78h], r12
0x140026048  dec     dword ptr [rbx+4Ch]
0x14002604b  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x14002604f  test    rcx, rcx
0x140026052  jz      short loc_14002605E
0x140026054  call    cs:__imp_LeaveCriticalSection
0x14002605a  mov     [rbp+lpCriticalSection], r12
0x14002605e  lea     rcx, [rbp+var_18]; this
0x140026062  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x140026067  mov     rcx, [rbp+pv]; pv
0x14002606b  mov     [rbp+pv], r12
0x14002606f  test    rcx, rcx
0x140026072  jz      short loc_14002607A
0x140026074  call    cs:__imp_CoTaskMemFree
0x14002607a  mov     eax, edi
0x14002607c  jmp     short loc_1400260D3
0x14002607e  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x140026082  test    rcx, rcx
0x140026085  jz      short loc_14002608D
0x140026087  call    cs:__imp_LeaveCriticalSection
0x14002608d  lea     rcx, [rbp+var_18]; this
0x140026091  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x140026096  mov     rcx, [rbp+pv]; pv
0x14002609a  mov     [rbp+pv], r12
0x14002609e  test    rcx, rcx
0x1400260a1  jz      short loc_1400260A9
0x1400260a3  call    cs:__imp_CoTaskMemFree
0x1400260a9  xor     eax, eax
0x1400260ab  jmp     short loc_1400260D3
0x1400260ad  mov     edx, 736h
0x1400260b2  jmp     short loc_1400260B9
0x1400260b4  mov     edx, 735h; void *
0x1400260b9  mov     ebx, 80070006h
0x1400260be  mov     r9d, ebx; char *
0x1400260c1  lea     r8, aAvcoreAudiocor_83; "avcore\\audiocore\\server\\audiodg\\exe"...
0x1400260c8  mov     rcx, [rbp+28h]; this
0x1400260cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400260d1  mov     eax, ebx
0x1400260d3  lea     r11, [rsp+70h+var_s0]
0x1400260d8  mov     rbx, [r11+30h]
0x1400260dc  mov     rsi, [r11+38h]
0x1400260e0  mov     rsp, r11
0x1400260e3  pop     r15
0x1400260e5  pop     r14
0x1400260e7  pop     r12
0x1400260e9  pop     rdi
0x1400260ea  pop     rbp
0x1400260eb  retn
```
