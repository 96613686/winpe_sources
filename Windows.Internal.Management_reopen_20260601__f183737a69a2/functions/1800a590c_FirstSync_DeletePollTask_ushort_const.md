# FirstSync::DeletePollTask(ushort const *)

- ea: `0x1800a590c`
- end: `0x1800a5c4a`
- name: `?DeletePollTask@FirstSync@@YAJPEBG@Z`
- size: `830`
- prototype: `__int64 __fastcall(FirstSync *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800a7230`
- `0x1800a73f8`

## callees

- `0x180009be4`
- `0x18000a5c4`
- `0x18002335c`
- `0x18006a99c`
- `0x1800a590c`
- `0x1800a67fc`
- `0x1800bb010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a59bf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a59bf`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800a5c0b`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800a5c0b`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800a5974`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800a5974`
- `OLEAUT32!__imp_VariantInit` at `0x1800a5a04`
- `OLEAUT32!__imp_VariantInit` at `0x1800a5a22`
- `OLEAUT32!__imp_VariantInit` at `0x1800a5a41`
- `OLEAUT32!__imp_VariantInit` at `0x1800a5a5e`
- `OLEAUT32!__imp_VariantInit` at `0x1800a5a04`
- `OLEAUT32!__imp_VariantInit` at `0x1800a5a22`
- `OLEAUT32!__imp_VariantInit` at `0x1800a5a41`
- `OLEAUT32!__imp_VariantInit` at `0x1800a5a5e`
- `OLEAUT32!__imp_VariantClear` at `0x1800a5ac5`
- `OLEAUT32!__imp_VariantClear` at `0x1800a5ad7`
- `OLEAUT32!__imp_VariantClear` at `0x1800a5ae9`
- `OLEAUT32!__imp_VariantClear` at `0x1800a5afb`
- `OLEAUT32!__imp_VariantClear` at `0x1800a5ac5`
- `OLEAUT32!__imp_VariantClear` at `0x1800a5ad7`
- `OLEAUT32!__imp_VariantClear` at `0x1800a5ae9`
- `OLEAUT32!__imp_VariantClear` at `0x1800a5afb`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall FirstSync::DeletePollTask(FirstSync *this, const unsigned __int16 *a2)
{
  int v4; // ebx
  HRESULT TaskFolder; // edi
  __int64 v6; // rdx
  LPVOID v7; // rsi
  __int64 (__fastcall *v8)(LPVOID, VARIANTARG *, __int128 *, __int128 *); // rdi
  __int128 v9; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v11; // xmm8
  IRecordInfo *v12; // xmm9_8
  __int128 v13; // xmm6
  IRecordInfo *v14; // xmm7_8
  int ppv; // [rsp+20h] [rbp-E0h]
  int *ppva; // [rsp+20h] [rbp-E0h]
  VARIANTARG v17; // [rsp+30h] [rbp-D0h] BYREF
  VARIANTARG v18; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG v19; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-88h] BYREF
  int v21[4]; // [rsp+90h] [rbp-70h] BYREF
  IRecordInfo *v22; // [rsp+A0h] [rbp-60h]
  __int128 v23; // [rsp+B0h] [rbp-50h] BYREF
  IRecordInfo *v24; // [rsp+C0h] [rbp-40h]
  __int128 v25; // [rsp+D0h] [rbp-30h] BYREF
  IRecordInfo *v26; // [rsp+E0h] [rbp-20h]
  VARIANTARG v27; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]
  LPVOID v29; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v30; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v31; // [rsp+1B8h] [rbp+B8h] BYREF

  if ( !this )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x319,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
      (const char *)0x80070057LL,
      ppv);
    return 2147942487LL;
  }
  v4 = RoInitialize(1);
  v29 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  TaskFolder = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &v29);
  if ( TaskFolder >= 0 )
  {
    v7 = v29;
    v8 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)v29 + 80LL);
    VariantInit(&pvarg);
    v9 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    VariantInit(&v19);
    v11 = *(_OWORD *)&v19.vt;
    v12 = v19.pRecInfo;
    VariantInit(&v18);
    v13 = *(_OWORD *)&v18.vt;
    v14 = v18.pRecInfo;
    VariantInit(&v17);
    *(_OWORD *)v21 = v9;
    v22 = pRecInfo;
    v23 = v11;
    v24 = v12;
    v25 = v13;
    v26 = v14;
    v27 = v17;
    ppva = v21;
    TaskFolder = v8(v7, &v27, &v25, &v23);
    VariantClear(&v17);
    VariantClear(&v18);
    VariantClear(&v19);
    VariantClear(&pvarg);
    if ( TaskFolder < 0 )
    {
      v6 = 800;
      goto LABEL_5;
    }
    v30 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
    TaskFolder = anonymous_namespace_::GetTaskFolder(v29, this, 0, &v30);
    if ( TaskFolder >= 0 )
    {
      wil::make_bstr_nothrow(&v31, L"Sync Status Poll");
      if ( !v31 )
      {
        TaskFolder = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x327,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
          (const char *)0x8007000ELL,
          (int)v21);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v31);
LABEL_16:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
        goto LABEL_17;
      }
      TaskFolder = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v30 + 120LL))(v30, v31, 0);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v31);
    }
    if ( (unsigned int)(TaskFolder + 2147024894) > 1 )
    {
      if ( TaskFolder < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x32D,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
          (const char *)(unsigned int)TaskFolder,
          (int)v21);
    }
    else
    {
      TaskFolder = 0;
    }
    goto LABEL_16;
  }
  v6 = 798;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
    (const char *)(unsigned int)TaskFolder,
    (int)ppva);
LABEL_17:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  if ( v4 >= 0 )
    RoUninitialize();
  return (unsigned int)TaskFolder;
}

```

## disassembly

```asm
0x1800a590c  mov     rax, rsp
0x1800a590f  push    rbp
0x1800a5910  push    rbx
0x1800a5911  push    rsi
0x1800a5912  push    rdi
0x1800a5913  push    r14
0x1800a5915  lea     rbp, [rsp-70h]
0x1800a591a  sub     rsp, 170h
0x1800a5921  movaps  xmmword ptr [rax-38h], xmm6
0x1800a5925  movaps  xmmword ptr [rax-48h], xmm7
0x1800a5929  movaps  xmmword ptr [rax-58h], xmm8
0x1800a592e  movaps  xmmword ptr [rax-68h], xmm9
0x1800a5933  movaps  xmmword ptr [rax-78h], xmm10
0x1800a5938  movaps  xmmword ptr [rax-88h], xmm11
0x1800a5940  mov     r14, rcx
0x1800a5943  test    rcx, rcx
0x1800a5946  jnz     short loc_1800A596F
0x1800a5948  mov     rcx, [rbp+98h]; this
0x1800a594f  mov     ebx, 80070057h
0x1800a5954  mov     r9d, ebx; char *
0x1800a5957  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a595e  mov     edx, 319h; void *
0x1800a5963  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5968  mov     eax, ebx
0x1800a596a  jmp     loc_1800A5C19
0x1800a596f  mov     ecx, 1
0x1800a5974  call    cs:__imp_RoInitialize
0x1800a597b  nop     dword ptr [rax+rax+00h]
0x1800a5980  mov     ebx, eax
0x1800a5982  mov     [rbp+90h+arg_0], eax
0x1800a5988  mov     [rbp+90h+arg_8], 0
0x1800a5993  lea     rcx, [rbp+90h+arg_8]
0x1800a599a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a599f  lea     rax, [rbp+90h+arg_8]
0x1800a59a6  mov     [rsp+190h+ppv], rax; int
0x1800a59ab  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1800a59b2  xor     edx, edx; pUnkOuter
0x1800a59b4  lea     r8d, [rdx+1]; dwClsContext
0x1800a59b8  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800a59bf  call    cs:__imp_CoCreateInstance
0x1800a59c6  nop     dword ptr [rax+rax+00h]
0x1800a59cb  mov     edi, eax
0x1800a59cd  test    eax, eax
0x1800a59cf  jns     short loc_1800A59F1
0x1800a59d1  mov     edx, 31Eh; void *
0x1800a59d6  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a59dd  mov     r9d, edi; char *
0x1800a59e0  mov     rcx, [rbp+98h]; this
0x1800a59e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a59ec  jmp     loc_1800A5BFA
0x1800a59f1  mov     rsi, [rbp+90h+arg_8]
0x1800a59f8  mov     rax, [rsi]
0x1800a59fb  mov     rdi, [rax+50h]
0x1800a59ff  lea     rcx, [rsp+190h+pvarg]; pvarg
0x1800a5a04  call    cs:__imp_VariantInit
0x1800a5a0b  nop     dword ptr [rax+rax+00h]
0x1800a5a10  nop
0x1800a5a11  movups  xmm10, xmmword ptr [rsp+190h+pvarg]
0x1800a5a17  movsd   xmm11, qword ptr [rbp+90h+pvarg+10h]
0x1800a5a1d  lea     rcx, [rsp+190h+var_130]; pvarg
0x1800a5a22  call    cs:__imp_VariantInit
0x1800a5a29  nop     dword ptr [rax+rax+00h]
0x1800a5a2e  nop
0x1800a5a2f  movups  xmm8, xmmword ptr [rsp+190h+var_130]
0x1800a5a35  movsd   xmm9, qword ptr [rsp+190h+var_130+10h]
0x1800a5a3c  lea     rcx, [rsp+190h+var_148]; pvarg
0x1800a5a41  call    cs:__imp_VariantInit
0x1800a5a48  nop     dword ptr [rax+rax+00h]
0x1800a5a4d  nop
0x1800a5a4e  movups  xmm6, xmmword ptr [rsp+190h+var_148]
0x1800a5a53  movsd   xmm7, qword ptr [rsp+190h+var_148+10h]
0x1800a5a59  lea     rcx, [rsp+190h+var_160]; pvarg
0x1800a5a5e  call    cs:__imp_VariantInit
0x1800a5a65  nop     dword ptr [rax+rax+00h]
0x1800a5a6a  nop
0x1800a5a6b  movups  xmm0, xmmword ptr [rsp+190h+var_160]
0x1800a5a70  movsd   xmm1, qword ptr [rsp+190h+var_160+10h]
0x1800a5a76  movaps  xmmword ptr [rbp+90h+var_100], xmm10
0x1800a5a7b  movsd   [rbp+90h+var_F0], xmm11
0x1800a5a81  movaps  [rbp+90h+var_E0], xmm8
0x1800a5a86  movsd   [rbp+90h+var_D0], xmm9
0x1800a5a8c  movaps  [rbp+90h+var_C0], xmm6
0x1800a5a90  movsd   [rbp+90h+var_B0], xmm7
0x1800a5a95  movaps  [rbp+90h+var_A0], xmm0
0x1800a5a99  movsd   [rbp+90h+var_90], xmm1
0x1800a5a9e  lea     rax, [rbp+90h+var_100]
0x1800a5aa2  mov     [rsp+190h+ppv], rax; int
0x1800a5aa7  lea     r9, [rbp+90h+var_E0]
0x1800a5aab  lea     r8, [rbp+90h+var_C0]
0x1800a5aaf  lea     rdx, [rbp+90h+var_A0]
0x1800a5ab3  mov     rcx, rsi
0x1800a5ab6  mov     rax, rdi
0x1800a5ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5abe  mov     edi, eax
0x1800a5ac0  lea     rcx, [rsp+190h+var_160]; pvarg
0x1800a5ac5  call    cs:__imp_VariantClear
0x1800a5acc  nop     dword ptr [rax+rax+00h]
0x1800a5ad1  nop
0x1800a5ad2  lea     rcx, [rsp+190h+var_148]; pvarg
0x1800a5ad7  call    cs:__imp_VariantClear
0x1800a5ade  nop     dword ptr [rax+rax+00h]
0x1800a5ae3  nop
0x1800a5ae4  lea     rcx, [rsp+190h+var_130]; pvarg
0x1800a5ae9  call    cs:__imp_VariantClear
0x1800a5af0  nop     dword ptr [rax+rax+00h]
0x1800a5af5  nop
0x1800a5af6  lea     rcx, [rsp+190h+pvarg]; pvarg
0x1800a5afb  call    cs:__imp_VariantClear
0x1800a5b02  nop     dword ptr [rax+rax+00h]
0x1800a5b07  test    edi, edi
0x1800a5b09  jns     short loc_1800A5B15
0x1800a5b0b  mov     edx, 320h
0x1800a5b10  jmp     loc_1800A59D6
0x1800a5b15  mov     [rbp+90h+arg_10], 0
0x1800a5b20  lea     rcx, [rbp+90h+arg_10]
0x1800a5b27  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a5b2c  lea     r9, [rbp+90h+arg_10]
0x1800a5b33  xor     r8d, r8d
0x1800a5b36  mov     rdx, r14
0x1800a5b39  mov     rcx, [rbp+90h+arg_8]
0x1800a5b40  call    _anonymous_namespace___GetTaskFolder
0x1800a5b45  mov     edi, eax
0x1800a5b47  test    eax, eax
0x1800a5b49  js      short loc_1800A5BBE
0x1800a5b4b  lea     rdx, aSyncStatusPoll; "Sync Status Poll"
0x1800a5b52  lea     rcx, [rbp+90h+arg_18]
0x1800a5b59  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x1800a5b5e  nop
0x1800a5b5f  mov     rdx, [rbp+90h+arg_18]
0x1800a5b66  test    rdx, rdx
0x1800a5b69  jnz     short loc_1800A5B9A
0x1800a5b6b  mov     rcx, [rbp+98h]; this
0x1800a5b72  mov     edi, 8007000Eh
0x1800a5b77  mov     r9d, edi; char *
0x1800a5b7a  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a5b81  mov     edx, 327h; void *
0x1800a5b86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5b8b  nop
0x1800a5b8c  lea     rcx, [rbp+90h+arg_18]
0x1800a5b93  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a5b98  jmp     short loc_1800A5BED
0x1800a5b9a  mov     rcx, [rbp+90h+arg_10]
0x1800a5ba1  mov     rax, [rcx]
0x1800a5ba4  xor     r8d, r8d
0x1800a5ba7  mov     rax, [rax+78h]
0x1800a5bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5bb0  mov     edi, eax
0x1800a5bb2  lea     rcx, [rbp+90h+arg_18]
0x1800a5bb9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a5bbe  lea     eax, [rdi+7FF8FFFEh]
0x1800a5bc4  cmp     eax, 1
0x1800a5bc7  ja      short loc_1800A5BCD
0x1800a5bc9  xor     edi, edi
0x1800a5bcb  jmp     short loc_1800A5BED
0x1800a5bcd  test    edi, edi
0x1800a5bcf  jns     short loc_1800A5BED
0x1800a5bd1  mov     rcx, [rbp+98h]; this
0x1800a5bd8  mov     r9d, edi; char *
0x1800a5bdb  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a5be2  mov     edx, 32Dh; void *
0x1800a5be7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5bec  nop
0x1800a5bed  lea     rcx, [rbp+90h+arg_10]
0x1800a5bf4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a5bf9  nop
0x1800a5bfa  lea     rcx, [rbp+90h+arg_8]
0x1800a5c01  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a5c06  nop
0x1800a5c07  test    ebx, ebx
0x1800a5c09  js      short loc_1800A5C17
0x1800a5c0b  call    cs:__imp_RoUninitialize
0x1800a5c12  nop     dword ptr [rax+rax+00h]
0x1800a5c17  mov     eax, edi
0x1800a5c19  lea     r11, [rsp+190h+var_20]
0x1800a5c21  movaps  xmm6, xmmword ptr [r11-10h]
0x1800a5c26  movaps  xmm7, xmmword ptr [r11-20h]
0x1800a5c2b  movaps  xmm8, xmmword ptr [r11-30h]
0x1800a5c30  movaps  xmm9, xmmword ptr [r11-40h]
0x1800a5c35  movaps  xmm10, xmmword ptr [r11-50h]
0x1800a5c3a  movaps  xmm11, xmmword ptr [r11-60h]
0x1800a5c3f  mov     rsp, r11
0x1800a5c42  pop     r14
0x1800a5c44  pop     rdi
0x1800a5c45  pop     rsi
0x1800a5c46  pop     rbx
0x1800a5c47  pop     rbp
0x1800a5c48  retn
```
