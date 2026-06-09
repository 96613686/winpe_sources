# XCF_Read

- ea: `0x18004e27c`
- end: `0x18004e31b`
- name: `XCF_Read`
- size: `159`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180046318`
- `0x180046ce0`
- `0x180048774`
- `0x18004e0e0`

## callees

- `0x18004e048`
- `0x18004e27c`

## pseudocode

```c
__int64 __fastcall XCF_Read(__int64 a1, int a2)
{
  unsigned __int8 *v3; // rcx
  int v4; // r8d
  int v5; // edx
  int v6; // edx
  int v7; // edx
  __int64 result; // rax

  v3 = *(unsigned __int8 **)(a1 + 14160);
  if ( (unsigned __int64)&v3[a2] > *(_QWORD *)(a1 + 14152) )
    XCF_FatalErrorHandler(a1, 1);
  v4 = 0;
  v5 = a2 - 1;
  if ( v5 )
  {
    v6 = v5 - 1;
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( v7 )
      {
        if ( v7 != 1 )
          XCF_FatalErrorHandler(a1, 20);
        v4 = *v3++ << 8;
        *(_QWORD *)(a1 + 14160) = v3;
      }
      v4 = (*v3++ + v4) << 8;
      *(_QWORD *)(a1 + 14160) = v3;
    }
    v4 = (*v3++ + v4) << 8;
    *(_QWORD *)(a1 + 14160) = v3;
  }
  result = v4 + (unsigned int)*v3;
  *(_QWORD *)(a1 + 14160) = v3 + 1;
  return result;
}

```

## disassembly

```asm
0x18004e27c  sub     rsp, 28h
0x18004e280  mov     r9, rcx
0x18004e283  movsxd  rax, edx
0x18004e286  mov     rcx, [rcx+3750h]
0x18004e28d  add     rax, rcx
0x18004e290  cmp     rax, [r9+3748h]
0x18004e297  ja      short loc_18004E2FF
0x18004e299  xor     r8d, r8d
0x18004e29c  sub     edx, 1
0x18004e29f  jz      short loc_18004E2EA
0x18004e2a1  sub     edx, 1
0x18004e2a4  jz      short loc_18004E2D6
0x18004e2a6  sub     edx, 1
0x18004e2a9  jz      short loc_18004E2C2
0x18004e2ab  cmp     edx, 1
0x18004e2ae  jnz     short loc_18004E30D
0x18004e2b0  movzx   r8d, byte ptr [rcx]
0x18004e2b4  shl     r8d, 8
0x18004e2b8  inc     rcx
0x18004e2bb  mov     [r9+3750h], rcx
0x18004e2c2  movzx   eax, byte ptr [rcx]
0x18004e2c5  add     r8d, eax
0x18004e2c8  shl     r8d, 8
0x18004e2cc  inc     rcx
0x18004e2cf  mov     [r9+3750h], rcx
0x18004e2d6  movzx   eax, byte ptr [rcx]
0x18004e2d9  add     r8d, eax
0x18004e2dc  shl     r8d, 8
0x18004e2e0  inc     rcx
0x18004e2e3  mov     [r9+3750h], rcx
0x18004e2ea  movzx   eax, byte ptr [rcx]
0x18004e2ed  add     eax, r8d
0x18004e2f0  inc     rcx
0x18004e2f3  mov     [r9+3750h], rcx
0x18004e2fa  add     rsp, 28h
0x18004e2fe  retn
0x18004e2ff  mov     edx, 1
0x18004e304  mov     rcx, r9
0x18004e307  call    XCF_FatalErrorHandler
0x18004e30d  mov     edx, 14h
0x18004e312  mov     rcx, r9
0x18004e315  call    XCF_FatalErrorHandler
```
