# FreeMatchBufEntry

- ea: `0x140004720`
- end: `0x14000485c`
- name: `FreeMatchBufEntry`
- size: `316`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1400029c0`
- `0x140005960`
- `0x140005b60`

## callees

- `0x140004720`
- `0x140004970`
- `0x14000c210`
- `0x140038dc8`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000484b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000484b`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400047e9`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400047e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004827`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004827`

## pseudocode

```c
__int64 __fastcall FreeMatchBufEntry(_QWORD *Entry)
{
  __int64 v2; // rdi
  __int64 v3; // rbx
  bool v4; // dl
  signed __int64 v5; // rcx
  void *v7; // rcx

  if ( Entry )
  {
    v2 = 0;
    if ( *((_WORD *)Entry + 12) )
    {
      while ( 1 )
      {
        v3 = Entry[v2 + 4];
        v4 = 0;
        _InterlockedIncrement64((volatile signed __int64 *)(v3 + 16));
        v5 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v3 + 16), 0xFFFFFFFFFFFFFFFFuLL) - 2;
        if ( (_DWORD)v5 == HIDWORD(v5) )
        {
          _m_prefetchw((const void *)(v3 + 52));
          v4 = (_InterlockedOr((volatile signed __int32 *)(v3 + 52), 0x10u) & 0x10) == 0;
        }
        if ( (*(_DWORD *)(*(_QWORD *)(v3 + 24) + 40LL) & 0x4000) == 0 || !v4 )
          goto LABEL_7;
        if ( !KeGetCurrentIrql() )
          break;
        NetioInsertWorkQueue(&gWfpGlobal[10].L.FreeEx);
LABEL_9:
        v2 = (unsigned int)(v2 + 1);
        if ( (unsigned int)v2 >= *((unsigned __int16 *)Entry + 12) )
          goto LABEL_10;
      }
      FeNotifyIntFilterDelete(v3);
LABEL_7:
      if ( _InterlockedExchangeAdd64((volatile signed __int64 *)(v3 + 16), 0xFFFFFFFFFFFFFFFFuLL) == 1 )
        FreeWFPFilter((_QWORD *)v3);
      goto LABEL_9;
    }
LABEL_10:
    if ( (*((_DWORD *)Entry + 7) & 1) == 0 )
    {
      v7 = (void *)Entry[11];
      if ( v7 )
      {
        ExFreePoolWithTag(v7, 0);
        Entry[11] = 0xBADBADFABADBADFAuLL;
      }
      ExFreeToNPagedLookasideList(gWfpGlobal, Entry);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140004720  push    rsi
0x140004722  sub     rsp, 20h
0x140004726  mov     rsi, rcx
0x140004729  test    rcx, rcx
0x14000472c  jz      loc_1400047C3
0x140004732  mov     [rsp+28h+arg_10], rdi
0x140004737  xor     eax, eax
0x140004739  xor     edi, edi
0x14000473b  cmp     ax, [rcx+18h]
0x14000473f  jnb     short loc_1400047B7
0x140004741  mov     [rsp+28h+arg_0], rbx
0x140004746  mov     [rsp+28h+arg_8], rbp
0x14000474b  mov     ebp, 1
0x140004750  mov     rbx, [rsi+rdi*8+20h]
0x140004755  xor     dl, dl
0x140004757  lock inc qword ptr [rbx+10h]
0x14000475c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140004763  lock xadd [rbx+10h], rcx
0x140004769  sub     rcx, 2
0x14000476d  mov     rax, rcx
0x140004770  shr     rax, 20h
0x140004774  cmp     ecx, eax
0x140004776  jz      short loc_1400047CC
0x140004778  mov     rax, [rbx+18h]
0x14000477c  test    dword ptr [rax+28h], 4000h
0x140004783  jz      short loc_140004789
0x140004785  test    dl, dl
0x140004787  jnz     short loc_1400047E9
0x140004789  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140004790  lock xadd [rbx+10h], rax
0x140004796  cmp     rax, rbp
0x140004799  jnz     short loc_1400047A3
0x14000479b  mov     rcx, rbx; P
0x14000479e  call    FreeWFPFilter
0x1400047a3  movzx   eax, word ptr [rsi+18h]
0x1400047a7  inc     edi
0x1400047a9  cmp     edi, eax
0x1400047ab  jb      short loc_140004750
0x1400047ad  mov     rbp, [rsp+28h+arg_8]
0x1400047b2  mov     rbx, [rsp+28h+arg_0]
0x1400047b7  mov     eax, [rsi+1Ch]
0x1400047ba  mov     rdi, [rsp+28h+arg_10]
0x1400047bf  test    al, 1
0x1400047c1  jz      short loc_14000481C
0x1400047c3  xor     eax, eax
0x1400047c5  add     rsp, 20h
0x1400047c9  pop     rsi
0x1400047ca  retn
0x1400047cc  prefetchw byte ptr [rbx+34h]
0x1400047d0  mov     eax, [rbx+34h]
0x1400047d3  mov     ecx, eax
0x1400047d5  or      ecx, 10h
0x1400047d8  lock cmpxchg [rbx+34h], ecx
0x1400047dd  jnz     short loc_1400047D3
0x1400047df  test    al, 10h
0x1400047e1  movzx   edx, dl
0x1400047e4  cmovz   edx, ebp
0x1400047e7  jmp     short loc_140004778
0x1400047e9  call    cs:__imp_KeGetCurrentIrql
0x1400047f0  nop     dword ptr [rax+rax+00h]
0x1400047f5  test    al, al
0x1400047f7  jnz     short loc_140004803
0x1400047f9  mov     rcx, rbx
0x1400047fc  call    FeNotifyIntFilterDelete
0x140004801  jmp     short loc_140004789
0x140004803  mov     rcx, cs:gWfpGlobal
0x14000480a  lea     rdx, [rbx+28h]
0x14000480e  add     rcx, 538h; Context
0x140004815  call    NetioInsertWorkQueue
0x14000481a  jmp     short loc_1400047A3
0x14000481c  mov     rcx, [rsi+58h]; P
0x140004820  test    rcx, rcx
0x140004823  jz      short loc_140004841
0x140004825  xor     edx, edx; Tag
0x140004827  call    cs:__imp_ExFreePoolWithTag
0x14000482e  nop     dword ptr [rax+rax+00h]
0x140004833  mov     rax, 0BADBADFABADBADFAh
0x14000483d  mov     [rsi+58h], rax
0x140004841  mov     rcx, cs:gWfpGlobal; Lookaside
0x140004848  mov     rdx, rsi; Entry
0x14000484b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140004852  nop     dword ptr [rax+rax+00h]
0x140004857  jmp     loc_1400047C3
```
