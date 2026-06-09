# StringCheckedPtr::LessThan::operator()(CheckedPtr<wchar_t const,FailAsExceptionPolicy<InvalidCacheDataException>,uint> const &,CheckedPtr<wchar_t const,FailAsExceptionPolicy<InvalidCacheDataException>,uint> const &)

- ea: `0x180051860`
- end: `0x1800518d2`
- name: `??RLessThan@StringCheckedPtr@@QEBA_NAEBV?$CheckedPtr@$$CB_WV?$FailAsExceptionPolicy@VInvalidCacheDataException@@@@I@@0@Z`
- size: `114`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800506b0`

## callees

- `0x180051860`
- `0x18009e420`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800518a3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800518a3`

## pseudocode

```c
__int64 __fastcall StringCheckedPtr::LessThan::operator()(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  const WCHAR *lpString2; // rax
  __int64 cchCount2; // rcx

  lpString2 = *(const WCHAR **)a3;
  if ( *(_QWORD *)a2 )
  {
    if ( lpString2 )
    {
      cchCount2 = *(unsigned int *)(a3 + 8);
      if ( (unsigned int)cchCount2 > 0x7FFFFFFF || (a4 = *(unsigned int *)(a2 + 8), (unsigned int)a4 > 0x7FFFFFFF) )
        SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(cchCount2, a2, a3, a4);
      LODWORD(lpString2) = CompareStringW(0x7Fu, 1u, *(PCNZWCH *)a2, a4, lpString2, cchCount2) - 2;
    }
    else
    {
      LODWORD(lpString2) = 1;
    }
    return (unsigned int)lpString2 >> 31;
  }
  if ( !lpString2 )
    return (unsigned int)lpString2 >> 31;
  return 1;
}

```

## disassembly

```asm
0x180051860  sub     rsp, 38h
0x180051864  mov     rax, [r8]
0x180051867  mov     r10, [rdx]
0x18005186a  test    r10, r10
0x18005186d  jz      short loc_1800518B4
0x18005186f  test    rax, rax
0x180051872  jz      short loc_1800518C5
0x180051874  mov     ecx, [r8+8]
0x180051878  cmp     ecx, 7FFFFFFFh
0x18005187e  ja      short loc_1800518CC
0x180051880  mov     r9d, [rdx+8]; cchCount1
0x180051884  cmp     r9d, 7FFFFFFFh
0x18005188b  ja      short loc_1800518CC
0x18005188d  mov     [rsp+38h+cchCount2], ecx; cchCount2
0x180051891  mov     [rsp+38h+lpString2], rax; lpString2
0x180051896  mov     r8, r10; lpString1
0x180051899  mov     edx, 1; dwCmpFlags
0x18005189e  mov     ecx, 7Fh; Locale
0x1800518a3  call    cs:__imp_CompareStringW
0x1800518a9  sub     eax, 2
0x1800518ac  shr     eax, 1Fh
0x1800518af  add     rsp, 38h
0x1800518b3  retn
0x1800518b4  test    rax, rax
0x1800518b7  jz      short loc_1800518AC
0x1800518b9  mov     eax, 1
0x1800518be  add     rsp, 38h
0x1800518c2  retn
0x1800518c3  jmp     short loc_1800518AC
0x1800518c5  mov     eax, 1
0x1800518ca  jmp     short loc_1800518AC
0x1800518cc  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@@@@SAXXZ; SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(void)
```
