# BaseSrvAddSepWowTask

- ea: `0x180008394`
- end: `0x180008522`
- name: `BaseSrvAddSepWowTask`
- size: `398`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x1800086cc`

## callees

- `0x18000835c`
- `0x180008394`
- `0x1800087b0`
- `0x18000a898`
- `0x18000b750`
- `0x18000db05`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000849a`
- `ntdll!RtlAllocateHeap` at `0x18000849a`
- `ntdll!RtlFreeHeap` at `0x180008418`
- `ntdll!RtlFreeHeap` at `0x18000846f`
- `ntdll!RtlFreeHeap` at `0x180008418`
- `ntdll!RtlFreeHeap` at `0x18000846f`

## pseudocode

```c
__int64 __fastcall BaseSrvAddSepWowTask(__int64 a1, __int64 a2)
{
  __int64 DOSRecord; // rbx
  int v6; // ebp
  void *v7; // r8
  __int64 v8; // rdi
  _BYTE *i; // rax
  void *v10; // r8
  unsigned int v11; // r15d
  PVOID Heap; // rax

  if ( *(_DWORD *)(a1 + 104) != 148 )
    return 3221225485LL;
  if ( !*(_QWORD *)(a2 + 88) )
    *(_QWORD *)(a2 + 88) = *(_QWORD *)(a1 + 152);
  if ( *(_DWORD *)a1 == -1 )
  {
    DOSRecord = BaseSrvAllocateDOSRecord();
    if ( !DOSRecord )
      return 3221225632LL;
    *(_DWORD *)(DOSRecord + 40) = BaseSrvGetWOWTaskId();
    v6 = 1;
    *(_DWORD *)(DOSRecord + 8) = 2;
  }
  else
  {
    DOSRecord = *(_QWORD *)(a2 + 72);
    v6 = 0;
  }
  v7 = *(void **)(DOSRecord + 56);
  if ( v7 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
    *(_QWORD *)(DOSRecord + 56) = 0;
  }
  v8 = *(_QWORD *)(a1 + 96);
  for ( i = (_BYTE *)(v8 + 17); *i; ++i )
  {
    if ( (unsigned __int64)i >= v8 + 144 )
      break;
  }
  v10 = *(void **)(DOSRecord + 56);
  v11 = (_DWORD)i - v8 - 16;
  if ( v10 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, BaseSrvTag + 0x40000, v11);
  *(_QWORD *)(DOSRecord + 56) = Heap;
  if ( !Heap )
  {
    if ( v6 )
      BaseSrvFreeDOSRecord(DOSRecord);
    return 3221225632LL;
  }
  *(_DWORD *)(DOSRecord + 44) = *(_DWORD *)v8;
  *(_WORD *)(DOSRecord + 48) = *(_WORD *)(v8 + 4);
  *(_WORD *)(DOSRecord + 50) = *(_WORD *)(v8 + 6);
  *(_QWORD *)(DOSRecord + 64) = *(_QWORD *)(v8 + 8);
  *(_BYTE *)(DOSRecord + 72) = *(_BYTE *)(v8 + 16);
  memcpy_0(Heap, (const void *)(v8 + 17), v11);
  *(_BYTE *)(v11 - 1 + *(_QWORD *)(DOSRecord + 56)) = 0;
  if ( v6 )
    BaseSrvAddDOSRecord(a2, DOSRecord);
  return 0;
}

```

## disassembly

```asm
0x180008394  push    rbx
0x180008396  push    rbp
0x180008397  push    rsi
0x180008398  push    rdi
0x180008399  push    r12
0x18000839b  push    r14
0x18000839d  push    r15
0x18000839f  sub     rsp, 20h
0x1800083a3  cmp     dword ptr [rcx+68h], 94h
0x1800083aa  mov     rsi, rdx
0x1800083ad  mov     rdi, rcx
0x1800083b0  jz      short loc_1800083BC
0x1800083b2  mov     eax, 0C000000Dh
0x1800083b7  jmp     loc_180008512
0x1800083bc  cmp     qword ptr [rdx+58h], 0
0x1800083c1  jnz     short loc_1800083CE
0x1800083c3  mov     rax, [rcx+98h]
0x1800083ca  mov     [rdx+58h], rax
0x1800083ce  cmp     dword ptr [rcx], 0FFFFFFFFh
0x1800083d1  jnz     short loc_1800083FA
0x1800083d3  call    BaseSrvAllocateDOSRecord
0x1800083d8  mov     rbx, rax
0x1800083db  test    rax, rax
0x1800083de  jz      loc_1800084BE
0x1800083e4  call    BaseSrvGetWOWTaskId
0x1800083e9  mov     [rbx+28h], eax
0x1800083ec  mov     ebp, 1
0x1800083f1  mov     dword ptr [rbx+8], 2
0x1800083f8  jmp     short loc_180008400
0x1800083fa  mov     rbx, [rdx+48h]
0x1800083fe  xor     ebp, ebp
0x180008400  mov     r8, [rbx+38h]; P
0x180008404  test    r8, r8
0x180008407  jz      short loc_18000842C
0x180008409  mov     rcx, gs:60h
0x180008412  xor     edx, edx; Flags
0x180008414  mov     rcx, [rcx+30h]; HeapHandle
0x180008418  call    cs:__imp_RtlFreeHeap
0x18000841f  nop     dword ptr [rax+rax+00h]
0x180008424  mov     qword ptr [rbx+38h], 0
0x18000842c  mov     rdi, [rdi+60h]
0x180008430  lea     r14, [rdi+11h]
0x180008434  cmp     byte ptr [r14], 0
0x180008438  mov     rax, r14
0x18000843b  jz      short loc_180008451
0x18000843d  lea     rcx, [rdi+90h]
0x180008444  cmp     rax, rcx
0x180008447  jnb     short loc_180008451
0x180008449  inc     rax
0x18000844c  cmp     byte ptr [rax], 0
0x18000844f  jnz     short loc_180008444
0x180008451  mov     r8, [rbx+38h]; P
0x180008455  sub     eax, edi
0x180008457  lea     r15d, [rax-10h]
0x18000845b  test    r8, r8
0x18000845e  jz      short loc_18000847B
0x180008460  mov     rcx, gs:60h
0x180008469  xor     edx, edx; Flags
0x18000846b  mov     rcx, [rcx+30h]; HeapHandle
0x18000846f  call    cs:__imp_RtlFreeHeap
0x180008476  nop     dword ptr [rax+rax+00h]
0x18000847b  mov     rcx, gs:60h
0x180008484  mov     edx, cs:BaseSrvTag
0x18000848a  add     edx, 40000h; Flags
0x180008490  mov     r8d, r15d; Size
0x180008493  mov     r12d, r15d
0x180008496  mov     rcx, [rcx+30h]; HeapHandle
0x18000849a  call    cs:__imp_RtlAllocateHeap
0x1800084a1  nop     dword ptr [rax+rax+00h]
0x1800084a6  mov     [rbx+38h], rax
0x1800084aa  mov     rcx, rax; void *
0x1800084ad  test    rax, rax
0x1800084b0  jnz     short loc_1800084C5
0x1800084b2  test    ebp, ebp
0x1800084b4  jz      short loc_1800084BE
0x1800084b6  mov     rcx, rbx
0x1800084b9  call    BaseSrvFreeDOSRecord
0x1800084be  mov     eax, 0C00000A0h
0x1800084c3  jmp     short loc_180008512
0x1800084c5  mov     eax, [rdi]
0x1800084c7  mov     r8, r12; Size
0x1800084ca  mov     [rbx+2Ch], eax
0x1800084cd  mov     rdx, r14; Src
0x1800084d0  movzx   eax, word ptr [rdi+4]
0x1800084d4  mov     [rbx+30h], ax
0x1800084d8  movzx   eax, word ptr [rdi+6]
0x1800084dc  mov     [rbx+32h], ax
0x1800084e0  movsd   xmm0, qword ptr [rdi+8]
0x1800084e5  movsd   qword ptr [rbx+40h], xmm0
0x1800084ea  mov     al, [rdi+10h]
0x1800084ed  mov     [rbx+48h], al
0x1800084f0  call    memcpy_0
0x1800084f5  mov     rax, [rbx+38h]
0x1800084f9  lea     ecx, [r15-1]
0x1800084fd  mov     byte ptr [rcx+rax], 0
0x180008501  test    ebp, ebp
0x180008503  jz      short loc_180008510
0x180008505  mov     rdx, rbx
0x180008508  mov     rcx, rsi
0x18000850b  call    BaseSrvAddDOSRecord
0x180008510  xor     eax, eax
0x180008512  add     rsp, 20h
0x180008516  pop     r15
0x180008518  pop     r14
0x18000851a  pop     r12
0x18000851c  pop     rdi
0x18000851d  pop     rsi
0x18000851e  pop     rbp
0x18000851f  pop     rbx
0x180008520  retn
```
