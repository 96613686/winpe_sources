# UpdateReserveManager::PrepareTIForWinlogonOnline(bool *)

- ea: `0x18001c23c`
- end: `0x18001c519`
- name: `?PrepareTIForWinlogonOnline@UpdateReserveManager@@AEAAJPEA_N@Z`
- size: `733`
- prototype: `__int64 __fastcall(UpdateReserveManager *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001bd30`

## callees

- `0x180003870`
- `0x18000fafc`
- `0x18001c23c`
- `0x18001fdb8`
- `0x18001ff90`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c2bd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c2bd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001c334`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001c3ca`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001c4ee`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001c334`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001c3ca`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001c4ee`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001c27c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001c27c`

## string_xrefs

- `0x18001c2d8`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001c348`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001c3fe`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001c2e3`: `UpdateReserveManager::PrepareTIForWinlogonOnline`
- `0x18001c353`: `UpdateReserveManager::PrepareTIForWinlogonOnline`
- `0x18001c409`: `UpdateReserveManager::PrepareTIForWinlogonOnline`
- `0x18001c366`: `hrCom`
- `0x18001c2f6`: `::CoCreateInstance(CLSID_CbsSession, 0, (CLSCTX_INPROC_SERVER|CLSCTX_LOCAL_SERVER|CLSCTX_REMOTE_SERVER), __uuidof(ICbsSession10), reinterpret_cast<void**>(CbsSession.GetVoidInitPointer()))`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::PrepareTIForWinlogonOnline(UpdateReserveManager *this, bool *a2)
{
  HRESULT started; // edi
  bool v5; // bl
  HRESULT v6; // eax
  int v8; // ebx
  const char *v9; // [rsp+38h] [rbp-29h] BYREF
  const char *v10; // [rsp+40h] [rbp-21h]
  __int64 v11; // [rsp+48h] [rbp-19h]
  const char *v12; // [rsp+50h] [rbp-11h]
  const char *v13; // [rsp+58h] [rbp-9h] BYREF
  char *v14; // [rsp+60h] [rbp-1h]
  __int64 v15; // [rsp+68h] [rbp+7h]
  const char *v16; // [rsp+70h] [rbp+Fh]
  __int64 v17; // [rsp+78h] [rbp+17h]
  char v18; // [rsp+80h] [rbp+1Fh] BYREF
  LPVOID ppv; // [rsp+88h] [rbp+27h] BYREF

  v17 = -2;
  v18 = 0;
  started = CoInitializeEx(0, 0);
  v5 = 1;
  if ( started < 0 )
  {
    if ( started != -2147417850 )
    {
      v13 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      v14 = "UpdateReserveManager::PrepareTIForWinlogonOnline";
      v15 = 4194;
      v16 = "hrCom";
      RtlReportErrorOrigination(&v13, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)started);
      return (unsigned int)started;
    }
  }
  else
  {
    v18 = 1;
  }
  LOBYTE(v13) = 1;
  v14 = &v18;
  ppv = 0;
  v6 = CoCreateInstance(&CLSID_CbsSession, 0, 0x15u, &GUID_f112757a_565b_4260_bd05_9fa34417349a, &ppv);
  started = v6;
  if ( v6 >= 0 )
  {
    started = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)ppv + 24LL))(
                ppv,
                0,
                L"ReserveManager",
                0,
                0);
    if ( started < 0 )
    {
      v9 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      v10 = "UpdateReserveManager::PrepareTIForWinlogonOnline";
      v11 = 4224;
      v12 = "CbsSession->Initialize(0 , L\"ReserveManager\", nullptr , nullptr )";
      RtlReportErrorOrigination(&v9, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)started);
      if ( ppv )
      {
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        ppv = 0;
      }
      goto LABEL_7;
    }
    started = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64))(*(_QWORD *)ppv + 200LL))(ppv, 0, 9);
    if ( started == -2147024809 )
    {
      started = UpdateReserveManager::SetTIAutoStartValue(this);
      if ( started < 0 )
      {
        if ( ppv )
        {
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          ppv = 0;
        }
        goto LABEL_7;
      }
      goto LABEL_33;
    }
    if ( started < 0 )
    {
      if ( ppv )
      {
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        ppv = 0;
      }
      goto LABEL_7;
    }
  }
  else
  {
    if ( v6 != -2147023781 )
    {
      v9 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      v10 = "UpdateReserveManager::PrepareTIForWinlogonOnline";
      v11 = 4220;
      v12 = "::CoCreateInstance(CLSID_CbsSession, 0, (CLSCTX_INPROC_SERVER|CLSCTX_LOCAL_SERVER|CLSCTX_REMOTE_SERVER), __u"
            "uidof(ICbsSession10), reinterpret_cast<void**>(CbsSession.GetVoidInitPointer()))";
      RtlReportErrorOrigination(&v9, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)v6);
      if ( ppv )
      {
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        ppv = 0;
      }
LABEL_7:
      if ( v18 )
        CoUninitialize();
      return (unsigned int)started;
    }
    v8 = UpdateReserveManager::SetTIAutoStartValue(this);
    if ( v8 < 0 || (v8 = UpdateReserveManager::SetWinlogonEventsValue(this), v8 < 0) )
    {
      if ( ppv )
      {
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        ppv = 0;
      }
      if ( v18 )
        CoUninitialize();
      return (unsigned int)v8;
    }
  }
  v5 = 0;
LABEL_33:
  *a2 = v5;
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v18 )
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x18001c23c  mov     rax, rsp
0x18001c23f  push    rbp
0x18001c240  push    rsi
0x18001c241  push    rdi
0x18001c242  push    r14
0x18001c244  push    r15
0x18001c246  lea     rbp, [rax-5Fh]
0x18001c24a  sub     rsp, 90h
0x18001c251  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFEh
0x18001c259  mov     [rax+18h], rbx
0x18001c25d  mov     rax, cs:__security_cookie
0x18001c264  xor     rax, rsp
0x18001c267  mov     [rbp+57h+var_28], rax
0x18001c26b  mov     r14, rdx
0x18001c26e  mov     rsi, rcx
0x18001c271  xor     r15d, r15d
0x18001c274  mov     [rbp+57h+var_38], r15b
0x18001c278  xor     edx, edx; dwCoInit
0x18001c27a  xor     ecx, ecx; pvReserved
0x18001c27c  call    cs:__imp_CoInitializeEx
0x18001c282  mov     edi, eax
0x18001c284  mov     bl, 1
0x18001c286  test    eax, eax
0x18001c288  js      loc_18001C33C
0x18001c28e  mov     [rbp+57h+var_38], bl
0x18001c291  mov     byte ptr [rbp+57h+var_60], bl
0x18001c294  lea     rax, [rbp+57h+var_38]
0x18001c298  mov     [rbp+57h+var_58], rax
0x18001c29c  mov     [rbp+57h+ppv], r15
0x18001c2a0  lea     rax, [rbp+57h+ppv]
0x18001c2a4  mov     [rsp+20h], rax; ppv
0x18001c2a9  lea     r9, _GUID_f112757a_565b_4260_bd05_9fa34417349a; riid
0x18001c2b0  xor     edx, edx; pUnkOuter
0x18001c2b2  lea     r8d, [rdx+15h]; dwClsContext
0x18001c2b6  lea     rcx, CLSID_CbsSession; rclsid
0x18001c2bd  call    cs:__imp_CoCreateInstance
0x18001c2c3  mov     edi, eax
0x18001c2c5  test    eax, eax
0x18001c2c7  jns     loc_18001C3D7
0x18001c2cd  cmp     eax, 8007045Bh
0x18001c2d2  jz      loc_18001C38B
0x18001c2d8  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001c2df  mov     [rbp+57h+var_80], rax
0x18001c2e3  lea     rax, aUpdatereservem_27; "UpdateReserveManager::PrepareTIForWinlo"...
0x18001c2ea  mov     [rbp+57h+var_78], rax
0x18001c2ee  mov     [rbp+57h+var_70], 107Ch
0x18001c2f6  lea     rax, aCocreateinstan; "::CoCreateInstance(CLSID_CbsSession, 0,"...
0x18001c2fd  mov     [rbp+57h+var_68], rax
0x18001c301  mov     r8d, edi
0x18001c304  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001c30b  lea     rcx, [rbp+57h+var_80]
0x18001c30f  call    RtlReportErrorOrigination
0x18001c314  nop
0x18001c315  mov     rcx, [rbp+57h+ppv]
0x18001c319  test    rcx, rcx
0x18001c31c  jz      short loc_18001C32E
0x18001c31e  mov     rax, [rcx]
0x18001c321  mov     rax, [rax+10h]
0x18001c325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c32a  mov     [rbp+57h+ppv], r15
0x18001c32e  cmp     [rbp+57h+var_38], r15b
0x18001c332  jz      short loc_18001C384
0x18001c334  call    cs:__imp_CoUninitialize
0x18001c33a  jmp     short loc_18001C384
0x18001c33c  cmp     edi, 80010106h
0x18001c342  jz      loc_18001C291
0x18001c348  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001c34f  mov     [rbp+57h+var_60], rax
0x18001c353  lea     rax, aUpdatereservem_27; "UpdateReserveManager::PrepareTIForWinlo"...
0x18001c35a  mov     [rbp+57h+var_58], rax
0x18001c35e  mov     [rbp+57h+var_50], 1062h
0x18001c366  lea     rax, aHrcom; "hrCom"
0x18001c36d  mov     [rbp+57h+var_48], rax
0x18001c371  mov     r8d, edi
0x18001c374  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001c37b  lea     rcx, [rbp+57h+var_60]
0x18001c37f  call    RtlReportErrorOrigination
0x18001c384  mov     eax, edi
0x18001c386  jmp     loc_18001C4F6
0x18001c38b  mov     rcx, rsi; this
0x18001c38e  call    ?SetTIAutoStartValue@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::SetTIAutoStartValue(void)
0x18001c393  mov     ebx, eax
0x18001c395  test    eax, eax
0x18001c397  js      short loc_18001C3AB
0x18001c399  mov     rcx, rsi; this
0x18001c39c  call    ?SetWinlogonEventsValue@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::SetWinlogonEventsValue(void)
0x18001c3a1  mov     ebx, eax
0x18001c3a3  test    eax, eax
0x18001c3a5  jns     loc_18001C4C9
0x18001c3ab  mov     rcx, [rbp+57h+ppv]
0x18001c3af  test    rcx, rcx
0x18001c3b2  jz      short loc_18001C3C4
0x18001c3b4  mov     rax, [rcx]
0x18001c3b7  mov     rax, [rax+10h]
0x18001c3bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3c0  mov     [rbp+57h+ppv], r15
0x18001c3c4  cmp     [rbp+57h+var_38], r15b
0x18001c3c8  jz      short loc_18001C3D0
0x18001c3ca  call    cs:__imp_CoUninitialize
0x18001c3d0  mov     eax, ebx
0x18001c3d2  jmp     loc_18001C4F6
0x18001c3d7  mov     rcx, [rbp+57h+ppv]
0x18001c3db  mov     rax, [rcx]
0x18001c3de  mov     [rsp+20h], r15
0x18001c3e3  xor     r9d, r9d
0x18001c3e6  lea     r8, aReservemanager_0; "ReserveManager"
0x18001c3ed  xor     edx, edx
0x18001c3ef  mov     rax, [rax+18h]
0x18001c3f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3f8  mov     edi, eax
0x18001c3fa  test    eax, eax
0x18001c3fc  jns     short loc_18001C459
0x18001c3fe  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001c405  mov     [rbp+57h+var_80], rax
0x18001c409  lea     rax, aUpdatereservem_27; "UpdateReserveManager::PrepareTIForWinlo"...
0x18001c410  mov     [rbp+57h+var_78], rax
0x18001c414  mov     [rbp+57h+var_70], 1080h
0x18001c41c  lea     rax, aCbssessionInit; "CbsSession->Initialize(0 , L\"ReserveMa"...
0x18001c423  mov     [rbp+57h+var_68], rax
0x18001c427  mov     r8d, edi
0x18001c42a  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001c431  lea     rcx, [rbp+57h+var_80]
0x18001c435  call    RtlReportErrorOrigination
0x18001c43a  nop
0x18001c43b  mov     rcx, [rbp+57h+ppv]
0x18001c43f  test    rcx, rcx
0x18001c442  jz      short loc_18001C454
0x18001c444  mov     rax, [rcx]
0x18001c447  mov     rax, [rax+10h]
0x18001c44b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c450  mov     [rbp+57h+ppv], r15
0x18001c454  jmp     loc_18001C32E
0x18001c459  mov     rcx, [rbp+57h+ppv]
0x18001c45d  mov     rax, [rcx]
0x18001c460  xor     edx, edx
0x18001c462  lea     r8d, [rdx+9]
0x18001c466  mov     rax, [rax+0C8h]
0x18001c46d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c472  mov     edi, eax
0x18001c474  cmp     eax, 80070057h
0x18001c479  jnz     short loc_18001C4A7
0x18001c47b  mov     rcx, rsi; this
0x18001c47e  call    ?SetTIAutoStartValue@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::SetTIAutoStartValue(void)
0x18001c483  mov     edi, eax
0x18001c485  test    eax, eax
0x18001c487  jns     short loc_18001C4CC
0x18001c489  mov     rcx, [rbp+57h+ppv]
0x18001c48d  test    rcx, rcx
0x18001c490  jz      short loc_18001C4A2
0x18001c492  mov     rdx, [rcx]
0x18001c495  mov     rax, [rdx+10h]
0x18001c499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c49e  mov     [rbp+57h+ppv], r15
0x18001c4a2  jmp     loc_18001C32E
0x18001c4a7  test    edi, edi
0x18001c4a9  jns     short loc_18001C4C9
0x18001c4ab  mov     rcx, [rbp+57h+ppv]
0x18001c4af  test    rcx, rcx
0x18001c4b2  jz      short loc_18001C4C4
0x18001c4b4  mov     rax, [rcx]
0x18001c4b7  mov     rax, [rax+10h]
0x18001c4bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c4c0  mov     [rbp+57h+ppv], r15
0x18001c4c4  jmp     loc_18001C32E
0x18001c4c9  mov     bl, r15b
0x18001c4cc  mov     [r14], bl
0x18001c4cf  mov     rcx, [rbp+57h+ppv]
0x18001c4d3  test    rcx, rcx
0x18001c4d6  jz      short loc_18001C4E8
0x18001c4d8  mov     rax, [rcx]
0x18001c4db  mov     rax, [rax+10h]
0x18001c4df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c4e4  mov     [rbp+57h+ppv], r15
0x18001c4e8  cmp     [rbp+57h+var_38], r15b
0x18001c4ec  jz      short loc_18001C4F4
0x18001c4ee  call    cs:__imp_CoUninitialize
0x18001c4f4  xor     eax, eax
0x18001c4f6  mov     rcx, [rbp+57h+var_28]
0x18001c4fa  xor     rcx, rsp; StackCookie
0x18001c4fd  call    __security_check_cookie
0x18001c502  mov     rbx, [rsp+0B0h+arg_10]
0x18001c50a  add     rsp, 90h
0x18001c511  pop     r15
0x18001c513  pop     r14
0x18001c515  pop     rdi
0x18001c516  pop     rsi
0x18001c517  pop     rbp
0x18001c518  retn
```
