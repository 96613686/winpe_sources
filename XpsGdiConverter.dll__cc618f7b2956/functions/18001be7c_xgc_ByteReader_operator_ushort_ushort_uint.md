# xgc::ByteReader::operator()<ushort>(ushort *,uint)

- ea: `0x18001be7c`
- end: `0x18001beec`
- name: `??$?RG@ByteReader@xgc@@QEBAXPEAGI@Z`
- size: `112`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18001f288`
- `0x18001f444`
- `0x180020c14`

## callees

- `0x18000d524`
- `0x18001be7c`
- `0x18001c058`
- `0x180037278`
- `0x1800372e4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001bebb`
- `KERNEL32!GetLastError` at `0x18001bebb`

## pseudocode

```c
__int64 __fastcall xgc::ByteReader::operator()<unsigned short>(__int64 **a1, void *a2, unsigned int a3)
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
  if ( v6 < (xpsrdr *)(v4 + 2) )
    xpsrdr::ThrowLogicException(v6, v4, v5);
  if ( memcpy_s(a2, 2u, &v4[v5], 2u) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)LastError, v8, v9, v10);
  }
  return xgc::SwapBytes<wchar_t>(a2);
}

```

## disassembly

```asm
0x18001be7c  push    rbx
0x18001be7e  sub     rsp, 20h
0x18001be82  mov     rax, [rcx]
0x18001be85  mov     rbx, rdx
0x18001be88  mov     edx, r8d; char *
0x18001be8b  mov     r8, [rax]; int
0x18001be8e  mov     rcx, [rax+8]
0x18001be92  lea     rax, [rdx+2]
0x18001be96  sub     rcx, r8; this
0x18001be99  cmp     rcx, rax
0x18001be9c  jnb     short loc_18001BEA4
0x18001be9e  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x18001bea4  add     r8, rdx; Source
0x18001bea7  mov     rcx, rbx; Destination
0x18001beaa  mov     edx, 2; DestinationSize
0x18001beaf  mov     r9d, edx; SourceSize
0x18001beb2  call    memcpy_s
0x18001beb7  test    eax, eax
0x18001beb9  jz      short loc_18001BEDF
0x18001bebb  call    cs:__imp_GetLastError
0x18001bec1  test    eax, eax
0x18001bec3  jle     short loc_18001BECD
0x18001bec5  movzx   eax, ax
0x18001bec8  or      eax, 80070000h
0x18001becd  mov     ecx, 80004005h
0x18001bed2  test    eax, eax
0x18001bed4  cmovns  eax, ecx
0x18001bed7  mov     ecx, eax; this
0x18001bed9  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18001bedf  mov     rcx, rbx
0x18001bee2  add     rsp, 20h
0x18001bee6  pop     rbx
0x18001bee7  jmp     ??$SwapBytes@_W@xgc@@YAXPEA_W@Z; xgc::SwapBytes<wchar_t>(wchar_t *)
```
