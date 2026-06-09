# TranslatePath(ushort const *,ushort *,ulong)

- ea: `0x18000fa60`
- end: `0x18000fad6`
- name: `?TranslatePath@@YAJPEBGPEAGK@Z`
- size: `118`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b8f8`
- `0x18000bf1c`

## callees

- `0x180005e24`
- `0x180005e98`
- `0x18000fa60`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000fa7d`
- `msvcrt!_wcsnicmp` at `0x18000fa7d`

## pseudocode

```c
__int64 __fastcall TranslatePath(unsigned __int16 *a1, unsigned __int16 *a2)
{
  if ( _wcsnicmp(a1, L"$(_prov)\\", 9u) )
    return StringCchCopyW(a2, 0x104u, a1);
  if ( a1[9] )
    return StringCchPrintfW(a2, 0x104u, L"%s\\%s", L"prov", a1 + 9);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000fa60  mov     [rsp+arg_0], rbx
0x18000fa65  push    rdi
0x18000fa66  sub     rsp, 30h
0x18000fa6a  mov     rdi, rdx
0x18000fa6d  mov     r8d, 9; MaxCount
0x18000fa73  lea     rdx, aProv; "$(_prov)\\"
0x18000fa7a  mov     rbx, rcx
0x18000fa7d  call    cs:__imp__wcsnicmp
0x18000fa83  xor     ecx, ecx
0x18000fa85  test    eax, eax
0x18000fa87  jnz     short loc_18000FABB
0x18000fa89  lea     rax, [rbx+12h]
0x18000fa8d  cmp     [rax], cx
0x18000fa90  jnz     short loc_18000FA99
0x18000fa92  mov     eax, 80070057h
0x18000fa97  jmp     short loc_18000FACB
0x18000fa99  lea     r9, aProv_0; "prov"
0x18000faa0  mov     [rsp+38h+var_18], rax
0x18000faa5  lea     r8, aSS; "%s\\%s"
0x18000faac  mov     edx, 104h; unsigned __int64
0x18000fab1  mov     rcx, rdi; unsigned __int16 *
0x18000fab4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000fab9  jmp     short loc_18000FACB
0x18000fabb  mov     r8, rbx; unsigned __int16 *
0x18000fabe  mov     edx, 104h; unsigned __int64
0x18000fac3  mov     rcx, rdi; unsigned __int16 *
0x18000fac6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000facb  mov     rbx, [rsp+38h+arg_0]
0x18000fad0  add     rsp, 30h
0x18000fad4  pop     rdi
0x18000fad5  retn
```
