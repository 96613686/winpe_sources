# WindowsMidiServicesInternal::WriteGroupTerminalBlocksToPropertyDataPointer(std::vector<WindowsMidiServicesInternal::GroupTerminalBlockInternal,std::allocator<WindowsMidiServicesInternal::GroupTerminalBlockInternal>> const &,std::vector<std::byte,std::allocator<std::byte>> &)

- ea: `0x1800210e4`
- end: `0x18002131f`
- name: `?WriteGroupTerminalBlocksToPropertyDataPointer@WindowsMidiServicesInternal@@YA_NAEBV?$vector@UGroupTerminalBlockInternal@WindowsMidiServicesInternal@@V?$allocator@UGroupTerminalBlockInternal@WindowsMidiServicesInternal@@@std@@@std@@AEAV?$vector@W4byte@std@@V?$allocator@W4byte@std@@@2@@3@@Z`
- size: `571`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18001d454`

## callees

- `0x18000500c`
- `0x18001bfc8`
- `0x18001c400`
- `0x18001c8d8`
- `0x1800210e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall WindowsMidiServicesInternal::WriteGroupTerminalBlocksToPropertyDataPointer(__int64 *a1, __int64 a2)
{
  __int64 v4; // rbx
  __int64 v5; // r14
  __int64 v7; // r15
  __int64 v8; // rcx
  __int64 v9; // rdx
  unsigned __int64 v10; // rbx
  _QWORD *v11; // rdx
  __int64 v12; // r14
  unsigned __int64 v13; // rcx
  char *v14; // rax
  size_t v15; // rbx
  __int64 v16; // r8
  __int64 v17; // r10
  __int64 j; // r9
  __int64 v19; // rax
  _QWORD *v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  _QWORD *v23; // r11
  __int64 k; // rdx
  _BYTE v25[13]; // [rsp+20h] [rbp-30h] BYREF
  __int128 v26; // [rsp+30h] [rbp-20h] BYREF
  __int64 i; // [rsp+40h] [rbp-10h]
  char v28; // [rsp+80h] [rbp+30h] BYREF
  __int64 v29; // [rsp+90h] [rbp+40h]

  v4 = *a1;
  v5 = a1[1];
  if ( v5 == *a1 )
    return 0;
  v7 = 0;
  v26 = 0;
  v8 = 0;
  for ( i = 0; ; v8 = i )
  {
    *(_WORD *)&v25[11] = 0;
    *(_DWORD *)&v25[2] = *(_DWORD *)v4;
    *(_WORD *)&v25[7] = *(_WORD *)(v4 + 6);
    *(_WORD *)&v25[9] = *(_WORD *)(v4 + 8);
    v25[6] = *(_BYTE *)(v4 + 4);
    *(_WORD *)v25 = 2 * *(_WORD *)(v4 + 32) + 13;
    v7 += *(unsigned __int16 *)v25;
    v9 = *((_QWORD *)&v26 + 1);
    if ( *((_QWORD *)&v26 + 1) == v8 )
    {
      std::vector<WindowsMidiServicesInternal::UMP_GROUP_TERMINAL_BLOCK_DEFINITION>::_Emplace_reallocate<WindowsMidiServicesInternal::UMP_GROUP_TERMINAL_BLOCK_DEFINITION const &>(
        &v26,
        *((_BYTE **)&v26 + 1),
        (__int64)v25);
    }
    else
    {
      **((_QWORD **)&v26 + 1) = *(_QWORD *)v25;
      *(_DWORD *)(v9 + 8) = *(_DWORD *)&v25[8];
      *(_BYTE *)(v9 + 12) = v25[12];
      *((_QWORD *)&v26 + 1) += 13LL;
    }
    v4 += 48;
    if ( v4 == v5 )
      break;
  }
  v10 = v7 + 8;
  HIDWORD(v29) = -1431655765 * ((a1[1] - *a1) >> 4);
  LODWORD(v29) = v7 + 8;
  v28 = 0;
  v11 = *(_QWORD **)a2;
  v12 = *(_QWORD *)(a2 + 8);
  v13 = v12 - *(_QWORD *)a2;
  if ( v7 + 8 < v13 )
  {
    v14 = (char *)v11 + v10;
LABEL_15:
    *(_QWORD *)(a2 + 8) = v14;
    goto LABEL_16;
  }
  if ( v7 + 8 > v13 )
  {
    if ( v10 <= *(_QWORD *)(a2 + 16) - (_QWORD)v11 )
    {
      v15 = v10 - v13;
      memset_0(*(void **)(a2 + 8), 0, v15);
      v14 = (char *)(v15 + v12);
      goto LABEL_15;
    }
    std::vector<enum std::byte>::_Resize_reallocate<enum std::byte>(a2, v7 + 8, &v28);
  }
LABEL_16:
  **(_QWORD **)a2 = v29;
  v16 = 8;
  v17 = 0;
  for ( j = v26; (unsigned int)v17 < (unsigned __int64)(0x4EC4EC4EC4EC4EC5LL * (*((_QWORD *)&v26 + 1) - v26)); j = v26 )
  {
    v19 = 13LL * (unsigned int)v17;
    v20 = *(_QWORD **)a2;
    *(_QWORD *)((char *)v20 + v16) = *(_QWORD *)(v19 + j);
    *(_DWORD *)((char *)v20 + v16 + 7) = *(_DWORD *)(v19 + j + 7);
    v21 = v16 + 11;
    v22 = 48 * v17;
    v23 = (_QWORD *)(48 * v17 + *a1 + 16);
    if ( *(_QWORD *)(48 * v17 + *a1 + 40) > 7u )
      v23 = (_QWORD *)*v23;
    for ( k = 0; (unsigned int)k < (unsigned __int64)(2LL * *(_QWORD *)(v22 + *a1 + 32)); k = (unsigned int)(k + 1) )
    {
      *(_BYTE *)(v21 + *(_QWORD *)a2) = *((_BYTE *)v23 + k);
      ++v21;
    }
    v16 = v21 + 2;
    v17 = (unsigned int)(v17 + 1);
  }
  std::vector<WindowsMidiServicesInternal::UMP_GROUP_TERMINAL_BLOCK_DEFINITION>::~vector<WindowsMidiServicesInternal::UMP_GROUP_TERMINAL_BLOCK_DEFINITION>(&v26);
  return 1;
}

```

## disassembly

```asm
0x1800210e4  mov     [rsp-28h+arg_8], rbx
0x1800210e9  mov     [rsp-28h+arg_18], rsi
0x1800210ee  push    rbp
0x1800210ef  push    rdi
0x1800210f0  push    r12
0x1800210f2  push    r14
0x1800210f4  push    r15
0x1800210f6  mov     rbp, rsp
0x1800210f9  sub     rsp, 50h
0x1800210fd  mov     rdi, rdx
0x180021100  mov     rsi, rcx
0x180021103  mov     rbx, [rcx]
0x180021106  mov     r14, [rcx+8]
0x18002110a  cmp     r14, rbx
0x18002110d  jnz     short loc_180021116
0x18002110f  xor     al, al
0x180021111  jmp     loc_180021306
0x180021116  xor     r15d, r15d
0x180021119  xorps   xmm0, xmm0
0x18002111c  movdqu  [rbp+var_20], xmm0
0x180021121  xor     ecx, ecx
0x180021123  mov     [rbp+var_10], rcx
0x180021127  cmp     rbx, r14
0x18002112a  jz      loc_1800211BF
0x180021130  lea     r12d, [r15+0Dh]
0x180021134  xor     eax, eax
0x180021136  mov     [rbp+var_25], ax
0x18002113a  mov     al, [rbx]
0x18002113c  mov     byte ptr [rbp+var_30+2], al
0x18002113f  mov     al, [rbx+1]
0x180021142  mov     byte ptr [rbp+var_30+3], al
0x180021145  mov     al, [rbx+2]
0x180021148  mov     byte ptr [rbp+var_30+4], al
0x18002114b  mov     al, [rbx+3]
0x18002114e  mov     byte ptr [rbp+var_30+5], al
0x180021151  movzx   eax, word ptr [rbx+6]
0x180021155  mov     word ptr [rbp+var_30+7], ax
0x180021159  movzx   eax, word ptr [rbx+8]
0x18002115d  mov     [rbp+var_27], ax
0x180021161  mov     al, [rbx+4]
0x180021164  mov     byte ptr [rbp+var_30+6], al
0x180021167  movzx   eax, word ptr [rbx+20h]
0x18002116b  add     ax, ax
0x18002116e  add     ax, r12w
0x180021172  movzx   eax, ax
0x180021175  mov     word ptr [rbp+var_30], ax
0x180021179  add     r15, rax
0x18002117c  mov     rdx, qword ptr [rbp+var_20+8]
0x180021180  cmp     rdx, rcx
0x180021183  jz      short loc_1800211A0
0x180021185  movsd   xmm0, [rbp+var_30]
0x18002118a  movsd   qword ptr [rdx], xmm0
0x18002118e  mov     eax, [rbp-28h]
0x180021191  mov     [rdx+8], eax
0x180021194  mov     al, byte ptr [rbp+var_25+1]
0x180021197  mov     [rdx+0Ch], al
0x18002119a  add     qword ptr [rbp+var_20+8], r12
0x18002119e  jmp     short loc_1800211AD
0x1800211a0  lea     r8, [rbp+var_30]
0x1800211a4  lea     rcx, [rbp+var_20]
0x1800211a8  call    ??$_Emplace_reallocate@AEBUUMP_GROUP_TERMINAL_BLOCK_DEFINITION@WindowsMidiServicesInternal@@@?$vector@UUMP_GROUP_TERMINAL_BLOCK_DEFINITION@WindowsMidiServicesInternal@@V?$allocator@UUMP_GROUP_TERMINAL_BLOCK_DEFINITION@WindowsMidiServicesInternal@@@std@@@std@@AEAAPEAUUMP_GROUP_TERMINAL_BLOCK_DEFINITION@WindowsMidiServicesInternal@@QEAU23@AEBU23@@Z; std::vector<WindowsMidiServicesInternal::UMP_GROUP_TERMINAL_BLOCK_DEFINITION>::_Emplace_reallocate<WindowsMidiServicesInternal::UMP_GROUP_TERMINAL_BLOCK_DEFINITION const &>(WindowsMidiServicesInternal::UMP_GROUP_TERMINAL_BLOCK_DEFINITION * const,WindowsMidiServicesInternal::UMP_GROUP_TERMINAL_BLOCK_DEFINITION const &)
0x1800211ad  add     rbx, 30h ; '0'
0x1800211b1  cmp     rbx, r14
0x1800211b4  jz      short loc_1800211BF
0x1800211b6  mov     rcx, [rbp+var_10]
0x1800211ba  jmp     loc_180021134
0x1800211bf  lea     rbx, [r15+8]
0x1800211c3  mov     rax, [rsi+8]
0x1800211c7  sub     rax, [rsi]
0x1800211ca  sar     rax, 4
0x1800211ce  mov     rcx, 0AAAAAAAAAAAAAAABh
0x1800211d8  imul    rax, rcx
0x1800211dc  mov     dword ptr [rbp+arg_10+4], eax
0x1800211df  mov     dword ptr [rbp+arg_10], ebx
0x1800211e2  mov     [rbp+arg_0], 0
0x1800211e6  mov     rdx, [rdi]
0x1800211e9  mov     r14, [rdi+8]
0x1800211ed  mov     rcx, r14
0x1800211f0  sub     rcx, rdx
0x1800211f3  cmp     rbx, rcx
0x1800211f6  jnb     short loc_1800211FE
0x1800211f8  lea     rax, [rdx+rbx]
0x1800211fc  jmp     short loc_180021231
0x1800211fe  jbe     short loc_180021235
0x180021200  mov     rax, [rdi+10h]
0x180021204  sub     rax, rdx
0x180021207  cmp     rbx, rax
0x18002120a  jbe     short loc_18002121D
0x18002120c  lea     r8, [rbp+arg_0]
0x180021210  mov     rdx, rbx
0x180021213  mov     rcx, rdi
0x180021216  call    ??$_Resize_reallocate@W4byte@std@@@?$vector@W4byte@std@@V?$allocator@W4byte@std@@@2@@std@@AEAAX_KAEBW4byte@1@@Z; std::vector<std::byte>::_Resize_reallocate<std::byte>(unsigned __int64,std::byte const &)
0x18002121b  jmp     short loc_180021235
0x18002121d  sub     rbx, rcx
0x180021220  mov     r8, rbx; Size
0x180021223  xor     edx, edx; Val
0x180021225  mov     rcx, r14; void *
0x180021228  call    memset_0
0x18002122d  lea     rax, [rbx+r14]
0x180021231  mov     [rdi+8], rax
0x180021235  mov     rcx, [rdi]
0x180021238  mov     rax, [rbp+arg_10]
0x18002123c  mov     [rcx], rax
0x18002123f  mov     r8d, 8
0x180021245  xor     r10d, r10d
0x180021248  mov     rax, qword ptr [rbp+var_20+8]
0x18002124c  mov     r9, qword ptr [rbp+var_20]
0x180021250  sub     rax, r9
0x180021253  mov     rbx, 4EC4EC4EC4EC4EC5h
0x18002125d  imul    rax, rbx
0x180021261  test    rax, rax
0x180021264  jz      loc_1800212FB
0x18002126a  mov     edx, r10d
0x18002126d  imul    rax, rdx, 0Dh
0x180021271  mov     rcx, [rdi]
0x180021274  movsd   xmm0, qword ptr [rax+r9]
0x18002127a  movsd   qword ptr [rcx+r8], xmm0
0x180021280  mov     eax, [rax+r9+7]
0x180021285  mov     [rcx+r8+7], eax
0x18002128a  add     r8, 0Bh
0x18002128e  lea     r9, [r10+r10*2]
0x180021292  shl     r9, 4
0x180021296  mov     rax, [rsi]
0x180021299  lea     r11, [rax+10h]
0x18002129d  add     r11, r9
0x1800212a0  cmp     qword ptr [r9+rax+28h], 7
0x1800212a6  jbe     short loc_1800212AB
0x1800212a8  mov     r11, [r11]
0x1800212ab  xor     edx, edx
0x1800212ad  mov     rax, [r9+rax+20h]
0x1800212b2  add     rax, rax
0x1800212b5  jz      short loc_1800212D9
0x1800212b7  mov     rcx, [rdi]
0x1800212ba  mov     al, [rdx+r11]
0x1800212be  mov     [r8+rcx], al
0x1800212c2  inc     r8
0x1800212c5  inc     edx
0x1800212c7  mov     rax, [rsi]
0x1800212ca  mov     rcx, [r9+rax+20h]
0x1800212cf  add     rcx, rcx
0x1800212d2  mov     eax, edx
0x1800212d4  cmp     rax, rcx
0x1800212d7  jb      short loc_1800212B7
0x1800212d9  add     r8, 2
0x1800212dd  inc     r10d
0x1800212e0  mov     rdx, qword ptr [rbp+var_20+8]
0x1800212e4  mov     r9, qword ptr [rbp+var_20]
0x1800212e8  sub     rdx, r9
0x1800212eb  imul    rdx, rbx
0x1800212ef  mov     ecx, r10d
0x1800212f2  cmp     rcx, rdx
0x1800212f5  jb      loc_18002126A
0x1800212fb  lea     rcx, [rbp+var_20]
0x1800212ff  call    ??1?$vector@UUMP_GROUP_TERMINAL_BLOCK_DEFINITION@WindowsMidiServicesInternal@@V?$allocator@UUMP_GROUP_TERMINAL_BLOCK_DEFINITION@WindowsMidiServicesInternal@@@std@@@std@@QEAA@XZ; std::vector<WindowsMidiServicesInternal::UMP_GROUP_TERMINAL_BLOCK_DEFINITION>::~vector<WindowsMidiServicesInternal::UMP_GROUP_TERMINAL_BLOCK_DEFINITION>(void)
0x180021304  mov     al, 1
0x180021306  lea     r11, [rsp+50h+var_s0]
0x18002130b  mov     rbx, [r11+38h]
0x18002130f  mov     rsi, [r11+48h]
0x180021313  mov     rsp, r11
0x180021316  pop     r15
0x180021318  pop     r14
0x18002131a  pop     r12
0x18002131c  pop     rdi
0x18002131d  pop     rbp
0x18002131e  retn
```
