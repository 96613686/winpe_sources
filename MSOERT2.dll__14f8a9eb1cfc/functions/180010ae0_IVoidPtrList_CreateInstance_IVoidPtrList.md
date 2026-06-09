# IVoidPtrList_CreateInstance(IVoidPtrList * *)

- ea: `0x180010ae0`
- end: `0x180010b0f`
- name: `?IVoidPtrList_CreateInstance@@YAJPEAPEAUIVoidPtrList@@@Z`
- size: `47`
- prototype: `__int64 __fastcall(struct IVoidPtrList **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180011040`

## callees

- `0x1800109a0`

## pseudocode

```c
__int64 __fastcall IVoidPtrList_CreateInstance(struct IVoidPtrList **a1)
{
  __int64 result; // rax
  struct CVoidPtrList *v3; // rdx
  struct CVoidPtrList *v4; // [rsp+38h] [rbp+10h] BYREF

  v4 = 0;
  result = CVoidPtrList::CreateInstance(&v4);
  v3 = 0;
  if ( (int)result >= 0 )
    v3 = v4;
  *a1 = v3;
  return result;
}

```

## disassembly

```asm
0x180010ae0  push    rbx
0x180010ae2  sub     rsp, 20h
0x180010ae6  mov     rbx, rcx
0x180010ae9  mov     [rsp+28h+arg_8], 0
0x180010af2  lea     rcx, [rsp+28h+arg_8]; struct CVoidPtrList **
0x180010af7  call    ?CreateInstance@CVoidPtrList@@SAJPEAPEAV1@@Z; CVoidPtrList::CreateInstance(CVoidPtrList * *)
0x180010afc  xor     edx, edx
0x180010afe  test    eax, eax
0x180010b00  cmovns  rdx, [rsp+28h+arg_8]
0x180010b06  mov     [rbx], rdx
0x180010b09  add     rsp, 20h
0x180010b0d  pop     rbx
0x180010b0e  retn
```
