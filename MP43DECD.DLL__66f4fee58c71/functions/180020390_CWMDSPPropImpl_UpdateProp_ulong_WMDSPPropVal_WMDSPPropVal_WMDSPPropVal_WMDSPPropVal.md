# CWMDSPPropImpl::UpdateProp(ulong,WMDSPPropVal,WMDSPPropVal,WMDSPPropVal,WMDSPPropVal)

- ea: `0x180020390`
- end: `0x1800204d8`
- name: `?UpdateProp@CWMDSPPropImpl@@MEAAXKTWMDSPPropVal@@000@Z`
- size: `328`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180020390`
- `0x1800204e0`
- `0x1800205d0`

## pseudocode

```c
__int64 __fastcall CWMDSPPropImpl::UpdateProp(__int64 a1, unsigned int a2, int *a3, int *a4, int *a5, int *a6)
{
  __int64 v9; // rdi
  __int64 v10; // r14
  __int64 v11; // rsi
  unsigned __int16 v12; // r12
  __int64 v13; // rbp
  unsigned __int16 v14; // r14
  __int64 v15; // rbp
  unsigned __int16 v16; // r14
  __int64 v17; // rbp
  unsigned __int16 v18; // si
  __int64 result; // rax

  v9 = 9LL * a2;
  v10 = *(_QWORD *)(a1 + 24) + 72LL * a2;
  v11 = 96LL * a2;
  v12 = *(_WORD *)(v11 + *(_QWORD *)(a1 + 16) + 20);
  if ( !(unsigned int)WMDSPPropValEqual(v12, v10 + 8) )
  {
    WMDSPPropValCopy(v12, (OLECHAR **)(v10 + 8), a3);
    *(_DWORD *)(*(_QWORD *)(a1 + 24) + 8 * v9) = 1;
  }
  v13 = *(_QWORD *)(a1 + 24) + 8 * v9;
  v14 = *(_WORD *)(v11 + *(_QWORD *)(a1 + 16) + 20);
  if ( !(unsigned int)WMDSPPropValEqual(v14, v13 + 24) )
  {
    WMDSPPropValCopy(v14, (OLECHAR **)(v13 + 24), a4);
    *(_DWORD *)(*(_QWORD *)(a1 + 24) + 8 * v9) = 1;
  }
  v15 = *(_QWORD *)(a1 + 24) + 8 * v9;
  v16 = *(_WORD *)(v11 + *(_QWORD *)(a1 + 16) + 20);
  if ( !(unsigned int)WMDSPPropValEqual(v16, v15 + 40) )
  {
    WMDSPPropValCopy(v16, (OLECHAR **)(v15 + 40), a5);
    *(_DWORD *)(*(_QWORD *)(a1 + 24) + 8 * v9) = 1;
  }
  v17 = *(_QWORD *)(a1 + 24) + 8 * v9;
  v18 = *(_WORD *)(v11 + *(_QWORD *)(a1 + 16) + 20);
  result = WMDSPPropValEqual(v18, v17 + 56);
  if ( !(_DWORD)result )
  {
    WMDSPPropValCopy(v18, (OLECHAR **)(v17 + 56), a6);
    result = *(_QWORD *)(a1 + 24);
    *(_DWORD *)(result + 8 * v9) = 1;
  }
  return result;
}

```

## disassembly

```asm
0x180020390  push    rbx
0x180020392  push    rbp
0x180020393  push    rsi
0x180020394  push    rdi
0x180020395  push    r12
0x180020397  push    r14
0x180020399  push    r15
0x18002039b  sub     rsp, 20h
0x18002039f  mov     rax, [rcx+18h]
0x1800203a3  mov     rbx, rcx
0x1800203a6  mov     r10d, edx
0x1800203a9  mov     r15, r9
0x1800203ac  mov     rbp, r8
0x1800203af  lea     rdi, [r10+r10*8]
0x1800203b3  lea     r14, [rax+rdi*8]
0x1800203b7  mov     rax, [rcx+10h]
0x1800203bb  lea     rsi, [r10+r10*2]
0x1800203bf  shl     rsi, 5
0x1800203c3  lea     rdx, [r14+8]
0x1800203c7  movzx   r12d, word ptr [rsi+rax+14h]
0x1800203cd  movzx   ecx, r12w
0x1800203d1  call    WMDSPPropValEqual
0x1800203d6  test    eax, eax
0x1800203d8  jnz     short loc_1800203F5
0x1800203da  mov     r8, rbp
0x1800203dd  lea     rdx, [r14+8]
0x1800203e1  movzx   ecx, r12w
0x1800203e5  call    WMDSPPropValCopy
0x1800203ea  mov     rax, [rbx+18h]
0x1800203ee  mov     dword ptr [rax+rdi*8], 1
0x1800203f5  mov     rax, [rbx+18h]
0x1800203f9  mov     r8, r15
0x1800203fc  lea     rbp, [rax+rdi*8]
0x180020400  mov     rax, [rbx+10h]
0x180020404  lea     rdx, [rbp+18h]
0x180020408  movzx   r14d, word ptr [rsi+rax+14h]
0x18002040e  movzx   ecx, r14w
0x180020412  call    WMDSPPropValEqual
0x180020417  test    eax, eax
0x180020419  jnz     short loc_180020436
0x18002041b  mov     r8, r15
0x18002041e  lea     rdx, [rbp+18h]
0x180020422  movzx   ecx, r14w
0x180020426  call    WMDSPPropValCopy
0x18002042b  mov     rax, [rbx+18h]
0x18002042f  mov     dword ptr [rax+rdi*8], 1
0x180020436  mov     rax, [rbx+18h]
0x18002043a  mov     r8, [rsp+58h+arg_20]
0x180020442  lea     rbp, [rax+rdi*8]
0x180020446  mov     rax, [rbx+10h]
0x18002044a  lea     rdx, [rbp+28h]
0x18002044e  movzx   r14d, word ptr [rsi+rax+14h]
0x180020454  movzx   ecx, r14w
0x180020458  call    WMDSPPropValEqual
0x18002045d  test    eax, eax
0x18002045f  jnz     short loc_180020481
0x180020461  mov     r8, [rsp+58h+arg_20]
0x180020469  lea     rdx, [rbp+28h]
0x18002046d  movzx   ecx, r14w
0x180020471  call    WMDSPPropValCopy
0x180020476  mov     rax, [rbx+18h]
0x18002047a  mov     dword ptr [rax+rdi*8], 1
0x180020481  mov     rax, [rbx+18h]
0x180020485  mov     r8, [rsp+58h+arg_28]
0x18002048d  lea     rbp, [rax+rdi*8]
0x180020491  mov     rax, [rbx+10h]
0x180020495  lea     rdx, [rbp+38h]
0x180020499  movzx   esi, word ptr [rsi+rax+14h]
0x18002049e  movzx   ecx, si
0x1800204a1  call    WMDSPPropValEqual
0x1800204a6  test    eax, eax
0x1800204a8  jnz     short loc_1800204C9
0x1800204aa  mov     r8, [rsp+58h+arg_28]
0x1800204b2  lea     rdx, [rbp+38h]
0x1800204b6  movzx   ecx, si
0x1800204b9  call    WMDSPPropValCopy
0x1800204be  mov     rax, [rbx+18h]
0x1800204c2  mov     dword ptr [rax+rdi*8], 1
0x1800204c9  add     rsp, 20h
0x1800204cd  pop     r15
0x1800204cf  pop     r14
0x1800204d1  pop     r12
0x1800204d3  pop     rdi
0x1800204d4  pop     rsi
0x1800204d5  pop     rbp
0x1800204d6  pop     rbx
0x1800204d7  retn
```
