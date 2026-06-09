# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::compare(unsigned __int64,unsigned __int64,wchar_t const *,unsigned __int64)

- ea: `0x18000ecac`
- end: `0x18000ed0c`
- name: `?compare@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAH_K0PEB_W0@Z`
- size: `96`
- prototype: `__int64 __fastcall(_QWORD *, __int64, unsigned __int64, _WORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000d1e8`

## callees

- `0x18000ecac`

## pseudocode

```c
__int64 __fastcall std::wstring::compare(_QWORD *a1, __int64 a2, unsigned __int64 a3, _WORD *a4, unsigned __int64 a5)
{
  unsigned __int64 v6; // rax

  if ( a1[2] < a3 )
    a3 = a1[2];
  v6 = a5;
  if ( a3 < a5 )
    v6 = a3;
  if ( a1[3] >= 8u )
    a1 = (_QWORD *)*a1;
  if ( v6 )
  {
    while ( v6 )
    {
      if ( *(_WORD *)a1 != *a4 )
        return *(_WORD *)a1 < *a4 ? -1 : 1;
      a1 = (_QWORD *)((char *)a1 + 2);
      ++a4;
      --v6;
    }
  }
  if ( a3 >= a5 )
    return a3 != a5;
  else
    return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18000ecac  cmp     [rcx+10h], r8
0x18000ecb0  mov     r10, r9
0x18000ecb3  mov     rdx, [rsp+arg_20]
0x18000ecb8  cmovb   r8, [rcx+10h]
0x18000ecbd  mov     rax, rdx
0x18000ecc0  cmp     r8, rdx
0x18000ecc3  cmovb   rax, r8
0x18000ecc7  cmp     qword ptr [rcx+18h], 8
0x18000eccc  jb      short loc_18000ECD1
0x18000ecce  mov     rcx, [rcx]
0x18000ecd1  test    rax, rax
0x18000ecd4  jz      short loc_18000ECFA
0x18000ecd6  test    rax, rax
0x18000ecd9  jz      short loc_18000ECFA
0x18000ecdb  movzx   r9d, word ptr [rcx]
0x18000ecdf  cmp     r9w, [r10]
0x18000ece3  jnz     short loc_18000ECF2
0x18000ece5  add     rcx, 2
0x18000ece9  add     r10, 2
0x18000eced  dec     rax
0x18000ecf0  jmp     short loc_18000ECD6
0x18000ecf2  sbb     eax, eax
0x18000ecf4  and     eax, 0FFFFFFFEh
0x18000ecf7  inc     eax
0x18000ecf9  retn
0x18000ecfa  cmp     r8, rdx
0x18000ecfd  jnb     short loc_18000ED03
0x18000ecff  or      eax, 0FFFFFFFFh
0x18000ed02  retn
0x18000ed03  xor     eax, eax
0x18000ed05  cmp     r8, rdx
0x18000ed08  setnz   al
0x18000ed0b  retn
```
