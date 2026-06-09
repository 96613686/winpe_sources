# xgc::writeString<wchar_t>(xgc::ByteWriter const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,uint)

- ea: `0x18001cd84`
- end: `0x18001ce4d`
- name: `??$writeString@_W@xgc@@YAXAEBUByteWriter@0@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180020c14`

## callees

- `0x18000d524`
- `0x18001c058`
- `0x18001cd84`
- `0x1800228f0`
- `0x180037278`
- `0x1800372e4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001ce23`
- `KERNEL32!GetLastError` at `0x18001ce23`

## pseudocode

```c
errno_t __fastcall xgc::writeString<wchar_t>(__int64 a1, __int64 a2, int a3)
{
  unsigned int v3; // esi
  errno_t result; // eax
  const char *v7; // rdx
  int v8; // r8d
  unsigned int v9; // edi
  _WORD *v10; // rbx
  xpsrdr *v11; // rcx
  __int64 v12; // r9
  __int64 v13; // r10
  signed int LastError; // eax
  int v15; // edx
  const char *v16; // r8
  int v17; // r9d
  _WORD *Source; // [rsp+48h] [rbp+10h] BYREF

  v3 = *(_DWORD *)(a2 + 16);
  result = std::wstring::begin(a2, &Source);
  v9 = 0;
  if ( v3 )
  {
    v10 = Source;
    do
    {
      LOWORD(Source) = *v10++;
      v11 = (xpsrdr *)(*(_QWORD *)(*(_QWORD *)a1 + 8LL) - **(_QWORD **)a1);
      if ( (unsigned __int64)v11 < (unsigned __int64)(a3 + 2 * v9) + 2 )
        xpsrdr::ThrowLogicException(v11, v7, v8);
      xgc::SwapBytes<wchar_t>(&Source);
      result = memcpy_s((void *const)(v13 + v12), 2u, &Source, 2u);
      if ( result )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        if ( LastError >= 0 )
          LastError = -2147467259;
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)LastError, v15, v16, v17);
      }
      ++v9;
    }
    while ( v9 < v3 );
  }
  return result;
}

```

## disassembly

```asm
0x18001cd84  mov     [rsp+arg_0], rbx
0x18001cd89  mov     [rsp+arg_10], rsi
0x18001cd8e  push    rdi
0x18001cd8f  push    r14
0x18001cd91  push    r15
0x18001cd93  sub     rsp, 20h
0x18001cd97  mov     esi, [rdx+10h]
0x18001cd9a  mov     rax, rdx
0x18001cd9d  mov     r15, rcx
0x18001cda0  lea     rdx, [rsp+38h+Source]
0x18001cda5  mov     rcx, rax
0x18001cda8  mov     r14d, r8d
0x18001cdab  call    ?begin@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$_String_const_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@2@XZ; std::wstring::begin(void)
0x18001cdb0  xor     edi, edi
0x18001cdb2  test    esi, esi
0x18001cdb4  jz      short loc_18001CE0F
0x18001cdb6  mov     rbx, [rsp+38h+Source]
0x18001cdbb  movzx   ecx, word ptr [rbx]
0x18001cdbe  lea     eax, [r14+rdi*2]
0x18001cdc2  mov     word ptr [rsp+38h+Source], cx
0x18001cdc7  lea     rbx, [rbx+2]
0x18001cdcb  mov     rcx, [r15]
0x18001cdce  mov     r9d, eax
0x18001cdd1  add     rax, 2
0x18001cdd5  mov     r10, [rcx]
0x18001cdd8  mov     rcx, [rcx+8]
0x18001cddc  sub     rcx, r10; this
0x18001cddf  cmp     rcx, rax
0x18001cde2  jb      short loc_18001CE47
0x18001cde4  lea     rcx, [rsp+38h+Source]
0x18001cde9  call    ??$SwapBytes@_W@xgc@@YAXPEA_W@Z; xgc::SwapBytes<wchar_t>(wchar_t *)
0x18001cdee  lea     rcx, [r10+r9]; Destination
0x18001cdf2  mov     r9d, 2; SourceSize
0x18001cdf8  mov     edx, r9d; DestinationSize
0x18001cdfb  lea     r8, [rsp+38h+Source]; Source
0x18001ce00  call    memcpy_s
0x18001ce05  test    eax, eax
0x18001ce07  jnz     short loc_18001CE23
0x18001ce09  inc     edi
0x18001ce0b  cmp     edi, esi
0x18001ce0d  jb      short loc_18001CDBB
0x18001ce0f  mov     rbx, [rsp+38h+arg_0]
0x18001ce14  mov     rsi, [rsp+38h+arg_10]
0x18001ce19  add     rsp, 20h
0x18001ce1d  pop     r15
0x18001ce1f  pop     r14
0x18001ce21  pop     rdi
0x18001ce22  retn
0x18001ce23  call    cs:__imp_GetLastError
0x18001ce29  test    eax, eax
0x18001ce2b  jle     short loc_18001CE35
0x18001ce2d  movzx   eax, ax
0x18001ce30  or      eax, 80070000h
0x18001ce35  mov     ecx, 80004005h
0x18001ce3a  test    eax, eax
0x18001ce3c  cmovns  eax, ecx
0x18001ce3f  mov     ecx, eax; this
0x18001ce41  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18001ce47  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
```
