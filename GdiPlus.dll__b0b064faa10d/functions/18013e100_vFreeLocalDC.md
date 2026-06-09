# vFreeLocalDC

- ea: `0x18013e100`
- end: `0x18013e214`
- name: `vFreeLocalDC`
- size: `276`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800e7358`
- `0x1800f12f0`

## callees

- `0x18013e100`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013e137`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013e178`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013e1cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013e1f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013e137`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013e178`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013e1cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013e1f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013e20d`
- `GDI32!DeleteDC` at `0x18013e116`
- `GDI32!DeleteDC` at `0x18013e116`
- `GDI32!DeleteObject` at `0x18013e125`
- `GDI32!DeleteObject` at `0x18013e161`
- `GDI32!DeleteObject` at `0x18013e1a9`
- `GDI32!DeleteObject` at `0x18013e125`
- `GDI32!DeleteObject` at `0x18013e161`
- `GDI32!DeleteObject` at `0x18013e1a9`

## pseudocode

```c
HLOCAL __fastcall vFreeLocalDC(__int64 a1)
{
  HDC v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  __int64 i; // rbx
  void *v6; // rcx
  unsigned int j; // ebx
  void *v8; // rcx
  _QWORD *k; // rcx
  _QWORD *v10; // rcx
  _QWORD *v11; // rbx

  v2 = *(HDC *)(a1 + 40);
  if ( v2 )
    DeleteDC(v2);
  v3 = *(void **)(a1 + 56);
  if ( v3 )
    DeleteObject(v3);
  v4 = *(void **)(a1 + 400);
  if ( v4 )
    LocalFree(v4);
  if ( *(_QWORD *)(a1 + 552) )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 520); i = (unsigned int)(i + 1) )
    {
      v6 = *(void **)(*(_QWORD *)(a1 + 552) + 8 * i);
      if ( v6 )
        DeleteObject(v6);
    }
    LocalFree(*(HLOCAL *)(a1 + 552));
  }
  if ( !*(_QWORD *)(a1 + 416) )
    goto LABEL_21;
  for ( j = 0; j < *(_DWORD *)(a1 + 408); ++j )
  {
    v8 = *(void **)(32LL * j + *(_QWORD *)(a1 + 416) + 8);
    if ( v8 )
      DeleteObject(v8);
  }
  for ( k = *(_QWORD **)(a1 + 416); ; *(_QWORD *)(a1 + 560) = k[2] )
  {
    LocalFree(k);
LABEL_21:
    k = *(_QWORD **)(a1 + 560);
    if ( !k )
      break;
  }
  v10 = *(_QWORD **)(a1 + 464);
  if ( v10 )
  {
    do
    {
      v11 = (_QWORD *)v10[58];
      LocalFree(v10);
      v10 = v11;
    }
    while ( v11 );
  }
  return LocalFree((HLOCAL)a1);
}

```

## disassembly

```asm
0x18013e100  mov     [rsp+arg_0], rbx
0x18013e105  push    rdi
0x18013e106  sub     rsp, 20h
0x18013e10a  mov     rdi, rcx
0x18013e10d  mov     rcx, [rcx+28h]; hdc
0x18013e111  test    rcx, rcx
0x18013e114  jz      short loc_18013E11C
0x18013e116  call    cs:__imp_DeleteDC
0x18013e11c  mov     rcx, [rdi+38h]; ho
0x18013e120  test    rcx, rcx
0x18013e123  jz      short loc_18013E12B
0x18013e125  call    cs:__imp_DeleteObject
0x18013e12b  mov     rcx, [rdi+190h]; hMem
0x18013e132  test    rcx, rcx
0x18013e135  jz      short loc_18013E13D
0x18013e137  call    cs:__imp_LocalFree
0x18013e13d  cmp     qword ptr [rdi+228h], 0
0x18013e145  jz      short loc_18013E17E
0x18013e147  xor     ebx, ebx
0x18013e149  cmp     [rdi+208h], ebx
0x18013e14f  jbe     short loc_18013E171
0x18013e151  mov     rax, [rdi+228h]
0x18013e158  mov     rcx, [rax+rbx*8]; ho
0x18013e15c  test    rcx, rcx
0x18013e15f  jz      short loc_18013E167
0x18013e161  call    cs:__imp_DeleteObject
0x18013e167  inc     ebx
0x18013e169  cmp     ebx, [rdi+208h]
0x18013e16f  jb      short loc_18013E151
0x18013e171  mov     rcx, [rdi+228h]; hMem
0x18013e178  call    cs:__imp_LocalFree
0x18013e17e  cmp     qword ptr [rdi+1A0h], 0
0x18013e186  jz      short loc_18013E1D3
0x18013e188  xor     ebx, ebx
0x18013e18a  cmp     [rdi+198h], ebx
0x18013e190  jbe     short loc_18013E1B9
0x18013e192  mov     rax, [rdi+1A0h]
0x18013e199  mov     ecx, ebx
0x18013e19b  shl     rcx, 5
0x18013e19f  mov     rcx, [rcx+rax+8]; ho
0x18013e1a4  test    rcx, rcx
0x18013e1a7  jz      short loc_18013E1AF
0x18013e1a9  call    cs:__imp_DeleteObject
0x18013e1af  inc     ebx
0x18013e1b1  cmp     ebx, [rdi+198h]
0x18013e1b7  jb      short loc_18013E192
0x18013e1b9  mov     rcx, [rdi+1A0h]
0x18013e1c0  jmp     short loc_18013E1CD
0x18013e1c2  mov     rax, [rcx+10h]
0x18013e1c6  mov     [rdi+230h], rax
0x18013e1cd  call    cs:__imp_LocalFree
0x18013e1d3  mov     rcx, [rdi+230h]; hMem
0x18013e1da  test    rcx, rcx
0x18013e1dd  jnz     short loc_18013E1C2
0x18013e1df  mov     rcx, [rdi+1D0h]; hMem
0x18013e1e6  test    rcx, rcx
0x18013e1e9  jz      short loc_18013E200
0x18013e1eb  mov     rbx, [rcx+1D0h]
0x18013e1f2  call    cs:__imp_LocalFree
0x18013e1f8  mov     rcx, rbx
0x18013e1fb  test    rbx, rbx
0x18013e1fe  jnz     short loc_18013E1EB
0x18013e200  mov     rcx, rdi
0x18013e203  mov     rbx, [rsp+28h+arg_0]
0x18013e208  add     rsp, 20h
0x18013e20c  pop     rdi
0x18013e20d  jmp     cs:__imp_LocalFree
```
