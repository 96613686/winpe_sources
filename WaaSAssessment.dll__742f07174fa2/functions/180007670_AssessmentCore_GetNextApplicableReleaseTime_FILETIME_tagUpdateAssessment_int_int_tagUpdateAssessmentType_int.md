# AssessmentCore::GetNextApplicableReleaseTime(_FILETIME *,tagUpdateAssessment *,int *,int *,tagUpdateAssessmentType,int)

- ea: `0x180007670`
- end: `0x1800078f8`
- name: `?GetNextApplicableReleaseTime@AssessmentCore@@UEAAJPEAU_FILETIME@@PEAUtagUpdateAssessment@@PEAH2W4tagUpdateAssessmentType@@H@Z`
- size: `648`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180007670`
- `0x18001752c`
- `0x18001972e`
- `0x180019760`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall AssessmentCore::GetNextApplicableReleaseTime(
        __int64 *a1,
        _QWORD *a2,
        __int64 a3,
        _DWORD *a4,
        _DWORD *a5,
        int a6,
        unsigned int a7)
{
  unsigned int v11; // ebx
  int v13; // eax
  int v14; // eax
  __int64 v15; // xmm0_8
  int v16; // eax
  int v17; // eax
  int v18; // eax
  __int64 v19; // rax
  int v20; // eax
  int v21; // eax
  __int64 v22; // rax
  __int64 v23; // rax
  int v24; // eax
  int v25; // eax
  __int64 v26; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v28; // [rsp+40h] [rbp-C0h] BYREF
  int v29; // [rsp+48h] [rbp-B8h]
  __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  int v31; // [rsp+58h] [rbp-A8h]
  _BYTE v32[16]; // [rsp+60h] [rbp-A0h] BYREF
  int v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+74h] [rbp-8Ch]
  _BYTE v35[4]; // [rsp+B0h] [rbp-50h] BYREF
  int v36; // [rsp+B4h] [rbp-4Ch]
  __int64 v37; // [rsp+B8h] [rbp-48h]

  if ( !a2 || !a4 || !a5 || (v11 = 0, !a3) )
    v11 = -2147467261;
  *a4 = 0;
  *a5 = 0;
  *a2 = 0;
  *(_QWORD *)a3 = 0;
  *(_DWORD *)(a3 + 8) = 0;
  if ( (v11 & 0x80000000) != 0 )
    goto LABEL_12;
  switch ( a6 )
  {
    case 0:
      memset_0(v35, 0, 0x50u);
      v23 = *a1;
      v27 = 0;
      v24 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *, __int64 *, _QWORD *, unsigned int))(v23 + 128))(
              a1,
              v35,
              &v27,
              a2,
              a7);
      v11 = v24;
      if ( v24 < 0 )
        goto LABEL_12;
      if ( v24 == 1 )
        return v11;
      v25 = v36;
      if ( v36 )
        *a4 = 1;
      if ( v25 == 3 )
        *a5 = 1;
      *(_DWORD *)a3 = v25;
      v22 = v37;
      goto LABEL_43;
    case 1:
      memset_0(v32, 0, 0x50u);
      v19 = *a1;
      v26 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *, _QWORD *, __int64 *, unsigned int))(v19 + 128))(
              a1,
              v32,
              a2,
              &v26,
              a7);
      v11 = v20;
      if ( v20 < 0 )
        goto LABEL_12;
      if ( v20 == 1 )
        return v11;
      v21 = v33;
      if ( v33 )
        *a4 = 1;
      if ( v21 == 3 )
        *a5 = 1;
      *(_DWORD *)a3 = v21;
      v22 = v34;
LABEL_43:
      *(_QWORD *)(a3 + 4) = v22;
      return v11;
    case 2:
      v30 = 0;
      v31 = 0;
      v17 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, _QWORD *, _QWORD, _DWORD))(*a1 + 136))(a1, &v30, a2, a7, 0);
      v11 = v17;
      if ( v17 < 0 )
        goto LABEL_12;
      if ( v17 == 1 )
        return v11;
      v18 = v30;
      if ( (_DWORD)v30 )
        *a4 = 1;
      if ( v18 == 3 )
        *a5 = 1;
      v15 = v30;
      v16 = v31;
      goto LABEL_28;
    case 3:
      v28 = 0;
      v29 = 0;
      v13 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, _QWORD *, _QWORD, _DWORD))(*a1 + 144))(a1, &v28, a2, a7, 0);
      v11 = v13;
      if ( v13 < 0 )
        goto LABEL_12;
      if ( v13 == 1 )
        return v11;
      v14 = v28;
      if ( (_DWORD)v28 )
        *a4 = 1;
      if ( v14 == 3 )
        *a5 = 1;
      v15 = v28;
      v16 = v29;
LABEL_28:
      *(_QWORD *)a3 = v15;
      *(_DWORD *)(a3 + 8) = v16;
      return v11;
  }
  v11 = -2147024809;
LABEL_12:
  LogLevel(2u, L"GetNextApplicableReleaseTime Failure: 0x%x", v11);
  return v11;
}

```

## disassembly

```asm
0x180007670  push    rbp
0x180007672  push    rbx
0x180007673  push    rsi
0x180007674  push    rdi
0x180007675  push    r12
0x180007677  push    r14
0x180007679  push    r15
0x18000767b  lea     rbp, [rsp-10h]
0x180007680  sub     rsp, 110h
0x180007687  mov     rax, cs:__security_cookie
0x18000768e  xor     rax, rsp
0x180007691  mov     [rbp+40h+var_40], rax
0x180007695  mov     r14, [rbp+40h+arg_20]
0x180007699  mov     rsi, r9
0x18000769c  mov     rdi, r8
0x18000769f  mov     r15, rdx
0x1800076a2  mov     r12, rcx
0x1800076a5  test    rdx, rdx
0x1800076a8  jz      short loc_1800076BB
0x1800076aa  test    r9, r9
0x1800076ad  jz      short loc_1800076BB
0x1800076af  test    r14, r14
0x1800076b2  jz      short loc_1800076BB
0x1800076b4  xor     ebx, ebx
0x1800076b6  test    r8, r8
0x1800076b9  jnz     short loc_1800076C0
0x1800076bb  mov     ebx, 80004003h
0x1800076c0  mov     dword ptr [r9], 0
0x1800076c7  xor     eax, eax
0x1800076c9  mov     dword ptr [r14], 0
0x1800076d0  mov     [rdx], rax
0x1800076d3  mov     [r8], rax
0x1800076d6  mov     [r8+8], eax
0x1800076da  test    ebx, ebx
0x1800076dc  js      short loc_180007705
0x1800076de  mov     ecx, [rbp+40h+arg_28]
0x1800076e1  test    ecx, ecx
0x1800076e3  jz      loc_180007880
0x1800076e9  sub     ecx, 1
0x1800076ec  jz      loc_18000780B
0x1800076f2  sub     ecx, 1
0x1800076f5  jz      loc_180007799
0x1800076fb  cmp     ecx, 1
0x1800076fe  jz      short loc_180007739
0x180007700  mov     ebx, 80070057h
0x180007705  mov     r8d, ebx
0x180007708  lea     rdx, aGetnextapplica; "GetNextApplicableReleaseTime Failure: 0"...
0x18000770f  mov     ecx, 2; unsigned __int8
0x180007714  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180007719  mov     eax, ebx
0x18000771b  mov     rcx, [rbp+40h+var_40]
0x18000771f  xor     rcx, rsp; StackCookie
0x180007722  call    __security_check_cookie
0x180007727  add     rsp, 110h
0x18000772e  pop     r15
0x180007730  pop     r14
0x180007732  pop     r12
0x180007734  pop     rdi
0x180007735  pop     rsi
0x180007736  pop     rbx
0x180007737  pop     rbp
0x180007738  retn
0x180007739  mov     r9d, [rbp+40h+arg_30]
0x180007740  lea     rdx, [rsp+140h+var_100]
0x180007745  mov     [rsp+140h+var_100], rax
0x18000774a  mov     r8, r15
0x18000774d  mov     [rsp+140h+var_F8], eax
0x180007751  mov     rcx, r12
0x180007754  mov     rax, [r12]
0x180007758  mov     [rsp+140h+var_120], 0
0x180007760  mov     rax, [rax+90h]
0x180007767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000776c  mov     ebx, eax
0x18000776e  test    eax, eax
0x180007770  js      short loc_180007705
0x180007772  mov     ecx, 1
0x180007777  cmp     eax, ecx
0x180007779  jz      short loc_180007719
0x18000777b  mov     eax, dword ptr [rsp+140h+var_100]
0x18000777f  test    eax, eax
0x180007781  jz      short loc_180007785
0x180007783  mov     [rsi], ecx
0x180007785  cmp     eax, 3
0x180007788  jnz     short loc_18000778D
0x18000778a  mov     [r14], ecx
0x18000778d  movsd   xmm0, [rsp+140h+var_100]
0x180007793  mov     eax, [rsp+140h+var_F8]
0x180007797  jmp     short loc_1800077FF
0x180007799  mov     r9d, [rbp+40h+arg_30]
0x1800077a0  lea     rdx, [rsp+140h+var_F0]
0x1800077a5  mov     [rsp+140h+var_F0], rax
0x1800077aa  mov     r8, r15
0x1800077ad  mov     [rsp+140h+var_E8], eax
0x1800077b1  mov     rcx, r12
0x1800077b4  mov     rax, [r12]
0x1800077b8  mov     [rsp+140h+var_120], 0
0x1800077c0  mov     rax, [rax+88h]
0x1800077c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077cc  mov     ebx, eax
0x1800077ce  test    eax, eax
0x1800077d0  js      loc_180007705
0x1800077d6  mov     ecx, 1
0x1800077db  cmp     eax, ecx
0x1800077dd  jz      loc_180007719
0x1800077e3  mov     eax, dword ptr [rsp+140h+var_F0]
0x1800077e7  test    eax, eax
0x1800077e9  jz      short loc_1800077ED
0x1800077eb  mov     [rsi], ecx
0x1800077ed  cmp     eax, 3
0x1800077f0  jnz     short loc_1800077F5
0x1800077f2  mov     [r14], ecx
0x1800077f5  movsd   xmm0, [rsp+140h+var_F0]
0x1800077fb  mov     eax, [rsp+140h+var_E8]
0x1800077ff  movsd   qword ptr [rdi], xmm0
0x180007803  mov     [rdi+8], eax
0x180007806  jmp     loc_180007719
0x18000780b  xor     edx, edx; Val
0x18000780d  lea     rcx, [rsp+140h+var_E0]; void *
0x180007812  lea     r8d, [rdx+50h]; Size
0x180007816  call    memset_0
0x18000781b  mov     rax, [r12]
0x18000781f  lea     r9, [rsp+140h+var_110]
0x180007824  mov     ecx, [rbp+40h+arg_30]
0x18000782a  lea     rdx, [rsp+140h+var_E0]
0x18000782f  mov     [rsp+140h+var_120], ecx
0x180007833  mov     r8, r15
0x180007836  mov     rcx, r12
0x180007839  mov     [rsp+140h+var_110], 0
0x180007842  mov     rax, [rax+80h]
0x180007849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000784e  mov     ebx, eax
0x180007850  test    eax, eax
0x180007852  js      loc_180007705
0x180007858  mov     ecx, 1
0x18000785d  cmp     eax, ecx
0x18000785f  jz      loc_180007719
0x180007865  mov     eax, [rsp+140h+var_D0]
0x180007869  test    eax, eax
0x18000786b  jz      short loc_18000786F
0x18000786d  mov     [rsi], ecx
0x18000786f  cmp     eax, 3
0x180007872  jnz     short loc_180007877
0x180007874  mov     [r14], ecx
0x180007877  mov     [rdi], eax
0x180007879  mov     rax, [rsp+140h+var_CC]
0x18000787e  jmp     short loc_1800078EF
0x180007880  xor     edx, edx; Val
0x180007882  lea     rcx, [rbp+40h+var_90]; void *
0x180007886  lea     r8d, [rdx+50h]; Size
0x18000788a  call    memset_0
0x18000788f  mov     rax, [r12]
0x180007893  lea     r8, [rsp+140h+var_108]
0x180007898  mov     ecx, [rbp+40h+arg_30]
0x18000789e  lea     rdx, [rbp+40h+var_90]
0x1800078a2  mov     [rsp+140h+var_120], ecx
0x1800078a6  mov     r9, r15
0x1800078a9  mov     rcx, r12
0x1800078ac  mov     [rsp+140h+var_108], 0
0x1800078b5  mov     rax, [rax+80h]
0x1800078bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078c1  mov     ebx, eax
0x1800078c3  test    eax, eax
0x1800078c5  js      loc_180007705
0x1800078cb  mov     ecx, 1
0x1800078d0  cmp     eax, ecx
0x1800078d2  jz      loc_180007719
0x1800078d8  mov     eax, [rbp+40h+var_8C]
0x1800078db  test    eax, eax
0x1800078dd  jz      short loc_1800078E1
0x1800078df  mov     [rsi], ecx
0x1800078e1  cmp     eax, 3
0x1800078e4  jnz     short loc_1800078E9
0x1800078e6  mov     [r14], ecx
0x1800078e9  mov     [rdi], eax
0x1800078eb  mov     rax, [rbp+40h+var_88]
0x1800078ef  mov     [rdi+4], rax
0x1800078f3  jmp     loc_180007719
```
