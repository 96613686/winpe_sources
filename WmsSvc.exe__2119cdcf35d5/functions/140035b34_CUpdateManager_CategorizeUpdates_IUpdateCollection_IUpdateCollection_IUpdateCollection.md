# CUpdateManager::CategorizeUpdates(IUpdateCollection *,IUpdateCollection * *,IUpdateCollection * *)

- ea: `0x140035b34`
- end: `0x140035eba`
- name: `?CategorizeUpdates@CUpdateManager@@IEAAJPEAUIUpdateCollection@@PEAPEAU2@1@Z`
- size: `902`
- prototype: `__int64 __fastcall(CUpdateManager *this, struct IUpdateCollection *, LPVOID *, LPVOID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x1400373f4`

## callees

- `0x140035b34`
- `0x140038f78`
- `0x140039114`
- `0x140039328`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007e010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140035be5`
- `KERNEL32!IsDebuggerPresent` at `0x140035be5`
- `ole32!CoCreateInstance` at `0x140035d50`
- `ole32!CoCreateInstance` at `0x140035dbb`
- `ole32!CoCreateInstance` at `0x140035d50`
- `ole32!CoCreateInstance` at `0x140035dbb`
- `OLEAUT32!__imp_SysFreeString` at `0x140035c76`
- `OLEAUT32!__imp_SysFreeString` at `0x140035e6e`
- `OLEAUT32!__imp_SysFreeString` at `0x140035c76`
- `OLEAUT32!__imp_SysFreeString` at `0x140035e6e`

## string_xrefs

- `0x140035bc4`: `termsrv\wms\src\devices\wmssvc\updatemanager.cpp`
- `0x140035b53`: `CUpdateManager::CategorizeUpdates - Enter.\n`
- `0x140035baf`: `CUpdateManager::CategorizeUpdates`
- `0x140035cd6`: `CUpdateManager::CategorizeUpdates - Update "%s" can request user input, skipping.\n`
- `0x140035d08`: `CUpdateManager::CategorizeUpdates - Update "%s" is a service pack, skipping.\n`
- `0x140035d64`: `CUpdateManager::CategorizeUpdates - Update "%s" requires exclusive handling, adding to exclusive list.\n`
- `0x140035dcf`: `CUpdateManager::CategorizeUpdates - Update "%s" being added to list.\n`

## pseudocode

```c
__int64 __fastcall CUpdateManager::CategorizeUpdates(
        CUpdateManager *this,
        struct IUpdateCollection *a2,
        LPVOID *a3,
        LPVOID *a4)
{
  HRESULT updated; // ebx
  unsigned int v8; // r13d
  unsigned int v9; // edi
  CUpdateManager *v10; // rcx
  CUpdateManager *v11; // rcx
  CUpdateManager *v12; // rcx
  int v14; // [rsp+40h] [rbp-30h] BYREF
  int v15; // [rsp+44h] [rbp-2Ch] BYREF
  int v16; // [rsp+48h] [rbp-28h] BYREF
  struct IUpdate *v17; // [rsp+50h] [rbp-20h] BYREF
  LPVOID v18; // [rsp+58h] [rbp-18h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-10h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-8h] BYREF
  int v21; // [rsp+B0h] [rbp+40h] BYREF
  int v22; // [rsp+B4h] [rbp+44h]
  int v23; // [rsp+B8h] [rbp+48h] BYREF

  v22 = HIDWORD(this);
  v21 = 0;
  v16 = 0;
  v17 = 0;
  v23 = 0;
  v14 = 0;
  v15 = 0;
  ppv = 0;
  v18 = 0;
  bstrString = 0;
  DEBUGMSG(L"CUpdateManager::CategorizeUpdates - Enter.\n");
  updated = ((__int64 (__fastcall *)(struct IUpdateCollection *, int *))a2->lpVtbl->get_Count)(a2, &v21);
  if ( updated >= 0 )
  {
    v9 = 0;
    if ( v21 <= 0 )
    {
LABEL_27:
      *a3 = ppv;
      *a4 = v18;
      ppv = 0;
      v18 = 0;
    }
    else
    {
      while ( 1 )
      {
        if ( v17 )
        {
          ((void (__fastcall *)(struct IUpdate *))v17->lpVtbl->Release)(v17);
          v17 = 0;
        }
        SysFreeString(bstrString);
        updated = ((__int64 (__fastcall *)(struct IUpdateCollection *, _QWORD, struct IUpdate **))a2->lpVtbl->get_Item)(
                    a2,
                    v9,
                    &v17);
        if ( updated < 0 )
          break;
        updated = ((__int64 (__fastcall *)(struct IUpdate *, BSTR *))v17->lpVtbl->get_Title)(v17, &bstrString);
        if ( updated < 0 )
        {
          v8 = 1454;
          goto LABEL_3;
        }
        updated = CUpdateManager::UpdateNeedsUserInput(v10, v17, &v23);
        if ( updated < 0 )
          break;
        if ( v23 )
        {
          DEBUGMSG(L"CUpdateManager::CategorizeUpdates - Update \"%s\" can request user input, skipping.\n", bstrString);
        }
        else
        {
          updated = CUpdateManager::UpdateIsServicePack(v11, v17, &v14);
          if ( updated < 0 )
            break;
          if ( v14 )
          {
            DEBUGMSG(L"CUpdateManager::CategorizeUpdates - Update \"%s\" is a service pack, skipping.\n", bstrString);
          }
          else
          {
            updated = CUpdateManager::UpdateIsExclusive(v12, v17, &v15);
            if ( updated < 0 )
              break;
            if ( v15 )
            {
              if ( !ppv )
              {
                updated = CoCreateInstance(
                            &GUID_13639463_00db_4646_803d_528026140d88,
                            0,
                            1u,
                            &GUID_07f7438c_7709_4ca5_b518_91279288134e,
                            &ppv);
                if ( updated < 0 )
                {
                  v8 = 1494;
                  goto LABEL_3;
                }
              }
              DEBUGMSG(
                L"CUpdateManager::CategorizeUpdates - Update \"%s\" requires exclusive handling, adding to exclusive list.\n",
                bstrString);
              updated = (*(__int64 (__fastcall **)(LPVOID, struct IUpdate *, int *))(*(_QWORD *)ppv + 96LL))(
                          ppv,
                          v17,
                          &v16);
              if ( updated < 0 )
              {
                v8 = 1500;
                goto LABEL_3;
              }
            }
            else
            {
              if ( !v18 )
              {
                updated = CoCreateInstance(
                            &GUID_13639463_00db_4646_803d_528026140d88,
                            0,
                            1u,
                            &GUID_07f7438c_7709_4ca5_b518_91279288134e,
                            &v18);
                if ( updated < 0 )
                {
                  v8 = 1507;
                  goto LABEL_3;
                }
              }
              DEBUGMSG(L"CUpdateManager::CategorizeUpdates - Update \"%s\" being added to list.\n", bstrString);
              updated = (*(__int64 (__fastcall **)(LPVOID, struct IUpdate *, int *))(*(_QWORD *)v18 + 96LL))(
                          v18,
                          v17,
                          &v16);
              if ( updated < 0 )
              {
                v8 = 1513;
                goto LABEL_3;
              }
            }
          }
        }
        if ( (int)++v9 >= v21 )
          goto LABEL_27;
      }
    }
  }
  else
  {
    v8 = 1443;
LABEL_3:
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
      v8,
      L"CUpdateManager::CategorizeUpdates",
      L"CHRA",
      L"hr",
      updated);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
        v8,
        L"CUpdateManager::CategorizeUpdates",
        L"CHRA",
        L"hr",
        updated);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
        v8,
        L"CUpdateManager::CategorizeUpdates",
        L"CHRA",
        L"hr",
        updated);
  }
  if ( v18 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v17 )
  {
    ((void (__fastcall *)(struct IUpdate *))v17->lpVtbl->Release)(v17);
    v17 = 0;
  }
  SysFreeString(bstrString);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x140035b34  mov     [rsp-38h+arg_10], rbx
0x140035b39  mov     [rsp-38h+arg_0], rcx
0x140035b3e  push    rbp
0x140035b3f  push    rsi
0x140035b40  push    rdi
0x140035b41  push    r12
0x140035b43  push    r13
0x140035b45  push    r14
0x140035b47  push    r15
0x140035b49  mov     rbp, rsp
0x140035b4c  sub     rsp, 70h
0x140035b50  xor     r12d, r12d
0x140035b53  lea     rcx, aCupdatemanager_59; "CUpdateManager::CategorizeUpdates - Ent"...
0x140035b5a  mov     dword ptr [rbp+arg_0], r12d
0x140035b5e  mov     r14, r9
0x140035b61  mov     [rbp+var_28], r12d
0x140035b65  mov     r15, r8
0x140035b68  mov     [rbp+var_20], r12
0x140035b6c  mov     rsi, rdx
0x140035b6f  mov     [rbp+arg_8], r12d
0x140035b73  mov     [rbp+var_30], r12d
0x140035b77  mov     [rbp+var_2C], r12d
0x140035b7b  mov     [rbp+var_10], r12
0x140035b7f  mov     [rbp+var_18], r12
0x140035b83  mov     [rbp+bstrString], r12
0x140035b87  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140035b8c  mov     rax, [rsi]
0x140035b8f  lea     rdx, [rbp+arg_0]
0x140035b93  mov     rcx, rsi
0x140035b96  mov     rax, [rax+50h]
0x140035b9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035b9f  mov     ebx, eax
0x140035ba1  test    eax, eax
0x140035ba3  jns     loc_140035C46
0x140035ba9  mov     r13d, 5A3h
0x140035baf  lea     rsi, aCupdatemanager_81; "CUpdateManager::CategorizeUpdates"
0x140035bb6  mov     [rsp+70h+var_48], ebx; int
0x140035bba  lea     r15, aChra; "CHRA"
0x140035bc1  mov     r8, rsi; unsigned __int16 *
0x140035bc4  lea     rdi, aTermsrvWmsSrcD_7; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x140035bcb  mov     r9, r15; unsigned __int16 *
0x140035bce  lea     r14, aHr; "hr"
0x140035bd5  mov     rcx, rdi; unsigned __int16 *
0x140035bd8  mov     edx, r13d; unsigned int
0x140035bdb  mov     [rsp+70h+ppv], r14; unsigned __int16 *
0x140035be0  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140035be5  call    cs:__imp_IsDebuggerPresent
0x140035beb  test    eax, eax
0x140035bed  jz      short loc_140035C1E
0x140035bef  mov     [rsp+70h+var_38], ebx
0x140035bf3  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140035bfa  mov     [rsp+70h+var_40], r14
0x140035bff  mov     r9d, r13d
0x140035c02  mov     qword ptr [rsp+70h+var_48], r15
0x140035c07  mov     r8, rdi
0x140035c0a  mov     ecx, 2; unsigned __int8
0x140035c0f  mov     [rsp+70h+ppv], rsi
0x140035c14  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140035c19  jmp     loc_140035E1F
0x140035c1e  mov     dword ptr [rsp+70h+var_40], ebx
0x140035c22  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140035c29  mov     qword ptr [rsp+70h+var_48], r14
0x140035c2e  mov     r9, rsi
0x140035c31  mov     r8d, r13d
0x140035c34  mov     [rsp+70h+ppv], r15
0x140035c39  mov     rdx, rdi
0x140035c3c  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140035c41  jmp     loc_140035E1F
0x140035c46  mov     edi, r12d
0x140035c49  cmp     dword ptr [rbp+arg_0], r12d
0x140035c4d  jle     loc_140035E09
0x140035c53  mov     r13d, 1
0x140035c59  mov     rcx, [rbp+var_20]
0x140035c5d  test    rcx, rcx
0x140035c60  jz      short loc_140035C72
0x140035c62  mov     rax, [rcx]
0x140035c65  mov     rax, [rax+10h]
0x140035c69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035c6e  mov     [rbp+var_20], r12
0x140035c72  mov     rcx, [rbp+bstrString]; bstrString
0x140035c76  call    cs:__imp_SysFreeString
0x140035c7c  mov     rax, [rsi]
0x140035c7f  lea     r8, [rbp+var_20]
0x140035c83  mov     edx, edi
0x140035c85  mov     rcx, rsi
0x140035c88  mov     rax, [rax+38h]
0x140035c8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035c91  mov     ebx, eax
0x140035c93  test    eax, eax
0x140035c95  js      loc_140035E1F
0x140035c9b  mov     rcx, [rbp+var_20]
0x140035c9f  lea     rdx, [rbp+bstrString]
0x140035ca3  mov     rax, [rcx]
0x140035ca6  mov     rax, [rax+38h]
0x140035caa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035caf  mov     ebx, eax
0x140035cb1  test    eax, eax
0x140035cb3  js      loc_140035EAF
0x140035cb9  mov     rdx, [rbp+var_20]; struct IUpdate *
0x140035cbd  lea     r8, [rbp+arg_8]; int *
0x140035cc1  call    ?UpdateNeedsUserInput@CUpdateManager@@IEAAJPEAUIUpdate@@PEAH@Z; CUpdateManager::UpdateNeedsUserInput(IUpdate *,int *)
0x140035cc6  mov     ebx, eax
0x140035cc8  test    eax, eax
0x140035cca  js      loc_140035E1F
0x140035cd0  cmp     [rbp+arg_8], r12d
0x140035cd4  jz      short loc_140035CEB
0x140035cd6  lea     rcx, aCupdatemanager_74; "CUpdateManager::CategorizeUpdates - Upd"...
0x140035cdd  mov     rdx, [rbp+bstrString]
0x140035ce1  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140035ce6  jmp     loc_140035DFD
0x140035ceb  mov     rdx, [rbp+var_20]; struct IUpdate *
0x140035cef  lea     r8, [rbp+var_30]; int *
0x140035cf3  call    ?UpdateIsServicePack@CUpdateManager@@IEAAJPEAUIUpdate@@PEAH@Z; CUpdateManager::UpdateIsServicePack(IUpdate *,int *)
0x140035cf8  mov     ebx, eax
0x140035cfa  test    eax, eax
0x140035cfc  js      loc_140035E1F
0x140035d02  cmp     [rbp+var_30], r12d
0x140035d06  jz      short loc_140035D11
0x140035d08  lea     rcx, aCupdatemanager_41; "CUpdateManager::CategorizeUpdates - Upd"...
0x140035d0f  jmp     short loc_140035CDD
0x140035d11  mov     rdx, [rbp+var_20]; struct IUpdate *
0x140035d15  lea     r8, [rbp+var_2C]; int *
0x140035d19  call    ?UpdateIsExclusive@CUpdateManager@@IEAAJPEAUIUpdate@@PEAH@Z; CUpdateManager::UpdateIsExclusive(IUpdate *,int *)
0x140035d1e  mov     ebx, eax
0x140035d20  test    eax, eax
0x140035d22  js      loc_140035E1F
0x140035d28  cmp     [rbp+var_2C], r12d
0x140035d2c  jz      short loc_140035D99
0x140035d2e  cmp     [rbp+var_10], r12
0x140035d32  jnz     short loc_140035D60
0x140035d34  lea     rax, [rbp+var_10]
0x140035d38  mov     r8d, r13d; dwClsContext
0x140035d3b  lea     r9, _GUID_07f7438c_7709_4ca5_b518_91279288134e; riid
0x140035d42  mov     [rsp+70h+ppv], rax; ppv
0x140035d47  xor     edx, edx; pUnkOuter
0x140035d49  lea     rcx, _GUID_13639463_00db_4646_803d_528026140d88; rclsid
0x140035d50  call    cs:__imp_CoCreateInstance
0x140035d56  mov     ebx, eax
0x140035d58  test    eax, eax
0x140035d5a  js      loc_140035E8E
0x140035d60  mov     rdx, [rbp+bstrString]
0x140035d64  lea     rcx, aCupdatemanager_22; "CUpdateManager::CategorizeUpdates - Upd"...
0x140035d6b  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140035d70  mov     rcx, [rbp+var_10]
0x140035d74  lea     r8, [rbp+var_28]
0x140035d78  mov     rdx, [rbp+var_20]
0x140035d7c  mov     rax, [rcx]
0x140035d7f  mov     rax, [rax+60h]
0x140035d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035d88  mov     ebx, eax
0x140035d8a  test    eax, eax
0x140035d8c  jns     short loc_140035DFD
0x140035d8e  mov     r13d, 5DCh
0x140035d94  jmp     loc_140035BAF
0x140035d99  cmp     [rbp+var_18], r12
0x140035d9d  jnz     short loc_140035DCB
0x140035d9f  lea     rax, [rbp+var_18]
0x140035da3  mov     r8d, r13d; dwClsContext
0x140035da6  lea     r9, _GUID_07f7438c_7709_4ca5_b518_91279288134e; riid
0x140035dad  mov     [rsp+70h+ppv], rax; ppv
0x140035db2  xor     edx, edx; pUnkOuter
0x140035db4  lea     rcx, _GUID_13639463_00db_4646_803d_528026140d88; rclsid
0x140035dbb  call    cs:__imp_CoCreateInstance
0x140035dc1  mov     ebx, eax
0x140035dc3  test    eax, eax
0x140035dc5  js      loc_140035E99
0x140035dcb  mov     rdx, [rbp+bstrString]
0x140035dcf  lea     rcx, aCupdatemanager_72; "CUpdateManager::CategorizeUpdates - Upd"...
0x140035dd6  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140035ddb  mov     rcx, [rbp+var_18]
0x140035ddf  lea     r8, [rbp+var_28]
0x140035de3  mov     rdx, [rbp+var_20]
0x140035de7  mov     rax, [rcx]
0x140035dea  mov     rax, [rax+60h]
0x140035dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035df3  mov     ebx, eax
0x140035df5  test    eax, eax
0x140035df7  js      loc_140035EA4
0x140035dfd  add     edi, r13d
0x140035e00  cmp     edi, dword ptr [rbp+arg_0]
0x140035e03  jl      loc_140035C59
0x140035e09  mov     rax, [rbp+var_10]
0x140035e0d  mov     [r15], rax
0x140035e10  mov     rax, [rbp+var_18]
0x140035e14  mov     [r14], rax
0x140035e17  mov     [rbp+var_10], r12
0x140035e1b  mov     [rbp+var_18], r12
0x140035e1f  mov     rcx, [rbp+var_18]
0x140035e23  test    rcx, rcx
0x140035e26  jz      short loc_140035E38
0x140035e28  mov     rax, [rcx]
0x140035e2b  mov     rax, [rax+10h]
0x140035e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035e34  mov     [rbp+var_18], r12
0x140035e38  mov     rcx, [rbp+var_10]
0x140035e3c  test    rcx, rcx
0x140035e3f  jz      short loc_140035E51
0x140035e41  mov     rax, [rcx]
0x140035e44  mov     rax, [rax+10h]
0x140035e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035e4d  mov     [rbp+var_10], r12
0x140035e51  mov     rcx, [rbp+var_20]
0x140035e55  test    rcx, rcx
0x140035e58  jz      short loc_140035E6A
0x140035e5a  mov     rax, [rcx]
0x140035e5d  mov     rax, [rax+10h]
0x140035e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035e66  mov     [rbp+var_20], r12
0x140035e6a  mov     rcx, [rbp+bstrString]; bstrString
0x140035e6e  call    cs:__imp_SysFreeString
0x140035e74  mov     eax, ebx
0x140035e76  mov     rbx, [rsp+70h+arg_10]
0x140035e7e  add     rsp, 70h
0x140035e82  pop     r15
0x140035e84  pop     r14
0x140035e86  pop     r13
0x140035e88  pop     r12
0x140035e8a  pop     rdi
0x140035e8b  pop     rsi
0x140035e8c  pop     rbp
0x140035e8d  retn
0x140035e8e  mov     r13d, 5D6h
0x140035e94  jmp     loc_140035BAF
0x140035e99  mov     r13d, 5E3h
0x140035e9f  jmp     loc_140035BAF
0x140035ea4  mov     r13d, 5E9h
0x140035eaa  jmp     loc_140035BAF
0x140035eaf  mov     r13d, 5AEh
0x140035eb5  jmp     loc_140035BAF
```
