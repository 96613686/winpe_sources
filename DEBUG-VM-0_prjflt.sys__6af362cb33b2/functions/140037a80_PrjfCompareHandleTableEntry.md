# PrjfCompareHandleTableEntry

- ea: `0x140037a80`
- end: `0x140037ab7`
- name: `PrjfCompareHandleTableEntry`
- size: `55`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000c3a0`
- `0x140037a80`

## pseudocode

```c
__int64 __fastcall PrjfCompareHandleTableEntry(struct _RTL_AVL_TABLE *Table, PVOID FirstStruct, PVOID SecondStruct)
{
  int v3; // edx
  __int64 result; // rax

  v3 = memcmp(FirstStruct, SecondStruct, 0x10u);
  if ( v3 > 0 )
    return 1;
  result = 2;
  if ( v3 < 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x140037a80  sub     rsp, 28h
0x140037a84  mov     rax, r8
0x140037a87  mov     rcx, rdx; Buf1
0x140037a8a  mov     rdx, rax; Buf2
0x140037a8d  mov     r8d, 10h; Size
0x140037a93  call    memcmp
0x140037a98  mov     edx, eax
0x140037a9a  test    eax, eax
0x140037a9c  jle     short loc_140037AA5
0x140037a9e  mov     eax, 1
0x140037aa3  jmp     short loc_140037AB1
0x140037aa5  xor     ecx, ecx
0x140037aa7  mov     eax, 2
0x140037aac  test    edx, edx
0x140037aae  cmovs   eax, ecx
0x140037ab1  add     rsp, 28h
0x140037ab5  retn
```
