# CImpIADOSecurity::IsObjectSafe(IUnknown *,ushort const *,ushort const *,long *)

- ea: `0x180029410`
- end: `0x1800295a4`
- name: `?IsObjectSafe@CImpIADOSecurity@@UEAAHPEAUIUnknown@@PEBG1PEAJ@Z`
- size: `404`
- prototype: `__int64 __fastcall(CImpIADOSecurity *__hidden this, struct IUnknown *, const unsigned __int16 *, const unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180029410`
- `0x180029cbc`
- `0x180030010`

## pseudocode

```c
_BOOL8 __fastcall CImpIADOSecurity::IsObjectSafe(
        CImpIADOSecurity *this,
        struct IUnknown *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int *a5)
{
  int *v5; // rbx
  const unsigned __int16 *v10; // rdx
  struct IUnknownVtbl *lpVtbl; // rax
  int *v12; // r8
  __int64 v13; // rcx
  char v14; // si
  int v15; // eax
  int v16; // eax
  _QWORD v18[3]; // [rsp+30h] [rbp-18h] BYREF
  int v19; // [rsp+80h] [rbp+38h] BYREF

  v5 = &v19;
  v19 = 0;
  if ( a5 )
    v5 = a5;
  *v5 = 0;
  v10 = (const unsigned __int16 *)*((_QWORD *)this + 4);
  if ( !v10 || !(unsigned int)CImpIADOSecurity::isTrustedMachine(this, v10) )
    return 1;
  if ( a2 )
  {
    lpVtbl = a2->lpVtbl;
    a5 = 0;
    v18[0] = 0;
    ((void (__fastcall *)(struct IUnknown *, GUID *, int **))lpVtbl->QueryInterface)(a2, &IID_IADOSecurity, &a5);
    ((void (__fastcall *)(struct IUnknown *, GUID *, _QWORD *))a2->lpVtbl->QueryInterface)(
      a2,
      &IID_IObjectWithSite,
      v18);
    v12 = a5;
    v13 = v18[0];
    if ( a5 && v18[0] )
    {
      v14 = 1;
      if ( *((_QWORD *)this + 5) )
      {
        v15 = (*(__int64 (**)(void))(*(_QWORD *)v18[0] + 24LL))();
        v12 = a5;
        v13 = v18[0];
        *v5 = v15;
      }
      if ( *v5 >= 0 )
      {
        v16 = (*(__int64 (__fastcall **)(int *, _QWORD))(*(_QWORD *)v12 + 32LL))(v12, *((unsigned int *)this + 6));
        *v5 = v16;
        if ( v16 >= 0 && *((_QWORD *)this + 4) )
          *v5 = (*(__int64 (__fastcall **)(int *))(*(_QWORD *)a5 + 24LL))(a5);
        v12 = a5;
        v13 = v18[0];
      }
    }
    else
    {
      v14 = 0;
    }
    if ( v12 )
    {
      (*(void (__fastcall **)(int *))(*(_QWORD *)v12 + 16LL))(v12);
      v13 = v18[0];
    }
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    if ( v14 )
      return *v5 >= 0;
  }
  if ( a3 )
    return (*(unsigned int (__fastcall **)(CImpIADOSecurity *, _QWORD, _QWORD, const unsigned __int16 *, const unsigned __int16 *))(*(_QWORD *)this + 80LL))(
             this,
             *((_QWORD *)this + 5),
             *((_QWORD *)this + 4),
             a3,
             a4) == 0;
  return 0;
}

```

## disassembly

```asm
0x180029410  push    rbp
0x180029412  push    rbx
0x180029413  push    rsi
0x180029414  push    rdi
0x180029415  push    r14
0x180029417  push    r15
0x180029419  mov     rbp, rsp
0x18002941c  sub     rsp, 48h
0x180029420  mov     rax, [rbp+arg_20]
0x180029424  lea     rbx, [rbp+arg_0]
0x180029428  test    rax, rax
0x18002942b  mov     [rbp+arg_0], 0
0x180029432  mov     rsi, rdx
0x180029435  mov     r15, r9
0x180029438  cmovnz  rbx, rax
0x18002943c  mov     r14, r8
0x18002943f  mov     rdi, rcx
0x180029442  mov     dword ptr [rbx], 0
0x180029448  mov     rdx, [rcx+20h]; unsigned __int16 *
0x18002944c  test    rdx, rdx
0x18002944f  jz      loc_180029592
0x180029455  call    ?isTrustedMachine@CImpIADOSecurity@@AEAAJPEBG@Z; CImpIADOSecurity::isTrustedMachine(ushort const *)
0x18002945a  test    eax, eax
0x18002945c  jz      loc_180029592
0x180029462  test    rsi, rsi
0x180029465  jz      loc_18002955F
0x18002946b  mov     rax, [rsi]
0x18002946e  lea     r8, [rbp+arg_20]
0x180029472  lea     rdx, IID_IADOSecurity
0x180029479  mov     [rbp+arg_20], 0
0x180029481  mov     rcx, rsi
0x180029484  mov     [rbp+var_18], 0
0x18002948c  mov     rax, [rax]
0x18002948f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029494  mov     rax, [rsi]
0x180029497  lea     r8, [rbp+var_18]
0x18002949b  lea     rdx, IID_IObjectWithSite
0x1800294a2  mov     rcx, rsi
0x1800294a5  mov     rax, [rax]
0x1800294a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800294ad  mov     r8, [rbp+arg_20]
0x1800294b1  mov     rcx, [rbp+var_18]
0x1800294b5  test    r8, r8
0x1800294b8  jz      short loc_180029525
0x1800294ba  test    rcx, rcx
0x1800294bd  jz      short loc_180029525
0x1800294bf  mov     rdx, [rdi+28h]
0x1800294c3  mov     esi, 1
0x1800294c8  test    rdx, rdx
0x1800294cb  jz      short loc_1800294E3
0x1800294cd  mov     rax, [rcx]
0x1800294d0  mov     rax, [rax+18h]
0x1800294d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800294d9  mov     r8, [rbp+arg_20]
0x1800294dd  mov     rcx, [rbp+var_18]
0x1800294e1  mov     [rbx], eax
0x1800294e3  cmp     dword ptr [rbx], 0
0x1800294e6  jl      short loc_180029528
0x1800294e8  mov     rax, [r8]
0x1800294eb  mov     rcx, r8
0x1800294ee  mov     edx, [rdi+18h]
0x1800294f1  mov     rax, [rax+20h]
0x1800294f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800294fa  mov     [rbx], eax
0x1800294fc  test    eax, eax
0x1800294fe  js      short loc_18002951B
0x180029500  mov     rdx, [rdi+20h]
0x180029504  test    rdx, rdx
0x180029507  jz      short loc_18002951B
0x180029509  mov     rcx, [rbp+arg_20]
0x18002950d  mov     rax, [rcx]
0x180029510  mov     rax, [rax+18h]
0x180029514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029519  mov     [rbx], eax
0x18002951b  mov     r8, [rbp+arg_20]
0x18002951f  mov     rcx, [rbp+var_18]
0x180029523  jmp     short loc_180029528
0x180029525  xor     sil, sil
0x180029528  test    r8, r8
0x18002952b  jz      short loc_180029540
0x18002952d  mov     rax, [r8]
0x180029530  mov     rcx, r8
0x180029533  mov     rax, [rax+10h]
0x180029537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002953c  mov     rcx, [rbp+var_18]
0x180029540  test    rcx, rcx
0x180029543  jz      short loc_180029551
0x180029545  mov     rax, [rcx]
0x180029548  mov     rax, [rax+10h]
0x18002954c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029551  test    sil, sil
0x180029554  jz      short loc_18002955F
0x180029556  mov     eax, [rbx]
0x180029558  not     eax
0x18002955a  shr     eax, 1Fh
0x18002955d  jmp     short loc_180029597
0x18002955f  test    r14, r14
0x180029562  jz      short loc_18002958E
0x180029564  mov     rax, [rdi]
0x180029567  mov     r9, r14
0x18002956a  mov     r8, [rdi+20h]
0x18002956e  mov     rcx, rdi
0x180029571  mov     rdx, [rdi+28h]
0x180029575  mov     [rsp+48h+var_28], r15
0x18002957a  mov     rax, [rax+50h]
0x18002957e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029583  xor     ecx, ecx
0x180029585  test    eax, eax
0x180029587  setz    cl
0x18002958a  mov     eax, ecx
0x18002958c  jmp     short loc_180029597
0x18002958e  xor     eax, eax
0x180029590  jmp     short loc_180029597
0x180029592  mov     eax, 1
0x180029597  add     rsp, 48h
0x18002959b  pop     r15
0x18002959d  pop     r14
0x18002959f  pop     rdi
0x1800295a0  pop     rsi
0x1800295a1  pop     rbx
0x1800295a2  pop     rbp
0x1800295a3  retn
```
