# CTClockSubordinate<__int64,__int64>::~CTClockSubordinate<__int64,__int64>(void)

- ea: `0x1800254b8`
- end: `0x180025569`
- name: `??1?$CTClockSubordinate@_J_J@@QEAA@XZ`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180025570`

## callees

- `0x180001048`
- `0x180010ea8`
- `0x1800254b8`
- `0x1800270f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180025547`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180025547`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180025562`
- `KERNEL32!DeleteCriticalSection` at `0x1800254ff`
- `KERNEL32!DeleteCriticalSection` at `0x1800254ff`

## pseudocode

```c
void __fastcall CTClockSubordinate<__int64,__int64>::~CTClockSubordinate<__int64,__int64>(__int64 a1)
{
  volatile signed __int32 *v2; // rdi
  __int64 **v3; // rdi
  __int64 *v4; // rcx
  __int64 v5; // rdx
  __int64 *v6; // rax
  int v7; // edi

  CTClockSubordinate<__int64,__int64>::Reset(a1);
  v2 = *(volatile signed __int32 **)(a1 + 152);
  if ( _InterlockedExchangeAdd(v2 + 10, 0xFFFFFFFF) == 1 && v2 )
  {
    CMpeg2Stats::~CMpeg2Stats((CMpeg2Stats *)v2);
    operator delete((void *)v2, 0x2530u);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 160));
  v3 = (__int64 **)(a1 + 40);
  while ( 1 )
  {
    v4 = *v3;
    if ( *v3 == (__int64 *)v3 )
      break;
    v5 = *v4;
    v6 = (__int64 *)v4[1];
    *v6 = *v4;
    *(_QWORD *)(v5 + 8) = v6;
    operator delete(v4, 0x5B8u);
  }
  v7 = 0;
  for ( *(_QWORD *)a1 = &CTDynArray<CTClockSubordinate<__int64,__int64>::CLOCK_SUBORDINATE_BRACKET *>::`vftable';
        v7 < *(_DWORD *)(a1 + 20);
        ++v7 )
  {
    free(*(void **)(*(_QWORD *)(a1 + 8) + 8LL * v7));
  }
  free(*(void **)(a1 + 8));
}

```

## disassembly

```asm
0x1800254b8  mov     [rsp+arg_8], rbx
0x1800254bd  push    rdi
0x1800254be  sub     rsp, 20h
0x1800254c2  mov     rbx, rcx
0x1800254c5  call    ?Reset@?$CTClockSubordinate@_J_J@@QEAAXH@Z; CTClockSubordinate<__int64,__int64>::Reset(int)
0x1800254ca  mov     rdi, [rbx+98h]
0x1800254d1  or      eax, 0FFFFFFFFh
0x1800254d4  lock xadd [rdi+28h], eax
0x1800254d9  cmp     eax, 1
0x1800254dc  jnz     short loc_1800254F8
0x1800254de  test    rdi, rdi
0x1800254e1  jz      short loc_1800254F8
0x1800254e3  mov     rcx, rdi; this
0x1800254e6  call    ??1CMpeg2Stats@@QEAA@XZ; CMpeg2Stats::~CMpeg2Stats(void)
0x1800254eb  mov     edx, 2530h; unsigned __int64
0x1800254f0  mov     rcx, rdi; void *
0x1800254f3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800254f8  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x1800254ff  call    cs:__imp_DeleteCriticalSection
0x180025505  lea     rdi, [rbx+28h]
0x180025509  mov     rcx, [rdi]; void *
0x18002550c  cmp     rcx, rdi
0x18002550f  jz      short loc_18002552B
0x180025511  mov     rdx, [rcx]
0x180025514  mov     rax, [rcx+8]
0x180025518  mov     [rax], rdx
0x18002551b  mov     [rdx+8], rax
0x18002551f  mov     edx, 5B8h; unsigned __int64
0x180025524  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180025529  jmp     short loc_180025509
0x18002552b  xor     edi, edi
0x18002552d  lea     rax, ??_7?$CTDynArray@PEAUCLOCK_SUBORDINATE_BRACKET@?$CTClockSubordinate@_J_J@@@@6B@; const CTDynArray<CTClockSubordinate<__int64,__int64>::CLOCK_SUBORDINATE_BRACKET *>::`vftable'
0x180025534  mov     [rbx], rax
0x180025537  cmp     [rbx+14h], edi
0x18002553a  jle     short loc_180025554
0x18002553c  mov     rcx, [rbx+8]
0x180025540  movsxd  rax, edi
0x180025543  mov     rcx, [rcx+rax*8]; Block
0x180025547  call    cs:__imp_free
0x18002554d  inc     edi
0x18002554f  cmp     edi, [rbx+14h]
0x180025552  jl      short loc_18002553C
0x180025554  mov     rcx, [rbx+8]
0x180025558  mov     rbx, [rsp+28h+arg_8]
0x18002555d  add     rsp, 20h
0x180025561  pop     rdi
0x180025562  jmp     cs:__imp_free
```
