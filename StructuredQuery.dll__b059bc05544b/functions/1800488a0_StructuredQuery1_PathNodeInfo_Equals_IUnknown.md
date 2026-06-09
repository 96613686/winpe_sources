# StructuredQuery1::PathNodeInfo::Equals(IUnknown *)

- ea: `0x1800488a0`
- end: `0x180048a50`
- name: `?Equals@PathNodeInfo@StructuredQuery1@@UEAAHPEAUIUnknown@@@Z`
- size: `432`
- prototype: `__int64 __fastcall(StructuredQuery1::PathNodeInfo *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800488a0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180048922`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800489a8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180048922`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800489a8`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::PathNodeInfo::Equals(StructuredQuery1::PathNodeInfo *this, struct IUnknown *a2)
{
  unsigned int v2; // edi
  const WCHAR *lpString2; // rbx
  const WCHAR *v5; // rax
  __int64 v6; // rcx
  const WCHAR *v7; // rbx
  const WCHAR *v8; // rax
  __int64 v9; // rcx
  unsigned int v11; // eax
  __int64 v12; // [rsp+58h] [rbp+28h] BYREF
  __int64 v13; // [rsp+60h] [rbp+30h] BYREF
  __int64 v14; // [rsp+68h] [rbp+38h] BYREF

  v2 = 0;
  v13 = 0;
  if ( a2
    && ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_e1c5257a_64e2_4466_8dae_876bb68ef77c,
         &v13) >= 0 )
  {
    lpString2 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 48LL))(v13);
    v5 = (const WCHAR *)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this - 1) + 48LL))((char *)this - 8);
    if ( CompareStringW(0x7Fu, 1u, v5, -1, lpString2, -1) != 2 )
      goto LABEL_15;
    v12 = 0;
    if ( (*(int (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v13 + 32LL))(
           v13,
           &GUID_ed956968_15f7_4b07_a79a_f0dc08b7a6b5,
           &v12) < 0 )
      goto LABEL_15;
    v6 = v12;
    if ( *((_QWORD *)this + 4) )
    {
      if ( !v12 )
        goto LABEL_15;
      v7 = (const WCHAR *)(*(__int64 (**)(void))(*(_QWORD *)v12 + 32LL))();
      v8 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 32LL))(*((_QWORD *)this + 4));
      if ( CompareStringW(0x7Fu, 1u, v8, -1, v7, -1) != 2 )
        goto LABEL_13;
    }
    else if ( v12 )
    {
      goto LABEL_14;
    }
    v14 = 0;
    if ( (*(int (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v13 + 40LL))(
           v13,
           &GUID_25adbbe7_10d0_40da_a8c8_10013f926880,
           &v14) < 0 )
      goto LABEL_13;
    v9 = v14;
    if ( v14 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v14 + 32LL))(v14, *((_QWORD *)this + 5));
      v9 = v14;
      v2 = v11;
    }
    else if ( !*((_QWORD *)this + 5) )
    {
      v2 = 1;
      goto LABEL_13;
    }
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
LABEL_13:
    v6 = v12;
    if ( v12 )
LABEL_14:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
LABEL_15:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  return v2;
}

```

## disassembly

```asm
0x1800488a0  mov     [rsp-18h+arg_0], rbx
0x1800488a5  push    rbp
0x1800488a6  push    rsi
0x1800488a7  push    rdi
0x1800488a8  mov     rbp, rsp
0x1800488ab  sub     rsp, 30h
0x1800488af  xor     edi, edi
0x1800488b1  mov     r9, rdx
0x1800488b4  mov     [rbp+arg_10], rdi
0x1800488b8  mov     rsi, rcx
0x1800488bb  test    rdx, rdx
0x1800488be  jz      loc_180048A1B
0x1800488c4  mov     rax, [rdx]
0x1800488c7  lea     r8, [rbp+arg_10]
0x1800488cb  lea     rdx, _GUID_e1c5257a_64e2_4466_8dae_876bb68ef77c
0x1800488d2  mov     rcx, r9
0x1800488d5  mov     rax, [rax]
0x1800488d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800488dd  test    eax, eax
0x1800488df  js      loc_180048A1B
0x1800488e5  mov     rcx, [rbp+arg_10]
0x1800488e9  mov     rax, [rcx]
0x1800488ec  mov     rax, [rax+30h]
0x1800488f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800488f5  mov     rbx, rax
0x1800488f8  lea     rcx, [rsi-8]
0x1800488fc  mov     rax, [rcx]
0x1800488ff  mov     rax, [rax+30h]
0x180048903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048908  or      r9d, 0FFFFFFFFh; cchCount1
0x18004890c  mov     [rsp+30h+cchCount2], 0FFFFFFFFh; cchCount2
0x180048914  mov     r8, rax; lpString1
0x180048917  mov     [rsp+30h+lpString2], rbx; lpString2
0x18004891c  lea     edx, [rdi+1]; dwCmpFlags
0x18004891f  lea     ecx, [rdi+7Fh]; Locale
0x180048922  call    cs:__imp_CompareStringW
0x180048928  cmp     eax, 2
0x18004892b  jnz     loc_180048A0B
0x180048931  mov     rcx, [rbp+arg_10]
0x180048935  lea     r8, [rbp+arg_8]
0x180048939  mov     [rbp+arg_8], rdi
0x18004893d  lea     rdx, _GUID_ed956968_15f7_4b07_a79a_f0dc08b7a6b5
0x180048944  mov     rax, [rcx]
0x180048947  mov     rax, [rax+20h]
0x18004894b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048950  test    eax, eax
0x180048952  js      loc_180048A0B
0x180048958  mov     rcx, [rbp+arg_8]
0x18004895c  cmp     [rsi+20h], rdi
0x180048960  jz      loc_180048A2A
0x180048966  test    rcx, rcx
0x180048969  jz      loc_180048A0B
0x18004896f  mov     rax, [rcx]
0x180048972  mov     rax, [rax+20h]
0x180048976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004897b  mov     rcx, [rsi+20h]
0x18004897f  mov     rbx, rax
0x180048982  mov     rax, [rcx]
0x180048985  mov     rax, [rax+20h]
0x180048989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004898e  or      r9d, 0FFFFFFFFh; cchCount1
0x180048992  mov     [rsp+30h+cchCount2], 0FFFFFFFFh; cchCount2
0x18004899a  mov     r8, rax; lpString1
0x18004899d  mov     [rsp+30h+lpString2], rbx; lpString2
0x1800489a2  lea     edx, [rdi+1]; dwCmpFlags
0x1800489a5  lea     ecx, [rdi+7Fh]; Locale
0x1800489a8  call    cs:__imp_CompareStringW
0x1800489ae  cmp     eax, 2
0x1800489b1  jnz     short loc_1800489F6
0x1800489b3  mov     rcx, [rbp+arg_10]
0x1800489b7  lea     r8, [rbp+arg_18]
0x1800489bb  mov     [rbp+arg_18], rdi
0x1800489bf  lea     rdx, _GUID_25adbbe7_10d0_40da_a8c8_10013f926880
0x1800489c6  mov     rax, [rcx]
0x1800489c9  mov     rax, [rax+28h]
0x1800489cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800489d2  test    eax, eax
0x1800489d4  js      short loc_1800489F6
0x1800489d6  mov     rcx, [rbp+arg_18]
0x1800489da  test    rcx, rcx
0x1800489dd  jnz     short loc_180048A31
0x1800489df  cmp     [rsi+28h], rdi
0x1800489e3  jz      short loc_180048A49
0x1800489e5  test    rcx, rcx
0x1800489e8  jz      short loc_1800489F6
0x1800489ea  mov     rax, [rcx]
0x1800489ed  mov     rax, [rax+10h]
0x1800489f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800489f6  mov     rcx, [rbp+arg_8]
0x1800489fa  test    rcx, rcx
0x1800489fd  jz      short loc_180048A0B
0x1800489ff  mov     rax, [rcx]
0x180048a02  mov     rax, [rax+10h]
0x180048a06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a0b  mov     rcx, [rbp+arg_10]
0x180048a0f  mov     rax, [rcx]
0x180048a12  mov     rax, [rax+10h]
0x180048a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a1b  mov     rbx, [rsp+30h+arg_0]
0x180048a20  mov     eax, edi
0x180048a22  add     rsp, 30h
0x180048a26  pop     rdi
0x180048a27  pop     rsi
0x180048a28  pop     rbp
0x180048a29  retn
0x180048a2a  test    rcx, rcx
0x180048a2d  jnz     short loc_1800489FF
0x180048a2f  jmp     short loc_1800489B3
0x180048a31  mov     rax, [rcx]
0x180048a34  mov     rdx, [rsi+28h]
0x180048a38  mov     rax, [rax+20h]
0x180048a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a41  mov     rcx, [rbp+arg_18]
0x180048a45  mov     edi, eax
0x180048a47  jmp     short loc_1800489E5
0x180048a49  mov     edi, 1
0x180048a4e  jmp     short loc_1800489F6
```
