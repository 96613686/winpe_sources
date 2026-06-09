# Microsoft::Resources::ContrastQualifierType::Evaluate(Microsoft::Resources::IQualifier const *,ushort const *,double *)

- ea: `0x18006d030`
- end: `0x18006d24f`
- name: `?Evaluate@ContrastQualifierType@Resources@Microsoft@@UEBAJPEBVIQualifier@23@PEBGPEAN@Z`
- size: `543`
- prototype: `int(Microsoft::Resources::ContrastQualifierType *__hidden this, const struct Microsoft::Resources::IQualifier *, const unsigned __int16 *, double *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180017960`
- `0x18002c8d0`
- `0x18002cfd0`
- `0x18006d030`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006d108`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006d126`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006d18a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006d1a8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006d1ca`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006d1e8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006d233`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006d108`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006d126`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006d18a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006d1a8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006d1ca`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006d1e8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006d233`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::ContrastQualifierType::Evaluate(
        Microsoft::Resources::ContrastQualifierType *this,
        const struct Microsoft::Resources::IQualifier *a2,
        const unsigned __int16 *a3,
        double *a4)
{
  __int64 v8; // rax
  int v9; // eax
  unsigned int v10; // ebx
  const WCHAR *v11; // rcx
  int v12; // eax
  const WCHAR *v13; // rbx
  double v14; // xmm0_8
  __int64 v16; // rdx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-58h]
  _BYTE *v18; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v19[64]; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  *a4 = 0.0;
  DefStringResult_InitBuf(v19);
  v8 = *(_QWORD *)this;
  v18 = v19;
  v9 = (*(__int64 (__fastcall **)(Microsoft::Resources::ContrastQualifierType *))(v8 + 16))(this);
  v10 = v9;
  if ( v9 < 0 )
  {
    v16 = 33;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\corequalifiertypes.cpp",
      (const char *)(unsigned int)v9,
      bIgnoreCase);
    goto LABEL_16;
  }
  v9 = (*(__int64 (__fastcall **)(Microsoft::Resources::ContrastQualifierType *, const unsigned __int16 *))(*(_QWORD *)this + 8LL))(
         this,
         a3);
  v10 = v9;
  if ( v9 < 0 )
  {
    v16 = 34;
    goto LABEL_19;
  }
  v9 = (*(__int64 (__fastcall **)(const struct Microsoft::Resources::IQualifier *, _BYTE **))(*(_QWORD *)a2 + 56LL))(
         a2,
         &v18);
  v10 = v9;
  if ( v9 < 0 )
  {
    v16 = 35;
    goto LABEL_19;
  }
  if ( v18 && (*(_QWORD *)v18 || !*((_DWORD *)v18 + 2)) && (*((_DWORD *)v18 + 2) || !*(_QWORD *)v18) )
  {
    v11 = (const WCHAR *)*((_QWORD *)v18 + 2);
    v12 = 0;
  }
  else
  {
    v11 = 0;
    v12 = -2147024809;
  }
  v13 = 0;
  if ( v12 >= 0 )
    v13 = v11;
  if ( CompareStringOrdinal(a3, -1, v13, -1, 1) == 2 )
  {
    v14 = DOUBLE_1_0;
  }
  else
  {
    if ( CompareStringOrdinal(L"standard", -1, a3, -1, 1) != 2 && CompareStringOrdinal(L"standard", -1, v13, -1, 1) != 2 )
    {
      if ( CompareStringOrdinal(L"high", -1, v13, -1, 1) == 2 )
        goto LABEL_29;
      if ( CompareStringOrdinal(L"white", -1, v13, -1, 1) == 2 || CompareStringOrdinal(L"white", -1, a3, -1, 1) == 2 )
      {
        v14 = DOUBLE_0_1;
        goto LABEL_15;
      }
      if ( CompareStringOrdinal(L"black", -1, v13, -1, 1) == 2 )
      {
LABEL_29:
        v14 = DOUBLE_0_5;
        goto LABEL_15;
      }
    }
    v14 = 0.0;
  }
LABEL_15:
  *a4 = v14;
  v10 = 0;
LABEL_16:
  Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v18);
  return v10;
}

```

## disassembly

```asm
0x18006d030  push    rbx
0x18006d032  push    rbp
0x18006d033  push    rsi
0x18006d034  push    rdi
0x18006d035  push    r14
0x18006d037  sub     rsp, 50h
0x18006d03b  mov     rdi, rcx
0x18006d03e  mov     qword ptr [r9], 0
0x18006d045  lea     rcx, [rsp+78h+var_40]
0x18006d04a  mov     r14, r9
0x18006d04d  mov     rbp, r8
0x18006d050  mov     rsi, rdx
0x18006d053  call    DefStringResult_InitBuf
0x18006d058  mov     rax, [rdi]
0x18006d05b  lea     rcx, [rsp+78h+var_40]
0x18006d060  mov     [rsp+78h+var_48], rcx
0x18006d065  mov     rcx, rdi
0x18006d068  mov     rax, [rax+10h]
0x18006d06c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d071  mov     ebx, eax
0x18006d073  test    eax, eax
0x18006d075  js      loc_18006D15C
0x18006d07b  mov     rax, [rdi]
0x18006d07e  mov     rdx, rbp
0x18006d081  mov     rcx, rdi
0x18006d084  mov     rax, [rax+8]
0x18006d088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d08d  mov     ebx, eax
0x18006d08f  test    eax, eax
0x18006d091  js      loc_18006D216
0x18006d097  mov     rax, [rsi]
0x18006d09a  lea     rdx, [rsp+78h+var_48]
0x18006d09f  mov     rcx, rsi
0x18006d0a2  mov     rax, [rax+38h]
0x18006d0a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d0ab  mov     ebx, eax
0x18006d0ad  test    eax, eax
0x18006d0af  js      loc_18006D20C
0x18006d0b5  mov     rax, [rsp+78h+var_48]
0x18006d0ba  test    rax, rax
0x18006d0bd  jz      loc_18006D200
0x18006d0c3  cmp     qword ptr [rax], 0
0x18006d0c7  jnz     short loc_18006D0D3
0x18006d0c9  cmp     dword ptr [rax+8], 0
0x18006d0cd  ja      loc_18006D200
0x18006d0d3  cmp     dword ptr [rax+8], 0
0x18006d0d7  jnz     short loc_18006D0E3
0x18006d0d9  cmp     qword ptr [rax], 0
0x18006d0dd  jnz     loc_18006D200
0x18006d0e3  mov     rcx, [rax+10h]
0x18006d0e7  xor     eax, eax
0x18006d0e9  xor     ebx, ebx
0x18006d0eb  mov     esi, 1
0x18006d0f0  test    eax, eax
0x18006d0f2  mov     [rsp+78h+bIgnoreCase], esi; bIgnoreCase
0x18006d0f6  cmovns  rbx, rcx
0x18006d0fa  or      edi, 0FFFFFFFFh
0x18006d0fd  mov     r9d, edi; cchCount2
0x18006d100  mov     edx, edi; cchCount1
0x18006d102  mov     r8, rbx; lpString2
0x18006d105  mov     rcx, rbp; lpString1
0x18006d108  call    cs:__imp_CompareStringOrdinal
0x18006d10e  cmp     eax, 2
0x18006d111  jz      short loc_18006D152
0x18006d113  mov     r9d, edi; cchCount2
0x18006d116  mov     [rsp+78h+bIgnoreCase], esi; bIgnoreCase
0x18006d11a  mov     r8, rbp; lpString2
0x18006d11d  lea     rcx, aStandard; "standard"
0x18006d124  mov     edx, edi; cchCount1
0x18006d126  call    cs:__imp_CompareStringOrdinal
0x18006d12c  cmp     eax, 2
0x18006d12f  jnz     short loc_18006D177
0x18006d131  xorps   xmm0, xmm0
0x18006d134  movsd   qword ptr [r14], xmm0
0x18006d139  xor     ebx, ebx
0x18006d13b  lea     rcx, [rsp+78h+var_48]; this
0x18006d140  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x18006d145  mov     eax, ebx
0x18006d147  add     rsp, 50h
0x18006d14b  pop     r14
0x18006d14d  pop     rdi
0x18006d14e  pop     rsi
0x18006d14f  pop     rbp
0x18006d150  pop     rbx
0x18006d151  retn
0x18006d152  movsd   xmm0, cs:__real@3ff0000000000000
0x18006d15a  jmp     short loc_18006D134
0x18006d15c  mov     edx, 21h ; '!'; void *
0x18006d161  mov     rcx, [rsp+78h]; this
0x18006d166  lea     r8, aMinkernelMrtMr_15; "minkernel\\mrt\\mrm\\mrmmin\\corequalif"...
0x18006d16d  mov     r9d, eax; char *
0x18006d170  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006d175  jmp     short loc_18006D13B
0x18006d177  mov     r9d, edi; cchCount2
0x18006d17a  mov     [rsp+78h+bIgnoreCase], esi; bIgnoreCase
0x18006d17e  mov     r8, rbx; lpString2
0x18006d181  lea     rcx, aStandard; "standard"
0x18006d188  mov     edx, edi; cchCount1
0x18006d18a  call    cs:__imp_CompareStringOrdinal
0x18006d190  cmp     eax, 2
0x18006d193  jz      short loc_18006D131
0x18006d195  mov     r9d, edi; cchCount2
0x18006d198  mov     [rsp+78h+bIgnoreCase], esi; bIgnoreCase
0x18006d19c  mov     r8, rbx; lpString2
0x18006d19f  lea     rcx, aHigh; "high"
0x18006d1a6  mov     edx, edi; cchCount1
0x18006d1a8  call    cs:__imp_CompareStringOrdinal
0x18006d1ae  cmp     eax, 2
0x18006d1b1  jz      loc_18006D242
0x18006d1b7  mov     r9d, edi; cchCount2
0x18006d1ba  mov     [rsp+78h+bIgnoreCase], esi; bIgnoreCase
0x18006d1be  mov     r8, rbx; lpString2
0x18006d1c1  lea     rcx, aWhite; "white"
0x18006d1c8  mov     edx, edi; cchCount1
0x18006d1ca  call    cs:__imp_CompareStringOrdinal
0x18006d1d0  cmp     eax, 2
0x18006d1d3  jz      short loc_18006D1F3
0x18006d1d5  mov     r9d, edi; cchCount2
0x18006d1d8  mov     [rsp+78h+bIgnoreCase], esi; bIgnoreCase
0x18006d1dc  mov     r8, rbp; lpString2
0x18006d1df  lea     rcx, aWhite; "white"
0x18006d1e6  mov     edx, edi; cchCount1
0x18006d1e8  call    cs:__imp_CompareStringOrdinal
0x18006d1ee  cmp     eax, 2
0x18006d1f1  jnz     short loc_18006D220
0x18006d1f3  movsd   xmm0, cs:__real@3fb999999999999a
0x18006d1fb  jmp     loc_18006D134
0x18006d200  xor     ecx, ecx
0x18006d202  mov     eax, 80070057h
0x18006d207  jmp     loc_18006D0E9
0x18006d20c  mov     edx, 23h ; '#'
0x18006d211  jmp     loc_18006D161
0x18006d216  mov     edx, 22h ; '"'
0x18006d21b  jmp     loc_18006D161
0x18006d220  mov     r9d, edi; cchCount2
0x18006d223  mov     [rsp+78h+bIgnoreCase], esi; bIgnoreCase
0x18006d227  mov     r8, rbx; lpString2
0x18006d22a  lea     rcx, aBlack; "black"
0x18006d231  mov     edx, edi; cchCount1
0x18006d233  call    cs:__imp_CompareStringOrdinal
0x18006d239  cmp     eax, 2
0x18006d23c  jnz     loc_18006D131
0x18006d242  movsd   xmm0, cs:__real@3fe0000000000000
0x18006d24a  jmp     loc_18006D134
```
