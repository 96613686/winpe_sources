# ec_enc_uint

- ea: `0x1800157e0`
- end: `0x18001597b`
- name: `ec_enc_uint`
- size: `411`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x18000bf50`
- `0x18000d040`
- `0x180015e30`

## callees

- `0x180008950`
- `0x1800156e0`
- `0x1800157e0`

## pseudocode

```c
__int64 __fastcall ec_enc_uint(__int64 a1, unsigned int a2, unsigned int a3)
{
  unsigned int v5; // r9d
  unsigned int v6; // eax
  __int64 v7; // rdx
  int v8; // eax
  int v9; // r14d
  char v10; // cl
  unsigned int v11; // r11d
  int v12; // eax
  unsigned int v13; // r11d
  int v14; // r10d
  unsigned int v15; // esi
  int v16; // edi
  int v17; // r8d
  unsigned int v18; // edx
  int v19; // eax
  __int64 result; // rax
  int v21; // eax
  unsigned int v22; // edi
  int v23; // r8d

  if ( a3 <= 1 )
    celt_fatal(
      "assertion failed: _ft>1",
      "D:\\os\\obj\\amd64fre\\avcore\\codecdsp\\audio\\opus\\opusliboss\\vcpkg\\objfre\\amd64\\vcpkg_buildtrees\\opus\\sr"
      "c\\v1.5.2-0503455b1e.clean\\celt\\entenc.c",
      191);
  v5 = *(_DWORD *)(a1 + 32);
  _BitScanReverse(&v6, a3 - 1);
  HIDWORD(v7) = 0;
  v8 = v6 + 1;
  if ( v8 <= 8 )
  {
    LODWORD(v7) = v5 % a3;
    v21 = v5 / a3;
    v22 = a3 - a2;
    v23 = v5 / a3;
    if ( a2 )
      *(_DWORD *)(a1 + 36) += v5 - v22 * v21;
    else
      v23 = v5 - v21 * (v22 - 1);
    *(_DWORD *)(a1 + 32) = v23;
    return ec_enc_normalize(a1, v7);
  }
  else
  {
    v9 = v8 - 8;
    v10 = v8 - 8;
    v11 = ((a3 - 1) >> (v8 - 8)) + 1;
    LODWORD(v7) = v5 % v11;
    v12 = v5 / v11;
    v13 = v11 - (a2 >> v10);
    v14 = v12;
    if ( a2 >> v10 )
      *(_DWORD *)(a1 + 36) += v5 - v13 * v12;
    else
      v14 = v5 - v12 * (v13 - 1);
    *(_DWORD *)(a1 + 32) = v14;
    ec_enc_normalize(a1, v7);
    v15 = *(_DWORD *)(a1 + 16);
    v16 = *(_DWORD *)(a1 + 20);
    if ( !v9 )
      celt_fatal(
        "assertion failed: _bits>0",
        "D:\\os\\obj\\amd64fre\\avcore\\codecdsp\\audio\\opus\\opusliboss\\vcpkg\\objfre\\amd64\\vcpkg_buildtrees\\opus\\"
        "src\\v1.5.2-0503455b1e.clean\\celt\\entenc.c",
        209);
    if ( (unsigned int)(v9 + v16) > 0x20 )
    {
      do
      {
        v17 = *(_DWORD *)(a1 + 12);
        v18 = *(_DWORD *)(a1 + 8);
        if ( v17 + *(_DWORD *)(a1 + 28) < v18 )
        {
          *(_DWORD *)(a1 + 12) = v17 + 1;
          *(_BYTE *)(v18 - v17 - 1 + *(_QWORD *)a1) = v15;
          v19 = 0;
        }
        else
        {
          v19 = -1;
        }
        *(_DWORD *)(a1 + 48) |= v19;
        v16 -= 8;
        v15 >>= 8;
      }
      while ( v16 >= 8 );
    }
    *(_DWORD *)(a1 + 24) += v9;
    *(_DWORD *)(a1 + 16) = v15 | ((a2 & ((1 << v9) - 1)) << v16);
    result = (unsigned int)(v16 + v9);
    *(_DWORD *)(a1 + 20) = result;
  }
  return result;
}

```

## disassembly

```asm
0x1800157e0  mov     [rsp+arg_10], rbx
0x1800157e5  mov     [rsp+arg_18], rbp
0x1800157ea  push    rdi
0x1800157eb  sub     rsp, 20h
0x1800157ef  mov     edi, r8d
0x1800157f2  mov     ebp, edx
0x1800157f4  mov     rbx, rcx
0x1800157f7  cmp     r8d, 1
0x1800157fb  ja      short loc_180015816
0x1800157fd  mov     r8d, 0BFh
0x180015803  lea     rdx, aDOsObjAmd64fre_18; "D:\\os\\obj\\amd64fre\\avcore\\codecdsp"...
0x18001580a  lea     rcx, aAssertionFaile_25; "assertion failed: _ft>1"
0x180015811  call    celt_fatal
0x180015816  mov     r9d, [rbx+20h]
0x18001581a  lea     r8d, [rdi-1]
0x18001581e  bsr     eax, r8d
0x180015822  xor     edx, edx
0x180015824  inc     eax
0x180015826  cmp     eax, 8
0x180015829  jle     loc_180015937
0x18001582f  mov     [rsp+28h+arg_0], rsi
0x180015834  mov     [rsp+28h+arg_8], r14
0x180015839  lea     r14d, [rax-8]
0x18001583d  mov     ecx, r14d
0x180015840  mov     eax, r9d
0x180015843  shr     r8d, cl
0x180015846  lea     r11d, [r8+1]
0x18001584a  mov     r8d, ebp
0x18001584d  div     r11d
0x180015850  shr     r8d, cl
0x180015853  sub     r11d, r8d
0x180015856  mov     r10d, eax
0x180015859  test    r8d, r8d
0x18001585c  jz      short loc_18001586D
0x18001585e  mov     ecx, eax
0x180015860  imul    ecx, r11d
0x180015864  sub     r9d, ecx
0x180015867  add     [rbx+24h], r9d
0x18001586b  jmp     short loc_18001587B
0x18001586d  lea     eax, [r11-1]
0x180015871  imul    eax, r10d
0x180015875  mov     r10d, r9d
0x180015878  sub     r10d, eax
0x18001587b  mov     rcx, rbx
0x18001587e  mov     [rbx+20h], r10d
0x180015882  call    ec_enc_normalize
0x180015887  mov     esi, [rbx+10h]
0x18001588a  mov     edi, [rbx+14h]
0x18001588d  test    r14d, r14d
0x180015890  jnz     short loc_1800158AB
0x180015892  mov     r8d, 0D1h
0x180015898  lea     rdx, aDOsObjAmd64fre_18; "D:\\os\\obj\\amd64fre\\avcore\\codecdsp"...
0x18001589f  lea     rcx, aAssertionFaile_21; "assertion failed: _bits>0"
0x1800158a6  call    celt_fatal
0x1800158ab  lea     eax, [r14+rdi]
0x1800158af  cmp     eax, 20h ; ' '
0x1800158b2  jbe     short loc_1800158FB
0x1800158b4  nop     dword ptr [rax+00h]
0x1800158b8  nop     dword ptr [rax+rax+00000000h]
0x1800158c0  mov     ecx, [rbx+1Ch]
0x1800158c3  mov     r8d, [rbx+0Ch]
0x1800158c7  add     ecx, r8d
0x1800158ca  mov     edx, [rbx+8]
0x1800158cd  cmp     ecx, edx
0x1800158cf  jb      short loc_1800158D8
0x1800158d1  mov     eax, 0FFFFFFFFh
0x1800158d6  jmp     short loc_1800158ED
0x1800158d8  sub     edx, r8d
0x1800158db  lea     eax, [r8+1]
0x1800158df  mov     [rbx+0Ch], eax
0x1800158e2  dec     edx
0x1800158e4  mov     rax, [rbx]
0x1800158e7  mov     [rdx+rax], sil
0x1800158eb  xor     eax, eax
0x1800158ed  or      [rbx+30h], eax
0x1800158f0  sub     edi, 8
0x1800158f3  shr     esi, 8
0x1800158f6  cmp     edi, 8
0x1800158f9  jge     short loc_1800158C0
0x1800158fb  mov     ecx, r14d
0x1800158fe  mov     eax, 1
0x180015903  shl     eax, cl
0x180015905  mov     ecx, edi
0x180015907  dec     eax
0x180015909  and     eax, ebp
0x18001590b  shl     eax, cl
0x18001590d  or      eax, esi
0x18001590f  mov     rsi, [rsp+28h+arg_0]
0x180015914  add     [rbx+18h], r14d
0x180015918  mov     [rbx+10h], eax
0x18001591b  lea     eax, [rdi+r14]
0x18001591f  mov     r14, [rsp+28h+arg_8]
0x180015924  mov     [rbx+14h], eax
0x180015927  mov     rbx, [rsp+28h+arg_10]
0x18001592c  mov     rbp, [rsp+28h+arg_18]
0x180015931  add     rsp, 20h
0x180015935  pop     rdi
0x180015936  retn
0x180015937  mov     eax, r9d
0x18001593a  div     edi
0x18001593c  sub     edi, ebp
0x18001593e  mov     r8d, eax
0x180015941  test    ebp, ebp
0x180015943  jz      short loc_180015953
0x180015945  mov     ecx, eax
0x180015947  imul    ecx, edi
0x18001594a  sub     r9d, ecx
0x18001594d  add     [rbx+24h], r9d
0x180015951  jmp     short loc_180015960
0x180015953  lea     eax, [rdi-1]
0x180015956  imul    eax, r8d
0x18001595a  mov     r8d, r9d
0x18001595d  sub     r8d, eax
0x180015960  mov     rcx, rbx
0x180015963  mov     [rbx+20h], r8d
0x180015967  mov     rbx, [rsp+28h+arg_10]
0x18001596c  mov     rbp, [rsp+28h+arg_18]
0x180015971  add     rsp, 20h
0x180015975  pop     rdi
0x180015976  jmp     ec_enc_normalize
```
