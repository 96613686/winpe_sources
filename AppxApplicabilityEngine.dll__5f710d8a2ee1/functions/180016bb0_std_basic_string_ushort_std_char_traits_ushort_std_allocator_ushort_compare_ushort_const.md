# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::compare(ushort const *)

- ea: `0x180016bb0`
- end: `0x180016bd8`
- name: `?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHPEBG@Z`
- size: `40`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002230`
- `0x18001f3ec`

## callees

- `0x180008ec0`
- `0x180016bb0`

## pseudocode

```c
__int64 __fastcall std::wstring::compare(__int64 a1, __int64 a2)
{
  __int64 v2; // rax

  v2 = -1;
  do
    ++v2;
  while ( *(_WORD *)(a2 + 2 * v2) );
  return std::wstring::compare(a1, a2, *(_QWORD *)(a1 + 16), a2, v2);
}

```

## disassembly

```asm
0x180016bb0  sub     rsp, 38h
0x180016bb4  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016bb8  inc     rax
0x180016bbb  cmp     word ptr [rdx+rax*2], 0
0x180016bc0  jnz     short loc_180016BB8
0x180016bc2  mov     r8, [rcx+10h]
0x180016bc6  mov     r9, rdx
0x180016bc9  mov     [rsp+38h+var_18], rax
0x180016bce  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAH_K0PEBG0@Z; std::wstring::compare(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)
0x180016bd3  add     rsp, 38h
0x180016bd7  retn
```
