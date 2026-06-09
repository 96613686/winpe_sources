# AfdAllocateMdlChain

- ea: `0x140008064`
- end: `0x140008203`
- name: `AfdAllocateMdlChain`
- size: `415`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x140007350`
- `0x1400086d0`
- `0x14001f120`
- `0x140022470`
- `0x140054228`

## callees

- `0x140008064`
- `0x14002fd5c`
- `0x140092110`
- `0x14009214c`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x1400081ad`
- `ntoskrnl!ExRaiseStatus` at `0x1400081ad`
- `ntoskrnl!ProbeForRead` at `0x1400080c9`
- `ntoskrnl!ProbeForRead` at `0x1400080c9`
- `ntoskrnl!IoFreeMdl` at `0x1400081d4`
- `ntoskrnl!IoFreeMdl` at `0x1400081d4`
- `ntoskrnl!MmProbeAndLockPages` at `0x14000815e`
- `ntoskrnl!MmProbeAndLockPages` at `0x14000815e`
- `ntoskrnl!IoAllocateMdl` at `0x14000812d`
- `ntoskrnl!IoAllocateMdl` at `0x14000812d`

## pseudocode

```c
__int64 __fastcall AfdAllocateMdlChain(__int64 a1, _QWORD *a2, unsigned int a3, LOCK_OPERATION a4, _DWORD *a5)
{
  unsigned int v5; // edi
  _QWORD *v6; // rbx
  KPROCESSOR_MODE v7; // r12
  struct _MDL *v8; // r13
  int v9; // esi
  void *ULong64FromUser; // r15
  ULONG ULongFromUser; // r14d
  struct _MDL *Mdl; // rax
  struct _MDL *v13; // r15
  unsigned int v15; // [rsp+30h] [rbp-58h]

  v5 = a3;
  v6 = a2;
  v7 = *(_BYTE *)(a1 + 64);
  v15 = 0;
  v8 = (struct _MDL *)(a1 + 8);
  v9 = 0;
  if ( v7 )
  {
    if ( !a2 || a3 - 1 > 0xFFFFFFE )
      ExRaiseStatus(-1073741811);
    ProbeForRead(a2, 16LL * a3, 4u);
  }
  while ( v5 )
  {
    if ( v7 )
      ULong64FromUser = (void *)RtlReadULong64FromUser(v6 + 1);
    else
      ULong64FromUser = (void *)v6[1];
    if ( v7 )
      ULongFromUser = RtlReadULongFromUser(v6);
    else
      ULongFromUser = *(_DWORD *)v6;
    if ( ULongFromUser )
    {
      if ( ~v9 < ULongFromUser )
      {
        v15 = -1073741811;
        break;
      }
      Mdl = IoAllocateMdl(ULong64FromUser, ULongFromUser, 0, 1u, 0);
      v13 = Mdl;
      if ( !Mdl )
      {
        v15 = -1073741670;
        break;
      }
      MmProbeAndLockPages(Mdl, v7, a4);
      v8->Next = v13;
      v8 = v13;
      v9 += ULongFromUser;
    }
    --v5;
    v6 += 2;
  }
  *a5 = v9;
  return v15;
}

```

## disassembly

```asm
0x140008064  mov     rax, rsp
0x140008067  mov     [rax+20h], r9d
0x14000806b  push    rbx
0x14000806c  push    rsi
0x14000806d  push    rdi
0x14000806e  push    r12
0x140008070  push    r13
0x140008072  push    r14
0x140008074  push    r15
0x140008076  sub     rsp, 50h
0x14000807a  mov     edi, r8d
0x14000807d  mov     rbx, rdx
0x140008080  mov     r12b, [rcx+40h]
0x140008084  mov     dword ptr [rax-58h], 0
0x14000808b  mov     qword ptr [rax-50h], 0
0x140008093  lea     r13, [rcx+8]
0x140008097  mov     [rax-48h], r13
0x14000809b  xor     esi, esi
0x14000809d  mov     [rax-54h], esi
0x1400080a0  test    r12b, r12b
0x1400080a3  jz      short loc_1400080D5
0x1400080a5  test    rdx, rdx
0x1400080a8  jz      loc_1400081A8
0x1400080ae  lea     eax, [rdi-1]
0x1400080b1  cmp     eax, 0FFFFFFEh
0x1400080b6  ja      loc_1400081A8
0x1400080bc  mov     edx, edi
0x1400080be  shl     rdx, 4; Length
0x1400080c2  lea     r8d, [rsi+4]; Alignment
0x1400080c6  mov     rcx, rbx; Address
0x1400080c9  call    cs:__imp_ProbeForRead
0x1400080d0  nop     dword ptr [rax+rax+00h]
0x1400080d5  test    edi, edi
0x1400080d7  jz      loc_1400081C1
0x1400080dd  test    r12b, r12b
0x1400080e0  jz      loc_140008197
0x1400080e6  lea     rcx, [rbx+8]
0x1400080ea  call    RtlReadULong64FromUser
0x1400080ef  mov     r15, rax
0x1400080f2  test    r12b, r12b
0x1400080f5  jz      loc_1400081A0
0x1400080fb  mov     rcx, rbx
0x1400080fe  call    RtlReadULongFromUser
0x140008103  mov     r14d, eax
0x140008106  test    r14d, r14d
0x140008109  jz      short loc_14000817D
0x14000810b  mov     eax, esi
0x14000810d  not     eax
0x14000810f  cmp     eax, r14d
0x140008112  jb      loc_1400081B9
0x140008118  mov     [rsp+88h+Irp], 0; Irp
0x140008121  mov     r9b, 1; ChargeQuota
0x140008124  xor     r8d, r8d; SecondaryBuffer
0x140008127  mov     edx, r14d; Length
0x14000812a  mov     rcx, r15; VirtualAddress
0x14000812d  call    cs:__imp_IoAllocateMdl
0x140008134  nop     dword ptr [rax+rax+00h]
0x140008139  mov     r15, rax
0x14000813c  mov     [rsp+88h+Mdl], rax
0x140008141  test    rax, rax
0x140008144  jnz     short loc_140008150
0x140008146  mov     [rsp+88h+var_58], 0C000009Ah
0x14000814e  jmp     short loc_1400081C1
0x140008150  mov     r8d, [rsp+88h+Operation]; Operation
0x140008158  mov     dl, r12b; AccessMode
0x14000815b  mov     rcx, r15; MemoryDescriptorList
0x14000815e  call    cs:__imp_MmProbeAndLockPages
0x140008165  nop     dword ptr [rax+rax+00h]
0x14000816a  mov     [r13+0], r15
0x14000816e  mov     r13, r15
0x140008171  mov     [rsp+88h+var_48], r15
0x140008176  add     esi, r14d
0x140008179  mov     [rsp+88h+var_54], esi
0x14000817d  dec     edi
0x14000817f  mov     [rsp+88h+arg_10], edi
0x140008186  add     rbx, 10h
0x14000818a  mov     [rsp+88h+arg_8], rbx
0x140008192  jmp     loc_1400080D5
0x140008197  mov     r15, [rbx+8]
0x14000819b  jmp     loc_1400080F2
0x1400081a0  mov     r14d, [rbx]
0x1400081a3  jmp     loc_140008106
0x1400081a8  mov     ecx, 0C000000Dh; Status
0x1400081ad  call    cs:__imp_ExRaiseStatus
0x1400081b9  mov     [rsp+88h+var_58], 0C000000Dh
0x1400081c1  jmp     short loc_1400081E4
0x1400081c3  mov     rcx, [rsp+88h+Mdl]; Mdl
0x1400081c8  test    rcx, rcx
0x1400081cb  jz      short loc_1400081E0
0x1400081cd  cmp     [rsp+88h+var_48], rcx
0x1400081d2  jz      short loc_1400081E0
0x1400081d4  call    cs:__imp_IoFreeMdl
0x1400081db  nop     dword ptr [rax+rax+00h]
0x1400081e0  mov     esi, [rsp+88h+var_54]
0x1400081e4  mov     rax, [rsp+88h+arg_20]
0x1400081ec  mov     [rax], esi
0x1400081ee  mov     eax, [rsp+88h+var_58]
0x1400081f2  add     rsp, 50h
0x1400081f6  pop     r15
0x1400081f8  pop     r14
0x1400081fa  pop     r13
0x1400081fc  pop     r12
0x1400081fe  pop     rdi
0x1400081ff  pop     rsi
0x140008200  pop     rbx
0x140008201  retn
0x140073221  push    rbp
0x140073223  sub     rsp, 30h
0x140073227  mov     rbp, rdx
0x14007322a  mov     r8, rcx
0x14007322d  lea     r9, [rbp+30h]
0x140073231  mov     edx, 1600h
0x140073236  lea     rcx, aMinioSocketsWi_6; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x14007323d  call    AfdExceptionFilter
0x140073242  nop
0x140073243  add     rsp, 30h
0x140073247  pop     rbp
0x140073248  retn
```
