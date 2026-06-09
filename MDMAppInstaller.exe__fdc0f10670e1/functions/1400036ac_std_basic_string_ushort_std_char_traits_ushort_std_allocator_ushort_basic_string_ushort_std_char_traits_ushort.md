# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(ushort const *)

- ea: `0x1400036ac`
- end: `0x1400036e5`
- name: `??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z`
- size: `57`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `28`
- callee_count: `2`
- tags: ``

## callers

- `0x140004128`
- `0x140006dc8`
- `0x1400071a0`
- `0x14000a39c`
- `0x14000a5e0`
- `0x14000d470`
- `0x14000d898`
- `0x14000e194`
- `0x14000e9bc`
- `0x140010a2c`
- `0x140015a38`
- `0x1400165f8`
- `0x1400177bc`
- `0x140017c9c`
- `0x140018b40`
- `0x140018d08`
- `0x140018e48`
- `0x140019054`
- `0x1400196dc`
- `0x14001984c`
- `0x140019c6c`
- `0x140019d68`
- `0x140019e94`
- `0x140019fcc`
- `0x14001a0c4`
- `0x14001a244`
- `0x14001a418`
- `0x14001a550`

## callees

- `0x140006604`
- `0x1400068c8`

## pseudocode

```c
__int64 __fastcall std::wstring::wstring(__int64 a1, __int64 a2)
{
  __int64 v3; // rax
  __int64 v4; // rcx

  *(_QWORD *)(a1 + 24) = 7;
  *(_QWORD *)(a1 + 16) = 0;
  *(_WORD *)a1 = 0;
  v3 = std::char_traits<unsigned short>::length(a2);
  std::wstring::assign(a1, v4, v3);
  return a1;
}

```

## disassembly

```asm
0x1400036ac  push    rbx
0x1400036ae  sub     rsp, 20h
0x1400036b2  xor     eax, eax
0x1400036b4  mov     qword ptr [rcx+18h], 7
0x1400036bc  mov     [rcx+10h], rax
0x1400036c0  mov     rbx, rcx
0x1400036c3  mov     [rcx], ax
0x1400036c6  mov     rcx, rdx
0x1400036c9  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x1400036ce  mov     rdx, rcx
0x1400036d1  mov     r8, rax
0x1400036d4  mov     rcx, rbx
0x1400036d7  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1400036dc  mov     rax, rbx
0x1400036df  add     rsp, 20h
0x1400036e3  pop     rbx
0x1400036e4  retn
```
