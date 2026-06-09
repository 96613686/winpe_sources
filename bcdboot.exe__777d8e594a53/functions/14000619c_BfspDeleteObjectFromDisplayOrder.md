# BfspDeleteObjectFromDisplayOrder

- ea: `0x14000619c`
- end: `0x140006291`
- name: `BfspDeleteObjectFromDisplayOrder`
- size: `245`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140004e98`
- `0x140008104`
- `0x140008400`

## callees

- `0x14000619c`
- `0x140006298`
- `0x140006a14`
- `0x140018b54`
- `0x140019990`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140006245`
- `KERNEL32!HeapFree` at `0x14000625e`
- `KERNEL32!HeapFree` at `0x140006245`
- `KERNEL32!HeapFree` at `0x14000625e`
- `KERNEL32!GetProcessHeap` at `0x140006236`
- `KERNEL32!GetProcessHeap` at `0x140006250`
- `KERNEL32!GetProcessHeap` at `0x140006236`
- `KERNEL32!GetProcessHeap` at `0x140006250`

## pseudocode

```c
__int64 __fastcall BfspDeleteObjectFromDisplayOrder(__int64 a1, __int64 a2, __int64 a3)
{
  void *v4; // rbx
  int BcdElementData; // edi
  __int64 v7; // r8
  HANDLE ProcessHeap; // rax
  HANDLE v9; // rax
  void *v11; // [rsp+30h] [rbp-10h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v13; // [rsp+68h] [rbp+28h] BYREF
  unsigned int v14; // [rsp+78h] [rbp+38h] BYREF

  v13 = 0;
  v4 = 0;
  v14 = 0;
  v11 = 0;
  lpMem = 0;
  BcdElementData = BfspGetBcdElementData(a1, 603979777, &lpMem, &v13);
  if ( BcdElementData >= 0 )
  {
    BcdElementData = BfspDeleteObjectInList(lpMem, v13, a3, &v11, &v14);
    if ( BcdElementData < 0 )
    {
LABEL_5:
      v4 = v11;
      goto LABEL_6;
    }
    if ( !v14 )
    {
      LOBYTE(v7) = 1;
      BcdElementData = BiDeleteElement(a1, 603979777, v7);
      goto LABEL_5;
    }
    v4 = v11;
    BcdElementData = BcdSetElementDataWithFlags(a1, 603979777, 0, (__int64)v11, v14);
  }
LABEL_6:
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
  if ( v4 )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v4);
  }
  return (unsigned int)BcdElementData;
}

```

## disassembly

```asm
0x14000619c  mov     [rsp-18h+arg_0], rbx
0x1400061a1  mov     [rsp-18h+arg_10], rdi
0x1400061a6  mov     [rsp-18h+arg_8], edx
0x1400061aa  push    rbp
0x1400061ab  push    r14
0x1400061ad  push    r15
0x1400061af  mov     rbp, rsp
0x1400061b2  sub     rsp, 40h
0x1400061b6  mov     r15, r8
0x1400061b9  mov     [rbp+arg_8], 0
0x1400061c0  xor     ebx, ebx
0x1400061c2  mov     [rbp+arg_18], 0
0x1400061c9  lea     r8, [rbp+lpMem]
0x1400061cd  mov     [rbp+var_10], rbx
0x1400061d1  lea     r9, [rbp+arg_8]
0x1400061d5  mov     [rbp+lpMem], 0
0x1400061dd  mov     edx, 24000001h
0x1400061e2  mov     r14, rcx
0x1400061e5  call    BfspGetBcdElementData
0x1400061ea  mov     edi, eax
0x1400061ec  test    eax, eax
0x1400061ee  js      short loc_14000622F
0x1400061f0  mov     edx, [rbp+arg_8]
0x1400061f3  lea     rax, [rbp+arg_18]
0x1400061f7  mov     rcx, [rbp+lpMem]
0x1400061fb  lea     r9, [rbp+var_10]
0x1400061ff  mov     r8, r15
0x140006202  mov     [rsp+40h+var_20], rax
0x140006207  call    BfspDeleteObjectInList
0x14000620c  mov     edi, eax
0x14000620e  test    eax, eax
0x140006210  js      short loc_14000622B
0x140006212  mov     eax, [rbp+arg_18]
0x140006215  mov     edx, 24000001h
0x14000621a  mov     rcx, r14
0x14000621d  test    eax, eax
0x14000621f  jnz     short loc_14000627A
0x140006221  mov     r8b, 1
0x140006224  call    BiDeleteElement
0x140006229  mov     edi, eax
0x14000622b  mov     rbx, [rbp+var_10]
0x14000622f  cmp     [rbp+lpMem], 0
0x140006234  jz      short loc_14000624B
0x140006236  call    cs:__imp_GetProcessHeap
0x14000623c  mov     r8, [rbp+lpMem]; lpMem
0x140006240  xor     edx, edx; dwFlags
0x140006242  mov     rcx, rax; hHeap
0x140006245  call    cs:__imp_HeapFree
0x14000624b  test    rbx, rbx
0x14000624e  jz      short loc_140006264
0x140006250  call    cs:__imp_GetProcessHeap
0x140006256  mov     r8, rbx; lpMem
0x140006259  xor     edx, edx; dwFlags
0x14000625b  mov     rcx, rax; hHeap
0x14000625e  call    cs:__imp_HeapFree
0x140006264  mov     rbx, [rsp+40h+arg_0]
0x140006269  mov     eax, edi
0x14000626b  mov     rdi, [rsp+40h+arg_10]
0x140006270  add     rsp, 40h
0x140006274  pop     r15
0x140006276  pop     r14
0x140006278  pop     rbp
0x140006279  retn
0x14000627a  mov     rbx, [rbp+var_10]
0x14000627e  xor     r8d, r8d
0x140006281  mov     r9, rbx
0x140006284  mov     dword ptr [rsp+40h+var_20], eax
0x140006288  call    BcdSetElementDataWithFlags
0x14000628d  mov     edi, eax
0x14000628f  jmp     short loc_14000622F
```
