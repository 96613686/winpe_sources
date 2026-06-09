# AslTelemetryDelete

- ea: `0x180047c58`
- end: `0x180047da7`
- name: `AslTelemetryDelete`
- size: `335`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180008448`
- `0x180047ae0`
- `0x1800e9ee0`

## callees

- `0x180047c58`
- `0x180047db0`
- `0x1800491a0`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180047d79`
- `ntdll!RtlDeleteCriticalSection` at `0x180047d79`
- `ntdll!RtlFreeHeap` at `0x180047d91`
- `ntdll!RtlFreeHeap` at `0x180047d91`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180047d1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180047d4e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180047d1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180047d4e`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180047ca0`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180047ca0`

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
  v2 = _InterlockedExchangeAdd(&dword_18011BF14, 0xFFFFFFFF);
  if ( v2 == 1 )
  {
    v3 = RegHandle;
    dword_180119490 = 0;
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
      HeapFree(*((HANDLE *)P + 22), 0, v9);
    *((_OWORD *)P + 11) = 0;
    *((_OWORD *)P + 12) = 0;
    *((_OWORD *)P + 13) = 0;
    v10 = (void *)*((_QWORD *)P + 21);
    if ( v10 )
      HeapFree(*((HANDLE *)P + 16), 0, v10);
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
0x180047c58  mov     [rsp+arg_8], rbx
0x180047c5d  mov     [rsp+arg_10], rsi
0x180047c62  push    rdi
0x180047c63  sub     rsp, 20h
0x180047c67  mov     rbx, rcx
0x180047c6a  test    rcx, rcx
0x180047c6d  jz      short loc_180047C74
0x180047c6f  call    AslTelemetryFlush
0x180047c74  or      eax, 0FFFFFFFFh
0x180047c77  lock xadd cs:dword_18011BF14, eax
0x180047c7f  cmp     eax, 1
0x180047c82  jnz     short loc_180047CA6
0x180047c84  mov     rcx, cs:RegHandle; RegHandle
0x180047c8b  mov     cs:dword_180119490, 0
0x180047c95  mov     cs:RegHandle, 0
0x180047ca0  call    cs:__imp_EventUnregister
0x180047ca6  test    rbx, rbx
0x180047ca9  jz      loc_180047D97
0x180047caf  mov     rcx, [rbx+0C0h]
0x180047cb6  test    rcx, rcx
0x180047cb9  jz      short loc_180047D06
0x180047cbb  xor     esi, esi
0x180047cbd  xor     edi, edi
0x180047cbf  mov     eax, esi
0x180047cc1  cmp     rax, rcx
0x180047cc4  jnb     short loc_180047CE4
0x180047cc6  mul     qword ptr [rbx+0B8h]
0x180047ccd  test    rdx, rdx
0x180047cd0  jnz     short loc_180047CE2
0x180047cd2  mov     rcx, [rbx+0D8h]
0x180047cd9  lea     rdi, [rcx+rax]
0x180047cdd  cmp     rdi, rcx
0x180047ce0  jnb     short loc_180047CE4
0x180047ce2  xor     edi, edi
0x180047ce4  lea     rcx, [rdi+8]
0x180047ce8  call    AslAnsiStringFree
0x180047ced  lea     rcx, [rdi+18h]
0x180047cf1  call    AslAnsiStringFree
0x180047cf6  mov     rcx, [rbx+0C0h]
0x180047cfd  inc     esi
0x180047cff  mov     eax, esi
0x180047d01  cmp     rax, rcx
0x180047d04  jb      short loc_180047CBD
0x180047d06  mov     r8, [rbx+0D8h]; lpMem
0x180047d0d  test    r8, r8
0x180047d10  jz      short loc_180047D21
0x180047d12  mov     rcx, [rbx+0B0h]; hHeap
0x180047d19  xor     edx, edx; dwFlags
0x180047d1b  call    cs:__imp_HeapFree
0x180047d21  xorps   xmm0, xmm0
0x180047d24  movups  xmmword ptr [rbx+0B0h], xmm0
0x180047d2b  movups  xmmword ptr [rbx+0C0h], xmm0
0x180047d32  movups  xmmword ptr [rbx+0D0h], xmm0
0x180047d39  mov     r8, [rbx+0A8h]; lpMem
0x180047d40  test    r8, r8
0x180047d43  jz      short loc_180047D54
0x180047d45  mov     rcx, [rbx+80h]; hHeap
0x180047d4c  xor     edx, edx; dwFlags
0x180047d4e  call    cs:__imp_HeapFree
0x180047d54  xorps   xmm0, xmm0
0x180047d57  lea     rcx, [rbx+48h]
0x180047d5b  movups  xmmword ptr [rbx+80h], xmm0
0x180047d62  movups  xmmword ptr [rbx+90h], xmm0
0x180047d69  movups  xmmword ptr [rbx+0A0h], xmm0
0x180047d70  call    AslAnsiStringFree
0x180047d75  lea     rcx, [rbx+58h]; CriticalSection
0x180047d79  call    cs:__imp_RtlDeleteCriticalSection
0x180047d7f  mov     rcx, gs:60h
0x180047d88  mov     r8, rbx; P
0x180047d8b  xor     edx, edx; Flags
0x180047d8d  mov     rcx, [rcx+30h]; HeapHandle
0x180047d91  call    cs:__imp_RtlFreeHeap
0x180047d97  mov     rbx, [rsp+28h+arg_8]
0x180047d9c  mov     rsi, [rsp+28h+arg_10]
0x180047da1  add     rsp, 20h
0x180047da5  pop     rdi
0x180047da6  retn
```
