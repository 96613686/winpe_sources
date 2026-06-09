# worker_start

- ea: `0x1800262c0`
- end: `0x180026456`
- name: `worker_start`
- size: `406`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180022090`
- `0x180022110`
- `0x180025e40`
- `0x1800262c0`
- `0x18002bfd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026326`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026372`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026403`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026326`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026372`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026403`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800262e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026354`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026383`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800262e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026354`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026383`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026421`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026421`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x1800262ff`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180026369`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x1800263f2`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x1800262ff`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180026369`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x1800263f2`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableCS` at `0x18002631b`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableCS` at `0x18002631b`

## pseudocode

```c
__int64 __fastcall worker_start(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  int v3; // edi
  __int64 v4; // rcx
  __int64 v6; // [rsp+40h] [rbp+8h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)(a1 + 440);
  while ( 1 )
  {
    EnterCriticalSection(v2);
    while ( 1 )
    {
      if ( *(_DWORD *)a1 == 3 )
      {
        *(_DWORD *)a1 = 0;
        WakeConditionVariable((PCONDITION_VARIABLE)(a1 + 480));
      }
      v3 = *(_DWORD *)a1;
      if ( *(_DWORD *)a1 )
        break;
      SleepConditionVariableCS((PCONDITION_VARIABLE)(a1 + 480), v2, 0xFFFFFFFF);
    }
    LeaveCriticalSection(v2);
    v6 = 0;
    if ( v3 <= 2 )
      v3 = worker_encode(a1, &v6, (unsigned int)v3);
    if ( v3 == 4 )
      break;
    EnterCriticalSection(v2);
    if ( *(_DWORD *)a1 != 4 )
    {
      *(_DWORD *)a1 = 0;
      WakeConditionVariable((PCONDITION_VARIABLE)(a1 + 480));
    }
    LeaveCriticalSection(v2);
    EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(a1 + 32) + 472LL));
    if ( v3 == 2 )
    {
      *(_QWORD *)(*(_QWORD *)(a1 + 24) + 24LL) = v6;
      *(_BYTE *)(*(_QWORD *)(a1 + 24) + 40LL) = 1;
    }
    *(_QWORD *)(*(_QWORD *)(a1 + 32) + 456LL) += *(_QWORD *)(*(_QWORD *)(a1 + 24) + 56LL);
    *(_QWORD *)(*(_QWORD *)(a1 + 32) + 464LL) += v6;
    v4 = *(_QWORD *)(a1 + 32);
    *(_QWORD *)(a1 + 48) = 0;
    *(_QWORD *)(a1 + 56) = 0;
    *(_QWORD *)(a1 + 432) = *(_QWORD *)(v4 + 440);
    *(_QWORD *)(v4 + 440) = a1;
    WakeConditionVariable((PCONDITION_VARIABLE)(*(_QWORD *)(a1 + 32) + 512LL));
    LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(a1 + 32) + 472LL));
  }
  lzma_filters_free(a1 + 352, *(_QWORD *)(a1 + 40));
  DeleteCriticalSection(v2);
  lzma_next_end(a1 + 64, *(_QWORD *)(a1 + 40));
  lzma_free(*(_QWORD *)(a1 + 8), *(_QWORD *)(a1 + 40));
  return 0;
}

```

## disassembly

```asm
0x1800262c0  mov     [rsp+arg_8], rbx
0x1800262c5  mov     [rsp+arg_10], rbp
0x1800262ca  push    rsi
0x1800262cb  push    rdi
0x1800262cc  push    r14
0x1800262ce  sub     rsp, 20h
0x1800262d2  mov     rbx, rcx
0x1800262d5  lea     rbp, [rcx+1B8h]
0x1800262dc  xor     r14d, r14d
0x1800262df  nop
0x1800262e0  mov     rcx, rbp; lpCriticalSection
0x1800262e3  call    cs:__imp_EnterCriticalSection
0x1800262e9  nop     dword ptr [rax+00000000h]
0x1800262f0  cmp     dword ptr [rbx], 3
0x1800262f3  jnz     short loc_180026305
0x1800262f5  lea     rcx, [rbx+1E0h]; ConditionVariable
0x1800262fc  mov     [rbx], r14d
0x1800262ff  call    cs:__imp_WakeConditionVariable
0x180026305  mov     edi, [rbx]
0x180026307  test    edi, edi
0x180026309  jnz     short loc_180026323
0x18002630b  mov     r8d, 0FFFFFFFFh; dwMilliseconds
0x180026311  lea     rcx, [rbx+1E0h]; ConditionVariable
0x180026318  mov     rdx, rbp; CriticalSection
0x18002631b  call    cs:__imp_SleepConditionVariableCS
0x180026321  jmp     short loc_1800262F0
0x180026323  mov     rcx, rbp; lpCriticalSection
0x180026326  call    cs:__imp_LeaveCriticalSection
0x18002632c  mov     [rsp+38h+arg_0], r14
0x180026331  cmp     edi, 2
0x180026334  jg      short loc_180026348
0x180026336  mov     r8d, edi
0x180026339  lea     rdx, [rsp+38h+arg_0]
0x18002633e  mov     rcx, rbx
0x180026341  call    worker_encode
0x180026346  mov     edi, eax
0x180026348  cmp     edi, 4
0x18002634b  jz      loc_18002640E
0x180026351  mov     rcx, rbp; lpCriticalSection
0x180026354  call    cs:__imp_EnterCriticalSection
0x18002635a  cmp     dword ptr [rbx], 4
0x18002635d  jz      short loc_18002636F
0x18002635f  lea     rcx, [rbx+1E0h]; ConditionVariable
0x180026366  mov     [rbx], r14d
0x180026369  call    cs:__imp_WakeConditionVariable
0x18002636f  mov     rcx, rbp; lpCriticalSection
0x180026372  call    cs:__imp_LeaveCriticalSection
0x180026378  mov     rcx, [rbx+20h]
0x18002637c  add     rcx, 1D8h; lpCriticalSection
0x180026383  call    cs:__imp_EnterCriticalSection
0x180026389  cmp     edi, 2
0x18002638c  jnz     short loc_1800263A3
0x18002638e  mov     rax, [rsp+38h+arg_0]
0x180026393  mov     rcx, [rbx+18h]
0x180026397  mov     [rcx+18h], rax
0x18002639b  mov     rax, [rbx+18h]
0x18002639f  mov     byte ptr [rax+28h], 1
0x1800263a3  mov     rax, [rbx+18h]
0x1800263a7  mov     rdx, [rbx+20h]
0x1800263ab  mov     rcx, [rax+38h]
0x1800263af  add     [rdx+1C8h], rcx
0x1800263b6  mov     rcx, [rbx+20h]
0x1800263ba  mov     rax, [rsp+38h+arg_0]
0x1800263bf  add     [rcx+1D0h], rax
0x1800263c6  mov     rcx, [rbx+20h]
0x1800263ca  mov     [rbx+30h], r14
0x1800263ce  mov     [rbx+38h], r14
0x1800263d2  mov     rax, [rcx+1B8h]
0x1800263d9  mov     [rbx+1B0h], rax
0x1800263e0  mov     [rcx+1B8h], rbx
0x1800263e7  mov     rcx, [rbx+20h]
0x1800263eb  add     rcx, 200h; ConditionVariable
0x1800263f2  call    cs:__imp_WakeConditionVariable
0x1800263f8  mov     rcx, [rbx+20h]
0x1800263fc  add     rcx, 1D8h; lpCriticalSection
0x180026403  call    cs:__imp_LeaveCriticalSection
0x180026409  jmp     loc_1800262E0
0x18002640e  mov     rdx, [rbx+28h]
0x180026412  lea     rcx, [rbx+160h]
0x180026419  call    lzma_filters_free
0x18002641e  mov     rcx, rbp; lpCriticalSection
0x180026421  call    cs:__imp_DeleteCriticalSection
0x180026427  mov     rdx, [rbx+28h]
0x18002642b  lea     rcx, [rbx+40h]
0x18002642f  call    lzma_next_end
0x180026434  mov     rdx, [rbx+28h]
0x180026438  mov     rcx, [rbx+8]
0x18002643c  call    lzma_free
0x180026441  mov     rbx, [rsp+38h+arg_8]
0x180026446  xor     eax, eax
0x180026448  mov     rbp, [rsp+38h+arg_10]
0x18002644d  add     rsp, 20h
0x180026451  pop     r14
0x180026453  pop     rdi
0x180026454  pop     rsi
0x180026455  retn
```
