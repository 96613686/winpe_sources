# CStreamParser::CopyStream(uchar *,int,CTStickyVal<int> *)

- ea: `0x180029040`
- end: `0x18002912b`
- name: `?CopyStream@CStreamParser@@IEAAHPEAEHPEAV?$CTStickyVal@H@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(_DWORD *, unsigned __int8 *, int, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800218c0`
- `0x180021980`
- `0x1800299a0`

## callees

- `0x180028dc4`
- `0x180028fd8`
- `0x180029040`
- `0x180029208`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x1800290c3`
- `KERNEL32!GetTickCount` at `0x1800290c3`

## pseudocode

```c
__int64 __fastcall CStreamParser::CopyStream(_DWORD *a1, unsigned __int8 *a2, int a3, __int64 a4)
{
  unsigned int v8; // esi
  int v9; // ebx
  int v10; // ecx
  int v12; // [rsp+20h] [rbp-48h] BYREF
  int v13[17]; // [rsp+24h] [rbp-44h] BYREF

  v8 = 0;
  while ( a3 > 0 )
  {
    v13[0] = 0;
    v12 = 0;
    if ( (unsigned int)CBufferSourceManager::CopyBlock((CBufferSourceManager *)(a1 + 12), a2, a3, v13) )
    {
      v9 = a3;
LABEL_11:
      if ( !v13[0] )
        CBufferSourceManager::Complete(a1 + 12, a4);
      v10 = 1;
      goto LABEL_15;
    }
    v9 = v13[0];
    if ( v13[0] <= 0 )
    {
      v12 = a1[94];
      if ( (int)CBufferSourceManager::GetNewCopyBuffer((CBufferSourceManager *)(a1 + 12), &v12) < 0 )
        goto LABEL_14;
      v9 = a3;
      if ( v12 < a3 )
        v9 = v12;
      a1[7] = GetTickCount();
    }
    if ( (unsigned int)CBufferSourceManager::CopyBlock((CBufferSourceManager *)(a1 + 12), a2, v9, v13) )
      goto LABEL_11;
LABEL_14:
    v9 = 0;
    v10 = 0;
LABEL_15:
    if ( (int)(v8 + v9) >= (int)v8 )
    {
      a3 -= v9;
      a2 += v9;
      v8 += v9;
      if ( v10 )
        continue;
    }
    return v8;
  }
  return v8;
}

```

## disassembly

```asm
0x180029040  push    rbx
0x180029042  push    rbp
0x180029043  push    rsi
0x180029044  push    rdi
0x180029045  push    r12
0x180029047  push    r14
0x180029049  push    r15
0x18002904b  sub     rsp, 30h
0x18002904f  mov     r12, r9
0x180029052  mov     edi, r8d
0x180029055  mov     r14, rdx
0x180029058  mov     r15, rcx
0x18002905b  xor     esi, esi
0x18002905d  test    edi, edi
0x18002905f  jle     loc_18002911A
0x180029065  lea     rbp, [r15+30h]
0x180029069  mov     [rsp+68h+var_44], 0
0x180029071  mov     rcx, rbp; this
0x180029074  mov     [rsp+68h+var_48], 0
0x18002907c  lea     r9, [rsp+68h+var_44]; int *
0x180029081  mov     r8d, edi; int
0x180029084  mov     rdx, r14; unsigned __int8 *
0x180029087  call    ?CopyBlock@CBufferSourceManager@@IEAAHPEAEHPEAH@Z; CBufferSourceManager::CopyBlock(uchar *,int,int *)
0x18002908c  test    eax, eax
0x18002908e  jz      short loc_180029094
0x180029090  mov     ebx, edi
0x180029092  jmp     short loc_1800290E4
0x180029094  mov     ebx, [rsp+68h+var_44]
0x180029098  test    ebx, ebx
0x18002909a  jg      short loc_1800290CD
0x18002909c  mov     eax, [r15+178h]
0x1800290a3  lea     rdx, [rsp+68h+var_48]; int *
0x1800290a8  mov     rcx, rbp; this
0x1800290ab  mov     [rsp+68h+var_48], eax
0x1800290af  call    ?GetNewCopyBuffer@CBufferSourceManager@@IEAAJPEAH@Z; CBufferSourceManager::GetNewCopyBuffer(int *)
0x1800290b4  test    eax, eax
0x1800290b6  js      short loc_1800290FD
0x1800290b8  cmp     [rsp+68h+var_48], edi
0x1800290bc  mov     ebx, edi
0x1800290be  cmovl   ebx, [rsp+68h+var_48]
0x1800290c3  call    cs:__imp_GetTickCount
0x1800290c9  mov     [r15+1Ch], eax
0x1800290cd  lea     r9, [rsp+68h+var_44]; int *
0x1800290d2  mov     r8d, ebx; int
0x1800290d5  mov     rdx, r14; unsigned __int8 *
0x1800290d8  mov     rcx, rbp; this
0x1800290db  call    ?CopyBlock@CBufferSourceManager@@IEAAHPEAEHPEAH@Z; CBufferSourceManager::CopyBlock(uchar *,int,int *)
0x1800290e0  test    eax, eax
0x1800290e2  jz      short loc_1800290FD
0x1800290e4  cmp     [rsp+68h+var_44], 0
0x1800290e9  jnz     short loc_1800290F6
0x1800290eb  mov     rdx, r12
0x1800290ee  mov     rcx, rbp
0x1800290f1  call    ?Complete@CBufferSourceManager@@IEAAJPEAV?$CTStickyVal@H@@@Z; CBufferSourceManager::Complete(CTStickyVal<int> *)
0x1800290f6  mov     ecx, 1
0x1800290fb  jmp     short loc_180029101
0x1800290fd  xor     ebx, ebx
0x1800290ff  xor     ecx, ecx
0x180029101  lea     edx, [rsi+rbx]
0x180029104  cmp     edx, esi
0x180029106  jl      short loc_18002911A
0x180029108  movsxd  rax, ebx
0x18002910b  sub     edi, ebx
0x18002910d  add     r14, rax
0x180029110  mov     esi, edx
0x180029112  test    ecx, ecx
0x180029114  jnz     loc_18002905D
0x18002911a  mov     eax, esi
0x18002911c  add     rsp, 30h
0x180029120  pop     r15
0x180029122  pop     r14
0x180029124  pop     r12
0x180029126  pop     rdi
0x180029127  pop     rsi
0x180029128  pop     rbp
0x180029129  pop     rbx
0x18002912a  retn
```
