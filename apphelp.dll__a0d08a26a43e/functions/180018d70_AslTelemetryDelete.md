# AslTelemetryDelete

- ea: `0x180018d70`
- end: `0x180018ec9`
- name: `AslTelemetryDelete`
- size: `345`
- prototype: `char __fastcall(__int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180018a14`
- `0x18002ac10`

## callees

- `0x180018988`
- `0x180018d70`
- `0x180018f20`
- `0x180019094`
- `0x1800190b8`
- `0x180024a80`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180018e22`
- `ntdll!RtlDeleteCriticalSection` at `0x180018e22`
- `ntdll!RtlFreeHeap` at `0x180018e4b`
- `ntdll!RtlFreeHeap` at `0x180018e5c`
- `ntdll!RtlFreeHeap` at `0x180018e4b`
- `ntdll!RtlFreeHeap` at `0x180018e5c`

## pseudocode

```c
char __fastcall AslTelemetryDelete(__int64 a1)
{
  signed __int32 v2; // eax
  unsigned __int64 v3; // rcx
  void *v4; // r8
  void *v5; // r8
  ULONGLONG v6; // rcx
  ULONGLONG v7; // rdi
  unsigned int i; // esi
  ULONGLONG v9; // rcx
  ULONGLONG pullResult; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
    AslTelemetryFlush();
  v2 = _InterlockedExchangeAdd(&dword_180081354, 0xFFFFFFFF);
  if ( v2 == 1 )
    LOBYTE(v2) = TraceLoggingUnregister_EventUnregister(&dword_180080528);
  if ( a1 )
  {
    v3 = *(_QWORD *)(a1 + 192);
    if ( v3 )
    {
      for ( i = 0; i < v3; ++i )
      {
        v7 = 0;
        if ( i < v3 )
        {
          v9 = *(_QWORD *)(a1 + 184);
          pullResult = 0;
          if ( ULongLongMult(v9, i, &pullResult) < 0
            || (v6 = *(_QWORD *)(a1 + 216), v7 = v6 + pullResult, v6 + pullResult < v6) )
          {
            v7 = 0;
          }
        }
        AslAnsiStringFree(v7 + 8);
        AslAnsiStringFree(v7 + 24);
        v3 = *(_QWORD *)(a1 + 192);
      }
    }
    v4 = *(void **)(a1 + 216);
    if ( v4 )
      RtlFreeHeap(*(HANDLE *)(a1 + 176), 0, v4);
    *(_OWORD *)(a1 + 176) = 0;
    *(_OWORD *)(a1 + 192) = 0;
    *(_OWORD *)(a1 + 208) = 0;
    v5 = *(void **)(a1 + 168);
    if ( v5 )
      RtlFreeHeap(*(HANDLE *)(a1 + 128), 0, v5);
    *(_OWORD *)(a1 + 128) = 0;
    *(_OWORD *)(a1 + 144) = 0;
    *(_OWORD *)(a1 + 160) = 0;
    AslAnsiStringFree(a1 + 72);
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 88));
    LOBYTE(v2) = AslFree(NtCurrentPeb()->ProcessHeap, (void *)a1);
  }
  return v2;
}

```

## disassembly

```asm
0x180018d70  mov     [rsp+arg_8], rbx
0x180018d75  mov     [rsp+arg_10], rsi
0x180018d7a  push    rdi
0x180018d7b  sub     rsp, 20h
0x180018d7f  mov     rbx, rcx
0x180018d82  test    rcx, rcx
0x180018d85  jz      short loc_180018D8C
0x180018d87  call    AslTelemetryFlush
0x180018d8c  or      eax, 0FFFFFFFFh
0x180018d8f  lock xadd cs:dword_180081354, eax
0x180018d97  cmp     eax, 1
0x180018d9a  jnz     short loc_180018DA8
0x180018d9c  lea     rcx, dword_180080528
0x180018da3  call    TraceLoggingUnregister_EventUnregister
0x180018da8  test    rbx, rbx
0x180018dab  jnz     short loc_180018DBD
0x180018dad  mov     rbx, [rsp+28h+arg_8]
0x180018db2  mov     rsi, [rsp+28h+arg_10]
0x180018db7  add     rsp, 20h
0x180018dbb  pop     rdi
0x180018dbc  retn
0x180018dbd  mov     rcx, [rbx+0C0h]
0x180018dc4  test    rcx, rcx
0x180018dc7  jnz     loc_180018EC5
0x180018dcd  mov     r8, [rbx+0D8h]; P
0x180018dd4  test    r8, r8
0x180018dd7  jnz     short loc_180018E42
0x180018dd9  xorps   xmm0, xmm0
0x180018ddc  movups  xmmword ptr [rbx+0B0h], xmm0
0x180018de3  movups  xmmword ptr [rbx+0C0h], xmm0
0x180018dea  movups  xmmword ptr [rbx+0D0h], xmm0
0x180018df1  mov     r8, [rbx+0A8h]; P
0x180018df8  test    r8, r8
0x180018dfb  jnz     short loc_180018E53
0x180018dfd  xorps   xmm0, xmm0
0x180018e00  lea     rcx, [rbx+48h]
0x180018e04  movups  xmmword ptr [rbx+80h], xmm0
0x180018e0b  movups  xmmword ptr [rbx+90h], xmm0
0x180018e12  movups  xmmword ptr [rbx+0A0h], xmm0
0x180018e19  call    AslAnsiStringFree
0x180018e1e  lea     rcx, [rbx+58h]; CriticalSection
0x180018e22  call    cs:__imp_RtlDeleteCriticalSection
0x180018e28  mov     rcx, gs:60h
0x180018e31  mov     rdx, rbx
0x180018e34  mov     rcx, [rcx+30h]
0x180018e38  call    AslFree
0x180018e3d  jmp     loc_180018DAD
0x180018e42  mov     rcx, [rbx+0B0h]; HeapHandle
0x180018e49  xor     edx, edx; Flags
0x180018e4b  call    cs:__imp_RtlFreeHeap
0x180018e51  jmp     short loc_180018DD9
0x180018e53  mov     rcx, [rbx+80h]; HeapHandle
0x180018e5a  xor     edx, edx; Flags
0x180018e5c  call    cs:__imp_RtlFreeHeap
0x180018e62  jmp     short loc_180018DFD
0x180018e64  mov     rcx, [rbx+0D8h]
0x180018e6b  mov     rdi, [rsp+28h+pullResult]
0x180018e70  add     rdi, rcx
0x180018e73  cmp     rdi, rcx
0x180018e76  jnb     short loc_180018E7A
0x180018e78  xor     edi, edi
0x180018e7a  lea     rcx, [rdi+8]
0x180018e7e  call    AslAnsiStringFree
0x180018e83  lea     rcx, [rdi+18h]
0x180018e87  call    AslAnsiStringFree
0x180018e8c  mov     rcx, [rbx+0C0h]
0x180018e93  inc     esi
0x180018e95  mov     eax, esi
0x180018e97  cmp     rax, rcx
0x180018e9a  jnb     loc_180018DCD
0x180018ea0  xor     edi, edi
0x180018ea2  mov     edx, esi; ullMultiplier
0x180018ea4  cmp     rdx, rcx
0x180018ea7  jnb     short loc_180018E7A
0x180018ea9  mov     rcx, [rbx+0B8h]; ullMultiplicand
0x180018eb0  lea     r8, [rsp+28h+pullResult]; pullResult
0x180018eb5  mov     [rsp+28h+pullResult], rdi
0x180018eba  call    ULongLongMult
0x180018ebf  test    eax, eax
0x180018ec1  js      short loc_180018E78
0x180018ec3  jmp     short loc_180018E64
0x180018ec5  xor     esi, esi
0x180018ec7  jmp     short loc_180018EA0
```
