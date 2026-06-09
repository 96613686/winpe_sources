# FH4::DecompFuncInfo(uchar *,FH4::FuncInfo4 &,unsigned __int64,int,bool)

- ea: `0x180036328`
- end: `0x180036454`
- name: `?DecompFuncInfo@FH4@@YA_JPEAEAEAUFuncInfo4@1@_KH_N@Z`
- size: `300`
- prototype: `__int64 __fastcall(FH4 *this, unsigned __int8 *, struct FH4::FuncInfo4 *, int, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180036a28`

## callees

- `0x180036328`

## pseudocode

```c
__int64 __fastcall FH4::DecompFuncInfo(FH4 *this, unsigned __int8 *a2, struct FH4::FuncInfo4 *a3, int a4, char a5)
{
  unsigned __int8 v5; // bl
  _BYTE *v6; // r10
  __int64 v11; // rcx
  int v12; // eax
  int v13; // eax
  int v14; // edx
  _BYTE *v15; // r8
  _BYTE *v16; // r9
  __int64 v17; // rcx
  int *v18; // r9
  unsigned int v19; // r10d
  int v20; // eax
  int v21; // ecx
  __int64 v22; // rcx

  v5 = *(_BYTE *)this;
  v6 = (char *)this + 1;
  *a2 = *(_BYTE *)this;
  if ( (v5 & 4) != 0 )
  {
    v11 = *v6 & 0xF;
    v6 -= *((char *)&FH4::s_negLengthTab + v11);
    *((_DWORD *)a2 + 1) = *((_DWORD *)v6 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v11);
  }
  if ( (v5 & 8) != 0 )
  {
    v12 = *(_DWORD *)v6;
    v6 += 4;
    *((_DWORD *)a2 + 2) = v12;
  }
  if ( (v5 & 0x10) != 0 )
  {
    v13 = *(_DWORD *)v6;
    v6 += 4;
    *((_DWORD *)a2 + 3) = v13;
  }
  v14 = 0;
  v15 = v6 + 4;
  if ( a5 || (v5 & 2) == 0 )
  {
    *((_DWORD *)a2 + 4) = *(_DWORD *)v6;
  }
  else
  {
    *((_DWORD *)a2 + 4) = 0;
    if ( !*(_DWORD *)v6 )
      __fastfail(7u);
    v16 = (char *)a3 + *(int *)v6;
    v17 = *v16 & 0xF;
    v18 = (int *)&v16[-*((char *)&FH4::s_negLengthTab + v17)];
    v19 = (unsigned int)*(v18 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v17);
    if ( v19 )
    {
      while ( 1 )
      {
        v20 = *v18;
        v21 = v18[1];
        v18 += 2;
        if ( v20 == a4 )
          break;
        if ( ++v14 >= v19 )
          goto LABEL_17;
      }
      *((_DWORD *)a2 + 4) = v21;
    }
  }
LABEL_17:
  if ( (v5 & 1) != 0 )
  {
    v22 = *v15 & 0xF;
    v15 -= *((char *)&FH4::s_negLengthTab + v22);
    *((_DWORD *)a2 + 5) = *((_DWORD *)v15 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v22);
  }
  return v15 - (_BYTE *)this;
}

```

## disassembly

```asm
0x180036328  mov     rax, rsp
0x18003632b  mov     [rax+8], rbx
0x18003632f  mov     [rax+10h], rbp
0x180036333  mov     [rax+18h], rsi
0x180036337  mov     [rax+20h], rdi
0x18003633b  mov     bl, [rcx]
0x18003633d  lea     r10, [rcx+1]
0x180036341  mov     [rdx], bl
0x180036343  mov     esi, r9d
0x180036346  lea     rbp, cs:180000000h
0x18003634d  mov     r9, r8
0x180036350  mov     r11, rdx
0x180036353  mov     rdi, rcx
0x180036356  test    bl, 4
0x180036359  jz      short loc_18003637E
0x18003635b  movzx   ecx, byte ptr [r10]
0x18003635f  and     ecx, 0Fh
0x180036362  movsx   rax, byte ptr [rcx+rbp+46AA0h]
0x18003636b  mov     cl, [rcx+rbp+46AB0h]
0x180036372  sub     r10, rax
0x180036375  mov     eax, [r10-4]
0x180036379  shr     eax, cl
0x18003637b  mov     [rdx+4], eax
0x18003637e  test    bl, 8
0x180036381  jz      short loc_18003638D
0x180036383  mov     eax, [r10]
0x180036386  add     r10, 4
0x18003638a  mov     [rdx+8], eax
0x18003638d  test    bl, 10h
0x180036390  jz      short loc_18003639C
0x180036392  mov     eax, [r10]
0x180036395  add     r10, 4
0x180036399  mov     [rdx+0Ch], eax
0x18003639c  xor     edx, edx
0x18003639e  lea     r8, [r10+4]
0x1800363a2  cmp     [rsp+arg_20], dl
0x1800363a6  jnz     short loc_180036409
0x1800363a8  test    bl, 2
0x1800363ab  jz      short loc_180036409
0x1800363ad  mov     [r11+10h], edx
0x1800363b1  cmp     [r10], edx
0x1800363b4  jz      short loc_180036400
0x1800363b6  movsxd  rax, dword ptr [r10]
0x1800363b9  add     r9, rax
0x1800363bc  movzx   ecx, byte ptr [r9]
0x1800363c0  and     ecx, 0Fh
0x1800363c3  movsx   rax, byte ptr [rcx+rbp+46AA0h]
0x1800363cc  mov     cl, [rcx+rbp+46AB0h]
0x1800363d3  sub     r9, rax
0x1800363d6  mov     r10d, [r9-4]
0x1800363da  shr     r10d, cl
0x1800363dd  test    r10d, r10d
0x1800363e0  jz      short loc_180036410
0x1800363e2  mov     eax, [r9]
0x1800363e5  mov     ecx, [r9+4]
0x1800363e9  lea     r9, [r9+8]
0x1800363ed  cmp     eax, esi
0x1800363ef  jz      short loc_1800363FA
0x1800363f1  inc     edx
0x1800363f3  cmp     edx, r10d
0x1800363f6  jb      short loc_1800363E2
0x1800363f8  jmp     short loc_180036410
0x1800363fa  mov     [r11+10h], ecx
0x1800363fe  jmp     short loc_180036410
0x180036400  mov     ecx, 7
0x180036405  int     29h; Win8: RtlFailFast(ecx)
0x180036407  jmp     short loc_180036410
0x180036409  mov     eax, [r10]
0x18003640c  mov     [r11+10h], eax
0x180036410  test    bl, 1
0x180036413  jz      short loc_180036439
0x180036415  movzx   ecx, byte ptr [r8]
0x180036419  and     ecx, 0Fh
0x18003641c  movsx   rdx, byte ptr [rcx+rbp+46AA0h]
0x180036425  mov     cl, [rcx+rbp+46AB0h]
0x18003642c  sub     r8, rdx
0x18003642f  mov     edx, [r8-4]
0x180036433  shr     edx, cl
0x180036435  mov     [r11+14h], edx
0x180036439  mov     rbx, [rsp+arg_0]
0x18003643e  sub     r8, rdi
0x180036441  mov     rbp, [rsp+arg_8]
0x180036446  mov     rax, r8
0x180036449  mov     rsi, [rsp+arg_10]
0x18003644e  mov     rdi, [rsp+arg_18]
0x180036453  retn
```
