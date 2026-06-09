# ipx::mtf::TransportLib_SerializeToStream(IUnknown *,IUnknown * *)

- ea: `0x1800243f0`
- end: `0x180024712`
- name: `?TransportLib_SerializeToStream@mtf@ipx@@YAJPEAUIUnknown@@PEAPEAU3@@Z`
- size: `802`
- prototype: `__int64 __fastcall(ipx::mtf *__hidden this, struct IUnknown *, struct IUnknown **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800215c0`
- `0x180022c0c`

## callees

- `0x180006074`
- `0x1800243f0`
- `0x18002bca0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180024521`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180024521`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ipx::mtf::TransportLib_SerializeToStream(ipx::mtf *this, struct IUnknown *a2, struct IUnknown **a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  struct IUnknownVtbl *v7; // rcx
  __int64 v8; // rcx
  int v10; // eax
  __int64 v11; // rcx
  HRESULT v12; // eax
  LPSTREAM v13; // rcx
  __int64 v14; // rcx
  int v15; // eax
  LPSTREAM v16; // rcx
  __int64 v17; // rcx
  int v18; // eax
  LPSTREAM v19; // rcx
  __int64 v20; // rcx
  int v21; // eax
  LPSTREAM v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  bool v25; // zf
  int v26; // [rsp+20h] [rbp-40h]
  __int64 v27; // [rsp+30h] [rbp-30h] BYREF
  LPSTREAM ppstm; // [rsp+38h] [rbp-28h] BYREF
  struct IUnknownVtbl *v29; // [rsp+40h] [rbp-20h] BYREF
  __int128 v30; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v27 = 0;
  if ( (**(int (__fastcall ***)(ipx::mtf *, GUID *, __int64 *))this)(
         this,
         &GUID_06445657_3a07_492d_94c3_052034ef2d12,
         &v27) >= 0 )
  {
    v30 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v27 + 24LL))(v27, &v30);
    v6 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\serialize.cpp",
        (const char *)(unsigned int)v10,
        v26);
      v11 = v27;
      v27 = 0;
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      return v6;
    }
    ppstm = 0;
    v12 = CreateStreamOnHGlobal(0, 1, &ppstm);
    v6 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x30,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\serialize.cpp",
        (const char *)(unsigned int)v12,
        v26);
      v13 = ppstm;
      ppstm = 0;
      if ( v13 )
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v13 + 16LL))(v13);
      v14 = v27;
      v27 = 0;
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      return v6;
    }
    v15 = (*(__int64 (__fastcall **)(LPSTREAM, __int128 *, __int64))(*(_QWORD *)ppstm + 32LL))(ppstm, &v30, 16);
    v6 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x32,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\serialize.cpp",
        (const char *)(unsigned int)v15,
        v26);
      v16 = ppstm;
      ppstm = 0;
      if ( v16 )
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v16 + 16LL))(v16);
      v17 = v27;
      v27 = 0;
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      return v6;
    }
    v18 = (*(__int64 (__fastcall **)(__int64, LPSTREAM))(*(_QWORD *)v27 + 32LL))(v27, ppstm);
    v6 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x34,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\serialize.cpp",
        (const char *)(unsigned int)v18,
        v26);
      v19 = ppstm;
      ppstm = 0;
      if ( v19 )
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v19 + 16LL))(v19);
      v20 = v27;
      v27 = 0;
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      return v6;
    }
    v21 = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(ppstm, 0, 0, 0);
    v6 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x37,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\serialize.cpp",
        (const char *)(unsigned int)v21,
        v26);
      v22 = ppstm;
      ppstm = 0;
      if ( v22 )
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v22 + 16LL))(v22);
      v23 = v27;
      v27 = 0;
      if ( v23 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      return v6;
    }
    a2->lpVtbl = (struct IUnknownVtbl *)ppstm;
    ppstm = 0;
  }
  else
  {
    v29 = 0;
    v5 = (**(__int64 (__fastcall ***)(ipx::mtf *, GUID *, struct IUnknownVtbl **))this)(
           this,
           &GUID_0000000c_0000_0000_c000_000000000046,
           &v29);
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x25,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\serialize.cpp",
        (const char *)(unsigned int)v5,
        v26);
      v7 = v29;
      v29 = 0;
      if ( v7 )
        (*((void (__fastcall **)(struct IUnknownVtbl *))v7->QueryInterface + 2))(v7);
      v8 = v27;
      v27 = 0;
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      return v6;
    }
    a2->lpVtbl = v29;
    v29 = 0;
  }
  v24 = v27;
  v25 = v27 == 0;
  v27 = 0;
  if ( !v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  return 0;
}

```

## disassembly

```asm
0x1800243f0  mov     [rsp-18h+arg_10], rbx
0x1800243f5  push    rbp
0x1800243f6  push    rsi
0x1800243f7  push    rdi
0x1800243f8  mov     rbp, rsp
0x1800243fb  sub     rsp, 60h
0x1800243ff  mov     rax, cs:__security_cookie
0x180024406  xor     rax, rsp
0x180024409  mov     [rbp+var_8], rax
0x18002440d  mov     rdi, rdx
0x180024410  mov     rbx, rcx
0x180024413  xor     esi, esi
0x180024415  mov     [rbp+var_30], rsi
0x180024419  mov     rax, [rcx]
0x18002441c  lea     r8, [rbp+var_30]
0x180024420  lea     rdx, _GUID_06445657_3a07_492d_94c3_052034ef2d12
0x180024427  mov     rax, [rax]
0x18002442a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002442f  test    eax, eax
0x180024431  jns     loc_1800244BC
0x180024437  mov     [rbp+var_20], rsi
0x18002443b  mov     rax, [rbx]
0x18002443e  lea     r8, [rbp+var_20]
0x180024442  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x180024449  mov     rcx, rbx
0x18002444c  mov     rax, [rax]
0x18002444f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024454  mov     ebx, eax
0x180024456  test    eax, eax
0x180024458  jns     short loc_1800244AC
0x18002445a  mov     rcx, [rbp+18h]; this
0x18002445e  mov     r9d, eax; char *
0x180024461  lea     r8, aMincoreTextinp_1; "mincore\\textinput\\dev\\mtf\\internal"...
0x180024468  lea     edx, [rsi+25h]; void *
0x18002446b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024470  nop
0x180024471  mov     rcx, [rbp+var_20]
0x180024475  mov     [rbp+var_20], rsi
0x180024479  test    rcx, rcx
0x18002447c  jz      short loc_18002448B
0x18002447e  mov     rax, [rcx]
0x180024481  mov     rax, [rax+10h]
0x180024485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002448a  nop
0x18002448b  mov     rcx, [rbp+var_30]
0x18002448f  mov     [rbp+var_30], rsi
0x180024493  test    rcx, rcx
0x180024496  jz      short loc_1800244A5
0x180024498  mov     rax, [rcx]
0x18002449b  mov     rax, [rax+10h]
0x18002449f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800244a4  nop
0x1800244a5  mov     eax, ebx
0x1800244a7  jmp     loc_1800246F6
0x1800244ac  mov     rax, [rbp+var_20]
0x1800244b0  mov     [rdi], rax
0x1800244b3  mov     [rbp+var_20], rsi
0x1800244b7  jmp     loc_1800246DA
0x1800244bc  xorps   xmm0, xmm0
0x1800244bf  movups  [rbp+var_18], xmm0
0x1800244c3  mov     rcx, [rbp+var_30]
0x1800244c7  mov     rax, [rcx]
0x1800244ca  lea     rdx, [rbp+var_18]
0x1800244ce  mov     rax, [rax+18h]
0x1800244d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800244d7  mov     ebx, eax
0x1800244d9  test    eax, eax
0x1800244db  jns     short loc_180024512
0x1800244dd  mov     rcx, [rbp+18h]; this
0x1800244e1  mov     r9d, eax; char *
0x1800244e4  lea     r8, aMincoreTextinp_1; "mincore\\textinput\\dev\\mtf\\internal"...
0x1800244eb  mov     edx, 2Dh ; '-'; void *
0x1800244f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800244f5  nop
0x1800244f6  mov     rcx, [rbp+var_30]
0x1800244fa  mov     [rbp+var_30], rsi
0x1800244fe  test    rcx, rcx
0x180024501  jz      short loc_180024510
0x180024503  mov     rax, [rcx]
0x180024506  mov     rax, [rax+10h]
0x18002450a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002450f  nop
0x180024510  jmp     short loc_1800244A5
0x180024512  mov     [rbp+ppstm], rsi
0x180024516  lea     r8, [rbp+ppstm]; ppstm
0x18002451a  mov     edx, 1; fDeleteOnRelease
0x18002451f  xor     ecx, ecx; hGlobal
0x180024521  call    cs:__imp_CreateStreamOnHGlobal
0x180024527  mov     ebx, eax
0x180024529  test    eax, eax
0x18002452b  jns     short loc_18002457F
0x18002452d  mov     rcx, [rbp+18h]; this
0x180024531  mov     r9d, eax; char *
0x180024534  lea     r8, aMincoreTextinp_1; "mincore\\textinput\\dev\\mtf\\internal"...
0x18002453b  mov     edx, 30h ; '0'; void *
0x180024540  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024545  nop
0x180024546  mov     rcx, [rbp+ppstm]
0x18002454a  mov     [rbp+ppstm], rsi
0x18002454e  test    rcx, rcx
0x180024551  jz      short loc_180024560
0x180024553  mov     rax, [rcx]
0x180024556  mov     rax, [rax+10h]
0x18002455a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002455f  nop
0x180024560  mov     rcx, [rbp+var_30]
0x180024564  mov     [rbp+var_30], rsi
0x180024568  test    rcx, rcx
0x18002456b  jz      short loc_18002457A
0x18002456d  mov     rax, [rcx]
0x180024570  mov     rax, [rax+10h]
0x180024574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024579  nop
0x18002457a  jmp     loc_1800244A5
0x18002457f  mov     rcx, [rbp+ppstm]
0x180024583  mov     rax, [rcx]
0x180024586  xor     r9d, r9d
0x180024589  lea     r8d, [r9+10h]
0x18002458d  lea     rdx, [rbp+var_18]
0x180024591  mov     rax, [rax+20h]
0x180024595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002459a  mov     ebx, eax
0x18002459c  test    eax, eax
0x18002459e  jns     short loc_1800245F2
0x1800245a0  mov     rcx, [rbp+18h]; this
0x1800245a4  mov     r9d, eax; char *
0x1800245a7  lea     r8, aMincoreTextinp_1; "mincore\\textinput\\dev\\mtf\\internal"...
0x1800245ae  mov     edx, 32h ; '2'; void *
0x1800245b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800245b8  nop
0x1800245b9  mov     rcx, [rbp+ppstm]
0x1800245bd  mov     [rbp+ppstm], rsi
0x1800245c1  test    rcx, rcx
0x1800245c4  jz      short loc_1800245D3
0x1800245c6  mov     rax, [rcx]
0x1800245c9  mov     rax, [rax+10h]
0x1800245cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245d2  nop
0x1800245d3  mov     rcx, [rbp+var_30]
0x1800245d7  mov     [rbp+var_30], rsi
0x1800245db  test    rcx, rcx
0x1800245de  jz      short loc_1800245ED
0x1800245e0  mov     rax, [rcx]
0x1800245e3  mov     rax, [rax+10h]
0x1800245e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245ec  nop
0x1800245ed  jmp     loc_1800244A5
0x1800245f2  mov     rcx, [rbp+var_30]
0x1800245f6  mov     rax, [rcx]
0x1800245f9  mov     rdx, [rbp+ppstm]
0x1800245fd  mov     rax, [rax+20h]
0x180024601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024606  mov     ebx, eax
0x180024608  test    eax, eax
0x18002460a  jns     short loc_18002465E
0x18002460c  mov     rcx, [rbp+18h]; this
0x180024610  mov     r9d, eax; char *
0x180024613  lea     r8, aMincoreTextinp_1; "mincore\\textinput\\dev\\mtf\\internal"...
0x18002461a  mov     edx, 34h ; '4'; void *
0x18002461f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024624  nop
0x180024625  mov     rcx, [rbp+ppstm]
0x180024629  mov     [rbp+ppstm], rsi
0x18002462d  test    rcx, rcx
0x180024630  jz      short loc_18002463F
0x180024632  mov     rax, [rcx]
0x180024635  mov     rax, [rax+10h]
0x180024639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002463e  nop
0x18002463f  mov     rcx, [rbp+var_30]
0x180024643  mov     [rbp+var_30], rsi
0x180024647  test    rcx, rcx
0x18002464a  jz      short loc_180024659
0x18002464c  mov     rax, [rcx]
0x18002464f  mov     rax, [rax+10h]
0x180024653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024658  nop
0x180024659  jmp     loc_1800244A5
0x18002465e  mov     rcx, [rbp+ppstm]
0x180024662  mov     rdx, rsi
0x180024665  mov     rax, [rcx]
0x180024668  xor     r9d, r9d
0x18002466b  xor     r8d, r8d
0x18002466e  mov     rax, [rax+28h]
0x180024672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024677  mov     ebx, eax
0x180024679  test    eax, eax
0x18002467b  jns     short loc_1800246CF
0x18002467d  mov     rcx, [rbp+18h]; this
0x180024681  mov     r9d, eax; char *
0x180024684  lea     r8, aMincoreTextinp_1; "mincore\\textinput\\dev\\mtf\\internal"...
0x18002468b  mov     edx, 37h ; '7'; void *
0x180024690  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024695  nop
0x180024696  mov     rcx, [rbp+ppstm]
0x18002469a  mov     [rbp+ppstm], rsi
0x18002469e  test    rcx, rcx
0x1800246a1  jz      short loc_1800246B0
0x1800246a3  mov     rax, [rcx]
0x1800246a6  mov     rax, [rax+10h]
0x1800246aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800246af  nop
0x1800246b0  mov     rcx, [rbp+var_30]
0x1800246b4  mov     [rbp+var_30], rsi
0x1800246b8  test    rcx, rcx
0x1800246bb  jz      short loc_1800246CA
0x1800246bd  mov     rax, [rcx]
0x1800246c0  mov     rax, [rax+10h]
0x1800246c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800246c9  nop
0x1800246ca  jmp     loc_1800244A5
0x1800246cf  mov     rax, [rbp+ppstm]
0x1800246d3  mov     [rdi], rax
0x1800246d6  mov     [rbp+ppstm], rsi
0x1800246da  mov     rcx, [rbp+var_30]
0x1800246de  test    rcx, rcx
0x1800246e1  mov     [rbp+var_30], rsi
0x1800246e5  jz      short loc_1800246F4
0x1800246e7  mov     rax, [rcx]
0x1800246ea  mov     rax, [rax+10h]
0x1800246ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800246f3  nop
0x1800246f4  xor     eax, eax
0x1800246f6  mov     rcx, [rbp+var_8]
0x1800246fa  xor     rcx, rsp; StackCookie
0x1800246fd  call    __security_check_cookie
0x180024702  mov     rbx, [rsp+60h+arg_10]
0x18002470a  add     rsp, 60h
0x18002470e  pop     rdi
0x18002470f  pop     rsi
0x180024710  pop     rbp
0x180024711  retn
```
