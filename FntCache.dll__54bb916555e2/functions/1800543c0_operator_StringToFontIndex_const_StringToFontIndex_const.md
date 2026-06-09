# operator<(StringToFontIndex const &,StringToFontIndex const &)

- ea: `0x1800543c0`
- end: `0x180054466`
- name: `??M@YA_NAEBUStringToFontIndex@@0@Z`
- size: `166`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180028d88`
- `0x1800bb7c4`
- `0x1800bb960`

## callees

- `0x1800543c0`
- `0x18009e420`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180054417`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180054417`

## pseudocode

```c
char __fastcall operator<(_DWORD *a1, _DWORD *a2)
{
  const WCHAR *lpString2; // r9
  __int64 v5; // r8
  const WCHAR *v6; // r10
  __int64 cchCount2; // rcx
  unsigned int v8; // eax
  unsigned int v9; // eax
  int v10; // eax

  lpString2 = (const WCHAR *)(*(_QWORD *)a2 + 8LL);
  v5 = *(_QWORD *)a1;
  v6 = (const WCHAR *)(*(_QWORD *)a1 + 8LL);
  if ( *(_QWORD *)a1 == -8 )
  {
    if ( *(_QWORD *)a2 != -8 )
    {
      LOBYTE(v10) = 1;
      return v10;
    }
    goto LABEL_7;
  }
  if ( *(_QWORD *)a2 != -8 )
  {
    cchCount2 = *(unsigned int *)(*(_QWORD *)a2 + 4LL);
    if ( (unsigned int)cchCount2 > 0x7FFFFFFF || (v8 = *(_DWORD *)(v5 + 4), v8 > 0x7FFFFFFF) )
      SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(cchCount2, a2, v5, lpString2);
    v9 = CompareStringW(0x7Fu, 1u, v6, v8, lpString2, cchCount2) - 2;
    if ( v9 )
      return v9 >> 31;
LABEL_7:
    LOBYTE(v10) = a1[2] < a2[2];
    return v10;
  }
  v9 = 1;
  return v9 >> 31;
}

```

## disassembly

```asm
0x1800543c0  mov     [rsp+arg_0], rbx
0x1800543c5  push    rdi
0x1800543c6  sub     rsp, 30h
0x1800543ca  mov     rbx, rdx
0x1800543cd  mov     rdi, rcx
0x1800543d0  mov     rax, [rdx]
0x1800543d3  lea     r9, [rax+8]
0x1800543d7  mov     r8, [rcx]
0x1800543da  lea     r10, [r8+8]
0x1800543de  test    r10, r10
0x1800543e1  jz      short loc_180054444
0x1800543e3  test    r9, r9
0x1800543e6  jz      short loc_180054459
0x1800543e8  mov     ecx, [rax+4]
0x1800543eb  cmp     ecx, 7FFFFFFFh
0x1800543f1  ja      short loc_180054460
0x1800543f3  mov     eax, [r8+4]
0x1800543f7  cmp     eax, 7FFFFFFFh
0x1800543fc  ja      short loc_180054460
0x1800543fe  mov     [rsp+38h+cchCount2], ecx; cchCount2
0x180054402  mov     [rsp+38h+lpString2], r9; lpString2
0x180054407  mov     r9d, eax; cchCount1
0x18005440a  mov     r8, r10; lpString1
0x18005440d  mov     edx, 1; dwCmpFlags
0x180054412  mov     ecx, 7Fh; Locale
0x180054417  call    cs:__imp_CompareStringW
0x18005441d  add     eax, 0FFFFFFFEh
0x180054420  jz      short loc_180054430
0x180054422  shr     eax, 1Fh
0x180054425  mov     rbx, [rsp+38h+arg_0]
0x18005442a  add     rsp, 30h
0x18005442e  pop     rdi
0x18005442f  retn
0x180054430  mov     eax, [rbx+8]
0x180054433  cmp     [rdi+8], eax
0x180054436  setb    al
0x180054439  mov     rbx, [rsp+38h+arg_0]
0x18005443e  add     rsp, 30h
0x180054442  pop     rdi
0x180054443  retn
0x180054444  test    r9, r9
0x180054447  jz      short loc_180054430
0x180054449  mov     eax, 1
0x18005444e  mov     rbx, [rsp+38h+arg_0]
0x180054453  add     rsp, 30h
0x180054457  pop     rdi
0x180054458  retn
0x180054459  mov     eax, 1
0x18005445e  jmp     short loc_180054422
0x180054460  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@@@@SAXXZ; SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(void)
```
