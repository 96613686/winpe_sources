# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::UI::Credentials::Controller::RequestCredentialsData *>,Windows::Foundation::IAsyncOperation<Windows::Internal::UI::Credentials::Controller::RequestCredentialsData *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::UI::Credentials::Controller::RequestCredentialsData *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x140006f50`
- end: `0x1400070e6`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVRequestCredentialsData@Controller@Credentials@UI@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVRequestCredentialsData@Controller@Credentials@UI@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVRequestCredentialsData@Controller@Credentials@UI@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `406`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), DWORD, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400111ac`

## callees

- `0x140005dd4`
- `0x140006f50`
- `0x14000e920`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x140006ffd`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x140006ffd`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::UI::Credentials::Controller::RequestCredentialsData *>,Windows::Foundation::IAsyncOperation<Windows::Internal::UI::Credentials::Controller::RequestCredentialsData *>>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        DWORD a2,
        void *a3)
{
  unsigned int v6; // edi
  __int64 v7; // rbx
  void *v8; // rax
  int (__fastcall **v9)(_QWORD, GUID *, __int64 *); // rax
  int (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rdi
  int (__fastcall *v11)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v13; // [rsp+30h] [rbp-30h] BYREF
  __int64 v14; // [rsp+38h] [rbp-28h] BYREF
  int (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // [rsp+40h] [rbp-20h] BYREF
  HANDLE pHandles[3]; // [rsp+48h] [rbp-18h] BYREF
  int v17; // [rsp+90h] [rbp+30h] BYREF
  DWORD dwindex; // [rsp+A8h] [rbp+48h] BYREF

  v15 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))a1;
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[1])(a1);
  v14 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  v17 = ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVRequestCredentialsData_Controller_Credentials_UI_Internal_Windows___Foundation_Windows__U__IAsyncOperation_PEAVRequestCredentialsData_Controller_Credentials_UI_Internal_Windows___23___YAJPEAU__IAsyncOperation_PEAVRequestCredentialsData_Controller_Credentials_UI_Internal_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVRequestCredentialsData_Controller_Credentials_UI_Internal_Windows___Foundation_Windows__U__IAsyncOperation_PEAVRequestCredentialsData_Controller_Credentials_UI_Internal_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVRequestCredentialsData_Controller_Credentials_UI_Internal_Windows___Foundation_Windows__U__IAsyncOperation_PEAVRequestCredentialsData_Controller_Credentials_UI_Internal_Windows___23___YAJPEAU__IAsyncOperation_PEAVRequestCredentialsData_Controller_Credentials_UI_Internal_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(&v14);
  v6 = v17;
  if ( v17 >= 0 )
  {
    v7 = v14;
    v17 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*a1)[6])(a1, v14);
    v6 = v17;
    if ( v17 >= 0 )
    {
      v8 = *(void **)(v7 + 56);
      pHandles[1] = a3;
      pHandles[0] = v8;
      dwindex = 0;
      v17 = CoWaitForMultipleHandles(a2, 0xFFFFFFFF, (a3 != 0) + 1, pHandles, &dwindex);
      if ( v17 >= 0 && dwindex )
      {
        v9 = *a1;
        v17 = -2147023673;
        v13 = 0;
        v10 = *v9;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
        if ( v10(a1, &GUID_00000036_0000_0000_c000_000000000046, &v13) >= 0 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 72LL))(v13);
      }
      else
      {
        v13 = 0;
      }
      if ( v17 >= 0 && *(_DWORD *)(v7 + 48) != 1 )
      {
        if ( v13
          || (v11 = **a1,
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13),
              v11(a1, &GUID_00000036_0000_0000_c000_000000000046, &v13) >= 0) )
        {
          (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v13 + 64LL))(v13, &v17);
        }
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
      v6 = v17;
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  return v6;
}

```

## disassembly

```asm
0x140006f50  mov     [rsp-28h+arg_8], rbx
0x140006f55  push    rbp
0x140006f56  push    rsi
0x140006f57  push    rdi
0x140006f58  push    r14
0x140006f5a  push    r15
0x140006f5c  mov     rbp, rsp
0x140006f5f  sub     rsp, 60h
0x140006f63  mov     [rbp+var_20], rcx
0x140006f67  mov     r14, r8
0x140006f6a  mov     r15d, edx
0x140006f6d  mov     rsi, rcx
0x140006f70  test    rcx, rcx
0x140006f73  jz      short loc_140006F81
0x140006f75  mov     rax, [rcx]
0x140006f78  mov     rax, [rax+8]
0x140006f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006f81  lea     rcx, [rbp+var_28]
0x140006f85  mov     [rbp+var_28], 0
0x140006f8d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140006f92  lea     rcx, [rbp+var_28]
0x140006f96  call    ??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVRequestCredentialsData@Controller@Credentials@UI@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVRequestCredentialsData@Controller@Credentials@UI@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVRequestCredentialsData@Controller@Credentials@UI@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVRequestCredentialsData@Controller@Credentials@UI@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVRequestCredentialsData@Controller@Credentials@UI@Internal@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVRequestCredentialsData@Controller@Credentials@UI@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVRequestCredentialsData@Controller@Credentials@UI@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVRequestCredentialsData@Controller@Credentials@UI@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::UI::Credentials::Controller::RequestCredentialsData *>,Windows::Foundation::IAsyncOperation<Windows::Internal::UI::Credentials::Controller::RequestCredentialsData *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::UI::Credentials::Controller::RequestCredentialsData *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::UI::Credentials::Controller::RequestCredentialsData *>,Windows::Foundation::IAsyncOperation<Windows::Internal::UI::Credentials::Controller::RequestCredentialsData *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::UI::Credentials::Controller::RequestCredentialsData *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::UI::Credentials::Controller::RequestCredentialsData *>,Windows::Foundation::IAsyncOperation<Windows::Internal::UI::Credentials::Controller::RequestCredentialsData *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::UI::Credentials::Controller::RequestCredentialsData *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)
0x140006f9b  mov     [rbp+arg_0], eax
0x140006f9e  mov     edi, eax
0x140006fa0  test    eax, eax
0x140006fa2  js      loc_1400070BE
0x140006fa8  mov     rax, [rsi]
0x140006fab  mov     rcx, rsi
0x140006fae  mov     rbx, [rbp+var_28]
0x140006fb2  mov     rdx, rbx
0x140006fb5  mov     rax, [rax+30h]
0x140006fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006fbe  mov     [rbp+arg_0], eax
0x140006fc1  mov     edi, eax
0x140006fc3  test    eax, eax
0x140006fc5  js      loc_1400070BE
0x140006fcb  mov     rax, [rbx+38h]
0x140006fcf  lea     r9, [rbp+pHandles]; pHandles
0x140006fd3  mov     [rbp+var_10], r14
0x140006fd7  mov     ecx, r15d; dwFlags
0x140006fda  mov     [rbp+pHandles], rax
0x140006fde  neg     r14
0x140006fe1  lea     rax, [rbp+dwindex]
0x140006fe5  mov     [rbp+dwindex], 0
0x140006fec  sbb     r8d, r8d
0x140006fef  mov     [rsp+60h+lpdwindex], rax; lpdwindex
0x140006ff4  neg     r8d
0x140006ff7  or      edx, 0FFFFFFFFh; dwTimeout
0x140006ffa  inc     r8d; cHandles
0x140006ffd  call    cs:__imp_CoWaitForMultipleHandles
0x140007003  mov     [rbp+arg_0], eax
0x140007006  test    eax, eax
0x140007008  js      short loc_14000705A
0x14000700a  cmp     [rbp+dwindex], 0
0x14000700e  jz      short loc_14000705A
0x140007010  mov     rax, [rsi]
0x140007013  lea     rcx, [rbp+var_30]
0x140007017  mov     [rbp+arg_0], 800704C7h
0x14000701e  mov     [rbp+var_30], 0
0x140007026  mov     rdi, [rax]
0x140007029  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000702e  lea     r8, [rbp+var_30]
0x140007032  mov     rcx, rsi
0x140007035  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x14000703c  mov     rax, rdi
0x14000703f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007044  test    eax, eax
0x140007046  js      short loc_140007062
0x140007048  mov     rcx, [rbp+var_30]
0x14000704c  mov     rax, [rcx]
0x14000704f  mov     rax, [rax+48h]
0x140007053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007058  jmp     short loc_140007062
0x14000705a  mov     [rbp+var_30], 0
0x140007062  cmp     [rbp+arg_0], 0
0x140007066  jl      short loc_1400070B2
0x140007068  cmp     dword ptr [rbx+30h], 1
0x14000706c  jz      short loc_1400070B2
0x14000706e  cmp     [rbp+var_30], 0
0x140007073  jnz     short loc_14000709E
0x140007075  mov     rax, [rsi]
0x140007078  lea     rcx, [rbp+var_30]
0x14000707c  mov     rbx, [rax]
0x14000707f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140007084  lea     r8, [rbp+var_30]
0x140007088  mov     rcx, rsi
0x14000708b  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x140007092  mov     rax, rbx
0x140007095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000709a  test    eax, eax
0x14000709c  js      short loc_1400070B2
0x14000709e  mov     rcx, [rbp+var_30]
0x1400070a2  lea     rdx, [rbp+arg_0]
0x1400070a6  mov     rax, [rcx]
0x1400070a9  mov     rax, [rax+40h]
0x1400070ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400070b2  lea     rcx, [rbp+var_30]
0x1400070b6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400070bb  mov     edi, [rbp+arg_0]
0x1400070be  lea     rcx, [rbp+var_28]
0x1400070c2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400070c7  lea     rcx, [rbp+var_20]
0x1400070cb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400070d0  mov     rbx, [rsp+60h+arg_8]
0x1400070d8  mov     eax, edi
0x1400070da  add     rsp, 60h
0x1400070de  pop     r15
0x1400070e0  pop     r14
0x1400070e2  pop     rdi
0x1400070e3  pop     rsi
0x1400070e4  pop     rbp
0x1400070e5  retn
```
