# Microsoft::Windows::Autopilot::AutoPilotTasks::GetNamedAutopilotTask(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Microsoft::WRL::ComPtr<IRegisteredTask> &)

- ea: `0x18019b28c`
- end: `0x18019b6e1`
- name: `?GetNamedAutopilotTask@AutoPilotTasks@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$ComPtr@UIRegisteredTask@@@WRL@4@@Z`
- size: `1109`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18019b1e4`

## callees

- `0x180067398`
- `0x180067e54`
- `0x180080bac`
- `0x180084d5c`
- `0x18008a26c`
- `0x18019b28c`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18019b2f2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18019b2f2`
- `OLEAUT32!__imp_VariantInit` at `0x18019b34c`
- `OLEAUT32!__imp_VariantInit` at `0x18019b371`
- `OLEAUT32!__imp_VariantInit` at `0x18019b393`
- `OLEAUT32!__imp_VariantInit` at `0x18019b3b0`
- `OLEAUT32!__imp_VariantInit` at `0x18019b34c`
- `OLEAUT32!__imp_VariantInit` at `0x18019b371`
- `OLEAUT32!__imp_VariantInit` at `0x18019b393`
- `OLEAUT32!__imp_VariantInit` at `0x18019b3b0`
- `OLEAUT32!__imp_VariantClear` at `0x18019b447`
- `OLEAUT32!__imp_VariantClear` at `0x18019b459`
- `OLEAUT32!__imp_VariantClear` at `0x18019b46b`
- `OLEAUT32!__imp_VariantClear` at `0x18019b480`
- `OLEAUT32!__imp_VariantClear` at `0x18019b447`
- `OLEAUT32!__imp_VariantClear` at `0x18019b459`
- `OLEAUT32!__imp_VariantClear` at `0x18019b46b`
- `OLEAUT32!__imp_VariantClear` at `0x18019b480`

## string_xrefs

- `0x18019b30f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18019b49b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18019b523`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18019b5b8`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18019b61f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotTasks::GetNamedAutopilotTask(__int64 a1, __int64 *a2)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  __int64 result; // rax
  __int64 (*v7)(void); // rbx
  __int128 v8; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v10; // xmm8
  IRecordInfo *v11; // xmm9_8
  __int128 v12; // xmm6
  IRecordInfo *v13; // xmm7_8
  int v14; // ebx
  const char *v15; // r9
  LPVOID v16; // rbx
  __int64 (__fastcall *v17)(LPVOID, _QWORD, __int64 *); // rdi
  _QWORD *bstr; // rax
  int v19; // ebx
  __int64 v20; // rdx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64, __int64 *); // rbx
  int v23; // eax
  unsigned int v24; // ebx
  __int64 v25; // rcx
  int ppv; // [rsp+20h] [rbp-188h]
  __int64 v27; // [rsp+30h] [rbp-178h] BYREF
  __int64 v28; // [rsp+38h] [rbp-170h] BYREF
  _BYTE v29[8]; // [rsp+40h] [rbp-168h] BYREF
  VARIANTARG v30; // [rsp+48h] [rbp-160h] BYREF
  VARIANTARG v31; // [rsp+60h] [rbp-148h] BYREF
  VARIANTARG v32; // [rsp+78h] [rbp-130h] BYREF
  VARIANTARG pvarg; // [rsp+90h] [rbp-118h] BYREF
  int v34[4]; // [rsp+B0h] [rbp-F8h] BYREF
  IRecordInfo *v35; // [rsp+C0h] [rbp-E8h]
  __int128 v36; // [rsp+D0h] [rbp-D8h]
  IRecordInfo *v37; // [rsp+E0h] [rbp-C8h]
  __int128 v38; // [rsp+F0h] [rbp-B8h]
  IRecordInfo *v39; // [rsp+100h] [rbp-A8h]
  VARIANTARG v40; // [rsp+110h] [rbp-98h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]
  LPVOID v42; // [rsp+1C0h] [rbp+18h] BYREF
  __int64 v43; // [rsp+1C8h] [rbp+20h] BYREF

  v42 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
  v4 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &v42);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v7 = *(__int64 (**)(void))(*(_QWORD *)v42 + 80LL);
    VariantInit(&pvarg);
    v8 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    VariantInit(&v32);
    v10 = *(_OWORD *)&v32.vt;
    v11 = v32.pRecInfo;
    VariantInit(&v31);
    v12 = *(_OWORD *)&v31.vt;
    v13 = v31.pRecInfo;
    VariantInit(&v30);
    *(_OWORD *)v34 = v8;
    v35 = pRecInfo;
    v36 = v10;
    v37 = v11;
    v38 = v12;
    v39 = v13;
    v40 = v30;
    try
    {
      v14 = v7();
      VariantClear(&v30);
      VariantClear(&v31);
      VariantClear(&v32);
      VariantClear(&pvarg);
      if ( v14 >= 0 )
      {
        v27 = 0;
        v16 = v42;
        v17 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v42 + 56LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
        bstr = (_QWORD *)wil::make_bstr(v29, L"\\Microsoft\\Windows\\Management\\Autopilot");
        v19 = v17(v16, *bstr, &v27);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v29);
        if ( v19 >= 0 )
        {
          v43 = 0;
          v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
          wil::make_bstr(&v28, v20);
          v21 = v27;
          v22 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v27 + 104LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
          v23 = v22(v21, v28, &v43);
          v24 = v23;
          if ( v23 >= 0 )
          {
            if ( v43 )
            {
              v25 = *a2;
              *a2 = v43;
              v43 = v25;
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
              result = 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x66,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
                (const char *)0x8000FFFFLL,
                (int)v34);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
              result = 2147549183LL;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x65,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
              (const char *)(unsigned int)v23,
              (int)v34);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
            result = v24;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x61,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
            (const char *)(unsigned int)v19,
            (int)v34);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
          result = (unsigned int)v19;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5E,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
          (const char *)(unsigned int)v14,
          (int)v34);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
        result = (unsigned int)v14;
      }
    }
    catch ( ... )
    {
      LODWORD(v42) = wil::details::in1diag3::Return_CaughtException(
                       retaddr,
                       (void *)0x6C,
                       (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
                       v15);
      return (unsigned int)v42;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
      (const char *)(unsigned int)v4,
      ppv);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18019b28c  mov     rax, rsp
0x18019b28f  mov     [rax+8], rbx
0x18019b293  push    rsi
0x18019b294  push    rdi
0x18019b295  push    r14
0x18019b297  sub     rsp, 190h
0x18019b29e  movaps  xmmword ptr [rax-28h], xmm6
0x18019b2a2  movaps  xmmword ptr [rax-38h], xmm7
0x18019b2a6  movaps  xmmword ptr [rax-48h], xmm8
0x18019b2ab  movaps  xmmword ptr [rax-58h], xmm9
0x18019b2b0  movaps  xmmword ptr [rax-68h], xmm10
0x18019b2b5  movaps  xmmword ptr [rax-78h], xmm11
0x18019b2ba  mov     rsi, rdx
0x18019b2bd  mov     r14, rcx
0x18019b2c0  mov     qword ptr [rax+18h], 0
0x18019b2c8  lea     rcx, [rax+18h]
0x18019b2cc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019b2d1  lea     rax, [rsp+1A8h+arg_10]
0x18019b2d9  mov     qword ptr [rsp+1A8h+ppv], rax; int
0x18019b2de  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x18019b2e5  xor     edx, edx; pUnkOuter
0x18019b2e7  lea     r8d, [rdx+1]; dwClsContext
0x18019b2eb  lea     rcx, CLSID_TaskScheduler; rclsid
0x18019b2f2  call    cs:__imp_CoCreateInstance
0x18019b2f9  nop     dword ptr [rax+rax+00h]
0x18019b2fe  mov     ebx, eax
0x18019b300  test    eax, eax
0x18019b302  jns     short loc_18019B335
0x18019b304  mov     rcx, [rsp+1A8h]; this
0x18019b30c  mov     r9d, eax; char *
0x18019b30f  lea     r8, aOnecoreuapAdmi_96; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019b316  mov     edx, 5Dh ; ']'; void *
0x18019b31b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019b320  nop
0x18019b321  lea     rcx, [rsp+1A8h+arg_10]
0x18019b329  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019b32e  mov     eax, ebx
0x18019b330  jmp     loc_18019B6AE
0x18019b335  mov     rdi, [rsp+1A8h+arg_10]
0x18019b33d  mov     rax, [rdi]
0x18019b340  mov     rbx, [rax+50h]
0x18019b344  lea     rcx, [rsp+1A8h+pvarg]; pvarg
0x18019b34c  call    cs:__imp_VariantInit
0x18019b353  nop     dword ptr [rax+rax+00h]
0x18019b358  nop
0x18019b359  movups  xmm10, xmmword ptr [rsp+1A8h+pvarg]
0x18019b362  movsd   xmm11, qword ptr [rsp+1A8h+pvarg+10h]
0x18019b36c  lea     rcx, [rsp+1A8h+var_130]; pvarg
0x18019b371  call    cs:__imp_VariantInit
0x18019b378  nop     dword ptr [rax+rax+00h]
0x18019b37d  nop
0x18019b37e  movups  xmm8, xmmword ptr [rsp+1A8h+var_130]
0x18019b384  movsd   xmm9, qword ptr [rsp+1A8h+var_130+10h]
0x18019b38e  lea     rcx, [rsp+1A8h+var_148]; pvarg
0x18019b393  call    cs:__imp_VariantInit
0x18019b39a  nop     dword ptr [rax+rax+00h]
0x18019b39f  nop
0x18019b3a0  movups  xmm6, xmmword ptr [rsp+1A8h+var_148]
0x18019b3a5  movsd   xmm7, qword ptr [rsp+1A8h+var_148+10h]
0x18019b3ab  lea     rcx, [rsp+1A8h+var_160]; pvarg
0x18019b3b0  call    cs:__imp_VariantInit
0x18019b3b7  nop     dword ptr [rax+rax+00h]
0x18019b3bc  nop
0x18019b3bd  movups  xmm0, xmmword ptr [rsp+1A8h+var_160]
0x18019b3c2  movsd   xmm1, qword ptr [rsp+1A8h+var_160+10h]
0x18019b3c8  movaps  xmmword ptr [rsp+1A8h+var_F8], xmm10
0x18019b3d1  movsd   [rsp+1A8h+var_E8], xmm11
0x18019b3db  movaps  [rsp+1A8h+var_D8], xmm8
0x18019b3e4  movsd   [rsp+1A8h+var_C8], xmm9
0x18019b3ee  movaps  [rsp+1A8h+var_B8], xmm6
0x18019b3f6  movsd   [rsp+1A8h+var_A8], xmm7
0x18019b3ff  movaps  [rsp+1A8h+var_98], xmm0
0x18019b407  movsd   [rsp+1A8h+var_88], xmm1
0x18019b410  lea     rax, [rsp+1A8h+var_F8]
0x18019b418  mov     qword ptr [rsp+1A8h+ppv], rax; int
0x18019b41d  lea     r9, [rsp+1A8h+var_D8]
0x18019b425  lea     r8, [rsp+1A8h+var_B8]
0x18019b42d  lea     rdx, [rsp+1A8h+var_98]
0x18019b435  mov     rcx, rdi
0x18019b438  mov     rax, rbx
0x18019b43b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b440  mov     ebx, eax
0x18019b442  lea     rcx, [rsp+1A8h+var_160]; pvarg
0x18019b447  call    cs:__imp_VariantClear
0x18019b44e  nop     dword ptr [rax+rax+00h]
0x18019b453  nop
0x18019b454  lea     rcx, [rsp+1A8h+var_148]; pvarg
0x18019b459  call    cs:__imp_VariantClear
0x18019b460  nop     dword ptr [rax+rax+00h]
0x18019b465  nop
0x18019b466  lea     rcx, [rsp+1A8h+var_130]; pvarg
0x18019b46b  call    cs:__imp_VariantClear
0x18019b472  nop     dword ptr [rax+rax+00h]
0x18019b477  nop
0x18019b478  lea     rcx, [rsp+1A8h+pvarg]; pvarg
0x18019b480  call    cs:__imp_VariantClear
0x18019b487  nop     dword ptr [rax+rax+00h]
0x18019b48c  test    ebx, ebx
0x18019b48e  jns     short loc_18019B4C1
0x18019b490  mov     rcx, [rsp+1A8h]; this
0x18019b498  mov     r9d, ebx; char *
0x18019b49b  lea     r8, aOnecoreuapAdmi_96; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019b4a2  mov     edx, 5Eh ; '^'; void *
0x18019b4a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019b4ac  nop
0x18019b4ad  lea     rcx, [rsp+1A8h+arg_10]
0x18019b4b5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019b4ba  mov     eax, ebx
0x18019b4bc  jmp     loc_18019B6AE
0x18019b4c1  mov     [rsp+1A8h+var_178], 0
0x18019b4ca  mov     rbx, [rsp+1A8h+arg_10]
0x18019b4d2  mov     rax, [rbx]
0x18019b4d5  mov     rdi, [rax+38h]
0x18019b4d9  lea     rcx, [rsp+1A8h+var_178]
0x18019b4de  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019b4e3  lea     rdx, aMicrosoftWindo_84; "\\Microsoft\\Windows\\Management\\Autop"...
0x18019b4ea  lea     rcx, [rsp+1A8h+var_168]
0x18019b4ef  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18019b4f4  nop
0x18019b4f5  lea     r8, [rsp+1A8h+var_178]
0x18019b4fa  mov     rdx, [rax]
0x18019b4fd  mov     rcx, rbx
0x18019b500  mov     rax, rdi
0x18019b503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b508  mov     ebx, eax
0x18019b50a  lea     rcx, [rsp+1A8h+var_168]
0x18019b50f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18019b514  test    ebx, ebx
0x18019b516  jns     short loc_18019B554
0x18019b518  mov     rcx, [rsp+1A8h]; this
0x18019b520  mov     r9d, ebx; char *
0x18019b523  lea     r8, aOnecoreuapAdmi_96; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019b52a  mov     edx, 61h ; 'a'; void *
0x18019b52f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019b534  nop
0x18019b535  lea     rcx, [rsp+1A8h+var_178]
0x18019b53a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019b53f  nop
0x18019b540  lea     rcx, [rsp+1A8h+arg_10]
0x18019b548  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019b54d  mov     eax, ebx
0x18019b54f  jmp     loc_18019B6AE
0x18019b554  mov     [rsp+1A8h+arg_18], 0
0x18019b560  mov     rcx, r14
0x18019b563  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18019b568  mov     rdx, rax
0x18019b56b  lea     rcx, [rsp+1A8h+var_170]
0x18019b570  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18019b575  nop
0x18019b576  mov     rdi, [rsp+1A8h+var_178]
0x18019b57b  mov     rax, [rdi]
0x18019b57e  mov     rbx, [rax+68h]
0x18019b582  lea     rcx, [rsp+1A8h+arg_18]
0x18019b58a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019b58f  lea     r8, [rsp+1A8h+arg_18]
0x18019b597  mov     rdx, [rsp+1A8h+var_170]
0x18019b59c  mov     rcx, rdi
0x18019b59f  mov     rax, rbx
0x18019b5a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b5a7  mov     ebx, eax
0x18019b5a9  test    eax, eax
0x18019b5ab  jns     short loc_18019B602
0x18019b5ad  mov     rcx, [rsp+1A8h]; this
0x18019b5b5  mov     r9d, eax; char *
0x18019b5b8  lea     r8, aOnecoreuapAdmi_96; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019b5bf  mov     edx, 65h ; 'e'; void *
0x18019b5c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019b5c9  nop
0x18019b5ca  lea     rcx, [rsp+1A8h+var_170]
0x18019b5cf  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18019b5d4  nop
0x18019b5d5  lea     rcx, [rsp+1A8h+arg_18]
0x18019b5dd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019b5e2  nop
0x18019b5e3  lea     rcx, [rsp+1A8h+var_178]
0x18019b5e8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019b5ed  nop
0x18019b5ee  lea     rcx, [rsp+1A8h+arg_10]
0x18019b5f6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019b5fb  mov     eax, ebx
0x18019b5fd  jmp     loc_18019B6AE
0x18019b602  mov     rax, [rsp+1A8h+arg_18]
0x18019b60a  test    rax, rax
0x18019b60d  jnz     short loc_18019B664
0x18019b60f  mov     rcx, [rsp+1A8h]; this
0x18019b617  mov     ebx, 8000FFFFh
0x18019b61c  mov     r9d, ebx; char *
0x18019b61f  lea     r8, aOnecoreuapAdmi_96; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019b626  lea     edx, [rax+66h]; void *
0x18019b629  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019b62e  nop
0x18019b62f  lea     rcx, [rsp+1A8h+var_170]
0x18019b634  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18019b639  nop
0x18019b63a  lea     rcx, [rsp+1A8h+arg_18]
0x18019b642  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019b647  nop
0x18019b648  lea     rcx, [rsp+1A8h+var_178]
0x18019b64d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019b652  nop
0x18019b653  lea     rcx, [rsp+1A8h+arg_10]
0x18019b65b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019b660  mov     eax, ebx
0x18019b662  jmp     short loc_18019B6AE
0x18019b664  mov     rcx, [rsi]
0x18019b667  mov     [rsi], rax
0x18019b66a  mov     [rsp+1A8h+arg_18], rcx
0x18019b672  lea     rcx, [rsp+1A8h+var_170]
0x18019b677  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18019b67c  nop
0x18019b67d  lea     rcx, [rsp+1A8h+arg_18]
0x18019b685  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019b68a  nop
0x18019b68b  lea     rcx, [rsp+1A8h+var_178]
0x18019b690  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019b695  nop
0x18019b696  lea     rcx, [rsp+1A8h+arg_10]
0x18019b69e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019b6a3  xor     eax, eax
0x18019b6a5  jmp     short loc_18019B6AE
0x18019b6a7  mov     eax, dword ptr [rsp+1A8h+arg_10]
0x18019b6ae  lea     r11, [rsp+1A8h+var_18]
0x18019b6b6  mov     rbx, [r11+20h]
0x18019b6ba  movaps  xmm6, xmmword ptr [r11-10h]
0x18019b6bf  movaps  xmm7, xmmword ptr [r11-20h]
0x18019b6c4  movaps  xmm8, xmmword ptr [r11-30h]
0x18019b6c9  movaps  xmm9, xmmword ptr [r11-40h]
0x18019b6ce  movaps  xmm10, xmmword ptr [r11-50h]
0x18019b6d3  movaps  xmm11, xmmword ptr [r11-60h]
0x18019b6d8  mov     rsp, r11
0x18019b6db  pop     r14
0x18019b6dd  pop     rdi
0x18019b6de  pop     rsi
0x18019b6df  retn
```
