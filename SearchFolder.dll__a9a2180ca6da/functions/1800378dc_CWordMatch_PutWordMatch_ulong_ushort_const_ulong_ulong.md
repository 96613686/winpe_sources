# CWordMatch::_PutWordMatch(ulong,ushort const *,ulong,ulong)

- ea: `0x1800378dc`
- end: `0x180037a75`
- name: `?_PutWordMatch@CWordMatch@@AEAAJKPEBGKK@Z`
- size: `409`
- prototype: `int(CWordMatch *__hidden this, unsigned int, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002ef10`
- `0x18002ef20`

## callees

- `0x1800120d0`
- `0x180029d08`
- `0x1800378dc`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180037a4f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180037a4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003796c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800379d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003796c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800379d5`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x1800379c1`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x180037a14`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x1800379c1`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x180037a14`

## pseudocode

```c
__int64 __fastcall CWordMatch::_PutWordMatch(CWordMatch *this, __int64 a2, const unsigned __int16 *a3)
{
  __int64 result; // rax
  __int64 v6; // rcx
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
    v6 = (unsigned int)(*((_DWORD *)this + 137) - 12);
    if ( (_DWORD)v6 )
    {
      if ( (_DWORD)v6 == 1 )
      {
        if ( *((_QWORD *)this + 67) )
        {
          lpStringSource = 0;
          if ( (int)_AllocStringWorker<CTCoAllocPolicy>(v6, a2, a3, (unsigned int)a2) >= 0 )
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
0x1800378dc  mov     [rsp+arg_8], rbx
0x1800378e1  mov     [rsp+arg_10], rsi
0x1800378e6  push    rdi
0x1800378e7  sub     rsp, 50h
0x1800378eb  xor     esi, esi
0x1800378ed  mov     r11d, edx
0x1800378f0  mov     r10, r8
0x1800378f3  mov     rdi, rcx
0x1800378f6  mov     eax, 1
0x1800378fb  cmp     [rcx+220h], esi
0x180037901  jnz     loc_180037A65
0x180037907  mov     ecx, [rcx+224h]
0x18003790d  sub     ecx, 0Ch
0x180037910  jz      loc_180037A27
0x180037916  cmp     ecx, eax
0x180037918  jnz     loc_180037A63
0x18003791e  cmp     [rdi+218h], rsi
0x180037925  jz      loc_1800379E0
0x18003792b  lea     rax, [rsp+58h+pv]
0x180037930  mov     [rsp+58h+lpStringSource], rsi
0x180037935  mov     r9d, r11d
0x180037938  mov     qword ptr [rsp+58h+cchValue], rax
0x18003793d  mov     [rsp+58h+pv], rsi
0x180037942  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180037947  test    eax, eax
0x180037949  js      loc_180037A63
0x18003794f  mov     rdx, [rsp+58h+pv]; unsigned __int16 *
0x180037954  lea     r8, [rsp+58h+lpStringSource]; unsigned __int16 **
0x180037959  lea     rcx, ?g_koreanDecomposition@@3VCKoreanDecomposition@@A; this
0x180037960  call    ?DecomposeKoreanForPrefixMatch@CKoreanDecomposition@@QEAAJPEBGPEAPEAG@Z; CKoreanDecomposition::DecomposeKoreanForPrefixMatch(ushort const *,ushort * *)
0x180037965  mov     rcx, [rsp+58h+pv]; pv
0x18003796a  mov     ebx, eax
0x18003796c  call    cs:__imp_CoTaskMemFree
0x180037972  test    ebx, ebx
0x180037974  js      loc_180037A63
0x18003797a  mov     rcx, [rdi+218h]
0x180037981  or      r9, 0FFFFFFFFFFFFFFFFh
0x180037985  mov     rax, r9
0x180037988  inc     rax
0x18003798b  cmp     [rcx+rax*2], si
0x18003798f  jnz     short loc_180037988
0x180037991  mov     rbx, [rsp+58h+lpStringSource]
0x180037996  inc     r9; cchSource
0x180037999  cmp     [rbx+r9*2], si
0x18003799e  jnz     short loc_180037996
0x1800379a0  mov     edx, [rdi+22Ch]
0x1800379a6  mov     r8, rbx; lpStringSource
0x1800379a9  mov     [rsp+58h+pcchFound], rsi; pcchFound
0x1800379ae  bts     edx, 14h; dwFindNLSStringFlags
0x1800379b2  mov     [rsp+58h+cchValue], eax; cchValue
0x1800379b6  mov     [rsp+58h+lpStringValue], rcx; lpStringValue
0x1800379bb  mov     ecx, [rdi+228h]; Locale
0x1800379c1  call    cs:__imp_FindNLSString
0x1800379c7  not     eax
0x1800379c9  mov     rcx, rbx; pv
0x1800379cc  shr     eax, 1Fh
0x1800379cf  mov     [rdi+220h], eax
0x1800379d5  call    cs:__imp_CoTaskMemFree
0x1800379db  jmp     loc_180037A63
0x1800379e0  lea     rax, [rdi+0Ch]
0x1800379e4  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800379e8  inc     r9
0x1800379eb  cmp     [rax+r9*2], si
0x1800379f0  jnz     short loc_1800379E8
0x1800379f2  mov     edx, [rdi+22Ch]
0x1800379f8  mov     ecx, [rdi+228h]; Locale
0x1800379fe  bts     edx, 14h; dwFindNLSStringFlags
0x180037a02  mov     [rsp+58h+pcchFound], rsi; pcchFound
0x180037a07  mov     [rsp+58h+cchValue], r9d; cchValue
0x180037a0c  mov     r9d, r11d; cchSource
0x180037a0f  mov     [rsp+58h+lpStringValue], rax; lpStringValue
0x180037a14  call    cs:__imp_FindNLSString
0x180037a1a  not     eax
0x180037a1c  shr     eax, 1Fh
0x180037a1f  mov     [rdi+220h], eax
0x180037a25  jmp     short loc_180037A63
0x180037a27  lea     r8, [rdi+0Ch]; lpString1
0x180037a2b  or      r9, 0FFFFFFFFFFFFFFFFh
0x180037a2f  inc     r9; cchCount1
0x180037a32  cmp     [r8+r9*2], si
0x180037a37  jnz     short loc_180037A2F
0x180037a39  mov     edx, [rdi+22Ch]; dwCmpFlags
0x180037a3f  mov     ecx, [rdi+228h]; Locale
0x180037a45  mov     [rsp+58h+cchValue], r11d; cchCount2
0x180037a4a  mov     [rsp+58h+lpStringValue], r10; lpString2
0x180037a4f  call    cs:__imp_CompareStringW
0x180037a55  mov     ecx, esi
0x180037a57  cmp     eax, 2
0x180037a5a  setz    cl
0x180037a5d  mov     [rdi+220h], ecx
0x180037a63  mov     eax, esi
0x180037a65  mov     rbx, [rsp+58h+arg_8]
0x180037a6a  mov     rsi, [rsp+58h+arg_10]
0x180037a6f  add     rsp, 50h
0x180037a73  pop     rdi
0x180037a74  retn
```
