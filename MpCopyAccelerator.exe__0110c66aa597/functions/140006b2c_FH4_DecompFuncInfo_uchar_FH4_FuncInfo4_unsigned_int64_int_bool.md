# FH4::DecompFuncInfo(uchar *,FH4::FuncInfo4 &,unsigned __int64,int,bool)

- ea: `0x140006b2c`
- end: `0x140006c58`
- name: `?DecompFuncInfo@FH4@@YA_JPEAEAEAUFuncInfo4@1@_KH_N@Z`
- size: `300`
- prototype: `__int64 __fastcall(FH4 *__hidden this, unsigned __int8 *, struct FH4::FuncInfo4 *, unsigned __int64, char, bool)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000766c`

## callees

- `0x140006b2c`

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
0x140006b2c  mov     rax, rsp
0x140006b2f  mov     [rax+8], rbx
0x140006b33  mov     [rax+10h], rbp
0x140006b37  mov     [rax+18h], rsi
0x140006b3b  mov     [rax+20h], rdi
0x140006b3f  mov     bl, [rcx]
0x140006b41  lea     r10, [rcx+1]
0x140006b45  mov     [rdx], bl
0x140006b47  mov     esi, r9d
0x140006b4a  lea     rbp, cs:140000000h
0x140006b51  mov     r9, r8
0x140006b54  mov     r11, rdx
0x140006b57  mov     rdi, rcx
0x140006b5a  test    bl, 4
0x140006b5d  jz      short loc_140006B82
0x140006b5f  movzx   ecx, byte ptr [r10]
0x140006b63  and     ecx, 0Fh
0x140006b66  movsx   rax, byte ptr [rcx+rbp+280B0h]
0x140006b6f  mov     cl, [rcx+rbp+280C0h]
0x140006b76  sub     r10, rax
0x140006b79  mov     eax, [r10-4]
0x140006b7d  shr     eax, cl
0x140006b7f  mov     [rdx+4], eax
0x140006b82  test    bl, 8
0x140006b85  jz      short loc_140006B91
0x140006b87  mov     eax, [r10]
0x140006b8a  add     r10, 4
0x140006b8e  mov     [rdx+8], eax
0x140006b91  test    bl, 10h
0x140006b94  jz      short loc_140006BA0
0x140006b96  mov     eax, [r10]
0x140006b99  add     r10, 4
0x140006b9d  mov     [rdx+0Ch], eax
0x140006ba0  xor     edx, edx
0x140006ba2  lea     r8, [r10+4]
0x140006ba6  cmp     [rsp+arg_20], dl
0x140006baa  jnz     short loc_140006C0D
0x140006bac  test    bl, 2
0x140006baf  jz      short loc_140006C0D
0x140006bb1  mov     [r11+10h], edx
0x140006bb5  cmp     [r10], edx
0x140006bb8  jz      short loc_140006C04
0x140006bba  movsxd  rax, dword ptr [r10]
0x140006bbd  add     r9, rax
0x140006bc0  movzx   ecx, byte ptr [r9]
0x140006bc4  and     ecx, 0Fh
0x140006bc7  movsx   rax, byte ptr [rcx+rbp+280B0h]
0x140006bd0  mov     cl, [rcx+rbp+280C0h]
0x140006bd7  sub     r9, rax
0x140006bda  mov     r10d, [r9-4]
0x140006bde  shr     r10d, cl
0x140006be1  test    r10d, r10d
0x140006be4  jz      short loc_140006C14
0x140006be6  mov     eax, [r9]
0x140006be9  mov     ecx, [r9+4]
0x140006bed  lea     r9, [r9+8]
0x140006bf1  cmp     eax, esi
0x140006bf3  jz      short loc_140006BFE
0x140006bf5  inc     edx
0x140006bf7  cmp     edx, r10d
0x140006bfa  jb      short loc_140006BE6
0x140006bfc  jmp     short loc_140006C14
0x140006bfe  mov     [r11+10h], ecx
0x140006c02  jmp     short loc_140006C14
0x140006c04  mov     ecx, 7
0x140006c09  int     29h; Win8: RtlFailFast(ecx)
0x140006c0b  jmp     short loc_140006C14
0x140006c0d  mov     eax, [r10]
0x140006c10  mov     [r11+10h], eax
0x140006c14  test    bl, 1
0x140006c17  jz      short loc_140006C3D
0x140006c19  movzx   ecx, byte ptr [r8]
0x140006c1d  and     ecx, 0Fh
0x140006c20  movsx   rdx, byte ptr [rcx+rbp+280B0h]
0x140006c29  mov     cl, [rcx+rbp+280C0h]
0x140006c30  sub     r8, rdx
0x140006c33  mov     edx, [r8-4]
0x140006c37  shr     edx, cl
0x140006c39  mov     [r11+14h], edx
0x140006c3d  mov     rbx, [rsp+arg_0]
0x140006c42  sub     r8, rdi
0x140006c45  mov     rbp, [rsp+arg_8]
0x140006c4a  mov     rax, r8
0x140006c4d  mov     rsi, [rsp+arg_10]
0x140006c52  mov     rdi, [rsp+arg_18]
0x140006c57  retn
```
