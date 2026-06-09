# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x180008820`
- end: `0x180008850`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `48`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `7`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000cd7b`
- `0x18000cd8d`
- `0x18000ce37`
- `0x18000cee8`
- `0x18000cf26`
- `0x18000cf38`
- `0x18000cf4a`

## callees

- `0x180008820`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008833`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008833`

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
0x180008820  push    rbx
0x180008822  sub     rsp, 20h
0x180008826  cmp     qword ptr [rcx+18h], 8
0x18000882b  mov     rbx, rcx
0x18000882e  jb      short loc_180008839
0x180008830  mov     rcx, [rcx]
0x180008833  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008839  xor     eax, eax
0x18000883b  mov     qword ptr [rbx+18h], 7
0x180008843  mov     [rbx+10h], rax
0x180008847  mov     [rbx], ax
0x18000884a  add     rsp, 20h
0x18000884e  pop     rbx
0x18000884f  retn
```
