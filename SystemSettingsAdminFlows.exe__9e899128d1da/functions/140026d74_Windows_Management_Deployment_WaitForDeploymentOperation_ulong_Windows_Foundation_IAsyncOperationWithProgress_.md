# Windows::Management::Deployment::WaitForDeploymentOperation(ulong,Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Management::Deployment::IDeploymentResult * *)

- ea: `0x140026d74`
- end: `0x140026f5b`
- name: `?WaitForDeploymentOperation@Deployment@Management@Windows@@YAJKPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@3@PEAU?$IAsyncOperationProgressHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@53@PEAU?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@53@PEAPEAUIDeploymentResult@123@@Z`
- size: `487`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14006403c`
- `0x140066e60`

## callees

- `0x14000a274`
- `0x14001a2a0`
- `0x14001cdc0`
- `0x140026d74`
- `0x14007d010`

## import_xrefs

- `KERNEL32!CreateEventExW` at `0x140026da8`
- `KERNEL32!CreateEventExW` at `0x140026da8`
- `KERNEL32!CloseHandle` at `0x140026f28`
- `KERNEL32!CloseHandle` at `0x140026f28`
- `KERNEL32!GetLastError` at `0x140026db6`
- `KERNEL32!GetLastError` at `0x140026e8c`
- `KERNEL32!GetLastError` at `0x140026db6`
- `KERNEL32!GetLastError` at `0x140026e8c`
- `KERNEL32!WaitForSingleObject` at `0x140026e71`
- `KERNEL32!WaitForSingleObject` at `0x140026e71`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 Windows::Management::Deployment::WaitForDeploymentOperation(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        __int64 a3,
        ...)
{
  __int64 v4; // rbx
  HANDLE Event; // rax
  void *v6; // r14
  signed int v7; // eax
  signed int v8; // edi
  __int64 *v9; // rax
  __int64 (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rdi
  DWORD v11; // eax
  signed int LastError; // eax
  __int128 v14; // [rsp+20h] [rbp-10h] BYREF
  int v15; // [rsp+60h] [rbp+30h] BYREF
  __int64 v16; // [rsp+70h] [rbp+40h] BYREF
  __int64 v17; // [rsp+78h] [rbp+48h] BYREF
  va_list va; // [rsp+78h] [rbp+48h]
  __int64 v19; // [rsp+80h] [rbp+50h]
  va_list va1; // [rsp+88h] [rbp+58h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v17 = va_arg(va1, _QWORD);
  v19 = va_arg(va1, _QWORD);
  v4 = 0;
  v16 = 0;
  v15 = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  v6 = Event;
  if ( Event )
  {
    v14 = (unsigned __int64)Event;
    v9 = Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IAsyncOperationWithProgressCompletedHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::IDeploymentResult *>,Windows::Management::Deployment::DeploymentProgress>::*)(Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,enum ABI::Windows::Foundation::AsyncStatus)>::DelegateInvokeHelper<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,_lambda_9a0aae7dbba35881869cec547d91271e_,-1,Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,enum ABI::Windows::Foundation::AsyncStatus>,_lambda_9a0aae7dbba35881869cec547d91271e_>(
           (__int64 *)va,
           &v14);
    v4 = *v9;
    *v9 = 0;
    if ( v17 )
    {
      v17 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICleanmgrAdminHelper>::Release();
    }
    *(_QWORD *)&v14 = v4;
    if ( v4 )
    {
      v10 = **a2;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
      v8 = v10(a2, &GUID_00000036_0000_0000_c000_000000000046, &v16);
      if ( v8 >= 0 )
      {
        v8 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*a2)[8])(a2, v4);
        if ( v8 >= 0 )
        {
          v11 = WaitForSingleObject(v6, 0xFFFFFFFF);
          if ( v11 == 258 )
          {
            v8 = -2147023436;
          }
          else if ( v11 )
          {
            LastError = GetLastError();
            v8 = LastError;
            if ( LastError > 0 )
              v8 = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v16 + 56LL))(v16, &v15);
            if ( v8 >= 0 )
            {
              if ( !v19
                || (v8 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a2)[10])(a2),
                    v8 >= 0) )
              {
                if ( v15 == 2 )
                {
                  v8 = -2147009288;
                }
                else if ( v15 == 3 )
                {
                  LODWORD(v17) = 0;
                  v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 64LL))(v16, (__int64 *)va);
                  if ( v8 >= 0 )
                    v8 = v17;
                }
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 80LL))(v16);
              }
            }
          }
        }
      }
    }
    else
    {
      v8 = -2147024882;
    }
    CloseHandle(v6);
  }
  else
  {
    v7 = GetLastError();
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140026d74  mov     [rsp-28h+arg_18], r9
0x140026d79  mov     [rsp-28h+arg_10], r8
0x140026d7e  mov     [rsp-28h+arg_0], ecx
0x140026d82  push    rbp
0x140026d83  push    rbx
0x140026d84  push    rsi
0x140026d85  push    rdi
0x140026d86  push    r14
0x140026d88  mov     rbp, rsp
0x140026d8b  sub     rsp, 30h
0x140026d8f  mov     rsi, rdx
0x140026d92  xor     ebx, ebx
0x140026d94  mov     [rbp+arg_10], rbx
0x140026d98  mov     [rbp+arg_0], ebx
0x140026d9b  mov     r9d, 1F0003h; dwDesiredAccess
0x140026da1  xor     r8d, r8d; dwFlags
0x140026da4  xor     edx, edx; lpName
0x140026da6  xor     ecx, ecx; lpEventAttributes
0x140026da8  call    cs:__imp_CreateEventExW
0x140026dae  mov     r14, rax
0x140026db1  test    rax, rax
0x140026db4  jnz     short loc_140026DD4
0x140026db6  call    cs:__imp_GetLastError
0x140026dbc  mov     edi, eax
0x140026dbe  test    eax, eax
0x140026dc0  jle     loc_140026F2F
0x140026dc6  movzx   edi, ax
0x140026dc9  or      edi, 80070000h
0x140026dcf  jmp     loc_140026F2F
0x140026dd4  mov     [rbp+var_10], r14
0x140026dd8  mov     [rbp+var_8], 0
0x140026de0  lea     rdx, [rbp+var_10]
0x140026de4  lea     rcx, [rbp+arg_18]
0x140026de8  call    ??$Make@U?$DelegateInvokeHelper@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@V_lambda_9a0aae7dbba35881869cec547d91271e_@@$0?0PEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@23@W4AsyncStatus@23ABI@@@?$DelegateArgTraits@P8?$IAsyncOperationWithProgressCompletedHandler_impl@U?$AggregateType@PEAVDeploymentResult@Deployment@Management@Windows@@PEAUIDeploymentResult@234@@Internal@Foundation@Windows@@UDeploymentProgress@Deployment@Management@4@@Foundation@Windows@@EAAJPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@23@W4AsyncStatus@23ABI@@@Z@Details@WRL@Microsoft@@V_lambda_9a0aae7dbba35881869cec547d91271e_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@U?$DelegateInvokeHelper@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@V_lambda_9a0aae7dbba35881869cec547d91271e_@@$0?0PEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@23@W4AsyncStatus@23ABI@@@?$DelegateArgTraits@P8?$IAsyncOperationWithProgressCompletedHandler_impl@U?$AggregateType@PEAVDeploymentResult@Deployment@Management@Windows@@PEAUIDeploymentResult@234@@Internal@Foundation@Windows@@UDeploymentProgress@Deployment@Management@4@@Foundation@Windows@@EAAJPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@23@W4AsyncStatus@23ABI@@@Z@Details@WRL@Microsoft@@@12@$$QEAV_lambda_9a0aae7dbba35881869cec547d91271e_@@@Z; Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IAsyncOperationWithProgressCompletedHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::IDeploymentResult *>,Windows::Management::Deployment::DeploymentProgress>::*)(Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,ABI::Windows::Foundation::AsyncStatus)>::DelegateInvokeHelper<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,_lambda_9a0aae7dbba35881869cec547d91271e_,-1,Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,ABI::Windows::Foundation::AsyncStatus>,_lambda_9a0aae7dbba35881869cec547d91271e_>(_lambda_9a0aae7dbba35881869cec547d91271e_ &&)
0x140026ded  mov     rbx, [rax]
0x140026df0  mov     qword ptr [rax], 0
0x140026df7  mov     rcx, [rbp+arg_18]
0x140026dfb  test    rcx, rcx
0x140026dfe  jz      short loc_140026E0D
0x140026e00  mov     [rbp+arg_18], 0
0x140026e08  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UICleanmgrAdminHelper@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICleanmgrAdminHelper>::Release(void)
0x140026e0d  mov     [rbp+var_10], rbx
0x140026e11  test    rbx, rbx
0x140026e14  jnz     short loc_140026E20
0x140026e16  mov     edi, 8007000Eh
0x140026e1b  jmp     loc_140026F25
0x140026e20  mov     rax, [rsi]
0x140026e23  mov     rdi, [rax]
0x140026e26  lea     rcx, [rbp+arg_10]
0x140026e2a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140026e2f  lea     r8, [rbp+arg_10]
0x140026e33  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x140026e3a  mov     rcx, rsi
0x140026e3d  mov     rax, rdi
0x140026e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026e45  mov     edi, eax
0x140026e47  test    eax, eax
0x140026e49  js      loc_140026F25
0x140026e4f  mov     rax, [rsi]
0x140026e52  mov     rdx, rbx
0x140026e55  mov     rcx, rsi
0x140026e58  mov     rax, [rax+40h]
0x140026e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026e61  mov     edi, eax
0x140026e63  test    eax, eax
0x140026e65  js      loc_140026F25
0x140026e6b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140026e6e  mov     rcx, r14; hHandle
0x140026e71  call    cs:__imp_WaitForSingleObject
0x140026e77  cmp     eax, 102h
0x140026e7c  jnz     short loc_140026E88
0x140026e7e  mov     edi, 800705B4h
0x140026e83  jmp     loc_140026F25
0x140026e88  test    eax, eax
0x140026e8a  jz      short loc_140026EA7
0x140026e8c  call    cs:__imp_GetLastError
0x140026e92  mov     edi, eax
0x140026e94  test    eax, eax
0x140026e96  jle     loc_140026F25
0x140026e9c  movzx   edi, ax
0x140026e9f  or      edi, 80070000h
0x140026ea5  jmp     short loc_140026F25
0x140026ea7  mov     rcx, [rbp+arg_10]
0x140026eab  mov     rax, [rcx]
0x140026eae  lea     rdx, [rbp+arg_0]
0x140026eb2  mov     rax, [rax+38h]
0x140026eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026ebb  mov     edi, eax
0x140026ebd  test    eax, eax
0x140026ebf  js      short loc_140026F25
0x140026ec1  mov     rdx, [rbp+arg_20]
0x140026ec5  test    rdx, rdx
0x140026ec8  jz      short loc_140026EDF
0x140026eca  mov     rax, [rsi]
0x140026ecd  mov     rcx, rsi
0x140026ed0  mov     rax, [rax+50h]
0x140026ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026ed9  mov     edi, eax
0x140026edb  test    eax, eax
0x140026edd  js      short loc_140026F25
0x140026edf  cmp     [rbp+arg_0], 2
0x140026ee3  jnz     short loc_140026EEC
0x140026ee5  mov     edi, 80073CF8h
0x140026eea  jmp     short loc_140026F15
0x140026eec  cmp     [rbp+arg_0], 3
0x140026ef0  jnz     short loc_140026F15
0x140026ef2  mov     dword ptr [rbp+arg_18], 0
0x140026ef9  mov     rcx, [rbp+arg_10]
0x140026efd  mov     rax, [rcx]
0x140026f00  lea     rdx, [rbp+arg_18]
0x140026f04  mov     rax, [rax+40h]
0x140026f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026f0d  mov     edi, eax
0x140026f0f  test    eax, eax
0x140026f11  cmovns  edi, dword ptr [rbp+arg_18]
0x140026f15  mov     rcx, [rbp+arg_10]
0x140026f19  mov     rax, [rcx]
0x140026f1c  mov     rax, [rax+50h]
0x140026f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026f25  mov     rcx, r14; hObject
0x140026f28  call    cs:__imp_CloseHandle
0x140026f2e  nop
0x140026f2f  lea     rcx, [rbp+arg_10]
0x140026f33  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140026f38  nop
0x140026f39  test    rbx, rbx
0x140026f3c  jz      short loc_140026F4E
0x140026f3e  mov     rax, [rbx]
0x140026f41  mov     rcx, rbx
0x140026f44  mov     rax, [rax+10h]
0x140026f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026f4d  nop
0x140026f4e  mov     eax, edi
0x140026f50  add     rsp, 30h
0x140026f54  pop     r14
0x140026f56  pop     rdi
0x140026f57  pop     rsi
0x140026f58  pop     rbx
0x140026f59  pop     rbp
0x140026f5a  retn
```
