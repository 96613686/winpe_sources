# FH4::DecompFuncInfo(uchar *,FH4::FuncInfo4 &,unsigned __int64,int,bool)

- ea: `0x180008204`
- end: `0x180008330`
- name: `?DecompFuncInfo@FH4@@YA_JPEAEAEAUFuncInfo4@1@_KH_N@Z`
- size: `300`
- prototype: `__int64 __fastcall(FH4 *this, unsigned __int8 *, struct FH4::FuncInfo4 *, int, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008904`

## callees

- `0x180008204`

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
0x180008204  mov     rax, rsp
0x180008207  mov     [rax+8], rbx
0x18000820b  mov     [rax+10h], rbp
0x18000820f  mov     [rax+18h], rsi
0x180008213  mov     [rax+20h], rdi
0x180008217  mov     bl, [rcx]
0x180008219  lea     r10, [rcx+1]
0x18000821d  mov     [rdx], bl
0x18000821f  mov     esi, r9d
0x180008222  lea     rbp, cs:180000000h
0x180008229  mov     r9, r8
0x18000822c  mov     r11, rdx
0x18000822f  mov     rdi, rcx
0x180008232  test    bl, 4
0x180008235  jz      short loc_18000825A
0x180008237  movzx   ecx, byte ptr [r10]
0x18000823b  and     ecx, 0Fh
0x18000823e  movsx   rax, byte ptr [rcx+rbp+0D5E8h]
0x180008247  mov     cl, [rcx+rbp+0D5F8h]
0x18000824e  sub     r10, rax
0x180008251  mov     eax, [r10-4]
0x180008255  shr     eax, cl
0x180008257  mov     [rdx+4], eax
0x18000825a  test    bl, 8
0x18000825d  jz      short loc_180008269
0x18000825f  mov     eax, [r10]
0x180008262  add     r10, 4
0x180008266  mov     [rdx+8], eax
0x180008269  test    bl, 10h
0x18000826c  jz      short loc_180008278
0x18000826e  mov     eax, [r10]
0x180008271  add     r10, 4
0x180008275  mov     [rdx+0Ch], eax
0x180008278  xor     edx, edx
0x18000827a  lea     r8, [r10+4]
0x18000827e  cmp     [rsp+arg_20], dl
0x180008282  jnz     short loc_1800082E5
0x180008284  test    bl, 2
0x180008287  jz      short loc_1800082E5
0x180008289  mov     [r11+10h], edx
0x18000828d  cmp     [r10], edx
0x180008290  jz      short loc_1800082DC
0x180008292  movsxd  rax, dword ptr [r10]
0x180008295  add     r9, rax
0x180008298  movzx   ecx, byte ptr [r9]
0x18000829c  and     ecx, 0Fh
0x18000829f  movsx   rax, byte ptr [rcx+rbp+0D5E8h]
0x1800082a8  mov     cl, [rcx+rbp+0D5F8h]
0x1800082af  sub     r9, rax
0x1800082b2  mov     r10d, [r9-4]
0x1800082b6  shr     r10d, cl
0x1800082b9  test    r10d, r10d
0x1800082bc  jz      short loc_1800082EC
0x1800082be  mov     eax, [r9]
0x1800082c1  mov     ecx, [r9+4]
0x1800082c5  lea     r9, [r9+8]
0x1800082c9  cmp     eax, esi
0x1800082cb  jz      short loc_1800082D6
0x1800082cd  inc     edx
0x1800082cf  cmp     edx, r10d
0x1800082d2  jb      short loc_1800082BE
0x1800082d4  jmp     short loc_1800082EC
0x1800082d6  mov     [r11+10h], ecx
0x1800082da  jmp     short loc_1800082EC
0x1800082dc  mov     ecx, 7
0x1800082e1  int     29h; Win8: RtlFailFast(ecx)
0x1800082e3  jmp     short loc_1800082EC
0x1800082e5  mov     eax, [r10]
0x1800082e8  mov     [r11+10h], eax
0x1800082ec  test    bl, 1
0x1800082ef  jz      short loc_180008315
0x1800082f1  movzx   ecx, byte ptr [r8]
0x1800082f5  and     ecx, 0Fh
0x1800082f8  movsx   rdx, byte ptr [rcx+rbp+0D5E8h]
0x180008301  mov     cl, [rcx+rbp+0D5F8h]
0x180008308  sub     r8, rdx
0x18000830b  mov     edx, [r8-4]
0x18000830f  shr     edx, cl
0x180008311  mov     [r11+14h], edx
0x180008315  mov     rbx, [rsp+arg_0]
0x18000831a  sub     r8, rdi
0x18000831d  mov     rbp, [rsp+arg_8]
0x180008322  mov     rax, r8
0x180008325  mov     rsi, [rsp+arg_10]
0x18000832a  mov     rdi, [rsp+arg_18]
0x18000832f  retn
```
