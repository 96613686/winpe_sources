# sub_18000DABC

- ea: `0x18000dabc`
- end: `0x18000db5a`
- name: `sub_18000DABC`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d5e4`
- `0x180027fa4`

## callees

- `0x18000dabc`
- `0x18000ed4c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dacf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dacf`

## pseudocode

```c
signed __int64 __fastcall sub_18000DABC(__int64 a1, char a2)
{
  __int64 v2; // rdi
  DWORD CurrentThreadId; // esi
  unsigned __int64 v5; // rbx
  __int64 i; // rax
  __int64 v8; // rax
  signed __int64 v9; // rcx
  signed __int64 v10; // rax

  v2 = qword_180084440;
  CurrentThreadId = GetCurrentThreadId();
  v5 = ((unsigned __int64)CurrentThreadId >> 2) % 0xA;
  for ( i = *(_QWORD *)(v2 + 8 * v5); i; i = *(_QWORD *)(i + 8) )
  {
    if ( *(_DWORD *)i == CurrentThreadId )
      return i + 16;
  }
  if ( !a2 )
    return 0;
  v8 = sub_18000ED4C(0, 0x18u);
  v9 = v8;
  if ( !v8 )
    return 0;
  *(_DWORD *)v8 = CurrentThreadId;
  *(_DWORD *)(v8 + 4) = 0;
  *(_QWORD *)(v8 + 8) = 0;
  *(_QWORD *)(v8 + 16) = 0;
  do
  {
    v10 = *(_QWORD *)(v2 + 8 * v5);
    *(_QWORD *)(v9 + 8) = v10;
  }
  while ( v10 != _InterlockedCompareExchange64((volatile signed __int64 *)(v2 + 8 * v5), v9, v10) );
  return v9 + 16;
}

```

## disassembly

```asm
0x18000dabc  push    rbx
0x18000dabe  push    rbp
0x18000dabf  push    rsi
0x18000dac0  push    rdi
0x18000dac1  sub     rsp, 28h
0x18000dac5  mov     rdi, cs:qword_180084440
0x18000dacc  mov     bpl, dl
0x18000dacf  call    cs:GetCurrentThreadId
0x18000dad5  mov     ebx, eax
0x18000dad7  mov     esi, eax
0x18000dad9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000dae3  shr     rbx, 2
0x18000dae7  mul     rbx
0x18000daea  shr     rdx, 3
0x18000daee  lea     rcx, [rdx+rdx*4]
0x18000daf2  add     rcx, rcx
0x18000daf5  sub     rbx, rcx
0x18000daf8  mov     rax, [rdi+rbx*8]
0x18000dafc  test    rax, rax
0x18000daff  jz      short loc_18000DB11
0x18000db01  cmp     [rax], esi
0x18000db03  jz      short loc_18000DB0B
0x18000db05  mov     rax, [rax+8]
0x18000db09  jmp     short loc_18000DAFC
0x18000db0b  add     rax, 10h
0x18000db0f  jmp     short loc_18000DB51
0x18000db11  test    bpl, bpl
0x18000db14  jz      short loc_18000DB4F
0x18000db16  mov     edx, 18h; dwBytes
0x18000db1b  xor     ecx, ecx; dwFlags
0x18000db1d  call    sub_18000ED4C
0x18000db22  mov     rcx, rax
0x18000db25  test    rax, rax
0x18000db28  jz      short loc_18000DB4F
0x18000db2a  mov     [rax], esi
0x18000db2c  xor     eax, eax
0x18000db2e  mov     [rcx+4], eax
0x18000db31  mov     [rcx+8], rax
0x18000db35  mov     [rcx+10h], rax
0x18000db39  mov     rax, [rdi+rbx*8]
0x18000db3d  mov     [rcx+8], rax
0x18000db41  lock cmpxchg [rdi+rbx*8], rcx
0x18000db47  jnz     short loc_18000DB39
0x18000db49  lea     rax, [rcx+10h]
0x18000db4d  jmp     short loc_18000DB51
0x18000db4f  xor     eax, eax
0x18000db51  add     rsp, 28h
0x18000db55  pop     rdi
0x18000db56  pop     rsi
0x18000db57  pop     rbp
0x18000db58  pop     rbx
0x18000db59  retn
```
