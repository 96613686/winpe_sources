# CWMDSPPropImpl::UpdateProp(ulong,WMDSPPropVal,WMDSPPropVal,WMDSPPropVal,WMDSPPropVal)

- ea: `0x180020450`
- end: `0x180020598`
- name: `?UpdateProp@CWMDSPPropImpl@@MEAAXKTWMDSPPropVal@@000@Z`
- size: `328`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180020450`
- `0x1800205a0`
- `0x180020690`

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
0x180020450  push    rbx
0x180020452  push    rbp
0x180020453  push    rsi
0x180020454  push    rdi
0x180020455  push    r12
0x180020457  push    r14
0x180020459  push    r15
0x18002045b  sub     rsp, 20h
0x18002045f  mov     rax, [rcx+18h]
0x180020463  mov     rbx, rcx
0x180020466  mov     r10d, edx
0x180020469  mov     r15, r9
0x18002046c  mov     rbp, r8
0x18002046f  lea     rdi, [r10+r10*8]
0x180020473  lea     r14, [rax+rdi*8]
0x180020477  mov     rax, [rcx+10h]
0x18002047b  lea     rsi, [r10+r10*2]
0x18002047f  shl     rsi, 5
0x180020483  lea     rdx, [r14+8]
0x180020487  movzx   r12d, word ptr [rsi+rax+14h]
0x18002048d  movzx   ecx, r12w
0x180020491  call    WMDSPPropValEqual
0x180020496  test    eax, eax
0x180020498  jnz     short loc_1800204B5
0x18002049a  mov     r8, rbp
0x18002049d  lea     rdx, [r14+8]
0x1800204a1  movzx   ecx, r12w
0x1800204a5  call    WMDSPPropValCopy
0x1800204aa  mov     rax, [rbx+18h]
0x1800204ae  mov     dword ptr [rax+rdi*8], 1
0x1800204b5  mov     rax, [rbx+18h]
0x1800204b9  mov     r8, r15
0x1800204bc  lea     rbp, [rax+rdi*8]
0x1800204c0  mov     rax, [rbx+10h]
0x1800204c4  lea     rdx, [rbp+18h]
0x1800204c8  movzx   r14d, word ptr [rsi+rax+14h]
0x1800204ce  movzx   ecx, r14w
0x1800204d2  call    WMDSPPropValEqual
0x1800204d7  test    eax, eax
0x1800204d9  jnz     short loc_1800204F6
0x1800204db  mov     r8, r15
0x1800204de  lea     rdx, [rbp+18h]
0x1800204e2  movzx   ecx, r14w
0x1800204e6  call    WMDSPPropValCopy
0x1800204eb  mov     rax, [rbx+18h]
0x1800204ef  mov     dword ptr [rax+rdi*8], 1
0x1800204f6  mov     rax, [rbx+18h]
0x1800204fa  mov     r8, [rsp+58h+arg_20]
0x180020502  lea     rbp, [rax+rdi*8]
0x180020506  mov     rax, [rbx+10h]
0x18002050a  lea     rdx, [rbp+28h]
0x18002050e  movzx   r14d, word ptr [rsi+rax+14h]
0x180020514  movzx   ecx, r14w
0x180020518  call    WMDSPPropValEqual
0x18002051d  test    eax, eax
0x18002051f  jnz     short loc_180020541
0x180020521  mov     r8, [rsp+58h+arg_20]
0x180020529  lea     rdx, [rbp+28h]
0x18002052d  movzx   ecx, r14w
0x180020531  call    WMDSPPropValCopy
0x180020536  mov     rax, [rbx+18h]
0x18002053a  mov     dword ptr [rax+rdi*8], 1
0x180020541  mov     rax, [rbx+18h]
0x180020545  mov     r8, [rsp+58h+arg_28]
0x18002054d  lea     rbp, [rax+rdi*8]
0x180020551  mov     rax, [rbx+10h]
0x180020555  lea     rdx, [rbp+38h]
0x180020559  movzx   esi, word ptr [rsi+rax+14h]
0x18002055e  movzx   ecx, si
0x180020561  call    WMDSPPropValEqual
0x180020566  test    eax, eax
0x180020568  jnz     short loc_180020589
0x18002056a  mov     r8, [rsp+58h+arg_28]
0x180020572  lea     rdx, [rbp+38h]
0x180020576  movzx   ecx, si
0x180020579  call    WMDSPPropValCopy
0x18002057e  mov     rax, [rbx+18h]
0x180020582  mov     dword ptr [rax+rdi*8], 1
0x180020589  add     rsp, 20h
0x18002058d  pop     r15
0x18002058f  pop     r14
0x180020591  pop     r12
0x180020593  pop     rdi
0x180020594  pop     rsi
0x180020595  pop     rbp
0x180020596  pop     rbx
0x180020597  retn
```
