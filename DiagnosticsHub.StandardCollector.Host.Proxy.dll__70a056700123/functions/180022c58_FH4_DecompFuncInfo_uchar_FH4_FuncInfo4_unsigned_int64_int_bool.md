# FH4::DecompFuncInfo(uchar *,FH4::FuncInfo4 &,unsigned __int64,int,bool)

- ea: `0x180022c58`
- end: `0x180022d84`
- name: `?DecompFuncInfo@FH4@@YA_JPEAEAEAUFuncInfo4@1@_KH_N@Z`
- size: `300`
- prototype: `__int64 __fastcall(FH4 *__hidden this, unsigned __int8 *, struct FH4::FuncInfo4 *, unsigned __int64, char, bool)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180022c44`
- `0x1800238a4`

## callees

- `0x180022c58`

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
0x180022c58  mov     rax, rsp
0x180022c5b  mov     [rax+8], rbx
0x180022c5f  mov     [rax+10h], rbp
0x180022c63  mov     [rax+18h], rsi
0x180022c67  mov     [rax+20h], rdi
0x180022c6b  mov     bl, [rcx]
0x180022c6d  lea     r10, [rcx+1]
0x180022c71  mov     [rdx], bl
0x180022c73  mov     esi, r9d
0x180022c76  lea     rbp, cs:180000000h
0x180022c7d  mov     r9, r8
0x180022c80  mov     r11, rdx
0x180022c83  mov     rdi, rcx
0x180022c86  test    bl, 4
0x180022c89  jz      short loc_180022CAE
0x180022c8b  movzx   ecx, byte ptr [r10]
0x180022c8f  and     ecx, 0Fh
0x180022c92  movsx   rax, byte ptr [rcx+rbp+699C0h]
0x180022c9b  mov     cl, [rcx+rbp+699D0h]
0x180022ca2  sub     r10, rax
0x180022ca5  mov     eax, [r10-4]
0x180022ca9  shr     eax, cl
0x180022cab  mov     [rdx+4], eax
0x180022cae  test    bl, 8
0x180022cb1  jz      short loc_180022CBD
0x180022cb3  mov     eax, [r10]
0x180022cb6  add     r10, 4
0x180022cba  mov     [rdx+8], eax
0x180022cbd  test    bl, 10h
0x180022cc0  jz      short loc_180022CCC
0x180022cc2  mov     eax, [r10]
0x180022cc5  add     r10, 4
0x180022cc9  mov     [rdx+0Ch], eax
0x180022ccc  xor     edx, edx
0x180022cce  lea     r8, [r10+4]
0x180022cd2  cmp     [rsp+arg_20], dl
0x180022cd6  jnz     short loc_180022D39
0x180022cd8  test    bl, 2
0x180022cdb  jz      short loc_180022D39
0x180022cdd  mov     [r11+10h], edx
0x180022ce1  cmp     [r10], edx
0x180022ce4  jz      short loc_180022D30
0x180022ce6  movsxd  rax, dword ptr [r10]
0x180022ce9  add     r9, rax
0x180022cec  movzx   ecx, byte ptr [r9]
0x180022cf0  and     ecx, 0Fh
0x180022cf3  movsx   rax, byte ptr [rcx+rbp+699C0h]
0x180022cfc  mov     cl, [rcx+rbp+699D0h]
0x180022d03  sub     r9, rax
0x180022d06  mov     r10d, [r9-4]
0x180022d0a  shr     r10d, cl
0x180022d0d  test    r10d, r10d
0x180022d10  jz      short loc_180022D40
0x180022d12  mov     eax, [r9]
0x180022d15  mov     ecx, [r9+4]
0x180022d19  lea     r9, [r9+8]
0x180022d1d  cmp     eax, esi
0x180022d1f  jz      short loc_180022D2A
0x180022d21  inc     edx
0x180022d23  cmp     edx, r10d
0x180022d26  jb      short loc_180022D12
0x180022d28  jmp     short loc_180022D40
0x180022d2a  mov     [r11+10h], ecx
0x180022d2e  jmp     short loc_180022D40
0x180022d30  mov     ecx, 7
0x180022d35  int     29h; Win8: RtlFailFast(ecx)
0x180022d37  jmp     short loc_180022D40
0x180022d39  mov     eax, [r10]
0x180022d3c  mov     [r11+10h], eax
0x180022d40  test    bl, 1
0x180022d43  jz      short loc_180022D69
0x180022d45  movzx   ecx, byte ptr [r8]
0x180022d49  and     ecx, 0Fh
0x180022d4c  movsx   rdx, byte ptr [rcx+rbp+699C0h]
0x180022d55  mov     cl, [rcx+rbp+699D0h]
0x180022d5c  sub     r8, rdx
0x180022d5f  mov     edx, [r8-4]
0x180022d63  shr     edx, cl
0x180022d65  mov     [r11+14h], edx
0x180022d69  mov     rbx, [rsp+arg_0]
0x180022d6e  sub     r8, rdi
0x180022d71  mov     rbp, [rsp+arg_8]
0x180022d76  mov     rax, r8
0x180022d79  mov     rsi, [rsp+arg_10]
0x180022d7e  mov     rdi, [rsp+arg_18]
0x180022d83  retn
```
