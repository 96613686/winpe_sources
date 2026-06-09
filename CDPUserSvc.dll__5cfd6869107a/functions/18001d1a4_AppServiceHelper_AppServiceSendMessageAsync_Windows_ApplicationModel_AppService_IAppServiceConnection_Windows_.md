# AppServiceHelper::AppServiceSendMessageAsync(Windows::ApplicationModel::AppService::IAppServiceConnection *,Windows::Foundation::Collections::IPropertySet *,Windows::Foundation::Collections::IPropertySet * *,HSTRING__ * *)

- ea: `0x18001d1a4`
- end: `0x18001d546`
- name: `?AppServiceSendMessageAsync@AppServiceHelper@@AEAAJPEAUIAppServiceConnection@AppService@ApplicationModel@Windows@@PEAUIPropertySet@Collections@Foundation@5@PEAPEAU6785@PEAPEAUHSTRING__@@@Z`
- size: `930`
- prototype: `__int64 __fastcall(AppServiceHelper *__hidden this, struct Windows::ApplicationModel::AppService::IAppServiceConnection *, struct Windows::Foundation::Collections::IPropertySet *, struct Windows::Foundation::Collections::IPropertySet **, HSTRING *)`
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001e0f0`

## callees

- `0x180003678`
- `0x18000eb48`
- `0x18001d1a4`
- `0x18001d54c`
- `0x18001d5a4`
- `0x18001d678`
- `0x18001e798`
- `0x180021398`
- `0x180025114`
- `0x18002c5a0`
- `0x18003a524`
- `0x18003af00`
- `0x18003b66c`
- `0x18003b7c4`
- `0x18003baac`
- `0x18003bc34`
- `0x18003e1ec`
- `0x18003e418`
- `0x18003e618`
- `0x18003e6b0`
- `0x18003e914`
- `0x180064010`

## string_xrefs

- `0x18001d24f`: `..\appservicehelper.cpp`
- `0x18001d385`: `..\appservicehelper.cpp`
- `0x18001d411`: `..\appservicehelper.cpp`
- `0x18001d4d2`: `..\appservicehelper.cpp`
- `0x18001d4f0`: `..\appservicehelper.cpp`
- `0x18001d267`: `Sending Input Message to App Service...`
- `0x18001d454`: `Received response from App Service.`
- `0x18001d46c`: `Failure waiting on response from App Service connection. AppServiceResponseStatus = %d.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall AppServiceHelper::AppServiceSendMessageAsync(
        AppServiceHelper *this,
        struct Windows::ApplicationModel::AppService::IAppServiceConnection *a2,
        struct Windows::Foundation::Collections::IPropertySet *a3,
        struct Windows::Foundation::Collections::IPropertySet **a4,
        HSTRING *a5)
{
  HSTRING *v9; // rsi
  __int64 (__fastcall *v10)(struct Windows::ApplicationModel::AppService::IAppServiceConnection *, struct Windows::Foundation::Collections::IPropertySet *, _QWORD); // rbx
  int v11; // eax
  int v12; // ebx
  __int64 v13; // rdx
  __int64 (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v15)(_QWORD, GUID *, __int64 *); // rdi
  char *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rbx
  __int64 v20; // r8
  unsigned __int64 v21; // r9
  __int64 v22; // rdx
  __int64 v23; // rdi
  int v24; // eax
  __int64 v25; // rcx
  __int64 (__fastcall *v26)(__int64, struct Windows::Foundation::Collections::IPropertySet **); // rbx
  int v27; // eax
  HSTRING v28; // rax
  int v29; // eax
  __int64 (__fastcall ***v31)(_QWORD, GUID *, __int64 *); // [rsp+20h] [rbp-60h] BYREF
  __int64 v32; // [rsp+28h] [rbp-58h] BYREF
  _QWORD v33[2]; // [rsp+30h] [rbp-50h] BYREF
  char *v34; // [rsp+40h] [rbp-40h] BYREF
  HSTRING v35; // [rsp+48h] [rbp-38h]
  __int64 v36; // [rsp+50h] [rbp-30h]
  __int64 v37; // [rsp+58h] [rbp-28h]
  __int64 v38; // [rsp+60h] [rbp-20h] BYREF
  char v39; // [rsp+68h] [rbp-18h]
  char v40; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  struct Windows::Foundation::Collections::IPropertySet *v42; // [rsp+B8h] [rbp+38h] BYREF

  v9 = a5;
  if ( a5 )
    *a5 = 0;
  v31 = 0;
  v32 = 0;
  v10 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::AppService::IAppServiceConnection *, struct Windows::Foundation::Collections::IPropertySet *, _QWORD))(*(_QWORD *)a2 + 88LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  v11 = v10(a2, a3, &v31);
  v12 = v11;
  if ( v11 >= 0 )
  {
    v14 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v31;
    v15 = **v31;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
    v11 = v15(v14, &GUID_00000036_0000_0000_c000_000000000046, &v32);
    v12 = v11;
    if ( v11 < 0 )
    {
      v13 = 165;
      goto LABEL_7;
    }
    Log<>(4u, "Sending Input Message to App Service...");
    v42 = (struct Windows::Foundation::Collections::IPropertySet *)operator new(0xE8u);
    v38 = std::_Associated_state__AppServiceHelper::AppServiceSendMessageAsync_::_2_::AppServiceResponseData_::_Associated_state__AppServiceHelper::AppServiceSendMessageAsync_::_2_::AppServiceResponseData_(v42);
    v39 = 0;
    v40 = 0;
    std::promise__AppServiceHelper::AppServiceSendMessageAsync_::_2_::AppServiceResponseData_::get_future(&v38, v33);
    v16 = (char *)v38;
    v38 = 0;
    v34 = v16;
    LOBYTE(v35) = 0;
    LOBYTE(v36) = v40;
    v17 = *((_QWORD *)this + 4);
    v37 = v17;
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
    v12 = wil::details::RunWhenComplete_Microsoft::WRL::FtmBase_Windows::Foundation::IAsyncOperation_Windows::ApplicationModel::AppService::AppServiceResponse_______lambda_30cff97d3f7625d10a256c38f131431f___(
            v31,
            &v34);
    lambda_30cff97d3f7625d10a256c38f131431f_::__lambda_30cff97d3f7625d10a256c38f131431f_(&v34);
    if ( v12 < 0 )
    {
      v18 = 189;
LABEL_39:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"..\\appservicehelper.cpp",
        (const char *)(unsigned int)v12,
        (int)v31);
      goto LABEL_40;
    }
    if ( !(unsigned __int8)std::_State_manager__AppServiceHelper::AppServiceSendMessageAsync_::_2_::AppServiceResponseData_::valid(v33) )
      std::_Throw_future_error2(4);
    v19 = v33[0];
    std::unique_lock<std::mutex>::unique_lock<std::mutex>(&v34, v33[0] + 56LL);
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v19 + 24LL))(v19)
      || !(unsigned __int8)std::condition_variable::wait_for___int64_std::ratio_1_1__std::_Associated_state__AppServiceHelper::AppServiceSendMessageAsync_::_2_::AppServiceResponseData_::_Test_ready_(
                             v19 + 136,
                             &v34,
                             v20,
                             v19) )
    {
      std::unique_lock<std::mutex>::~unique_lock<std::mutex>(&v34);
      v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 72LL))(v32);
      if ( v29 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xC1,
          (unsigned int)"..\\appservicehelper.cpp",
          (const char *)(unsigned int)v29,
          (int)v31);
      v12 = -2147217657;
      v18 = 194;
      goto LABEL_39;
    }
    std::unique_lock<std::mutex>::~unique_lock<std::mutex>(&v34);
    std::future__AppServiceHelper::AppServiceSendMessageAsync_::_2_::AppServiceResponseData_::get(v33, &v34);
    v12 = (int)v34;
    if ( (int)v34 >= 0 )
    {
      v23 = v36;
      LODWORD(a5) = 3;
      v24 = (*(__int64 (__fastcall **)(__int64, HSTRING **))(*(_QWORD *)v36 + 56LL))(v36, &a5);
      v12 = v24;
      if ( v24 >= 0 )
      {
        if ( (_DWORD)a5 )
        {
          LODWORD(v42) = (_DWORD)a5;
          Log<int>(
            v25,
            "Failure waiting on response from App Service connection. AppServiceResponseStatus = %d.",
            (unsigned int)&v42);
          if ( (_DWORD)a5 )
          {
            if ( (_DWORD)a5 == 1 )
            {
              v12 = -2147217659;
            }
            else if ( (_DWORD)a5 == 2 )
            {
              v12 = -2147217658;
            }
            else
            {
              v12 = -2147217656;
            }
          }
          else
          {
            v12 = 0;
          }
        }
        else
        {
          v42 = 0;
          v26 = *(__int64 (__fastcall **)(__int64, struct Windows::Foundation::Collections::IPropertySet **))(*(_QWORD *)v23 + 48LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
          v27 = v26(v23, &v42);
          v12 = v27;
          if ( v27 >= 0 )
          {
            v12 = 0;
            Microsoft::WRL::ComPtr<MobilityExperienceResourceHandler>::InternalAddRef(&v42);
            *a4 = v42;
            if ( v9 )
            {
              v28 = v35;
              v35 = 0;
              *v9 = v28;
            }
            Log<>(4u, "Received response from App Service.");
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xCE,
              (unsigned int)"..\\appservicehelper.cpp",
              (const char *)(unsigned int)v27,
              (int)v31);
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
        }
        goto LABEL_19;
      }
      v21 = (unsigned int)v24;
      v22 = 202;
    }
    else
    {
      v21 = (unsigned int)v34;
      v22 = 198;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"..\\appservicehelper.cpp",
      (const char *)v21,
      (int)v31);
LABEL_19:
    AppServiceHelper::AppServiceSendMessageAsync_::_2_::AppServiceResponseData::_AppServiceResponseData(&v34);
LABEL_40:
    std::_State_manager__AppServiceHelper::AppServiceSendMessageAsync_::_2_::AppServiceResponseData_::__State_manager__AppServiceHelper::AppServiceSendMessageAsync_::_2_::AppServiceResponseData_(v33);
    std::promise__AppServiceHelper::AppServiceSendMessageAsync_::_2_::AppServiceResponseData_::_promise__AppServiceHelper::AppServiceSendMessageAsync_::_2_::AppServiceResponseData_(&v38);
    goto LABEL_41;
  }
  v13 = 164;
LABEL_7:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v13,
    (unsigned int)"..\\appservicehelper.cpp",
    (const char *)(unsigned int)v11,
    (int)v31);
LABEL_41:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001d1a4  mov     [rsp-28h+arg_0], rbx
0x18001d1a9  mov     [rsp-28h+arg_10], rsi
0x18001d1ae  push    rbp
0x18001d1af  push    rdi
0x18001d1b0  push    r12
0x18001d1b2  push    r14
0x18001d1b4  push    r15
0x18001d1b6  mov     rbp, rsp
0x18001d1b9  sub     rsp, 80h
0x18001d1c0  mov     r12, r9
0x18001d1c3  mov     r14, r8
0x18001d1c6  mov     rdi, rdx
0x18001d1c9  mov     r15, rcx
0x18001d1cc  mov     rsi, [rbp+arg_20]
0x18001d1d0  test    rsi, rsi
0x18001d1d3  jz      short loc_18001D1DC
0x18001d1d5  mov     qword ptr [rsi], 0
0x18001d1dc  mov     [rbp+var_60], 0
0x18001d1e4  mov     [rbp+var_58], 0
0x18001d1ec  mov     rax, [rdx]
0x18001d1ef  mov     rbx, [rax+58h]
0x18001d1f3  lea     rcx, [rbp+var_60]
0x18001d1f7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d1fc  lea     r8, [rbp+var_60]
0x18001d200  mov     rdx, r14
0x18001d203  mov     rcx, rdi
0x18001d206  mov     rax, rbx
0x18001d209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d20e  mov     ebx, eax
0x18001d210  test    eax, eax
0x18001d212  jns     short loc_18001D21B
0x18001d214  mov     edx, 0A4h
0x18001d219  jmp     short loc_18001D24F
0x18001d21b  mov     rbx, [rbp+var_60]
0x18001d21f  mov     rax, [rbx]
0x18001d222  mov     rdi, [rax]
0x18001d225  lea     rcx, [rbp+var_58]
0x18001d229  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d22e  lea     r8, [rbp+var_58]
0x18001d232  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18001d239  mov     rcx, rbx
0x18001d23c  mov     rax, rdi
0x18001d23f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d244  mov     ebx, eax
0x18001d246  test    eax, eax
0x18001d248  jns     short loc_18001D267
0x18001d24a  mov     edx, 0A5h; void *
0x18001d24f  lea     r8, aAppservicehelp; "..\\appservicehelper.cpp"
0x18001d256  mov     r9d, eax; char *
0x18001d259  mov     rcx, [rbp+28h]; this
0x18001d25d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d262  jmp     loc_18001D515
0x18001d267  lea     rdx, aSendingInputMe; "Sending Input Message to App Service..."
0x18001d26e  mov     r14d, 4
0x18001d274  mov     ecx, r14d
0x18001d277  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x18001d27c  mov     ecx, 0E8h; Size
0x18001d281  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d286  mov     [rbp+arg_8], rax
0x18001d28a  mov     rcx, rax
0x18001d28d  call    std___Associated_state__AppServiceHelper__AppServiceSendMessageAsync____2___AppServiceResponseData____Associated_state__AppServiceHelper__AppServiceSendMessageAsync____2___AppServiceResponseData_
0x18001d292  mov     [rbp+var_20], rax
0x18001d296  mov     [rbp+var_18], 0
0x18001d29a  mov     [rbp+var_10], 0
0x18001d29e  lea     rdx, [rbp+var_50]
0x18001d2a2  lea     rcx, [rbp+var_20]
0x18001d2a6  call    std__promise__AppServiceHelper__AppServiceSendMessageAsync____2___AppServiceResponseData___get_future
0x18001d2ab  nop
0x18001d2ac  mov     rax, [rbp+var_20]
0x18001d2b0  mov     [rbp+var_20], 0
0x18001d2b8  mov     [rbp+var_40], rax
0x18001d2bc  mov     byte ptr [rbp+var_38], 0
0x18001d2c0  mov     al, [rbp+var_10]
0x18001d2c3  mov     byte ptr [rbp+var_30], al
0x18001d2c6  mov     rcx, [r15+20h]
0x18001d2ca  mov     [rbp+var_28], rcx
0x18001d2ce  test    rcx, rcx
0x18001d2d1  jz      short loc_18001D2E0
0x18001d2d3  mov     rax, [rcx]
0x18001d2d6  mov     rax, [rax+8]
0x18001d2da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2df  nop
0x18001d2e0  lea     rdx, [rbp+var_40]
0x18001d2e4  mov     rcx, [rbp+var_60]
0x18001d2e8  call    wil__details__RunWhenComplete_Microsoft__WRL__FtmBase_Windows__Foundation__IAsyncOperation_Windows__ApplicationModel__AppService__AppServiceResponse_______lambda_30cff97d3f7625d10a256c38f131431f___
0x18001d2ed  mov     ebx, eax
0x18001d2ef  lea     rcx, [rbp+var_40]
0x18001d2f3  call    _lambda_30cff97d3f7625d10a256c38f131431f_____lambda_30cff97d3f7625d10a256c38f131431f_
0x18001d2f8  test    ebx, ebx
0x18001d2fa  jns     short loc_18001D306
0x18001d2fc  mov     edx, 0BDh
0x18001d301  jmp     loc_18001D4ED
0x18001d306  lea     rcx, [rbp+var_50]
0x18001d30a  call    std___State_manager__AppServiceHelper__AppServiceSendMessageAsync____2___AppServiceResponseData___valid
0x18001d30f  test    al, al
0x18001d311  jnz     short loc_18001D31C
0x18001d313  mov     ecx, r14d
0x18001d316  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x18001d31c  mov     rbx, [rbp+var_50]
0x18001d320  lea     rdx, [rbx+38h]
0x18001d324  lea     rcx, [rbp+var_40]
0x18001d328  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18001d32d  mov     rax, [rbx]
0x18001d330  mov     rcx, rbx
0x18001d333  mov     rax, [rax+18h]
0x18001d337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d33c  test    al, al
0x18001d33e  jnz     loc_18001D4AE
0x18001d344  lea     rcx, [rbx+88h]
0x18001d34b  mov     r9, rbx
0x18001d34e  lea     rdx, [rbp+var_40]
0x18001d352  call    std__condition_variable__wait_for___int64_std__ratio_1_1__std___Associated_state__AppServiceHelper__AppServiceSendMessageAsync____2___AppServiceResponseData____Test_ready_
0x18001d357  test    al, al
0x18001d359  jz      loc_18001D4AE
0x18001d35f  lea     rcx, [rbp+var_40]
0x18001d363  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18001d368  lea     rdx, [rbp+var_40]
0x18001d36c  lea     rcx, [rbp+var_50]
0x18001d370  call    std__future__AppServiceHelper__AppServiceSendMessageAsync____2___AppServiceResponseData___get
0x18001d375  nop
0x18001d376  mov     ebx, dword ptr [rbp+var_40]
0x18001d379  test    ebx, ebx
0x18001d37b  jns     short loc_18001D3A4
0x18001d37d  mov     r9d, ebx; char *
0x18001d380  mov     edx, 0C6h; void *
0x18001d385  lea     r8, aAppservicehelp; "..\\appservicehelper.cpp"
0x18001d38c  mov     rcx, [rbp+28h]; this
0x18001d390  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d395  nop
0x18001d396  lea     rcx, [rbp+var_40]
0x18001d39a  call    _AppServiceHelper__AppServiceSendMessageAsync____2___AppServiceResponseData___AppServiceResponseData
0x18001d39f  jmp     loc_18001D501
0x18001d3a4  mov     rdi, [rbp+var_30]
0x18001d3a8  mov     dword ptr [rbp+arg_20], 3
0x18001d3af  mov     rax, [rdi]
0x18001d3b2  lea     rdx, [rbp+arg_20]
0x18001d3b6  mov     rcx, rdi
0x18001d3b9  mov     rax, [rax+38h]
0x18001d3bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3c2  mov     ebx, eax
0x18001d3c4  test    eax, eax
0x18001d3c6  jns     short loc_18001D3D2
0x18001d3c8  mov     r9d, eax
0x18001d3cb  mov     edx, 0CAh
0x18001d3d0  jmp     short loc_18001D385
0x18001d3d2  mov     eax, dword ptr [rbp+arg_20]
0x18001d3d5  test    eax, eax
0x18001d3d7  jnz     loc_18001D465
0x18001d3dd  mov     [rbp+arg_8], 0
0x18001d3e5  mov     rax, [rdi]
0x18001d3e8  mov     rbx, [rax+30h]
0x18001d3ec  lea     rcx, [rbp+arg_8]
0x18001d3f0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d3f5  lea     rdx, [rbp+arg_8]
0x18001d3f9  mov     rcx, rdi
0x18001d3fc  mov     rax, rbx
0x18001d3ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d404  mov     ebx, eax
0x18001d406  test    eax, eax
0x18001d408  jns     short loc_18001D431
0x18001d40a  mov     rcx, [rbp+28h]; this
0x18001d40e  mov     r9d, eax; char *
0x18001d411  lea     r8, aAppservicehelp; "..\\appservicehelper.cpp"
0x18001d418  mov     edx, 0CEh; void *
0x18001d41d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d422  nop
0x18001d423  lea     rcx, [rbp+arg_8]
0x18001d427  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d42c  jmp     loc_18001D396
0x18001d431  xor     ebx, ebx
0x18001d433  lea     rcx, [rbp+arg_8]
0x18001d437  call    ?InternalAddRef@?$ComPtr@VMobilityExperienceResourceHandler@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MobilityExperienceResourceHandler>::InternalAddRef(void)
0x18001d43c  mov     rax, [rbp+arg_8]
0x18001d440  mov     [r12], rax
0x18001d444  test    rsi, rsi
0x18001d447  jz      short loc_18001D454
0x18001d449  mov     rax, [rbp+var_38]
0x18001d44d  mov     [rbp+var_38], rbx
0x18001d451  mov     [rsi], rax
0x18001d454  lea     rdx, aReceivedRespon; "Received response from App Service."
0x18001d45b  mov     ecx, r14d
0x18001d45e  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x18001d463  jmp     short loc_18001D423
0x18001d465  mov     dword ptr [rbp+arg_8], eax
0x18001d468  lea     r8, [rbp+arg_8]
0x18001d46c  lea     rdx, aFailureWaiting; "Failure waiting on response from App Se"...
0x18001d473  call    ??$Log@H@@YAXW4CDPLogLevel@@PEBD$$QEAH@Z; Log<int>(CDPLogLevel,char const *,int &&)
0x18001d478  mov     ecx, dword ptr [rbp+arg_20]
0x18001d47b  test    ecx, ecx
0x18001d47d  jz      short loc_18001D4A7
0x18001d47f  sub     ecx, 1
0x18001d482  jz      short loc_18001D49D
0x18001d484  sub     ecx, 1
0x18001d487  jz      short loc_18001D493
0x18001d489  mov     ebx, 80040F08h
0x18001d48e  jmp     loc_18001D396
0x18001d493  mov     ebx, 80040F06h
0x18001d498  jmp     loc_18001D396
0x18001d49d  mov     ebx, 80040F05h
0x18001d4a2  jmp     loc_18001D396
0x18001d4a7  xor     ebx, ebx
0x18001d4a9  jmp     loc_18001D396
0x18001d4ae  lea     rcx, [rbp+var_40]
0x18001d4b2  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18001d4b7  mov     rcx, [rbp+var_58]
0x18001d4bb  mov     rax, [rcx]
0x18001d4be  mov     rax, [rax+48h]
0x18001d4c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4c7  mov     rcx, [rbp+28h]; this
0x18001d4cb  test    eax, eax
0x18001d4cd  jns     short loc_18001D4E3
0x18001d4cf  mov     r9d, eax; char *
0x18001d4d2  lea     r8, aAppservicehelp; "..\\appservicehelper.cpp"
0x18001d4d9  mov     edx, 0C1h; void *
0x18001d4de  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d4e3  mov     ebx, 80040F07h
0x18001d4e8  mov     edx, 0C2h; void *
0x18001d4ed  mov     r9d, ebx; char *
0x18001d4f0  lea     r8, aAppservicehelp; "..\\appservicehelper.cpp"
0x18001d4f7  mov     rcx, [rbp+28h]; this
0x18001d4fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d500  nop
0x18001d501  lea     rcx, [rbp+var_50]
0x18001d505  call    std___State_manager__AppServiceHelper__AppServiceSendMessageAsync____2___AppServiceResponseData_____State_manager__AppServiceHelper__AppServiceSendMessageAsync____2___AppServiceResponseData_
0x18001d50a  nop
0x18001d50b  lea     rcx, [rbp+var_20]
0x18001d50f  call    std__promise__AppServiceHelper__AppServiceSendMessageAsync____2___AppServiceResponseData____promise__AppServiceHelper__AppServiceSendMessageAsync____2___AppServiceResponseData_
0x18001d514  nop
0x18001d515  lea     rcx, [rbp+var_58]
0x18001d519  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d51e  nop
0x18001d51f  lea     rcx, [rbp+var_60]
0x18001d523  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d528  mov     eax, ebx
0x18001d52a  lea     r11, [rsp+80h+var_s0]
0x18001d532  mov     rbx, [r11+30h]
0x18001d536  mov     rsi, [r11+40h]
0x18001d53a  mov     rsp, r11
0x18001d53d  pop     r15
0x18001d53f  pop     r14
0x18001d541  pop     r12
0x18001d543  pop     rdi
0x18001d544  pop     rbp
0x18001d545  retn
```
