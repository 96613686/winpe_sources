# LKRhash::CLKRLinearHashTable::Begin(void)

- ea: `0x180008070`
- end: `0x18000822c`
- name: `?Begin@CLKRLinearHashTable@LKRhash@@QEAA?AVCLKRLinearHashTable_Iterator@2@XZ`
- size: `444`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009b98`

## callees

- `0x1800075f0`
- `0x180008070`
- `0x180009c78`
- `0x18000b010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800080be`
- `KERNEL32!GetCurrentThreadId` at `0x1800080be`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LKRhash::CLKRLinearHashTable::Begin(__int64 a1, __int64 a2)
{
  volatile signed __int32 *v4; // rdi
  int v5; // ebx
  DWORD CurrentThreadId; // eax
  char v7; // cl
  signed __int32 v8; // edx
  bool j; // zf
  volatile signed __int32 v10; // edx
  signed __int32 v11; // edx
  volatile signed __int32 v12; // edx
  bool i; // zf
  volatile signed __int32 v14; // edx
  __int64 v15; // r8
  volatile signed __int32 *v16; // r9
  __int64 v17; // rax
  __int64 v19; // [rsp+28h] [rbp-18h] BYREF
  volatile signed __int32 *v20; // [rsp+30h] [rbp-10h]
  int v21; // [rsp+38h] [rbp-8h]
  __int16 v22; // [rsp+3Ch] [rbp-4h]

  if ( *(_DWORD *)(a1 + 20) )
  {
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = 0;
    *(_WORD *)(a2 + 20) = 0;
    return a2;
  }
  v4 = **(volatile signed __int32 ***)(a1 + 104);
  if ( !*(_BYTE *)(a1 + 153) )
  {
    v7 = *(_BYTE *)(a1 + 153);
LABEL_15:
    if ( v7 )
    {
      if ( (unsigned __int16)*v4 || (v11 = *v4, v11 != _InterlockedCompareExchange(v4, (v11 + 0x10000) | 0xFFFF, v11)) )
      {
        do
          v12 = *v4;
        while ( v12 != _InterlockedCompareExchange(v4, *v4 + 0x10000, *v4) );
        CReaderWriterLock2::_LockSpin((CReaderWriterLock2 *)v4, 1);
      }
    }
    for ( i = *(_BYTE *)(a1 + 153) == 0; !i; i = v14 == _InterlockedCompareExchange(
                                                          v4,
                                                          (*v4 - 0x10000) & 0xFFFF0000,
                                                          *v4) )
      v14 = *v4;
    goto LABEL_23;
  }
  v5 = *(_DWORD *)(a1 + 28);
  CurrentThreadId = GetCurrentThreadId();
  v7 = *(_BYTE *)(a1 + 153);
  if ( ((CurrentThreadId ^ v5) & 0xFFFFFFFC) == 0 )
    goto LABEL_15;
  if ( (!v7 || (*(_DWORD *)(a1 + 24) & 0x7FFF) != 0) && *(_BYTE *)(a1 + 153) )
  {
    if ( (*v4 & 0xFFFF8000) != 0 || (v8 = *v4, v8 != _InterlockedCompareExchange(v4, v8 + 1, v8)) )
      CReaderWriterLock2::_LockSpin((CReaderWriterLock2 *)v4, 0);
    for ( j = *(_BYTE *)(a1 + 153) == 0; !j; j = v10 == _InterlockedCompareExchange(v4, *v4 - 1, *v4) )
      v10 = *v4;
  }
LABEL_23:
  v19 = a1;
  v20 = v4 + 2;
  v21 = 0;
  v22 = -1;
  LKRhash::CLKRLinearHashTable_Iterator::_Increment((LKRhash::CLKRLinearHashTable_Iterator *)&v19, 0);
  v15 = v19;
  *(_QWORD *)a2 = v19;
  v16 = v20;
  *(_QWORD *)(a2 + 8) = v20;
  *(_DWORD *)(a2 + 16) = v21;
  v17 = v22;
  *(_WORD *)(a2 + 20) = v22;
  if ( v15 && (_WORD)v17 != 0xFFFF )
  {
    (*(void (__fastcall **)(_QWORD, __int64))(v15 + 56))(*(_QWORD *)&v16[2 * v17 + 6], 1);
    LOWORD(v17) = v22;
    v16 = v20;
    v15 = v19;
  }
  if ( v15 && (_WORD)v17 != 0xFFFF )
    (*(void (__fastcall **)(_QWORD, __int64))(v15 + 56))(*(_QWORD *)&v16[2 * (__int16)v17 + 6], 0xFFFFFFFFLL);
  return a2;
}

```

## disassembly

```asm
0x180008070  push    rbp
0x180008072  push    rbx
0x180008073  push    rsi
0x180008074  push    rdi
0x180008075  push    r14
0x180008077  mov     rbp, rsp
0x18000807a  sub     rsp, 40h
0x18000807e  mov     r14, rdx
0x180008081  mov     rsi, rcx
0x180008084  cmp     dword ptr [rcx+14h], 0
0x180008088  jz      short loc_1800080AB
0x18000808a  mov     qword ptr [rdx], 0
0x180008091  mov     qword ptr [rdx+8], 0
0x180008099  mov     dword ptr [rdx+10h], 0
0x1800080a0  xor     eax, eax
0x1800080a2  mov     [rdx+14h], ax
0x1800080a6  jmp     loc_18000821E
0x1800080ab  mov     rax, [rcx+68h]
0x1800080af  mov     rdi, [rax]
0x1800080b2  cmp     byte ptr [rcx+99h], 0
0x1800080b9  jz      short loc_18000812F
0x1800080bb  mov     ebx, [rcx+1Ch]
0x1800080be  call    cs:__imp_GetCurrentThreadId
0x1800080c4  mov     cl, [rsi+99h]
0x1800080ca  xor     ebx, eax
0x1800080cc  test    ebx, 0FFFFFFFCh
0x1800080d2  jz      short loc_180008135
0x1800080d4  test    cl, cl
0x1800080d6  jz      short loc_1800080E9
0x1800080d8  mov     eax, [rsi+18h]
0x1800080db  and     eax, 7FFFh
0x1800080e0  cmp     eax, 1
0x1800080e3  jb      loc_180008193
0x1800080e9  cmp     byte ptr [rsi+99h], 0
0x1800080f0  jz      loc_180008193
0x1800080f6  mov     edx, [rdi]
0x1800080f8  test    edx, 0FFFF8000h
0x1800080fe  jnz     short loc_18000810D
0x180008100  lea     ecx, [rdx+1]
0x180008103  mov     eax, edx
0x180008105  lock cmpxchg [rdi], ecx
0x180008109  cmp     edx, eax
0x18000810b  jz      short loc_180008117
0x18000810d  xor     edx, edx; bool
0x18000810f  mov     rcx, rdi; this
0x180008112  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x180008117  cmp     byte ptr [rsi+99h], 0
0x18000811e  jz      short loc_180008193
0x180008120  mov     edx, [rdi]
0x180008122  lea     ecx, [rdx-1]
0x180008125  mov     eax, edx
0x180008127  lock cmpxchg [rdi], ecx
0x18000812b  cmp     edx, eax
0x18000812d  jmp     short loc_18000811E
0x18000812f  mov     cl, [rcx+99h]
0x180008135  test    cl, cl
0x180008137  jz      short loc_180008172
0x180008139  mov     edx, [rdi]
0x18000813b  test    dx, dx
0x18000813e  jnz     short loc_180008156
0x180008140  lea     ecx, [rdx+10000h]
0x180008146  or      ecx, 0FFFFh
0x18000814c  mov     eax, edx
0x18000814e  lock cmpxchg [rdi], ecx
0x180008152  cmp     edx, eax
0x180008154  jz      short loc_180008172
0x180008156  mov     edx, [rdi]
0x180008158  lea     ecx, [rdx+10000h]
0x18000815e  mov     eax, edx
0x180008160  lock cmpxchg [rdi], ecx
0x180008164  cmp     edx, eax
0x180008166  jnz     short loc_180008156
0x180008168  mov     dl, 1; bool
0x18000816a  mov     rcx, rdi; this
0x18000816d  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x180008172  cmp     byte ptr [rsi+99h], 0
0x180008179  jz      short loc_180008193
0x18000817b  mov     edx, [rdi]
0x18000817d  lea     ecx, [rdx-10000h]
0x180008183  and     ecx, 0FFFF0000h
0x180008189  mov     eax, edx
0x18000818b  lock cmpxchg [rdi], ecx
0x18000818f  cmp     edx, eax
0x180008191  jmp     short loc_180008179
0x180008193  mov     [rbp+var_18], rsi
0x180008197  lea     rax, [rdi+8]
0x18000819b  mov     [rbp+var_10], rax
0x18000819f  mov     [rbp+var_8], 0
0x1800081a6  or      ebx, 0FFFFFFFFh
0x1800081a9  mov     [rbp+var_4], bx
0x1800081ad  xor     edx, edx; bool
0x1800081af  lea     rcx, [rbp+var_18]; this
0x1800081b3  call    ?_Increment@CLKRLinearHashTable_Iterator@LKRhash@@IEAA_N_N@Z; LKRhash::CLKRLinearHashTable_Iterator::_Increment(bool)
0x1800081b8  mov     r8, [rbp+var_18]
0x1800081bc  mov     [r14], r8
0x1800081bf  mov     r9, [rbp+var_10]
0x1800081c3  mov     [r14+8], r9
0x1800081c7  mov     eax, [rbp+var_8]
0x1800081ca  mov     [r14+10h], eax
0x1800081ce  movsx   rax, [rbp+var_4]
0x1800081d3  mov     [r14+14h], ax
0x1800081d8  test    r8, r8
0x1800081db  jz      short loc_1800081FF
0x1800081dd  cmp     ax, bx
0x1800081e0  jz      short loc_1800081FF
0x1800081e2  lea     edx, [rbx+2]
0x1800081e5  mov     rcx, [r9+rax*8+18h]
0x1800081ea  mov     rax, [r8+38h]
0x1800081ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081f3  movzx   eax, [rbp+var_4]
0x1800081f7  mov     r9, [rbp+var_10]
0x1800081fb  mov     r8, [rbp+var_18]
0x1800081ff  test    r8, r8
0x180008202  jz      short loc_18000821E
0x180008204  cmp     ax, bx
0x180008207  jz      short loc_18000821E
0x180008209  movsx   rcx, ax
0x18000820d  mov     edx, ebx
0x18000820f  mov     rcx, [r9+rcx*8+18h]
0x180008214  mov     rax, [r8+38h]
0x180008218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000821d  nop
0x18000821e  mov     rax, r14
0x180008221  add     rsp, 40h
0x180008225  pop     r14
0x180008227  pop     rdi
0x180008228  pop     rsi
0x180008229  pop     rbx
0x18000822a  pop     rbp
0x18000822b  retn
```
