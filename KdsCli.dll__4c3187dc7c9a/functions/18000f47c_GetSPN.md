# GetSPN

- ea: `0x18000f47c`
- end: `0x18000f55a`
- name: `GetSPN`
- size: `222`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f640`

## callees

- `0x180001fdc`
- `0x18000f47c`
- `0x180010920`
- `0x180010950`
- `0x18001a450`

## string_xrefs

- `0x18000f4d4`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyrpccommon.cxx`
- `0x18000f51e`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyrpccommon.cxx`

## pseudocode

```c
__int64 __fastcall GetSPN(__int64 a1, __int64 a2, wchar_t **a3)
{
  __int64 v3; // rax
  __int64 v5; // r9
  unsigned __int64 v8; // rbx
  wchar_t *v9; // rax
  wchar_t *v10; // rdi
  unsigned int v11; // ebx

  v3 = -1;
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(a2 + 2 * v5) );
  do
    ++v3;
  while ( *(_WORD *)(a1 + 2 * v3) );
  v8 = 2 * (v5 + v3) + 14;
  v9 = (wchar_t *)SIDKeyProvAlloc(v8);
  v10 = v9;
  if ( v9 )
  {
    if ( swprintf_s(v9, v8 >> 1, L"%s/%s/%s", L"HOST", a1, a2) >= 0 )
    {
      v11 = 0;
      *a3 = v10;
    }
    else
    {
      SidKeyDebugTraceError(
        0x80004005,
        "hr",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyrpccommon.cxx",
        0x83u);
      SIDKeyProvFree(v10);
      return (unsigned int)-2147467259;
    }
  }
  else
  {
    v11 = -2147024882;
    SidKeyDebugTraceError(
      0x8007000E,
      "hr",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyrpccommon.cxx",
      0x76u);
  }
  return v11;
}

```

## disassembly

```asm
0x18000f47c  push    rbx
0x18000f47e  push    rbp
0x18000f47f  push    rsi
0x18000f480  push    rdi
0x18000f481  push    r14
0x18000f483  push    r15
0x18000f485  sub     rsp, 38h
0x18000f489  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f48d  mov     r14, r8
0x18000f490  mov     r9, rax
0x18000f493  xor     r15d, r15d
0x18000f496  mov     rsi, rdx
0x18000f499  mov     rbp, rcx
0x18000f49c  inc     r9
0x18000f49f  cmp     [rdx+r9*2], r15w
0x18000f4a4  jnz     short loc_18000F49C
0x18000f4a6  inc     rax
0x18000f4a9  cmp     [rcx+rax*2], r15w
0x18000f4ae  jnz     short loc_18000F4A6
0x18000f4b0  add     rax, r9
0x18000f4b3  lea     rbx, ds:0Eh[rax*2]
0x18000f4bb  mov     rcx, rbx; unsigned __int64
0x18000f4be  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000f4c3  mov     rdi, rax
0x18000f4c6  test    rax, rax
0x18000f4c9  jnz     short loc_18000F4EE
0x18000f4cb  lea     r9d, [rax+76h]; unsigned int
0x18000f4cf  mov     ecx, 8007000Eh; unsigned int
0x18000f4d4  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000f4db  mov     ebx, 8007000Eh
0x18000f4e0  lea     rdx, aHr; "hr"
0x18000f4e7  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000f4ec  jmp     short loc_18000F54B
0x18000f4ee  shr     rbx, 1
0x18000f4f1  lea     r9, aHost; "HOST"
0x18000f4f8  mov     rdx, rbx; BufferCount
0x18000f4fb  mov     [rsp+68h+var_40], rsi
0x18000f500  lea     r8, aSSS; "%s/%s/%s"
0x18000f507  mov     [rsp+68h+var_48], rbp
0x18000f50c  mov     rcx, rdi; Buffer
0x18000f50f  call    swprintf_s
0x18000f514  test    eax, eax
0x18000f516  jns     short loc_18000F545
0x18000f518  mov     r9d, 83h; unsigned int
0x18000f51e  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000f525  lea     rdx, aHr; "hr"
0x18000f52c  mov     ecx, 80004005h; unsigned int
0x18000f531  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000f536  mov     rcx, rdi; lpMem
0x18000f539  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000f53e  mov     ebx, 80004005h
0x18000f543  jmp     short loc_18000F54B
0x18000f545  mov     ebx, r15d
0x18000f548  mov     [r14], rdi
0x18000f54b  mov     eax, ebx
0x18000f54d  add     rsp, 38h
0x18000f551  pop     r15
0x18000f553  pop     r14
0x18000f555  pop     rdi
0x18000f556  pop     rsi
0x18000f557  pop     rbp
0x18000f558  pop     rbx
0x18000f559  retn
```
