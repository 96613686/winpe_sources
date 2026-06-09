# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Tidy_deallocate(void)

- ea: `0x14000df28`
- end: `0x14000df62`
- name: `?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ`
- size: `58`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x140005c14`
- `0x14000628c`
- `0x1400063b0`
- `0x140007ad8`
- `0x1400082e8`
- `0x14000b0cc`
- `0x14000d384`
- `0x14000d940`
- `0x14000fa90`
- `0x1400100e0`
- `0x140010ce8`
- `0x1400122f8`
- `0x140014900`
- `0x140014db4`

## callees

- `0x140004f44`
- `0x14000df28`

## pseudocode

```c
__int64 __fastcall std::wstring::_Tidy_deallocate(_QWORD *a1)
{
  unsigned __int64 v1; // rdx
  __int64 result; // rax

  v1 = a1[3];
  if ( v1 > 7 )
    std::_Deallocate<16>(*a1, 2 * v1 + 2);
  result = 0;
  a1[3] = 7;
  a1[2] = 0;
  *(_WORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x14000df28  push    rbx
0x14000df2a  sub     rsp, 20h
0x14000df2e  mov     rdx, [rcx+18h]
0x14000df32  mov     rbx, rcx
0x14000df35  cmp     rdx, 7
0x14000df39  jbe     short loc_14000DF4B
0x14000df3b  mov     rcx, [rcx]
0x14000df3e  lea     rdx, ds:2[rdx*2]
0x14000df46  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14000df4b  xor     eax, eax
0x14000df4d  mov     qword ptr [rbx+18h], 7
0x14000df55  mov     [rbx+10h], rax
0x14000df59  mov     [rbx], ax
0x14000df5c  add     rsp, 20h
0x14000df60  pop     rbx
0x14000df61  retn
```
