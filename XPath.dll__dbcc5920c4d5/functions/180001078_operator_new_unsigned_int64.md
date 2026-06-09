# operator new(unsigned __int64)

- ea: `0x180001078`
- end: `0x1800010b1`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `111`
- callee_count: `3`
- tags: ``

## callers

- `0x1800010c4`
- `0x1800021e0`
- `0x180002664`
- `0x180002e9c`
- `0x1800036f0`
- `0x1800037b0`
- `0x180003870`
- `0x180003940`
- `0x180003a00`
- `0x180003ac0`
- `0x180003b80`
- `0x180003c60`
- `0x180003d20`
- `0x180003e00`
- `0x180003ee0`
- `0x180003fc0`
- `0x180004080`
- `0x180004140`
- `0x180004200`
- `0x1800042c0`
- `0x180004380`
- `0x180004440`
- `0x180004500`
- `0x1800045c0`
- `0x180004680`
- `0x180004750`
- `0x180004830`
- `0x1800048f0`
- `0x180004960`
- `0x1800049d0`
- `0x180004a40`
- `0x180004c30`
- `0x180004d24`
- `0x180005068`
- `0x180005124`
- `0x180006de0`
- `0x180006e90`
- `0x180006f40`
- `0x180006ff0`
- `0x1800070a0`
- `0x180007110`
- `0x1800071b4`
- `0x180007258`
- `0x180007300`
- `0x180007390`
- `0x180007420`
- `0x1800074b0`
- `0x180007540`
- `0x1800075c0`
- `0x180007640`

## callees

- `0x180001078`
- `0x1800017a2`
- `0x1800017ae`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rdi
  void *v2; // rbx

  for ( i = Size; ; Size = i )
  {
    v2 = malloc_0(Size);
    if ( v2 || !callnewh_0(i) )
      break;
  }
  return v2;
}

```

## disassembly

```asm
0x180001078  mov     [rsp+arg_0], rbx
0x18000107d  push    rdi
0x18000107e  sub     rsp, 20h
0x180001082  mov     rdi, rcx
0x180001085  jmp     short loc_180001096
0x180001087  mov     rcx, rdi; Size
0x18000108a  call    _callnewh_0
0x18000108f  test    eax, eax
0x180001091  jz      short loc_1800010A3
0x180001093  mov     rcx, rdi; Size
0x180001096  call    malloc_0
0x18000109b  mov     rbx, rax
0x18000109e  test    rax, rax
0x1800010a1  jz      short loc_180001087
0x1800010a3  mov     rax, rbx
0x1800010a6  mov     rbx, [rsp+28h+arg_0]
0x1800010ab  add     rsp, 20h
0x1800010af  pop     rdi
0x1800010b0  retn
```
