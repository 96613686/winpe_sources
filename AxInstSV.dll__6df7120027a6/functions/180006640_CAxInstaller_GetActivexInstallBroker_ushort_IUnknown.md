# CAxInstaller::GetActivexInstallBroker(ushort * *,IUnknown * *)

- ea: `0x180006640`
- end: `0x180006911`
- name: `?GetActivexInstallBroker@CAxInstaller@@UEAAJPEAPEAGPEAPEAUIUnknown@@@Z`
- size: `721`
- prototype: `__int64 __fastcall(CAxInstaller *__hidden this, unsigned __int16 **, struct IUnknown **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180002af0`
- `0x180002c00`
- `0x180006640`
- `0x18000725c`
- `0x180015010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800068cf`
- `OLEAUT32!__imp_SysFreeString` at `0x1800068f0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800068cf`
- `OLEAUT32!__imp_SysFreeString` at `0x1800068f0`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800067e7`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800067e7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006789`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006789`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006729`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006729`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000671f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000671f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800067f4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800068a2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800067f4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800068a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066f7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800066c4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800066c4`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x1800066d9`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x1800066d9`

## string_xrefs

- `0x180006675`: `GetActivexInstallBroker called `
- `0x18000673e`: `Failed to Impersonate %x`
- `0x180006805`: `CoSetProxyBlanket on ActiveXInstallBroker failed. Error 0x%x`
- `0x18000686b`: `InitializeSystemInstaller Failed. Error 0x%x`
- `0x18000687d`: `Failed to create IeAxiSystemInstaller. Error 0x%x`

## pseudocode

```c
__int64 __fastcall CAxInstaller::GetActivexInstallBroker(
        CAxInstaller *this,
        unsigned __int16 **a2,
        struct IUnknown **a3)
{
  int v6; // ebx
  int v7; // r15d
  DWORD v8; // r8d
  HANDLE v9; // rax
  void *v10; // rbx
  WINBOOL v11; // eax
  int v12; // ebx
  void *v13; // rcx
  signed int LastError; // eax
  HRESULT v15; // eax
  unsigned __int16 *v16; // r9
  LPVOID *ppv; // [rsp+20h] [rbp-30h]
  _QWORD v19[2]; // [rsp+40h] [rbp-10h] BYREF
  WINBOOL Wow64Process; // [rsp+90h] [rbp+40h] BYREF
  LPVOID v21; // [rsp+98h] [rbp+48h] BYREF

  v19[0] = 0;
  v21 = 0;
  v6 = -2147024809;
  AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 4u, L"GetActivexInstallBroker called ");
  if ( a3 )
  {
    if ( !a2 )
    {
LABEL_32:
      if ( *a3 )
        ((void (__fastcall *)(_QWORD))(*a3)->lpVtbl->Release)(*a3);
      *a3 = 0;
      goto LABEL_35;
    }
    v7 = 0;
    *a2 = 0;
    *a3 = 0;
    v8 = *((_DWORD *)this + 166);
    Wow64Process = 0;
    v9 = OpenProcess(0x400u, 0, v8);
    v10 = v9;
    if ( v9 )
    {
      v11 = IsWow64Process(v9, &Wow64Process) && Wow64Process;
      Wow64Process = v11;
      CloseHandle(v10);
    }
    v12 = Wow64Process != 0 ? 0x40000 : 0;
    if ( *((_DWORD *)this + 176) )
    {
      v13 = (void *)*((_QWORD *)this + 89);
      if ( v13 )
      {
        if ( !ImpersonateLoggedOnUser(v13) )
        {
          LastError = GetLastError();
          v6 = LastError;
          if ( LastError > 0 )
            v6 = (unsigned __int16)LastError | 0x80070000;
          AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 2u, L"Failed to Impersonate %x", v6);
          goto LABEL_31;
        }
        v7 = 1;
      }
    }
    v15 = CoCreateInstance(
            &GUID_bdb57ff2_79b9_4205_9447_f5fe85f37312,
            0,
            v12 + 1114116,
            &GUID_a50ea6f8_4764_4299_b309_022b2a8b4d8d,
            &v21);
    v6 = v15;
    if ( v21 )
    {
      v6 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct IUnknown **))v21)(
             v21,
             &GUID_c374ce57_e034_4327_aa86_6b5d71ce604f,
             a3);
      if ( v6 < 0 )
        goto LABEL_29;
      v6 = CoSetProxyBlanket(
             *a3,
             0xFFFFFFFF,
             0xFFFFFFFF,
             (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
             0,
             3u,
             (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
             0);
      if ( v7 )
      {
        RevertToSelf();
        v7 = 0;
      }
      if ( v6 < 0 )
      {
        LODWORD(ppv) = v6;
        AxISEvents::DebugMsg(
          (AxISEvents *)&qword_180021AD8,
          8u,
          2u,
          L"CoSetProxyBlanket on ActiveXInstallBroker failed. Error 0x%x",
          ppv);
        goto LABEL_29;
      }
      v15 = (**(__int64 (__fastcall ***)(CAxInstaller *, GUID *, _QWORD *))this)(this, &IID_IUnknown, v19);
      v6 = v15;
      if ( v15 < 0 )
      {
        v16 = L"Failed to get Callback interface 0x%x";
      }
      else
      {
        v15 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD, unsigned __int16 **))(*(_QWORD *)v21 + 24LL))(
                v21,
                *((_QWORD *)this + 79),
                *((unsigned int *)this + 166),
                v19[0],
                a2);
        v6 = v15;
        if ( v15 >= 0 )
        {
          ATL::CComBSTR::operator=((char *)this + 648, *a2);
          goto LABEL_29;
        }
        v16 = L"InitializeSystemInstaller Failed. Error 0x%x";
      }
    }
    else
    {
      v16 = L"Failed to create IeAxiSystemInstaller. Error 0x%x";
    }
    LODWORD(ppv) = v15;
    AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 2u, v16, ppv);
LABEL_29:
    if ( v7 )
      RevertToSelf();
LABEL_31:
    if ( v6 >= 0 )
      goto LABEL_37;
    goto LABEL_32;
  }
LABEL_35:
  if ( a2 )
  {
    SysFreeString(*a2);
    *a2 = 0;
  }
LABEL_37:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v19);
  SysFreeString(0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180006640  mov     [rsp-28h+arg_0], rbx
0x180006645  mov     [rsp-28h+arg_8], rsi
0x18000664a  push    rbp
0x18000664b  push    rdi
0x18000664c  push    r13
0x18000664e  push    r14
0x180006650  push    r15
0x180006652  mov     rbp, rsp
0x180006655  sub     rsp, 50h
0x180006659  mov     r14, r8
0x18000665c  mov     [rbp+var_10], 0
0x180006664  mov     r8d, 4; unsigned __int8
0x18000666a  mov     [rbp+arg_18], 0
0x180006672  mov     rdi, rdx
0x180006675  lea     r9, aGetactivexinst; "GetActivexInstallBroker called "
0x18000667c  mov     rsi, rcx
0x18000667f  mov     ebx, 80070057h
0x180006684  lea     rcx, qword_180021AD8; this
0x18000668b  lea     r13d, [r8+4]
0x18000668f  mov     edx, r13d; unsigned int
0x180006692  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x180006697  test    r14, r14
0x18000669a  jz      loc_1800068C7
0x1800066a0  test    rdi, rdi
0x1800066a3  jz      loc_1800068AC
0x1800066a9  xor     r15d, r15d
0x1800066ac  xor     edx, edx; bInheritHandle
0x1800066ae  mov     [rdi], r15
0x1800066b1  mov     ecx, 400h; dwDesiredAccess
0x1800066b6  mov     [r14], r15
0x1800066b9  mov     r8d, [rsi+298h]; dwProcessId
0x1800066c0  mov     [rbp+Wow64Process], r15d
0x1800066c4  call    cs:__imp_OpenProcess
0x1800066ca  mov     rbx, rax
0x1800066cd  test    rax, rax
0x1800066d0  jz      short loc_1800066FD
0x1800066d2  lea     rdx, [rbp+Wow64Process]; Wow64Process
0x1800066d6  mov     rcx, rax; hProcess
0x1800066d9  call    cs:__imp_IsWow64Process
0x1800066df  test    eax, eax
0x1800066e1  jz      short loc_1800066EF
0x1800066e3  cmp     [rbp+Wow64Process], r15d
0x1800066e7  jz      short loc_1800066EF
0x1800066e9  lea     eax, [r13-7]
0x1800066ed  jmp     short loc_1800066F1
0x1800066ef  xor     eax, eax
0x1800066f1  mov     rcx, rbx; hObject
0x1800066f4  mov     [rbp+Wow64Process], eax
0x1800066f7  call    cs:__imp_CloseHandle
0x1800066fd  mov     eax, [rbp+Wow64Process]
0x180006700  neg     eax
0x180006702  sbb     ebx, ebx
0x180006704  and     ebx, 40000h
0x18000670a  cmp     [rsi+2C0h], r15d
0x180006711  jz      short loc_180006769
0x180006713  mov     rcx, [rsi+2C8h]; hToken
0x18000671a  test    rcx, rcx
0x18000671d  jz      short loc_180006769
0x18000671f  call    cs:__imp_ImpersonateLoggedOnUser
0x180006725  test    eax, eax
0x180006727  jnz     short loc_180006763
0x180006729  call    cs:__imp_GetLastError
0x18000672f  mov     ebx, eax
0x180006731  test    eax, eax
0x180006733  jle     short loc_18000673E
0x180006735  movzx   ebx, ax
0x180006738  or      ebx, 80070000h
0x18000673e  lea     r9, aFailedToImpers; "Failed to Impersonate %x"
0x180006745  mov     dword ptr [rsp+50h+ppv], ebx
0x180006749  mov     r8d, 2; unsigned __int8
0x18000674f  lea     rcx, qword_180021AD8; this
0x180006756  mov     edx, r13d; unsigned int
0x180006759  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x18000675e  jmp     loc_1800068A8
0x180006763  mov     r15d, 1
0x180006769  lea     rax, [rbp+arg_18]
0x18000676d  xor     edx, edx; pUnkOuter
0x18000676f  lea     r9, _GUID_a50ea6f8_4764_4299_b309_022b2a8b4d8d; riid
0x180006776  mov     [rsp+50h+ppv], rax; ppv
0x18000677b  lea     r8d, [rbx+110004h]; dwClsContext
0x180006782  lea     rcx, _GUID_bdb57ff2_79b9_4205_9447_f5fe85f37312; rclsid
0x180006789  call    cs:__imp_CoCreateInstance
0x18000678f  mov     rcx, [rbp+arg_18]
0x180006793  mov     ebx, eax
0x180006795  test    rcx, rcx
0x180006798  jz      loc_18000687D
0x18000679e  mov     rax, [rcx]
0x1800067a1  lea     rdx, _GUID_c374ce57_e034_4327_aa86_6b5d71ce604f
0x1800067a8  mov     r8, r14
0x1800067ab  mov     rax, [rax]
0x1800067ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067b3  mov     ebx, eax
0x1800067b5  test    eax, eax
0x1800067b7  js      loc_18000689D
0x1800067bd  mov     rcx, [r14]; pProxy
0x1800067c0  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x1800067c4  mov     [rsp+50h+dwCapabilities], 0; dwCapabilities
0x1800067cc  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x1800067cf  mov     [rsp+50h+pAuthInfo], r9; pAuthInfo
0x1800067d4  mov     r8d, edx; dwAuthzSvc
0x1800067d7  mov     [rsp+50h+dwImpLevel], 3; dwImpLevel
0x1800067df  mov     dword ptr [rsp+50h+ppv], 0; dwAuthnLevel
0x1800067e7  call    cs:__imp_CoSetProxyBlanket
0x1800067ed  mov     ebx, eax
0x1800067ef  test    r15d, r15d
0x1800067f2  jz      short loc_1800067FD
0x1800067f4  call    cs:__imp_RevertToSelf
0x1800067fa  xor     r15d, r15d
0x1800067fd  test    ebx, ebx
0x1800067ff  jns     short loc_18000680E
0x180006801  mov     dword ptr [rsp+50h+ppv], ebx
0x180006805  lea     r9, aCosetproxyblan; "CoSetProxyBlanket on ActiveXInstallBrok"...
0x18000680c  jmp     short loc_180006888
0x18000680e  mov     rax, [rsi]
0x180006811  lea     r8, [rbp+var_10]
0x180006815  lea     rdx, IID_IUnknown
0x18000681c  mov     rcx, rsi
0x18000681f  mov     rax, [rax]
0x180006822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006827  mov     ebx, eax
0x180006829  test    eax, eax
0x18000682b  js      short loc_180006874
0x18000682d  mov     rcx, [rbp+arg_18]
0x180006831  mov     r9, [rbp+var_10]
0x180006835  mov     r8d, [rsi+298h]
0x18000683c  mov     rdx, [rsi+278h]
0x180006843  mov     rax, [rcx]
0x180006846  mov     [rsp+50h+ppv], rdi
0x18000684b  mov     rax, [rax+18h]
0x18000684f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006854  mov     ebx, eax
0x180006856  test    eax, eax
0x180006858  js      short loc_18000686B
0x18000685a  mov     rdx, [rdi]
0x18000685d  lea     rcx, [rsi+288h]
0x180006864  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180006869  jmp     short loc_18000689D
0x18000686b  lea     r9, aInitializesyst; "InitializeSystemInstaller Failed. Error"...
0x180006872  jmp     short loc_180006884
0x180006874  lea     r9, aFailedToGetCal; "Failed to get Callback interface 0x%x"
0x18000687b  jmp     short loc_180006884
0x18000687d  lea     r9, aFailedToCreate; "Failed to create IeAxiSystemInstaller. "...
0x180006884  mov     dword ptr [rsp+50h+ppv], eax
0x180006888  mov     r8d, 2; unsigned __int8
0x18000688e  lea     rcx, qword_180021AD8; this
0x180006895  mov     edx, r13d; unsigned int
0x180006898  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x18000689d  test    r15d, r15d
0x1800068a0  jz      short loc_1800068A8
0x1800068a2  call    cs:__imp_RevertToSelf
0x1800068a8  test    ebx, ebx
0x1800068aa  jns     short loc_1800068DC
0x1800068ac  mov     rcx, [r14]
0x1800068af  test    rcx, rcx
0x1800068b2  jz      short loc_1800068C0
0x1800068b4  mov     rax, [rcx]
0x1800068b7  mov     rax, [rax+10h]
0x1800068bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068c0  mov     qword ptr [r14], 0
0x1800068c7  test    rdi, rdi
0x1800068ca  jz      short loc_1800068DC
0x1800068cc  mov     rcx, [rdi]; bstrString
0x1800068cf  call    cs:__imp_SysFreeString
0x1800068d5  mov     qword ptr [rdi], 0
0x1800068dc  lea     rcx, [rbp+arg_18]
0x1800068e0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800068e5  lea     rcx, [rbp+var_10]
0x1800068e9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800068ee  xor     ecx, ecx; bstrString
0x1800068f0  call    cs:__imp_SysFreeString
0x1800068f6  lea     r11, [rsp+50h+var_s0]
0x1800068fb  mov     eax, ebx
0x1800068fd  mov     rbx, [r11+30h]
0x180006901  mov     rsi, [r11+38h]
0x180006905  mov     rsp, r11
0x180006908  pop     r15
0x18000690a  pop     r14
0x18000690c  pop     r13
0x18000690e  pop     rdi
0x18000690f  pop     rbp
0x180006910  retn
```
