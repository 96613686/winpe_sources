# PropVariantString(ushort const *,tagPROPVARIANT *)

- ea: `0x180002608`
- end: `0x180002707`
- name: `?PropVariantString@@YAJPEBGPEAUtagPROPVARIANT@@@Z`
- size: `255`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800022a8`
- `0x180022c50`

## callees

- `0x180002594`
- `0x180002608`
- `0x1800171c4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800026dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800026dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000268f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000268f`

## pseudocode

```c
__int64 __fastcall PropVariantString(const unsigned __int16 *a1, struct tagPROPVARIANT *a2)
{
  unsigned int v4; // ebx
  const unsigned __int16 *v5; // rax
  __int64 v6; // r8
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // rbx
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rdi
  int v12; // eax

  v4 = 0;
  if ( !a1 )
    return v4;
  v5 = a1;
  v6 = 0x7FFFFFFF;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v6;
  }
  while ( v6 );
  v4 = v6 == 0 ? 0x80070057 : 0;
  v7 = (0x7FFFFFFF - v6) & -(__int64)(v6 != 0);
  if ( !v6 )
    goto LABEL_11;
  v8 = v7 + 1;
  if ( v7 + 1 < v7 || (v9 = 2 * v8, !is_mul_ok(v8, 2u)) )
  {
    v4 = -2147024362;
    goto LABEL_11;
  }
  v10 = (unsigned __int16 *)CoTaskMemAlloc(2 * v8);
  v11 = v10;
  if ( !v10 )
  {
    v4 = -2147024882;
LABEL_11:
    if ( g_doStackCaptures )
      DoStackCapture(v4);
    return v4;
  }
  v12 = StringCchCopyW(v10, v9 >> 1, a1);
  v4 = v12;
  if ( v12 >= 0 )
  {
    a2->vt = 31;
    a2->hVal.QuadPart = (LONGLONG)v11;
  }
  else
  {
    if ( g_doStackCaptures )
      DoStackCapture(v12);
    CoTaskMemFree(v11);
  }
  return v4;
}

```

## disassembly

```asm
0x180002608  mov     [rsp+arg_8], rbx
0x18000260d  mov     [rsp+arg_10], rbp
0x180002612  push    rsi
0x180002613  push    rdi
0x180002614  push    r14
0x180002616  sub     rsp, 20h
0x18000261a  xor     ebp, ebp
0x18000261c  mov     r14, rdx
0x18000261f  mov     rsi, rcx
0x180002622  mov     ebx, ebp
0x180002624  test    rcx, rcx
0x180002627  jz      loc_1800026E2
0x18000262d  mov     r9d, 7FFFFFFFh
0x180002633  mov     rax, rcx
0x180002636  mov     r8d, r9d
0x180002639  cmp     [rax], bp
0x18000263c  jz      short loc_180002648
0x18000263e  add     rax, 2
0x180002642  sub     r8, 1
0x180002646  jnz     short loc_180002639
0x180002648  mov     rax, r8
0x18000264b  neg     rax
0x18000264e  mov     rax, r8
0x180002651  sbb     ebx, ebx
0x180002653  sub     r9, r8
0x180002656  not     ebx
0x180002658  and     ebx, 80070057h
0x18000265e  neg     rax
0x180002661  sbb     rcx, rcx
0x180002664  and     rcx, r9
0x180002667  test    r8, r8
0x18000266a  jz      short loc_1800026A2
0x18000266c  lea     rdx, [rcx+1]
0x180002670  cmp     rdx, rcx
0x180002673  jnb     short loc_18000267C
0x180002675  mov     ebx, 80070216h
0x18000267a  jmp     short loc_1800026A2
0x18000267c  mov     eax, 2
0x180002681  mul     rdx
0x180002684  mov     rbx, rax
0x180002687  test    rdx, rdx
0x18000268a  jnz     short loc_180002675
0x18000268c  mov     rcx, rax; cb
0x18000268f  call    cs:__imp_CoTaskMemAlloc
0x180002695  mov     rdi, rax
0x180002698  test    rax, rax
0x18000269b  jnz     short loc_1800026B3
0x18000269d  mov     ebx, 8007000Eh
0x1800026a2  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x1800026a8  jz      short loc_1800026E2
0x1800026aa  mov     ecx, ebx; int
0x1800026ac  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800026b1  jmp     short loc_1800026E2
0x1800026b3  shr     rbx, 1
0x1800026b6  mov     r8, rsi; unsigned __int16 *
0x1800026b9  mov     rdx, rbx; unsigned __int64
0x1800026bc  mov     rcx, rdi; unsigned __int16 *
0x1800026bf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800026c4  mov     ebx, eax
0x1800026c6  test    eax, eax
0x1800026c8  jns     short loc_1800026FB
0x1800026ca  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x1800026d0  jz      short loc_1800026F7
0x1800026d2  mov     ecx, eax; int
0x1800026d4  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800026d9  mov     rcx, rdi; pv
0x1800026dc  call    cs:__imp_CoTaskMemFree
0x1800026e2  mov     rbp, [rsp+38h+arg_10]
0x1800026e7  mov     eax, ebx
0x1800026e9  mov     rbx, [rsp+38h+arg_8]
0x1800026ee  add     rsp, 20h
0x1800026f2  pop     r14
0x1800026f4  pop     rdi
0x1800026f5  pop     rsi
0x1800026f6  retn
0x1800026f7  test    eax, eax
0x1800026f9  js      short loc_1800026D9
0x1800026fb  mov     word ptr [r14], 1Fh
0x180002701  mov     [r14+8], rdi
0x180002705  jmp     short loc_1800026E2
```
