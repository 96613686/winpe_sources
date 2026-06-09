# Microsoft::Windows::Autopilot::AutoPilotTasks::GetNamedAutopilotTask(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Microsoft::WRL::ComPtr<IRegisteredTask> &)

- ea: `0x180196110`
- end: `0x18019652f`
- name: `?GetNamedAutopilotTask@AutoPilotTasks@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$ComPtr@UIRegisteredTask@@@WRL@4@@Z`
- size: `1055`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180196068`

## callees

- `0x180067008`
- `0x180067a54`
- `0x18008019c`
- `0x1800841e8`
- `0x18008939c`
- `0x180196110`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180196176`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180196176`
- `OLEAUT32!__imp_VariantInit` at `0x1801961ca`
- `OLEAUT32!__imp_VariantInit` at `0x1801961e9`
- `OLEAUT32!__imp_VariantInit` at `0x180196205`
- `OLEAUT32!__imp_VariantInit` at `0x18019621c`
- `OLEAUT32!__imp_VariantInit` at `0x1801961ca`
- `OLEAUT32!__imp_VariantInit` at `0x1801961e9`
- `OLEAUT32!__imp_VariantInit` at `0x180196205`
- `OLEAUT32!__imp_VariantInit` at `0x18019621c`
- `OLEAUT32!__imp_VariantClear` at `0x1801962ad`
- `OLEAUT32!__imp_VariantClear` at `0x1801962b9`
- `OLEAUT32!__imp_VariantClear` at `0x1801962c5`
- `OLEAUT32!__imp_VariantClear` at `0x1801962d4`
- `OLEAUT32!__imp_VariantClear` at `0x1801962ad`
- `OLEAUT32!__imp_VariantClear` at `0x1801962b9`
- `OLEAUT32!__imp_VariantClear` at `0x1801962c5`
- `OLEAUT32!__imp_VariantClear` at `0x1801962d4`

## string_xrefs

- `0x18019618d`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x1801962e9`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x180196371`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x180196406`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18019646d`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
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
0x180196110  mov     rax, rsp
0x180196113  mov     [rax+8], rbx
0x180196117  push    rsi
0x180196118  push    rdi
0x180196119  push    r14
0x18019611b  sub     rsp, 190h
0x180196122  movaps  xmmword ptr [rax-28h], xmm6
0x180196126  movaps  xmmword ptr [rax-38h], xmm7
0x18019612a  movaps  xmmword ptr [rax-48h], xmm8
0x18019612f  movaps  xmmword ptr [rax-58h], xmm9
0x180196134  movaps  xmmword ptr [rax-68h], xmm10
0x180196139  movaps  xmmword ptr [rax-78h], xmm11
0x18019613e  mov     rsi, rdx
0x180196141  mov     r14, rcx
0x180196144  mov     qword ptr [rax+18h], 0
0x18019614c  lea     rcx, [rax+18h]
0x180196150  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180196155  lea     rax, [rsp+1A8h+arg_10]
0x18019615d  mov     qword ptr [rsp+1A8h+ppv], rax; int
0x180196162  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x180196169  xor     edx, edx; pUnkOuter
0x18019616b  lea     r8d, [rdx+1]; dwClsContext
0x18019616f  lea     rcx, CLSID_TaskScheduler; rclsid
0x180196176  call    cs:__imp_CoCreateInstance
0x18019617c  mov     ebx, eax
0x18019617e  test    eax, eax
0x180196180  jns     short loc_1801961B3
0x180196182  mov     rcx, [rsp+1A8h]; this
0x18019618a  mov     r9d, eax; char *
0x18019618d  lea     r8, aOnecoreuapAdmi_96; "onecoreuap\\admin\\moderndeployment\\au"...
0x180196194  mov     edx, 5Dh ; ']'; void *
0x180196199  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019619e  nop
0x18019619f  lea     rcx, [rsp+1A8h+arg_10]
0x1801961a7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801961ac  mov     eax, ebx
0x1801961ae  jmp     loc_1801964FC
0x1801961b3  mov     rdi, [rsp+1A8h+arg_10]
0x1801961bb  mov     rax, [rdi]
0x1801961be  mov     rbx, [rax+50h]
0x1801961c2  lea     rcx, [rsp+1A8h+pvarg]; pvarg
0x1801961ca  call    cs:__imp_VariantInit
0x1801961d0  nop
0x1801961d1  movups  xmm10, xmmword ptr [rsp+1A8h+pvarg]
0x1801961da  movsd   xmm11, qword ptr [rsp+1A8h+pvarg+10h]
0x1801961e4  lea     rcx, [rsp+1A8h+var_130]; pvarg
0x1801961e9  call    cs:__imp_VariantInit
0x1801961ef  nop
0x1801961f0  movups  xmm8, xmmword ptr [rsp+1A8h+var_130]
0x1801961f6  movsd   xmm9, qword ptr [rsp+1A8h+var_130+10h]
0x180196200  lea     rcx, [rsp+1A8h+var_148]; pvarg
0x180196205  call    cs:__imp_VariantInit
0x18019620b  nop
0x18019620c  movups  xmm6, xmmword ptr [rsp+1A8h+var_148]
0x180196211  movsd   xmm7, qword ptr [rsp+1A8h+var_148+10h]
0x180196217  lea     rcx, [rsp+1A8h+var_160]; pvarg
0x18019621c  call    cs:__imp_VariantInit
0x180196222  nop
0x180196223  movups  xmm0, xmmword ptr [rsp+1A8h+var_160]
0x180196228  movsd   xmm1, qword ptr [rsp+1A8h+var_160+10h]
0x18019622e  movaps  xmmword ptr [rsp+1A8h+var_F8], xmm10
0x180196237  movsd   [rsp+1A8h+var_E8], xmm11
0x180196241  movaps  [rsp+1A8h+var_D8], xmm8
0x18019624a  movsd   [rsp+1A8h+var_C8], xmm9
0x180196254  movaps  [rsp+1A8h+var_B8], xmm6
0x18019625c  movsd   [rsp+1A8h+var_A8], xmm7
0x180196265  movaps  [rsp+1A8h+var_98], xmm0
0x18019626d  movsd   [rsp+1A8h+var_88], xmm1
0x180196276  lea     rax, [rsp+1A8h+var_F8]
0x18019627e  mov     qword ptr [rsp+1A8h+ppv], rax; int
0x180196283  lea     r9, [rsp+1A8h+var_D8]
0x18019628b  lea     r8, [rsp+1A8h+var_B8]
0x180196293  lea     rdx, [rsp+1A8h+var_98]
0x18019629b  mov     rcx, rdi
0x18019629e  mov     rax, rbx
0x1801962a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801962a6  mov     ebx, eax
0x1801962a8  lea     rcx, [rsp+1A8h+var_160]; pvarg
0x1801962ad  call    cs:__imp_VariantClear
0x1801962b3  nop
0x1801962b4  lea     rcx, [rsp+1A8h+var_148]; pvarg
0x1801962b9  call    cs:__imp_VariantClear
0x1801962bf  nop
0x1801962c0  lea     rcx, [rsp+1A8h+var_130]; pvarg
0x1801962c5  call    cs:__imp_VariantClear
0x1801962cb  nop
0x1801962cc  lea     rcx, [rsp+1A8h+pvarg]; pvarg
0x1801962d4  call    cs:__imp_VariantClear
0x1801962da  test    ebx, ebx
0x1801962dc  jns     short loc_18019630F
0x1801962de  mov     rcx, [rsp+1A8h]; this
0x1801962e6  mov     r9d, ebx; char *
0x1801962e9  lea     r8, aOnecoreuapAdmi_96; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801962f0  mov     edx, 5Eh ; '^'; void *
0x1801962f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801962fa  nop
0x1801962fb  lea     rcx, [rsp+1A8h+arg_10]
0x180196303  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180196308  mov     eax, ebx
0x18019630a  jmp     loc_1801964FC
0x18019630f  mov     [rsp+1A8h+var_178], 0
0x180196318  mov     rbx, [rsp+1A8h+arg_10]
0x180196320  mov     rax, [rbx]
0x180196323  mov     rdi, [rax+38h]
0x180196327  lea     rcx, [rsp+1A8h+var_178]
0x18019632c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180196331  lea     rdx, aMicrosoftWindo_84; "\\Microsoft\\Windows\\Management\\Autop"...
0x180196338  lea     rcx, [rsp+1A8h+var_168]
0x18019633d  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180196342  nop
0x180196343  lea     r8, [rsp+1A8h+var_178]
0x180196348  mov     rdx, [rax]
0x18019634b  mov     rcx, rbx
0x18019634e  mov     rax, rdi
0x180196351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180196356  mov     ebx, eax
0x180196358  lea     rcx, [rsp+1A8h+var_168]
0x18019635d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180196362  test    ebx, ebx
0x180196364  jns     short loc_1801963A2
0x180196366  mov     rcx, [rsp+1A8h]; this
0x18019636e  mov     r9d, ebx; char *
0x180196371  lea     r8, aOnecoreuapAdmi_96; "onecoreuap\\admin\\moderndeployment\\au"...
0x180196378  mov     edx, 61h ; 'a'; void *
0x18019637d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180196382  nop
0x180196383  lea     rcx, [rsp+1A8h+var_178]
0x180196388  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019638d  nop
0x18019638e  lea     rcx, [rsp+1A8h+arg_10]
0x180196396  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019639b  mov     eax, ebx
0x18019639d  jmp     loc_1801964FC
0x1801963a2  mov     [rsp+1A8h+arg_18], 0
0x1801963ae  mov     rcx, r14
0x1801963b1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801963b6  mov     rdx, rax
0x1801963b9  lea     rcx, [rsp+1A8h+var_170]
0x1801963be  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1801963c3  nop
0x1801963c4  mov     rdi, [rsp+1A8h+var_178]
0x1801963c9  mov     rax, [rdi]
0x1801963cc  mov     rbx, [rax+68h]
0x1801963d0  lea     rcx, [rsp+1A8h+arg_18]
0x1801963d8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801963dd  lea     r8, [rsp+1A8h+arg_18]
0x1801963e5  mov     rdx, [rsp+1A8h+var_170]
0x1801963ea  mov     rcx, rdi
0x1801963ed  mov     rax, rbx
0x1801963f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801963f5  mov     ebx, eax
0x1801963f7  test    eax, eax
0x1801963f9  jns     short loc_180196450
0x1801963fb  mov     rcx, [rsp+1A8h]; this
0x180196403  mov     r9d, eax; char *
0x180196406  lea     r8, aOnecoreuapAdmi_96; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019640d  mov     edx, 65h ; 'e'; void *
0x180196412  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180196417  nop
0x180196418  lea     rcx, [rsp+1A8h+var_170]
0x18019641d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180196422  nop
0x180196423  lea     rcx, [rsp+1A8h+arg_18]
0x18019642b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180196430  nop
0x180196431  lea     rcx, [rsp+1A8h+var_178]
0x180196436  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019643b  nop
0x18019643c  lea     rcx, [rsp+1A8h+arg_10]
0x180196444  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180196449  mov     eax, ebx
0x18019644b  jmp     loc_1801964FC
0x180196450  mov     rax, [rsp+1A8h+arg_18]
0x180196458  test    rax, rax
0x18019645b  jnz     short loc_1801964B2
0x18019645d  mov     rcx, [rsp+1A8h]; this
0x180196465  mov     ebx, 8000FFFFh
0x18019646a  mov     r9d, ebx; char *
0x18019646d  lea     r8, aOnecoreuapAdmi_96; "onecoreuap\\admin\\moderndeployment\\au"...
0x180196474  lea     edx, [rax+66h]; void *
0x180196477  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019647c  nop
0x18019647d  lea     rcx, [rsp+1A8h+var_170]
0x180196482  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180196487  nop
0x180196488  lea     rcx, [rsp+1A8h+arg_18]
0x180196490  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180196495  nop
0x180196496  lea     rcx, [rsp+1A8h+var_178]
0x18019649b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801964a0  nop
0x1801964a1  lea     rcx, [rsp+1A8h+arg_10]
0x1801964a9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801964ae  mov     eax, ebx
0x1801964b0  jmp     short loc_1801964FC
0x1801964b2  mov     rcx, [rsi]
0x1801964b5  mov     [rsi], rax
0x1801964b8  mov     [rsp+1A8h+arg_18], rcx
0x1801964c0  lea     rcx, [rsp+1A8h+var_170]
0x1801964c5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801964ca  nop
0x1801964cb  lea     rcx, [rsp+1A8h+arg_18]
0x1801964d3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801964d8  nop
0x1801964d9  lea     rcx, [rsp+1A8h+var_178]
0x1801964de  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801964e3  nop
0x1801964e4  lea     rcx, [rsp+1A8h+arg_10]
0x1801964ec  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801964f1  xor     eax, eax
0x1801964f3  jmp     short loc_1801964FC
0x1801964f5  mov     eax, dword ptr [rsp+1A8h+arg_10]
0x1801964fc  lea     r11, [rsp+1A8h+var_18]
0x180196504  mov     rbx, [r11+20h]
0x180196508  movaps  xmm6, xmmword ptr [r11-10h]
0x18019650d  movaps  xmm7, xmmword ptr [r11-20h]
0x180196512  movaps  xmm8, xmmword ptr [r11-30h]
0x180196517  movaps  xmm9, xmmword ptr [r11-40h]
0x18019651c  movaps  xmm10, xmmword ptr [r11-50h]
0x180196521  movaps  xmm11, xmmword ptr [r11-60h]
0x180196526  mov     rsp, r11
0x180196529  pop     r14
0x18019652b  pop     rdi
0x18019652c  pop     rsi
0x18019652d  retn
```
