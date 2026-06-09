# DisableScheduledTask(void)

- ea: `0x1800149bc`
- end: `0x180014d96`
- name: `?DisableScheduledTask@@YAJXZ`
- size: `986`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001fd50`

## callees

- `0x18000ab14`
- `0x1800149bc`
- `0x18001a848`
- `0x1800232fc`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800149f0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800149f0`
- `OLEAUT32!__imp_SysFreeString` at `0x180014b9c`
- `OLEAUT32!__imp_SysFreeString` at `0x180014c3c`
- `OLEAUT32!__imp_SysFreeString` at `0x180014c62`
- `OLEAUT32!__imp_SysFreeString` at `0x180014cd9`
- `OLEAUT32!__imp_SysFreeString` at `0x180014cff`
- `OLEAUT32!__imp_SysFreeString` at `0x180014d47`
- `OLEAUT32!__imp_SysFreeString` at `0x180014d6d`
- `OLEAUT32!__imp_SysFreeString` at `0x180014b9c`
- `OLEAUT32!__imp_SysFreeString` at `0x180014c3c`
- `OLEAUT32!__imp_SysFreeString` at `0x180014c62`
- `OLEAUT32!__imp_SysFreeString` at `0x180014cd9`
- `OLEAUT32!__imp_SysFreeString` at `0x180014cff`
- `OLEAUT32!__imp_SysFreeString` at `0x180014d47`
- `OLEAUT32!__imp_SysFreeString` at `0x180014d6d`
- `OLEAUT32!__imp_VariantClear` at `0x180014ac4`
- `OLEAUT32!__imp_VariantClear` at `0x180014ad0`
- `OLEAUT32!__imp_VariantClear` at `0x180014adc`
- `OLEAUT32!__imp_VariantClear` at `0x180014ae7`
- `OLEAUT32!__imp_VariantClear` at `0x180014ac4`
- `OLEAUT32!__imp_VariantClear` at `0x180014ad0`
- `OLEAUT32!__imp_VariantClear` at `0x180014adc`
- `OLEAUT32!__imp_VariantClear` at `0x180014ae7`

## string_xrefs

- `0x180014a03`: `pcshell\shell\aix\shellconfigtask\lib\recallconfigtaskhandler.cpp`
- `0x180014af8`: `pcshell\shell\aix\shellconfigtask\lib\recallconfigtaskhandler.cpp`
- `0x180014b6b`: `pcshell\shell\aix\shellconfigtask\lib\recallconfigtaskhandler.cpp`
- `0x180014c0a`: `pcshell\shell\aix\shellconfigtask\lib\recallconfigtaskhandler.cpp`
- `0x180014ca7`: `pcshell\shell\aix\shellconfigtask\lib\recallconfigtaskhandler.cpp`
- `0x180014bbe`: `InitialConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 DisableScheduledTask(void)
{
  HRESULT v0; // eax
  unsigned int v1; // ebx
  __int64 (__fastcall *v3)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *); // r10
  __int64 v4; // rax
  int v5; // eax
  __int64 v6; // rax
  int v7; // eax
  int v8; // eax
  int ppv; // [rsp+20h] [rbp-E0h]
  BSTR v10; // [rsp+30h] [rbp-D0h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG v12; // [rsp+50h] [rbp-B0h] BYREF
  VARIANTARG v13; // [rsp+68h] [rbp-98h] BYREF
  VARIANTARG v14; // [rsp+80h] [rbp-80h] BYREF
  VARIANTARG v15; // [rsp+A0h] [rbp-60h] BYREF
  VARIANTARG v16; // [rsp+C0h] [rbp-40h] BYREF
  VARIANTARG v17; // [rsp+E0h] [rbp-20h] BYREF
  VARIANTARG v18; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]
  LPVOID v20; // [rsp+140h] [rbp+40h] BYREF
  __int64 *v21; // [rsp+148h] [rbp+48h] BYREF
  __int64 v22; // [rsp+150h] [rbp+50h] BYREF
  BSTR bstrString; // [rsp+158h] [rbp+58h] BYREF

  v20 = 0;
  v0 = CoCreateInstance(
         &GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd,
         0,
         1u,
         &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,
         &v20);
  v1 = v0;
  if ( v0 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C,
      (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\recallconfigtaskhandler.cpp",
      (const char *)(unsigned int)v0,
      ppv);
    if ( v20 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
    return v1;
  }
  v3 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *))(*(_QWORD *)v20 + 80LL);
  v14.vt = 0;
  v13.vt = 0;
  v12.vt = 0;
  pvarg.vt = 0;
  v15 = v14;
  v16 = v13;
  v17 = v12;
  v18 = pvarg;
  v1 = v3(v20, &v18, &v17, &v16);
  VariantClear(&pvarg);
  VariantClear(&v12);
  VariantClear(&v13);
  VariantClear(&v14);
  if ( (v1 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\recallconfigtaskhandler.cpp",
      (const char *)v1,
      (int)&v15);
    if ( v20 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
    return v1;
  }
  wil::make_bstr(&bstrString, L"\\Microsoft\\Windows\\WindowsAI\\Recall");
  v21 = 0;
  v4 = *(_QWORD *)v20;
  v21 = 0;
  v5 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 **))(v4 + 56))(v20, bstrString, &v21);
  v1 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21,
      (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\recallconfigtaskhandler.cpp",
      (const char *)(unsigned int)v5,
      (int)&v15);
    if ( v21 )
      (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
    if ( bstrString )
      SysFreeString(bstrString);
    if ( v20 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
    return v1;
  }
  wil::make_bstr(&v10, L"InitialConfiguration");
  v22 = 0;
  v6 = *v21;
  v22 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *, BSTR, __int64 *))(v6 + 104))(v21, v10, &v22);
  v1 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25,
      (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\recallconfigtaskhandler.cpp",
      (const char *)(unsigned int)v7,
      (int)&v15);
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    if ( v10 )
      SysFreeString(v10);
    if ( v21 )
      (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
    if ( bstrString )
      SysFreeString(bstrString);
    if ( v20 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
    return v1;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v22 + 88LL))(v22, 0);
  v1 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\recallconfigtaskhandler.cpp",
      (const char *)(unsigned int)v8,
      (int)&v15);
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    if ( v10 )
      SysFreeString(v10);
    if ( v21 )
      (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
    if ( bstrString )
      SysFreeString(bstrString);
    if ( v20 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
    return v1;
  }
  AIXTelemetry::InitialTask_Disabled();
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  if ( v10 )
    SysFreeString(v10);
  if ( v21 )
    (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v20 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
  return 0;
}

```

## disassembly

```asm
0x1800149bc  push    rbp
0x1800149be  push    rbx
0x1800149bf  lea     rbp, [rsp-28h]
0x1800149c4  sub     rsp, 128h
0x1800149cb  mov     [rbp+30h+arg_0], 0
0x1800149d3  lea     rax, [rbp+30h+arg_0]
0x1800149d7  mov     qword ptr [rsp+130h+ppv], rax; int
0x1800149dc  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1800149e3  xor     edx, edx; pUnkOuter
0x1800149e5  lea     r8d, [rdx+1]; dwClsContext
0x1800149e9  lea     rcx, _GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd; rclsid
0x1800149f0  call    cs:__imp_CoCreateInstance
0x1800149f6  mov     ebx, eax
0x1800149f8  test    eax, eax
0x1800149fa  jns     short loc_180014A32
0x1800149fc  mov     rcx, [rbp+38h]; this
0x180014a00  mov     r9d, eax; char *
0x180014a03  lea     r8, aPcshellShellAi; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x180014a0a  mov     edx, 1Ch; void *
0x180014a0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014a14  nop
0x180014a15  mov     rcx, [rbp+30h+arg_0]
0x180014a19  test    rcx, rcx
0x180014a1c  jz      short loc_180014A2B
0x180014a1e  mov     rax, [rcx]
0x180014a21  mov     rax, [rax+10h]
0x180014a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a2a  nop
0x180014a2b  mov     eax, ebx
0x180014a2d  jmp     loc_180014D8C
0x180014a32  mov     rcx, [rbp+30h+arg_0]
0x180014a36  mov     rax, [rcx]
0x180014a39  mov     r10, [rax+50h]
0x180014a3d  xor     eax, eax
0x180014a3f  mov     word ptr [rbp+30h+var_B0], ax
0x180014a43  mov     word ptr [rsp+130h+var_C8], ax
0x180014a48  mov     word ptr [rsp+130h+var_E0], ax
0x180014a4d  mov     word ptr [rsp+130h+pvarg], ax
0x180014a52  movups  xmm0, xmmword ptr [rbp+30h+var_B0]
0x180014a56  movaps  xmmword ptr [rbp+30h+var_90], xmm0
0x180014a5a  movsd   xmm1, qword ptr [rbp+30h+var_B0+10h]
0x180014a5f  movsd   [rbp+30h+var_80], xmm1
0x180014a64  movups  xmm0, xmmword ptr [rsp+130h+var_C8]
0x180014a69  movaps  [rbp+30h+var_70], xmm0
0x180014a6d  movsd   xmm1, qword ptr [rsp+130h+var_C8+10h]
0x180014a73  movsd   [rbp+30h+var_60], xmm1
0x180014a78  movups  xmm0, xmmword ptr [rsp+130h+var_E0]
0x180014a7d  movaps  [rbp+30h+var_50], xmm0
0x180014a81  movsd   xmm1, qword ptr [rsp+130h+var_E0+10h]
0x180014a87  movsd   [rbp+30h+var_40], xmm1
0x180014a8c  movups  xmm0, xmmword ptr [rsp+130h+pvarg]
0x180014a91  movaps  [rbp+30h+var_30], xmm0
0x180014a95  movsd   xmm1, qword ptr [rsp+130h+pvarg+10h]
0x180014a9b  movsd   [rbp+30h+var_20], xmm1
0x180014aa0  lea     rax, [rbp+30h+var_90]
0x180014aa4  mov     qword ptr [rsp+130h+ppv], rax; int
0x180014aa9  lea     r9, [rbp+30h+var_70]
0x180014aad  lea     r8, [rbp+30h+var_50]
0x180014ab1  lea     rdx, [rbp+30h+var_30]
0x180014ab5  mov     rax, r10
0x180014ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014abd  mov     ebx, eax
0x180014abf  lea     rcx, [rsp+130h+pvarg]; pvarg
0x180014ac4  call    cs:__imp_VariantClear
0x180014aca  nop
0x180014acb  lea     rcx, [rsp+130h+var_E0]; pvarg
0x180014ad0  call    cs:__imp_VariantClear
0x180014ad6  nop
0x180014ad7  lea     rcx, [rsp+130h+var_C8]; pvarg
0x180014adc  call    cs:__imp_VariantClear
0x180014ae2  nop
0x180014ae3  lea     rcx, [rbp+30h+var_B0]; pvarg
0x180014ae7  call    cs:__imp_VariantClear
0x180014aed  test    ebx, ebx
0x180014aef  jns     short loc_180014B25
0x180014af1  mov     rcx, [rbp+38h]; this
0x180014af5  mov     r9d, ebx; char *
0x180014af8  lea     r8, aPcshellShellAi; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x180014aff  mov     edx, 1Dh; void *
0x180014b04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014b09  nop
0x180014b0a  mov     rcx, [rbp+30h+arg_0]
0x180014b0e  test    rcx, rcx
0x180014b11  jz      short loc_180014B20
0x180014b13  mov     rax, [rcx]
0x180014b16  mov     rax, [rax+10h]
0x180014b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b1f  nop
0x180014b20  jmp     loc_180014A2B
0x180014b25  lea     rdx, aMicrosoftWindo_7; "\\Microsoft\\Windows\\WindowsAI\\Recall"
0x180014b2c  lea     rcx, [rbp+30h+bstrString]
0x180014b30  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180014b35  nop
0x180014b36  mov     [rbp+30h+arg_8], 0
0x180014b3e  mov     rcx, [rbp+30h+arg_0]
0x180014b42  mov     rax, [rcx]
0x180014b45  mov     [rbp+30h+arg_8], 0
0x180014b4d  lea     r8, [rbp+30h+arg_8]
0x180014b51  mov     rdx, [rbp+30h+bstrString]
0x180014b55  mov     rax, [rax+38h]
0x180014b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b5e  mov     ebx, eax
0x180014b60  test    eax, eax
0x180014b62  jns     short loc_180014BBE
0x180014b64  mov     rcx, [rbp+38h]; this
0x180014b68  mov     r9d, eax; char *
0x180014b6b  lea     r8, aPcshellShellAi; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x180014b72  mov     edx, 21h ; '!'; void *
0x180014b77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014b7c  nop
0x180014b7d  mov     rcx, [rbp+30h+arg_8]
0x180014b81  test    rcx, rcx
0x180014b84  jz      short loc_180014B93
0x180014b86  mov     rax, [rcx]
0x180014b89  mov     rax, [rax+10h]
0x180014b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b92  nop
0x180014b93  mov     rcx, [rbp+30h+bstrString]; bstrString
0x180014b97  test    rcx, rcx
0x180014b9a  jz      short loc_180014BA3
0x180014b9c  call    cs:__imp_SysFreeString
0x180014ba2  nop
0x180014ba3  mov     rcx, [rbp+30h+arg_0]
0x180014ba7  test    rcx, rcx
0x180014baa  jz      short loc_180014BB9
0x180014bac  mov     rax, [rcx]
0x180014baf  mov     rax, [rax+10h]
0x180014bb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bb8  nop
0x180014bb9  jmp     loc_180014A2B
0x180014bbe  lea     rdx, aInitialconfigu; "InitialConfiguration"
0x180014bc5  lea     rcx, [rsp+130h+var_100]
0x180014bca  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180014bcf  nop
0x180014bd0  mov     [rbp+30h+arg_10], 0
0x180014bd8  mov     rcx, [rbp+30h+arg_8]
0x180014bdc  mov     rax, [rcx]
0x180014bdf  mov     [rbp+30h+arg_10], 0
0x180014be7  lea     r8, [rbp+30h+arg_10]
0x180014beb  mov     rdx, [rsp+130h+var_100]
0x180014bf0  mov     rax, [rax+68h]
0x180014bf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bf9  mov     ebx, eax
0x180014bfb  test    eax, eax
0x180014bfd  jns     loc_180014C84
0x180014c03  mov     rcx, [rbp+38h]; this
0x180014c07  mov     r9d, eax; char *
0x180014c0a  lea     r8, aPcshellShellAi; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x180014c11  mov     edx, 25h ; '%'; void *
0x180014c16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014c1b  nop
0x180014c1c  mov     rcx, [rbp+30h+arg_10]
0x180014c20  test    rcx, rcx
0x180014c23  jz      short loc_180014C32
0x180014c25  mov     rax, [rcx]
0x180014c28  mov     rax, [rax+10h]
0x180014c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c31  nop
0x180014c32  mov     rcx, [rsp+130h+var_100]; bstrString
0x180014c37  test    rcx, rcx
0x180014c3a  jz      short loc_180014C43
0x180014c3c  call    cs:__imp_SysFreeString
0x180014c42  nop
0x180014c43  mov     rcx, [rbp+30h+arg_8]
0x180014c47  test    rcx, rcx
0x180014c4a  jz      short loc_180014C59
0x180014c4c  mov     rax, [rcx]
0x180014c4f  mov     rax, [rax+10h]
0x180014c53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c58  nop
0x180014c59  mov     rcx, [rbp+30h+bstrString]; bstrString
0x180014c5d  test    rcx, rcx
0x180014c60  jz      short loc_180014C69
0x180014c62  call    cs:__imp_SysFreeString
0x180014c68  nop
0x180014c69  mov     rcx, [rbp+30h+arg_0]
0x180014c6d  test    rcx, rcx
0x180014c70  jz      short loc_180014C7F
0x180014c72  mov     rax, [rcx]
0x180014c75  mov     rax, [rax+10h]
0x180014c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c7e  nop
0x180014c7f  jmp     loc_180014A2B
0x180014c84  mov     rcx, [rbp+30h+arg_10]
0x180014c88  mov     rax, [rcx]
0x180014c8b  xor     edx, edx
0x180014c8d  mov     rax, [rax+58h]
0x180014c91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c96  mov     ebx, eax
0x180014c98  test    eax, eax
0x180014c9a  jns     loc_180014D21
0x180014ca0  mov     rcx, [rbp+38h]; this
0x180014ca4  mov     r9d, eax; char *
0x180014ca7  lea     r8, aPcshellShellAi; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x180014cae  mov     edx, 26h ; '&'; void *
0x180014cb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014cb8  nop
0x180014cb9  mov     rcx, [rbp+30h+arg_10]
0x180014cbd  test    rcx, rcx
0x180014cc0  jz      short loc_180014CCF
0x180014cc2  mov     rax, [rcx]
0x180014cc5  mov     rax, [rax+10h]
0x180014cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cce  nop
0x180014ccf  mov     rcx, [rsp+130h+var_100]; bstrString
0x180014cd4  test    rcx, rcx
0x180014cd7  jz      short loc_180014CE0
0x180014cd9  call    cs:__imp_SysFreeString
0x180014cdf  nop
0x180014ce0  mov     rcx, [rbp+30h+arg_8]
0x180014ce4  test    rcx, rcx
0x180014ce7  jz      short loc_180014CF6
0x180014ce9  mov     rax, [rcx]
0x180014cec  mov     rax, [rax+10h]
0x180014cf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cf5  nop
0x180014cf6  mov     rcx, [rbp+30h+bstrString]; bstrString
0x180014cfa  test    rcx, rcx
0x180014cfd  jz      short loc_180014D06
0x180014cff  call    cs:__imp_SysFreeString
0x180014d05  nop
0x180014d06  mov     rcx, [rbp+30h+arg_0]
0x180014d0a  test    rcx, rcx
0x180014d0d  jz      short loc_180014D1C
0x180014d0f  mov     rax, [rcx]
0x180014d12  mov     rax, [rax+10h]
0x180014d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d1b  nop
0x180014d1c  jmp     loc_180014A2B
0x180014d21  call    ?InitialTask_Disabled@AIXTelemetry@@SAXXZ; AIXTelemetry::InitialTask_Disabled(void)
0x180014d26  nop
0x180014d27  mov     rcx, [rbp+30h+arg_10]
0x180014d2b  test    rcx, rcx
0x180014d2e  jz      short loc_180014D3D
0x180014d30  mov     rax, [rcx]
0x180014d33  mov     rax, [rax+10h]
0x180014d37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d3c  nop
0x180014d3d  mov     rcx, [rsp+130h+var_100]; bstrString
0x180014d42  test    rcx, rcx
0x180014d45  jz      short loc_180014D4E
0x180014d47  call    cs:__imp_SysFreeString
0x180014d4d  nop
0x180014d4e  mov     rcx, [rbp+30h+arg_8]
0x180014d52  test    rcx, rcx
0x180014d55  jz      short loc_180014D64
0x180014d57  mov     rax, [rcx]
0x180014d5a  mov     rax, [rax+10h]
0x180014d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d63  nop
0x180014d64  mov     rcx, [rbp+30h+bstrString]; bstrString
0x180014d68  test    rcx, rcx
0x180014d6b  jz      short loc_180014D74
0x180014d6d  call    cs:__imp_SysFreeString
0x180014d73  nop
0x180014d74  mov     rcx, [rbp+30h+arg_0]
0x180014d78  test    rcx, rcx
0x180014d7b  jz      short loc_180014D8A
0x180014d7d  mov     rax, [rcx]
0x180014d80  mov     rax, [rax+10h]
0x180014d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d89  nop
0x180014d8a  xor     eax, eax
0x180014d8c  add     rsp, 128h
0x180014d93  pop     rbx
0x180014d94  pop     rbp
0x180014d95  retn
```
