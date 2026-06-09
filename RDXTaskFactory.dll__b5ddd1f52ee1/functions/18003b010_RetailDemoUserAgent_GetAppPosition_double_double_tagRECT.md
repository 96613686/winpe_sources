# RetailDemoUserAgent::GetAppPosition(double,double,tagRECT *)

- ea: `0x18003b010`
- end: `0x18003b392`
- name: `?GetAppPosition@RetailDemoUserAgent@@UEAAJNNPEAUtagRECT@@@Z`
- size: `898`
- prototype: `__int64 __fastcall(RetailDemoUserAgent *__hidden this, double, double, struct tagRECT *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003390`
- `0x180003de8`
- `0x180008bbc`
- `0x18000aa5c`
- `0x18001094c`
- `0x180014d04`
- `0x180036a1c`
- `0x18003b010`
- `0x180050010`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18003b0b4`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18003b0b4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003b113`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003b113`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x18003b087`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x18003b098`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x18003b27b`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x18003b290`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x18003b087`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x18003b098`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x18003b27b`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x18003b290`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x18003b04f`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x18003b04f`

## string_xrefs

- `0x18003b06d`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18003b0c2`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18003b124`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18003b176`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18003b1d4`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RetailDemoUserAgent::GetAppPosition(
        RetailDemoUserAgent *this,
        double a2,
        double a3,
        struct tagRECT *a4)
{
  HDC DC; // rax
  const char *v6; // r9
  HDC v7; // rsi
  unsigned int DeviceCaps; // r12d
  unsigned int v9; // r15d
  __int64 v10; // rdx
  __int64 v11; // r8
  const char *v12; // r9
  unsigned int LastError; // ebx
  HRESULT v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  LPVOID v18; // rdi
  __int64 (__fastcall *v19)(LPVOID, GUID *, GUID *, __int64 *); // rbx
  int v20; // eax
  int v21; // eax
  int v22; // ecx
  int v23; // r9d
  int v24; // r10d
  int v25; // r11d
  int v26; // ebx
  float v27; // xmm0_4
  __int64 v28; // rdx
  double v29; // xmm0_8
  float v30; // xmm0_4
  float v31; // xmm6_4
  int v32; // eax
  float v33; // xmm0_4
  float v34; // xmm1_4
  __int64 v35; // r8
  __int64 v36; // rdx
  __int64 v37; // r8
  int ppv; // [rsp+28h] [rbp-49h]
  int v39; // [rsp+38h] [rbp-39h] BYREF
  int v40; // [rsp+3Ch] [rbp-35h] BYREF
  int v41; // [rsp+40h] [rbp-31h] BYREF
  int v42; // [rsp+44h] [rbp-2Dh] BYREF
  __int64 v43; // [rsp+48h] [rbp-29h] BYREF
  LPVOID v44; // [rsp+50h] [rbp-21h] BYREF
  _QWORD v45[2]; // [rsp+58h] [rbp-19h] BYREF
  __int128 pvParam; // [rsp+68h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]

  DC = GetDC(0);
  v7 = DC;
  v45[0] = DC;
  v45[1] = 0;
  if ( !DC )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x77A,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      v6);
  DeviceCaps = GetDeviceCaps(DC, 8);
  v9 = GetDeviceCaps(v7, 10);
  pvParam = 0;
  if ( SystemParametersInfoW(0x30u, 0, &pvParam, 0) )
  {
    v44 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44, v10, v11);
    v15 = CoCreateInstance(
            &GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239,
            0,
            4u,
            &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
            &v44);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x782,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
        (const char *)(unsigned int)v15,
        ppv);
    v43 = 0;
    v18 = v44;
    v19 = *(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, __int64 *))(*(_QWORD *)v44 + 24LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43, v16, v17);
    v20 = v19(v18, &GUID_c83ec4e0_068f_4a90_a1c7_20841a08f99f, &GUID_c83ec4e0_068f_4a90_a1c7_20841a08f99f, &v43);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x784,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
        (const char *)(unsigned int)v20,
        ppv);
    v42 = 0;
    v40 = 0;
    v41 = 0;
    v39 = 0;
    v21 = (*(__int64 (__fastcall **)(__int64, int *, int *, int *))(*(_QWORD *)v43 + 88LL))(v43, &v42, &v40, &v41);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x788,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
        (const char *)(unsigned int)v21,
        (int)&v39);
    v22 = DWORD2(pvParam);
    v23 = pvParam;
    v24 = v41;
    v25 = v40;
    v26 = DWORD2(pvParam) - pvParam - v41 - v40;
    if ( a2 >= 0.0 )
    {
      v29 = (double)v26 * a2;
      v28 = (unsigned int)(int)v29;
      v39 = (int)v29;
    }
    else
    {
      v27 = (float)v26 * 0.025;
      v28 = (unsigned int)(int)v27;
      v39 = (int)v27;
    }
    if ( a3 >= 0.0 )
    {
      v35 = (unsigned int)(int)((double)v26 * a3);
    }
    else
    {
      if ( v42 )
      {
        v30 = (float)v26 * 0.07;
      }
      else
      {
        v31 = (float)GetDeviceCaps(v7, 4);
        v32 = GetDeviceCaps(v7, 6);
        v33 = o_sqrtf_0((float)((float)v32 * (float)v32) + (float)(v31 * v31));
        if ( DeviceCaps <= 0x780 || v9 <= 0x438 || (int)(float)(v33 / 25.4) < 15 )
          v34 = FLOAT_0_026000001;
        else
          v34 = FLOAT_0_082000002;
        v30 = (float)v26 * v34;
        v22 = DWORD2(pvParam);
        v23 = pvParam;
        v25 = v40;
        v24 = v41;
        v28 = (unsigned int)v39;
      }
      v35 = (unsigned int)(int)v30;
    }
    a4->left = v35 + v25;
    a4->top = v28;
    a4->right = v22 - v35 - v23 - v24;
    a4->bottom = HIDWORD(pvParam) - DWORD1(pvParam) - v28;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43, v28, v35);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44, v36, v37);
    __1__unique_storage_U__resource_policy_PEAUHDC____P6AXUwindow_dc_wil____E_1_close_23_SAX0_ZU__integral_constant__K_0A__wistd__U23_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(v45);
    return 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x77F,
                  (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
                  v12);
    __1__unique_storage_U__resource_policy_PEAUHDC____P6AXUwindow_dc_wil____E_1_close_23_SAX0_ZU__integral_constant__K_0A__wistd__U23_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(v45);
    return LastError;
  }
}

```

## disassembly

```asm
0x18003b010  mov     rax, rsp
0x18003b013  mov     [rax+8], rbx
0x18003b017  mov     [rax+10h], rsi
0x18003b01b  push    rbp
0x18003b01c  push    rdi
0x18003b01d  push    r12
0x18003b01f  push    r14
0x18003b021  push    r15
0x18003b023  lea     rbp, [rax-5Fh]
0x18003b027  sub     rsp, 0A0h
0x18003b02e  movaps  xmmword ptr [rax-38h], xmm6
0x18003b032  movaps  xmmword ptr [rax-48h], xmm7
0x18003b036  mov     rax, cs:__security_cookie
0x18003b03d  xor     rax, rsp
0x18003b040  mov     [rbp+57h+var_50], rax
0x18003b044  mov     r14, r9
0x18003b047  movaps  xmm7, xmm2
0x18003b04a  movaps  xmm6, xmm1
0x18003b04d  xor     ecx, ecx; hWnd
0x18003b04f  call    cs:__imp_GetDC
0x18003b055  mov     rsi, rax
0x18003b058  mov     [rbp+57h+var_70], rax
0x18003b05c  mov     [rbp+57h+var_68], 0
0x18003b064  mov     rcx, [rbp+5Fh]; this
0x18003b068  test    rax, rax
0x18003b06b  jnz     short loc_18003B07F
0x18003b06d  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003b074  mov     edx, 77Ah; void *
0x18003b079  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18003b07f  mov     edx, 8; index
0x18003b084  mov     rcx, rsi; hdc
0x18003b087  call    cs:__imp_GetDeviceCaps
0x18003b08d  mov     r12d, eax
0x18003b090  mov     edx, 0Ah; index
0x18003b095  mov     rcx, rsi; hdc
0x18003b098  call    cs:__imp_GetDeviceCaps
0x18003b09e  mov     r15d, eax
0x18003b0a1  xorps   xmm0, xmm0
0x18003b0a4  movups  [rbp+57h+pvParam], xmm0
0x18003b0a8  xor     r9d, r9d; fWinIni
0x18003b0ab  lea     r8, [rbp+57h+pvParam]; pvParam
0x18003b0af  xor     edx, edx; uiParam
0x18003b0b1  lea     ecx, [rdx+30h]; uiAction
0x18003b0b4  call    cs:__imp_SystemParametersInfoW
0x18003b0ba  test    eax, eax
0x18003b0bc  jnz     short loc_18003B0E5
0x18003b0be  mov     rcx, [rbp+5Fh]; this
0x18003b0c2  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003b0c9  mov     edx, 77Fh; void *
0x18003b0ce  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003b0d3  mov     ebx, eax
0x18003b0d5  lea     rcx, [rbp+57h+var_70]
0x18003b0d9  call    ??1?$unique_storage@U?$resource_policy@PEAUHDC__@@P6AXUwindow_dc@wil@@@_E$1?close@23@SAX0@ZU?$integral_constant@_K$0A@@wistd@@U23@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003b0de  mov     eax, ebx
0x18003b0e0  jmp     loc_18003B360
0x18003b0e5  mov     [rbp+57h+var_78], 0
0x18003b0ed  lea     rcx, [rbp+57h+var_78]
0x18003b0f1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003b0f6  lea     rax, [rbp+57h+var_78]
0x18003b0fa  mov     qword ptr [rsp+0C0h+ppv], rax; int
0x18003b0ff  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x18003b106  xor     edx, edx; pUnkOuter
0x18003b108  lea     r8d, [rdx+4]; dwClsContext
0x18003b10c  lea     rcx, _GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239; rclsid
0x18003b113  call    cs:__imp_CoCreateInstance
0x18003b119  mov     rcx, [rbp+5Fh]; this
0x18003b11d  test    eax, eax
0x18003b11f  jns     short loc_18003B136
0x18003b121  mov     r9d, eax; char *
0x18003b124  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003b12b  mov     edx, 782h; void *
0x18003b130  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003b136  mov     [rbp+57h+var_80], 0
0x18003b13e  mov     rdi, [rbp+57h+var_78]
0x18003b142  mov     rax, [rdi]
0x18003b145  mov     rbx, [rax+18h]
0x18003b149  lea     rcx, [rbp+57h+var_80]
0x18003b14d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003b152  lea     r9, [rbp+57h+var_80]
0x18003b156  lea     rdx, _GUID_c83ec4e0_068f_4a90_a1c7_20841a08f99f
0x18003b15d  mov     r8, rdx
0x18003b160  mov     rcx, rdi
0x18003b163  mov     rax, rbx
0x18003b166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b16b  mov     rcx, [rbp+5Fh]; this
0x18003b16f  test    eax, eax
0x18003b171  jns     short loc_18003B188
0x18003b173  mov     r9d, eax; char *
0x18003b176  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003b17d  mov     edx, 784h; void *
0x18003b182  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003b188  mov     [rbp+57h+var_84], 0
0x18003b18f  mov     [rbp+57h+var_8C], 0
0x18003b196  mov     [rbp+57h+var_88], 0
0x18003b19d  mov     [rbp+57h+var_90], 0
0x18003b1a4  mov     rcx, [rbp+57h+var_80]
0x18003b1a8  mov     rax, [rcx]
0x18003b1ab  lea     rdx, [rbp+57h+var_90]
0x18003b1af  mov     qword ptr [rsp+0C0h+ppv], rdx; int
0x18003b1b4  lea     r9, [rbp+57h+var_88]
0x18003b1b8  lea     r8, [rbp+57h+var_8C]
0x18003b1bc  lea     rdx, [rbp+57h+var_84]
0x18003b1c0  mov     rax, [rax+58h]
0x18003b1c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b1c9  mov     rcx, [rbp+5Fh]; this
0x18003b1cd  test    eax, eax
0x18003b1cf  jns     short loc_18003B1E6
0x18003b1d1  mov     r9d, eax; char *
0x18003b1d4  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003b1db  mov     edx, 788h; void *
0x18003b1e0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003b1e6  mov     ecx, dword ptr [rbp+57h+pvParam+8]
0x18003b1e9  mov     ebx, ecx
0x18003b1eb  mov     r9d, dword ptr [rbp+57h+pvParam]
0x18003b1ef  sub     ebx, r9d
0x18003b1f2  mov     r10d, [rbp+57h+var_88]
0x18003b1f6  sub     ebx, r10d
0x18003b1f9  mov     r11d, [rbp+57h+var_8C]
0x18003b1fd  sub     ebx, r11d
0x18003b200  xorps   xmm1, xmm1
0x18003b203  mov     r8d, [rbp+57h+var_84]
0x18003b207  comisd  xmm1, xmm6
0x18003b20b  jbe     short loc_18003B235
0x18003b20d  test    r8d, r8d
0x18003b210  jz      short loc_18003B219
0x18003b212  mov     edx, [rbp+57h+var_90]
0x18003b215  test    edx, edx
0x18003b217  jnz     short loc_18003B24D
0x18003b219  mov     eax, ebx
0x18003b21b  xorps   xmm0, xmm0
0x18003b21e  cvtsi2ss xmm0, rax
0x18003b223  mulss   xmm0, cs:__real@3ccccccd
0x18003b22b  cvttss2si rdx, xmm0
0x18003b230  mov     [rbp+57h+var_90], edx
0x18003b233  jmp     short loc_18003B24D
0x18003b235  mov     eax, ebx
0x18003b237  xorps   xmm0, xmm0
0x18003b23a  cvtsi2sd xmm0, rax
0x18003b23f  mulsd   xmm0, xmm6
0x18003b243  cvttsd2si rax, xmm0
0x18003b248  mov     edx, eax
0x18003b24a  mov     [rbp+57h+var_90], eax
0x18003b24d  comisd  xmm1, xmm7
0x18003b251  jbe     loc_18003B30A
0x18003b257  test    r8d, r8d
0x18003b25a  jz      short loc_18003B273
0x18003b25c  mov     eax, ebx
0x18003b25e  xorps   xmm0, xmm0
0x18003b261  cvtsi2ss xmm0, rax
0x18003b266  mulss   xmm0, cs:__real@3d8f5c29
0x18003b26e  jmp     loc_18003B303
0x18003b273  mov     edx, 4; index
0x18003b278  mov     rcx, rsi; hdc
0x18003b27b  call    cs:__imp_GetDeviceCaps
0x18003b281  movd    xmm6, eax
0x18003b285  cvtdq2ps xmm6, xmm6
0x18003b288  mov     edx, 6; index
0x18003b28d  mov     rcx, rsi; hdc
0x18003b290  call    cs:__imp_GetDeviceCaps
0x18003b296  movd    xmm0, eax
0x18003b29a  cvtdq2ps xmm0, xmm0
0x18003b29d  mulss   xmm0, xmm0
0x18003b2a1  mulss   xmm6, xmm6
0x18003b2a5  addss   xmm0, xmm6; X
0x18003b2a9  call    _o_sqrtf_0
0x18003b2ae  cmp     r12d, 780h
0x18003b2b5  jbe     short loc_18003B2DB
0x18003b2b7  cmp     r15d, 438h
0x18003b2be  jbe     short loc_18003B2DB
0x18003b2c0  divss   xmm0, cs:__real@41cb3333
0x18003b2c8  cvttss2si eax, xmm0
0x18003b2cc  cmp     eax, 0Fh
0x18003b2cf  jl      short loc_18003B2DB
0x18003b2d1  movss   xmm1, cs:__real@3da7ef9e
0x18003b2d9  jmp     short loc_18003B2E3
0x18003b2db  movss   xmm1, cs:__real@3cd4fdf4
0x18003b2e3  mov     eax, ebx
0x18003b2e5  xorps   xmm0, xmm0
0x18003b2e8  cvtsi2ss xmm0, rax
0x18003b2ed  mulss   xmm0, xmm1
0x18003b2f1  mov     ecx, dword ptr [rbp+57h+pvParam+8]
0x18003b2f4  mov     r9d, dword ptr [rbp+57h+pvParam]
0x18003b2f8  mov     r11d, [rbp+57h+var_8C]
0x18003b2fc  mov     r10d, [rbp+57h+var_88]
0x18003b300  mov     edx, [rbp+57h+var_90]
0x18003b303  cvttss2si r8, xmm0
0x18003b308  jmp     short loc_18003B31D
0x18003b30a  mov     eax, ebx
0x18003b30c  xorps   xmm0, xmm0
0x18003b30f  cvtsi2sd xmm0, rax
0x18003b314  mulsd   xmm0, xmm7
0x18003b318  cvttsd2si r8, xmm0
0x18003b31d  lea     eax, [r8+r11]
0x18003b321  mov     [r14], eax
0x18003b324  mov     [r14+4], edx
0x18003b328  sub     ecx, r8d
0x18003b32b  sub     ecx, r9d
0x18003b32e  sub     ecx, r10d
0x18003b331  mov     [r14+8], ecx
0x18003b335  mov     eax, dword ptr [rbp+57h+pvParam+0Ch]
0x18003b338  sub     eax, dword ptr [rbp+57h+pvParam+4]
0x18003b33b  sub     eax, edx
0x18003b33d  mov     [r14+0Ch], eax
0x18003b341  lea     rcx, [rbp+57h+var_80]
0x18003b345  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003b34a  nop
0x18003b34b  lea     rcx, [rbp+57h+var_78]
0x18003b34f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003b354  nop
0x18003b355  lea     rcx, [rbp+57h+var_70]
0x18003b359  call    ??1?$unique_storage@U?$resource_policy@PEAUHDC__@@P6AXUwindow_dc@wil@@@_E$1?close@23@SAX0@ZU?$integral_constant@_K$0A@@wistd@@U23@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003b35e  xor     eax, eax
0x18003b360  mov     rcx, [rbp+57h+var_50]
0x18003b364  xor     rcx, rsp; StackCookie
0x18003b367  call    __security_check_cookie
0x18003b36c  lea     r11, [rsp+0C0h+var_20]
0x18003b374  mov     rbx, [r11+30h]
0x18003b378  mov     rsi, [r11+38h]
0x18003b37c  movaps  xmm6, xmmword ptr [r11-10h]
0x18003b381  movaps  xmm7, xmmword ptr [r11-20h]
0x18003b386  mov     rsp, r11
0x18003b389  pop     r15
0x18003b38b  pop     r14
0x18003b38d  pop     r12
0x18003b38f  pop     rdi
0x18003b390  pop     rbp
0x18003b391  retn
```
