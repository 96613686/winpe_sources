# WindowsPerformanceRecorder::CControlManager::SetRunningEventTraceProperties(WindowsPerformanceRecorder::CETWProperties::CEventSession const &)

- ea: `0x18001d1bc`
- end: `0x18001d3cf`
- name: `?SetRunningEventTraceProperties@CControlManager@WindowsPerformanceRecorder@@AEAAJAEBUCEventSession@CETWProperties@2@@Z`
- size: `531`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CControlManager *__hidden this, const struct WindowsPerformanceRecorder::CETWProperties::CEventSession *)`
- caller_count: `9`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c5dc`
- `0x18001e2b8`
- `0x180032adc`
- `0x18003af80`
- `0x18003c6a4`
- `0x180058e54`
- `0x18005a1f0`
- `0x18005deb0`
- `0x18005ed4c`

## callees

- `0x18000829c`
- `0x18001a8c8`
- `0x18001d1bc`
- `0x18001e6e0`
- `0x1800351c0`
- `0x180038cd4`
- `0x18004f964`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001d1ee`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001d1ee`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18001d343`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18001d343`

## string_xrefs

- `0x18001d307`: `COMGUARD`
- `0x18001d38e`: `COMGUARD`

## pseudocode

```c
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::SetRunningEventTraceProperties(
        WindowsPerformanceRecorder::CControlManager *this,
        const struct WindowsPerformanceRecorder::CETWProperties::CEventSession *a2)
{
  unsigned int v3; // ecx
  void **v5; // rbx
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rax
  const WCHAR *v9; // rdx
  ULONG v11; // ebx
  const char *v12; // [rsp+28h] [rbp-10h]
  char v13; // [rsp+40h] [rbp+8h] BYREF

  v3 = *((_DWORD *)this + 102);
  v5 = (void **)((char *)this + 392);
  if ( v3 < **((_DWORD **)a2 + 1) )
  {
    if ( *v5 )
    {
      free(*v5);
      *v5 = 0;
    }
    if ( *((_QWORD *)this + 50) )
      *((_QWORD *)this + 50) = 0;
    v3 = **((_DWORD **)a2 + 1);
    *((_DWORD *)this + 102) = v3;
  }
  if ( !*v5 )
  {
    if ( !(unsigned __int8)ATL::CHeapPtrBase<_TRACE_LOGFILE_HEADER,ATL::CCRTAllocator>::AllocateBytes(
                             (char *)this + 392,
                             v3) )
    {
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)2,
        (unsigned __int8)"SetRunningEventTraceProperties",
        (const char *)0x1259,
        0x8007000E,
        "COMGUARD",
        v12);
      return 2147942414LL;
    }
    if ( *((_QWORD *)a2 + 2) )
      *((_QWORD *)this + 50) = *v5;
  }
  memset_0(*v5, 0, *((unsigned int *)this + 102));
  *(_DWORD *)*v5 = *((_DWORD *)this + 102);
  *(_OWORD *)((char *)*v5 + 24) = *(_OWORD *)(*((_QWORD *)a2 + 1) + 24LL);
  *((_DWORD *)*v5 + 11) = *(_DWORD *)(*((_QWORD *)a2 + 1) + 44LL);
  *((_DWORD *)*v5 + 29) = *(_DWORD *)(*((_QWORD *)a2 + 1) + 116LL);
  *((_DWORD *)*v5 + 28) = *(_DWORD *)(*((_QWORD *)a2 + 1) + 112LL);
  *((_DWORD *)*v5 + 16) = *(_DWORD *)(*((_QWORD *)a2 + 1) + 64LL);
  v6 = *((_QWORD *)this + 50);
  if ( v6 )
  {
    v7 = *((_QWORD *)a2 + 2);
    if ( v7 )
    {
      *(_BYTE *)(v6 + 120) = *(_BYTE *)(v7 + 120);
      *(_DWORD *)(*((_QWORD *)this + 50) + 136LL) ^= (*(_DWORD *)(*((_QWORD *)a2 + 2) + 136LL)
                                                    ^ *(_DWORD *)(*((_QWORD *)this + 50) + 136LL))
                                                   & 2;
    }
  }
  WindowsPerformanceRecorder::CControlManager::SaveEventSession_::_64_::CPerfEventMacro::CPerfEventMacro(&v13);
  v8 = *((_QWORD *)a2 + 1);
  if ( v8 && *(_DWORD *)(v8 + 116) )
    v9 = (const WCHAR *)(v8 + *(unsigned int *)(v8 + 116));
  else
    v9 = 0;
  v11 = ControlTraceW(0, v9, (PEVENT_TRACE_PROPERTIES)*v5, 0);
  WindowsPerformanceRecorder::CControlManager::SaveStateInRegistry_::_14_::CPerfEventMacro::_CPerfEventMacro(&v13);
  if ( v11 == 4201 )
  {
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      (unsigned __int8)"SetRunningEventTraceProperties",
      (const char *)0x1272,
      0x1069u,
      (char *)&byte_1800986EF,
      v12);
    return 3310891008LL;
  }
  else if ( v11 )
  {
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      (unsigned __int8)"SetRunningEventTraceProperties",
      (const char *)0x1276,
      v11,
      "COMGUARD",
      v12);
    return ATL::AtlHresultFromWin32(v11);
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x18001d1bc  mov     [rsp+arg_8], rbx
0x18001d1c1  mov     [rsp+arg_10], rsi
0x18001d1c6  push    rdi
0x18001d1c7  sub     rsp, 30h
0x18001d1cb  mov     rax, [rdx+8]
0x18001d1cf  mov     rdi, rcx
0x18001d1d2  mov     ecx, [rcx+198h]
0x18001d1d8  mov     rsi, rdx
0x18001d1db  lea     rbx, [rdi+188h]
0x18001d1e2  cmp     ecx, [rax]
0x18001d1e4  jnb     short loc_18001D21C
0x18001d1e6  mov     rcx, [rbx]; Block
0x18001d1e9  test    rcx, rcx
0x18001d1ec  jz      short loc_18001D1FB
0x18001d1ee  call    cs:__imp_free
0x18001d1f4  mov     qword ptr [rbx], 0
0x18001d1fb  cmp     qword ptr [rdi+190h], 0
0x18001d203  jz      short loc_18001D210
0x18001d205  mov     qword ptr [rdi+190h], 0
0x18001d210  mov     rax, [rsi+8]
0x18001d214  mov     ecx, [rax]
0x18001d216  mov     [rdi+198h], ecx
0x18001d21c  cmp     qword ptr [rbx], 0
0x18001d220  jnz     short loc_18001D245
0x18001d222  mov     edx, ecx
0x18001d224  mov     rcx, rbx
0x18001d227  call    ?AllocateBytes@?$CHeapPtrBase@U_TRACE_LOGFILE_HEADER@@VCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtrBase<_TRACE_LOGFILE_HEADER,ATL::CCRTAllocator>::AllocateBytes(unsigned __int64)
0x18001d22c  test    al, al
0x18001d22e  jz      loc_18001D307
0x18001d234  cmp     qword ptr [rsi+10h], 0
0x18001d239  jz      short loc_18001D245
0x18001d23b  mov     rax, [rbx]
0x18001d23e  mov     [rdi+190h], rax
0x18001d245  mov     r8d, [rdi+198h]; Size
0x18001d24c  xor     edx, edx; Val
0x18001d24e  mov     rcx, [rbx]; void *
0x18001d251  call    memset_0
0x18001d256  mov     rcx, [rbx]
0x18001d259  mov     eax, [rdi+198h]
0x18001d25f  mov     [rcx], eax
0x18001d261  mov     rax, [rsi+8]
0x18001d265  movups  xmm0, xmmword ptr [rax+18h]
0x18001d269  mov     rax, [rbx]
0x18001d26c  movdqu  xmmword ptr [rax+18h], xmm0
0x18001d271  mov     rax, [rsi+8]
0x18001d275  mov     rcx, [rbx]
0x18001d278  mov     eax, [rax+2Ch]
0x18001d27b  mov     [rcx+2Ch], eax
0x18001d27e  mov     rax, [rsi+8]
0x18001d282  mov     rcx, [rbx]
0x18001d285  mov     eax, [rax+74h]
0x18001d288  mov     [rcx+74h], eax
0x18001d28b  mov     rax, [rsi+8]
0x18001d28f  mov     rcx, [rbx]
0x18001d292  mov     eax, [rax+70h]
0x18001d295  mov     [rcx+70h], eax
0x18001d298  mov     rax, [rsi+8]
0x18001d29c  mov     rcx, [rbx]
0x18001d29f  mov     eax, [rax+40h]
0x18001d2a2  mov     [rcx+40h], eax
0x18001d2a5  mov     rcx, [rdi+190h]
0x18001d2ac  test    rcx, rcx
0x18001d2af  jz      short loc_18001D2E6
0x18001d2b1  mov     rax, [rsi+10h]
0x18001d2b5  test    rax, rax
0x18001d2b8  jz      short loc_18001D2E6
0x18001d2ba  mov     al, [rax+78h]
0x18001d2bd  mov     [rcx+78h], al
0x18001d2c0  mov     r8, [rdi+190h]
0x18001d2c7  mov     rax, [rsi+10h]
0x18001d2cb  mov     edx, [r8+88h]
0x18001d2d2  mov     ecx, edx
0x18001d2d4  xor     ecx, [rax+88h]
0x18001d2da  and     ecx, 2
0x18001d2dd  xor     ecx, edx
0x18001d2df  mov     [r8+88h], ecx
0x18001d2e6  lea     rcx, [rsp+38h+arg_0]
0x18001d2eb  call    _WindowsPerformanceRecorder__CControlManager__SaveEventSession____64___CPerfEventMacro__CPerfEventMacro
0x18001d2f0  mov     rax, [rsi+8]
0x18001d2f4  test    rax, rax
0x18001d2f7  jz      short loc_18001D339
0x18001d2f9  cmp     dword ptr [rax+74h], 0
0x18001d2fd  jz      short loc_18001D339
0x18001d2ff  mov     edx, [rax+74h]
0x18001d302  add     rdx, rax
0x18001d305  jmp     short loc_18001D33B
0x18001d307  lea     rax, aComguard; "COMGUARD"
0x18001d30e  mov     ebx, 8007000Eh
0x18001d313  mov     r9d, ebx; unsigned int
0x18001d316  mov     [rsp+38h+Format], rax; Format
0x18001d31b  mov     r8d, 1259h; char *
0x18001d321  lea     rdx, aSetrunningeven; "SetRunningEventTraceProperties"
0x18001d328  mov     ecx, 2; this
0x18001d32d  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18001d332  mov     eax, ebx
0x18001d334  jmp     loc_18001D3BF
0x18001d339  xor     edx, edx; InstanceName
0x18001d33b  mov     r8, [rbx]; Properties
0x18001d33e  xor     r9d, r9d; ControlCode
0x18001d341  xor     ecx, ecx; TraceHandle
0x18001d343  call    cs:__imp_ControlTraceW
0x18001d349  lea     rcx, [rsp+38h+arg_0]
0x18001d34e  mov     ebx, eax
0x18001d350  call    _WindowsPerformanceRecorder__CControlManager__SaveStateInRegistry____14___CPerfEventMacro___CPerfEventMacro
0x18001d355  mov     r9d, 1069h; unsigned int
0x18001d35b  cmp     ebx, r9d
0x18001d35e  jnz     short loc_18001D38A
0x18001d360  lea     rax, byte_1800986EF
0x18001d367  mov     r8d, 1272h; char *
0x18001d36d  lea     rdx, aSetrunningeven; "SetRunningEventTraceProperties"
0x18001d374  mov     [rsp+38h+Format], rax; Format
0x18001d379  mov     ecx, 2; this
0x18001d37e  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18001d383  mov     eax, 0C5583000h
0x18001d388  jmp     short loc_18001D3BF
0x18001d38a  test    ebx, ebx
0x18001d38c  jz      short loc_18001D3BD
0x18001d38e  lea     rax, aComguard; "COMGUARD"
0x18001d395  mov     r9d, ebx; unsigned int
0x18001d398  mov     r8d, 1276h; char *
0x18001d39e  mov     [rsp+38h+Format], rax; Format
0x18001d3a3  lea     rdx, aSetrunningeven; "SetRunningEventTraceProperties"
0x18001d3aa  mov     ecx, 2; this
0x18001d3af  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18001d3b4  mov     ecx, ebx; unsigned int
0x18001d3b6  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18001d3bb  jmp     short loc_18001D3BF
0x18001d3bd  xor     eax, eax
0x18001d3bf  mov     rbx, [rsp+38h+arg_8]
0x18001d3c4  mov     rsi, [rsp+38h+arg_10]
0x18001d3c9  add     rsp, 30h
0x18001d3cd  pop     rdi
0x18001d3ce  retn
```
