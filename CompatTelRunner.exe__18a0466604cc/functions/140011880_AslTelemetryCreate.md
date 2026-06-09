# AslTelemetryCreate

- ea: `0x140011880`
- end: `0x1400119f2`
- name: `AslTelemetryCreate`
- size: `370`
- prototype: `__int64 __fastcall(_QWORD *, const char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x14000b320`

## callees

- `0x140001214`
- `0x14000266c`
- `0x140011168`
- `0x140011880`
- `0x1400119f8`
- `0x1400151b0`
- `0x1400160ec`

## import_xrefs

- `ntdll!RtlInitializeCriticalSection` at `0x1400118fe`
- `ntdll!RtlInitializeCriticalSection` at `0x1400118fe`
- `ntdll!RtlAllocateHeap` at `0x1400118c6`
- `ntdll!RtlAllocateHeap` at `0x1400118c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001198d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001198d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001196f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001196f`

## string_xrefs

- `0x1400118e1`: `AslTelemetryCreate`

## pseudocode

```c
__int64 __fastcall AslTelemetryCreate(_QWORD *a1, const char *a2)
{
  char *Heap; // rax
  char *v5; // rbx
  int v6; // edi
  void *v7; // r8
  HANDLE ProcessHeap; // rax

  if ( _InterlockedIncrement(&dword_1400C90C4) == 1 )
    TraceLoggingRegister_EventRegister_2U();
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xF8u);
  v5 = Heap;
  if ( Heap )
  {
    RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(Heap + 88));
    *((_QWORD *)v5 + 28) = (((unsigned __int64)MEMORY[0x7FFE0004] << 32)
                          * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64;
    strcpy_s(v5, 0x40u, a2);
    v6 = AslAnsiStringCreate((PANSI_STRING)(v5 + 72));
    if ( v6 < 0 || (v6 = RtlArray<_ASL_TELEMETRY_EVENT>::Initialize(v5 + 128), v6 < 0) )
    {
      AslTelemetryDelete(v5);
    }
    else
    {
      v7 = (void *)*((_QWORD *)v5 + 27);
      if ( v7 )
        HeapFree(*((HANDLE *)v5 + 22), 0, v7);
      *((_OWORD *)v5 + 11) = 0;
      *((_OWORD *)v5 + 12) = 0;
      *((_OWORD *)v5 + 13) = 0;
      ProcessHeap = GetProcessHeap();
      *((_QWORD *)v5 + 26) = 4;
      v6 = 0;
      *((_QWORD *)v5 + 22) = ProcessHeap;
      *((_QWORD *)v5 + 24) = 0;
      *((_QWORD *)v5 + 25) = 0;
      *((_QWORD *)v5 + 27) = 0;
      *((_QWORD *)v5 + 23) = 48;
      *a1 = v5;
    }
  }
  else
  {
    v6 = -1073741801;
    AslLogCallPrintf(1, "AslTelemetryCreate", 204, "Out of memory");
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140011880  mov     [rsp+arg_0], rbx
0x140011885  mov     [rsp+arg_8], rsi
0x14001188a  push    rdi
0x14001188b  sub     rsp, 20h
0x14001188f  mov     rdi, rdx
0x140011892  mov     rsi, rcx
0x140011895  mov     eax, 1
0x14001189a  lock xadd cs:dword_1400C90C4, eax
0x1400118a2  inc     eax
0x1400118a4  cmp     eax, 1
0x1400118a7  jnz     short loc_1400118AE
0x1400118a9  call    TraceLoggingRegister_EventRegister_2U
0x1400118ae  mov     rcx, gs:60h
0x1400118b7  mov     edx, 8; Flags
0x1400118bc  mov     r8d, 0F8h; Size
0x1400118c2  mov     rcx, [rcx+30h]; HeapHandle
0x1400118c6  call    cs:__imp_RtlAllocateHeap
0x1400118cc  mov     rbx, rax
0x1400118cf  test    rax, rax
0x1400118d2  jnz     short loc_1400118FA
0x1400118d4  lea     r9, aOutOfMemory_0; "Out of memory"
0x1400118db  mov     r8d, 0CCh
0x1400118e1  lea     rdx, aAsltelemetrycr; "AslTelemetryCreate"
0x1400118e8  mov     edi, 0C0000017h
0x1400118ed  lea     ecx, [rax+1]
0x1400118f0  call    AslLogCallPrintf
0x1400118f5  jmp     loc_1400119E0
0x1400118fa  lea     rcx, [rax+58h]; CriticalSection
0x1400118fe  call    cs:__imp_RtlInitializeCriticalSection
0x140011904  mov     ecx, ds:7FFE0004h
0x14001190b  mov     eax, 7FFE0320h
0x140011910  shl     rcx, 20h
0x140011914  mov     r8, rdi; Source
0x140011917  mov     rax, [rax]
0x14001191a  shl     rax, 8
0x14001191e  mul     rcx
0x140011921  mov     rcx, rbx; Destination
0x140011924  mov     [rbx+0E0h], rdx
0x14001192b  mov     edx, 40h ; '@'; SizeInBytes
0x140011930  call    strcpy_s
0x140011935  lea     rcx, [rbx+48h]; DestinationString
0x140011939  call    AslAnsiStringCreate
0x14001193e  mov     edi, eax
0x140011940  test    eax, eax
0x140011942  js      loc_1400119D8
0x140011948  lea     rcx, [rbx+80h]
0x14001194f  call    ?Initialize@?$RtlArray@U_ASL_TELEMETRY_EVENT@@@@QEAAJ_K0@Z; RtlArray<_ASL_TELEMETRY_EVENT>::Initialize(unsigned __int64,unsigned __int64)
0x140011954  mov     edi, eax
0x140011956  test    eax, eax
0x140011958  js      short loc_1400119D8
0x14001195a  mov     r8, [rbx+0D8h]; lpMem
0x140011961  test    r8, r8
0x140011964  jz      short loc_140011975
0x140011966  mov     rcx, [rbx+0B0h]; hHeap
0x14001196d  xor     edx, edx; dwFlags
0x14001196f  call    cs:__imp_HeapFree
0x140011975  xorps   xmm0, xmm0
0x140011978  movups  xmmword ptr [rbx+0B0h], xmm0
0x14001197f  movups  xmmword ptr [rbx+0C0h], xmm0
0x140011986  movups  xmmword ptr [rbx+0D0h], xmm0
0x14001198d  call    cs:__imp_GetProcessHeap
0x140011993  mov     qword ptr [rbx+0D0h], 4
0x14001199e  xor     edi, edi
0x1400119a0  mov     [rbx+0B0h], rax
0x1400119a7  mov     qword ptr [rbx+0C0h], 0
0x1400119b2  mov     qword ptr [rbx+0C8h], 0
0x1400119bd  mov     qword ptr [rbx+0D8h], 0
0x1400119c8  mov     qword ptr [rbx+0B8h], 30h ; '0'
0x1400119d3  mov     [rsi], rbx
0x1400119d6  jmp     short loc_1400119E0
0x1400119d8  mov     rcx, rbx; P
0x1400119db  call    AslTelemetryDelete
0x1400119e0  mov     rbx, [rsp+28h+arg_0]
0x1400119e5  mov     eax, edi
0x1400119e7  mov     rsi, [rsp+28h+arg_8]
0x1400119ec  add     rsp, 20h
0x1400119f0  pop     rdi
0x1400119f1  retn
```
