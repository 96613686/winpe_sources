# BGetOemInterface

- ea: `0x180022d54`
- end: `0x180023114`
- name: `BGetOemInterface`
- size: `960`
- prototype: `__int64 __fastcall(__int64, GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003148c`

## callees

- `0x180001ae4`
- `0x180022d54`
- `0x180023190`
- `0x18005f010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180022d9b`
- `KERNEL32!GetProcAddress` at `0x180022ea0`
- `KERNEL32!GetProcAddress` at `0x180022d9b`
- `KERNEL32!GetProcAddress` at `0x180022ea0`

## string_xrefs

- `0x180022d94`: `DllGetClassObject`
- `0x180022e99`: `PrintVerifierCreatePluginInterfaceWrapper`

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
  __int64 v26; // [rsp+A0h] [rbp+58h] BYREF
  __int64 v27; // [rsp+A8h] [rbp+60h] BYREF

  v3 = 0;
  v4 = -2147467259;
  v26 = 0;
  v24[0] = 0;
  v27 = 0;
  if ( *(_QWORD *)&a2[2].Data1 )
  {
    ProcAddress = GetProcAddress(*(HMODULE *)&a2[2].Data1, "DllGetClassObject");
    if ( ProcAddress )
    {
      v4 = ((__int64 (__fastcall *)(GUID *, GUID *, __int64 *))ProcAddress)(&CLSID_OEMRENDER, &IID_IClassFactory, &v27);
      if ( v4 >= 0 )
      {
        if ( !v27 )
          return 0;
        v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v27 + 24LL))(
               v27,
               0,
               &IID_IUnknown,
               &v26);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      }
    }
    v3 = v26;
  }
  if ( v4 >= 0 && v3 )
  {
    v6 = 0;
    v7 = 0;
    while ( 1 )
    {
      v8 = off_1800738E0[v6];
      if ( !v8 )
        break;
      if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v3)(v3, v8, v24) >= 0 && v24[0] )
      {
        v3 = v26;
        v7 = 1;
        break;
      }
      v3 = v26;
      ++v6;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    if ( v7 )
    {
      v9 = ghPrintVerifierModule;
      v10 = v24[0];
      a2[5] = *off_1800738E0[v6];
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
      HComOEMGetInfo((__int64)a2, 5u);
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
        v17 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *))(**(_QWORD **)a2[4].Data4 + 80LL))(
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
0x180022d54  mov     [rsp-40h+arg_0], rcx
0x180022d59  push    rbp
0x180022d5a  push    rbx
0x180022d5b  push    rsi
0x180022d5c  push    rdi
0x180022d5d  push    r12
0x180022d5f  push    r13
0x180022d61  push    r14
0x180022d63  push    r15
0x180022d65  mov     rbp, rsp
0x180022d68  sub     rsp, 48h
0x180022d6c  xor     r12d, r12d
0x180022d6f  mov     r14, rdx
0x180022d72  mov     ecx, r12d
0x180022d75  mov     [rbp+arg_8], r12d
0x180022d79  mov     ebx, 80004005h
0x180022d7e  mov     [rbp+arg_10], rcx
0x180022d82  mov     [rbp+var_18], r12
0x180022d86  mov     [rbp+arg_18], r12
0x180022d8a  cmp     [rdx+20h], r12
0x180022d8e  jz      short loc_180022E05
0x180022d90  mov     rcx, [r14+20h]; hModule
0x180022d94  lea     rdx, aDllgetclassobj; "DllGetClassObject"
0x180022d9b  call    cs:__imp_GetProcAddress
0x180022da2  nop     dword ptr [rax+rax+00h]
0x180022da7  test    rax, rax
0x180022daa  jz      short loc_180022E01
0x180022dac  lea     r8, [rbp+arg_18]
0x180022db0  lea     rdx, IID_IClassFactory
0x180022db7  lea     rcx, CLSID_OEMRENDER
0x180022dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022dc3  mov     ebx, eax
0x180022dc5  test    eax, eax
0x180022dc7  js      short loc_180022E01
0x180022dc9  mov     rcx, [rbp+arg_18]
0x180022dcd  test    rcx, rcx
0x180022dd0  jz      loc_180023100
0x180022dd6  mov     rax, [rcx]
0x180022dd9  lea     r9, [rbp+arg_10]
0x180022ddd  lea     r8, IID_IUnknown
0x180022de4  xor     edx, edx
0x180022de6  mov     rax, [rax+18h]
0x180022dea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022def  mov     rcx, [rbp+arg_18]
0x180022df3  mov     ebx, eax
0x180022df5  mov     rdx, [rcx]
0x180022df8  mov     rax, [rdx+10h]
0x180022dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e01  mov     rcx, [rbp+arg_10]
0x180022e05  test    ebx, ebx
0x180022e07  js      loc_180023100
0x180022e0d  test    rcx, rcx
0x180022e10  jz      loc_180023100
0x180022e16  mov     ebx, r12d
0x180022e19  lea     rsi, off_1800738E0
0x180022e20  mov     edi, r12d
0x180022e23  movsxd  rax, ebx
0x180022e26  mov     rdx, [rsi+rax*8]
0x180022e2a  test    rdx, rdx
0x180022e2d  jz      short loc_180022E59
0x180022e2f  mov     rax, [rcx]
0x180022e32  lea     r8, [rbp+var_18]
0x180022e36  mov     rax, [rax]
0x180022e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e3e  test    eax, eax
0x180022e40  js      short loc_180022E48
0x180022e42  cmp     [rbp+var_18], r12
0x180022e46  jnz     short loc_180022E50
0x180022e48  mov     rcx, [rbp+arg_10]
0x180022e4c  inc     ebx
0x180022e4e  jmp     short loc_180022E23
0x180022e50  mov     rcx, [rbp+arg_10]
0x180022e54  mov     edi, 1
0x180022e59  mov     rax, [rcx]
0x180022e5c  mov     rax, [rax+10h]
0x180022e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e65  test    edi, edi
0x180022e67  jz      loc_180023100
0x180022e6d  mov     rcx, cs:ghPrintVerifierModule; hModule
0x180022e74  mov     rdi, [rbp+var_18]
0x180022e78  movsxd  rax, ebx
0x180022e7b  mov     rax, [rsi+rax*8]
0x180022e7f  movups  xmm0, xmmword ptr [rax]
0x180022e82  movdqu  xmmword ptr [r14+50h], xmm0
0x180022e88  test    rcx, rcx
0x180022e8b  jz      short loc_180022ED6
0x180022e8d  cmp     cs:gbPrintVerifierDriverLayerEnabled, r12d
0x180022e94  jz      short loc_180022ED6
0x180022e96  mov     rbx, [r14]
0x180022e99  lea     rdx, aPrintverifierc; "PrintVerifierCreatePluginInterfaceWrapp"...
0x180022ea0  call    cs:__imp_GetProcAddress
0x180022ea7  nop     dword ptr [rax+rax+00h]
0x180022eac  lea     rsi, [r14+48h]
0x180022eb0  test    rax, rax
0x180022eb3  jz      short loc_180022EDA
0x180022eb5  lea     r9, [r14+50h]
0x180022eb9  mov     [rsp+48h+var_28], rsi
0x180022ebe  lea     r8, CLSID_OEMRENDER
0x180022ec5  mov     rdx, rdi
0x180022ec8  mov     rcx, rbx
0x180022ecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ed0  test    eax, eax
0x180022ed2  jns     short loc_180022EDD
0x180022ed4  jmp     short loc_180022EDA
0x180022ed6  lea     rsi, [r14+48h]
0x180022eda  mov     [rsi], rdi
0x180022edd  mov     r9d, 4
0x180022ee3  lea     rax, [rbp+arg_8]
0x180022ee7  lea     r8, [r14+60h]
0x180022eeb  mov     [rsp+48h+var_28], rax
0x180022ef0  mov     rcx, r14
0x180022ef3  lea     edx, [r9+1]
0x180022ef7  call    HComOEMGetInfo
0x180022efc  mov     r15d, 2
0x180022f02  mov     rbx, rsi
0x180022f05  mov     ecx, r15d
0x180022f08  sub     ecx, 1
0x180022f0b  jz      short loc_180022F49
0x180022f0d  cmp     ecx, 1
0x180022f10  jnz     loc_1800230EE
0x180022f16  mov     ecx, 10h; Size
0x180022f1b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022f20  mov     rdi, rax
0x180022f23  test    rax, rax
0x180022f26  jz      short loc_180022F38
0x180022f28  lea     rax, ??_7CPrintCorePS2@@6B@; const CPrintCorePS2::`vftable'
0x180022f2f  mov     [rdi+8], r12d
0x180022f33  mov     [rdi], rax
0x180022f36  jmp     short loc_180022F3B
0x180022f38  mov     rdi, r12
0x180022f3b  mov     rbx, rsi
0x180022f3e  test    rdi, rdi
0x180022f41  jz      loc_1800230EE
0x180022f47  jmp     short loc_180022F6D
0x180022f49  mov     ecx, 10h; Size
0x180022f4e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022f53  mov     rdi, rax
0x180022f56  test    rax, rax
0x180022f59  jz      loc_1800230E6
0x180022f5f  lea     rax, ??_7CPrintOemDriverPS@@6B@; const CPrintOemDriverPS::`vftable'
0x180022f66  mov     [rdi+8], r12d
0x180022f6a  mov     [rdi], rax
0x180022f6d  mov     rax, [rdi]
0x180022f70  mov     rcx, rdi
0x180022f73  mov     rax, [rax+8]
0x180022f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f7c  lea     rbx, [r14+48h]
0x180022f80  mov     rdx, rdi
0x180022f83  mov     rcx, [rbx]
0x180022f86  mov     rax, [rcx]
0x180022f89  mov     rax, [rax+50h]
0x180022f8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f92  mov     rdx, [rdi]
0x180022f95  mov     r12d, eax
0x180022f98  mov     rcx, rdi
0x180022f9b  mov     rax, [rdx+10h]
0x180022f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022fa4  test    r12d, r12d
0x180022fa7  jns     short loc_180022FB9
0x180022fa9  dec     r15d
0x180022fac  test    r15d, r15d
0x180022faf  jle     short loc_180022FB9
0x180022fb1  xor     r12d, r12d
0x180022fb4  jmp     loc_180022F05
0x180022fb9  mov     rdi, [rbp+arg_0]
0x180022fbd  test    rdi, rdi
0x180022fc0  jz      loc_1800230DA
0x180022fc6  test    byte ptr [r14+60h], 1
0x180022fcb  jz      loc_1800230DA
0x180022fd1  mov     ecx, 4B8h; Size
0x180022fd6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022fdb  xor     r12d, r12d
0x180022fde  mov     rcx, rax
0x180022fe1  test    rax, rax
0x180022fe4  jz      loc_180023092
0x180022fea  mov     [rax+8], rdi
0x180022fee  lea     rax, ?PScriptFuncs@@3U_PrintCoreConfigFuncs@@A; _PrintCoreConfigFuncs PScriptFuncs
0x180022ff5  mov     [rcx+10h], rax
0x180022ff9  mov     [rcx+18h], r12
0x180022ffd  mov     [rcx+20h], r12d
0x180023001  mov     [rcx+428h], r12
0x180023008  mov     [rcx+448h], r12d
0x18002300f  mov     [rcx+450h], r12
0x180023016  mov     [rcx+430h], rax
0x18002301d  lea     rax, ??_7CPrintCoreHelperPS@@6BCPrintAbstractHelper@@@; const CPrintCoreHelperPS::`vftable'{for `CPrintAbstractHelper'}
0x180023024  mov     [rcx], rax
0x180023027  lea     rax, ??_7CPrintCoreHelperPS@@6BIPrintCoreHelperPS@@@; const CPrintCoreHelperPS::`vftable'{for `IPrintCoreHelperPS'}
0x18002302e  mov     [rcx+478h], rax
0x180023035  mov     [rcx+438h], r12
0x18002303c  mov     [rcx+440h], r12
0x180023043  mov     [rcx+458h], r12
0x18002304a  mov     [rcx+460h], r12d
0x180023051  mov     [rcx+468h], r12
0x180023058  mov     [rcx+470h], r12
0x18002305f  mov     [rcx+480h], r12
0x180023066  mov     [rcx+488h], r12d
0x18002306d  mov     [rcx+490h], r12
0x180023074  mov     [rcx+498h], r12d
0x18002307b  mov     [rcx+4A0h], r12
0x180023082  mov     [rcx+4A8h], r12d
0x180023089  mov     [rcx+4B0h], r12
0x180023090  jmp     short loc_180023095
0x180023092  mov     rcx, r12
0x180023095  lea     rax, [rcx+478h]
0x18002309c  neg     rcx
0x18002309f  sbb     rdi, rdi
0x1800230a2  and     rdi, rax
0x1800230a5  jz      short loc_1800230EE
0x1800230a7  mov     rax, [rdi]
0x1800230aa  mov     rcx, rdi
0x1800230ad  mov     rax, [rax+8]
0x1800230b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230b6  mov     rcx, [rbx]
0x1800230b9  mov     rdx, rdi
0x1800230bc  mov     rax, [rcx]
0x1800230bf  mov     rax, [rax+50h]
0x1800230c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230c8  mov     r12d, eax
0x1800230cb  mov     rcx, rdi
0x1800230ce  mov     rax, [rdi]
0x1800230d1  mov     rax, [rax+10h]
0x1800230d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230da  test    r12d, r12d
0x1800230dd  js      short loc_1800230EB
0x1800230df  mov     eax, 1
0x1800230e4  jmp     short loc_180023102
0x1800230e6  mov     rbx, rsi
0x1800230e9  jmp     short loc_1800230EE
0x1800230eb  xor     r12d, r12d
0x1800230ee  mov     rcx, [rbx]
0x1800230f1  mov     rax, [rcx]
0x1800230f4  mov     rax, [rax+10h]
0x1800230f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230fd  mov     [rbx], r12
0x180023100  xor     eax, eax
0x180023102  add     rsp, 48h
0x180023106  pop     r15
0x180023108  pop     r14
0x18002310a  pop     r13
0x18002310c  pop     r12
0x18002310e  pop     rdi
0x18002310f  pop     rsi
0x180023110  pop     rbx
0x180023111  pop     rbp
0x180023112  retn
```
