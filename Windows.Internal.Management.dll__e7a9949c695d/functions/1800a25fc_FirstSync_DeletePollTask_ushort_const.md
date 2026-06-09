# FirstSync::DeletePollTask(ushort const *)

- ea: `0x1800a25fc`
- end: `0x1800a28f7`
- name: `?DeletePollTask@FirstSync@@YAJPEBG@Z`
- size: `763`
- prototype: `__int64 __fastcall(FirstSync *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800a3ef4`
- `0x1800a40ac`

## callees

- `0x18000992c`
- `0x18000a2a4`
- `0x180024cd0`
- `0x180069770`
- `0x1800a25fc`
- `0x1800a3424`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a26a9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a26a9`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800a28bf`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800a28bf`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800a2664`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800a2664`
- `OLEAUT32!__imp_VariantInit` at `0x1800a26e8`
- `OLEAUT32!__imp_VariantInit` at `0x1800a2700`
- `OLEAUT32!__imp_VariantInit` at `0x1800a2719`
- `OLEAUT32!__imp_VariantInit` at `0x1800a2730`
- `OLEAUT32!__imp_VariantInit` at `0x1800a26e8`
- `OLEAUT32!__imp_VariantInit` at `0x1800a2700`
- `OLEAUT32!__imp_VariantInit` at `0x1800a2719`
- `OLEAUT32!__imp_VariantInit` at `0x1800a2730`
- `OLEAUT32!__imp_VariantClear` at `0x1800a2791`
- `OLEAUT32!__imp_VariantClear` at `0x1800a279d`
- `OLEAUT32!__imp_VariantClear` at `0x1800a27a9`
- `OLEAUT32!__imp_VariantClear` at `0x1800a27b5`
- `OLEAUT32!__imp_VariantClear` at `0x1800a2791`
- `OLEAUT32!__imp_VariantClear` at `0x1800a279d`
- `OLEAUT32!__imp_VariantClear` at `0x1800a27a9`
- `OLEAUT32!__imp_VariantClear` at `0x1800a27b5`

## pseudocode

```c
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
0x1800a25fc  mov     rax, rsp
0x1800a25ff  push    rbp
0x1800a2600  push    rbx
0x1800a2601  push    rsi
0x1800a2602  push    rdi
0x1800a2603  push    r14
0x1800a2605  lea     rbp, [rsp-70h]
0x1800a260a  sub     rsp, 170h
0x1800a2611  movaps  xmmword ptr [rax-38h], xmm6
0x1800a2615  movaps  xmmword ptr [rax-48h], xmm7
0x1800a2619  movaps  xmmword ptr [rax-58h], xmm8
0x1800a261e  movaps  xmmword ptr [rax-68h], xmm9
0x1800a2623  movaps  xmmword ptr [rax-78h], xmm10
0x1800a2628  movaps  xmmword ptr [rax-88h], xmm11
0x1800a2630  mov     r14, rcx
0x1800a2633  test    rcx, rcx
0x1800a2636  jnz     short loc_1800A265F
0x1800a2638  mov     rcx, [rbp+98h]; this
0x1800a263f  mov     ebx, 80070057h
0x1800a2644  mov     r9d, ebx; char *
0x1800a2647  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a264e  mov     edx, 319h; void *
0x1800a2653  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2658  mov     eax, ebx
0x1800a265a  jmp     loc_1800A28C7
0x1800a265f  mov     ecx, 1
0x1800a2664  call    cs:__imp_RoInitialize
0x1800a266a  mov     ebx, eax
0x1800a266c  mov     [rbp+90h+arg_0], eax
0x1800a2672  mov     [rbp+90h+arg_8], 0
0x1800a267d  lea     rcx, [rbp+90h+arg_8]
0x1800a2684  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a2689  lea     rax, [rbp+90h+arg_8]
0x1800a2690  mov     [rsp+190h+ppv], rax; int
0x1800a2695  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1800a269c  xor     edx, edx; pUnkOuter
0x1800a269e  lea     r8d, [rdx+1]; dwClsContext
0x1800a26a2  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800a26a9  call    cs:__imp_CoCreateInstance
0x1800a26af  mov     edi, eax
0x1800a26b1  test    eax, eax
0x1800a26b3  jns     short loc_1800A26D5
0x1800a26b5  mov     edx, 31Eh; void *
0x1800a26ba  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a26c1  mov     r9d, edi; char *
0x1800a26c4  mov     rcx, [rbp+98h]; this
0x1800a26cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a26d0  jmp     loc_1800A28AE
0x1800a26d5  mov     rsi, [rbp+90h+arg_8]
0x1800a26dc  mov     rax, [rsi]
0x1800a26df  mov     rdi, [rax+50h]
0x1800a26e3  lea     rcx, [rsp+190h+pvarg]; pvarg
0x1800a26e8  call    cs:__imp_VariantInit
0x1800a26ee  nop
0x1800a26ef  movups  xmm10, xmmword ptr [rsp+190h+pvarg]
0x1800a26f5  movsd   xmm11, qword ptr [rbp+90h+pvarg+10h]
0x1800a26fb  lea     rcx, [rsp+190h+var_130]; pvarg
0x1800a2700  call    cs:__imp_VariantInit
0x1800a2706  nop
0x1800a2707  movups  xmm8, xmmword ptr [rsp+190h+var_130]
0x1800a270d  movsd   xmm9, qword ptr [rsp+190h+var_130+10h]
0x1800a2714  lea     rcx, [rsp+190h+var_148]; pvarg
0x1800a2719  call    cs:__imp_VariantInit
0x1800a271f  nop
0x1800a2720  movups  xmm6, xmmword ptr [rsp+190h+var_148]
0x1800a2725  movsd   xmm7, qword ptr [rsp+190h+var_148+10h]
0x1800a272b  lea     rcx, [rsp+190h+var_160]; pvarg
0x1800a2730  call    cs:__imp_VariantInit
0x1800a2736  nop
0x1800a2737  movups  xmm0, xmmword ptr [rsp+190h+var_160]
0x1800a273c  movsd   xmm1, qword ptr [rsp+190h+var_160+10h]
0x1800a2742  movaps  xmmword ptr [rbp+90h+var_100], xmm10
0x1800a2747  movsd   [rbp+90h+var_F0], xmm11
0x1800a274d  movaps  [rbp+90h+var_E0], xmm8
0x1800a2752  movsd   [rbp+90h+var_D0], xmm9
0x1800a2758  movaps  [rbp+90h+var_C0], xmm6
0x1800a275c  movsd   [rbp+90h+var_B0], xmm7
0x1800a2761  movaps  [rbp+90h+var_A0], xmm0
0x1800a2765  movsd   [rbp+90h+var_90], xmm1
0x1800a276a  lea     rax, [rbp+90h+var_100]
0x1800a276e  mov     [rsp+190h+ppv], rax; int
0x1800a2773  lea     r9, [rbp+90h+var_E0]
0x1800a2777  lea     r8, [rbp+90h+var_C0]
0x1800a277b  lea     rdx, [rbp+90h+var_A0]
0x1800a277f  mov     rcx, rsi
0x1800a2782  mov     rax, rdi
0x1800a2785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a278a  mov     edi, eax
0x1800a278c  lea     rcx, [rsp+190h+var_160]; pvarg
0x1800a2791  call    cs:__imp_VariantClear
0x1800a2797  nop
0x1800a2798  lea     rcx, [rsp+190h+var_148]; pvarg
0x1800a279d  call    cs:__imp_VariantClear
0x1800a27a3  nop
0x1800a27a4  lea     rcx, [rsp+190h+var_130]; pvarg
0x1800a27a9  call    cs:__imp_VariantClear
0x1800a27af  nop
0x1800a27b0  lea     rcx, [rsp+190h+pvarg]; pvarg
0x1800a27b5  call    cs:__imp_VariantClear
0x1800a27bb  test    edi, edi
0x1800a27bd  jns     short loc_1800A27C9
0x1800a27bf  mov     edx, 320h
0x1800a27c4  jmp     loc_1800A26BA
0x1800a27c9  mov     [rbp+90h+arg_10], 0
0x1800a27d4  lea     rcx, [rbp+90h+arg_10]
0x1800a27db  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a27e0  lea     r9, [rbp+90h+arg_10]
0x1800a27e7  xor     r8d, r8d
0x1800a27ea  mov     rdx, r14
0x1800a27ed  mov     rcx, [rbp+90h+arg_8]
0x1800a27f4  call    _anonymous_namespace___GetTaskFolder
0x1800a27f9  mov     edi, eax
0x1800a27fb  test    eax, eax
0x1800a27fd  js      short loc_1800A2872
0x1800a27ff  lea     rdx, aSyncStatusPoll; "Sync Status Poll"
0x1800a2806  lea     rcx, [rbp+90h+arg_18]
0x1800a280d  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x1800a2812  nop
0x1800a2813  mov     rdx, [rbp+90h+arg_18]
0x1800a281a  test    rdx, rdx
0x1800a281d  jnz     short loc_1800A284E
0x1800a281f  mov     rcx, [rbp+98h]; this
0x1800a2826  mov     edi, 8007000Eh
0x1800a282b  mov     r9d, edi; char *
0x1800a282e  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a2835  mov     edx, 327h; void *
0x1800a283a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a283f  nop
0x1800a2840  lea     rcx, [rbp+90h+arg_18]
0x1800a2847  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a284c  jmp     short loc_1800A28A1
0x1800a284e  mov     rcx, [rbp+90h+arg_10]
0x1800a2855  mov     rax, [rcx]
0x1800a2858  xor     r8d, r8d
0x1800a285b  mov     rax, [rax+78h]
0x1800a285f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2864  mov     edi, eax
0x1800a2866  lea     rcx, [rbp+90h+arg_18]
0x1800a286d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a2872  lea     eax, [rdi+7FF8FFFEh]
0x1800a2878  cmp     eax, 1
0x1800a287b  ja      short loc_1800A2881
0x1800a287d  xor     edi, edi
0x1800a287f  jmp     short loc_1800A28A1
0x1800a2881  test    edi, edi
0x1800a2883  jns     short loc_1800A28A1
0x1800a2885  mov     rcx, [rbp+98h]; this
0x1800a288c  mov     r9d, edi; char *
0x1800a288f  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a2896  mov     edx, 32Dh; void *
0x1800a289b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a28a0  nop
0x1800a28a1  lea     rcx, [rbp+90h+arg_10]
0x1800a28a8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a28ad  nop
0x1800a28ae  lea     rcx, [rbp+90h+arg_8]
0x1800a28b5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a28ba  nop
0x1800a28bb  test    ebx, ebx
0x1800a28bd  js      short loc_1800A28C5
0x1800a28bf  call    cs:__imp_RoUninitialize
0x1800a28c5  mov     eax, edi
0x1800a28c7  lea     r11, [rsp+190h+var_20]
0x1800a28cf  movaps  xmm6, xmmword ptr [r11-10h]
0x1800a28d4  movaps  xmm7, xmmword ptr [r11-20h]
0x1800a28d9  movaps  xmm8, xmmword ptr [r11-30h]
0x1800a28de  movaps  xmm9, xmmword ptr [r11-40h]
0x1800a28e3  movaps  xmm10, xmmword ptr [r11-50h]
0x1800a28e8  movaps  xmm11, xmmword ptr [r11-60h]
0x1800a28ed  mov     rsp, r11
0x1800a28f0  pop     r14
0x1800a28f2  pop     rdi
0x1800a28f3  pop     rsi
0x1800a28f4  pop     rbx
0x1800a28f5  pop     rbp
0x1800a28f6  retn
```
