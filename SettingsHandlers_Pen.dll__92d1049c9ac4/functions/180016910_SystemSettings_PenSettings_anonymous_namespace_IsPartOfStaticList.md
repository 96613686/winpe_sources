# SystemSettings::PenSettings::_anonymous_namespace_::IsPartOfStaticList

- ea: `0x180016910`
- end: `0x18001696f`
- name: `SystemSettings::PenSettings::_anonymous_namespace_::IsPartOfStaticList`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800159f8`

## callees

- `0x180016910`
- `0x180019fcc`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001694a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001694a`

## pseudocode

```c
char __fastcall SystemSettings::PenSettings::_anonymous_namespace_::IsPartOfStaticList(__int64 a1, __int64 a2)
{
  __int64 i; // rbx
  const WCHAR *v5; // rax

  for ( i = 0; !(_DWORD)i; i = 1 )
  {
    v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
    if ( CompareStringOrdinal(v5, -1, *(LPCWCH *)(a2 + 8 * i), -1, 1) == 2 )
      return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180016910  mov     [rsp+arg_0], rbx
0x180016915  mov     [rsp+arg_8], rsi
0x18001691a  push    rdi
0x18001691b  sub     rsp, 30h
0x18001691f  mov     rdi, rdx
0x180016922  mov     rsi, rcx
0x180016925  xor     ebx, ebx
0x180016927  cmp     ebx, 1
0x18001692a  jnb     short loc_18001695D
0x18001692c  mov     rcx, rsi
0x18001692f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180016934  mov     r8, [rdi+rbx*8]; lpString2
0x180016938  or      r9d, 0FFFFFFFFh; cchCount2
0x18001693c  or      edx, r9d; cchCount1
0x18001693f  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180016947  mov     rcx, rax; lpString1
0x18001694a  call    cs:__imp_CompareStringOrdinal
0x180016950  cmp     eax, 2
0x180016953  jz      short loc_180016959
0x180016955  inc     ebx
0x180016957  jmp     short loc_180016927
0x180016959  mov     al, 1
0x18001695b  jmp     short loc_18001695F
0x18001695d  xor     al, al
0x18001695f  mov     rbx, [rsp+38h+arg_0]
0x180016964  mov     rsi, [rsp+38h+arg_8]
0x180016969  add     rsp, 30h
0x18001696d  pop     rdi
0x18001696e  retn
```
