# CWordMatch::_PutWordMatch(ulong,ushort const *,ulong,ulong)

- ea: `0x18004af80`
- end: `0x18004b119`
- name: `?_PutWordMatch@CWordMatch@@AEAAJKPEBGKK@Z`
- size: `409`
- prototype: `int(CWordMatch *__hidden this, unsigned int, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180047be0`
- `0x180047bf0`

## callees

- `0x18001f424`
- `0x180044b70`
- `0x18004af80`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18004b065`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18004b0b8`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18004b065`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18004b0b8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004b0f3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004b0f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b010`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b079`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b010`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b079`

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
          if ( (int)_AllocStringWorker<CTCoAllocPolicy>(v6, a2, a3) >= 0 )
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
0x18004af80  mov     [rsp+arg_8], rbx
0x18004af85  mov     [rsp+arg_10], rsi
0x18004af8a  push    rdi
0x18004af8b  sub     rsp, 50h
0x18004af8f  xor     esi, esi
0x18004af91  mov     r11d, edx
0x18004af94  mov     r10, r8
0x18004af97  mov     rdi, rcx
0x18004af9a  mov     eax, 1
0x18004af9f  cmp     [rcx+220h], esi
0x18004afa5  jnz     loc_18004B109
0x18004afab  mov     ecx, [rcx+224h]
0x18004afb1  sub     ecx, 0Ch
0x18004afb4  jz      loc_18004B0CB
0x18004afba  cmp     ecx, eax
0x18004afbc  jnz     loc_18004B107
0x18004afc2  cmp     [rdi+218h], rsi
0x18004afc9  jz      loc_18004B084
0x18004afcf  lea     rax, [rsp+58h+pv]
0x18004afd4  mov     [rsp+58h+lpStringSource], rsi
0x18004afd9  mov     r9d, r11d
0x18004afdc  mov     qword ptr [rsp+58h+cchValue], rax
0x18004afe1  mov     [rsp+58h+pv], rsi
0x18004afe6  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18004afeb  test    eax, eax
0x18004afed  js      loc_18004B107
0x18004aff3  mov     rdx, [rsp+58h+pv]; unsigned __int16 *
0x18004aff8  lea     r8, [rsp+58h+lpStringSource]; unsigned __int16 **
0x18004affd  lea     rcx, ?g_koreanDecomposition@@3VCKoreanDecomposition@@A; this
0x18004b004  call    ?DecomposeKoreanForPrefixMatch@CKoreanDecomposition@@QEAAJPEBGPEAPEAG@Z; CKoreanDecomposition::DecomposeKoreanForPrefixMatch(ushort const *,ushort * *)
0x18004b009  mov     rcx, [rsp+58h+pv]; pv
0x18004b00e  mov     ebx, eax
0x18004b010  call    cs:__imp_CoTaskMemFree
0x18004b016  test    ebx, ebx
0x18004b018  js      loc_18004B107
0x18004b01e  mov     rcx, [rdi+218h]
0x18004b025  or      r9, 0FFFFFFFFFFFFFFFFh
0x18004b029  mov     rax, r9
0x18004b02c  inc     rax
0x18004b02f  cmp     [rcx+rax*2], si
0x18004b033  jnz     short loc_18004B02C
0x18004b035  mov     rbx, [rsp+58h+lpStringSource]
0x18004b03a  inc     r9; cchSource
0x18004b03d  cmp     [rbx+r9*2], si
0x18004b042  jnz     short loc_18004B03A
0x18004b044  mov     edx, [rdi+22Ch]
0x18004b04a  mov     r8, rbx; lpStringSource
0x18004b04d  mov     [rsp+58h+pcchFound], rsi; pcchFound
0x18004b052  bts     edx, 14h; dwFindNLSStringFlags
0x18004b056  mov     [rsp+58h+cchValue], eax; cchValue
0x18004b05a  mov     [rsp+58h+lpStringValue], rcx; lpStringValue
0x18004b05f  mov     ecx, [rdi+228h]; Locale
0x18004b065  call    cs:__imp_FindNLSString
0x18004b06b  not     eax
0x18004b06d  mov     rcx, rbx; pv
0x18004b070  shr     eax, 1Fh
0x18004b073  mov     [rdi+220h], eax
0x18004b079  call    cs:__imp_CoTaskMemFree
0x18004b07f  jmp     loc_18004B107
0x18004b084  lea     rax, [rdi+0Ch]
0x18004b088  or      r9, 0FFFFFFFFFFFFFFFFh
0x18004b08c  inc     r9
0x18004b08f  cmp     [rax+r9*2], si
0x18004b094  jnz     short loc_18004B08C
0x18004b096  mov     edx, [rdi+22Ch]
0x18004b09c  mov     ecx, [rdi+228h]; Locale
0x18004b0a2  bts     edx, 14h; dwFindNLSStringFlags
0x18004b0a6  mov     [rsp+58h+pcchFound], rsi; pcchFound
0x18004b0ab  mov     [rsp+58h+cchValue], r9d; cchValue
0x18004b0b0  mov     r9d, r11d; cchSource
0x18004b0b3  mov     [rsp+58h+lpStringValue], rax; lpStringValue
0x18004b0b8  call    cs:__imp_FindNLSString
0x18004b0be  not     eax
0x18004b0c0  shr     eax, 1Fh
0x18004b0c3  mov     [rdi+220h], eax
0x18004b0c9  jmp     short loc_18004B107
0x18004b0cb  lea     r8, [rdi+0Ch]; lpString1
0x18004b0cf  or      r9, 0FFFFFFFFFFFFFFFFh
0x18004b0d3  inc     r9; cchCount1
0x18004b0d6  cmp     [r8+r9*2], si
0x18004b0db  jnz     short loc_18004B0D3
0x18004b0dd  mov     edx, [rdi+22Ch]; dwCmpFlags
0x18004b0e3  mov     ecx, [rdi+228h]; Locale
0x18004b0e9  mov     [rsp+58h+cchValue], r11d; cchCount2
0x18004b0ee  mov     [rsp+58h+lpStringValue], r10; lpString2
0x18004b0f3  call    cs:__imp_CompareStringW
0x18004b0f9  mov     ecx, esi
0x18004b0fb  cmp     eax, 2
0x18004b0fe  setz    cl
0x18004b101  mov     [rdi+220h], ecx
0x18004b107  mov     eax, esi
0x18004b109  mov     rbx, [rsp+58h+arg_8]
0x18004b10e  mov     rsi, [rsp+58h+arg_10]
0x18004b113  add     rsp, 50h
0x18004b117  pop     rdi
0x18004b118  retn
```
