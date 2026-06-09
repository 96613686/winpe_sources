# ProgressDispatchShim::OnCompleted(Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager *,Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManagerItemEventArgs *)

- ea: `0x180071ea0`
- end: `0x1800720b7`
- name: `?OnCompleted@ProgressDispatchShim@@QEAAJPEAUIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAUIAppInstallManagerItemEventArgs@34567@@Z`
- size: `535`
- prototype: `__int64 __fastcall(ProgressDispatchShim *__hidden this, struct Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager *, struct Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManagerItemEventArgs *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002958`
- `0x18006fa04`
- `0x180071b54`
- `0x180071ea0`
- `0x1800736ac`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071f44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072092`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071f44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072092`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007203e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007203e`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ProgressDispatchShim::OnCompleted(
        ProgressDispatchShim *this,
        struct Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager *a2,
        int (__fastcall ***a3)(struct Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManagerItemEventArgs *, GUID *, __int64 *))
{
  int (__fastcall *v5)(struct Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManagerItemEventArgs *, GUID *, __int64 *); // rbx
  __int64 v6; // rsi
  __int64 v7; // rdi
  int (__fastcall *v8)(__int64, HSTRING *); // rbx
  __int64 v9; // rdi
  int (__fastcall *v10)(__int64, __int64 *); // rbx
  int i; // eax
  __int64 v12; // rdi
  int (__fastcall *v13)(__int64, __int64 *); // rbx
  __int64 v14; // rdi
  int (__fastcall *v15)(__int64, __int64 *); // rbx
  __int64 v16; // r8
  __int64 v17; // rdi
  void (__fastcall *v18)(__int64, _QWORD, PCWSTR); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v21; // [rsp+20h] [rbp-30h] BYREF
  __int64 v22; // [rsp+28h] [rbp-28h] BYREF
  __int64 v23; // [rsp+30h] [rbp-20h] BYREF
  __int64 v24; // [rsp+38h] [rbp-18h] BYREF
  HSTRING string[2]; // [rsp+40h] [rbp-10h] BYREF
  char v26; // [rsp+80h] [rbp+30h] BYREF
  unsigned int v27; // [rsp+88h] [rbp+38h] BYREF

  v22 = 0;
  v5 = **a3;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
  if ( v5(
         (struct Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManagerItemEventArgs *)a3,
         &GUID_49d3dfab_168a_4cbf_a93a_9e448c82737d,
         &v22) >= 0 )
  {
    v27 = 0;
    if ( (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v22 + 64LL))(v22, &v27) >= 0 )
    {
      v6 = (unsigned int)MapType(v27);
      if ( (unsigned __int8)ProgressDispatchShim::DoAnyHandlersWantThisEvent(this, v6) )
      {
        string[0] = 0;
        v7 = v22;
        v8 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v22 + 56LL);
        WindowsDeleteString(0);
        string[0] = 0;
        if ( v8(v7, string) >= 0 )
        {
          v21 = 0;
          v9 = *((_QWORD *)this + 7);
          v10 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(v9 + 16) + 48LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
          if ( v10(v9 + 16, &v21) >= 0 )
          {
            v26 = 0;
            for ( i = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v21 + 56LL))(v21, &v26);
                  i >= 0 && v26;
                  i = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v21 + 64LL))(v21, &v26) )
            {
              v24 = 0;
              v23 = 0;
              v12 = v21;
              v13 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 48LL);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
              if ( v13(v12, &v24) >= 0 )
              {
                v14 = v24;
                v15 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 56LL);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
                if ( v15(v14, &v23) >= 0 )
                {
                  if ( (unsigned __int8)ShouldSendProgressToHandler(*(unsigned int *)(v23 + 40), (unsigned int)v6) )
                  {
                    v17 = *(_QWORD *)(v16 + 32);
                    v18 = *(void (__fastcall **)(__int64, _QWORD, PCWSTR))(*(_QWORD *)v17 + 32LL);
                    StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
                    v18(v17, (unsigned int)v6, StringRawBuffer);
                  }
                }
              }
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
            }
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
        }
        WindowsDeleteString(string[0]);
      }
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
  return 0;
}

```

## disassembly

```asm
0x180071ea0  mov     [rsp-18h+arg_0], rbx
0x180071ea5  mov     [rsp-18h+arg_8], rsi
0x180071eaa  push    rbp
0x180071eab  push    rdi
0x180071eac  push    r14
0x180071eae  mov     rbp, rsp
0x180071eb1  sub     rsp, 50h
0x180071eb5  mov     rdi, r8
0x180071eb8  mov     r14, rcx
0x180071ebb  mov     [rbp+var_28], 0
0x180071ec3  mov     rax, [r8]
0x180071ec6  mov     rbx, [rax]
0x180071ec9  lea     rcx, [rbp+var_28]
0x180071ecd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180071ed2  lea     r8, [rbp+var_28]
0x180071ed6  lea     rdx, _GUID_49d3dfab_168a_4cbf_a93a_9e448c82737d
0x180071edd  mov     rcx, rdi
0x180071ee0  mov     rax, rbx
0x180071ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071ee8  test    eax, eax
0x180071eea  js      loc_180072099
0x180071ef0  mov     [rbp+arg_18], 0
0x180071ef7  mov     rcx, [rbp+var_28]
0x180071efb  mov     rax, [rcx]
0x180071efe  lea     rdx, [rbp+arg_18]
0x180071f02  mov     rax, [rax+40h]
0x180071f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071f0b  test    eax, eax
0x180071f0d  js      loc_180072099
0x180071f13  mov     ecx, [rbp+arg_18]
0x180071f16  call    ?MapType@@YA?AW4__MIDL_IWindowsStoreInstallProgress_0002@@W4AppInstallType@InstallControl@Preview@Store@ApplicationModel@Windows@@@Z; MapType(Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallType)
0x180071f1b  mov     esi, eax
0x180071f1d  mov     edx, eax
0x180071f1f  mov     rcx, r14
0x180071f22  call    ?DoAnyHandlersWantThisEvent@ProgressDispatchShim@@AEAA_NW4__MIDL_IWindowsStoreInstallProgress_0002@@@Z; ProgressDispatchShim::DoAnyHandlersWantThisEvent(__MIDL_IWindowsStoreInstallProgress_0002)
0x180071f27  test    al, al
0x180071f29  jz      loc_180072099
0x180071f2f  mov     [rbp+string], 0
0x180071f37  mov     rdi, [rbp+var_28]
0x180071f3b  mov     rdx, [rdi]
0x180071f3e  mov     rbx, [rdx+38h]
0x180071f42  xor     ecx, ecx; string
0x180071f44  call    cs:__imp_WindowsDeleteString
0x180071f4a  mov     [rbp+string], 0
0x180071f52  lea     rdx, [rbp+string]
0x180071f56  mov     rcx, rdi
0x180071f59  mov     rax, rbx
0x180071f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071f61  test    eax, eax
0x180071f63  js      loc_18007208E
0x180071f69  mov     [rbp+var_30], 0
0x180071f71  mov     rdi, [r14+38h]
0x180071f75  mov     rax, [rdi+10h]
0x180071f79  mov     rbx, [rax+30h]
0x180071f7d  lea     rcx, [rbp+var_30]
0x180071f81  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180071f86  lea     rdx, [rbp+var_30]
0x180071f8a  lea     rcx, [rdi+10h]
0x180071f8e  mov     rax, rbx
0x180071f91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071f96  test    eax, eax
0x180071f98  js      loc_180072084
0x180071f9e  mov     [rbp+arg_10], 0
0x180071fa2  mov     rcx, [rbp+var_30]
0x180071fa6  mov     rax, [rcx]
0x180071fa9  mov     rax, [rax+38h]
0x180071fad  jmp     loc_180072073
0x180071fb2  cmp     [rbp+arg_10], 0
0x180071fb6  jz      loc_180072084
0x180071fbc  mov     [rbp+var_18], 0
0x180071fc4  mov     [rbp+var_20], 0
0x180071fcc  mov     rdi, [rbp+var_30]
0x180071fd0  mov     rax, [rdi]
0x180071fd3  mov     rbx, [rax+30h]
0x180071fd7  lea     rcx, [rbp+var_18]
0x180071fdb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180071fe0  lea     rdx, [rbp+var_18]
0x180071fe4  mov     rcx, rdi
0x180071fe7  mov     rax, rbx
0x180071fea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071fef  test    eax, eax
0x180071ff1  js      short loc_180072055
0x180071ff3  mov     rdi, [rbp+var_18]
0x180071ff7  mov     rax, [rdi]
0x180071ffa  mov     rbx, [rax+38h]
0x180071ffe  lea     rcx, [rbp+var_20]
0x180072002  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180072007  lea     rdx, [rbp+var_20]
0x18007200b  mov     rcx, rdi
0x18007200e  mov     rax, rbx
0x180072011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072016  test    eax, eax
0x180072018  js      short loc_180072055
0x18007201a  mov     edx, esi
0x18007201c  mov     r8, [rbp+var_20]
0x180072020  mov     ecx, [r8+28h]
0x180072024  call    ?ShouldSendProgressToHandler@@YA_NW4__MIDL_IWindowsStoreInstallProgress_0003@@W4__MIDL_IWindowsStoreInstallProgress_0002@@@Z; ShouldSendProgressToHandler(__MIDL_IWindowsStoreInstallProgress_0003,__MIDL_IWindowsStoreInstallProgress_0002)
0x180072029  test    al, al
0x18007202b  jz      short loc_180072055
0x18007202d  mov     rdi, [r8+20h]
0x180072031  mov     rax, [rdi]
0x180072034  mov     rbx, [rax+20h]
0x180072038  xor     edx, edx; length
0x18007203a  mov     rcx, [rbp+string]; string
0x18007203e  call    cs:__imp_WindowsGetStringRawBuffer
0x180072044  mov     r8, rax
0x180072047  mov     edx, esi
0x180072049  mov     rcx, rdi
0x18007204c  mov     rax, rbx
0x18007204f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072054  nop
0x180072055  lea     rcx, [rbp+var_20]
0x180072059  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007205e  nop
0x18007205f  lea     rcx, [rbp+var_18]
0x180072063  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180072068  mov     rcx, [rbp+var_30]
0x18007206c  mov     rax, [rcx]
0x18007206f  mov     rax, [rax+40h]
0x180072073  lea     rdx, [rbp+arg_10]
0x180072077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007207c  test    eax, eax
0x18007207e  jns     loc_180071FB2
0x180072084  lea     rcx, [rbp+var_30]
0x180072088  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007208d  nop
0x18007208e  mov     rcx, [rbp+string]; string
0x180072092  call    cs:__imp_WindowsDeleteString
0x180072098  nop
0x180072099  lea     rcx, [rbp+var_28]
0x18007209d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800720a2  xor     eax, eax
0x1800720a4  mov     rbx, [rsp+50h+arg_0]
0x1800720a9  mov     rsi, [rsp+50h+arg_8]
0x1800720ae  add     rsp, 50h
0x1800720b2  pop     r14
0x1800720b4  pop     rdi
0x1800720b5  pop     rbp
0x1800720b6  retn
```
