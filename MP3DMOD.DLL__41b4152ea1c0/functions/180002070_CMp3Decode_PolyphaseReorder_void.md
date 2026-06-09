# CMp3Decode::PolyphaseReorder(void)

- ea: `0x180002070`
- end: `0x1800022e0`
- name: `?PolyphaseReorder@CMp3Decode@@IEAAXXZ`
- size: `624`
- prototype: `void __fastcall(CMp3Decode *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003b80`
- `0x18000d780`

## callees

- `0x180002070`

## pseudocode

```c
void __fastcall CMp3Decode::PolyphaseReorder(CMp3Decode *this)
{
  int v1; // edi
  int i; // ebx
  __int64 v3; // r9
  __int64 j; // r8
  _DWORD *v5; // rdx
  __int64 v6; // rax

  if ( *((_DWORD *)this + 3966) )
  {
    v1 = 1;
  }
  else
  {
    v1 = *(_DWORD *)(*((_QWORD *)this + 627) + 136LL);
    if ( v1 <= 0 )
      return;
  }
  for ( i = 0; i < v1; ++i )
  {
    v3 = 576LL * i;
    for ( j = 0; j != 18; ++j )
    {
      v5 = (_DWORD *)*((_QWORD *)this + 18 * i + j + 1945);
      *v5 = *((_DWORD *)this + v3 + j + 2738);
      v5[1] = *((_DWORD *)this + v3 + j + 2756);
      v5[2] = *((_DWORD *)this + v3 + j + 2774);
      v5[3] = *((_DWORD *)this + v3 + j + 2792);
      v5[4] = *((_DWORD *)this + v3 + j + 2810);
      v5[5] = *((_DWORD *)this + v3 + j + 2828);
      v5[6] = *((_DWORD *)this + v3 + j + 2846);
      v5[7] = *((_DWORD *)this + v3 + j + 2864);
      v5[8] = *((_DWORD *)this + v3 + j + 2882);
      v5[9] = *((_DWORD *)this + v3 + j + 2900);
      v5[10] = *((_DWORD *)this + j + v3 + 2918);
      v5[11] = *((_DWORD *)this + j + v3 + 2936);
      v5[12] = *((_DWORD *)this + v3 + j + 2954);
      v5[13] = *((_DWORD *)this + v3 + j + 2972);
      v5[14] = *((_DWORD *)this + v3 + j + 2990);
      v5[15] = *((_DWORD *)this + v3 + j + 3008);
      v5[16] = *((_DWORD *)this + v3 + j + 3026);
      v5[17] = *((_DWORD *)this + v3 + j + 3044);
      v5[18] = *((_DWORD *)this + v3 + j + 3062);
      v5[19] = *((_DWORD *)this + v3 + j + 3080);
      v5[20] = *((_DWORD *)this + v3 + j + 3098);
      v5[21] = *((_DWORD *)this + v3 + j + 3116);
      v5[22] = *((_DWORD *)this + v3 + j + 3134);
      v5[23] = *((_DWORD *)this + v3 + j + 3152);
      v5[24] = *((_DWORD *)this + v3 + j + 3170);
      v5[25] = *((_DWORD *)this + v3 + j + 3188);
      v5[26] = *((_DWORD *)this + v3 + j + 3206);
      v5[27] = *((_DWORD *)this + v3 + j + 3224);
      v5[28] = *((_DWORD *)this + v3 + j + 3242);
      v5[29] = *((_DWORD *)this + v3 + j + 3260);
      v6 = v3 + j;
      v5[30] = *((_DWORD *)this + v3 + j + 3278);
      v5[31] = *((_DWORD *)this + v6 + 3296);
    }
  }
}

```

## disassembly

```asm
0x180002070  mov     [rsp+arg_8], rbx
0x180002075  push    rdi
0x180002076  cmp     dword ptr [rcx+3DF8h], 0
0x18000207d  mov     r10, rcx
0x180002080  jnz     loc_1800022D6
0x180002086  mov     rax, [rcx+1398h]
0x18000208d  mov     edi, [rax+88h]
0x180002093  test    edi, edi
0x180002095  jle     loc_1800022CF
0x18000209b  mov     [rsp+8+arg_0], rsi
0x1800020a0  xor     ebx, ebx
0x1800020a2  lea     rsi, [rcx+3CC8h]
0x1800020a9  movsxd  rax, ebx
0x1800020ac  lea     r11, [rax+rax*8]
0x1800020b0  shl     r11, 4
0x1800020b4  lea     r9, [rax+rax*8]
0x1800020b8  add     r11, rsi
0x1800020bb  shl     r9, 6
0x1800020bf  xor     r8d, r8d
0x1800020c2  nop     dword ptr [rax+00h]
0x1800020c6  nop     word ptr [rax+rax+00000000h]
0x1800020d0  mov     rdx, [r11+r8*8]
0x1800020d4  lea     rax, [r9+r8]
0x1800020d8  mov     ecx, [r10+rax*4+2AC8h]
0x1800020e0  lea     rax, [r9+r8]
0x1800020e4  mov     [rdx], ecx
0x1800020e6  mov     ecx, [r10+rax*4+2B10h]
0x1800020ee  lea     rax, [r9+r8]
0x1800020f2  mov     [rdx+4], ecx
0x1800020f5  mov     ecx, [r10+rax*4+2B58h]
0x1800020fd  lea     rax, [r9+r8]
0x180002101  mov     [rdx+8], ecx
0x180002104  mov     ecx, [r10+rax*4+2BA0h]
0x18000210c  lea     rax, [r9+r8]
0x180002110  mov     [rdx+0Ch], ecx
0x180002113  mov     ecx, [r10+rax*4+2BE8h]
0x18000211b  lea     rax, [r9+r8]
0x18000211f  mov     [rdx+10h], ecx
0x180002122  mov     ecx, [r10+rax*4+2C30h]
0x18000212a  lea     rax, [r9+r8]
0x18000212e  mov     [rdx+14h], ecx
0x180002131  mov     ecx, [r10+rax*4+2C78h]
0x180002139  lea     rax, [r9+r8]
0x18000213d  mov     [rdx+18h], ecx
0x180002140  mov     ecx, [r10+rax*4+2CC0h]
0x180002148  lea     rax, [r9+r8]
0x18000214c  mov     [rdx+1Ch], ecx
0x18000214f  mov     ecx, [r10+rax*4+2D08h]
0x180002157  lea     rax, [r9+r8]
0x18000215b  mov     [rdx+20h], ecx
0x18000215e  mov     ecx, [r10+rax*4+2D50h]
0x180002166  lea     rax, [r8+r9]
0x18000216a  mov     [rdx+24h], ecx
0x18000216d  mov     ecx, [r10+rax*4+2D98h]
0x180002175  lea     rax, [r8+r9]
0x180002179  mov     [rdx+28h], ecx
0x18000217c  mov     ecx, [r10+rax*4+2DE0h]
0x180002184  lea     rax, [r9+r8]
0x180002188  mov     [rdx+2Ch], ecx
0x18000218b  mov     ecx, [r10+rax*4+2E28h]
0x180002193  lea     rax, [r9+r8]
0x180002197  mov     [rdx+30h], ecx
0x18000219a  mov     ecx, [r10+rax*4+2E70h]
0x1800021a2  lea     rax, [r9+r8]
0x1800021a6  mov     [rdx+34h], ecx
0x1800021a9  mov     ecx, [r10+rax*4+2EB8h]
0x1800021b1  lea     rax, [r9+r8]
0x1800021b5  mov     [rdx+38h], ecx
0x1800021b8  mov     ecx, [r10+rax*4+2F00h]
0x1800021c0  lea     rax, [r9+r8]
0x1800021c4  mov     [rdx+3Ch], ecx
0x1800021c7  mov     ecx, [r10+rax*4+2F48h]
0x1800021cf  lea     rax, [r9+r8]
0x1800021d3  mov     [rdx+40h], ecx
0x1800021d6  mov     ecx, [r10+rax*4+2F90h]
0x1800021de  lea     rax, [r9+r8]
0x1800021e2  mov     [rdx+44h], ecx
0x1800021e5  mov     ecx, [r10+rax*4+2FD8h]
0x1800021ed  lea     rax, [r9+r8]
0x1800021f1  mov     [rdx+48h], ecx
0x1800021f4  mov     ecx, [r10+rax*4+3020h]
0x1800021fc  lea     rax, [r9+r8]
0x180002200  mov     [rdx+4Ch], ecx
0x180002203  mov     ecx, [r10+rax*4+3068h]
0x18000220b  lea     rax, [r9+r8]
0x18000220f  mov     [rdx+50h], ecx
0x180002212  mov     ecx, [r10+rax*4+30B0h]
0x18000221a  lea     rax, [r9+r8]
0x18000221e  mov     [rdx+54h], ecx
0x180002221  mov     ecx, [r10+rax*4+30F8h]
0x180002229  lea     rax, [r9+r8]
0x18000222d  mov     [rdx+58h], ecx
0x180002230  mov     ecx, [r10+rax*4+3140h]
0x180002238  lea     rax, [r9+r8]
0x18000223c  mov     [rdx+5Ch], ecx
0x18000223f  mov     ecx, [r10+rax*4+3188h]
0x180002247  lea     rax, [r9+r8]
0x18000224b  mov     [rdx+60h], ecx
0x18000224e  mov     ecx, [r10+rax*4+31D0h]
0x180002256  lea     rax, [r9+r8]
0x18000225a  mov     [rdx+64h], ecx
0x18000225d  mov     ecx, [r10+rax*4+3218h]
0x180002265  mov     [rdx+68h], ecx
0x180002268  lea     rax, [r9+r8]
0x18000226c  mov     ecx, [r10+rax*4+3260h]
0x180002274  lea     rax, [r9+r8]
0x180002278  mov     [rdx+6Ch], ecx
0x18000227b  mov     ecx, [r10+rax*4+32A8h]
0x180002283  lea     rax, [r9+r8]
0x180002287  mov     [rdx+70h], ecx
0x18000228a  mov     ecx, [r10+rax*4+32F0h]
0x180002292  lea     rax, [r9+r8]
0x180002296  mov     [rdx+74h], ecx
0x180002299  mov     ecx, [r10+rax*4+3338h]
0x1800022a1  lea     rax, [r9+r8]
0x1800022a5  mov     [rdx+78h], ecx
0x1800022a8  inc     r8
0x1800022ab  mov     ecx, [r10+rax*4+3380h]
0x1800022b3  mov     [rdx+7Ch], ecx
0x1800022b6  cmp     r8, 12h
0x1800022ba  jnz     loc_1800020D0
0x1800022c0  inc     ebx
0x1800022c2  cmp     ebx, edi
0x1800022c4  jl      loc_1800020A9
0x1800022ca  mov     rsi, [rsp+8+arg_0]
0x1800022cf  mov     rbx, [rsp+8+arg_8]
0x1800022d4  pop     rdi
0x1800022d5  retn
0x1800022d6  mov     edi, 1
0x1800022db  jmp     loc_18000209B
```
