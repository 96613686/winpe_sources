# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)

- ea: `0x18000b6a4`
- end: `0x18000b6d3`
- name: `??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ`
- size: `47`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `16`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800354b0`
- `0x18003566c`
- `0x18003567e`
- `0x180035690`
- `0x1800356bf`
- `0x1800356ee`
- `0x18003571d`
- `0x1800358a2`
- `0x1800358b4`
- `0x1800358c6`
- `0x18003590e`
- `0x180035920`
- `0x18003599e`
- `0x1800359b0`
- `0x1800359c2`
- `0x180035a00`

## callees

- `0x18000b6a4`
- `0x180026609`

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
0x18000b6a4  push    rbx
0x18000b6a6  sub     rsp, 20h
0x18000b6aa  cmp     qword ptr [rcx+18h], 8
0x18000b6af  mov     rbx, rcx
0x18000b6b2  jb      short loc_18000B6BC
0x18000b6b4  mov     rcx, [rcx]; void *
0x18000b6b7  call    ??3@YAXPEAX@Z_0
0x18000b6bc  xor     eax, eax
0x18000b6be  mov     qword ptr [rbx+18h], 7
0x18000b6c6  mov     [rbx+10h], rax
0x18000b6ca  mov     [rbx], ax
0x18000b6cd  add     rsp, 20h
0x18000b6d1  pop     rbx
0x18000b6d2  retn
```
