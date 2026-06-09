# SdbpCreateSDBLookupEntry

- ea: `0x18003756c`
- end: `0x180037708`
- name: `SdbpCreateSDBLookupEntry`
- size: `412`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001b1c4`

## callees

- `0x1800055e0`
- `0x18000f114`
- `0x180036a5c`
- `0x18003756c`
- `0x18004b598`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18003762f`
- `ntdll!RtlAllocateHeap` at `0x18003762f`

## string_xrefs

- `0x18003764e`: `SdbpCreateSDBLookupEntry`
- `0x1800376e4`: `SdbpCreateSDBLookupEntry`

## pseudocode

```c
_QWORD *__fastcall SdbpCreateSDBLookupEntry(__int64 a1, int a2, __int64 a3, unsigned int a4)
{
  __int64 SDBLookupEntry; // rax
  __int64 v9; // rax
  int v10; // r14d
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // rsi
  unsigned int v13; // eax
  unsigned int v14; // edi
  _DWORD *Heap; // rax
  char *v16; // rcx
  _QWORD *v17; // r10
  __int64 v18; // rax

  SDBLookupEntry = SdbpFindSDBLookupEntry(a1, a3, a4);
  if ( SDBLookupEntry )
    SdbpRemoveSDBLookupEntry(a1, SDBLookupEntry);
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)(a3 + 2 * v9) );
  v10 = v9 + 1;
  v11 = 2LL * (unsigned int)(v9 + 1);
  if ( v11 > 0xFFFFFFFF || (v12 = 24LL * (unsigned int)(a2 - 1), v12 > 0xFFFFFFFF) )
  {
    AslLogCallPrintf(1, "SdbpCreateSDBLookupEntry", 270, "Invalid sdb lookup buffer request");
    return 0;
  }
  v13 = v12 + v11;
  if ( (int)v12 + (int)v11 < (unsigned int)v11 )
  {
    AslLogCallPrintf(1, "SdbpCreateSDBLookupEntry", 277, "Invalid sdb lookup total buffer request");
    return 0;
  }
  v14 = v13 + 56;
  if ( v13 + 56 < v13 )
  {
    AslLogCallPrintf(1, "SdbpCreateSDBLookupEntry", 282, "Invalid sdb lookup total buffer request");
    return 0;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v14);
  if ( !Heap )
  {
    AslLogCallPrintf(1, "SdbpCreateSDBLookupEntry", 289, "Failed to allocate 0x%lx bytes for sdb lookup buffer", v14);
    return 0;
  }
  v16 = (char *)&Heap[v12 / 4 + 14];
  Heap[6] = a4;
  *((_QWORD *)Heap + 2) = v16;
  Heap[7] = a2;
  if ( (int)RtlStringCchCopyW(v16, v10, a3) < 0 )
    return 0;
  v18 = *(_QWORD *)(a1 + 576);
  if ( v18 )
  {
    *v17 = v18;
    v17[1] = *(_QWORD *)(*(_QWORD *)(a1 + 576) + 8LL);
    **(_QWORD **)(*(_QWORD *)(a1 + 576) + 8LL) = v17;
    *(_QWORD *)(*(_QWORD *)(a1 + 576) + 8LL) = v17;
    *(_QWORD *)(a1 + 576) = v17;
  }
  else
  {
    *(_QWORD *)(a1 + 576) = v17;
    v17[1] = v17;
    *v17 = v17;
  }
  return v17;
}

```

## disassembly

```asm
0x18003756c  push    rbx
0x18003756e  push    rbp
0x18003756f  push    rsi
0x180037570  push    rdi
0x180037571  push    r12
0x180037573  push    r13
0x180037575  push    r14
0x180037577  push    r15
0x180037579  sub     rsp, 38h
0x18003757d  mov     rbp, r8
0x180037580  mov     r15d, edx
0x180037583  mov     rdx, rbp
0x180037586  mov     r8d, r9d
0x180037589  mov     r12d, r9d
0x18003758c  mov     rbx, rcx
0x18003758f  call    SdbpFindSDBLookupEntry
0x180037594  xor     r13d, r13d
0x180037597  test    rax, rax
0x18003759a  jz      short loc_1800375A7
0x18003759c  mov     rdx, rax
0x18003759f  mov     rcx, rbx
0x1800375a2  call    SdbpRemoveSDBLookupEntry
0x1800375a7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800375ab  inc     rax
0x1800375ae  cmp     [rbp+rax*2+0], r13w
0x1800375b4  jnz     short loc_1800375AB
0x1800375b6  lea     r14d, [rax+1]
0x1800375ba  mov     r8d, 0FFFFFFFFh
0x1800375c0  mov     edx, r14d
0x1800375c3  add     rdx, rdx
0x1800375c6  cmp     rdx, r8
0x1800375c9  ja      loc_1800376D7
0x1800375cf  lea     eax, [r15-1]
0x1800375d3  lea     rax, [rax+rax*2]
0x1800375d7  lea     rsi, ds:0[rax*8]
0x1800375df  cmp     rsi, r8
0x1800375e2  ja      loc_1800376D7
0x1800375e8  lea     eax, [rsi+rdx]
0x1800375eb  cmp     eax, edx
0x1800375ed  jnb     short loc_180037601
0x1800375ef  lea     r9, aInvalidSdbLook_0; "Invalid sdb lookup total buffer request"
0x1800375f6  mov     r8d, 115h
0x1800375fc  jmp     loc_1800376E4
0x180037601  lea     edi, [rax+38h]
0x180037604  cmp     edi, eax
0x180037606  jnb     short loc_18003761A
0x180037608  lea     r9, aInvalidSdbLook_0; "Invalid sdb lookup total buffer request"
0x18003760f  mov     r8d, 11Ah
0x180037615  jmp     loc_1800376E4
0x18003761a  mov     rcx, gs:60h
0x180037623  mov     edx, 8; Flags
0x180037628  mov     r8d, edi; Size
0x18003762b  mov     rcx, [rcx+30h]; HeapHandle
0x18003762f  call    cs:__imp_RtlAllocateHeap
0x180037635  mov     r10, rax
0x180037638  test    rax, rax
0x18003763b  jnz     short loc_180037662
0x18003763d  lea     r9, aFailedToAlloca_8; "Failed to allocate 0x%lx bytes for sdb "...
0x180037644  mov     [rsp+78h+var_58], edi
0x180037648  mov     r8d, 121h
0x18003764e  lea     rdx, aSdbpcreatesdbl; "SdbpCreateSDBLookupEntry"
0x180037655  lea     ecx, [rax+1]
0x180037658  call    AslLogCallPrintf
0x18003765d  jmp     loc_1800376F5
0x180037662  lea     rcx, [rsi+38h]
0x180037666  movsxd  rdx, r14d
0x180037669  add     rcx, r10
0x18003766c  mov     [rax+18h], r12d
0x180037670  mov     r8, rbp
0x180037673  mov     [rax+10h], rcx
0x180037677  mov     [rax+1Ch], r15d
0x18003767b  call    RtlStringCchCopyW
0x180037680  test    eax, eax
0x180037682  js      short loc_1800376F5
0x180037684  mov     rax, [rbx+240h]
0x18003768b  test    rax, rax
0x18003768e  jnz     short loc_1800376A0
0x180037690  mov     [rbx+240h], r10
0x180037697  mov     [r10+8], r10
0x18003769b  mov     [r10], r10
0x18003769e  jmp     short loc_1800376D2
0x1800376a0  mov     [r10], rax
0x1800376a3  mov     rax, [rbx+240h]
0x1800376aa  mov     rcx, [rax+8]
0x1800376ae  mov     [r10+8], rcx
0x1800376b2  mov     rax, [rbx+240h]
0x1800376b9  mov     rcx, [rax+8]
0x1800376bd  mov     [rcx], r10
0x1800376c0  mov     rax, [rbx+240h]
0x1800376c7  mov     [rax+8], r10
0x1800376cb  mov     [rbx+240h], r10
0x1800376d2  mov     rax, r10
0x1800376d5  jmp     short loc_1800376F7
0x1800376d7  lea     r9, aInvalidSdbLook; "Invalid sdb lookup buffer request"
0x1800376de  mov     r8d, 10Eh
0x1800376e4  lea     rdx, aSdbpcreatesdbl; "SdbpCreateSDBLookupEntry"
0x1800376eb  mov     ecx, 1
0x1800376f0  call    AslLogCallPrintf
0x1800376f5  xor     eax, eax
0x1800376f7  add     rsp, 38h
0x1800376fb  pop     r15
0x1800376fd  pop     r14
0x1800376ff  pop     r13
0x180037701  pop     r12
0x180037703  pop     rdi
0x180037704  pop     rsi
0x180037705  pop     rbp
0x180037706  pop     rbx
0x180037707  retn
```
