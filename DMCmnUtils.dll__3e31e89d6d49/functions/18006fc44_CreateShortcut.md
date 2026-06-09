# CreateShortcut

- ea: `0x18006fc44`
- end: `0x18007022c`
- name: `CreateShortcut`
- size: `1512`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800704a0`

## callees

- `0x180007270`
- `0x180007620`
- `0x180007c7c`
- `0x180051ea0`
- `0x180051f08`
- `0x180057c4c`
- `0x180057c6c`
- `0x180059d18`
- `0x180064a44`
- `0x18006fc44`
- `0x1800725a0`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18006fcc8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18006fcc8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800701fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800701fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006fcef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006fcef`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006fd52`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006fd52`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006fe7c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006ff03`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006ff15`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006ff9b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006fff5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007009e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800701ab`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800701bd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800701cf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006fe7c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006ff03`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006ff15`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006ff9b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006fff5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007009e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800701ab`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800701bd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800701cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006feba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006feba`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18006fd02`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18006fd02`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180070071`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180070071`
- `PROPSYS!InitPropVariantFromCLSID` at `0x18006ffc2`
- `PROPSYS!InitPropVariantFromCLSID` at `0x18006ffc2`

## string_xrefs

- `0x18007006a`: `C:\Windows\System32\Shell32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CreateShortcut(__int64 a1, const WCHAR *a2, _WORD *a3, const IID *a4)
{
  __int64 v8; // r14
  unsigned int LastError; // esi
  HRESULT inited; // ebx
  __int64 v11; // rdx
  LPVOID v12; // rbx
  __int64 (__fastcall *v13)(LPVOID, GUID *, __int64 *); // rdi
  int v14; // eax
  int v15; // eax
  __int64 v16; // r14
  void *v17; // rax
  int v18; // eax
  __int64 v19; // rdx
  const char *v20; // r9
  LPVOID v21; // rbx
  __int64 (__fastcall *v22)(LPVOID, GUID *, __int64 *); // rdi
  int v23; // eax
  int v24; // eax
  __int64 v25; // rdx
  int ppv; // [rsp+20h] [rbp-E0h]
  LPVOID v28; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v29; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v30; // [rsp+40h] [rbp-C0h] BYREF
  PROPVARIANT v31[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+58h] [rbp-A8h]
  PROPVARIANT pvar[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v34; // [rsp+70h] [rbp-90h]
  PROPVARIANT ppropvar[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v36; // [rsp+88h] [rbp-78h]
  struct _RTL_CRITICAL_SECTION *v37; // [rsp+90h] [rbp-70h]
  WCHAR Dst; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v39[526]; // [rsp+A2h] [rbp-5Eh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  v8 = -1;
  if ( dword_18010E328 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18010E328);
    if ( dword_18010E328 == -1 )
    {
      InitializeCriticalSectionEx(&stru_18010E330, 0, 0);
      atexit(CreateShortcut_::_2_::_dynamic_atexit_destructor_for__s_criticalSection__);
      Init_thread_footer(&dword_18010E328);
    }
  }
  EnterCriticalSection(&stru_18010E330);
  v37 = &stru_18010E330;
  if ( GetFileAttributesW(a2) == -1 )
  {
    v28 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    inited = CoCreateInstance(&CLSID_ShellLink, 0, 1u, &GUID_000214f9_0000_0000_c000_000000000046, &v28);
    if ( inited < 0 )
    {
      v11 = 100;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
        (const char *)(unsigned int)inited,
        ppv);
LABEL_9:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
      LastError = inited;
      goto LABEL_49;
    }
    inited = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v28 + 160LL))(v28, a1);
    if ( inited < 0 )
    {
      v11 = 101;
      goto LABEL_8;
    }
    v29 = 0;
    v12 = v28;
    v13 = **(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v28;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
    v14 = v13(v12, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &v29);
    inited = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x68,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
        (const char *)(unsigned int)v14,
        ppv);
LABEL_14:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
      goto LABEL_9;
    }
    *(_OWORD *)pvar = 0;
    v34 = 0;
    LOWORD(pvar[0]) = 11;
    LOWORD(pvar[1]) = -1;
    v15 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v29 + 48LL))(
            v29,
            &PKEY_AppUserModel_PreventPinning,
            pvar);
    inited = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6D,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
        (const char *)(unsigned int)v15,
        ppv);
LABEL_17:
      PropVariantClear(pvar);
      goto LABEL_14;
    }
    *(_OWORD *)v31 = 0;
    v32 = 0;
    if ( !a3 )
    {
      LastError = -2147024809;
LABEL_23:
      *(_OWORD *)v31 = 0;
      v32 = 0;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x71,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
        (const char *)LastError,
        ppv);
LABEL_24:
      PropVariantClear(v31);
      PropVariantClear(pvar);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
      goto LABEL_49;
    }
    do
      ++v8;
    while ( a3[v8] );
    v16 = 2 * v8 + 2;
    v17 = CoTaskMemAlloc(v16);
    v31[1] = v17;
    if ( !v17 )
    {
      LastError = -2147024882;
      goto LABEL_23;
    }
    memcpy_s(v17, v16, a3, v16);
    LOWORD(v31[0]) = 31;
    v18 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v29 + 48LL))(
            v29,
            &PKEY_AppUserModel_ID,
            v31);
    inited = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x72,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
        (const char *)(unsigned int)v18,
        ppv);
LABEL_27:
      PropVariantClear(v31);
      goto LABEL_17;
    }
    *(_OWORD *)ppropvar = 0;
    v36 = 0;
    inited = InitPropVariantFromCLSID(a4, ppropvar);
    if ( inited >= 0 )
    {
      inited = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v29 + 48LL))(
                 v29,
                 &PKEY_AppUserModel_ToastActivatorCLSID,
                 ppropvar);
      if ( inited >= 0 )
      {
        inited = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 56LL))(v29);
        if ( inited >= 0 )
        {
          Dst = 0;
          memset_0(v39, 0, 0x206u);
          if ( ExpandEnvironmentStringsW(L"C:\\Windows\\System32\\Shell32.dll", &Dst, 0x104u) )
          {
            inited = (*(__int64 (__fastcall **)(LPVOID, WCHAR *, __int64))(*(_QWORD *)v28 + 136LL))(
                       v28,
                       &Dst,
                       4294950470LL);
            if ( inited < 0 )
            {
              v19 = 127;
              goto LABEL_30;
            }
            v30 = 0;
            v21 = v28;
            v22 = **(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v28;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
            v23 = v22(v21, &GUID_0000010b_0000_0000_c000_000000000046, &v30);
            inited = v23;
            if ( v23 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x83,
                (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
                (const char *)(unsigned int)v23,
                ppv);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
              goto LABEL_31;
            }
            v24 = (*(__int64 (__fastcall **)(__int64, const WCHAR *, __int64))(*(_QWORD *)v30 + 48LL))(v30, a2, 1);
            LastError = v24;
            if ( v24 >= 0 )
            {
              v24 = WaitForAppResolver();
              LastError = v24;
              if ( v24 >= 0 )
              {
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
                PropVariantClear(ppropvar);
                PropVariantClear(v31);
                PropVariantClear(pvar);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
                LastError = 0;
                goto LABEL_49;
              }
              v25 = 134;
            }
            else
            {
              v25 = 132;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v25,
              (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
              (const char *)(unsigned int)v24,
              ppv);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
          }
          else
          {
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x7E,
                          (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
                          v20);
          }
          PropVariantClear(ppropvar);
          goto LABEL_24;
        }
        v19 = 122;
      }
      else
      {
        v19 = 119;
      }
    }
    else
    {
      v19 = 118;
    }
LABEL_30:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
      (const char *)(unsigned int)inited,
      ppv);
LABEL_31:
    PropVariantClear(ppropvar);
    goto LABEL_27;
  }
  LastError = 1;
LABEL_49:
  LeaveCriticalSection(&stru_18010E330);
  return LastError;
}

```

## disassembly

```asm
0x18006fc44  push    rbp
0x18006fc46  push    rbx
0x18006fc47  push    rsi
0x18006fc48  push    rdi
0x18006fc49  push    r12
0x18006fc4b  push    r13
0x18006fc4d  push    r14
0x18006fc4f  push    r15
0x18006fc51  lea     rbp, [rsp-1C8h]
0x18006fc59  sub     rsp, 2C8h
0x18006fc60  mov     rax, cs:__security_cookie
0x18006fc67  xor     rax, rsp
0x18006fc6a  mov     [rbp+200h+var_50], rax
0x18006fc71  mov     r13, r9
0x18006fc74  mov     r15, r8
0x18006fc77  mov     r12, rdx
0x18006fc7a  mov     rdi, rcx
0x18006fc7d  mov     ecx, cs:_tls_index
0x18006fc83  mov     rax, gs:58h
0x18006fc8c  mov     edx, 4
0x18006fc91  mov     rax, [rax+rcx*8]
0x18006fc95  or      r14, 0FFFFFFFFFFFFFFFFh
0x18006fc99  lea     rsi, stru_18010E330
0x18006fca0  mov     eax, [rdx+rax]
0x18006fca3  cmp     cs:dword_18010E328, eax
0x18006fca9  jle     short loc_18006FCEC
0x18006fcab  lea     rcx, dword_18010E328
0x18006fcb2  call    _Init_thread_header
0x18006fcb7  cmp     cs:dword_18010E328, r14d
0x18006fcbe  jnz     short loc_18006FCEC
0x18006fcc0  xor     r8d, r8d; Flags
0x18006fcc3  xor     edx, edx; dwSpinCount
0x18006fcc5  mov     rcx, rsi; lpCriticalSection
0x18006fcc8  call    cs:__imp_InitializeCriticalSectionEx
0x18006fccf  nop     dword ptr [rax+rax+00h]
0x18006fcd4  lea     rcx, _CreateShortcut____2____dynamic_atexit_destructor_for__s_criticalSection__; void (__cdecl *)()
0x18006fcdb  call    atexit
0x18006fce0  lea     rcx, dword_18010E328
0x18006fce7  call    _Init_thread_footer
0x18006fcec  mov     rcx, rsi; lpCriticalSection
0x18006fcef  call    cs:__imp_EnterCriticalSection
0x18006fcf6  nop     dword ptr [rax+rax+00h]
0x18006fcfb  mov     [rbp+200h+var_270], rsi
0x18006fcff  mov     rcx, r12; lpFileName
0x18006fd02  call    cs:__imp_GetFileAttributesW
0x18006fd09  nop     dword ptr [rax+rax+00h]
0x18006fd0e  cmp     eax, 0FFFFFFFFh
0x18006fd11  jnb     short loc_18006FD1D
0x18006fd13  mov     esi, 1
0x18006fd18  jmp     loc_1800701F3
0x18006fd1d  mov     [rsp+300h+var_2D0], 0
0x18006fd26  lea     rcx, [rsp+300h+var_2D0]
0x18006fd2b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006fd30  lea     rax, [rsp+300h+var_2D0]
0x18006fd35  mov     qword ptr [rsp+300h+ppv], rax; int
0x18006fd3a  lea     r9, _GUID_000214f9_0000_0000_c000_000000000046; riid
0x18006fd41  mov     esi, 1
0x18006fd46  mov     r8d, esi; dwClsContext
0x18006fd49  xor     edx, edx; pUnkOuter
0x18006fd4b  lea     rcx, CLSID_ShellLink; rclsid
0x18006fd52  call    cs:__imp_CoCreateInstance
0x18006fd59  nop     dword ptr [rax+rax+00h]
0x18006fd5e  mov     ebx, eax
0x18006fd60  test    eax, eax
0x18006fd62  jns     short loc_18006FD8F
0x18006fd64  lea     edx, [rsi+63h]; void *
0x18006fd67  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\dm\\dmcmnutils\\toas"...
0x18006fd6e  mov     r9d, ebx; char *
0x18006fd71  mov     rcx, [rbp+208h]; this
0x18006fd78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006fd7d  nop
0x18006fd7e  lea     rcx, [rsp+300h+var_2D0]
0x18006fd83  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006fd88  mov     esi, ebx
0x18006fd8a  jmp     loc_1800701F3
0x18006fd8f  mov     rcx, [rsp+300h+var_2D0]
0x18006fd94  mov     rax, [rcx]
0x18006fd97  mov     rdx, rdi
0x18006fd9a  mov     rax, [rax+0A0h]
0x18006fda1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fda6  mov     ebx, eax
0x18006fda8  test    eax, eax
0x18006fdaa  jns     short loc_18006FDB3
0x18006fdac  mov     edx, 65h ; 'e'
0x18006fdb1  jmp     short loc_18006FD67
0x18006fdb3  mov     [rsp+300h+var_2C8], 0
0x18006fdbc  mov     rbx, [rsp+300h+var_2D0]
0x18006fdc1  mov     rax, [rbx]
0x18006fdc4  mov     rdi, [rax]
0x18006fdc7  lea     rcx, [rsp+300h+var_2C8]
0x18006fdcc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006fdd1  lea     r8, [rsp+300h+var_2C8]
0x18006fdd6  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18006fddd  mov     rcx, rbx
0x18006fde0  mov     rax, rdi
0x18006fde3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fde8  mov     ebx, eax
0x18006fdea  xor     edi, edi
0x18006fdec  test    eax, eax
0x18006fdee  jns     short loc_18006FE19
0x18006fdf0  mov     rcx, [rbp+208h]; this
0x18006fdf7  mov     r9d, eax; char *
0x18006fdfa  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\dm\\dmcmnutils\\toas"...
0x18006fe01  lea     edx, [rdi+68h]; void *
0x18006fe04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006fe09  nop
0x18006fe0a  lea     rcx, [rsp+300h+var_2C8]
0x18006fe0f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006fe14  jmp     loc_18006FD7E
0x18006fe19  xorps   xmm0, xmm0
0x18006fe1c  xor     eax, eax
0x18006fe1e  movups  xmmword ptr [rsp+300h+pvar], xmm0
0x18006fe23  mov     [rsp+300h+var_290], rax
0x18006fe28  mov     eax, 0Bh
0x18006fe2d  mov     word ptr [rsp+300h+pvar], ax
0x18006fe32  mov     word ptr [rsp+300h+pvar+8], r14w
0x18006fe38  mov     rcx, [rsp+300h+var_2C8]
0x18006fe3d  mov     rax, [rcx]
0x18006fe40  lea     r8, [rsp+300h+pvar]
0x18006fe45  lea     rdx, PKEY_AppUserModel_PreventPinning
0x18006fe4c  mov     rax, [rax+30h]
0x18006fe50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fe55  mov     ebx, eax
0x18006fe57  test    eax, eax
0x18006fe59  jns     short loc_18006FE8A
0x18006fe5b  mov     rcx, [rbp+208h]; this
0x18006fe62  mov     r9d, eax; char *
0x18006fe65  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\dm\\dmcmnutils\\toas"...
0x18006fe6c  mov     edx, 6Dh ; 'm'; void *
0x18006fe71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006fe76  nop
0x18006fe77  lea     rcx, [rsp+300h+pvar]; pvar
0x18006fe7c  call    cs:__imp_PropVariantClear
0x18006fe83  nop     dword ptr [rax+rax+00h]
0x18006fe88  jmp     short loc_18006FE0A
0x18006fe8a  xorps   xmm0, xmm0
0x18006fe8d  xor     eax, eax
0x18006fe8f  movups  xmmword ptr [rsp+300h+var_2B8], xmm0
0x18006fe94  mov     [rsp+300h+var_2A8], rax
0x18006fe99  test    r15, r15
0x18006fe9c  jnz     short loc_18006FEA5
0x18006fe9e  mov     esi, 80070057h
0x18006fea3  jmp     short loc_18006FED5
0x18006fea5  inc     r14
0x18006fea8  cmp     [r15+r14*2], di
0x18006fead  jnz     short loc_18006FEA5
0x18006feaf  lea     r14, ds:2[r14*2]
0x18006feb7  mov     rcx, r14; cb
0x18006feba  call    cs:__imp_CoTaskMemAlloc
0x18006fec1  nop     dword ptr [rax+rax+00h]
0x18006fec6  mov     [rsp+300h+var_2B8+8], rax
0x18006fecb  test    rax, rax
0x18006fece  jnz     short loc_18006FF3C
0x18006fed0  mov     esi, 8007000Eh
0x18006fed5  xorps   xmm0, xmm0
0x18006fed8  xor     eax, eax
0x18006feda  movups  xmmword ptr [rsp+300h+var_2B8], xmm0
0x18006fedf  mov     [rsp+300h+var_2A8], rax
0x18006fee4  mov     rcx, [rbp+208h]; this
0x18006feeb  mov     r9d, esi; char *
0x18006feee  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\dm\\dmcmnutils\\toas"...
0x18006fef5  lea     edx, [rax+71h]; void *
0x18006fef8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006fefd  nop
0x18006fefe  lea     rcx, [rsp+300h+var_2B8]; pvar
0x18006ff03  call    cs:__imp_PropVariantClear
0x18006ff0a  nop     dword ptr [rax+rax+00h]
0x18006ff0f  nop
0x18006ff10  lea     rcx, [rsp+300h+pvar]; pvar
0x18006ff15  call    cs:__imp_PropVariantClear
0x18006ff1c  nop     dword ptr [rax+rax+00h]
0x18006ff21  nop
0x18006ff22  lea     rcx, [rsp+300h+var_2C8]
0x18006ff27  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006ff2c  nop
0x18006ff2d  lea     rcx, [rsp+300h+var_2D0]
0x18006ff32  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006ff37  jmp     loc_1800701F3
0x18006ff3c  mov     r9, r14; SourceSize
0x18006ff3f  mov     r8, r15; Source
0x18006ff42  mov     rdx, r14; DestinationSize
0x18006ff45  mov     rcx, rax; Destination
0x18006ff48  call    memcpy_s
0x18006ff4d  mov     eax, 1Fh
0x18006ff52  mov     word ptr [rsp+300h+var_2B8], ax
0x18006ff57  mov     rcx, [rsp+300h+var_2C8]
0x18006ff5c  mov     rax, [rcx]
0x18006ff5f  lea     r8, [rsp+300h+var_2B8]
0x18006ff64  lea     rdx, PKEY_AppUserModel_ID
0x18006ff6b  mov     rax, [rax+30h]
0x18006ff6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ff74  mov     ebx, eax
0x18006ff76  test    eax, eax
0x18006ff78  jns     short loc_18006FFAC
0x18006ff7a  mov     rcx, [rbp+208h]; this
0x18006ff81  mov     r9d, eax; char *
0x18006ff84  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\dm\\dmcmnutils\\toas"...
0x18006ff8b  mov     edx, 72h ; 'r'; void *
0x18006ff90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ff95  nop
0x18006ff96  lea     rcx, [rsp+300h+var_2B8]; pvar
0x18006ff9b  call    cs:__imp_PropVariantClear
0x18006ffa2  nop     dword ptr [rax+rax+00h]
0x18006ffa7  jmp     loc_18006FE77
0x18006ffac  xorps   xmm0, xmm0
0x18006ffaf  xor     eax, eax
0x18006ffb1  movups  xmmword ptr [rsp+300h+ppropvar], xmm0
0x18006ffb6  mov     [rbp+200h+var_278], rax
0x18006ffba  lea     rdx, [rsp+300h+ppropvar]; ppropvar
0x18006ffbf  mov     rcx, r13; clsid
0x18006ffc2  call    cs:__imp_InitPropVariantFromCLSID
0x18006ffc9  nop     dword ptr [rax+rax+00h]
0x18006ffce  mov     ebx, eax
0x18006ffd0  test    eax, eax
0x18006ffd2  jns     short loc_180070003
0x18006ffd4  mov     edx, 76h ; 'v'; void *
0x18006ffd9  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\dm\\dmcmnutils\\toas"...
0x18006ffe0  mov     r9d, ebx; char *
0x18006ffe3  mov     rcx, [rbp+208h]; this
0x18006ffea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ffef  nop
0x18006fff0  lea     rcx, [rsp+300h+ppropvar]; pvar
0x18006fff5  call    cs:__imp_PropVariantClear
0x18006fffc  nop     dword ptr [rax+rax+00h]
0x180070001  jmp     short loc_18006FF96
0x180070003  mov     rcx, [rsp+300h+var_2C8]
0x180070008  mov     rax, [rcx]
0x18007000b  lea     r8, [rsp+300h+ppropvar]
0x180070010  lea     rdx, PKEY_AppUserModel_ToastActivatorCLSID
0x180070017  mov     rax, [rax+30h]
0x18007001b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070020  mov     ebx, eax
0x180070022  test    eax, eax
0x180070024  jns     short loc_18007002D
0x180070026  mov     edx, 77h ; 'w'
0x18007002b  jmp     short loc_18006FFD9
0x18007002d  mov     rcx, [rsp+300h+var_2C8]
0x180070032  mov     rax, [rcx]
0x180070035  mov     rax, [rax+38h]
0x180070039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007003e  mov     ebx, eax
0x180070040  test    eax, eax
0x180070042  jns     short loc_18007004B
0x180070044  mov     edx, 7Ah ; 'z'
0x180070049  jmp     short loc_18006FFD9
0x18007004b  mov     [rbp+200h+Dst], di
0x18007004f  xor     edx, edx; Val
0x180070051  mov     r8d, 206h; Size
0x180070057  lea     rcx, [rbp+200h+var_25E]; void *
0x18007005b  call    memset_0
0x180070060  mov     r8d, 104h; nSize
0x180070066  lea     rdx, [rbp+200h+Dst]; lpDst
0x18007006a  lea     rcx, aCWindowsSystem; "C:\\Windows\\System32\\Shell32.dll"
0x180070071  call    cs:__imp_ExpandEnvironmentStringsW
0x180070078  nop     dword ptr [rax+rax+00h]
0x18007007d  test    eax, eax
0x18007007f  jnz     short loc_1800700AF
0x180070081  mov     rcx, [rbp+208h]; this
0x180070088  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\dm\\dmcmnutils\\toas"...
0x18007008f  lea     edx, [rax+7Eh]; void *
0x180070092  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180070097  mov     esi, eax
0x180070099  lea     rcx, [rsp+300h+ppropvar]; pvar
0x18007009e  call    cs:__imp_PropVariantClear
0x1800700a5  nop     dword ptr [rax+rax+00h]
0x1800700aa  jmp     loc_18006FEFE
0x1800700af  mov     rcx, [rsp+300h+var_2D0]
0x1800700b4  mov     rax, [rcx]
0x1800700b7  mov     r8d, 0FFFFBE46h
0x1800700bd  lea     rdx, [rbp+200h+Dst]
0x1800700c1  mov     rax, [rax+88h]
0x1800700c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800700cd  mov     ebx, eax
0x1800700cf  test    eax, eax
0x1800700d1  jns     short loc_1800700DD
0x1800700d3  mov     edx, 7Fh
0x1800700d8  jmp     loc_18006FFD9
0x1800700dd  mov     [rsp+300h+var_2C0], rdi
0x1800700e2  mov     rbx, [rsp+300h+var_2D0]
0x1800700e7  mov     rax, [rbx]
0x1800700ea  mov     rdi, [rax]
0x1800700ed  lea     rcx, [rsp+300h+var_2C0]
0x1800700f2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800700f7  lea     r8, [rsp+300h+var_2C0]
0x1800700fc  lea     rdx, _GUID_0000010b_0000_0000_c000_000000000046
0x180070103  mov     rcx, rbx
0x180070106  mov     rax, rdi
0x180070109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007010e  mov     ebx, eax
0x180070110  xor     edi, edi
0x180070112  test    eax, eax
0x180070114  jns     short loc_180070141
0x180070116  mov     rcx, [rbp+208h]; this
0x18007011d  mov     r9d, eax; char *
0x180070120  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\dm\\dmcmnutils\\toas"...
0x180070127  mov     edx, 83h; void *
0x18007012c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180070131  nop
0x180070132  lea     rcx, [rsp+300h+var_2C0]
0x180070137  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
  ... truncated ...
```
