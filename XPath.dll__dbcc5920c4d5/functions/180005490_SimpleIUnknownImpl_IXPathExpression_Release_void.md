# SimpleIUnknownImpl<IXPathExpression>::Release(void)

- ea: `0x180005490`
- end: `0x1800054bf`
- name: `?Release@?$SimpleIUnknownImpl@UIXPathExpression@@@@UEAAKXZ`
- size: `47`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800054e0`
- `0x18000d770`

## callees

- `0x180005490`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall SimpleIUnknownImpl<IXPathExpression>::Release(volatile signed __int32 *a1)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement(a1 + 2);
  if ( !v1 && a1 )
    (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)a1 + 56LL))(a1, 1);
  return v1;
}

```

## disassembly

```asm
0x180005490  push    rbx
0x180005492  sub     rsp, 20h
0x180005496  or      ebx, 0FFFFFFFFh
0x180005499  lock xadd [rcx+8], ebx
0x18000549e  sub     ebx, 1
0x1800054a1  jnz     short loc_1800054B7
0x1800054a3  test    rcx, rcx
0x1800054a6  jz      short loc_1800054B7
0x1800054a8  mov     rdx, [rcx]
0x1800054ab  mov     rax, [rdx+38h]
0x1800054af  lea     edx, [rbx+1]
0x1800054b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054b7  mov     eax, ebx
0x1800054b9  add     rsp, 20h
0x1800054bd  pop     rbx
0x1800054be  retn
```
