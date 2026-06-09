# NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x180006b60`
- end: `0x180006f92`
- name: `?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z`
- size: `1074`
- prototype: `int(NgcUtils *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `7`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180056438`
- `0x180057350`
- `0x18008b900`
- `0x18008c4a4`
- `0x18008c5ac`
- `0x18008c740`
- `0x18008ca54`

## callees

- `0x180006b60`
- `0x18000782c`
- `0x1800164b0`
- `0x180048304`
- `0x180062abc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006c53`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006cca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006e8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006eb7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006ee5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006f70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006c53`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006cca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006e8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006eb7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006ee5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006f70`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006bb7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006d70`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006bb7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006d70`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180006b97`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180006c9e`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180006b97`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180006c9e`

## string_xrefs

- `0x180006c28`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x180006e77`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x180006e9e`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x180006f59`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x180006bce`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x180006c3c`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x180006cb1`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x180006f0c`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x180006f3b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall NgcUtils::GetNgcStateSeparatedRegistryLocation(
        NgcUtils *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  int PersistedRegistryLocationW; // eax
  unsigned int v9; // ebx
  _BYTE *v10; // rax
  void *v11; // rdi
  __int64 v13; // r8
  _WORD *v14; // rax
  __int64 v15; // rcx
  unsigned int v16; // esi
  __int64 v17; // rdx
  _BYTE *i; // rcx
  unsigned int v19; // eax
  unsigned int v20; // ebx
  const unsigned __int16 *v21; // rbx
  const unsigned __int16 *v22; // rax
  const char *v23; // r9
  __int64 v24; // rdx
  const unsigned __int16 *v25; // rax
  unsigned __int64 v26; // rbp
  _WORD *v27; // r14
  __int64 v28; // r10
  _WORD *v29; // rdx
  __int64 v30; // rcx
  unsigned __int64 v31; // r8
  _WORD *v32; // r9
  _WORD *v33; // rcx
  unsigned __int64 v34; // rcx
  _WORD *v35; // rax
  _WORD *v36; // r8
  unsigned __int64 v37; // rdx
  _WORD *v38; // rcx
  _WORD *v39; // rbx
  int v40; // eax
  int v41; // [rsp+20h] [rbp-38h]
  unsigned int uBytes[10]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  uBytes[0] = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(this, a2, 0, 0);
  v9 = PersistedRegistryLocationW;
  if ( PersistedRegistryLocationW == 234 )
  {
    v10 = LocalAlloc(0, uBytes[0]);
    v11 = v10;
    if ( !v10 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB9,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
        (const char *)0x8007000ELL,
        (int)uBytes);
      return 2147942414LL;
    }
    for ( i = &v10[uBytes[0]]; v10 != i; ++v10 )
      *v10 = 0;
    v19 = GetPersistedRegistryLocationW(this, a2, v11, uBytes[0]);
    if ( v19 )
    {
      v20 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xC0,
              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
              (const char *)v19,
              (unsigned int)uBytes);
      LocalFree(v11);
      return v20;
    }
    if ( !a3 )
    {
      *(_QWORD *)a4 = v11;
      return 0;
    }
    v13 = 260;
    v14 = v11;
    v15 = 260;
    while ( *v14 )
    {
      ++v14;
      if ( !--v15 )
      {
        v16 = -2147024809;
        v17 = 179;
        goto LABEL_9;
      }
    }
    v21 = L"\\";
    v22 = L"\\";
    v23 = (const char *)(260 - v15);
    v24 = 260;
    while ( *v22 )
    {
      ++v22;
      if ( !--v24 )
      {
        v16 = -2147024809;
        v17 = 185;
        goto LABEL_9;
      }
    }
    v25 = a3;
    while ( *v25 )
    {
      ++v25;
      if ( !--v13 )
      {
        v16 = -2147024809;
        v17 = 191;
        goto LABEL_9;
      }
    }
    v26 = (unsigned __int64)&v23[260 - v24 - v13 + 261];
    if ( v26 == -1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF89,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v23);
    v27 = LocalAlloc(0, 2 * v26 + 2);
    if ( !v27 )
    {
      v16 = -2147024882;
      v17 = 199;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
        (const char *)v16,
        (int)uBytes);
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC9,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
        (const char *)v16,
        v41);
      LocalFree(v11);
      return v16;
    }
    *v27 = 0;
    v27[v26] = 0;
    if ( v26 )
    {
      if ( v26 > 0x7FFFFFFF )
      {
        v16 = -2147024809;
        *v27 = 0;
      }
      else
      {
        v28 = 2147483646;
        v29 = v11;
        v30 = 2147483646;
        v31 = v26;
        v32 = v27;
        do
        {
          if ( !v30 )
            break;
          if ( !*v29 )
            break;
          *v32++ = *v29++;
          --v30;
          --v31;
        }
        while ( v31 );
        v33 = v32 - 1;
        v16 = -2147024774;
        if ( v31 )
        {
          v33 = v32;
          v16 = 0;
        }
        *v33 = 0;
        if ( v31 )
        {
          v34 = v26;
          v35 = v27;
          do
          {
            if ( !*v35 )
              break;
            ++v35;
            --v34;
          }
          while ( v34 );
          v16 = -2147024809;
          if ( !v34 )
            goto LABEL_49;
          v36 = &v27[v26 - v34];
          v37 = v34;
          if ( v26 != v26 - v34 )
          {
            do
            {
              if ( !v28 )
                break;
              if ( !*v21 )
                break;
              *v36++ = *v21++;
              --v28;
              --v37;
            }
            while ( v37 );
          }
          v38 = v36 - 1;
          v16 = -2147024774;
          if ( v37 )
          {
            v38 = v36;
            v16 = 0;
          }
          *v38 = 0;
          if ( !v37 )
          {
LABEL_49:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xD2,
              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
              (const char *)v16,
              (int)uBytes);
            LocalFree(v27);
            goto LABEL_10;
          }
          v40 = StringCchCatW(v27, v26, a3);
          v16 = v40;
          if ( v40 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xD7,
              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
              (const char *)(unsigned int)v40,
              (int)uBytes);
            LocalFree(v27);
            goto LABEL_10;
          }
          v39 = v27;
          goto LABEL_54;
        }
      }
    }
    else
    {
      v16 = -2147024809;
    }
    v39 = 0;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCD,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
      (const char *)v16,
      (int)uBytes);
    LocalFree(v27);
    if ( (v16 & 0x80000000) != 0 )
      goto LABEL_10;
LABEL_54:
    *(_QWORD *)a4 = v39;
    LocalFree(v11);
    return 0;
  }
  if ( PersistedRegistryLocationW > 0 )
    v9 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
  if ( (v9 & 0x80000000) != 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB6,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
      (const char *)v9,
      (int)uBytes);
  return v9;
}

```

## disassembly

```asm
0x180006b60  mov     [rsp+arg_10], rbx
0x180006b65  mov     [rsp+arg_18], rbp
0x180006b6a  push    rsi
0x180006b6b  push    r12
0x180006b6d  push    r15
0x180006b6f  sub     rsp, 40h
0x180006b73  mov     r12, r9
0x180006b76  mov     [rsp+58h+uBytes], 0
0x180006b7e  mov     r15, r8
0x180006b81  lea     rax, [rsp+58h+uBytes]
0x180006b86  xor     r9d, r9d
0x180006b89  mov     qword ptr [rsp+58h+var_38], rax; int
0x180006b8e  xor     r8d, r8d
0x180006b91  mov     rsi, rdx
0x180006b94  mov     rbp, rcx
0x180006b97  call    cs:__imp_GetPersistedRegistryLocationW
0x180006b9d  mov     ebx, eax
0x180006b9f  cmp     eax, 0EAh
0x180006ba4  jnz     loc_180006D06
0x180006baa  mov     ebx, [rsp+58h+uBytes]
0x180006bae  xor     ecx, ecx; uFlags
0x180006bb0  mov     edx, ebx; uBytes
0x180006bb2  mov     [rsp+58h+arg_0], rdi
0x180006bb7  call    cs:__imp_LocalAlloc
0x180006bbd  mov     rdi, rax
0x180006bc0  test    rax, rax
0x180006bc3  jnz     loc_180006C79
0x180006bc9  mov     rcx, [rsp+58h]; this
0x180006bce  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180006bd5  mov     esi, 8007000Eh
0x180006bda  mov     edx, 0B9h; void *
0x180006bdf  mov     r9d, esi; char *
0x180006be2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006be7  mov     eax, esi
0x180006be9  jmp     short loc_180006C60
0x180006beb  mov     [rsp+58h+arg_8], r14
0x180006bf0  test    r15, r15
0x180006bf3  jz      loc_180006F01
0x180006bf9  mov     r8d, 104h
0x180006bff  mov     rax, rdi
0x180006c02  mov     ecx, r8d
0x180006c05  cmp     word ptr [rax], 0
0x180006c09  jz      loc_180006CD4
0x180006c0f  add     rax, 2
0x180006c13  sub     rcx, 1
0x180006c17  jnz     short loc_180006C05
0x180006c19  mov     esi, 80070057h
0x180006c1e  mov     edx, 0B3h; void *
0x180006c23  mov     rcx, [rsp+58h]; this
0x180006c28  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180006c2f  mov     r9d, esi; char *
0x180006c32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006c37  mov     rcx, [rsp+58h]; this
0x180006c3c  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180006c43  mov     r9d, esi; char *
0x180006c46  mov     edx, 0C9h; void *
0x180006c4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006c50  mov     rcx, rdi; hMem
0x180006c53  call    cs:__imp_LocalFree
0x180006c59  mov     eax, esi
0x180006c5b  mov     r14, [rsp+58h+arg_8]
0x180006c60  mov     rdi, [rsp+58h+arg_0]
0x180006c65  mov     rbx, [rsp+58h+arg_10]
0x180006c6a  mov     rbp, [rsp+58h+arg_18]
0x180006c6f  add     rsp, 40h
0x180006c73  pop     r15
0x180006c75  pop     r12
0x180006c77  pop     rsi
0x180006c78  retn
0x180006c79  lea     rcx, [rbx+rax]
0x180006c7d  cmp     rdi, rcx
0x180006c80  jnz     loc_180006F25
0x180006c86  mov     r9d, [rsp+58h+uBytes]
0x180006c8b  lea     rax, [rsp+58h+uBytes]
0x180006c90  mov     r8, rdi
0x180006c93  mov     qword ptr [rsp+58h+var_38], rax; int
0x180006c98  mov     rdx, rsi
0x180006c9b  mov     rcx, rbp
0x180006c9e  call    cs:__imp_GetPersistedRegistryLocationW
0x180006ca4  test    eax, eax
0x180006ca6  jz      loc_180006BEB
0x180006cac  mov     rcx, [rsp+58h]; this
0x180006cb1  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180006cb8  mov     r9d, eax; char *
0x180006cbb  mov     edx, 0C0h; void *
0x180006cc0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180006cc5  mov     rcx, rdi; hMem
0x180006cc8  mov     ebx, eax
0x180006cca  call    cs:__imp_LocalFree
0x180006cd0  mov     eax, ebx
0x180006cd2  jmp     short loc_180006C60
0x180006cd4  lea     rbx, asc_1800DB4FC; "\\"
0x180006cdb  mov     r9, r8
0x180006cde  mov     rax, rbx
0x180006ce1  sub     r9, rcx; char *
0x180006ce4  mov     rdx, r8
0x180006ce7  cmp     word ptr [rax], 0
0x180006ceb  jz      short loc_180006D22
0x180006ced  add     rax, 2
0x180006cf1  sub     rdx, 1
0x180006cf5  jnz     short loc_180006CE7
0x180006cf7  mov     esi, 80070057h
0x180006cfc  mov     edx, 0B9h
0x180006d01  jmp     loc_180006C23
0x180006d06  test    eax, eax
0x180006d08  jle     short loc_180006D13
0x180006d0a  movzx   ebx, ax
0x180006d0d  or      ebx, 80070000h
0x180006d13  test    ebx, ebx
0x180006d15  js      loc_180006F07
0x180006d1b  mov     eax, ebx
0x180006d1d  jmp     loc_180006C65
0x180006d22  mov     rcx, r8
0x180006d25  mov     rax, r15
0x180006d28  sub     rcx, rdx
0x180006d2b  nop     dword ptr [rax+rax+00h]
0x180006d30  cmp     word ptr [rax], 0
0x180006d34  jz      short loc_180006D4F
0x180006d36  add     rax, 2
0x180006d3a  sub     r8, 1
0x180006d3e  jnz     short loc_180006D30
0x180006d40  mov     esi, 80070057h
0x180006d45  mov     edx, 0BFh
0x180006d4a  jmp     loc_180006C23
0x180006d4f  sub     rcx, r8
0x180006d52  lea     rbp, [rcx+105h]
0x180006d59  add     rbp, r9
0x180006d5c  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x180006d60  jz      loc_180006F36
0x180006d66  lea     rdx, ds:2[rbp*2]; uBytes
0x180006d6e  xor     ecx, ecx; uFlags
0x180006d70  call    cs:__imp_LocalAlloc
0x180006d76  mov     r14, rax
0x180006d79  test    rax, rax
0x180006d7c  jz      loc_180006EF2
0x180006d82  xor     eax, eax
0x180006d84  mov     [r14], ax
0x180006d88  mov     [r14+rbp*2], ax
0x180006d8d  test    rbp, rbp
0x180006d90  jz      loc_180006F7B
0x180006d96  cmp     rbp, 7FFFFFFFh
0x180006d9d  ja      loc_180006F4D
0x180006da3  mov     r10d, 7FFFFFFEh
0x180006da9  mov     rdx, rdi
0x180006dac  mov     ecx, r10d
0x180006daf  mov     r8, rbp
0x180006db2  mov     r9, r14
0x180006db5  test    rcx, rcx
0x180006db8  jz      short loc_180006DD7
0x180006dba  movzx   eax, word ptr [rdx]
0x180006dbd  test    ax, ax
0x180006dc0  jz      short loc_180006DD7
0x180006dc2  mov     [r9], ax
0x180006dc6  add     rdx, 2
0x180006dca  add     r9, 2
0x180006dce  dec     rcx
0x180006dd1  sub     r8, 1
0x180006dd5  jnz     short loc_180006DB5
0x180006dd7  test    r8, r8
0x180006dda  lea     rcx, [r9-2]
0x180006dde  mov     esi, 8007007Ah
0x180006de3  cmovnz  rcx, r9
0x180006de7  xor     eax, eax
0x180006de9  test    r8, r8
0x180006dec  cmovnz  esi, eax
0x180006def  mov     [rcx], ax
0x180006df2  jz      loc_180006E99
0x180006df8  mov     rcx, rbp
0x180006dfb  mov     rax, r14
0x180006dfe  xchg    ax, ax
0x180006e00  cmp     word ptr [rax], 0
0x180006e04  jz      short loc_180006E10
0x180006e06  add     rax, 2
0x180006e0a  sub     rcx, 1
0x180006e0e  jnz     short loc_180006E00
0x180006e10  xor     eax, eax
0x180006e12  mov     esi, 80070057h
0x180006e17  test    rcx, rcx
0x180006e1a  cmovnz  esi, eax
0x180006e1d  jz      short loc_180006E72
0x180006e1f  mov     rax, rbp
0x180006e22  sub     rax, rcx
0x180006e25  test    rcx, rcx
0x180006e28  jz      short loc_180006E72
0x180006e2a  mov     rdx, rbp
0x180006e2d  lea     r8, [r14+rax*2]
0x180006e31  sub     rdx, rax
0x180006e34  jz      short loc_180006E58
0x180006e36  test    r10, r10
0x180006e39  jz      short loc_180006E58
0x180006e3b  movzx   eax, word ptr [rbx]
0x180006e3e  test    ax, ax
0x180006e41  jz      short loc_180006E58
0x180006e43  mov     [r8], ax
0x180006e47  add     rbx, 2
0x180006e4b  add     r8, 2
0x180006e4f  dec     r10
0x180006e52  sub     rdx, 1
0x180006e56  jnz     short loc_180006E36
0x180006e58  xor     eax, eax
0x180006e5a  lea     rcx, [r8-2]
0x180006e5e  test    rdx, rdx
0x180006e61  mov     esi, 8007007Ah
0x180006e66  cmovnz  rcx, r8
0x180006e6a  cmovnz  esi, eax
0x180006e6d  mov     [rcx], ax
0x180006e70  jnz     short loc_180006EC7
0x180006e72  mov     rcx, [rsp+58h]; this
0x180006e77  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180006e7e  mov     r9d, esi; char *
0x180006e81  mov     edx, 0D2h; void *
0x180006e86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006e8b  mov     rcx, r14; hMem
0x180006e8e  call    cs:__imp_LocalFree
0x180006e94  jmp     loc_180006C37
0x180006e99  mov     rcx, [rsp+58h]; this
0x180006e9e  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180006ea5  mov     r9d, esi; char *
0x180006ea8  mov     edx, 0CDh; void *
0x180006ead  xor     ebx, ebx
0x180006eaf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006eb4  mov     rcx, r14; hMem
0x180006eb7  call    cs:__imp_LocalFree
0x180006ebd  test    esi, esi
0x180006ebf  js      loc_180006C37
0x180006ec5  jmp     short loc_180006EDE
0x180006ec7  mov     r8, r15; unsigned __int16 *
0x180006eca  mov     rdx, rbp; unsigned __int64
0x180006ecd  mov     rcx, r14; unsigned __int16 *
0x180006ed0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006ed5  mov     esi, eax
0x180006ed7  test    eax, eax
0x180006ed9  js      short loc_180006F54
0x180006edb  mov     rbx, r14
0x180006ede  mov     rcx, rdi; hMem
0x180006ee1  mov     [r12], rbx
0x180006ee5  call    cs:__imp_LocalFree
0x180006eeb  xor     eax, eax
0x180006eed  jmp     loc_180006C5B
0x180006ef2  mov     esi, 8007000Eh
0x180006ef7  mov     edx, 0C7h
0x180006efc  jmp     loc_180006C23
0x180006f01  mov     [r12], rdi
0x180006f05  jmp     short loc_180006EEB
0x180006f07  mov     rcx, [rsp+58h]; this
0x180006f0c  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180006f13  mov     r9d, ebx; char *
0x180006f16  mov     edx, 0B6h; void *
0x180006f1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006f20  jmp     loc_180006D1B
0x180006f25  xor     edx, edx
0x180006f27  mov     [rax], dl
0x180006f29  inc     rax
0x180006f2c  cmp     rax, rcx
0x180006f2f  jnz     short loc_180006F25
0x180006f31  jmp     loc_180006C86
0x180006f36  mov     rcx, [rsp+58h]; this
0x180006f3b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006f42  mov     edx, 0F89h; void *
0x180006f47  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180006f4d  mov     esi, 80070057h
0x180006f52  jmp     short loc_180006F89
0x180006f54  mov     rcx, [rsp+58h]; this
0x180006f59  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180006f60  mov     r9d, eax; char *
0x180006f63  mov     edx, 0D7h; void *
0x180006f68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006f6d  mov     rcx, r14; hMem
0x180006f70  call    cs:__imp_LocalFree
0x180006f76  jmp     loc_180006C37
0x180006f7b  mov     esi, 80070057h
0x180006f80  test    rbp, rbp
0x180006f83  jz      loc_180006E99
0x180006f89  mov     [r14], ax
0x180006f8d  jmp     loc_180006E99
```
