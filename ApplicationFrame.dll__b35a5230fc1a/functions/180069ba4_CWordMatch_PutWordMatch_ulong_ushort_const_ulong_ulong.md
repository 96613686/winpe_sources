# CWordMatch::_PutWordMatch(ulong,ushort const *,ulong,ulong)

- ea: `0x180069ba4`
- end: `0x180069d3d`
- name: `?_PutWordMatch@CWordMatch@@AEAAJKPEBGKK@Z`
- size: `409`
- prototype: `int(CWordMatch *__hidden this, unsigned int, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180066830`
- `0x180066840`

## callees

- `0x180025a98`
- `0x180063a34`
- `0x180069ba4`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x180069c89`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x180069cdc`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x180069c89`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x180069cdc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180069d17`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180069d17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069c34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069c9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069c34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069c9d`

## pseudocode

```c
__int64 __fastcall CWordMatch::_PutWordMatch(CWordMatch *this, int a2, const unsigned __int16 *a3)
{
  __int64 result; // rax
  int v6; // ecx
  int v7; // ebx
  const WCHAR *lpStringValue; // rcx
  __int64 v9; // r9
  __int64 cchValue; // rax
  WCHAR *v11; // rbx
  __int64 v12; // r9
  const WCHAR *v13; // r8
  __int64 v14; // r9
  LPCWSTR lpStringSource; // [rsp+40h] [rbp-18h] BYREF

  result = 1;
  if ( !*((_DWORD *)this + 136) )
  {
    v6 = *((_DWORD *)this + 137) - 12;
    if ( v6 )
    {
      if ( v6 == 1 )
      {
        if ( *((_QWORD *)this + 67) )
        {
          lpStringSource = 0;
          if ( (int)_AllocStringWorker<CTCoAllocPolicy>(1, a2, (_DWORD)a3, a2) >= 0 )
          {
            v7 = CKoreanDecomposition::DecomposeKoreanForPrefixMatch(
                   (CKoreanDecomposition *)g_koreanDecomposition,
                   0,
                   (unsigned __int16 **)&lpStringSource);
            CoTaskMemFree(0);
            if ( v7 >= 0 )
            {
              lpStringValue = (const WCHAR *)*((_QWORD *)this + 67);
              v9 = -1;
              cchValue = -1;
              do
                ++cchValue;
              while ( lpStringValue[cchValue] );
              v11 = (WCHAR *)lpStringSource;
              do
                ++v9;
              while ( lpStringSource[v9] );
              *((_DWORD *)this + 136) = FindNLSString(
                                          *((_DWORD *)this + 138),
                                          *((_DWORD *)this + 139) | 0x100000,
                                          lpStringSource,
                                          v9,
                                          lpStringValue,
                                          cchValue,
                                          0) >= 0;
              CoTaskMemFree(v11);
            }
          }
        }
        else
        {
          v12 = -1;
          do
            ++v12;
          while ( *((_WORD *)this + v12 + 6) );
          *((_DWORD *)this + 136) = FindNLSString(
                                      *((_DWORD *)this + 138),
                                      *((_DWORD *)this + 139) | 0x100000,
                                      a3,
                                      a2,
                                      (LPCWSTR)this + 6,
                                      v12,
                                      0) >= 0;
        }
      }
    }
    else
    {
      v13 = (const WCHAR *)((char *)this + 12);
      v14 = -1;
      do
        ++v14;
      while ( v13[v14] );
      *((_DWORD *)this + 136) = CompareStringW(*((_DWORD *)this + 138), *((_DWORD *)this + 139), v13, v14, a3, a2) == 2;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180069ba4  mov     [rsp+arg_8], rbx
0x180069ba9  mov     [rsp+arg_10], rsi
0x180069bae  push    rdi
0x180069baf  sub     rsp, 50h
0x180069bb3  xor     esi, esi
0x180069bb5  mov     r11d, edx
0x180069bb8  mov     r10, r8
0x180069bbb  mov     rdi, rcx
0x180069bbe  mov     eax, 1
0x180069bc3  cmp     [rcx+220h], esi
0x180069bc9  jnz     loc_180069D2D
0x180069bcf  mov     ecx, [rcx+224h]
0x180069bd5  sub     ecx, 0Ch
0x180069bd8  jz      loc_180069CEF
0x180069bde  cmp     ecx, eax
0x180069be0  jnz     loc_180069D2B
0x180069be6  cmp     [rdi+218h], rsi
0x180069bed  jz      loc_180069CA8
0x180069bf3  lea     rax, [rsp+58h+pv]
0x180069bf8  mov     [rsp+58h+lpStringSource], rsi
0x180069bfd  mov     r9d, r11d
0x180069c00  mov     qword ptr [rsp+58h+cchValue], rax
0x180069c05  mov     [rsp+58h+pv], rsi
0x180069c0a  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180069c0f  test    eax, eax
0x180069c11  js      loc_180069D2B
0x180069c17  mov     rdx, [rsp+58h+pv]; unsigned __int16 *
0x180069c1c  lea     r8, [rsp+58h+lpStringSource]; unsigned __int16 **
0x180069c21  lea     rcx, ?g_koreanDecomposition@@3VCKoreanDecomposition@@A; this
0x180069c28  call    ?DecomposeKoreanForPrefixMatch@CKoreanDecomposition@@QEAAJPEBGPEAPEAG@Z; CKoreanDecomposition::DecomposeKoreanForPrefixMatch(ushort const *,ushort * *)
0x180069c2d  mov     rcx, [rsp+58h+pv]; pv
0x180069c32  mov     ebx, eax
0x180069c34  call    cs:__imp_CoTaskMemFree
0x180069c3a  test    ebx, ebx
0x180069c3c  js      loc_180069D2B
0x180069c42  mov     rcx, [rdi+218h]
0x180069c49  or      r9, 0FFFFFFFFFFFFFFFFh
0x180069c4d  mov     rax, r9
0x180069c50  inc     rax
0x180069c53  cmp     [rcx+rax*2], si
0x180069c57  jnz     short loc_180069C50
0x180069c59  mov     rbx, [rsp+58h+lpStringSource]
0x180069c5e  inc     r9; cchSource
0x180069c61  cmp     [rbx+r9*2], si
0x180069c66  jnz     short loc_180069C5E
0x180069c68  mov     edx, [rdi+22Ch]
0x180069c6e  mov     r8, rbx; lpStringSource
0x180069c71  mov     [rsp+58h+pcchFound], rsi; pcchFound
0x180069c76  bts     edx, 14h; dwFindNLSStringFlags
0x180069c7a  mov     [rsp+58h+cchValue], eax; cchValue
0x180069c7e  mov     [rsp+58h+lpStringValue], rcx; lpStringValue
0x180069c83  mov     ecx, [rdi+228h]; Locale
0x180069c89  call    cs:__imp_FindNLSString
0x180069c8f  not     eax
0x180069c91  mov     rcx, rbx; pv
0x180069c94  shr     eax, 1Fh
0x180069c97  mov     [rdi+220h], eax
0x180069c9d  call    cs:__imp_CoTaskMemFree
0x180069ca3  jmp     loc_180069D2B
0x180069ca8  lea     rax, [rdi+0Ch]
0x180069cac  or      r9, 0FFFFFFFFFFFFFFFFh
0x180069cb0  inc     r9
0x180069cb3  cmp     [rax+r9*2], si
0x180069cb8  jnz     short loc_180069CB0
0x180069cba  mov     edx, [rdi+22Ch]
0x180069cc0  mov     ecx, [rdi+228h]; Locale
0x180069cc6  bts     edx, 14h; dwFindNLSStringFlags
0x180069cca  mov     [rsp+58h+pcchFound], rsi; pcchFound
0x180069ccf  mov     [rsp+58h+cchValue], r9d; cchValue
0x180069cd4  mov     r9d, r11d; cchSource
0x180069cd7  mov     [rsp+58h+lpStringValue], rax; lpStringValue
0x180069cdc  call    cs:__imp_FindNLSString
0x180069ce2  not     eax
0x180069ce4  shr     eax, 1Fh
0x180069ce7  mov     [rdi+220h], eax
0x180069ced  jmp     short loc_180069D2B
0x180069cef  lea     r8, [rdi+0Ch]; lpString1
0x180069cf3  or      r9, 0FFFFFFFFFFFFFFFFh
0x180069cf7  inc     r9; cchCount1
0x180069cfa  cmp     [r8+r9*2], si
0x180069cff  jnz     short loc_180069CF7
0x180069d01  mov     edx, [rdi+22Ch]; dwCmpFlags
0x180069d07  mov     ecx, [rdi+228h]; Locale
0x180069d0d  mov     [rsp+58h+cchValue], r11d; cchCount2
0x180069d12  mov     [rsp+58h+lpStringValue], r10; lpString2
0x180069d17  call    cs:__imp_CompareStringW
0x180069d1d  mov     ecx, esi
0x180069d1f  cmp     eax, 2
0x180069d22  setz    cl
0x180069d25  mov     [rdi+220h], ecx
0x180069d2b  mov     eax, esi
0x180069d2d  mov     rbx, [rsp+58h+arg_8]
0x180069d32  mov     rsi, [rsp+58h+arg_10]
0x180069d37  add     rsp, 50h
0x180069d3b  pop     rdi
0x180069d3c  retn
```
