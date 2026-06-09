# VfsMergeDirectory

- ea: `0x14000652c`
- end: `0x140006707`
- name: `VfsMergeDirectory`
- size: `475`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140006998`

## callees

- `0x14000652c`
- `0x140006c10`
- `0x140013d00`

## pseudocode

```c
__int64 __fastcall VfsMergeDirectory(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  unsigned int *v7; // r14
  unsigned int v8; // esi
  char v9; // r8
  BOOLEAN v10; // al
  char i; // r8
  int v12; // edi
  unsigned int v13; // eax
  __int64 v14; // rax
  unsigned int v15; // ecx
  char v17; // [rsp+40h] [rbp-78h]
  BOOLEAN v18; // [rsp+41h] [rbp-77h]
  unsigned int Size; // [rsp+44h] [rbp-74h] BYREF
  unsigned int Size_4; // [rsp+48h] [rbp-70h]
  int v21; // [rsp+4Ch] [rbp-6Ch] BYREF
  unsigned int v22; // [rsp+50h] [rbp-68h]
  void *Src; // [rsp+58h] [rbp-60h] BYREF
  __int64 v24; // [rsp+60h] [rbp-58h] BYREF
  unsigned int *v25; // [rsp+68h] [rbp-50h]
  __int64 v26; // [rsp+70h] [rbp-48h]

  v26 = a2;
  v7 = 0;
  v25 = 0;
  v8 = 0;
  Size_4 = 0;
  v9 = *(_BYTE *)(*(_QWORD *)(a1 + 16) + 6LL);
  v17 = v9 & 2;
  v10 = (v9 & 2) != 0;
  v18 = v10;
  for ( i = v9 & 1; ; i = 0 )
  {
    Src = 0;
    Size = 0;
    v21 = 0;
    v24 = 0;
    v12 = VfsQueryDirectoryRecord(a2, v10, i, (__int64 *)&Src, &Size, &v21, &v24);
    if ( v12 == -1073741809 )
      break;
    if ( v12 == -2147483642 )
    {
      if ( v8 )
      {
        v12 = 0;
      }
      else if ( (*(_DWORD *)a2 & 1) != 0 )
      {
        v12 = -1073741809;
      }
      break;
    }
    if ( v12 < 0 )
      goto LABEL_21;
    v22 = (Size + 7) & 0xFFFFFFF8;
    if ( v22 > a4 - v8 )
    {
      if ( !v8 )
        v12 = -2147483643;
      break;
    }
    v7 = (unsigned int *)(a3 + v8);
    memmove(v7, Src, Size);
    v25 = v7;
    v13 = v22;
    *v7 = v22;
    v8 += v13;
    Size_4 = v8;
    v14 = v24;
    if ( v21 )
    {
      v15 = Size;
      *(_DWORD *)(v24 + 60) -= Size;
      *(_DWORD *)(v14 + 64) += v15;
    }
    else
    {
      *(_QWORD *)(v24 + 60) = 0;
    }
    if ( v17 )
      break;
    v10 = v18;
  }
  if ( v12 >= 0 )
  {
    if ( v7 )
      *v7 = 0;
    *(_DWORD *)(a1 + 24) = v12;
    *(_QWORD *)(a1 + 32) = v8;
  }
LABEL_21:
  *(_DWORD *)a2 &= ~1u;
  _InterlockedExchange((volatile __int32 *)(a2 + 4), 0);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14000652c  mov     rax, rsp
0x14000652f  mov     [rax+20h], r9d
0x140006533  mov     [rax+18h], r8
0x140006537  mov     [rax+10h], rdx
0x14000653b  mov     [rax+8], rcx
0x14000653f  push    rbx
0x140006540  push    rsi
0x140006541  push    rdi
0x140006542  push    r12
0x140006544  push    r13
0x140006546  push    r14
0x140006548  push    r15
0x14000654a  sub     rsp, 80h
0x140006551  mov     r12, rdx
0x140006554  mov     r13, rcx
0x140006557  mov     r15, rdx
0x14000655a  mov     [rsp+0B8h+var_48], rdx
0x14000655f  xor     ebx, ebx
0x140006561  mov     r14d, ebx
0x140006564  mov     [rsp+0B8h+var_50], rbx
0x140006569  mov     esi, ebx
0x14000656b  mov     dword ptr [rsp+0B8h+Size+4], ebx
0x14000656f  mov     rax, [rcx+10h]
0x140006573  mov     r8b, [rax+6]
0x140006577  mov     al, r8b
0x14000657a  and     al, 2
0x14000657c  mov     [rsp+0B8h+var_78], al
0x140006580  setnz   al
0x140006583  mov     [rsp+0B8h+var_77], al
0x140006587  and     r8b, 1
0x14000658b  mov     [rsp+0B8h+Src], rbx
0x140006590  mov     dword ptr [rsp+0B8h+Size], ebx
0x140006594  mov     [rsp+0B8h+var_6C], ebx
0x140006598  mov     [rsp+0B8h+var_58], rbx
0x14000659d  lea     rcx, [rsp+0B8h+var_58]
0x1400065a2  mov     [rsp+0B8h+var_88], rcx
0x1400065a7  lea     rcx, [rsp+0B8h+var_6C]
0x1400065ac  mov     [rsp+0B8h+var_90], rcx
0x1400065b1  lea     rcx, [rsp+0B8h+Size]
0x1400065b6  mov     [rsp+0B8h+var_98], rcx
0x1400065bb  lea     r9, [rsp+0B8h+Src]
0x1400065c0  mov     dl, al
0x1400065c2  mov     rcx, r12
0x1400065c5  call    VfsQueryDirectoryRecord
0x1400065ca  mov     edi, eax
0x1400065cc  mov     eax, 0C000000Fh
0x1400065d1  cmp     edi, eax
0x1400065d3  jz      loc_1400066AF
0x1400065d9  cmp     edi, 80000006h
0x1400065df  jnz     short loc_140006600
0x1400065e1  test    esi, esi
0x1400065e3  jnz     short loc_1400065F9
0x1400065e5  mov     ecx, [r12]
0x1400065e9  test    cl, 1
0x1400065ec  jz      loc_1400066AF
0x1400065f2  mov     edi, eax
0x1400065f4  jmp     loc_1400066AF
0x1400065f9  mov     edi, ebx
0x1400065fb  jmp     loc_1400066AF
0x140006600  test    edi, edi
0x140006602  js      loc_1400066E8
0x140006608  mov     edx, dword ptr [rsp+0B8h+Size]
0x14000660c  lea     ecx, [rdx+7]
0x14000660f  and     ecx, 0FFFFFFF8h
0x140006612  mov     [rsp+0B8h+var_68], ecx
0x140006616  mov     eax, [rsp+0B8h+arg_18]
0x14000661d  sub     eax, esi
0x14000661f  cmp     ecx, eax
0x140006621  jbe     short loc_140006632
0x140006623  test    esi, esi
0x140006625  jnz     loc_1400066AF
0x14000662b  mov     edi, 80000005h
0x140006630  jmp     short loc_1400066AF
0x140006632  mov     r14d, esi
0x140006635  add     r14, [rsp+0B8h+arg_10]
0x14000663d  mov     r8, rdx; Size
0x140006640  mov     rdx, [rsp+0B8h+Src]; Src
0x140006645  mov     rcx, r14; void *
0x140006648  call    memmove
0x14000664d  nop
0x14000664e  mov     [rsp+0B8h+var_50], r14
0x140006653  mov     eax, [rsp+0B8h+var_68]
0x140006657  mov     [r14], eax
0x14000665a  add     esi, eax
0x14000665c  mov     dword ptr [rsp+0B8h+Size+4], esi
0x140006660  mov     rax, [rsp+0B8h+var_58]
0x140006665  cmp     [rsp+0B8h+var_6C], ebx
0x140006669  jnz     short loc_140006671
0x14000666b  mov     [rax+3Ch], rbx
0x14000666f  jmp     short loc_14000667B
0x140006671  mov     ecx, dword ptr [rsp+0B8h+Size]
0x140006675  sub     [rax+3Ch], ecx
0x140006678  add     [rax+40h], ecx
0x14000667b  cmp     [rsp+0B8h+var_78], bl
0x14000667f  jnz     short loc_1400066AF
0x140006681  mov     r8b, bl
0x140006684  mov     al, [rsp+0B8h+var_77]
0x140006688  jmp     loc_14000658B
0x14000668d  mov     edi, eax
0x14000668f  xor     ebx, ebx
0x140006691  mov     r12, [rsp+0B8h+arg_8]
0x140006699  mov     r13, [rsp+0B8h+arg_0]
0x1400066a1  mov     r14, [rsp+0B8h+var_50]
0x1400066a6  mov     esi, dword ptr [rsp+0B8h+Size+4]
0x1400066aa  mov     r15, [rsp+0B8h+var_48]
0x1400066af  test    edi, edi
0x1400066b1  js      short loc_1400066E8
0x1400066b3  test    r14, r14
0x1400066b6  jz      short loc_1400066DA
0x1400066b8  mov     [r14], ebx
0x1400066bb  jmp     short loc_1400066DA
0x1400066bd  mov     edi, eax
0x1400066bf  xor     ebx, ebx
0x1400066c1  mov     r12, [rsp+0B8h+arg_8]
0x1400066c9  mov     r13, [rsp+0B8h+arg_0]
0x1400066d1  mov     esi, dword ptr [rsp+0B8h+Size+4]
0x1400066d5  mov     r15, [rsp+0B8h+var_48]
0x1400066da  test    edi, edi
0x1400066dc  js      short loc_1400066E8
0x1400066de  mov     [r13+18h], edi
0x1400066e2  mov     eax, esi
0x1400066e4  mov     [r13+20h], rax
0x1400066e8  and     dword ptr [r15], 0FFFFFFFEh
0x1400066ec  xchg    ebx, [r12+4]
0x1400066f1  mov     eax, edi
0x1400066f3  add     rsp, 80h
0x1400066fa  pop     r15
0x1400066fc  pop     r14
0x1400066fe  pop     r13
0x140006700  pop     r12
0x140006702  pop     rdi
0x140006703  pop     rsi
0x140006704  pop     rbx
0x140006705  retn
```
