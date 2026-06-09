# GetHtmlCharsetThreadEntry(ulong *)

- ea: `0x180006330`
- end: `0x180006541`
- name: `?GetHtmlCharsetThreadEntry@@YAKPEAK@Z`
- size: `529`
- prototype: `void __fastcall __noreturn(_QWORD *lpThreadParameter)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001f7c`
- `0x1800060b4`
- `0x1800060e4`
- `0x180006180`
- `0x180006330`
- `0x180011b6c`
- `0x180011b80`
- `0x180014010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800063ca`
- `ole32!CoCreateInstance` at `0x1800063ca`
- `ole32!CoUninitialize` at `0x18000652c`
- `ole32!CoUninitialize` at `0x18000652c`
- `ole32!CoInitialize` at `0x180006389`
- `ole32!CoInitialize` at `0x180006389`
- `USER32!GetMessageA` at `0x1800064ca`
- `USER32!GetMessageA` at `0x1800064ca`
- `USER32!TranslateMessage` at `0x1800064ae`
- `USER32!TranslateMessage` at `0x1800064ae`
- `USER32!DispatchMessageA` at `0x1800064b8`
- `USER32!DispatchMessageA` at `0x1800064b8`

## pseudocode

```c
void __fastcall __noreturn GetHtmlCharsetThreadEntry(_QWORD *lpThreadParameter)
{
  HRESULT v2; // eax
  DWORD v3; // eax
  HRESULT Instance; // ebx
  CSimpleSite *v5; // rax
  CSimpleSite *v6; // rdi
  __int64 v7; // [rsp+30h] [rbp-48h] BYREF
  CSimpleSite *v8; // [rsp+38h] [rbp-40h] BYREF
  MSG Msg; // [rsp+40h] [rbp-38h] BYREF
  __int64 v10; // [rsp+A0h] [rbp+28h] BYREF
  __int64 (__fastcall ***v11)(_QWORD, GUID *, __int64 *); // [rsp+A8h] [rbp+30h] BYREF
  struct IHTMLDocument2 *ppv; // [rsp+B0h] [rbp+38h] BYREF
  __int64 v13; // [rsp+B8h] [rbp+40h] BYREF

  v7 = 0;
  GetCurrentHINSTANCE(&v7);
  v8 = 0;
  ppv = 0;
  memset(&Msg, 0, sizeof(Msg));
  v10 = 0;
  v11 = 0;
  v13 = 0;
  v2 = CoInitialize(0);
  if ( v2 < 0 )
  {
    *(_DWORD *)lpThreadParameter = v2;
    CLoadLibrary_FreeLibraryAndExitThread_Pair::ExitThread_DWORD((CLoadLibrary_FreeLibraryAndExitThread_Pair *)&v7, 0);
  }
  v3 = operator|(1);
  Instance = CoCreateInstance(&CLSID_HTMLDocument, 0, v3, &IID_IHTMLDocument2, (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    v5 = (CSimpleSite *)operator new(0x30u);
    if ( v5 && (v8 = CSimpleSite::CSimpleSite(v5, ppv), (v6 = v8) != 0) )
    {
      Instance = ((__int64 (__fastcall *)(struct IHTMLDocument2 *, GUID *, _QWORD))ppv->lpVtbl->QueryInterface)(
                   ppv,
                   &IID_IOleCommandTarget,
                   &v11);
      if ( Instance >= 0 )
      {
        Instance = (**v11)(v11, &IID_IOleObject, &v10);
        if ( Instance >= 0 )
        {
          Instance = (*(__int64 (__fastcall **)(__int64, CSimpleSite *))(*(_QWORD *)v10 + 24LL))(v10, v6);
          if ( Instance >= 0 )
          {
            Instance = (**v11)(v11, &IID_IPersistStreamInit, &v13);
            if ( Instance >= 0 )
            {
              Instance = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v13 + 40LL))(v13, lpThreadParameter[1]);
              if ( Instance >= 0 )
              {
                while ( GetMessageA(&Msg, 0, 0, 0) )
                {
                  TranslateMessage(&Msg);
                  DispatchMessageA(&Msg);
                }
                (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v10 + 24LL))(v10, 0);
                lpThreadParameter[2] = *((_QWORD *)v6 + 5);
                *((_QWORD *)v6 + 5) = 0;
              }
            }
          }
        }
      }
    }
    else
    {
      Instance = -2147024882;
    }
  }
  OE_SafeReleaseAndNullPtr<IPersistStreamInit>(&v8);
  OE_SafeReleaseAndNullPtr<IPersistStreamInit>(&v10);
  OE_SafeReleaseAndNullPtr<IPersistStreamInit>(&v13);
  OE_SafeReleaseAndNullPtr<IPersistStreamInit>(&v11);
  OE_SafeReleaseAndNullPtr<IPersistStreamInit>(&ppv);
  *(_DWORD *)lpThreadParameter = Instance;
  CoUninitialize();
  CLoadLibrary_FreeLibraryAndExitThread_Pair::ExitThread_DWORD((CLoadLibrary_FreeLibraryAndExitThread_Pair *)&v7, 1u);
}

```

## disassembly

```asm
0x180006330  push    rbp
0x180006332  push    rbx
0x180006333  push    rsi
0x180006334  push    rdi
0x180006335  mov     rbp, rsp
0x180006338  sub     rsp, 78h
0x18000633c  mov     rsi, rcx
0x18000633f  mov     [rbp+var_48], 0
0x180006347  lea     rcx, [rbp+var_48]
0x18000634b  call    _GetCurrentHINSTANCE
0x180006350  xorps   xmm0, xmm0
0x180006353  mov     [rbp+var_40], 0
0x18000635b  xor     ecx, ecx; pvReserved
0x18000635d  mov     [rbp+arg_10], 0
0x180006365  movups  xmmword ptr [rbp+Msg.hwnd], xmm0
0x180006369  mov     [rbp+arg_0], 0
0x180006371  movups  xmmword ptr [rbp+Msg.wParam], xmm0
0x180006375  mov     [rbp+arg_8], 0
0x18000637d  movups  xmmword ptr [rbp+Msg.time], xmm0
0x180006381  mov     [rbp+arg_18], 0
0x180006389  call    cs:__imp_CoInitialize
0x18000638f  test    eax, eax
0x180006391  jns     short loc_1800063A1
0x180006393  xor     edx, edx; unsigned int
0x180006395  mov     [rsi], eax
0x180006397  lea     rcx, [rbp+var_48]; this
0x18000639b  call    ?ExitThread_DWORD@CLoadLibrary_FreeLibraryAndExitThread_Pair@@QEAAXK@Z; CLoadLibrary_FreeLibraryAndExitThread_Pair::ExitThread_DWORD(ulong)
0x1800063a1  mov     edx, 2
0x1800063a6  lea     ecx, [rdx-1]
0x1800063a9  call    ??U@YA?AW4tagCLSCTX@@W40@0@Z; operator|(tagCLSCTX,tagCLSCTX)
0x1800063ae  mov     r8d, eax; dwClsContext
0x1800063b1  lea     r9, IID_IHTMLDocument2; riid
0x1800063b8  lea     rax, [rbp+arg_10]
0x1800063bc  xor     edx, edx; pUnkOuter
0x1800063be  lea     rcx, CLSID_HTMLDocument; rclsid
0x1800063c5  mov     [rsp+78h+ppv], rax; ppv
0x1800063ca  call    cs:__imp_CoCreateInstance
0x1800063d0  mov     ebx, eax
0x1800063d2  test    eax, eax
0x1800063d4  js      loc_1800064FD
0x1800063da  mov     ecx, 30h ; '0'; Size
0x1800063df  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800063e4  test    rax, rax
0x1800063e7  jz      loc_1800064F8
0x1800063ed  mov     rdx, [rbp+arg_10]; struct IHTMLDocument2 *
0x1800063f1  mov     rcx, rax; this
0x1800063f4  call    ??0CSimpleSite@@QEAA@PEAUIHTMLDocument2@@@Z; CSimpleSite::CSimpleSite(IHTMLDocument2 *)
0x1800063f9  mov     [rbp+var_40], rax
0x1800063fd  mov     rdi, rax
0x180006400  test    rax, rax
0x180006403  jz      loc_1800064F8
0x180006409  mov     rcx, [rbp+arg_10]
0x18000640d  lea     r8, [rbp+arg_8]
0x180006411  mov     rdx, [rcx]
0x180006414  mov     rax, [rdx]
0x180006417  lea     rdx, IID_IOleCommandTarget
0x18000641e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006423  mov     ebx, eax
0x180006425  test    eax, eax
0x180006427  js      loc_1800064FD
0x18000642d  mov     rcx, [rbp+arg_8]
0x180006431  lea     r8, [rbp+arg_0]
0x180006435  lea     rdx, IID_IOleObject
0x18000643c  mov     rax, [rcx]
0x18000643f  mov     rax, [rax]
0x180006442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006447  mov     ebx, eax
0x180006449  test    eax, eax
0x18000644b  js      loc_1800064FD
0x180006451  mov     rcx, [rbp+arg_0]
0x180006455  mov     rdx, rdi
0x180006458  mov     rax, [rcx]
0x18000645b  mov     rax, [rax+18h]
0x18000645f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006464  mov     ebx, eax
0x180006466  test    eax, eax
0x180006468  js      loc_1800064FD
0x18000646e  mov     rcx, [rbp+arg_8]
0x180006472  lea     r8, [rbp+arg_18]
0x180006476  lea     rdx, IID_IPersistStreamInit
0x18000647d  mov     rax, [rcx]
0x180006480  mov     rax, [rax]
0x180006483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006488  mov     ebx, eax
0x18000648a  test    eax, eax
0x18000648c  js      short loc_1800064FD
0x18000648e  mov     rcx, [rbp+arg_18]
0x180006492  mov     rdx, [rsi+8]
0x180006496  mov     rax, [rcx]
0x180006499  mov     rax, [rax+28h]
0x18000649d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064a2  mov     ebx, eax
0x1800064a4  test    eax, eax
0x1800064a6  js      short loc_1800064FD
0x1800064a8  jmp     short loc_1800064BE
0x1800064aa  lea     rcx, [rbp+Msg]; lpMsg
0x1800064ae  call    cs:__imp_TranslateMessage
0x1800064b4  lea     rcx, [rbp+Msg]; lpMsg
0x1800064b8  call    cs:__imp_DispatchMessageA
0x1800064be  xor     r9d, r9d; wMsgFilterMax
0x1800064c1  lea     rcx, [rbp+Msg]; lpMsg
0x1800064c5  xor     r8d, r8d; wMsgFilterMin
0x1800064c8  xor     edx, edx; hWnd
0x1800064ca  call    cs:__imp_GetMessageA
0x1800064d0  test    eax, eax
0x1800064d2  jnz     short loc_1800064AA
0x1800064d4  mov     rcx, [rbp+arg_0]
0x1800064d8  xor     edx, edx
0x1800064da  mov     rax, [rcx]
0x1800064dd  mov     rax, [rax+18h]
0x1800064e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064e6  mov     rax, [rdi+28h]
0x1800064ea  mov     [rsi+10h], rax
0x1800064ee  mov     qword ptr [rdi+28h], 0
0x1800064f6  jmp     short loc_1800064FD
0x1800064f8  mov     ebx, 8007000Eh
0x1800064fd  lea     rcx, [rbp+var_40]
0x180006501  call    ??$OE_SafeReleaseAndNullPtr@UIPersistStreamInit@@@@YAXAEAPEAUIPersistStreamInit@@@Z; OE_SafeReleaseAndNullPtr<IPersistStreamInit>(IPersistStreamInit * &)
0x180006506  lea     rcx, [rbp+arg_0]
0x18000650a  call    ??$OE_SafeReleaseAndNullPtr@UIPersistStreamInit@@@@YAXAEAPEAUIPersistStreamInit@@@Z; OE_SafeReleaseAndNullPtr<IPersistStreamInit>(IPersistStreamInit * &)
0x18000650f  lea     rcx, [rbp+arg_18]
0x180006513  call    ??$OE_SafeReleaseAndNullPtr@UIPersistStreamInit@@@@YAXAEAPEAUIPersistStreamInit@@@Z; OE_SafeReleaseAndNullPtr<IPersistStreamInit>(IPersistStreamInit * &)
0x180006518  lea     rcx, [rbp+arg_8]
0x18000651c  call    ??$OE_SafeReleaseAndNullPtr@UIPersistStreamInit@@@@YAXAEAPEAUIPersistStreamInit@@@Z; OE_SafeReleaseAndNullPtr<IPersistStreamInit>(IPersistStreamInit * &)
0x180006521  lea     rcx, [rbp+arg_10]
0x180006525  call    ??$OE_SafeReleaseAndNullPtr@UIPersistStreamInit@@@@YAXAEAPEAUIPersistStreamInit@@@Z; OE_SafeReleaseAndNullPtr<IPersistStreamInit>(IPersistStreamInit * &)
0x18000652a  mov     [rsi], ebx
0x18000652c  call    cs:__imp_CoUninitialize
0x180006532  mov     edx, 1; unsigned int
0x180006537  lea     rcx, [rbp+var_48]; this
0x18000653b  call    ?ExitThread_DWORD@CLoadLibrary_FreeLibraryAndExitThread_Pair@@QEAAXK@Z; CLoadLibrary_FreeLibraryAndExitThread_Pair::ExitThread_DWORD(ulong)
```
