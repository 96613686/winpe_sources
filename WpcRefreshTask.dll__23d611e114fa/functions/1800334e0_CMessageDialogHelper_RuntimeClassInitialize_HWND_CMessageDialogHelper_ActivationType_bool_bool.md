# CMessageDialogHelper::RuntimeClassInitialize(HWND__ *,CMessageDialogHelper::ActivationType,bool,bool)

- ea: `0x1800334e0`
- end: `0x180033857`
- name: `?RuntimeClassInitialize@CMessageDialogHelper@@QEAAJPEAUHWND__@@W4ActivationType@1@_N2@Z`
- size: `887`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180033a44`

## callees

- `0x1800060a0`
- `0x18002eb3c`
- `0x1800334e0`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033540`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033540`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003357c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003357c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800335b6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800335b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CMessageDialogHelper::RuntimeClassInitialize(__int64 a1, __int64 a2, int a3)
{
  LPVOID v6; // rcx
  HRESULT ActivationFactory; // edi
  HRESULT v8; // eax
  int v9; // edx
  unsigned int v10; // r8d
  HSTRING v11; // rbx
  LPVOID v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rbx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v21; // [rsp+30h] [rbp-50h] BYREF
  __int64 v22; // [rsp+38h] [rbp-48h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-40h] BYREF
  __int64 v24; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+68h] [rbp-18h] BYREF

  v6 = 0;
  ppv = 0;
  if ( a3 == 1 )
  {
    ActivationFactory = CoCreateInstance(
                          &CLSID_IsolatedMessageDialogFactory,
                          0,
                          4u,
                          &GUID_2d161777_a66f_4ea5_bb87_793ffa4941f2,
                          &ppv);
    v6 = ppv;
    goto LABEL_5;
  }
  if ( a3 )
  {
    ActivationFactory = -2147418113;
    if ( a3 != 2 )
    {
LABEL_5:
      if ( ActivationFactory != -2147221164 )
        goto LABEL_10;
    }
  }
  string = 0;
  v8 = WindowsCreateStringReference(L"Windows.UI.Popups.MessageDialog", 0x1Fu, &hstringHeader, &string);
  if ( v8 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v8, v9, v10);
    JUMPOUT(0x180033856LL);
  }
  v11 = string;
  v12 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
  }
  ActivationFactory = RoGetActivationFactory(v11, &GUID_2d161777_a66f_4ea5_bb87_793ffa4941f2, &ppv);
  v6 = ppv;
LABEL_10:
  if ( ActivationFactory < 0 )
    goto LABEL_43;
  v22 = 0;
  v24 = 0;
  if ( (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))v6)(v6, &GUID_b83e0e2f_5dfd_4492_acb4_e96c848b6fab, &v24) >= 0
    && v24 )
  {
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v24 + 48LL))(
                          v24,
                          (unsigned int)a2,
                          0,
                          0,
                          &v22);
  }
  else
  {
    ActivationFactory = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)ppv + 48LL))(ppv, 0, &v22);
    if ( ActivationFactory < 0 )
      goto LABEL_38;
    if ( !a2 )
    {
LABEL_21:
      v21 = 0;
      if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v22)(
             v22,
             &GUID_6a193f22_6d3e_4803_b595_a581906c929b,
             &v21) >= 0 )
        ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 24LL))(v21, 1);
      v14 = v21;
      if ( v21 )
      {
        v21 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      }
      if ( ActivationFactory >= 0 )
      {
        if ( (unsigned int)(a3 - 1) > 1 )
          goto LABEL_33;
        v21 = 0;
        if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v22)(
               v22,
               &GUID_8ee722cd_fdcd_4aed_94af_b8b3ccc25770,
               &v21) >= 0
          && (unsigned int)(a3 - 1) <= 1 )
        {
          ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 24LL))(v21, 1);
        }
        v15 = v21;
        if ( v21 )
        {
          v21 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        }
        if ( ActivationFactory >= 0 )
        {
LABEL_33:
          v16 = v22;
          if ( *(_QWORD *)(a1 + 72) != v22 )
          {
            if ( v22 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
            v17 = *(_QWORD *)(a1 + 72);
            *(_QWORD *)(a1 + 72) = v16;
            if ( v17 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
          }
        }
      }
      goto LABEL_38;
    }
    v21 = 0;
    if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v22)(
           v22,
           &GUID_3e68d4bd_7135_4d10_8018_9fb6d9f33fa1,
           &v21) >= 0 )
      ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 24LL))(v21, a2);
    v13 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
  }
  if ( ActivationFactory >= 0 )
    goto LABEL_21;
LABEL_38:
  v18 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  v19 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  v6 = ppv;
LABEL_43:
  if ( v6 )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x1800334e0  mov     [rsp-28h+arg_10], rbx
0x1800334e5  mov     [rsp-28h+arg_18], rsi
0x1800334ea  push    rbp
0x1800334eb  push    rdi
0x1800334ec  push    r12
0x1800334ee  push    r14
0x1800334f0  push    r15
0x1800334f2  mov     rbp, rsp
0x1800334f5  sub     rsp, 80h
0x1800334fc  mov     rax, cs:__security_cookie
0x180033503  xor     rax, rsp
0x180033506  mov     [rbp+var_10], rax
0x18003350a  mov     esi, r8d
0x18003350d  mov     r14, rdx
0x180033510  mov     r15, rcx
0x180033513  xor     r12d, r12d
0x180033516  mov     ecx, r12d
0x180033519  mov     [rbp+var_40], rcx
0x18003351d  cmp     r8d, 1
0x180033521  jnz     short loc_18003354E
0x180033523  lea     rax, [rbp+var_40]
0x180033527  mov     [rsp+80h+ppv], rax; ppv
0x18003352c  lea     r9, _GUID_2d161777_a66f_4ea5_bb87_793ffa4941f2; riid
0x180033533  xor     edx, edx; pUnkOuter
0x180033535  lea     r8d, [rsi+3]; dwClsContext
0x180033539  lea     rcx, ?CLSID_IsolatedMessageDialogFactory@@3U_GUID@@A; rclsid
0x180033540  call    cs:__imp_CoCreateInstance
0x180033546  mov     edi, eax
0x180033548  mov     rcx, [rbp+var_40]
0x18003354c  jmp     short loc_18003355C
0x18003354e  test    esi, esi
0x180033550  jz      short loc_180033564
0x180033552  mov     edi, 8000FFFFh
0x180033557  cmp     esi, 2
0x18003355a  jz      short loc_180033564
0x18003355c  cmp     edi, 80040154h
0x180033562  jnz     short loc_1800335C2
0x180033564  mov     [rbp+string], r12
0x180033568  lea     r9, [rbp+string]; string
0x18003356c  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180033570  mov     edx, 1Fh; length
0x180033575  lea     rcx, ?RuntimeClass_Windows_UI_Popups_MessageDialog@@3QBGB; "Windows.UI.Popups.MessageDialog"
0x18003357c  call    cs:__imp_WindowsCreateStringReference
0x180033582  test    eax, eax
0x180033584  js      loc_18003384F
0x18003358a  mov     rbx, [rbp+string]
0x18003358e  mov     rcx, [rbp+var_40]
0x180033592  test    rcx, rcx
0x180033595  jz      short loc_1800335A8
0x180033597  mov     [rbp+var_40], r12
0x18003359b  mov     rax, [rcx]
0x18003359e  mov     rax, [rax+10h]
0x1800335a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800335a7  nop
0x1800335a8  lea     r8, [rbp+var_40]
0x1800335ac  lea     rdx, _GUID_2d161777_a66f_4ea5_bb87_793ffa4941f2
0x1800335b3  mov     rcx, rbx
0x1800335b6  call    cs:__imp_RoGetActivationFactory
0x1800335bc  mov     edi, eax
0x1800335be  mov     rcx, [rbp+var_40]
0x1800335c2  test    edi, edi
0x1800335c4  js      loc_18003380F
0x1800335ca  mov     [rbp+var_48], r12
0x1800335ce  mov     [rbp+var_38], r12
0x1800335d2  mov     rax, [rcx]
0x1800335d5  lea     r8, [rbp+var_38]
0x1800335d9  lea     rdx, _GUID_b83e0e2f_5dfd_4492_acb4_e96c848b6fab
0x1800335e0  mov     rax, [rax]
0x1800335e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800335e8  nop
0x1800335e9  test    eax, eax
0x1800335eb  js      short loc_18003363B
0x1800335ed  mov     rbx, [rbp+var_38]
0x1800335f1  test    rbx, rbx
0x1800335f4  jz      short loc_18003363B
0x1800335f6  mov     rax, [rbx]
0x1800335f9  mov     rdi, [rax+30h]
0x1800335fd  mov     rcx, [rbp+var_48]
0x180033601  test    rcx, rcx
0x180033604  jz      short loc_180033617
0x180033606  mov     [rbp+var_48], r12
0x18003360a  mov     rax, [rcx]
0x18003360d  mov     rax, [rax+10h]
0x180033611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033616  nop
0x180033617  mov     edx, r14d
0x18003361a  lea     rax, [rbp+var_48]
0x18003361e  mov     [rsp+80h+ppv], rax
0x180033623  xor     r9d, r9d
0x180033626  xor     r8d, r8d
0x180033629  mov     rcx, rbx
0x18003362c  mov     rax, rdi
0x18003362f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033634  mov     edi, eax
0x180033636  jmp     loc_1800336D2
0x18003363b  mov     rbx, [rbp+var_40]
0x18003363f  mov     rax, [rbx]
0x180033642  mov     rdi, [rax+30h]
0x180033646  mov     rcx, [rbp+var_48]
0x18003364a  test    rcx, rcx
0x18003364d  jz      short loc_180033660
0x18003364f  mov     [rbp+var_48], r12
0x180033653  mov     rdx, [rcx]
0x180033656  mov     rax, [rdx+10h]
0x18003365a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003365f  nop
0x180033660  lea     r8, [rbp+var_48]
0x180033664  xor     edx, edx
0x180033666  mov     rcx, rbx
0x180033669  mov     rax, rdi
0x18003366c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033671  mov     edi, eax
0x180033673  test    eax, eax
0x180033675  js      loc_1800337D7
0x18003367b  test    r14, r14
0x18003367e  jz      short loc_1800336DA
0x180033680  mov     [rbp+var_50], r12
0x180033684  mov     rcx, [rbp+var_48]
0x180033688  mov     rax, [rcx]
0x18003368b  lea     r8, [rbp+var_50]
0x18003368f  lea     rdx, _GUID_3e68d4bd_7135_4d10_8018_9fb6d9f33fa1
0x180033696  mov     rax, [rax]
0x180033699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003369e  nop
0x18003369f  test    eax, eax
0x1800336a1  js      short loc_1800336B8
0x1800336a3  mov     rcx, [rbp+var_50]
0x1800336a7  mov     rax, [rcx]
0x1800336aa  mov     rdx, r14
0x1800336ad  mov     rax, [rax+18h]
0x1800336b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800336b6  mov     edi, eax
0x1800336b8  mov     rcx, [rbp+var_50]
0x1800336bc  test    rcx, rcx
0x1800336bf  jz      short loc_1800336D2
0x1800336c1  mov     [rbp+var_50], r12
0x1800336c5  mov     rax, [rcx]
0x1800336c8  mov     rax, [rax+10h]
0x1800336cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800336d1  nop
0x1800336d2  test    edi, edi
0x1800336d4  js      loc_1800337D7
0x1800336da  mov     [rbp+var_50], r12
0x1800336de  mov     rcx, [rbp+var_48]
0x1800336e2  mov     rax, [rcx]
0x1800336e5  lea     r8, [rbp+var_50]
0x1800336e9  lea     rdx, _GUID_6a193f22_6d3e_4803_b595_a581906c929b
0x1800336f0  mov     rax, [rax]
0x1800336f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800336f8  nop
0x1800336f9  test    eax, eax
0x1800336fb  js      short loc_180033714
0x1800336fd  mov     rcx, [rbp+var_50]
0x180033701  mov     rax, [rcx]
0x180033704  mov     edx, 1
0x180033709  mov     rax, [rax+18h]
0x18003370d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033712  mov     edi, eax
0x180033714  mov     rcx, [rbp+var_50]
0x180033718  test    rcx, rcx
0x18003371b  jz      short loc_18003372E
0x18003371d  mov     [rbp+var_50], r12
0x180033721  mov     rax, [rcx]
0x180033724  mov     rax, [rax+10h]
0x180033728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003372d  nop
0x18003372e  test    edi, edi
0x180033730  js      loc_1800337D7
0x180033736  lea     eax, [rsi-1]
0x180033739  cmp     eax, 1
0x18003373c  ja      short loc_18003379E
0x18003373e  mov     [rbp+var_50], r12
0x180033742  mov     rcx, [rbp+var_48]
0x180033746  mov     rax, [rcx]
0x180033749  lea     r8, [rbp+var_50]
0x18003374d  lea     rdx, _GUID_8ee722cd_fdcd_4aed_94af_b8b3ccc25770
0x180033754  mov     rax, [rax]
0x180033757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003375c  nop
0x18003375d  test    eax, eax
0x18003375f  js      short loc_180033780
0x180033761  lea     eax, [rsi-1]
0x180033764  cmp     eax, 1
0x180033767  ja      short loc_180033780
0x180033769  mov     rcx, [rbp+var_50]
0x18003376d  mov     rax, [rcx]
0x180033770  mov     edx, 1
0x180033775  mov     rax, [rax+18h]
0x180033779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003377e  mov     edi, eax
0x180033780  mov     rcx, [rbp+var_50]
0x180033784  test    rcx, rcx
0x180033787  jz      short loc_18003379A
0x180033789  mov     [rbp+var_50], r12
0x18003378d  mov     rax, [rcx]
0x180033790  mov     rax, [rax+10h]
0x180033794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033799  nop
0x18003379a  test    edi, edi
0x18003379c  js      short loc_1800337D7
0x18003379e  mov     rbx, [rbp+var_48]
0x1800337a2  cmp     [r15+48h], rbx
0x1800337a6  jz      short loc_1800337D7
0x1800337a8  test    rbx, rbx
0x1800337ab  jz      short loc_1800337BD
0x1800337ad  mov     rax, [rbx]
0x1800337b0  mov     rcx, rbx
0x1800337b3  mov     rax, [rax+8]
0x1800337b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337bc  nop
0x1800337bd  mov     rcx, [r15+48h]
0x1800337c1  mov     [r15+48h], rbx
0x1800337c5  test    rcx, rcx
0x1800337c8  jz      short loc_1800337D7
0x1800337ca  mov     rax, [rcx]
0x1800337cd  mov     rax, [rax+10h]
0x1800337d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337d6  nop
0x1800337d7  mov     rcx, [rbp+var_38]
0x1800337db  test    rcx, rcx
0x1800337de  jz      short loc_1800337F1
0x1800337e0  mov     [rbp+var_38], r12
0x1800337e4  mov     rax, [rcx]
0x1800337e7  mov     rax, [rax+10h]
0x1800337eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337f0  nop
0x1800337f1  mov     rcx, [rbp+var_48]
0x1800337f5  test    rcx, rcx
0x1800337f8  jz      short loc_18003380B
0x1800337fa  mov     [rbp+var_48], r12
0x1800337fe  mov     rax, [rcx]
0x180033801  mov     rax, [rax+10h]
0x180033805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003380a  nop
0x18003380b  mov     rcx, [rbp+var_40]
0x18003380f  test    rcx, rcx
0x180033812  jz      short loc_180033825
0x180033814  mov     [rbp+var_40], r12
0x180033818  mov     rax, [rcx]
0x18003381b  mov     rax, [rax+10h]
0x18003381f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033824  nop
0x180033825  mov     eax, edi
0x180033827  mov     rcx, [rbp+var_10]
0x18003382b  xor     rcx, rsp; StackCookie
0x18003382e  call    __security_check_cookie
0x180033833  lea     r11, [rsp+80h+var_s0]
0x18003383b  mov     rbx, [r11+40h]
0x18003383f  mov     rsi, [r11+48h]
0x180033843  mov     rsp, r11
0x180033846  pop     r15
0x180033848  pop     r14
0x18003384a  pop     r12
0x18003384c  pop     rdi
0x18003384d  pop     rbp
0x18003384e  retn
0x18003384f  mov     ecx, eax; this
0x180033851  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
