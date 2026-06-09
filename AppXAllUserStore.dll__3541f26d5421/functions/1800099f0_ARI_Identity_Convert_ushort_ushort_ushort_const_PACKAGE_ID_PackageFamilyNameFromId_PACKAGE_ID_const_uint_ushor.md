# ARI::Identity::Convert<ushort,ushort *,ushort const *,PACKAGE_ID>::PackageFamilyNameFromId(PACKAGE_ID const *,uint *,ushort *)

- ea: `0x1800099f0`
- end: `0x180009d79`
- name: `?PackageFamilyNameFromId@?$Convert@GPEAGPEBGUPACKAGE_ID@@@Identity@ARI@@SAJPEBUPACKAGE_ID@@PEAIPEAG@Z`
- size: `905`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800095d0`
- `0x180045bb0`

## callees

- `0x1800099f0`
- `0x180016734`
- `0x180048f08`
- `0x18004c972`
- `0x18004c9d0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009b2e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009b6f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009bfa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009b2e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009b6f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009bfa`

## pseudocode

```c
__int64 __fastcall ARI::Identity::Convert<unsigned short,unsigned short *,unsigned short const *,PACKAGE_ID>::PackageFamilyNameFromId(
        _QWORD *a1,
        _DWORD *a2,
        void *a3)
{
  const WCHAR *v6; // rsi
  __int64 v7; // rbp
  const WCHAR *v8; // rdx
  WCHAR *v9; // r8
  unsigned int v10; // eax
  __int64 v11; // r9
  WCHAR v12; // cx
  unsigned __int64 v13; // rdi
  unsigned __int64 i; // rbx
  unsigned __int64 j; // rbx
  unsigned __int64 v16; // rdx
  unsigned __int64 v18; // rbx
  unsigned __int64 v19; // rdi
  unsigned int v20; // edi
  int v21; // eax
  unsigned int v22; // ecx
  unsigned __int16 *v23; // r11
  unsigned int v24; // r10d
  __int64 v25; // rbp
  unsigned __int16 *v26; // r9
  unsigned int v27; // eax
  int v28; // r8d
  const char *k; // rax
  unsigned int v30; // [rsp+30h] [rbp-D8h] BYREF
  unsigned int v31; // [rsp+34h] [rbp-D4h] BYREF
  _OWORD Src[8]; // [rsp+40h] [rbp-C8h] BYREF

  if ( !a1 || !a2 || *a2 && !a3 )
    return 87;
  v6 = (const WCHAR *)a1[2];
  v7 = 0;
  memset(Src, 0, sizeof(Src));
  if ( !v6 )
    return 87;
  v8 = v6;
  v9 = (WCHAR *)Src;
  v10 = 0;
  v11 = 97;
  while ( 1 )
  {
    v12 = *v8;
    if ( !*v8 )
      break;
    if ( v10 >= 0x32 )
      return 87;
    if ( v12 >= 0x61u )
    {
      if ( v12 > 0x7Au )
        return 87;
    }
    else if ( v12 >= 0x41u )
    {
      if ( v12 > 0x5Au )
        return 87;
    }
    else if ( (unsigned __int16)(v12 - 45) > 1u && (unsigned __int16)(v12 - 48) > 9u )
    {
      return 87;
    }
    *v9 = v12;
    ++v8;
    ++v9;
    v7 = (unsigned int)(v7 + 1);
    v10 = v7;
  }
  if ( v10 < 3 )
    return 87;
  v13 = (unsigned int)(v8 - v6);
  for ( i = 0; i < 0x18; ++i )
  {
    v9 = (WCHAR *)(2 * i);
    v11 = (unsigned int)dword_18004E190[4 * i];
    if ( v13 == v11 && CompareStringOrdinal(v6, v13, (&off_18004E198)[2 * i], v11, 1) == 2 )
      return 87;
  }
  for ( j = 0; j < 0x17; ++j )
  {
    v9 = (WCHAR *)(2 * j);
    v16 = (unsigned int)dword_18004E020[4 * j];
    if ( v13 >= v16 && CompareStringOrdinal(v6, v16, (&off_18004E028)[2 * j], v16, 1) == 2 )
      return 87;
  }
  if ( v13 && v6[v13 - 1] == 46 )
    return 87;
  if ( v13 >= 5 )
  {
    v18 = 0;
    v19 = v13 - 5;
    while ( v18 <= v19 )
    {
      if ( CompareStringOrdinal(&v6[v18], 5, L".xn--", 5, 1) == 2 )
        return 87;
      ++v18;
    }
  }
  v23 = (unsigned __int16 *)a1[5];
  v24 = 0;
  v30 = 0;
  *((_WORD *)Src + v7) = 95;
  v25 = (unsigned int)(v7 + 1);
  v31 = v25;
  if ( v23 )
  {
    v26 = v23;
    v27 = 0;
LABEL_49:
    v28 = *v26;
    if ( (_WORD)v28 )
    {
      if ( v27 < 0xD )
      {
        for ( k = "1234567890abcdefghjkmnpqrstvwxyzABCDEFGHJKMNPQRSTVWXYZ"; *k; ++k )
        {
          if ( v28 == *k )
          {
            v27 = ++v24;
            ++v26;
            goto LABEL_49;
          }
        }
      }
      return 87;
    }
    if ( v27 != 13 )
      return 87;
  }
  else
  {
    if ( !(unsigned __int8)ReservedForLocalUse::IsPublisherValid<unsigned short,unsigned short const *>(
                             a1[3],
                             &v30,
                             v9,
                             v11) )
      return 87;
    v24 = v30;
  }
  v20 = v25 + 13;
  if ( *a2 < (unsigned int)(v25 + 14) )
  {
    *a2 = v25 + 14;
    return 122;
  }
  else
  {
    if ( v23 )
    {
      memcpy_0((char *)Src + 2 * v25, v23, 2LL * v24);
LABEL_37:
      memcpy_0(a3, Src, 2LL * v20);
      *((_WORD *)a3 + v20) = 0;
      *a2 = v20 + 1;
      return 0;
    }
    v21 = ReservedForLocalUse::HashThePublisher<unsigned short,unsigned short const *>(
            v24,
            a1[3],
            v28,
            (unsigned int)&v31,
            (__int64)Src);
    v22 = v21;
    if ( v21 >= 0 )
    {
      v20 = v31;
      goto LABEL_37;
    }
    if ( (v21 & 0x1FFF0000) == 0x70000 )
      return (unsigned __int16)v21;
    return v22;
  }
}

```

## disassembly

```asm
0x1800099f0  mov     [rsp+arg_18], rbx
0x1800099f5  push    rbp
0x1800099f6  push    rsi
0x1800099f7  push    rdi
0x1800099f8  push    r12
0x1800099fa  push    r13
0x1800099fc  push    r14
0x1800099fe  push    r15
0x180009a00  sub     rsp, 0D0h
0x180009a07  mov     rax, cs:__security_cookie
0x180009a0e  xor     rax, rsp
0x180009a11  mov     [rsp+108h+var_48], rax
0x180009a19  mov     r12, r8
0x180009a1c  mov     r15, rdx
0x180009a1f  mov     r14, rcx
0x180009a22  test    rcx, rcx
0x180009a25  jz      loc_180009B88
0x180009a2b  test    rdx, rdx
0x180009a2e  jz      loc_180009B88
0x180009a34  cmp     dword ptr [rdx], 0
0x180009a37  ja      loc_180009C71
0x180009a3d  mov     rsi, [rcx+10h]
0x180009a41  xorps   xmm0, xmm0
0x180009a44  xor     ebp, ebp
0x180009a46  movups  [rsp+108h+Src], xmm0
0x180009a4b  movups  [rsp+108h+var_B8], xmm0
0x180009a50  movups  [rsp+108h+var_A8], xmm0
0x180009a55  movups  [rsp+108h+var_98], xmm0
0x180009a5a  movups  [rsp+108h+var_88], xmm0
0x180009a62  movups  [rsp+108h+var_78], xmm0
0x180009a6a  movups  [rsp+108h+var_68], xmm0
0x180009a72  movups  [rsp+108h+var_58], xmm0
0x180009a7a  test    rsi, rsi
0x180009a7d  jz      loc_180009B88
0x180009a83  mov     rdx, rsi
0x180009a86  lea     r8, [rsp+108h+Src]
0x180009a8b  xor     eax, eax
0x180009a8d  mov     r9d, 61h ; 'a'
0x180009a93  mov     r10d, 41h ; 'A'
0x180009a99  nop     dword ptr [rax+00000000h]
0x180009aa0  movzx   ecx, word ptr [rdx]
0x180009aa3  test    cx, cx
0x180009aa6  jz      short loc_180009AE4
0x180009aa8  cmp     eax, 32h ; '2'
0x180009aab  jnb     loc_180009B88
0x180009ab1  cmp     r9w, cx
0x180009ab5  jbe     loc_180009D41
0x180009abb  cmp     r10w, cx
0x180009abf  jbe     loc_180009C7F
0x180009ac5  lea     eax, [rcx-2Dh]
0x180009ac8  cmp     ax, 1
0x180009acc  ja      loc_180009C0A
0x180009ad2  mov     [r8], cx
0x180009ad6  add     rdx, 2
0x180009ada  add     r8, 2
0x180009ade  inc     ebp
0x180009ae0  mov     eax, ebp
0x180009ae2  jmp     short loc_180009AA0
0x180009ae4  cmp     eax, 3
0x180009ae7  jb      loc_180009B88
0x180009aed  sub     rdx, rsi
0x180009af0  lea     r13, __ImageBase
0x180009af7  sar     rdx, 1
0x180009afa  mov     edi, edx
0x180009afc  xor     ebx, ebx
0x180009afe  xchg    ax, ax
0x180009b00  cmp     rbx, 18h
0x180009b04  jnb     short loc_180009B3E
0x180009b06  mov     r8, rbx
0x180009b09  add     r8, r8
0x180009b0c  mov     r9d, ds:rva dword_18004E190[r13+r8*8]; cchCount2
0x180009b14  cmp     rdi, r9
0x180009b17  jnz     short loc_180009B39
0x180009b19  mov     r8, ds:rva off_18004E198[r13+r8*8]; lpString2
0x180009b21  mov     edx, edi; cchCount1
0x180009b23  mov     rcx, rsi; lpString1
0x180009b26  mov     [rsp+108h+bIgnoreCase], 1; bIgnoreCase
0x180009b2e  call    cs:__imp_CompareStringOrdinal
0x180009b34  cmp     eax, 2
0x180009b37  jz      short loc_180009B88
0x180009b39  inc     rbx
0x180009b3c  jmp     short loc_180009B00
0x180009b3e  xor     ebx, ebx
0x180009b40  cmp     rbx, 17h
0x180009b44  jnb     short loc_180009BB8
0x180009b46  mov     r8, rbx
0x180009b49  add     r8, r8
0x180009b4c  mov     edx, ds:rva dword_18004E020[r13+r8*8]; cchCount1
0x180009b54  cmp     rdi, rdx
0x180009b57  jb      short loc_180009B7A
0x180009b59  mov     r8, ds:rva off_18004E028[r13+r8*8]; lpString2
0x180009b61  mov     r9d, edx; cchCount2
0x180009b64  mov     rcx, rsi; lpString1
0x180009b67  mov     [rsp+108h+bIgnoreCase], 1; bIgnoreCase
0x180009b6f  call    cs:__imp_CompareStringOrdinal
0x180009b75  cmp     eax, 2
0x180009b78  jz      short loc_180009B88
0x180009b7a  inc     rbx
0x180009b7d  jmp     short loc_180009B40
0x180009b7f  cmp     eax, 0Dh
0x180009b82  jz      loc_180009C1C
0x180009b88  mov     eax, 57h ; 'W'
0x180009b8d  mov     rcx, [rsp+108h+var_48]
0x180009b95  xor     rcx, rsp; StackCookie
0x180009b98  call    __security_check_cookie
0x180009b9d  mov     rbx, [rsp+108h+arg_18]
0x180009ba5  add     rsp, 0D0h
0x180009bac  pop     r15
0x180009bae  pop     r14
0x180009bb0  pop     r13
0x180009bb2  pop     r12
0x180009bb4  pop     rdi
0x180009bb5  pop     rsi
0x180009bb6  pop     rbp
0x180009bb7  retn
0x180009bb8  test    rdi, rdi
0x180009bbb  jz      short loc_180009BC5
0x180009bbd  cmp     word ptr [rsi+rdi*2-2], 2Eh ; '.'
0x180009bc3  jz      short loc_180009B88
0x180009bc5  cmp     rdi, 5
0x180009bc9  jb      loc_180009CD6
0x180009bcf  xor     ebx, ebx
0x180009bd1  add     rdi, 0FFFFFFFFFFFFFFFBh
0x180009bd5  cmp     rbx, rdi
0x180009bd8  ja      loc_180009CD6
0x180009bde  mov     r9d, 5; cchCount2
0x180009be4  mov     [rsp+108h+bIgnoreCase], 1; bIgnoreCase
0x180009bec  mov     edx, r9d; cchCount1
0x180009bef  lea     rcx, [rsi+rbx*2]; lpString1
0x180009bf3  lea     r8, String2; ".xn--"
0x180009bfa  call    cs:__imp_CompareStringOrdinal
0x180009c00  cmp     eax, 2
0x180009c03  jz      short loc_180009B88
0x180009c05  inc     rbx
0x180009c08  jmp     short loc_180009BD5
0x180009c0a  lea     eax, [rcx-30h]
0x180009c0d  cmp     ax, 9
0x180009c11  jbe     loc_180009AD2
0x180009c17  jmp     loc_180009B88
0x180009c1c  lea     edi, [rbp+0Dh]
0x180009c1f  lea     eax, [rdi+1]
0x180009c22  cmp     [r15], eax
0x180009c25  jb      loc_180009CC9
0x180009c2b  test    r11, r11
0x180009c2e  jz      short loc_180009C8E
0x180009c30  mov     r8d, r10d
0x180009c33  lea     rcx, [rsp+108h+Src]
0x180009c38  add     r8, r8; Size
0x180009c3b  lea     rcx, [rcx+rbp*2]; void *
0x180009c3f  mov     rdx, r11; Src
0x180009c42  call    memcpy_0
0x180009c47  mov     eax, edi
0x180009c49  lea     rdx, [rsp+108h+Src]; Src
0x180009c4e  mov     rcx, r12; void *
0x180009c51  lea     rbx, [rax+rax]
0x180009c55  mov     r8, rbx; Size
0x180009c58  call    memcpy_0
0x180009c5d  xor     eax, eax
0x180009c5f  mov     [rbx+r12], ax
0x180009c64  lea     eax, [rdi+1]
0x180009c67  mov     [r15], eax
0x180009c6a  xor     eax, eax
0x180009c6c  jmp     loc_180009B8D
0x180009c71  test    r12, r12
0x180009c74  jnz     loc_180009A3D
0x180009c7a  jmp     loc_180009B88
0x180009c7f  cmp     cx, 5Ah ; 'Z'
0x180009c83  ja      loc_180009B88
0x180009c89  jmp     loc_180009AD2
0x180009c8e  mov     rdx, [r14+18h]
0x180009c92  lea     rax, [rsp+108h+Src]
0x180009c97  lea     r9, [rsp+108h+var_D4]
0x180009c9c  mov     qword ptr [rsp+108h+bIgnoreCase], rax
0x180009ca1  mov     ecx, r10d
0x180009ca4  call    ??$HashThePublisher@GPEBG@ReservedForLocalUse@@YAJIPEBGIAEAIPEAG@Z; ReservedForLocalUse::HashThePublisher<ushort,ushort const *>(uint,ushort const *,uint,uint &,ushort *)
0x180009ca9  mov     ecx, eax
0x180009cab  test    eax, eax
0x180009cad  jns     loc_180009D70
0x180009cb3  and     eax, 1FFF0000h
0x180009cb8  cmp     eax, 70000h
0x180009cbd  jnz     short loc_180009CC2
0x180009cbf  movzx   ecx, cx
0x180009cc2  mov     eax, ecx
0x180009cc4  jmp     loc_180009B8D
0x180009cc9  mov     [r15], eax
0x180009ccc  mov     eax, 7Ah ; 'z'
0x180009cd1  jmp     loc_180009B8D
0x180009cd6  mov     r11, [r14+28h]
0x180009cda  xor     r10d, r10d
0x180009cdd  mov     ecx, 5Fh ; '_'
0x180009ce2  mov     [rsp+108h+var_D8], r10d
0x180009ce7  mov     word ptr [rsp+rbp*2+108h+Src], cx
0x180009cec  inc     ebp
0x180009cee  mov     [rsp+108h+var_D4], ebp
0x180009cf2  test    r11, r11
0x180009cf5  jz      short loc_180009D50
0x180009cf7  mov     r9, r11
0x180009cfa  xor     eax, eax
0x180009cfc  nop     dword ptr [rax+00h]
0x180009d00  movzx   r8d, word ptr [r9]
0x180009d04  test    r8w, r8w
0x180009d08  jz      loc_180009B7F
0x180009d0e  cmp     eax, 0Dh
0x180009d11  jnb     loc_180009B88
0x180009d17  lea     rax, a1234567890abcd; "1234567890abcdefghjkmnpqrstvwxyzABCDEFG"...
0x180009d1e  xchg    ax, ax
0x180009d20  movsx   ecx, byte ptr [rax]
0x180009d23  test    cl, cl
0x180009d25  jz      loc_180009B88
0x180009d2b  cmp     r8d, ecx
0x180009d2e  jz      short loc_180009D35
0x180009d30  inc     rax
0x180009d33  jmp     short loc_180009D20
0x180009d35  inc     r10d
0x180009d38  mov     eax, r10d
0x180009d3b  add     r9, 2
0x180009d3f  jmp     short loc_180009D00
0x180009d41  cmp     cx, 7Ah ; 'z'
0x180009d45  ja      loc_180009B88
0x180009d4b  jmp     loc_180009AD2
0x180009d50  mov     rcx, [r14+18h]
0x180009d54  lea     rdx, [rsp+108h+var_D8]
0x180009d59  call    ??$IsPublisherValid@GPEBG@ReservedForLocalUse@@YA_NPEBGAEAI@Z; ReservedForLocalUse::IsPublisherValid<ushort,ushort const *>(ushort const *,uint &)
0x180009d5e  test    al, al
0x180009d60  jz      loc_180009B88
0x180009d66  mov     r10d, [rsp+108h+var_D8]
0x180009d6b  jmp     loc_180009C1C
0x180009d70  mov     edi, [rsp+108h+var_D4]
0x180009d74  jmp     loc_180009C47
```
