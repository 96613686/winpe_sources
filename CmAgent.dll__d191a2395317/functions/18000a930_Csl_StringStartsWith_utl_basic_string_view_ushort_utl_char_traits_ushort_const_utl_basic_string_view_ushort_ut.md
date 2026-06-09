# Csl::StringStartsWith(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &,utl::basic_string_view<ushort,utl::char_traits<ushort>> const &,bool)

- ea: `0x18000a930`
- end: `0x18000a97c`
- name: `?StringStartsWith@Csl@@YA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@0_N@Z`
- size: `76`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001fb70`

## callees

- `0x18000a930`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a960`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a960`

## pseudocode

```c
bool __fastcall Csl::StringStartsWith(__int64 a1, __int64 a2)
{
  unsigned __int64 v3; // rdx
  unsigned __int64 v4; // rax
  const WCHAR *v5; // r8
  const WCHAR *v6; // rcx

  v3 = *(_QWORD *)(a1 + 8);
  if ( !v3 )
    return 0;
  v4 = *(_QWORD *)(a2 + 8);
  if ( !v4 )
    return 0;
  v5 = *(const WCHAR **)a2;
  v6 = *(const WCHAR **)a1;
  if ( v3 >= v4 )
    LODWORD(v3) = v4;
  return CompareStringOrdinal(v6, v3, v5, v4, 1) == 2;
}

```

## disassembly

```asm
0x18000a930  sub     rsp, 38h
0x18000a934  mov     r8, rdx
0x18000a937  mov     rdx, [rcx+8]
0x18000a93b  test    rdx, rdx
0x18000a93e  jz      short loc_18000A974
0x18000a940  mov     rax, [r8+8]
0x18000a944  test    rax, rax
0x18000a947  jz      short loc_18000A974
0x18000a949  mov     r8, [r8]; lpString2
0x18000a94c  cmp     rdx, rax
0x18000a94f  mov     rcx, [rcx]; lpString1
0x18000a952  mov     r9d, eax; cchCount2
0x18000a955  cmovnb  edx, eax; cchCount1
0x18000a958  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18000a960  call    cs:__imp_CompareStringOrdinal
0x18000a967  nop     dword ptr [rax+rax+00h]
0x18000a96c  cmp     eax, 2
0x18000a96f  setz    al
0x18000a972  jmp     short loc_18000A976
0x18000a974  xor     al, al
0x18000a976  add     rsp, 38h
0x18000a97a  retn
```
