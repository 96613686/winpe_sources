# BfspDeleteObjectFromDisplayOrder

- ea: `0x18004f454`
- end: `0x18004f543`
- name: `BfspDeleteObjectFromDisplayOrder`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180050554`

## callees

- `0x18004f454`
- `0x18004f54c`
- `0x18004f888`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f4fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f516`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f4fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f516`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f4ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f508`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f4ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f508`
- `bcd!BcdSetElementData` at `0x18004f539`
- `bcd!BcdSetElementData` at `0x18004f539`
- `bcd!BcdDeleteElement` at `0x18004f4db`
- `bcd!BcdDeleteElement` at `0x18004f4db`

## pseudocode

```c
__int64 __fastcall BfspDeleteObjectFromDisplayOrder(__int64 a1, __int64 a2, __int64 a3)
{
  void *v4; // rbx
  int BcdElementData; // edi
  HANDLE ProcessHeap; // rax
  HANDLE v8; // rax
  void *v10; // [rsp+30h] [rbp-10h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v12; // [rsp+68h] [rbp+28h] BYREF
  unsigned int v13; // [rsp+78h] [rbp+38h] BYREF

  v12 = 0;
  v4 = 0;
  v13 = 0;
  v10 = 0;
  lpMem = 0;
  BcdElementData = BfspGetBcdElementData(a1, 603979777, &lpMem, &v12);
  if ( BcdElementData >= 0 )
  {
    BcdElementData = BfspDeleteObjectInList(lpMem, v12, a3, &v10, &v13);
    if ( BcdElementData < 0 )
    {
LABEL_5:
      v4 = v10;
      goto LABEL_6;
    }
    if ( !v13 )
    {
      BcdElementData = BcdDeleteElement(a1, 603979777);
      goto LABEL_5;
    }
    v4 = v10;
    BcdElementData = BcdSetElementData(a1, 603979777, v10, v13);
  }
LABEL_6:
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
  if ( v4 )
  {
    v8 = GetProcessHeap();
    HeapFree(v8, 0, v4);
  }
  return (unsigned int)BcdElementData;
}

```

## disassembly

```asm
0x18004f454  mov     [rsp-18h+arg_0], rbx
0x18004f459  mov     [rsp-18h+arg_10], rdi
0x18004f45e  mov     [rsp-18h+arg_8], edx
0x18004f462  push    rbp
0x18004f463  push    r14
0x18004f465  push    r15
0x18004f467  mov     rbp, rsp
0x18004f46a  sub     rsp, 40h
0x18004f46e  mov     r15, r8
0x18004f471  mov     [rbp+arg_8], 0
0x18004f478  xor     ebx, ebx
0x18004f47a  mov     [rbp+arg_18], 0
0x18004f481  lea     r8, [rbp+lpMem]
0x18004f485  mov     [rbp+var_10], rbx
0x18004f489  lea     r9, [rbp+arg_8]
0x18004f48d  mov     [rbp+lpMem], 0
0x18004f495  mov     edx, 24000001h
0x18004f49a  mov     r14, rcx
0x18004f49d  call    BfspGetBcdElementData
0x18004f4a2  mov     edi, eax
0x18004f4a4  test    eax, eax
0x18004f4a6  js      short loc_18004F4E7
0x18004f4a8  mov     edx, [rbp+arg_8]
0x18004f4ab  lea     rax, [rbp+arg_18]
0x18004f4af  mov     rcx, [rbp+lpMem]
0x18004f4b3  lea     r9, [rbp+var_10]
0x18004f4b7  mov     r8, r15
0x18004f4ba  mov     [rsp+40h+var_20], rax
0x18004f4bf  call    BfspDeleteObjectInList
0x18004f4c4  mov     edi, eax
0x18004f4c6  test    eax, eax
0x18004f4c8  js      short loc_18004F4E3
0x18004f4ca  mov     r9d, [rbp+arg_18]
0x18004f4ce  mov     edx, 24000001h
0x18004f4d3  mov     rcx, r14
0x18004f4d6  test    r9d, r9d
0x18004f4d9  jnz     short loc_18004F532
0x18004f4db  call    cs:__imp_BcdDeleteElement
0x18004f4e1  mov     edi, eax
0x18004f4e3  mov     rbx, [rbp+var_10]
0x18004f4e7  cmp     [rbp+lpMem], 0
0x18004f4ec  jz      short loc_18004F503
0x18004f4ee  call    cs:__imp_GetProcessHeap
0x18004f4f4  mov     r8, [rbp+lpMem]; lpMem
0x18004f4f8  xor     edx, edx; dwFlags
0x18004f4fa  mov     rcx, rax; hHeap
0x18004f4fd  call    cs:__imp_HeapFree
0x18004f503  test    rbx, rbx
0x18004f506  jz      short loc_18004F51C
0x18004f508  call    cs:__imp_GetProcessHeap
0x18004f50e  mov     r8, rbx; lpMem
0x18004f511  xor     edx, edx; dwFlags
0x18004f513  mov     rcx, rax; hHeap
0x18004f516  call    cs:__imp_HeapFree
0x18004f51c  mov     rbx, [rsp+40h+arg_0]
0x18004f521  mov     eax, edi
0x18004f523  mov     rdi, [rsp+40h+arg_10]
0x18004f528  add     rsp, 40h
0x18004f52c  pop     r15
0x18004f52e  pop     r14
0x18004f530  pop     rbp
0x18004f531  retn
0x18004f532  mov     rbx, [rbp+var_10]
0x18004f536  mov     r8, rbx
0x18004f539  call    cs:__imp_BcdSetElementData
0x18004f53f  mov     edi, eax
0x18004f541  jmp     short loc_18004F4E7
```
