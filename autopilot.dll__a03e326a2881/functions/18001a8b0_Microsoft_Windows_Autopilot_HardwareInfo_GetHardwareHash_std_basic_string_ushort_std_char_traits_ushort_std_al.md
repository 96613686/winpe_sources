# Microsoft::Windows::Autopilot::HardwareInfo::GetHardwareHash(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001a8b0`
- end: `0x18001ab7f`
- name: `?GetHardwareHash@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `719`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180009957`
- `0x1800105f4`
- `0x180018cd0`
- `0x18001a8b0`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001a915`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001a915`
- `OLEAUT32!__imp_VariantInit` at `0x18001a8d7`
- `OLEAUT32!__imp_VariantInit` at `0x18001a8d7`
- `OLEAUT32!__imp_VariantClear` at `0x18001a93e`
- `OLEAUT32!__imp_VariantClear` at `0x18001a9d6`
- `OLEAUT32!__imp_VariantClear` at `0x18001aa45`
- `OLEAUT32!__imp_VariantClear` at `0x18001aaaa`
- `OLEAUT32!__imp_VariantClear` at `0x18001ab35`
- `OLEAUT32!__imp_VariantClear` at `0x18001a93e`
- `OLEAUT32!__imp_VariantClear` at `0x18001a9d6`
- `OLEAUT32!__imp_VariantClear` at `0x18001aa45`
- `OLEAUT32!__imp_VariantClear` at `0x18001aaaa`
- `OLEAUT32!__imp_VariantClear` at `0x18001ab35`

## string_xrefs

- `0x18001a928`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001a9c0`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001aa2f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001aa94`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::Windows::Autopilot::HardwareInfo::GetHardwareHash(char **a1)
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
    if ( v13 > (unsigned __int64)a1[3] )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        a1,
        v13,
        v11,
        pvarg.llVal);
    }
    else
    {
      if ( (unsigned __int64)a1[3] <= 7 )
        v14 = (char *)a1;
      else
        v14 = *a1;
      a1[2] = (char *)v13;
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
0x18001a8b0  mov     [rsp-18h+arg_0], rbx
0x18001a8b5  mov     [rsp-18h+arg_18], rsi
0x18001a8ba  push    rbp
0x18001a8bb  push    rdi
0x18001a8bc  push    r14
0x18001a8be  mov     rbp, rsp
0x18001a8c1  sub     rsp, 50h
0x18001a8c5  mov     rbx, rcx
0x18001a8c8  xor     r14d, r14d
0x18001a8cb  mov     [rbp+arg_10], r14
0x18001a8cf  mov     [rbp+arg_8], r14
0x18001a8d3  lea     rcx, [rbp+pvarg]; pvarg
0x18001a8d7  call    cs:__imp_VariantInit
0x18001a8dd  nop
0x18001a8de  mov     rcx, [rbp+arg_8]
0x18001a8e2  mov     [rbp+arg_8], r14
0x18001a8e6  test    rcx, rcx
0x18001a8e9  jz      short loc_18001A8F8
0x18001a8eb  mov     rax, [rcx]
0x18001a8ee  mov     rax, [rax+10h]
0x18001a8f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8f7  nop
0x18001a8f8  lea     rax, [rbp+arg_8]
0x18001a8fc  mov     qword ptr [rsp+50h+ppv], rax; int
0x18001a901  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x18001a908  xor     edx, edx; pUnkOuter
0x18001a90a  lea     r8d, [rdx+1]; dwClsContext
0x18001a90e  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x18001a915  call    cs:__imp_CoCreateInstance
0x18001a91b  mov     edi, eax
0x18001a91d  test    eax, eax
0x18001a91f  jns     short loc_18001A978
0x18001a921  mov     rcx, [rbp+18h]; this
0x18001a925  mov     r9d, eax; char *
0x18001a928  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001a92f  mov     edx, 0FBh; void *
0x18001a934  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a939  nop
0x18001a93a  lea     rcx, [rbp+pvarg]; pvarg
0x18001a93e  call    cs:__imp_VariantClear
0x18001a944  nop
0x18001a945  mov     rcx, [rbp+arg_8]
0x18001a949  test    rcx, rcx
0x18001a94c  jz      short loc_18001A95B
0x18001a94e  mov     rax, [rcx]
0x18001a951  mov     rax, [rax+10h]
0x18001a955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a95a  nop
0x18001a95b  mov     rcx, [rbp+arg_10]
0x18001a95f  test    rcx, rcx
0x18001a962  jz      short loc_18001A971
0x18001a964  mov     rax, [rcx]
0x18001a967  mov     rax, [rax+10h]
0x18001a96b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a970  nop
0x18001a971  mov     eax, edi
0x18001a973  jmp     loc_18001AB6A
0x18001a978  mov     rdi, [rbp+arg_8]
0x18001a97c  mov     rax, [rdi]
0x18001a97f  mov     rsi, [rax+50h]
0x18001a983  mov     rcx, [rbp+arg_10]
0x18001a987  mov     [rbp+arg_10], r14
0x18001a98b  test    rcx, rcx
0x18001a98e  jz      short loc_18001A99D
0x18001a990  mov     rdx, [rcx]
0x18001a993  mov     rax, [rdx+10h]
0x18001a997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a99c  nop
0x18001a99d  lea     r8, [rbp+arg_10]
0x18001a9a1  lea     rdx, aDevdetailExtDe; "./DevDetail/Ext/DeviceHardwareData"
0x18001a9a8  mov     rcx, rdi
0x18001a9ab  mov     rax, rsi
0x18001a9ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9b3  mov     edi, eax
0x18001a9b5  test    eax, eax
0x18001a9b7  jns     short loc_18001AA0E
0x18001a9b9  mov     rcx, [rbp+18h]; this
0x18001a9bd  mov     r9d, eax; char *
0x18001a9c0  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001a9c7  mov     edx, 0FCh; void *
0x18001a9cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a9d1  nop
0x18001a9d2  lea     rcx, [rbp+pvarg]; pvarg
0x18001a9d6  call    cs:__imp_VariantClear
0x18001a9dc  nop
0x18001a9dd  mov     rcx, [rbp+arg_8]
0x18001a9e1  test    rcx, rcx
0x18001a9e4  jz      short loc_18001A9F3
0x18001a9e6  mov     rax, [rcx]
0x18001a9e9  mov     rax, [rax+10h]
0x18001a9ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9f2  nop
0x18001a9f3  mov     rcx, [rbp+arg_10]
0x18001a9f7  test    rcx, rcx
0x18001a9fa  jz      short loc_18001AA09
0x18001a9fc  mov     rax, [rcx]
0x18001a9ff  mov     rax, [rax+10h]
0x18001aa03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa08  nop
0x18001aa09  jmp     loc_18001A971
0x18001aa0e  mov     rcx, [rbp+arg_10]
0x18001aa12  mov     rax, [rcx]
0x18001aa15  lea     rdx, [rbp+pvarg]
0x18001aa19  mov     rax, [rax+68h]
0x18001aa1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa22  mov     edi, eax
0x18001aa24  test    eax, eax
0x18001aa26  jns     short loc_18001AA7D
0x18001aa28  mov     rcx, [rbp+18h]; this
0x18001aa2c  mov     r9d, eax; char *
0x18001aa2f  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001aa36  mov     edx, 0FDh; void *
0x18001aa3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001aa40  nop
0x18001aa41  lea     rcx, [rbp+pvarg]; pvarg
0x18001aa45  call    cs:__imp_VariantClear
0x18001aa4b  nop
0x18001aa4c  mov     rcx, [rbp+arg_8]
0x18001aa50  test    rcx, rcx
0x18001aa53  jz      short loc_18001AA62
0x18001aa55  mov     rax, [rcx]
0x18001aa58  mov     rax, [rax+10h]
0x18001aa5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa61  nop
0x18001aa62  mov     rcx, [rbp+arg_10]
0x18001aa66  test    rcx, rcx
0x18001aa69  jz      short loc_18001AA78
0x18001aa6b  mov     rax, [rcx]
0x18001aa6e  mov     rax, [rax+10h]
0x18001aa72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa77  nop
0x18001aa78  jmp     loc_18001A971
0x18001aa7d  mov     eax, 8
0x18001aa82  cmp     ax, word ptr [rbp+pvarg]
0x18001aa86  jz      short loc_18001AAE4
0x18001aa88  mov     rcx, [rbp+18h]; this
0x18001aa8c  mov     ebx, 8000FFFFh
0x18001aa91  mov     r9d, ebx; char *
0x18001aa94  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001aa9b  mov     edx, 0FEh; void *
0x18001aaa0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001aaa5  nop
0x18001aaa6  lea     rcx, [rbp+pvarg]; pvarg
0x18001aaaa  call    cs:__imp_VariantClear
0x18001aab0  nop
0x18001aab1  mov     rcx, [rbp+arg_8]
0x18001aab5  test    rcx, rcx
0x18001aab8  jz      short loc_18001AAC7
0x18001aaba  mov     rax, [rcx]
0x18001aabd  mov     rax, [rax+10h]
0x18001aac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aac6  nop
0x18001aac7  mov     rcx, [rbp+arg_10]
0x18001aacb  test    rcx, rcx
0x18001aace  jz      short loc_18001AADD
0x18001aad0  mov     rdx, [rcx]
0x18001aad3  mov     rax, [rdx+10h]
0x18001aad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aadc  nop
0x18001aadd  mov     eax, ebx
0x18001aadf  jmp     loc_18001AB6A
0x18001aae4  mov     r9, qword ptr [rbp+pvarg+8]
0x18001aae8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001aaec  inc     rdx
0x18001aaef  cmp     [r9+rdx*2], r14w
0x18001aaf4  jnz     short loc_18001AAEC
0x18001aaf6  cmp     rdx, [rbx+18h]
0x18001aafa  ja      short loc_18001AB28
0x18001aafc  cmp     qword ptr [rbx+18h], 7
0x18001ab01  jbe     short loc_18001AB08
0x18001ab03  mov     rdi, [rbx]
0x18001ab06  jmp     short loc_18001AB0B
0x18001ab08  mov     rdi, rbx
0x18001ab0b  mov     [rbx+10h], rdx
0x18001ab0f  lea     rbx, [rdx+rdx]
0x18001ab13  mov     r8, rbx; Size
0x18001ab16  mov     rdx, r9; Src
0x18001ab19  mov     rcx, rdi; void *
0x18001ab1c  call    memmove_0
0x18001ab21  mov     [rbx+rdi], r14w
0x18001ab26  jmp     short loc_18001AB31
0x18001ab28  mov     rcx, rbx
0x18001ab2b  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001ab30  nop
0x18001ab31  lea     rcx, [rbp+pvarg]; pvarg
0x18001ab35  call    cs:__imp_VariantClear
0x18001ab3b  nop
0x18001ab3c  mov     rcx, [rbp+arg_8]
0x18001ab40  test    rcx, rcx
0x18001ab43  jz      short loc_18001AB52
0x18001ab45  mov     rax, [rcx]
0x18001ab48  mov     rax, [rax+10h]
0x18001ab4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab51  nop
0x18001ab52  mov     rcx, [rbp+arg_10]
0x18001ab56  test    rcx, rcx
0x18001ab59  jz      short loc_18001AB68
0x18001ab5b  mov     rax, [rcx]
0x18001ab5e  mov     rax, [rax+10h]
0x18001ab62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab67  nop
0x18001ab68  xor     eax, eax
0x18001ab6a  lea     r11, [rsp+50h+var_s0]
0x18001ab6f  mov     rbx, [r11+20h]
0x18001ab73  mov     rsi, [r11+38h]
0x18001ab77  mov     rsp, r11
0x18001ab7a  pop     r14
0x18001ab7c  pop     rdi
0x18001ab7d  pop     rbp
0x18001ab7e  retn
```
