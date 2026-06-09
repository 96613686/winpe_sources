# GetContentTypeFromFilePathThroughPacMan

- ea: `0x180007d80`
- end: `0x1800080c7`
- name: `GetContentTypeFromFilePathThroughPacMan`
- size: `839`
- prototype: `__int64 __fastcall(const WCHAR *, OLECHAR **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800083b0`

## callees

- `0x180007c90`
- `0x180007d80`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180007d99`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180007d99`
- `OLEAUT32!__imp_SysAllocString` at `0x180007dbf`
- `OLEAUT32!__imp_SysAllocString` at `0x180007dbf`
- `OLEAUT32!__imp_SysFreeString` at `0x180007e16`
- `OLEAUT32!__imp_SysFreeString` at `0x180007f45`
- `OLEAUT32!__imp_SysFreeString` at `0x180007f70`
- `OLEAUT32!__imp_SysFreeString` at `0x180007fdd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000803a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000808a`
- `OLEAUT32!__imp_SysFreeString` at `0x180008092`
- `OLEAUT32!__imp_SysFreeString` at `0x1800080a1`
- `OLEAUT32!__imp_SysFreeString` at `0x180007e16`
- `OLEAUT32!__imp_SysFreeString` at `0x180007f45`
- `OLEAUT32!__imp_SysFreeString` at `0x180007f70`
- `OLEAUT32!__imp_SysFreeString` at `0x180007fdd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000803a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000808a`
- `OLEAUT32!__imp_SysFreeString` at `0x180008092`
- `OLEAUT32!__imp_SysFreeString` at `0x1800080a1`
- `OLEAUT32!__imp_SysStringLen` at `0x180007ea4`
- `OLEAUT32!__imp_SysStringLen` at `0x180007f1a`
- `OLEAUT32!__imp_SysStringLen` at `0x180007ea4`
- `OLEAUT32!__imp_SysStringLen` at `0x180007f1a`
- `OLEAUT32!__imp_VarBstrCat` at `0x180007f32`
- `OLEAUT32!__imp_VarBstrCat` at `0x180007f32`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007df2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007df2`

## pseudocode

```c
__int64 __fastcall GetContentTypeFromFilePathThroughPacMan(const WCHAR *a1, OLECHAR **a2)
{
  LPWSTR ExtensionW; // rax
  OLECHAR *v4; // rbx
  OLECHAR *v5; // rdi
  HRESULT v6; // eax
  LPVOID v7; // rcx
  int v8; // esi
  __int64 v9; // rax
  const unsigned __int16 *v10; // rdx
  __int64 v11; // rcx
  OLECHAR *v12; // rsi
  OLECHAR *v13; // rcx
  __int64 v14; // rcx
  __int64 v16; // [rsp+30h] [rbp-50h] BYREF
  BSTR pbstr; // [rsp+38h] [rbp-48h] BYREF
  __int64 v18; // [rsp+40h] [rbp-40h] BYREF
  BSTR v19; // [rsp+48h] [rbp-38h] BYREF
  BSTR pbstrResult; // [rsp+50h] [rbp-30h] BYREF
  _QWORD v21[2]; // [rsp+60h] [rbp-20h] BYREF
  __int128 v22; // [rsp+70h] [rbp-10h]
  __int64 v23; // [rsp+C0h] [rbp+40h] BYREF
  LPVOID ppv; // [rsp+C8h] [rbp+48h] BYREF

  ExtensionW = PathFindExtensionW(a1);
  if ( !ExtensionW || !*ExtensionW )
  {
    *a2 = 0;
    return 0;
  }
  v4 = 0;
  v19 = 0;
  v5 = SysAllocString(ExtensionW);
  if ( v5 )
  {
    ppv = 0;
    v6 = CoCreateInstance(
           &GUID_b9e511fc_e364_497a_a121_b7b3612cedce,
           0,
           0x17u,
           &GUID_698d57c2_292d_4cf3_b73c_d95a6922ed9a,
           &ppv);
    v7 = ppv;
    v8 = v6;
    if ( v6 < 0 )
    {
      if ( !ppv )
      {
LABEL_7:
        SysFreeString(v5);
        goto LABEL_52;
      }
LABEL_6:
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(v7);
      goto LABEL_7;
    }
    v21[0] = 19;
    v21[1] = v5;
    v16 = 0;
    v9 = *(_QWORD *)ppv;
    v22 = 0;
    v8 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, _QWORD *))(v9 + 48))(ppv, &v16, v21);
    if ( v8 < 0 )
    {
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      v7 = ppv;
      if ( !ppv )
        goto LABEL_7;
      goto LABEL_6;
    }
    v23 = 0;
    while ( !(*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 24LL))(v16, &v23) )
    {
      if ( SysStringLen(v4) )
      {
        v8 = ATL::CComBSTR::Append(&v19, v10);
        if ( v8 < 0 )
        {
          if ( v23 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
          if ( v16 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          if ( ppv )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          v4 = v19;
          goto LABEL_43;
        }
        v4 = v19;
      }
      v11 = 0;
      v18 = 0;
      if ( v23 )
      {
        (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v23)(
          v23,
          &GUID_6b87cb6c_0b88_4989_a4ec_033714f710d4,
          &v18);
        v11 = v18;
      }
      pbstr = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, BSTR *))(*(_QWORD *)v11 + 48LL))(v11, v5, &pbstr);
      if ( v8 < 0 )
      {
LABEL_35:
        SysFreeString(pbstr);
        if ( v18 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        if ( v23 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        if ( v16 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        if ( ppv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
LABEL_43:
        SysFreeString(v5);
        v13 = v4;
        goto LABEL_53;
      }
      v12 = pbstr;
      if ( SysStringLen(pbstr) )
      {
        pbstrResult = 0;
        v8 = VarBstrCat(v4, v12, &pbstrResult);
        if ( v8 < 0 )
          goto LABEL_35;
        SysFreeString(v4);
        v4 = pbstrResult;
        v19 = pbstrResult;
      }
      if ( v23 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        v23 = 0;
      }
      SysFreeString(pbstr);
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v14 = v23;
    *a2 = v4;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    SysFreeString(v5);
    SysFreeString(0);
    return 0;
  }
  v8 = -2147024882;
LABEL_52:
  v13 = 0;
LABEL_53:
  SysFreeString(v13);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180007d80  mov     [rsp-28h+arg_0], rbx
0x180007d85  push    rbp
0x180007d86  push    rsi
0x180007d87  push    rdi
0x180007d88  push    r14
0x180007d8a  push    r15
0x180007d8c  mov     rbp, rsp
0x180007d8f  sub     rsp, 80h
0x180007d96  mov     r14, rdx
0x180007d99  call    cs:__imp_PathFindExtensionW
0x180007d9f  xor     r15d, r15d
0x180007da2  test    rax, rax
0x180007da5  jz      loc_1800080AB
0x180007dab  cmp     [rax], r15w
0x180007daf  jz      loc_1800080AB
0x180007db5  mov     ebx, r15d
0x180007db8  mov     rcx, rax; psz
0x180007dbb  mov     [rbp+var_38], rbx
0x180007dbf  call    cs:__imp_SysAllocString
0x180007dc5  mov     rdi, rax
0x180007dc8  test    rax, rax
0x180007dcb  jz      loc_18000809A
0x180007dd1  lea     rax, [rbp+arg_18]
0x180007dd5  mov     [rbp+arg_18], r15
0x180007dd9  lea     r9, _GUID_698d57c2_292d_4cf3_b73c_d95a6922ed9a; riid
0x180007de0  mov     [rsp+80h+ppv], rax; ppv
0x180007de5  xor     edx, edx; pUnkOuter
0x180007de7  lea     r8d, [r15+17h]; dwClsContext
0x180007deb  lea     rcx, _GUID_b9e511fc_e364_497a_a121_b7b3612cedce; rclsid
0x180007df2  call    cs:__imp_CoCreateInstance
0x180007df8  mov     rcx, [rbp+arg_18]
0x180007dfc  mov     esi, eax
0x180007dfe  test    eax, eax
0x180007e00  jns     short loc_180007E21
0x180007e02  test    rcx, rcx
0x180007e05  jz      short loc_180007E13
0x180007e07  mov     rdx, [rcx]
0x180007e0a  mov     rax, [rdx+10h]
0x180007e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e13  mov     rcx, rdi; bstrString
0x180007e16  call    cs:__imp_SysFreeString
0x180007e1c  jmp     loc_18000809F
0x180007e21  mov     qword ptr [rbp+var_20], 13h
0x180007e29  lea     r8, [rbp+var_20]
0x180007e2d  mov     qword ptr [rbp+var_20+8], rdi
0x180007e31  lea     rdx, [rbp+var_50]
0x180007e35  movups  xmm0, [rbp+var_20]
0x180007e39  mov     [rbp+var_50], r15
0x180007e3d  mov     rax, [rcx]
0x180007e40  xorps   xmm1, xmm1
0x180007e43  movaps  [rbp+var_20], xmm0
0x180007e47  movaps  [rbp+var_10], xmm1
0x180007e4b  mov     rax, [rax+30h]
0x180007e4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e54  mov     esi, eax
0x180007e56  test    eax, eax
0x180007e58  jns     short loc_180007E81
0x180007e5a  mov     rcx, [rbp+var_50]
0x180007e5e  test    rcx, rcx
0x180007e61  jz      short loc_180007E6F
0x180007e63  mov     rdx, [rcx]
0x180007e66  mov     rax, [rdx+10h]
0x180007e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e6f  mov     rcx, [rbp+arg_18]
0x180007e73  test    rcx, rcx
0x180007e76  jz      short loc_180007E13
0x180007e78  mov     rax, [rcx]
0x180007e7b  mov     rax, [rax+10h]
0x180007e7f  jmp     short loc_180007E0E
0x180007e81  mov     [rbp+arg_10], r15
0x180007e85  mov     rcx, [rbp+var_50]
0x180007e89  lea     rdx, [rbp+arg_10]
0x180007e8d  mov     rax, [rcx]
0x180007e90  mov     rax, [rax+18h]
0x180007e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e99  test    eax, eax
0x180007e9b  jnz     loc_180008045
0x180007ea1  mov     rcx, rbx; pbstr
0x180007ea4  call    cs:__imp_SysStringLen
0x180007eaa  test    eax, eax
0x180007eac  jz      short loc_180007EC5
0x180007eae  lea     rcx, [rbp+var_38]; this
0x180007eb2  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x180007eb7  mov     esi, eax
0x180007eb9  test    eax, eax
0x180007ebb  js      loc_180007F94
0x180007ec1  mov     rbx, [rbp+var_38]
0x180007ec5  mov     r9, [rbp+arg_10]
0x180007ec9  mov     rcx, r15
0x180007ecc  mov     [rbp+var_40], rcx
0x180007ed0  test    r9, r9
0x180007ed3  jz      short loc_180007EF2
0x180007ed5  mov     rax, [r9]
0x180007ed8  lea     r8, [rbp+var_40]
0x180007edc  lea     rdx, _GUID_6b87cb6c_0b88_4989_a4ec_033714f710d4
0x180007ee3  mov     rcx, r9
0x180007ee6  mov     rax, [rax]
0x180007ee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007eee  mov     rcx, [rbp+var_40]
0x180007ef2  mov     [rbp+pbstr], r15
0x180007ef6  lea     r8, [rbp+pbstr]
0x180007efa  mov     rax, [rcx]
0x180007efd  mov     rdx, rdi
0x180007f00  mov     rax, [rax+30h]
0x180007f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f09  mov     esi, eax
0x180007f0b  test    eax, eax
0x180007f0d  js      loc_180007FD9
0x180007f13  mov     rsi, [rbp+pbstr]
0x180007f17  mov     rcx, rsi; pbstr
0x180007f1a  call    cs:__imp_SysStringLen
0x180007f20  test    eax, eax
0x180007f22  jz      short loc_180007F53
0x180007f24  lea     r8, [rbp+pbstrResult]; pbstrResult
0x180007f28  mov     [rbp+pbstrResult], r15
0x180007f2c  mov     rdx, rsi; bstrRight
0x180007f2f  mov     rcx, rbx; bstrLeft
0x180007f32  call    cs:__imp_VarBstrCat
0x180007f38  mov     esi, eax
0x180007f3a  test    eax, eax
0x180007f3c  js      loc_180007FD9
0x180007f42  mov     rcx, rbx; bstrString
0x180007f45  call    cs:__imp_SysFreeString
0x180007f4b  mov     rbx, [rbp+pbstrResult]
0x180007f4f  mov     [rbp+var_38], rbx
0x180007f53  mov     rcx, [rbp+arg_10]
0x180007f57  test    rcx, rcx
0x180007f5a  jz      short loc_180007F6C
0x180007f5c  mov     rax, [rcx]
0x180007f5f  mov     rax, [rax+10h]
0x180007f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f68  mov     [rbp+arg_10], r15
0x180007f6c  mov     rcx, [rbp+pbstr]; bstrString
0x180007f70  call    cs:__imp_SysFreeString
0x180007f76  mov     rcx, [rbp+var_40]
0x180007f7a  test    rcx, rcx
0x180007f7d  jz      loc_180007E85
0x180007f83  mov     rax, [rcx]
0x180007f86  mov     rax, [rax+10h]
0x180007f8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f8f  jmp     loc_180007E85
0x180007f94  mov     rcx, [rbp+arg_10]
0x180007f98  test    rcx, rcx
0x180007f9b  jz      short loc_180007FA9
0x180007f9d  mov     rax, [rcx]
0x180007fa0  mov     rax, [rax+10h]
0x180007fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fa9  mov     rcx, [rbp+var_50]
0x180007fad  test    rcx, rcx
0x180007fb0  jz      short loc_180007FBE
0x180007fb2  mov     rax, [rcx]
0x180007fb5  mov     rax, [rax+10h]
0x180007fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fbe  mov     rcx, [rbp+arg_18]
0x180007fc2  test    rcx, rcx
0x180007fc5  jz      short loc_180007FD3
0x180007fc7  mov     rax, [rcx]
0x180007fca  mov     rax, [rax+10h]
0x180007fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fd3  mov     rbx, [rbp+var_38]
0x180007fd7  jmp     short loc_180008037
0x180007fd9  mov     rcx, [rbp+pbstr]; bstrString
0x180007fdd  call    cs:__imp_SysFreeString
0x180007fe3  mov     rcx, [rbp+var_40]
0x180007fe7  test    rcx, rcx
0x180007fea  jz      short loc_180007FF8
0x180007fec  mov     rax, [rcx]
0x180007fef  mov     rax, [rax+10h]
0x180007ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ff8  mov     rcx, [rbp+arg_10]
0x180007ffc  test    rcx, rcx
0x180007fff  jz      short loc_18000800D
0x180008001  mov     rax, [rcx]
0x180008004  mov     rax, [rax+10h]
0x180008008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000800d  mov     rcx, [rbp+var_50]
0x180008011  test    rcx, rcx
0x180008014  jz      short loc_180008022
0x180008016  mov     rax, [rcx]
0x180008019  mov     rax, [rax+10h]
0x18000801d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008022  mov     rcx, [rbp+arg_18]
0x180008026  test    rcx, rcx
0x180008029  jz      short loc_180008037
0x18000802b  mov     rax, [rcx]
0x18000802e  mov     rax, [rax+10h]
0x180008032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008037  mov     rcx, rdi; bstrString
0x18000803a  call    cs:__imp_SysFreeString
0x180008040  mov     rcx, rbx
0x180008043  jmp     short loc_1800080A1
0x180008045  mov     rcx, [rbp+arg_10]
0x180008049  mov     [r14], rbx
0x18000804c  test    rcx, rcx
0x18000804f  jz      short loc_18000805D
0x180008051  mov     rax, [rcx]
0x180008054  mov     rax, [rax+10h]
0x180008058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000805d  mov     rcx, [rbp+var_50]
0x180008061  test    rcx, rcx
0x180008064  jz      short loc_180008072
0x180008066  mov     rax, [rcx]
0x180008069  mov     rax, [rax+10h]
0x18000806d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008072  mov     rcx, [rbp+arg_18]
0x180008076  test    rcx, rcx
0x180008079  jz      short loc_180008087
0x18000807b  mov     rax, [rcx]
0x18000807e  mov     rax, [rax+10h]
0x180008082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008087  mov     rcx, rdi; bstrString
0x18000808a  call    cs:__imp_SysFreeString
0x180008090  xor     ecx, ecx; bstrString
0x180008092  call    cs:__imp_SysFreeString
0x180008098  jmp     short loc_1800080AE
0x18000809a  mov     esi, 8007000Eh
0x18000809f  xor     ecx, ecx; bstrString
0x1800080a1  call    cs:__imp_SysFreeString
0x1800080a7  mov     eax, esi
0x1800080a9  jmp     short loc_1800080B0
0x1800080ab  mov     [r14], r15
0x1800080ae  xor     eax, eax
0x1800080b0  mov     rbx, [rsp+80h+arg_0]
0x1800080b8  add     rsp, 80h
0x1800080bf  pop     r15
0x1800080c1  pop     r14
0x1800080c3  pop     rdi
0x1800080c4  pop     rsi
0x1800080c5  pop     rbp
0x1800080c6  retn
```
