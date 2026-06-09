# AslTelemetryDelete

- ea: `0x18002bbe8`
- end: `0x18002bd30`
- name: `AslTelemetryDelete`
- size: `328`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800228d4`
- `0x180022920`
- `0x18002ba70`

## callees

- `0x180001830`
- `0x18001b970`
- `0x18002979c`
- `0x18002abe4`
- `0x18002bbe8`
- `0x18002bd38`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x18002bd05`
- `ntdll!RtlDeleteCriticalSection` at `0x18002bd05`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002bca7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002bcda`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002bca7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002bcda`

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
  result = (unsigned int)_InterlockedExchangeAdd(&dword_1801228A8, 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
    result = TraceLoggingUnregister_EventUnregister(&dword_18011FF50);
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
0x18002bbe8  mov     [rsp+arg_8], rbx
0x18002bbed  mov     [rsp+arg_10], rsi
0x18002bbf2  push    rdi
0x18002bbf3  sub     rsp, 20h
0x18002bbf7  mov     rbx, rcx
0x18002bbfa  test    rcx, rcx
0x18002bbfd  jz      short loc_18002BC04
0x18002bbff  call    AslTelemetryFlush
0x18002bc04  or      eax, 0FFFFFFFFh
0x18002bc07  lock xadd cs:dword_1801228A8, eax
0x18002bc0f  cmp     eax, 1
0x18002bc12  jnz     short loc_18002BC20
0x18002bc14  lea     rcx, dword_18011FF50
0x18002bc1b  call    TraceLoggingUnregister_EventUnregister
0x18002bc20  test    rbx, rbx
0x18002bc23  jz      loc_18002BD20
0x18002bc29  mov     rcx, [rbx+0C0h]
0x18002bc30  test    rcx, rcx
0x18002bc33  jz      short loc_18002BC92
0x18002bc35  xor     esi, esi
0x18002bc37  xor     edi, edi
0x18002bc39  mov     edx, esi; unsigned __int64
0x18002bc3b  cmp     rdx, rcx
0x18002bc3e  jnb     short loc_18002BC70
0x18002bc40  mov     rcx, [rbx+0B8h]; unsigned __int64
0x18002bc47  lea     r8, [rsp+28h+arg_0]; unsigned __int64 *
0x18002bc4c  mov     [rsp+28h+arg_0], rdi
0x18002bc51  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18002bc56  test    eax, eax
0x18002bc58  js      short loc_18002BC6E
0x18002bc5a  mov     rcx, [rbx+0D8h]
0x18002bc61  mov     rdi, [rsp+28h+arg_0]
0x18002bc66  add     rdi, rcx
0x18002bc69  cmp     rdi, rcx
0x18002bc6c  jnb     short loc_18002BC70
0x18002bc6e  xor     edi, edi
0x18002bc70  lea     rcx, [rdi+8]
0x18002bc74  call    AslAnsiStringFree
0x18002bc79  lea     rcx, [rdi+18h]
0x18002bc7d  call    AslAnsiStringFree
0x18002bc82  mov     rcx, [rbx+0C0h]
0x18002bc89  inc     esi
0x18002bc8b  mov     eax, esi
0x18002bc8d  cmp     rax, rcx
0x18002bc90  jb      short loc_18002BC37
0x18002bc92  mov     r8, [rbx+0D8h]; lpMem
0x18002bc99  test    r8, r8
0x18002bc9c  jz      short loc_18002BCAD
0x18002bc9e  mov     rcx, [rbx+0B0h]; hHeap
0x18002bca5  xor     edx, edx; dwFlags
0x18002bca7  call    cs:__imp_HeapFree
0x18002bcad  xorps   xmm0, xmm0
0x18002bcb0  movups  xmmword ptr [rbx+0B0h], xmm0
0x18002bcb7  movups  xmmword ptr [rbx+0C0h], xmm0
0x18002bcbe  movups  xmmword ptr [rbx+0D0h], xmm0
0x18002bcc5  mov     r8, [rbx+0A8h]; lpMem
0x18002bccc  test    r8, r8
0x18002bccf  jz      short loc_18002BCE0
0x18002bcd1  mov     rcx, [rbx+80h]; hHeap
0x18002bcd8  xor     edx, edx; dwFlags
0x18002bcda  call    cs:__imp_HeapFree
0x18002bce0  xorps   xmm0, xmm0
0x18002bce3  lea     rcx, [rbx+48h]
0x18002bce7  movups  xmmword ptr [rbx+80h], xmm0
0x18002bcee  movups  xmmword ptr [rbx+90h], xmm0
0x18002bcf5  movups  xmmword ptr [rbx+0A0h], xmm0
0x18002bcfc  call    AslAnsiStringFree
0x18002bd01  lea     rcx, [rbx+58h]; CriticalSection
0x18002bd05  call    cs:__imp_RtlDeleteCriticalSection
0x18002bd0b  mov     rcx, gs:60h
0x18002bd14  mov     rdx, rbx
0x18002bd17  mov     rcx, [rcx+30h]
0x18002bd1b  call    AslFree
0x18002bd20  mov     rbx, [rsp+28h+arg_8]
0x18002bd25  mov     rsi, [rsp+28h+arg_10]
0x18002bd2a  add     rsp, 20h
0x18002bd2e  pop     rdi
0x18002bd2f  retn
```
