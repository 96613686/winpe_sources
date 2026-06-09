# SystemStoreLite::GetCurrentUserSidString(IExecutionContextLite *,ushort * *)

- ea: `0x180024d24`
- end: `0x1800250e6`
- name: `?GetCurrentUserSidString@SystemStoreLite@@SAJPEAVIExecutionContextLite@@PEAPEAG@Z`
- size: `962`
- prototype: `__int64 __fastcall(struct IExecutionContextLite *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x180024bf0`
- `0x180025aa4`

## callees

- `0x180008440`
- `0x18000baac`
- `0x18000d91c`
- `0x18000def8`
- `0x1800120e0`
- `0x180023b5c`
- `0x180023c04`
- `0x180024d24`
- `0x1800267c0`
- `0x180026c8c`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024f58`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024f58`

## string_xrefs

- `0x18002506a`: `pContext != nullptr && ppSidString != nullptr`
- `0x180024d7d`: `SystemStoreLite::GetCurrentUserSidString`
- `0x180024ec3`: `OpenProcessToken failed. (win32 = 0x%0x)`
- `0x180024e48`: `OpenThreadToken failed. (win32 = 0x%0x)`
- `0x180024f3e`: `OpenProccessToken failed. (win32 = 0x%0x)`
- `0x180024ff8`: `OpenProccessToken failed. (win32 = 0x%0x)`
- `0x180024f07`: `(result = pWinApiFunctions->GetTokenInformation(accessToken, TokenUser, nullptr, 0, &tokenUserLength)) == FALSE`
- `0x180025041`: `ConvertSidToStringSid failed. (win32 = 0x%0x)`

## pseudocode

```c
__int64 __fastcall SystemStoreLite::GetCurrentUserSidString(struct IExecutionContextLite *a1, unsigned __int16 **a2)
{
  __int64 v3; // rbx
  __int64 v4; // rax
  int v5; // eax
  unsigned int v6; // ecx
  const unsigned __int16 *v7; // r9
  unsigned int v8; // r8d
  __int64 v9; // rax
  int v10; // r9d
  const char *v11; // rax
  unsigned int v12; // r8d
  _QWORD *v13; // rdi
  int v14; // eax
  __int64 v15; // r9
  unsigned __int16 *v16; // rax
  unsigned int v17; // ebx
  __int64 v18; // rdx
  int v19; // r8d
  char *v21; // [rsp+20h] [rbp-79h]
  char *v22; // [rsp+20h] [rbp-79h]
  unsigned __int16 *v23; // [rsp+40h] [rbp-59h] BYREF
  __int64 v24; // [rsp+48h] [rbp-51h]
  __int64 v25; // [rsp+50h] [rbp-49h]
  _QWORD v26[3]; // [rsp+58h] [rbp-41h] BYREF
  _QWORD v27[3]; // [rsp+70h] [rbp-29h] BYREF
  int *v28[4]; // [rsp+88h] [rbp-11h] BYREF
  _QWORD v29[9]; // [rsp+A8h] [rbp+Fh] BYREF
  int v30; // [rsp+100h] [rbp+67h] BYREF
  SIZE_T uBytes; // [rsp+110h] [rbp+77h] BYREF

  v3 = (*(__int64 (__fastcall **)(struct IExecutionContextLite *))(*(_QWORD *)a1 + 24LL))(a1);
  v26[0] = 0;
  v26[2] = v3;
  v26[1] = 0;
  LODWORD(uBytes) = 0;
  memset(v27, 0, sizeof(v27));
  v23 = 0;
  v25 = 0;
  v24 = 0;
  v30 = 0;
  v29[0] = "SystemStoreLite::GetCurrentUserSidString";
  v29[1] = &v30;
  v29[2] = 0;
  v29[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
    "SystemStoreLite::GetCurrentUserSidString",
    (const char *)0x162,
    0,
    (const unsigned __int16 *)v21);
  ErrorVerifier::ErrorVerifier(
    (ErrorVerifier *)v28,
    "SystemStoreLite::GetCurrentUserSidString",
    &v30,
    10,
    &qword_180040148);
  if ( !a2 )
  {
    v10 = -2147024809;
    v11 = "pContext != nullptr && ppSidString != nullptr";
    v12 = 359;
    goto LABEL_38;
  }
  *a2 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 80LL))(v3);
  if ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64, __int64, _QWORD *))(*(_QWORD *)v3 + 224LL))(
          v3,
          v4,
          8,
          1,
          v26) )
  {
    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 120LL))(v3);
    if ( v5 != 1008 )
    {
      if ( v5 > 0 )
        v6 = (unsigned __int16)v5 | 0x80070000;
      else
        v6 = v5;
      v7 = L"OpenThreadToken failed. (win32 = 0x%0x)";
      v8 = 373;
      goto LABEL_8;
    }
    v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 88LL))(v3);
    if ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64, _QWORD *))(*(_QWORD *)v3 + 256LL))(v3, v9, 8, v26) )
    {
      v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 120LL))(v3);
      if ( v5 > 0 )
        v6 = (unsigned __int16)v5 | 0x80070000;
      else
        v6 = v5;
      v7 = L"OpenProcessToken failed. (win32 = 0x%0x)";
      v8 = 390;
      goto LABEL_8;
    }
  }
  if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v3 + 144LL))(v3, v26[0], 1) )
  {
    v10 = -2147418113;
    v11 = "(result = pWinApiFunctions->GetTokenInformation(accessToken, TokenUser, nullptr, 0, &tokenUserLength)) == FALSE";
    v12 = 397;
LABEL_38:
    v30 = v10;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
      "SystemStoreLite::GetCurrentUserSidString",
      v12,
      v10,
      v11);
    goto LABEL_39;
  }
  v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 120LL))(v3);
  if ( v5 == 122 )
  {
    v13 = LocalAlloc(0x40u, (unsigned int)uBytes);
    if ( v13 )
    {
      Auto<unsigned char *,LocalAllocFunctor<unsigned char *>,DummyContext>::Clear((__int64)v27);
      v27[0] = v13;
      v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD *, _DWORD, SIZE_T *))(*(_QWORD *)v3 + 144LL))(
              v3,
              v26[0],
              1,
              v13,
              uBytes,
              &uBytes);
      v15 = *(_QWORD *)v3;
      if ( v14 )
      {
        if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, unsigned __int16 **))(v15 + 192))(v3, *v13, &v23) )
        {
          v16 = v23;
          v23 = 0;
          v24 = 0;
          *a2 = v16;
          goto LABEL_39;
        }
        v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 120LL))(v3);
        if ( v5 > 0 )
          v6 = (unsigned __int16)v5 | 0x80070000;
        else
          v6 = v5;
        v7 = L"ConvertSidToStringSid failed. (win32 = 0x%0x)";
        v8 = 444;
      }
      else
      {
        v5 = (*(__int64 (__fastcall **)(__int64))(v15 + 120))(v3);
        if ( v5 > 0 )
          v6 = (unsigned __int16)v5 | 0x80070000;
        else
          v6 = v5;
        v7 = L"OpenProccessToken failed. (win32 = 0x%0x)";
        v8 = 431;
      }
    }
    else
    {
      v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 120LL))(v3);
      if ( v5 > 0 )
        v6 = (unsigned __int16)v5 | 0x80070000;
      else
        v6 = v5;
      v7 = L"LocalAlloc failed. (win32 = 0x%0x)";
      v8 = 413;
    }
  }
  else
  {
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    else
      v6 = v5;
    v7 = L"OpenProccessToken failed. (win32 = 0x%0x)";
    v8 = 403;
  }
LABEL_8:
  LODWORD(v22) = v5;
  v30 = v6;
  TracePrintW(2u, "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp", v8, v7, v22);
LABEL_39:
  v17 = v30;
  ErrorVerifier::CheckAgainstList((PPTraceStatus *)v28[3], *v28[2], (unsigned __int64)v28[1], v28[0]);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v29, v18, v19);
  Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>((__int64)&v23);
  Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>((__int64)v27);
  Auto<void *,HandleFunctor,IWinApiLite>::~Auto<void *,HandleFunctor,IWinApiLite>(v26);
  return v17;
}

```

## disassembly

```asm
0x180024d24  mov     [rsp-8+arg_8], rbx
0x180024d29  push    rbp
0x180024d2a  push    rsi
0x180024d2b  push    rdi
0x180024d2c  push    r14
0x180024d2e  push    r15
0x180024d30  lea     rbp, [rsp-37h]
0x180024d35  sub     rsp, 0D0h
0x180024d3c  mov     rsi, rdx
0x180024d3f  mov     rax, [rcx]
0x180024d42  mov     rax, [rax+18h]
0x180024d46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d4b  mov     rbx, rax
0x180024d4e  xor     r14d, r14d
0x180024d51  mov     [rbp+57h+var_98], r14
0x180024d55  mov     [rbp+57h+var_88], rax
0x180024d59  mov     [rbp+57h+var_90], r14
0x180024d5d  mov     dword ptr [rbp+57h+uBytes], r14d
0x180024d61  mov     [rbp+57h+var_80], r14
0x180024d65  mov     [rbp+57h+var_70], r14
0x180024d69  mov     [rbp+57h+var_78], r14
0x180024d6d  mov     [rbp+57h+var_B0], r14
0x180024d71  mov     [rbp+57h+var_A0], r14
0x180024d75  mov     [rbp+57h+var_A8], r14
0x180024d79  mov     [rbp+57h+arg_0], r14d
0x180024d7d  lea     rdi, aSystemstorelit_2; "SystemStoreLite::GetCurrentUserSidStrin"...
0x180024d84  mov     [rbp+57h+var_48], rdi
0x180024d88  lea     rax, [rbp+57h+arg_0]
0x180024d8c  mov     [rbp+57h+var_40], rax
0x180024d90  mov     [rbp+57h+var_38], r14
0x180024d94  mov     [rbp+57h+var_30], r14
0x180024d98  xor     r9d, r9d; unsigned int
0x180024d9b  mov     r8d, 162h; char *
0x180024da1  mov     rdx, rdi; char *
0x180024da4  lea     r15, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180024dab  mov     rcx, r15; this
0x180024dae  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180024db3  nop
0x180024db4  lea     rax, qword_180040148
0x180024dbb  mov     [rsp+0F0h+var_D0], rax; int *
0x180024dc0  lea     r9d, [r14+0Ah]; unsigned __int64
0x180024dc4  lea     r8, [rbp+57h+arg_0]; int *
0x180024dc8  mov     rdx, rdi; char *
0x180024dcb  lea     rcx, [rbp+57h+var_68]; this
0x180024dcf  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x180024dd4  nop
0x180024dd5  test    rsi, rsi
0x180024dd8  jz      loc_180025064
0x180024dde  mov     [rsi], r14
0x180024de1  mov     rax, [rbx]
0x180024de4  mov     rcx, rbx
0x180024de7  mov     rax, [rax+50h]
0x180024deb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024df0  mov     rcx, [rbx]
0x180024df3  mov     r10, [rcx+0E0h]
0x180024dfa  lea     rcx, [rbp+57h+var_98]
0x180024dfe  mov     [rsp+0F0h+var_D0], rcx
0x180024e03  lea     r9d, [r14+1]
0x180024e07  lea     r8d, [r14+8]
0x180024e0b  mov     rdx, rax
0x180024e0e  mov     rcx, rbx
0x180024e11  mov     rax, r10
0x180024e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e19  test    eax, eax
0x180024e1b  jnz     loc_180024ED2
0x180024e21  mov     rax, [rbx]
0x180024e24  mov     rcx, rbx
0x180024e27  mov     rax, [rax+78h]
0x180024e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e30  cmp     eax, 3F0h
0x180024e35  jz      short loc_180024E6E
0x180024e37  test    eax, eax
0x180024e39  jg      short loc_180024E3F
0x180024e3b  mov     ecx, eax
0x180024e3d  jmp     short loc_180024E48
0x180024e3f  movzx   ecx, ax
0x180024e42  or      ecx, 80070000h
0x180024e48  lea     r9, aOpenthreadtoke; "OpenThreadToken failed. (win32 = 0x%0x)"
0x180024e4f  mov     r8d, 175h; unsigned int
0x180024e55  mov     dword ptr [rsp+0F0h+var_D0], eax
0x180024e59  mov     [rbp+57h+arg_0], ecx
0x180024e5c  mov     rdx, r15; char *
0x180024e5f  mov     ecx, 2; unsigned __int8
0x180024e64  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180024e69  jmp     loc_18002508B
0x180024e6e  mov     rax, [rbx]
0x180024e71  mov     rcx, rbx
0x180024e74  mov     rax, [rax+58h]
0x180024e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e7d  mov     rcx, [rbx]
0x180024e80  mov     r10, [rcx+100h]
0x180024e87  lea     r9, [rbp+57h+var_98]
0x180024e8b  mov     r8d, 8
0x180024e91  mov     rdx, rax
0x180024e94  mov     rcx, rbx
0x180024e97  mov     rax, r10
0x180024e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e9f  test    eax, eax
0x180024ea1  jnz     short loc_180024ED2
0x180024ea3  mov     rax, [rbx]
0x180024ea6  mov     rcx, rbx
0x180024ea9  mov     rax, [rax+78h]
0x180024ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024eb2  test    eax, eax
0x180024eb4  jg      short loc_180024EBA
0x180024eb6  mov     ecx, eax
0x180024eb8  jmp     short loc_180024EC3
0x180024eba  movzx   ecx, ax
0x180024ebd  or      ecx, 80070000h
0x180024ec3  lea     r9, aOpenprocesstok; "OpenProcessToken failed. (win32 = 0x%0x"...
0x180024eca  mov     r8d, 186h
0x180024ed0  jmp     short loc_180024E55
0x180024ed2  mov     rax, [rbx]
0x180024ed5  lea     rcx, [rbp+57h+uBytes]
0x180024ed9  mov     [rsp+0F0h+var_C8], rcx
0x180024ede  mov     dword ptr [rsp+0F0h+var_D0], r14d
0x180024ee3  xor     r9d, r9d
0x180024ee6  lea     r8d, [r9+1]
0x180024eea  mov     rdx, [rbp+57h+var_98]
0x180024eee  mov     rcx, rbx
0x180024ef1  mov     rax, [rax+90h]
0x180024ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024efd  test    eax, eax
0x180024eff  jz      short loc_180024F19
0x180024f01  mov     r9d, 8000FFFFh
0x180024f07  lea     rax, aResultPwinapif; "(result = pWinApiFunctions->GetTokenInf"...
0x180024f0e  mov     r8d, 18Dh
0x180024f14  jmp     loc_180025077
0x180024f19  mov     rax, [rbx]
0x180024f1c  mov     rcx, rbx
0x180024f1f  mov     rax, [rax+78h]
0x180024f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f28  cmp     eax, 7Ah ; 'z'
0x180024f2b  jz      short loc_180024F50
0x180024f2d  test    eax, eax
0x180024f2f  jg      short loc_180024F35
0x180024f31  mov     ecx, eax
0x180024f33  jmp     short loc_180024F3E
0x180024f35  movzx   ecx, ax
0x180024f38  or      ecx, 80070000h
0x180024f3e  lea     r9, aOpenproccessto; "OpenProccessToken failed. (win32 = 0x%0"...
0x180024f45  mov     r8d, 193h
0x180024f4b  jmp     loc_180024E55
0x180024f50  mov     edx, dword ptr [rbp+57h+uBytes]; uBytes
0x180024f53  mov     ecx, 40h ; '@'; uFlags
0x180024f58  call    cs:__imp_LocalAlloc
0x180024f5e  mov     rdi, rax
0x180024f61  test    rax, rax
0x180024f64  jnz     short loc_180024F98
0x180024f66  mov     rax, [rbx]
0x180024f69  mov     rcx, rbx
0x180024f6c  mov     rax, [rax+78h]
0x180024f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f75  test    eax, eax
0x180024f77  jg      short loc_180024F7D
0x180024f79  mov     ecx, eax
0x180024f7b  jmp     short loc_180024F86
0x180024f7d  movzx   ecx, ax
0x180024f80  or      ecx, 80070000h
0x180024f86  lea     r9, aLocalallocFail; "LocalAlloc failed. (win32 = 0x%0x)"
0x180024f8d  mov     r8d, 19Dh
0x180024f93  jmp     loc_180024E55
0x180024f98  lea     rcx, [rbp+57h+var_80]
0x180024f9c  call    ?Clear@?$Auto@PEAEV?$LocalAllocFunctor@PEAE@@VDummyContext@@@@QEAAXXZ; Auto<uchar *,LocalAllocFunctor<uchar *>,DummyContext>::Clear(void)
0x180024fa1  mov     [rbp+57h+var_80], rdi
0x180024fa5  mov     ecx, dword ptr [rbp+57h+uBytes]
0x180024fa8  mov     rax, [rbx]
0x180024fab  lea     rdx, [rbp+57h+uBytes]
0x180024faf  mov     [rsp+0F0h+var_C8], rdx
0x180024fb4  mov     dword ptr [rsp+0F0h+var_D0], ecx
0x180024fb8  mov     r9, rdi
0x180024fbb  mov     r8d, 1
0x180024fc1  mov     rdx, [rbp+57h+var_98]
0x180024fc5  mov     rcx, rbx
0x180024fc8  mov     rax, [rax+90h]
0x180024fcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fd4  mov     r9, [rbx]
0x180024fd7  mov     rcx, rbx
0x180024fda  test    eax, eax
0x180024fdc  jnz     short loc_18002500A
0x180024fde  mov     rax, [r9+78h]
0x180024fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fe7  test    eax, eax
0x180024fe9  jg      short loc_180024FEF
0x180024feb  mov     ecx, eax
0x180024fed  jmp     short loc_180024FF8
0x180024fef  movzx   ecx, ax
0x180024ff2  or      ecx, 80070000h
0x180024ff8  lea     r9, aOpenproccessto; "OpenProccessToken failed. (win32 = 0x%0"...
0x180024fff  mov     r8d, 1AFh
0x180025005  jmp     loc_180024E55
0x18002500a  lea     r8, [rbp+57h+var_B0]
0x18002500e  mov     rdx, [rdi]
0x180025011  mov     rax, [r9+0C0h]
0x180025018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002501d  test    eax, eax
0x18002501f  jnz     short loc_180025053
0x180025021  mov     rax, [rbx]
0x180025024  mov     rcx, rbx
0x180025027  mov     rax, [rax+78h]
0x18002502b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025030  test    eax, eax
0x180025032  jg      short loc_180025038
0x180025034  mov     ecx, eax
0x180025036  jmp     short loc_180025041
0x180025038  movzx   ecx, ax
0x18002503b  or      ecx, 80070000h
0x180025041  lea     r9, aConvertsidtost_0; "ConvertSidToStringSid failed. (win32 = "...
0x180025048  mov     r8d, 1BCh
0x18002504e  jmp     loc_180024E55
0x180025053  mov     rax, [rbp+57h+var_B0]
0x180025057  mov     [rbp+57h+var_B0], r14
0x18002505b  mov     [rbp+57h+var_A8], r14
0x18002505f  mov     [rsi], rax
0x180025062  jmp     short loc_18002508B
0x180025064  mov     r9d, 80070057h; int
0x18002506a  lea     rax, aPcontextNullpt_0; "pContext != nullptr && ppSidString != n"...
0x180025071  mov     r8d, 167h; unsigned int
0x180025077  mov     [rsp+0F0h+var_D0], rax; char *
0x18002507c  mov     [rbp+57h+arg_0], r9d
0x180025080  mov     rdx, rdi; char *
0x180025083  mov     rcx, r15; char *
0x180025086  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18002508b  mov     ebx, [rbp+57h+arg_0]
0x18002508e  mov     r9, [rbp+57h+var_68]; int *
0x180025092  mov     r8, [rbp+57h+var_60]; unsigned __int64
0x180025096  mov     rdx, [rbp+57h+var_58]
0x18002509a  mov     edx, [rdx]; int
0x18002509c  mov     rcx, [rbp+57h+var_50]; char *
0x1800250a0  call    ?CheckAgainstList@ErrorVerifier@@SAXPEBDJ_KPEBJ@Z; ErrorVerifier::CheckAgainstList(char const *,long,unsigned __int64,long const *)
0x1800250a5  nop
0x1800250a6  lea     rcx, [rbp+57h+var_48]
0x1800250aa  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800250af  nop
0x1800250b0  lea     rcx, [rbp+57h+var_B0]
0x1800250b4  call    ??1?$Auto@PEAPEAXV?$LocalAllocFunctor@PEAPEAX@@VDummyContext@@@@QEAA@XZ; Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(void)
0x1800250b9  nop
0x1800250ba  lea     rcx, [rbp+57h+var_80]
0x1800250be  call    ??1?$Auto@PEAPEAXV?$LocalAllocFunctor@PEAPEAX@@VDummyContext@@@@QEAA@XZ; Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(void)
0x1800250c3  nop
0x1800250c4  lea     rcx, [rbp+57h+var_98]
0x1800250c8  call    ??1?$Auto@PEAXVHandleFunctor@@VIWinApiLite@@@@QEAA@XZ; Auto<void *,HandleFunctor,IWinApiLite>::~Auto<void *,HandleFunctor,IWinApiLite>(void)
0x1800250cd  mov     eax, ebx
0x1800250cf  mov     rbx, [rsp+0F0h+arg_8]
0x1800250d7  add     rsp, 0D0h
0x1800250de  pop     r15
0x1800250e0  pop     r14
0x1800250e2  pop     rdi
0x1800250e3  pop     rsi
0x1800250e4  pop     rbp
0x1800250e5  retn
```
