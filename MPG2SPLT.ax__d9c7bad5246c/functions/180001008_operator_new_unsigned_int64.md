# operator new(unsigned __int64)

- ea: `0x180001008`
- end: `0x180001041`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `81`
- callee_count: `3`
- tags: ``

## callers

- `0x180001054`
- `0x180002200`
- `0x180003590`
- `0x180003a50`
- `0x180003af0`
- `0x180004140`
- `0x1800041b0`
- `0x1800067a4`
- `0x180007550`
- `0x180007b40`
- `0x180007cc0`
- `0x180007d80`
- `0x180009018`
- `0x18000a5d0`
- `0x18000a680`
- `0x18000bda0`
- `0x18000bed0`
- `0x18000bf70`
- `0x18000c170`
- `0x18000c488`
- `0x18000cd60`
- `0x18000cfc0`
- `0x18000dd90`
- `0x180011730`
- `0x180011d44`
- `0x180012520`
- `0x180012acc`
- `0x180013b58`
- `0x180013d34`
- `0x180013ea0`
- `0x180013f20`
- `0x1800140bc`
- `0x180014a40`
- `0x1800156e4`
- `0x180015a0c`
- `0x1800162f4`
- `0x180016410`
- `0x180016c8c`
- `0x180019180`
- `0x180019294`
- `0x180019570`
- `0x180019680`
- `0x18001ac30`
- `0x18001c2b0`
- `0x18001c3a0`
- `0x18001ceb8`
- `0x18001d040`
- `0x18001d190`
- `0x18001e060`
- `0x18001ec78`

## callees

- `0x180001008`
- `0x180001df2`
- `0x180001e80`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rdi
  void *v2; // rbx

  for ( i = Size; ; Size = i )
  {
    v2 = o_malloc_0(Size);
    if ( v2 || !(unsigned int)o__callnewh_0(i) )
      break;
  }
  return v2;
}

```

## disassembly

```asm
0x180001008  mov     [rsp+arg_0], rbx
0x18000100d  push    rdi
0x18000100e  sub     rsp, 20h
0x180001012  mov     rdi, rcx
0x180001015  jmp     short loc_180001026
0x180001017  mov     rcx, rdi
0x18000101a  call    _o__callnewh_0
0x18000101f  test    eax, eax
0x180001021  jz      short loc_180001033
0x180001023  mov     rcx, rdi; Size
0x180001026  call    _o_malloc_0
0x18000102b  mov     rbx, rax
0x18000102e  test    rax, rax
0x180001031  jz      short loc_180001017
0x180001033  mov     rax, rbx
0x180001036  mov     rbx, [rsp+28h+arg_0]
0x18000103b  add     rsp, 20h
0x18000103f  pop     rdi
0x180001040  retn
```
