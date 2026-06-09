# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::~basic_string<char,std::char_traits<char>,std::allocator<char>>(void)

- ea: `0x180027f0c`
- end: `0x180027f3e`
- name: `??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ`
- size: `50`
- prototype: `void __fastcall(__int64)`
- caller_count: `31`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18003523f`
- `0x180035275`
- `0x180035287`
- `0x180035325`
- `0x180035349`
- `0x18003535b`
- `0x18003536d`
- `0x18003537f`
- `0x180035411`
- `0x1800354e6`
- `0x18003554b`
- `0x180035648`
- `0x18003565a`
- `0x18003586c`
- `0x1800358d8`
- `0x180035a2c`
- `0x180035a58`
- `0x180035a6a`
- `0x180035a99`
- `0x180035ac8`
- `0x180035af7`
- `0x180035b99`
- `0x180035bab`
- `0x180035bbd`
- `0x180035bcf`
- `0x180035be1`
- `0x180035bf3`
- `0x180035c05`
- `0x18003600b`
- `0x180036319`
- `0x18003632b`

## callees

- `0x180027f0c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180027f1f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027f1f`

## pseudocode

```c
void __fastcall std::string::~string(__int64 a1)
{
  if ( *(_QWORD *)(a1 + 24) >= 0x10u )
    operator delete(*(void **)a1);
  *(_QWORD *)(a1 + 24) = 15;
  *(_QWORD *)(a1 + 16) = 0;
  *(_BYTE *)a1 = 0;
}

```

## disassembly

```asm
0x180027f0c  push    rbx
0x180027f0e  sub     rsp, 20h
0x180027f12  cmp     qword ptr [rcx+18h], 10h
0x180027f17  mov     rbx, rcx
0x180027f1a  jb      short loc_180027F25
0x180027f1c  mov     rcx, [rcx]
0x180027f1f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180027f25  mov     qword ptr [rbx+18h], 0Fh
0x180027f2d  mov     qword ptr [rbx+10h], 0
0x180027f35  mov     byte ptr [rbx], 0
0x180027f38  add     rsp, 20h
0x180027f3c  pop     rbx
0x180027f3d  retn
```
