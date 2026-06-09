# _ResolveConflictByFiletype

- ea: `0x180048c3c`
- end: `0x180048f0a`
- name: `_ResolveConflictByFiletype`
- size: `718`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180048ff4`

## callees

- `0x1800133b0`
- `0x1800134dc`
- `0x180031548`
- `0x180048ad4`
- `0x180048c3c`
- `0x180048f10`
- `0x180052906`
- `0x180052950`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048e5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048e68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048e71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048e7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048eb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048ec0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048ec9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048ed2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048e5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048e68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048e71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048e7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048eb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048ec0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048ec9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048ed2`

## pseudocode

```c
__int64 __fastcall ResolveConflictByFiletype(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 *v8; // rdx
  __int64 v9; // rax
  int (__fastcall *v10)(__int64, __int64 *); // rax
  __int64 v11; // r8
  GUID v12; // xmm6
  int v13; // esi
  int PresenterClsidForItem; // eax
  int v15; // edi
  LPVOID v16; // rcx
  void *v17; // rbx
  void *v18; // rdi
  void *v19; // rsi
  void *v20; // r14
  LPVOID v21; // rcx
  void *v22; // rbx
  void *v23; // rdi
  void *v24; // rsi
  void *v25; // r14
  __int64 v27; // [rsp+38h] [rbp-A9h] BYREF
  __int64 v28; // [rsp+40h] [rbp-A1h] BYREF
  __int64 v29; // [rsp+48h] [rbp-99h] BYREF
  LPVOID v30[3]; // [rsp+50h] [rbp-91h] BYREF
  LPVOID pv[2]; // [rsp+68h] [rbp-79h] BYREF
  LPVOID v32[2]; // [rsp+78h] [rbp-69h]
  LPVOID v33[2]; // [rsp+88h] [rbp-59h]
  LPVOID v34[2]; // [rsp+98h] [rbp-49h] BYREF
  LPVOID v35[2]; // [rsp+A8h] [rbp-39h]
  LPVOID v36[2]; // [rsp+B8h] [rbp-29h]
  GUID Buf1; // [rsp+C8h] [rbp-19h] BYREF
  GUID Buf2; // [rsp+D8h] [rbp-9h] BYREF

  ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(&v28);
  v9 = *v8;
  LODWORD(v27) = 0;
  *(_OWORD *)v34 = 0;
  v10 = *(int (__fastcall **)(__int64, __int64 *))(v9 + 40);
  *(_OWORD *)v35 = 0;
  *(_OWORD *)v36 = 0;
  *(_OWORD *)pv = 0;
  *(_OWORD *)v32 = 0;
  *(_OWORD *)v33 = 0;
  if ( v10(a2, &v28) >= 0
    && (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v28 + 24LL))(v28, &v27) >= 0
    && (_DWORD)v27 == 2
    && (*(int (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)v28 + 32LL))(v28, 0, v34) >= 0
    && (*(int (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v28 + 32LL))(v28, 1, pv) >= 0 )
  {
    ATL::CComPtr<IShellItem>::CComPtr<IShellItem>(v30, (__int64)v34[0]);
    ATL::CComPtr<IShellItem>::CComPtr<IShellItem>(&v29, (__int64)pv[0]);
    v12 = GUID_NULL;
    v13 = (int)v36[1];
    PresenterClsidForItem = -2147467259;
    v15 = (int)v33[1];
    Buf1 = GUID_NULL;
    Buf2 = GUID_NULL;
    if ( LODWORD(v36[1]) != 2 )
    {
      PresenterClsidForItem = GetPresenterClsidForItem(v30[0], &Buf1);
      v12 = Buf1;
    }
    if ( v15 != 2 )
    {
      PresenterClsidForItem = GetPresenterClsidForItem(v29, &Buf2);
      v12 = Buf1;
    }
    if ( PresenterClsidForItem < 0 )
      goto LABEL_22;
    if ( v13 != 1 )
    {
      if ( v13 != 2 || v15 != 1 )
        goto LABEL_22;
      *(GUID *)&v30[1] = Buf2;
      goto LABEL_21;
    }
    if ( v15 == 1 )
    {
      if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
      {
LABEL_14:
        *(GUID *)&v30[1] = v12;
LABEL_21:
        ResolveConflictWithPresenterClsid(a1, (__int64)&v30[1], v11, a2, a3, a4);
        goto LABEL_22;
      }
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a3 + 64LL))(a3, 1);
    }
    else if ( v15 == 2 )
    {
      goto LABEL_14;
    }
LABEL_22:
    ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>((__int64)&v29);
    ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>((__int64)v30);
  }
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a3 + 32LL))(a3, a4);
  v16 = pv[0];
  v17 = pv[1];
  v18 = v32[0];
  v19 = v32[1];
  v20 = v33[0];
  *(_OWORD *)pv = 0;
  *(_OWORD *)v32 = 0;
  *(_OWORD *)v33 = 0;
  if ( v16 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
  CoTaskMemFree(v17);
  CoTaskMemFree(v18);
  CoTaskMemFree(v19);
  CoTaskMemFree(v20);
  v21 = v34[0];
  v22 = v34[1];
  v23 = v35[0];
  v24 = v35[1];
  v25 = v36[0];
  *(_OWORD *)v34 = 0;
  *(_OWORD *)v35 = 0;
  *(_OWORD *)v36 = 0;
  if ( v21 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v21 + 16LL))(v21);
  CoTaskMemFree(v22);
  CoTaskMemFree(v23);
  CoTaskMemFree(v24);
  CoTaskMemFree(v25);
  ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>((__int64)&v28);
  return 0;
}

```

## disassembly

```asm
0x180048c3c  mov     rax, rsp
0x180048c3f  push    rbp
0x180048c40  push    rbx
0x180048c41  push    rsi
0x180048c42  push    rdi
0x180048c43  push    r12
0x180048c45  push    r14
0x180048c47  push    r15
0x180048c49  lea     rbp, [rax-5Fh]
0x180048c4d  sub     rsp, 100h
0x180048c54  movaps  xmmword ptr [rax-48h], xmm6
0x180048c58  mov     rax, cs:__security_cookie
0x180048c5f  xor     rax, rsp
0x180048c62  mov     [rbp+57h+var_50], rax
0x180048c66  mov     r12, rcx
0x180048c69  mov     r14, r9
0x180048c6c  lea     rcx, [rsp+130h+var_F8]; void *
0x180048c71  mov     rbx, r8
0x180048c74  mov     r15, rdx
0x180048c77  call    ??0?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(void)
0x180048c7c  mov     rax, [rdx]
0x180048c7f  xorps   xmm0, xmm0
0x180048c82  xorps   xmm1, xmm1
0x180048c85  mov     dword ptr [rsp+130h+var_100], 0
0x180048c8d  lea     rdx, [rsp+130h+var_F8]
0x180048c92  mov     rcx, r15
0x180048c95  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x180048c99  mov     rax, [rax+28h]
0x180048c9d  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x180048ca1  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x180048ca5  movups  xmmword ptr [rbp+57h+pv], xmm1
0x180048ca9  movups  xmmword ptr [rbp+57h+var_C0], xmm1
0x180048cad  movups  xmmword ptr [rbp+57h+var_B0], xmm1
0x180048cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048cb6  test    eax, eax
0x180048cb8  js      loc_180048E16
0x180048cbe  mov     rcx, [rsp+130h+var_F8]
0x180048cc3  lea     rdx, [rsp+130h+var_100]
0x180048cc8  mov     rax, [rcx]
0x180048ccb  mov     rax, [rax+18h]
0x180048ccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048cd4  test    eax, eax
0x180048cd6  js      loc_180048E16
0x180048cdc  cmp     dword ptr [rsp+130h+var_100], 2
0x180048ce1  jnz     loc_180048E16
0x180048ce7  mov     rcx, [rsp+130h+var_F8]
0x180048cec  lea     r8, [rbp+57h+var_A0]
0x180048cf0  xor     edx, edx
0x180048cf2  mov     rax, [rcx]
0x180048cf5  mov     rax, [rax+20h]
0x180048cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048cfe  test    eax, eax
0x180048d00  js      loc_180048E16
0x180048d06  mov     rcx, [rsp+130h+var_F8]
0x180048d0b  lea     r8, [rbp+57h+pv]
0x180048d0f  mov     edx, 1
0x180048d14  mov     rax, [rcx]
0x180048d17  mov     rax, [rax+20h]
0x180048d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048d20  test    eax, eax
0x180048d22  js      loc_180048E16
0x180048d28  mov     rdx, [rbp+57h+var_A0]
0x180048d2c  lea     rcx, [rsp+130h+var_E8]
0x180048d31  call    ??0?$CComPtr@UIShellItem@@@ATL@@QEAA@PEAUIShellItem@@@Z; ATL::CComPtr<IShellItem>::CComPtr<IShellItem>(IShellItem *)
0x180048d36  mov     rdx, [rbp+57h+pv]
0x180048d3a  lea     rcx, [rsp+130h+var_F0]
0x180048d3f  call    ??0?$CComPtr@UIShellItem@@@ATL@@QEAA@PEAUIShellItem@@@Z; ATL::CComPtr<IShellItem>::CComPtr<IShellItem>(IShellItem *)
0x180048d44  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x180048d4b  mov     esi, dword ptr [rbp+57h+var_80+8]
0x180048d4e  mov     eax, 80004005h
0x180048d53  mov     edi, dword ptr [rbp+57h+var_B0+8]
0x180048d56  movaps  [rbp+57h+Buf1], xmm6
0x180048d5a  movdqu  [rbp+57h+Buf2], xmm6
0x180048d5f  cmp     esi, 2
0x180048d62  jz      short loc_180048D76
0x180048d64  mov     rcx, qword ptr [rsp+130h+var_E8]
0x180048d69  lea     rdx, [rbp+57h+Buf1]
0x180048d6d  call    _GetPresenterClsidForItem
0x180048d72  movaps  xmm6, [rbp+57h+Buf1]
0x180048d76  cmp     edi, 2
0x180048d79  jz      short loc_180048D8D
0x180048d7b  mov     rcx, [rsp+130h+var_F0]
0x180048d80  lea     rdx, [rbp+57h+Buf2]
0x180048d84  call    _GetPresenterClsidForItem
0x180048d89  movaps  xmm6, [rbp+57h+Buf1]
0x180048d8d  test    eax, eax
0x180048d8f  js      short loc_180048E02
0x180048d91  cmp     esi, 1
0x180048d94  jnz     short loc_180048DD4
0x180048d96  cmp     edi, esi
0x180048d98  jnz     short loc_180048DCD
0x180048d9a  lea     r8d, [rsi+0Fh]; Size
0x180048d9e  lea     rdx, [rbp+57h+Buf2]; Buf2
0x180048da2  lea     rcx, [rbp+57h+Buf1]; Buf1
0x180048da6  call    memcmp_0
0x180048dab  test    eax, eax
0x180048dad  jnz     short loc_180048DB7
0x180048daf  movdqa  xmmword ptr [rsp+130h+var_E8+8], xmm6
0x180048db5  jmp     short loc_180048DE8
0x180048db7  mov     rax, [rbx]
0x180048dba  mov     edx, 1
0x180048dbf  mov     rcx, rbx
0x180048dc2  mov     rax, [rax+40h]
0x180048dc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048dcb  jmp     short loc_180048E02
0x180048dcd  cmp     edi, 2
0x180048dd0  jnz     short loc_180048E02
0x180048dd2  jmp     short loc_180048DAF
0x180048dd4  cmp     esi, 2
0x180048dd7  jnz     short loc_180048E02
0x180048dd9  cmp     edi, 1
0x180048ddc  jnz     short loc_180048E02
0x180048dde  movaps  xmm0, [rbp+57h+Buf2]
0x180048de2  movdqa  xmmword ptr [rsp+130h+var_E8+8], xmm0
0x180048de8  mov     qword ptr [rsp+130h+var_108], r14
0x180048ded  lea     rdx, [rsp+130h+var_E8+8]
0x180048df2  mov     r9, r15
0x180048df5  mov     [rsp+130h+var_110], rbx
0x180048dfa  mov     rcx, r12
0x180048dfd  call    _ResolveConflictWithPresenterClsid
0x180048e02  lea     rcx, [rsp+130h+var_F0]
0x180048e07  call    ??1?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>(void)
0x180048e0c  lea     rcx, [rsp+130h+var_E8]
0x180048e11  call    ??1?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>(void)
0x180048e16  mov     rax, [rbx]
0x180048e19  mov     rdx, r14
0x180048e1c  mov     rcx, rbx
0x180048e1f  mov     rax, [rax+20h]
0x180048e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e28  mov     rcx, [rbp+57h+pv]
0x180048e2c  xorps   xmm0, xmm0
0x180048e2f  mov     rbx, [rbp+57h+pv+8]
0x180048e33  mov     rdi, [rbp+57h+var_C0]
0x180048e37  mov     rsi, [rbp+57h+var_C0+8]
0x180048e3b  mov     r14, [rbp+57h+var_B0]
0x180048e3f  movups  xmmword ptr [rbp+57h+pv], xmm0
0x180048e43  movups  xmmword ptr [rbp+57h+var_C0], xmm0
0x180048e47  movups  xmmword ptr [rbp+57h+var_B0], xmm0
0x180048e4b  test    rcx, rcx
0x180048e4e  jz      short loc_180048E5C
0x180048e50  mov     rax, [rcx]
0x180048e53  mov     rax, [rax+10h]
0x180048e57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e5c  mov     rcx, rbx; pv
0x180048e5f  call    cs:__imp_CoTaskMemFree
0x180048e65  mov     rcx, rdi; pv
0x180048e68  call    cs:__imp_CoTaskMemFree
0x180048e6e  mov     rcx, rsi; pv
0x180048e71  call    cs:__imp_CoTaskMemFree
0x180048e77  mov     rcx, r14; pv
0x180048e7a  call    cs:__imp_CoTaskMemFree
0x180048e80  mov     rcx, [rbp+57h+var_A0]
0x180048e84  xorps   xmm0, xmm0
0x180048e87  mov     rbx, [rbp+57h+var_A0+8]
0x180048e8b  mov     rdi, [rbp+57h+var_90]
0x180048e8f  mov     rsi, [rbp+57h+var_90+8]
0x180048e93  mov     r14, [rbp+57h+var_80]
0x180048e97  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x180048e9b  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x180048e9f  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x180048ea3  test    rcx, rcx
0x180048ea6  jz      short loc_180048EB4
0x180048ea8  mov     rax, [rcx]
0x180048eab  mov     rax, [rax+10h]
0x180048eaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048eb4  mov     rcx, rbx; pv
0x180048eb7  call    cs:__imp_CoTaskMemFree
0x180048ebd  mov     rcx, rdi; pv
0x180048ec0  call    cs:__imp_CoTaskMemFree
0x180048ec6  mov     rcx, rsi; pv
0x180048ec9  call    cs:__imp_CoTaskMemFree
0x180048ecf  mov     rcx, r14; pv
0x180048ed2  call    cs:__imp_CoTaskMemFree
0x180048ed8  lea     rcx, [rsp+130h+var_F8]
0x180048edd  call    ??1?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>(void)
0x180048ee2  xor     eax, eax
0x180048ee4  mov     rcx, [rbp+57h+var_50]
0x180048ee8  xor     rcx, rsp; StackCookie
0x180048eeb  call    __security_check_cookie
0x180048ef0  movaps  xmm6, [rsp+130h+var_48+8]
0x180048ef8  add     rsp, 100h
0x180048eff  pop     r15
0x180048f01  pop     r14
0x180048f03  pop     r12
0x180048f05  pop     rdi
0x180048f06  pop     rsi
0x180048f07  pop     rbx
0x180048f08  pop     rbp
0x180048f09  retn
```
