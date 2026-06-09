# FontNameList::StringLessThanIgnoreCase::operator()(wchar_t const *,wchar_t const *)

- ea: `0x18000a7d4`
- end: `0x18000a841`
- name: `??RStringLessThanIgnoreCase@FontNameList@@QEBA_NPEB_W0@Z`
- size: `109`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a0a8`
- `0x18000a704`

## callees

- `0x18000a7d4`
- `0x18009e420`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a81c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a81c`

## pseudocode

```c
__int64 __fastcall FontNameList::StringLessThanIgnoreCase::operator()(__int64 a1, const WCHAR *a2, const WCHAR *a3)
{
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // r9
  unsigned int v6; // eax

  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( a3[v5] );
  do
    ++v4;
  while ( a2[v4] );
  if ( a2 )
  {
    if ( a3 )
    {
      if ( v5 > 0x7FFFFFFF || v4 > 0x7FFFFFFF )
        SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(a1, v4, a3, v5);
      v6 = CompareStringOrdinal(a2, v4, a3, v5, 1) - 2;
    }
    else
    {
      v6 = 1;
    }
  }
  else
  {
    v6 = -(a3 != 0);
  }
  return v6 >> 31;
}

```

## disassembly

```asm
0x18000a7d4  sub     rsp, 38h
0x18000a7d8  mov     r10, rdx
0x18000a7db  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000a7df  mov     r9, rdx
0x18000a7e2  xor     eax, eax
0x18000a7e4  inc     r9; cchCount2
0x18000a7e7  cmp     [r8+r9*2], ax
0x18000a7ec  jnz     short loc_18000A7E4
0x18000a7ee  inc     rdx; cchCount1
0x18000a7f1  cmp     [r10+rdx*2], ax
0x18000a7f6  jnz     short loc_18000A7EE
0x18000a7f8  test    r10, r10
0x18000a7fb  jz      short loc_18000A82D
0x18000a7fd  test    r8, r8
0x18000a800  jz      short loc_18000A834
0x18000a802  mov     eax, 7FFFFFFFh
0x18000a807  cmp     r9, rax
0x18000a80a  ja      short loc_18000A83B
0x18000a80c  cmp     rdx, rax
0x18000a80f  ja      short loc_18000A83B
0x18000a811  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18000a819  mov     rcx, r10; lpString1
0x18000a81c  call    cs:__imp_CompareStringOrdinal
0x18000a822  sub     eax, 2
0x18000a825  shr     eax, 1Fh
0x18000a828  add     rsp, 38h
0x18000a82c  retn
0x18000a82d  neg     r8
0x18000a830  sbb     eax, eax
0x18000a832  jmp     short loc_18000A825
0x18000a834  mov     eax, 1
0x18000a839  jmp     short loc_18000A825
0x18000a83b  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@@@@SAXXZ; SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(void)
```
