# FH4::DecompFuncInfo(uchar *,FH4::FuncInfo4 &,unsigned __int64,int,bool)

- ea: `0x18000fe68`
- end: `0x18000ff94`
- name: `?DecompFuncInfo@FH4@@YA_JPEAEAEAUFuncInfo4@1@_KH_N@Z`
- size: `300`
- prototype: `__int64 __fastcall(FH4 *__hidden this, unsigned __int8 *, struct FH4::FuncInfo4 *, unsigned __int64, char, bool)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010a24`

## callees

- `0x18000fe68`

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
0x18000fe68  mov     rax, rsp
0x18000fe6b  mov     [rax+8], rbx
0x18000fe6f  mov     [rax+10h], rbp
0x18000fe73  mov     [rax+18h], rsi
0x18000fe77  mov     [rax+20h], rdi
0x18000fe7b  mov     bl, [rcx]
0x18000fe7d  lea     r10, [rcx+1]
0x18000fe81  mov     [rdx], bl
0x18000fe83  mov     esi, r9d
0x18000fe86  lea     rbp, __ImageBase
0x18000fe8d  mov     r9, r8
0x18000fe90  mov     r11, rdx
0x18000fe93  mov     rdi, rcx
0x18000fe96  test    bl, 4
0x18000fe99  jz      short loc_18000FEBE
0x18000fe9b  movzx   ecx, byte ptr [r10]
0x18000fe9f  and     ecx, 0Fh
0x18000fea2  movsx   rax, byte ptr [rcx+rbp+177D8h]
0x18000feab  mov     cl, [rcx+rbp+177E8h]
0x18000feb2  sub     r10, rax
0x18000feb5  mov     eax, [r10-4]
0x18000feb9  shr     eax, cl
0x18000febb  mov     [rdx+4], eax
0x18000febe  test    bl, 8
0x18000fec1  jz      short loc_18000FECD
0x18000fec3  mov     eax, [r10]
0x18000fec6  add     r10, 4
0x18000feca  mov     [rdx+8], eax
0x18000fecd  test    bl, 10h
0x18000fed0  jz      short loc_18000FEDC
0x18000fed2  mov     eax, [r10]
0x18000fed5  add     r10, 4
0x18000fed9  mov     [rdx+0Ch], eax
0x18000fedc  xor     edx, edx
0x18000fede  lea     r8, [r10+4]
0x18000fee2  cmp     [rsp+arg_20], dl
0x18000fee6  jnz     short loc_18000FF49
0x18000fee8  test    bl, 2
0x18000feeb  jz      short loc_18000FF49
0x18000feed  mov     [r11+10h], edx
0x18000fef1  cmp     [r10], edx
0x18000fef4  jz      short loc_18000FF40
0x18000fef6  movsxd  rax, dword ptr [r10]
0x18000fef9  add     r9, rax
0x18000fefc  movzx   ecx, byte ptr [r9]
0x18000ff00  and     ecx, 0Fh
0x18000ff03  movsx   rax, byte ptr [rcx+rbp+177D8h]
0x18000ff0c  mov     cl, [rcx+rbp+177E8h]
0x18000ff13  sub     r9, rax
0x18000ff16  mov     r10d, [r9-4]
0x18000ff1a  shr     r10d, cl
0x18000ff1d  test    r10d, r10d
0x18000ff20  jz      short loc_18000FF50
0x18000ff22  mov     eax, [r9]
0x18000ff25  mov     ecx, [r9+4]
0x18000ff29  lea     r9, [r9+8]
0x18000ff2d  cmp     eax, esi
0x18000ff2f  jz      short loc_18000FF3A
0x18000ff31  inc     edx
0x18000ff33  cmp     edx, r10d
0x18000ff36  jb      short loc_18000FF22
0x18000ff38  jmp     short loc_18000FF50
0x18000ff3a  mov     [r11+10h], ecx
0x18000ff3e  jmp     short loc_18000FF50
0x18000ff40  mov     ecx, 7
0x18000ff45  int     29h; Win8: RtlFailFast(ecx)
0x18000ff47  jmp     short loc_18000FF50
0x18000ff49  mov     eax, [r10]
0x18000ff4c  mov     [r11+10h], eax
0x18000ff50  test    bl, 1
0x18000ff53  jz      short loc_18000FF79
0x18000ff55  movzx   ecx, byte ptr [r8]
0x18000ff59  and     ecx, 0Fh
0x18000ff5c  movsx   rdx, byte ptr [rcx+rbp+177D8h]
0x18000ff65  mov     cl, [rcx+rbp+177E8h]
0x18000ff6c  sub     r8, rdx
0x18000ff6f  mov     edx, [r8-4]
0x18000ff73  shr     edx, cl
0x18000ff75  mov     [r11+14h], edx
0x18000ff79  mov     rbx, [rsp+arg_0]
0x18000ff7e  sub     r8, rdi
0x18000ff81  mov     rbp, [rsp+arg_8]
0x18000ff86  mov     rax, r8
0x18000ff89  mov     rsi, [rsp+arg_10]
0x18000ff8e  mov     rdi, [rsp+arg_18]
0x18000ff93  retn
```
