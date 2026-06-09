# MbbUtilMbbToWwanReadyInfo<_MBB_SUBSCRIBER_READY_INFO_EX4>(_MBB_SUBSCRIBER_READY_INFO_EX4 *,_WWAN_READY_INFO *)

- ea: `0x14003c588`
- end: `0x14003c667`
- name: `??$MbbUtilMbbToWwanReadyInfo@U_MBB_SUBSCRIBER_READY_INFO_EX4@@@@YAXPEAU_MBB_SUBSCRIBER_READY_INFO_EX4@@PEAU_WWAN_READY_INFO@@@Z`
- size: `223`
- prototype: `__int64 __fastcall(_DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400291c0`

## callees

- `0x14003c588`
- `0x140048040`

## pseudocode

```c
__int64 __fastcall MbbUtilMbbToWwanReadyInfo<_MBB_SUBSCRIBER_READY_INFO_EX4>(_DWORD *a1, _DWORD *a2)
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
    if ( a1[2 * v10 + 10] < 0x2Cu )
      v12 = a1[2 * v10 + 10];
    v13 = v12;
    memmove(v11, (char *)a1 + (unsigned int)a1[2 * v10 + 9], v12);
    v10 = (unsigned int)(v10 + 1);
    *((_WORD *)v11 + (v13 >> 1)) = 0;
  }
  a2[21] = 0x80000000;
  a2[21] = a1[1] | 0x80000000;
  result = (unsigned int)a1[8];
  a2[22] = result;
  return result;
}

```

## disassembly

```asm
0x14003c588  push    rbx
0x14003c58a  push    rbp
0x14003c58b  push    rsi
0x14003c58c  push    rdi
0x14003c58d  push    r14
0x14003c58f  push    r15
0x14003c591  sub     rsp, 28h
0x14003c595  mov     eax, [rcx]
0x14003c597  mov     rsi, rdx
0x14003c59a  mov     r15d, [rcx+1Ch]
0x14003c59e  mov     r8d, 1Eh
0x14003c5a4  mov     [rdx], eax
0x14003c5a6  mov     rdi, rcx
0x14003c5a9  mov     eax, [rcx+0Ch]
0x14003c5ac  cmp     eax, r8d
0x14003c5af  mov     edx, [rcx+8]
0x14003c5b2  cmovb   r8d, eax; Size
0x14003c5b6  add     rdx, rcx; Src
0x14003c5b9  lea     rcx, [rsi+8]; void *
0x14003c5bd  mov     ebx, r8d
0x14003c5c0  call    memmove
0x14003c5c5  xor     eax, eax
0x14003c5c7  shr     rbx, 1
0x14003c5ca  mov     ecx, 28h ; '('
0x14003c5cf  mov     [rsi+rbx*2+8], ax
0x14003c5d4  mov     eax, [rdi+14h]
0x14003c5d7  cmp     eax, ecx
0x14003c5d9  mov     edx, [rdi+10h]
0x14003c5dc  cmovb   ecx, eax
0x14003c5df  add     rdx, rdi; Src
0x14003c5e2  mov     ebx, ecx
0x14003c5e4  lea     rcx, [rsi+28h]; void *
0x14003c5e8  mov     r8d, ebx; Size
0x14003c5eb  call    memmove
0x14003c5f0  xor     eax, eax
0x14003c5f2  shr     rbx, 1
0x14003c5f5  xor     ebp, ebp
0x14003c5f7  lea     r14, [rsi+64h]
0x14003c5fb  mov     [rsi+rbx*2+28h], ax
0x14003c600  mov     [rsi+5Ch], eax
0x14003c603  mov     [rsi+60h], r15d
0x14003c607  test    r15d, r15d
0x14003c60a  jz      short loc_14003C643
0x14003c60c  mov     eax, [rdi+rbp*8+28h]
0x14003c610  mov     ecx, 2Ch ; ','
0x14003c615  mov     edx, [rdi+rbp*8+24h]
0x14003c619  add     rdx, rdi; Src
0x14003c61c  cmp     eax, ecx
0x14003c61e  cmovb   ecx, eax
0x14003c621  mov     ebx, ecx
0x14003c623  mov     r8d, ecx; Size
0x14003c626  mov     rcx, r14; void *
0x14003c629  call    memmove
0x14003c62e  shr     rbx, 1
0x14003c631  xor     eax, eax
0x14003c633  inc     ebp
0x14003c635  mov     [r14+rbx*2], ax
0x14003c63a  add     r14, 2Eh ; '.'
0x14003c63e  cmp     ebp, r15d
0x14003c641  jb      short loc_14003C60C
0x14003c643  mov     ecx, 80000000h
0x14003c648  mov     [rsi+54h], ecx
0x14003c64b  mov     eax, [rdi+4]
0x14003c64e  or      eax, ecx
0x14003c650  mov     [rsi+54h], eax
0x14003c653  mov     eax, [rdi+20h]
0x14003c656  mov     [rsi+58h], eax
0x14003c659  add     rsp, 28h
0x14003c65d  pop     r15
0x14003c65f  pop     r14
0x14003c661  pop     rdi
0x14003c662  pop     rsi
0x14003c663  pop     rbp
0x14003c664  pop     rbx
0x14003c665  retn
```
