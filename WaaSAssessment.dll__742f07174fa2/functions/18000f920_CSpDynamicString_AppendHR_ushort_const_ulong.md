# CSpDynamicString::AppendHR(ushort const *,ulong)

- ea: `0x18000f920`
- end: `0x18000fa16`
- name: `?AppendHR@CSpDynamicString@@QEAAJPEBGK@Z`
- size: `246`
- prototype: `int(CSpDynamicString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012fc8`

## callees

- `0x18000f920`
- `0x180019722`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f9cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f9cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f9a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f9a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f97c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f97c`

## pseudocode

```c
__int64 __fastcall CSpDynamicString::AppendHR(const void **this, const unsigned __int16 *a2, unsigned int a3)
{
  __int64 v4; // rbp
  unsigned int v6; // esi
  _WORD *v7; // rcx
  unsigned int v8; // ebx
  __int64 v9; // rax
  __int64 v10; // rax
  unsigned __int64 v11; // rdx
  _WORD *v12; // rax
  _WORD *v13; // r14

  v4 = a3;
  v6 = 0;
  if ( !a2 )
    return v6;
  if ( a3 )
  {
    v7 = *this;
    if ( v7 )
    {
      v9 = -1;
      do
        ++v9;
      while ( v7[v9] );
      v8 = v9;
      if ( (unsigned int)v9 != v9 )
      {
        SetLastError(0x216u);
        v8 = -1;
      }
      goto LABEL_11;
    }
  }
  else if ( *this )
  {
    return v6;
  }
  v8 = 0;
LABEL_11:
  v10 = v8 + v4;
  v11 = 2 * v10 + 2;
  if ( v11 > v10 + 1 && (unsigned int)v11 == v11 )
  {
    v12 = CoTaskMemAlloc((unsigned int)v11);
    v13 = v12;
    if ( v12 )
    {
      if ( *this )
      {
        if ( v8 )
          memcpy_0(v12, *this, 2LL * v8);
        CoTaskMemFree((LPVOID)*this);
      }
      memcpy_0(&v13[v8], a2, 2 * v4);
      v13[v4 + v8] = 0;
      *this = v13;
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x18000f920  push    rbx
0x18000f922  push    rbp
0x18000f923  push    rsi
0x18000f924  push    rdi
0x18000f925  push    r12
0x18000f927  push    r13
0x18000f929  push    r14
0x18000f92b  push    r15
0x18000f92d  sub     rsp, 28h
0x18000f931  mov     r13, rdx
0x18000f934  mov     ebp, r8d
0x18000f937  xor     edx, edx
0x18000f939  mov     rdi, rcx
0x18000f93c  mov     esi, edx
0x18000f93e  test    r13, r13
0x18000f941  jz      loc_18000FA03
0x18000f947  test    r8d, r8d
0x18000f94a  jnz     short loc_18000F957
0x18000f94c  cmp     [rcx], rdx
0x18000f94f  jnz     loc_18000FA03
0x18000f955  jmp     short loc_18000F95F
0x18000f957  mov     rcx, [rcx]
0x18000f95a  test    rcx, rcx
0x18000f95d  jnz     short loc_18000F963
0x18000f95f  mov     ebx, edx
0x18000f961  jmp     short loc_18000F985
0x18000f963  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f967  inc     rax
0x18000f96a  cmp     [rcx+rax*2], dx
0x18000f96e  jnz     short loc_18000F967
0x18000f970  mov     ebx, eax
0x18000f972  cmp     rbx, rax
0x18000f975  jz      short loc_18000F985
0x18000f977  mov     ecx, 216h; dwErrCode
0x18000f97c  call    cs:__imp_SetLastError
0x18000f982  or      ebx, 0FFFFFFFFh
0x18000f985  mov     r15d, ebx
0x18000f988  lea     rax, [r15+rbp]
0x18000f98c  lea     rdx, ds:2[rax*2]
0x18000f994  inc     rax
0x18000f997  cmp     rdx, rax
0x18000f99a  jbe     short loc_18000F9FE
0x18000f99c  mov     ecx, edx; cb
0x18000f99e  cmp     rcx, rdx
0x18000f9a1  jnz     short loc_18000F9FE
0x18000f9a3  call    cs:__imp_CoTaskMemAlloc
0x18000f9a9  mov     r14, rax
0x18000f9ac  test    rax, rax
0x18000f9af  jz      short loc_18000F9F7
0x18000f9b1  mov     rdx, [rdi]; Src
0x18000f9b4  test    rdx, rdx
0x18000f9b7  jz      short loc_18000F9D2
0x18000f9b9  test    ebx, ebx
0x18000f9bb  jz      short loc_18000F9C9
0x18000f9bd  lea     r8, [r15+r15]; Size
0x18000f9c1  mov     rcx, rax; void *
0x18000f9c4  call    memcpy_0
0x18000f9c9  mov     rcx, [rdi]; pv
0x18000f9cc  call    cs:__imp_CoTaskMemFree
0x18000f9d2  lea     r8, ds:0[rbp*2]; Size
0x18000f9da  mov     rdx, r13; Src
0x18000f9dd  lea     rcx, [r14+r15*2]; void *
0x18000f9e1  call    memcpy_0
0x18000f9e6  mov     ecx, ebx
0x18000f9e8  add     rcx, rbp
0x18000f9eb  xor     eax, eax
0x18000f9ed  mov     [r14+rcx*2], ax
0x18000f9f2  mov     [rdi], r14
0x18000f9f5  jmp     short loc_18000FA03
0x18000f9f7  mov     esi, 8007000Eh
0x18000f9fc  jmp     short loc_18000FA03
0x18000f9fe  mov     esi, 80070057h
0x18000fa03  mov     eax, esi
0x18000fa05  add     rsp, 28h
0x18000fa09  pop     r15
0x18000fa0b  pop     r14
0x18000fa0d  pop     r13
0x18000fa0f  pop     r12
0x18000fa11  pop     rdi
0x18000fa12  pop     rsi
0x18000fa13  pop     rbp
0x18000fa14  pop     rbx
0x18000fa15  retn
```
