# MakeStringW(ushort * *,ushort const *,...)

- ea: `0x1800858a4`
- end: `0x18008596d`
- name: `?MakeStringW@@YAJPEAPEAGPEBGZZ`
- size: `201`
- prototype: `int(unsigned __int16 **, const unsigned __int16 *, ...)`
- caller_count: `5`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019c70`
- `0x18001ebdc`
- `0x180023160`
- `0x180023b7c`
- `0x18008571c`

## callees

- `0x1800206c4`
- `0x1800846c0`
- `0x1800858a4`
- `0x1800859a8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008590a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008590a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180085913`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180085913`

## string_xrefs

- `0x180085945`: `com\complus\dtc\shared\util\stringutil.cpp`
- `0x1800858c8`: `MakeStringW (com\complus\dtc\shared\util\stringutil.cpp@63): MakeStringW, ppwszDestString != NULL`
- `0x1800858da`: `MakeStringW (com\complus\dtc\shared\util\stringutil.cpp@64): MakeStringW, pwszFormatString != NULL`

## pseudocode

```c
__int64 MakeStringW(unsigned __int16 **a1, const unsigned __int16 *a2, ...)
{
  unsigned __int16 *v4; // rsi
  SIZE_T v5; // r14
  unsigned __int16 *v6; // rax
  unsigned int v7; // ebx
  va_list va; // [rsp+70h] [rbp+18h] BYREF

  va_start(va, a2);
  if ( !a1 )
    DtcInternalErrorW(L"MakeStringW (com\\complus\\dtc\\shared\\util\\stringutil.cpp@63): MakeStringW, ppwszDestString != NULL");
  if ( !a2 )
    DtcInternalErrorW(L"MakeStringW (com\\complus\\dtc\\shared\\util\\stringutil.cpp@64): MakeStringW, pwszFormatString != NULL");
  *a1 = 0;
  v4 = 0;
  v5 = 128;
  while ( 1 )
  {
    v5 *= 2LL;
    CoTaskMemFree(v4);
    v6 = (unsigned __int16 *)CoTaskMemAlloc(v5);
    v4 = v6;
    if ( !v6 )
      break;
    if ( (unsigned int)StringCbVPrintfW(v6, v5, a2, va) != -2147024774 )
    {
      v7 = 0;
      *a1 = v4;
      return v7;
    }
  }
  v7 = -2147024882;
  TraceFileW(
    -2147024882,
    L"MakeStringW, StringCchVPrintfExW failed",
    L"com\\complus\\dtc\\shared\\util\\stringutil.cpp",
    0x4Fu);
  return v7;
}

```

## disassembly

```asm
0x1800858a4  mov     [rsp+arg_8], rdx
0x1800858a9  mov     qword ptr [rsp+arg_10], r8
0x1800858ae  mov     [rsp+arg_18], r9
0x1800858b3  push    rbx
0x1800858b4  push    rbp
0x1800858b5  push    rsi
0x1800858b6  push    rdi
0x1800858b7  push    r14
0x1800858b9  sub     rsp, 30h
0x1800858bd  mov     rbx, rdx
0x1800858c0  mov     rdi, rcx
0x1800858c3  test    rcx, rcx
0x1800858c6  jnz     short loc_1800858D5
0x1800858c8  lea     rcx, aMakestringwCom; "MakeStringW (com\\complus\\dtc\\shared"...
0x1800858cf  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x1800858d5  test    rbx, rbx
0x1800858d8  jnz     short loc_1800858E7
0x1800858da  lea     rcx, aMakestringwCom_0; "MakeStringW (com\\complus\\dtc\\shared"...
0x1800858e1  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x1800858e7  mov     qword ptr [rcx], 0
0x1800858ee  lea     rbp, [rsp+58h+arg_10]
0x1800858f3  mov     [rsp+58h+var_38], 0
0x1800858fc  xor     esi, esi
0x1800858fe  mov     r14d, 80h
0x180085904  mov     rcx, rsi; pv
0x180085907  add     r14, r14
0x18008590a  call    cs:__imp_CoTaskMemFree
0x180085910  mov     rcx, r14; cb
0x180085913  call    cs:__imp_CoTaskMemAlloc
0x180085919  mov     rsi, rax
0x18008591c  test    rax, rax
0x18008591f  jz      short loc_180085940
0x180085921  mov     r9, rbp; char *
0x180085924  mov     r8, rbx; unsigned __int16 *
0x180085927  mov     rdx, r14; unsigned __int64
0x18008592a  mov     rcx, rax; unsigned __int16 *
0x18008592d  call    ?StringCbVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCbVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x180085932  cmp     eax, 8007007Ah
0x180085937  jz      short loc_180085904
0x180085939  xor     ebx, ebx
0x18008593b  mov     [rdi], rsi
0x18008593e  jmp     short loc_180085960
0x180085940  mov     ebx, 8007000Eh
0x180085945  lea     r8, aComComplusDtcS_0; "com\\complus\\dtc\\shared\\util\\string"...
0x18008594c  mov     ecx, ebx; int
0x18008594e  lea     rdx, aMakestringwStr; "MakeStringW, StringCchVPrintfExW failed"
0x180085955  mov     r9d, 4Fh ; 'O'; unsigned int
0x18008595b  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x180085960  mov     eax, ebx
0x180085962  add     rsp, 30h
0x180085966  pop     r14
0x180085968  pop     rdi
0x180085969  pop     rsi
0x18008596a  pop     rbp
0x18008596b  pop     rbx
0x18008596c  retn
```
