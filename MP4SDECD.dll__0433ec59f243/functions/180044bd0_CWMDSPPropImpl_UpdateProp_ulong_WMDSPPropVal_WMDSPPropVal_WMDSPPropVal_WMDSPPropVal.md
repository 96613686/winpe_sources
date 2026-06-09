# CWMDSPPropImpl::UpdateProp(ulong,WMDSPPropVal,WMDSPPropVal,WMDSPPropVal,WMDSPPropVal)

- ea: `0x180044bd0`
- end: `0x180044d18`
- name: `?UpdateProp@CWMDSPPropImpl@@MEAAXKTWMDSPPropVal@@000@Z`
- size: `328`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180044bd0`
- `0x180044e64`
- `0x180044f54`

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
0x180044bd0  push    rbx
0x180044bd2  push    rbp
0x180044bd3  push    rsi
0x180044bd4  push    rdi
0x180044bd5  push    r12
0x180044bd7  push    r14
0x180044bd9  push    r15
0x180044bdb  sub     rsp, 20h
0x180044bdf  mov     rax, [rcx+18h]
0x180044be3  mov     rbx, rcx
0x180044be6  mov     r10d, edx
0x180044be9  mov     r15, r9
0x180044bec  mov     rbp, r8
0x180044bef  lea     rdi, [r10+r10*8]
0x180044bf3  lea     r14, [rax+rdi*8]
0x180044bf7  mov     rax, [rcx+10h]
0x180044bfb  lea     rsi, [r10+r10*2]
0x180044bff  shl     rsi, 5
0x180044c03  lea     rdx, [r14+8]
0x180044c07  movzx   r12d, word ptr [rsi+rax+14h]
0x180044c0d  movzx   ecx, r12w
0x180044c11  call    WMDSPPropValEqual
0x180044c16  test    eax, eax
0x180044c18  jnz     short loc_180044C35
0x180044c1a  mov     r8, rbp
0x180044c1d  lea     rdx, [r14+8]
0x180044c21  movzx   ecx, r12w
0x180044c25  call    WMDSPPropValCopy
0x180044c2a  mov     rax, [rbx+18h]
0x180044c2e  mov     dword ptr [rax+rdi*8], 1
0x180044c35  mov     rax, [rbx+18h]
0x180044c39  mov     r8, r15
0x180044c3c  lea     rbp, [rax+rdi*8]
0x180044c40  mov     rax, [rbx+10h]
0x180044c44  lea     rdx, [rbp+18h]
0x180044c48  movzx   r14d, word ptr [rsi+rax+14h]
0x180044c4e  movzx   ecx, r14w
0x180044c52  call    WMDSPPropValEqual
0x180044c57  test    eax, eax
0x180044c59  jnz     short loc_180044C76
0x180044c5b  mov     r8, r15
0x180044c5e  lea     rdx, [rbp+18h]
0x180044c62  movzx   ecx, r14w
0x180044c66  call    WMDSPPropValCopy
0x180044c6b  mov     rax, [rbx+18h]
0x180044c6f  mov     dword ptr [rax+rdi*8], 1
0x180044c76  mov     rax, [rbx+18h]
0x180044c7a  mov     r8, [rsp+58h+arg_20]
0x180044c82  lea     rbp, [rax+rdi*8]
0x180044c86  mov     rax, [rbx+10h]
0x180044c8a  lea     rdx, [rbp+28h]
0x180044c8e  movzx   r14d, word ptr [rsi+rax+14h]
0x180044c94  movzx   ecx, r14w
0x180044c98  call    WMDSPPropValEqual
0x180044c9d  test    eax, eax
0x180044c9f  jnz     short loc_180044CC1
0x180044ca1  mov     r8, [rsp+58h+arg_20]
0x180044ca9  lea     rdx, [rbp+28h]
0x180044cad  movzx   ecx, r14w
0x180044cb1  call    WMDSPPropValCopy
0x180044cb6  mov     rax, [rbx+18h]
0x180044cba  mov     dword ptr [rax+rdi*8], 1
0x180044cc1  mov     rax, [rbx+18h]
0x180044cc5  mov     r8, [rsp+58h+arg_28]
0x180044ccd  lea     rbp, [rax+rdi*8]
0x180044cd1  mov     rax, [rbx+10h]
0x180044cd5  lea     rdx, [rbp+38h]
0x180044cd9  movzx   esi, word ptr [rsi+rax+14h]
0x180044cde  movzx   ecx, si
0x180044ce1  call    WMDSPPropValEqual
0x180044ce6  test    eax, eax
0x180044ce8  jnz     short loc_180044D09
0x180044cea  mov     r8, [rsp+58h+arg_28]
0x180044cf2  lea     rdx, [rbp+38h]
0x180044cf6  movzx   ecx, si
0x180044cf9  call    WMDSPPropValCopy
0x180044cfe  mov     rax, [rbx+18h]
0x180044d02  mov     dword ptr [rax+rdi*8], 1
0x180044d09  add     rsp, 20h
0x180044d0d  pop     r15
0x180044d0f  pop     r14
0x180044d11  pop     r12
0x180044d13  pop     rdi
0x180044d14  pop     rsi
0x180044d15  pop     rbp
0x180044d16  pop     rbx
0x180044d17  retn
```
