# AppActivation::SetExtensionContext(unsigned __int64,_ActivateComponentInfo const *)

- ea: `0x18000d6b0`
- end: `0x18000dbe0`
- name: `?SetExtensionContext@AppActivation@@AEAAJ_KPEBU_ActivateComponentInfo@@@Z`
- size: `1328`
- prototype: `__int64 __fastcall(AppActivation *__hidden this, unsigned __int64, const struct _ActivateComponentInfo *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000cd40`

## callees

- `0x18000b5c0`
- `0x18000d6b0`
- `0x180011328`
- `0x180031540`
- `0x18004498c`
- `0x18005ae90`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-com-private-l1-1-0!CoRegisterRacActivationToken` at `0x18000da4e`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterRacActivationToken` at `0x18000db61`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterRacActivationToken` at `0x18000da4e`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterRacActivationToken` at `0x18000db61`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000d9dd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000d9dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall AppActivation::SetExtensionContext(
        AppActivation *this,
        __int64 a2,
        const struct _ActivateComponentInfo *a3)
{
  __int64 (__fastcall ***v6)(_QWORD, GUID *, __int64 *, wil::details::in1diag3 *); // rcx
  __int64 v8; // r15
  int v9; // eax
  unsigned int v10; // edi
  int v11; // eax
  unsigned int v12; // edi
  int v13; // eax
  unsigned int v14; // edi
  __int64 v15; // rax
  int v16; // eax
  int v17; // ebx
  __int64 v18; // rcx
  int v20; // eax
  int ActivationFactory; // edi
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rdi
  __int64 v28; // rdx
  __int64 v29; // rax
  __int64 v30; // r13
  __int64 v31; // r14
  __int64 (__fastcall *v32)(__int64, __int64, __int64, HSTRING_HEADER *); // rsi
  int v33; // eax
  unsigned int v34; // ebx
  int v35; // eax
  _QWORD *v36; // rdi
  __int64 v37; // rdx
  int v38; // [rsp+20h] [rbp-59h]
  int v39; // [rsp+20h] [rbp-59h]
  __int64 v40; // [rsp+50h] [rbp-29h] BYREF
  __int64 v41; // [rsp+58h] [rbp-21h] BYREF
  __int64 v42; // [rsp+60h] [rbp-19h]
  int v43[2]; // [rsp+68h] [rbp-11h]
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-9h] BYREF
  __int64 v45; // [rsp+88h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v6 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *, wil::details::in1diag3 *))*((_QWORD *)this + 21);
  if ( !v6 && !*((_QWORD *)this + 24) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x158,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
      (const char *)retaddr);
  v8 = 0;
  if ( (*((_DWORD *)this + 25) & 0x2010001) == 0 )
    v8 = *((_QWORD *)this + 8);
  if ( *((_QWORD *)this + 24) )
  {
    if ( !a3 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x164,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
        (const char *)retaddr);
    v41 = 0;
    v45 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Foundation.ActivationContext",
      0x25u,
      0x24u);
    v27 = v45;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
    ActivationFactory = RoGetActivationFactory(v27, &GUID_78c23c4c_270b_441b_b48d_282f8254d86c, &v41);
    if ( ActivationFactory < 0 )
    {
      v28 = 365;
LABEL_43:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v38);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
      return (unsigned int)ActivationFactory;
    }
    if ( a2 == -1 )
      a2 = 0;
    v29 = *((_QWORD *)a3 + 3);
    if ( v29 )
    {
      LODWORD(v40) = *(_DWORD *)v29;
      v42 = *(_QWORD *)(v29 + 8);
    }
    else
    {
      LODWORD(v40) = 0;
      v42 = 0;
    }
    if ( *(_QWORD *)a3 )
    {
      ActivationFactory = CoRegisterRacActivationToken(*(_QWORD *)a3, (char *)this + 224);
      if ( ActivationFactory < 0 )
      {
        v28 = 380;
        goto LABEL_43;
      }
      v30 = 0;
      *(_QWORD *)v43 = *((_QWORD *)this + 28);
    }
    else
    {
      *(_QWORD *)v43 = 0;
      v30 = *((_QWORD *)this + 10);
    }
    v31 = v41;
    v32 = *(__int64 (__fastcall **)(__int64, __int64, __int64, HSTRING_HEADER *))(*(_QWORD *)v41 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 200);
    *(_OWORD *)&hstringHeader.Reserved.Reserved1 = *((_OWORD *)this + 3);
    v39 = v43[0];
    v33 = v32(v31, a2, v30, &hstringHeader);
    v34 = v33;
    if ( v33 >= 0 )
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x185,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
      (const char *)(unsigned int)v33,
      v39);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
    return v34;
  }
  v40 = 0;
  v9 = (**v6)(v6, &GUID_533148e2_ee0a_4b06_8500_7fda28f92ae2, &v40, retaddr);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18A,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
      (const char *)(unsigned int)v9,
      v38);
    v23 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    return v10;
  }
  else
  {
    v11 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v40 + 128LL))(v40, v8);
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18B,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
        (const char *)(unsigned int)v11,
        v38);
      v24 = v40;
      if ( v40 )
      {
        v40 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      }
      return v12;
    }
    else
    {
      if ( a2 == -1
        || (v13 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v40 + 32LL))(v40, a2), v14 = v13, v13 >= 0) )
      {
        v15 = *((_QWORD *)this + 6) - *(_QWORD *)&GUID_NULL.Data1;
        if ( !v15 )
          v15 = *((_QWORD *)this + 7) - *(_QWORD *)GUID_NULL.Data4;
        if ( v15 )
        {
          *(_OWORD *)&hstringHeader.Reserved.Reserved1 = *((_OWORD *)this + 3);
          v20 = (*(__int64 (__fastcall **)(__int64, HSTRING_HEADER *))(*(_QWORD *)v40 + 64LL))(v40, &hstringHeader);
          ActivationFactory = v20;
          if ( v20 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x194,
              (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
              (const char *)(unsigned int)v20,
              v38);
            v22 = v40;
            if ( v40 )
            {
              v40 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
            }
            return (unsigned int)ActivationFactory;
          }
        }
        if ( !a3 )
        {
          v16 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v40 + 48LL))(v40, *((_QWORD *)this + 10));
          v17 = v16;
          if ( v16 >= 0 )
            goto LABEL_16;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1AA,
            (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
            (const char *)(unsigned int)v16,
            v38);
          v25 = v40;
          if ( v40 )
          {
            v40 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
          }
          return (unsigned int)v17;
        }
        if ( *((_QWORD *)a3 + 3) )
        {
          v35 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v40 + 96LL))(v40);
          ActivationFactory = v35;
          if ( v35 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x19B,
              (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
              (const char *)(unsigned int)v35,
              v38);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
            return (unsigned int)ActivationFactory;
          }
        }
        if ( *(_QWORD *)a3 )
        {
          v36 = (_QWORD *)((char *)this + 224);
          v17 = CoRegisterRacActivationToken(*(_QWORD *)a3, (char *)this + 224);
          if ( v17 < 0 )
          {
            v37 = 416;
LABEL_62:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v37,
              (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
              (const char *)(unsigned int)v17,
              v38);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
            return (unsigned int)v17;
          }
          v17 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v40 + 80LL))(v40, *v36);
          if ( v17 < 0 )
          {
            v37 = 417;
            goto LABEL_62;
          }
        }
        else
        {
          v17 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v40 + 48LL))(v40, *((_QWORD *)this + 10));
          if ( v17 < 0 )
          {
            v37 = 421;
            goto LABEL_62;
          }
        }
LABEL_16:
        v18 = v40;
        if ( v40 )
        {
          v40 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        }
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18F,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
        (const char *)(unsigned int)v13,
        v38);
      v26 = v40;
      if ( v40 )
      {
        v40 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      }
      return v14;
    }
  }
}

```

## disassembly

```asm
0x18000d6b0  mov     [rsp-8+arg_18], rbx
0x18000d6b5  push    rbp
0x18000d6b6  push    rsi
0x18000d6b7  push    rdi
0x18000d6b8  push    r12
0x18000d6ba  push    r13
0x18000d6bc  push    r14
0x18000d6be  push    r15
0x18000d6c0  lea     rbp, [rsp-27h]
0x18000d6c5  sub     rsp, 0A0h
0x18000d6cc  mov     rax, cs:__security_cookie
0x18000d6d3  xor     rax, rsp
0x18000d6d6  mov     [rbp+57h+var_40], rax
0x18000d6da  mov     rsi, r8
0x18000d6dd  mov     r12, rdx
0x18000d6e0  mov     rbx, rcx
0x18000d6e3  mov     rcx, [rcx+0A8h]
0x18000d6ea  test    rcx, rcx
0x18000d6ed  jz      loc_18000D989
0x18000d6f3  xor     dl, dl
0x18000d6f5  mov     r9, [rbp+5Fh]; char *
0x18000d6f9  test    dl, dl
0x18000d6fb  jnz     loc_18000D959
0x18000d701  test    dword ptr [rbx+64h], 2010001h
0x18000d708  mov     r14d, 0
0x18000d70e  mov     r15d, r14d
0x18000d711  cmovz   r15, [rbx+40h]
0x18000d716  cmp     [rbx+0C0h], r14
0x18000d71d  jnz     loc_18000D96E
0x18000d723  mov     [rbp+57h+var_80], r14
0x18000d727  mov     rax, [rcx]
0x18000d72a  lea     r8, [rbp+57h+var_80]
0x18000d72e  lea     rdx, _GUID_533148e2_ee0a_4b06_8500_7fda28f92ae2
0x18000d735  mov     rax, [rax]
0x18000d738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d73d  mov     edi, eax
0x18000d73f  test    eax, eax
0x18000d741  js      loc_18000D871
0x18000d747  mov     rcx, [rbp+57h+var_80]
0x18000d74b  mov     rax, [rcx]
0x18000d74e  mov     rdx, r15
0x18000d751  mov     rax, [rax+80h]
0x18000d758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d75d  mov     edi, eax
0x18000d75f  test    eax, eax
0x18000d761  js      loc_18000D8AB
0x18000d767  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x18000d76b  jz      short loc_18000D78A
0x18000d76d  mov     rcx, [rbp+57h+var_80]
0x18000d771  mov     rax, [rcx]
0x18000d774  mov     rdx, r12
0x18000d777  mov     rax, [rax+20h]
0x18000d77b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d780  mov     edi, eax
0x18000d782  test    eax, eax
0x18000d784  js      loc_18000D91F
0x18000d78a  mov     rax, [rbx+30h]
0x18000d78e  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18000d795  jnz     short loc_18000D7A2
0x18000d797  mov     rax, [rbx+38h]
0x18000d79b  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18000d7a2  test    rax, rax
0x18000d7a5  jnz     short loc_18000D811
0x18000d7a7  test    rsi, rsi
0x18000d7aa  jnz     loc_18000DB09
0x18000d7b0  mov     rcx, [rbp+57h+var_80]
0x18000d7b4  mov     rax, [rcx]
0x18000d7b7  mov     rdx, [rbx+50h]
0x18000d7bb  mov     rax, [rax+30h]
0x18000d7bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7c4  mov     ebx, eax
0x18000d7c6  test    eax, eax
0x18000d7c8  js      loc_18000D8E5
0x18000d7ce  mov     rcx, [rbp+57h+var_80]
0x18000d7d2  test    rcx, rcx
0x18000d7d5  jz      short loc_18000D7E8
0x18000d7d7  mov     [rbp+57h+var_80], r14
0x18000d7db  mov     rax, [rcx]
0x18000d7de  mov     rax, [rax+10h]
0x18000d7e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7e7  nop
0x18000d7e8  xor     eax, eax
0x18000d7ea  mov     rcx, [rbp+57h+var_40]
0x18000d7ee  xor     rcx, rsp; StackCookie
0x18000d7f1  call    __security_check_cookie
0x18000d7f6  mov     rbx, [rsp+0D0h+arg_18]
0x18000d7fe  add     rsp, 0A0h
0x18000d805  pop     r15
0x18000d807  pop     r14
0x18000d809  pop     r13
0x18000d80b  pop     r12
0x18000d80d  pop     rdi
0x18000d80e  pop     rsi
0x18000d80f  pop     rbp
0x18000d810  retn
0x18000d811  mov     rcx, [rbp+57h+var_80]
0x18000d815  movups  xmm0, xmmword ptr [rbx+30h]
0x18000d819  movaps  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x18000d81d  mov     rax, [rcx]
0x18000d820  lea     rdx, [rbp+57h+hstringHeader]
0x18000d824  mov     rax, [rax+40h]
0x18000d828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d82d  mov     edi, eax
0x18000d82f  test    eax, eax
0x18000d831  jns     loc_18000D7A7
0x18000d837  mov     rcx, [rbp+5Fh]; this
0x18000d83b  mov     r9d, eax; char *
0x18000d83e  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18000d845  mov     edx, 194h; void *
0x18000d84a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d84f  nop
0x18000d850  mov     rcx, [rbp+57h+var_80]
0x18000d854  test    rcx, rcx
0x18000d857  jz      short loc_18000D86A
0x18000d859  mov     [rbp+57h+var_80], r14
0x18000d85d  mov     rax, [rcx]
0x18000d860  mov     rax, [rax+10h]
0x18000d864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d869  nop
0x18000d86a  mov     eax, edi
0x18000d86c  jmp     loc_18000D7EA
0x18000d871  mov     rcx, [rbp+5Fh]; this
0x18000d875  mov     r9d, edi; char *
0x18000d878  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18000d87f  mov     edx, 18Ah; void *
0x18000d884  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d889  nop
0x18000d88a  mov     rcx, [rbp+57h+var_80]
0x18000d88e  test    rcx, rcx
0x18000d891  jz      short loc_18000D8A4
0x18000d893  mov     [rbp+57h+var_80], r14
0x18000d897  mov     rax, [rcx]
0x18000d89a  mov     rax, [rax+10h]
0x18000d89e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8a3  nop
0x18000d8a4  mov     eax, edi
0x18000d8a6  jmp     loc_18000D7EA
0x18000d8ab  mov     rcx, [rbp+5Fh]; this
0x18000d8af  mov     r9d, edi; char *
0x18000d8b2  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18000d8b9  mov     edx, 18Bh; void *
0x18000d8be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d8c3  nop
0x18000d8c4  mov     rcx, [rbp+57h+var_80]
0x18000d8c8  test    rcx, rcx
0x18000d8cb  jz      short loc_18000D8DE
0x18000d8cd  mov     [rbp+57h+var_80], r14
0x18000d8d1  mov     rax, [rcx]
0x18000d8d4  mov     rax, [rax+10h]
0x18000d8d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8dd  nop
0x18000d8de  mov     eax, edi
0x18000d8e0  jmp     loc_18000D7EA
0x18000d8e5  mov     rcx, [rbp+5Fh]; this
0x18000d8e9  mov     r9d, ebx; char *
0x18000d8ec  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18000d8f3  mov     edx, 1AAh; void *
0x18000d8f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d8fd  nop
0x18000d8fe  mov     rcx, [rbp+57h+var_80]
0x18000d902  test    rcx, rcx
0x18000d905  jz      short loc_18000D918
0x18000d907  mov     [rbp+57h+var_80], r14
0x18000d90b  mov     rax, [rcx]
0x18000d90e  mov     rax, [rax+10h]
0x18000d912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d917  nop
0x18000d918  mov     eax, ebx
0x18000d91a  jmp     loc_18000D7EA
0x18000d91f  mov     rcx, [rbp+5Fh]; this
0x18000d923  mov     r9d, edi; char *
0x18000d926  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18000d92d  mov     edx, 18Fh; void *
0x18000d932  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d937  nop
0x18000d938  mov     rcx, [rbp+57h+var_80]
0x18000d93c  test    rcx, rcx
0x18000d93f  jz      short loc_18000D952
0x18000d941  mov     [rbp+57h+var_80], r14
0x18000d945  mov     rax, [rcx]
0x18000d948  mov     rax, [rax+10h]
0x18000d94c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d951  nop
0x18000d952  mov     eax, edi
0x18000d954  jmp     loc_18000D7EA
0x18000d959  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18000d960  mov     edx, 158h; void *
0x18000d965  mov     rcx, r9; this
0x18000d968  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000d96e  mov     rcx, [rbp+5Fh]; this
0x18000d972  test    rsi, rsi
0x18000d975  jnz     short loc_18000D99E
0x18000d977  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18000d97e  mov     edx, 164h; void *
0x18000d983  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000d989  cmp     qword ptr [rbx+0C0h], 0
0x18000d991  jnz     loc_18000D6F3
0x18000d997  mov     dl, 1
0x18000d999  jmp     loc_18000D6F5
0x18000d99e  mov     [rbp+57h+var_78], r14
0x18000d9a2  mov     [rbp+57h+var_48], r14
0x18000d9a6  mov     r9d, 24h ; '$'; unsigned int
0x18000d9ac  mov     r8d, 25h ; '%'; unsigned int
0x18000d9b2  lea     rdx, ?RuntimeClass_Windows_Foundation_ActivationContext@@3QBGB; "Windows.Foundation.ActivationContext"
0x18000d9b9  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18000d9bd  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000d9c2  mov     rdi, [rbp+57h+var_48]
0x18000d9c6  lea     rcx, [rbp+57h+var_78]
0x18000d9ca  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000d9cf  lea     r8, [rbp+57h+var_78]
0x18000d9d3  lea     rdx, _GUID_78c23c4c_270b_441b_b48d_282f8254d86c
0x18000d9da  mov     rcx, rdi
0x18000d9dd  call    cs:__imp_RoGetActivationFactory
0x18000d9e3  mov     edi, eax
0x18000d9e5  test    eax, eax
0x18000d9e7  jns     short loc_18000DA17
0x18000d9e9  mov     edx, 16Dh
0x18000d9ee  jmp     short loc_18000D9F5
0x18000d9f0  mov     edx, 17Ch; void *
0x18000d9f5  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18000d9fc  mov     r9d, edi; char *
0x18000d9ff  mov     rcx, [rbp+5Fh]; this
0x18000da03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000da08  nop
0x18000da09  lea     rcx, [rbp+57h+var_78]
0x18000da0d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000da12  jmp     loc_18000D86A
0x18000da17  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x18000da1b  cmovz   r12, r14
0x18000da1f  mov     rax, [rsi+18h]
0x18000da23  test    rax, rax
0x18000da26  jz      short loc_18000DA37
0x18000da28  mov     edx, [rax]
0x18000da2a  mov     dword ptr [rbp+57h+var_80], edx
0x18000da2d  mov     rax, [rax+8]
0x18000da31  mov     [rbp+57h+var_70], rax
0x18000da35  jmp     short loc_18000DA3F
0x18000da37  mov     dword ptr [rbp+57h+var_80], r14d
0x18000da3b  mov     [rbp+57h+var_70], r14
0x18000da3f  mov     rcx, [rsi]
0x18000da42  test    rcx, rcx
0x18000da45  jz      short loc_18000DA6A
0x18000da47  lea     rdx, [rbx+0E0h]
0x18000da4e  call    cs:__imp_CoRegisterRacActivationToken
0x18000da54  mov     edi, eax
0x18000da56  test    eax, eax
0x18000da58  js      short loc_18000D9F0
0x18000da5a  mov     r13, r14
0x18000da5d  mov     rax, [rbx+0E0h]
0x18000da64  mov     qword ptr [rbp+57h+var_68], rax
0x18000da68  jmp     short loc_18000DA72
0x18000da6a  mov     qword ptr [rbp+57h+var_68], r14
0x18000da6e  mov     r13, [rbx+50h]
0x18000da72  mov     r14, [rbp+57h+var_78]
0x18000da76  mov     rax, [r14]
0x18000da79  mov     rsi, [rax+30h]
0x18000da7d  lea     rdi, [rbx+0C8h]
0x18000da84  mov     rcx, rdi
0x18000da87  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000da8c  movups  xmm0, xmmword ptr [rbx+30h]
0x18000da90  movaps  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x18000da94  mov     [rsp+0D0h+var_90], rdi
0x18000da99  mov     [rsp+0D0h+var_98], r15
0x18000da9e  mov     rax, [rbp+57h+var_70]
0x18000daa2  mov     [rsp+0D0h+var_A0], rax
0x18000daa7  mov     eax, dword ptr [rbp+57h+var_80]
0x18000daaa  mov     [rsp+0D0h+var_A8], eax
0x18000daae  mov     rax, qword ptr [rbp+57h+var_68]
0x18000dab2  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18000dab7  lea     r9, [rbp+57h+hstringHeader]
0x18000dabb  mov     r8, r13
0x18000dabe  mov     rdx, r12
0x18000dac1  mov     rcx, r14
0x18000dac4  mov     rax, rsi
0x18000dac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dacc  mov     ebx, eax
0x18000dace  test    eax, eax
0x18000dad0  jns     short loc_18000DAFB
0x18000dad2  mov     rcx, [rbp+5Fh]; this
0x18000dad6  mov     r9d, eax; char *
0x18000dad9  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18000dae0  mov     edx, 185h; void *
0x18000dae5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000daea  nop
0x18000daeb  lea     rcx, [rbp+57h+var_78]
0x18000daef  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000daf4  mov     eax, ebx
0x18000daf6  jmp     loc_18000D7EA
0x18000dafb  lea     rcx, [rbp+57h+var_78]
0x18000daff  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000db04  jmp     loc_18000D7E8
0x18000db09  mov     rdx, [rsi+18h]
0x18000db0d  test    rdx, rdx
0x18000db10  jz      short loc_18000DB4F
0x18000db12  mov     rcx, [rbp+57h+var_80]
0x18000db16  mov     rax, [rcx]
0x18000db19  mov     rax, [rax+60h]
0x18000db1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db22  mov     edi, eax
0x18000db24  test    eax, eax
  ... truncated ...
```
