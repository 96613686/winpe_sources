# std::_Median_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent_______lambda_4e00c4f2fc8604fa547e688629cc8b0c___

- ea: `0x18000fc38`
- end: `0x18000fe34`
- name: `std::_Median_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent_______lambda_4e00c4f2fc8604fa547e688629cc8b0c___`
- size: `508`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000fe3c`

## callees

- `0x18000fc38`

## pseudocode

```c
unsigned __int8 __fastcall std::_Median_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent_______lambda_4e00c4f2fc8604fa547e688629cc8b0c___(
        __int64 *a1,
        __int64 *a2,
        __int64 *a3)
{
  __int64 v3; // r11
  __int64 v5; // rax
  __int64 v7; // rax
  __int64 v8; // r14
  __int64 v9; // r8
  __int64 v10; // rbx
  __int64 v11; // r11
  __int64 v12; // rdx
  __int64 v13; // rsi
  __int64 *v14; // r11
  __int64 v15; // rbx
  __int64 v16; // rdx
  __int64 *v17; // rbx
  __int64 *v18; // r11
  __int64 v19; // rsi
  __int64 v20; // rbp
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rbx
  __int64 v24; // rdx
  unsigned __int8 result; // al
  __int64 v26; // r11
  __int64 v27; // r8
  __int64 v28; // rdx

  v3 = *a1;
  v5 = a3 - a1;
  if ( v5 <= 40 )
  {
    v27 = *a2;
    if ( *(_BYTE *)(*(_QWORD *)(*a2 + 16) + 8LL) < *(_BYTE *)(*(_QWORD *)(v3 + 16) + 8LL) )
    {
      *a2 = v3;
      *a1 = v27;
    }
    v28 = *a3;
    result = *(_BYTE *)(*(_QWORD *)(*a2 + 16) + 8LL);
    if ( *(_BYTE *)(*(_QWORD *)(*a3 + 16) + 8LL) < result )
    {
      *a3 = *a2;
      *a2 = v28;
      result = *(_BYTE *)(*(_QWORD *)(*a1 + 16) + 8LL);
      if ( *(_BYTE *)(*(_QWORD *)(v28 + 16) + 8LL) < result )
      {
        *a2 = *a1;
        *a1 = v28;
      }
    }
  }
  else
  {
    v7 = (v5 + 1) / 8;
    v8 = 16 * v7;
    v9 = 8 * v7;
    v10 = a1[v7];
    if ( *(_BYTE *)(*(_QWORD *)(v10 + 16) + 8LL) < *(_BYTE *)(*(_QWORD *)(v3 + 16) + 8LL) )
    {
      a1[(unsigned __int64)v9 / 8] = v3;
      *a1 = v10;
    }
    v11 = a1[(unsigned __int64)v9 / 8];
    v12 = a1[(unsigned __int64)v8 / 8];
    if ( *(_BYTE *)(*(_QWORD *)(v12 + 16) + 8LL) < *(_BYTE *)(*(_QWORD *)(v11 + 16) + 8LL) )
    {
      a1[(unsigned __int64)v8 / 8] = v11;
      a1[(unsigned __int64)v9 / 8] = v12;
      if ( *(_BYTE *)(*(_QWORD *)(v12 + 16) + 8LL) < *(_BYTE *)(*(_QWORD *)(*a1 + 16) + 8LL) )
      {
        a1[(unsigned __int64)v9 / 8] = *a1;
        *a1 = v12;
      }
    }
    v13 = *a2;
    v14 = &a2[v9 / 0xFFFFFFFFFFFFFFF8uLL];
    v15 = a2[-v7];
    if ( *(_BYTE *)(*(_QWORD *)(*a2 + 16) + 8LL) < *(_BYTE *)(*(_QWORD *)(v15 + 16) + 8LL) )
    {
      *a2 = v15;
      *v14 = v13;
    }
    v16 = a2[(unsigned __int64)v9 / 8];
    if ( *(_BYTE *)(*(_QWORD *)(v16 + 16) + 8LL) < *(_BYTE *)(*(_QWORD *)(*a2 + 16) + 8LL) )
    {
      a2[(unsigned __int64)v9 / 8] = *a2;
      *a2 = v16;
      if ( *(_BYTE *)(*(_QWORD *)(v16 + 16) + 8LL) < *(_BYTE *)(*(_QWORD *)(*v14 + 16) + 8LL) )
      {
        *a2 = *v14;
        *v14 = v16;
      }
    }
    v17 = &a3[v8 / 0xFFFFFFFFFFFFFFF8uLL];
    v18 = &a3[v9 / 0xFFFFFFFFFFFFFFF8uLL];
    v19 = a3[-2 * v7];
    v20 = a3[-v7];
    if ( *(_BYTE *)(*(_QWORD *)(v20 + 16) + 8LL) < *(_BYTE *)(*(_QWORD *)(v19 + 16) + 8LL) )
    {
      *v18 = v19;
      *v17 = v20;
    }
    v21 = *a3;
    if ( *(_BYTE *)(*(_QWORD *)(*a3 + 16) + 8LL) < *(_BYTE *)(*(_QWORD *)(*v18 + 16) + 8LL) )
    {
      *a3 = *v18;
      *v18 = v21;
      if ( *(_BYTE *)(*(_QWORD *)(v21 + 16) + 8LL) < *(_BYTE *)(*(_QWORD *)(*v17 + 16) + 8LL) )
      {
        *v18 = *v17;
        *v17 = v21;
      }
    }
    v22 = a1[(unsigned __int64)v9 / 8];
    v23 = *a2;
    if ( *(_BYTE *)(*(_QWORD *)(*a2 + 16) + 8LL) < *(_BYTE *)(*(_QWORD *)(v22 + 16) + 8LL) )
    {
      *a2 = v22;
      a1[(unsigned __int64)v9 / 8] = v23;
    }
    v24 = *v18;
    result = *(_BYTE *)(*(_QWORD *)(*a2 + 16) + 8LL);
    if ( *(_BYTE *)(*(_QWORD *)(*v18 + 16) + 8LL) < result )
    {
      *v18 = *a2;
      *a2 = v24;
      v26 = a1[(unsigned __int64)v9 / 8];
      result = *(_BYTE *)(*(_QWORD *)(v26 + 16) + 8LL);
      if ( *(_BYTE *)(*(_QWORD *)(v24 + 16) + 8LL) < result )
      {
        *a2 = v26;
        a1[(unsigned __int64)v9 / 8] = v24;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000fc38  push    rbx
0x18000fc3a  push    rbp
0x18000fc3b  push    rsi
0x18000fc3c  push    rdi
0x18000fc3d  push    r14
0x18000fc3f  mov     r11, [rcx]
0x18000fc42  mov     rax, r8
0x18000fc45  sub     rax, rcx
0x18000fc48  mov     rdi, r8
0x18000fc4b  sar     rax, 3
0x18000fc4f  mov     r9, rdx
0x18000fc52  mov     r10, rcx
0x18000fc55  cmp     rax, 28h ; '('
0x18000fc59  jle     loc_18000FDDF
0x18000fc5f  inc     rax
0x18000fc62  cqo
0x18000fc64  and     edx, 7
0x18000fc67  add     rax, rdx
0x18000fc6a  sar     rax, 3
0x18000fc6e  mov     r14, rax
0x18000fc71  shl     r14, 4
0x18000fc75  lea     r8, ds:0[rax*8]
0x18000fc7d  mov     rax, [r11+10h]
0x18000fc81  mov     rbx, [r8+rcx]
0x18000fc85  mov     cl, [rax+8]
0x18000fc88  mov     rdx, [rbx+10h]
0x18000fc8c  cmp     [rdx+8], cl
0x18000fc8f  jnb     short loc_18000FC98
0x18000fc91  mov     [r8+r10], r11
0x18000fc95  mov     [r10], rbx
0x18000fc98  mov     r11, [r8+r10]
0x18000fc9c  mov     rdx, [r14+r10]
0x18000fca0  mov     rax, [r11+10h]
0x18000fca4  mov     rcx, [rdx+10h]
0x18000fca8  mov     al, [rax+8]
0x18000fcab  cmp     [rcx+8], al
0x18000fcae  jnb     short loc_18000FCD2
0x18000fcb0  mov     [r14+r10], r11
0x18000fcb4  mov     [r8+r10], rdx
0x18000fcb8  mov     r11, [r10]
0x18000fcbb  mov     rcx, [rdx+10h]
0x18000fcbf  mov     rax, [r11+10h]
0x18000fcc3  mov     al, [rax+8]
0x18000fcc6  cmp     [rcx+8], al
0x18000fcc9  jnb     short loc_18000FCD2
0x18000fccb  mov     [r8+r10], r11
0x18000fccf  mov     [r10], rdx
0x18000fcd2  mov     rsi, [r9]
0x18000fcd5  mov     r11, r9
0x18000fcd8  sub     r11, r8
0x18000fcdb  mov     rdx, [rsi+10h]
0x18000fcdf  mov     rbx, [r11]
0x18000fce2  mov     rax, [rbx+10h]
0x18000fce6  mov     cl, [rax+8]
0x18000fce9  cmp     [rdx+8], cl
0x18000fcec  jnb     short loc_18000FCF4
0x18000fcee  mov     [r9], rbx
0x18000fcf1  mov     [r11], rsi
0x18000fcf4  mov     rbx, [r9]
0x18000fcf7  mov     rdx, [r8+r9]
0x18000fcfb  mov     rax, [rbx+10h]
0x18000fcff  mov     rcx, [rdx+10h]
0x18000fd03  mov     al, [rax+8]
0x18000fd06  cmp     [rcx+8], al
0x18000fd09  jnb     short loc_18000FD2B
0x18000fd0b  mov     [r8+r9], rbx
0x18000fd0f  mov     [r9], rdx
0x18000fd12  mov     rbx, [r11]
0x18000fd15  mov     rcx, [rdx+10h]
0x18000fd19  mov     rax, [rbx+10h]
0x18000fd1d  mov     al, [rax+8]
0x18000fd20  cmp     [rcx+8], al
0x18000fd23  jnb     short loc_18000FD2B
0x18000fd25  mov     [r9], rbx
0x18000fd28  mov     [r11], rdx
0x18000fd2b  mov     rbx, rdi
0x18000fd2e  mov     r11, rdi
0x18000fd31  sub     rbx, r14
0x18000fd34  sub     r11, r8
0x18000fd37  mov     rsi, [rbx]
0x18000fd3a  mov     rbp, [r11]
0x18000fd3d  mov     rax, [rsi+10h]
0x18000fd41  mov     rdx, [rbp+10h]
0x18000fd45  mov     cl, [rax+8]
0x18000fd48  cmp     [rdx+8], cl
0x18000fd4b  jnb     short loc_18000FD53
0x18000fd4d  mov     [r11], rsi
0x18000fd50  mov     [rbx], rbp
0x18000fd53  mov     rsi, [r11]
0x18000fd56  mov     rdx, [rdi]
0x18000fd59  mov     rax, [rsi+10h]
0x18000fd5d  mov     rcx, [rdx+10h]
0x18000fd61  mov     al, [rax+8]
0x18000fd64  cmp     [rcx+8], al
0x18000fd67  jnb     short loc_18000FD88
0x18000fd69  mov     [rdi], rsi
0x18000fd6c  mov     [r11], rdx
0x18000fd6f  mov     rdi, [rbx]
0x18000fd72  mov     rcx, [rdx+10h]
0x18000fd76  mov     rax, [rdi+10h]
0x18000fd7a  mov     al, [rax+8]
0x18000fd7d  cmp     [rcx+8], al
0x18000fd80  jnb     short loc_18000FD88
0x18000fd82  mov     [r11], rdi
0x18000fd85  mov     [rbx], rdx
0x18000fd88  mov     rdx, [r8+r10]
0x18000fd8c  mov     rbx, [r9]
0x18000fd8f  mov     rax, [rdx+10h]
0x18000fd93  mov     rcx, [rbx+10h]
0x18000fd97  mov     al, [rax+8]
0x18000fd9a  cmp     [rcx+8], al
0x18000fd9d  jnb     short loc_18000FDA6
0x18000fd9f  mov     [r9], rdx
0x18000fda2  mov     [r8+r10], rbx
0x18000fda6  mov     rbx, [r9]
0x18000fda9  mov     rdx, [r11]
0x18000fdac  mov     rax, [rbx+10h]
0x18000fdb0  mov     rcx, [rdx+10h]
0x18000fdb4  mov     al, [rax+8]
0x18000fdb7  cmp     [rcx+8], al
0x18000fdba  jnb     short loc_18000FE2D
0x18000fdbc  mov     [r11], rbx
0x18000fdbf  mov     [r9], rdx
0x18000fdc2  mov     r11, [r8+r10]
0x18000fdc6  mov     rcx, [rdx+10h]
0x18000fdca  mov     rax, [r11+10h]
0x18000fdce  mov     al, [rax+8]
0x18000fdd1  cmp     [rcx+8], al
0x18000fdd4  jnb     short loc_18000FE2D
0x18000fdd6  mov     [r9], r11
0x18000fdd9  mov     [r8+r10], rdx
0x18000fddd  jmp     short loc_18000FE2D
0x18000fddf  mov     r8, [rdx]
0x18000fde2  mov     rax, [r11+10h]
0x18000fde6  mov     rdx, [r8+10h]
0x18000fdea  mov     cl, [rax+8]
0x18000fded  cmp     [rdx+8], cl
0x18000fdf0  jnb     short loc_18000FDF8
0x18000fdf2  mov     [r9], r11
0x18000fdf5  mov     [r10], r8
0x18000fdf8  mov     r8, [r9]
0x18000fdfb  mov     rdx, [rdi]
0x18000fdfe  mov     rax, [r8+10h]
0x18000fe02  mov     rcx, [rdx+10h]
0x18000fe06  mov     al, [rax+8]
0x18000fe09  cmp     [rcx+8], al
0x18000fe0c  jnb     short loc_18000FE2D
0x18000fe0e  mov     [rdi], r8
0x18000fe11  mov     [r9], rdx
0x18000fe14  mov     r8, [r10]
0x18000fe17  mov     rcx, [rdx+10h]
0x18000fe1b  mov     rax, [r8+10h]
0x18000fe1f  mov     al, [rax+8]
0x18000fe22  cmp     [rcx+8], al
0x18000fe25  jnb     short loc_18000FE2D
0x18000fe27  mov     [r9], r8
0x18000fe2a  mov     [r10], rdx
0x18000fe2d  pop     r14
0x18000fe2f  pop     rdi
0x18000fe30  pop     rsi
0x18000fe31  pop     rbp
0x18000fe32  pop     rbx
0x18000fe33  retn
```
