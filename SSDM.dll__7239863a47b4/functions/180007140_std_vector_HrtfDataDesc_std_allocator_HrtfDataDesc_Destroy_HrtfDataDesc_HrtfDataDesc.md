# std::vector<HrtfDataDesc,std::allocator<HrtfDataDesc>>::_Destroy(HrtfDataDesc *,HrtfDataDesc *)

- ea: `0x180007140`
- end: `0x1800071cb`
- name: `?_Destroy@?$vector@UHrtfDataDesc@@V?$allocator@UHrtfDataDesc@@@std@@@std@@IEAAXPEAUHrtfDataDesc@@0@Z`
- size: `139`
- prototype: `void __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004a40`
- `0x180004c60`
- `0x180007334`
- `0x1800078e4`

## callees

- `0x180007140`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180007190`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007190`
- `msvcrt!_aligned_free` at `0x18000716a`
- `msvcrt!_aligned_free` at `0x18000716a`

## pseudocode

```c
void __fastcall std::vector<HrtfDataDesc>::_Destroy(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  void **v4; // rdi
  _QWORD *v5; // rbx
  void *v6; // rcx

  if ( a2 != a3 )
  {
    v4 = (void **)(a2 + 4);
    v5 = a2;
    do
    {
      if ( *v4 )
      {
        _aligned_free(*v4);
        *v4 = 0;
        v4[1] = 0;
        v4[2] = 0;
      }
      v6 = (void *)v5[1];
      if ( v6 )
      {
        operator delete(v6);
        v5[1] = 0;
        v5[2] = 0;
        v5[3] = 0;
      }
      v5 += 7;
      v4 += 7;
    }
    while ( v5 != a3 );
  }
}

```

## disassembly

```asm
0x180007140  cmp     rdx, r8
0x180007143  jz      locret_1800071CA
0x180007149  mov     [rsp+arg_0], rbx
0x18000714e  mov     [rsp+arg_8], rsi
0x180007153  push    rdi
0x180007154  sub     rsp, 20h
0x180007158  mov     rsi, r8
0x18000715b  lea     rdi, [rdx+20h]
0x18000715f  mov     rbx, rdx
0x180007162  mov     rcx, [rdi]; Block
0x180007165  test    rcx, rcx
0x180007168  jz      short loc_180007187
0x18000716a  call    cs:__imp__aligned_free
0x180007170  mov     qword ptr [rdi], 0
0x180007177  mov     qword ptr [rdi+8], 0
0x18000717f  mov     qword ptr [rdi+10h], 0
0x180007187  mov     rcx, [rbx+8]
0x18000718b  test    rcx, rcx
0x18000718e  jz      short loc_1800071AE
0x180007190  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007196  mov     qword ptr [rbx+8], 0
0x18000719e  mov     qword ptr [rbx+10h], 0
0x1800071a6  mov     qword ptr [rbx+18h], 0
0x1800071ae  add     rbx, 38h ; '8'
0x1800071b2  add     rdi, 38h ; '8'
0x1800071b6  cmp     rbx, rsi
0x1800071b9  jnz     short loc_180007162
0x1800071bb  mov     rbx, [rsp+28h+arg_0]
0x1800071c0  mov     rsi, [rsp+28h+arg_8]
0x1800071c5  add     rsp, 20h
0x1800071c9  pop     rdi
0x1800071ca  retn
```
