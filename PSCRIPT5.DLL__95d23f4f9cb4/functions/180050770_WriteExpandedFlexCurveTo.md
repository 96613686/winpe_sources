# WriteExpandedFlexCurveTo

- ea: `0x180050770`
- end: `0x180050c89`
- name: `WriteExpandedFlexCurveTo`
- size: `1305`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: ``

## callers

- `0x180052478`
- `0x180052538`
- `0x1800527b8`
- `0x180052898`

## callees

- `0x180001ee0`
- `0x1800028d8`
- `0x18004f2f0`
- `0x18004f41c`
- `0x18004f464`
- `0x18004f538`
- `0x18004f5f8`
- `0x18004ff08`
- `0x180050770`
- `0x180050de0`
- `0x180052ed8`
- `0x180052f30`

## pseudocode

```c
__int64 __fastcall WriteExpandedFlexCurveTo(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        unsigned int a15)
{
  __int64 v19; // rax
  __int64 v20; // r10
  int v21; // ecx
  int v22; // r8d
  int v23; // ecx
  int v24; // r9d
  int v25; // r8d
  int v26; // edx
  int v27; // eax
  __int64 v28; // r8
  _DWORD v30[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v31; // [rsp+90h] [rbp-70h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  _DWORD v33[20]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v34[4]; // [rsp+F0h] [rbp-10h] BYREF
  int v35; // [rsp+F4h] [rbp-Ch]
  _BYTE v36[80]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v37[80]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v38[4]; // [rsp+1E0h] [rbp+E0h] BYREF
  int v39; // [rsp+1E4h] [rbp+E4h]
  _BYTE v40[4]; // [rsp+230h] [rbp+130h] BYREF
  int v41; // [rsp+234h] [rbp+134h]
  _BYTE v42[80]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v43[80]; // [rsp+2D0h] [rbp+1D0h] BYREF

  v32 = a14;
  v31 = a4;
  memset_0(v38, 0, 0x44u);
  memset_0(v40, 0, 0x44u);
  memset_0(v34, 0, 0x44u);
  memset_0(v33, 0, 0x44u);
  memset_0(v43, 0, 0x44u);
  memset_0(v42, 0, 0x44u);
  memset_0(v36, 0, 0x44u);
  memset_0(v37, 0, 0x44u);
  PSVAdd7(a1, (unsigned int)v38, *(_QWORD *)(a1 + 21952), a2, a4, a6, a8, a10, a12);
  PSVAdd7(a1, (unsigned int)v40, *(_QWORD *)(a1 + 21960), a3, a5, a7, a9, a11, a13);
  v19 = *(_QWORD *)(a1 + 21960);
  v20 = *(_QWORD *)(a1 + 21952);
  v21 = v41;
  v22 = v39;
  *(_DWORD *)(a1 + 21936) = 1;
  v23 = v21 - *(_DWORD *)(v19 + 4);
  v24 = *(_DWORD *)(v20 + 4);
  v25 = v22 - v24;
  v26 = -v23;
  if ( v23 > 0 )
    v26 = v23;
  v27 = -v25;
  if ( v25 > 0 )
    v27 = v25;
  if ( v27 <= v26 )
  {
    PSVAdd7(a1, (unsigned int)v34, v20, a2, a4, a6, a8, a10, a12);
    v28 = *(_QWORD *)(a1 + 21960);
    if ( *(_DWORD *)(a1 + 488) )
    {
      PStackValueAdd4(a1, (unsigned int)v33, v28, a3, a5, a7);
    }
    else
    {
      v33[1] = *(_DWORD *)(a3 + 4) + *(_DWORD *)(a5 + 4) + *(_DWORD *)(a7 + 4) + *(_DWORD *)(v28 + 4);
      v33[0] = 0;
    }
  }
  else
  {
    if ( *(_DWORD *)(a1 + 488) )
      PStackValueAdd4(a1, (unsigned int)v34, v20, a2, a4, a6);
    else
      v35 = v24 + *(_DWORD *)(a2 + 4) + *(_DWORD *)(a4 + 4) + *(_DWORD *)(a6 + 4);
    PSVAdd7(a1, (unsigned int)v33, *(_QWORD *)(a1 + 21960), a3, a5, a7, a9, a11, a13);
  }
  PSVSubtract(a1, v43, v34, *(_QWORD *)(a1 + 21952));
  PSVSubtract(a1, v42, v33, *(_QWORD *)(a1 + 21960));
  PSVSubtract(a1, v36, *(_QWORD *)(a1 + 21952), v34);
  PSVCopy(a1, v37, a2);
  PStackValueAdd(a1, a2, v37, v36);
  PSVSubtract(a1, v36, *(_QWORD *)(a1 + 21960), v33);
  PSVCopy(a1, v37, a3);
  PStackValueAdd(a1, a3, v37, v36);
  StateChange(a1, 2, 1, 0, 0, a15);
  v30[0] = 0;
  v30[1] = 0x10000;
  XC_WriteT1PStackValue(a1, v30, a15);
  XC_WriteT1OpCode(a1, 10, a15);
  WriteFlexCoordinate(a1, v43, v42, a15);
  WriteFlexCoordinate(a1, a2, a3, a15);
  WriteFlexCoordinate(a1, v31, a5, a15);
  WriteFlexCoordinate(a1, a6, a7, a15);
  WriteFlexCoordinate(a1, a8, a9, a15);
  WriteFlexCoordinate(a1, a10, a11, a15);
  WriteFlexCoordinate(a1, a12, a13, a15);
  XC_WriteT1PStackValue(a1, v32, a15);
  XC_WriteT1PStackValue(a1, v38, a15);
  XC_WriteT1PStackValue(a1, v40, a15);
  XC_WriteT1PStackValue(a1, *(_QWORD *)(a1 + 26048), a15);
  XC_WriteT1OpCode(a1, 10, a15);
  PSVCopy(a1, *(_QWORD *)(a1 + 21952), v38);
  return PSVCopy(a1, *(_QWORD *)(a1 + 21960), v40);
}

```

## disassembly

```asm
0x180050770  push    rbp
0x180050772  push    rbx
0x180050773  push    rsi
0x180050774  push    rdi
0x180050775  push    r12
0x180050777  push    r13
0x180050779  push    r14
0x18005077b  push    r15
0x18005077d  lea     rbp, [rsp-238h]
0x180050785  sub     rsp, 338h
0x18005078c  mov     rax, cs:__security_cookie
0x180050793  xor     rax, rsp
0x180050796  mov     [rbp+270h+var_50], rax
0x18005079d  mov     rax, [rbp+270h+arg_38]
0x1800507a4  mov     r15, rdx
0x1800507a7  mov     rsi, [rbp+270h+arg_28]
0x1800507ae  xor     edx, edx; Val
0x1800507b0  mov     r12, [rbp+270h+arg_20]
0x1800507b7  mov     rbx, r9
0x1800507ba  mov     r13, [rbp+270h+arg_30]
0x1800507c1  mov     r14, r8
0x1800507c4  mov     [rsp+370h+var_310], rax
0x1800507c9  mov     rdi, rcx
0x1800507cc  mov     rax, [rbp+270h+arg_40]
0x1800507d3  lea     r8d, [rdx+44h]; Size
0x1800507d7  mov     [rsp+370h+var_318], rax
0x1800507dc  lea     rcx, [rbp+270h+var_190]; void *
0x1800507e3  mov     rax, [rbp+270h+arg_48]
0x1800507ea  mov     [rsp+370h+var_300], rax
0x1800507ef  mov     rax, [rbp+270h+arg_50]
0x1800507f6  mov     [rsp+370h+var_308], rax
0x1800507fb  mov     rax, [rbp+270h+arg_58]
0x180050802  mov     [rbp+270h+var_2F0], rax
0x180050806  mov     rax, [rbp+270h+arg_60]
0x18005080d  mov     [rsp+370h+var_2F8], rax
0x180050812  mov     rax, [rbp+270h+arg_68]
0x180050819  mov     [rbp+270h+var_2D8], rax
0x18005081d  mov     [rbp+270h+var_2E0], rbx
0x180050821  mov     [rsp+370h+var_320], rsi
0x180050826  call    memset_0
0x18005082b  xor     edx, edx; Val
0x18005082d  lea     rcx, [rbp+270h+var_140]; void *
0x180050834  lea     r8d, [rdx+44h]; Size
0x180050838  call    memset_0
0x18005083d  xor     edx, edx; Val
0x18005083f  lea     rcx, [rbp+270h+var_280]; void *
0x180050843  lea     r8d, [rdx+44h]; Size
0x180050847  call    memset_0
0x18005084c  xor     edx, edx; Val
0x18005084e  lea     rcx, [rbp+270h+var_2D0]; void *
0x180050852  lea     r8d, [rdx+44h]; Size
0x180050856  call    memset_0
0x18005085b  xor     edx, edx; Val
0x18005085d  lea     rcx, [rbp+270h+var_A0]; void *
0x180050864  lea     r8d, [rdx+44h]; Size
0x180050868  call    memset_0
0x18005086d  xor     edx, edx; Val
0x18005086f  lea     rcx, [rbp+270h+var_F0]; void *
0x180050876  lea     r8d, [rdx+44h]; Size
0x18005087a  call    memset_0
0x18005087f  xor     edx, edx; Val
0x180050881  lea     rcx, [rbp+270h+var_230]; void *
0x180050885  lea     r8d, [rdx+44h]; Size
0x180050889  call    memset_0
0x18005088e  xor     edx, edx; Val
0x180050890  lea     rcx, [rbp+270h+var_1E0]; void *
0x180050897  lea     r8d, [rdx+44h]; Size
0x18005089b  call    memset_0
0x1800508a0  mov     rax, [rbp+270h+var_2F0]
0x1800508a4  lea     rdx, [rbp+270h+var_190]
0x1800508ab  mov     r8, [rdi+55C0h]
0x1800508b2  mov     r9, r15
0x1800508b5  mov     [rsp+370h+var_330], rax
0x1800508ba  mov     rcx, rdi
0x1800508bd  mov     rax, [rsp+370h+var_300]
0x1800508c2  mov     [rsp+370h+var_338], rax
0x1800508c7  mov     rax, [rsp+370h+var_310]
0x1800508cc  mov     [rsp+370h+var_340], rax
0x1800508d1  mov     [rsp+370h+var_348], rsi
0x1800508d6  mov     [rsp+370h+var_350], rbx
0x1800508db  call    PSVAdd7
0x1800508e0  mov     rax, [rsp+370h+var_2F8]
0x1800508e5  lea     rdx, [rbp+270h+var_140]
0x1800508ec  mov     r8, [rdi+55C8h]
0x1800508f3  mov     r9, r14
0x1800508f6  mov     [rsp+370h+var_330], rax
0x1800508fb  mov     rcx, rdi
0x1800508fe  mov     rax, [rsp+370h+var_308]
0x180050903  mov     [rsp+370h+var_338], rax
0x180050908  mov     rax, [rsp+370h+var_318]
0x18005090d  mov     [rsp+370h+var_340], rax
0x180050912  mov     [rsp+370h+var_348], r13
0x180050917  mov     [rsp+370h+var_350], r12
0x18005091c  call    PSVAdd7
0x180050921  mov     rax, [rdi+55C8h]
0x180050928  mov     r10, [rdi+55C0h]
0x18005092f  mov     ecx, [rbp+270h+var_13C]
0x180050935  mov     r8d, [rbp+270h+var_18C]
0x18005093c  mov     dword ptr [rdi+55B0h], 1
0x180050946  sub     ecx, [rax+4]
0x180050949  mov     r9d, [r10+4]
0x18005094d  mov     edx, ecx
0x18005094f  sub     r8d, r9d
0x180050952  neg     edx
0x180050954  mov     eax, r8d
0x180050957  cmovs   edx, ecx
0x18005095a  neg     eax
0x18005095c  cmovs   eax, r8d
0x180050960  cmp     eax, edx
0x180050962  jle     short loc_1800509E1
0x180050964  mov     rax, [rsp+370h+var_320]
0x180050969  xor     esi, esi
0x18005096b  cmp     [rdi+1E8h], esi
0x180050971  jnz     short loc_180050985
0x180050973  mov     eax, [rax+4]
0x180050976  add     eax, [rbx+4]
0x180050979  add     eax, [r15+4]
0x18005097d  add     eax, r9d
0x180050980  mov     [rbp+270h+var_27C], eax
0x180050983  jmp     short loc_1800509A1
0x180050985  mov     [rsp+370h+var_348], rax
0x18005098a  lea     rdx, [rbp+270h+var_280]
0x18005098e  mov     r9, r15
0x180050991  mov     [rsp+370h+var_350], rbx
0x180050996  mov     r8, r10
0x180050999  mov     rcx, rdi
0x18005099c  call    PStackValueAdd4
0x1800509a1  mov     rax, [rsp+370h+var_2F8]
0x1800509a6  lea     rdx, [rbp+270h+var_2D0]
0x1800509aa  mov     r8, [rdi+55C8h]
0x1800509b1  mov     r9, r14
0x1800509b4  mov     [rsp+370h+var_330], rax
0x1800509b9  mov     rcx, rdi
0x1800509bc  mov     rax, [rsp+370h+var_308]
0x1800509c1  mov     [rsp+370h+var_338], rax
0x1800509c6  mov     rax, [rsp+370h+var_318]
0x1800509cb  mov     [rsp+370h+var_340], rax
0x1800509d0  mov     [rsp+370h+var_348], r13
0x1800509d5  mov     [rsp+370h+var_350], r12
0x1800509da  call    PSVAdd7
0x1800509df  jmp     short loc_180050A5D
0x1800509e1  mov     rax, [rbp+270h+var_2F0]
0x1800509e5  lea     rdx, [rbp+270h+var_280]
0x1800509e9  mov     [rsp+370h+var_330], rax
0x1800509ee  mov     r9, r15
0x1800509f1  mov     rax, [rsp+370h+var_300]
0x1800509f6  mov     r8, r10
0x1800509f9  mov     [rsp+370h+var_338], rax
0x1800509fe  mov     rcx, rdi
0x180050a01  mov     rax, [rsp+370h+var_310]
0x180050a06  mov     [rsp+370h+var_340], rax
0x180050a0b  mov     [rsp+370h+var_348], rsi
0x180050a10  mov     [rsp+370h+var_350], rbx
0x180050a15  call    PSVAdd7
0x180050a1a  mov     r8, [rdi+55C8h]
0x180050a21  xor     esi, esi
0x180050a23  cmp     [rdi+1E8h], esi
0x180050a29  jnz     short loc_180050A44
0x180050a2b  mov     eax, [r8+4]
0x180050a2f  add     eax, [r13+4]
0x180050a33  add     eax, [r12+4]
0x180050a38  add     eax, [r14+4]
0x180050a3c  mov     [rbp+270h+var_2CC], eax
0x180050a3f  mov     [rbp+270h+var_2D0], esi
0x180050a42  jmp     short loc_180050A5D
0x180050a44  mov     [rsp+370h+var_348], r13
0x180050a49  lea     rdx, [rbp+270h+var_2D0]
0x180050a4d  mov     r9, r14
0x180050a50  mov     [rsp+370h+var_350], r12
0x180050a55  mov     rcx, rdi
0x180050a58  call    PStackValueAdd4
0x180050a5d  mov     r9, [rdi+55C0h]
0x180050a64  lea     r8, [rbp+270h+var_280]
0x180050a68  lea     rdx, [rbp+270h+var_A0]
0x180050a6f  mov     rcx, rdi
0x180050a72  call    PSVSubtract
0x180050a77  mov     r9, [rdi+55C8h]
0x180050a7e  lea     r8, [rbp+270h+var_2D0]
0x180050a82  mov     rcx, rdi
0x180050a85  lea     rdx, [rbp+270h+var_F0]
0x180050a8c  call    PSVSubtract
0x180050a91  mov     r8, [rdi+55C0h]
0x180050a98  lea     r9, [rbp+270h+var_280]
0x180050a9c  mov     rcx, rdi
0x180050a9f  lea     rdx, [rbp+270h+var_230]
0x180050aa3  call    PSVSubtract
0x180050aa8  mov     r8, r15
0x180050aab  lea     rdx, [rbp+270h+var_1E0]
0x180050ab2  mov     rcx, rdi
0x180050ab5  call    PSVCopy
0x180050aba  lea     r9, [rbp+270h+var_230]
0x180050abe  mov     rcx, rdi
0x180050ac1  lea     r8, [rbp+270h+var_1E0]
0x180050ac8  mov     rdx, r15
0x180050acb  call    PStackValueAdd
0x180050ad0  mov     r8, [rdi+55C8h]
0x180050ad7  lea     r9, [rbp+270h+var_2D0]
0x180050adb  mov     rcx, rdi
0x180050ade  lea     rdx, [rbp+270h+var_230]
0x180050ae2  call    PSVSubtract
0x180050ae7  mov     r8, r14
0x180050aea  lea     rdx, [rbp+270h+var_1E0]
0x180050af1  mov     rcx, rdi
0x180050af4  call    PSVCopy
0x180050af9  lea     r9, [rbp+270h+var_230]
0x180050afd  mov     rcx, rdi
0x180050b00  lea     r8, [rbp+270h+var_1E0]
0x180050b07  mov     rdx, r14
0x180050b0a  call    PStackValueAdd
0x180050b0f  mov     ebx, [rbp+270h+arg_70]
0x180050b15  xor     r9d, r9d
0x180050b18  mov     dword ptr [rsp+370h+var_348], ebx
0x180050b1c  mov     rcx, rdi
0x180050b1f  mov     dword ptr [rsp+370h+var_350], esi
0x180050b23  lea     edx, [r9+2]
0x180050b27  lea     r8d, [r9+1]
0x180050b2b  call    StateChange
0x180050b30  mov     r8d, ebx
0x180050b33  mov     [rbp+270h+var_2E8], esi
0x180050b36  lea     rdx, [rbp+270h+var_2E8]
0x180050b3a  mov     [rbp+270h+var_2E4], 10000h
0x180050b41  mov     rcx, rdi
0x180050b44  call    XC_WriteT1PStackValue
0x180050b49  mov     esi, 0Ah
0x180050b4e  mov     r8d, ebx
0x180050b51  mov     edx, esi
0x180050b53  mov     rcx, rdi
0x180050b56  call    XC_WriteT1OpCode
0x180050b5b  mov     r9d, ebx
0x180050b5e  lea     r8, [rbp+270h+var_F0]
0x180050b65  lea     rdx, [rbp+270h+var_A0]
0x180050b6c  mov     rcx, rdi
0x180050b6f  call    WriteFlexCoordinate
0x180050b74  mov     r9d, ebx
0x180050b77  mov     r8, r14
0x180050b7a  mov     rdx, r15
0x180050b7d  mov     rcx, rdi
0x180050b80  call    WriteFlexCoordinate
0x180050b85  mov     rdx, [rbp+270h+var_2E0]
0x180050b89  mov     r9d, ebx
0x180050b8c  mov     r8, r12
0x180050b8f  mov     rcx, rdi
0x180050b92  call    WriteFlexCoordinate
0x180050b97  mov     rdx, [rsp+370h+var_320]
0x180050b9c  mov     r9d, ebx
0x180050b9f  mov     r8, r13
0x180050ba2  mov     rcx, rdi
0x180050ba5  call    WriteFlexCoordinate
0x180050baa  mov     r8, [rsp+370h+var_318]
0x180050baf  mov     r9d, ebx
0x180050bb2  mov     rdx, [rsp+370h+var_310]
0x180050bb7  mov     rcx, rdi
0x180050bba  call    WriteFlexCoordinate
0x180050bbf  mov     r8, [rsp+370h+var_308]
0x180050bc4  mov     r9d, ebx
0x180050bc7  mov     rdx, [rsp+370h+var_300]
0x180050bcc  mov     rcx, rdi
0x180050bcf  call    WriteFlexCoordinate
0x180050bd4  mov     r8, [rsp+370h+var_2F8]
0x180050bd9  mov     r9d, ebx
0x180050bdc  mov     rdx, [rbp+270h+var_2F0]
0x180050be0  mov     rcx, rdi
0x180050be3  call    WriteFlexCoordinate
0x180050be8  mov     rdx, [rbp+270h+var_2D8]
0x180050bec  mov     r8d, ebx
0x180050bef  mov     rcx, rdi
0x180050bf2  call    XC_WriteT1PStackValue
0x180050bf7  mov     r8d, ebx
0x180050bfa  lea     rdx, [rbp+270h+var_190]
0x180050c01  mov     rcx, rdi
0x180050c04  call    XC_WriteT1PStackValue
0x180050c09  mov     r8d, ebx
0x180050c0c  lea     rdx, [rbp+270h+var_140]
0x180050c13  mov     rcx, rdi
0x180050c16  call    XC_WriteT1PStackValue
0x180050c1b  mov     rdx, [rdi+65C0h]
0x180050c22  mov     r8d, ebx
0x180050c25  mov     rcx, rdi
0x180050c28  call    XC_WriteT1PStackValue
0x180050c2d  mov     edx, esi
0x180050c2f  mov     r8d, ebx
0x180050c32  mov     rcx, rdi
0x180050c35  call    XC_WriteT1OpCode
0x180050c3a  mov     rdx, [rdi+55C0h]
0x180050c41  lea     r8, [rbp+270h+var_190]
0x180050c48  mov     rcx, rdi
0x180050c4b  call    PSVCopy
0x180050c50  mov     rdx, [rdi+55C8h]
0x180050c57  lea     r8, [rbp+270h+var_140]
0x180050c5e  mov     rcx, rdi
0x180050c61  call    PSVCopy
0x180050c66  mov     rcx, [rbp+270h+var_50]
0x180050c6d  xor     rcx, rsp; StackCookie
0x180050c70  call    __security_check_cookie
0x180050c75  add     rsp, 338h
0x180050c7c  pop     r15
0x180050c7e  pop     r14
0x180050c80  pop     r13
0x180050c82  pop     r12
0x180050c84  pop     rdi
  ... truncated ...
```
