# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x1400087c4`
- end: `0x1400087f4`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `48`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `12`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140012130`
- `0x14001215c`
- `0x1400123b4`
- `0x1400123c6`
- `0x1400123f2`
- `0x14001241e`
- `0x1400124ca`
- `0x1400125db`
- `0x1400125ed`
- `0x1400125ff`
- `0x140012611`
- `0x140012623`

## callees

- `0x1400087c4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1400087d7`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400087d7`

## pseudocode

```c
__int64 __fastcall std::wstring::~wstring(__int64 a1)
{
  __int64 result; // rax

  if ( *(_QWORD *)(a1 + 24) >= 8u )
    operator delete(*(void **)a1);
  result = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_QWORD *)(a1 + 16) = 0;
  *(_WORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x1400087c4  push    rbx
0x1400087c6  sub     rsp, 20h
0x1400087ca  cmp     qword ptr [rcx+18h], 8
0x1400087cf  mov     rbx, rcx
0x1400087d2  jb      short loc_1400087DD
0x1400087d4  mov     rcx, [rcx]
0x1400087d7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400087dd  xor     eax, eax
0x1400087df  mov     qword ptr [rbx+18h], 7
0x1400087e7  mov     [rbx+10h], rax
0x1400087eb  mov     [rbx], ax
0x1400087ee  add     rsp, 20h
0x1400087f2  pop     rbx
0x1400087f3  retn
```
