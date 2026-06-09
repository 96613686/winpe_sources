# AslTelemetryDelete

- ea: `0x180014568`
- end: `0x1800146b7`
- name: `AslTelemetryDelete`
- size: `335`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000782c`
- `0x180014320`
- `0x1800d0920`

## callees

- `0x180014568`
- `0x1800146c0`
- `0x180017894`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18001462b`
- `ntdll!RtlFreeHeap` at `0x18001465e`
- `ntdll!RtlFreeHeap` at `0x1800146a1`
- `ntdll!RtlFreeHeap` at `0x18001462b`
- `ntdll!RtlFreeHeap` at `0x18001465e`
- `ntdll!RtlFreeHeap` at `0x1800146a1`
- `ntdll!RtlDeleteCriticalSection` at `0x180014689`
- `ntdll!RtlDeleteCriticalSection` at `0x180014689`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800145b0`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800145b0`

## pseudocode

```c
char __fastcall AslTelemetryDelete(char *P)
{
  signed __int32 v2; // eax
  REGHANDLE v3; // rcx
  unsigned __int64 v4; // rcx
  unsigned int i; // esi
  __int64 v6; // rdi
  __int64 v7; // rax
  unsigned __int64 v8; // rcx
  void *v9; // r8
  void *v10; // r8

  if ( P )
    AslTelemetryFlush();
  v2 = _InterlockedExchangeAdd(&dword_1800FEF50, 0xFFFFFFFF);
  if ( v2 == 1 )
  {
    v3 = RegHandle;
    dword_1800FDED0 = 0;
    RegHandle = 0;
    LOBYTE(v2) = EventUnregister(v3);
  }
  if ( P )
  {
    v4 = *((_QWORD *)P + 24);
    if ( v4 )
    {
      for ( i = 0; i < v4; ++i )
      {
        v6 = 0;
        if ( i < v4 )
        {
          v7 = *((_QWORD *)P + 23) * i;
          if ( !is_mul_ok(*((_QWORD *)P + 23), i) || (v8 = *((_QWORD *)P + 27), v6 = v8 + v7, v8 + v7 < v8) )
            v6 = 0;
        }
        AslAnsiStringFree(v6 + 8);
        AslAnsiStringFree(v6 + 24);
        v4 = *((_QWORD *)P + 24);
      }
    }
    v9 = (void *)*((_QWORD *)P + 27);
    if ( v9 )
      RtlFreeHeap(*((HANDLE *)P + 22), 0, v9);
    *((_OWORD *)P + 11) = 0;
    *((_OWORD *)P + 12) = 0;
    *((_OWORD *)P + 13) = 0;
    v10 = (void *)*((_QWORD *)P + 21);
    if ( v10 )
      RtlFreeHeap(*((HANDLE *)P + 16), 0, v10);
    *((_OWORD *)P + 8) = 0;
    *((_OWORD *)P + 9) = 0;
    *((_OWORD *)P + 10) = 0;
    AslAnsiStringFree(P + 72);
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(P + 88));
    LOBYTE(v2) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  }
  return v2;
}

```

## disassembly

```asm
0x180014568  mov     [rsp+arg_8], rbx
0x18001456d  mov     [rsp+arg_10], rsi
0x180014572  push    rdi
0x180014573  sub     rsp, 20h
0x180014577  mov     rbx, rcx
0x18001457a  test    rcx, rcx
0x18001457d  jz      short loc_180014584
0x18001457f  call    AslTelemetryFlush
0x180014584  or      eax, 0FFFFFFFFh
0x180014587  lock xadd cs:dword_1800FEF50, eax
0x18001458f  cmp     eax, 1
0x180014592  jnz     short loc_1800145B6
0x180014594  mov     rcx, cs:RegHandle; RegHandle
0x18001459b  mov     cs:dword_1800FDED0, 0
0x1800145a5  mov     cs:RegHandle, 0
0x1800145b0  call    cs:__imp_EventUnregister
0x1800145b6  test    rbx, rbx
0x1800145b9  jz      loc_1800146A7
0x1800145bf  mov     rcx, [rbx+0C0h]
0x1800145c6  test    rcx, rcx
0x1800145c9  jz      short loc_180014616
0x1800145cb  xor     esi, esi
0x1800145cd  xor     edi, edi
0x1800145cf  mov     eax, esi
0x1800145d1  cmp     rax, rcx
0x1800145d4  jnb     short loc_1800145F4
0x1800145d6  mul     qword ptr [rbx+0B8h]
0x1800145dd  test    rdx, rdx
0x1800145e0  jnz     short loc_1800145F2
0x1800145e2  mov     rcx, [rbx+0D8h]
0x1800145e9  lea     rdi, [rcx+rax]
0x1800145ed  cmp     rdi, rcx
0x1800145f0  jnb     short loc_1800145F4
0x1800145f2  xor     edi, edi
0x1800145f4  lea     rcx, [rdi+8]
0x1800145f8  call    AslAnsiStringFree
0x1800145fd  lea     rcx, [rdi+18h]
0x180014601  call    AslAnsiStringFree
0x180014606  mov     rcx, [rbx+0C0h]
0x18001460d  inc     esi
0x18001460f  mov     eax, esi
0x180014611  cmp     rax, rcx
0x180014614  jb      short loc_1800145CD
0x180014616  mov     r8, [rbx+0D8h]; P
0x18001461d  test    r8, r8
0x180014620  jz      short loc_180014631
0x180014622  mov     rcx, [rbx+0B0h]; HeapHandle
0x180014629  xor     edx, edx; Flags
0x18001462b  call    cs:__imp_RtlFreeHeap
0x180014631  xorps   xmm0, xmm0
0x180014634  movups  xmmword ptr [rbx+0B0h], xmm0
0x18001463b  movups  xmmword ptr [rbx+0C0h], xmm0
0x180014642  movups  xmmword ptr [rbx+0D0h], xmm0
0x180014649  mov     r8, [rbx+0A8h]; P
0x180014650  test    r8, r8
0x180014653  jz      short loc_180014664
0x180014655  mov     rcx, [rbx+80h]; HeapHandle
0x18001465c  xor     edx, edx; Flags
0x18001465e  call    cs:__imp_RtlFreeHeap
0x180014664  xorps   xmm0, xmm0
0x180014667  lea     rcx, [rbx+48h]
0x18001466b  movups  xmmword ptr [rbx+80h], xmm0
0x180014672  movups  xmmword ptr [rbx+90h], xmm0
0x180014679  movups  xmmword ptr [rbx+0A0h], xmm0
0x180014680  call    AslAnsiStringFree
0x180014685  lea     rcx, [rbx+58h]; CriticalSection
0x180014689  call    cs:__imp_RtlDeleteCriticalSection
0x18001468f  mov     rcx, gs:60h
0x180014698  mov     r8, rbx; P
0x18001469b  xor     edx, edx; Flags
0x18001469d  mov     rcx, [rcx+30h]; HeapHandle
0x1800146a1  call    cs:__imp_RtlFreeHeap
0x1800146a7  mov     rbx, [rsp+28h+arg_8]
0x1800146ac  mov     rsi, [rsp+28h+arg_10]
0x1800146b1  add     rsp, 20h
0x1800146b5  pop     rdi
0x1800146b6  retn
```
