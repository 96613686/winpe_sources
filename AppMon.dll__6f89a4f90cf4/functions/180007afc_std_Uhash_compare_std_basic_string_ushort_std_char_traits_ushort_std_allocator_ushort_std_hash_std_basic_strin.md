# std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>::operator()<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180007afc`
- end: `0x180007b49`
- name: `??$?RV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V01@@?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z`
- size: `77`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007f08`
- `0x180009b90`
- `0x18000d96c`

## callees

- `0x180007afc`
- `0x180009f34`

## pseudocode

```c
bool __fastcall std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  const wchar_t *v3; // r9
  __int64 v4; // rcx
  const wchar_t *v5; // rax
  size_t v6; // r8

  v3 = (const wchar_t *)a3;
  v4 = *(_QWORD *)(a3 + 16);
  v5 = (const wchar_t *)a2;
  if ( *(_QWORD *)(a3 + 24) > 7u )
    v3 = *(const wchar_t **)a3;
  v6 = *(_QWORD *)(a2 + 16);
  if ( *(_QWORD *)(a2 + 24) > 7u )
    v5 = *(const wchar_t **)a2;
  if ( v6 != v4 )
    return 1;
  if ( v6 )
    return wmemcmp(v5, v3, v6) != 0;
  return 0;
}

```

## disassembly

```asm
0x180007afc  sub     rsp, 28h
0x180007b00  cmp     qword ptr [r8+18h], 7
0x180007b05  mov     r9, r8
0x180007b08  mov     rcx, [r8+10h]
0x180007b0c  mov     rax, rdx
0x180007b0f  jbe     short loc_180007B14
0x180007b11  mov     r9, [r8]
0x180007b14  cmp     qword ptr [rdx+18h], 7
0x180007b19  mov     r8, [rdx+10h]; N
0x180007b1d  jbe     short loc_180007B22
0x180007b1f  mov     rax, [rdx]
0x180007b22  cmp     r8, rcx
0x180007b25  jz      short loc_180007B2B
0x180007b27  mov     al, 1
0x180007b29  jmp     short loc_180007B44
0x180007b2b  test    r8, r8
0x180007b2e  jnz     short loc_180007B34
0x180007b30  xor     al, al
0x180007b32  jmp     short loc_180007B44
0x180007b34  mov     rdx, r9; S2
0x180007b37  mov     rcx, rax; S1
0x180007b3a  call    wmemcmp
0x180007b3f  test    eax, eax
0x180007b41  setnz   al
0x180007b44  add     rsp, 28h
0x180007b48  retn
```
