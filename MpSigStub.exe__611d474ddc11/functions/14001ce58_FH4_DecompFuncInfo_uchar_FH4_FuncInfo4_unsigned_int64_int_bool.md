# FH4::DecompFuncInfo(uchar *,FH4::FuncInfo4 &,unsigned __int64,int,bool)

- ea: `0x14001ce58`
- end: `0x14001cf8a`
- name: `?DecompFuncInfo@FH4@@YA_JPEAEAEAUFuncInfo4@1@_KH_N@Z`
- size: `306`
- prototype: `__int64 __fastcall(FH4 *this, unsigned __int8 *, struct FH4::FuncInfo4 *, int, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001d960`

## callees

- `0x14001ce58`

## pseudocode

```c
__int64 __fastcall FH4::DecompFuncInfo(FH4 *this, unsigned __int8 *a2, struct FH4::FuncInfo4 *a3, int a4, char a5)
{
  unsigned __int8 v5; // bl
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
    v6 -= *((char *)qword_1400BBEB0 + v11);
    *((_DWORD *)a2 + 1) = *((_DWORD *)v6 - 1) >> *((_BYTE *)&qword_1400BBEB0[2] + v11);
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
    v18 = (int *)&v16[-*((char *)qword_1400BBEB0 + v17)];
    v19 = (unsigned int)*(v18 - 1) >> *((_BYTE *)&qword_1400BBEB0[2] + v17);
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
    v15 -= *((char *)qword_1400BBEB0 + v22);
    *((_DWORD *)a2 + 5) = *((_DWORD *)v15 - 1) >> *((_BYTE *)&qword_1400BBEB0[2] + v22);
  }
  return v15 - (_BYTE *)this;
}

```

## disassembly

```asm
0x14001ce58  mov     rax, rsp
0x14001ce5b  mov     [rax+8], rbx
0x14001ce5f  mov     [rax+10h], rbp
0x14001ce63  mov     [rax+18h], rsi
0x14001ce67  mov     [rax+20h], rdi
0x14001ce6b  push    r14
0x14001ce6d  mov     bl, [rcx]
0x14001ce6f  lea     r10, [rcx+1]
0x14001ce73  mov     [rdx], bl
0x14001ce75  mov     esi, r9d
0x14001ce78  lea     r14, cs:140000000h
0x14001ce7f  mov     rbp, r8
0x14001ce82  mov     r11, rdx
0x14001ce85  mov     rdi, rcx
0x14001ce88  test    bl, 4
0x14001ce8b  jz      short loc_14001CEB1
0x14001ce8d  movzx   ecx, byte ptr [r10]
0x14001ce91  and     ecx, 0Fh
0x14001ce94  movsx   rax, byte ptr [rcx+r14+0BBEB0h]
0x14001ce9d  mov     cl, [rcx+r14+0BBEC0h]
0x14001cea5  sub     r10, rax
0x14001cea8  mov     eax, [r10-4]
0x14001ceac  shr     eax, cl
0x14001ceae  mov     [rdx+4], eax
0x14001ceb1  test    bl, 8
0x14001ceb4  jz      short loc_14001CEC0
0x14001ceb6  mov     eax, [r10]
0x14001ceb9  add     r10, 4
0x14001cebd  mov     [rdx+8], eax
0x14001cec0  test    bl, 10h
0x14001cec3  jz      short loc_14001CECF
0x14001cec5  mov     eax, [r10]
0x14001cec8  add     r10, 4
0x14001cecc  mov     [rdx+0Ch], eax
0x14001cecf  xor     r9d, r9d
0x14001ced2  lea     r8, [r10+4]
0x14001ced6  cmp     [rsp+8+arg_20], r9b
0x14001cedb  jnz     short loc_14001CF3D
0x14001cedd  test    bl, 2
0x14001cee0  jz      short loc_14001CF3D
0x14001cee2  mov     [rdx+10h], r9d
0x14001cee6  cmp     [r10], r9d
0x14001cee9  jz      short loc_14001CF34
0x14001ceeb  movsxd  rdx, dword ptr [r10]
0x14001ceee  add     rdx, rbp
0x14001cef1  movzx   ecx, byte ptr [rdx]
0x14001cef4  and     ecx, 0Fh
0x14001cef7  movsx   rax, byte ptr [rcx+r14+0BBEB0h]
0x14001cf00  mov     cl, [rcx+r14+0BBEC0h]
0x14001cf08  sub     rdx, rax
0x14001cf0b  mov     r10d, [rdx-4]
0x14001cf0f  shr     r10d, cl
0x14001cf12  test    r10d, r10d
0x14001cf15  jz      short loc_14001CF43
0x14001cf17  mov     eax, [rdx]
0x14001cf19  mov     ecx, [rdx+4]
0x14001cf1c  lea     rdx, [rdx+8]
0x14001cf20  cmp     eax, esi
0x14001cf22  jz      short loc_14001CF2E
0x14001cf24  inc     r9d
0x14001cf27  cmp     r9d, r10d
0x14001cf2a  jb      short loc_14001CF17
0x14001cf2c  jmp     short loc_14001CF43
0x14001cf2e  mov     [r11+10h], ecx
0x14001cf32  jmp     short loc_14001CF43
0x14001cf34  mov     ecx, 7
0x14001cf39  int     29h; Win8: RtlFailFast(ecx)
0x14001cf3b  jmp     short loc_14001CF43
0x14001cf3d  mov     eax, [r10]
0x14001cf40  mov     [rdx+10h], eax
0x14001cf43  test    bl, 1
0x14001cf46  jz      short loc_14001CF6D
0x14001cf48  movzx   ecx, byte ptr [r8]
0x14001cf4c  and     ecx, 0Fh
0x14001cf4f  movsx   rdx, byte ptr [rcx+r14+0BBEB0h]
0x14001cf58  mov     cl, [rcx+r14+0BBEC0h]
0x14001cf60  sub     r8, rdx
0x14001cf63  mov     edx, [r8-4]
0x14001cf67  shr     edx, cl
0x14001cf69  mov     [r11+14h], edx
0x14001cf6d  mov     rbx, [rsp+8+arg_0]
0x14001cf72  sub     r8, rdi
0x14001cf75  mov     rbp, [rsp+8+arg_8]
0x14001cf7a  mov     rax, r8
0x14001cf7d  mov     rsi, [rsp+8+arg_10]
0x14001cf82  mov     rdi, [rsp+8+arg_18]
0x14001cf87  pop     r14
0x14001cf89  retn
```
