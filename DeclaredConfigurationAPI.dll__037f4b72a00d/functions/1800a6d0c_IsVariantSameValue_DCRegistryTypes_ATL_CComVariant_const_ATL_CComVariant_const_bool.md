# IsVariantSameValue(DCRegistryTypes,ATL::CComVariant const &,ATL::CComVariant const &,bool *)

- ea: `0x1800a6d0c`
- end: `0x1800a6fc2`
- name: `?IsVariantSameValue@@YAJW4DCRegistryTypes@@AEBVCComVariant@ATL@@1PEA_N@Z`
- size: `694`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ae150`
- `0x1800e4848`

## callees

- `0x18000c8d0`
- `0x1800117dc`
- `0x18004e188`
- `0x1800a6d0c`
- `0x180102c48`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800a6f9c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800a6f9c`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800a6eb2`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800a6ef6`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800a6eb2`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800a6ef6`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800a6e7b`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800a6ed8`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800a6e7b`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800a6ed8`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800a6f46`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800a6f6c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800a6f46`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800a6f6c`

## string_xrefs

- `0x1800a6d41`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcutils.cpp`
- `0x1800a6de0`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcutils.cpp`
- `0x1800a6e91`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcutils.cpp`
- `0x1800a6f06`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcutils.cpp`

## pseudocode

```c
__int64 __fastcall IsVariantSameValue(int a1, __int64 a2, __int64 a3, bool *a4)
{
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  SAFEARRAY *v16; // rcx
  HRESULT v17; // edi
  __int64 v18; // rdx
  bool v19; // al
  int v20; // eax
  bool v21; // zf
  SAFEARRAY *v22; // rcx
  HRESULT LBound; // r15d
  __int64 v24; // rdx
  int v25; // r13d
  HRESULT UBound; // eax
  unsigned int v27; // esi
  int v28; // ecx
  SAFEARRAY *v29; // rcx
  SAFEARRAY *v30; // rcx
  LONG plLbound[2]; // [rsp+20h] [rbp-20h] BYREF
  wchar_t *S2; // [rsp+28h] [rbp-18h] BYREF
  wchar_t *S1[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  size_t N; // [rsp+88h] [rbp+48h] BYREF

  if ( !a4 )
  {
    v7 = -2147024809;
    v8 = 1259;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcutils.cpp",
      (const char *)v7,
      plLbound[0]);
    return v7;
  }
  v10 = a1 - 1;
  if ( !v10 )
    goto LABEL_39;
  v11 = v10 - 2;
  if ( !v11 )
  {
    v22 = *(SAFEARRAY **)(a2 + 8);
    plLbound[0] = 0;
    LODWORD(N) = 0;
    LBound = SafeArrayGetLBound(v22, 1u, plLbound);
    if ( LBound >= 0 )
    {
      LBound = SafeArrayGetUBound(*(SAFEARRAY **)(a2 + 8), 1u, (LONG *)&N);
      if ( LBound >= 0 )
      {
        v25 = N - plLbound[0];
        LBound = SafeArrayGetLBound(*(SAFEARRAY **)(a3 + 8), 1u, plLbound);
        if ( LBound >= 0 )
        {
          UBound = SafeArrayGetUBound(*(SAFEARRAY **)(a3 + 8), 1u, (LONG *)&N);
          v27 = UBound;
          if ( UBound < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x514,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcutils.cpp",
              (const char *)(unsigned int)UBound,
              plLbound[0]);
            return v27;
          }
          v28 = N - plLbound[0] + 1;
          *a4 = v25 + 1 == v28;
          if ( v25 + 1 == v28 )
          {
            v29 = *(SAFEARRAY **)(a2 + 8);
            S2 = 0;
            v17 = SafeArrayAccessData(v29, (void **)&S2);
            if ( v17 < 0 )
            {
              v18 = 1310;
              goto LABEL_14;
            }
            v30 = *(SAFEARRAY **)(a3 + 8);
            S1[0] = 0;
            v17 = SafeArrayAccessData(v30, (void **)S1);
            if ( v17 < 0 )
            {
              v18 = 1315;
              goto LABEL_14;
            }
            v20 = memcmp_0(S2, S1[0], v25 + 1);
            goto LABEL_40;
          }
          return 0;
        }
        v24 = 1299;
      }
      else
      {
        v24 = 1296;
      }
    }
    else
    {
      v24 = 1295;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcutils.cpp",
      (const char *)(unsigned int)LBound,
      plLbound[0]);
    return (unsigned int)LBound;
  }
  v12 = v11 - 1;
  if ( !v12 )
  {
    v21 = *(_DWORD *)(a2 + 8) == *(_DWORD *)(a3 + 8);
LABEL_23:
    *a4 = v21;
    return 0;
  }
  v13 = v12 - 1;
  if ( v13 )
  {
    v14 = v13 - 1;
    if ( v14 )
    {
      v15 = v14 - 1;
      if ( v15 )
      {
        if ( v15 != 1 )
        {
          v7 = -2147418113;
          v8 = 1325;
          goto LABEL_3;
        }
LABEL_39:
        v20 = _o__wcsicmp(*(_QWORD *)(a2 + 8), *(_QWORD *)(a3 + 8));
        goto LABEL_40;
      }
      v16 = *(SAFEARRAY **)(a2 + 8);
      S1[0] = 0;
      N = 0;
      S2 = 0;
      *(_QWORD *)plLbound = 0;
      v17 = SafeArrayToMultiString(v16, 0, S1, &N);
      if ( v17 < 0 )
      {
        v18 = 1279;
LABEL_14:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcutils.cpp",
          (const char *)(unsigned int)v17,
          plLbound[0]);
        return (unsigned int)v17;
      }
      v17 = SafeArrayToMultiString(*(SAFEARRAY **)(a3 + 8), 0, &S2, (unsigned __int64 *)plLbound);
      if ( v17 < 0 )
      {
        v18 = 1280;
        goto LABEL_14;
      }
      if ( N != *(_QWORD *)plLbound )
      {
        v19 = 0;
LABEL_41:
        *a4 = v19;
        return 0;
      }
      v20 = wmemcmp(S1[0], S2, N);
LABEL_40:
      v19 = v20 == 0;
      goto LABEL_41;
    }
    v21 = *(_QWORD *)(a2 + 8) == *(_QWORD *)(a3 + 8);
    goto LABEL_23;
  }
  *a4 = 1;
  return 0;
}

```

## disassembly

```asm
0x1800a6d0c  mov     [rsp-28h+arg_0], rbx
0x1800a6d11  mov     [rsp-28h+arg_8], rsi
0x1800a6d16  push    rbp
0x1800a6d17  push    rdi
0x1800a6d18  push    r13
0x1800a6d1a  push    r14
0x1800a6d1c  push    r15
0x1800a6d1e  mov     rbp, rsp
0x1800a6d21  sub     rsp, 40h
0x1800a6d25  mov     rbx, r9
0x1800a6d28  mov     r14, r8
0x1800a6d2b  mov     rdi, rdx
0x1800a6d2e  test    r9, r9
0x1800a6d31  jnz     short loc_1800A6D57
0x1800a6d33  mov     ebx, 80070057h
0x1800a6d38  mov     edx, 4EBh; void *
0x1800a6d3d  mov     rcx, [rbp+28h]; this
0x1800a6d41  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800a6d48  mov     r9d, ebx; char *
0x1800a6d4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6d50  mov     eax, ebx
0x1800a6d52  jmp     loc_1800A6FAB
0x1800a6d57  sub     ecx, 1
0x1800a6d5a  jz      loc_1800A6F94
0x1800a6d60  sub     ecx, 2
0x1800a6d63  jz      loc_1800A6E5E
0x1800a6d69  sub     ecx, 1
0x1800a6d6c  jz      loc_1800A6E4C
0x1800a6d72  sub     ecx, 1
0x1800a6d75  jz      loc_1800A6E43
0x1800a6d7b  sub     ecx, 1
0x1800a6d7e  jz      loc_1800A6E39
0x1800a6d84  sub     ecx, 1
0x1800a6d87  jz      short loc_1800A6D9E
0x1800a6d89  cmp     ecx, 1
0x1800a6d8c  jz      loc_1800A6F94
0x1800a6d92  mov     ebx, 8000FFFFh
0x1800a6d97  mov     edx, 52Dh
0x1800a6d9c  jmp     short loc_1800A6D3D
0x1800a6d9e  mov     rcx, [rdi+8]; psa
0x1800a6da2  lea     r9, [rbp+N]; unsigned __int64 *
0x1800a6da6  xor     edx, edx; unsigned __int16
0x1800a6da8  mov     [rbp+S1], 0
0x1800a6db0  lea     r8, [rbp+S1]; unsigned __int16 **
0x1800a6db4  mov     [rbp+N], 0
0x1800a6dbc  mov     [rbp+S2], 0
0x1800a6dc4  mov     qword ptr [rbp+plLbound], 0
0x1800a6dcc  call    ?SafeArrayToMultiString@@YAJPEAUtagSAFEARRAY@@GPEAPEAGPEA_K@Z; SafeArrayToMultiString(tagSAFEARRAY *,ushort,ushort * *,unsigned __int64 *)
0x1800a6dd1  mov     edi, eax
0x1800a6dd3  test    eax, eax
0x1800a6dd5  jns     short loc_1800A6DF6
0x1800a6dd7  mov     edx, 4FFh; void *
0x1800a6ddc  mov     rcx, [rbp+28h]; this
0x1800a6de0  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800a6de7  mov     r9d, edi; char *
0x1800a6dea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6def  mov     eax, edi
0x1800a6df1  jmp     loc_1800A6FAB
0x1800a6df6  mov     rcx, [r14+8]; psa
0x1800a6dfa  lea     r9, [rbp+plLbound]; unsigned __int64 *
0x1800a6dfe  xor     edx, edx; unsigned __int16
0x1800a6e00  lea     r8, [rbp+S2]; unsigned __int16 **
0x1800a6e04  call    ?SafeArrayToMultiString@@YAJPEAUtagSAFEARRAY@@GPEAPEAGPEA_K@Z; SafeArrayToMultiString(tagSAFEARRAY *,ushort,ushort * *,unsigned __int64 *)
0x1800a6e09  mov     edi, eax
0x1800a6e0b  test    eax, eax
0x1800a6e0d  jns     short loc_1800A6E16
0x1800a6e0f  mov     edx, 500h
0x1800a6e14  jmp     short loc_1800A6DDC
0x1800a6e16  mov     r8, [rbp+N]; N
0x1800a6e1a  cmp     r8, qword ptr [rbp+plLbound]
0x1800a6e1e  jz      short loc_1800A6E27
0x1800a6e20  xor     al, al
0x1800a6e22  jmp     loc_1800A6FA7
0x1800a6e27  mov     rdx, [rbp+S2]; S2
0x1800a6e2b  mov     rcx, [rbp+S1]; S1
0x1800a6e2f  call    wmemcmp
0x1800a6e34  jmp     loc_1800A6FA2
0x1800a6e39  mov     rax, [r8+8]
0x1800a6e3d  cmp     [rdx+8], rax
0x1800a6e41  jmp     short loc_1800A6E53
0x1800a6e43  mov     byte ptr [r9], 1
0x1800a6e47  jmp     loc_1800A6FA9
0x1800a6e4c  mov     eax, [r8+8]
0x1800a6e50  cmp     [rdx+8], eax
0x1800a6e53  setz    al
0x1800a6e56  mov     [r9], al
0x1800a6e59  jmp     loc_1800A6FA9
0x1800a6e5e  mov     rcx, [rdi+8]; psa
0x1800a6e62  lea     r8, [rbp+plLbound]; plLbound
0x1800a6e66  mov     esi, 1
0x1800a6e6b  mov     [rbp+plLbound], 0
0x1800a6e72  mov     edx, esi; nDim
0x1800a6e74  mov     dword ptr [rbp+N], 0
0x1800a6e7b  call    cs:__imp_SafeArrayGetLBound
0x1800a6e81  mov     r15d, eax
0x1800a6e84  test    eax, eax
0x1800a6e86  jns     short loc_1800A6EA8
0x1800a6e88  mov     edx, 50Fh; void *
0x1800a6e8d  mov     rcx, [rbp+28h]; this
0x1800a6e91  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800a6e98  mov     r9d, r15d; char *
0x1800a6e9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6ea0  mov     eax, r15d
0x1800a6ea3  jmp     loc_1800A6FAB
0x1800a6ea8  mov     rcx, [rdi+8]; psa
0x1800a6eac  lea     r8, [rbp+N]; plUbound
0x1800a6eb0  mov     edx, esi; nDim
0x1800a6eb2  call    cs:__imp_SafeArrayGetUBound
0x1800a6eb8  mov     r15d, eax
0x1800a6ebb  test    eax, eax
0x1800a6ebd  jns     short loc_1800A6EC6
0x1800a6ebf  mov     edx, 510h
0x1800a6ec4  jmp     short loc_1800A6E8D
0x1800a6ec6  mov     r13d, dword ptr [rbp+N]
0x1800a6eca  lea     r8, [rbp+plLbound]; plLbound
0x1800a6ece  mov     rcx, [r14+8]; psa
0x1800a6ed2  mov     edx, esi; nDim
0x1800a6ed4  sub     r13d, [rbp+plLbound]
0x1800a6ed8  call    cs:__imp_SafeArrayGetLBound
0x1800a6ede  mov     r15d, eax
0x1800a6ee1  test    eax, eax
0x1800a6ee3  jns     short loc_1800A6EEC
0x1800a6ee5  mov     edx, 513h
0x1800a6eea  jmp     short loc_1800A6E8D
0x1800a6eec  mov     rcx, [r14+8]; psa
0x1800a6ef0  lea     r8, [rbp+N]; plUbound
0x1800a6ef4  mov     edx, esi; nDim
0x1800a6ef6  call    cs:__imp_SafeArrayGetUBound
0x1800a6efc  mov     esi, eax
0x1800a6efe  test    eax, eax
0x1800a6f00  jns     short loc_1800A6F21
0x1800a6f02  mov     rcx, [rbp+28h]; this
0x1800a6f06  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800a6f0d  mov     r9d, eax; char *
0x1800a6f10  mov     edx, 514h; void *
0x1800a6f15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6f1a  mov     eax, esi
0x1800a6f1c  jmp     loc_1800A6FAB
0x1800a6f21  mov     ecx, dword ptr [rbp+N]
0x1800a6f24  lea     esi, [r13+1]
0x1800a6f28  sub     ecx, [rbp+plLbound]
0x1800a6f2b  inc     ecx
0x1800a6f2d  cmp     esi, ecx
0x1800a6f2f  setz    al
0x1800a6f32  mov     [rbx], al
0x1800a6f34  jnz     short loc_1800A6FA9
0x1800a6f36  mov     rcx, [rdi+8]; psa
0x1800a6f3a  lea     rdx, [rbp+S2]; ppvData
0x1800a6f3e  mov     [rbp+S2], 0
0x1800a6f46  call    cs:__imp_SafeArrayAccessData
0x1800a6f4c  mov     edi, eax
0x1800a6f4e  test    eax, eax
0x1800a6f50  jns     short loc_1800A6F5C
0x1800a6f52  mov     edx, 51Eh
0x1800a6f57  jmp     loc_1800A6DDC
0x1800a6f5c  mov     rcx, [r14+8]; psa
0x1800a6f60  lea     rdx, [rbp+S1]; ppvData
0x1800a6f64  mov     [rbp+S1], 0
0x1800a6f6c  call    cs:__imp_SafeArrayAccessData
0x1800a6f72  mov     edi, eax
0x1800a6f74  test    eax, eax
0x1800a6f76  jns     short loc_1800A6F82
0x1800a6f78  mov     edx, 523h
0x1800a6f7d  jmp     loc_1800A6DDC
0x1800a6f82  mov     rdx, [rbp+S1]; Buf2
0x1800a6f86  mov     rcx, [rbp+S2]; Buf1
0x1800a6f8a  movsxd  r8, esi; Size
0x1800a6f8d  call    memcmp_0
0x1800a6f92  jmp     short loc_1800A6FA2
0x1800a6f94  mov     rdx, [r8+8]
0x1800a6f98  mov     rcx, [rdi+8]
0x1800a6f9c  call    cs:__imp__o__wcsicmp
0x1800a6fa2  test    eax, eax
0x1800a6fa4  setz    al
0x1800a6fa7  mov     [rbx], al
0x1800a6fa9  xor     eax, eax
0x1800a6fab  mov     rbx, [rsp+40h+arg_0]
0x1800a6fb0  mov     rsi, [rsp+40h+arg_8]
0x1800a6fb5  add     rsp, 40h
0x1800a6fb9  pop     r15
0x1800a6fbb  pop     r14
0x1800a6fbd  pop     r13
0x1800a6fbf  pop     rdi
0x1800a6fc0  pop     rbp
0x1800a6fc1  retn
```
