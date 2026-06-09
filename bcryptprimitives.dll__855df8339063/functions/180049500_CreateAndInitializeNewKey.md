# CreateAndInitializeNewKey

- ea: `0x180049500`
- end: `0x1800495a6`
- name: `CreateAndInitializeNewKey`
- size: `166`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003c070`
- `0x18004a3b0`

## callees

- `0x18000ecb0`
- `0x180049500`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18004952c`
- `ntdll!RtlAllocateHeap` at `0x18004952c`

## string_xrefs

- `0x180049587`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

## pseudocode

```c
__int64 __fastcall CreateAndInitializeNewKey(__int64 a1, int a2, _QWORD *a3)
{
  _QWORD *Heap; // rax

  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x28u);
  if ( Heap )
  {
    Heap[1] = 0;
    Heap[2] = 0;
    Heap[3] = 0;
    Heap[4] = 0;
    *(_DWORD *)Heap = 40;
    *((_DWORD *)Heap + 1) = 1297306187;
    *((_DWORD *)Heap + 2) = *(_DWORD *)(a1 + 8);
    *((_DWORD *)Heap + 3) = a2;
    Heap[3] = a1;
    *a3 = Heap;
    return 0;
  }
  else
  {
    DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", 346);
    return 3221225495LL;
  }
}

```

## disassembly

```asm
0x180049500  mov     [rsp+arg_0], rbx
0x180049505  mov     [rsp+arg_8], rsi
0x18004950a  push    rdi
0x18004950b  sub     rsp, 20h
0x18004950f  mov     rbx, rcx
0x180049512  mov     rdi, r8
0x180049515  mov     rcx, gs:60h
0x18004951e  mov     esi, edx
0x180049520  xor     edx, edx; Flags
0x180049522  mov     r8d, 28h ; '('; Size
0x180049528  mov     rcx, [rcx+30h]; HeapHandle
0x18004952c  call    cs:__imp_RtlAllocateHeap
0x180049533  nop     dword ptr [rax+rax+00h]
0x180049538  test    rax, rax
0x18004953b  jz      short loc_180049581
0x18004953d  xor     ecx, ecx
0x18004953f  mov     [rax+8], rcx
0x180049543  mov     edx, ecx
0x180049545  mov     [rax+10h], rcx
0x180049549  mov     [rax+18h], rcx
0x18004954d  mov     [rax+20h], rcx
0x180049551  mov     dword ptr [rax], 28h ; '('
0x180049557  mov     dword ptr [rax+4], 4D53524Bh
0x18004955e  mov     ecx, [rbx+8]
0x180049561  mov     [rax+8], ecx
0x180049564  mov     [rax+0Ch], esi
0x180049567  mov     [rax+18h], rbx
0x18004956b  mov     [rdi], rax
0x18004956e  mov     eax, edx
0x180049570  mov     rbx, [rsp+28h+arg_0]
0x180049575  mov     rsi, [rsp+28h+arg_8]
0x18004957a  add     rsp, 20h
0x18004957e  pop     rdi
0x18004957f  retn
0x180049581  mov     r9d, 15Ah
0x180049587  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004958e  lea     rdx, aStatus; "Status"
0x180049595  mov     ecx, 0C0000017h
0x18004959a  call    DebugTraceError
0x18004959f  mov     eax, 0C0000017h
0x1800495a4  jmp     short loc_180049570
```
