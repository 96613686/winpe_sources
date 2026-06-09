# UpdateDstMBUYVY(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x18001ce30`
- end: `0x18001d070`
- name: `?UpdateDstMBUYVY@@YAXPEAEPEBE11JJJ@Z`
- size: `576`
- prototype: `void __fastcall(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18001d990`

## callees

- `0x18001ce30`

## pseudocode

```c
void __fastcall UpdateDstMBUYVY(
        unsigned __int8 *a1,
        const unsigned __int8 *a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4,
        int a5,
        int a6,
        int a7)
{
  int v10; // r14d
  int v11; // r8d
  int v12; // edx
  int v13; // edx
  int v14; // edx
  int v15; // edx
  int v16; // edx
  int v17; // edx
  int v18; // eax
  int v19; // edx
  int v20; // edx
  int v21; // ecx
  int v22; // eax

  v10 = 8;
  do
  {
    v11 = *a3 | (*a4 << 16);
    *(_DWORD *)a1 = v11 | ((*a2 | (a2[1] << 16)) << 8);
    *(_DWORD *)&a1[a7] = v11 | ((a2[a5] | (a2[a5 + 1] << 16)) << 8);
    v12 = a3[1] | (a4[1] << 16);
    *((_DWORD *)a1 + 1) = v12 | ((a2[2] | (a2[3] << 16)) << 8);
    *(_DWORD *)&a1[a7 + 4] = v12 | ((a2[a5 + 2] | (a2[a5 + 3] << 16)) << 8);
    v13 = a3[2] | (a4[2] << 16);
    *((_DWORD *)a1 + 2) = v13 | ((a2[4] | (a2[5] << 16)) << 8);
    *(_DWORD *)&a1[a7 + 8] = v13 | ((a2[a5 + 4] | (a2[a5 + 5] << 16)) << 8);
    v14 = a3[3] | (a4[3] << 16);
    *((_DWORD *)a1 + 3) = v14 | ((a2[6] | (a2[7] << 16)) << 8);
    *(_DWORD *)&a1[a7 + 12] = v14 | ((a2[a5 + 6] | (a2[a5 + 7] << 16)) << 8);
    v15 = a3[4] | (a4[4] << 16);
    *((_DWORD *)a1 + 4) = v15 | ((a2[8] | (a2[9] << 16)) << 8);
    *(_DWORD *)&a1[a7 + 16] = v15 | ((a2[a5 + 8] | (a2[a5 + 9] << 16)) << 8);
    v16 = a3[5] | (a4[5] << 16);
    *((_DWORD *)a1 + 5) = v16 | ((a2[10] | (a2[11] << 16)) << 8);
    *(_DWORD *)&a1[a7 + 20] = v16 | ((a2[a5 + 10] | (a2[a5 + 11] << 16)) << 8);
    v17 = a3[6] | (a4[6] << 16);
    *((_DWORD *)a1 + 6) = v17 | ((a2[12] | (a2[13] << 16)) << 8);
    *(_DWORD *)&a1[a7 + 24] = v17 | ((a2[a5 + 12] | (a2[a5 + 13] << 16)) << 8);
    v18 = a3[7];
    a3 += a6;
    v19 = a4[7];
    a4 += a6;
    v20 = v18 | (v19 << 16);
    *((_DWORD *)a1 + 7) = v20 | ((a2[14] | (a2[15] << 16)) << 8);
    v21 = a2[a5 + 15];
    v22 = a2[a5 + 14];
    a2 += 2 * a5;
    *(_DWORD *)&a1[a7 + 28] = v20 | ((v22 | (v21 << 16)) << 8);
    a1 += 2 * a7;
    --v10;
  }
  while ( v10 );
}

```

## disassembly

```asm
0x18001ce30  push    rbx
0x18001ce32  push    rbp
0x18001ce33  push    rsi
0x18001ce34  push    rdi
0x18001ce35  push    r12
0x18001ce37  push    r14
0x18001ce39  push    r15
0x18001ce3b  movsxd  r11, [rsp+38h+arg_30]
0x18001ce40  mov     rsi, r8
0x18001ce43  movsxd  r10, [rsp+38h+arg_20]
0x18001ce48  mov     rbx, rdx
0x18001ce4b  movsxd  rbp, [rsp+38h+arg_28]
0x18001ce50  mov     rdi, rcx
0x18001ce53  mov     r14d, 8
0x18001ce59  lea     r15, [r11+r11]
0x18001ce5d  lea     r12, [r10+r10]
0x18001ce61  movzx   eax, byte ptr [rsi]
0x18001ce64  movzx   r8d, byte ptr [r9]
0x18001ce68  movzx   ecx, byte ptr [rbx+1]
0x18001ce6c  shl     ecx, 10h
0x18001ce6f  shl     r8d, 10h
0x18001ce73  or      r8d, eax
0x18001ce76  movzx   eax, byte ptr [rbx]
0x18001ce79  or      ecx, eax
0x18001ce7b  shl     ecx, 8
0x18001ce7e  or      ecx, r8d
0x18001ce81  mov     [rdi], ecx
0x18001ce83  movzx   eax, byte ptr [r10+rbx]
0x18001ce88  movzx   ecx, byte ptr [r10+rbx+1]
0x18001ce8e  shl     ecx, 10h
0x18001ce91  or      ecx, eax
0x18001ce93  shl     ecx, 8
0x18001ce96  or      ecx, r8d
0x18001ce99  mov     [r11+rdi], ecx
0x18001ce9d  movzx   eax, byte ptr [rsi+1]
0x18001cea1  movzx   edx, byte ptr [r9+1]
0x18001cea6  movzx   ecx, byte ptr [rbx+3]
0x18001ceaa  shl     ecx, 10h
0x18001cead  shl     edx, 10h
0x18001ceb0  or      edx, eax
0x18001ceb2  movzx   eax, byte ptr [rbx+2]
0x18001ceb6  or      ecx, eax
0x18001ceb8  shl     ecx, 8
0x18001cebb  or      ecx, edx
0x18001cebd  mov     [rdi+4], ecx
0x18001cec0  movzx   eax, byte ptr [r10+rbx+2]
0x18001cec6  movzx   ecx, byte ptr [r10+rbx+3]
0x18001cecc  shl     ecx, 10h
0x18001cecf  or      ecx, eax
0x18001ced1  shl     ecx, 8
0x18001ced4  or      ecx, edx
0x18001ced6  mov     [r11+rdi+4], ecx
0x18001cedb  movzx   eax, byte ptr [rsi+2]
0x18001cedf  movzx   edx, byte ptr [r9+2]
0x18001cee4  movzx   ecx, byte ptr [rbx+5]
0x18001cee8  shl     ecx, 10h
0x18001ceeb  shl     edx, 10h
0x18001ceee  or      edx, eax
0x18001cef0  movzx   eax, byte ptr [rbx+4]
0x18001cef4  or      ecx, eax
0x18001cef6  shl     ecx, 8
0x18001cef9  or      ecx, edx
0x18001cefb  mov     [rdi+8], ecx
0x18001cefe  movzx   eax, byte ptr [r10+rbx+4]
0x18001cf04  movzx   ecx, byte ptr [r10+rbx+5]
0x18001cf0a  shl     ecx, 10h
0x18001cf0d  or      ecx, eax
0x18001cf0f  shl     ecx, 8
0x18001cf12  or      ecx, edx
0x18001cf14  mov     [r11+rdi+8], ecx
0x18001cf19  movzx   eax, byte ptr [rsi+3]
0x18001cf1d  movzx   edx, byte ptr [r9+3]
0x18001cf22  movzx   ecx, byte ptr [rbx+7]
0x18001cf26  shl     ecx, 10h
0x18001cf29  shl     edx, 10h
0x18001cf2c  or      edx, eax
0x18001cf2e  movzx   eax, byte ptr [rbx+6]
0x18001cf32  or      ecx, eax
0x18001cf34  shl     ecx, 8
0x18001cf37  or      ecx, edx
0x18001cf39  mov     [rdi+0Ch], ecx
0x18001cf3c  movzx   eax, byte ptr [r10+rbx+6]
0x18001cf42  movzx   ecx, byte ptr [r10+rbx+7]
0x18001cf48  shl     ecx, 10h
0x18001cf4b  or      ecx, eax
0x18001cf4d  shl     ecx, 8
0x18001cf50  or      ecx, edx
0x18001cf52  mov     [r11+rdi+0Ch], ecx
0x18001cf57  movzx   eax, byte ptr [rsi+4]
0x18001cf5b  movzx   edx, byte ptr [r9+4]
0x18001cf60  movzx   ecx, byte ptr [rbx+9]
0x18001cf64  shl     edx, 10h
0x18001cf67  or      edx, eax
0x18001cf69  shl     ecx, 10h
0x18001cf6c  movzx   eax, byte ptr [rbx+8]
0x18001cf70  or      ecx, eax
0x18001cf72  shl     ecx, 8
0x18001cf75  or      ecx, edx
0x18001cf77  mov     [rdi+10h], ecx
0x18001cf7a  movzx   eax, byte ptr [r10+rbx+8]
0x18001cf80  movzx   ecx, byte ptr [r10+rbx+9]
0x18001cf86  shl     ecx, 10h
0x18001cf89  or      ecx, eax
0x18001cf8b  shl     ecx, 8
0x18001cf8e  or      ecx, edx
0x18001cf90  mov     [r11+rdi+10h], ecx
0x18001cf95  movzx   eax, byte ptr [rsi+5]
0x18001cf99  movzx   edx, byte ptr [r9+5]
0x18001cf9e  movzx   ecx, byte ptr [rbx+0Bh]
0x18001cfa2  shl     ecx, 10h
0x18001cfa5  shl     edx, 10h
0x18001cfa8  or      edx, eax
0x18001cfaa  movzx   eax, byte ptr [rbx+0Ah]
0x18001cfae  or      ecx, eax
0x18001cfb0  shl     ecx, 8
0x18001cfb3  or      ecx, edx
0x18001cfb5  mov     [rdi+14h], ecx
0x18001cfb8  movzx   eax, byte ptr [r10+rbx+0Ah]
0x18001cfbe  movzx   ecx, byte ptr [r10+rbx+0Bh]
0x18001cfc4  shl     ecx, 10h
0x18001cfc7  or      ecx, eax
0x18001cfc9  shl     ecx, 8
0x18001cfcc  or      ecx, edx
0x18001cfce  mov     [r11+rdi+14h], ecx
0x18001cfd3  movzx   eax, byte ptr [rsi+6]
0x18001cfd7  movzx   edx, byte ptr [r9+6]
0x18001cfdc  movzx   ecx, byte ptr [rbx+0Dh]
0x18001cfe0  shl     ecx, 10h
0x18001cfe3  shl     edx, 10h
0x18001cfe6  or      edx, eax
0x18001cfe8  movzx   eax, byte ptr [rbx+0Ch]
0x18001cfec  or      ecx, eax
0x18001cfee  shl     ecx, 8
0x18001cff1  or      ecx, edx
0x18001cff3  mov     [rdi+18h], ecx
0x18001cff6  movzx   eax, byte ptr [r10+rbx+0Ch]
0x18001cffc  movzx   ecx, byte ptr [r10+rbx+0Dh]
0x18001d002  shl     ecx, 10h
0x18001d005  or      ecx, eax
0x18001d007  shl     ecx, 8
0x18001d00a  or      ecx, edx
0x18001d00c  mov     [r11+rdi+18h], ecx
0x18001d011  movzx   eax, byte ptr [rsi+7]
0x18001d015  add     rsi, rbp
0x18001d018  movzx   edx, byte ptr [r9+7]
0x18001d01d  add     r9, rbp
0x18001d020  movzx   ecx, byte ptr [rbx+0Fh]
0x18001d024  shl     ecx, 10h
0x18001d027  shl     edx, 10h
0x18001d02a  or      edx, eax
0x18001d02c  movzx   eax, byte ptr [rbx+0Eh]
0x18001d030  or      ecx, eax
0x18001d032  shl     ecx, 8
0x18001d035  or      ecx, edx
0x18001d037  mov     [rdi+1Ch], ecx
0x18001d03a  movzx   ecx, byte ptr [r10+rbx+0Fh]
0x18001d040  movzx   eax, byte ptr [r10+rbx+0Eh]
0x18001d046  add     rbx, r12
0x18001d049  shl     ecx, 10h
0x18001d04c  or      ecx, eax
0x18001d04e  shl     ecx, 8
0x18001d051  or      ecx, edx
0x18001d053  mov     [r11+rdi+1Ch], ecx
0x18001d058  add     rdi, r15
0x18001d05b  sub     r14d, 1
0x18001d05f  jnz     loc_18001CE61
0x18001d065  pop     r15
0x18001d067  pop     r14
0x18001d069  pop     r12
0x18001d06b  pop     rdi
0x18001d06c  pop     rsi
0x18001d06d  pop     rbp
0x18001d06e  pop     rbx
0x18001d06f  retn
```
