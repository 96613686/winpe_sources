# AppManager::GetLaunchUri(_GUID,ushort *,_GUID *,ushort * *)

- ea: `0x180013054`
- end: `0x180013320`
- name: `?GetLaunchUri@AppManager@@QEAAJU_GUID@@PEAGPEAU2@PEAPEAG@Z`
- size: `716`
- prototype: `int(AppManager *__hidden this, struct _GUID *__struct_ptr, unsigned __int16 *, struct _GUID *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004860`

## callees

- `0x18000702c`
- `0x180013054`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800130cc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800130cc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800131c6`
- `OLEAUT32!__imp_SysFreeString` at `0x18001328d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800132a7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800132b2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800132bd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800131c6`
- `OLEAUT32!__imp_SysFreeString` at `0x18001328d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800132a7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800132b2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800132bd`
- `OLEAUT32!__imp_SysStringLen` at `0x180013198`
- `OLEAUT32!__imp_SysStringLen` at `0x18001325d`
- `OLEAUT32!__imp_SysStringLen` at `0x180013198`
- `OLEAUT32!__imp_SysStringLen` at `0x18001325d`
- `OLEAUT32!__imp_VarBstrCat` at `0x1800131b4`
- `OLEAUT32!__imp_VarBstrCat` at `0x18001327e`
- `OLEAUT32!__imp_VarBstrCat` at `0x1800131b4`
- `OLEAUT32!__imp_VarBstrCat` at `0x18001327e`

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
  int v9; // edi
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
              ATL::CComBSTR::Append((const void **)&bstrLeft, L"#");
            v9 = ATL::CComBSTR::Append((const void **)&bstrLeft, a3);
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
        v9 = ATL::CComBSTR::Append((const void **)&bstrLeft, L"?");
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
0x180013054  mov     [rsp-38h+arg_8], rbx
0x180013059  mov     [rsp-38h+bstrLeft], rcx
0x18001305e  push    rbp
0x18001305f  push    rsi
0x180013060  push    rdi
0x180013061  push    r12
0x180013063  push    r13
0x180013065  push    r14
0x180013067  push    r15
0x180013069  mov     rbp, rsp
0x18001306c  sub     rsp, 70h
0x180013070  mov     rsi, r9
0x180013073  mov     r14, r8
0x180013076  mov     r15, rdx
0x180013079  xor     r13d, r13d
0x18001307c  mov     [rbp+var_30], r13
0x180013080  mov     [rbp+arg_18], r13
0x180013084  mov     [rbp+var_10], r13
0x180013088  mov     [rbp+pbstr], r13
0x18001308c  mov     [rbp+bstrRight], r13
0x180013090  mov     ebx, r13d
0x180013093  mov     [rbp+bstrLeft], rbx
0x180013097  test    r9, r9
0x18001309a  jnz     short loc_1800130A6
0x18001309c  mov     edi, 80070057h
0x1800130a1  jmp     loc_1800132A4
0x1800130a6  mov     r12, [rbp+arg_20]
0x1800130aa  test    r12, r12
0x1800130ad  jz      short loc_18001309C
0x1800130af  lea     rax, [rbp+var_30]
0x1800130b3  mov     [rsp+70h+ppv], rax; ppv
0x1800130b8  lea     r9, IID_IPMEnumerationManager; riid
0x1800130bf  xor     edx, edx; pUnkOuter
0x1800130c1  lea     r8d, [rdx+17h]; dwClsContext
0x1800130c5  lea     rcx, CLSID_PMSvc; rclsid
0x1800130cc  call    cs:__imp_CoCreateInstance
0x1800130d2  mov     edi, eax
0x1800130d4  test    eax, eax
0x1800130d6  js      loc_1800132A4
0x1800130dc  mov     rcx, [rbp+var_30]
0x1800130e0  movaps  xmm0, xmmword ptr [r15]
0x1800130e4  movdqa  xmmword ptr [rbp+pbstrResult], xmm0
0x1800130e9  mov     rax, [rcx]
0x1800130ec  lea     r8, [rbp+arg_18]
0x1800130f0  lea     rdx, [rbp+pbstrResult]
0x1800130f4  mov     rax, [rax+48h]
0x1800130f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130fd  mov     edi, eax
0x1800130ff  test    eax, eax
0x180013101  js      loc_1800132A4
0x180013107  mov     rcx, [rbp+arg_18]
0x18001310b  mov     rax, [rcx]
0x18001310e  lea     r8, [rbp+var_10]
0x180013112  lea     rdx, _GUID_2925390a_d947_4062_9dad_cf6f60e6a707
0x180013119  mov     rax, [rax]
0x18001311c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013121  test    eax, eax
0x180013123  jns     loc_18001309C
0x180013129  mov     rcx, [rbp+arg_18]
0x18001312d  mov     rax, [rcx]
0x180013130  mov     rdx, rsi
0x180013133  mov     rax, [rax+0E0h]
0x18001313a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001313f  mov     edi, eax
0x180013141  test    eax, eax
0x180013143  js      loc_1800132A4
0x180013149  mov     rcx, [rbp+arg_18]
0x18001314d  mov     rax, [rcx]
0x180013150  lea     r8, [rbp+bstrRight]
0x180013154  lea     rdx, [rbp+pbstr]
0x180013158  mov     rax, [rax+0C8h]
0x18001315f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013164  mov     edi, eax
0x180013166  test    eax, eax
0x180013168  js      loc_1800132A4
0x18001316e  mov     rdi, [rbp+pbstr]
0x180013172  test    rdi, rdi
0x180013175  jz      loc_18001329F
0x18001317b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001317f  mov     rax, rsi
0x180013182  inc     rax
0x180013185  cmp     [rdi+rax*2], r13w
0x18001318a  jnz     short loc_180013182
0x18001318c  test    rax, rax
0x18001318f  jz      loc_18001329F
0x180013195  mov     rcx, rdi; pbstr
0x180013198  call    cs:__imp_SysStringLen
0x18001319e  test    eax, eax
0x1800131a0  jnz     short loc_1800131A7
0x1800131a2  mov     edi, r13d
0x1800131a5  jmp     short loc_1800131D4
0x1800131a7  mov     [rbp+pbstrResult], r13
0x1800131ab  lea     r8, [rbp+pbstrResult]; pbstrResult
0x1800131af  mov     rdx, rdi; bstrRight
0x1800131b2  xor     ecx, ecx; bstrLeft
0x1800131b4  call    cs:__imp_VarBstrCat
0x1800131ba  mov     edi, eax
0x1800131bc  test    eax, eax
0x1800131be  js      loc_1800132A4
0x1800131c4  xor     ecx, ecx; bstrString
0x1800131c6  call    cs:__imp_SysFreeString
0x1800131cc  mov     rbx, [rbp+pbstrResult]
0x1800131d0  mov     [rbp+bstrLeft], rbx
0x1800131d4  test    r14, r14
0x1800131d7  jz      short loc_180013228
0x1800131d9  mov     rax, rsi
0x1800131dc  inc     rax
0x1800131df  cmp     [r14+rax*2], r13w
0x1800131e4  jnz     short loc_1800131DC
0x1800131e6  test    rax, rax
0x1800131e9  jz      short loc_180013228
0x1800131eb  cmp     word ptr [r14], 2Fh ; '/'
0x1800131f0  jnz     short loc_180013202
0x1800131f2  lea     rdx, asc_180072B04; "#"
0x1800131f9  lea     rcx, [rbp+bstrLeft]; this
0x1800131fd  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x180013202  mov     rdx, r14; unsigned __int16 *
0x180013205  lea     rcx, [rbp+bstrLeft]; this
0x180013209  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18001320e  mov     edi, eax
0x180013210  test    eax, eax
0x180013212  js      loc_180013299
0x180013218  mov     rbx, [rbp+bstrLeft]
0x18001321c  mov     rax, rbx
0x18001321f  mov     rbx, r13
0x180013222  mov     [r12], rax
0x180013226  jmp     short loc_1800132A4
0x180013228  mov     rax, [rbp+bstrRight]
0x18001322c  test    rax, rax
0x18001322f  jz      short loc_18001321C
0x180013231  inc     rsi
0x180013234  cmp     [rax+rsi*2], r13w
0x180013239  jnz     short loc_180013231
0x18001323b  test    rsi, rsi
0x18001323e  jz      short loc_18001321C
0x180013240  lea     rdx, asc_180072B00; "?"
0x180013247  lea     rcx, [rbp+bstrLeft]; this
0x18001324b  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x180013250  mov     edi, eax
0x180013252  test    eax, eax
0x180013254  js      short loc_180013299
0x180013256  mov     rbx, [rbp+bstrRight]
0x18001325a  mov     rcx, rbx; pbstr
0x18001325d  call    cs:__imp_SysStringLen
0x180013263  test    eax, eax
0x180013265  jnz     short loc_18001326C
0x180013267  mov     edi, r13d
0x18001326a  jmp     short loc_180013218
0x18001326c  mov     [rbp+pbstrResult], r13
0x180013270  lea     r8, [rbp+pbstrResult]; pbstrResult
0x180013274  mov     rdx, rbx; bstrRight
0x180013277  mov     rbx, [rbp+bstrLeft]
0x18001327b  mov     rcx, rbx; bstrLeft
0x18001327e  call    cs:__imp_VarBstrCat
0x180013284  mov     edi, eax
0x180013286  test    eax, eax
0x180013288  js      short loc_1800132A4
0x18001328a  mov     rcx, rbx; bstrString
0x18001328d  call    cs:__imp_SysFreeString
0x180013293  mov     rbx, [rbp+pbstrResult]
0x180013297  jmp     short loc_18001321C
0x180013299  mov     rbx, [rbp+bstrLeft]
0x18001329d  jmp     short loc_1800132A4
0x18001329f  mov     edi, 80004005h
0x1800132a4  mov     rcx, rbx; bstrString
0x1800132a7  call    cs:__imp_SysFreeString
0x1800132ad  nop
0x1800132ae  mov     rcx, [rbp+bstrRight]; bstrString
0x1800132b2  call    cs:__imp_SysFreeString
0x1800132b8  nop
0x1800132b9  mov     rcx, [rbp+pbstr]; bstrString
0x1800132bd  call    cs:__imp_SysFreeString
0x1800132c3  nop
0x1800132c4  mov     rcx, [rbp+var_10]
0x1800132c8  test    rcx, rcx
0x1800132cb  jz      short loc_1800132DA
0x1800132cd  mov     rax, [rcx]
0x1800132d0  mov     rax, [rax+10h]
0x1800132d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132d9  nop
0x1800132da  mov     rcx, [rbp+arg_18]
0x1800132de  test    rcx, rcx
0x1800132e1  jz      short loc_1800132F0
0x1800132e3  mov     rax, [rcx]
0x1800132e6  mov     rax, [rax+10h]
0x1800132ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132ef  nop
0x1800132f0  mov     rcx, [rbp+var_30]
0x1800132f4  test    rcx, rcx
0x1800132f7  jz      short loc_180013306
0x1800132f9  mov     rax, [rcx]
0x1800132fc  mov     rax, [rax+10h]
0x180013300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013305  nop
0x180013306  mov     eax, edi
0x180013308  mov     rbx, [rsp+70h+arg_8]
0x180013310  add     rsp, 70h
0x180013314  pop     r15
0x180013316  pop     r14
0x180013318  pop     r13
0x18001331a  pop     r12
0x18001331c  pop     rdi
0x18001331d  pop     rsi
0x18001331e  pop     rbp
0x18001331f  retn
```
