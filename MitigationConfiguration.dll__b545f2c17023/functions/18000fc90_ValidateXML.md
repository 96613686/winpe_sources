# ValidateXML

- ea: `0x18000fc90`
- end: `0x18000fe97`
- name: `ValidateXML`
- size: `519`
- prototype: `__int64 __fastcall(OLECHAR *psz, _BYTE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000fea0`

## callees

- `0x180005db4`
- `0x18000fc90`
- `0x180010438`
- `0x18001044c`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000fcfc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000fcfc`
- `OLEAUT32!__imp_SysAllocString` at `0x18000fdaf`
- `OLEAUT32!__imp_SysAllocString` at `0x18000fdaf`
- `OLEAUT32!__imp_VariantClear` at `0x18000fe0d`
- `OLEAUT32!__imp_VariantClear` at `0x18000fe0d`

## string_xrefs

- `0x18000fcbc`: `onecore\ds\security\exploitguard\dll\mitigationconfiguration.cpp`

## pseudocode

```c
__int64 __fastcall ValidateXML(OLECHAR *psz, _BYTE *a2)
{
  HRESULT Instance; // eax
  struct IUnknown *v6; // rbx
  int v7; // eax
  const struct _GUID *v8; // r8
  struct IUnknown *v9; // rbx
  int v10; // eax
  const struct _GUID *v11; // r8
  struct IUnknown *v12; // rbx
  int v13; // eax
  const struct _GUID *v14; // r8
  struct IUnknown *v15; // rbx
  int v16; // eax
  const struct _GUID *v17; // r8
  bool v18; // bl
  bool v19; // zf
  int ppv; // [rsp+20h] [rbp-50h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-40h] BYREF
  VARIANTARG v22; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  __int16 v24; // [rsp+98h] [rbp+28h] BYREF
  struct IUnknown *v25; // [rsp+A0h] [rbp+30h] BYREF

  if ( a2 )
  {
    *a2 = 0;
    v25 = 0;
    Instance = CoCreateInstance(
                 &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
                 0,
                 1u,
                 &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
                 (LPVOID *)&v25);
    if ( Instance >= 0 )
    {
      v6 = v25;
    }
    else
    {
      v6 = 0;
      v25 = 0;
    }
    if ( !Instance )
    {
      if ( !v6 )
        goto LABEL_23;
      v7 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD))v6->lpVtbl[21].QueryInterface)(v6, 0);
      if ( v7 < 0 )
        _com_issue_errorex(v7, v6, v8);
      v9 = v25;
      if ( !v25 )
        goto LABEL_23;
      v10 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v25->lpVtbl[22].Release)(v25, 0xFFFFFFFFLL);
      if ( v10 < 0 )
        _com_issue_errorex(v10, v9, v11);
      v12 = v25;
      if ( !v25 )
LABEL_23:
        _com_issue_error(-2147467261);
      v13 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v25->lpVtbl[23].AddRef)(v25, 0xFFFFFFFFLL);
      if ( v13 < 0 )
        _com_issue_errorex(v13, v12, v14);
      v15 = v25;
      if ( !v25 )
        _com_issue_error(-2147467261);
      pvarg.vt = 8;
      pvarg.llVal = (LONGLONG)SysAllocString(psz);
      if ( !pvarg.llVal && psz )
        _com_issue_error(-2147024882);
      v24 = 0;
      v22 = pvarg;
      v16 = ((__int64 (__fastcall *)(struct IUnknown *, VARIANTARG *, __int16 *))v15->lpVtbl[19].AddRef)(
              v15,
              &v22,
              &v24);
      if ( v16 < 0 )
        _com_issue_errorex(v16, v15, v17);
      v18 = v24 == -1;
      VariantClear(&pvarg);
      v19 = !v18;
      v6 = v25;
      if ( !v19 )
        *a2 = 1;
    }
    if ( v6 )
      ((void (__fastcall *)(struct IUnknown *))v6->lpVtbl->Release)(v6);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x93,
      (unsigned int)"onecore\\ds\\security\\exploitguard\\dll\\mitigationconfiguration.cpp",
      (const char *)0x80070057LL,
      ppv);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18000fc90  mov     [rsp-18h+arg_0], rbx
0x18000fc95  mov     [rsp-18h+arg_18], rsi
0x18000fc9a  push    rbp
0x18000fc9b  push    rdi
0x18000fc9c  push    r14
0x18000fc9e  mov     rbp, rsp
0x18000fca1  sub     rsp, 70h
0x18000fca5  mov     rdi, rdx
0x18000fca8  mov     rsi, rcx
0x18000fcab  test    rdx, rdx
0x18000fcae  jnz     short loc_18000FCD4
0x18000fcb0  mov     rcx, [rbp+18h]; this
0x18000fcb4  mov     ebx, 80070057h
0x18000fcb9  mov     r9d, ebx; char *
0x18000fcbc  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\exploitguard\\dl"...
0x18000fcc3  mov     edx, 93h; void *
0x18000fcc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fccd  mov     eax, ebx
0x18000fccf  jmp     loc_18000FE35
0x18000fcd4  mov     byte ptr [rdx], 0
0x18000fcd7  mov     [rbp+arg_10], 0
0x18000fcdf  lea     rax, [rbp+arg_10]
0x18000fce3  mov     qword ptr [rsp+70h+ppv], rax; ppv
0x18000fce8  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x18000fcef  xor     edx, edx; pUnkOuter
0x18000fcf1  lea     r8d, [rdx+1]; dwClsContext
0x18000fcf5  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x18000fcfc  call    cs:__imp_CoCreateInstance
0x18000fd02  test    eax, eax
0x18000fd04  jns     short loc_18000FD0E
0x18000fd06  xor     ebx, ebx
0x18000fd08  mov     [rbp+arg_10], rbx
0x18000fd0c  jmp     short loc_18000FD12
0x18000fd0e  mov     rbx, [rbp+arg_10]
0x18000fd12  test    eax, eax
0x18000fd14  jnz     loc_18000FE1E
0x18000fd1a  test    rbx, rbx
0x18000fd1d  jz      loc_18000FE55
0x18000fd23  mov     rax, [rbx]
0x18000fd26  xor     edx, edx
0x18000fd28  mov     rcx, rbx
0x18000fd2b  mov     rax, [rax+1F8h]
0x18000fd32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd37  test    eax, eax
0x18000fd39  js      loc_18000FE60
0x18000fd3f  mov     rbx, [rbp+arg_10]
0x18000fd43  test    rbx, rbx
0x18000fd46  jz      loc_18000FE55
0x18000fd4c  mov     rax, [rbx]
0x18000fd4f  or      r14d, 0FFFFFFFFh
0x18000fd53  mov     edx, r14d
0x18000fd56  mov     rcx, rbx
0x18000fd59  mov     rax, [rax+220h]
0x18000fd60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd65  test    eax, eax
0x18000fd67  js      loc_18000FE6B
0x18000fd6d  mov     rbx, [rbp+arg_10]
0x18000fd71  test    rbx, rbx
0x18000fd74  jz      loc_18000FE55
0x18000fd7a  mov     rax, [rbx]
0x18000fd7d  mov     edx, r14d
0x18000fd80  mov     rcx, rbx
0x18000fd83  mov     rax, [rax+230h]
0x18000fd8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd8f  test    eax, eax
0x18000fd91  js      loc_18000FE76
0x18000fd97  mov     rbx, [rbp+arg_10]
0x18000fd9b  test    rbx, rbx
0x18000fd9e  jz      loc_18000FE4A
0x18000fda4  lea     eax, [r14+9]
0x18000fda8  mov     word ptr [rbp+pvarg], ax
0x18000fdac  mov     rcx, rsi; psz
0x18000fdaf  call    cs:__imp_SysAllocString
0x18000fdb5  mov     qword ptr [rbp+pvarg+8], rax
0x18000fdb9  test    rax, rax
0x18000fdbc  jnz     short loc_18000FDC7
0x18000fdbe  test    rsi, rsi
0x18000fdc1  jnz     loc_18000FE81
0x18000fdc7  xor     eax, eax
0x18000fdc9  mov     [rbp+arg_8], ax
0x18000fdcd  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18000fdd1  movaps  [rbp+var_20], xmm0
0x18000fdd5  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18000fdda  movsd   [rbp+var_10], xmm1
0x18000fddf  mov     rax, [rbx]
0x18000fde2  lea     r8, [rbp+arg_8]
0x18000fde6  lea     rdx, [rbp+var_20]
0x18000fdea  mov     rcx, rbx
0x18000fded  mov     rax, [rax+1D0h]
0x18000fdf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdf9  test    eax, eax
0x18000fdfb  js      loc_18000FE8C
0x18000fe01  cmp     [rbp+arg_8], r14w
0x18000fe06  setz    bl
0x18000fe09  lea     rcx, [rbp+pvarg]; pvarg
0x18000fe0d  call    cs:__imp_VariantClear
0x18000fe13  test    bl, bl
0x18000fe15  mov     rbx, [rbp+arg_10]
0x18000fe19  jz      short loc_18000FE1E
0x18000fe1b  mov     byte ptr [rdi], 1
0x18000fe1e  test    rbx, rbx
0x18000fe21  jz      short loc_18000FE33
0x18000fe23  mov     rax, [rbx]
0x18000fe26  mov     rcx, rbx
0x18000fe29  mov     rax, [rax+10h]
0x18000fe2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe32  nop
0x18000fe33  xor     eax, eax
0x18000fe35  lea     r11, [rsp+70h+var_s0]
0x18000fe3a  mov     rbx, [r11+20h]
0x18000fe3e  mov     rsi, [r11+38h]
0x18000fe42  mov     rsp, r11
0x18000fe45  pop     r14
0x18000fe47  pop     rdi
0x18000fe48  pop     rbp
0x18000fe49  retn
0x18000fe4a  mov     ecx, 80004003h; int
0x18000fe4f  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18000fe55  mov     ecx, 80004003h; int
0x18000fe5a  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18000fe60  mov     rdx, rbx; struct IUnknown *
0x18000fe63  mov     ecx, eax; int
0x18000fe65  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x18000fe6b  mov     rdx, rbx; struct IUnknown *
0x18000fe6e  mov     ecx, eax; int
0x18000fe70  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x18000fe76  mov     rdx, rbx; struct IUnknown *
0x18000fe79  mov     ecx, eax; int
0x18000fe7b  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x18000fe81  mov     ecx, 8007000Eh; int
0x18000fe86  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18000fe8c  mov     rdx, rbx; struct IUnknown *
0x18000fe8f  mov     ecx, eax; int
0x18000fe91  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
```
