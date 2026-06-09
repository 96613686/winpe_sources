# FH4::DecompFuncInfo(uchar *,FH4::FuncInfo4 &,unsigned __int64,int,bool)

- ea: `0x180019214`
- end: `0x180019340`
- name: `?DecompFuncInfo@FH4@@YA_JPEAEAEAUFuncInfo4@1@_KH_N@Z`
- size: `300`
- prototype: `__int64 __fastcall(FH4 *this, unsigned __int8 *, struct FH4::FuncInfo4 *, int, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180019914`

## callees

- `0x180019214`

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
0x180019214  mov     rax, rsp
0x180019217  mov     [rax+8], rbx
0x18001921b  mov     [rax+10h], rbp
0x18001921f  mov     [rax+18h], rsi
0x180019223  mov     [rax+20h], rdi
0x180019227  mov     bl, [rcx]
0x180019229  lea     r10, [rcx+1]
0x18001922d  mov     [rdx], bl
0x18001922f  mov     esi, r9d
0x180019232  lea     rbp, cs:180000000h
0x180019239  mov     r9, r8
0x18001923c  mov     r11, rdx
0x18001923f  mov     rdi, rcx
0x180019242  test    bl, 4
0x180019245  jz      short loc_18001926A
0x180019247  movzx   ecx, byte ptr [r10]
0x18001924b  and     ecx, 0Fh
0x18001924e  movsx   rax, byte ptr [rcx+rbp+24098h]
0x180019257  mov     cl, [rcx+rbp+240A8h]
0x18001925e  sub     r10, rax
0x180019261  mov     eax, [r10-4]
0x180019265  shr     eax, cl
0x180019267  mov     [rdx+4], eax
0x18001926a  test    bl, 8
0x18001926d  jz      short loc_180019279
0x18001926f  mov     eax, [r10]
0x180019272  add     r10, 4
0x180019276  mov     [rdx+8], eax
0x180019279  test    bl, 10h
0x18001927c  jz      short loc_180019288
0x18001927e  mov     eax, [r10]
0x180019281  add     r10, 4
0x180019285  mov     [rdx+0Ch], eax
0x180019288  xor     edx, edx
0x18001928a  lea     r8, [r10+4]
0x18001928e  cmp     [rsp+arg_20], dl
0x180019292  jnz     short loc_1800192F5
0x180019294  test    bl, 2
0x180019297  jz      short loc_1800192F5
0x180019299  mov     [r11+10h], edx
0x18001929d  cmp     [r10], edx
0x1800192a0  jz      short loc_1800192EC
0x1800192a2  movsxd  rax, dword ptr [r10]
0x1800192a5  add     r9, rax
0x1800192a8  movzx   ecx, byte ptr [r9]
0x1800192ac  and     ecx, 0Fh
0x1800192af  movsx   rax, byte ptr [rcx+rbp+24098h]
0x1800192b8  mov     cl, [rcx+rbp+240A8h]
0x1800192bf  sub     r9, rax
0x1800192c2  mov     r10d, [r9-4]
0x1800192c6  shr     r10d, cl
0x1800192c9  test    r10d, r10d
0x1800192cc  jz      short loc_1800192FC
0x1800192ce  mov     eax, [r9]
0x1800192d1  mov     ecx, [r9+4]
0x1800192d5  lea     r9, [r9+8]
0x1800192d9  cmp     eax, esi
0x1800192db  jz      short loc_1800192E6
0x1800192dd  inc     edx
0x1800192df  cmp     edx, r10d
0x1800192e2  jb      short loc_1800192CE
0x1800192e4  jmp     short loc_1800192FC
0x1800192e6  mov     [r11+10h], ecx
0x1800192ea  jmp     short loc_1800192FC
0x1800192ec  mov     ecx, 7
0x1800192f1  int     29h; Win8: RtlFailFast(ecx)
0x1800192f3  jmp     short loc_1800192FC
0x1800192f5  mov     eax, [r10]
0x1800192f8  mov     [r11+10h], eax
0x1800192fc  test    bl, 1
0x1800192ff  jz      short loc_180019325
0x180019301  movzx   ecx, byte ptr [r8]
0x180019305  and     ecx, 0Fh
0x180019308  movsx   rdx, byte ptr [rcx+rbp+24098h]
0x180019311  mov     cl, [rcx+rbp+240A8h]
0x180019318  sub     r8, rdx
0x18001931b  mov     edx, [r8-4]
0x18001931f  shr     edx, cl
0x180019321  mov     [r11+14h], edx
0x180019325  mov     rbx, [rsp+arg_0]
0x18001932a  sub     r8, rdi
0x18001932d  mov     rbp, [rsp+arg_8]
0x180019332  mov     rax, r8
0x180019335  mov     rsi, [rsp+arg_10]
0x18001933a  mov     rdi, [rsp+arg_18]
0x18001933f  retn
```
