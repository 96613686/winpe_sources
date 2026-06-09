# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x1800060c4`
- end: `0x1800060f4`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `48`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `7`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000c56a`
- `0x18000c580`
- `0x18000c5c8`
- `0x18000c5e1`
- `0x18000c63d`
- `0x18000c653`
- `0x18000c69b`

## callees

- `0x1800060c4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800060d7`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800060d7`

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
0x1800060c4  push    rbx
0x1800060c6  sub     rsp, 20h
0x1800060ca  cmp     qword ptr [rcx+18h], 8
0x1800060cf  mov     rbx, rcx
0x1800060d2  jb      short loc_1800060DD
0x1800060d4  mov     rcx, [rcx]
0x1800060d7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800060dd  xor     eax, eax
0x1800060df  mov     qword ptr [rbx+18h], 7
0x1800060e7  mov     [rbx+10h], rax
0x1800060eb  mov     [rbx], ax
0x1800060ee  add     rsp, 20h
0x1800060f2  pop     rbx
0x1800060f3  retn
```
