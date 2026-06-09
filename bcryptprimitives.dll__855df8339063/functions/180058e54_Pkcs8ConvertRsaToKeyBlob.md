# Pkcs8ConvertRsaToKeyBlob

- ea: `0x180058e54`
- end: `0x18005911e`
- name: `Pkcs8ConvertRsaToKeyBlob`
- size: `714`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180067c40`

## callees

- `0x18000ecb0`
- `0x180058e54`
- `0x180063170`
- `0x18006ccf0`
- `0x18007f790`

## string_xrefs

- `0x1800590e1`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`

## pseudocode

```c
__int64 __fastcall Pkcs8ConvertRsaToKeyBlob(_DWORD *a1, unsigned int *a2, int *a3)
{
  int v5; // edx
  __int64 v6; // rcx
  int Values; // eax
  __int64 v8; // r9
  unsigned int v9; // ebx
  __int64 v10; // rcx
  _BYTE *v11; // rdx
  unsigned int i; // ecx
  _BYTE *v13; // rbx
  unsigned int v14; // r8d
  _BYTE *v15; // r14
  unsigned int v16; // r10d
  _BYTE *v17; // r15
  unsigned int v18; // r9d
  unsigned int v19; // r11d
  unsigned int v20; // eax
  unsigned int v21; // esi
  unsigned int v22; // r13d
  unsigned int v23; // ebx
  __int64 v24; // rcx
  int v26; // [rsp+30h] [rbp-D0h] BYREF
  char v27[16]; // [rsp+40h] [rbp-C0h] BYREF
  int v28; // [rsp+50h] [rbp-B0h]
  unsigned int v29; // [rsp+70h] [rbp-90h]
  void *Src; // [rsp+78h] [rbp-88h]
  size_t Size; // [rsp+80h] [rbp-80h]
  _BYTE *v32; // [rsp+88h] [rbp-78h]
  unsigned int v33; // [rsp+A0h] [rbp-60h]
  void *v34; // [rsp+A8h] [rbp-58h]
  unsigned int v35; // [rsp+B0h] [rbp-50h]
  void *v36; // [rsp+B8h] [rbp-48h]

  if ( !a3 || !a2 )
  {
    v9 = -1073741811;
    v8 = 147;
    v10 = 3221225485LL;
    goto LABEL_49;
  }
  v5 = *a3;
  v6 = *((_QWORD *)a3 + 1);
  v26 = 11;
  Values = MinAsn1ExtractValues(v6, v5, (unsigned int)&v26, (unsigned int)&qword_180087820, 12, (__int64)v27);
  if ( Values > 0 )
    Values = v28;
  if ( Values < 0 )
  {
    v8 = 154;
LABEL_7:
    v9 = -1073739509;
    v10 = 3221227787LL;
LABEL_49:
    DebugTraceError(v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\pkcsblob.c", v8);
    return v9;
  }
  v11 = v32;
  for ( i = Size; v11; ++v11 )
  {
    if ( i <= 1 )
      break;
    if ( *v11 )
      break;
    --i;
  }
  v13 = Src;
  v14 = v29;
  if ( Src )
  {
    do
    {
      if ( v14 <= 1 )
        break;
      if ( *v13 )
        break;
      --v14;
      ++v13;
    }
    while ( v13 );
  }
  v15 = v34;
  v16 = v33;
  if ( v34 )
  {
    do
    {
      if ( v16 <= 1 )
        break;
      if ( *v15 )
        break;
      --v16;
      ++v15;
    }
    while ( v15 );
  }
  v17 = v36;
  v18 = v35;
  if ( v36 )
  {
    do
    {
      if ( v18 <= 1 )
        break;
      if ( *v17 )
        break;
      --v18;
      ++v17;
    }
    while ( v17 );
  }
  if ( i > 0xFFFFFFF || v14 > 0xFFFFFFF || v16 > 0xFFFFFFF || v18 > 0xFFFFFFF )
  {
    v8 = 182;
    goto LABEL_7;
  }
  v19 = i + 24 + v14;
  if ( v19 < i + 24 )
  {
    v8 = 196;
    goto LABEL_41;
  }
  v20 = v19 + v16;
  if ( v19 + v16 < v19 )
  {
    v8 = 202;
    goto LABEL_41;
  }
  v21 = v20 + v18;
  if ( v20 + v18 < v20 )
  {
    v8 = 208;
    goto LABEL_41;
  }
  if ( a1 )
  {
    if ( *a2 < v21 )
    {
      *a2 = v21;
      v9 = -1073741789;
      v8 = 221;
      v10 = 3221225507LL;
      goto LABEL_49;
    }
    a1[3] = v14;
    a1[2] = i;
    *a1 = 843141970;
    a1[1] = 8 * v14;
    a1[4] = v16;
    a1[5] = v18;
    memcpy_0(a1 + 6, v11, i);
    v22 = a1[2] + 24;
    if ( a1[2] >= 0xFFFFFFE8 )
    {
      v8 = 240;
    }
    else
    {
      memcpy_0((char *)a1 + v22, v13, (unsigned int)a1[3]);
      v23 = v22 + a1[3];
      if ( v23 < v22 )
      {
        v8 = 250;
      }
      else
      {
        memcpy_0((char *)a1 + v23, v15, (unsigned int)a1[4]);
        v24 = v23 + a1[4];
        if ( (unsigned int)v24 >= v23 )
        {
          v9 = 0;
          memcpy_0((char *)a1 + v24, v17, (unsigned int)a1[5]);
          goto LABEL_33;
        }
        v8 = 260;
      }
    }
LABEL_41:
    v9 = -1073741675;
    v10 = 3221225621LL;
    goto LABEL_49;
  }
  v9 = 0;
LABEL_33:
  *a2 = v21;
  return v9;
}

```

## disassembly

```asm
0x180058e54  mov     [rsp-8+arg_18], rbx
0x180058e59  push    rbp
0x180058e5a  push    rsi
0x180058e5b  push    rdi
0x180058e5c  push    r12
0x180058e5e  push    r13
0x180058e60  push    r14
0x180058e62  push    r15
0x180058e64  lea     rbp, [rsp-10h]
0x180058e69  sub     rsp, 110h
0x180058e70  mov     rax, cs:__security_cookie
0x180058e77  xor     rax, rsp
0x180058e7a  mov     [rbp+40h+var_40], rax
0x180058e7e  xor     r13d, r13d
0x180058e81  mov     rax, r8
0x180058e84  mov     r12, rdx
0x180058e87  mov     rdi, rcx
0x180058e8a  test    r8, r8
0x180058e8d  jz      loc_1800590D1
0x180058e93  test    rdx, rdx
0x180058e96  jz      loc_1800590D1
0x180058e9c  mov     edx, [rax]
0x180058e9e  lea     rcx, [rsp+140h+var_100]
0x180058ea3  mov     [rsp+140h+var_118], rcx
0x180058ea8  lea     r9, qword_180087820
0x180058eaf  mov     rcx, [rax+8]
0x180058eb3  lea     r8, [rsp+140h+var_110]
0x180058eb8  mov     [rsp+140h+var_110], 0Bh
0x180058ec0  mov     [rsp+140h+var_120], 0Ch
0x180058ec8  call    MinAsn1ExtractValues
0x180058ecd  test    eax, eax
0x180058ecf  cmovg   eax, [rsp+140h+var_F0]
0x180058ed4  test    eax, eax
0x180058ed6  jns     short loc_180058EED
0x180058ed8  mov     r9d, 9Ah
0x180058ede  mov     ebx, 0C000090Bh
0x180058ee3  mov     ecx, 0C000090Bh
0x180058ee8  jmp     loc_1800590E1
0x180058eed  mov     rdx, [rbp+40h+var_B8]
0x180058ef1  or      eax, 0FFFFFFFFh
0x180058ef4  mov     ecx, dword ptr [rbp+40h+Size]
0x180058ef7  test    rdx, rdx
0x180058efa  jz      short loc_180058F0E
0x180058efc  cmp     ecx, 1
0x180058eff  jbe     short loc_180058F0E
0x180058f01  cmp     [rdx], r13b
0x180058f04  jnz     short loc_180058F0E
0x180058f06  add     ecx, eax
0x180058f08  add     rdx, 1; Src
0x180058f0c  jnz     short loc_180058EFC
0x180058f0e  mov     rbx, [rsp+140h+Src]
0x180058f13  mov     r8d, [rsp+140h+var_D0]
0x180058f18  test    rbx, rbx
0x180058f1b  jz      short loc_180058F31
0x180058f1d  cmp     r8d, 1
0x180058f21  jbe     short loc_180058F31
0x180058f23  cmp     [rbx], r13b
0x180058f26  jnz     short loc_180058F31
0x180058f28  add     r8d, eax
0x180058f2b  add     rbx, 1
0x180058f2f  jnz     short loc_180058F1D
0x180058f31  mov     r14, [rbp+40h+var_98]
0x180058f35  mov     r10d, [rbp+40h+var_A0]
0x180058f39  test    r14, r14
0x180058f3c  jz      short loc_180058F52
0x180058f3e  cmp     r10d, 1
0x180058f42  jbe     short loc_180058F52
0x180058f44  cmp     [r14], r13b
0x180058f47  jnz     short loc_180058F52
0x180058f49  add     r10d, eax
0x180058f4c  add     r14, 1
0x180058f50  jnz     short loc_180058F3E
0x180058f52  mov     r15, [rbp+40h+var_88]
0x180058f56  mov     r9d, [rbp+40h+var_90]
0x180058f5a  test    r15, r15
0x180058f5d  jz      short loc_180058F73
0x180058f5f  cmp     r9d, 1
0x180058f63  jbe     short loc_180058F73
0x180058f65  cmp     [r15], r13b
0x180058f68  jnz     short loc_180058F73
0x180058f6a  add     r9d, eax
0x180058f6d  add     r15, 1
0x180058f71  jnz     short loc_180058F5F
0x180058f73  mov     eax, 0FFFFFFFh
0x180058f78  cmp     ecx, eax
0x180058f7a  ja      loc_1800590C6
0x180058f80  cmp     r8d, eax
0x180058f83  ja      loc_1800590C6
0x180058f89  cmp     r10d, eax
0x180058f8c  ja      loc_1800590C6
0x180058f92  cmp     r9d, eax
0x180058f95  ja      loc_1800590C6
0x180058f9b  lea     eax, [rcx+18h]
0x180058f9e  cmp     eax, 18h
0x180058fa1  jb      loc_1800590BE
0x180058fa7  lea     r11d, [rax+r8]
0x180058fab  cmp     r11d, eax
0x180058fae  jb      loc_1800590B6
0x180058fb4  lea     eax, [r11+r10]
0x180058fb8  cmp     eax, r11d
0x180058fbb  jb      loc_1800590AE
0x180058fc1  lea     esi, [rax+r9]
0x180058fc5  cmp     esi, eax
0x180058fc7  jb      loc_1800590A6
0x180058fcd  test    rdi, rdi
0x180058fd0  jnz     short loc_180058FDE
0x180058fd2  mov     ebx, r13d
0x180058fd5  mov     [r12], esi
0x180058fd9  jmp     loc_1800590F4
0x180058fde  cmp     [r12], esi
0x180058fe2  jnb     short loc_180058FFD
0x180058fe4  mov     [r12], esi
0x180058fe8  mov     ebx, 0C0000023h
0x180058fed  mov     r9d, 0DDh
0x180058ff3  mov     ecx, 0C0000023h
0x180058ff8  jmp     loc_1800590E1
0x180058ffd  lea     eax, ds:0[r8*8]
0x180059005  mov     [rdi+0Ch], r8d
0x180059009  mov     r8d, ecx; Size
0x18005900c  mov     [rdi+8], ecx
0x18005900f  lea     rcx, [rdi+18h]; void *
0x180059013  mov     dword ptr [rdi], 32415352h
0x180059019  mov     [rdi+4], eax
0x18005901c  mov     [rdi+10h], r10d
0x180059020  mov     [rdi+14h], r9d
0x180059024  call    memcpy_0
0x180059029  mov     r13d, [rdi+8]
0x18005902d  add     r13d, 18h
0x180059031  cmp     r13d, 18h
0x180059035  jb      short loc_18005909E
0x180059037  mov     r8d, [rdi+0Ch]; Size
0x18005903b  mov     rdx, rbx; Src
0x18005903e  mov     ecx, r13d
0x180059041  add     rcx, rdi; void *
0x180059044  call    memcpy_0
0x180059049  mov     ebx, [rdi+0Ch]
0x18005904c  add     ebx, r13d
0x18005904f  cmp     ebx, r13d
0x180059052  jb      short loc_180059096
0x180059054  mov     r8d, [rdi+10h]; Size
0x180059058  mov     rdx, r14; Src
0x18005905b  mov     ecx, ebx
0x18005905d  add     rcx, rdi; void *
0x180059060  call    memcpy_0
0x180059065  mov     ecx, [rdi+10h]
0x180059068  add     ecx, ebx
0x18005906a  cmp     ecx, ebx
0x18005906c  jb      short loc_180059084
0x18005906e  mov     r8d, [rdi+14h]; Size
0x180059072  xor     ebx, ebx
0x180059074  add     rcx, rdi; void *
0x180059077  mov     rdx, r15; Src
0x18005907a  call    memcpy_0
0x18005907f  jmp     loc_180058FD5
0x180059084  mov     r9d, 104h
0x18005908a  mov     ebx, 0C0000095h
0x18005908f  mov     ecx, 0C0000095h
0x180059094  jmp     short loc_1800590E1
0x180059096  mov     r9d, 0FAh
0x18005909c  jmp     short loc_18005908A
0x18005909e  mov     r9d, 0F0h
0x1800590a4  jmp     short loc_18005908A
0x1800590a6  mov     r9d, 0D0h
0x1800590ac  jmp     short loc_18005908A
0x1800590ae  mov     r9d, 0CAh
0x1800590b4  jmp     short loc_18005908A
0x1800590b6  mov     r9d, 0C4h
0x1800590bc  jmp     short loc_18005908A
0x1800590be  mov     r9d, 0BEh
0x1800590c4  jmp     short loc_18005908A
0x1800590c6  mov     r9d, 0B6h
0x1800590cc  jmp     loc_180058EDE
0x1800590d1  mov     ebx, 0C000000Dh
0x1800590d6  mov     r9d, 93h
0x1800590dc  mov     ecx, 0C000000Dh
0x1800590e1  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800590e8  lea     rdx, aStatus; "Status"
0x1800590ef  call    DebugTraceError
0x1800590f4  mov     eax, ebx
0x1800590f6  mov     rcx, [rbp+40h+var_40]
0x1800590fa  xor     rcx, rsp; StackCookie
0x1800590fd  call    __security_check_cookie
0x180059102  mov     rbx, [rsp+140h+arg_18]
0x18005910a  add     rsp, 110h
0x180059111  pop     r15
0x180059113  pop     r14
0x180059115  pop     r13
0x180059117  pop     r12
0x180059119  pop     rdi
0x18005911a  pop     rsi
0x18005911b  pop     rbp
0x18005911c  retn
```
