# BiUpdateEfiEntry

- ea: `0x14002515c`
- end: `0x14002535f`
- name: `BiUpdateEfiEntry`
- size: `515`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x140022cb8`
- `0x140023714`

## callees

- `0x1400133e4`
- `0x140013b48`
- `0x140013ee8`
- `0x14001a5d8`
- `0x140022e8c`
- `0x14002467c`
- `0x14002515c`
- `0x1400265d6`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x14002529c`
- `ntdll!RtlFreeHeap` at `0x1400252d9`
- `ntdll!RtlFreeHeap` at `0x1400252f6`
- `ntdll!RtlFreeHeap` at `0x140025313`
- `ntdll!RtlFreeHeap` at `0x14002534c`
- `ntdll!RtlFreeHeap` at `0x14002529c`
- `ntdll!RtlFreeHeap` at `0x1400252d9`
- `ntdll!RtlFreeHeap` at `0x1400252f6`
- `ntdll!RtlFreeHeap` at `0x140025313`
- `ntdll!RtlFreeHeap` at `0x14002534c`

## string_xrefs

- `0x1400252a6`: `BiUpdateEfiEntry %d '%ws' failed 0x%x`

## pseudocode

```c
__int64 __fastcall BiUpdateEfiEntry(__int64 a1, __int64 a2)
{
  _DWORD *v2; // rdi
  PVOID v4; // r15
  _DWORD *v5; // r13
  _WORD *v6; // r12
  int v7; // ebx
  int v8; // eax
  void *v9; // rsi
  unsigned int v10; // eax
  __int64 v12; // [rsp+20h] [rbp-40h]
  int v13; // [rsp+30h] [rbp-30h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-28h] BYREF
  _DWORD *v15; // [rsp+40h] [rbp-20h] BYREF
  _WORD *v16; // [rsp+48h] [rbp-18h] BYREF
  PVOID P; // [rsp+50h] [rbp-10h] BYREF
  void *Buf2; // [rsp+58h] [rbp-8h] BYREF
  int v20; // [rsp+B0h] [rbp+50h] BYREF
  int v21; // [rsp+B8h] [rbp+58h] BYREF

  v2 = *(_DWORD **)(a2 + 40);
  v20 = 0;
  v21 = 0;
  v4 = 0;
  v13 = 0;
  v5 = 0;
  P = 0;
  v6 = 0;
  v15 = 0;
  v16 = 0;
  Buf2 = 0;
  Handle = 0;
  v7 = BcdOpenObject(a1, (_QWORD *)(a2 + 16), &Handle);
  if ( v7 < 0 )
    goto LABEL_11;
  BiGetElement((__int64)Handle, 0x12000004u, &P, &v20);
  if ( (*(_BYTE *)(a2 + 48) & 8) == 0 )
  {
    BiGetElement((__int64)Handle, 0x11000001u, &v15, &v21);
    BiGetElement((__int64)Handle, 0x12000002u, &v16, &v13);
    v5 = v15;
    v6 = v16;
  }
  v4 = P;
  v8 = BiCreateMergedBootEntry(v2, P, v5, v6, &Buf2);
  v7 = v8;
  if ( v8 == -1073741766 )
  {
    v7 = 0;
    goto LABEL_12;
  }
  if ( v8 < 0 )
    goto LABEL_11;
  v9 = Buf2;
  v10 = v2[1];
  if ( v10 != *((_DWORD *)Buf2 + 1) || memcmp_0(v2, Buf2, v10) )
  {
    BiLogMessage(2, L"Updating BootEntry: %d '%ws'", (unsigned int)v2[2], (char *)v2 + (unsigned int)v2[4]);
    v7 = BiModifyBootEntry(v9);
    if ( v7 < 0 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
LABEL_11:
      LODWORD(v12) = v7;
      BiLogMessage(
        4,
        L"BiUpdateEfiEntry %d '%ws' failed 0x%x",
        (unsigned int)v2[2],
        (char *)v2 + (unsigned int)v2[4],
        v12);
      goto LABEL_12;
    }
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
  *(_QWORD *)(a2 + 40) = v9;
LABEL_12:
  if ( v4 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  if ( v5 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  if ( v6 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  if ( Handle )
    BcdCloseObject(Handle);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14002515c  mov     [rsp-38h+arg_8], rdx
0x140025161  push    rbp
0x140025162  push    rbx
0x140025163  push    rsi
0x140025164  push    rdi
0x140025165  push    r12
0x140025167  push    r13
0x140025169  push    r15
0x14002516b  mov     rbp, rsp
0x14002516e  sub     rsp, 60h
0x140025172  mov     rdi, [rdx+28h]
0x140025176  lea     r8, [rbp+Handle]
0x14002517a  xor     eax, eax
0x14002517c  mov     rsi, rdx
0x14002517f  add     rdx, 10h
0x140025183  mov     [rbp+arg_10], eax
0x140025186  mov     [rbp+arg_18], eax
0x140025189  mov     r15d, eax
0x14002518c  mov     [rbp+var_30], eax
0x14002518f  mov     r13d, eax
0x140025192  mov     [rbp+P], rax
0x140025196  mov     r12d, eax
0x140025199  mov     [rbp+var_20], rax
0x14002519d  mov     [rbp+var_18], rax
0x1400251a1  mov     [rbp+Buf2], rax
0x1400251a5  mov     [rbp+Handle], rax
0x1400251a9  call    BcdOpenObject
0x1400251ae  mov     ebx, eax
0x1400251b0  test    eax, eax
0x1400251b2  js      loc_1400252A2
0x1400251b8  mov     rcx, [rbp+Handle]
0x1400251bc  lea     r9, [rbp+arg_10]
0x1400251c0  lea     r8, [rbp+P]
0x1400251c4  mov     edx, 12000004h
0x1400251c9  call    BiGetElement
0x1400251ce  test    byte ptr [rsi+30h], 8
0x1400251d2  jnz     short loc_140025208
0x1400251d4  mov     rcx, [rbp+Handle]
0x1400251d8  lea     r9, [rbp+arg_18]
0x1400251dc  lea     r8, [rbp+var_20]
0x1400251e0  mov     edx, 11000001h
0x1400251e5  call    BiGetElement
0x1400251ea  mov     rcx, [rbp+Handle]
0x1400251ee  lea     r9, [rbp+var_30]
0x1400251f2  lea     r8, [rbp+var_18]
0x1400251f6  mov     edx, 12000002h
0x1400251fb  call    BiGetElement
0x140025200  mov     r13, [rbp+var_20]
0x140025204  mov     r12, [rbp+var_18]
0x140025208  mov     r15, [rbp+P]
0x14002520c  lea     rax, [rbp+Buf2]
0x140025210  mov     rdx, r15
0x140025213  mov     [rsp+60h+var_40], rax
0x140025218  mov     r9, r12
0x14002521b  mov     r8, r13
0x14002521e  mov     rcx, rdi
0x140025221  call    BiCreateMergedBootEntry
0x140025226  mov     ebx, eax
0x140025228  cmp     eax, 0C000003Ah
0x14002522d  jnz     short loc_140025236
0x14002522f  xor     ebx, ebx
0x140025231  jmp     loc_1400252C2
0x140025236  test    eax, eax
0x140025238  js      short loc_1400252A2
0x14002523a  mov     rsi, [rbp+Buf2]
0x14002523e  mov     eax, [rdi+4]
0x140025241  cmp     eax, [rsi+4]
0x140025244  jnz     short loc_14002525C
0x140025246  mov     r8d, eax; Size
0x140025249  mov     rdx, rsi; Buf2
0x14002524c  mov     rcx, rdi; Buf1
0x14002524f  call    memcmp_0
0x140025254  test    eax, eax
0x140025256  jz      loc_14002533A
0x14002525c  mov     r9d, [rdi+10h]
0x140025260  lea     rdx, aUpdatingBooten; "Updating BootEntry: %d '%ws'"
0x140025267  mov     r8d, [rdi+8]
0x14002526b  add     r9, rdi
0x14002526e  mov     ecx, 2
0x140025273  call    BiLogMessage
0x140025278  mov     rcx, rsi
0x14002527b  call    BiModifyBootEntry
0x140025280  mov     ebx, eax
0x140025282  test    eax, eax
0x140025284  jns     loc_14002533A
0x14002528a  mov     rcx, gs:60h
0x140025293  mov     r8, rsi; P
0x140025296  xor     edx, edx; Flags
0x140025298  mov     rcx, [rcx+30h]; HeapHandle
0x14002529c  call    cs:__imp_RtlFreeHeap
0x1400252a2  mov     r9d, [rdi+10h]
0x1400252a6  lea     rdx, aBiupdateefient; "BiUpdateEfiEntry %d '%ws' failed 0x%x"
0x1400252ad  mov     r8d, [rdi+8]
0x1400252b1  add     r9, rdi
0x1400252b4  mov     ecx, 4
0x1400252b9  mov     dword ptr [rsp+60h+var_40], ebx
0x1400252bd  call    BiLogMessage
0x1400252c2  test    r15, r15
0x1400252c5  jz      short loc_1400252DF
0x1400252c7  mov     rcx, gs:60h
0x1400252d0  mov     r8, r15; P
0x1400252d3  xor     edx, edx; Flags
0x1400252d5  mov     rcx, [rcx+30h]; HeapHandle
0x1400252d9  call    cs:__imp_RtlFreeHeap
0x1400252df  test    r13, r13
0x1400252e2  jz      short loc_1400252FC
0x1400252e4  mov     rcx, gs:60h
0x1400252ed  mov     r8, r13; P
0x1400252f0  xor     edx, edx; Flags
0x1400252f2  mov     rcx, [rcx+30h]; HeapHandle
0x1400252f6  call    cs:__imp_RtlFreeHeap
0x1400252fc  test    r12, r12
0x1400252ff  jz      short loc_140025319
0x140025301  mov     rcx, gs:60h
0x14002530a  mov     r8, r12; P
0x14002530d  xor     edx, edx; Flags
0x14002530f  mov     rcx, [rcx+30h]; HeapHandle
0x140025313  call    cs:__imp_RtlFreeHeap
0x140025319  cmp     [rbp+Handle], 0
0x14002531e  jz      short loc_140025329
0x140025320  mov     rcx, [rbp+Handle]; Handle
0x140025324  call    BcdCloseObject
0x140025329  mov     eax, ebx
0x14002532b  add     rsp, 60h
0x14002532f  pop     r15
0x140025331  pop     r13
0x140025333  pop     r12
0x140025335  pop     rdi
0x140025336  pop     rsi
0x140025337  pop     rbx
0x140025338  pop     rbp
0x140025339  retn
0x14002533a  mov     rcx, gs:60h
0x140025343  mov     r8, rdi; P
0x140025346  xor     edx, edx; Flags
0x140025348  mov     rcx, [rcx+30h]; HeapHandle
0x14002534c  call    cs:__imp_RtlFreeHeap
0x140025352  mov     rax, [rbp+arg_8]
0x140025356  mov     [rax+28h], rsi
0x14002535a  jmp     loc_1400252C2
```
