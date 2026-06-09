# GetTaskSchedulerFolder(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,wil::com_ptr_t<ITaskFolder,wil::err_returncode_policy> &)

- ea: `0x18000c9e0`
- end: `0x18000cc91`
- name: `?GetTaskSchedulerFolder@@YAJV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV?$com_ptr_t@UITaskFolder@@Uerr_returncode_policy@wil@@@2@@Z`
- size: `689`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800140d4`
- `0x1800142a4`
- `0x1800143e8`

## callees

- `0x180007804`
- `0x18000c9e0`
- `0x180056500`
- `0x18005c5e0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000ca83`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cc65`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ca83`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cc65`
- `OLEAUT32!__imp_VariantInit` at `0x18000ca9b`
- `OLEAUT32!__imp_VariantInit` at `0x18000caba`
- `OLEAUT32!__imp_VariantInit` at `0x18000cad9`
- `OLEAUT32!__imp_VariantInit` at `0x18000caf7`
- `OLEAUT32!__imp_VariantInit` at `0x18000ca9b`
- `OLEAUT32!__imp_VariantInit` at `0x18000caba`
- `OLEAUT32!__imp_VariantInit` at `0x18000cad9`
- `OLEAUT32!__imp_VariantInit` at `0x18000caf7`
- `OLEAUT32!__imp_VariantClear` at `0x18000cb76`
- `OLEAUT32!__imp_VariantClear` at `0x18000cb81`
- `OLEAUT32!__imp_VariantClear` at `0x18000cb8c`
- `OLEAUT32!__imp_VariantClear` at `0x18000cb97`
- `OLEAUT32!__imp_VariantClear` at `0x18000cb76`
- `OLEAUT32!__imp_VariantClear` at `0x18000cb81`
- `OLEAUT32!__imp_VariantClear` at `0x18000cb8c`
- `OLEAUT32!__imp_VariantClear` at `0x18000cb97`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ca37`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ca37`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall GetTaskSchedulerFolder(BSTR *a1, __int64 *a2)
{
  LPVOID v4; // rbx
  int v5; // ebx
  __int64 (__fastcall *v7)(LPVOID, VARIANTARG *, __int128 *, __int128 *); // rdi
  LPVOID v8; // rbx
  __int64 (__fastcall *v9)(LPVOID, BSTR, __int64 *); // rdi
  __int64 v10; // rcx
  int v11; // eax
  int ppv; // [rsp+20h] [rbp-E0h]
  IRecordInfo *pRecInfo; // [rsp+30h] [rbp-D0h]
  IRecordInfo *v14; // [rsp+38h] [rbp-C8h]
  IRecordInfo *v15; // [rsp+40h] [rbp-C0h]
  int v16[4]; // [rsp+50h] [rbp-B0h] BYREF
  IRecordInfo *v17; // [rsp+60h] [rbp-A0h]
  __int128 v18; // [rsp+70h] [rbp-90h] BYREF
  IRecordInfo *v19; // [rsp+80h] [rbp-80h]
  __int128 v20; // [rsp+90h] [rbp-70h] BYREF
  IRecordInfo *v21; // [rsp+A0h] [rbp-60h]
  VARIANTARG v22; // [rsp+B0h] [rbp-50h] BYREF
  VARIANTARG v23; // [rsp+C8h] [rbp-38h] BYREF
  VARIANTARG v24; // [rsp+E0h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+F8h] [rbp-8h] BYREF
  BSTR *v26; // [rsp+110h] [rbp+10h]
  VARIANTARG v27; // [rsp+120h] [rbp+20h] BYREF
  LPVOID v28; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v26 = a1;
  v28 = 0;
  CoCreateInstance(&GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &v28);
  v4 = v28;
  if ( !v28 )
  {
    v5 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\ClientImpl.cpp",
      (const char *)0x80004003LL,
      ppv);
    if ( v28 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v28 + 16LL))(v28);
LABEL_4:
    if ( *a1 )
      SysFreeString(*a1);
    return (unsigned int)v5;
  }
  v7 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)v28 + 80LL);
  VariantInit(&pvarg);
  *(_OWORD *)v16 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v24);
  v18 = *(_OWORD *)&v24.vt;
  v14 = v24.pRecInfo;
  VariantInit(&v23);
  v20 = *(_OWORD *)&v23.vt;
  v15 = v23.pRecInfo;
  VariantInit(&v22);
  v17 = pRecInfo;
  v19 = v14;
  v21 = v15;
  v27 = v22;
  v5 = v7(v4, &v27, &v20, &v18);
  VariantClear(&v22);
  VariantClear(&v23);
  VariantClear(&v24);
  VariantClear(&pvarg);
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\ClientImpl.cpp",
      (const char *)(unsigned int)v5,
      (int)v16);
    if ( v28 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v28 + 16LL))(v28);
    goto LABEL_4;
  }
  v8 = v28;
  v9 = *(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)v28 + 56LL);
  v10 = *a2;
  *a2 = 0;
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  v11 = v9(v8, *a1, a2);
  v5 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\ClientImpl.cpp",
      (const char *)(unsigned int)v11,
      (int)v16);
    if ( v28 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v28 + 16LL))(v28);
    goto LABEL_4;
  }
  if ( v28 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v28 + 16LL))(v28);
  if ( *a1 )
    SysFreeString(*a1);
  return 0;
}

```

## disassembly

```asm
0x18000c9e0  mov     [rsp-8+arg_10], rbx
0x18000c9e5  mov     [rsp-8+arg_18], rsi
0x18000c9ea  push    rbp
0x18000c9eb  push    rdi
0x18000c9ec  push    r14
0x18000c9ee  lea     rbp, [rsp-50h]
0x18000c9f3  sub     rsp, 150h
0x18000c9fa  mov     rax, cs:__security_cookie
0x18000ca01  xor     rax, rsp
0x18000ca04  mov     [rbp+60h+var_18], rax
0x18000ca08  mov     r14, rdx
0x18000ca0b  mov     rsi, rcx
0x18000ca0e  mov     [rbp+60h+var_50], rcx
0x18000ca12  mov     [rbp+60h+var_20], 0
0x18000ca1a  lea     rax, [rbp+60h+var_20]
0x18000ca1e  mov     qword ptr [rsp+160h+ppv], rax; int
0x18000ca23  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x18000ca2a  xor     edx, edx; pUnkOuter
0x18000ca2c  lea     r8d, [rdx+1]; dwClsContext
0x18000ca30  lea     rcx, _GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd; rclsid
0x18000ca37  call    cs:__imp_CoCreateInstance
0x18000ca3d  nop
0x18000ca3e  mov     rbx, [rbp+60h+var_20]
0x18000ca42  test    rbx, rbx
0x18000ca45  jnz     short loc_18000CA90
0x18000ca47  mov     rcx, [rbp+68h]; this
0x18000ca4b  mov     ebx, 80004003h
0x18000ca50  mov     r9d, ebx; char *
0x18000ca53  lea     r8, aCW1SSrcOrchest_3; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x18000ca5a  mov     edx, 21h ; '!'; void *
0x18000ca5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ca64  nop
0x18000ca65  mov     rcx, [rbp+60h+var_20]
0x18000ca69  test    rcx, rcx
0x18000ca6c  jz      short loc_18000CA7B
0x18000ca6e  mov     rax, [rcx]
0x18000ca71  mov     rax, [rax+10h]
0x18000ca75  call    _guard_dispatch_icall
0x18000ca7a  nop
0x18000ca7b  mov     rcx, [rsi]; bstrString
0x18000ca7e  test    rcx, rcx
0x18000ca81  jz      short loc_18000CA89
0x18000ca83  call    cs:__imp_SysFreeString
0x18000ca89  mov     eax, ebx
0x18000ca8b  jmp     loc_18000CC6D
0x18000ca90  mov     rax, [rbx]
0x18000ca93  mov     rdi, [rax+50h]
0x18000ca97  lea     rcx, [rbp+60h+pvarg]; pvarg
0x18000ca9b  call    cs:__imp_VariantInit
0x18000caa1  nop
0x18000caa2  movups  xmm0, xmmword ptr [rbp+60h+pvarg]
0x18000caa6  movups  xmmword ptr [rsp+160h+var_110], xmm0
0x18000caab  movsd   xmm0, qword ptr [rbp+60h+pvarg+10h]
0x18000cab0  movsd   [rsp+160h+var_130], xmm0
0x18000cab6  lea     rcx, [rbp+60h+var_80]; pvarg
0x18000caba  call    cs:__imp_VariantInit
0x18000cac0  nop
0x18000cac1  movups  xmm0, xmmword ptr [rbp+60h+var_80]
0x18000cac5  movups  [rsp+160h+var_F0], xmm0
0x18000caca  movsd   xmm0, qword ptr [rbp+60h+var_80+10h]
0x18000cacf  movsd   [rsp+160h+var_128], xmm0
0x18000cad5  lea     rcx, [rbp+60h+var_98]; pvarg
0x18000cad9  call    cs:__imp_VariantInit
0x18000cadf  nop
0x18000cae0  movups  xmm0, xmmword ptr [rbp+60h+var_98]
0x18000cae4  movups  [rbp+60h+var_D0], xmm0
0x18000cae8  movsd   xmm0, qword ptr [rbp+60h+var_98+10h]
0x18000caed  movsd   [rsp+160h+var_120], xmm0
0x18000caf3  lea     rcx, [rbp+60h+var_B0]; pvarg
0x18000caf7  call    cs:__imp_VariantInit
0x18000cafd  nop
0x18000cafe  movups  xmm0, xmmword ptr [rsp+160h+var_110]
0x18000cb03  movaps  xmmword ptr [rsp+160h+var_110], xmm0
0x18000cb08  movsd   xmm0, [rsp+160h+var_130]
0x18000cb0e  movsd   [rsp+160h+var_100], xmm0
0x18000cb14  movups  xmm0, [rsp+160h+var_F0]
0x18000cb19  movaps  [rsp+160h+var_F0], xmm0
0x18000cb1e  movsd   xmm0, [rsp+160h+var_128]
0x18000cb24  movsd   [rbp+60h+var_E0], xmm0
0x18000cb29  movups  xmm0, [rbp+60h+var_D0]
0x18000cb2d  movaps  [rbp+60h+var_D0], xmm0
0x18000cb31  movsd   xmm0, [rsp+160h+var_120]
0x18000cb37  movsd   [rbp+60h+var_C0], xmm0
0x18000cb3c  movups  xmm0, xmmword ptr [rbp+60h+var_B0]
0x18000cb40  movaps  [rbp+60h+var_40], xmm0
0x18000cb44  movsd   xmm1, qword ptr [rbp+60h+var_B0+10h]
0x18000cb49  movsd   [rbp+60h+var_30], xmm1
0x18000cb4e  lea     rax, [rsp+160h+var_110]
0x18000cb53  mov     qword ptr [rsp+160h+ppv], rax; int
0x18000cb58  lea     r9, [rsp+160h+var_F0]
0x18000cb5d  lea     r8, [rbp+60h+var_D0]
0x18000cb61  lea     rdx, [rbp+60h+var_40]
0x18000cb65  mov     rcx, rbx
0x18000cb68  mov     rax, rdi
0x18000cb6b  call    _guard_dispatch_icall
0x18000cb70  mov     ebx, eax
0x18000cb72  lea     rcx, [rbp+60h+var_B0]; pvarg
0x18000cb76  call    cs:__imp_VariantClear
0x18000cb7c  nop
0x18000cb7d  lea     rcx, [rbp+60h+var_98]; pvarg
0x18000cb81  call    cs:__imp_VariantClear
0x18000cb87  nop
0x18000cb88  lea     rcx, [rbp+60h+var_80]; pvarg
0x18000cb8c  call    cs:__imp_VariantClear
0x18000cb92  nop
0x18000cb93  lea     rcx, [rbp+60h+pvarg]; pvarg
0x18000cb97  call    cs:__imp_VariantClear
0x18000cb9d  test    ebx, ebx
0x18000cb9f  jns     short loc_18000CBD5
0x18000cba1  mov     rcx, [rbp+68h]; this
0x18000cba5  mov     r9d, ebx; char *
0x18000cba8  lea     r8, aCW1SSrcOrchest_3; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x18000cbaf  mov     edx, 22h ; '"'; void *
0x18000cbb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cbb9  nop
0x18000cbba  mov     rcx, [rbp+60h+var_20]
0x18000cbbe  test    rcx, rcx
0x18000cbc1  jz      short loc_18000CBD0
0x18000cbc3  mov     rax, [rcx]
0x18000cbc6  mov     rax, [rax+10h]
0x18000cbca  call    _guard_dispatch_icall
0x18000cbcf  nop
0x18000cbd0  jmp     loc_18000CA7B
0x18000cbd5  mov     rbx, [rbp+60h+var_20]
0x18000cbd9  mov     rax, [rbx]
0x18000cbdc  mov     rdi, [rax+38h]
0x18000cbe0  mov     rcx, [r14]
0x18000cbe3  mov     qword ptr [r14], 0
0x18000cbea  test    rcx, rcx
0x18000cbed  jz      short loc_18000CBFC
0x18000cbef  mov     rdx, [rcx]
0x18000cbf2  mov     rax, [rdx+10h]
0x18000cbf6  call    _guard_dispatch_icall
0x18000cbfb  nop
0x18000cbfc  mov     r8, r14
0x18000cbff  mov     rdx, [rsi]
0x18000cc02  mov     rcx, rbx
0x18000cc05  mov     rax, rdi
0x18000cc08  call    _guard_dispatch_icall
0x18000cc0d  mov     ebx, eax
0x18000cc0f  test    eax, eax
0x18000cc11  jns     short loc_18000CC47
0x18000cc13  mov     rcx, [rbp+68h]; this
0x18000cc17  mov     r9d, eax; char *
0x18000cc1a  lea     r8, aCW1SSrcOrchest_3; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x18000cc21  mov     edx, 23h ; '#'; void *
0x18000cc26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cc2b  nop
0x18000cc2c  mov     rcx, [rbp+60h+var_20]
0x18000cc30  test    rcx, rcx
0x18000cc33  jz      short loc_18000CC42
0x18000cc35  mov     rax, [rcx]
0x18000cc38  mov     rax, [rax+10h]
0x18000cc3c  call    _guard_dispatch_icall
0x18000cc41  nop
0x18000cc42  jmp     loc_18000CA7B
0x18000cc47  mov     rcx, [rbp+60h+var_20]
0x18000cc4b  test    rcx, rcx
0x18000cc4e  jz      short loc_18000CC5D
0x18000cc50  mov     rax, [rcx]
0x18000cc53  mov     rax, [rax+10h]
0x18000cc57  call    _guard_dispatch_icall
0x18000cc5c  nop
0x18000cc5d  mov     rcx, [rsi]; bstrString
0x18000cc60  test    rcx, rcx
0x18000cc63  jz      short loc_18000CC6B
0x18000cc65  call    cs:__imp_SysFreeString
0x18000cc6b  xor     eax, eax
0x18000cc6d  mov     rcx, [rbp+60h+var_18]
0x18000cc71  xor     rcx, rsp; StackCookie
0x18000cc74  call    __security_check_cookie
0x18000cc79  lea     r11, [rsp+160h+var_10]
0x18000cc81  mov     rbx, [r11+30h]
0x18000cc85  mov     rsi, [r11+38h]
0x18000cc89  mov     rsp, r11
0x18000cc8c  pop     r14
0x18000cc8e  pop     rdi
0x18000cc8f  pop     rbp
0x18000cc90  retn
```
