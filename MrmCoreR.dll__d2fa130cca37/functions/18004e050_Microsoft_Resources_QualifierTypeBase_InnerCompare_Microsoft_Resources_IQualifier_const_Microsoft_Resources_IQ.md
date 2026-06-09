# Microsoft::Resources::QualifierTypeBase::InnerCompare(Microsoft::Resources::IQualifier const *,Microsoft::Resources::IQualifier const *,_DEFCOMPARISON *)

- ea: `0x18004e050`
- end: `0x18004e2d7`
- name: `?InnerCompare@QualifierTypeBase@Resources@Microsoft@@MEBAJPEBVIQualifier@23@0PEAW4_DEFCOMPARISON@@@Z`
- size: `647`
- prototype: `__int64 __fastcall(Microsoft::Resources::QualifierTypeBase *__hidden this, const struct Microsoft::Resources::IQualifier *, const struct Microsoft::Resources::IQualifier *, enum _DEFCOMPARISON *)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18004deb0`
- `0x1800a6c80`
- `0x1800ba3b0`
- `0x1800bad50`

## callees

- `0x18002c8d0`
- `0x18002cfd0`
- `0x18004e050`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e207`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e279`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e299`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e207`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e279`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e299`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e215`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e287`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e2a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e215`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e287`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e2a7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004e14d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004e14d`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::QualifierTypeBase::InnerCompare(
        Microsoft::Resources::QualifierTypeBase *this,
        const struct Microsoft::Resources::IQualifier *a2,
        const struct Microsoft::Resources::IQualifier *a3,
        enum _DEFCOMPARISON *a4)
{
  __int64 v5; // rax
  int (__fastcall *v7)(const struct Microsoft::Resources::IQualifier *, LPVOID **); // rax
  LPVOID *v8; // rcx
  const WCHAR *v9; // r8
  const WCHAR *v10; // rcx
  int v11; // ebx
  int v12; // eax
  void *v13; // rbx
  void *v14; // rbx
  void *v16; // rbx
  HANDLE v17; // rax
  HANDLE v18; // rax
  HANDLE ProcessHeap; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-58h]
  LPVOID *v21; // [rsp+30h] [rbp-48h] BYREF
  LPVOID v22; // [rsp+38h] [rbp-40h] BYREF
  int v23; // [rsp+40h] [rbp-38h]
  __int64 v24; // [rsp+48h] [rbp-30h]
  LPVOID *p_lpMem; // [rsp+50h] [rbp-28h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-20h] BYREF
  int v27; // [rsp+60h] [rbp-18h]
  __int64 v28; // [rsp+68h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  p_lpMem = &lpMem;
  *(_DWORD *)a4 = 0;
  v21 = &v22;
  v5 = *(_QWORD *)a2;
  lpMem = 0;
  v27 = 0;
  v28 = 0;
  v7 = *(int (__fastcall **)(const struct Microsoft::Resources::IQualifier *, LPVOID **))(v5 + 56);
  v22 = 0;
  v23 = 0;
  v24 = 0;
  if ( v7(a2, &p_lpMem) < 0
    || (*(int (__fastcall **)(const struct Microsoft::Resources::IQualifier *, LPVOID **))(*(_QWORD *)a3 + 56LL))(
         a3,
         &v21) < 0 )
  {
    v16 = v22;
    if ( (v22 || !v23) && (v23 || !v22) )
    {
      v24 = 0;
      if ( v22 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v16);
        v22 = 0;
        v23 = 0;
      }
    }
    v14 = lpMem;
    if ( !lpMem && v27 )
      return 0;
    if ( !v27 && lpMem )
      return 0;
    v28 = 0;
    if ( !lpMem )
      return 0;
LABEL_41:
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v14);
    return 0;
  }
  v8 = v21;
  *(_DWORD *)a4 = 0x7FFFFFFF;
  if ( v8 && (*v8 || !*((_DWORD *)v8 + 2)) && (*((_DWORD *)v8 + 2) || !*v8) )
  {
    if ( p_lpMem && (*p_lpMem || !*((_DWORD *)p_lpMem + 2)) && (*((_DWORD *)p_lpMem + 2) || !*p_lpMem) )
    {
      v9 = (const WCHAR *)v8[2];
      v10 = (const WCHAR *)p_lpMem[2];
      if ( v10 )
      {
        if ( v9 )
        {
          v11 = -1;
          v12 = CompareStringOrdinal(v10, -1, v9, -1, 1) - 2;
          if ( v12 == 0x7FFFFFFF )
          {
            v11 = 0x7FFFFFFF;
          }
          else if ( v12 >= 0 )
          {
            v11 = v12 > 0;
          }
        }
        else
        {
          v11 = 1;
        }
      }
      else
      {
        v11 = -(v9 != 0);
      }
      *(_DWORD *)a4 = v11;
      v13 = v22;
      if ( (v22 || !v23) && (v23 || !v22) )
      {
        v24 = 0;
        if ( v22 )
        {
          v18 = GetProcessHeap();
          HeapFree(v18, 0, v13);
          v22 = 0;
          v23 = 0;
        }
      }
      v14 = lpMem;
      if ( !lpMem && v27 )
        return 0;
      if ( !v27 && lpMem )
        return 0;
      v28 = 0;
      if ( !lpMem )
        return 0;
      goto LABEL_41;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE1,
      (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\stringresult.cpp",
      (const char *)0x80070057LL,
      bIgnoreCase);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x102,
    (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\basequalifiertypes.cpp",
    (const char *)0x80070057LL,
    bIgnoreCase);
  Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v21);
  Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&p_lpMem);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18004e050  push    rbp
0x18004e052  push    rbx
0x18004e053  push    rsi
0x18004e054  push    rdi
0x18004e055  mov     rbp, rsp
0x18004e058  sub     rsp, 78h
0x18004e05c  xor     esi, esi
0x18004e05e  lea     rax, [rbp+lpMem]
0x18004e062  mov     [rbp+var_28], rax
0x18004e066  mov     rcx, rdx
0x18004e069  lea     rax, [rbp+var_40]
0x18004e06d  mov     [r9], esi
0x18004e070  mov     [rbp+var_48], rax
0x18004e074  mov     rdi, r9
0x18004e077  mov     rax, [rdx]
0x18004e07a  mov     rbx, r8
0x18004e07d  lea     rdx, [rbp+var_28]
0x18004e081  mov     [rbp+lpMem], rsi
0x18004e085  mov     [rbp+var_18], esi
0x18004e088  mov     [rbp+var_10], rsi
0x18004e08c  mov     rax, [rax+38h]
0x18004e090  mov     [rbp+var_40], rsi
0x18004e094  mov     [rbp+var_38], esi
0x18004e097  mov     [rbp+var_30], rsi
0x18004e09b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e0a0  test    eax, eax
0x18004e0a2  js      loc_18004E1BF
0x18004e0a8  mov     rax, [rbx]
0x18004e0ab  lea     rdx, [rbp+var_48]
0x18004e0af  mov     rcx, rbx
0x18004e0b2  mov     rax, [rax+38h]
0x18004e0b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e0bb  test    eax, eax
0x18004e0bd  js      loc_18004E1BF
0x18004e0c3  mov     rcx, [rbp+var_48]
0x18004e0c7  mov     dword ptr [rdi], 7FFFFFFFh
0x18004e0cd  test    rcx, rcx
0x18004e0d0  jz      loc_18004E227
0x18004e0d6  mov     rdx, [rcx]
0x18004e0d9  test    rdx, rdx
0x18004e0dc  jnz     short loc_18004E0E7
0x18004e0de  cmp     [rcx+8], esi
0x18004e0e1  ja      loc_18004E227
0x18004e0e7  cmp     [rcx+8], esi
0x18004e0ea  jnz     short loc_18004E0F5
0x18004e0ec  test    rdx, rdx
0x18004e0ef  jnz     loc_18004E227
0x18004e0f5  mov     rax, [rbp+var_28]
0x18004e0f9  test    rax, rax
0x18004e0fc  jz      loc_18004E2C3
0x18004e102  mov     r8, [rax]
0x18004e105  test    r8, r8
0x18004e108  jnz     short loc_18004E113
0x18004e10a  cmp     [rax+8], esi
0x18004e10d  ja      loc_18004E2C3
0x18004e113  cmp     [rax+8], esi
0x18004e116  jnz     short loc_18004E121
0x18004e118  test    r8, r8
0x18004e11b  jnz     loc_18004E2C3
0x18004e121  mov     r8, [rcx+10h]; lpString2
0x18004e125  mov     rcx, [rax+10h]; lpString1
0x18004e129  test    rcx, rcx
0x18004e12c  jz      loc_18004E2B9
0x18004e132  test    r8, r8
0x18004e135  jz      loc_18004E21D
0x18004e13b  mov     ebx, 0FFFFFFFFh
0x18004e140  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18004e148  mov     r9d, ebx; cchCount2
0x18004e14b  mov     edx, ebx; cchCount1
0x18004e14d  call    cs:__imp_CompareStringOrdinal
0x18004e153  add     eax, 0FFFFFFFEh
0x18004e156  cmp     eax, 7FFFFFFFh
0x18004e15b  jz      loc_18004E2CD
0x18004e161  test    eax, eax
0x18004e163  js      short loc_18004E16A
0x18004e165  mov     ebx, esi
0x18004e167  setnle  bl
0x18004e16a  mov     [rdi], ebx
0x18004e16c  mov     rbx, [rbp+var_40]
0x18004e170  mov     eax, [rbp+var_38]
0x18004e173  test    rbx, rbx
0x18004e176  jnz     short loc_18004E17C
0x18004e178  test    eax, eax
0x18004e17a  jnz     short loc_18004E192
0x18004e17c  test    eax, eax
0x18004e17e  jnz     short loc_18004E185
0x18004e180  test    rbx, rbx
0x18004e183  jnz     short loc_18004E192
0x18004e185  mov     [rbp+var_30], rsi
0x18004e189  test    rbx, rbx
0x18004e18c  jnz     loc_18004E279
0x18004e192  mov     rbx, [rbp+lpMem]
0x18004e196  mov     eax, [rbp+var_18]
0x18004e199  test    rbx, rbx
0x18004e19c  jnz     short loc_18004E1A2
0x18004e19e  test    eax, eax
0x18004e1a0  jnz     short loc_18004E1B4
0x18004e1a2  test    eax, eax
0x18004e1a4  jnz     short loc_18004E1AB
0x18004e1a6  test    rbx, rbx
0x18004e1a9  jnz     short loc_18004E1B4
0x18004e1ab  mov     [rbp+var_10], rsi
0x18004e1af  test    rbx, rbx
0x18004e1b2  jnz     short loc_18004E207
0x18004e1b4  xor     eax, eax
0x18004e1b6  add     rsp, 78h
0x18004e1ba  pop     rdi
0x18004e1bb  pop     rsi
0x18004e1bc  pop     rbx
0x18004e1bd  pop     rbp
0x18004e1be  retn
0x18004e1bf  mov     rbx, [rbp+var_40]
0x18004e1c3  mov     eax, [rbp+var_38]
0x18004e1c6  test    rbx, rbx
0x18004e1c9  jnz     short loc_18004E1CF
0x18004e1cb  test    eax, eax
0x18004e1cd  jnz     short loc_18004E1E5
0x18004e1cf  test    eax, eax
0x18004e1d1  jnz     short loc_18004E1D8
0x18004e1d3  test    rbx, rbx
0x18004e1d6  jnz     short loc_18004E1E5
0x18004e1d8  mov     [rbp+var_30], rsi
0x18004e1dc  test    rbx, rbx
0x18004e1df  jnz     loc_18004E299
0x18004e1e5  mov     rbx, [rbp+lpMem]
0x18004e1e9  mov     eax, [rbp+var_18]
0x18004e1ec  test    rbx, rbx
0x18004e1ef  jnz     short loc_18004E1F5
0x18004e1f1  test    eax, eax
0x18004e1f3  jnz     short loc_18004E1B4
0x18004e1f5  test    eax, eax
0x18004e1f7  jnz     short loc_18004E1FE
0x18004e1f9  test    rbx, rbx
0x18004e1fc  jnz     short loc_18004E1B4
0x18004e1fe  mov     [rbp+var_10], rsi
0x18004e202  test    rbx, rbx
0x18004e205  jz      short loc_18004E1B4
0x18004e207  call    cs:__imp_GetProcessHeap
0x18004e20d  mov     r8, rbx; lpMem
0x18004e210  xor     edx, edx; dwFlags
0x18004e212  mov     rcx, rax; hHeap
0x18004e215  call    cs:__imp_HeapFree
0x18004e21b  jmp     short loc_18004E1B4
0x18004e21d  mov     ebx, 1
0x18004e222  jmp     loc_18004E16A
0x18004e227  mov     rcx, [rbp+20h]; this
0x18004e22b  lea     r8, aMinkernelMrtMr_0; "minkernel\\mrt\\mrm\\mrmmin\\stringresu"...
0x18004e232  mov     ebx, 80070057h
0x18004e237  mov     edx, 0E1h; void *
0x18004e23c  mov     r9d, ebx; char *
0x18004e23f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e244  mov     rcx, [rbp+20h]; this
0x18004e248  lea     r8, aMinkernelMrtMr_29; "minkernel\\mrt\\mrm\\mrmmin\\basequalif"...
0x18004e24f  mov     r9d, ebx; char *
0x18004e252  mov     edx, 102h; void *
0x18004e257  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e25c  lea     rcx, [rbp+var_48]; this
0x18004e260  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x18004e265  lea     rcx, [rbp+var_28]; this
0x18004e269  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x18004e26e  mov     eax, ebx
0x18004e270  add     rsp, 78h
0x18004e274  pop     rdi
0x18004e275  pop     rsi
0x18004e276  pop     rbx
0x18004e277  pop     rbp
0x18004e278  retn
0x18004e279  call    cs:__imp_GetProcessHeap
0x18004e27f  mov     r8, rbx; lpMem
0x18004e282  xor     edx, edx; dwFlags
0x18004e284  mov     rcx, rax; hHeap
0x18004e287  call    cs:__imp_HeapFree
0x18004e28d  mov     [rbp+var_40], rsi
0x18004e291  mov     [rbp+var_38], esi
0x18004e294  jmp     loc_18004E192
0x18004e299  call    cs:__imp_GetProcessHeap
0x18004e29f  mov     r8, rbx; lpMem
0x18004e2a2  xor     edx, edx; dwFlags
0x18004e2a4  mov     rcx, rax; hHeap
0x18004e2a7  call    cs:__imp_HeapFree
0x18004e2ad  mov     [rbp+var_40], rsi
0x18004e2b1  mov     [rbp+var_38], esi
0x18004e2b4  jmp     loc_18004E1E5
0x18004e2b9  neg     r8
0x18004e2bc  sbb     ebx, ebx
0x18004e2be  jmp     loc_18004E16A
0x18004e2c3  mov     ebx, 80070057h
0x18004e2c8  jmp     loc_18004E244
0x18004e2cd  mov     ebx, 7FFFFFFFh
0x18004e2d2  jmp     loc_18004E16A
```
