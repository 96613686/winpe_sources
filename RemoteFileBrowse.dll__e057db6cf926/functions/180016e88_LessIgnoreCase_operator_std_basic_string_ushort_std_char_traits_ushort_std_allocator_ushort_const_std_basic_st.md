# LessIgnoreCase::operator()(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180016e88`
- end: `0x180016efb`
- name: `??RLessIgnoreCase@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `115`
- prototype: `bool __fastcall(__int64, __int64 *, __int64 *, const char *)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d5c4`
- `0x18000d6b8`
- `0x18000d740`
- `0x18000da44`
- `0x180013bb0`
- `0x180014080`

## callees

- `0x180016e88`
- `0x180017334`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180016ec6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180016ec6`

## pseudocode

```c
bool __fastcall LessIgnoreCase::operator()(__int64 a1, __int64 *a2, __int64 *a3, const char *a4)
{
  const WCHAR *v4; // rax
  int v5; // r9d
  int v6; // edx
  int v7; // eax
  unsigned int v8; // r8d
  const char *v9; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = (const WCHAR *)a2;
  if ( (unsigned __int64)a2[2] > 0x7FFFFFFF || (unsigned __int64)a3[2] > 0x7FFFFFFF )
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, (void *)0x172, (unsigned int)a3, a4);
  v5 = *((_DWORD *)a3 + 4);
  if ( (unsigned __int64)a3[3] > 7 )
    a3 = (__int64 *)*a3;
  v6 = *((_DWORD *)a2 + 4);
  if ( *((_QWORD *)v4 + 3) > 7u )
    v4 = *(const WCHAR **)v4;
  v7 = CompareStringOrdinal(v4, v6, (LPCWCH)a3, v5, 1);
  if ( !v7 )
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, (void *)0x17A, v8, v9);
  return v7 == 1;
}

```

## disassembly

```asm
0x180016e88  sub     rsp, 38h
0x180016e8c  mov     ecx, 7FFFFFFFh
0x180016e91  mov     rax, rdx
0x180016e94  cmp     [rdx+10h], rcx
0x180016e98  ja      short loc_180016EEB
0x180016e9a  cmp     [r8+10h], rcx
0x180016e9e  ja      short loc_180016EEB
0x180016ea0  cmp     qword ptr [r8+18h], 7
0x180016ea5  mov     r9d, [r8+10h]; cchCount2
0x180016ea9  jbe     short loc_180016EAE
0x180016eab  mov     r8, [r8]; lpString2
0x180016eae  cmp     qword ptr [rax+18h], 7
0x180016eb3  mov     edx, [rdx+10h]; cchCount1
0x180016eb6  jbe     short loc_180016EBB
0x180016eb8  mov     rax, [rax]
0x180016ebb  mov     rcx, rax; lpString1
0x180016ebe  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180016ec6  call    cs:__imp_CompareStringOrdinal
0x180016ecc  test    eax, eax
0x180016ece  jz      short loc_180016EDB
0x180016ed0  cmp     eax, 1
0x180016ed3  setz    al
0x180016ed6  add     rsp, 38h
0x180016eda  retn
0x180016edb  mov     rcx, [rsp+38h]; this
0x180016ee0  mov     edx, 17Ah; void *
0x180016ee5  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180016eeb  mov     rcx, [rsp+38h]; this
0x180016ef0  mov     edx, 172h; void *
0x180016ef5  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
