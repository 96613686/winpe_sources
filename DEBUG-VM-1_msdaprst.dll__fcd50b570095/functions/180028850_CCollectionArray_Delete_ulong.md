# CCollectionArray::Delete(ulong)

- ea: `0x180028850`
- end: `0x18002888e`
- name: `?Delete@CCollectionArray@@QEAAJK@Z`
- size: `62`
- prototype: `__int64 __fastcall(CCollectionArray *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800266bc`
- `0x180028894`
- `0x180028920`
- `0x180028bdc`

## callees

- `0x180028850`
- `0x18002e01e`

## pseudocode

```c
__int64 __fastcall CCollectionArray::Delete(CCollectionArray *this, unsigned int a2)
{
  int v2; // r9d
  __int64 v4; // rcx

  v2 = *((_DWORD *)this + 4);
  if ( a2 != v2 - 1 )
  {
    v4 = *((_QWORD *)this + 1) + 8LL * a2;
    memmove_0((void *)v4, (const void *)(v4 + 8), 8LL * (v2 + ~a2));
  }
  --*((_DWORD *)this + 4);
  return 0;
}

```

## disassembly

```asm
0x180028850  push    rbx
0x180028852  sub     rsp, 20h
0x180028856  mov     r9d, [rcx+10h]
0x18002885a  mov     rbx, rcx
0x18002885d  lea     eax, [r9-1]
0x180028861  cmp     edx, eax
0x180028863  jz      short loc_180028883
0x180028865  mov     rax, [rcx+8]
0x180028869  mov     r8d, edx
0x18002886c  not     edx
0x18002886e  lea     rcx, [rax+r8*8]; void *
0x180028872  lea     r8d, [r9+rdx]
0x180028876  shl     r8, 3; Size
0x18002887a  lea     rdx, [rcx+8]; Src
0x18002887e  call    memmove_0
0x180028883  dec     dword ptr [rbx+10h]
0x180028886  xor     eax, eax
0x180028888  add     rsp, 20h
0x18002888c  pop     rbx
0x18002888d  retn
```
