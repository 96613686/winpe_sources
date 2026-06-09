# CNetworkItemFactory::_GetComputerNameAlloc(INetworkItem *,ushort * *)

- ea: `0x18000442c`
- end: `0x18000451c`
- name: `?_GetComputerNameAlloc@CNetworkItemFactory@@CAJPEAUINetworkItem@@PEAPEAG@Z`
- size: `240`
- prototype: `__int64 __fastcall(struct INetworkItem *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003d28`
- `0x1800049f4`
- `0x18000531c`

## callees

- `0x180003c14`
- `0x18000442c`
- `0x18000b010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800044ad`
- `ole32!CoTaskMemAlloc` at `0x1800044ad`
- `ole32!CoTaskMemFree` at `0x1800044f1`
- `ole32!CoTaskMemFree` at `0x1800044fc`
- `ole32!CoTaskMemFree` at `0x180004507`
- `ole32!CoTaskMemFree` at `0x1800044f1`
- `ole32!CoTaskMemFree` at `0x1800044fc`
- `ole32!CoTaskMemFree` at `0x180004507`

## pseudocode

```c
__int64 __fastcall CNetworkItemFactory::_GetComputerNameAlloc(struct INetworkItem *a1, unsigned __int16 **a2)
{
  __int64 v2; // rax
  int v5; // ebx
  __int64 v6; // rax
  __int64 v7; // rbx
  int v8; // eax
  __int64 v9; // rcx
  unsigned __int64 v10; // rbx
  unsigned __int16 *v11; // rdi
  LPVOID pv; // [rsp+50h] [rbp+8h] BYREF
  LPVOID v14; // [rsp+60h] [rbp+18h] BYREF

  v2 = *(_QWORD *)a1;
  v14 = 0;
  v5 = (*(__int64 (__fastcall **)(struct INetworkItem *, LPVOID *))(v2 + 40))(a1, &v14);
  if ( v5 >= 0 )
  {
    v6 = *(_QWORD *)a1;
    pv = 0;
    v7 = 0;
    v8 = (*(__int64 (__fastcall **)(struct INetworkItem *, LPVOID *))(v6 + 56))(a1, &pv);
    v9 = -1;
    if ( v8 >= 0 )
    {
      v7 = -1;
      do
        ++v7;
      while ( *((_WORD *)pv + v7) );
    }
    do
      ++v9;
    while ( *((_WORD *)v14 + v9) );
    v10 = v9 + 2 + v7;
    v11 = (unsigned __int16 *)CoTaskMemAlloc(2 * v10);
    if ( v11 )
    {
      v5 = StringCchPrintfW(v11, v10, L"%s\\%s", pv, v14);
      if ( v5 < 0 )
        CoTaskMemFree(v11);
      else
        *a2 = v11;
    }
    else
    {
      v5 = -2147024882;
    }
    CoTaskMemFree(pv);
    CoTaskMemFree(v14);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000442c  mov     [rsp+arg_8], rbx
0x180004431  push    rbp
0x180004432  push    rsi
0x180004433  push    rdi
0x180004434  sub     rsp, 30h
0x180004438  mov     rax, [rcx]
0x18000443b  mov     rsi, rdx
0x18000443e  xor     ebp, ebp
0x180004440  lea     rdx, [rsp+48h+arg_10]
0x180004445  mov     rdi, rcx
0x180004448  mov     [rsp+48h+arg_10], rbp
0x18000444d  mov     rax, [rax+28h]
0x180004451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004456  mov     ebx, eax
0x180004458  test    eax, eax
0x18000445a  js      loc_18000450D
0x180004460  mov     rax, [rdi]
0x180004463  lea     rdx, [rsp+48h+pv]
0x180004468  mov     rcx, rdi
0x18000446b  mov     [rsp+48h+pv], rbp
0x180004470  mov     ebx, ebp
0x180004472  mov     rax, [rax+38h]
0x180004476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000447b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000447f  test    eax, eax
0x180004481  js      short loc_180004494
0x180004483  mov     rax, [rsp+48h+pv]
0x180004488  mov     rbx, rcx
0x18000448b  inc     rbx
0x18000448e  cmp     [rax+rbx*2], bp
0x180004492  jnz     short loc_18000448B
0x180004494  mov     rax, [rsp+48h+arg_10]
0x180004499  inc     rcx
0x18000449c  cmp     [rax+rcx*2], bp
0x1800044a0  jnz     short loc_180004499
0x1800044a2  add     rcx, 2
0x1800044a6  add     rbx, rcx
0x1800044a9  lea     rcx, [rbx+rbx]; cb
0x1800044ad  call    cs:__imp_CoTaskMemAlloc
0x1800044b3  mov     rdi, rax
0x1800044b6  test    rax, rax
0x1800044b9  jnz     short loc_1800044C2
0x1800044bb  mov     ebx, 8007000Eh
0x1800044c0  jmp     short loc_1800044F7
0x1800044c2  mov     rax, [rsp+48h+arg_10]
0x1800044c7  lea     r8, aSS; "%s\\%s"
0x1800044ce  mov     r9, [rsp+48h+pv]
0x1800044d3  mov     rdx, rbx; unsigned __int64
0x1800044d6  mov     rcx, rdi; unsigned __int16 *
0x1800044d9  mov     [rsp+48h+var_28], rax
0x1800044de  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800044e3  mov     ebx, eax
0x1800044e5  test    eax, eax
0x1800044e7  js      short loc_1800044EE
0x1800044e9  mov     [rsi], rdi
0x1800044ec  jmp     short loc_1800044F7
0x1800044ee  mov     rcx, rdi; pv
0x1800044f1  call    cs:__imp_CoTaskMemFree
0x1800044f7  mov     rcx, [rsp+48h+pv]; pv
0x1800044fc  call    cs:__imp_CoTaskMemFree
0x180004502  mov     rcx, [rsp+48h+arg_10]; pv
0x180004507  call    cs:__imp_CoTaskMemFree
0x18000450d  mov     eax, ebx
0x18000450f  mov     rbx, [rsp+48h+arg_8]
0x180004514  add     rsp, 30h
0x180004518  pop     rdi
0x180004519  pop     rsi
0x18000451a  pop     rbp
0x18000451b  retn
```
