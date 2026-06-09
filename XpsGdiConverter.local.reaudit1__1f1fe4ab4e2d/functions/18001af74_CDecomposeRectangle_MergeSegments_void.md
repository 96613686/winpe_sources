# CDecomposeRectangle::MergeSegments(void)

- ea: `0x18001af74`
- end: `0x18001b096`
- name: `?MergeSegments@CDecomposeRectangle@@QEAAXXZ`
- size: `290`
- prototype: `void __fastcall(CDecomposeRectangle *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001425c`

## callees

- `0x180008830`
- `0x180011fb8`
- `0x180015a88`
- `0x180015aac`
- `0x180015b14`
- `0x18001af74`

## pseudocode

```c
void __fastcall CDecomposeRectangle::MergeSegments(CDecomposeRectangle *this)
{
  char *v1; // r15
  __int64 v2; // r8
  float *v3; // rdi
  __int64 v4; // rcx
  float **v5; // rax
  __int64 v6; // r8
  __int64 v7; // r12
  float *v8; // rsi
  __int64 i; // rbx
  unsigned int v10; // r14d
  unsigned int j; // ebp
  float v12; // xmm2_4
  float v13; // xmm3_4
  float v14; // xmm1_4
  _BYTE v15[8]; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v16[8]; // [rsp+28h] [rbp-60h] BYREF
  _BYTE v17[8]; // [rsp+30h] [rbp-58h] BYREF
  _DWORD v18[4]; // [rsp+38h] [rbp-50h] BYREF

  v1 = (char *)this + 72;
  std::vector<D2D_RECT_U>::clear((char *)this + 72);
  v3 = *(float **)std::vector<tagRGBQUAD>::begin(v2 + 24, v16, v2);
  v5 = (float **)std::vector<CCoordinate>::end(v4, v15);
  v7 = v6 + 48;
  v8 = *v5;
  for ( i = *(_QWORD *)std::vector<tagRGBQUAD>::begin(v6 + 48, v15, v6);
        i != *(_QWORD *)std::vector<CCoordinate>::end(v7, v17) && v3 != v8;
        i += 12 )
  {
    v10 = *(_DWORD *)(i + 8);
    for ( j = 0; v3 != v8 && j < v10; ++j )
    {
      v12 = fmaxf(v3[1], 0.0);
      v13 = fmaxf(*(float *)(i + 4), 0.0);
      v14 = fmaxf(*(float *)i, 0.0);
      v18[0] = fmaxf(*v3, 0.0);
      *(float *)&v18[1] = v14;
      *(float *)&v18[2] = v12;
      *(float *)&v18[3] = v13;
      if ( v12 > 0.0 && v13 > 0.0 )
        std::vector<D2D_RECT_F>::push_back(v1, v18);
      v3 += 3;
    }
  }
}

```

## disassembly

```asm
0x18001af74  mov     [rsp+arg_8], rbx
0x18001af79  mov     [rsp+arg_10], rbp
0x18001af7e  push    rsi
0x18001af7f  push    rdi
0x18001af80  push    r12
0x18001af82  push    r14
0x18001af84  push    r15
0x18001af86  sub     rsp, 60h
0x18001af8a  movaps  [rsp+88h+var_38], xmm6
0x18001af8f  mov     rax, cs:__security_cookie
0x18001af96  xor     rax, rsp
0x18001af99  mov     [rsp+88h+var_40], rax
0x18001af9e  lea     r15, [rcx+48h]
0x18001afa2  mov     r8, rcx
0x18001afa5  mov     rcx, r15
0x18001afa8  call    ?clear@?$vector@UD2D_RECT_U@@V?$allocator@UD2D_RECT_U@@@std@@@std@@QEAAXXZ; std::vector<D2D_RECT_U>::clear(void)
0x18001afad  lea     rcx, [r8+18h]
0x18001afb1  lea     rdx, [rsp+88h+var_60]
0x18001afb6  call    ?begin@?$vector@UtagRGBQUAD@@V?$allocator@UtagRGBQUAD@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UtagRGBQUAD@@@std@@@std@@@2@XZ; std::vector<tagRGBQUAD>::begin(void)
0x18001afbb  lea     rdx, [rsp+88h+var_68]
0x18001afc0  mov     rdi, [rax]
0x18001afc3  call    ?end@?$vector@UCCoordinate@@V?$allocator@UCCoordinate@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UCCoordinate@@@std@@@std@@@2@XZ; std::vector<CCoordinate>::end(void)
0x18001afc8  lea     r12, [r8+30h]
0x18001afcc  lea     rdx, [rsp+88h+var_68]
0x18001afd1  mov     rcx, r12
0x18001afd4  mov     rsi, [rax]
0x18001afd7  call    ?begin@?$vector@UtagRGBQUAD@@V?$allocator@UtagRGBQUAD@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UtagRGBQUAD@@@std@@@std@@@2@XZ; std::vector<tagRGBQUAD>::begin(void)
0x18001afdc  xorps   xmm6, xmm6
0x18001afdf  mov     rbx, [rax]
0x18001afe2  lea     rdx, [rsp+88h+var_58]
0x18001afe7  mov     rcx, r12
0x18001afea  call    ?end@?$vector@UCCoordinate@@V?$allocator@UCCoordinate@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UCCoordinate@@@std@@@std@@@2@XZ; std::vector<CCoordinate>::end(void)
0x18001afef  cmp     rbx, [rax]
0x18001aff2  jz      short loc_18001B06B
0x18001aff4  cmp     rdi, rsi
0x18001aff7  jz      short loc_18001B06B
0x18001aff9  mov     r14d, [rbx+8]
0x18001affd  xor     ebp, ebp
0x18001afff  cmp     rdi, rsi
0x18001b002  jz      short loc_18001B062
0x18001b004  cmp     ebp, r14d
0x18001b007  jnb     short loc_18001B062
0x18001b009  movss   xmm2, dword ptr [rdi+4]
0x18001b00e  movss   xmm3, dword ptr [rbx+4]
0x18001b013  maxss   xmm2, xmm6
0x18001b017  movss   xmm0, dword ptr [rdi]
0x18001b01b  maxss   xmm3, xmm6
0x18001b01f  movss   xmm1, dword ptr [rbx]
0x18001b023  maxss   xmm0, xmm6
0x18001b027  maxss   xmm1, xmm6
0x18001b02b  comiss  xmm2, xmm6
0x18001b02e  movss   [rsp+88h+var_50], xmm0
0x18001b034  movss   [rsp+88h+var_4C], xmm1
0x18001b03a  movss   [rsp+88h+var_48], xmm2
0x18001b040  movss   [rsp+88h+var_44], xmm3
0x18001b046  jbe     short loc_18001B05A
0x18001b048  comiss  xmm3, xmm6
0x18001b04b  jbe     short loc_18001B05A
0x18001b04d  lea     rdx, [rsp+88h+var_50]
0x18001b052  mov     rcx, r15
0x18001b055  call    ?push_back@?$vector@UD2D_RECT_F@@V?$allocator@UD2D_RECT_F@@@std@@@std@@QEAAXAEBUD2D_RECT_F@@@Z; std::vector<D2D_RECT_F>::push_back(D2D_RECT_F const &)
0x18001b05a  add     rdi, 0Ch
0x18001b05e  inc     ebp
0x18001b060  jmp     short loc_18001AFFF
0x18001b062  add     rbx, 0Ch
0x18001b066  jmp     loc_18001AFE2
0x18001b06b  mov     rcx, [rsp+88h+var_40]
0x18001b070  xor     rcx, rsp; StackCookie
0x18001b073  call    __security_check_cookie
0x18001b078  lea     r11, [rsp+88h+var_28]
0x18001b07d  mov     rbx, [r11+38h]
0x18001b081  mov     rbp, [r11+40h]
0x18001b085  movaps  xmm6, [rsp+88h+var_38]
0x18001b08a  mov     rsp, r11
0x18001b08d  pop     r15
0x18001b08f  pop     r14
0x18001b091  pop     r12
0x18001b093  pop     rdi
0x18001b094  pop     rsi
0x18001b095  retn
```
