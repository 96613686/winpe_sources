# ARI::Identity::Convert<ushort,ushort *,ushort const *,PACKAGE_ID>::PackageFamilyNameFromFullName(ushort const *,uint *,ushort *)

- ea: `0x180009d80`
- end: `0x18000a165`
- name: `?PackageFamilyNameFromFullName@?$Convert@GPEAGPEBGUPACKAGE_ID@@@Identity@ARI@@SAJPEBGPEAIPEAG@Z`
- size: `997`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `8`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180002c94`
- `0x18000b87c`
- `0x18000bf10`
- `0x180022188`
- `0x18002eb70`
- `0x180038560`
- `0x180038c28`
- `0x18003adb0`

## callees

- `0x180009d80`
- `0x18000a600`
- `0x180016734`
- `0x180048f08`
- `0x18004c972`
- `0x18004c98a`
- `0x18004c9d0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009ede`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009f23`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009fc5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009ede`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009f23`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009fc5`

## pseudocode

```c
__int64 __fastcall ARI::Identity::Convert<unsigned short,unsigned short *,unsigned short const *,PACKAGE_ID>::PackageFamilyNameFromFullName(
        LPCWCH lpString1,
        _DWORD *a2,
        void *a3)
{
  __int64 v6; // rdx
  __int64 result; // rax
  const WCHAR *v8; // rsi
  __int64 v9; // rbp
  LPCWCH v10; // rdx
  WCHAR *v11; // r8
  unsigned int v12; // eax
  __int64 v13; // r9
  WCHAR v14; // cx
  unsigned __int64 v15; // rdi
  unsigned __int64 i; // rbx
  unsigned __int64 j; // rbx
  unsigned __int64 v18; // rdx
  unsigned int v19; // ecx
  unsigned __int64 v20; // rbx
  unsigned __int64 v21; // rdi
  int v22; // r10d
  unsigned int v23; // edi
  unsigned __int16 *v24; // rbx
  unsigned int v25; // r11d
  __int64 v26; // rbp
  unsigned __int16 *v27; // r9
  unsigned int v28; // eax
  int v29; // r8d
  const char *k; // rax
  int v31; // eax
  unsigned int v32; // [rsp+30h] [rbp-1C8h] BYREF
  unsigned int v33[3]; // [rsp+34h] [rbp-1C4h] BYREF
  _WORD v34[64]; // [rsp+40h] [rbp-1B8h] BYREF
  _BYTE v35[16]; // [rsp+C0h] [rbp-138h] BYREF
  LPCWCH lpString1a; // [rsp+D0h] [rbp-128h]
  __int64 v37; // [rsp+D8h] [rbp-120h]
  void *Src; // [rsp+E8h] [rbp-110h]

  memset_0(v35, 0, 0xF0u);
  v32 = 240;
  result = ARI::Identity::Convert<unsigned short,unsigned short *,unsigned short const *,PACKAGE_ID>::PackageIdBasicFromFullName(
             lpString1,
             v6,
             &v32,
             (__int64)v35);
  if ( !(_DWORD)result )
  {
    if ( !a2 || *a2 && !a3 )
      return 87;
    memset_0(v34, 0, sizeof(v34));
    v8 = lpString1a;
    v9 = 0;
    if ( !lpString1a )
      return 87;
    v10 = lpString1a;
    v11 = v34;
    v12 = 0;
    v13 = 97;
    while ( 1 )
    {
      v14 = *v10;
      if ( !*v10 )
        break;
      if ( v12 >= 0x32 )
        return 87;
      if ( v14 >= 0x61u )
      {
        if ( v14 > 0x7Au )
          return 87;
      }
      else if ( v14 >= 0x41u )
      {
        if ( v14 > 0x5Au )
          return 87;
      }
      else if ( (unsigned __int16)(v14 - 45) > 1u && (unsigned __int16)(v14 - 48) > 9u )
      {
        return 87;
      }
      *v11 = v14;
      ++v10;
      ++v11;
      v9 = (unsigned int)(v9 + 1);
      v12 = v9;
    }
    if ( v12 < 3 )
      return 87;
    v15 = (unsigned int)(v10 - v8);
    for ( i = 0; i < 0x18; ++i )
    {
      v11 = (WCHAR *)(2 * i);
      v13 = (unsigned int)dword_18004E190[4 * i];
      if ( v15 == v13 && CompareStringOrdinal(v8, v15, (&off_18004E198)[2 * i], v13, 1) == 2 )
        return 87;
    }
    for ( j = 0; j < 0x17; ++j )
    {
      v11 = (WCHAR *)(2 * j);
      v18 = (unsigned int)dword_18004E020[4 * j];
      if ( v15 >= v18 && CompareStringOrdinal(v8, v18, (&off_18004E028)[2 * j], v18, 1) == 2 )
        return 87;
    }
    if ( v15 && v8[v15 - 1] == 46 )
      return 87;
    if ( v15 >= 5 )
    {
      v20 = 0;
      v21 = v15 - 5;
      while ( v20 <= v21 )
      {
        if ( CompareStringOrdinal(&v8[v20], 5, L".xn--", 5, 1) == 2 )
          return 87;
        ++v20;
      }
    }
    v24 = (unsigned __int16 *)Src;
    v25 = 0;
    v33[0] = 0;
    v34[v9] = 95;
    v26 = (unsigned int)(v9 + 1);
    v32 = v26;
    if ( v24 )
    {
      v27 = v24;
      v28 = 0;
LABEL_47:
      v29 = *v27;
      if ( (_WORD)v29 )
      {
        if ( v28 < 0xD )
        {
          for ( k = "1234567890abcdefghjkmnpqrstvwxyzABCDEFGHJKMNPQRSTVWXYZ"; *k; ++k )
          {
            if ( v29 == *k )
            {
              v28 = ++v25;
              ++v27;
              goto LABEL_47;
            }
          }
        }
        return 87;
      }
      if ( v28 != 13 )
        return 87;
      v22 = v37;
    }
    else
    {
      if ( !(unsigned __int8)ReservedForLocalUse::IsPublisherValid<unsigned short,unsigned short const *>(
                               v37,
                               v33,
                               v11,
                               v13) )
        return 87;
      v25 = v33[0];
    }
    v23 = v26 + 13;
    if ( *a2 < (unsigned int)(v26 + 14) )
    {
      *a2 = v26 + 14;
      return 122;
    }
    else
    {
      if ( v24 )
      {
        memcpy_0(&v34[v26], v24, 2LL * v25);
      }
      else
      {
        v31 = ReservedForLocalUse::HashThePublisher<unsigned short,unsigned short const *>(
                v25,
                v22,
                v29,
                (unsigned int)&v32,
                (__int64)v34);
        v19 = v31;
        if ( v31 < 0 )
        {
          if ( (v31 & 0x1FFF0000) == 0x70000 )
            return (unsigned __int16)v31;
          return v19;
        }
        v23 = v32;
      }
      memcpy_0(a3, v34, 2LL * v23);
      *((_WORD *)a3 + v23) = 0;
      v19 = 0;
      *a2 = v23 + 1;
    }
    return v19;
  }
  return result;
}

```

## disassembly

```asm
0x180009d80  push    rbx
0x180009d82  push    r14
0x180009d84  push    r15
0x180009d86  sub     rsp, 1E0h
0x180009d8d  mov     rax, cs:__security_cookie
0x180009d94  xor     rax, rsp
0x180009d97  mov     [rsp+1F8h+var_48], rax
0x180009d9f  mov     r15, r8
0x180009da2  mov     r14, rdx
0x180009da5  mov     rbx, rcx
0x180009da8  xor     edx, edx; Val
0x180009daa  mov     r8d, 0F0h; Size
0x180009db0  lea     rcx, [rsp+1F8h+var_138]; void *
0x180009db8  call    memset_0
0x180009dbd  lea     r9, [rsp+1F8h+var_138]
0x180009dc5  mov     [rsp+1F8h+var_1C8], 0F0h
0x180009dcd  lea     r8, [rsp+1F8h+var_1C8]
0x180009dd2  mov     rcx, rbx; lpString1
0x180009dd5  call    ?PackageIdBasicFromFullName@?$Convert@GPEAGPEBGUPACKAGE_ID@@@Identity@ARI@@SAJPEBGIPEAIPEAE@Z; ARI::Identity::Convert<ushort,ushort *,ushort const *,PACKAGE_ID>::PackageIdBasicFromFullName(ushort const *,uint,uint *,uchar *)
0x180009dda  test    eax, eax
0x180009ddc  jnz     loc_180009F63
0x180009de2  mov     [rsp+1F8h+var_20], rbp
0x180009dea  mov     [rsp+1F8h+var_28], rsi
0x180009df2  mov     [rsp+1F8h+var_30], rdi
0x180009dfa  mov     [rsp+1F8h+var_38], r12
0x180009e02  test    r14, r14
0x180009e05  jz      loc_180009F3C
0x180009e0b  cmp     [r14], eax
0x180009e0e  ja      loc_18000A04C
0x180009e14  xor     edx, edx; Val
0x180009e16  lea     rcx, [rsp+1F8h+var_1B8]; void *
0x180009e1b  mov     r8d, 80h; Size
0x180009e21  call    memset_0
0x180009e26  mov     rsi, [rsp+1F8h+lpString1]
0x180009e2e  xor     ebp, ebp
0x180009e30  test    rsi, rsi
0x180009e33  jz      loc_180009F3C
0x180009e39  mov     rdx, rsi
0x180009e3c  lea     r8, [rsp+1F8h+var_1B8]
0x180009e41  xor     eax, eax
0x180009e43  mov     r9d, 61h ; 'a'
0x180009e49  mov     r10d, 41h ; 'A'
0x180009e4f  nop
0x180009e50  movzx   ecx, word ptr [rdx]
0x180009e53  test    cx, cx
0x180009e56  jz      short loc_180009E94
0x180009e58  cmp     eax, 32h ; '2'
0x180009e5b  jnb     loc_180009F3C
0x180009e61  cmp     r9w, cx
0x180009e65  jbe     loc_18000A126
0x180009e6b  cmp     r10w, cx
0x180009e6f  jbe     loc_18000A05A
0x180009e75  lea     eax, [rcx-2Dh]
0x180009e78  cmp     ax, 1
0x180009e7c  ja      loc_180009FD9
0x180009e82  mov     [r8], cx
0x180009e86  add     rdx, 2
0x180009e8a  add     r8, 2
0x180009e8e  inc     ebp
0x180009e90  mov     eax, ebp
0x180009e92  jmp     short loc_180009E50
0x180009e94  cmp     eax, 3
0x180009e97  jb      loc_180009F3C
0x180009e9d  sub     rdx, rsi
0x180009ea0  lea     r12, __ImageBase
0x180009ea7  sar     rdx, 1
0x180009eaa  mov     edi, edx
0x180009eac  xor     ebx, ebx
0x180009eae  xchg    ax, ax
0x180009eb0  cmp     rbx, 18h
0x180009eb4  jnb     short loc_180009EEE
0x180009eb6  mov     r8, rbx
0x180009eb9  add     r8, r8
0x180009ebc  mov     r9d, ds:rva dword_18004E190[r12+r8*8]; cchCount2
0x180009ec4  cmp     rdi, r9
0x180009ec7  jnz     short loc_180009EE9
0x180009ec9  mov     r8, ds:rva off_18004E198[r12+r8*8]; lpString2
0x180009ed1  mov     edx, edi; cchCount1
0x180009ed3  mov     rcx, rsi; lpString1
0x180009ed6  mov     [rsp+1F8h+bIgnoreCase], 1; bIgnoreCase
0x180009ede  call    cs:__imp_CompareStringOrdinal
0x180009ee4  cmp     eax, 2
0x180009ee7  jz      short loc_180009F3C
0x180009ee9  inc     rbx
0x180009eec  jmp     short loc_180009EB0
0x180009eee  xor     ebx, ebx
0x180009ef0  cmp     rbx, 17h
0x180009ef4  jnb     loc_180009F80
0x180009efa  mov     r8, rbx
0x180009efd  add     r8, r8
0x180009f00  mov     edx, ds:rva dword_18004E020[r12+r8*8]; cchCount1
0x180009f08  cmp     rdi, rdx
0x180009f0b  jb      short loc_180009F2E
0x180009f0d  mov     r8, ds:rva off_18004E028[r12+r8*8]; lpString2
0x180009f15  mov     r9d, edx; cchCount2
0x180009f18  mov     rcx, rsi; lpString1
0x180009f1b  mov     [rsp+1F8h+bIgnoreCase], 1; bIgnoreCase
0x180009f23  call    cs:__imp_CompareStringOrdinal
0x180009f29  cmp     eax, 2
0x180009f2c  jz      short loc_180009F3C
0x180009f2e  inc     rbx
0x180009f31  jmp     short loc_180009EF0
0x180009f33  cmp     eax, 0Dh
0x180009f36  jz      loc_180009FEB
0x180009f3c  mov     ecx, 57h ; 'W'
0x180009f41  mov     r12, [rsp+1F8h+var_38]
0x180009f49  mov     eax, ecx
0x180009f4b  mov     rdi, [rsp+1F8h+var_30]
0x180009f53  mov     rsi, [rsp+1F8h+var_28]
0x180009f5b  mov     rbp, [rsp+1F8h+var_20]
0x180009f63  mov     rcx, [rsp+1F8h+var_48]
0x180009f6b  xor     rcx, rsp; StackCookie
0x180009f6e  call    __security_check_cookie
0x180009f73  add     rsp, 1E0h
0x180009f7a  pop     r15
0x180009f7c  pop     r14
0x180009f7e  pop     rbx
0x180009f7f  retn
0x180009f80  test    rdi, rdi
0x180009f83  jz      short loc_180009F8D
0x180009f85  cmp     word ptr [rsi+rdi*2-2], 2Eh ; '.'
0x180009f8b  jz      short loc_180009F3C
0x180009f8d  cmp     rdi, 5
0x180009f91  jb      loc_18000A069
0x180009f97  xor     ebx, ebx
0x180009f99  add     rdi, 0FFFFFFFFFFFFFFFBh
0x180009f9d  nop     dword ptr [rax]
0x180009fa0  cmp     rbx, rdi
0x180009fa3  ja      loc_18000A069
0x180009fa9  mov     r9d, 5; cchCount2
0x180009faf  mov     [rsp+1F8h+bIgnoreCase], 1; bIgnoreCase
0x180009fb7  mov     edx, r9d; cchCount1
0x180009fba  lea     rcx, [rsi+rbx*2]; lpString1
0x180009fbe  lea     r8, String2; ".xn--"
0x180009fc5  call    cs:__imp_CompareStringOrdinal
0x180009fcb  cmp     eax, 2
0x180009fce  jz      loc_180009F3C
0x180009fd4  inc     rbx
0x180009fd7  jmp     short loc_180009FA0
0x180009fd9  lea     eax, [rcx-30h]
0x180009fdc  cmp     ax, 9
0x180009fe0  jbe     loc_180009E82
0x180009fe6  jmp     loc_180009F3C
0x180009feb  mov     r10, [rsp+1F8h+var_120]
0x180009ff3  lea     edi, [rbp+0Dh]
0x180009ff6  lea     eax, [rdi+1]
0x180009ff9  cmp     [r14], eax
0x180009ffc  jb      loc_18000A119
0x18000a002  test    rbx, rbx
0x18000a005  jz      loc_18000A0E1
0x18000a00b  mov     r8d, r11d
0x18000a00e  lea     rcx, [rsp+1F8h+var_1B8]
0x18000a013  add     r8, r8; Size
0x18000a016  lea     rcx, [rcx+rbp*2]; void *
0x18000a01a  mov     rdx, rbx; Src
0x18000a01d  call    memcpy_0
0x18000a022  mov     eax, edi
0x18000a024  lea     rdx, [rsp+1F8h+var_1B8]; Src
0x18000a029  mov     rcx, r15; void *
0x18000a02c  lea     rbx, [rax+rax]
0x18000a030  mov     r8, rbx; Size
0x18000a033  call    memcpy_0
0x18000a038  xor     eax, eax
0x18000a03a  mov     [rbx+r15], ax
0x18000a03f  xor     ecx, ecx
0x18000a041  lea     eax, [rdi+1]
0x18000a044  mov     [r14], eax
0x18000a047  jmp     loc_180009F41
0x18000a04c  test    r15, r15
0x18000a04f  jnz     loc_180009E14
0x18000a055  jmp     loc_180009F3C
0x18000a05a  cmp     cx, 5Ah ; 'Z'
0x18000a05e  ja      loc_180009F3C
0x18000a064  jmp     loc_180009E82
0x18000a069  mov     rbx, [rsp+1F8h+Src]
0x18000a071  xor     r11d, r11d
0x18000a074  mov     ecx, 5Fh ; '_'
0x18000a079  mov     [rsp+1F8h+var_1C4], r11d
0x18000a07e  mov     [rsp+rbp*2+1F8h+var_1B8], cx
0x18000a083  inc     ebp
0x18000a085  mov     [rsp+1F8h+var_1C8], ebp
0x18000a089  test    rbx, rbx
0x18000a08c  jz      loc_18000A135
0x18000a092  mov     r9, rbx
0x18000a095  xor     eax, eax
0x18000a097  nop     word ptr [rax+rax+00000000h]
0x18000a0a0  movzx   r8d, word ptr [r9]
0x18000a0a4  test    r8w, r8w
0x18000a0a8  jz      loc_180009F33
0x18000a0ae  cmp     eax, 0Dh
0x18000a0b1  jnb     loc_180009F3C
0x18000a0b7  lea     rax, a1234567890abcd; "1234567890abcdefghjkmnpqrstvwxyzABCDEFG"...
0x18000a0be  xchg    ax, ax
0x18000a0c0  movsx   ecx, byte ptr [rax]
0x18000a0c3  test    cl, cl
0x18000a0c5  jz      loc_180009F3C
0x18000a0cb  cmp     r8d, ecx
0x18000a0ce  jz      short loc_18000A0D5
0x18000a0d0  inc     rax
0x18000a0d3  jmp     short loc_18000A0C0
0x18000a0d5  inc     r11d
0x18000a0d8  mov     eax, r11d
0x18000a0db  add     r9, 2
0x18000a0df  jmp     short loc_18000A0A0
0x18000a0e1  lea     rax, [rsp+1F8h+var_1B8]
0x18000a0e6  mov     rdx, r10
0x18000a0e9  lea     r9, [rsp+1F8h+var_1C8]
0x18000a0ee  mov     qword ptr [rsp+1F8h+bIgnoreCase], rax
0x18000a0f3  mov     ecx, r11d
0x18000a0f6  call    ??$HashThePublisher@GPEBG@ReservedForLocalUse@@YAJIPEBGIAEAIPEAG@Z; ReservedForLocalUse::HashThePublisher<ushort,ushort const *>(uint,ushort const *,uint,uint &,ushort *)
0x18000a0fb  mov     ecx, eax
0x18000a0fd  test    eax, eax
0x18000a0ff  jns     short loc_18000A15C
0x18000a101  and     eax, 1FFF0000h
0x18000a106  cmp     eax, 70000h
0x18000a10b  jnz     loc_180009F41
0x18000a111  movzx   ecx, cx
0x18000a114  jmp     loc_180009F41
0x18000a119  mov     [r14], eax
0x18000a11c  mov     ecx, 7Ah ; 'z'
0x18000a121  jmp     loc_180009F41
0x18000a126  cmp     cx, 7Ah ; 'z'
0x18000a12a  ja      loc_180009F3C
0x18000a130  jmp     loc_180009E82
0x18000a135  mov     r10, [rsp+1F8h+var_120]
0x18000a13d  lea     rdx, [rsp+1F8h+var_1C4]
0x18000a142  mov     rcx, r10
0x18000a145  call    ??$IsPublisherValid@GPEBG@ReservedForLocalUse@@YA_NPEBGAEAI@Z; ReservedForLocalUse::IsPublisherValid<ushort,ushort const *>(ushort const *,uint &)
0x18000a14a  test    al, al
0x18000a14c  jz      loc_180009F3C
0x18000a152  mov     r11d, [rsp+1F8h+var_1C4]
0x18000a157  jmp     loc_180009FF3
0x18000a15c  mov     edi, [rsp+1F8h+var_1C8]
0x18000a160  jmp     loc_18000A022
```
