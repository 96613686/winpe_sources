# RestoreDevice::Worker(void)

- ea: `0x1800104b0`
- end: `0x1800107c1`
- name: `?Worker@RestoreDevice@@EEAAJXZ`
- size: `785`
- prototype: `__int64 __fastcall(RestoreDevice *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003948`
- `0x18000b85c`
- `0x18000d544`
- `0x18000d63c`
- `0x18000da30`
- `0x180010150`
- `0x1800104b0`
- `0x1800110d0`
- `0x180011284`
- `0x180012118`
- `0x180030434`
- `0x180046010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180010551`
- `OLEAUT32!__imp_VariantInit` at `0x180010570`
- `OLEAUT32!__imp_VariantInit` at `0x18001058c`
- `OLEAUT32!__imp_VariantInit` at `0x1800105a3`
- `OLEAUT32!__imp_VariantInit` at `0x180010551`
- `OLEAUT32!__imp_VariantInit` at `0x180010570`
- `OLEAUT32!__imp_VariantInit` at `0x18001058c`
- `OLEAUT32!__imp_VariantInit` at `0x1800105a3`
- `OLEAUT32!__imp_VariantClear` at `0x18001064a`
- `OLEAUT32!__imp_VariantClear` at `0x180010656`
- `OLEAUT32!__imp_VariantClear` at `0x180010662`
- `OLEAUT32!__imp_VariantClear` at `0x180010671`
- `OLEAUT32!__imp_VariantClear` at `0x18001064a`
- `OLEAUT32!__imp_VariantClear` at `0x180010656`
- `OLEAUT32!__imp_VariantClear` at `0x180010662`
- `OLEAUT32!__imp_VariantClear` at `0x180010671`

## string_xrefs

- `0x1800107ae`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1800106f1`: `onecoreuap\enduser\winstore\installservice\tasksdll\installservicetasks.cpp`
- `0x1800106b6`: `Microsoft\Windows\InstallService\RestoreDevice`
- `0x180010705`: `Disabled RestoreDevice task`
- `0x18001072b`: `Failed to disable RestoreDevice task`

## pseudocode

```c
__int64 __fastcall RestoreDevice::Worker(RestoreDevice *this)
{
  RestoreDeviceWorker *v2; // rcx
  __int64 v3; // rdx
  unsigned int v4; // esi
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, VARIANTARG *, __int128 *, __int128 *); // rbx
  __int128 v7; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v9; // xmm8
  IRecordInfo *v10; // xmm9_8
  __int128 v11; // xmm6
  IRecordInfo *v12; // xmm7_8
  unsigned int v13; // eax
  int v14; // eax
  int v15; // eax
  const char *v17; // [rsp+20h] [rbp-1A8h]
  __int64 v18; // [rsp+40h] [rbp-188h] BYREF
  VARIANTARG v19; // [rsp+48h] [rbp-180h] BYREF
  VARIANTARG v20; // [rsp+60h] [rbp-168h] BYREF
  VARIANTARG v21; // [rsp+78h] [rbp-150h] BYREF
  VARIANTARG pvarg; // [rsp+90h] [rbp-138h] BYREF
  int v23[4]; // [rsp+B0h] [rbp-118h] BYREF
  IRecordInfo *v24; // [rsp+C0h] [rbp-108h]
  __int128 v25; // [rsp+D0h] [rbp-F8h] BYREF
  IRecordInfo *v26; // [rsp+E0h] [rbp-E8h]
  __int128 v27; // [rsp+F0h] [rbp-D8h] BYREF
  IRecordInfo *v28; // [rsp+100h] [rbp-C8h]
  VARIANTARG v29; // [rsp+110h] [rbp-B8h] BYREF
  int v30; // [rsp+130h] [rbp-98h] BYREF
  __int128 v31; // [rsp+138h] [rbp-90h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]
  _QWORD *v33; // [rsp+1D0h] [rbp+8h]
  char v34; // [rsp+1D8h] [rbp+10h] BYREF
  __int64 v35; // [rsp+1E0h] [rbp+18h] BYREF
  __int64 v36; // [rsp+1E8h] [rbp+20h] BYREF

  v33 = operator new(8u);
  *v33 = 0;
  v3 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = v33;
  if ( v3 )
    std::default_delete<RestoreDeviceWorker>::operator()();
  v4 = RestoreDeviceWorker::DoWork(v2);
  try
  {
    wil::CoCreateInstance<ITaskService,wil::err_exception_policy>(&v36);
    v30 = 0;
    v31 = 0;
    v5 = v36;
    v6 = *(__int64 (__fastcall **)(__int64, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)v36 + 80LL);
    VariantInit(&pvarg);
    v7 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    VariantInit(&v21);
    v9 = *(_OWORD *)&v21.vt;
    v10 = v21.pRecInfo;
    VariantInit(&v20);
    v11 = *(_OWORD *)&v20.vt;
    v12 = v20.pRecInfo;
    VariantInit(&v19);
    *(_OWORD *)v23 = v7;
    v24 = pRecInfo;
    v25 = v9;
    v26 = v10;
    v27 = v11;
    v28 = v12;
    v29 = v19;
    v13 = v6(v5, &v29, &v27, &v25);
    winrt::check_hresult(&v34, v13, &v30);
    VariantClear(&v19);
    VariantClear(&v20);
    VariantClear(&v21);
    VariantClear(&pvarg);
    v35 = 0;
    v14 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v36)(
            v36,
            &GUID_ee57976b_0c5e_4fe9_8c91_a54082ef699b,
            &v35);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v14,
        (int)v23);
    wil::make_bstr(&v18, L"Microsoft\\Windows\\InstallService\\RestoreDevice");
    v15 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v35 + 56LL))(v35, v18);
    if ( v15 < 0 )
      LogSimpleMessage(
        1u,
        "onecoreuap\\enduser\\winstore\\installservice\\tasksdll\\installservicetasks.cpp",
        0x16Au,
        "RestoreDevice::Worker",
        v15,
        L"Failed to disable RestoreDevice task",
        0,
        0);
    else
      LogSimpleMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\tasksdll\\installservicetasks.cpp",
        0x166u,
        "RestoreDevice::Worker",
        -1,
        L"Disabled RestoreDevice task",
        0,
        0);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v18);
    wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(&v35);
    wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(&v36);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtExceptionMsg(
      retaddr,
      (void *)0x16C,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\tasksdll\\installservicetasks.cpp",
      "Error disabling RestoreDevice task",
      v17);
  }
  return v4;
}

```

## disassembly

```asm
0x1800104b0  mov     rax, rsp
0x1800104b3  push    rbx
0x1800104b4  push    rsi
0x1800104b5  push    rdi
0x1800104b6  sub     rsp, 1B0h
0x1800104bd  movaps  xmmword ptr [rax-28h], xmm6
0x1800104c1  movaps  xmmword ptr [rax-38h], xmm7
0x1800104c5  movaps  xmmword ptr [rax-48h], xmm8
0x1800104ca  movaps  xmmword ptr [rax-58h], xmm9
0x1800104cf  movaps  xmmword ptr [rax-68h], xmm10
0x1800104d4  movaps  xmmword ptr [rax-78h], xmm11
0x1800104d9  mov     rbx, rcx
0x1800104dc  mov     ecx, 8; Size
0x1800104e1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800104e6  mov     [rsp+1C8h+arg_0], rax
0x1800104ee  mov     qword ptr [rax], 0
0x1800104f5  mov     rdx, [rbx+38h]
0x1800104f9  mov     [rbx+38h], rax
0x1800104fd  test    rdx, rdx
0x180010500  jz      short loc_180010507
0x180010502  call    ??R?$default_delete@VRestoreDeviceWorker@@@std@@QEBAXPEAVRestoreDeviceWorker@@@Z; std::default_delete<RestoreDeviceWorker>::operator()(RestoreDeviceWorker *)
0x180010507  call    ?DoWork@RestoreDeviceWorker@@QEAAJXZ; RestoreDeviceWorker::DoWork(void)
0x18001050c  mov     esi, eax
0x18001050e  mov     dword ptr [rsp+1C8h+arg_0], eax
0x180010515  lea     rcx, [rsp+1C8h+arg_18]
0x18001051d  call    ??$CoCreateInstance@UITaskService@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UITaskService@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z; wil::CoCreateInstance<ITaskService,wil::err_exception_policy>(_GUID const &,ulong)
0x180010522  nop
0x180010523  mov     [rsp+1C8h+var_98], 0
0x18001052e  xorps   xmm0, xmm0
0x180010531  movdqu  [rsp+1C8h+var_90], xmm0
0x18001053a  mov     rdi, [rsp+1C8h+arg_18]
0x180010542  mov     rax, [rdi]
0x180010545  mov     rbx, [rax+50h]
0x180010549  lea     rcx, [rsp+1C8h+pvarg]; pvarg
0x180010551  call    cs:__imp_VariantInit
0x180010557  nop
0x180010558  movups  xmm10, xmmword ptr [rsp+1C8h+pvarg]
0x180010561  movsd   xmm11, qword ptr [rsp+1C8h+pvarg+10h]
0x18001056b  lea     rcx, [rsp+1C8h+var_150]; pvarg
0x180010570  call    cs:__imp_VariantInit
0x180010576  nop
0x180010577  movups  xmm8, xmmword ptr [rsp+1C8h+var_150]
0x18001057d  movsd   xmm9, qword ptr [rsp+1C8h+var_150+10h]
0x180010587  lea     rcx, [rsp+1C8h+var_168]; pvarg
0x18001058c  call    cs:__imp_VariantInit
0x180010592  nop
0x180010593  movups  xmm6, xmmword ptr [rsp+1C8h+var_168]
0x180010598  movsd   xmm7, qword ptr [rsp+1C8h+var_168+10h]
0x18001059e  lea     rcx, [rsp+1C8h+var_180]; pvarg
0x1800105a3  call    cs:__imp_VariantInit
0x1800105a9  nop
0x1800105aa  movups  xmm0, xmmword ptr [rsp+1C8h+var_180]
0x1800105af  movsd   xmm1, qword ptr [rsp+1C8h+var_180+10h]
0x1800105b5  movaps  xmmword ptr [rsp+1C8h+var_118], xmm10
0x1800105be  movsd   [rsp+1C8h+var_108], xmm11
0x1800105c8  movaps  [rsp+1C8h+var_F8], xmm8
0x1800105d1  movsd   [rsp+1C8h+var_E8], xmm9
0x1800105db  movaps  [rsp+1C8h+var_D8], xmm6
0x1800105e3  movsd   [rsp+1C8h+var_C8], xmm7
0x1800105ec  movaps  [rsp+1C8h+var_B8], xmm0
0x1800105f4  movsd   [rsp+1C8h+var_A8], xmm1
0x1800105fd  lea     rax, [rsp+1C8h+var_118]
0x180010605  mov     qword ptr [rsp+1C8h+var_1A8], rax; int
0x18001060a  lea     r9, [rsp+1C8h+var_F8]
0x180010612  lea     r8, [rsp+1C8h+var_D8]
0x18001061a  lea     rdx, [rsp+1C8h+var_B8]
0x180010622  mov     rcx, rdi
0x180010625  mov     rax, rbx
0x180010628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001062d  lea     r8, [rsp+1C8h+var_98]
0x180010635  mov     edx, eax
0x180010637  lea     rcx, [rsp+1C8h+arg_8]
0x18001063f  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180010644  nop
0x180010645  lea     rcx, [rsp+1C8h+var_180]; pvarg
0x18001064a  call    cs:__imp_VariantClear
0x180010650  nop
0x180010651  lea     rcx, [rsp+1C8h+var_168]; pvarg
0x180010656  call    cs:__imp_VariantClear
0x18001065c  nop
0x18001065d  lea     rcx, [rsp+1C8h+var_150]; pvarg
0x180010662  call    cs:__imp_VariantClear
0x180010668  nop
0x180010669  lea     rcx, [rsp+1C8h+pvarg]; pvarg
0x180010671  call    cs:__imp_VariantClear
0x180010677  nop
0x180010678  mov     [rsp+1C8h+arg_10], 0
0x180010684  mov     rcx, [rsp+1C8h+arg_18]
0x18001068c  mov     rax, [rcx]
0x18001068f  lea     r8, [rsp+1C8h+arg_10]
0x180010697  lea     rdx, _GUID_ee57976b_0c5e_4fe9_8c91_a54082ef699b
0x18001069e  mov     rax, [rax]
0x1800106a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106a6  mov     rcx, [rsp+1C8h]; this
0x1800106ae  test    eax, eax
0x1800106b0  js      loc_1800107AB
0x1800106b6  lea     rdx, aMicrosoftWindo_0; "Microsoft\\Windows\\InstallService\\Res"...
0x1800106bd  lea     rcx, [rsp+1C8h+var_188]
0x1800106c2  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1800106c7  nop
0x1800106c8  mov     rcx, [rsp+1C8h+arg_10]
0x1800106d0  mov     rax, [rcx]
0x1800106d3  mov     rdx, [rsp+1C8h+var_188]
0x1800106d8  mov     rax, [rax+38h]
0x1800106dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106e1  mov     [rsp+1C8h+var_190], 0; unsigned __int16 *
0x1800106ea  lea     r9, aRestoredeviceW; "RestoreDevice::Worker"
0x1800106f1  lea     rdx, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\installs"...
0x1800106f8  mov     [rsp+1C8h+var_198], 0; char *
0x180010701  test    eax, eax
0x180010703  js      short loc_18001072B
0x180010705  lea     rax, aDisabledRestor; "Disabled RestoreDevice task"
0x18001070c  mov     [rsp+1C8h+var_1A0], rax; unsigned __int16 *
0x180010711  mov     [rsp+1C8h+var_1A8], 0FFFFFFFFh; int
0x180010719  mov     r8d, 166h; unsigned int
0x18001071f  mov     ecx, 3; unsigned int
0x180010724  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x180010729  jmp     short loc_18001074C
0x18001072b  lea     rcx, aFailedToDisabl; "Failed to disable RestoreDevice task"
0x180010732  mov     [rsp+1C8h+var_1A0], rcx; unsigned __int16 *
0x180010737  mov     [rsp+1C8h+var_1A8], eax; int
0x18001073b  mov     r8d, 16Ah; unsigned int
0x180010741  mov     ecx, 1; unsigned int
0x180010746  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x18001074b  nop
0x18001074c  lea     rcx, [rsp+1C8h+var_188]
0x180010751  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180010756  nop
0x180010757  lea     rcx, [rsp+1C8h+arg_10]
0x18001075f  call    ??1?$com_ptr_t@UITaskSchedulerEx2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(void)
0x180010764  nop
0x180010765  lea     rcx, [rsp+1C8h+arg_18]
0x18001076d  call    ??1?$com_ptr_t@UITaskSchedulerEx2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(void)
0x180010772  nop
0x180010773  jmp     short loc_18001077C
0x180010775  mov     esi, dword ptr [rsp+1C8h+arg_0]
0x18001077c  mov     eax, esi
0x18001077e  lea     r11, [rsp+1C8h+var_18]
0x180010786  movaps  xmm6, xmmword ptr [r11-10h]
0x18001078b  movaps  xmm7, xmmword ptr [r11-20h]
0x180010790  movaps  xmm8, xmmword ptr [r11-30h]
0x180010795  movaps  xmm9, xmmword ptr [r11-40h]
0x18001079a  movaps  xmm10, xmmword ptr [r11-50h]
0x18001079f  movaps  xmm11, xmmword ptr [r11-60h]
0x1800107a4  mov     rsp, r11
0x1800107a7  pop     rdi
0x1800107a8  pop     rsi
0x1800107a9  pop     rbx
0x1800107aa  retn
0x1800107ab  mov     r9d, eax; char *
0x1800107ae  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800107b5  mov     edx, 1CBEh; void *
0x1800107ba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
