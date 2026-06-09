# sqlite3VdbeMakeReady

- ea: `0x180034e60`
- end: `0x1800351bf`
- name: `sqlite3VdbeMakeReady`
- size: `863`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180034704`
- `0x18008c9b0`

## callees

- `0x180010390`
- `0x180034e60`
- `0x180056880`
- `0x18006910e`

## pseudocode

```c
char *__fastcall sqlite3VdbeMakeReady(__int64 *a1, __int64 a2)
{
  __int64 v4; // r12
  int v5; // esi
  int v6; // esi
  __int64 v7; // rax
  __int16 v8; // cx
  int v9; // edx
  __int64 v10; // rbp
  signed __int64 v11; // r14
  int v12; // eax
  char v13; // cl
  unsigned int v14; // edx
  __int64 v15; // r15
  __int64 v16; // rax
  __int16 v17; // r8
  signed __int64 v18; // rcx
  __int64 v19; // rdi
  __int64 v20; // r13
  __int64 v21; // rax
  __int64 v22; // r14
  char *result; // rax
  signed __int64 v24; // rdx
  signed __int64 v25; // r12
  signed __int64 v26; // rbp
  __int64 v27; // rbp
  __int64 v28; // rax
  int v29; // ecx
  __int64 v30; // rcx
  char *v31; // rcx
  char *v32; // rax
  char *v33; // rax
  char *v34; // rax
  __int16 v35; // [rsp+70h] [rbp+8h]
  int v36; // [rsp+78h] [rbp+10h] BYREF
  int v37; // [rsp+80h] [rbp+18h]
  __int64 v38; // [rsp+88h] [rbp+20h]

  a1[22] = *(_QWORD *)(a2 + 328);
  v4 = *(int *)(a2 + 56);
  v5 = *(_DWORD *)(a2 + 60);
  *(_QWORD *)(a2 + 328) = 0;
  v6 = v4 + v5;
  v7 = *a1;
  v8 = *(_WORD *)(a2 + 304);
  v38 = v7;
  v36 = *(_DWORD *)(a2 + 144);
  v35 = v8;
  v37 = v4;
  if ( !(_DWORD)v4 && v6 > 0 )
    ++v6;
  v9 = 24 * *((_DWORD *)a1 + 36);
  v10 = v9 + a1[17];
  v11 = (*(_DWORD *)(a2 + 64) - v9) & 0xFFFFFFFFFFFFFFF8uLL;
  resolveP2Values(a1, &v36);
  if ( !*(_BYTE *)(a2 + 32) || (v12 = 32, !*(_BYTE *)(a2 + 33)) )
    v12 = 0;
  *((_DWORD *)a1 + 50) &= ~0x20u;
  *((_DWORD *)a1 + 50) |= v12;
  v13 = *(_BYTE *)(a2 + 307);
  if ( v13 )
  {
    if ( v6 < 10 )
      v6 = 10;
    v14 = *((_DWORD *)a1 + 50) ^ ((unsigned __int8)*((_DWORD *)a1 + 50) ^ (unsigned __int8)(4 * v13)) & 0xC;
    *((_WORD *)a1 + 96) = 4 * (3 - ((v14 >> 2) & 3));
  }
  else
  {
    v14 = *((_DWORD *)a1 + 50);
  }
  v15 = 56LL * v6;
  *((_DWORD *)a1 + 50) = v14 & 0xFFFFFFFC;
  if ( v15 <= v11 )
    v16 = v10 + v11 - v15;
  else
    v16 = 0;
  v17 = v35;
  v18 = v11 - v15;
  a1[13] = v16;
  v19 = 0;
  if ( v15 > v11 )
  {
    v18 = v11;
    v19 = 56LL * v6;
  }
  v20 = 56LL * v35;
  if ( v20 <= v18 )
  {
    v18 -= v20;
    v21 = v18 + v10;
  }
  else
  {
    v21 = 0;
    v19 += v20;
  }
  v22 = 8LL * v36;
  a1[16] = v21;
  if ( v22 <= v18 )
  {
    result = (char *)(v18 + v10 - v22);
  }
  else
  {
    result = 0;
    v19 += v22;
  }
  a1[14] = (__int64)result;
  v24 = v18 - v22;
  if ( v22 > v18 )
    v24 = v18;
  v25 = 8 * v4;
  if ( v25 <= v24 )
  {
    v26 = v24 + v10 - v25;
  }
  else
  {
    v26 = 0;
    v19 += v25;
  }
  a1[15] = v26;
  v27 = v38;
  if ( v19 )
  {
    result = (char *)sqlite3DbMallocRawNN(v38, v19);
    a1[32] = (__int64)result;
    v31 = result;
    if ( !*(_BYTE *)(v27 + 103) )
    {
      v32 = (char *)a1[13];
      if ( !v32 && v15 <= v19 )
      {
        v19 -= v15;
        v32 = &v31[v19];
      }
      a1[13] = (__int64)v32;
      v33 = (char *)a1[16];
      if ( !v33 && v20 <= v19 )
      {
        v19 -= v20;
        v33 = &v31[v19];
      }
      a1[16] = (__int64)v33;
      v34 = (char *)a1[14];
      if ( !v34 && v22 <= v19 )
      {
        v19 -= v22;
        v34 = &v31[v19];
      }
      a1[14] = (__int64)v34;
      result = (char *)a1[15];
      if ( !result && v25 <= v19 )
        result = &v31[v19 - v25];
      a1[15] = (__int64)result;
    }
    v17 = v35;
  }
  if ( *(_BYTE *)(v27 + 103) )
  {
    *((_WORD *)a1 + 16) = 0;
    *(__int64 *)((char *)a1 + 36) = 0;
  }
  else
  {
    *((_DWORD *)a1 + 10) = v37;
    v28 = a1[16];
    *((_WORD *)a1 + 16) = v17;
    v29 = v17;
    while ( v29 > 0 )
    {
      *(_WORD *)(v28 + 20) = 1;
      --v29;
      *(_QWORD *)(v28 + 24) = v27;
      *(_DWORD *)(v28 + 32) = 0;
      v28 += 56;
    }
    v30 = a1[13];
    *((_DWORD *)a1 + 9) = v6;
    while ( v6 > 0 )
    {
      *(_WORD *)(v30 + 20) = 0;
      --v6;
      *(_QWORD *)(v30 + 24) = v27;
      *(_DWORD *)(v30 + 32) = 0;
      v30 += 56;
    }
    result = (char *)memset_0((void *)a1[15], 0, v25);
  }
  *((_BYTE *)a1 + 199) = 1;
  *((_DWORD *)a1 + 12) = -1;
  *((_DWORD *)a1 + 13) = 0;
  *((_WORD *)a1 + 98) = -254;
  a1[7] = 0;
  *((_DWORD *)a1 + 11) = 1;
  *((_DWORD *)a1 + 16) = 0;
  a1[10] = 0;
  return result;
}

```

## disassembly

```asm
0x180034e60  push    rbx
0x180034e62  push    rbp
0x180034e63  push    rsi
0x180034e64  push    rdi
0x180034e65  push    r12
0x180034e67  push    r13
0x180034e69  push    r14
0x180034e6b  push    r15
0x180034e6d  sub     rsp, 28h
0x180034e71  mov     rax, [rdx+148h]
0x180034e78  mov     rbx, rcx
0x180034e7b  mov     [rcx+0B0h], rax
0x180034e82  mov     rdi, rdx
0x180034e85  movsxd  r12, dword ptr [rdx+38h]
0x180034e89  mov     esi, [rdx+3Ch]
0x180034e8c  mov     qword ptr [rdx+148h], 0
0x180034e97  add     esi, r12d
0x180034e9a  mov     rax, [rcx]
0x180034e9d  movzx   ecx, word ptr [rdx+130h]
0x180034ea4  mov     [rsp+68h+arg_18], rax
0x180034eac  mov     eax, [rdx+90h]
0x180034eb2  mov     [rsp+68h+arg_8], eax
0x180034eb6  mov     [rsp+68h+arg_0], cx
0x180034ebb  mov     [rsp+68h+arg_10], r12d
0x180034ec3  test    r12d, r12d
0x180034ec6  jz      loc_180035154
0x180034ecc  mov     eax, [rbx+90h]
0x180034ed2  mov     rbp, [rbx+88h]
0x180034ed9  lea     edx, [rax+rax*2]
0x180034edc  mov     eax, [rdi+40h]
0x180034edf  shl     edx, 3
0x180034ee2  movsxd  rcx, edx
0x180034ee5  sub     eax, edx
0x180034ee7  add     rbp, rcx
0x180034eea  movsxd  r14, eax
0x180034eed  mov     rcx, rbx
0x180034ef0  lea     rdx, [rsp+68h+arg_8]
0x180034ef5  and     r14, 0FFFFFFFFFFFFFFF8h
0x180034ef9  call    resolveP2Values
0x180034efe  xor     r9d, r9d
0x180034f01  cmp     [rdi+20h], r9b
0x180034f05  jnz     loc_180035163
0x180034f0b  mov     eax, r9d
0x180034f0e  and     dword ptr [rbx+0C8h], 0FFFFFFDFh
0x180034f15  or      [rbx+0C8h], eax
0x180034f1b  movzx   ecx, byte ptr [rdi+133h]
0x180034f22  mov     eax, [rbx+0C8h]
0x180034f28  test    cl, cl
0x180034f2a  jnz     loc_180035177
0x180034f30  mov     edx, eax
0x180034f32  and     edx, 0FFFFFFFCh
0x180034f35  movsxd  rax, esi
0x180034f38  imul    r15, rax, 38h ; '8'
0x180034f3c  mov     [rbx+0C8h], edx
0x180034f42  cmp     r15, r14
0x180034f45  jle     loc_180035084
0x180034f4b  mov     rax, r9
0x180034f4e  movsx   r8, [rsp+68h+arg_0]
0x180034f54  mov     rcx, r14
0x180034f57  sub     rcx, r15
0x180034f5a  mov     [rbx+68h], rax
0x180034f5e  cmp     r15, r14
0x180034f61  mov     rdi, r9
0x180034f64  cmovg   rcx, r14
0x180034f68  cmovg   rdi, r15
0x180034f6c  imul    r13, r8, 38h ; '8'
0x180034f70  cmp     r13, rcx
0x180034f73  jle     loc_180035092
0x180034f79  mov     rax, r9
0x180034f7c  add     rdi, r13
0x180034f7f  movsxd  r14, [rsp+68h+arg_8]
0x180034f84  shl     r14, 3
0x180034f88  mov     [rbx+80h], rax
0x180034f8f  cmp     r14, rcx
0x180034f92  jle     loc_18003509E
0x180034f98  mov     rax, r9
0x180034f9b  add     rdi, r14
0x180034f9e  mov     rdx, rcx
0x180034fa1  mov     [rbx+70h], rax
0x180034fa5  sub     rdx, r14
0x180034fa8  cmp     r14, rcx
0x180034fab  cmovg   rdx, rcx
0x180034faf  shl     r12, 3
0x180034fb3  cmp     r12, rdx
0x180034fb6  jle     loc_1800350AC
0x180034fbc  mov     rbp, r9
0x180034fbf  add     rdi, r12
0x180034fc2  mov     [rbx+78h], rbp
0x180034fc6  mov     rbp, [rsp+68h+arg_18]
0x180034fce  test    rdi, rdi
0x180034fd1  jnz     loc_1800350B7
0x180034fd7  mov     edi, 1
0x180034fdc  cmp     [rbp+67h], r9b
0x180034fe0  jnz     loc_1800351AD
0x180034fe6  mov     eax, [rsp+68h+arg_10]
0x180034fed  mov     [rbx+28h], eax
0x180034ff0  mov     rax, [rbx+80h]
0x180034ff7  mov     [rbx+20h], r8w
0x180034ffc  movsx   ecx, r8w
0x180035000  jmp     short loc_180035014
0x180035002  mov     [rax+14h], di
0x180035006  sub     ecx, edi
0x180035008  mov     [rax+18h], rbp
0x18003500c  mov     [rax+20h], r9d
0x180035010  lea     rax, [rax+38h]
0x180035014  test    ecx, ecx
0x180035016  jg      short loc_180035002
0x180035018  mov     rcx, [rbx+68h]
0x18003501c  mov     [rbx+24h], esi
0x18003501f  jmp     short loc_180035034
0x180035021  mov     [rcx+14h], r9w
0x180035026  sub     esi, edi
0x180035028  mov     [rcx+18h], rbp
0x18003502c  mov     [rcx+20h], r9d
0x180035030  lea     rcx, [rcx+38h]
0x180035034  test    esi, esi
0x180035036  jg      short loc_180035021
0x180035038  mov     rcx, [rbx+78h]; void *
0x18003503c  mov     r8, r12; Size
0x18003503f  xor     edx, edx; Val
0x180035041  call    memset_0
0x180035046  xor     r9d, r9d
0x180035049  mov     [rbx+0C7h], dil
0x180035050  mov     dword ptr [rbx+30h], 0FFFFFFFFh
0x180035057  mov     [rbx+34h], r9d
0x18003505b  mov     word ptr [rbx+0C4h], 0FF02h
0x180035064  mov     [rbx+38h], r9
0x180035068  mov     [rbx+2Ch], edi
0x18003506b  mov     [rbx+40h], r9d
0x18003506f  mov     [rbx+50h], r9
0x180035073  add     rsp, 28h
0x180035077  pop     r15
0x180035079  pop     r14
0x18003507b  pop     r13
0x18003507d  pop     r12
0x18003507f  pop     rdi
0x180035080  pop     rsi
0x180035081  pop     rbp
0x180035082  pop     rbx
0x180035083  retn
0x180035084  mov     rax, r14
0x180035087  sub     rax, r15
0x18003508a  add     rax, rbp
0x18003508d  jmp     loc_180034F4E
0x180035092  sub     rcx, r13
0x180035095  lea     rax, [rcx+rbp]
0x180035099  jmp     loc_180034F7F
0x18003509e  mov     rax, rbp
0x1800350a1  sub     rax, r14
0x1800350a4  add     rax, rcx
0x1800350a7  jmp     loc_180034F9E
0x1800350ac  sub     rbp, r12
0x1800350af  add     rbp, rdx
0x1800350b2  jmp     loc_180034FC2
0x1800350b7  mov     rdx, rdi
0x1800350ba  mov     rcx, rbp
0x1800350bd  call    sqlite3DbMallocRawNN
0x1800350c2  xor     r9d, r9d
0x1800350c5  mov     [rbx+100h], rax
0x1800350cc  mov     rcx, rax
0x1800350cf  cmp     [rbp+67h], r9b
0x1800350d3  jnz     short loc_180035123
0x1800350d5  mov     rax, [rbx+68h]
0x1800350d9  test    rax, rax
0x1800350dc  jnz     short loc_1800350E3
0x1800350de  cmp     r15, rdi
0x1800350e1  jle     short loc_18003512E
0x1800350e3  mov     [rbx+68h], rax
0x1800350e7  mov     rax, [rbx+80h]
0x1800350ee  test    rax, rax
0x1800350f1  jnz     short loc_1800350F8
0x1800350f3  cmp     r13, rdi
0x1800350f6  jle     short loc_180035137
0x1800350f8  mov     [rbx+80h], rax
0x1800350ff  mov     rax, [rbx+70h]
0x180035103  test    rax, rax
0x180035106  jnz     short loc_18003510D
0x180035108  cmp     r14, rdi
0x18003510b  jle     short loc_180035140
0x18003510d  mov     [rbx+70h], rax
0x180035111  mov     rax, [rbx+78h]
0x180035115  test    rax, rax
0x180035118  jnz     short loc_18003511F
0x18003511a  cmp     r12, rdi
0x18003511d  jle     short loc_180035149
0x18003511f  mov     [rbx+78h], rax
0x180035123  movzx   r8d, [rsp+68h+arg_0]
0x180035129  jmp     loc_180034FD7
0x18003512e  sub     rdi, r15
0x180035131  lea     rax, [rdi+rcx]
0x180035135  jmp     short loc_1800350E3
0x180035137  sub     rdi, r13
0x18003513a  lea     rax, [rdi+rcx]
0x18003513e  jmp     short loc_1800350F8
0x180035140  sub     rdi, r14
0x180035143  lea     rax, [rdi+rcx]
0x180035147  jmp     short loc_18003510D
0x180035149  mov     rax, rdi
0x18003514c  sub     rax, r12
0x18003514f  add     rax, rcx
0x180035152  jmp     short loc_18003511F
0x180035154  test    esi, esi
0x180035156  jle     loc_180034ECC
0x18003515c  inc     esi
0x18003515e  jmp     loc_180034ECC
0x180035163  mov     eax, 20h ; ' '
0x180035168  cmp     [rdi+21h], r9b
0x18003516c  jnz     loc_180034F0E
0x180035172  jmp     loc_180034F0B
0x180035177  mov     edx, 0Ah
0x18003517c  cmp     esi, edx
0x18003517e  cmovl   esi, edx
0x180035181  mov     edx, ecx
0x180035183  shl     edx, 2
0x180035186  mov     ecx, 3
0x18003518b  xor     edx, eax
0x18003518d  and     edx, 0Ch
0x180035190  xor     edx, eax
0x180035192  mov     eax, edx
0x180035194  shr     eax, 2
0x180035197  and     ax, cx
0x18003519a  sub     cx, ax
0x18003519d  shl     cx, 2
0x1800351a1  mov     [rbx+0C0h], cx
0x1800351a8  jmp     loc_180034F32
0x1800351ad  mov     [rbx+20h], r9w
0x1800351b2  mov     qword ptr [rbx+24h], 0
0x1800351ba  jmp     loc_180035049
```
