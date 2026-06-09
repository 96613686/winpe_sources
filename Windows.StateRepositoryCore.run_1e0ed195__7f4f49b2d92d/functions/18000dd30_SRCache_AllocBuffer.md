# SRCache_AllocBuffer

- ea: `0x18000dd30`
- end: `0x18000dd75`
- name: `SRCache_AllocBuffer`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x1800022a0`
- `0x18000be7c`
- `0x18000dd30`

## pseudocode

```c
__int64 __fastcall SRCache_AllocBuffer(unsigned int a1)
{
  __int64 *unique; // rax
  __int64 v3; // rbx
  void *v4; // rcx
  void *v5; // [rsp+38h] [rbp+10h] BYREF

  if ( !a1 )
    return 0;
  unique = wil::make_unique_nothrow<unsigned char [0]>(&v5, a1);
  v3 = *unique;
  *unique = 0;
  v4 = v5;
  v5 = 0;
  if ( v4 )
    operator delete(v4);
  return v3;
}

```

## disassembly

```asm
0x18000dd30  push    rbx
0x18000dd32  sub     rsp, 20h
0x18000dd36  test    ecx, ecx
0x18000dd38  jnz     short loc_18000DD3E
0x18000dd3a  xor     eax, eax
0x18000dd3c  jmp     short loc_18000DD6F
0x18000dd3e  mov     edx, ecx
0x18000dd40  lea     rcx, [rsp+28h+arg_8]
0x18000dd45  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18000dd4a  mov     rbx, [rax]
0x18000dd4d  mov     qword ptr [rax], 0
0x18000dd54  mov     rcx, [rsp+28h+arg_8]; void *
0x18000dd59  mov     [rsp+28h+arg_8], 0
0x18000dd62  test    rcx, rcx
0x18000dd65  jz      short loc_18000DD6C
0x18000dd67  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000dd6c  mov     rax, rbx
0x18000dd6f  add     rsp, 20h
0x18000dd73  pop     rbx
0x18000dd74  retn
```
