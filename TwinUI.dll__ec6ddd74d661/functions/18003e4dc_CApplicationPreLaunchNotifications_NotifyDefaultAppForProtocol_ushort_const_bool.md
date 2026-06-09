# CApplicationPreLaunchNotifications::NotifyDefaultAppForProtocol(ushort const *,bool)

- ea: `0x18003e4dc`
- end: `0x18003e91b`
- name: `?NotifyDefaultAppForProtocol@CApplicationPreLaunchNotifications@@AEAAJPEBG_N@Z`
- size: `1087`
- prototype: `int(CApplicationPreLaunchNotifications *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003e410`

## callees

- `0x180009dd0`
- `0x180009dfc`
- `0x18001c710`
- `0x18003e4dc`
- `0x180053740`
- `0x1800a9dc4`
- `0x180142e10`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e6a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e778`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e7e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e847`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e860`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e882`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e6a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e778`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e7e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e847`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e860`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e882`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e6d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e80e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e823`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e6d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e80e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e823`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e8d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e8d2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003e540`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003e540`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003e5c5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003e5c5`

## string_xrefs

- `0x18003e59a`: `Windows.Internal.StateRepository.Protocol`

## pseudocode

```c
__int64 __fastcall CApplicationPreLaunchNotifications::NotifyDefaultAppForProtocol(
        CApplicationPreLaunchNotifications *this,
        unsigned __int16 *a2,
        bool a3)
{
  HRESULT ActivationFactory; // edi
  __int64 v6; // rbx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, _QWORD, __int64 *); // rbx
  __int64 v9; // rax
  unsigned int v10; // esi
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, __int64 *); // rbx
  __int64 v13; // rdi
  int v14; // r14d
  __int64 (__fastcall *v15)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  unsigned __int16 *v17; // rcx
  signed __int64 v18; // rax
  int v19; // r8d
  int v20; // edx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64 *); // rbx
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, __int64 *); // rbx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, HSTRING *); // rbx
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, __int64 *); // rbx
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, HSTRING *); // rbx
  const unsigned __int16 *v31; // rbx
  const unsigned __int16 *v32; // rax
  CApplicationPreLaunchNotifications *v33; // rcx
  unsigned int v34; // eax
  unsigned int v36; // [rsp+30h] [rbp-59h] BYREF
  __int64 v37; // [rsp+38h] [rbp-51h] BYREF
  HSTRING string; // [rsp+40h] [rbp-49h] BYREF
  __int64 v39; // [rsp+48h] [rbp-41h] BYREF
  __int64 v40; // [rsp+50h] [rbp-39h] BYREF
  HSTRING v41; // [rsp+58h] [rbp-31h] BYREF
  __int64 v42; // [rsp+60h] [rbp-29h] BYREF
  HSTRING v43; // [rsp+68h] [rbp-21h] BYREF
  __int64 v44; // [rsp+70h] [rbp-19h] BYREF
  __int64 v45; // [rsp+78h] [rbp-11h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp-9h] BYREF
  LPVOID pv; // [rsp+88h] [rbp-1h]
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp+7h] BYREF
  __int64 v49; // [rsp+A8h] [rbp+1Fh]

  string = (HSTRING)a2;
  ppv = 0;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
  ActivationFactory = CoCreateInstance(
                        &GUID_591209c7_767b_42b2_9fba_44ee4615f2c7,
                        0,
                        3u,
                        &GUID_4e530b0a_e611_4c77_a3ac_9031d022281b,
                        &ppv);
  if ( ActivationFactory >= 0 )
  {
    pv = 0;
    ActivationFactory = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, __int64))(*(_QWORD *)ppv + 24LL))(
                          ppv,
                          a2,
                          1);
    if ( ActivationFactory >= 0 )
    {
      v45 = 0;
      v49 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Internal.StateRepository.Protocol",
        0x2Au,
        0x29u);
      v6 = v49;
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v45);
      ActivationFactory = RoGetActivationFactory(v6, &GUID_0f2f217e_7957_4262_a74c_df03d9e9e9c1, &v45);
      if ( ActivationFactory >= 0 )
      {
        v7 = v45;
        v40 = 0;
        v8 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v45 + 200LL);
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v40);
        v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &string);
        ActivationFactory = v8(v7, 0, *(_QWORD *)(v9 + 24), &v40);
        if ( ActivationFactory >= 0 )
        {
          v36 = 0;
          ActivationFactory = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v40 + 56LL))(v40, &v36);
          if ( ActivationFactory >= 0 )
          {
            if ( v36 )
            {
              v10 = 0;
              while ( 1 )
              {
                v11 = v40;
                v37 = 0;
                v12 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v40 + 48LL);
                Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v37);
                ActivationFactory = v12(v11, v10, &v37);
                if ( ActivationFactory < 0 )
                  break;
                v13 = v37;
                string = 0;
                v14 = 0;
                v15 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v37 + 112LL);
                WindowsDeleteString(0);
                string = 0;
                ActivationFactory = v15(v13, &string);
                if ( ActivationFactory >= 0 )
                {
                  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
                  v17 = (unsigned __int16 *)pv;
                  v18 = (char *)StringRawBuffer - (_BYTE *)pv;
                  do
                  {
                    v19 = *(unsigned __int16 *)((char *)v17 + v18);
                    v20 = *v17 - v19;
                    if ( v20 )
                      break;
                    ++v17;
                  }
                  while ( v19 );
                  if ( !v20 )
                  {
                    v21 = v37;
                    v44 = 0;
                    v22 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v37 + 88LL);
                    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v44);
                    ActivationFactory = v22(v21, &v44);
                    if ( ActivationFactory >= 0 )
                    {
                      v23 = v44;
                      v39 = 0;
                      v24 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 72LL);
                      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v39);
                      ActivationFactory = v24(v23, &v39);
                      if ( ActivationFactory >= 0 )
                      {
                        v25 = v39;
                        v43 = 0;
                        v26 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v39 + 232LL);
                        WindowsDeleteString(0);
                        v43 = 0;
                        ActivationFactory = v26(v25, &v43);
                        if ( ActivationFactory >= 0 )
                        {
                          v27 = v39;
                          v42 = 0;
                          v28 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 72LL);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
                          ActivationFactory = v28(v27, &v42);
                          if ( ActivationFactory >= 0 )
                          {
                            v29 = v42;
                            v41 = 0;
                            v30 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v42 + 112LL);
                            WindowsDeleteString(0);
                            v41 = 0;
                            ActivationFactory = v30(v29, &v41);
                            if ( ActivationFactory >= 0 )
                            {
                              v31 = WindowsGetStringRawBuffer(v41, 0);
                              v32 = WindowsGetStringRawBuffer(v43, 0);
                              CApplicationPreLaunchNotifications::NotifyDefaultApp(v33, v32, v31, a3);
                              v14 = 1;
                            }
                            WindowsDeleteString(v41);
                          }
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
                        }
                        WindowsDeleteString(v43);
                      }
                      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v39);
                    }
                    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v44);
                  }
                }
                WindowsDeleteString(string);
                if ( ActivationFactory < 0 || v14 )
                  break;
                Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v37);
                v34 = v36;
                if ( ++v10 >= v36 )
                  goto LABEL_30;
              }
              Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v37);
              v34 = v36;
LABEL_30:
              if ( v10 == v34 )
                ActivationFactory = -2147024846;
            }
          }
        }
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v40);
      }
      CoTaskMemFree(pv);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v45);
    }
  }
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18003e4dc  mov     [rsp-8+arg_0], rbx
0x18003e4e1  mov     [rsp-8+arg_18], rsi
0x18003e4e6  push    rbp
0x18003e4e7  push    rdi
0x18003e4e8  push    r12
0x18003e4ea  push    r14
0x18003e4ec  push    r15
0x18003e4ee  lea     rbp, [rsp-37h]
0x18003e4f3  sub     rsp, 0C0h
0x18003e4fa  mov     rax, cs:__security_cookie
0x18003e501  xor     rax, rsp
0x18003e504  mov     [rbp+57h+var_30], rax
0x18003e508  xor     r12d, r12d
0x18003e50b  mov     [rbp+57h+string], rdx
0x18003e50f  lea     rcx, [rbp+57h+var_60]
0x18003e513  mov     [rbp+57h+var_60], r12
0x18003e517  mov     r15b, r8b
0x18003e51a  mov     rbx, rdx
0x18003e51d  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18003e522  lea     rax, [rbp+57h+var_60]
0x18003e526  xor     edx, edx; pUnkOuter
0x18003e528  lea     r9, _GUID_4e530b0a_e611_4c77_a3ac_9031d022281b; riid
0x18003e52f  mov     [rsp+0E0h+ppv], rax; ppv
0x18003e534  lea     r8d, [r12+3]; dwClsContext
0x18003e539  lea     rcx, _GUID_591209c7_767b_42b2_9fba_44ee4615f2c7; rclsid
0x18003e540  call    cs:__imp_CoCreateInstance
0x18003e547  nop     dword ptr [rax+rax+00h]
0x18003e54c  mov     edi, eax
0x18003e54e  test    eax, eax
0x18003e550  js      loc_18003E8E7
0x18003e556  mov     rcx, [rbp+57h+var_60]
0x18003e55a  lea     rdx, [rbp+57h+pv]
0x18003e55e  mov     [rbp+57h+pv], r12
0x18003e562  lea     r9d, [r12+1]
0x18003e567  mov     [rsp+0E0h+ppv], rdx
0x18003e56c  mov     r8d, r9d
0x18003e56f  mov     rdx, rbx
0x18003e572  mov     rax, [rcx]
0x18003e575  mov     rax, [rax+18h]
0x18003e579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e57e  mov     edi, eax
0x18003e580  test    eax, eax
0x18003e582  js      loc_18003E8E7
0x18003e588  lea     r9d, [r12+29h]; unsigned int
0x18003e58d  mov     [rbp+57h+var_68], r12
0x18003e591  lea     r8d, [r12+2Ah]; unsigned int
0x18003e596  mov     [rbp+57h+var_38], r12
0x18003e59a  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Protocol@@3QBGB; "Windows.Internal.StateRepository.Protoc"...
0x18003e5a1  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18003e5a5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003e5aa  mov     rbx, [rbp+57h+var_38]
0x18003e5ae  lea     rcx, [rbp+57h+var_68]
0x18003e5b2  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18003e5b7  lea     r8, [rbp+57h+var_68]
0x18003e5bb  mov     rcx, rbx
0x18003e5be  lea     rdx, _GUID_0f2f217e_7957_4262_a74c_df03d9e9e9c1
0x18003e5c5  call    cs:__imp_RoGetActivationFactory
0x18003e5cc  nop     dword ptr [rax+rax+00h]
0x18003e5d1  mov     edi, eax
0x18003e5d3  test    eax, eax
0x18003e5d5  js      loc_18003E8CE
0x18003e5db  mov     rdi, [rbp+57h+var_68]
0x18003e5df  lea     rcx, [rbp+57h+var_90]
0x18003e5e3  mov     [rbp+57h+var_90], r12
0x18003e5e7  mov     rax, [rdi]
0x18003e5ea  mov     rbx, [rax+0C8h]
0x18003e5f1  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18003e5f6  lea     rdx, [rbp+57h+string]
0x18003e5fa  lea     rcx, [rbp+57h+hstringHeader]
0x18003e5fe  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003e603  lea     r9, [rbp+57h+var_90]
0x18003e607  xor     edx, edx
0x18003e609  mov     rcx, rdi
0x18003e60c  mov     r8, [rax+18h]
0x18003e610  mov     rax, rbx
0x18003e613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e618  mov     edi, eax
0x18003e61a  test    eax, eax
0x18003e61c  js      loc_18003E8C5
0x18003e622  mov     rcx, [rbp+57h+var_90]
0x18003e626  lea     rdx, [rbp+57h+var_B0]
0x18003e62a  mov     [rbp+57h+var_B0], r12d
0x18003e62e  mov     rax, [rcx]
0x18003e631  mov     rax, [rax+38h]
0x18003e635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e63a  mov     edi, eax
0x18003e63c  test    eax, eax
0x18003e63e  js      loc_18003E8C5
0x18003e644  mov     eax, [rbp+57h+var_B0]
0x18003e647  cmp     eax, 1
0x18003e64a  jb      loc_18003E8C5
0x18003e650  mov     esi, r12d
0x18003e653  test    eax, eax
0x18003e655  jz      loc_18003E8BB
0x18003e65b  mov     rdi, [rbp+57h+var_90]
0x18003e65f  lea     rcx, [rbp+57h+var_A8]
0x18003e663  mov     [rbp+57h+var_A8], r12
0x18003e667  mov     rax, [rdi]
0x18003e66a  mov     rbx, [rax+30h]
0x18003e66e  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18003e673  lea     r8, [rbp+57h+var_A8]
0x18003e677  mov     edx, esi
0x18003e679  mov     rcx, rdi
0x18003e67c  mov     rax, rbx
0x18003e67f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e684  mov     edi, eax
0x18003e686  test    eax, eax
0x18003e688  js      loc_18003E8AF
0x18003e68e  mov     rdi, [rbp+57h+var_A8]
0x18003e692  xor     ecx, ecx; string
0x18003e694  mov     [rbp+57h+string], r12
0x18003e698  mov     r14d, r12d
0x18003e69b  mov     rax, [rdi]
0x18003e69e  mov     rbx, [rax+70h]
0x18003e6a2  call    cs:__imp_WindowsDeleteString
0x18003e6a9  nop     dword ptr [rax+rax+00h]
0x18003e6ae  lea     rdx, [rbp+57h+string]
0x18003e6b2  mov     [rbp+57h+string], r12
0x18003e6b6  mov     rcx, rdi
0x18003e6b9  mov     rax, rbx
0x18003e6bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e6c1  mov     edi, eax
0x18003e6c3  test    eax, eax
0x18003e6c5  js      loc_18003E87E
0x18003e6cb  mov     rcx, [rbp+57h+string]; string
0x18003e6cf  xor     edx, edx; length
0x18003e6d1  call    cs:__imp_WindowsGetStringRawBuffer
0x18003e6d8  nop     dword ptr [rax+rax+00h]
0x18003e6dd  mov     rcx, [rbp+57h+pv]
0x18003e6e1  sub     rax, rcx
0x18003e6e4  movzx   edx, word ptr [rcx]
0x18003e6e7  movzx   r8d, word ptr [rcx+rax]
0x18003e6ec  sub     edx, r8d
0x18003e6ef  jnz     short loc_18003E6FA
0x18003e6f1  add     rcx, 2
0x18003e6f5  test    r8d, r8d
0x18003e6f8  jnz     short loc_18003E6E4
0x18003e6fa  test    edx, edx
0x18003e6fc  jnz     loc_18003E87E
0x18003e702  mov     rdi, [rbp+57h+var_A8]
0x18003e706  lea     rcx, [rbp+57h+var_70]
0x18003e70a  mov     [rbp+57h+var_70], r12
0x18003e70e  mov     rax, [rdi]
0x18003e711  mov     rbx, [rax+58h]
0x18003e715  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18003e71a  lea     rdx, [rbp+57h+var_70]
0x18003e71e  mov     rcx, rdi
0x18003e721  mov     rax, rbx
0x18003e724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e729  mov     edi, eax
0x18003e72b  test    eax, eax
0x18003e72d  js      loc_18003E875
0x18003e733  mov     rdi, [rbp+57h+var_70]
0x18003e737  lea     rcx, [rbp+57h+var_98]
0x18003e73b  mov     [rbp+57h+var_98], r12
0x18003e73f  mov     rax, [rdi]
0x18003e742  mov     rbx, [rax+48h]
0x18003e746  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18003e74b  lea     rdx, [rbp+57h+var_98]
0x18003e74f  mov     rcx, rdi
0x18003e752  mov     rax, rbx
0x18003e755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e75a  mov     edi, eax
0x18003e75c  test    eax, eax
0x18003e75e  js      loc_18003E86C
0x18003e764  mov     rdi, [rbp+57h+var_98]
0x18003e768  xor     ecx, ecx; string
0x18003e76a  mov     [rbp+57h+var_78], r12
0x18003e76e  mov     rax, [rdi]
0x18003e771  mov     rbx, [rax+0E8h]
0x18003e778  call    cs:__imp_WindowsDeleteString
0x18003e77f  nop     dword ptr [rax+rax+00h]
0x18003e784  lea     rdx, [rbp+57h+var_78]
0x18003e788  mov     [rbp+57h+var_78], r12
0x18003e78c  mov     rcx, rdi
0x18003e78f  mov     rax, rbx
0x18003e792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e797  mov     edi, eax
0x18003e799  test    eax, eax
0x18003e79b  js      loc_18003E85C
0x18003e7a1  mov     rdi, [rbp+57h+var_98]
0x18003e7a5  lea     rcx, [rbp+57h+var_80]
0x18003e7a9  mov     [rbp+57h+var_80], r12
0x18003e7ad  mov     rax, [rdi]
0x18003e7b0  mov     rbx, [rax+48h]
0x18003e7b4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003e7b9  lea     rdx, [rbp+57h+var_80]
0x18003e7bd  mov     rcx, rdi
0x18003e7c0  mov     rax, rbx
0x18003e7c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e7c8  mov     edi, eax
0x18003e7ca  test    eax, eax
0x18003e7cc  js      loc_18003E853
0x18003e7d2  mov     rdi, [rbp+57h+var_80]
0x18003e7d6  xor     ecx, ecx; string
0x18003e7d8  mov     [rbp+57h+var_88], r12
0x18003e7dc  mov     rax, [rdi]
0x18003e7df  mov     rbx, [rax+70h]
0x18003e7e3  call    cs:__imp_WindowsDeleteString
0x18003e7ea  nop     dword ptr [rax+rax+00h]
0x18003e7ef  lea     rdx, [rbp+57h+var_88]
0x18003e7f3  mov     [rbp+57h+var_88], r12
0x18003e7f7  mov     rcx, rdi
0x18003e7fa  mov     rax, rbx
0x18003e7fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e802  mov     edi, eax
0x18003e804  test    eax, eax
0x18003e806  js      short loc_18003E843
0x18003e808  mov     rcx, [rbp+57h+var_88]; string
0x18003e80c  xor     edx, edx; length
0x18003e80e  call    cs:__imp_WindowsGetStringRawBuffer
0x18003e815  nop     dword ptr [rax+rax+00h]
0x18003e81a  mov     rcx, [rbp+57h+var_78]; string
0x18003e81e  xor     edx, edx; length
0x18003e820  mov     rbx, rax
0x18003e823  call    cs:__imp_WindowsGetStringRawBuffer
0x18003e82a  nop     dword ptr [rax+rax+00h]
0x18003e82f  mov     r9b, r15b; bool
0x18003e832  mov     r8, rbx; unsigned __int16 *
0x18003e835  mov     rdx, rax; unsigned __int16 *
0x18003e838  call    ?NotifyDefaultApp@CApplicationPreLaunchNotifications@@AEAAXPEBG0_N@Z; CApplicationPreLaunchNotifications::NotifyDefaultApp(ushort const *,ushort const *,bool)
0x18003e83d  mov     r14d, 1
0x18003e843  mov     rcx, [rbp+57h+var_88]; string
0x18003e847  call    cs:__imp_WindowsDeleteString
0x18003e84e  nop     dword ptr [rax+rax+00h]
0x18003e853  lea     rcx, [rbp+57h+var_80]
0x18003e857  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003e85c  mov     rcx, [rbp+57h+var_78]; string
0x18003e860  call    cs:__imp_WindowsDeleteString
0x18003e867  nop     dword ptr [rax+rax+00h]
0x18003e86c  lea     rcx, [rbp+57h+var_98]
0x18003e870  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18003e875  lea     rcx, [rbp+57h+var_70]
0x18003e879  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18003e87e  mov     rcx, [rbp+57h+string]; string
0x18003e882  call    cs:__imp_WindowsDeleteString
0x18003e889  nop     dword ptr [rax+rax+00h]
0x18003e88e  test    edi, edi
0x18003e890  js      short loc_18003E8AF
0x18003e892  test    r14d, r14d
0x18003e895  jnz     short loc_18003E8AF
0x18003e897  lea     rcx, [rbp+57h+var_A8]
0x18003e89b  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18003e8a0  mov     eax, [rbp+57h+var_B0]
0x18003e8a3  inc     esi
0x18003e8a5  cmp     esi, eax
0x18003e8a7  jb      loc_18003E65B
0x18003e8ad  jmp     short loc_18003E8BB
0x18003e8af  lea     rcx, [rbp+57h+var_A8]
0x18003e8b3  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18003e8b8  mov     eax, [rbp+57h+var_B0]
0x18003e8bb  cmp     esi, eax
0x18003e8bd  mov     ecx, 80070032h
0x18003e8c2  cmovz   edi, ecx
0x18003e8c5  lea     rcx, [rbp+57h+var_90]
0x18003e8c9  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18003e8ce  mov     rcx, [rbp+57h+pv]; pv
0x18003e8d2  call    cs:__imp_CoTaskMemFree
0x18003e8d9  nop     dword ptr [rax+rax+00h]
0x18003e8de  lea     rcx, [rbp+57h+var_68]
0x18003e8e2  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18003e8e7  lea     rcx, [rbp+57h+var_60]
0x18003e8eb  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18003e8f0  mov     eax, edi
0x18003e8f2  mov     rcx, [rbp+57h+var_30]
0x18003e8f6  xor     rcx, rsp; StackCookie
0x18003e8f9  call    __security_check_cookie
0x18003e8fe  lea     r11, [rsp+0E0h+var_20]
0x18003e906  mov     rbx, [r11+30h]
0x18003e90a  mov     rsi, [r11+48h]
0x18003e90e  mov     rsp, r11
0x18003e911  pop     r15
0x18003e913  pop     r14
0x18003e915  pop     r12
0x18003e917  pop     rdi
0x18003e918  pop     rbp
0x18003e919  retn
```
