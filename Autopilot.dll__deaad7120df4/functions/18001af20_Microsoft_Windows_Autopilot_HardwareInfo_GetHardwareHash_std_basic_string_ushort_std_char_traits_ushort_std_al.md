# Microsoft::Windows::Autopilot::HardwareInfo::GetHardwareHash(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001af20`
- end: `0x18001b21a`
- name: `?GetHardwareHash@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `762`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800098e7`
- `0x180010764`
- `0x1800192a4`
- `0x18001af20`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001af8b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001af8b`
- `OLEAUT32!__imp_VariantInit` at `0x18001af47`
- `OLEAUT32!__imp_VariantInit` at `0x18001af47`
- `OLEAUT32!__imp_VariantClear` at `0x18001afba`
- `OLEAUT32!__imp_VariantClear` at `0x18001b058`
- `OLEAUT32!__imp_VariantClear` at `0x18001b0cd`
- `OLEAUT32!__imp_VariantClear` at `0x18001b138`
- `OLEAUT32!__imp_VariantClear` at `0x18001b1c9`
- `OLEAUT32!__imp_VariantClear` at `0x18001afba`
- `OLEAUT32!__imp_VariantClear` at `0x18001b058`
- `OLEAUT32!__imp_VariantClear` at `0x18001b0cd`
- `OLEAUT32!__imp_VariantClear` at `0x18001b138`
- `OLEAUT32!__imp_VariantClear` at `0x18001b1c9`

## string_xrefs

- `0x18001afa4`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001b042`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001b0b7`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001b122`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::HardwareInfo::GetHardwareHash(__int64 a1)
{
  LPVOID v2; // rcx
  HRESULT v3; // eax
  unsigned int v4; // edi
  LPVOID v6; // rdi
  __int64 (__fastcall *v7)(LPVOID, const wchar_t *, __int64 *); // rsi
  __int64 v8; // rcx
  int v9; // eax
  int v10; // eax
  __int64 v11; // r8
  BSTR bstrVal; // r9
  unsigned __int64 v13; // rdx
  char *v14; // rdi
  __int64 v15; // rbx
  int ppv; // [rsp+20h] [rbp-30h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  LPVOID v19; // [rsp+78h] [rbp+28h] BYREF
  __int64 v20; // [rsp+80h] [rbp+30h] BYREF

  v20 = 0;
  v19 = 0;
  VariantInit(&pvarg);
  v2 = v19;
  v19 = 0;
  if ( v2 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = CoCreateInstance(
         &GUID_66d0db14_5638_475f_a386_629522d8c461,
         0,
         1u,
         &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
         &v19);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFB,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)v3,
      ppv);
    VariantClear(&pvarg);
    if ( v19 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v19 + 16LL))(v19);
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    return v4;
  }
  v6 = v19;
  v7 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)v19 + 80LL);
  v8 = v20;
  v20 = 0;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  v9 = v7(v6, L"./DevDetail/Ext/DeviceHardwareData", &v20);
  v4 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFC,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)v9,
      ppv);
    VariantClear(&pvarg);
    if ( v19 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v19 + 16LL))(v19);
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    return v4;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v20 + 104LL))(v20, &pvarg);
  v4 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFD,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)v10,
      ppv);
    VariantClear(&pvarg);
    if ( v19 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v19 + 16LL))(v19);
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    return v4;
  }
  if ( pvarg.vt == 8 )
  {
    bstrVal = pvarg.bstrVal;
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)(pvarg.llVal + 2 * v13) );
    if ( v13 > *(_QWORD *)(a1 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)a1,
        v13,
        v11,
        pvarg.bstrVal);
    }
    else
    {
      if ( *(_QWORD *)(a1 + 24) <= 7u )
        v14 = (char *)a1;
      else
        v14 = *(char **)a1;
      *(_QWORD *)(a1 + 16) = v13;
      v15 = 2 * v13;
      memmove_0(v14, bstrVal, 2 * v13);
      *(_WORD *)&v14[v15] = 0;
    }
    VariantClear(&pvarg);
    if ( v19 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v19 + 16LL))(v19);
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFE,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)0x8000FFFFLL,
      ppv);
    VariantClear(&pvarg);
    if ( v19 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v19 + 16LL))(v19);
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x18001af20  mov     [rsp-18h+arg_0], rbx
0x18001af25  mov     [rsp-18h+arg_18], rsi
0x18001af2a  push    rbp
0x18001af2b  push    rdi
0x18001af2c  push    r14
0x18001af2e  mov     rbp, rsp
0x18001af31  sub     rsp, 50h
0x18001af35  mov     rbx, rcx
0x18001af38  xor     r14d, r14d
0x18001af3b  mov     [rbp+arg_10], r14
0x18001af3f  mov     [rbp+arg_8], r14
0x18001af43  lea     rcx, [rbp+pvarg]; pvarg
0x18001af47  call    cs:__imp_VariantInit
0x18001af4e  nop     dword ptr [rax+rax+00h]
0x18001af53  nop
0x18001af54  mov     rcx, [rbp+arg_8]
0x18001af58  mov     [rbp+arg_8], r14
0x18001af5c  test    rcx, rcx
0x18001af5f  jz      short loc_18001AF6E
0x18001af61  mov     rax, [rcx]
0x18001af64  mov     rax, [rax+10h]
0x18001af68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af6d  nop
0x18001af6e  lea     rax, [rbp+arg_8]
0x18001af72  mov     qword ptr [rsp+50h+ppv], rax; int
0x18001af77  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x18001af7e  xor     edx, edx; pUnkOuter
0x18001af80  lea     r8d, [rdx+1]; dwClsContext
0x18001af84  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x18001af8b  call    cs:__imp_CoCreateInstance
0x18001af92  nop     dword ptr [rax+rax+00h]
0x18001af97  mov     edi, eax
0x18001af99  test    eax, eax
0x18001af9b  jns     short loc_18001AFFA
0x18001af9d  mov     rcx, [rbp+18h]; this
0x18001afa1  mov     r9d, eax; char *
0x18001afa4  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001afab  mov     edx, 0FBh; void *
0x18001afb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001afb5  nop
0x18001afb6  lea     rcx, [rbp+pvarg]; pvarg
0x18001afba  call    cs:__imp_VariantClear
0x18001afc1  nop     dword ptr [rax+rax+00h]
0x18001afc6  nop
0x18001afc7  mov     rcx, [rbp+arg_8]
0x18001afcb  test    rcx, rcx
0x18001afce  jz      short loc_18001AFDD
0x18001afd0  mov     rax, [rcx]
0x18001afd3  mov     rax, [rax+10h]
0x18001afd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001afdc  nop
0x18001afdd  mov     rcx, [rbp+arg_10]
0x18001afe1  test    rcx, rcx
0x18001afe4  jz      short loc_18001AFF3
0x18001afe6  mov     rax, [rcx]
0x18001afe9  mov     rax, [rax+10h]
0x18001afed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aff2  nop
0x18001aff3  mov     eax, edi
0x18001aff5  jmp     loc_18001B204
0x18001affa  mov     rdi, [rbp+arg_8]
0x18001affe  mov     rax, [rdi]
0x18001b001  mov     rsi, [rax+50h]
0x18001b005  mov     rcx, [rbp+arg_10]
0x18001b009  mov     [rbp+arg_10], r14
0x18001b00d  test    rcx, rcx
0x18001b010  jz      short loc_18001B01F
0x18001b012  mov     rdx, [rcx]
0x18001b015  mov     rax, [rdx+10h]
0x18001b019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b01e  nop
0x18001b01f  lea     r8, [rbp+arg_10]
0x18001b023  lea     rdx, aDevdetailExtDe; "./DevDetail/Ext/DeviceHardwareData"
0x18001b02a  mov     rcx, rdi
0x18001b02d  mov     rax, rsi
0x18001b030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b035  mov     edi, eax
0x18001b037  test    eax, eax
0x18001b039  jns     short loc_18001B096
0x18001b03b  mov     rcx, [rbp+18h]; this
0x18001b03f  mov     r9d, eax; char *
0x18001b042  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001b049  mov     edx, 0FCh; void *
0x18001b04e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b053  nop
0x18001b054  lea     rcx, [rbp+pvarg]; pvarg
0x18001b058  call    cs:__imp_VariantClear
0x18001b05f  nop     dword ptr [rax+rax+00h]
0x18001b064  nop
0x18001b065  mov     rcx, [rbp+arg_8]
0x18001b069  test    rcx, rcx
0x18001b06c  jz      short loc_18001B07B
0x18001b06e  mov     rax, [rcx]
0x18001b071  mov     rax, [rax+10h]
0x18001b075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b07a  nop
0x18001b07b  mov     rcx, [rbp+arg_10]
0x18001b07f  test    rcx, rcx
0x18001b082  jz      short loc_18001B091
0x18001b084  mov     rax, [rcx]
0x18001b087  mov     rax, [rax+10h]
0x18001b08b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b090  nop
0x18001b091  jmp     loc_18001AFF3
0x18001b096  mov     rcx, [rbp+arg_10]
0x18001b09a  mov     rax, [rcx]
0x18001b09d  lea     rdx, [rbp+pvarg]
0x18001b0a1  mov     rax, [rax+68h]
0x18001b0a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0aa  mov     edi, eax
0x18001b0ac  test    eax, eax
0x18001b0ae  jns     short loc_18001B10B
0x18001b0b0  mov     rcx, [rbp+18h]; this
0x18001b0b4  mov     r9d, eax; char *
0x18001b0b7  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001b0be  mov     edx, 0FDh; void *
0x18001b0c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b0c8  nop
0x18001b0c9  lea     rcx, [rbp+pvarg]; pvarg
0x18001b0cd  call    cs:__imp_VariantClear
0x18001b0d4  nop     dword ptr [rax+rax+00h]
0x18001b0d9  nop
0x18001b0da  mov     rcx, [rbp+arg_8]
0x18001b0de  test    rcx, rcx
0x18001b0e1  jz      short loc_18001B0F0
0x18001b0e3  mov     rax, [rcx]
0x18001b0e6  mov     rax, [rax+10h]
0x18001b0ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0ef  nop
0x18001b0f0  mov     rcx, [rbp+arg_10]
0x18001b0f4  test    rcx, rcx
0x18001b0f7  jz      short loc_18001B106
0x18001b0f9  mov     rax, [rcx]
0x18001b0fc  mov     rax, [rax+10h]
0x18001b100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b105  nop
0x18001b106  jmp     loc_18001AFF3
0x18001b10b  mov     eax, 8
0x18001b110  cmp     ax, word ptr [rbp+pvarg]
0x18001b114  jz      short loc_18001B178
0x18001b116  mov     rcx, [rbp+18h]; this
0x18001b11a  mov     ebx, 8000FFFFh
0x18001b11f  mov     r9d, ebx; char *
0x18001b122  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001b129  mov     edx, 0FEh; void *
0x18001b12e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b133  nop
0x18001b134  lea     rcx, [rbp+pvarg]; pvarg
0x18001b138  call    cs:__imp_VariantClear
0x18001b13f  nop     dword ptr [rax+rax+00h]
0x18001b144  nop
0x18001b145  mov     rcx, [rbp+arg_8]
0x18001b149  test    rcx, rcx
0x18001b14c  jz      short loc_18001B15B
0x18001b14e  mov     rax, [rcx]
0x18001b151  mov     rax, [rax+10h]
0x18001b155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b15a  nop
0x18001b15b  mov     rcx, [rbp+arg_10]
0x18001b15f  test    rcx, rcx
0x18001b162  jz      short loc_18001B171
0x18001b164  mov     rdx, [rcx]
0x18001b167  mov     rax, [rdx+10h]
0x18001b16b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b170  nop
0x18001b171  mov     eax, ebx
0x18001b173  jmp     loc_18001B204
0x18001b178  mov     r9, qword ptr [rbp+pvarg+8]
0x18001b17c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001b180  inc     rdx
0x18001b183  cmp     [r9+rdx*2], r14w
0x18001b188  jnz     short loc_18001B180
0x18001b18a  cmp     rdx, [rbx+18h]
0x18001b18e  ja      short loc_18001B1BC
0x18001b190  cmp     qword ptr [rbx+18h], 7
0x18001b195  jbe     short loc_18001B19C
0x18001b197  mov     rdi, [rbx]
0x18001b19a  jmp     short loc_18001B19F
0x18001b19c  mov     rdi, rbx
0x18001b19f  mov     [rbx+10h], rdx
0x18001b1a3  lea     rbx, [rdx+rdx]
0x18001b1a7  mov     r8, rbx; Size
0x18001b1aa  mov     rdx, r9; Src
0x18001b1ad  mov     rcx, rdi; void *
0x18001b1b0  call    memmove_0
0x18001b1b5  mov     [rbx+rdi], r14w
0x18001b1ba  jmp     short loc_18001B1C5
0x18001b1bc  mov     rcx, rbx
0x18001b1bf  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001b1c4  nop
0x18001b1c5  lea     rcx, [rbp+pvarg]; pvarg
0x18001b1c9  call    cs:__imp_VariantClear
0x18001b1d0  nop     dword ptr [rax+rax+00h]
0x18001b1d5  nop
0x18001b1d6  mov     rcx, [rbp+arg_8]
0x18001b1da  test    rcx, rcx
0x18001b1dd  jz      short loc_18001B1EC
0x18001b1df  mov     rax, [rcx]
0x18001b1e2  mov     rax, [rax+10h]
0x18001b1e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1eb  nop
0x18001b1ec  mov     rcx, [rbp+arg_10]
0x18001b1f0  test    rcx, rcx
0x18001b1f3  jz      short loc_18001B202
0x18001b1f5  mov     rax, [rcx]
0x18001b1f8  mov     rax, [rax+10h]
0x18001b1fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b201  nop
0x18001b202  xor     eax, eax
0x18001b204  lea     r11, [rsp+50h+var_s0]
0x18001b209  mov     rbx, [r11+20h]
0x18001b20d  mov     rsi, [r11+38h]
0x18001b211  mov     rsp, r11
0x18001b214  pop     r14
0x18001b216  pop     rdi
0x18001b217  pop     rbp
0x18001b218  retn
```
