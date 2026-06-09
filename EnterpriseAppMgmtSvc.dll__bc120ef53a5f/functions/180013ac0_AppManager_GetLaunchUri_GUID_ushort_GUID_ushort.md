# AppManager::GetLaunchUri(_GUID,ushort *,_GUID *,ushort * *)

- ea: `0x180013ac0`
- end: `0x180013dcf`
- name: `?GetLaunchUri@AppManager@@QEAAJU_GUID@@PEAGPEAU2@PEAPEAG@Z`
- size: `783`
- prototype: `int(AppManager *__hidden this, struct _GUID *__struct_ptr, unsigned __int16 *, struct _GUID *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800049f0`

## callees

- `0x1800072ac`
- `0x180013ac0`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013b38`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013b38`
- `OLEAUT32!__imp_SysFreeString` at `0x180013c44`
- `OLEAUT32!__imp_SysFreeString` at `0x180013d20`
- `OLEAUT32!__imp_SysFreeString` at `0x180013d43`
- `OLEAUT32!__imp_SysFreeString` at `0x180013d54`
- `OLEAUT32!__imp_SysFreeString` at `0x180013d65`
- `OLEAUT32!__imp_SysFreeString` at `0x180013c44`
- `OLEAUT32!__imp_SysFreeString` at `0x180013d20`
- `OLEAUT32!__imp_SysFreeString` at `0x180013d43`
- `OLEAUT32!__imp_SysFreeString` at `0x180013d54`
- `OLEAUT32!__imp_SysFreeString` at `0x180013d65`
- `OLEAUT32!__imp_SysStringLen` at `0x180013c0a`
- `OLEAUT32!__imp_SysStringLen` at `0x180013ce4`
- `OLEAUT32!__imp_SysStringLen` at `0x180013c0a`
- `OLEAUT32!__imp_SysStringLen` at `0x180013ce4`
- `OLEAUT32!__imp_VarBstrCat` at `0x180013c2c`
- `OLEAUT32!__imp_VarBstrCat` at `0x180013d0b`
- `OLEAUT32!__imp_VarBstrCat` at `0x180013c2c`
- `OLEAUT32!__imp_VarBstrCat` at `0x180013d0b`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall AppManager::GetLaunchUri(
        AppManager *this,
        struct _GUID *a2,
        unsigned __int16 *a3,
        struct _GUID *a4,
        unsigned __int16 **a5)
{
  OLECHAR *v8; // rbx
  HRESULT v9; // edi
  unsigned __int16 **v10; // r12
  OLECHAR *v11; // rdi
  __int64 v12; // rsi
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned __int16 *v15; // rax
  BSTR v16; // rbx
  OLECHAR *v17; // rdx
  BSTR bstrRight; // [rsp+30h] [rbp-40h] BYREF
  BSTR pbstr; // [rsp+38h] [rbp-38h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-30h] BYREF
  BSTR pbstrResult[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v23; // [rsp+60h] [rbp-10h] BYREF
  BSTR bstrLeft; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v25; // [rsp+C8h] [rbp+58h] BYREF

  ppv = 0;
  v25 = 0;
  v23 = 0;
  pbstr = 0;
  bstrRight = 0;
  v8 = 0;
  bstrLeft = 0;
  if ( !a4 )
    goto LABEL_2;
  v10 = a5;
  if ( !a5 )
    goto LABEL_2;
  v9 = CoCreateInstance(&CLSID_PMSvc, 0, 0x17u, &IID_IPMEnumerationManager, &ppv);
  if ( v9 < 0 )
    goto LABEL_36;
  *(struct _GUID *)pbstrResult = *a2;
  v9 = (*(__int64 (__fastcall **)(LPVOID, BSTR *, __int64 *))(*(_QWORD *)ppv + 72LL))(ppv, pbstrResult, &v25);
  if ( v9 < 0 )
    goto LABEL_36;
  if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v25)(v25, &GUID_2925390a_d947_4062_9dad_cf6f60e6a707, &v23) >= 0 )
  {
LABEL_2:
    v9 = -2147024809;
    goto LABEL_36;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v25 + 224LL))(v25, a4);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, BSTR *, BSTR *))(*(_QWORD *)v25 + 200LL))(v25, &pbstr, &bstrRight);
    if ( v9 >= 0 )
    {
      v11 = pbstr;
      if ( !pbstr )
        goto LABEL_35;
      v12 = -1;
      v13 = -1;
      do
        ++v13;
      while ( pbstr[v13] );
      if ( v13 )
      {
        if ( SysStringLen(pbstr) )
        {
          pbstrResult[0] = 0;
          v9 = VarBstrCat(0, v11, pbstrResult);
          if ( v9 < 0 )
            goto LABEL_36;
          SysFreeString(0);
          v8 = pbstrResult[0];
          bstrLeft = pbstrResult[0];
        }
        else
        {
          v9 = 0;
        }
        if ( a3 )
        {
          v14 = -1;
          do
            ++v14;
          while ( a3[v14] );
          if ( v14 )
          {
            if ( *a3 == 47 )
              ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrLeft, L"#");
            v9 = ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrLeft, a3);
            if ( v9 >= 0 )
              goto LABEL_24;
            goto LABEL_34;
          }
        }
        if ( !bstrRight )
          goto LABEL_25;
        do
          ++v12;
        while ( bstrRight[v12] );
        if ( !v12 )
          goto LABEL_25;
        v9 = ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrLeft, L"?");
        if ( v9 < 0 )
        {
LABEL_34:
          v8 = bstrLeft;
          goto LABEL_36;
        }
        v16 = bstrRight;
        if ( !SysStringLen(bstrRight) )
        {
          v9 = 0;
LABEL_24:
          v8 = bstrLeft;
LABEL_25:
          v15 = v8;
          v8 = 0;
          *v10 = v15;
          goto LABEL_36;
        }
        pbstrResult[0] = 0;
        v17 = v16;
        v8 = bstrLeft;
        v9 = VarBstrCat(bstrLeft, v17, pbstrResult);
        if ( v9 >= 0 )
        {
          SysFreeString(v8);
          v8 = pbstrResult[0];
          goto LABEL_25;
        }
      }
      else
      {
LABEL_35:
        v9 = -2147467259;
      }
    }
  }
LABEL_36:
  SysFreeString(v8);
  SysFreeString(bstrRight);
  SysFreeString(pbstr);
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180013ac0  mov     [rsp-38h+arg_8], rbx
0x180013ac5  mov     [rsp-38h+bstrLeft], rcx
0x180013aca  push    rbp
0x180013acb  push    rsi
0x180013acc  push    rdi
0x180013acd  push    r12
0x180013acf  push    r13
0x180013ad1  push    r14
0x180013ad3  push    r15
0x180013ad5  mov     rbp, rsp
0x180013ad8  sub     rsp, 70h
0x180013adc  mov     rsi, r9
0x180013adf  mov     r14, r8
0x180013ae2  mov     r15, rdx
0x180013ae5  xor     r13d, r13d
0x180013ae8  mov     [rbp+var_30], r13
0x180013aec  mov     [rbp+arg_18], r13
0x180013af0  mov     [rbp+var_10], r13
0x180013af4  mov     [rbp+pbstr], r13
0x180013af8  mov     [rbp+bstrRight], r13
0x180013afc  mov     ebx, r13d
0x180013aff  mov     [rbp+bstrLeft], rbx
0x180013b03  test    r9, r9
0x180013b06  jnz     short loc_180013B12
0x180013b08  mov     edi, 80070057h
0x180013b0d  jmp     loc_180013D40
0x180013b12  mov     r12, [rbp+arg_20]
0x180013b16  test    r12, r12
0x180013b19  jz      short loc_180013B08
0x180013b1b  lea     rax, [rbp+var_30]
0x180013b1f  mov     [rsp+70h+ppv], rax; ppv
0x180013b24  lea     r9, IID_IPMEnumerationManager; riid
0x180013b2b  xor     edx, edx; pUnkOuter
0x180013b2d  lea     r8d, [rdx+17h]; dwClsContext
0x180013b31  lea     rcx, CLSID_PMSvc; rclsid
0x180013b38  call    cs:__imp_CoCreateInstance
0x180013b3f  nop     dword ptr [rax+rax+00h]
0x180013b44  mov     edi, eax
0x180013b46  test    eax, eax
0x180013b48  js      loc_180013D40
0x180013b4e  mov     rcx, [rbp+var_30]
0x180013b52  movaps  xmm0, xmmword ptr [r15]
0x180013b56  movdqa  xmmword ptr [rbp+pbstrResult], xmm0
0x180013b5b  mov     rax, [rcx]
0x180013b5e  lea     r8, [rbp+arg_18]
0x180013b62  lea     rdx, [rbp+pbstrResult]
0x180013b66  mov     rax, [rax+48h]
0x180013b6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b6f  mov     edi, eax
0x180013b71  test    eax, eax
0x180013b73  js      loc_180013D40
0x180013b79  mov     rcx, [rbp+arg_18]
0x180013b7d  mov     rax, [rcx]
0x180013b80  lea     r8, [rbp+var_10]
0x180013b84  lea     rdx, _GUID_2925390a_d947_4062_9dad_cf6f60e6a707
0x180013b8b  mov     rax, [rax]
0x180013b8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b93  test    eax, eax
0x180013b95  jns     loc_180013B08
0x180013b9b  mov     rcx, [rbp+arg_18]
0x180013b9f  mov     rax, [rcx]
0x180013ba2  mov     rdx, rsi
0x180013ba5  mov     rax, [rax+0E0h]
0x180013bac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bb1  mov     edi, eax
0x180013bb3  test    eax, eax
0x180013bb5  js      loc_180013D40
0x180013bbb  mov     rcx, [rbp+arg_18]
0x180013bbf  mov     rax, [rcx]
0x180013bc2  lea     r8, [rbp+bstrRight]
0x180013bc6  lea     rdx, [rbp+pbstr]
0x180013bca  mov     rax, [rax+0C8h]
0x180013bd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bd6  mov     edi, eax
0x180013bd8  test    eax, eax
0x180013bda  js      loc_180013D40
0x180013be0  mov     rdi, [rbp+pbstr]
0x180013be4  test    rdi, rdi
0x180013be7  jz      loc_180013D3B
0x180013bed  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180013bf1  mov     rax, rsi
0x180013bf4  inc     rax
0x180013bf7  cmp     [rdi+rax*2], r13w
0x180013bfc  jnz     short loc_180013BF4
0x180013bfe  test    rax, rax
0x180013c01  jz      loc_180013D3B
0x180013c07  mov     rcx, rdi; pbstr
0x180013c0a  call    cs:__imp_SysStringLen
0x180013c11  nop     dword ptr [rax+rax+00h]
0x180013c16  test    eax, eax
0x180013c18  jnz     short loc_180013C1F
0x180013c1a  mov     edi, r13d
0x180013c1d  jmp     short loc_180013C58
0x180013c1f  mov     [rbp+pbstrResult], r13
0x180013c23  lea     r8, [rbp+pbstrResult]; pbstrResult
0x180013c27  mov     rdx, rdi; bstrRight
0x180013c2a  xor     ecx, ecx; bstrLeft
0x180013c2c  call    cs:__imp_VarBstrCat
0x180013c33  nop     dword ptr [rax+rax+00h]
0x180013c38  mov     edi, eax
0x180013c3a  test    eax, eax
0x180013c3c  js      loc_180013D40
0x180013c42  xor     ecx, ecx; bstrString
0x180013c44  call    cs:__imp_SysFreeString
0x180013c4b  nop     dword ptr [rax+rax+00h]
0x180013c50  mov     rbx, [rbp+pbstrResult]
0x180013c54  mov     [rbp+bstrLeft], rbx
0x180013c58  test    r14, r14
0x180013c5b  jz      short loc_180013CAF
0x180013c5d  mov     rax, rsi
0x180013c60  inc     rax
0x180013c63  cmp     [r14+rax*2], r13w
0x180013c68  jnz     short loc_180013C60
0x180013c6a  test    rax, rax
0x180013c6d  jz      short loc_180013CAF
0x180013c6f  cmp     word ptr [r14], 2Fh ; '/'
0x180013c74  jnz     short loc_180013C86
0x180013c76  lea     rdx, asc_180078B04; "#"
0x180013c7d  lea     rcx, [rbp+bstrLeft]; this
0x180013c81  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x180013c86  mov     rdx, r14; unsigned __int16 *
0x180013c89  lea     rcx, [rbp+bstrLeft]; this
0x180013c8d  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x180013c92  mov     edi, eax
0x180013c94  test    eax, eax
0x180013c96  js      loc_180013D35
0x180013c9c  mov     rbx, [rbp+bstrLeft]
0x180013ca0  mov     rax, rbx
0x180013ca3  mov     rbx, r13
0x180013ca6  mov     [r12], rax
0x180013caa  jmp     loc_180013D40
0x180013caf  mov     rax, [rbp+bstrRight]
0x180013cb3  test    rax, rax
0x180013cb6  jz      short loc_180013CA0
0x180013cb8  inc     rsi
0x180013cbb  cmp     [rax+rsi*2], r13w
0x180013cc0  jnz     short loc_180013CB8
0x180013cc2  test    rsi, rsi
0x180013cc5  jz      short loc_180013CA0
0x180013cc7  lea     rdx, asc_180078B00; "?"
0x180013cce  lea     rcx, [rbp+bstrLeft]; this
0x180013cd2  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x180013cd7  mov     edi, eax
0x180013cd9  test    eax, eax
0x180013cdb  js      short loc_180013D35
0x180013cdd  mov     rbx, [rbp+bstrRight]
0x180013ce1  mov     rcx, rbx; pbstr
0x180013ce4  call    cs:__imp_SysStringLen
0x180013ceb  nop     dword ptr [rax+rax+00h]
0x180013cf0  test    eax, eax
0x180013cf2  jnz     short loc_180013CF9
0x180013cf4  mov     edi, r13d
0x180013cf7  jmp     short loc_180013C9C
0x180013cf9  mov     [rbp+pbstrResult], r13
0x180013cfd  lea     r8, [rbp+pbstrResult]; pbstrResult
0x180013d01  mov     rdx, rbx; bstrRight
0x180013d04  mov     rbx, [rbp+bstrLeft]
0x180013d08  mov     rcx, rbx; bstrLeft
0x180013d0b  call    cs:__imp_VarBstrCat
0x180013d12  nop     dword ptr [rax+rax+00h]
0x180013d17  mov     edi, eax
0x180013d19  test    eax, eax
0x180013d1b  js      short loc_180013D40
0x180013d1d  mov     rcx, rbx; bstrString
0x180013d20  call    cs:__imp_SysFreeString
0x180013d27  nop     dword ptr [rax+rax+00h]
0x180013d2c  mov     rbx, [rbp+pbstrResult]
0x180013d30  jmp     loc_180013CA0
0x180013d35  mov     rbx, [rbp+bstrLeft]
0x180013d39  jmp     short loc_180013D40
0x180013d3b  mov     edi, 80004005h
0x180013d40  mov     rcx, rbx; bstrString
0x180013d43  call    cs:__imp_SysFreeString
0x180013d4a  nop     dword ptr [rax+rax+00h]
0x180013d4f  nop
0x180013d50  mov     rcx, [rbp+bstrRight]; bstrString
0x180013d54  call    cs:__imp_SysFreeString
0x180013d5b  nop     dword ptr [rax+rax+00h]
0x180013d60  nop
0x180013d61  mov     rcx, [rbp+pbstr]; bstrString
0x180013d65  call    cs:__imp_SysFreeString
0x180013d6c  nop     dword ptr [rax+rax+00h]
0x180013d71  nop
0x180013d72  mov     rcx, [rbp+var_10]
0x180013d76  test    rcx, rcx
0x180013d79  jz      short loc_180013D88
0x180013d7b  mov     rax, [rcx]
0x180013d7e  mov     rax, [rax+10h]
0x180013d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d87  nop
0x180013d88  mov     rcx, [rbp+arg_18]
0x180013d8c  test    rcx, rcx
0x180013d8f  jz      short loc_180013D9E
0x180013d91  mov     rax, [rcx]
0x180013d94  mov     rax, [rax+10h]
0x180013d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d9d  nop
0x180013d9e  mov     rcx, [rbp+var_30]
0x180013da2  test    rcx, rcx
0x180013da5  jz      short loc_180013DB4
0x180013da7  mov     rax, [rcx]
0x180013daa  mov     rax, [rax+10h]
0x180013dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013db3  nop
0x180013db4  mov     eax, edi
0x180013db6  mov     rbx, [rsp+70h+arg_8]
0x180013dbe  add     rsp, 70h
0x180013dc2  pop     r15
0x180013dc4  pop     r14
0x180013dc6  pop     r13
0x180013dc8  pop     r12
0x180013dca  pop     rdi
0x180013dcb  pop     rsi
0x180013dcc  pop     rbp
0x180013dcd  retn
```
