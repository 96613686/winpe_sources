# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Tidy_deallocate(void)

- ea: `0x140004c2c`
- end: `0x140004c66`
- name: `?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ`
- size: `58`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x1400049bc`
- `0x140004b00`
- `0x140004da8`
- `0x140004e04`
- `0x140004ed8`
- `0x140004fb0`
- `0x140004fe0`
- `0x1400053b0`
- `0x140005490`

## callees

- `0x140001628`
- `0x140004c2c`

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
0x140004c2c  push    rbx
0x140004c2e  sub     rsp, 20h
0x140004c32  mov     rdx, [rcx+18h]
0x140004c36  mov     rbx, rcx
0x140004c39  cmp     rdx, 7
0x140004c3d  jbe     short loc_140004C4F
0x140004c3f  mov     rcx, [rcx]
0x140004c42  lea     rdx, ds:2[rdx*2]
0x140004c4a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140004c4f  xor     eax, eax
0x140004c51  mov     qword ptr [rbx+18h], 7
0x140004c59  mov     [rbx+10h], rax
0x140004c5d  mov     [rbx], ax
0x140004c60  add     rsp, 20h
0x140004c64  pop     rbx
0x140004c65  retn
```
