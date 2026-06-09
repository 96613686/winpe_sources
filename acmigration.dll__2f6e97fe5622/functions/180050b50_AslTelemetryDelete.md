# AslTelemetryDelete

- ea: `0x180050b50`
- end: `0x180050c9f`
- name: `AslTelemetryDelete`
- size: `335`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000aa40`
- `0x1800509d0`
- `0x180069110`

## callees

- `0x180050b50`
- `0x180050ca8`
- `0x18005453c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180050c13`
- `KERNEL32!HeapFree` at `0x180050c46`
- `KERNEL32!HeapFree` at `0x180050c13`
- `KERNEL32!HeapFree` at `0x180050c46`
- `ntdll!RtlDeleteCriticalSection` at `0x180050c71`
- `ntdll!RtlDeleteCriticalSection` at `0x180050c71`
- `ntdll!RtlFreeHeap` at `0x180050c89`
- `ntdll!RtlFreeHeap` at `0x180050c89`
- `ADVAPI32!EventUnregister` at `0x180050b98`
- `ADVAPI32!EventUnregister` at `0x180050b98`

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
  v2 = _InterlockedExchangeAdd(&dword_180097B18, 0xFFFFFFFF);
  if ( v2 == 1 )
  {
    v3 = qword_180096998;
    dword_180096978 = 0;
    qword_180096998 = 0;
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
0x180050b50  mov     [rsp+arg_8], rbx
0x180050b55  mov     [rsp+arg_10], rsi
0x180050b5a  push    rdi
0x180050b5b  sub     rsp, 20h
0x180050b5f  mov     rbx, rcx
0x180050b62  test    rcx, rcx
0x180050b65  jz      short loc_180050B6C
0x180050b67  call    AslTelemetryFlush
0x180050b6c  or      eax, 0FFFFFFFFh
0x180050b6f  lock xadd cs:dword_180097B18, eax
0x180050b77  cmp     eax, 1
0x180050b7a  jnz     short loc_180050B9E
0x180050b7c  mov     rcx, cs:qword_180096998; RegHandle
0x180050b83  mov     cs:dword_180096978, 0
0x180050b8d  mov     cs:qword_180096998, 0
0x180050b98  call    cs:__imp_EventUnregister
0x180050b9e  test    rbx, rbx
0x180050ba1  jz      loc_180050C8F
0x180050ba7  mov     rcx, [rbx+0C0h]
0x180050bae  test    rcx, rcx
0x180050bb1  jz      short loc_180050BFE
0x180050bb3  xor     esi, esi
0x180050bb5  xor     edi, edi
0x180050bb7  mov     eax, esi
0x180050bb9  cmp     rax, rcx
0x180050bbc  jnb     short loc_180050BDC
0x180050bbe  mul     qword ptr [rbx+0B8h]
0x180050bc5  test    rdx, rdx
0x180050bc8  jnz     short loc_180050BDA
0x180050bca  mov     rcx, [rbx+0D8h]
0x180050bd1  lea     rdi, [rcx+rax]
0x180050bd5  cmp     rdi, rcx
0x180050bd8  jnb     short loc_180050BDC
0x180050bda  xor     edi, edi
0x180050bdc  lea     rcx, [rdi+8]
0x180050be0  call    AslAnsiStringFree
0x180050be5  lea     rcx, [rdi+18h]
0x180050be9  call    AslAnsiStringFree
0x180050bee  mov     rcx, [rbx+0C0h]
0x180050bf5  inc     esi
0x180050bf7  mov     eax, esi
0x180050bf9  cmp     rax, rcx
0x180050bfc  jb      short loc_180050BB5
0x180050bfe  mov     r8, [rbx+0D8h]; lpMem
0x180050c05  test    r8, r8
0x180050c08  jz      short loc_180050C19
0x180050c0a  mov     rcx, [rbx+0B0h]; hHeap
0x180050c11  xor     edx, edx; dwFlags
0x180050c13  call    cs:__imp_HeapFree
0x180050c19  xorps   xmm0, xmm0
0x180050c1c  movups  xmmword ptr [rbx+0B0h], xmm0
0x180050c23  movups  xmmword ptr [rbx+0C0h], xmm0
0x180050c2a  movups  xmmword ptr [rbx+0D0h], xmm0
0x180050c31  mov     r8, [rbx+0A8h]; lpMem
0x180050c38  test    r8, r8
0x180050c3b  jz      short loc_180050C4C
0x180050c3d  mov     rcx, [rbx+80h]; hHeap
0x180050c44  xor     edx, edx; dwFlags
0x180050c46  call    cs:__imp_HeapFree
0x180050c4c  xorps   xmm0, xmm0
0x180050c4f  lea     rcx, [rbx+48h]
0x180050c53  movups  xmmword ptr [rbx+80h], xmm0
0x180050c5a  movups  xmmword ptr [rbx+90h], xmm0
0x180050c61  movups  xmmword ptr [rbx+0A0h], xmm0
0x180050c68  call    AslAnsiStringFree
0x180050c6d  lea     rcx, [rbx+58h]; CriticalSection
0x180050c71  call    cs:__imp_RtlDeleteCriticalSection
0x180050c77  mov     rcx, gs:60h
0x180050c80  mov     r8, rbx; P
0x180050c83  xor     edx, edx; Flags
0x180050c85  mov     rcx, [rcx+30h]; HeapHandle
0x180050c89  call    cs:__imp_RtlFreeHeap
0x180050c8f  mov     rbx, [rsp+28h+arg_8]
0x180050c94  mov     rsi, [rsp+28h+arg_10]
0x180050c99  add     rsp, 20h
0x180050c9d  pop     rdi
0x180050c9e  retn
```
