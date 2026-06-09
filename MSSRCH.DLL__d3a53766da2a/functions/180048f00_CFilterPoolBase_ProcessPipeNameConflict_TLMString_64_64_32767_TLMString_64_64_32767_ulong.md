# CFilterPoolBase::ProcessPipeNameConflict(TLMString<64,64,32767> &,TLMString<64,64,32767> &,ulong)

- ea: `0x180048f00`
- end: `0x1800492eb`
- name: `?ProcessPipeNameConflict@CFilterPoolBase@@IEAAJAEAV?$TLMString@$0EA@$0EA@$0HPPP@@@0K@Z`
- size: `1003`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004a638`

## callees

- `0x18000c620`
- `0x180022688`
- `0x1800252e4`
- `0x1800269b0`
- `0x180026b58`
- `0x180029db0`
- `0x180048f00`
- `0x180056610`
- `0x18005e788`
- `0x18006028c`
- `0x1800800f4`
- `0x180103788`
- `0x1801244c0`
- `0x18019e43c`
- `0x180241010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x180049023`
- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x1800490bb`
- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x1800490f4`
- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x180049023`
- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x1800490bb`
- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x1800490f4`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800491d1`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800491d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004907c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004907c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004916e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004916e`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180049057`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180049057`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFilterPoolBase::ProcessPipeNameConflict(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  int v7; // r14d
  int v8; // esi
  HANDLE v9; // rax
  void *v10; // rbx
  DWORD ProcId; // edi
  __int64 v12; // rcx
  unsigned int i; // ebx
  HANDLE v14; // rax
  __int64 v15; // rcx
  HANDLE v16; // rbx
  __int64 v17; // rcx
  HANDLE hProcess[2]; // [rsp+30h] [rbp-D0h] BYREF
  void **v20; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpName; // [rsp+48h] [rbp-B8h]
  int v22; // [rsp+50h] [rbp-B0h]
  unsigned int v23; // [rsp+54h] [rbp-ACh]
  char v24; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t v25[20]; // [rsp+E0h] [rbp-20h] BYREF
  HANDLE v26; // [rsp+108h] [rbp+8h]
  void **v27; // [rsp+110h] [rbp+10h] BYREF
  wchar_t *v28; // [rsp+118h] [rbp+18h]
  int v29; // [rsp+120h] [rbp+20h]
  char v30; // [rsp+128h] [rbp+28h] BYREF
  _QWORD v31[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  int v32; // [rsp+1C0h] [rbp+C0h]
  char v33; // [rsp+1C8h] [rbp+C8h] BYREF
  wchar_t Buffer[32]; // [rsp+250h] [rbp+150h] BYREF

  v31[0] = &CLMString::`vftable';
  v31[1] = &v33;
  v32 = 65;
  CLMString::AssignInConstructor((CLMString *)v31, *(const wchar_t **)(a2 + 8), 0xFFFFFFFF);
  v31[0] = &CCICommonPathString::`vftable';
  v27 = &CLMString::`vftable';
  v28 = (wchar_t *)&v30;
  v29 = 65;
  CLMString::AssignInConstructor((CLMString *)&v27, *(const wchar_t **)(a3 + 8), 0xFFFFFFFF);
  v27 = (void **)&CCICommonPathString::`vftable';
  if ( ++CFilterPoolBase::m_dwProcessNumber == 1024 )
    CFilterPoolBase::m_dwProcessNumber = 1;
  v7 = 0;
  v8 = 0;
  while ( 1 )
  {
    v20 = &CLMString::`vftable';
    lpName = (LPCWSTR)&v24;
    v22 = 65;
    CLMString::AssignInConstructor((CLMString *)&v20, v28, 0xFFFFFFFF);
    v20 = (void **)&CCICommonPathString::`vftable';
    _itow(CFilterPoolBase::m_dwProcessNumber, Buffer, 10);
    ((void (__fastcall *)(void ***, wchar_t *, _QWORD, __int64))v20[4])(&v20, Buffer, v23, 0xFFFFFFFFLL);
    v9 = OpenFileMappingW(0xF001Fu, 0, lpName);
    v10 = v9;
    if ( !v9 || v9 == (HANDLE)-1LL )
      break;
    ProcId = CFilterPoolBase::ExtractProcId(v9);
    LODWORD(hProcess[0]) = ProcId;
    CloseHandle(v10);
LABEL_12:
    if ( v7 )
    {
      ProcId = 0;
      v7 = 0;
    }
    if ( ProcId )
    {
      if ( (byte_1802DA181 & 8) != 0 )
        McTemplateU0qz_EventWriteTransfer(
          v12,
          MSSearchTraceId_ProtocolHostNameConflict_Killing,
          ProcId,
          *(_QWORD *)(a1 + 696));
      hProcess[0] = 0;
      v14 = OpenProcess(0x401u, 0, ProcId);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        hProcess,
        v14);
      v16 = hProcess[0];
      if ( (unsigned __int64)hProcess[0] - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      {
        if ( byte_1802DA181 < 0 )
          McTemplateU0qz_EventWriteTransfer(
            v15,
            MSSearchTraceId_ProtocolHostNameConflict_FailedToKill,
            0,
            *(_QWORD *)(a1 + 696));
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hProcess);
        goto LABEL_24;
      }
      v26 = hProcess[0];
      StringCbPrintfW(v25, 0x26u, L"%p", hProcess[0]);
      SearchIndexerTrace::Information(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssrch\\\\gather\\\\gthrsvc\\\\fltrpool.cxx\"",
        (const wchar_t *)0x73D,
        (unsigned int)L"[SrchGatherSvc] TerminateProcess( %ws )\n",
        v25);
      TerminateProcess(v16, 0);
      v7 = 1;
      if ( (byte_1802DA181 & 8) != 0 )
        McTemplateU0qz_EventWriteTransfer(
          v17,
          MSSearchTraceId_ProtocolHostNameConflict_Killed,
          ProcId,
          *(_QWORD *)(a1 + 696));
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hProcess);
      TLMString<64,64,32767>::~TLMString<64,64,32767>(&v20);
    }
    else
    {
LABEL_24:
      if ( ++CFilterPoolBase::m_dwProcessNumber == 1024 )
        CFilterPoolBase::m_dwProcessNumber = 1;
      if ( ++v8 == 1024 )
      {
        TLMString<64,64,32767>::~TLMString<64,64,32767>(&v20);
        TLMString<64,64,32767>::~TLMString<64,64,32767>(&v27);
        TLMString<64,64,32767>::~TLMString<64,64,32767>(v31);
        return 2147500037LL;
      }
      TLMString<64,64,32767>::~TLMString<64,64,32767>(&v20);
    }
  }
  LODWORD(hProcess[0]) = 0;
  for ( i = 1; i <= a4; ++i )
  {
    TLMString<192,64,32767>::operator=(&v20, v31);
    _itow(CFilterPoolBase::m_dwProcessNumber, Buffer, 10);
    CLMString::Append((CLMString *)&v20, Buffer, 0xFFFFFFFF);
    CLMString::operator+=(&v20, 95);
    _itow(i, Buffer, 10);
    CLMString::Append((CLMString *)&v20, Buffer, 0xFFFFFFFF);
    if ( (unsigned __int8)CFilterPoolBase::IsPipeNameConflict(&v20, hProcess) )
    {
      ProcId = (DWORD)hProcess[0];
      goto LABEL_12;
    }
  }
  TLMString<64,64,32767>::~TLMString<64,64,32767>(&v20);
  TLMString<64,64,32767>::~TLMString<64,64,32767>(&v27);
  TLMString<64,64,32767>::~TLMString<64,64,32767>(v31);
  return 0;
}

```

## disassembly

```asm
0x180048f00  mov     [rsp-8+arg_18], rbx
0x180048f05  push    rbp
0x180048f06  push    rsi
0x180048f07  push    rdi
0x180048f08  push    r12
0x180048f0a  push    r13
0x180048f0c  push    r14
0x180048f0e  push    r15
0x180048f10  lea     rbp, [rsp-1A0h]
0x180048f18  sub     rsp, 2A0h
0x180048f1f  mov     rax, cs:__security_cookie
0x180048f26  xor     rax, rsp
0x180048f29  mov     [rbp+1D0h+var_40], rax
0x180048f30  mov     r12d, r9d
0x180048f33  mov     rbx, r8
0x180048f36  mov     r15, rcx
0x180048f39  lea     rsi, ??_7CLMString@@6B@; const CLMString::`vftable'
0x180048f40  mov     [rbp+1D0h+var_120], rsi
0x180048f47  lea     rax, [rbp+1D0h+var_108]
0x180048f4e  mov     [rbp+1D0h+var_118], rax
0x180048f55  mov     r14d, 41h ; 'A'
0x180048f5b  mov     [rbp+1D0h+var_110], r14d
0x180048f62  or      edi, 0FFFFFFFFh
0x180048f65  mov     r8d, edi; unsigned int
0x180048f68  mov     rdx, [rdx+8]; wchar_t *
0x180048f6c  lea     rcx, [rbp+1D0h+var_120]; this
0x180048f73  call    ?AssignInConstructor@CLMString@@IEAAHPEB_WI@Z; CLMString::AssignInConstructor(wchar_t const *,uint)
0x180048f78  lea     r13, ??_7CCICommonPathString@@6B@; const CCICommonPathString::`vftable'
0x180048f7f  mov     [rbp+1D0h+var_120], r13
0x180048f86  mov     [rbp+1D0h+var_1C0], rsi
0x180048f8a  lea     rax, [rbp+1D0h+var_1A8]
0x180048f8e  mov     [rbp+1D0h+var_1B8], rax
0x180048f92  mov     [rbp+1D0h+var_1B0], r14d
0x180048f96  mov     r8d, edi; unsigned int
0x180048f99  mov     rdx, [rbx+8]; wchar_t *
0x180048f9d  lea     rcx, [rbp+1D0h+var_1C0]; this
0x180048fa1  call    ?AssignInConstructor@CLMString@@IEAAHPEB_WI@Z; CLMString::AssignInConstructor(wchar_t const *,uint)
0x180048fa6  mov     [rbp+1D0h+var_1C0], r13
0x180048faa  mov     eax, cs:?m_dwProcessNumber@CFilterPoolBase@@1KA; ulong CFilterPoolBase::m_dwProcessNumber
0x180048fb0  lea     edi, [r14-40h]
0x180048fb4  add     eax, edi
0x180048fb6  mov     cs:?m_dwProcessNumber@CFilterPoolBase@@1KA, eax; ulong CFilterPoolBase::m_dwProcessNumber
0x180048fbc  cmp     eax, 400h
0x180048fc1  jnz     short loc_180048FC9
0x180048fc3  mov     cs:?m_dwProcessNumber@CFilterPoolBase@@1KA, edi; ulong CFilterPoolBase::m_dwProcessNumber
0x180048fc9  xor     r13d, r13d
0x180048fcc  mov     r14d, r13d
0x180048fcf  mov     esi, r13d
0x180048fd2  lea     rax, ??_7CLMString@@6B@; const CLMString::`vftable'
0x180048fd9  mov     [rsp+2D0h+var_290], rax
0x180048fde  lea     rax, [rsp+2D0h+var_278]
0x180048fe3  mov     [rsp+2D0h+lpName], rax
0x180048fe8  mov     [rsp+2D0h+var_280], 41h ; 'A'
0x180048ff0  or      ebx, 0FFFFFFFFh
0x180048ff3  mov     r8d, ebx; unsigned int
0x180048ff6  mov     rdx, [rbp+1D0h+var_1B8]; wchar_t *
0x180048ffa  lea     rcx, [rsp+2D0h+var_290]; this
0x180048fff  call    ?AssignInConstructor@CLMString@@IEAAHPEB_WI@Z; CLMString::AssignInConstructor(wchar_t const *,uint)
0x180049004  lea     rax, ??_7CCICommonPathString@@6B@; const CCICommonPathString::`vftable'
0x18004900b  mov     [rsp+2D0h+var_290], rax
0x180049010  mov     r8d, 0Ah; Radix
0x180049016  lea     rdx, [rbp+1D0h+Buffer]; Buffer
0x18004901d  mov     ecx, cs:?m_dwProcessNumber@CFilterPoolBase@@1KA; Value
0x180049023  call    cs:__imp__itow
0x180049029  mov     rax, [rsp+2D0h+var_290]
0x18004902e  mov     r9d, ebx
0x180049031  mov     r8d, [rsp+2D0h+var_27C]
0x180049036  lea     rdx, [rbp+1D0h+Buffer]
0x18004903d  lea     rcx, [rsp+2D0h+var_290]
0x180049042  mov     rax, [rax+20h]
0x180049046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004904b  mov     r8, [rsp+2D0h+lpName]; lpName
0x180049050  xor     edx, edx; bInheritHandle
0x180049052  mov     ecx, 0F001Fh; dwDesiredAccess
0x180049057  call    cs:__imp_OpenFileMappingW
0x18004905d  mov     rbx, rax
0x180049060  test    rax, rax
0x180049063  jz      short loc_180049087
0x180049065  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180049069  jz      short loc_180049087
0x18004906b  mov     rcx, rax; void *
0x18004906e  call    ?ExtractProcId@CFilterPoolBase@@KAKPEAX@Z; CFilterPoolBase::ExtractProcId(void *)
0x180049073  mov     edi, eax
0x180049075  mov     dword ptr [rsp+2D0h+hProcess], eax
0x180049079  mov     rcx, rbx; hObject
0x18004907c  call    cs:__imp_CloseHandle
0x180049082  jmp     loc_18004912D
0x180049087  mov     dword ptr [rsp+2D0h+hProcess], r13d
0x18004908c  mov     ebx, edi
0x18004908e  cmp     ebx, r12d
0x180049091  ja      loc_18004929E
0x180049097  lea     rdx, [rbp+1D0h+var_120]
0x18004909e  lea     rcx, [rsp+2D0h+var_290]
0x1800490a3  call    ??4?$TLMString@$0MA@$0EA@$0HPPP@@@QEAAXAEBV0@@Z; TLMString<192,64,32767>::operator=(TLMString<192,64,32767> const &)
0x1800490a8  mov     r8d, 0Ah; Radix
0x1800490ae  lea     rdx, [rbp+1D0h+Buffer]; Buffer
0x1800490b5  mov     ecx, cs:?m_dwProcessNumber@CFilterPoolBase@@1KA; Value
0x1800490bb  call    cs:__imp__itow
0x1800490c1  or      r8d, 0FFFFFFFFh; unsigned int
0x1800490c5  lea     rdx, [rbp+1D0h+Buffer]; wchar_t *
0x1800490cc  lea     rcx, [rsp+2D0h+var_290]; this
0x1800490d1  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x1800490d6  mov     edx, 5Fh ; '_'
0x1800490db  lea     rcx, [rsp+2D0h+var_290]
0x1800490e0  call    ??YCLMString@@QEAAX_W@Z; CLMString::operator+=(wchar_t)
0x1800490e5  mov     r8d, 0Ah; Radix
0x1800490eb  lea     rdx, [rbp+1D0h+Buffer]; Buffer
0x1800490f2  mov     ecx, ebx; Value
0x1800490f4  call    cs:__imp__itow
0x1800490fa  or      r8d, 0FFFFFFFFh; unsigned int
0x1800490fe  lea     rdx, [rbp+1D0h+Buffer]; wchar_t *
0x180049105  lea     rcx, [rsp+2D0h+var_290]; this
0x18004910a  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x18004910f  lea     rdx, [rsp+2D0h+hProcess]
0x180049114  lea     rcx, [rsp+2D0h+var_290]
0x180049119  call    ?IsPipeNameConflict@CFilterPoolBase@@KA_NAEAV?$TLMString@$0EA@$0EA@$0HPPP@@@PEAK@Z; CFilterPoolBase::IsPipeNameConflict(TLMString<64,64,32767> &,ulong *)
0x18004911e  test    al, al
0x180049120  jnz     short loc_180049129
0x180049122  add     ebx, edi
0x180049124  jmp     loc_18004908E
0x180049129  mov     edi, dword ptr [rsp+2D0h+hProcess]
0x18004912d  test    r14d, r14d
0x180049130  jz      short loc_180049138
0x180049132  mov     edi, r13d
0x180049135  mov     r14d, r13d
0x180049138  test    edi, edi
0x18004913a  jz      loc_180049244
0x180049140  test    cs:byte_1802DA181, 8
0x180049147  jz      short loc_18004915F
0x180049149  mov     r9, [r15+2B8h]
0x180049150  mov     r8d, edi
0x180049153  lea     rdx, MSSearchTraceId_ProtocolHostNameConflict_Killing
0x18004915a  call    McTemplateU0qz_EventWriteTransfer
0x18004915f  mov     [rsp+2D0h+hProcess], r13
0x180049164  mov     r8d, edi; dwProcessId
0x180049167  xor     edx, edx; bInheritHandle
0x180049169  mov     ecx, 401h; dwDesiredAccess
0x18004916e  call    cs:__imp_OpenProcess
0x180049174  mov     rdx, rax
0x180049177  lea     rcx, [rsp+2D0h+hProcess]
0x18004917c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180049181  mov     rbx, [rsp+2D0h+hProcess]
0x180049186  lea     rax, [rbx-1]
0x18004918a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004918e  ja      loc_18004921B
0x180049194  mov     [rbp+1D0h+var_1C8], rbx
0x180049198  mov     r9, rbx
0x18004919b  lea     r8, aP; "%p"
0x1800491a2  mov     edx, 26h ; '&'; unsigned __int64
0x1800491a7  lea     rcx, [rbp+1D0h+var_1F0]; wchar_t *
0x1800491ab  call    ?StringCbPrintfW@@YAJPEA_W_KPEB_WZZ; StringCbPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800491b0  lea     r9, [rbp+1D0h+var_1F0]; wchar_t *
0x1800491b4  lea     r8, aSrchgathersvcT_1; "[SrchGatherSvc] TerminateProcess( %ws )"...
0x1800491bb  mov     edx, 73Dh; wchar_t *
0x1800491c0  lea     rcx, aOnecoreuapBase_255; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1800491c7  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x1800491cc  xor     edx, edx; uExitCode
0x1800491ce  mov     rcx, rbx; hProcess
0x1800491d1  call    cs:__imp_TerminateProcess
0x1800491d7  mov     r14d, 1
0x1800491dd  test    cs:byte_1802DA181, 8
0x1800491e4  jz      short loc_1800491FC
0x1800491e6  mov     r9, [r15+2B8h]
0x1800491ed  mov     r8d, edi
0x1800491f0  lea     rdx, MSSearchTraceId_ProtocolHostNameConflict_Killed
0x1800491f7  call    McTemplateU0qz_EventWriteTransfer
0x1800491fc  lea     rcx, [rsp+2D0h+hProcess]
0x180049201  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180049206  nop
0x180049207  lea     rcx, [rsp+2D0h+var_290]
0x18004920c  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x180049211  mov     edi, 1
0x180049216  jmp     loc_180048FD2
0x18004921b  cmp     cs:byte_1802DA181, r13b
0x180049222  jge     short loc_18004923A
0x180049224  mov     r9, [r15+2B8h]
0x18004922b  xor     r8d, r8d
0x18004922e  lea     rdx, MSSearchTraceId_ProtocolHostNameConflict_FailedToKill
0x180049235  call    McTemplateU0qz_EventWriteTransfer
0x18004923a  lea     rcx, [rsp+2D0h+hProcess]
0x18004923f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180049244  mov     eax, cs:?m_dwProcessNumber@CFilterPoolBase@@1KA; ulong CFilterPoolBase::m_dwProcessNumber
0x18004924a  mov     edi, 1
0x18004924f  add     eax, edi
0x180049251  mov     cs:?m_dwProcessNumber@CFilterPoolBase@@1KA, eax; ulong CFilterPoolBase::m_dwProcessNumber
0x180049257  mov     ecx, 400h
0x18004925c  cmp     eax, ecx
0x18004925e  jnz     short loc_180049266
0x180049260  mov     cs:?m_dwProcessNumber@CFilterPoolBase@@1KA, edi; ulong CFilterPoolBase::m_dwProcessNumber
0x180049266  add     esi, edi
0x180049268  cmp     esi, ecx
0x18004926a  lea     rcx, [rsp+2D0h+var_290]
0x18004926f  jz      short loc_18004927B
0x180049271  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x180049276  jmp     loc_180048FD2
0x18004927b  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x180049280  nop
0x180049281  lea     rcx, [rbp+1D0h+var_1C0]
0x180049285  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x18004928a  nop
0x18004928b  lea     rcx, [rbp+1D0h+var_120]
0x180049292  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x180049297  mov     eax, 80004005h
0x18004929c  jmp     short loc_1800492C1
0x18004929e  lea     rcx, [rsp+2D0h+var_290]
0x1800492a3  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x1800492a8  nop
0x1800492a9  lea     rcx, [rbp+1D0h+var_1C0]
0x1800492ad  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x1800492b2  nop
0x1800492b3  lea     rcx, [rbp+1D0h+var_120]
0x1800492ba  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x1800492bf  xor     eax, eax
0x1800492c1  mov     rcx, [rbp+1D0h+var_40]
0x1800492c8  xor     rcx, rsp; StackCookie
0x1800492cb  call    __security_check_cookie
0x1800492d0  mov     rbx, [rsp+2D0h+arg_18]
0x1800492d8  add     rsp, 2A0h
0x1800492df  pop     r15
0x1800492e1  pop     r14
0x1800492e3  pop     r13
0x1800492e5  pop     r12
0x1800492e7  pop     rdi
0x1800492e8  pop     rsi
0x1800492e9  pop     rbp
0x1800492ea  retn
```
