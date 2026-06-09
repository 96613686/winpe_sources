# KSMidiDevice::OpenStream(ulong &,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004)

- ea: `0x180028bc8`
- end: `0x180029030`
- name: `?OpenStream@KSMidiDevice@@IEAAJAEAKW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@@Z`
- size: `1128`
- prototype: `__int64 __fastcall(__int64, unsigned int *, int)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180028300`

## callees

- `0x180004410`
- `0x180004434`
- `0x180004bf0`
- `0x180005260`
- `0x18000a814`
- `0x18000bb04`
- `0x18000f684`
- `0x180010f30`
- `0x180011400`
- `0x180025cfc`
- `0x180026760`
- `0x1800267e4`
- `0x180027910`
- `0x180027ba4`
- `0x180027ddc`
- `0x180027f00`
- `0x180028bc8`
- `0x18002a3c0`
- `0x18003c59c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180028f3b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180028f3b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180028ddb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180028ddb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028e8e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028f6e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028e8e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028f6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028e7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028e7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028e86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028fd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028fea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028e86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028fd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028fea`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180028ea0`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180028ea0`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180028e5c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180028e5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028c3c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028f59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028ff9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028c3c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028f59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028ff9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall KSMidiDevice::OpenStream(__int64 a1, unsigned int *a2, int a3)
{
  char *Handle; // rbx
  unsigned int v7; // edi
  __int64 *v9; // rax
  __int64 v10; // rcx
  KsHandleWrapper *v11; // rdi
  void *v12; // rdi
  int v13; // eax
  char *v14; // rax
  char *v15; // rcx
  MEMORY_MAPPED_PIPE *v16; // rdi
  __int64 v17; // rax
  __int64 v18; // rdx
  _DWORD *v19; // rax
  _DWORD *v20; // rdi
  CMidiXProc *v21; // r14
  __int64 v22; // r9
  HRESULT v23; // eax
  void *v24; // r14
  DWORD LastError; // edi
  __int64 v26; // r8
  _WORD **v27; // rcx
  _WORD *v28; // rdi
  __int64 v29; // rdi
  const WCHAR *v30; // r9
  HANDLE EventW; // r12
  void *v32; // r14
  DWORD v33; // r15d
  unsigned int v34; // r8d
  const char *v35; // r9
  int v36; // [rsp+20h] [rbp-40h]
  int v37; // [rsp+20h] [rbp-40h]
  LPVOID pv; // [rsp+30h] [rbp-30h] BYREF
  void *Block[2]; // [rsp+38h] [rbp-28h] BYREF
  GUID pguid; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  Handle = (char *)KsHandleWrapper::GetHandle(*(PSRWLOCK *)(a1 + 48));
  Block[1] = Handle;
  if ( ((unsigned __int64)(Handle + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v7 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC1,
      (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
      (const char *)0x8007000ELL,
      v36);
    if ( (unsigned __int64)(Handle - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      return v7;
LABEL_3:
    CloseHandle(Handle);
    return v7;
  }
  pv = Handle;
  *(_QWORD *)&pguid.Data1 = *(_QWORD *)(a1 + 64);
  v9 = (__int64 *)std::make_unique<KsHandleWrapper,unsigned short *,unsigned int &,enum _MidiTransport &,void *,0>(
                    (unsigned int)Block,
                    (unsigned int)&pguid,
                    (int)a1 + 72,
                    (int)a1 + 76,
                    (__int64)&pv);
  v10 = *v9;
  *v9 = 0;
  v11 = *(KsHandleWrapper **)(a1 + 56);
  *(_QWORD *)(a1 + 56) = v10;
  if ( v11 )
  {
    KsHandleWrapper::~KsHandleWrapper(v11);
    operator delete(v11);
  }
  v12 = Block[0];
  if ( Block[0] )
  {
    KsHandleWrapper::~KsHandleWrapper((KsHandleWrapper *)Block[0]);
    operator delete(v12);
  }
  v13 = KsHandleWrapper::Open(*(KsHandleWrapper **)(a1 + 56));
  v7 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
      (const char *)(unsigned int)v13,
      v37);
    goto LABEL_3;
  }
  if ( ((*(_DWORD *)(a1 + 76) - 2) & 0xFFFFFFFD) != 0 )
  {
    *a2 = 0;
  }
  else
  {
    pguid = 0;
    pv = 0;
    v14 = (char *)operator new(0x68u, (const struct std::nothrow_t *)std::nothrow);
    v15 = v14;
    if ( v14 )
    {
      *(_QWORD *)v14 = 0;
      *((_QWORD *)v14 + 1) = 0;
      *((_QWORD *)v14 + 2) = 0;
      *((_QWORD *)v14 + 3) = 0;
      *((_DWORD *)v14 + 8) = 0;
      *((_QWORD *)v14 + 5) = 0;
      *((_QWORD *)v14 + 6) = 0;
      *((_QWORD *)v14 + 7) = 0;
      *((_QWORD *)v14 + 8) = 0;
      *(_OWORD *)(v14 + 72) = 0;
      *((_QWORD *)v14 + 11) = 0;
      *((_QWORD *)v14 + 12) = 7;
      *((_WORD *)v14 + 36) = 0;
    }
    else
    {
      v15 = 0;
    }
    v16 = *(MEMORY_MAPPED_PIPE **)(a1 + 80);
    *(_QWORD *)(a1 + 80) = v15;
    if ( v16 )
    {
      MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(v16);
      operator delete(v16);
    }
    v17 = *(_QWORD *)(a1 + 80);
    if ( !v17 )
    {
      v18 = 206;
LABEL_26:
      v7 = -2147024882;
      v22 = 2147942414LL;
      goto LABEL_51;
    }
    *(_DWORD *)(v17 + 4) = a3;
    **(_DWORD **)(a1 + 80) = (*(_DWORD *)(a1 + 76) != 2) + 1;
    v19 = operator new(0x90u, (const struct std::nothrow_t *)std::nothrow);
    v20 = v19;
    Block[0] = v19;
    if ( v19 )
    {
      *v19 = 1;
      InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v19 + 2), 0, 0);
      *((_BYTE *)v20 + 48) = 0;
      v20[13] = 0;
      *((_QWORD *)v20 + 7) = 0;
      *((_QWORD *)v20 + 8) = 0;
      *((_QWORD *)v20 + 9) = 0;
      v20[20] = 0;
      *((_QWORD *)v20 + 11) = 0;
      *((_QWORD *)v20 + 12) = 0;
      *((_QWORD *)v20 + 13) = 0;
      *((_QWORD *)v20 + 14) = 0;
      *((_QWORD *)v20 + 15) = 0;
      *((_QWORD *)v20 + 16) = 0;
      *((_QWORD *)v20 + 17) = 0;
    }
    else
    {
      v20 = 0;
    }
    v21 = *(CMidiXProc **)(a1 + 88);
    *(_QWORD *)(a1 + 88) = v20;
    if ( v21 )
    {
      CMidiXProc::~CMidiXProc(v21);
      operator delete(v21);
    }
    if ( !*(_QWORD *)(a1 + 88) )
    {
      v18 = 211;
      goto LABEL_26;
    }
    v23 = CoCreateGuid(&pguid);
    v7 = v23;
    if ( v23 < 0 )
    {
      v18 = 214;
LABEL_50:
      v22 = (unsigned int)v23;
LABEL_51:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
        (const char *)v22,
        v37);
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_3;
    }
    v24 = pv;
    if ( pv )
    {
      LastError = GetLastError();
      CoTaskMemFree(v24);
      SetLastError(LastError);
    }
    pv = 0;
    v23 = StringFromCLSID(&pguid, (LPOLESTR *)&pv);
    v7 = v23;
    if ( v23 < 0 )
    {
      v18 = 215;
      goto LABEL_50;
    }
    _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(*(_QWORD *)(a1 + 80) + 56LL);
    v27 = (_WORD **)(*(_QWORD *)(a1 + 80) + 72LL);
    if ( *(_QWORD *)(*(_QWORD *)(a1 + 80) + 96LL) < 7u )
    {
      ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
        v27,
        7,
        v26,
        L"Global\\");
    }
    else
    {
      if ( *(_QWORD *)(*(_QWORD *)(a1 + 80) + 96LL) <= 7u )
        v28 = (_WORD *)(*(_QWORD *)(a1 + 80) + 72LL);
      else
        v28 = *v27;
      *(_QWORD *)(*(_QWORD *)(a1 + 80) + 88LL) = 7;
      memmove_0(v28, L"Global\\", 0xEu);
      v28[7] = 0;
    }
    std::wstring::operator+=((void *)(*(_QWORD *)(a1 + 80) + 72LL), pv);
    v29 = *(_QWORD *)(a1 + 80);
    v30 = (const WCHAR *)(v29 + 72);
    if ( *(_QWORD *)(v29 + 96) > 7u )
      v30 = *(const WCHAR **)v30;
    EventW = CreateEventW(0, 1, 0, v30);
    v32 = *(void **)(v29 + 64);
    if ( v32 )
    {
      v33 = GetLastError();
      if ( !CloseHandle(v32) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v34, v35);
      SetLastError(v33);
    }
    *(_QWORD *)(v29 + 64) = EventW;
    v23 = KSMidiDevice::ConfigureLoopedBuffer((KSMidiDevice *)a1, a2);
    v7 = v23;
    if ( v23 < 0 )
    {
      v18 = 225;
      goto LABEL_50;
    }
    v23 = KSMidiDevice::ConfigureLoopedRegisters((KSMidiDevice *)a1);
    v7 = v23;
    if ( v23 < 0 )
    {
      v18 = 226;
      goto LABEL_50;
    }
    v23 = KSMidiDevice::ConfigureLoopedEvent((KSMidiDevice *)a1);
    v7 = v23;
    if ( v23 < 0 )
    {
      v18 = 227;
      goto LABEL_50;
    }
    if ( pv )
      CoTaskMemFree(pv);
  }
  CloseHandle(Handle);
  return 0;
}

```

## disassembly

```asm
0x180028bc8  mov     [rsp-38h+arg_10], rbx
0x180028bcd  push    rbp
0x180028bce  push    rsi
0x180028bcf  push    rdi
0x180028bd0  push    r12
0x180028bd2  push    r13
0x180028bd4  push    r14
0x180028bd6  push    r15
0x180028bd8  mov     rbp, rsp
0x180028bdb  sub     rsp, 60h
0x180028bdf  mov     rax, cs:__security_cookie
0x180028be6  xor     rax, rsp
0x180028be9  mov     [rbp+var_8], rax
0x180028bed  mov     r15d, r8d
0x180028bf0  mov     r13, rdx
0x180028bf3  mov     rsi, rcx
0x180028bf6  mov     rcx, [rcx+30h]; SRWLock
0x180028bfa  call    ?GetHandle@KsHandleWrapper@@QEAAPEAXXZ; KsHandleWrapper::GetHandle(void)
0x180028bff  mov     rbx, rax
0x180028c02  mov     [rbp+var_20], rax
0x180028c06  inc     rax
0x180028c09  test    rax, 0FFFFFFFFFFFFFFFEh
0x180028c0f  jnz     short loc_180028C49
0x180028c11  mov     rcx, [rbp+38h]; this
0x180028c15  mov     edi, 8007000Eh
0x180028c1a  mov     r9d, edi; char *
0x180028c1d  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x180028c24  mov     edx, 0C1h; void *
0x180028c29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028c2e  nop
0x180028c2f  lea     rcx, [rbx-1]
0x180028c33  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180028c37  ja      short loc_180028C42
0x180028c39  mov     rcx, rbx; hObject
0x180028c3c  call    cs:__imp_CloseHandle
0x180028c42  mov     eax, edi
0x180028c44  jmp     loc_180029001
0x180028c49  mov     [rbp+pv], rbx
0x180028c4d  mov     rax, [rsi+40h]
0x180028c51  mov     qword ptr [rbp+pguid.Data1], rax
0x180028c55  lea     r14, [rsi+4Ch]
0x180028c59  lea     r8, [rsi+48h]
0x180028c5d  lea     rax, [rbp+pv]
0x180028c61  mov     qword ptr [rsp+60h+var_40], rax; int
0x180028c66  mov     r9, r14
0x180028c69  lea     rdx, [rbp+pguid]
0x180028c6d  lea     rcx, [rbp+Block]
0x180028c71  call    ??$make_unique@VKsHandleWrapper@@PEAGAEAIAEAW4_MidiTransport@@PEAX$0A@@std@@YA?AV?$unique_ptr@VKsHandleWrapper@@U?$default_delete@VKsHandleWrapper@@@std@@@0@$$QEAPEAGAEAIAEAW4_MidiTransport@@$$QEAPEAX@Z; std::make_unique<KsHandleWrapper,ushort *,uint &,_MidiTransport &,void *,0>(ushort * &&,uint &,_MidiTransport &,void * &&)
0x180028c76  mov     rcx, [rax]
0x180028c79  xor     r12d, r12d
0x180028c7c  mov     [rax], r12
0x180028c7f  mov     rdi, [rsi+38h]
0x180028c83  mov     [rsi+38h], rcx
0x180028c87  test    rdi, rdi
0x180028c8a  jz      short loc_180028CA1
0x180028c8c  mov     rcx, rdi; this
0x180028c8f  call    ??1KsHandleWrapper@@QEAA@XZ; KsHandleWrapper::~KsHandleWrapper(void)
0x180028c94  mov     edx, 0D8h
0x180028c99  mov     rcx, rdi; Block
0x180028c9c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180028ca1  mov     rdi, [rbp+Block]
0x180028ca5  test    rdi, rdi
0x180028ca8  jz      short loc_180028CBF
0x180028caa  mov     rcx, rdi; this
0x180028cad  call    ??1KsHandleWrapper@@QEAA@XZ; KsHandleWrapper::~KsHandleWrapper(void)
0x180028cb2  mov     edx, 0D8h
0x180028cb7  mov     rcx, rdi; Block
0x180028cba  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180028cbf  mov     rcx, [rsi+38h]; this
0x180028cc3  call    ?Open@KsHandleWrapper@@QEAAJXZ; KsHandleWrapper::Open(void)
0x180028cc8  mov     edi, eax
0x180028cca  test    eax, eax
0x180028ccc  jns     short loc_180028CEB
0x180028cce  mov     rcx, [rbp+38h]; this
0x180028cd2  mov     r9d, eax; char *
0x180028cd5  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x180028cdc  mov     edx, 0C4h; void *
0x180028ce1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028ce6  jmp     loc_180028FDC
0x180028ceb  mov     eax, [r14]
0x180028cee  sub     eax, 2
0x180028cf1  test    eax, 0FFFFFFFDh
0x180028cf6  jnz     loc_180028FF2
0x180028cfc  xorps   xmm0, xmm0
0x180028cff  movups  xmmword ptr [rbp+pguid.Data1], xmm0
0x180028d03  mov     [rbp+pv], r12
0x180028d07  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180028d0e  mov     ecx, 68h ; 'h'; unsigned __int64
0x180028d13  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180028d18  mov     rcx, rax
0x180028d1b  test    rax, rax
0x180028d1e  jz      short loc_180028D5D
0x180028d20  mov     [rax], r12
0x180028d23  mov     [rax+8], r12
0x180028d27  mov     [rax+10h], r12
0x180028d2b  mov     [rax+18h], r12
0x180028d2f  mov     [rax+20h], r12d
0x180028d33  mov     [rax+28h], r12
0x180028d37  mov     [rax+30h], r12
0x180028d3b  mov     [rax+38h], r12
0x180028d3f  mov     [rax+40h], r12
0x180028d43  xorps   xmm0, xmm0
0x180028d46  movups  xmmword ptr [rax+48h], xmm0
0x180028d4a  mov     [rax+58h], r12
0x180028d4e  mov     qword ptr [rax+60h], 7
0x180028d56  mov     [rax+48h], r12w
0x180028d5b  jmp     short loc_180028D60
0x180028d5d  mov     rcx, r12
0x180028d60  mov     rdi, [rsi+50h]
0x180028d64  mov     [rsi+50h], rcx
0x180028d68  test    rdi, rdi
0x180028d6b  jz      short loc_180028D82
0x180028d6d  mov     rcx, rdi; this
0x180028d70  call    ??1MEMORY_MAPPED_PIPE@@QEAA@XZ; MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(void)
0x180028d75  mov     edx, 68h ; 'h'
0x180028d7a  mov     rcx, rdi; Block
0x180028d7d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180028d82  mov     rax, [rsi+50h]
0x180028d86  test    rax, rax
0x180028d89  jnz     short loc_180028D95
0x180028d8b  mov     edx, 0CEh
0x180028d90  jmp     loc_180028E4B
0x180028d95  mov     [rax+4], r15d
0x180028d99  mov     ecx, r12d
0x180028d9c  cmp     dword ptr [r14], 2
0x180028da0  setnz   cl
0x180028da3  inc     ecx
0x180028da5  mov     rax, [rsi+50h]
0x180028da9  mov     [rax], ecx
0x180028dab  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180028db2  mov     r15d, 90h
0x180028db8  mov     ecx, r15d; unsigned __int64
0x180028dbb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180028dc0  mov     rdi, rax
0x180028dc3  mov     [rbp+Block], rax
0x180028dc7  test    rax, rax
0x180028dca  jz      short loc_180028E1D
0x180028dcc  mov     dword ptr [rax], 1
0x180028dd2  lea     rcx, [rax+8]; lpCriticalSection
0x180028dd6  xor     r8d, r8d; Flags
0x180028dd9  xor     edx, edx; dwSpinCount
0x180028ddb  call    cs:__imp_InitializeCriticalSectionEx
0x180028de1  mov     [rdi+30h], r12b
0x180028de5  mov     [rdi+34h], r12d
0x180028de9  mov     [rdi+38h], r12
0x180028ded  mov     [rdi+40h], r12
0x180028df1  mov     [rdi+48h], r12
0x180028df5  mov     [rdi+50h], r12d
0x180028df9  mov     [rdi+58h], r12
0x180028dfd  mov     [rdi+60h], r12
0x180028e01  mov     [rdi+68h], r12
0x180028e05  mov     [rdi+70h], r12
0x180028e09  mov     [rdi+78h], r12
0x180028e0d  mov     [rdi+80h], r12
0x180028e14  mov     [rdi+88h], r12
0x180028e1b  jmp     short loc_180028E20
0x180028e1d  mov     rdi, r12
0x180028e20  mov     r14, [rsi+58h]
0x180028e24  mov     [rsi+58h], rdi
0x180028e28  test    r14, r14
0x180028e2b  jz      short loc_180028E40
0x180028e2d  mov     rcx, r14; this
0x180028e30  call    ??1CMidiXProc@@QEAA@XZ; CMidiXProc::~CMidiXProc(void)
0x180028e35  mov     rdx, r15
0x180028e38  mov     rcx, r14; Block
0x180028e3b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180028e40  cmp     [rsi+58h], r12
0x180028e44  jnz     short loc_180028E58
0x180028e46  mov     edx, 0D3h
0x180028e4b  mov     edi, 8007000Eh
0x180028e50  mov     r9d, edi
0x180028e53  jmp     loc_180028FBB
0x180028e58  lea     rcx, [rbp+pguid]; pguid
0x180028e5c  call    cs:__imp_CoCreateGuid
0x180028e62  mov     edi, eax
0x180028e64  test    eax, eax
0x180028e66  jns     short loc_180028E72
0x180028e68  mov     edx, 0D6h
0x180028e6d  jmp     loc_180028FB8
0x180028e72  mov     r14, [rbp+pv]
0x180028e76  test    r14, r14
0x180028e79  jz      short loc_180028E94
0x180028e7b  call    cs:__imp_GetLastError
0x180028e81  mov     edi, eax
0x180028e83  mov     rcx, r14; pv
0x180028e86  call    cs:__imp_CoTaskMemFree
0x180028e8c  mov     ecx, edi; dwErrCode
0x180028e8e  call    cs:__imp_SetLastError
0x180028e94  mov     [rbp+pv], r12
0x180028e98  lea     rdx, [rbp+pv]; lplpsz
0x180028e9c  lea     rcx, [rbp+pguid]; rclsid
0x180028ea0  call    cs:__imp_StringFromCLSID
0x180028ea6  mov     edi, eax
0x180028ea8  test    eax, eax
0x180028eaa  jns     short loc_180028EB6
0x180028eac  mov     edx, 0D7h
0x180028eb1  jmp     loc_180028FB8
0x180028eb6  mov     rcx, [rsi+50h]
0x180028eba  add     rcx, 38h ; '8'
0x180028ebe  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180028ec3  mov     rcx, [rsi+50h]
0x180028ec7  add     rcx, 48h ; 'H'
0x180028ecb  mov     r14d, 7
0x180028ed1  cmp     [rcx+18h], r14
0x180028ed5  jb      short loc_180028F01
0x180028ed7  jbe     short loc_180028EDE
0x180028ed9  mov     rdi, [rcx]
0x180028edc  jmp     short loc_180028EE1
0x180028ede  mov     rdi, rcx
0x180028ee1  mov     [rcx+10h], r14
0x180028ee5  mov     r8d, 0Eh; Size
0x180028eeb  lea     rdx, aGlobal; "Global\\"
0x180028ef2  mov     rcx, rdi; void *
0x180028ef5  call    memmove_0
0x180028efa  mov     [rdi+0Eh], r12w
0x180028eff  jmp     short loc_180028F10
0x180028f01  lea     r9, aGlobal; "Global\\"
0x180028f08  mov     rdx, r14
0x180028f0b  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x180028f10  mov     rcx, [rsi+50h]
0x180028f14  add     rcx, 48h ; 'H'; Src
0x180028f18  mov     rdx, [rbp+pv]; void *
0x180028f1c  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x180028f21  mov     rdi, [rsi+50h]
0x180028f25  lea     r9, [rdi+48h]
0x180028f29  cmp     [r9+18h], r14
0x180028f2d  jbe     short loc_180028F32
0x180028f2f  mov     r9, [r9]; lpName
0x180028f32  xor     r8d, r8d; bInitialState
0x180028f35  lea     edx, [r8+1]; bManualReset
0x180028f39  xor     ecx, ecx; lpEventAttributes
0x180028f3b  call    cs:__imp_CreateEventW
0x180028f41  mov     r12, rax
0x180028f44  mov     r14, [rdi+40h]
0x180028f48  test    r14, r14
0x180028f4b  jz      short loc_180028F74
0x180028f4d  call    cs:__imp_GetLastError
0x180028f53  mov     r15d, eax
0x180028f56  mov     rcx, r14; hObject
0x180028f59  call    cs:__imp_CloseHandle
0x180028f5f  mov     rcx, [rbp+38h]; this
0x180028f63  test    eax, eax
0x180028f65  jz      loc_180029025
0x180028f6b  mov     ecx, r15d; dwErrCode
0x180028f6e  call    cs:__imp_SetLastError
0x180028f74  mov     [rdi+40h], r12
0x180028f78  mov     rdx, r13; unsigned int *
0x180028f7b  mov     rcx, rsi; this
0x180028f7e  call    ?ConfigureLoopedBuffer@KSMidiDevice@@IEAAJAEAK@Z; KSMidiDevice::ConfigureLoopedBuffer(ulong &)
0x180028f83  mov     edi, eax
0x180028f85  test    eax, eax
0x180028f87  jns     short loc_180028F90
0x180028f89  mov     edx, 0E1h
0x180028f8e  jmp     short loc_180028FB8
0x180028f90  mov     rcx, rsi; this
0x180028f93  call    ?ConfigureLoopedRegisters@KSMidiDevice@@IEAAJXZ; KSMidiDevice::ConfigureLoopedRegisters(void)
0x180028f98  mov     edi, eax
0x180028f9a  test    eax, eax
0x180028f9c  jns     short loc_180028FA5
0x180028f9e  mov     edx, 0E2h
0x180028fa3  jmp     short loc_180028FB8
0x180028fa5  mov     rcx, rsi; this
0x180028fa8  call    ?ConfigureLoopedEvent@KSMidiDevice@@IEAAJXZ; KSMidiDevice::ConfigureLoopedEvent(void)
0x180028fad  mov     edi, eax
0x180028faf  test    eax, eax
0x180028fb1  jns     short loc_180028FE1
0x180028fb3  mov     edx, 0E3h; void *
0x180028fb8  mov     r9d, eax; char *
0x180028fbb  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x180028fc2  mov     rcx, [rbp+38h]; this
0x180028fc6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028fcb  nop
0x180028fcc  mov     rcx, [rbp+pv]; pv
0x180028fd0  test    rcx, rcx
0x180028fd3  jz      short loc_180028FDC
0x180028fd5  call    cs:__imp_CoTaskMemFree
0x180028fdb  nop
0x180028fdc  jmp     loc_180028C39
0x180028fe1  mov     rcx, [rbp+pv]; pv
0x180028fe5  test    rcx, rcx
0x180028fe8  jz      short loc_180028FF6
0x180028fea  call    cs:__imp_CoTaskMemFree
0x180028ff0  jmp     short loc_180028FF6
0x180028ff2  mov     [r13+0], r12d
0x180028ff6  mov     rcx, rbx; hObject
0x180028ff9  call    cs:__imp_CloseHandle
0x180028fff  xor     eax, eax
0x180029001  mov     rcx, [rbp+var_8]
0x180029005  xor     rcx, rsp; StackCookie
0x180029008  call    __security_check_cookie
0x18002900d  mov     rbx, [rsp+60h+arg_10]
0x180029015  add     rsp, 60h
0x180029019  pop     r15
0x18002901b  pop     r14
0x18002901d  pop     r13
0x18002901f  pop     r12
0x180029021  pop     rdi
0x180029022  pop     rsi
0x180029023  pop     rbp
0x180029024  retn
  ... truncated ...
```
