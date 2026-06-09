# FH4::DecompFuncInfo(uchar *,FH4::FuncInfo4 &,unsigned __int64,int,bool)

- ea: `0x14000b234`
- end: `0x14000b360`
- name: `?DecompFuncInfo@FH4@@YA_JPEAEAEAUFuncInfo4@1@_KH_N@Z`
- size: `300`
- prototype: `__int64 __fastcall(FH4 *this, unsigned __int8 *, struct FH4::FuncInfo4 *, int, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000b980`

## callees

- `0x14000b234`

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
0x14000b234  mov     rax, rsp
0x14000b237  mov     [rax+8], rbx
0x14000b23b  mov     [rax+10h], rbp
0x14000b23f  mov     [rax+18h], rsi
0x14000b243  mov     [rax+20h], rdi
0x14000b247  mov     bl, [rcx]
0x14000b249  lea     r10, [rcx+1]
0x14000b24d  mov     [rdx], bl
0x14000b24f  mov     esi, r9d
0x14000b252  lea     rbp, cs:140000000h
0x14000b259  mov     r9, r8
0x14000b25c  mov     r11, rdx
0x14000b25f  mov     rdi, rcx
0x14000b262  test    bl, 4
0x14000b265  jz      short loc_14000B28A
0x14000b267  movzx   ecx, byte ptr [r10]
0x14000b26b  and     ecx, 0Fh
0x14000b26e  movsx   rax, byte ptr [rcx+rbp+115A0h]
0x14000b277  mov     cl, [rcx+rbp+115B0h]
0x14000b27e  sub     r10, rax
0x14000b281  mov     eax, [r10-4]
0x14000b285  shr     eax, cl
0x14000b287  mov     [rdx+4], eax
0x14000b28a  test    bl, 8
0x14000b28d  jz      short loc_14000B299
0x14000b28f  mov     eax, [r10]
0x14000b292  add     r10, 4
0x14000b296  mov     [rdx+8], eax
0x14000b299  test    bl, 10h
0x14000b29c  jz      short loc_14000B2A8
0x14000b29e  mov     eax, [r10]
0x14000b2a1  add     r10, 4
0x14000b2a5  mov     [rdx+0Ch], eax
0x14000b2a8  xor     edx, edx
0x14000b2aa  lea     r8, [r10+4]
0x14000b2ae  cmp     [rsp+arg_20], dl
0x14000b2b2  jnz     short loc_14000B315
0x14000b2b4  test    bl, 2
0x14000b2b7  jz      short loc_14000B315
0x14000b2b9  mov     [r11+10h], edx
0x14000b2bd  cmp     [r10], edx
0x14000b2c0  jz      short loc_14000B30C
0x14000b2c2  movsxd  rax, dword ptr [r10]
0x14000b2c5  add     r9, rax
0x14000b2c8  movzx   ecx, byte ptr [r9]
0x14000b2cc  and     ecx, 0Fh
0x14000b2cf  movsx   rax, byte ptr [rcx+rbp+115A0h]
0x14000b2d8  mov     cl, [rcx+rbp+115B0h]
0x14000b2df  sub     r9, rax
0x14000b2e2  mov     r10d, [r9-4]
0x14000b2e6  shr     r10d, cl
0x14000b2e9  test    r10d, r10d
0x14000b2ec  jz      short loc_14000B31C
0x14000b2ee  mov     eax, [r9]
0x14000b2f1  mov     ecx, [r9+4]
0x14000b2f5  lea     r9, [r9+8]
0x14000b2f9  cmp     eax, esi
0x14000b2fb  jz      short loc_14000B306
0x14000b2fd  inc     edx
0x14000b2ff  cmp     edx, r10d
0x14000b302  jb      short loc_14000B2EE
0x14000b304  jmp     short loc_14000B31C
0x14000b306  mov     [r11+10h], ecx
0x14000b30a  jmp     short loc_14000B31C
0x14000b30c  mov     ecx, 7
0x14000b311  int     29h; Win8: RtlFailFast(ecx)
0x14000b313  jmp     short loc_14000B31C
0x14000b315  mov     eax, [r10]
0x14000b318  mov     [r11+10h], eax
0x14000b31c  test    bl, 1
0x14000b31f  jz      short loc_14000B345
0x14000b321  movzx   ecx, byte ptr [r8]
0x14000b325  and     ecx, 0Fh
0x14000b328  movsx   rdx, byte ptr [rcx+rbp+115A0h]
0x14000b331  mov     cl, [rcx+rbp+115B0h]
0x14000b338  sub     r8, rdx
0x14000b33b  mov     edx, [r8-4]
0x14000b33f  shr     edx, cl
0x14000b341  mov     [r11+14h], edx
0x14000b345  mov     rbx, [rsp+arg_0]
0x14000b34a  sub     r8, rdi
0x14000b34d  mov     rbp, [rsp+arg_8]
0x14000b352  mov     rax, r8
0x14000b355  mov     rsi, [rsp+arg_10]
0x14000b35a  mov     rdi, [rsp+arg_18]
0x14000b35f  retn
```
