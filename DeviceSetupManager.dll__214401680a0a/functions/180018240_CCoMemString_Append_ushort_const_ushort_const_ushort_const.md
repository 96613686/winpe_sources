# CCoMemString::Append(ushort const *,ushort const *,ushort const *)

- ea: `0x180018240`
- end: `0x1800182ff`
- name: `?Append@CCoMemString@@QEAAJPEBG00@Z`
- size: `191`
- prototype: `int(CCoMemString *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010f48`
- `0x18003598c`
- `0x180035ba8`

## callees

- `0x180007720`
- `0x180010a7c`
- `0x180018240`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018293`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018293`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800182c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800182f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800182c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800182f4`

## pseudocode

```c
__int64 __fastcall CCoMemString::Append(
        const unsigned __int16 **this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 v5; // rax
  __int64 v7; // rcx
  int v8; // edi
  unsigned __int64 v9; // r14
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rbx

  v5 = -1;
  v7 = -1;
  v8 = 0;
  do
    ++v7;
  while ( a2[v7] );
  if ( v7 )
  {
    if ( *this )
    {
      do
        ++v5;
      while ( (*this)[v5] );
    }
    else
    {
      LODWORD(v5) = 0;
    }
    v9 = v7 + 1 + (unsigned int)v5;
    v10 = (unsigned __int16 *)CoTaskMemAlloc(2 * v9);
    v11 = v10;
    if ( !v10 )
      return (unsigned int)-2147024882;
    if ( *this )
    {
      v8 = StringCchCopyW(v10, v9, *this);
      if ( v8 < 0 )
      {
LABEL_11:
        CoTaskMemFree(v11);
        return (unsigned int)v8;
      }
    }
    else
    {
      *v10 = 0;
    }
    v8 = StringCchCatW(v11, v9, a2);
    if ( v8 >= 0 )
    {
      CoTaskMemFree((LPVOID)*this);
      *this = v11;
      return (unsigned int)v8;
    }
    goto LABEL_11;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180018240  push    rbx
0x180018242  push    rbp
0x180018243  push    rsi
0x180018244  push    rdi
0x180018245  push    r14
0x180018247  push    r15
0x180018249  sub     rsp, 28h
0x18001824d  xor     r15d, r15d
0x180018250  mov     rsi, rcx
0x180018253  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018257  mov     rbp, rdx
0x18001825a  mov     rcx, rax
0x18001825d  mov     edi, r15d
0x180018260  inc     rcx
0x180018263  cmp     [rdx+rcx*2], r15w
0x180018268  jnz     short loc_180018260
0x18001826a  test    rcx, rcx
0x18001826d  jz      short loc_1800182CA
0x18001826f  mov     rdx, [rsi]
0x180018272  test    rdx, rdx
0x180018275  jnz     short loc_18001827C
0x180018277  mov     eax, r15d
0x18001827a  jmp     short loc_180018286
0x18001827c  inc     rax
0x18001827f  cmp     [rdx+rax*2], r15w
0x180018284  jnz     short loc_18001827C
0x180018286  inc     rcx
0x180018289  mov     r14d, eax
0x18001828c  add     r14, rcx
0x18001828f  lea     rcx, [r14+r14]; cb
0x180018293  call    cs:__imp_CoTaskMemAlloc
0x180018299  mov     rbx, rax
0x18001829c  test    rax, rax
0x18001829f  jnz     short loc_1800182A8
0x1800182a1  mov     edi, 8007000Eh
0x1800182a6  jmp     short loc_1800182CA
0x1800182a8  mov     r8, [rsi]; unsigned __int16 *
0x1800182ab  test    r8, r8
0x1800182ae  jz      short loc_1800182D9
0x1800182b0  mov     rdx, r14; unsigned __int64
0x1800182b3  mov     rcx, rbx; unsigned __int16 *
0x1800182b6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800182bb  mov     edi, eax
0x1800182bd  test    eax, eax
0x1800182bf  jns     short loc_1800182DD
0x1800182c1  mov     rcx, rbx; pv
0x1800182c4  call    cs:__imp_CoTaskMemFree
0x1800182ca  mov     eax, edi
0x1800182cc  add     rsp, 28h
0x1800182d0  pop     r15
0x1800182d2  pop     r14
0x1800182d4  pop     rdi
0x1800182d5  pop     rsi
0x1800182d6  pop     rbp
0x1800182d7  pop     rbx
0x1800182d8  retn
0x1800182d9  mov     [rax], r15w
0x1800182dd  mov     r8, rbp; unsigned __int16 *
0x1800182e0  mov     rdx, r14; unsigned __int64
0x1800182e3  mov     rcx, rbx; unsigned __int16 *
0x1800182e6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800182eb  mov     edi, eax
0x1800182ed  test    eax, eax
0x1800182ef  js      short loc_1800182C1
0x1800182f1  mov     rcx, [rsi]; pv
0x1800182f4  call    cs:__imp_CoTaskMemFree
0x1800182fa  mov     [rsi], rbx
0x1800182fd  jmp     short loc_1800182CA
```
