# BaseSrvAddSharedWowTask

- ea: `0x18000821c`
- end: `0x1800083ae`
- name: `BaseSrvAddSharedWowTask`
- size: `402`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x1800083dc`

## callees

- `0x18000821c`
- `0x1800083b4`
- `0x1800085bc`
- `0x18000a894`
- `0x18000d6fb`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800082f6`
- `ntdll!RtlAllocateHeap` at `0x1800082f6`
- `ntdll!RtlFreeHeap` at `0x1800082cb`
- `ntdll!RtlFreeHeap` at `0x1800082cb`

## pseudocode

```c
__int64 __fastcall BaseSrvAddSharedWowTask(__int64 a1, __int64 a2)
{
  int v2; // r14d
  __int64 WOWRecord; // rax
  __int64 i; // rbx
  __int64 v7; // rsi
  _BYTE *j; // rdi
  void *v9; // r8
  unsigned int v10; // edi
  PVOID Heap; // rax

  v2 = 0;
  if ( *(_DWORD *)(a1 + 104) != 148 )
    return 3221225485LL;
  if ( !*(_QWORD *)(a2 + 88) )
    *(_QWORD *)(a2 + 88) = *(_QWORD *)(a1 + 152);
  if ( *(_DWORD *)a1 != -1 )
  {
    for ( i = *(_QWORD *)(a2 + 56); i; i = *(_QWORD *)(i + 32) )
    {
      if ( *(_DWORD *)i == *(_DWORD *)a1 )
        goto LABEL_7;
    }
    return 3221225485LL;
  }
  WOWRecord = BaseSrvAllocateWOWRecord();
  i = WOWRecord;
  if ( !WOWRecord )
    return 3221225632LL;
  *(_DWORD *)(WOWRecord + 4) = 1;
  v2 = 1;
LABEL_7:
  v7 = *(_QWORD *)(a1 + 96);
  *(_DWORD *)a1 = *(_DWORD *)i;
  for ( j = (_BYTE *)(v7 + 17); *j; ++j )
  {
    if ( (unsigned __int64)j >= v7 + 144 )
      break;
  }
  v9 = *(void **)(i + 48);
  v10 = (_DWORD)j - v7 - 16;
  if ( v9 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, BaseSrvTag + 0x40000, v10);
  *(_QWORD *)(i + 48) = Heap;
  if ( !Heap )
  {
    if ( v2 )
      BaseSrvFreeWOWRecord((PVOID)i);
    return 3221225632LL;
  }
  *(_DWORD *)(i + 40) = *(_DWORD *)v7;
  *(_WORD *)(i + 44) = *(_WORD *)(v7 + 4);
  *(_WORD *)(i + 46) = *(_WORD *)(v7 + 6);
  *(_QWORD *)(i + 56) = *(_QWORD *)(v7 + 8);
  *(_BYTE *)(i + 64) = *(_BYTE *)(v7 + 16);
  memcpy_0(Heap, (const void *)(v7 + 17), v10);
  *(_BYTE *)(v10 - 1 + *(_QWORD *)(i + 48)) = 0;
  if ( v2 )
    BaseSrvAddWOWRecord(a2, i);
  return 0;
}

```

## disassembly

```asm
0x18000821c  mov     rax, rsp
0x18000821f  mov     [rax+8], rbx
0x180008223  mov     [rax+10h], rbp
0x180008227  mov     [rax+18h], rsi
0x18000822b  mov     [rax+20h], rdi
0x18000822f  push    r12
0x180008231  push    r14
0x180008233  push    r15
0x180008235  sub     rsp, 20h
0x180008239  xor     r14d, r14d
0x18000823c  mov     rbp, rdx
0x18000823f  cmp     dword ptr [rcx+68h], 94h
0x180008246  mov     rdi, rcx
0x180008249  jnz     loc_180008339
0x18000824f  cmp     [rdx+58h], r14
0x180008253  jnz     short loc_180008260
0x180008255  mov     rax, [rcx+98h]
0x18000825c  mov     [rdx+58h], rax
0x180008260  mov     eax, [rcx]
0x180008262  cmp     eax, 0FFFFFFFFh
0x180008265  jnz     loc_180008322
0x18000826b  call    BaseSrvAllocateWOWRecord
0x180008270  mov     rbx, rax
0x180008273  test    rax, rax
0x180008276  jz      loc_18000831B
0x18000827c  mov     dword ptr [rax+4], 1
0x180008283  mov     r14d, 1
0x180008289  mov     rsi, [rdi+60h]
0x18000828d  mov     eax, [rbx]
0x18000828f  mov     [rdi], eax
0x180008291  lea     rdi, [rsi+11h]
0x180008295  cmp     byte ptr [rdi], 0
0x180008298  jz      short loc_1800082AE
0x18000829a  lea     rax, [rsi+90h]
0x1800082a1  cmp     rdi, rax
0x1800082a4  jnb     short loc_1800082AE
0x1800082a6  inc     rdi
0x1800082a9  cmp     byte ptr [rdi], 0
0x1800082ac  jnz     short loc_1800082A1
0x1800082ae  mov     r8, [rbx+30h]; P
0x1800082b2  sub     edi, esi
0x1800082b4  sub     edi, 10h
0x1800082b7  test    r8, r8
0x1800082ba  jz      short loc_1800082D7
0x1800082bc  mov     rcx, gs:60h
0x1800082c5  xor     edx, edx; Flags
0x1800082c7  mov     rcx, [rcx+30h]; HeapHandle
0x1800082cb  call    cs:__imp_RtlFreeHeap
0x1800082d2  nop     dword ptr [rax+rax+00h]
0x1800082d7  mov     rcx, gs:60h
0x1800082e0  mov     edx, cs:BaseSrvTag
0x1800082e6  add     edx, 40000h; Flags
0x1800082ec  mov     r8d, edi; Size
0x1800082ef  mov     r15d, edi
0x1800082f2  mov     rcx, [rcx+30h]; HeapHandle
0x1800082f6  call    cs:__imp_RtlAllocateHeap
0x1800082fd  nop     dword ptr [rax+rax+00h]
0x180008302  mov     [rbx+30h], rax
0x180008306  mov     rcx, rax; void *
0x180008309  test    rax, rax
0x18000830c  jnz     short loc_18000835E
0x18000830e  test    r14d, r14d
0x180008311  jz      short loc_18000831B
0x180008313  mov     rcx, rbx; P
0x180008316  call    BaseSrvFreeWOWRecord
0x18000831b  mov     eax, 0C00000A0h
0x180008320  jmp     short loc_18000833E
0x180008322  mov     rbx, [rdx+38h]
0x180008326  jmp     short loc_180008334
0x180008328  cmp     [rbx], eax
0x18000832a  jz      loc_180008289
0x180008330  mov     rbx, [rbx+20h]
0x180008334  test    rbx, rbx
0x180008337  jnz     short loc_180008328
0x180008339  mov     eax, 0C000000Dh
0x18000833e  mov     rbx, [rsp+38h+arg_0]
0x180008343  mov     rbp, [rsp+38h+arg_8]
0x180008348  mov     rsi, [rsp+38h+arg_10]
0x18000834d  mov     rdi, [rsp+38h+arg_18]
0x180008352  add     rsp, 20h
0x180008356  pop     r15
0x180008358  pop     r14
0x18000835a  pop     r12
0x18000835c  retn
0x18000835e  mov     eax, [rsi]
0x180008360  lea     rdx, [rsi+11h]; Src
0x180008364  mov     [rbx+28h], eax
0x180008367  mov     r8, r15; Size
0x18000836a  movzx   eax, word ptr [rsi+4]
0x18000836e  mov     [rbx+2Ch], ax
0x180008372  movzx   eax, word ptr [rsi+6]
0x180008376  mov     [rbx+2Eh], ax
0x18000837a  movsd   xmm0, qword ptr [rsi+8]
0x18000837f  movsd   qword ptr [rbx+38h], xmm0
0x180008384  mov     al, [rsi+10h]
0x180008387  mov     [rbx+40h], al
0x18000838a  call    memcpy_0
0x18000838f  mov     rax, [rbx+30h]
0x180008393  lea     ecx, [rdi-1]
0x180008396  mov     byte ptr [rcx+rax], 0
0x18000839a  test    r14d, r14d
0x18000839d  jz      short loc_1800083AA
0x18000839f  mov     rdx, rbx
0x1800083a2  mov     rcx, rbp
0x1800083a5  call    BaseSrvAddWOWRecord
0x1800083aa  xor     eax, eax
0x1800083ac  jmp     short loc_18000833E
```
