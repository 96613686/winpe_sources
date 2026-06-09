# CAutoplayDialog::_PopulateUIForDeviceStage(IAutoplayDeviceHandler *)

- ea: `0x180199b6c`
- end: `0x180199e21`
- name: `?_PopulateUIForDeviceStage@CAutoplayDialog@@AEAAJPEAUIAutoplayDeviceHandler@@@Z`
- size: `693`
- prototype: `__int64 __fastcall(CAutoplayDialog *__hidden this, struct IAutoplayDeviceHandler *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800c2560`

## callees

- `0x180009dd0`
- `0x18008a088`
- `0x180193970`
- `0x1801949e0`
- `0x180199b6c`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180199d1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180199dee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180199d1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180199dee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180199cec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180199cfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180199d0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180199cec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180199cfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180199d0c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180199bd6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180199d86`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180199bd6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180199d86`

## pseudocode

```c
__int64 __fastcall CAutoplayDialog::_PopulateUIForDeviceStage(CAutoplayDialog *this, struct IAutoplayDeviceHandler *a2)
{
  HRESULT v4; // ebx
  __int64 v5; // rax
  __int64 v6; // rax
  LPVOID pv; // [rsp+30h] [rbp-20h] BYREF
  LPVOID v9; // [rsp+38h] [rbp-18h] BYREF
  LPVOID v10[2]; // [rsp+40h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp+30h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp+38h] BYREF

  hMem = 0;
  v4 = SHFormatResMessageArgAlloc(&_ImageBase, 9913, &hMem);
  if ( v4 >= 0 )
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
    v4 = CoCreateInstance(&CLSID_AutoplayHandler, 0, 3u, &GUID_d38d6ad9_8a0f_4d03_9a5b_cb3ca657a39f, &ppv);
    if ( v4 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *))(*(_QWORD *)ppv + 24LL))(ppv, L"MSDoDxp");
      if ( v4 >= 0 )
      {
        v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 128LL))(ppv, *((_QWORD *)this + 2));
        if ( v4 >= 0 )
        {
          v5 = *(_QWORD *)a2;
          v10[0] = 0;
          v4 = (*(__int64 (__fastcall **)(struct IAutoplayDeviceHandler *, LPVOID *))(v5 + 72))(a2, v10);
          if ( v4 >= 0 )
          {
            v9 = 0;
            v4 = SHFormatResMessageArgAlloc(&_ImageBase, 9928, &v9);
            if ( v4 >= 0 )
            {
              v4 = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)ppv + 112LL))(ppv, v9);
              if ( v4 >= 0 )
              {
                v6 = *(_QWORD *)a2;
                pv = 0;
                v4 = (*(__int64 (__fastcall **)(struct IAutoplayDeviceHandler *, LPVOID *))(v6 + 64))(a2, &pv);
                if ( v4 >= 0 )
                {
                  v4 = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)ppv + 120LL))(ppv, pv);
                  if ( v4 >= 0 )
                    v4 = CAutoPlayHandlerChooser::AddHandlerToNewGroup(this, ppv, hMem, 0);
                  CoTaskMemFree(pv);
                }
              }
              CoTaskMemFree(v9);
            }
            CoTaskMemFree(v10[0]);
          }
        }
      }
    }
    LocalFree(hMem);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
    if ( v4 >= 0 )
    {
      v4 = SHFormatResMessageArgAlloc(&_ImageBase, 9904, &hMem);
      if ( v4 >= 0 )
      {
        ppv = 0;
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
        v4 = CoCreateInstance(&CLSID_AutoplayHandler, 0, 3u, &GUID_d38d6ad9_8a0f_4d03_9a5b_cb3ca657a39f, &ppv);
        if ( v4 >= 0 )
        {
          v4 = (*(__int64 (__fastcall **)(LPVOID, const WCHAR *))(*(_QWORD *)ppv + 24LL))(ppv, L"MSTakeNoAction");
          if ( v4 >= 0 )
          {
            v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 128LL))(ppv, *((_QWORD *)this + 2));
            if ( v4 >= 0 )
              v4 = CAutoPlayHandlerChooser::AddHandlerToNewGroup(this, ppv, hMem, 4);
          }
        }
        LocalFree(hMem);
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
        if ( v4 >= 0 )
          CAutoPlayHandlerChooser::SelectHandler(this, 0);
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180199b6c  mov     [rsp-18h+arg_0], rbx
0x180199b71  push    rbp
0x180199b72  push    rsi
0x180199b73  push    rdi
0x180199b74  mov     rbp, rsp
0x180199b77  sub     rsp, 50h
0x180199b7b  mov     rsi, rdx
0x180199b7e  mov     [rbp+hMem], 0
0x180199b86  mov     rdi, rcx
0x180199b89  lea     r8, [rbp+hMem]
0x180199b8d  mov     edx, 26B9h
0x180199b92  lea     rcx, __ImageBase
0x180199b99  call    SHFormatResMessageArgAlloc
0x180199b9e  mov     ebx, eax
0x180199ba0  test    eax, eax
0x180199ba2  js      loc_180199E11
0x180199ba8  lea     rcx, [rbp+arg_10]
0x180199bac  mov     [rbp+arg_10], 0
0x180199bb4  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180199bb9  xor     edx, edx; pUnkOuter
0x180199bbb  lea     rax, [rbp+arg_10]
0x180199bbf  lea     r9, _GUID_d38d6ad9_8a0f_4d03_9a5b_cb3ca657a39f; riid
0x180199bc6  mov     [rsp+50h+ppv], rax; ppv
0x180199bcb  lea     rcx, CLSID_AutoplayHandler; rclsid
0x180199bd2  lea     r8d, [rdx+3]; dwClsContext
0x180199bd6  call    cs:__imp_CoCreateInstance
0x180199bdd  nop     dword ptr [rax+rax+00h]
0x180199be2  mov     ebx, eax
0x180199be4  test    eax, eax
0x180199be6  js      loc_180199D18
0x180199bec  mov     rcx, [rbp+arg_10]
0x180199bf0  lea     rdx, aMsdodxp; "MSDoDxp"
0x180199bf7  mov     rax, [rcx]
0x180199bfa  mov     rax, [rax+18h]
0x180199bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180199c03  mov     ebx, eax
0x180199c05  test    eax, eax
0x180199c07  js      loc_180199D18
0x180199c0d  mov     rcx, [rbp+arg_10]
0x180199c11  mov     rdx, [rdi+10h]
0x180199c15  mov     rax, [rcx]
0x180199c18  mov     rax, [rax+80h]
0x180199c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180199c24  mov     ebx, eax
0x180199c26  test    eax, eax
0x180199c28  js      loc_180199D18
0x180199c2e  mov     rax, [rsi]
0x180199c31  lea     rdx, [rbp+var_10]
0x180199c35  mov     rcx, rsi
0x180199c38  mov     [rbp+var_10], 0
0x180199c40  mov     rax, [rax+48h]
0x180199c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180199c49  mov     ebx, eax
0x180199c4b  test    eax, eax
0x180199c4d  js      loc_180199D18
0x180199c53  mov     r9, [rbp+var_10]
0x180199c57  lea     r8, [rbp+var_18]
0x180199c5b  mov     edx, 26C8h
0x180199c60  mov     [rbp+var_18], 0
0x180199c68  lea     rcx, __ImageBase
0x180199c6f  call    SHFormatResMessageArgAlloc
0x180199c74  mov     ebx, eax
0x180199c76  test    eax, eax
0x180199c78  js      loc_180199D08
0x180199c7e  mov     rcx, [rbp+arg_10]
0x180199c82  mov     rdx, [rbp+var_18]
0x180199c86  mov     rax, [rcx]
0x180199c89  mov     rax, [rax+70h]
0x180199c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180199c92  mov     ebx, eax
0x180199c94  test    eax, eax
0x180199c96  js      short loc_180199CF8
0x180199c98  mov     rax, [rsi]
0x180199c9b  lea     rdx, [rbp+pv]
0x180199c9f  mov     rcx, rsi
0x180199ca2  mov     [rbp+pv], 0
0x180199caa  mov     rax, [rax+40h]
0x180199cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180199cb3  mov     ebx, eax
0x180199cb5  test    eax, eax
0x180199cb7  js      short loc_180199CF8
0x180199cb9  mov     rcx, [rbp+arg_10]
0x180199cbd  mov     rdx, [rbp+pv]
0x180199cc1  mov     rax, [rcx]
0x180199cc4  mov     rax, [rax+78h]
0x180199cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180199ccd  mov     ebx, eax
0x180199ccf  test    eax, eax
0x180199cd1  js      short loc_180199CE8
0x180199cd3  mov     r8, [rbp+hMem]
0x180199cd7  xor     r9d, r9d
0x180199cda  mov     rdx, [rbp+arg_10]
0x180199cde  mov     rcx, rdi
0x180199ce1  call    ?AddHandlerToNewGroup@CAutoPlayHandlerChooser@@MEAAJPEAUIAutoplayHandler@@PEAGW4tag_GROUPIDS@@@Z; CAutoPlayHandlerChooser::AddHandlerToNewGroup(IAutoplayHandler *,ushort *,tag_GROUPIDS)
0x180199ce6  mov     ebx, eax
0x180199ce8  mov     rcx, [rbp+pv]; pv
0x180199cec  call    cs:__imp_CoTaskMemFree
0x180199cf3  nop     dword ptr [rax+rax+00h]
0x180199cf8  mov     rcx, [rbp+var_18]; pv
0x180199cfc  call    cs:__imp_CoTaskMemFree
0x180199d03  nop     dword ptr [rax+rax+00h]
0x180199d08  mov     rcx, [rbp+var_10]; pv
0x180199d0c  call    cs:__imp_CoTaskMemFree
0x180199d13  nop     dword ptr [rax+rax+00h]
0x180199d18  mov     rcx, [rbp+hMem]; hMem
0x180199d1c  call    cs:__imp_LocalFree
0x180199d23  nop     dword ptr [rax+rax+00h]
0x180199d28  lea     rcx, [rbp+arg_10]
0x180199d2c  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180199d31  test    ebx, ebx
0x180199d33  js      loc_180199E11
0x180199d39  lea     r8, [rbp+hMem]
0x180199d3d  mov     edx, 26B0h
0x180199d42  lea     rcx, __ImageBase
0x180199d49  call    SHFormatResMessageArgAlloc
0x180199d4e  mov     ebx, eax
0x180199d50  test    eax, eax
0x180199d52  js      loc_180199E11
0x180199d58  lea     rcx, [rbp+arg_10]
0x180199d5c  mov     [rbp+arg_10], 0
0x180199d64  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180199d69  xor     edx, edx; pUnkOuter
0x180199d6b  lea     rax, [rbp+arg_10]
0x180199d6f  lea     r9, _GUID_d38d6ad9_8a0f_4d03_9a5b_cb3ca657a39f; riid
0x180199d76  mov     [rsp+50h+ppv], rax; ppv
0x180199d7b  lea     rcx, CLSID_AutoplayHandler; rclsid
0x180199d82  lea     r8d, [rdx+3]; dwClsContext
0x180199d86  call    cs:__imp_CoCreateInstance
0x180199d8d  nop     dword ptr [rax+rax+00h]
0x180199d92  mov     ebx, eax
0x180199d94  test    eax, eax
0x180199d96  js      short loc_180199DEA
0x180199d98  mov     rcx, [rbp+arg_10]
0x180199d9c  lea     rdx, aMstakenoaction; "MSTakeNoAction"
0x180199da3  mov     rax, [rcx]
0x180199da6  mov     rax, [rax+18h]
0x180199daa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180199daf  mov     ebx, eax
0x180199db1  test    eax, eax
0x180199db3  js      short loc_180199DEA
0x180199db5  mov     rcx, [rbp+arg_10]
0x180199db9  mov     rdx, [rdi+10h]
0x180199dbd  mov     rax, [rcx]
0x180199dc0  mov     rax, [rax+80h]
0x180199dc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180199dcc  mov     ebx, eax
0x180199dce  test    eax, eax
0x180199dd0  js      short loc_180199DEA
0x180199dd2  mov     r8, [rbp+hMem]
0x180199dd6  mov     r9d, 4
0x180199ddc  mov     rdx, [rbp+arg_10]
0x180199de0  mov     rcx, rdi
0x180199de3  call    ?AddHandlerToNewGroup@CAutoPlayHandlerChooser@@MEAAJPEAUIAutoplayHandler@@PEAGW4tag_GROUPIDS@@@Z; CAutoPlayHandlerChooser::AddHandlerToNewGroup(IAutoplayHandler *,ushort *,tag_GROUPIDS)
0x180199de8  mov     ebx, eax
0x180199dea  mov     rcx, [rbp+hMem]; hMem
0x180199dee  call    cs:__imp_LocalFree
0x180199df5  nop     dword ptr [rax+rax+00h]
0x180199dfa  lea     rcx, [rbp+arg_10]
0x180199dfe  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180199e03  test    ebx, ebx
0x180199e05  js      short loc_180199E11
0x180199e07  xor     edx, edx; unsigned __int16 *
0x180199e09  mov     rcx, rdi; this
0x180199e0c  call    ?SelectHandler@CAutoPlayHandlerChooser@@MEAAJPEBG@Z; CAutoPlayHandlerChooser::SelectHandler(ushort const *)
0x180199e11  mov     eax, ebx
0x180199e13  mov     rbx, [rsp+50h+arg_0]
0x180199e18  add     rsp, 50h
0x180199e1c  pop     rdi
0x180199e1d  pop     rsi
0x180199e1e  pop     rbp
0x180199e1f  retn
```
