# XCF_ReadBlock

- ea: `0x180048b5c`
- end: `0x180048bc8`
- name: `XCF_ReadBlock`
- size: `108`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180046318`
- `0x180046530`
- `0x1800466cc`
- `0x180046a58`
- `0x180046b10`
- `0x180046c1c`
- `0x180046ce0`
- `0x180048774`
- `0x1800487e0`
- `0x18004eee0`

## callees

- `0x180048b5c`
- `0x18004e048`
- `0x18005d010`

## pseudocode

```c
__int64 __fastcall XCF_ReadBlock(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 *v3; // r14
  __int64 v5; // rdi
  int v6; // esi
  __int64 v7; // rcx
  __int64 result; // rax

  v3 = (__int64 *)(a1 + 14144);
  v5 = (unsigned int)a3;
  v6 = a2;
  if ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64, _QWORD))(a1 + 288))(
          a1 + 14144,
          a2,
          a3,
          *(_QWORD *)(a1 + 296)) )
    XCF_FatalErrorHandler(a1, 22);
  v7 = *v3;
  *(_QWORD *)(a1 + 14160) = *v3;
  *(_DWORD *)(a1 + 14168) = v6;
  *(_DWORD *)(a1 + 14172) = v5;
  result = v7 + v5;
  *(_QWORD *)(a1 + 14152) = v7 + v5;
  return result;
}

```

## disassembly

```asm
0x180048b5c  push    rbx
0x180048b5e  push    rsi
0x180048b5f  push    rdi
0x180048b60  push    r14
0x180048b62  sub     rsp, 38h
0x180048b66  mov     r9, [rcx+128h]
0x180048b6d  lea     r14, [rcx+3740h]
0x180048b74  mov     rbx, rcx
0x180048b77  mov     edi, r8d
0x180048b7a  mov     rcx, r14
0x180048b7d  mov     esi, edx
0x180048b7f  mov     rax, [rbx+120h]
0x180048b86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048b8b  test    eax, eax
0x180048b8d  jz      short loc_180048BBA
0x180048b8f  mov     rcx, [r14]
0x180048b92  mov     [rbx+3750h], rcx
0x180048b99  mov     [rbx+3758h], esi
0x180048b9f  mov     [rbx+375Ch], edi
0x180048ba5  lea     rax, [rcx+rdi]
0x180048ba9  mov     [rbx+3748h], rax
0x180048bb0  add     rsp, 38h
0x180048bb4  pop     r14
0x180048bb6  pop     rdi
0x180048bb7  pop     rsi
0x180048bb8  pop     rbx
0x180048bb9  retn
0x180048bba  mov     edx, 16h
0x180048bbf  mov     rcx, rbx
0x180048bc2  call    XCF_FatalErrorHandler
```
