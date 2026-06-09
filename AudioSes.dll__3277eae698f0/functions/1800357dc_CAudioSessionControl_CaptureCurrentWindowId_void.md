# CAudioSessionControl::CaptureCurrentWindowId(void)

- ea: `0x1800357dc`
- end: `0x180035f56`
- name: `?CaptureCurrentWindowId@CAudioSessionControl@@AEAAJXZ`
- size: `1914`
- prototype: `__int64 __fastcall(CAudioSessionControl *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180070820`

## callees

- `0x180007f00`
- `0x180010a90`
- `0x1800357dc`
- `0x180035f5c`
- `0x180087e80`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180035e3d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180035e7f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180035e3d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180035e7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800359c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800359c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180035829`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180035955`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180035829`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180035955`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180035a5b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180035a5b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180035846`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180035972`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180035846`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180035972`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall CAudioSessionControl::CaptureCurrentWindowId(CAudioSessionControl *this)
{
  int (__fastcall *v2)(__int64, __int64 *); // rdi
  void (__fastcall *v3)(__int64, __int64 *); // rdi
  __int64 v4; // rcx
  int ActivationFactory; // ebx
  int v7; // eax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, __int64 *); // rbx
  DWORD CurrentThreadId; // eax
  int v11; // eax
  int v12; // eax
  HRESULT v13; // eax
  __int64 v14; // rax
  int v15; // eax
  int v16; // eax
  __int64 v17; // rdx
  int ppv; // [rsp+20h] [rbp-49h]
  int ppva; // [rsp+20h] [rbp-49h]
  _BYTE v20[8]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v21; // [rsp+38h] [rbp-31h] BYREF
  __int64 v22; // [rsp+40h] [rbp-29h] BYREF
  __int64 v23; // [rsp+48h] [rbp-21h] BYREF
  __int64 v24; // [rsp+50h] [rbp-19h] BYREF
  __int64 v25; // [rsp+58h] [rbp-11h] BYREF
  __int64 v26; // [rsp+60h] [rbp-9h] BYREF
  __int64 v27; // [rsp+68h] [rbp-1h] BYREF
  LPVOID v28; // [rsp+70h] [rbp+7h] BYREF
  __int64 v29; // [rsp+78h] [rbp+Fh] BYREF
  unsigned int v30; // [rsp+80h] [rbp+17h] BYREF
  int v31; // [rsp+84h] [rbp+1Bh] BYREF
  HSTRING string; // [rsp+88h] [rbp+1Fh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v24 = 0;
  v23 = 0;
  v26 = 0;
  if ( WindowsCreateStringReference(L"Windows.UI.Core.CoreWindow", 0x1Au, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  if ( (int)RoGetActivationFactory(string, &GUID_4d239005_3c2a_41b1_9022_536bb9cf93b1, &v26) >= 0 )
  {
    v2 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 48LL);
    v24 = 0;
    if ( v2(v26, &v24) >= 0 )
    {
      if ( v24 )
      {
        v3 = *(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 72LL);
        v23 = 0;
        v3(v24, &v23);
      }
    }
  }
  v20[0] = 0;
  v4 = v23;
  if ( !v23 )
    goto LABEL_10;
  (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v23 + 48LL))(v23, v20);
  if ( !v20[0] )
  {
LABEL_9:
    v4 = v23;
LABEL_10:
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    return 0;
  }
  v29 = 0;
  if ( WindowsCreateStringReference(L"Windows.ApplicationModel.Core.CoreApplication", 0x2Du, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(string, &GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1, &v29);
  if ( ActivationFactory < 0 )
    goto LABEL_112;
  if ( v29 )
  {
    v22 = 0;
    v7 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v29)(
           v29,
           &GUID_17b0e613_942a_422d_904c_f90dc71a7dae,
           &v22);
    ActivationFactory = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x199,
        (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientsubmix.cpp",
        (const char *)(unsigned int)v7,
        ppv);
    }
    else
    {
      v21 = 0;
      v8 = v22;
      v9 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v22 + 72LL);
      v21 = 0;
      CurrentThreadId = GetCurrentThreadId();
      ActivationFactory = v9(v8, CurrentThreadId, &v21);
      if ( ActivationFactory >= 0 )
      {
        if ( !v21 )
        {
          wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v21);
          wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v22);
          ActivationFactory = -2147023728;
LABEL_112:
          wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v29);
          wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v23);
          wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v24);
          wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v26);
          return (unsigned int)ActivationFactory;
        }
        v30 = 0;
        v25 = 0;
        v11 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v21)(
                v21,
                &GUID_9ebd287a_8a6b_4191_915f_01b8da7dc177,
                &v25);
        ActivationFactory = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1A1,
            (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientsubmix.cpp",
            (const char *)(unsigned int)v11,
            ppv);
          if ( v25 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
          if ( v21 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          if ( v22 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          if ( v29 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
          if ( v23 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
          if ( v24 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
          if ( v26 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          return (unsigned int)ActivationFactory;
        }
        v12 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v25 + 72LL))(v25, &v30);
        ActivationFactory = v12;
        if ( v12 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1A2,
            (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientsubmix.cpp",
            (const char *)(unsigned int)v12,
            ppv);
        }
        else
        {
          v28 = 0;
          v13 = CoCreateInstance(
                  &CLSID_ShellServiceHostBrokerProvider,
                  0,
                  4u,
                  &GUID_0f4accb1_d8f9_4011_ba37_2557925a78cf,
                  &v28);
          ActivationFactory = v13;
          if ( v13 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1A6,
              (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientsubmix.cpp",
              (const char *)(unsigned int)v13,
              ppva);
            if ( v28 )
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v28 + 16LL))(v28);
            if ( v25 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
            if ( v21 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
            if ( v22 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
            if ( v29 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
            if ( v23 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
            if ( v24 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
            if ( v26 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
            return (unsigned int)ActivationFactory;
          }
          v27 = 0;
          v14 = *(_QWORD *)v28;
          v27 = 0;
          v15 = (*(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, __int64 *))(v14 + 24))(
                  v28,
                  &GUID_1f79f7de_20bf_4591_930a_d490b78fb09f,
                  &GUID_23030752_8e7c_4225_8c88_28211f93ddf7,
                  &v27);
          ActivationFactory = v15;
          if ( v15 < 0 )
          {
            v17 = 425;
          }
          else
          {
            v31 = 0;
            v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v27 + 56LL))(v27, v30, &v31);
            ActivationFactory = v15;
            if ( v15 >= 0 )
            {
              if ( v31 )
                *((_DWORD *)this + 54) = v31;
              v16 = CAudioSessionControl::AudioServerSetWindowId((void **)this + 23, *((_DWORD *)this + 54));
              ActivationFactory = v16;
              if ( v16 >= 0 )
              {
                if ( v27 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
                if ( v28 )
                  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v28 + 16LL))(v28);
                if ( v25 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
                if ( v21 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
                if ( v22 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
                if ( v29 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
                goto LABEL_9;
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1B6,
                (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientsubmix.cpp",
                (const char *)(unsigned int)v16,
                ppva);
              if ( v27 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
              if ( v28 )
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v28 + 16LL))(v28);
              if ( v25 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
              if ( v21 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
              if ( v22 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
              if ( v29 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
              if ( v23 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
              if ( v24 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
              if ( v26 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
              return (unsigned int)ActivationFactory;
            }
            v17 = 429;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v17,
            (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientsubmix.cpp",
            (const char *)(unsigned int)v15,
            ppva);
          wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v27);
          wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v28);
        }
        wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v25);
      }
      wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v21);
    }
    wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v22);
    goto LABEL_112;
  }
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  return 2147943568LL;
}

```

## disassembly

```asm
0x1800357dc  mov     [rsp-8+arg_8], rbx
0x1800357e1  mov     [rsp-8+arg_10], rsi
0x1800357e6  push    rbp
0x1800357e7  push    rdi
0x1800357e8  push    r14
0x1800357ea  lea     rbp, [rsp-47h]
0x1800357ef  sub     rsp, 0B0h
0x1800357f6  mov     rax, cs:__security_cookie
0x1800357fd  xor     rax, rsp
0x180035800  mov     [rbp+57h+var_18], rax
0x180035804  mov     rsi, rcx
0x180035807  xor     r14d, r14d
0x18003580a  mov     [rbp+57h+var_70], r14
0x18003580e  mov     [rbp+57h+var_78], r14
0x180035812  mov     [rbp+57h+var_60], r14
0x180035816  lea     r9, [rbp+57h+string]; string
0x18003581a  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18003581e  lea     edx, [r14+1Ah]; length
0x180035822  lea     rcx, ?RuntimeClass_Windows_UI_Core_CoreWindow@@3QBGB; "Windows.UI.Core.CoreWindow"
0x180035829  call    cs:__imp_WindowsCreateStringReference
0x18003582f  test    eax, eax
0x180035831  js      loc_180035E2E
0x180035837  lea     r8, [rbp+57h+var_60]
0x18003583b  lea     rdx, _GUID_4d239005_3c2a_41b1_9022_536bb9cf93b1
0x180035842  mov     rcx, [rbp+57h+string]
0x180035846  call    cs:__imp_RoGetActivationFactory
0x18003584c  test    eax, eax
0x18003584e  js      short loc_1800358AF
0x180035850  mov     rbx, [rbp+57h+var_60]
0x180035854  mov     rax, [rbx]
0x180035857  mov     rdi, [rax+30h]
0x18003585b  mov     rdx, [rbp+57h+var_70]
0x18003585f  mov     [rbp+57h+var_70], r14
0x180035863  test    rdx, rdx
0x180035866  jnz     loc_180035E48
0x18003586c  lea     rdx, [rbp+57h+var_70]
0x180035870  mov     rcx, rbx
0x180035873  mov     rax, rdi
0x180035876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003587b  test    eax, eax
0x18003587d  js      short loc_1800358AF
0x18003587f  mov     rbx, [rbp+57h+var_70]
0x180035883  test    rbx, rbx
0x180035886  jz      short loc_1800358AF
0x180035888  mov     rax, [rbx]
0x18003588b  mov     rdi, [rax+48h]
0x18003588f  mov     rdx, [rbp+57h+var_78]
0x180035893  mov     [rbp+57h+var_78], r14
0x180035897  test    rdx, rdx
0x18003589a  jnz     loc_180035E5C
0x1800358a0  lea     rdx, [rbp+57h+var_78]
0x1800358a4  mov     rcx, rbx
0x1800358a7  mov     rax, rdi
0x1800358aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358af  mov     [rbp+57h+var_90], r14b
0x1800358b3  mov     rcx, [rbp+57h+var_78]
0x1800358b7  test    rcx, rcx
0x1800358ba  jz      short loc_1800358D6
0x1800358bc  mov     rax, [rcx]
0x1800358bf  lea     rdx, [rbp+57h+var_90]
0x1800358c3  mov     rax, [rax+30h]
0x1800358c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358cc  cmp     [rbp+57h+var_90], r14b
0x1800358d0  jnz     short loc_18003593D
0x1800358d2  mov     rcx, [rbp+57h+var_78]
0x1800358d6  test    rcx, rcx
0x1800358d9  jz      short loc_1800358E8
0x1800358db  mov     rax, [rcx]
0x1800358de  mov     rax, [rax+10h]
0x1800358e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358e7  nop
0x1800358e8  mov     rbx, [rbp+57h+var_70]
0x1800358ec  test    rbx, rbx
0x1800358ef  jz      short loc_180035901
0x1800358f1  mov     rax, [rbx]
0x1800358f4  mov     rcx, rbx
0x1800358f7  mov     rax, [rax+10h]
0x1800358fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035900  nop
0x180035901  mov     rcx, [rbp+57h+var_60]
0x180035905  test    rcx, rcx
0x180035908  jz      short loc_180035917
0x18003590a  mov     rax, [rcx]
0x18003590d  mov     rax, [rax+10h]
0x180035911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035916  nop
0x180035917  xor     eax, eax
0x180035919  mov     rcx, [rbp+57h+var_18]
0x18003591d  xor     rcx, rsp; StackCookie
0x180035920  call    __security_check_cookie
0x180035925  lea     r11, [rsp+0C0h+var_10]
0x18003592d  mov     rbx, [r11+28h]
0x180035931  mov     rsi, [r11+30h]
0x180035935  mov     rsp, r11
0x180035938  pop     r14
0x18003593a  pop     rdi
0x18003593b  pop     rbp
0x18003593c  retn
0x18003593d  mov     [rbp+57h+var_48], r14
0x180035941  lea     r9, [rbp+57h+string]; string
0x180035945  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180035949  mov     edx, 2Dh ; '-'; length
0x18003594e  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_Core_CoreApplication@@3QBGB; "Windows.ApplicationModel.Core.CoreAppli"...
0x180035955  call    cs:__imp_WindowsCreateStringReference
0x18003595b  test    eax, eax
0x18003595d  js      loc_180035E70
0x180035963  lea     r8, [rbp+57h+var_48]
0x180035967  lea     rdx, _GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1
0x18003596e  mov     rcx, [rbp+57h+string]
0x180035972  call    cs:__imp_RoGetActivationFactory
0x180035978  mov     ebx, eax
0x18003597a  test    eax, eax
0x18003597c  js      loc_180035F2A
0x180035982  mov     rcx, [rbp+57h+var_48]
0x180035986  test    rcx, rcx
0x180035989  jz      loc_180035BD3
0x18003598f  mov     [rbp+57h+var_80], r14
0x180035993  mov     rax, [rcx]
0x180035996  lea     r8, [rbp+57h+var_80]
0x18003599a  lea     rdx, _GUID_17b0e613_942a_422d_904c_f90dc71a7dae
0x1800359a1  mov     rax, [rax]
0x1800359a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800359a9  mov     ebx, eax
0x1800359ab  test    eax, eax
0x1800359ad  js      loc_180035E8A
0x1800359b3  mov     [rbp+57h+var_88], r14
0x1800359b7  mov     rdi, [rbp+57h+var_80]
0x1800359bb  mov     rax, [rdi]
0x1800359be  mov     rbx, [rax+48h]
0x1800359c2  mov     [rbp+57h+var_88], r14
0x1800359c6  call    cs:__imp_GetCurrentThreadId
0x1800359cc  lea     r8, [rbp+57h+var_88]
0x1800359d0  mov     edx, eax
0x1800359d2  mov     rcx, rdi
0x1800359d5  mov     rax, rbx
0x1800359d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800359dd  mov     ebx, eax
0x1800359df  test    eax, eax
0x1800359e1  js      loc_180035F16
0x1800359e7  mov     rcx, [rbp+57h+var_88]
0x1800359eb  test    rcx, rcx
0x1800359ee  jz      loc_180035EA4
0x1800359f4  mov     [rbp+57h+var_40], r14d
0x1800359f8  mov     [rbp+57h+var_68], r14
0x1800359fc  mov     rax, [rcx]
0x1800359ff  lea     r8, [rbp+57h+var_68]
0x180035a03  lea     rdx, _GUID_9ebd287a_8a6b_4191_915f_01b8da7dc177
0x180035a0a  mov     rax, [rax]
0x180035a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035a12  mov     ebx, eax
0x180035a14  test    eax, eax
0x180035a16  js      loc_180035D76
0x180035a1c  mov     rcx, [rbp+57h+var_68]
0x180035a20  mov     rax, [rcx]
0x180035a23  lea     rdx, [rbp+57h+var_40]
0x180035a27  mov     rax, [rax+48h]
0x180035a2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035a30  mov     ebx, eax
0x180035a32  test    eax, eax
0x180035a34  js      loc_180035EBE
0x180035a3a  mov     [rbp+57h+var_50], r14
0x180035a3e  lea     rax, [rbp+57h+var_50]
0x180035a42  mov     qword ptr [rsp+0C0h+ppv], rax; int
0x180035a47  lea     r9, _GUID_0f4accb1_d8f9_4011_ba37_2557925a78cf; riid
0x180035a4e  xor     edx, edx; pUnkOuter
0x180035a50  lea     r8d, [rdx+4]; dwClsContext
0x180035a54  lea     rcx, CLSID_ShellServiceHostBrokerProvider; rclsid
0x180035a5b  call    cs:__imp_CoCreateInstance
0x180035a61  mov     ebx, eax
0x180035a63  test    eax, eax
0x180035a65  js      loc_180035CA8
0x180035a6b  mov     [rbp+57h+var_58], r14
0x180035a6f  mov     rcx, [rbp+57h+var_50]
0x180035a73  mov     rax, [rcx]
0x180035a76  mov     [rbp+57h+var_58], r14
0x180035a7a  lea     r9, [rbp+57h+var_58]
0x180035a7e  lea     r8, _GUID_23030752_8e7c_4225_8c88_28211f93ddf7
0x180035a85  lea     rdx, _GUID_1f79f7de_20bf_4591_930a_d490b78fb09f
0x180035a8c  mov     rax, [rax+18h]
0x180035a90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035a95  mov     ebx, eax
0x180035a97  test    eax, eax
0x180035a99  js      loc_180035ED8
0x180035a9f  mov     [rbp+57h+var_3C], r14d
0x180035aa3  mov     rcx, [rbp+57h+var_58]
0x180035aa7  mov     rax, [rcx]
0x180035aaa  lea     r8, [rbp+57h+var_3C]
0x180035aae  mov     edx, [rbp+57h+var_40]
0x180035ab1  mov     rax, [rax+38h]
0x180035ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035aba  mov     ebx, eax
0x180035abc  test    eax, eax
0x180035abe  js      loc_180035EDF
0x180035ac4  mov     eax, [rbp+57h+var_3C]
0x180035ac7  test    eax, eax
0x180035ac9  jz      short loc_180035AD1
0x180035acb  mov     [rsi+0D8h], eax
0x180035ad1  lea     rcx, [rsi+0B8h]; void **
0x180035ad8  mov     edx, [rsi+0D8h]; unsigned int
0x180035ade  call    ?AudioServerSetWindowId@CAudioSessionControl@@CAJPEAPEAXI@Z; CAudioSessionControl::AudioServerSetWindowId(void * *,uint)
0x180035ae3  mov     ebx, eax
0x180035ae5  test    eax, eax
0x180035ae7  jns     loc_180035C1F
0x180035aed  mov     rcx, [rbp+5Fh]; this
0x180035af1  mov     r9d, eax; char *
0x180035af4  lea     r8, aAvcoreAudiocor_29; "avcore\\audiocore\\client\\audioclient"...
0x180035afb  mov     edx, 1B6h; void *
0x180035b00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035b05  nop
0x180035b06  mov     rcx, [rbp+57h+var_58]
0x180035b0a  test    rcx, rcx
0x180035b0d  jz      short loc_180035B1C
0x180035b0f  mov     rax, [rcx]
0x180035b12  mov     rax, [rax+10h]
0x180035b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b1b  nop
0x180035b1c  mov     rcx, [rbp+57h+var_50]
0x180035b20  test    rcx, rcx
0x180035b23  jz      short loc_180035B32
0x180035b25  mov     rax, [rcx]
0x180035b28  mov     rax, [rax+10h]
0x180035b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b31  nop
0x180035b32  mov     rcx, [rbp+57h+var_68]
0x180035b36  test    rcx, rcx
0x180035b39  jz      short loc_180035B48
0x180035b3b  mov     rax, [rcx]
0x180035b3e  mov     rax, [rax+10h]
0x180035b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b47  nop
0x180035b48  mov     rcx, [rbp+57h+var_88]
0x180035b4c  test    rcx, rcx
0x180035b4f  jz      short loc_180035B5E
0x180035b51  mov     rax, [rcx]
0x180035b54  mov     rax, [rax+10h]
0x180035b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b5d  nop
0x180035b5e  mov     rcx, [rbp+57h+var_80]
0x180035b62  test    rcx, rcx
0x180035b65  jz      short loc_180035B74
0x180035b67  mov     rax, [rcx]
0x180035b6a  mov     rax, [rax+10h]
0x180035b6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b73  nop
0x180035b74  mov     rcx, [rbp+57h+var_48]
0x180035b78  test    rcx, rcx
0x180035b7b  jz      short loc_180035B8A
0x180035b7d  mov     rax, [rcx]
0x180035b80  mov     rax, [rax+10h]
0x180035b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b89  nop
0x180035b8a  mov     rcx, [rbp+57h+var_78]
0x180035b8e  test    rcx, rcx
0x180035b91  jz      short loc_180035BA0
0x180035b93  mov     rax, [rcx]
0x180035b96  mov     rax, [rax+10h]
0x180035b9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b9f  nop
0x180035ba0  mov     rcx, [rbp+57h+var_70]
0x180035ba4  test    rcx, rcx
0x180035ba7  jz      short loc_180035BB6
0x180035ba9  mov     rax, [rcx]
0x180035bac  mov     rax, [rax+10h]
0x180035bb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035bb5  nop
0x180035bb6  mov     rcx, [rbp+57h+var_60]
0x180035bba  test    rcx, rcx
0x180035bbd  jz      short loc_180035BCC
0x180035bbf  mov     rax, [rcx]
0x180035bc2  mov     rax, [rax+10h]
0x180035bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035bcb  nop
0x180035bcc  mov     eax, ebx
0x180035bce  jmp     loc_180035919
0x180035bd3  mov     rcx, [rbp+57h+var_78]
0x180035bd7  test    rcx, rcx
0x180035bda  jz      short loc_180035BE9
0x180035bdc  mov     rax, [rcx]
0x180035bdf  mov     rax, [rax+10h]
0x180035be3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035be8  nop
0x180035be9  mov     rcx, [rbp+57h+var_70]
0x180035bed  test    rcx, rcx
0x180035bf0  jz      short loc_180035BFF
0x180035bf2  mov     rax, [rcx]
0x180035bf5  mov     rax, [rax+10h]
0x180035bf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035bfe  nop
0x180035bff  mov     rcx, [rbp+57h+var_60]
0x180035c03  test    rcx, rcx
0x180035c06  jz      short loc_180035C15
0x180035c08  mov     rax, [rcx]
0x180035c0b  mov     rax, [rax+10h]
0x180035c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035c14  nop
0x180035c15  mov     eax, 80070490h
0x180035c1a  jmp     loc_180035919
0x180035c1f  mov     rcx, [rbp+57h+var_58]
0x180035c23  test    rcx, rcx
0x180035c26  jz      short loc_180035C35
  ... truncated ...
```
