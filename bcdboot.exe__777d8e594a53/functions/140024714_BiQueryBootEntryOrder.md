# BiQueryBootEntryOrder

- ea: `0x140024714`
- end: `0x140024834`
- name: `BiQueryBootEntryOrder`
- size: `288`
- prototype: `__int64 __fastcall(_QWORD *, unsigned int *)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140021b04`
- `0x140021c10`
- `0x1400232c4`
- `0x140023824`
- `0x14002496c`

## callees

- `0x1400133e4`
- `0x140020678`
- `0x14002166c`
- `0x140021888`
- `0x140024714`
- `0x140027010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1400247ad`
- `ntdll!RtlAllocateHeap` at `0x1400247ad`
- `ntdll!RtlFreeHeap` at `0x140024809`
- `ntdll!RtlFreeHeap` at `0x140024809`

## pseudocode

```c
__int64 __fastcall BiQueryBootEntryOrder(_QWORD *a1, unsigned int *a2)
{
  NTSTATUS v4; // ebx
  void *v5; // rdi
  PVOID Heap; // rax
  _QWORD v8[5]; // [rsp+20h] [rbp-28h] BYREF
  unsigned int v9; // [rsp+60h] [rbp+18h] BYREF
  __int64 (__fastcall *v10)(PVOID, unsigned int *); // [rsp+68h] [rbp+20h] BYREF

  v10 = 0;
  v8[0] = 0;
  v9 = 0;
  if ( (int)BiLookupNtdllProcedureAddress("ZwQueryBootEntryOrder", (PVOID *)&v10) >= 0 )
  {
    v4 = BiAcquirePrivilege(0x16u, (__int64)v8);
    if ( v4 < 0 )
      return (unsigned int)v4;
    v4 = v10(0, &v9);
    if ( v4 == -1073741789 )
    {
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 4LL * v9);
      v5 = Heap;
      if ( !Heap )
      {
        v4 = -1073741670;
LABEL_13:
        BiReleasePrivilege(v8);
        return (unsigned int)v4;
      }
      v4 = v10(Heap, &v9);
      if ( v4 >= 0 )
      {
LABEL_12:
        *a2 = v9;
        *a1 = v5;
        goto LABEL_13;
      }
    }
    else
    {
      v5 = 0;
    }
    BiLogMessage(4, L"Failed to query boot entry order. Status: %x", (unsigned int)v4);
    if ( v4 < 0 )
    {
      if ( v5 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
      goto LABEL_13;
    }
    goto LABEL_12;
  }
  return (unsigned int)-1073741637;
}

```

## disassembly

```asm
0x140024714  mov     rax, rsp
0x140024717  mov     [rax+8], rbx
0x14002471b  push    rsi
0x14002471c  push    rdi
0x14002471d  push    r14
0x14002471f  sub     rsp, 30h
0x140024723  mov     rsi, rdx
0x140024726  mov     qword ptr [rax+20h], 0
0x14002472e  mov     r14, rcx
0x140024731  mov     qword ptr [rax-28h], 0
0x140024739  lea     rdx, [rax+20h]
0x14002473d  mov     dword ptr [rax+18h], 0
0x140024744  lea     rcx, aZwquerybootent; "ZwQueryBootEntryOrder"
0x14002474b  call    BiLookupNtdllProcedureAddress
0x140024750  test    eax, eax
0x140024752  jns     short loc_14002475E
0x140024754  mov     ebx, 0C00000BBh
0x140024759  jmp     loc_140024824
0x14002475e  lea     rdx, [rsp+48h+var_28]
0x140024763  mov     ecx, 16h
0x140024768  call    BiAcquirePrivilege
0x14002476d  mov     ebx, eax
0x14002476f  test    eax, eax
0x140024771  js      loc_140024824
0x140024777  mov     rax, [rsp+48h+arg_18]
0x14002477c  lea     rdx, [rsp+48h+arg_10]
0x140024781  xor     ecx, ecx
0x140024783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024788  mov     ebx, eax
0x14002478a  cmp     eax, 0C0000023h
0x14002478f  jz      short loc_140024795
0x140024791  xor     edi, edi
0x140024793  jmp     short loc_1400247DA
0x140024795  mov     rcx, gs:60h
0x14002479e  xor     edx, edx; Flags
0x1400247a0  mov     r8d, [rsp+48h+arg_10]
0x1400247a5  shl     r8, 2; Size
0x1400247a9  mov     rcx, [rcx+30h]; HeapHandle
0x1400247ad  call    cs:__imp_RtlAllocateHeap
0x1400247b3  mov     rdi, rax
0x1400247b6  test    rax, rax
0x1400247b9  jnz     short loc_1400247C2
0x1400247bb  mov     ebx, 0C000009Ah
0x1400247c0  jmp     short loc_14002481A
0x1400247c2  mov     rcx, rax
0x1400247c5  lea     rdx, [rsp+48h+arg_10]
0x1400247ca  mov     rax, [rsp+48h+arg_18]
0x1400247cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400247d4  mov     ebx, eax
0x1400247d6  test    eax, eax
0x1400247d8  jns     short loc_140024811
0x1400247da  lea     rdx, aFailedToQueryB; "Failed to query boot entry order. Statu"...
0x1400247e1  mov     ecx, 4
0x1400247e6  mov     r8d, ebx
0x1400247e9  call    BiLogMessage
0x1400247ee  test    ebx, ebx
0x1400247f0  jns     short loc_140024811
0x1400247f2  test    rdi, rdi
0x1400247f5  jz      short loc_14002481A
0x1400247f7  mov     rcx, gs:60h
0x140024800  mov     r8, rdi; P
0x140024803  xor     edx, edx; Flags
0x140024805  mov     rcx, [rcx+30h]; HeapHandle
0x140024809  call    cs:__imp_RtlFreeHeap
0x14002480f  jmp     short loc_14002481A
0x140024811  mov     eax, [rsp+48h+arg_10]
0x140024815  mov     [rsi], eax
0x140024817  mov     [r14], rdi
0x14002481a  lea     rcx, [rsp+48h+var_28]
0x14002481f  call    BiReleasePrivilege
0x140024824  mov     eax, ebx
0x140024826  mov     rbx, [rsp+48h+arg_0]
0x14002482b  add     rsp, 30h
0x14002482f  pop     r14
0x140024831  pop     rdi
0x140024832  pop     rsi
0x140024833  retn
```
