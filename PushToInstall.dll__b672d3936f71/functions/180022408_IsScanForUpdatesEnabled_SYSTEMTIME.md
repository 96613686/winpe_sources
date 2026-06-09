# IsScanForUpdatesEnabled(_SYSTEMTIME *)

- ea: `0x180022408`
- end: `0x18002271c`
- name: `?IsScanForUpdatesEnabled@@YA_NPEAU_SYSTEMTIME@@@Z`
- size: `788`
- prototype: `bool __fastcall(LPSYSTEMTIME lpSystemTime)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180044fd8`

## callees

- `0x18002008c`
- `0x180021d38`
- `0x180022408`
- `0x180022834`
- `0x180022888`
- `0x18004f010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180022688`
- `OLEAUT32!__imp_SysFreeString` at `0x180022688`
- `OLEAUT32!__imp_VariantInit` at `0x180022473`
- `OLEAUT32!__imp_VariantInit` at `0x180022495`
- `OLEAUT32!__imp_VariantInit` at `0x1800224b7`
- `OLEAUT32!__imp_VariantInit` at `0x1800224d7`
- `OLEAUT32!__imp_VariantInit` at `0x180022473`
- `OLEAUT32!__imp_VariantInit` at `0x180022495`
- `OLEAUT32!__imp_VariantInit` at `0x1800224b7`
- `OLEAUT32!__imp_VariantInit` at `0x1800224d7`
- `OLEAUT32!__imp_VariantClear` at `0x180022577`
- `OLEAUT32!__imp_VariantClear` at `0x180022586`
- `OLEAUT32!__imp_VariantClear` at `0x180022595`
- `OLEAUT32!__imp_VariantClear` at `0x1800225a4`
- `OLEAUT32!__imp_VariantClear` at `0x180022577`
- `OLEAUT32!__imp_VariantClear` at `0x180022586`
- `OLEAUT32!__imp_VariantClear` at `0x180022595`
- `OLEAUT32!__imp_VariantClear` at `0x1800225a4`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x180022677`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x180022677`

## string_xrefs

- `0x1800225e0`: `Microsoft\Windows\InstallService\ScanForUpdates`
- `0x180022709`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
bool __fastcall IsScanForUpdatesEnabled(LPSYSTEMTIME lpSystemTime)
{
  LPVOID v2; // rdi
  __int64 (__fastcall *v3)(LPVOID, VARIANTARG *, __int128 *, __int128 *); // rbx
  __int128 v4; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v6; // xmm8
  IRecordInfo *v7; // xmm9_8
  __int128 v8; // xmm6
  IRecordInfo *v9; // xmm7_8
  int v10; // eax
  int v11; // eax
  const char *v13; // [rsp+20h] [rbp-1D8h]
  __int64 v14; // [rsp+50h] [rbp-1A8h] BYREF
  LPVOID v15; // [rsp+58h] [rbp-1A0h] BYREF
  DOUBLE vtime; // [rsp+60h] [rbp-198h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-190h] BYREF
  __int64 v18; // [rsp+70h] [rbp-188h] BYREF
  __int64 v19; // [rsp+78h] [rbp-180h] BYREF
  VARIANTARG v20; // [rsp+80h] [rbp-178h] BYREF
  VARIANTARG v21; // [rsp+98h] [rbp-160h] BYREF
  VARIANTARG v22; // [rsp+B0h] [rbp-148h] BYREF
  VARIANTARG pvarg; // [rsp+C8h] [rbp-130h] BYREF
  int v24[4]; // [rsp+E0h] [rbp-118h] BYREF
  IRecordInfo *v25; // [rsp+F0h] [rbp-108h]
  __int128 v26; // [rsp+100h] [rbp-F8h] BYREF
  IRecordInfo *v27; // [rsp+110h] [rbp-E8h]
  __int128 v28; // [rsp+120h] [rbp-D8h] BYREF
  IRecordInfo *v29; // [rsp+130h] [rbp-C8h]
  VARIANTARG v30; // [rsp+140h] [rbp-B8h] BYREF
  int v31; // [rsp+160h] [rbp-98h] BYREF
  __int128 v32; // [rsp+168h] [rbp-90h]
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+0h]
  __int16 v34; // [rsp+208h] [rbp+10h] BYREF
  int v35; // [rsp+210h] [rbp+18h] BYREF
  int v36; // [rsp+218h] [rbp+20h] BYREF

  v34 = 0;
  try
  {
    wil::CoCreateInstance<ITaskService,wil::err_exception_policy>(&v15);
    v31 = 0;
    v32 = 0;
    v2 = v15;
    v3 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)v15 + 80LL);
    VariantInit(&pvarg);
    v4 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    VariantInit(&v22);
    v6 = *(_OWORD *)&v22.vt;
    v7 = v22.pRecInfo;
    VariantInit(&v21);
    v8 = *(_OWORD *)&v21.vt;
    v9 = v21.pRecInfo;
    VariantInit(&v20);
    *(_OWORD *)v24 = v4;
    v25 = pRecInfo;
    v26 = v6;
    v27 = v7;
    v28 = v8;
    v29 = v9;
    v30 = v20;
    v10 = v3(v2, &v30, &v28, &v26);
    if ( v10 < 0 )
      winrt::throw_hresult((unsigned int)v10, &v31);
    VariantClear(&v20);
    VariantClear(&v21);
    VariantClear(&v22);
    VariantClear(&pvarg);
    v14 = 0;
    v11 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v15)(
            v15,
            &GUID_ee57976b_0c5e_4fe9_8c91_a54082ef699b,
            &v14);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v11,
        (int)v24);
    wil::make_bstr(&bstrString, L"Microsoft\\Windows\\InstallService\\ScanForUpdates");
    v36 = 0;
    v35 = 0;
    v19 = 0;
    v18 = 0;
    vtime = 0.0;
    (*(void (__fastcall **)(__int64, BSTR, __int16 *, int *, int *, DOUBLE *, __int64 *, __int64 *))(*(_QWORD *)v14 + 24LL))(
      v14,
      bstrString,
      &v34,
      &v36,
      &v35,
      &vtime,
      &v19,
      &v18);
    VariantTimeToSystemTime(vtime, lpSystemTime);
    if ( bstrString )
      SysFreeString(bstrString);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    if ( v15 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v15 + 16LL))(v15);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtExceptionMsg(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\commonsettings.cpp",
      "Error getting ScanForUpdates scheduled task info",
      v13);
  }
  return v34 == -1;
}

```

## disassembly

```asm
0x180022408  mov     r11, rsp
0x18002240b  push    rbx
0x18002240c  push    rsi
0x18002240d  push    rdi
0x18002240e  sub     rsp, 1E0h
0x180022415  movaps  xmmword ptr [r11-28h], xmm6
0x18002241a  movaps  xmmword ptr [r11-38h], xmm7
0x18002241f  movaps  xmmword ptr [r11-48h], xmm8
0x180022424  movaps  xmmword ptr [r11-58h], xmm9
0x180022429  movaps  xmmword ptr [r11-68h], xmm10
0x18002242e  movaps  xmmword ptr [r11-78h], xmm11
0x180022433  mov     rsi, rcx
0x180022436  xor     eax, eax
0x180022438  mov     [r11+10h], ax
0x18002243d  lea     rcx, [rsp+1F8h+var_1A0]
0x180022442  call    ??$CoCreateInstance@UITaskService@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UITaskService@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z; wil::CoCreateInstance<ITaskService,wil::err_exception_policy>(_GUID const &,ulong)
0x180022447  nop
0x180022448  mov     [rsp+1F8h+var_98], 0
0x180022453  xorps   xmm0, xmm0
0x180022456  movdqu  [rsp+1F8h+var_90], xmm0
0x18002245f  mov     rdi, [rsp+1F8h+var_1A0]
0x180022464  mov     rax, [rdi]
0x180022467  mov     rbx, [rax+50h]
0x18002246b  lea     rcx, [rsp+1F8h+pvarg]; pvarg
0x180022473  call    cs:__imp_VariantInit
0x180022479  nop
0x18002247a  movups  xmm10, xmmword ptr [rsp+1F8h+pvarg]
0x180022483  movsd   xmm11, qword ptr [rsp+1F8h+pvarg+10h]
0x18002248d  lea     rcx, [rsp+1F8h+var_148]; pvarg
0x180022495  call    cs:__imp_VariantInit
0x18002249b  nop
0x18002249c  movups  xmm8, xmmword ptr [rsp+1F8h+var_148]
0x1800224a5  movsd   xmm9, qword ptr [rsp+1F8h+var_148+10h]
0x1800224af  lea     rcx, [rsp+1F8h+var_160]; pvarg
0x1800224b7  call    cs:__imp_VariantInit
0x1800224bd  nop
0x1800224be  movups  xmm6, xmmword ptr [rsp+1F8h+var_160]
0x1800224c6  movsd   xmm7, qword ptr [rsp+1F8h+var_160+10h]
0x1800224cf  lea     rcx, [rsp+1F8h+var_178]; pvarg
0x1800224d7  call    cs:__imp_VariantInit
0x1800224dd  nop
0x1800224de  movups  xmm0, xmmword ptr [rsp+1F8h+var_178]
0x1800224e6  movsd   xmm1, qword ptr [rsp+1F8h+var_178+10h]
0x1800224ef  movaps  xmmword ptr [rsp+1F8h+var_118], xmm10
0x1800224f8  movsd   [rsp+1F8h+var_108], xmm11
0x180022502  movaps  [rsp+1F8h+var_F8], xmm8
0x18002250b  movsd   [rsp+1F8h+var_E8], xmm9
0x180022515  movaps  [rsp+1F8h+var_D8], xmm6
0x18002251d  movsd   [rsp+1F8h+var_C8], xmm7
0x180022526  movaps  [rsp+1F8h+var_B8], xmm0
0x18002252e  movsd   [rsp+1F8h+var_A8], xmm1
0x180022537  lea     rax, [rsp+1F8h+var_118]
0x18002253f  mov     qword ptr [rsp+1F8h+var_1D8], rax; int
0x180022544  lea     r9, [rsp+1F8h+var_F8]
0x18002254c  lea     r8, [rsp+1F8h+var_D8]
0x180022554  lea     rdx, [rsp+1F8h+var_B8]
0x18002255c  mov     rcx, rdi
0x18002255f  mov     rax, rbx
0x180022562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022567  test    eax, eax
0x180022569  js      loc_1800226F6
0x18002256f  lea     rcx, [rsp+1F8h+var_178]; pvarg
0x180022577  call    cs:__imp_VariantClear
0x18002257d  nop
0x18002257e  lea     rcx, [rsp+1F8h+var_160]; pvarg
0x180022586  call    cs:__imp_VariantClear
0x18002258c  nop
0x18002258d  lea     rcx, [rsp+1F8h+var_148]; pvarg
0x180022595  call    cs:__imp_VariantClear
0x18002259b  nop
0x18002259c  lea     rcx, [rsp+1F8h+pvarg]; pvarg
0x1800225a4  call    cs:__imp_VariantClear
0x1800225aa  nop
0x1800225ab  mov     [rsp+1F8h+var_1A8], 0
0x1800225b4  mov     rcx, [rsp+1F8h+var_1A0]
0x1800225b9  mov     rax, [rcx]
0x1800225bc  lea     r8, [rsp+1F8h+var_1A8]
0x1800225c1  lea     rdx, _GUID_ee57976b_0c5e_4fe9_8c91_a54082ef699b
0x1800225c8  mov     rax, [rax]
0x1800225cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225d0  mov     rcx, [rsp+1F8h]; this
0x1800225d8  test    eax, eax
0x1800225da  js      loc_180022706
0x1800225e0  lea     rdx, aMicrosoftWindo; "Microsoft\\Windows\\InstallService\\Sca"...
0x1800225e7  lea     rcx, [rsp+1F8h+bstrString]
0x1800225ec  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1800225f1  nop
0x1800225f2  mov     [rsp+1F8h+arg_18], 0
0x1800225fd  mov     [rsp+1F8h+arg_10], 0
0x180022608  xorps   xmm0, xmm0
0x18002260b  movsd   [rsp+1F8h+var_180], xmm0
0x180022611  movsd   [rsp+1F8h+var_188], xmm0
0x180022617  movsd   [rsp+1F8h+vtime], xmm0
0x18002261d  mov     rcx, [rsp+1F8h+var_1A8]
0x180022622  mov     rax, [rcx]
0x180022625  lea     rdx, [rsp+1F8h+var_188]
0x18002262a  mov     [rsp+1F8h+var_1C0], rdx
0x18002262f  lea     rdx, [rsp+1F8h+var_180]
0x180022634  mov     [rsp+1F8h+var_1C8], rdx
0x180022639  lea     rdx, [rsp+1F8h+vtime]
0x18002263e  mov     [rsp+1F8h+var_1D0], rdx
0x180022643  lea     rdx, [rsp+1F8h+arg_10]
0x18002264b  mov     qword ptr [rsp+1F8h+var_1D8], rdx
0x180022650  lea     r9, [rsp+1F8h+arg_18]
0x180022658  lea     r8, [rsp+1F8h+arg_8]
0x180022660  mov     rdx, [rsp+1F8h+bstrString]
0x180022665  mov     rax, [rax+18h]
0x180022669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002266e  mov     rdx, rsi; lpSystemTime
0x180022671  movsd   xmm0, [rsp+1F8h+vtime]; vtime
0x180022677  call    cs:__imp_VariantTimeToSystemTime
0x18002267d  nop
0x18002267e  mov     rcx, [rsp+1F8h+bstrString]; bstrString
0x180022683  test    rcx, rcx
0x180022686  jz      short loc_18002268F
0x180022688  call    cs:__imp_SysFreeString
0x18002268e  nop
0x18002268f  mov     rcx, [rsp+1F8h+var_1A8]
0x180022694  test    rcx, rcx
0x180022697  jz      short loc_1800226A6
0x180022699  mov     rax, [rcx]
0x18002269c  mov     rax, [rax+10h]
0x1800226a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226a5  nop
0x1800226a6  mov     rcx, [rsp+1F8h+var_1A0]
0x1800226ab  test    rcx, rcx
0x1800226ae  jz      short loc_1800226BD
0x1800226b0  mov     rax, [rcx]
0x1800226b3  mov     rax, [rax+10h]
0x1800226b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226bc  nop
0x1800226bd  cmp     [rsp+1F8h+arg_8], 0FFFFh
0x1800226c6  setz    al
0x1800226c9  lea     r11, [rsp+1F8h+var_18]
0x1800226d1  movaps  xmm6, xmmword ptr [r11-10h]
0x1800226d6  movaps  xmm7, xmmword ptr [r11-20h]
0x1800226db  movaps  xmm8, xmmword ptr [r11-30h]
0x1800226e0  movaps  xmm9, xmmword ptr [r11-40h]
0x1800226e5  movaps  xmm10, xmmword ptr [r11-50h]
0x1800226ea  movaps  xmm11, xmmword ptr [r11-60h]
0x1800226ef  mov     rsp, r11
0x1800226f2  pop     rdi
0x1800226f3  pop     rsi
0x1800226f4  pop     rbx
0x1800226f5  retn
0x1800226f6  lea     rdx, [rsp+1F8h+var_98]
0x1800226fe  mov     ecx, eax
0x180022700  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180022706  mov     r9d, eax; char *
0x180022709  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180022710  mov     edx, 1CBEh; void *
0x180022715  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
