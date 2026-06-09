# IoCompletionForOpenChannelSuccess

- ea: `0x140002660`
- end: `0x140002926`
- name: `IoCompletionForOpenChannelSuccess`
- size: `710`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001008`
- `0x1400013e8`
- `0x140002660`
- `0x140007d00`

## import_xrefs

- `ntoskrnl!_ui64tow_s` at `0x1400027dc`
- `ntoskrnl!_ui64tow_s` at `0x1400027dc`

## pseudocode

```c
__int64 __fastcall IoCompletionForOpenChannelSuccess(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rbx
  unsigned int *v6; // rdi
  __int16 v7; // r15
  __int16 v8; // dx
  char v9; // bl
  unsigned __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rax
  __int64 v15; // [rsp+28h] [rbp-D8h]
  char v16; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v17; // [rsp+34h] [rbp-CCh] BYREF
  int v18; // [rsp+38h] [rbp-C8h] BYREF
  int v19; // [rsp+3Ch] [rbp-C4h] BYREF
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v22; // [rsp+70h] [rbp-90h]
  __int64 v23; // [rsp+78h] [rbp-88h]
  __int64 v24; // [rsp+80h] [rbp-80h]
  __int64 v25; // [rsp+88h] [rbp-78h]
  int *v26; // [rsp+90h] [rbp-70h]
  __int64 v27; // [rsp+98h] [rbp-68h]
  wchar_t *v28; // [rsp+A0h] [rbp-60h]
  int v29; // [rsp+A8h] [rbp-58h]
  int v30; // [rsp+ACh] [rbp-54h]
  __int16 *v31; // [rsp+B0h] [rbp-50h]
  __int64 v32; // [rsp+B8h] [rbp-48h]
  char *v33; // [rsp+C0h] [rbp-40h]
  __int64 v34; // [rsp+C8h] [rbp-38h]
  int *v35; // [rsp+D0h] [rbp-30h]
  __int64 v36; // [rsp+D8h] [rbp-28h]
  wchar_t DstBuf[8]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v38; // [rsp+F0h] [rbp-10h]

  v4 = 0;
  v6 = (unsigned int *)(a2 + 48);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      (unsigned int)WPP_f24dc5fc8d98372b7b5478949da3430c_Traceguids,
      3,
      15,
      (__int64)WPP_f24dc5fc8d98372b7b5478949da3430c_Traceguids,
      *v6);
  if ( *(_BYTE *)(a2 + 65) )
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
  if ( (*v6 & 0x80000000) == 0 )
  {
    v4 = *(_QWORD *)(*(_QWORD *)(a2 + 184) + 8LL);
    if ( v4 )
    {
      if ( *(_WORD *)(v4 + 22) == 258
        || *(_WORD *)(v4 + 22) == 259
        || *(_WORD *)(v4 + 22) == 514
        || *(_WORD *)(v4 + 22) == 515
        || *(_WORD *)(v4 + 22) == 528
        || *(_WORD *)(v4 + 22) == 529
        || (unsigned int)*(unsigned __int16 *)(v4 + 22) - 530 <= 1 )
      {
        _InterlockedIncrement((volatile signed __int32 *)(a3 + 2924));
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v15) = *(_DWORD *)(a3 + 2924);
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            (unsigned int)WPP_f24dc5fc8d98372b7b5478949da3430c_Traceguids,
            2,
            16,
            (__int64)WPP_f24dc5fc8d98372b7b5478949da3430c_Traceguids,
            v15);
        }
      }
    }
  }
  if ( a3 )
  {
    v7 = 0;
    if ( *(int *)(a2 + 48) < 0 )
      goto LABEL_25;
    v8 = *(_WORD *)(v4 + 22);
    if ( v8 == 258 || *(_WORD *)(v4 + 22) == 259 || (unsigned int)*(unsigned __int16 *)(v4 + 22) - 530 <= 1 )
      v7 = *(_WORD *)(v4 + 120);
    if ( v8 == 258 || v8 == 530 )
      v9 = 1;
    else
LABEL_25:
      v9 = 0;
    v10 = *(_QWORD *)(a3 + 192);
    *(_OWORD *)DstBuf = 0;
    v38 = 0;
    _ui64tow_s(v10, DstBuf, 0x10u, 10);
    if ( (unsigned int)dword_140015010 > 5
      && (qword_140015020 & 0x400000000000LL) != 0
      && (*(_QWORD *)&qword_140015028 & 0x400000000000LL) == *(_QWORD *)&qword_140015028 )
    {
      v20 = 50333696;
      v22 = &v20;
      v23 = 8;
      v24 = a3 + 1056;
      v18 = *(_DWORD *)(a3 + 200);
      v26 = &v18;
      v13 = -1;
      v25 = 16;
      v27 = 4;
      do
        ++v13;
      while ( DstBuf[v13] );
      v30 = 0;
      v29 = 2 * v13 + 2;
      v28 = DstBuf;
      v31 = &v17;
      v17 = v7;
      v33 = &v16;
      v19 = *(_DWORD *)(a2 + 48);
      v35 = &v19;
      v32 = 2;
      v16 = v9;
      v34 = 1;
      v36 = 4;
      tlgWriteTransfer_EtwWriteTransfer((__int64)DstBuf, (unsigned __int8 *)&byte_140013A0D, v11, v12, 9u, &v21);
    }
  }
  return *v6;
}

```

## disassembly

```asm
0x140002660  mov     [rsp-8+arg_0], rbx
0x140002665  push    rbp
0x140002666  push    rsi
0x140002667  push    rdi
0x140002668  push    r12
0x14000266a  push    r13
0x14000266c  push    r14
0x14000266e  push    r15
0x140002670  lea     rbp, [rsp-10h]
0x140002675  sub     rsp, 110h
0x14000267c  mov     rax, cs:__security_cookie
0x140002683  xor     rax, rsp
0x140002686  mov     [rbp+40h+var_40], rax
0x14000268a  xor     r12d, r12d
0x14000268d  mov     rsi, r8
0x140002690  mov     ebx, r12d
0x140002693  mov     r14, rdx
0x140002696  lea     r15, WPP_RECORDER_INITIALIZED
0x14000269d  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400026a4  lea     rdi, [rdx+30h]
0x1400026a8  lea     rdx, WPP_f24dc5fc8d98372b7b5478949da3430c_Traceguids
0x1400026af  jz      short loc_1400026DD
0x1400026b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400026b8  lea     r9d, [r12+0Fh]
0x1400026bd  mov     eax, [rdi]
0x1400026bf  lea     r8d, [r12+3]
0x1400026c4  mov     dword ptr [rsp+140h+var_118], eax
0x1400026c8  mov     qword ptr [rsp+140h+var_120], rdx
0x1400026cd  mov     rcx, [rcx+40h]
0x1400026d1  call    WPP_RECORDER_SF_d
0x1400026d6  lea     rdx, WPP_f24dc5fc8d98372b7b5478949da3430c_Traceguids
0x1400026dd  cmp     [r14+41h], r12b
0x1400026e1  jz      short loc_1400026EE
0x1400026e3  mov     rax, [r14+0B8h]
0x1400026ea  or      byte ptr [rax+3], 1
0x1400026ee  mov     r13d, 102h
0x1400026f4  cmp     [rdi], r12d
0x1400026f7  jl      short loc_140002771
0x1400026f9  mov     rax, [r14+0B8h]
0x140002700  mov     rbx, [rax+8]
0x140002704  test    rbx, rbx
0x140002707  jz      short loc_140002771
0x140002709  movzx   ecx, word ptr [rbx+16h]
0x14000270d  sub     ecx, r13d
0x140002710  jz      short loc_140002738
0x140002712  sub     ecx, 1
0x140002715  jz      short loc_140002738
0x140002717  sub     ecx, 0FFh
0x14000271d  jz      short loc_140002738
0x14000271f  sub     ecx, 1
0x140002722  jz      short loc_140002738
0x140002724  sub     ecx, 0Dh
0x140002727  jz      short loc_140002738
0x140002729  sub     ecx, 1
0x14000272c  jz      short loc_140002738
0x14000272e  sub     ecx, 1
0x140002731  jz      short loc_140002738
0x140002733  cmp     ecx, 1
0x140002736  jnz     short loc_140002771
0x140002738  lock inc dword ptr [rsi+0B6Ch]
0x14000273f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140002746  jz      short loc_140002771
0x140002748  mov     rcx, cs:WPP_GLOBAL_Control
0x14000274f  mov     r9d, 10h
0x140002755  mov     eax, [rsi+0B6Ch]
0x14000275b  mov     dword ptr [rsp+140h+var_118], eax
0x14000275f  mov     qword ptr [rsp+140h+var_120], rdx
0x140002764  mov     rcx, [rcx+40h]
0x140002768  lea     r8d, [r9-0Eh]
0x14000276c  call    WPP_RECORDER_SF_d
0x140002771  test    rsi, rsi
0x140002774  jz      loc_1400028FC
0x14000277a  mov     r15d, r12d
0x14000277d  cmp     [r14+30h], r12d
0x140002781  jl      short loc_1400027B9
0x140002783  movzx   edx, word ptr [rbx+16h]
0x140002787  mov     ecx, edx
0x140002789  sub     ecx, r13d
0x14000278c  jz      short loc_1400027A0
0x14000278e  sub     ecx, 1
0x140002791  jz      short loc_1400027A0
0x140002793  sub     ecx, 10Fh
0x140002799  jz      short loc_1400027A0
0x14000279b  cmp     ecx, 1
0x14000279e  jnz     short loc_1400027A5
0x1400027a0  movzx   r15d, word ptr [rbx+78h]
0x1400027a5  cmp     dx, r13w
0x1400027a9  jz      short loc_1400027B5
0x1400027ab  mov     eax, 212h
0x1400027b0  cmp     dx, ax
0x1400027b3  jnz     short loc_1400027B9
0x1400027b5  mov     bl, 1
0x1400027b7  jmp     short loc_1400027BC
0x1400027b9  mov     bl, r12b
0x1400027bc  mov     rcx, [rsi+0C0h]; Val
0x1400027c3  lea     rdx, [rbp+40h+DstBuf]; DstBuf
0x1400027c7  xorps   xmm0, xmm0
0x1400027ca  mov     r9d, 0Ah; Radix
0x1400027d0  movups  xmmword ptr [rbp+40h+DstBuf], xmm0
0x1400027d4  movups  [rbp+40h+var_50], xmm0
0x1400027d8  lea     r8d, [r9+6]; SizeInWords
0x1400027dc  call    cs:__imp__ui64tow_s
0x1400027e3  nop     dword ptr [rax+rax+00h]
0x1400027e8  mov     eax, cs:dword_140015010
0x1400027ee  cmp     eax, 5
0x1400027f1  jbe     loc_1400028FC
0x1400027f7  mov     rcx, cs:qword_140015028
0x1400027fe  mov     rdx, 400000000000h
0x140002808  mov     rax, cs:qword_140015020
0x14000280f  test    rdx, rax
0x140002812  jz      loc_1400028FC
0x140002818  mov     rax, rcx
0x14000281b  and     rax, rdx
0x14000281e  cmp     rax, rcx
0x140002821  jnz     loc_1400028FC
0x140002827  lea     rax, [rsp+140h+var_100]
0x14000282c  mov     [rsp+140h+var_100], 3000800h
0x140002835  mov     [rsp+140h+var_D0], rax
0x14000283a  lea     rcx, [rbp+40h+DstBuf]
0x14000283e  lea     rax, [rsi+420h]
0x140002845  mov     [rsp+140h+var_C8], 8
0x14000284e  mov     [rbp+40h+var_C0], rax
0x140002852  mov     eax, [rsi+0C8h]
0x140002858  mov     [rsp+140h+var_108], eax
0x14000285c  lea     rax, [rsp+140h+var_108]
0x140002861  mov     [rbp+40h+var_B0], rax
0x140002865  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002869  mov     [rbp+40h+var_B8], 10h
0x140002871  mov     [rbp+40h+var_A8], 4
0x140002879  inc     rax
0x14000287c  cmp     [rcx+rax*2], r12w
0x140002881  jnz     short loc_140002879
0x140002883  lea     eax, ds:2[rax*2]
0x14000288a  mov     [rbp+40h+var_94], r12d
0x14000288e  mov     [rbp+40h+var_98], eax
0x140002891  lea     rcx, [rbp+40h+DstBuf]; int
0x140002895  lea     rax, [rsp+140h+var_10C]
0x14000289a  mov     [rbp+40h+var_A0], rcx
0x14000289e  mov     [rbp+40h+var_90], rax
0x1400028a2  lea     rdx, byte_140013A0D; int
0x1400028a9  lea     rax, [rsp+140h+var_110]
0x1400028ae  mov     [rsp+140h+var_10C], r15w
0x1400028b4  mov     [rbp+40h+var_80], rax
0x1400028b8  mov     eax, [r14+30h]
0x1400028bc  mov     [rsp+140h+var_104], eax
0x1400028c0  lea     rax, [rsp+140h+var_104]
0x1400028c5  mov     [rbp+40h+var_70], rax
0x1400028c9  lea     rax, [rsp+140h+var_F0]
0x1400028ce  mov     [rsp+140h+var_118], rax; __int64
0x1400028d3  mov     [rsp+140h+var_120], 9; ULONG
0x1400028db  mov     [rbp+40h+var_88], 2
0x1400028e3  mov     [rsp+140h+var_110], bl
0x1400028e7  mov     [rbp+40h+var_78], 1
0x1400028ef  mov     [rbp+40h+var_68], 4
0x1400028f7  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400028fc  mov     eax, [rdi]
0x1400028fe  mov     rcx, [rbp+40h+var_40]
0x140002902  xor     rcx, rsp; StackCookie
0x140002905  call    __security_check_cookie
0x14000290a  mov     rbx, [rsp+140h+arg_0]
0x140002912  add     rsp, 110h
0x140002919  pop     r15
0x14000291b  pop     r14
0x14000291d  pop     r13
0x14000291f  pop     r12
0x140002921  pop     rdi
0x140002922  pop     rsi
0x140002923  pop     rbp
0x140002924  retn
```
