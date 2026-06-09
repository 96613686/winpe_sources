# BGetOemInterface

- ea: `0x180022024`
- end: `0x1800223d7`
- name: `BGetOemInterface`
- size: `947`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002fea0`

## callees

- `0x180001aa4`
- `0x180022024`
- `0x180022454`
- `0x18005d010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002206b`
- `KERNEL32!GetProcAddress` at `0x18002216a`
- `KERNEL32!GetProcAddress` at `0x18002206b`
- `KERNEL32!GetProcAddress` at `0x18002216a`

## string_xrefs

- `0x180022064`: `DllGetClassObject`
- `0x180022163`: `PrintVerifierCreatePluginInterfaceWrapper`

## pseudocode

```c
__int64 __fastcall BGetOemInterface(__int64 a1, GUID *a2)
{
  __int64 v3; // rcx
  int v4; // ebx
  FARPROC ProcAddress; // rax
  int v6; // ebx
  int v7; // edi
  GUID *v8; // rdx
  HMODULE v9; // rcx
  __int64 v10; // rdi
  __int64 v11; // rbx
  FARPROC v12; // rax
  unsigned __int8 *Data4; // rsi
  int v14; // r15d
  unsigned __int8 *v15; // rbx
  _DWORD *v16; // rdi
  int v17; // r12d
  _QWORD *v18; // rax
  __int64 v19; // rcx
  unsigned __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rdi
  __int64 v24[3]; // [rsp+30h] [rbp-18h] BYREF
  int v26; // [rsp+98h] [rbp+50h] BYREF
  __int64 v27; // [rsp+A0h] [rbp+58h] BYREF
  __int64 v28; // [rsp+A8h] [rbp+60h] BYREF

  v3 = 0;
  v26 = 0;
  v4 = -2147467259;
  v27 = 0;
  v24[0] = 0;
  v28 = 0;
  if ( *(_QWORD *)&a2[2].Data1 )
  {
    ProcAddress = GetProcAddress(*(HMODULE *)&a2[2].Data1, "DllGetClassObject");
    if ( ProcAddress )
    {
      v4 = ((__int64 (__fastcall *)(GUID *, GUID *, __int64 *))ProcAddress)(&CLSID_OEMRENDER, &IID_IClassFactory, &v28);
      if ( v4 >= 0 )
      {
        if ( !v28 )
          return 0;
        v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v28 + 24LL))(
               v28,
               0,
               &IID_IUnknown,
               &v27);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      }
    }
    v3 = v27;
  }
  if ( v4 >= 0 && v3 )
  {
    v6 = 0;
    v7 = 0;
    while ( 1 )
    {
      v8 = off_1800718E0[v6];
      if ( !v8 )
        break;
      if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v3)(v3, v8, v24) >= 0 && v24[0] )
      {
        v3 = v27;
        v7 = 1;
        break;
      }
      v3 = v27;
      ++v6;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    if ( v7 )
    {
      v9 = ghPrintVerifierModule;
      v10 = v24[0];
      a2[5] = *off_1800718E0[v6];
      if ( v9 && gbPrintVerifierDriverLayerEnabled )
      {
        v11 = *(_QWORD *)&a2->Data1;
        v12 = GetProcAddress(v9, "PrintVerifierCreatePluginInterfaceWrapper");
        Data4 = a2[4].Data4;
        if ( v12
          && ((int (__fastcall *)(__int64, __int64, GUID *, GUID *, unsigned __int8 *))v12)(
               v11,
               v10,
               &CLSID_OEMRENDER,
               &a2[5],
               a2[4].Data4) >= 0 )
        {
          goto LABEL_23;
        }
      }
      else
      {
        Data4 = a2[4].Data4;
      }
      *(_QWORD *)Data4 = v10;
LABEL_23:
      HComOEMGetInfo((_DWORD)a2, 5, (_DWORD)a2 + 96, 4, (__int64)&v26);
      v14 = 2;
      v15 = Data4;
      do
      {
        if ( v14 == 1 )
        {
          v16 = operator new(0x10u);
          if ( !v16 )
          {
            v15 = Data4;
            goto LABEL_45;
          }
          v16[2] = 0;
          *(_QWORD *)v16 = &CPrintOemDriverPS::`vftable';
        }
        else
        {
          if ( v14 != 2 )
            goto LABEL_45;
          v16 = operator new(0x10u);
          if ( v16 )
          {
            v16[2] = 0;
            *(_QWORD *)v16 = &CPrintCorePS2::`vftable';
          }
          else
          {
            v16 = 0;
          }
          v15 = Data4;
          if ( !v16 )
            goto LABEL_45;
        }
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v16 + 8LL))(v16);
        v15 = a2[4].Data4;
        v17 = (*(__int64 (__fastcall **)(__int64, _DWORD *))(**(_QWORD **)a2[4].Data4 + 80LL))(
                *(_QWORD *)a2[4].Data4,
                v16);
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v16 + 16LL))(v16);
        if ( v17 >= 0 )
          break;
        --v14;
      }
      while ( v14 > 0 );
      if ( a1 && (a2[6].Data1 & 1) != 0 )
      {
        v18 = operator new(0x4B8u);
        v19 = (__int64)v18;
        if ( v18 )
        {
          v18[1] = a1;
          v18[2] = &PScriptFuncs;
          v18[3] = 0;
          *((_DWORD *)v18 + 8) = 0;
          v18[133] = 0;
          *((_DWORD *)v18 + 274) = 0;
          v18[138] = 0;
          v18[134] = &PScriptFuncs;
          *v18 = &CPrintCoreHelperPS::`vftable'{for `CPrintAbstractHelper'};
          v18[143] = &CPrintCoreHelperPS::`vftable'{for `IPrintCoreHelperPS'};
          v18[135] = 0;
          v18[136] = 0;
          v18[139] = 0;
          *((_DWORD *)v18 + 280) = 0;
          v18[141] = 0;
          v18[142] = 0;
          v18[144] = 0;
          *((_DWORD *)v18 + 290) = 0;
          v18[146] = 0;
          *((_DWORD *)v18 + 294) = 0;
          v18[148] = 0;
          *((_DWORD *)v18 + 298) = 0;
          v18[150] = 0;
        }
        else
        {
          v19 = 0;
        }
        v20 = v19 + 1144;
        v21 = -v19;
        v22 = v20 & -(__int64)(v21 != 0);
        if ( !v22 )
        {
LABEL_45:
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v15 + 16LL))(*(_QWORD *)v15);
          *(_QWORD *)v15 = 0;
          return 0;
        }
        (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v22 + 8LL))(v20 & -(__int64)(v21 != 0));
        v17 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v15 + 80LL))(*(_QWORD *)v15, v22);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
      if ( v17 >= 0 )
        return 1;
      goto LABEL_45;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180022024  mov     [rsp-40h+arg_0], rcx
0x180022029  push    rbp
0x18002202a  push    rbx
0x18002202b  push    rsi
0x18002202c  push    rdi
0x18002202d  push    r12
0x18002202f  push    r13
0x180022031  push    r14
0x180022033  push    r15
0x180022035  mov     rbp, rsp
0x180022038  sub     rsp, 48h
0x18002203c  xor     r12d, r12d
0x18002203f  mov     r14, rdx
0x180022042  mov     ecx, r12d
0x180022045  mov     [rbp+arg_8], r12d
0x180022049  mov     ebx, 80004005h
0x18002204e  mov     [rbp+arg_10], rcx
0x180022052  mov     [rbp+var_18], r12
0x180022056  mov     [rbp+arg_18], r12
0x18002205a  cmp     [rdx+20h], r12
0x18002205e  jz      short loc_1800220CF
0x180022060  mov     rcx, [r14+20h]; hModule
0x180022064  lea     rdx, aDllgetclassobj; "DllGetClassObject"
0x18002206b  call    cs:__imp_GetProcAddress
0x180022071  test    rax, rax
0x180022074  jz      short loc_1800220CB
0x180022076  lea     r8, [rbp+arg_18]
0x18002207a  lea     rdx, IID_IClassFactory
0x180022081  lea     rcx, CLSID_OEMRENDER
0x180022088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002208d  mov     ebx, eax
0x18002208f  test    eax, eax
0x180022091  js      short loc_1800220CB
0x180022093  mov     rcx, [rbp+arg_18]
0x180022097  test    rcx, rcx
0x18002209a  jz      loc_1800223C4
0x1800220a0  mov     rax, [rcx]
0x1800220a3  lea     r9, [rbp+arg_10]
0x1800220a7  lea     r8, IID_IUnknown
0x1800220ae  xor     edx, edx
0x1800220b0  mov     rax, [rax+18h]
0x1800220b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220b9  mov     rcx, [rbp+arg_18]
0x1800220bd  mov     ebx, eax
0x1800220bf  mov     rdx, [rcx]
0x1800220c2  mov     rax, [rdx+10h]
0x1800220c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220cb  mov     rcx, [rbp+arg_10]
0x1800220cf  test    ebx, ebx
0x1800220d1  js      loc_1800223C4
0x1800220d7  test    rcx, rcx
0x1800220da  jz      loc_1800223C4
0x1800220e0  mov     ebx, r12d
0x1800220e3  lea     rsi, off_1800718E0
0x1800220ea  mov     edi, r12d
0x1800220ed  movsxd  rax, ebx
0x1800220f0  mov     rdx, [rsi+rax*8]
0x1800220f4  test    rdx, rdx
0x1800220f7  jz      short loc_180022123
0x1800220f9  mov     rax, [rcx]
0x1800220fc  lea     r8, [rbp+var_18]
0x180022100  mov     rax, [rax]
0x180022103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022108  test    eax, eax
0x18002210a  js      short loc_180022112
0x18002210c  cmp     [rbp+var_18], r12
0x180022110  jnz     short loc_18002211A
0x180022112  mov     rcx, [rbp+arg_10]
0x180022116  inc     ebx
0x180022118  jmp     short loc_1800220ED
0x18002211a  mov     rcx, [rbp+arg_10]
0x18002211e  mov     edi, 1
0x180022123  mov     rax, [rcx]
0x180022126  mov     rax, [rax+10h]
0x18002212a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002212f  test    edi, edi
0x180022131  jz      loc_1800223C4
0x180022137  mov     rcx, cs:ghPrintVerifierModule; hModule
0x18002213e  mov     rdi, [rbp+var_18]
0x180022142  movsxd  rax, ebx
0x180022145  mov     rax, [rsi+rax*8]
0x180022149  movups  xmm0, xmmword ptr [rax]
0x18002214c  movdqu  xmmword ptr [r14+50h], xmm0
0x180022152  test    rcx, rcx
0x180022155  jz      short loc_18002219A
0x180022157  cmp     cs:gbPrintVerifierDriverLayerEnabled, r12d
0x18002215e  jz      short loc_18002219A
0x180022160  mov     rbx, [r14]
0x180022163  lea     rdx, aPrintverifierc; "PrintVerifierCreatePluginInterfaceWrapp"...
0x18002216a  call    cs:__imp_GetProcAddress
0x180022170  lea     rsi, [r14+48h]
0x180022174  test    rax, rax
0x180022177  jz      short loc_18002219E
0x180022179  lea     r9, [r14+50h]
0x18002217d  mov     [rsp+48h+var_28], rsi
0x180022182  lea     r8, CLSID_OEMRENDER
0x180022189  mov     rdx, rdi
0x18002218c  mov     rcx, rbx
0x18002218f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022194  test    eax, eax
0x180022196  jns     short loc_1800221A1
0x180022198  jmp     short loc_18002219E
0x18002219a  lea     rsi, [r14+48h]
0x18002219e  mov     [rsi], rdi
0x1800221a1  mov     r9d, 4
0x1800221a7  lea     rax, [rbp+arg_8]
0x1800221ab  lea     r8, [r14+60h]
0x1800221af  mov     [rsp+48h+var_28], rax
0x1800221b4  mov     rcx, r14
0x1800221b7  lea     edx, [r9+1]
0x1800221bb  call    HComOEMGetInfo
0x1800221c0  mov     r15d, 2
0x1800221c6  mov     rbx, rsi
0x1800221c9  mov     ecx, r15d
0x1800221cc  sub     ecx, 1
0x1800221cf  jz      short loc_18002220D
0x1800221d1  cmp     ecx, 1
0x1800221d4  jnz     loc_1800223B2
0x1800221da  mov     ecx, 10h; Size
0x1800221df  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800221e4  mov     rdi, rax
0x1800221e7  test    rax, rax
0x1800221ea  jz      short loc_1800221FC
0x1800221ec  lea     rax, ??_7CPrintCorePS2@@6B@; const CPrintCorePS2::`vftable'
0x1800221f3  mov     [rdi+8], r12d
0x1800221f7  mov     [rdi], rax
0x1800221fa  jmp     short loc_1800221FF
0x1800221fc  mov     rdi, r12
0x1800221ff  mov     rbx, rsi
0x180022202  test    rdi, rdi
0x180022205  jz      loc_1800223B2
0x18002220b  jmp     short loc_180022231
0x18002220d  mov     ecx, 10h; Size
0x180022212  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022217  mov     rdi, rax
0x18002221a  test    rax, rax
0x18002221d  jz      loc_1800223AA
0x180022223  lea     rax, ??_7CPrintOemDriverPS@@6B@; const CPrintOemDriverPS::`vftable'
0x18002222a  mov     [rdi+8], r12d
0x18002222e  mov     [rdi], rax
0x180022231  mov     rax, [rdi]
0x180022234  mov     rcx, rdi
0x180022237  mov     rax, [rax+8]
0x18002223b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022240  lea     rbx, [r14+48h]
0x180022244  mov     rdx, rdi
0x180022247  mov     rcx, [rbx]
0x18002224a  mov     rax, [rcx]
0x18002224d  mov     rax, [rax+50h]
0x180022251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022256  mov     rdx, [rdi]
0x180022259  mov     r12d, eax
0x18002225c  mov     rcx, rdi
0x18002225f  mov     rax, [rdx+10h]
0x180022263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022268  test    r12d, r12d
0x18002226b  jns     short loc_18002227D
0x18002226d  dec     r15d
0x180022270  test    r15d, r15d
0x180022273  jle     short loc_18002227D
0x180022275  xor     r12d, r12d
0x180022278  jmp     loc_1800221C9
0x18002227d  mov     rdi, [rbp+arg_0]
0x180022281  test    rdi, rdi
0x180022284  jz      loc_18002239E
0x18002228a  test    byte ptr [r14+60h], 1
0x18002228f  jz      loc_18002239E
0x180022295  mov     ecx, 4B8h; Size
0x18002229a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002229f  xor     r12d, r12d
0x1800222a2  mov     rcx, rax
0x1800222a5  test    rax, rax
0x1800222a8  jz      loc_180022356
0x1800222ae  mov     [rax+8], rdi
0x1800222b2  lea     rax, ?PScriptFuncs@@3U_PrintCoreConfigFuncs@@A; _PrintCoreConfigFuncs PScriptFuncs
0x1800222b9  mov     [rcx+10h], rax
0x1800222bd  mov     [rcx+18h], r12
0x1800222c1  mov     [rcx+20h], r12d
0x1800222c5  mov     [rcx+428h], r12
0x1800222cc  mov     [rcx+448h], r12d
0x1800222d3  mov     [rcx+450h], r12
0x1800222da  mov     [rcx+430h], rax
0x1800222e1  lea     rax, ??_7CPrintCoreHelperPS@@6BCPrintAbstractHelper@@@; const CPrintCoreHelperPS::`vftable'{for `CPrintAbstractHelper'}
0x1800222e8  mov     [rcx], rax
0x1800222eb  lea     rax, ??_7CPrintCoreHelperPS@@6BIPrintCoreHelperPS@@@; const CPrintCoreHelperPS::`vftable'{for `IPrintCoreHelperPS'}
0x1800222f2  mov     [rcx+478h], rax
0x1800222f9  mov     [rcx+438h], r12
0x180022300  mov     [rcx+440h], r12
0x180022307  mov     [rcx+458h], r12
0x18002230e  mov     [rcx+460h], r12d
0x180022315  mov     [rcx+468h], r12
0x18002231c  mov     [rcx+470h], r12
0x180022323  mov     [rcx+480h], r12
0x18002232a  mov     [rcx+488h], r12d
0x180022331  mov     [rcx+490h], r12
0x180022338  mov     [rcx+498h], r12d
0x18002233f  mov     [rcx+4A0h], r12
0x180022346  mov     [rcx+4A8h], r12d
0x18002234d  mov     [rcx+4B0h], r12
0x180022354  jmp     short loc_180022359
0x180022356  mov     rcx, r12
0x180022359  lea     rax, [rcx+478h]
0x180022360  neg     rcx
0x180022363  sbb     rdi, rdi
0x180022366  and     rdi, rax
0x180022369  jz      short loc_1800223B2
0x18002236b  mov     rax, [rdi]
0x18002236e  mov     rcx, rdi
0x180022371  mov     rax, [rax+8]
0x180022375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002237a  mov     rcx, [rbx]
0x18002237d  mov     rdx, rdi
0x180022380  mov     rax, [rcx]
0x180022383  mov     rax, [rax+50h]
0x180022387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002238c  mov     r12d, eax
0x18002238f  mov     rcx, rdi
0x180022392  mov     rax, [rdi]
0x180022395  mov     rax, [rax+10h]
0x180022399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002239e  test    r12d, r12d
0x1800223a1  js      short loc_1800223AF
0x1800223a3  mov     eax, 1
0x1800223a8  jmp     short loc_1800223C6
0x1800223aa  mov     rbx, rsi
0x1800223ad  jmp     short loc_1800223B2
0x1800223af  xor     r12d, r12d
0x1800223b2  mov     rcx, [rbx]
0x1800223b5  mov     rax, [rcx]
0x1800223b8  mov     rax, [rax+10h]
0x1800223bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223c1  mov     [rbx], r12
0x1800223c4  xor     eax, eax
0x1800223c6  add     rsp, 48h
0x1800223ca  pop     r15
0x1800223cc  pop     r14
0x1800223ce  pop     r13
0x1800223d0  pop     r12
0x1800223d2  pop     rdi
0x1800223d3  pop     rsi
0x1800223d4  pop     rbx
0x1800223d5  pop     rbp
0x1800223d6  retn
```
