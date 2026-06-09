# init_main_qtable(fuji_compressed_params *,uchar)

- ea: `0x180014970`
- end: `0x180014a5e`
- name: `?init_main_qtable@@YAXPEAUfuji_compressed_params@@E@Z`
- size: `238`
- prototype: `void __fastcall(struct fuji_compressed_params *, unsigned __int8)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180013a50`
- `0x1800146a0`

## callees

- `0x180014970`
- `0x180014cf0`

## pseudocode

```c
void __fastcall init_main_qtable(struct fuji_compressed_params *a1, unsigned __int8 a2)
{
  int v2; // ebx
  int v4; // esi
  int v5; // r8d
  int v6; // ecx
  int v7; // edx
  int v8; // eax
  int v9; // r8d
  int v10; // eax
  int v11; // edx
  int v12; // [rsp+20h] [rbp-28h] BYREF
  int v13; // [rsp+24h] [rbp-24h]
  int v14; // [rsp+28h] [rbp-20h]
  int v15; // [rsp+2Ch] [rbp-1Ch]
  int v16; // [rsp+30h] [rbp-18h]

  v2 = *((_DWORD *)a1 + 36);
  v4 = a2;
  v12 = v4;
  v5 = v2 + 1;
  v16 = v2;
  v6 = 3 * (a2 + 6);
  v7 = 7 * a2 + 276;
  v13 = v6;
  v15 = v7;
  v8 = v4 + 4 * v4 + 67;
  v14 = v8;
  if ( v6 >= v2 + 1 || v6 < (unsigned int)(v4 + 1) )
  {
    v6 = v4 + 1;
    v13 = v4 + 1;
  }
  if ( v8 < v6 || v8 >= v5 )
  {
    v8 = v6;
    v14 = v6;
  }
  if ( v7 < v8 || v7 >= v5 )
    v15 = v8;
  setup_qlut(*(signed __int8 **)a1, &v12);
  v9 = 0;
  *((_DWORD *)a1 + 6) = v4;
  *((_DWORD *)a1 + 4) = 0;
  v10 = (2 * v4 + v2) / (2 * v4 + 1);
  v11 = 0;
  *((_DWORD *)a1 + 3) = v10 + 1;
  if ( v10 != -1 )
  {
    do
    {
      ++v11;
      v10 >>= 1;
    }
    while ( v10 );
  }
  *((_DWORD *)a1 + 2) = v11;
  *((_DWORD *)a1 + 5) = 9;
  if ( v2 != -1 )
  {
    do
    {
      v2 >>= 1;
      ++v9;
    }
    while ( v2 );
  }
  *((_DWORD *)a1 + 34) = 4 * v9;
}

```

## disassembly

```asm
0x180014970  mov     [rsp+arg_0], rbx
0x180014975  mov     [rsp+arg_8], rsi
0x18001497a  push    rdi
0x18001497b  sub     rsp, 40h
0x18001497f  mov     ebx, [rcx+90h]
0x180014985  mov     rdi, rcx
0x180014988  movzx   esi, dl
0x18001498b  imul    edx, esi, 7
0x18001498e  mov     [rsp+48h+var_28], esi
0x180014992  lea     r8d, [rbx+1]
0x180014996  mov     [rsp+48h+var_18], ebx
0x18001499a  lea     eax, [rsi+6]
0x18001499d  lea     ecx, [rax+rax*2]
0x1800149a0  add     edx, 114h
0x1800149a6  mov     [rsp+48h+var_24], ecx
0x1800149aa  lea     eax, ds:43h[rsi*4]
0x1800149b1  mov     [rsp+48h+var_1C], edx
0x1800149b5  add     eax, esi
0x1800149b7  lea     r9d, [rsi+1]
0x1800149bb  mov     [rsp+48h+var_20], eax
0x1800149bf  cmp     ecx, r8d
0x1800149c2  jge     short loc_1800149C9
0x1800149c4  cmp     ecx, r9d
0x1800149c7  jnb     short loc_1800149D0
0x1800149c9  mov     ecx, r9d
0x1800149cc  mov     [rsp+48h+var_24], ecx
0x1800149d0  cmp     eax, ecx
0x1800149d2  jl      short loc_1800149D9
0x1800149d4  cmp     eax, r8d
0x1800149d7  jl      short loc_1800149DF
0x1800149d9  mov     eax, ecx
0x1800149db  mov     [rsp+48h+var_20], ecx
0x1800149df  cmp     edx, eax
0x1800149e1  jl      short loc_1800149E8
0x1800149e3  cmp     edx, r8d
0x1800149e6  jl      short loc_1800149EC
0x1800149e8  mov     [rsp+48h+var_1C], eax
0x1800149ec  mov     rcx, [rdi]; signed __int8 *
0x1800149ef  lea     rdx, [rsp+48h+var_28]; int *
0x1800149f4  call    ?setup_qlut@@YAXPEACPEAH@Z; setup_qlut(signed char *,int *)
0x1800149f9  xor     r8d, r8d
0x1800149fc  mov     [rdi+18h], esi
0x1800149ff  lea     ecx, [rsi+rsi]
0x180014a02  mov     [rdi+10h], r8d
0x180014a06  lea     eax, [rcx+rbx]
0x180014a09  inc     ecx
0x180014a0b  cdq
0x180014a0c  idiv    ecx
0x180014a0e  mov     edx, r8d
0x180014a11  lea     ecx, [rax+1]
0x180014a14  mov     [rdi+0Ch], ecx
0x180014a17  test    ecx, ecx
0x180014a19  jz      short loc_180014A26
0x180014a1b  nop     dword ptr [rax+rax+00h]
0x180014a20  inc     edx
0x180014a22  sar     eax, 1
0x180014a24  jnz     short loc_180014A20
0x180014a26  lea     eax, [rbx+1]
0x180014a29  mov     [rdi+8], edx
0x180014a2c  mov     dword ptr [rdi+14h], 9
0x180014a33  test    eax, eax
0x180014a35  jz      short loc_180014A3F
0x180014a37  sar     ebx, 1
0x180014a39  lea     r8d, [r8+1]
0x180014a3d  jnz     short loc_180014A37
0x180014a3f  mov     rbx, [rsp+48h+arg_0]
0x180014a44  lea     r8d, ds:0[r8*4]
0x180014a4c  mov     rsi, [rsp+48h+arg_8]
0x180014a51  mov     [rdi+88h], r8d
0x180014a58  add     rsp, 40h
0x180014a5c  pop     rdi
0x180014a5d  retn
```
