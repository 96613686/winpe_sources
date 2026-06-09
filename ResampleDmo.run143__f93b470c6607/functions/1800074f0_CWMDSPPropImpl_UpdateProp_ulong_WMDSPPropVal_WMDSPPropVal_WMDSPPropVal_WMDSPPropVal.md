# CWMDSPPropImpl::UpdateProp(ulong,WMDSPPropVal,WMDSPPropVal,WMDSPPropVal,WMDSPPropVal)

- ea: `0x1800074f0`
- end: `0x180007638`
- name: `?UpdateProp@CWMDSPPropImpl@@MEAAXKTWMDSPPropVal@@000@Z`
- size: `328`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x1800074f0`
- `0x180007640`
- `0x180007758`

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
0x1800074f0  push    rbx
0x1800074f2  push    rbp
0x1800074f3  push    rsi
0x1800074f4  push    rdi
0x1800074f5  push    r12
0x1800074f7  push    r14
0x1800074f9  push    r15
0x1800074fb  sub     rsp, 20h
0x1800074ff  mov     rax, [rcx+18h]
0x180007503  mov     rbx, rcx
0x180007506  mov     r10d, edx
0x180007509  mov     r15, r9
0x18000750c  mov     rbp, r8
0x18000750f  lea     rdi, [r10+r10*8]
0x180007513  lea     r14, [rax+rdi*8]
0x180007517  mov     rax, [rcx+10h]
0x18000751b  lea     rsi, [r10+r10*2]
0x18000751f  shl     rsi, 5
0x180007523  lea     rdx, [r14+8]
0x180007527  movzx   r12d, word ptr [rsi+rax+14h]
0x18000752d  movzx   ecx, r12w
0x180007531  call    WMDSPPropValEqual
0x180007536  test    eax, eax
0x180007538  jnz     short loc_180007555
0x18000753a  mov     r8, rbp
0x18000753d  lea     rdx, [r14+8]
0x180007541  movzx   ecx, r12w
0x180007545  call    WMDSPPropValCopy
0x18000754a  mov     rax, [rbx+18h]
0x18000754e  mov     dword ptr [rax+rdi*8], 1
0x180007555  mov     rax, [rbx+18h]
0x180007559  mov     r8, r15
0x18000755c  lea     rbp, [rax+rdi*8]
0x180007560  mov     rax, [rbx+10h]
0x180007564  lea     rdx, [rbp+18h]
0x180007568  movzx   r14d, word ptr [rsi+rax+14h]
0x18000756e  movzx   ecx, r14w
0x180007572  call    WMDSPPropValEqual
0x180007577  test    eax, eax
0x180007579  jnz     short loc_180007596
0x18000757b  mov     r8, r15
0x18000757e  lea     rdx, [rbp+18h]
0x180007582  movzx   ecx, r14w
0x180007586  call    WMDSPPropValCopy
0x18000758b  mov     rax, [rbx+18h]
0x18000758f  mov     dword ptr [rax+rdi*8], 1
0x180007596  mov     rax, [rbx+18h]
0x18000759a  mov     r8, [rsp+58h+arg_20]
0x1800075a2  lea     rbp, [rax+rdi*8]
0x1800075a6  mov     rax, [rbx+10h]
0x1800075aa  lea     rdx, [rbp+28h]
0x1800075ae  movzx   r14d, word ptr [rsi+rax+14h]
0x1800075b4  movzx   ecx, r14w
0x1800075b8  call    WMDSPPropValEqual
0x1800075bd  test    eax, eax
0x1800075bf  jnz     short loc_1800075E1
0x1800075c1  mov     r8, [rsp+58h+arg_20]
0x1800075c9  lea     rdx, [rbp+28h]
0x1800075cd  movzx   ecx, r14w
0x1800075d1  call    WMDSPPropValCopy
0x1800075d6  mov     rax, [rbx+18h]
0x1800075da  mov     dword ptr [rax+rdi*8], 1
0x1800075e1  mov     rax, [rbx+18h]
0x1800075e5  mov     r8, [rsp+58h+arg_28]
0x1800075ed  lea     rbp, [rax+rdi*8]
0x1800075f1  mov     rax, [rbx+10h]
0x1800075f5  lea     rdx, [rbp+38h]
0x1800075f9  movzx   esi, word ptr [rsi+rax+14h]
0x1800075fe  movzx   ecx, si
0x180007601  call    WMDSPPropValEqual
0x180007606  test    eax, eax
0x180007608  jnz     short loc_180007629
0x18000760a  mov     r8, [rsp+58h+arg_28]
0x180007612  lea     rdx, [rbp+38h]
0x180007616  movzx   ecx, si
0x180007619  call    WMDSPPropValCopy
0x18000761e  mov     rax, [rbx+18h]
0x180007622  mov     dword ptr [rax+rdi*8], 1
0x180007629  add     rsp, 20h
0x18000762d  pop     r15
0x18000762f  pop     r14
0x180007631  pop     r12
0x180007633  pop     rdi
0x180007634  pop     rsi
0x180007635  pop     rbp
0x180007636  pop     rbx
0x180007637  retn
```
