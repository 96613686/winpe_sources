# KSMidiDevice::OpenStream(ulong &,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004)

- ea: `0x180049708`
- end: `0x180049b70`
- name: `?OpenStream@KSMidiDevice@@IEAAJAEAKW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@@Z`
- size: `1128`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180048e60`

## callees

- `0x180005020`
- `0x180005044`
- `0x180005800`
- `0x180005e90`
- `0x18000b394`
- `0x18000c684`
- `0x180013540`
- `0x180015144`
- `0x180042480`
- `0x180043a74`
- `0x1800467b0`
- `0x180047210`
- `0x180047294`
- `0x180048474`
- `0x180048708`
- `0x180048940`
- `0x180048a64`
- `0x180049708`
- `0x180057c3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18004991b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18004991b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180049a7b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180049a7b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800499ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180049aae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800499ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180049aae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800499bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049a8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800499bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049a8d`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800499e0`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800499e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800499c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049b15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049b2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800499c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049b15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049b2a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18004999c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18004999c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004977c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049a99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049b39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004977c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049a99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049b39`

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
0x180049708  mov     [rsp-38h+arg_10], rbx
0x18004970d  push    rbp
0x18004970e  push    rsi
0x18004970f  push    rdi
0x180049710  push    r12
0x180049712  push    r13
0x180049714  push    r14
0x180049716  push    r15
0x180049718  mov     rbp, rsp
0x18004971b  sub     rsp, 60h
0x18004971f  mov     rax, cs:__security_cookie
0x180049726  xor     rax, rsp
0x180049729  mov     [rbp+var_8], rax
0x18004972d  mov     r15d, r8d
0x180049730  mov     r13, rdx
0x180049733  mov     rsi, rcx
0x180049736  mov     rcx, [rcx+30h]; SRWLock
0x18004973a  call    ?GetHandle@KsHandleWrapper@@QEAAPEAXXZ; KsHandleWrapper::GetHandle(void)
0x18004973f  mov     rbx, rax
0x180049742  mov     [rbp+var_20], rax
0x180049746  inc     rax
0x180049749  test    rax, 0FFFFFFFFFFFFFFFEh
0x18004974f  jnz     short loc_180049789
0x180049751  mov     rcx, [rbp+38h]; this
0x180049755  mov     edi, 8007000Eh
0x18004975a  mov     r9d, edi; char *
0x18004975d  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x180049764  mov     edx, 0C1h; void *
0x180049769  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004976e  nop
0x18004976f  lea     rcx, [rbx-1]
0x180049773  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180049777  ja      short loc_180049782
0x180049779  mov     rcx, rbx; hObject
0x18004977c  call    cs:__imp_CloseHandle
0x180049782  mov     eax, edi
0x180049784  jmp     loc_180049B41
0x180049789  mov     [rbp+pv], rbx
0x18004978d  mov     rax, [rsi+40h]
0x180049791  mov     qword ptr [rbp+pguid.Data1], rax
0x180049795  lea     r14, [rsi+4Ch]
0x180049799  lea     r8, [rsi+48h]
0x18004979d  lea     rax, [rbp+pv]
0x1800497a1  mov     qword ptr [rsp+60h+var_40], rax; int
0x1800497a6  mov     r9, r14
0x1800497a9  lea     rdx, [rbp+pguid]
0x1800497ad  lea     rcx, [rbp+Block]
0x1800497b1  call    ??$make_unique@VKsHandleWrapper@@PEAGAEAIAEAW4_MidiTransport@@PEAX$0A@@std@@YA?AV?$unique_ptr@VKsHandleWrapper@@U?$default_delete@VKsHandleWrapper@@@std@@@0@$$QEAPEAGAEAIAEAW4_MidiTransport@@$$QEAPEAX@Z; std::make_unique<KsHandleWrapper,ushort *,uint &,_MidiTransport &,void *,0>(ushort * &&,uint &,_MidiTransport &,void * &&)
0x1800497b6  mov     rcx, [rax]
0x1800497b9  xor     r12d, r12d
0x1800497bc  mov     [rax], r12
0x1800497bf  mov     rdi, [rsi+38h]
0x1800497c3  mov     [rsi+38h], rcx
0x1800497c7  test    rdi, rdi
0x1800497ca  jz      short loc_1800497E1
0x1800497cc  mov     rcx, rdi; this
0x1800497cf  call    ??1KsHandleWrapper@@QEAA@XZ; KsHandleWrapper::~KsHandleWrapper(void)
0x1800497d4  mov     edx, 0D8h
0x1800497d9  mov     rcx, rdi; Block
0x1800497dc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800497e1  mov     rdi, [rbp+Block]
0x1800497e5  test    rdi, rdi
0x1800497e8  jz      short loc_1800497FF
0x1800497ea  mov     rcx, rdi; this
0x1800497ed  call    ??1KsHandleWrapper@@QEAA@XZ; KsHandleWrapper::~KsHandleWrapper(void)
0x1800497f2  mov     edx, 0D8h
0x1800497f7  mov     rcx, rdi; Block
0x1800497fa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800497ff  mov     rcx, [rsi+38h]; this
0x180049803  call    ?Open@KsHandleWrapper@@QEAAJXZ; KsHandleWrapper::Open(void)
0x180049808  mov     edi, eax
0x18004980a  test    eax, eax
0x18004980c  jns     short loc_18004982B
0x18004980e  mov     rcx, [rbp+38h]; this
0x180049812  mov     r9d, eax; char *
0x180049815  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x18004981c  mov     edx, 0C4h; void *
0x180049821  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049826  jmp     loc_180049B1C
0x18004982b  mov     eax, [r14]
0x18004982e  sub     eax, 2
0x180049831  test    eax, 0FFFFFFFDh
0x180049836  jnz     loc_180049B32
0x18004983c  xorps   xmm0, xmm0
0x18004983f  movups  xmmword ptr [rbp+pguid.Data1], xmm0
0x180049843  mov     [rbp+pv], r12
0x180049847  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004984e  mov     ecx, 68h ; 'h'; unsigned __int64
0x180049853  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180049858  mov     rcx, rax
0x18004985b  test    rax, rax
0x18004985e  jz      short loc_18004989D
0x180049860  mov     [rax], r12
0x180049863  mov     [rax+8], r12
0x180049867  mov     [rax+10h], r12
0x18004986b  mov     [rax+18h], r12
0x18004986f  mov     [rax+20h], r12d
0x180049873  mov     [rax+28h], r12
0x180049877  mov     [rax+30h], r12
0x18004987b  mov     [rax+38h], r12
0x18004987f  mov     [rax+40h], r12
0x180049883  xorps   xmm0, xmm0
0x180049886  movups  xmmword ptr [rax+48h], xmm0
0x18004988a  mov     [rax+58h], r12
0x18004988e  mov     qword ptr [rax+60h], 7
0x180049896  mov     [rax+48h], r12w
0x18004989b  jmp     short loc_1800498A0
0x18004989d  mov     rcx, r12
0x1800498a0  mov     rdi, [rsi+50h]
0x1800498a4  mov     [rsi+50h], rcx
0x1800498a8  test    rdi, rdi
0x1800498ab  jz      short loc_1800498C2
0x1800498ad  mov     rcx, rdi; this
0x1800498b0  call    ??1MEMORY_MAPPED_PIPE@@QEAA@XZ; MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(void)
0x1800498b5  mov     edx, 68h ; 'h'
0x1800498ba  mov     rcx, rdi; Block
0x1800498bd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800498c2  mov     rax, [rsi+50h]
0x1800498c6  test    rax, rax
0x1800498c9  jnz     short loc_1800498D5
0x1800498cb  mov     edx, 0CEh
0x1800498d0  jmp     loc_18004998B
0x1800498d5  mov     [rax+4], r15d
0x1800498d9  mov     ecx, r12d
0x1800498dc  cmp     dword ptr [r14], 2
0x1800498e0  setnz   cl
0x1800498e3  inc     ecx
0x1800498e5  mov     rax, [rsi+50h]
0x1800498e9  mov     [rax], ecx
0x1800498eb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800498f2  mov     r15d, 90h
0x1800498f8  mov     ecx, r15d; unsigned __int64
0x1800498fb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180049900  mov     rdi, rax
0x180049903  mov     [rbp+Block], rax
0x180049907  test    rax, rax
0x18004990a  jz      short loc_18004995D
0x18004990c  mov     dword ptr [rax], 1
0x180049912  lea     rcx, [rax+8]; lpCriticalSection
0x180049916  xor     r8d, r8d; Flags
0x180049919  xor     edx, edx; dwSpinCount
0x18004991b  call    cs:__imp_InitializeCriticalSectionEx
0x180049921  mov     [rdi+30h], r12b
0x180049925  mov     [rdi+34h], r12d
0x180049929  mov     [rdi+38h], r12
0x18004992d  mov     [rdi+40h], r12
0x180049931  mov     [rdi+48h], r12
0x180049935  mov     [rdi+50h], r12d
0x180049939  mov     [rdi+58h], r12
0x18004993d  mov     [rdi+60h], r12
0x180049941  mov     [rdi+68h], r12
0x180049945  mov     [rdi+70h], r12
0x180049949  mov     [rdi+78h], r12
0x18004994d  mov     [rdi+80h], r12
0x180049954  mov     [rdi+88h], r12
0x18004995b  jmp     short loc_180049960
0x18004995d  mov     rdi, r12
0x180049960  mov     r14, [rsi+58h]
0x180049964  mov     [rsi+58h], rdi
0x180049968  test    r14, r14
0x18004996b  jz      short loc_180049980
0x18004996d  mov     rcx, r14; this
0x180049970  call    ??1CMidiXProc@@QEAA@XZ; CMidiXProc::~CMidiXProc(void)
0x180049975  mov     rdx, r15
0x180049978  mov     rcx, r14; Block
0x18004997b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180049980  cmp     [rsi+58h], r12
0x180049984  jnz     short loc_180049998
0x180049986  mov     edx, 0D3h
0x18004998b  mov     edi, 8007000Eh
0x180049990  mov     r9d, edi
0x180049993  jmp     loc_180049AFB
0x180049998  lea     rcx, [rbp+pguid]; pguid
0x18004999c  call    cs:__imp_CoCreateGuid
0x1800499a2  mov     edi, eax
0x1800499a4  test    eax, eax
0x1800499a6  jns     short loc_1800499B2
0x1800499a8  mov     edx, 0D6h
0x1800499ad  jmp     loc_180049AF8
0x1800499b2  mov     r14, [rbp+pv]
0x1800499b6  test    r14, r14
0x1800499b9  jz      short loc_1800499D4
0x1800499bb  call    cs:__imp_GetLastError
0x1800499c1  mov     edi, eax
0x1800499c3  mov     rcx, r14; pv
0x1800499c6  call    cs:__imp_CoTaskMemFree
0x1800499cc  mov     ecx, edi; dwErrCode
0x1800499ce  call    cs:__imp_SetLastError
0x1800499d4  mov     [rbp+pv], r12
0x1800499d8  lea     rdx, [rbp+pv]; lplpsz
0x1800499dc  lea     rcx, [rbp+pguid]; rclsid
0x1800499e0  call    cs:__imp_StringFromCLSID
0x1800499e6  mov     edi, eax
0x1800499e8  test    eax, eax
0x1800499ea  jns     short loc_1800499F6
0x1800499ec  mov     edx, 0D7h
0x1800499f1  jmp     loc_180049AF8
0x1800499f6  mov     rcx, [rsi+50h]
0x1800499fa  add     rcx, 38h ; '8'
0x1800499fe  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180049a03  mov     rcx, [rsi+50h]
0x180049a07  add     rcx, 48h ; 'H'
0x180049a0b  mov     r14d, 7
0x180049a11  cmp     [rcx+18h], r14
0x180049a15  jb      short loc_180049A41
0x180049a17  jbe     short loc_180049A1E
0x180049a19  mov     rdi, [rcx]
0x180049a1c  jmp     short loc_180049A21
0x180049a1e  mov     rdi, rcx
0x180049a21  mov     [rcx+10h], r14
0x180049a25  mov     r8d, 0Eh; Size
0x180049a2b  lea     rdx, aGlobal; "Global\\"
0x180049a32  mov     rcx, rdi; void *
0x180049a35  call    memmove_0
0x180049a3a  mov     [rdi+0Eh], r12w
0x180049a3f  jmp     short loc_180049A50
0x180049a41  lea     r9, aGlobal; "Global\\"
0x180049a48  mov     rdx, r14
0x180049a4b  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x180049a50  mov     rcx, [rsi+50h]
0x180049a54  add     rcx, 48h ; 'H'; Src
0x180049a58  mov     rdx, [rbp+pv]; void *
0x180049a5c  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x180049a61  mov     rdi, [rsi+50h]
0x180049a65  lea     r9, [rdi+48h]
0x180049a69  cmp     [r9+18h], r14
0x180049a6d  jbe     short loc_180049A72
0x180049a6f  mov     r9, [r9]; lpName
0x180049a72  xor     r8d, r8d; bInitialState
0x180049a75  lea     edx, [r8+1]; bManualReset
0x180049a79  xor     ecx, ecx; lpEventAttributes
0x180049a7b  call    cs:__imp_CreateEventW
0x180049a81  mov     r12, rax
0x180049a84  mov     r14, [rdi+40h]
0x180049a88  test    r14, r14
0x180049a8b  jz      short loc_180049AB4
0x180049a8d  call    cs:__imp_GetLastError
0x180049a93  mov     r15d, eax
0x180049a96  mov     rcx, r14; hObject
0x180049a99  call    cs:__imp_CloseHandle
0x180049a9f  mov     rcx, [rbp+38h]; this
0x180049aa3  test    eax, eax
0x180049aa5  jz      loc_180049B65
0x180049aab  mov     ecx, r15d; dwErrCode
0x180049aae  call    cs:__imp_SetLastError
0x180049ab4  mov     [rdi+40h], r12
0x180049ab8  mov     rdx, r13; unsigned int *
0x180049abb  mov     rcx, rsi; this
0x180049abe  call    ?ConfigureLoopedBuffer@KSMidiDevice@@IEAAJAEAK@Z; KSMidiDevice::ConfigureLoopedBuffer(ulong &)
0x180049ac3  mov     edi, eax
0x180049ac5  test    eax, eax
0x180049ac7  jns     short loc_180049AD0
0x180049ac9  mov     edx, 0E1h
0x180049ace  jmp     short loc_180049AF8
0x180049ad0  mov     rcx, rsi; this
0x180049ad3  call    ?ConfigureLoopedRegisters@KSMidiDevice@@IEAAJXZ; KSMidiDevice::ConfigureLoopedRegisters(void)
0x180049ad8  mov     edi, eax
0x180049ada  test    eax, eax
0x180049adc  jns     short loc_180049AE5
0x180049ade  mov     edx, 0E2h
0x180049ae3  jmp     short loc_180049AF8
0x180049ae5  mov     rcx, rsi; this
0x180049ae8  call    ?ConfigureLoopedEvent@KSMidiDevice@@IEAAJXZ; KSMidiDevice::ConfigureLoopedEvent(void)
0x180049aed  mov     edi, eax
0x180049aef  test    eax, eax
0x180049af1  jns     short loc_180049B21
0x180049af3  mov     edx, 0E3h; void *
0x180049af8  mov     r9d, eax; char *
0x180049afb  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x180049b02  mov     rcx, [rbp+38h]; this
0x180049b06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049b0b  nop
0x180049b0c  mov     rcx, [rbp+pv]; pv
0x180049b10  test    rcx, rcx
0x180049b13  jz      short loc_180049B1C
0x180049b15  call    cs:__imp_CoTaskMemFree
0x180049b1b  nop
0x180049b1c  jmp     loc_180049779
0x180049b21  mov     rcx, [rbp+pv]; pv
0x180049b25  test    rcx, rcx
0x180049b28  jz      short loc_180049B36
0x180049b2a  call    cs:__imp_CoTaskMemFree
0x180049b30  jmp     short loc_180049B36
0x180049b32  mov     [r13+0], r12d
0x180049b36  mov     rcx, rbx; hObject
0x180049b39  call    cs:__imp_CloseHandle
0x180049b3f  xor     eax, eax
0x180049b41  mov     rcx, [rbp+var_8]
0x180049b45  xor     rcx, rsp; StackCookie
0x180049b48  call    __security_check_cookie
0x180049b4d  mov     rbx, [rsp+60h+arg_10]
0x180049b55  add     rsp, 60h
0x180049b59  pop     r15
0x180049b5b  pop     r14
0x180049b5d  pop     r13
0x180049b5f  pop     r12
0x180049b61  pop     rdi
0x180049b62  pop     rsi
0x180049b63  pop     rbp
0x180049b64  retn
  ... truncated ...
```
