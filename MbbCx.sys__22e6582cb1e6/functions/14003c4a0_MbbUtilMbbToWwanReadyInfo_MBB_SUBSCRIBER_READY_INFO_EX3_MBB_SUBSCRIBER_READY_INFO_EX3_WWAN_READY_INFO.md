# MbbUtilMbbToWwanReadyInfo<_MBB_SUBSCRIBER_READY_INFO_EX3>(_MBB_SUBSCRIBER_READY_INFO_EX3 *,_WWAN_READY_INFO *)

- ea: `0x14003c4a0`
- end: `0x14003c582`
- name: `??$MbbUtilMbbToWwanReadyInfo@U_MBB_SUBSCRIBER_READY_INFO_EX3@@@@YAXPEAU_MBB_SUBSCRIBER_READY_INFO_EX3@@PEAU_WWAN_READY_INFO@@@Z`
- size: `226`
- prototype: `__int64 __fastcall(_DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140028cb8`

## callees

- `0x14003c4a0`
- `0x140048040`

## pseudocode

```c
__int64 __fastcall MbbUtilMbbToWwanReadyInfo<_MBB_SUBSCRIBER_READY_INFO_EX3>(_DWORD *a1, _DWORD *a2)
{
  unsigned int v3; // r15d
  size_t v4; // r8
  unsigned int v6; // eax
  unsigned __int64 v7; // rbx
  unsigned int v8; // ecx
  unsigned __int64 v9; // rbx
  __int64 v10; // rbp
  _DWORD *v11; // r14
  unsigned int v12; // ecx
  unsigned __int64 v13; // rbx
  __int64 result; // rax

  v3 = a1[7];
  v4 = 30;
  *a2 = *a1;
  v6 = a1[3];
  if ( v6 < 0x1E )
    v4 = v6;
  v7 = (unsigned int)v4;
  memmove(a2 + 2, (char *)a1 + (unsigned int)a1[2], v4);
  v8 = 40;
  *((_WORD *)a2 + (v7 >> 1) + 4) = 0;
  if ( a1[5] < 0x28u )
    v8 = a1[5];
  v9 = v8;
  memmove(a2 + 10, (char *)a1 + (unsigned int)a1[4], v8);
  v10 = 0;
  v11 = a2 + 25;
  *((_WORD *)a2 + (v9 >> 1) + 20) = 0;
  a2[23] = 0;
  for ( a2[24] = v3; (unsigned int)v10 < v3; v11 = (_DWORD *)((char *)v11 + 46) )
  {
    v12 = 44;
    if ( a1[2 * v10 + 9] < 0x2Cu )
      v12 = a1[2 * v10 + 9];
    v13 = v12;
    memmove(v11, (char *)a1 + (unsigned int)a1[2 * v10 + 8], v12);
    v10 = (unsigned int)(v10 + 1);
    *((_WORD *)v11 + (v13 >> 1)) = 0;
  }
  a2[21] = 0x80000000;
  result = a1[1] | 0x80000008;
  a2[22] = -1;
  a2[21] = result;
  return result;
}

```

## disassembly

```asm
0x14003c4a0  push    rbx
0x14003c4a2  push    rbp
0x14003c4a3  push    rsi
0x14003c4a4  push    rdi
0x14003c4a5  push    r14
0x14003c4a7  push    r15
0x14003c4a9  sub     rsp, 28h
0x14003c4ad  mov     eax, [rcx]
0x14003c4af  mov     rdi, rdx
0x14003c4b2  mov     r15d, [rcx+1Ch]
0x14003c4b6  mov     r8d, 1Eh
0x14003c4bc  mov     [rdx], eax
0x14003c4be  mov     rsi, rcx
0x14003c4c1  mov     eax, [rcx+0Ch]
0x14003c4c4  cmp     eax, r8d
0x14003c4c7  mov     edx, [rcx+8]
0x14003c4ca  cmovb   r8d, eax; Size
0x14003c4ce  add     rdx, rcx; Src
0x14003c4d1  lea     rcx, [rdi+8]; void *
0x14003c4d5  mov     ebx, r8d
0x14003c4d8  call    memmove
0x14003c4dd  xor     eax, eax
0x14003c4df  shr     rbx, 1
0x14003c4e2  mov     ecx, 28h ; '('
0x14003c4e7  mov     [rdi+rbx*2+8], ax
0x14003c4ec  mov     eax, [rsi+14h]
0x14003c4ef  cmp     eax, ecx
0x14003c4f1  mov     edx, [rsi+10h]
0x14003c4f4  cmovb   ecx, eax
0x14003c4f7  add     rdx, rsi; Src
0x14003c4fa  mov     ebx, ecx
0x14003c4fc  lea     rcx, [rdi+28h]; void *
0x14003c500  mov     r8d, ebx; Size
0x14003c503  call    memmove
0x14003c508  xor     eax, eax
0x14003c50a  shr     rbx, 1
0x14003c50d  xor     ebp, ebp
0x14003c50f  lea     r14, [rdi+64h]
0x14003c513  mov     [rdi+rbx*2+28h], ax
0x14003c518  mov     [rdi+5Ch], eax
0x14003c51b  mov     [rdi+60h], r15d
0x14003c51f  test    r15d, r15d
0x14003c522  jz      short loc_14003C55B
0x14003c524  mov     eax, [rsi+rbp*8+24h]
0x14003c528  mov     ecx, 2Ch ; ','
0x14003c52d  mov     edx, [rsi+rbp*8+20h]
0x14003c531  add     rdx, rsi; Src
0x14003c534  cmp     eax, ecx
0x14003c536  cmovb   ecx, eax
0x14003c539  mov     ebx, ecx
0x14003c53b  mov     r8d, ecx; Size
0x14003c53e  mov     rcx, r14; void *
0x14003c541  call    memmove
0x14003c546  shr     rbx, 1
0x14003c549  xor     eax, eax
0x14003c54b  inc     ebp
0x14003c54d  mov     [r14+rbx*2], ax
0x14003c552  add     r14, 2Eh ; '.'
0x14003c556  cmp     ebp, r15d
0x14003c559  jb      short loc_14003C524
0x14003c55b  mov     dword ptr [rdi+54h], 80000000h
0x14003c562  mov     eax, [rsi+4]
0x14003c565  or      eax, 80000008h
0x14003c56a  mov     dword ptr [rdi+58h], 0FFFFFFFFh
0x14003c571  mov     [rdi+54h], eax
0x14003c574  add     rsp, 28h
0x14003c578  pop     r15
0x14003c57a  pop     r14
0x14003c57c  pop     rdi
0x14003c57d  pop     rsi
0x14003c57e  pop     rbp
0x14003c57f  pop     rbx
0x14003c580  retn
```
