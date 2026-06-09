# XC_WriteFlex1

- ea: `0x180053eb8`
- end: `0x180054130`
- name: `XC_WriteFlex1`
- size: `632`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180051af4`

## callees

- `0x180001f20`
- `0x180002938`
- `0x18004f8e4`
- `0x180050b84`
- `0x180050d8c`
- `0x180050dd4`
- `0x180050ea8`
- `0x1800520e8`
- `0x180053eb8`

## pseudocode

```c
__int64 __fastcall XC_WriteFlex1(__int64 a1, unsigned int a2)
{
  int v4; // ecx
  int v5; // eax
  unsigned int v7; // [rsp+80h] [rbp-80h] BYREF
  int v8; // [rsp+84h] [rbp-7Ch]
  unsigned int v9; // [rsp+D0h] [rbp-30h] BYREF
  int v10; // [rsp+D4h] [rbp-2Ch]
  unsigned int v11[20]; // [rsp+120h] [rbp+20h] BYREF
  unsigned int v12[20]; // [rsp+170h] [rbp+70h] BYREF
  unsigned int v13[20]; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned int v14[20]; // [rsp+210h] [rbp+110h] BYREF

  memset_0(v13, 0, 0x44u);
  memset_0(v14, 0, 0x44u);
  memset_0(v12, 0, 0x44u);
  memset_0(v11, 0, 0x44u);
  memset_0(&v9, 0, 0x44u);
  memset_0(&v7, 0, 0x44u);
  if ( *(_WORD *)(a1 + 22736) != 11 )
    XCF_FatalErrorHandler((_JBTYPE *)a1, 14);
  PSVAdd5(
    a1,
    (__int64)&v9,
    *(_QWORD *)(a1 + 21968),
    *(_QWORD *)(a1 + 21984),
    *(_QWORD *)(a1 + 22000),
    *(_QWORD *)(a1 + 22016),
    *(_QWORD *)(a1 + 22032));
  PSVAdd5(
    a1,
    (__int64)&v7,
    *(_QWORD *)(a1 + 21976),
    *(_QWORD *)(a1 + 21992),
    *(_QWORD *)(a1 + 22008),
    *(_QWORD *)(a1 + 22024),
    *(_QWORD *)(a1 + 22040));
  if ( *(_DWORD *)(a1 + 488) )
  {
    PStackValueAdd(a1, v13, *(unsigned int **)(a1 + 21952), &v9);
    if ( *(_DWORD *)(a1 + 488) )
      PStackValueAdd(a1, v14, *(unsigned int **)(a1 + 21960), &v7);
  }
  v4 = -v8;
  if ( v8 > 0 )
    v4 = v8;
  v5 = -v10;
  if ( v10 > 0 )
    v5 = v10;
  if ( v5 <= v4 )
  {
    PSVSubtract(a1, v12, *(unsigned int **)(a1 + 26048), &v9);
    PSVCopy(a1, v11, *(unsigned int **)(a1 + 22048));
  }
  else
  {
    PSVCopy(a1, v12, *(unsigned int **)(a1 + 22048));
    PSVSubtract(a1, v11, *(unsigned int **)(a1 + 26048), &v7);
  }
  return WriteExpandedFlexCurveTo(
           a1,
           *(unsigned int **)(a1 + 21968),
           *(unsigned int **)(a1 + 21976),
           *(unsigned int **)(a1 + 21984),
           *(unsigned int **)(a1 + 21992),
           *(unsigned int **)(a1 + 22000),
           *(unsigned int **)(a1 + 22008),
           *(_DWORD **)(a1 + 22016),
           *(_DWORD **)(a1 + 22024),
           *(_DWORD **)(a1 + 22032),
           *(_DWORD **)(a1 + 22040),
           v12,
           v11,
           *(_DWORD **)(a1 + 26056),
           a2);
}

```

## disassembly

```asm
0x180053eb8  push    rbp
0x180053eba  push    rbx
0x180053ebb  push    rsi
0x180053ebc  push    rdi
0x180053ebd  lea     rbp, [rsp-178h]
0x180053ec5  sub     rsp, 278h
0x180053ecc  mov     rax, cs:__security_cookie
0x180053ed3  xor     rax, rsp
0x180053ed6  mov     [rbp+190h+var_30], rax
0x180053edd  mov     edi, edx
0x180053edf  mov     rbx, rcx
0x180053ee2  mov     esi, 44h ; 'D'
0x180053ee7  lea     rcx, [rbp+190h+var_D0]; void *
0x180053eee  mov     r8d, esi; Size
0x180053ef1  xor     edx, edx; Val
0x180053ef3  call    memset_0
0x180053ef8  mov     r8d, esi; Size
0x180053efb  lea     rcx, [rbp+190h+var_80]; void *
0x180053f02  xor     edx, edx; Val
0x180053f04  call    memset_0
0x180053f09  mov     r8d, esi; Size
0x180053f0c  lea     rcx, [rbp+190h+var_120]; void *
0x180053f10  xor     edx, edx; Val
0x180053f12  call    memset_0
0x180053f17  mov     r8d, esi; Size
0x180053f1a  lea     rcx, [rbp+190h+var_170]; void *
0x180053f1e  xor     edx, edx; Val
0x180053f20  call    memset_0
0x180053f25  mov     r8d, esi; Size
0x180053f28  lea     rcx, [rbp+190h+var_1C0]; void *
0x180053f2c  xor     edx, edx; Val
0x180053f2e  call    memset_0
0x180053f33  mov     r8d, esi; Size
0x180053f36  lea     rcx, [rbp+190h+var_210]; void *
0x180053f3a  xor     edx, edx; Val
0x180053f3c  call    memset_0
0x180053f41  cmp     word ptr [rbx+58D0h], 0Bh
0x180053f49  mov     rcx, rbx
0x180053f4c  jnz     loc_180054125
0x180053f52  mov     rax, [rbx+5610h]
0x180053f59  lea     rdx, [rbp+190h+var_1C0]
0x180053f5d  mov     r9, [rbx+55E0h]
0x180053f64  mov     r8, [rbx+55D0h]
0x180053f6b  mov     [rsp+290h+var_260], rax
0x180053f70  mov     rax, [rbx+5600h]
0x180053f77  mov     [rsp+290h+var_268], rax
0x180053f7c  mov     rax, [rbx+55F0h]
0x180053f83  mov     [rsp+290h+var_270], rax
0x180053f88  call    PSVAdd5
0x180053f8d  mov     rax, [rbx+5618h]
0x180053f94  lea     rdx, [rbp+190h+var_210]
0x180053f98  mov     r9, [rbx+55E8h]
0x180053f9f  mov     rcx, rbx
0x180053fa2  mov     r8, [rbx+55D8h]
0x180053fa9  mov     [rsp+290h+var_260], rax
0x180053fae  mov     rax, [rbx+5608h]
0x180053fb5  mov     [rsp+290h+var_268], rax
0x180053fba  mov     rax, [rbx+55F8h]
0x180053fc1  mov     [rsp+290h+var_270], rax
0x180053fc6  call    PSVAdd5
0x180053fcb  cmp     dword ptr [rbx+1E8h], 0
0x180053fd2  jz      short loc_180054011
0x180053fd4  mov     r8, [rbx+55C0h]
0x180053fdb  lea     r9, [rbp+190h+var_1C0]
0x180053fdf  lea     rdx, [rbp+190h+var_D0]
0x180053fe6  mov     rcx, rbx
0x180053fe9  call    PStackValueAdd
0x180053fee  cmp     dword ptr [rbx+1E8h], 0
0x180053ff5  jz      short loc_180054011
0x180053ff7  mov     r8, [rbx+55C8h]
0x180053ffe  lea     r9, [rbp+190h+var_210]
0x180054002  lea     rdx, [rbp+190h+var_80]
0x180054009  mov     rcx, rbx
0x18005400c  call    PStackValueAdd
0x180054011  mov     ecx, [rbp+190h+var_20C]
0x180054014  lea     rdx, [rbp+190h+var_120]
0x180054018  mov     eax, [rbp+190h+var_1BC]
0x18005401b  neg     ecx
0x18005401d  cmovs   ecx, [rbp+190h+var_20C]
0x180054021  neg     eax
0x180054023  cmovs   eax, [rbp+190h+var_1BC]
0x180054027  cmp     eax, ecx
0x180054029  mov     rcx, rbx
0x18005402c  jle     short loc_180054053
0x18005402e  mov     r8, [rbx+5620h]
0x180054035  call    PSVCopy
0x18005403a  mov     r8, [rbx+65C0h]
0x180054041  lea     r9, [rbp+190h+var_210]
0x180054045  mov     rcx, rbx
0x180054048  lea     rdx, [rbp+190h+var_170]
0x18005404c  call    PSVSubtract
0x180054051  jmp     short loc_180054076
0x180054053  mov     r8, [rbx+65C0h]
0x18005405a  lea     r9, [rbp+190h+var_1C0]
0x18005405e  call    PSVSubtract
0x180054063  mov     r8, [rbx+5620h]
0x18005406a  lea     rdx, [rbp+190h+var_170]
0x18005406e  mov     rcx, rbx
0x180054071  call    PSVCopy
0x180054076  mov     rax, [rbx+65C8h]
0x18005407d  mov     rcx, rbx
0x180054080  mov     r9, [rbx+55E0h]
0x180054087  mov     r8, [rbx+55D8h]
0x18005408e  mov     rdx, [rbx+55D0h]
0x180054095  mov     [rsp+290h+var_220], edi
0x180054099  mov     [rsp+290h+var_228], rax
0x18005409e  lea     rax, [rbp+190h+var_170]
0x1800540a2  mov     [rsp+290h+var_230], rax
0x1800540a7  lea     rax, [rbp+190h+var_120]
0x1800540ab  mov     [rsp+290h+var_238], rax
0x1800540b0  mov     rax, [rbx+5618h]
0x1800540b7  mov     [rsp+290h+var_240], rax
0x1800540bc  mov     rax, [rbx+5610h]
0x1800540c3  mov     [rsp+290h+var_248], rax
0x1800540c8  mov     rax, [rbx+5608h]
0x1800540cf  mov     [rsp+290h+var_250], rax
0x1800540d4  mov     rax, [rbx+5600h]
0x1800540db  mov     [rsp+290h+var_258], rax
0x1800540e0  mov     rax, [rbx+55F8h]
0x1800540e7  mov     [rsp+290h+var_260], rax
0x1800540ec  mov     rax, [rbx+55F0h]
0x1800540f3  mov     [rsp+290h+var_268], rax
0x1800540f8  mov     rax, [rbx+55E8h]
0x1800540ff  mov     [rsp+290h+var_270], rax
0x180054104  call    WriteExpandedFlexCurveTo
0x180054109  mov     rcx, [rbp+190h+var_30]
0x180054110  xor     rcx, rsp; StackCookie
0x180054113  call    __security_check_cookie
0x180054118  add     rsp, 278h
0x18005411f  pop     rdi
0x180054120  pop     rsi
0x180054121  pop     rbx
0x180054122  pop     rbp
0x180054123  retn
0x180054125  mov     edx, 0Eh
0x18005412a  call    XCF_FatalErrorHandler
```
