# WriteExpandedFlexCurveTo

- ea: `0x1800520e8`
- end: `0x180052602`
- name: `WriteExpandedFlexCurveTo`
- size: `1306`
- prototype: `__int64 __fastcall(__int64, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, __int64, __int64, __int64, __int64, __int64, __int64, __int64, unsigned int)`
- caller_count: `4`
- callee_count: `12`
- tags: ``

## callers

- `0x180053df8`
- `0x180053eb8`
- `0x180054138`
- `0x18005421c`

## callees

- `0x180001f20`
- `0x180002938`
- `0x180050c5c`
- `0x180050d8c`
- `0x180050dd4`
- `0x180050ea8`
- `0x180050f68`
- `0x180051880`
- `0x1800520e8`
- `0x180052758`
- `0x180054864`
- `0x1800548bc`

## pseudocode

```c
__int64 __fastcall WriteExpandedFlexCurveTo(
        __int64 a1,
        unsigned int *a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned int *a6,
        unsigned int *a7,
        _DWORD *a8,
        _DWORD *a9,
        _DWORD *a10,
        _DWORD *a11,
        _DWORD *a12,
        _DWORD *a13,
        _DWORD *a14,
        unsigned int a15)
{
  __int64 v19; // rax
  unsigned int *v20; // r10
  unsigned int v21; // ecx
  unsigned int v22; // r8d
  int v23; // ecx
  unsigned int v24; // r9d
  int v25; // r8d
  int v26; // edx
  int v27; // eax
  unsigned int *v28; // r8
  _DWORD v30[2]; // [rsp+88h] [rbp-78h] BYREF
  _DWORD *v31; // [rsp+90h] [rbp-70h]
  _DWORD *v32; // [rsp+98h] [rbp-68h]
  unsigned int v33[20]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v34[20]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int v35[20]; // [rsp+140h] [rbp+40h] BYREF
  unsigned int v36[20]; // [rsp+190h] [rbp+90h] BYREF
  unsigned int v37[20]; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned int v38[20]; // [rsp+230h] [rbp+130h] BYREF
  unsigned int v39[20]; // [rsp+280h] [rbp+180h] BYREF
  unsigned int v40[20]; // [rsp+2D0h] [rbp+1D0h] BYREF

  v32 = a14;
  v31 = a4;
  memset_0(v37, 0, 0x44u);
  memset_0(v38, 0, 0x44u);
  memset_0(v34, 0, 0x44u);
  memset_0(v33, 0, 0x44u);
  memset_0(v40, 0, 0x44u);
  memset_0(v39, 0, 0x44u);
  memset_0(v35, 0, 0x44u);
  memset_0(v36, 0, 0x44u);
  PSVAdd7(
    a1,
    v37,
    *(_QWORD *)(a1 + 21952),
    (__int64)a2,
    (__int64)a4,
    (__int64)a6,
    (__int64)a8,
    (__int64)a10,
    (__int64)a12);
  PSVAdd7(
    a1,
    v38,
    *(_QWORD *)(a1 + 21960),
    (__int64)a3,
    (__int64)a5,
    (__int64)a7,
    (__int64)a9,
    (__int64)a11,
    (__int64)a13);
  v19 = *(_QWORD *)(a1 + 21960);
  v20 = *(unsigned int **)(a1 + 21952);
  v21 = v38[1];
  v22 = v37[1];
  *(_DWORD *)(a1 + 21936) = 1;
  v23 = v21 - *(_DWORD *)(v19 + 4);
  v24 = v20[1];
  v25 = v22 - v24;
  v26 = -v23;
  if ( v23 > 0 )
    v26 = v23;
  v27 = -v25;
  if ( v25 > 0 )
    v27 = v25;
  if ( v27 <= v26 )
  {
    PSVAdd7(a1, v34, (__int64)v20, (__int64)a2, (__int64)a4, (__int64)a6, (__int64)a8, (__int64)a10, (__int64)a12);
    v28 = *(unsigned int **)(a1 + 21960);
    if ( *(_DWORD *)(a1 + 488) )
    {
      PStackValueAdd4(a1, v33, v28, a3, a5, a7);
    }
    else
    {
      v33[1] = a3[1] + a5[1] + a7[1] + v28[1];
      v33[0] = 0;
    }
  }
  else
  {
    if ( *(_DWORD *)(a1 + 488) )
      PStackValueAdd4(a1, v34, v20, a2, a4, a6);
    else
      v34[1] = v24 + a2[1] + a4[1] + a6[1];
    PSVAdd7(
      a1,
      v33,
      *(_QWORD *)(a1 + 21960),
      (__int64)a3,
      (__int64)a5,
      (__int64)a7,
      (__int64)a9,
      (__int64)a11,
      (__int64)a13);
  }
  PSVSubtract(a1, v40, v34, *(unsigned int **)(a1 + 21952));
  PSVSubtract(a1, v39, v33, *(unsigned int **)(a1 + 21960));
  PSVSubtract(a1, v35, *(unsigned int **)(a1 + 21952), v34);
  PSVCopy(a1, v36, a2);
  PStackValueAdd(a1, a2, v36, v35);
  PSVSubtract(a1, v35, *(unsigned int **)(a1 + 21960), v33);
  PSVCopy(a1, v36, a3);
  PStackValueAdd(a1, a3, v36, v35);
  StateChange(a1, 2, 1, 0, 0, a15);
  v30[0] = 0;
  v30[1] = 0x10000;
  XC_WriteT1PStackValue(a1, v30, a15);
  XC_WriteT1OpCode(a1, 10, a15);
  WriteFlexCoordinate(a1, v40, v39, a15);
  WriteFlexCoordinate(a1, a2, a3, a15);
  WriteFlexCoordinate(a1, v31, a5, a15);
  WriteFlexCoordinate(a1, a6, a7, a15);
  WriteFlexCoordinate(a1, a8, a9, a15);
  WriteFlexCoordinate(a1, a10, a11, a15);
  WriteFlexCoordinate(a1, a12, a13, a15);
  XC_WriteT1PStackValue(a1, v32, a15);
  XC_WriteT1PStackValue(a1, v37, a15);
  XC_WriteT1PStackValue(a1, v38, a15);
  XC_WriteT1PStackValue(a1, *(_DWORD **)(a1 + 26048), a15);
  XC_WriteT1OpCode(a1, 10, a15);
  PSVCopy(a1, *(unsigned int **)(a1 + 21952), v37);
  return PSVCopy(a1, *(unsigned int **)(a1 + 21960), v38);
}

```

## disassembly

```asm
0x1800520e8  push    rbp
0x1800520ea  push    rbx
0x1800520eb  push    rsi
0x1800520ec  push    rdi
0x1800520ed  push    r12
0x1800520ef  push    r13
0x1800520f1  push    r14
0x1800520f3  push    r15
0x1800520f5  lea     rbp, [rsp-238h]
0x1800520fd  sub     rsp, 338h
0x180052104  mov     rax, cs:__security_cookie
0x18005210b  xor     rax, rsp
0x18005210e  mov     [rbp+270h+var_50], rax
0x180052115  mov     rax, [rbp+270h+arg_38]
0x18005211c  mov     r15, rdx
0x18005211f  mov     rsi, [rbp+270h+arg_28]
0x180052126  xor     edx, edx; Val
0x180052128  mov     r12, [rbp+270h+arg_20]
0x18005212f  mov     rbx, r9
0x180052132  mov     r13, [rbp+270h+arg_30]
0x180052139  mov     r14, r8
0x18005213c  mov     [rsp+370h+var_310], rax
0x180052141  mov     rdi, rcx
0x180052144  mov     rax, [rbp+270h+arg_40]
0x18005214b  lea     r8d, [rdx+44h]; Size
0x18005214f  mov     [rsp+370h+var_318], rax
0x180052154  lea     rcx, [rbp+270h+var_190]; void *
0x18005215b  mov     rax, [rbp+270h+arg_48]
0x180052162  mov     [rsp+370h+var_300], rax
0x180052167  mov     rax, [rbp+270h+arg_50]
0x18005216e  mov     [rsp+370h+var_308], rax
0x180052173  mov     rax, [rbp+270h+arg_58]
0x18005217a  mov     [rbp+270h+var_2F0], rax
0x18005217e  mov     rax, [rbp+270h+arg_60]
0x180052185  mov     [rsp+370h+var_2F8], rax
0x18005218a  mov     rax, [rbp+270h+arg_68]
0x180052191  mov     [rbp+270h+var_2D8], rax
0x180052195  mov     [rbp+270h+var_2E0], rbx
0x180052199  mov     [rsp+370h+var_320], rsi
0x18005219e  call    memset_0
0x1800521a3  xor     edx, edx; Val
0x1800521a5  lea     rcx, [rbp+270h+var_140]; void *
0x1800521ac  lea     r8d, [rdx+44h]; Size
0x1800521b0  call    memset_0
0x1800521b5  xor     edx, edx; Val
0x1800521b7  lea     rcx, [rbp+270h+var_280]; void *
0x1800521bb  lea     r8d, [rdx+44h]; Size
0x1800521bf  call    memset_0
0x1800521c4  xor     edx, edx; Val
0x1800521c6  lea     rcx, [rbp+270h+var_2D0]; void *
0x1800521ca  lea     r8d, [rdx+44h]; Size
0x1800521ce  call    memset_0
0x1800521d3  xor     edx, edx; Val
0x1800521d5  lea     rcx, [rbp+270h+var_A0]; void *
0x1800521dc  lea     r8d, [rdx+44h]; Size
0x1800521e0  call    memset_0
0x1800521e5  xor     edx, edx; Val
0x1800521e7  lea     rcx, [rbp+270h+var_F0]; void *
0x1800521ee  lea     r8d, [rdx+44h]; Size
0x1800521f2  call    memset_0
0x1800521f7  xor     edx, edx; Val
0x1800521f9  lea     rcx, [rbp+270h+var_230]; void *
0x1800521fd  lea     r8d, [rdx+44h]; Size
0x180052201  call    memset_0
0x180052206  xor     edx, edx; Val
0x180052208  lea     rcx, [rbp+270h+var_1E0]; void *
0x18005220f  lea     r8d, [rdx+44h]; Size
0x180052213  call    memset_0
0x180052218  mov     rax, [rbp+270h+var_2F0]
0x18005221c  lea     rdx, [rbp+270h+var_190]
0x180052223  mov     r8, [rdi+55C0h]
0x18005222a  mov     r9, r15
0x18005222d  mov     [rsp+370h+var_330], rax
0x180052232  mov     rcx, rdi
0x180052235  mov     rax, [rsp+370h+var_300]
0x18005223a  mov     [rsp+370h+var_338], rax
0x18005223f  mov     rax, [rsp+370h+var_310]
0x180052244  mov     [rsp+370h+var_340], rax
0x180052249  mov     [rsp+370h+var_348], rsi
0x18005224e  mov     [rsp+370h+var_350], rbx
0x180052253  call    PSVAdd7
0x180052258  mov     rax, [rsp+370h+var_2F8]
0x18005225d  lea     rdx, [rbp+270h+var_140]
0x180052264  mov     r8, [rdi+55C8h]
0x18005226b  mov     r9, r14
0x18005226e  mov     [rsp+370h+var_330], rax
0x180052273  mov     rcx, rdi
0x180052276  mov     rax, [rsp+370h+var_308]
0x18005227b  mov     [rsp+370h+var_338], rax
0x180052280  mov     rax, [rsp+370h+var_318]
0x180052285  mov     [rsp+370h+var_340], rax
0x18005228a  mov     [rsp+370h+var_348], r13
0x18005228f  mov     [rsp+370h+var_350], r12
0x180052294  call    PSVAdd7
0x180052299  mov     rax, [rdi+55C8h]
0x1800522a0  mov     r10, [rdi+55C0h]
0x1800522a7  mov     ecx, [rbp+270h+var_13C]
0x1800522ad  mov     r8d, [rbp+270h+var_18C]
0x1800522b4  mov     dword ptr [rdi+55B0h], 1
0x1800522be  sub     ecx, [rax+4]
0x1800522c1  mov     r9d, [r10+4]
0x1800522c5  mov     edx, ecx
0x1800522c7  sub     r8d, r9d
0x1800522ca  neg     edx
0x1800522cc  mov     eax, r8d
0x1800522cf  cmovs   edx, ecx
0x1800522d2  neg     eax
0x1800522d4  cmovs   eax, r8d
0x1800522d8  cmp     eax, edx
0x1800522da  jle     short loc_180052359
0x1800522dc  mov     rax, [rsp+370h+var_320]
0x1800522e1  xor     esi, esi
0x1800522e3  cmp     [rdi+1E8h], esi
0x1800522e9  jnz     short loc_1800522FD
0x1800522eb  mov     eax, [rax+4]
0x1800522ee  add     eax, [rbx+4]
0x1800522f1  add     eax, [r15+4]
0x1800522f5  add     eax, r9d
0x1800522f8  mov     [rbp+270h+var_27C], eax
0x1800522fb  jmp     short loc_180052319
0x1800522fd  mov     [rsp+370h+var_348], rax
0x180052302  lea     rdx, [rbp+270h+var_280]
0x180052306  mov     r9, r15
0x180052309  mov     [rsp+370h+var_350], rbx
0x18005230e  mov     r8, r10
0x180052311  mov     rcx, rdi
0x180052314  call    PStackValueAdd4
0x180052319  mov     rax, [rsp+370h+var_2F8]
0x18005231e  lea     rdx, [rbp+270h+var_2D0]
0x180052322  mov     r8, [rdi+55C8h]
0x180052329  mov     r9, r14
0x18005232c  mov     [rsp+370h+var_330], rax
0x180052331  mov     rcx, rdi
0x180052334  mov     rax, [rsp+370h+var_308]
0x180052339  mov     [rsp+370h+var_338], rax
0x18005233e  mov     rax, [rsp+370h+var_318]
0x180052343  mov     [rsp+370h+var_340], rax
0x180052348  mov     [rsp+370h+var_348], r13
0x18005234d  mov     [rsp+370h+var_350], r12
0x180052352  call    PSVAdd7
0x180052357  jmp     short loc_1800523D5
0x180052359  mov     rax, [rbp+270h+var_2F0]
0x18005235d  lea     rdx, [rbp+270h+var_280]
0x180052361  mov     [rsp+370h+var_330], rax
0x180052366  mov     r9, r15
0x180052369  mov     rax, [rsp+370h+var_300]
0x18005236e  mov     r8, r10
0x180052371  mov     [rsp+370h+var_338], rax
0x180052376  mov     rcx, rdi
0x180052379  mov     rax, [rsp+370h+var_310]
0x18005237e  mov     [rsp+370h+var_340], rax
0x180052383  mov     [rsp+370h+var_348], rsi
0x180052388  mov     [rsp+370h+var_350], rbx
0x18005238d  call    PSVAdd7
0x180052392  mov     r8, [rdi+55C8h]
0x180052399  xor     esi, esi
0x18005239b  cmp     [rdi+1E8h], esi
0x1800523a1  jnz     short loc_1800523BC
0x1800523a3  mov     eax, [r8+4]
0x1800523a7  add     eax, [r13+4]
0x1800523ab  add     eax, [r12+4]
0x1800523b0  add     eax, [r14+4]
0x1800523b4  mov     [rbp+270h+var_2CC], eax
0x1800523b7  mov     [rbp+270h+var_2D0], esi
0x1800523ba  jmp     short loc_1800523D5
0x1800523bc  mov     [rsp+370h+var_348], r13
0x1800523c1  lea     rdx, [rbp+270h+var_2D0]
0x1800523c5  mov     r9, r14
0x1800523c8  mov     [rsp+370h+var_350], r12
0x1800523cd  mov     rcx, rdi
0x1800523d0  call    PStackValueAdd4
0x1800523d5  mov     r9, [rdi+55C0h]
0x1800523dc  lea     r8, [rbp+270h+var_280]
0x1800523e0  lea     rdx, [rbp+270h+var_A0]
0x1800523e7  mov     rcx, rdi
0x1800523ea  call    PSVSubtract
0x1800523ef  mov     r9, [rdi+55C8h]
0x1800523f6  lea     r8, [rbp+270h+var_2D0]
0x1800523fa  mov     rcx, rdi
0x1800523fd  lea     rdx, [rbp+270h+var_F0]
0x180052404  call    PSVSubtract
0x180052409  mov     r8, [rdi+55C0h]
0x180052410  lea     r9, [rbp+270h+var_280]
0x180052414  mov     rcx, rdi
0x180052417  lea     rdx, [rbp+270h+var_230]
0x18005241b  call    PSVSubtract
0x180052420  mov     r8, r15
0x180052423  lea     rdx, [rbp+270h+var_1E0]
0x18005242a  mov     rcx, rdi
0x18005242d  call    PSVCopy
0x180052432  lea     r9, [rbp+270h+var_230]
0x180052436  mov     rcx, rdi
0x180052439  lea     r8, [rbp+270h+var_1E0]
0x180052440  mov     rdx, r15
0x180052443  call    PStackValueAdd
0x180052448  mov     r8, [rdi+55C8h]
0x18005244f  lea     r9, [rbp+270h+var_2D0]
0x180052453  mov     rcx, rdi
0x180052456  lea     rdx, [rbp+270h+var_230]
0x18005245a  call    PSVSubtract
0x18005245f  mov     r8, r14
0x180052462  lea     rdx, [rbp+270h+var_1E0]
0x180052469  mov     rcx, rdi
0x18005246c  call    PSVCopy
0x180052471  lea     r9, [rbp+270h+var_230]
0x180052475  mov     rcx, rdi
0x180052478  lea     r8, [rbp+270h+var_1E0]
0x18005247f  mov     rdx, r14
0x180052482  call    PStackValueAdd
0x180052487  mov     ebx, [rbp+270h+arg_70]
0x18005248d  xor     r9d, r9d
0x180052490  mov     dword ptr [rsp+370h+var_348], ebx
0x180052494  mov     rcx, rdi
0x180052497  mov     dword ptr [rsp+370h+var_350], esi
0x18005249b  lea     edx, [r9+2]
0x18005249f  lea     r8d, [r9+1]
0x1800524a3  call    StateChange
0x1800524a8  mov     r8d, ebx
0x1800524ab  mov     [rbp+270h+var_2E8], esi
0x1800524ae  lea     rdx, [rbp+270h+var_2E8]
0x1800524b2  mov     [rbp+270h+var_2E4], 10000h
0x1800524b9  mov     rcx, rdi
0x1800524bc  call    XC_WriteT1PStackValue
0x1800524c1  mov     esi, 0Ah
0x1800524c6  mov     r8d, ebx
0x1800524c9  mov     edx, esi
0x1800524cb  mov     rcx, rdi
0x1800524ce  call    XC_WriteT1OpCode
0x1800524d3  mov     r9d, ebx
0x1800524d6  lea     r8, [rbp+270h+var_F0]
0x1800524dd  lea     rdx, [rbp+270h+var_A0]
0x1800524e4  mov     rcx, rdi
0x1800524e7  call    WriteFlexCoordinate
0x1800524ec  mov     r9d, ebx
0x1800524ef  mov     r8, r14
0x1800524f2  mov     rdx, r15
0x1800524f5  mov     rcx, rdi
0x1800524f8  call    WriteFlexCoordinate
0x1800524fd  mov     rdx, [rbp+270h+var_2E0]
0x180052501  mov     r9d, ebx
0x180052504  mov     r8, r12
0x180052507  mov     rcx, rdi
0x18005250a  call    WriteFlexCoordinate
0x18005250f  mov     rdx, [rsp+370h+var_320]
0x180052514  mov     r9d, ebx
0x180052517  mov     r8, r13
0x18005251a  mov     rcx, rdi
0x18005251d  call    WriteFlexCoordinate
0x180052522  mov     r8, [rsp+370h+var_318]
0x180052527  mov     r9d, ebx
0x18005252a  mov     rdx, [rsp+370h+var_310]
0x18005252f  mov     rcx, rdi
0x180052532  call    WriteFlexCoordinate
0x180052537  mov     r8, [rsp+370h+var_308]
0x18005253c  mov     r9d, ebx
0x18005253f  mov     rdx, [rsp+370h+var_300]
0x180052544  mov     rcx, rdi
0x180052547  call    WriteFlexCoordinate
0x18005254c  mov     r8, [rsp+370h+var_2F8]
0x180052551  mov     r9d, ebx
0x180052554  mov     rdx, [rbp+270h+var_2F0]
0x180052558  mov     rcx, rdi
0x18005255b  call    WriteFlexCoordinate
0x180052560  mov     rdx, [rbp+270h+var_2D8]
0x180052564  mov     r8d, ebx
0x180052567  mov     rcx, rdi
0x18005256a  call    XC_WriteT1PStackValue
0x18005256f  mov     r8d, ebx
0x180052572  lea     rdx, [rbp+270h+var_190]
0x180052579  mov     rcx, rdi
0x18005257c  call    XC_WriteT1PStackValue
0x180052581  mov     r8d, ebx
0x180052584  lea     rdx, [rbp+270h+var_140]
0x18005258b  mov     rcx, rdi
0x18005258e  call    XC_WriteT1PStackValue
0x180052593  mov     rdx, [rdi+65C0h]
0x18005259a  mov     r8d, ebx
0x18005259d  mov     rcx, rdi
0x1800525a0  call    XC_WriteT1PStackValue
0x1800525a5  mov     edx, esi
0x1800525a7  mov     r8d, ebx
0x1800525aa  mov     rcx, rdi
0x1800525ad  call    XC_WriteT1OpCode
0x1800525b2  mov     rdx, [rdi+55C0h]
0x1800525b9  lea     r8, [rbp+270h+var_190]
0x1800525c0  mov     rcx, rdi
0x1800525c3  call    PSVCopy
0x1800525c8  mov     rdx, [rdi+55C8h]
0x1800525cf  lea     r8, [rbp+270h+var_140]
0x1800525d6  mov     rcx, rdi
0x1800525d9  call    PSVCopy
0x1800525de  mov     rcx, [rbp+270h+var_50]
0x1800525e5  xor     rcx, rsp; StackCookie
0x1800525e8  call    __security_check_cookie
0x1800525ed  add     rsp, 338h
0x1800525f4  pop     r15
0x1800525f6  pop     r14
0x1800525f8  pop     r13
0x1800525fa  pop     r12
0x1800525fc  pop     rdi
  ... truncated ...
```
