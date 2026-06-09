# CActivationBrokerManager::_GetTaskIdLambda(ulong,ulong,ulong *)

- ea: `0x1800675b0`
- end: `0x180067ac0`
- name: `?_GetTaskIdLambda@CActivationBrokerManager@@AEAAJKKPEAK@Z`
- size: `1296`
- prototype: `__int64 __fastcall(CActivationBrokerManager *__hidden this, unsigned int, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180065bd0`

## callees

- `0x18000b5c0`
- `0x180011328`
- `0x1800675b0`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800678d5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800678d5`

## string_xrefs

- `0x180067631`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\activationbrokermanager.cpp`
- `0x1800678e8`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\activationbrokermanager.cpp`
- `0x180067951`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\activationbrokermanager.cpp`
- `0x180067a2a`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\activationbrokermanager.cpp`
- `0x180067a5c`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\activationbrokermanager.cpp`
- `0x180067a7b`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\activationbrokermanager.cpp`
- `0x180067a9f`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\activationbrokermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CActivationBrokerManager::_GetTaskIdLambda(
        CActivationBrokerManager *this,
        unsigned int a2,
        int a3,
        unsigned int *a4)
{
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD *); // rbx
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdx
  unsigned int v12; // r14d
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, _QWORD); // rbx
  int v15; // eax
  __int64 (__fastcall ***v16)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v17)(_QWORD, GUID *, __int64 *); // rdi
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, __int64 *); // rbx
  int v21; // eax
  unsigned int v22; // esi
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, _QWORD, _QWORD); // rbx
  __int64 (__fastcall ***v25)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v26)(_QWORD, GUID *, __int64 *); // rdi
  int v27; // eax
  __int64 v29; // rdx
  HRESULT v30; // eax
  LPVOID v31; // rdi
  __int64 (__fastcall *v32)(LPVOID, SID *, GUID *, __int64 *); // rbx
  int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // r9
  __int64 v36; // r9
  __int64 v37; // rdx
  int ppv; // [rsp+20h] [rbp-49h]
  int ppva; // [rsp+20h] [rbp-49h]
  __int64 (__fastcall ***v40)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-39h] BYREF
  __int64 v41; // [rsp+38h] [rbp-31h] BYREF
  __int64 v42; // [rsp+40h] [rbp-29h] BYREF
  __int64 v43; // [rsp+48h] [rbp-21h] BYREF
  LPVOID v44; // [rsp+50h] [rbp-19h] BYREF
  int v45; // [rsp+58h] [rbp-11h] BYREF
  unsigned int v46; // [rsp+5Ch] [rbp-Dh] BYREF
  __int64 v47; // [rsp+60h] [rbp-9h] BYREF
  int v48; // [rsp+68h] [rbp-1h] BYREF
  int v49; // [rsp+6Ch] [rbp+3h] BYREF
  int v50; // [rsp+70h] [rbp+7h] BYREF
  int v51; // [rsp+74h] [rbp+Bh] BYREF
  _QWORD v52[9]; // [rsp+78h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  int v54; // [rsp+D0h] [rbp+67h] BYREF

  v52[0] = 0;
  v7 = *((_QWORD *)this + 38);
  v8 = *(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v7 + 40LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v52);
  v9 = v8(v7, v52);
  v10 = v9;
  if ( v9 < 0 )
  {
    v11 = 996;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationbrokermanager.cpp",
      (const char *)(unsigned int)v9,
      ppv);
    goto LABEL_19;
  }
  v45 = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v52[0] + 48LL))(v52[0], &v45);
  v10 = v9;
  if ( v9 < 0 )
  {
    v11 = 1000;
    goto LABEL_5;
  }
  v12 = 0;
  if ( v45 <= 0 )
  {
LABEL_18:
    v10 = -2147319765;
    goto LABEL_19;
  }
  while ( 1 )
  {
    v40 = 0;
    v13 = v52[0];
    v14 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v52[0] + 56LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
    v15 = v14(v13, v12, &v40);
    v10 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3EC,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationbrokermanager.cpp",
        (const char *)(unsigned int)v15,
        ppv);
      goto LABEL_57;
    }
    v41 = 0;
    v16 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v40;
    v17 = **v40;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
    v18 = v17(v16, &GUID_a55d85b2_9d89_4b30_a725_6e07307073fa, &v41);
    v10 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3EF,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationbrokermanager.cpp",
        (const char *)(unsigned int)v18,
        ppv);
      goto LABEL_55;
    }
    v42 = 0;
    v19 = v41;
    v20 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v41 + 128LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
    v21 = v20(v19, &v42);
    v10 = v21;
    if ( v21 < 0 )
    {
      v37 = 1011;
      goto LABEL_52;
    }
    v54 = 0;
    v21 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v42 + 48LL))(v42, &v54);
    v10 = v21;
    if ( v21 < 0 )
    {
      v37 = 1014;
      goto LABEL_52;
    }
    v22 = 0;
    if ( v54 > 0 )
      break;
LABEL_17:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
    if ( (int)++v12 >= v45 )
      goto LABEL_18;
  }
  while ( 1 )
  {
    v23 = v42;
    v24 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v42 + 56LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
    v21 = v24(v23, v22, &v40);
    v10 = v21;
    if ( v21 < 0 )
    {
      v37 = 1017;
LABEL_52:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v37,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationbrokermanager.cpp",
        (const char *)(unsigned int)v21,
        ppv);
      goto LABEL_53;
    }
    v43 = 0;
    v25 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v40;
    v26 = **v40;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
    v27 = v26(v25, &GUID_8b494dca_e0e9_479a_adf3_023a8da54cb7, &v43);
    v10 = v27;
    if ( v27 < 0 )
    {
      v29 = 1020;
      goto LABEL_46;
    }
    v48 = 0;
    v27 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v43 + 24LL))(v43, &v48);
    v10 = v27;
    if ( v27 < 0 )
    {
      v29 = 1023;
LABEL_46:
      v36 = (unsigned int)v27;
      goto LABEL_47;
    }
    if ( a3 == v48 )
      break;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
    if ( (int)++v22 >= v54 )
      goto LABEL_17;
  }
  v46 = 0;
  v27 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v41 + 120LL))(v41, &v46);
  v10 = v27;
  if ( v27 < 0 )
  {
    v29 = 1029;
    goto LABEL_46;
  }
  v49 = 0;
  v27 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v41 + 88LL))(v41, &v49);
  v10 = v27;
  if ( v27 < 0 )
  {
    v29 = 1033;
    goto LABEL_46;
  }
  if ( v49 )
  {
    if ( v49 == a2 )
      goto LABEL_42;
    v10 = -2147319765;
    v36 = 2147647531LL;
    v29 = 1056;
LABEL_47:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationbrokermanager.cpp",
      (const char *)v36,
      ppv);
    goto LABEL_48;
  }
  v50 = 0;
  v27 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v43 + 88LL))(v43, &v50);
  v10 = v27;
  if ( v27 < 0 )
  {
    v29 = 1040;
    goto LABEL_46;
  }
  if ( v50 != 1 )
  {
    v10 = -2147319765;
    v36 = 2147647531LL;
    v29 = 1041;
    goto LABEL_47;
  }
  v44 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v44);
  v30 = CoCreateInstance(&CLSID_ShellServiceHost, 0, 0x404u, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, &v44);
  v10 = v30;
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x415,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationbrokermanager.cpp",
      (const char *)(unsigned int)v30,
      ppva);
    goto LABEL_30;
  }
  v47 = 0;
  v31 = v44;
  v32 = *(__int64 (__fastcall **)(LPVOID, SID *, GUID *, __int64 *))(*(_QWORD *)v44 + 24LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v47);
  v33 = v32(v31, &SID_ForegroundManager, &GUID_e7a2857b_dbc5_4599_a8f6_0bb15c905fc0, &v47);
  v10 = v33;
  if ( v33 < 0 )
  {
    v34 = 1048;
    goto LABEL_33;
  }
  v51 = 0;
  v33 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, int *))(*(_QWORD *)v47 + 136LL))(v47, v46, a2, &v51);
  v10 = v33;
  if ( v33 >= 0 )
  {
    if ( !v51 )
    {
      v10 = -2147319765;
      v35 = 2147647531LL;
      v34 = 1052;
      goto LABEL_34;
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v47);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v44);
LABEL_42:
    *a4 = v46;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
    v10 = 0;
    goto LABEL_19;
  }
  v34 = 1051;
LABEL_33:
  v35 = (unsigned int)v33;
LABEL_34:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v34,
    (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationbrokermanager.cpp",
    (const char *)v35,
    ppva);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v47);
LABEL_30:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v44);
LABEL_48:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
LABEL_53:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
LABEL_55:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
LABEL_57:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
LABEL_19:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v52);
  return v10;
}

```

## disassembly

```asm
0x1800675b0  push    rbp
0x1800675b2  push    rbx
0x1800675b3  push    rsi
0x1800675b4  push    rdi
0x1800675b5  push    r12
0x1800675b7  push    r13
0x1800675b9  push    r14
0x1800675bb  push    r15
0x1800675bd  lea     rbp, [rsp-1Fh]
0x1800675c2  sub     rsp, 88h
0x1800675c9  mov     r13, r9
0x1800675cc  mov     r12d, r8d
0x1800675cf  mov     r15d, edx
0x1800675d2  mov     [rbp+57h+var_48], 0
0x1800675da  mov     rdi, [rcx+130h]
0x1800675e1  mov     rax, [rdi]
0x1800675e4  mov     rbx, [rax+28h]
0x1800675e8  lea     rcx, [rbp+57h+var_48]
0x1800675ec  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800675f1  lea     rdx, [rbp+57h+var_48]
0x1800675f5  mov     rcx, rdi
0x1800675f8  mov     rax, rbx
0x1800675fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067600  mov     ebx, eax
0x180067602  xor     edi, edi
0x180067604  test    eax, eax
0x180067606  jns     short loc_18006760F
0x180067608  mov     edx, 3E4h
0x18006760d  jmp     short loc_180067631
0x18006760f  mov     [rbp+57h+var_68], edi
0x180067612  mov     rcx, [rbp+57h+var_48]
0x180067616  mov     rax, [rcx]
0x180067619  lea     rdx, [rbp+57h+var_68]
0x18006761d  mov     rax, [rax+30h]
0x180067621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067626  mov     ebx, eax
0x180067628  test    eax, eax
0x18006762a  jns     short loc_180067649
0x18006762c  mov     edx, 3E8h; void *
0x180067631  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180067638  mov     r9d, eax; char *
0x18006763b  mov     rcx, [rbp+5Fh]; this
0x18006763f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180067644  jmp     loc_180067800
0x180067649  mov     r14d, edi
0x18006764c  cmp     [rbp+57h+var_68], edi
0x18006764f  jle     loc_1800677FB
0x180067655  mov     [rbp+57h+var_90], rdi
0x180067659  mov     rdi, [rbp+57h+var_48]
0x18006765d  mov     rax, [rdi]
0x180067660  mov     rbx, [rax+38h]
0x180067664  lea     rcx, [rbp+57h+var_90]
0x180067668  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006766d  lea     r8, [rbp+57h+var_90]
0x180067671  mov     edx, r14d
0x180067674  mov     rcx, rdi
0x180067677  mov     rax, rbx
0x18006767a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006767f  mov     ebx, eax
0x180067681  test    eax, eax
0x180067683  js      loc_180067A98
0x180067689  mov     [rbp+57h+var_88], 0
0x180067691  mov     rbx, [rbp+57h+var_90]
0x180067695  mov     rax, [rbx]
0x180067698  mov     rdi, [rax]
0x18006769b  lea     rcx, [rbp+57h+var_88]
0x18006769f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800676a4  lea     r8, [rbp+57h+var_88]
0x1800676a8  lea     rdx, _GUID_a55d85b2_9d89_4b30_a725_6e07307073fa
0x1800676af  mov     rcx, rbx
0x1800676b2  mov     rax, rdi
0x1800676b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800676ba  mov     ebx, eax
0x1800676bc  test    eax, eax
0x1800676be  js      loc_180067A74
0x1800676c4  mov     [rbp+57h+var_80], 0
0x1800676cc  mov     rdi, [rbp+57h+var_88]
0x1800676d0  mov     rax, [rdi]
0x1800676d3  mov     rbx, [rax+80h]
0x1800676da  lea     rcx, [rbp+57h+var_80]
0x1800676de  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800676e3  lea     rdx, [rbp+57h+var_80]
0x1800676e7  mov     rcx, rdi
0x1800676ea  mov     rax, rbx
0x1800676ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800676f2  mov     ebx, eax
0x1800676f4  xor     edi, edi
0x1800676f6  test    eax, eax
0x1800676f8  js      loc_180067A50
0x1800676fe  mov     [rbp+57h+arg_0], edi
0x180067701  mov     rcx, [rbp+57h+var_80]
0x180067705  mov     rax, [rcx]
0x180067708  lea     rdx, [rbp+57h+arg_0]
0x18006770c  mov     rax, [rax+30h]
0x180067710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067715  mov     ebx, eax
0x180067717  test    eax, eax
0x180067719  js      loc_180067A49
0x18006771f  mov     esi, edi
0x180067721  cmp     [rbp+57h+arg_0], edi
0x180067724  jle     loc_1800677D1
0x18006772a  mov     rdi, [rbp+57h+var_80]
0x18006772e  mov     rax, [rdi]
0x180067731  mov     rbx, [rax+38h]
0x180067735  lea     rcx, [rbp+57h+var_90]
0x180067739  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006773e  lea     r8, [rbp+57h+var_90]
0x180067742  mov     edx, esi
0x180067744  mov     rcx, rdi
0x180067747  mov     rax, rbx
0x18006774a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006774f  mov     ebx, eax
0x180067751  test    eax, eax
0x180067753  js      loc_180067A42
0x180067759  mov     [rbp+57h+var_78], 0
0x180067761  mov     rbx, [rbp+57h+var_90]
0x180067765  mov     rax, [rbx]
0x180067768  mov     rdi, [rax]
0x18006776b  lea     rcx, [rbp+57h+var_78]
0x18006776f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180067774  lea     r8, [rbp+57h+var_78]
0x180067778  lea     rdx, _GUID_8b494dca_e0e9_479a_adf3_023a8da54cb7
0x18006777f  mov     rcx, rbx
0x180067782  mov     rax, rdi
0x180067785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006778a  mov     ebx, eax
0x18006778c  xor     edi, edi
0x18006778e  test    eax, eax
0x180067790  js      loc_180067A1E
0x180067796  mov     [rbp+57h+var_58], edi
0x180067799  mov     rcx, [rbp+57h+var_78]
0x18006779d  mov     rax, [rcx]
0x1800677a0  lea     rdx, [rbp+57h+var_58]
0x1800677a4  mov     rax, [rax+18h]
0x1800677a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800677ad  mov     ebx, eax
0x1800677af  test    eax, eax
0x1800677b1  js      loc_180067A17
0x1800677b7  cmp     r12d, [rbp+57h+var_58]
0x1800677bb  jz      short loc_18006781F
0x1800677bd  lea     rcx, [rbp+57h+var_78]
0x1800677c1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800677c6  inc     esi
0x1800677c8  cmp     esi, [rbp+57h+arg_0]
0x1800677cb  jl      loc_18006772A
0x1800677d1  lea     rcx, [rbp+57h+var_80]
0x1800677d5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800677da  nop
0x1800677db  lea     rcx, [rbp+57h+var_88]
0x1800677df  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800677e4  nop
0x1800677e5  lea     rcx, [rbp+57h+var_90]
0x1800677e9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800677ee  inc     r14d
0x1800677f1  cmp     r14d, [rbp+57h+var_68]
0x1800677f5  jl      loc_180067655
0x1800677fb  mov     ebx, 8002802Bh
0x180067800  lea     rcx, [rbp+57h+var_48]
0x180067804  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180067809  mov     eax, ebx
0x18006780b  add     rsp, 88h
0x180067812  pop     r15
0x180067814  pop     r14
0x180067816  pop     r13
0x180067818  pop     r12
0x18006781a  pop     rdi
0x18006781b  pop     rsi
0x18006781c  pop     rbx
0x18006781d  pop     rbp
0x18006781e  retn
0x18006781f  mov     [rbp+57h+var_64], edi
0x180067822  mov     rcx, [rbp+57h+var_88]
0x180067826  mov     rax, [rcx]
0x180067829  lea     rdx, [rbp+57h+var_64]
0x18006782d  mov     rax, [rax+78h]
0x180067831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067836  mov     ebx, eax
0x180067838  test    eax, eax
0x18006783a  jns     short loc_180067846
0x18006783c  mov     edx, 405h
0x180067841  jmp     loc_180067A23
0x180067846  mov     [rbp+57h+var_54], edi
0x180067849  mov     rcx, [rbp+57h+var_88]
0x18006784d  mov     rax, [rcx]
0x180067850  lea     rdx, [rbp+57h+var_54]
0x180067854  mov     rax, [rax+58h]
0x180067858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006785d  mov     ebx, eax
0x18006785f  test    eax, eax
0x180067861  jns     short loc_18006786D
0x180067863  mov     edx, 409h
0x180067868  jmp     loc_180067A23
0x18006786d  mov     eax, [rbp+57h+var_54]
0x180067870  test    eax, eax
0x180067872  jnz     loc_1800679CE
0x180067878  mov     [rbp+57h+var_50], edi
0x18006787b  mov     rcx, [rbp+57h+var_78]
0x18006787f  mov     rax, [rcx]
0x180067882  lea     rdx, [rbp+57h+var_50]
0x180067886  mov     rax, [rax+58h]
0x18006788a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006788f  mov     ebx, eax
0x180067891  test    eax, eax
0x180067893  jns     short loc_18006789F
0x180067895  mov     edx, 410h
0x18006789a  jmp     loc_180067A23
0x18006789f  cmp     [rbp+57h+var_50], 1
0x1800678a3  jnz     loc_1800679BF
0x1800678a9  mov     [rbp+57h+var_70], rdi
0x1800678ad  lea     rcx, [rbp+57h+var_70]
0x1800678b1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800678b6  lea     rax, [rbp+57h+var_70]
0x1800678ba  mov     qword ptr [rsp+0C0h+ppv], rax; int
0x1800678bf  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x1800678c6  xor     edx, edx; pUnkOuter
0x1800678c8  mov     r8d, 404h; dwClsContext
0x1800678ce  lea     rcx, CLSID_ShellServiceHost; rclsid
0x1800678d5  call    cs:__imp_CoCreateInstance
0x1800678db  mov     ebx, eax
0x1800678dd  test    eax, eax
0x1800678df  jns     short loc_180067908
0x1800678e1  mov     rcx, [rbp+5Fh]; this
0x1800678e5  mov     r9d, eax; char *
0x1800678e8  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800678ef  mov     edx, 415h; void *
0x1800678f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800678f9  nop
0x1800678fa  lea     rcx, [rbp+57h+var_70]
0x1800678fe  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180067903  jmp     loc_180067A37
0x180067908  mov     [rbp+57h+var_60], rdi
0x18006790c  mov     rdi, [rbp+57h+var_70]
0x180067910  mov     rax, [rdi]
0x180067913  mov     rbx, [rax+18h]
0x180067917  lea     rcx, [rbp+57h+var_60]
0x18006791b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180067920  lea     r9, [rbp+57h+var_60]
0x180067924  lea     r8, _GUID_e7a2857b_dbc5_4599_a8f6_0bb15c905fc0
0x18006792b  lea     rdx, SID_ForegroundManager
0x180067932  mov     rcx, rdi
0x180067935  mov     rax, rbx
0x180067938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006793d  mov     ebx, eax
0x18006793f  xor     edi, edi
0x180067941  test    eax, eax
0x180067943  jns     short loc_180067969
0x180067945  mov     edx, 418h; void *
0x18006794a  mov     r9d, eax; char *
0x18006794d  mov     rcx, [rbp+5Fh]; this
0x180067951  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180067958  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006795d  nop
0x18006795e  lea     rcx, [rbp+57h+var_60]
0x180067962  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180067967  jmp     short loc_1800678FA
0x180067969  mov     [rbp+57h+var_4C], edi
0x18006796c  mov     rcx, [rbp+57h+var_60]
0x180067970  mov     rax, [rcx]
0x180067973  lea     r9, [rbp+57h+var_4C]
0x180067977  mov     r8d, r15d
0x18006797a  mov     edx, [rbp+57h+var_64]
0x18006797d  mov     rax, [rax+88h]
0x180067984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067989  mov     ebx, eax
0x18006798b  test    eax, eax
0x18006798d  jns     short loc_180067996
0x18006798f  mov     edx, 41Bh
0x180067994  jmp     short loc_18006794A
0x180067996  cmp     [rbp+57h+var_4C], edi
0x180067999  jz      short loc_1800679B0
0x18006799b  lea     rcx, [rbp+57h+var_60]
0x18006799f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800679a4  nop
0x1800679a5  lea     rcx, [rbp+57h+var_70]
0x1800679a9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800679ae  jmp     short loc_1800679D3
0x1800679b0  mov     ebx, 8002802Bh
0x1800679b5  mov     r9d, ebx
0x1800679b8  mov     edx, 41Ch
0x1800679bd  jmp     short loc_18006794D
0x1800679bf  mov     ebx, 8002802Bh
0x1800679c4  mov     r9d, ebx
0x1800679c7  mov     edx, 411h
0x1800679cc  jmp     short loc_180067A26
0x1800679ce  cmp     eax, r15d
0x1800679d1  jnz     short loc_180067A08
0x1800679d3  mov     eax, [rbp+57h+var_64]
0x1800679d6  mov     [r13+0], eax
0x1800679da  lea     rcx, [rbp+57h+var_78]
0x1800679de  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800679e3  nop
0x1800679e4  lea     rcx, [rbp+57h+var_80]
0x1800679e8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800679ed  nop
0x1800679ee  lea     rcx, [rbp+57h+var_88]
0x1800679f2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800679f7  nop
0x1800679f8  lea     rcx, [rbp+57h+var_90]
0x1800679fc  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180067a01  mov     ebx, edi
  ... truncated ...
```
