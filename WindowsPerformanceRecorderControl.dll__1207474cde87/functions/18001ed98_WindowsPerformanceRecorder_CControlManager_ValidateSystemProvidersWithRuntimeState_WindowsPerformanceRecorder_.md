# WindowsPerformanceRecorder::CControlManager::ValidateSystemProvidersWithRuntimeState(WindowsPerformanceRecorder::CETWProperties::CEventSession const &)

- ea: `0x18001ed98`
- end: `0x18001f166`
- name: `?ValidateSystemProvidersWithRuntimeState@CControlManager@WindowsPerformanceRecorder@@AEAAJAEBUCEventSession@CETWProperties@2@@Z`
- size: `974`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CControlManager *__hidden this, const struct WindowsPerformanceRecorder::CETWProperties::CEventSession *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003c6a4`

## callees

- `0x180002770`
- `0x18001e6e0`
- `0x18001ed98`
- `0x1800209d0`
- `0x18004f964`
- `0x180056f68`
- `0x1800570f0`
- `0x180057244`
- `0x1800577a0`
- `0x180057c4c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ee2a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001eebb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001eee2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001efac`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001efee`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001efff`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f031`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f0d6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f141`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f14d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ee2a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001eebb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001eee2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001efac`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001efee`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001efff`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f031`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f0d6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f141`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f14d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001edcf`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001ee35`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001edcf`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001ee35`
- `ntdll!NtQuerySystemInformation` at `0x18001ee18`
- `ntdll!NtQuerySystemInformation` at `0x18001ee71`
- `ntdll!NtQuerySystemInformation` at `0x18001ee18`
- `ntdll!NtQuerySystemInformation` at `0x18001ee71`

## string_xrefs

- `0x18001ee92`: `COMGUARD`

## pseudocode

```c
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::ValidateSystemProvidersWithRuntimeState(
        WindowsPerformanceRecorder::CControlManager *this,
        const struct WindowsPerformanceRecorder::CETWProperties::CEventSession *a2)
{
  __int64 v2; // r14
  _DWORD *v4; // rax
  _DWORD *v5; // rbx
  signed int v6; // edi
  NTSTATUS SystemInformation; // ecx
  size_t v8; // rdi
  _DWORD *v9; // rax
  __int128 v11; // xmm1
  char v12; // r15
  unsigned __int64 i; // rax
  void *v14; // rdi
  unsigned __int64 v15; // rsi
  int RunningOSMaximumStackWalkedKernelEventTypes; // eax
  __int64 v17; // rcx
  int EventTraceInformation; // eax
  void *v19; // rbx
  unsigned __int64 v20; // r14
  __int64 v21; // rcx
  void *v22; // rcx
  unsigned int v23; // ebx
  __int64 v24; // r12
  __int64 v25; // r13
  unsigned __int16 *v26; // rsi
  int j; // r14d
  unsigned __int64 k; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  const char *v31; // [rsp+28h] [rbp-40h]
  unsigned __int64 v32; // [rsp+30h] [rbp-38h] BYREF
  __int128 v33; // [rsp+38h] [rbp-30h]
  __int128 v34; // [rsp+48h] [rbp-20h]
  WindowsPerformanceRecorder::CControlManager *ReturnLength; // [rsp+B0h] [rbp+48h] BYREF
  int v36; // [rsp+B8h] [rbp+50h] BYREF
  void *v37; // [rsp+C0h] [rbp+58h] BYREF
  void *Block; // [rsp+C8h] [rbp+60h] BYREF

  ReturnLength = this;
  v2 = *((_QWORD *)a2 + 14);
  v33 = 0;
  LODWORD(ReturnLength) = 0;
  v34 = 0;
  v4 = malloc(0x30u);
  v5 = v4;
  if ( !v4 )
    goto LABEL_2;
  *(_OWORD *)v4 = 0;
  *((_OWORD *)v4 + 1) = 0;
  *((_OWORD *)v4 + 2) = 0;
  *v4 = 1;
  *((_QWORD *)v4 + 1) = v2;
  `WindowsPerformanceRecorder::CControlManager::GetEventTraceInformationT<_EVENT_TRACE_GROUPMASK_INFORMATION>'::`6'::CPerfEventMacro::CPerfEventMacro(&v36);
  SystemInformation = NtQuerySystemInformation(SystemPerformanceTraceInformation, v5, 0x30u, (PULONG)&ReturnLength);
  if ( SystemInformation == -1073741789 )
  {
    free(v5);
    v8 = (unsigned int)ReturnLength;
    v9 = malloc((unsigned int)ReturnLength);
    v5 = v9;
    if ( !v9 )
    {
      `WindowsPerformanceRecorder::CControlManager::GetEventTraceInformationT<_EVENT_TRACE_TAG_FILTER_INFORMATION>'::`6'::CPerfEventMacro::~CPerfEventMacro(&v36);
LABEL_2:
      v6 = -2147024882;
LABEL_8:
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)2,
        "GetRunningSystemGroupMask",
        (const char *)0x1285,
        v6,
        "COMGUARD",
        v31);
      free(v5);
      return 3310891015LL;
    }
    memset_0(v9, 0, v8);
    *v5 = 1;
    *((_QWORD *)v5 + 1) = v2;
    SystemInformation = NtQuerySystemInformation(SystemPerformanceTraceInformation, v5, v8, (PULONG)&ReturnLength);
  }
  v6 = SystemInformation != 0 ? SystemInformation | 0x10000000 : 0;
  `WindowsPerformanceRecorder::CControlManager::GetEventTraceInformationT<_EVENT_TRACE_TAG_FILTER_INFORMATION>'::`6'::CPerfEventMacro::~CPerfEventMacro(&v36);
  if ( v6 < 0 )
    goto LABEL_8;
  v11 = *((_OWORD *)v5 + 2);
  v33 = *((_OWORD *)v5 + 1);
  v34 = v11;
  free(v5);
  v12 = 0;
  for ( i = 0; i < 8; ++i )
  {
    if ( *((_DWORD *)&v33 + i) )
    {
      v12 = 1;
      break;
    }
  }
  v14 = 0;
  v37 = 0;
  v32 = 0;
  v15 = 0;
  if ( Performance::COSVersionInfo::IsWin7AndUp() )
  {
    RunningOSMaximumStackWalkedKernelEventTypes = WindowsPerformanceRecorder::CSystemProviderElement::GetRunningOSMaximumStackWalkedKernelEventTypes();
    LODWORD(ReturnLength) = 0;
    v36 = 4 * RunningOSMaximumStackWalkedKernelEventTypes + 24;
    EventTraceInformation = WindowsPerformanceRecorder::CControlManager::GetEventTraceInformationT<_EVENT_TRACE_SYSTEM_EVENT_INFORMATION>(
                              v17,
                              &v37,
                              &v36,
                              &ReturnLength);
    v14 = v37;
    if ( EventTraceInformation < 0 )
    {
LABEL_45:
      v23 = -984076273;
      goto LABEL_52;
    }
    v15 = (unsigned __int64)(unsigned int)((_DWORD)ReturnLength - 16) >> 2;
    v32 = v15;
  }
  v19 = 0;
  v37 = 0;
  Block = 0;
  v20 = 0;
  if ( Performance::COSVersionInfo::IsWin7AndUp() )
  {
    LODWORD(v37) = 384;
    v36 = 0;
    if ( (int)WindowsPerformanceRecorder::CControlManager::GetEventTraceInformationT<_EVENT_TRACE_TAG_FILTER_INFORMATION>(
                v21,
                &Block,
                &v37,
                &v36) < 0 )
    {
      v22 = Block;
LABEL_20:
      free(v22);
      v23 = -984076272;
      goto LABEL_52;
    }
    v19 = Block;
    v20 = (unsigned __int64)(unsigned int)(v36 - 16) >> 2;
    v37 = (void *)v20;
  }
  v24 = *((_QWORD *)a2 + 1);
  if ( *(_DWORD *)(v24 + 72) )
  {
    v25 = *(unsigned __int16 *)(v24 + 72);
    if ( *(_WORD *)(v24 + v25 + 2) )
    {
      v26 = (unsigned __int16 *)(v25 + v24 + 4);
      for ( j = 0; j < *(unsigned __int16 *)(v24 + v25 + 2); ++j )
      {
        if ( v26[1] == 1 )
        {
          if ( *v26 != 9 )
            goto LABEL_27;
          for ( k = 0; k < 8; ++k )
          {
            if ( *(_DWORD *)&v26[2 * k + 2] != *((_DWORD *)&v33 + k) )
              goto LABEL_27;
          }
        }
        else if ( v26[1] == 3 && Performance::COSVersionInfo::IsWin7AndUp() )
        {
          Block = (void *)(*v26 - 1LL);
          if ( (unsigned int)WindowsPerformanceRecorder::CControlManager::CompareValuesT<unsigned long>(
                               v29,
                               (__int64)(v26 + 2),
                               (unsigned __int64 *)&Block,
                               (__int64)v14 + 16,
                               &v32) )
          {
            free(v19);
            goto LABEL_45;
          }
        }
        else if ( v26[1] == 4 && Performance::COSVersionInfo::IsWin7AndUp() )
        {
          Block = (void *)(*v26 - 1LL);
          if ( (unsigned int)WindowsPerformanceRecorder::CControlManager::CompareValuesT<unsigned long>(
                               v30,
                               (__int64)(v26 + 2),
                               (unsigned __int64 *)&Block,
                               (__int64)v19 + 16,
                               (unsigned __int64 *)&v37) )
          {
            v22 = v19;
            goto LABEL_20;
          }
        }
        v26 += 2 * *v26;
      }
      free(v19);
      v23 = 0;
      goto LABEL_52;
    }
    if ( !v12 && !v15 && !v20 )
      goto LABEL_26;
LABEL_27:
    free(v19);
    v23 = -984076281;
    goto LABEL_52;
  }
  if ( v12 || v15 || v20 )
    goto LABEL_27;
LABEL_26:
  free(v19);
  v23 = 0;
LABEL_52:
  free(v14);
  return v23;
}

```

## disassembly

```asm
0x18001ed98  mov     [rsp-40h+ReturnLength], rcx
0x18001ed9d  push    rbp
0x18001ed9e  push    rbx
0x18001ed9f  push    rsi
0x18001eda0  push    rdi
0x18001eda1  push    r12
0x18001eda3  push    r13
0x18001eda5  push    r14
0x18001eda7  push    r15
0x18001eda9  mov     rbp, rsp
0x18001edac  sub     rsp, 68h
0x18001edb0  mov     r14, [rdx+70h]
0x18001edb4  xorps   xmm0, xmm0
0x18001edb7  xor     r13d, r13d
0x18001edba  mov     r12, rdx
0x18001edbd  movups  [rbp+var_30], xmm0
0x18001edc1  mov     dword ptr [rbp+ReturnLength], r13d
0x18001edc5  movups  [rbp+var_20], xmm0
0x18001edc9  lea     edi, [r13+30h]
0x18001edcd  mov     ecx, edi; Size
0x18001edcf  call    cs:__imp_malloc
0x18001edd5  lea     r15d, [r13+1]
0x18001edd9  mov     rbx, rax
0x18001eddc  test    rax, rax
0x18001eddf  jnz     short loc_18001EDEB
0x18001ede1  mov     edi, 8007000Eh
0x18001ede6  jmp     loc_18001EE92
0x18001edeb  xorps   xmm0, xmm0
0x18001edee  lea     rcx, [rbp+arg_8]
0x18001edf2  movups  xmmword ptr [rax], xmm0
0x18001edf5  movups  xmmword ptr [rax+10h], xmm0
0x18001edf9  movups  xmmword ptr [rax+20h], xmm0
0x18001edfd  mov     [rax], r15d
0x18001ee00  mov     [rax+8], r14
0x18001ee04  call    ??0CPerfEventMacro@?5???$GetEventTraceInformationT@U_EVENT_TRACE_GROUPMASK_INFORMATION@@@CControlManager@WindowsPerformanceRecorder@@AEBAJAEAV?$CHeapPtr@U_EVENT_TRACE_GROUPMASK_INFORMATION@@VCCRTAllocator@ATL@@@ATL@@AEAK1W4_EVENT_TRACE_INFORMATION_CLASS@@_K@Z@QEAA@XZ; `WindowsPerformanceRecorder::CControlManager::GetEventTraceInformationT<_EVENT_TRACE_GROUPMASK_INFORMATION>(ATL::CHeapPtr<_EVENT_TRACE_GROUPMASK_INFORMATION,ATL::CCRTAllocator> &,ulong &,ulong &,_EVENT_TRACE_INFORMATION_CLASS,unsigned __int64)'::`6'::CPerfEventMacro::CPerfEventMacro(void)
0x18001ee09  lea     r9, [rbp+ReturnLength]; ReturnLength
0x18001ee0d  mov     r8d, edi; SystemInformationLength
0x18001ee10  mov     rdx, rbx; SystemInformation
0x18001ee13  mov     ecx, 1Fh; SystemInformationClass
0x18001ee18  call    cs:__imp_NtQuerySystemInformation
0x18001ee1e  mov     ecx, eax
0x18001ee20  cmp     eax, 0C0000023h
0x18001ee25  jnz     short loc_18001EE79
0x18001ee27  mov     rcx, rbx; Block
0x18001ee2a  call    cs:__imp_free
0x18001ee30  mov     edi, dword ptr [rbp+ReturnLength]
0x18001ee33  mov     ecx, edi; Size
0x18001ee35  call    cs:__imp_malloc
0x18001ee3b  mov     rbx, rax
0x18001ee3e  test    rax, rax
0x18001ee41  jnz     short loc_18001EE4E
0x18001ee43  lea     rcx, [rbp+arg_8]
0x18001ee47  call    ??1CPerfEventMacro@?5???$GetEventTraceInformationT@U_EVENT_TRACE_TAG_FILTER_INFORMATION@@@CControlManager@WindowsPerformanceRecorder@@AEBAJAEAV?$CHeapPtr@U_EVENT_TRACE_TAG_FILTER_INFORMATION@@VCCRTAllocator@ATL@@@ATL@@AEAK1W4_EVENT_TRACE_INFORMATION_CLASS@@_K@Z@UEAA@XZ; `WindowsPerformanceRecorder::CControlManager::GetEventTraceInformationT<_EVENT_TRACE_TAG_FILTER_INFORMATION>(ATL::CHeapPtr<_EVENT_TRACE_TAG_FILTER_INFORMATION,ATL::CCRTAllocator> &,ulong &,ulong &,_EVENT_TRACE_INFORMATION_CLASS,unsigned __int64)'::`6'::CPerfEventMacro::~CPerfEventMacro(void)
0x18001ee4c  jmp     short loc_18001EDE1
0x18001ee4e  mov     r8, rdi; Size
0x18001ee51  xor     edx, edx; Val
0x18001ee53  mov     rcx, rbx; void *
0x18001ee56  call    memset_0
0x18001ee5b  lea     r9, [rbp+ReturnLength]; ReturnLength
0x18001ee5f  mov     [rbx], r15d
0x18001ee62  mov     r8d, edi; SystemInformationLength
0x18001ee65  mov     [rbx+8], r14
0x18001ee69  mov     rdx, rbx; SystemInformation
0x18001ee6c  mov     ecx, 1Fh; SystemInformationClass
0x18001ee71  call    cs:__imp_NtQuerySystemInformation
0x18001ee77  mov     ecx, eax
0x18001ee79  mov     eax, ecx
0x18001ee7b  bts     eax, 1Ch
0x18001ee7f  neg     ecx
0x18001ee81  lea     rcx, [rbp+arg_8]
0x18001ee85  sbb     edi, edi
0x18001ee87  and     edi, eax
0x18001ee89  call    ??1CPerfEventMacro@?5???$GetEventTraceInformationT@U_EVENT_TRACE_TAG_FILTER_INFORMATION@@@CControlManager@WindowsPerformanceRecorder@@AEBAJAEAV?$CHeapPtr@U_EVENT_TRACE_TAG_FILTER_INFORMATION@@VCCRTAllocator@ATL@@@ATL@@AEAK1W4_EVENT_TRACE_INFORMATION_CLASS@@_K@Z@UEAA@XZ; `WindowsPerformanceRecorder::CControlManager::GetEventTraceInformationT<_EVENT_TRACE_TAG_FILTER_INFORMATION>(ATL::CHeapPtr<_EVENT_TRACE_TAG_FILTER_INFORMATION,ATL::CCRTAllocator> &,ulong &,ulong &,_EVENT_TRACE_INFORMATION_CLASS,unsigned __int64)'::`6'::CPerfEventMacro::~CPerfEventMacro(void)
0x18001ee8e  test    edi, edi
0x18001ee90  jns     short loc_18001EECF
0x18001ee92  lea     rax, aComguard; "COMGUARD"
0x18001ee99  mov     r9d, edi; unsigned int
0x18001ee9c  mov     r8d, 1285h; char *
0x18001eea2  mov     [rsp+68h+Format], rax; Format
0x18001eea7  lea     rdx, aGetrunningsyst; "GetRunningSystemGroupMask"
0x18001eeae  mov     ecx, 2; this
0x18001eeb3  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18001eeb8  mov     rcx, rbx; Block
0x18001eebb  call    cs:__imp_free
0x18001eec1  test    edi, edi
0x18001eec3  jns     short loc_18001EEE8
0x18001eec5  mov     eax, 0C5583007h
0x18001eeca  jmp     loc_18001F155
0x18001eecf  movups  xmm0, xmmword ptr [rbx+10h]
0x18001eed3  mov     rcx, rbx; Block
0x18001eed6  movups  xmm1, xmmword ptr [rbx+20h]
0x18001eeda  movups  [rbp+var_30], xmm0
0x18001eede  movups  [rbp+var_20], xmm1
0x18001eee2  call    cs:__imp_free
0x18001eee8  mov     r15b, r13b
0x18001eeeb  mov     rax, r13
0x18001eeee  mov     ecx, 1
0x18001eef3  cmp     rax, 8
0x18001eef7  jnb     short loc_18001EF08
0x18001eef9  cmp     dword ptr [rbp+rax*4+var_30], r13d
0x18001eefe  jnz     short loc_18001EF05
0x18001ef00  add     rax, rcx
0x18001ef03  jmp     short loc_18001EEF3
0x18001ef05  mov     r15b, cl
0x18001ef08  mov     rdi, r13
0x18001ef0b  mov     [rbp+arg_10], r13
0x18001ef0f  mov     [rbp+var_38], r13
0x18001ef13  mov     rsi, r13
0x18001ef16  call    ?IsWin7AndUp@COSVersionInfo@Performance@@SA_NXZ; Performance::COSVersionInfo::IsWin7AndUp(void)
0x18001ef1b  test    al, al
0x18001ef1d  jz      short loc_18001EF67
0x18001ef1f  call    ?GetRunningOSMaximumStackWalkedKernelEventTypes@CSystemProviderElement@WindowsPerformanceRecorder@@SA_KXZ; WindowsPerformanceRecorder::CSystemProviderElement::GetRunningOSMaximumStackWalkedKernelEventTypes(void)
0x18001ef24  lea     r9, [rbp+ReturnLength]
0x18001ef28  mov     dword ptr [rbp+ReturnLength], r13d
0x18001ef2c  lea     r8, [rbp+arg_8]
0x18001ef30  lea     rdx, [rbp+arg_10]
0x18001ef34  lea     eax, ds:18h[rax*4]
0x18001ef3b  mov     [rbp+arg_8], eax
0x18001ef3e  mov     rax, [r12+70h]
0x18001ef43  mov     [rsp+68h+var_40], rax
0x18001ef48  call    ??$GetEventTraceInformationT@U_EVENT_TRACE_SYSTEM_EVENT_INFORMATION@@@CControlManager@WindowsPerformanceRecorder@@AEBAJAEAV?$CHeapPtr@U_EVENT_TRACE_SYSTEM_EVENT_INFORMATION@@VCCRTAllocator@ATL@@@ATL@@AEAK1W4_EVENT_TRACE_INFORMATION_CLASS@@_K@Z; WindowsPerformanceRecorder::CControlManager::GetEventTraceInformationT<_EVENT_TRACE_SYSTEM_EVENT_INFORMATION>(ATL::CHeapPtr<_EVENT_TRACE_SYSTEM_EVENT_INFORMATION,ATL::CCRTAllocator> &,ulong &,ulong &,_EVENT_TRACE_INFORMATION_CLASS,unsigned __int64)
0x18001ef4d  mov     rdi, [rbp+arg_10]
0x18001ef51  test    eax, eax
0x18001ef53  js      loc_18001F0DC
0x18001ef59  mov     esi, dword ptr [rbp+ReturnLength]
0x18001ef5c  add     esi, 0FFFFFFF0h
0x18001ef5f  shr     rsi, 2
0x18001ef63  mov     [rbp+var_38], rsi
0x18001ef67  mov     rbx, r13
0x18001ef6a  mov     [rbp+arg_10], r13
0x18001ef6e  mov     [rbp+Block], rbx
0x18001ef72  mov     r14, r13
0x18001ef75  call    ?IsWin7AndUp@COSVersionInfo@Performance@@SA_NXZ; Performance::COSVersionInfo::IsWin7AndUp(void)
0x18001ef7a  test    al, al
0x18001ef7c  jz      short loc_18001EFD0
0x18001ef7e  mov     rax, [r12+70h]
0x18001ef83  lea     r9, [rbp+arg_8]
0x18001ef87  lea     r8, [rbp+arg_10]
0x18001ef8b  mov     [rsp+68h+var_40], rax
0x18001ef90  lea     rdx, [rbp+Block]
0x18001ef94  mov     dword ptr [rbp+arg_10], 180h
0x18001ef9b  mov     [rbp+arg_8], r13d
0x18001ef9f  call    ??$GetEventTraceInformationT@U_EVENT_TRACE_TAG_FILTER_INFORMATION@@@CControlManager@WindowsPerformanceRecorder@@AEBAJAEAV?$CHeapPtr@U_EVENT_TRACE_TAG_FILTER_INFORMATION@@VCCRTAllocator@ATL@@@ATL@@AEAK1W4_EVENT_TRACE_INFORMATION_CLASS@@_K@Z; WindowsPerformanceRecorder::CControlManager::GetEventTraceInformationT<_EVENT_TRACE_TAG_FILTER_INFORMATION>(ATL::CHeapPtr<_EVENT_TRACE_TAG_FILTER_INFORMATION,ATL::CCRTAllocator> &,ulong &,ulong &,_EVENT_TRACE_INFORMATION_CLASS,unsigned __int64)
0x18001efa4  test    eax, eax
0x18001efa6  jns     short loc_18001EFBC
0x18001efa8  mov     rcx, [rbp+Block]; Block
0x18001efac  call    cs:__imp_free
0x18001efb2  mov     ebx, 0C5583010h
0x18001efb7  jmp     loc_18001F14A
0x18001efbc  mov     r14d, [rbp+arg_8]
0x18001efc0  mov     rbx, [rbp+Block]
0x18001efc4  add     r14d, 0FFFFFFF0h
0x18001efc8  shr     r14, 2
0x18001efcc  mov     [rbp+arg_10], r14
0x18001efd0  mov     r12, [r12+8]
0x18001efd5  cmp     [r12+48h], r13d
0x18001efda  jnz     short loc_18001F00F
0x18001efdc  test    r15b, r15b
0x18001efdf  jnz     short loc_18001EFFC
0x18001efe1  test    rsi, rsi
0x18001efe4  jnz     short loc_18001EFFC
0x18001efe6  test    r14, r14
0x18001efe9  jnz     short loc_18001EFFC
0x18001efeb  mov     rcx, rbx; Block
0x18001efee  call    cs:__imp_free
0x18001eff4  mov     ebx, r13d
0x18001eff7  jmp     loc_18001F14A
0x18001effc  mov     rcx, rbx; Block
0x18001efff  call    cs:__imp_free
0x18001f005  mov     ebx, 0C5583007h
0x18001f00a  jmp     loc_18001F14A
0x18001f00f  movzx   r13d, word ptr [r12+48h]
0x18001f015  xor     eax, eax
0x18001f017  cmp     [r12+r13+2], ax
0x18001f01d  jnz     short loc_18001F03E
0x18001f01f  test    r15b, r15b
0x18001f022  jnz     short loc_18001EFFC
0x18001f024  test    rsi, rsi
0x18001f027  jnz     short loc_18001EFFC
0x18001f029  test    r14, r14
0x18001f02c  jnz     short loc_18001EFFC
0x18001f02e  mov     rcx, rbx; Block
0x18001f031  call    cs:__imp_free
0x18001f037  xor     ebx, ebx
0x18001f039  jmp     loc_18001F14A
0x18001f03e  lea     rsi, [r12+4]
0x18001f043  add     rsi, r13
0x18001f046  xor     r15d, r15d
0x18001f049  mov     r14d, r15d
0x18001f04c  lea     r8d, [r15+1]
0x18001f050  movzx   eax, word ptr [r12+r13+2]
0x18001f056  cmp     r14d, eax
0x18001f059  jge     loc_18001F13E
0x18001f05f  cmp     [rsi+2], r8w
0x18001f064  jnz     short loc_18001F09B
0x18001f066  movzx   edx, word ptr [rsi]
0x18001f069  sub     rdx, r8
0x18001f06c  cmp     rdx, 8
0x18001f070  jnz     short loc_18001EFFC
0x18001f072  mov     rcx, r15
0x18001f075  cmp     rcx, rdx
0x18001f078  jnb     loc_18001F127
0x18001f07e  cmp     rcx, 8
0x18001f082  jnb     loc_18001F127
0x18001f088  mov     eax, dword ptr [rbp+rcx*4+var_30]
0x18001f08c  cmp     [rsi+rcx*4+4], eax
0x18001f090  jnz     loc_18001EFFC
0x18001f096  add     rcx, r8
0x18001f099  jmp     short loc_18001F075
0x18001f09b  cmp     word ptr [rsi+2], 3
0x18001f0a0  jnz     short loc_18001F0E9
0x18001f0a2  call    ?IsWin7AndUp@COSVersionInfo@Performance@@SA_NXZ; Performance::COSVersionInfo::IsWin7AndUp(void)
0x18001f0a7  test    al, al
0x18001f0a9  jz      short loc_18001F0E3
0x18001f0ab  movzx   eax, word ptr [rsi]
0x18001f0ae  lea     r9, [rdi+10h]
0x18001f0b2  dec     rax
0x18001f0b5  lea     rdx, [rsi+4]
0x18001f0b9  mov     [rbp+Block], rax
0x18001f0bd  lea     r8, [rbp+Block]
0x18001f0c1  lea     rax, [rbp+var_38]
0x18001f0c5  mov     [rsp+68h+Format], rax
0x18001f0ca  call    ??$CompareValuesT@K@CControlManager@WindowsPerformanceRecorder@@AEBAJPEBKAEB_K01@Z; WindowsPerformanceRecorder::CControlManager::CompareValuesT<ulong>(ulong const *,unsigned __int64 const &,ulong const *,unsigned __int64 const &)
0x18001f0cf  test    eax, eax
0x18001f0d1  jz      short loc_18001F121
0x18001f0d3  mov     rcx, rbx; Block
0x18001f0d6  call    cs:__imp_free
0x18001f0dc  mov     ebx, 0C558300Fh
0x18001f0e1  jmp     short loc_18001F14A
0x18001f0e3  mov     r8d, 1
0x18001f0e9  cmp     word ptr [rsi+2], 4
0x18001f0ee  jnz     short loc_18001F127
0x18001f0f0  call    ?IsWin7AndUp@COSVersionInfo@Performance@@SA_NXZ; Performance::COSVersionInfo::IsWin7AndUp(void)
0x18001f0f5  test    al, al
0x18001f0f7  jz      short loc_18001F121
0x18001f0f9  movzx   eax, word ptr [rsi]
0x18001f0fc  lea     r9, [rbx+10h]
0x18001f100  dec     rax
0x18001f103  lea     rdx, [rsi+4]
0x18001f107  mov     [rbp+Block], rax
0x18001f10b  lea     r8, [rbp+Block]
0x18001f10f  lea     rax, [rbp+arg_10]
0x18001f113  mov     [rsp+68h+Format], rax
0x18001f118  call    ??$CompareValuesT@K@CControlManager@WindowsPerformanceRecorder@@AEBAJPEBKAEB_K01@Z; WindowsPerformanceRecorder::CControlManager::CompareValuesT<ulong>(ulong const *,unsigned __int64 const &,ulong const *,unsigned __int64 const &)
0x18001f11d  test    eax, eax
0x18001f11f  jnz     short loc_18001F136
0x18001f121  mov     r8d, 1
0x18001f127  movzx   eax, word ptr [rsi]
0x18001f12a  add     r14d, r8d
0x18001f12d  lea     rsi, [rsi+rax*4]
0x18001f131  jmp     loc_18001F050
0x18001f136  mov     rcx, rbx
0x18001f139  jmp     loc_18001EFAC
0x18001f13e  mov     rcx, rbx; Block
0x18001f141  call    cs:__imp_free
0x18001f147  mov     ebx, r15d
0x18001f14a  mov     rcx, rdi; Block
0x18001f14d  call    cs:__imp_free
0x18001f153  mov     eax, ebx
0x18001f155  add     rsp, 68h
0x18001f159  pop     r15
0x18001f15b  pop     r14
0x18001f15d  pop     r13
0x18001f15f  pop     r12
0x18001f161  pop     rdi
0x18001f162  pop     rsi
0x18001f163  pop     rbx
0x18001f164  pop     rbp
0x18001f165  retn
```
