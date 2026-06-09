# xgc::ByteReader::operator()<uint>(uint *,uint)

- ea: `0x18001bf70`
- end: `0x18001bfe0`
- name: `??$?RI@ByteReader@xgc@@QEBAXPEAII@Z`
- size: `112`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18001e4d4`
- `0x18001f288`
- `0x18001f368`
- `0x18001f444`

## callees

- `0x18000d524`
- `0x18001bf70`
- `0x18001c08c`
- `0x180037278`
- `0x1800372e4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001bfaf`
- `KERNEL32!GetLastError` at `0x18001bfaf`

## pseudocode

```c
__int64 __fastcall xgc::ByteReader::operator()<unsigned int>(__int64 **a1, void *a2, unsigned int a3)
{
  const char *v4; // rdx
  __int64 v5; // r8
  xpsrdr *v6; // rcx
  signed int LastError; // eax
  int v8; // edx
  const char *v9; // r8
  int v10; // r9d

  v4 = (const char *)a3;
  v5 = **a1;
  v6 = (xpsrdr *)((*a1)[1] - v5);
  if ( v6 < (xpsrdr *)(v4 + 4) )
    xpsrdr::ThrowLogicException(v6, v4, v5);
  if ( memcpy_s(a2, 4u, &v4[v5], 4u) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)LastError, v8, v9, v10);
  }
  return xgc::SwapBytes<unsigned int>(a2);
}

```

## disassembly

```asm
0x18001bf70  push    rbx
0x18001bf72  sub     rsp, 20h
0x18001bf76  mov     rax, [rcx]
0x18001bf79  mov     rbx, rdx
0x18001bf7c  mov     edx, r8d; char *
0x18001bf7f  mov     r8, [rax]; int
0x18001bf82  mov     rcx, [rax+8]
0x18001bf86  lea     rax, [rdx+4]
0x18001bf8a  sub     rcx, r8; this
0x18001bf8d  cmp     rcx, rax
0x18001bf90  jnb     short loc_18001BF98
0x18001bf92  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x18001bf98  add     r8, rdx; Source
0x18001bf9b  mov     rcx, rbx; Destination
0x18001bf9e  mov     edx, 4; DestinationSize
0x18001bfa3  mov     r9d, edx; SourceSize
0x18001bfa6  call    memcpy_s
0x18001bfab  test    eax, eax
0x18001bfad  jz      short loc_18001BFD3
0x18001bfaf  call    cs:__imp_GetLastError
0x18001bfb5  test    eax, eax
0x18001bfb7  jle     short loc_18001BFC1
0x18001bfb9  movzx   eax, ax
0x18001bfbc  or      eax, 80070000h
0x18001bfc1  mov     ecx, 80004005h
0x18001bfc6  test    eax, eax
0x18001bfc8  cmovns  eax, ecx
0x18001bfcb  mov     ecx, eax; this
0x18001bfcd  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18001bfd3  mov     rcx, rbx
0x18001bfd6  add     rsp, 20h
0x18001bfda  pop     rbx
0x18001bfdb  jmp     ??$SwapBytes@I@xgc@@YAXPEAI@Z; xgc::SwapBytes<uint>(uint *)
```
