# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::~basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>(void)

- ea: `0x1800036c0`
- end: `0x1800036fe`
- name: `??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@XZ`
- size: `62`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f700`
- `0x18000fbb2`
- `0x18000fda6`
- `0x18000fe32`

## callees

- `0x1800036c0`

## import_xrefs

- `msvcrt!free` at `0x1800036d8`
- `msvcrt!free` at `0x1800036d8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::string::~string(__int64 a1)
{
  if ( *(_QWORD *)(a1 + 32) >= 0x10u )
    free(*(void **)(a1 + 8));
  *(_QWORD *)(a1 + 32) = 15;
  *(_QWORD *)(a1 + 24) = 0;
  *(_BYTE *)(a1 + 8) = 0;
}

```

## disassembly

```asm
0x1800036c0  mov     [rsp+arg_0], rbx
0x1800036c5  push    rdi
0x1800036c6  sub     rsp, 20h
0x1800036ca  mov     rdi, rcx
0x1800036cd  cmp     qword ptr [rcx+20h], 10h
0x1800036d2  jb      short loc_1800036DF
0x1800036d4  mov     rcx, [rcx+8]; Block
0x1800036d8  call    cs:__imp_free
0x1800036de  nop
0x1800036df  mov     qword ptr [rdi+20h], 0Fh
0x1800036e7  mov     qword ptr [rdi+18h], 0
0x1800036ef  mov     byte ptr [rdi+8], 0
0x1800036f3  mov     rbx, [rsp+28h+arg_0]
0x1800036f8  add     rsp, 20h
0x1800036fc  pop     rdi
0x1800036fd  retn
```
