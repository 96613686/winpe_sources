# FH4::DecompFuncInfo(uchar *,FH4::FuncInfo4 &,unsigned __int64,int,bool)

- ea: `0x180008554`
- end: `0x18000868b`
- name: `?DecompFuncInfo@FH4@@YA_JPEAEAEAUFuncInfo4@1@_KH_N@Z`
- size: `311`
- prototype: `__int64 __fastcall(FH4 *this, unsigned __int8 *, struct FH4::FuncInfo4 *, int, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008c24`

## callees

- `0x180008554`

## pseudocode

```c
__int64 __fastcall FH4::DecompFuncInfo(FH4 *this, unsigned __int8 *a2, struct FH4::FuncInfo4 *a3, int a4, char a5)
{
  unsigned __int8 v5; // r11
  _BYTE *v6; // r10
  __int64 v11; // rcx
  int v12; // eax
  int v13; // eax
  int v14; // r9d
  _BYTE *v15; // r8
  _BYTE *v16; // rdx
  __int64 v17; // rcx
  int *v18; // rdx
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
0x180008554  mov     rax, rsp
0x180008557  mov     [rax+8], rbx
0x18000855b  mov     [rax+10h], rbp
0x18000855f  mov     [rax+18h], rsi
0x180008563  mov     [rax+20h], rdi
0x180008567  push    r14
0x180008569  mov     r11b, [rcx]
0x18000856c  lea     r10, [rcx+1]
0x180008570  mov     [rdx], r11b
0x180008573  mov     edi, r9d
0x180008576  lea     r14, cs:180000000h
0x18000857d  mov     rbp, r8
0x180008580  mov     rbx, rdx
0x180008583  mov     rsi, rcx
0x180008586  test    r11b, 4
0x18000858a  jz      short loc_1800085B0
0x18000858c  movzx   ecx, byte ptr [r10]
0x180008590  and     ecx, 0Fh
0x180008593  movsx   rax, byte ptr [rcx+r14+267F0h]
0x18000859c  mov     cl, [rcx+r14+26800h]
0x1800085a4  sub     r10, rax
0x1800085a7  mov     eax, [r10-4]
0x1800085ab  shr     eax, cl
0x1800085ad  mov     [rdx+4], eax
0x1800085b0  test    r11b, 8
0x1800085b4  jz      short loc_1800085C0
0x1800085b6  mov     eax, [r10]
0x1800085b9  add     r10, 4
0x1800085bd  mov     [rdx+8], eax
0x1800085c0  test    r11b, 10h
0x1800085c4  jz      short loc_1800085D0
0x1800085c6  mov     eax, [r10]
0x1800085c9  add     r10, 4
0x1800085cd  mov     [rdx+0Ch], eax
0x1800085d0  xor     r9d, r9d
0x1800085d3  lea     r8, [r10+4]
0x1800085d7  cmp     [rsp+8+arg_20], r9b
0x1800085dc  jnz     short loc_18000863E
0x1800085de  test    r11b, 2
0x1800085e2  jz      short loc_18000863E
0x1800085e4  mov     [rdx+10h], r9d
0x1800085e8  cmp     [r10], r9d
0x1800085eb  jz      short loc_180008635
0x1800085ed  movsxd  rdx, dword ptr [r10]
0x1800085f0  add     rdx, rbp
0x1800085f3  movzx   ecx, byte ptr [rdx]
0x1800085f6  and     ecx, 0Fh
0x1800085f9  movsx   rax, byte ptr [rcx+r14+267F0h]
0x180008602  mov     cl, [rcx+r14+26800h]
0x18000860a  sub     rdx, rax
0x18000860d  mov     r10d, [rdx-4]
0x180008611  shr     r10d, cl
0x180008614  test    r10d, r10d
0x180008617  jz      short loc_180008644
0x180008619  mov     eax, [rdx]
0x18000861b  mov     ecx, [rdx+4]
0x18000861e  lea     rdx, [rdx+8]
0x180008622  cmp     eax, edi
0x180008624  jz      short loc_180008630
0x180008626  inc     r9d
0x180008629  cmp     r9d, r10d
0x18000862c  jb      short loc_180008619
0x18000862e  jmp     short loc_180008644
0x180008630  mov     [rbx+10h], ecx
0x180008633  jmp     short loc_180008644
0x180008635  mov     ecx, 7
0x18000863a  int     29h; Win8: RtlFailFast(ecx)
0x18000863c  jmp     short loc_180008644
0x18000863e  mov     eax, [r10]
0x180008641  mov     [rdx+10h], eax
0x180008644  test    r11b, 1
0x180008648  jz      short loc_18000866E
0x18000864a  movzx   ecx, byte ptr [r8]
0x18000864e  and     ecx, 0Fh
0x180008651  movsx   rdx, byte ptr [rcx+r14+267F0h]
0x18000865a  mov     cl, [rcx+r14+26800h]
0x180008662  sub     r8, rdx
0x180008665  mov     edx, [r8-4]
0x180008669  shr     edx, cl
0x18000866b  mov     [rbx+14h], edx
0x18000866e  mov     rbx, [rsp+8+arg_0]
0x180008673  sub     r8, rsi
0x180008676  mov     rbp, [rsp+8+arg_8]
0x18000867b  mov     rax, r8
0x18000867e  mov     rsi, [rsp+8+arg_10]
0x180008683  mov     rdi, [rsp+8+arg_18]
0x180008688  pop     r14
0x18000868a  retn
```
