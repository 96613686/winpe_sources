# utl::vector<utl::unique_ptr<_URB,utl::default_delete<_URB>>,utl::allocator<utl::unique_ptr<_URB,utl::default_delete<_URB>>>>::_SetCapacity(unsigned __int64)

- ea: `0x140002944`
- end: `0x140002a8b`
- name: `?_SetCapacity@?$vector@V?$unique_ptr@U_URB@@U?$default_delete@U_URB@@@utl@@@utl@@V?$allocator@V?$unique_ptr@U_URB@@U?$default_delete@U_URB@@@utl@@@utl@@@2@@utl@@AEAA_N_K@Z`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140002a94`

## callees

- `0x140001ed0`
- `0x140002944`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000297b`
- `ntoskrnl!ExAllocatePool2` at `0x14000297b`
- `ntoskrnl!ExFreePool` at `0x140002a27`
- `ntoskrnl!ExFreePool` at `0x140002a40`
- `ntoskrnl!ExFreePool` at `0x140002a27`
- `ntoskrnl!ExFreePool` at `0x140002a40`

## pseudocode

```c
char __fastcall utl::vector<utl::unique_ptr<_URB,utl::default_delete<_URB>>,utl::allocator<utl::unique_ptr<_URB,utl::default_delete<_URB>>>>::_SetCapacity(
        __int64 a1,
        unsigned __int64 a2)
{
  __int64 v2; // rdi
  __int64 Pool2; // rbx
  __int64 v5; // r15
  char v6; // bp
  _QWORD *v7; // r8
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rax
  _QWORD *v11; // r14
  __int64 v12; // rdi
  __int64 v13; // r12
  void *v14; // rcx
  __m128i si128; // [rsp+20h] [rbp-58h] BYREF
  __int64 v17; // [rsp+30h] [rbp-48h]

  v2 = 8 * a2;
  if ( a2 > 0x1FFFFFFFFFFFFFFFLL )
    Pool2 = 0;
  else
    Pool2 = ExAllocatePool2(64, v2, 1111642965);
  si128.m128i_i64[0] = Pool2;
  if ( !Pool2 )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    v17 = -1;
LABEL_7:
    v6 = 0;
    goto LABEL_18;
  }
  si128.m128i_i64[1] = Pool2;
  v5 = v2 + Pool2;
  v17 = v2 + Pool2;
  if ( Pool2 == -1 )
    goto LABEL_7;
  v7 = *(_QWORD **)a1;
  v8 = 0;
  v9 = (__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 3;
  v6 = 1;
  if ( v9 )
  {
    do
    {
      v10 = v7[v8];
      v7[v8] = 0;
      *(_QWORD *)(Pool2 + 8 * v8++) = v10;
    }
    while ( v8 != v9 );
  }
  v11 = *(_QWORD **)a1;
  v12 = (__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 3;
  v13 = Pool2 + 8 * v12;
  if ( *(_QWORD *)a1 != -1 )
  {
    *(_QWORD *)(a1 + 8) = v11;
    while ( v12 )
    {
      v14 = (void *)v11[--v12];
      if ( v14 )
        ExFreePool(v14);
    }
    if ( *(_QWORD *)a1 )
      ExFreePool(*(PVOID *)a1);
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  *(_QWORD *)a1 = Pool2;
  *(_QWORD *)(a1 + 8) = v13;
  *(_QWORD *)(a1 + 16) = v5;
  v17 = -1;
LABEL_18:
  utl::vector<utl::unique_ptr<_URB,utl::default_delete<_URB>>,utl::allocator<utl::unique_ptr<_URB,utl::default_delete<_URB>>>>::~vector<utl::unique_ptr<_URB,utl::default_delete<_URB>>,utl::allocator<utl::unique_ptr<_URB,utl::default_delete<_URB>>>>(&si128);
  return v6;
}

```

## disassembly

```asm
0x140002944  push    rbx
0x140002946  push    rbp
0x140002947  push    rsi
0x140002948  push    rdi
0x140002949  push    r12
0x14000294b  push    r14
0x14000294d  push    r15
0x14000294f  sub     rsp, 40h
0x140002953  mov     rax, 1FFFFFFFFFFFFFFFh
0x14000295d  lea     rdi, ds:0[rdx*8]
0x140002965  mov     rsi, rcx
0x140002968  cmp     rdx, rax
0x14000296b  ja      short loc_14000298C
0x14000296d  mov     r8d, 42425355h
0x140002973  mov     rdx, rdi
0x140002976  mov     ecx, 40h ; '@'
0x14000297b  call    cs:__imp_ExAllocatePool2
0x140002982  nop     dword ptr [rax+rax+00h]
0x140002987  mov     rbx, rax
0x14000298a  jmp     short loc_14000298E
0x14000298c  xor     ebx, ebx
0x14000298e  mov     qword ptr [rsp+78h+var_58], rbx
0x140002993  test    rbx, rbx
0x140002996  jnz     short loc_1400029B1
0x140002998  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1400029a0  movdqu  [rsp+78h+var_58], xmm0
0x1400029a6  mov     [rsp+78h+var_48], 0FFFFFFFFFFFFFFFFh
0x1400029af  jmp     short loc_1400029C5
0x1400029b1  mov     qword ptr [rsp+78h+var_58+8], rbx
0x1400029b6  lea     r15, [rdi+rbx]
0x1400029ba  mov     [rsp+78h+var_48], r15
0x1400029bf  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400029c3  jnz     short loc_1400029CD
0x1400029c5  xor     bpl, bpl
0x1400029c8  jmp     loc_140002A6E
0x1400029cd  mov     r8, [rsi]
0x1400029d0  xor     ecx, ecx
0x1400029d2  mov     rdx, [rsi+8]
0x1400029d6  sub     rdx, r8
0x1400029d9  sar     rdx, 3
0x1400029dd  lea     ebp, [rcx+1]
0x1400029e0  test    rdx, rdx
0x1400029e3  jz      short loc_1400029FD
0x1400029e5  mov     rax, [r8+rcx*8]
0x1400029e9  mov     qword ptr [r8+rcx*8], 0
0x1400029f1  mov     [rbx+rcx*8], rax
0x1400029f5  add     rcx, rbp
0x1400029f8  cmp     rcx, rdx
0x1400029fb  jnz     short loc_1400029E5
0x1400029fd  mov     r14, [rsi]
0x140002a00  mov     rdi, [rsi+8]
0x140002a04  sub     rdi, r14
0x140002a07  sar     rdi, 3
0x140002a0b  lea     r12, [rbx+rdi*8]
0x140002a0f  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x140002a13  jz      short loc_140002A4C
0x140002a15  mov     [rsi+8], r14
0x140002a19  jmp     short loc_140002A33
0x140002a1b  sub     rdi, rbp
0x140002a1e  mov     rcx, [r14+rdi*8]; P
0x140002a22  test    rcx, rcx
0x140002a25  jz      short loc_140002A33
0x140002a27  call    cs:__imp_ExFreePool
0x140002a2e  nop     dword ptr [rax+rax+00h]
0x140002a33  test    rdi, rdi
0x140002a36  jnz     short loc_140002A1B
0x140002a38  mov     rcx, [rsi]; P
0x140002a3b  test    rcx, rcx
0x140002a3e  jz      short loc_140002A4C
0x140002a40  call    cs:__imp_ExFreePool
0x140002a47  nop     dword ptr [rax+rax+00h]
0x140002a4c  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140002a54  movdqu  [rsp+78h+var_58], xmm0
0x140002a5a  mov     [rsi], rbx
0x140002a5d  mov     [rsi+8], r12
0x140002a61  mov     [rsi+10h], r15
0x140002a65  mov     [rsp+78h+var_48], 0FFFFFFFFFFFFFFFFh
0x140002a6e  lea     rcx, [rsp+78h+var_58]
0x140002a73  call    ??1?$vector@V?$unique_ptr@U_URB@@U?$default_delete@U_URB@@@utl@@@utl@@V?$allocator@V?$unique_ptr@U_URB@@U?$default_delete@U_URB@@@utl@@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::unique_ptr<_URB,utl::default_delete<_URB>>,utl::allocator<utl::unique_ptr<_URB,utl::default_delete<_URB>>>>::~vector<utl::unique_ptr<_URB,utl::default_delete<_URB>>,utl::allocator<utl::unique_ptr<_URB,utl::default_delete<_URB>>>>(void)
0x140002a78  mov     al, bpl
0x140002a7b  add     rsp, 40h
0x140002a7f  pop     r15
0x140002a81  pop     r14
0x140002a83  pop     r12
0x140002a85  pop     rdi
0x140002a86  pop     rsi
0x140002a87  pop     rbp
0x140002a88  pop     rbx
0x140002a89  retn
```
