# GetRootKeyDN(ushort const *,ushort const *,ushort * *)

- ea: `0x180005934`
- end: `0x180005a1c`
- name: `?GetRootKeyDN@@YAJPEBG0PEAPEAG@Z`
- size: `232`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004a00`

## callees

- `0x180001fdc`
- `0x180005934`
- `0x180010920`
- `0x180010950`
- `0x18001a450`

## string_xrefs

- `0x18000598b`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsrootkey.cxx`
- `0x1800059d8`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsrootkey.cxx`

## pseudocode

```c
__int64 __fastcall GetRootKeyDN(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  __int64 v3; // rax
  __int64 v5; // r9
  __int64 v8; // rbx
  __int64 v9; // rsi
  wchar_t *v10; // rax
  unsigned __int16 *v11; // rdi
  unsigned int v12; // ebx

  v3 = -1;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  do
    ++v3;
  while ( a1[v3] );
  v8 = v5 + v3 + 5;
  v9 = v8;
  v10 = (wchar_t *)SIDKeyProvAlloc(2 * v8);
  v11 = v10;
  if ( v10 )
  {
    if ( swprintf_s(v10, v8 & 0x7FFFFFFFFFFFFFFFLL, L"cn=%s,%s", a2, a1) >= 0 )
    {
      v12 = 0;
      v11[v9 - 1] = 0;
      *a3 = v11;
    }
    else
    {
      SidKeyDebugTraceError(
        0x80004005,
        "hr",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx",
        0x11Eu);
      SIDKeyProvFree(v11);
      return (unsigned int)-2147467259;
    }
  }
  else
  {
    v12 = -2147024882;
    SidKeyDebugTraceError(0x8007000E, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx", 0x111u);
  }
  return v12;
}

```

## disassembly

```asm
0x180005934  push    rbx
0x180005936  push    rbp
0x180005937  push    rsi
0x180005938  push    rdi
0x180005939  push    r12
0x18000593b  push    r14
0x18000593d  push    r15
0x18000593f  sub     rsp, 30h
0x180005943  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005947  mov     r15, r8
0x18000594a  mov     r9, rax
0x18000594d  xor     r12d, r12d
0x180005950  mov     rbp, rdx
0x180005953  mov     r14, rcx
0x180005956  inc     r9
0x180005959  cmp     [rdx+r9*2], r12w
0x18000595e  jnz     short loc_180005956
0x180005960  inc     rax
0x180005963  cmp     [rcx+rax*2], r12w
0x180005968  jnz     short loc_180005960
0x18000596a  lea     rbx, [rax+5]
0x18000596e  add     rbx, r9
0x180005971  lea     rsi, [rbx+rbx]
0x180005975  mov     rcx, rsi; unsigned __int64
0x180005978  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000597d  mov     rdi, rax
0x180005980  test    rax, rax
0x180005983  jnz     short loc_1800059AA
0x180005985  mov     r9d, 111h; unsigned int
0x18000598b  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180005992  lea     rdx, aHr; "hr"
0x180005999  mov     ecx, 8007000Eh; unsigned int
0x18000599e  mov     ebx, 8007000Eh
0x1800059a3  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800059a8  jmp     short loc_180005A0B
0x1800059aa  mov     rdx, 7FFFFFFFFFFFFFFFh
0x1800059b4  mov     [rsp+68h+var_48], r14
0x1800059b9  and     rdx, rbx; BufferCount
0x1800059bc  lea     r8, aCnSS; "cn=%s,%s"
0x1800059c3  mov     r9, rbp
0x1800059c6  mov     rcx, rdi; Buffer
0x1800059c9  call    swprintf_s
0x1800059ce  test    eax, eax
0x1800059d0  jns     short loc_1800059FF
0x1800059d2  mov     r9d, 11Eh; unsigned int
0x1800059d8  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800059df  lea     rdx, aHr; "hr"
0x1800059e6  mov     ecx, 80004005h; unsigned int
0x1800059eb  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800059f0  mov     rcx, rdi; lpMem
0x1800059f3  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x1800059f8  mov     ebx, 80004005h
0x1800059fd  jmp     short loc_180005A0B
0x1800059ff  mov     ebx, r12d
0x180005a02  mov     [rsi+rdi-2], r12w
0x180005a08  mov     [r15], rdi
0x180005a0b  mov     eax, ebx
0x180005a0d  add     rsp, 30h
0x180005a11  pop     r15
0x180005a13  pop     r14
0x180005a15  pop     r12
0x180005a17  pop     rdi
0x180005a18  pop     rsi
0x180005a19  pop     rbp
0x180005a1a  pop     rbx
0x180005a1b  retn
```
