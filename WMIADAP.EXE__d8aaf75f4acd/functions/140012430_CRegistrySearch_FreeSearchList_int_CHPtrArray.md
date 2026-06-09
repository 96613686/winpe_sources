# CRegistrySearch::FreeSearchList(int,CHPtrArray &)

- ea: `0x140012430`
- end: `0x140012489`
- name: `?FreeSearchList@CRegistrySearch@@QEAAHHAEAVCHPtrArray@@@Z`
- size: `89`
- prototype: `__int64 __fastcall(CRegistrySearch *this, int, struct CHPtrArray *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x14001057c`
- `0x140012430`
- `0x140014830`

## pseudocode

```c
__int64 __fastcall CRegistrySearch::FreeSearchList(CRegistrySearch *this, int a2, struct CHPtrArray *a3)
{
  unsigned int v3; // ebx
  int v5; // ebp
  unsigned int i; // edi
  CHString *v7; // rcx

  v3 = 0;
  if ( a2 == 1 )
  {
    v5 = *((_DWORD *)a3 + 2);
    for ( i = 0; (int)i < v5; ++i )
    {
      v7 = *(CHString **)(*(_QWORD *)a3 + 8LL * i);
      if ( v7 )
        CHString::`scalar deleting destructor'(v7, 1u);
    }
    v3 = 1;
    CHPtrArray::SetSize(a3, 0, -1);
  }
  return v3;
}

```

## disassembly

```asm
0x140012430  push    rbx
0x140012432  push    rbp
0x140012433  push    rsi
0x140012434  push    rdi
0x140012435  sub     rsp, 28h
0x140012439  xor     ebx, ebx
0x14001243b  mov     rsi, r8
0x14001243e  cmp     edx, 1
0x140012441  jnz     short loc_14001247E
0x140012443  mov     ebp, [r8+8]
0x140012447  mov     edi, ebx
0x140012449  test    ebp, ebp
0x14001244b  jle     short loc_14001246B
0x14001244d  mov     rax, [rsi]
0x140012450  mov     ecx, edi
0x140012452  mov     rcx, [rax+rcx*8]; this
0x140012456  test    rcx, rcx
0x140012459  jz      short loc_140012465
0x14001245b  mov     edx, 1; unsigned int
0x140012460  call    ??_GCHString@@QEAAPEAXI@Z; CHString::`scalar deleting destructor'(uint)
0x140012465  inc     edi
0x140012467  cmp     edi, ebp
0x140012469  jl      short loc_14001244D
0x14001246b  or      r8d, 0FFFFFFFFh; int
0x14001246f  xor     edx, edx; int
0x140012471  mov     rcx, rsi; this
0x140012474  mov     ebx, 1
0x140012479  call    ?SetSize@CHPtrArray@@QEAAXHH@Z; CHPtrArray::SetSize(int,int)
0x14001247e  mov     eax, ebx
0x140012480  add     rsp, 28h
0x140012484  pop     rdi
0x140012485  pop     rsi
0x140012486  pop     rbp
0x140012487  pop     rbx
0x140012488  retn
```
