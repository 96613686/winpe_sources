# SubAllocate

- ea: `0x1800071e0`
- end: `0x1800072ac`
- name: `SubAllocate`
- size: `204`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000380c`
- `0x180007b4c`

## callees

- `0x1800071e0`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180007243`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18000726b`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180007243`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18000726b`

## pseudocode

```c
_QWORD *__fastcall SubAllocate(_QWORD *a1, __int64 a2)
{
  _QWORD *result; // rax
  unsigned __int64 v3; // rbx
  SIZE_T v5; // rdi
  _QWORD *v6; // rcx

  result = (_QWORD *)a1[2];
  v3 = (a2 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
  if ( v3 > a1[3] - (_QWORD)result )
  {
    v5 = a1[4];
    if ( v5 < v3 + 8 )
      v5 = (v3 + 65543) & 0xFFFFFFFFFFFF0000uLL;
    v6 = VirtualAlloc(0, v5, 0x1000u, 4u);
    if ( v6 || v3 <= 0xFFF8 && (v5 = 0x10000, (v6 = VirtualAlloc(0, 0x10000u, 0x1000u, 4u)) != 0) )
    {
      a1[3] = (char *)v6 + v5;
      *v6 = a1[1];
      result = v6 + 1;
      a1[1] = v6;
      a1[2] = (char *)v6 + v3 + 8;
    }
    else
    {
      return 0;
    }
  }
  else
  {
    a1[2] = (char *)result + v3;
  }
  return result;
}

```

## disassembly

```asm
0x1800071e0  mov     [rsp+arg_0], rbx
0x1800071e5  mov     [rsp+arg_8], rsi
0x1800071ea  push    rdi
0x1800071eb  sub     rsp, 20h
0x1800071ef  mov     rax, [rcx+10h]
0x1800071f3  lea     rbx, [rdx+7]
0x1800071f7  mov     rdx, [rcx+18h]
0x1800071fb  and     rbx, 0FFFFFFFFFFFFFFF8h
0x1800071ff  sub     rdx, rax
0x180007202  mov     rsi, rcx
0x180007205  cmp     rbx, rdx
0x180007208  ja      short loc_180007217
0x18000720a  lea     rdx, [rax+rbx]
0x18000720e  mov     [rcx+10h], rdx
0x180007212  jmp     loc_18000729C
0x180007217  mov     rdi, [rcx+20h]
0x18000721b  lea     rax, [rbx+8]
0x18000721f  cmp     rdi, rax
0x180007222  jnb     short loc_180007232
0x180007224  lea     rdi, [rbx+10007h]
0x18000722b  and     rdi, 0FFFFFFFFFFFF0000h
0x180007232  mov     r9d, 4; flProtect
0x180007238  mov     r8d, 1000h; flAllocationType
0x18000723e  mov     rdx, rdi; dwSize
0x180007241  xor     ecx, ecx; lpAddress
0x180007243  call    cs:__imp_VirtualAlloc
0x180007249  mov     rcx, rax; lpAddress
0x18000724c  test    rax, rax
0x18000724f  jnz     short loc_18000727D
0x180007251  cmp     rbx, 0FFF8h
0x180007258  ja      short loc_180007279
0x18000725a  mov     edi, 10000h
0x18000725f  lea     r9d, [rax+4]; flProtect
0x180007263  mov     edx, edi; dwSize
0x180007265  mov     r8d, 1000h; flAllocationType
0x18000726b  call    cs:__imp_VirtualAlloc
0x180007271  mov     rcx, rax
0x180007274  test    rax, rax
0x180007277  jnz     short loc_18000727D
0x180007279  xor     eax, eax
0x18000727b  jmp     short loc_18000729C
0x18000727d  lea     rax, [rdi+rcx]
0x180007281  mov     [rsi+18h], rax
0x180007285  mov     rax, [rsi+8]
0x180007289  mov     [rcx], rax
0x18000728c  lea     rax, [rcx+8]
0x180007290  mov     [rsi+8], rcx
0x180007294  lea     rcx, [rax+rbx]
0x180007298  mov     [rsi+10h], rcx
0x18000729c  mov     rbx, [rsp+28h+arg_0]
0x1800072a1  mov     rsi, [rsp+28h+arg_8]
0x1800072a6  add     rsp, 20h
0x1800072aa  pop     rdi
0x1800072ab  retn
```
