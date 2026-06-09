# AppHashComputeFileHashesInternal

- ea: `0x140003598`
- end: `0x140003727`
- name: `AppHashComputeFileHashesInternal`
- size: `399`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, char *, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140003570`
- `0x1400360a0`

## callees

- `0x140003598`
- `0x140006a20`
- `0x140006f40`
- `0x140029db4`
- `0x14002a33c`
- `0x14002a3fc`

## pseudocode

```c
__int64 __fastcall AppHashComputeFileHashesInternal(__int64 a1, __int64 a2, __int64 a3, char *a4, __int64 a5)
{
  __int64 v5; // rsi
  __int64 v7; // rcx
  __int64 *v8; // r15
  unsigned int v9; // r12d
  __int64 v10; // r14
  __int64 v11; // r13
  __int64 v12; // rsi
  int inited; // ebx
  unsigned int v14; // eax
  __int64 i; // rdi
  _QWORD v21[12]; // [rsp+50h] [rbp-A8h] BYREF

  v5 = a3;
  memset(v21, 0, sizeof(v21));
  memset(a4, 0, 0x60u);
  v7 = a5;
  v8 = AppHashSupportedAttributes;
  v9 = 0;
  v10 = 0;
  while ( (unsigned int)v10 < 3 )
  {
    v11 = 4 * v10;
    if ( *(_DWORD *)(v5 + 4 * v10) )
    {
      v12 = 4LL * v9;
      inited = AppHashInitHash(*(&AppHashAlgHandle + *((int *)v8 + 1)), (BCRYPT_HASH_HANDLE *)&v21[v12]);
      if ( inited < 0 )
      {
        AppHashDestroyHash(&v21[v12]);
        goto LABEL_12;
      }
      v14 = WORD2(v21[4 * v9 + 2]);
      if ( v14 > 0x20 )
      {
        AppHashDestroyHash(&v21[v12]);
        inited = -1073741789;
        goto LABEL_12;
      }
      LODWORD(v21[4 * v9++ + 2]) = *((_DWORD *)v8 + 2);
      v7 = a5;
      v21[v12 + 3] = &a4[32 * (unsigned int)v10];
      v5 = a3;
    }
    else
    {
      v14 = 0;
    }
    v10 = (unsigned int)(v10 + 1);
    *(_DWORD *)(v7 + v11) = v14;
    v8 = (__int64 *)((char *)v8 + 12);
  }
  inited = AppHashComputeImageHashInternal(a1, a2, v9, v21);
LABEL_12:
  for ( i = 0; i != 3; ++i )
    AppHashDestroyHash(&v21[4 * i]);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x140003598  mov     [rsp+arg_10], rbx
0x14000359d  push    rbp
0x14000359e  push    rsi
0x14000359f  push    rdi
0x1400035a0  push    r12
0x1400035a2  push    r13
0x1400035a4  push    r14
0x1400035a6  push    r15
0x1400035a8  sub     rsp, 0C0h
0x1400035af  mov     rax, cs:__security_cookie
0x1400035b6  xor     rax, rsp
0x1400035b9  mov     [rsp+0F8h+var_48], rax
0x1400035c1  mov     rax, [rsp+0F8h+arg_20]
0x1400035c9  mov     rsi, r8
0x1400035cc  mov     [rsp+0F8h+var_C8], r8
0x1400035d1  xor     ebx, ebx
0x1400035d3  mov     [rsp+0F8h+var_C0], rdx
0x1400035d8  mov     rdi, r9
0x1400035db  mov     [rsp+0F8h+var_B8], rcx
0x1400035e0  xor     edx, edx; Val
0x1400035e2  lea     rcx, [rsp+0F8h+var_A8]; void *
0x1400035e7  mov     [rsp+0F8h+var_D0], r9
0x1400035ec  lea     ebp, [rbx+60h]
0x1400035ef  mov     [rsp+0F8h+var_D8], rax
0x1400035f4  mov     r8d, ebp; Size
0x1400035f7  call    memset
0x1400035fc  mov     r8d, ebp; Size
0x1400035ff  xor     edx, edx; Val
0x140003601  mov     rcx, rdi; void *
0x140003604  call    memset
0x140003609  mov     rcx, [rsp+0F8h+var_D8]
0x14000360e  lea     r15, AppHashSupportedAttributes
0x140003615  xor     r12d, r12d
0x140003618  xor     r14d, r14d
0x14000361b  cmp     r14d, 3
0x14000361f  jnb     loc_1400036BD
0x140003625  lea     r13, ds:0[r14*4]
0x14000362d  mov     edi, r14d
0x140003630  cmp     dword ptr [rsi+r13], 0
0x140003635  jz      short loc_140003692
0x140003637  movsxd  rcx, dword ptr [r15+4]
0x14000363b  lea     rax, AppHashAlgHandle
0x140003642  mov     esi, r12d
0x140003645  lea     rbp, [rsp+0F8h+var_A8]
0x14000364a  shl     rsi, 5
0x14000364e  add     rbp, rsi
0x140003651  mov     rcx, [rax+rcx*8]; hAlgorithm
0x140003655  mov     rdx, rbp; phHash
0x140003658  call    AppHashInitHash
0x14000365d  mov     ebx, eax
0x14000365f  test    eax, eax
0x140003661  js      short loc_1400036B3
0x140003663  movzx   eax, [rsp+rsi+0F8h+var_94]
0x140003668  cmp     eax, 20h ; ' '
0x14000366b  ja      short loc_1400036A4
0x14000366d  mov     ecx, [r15+8]
0x140003671  shl     rdi, 5
0x140003675  add     rdi, [rsp+0F8h+var_D0]
0x14000367a  mov     [rsp+rsi+0F8h+var_98], ecx
0x14000367e  inc     r12d
0x140003681  mov     rcx, [rsp+0F8h+var_D8]
0x140003686  mov     [rsp+rsi+0F8h+var_90], rdi
0x14000368b  mov     rsi, [rsp+0F8h+var_C8]
0x140003690  jmp     short loc_140003694
0x140003692  xor     eax, eax
0x140003694  inc     r14d
0x140003697  mov     [rcx+r13], eax
0x14000369b  add     r15, 0Ch
0x14000369f  jmp     loc_14000361B
0x1400036a4  mov     rcx, rbp
0x1400036a7  call    AppHashDestroyHash
0x1400036ac  mov     ebx, 0C0000023h
0x1400036b1  jmp     short loc_1400036DA
0x1400036b3  mov     rcx, rbp
0x1400036b6  call    AppHashDestroyHash
0x1400036bb  jmp     short loc_1400036DA
0x1400036bd  test    ebx, ebx
0x1400036bf  js      short loc_1400036DA
0x1400036c1  mov     rdx, [rsp+0F8h+var_C0]
0x1400036c6  lea     r9, [rsp+0F8h+var_A8]
0x1400036cb  mov     rcx, [rsp+0F8h+var_B8]
0x1400036d0  mov     r8d, r12d
0x1400036d3  call    AppHashComputeImageHashInternal
0x1400036d8  mov     ebx, eax
0x1400036da  xor     edi, edi
0x1400036dc  mov     rax, rdi
0x1400036df  lea     rcx, [rsp+0F8h+var_A8]
0x1400036e4  shl     rax, 5
0x1400036e8  add     rcx, rax
0x1400036eb  call    AppHashDestroyHash
0x1400036f0  inc     rdi
0x1400036f3  cmp     rdi, 3
0x1400036f7  jnz     short loc_1400036DC
0x1400036f9  mov     eax, ebx
0x1400036fb  mov     rcx, [rsp+0F8h+var_48]
0x140003703  xor     rcx, rsp; StackCookie
0x140003706  call    __security_check_cookie
0x14000370b  mov     rbx, [rsp+0F8h+arg_10]
0x140003713  add     rsp, 0C0h
0x14000371a  pop     r15
0x14000371c  pop     r14
0x14000371e  pop     r13
0x140003720  pop     r12
0x140003722  pop     rdi
0x140003723  pop     rsi
0x140003724  pop     rbp
0x140003725  retn
```
