# XC_WriteFlex1

- ea: `0x180052538`
- end: `0x1800527af`
- name: `XC_WriteFlex1`
- size: `631`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18005017c`

## callees

- `0x180001ee0`
- `0x1800028d8`
- `0x18004e048`
- `0x18004f218`
- `0x18004f41c`
- `0x18004f464`
- `0x18004f538`
- `0x180050770`
- `0x180052538`

## pseudocode

```c
__int64 __fastcall XC_WriteFlex1(__int64 a1, unsigned int a2)
{
  int v4; // ecx
  int v5; // eax
  _BYTE v7[4]; // [rsp+80h] [rbp-80h] BYREF
  int v8; // [rsp+84h] [rbp-7Ch]
  _BYTE v9[4]; // [rsp+D0h] [rbp-30h] BYREF
  int v10; // [rsp+D4h] [rbp-2Ch]
  _BYTE v11[80]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v12[80]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v13[80]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v14[80]; // [rsp+210h] [rbp+110h] BYREF

  memset_0(v13, 0, 0x44u);
  memset_0(v14, 0, 0x44u);
  memset_0(v12, 0, 0x44u);
  memset_0(v11, 0, 0x44u);
  memset_0(v9, 0, 0x44u);
  memset_0(v7, 0, 0x44u);
  if ( *(_WORD *)(a1 + 22736) != 11 )
    XCF_FatalErrorHandler(a1, 14);
  PSVAdd5(
    a1,
    (unsigned int)v9,
    *(_QWORD *)(a1 + 21968),
    *(_QWORD *)(a1 + 21984),
    *(_QWORD *)(a1 + 22000),
    *(_QWORD *)(a1 + 22016),
    *(_QWORD *)(a1 + 22032));
  PSVAdd5(
    a1,
    (unsigned int)v7,
    *(_QWORD *)(a1 + 21976),
    *(_QWORD *)(a1 + 21992),
    *(_QWORD *)(a1 + 22008),
    *(_QWORD *)(a1 + 22024),
    *(_QWORD *)(a1 + 22040));
  if ( *(_DWORD *)(a1 + 488) )
  {
    PStackValueAdd(a1, v13, *(_QWORD *)(a1 + 21952), v9);
    if ( *(_DWORD *)(a1 + 488) )
      PStackValueAdd(a1, v14, *(_QWORD *)(a1 + 21960), v7);
  }
  v4 = -v8;
  if ( v8 > 0 )
    v4 = v8;
  v5 = -v10;
  if ( v10 > 0 )
    v5 = v10;
  if ( v5 <= v4 )
  {
    PSVSubtract(a1, v12, *(_QWORD *)(a1 + 26048), v9);
    PSVCopy(a1, v11, *(_QWORD *)(a1 + 22048));
  }
  else
  {
    PSVCopy(a1, v12, *(_QWORD *)(a1 + 22048));
    PSVSubtract(a1, v11, *(_QWORD *)(a1 + 26048), v7);
  }
  return WriteExpandedFlexCurveTo(
           a1,
           *(_QWORD *)(a1 + 21968),
           *(_QWORD *)(a1 + 21976),
           *(_QWORD *)(a1 + 21984),
           *(_QWORD *)(a1 + 21992),
           *(_QWORD *)(a1 + 22000),
           *(_QWORD *)(a1 + 22008),
           *(_QWORD *)(a1 + 22016),
           *(_QWORD *)(a1 + 22024),
           *(_QWORD *)(a1 + 22032),
           *(_QWORD *)(a1 + 22040),
           (__int64)v12,
           (__int64)v11,
           *(_QWORD *)(a1 + 26056),
           a2);
}

```

## disassembly

```asm
0x180052538  push    rbp
0x18005253a  push    rbx
0x18005253b  push    rsi
0x18005253c  push    rdi
0x18005253d  lea     rbp, [rsp-178h]
0x180052545  sub     rsp, 278h
0x18005254c  mov     rax, cs:__security_cookie
0x180052553  xor     rax, rsp
0x180052556  mov     [rbp+190h+var_30], rax
0x18005255d  mov     edi, edx
0x18005255f  mov     rbx, rcx
0x180052562  mov     esi, 44h ; 'D'
0x180052567  lea     rcx, [rbp+190h+var_D0]; void *
0x18005256e  mov     r8d, esi; Size
0x180052571  xor     edx, edx; Val
0x180052573  call    memset_0
0x180052578  mov     r8d, esi; Size
0x18005257b  lea     rcx, [rbp+190h+var_80]; void *
0x180052582  xor     edx, edx; Val
0x180052584  call    memset_0
0x180052589  mov     r8d, esi; Size
0x18005258c  lea     rcx, [rbp+190h+var_120]; void *
0x180052590  xor     edx, edx; Val
0x180052592  call    memset_0
0x180052597  mov     r8d, esi; Size
0x18005259a  lea     rcx, [rbp+190h+var_170]; void *
0x18005259e  xor     edx, edx; Val
0x1800525a0  call    memset_0
0x1800525a5  mov     r8d, esi; Size
0x1800525a8  lea     rcx, [rbp+190h+var_1C0]; void *
0x1800525ac  xor     edx, edx; Val
0x1800525ae  call    memset_0
0x1800525b3  mov     r8d, esi; Size
0x1800525b6  lea     rcx, [rbp+190h+var_210]; void *
0x1800525ba  xor     edx, edx; Val
0x1800525bc  call    memset_0
0x1800525c1  cmp     word ptr [rbx+58D0h], 0Bh
0x1800525c9  mov     rcx, rbx
0x1800525cc  jnz     loc_1800527A4
0x1800525d2  mov     rax, [rbx+5610h]
0x1800525d9  lea     rdx, [rbp+190h+var_1C0]
0x1800525dd  mov     r9, [rbx+55E0h]
0x1800525e4  mov     r8, [rbx+55D0h]
0x1800525eb  mov     [rsp+290h+var_260], rax
0x1800525f0  mov     rax, [rbx+5600h]
0x1800525f7  mov     [rsp+290h+var_268], rax
0x1800525fc  mov     rax, [rbx+55F0h]
0x180052603  mov     [rsp+290h+var_270], rax
0x180052608  call    PSVAdd5
0x18005260d  mov     rax, [rbx+5618h]
0x180052614  lea     rdx, [rbp+190h+var_210]
0x180052618  mov     r9, [rbx+55E8h]
0x18005261f  mov     rcx, rbx
0x180052622  mov     r8, [rbx+55D8h]
0x180052629  mov     [rsp+290h+var_260], rax
0x18005262e  mov     rax, [rbx+5608h]
0x180052635  mov     [rsp+290h+var_268], rax
0x18005263a  mov     rax, [rbx+55F8h]
0x180052641  mov     [rsp+290h+var_270], rax
0x180052646  call    PSVAdd5
0x18005264b  cmp     dword ptr [rbx+1E8h], 0
0x180052652  jz      short loc_180052691
0x180052654  mov     r8, [rbx+55C0h]
0x18005265b  lea     r9, [rbp+190h+var_1C0]
0x18005265f  lea     rdx, [rbp+190h+var_D0]
0x180052666  mov     rcx, rbx
0x180052669  call    PStackValueAdd
0x18005266e  cmp     dword ptr [rbx+1E8h], 0
0x180052675  jz      short loc_180052691
0x180052677  mov     r8, [rbx+55C8h]
0x18005267e  lea     r9, [rbp+190h+var_210]
0x180052682  lea     rdx, [rbp+190h+var_80]
0x180052689  mov     rcx, rbx
0x18005268c  call    PStackValueAdd
0x180052691  mov     ecx, [rbp+190h+var_20C]
0x180052694  lea     rdx, [rbp+190h+var_120]
0x180052698  mov     eax, [rbp+190h+var_1BC]
0x18005269b  neg     ecx
0x18005269d  cmovs   ecx, [rbp+190h+var_20C]
0x1800526a1  neg     eax
0x1800526a3  cmovs   eax, [rbp+190h+var_1BC]
0x1800526a7  cmp     eax, ecx
0x1800526a9  mov     rcx, rbx
0x1800526ac  jle     short loc_1800526D3
0x1800526ae  mov     r8, [rbx+5620h]
0x1800526b5  call    PSVCopy
0x1800526ba  mov     r8, [rbx+65C0h]
0x1800526c1  lea     r9, [rbp+190h+var_210]
0x1800526c5  mov     rcx, rbx
0x1800526c8  lea     rdx, [rbp+190h+var_170]
0x1800526cc  call    PSVSubtract
0x1800526d1  jmp     short loc_1800526F6
0x1800526d3  mov     r8, [rbx+65C0h]
0x1800526da  lea     r9, [rbp+190h+var_1C0]
0x1800526de  call    PSVSubtract
0x1800526e3  mov     r8, [rbx+5620h]
0x1800526ea  lea     rdx, [rbp+190h+var_170]
0x1800526ee  mov     rcx, rbx
0x1800526f1  call    PSVCopy
0x1800526f6  mov     rax, [rbx+65C8h]
0x1800526fd  mov     rcx, rbx
0x180052700  mov     r9, [rbx+55E0h]
0x180052707  mov     r8, [rbx+55D8h]
0x18005270e  mov     rdx, [rbx+55D0h]
0x180052715  mov     [rsp+290h+var_220], edi
0x180052719  mov     [rsp+290h+var_228], rax
0x18005271e  lea     rax, [rbp+190h+var_170]
0x180052722  mov     [rsp+290h+var_230], rax
0x180052727  lea     rax, [rbp+190h+var_120]
0x18005272b  mov     [rsp+290h+var_238], rax
0x180052730  mov     rax, [rbx+5618h]
0x180052737  mov     [rsp+290h+var_240], rax
0x18005273c  mov     rax, [rbx+5610h]
0x180052743  mov     [rsp+290h+var_248], rax
0x180052748  mov     rax, [rbx+5608h]
0x18005274f  mov     [rsp+290h+var_250], rax
0x180052754  mov     rax, [rbx+5600h]
0x18005275b  mov     [rsp+290h+var_258], rax
0x180052760  mov     rax, [rbx+55F8h]
0x180052767  mov     [rsp+290h+var_260], rax
0x18005276c  mov     rax, [rbx+55F0h]
0x180052773  mov     [rsp+290h+var_268], rax
0x180052778  mov     rax, [rbx+55E8h]
0x18005277f  mov     [rsp+290h+var_270], rax
0x180052784  call    WriteExpandedFlexCurveTo
0x180052789  mov     rcx, [rbp+190h+var_30]
0x180052790  xor     rcx, rsp; StackCookie
0x180052793  call    __security_check_cookie
0x180052798  add     rsp, 278h
0x18005279f  pop     rdi
0x1800527a0  pop     rsi
0x1800527a1  pop     rbx
0x1800527a2  pop     rbp
0x1800527a3  retn
0x1800527a4  mov     edx, 0Eh
0x1800527a9  call    XCF_FatalErrorHandler
```
