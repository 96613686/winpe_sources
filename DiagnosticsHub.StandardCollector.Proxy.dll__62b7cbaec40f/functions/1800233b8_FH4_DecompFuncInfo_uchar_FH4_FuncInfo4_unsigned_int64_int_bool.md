# FH4::DecompFuncInfo(uchar *,FH4::FuncInfo4 &,unsigned __int64,int,bool)

- ea: `0x1800233b8`
- end: `0x1800234e4`
- name: `?DecompFuncInfo@FH4@@YA_JPEAEAEAUFuncInfo4@1@_KH_N@Z`
- size: `300`
- prototype: `__int64 __fastcall(FH4 *__hidden this, unsigned __int8 *, struct FH4::FuncInfo4 *, unsigned __int64, char, bool)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800233a4`
- `0x180024004`

## callees

- `0x1800233b8`

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
0x1800233b8  mov     rax, rsp
0x1800233bb  mov     [rax+8], rbx
0x1800233bf  mov     [rax+10h], rbp
0x1800233c3  mov     [rax+18h], rsi
0x1800233c7  mov     [rax+20h], rdi
0x1800233cb  mov     bl, [rcx]
0x1800233cd  lea     r10, [rcx+1]
0x1800233d1  mov     [rdx], bl
0x1800233d3  mov     esi, r9d
0x1800233d6  lea     rbp, cs:180000000h
0x1800233dd  mov     r9, r8
0x1800233e0  mov     r11, rdx
0x1800233e3  mov     rdi, rcx
0x1800233e6  test    bl, 4
0x1800233e9  jz      short loc_18002340E
0x1800233eb  movzx   ecx, byte ptr [r10]
0x1800233ef  and     ecx, 0Fh
0x1800233f2  movsx   rax, byte ptr [rcx+rbp+6D0A0h]
0x1800233fb  mov     cl, [rcx+rbp+6D0B0h]
0x180023402  sub     r10, rax
0x180023405  mov     eax, [r10-4]
0x180023409  shr     eax, cl
0x18002340b  mov     [rdx+4], eax
0x18002340e  test    bl, 8
0x180023411  jz      short loc_18002341D
0x180023413  mov     eax, [r10]
0x180023416  add     r10, 4
0x18002341a  mov     [rdx+8], eax
0x18002341d  test    bl, 10h
0x180023420  jz      short loc_18002342C
0x180023422  mov     eax, [r10]
0x180023425  add     r10, 4
0x180023429  mov     [rdx+0Ch], eax
0x18002342c  xor     edx, edx
0x18002342e  lea     r8, [r10+4]
0x180023432  cmp     [rsp+arg_20], dl
0x180023436  jnz     short loc_180023499
0x180023438  test    bl, 2
0x18002343b  jz      short loc_180023499
0x18002343d  mov     [r11+10h], edx
0x180023441  cmp     [r10], edx
0x180023444  jz      short loc_180023490
0x180023446  movsxd  rax, dword ptr [r10]
0x180023449  add     r9, rax
0x18002344c  movzx   ecx, byte ptr [r9]
0x180023450  and     ecx, 0Fh
0x180023453  movsx   rax, byte ptr [rcx+rbp+6D0A0h]
0x18002345c  mov     cl, [rcx+rbp+6D0B0h]
0x180023463  sub     r9, rax
0x180023466  mov     r10d, [r9-4]
0x18002346a  shr     r10d, cl
0x18002346d  test    r10d, r10d
0x180023470  jz      short loc_1800234A0
0x180023472  mov     eax, [r9]
0x180023475  mov     ecx, [r9+4]
0x180023479  lea     r9, [r9+8]
0x18002347d  cmp     eax, esi
0x18002347f  jz      short loc_18002348A
0x180023481  inc     edx
0x180023483  cmp     edx, r10d
0x180023486  jb      short loc_180023472
0x180023488  jmp     short loc_1800234A0
0x18002348a  mov     [r11+10h], ecx
0x18002348e  jmp     short loc_1800234A0
0x180023490  mov     ecx, 7
0x180023495  int     29h; Win8: RtlFailFast(ecx)
0x180023497  jmp     short loc_1800234A0
0x180023499  mov     eax, [r10]
0x18002349c  mov     [r11+10h], eax
0x1800234a0  test    bl, 1
0x1800234a3  jz      short loc_1800234C9
0x1800234a5  movzx   ecx, byte ptr [r8]
0x1800234a9  and     ecx, 0Fh
0x1800234ac  movsx   rdx, byte ptr [rcx+rbp+6D0A0h]
0x1800234b5  mov     cl, [rcx+rbp+6D0B0h]
0x1800234bc  sub     r8, rdx
0x1800234bf  mov     edx, [r8-4]
0x1800234c3  shr     edx, cl
0x1800234c5  mov     [r11+14h], edx
0x1800234c9  mov     rbx, [rsp+arg_0]
0x1800234ce  sub     r8, rdi
0x1800234d1  mov     rbp, [rsp+arg_8]
0x1800234d6  mov     rax, r8
0x1800234d9  mov     rsi, [rsp+arg_10]
0x1800234de  mov     rdi, [rsp+arg_18]
0x1800234e3  retn
```
