# XCF_ReadBlock

- ea: `0x18004a3cc`
- end: `0x18004a439`
- name: `XCF_ReadBlock`
- size: `109`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `10`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180047c38`
- `0x180047e54`
- `0x180047ff4`
- `0x180048380`
- `0x180048438`
- `0x180048544`
- `0x180048608`
- `0x180049fe4`
- `0x18004a050`
- `0x180050848`

## callees

- `0x18004a3cc`
- `0x18004f8e4`
- `0x18005f010`

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
    XCF_FatalErrorHandler((_JBTYPE *)a1, 22);
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
0x18004a3cc  push    rbx
0x18004a3ce  push    rsi
0x18004a3cf  push    rdi
0x18004a3d0  push    r14
0x18004a3d2  sub     rsp, 38h
0x18004a3d6  mov     r9, [rcx+128h]
0x18004a3dd  lea     r14, [rcx+3740h]
0x18004a3e4  mov     rbx, rcx
0x18004a3e7  mov     edi, r8d
0x18004a3ea  mov     rcx, r14
0x18004a3ed  mov     esi, edx
0x18004a3ef  mov     rax, [rbx+120h]
0x18004a3f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a3fb  test    eax, eax
0x18004a3fd  jz      short loc_18004A42B
0x18004a3ff  mov     rcx, [r14]
0x18004a402  mov     [rbx+3750h], rcx
0x18004a409  mov     [rbx+3758h], esi
0x18004a40f  mov     [rbx+375Ch], edi
0x18004a415  lea     rax, [rcx+rdi]
0x18004a419  mov     [rbx+3748h], rax
0x18004a420  add     rsp, 38h
0x18004a424  pop     r14
0x18004a426  pop     rdi
0x18004a427  pop     rsi
0x18004a428  pop     rbx
0x18004a429  retn
0x18004a42b  mov     edx, 16h
0x18004a430  mov     rcx, rbx
0x18004a433  call    XCF_FatalErrorHandler
```
