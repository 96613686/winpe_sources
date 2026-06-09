# std::function<long (void)>::operator=(std::function<long (void)> const &)

- ea: `0x140003888`
- end: `0x140003a27`
- name: `??4?$function@$$A6AJXZ@std@@QEAAAEAV01@AEBV01@@Z`
- size: `415`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140004f6c`
- `0x140007000`

## callees

- `0x140001460`
- `0x140003888`
- `0x14000a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::function<long (void)>::operator=(__int64 a1, __int64 a2)
{
  __int64 (__fastcall ***v3)(_QWORD, _BYTE *); // r8
  _BYTE *v4; // rcx
  _BYTE *v5; // rdx
  _BYTE *v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  _BYTE *v11; // rdx
  _BYTE v12[56]; // [rsp+20h] [rbp-39h] BYREF
  _BYTE *v13; // [rsp+58h] [rbp-1h]
  _BYTE v14[56]; // [rsp+60h] [rbp+7h] BYREF
  _BYTE *v15; // [rsp+98h] [rbp+3Fh]

  v13 = 0;
  v3 = *(__int64 (__fastcall ****)(_QWORD, _BYTE *))(a2 + 56);
  v4 = 0;
  if ( v3 )
  {
    v4 = (_BYTE *)(**v3)(v3, v12);
    v13 = v4;
  }
  if ( v4 != v12 && *(_QWORD *)(a1 + 56) != a1 )
  {
    v13 = *(_BYTE **)(a1 + 56);
LABEL_6:
    *(_QWORD *)(a1 + 56) = v4;
    goto LABEL_7;
  }
  v15 = 0;
  if ( v4 )
  {
    if ( v4 == v12 )
    {
      v15 = (_BYTE *)(*(__int64 (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v4 + 8LL))(v4, v14);
      if ( !v13 )
        goto LABEL_16;
      v7 = v12;
      LOBYTE(v7) = v13 != v12;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v13 + 32LL))(v13, v7);
    }
    else
    {
      v15 = v4;
    }
    v13 = 0;
  }
LABEL_16:
  v8 = *(_QWORD *)(a1 + 56);
  if ( !v8 )
    goto LABEL_22;
  if ( v8 == a1 )
  {
    v13 = (_BYTE *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v8 + 8LL))(v8, v12);
    v10 = *(_QWORD *)(a1 + 56);
    if ( !v10 )
      goto LABEL_22;
    LOBYTE(v9) = v10 != a1;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 32LL))(v10, v9);
  }
  else
  {
    v13 = *(_BYTE **)(a1 + 56);
  }
  *(_QWORD *)(a1 + 56) = 0;
LABEL_22:
  v4 = v15;
  if ( v15 )
  {
    if ( v15 != v14 )
      goto LABEL_6;
    *(_QWORD *)(a1 + 56) = (*(__int64 (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v15 + 8LL))(v15, a1);
    if ( v15 )
    {
      v11 = v14;
      LOBYTE(v11) = v15 != v14;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v15 + 32LL))(v15, v11);
    }
  }
LABEL_7:
  if ( v13 )
  {
    v5 = v12;
    LOBYTE(v5) = v13 != v12;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v13 + 32LL))(v13, v5);
  }
  return a1;
}

```

## disassembly

```asm
0x140003888  mov     [rsp-8+arg_10], rbx
0x14000388d  push    rbp
0x14000388e  lea     rbp, [rsp-57h]
0x140003893  sub     rsp, 0B0h
0x14000389a  mov     rax, cs:__security_cookie
0x1400038a1  xor     rax, rsp
0x1400038a4  mov     [rbp+57h+var_10], rax
0x1400038a8  mov     rbx, rcx
0x1400038ab  mov     [rbp+57h+var_58], 0
0x1400038b3  mov     r8, [rdx+38h]
0x1400038b7  xor     ecx, ecx
0x1400038b9  test    r8, r8
0x1400038bc  jz      short loc_1400038D7
0x1400038be  mov     rax, [r8]
0x1400038c1  lea     rdx, [rbp+57h+var_90]
0x1400038c5  mov     rcx, r8
0x1400038c8  mov     rax, [rax]
0x1400038cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400038d0  mov     rcx, rax
0x1400038d3  mov     [rbp+57h+var_58], rax
0x1400038d7  lea     rax, [rbp+57h+var_90]
0x1400038db  cmp     rcx, rax
0x1400038de  jz      short loc_140003930
0x1400038e0  mov     rax, [rbx+38h]
0x1400038e4  cmp     rax, rbx
0x1400038e7  jz      short loc_140003930
0x1400038e9  mov     [rbp+57h+var_58], rax
0x1400038ed  mov     [rbx+38h], rcx
0x1400038f1  mov     rcx, [rbp+57h+var_58]
0x1400038f5  test    rcx, rcx
0x1400038f8  jz      short loc_140003910
0x1400038fa  mov     rax, [rcx]
0x1400038fd  lea     rdx, [rbp+57h+var_90]
0x140003901  cmp     rcx, rdx
0x140003904  setnz   dl
0x140003907  mov     rax, [rax+20h]
0x14000390b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003910  mov     rax, rbx
0x140003913  mov     rcx, [rbp+57h+var_10]
0x140003917  xor     rcx, rsp; StackCookie
0x14000391a  call    __security_check_cookie
0x14000391f  mov     rbx, [rsp+0B0h+arg_10]
0x140003927  add     rsp, 0B0h
0x14000392e  pop     rbp
0x14000392f  retn
0x140003930  mov     [rbp+57h+var_18], 0
0x140003938  test    rcx, rcx
0x14000393b  jz      short loc_140003987
0x14000393d  lea     rax, [rbp+57h+var_90]
0x140003941  cmp     rcx, rax
0x140003944  jnz     short loc_14000397B
0x140003946  mov     rax, [rcx]
0x140003949  lea     rdx, [rbp+57h+var_50]
0x14000394d  mov     rax, [rax+8]
0x140003951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003956  mov     [rbp+57h+var_18], rax
0x14000395a  mov     rcx, [rbp+57h+var_58]
0x14000395e  test    rcx, rcx
0x140003961  jz      short loc_140003987
0x140003963  mov     rax, [rcx]
0x140003966  lea     rdx, [rbp+57h+var_90]
0x14000396a  cmp     rcx, rdx
0x14000396d  setnz   dl
0x140003970  mov     rax, [rax+20h]
0x140003974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003979  jmp     short loc_14000397F
0x14000397b  mov     [rbp+57h+var_18], rcx
0x14000397f  mov     [rbp+57h+var_58], 0
0x140003987  mov     rcx, [rbx+38h]
0x14000398b  test    rcx, rcx
0x14000398e  jz      short loc_1400039D2
0x140003990  cmp     rcx, rbx
0x140003993  jnz     short loc_1400039C6
0x140003995  mov     rax, [rcx]
0x140003998  lea     rdx, [rbp+57h+var_90]
0x14000399c  mov     rax, [rax+8]
0x1400039a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400039a5  mov     [rbp+57h+var_58], rax
0x1400039a9  mov     rcx, [rbx+38h]
0x1400039ad  test    rcx, rcx
0x1400039b0  jz      short loc_1400039D2
0x1400039b2  mov     rax, [rcx]
0x1400039b5  cmp     rcx, rbx
0x1400039b8  setnz   dl
0x1400039bb  mov     rax, [rax+20h]
0x1400039bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400039c4  jmp     short loc_1400039CA
0x1400039c6  mov     [rbp+57h+var_58], rcx
0x1400039ca  mov     qword ptr [rbx+38h], 0
0x1400039d2  mov     rcx, [rbp+57h+var_18]
0x1400039d6  test    rcx, rcx
0x1400039d9  jz      loc_1400038F1
0x1400039df  lea     rax, [rbp+57h+var_50]
0x1400039e3  cmp     rcx, rax
0x1400039e6  jnz     loc_1400038ED
0x1400039ec  mov     rax, [rcx]
0x1400039ef  mov     rdx, rbx
0x1400039f2  mov     rax, [rax+8]
0x1400039f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400039fb  mov     [rbx+38h], rax
0x1400039ff  mov     rcx, [rbp+57h+var_18]
0x140003a03  test    rcx, rcx
0x140003a06  jz      loc_1400038F1
0x140003a0c  mov     rax, [rcx]
0x140003a0f  lea     rdx, [rbp+57h+var_50]
0x140003a13  cmp     rcx, rdx
0x140003a16  setnz   dl
0x140003a19  mov     rax, [rax+20h]
0x140003a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003a22  jmp     loc_1400038F1
```
