# WindowsPerformanceRecorder::CEventProvidersCollection::GetUTCSessionHandle(unsigned __int64 &)

- ea: `0x180020df0`
- end: `0x180020f99`
- name: `?GetUTCSessionHandle@CEventProvidersCollection@WindowsPerformanceRecorder@@AEAAJAEA_K@Z`
- size: `425`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CEventProvidersCollection *__hidden this, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x180024ae0`
- `0x18003943c`

## callees

- `0x18000829c`
- `0x180020df0`
- `0x180020fa0`
- `0x180021018`
- `0x180021308`
- `0x18004f1d0`
- `0x18004f964`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180020efb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180020f0f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180020f23`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180020efb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180020f0f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180020f23`
- `api-ms-win-eventing-controller-l1-1-0!QueryAllTracesW` at `0x180020ebe`
- `api-ms-win-eventing-controller-l1-1-0!QueryAllTracesW` at `0x180020ebe`

## string_xrefs

- `0x180020f19`: `DiagTrack-Agent-Listener`

## pseudocode

```c
__int64 __fastcall WindowsPerformanceRecorder::CEventProvidersCollection::GetUTCSessionHandle(
        WindowsPerformanceRecorder::CEventProvidersCollection *this,
        unsigned __int64 *a2)
{
  struct _EVENT_TRACE_PROPERTIES *v3; // rdi
  ULONG v4; // esi
  char v5; // al
  struct _EVENT_TRACE_PROPERTIES *v6; // rcx
  __int64 v7; // r8
  PEVENT_TRACE_PROPERTIES *v8; // rbx
  ULONG v9; // eax
  PEVENT_TRACE_PROPERTIES v10; // rsi
  __int64 i; // r14
  unsigned __int64 v12; // r12
  ULONG LoggerCount; // [rsp+70h] [rbp+8h] BYREF
  int v15; // [rsp+74h] [rbp+Ch]
  PEVENT_TRACE_PROPERTIES *PropertyArray; // [rsp+80h] [rbp+18h] BYREF
  void *Block; // [rsp+88h] [rbp+20h] BYREF

  v15 = HIDWORD(this);
  PropertyArray = 0;
  v3 = 0;
  Block = 0;
  LoggerCount = 0;
  v4 = Performance::COSVersionInfo::IsWindows10AndUp() ? 256 : 64;
  if ( (unsigned __int8)ATL::CAutoVectorPtr<unsigned __int64>::Allocate(&PropertyArray, v4)
    && (v5 = ATL::CAutoVectorPtr<unsigned char>::Allocate(&Block, 4216 * v4),
        v3 = (struct _EVENT_TRACE_PROPERTIES *)Block,
        v5) )
  {
    memset_0(Block, 0, 4216 * v4);
    v6 = v3;
    v7 = 0;
    v8 = PropertyArray;
    do
    {
      v6->Wnode.BufferSize = 4216;
      v6->LoggerNameOffset = 120;
      v6->LogFileNameOffset = 2168;
      v8[v7] = v6;
      v6 = (struct _EVENT_TRACE_PROPERTIES *)((char *)v6 + v6->Wnode.BufferSize);
      v7 = (unsigned int)(v7 + 1);
    }
    while ( (unsigned int)v7 < v4 );
    v9 = QueryAllTracesW(v8, v4, &LoggerCount);
    if ( !v9 || (int)ATL::AtlHresultFromWin32(v9) >= 0 )
    {
      v10 = 0;
      for ( i = 0; (unsigned int)i < LoggerCount; i = (unsigned int)(i + 1) )
      {
        v12 = (unsigned __int64)v8[i] + 2 * ((unsigned __int64)v8[i]->LoggerNameOffset >> 1);
        if ( !(unsigned int)_o__wcsicmp(v12, L"DiagTrack-Listener") )
        {
          _mm_lfence();
          v10 = v8[i];
          break;
        }
        if ( !(unsigned int)_o__wcsicmp(v12, L"AutoLogger-Diagtrack-Listener")
          || !(unsigned int)_o__wcsicmp(v12, L"DiagTrack-Agent-Listener") )
        {
          v10 = v8[i];
        }
      }
      if ( v10 )
      {
        *a2 = v10->Wnode.HistoricalContext;
        operator delete(v3);
        operator delete(v8);
        return 0;
      }
    }
  }
  else
  {
    v8 = PropertyArray;
  }
  operator delete(v3);
  operator delete(v8);
  return 1;
}

```

## disassembly

```asm
0x180020df0  mov     rax, rsp
0x180020df3  mov     [rax+8], rcx
0x180020df7  push    rbx
0x180020df8  push    rsi
0x180020df9  push    rdi
0x180020dfa  push    r12
0x180020dfc  push    r13
0x180020dfe  push    r14
0x180020e00  push    r15
0x180020e02  sub     rsp, 30h
0x180020e06  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x180020e0e  mov     r13, rdx
0x180020e11  mov     qword ptr [rax+18h], 0
0x180020e19  xor     edi, edi
0x180020e1b  mov     [rax+20h], rdi
0x180020e1f  mov     [rax+8], edi
0x180020e22  call    ?IsWindows10AndUp@COSVersionInfo@Performance@@SA_NXZ; Performance::COSVersionInfo::IsWindows10AndUp(void)
0x180020e27  neg     al
0x180020e29  sbb     ecx, ecx
0x180020e2b  and     ecx, 0C0h
0x180020e31  add     ecx, 40h ; '@'
0x180020e34  mov     esi, ecx
0x180020e36  mov     edx, ecx
0x180020e38  lea     rcx, [rsp+68h+PropertyArray]
0x180020e40  call    ?Allocate@?$CAutoVectorPtr@_K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<unsigned __int64>::Allocate(unsigned __int64)
0x180020e45  test    al, al
0x180020e47  jz      loc_180020F5E
0x180020e4d  imul    eax, esi, 1078h
0x180020e53  mov     ebx, eax
0x180020e55  mov     edx, eax
0x180020e57  lea     rcx, [rsp+68h+Block]
0x180020e5f  call    ?Allocate@?$CAutoVectorPtr@E@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<uchar>::Allocate(unsigned __int64)
0x180020e64  mov     rdi, [rsp+68h+Block]
0x180020e6c  test    al, al
0x180020e6e  jz      loc_180020F5E
0x180020e74  mov     r8d, ebx; Size
0x180020e77  xor     edx, edx; Val
0x180020e79  mov     rcx, rdi; void *
0x180020e7c  call    memset_0
0x180020e81  mov     rcx, rdi
0x180020e84  xor     r8d, r8d
0x180020e87  mov     rbx, [rsp+68h+PropertyArray]
0x180020e8f  mov     dword ptr [rcx], 1078h
0x180020e95  mov     dword ptr [rcx+74h], 78h ; 'x'
0x180020e9c  mov     dword ptr [rcx+70h], 878h
0x180020ea3  mov     [rbx+r8*8], rcx
0x180020ea7  mov     eax, [rcx]
0x180020ea9  add     rcx, rax
0x180020eac  inc     r8d
0x180020eaf  cmp     r8d, esi
0x180020eb2  jb      short loc_180020E8F
0x180020eb4  lea     r8, [rsp+68h+LoggerCount]; LoggerCount
0x180020eb9  mov     edx, esi; PropertyArrayCount
0x180020ebb  mov     rcx, rbx; PropertyArray
0x180020ebe  call    cs:__imp_QueryAllTracesW
0x180020ec4  test    eax, eax
0x180020ec6  jz      short loc_180020ED7
0x180020ec8  mov     ecx, eax; unsigned int
0x180020eca  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180020ecf  test    eax, eax
0x180020ed1  js      loc_180020F66
0x180020ed7  xor     esi, esi
0x180020ed9  xor     r14d, r14d
0x180020edc  cmp     r14d, [rsp+68h+LoggerCount]
0x180020ee1  jnb     short loc_180020F3D
0x180020ee3  mov     rcx, [rbx+r14*8]
0x180020ee7  mov     eax, [rcx+74h]
0x180020eea  shr     rax, 1
0x180020eed  lea     r12, [rcx+rax*2]
0x180020ef1  lea     rdx, aDiagtrackListe; "DiagTrack-Listener"
0x180020ef8  mov     rcx, r12
0x180020efb  call    cs:__imp__o__wcsicmp
0x180020f01  test    eax, eax
0x180020f03  jz      short loc_180020F36
0x180020f05  lea     rdx, aAutologgerDiag; "AutoLogger-Diagtrack-Listener"
0x180020f0c  mov     rcx, r12
0x180020f0f  call    cs:__imp__o__wcsicmp
0x180020f15  test    eax, eax
0x180020f17  jz      short loc_180020F2D
0x180020f19  lea     rdx, aDiagtrackAgent; "DiagTrack-Agent-Listener"
0x180020f20  mov     rcx, r12
0x180020f23  call    cs:__imp__o__wcsicmp
0x180020f29  test    eax, eax
0x180020f2b  jnz     short loc_180020F31
0x180020f2d  mov     rsi, [rbx+r14*8]
0x180020f31  inc     r14d
0x180020f34  jmp     short loc_180020EDC
0x180020f36  lfence
0x180020f39  mov     rsi, [rbx+r14*8]
0x180020f3d  test    rsi, rsi
0x180020f40  jz      short loc_180020F66
0x180020f42  mov     rax, [rsi+8]
0x180020f46  mov     [r13+0], rax
0x180020f4a  mov     rcx, rdi; Block
0x180020f4d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180020f52  mov     rcx, rbx; Block
0x180020f55  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180020f5a  xor     eax, eax
0x180020f5c  jmp     short loc_180020F88
0x180020f5e  mov     rbx, [rsp+68h+PropertyArray]
0x180020f66  mov     rcx, rdi; Block
0x180020f69  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180020f6e  mov     rcx, rbx; Block
0x180020f71  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180020f76  mov     eax, 1
0x180020f7b  jmp     short loc_180020F88
0x180020f7d  mov     eax, [rsp+68h+LoggerCount]
0x180020f81  jmp     short loc_180020F88
0x180020f83  mov     eax, 8007000Eh
0x180020f88  add     rsp, 30h
0x180020f8c  pop     r15
0x180020f8e  pop     r14
0x180020f90  pop     r13
0x180020f92  pop     r12
0x180020f94  pop     rdi
0x180020f95  pop     rsi
0x180020f96  pop     rbx
0x180020f97  retn
```
