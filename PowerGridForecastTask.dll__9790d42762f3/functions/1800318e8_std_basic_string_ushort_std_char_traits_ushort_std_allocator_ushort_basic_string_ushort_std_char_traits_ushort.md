# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x1800318e8`
- end: `0x180031918`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `48`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `17`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18003549e`
- `0x180035539`
- `0x18003557a`
- `0x18003558c`
- `0x1800355bb`
- `0x1800355ea`
- `0x180035619`
- `0x18003585a`
- `0x18003587e`
- `0x180035890`
- `0x1800358ea`
- `0x1800358fc`
- `0x18003597a`
- `0x18003598c`
- `0x1800359d4`
- `0x180036021`
- `0x180036249`

## callees

- `0x1800318e8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800318fb`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800318fb`

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
0x1800318e8  push    rbx
0x1800318ea  sub     rsp, 20h
0x1800318ee  cmp     qword ptr [rcx+18h], 8
0x1800318f3  mov     rbx, rcx
0x1800318f6  jb      short loc_180031901
0x1800318f8  mov     rcx, [rcx]
0x1800318fb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180031901  xor     eax, eax
0x180031903  mov     qword ptr [rbx+18h], 7
0x18003190b  mov     [rbx+10h], rax
0x18003190f  mov     [rbx], ax
0x180031912  add     rsp, 20h
0x180031916  pop     rbx
0x180031917  retn
```
