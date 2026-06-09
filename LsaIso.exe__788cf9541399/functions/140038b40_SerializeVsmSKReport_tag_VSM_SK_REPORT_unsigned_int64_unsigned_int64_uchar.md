# SerializeVsmSKReport(tag_VSM_SK_REPORT *,unsigned __int64,unsigned __int64 *,uchar *)

- ea: `0x140038b40`
- end: `0x140038bb8`
- name: `?SerializeVsmSKReport@@YAJPEAUtag_VSM_SK_REPORT@@_KPEA_KPEAE@Z`
- size: `120`
- prototype: `__int64 __fastcall(struct tag_VSM_SK_REPORT *Src, size_t Size, unsigned __int64 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140037bec`

## callees

- `0x140003ad6`
- `0x1400385f0`
- `0x140038b40`

## string_xrefs

- `0x140038b59`: `onecore\ds\security\cryptoapi\ncrypt\common\vsmskreporthelper\lib\vsmskreporthelper.cpp`

## pseudocode

```c
__int64 __fastcall SerializeVsmSKReport(
        struct tag_VSM_SK_REPORT *Src,
        size_t Size,
        unsigned __int64 *a3,
        unsigned __int8 *a4)
{
  __int64 v6; // r9

  if ( !Src )
  {
    v6 = 36;
LABEL_3:
    DebugTraceError(
      2147942487LL,
      "in_hr",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\vsmskreporthelper\\lib\\vsmskreporthelper.cpp",
      v6);
    return 2147942487LL;
  }
  if ( !a3 )
  {
    v6 = 37;
    goto LABEL_3;
  }
  if ( a4 )
  {
    if ( *a3 < Size )
    {
      v6 = 45;
      goto LABEL_3;
    }
    memcpy_0(a4, Src, Size);
    *a3 = Size;
  }
  else
  {
    *a3 = Size;
  }
  return 0;
}

```

## disassembly

```asm
0x140038b40  mov     [rsp+arg_0], rbx
0x140038b45  push    rdi
0x140038b46  sub     rsp, 20h
0x140038b4a  mov     rbx, r8
0x140038b4d  mov     rdi, rdx
0x140038b50  test    rcx, rcx
0x140038b53  jnz     short loc_140038B78
0x140038b55  lea     r9d, [rcx+24h]
0x140038b59  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x140038b60  mov     ecx, 80070057h
0x140038b65  lea     rdx, aInHr; "in_hr"
0x140038b6c  call    DebugTraceError
0x140038b71  mov     eax, 80070057h
0x140038b76  jmp     short loc_140038BAD
0x140038b78  test    rbx, rbx
0x140038b7b  jnz     short loc_140038B83
0x140038b7d  lea     r9d, [rbx+25h]
0x140038b81  jmp     short loc_140038B59
0x140038b83  test    r9, r9
0x140038b86  jnz     short loc_140038B8D
0x140038b88  mov     [r8], rdi
0x140038b8b  jmp     short loc_140038BAB
0x140038b8d  cmp     [r8], rdi
0x140038b90  jnb     short loc_140038B9A
0x140038b92  mov     r9d, 2Dh ; '-'
0x140038b98  jmp     short loc_140038B59
0x140038b9a  mov     rdx, rcx; Src
0x140038b9d  mov     r8, rdi; Size
0x140038ba0  mov     rcx, r9; void *
0x140038ba3  call    memcpy_0
0x140038ba8  mov     [rbx], rdi
0x140038bab  xor     eax, eax
0x140038bad  mov     rbx, [rsp+28h+arg_0]
0x140038bb2  add     rsp, 20h
0x140038bb6  pop     rdi
0x140038bb7  retn
```
