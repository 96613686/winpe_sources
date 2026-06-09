# CombinePaths(ushort const *,ushort const *,ushort * *)

- ea: `0x180054340`
- end: `0x1800543e2`
- name: `?CombinePaths@@YAJPEBG0PEAPEAG@Z`
- size: `162`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x180052848`

## callees

- `0x180033cd4`
- `0x180054340`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800543be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800543be`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800543af`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800543af`

## pseudocode

```c
__int64 __fastcall CombinePaths(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  __int64 v5; // r8
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rcx
  size_t v9; // rdi
  HRESULT v10; // ebx

  *a3 = 0;
  v5 = -1;
  v7 = -1;
  do
    ++v7;
  while ( a1[v7] );
  v8 = v7 + 2;
  if ( v7 + 2 < v7 )
    return (unsigned int)-2147024362;
  do
    ++v5;
  while ( a2[v5] );
  v9 = v8 + v5;
  if ( v8 + v5 < v8 )
  {
    return (unsigned int)-2147024362;
  }
  else if ( v9 > 0x104 )
  {
    return (unsigned int)-2147418113;
  }
  else
  {
    v10 = _AllocStringWorker<CTCoAllocPolicy>(v8, a2, a1, v8 + v5);
    if ( v10 >= 0 )
    {
      v10 = PathCchAppend(*a3, v9, a2);
      if ( v10 < 0 )
      {
        CoTaskMemFree(*a3);
        *a3 = 0;
      }
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180054340  push    rbx
0x180054342  push    rbp
0x180054343  push    rsi
0x180054344  push    rdi
0x180054345  push    r14
0x180054347  sub     rsp, 30h
0x18005434b  xor     r14d, r14d
0x18005434e  mov     rsi, r8
0x180054351  mov     [r8], r14
0x180054354  mov     rbp, rdx
0x180054357  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005435b  mov     r10, rcx
0x18005435e  mov     rax, r8
0x180054361  inc     rax
0x180054364  cmp     [rcx+rax*2], r14w
0x180054369  jnz     short loc_180054361
0x18005436b  lea     rcx, [rax+2]
0x18005436f  cmp     rcx, rax
0x180054372  jb      short loc_1800543D0
0x180054374  inc     r8
0x180054377  cmp     [rdx+r8*2], r14w
0x18005437c  jnz     short loc_180054374
0x18005437e  lea     rdi, [rcx+r8]
0x180054382  cmp     rdi, rcx
0x180054385  jb      short loc_1800543D0
0x180054387  cmp     rdi, 104h
0x18005438e  ja      short loc_1800543C9
0x180054390  mov     r9, rdi
0x180054393  mov     [rsp+58h+var_30], rsi
0x180054398  mov     r8, r10
0x18005439b  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1800543a0  mov     ebx, eax
0x1800543a2  test    eax, eax
0x1800543a4  js      short loc_1800543D5
0x1800543a6  mov     rcx, [rsi]; pszPath
0x1800543a9  mov     r8, rbp; pszMore
0x1800543ac  mov     rdx, rdi; cchPath
0x1800543af  call    cs:__imp_PathCchAppend
0x1800543b5  mov     ebx, eax
0x1800543b7  test    eax, eax
0x1800543b9  jns     short loc_1800543D5
0x1800543bb  mov     rcx, [rsi]; pv
0x1800543be  call    cs:__imp_CoTaskMemFree
0x1800543c4  mov     [rsi], r14
0x1800543c7  jmp     short loc_1800543D5
0x1800543c9  mov     ebx, 8000FFFFh
0x1800543ce  jmp     short loc_1800543D5
0x1800543d0  mov     ebx, 80070216h
0x1800543d5  mov     eax, ebx
0x1800543d7  add     rsp, 30h
0x1800543db  pop     r14
0x1800543dd  pop     rdi
0x1800543de  pop     rsi
0x1800543df  pop     rbp
0x1800543e0  pop     rbx
0x1800543e1  retn
```
