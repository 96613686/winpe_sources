# CBrokeredAppointmentsManager::_ReplaceAppointmentAsyncInternal(HSTRING__ *,Windows::ApplicationModel::Appointments::IAppointment *,Windows::Foundation::Rect const &,Windows::UI::Popups::Placement,Windows::Foundation::DateTime *,Windows::Foundation::IAsyncOperation<HSTRING__ *> * *)

- ea: `0x18018e804`
- end: `0x18018ea31`
- name: `?_ReplaceAppointmentAsyncInternal@CBrokeredAppointmentsManager@@CAJPEAUHSTRING__@@PEAUIAppointment@Appointments@ApplicationModel@Windows@@AEBURect@Foundation@6@W4Placement@Popups@UI@6@PEAUDateTime@86@PEAPEAU?$IAsyncOperation@PEAUHSTRING__@@@86@@Z`
- size: `557`
- prototype: `__int64 __usercall@<rax>(HSTRING string@<rcx>, struct Windows::ApplicationModel::Appointments::IAppointment *@<rdx>, __int64, __int64)`
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18018d520`
- `0x18018d560`
- `0x18018d5a0`

## callees

- `0x18000edd4`
- `0x180055128`
- `0x180142e34`
- `0x180182dfc`
- `0x180184904`
- `0x180185f54`
- `0x18018b040`
- `0x18018e508`
- `0x18018e804`
- `0x18018ed98`
- `0x18018f158`
- `0x1803853fc`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18018e8ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18018e8ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18018e84a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18018e84a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e8b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e8de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e9bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e9ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e9f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018ea07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e8b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e8de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e9bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e9ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e9f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018ea07`

## pseudocode

```c
__int64 __fastcall CBrokeredAppointmentsManager::_ReplaceAppointmentAsyncInternal(
        HSTRING string,
        struct Windows::ApplicationModel::Appointments::IAppointment *a2,
        __int64 a3,
        int a4,
        __int64 *a5,
        _QWORD *a6)
{
  char v6; // r15
  int CallingApplicationWindowAndVerifyVisibility; // esi
  unsigned int v11; // r8d
  void *v12; // rbx
  unsigned __int16 **v13; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rsi
  void *v18; // rdi
  __int128 v19; // xmm0
  void *v20; // rax
  __int64 v21; // r8
  void *v23; // [rsp+20h] [rbp-59h] BYREF
  void *v24; // [rsp+28h] [rbp-51h] BYREF
  _QWORD v25[2]; // [rsp+30h] [rbp-49h] BYREF
  HWND v26; // [rsp+40h] [rbp-39h] BYREF
  struct Windows::ApplicationModel::Appointments::IAppointment *v27; // [rsp+48h] [rbp-31h] BYREF
  void *v28; // [rsp+50h] [rbp-29h] BYREF
  __int128 v29; // [rsp+58h] [rbp-21h]
  int v30; // [rsp+68h] [rbp-11h]
  char v31; // [rsp+6Ch] [rbp-Dh]
  __int64 v32; // [rsp+70h] [rbp-9h]
  void *v33; // [rsp+78h] [rbp-1h]
  HWND v34; // [rsp+80h] [rbp+7h]
  struct Windows::ApplicationModel::Appointments::IAppointment *v35; // [rsp+88h] [rbp+Fh] BYREF

  v6 = 0;
  v25[0] = a3;
  *a6 = 0;
  if ( !a2 )
  {
    CallingApplicationWindowAndVerifyVisibility = -2147467261;
    v11 = 11206;
LABEL_5:
    OriginateErrorWithResourceString(CallingApplicationWindowAndVerifyVisibility, 0, v11);
    return (unsigned int)CallingApplicationWindowAndVerifyVisibility;
  }
  if ( WindowsIsStringEmpty(string) )
  {
    CallingApplicationWindowAndVerifyVisibility = -2147024809;
    v11 = 11208;
    goto LABEL_5;
  }
  CallingApplicationWindowAndVerifyVisibility = CBrokeredAppointmentsManager::_ValidateAppointmentInternalImplementation(a2);
  if ( CallingApplicationWindowAndVerifyVisibility >= 0 )
  {
    CallingApplicationWindowAndVerifyVisibility = CBrokeredAppointmentsManager::_ValidateAppointmentPropertyValues(a2);
    if ( CallingApplicationWindowAndVerifyVisibility >= 0 )
    {
      v12 = 0;
      v26 = 0;
      v23 = 0;
      CallingApplicationWindowAndVerifyVisibility = CBrokeredAppointmentsManager::_GetCallingApplicationWindowAndVerifyVisibility(
                                                      &v26,
                                                      0);
      if ( CallingApplicationWindowAndVerifyVisibility >= 0 )
      {
        CoTaskMemFree(0);
        CallingApplicationWindowAndVerifyVisibility = CallerIdentity::GetCallingProcessPackageFamilyName(
                                                        (CallerIdentity *)&v23,
                                                        v13);
        if ( CallingApplicationWindowAndVerifyVisibility < 0 )
        {
          v12 = v23;
        }
        else
        {
          v24 = 0;
          CoTaskMemFree(0);
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          CallingApplicationWindowAndVerifyVisibility = _AllocString<CTCoAllocPolicy>(v16, v15, StringRawBuffer, &v24);
          if ( CallingApplicationWindowAndVerifyVisibility < 0 )
          {
            v12 = v23;
            v18 = v24;
          }
          else
          {
            if ( a5 )
            {
              v17 = *a5;
              v6 = 1;
            }
            else
            {
              v17 = 0;
            }
            v27 = a2;
            Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(&v27);
            v18 = 0;
            v28 = v24;
            v33 = v23;
            v30 = a4;
            v31 = v6;
            v19 = *(_OWORD *)v25[0];
            v32 = v17;
            v29 = v19;
            v34 = v26;
            v35 = a2;
            Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(&v35);
            LODWORD(v25[0]) = 1;
            *(_QWORD *)((char *)v25 + 4) = 4;
            v20 = operator new(0x58u, (const struct std::nothrow_t *)std::nothrow);
            if ( v20 )
              v20 = (void *)Windows::Internal::COperationLambdaVar<0,_lambda_05f3cc7b8d847fd5ad9f7c464deabe87_,Windows::Internal::CHSTRINGResult,>::COperationLambdaVar<0,_lambda_05f3cc7b8d847fd5ad9f7c464deabe87_,Windows::Internal::CHSTRINGResult,>(
                              v20,
                              &v28);
            CallingApplicationWindowAndVerifyVisibility = Windows::Internal::MakeAsyncOperationHelper<Windows::Internal::CHSTRINGResult,HSTRING__ *,Windows::Internal::ComTaskPoolHandler>(
                                                            v25,
                                                            a6,
                                                            v21,
                                                            v20);
            _lambda_05f3cc7b8d847fd5ad9f7c464deabe87_::~_lambda_05f3cc7b8d847fd5ad9f7c464deabe87_((_lambda_05f3cc7b8d847fd5ad9f7c464deabe87_ *)&v28);
            CoTaskMemFree(0);
            CoTaskMemFree(0);
            (*(void (__fastcall **)(struct Windows::ApplicationModel::Appointments::IAppointment *))(*(_QWORD *)a2 + 16LL))(a2);
          }
          CoTaskMemFree(v18);
        }
      }
      CoTaskMemFree(v12);
    }
  }
  return (unsigned int)CallingApplicationWindowAndVerifyVisibility;
}

```

## disassembly

```asm
0x18018e804  mov     [rsp-8+arg_10], rbx
0x18018e809  push    rbp
0x18018e80a  push    rsi
0x18018e80b  push    rdi
0x18018e80c  push    r12
0x18018e80e  push    r13
0x18018e810  push    r14
0x18018e812  push    r15
0x18018e814  lea     rbp, [rsp-17h]
0x18018e819  sub     rsp, 90h
0x18018e820  mov     r12, [rbp+47h+arg_28]
0x18018e824  xor     r15d, r15d
0x18018e827  mov     qword ptr [rbp+47h+var_90], r8
0x18018e82b  mov     r13d, r9d
0x18018e82e  mov     r14, rdx
0x18018e831  mov     rdi, rcx
0x18018e834  mov     [r12], r15
0x18018e838  test    rdx, rdx
0x18018e83b  jnz     short loc_18018E84A
0x18018e83d  mov     esi, 80004003h
0x18018e842  mov     r8d, 2BC6h
0x18018e848  jmp     short loc_18018E865
0x18018e84a  call    cs:__imp_WindowsIsStringEmpty
0x18018e851  nop     dword ptr [rax+rax+00h]
0x18018e856  test    eax, eax
0x18018e858  jz      short loc_18018E873
0x18018e85a  mov     esi, 80070057h
0x18018e85f  mov     r8d, 2BC8h; unsigned int
0x18018e865  xor     edx, edx; HINSTANCE
0x18018e867  mov     ecx, esi; int
0x18018e869  call    ?OriginateErrorWithResourceString@@YAXJPEAUHINSTANCE__@@I@Z; OriginateErrorWithResourceString(long,HINSTANCE__ *,uint)
0x18018e86e  jmp     loc_18018EA13
0x18018e873  mov     rcx, r14; struct Windows::ApplicationModel::Appointments::IAppointment *
0x18018e876  call    ?_ValidateAppointmentInternalImplementation@CBrokeredAppointmentsManager@@CAJPEAUIAppointment@Appointments@ApplicationModel@Windows@@@Z; CBrokeredAppointmentsManager::_ValidateAppointmentInternalImplementation(Windows::ApplicationModel::Appointments::IAppointment *)
0x18018e87b  mov     esi, eax
0x18018e87d  test    eax, eax
0x18018e87f  js      loc_18018EA13
0x18018e885  mov     rcx, r14; struct Windows::ApplicationModel::Appointments::IAppointment *
0x18018e888  call    ?_ValidateAppointmentPropertyValues@CBrokeredAppointmentsManager@@CAJPEAUIAppointment@Appointments@ApplicationModel@Windows@@@Z; CBrokeredAppointmentsManager::_ValidateAppointmentPropertyValues(Windows::ApplicationModel::Appointments::IAppointment *)
0x18018e88d  mov     esi, eax
0x18018e88f  test    eax, eax
0x18018e891  js      loc_18018EA13
0x18018e897  mov     rbx, r15
0x18018e89a  mov     [rbp+47h+var_80], r15
0x18018e89e  xor     edx, edx; unsigned __int16 **
0x18018e8a0  mov     [rbp+47h+var_A0], rbx
0x18018e8a4  lea     rcx, [rbp+47h+var_80]; this
0x18018e8a8  call    ?_GetCallingApplicationWindowAndVerifyVisibility@CBrokeredAppointmentsManager@@CAJPEAPEAUHWND__@@PEAPEAG@Z; CBrokeredAppointmentsManager::_GetCallingApplicationWindowAndVerifyVisibility(HWND__ * *,ushort * *)
0x18018e8ad  mov     esi, eax
0x18018e8af  test    eax, eax
0x18018e8b1  js      loc_18018EA04
0x18018e8b7  xor     ecx, ecx; pv
0x18018e8b9  call    cs:__imp_CoTaskMemFree
0x18018e8c0  nop     dword ptr [rax+rax+00h]
0x18018e8c5  lea     rcx, [rbp+47h+var_A0]; this
0x18018e8c9  call    ?GetCallingProcessPackageFamilyName@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessPackageFamilyName(ushort * *)
0x18018e8ce  mov     esi, eax
0x18018e8d0  test    eax, eax
0x18018e8d2  js      loc_18018EA00
0x18018e8d8  xor     ecx, ecx; pv
0x18018e8da  mov     [rbp+47h+var_98], r15
0x18018e8de  call    cs:__imp_CoTaskMemFree
0x18018e8e5  nop     dword ptr [rax+rax+00h]
0x18018e8ea  xor     edx, edx; length
0x18018e8ec  mov     rcx, rdi; string
0x18018e8ef  call    cs:__imp_WindowsGetStringRawBuffer
0x18018e8f6  nop     dword ptr [rax+rax+00h]
0x18018e8fb  mov     r8, rax
0x18018e8fe  lea     r9, [rbp+47h+var_98]
0x18018e902  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18018e907  mov     esi, eax
0x18018e909  test    eax, eax
0x18018e90b  js      loc_18018E9E7
0x18018e911  mov     rsi, [rbp+47h+arg_20]
0x18018e915  test    rsi, rsi
0x18018e918  jz      short loc_18018E922
0x18018e91a  mov     rsi, [rsi]
0x18018e91d  mov     r15b, 1
0x18018e920  jmp     short loc_18018E925
0x18018e922  mov     rsi, r15
0x18018e925  lea     rcx, [rbp+47h+var_78]
0x18018e929  mov     [rbp+47h+var_78], r14
0x18018e92d  call    ?InternalAddRef@?$ComPtr@UIWindowingEnvironmentConfig@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(void)
0x18018e932  mov     rax, [rbp+47h+var_98]
0x18018e936  xor     edi, edi
0x18018e938  mov     rcx, [rbp+47h+var_A0]
0x18018e93c  mov     [rbp+47h+var_70], rax
0x18018e940  mov     rax, qword ptr [rbp+47h+var_90]
0x18018e944  mov     [rbp+47h+var_48], rcx
0x18018e948  lea     rcx, [rbp+47h+var_38]
0x18018e94c  mov     [rbp+47h+var_58], r13d
0x18018e950  mov     [rbp+47h+var_54], r15b
0x18018e954  movups  xmm0, xmmword ptr [rax]
0x18018e957  mov     rax, [rbp+47h+var_80]
0x18018e95b  mov     [rbp+47h+var_50], rsi
0x18018e95f  movdqu  [rbp+47h+var_68], xmm0
0x18018e964  mov     [rbp+47h+var_40], rax
0x18018e968  mov     [rbp+47h+var_38], r14
0x18018e96c  call    ?InternalAddRef@?$ComPtr@UIWindowingEnvironmentConfig@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(void)
0x18018e971  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18018e978  mov     dword ptr [rbp+47h+var_90], 1
0x18018e97f  lea     ecx, [rdi+58h]; unsigned __int64
0x18018e982  mov     qword ptr [rbp+47h+var_90+4], 4
0x18018e98a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18018e98f  test    rax, rax
0x18018e992  jz      short loc_18018E9A0
0x18018e994  lea     rdx, [rbp+47h+var_70]
0x18018e998  mov     rcx, rax
0x18018e99b  call    ??$?0V_lambda_05f3cc7b8d847fd5ad9f7c464deabe87_@@@?$COperationLambdaVar@$0A@V_lambda_05f3cc7b8d847fd5ad9f7c464deabe87_@@VCHSTRINGResult@Internal@Windows@@$$V@Internal@Windows@@QEAA@$$QEAV_lambda_05f3cc7b8d847fd5ad9f7c464deabe87_@@@Z; Windows::Internal::COperationLambdaVar<0,_lambda_05f3cc7b8d847fd5ad9f7c464deabe87_,Windows::Internal::CHSTRINGResult,>::COperationLambdaVar<0,_lambda_05f3cc7b8d847fd5ad9f7c464deabe87_,Windows::Internal::CHSTRINGResult,>(_lambda_05f3cc7b8d847fd5ad9f7c464deabe87_ &&)
0x18018e9a0  mov     r9, rax
0x18018e9a3  lea     rcx, [rbp+47h+var_90]
0x18018e9a7  mov     rdx, r12
0x18018e9aa  call    ??$MakeAsyncOperationHelper@VCHSTRINGResult@Internal@Windows@@PEAUHSTRING__@@VComTaskPoolHandler@23@@Internal@Windows@@YAJ$$QEAVComTaskPoolHandler@01@PEAPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@1@W4TrustLevel@@PEAV?$AsyncCallbackBase@VCHSTRINGResult@Internal@Windows@@@01@@Z; Windows::Internal::MakeAsyncOperationHelper<Windows::Internal::CHSTRINGResult,HSTRING__ *,Windows::Internal::ComTaskPoolHandler>(Windows::Internal::ComTaskPoolHandler &&,Windows::Foundation::IAsyncOperation<HSTRING__ *> * *,TrustLevel,Windows::Internal::AsyncCallbackBase<Windows::Internal::CHSTRINGResult> *)
0x18018e9af  lea     rcx, [rbp+47h+var_70]; this
0x18018e9b3  mov     esi, eax
0x18018e9b5  call    ??1_lambda_05f3cc7b8d847fd5ad9f7c464deabe87_@@QEAA@XZ; _lambda_05f3cc7b8d847fd5ad9f7c464deabe87_::~_lambda_05f3cc7b8d847fd5ad9f7c464deabe87_(void)
0x18018e9ba  xor     ecx, ecx; pv
0x18018e9bc  call    cs:__imp_CoTaskMemFree
0x18018e9c3  nop     dword ptr [rax+rax+00h]
0x18018e9c8  xor     ecx, ecx; pv
0x18018e9ca  call    cs:__imp_CoTaskMemFree
0x18018e9d1  nop     dword ptr [rax+rax+00h]
0x18018e9d6  mov     rax, [r14]
0x18018e9d9  mov     rcx, r14
0x18018e9dc  mov     rax, [rax+10h]
0x18018e9e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e9e5  jmp     short loc_18018E9EF
0x18018e9e7  mov     rbx, [rbp+47h+var_A0]
0x18018e9eb  mov     rdi, [rbp+47h+var_98]
0x18018e9ef  mov     rcx, rdi; pv
0x18018e9f2  call    cs:__imp_CoTaskMemFree
0x18018e9f9  nop     dword ptr [rax+rax+00h]
0x18018e9fe  jmp     short loc_18018EA04
0x18018ea00  mov     rbx, [rbp+47h+var_A0]
0x18018ea04  mov     rcx, rbx; pv
0x18018ea07  call    cs:__imp_CoTaskMemFree
0x18018ea0e  nop     dword ptr [rax+rax+00h]
0x18018ea13  mov     rbx, [rsp+0C0h+arg_10]
0x18018ea1b  mov     eax, esi
0x18018ea1d  add     rsp, 90h
0x18018ea24  pop     r15
0x18018ea26  pop     r14
0x18018ea28  pop     r13
0x18018ea2a  pop     r12
0x18018ea2c  pop     rdi
0x18018ea2d  pop     rsi
0x18018ea2e  pop     rbp
0x18018ea2f  retn
```
