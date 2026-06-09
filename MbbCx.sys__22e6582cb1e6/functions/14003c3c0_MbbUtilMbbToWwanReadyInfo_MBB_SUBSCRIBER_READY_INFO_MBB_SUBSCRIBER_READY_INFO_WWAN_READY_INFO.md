# MbbUtilMbbToWwanReadyInfo<_MBB_SUBSCRIBER_READY_INFO>(_MBB_SUBSCRIBER_READY_INFO *,_WWAN_READY_INFO *)

- ea: `0x14003c3c0`
- end: `0x14003c497`
- name: `??$MbbUtilMbbToWwanReadyInfo@U_MBB_SUBSCRIBER_READY_INFO@@@@YAXPEAU_MBB_SUBSCRIBER_READY_INFO@@PEAU_WWAN_READY_INFO@@@Z`
- size: `215`
- prototype: `__int64 __fastcall(_DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400287b0`

## callees

- `0x14003c3c0`
- `0x140048040`

## pseudocode

```c
__int64 __fastcall MbbUtilMbbToWwanReadyInfo<_MBB_SUBSCRIBER_READY_INFO>(_DWORD *a1, _DWORD *a2)
{
  unsigned int v3; // r15d
  size_t v4; // r8
  unsigned int v6; // eax
  unsigned __int64 v7; // rbx
  unsigned int v8; // ecx
  unsigned __int64 v9; // rbx
  __int64 result; // rax
  __int64 v11; // rbp
  _DWORD *v12; // r14
  unsigned int v13; // ecx
  unsigned __int64 v14; // rbx

  v3 = a1[6];
  v4 = 30;
  *a2 = *a1;
  v6 = a1[2];
  if ( v6 < 0x1E )
    v4 = v6;
  v7 = (unsigned int)v4;
  memmove(a2 + 2, (char *)a1 + (unsigned int)a1[1], v4);
  v8 = 40;
  *((_WORD *)a2 + (v7 >> 1) + 4) = 0;
  if ( a1[4] < 0x28u )
    v8 = a1[4];
  v9 = v8;
  memmove(a2 + 10, (char *)a1 + (unsigned int)a1[3], v8);
  result = 0;
  v11 = 0;
  v12 = a2 + 25;
  *((_WORD *)a2 + (v9 >> 1) + 20) = 0;
  a2[23] = 0;
  for ( a2[24] = v3; (unsigned int)v11 < v3; v12 = (_DWORD *)((char *)v12 + 46) )
  {
    v13 = 44;
    if ( a1[2 * v11 + 8] < 0x2Cu )
      v13 = a1[2 * v11 + 8];
    v14 = v13;
    memmove(v12, (char *)a1 + (unsigned int)a1[2 * v11 + 7], v13);
    result = 0;
    v11 = (unsigned int)(v11 + 1);
    *((_WORD *)v12 + (v14 >> 1)) = 0;
  }
  a2[21] = 8;
  a2[22] = -1;
  return result;
}

```

## disassembly

```asm
0x14003c3c0  push    rbx
0x14003c3c2  push    rbp
0x14003c3c3  push    rsi
0x14003c3c4  push    rdi
0x14003c3c5  push    r14
0x14003c3c7  push    r15
0x14003c3c9  sub     rsp, 28h
0x14003c3cd  mov     eax, [rcx]
0x14003c3cf  mov     rdi, rdx
0x14003c3d2  mov     r15d, [rcx+18h]
0x14003c3d6  mov     r8d, 1Eh
0x14003c3dc  mov     [rdx], eax
0x14003c3de  mov     rsi, rcx
0x14003c3e1  mov     eax, [rcx+8]
0x14003c3e4  cmp     eax, r8d
0x14003c3e7  mov     edx, [rcx+4]
0x14003c3ea  cmovb   r8d, eax; Size
0x14003c3ee  add     rdx, rcx; Src
0x14003c3f1  lea     rcx, [rdi+8]; void *
0x14003c3f5  mov     ebx, r8d
0x14003c3f8  call    memmove
0x14003c3fd  xor     eax, eax
0x14003c3ff  shr     rbx, 1
0x14003c402  mov     ecx, 28h ; '('
0x14003c407  mov     [rdi+rbx*2+8], ax
0x14003c40c  mov     eax, [rsi+10h]
0x14003c40f  cmp     eax, ecx
0x14003c411  mov     edx, [rsi+0Ch]
0x14003c414  cmovb   ecx, eax
0x14003c417  add     rdx, rsi; Src
0x14003c41a  mov     ebx, ecx
0x14003c41c  lea     rcx, [rdi+28h]; void *
0x14003c420  mov     r8d, ebx; Size
0x14003c423  call    memmove
0x14003c428  xor     eax, eax
0x14003c42a  shr     rbx, 1
0x14003c42d  xor     ebp, ebp
0x14003c42f  lea     r14, [rdi+64h]
0x14003c433  mov     [rdi+rbx*2+28h], ax
0x14003c438  mov     [rdi+5Ch], eax
0x14003c43b  mov     [rdi+60h], r15d
0x14003c43f  test    r15d, r15d
0x14003c442  jz      short loc_14003C47B
0x14003c444  mov     eax, [rsi+rbp*8+20h]
0x14003c448  mov     ecx, 2Ch ; ','
0x14003c44d  mov     edx, [rsi+rbp*8+1Ch]
0x14003c451  add     rdx, rsi; Src
0x14003c454  cmp     eax, ecx
0x14003c456  cmovb   ecx, eax
0x14003c459  mov     ebx, ecx
0x14003c45b  mov     r8d, ecx; Size
0x14003c45e  mov     rcx, r14; void *
0x14003c461  call    memmove
0x14003c466  shr     rbx, 1
0x14003c469  xor     eax, eax
0x14003c46b  inc     ebp
0x14003c46d  mov     [r14+rbx*2], ax
0x14003c472  add     r14, 2Eh ; '.'
0x14003c476  cmp     ebp, r15d
0x14003c479  jb      short loc_14003C444
0x14003c47b  mov     dword ptr [rdi+54h], 8
0x14003c482  mov     dword ptr [rdi+58h], 0FFFFFFFFh
0x14003c489  add     rsp, 28h
0x14003c48d  pop     r15
0x14003c48f  pop     r14
0x14003c491  pop     rdi
0x14003c492  pop     rsi
0x14003c493  pop     rbp
0x14003c494  pop     rbx
0x14003c495  retn
```
