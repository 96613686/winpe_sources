# CallerIdentity::GetActiveWindowForCallingThread(HWND__ * *)

- ea: `0x1800274b8`
- end: `0x18002766f`
- name: `?GetActiveWindowForCallingThread@CallerIdentity@@YAJPEAPEAUHWND__@@@Z`
- size: `439`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, HWND *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180023e98`

## callees

- `0x18000c4cc`
- `0x18002748c`
- `0x1800274b8`
- `0x180027678`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetCallerTID` at `0x180027500`
- `api-ms-win-core-com-l1-1-0!CoGetCallerTID` at `0x180027500`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetActiveWindowForCallingThread(CallerIdentity *this, HWND *a2)
{
  CallerIdentity *v3; // rcx
  void **v4; // r8
  HRESULT CoreApplicationForCallingProcess; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, _QWORD, _QWORD); // rbx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v16)(_QWORD, GUID *, __int64 *); // rdi
  int v17; // eax
  __int64 v18; // r9
  __int64 v19; // rdx
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rdx
  struct _GUID v27; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+20h]
  DWORD dwTID; // [rsp+60h] [rbp+28h] BYREF
  unsigned int v30; // [rsp+68h] [rbp+30h] BYREF
  __int64 (__fastcall ***v31)(_QWORD, GUID *, __int64 *); // [rsp+70h] [rbp+38h] BYREF
  __int64 v32; // [rsp+78h] [rbp+40h] BYREF

  *(_QWORD *)this = 0;
  *(_QWORD *)&v27.Data1 = 0;
  Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v27, a2);
  CoreApplicationForCallingProcess = CallerIdentity::GetCoreApplicationForCallingProcess(v3, &v27, v4);
  v6 = CoreApplicationForCallingProcess;
  if ( CoreApplicationForCallingProcess < 0 )
  {
    v7 = 116;
LABEL_5:
    v9 = (unsigned int)CoreApplicationForCallingProcess;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\shell\\lib\\calleridentity\\callerwindow_twinapi.cpp",
      (const char *)v9,
      v27.Data1);
    goto LABEL_20;
  }
  dwTID = 0;
  CoreApplicationForCallingProcess = CoGetCallerTID(&dwTID);
  v6 = CoreApplicationForCallingProcess;
  if ( CoreApplicationForCallingProcess < 0 )
  {
    v7 = 119;
    goto LABEL_5;
  }
  if ( dwTID - 1 > 0xFFFFFFFD )
  {
    v6 = -2147023728;
    v7 = 124;
    v9 = 2147943568LL;
    goto LABEL_19;
  }
  v10 = *(_QWORD *)&v27.Data1;
  v31 = 0;
  v11 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(**(_QWORD **)&v27.Data1 + 72LL);
  Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v31, v8);
  v12 = v11(v10, dwTID, &v31);
  v6 = v12;
  if ( v12 >= 0 )
  {
    v15 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v31;
    v32 = 0;
    v16 = **v31;
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v32, v13);
    v17 = v16(v15, &GUID_8b09dcbb_1381_4067_8751_faebf8a056f1, &v32);
    v6 = v17;
    if ( v17 >= 0 )
    {
      v30 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v32 + 64LL))(v32, &v30);
      v6 = v20;
      if ( v20 >= 0 )
      {
        if ( v30 )
        {
          *(_QWORD *)this = v30;
          Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v32, v21);
          Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v31, v24);
          Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v27, v25);
          return 0;
        }
        v6 = -2147023728;
        v19 = 139;
        v18 = 2147943568LL;
      }
      else
      {
        v18 = (unsigned int)v20;
        v19 = 134;
      }
    }
    else
    {
      v18 = (unsigned int)v17;
      v19 = 131;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\shell\\lib\\calleridentity\\callerwindow_twinapi.cpp",
      (const char *)v18,
      v27.Data1);
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v32, v22);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x80,
      (unsigned int)"onecore\\shell\\lib\\calleridentity\\callerwindow_twinapi.cpp",
      (const char *)(unsigned int)v12,
      v27.Data1);
  }
  Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v31, v14);
LABEL_20:
  Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v27, v23);
  return v6;
}

```

## disassembly

```asm
0x1800274b8  push    rbp
0x1800274ba  push    rbx
0x1800274bb  push    rsi
0x1800274bc  push    rdi
0x1800274bd  mov     rbp, rsp
0x1800274c0  sub     rsp, 38h
0x1800274c4  mov     rsi, rcx
0x1800274c7  mov     qword ptr [rcx], 0
0x1800274ce  lea     rcx, [rbp+var_18]
0x1800274d2  mov     qword ptr [rbp+var_18.Data1], 0
0x1800274da  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x1800274df  lea     rdx, [rbp+var_18]; struct _GUID *
0x1800274e3  call    ?GetCoreApplicationForCallingProcess@CallerIdentity@@YAJAEBU_GUID@@PEAPEAX@Z; CallerIdentity::GetCoreApplicationForCallingProcess(_GUID const &,void * *)
0x1800274e8  mov     ebx, eax
0x1800274ea  test    eax, eax
0x1800274ec  jns     short loc_1800274F5
0x1800274ee  mov     edx, 74h ; 't'
0x1800274f3  jmp     short loc_180027511
0x1800274f5  lea     rcx, [rbp+dwTID]; lpdwTID
0x1800274f9  mov     [rbp+dwTID], 0
0x180027500  call    cs:__imp_CoGetCallerTID
0x180027506  mov     ebx, eax
0x180027508  test    eax, eax
0x18002750a  jns     short loc_180027519
0x18002750c  mov     edx, 77h ; 'w'
0x180027511  mov     r9d, eax
0x180027514  jmp     loc_18002764B
0x180027519  mov     eax, [rbp+dwTID]
0x18002751c  dec     eax
0x18002751e  cmp     eax, 0FFFFFFFDh
0x180027521  ja      loc_18002763E
0x180027527  mov     rdi, qword ptr [rbp+var_18.Data1]
0x18002752b  lea     rcx, [rbp+arg_10]
0x18002752f  mov     [rbp+arg_10], 0
0x180027537  mov     rax, [rdi]
0x18002753a  mov     rbx, [rax+48h]
0x18002753e  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x180027543  mov     edx, [rbp+dwTID]
0x180027546  lea     r8, [rbp+arg_10]
0x18002754a  mov     rcx, rdi
0x18002754d  mov     rax, rbx
0x180027550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027555  mov     ebx, eax
0x180027557  test    eax, eax
0x180027559  jns     short loc_180027578
0x18002755b  mov     rcx, [rbp+20h]; this
0x18002755f  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180027566  mov     r9d, eax; char *
0x180027569  mov     edx, 80h; void *
0x18002756e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027573  jmp     loc_180027611
0x180027578  mov     rbx, [rbp+arg_10]
0x18002757c  lea     rcx, [rbp+arg_18]
0x180027580  mov     [rbp+arg_18], 0
0x180027588  mov     rax, [rbx]
0x18002758b  mov     rdi, [rax]
0x18002758e  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x180027593  lea     r8, [rbp+arg_18]
0x180027597  mov     rcx, rbx
0x18002759a  lea     rdx, _GUID_8b09dcbb_1381_4067_8751_faebf8a056f1
0x1800275a1  mov     rax, rdi
0x1800275a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275a9  mov     ebx, eax
0x1800275ab  test    eax, eax
0x1800275ad  jns     short loc_1800275B9
0x1800275af  mov     r9d, eax
0x1800275b2  mov     edx, 83h
0x1800275b7  jmp     short loc_1800275F8
0x1800275b9  mov     rcx, [rbp+arg_18]
0x1800275bd  lea     rdx, [rbp+arg_8]
0x1800275c1  mov     [rbp+arg_8], 0
0x1800275c8  mov     rax, [rcx]
0x1800275cb  mov     rax, [rax+40h]
0x1800275cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275d4  mov     ebx, eax
0x1800275d6  test    eax, eax
0x1800275d8  jns     short loc_1800275E4
0x1800275da  mov     r9d, eax
0x1800275dd  mov     edx, 86h
0x1800275e2  jmp     short loc_1800275F8
0x1800275e4  mov     eax, [rbp+arg_8]
0x1800275e7  test    eax, eax
0x1800275e9  jnz     short loc_18002761C
0x1800275eb  mov     ebx, 80070490h
0x1800275f0  mov     edx, 8Bh; void *
0x1800275f5  mov     r9d, ebx; char *
0x1800275f8  mov     rcx, [rbp+20h]; this
0x1800275fc  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180027603  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027608  lea     rcx, [rbp+arg_18]
0x18002760c  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x180027611  lea     rcx, [rbp+arg_10]
0x180027615  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18002761a  jmp     short loc_18002765B
0x18002761c  lea     rcx, [rbp+arg_18]
0x180027620  mov     [rsi], rax
0x180027623  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x180027628  lea     rcx, [rbp+arg_10]
0x18002762c  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x180027631  lea     rcx, [rbp+var_18]
0x180027635  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18002763a  xor     eax, eax
0x18002763c  jmp     short loc_180027666
0x18002763e  mov     ebx, 80070490h
0x180027643  mov     edx, 7Ch ; '|'; void *
0x180027648  mov     r9d, ebx; char *
0x18002764b  mov     rcx, [rbp+20h]; this
0x18002764f  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180027656  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002765b  lea     rcx, [rbp+var_18]
0x18002765f  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x180027664  mov     eax, ebx
0x180027666  add     rsp, 38h
0x18002766a  pop     rdi
0x18002766b  pop     rsi
0x18002766c  pop     rbx
0x18002766d  pop     rbp
0x18002766e  retn
```
