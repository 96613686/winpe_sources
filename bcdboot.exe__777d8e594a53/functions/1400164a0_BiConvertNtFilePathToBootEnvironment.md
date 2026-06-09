# BiConvertNtFilePathToBootEnvironment

- ea: `0x1400164a0`
- end: `0x1400165ad`
- name: `BiConvertNtFilePathToBootEnvironment`
- size: `269`
- prototype: `__int64 __fastcall(_DWORD *, __int64, _WORD *, unsigned int, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140015cd8`

## callees

- `0x140015cd8`
- `0x1400164a0`
- `0x140019424`
- `0x1400265e2`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x14001651b`
- `ntdll!RtlAllocateHeap` at `0x14001651b`
- `ntdll!RtlFreeHeap` at `0x140016592`
- `ntdll!RtlFreeHeap` at `0x140016592`

## pseudocode

```c
__int64 __fastcall BiConvertNtFilePathToBootEnvironment(_DWORD *a1, __int64 a2, _WORD *a3, unsigned int a4, _QWORD *a5)
{
  bool v5; // zf
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rax
  unsigned int v10; // esi
  unsigned int v11; // ebp
  _DWORD *Heap; // rax
  _DWORD *v13; // rbx
  void *Src; // [rsp+40h] [rbp+8h] BYREF

  v5 = *a1 == 6;
  Src = 0;
  if ( v5 )
    v7 = BiConvertQualifiedPartitionToBootEnvironment(a1, a2, &Src);
  else
    v7 = BiConvertNtDeviceToBootEnvironment((__int64)a1, a2, a4, &Src);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a3[v9] );
    v10 = 2 * v9 + 2;
    v11 = v10 + *((_DWORD *)Src + 2) + 12;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
    v13 = Heap;
    if ( Heap )
    {
      *Heap = 1;
      Heap[2] = 5;
      Heap[1] = v11;
      memcpy_0(Heap + 3, Src, *((unsigned int *)Src + 2));
      memcpy_0((char *)v13 + *((unsigned int *)Src + 2) + 12, a3, v10);
      *a5 = v13;
      v8 = 0;
    }
    else
    {
      v8 = -1073741670;
    }
  }
  if ( Src )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Src);
  return v8;
}

```

## disassembly

```asm
0x1400164a0  mov     r11, rsp
0x1400164a3  mov     [r11+10h], rbx
0x1400164a7  mov     [r11+18h], rbp
0x1400164ab  push    rsi
0x1400164ac  push    rdi
0x1400164ad  push    r14
0x1400164af  sub     rsp, 20h
0x1400164b3  xor     r14d, r14d
0x1400164b6  mov     eax, r9d
0x1400164b9  cmp     dword ptr [rcx], 6
0x1400164bc  mov     rdi, r8
0x1400164bf  mov     [r11+8], r14
0x1400164c3  jnz     short loc_1400164D0
0x1400164c5  lea     r8, [r11+8]
0x1400164c9  call    BiConvertQualifiedPartitionToBootEnvironment
0x1400164ce  jmp     short loc_1400164DD
0x1400164d0  lea     r9, [rsp+38h+Src]
0x1400164d5  mov     r8d, eax
0x1400164d8  call    BiConvertNtDeviceToBootEnvironment
0x1400164dd  mov     ebx, eax
0x1400164df  test    eax, eax
0x1400164e1  js      loc_140016577
0x1400164e7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400164eb  inc     rax
0x1400164ee  cmp     [rdi+rax*2], r14w
0x1400164f3  jnz     short loc_1400164EB
0x1400164f5  mov     rcx, gs:60h
0x1400164fe  lea     esi, ds:2[rax*2]
0x140016505  mov     rax, [rsp+38h+Src]
0x14001650a  xor     edx, edx; Flags
0x14001650c  mov     rcx, [rcx+30h]; HeapHandle
0x140016510  mov     ebp, [rax+8]
0x140016513  add     ebp, 0Ch
0x140016516  add     ebp, esi
0x140016518  mov     r8d, ebp; Size
0x14001651b  call    cs:__imp_RtlAllocateHeap
0x140016521  mov     rbx, rax
0x140016524  test    rax, rax
0x140016527  jnz     short loc_140016530
0x140016529  mov     ebx, 0C000009Ah
0x14001652e  jmp     short loc_140016577
0x140016530  mov     dword ptr [rax], 1
0x140016536  lea     rcx, [rax+0Ch]; void *
0x14001653a  mov     dword ptr [rax+8], 5
0x140016541  mov     [rax+4], ebp
0x140016544  mov     rdx, [rsp+38h+Src]; Src
0x140016549  mov     r8d, [rdx+8]; Size
0x14001654d  call    memcpy_0
0x140016552  mov     rax, [rsp+38h+Src]
0x140016557  mov     rdx, rdi; Src
0x14001655a  mov     r8d, esi; Size
0x14001655d  mov     ecx, [rax+8]
0x140016560  add     rcx, 0Ch
0x140016564  add     rcx, rbx; void *
0x140016567  call    memcpy_0
0x14001656c  mov     rax, [rsp+38h+arg_20]
0x140016571  mov     [rax], rbx
0x140016574  mov     ebx, r14d
0x140016577  cmp     [rsp+38h+Src], r14
0x14001657c  jz      short loc_140016598
0x14001657e  mov     rcx, gs:60h
0x140016587  xor     edx, edx; Flags
0x140016589  mov     r8, [rsp+38h+Src]; P
0x14001658e  mov     rcx, [rcx+30h]; HeapHandle
0x140016592  call    cs:__imp_RtlFreeHeap
0x140016598  mov     rbp, [rsp+38h+arg_10]
0x14001659d  mov     eax, ebx
0x14001659f  mov     rbx, [rsp+38h+arg_8]
0x1400165a4  add     rsp, 20h
0x1400165a8  pop     r14
0x1400165aa  pop     rdi
0x1400165ab  pop     rsi
0x1400165ac  retn
```
