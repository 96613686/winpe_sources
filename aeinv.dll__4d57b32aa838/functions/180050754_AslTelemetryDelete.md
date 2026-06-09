# AslTelemetryDelete

- ea: `0x180050754`
- end: `0x18005089c`
- name: `AslTelemetryDelete`
- size: `328`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180050550`
- `0x1800506d0`
- `0x180050724`

## callees

- `0x180002460`
- `0x18001cce4`
- `0x18003414c`
- `0x18004ba9c`
- `0x180050754`
- `0x180050984`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180050871`
- `ntdll!RtlDeleteCriticalSection` at `0x180050871`
- `KERNEL32!HeapFree` at `0x180050813`
- `KERNEL32!HeapFree` at `0x180050846`
- `KERNEL32!HeapFree` at `0x180050813`
- `KERNEL32!HeapFree` at `0x180050846`

## pseudocode

```c
__int64 __fastcall AslTelemetryDelete(__int64 a1)
{
  __int64 result; // rax
  unsigned __int64 v3; // rcx
  unsigned int i; // esi
  __int64 v5; // rdi
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // rcx
  void *v8; // r8
  void *v9; // r8
  unsigned __int64 v10; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
    AslTelemetryFlush();
  result = (unsigned int)_InterlockedExchangeAdd(&dword_180182138, 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
    result = TraceLoggingUnregister_EventUnregister(&dword_180180030);
  if ( a1 )
  {
    v3 = *(_QWORD *)(a1 + 192);
    if ( v3 )
    {
      for ( i = 0; i < v3; ++i )
      {
        v5 = 0;
        if ( i < v3 )
        {
          v6 = *(_QWORD *)(a1 + 184);
          v10 = 0;
          if ( (int)ULongLongMult(v6, i, &v10) < 0 || (v7 = *(_QWORD *)(a1 + 216), v5 = v7 + v10, v7 + v10 < v7) )
            v5 = 0;
        }
        AslAnsiStringFree(v5 + 8);
        AslAnsiStringFree(v5 + 24);
        v3 = *(_QWORD *)(a1 + 192);
      }
    }
    v8 = *(void **)(a1 + 216);
    if ( v8 )
      HeapFree(*(HANDLE *)(a1 + 176), 0, v8);
    *(_OWORD *)(a1 + 176) = 0;
    *(_OWORD *)(a1 + 192) = 0;
    *(_OWORD *)(a1 + 208) = 0;
    v9 = *(void **)(a1 + 168);
    if ( v9 )
      HeapFree(*(HANDLE *)(a1 + 128), 0, v9);
    *(_OWORD *)(a1 + 128) = 0;
    *(_OWORD *)(a1 + 144) = 0;
    *(_OWORD *)(a1 + 160) = 0;
    AslAnsiStringFree(a1 + 72);
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 88));
    return AslFree(NtCurrentPeb()->ProcessHeap, a1);
  }
  return result;
}

```

## disassembly

```asm
0x180050754  mov     [rsp+arg_8], rbx
0x180050759  mov     [rsp+arg_10], rsi
0x18005075e  push    rdi
0x18005075f  sub     rsp, 20h
0x180050763  mov     rbx, rcx
0x180050766  test    rcx, rcx
0x180050769  jz      short loc_180050770
0x18005076b  call    AslTelemetryFlush
0x180050770  or      eax, 0FFFFFFFFh
0x180050773  lock xadd cs:dword_180182138, eax
0x18005077b  cmp     eax, 1
0x18005077e  jnz     short loc_18005078C
0x180050780  lea     rcx, dword_180180030
0x180050787  call    TraceLoggingUnregister_EventUnregister
0x18005078c  test    rbx, rbx
0x18005078f  jz      loc_18005088C
0x180050795  mov     rcx, [rbx+0C0h]
0x18005079c  test    rcx, rcx
0x18005079f  jz      short loc_1800507FE
0x1800507a1  xor     esi, esi
0x1800507a3  xor     edi, edi
0x1800507a5  mov     edx, esi; unsigned __int64
0x1800507a7  cmp     rdx, rcx
0x1800507aa  jnb     short loc_1800507DC
0x1800507ac  mov     rcx, [rbx+0B8h]; unsigned __int64
0x1800507b3  lea     r8, [rsp+28h+arg_0]; unsigned __int64 *
0x1800507b8  mov     [rsp+28h+arg_0], rdi
0x1800507bd  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800507c2  test    eax, eax
0x1800507c4  js      short loc_1800507DA
0x1800507c6  mov     rcx, [rbx+0D8h]
0x1800507cd  mov     rdi, [rsp+28h+arg_0]
0x1800507d2  add     rdi, rcx
0x1800507d5  cmp     rdi, rcx
0x1800507d8  jnb     short loc_1800507DC
0x1800507da  xor     edi, edi
0x1800507dc  lea     rcx, [rdi+8]
0x1800507e0  call    AslAnsiStringFree
0x1800507e5  lea     rcx, [rdi+18h]
0x1800507e9  call    AslAnsiStringFree
0x1800507ee  mov     rcx, [rbx+0C0h]
0x1800507f5  inc     esi
0x1800507f7  mov     eax, esi
0x1800507f9  cmp     rax, rcx
0x1800507fc  jb      short loc_1800507A3
0x1800507fe  mov     r8, [rbx+0D8h]; lpMem
0x180050805  test    r8, r8
0x180050808  jz      short loc_180050819
0x18005080a  mov     rcx, [rbx+0B0h]; hHeap
0x180050811  xor     edx, edx; dwFlags
0x180050813  call    cs:__imp_HeapFree
0x180050819  xorps   xmm0, xmm0
0x18005081c  movups  xmmword ptr [rbx+0B0h], xmm0
0x180050823  movups  xmmword ptr [rbx+0C0h], xmm0
0x18005082a  movups  xmmword ptr [rbx+0D0h], xmm0
0x180050831  mov     r8, [rbx+0A8h]; lpMem
0x180050838  test    r8, r8
0x18005083b  jz      short loc_18005084C
0x18005083d  mov     rcx, [rbx+80h]; hHeap
0x180050844  xor     edx, edx; dwFlags
0x180050846  call    cs:__imp_HeapFree
0x18005084c  xorps   xmm0, xmm0
0x18005084f  lea     rcx, [rbx+48h]
0x180050853  movups  xmmword ptr [rbx+80h], xmm0
0x18005085a  movups  xmmword ptr [rbx+90h], xmm0
0x180050861  movups  xmmword ptr [rbx+0A0h], xmm0
0x180050868  call    AslAnsiStringFree
0x18005086d  lea     rcx, [rbx+58h]; CriticalSection
0x180050871  call    cs:__imp_RtlDeleteCriticalSection
0x180050877  mov     rcx, gs:60h
0x180050880  mov     rdx, rbx
0x180050883  mov     rcx, [rcx+30h]
0x180050887  call    AslFree
0x18005088c  mov     rbx, [rsp+28h+arg_8]
0x180050891  mov     rsi, [rsp+28h+arg_10]
0x180050896  add     rsp, 20h
0x18005089a  pop     rdi
0x18005089b  retn
```
