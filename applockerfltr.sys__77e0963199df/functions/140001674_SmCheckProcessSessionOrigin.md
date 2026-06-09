# SmCheckProcessSessionOrigin

- ea: `0x140001674`
- end: `0x14000174e`
- name: `SmCheckProcessSessionOrigin`
- size: `218`
- prototype: `__int64 __fastcall(__int64, unsigned int *, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140007030`
- `0x140007410`

## callees

- `0x140001674`
- `0x140001a40`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400016fa`
- `ntoskrnl!ExAllocatePool2` at `0x1400016fa`
- `FLTMGR!FltAcquireResourceShared` at `0x1400016b3`
- `FLTMGR!FltAcquireResourceShared` at `0x1400016b3`
- `FLTMGR!FltReleaseResource` at `0x140001732`
- `FLTMGR!FltReleaseResource` at `0x140001732`

## pseudocode

```c
__int64 __fastcall SmCheckProcessSessionOrigin(__int64 a1, unsigned int *a2, _QWORD *a3)
{
  unsigned int v3; // edi
  __int64 **v7; // rcx
  __int64 *v8; // rbx
  unsigned int v9; // ebp
  void *Pool2; // rax
  void *v11; // rsi

  v3 = 0;
  if ( qword_1400040C8 && _InterlockedCompareExchange64((volatile signed __int64 *)qword_1400040C8, 0, 0) )
  {
    FltAcquireResourceShared(Resource);
    if ( qword_1400040C8 && *(_QWORD *)qword_1400040C8 )
    {
      v7 = (__int64 **)(*(_QWORD *)qword_1400040C8 + 16LL);
      v8 = *v7;
      while ( a1 != v8[2] )
      {
        v8 = (__int64 *)*v8;
        if ( v8 == (__int64 *)v7 )
          goto LABEL_11;
      }
      v9 = *((_DWORD *)v8 + 8);
      Pool2 = (void *)ExAllocatePool2(258, v9, 1400139123);
      v11 = Pool2;
      if ( Pool2 )
      {
        memmove(Pool2, (const void *)v8[3], *((unsigned int *)v8 + 8));
        *a3 = v11;
        *a2 = v9;
      }
      else
      {
        v3 = -1073741801;
      }
    }
LABEL_11:
    FltReleaseResource(Resource);
  }
  return v3;
}

```

## disassembly

```asm
0x140001674  push    rbx
0x140001676  push    rbp
0x140001677  push    rsi
0x140001678  push    rdi
0x140001679  push    r14
0x14000167b  push    r15
0x14000167d  sub     rsp, 28h
0x140001681  mov     r10, cs:qword_1400040C8
0x140001688  xor     edi, edi
0x14000168a  mov     r14, r8
0x14000168d  mov     r15, rdx
0x140001690  mov     rsi, rcx
0x140001693  test    r10, r10
0x140001696  jz      loc_14000173E
0x14000169c  xor     r9d, r9d
0x14000169f  xor     eax, eax
0x1400016a1  lock cmpxchg [r10], r9
0x1400016a6  jz      loc_14000173E
0x1400016ac  mov     rcx, cs:Resource; Resource
0x1400016b3  call    cs:__imp_FltAcquireResourceShared
0x1400016ba  nop     dword ptr [rax+rax+00h]
0x1400016bf  mov     rax, cs:qword_1400040C8
0x1400016c6  test    rax, rax
0x1400016c9  jz      short loc_14000172B
0x1400016cb  mov     rcx, [rax]
0x1400016ce  test    rcx, rcx
0x1400016d1  jz      short loc_14000172B
0x1400016d3  add     rcx, 10h
0x1400016d7  mov     rbx, [rcx]
0x1400016da  jmp     short loc_1400016E4
0x1400016dc  mov     rbx, [rbx]
0x1400016df  cmp     rbx, rcx
0x1400016e2  jz      short loc_14000172B
0x1400016e4  cmp     rsi, [rbx+10h]
0x1400016e8  jnz     short loc_1400016DC
0x1400016ea  mov     ebp, [rbx+20h]
0x1400016ed  mov     ecx, 102h
0x1400016f2  mov     edx, ebp
0x1400016f4  mov     r8d, 53746D73h
0x1400016fa  call    cs:__imp_ExAllocatePool2
0x140001701  nop     dword ptr [rax+rax+00h]
0x140001706  mov     rsi, rax
0x140001709  test    rax, rax
0x14000170c  jnz     short loc_140001715
0x14000170e  mov     edi, 0C0000017h
0x140001713  jmp     short loc_14000172B
0x140001715  mov     r8d, [rbx+20h]; Size
0x140001719  mov     rcx, rsi; void *
0x14000171c  mov     rdx, [rbx+18h]; Src
0x140001720  call    memmove
0x140001725  mov     [r14], rsi
0x140001728  mov     [r15], ebp
0x14000172b  mov     rcx, cs:Resource; Resource
0x140001732  call    cs:__imp_FltReleaseResource
0x140001739  nop     dword ptr [rax+rax+00h]
0x14000173e  mov     eax, edi
0x140001740  add     rsp, 28h
0x140001744  pop     r15
0x140001746  pop     r14
0x140001748  pop     rdi
0x140001749  pop     rsi
0x14000174a  pop     rbp
0x14000174b  pop     rbx
0x14000174c  retn
```
