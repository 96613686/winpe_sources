# StreamRead

- ea: `0x1800153d4`
- end: `0x1800155bf`
- name: `StreamRead`
- size: `491`
- prototype: `__int64 __usercall@<rax>(struct STREAMINDEX *@<rcx>, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000acf0`

## callees

- `0x180001460`
- `0x180014a68`
- `0x1800153d4`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall StreamRead(struct STREAMINDEX *a1, int a2)
{
  if ( a2 < *((_DWORD *)a1 + 7) || a2 >= *((_DWORD *)a1 + 8) || (unsigned int)SearchIndex(a1) == -100 )
    return 0xFFFFFFFFLL;
  else
    return 0;
}

```

## disassembly

```asm
0x1800153d4  push    rbp
0x1800153d6  push    rbx
0x1800153d7  push    rsi
0x1800153d8  push    rdi
0x1800153d9  push    r12
0x1800153db  push    r13
0x1800153dd  push    r14
0x1800153df  push    r15
0x1800153e1  mov     rbp, rsp
0x1800153e4  sub     rsp, 68h
0x1800153e8  mov     rax, cs:__security_cookie
0x1800153ef  xor     rax, rsp
0x1800153f2  mov     [rbp+var_10], rax
0x1800153f6  xor     eax, eax
0x1800153f8  mov     [rbp+var_20], r9
0x1800153fc  xorps   xmm0, xmm0
0x1800153ff  mov     r15, r9
0x180015402  mov     edi, r8d
0x180015405  mov     r12d, edx
0x180015408  mov     r13, rcx
0x18001540b  mov     [rbp+var_28], eax
0x18001540e  movups  [rbp+var_38], xmm0
0x180015412  cmp     edx, [rcx+1Ch]
0x180015415  jl      loc_18001559F
0x18001541b  cmp     edx, [rcx+20h]
0x18001541e  jge     loc_18001559F
0x180015424  lea     r9, [rbp+var_38]
0x180015428  lea     r8d, [rax+4]
0x18001542c  call    SearchIndex
0x180015431  cmp     eax, 0FFFFFF9Ch
0x180015434  jz      loc_18001559F
0x18001543a  mov     ecx, dword ptr [rbp+var_38+4]
0x18001543d  cmp     r12d, ecx
0x180015440  jl      loc_18001559B
0x180015446  add     ecx, dword ptr [rbp+var_38+8]
0x180015449  cmp     r12d, ecx
0x18001544c  jge     loc_18001559B
0x180015452  mov     ebx, [rbp+arg_20]
0x180015455  test    r15, r15
0x180015458  jnz     short loc_180015468
0x18001545a  test    ebx, ebx
0x18001545c  jnz     short loc_180015468
0x18001545e  test    edi, edi
0x180015460  mov     eax, 7FFFFFFFh
0x180015465  cmovnz  ebx, eax
0x180015468  mov     r14d, [r13+28h]
0x18001546c  mov     esi, [rbp+var_28]
0x18001546f  test    r14d, r14d
0x180015472  jz      short loc_18001549D
0x180015474  cmp     edi, 0FFFFFFFFh
0x180015477  jnz     short loc_180015487
0x180015479  cmp     ebx, esi
0x18001547b  jl      short loc_180015487
0x18001547d  mov     eax, esi
0x18001547f  mov     ebx, esi
0x180015481  cdq
0x180015482  idiv    r14d
0x180015485  jmp     short loc_180015495
0x180015487  mov     eax, ebx
0x180015489  cdq
0x18001548a  idiv    r14d
0x18001548d  test    edi, edi
0x18001548f  jle     short loc_180015495
0x180015491  cmp     edi, eax
0x180015493  jl      short loc_180015497
0x180015495  mov     edi, eax
0x180015497  imul    edi, r14d
0x18001549b  jmp     short loc_18001549F
0x18001549d  mov     edi, esi
0x18001549f  test    r15, r15
0x1800154a2  jnz     short loc_1800154AB
0x1800154a4  mov     eax, edi
0x1800154a6  jmp     loc_1800155A2
0x1800154ab  cmp     ebx, edi
0x1800154ad  jl      loc_18001559F
0x1800154b3  test    r14d, r14d
0x1800154b6  jnz     short loc_180015520
0x1800154b8  mov     edx, dword ptr [rbp+var_38+0Ch]
0x1800154bb  lea     r9, [rbp+var_18]
0x1800154bf  mov     rcx, [r13+40h]
0x1800154c3  lea     r8d, [r14+8]
0x1800154c7  mov     rax, [r13+48h]
0x1800154cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154d0  cmp     eax, 8
0x1800154d3  jnz     loc_18001559F
0x1800154d9  mov     rax, [rbp+var_18]
0x1800154dd  movzx   edx, al
0x1800154e0  shl     edx, 4
0x1800154e3  cmp     al, 41h ; 'A'
0x1800154e5  jb      short loc_1800154EF
0x1800154e7  sub     edx, 370h
0x1800154ed  jmp     short loc_1800154F5
0x1800154ef  sub     edx, 300h
0x1800154f5  shr     ax, 8
0x1800154f9  movzx   ecx, al
0x1800154fc  cmp     cl, 41h ; 'A'
0x1800154ff  sbb     eax, eax
0x180015501  and     eax, 0FFFFFFF9h
0x180015504  add     eax, 37h ; '7'
0x180015507  sub     ecx, eax
0x180015509  add     ecx, edx
0x18001550b  movzx   eax, cx
0x18001550e  cmp     eax, [r13+0]
0x180015512  jnz     short loc_180015520
0x180015514  mov     esi, dword ptr [rbp+var_18+4]
0x180015517  mov     [rbp+var_28], esi
0x18001551a  cmp     ebx, esi
0x18001551c  jl      short loc_180015522
0x18001551e  mov     edi, esi
0x180015520  mov     ebx, edi
0x180015522  xor     r15d, r15d
0x180015525  test    ebx, ebx
0x180015527  jle     short loc_180015596
0x180015529  cmp     esi, ebx
0x18001552b  mov     edi, ebx
0x18001552d  cmovl   edi, esi
0x180015530  test    edi, edi
0x180015532  jle     short loc_180015596
0x180015534  mov     edx, dword ptr [rbp+var_38+0Ch]
0x180015537  mov     r8d, edi
0x18001553a  mov     rsi, [rbp+var_20]
0x18001553e  add     edx, 8
0x180015541  mov     rcx, [r13+40h]
0x180015545  mov     r9, rsi
0x180015548  mov     rax, [r13+48h]
0x18001554c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015551  cmp     eax, edi
0x180015553  jnz     short loc_18001559F
0x180015555  add     r15d, edi
0x180015558  sub     ebx, edi
0x18001555a  test    ebx, ebx
0x18001555c  jle     short loc_180015596
0x18001555e  test    r14d, r14d
0x180015561  jz      short loc_180015596
0x180015563  mov     eax, edi
0x180015565  lea     r9, [rbp+var_38]
0x180015569  cdq
0x18001556a  mov     r8d, 4
0x180015570  idiv    r14d
0x180015573  mov     rcx, r13; struct STREAMINDEX *
0x180015576  lea     edx, [r12+rax]
0x18001557a  call    SearchIndex
0x18001557f  mov     r12d, eax
0x180015582  cmp     eax, 0FFFFFF9Ch
0x180015585  jz      short loc_180015596
0x180015587  movsxd  rcx, edi
0x18001558a  add     rsi, rcx
0x18001558d  mov     [rbp+var_20], rsi
0x180015591  mov     esi, [rbp+var_28]
0x180015594  jmp     short loc_180015529
0x180015596  mov     eax, r15d
0x180015599  jmp     short loc_1800155A2
0x18001559b  xor     eax, eax
0x18001559d  jmp     short loc_1800155A2
0x18001559f  or      eax, 0FFFFFFFFh
0x1800155a2  mov     rcx, [rbp+var_10]
0x1800155a6  xor     rcx, rsp; StackCookie
0x1800155a9  call    __security_check_cookie
0x1800155ae  add     rsp, 68h
0x1800155b2  pop     r15
0x1800155b4  pop     r14
0x1800155b6  pop     r13
0x1800155b8  pop     r12
0x1800155ba  pop     rdi
0x1800155bb  pop     rsi
0x1800155bc  pop     rbx
0x1800155bd  pop     rbp
0x1800155be  retn
```
