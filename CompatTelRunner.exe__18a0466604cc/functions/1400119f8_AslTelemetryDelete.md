# AslTelemetryDelete

- ea: `0x1400119f8`
- end: `0x140011b47`
- name: `AslTelemetryDelete`
- size: `335`
- prototype: `char __fastcall(char *P)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000b2fc`
- `0x140011880`
- `0x1400a7ca0`

## callees

- `0x1400119f8`
- `0x140011b50`
- `0x140016230`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x140011b31`
- `ntdll!RtlFreeHeap` at `0x140011b31`
- `ntdll!RtlDeleteCriticalSection` at `0x140011b19`
- `ntdll!RtlDeleteCriticalSection` at `0x140011b19`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140011abb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140011aee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140011abb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140011aee`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x140011a40`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x140011a40`

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
  v2 = _InterlockedExchangeAdd(&dword_1400C90C4, 0xFFFFFFFF);
  if ( v2 == 1 )
  {
    v3 = RegHandle;
    dword_1400C7ED0 = 0;
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
0x1400119f8  mov     [rsp+arg_8], rbx
0x1400119fd  mov     [rsp+arg_10], rsi
0x140011a02  push    rdi
0x140011a03  sub     rsp, 20h
0x140011a07  mov     rbx, rcx
0x140011a0a  test    rcx, rcx
0x140011a0d  jz      short loc_140011A14
0x140011a0f  call    AslTelemetryFlush
0x140011a14  or      eax, 0FFFFFFFFh
0x140011a17  lock xadd cs:dword_1400C90C4, eax
0x140011a1f  cmp     eax, 1
0x140011a22  jnz     short loc_140011A46
0x140011a24  mov     rcx, cs:RegHandle; RegHandle
0x140011a2b  mov     cs:dword_1400C7ED0, 0
0x140011a35  mov     cs:RegHandle, 0
0x140011a40  call    cs:__imp_EventUnregister
0x140011a46  test    rbx, rbx
0x140011a49  jz      loc_140011B37
0x140011a4f  mov     rcx, [rbx+0C0h]
0x140011a56  test    rcx, rcx
0x140011a59  jz      short loc_140011AA6
0x140011a5b  xor     esi, esi
0x140011a5d  xor     edi, edi
0x140011a5f  mov     eax, esi
0x140011a61  cmp     rax, rcx
0x140011a64  jnb     short loc_140011A84
0x140011a66  mul     qword ptr [rbx+0B8h]
0x140011a6d  test    rdx, rdx
0x140011a70  jnz     short loc_140011A82
0x140011a72  mov     rcx, [rbx+0D8h]
0x140011a79  lea     rdi, [rcx+rax]
0x140011a7d  cmp     rdi, rcx
0x140011a80  jnb     short loc_140011A84
0x140011a82  xor     edi, edi
0x140011a84  lea     rcx, [rdi+8]
0x140011a88  call    AslAnsiStringFree
0x140011a8d  lea     rcx, [rdi+18h]
0x140011a91  call    AslAnsiStringFree
0x140011a96  mov     rcx, [rbx+0C0h]
0x140011a9d  inc     esi
0x140011a9f  mov     eax, esi
0x140011aa1  cmp     rax, rcx
0x140011aa4  jb      short loc_140011A5D
0x140011aa6  mov     r8, [rbx+0D8h]; lpMem
0x140011aad  test    r8, r8
0x140011ab0  jz      short loc_140011AC1
0x140011ab2  mov     rcx, [rbx+0B0h]; hHeap
0x140011ab9  xor     edx, edx; dwFlags
0x140011abb  call    cs:__imp_HeapFree
0x140011ac1  xorps   xmm0, xmm0
0x140011ac4  movups  xmmword ptr [rbx+0B0h], xmm0
0x140011acb  movups  xmmword ptr [rbx+0C0h], xmm0
0x140011ad2  movups  xmmword ptr [rbx+0D0h], xmm0
0x140011ad9  mov     r8, [rbx+0A8h]; lpMem
0x140011ae0  test    r8, r8
0x140011ae3  jz      short loc_140011AF4
0x140011ae5  mov     rcx, [rbx+80h]; hHeap
0x140011aec  xor     edx, edx; dwFlags
0x140011aee  call    cs:__imp_HeapFree
0x140011af4  xorps   xmm0, xmm0
0x140011af7  lea     rcx, [rbx+48h]
0x140011afb  movups  xmmword ptr [rbx+80h], xmm0
0x140011b02  movups  xmmword ptr [rbx+90h], xmm0
0x140011b09  movups  xmmword ptr [rbx+0A0h], xmm0
0x140011b10  call    AslAnsiStringFree
0x140011b15  lea     rcx, [rbx+58h]; CriticalSection
0x140011b19  call    cs:__imp_RtlDeleteCriticalSection
0x140011b1f  mov     rcx, gs:60h
0x140011b28  mov     r8, rbx; P
0x140011b2b  xor     edx, edx; Flags
0x140011b2d  mov     rcx, [rcx+30h]; HeapHandle
0x140011b31  call    cs:__imp_RtlFreeHeap
0x140011b37  mov     rbx, [rsp+28h+arg_8]
0x140011b3c  mov     rsi, [rsp+28h+arg_10]
0x140011b41  add     rsp, 20h
0x140011b45  pop     rdi
0x140011b46  retn
```
