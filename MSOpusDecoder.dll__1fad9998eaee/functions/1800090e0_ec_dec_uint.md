# ec_dec_uint

- ea: `0x1800090e0`
- end: `0x18000927e`
- name: `ec_dec_uint`
- size: `414`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x1800022f0`
- `0x180005aa0`
- `0x18000bf50`
- `0x18000d040`
- `0x180015da0`

## callees

- `0x180008950`
- `0x180009040`
- `0x1800090e0`

## pseudocode

```c
__int64 __fastcall ec_dec_uint(__int64 a1, unsigned int a2)
{
  unsigned int v3; // ebp
  unsigned int v4; // r14d
  unsigned int v5; // r11d
  unsigned int v6; // eax
  int v7; // esi
  int v8; // eax
  unsigned int v9; // edi
  unsigned int v10; // r9d
  int v11; // r10d
  unsigned int v12; // r8d
  unsigned int v13; // ecx
  unsigned int v14; // eax
  unsigned int v15; // ecx
  int v16; // r9d
  unsigned int v17; // r15d
  int v18; // ebp
  int v19; // r8d
  unsigned int v20; // r9d
  unsigned int v21; // r10d
  unsigned int v22; // ecx
  int v23; // edx
  char v24; // cl
  __int64 result; // rax
  int v26; // r8d
  unsigned int v27; // eax
  int v28; // edi
  int v29; // ebp
  unsigned int v30; // edx

  if ( a2 <= 1 )
    celt_fatal(
      "assertion failed: _ft>1",
      "D:\\os\\obj\\amd64fre\\avcore\\codecdsp\\audio\\opus\\opusliboss\\vcpkg\\objfre\\amd64\\vcpkg_buildtrees\\opus\\sr"
      "c\\v1.5.2-0503455b1e.clean\\celt\\entdec.c",
      224);
  v3 = *(_DWORD *)(a1 + 32);
  v4 = a2 - 1;
  v5 = *(_DWORD *)(a1 + 36);
  _BitScanReverse(&v6, a2 - 1);
  v7 = 0;
  v8 = v6 + 1;
  if ( v8 <= 8 )
  {
    v26 = v3 / a2;
    *(_DWORD *)(a1 + 40) = v3 / a2;
    v27 = v5 / (v3 / a2);
    if ( a2 < v27 + 1 )
      v7 = a2 - v27 - 1;
    v28 = v26 * (v27 + v7);
    v29 = v3 - v28;
    *(_DWORD *)(a1 + 36) = v5 - v28;
    if ( a2 - v7 - v27 == 1 )
      v26 = v29;
    *(_DWORD *)(a1 + 32) = v26;
    ec_dec_normalize(a1);
    return v30;
  }
  else
  {
    v9 = v8 - 8;
    v10 = (v4 >> (v8 - 8)) + 1;
    v11 = v3 / v10;
    *(_DWORD *)(a1 + 40) = v3 / v10;
    v12 = v5 / (v3 / v10);
    v13 = (v4 >> (v8 - 8)) - v12;
    v14 = 0;
    if ( v10 < v12 + 1 )
      v14 = v13;
    v15 = v10 - v14 - v12;
    v16 = v11 * (v12 + v14);
    v17 = v15 - 1;
    v18 = v3 - v16;
    *(_DWORD *)(a1 + 36) = v5 - v16;
    if ( v15 == 1 )
      v11 = v18;
    *(_DWORD *)(a1 + 32) = v11;
    ec_dec_normalize(a1);
    v19 = *(_DWORD *)(a1 + 20);
    v20 = *(_DWORD *)(a1 + 16);
    if ( v19 < v9 )
    {
      v21 = *(_DWORD *)(a1 + 8);
      do
      {
        v22 = *(_DWORD *)(a1 + 12);
        if ( v22 >= v21 )
        {
          v23 = 0;
        }
        else
        {
          *(_DWORD *)(a1 + 12) = v22 + 1;
          v23 = *(unsigned __int8 *)(v21 - v22 - 1 + *(_QWORD *)a1);
        }
        v24 = v19;
        v19 += 8;
        v20 |= v23 << v24;
      }
      while ( v19 <= 24 );
    }
    *(_DWORD *)(a1 + 24) += v9;
    *(_DWORD *)(a1 + 20) = v19 - v9;
    *(_DWORD *)(a1 + 16) = v20 >> v9;
    result = (v17 << v9) | v20 & ((1 << v9) - 1);
    if ( (unsigned int)result > v4 )
    {
      *(_DWORD *)(a1 + 48) = 1;
      return v4;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800090e0  mov     [rsp+arg_10], rbx
0x1800090e5  push    rbp
0x1800090e6  push    rdi
0x1800090e7  push    r14
0x1800090e9  sub     rsp, 20h
0x1800090ed  mov     edi, edx
0x1800090ef  mov     rbx, rcx
0x1800090f2  cmp     edx, 1
0x1800090f5  ja      short loc_180009110
0x1800090f7  mov     r8d, 0E0h
0x1800090fd  lea     rdx, aDOsObjAmd64fre_20; "D:\\os\\obj\\amd64fre\\avcore\\codecdsp"...
0x180009104  lea     rcx, aAssertionFaile_25; "assertion failed: _ft>1"
0x18000910b  call    celt_fatal
0x180009110  mov     ebp, [rbx+20h]
0x180009113  lea     r14d, [rdi-1]
0x180009117  mov     r11d, [rbx+24h]
0x18000911b  xor     edx, edx
0x18000911d  bsr     eax, r14d
0x180009121  mov     [rsp+38h+arg_0], rsi
0x180009126  xor     esi, esi
0x180009128  inc     eax
0x18000912a  cmp     eax, 8
0x18000912d  jle     loc_18000921F
0x180009133  lea     edi, [rax-8]
0x180009136  mov     [rsp+38h+arg_8], r15
0x18000913b  mov     ecx, edi
0x18000913d  mov     eax, ebp
0x18000913f  mov     r9d, r14d
0x180009142  shr     r9d, cl
0x180009145  inc     r9d
0x180009148  div     r9d
0x18000914b  xor     edx, edx
0x18000914d  mov     ecx, r9d
0x180009150  mov     r10d, eax
0x180009153  mov     [rbx+28h], eax
0x180009156  mov     eax, r11d
0x180009159  div     r10d
0x18000915c  sub     ecx, eax
0x18000915e  mov     r8d, eax
0x180009161  dec     ecx
0x180009163  lea     edx, [rax+1]
0x180009166  mov     eax, esi
0x180009168  cmp     r9d, edx
0x18000916b  cmovb   eax, ecx
0x18000916e  mov     ecx, r9d
0x180009171  sub     ecx, eax
0x180009173  sub     ecx, r8d
0x180009176  sub     r9d, ecx
0x180009179  imul    r9d, r10d
0x18000917d  lea     r15d, [rcx-1]
0x180009181  mov     rcx, rbx
0x180009184  sub     r11d, r9d
0x180009187  sub     ebp, r9d
0x18000918a  test    r15d, r15d
0x18000918d  mov     [rbx+24h], r11d
0x180009191  cmovz   r10d, ebp
0x180009195  mov     [rbx+20h], r10d
0x180009199  call    ec_dec_normalize
0x18000919e  mov     r8d, [rbx+14h]
0x1800091a2  mov     r9d, [rbx+10h]
0x1800091a6  cmp     r8d, edi
0x1800091a9  jnb     short loc_1800091E3
0x1800091ab  mov     r10d, [rbx+8]
0x1800091af  nop
0x1800091b0  mov     ecx, [rbx+0Ch]
0x1800091b3  cmp     ecx, r10d
0x1800091b6  jnb     short loc_1800091CF
0x1800091b8  lea     eax, [rcx+1]
0x1800091bb  mov     [rbx+0Ch], eax
0x1800091be  mov     eax, r10d
0x1800091c1  sub     eax, ecx
0x1800091c3  lea     ecx, [rax-1]
0x1800091c6  mov     rax, [rbx]
0x1800091c9  movzx   edx, byte ptr [rcx+rax]
0x1800091cd  jmp     short loc_1800091D1
0x1800091cf  mov     edx, esi
0x1800091d1  mov     ecx, r8d
0x1800091d4  add     r8d, 8
0x1800091d8  shl     edx, cl
0x1800091da  or      r9d, edx
0x1800091dd  cmp     r8d, 18h
0x1800091e1  jle     short loc_1800091B0
0x1800091e3  add     [rbx+18h], edi
0x1800091e6  mov     ecx, edi
0x1800091e8  shl     r15d, cl
0x1800091eb  sub     r8d, edi
0x1800091ee  mov     eax, r9d
0x1800091f1  mov     [rbx+14h], r8d
0x1800091f5  shr     eax, cl
0x1800091f7  mov     [rbx+10h], eax
0x1800091fa  mov     eax, 1
0x1800091ff  shl     eax, cl
0x180009201  dec     eax
0x180009203  and     eax, r9d
0x180009206  or      eax, r15d
0x180009209  mov     r15, [rsp+38h+arg_8]
0x18000920e  cmp     eax, r14d
0x180009211  jbe     short loc_18000926B
0x180009213  mov     dword ptr [rbx+30h], 1
0x18000921a  mov     eax, r14d
0x18000921d  jmp     short loc_18000926B
0x18000921f  mov     eax, ebp
0x180009221  mov     ecx, edi
0x180009223  div     edi
0x180009225  xor     edx, edx
0x180009227  mov     r8d, eax
0x18000922a  mov     [rbx+28h], eax
0x18000922d  mov     eax, r11d
0x180009230  div     r8d
0x180009233  sub     ecx, eax
0x180009235  dec     ecx
0x180009237  lea     edx, [rax+1]
0x18000923a  cmp     edi, edx
0x18000923c  cmovb   esi, ecx
0x18000923f  mov     ecx, edi
0x180009241  sub     ecx, esi
0x180009243  sub     ecx, eax
0x180009245  sub     edi, ecx
0x180009247  imul    edi, r8d
0x18000924b  lea     edx, [rcx-1]
0x18000924e  mov     rcx, rbx
0x180009251  sub     r11d, edi
0x180009254  sub     ebp, edi
0x180009256  test    edx, edx
0x180009258  mov     [rbx+24h], r11d
0x18000925c  cmovz   r8d, ebp
0x180009260  mov     [rbx+20h], r8d
0x180009264  call    ec_dec_normalize
0x180009269  mov     eax, edx
0x18000926b  mov     rsi, [rsp+38h+arg_0]
0x180009270  mov     rbx, [rsp+38h+arg_10]
0x180009275  add     rsp, 20h
0x180009279  pop     r14
0x18000927b  pop     rdi
0x18000927c  pop     rbp
0x18000927d  retn
```
