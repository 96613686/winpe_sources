# PROPERTY_BAG::DeleteEntry(ulong)

- ea: `0x18000fde4`
- end: `0x18000fe33`
- name: `?DeleteEntry@PROPERTY_BAG@@QEAAJK@Z`
- size: `79`
- prototype: `__int64 __fastcall(PROPERTY_BAG *__hidden this, unsigned int)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1800075cc`
- `0x1800087bc`
- `0x18000a6fc`
- `0x18000c990`
- `0x180010560`
- `0x18001a4f8`

## callees

- `0x180007670`
- `0x18000fde4`

## import_xrefs

- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fe05`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fe05`

## pseudocode

```c
__int64 __fastcall PROPERTY_BAG::DeleteEntry(PROPERTY_BAG *this, int a2)
{
  __int64 v2; // rbx

  v2 = 0;
  if ( !*((_DWORD *)this + 4) )
    return 2147942402LL;
  while ( *(_DWORD *)BUFFER::QueryPtr((BUFFER *)(*(_QWORD *)(*((_QWORD *)this + 1) + 8 * v2) + 16LL)) != a2 )
  {
    v2 = (unsigned int)(v2 + 1);
    if ( (unsigned int)v2 >= *((_DWORD *)this + 4) )
      return 2147942402LL;
  }
  ARRAY_LIST::DeleteEntry((PROPERTY_BAG *)((char *)this + 8), v2);
  return 0;
}

```

## disassembly

```asm
0x18000fde4  push    rbx
0x18000fde6  push    rbp
0x18000fde7  push    rsi
0x18000fde8  push    rdi
0x18000fde9  sub     rsp, 28h
0x18000fded  xor     ebx, ebx
0x18000fdef  mov     ebp, edx
0x18000fdf1  mov     rdi, rcx
0x18000fdf4  cmp     [rcx+10h], ebx
0x18000fdf7  jbe     short loc_18000FE16
0x18000fdf9  mov     rax, [rdi+8]
0x18000fdfd  mov     rcx, [rax+rbx*8]
0x18000fe01  add     rcx, 10h
0x18000fe05  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000fe0b  cmp     [rax], ebp
0x18000fe0d  jz      short loc_18000FE24
0x18000fe0f  inc     ebx
0x18000fe11  cmp     ebx, [rdi+10h]
0x18000fe14  jb      short loc_18000FDF9
0x18000fe16  mov     eax, 80070002h
0x18000fe1b  add     rsp, 28h
0x18000fe1f  pop     rdi
0x18000fe20  pop     rsi
0x18000fe21  pop     rbp
0x18000fe22  pop     rbx
0x18000fe23  retn
0x18000fe24  mov     edx, ebx; unsigned int
0x18000fe26  lea     rcx, [rdi+8]; this
0x18000fe2a  call    ?DeleteEntry@ARRAY_LIST@@QEAAJK@Z; ARRAY_LIST::DeleteEntry(ulong)
0x18000fe2f  xor     eax, eax
0x18000fe31  jmp     short loc_18000FE1B
```
