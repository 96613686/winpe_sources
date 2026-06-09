# Windows::Management::Deployment::WaitForDeploymentOperation(ulong,Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Management::Deployment::IDeploymentResult * *)

- ea: `0x180002b0c`
- end: `0x180002ce2`
- name: `?WaitForDeploymentOperation@Deployment@Management@Windows@@YAJKPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@3@PEAU?$IAsyncOperationProgressHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@53@PEAU?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@53@PEAPEAUIDeploymentResult@123@@Z`
- size: `470`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800286e4`
- `0x18004c9f4`
- `0x18006351c`
- `0x1800635c4`
- `0x180063710`
- `0x1800637a8`
- `0x180066670`

## callees

- `0x180002958`
- `0x180002b0c`
- `0x18002467c`
- `0x180040338`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002c09`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002c09`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180002b44`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180002b44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002c9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002c9b`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 Windows::Management::Deployment::WaitForDeploymentOperation(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        __int64 a3,
        ...)
{
  __int64 v4; // rbx
  HANDLE Event; // rax
  void *v6; // rsi
  signed int v7; // eax
  signed int v8; // edi
  void *v9; // rax
  __int64 (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rdi
  DWORD v11; // eax
  signed int LastError; // eax
  __int64 v13; // rcx
  __int128 v15; // [rsp+20h] [rbp-10h] BYREF
  int v16; // [rsp+60h] [rbp+30h] BYREF
  __int64 v17; // [rsp+70h] [rbp+40h] BYREF
  __int64 v18; // [rsp+78h] [rbp+48h] BYREF
  va_list va; // [rsp+78h] [rbp+48h]
  __int64 v20; // [rsp+80h] [rbp+50h]
  va_list va1; // [rsp+88h] [rbp+58h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v18 = va_arg(va1, _QWORD);
  va_arg(va1, _QWORD);
  v4 = 0;
  v20 = 0;
  v17 = 0;
  v16 = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  v6 = Event;
  if ( Event )
  {
    v15 = (unsigned __int64)Event;
    v9 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v9 )
      v4 = Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IAsyncOperationWithProgressCompletedHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::IDeploymentResult *>,Windows::Management::Deployment::DeploymentProgress>::*)(Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,enum ABI::Windows::Foundation::AsyncStatus)>::DelegateInvokeHelper<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,_lambda_9a0aae7dbba35881869cec547d91271e_,-1,Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,enum ABI::Windows::Foundation::AsyncStatus>::DelegateInvokeHelper<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,_lambda_9a0aae7dbba35881869cec547d91271e_,-1,Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,enum ABI::Windows::Foundation::AsyncStatus>(
             (__int64)v9,
             &v15);
    else
      v4 = 0;
    v20 = v4;
    if ( v4 )
    {
      v10 = **a2;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
      v8 = v10(a2, &GUID_00000036_0000_0000_c000_000000000046, &v17);
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
            v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v17 + 56LL))(v17, &v16);
            if ( v8 >= 0 )
            {
              if ( v16 == 2 )
              {
                v8 = -2147009288;
              }
              else if ( v16 == 3 )
              {
                LODWORD(v18) = 0;
                v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 64LL))(v17, (__int64 *)va);
                if ( v8 >= 0 )
                  v8 = v18;
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 80LL))(v17);
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
  v13 = v17;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180002b0c  mov     [rsp-28h+arg_18], r9
0x180002b11  mov     [rsp-28h+arg_10], r8
0x180002b16  mov     [rsp-28h+arg_0], ecx
0x180002b1a  push    rbp
0x180002b1b  push    rbx
0x180002b1c  push    rsi
0x180002b1d  push    rdi
0x180002b1e  push    r14
0x180002b20  mov     rbp, rsp
0x180002b23  sub     rsp, 30h
0x180002b27  mov     r14, rdx
0x180002b2a  xor     ebx, ebx
0x180002b2c  mov     [rbp+arg_20], rbx
0x180002b30  mov     [rbp+arg_10], rbx
0x180002b34  mov     [rbp+arg_0], ebx
0x180002b37  mov     r9d, 1F0003h; dwDesiredAccess
0x180002b3d  xor     r8d, r8d; dwFlags
0x180002b40  xor     edx, edx; lpName
0x180002b42  xor     ecx, ecx; lpEventAttributes
0x180002b44  call    cs:__imp_CreateEventExW
0x180002b4a  mov     rsi, rax
0x180002b4d  test    rax, rax
0x180002b50  jnz     short loc_180002B70
0x180002b52  call    cs:__imp_GetLastError
0x180002b58  mov     edi, eax
0x180002b5a  test    eax, eax
0x180002b5c  jle     loc_180002CA2
0x180002b62  movzx   edi, ax
0x180002b65  or      edi, 80070000h
0x180002b6b  jmp     loc_180002CA2
0x180002b70  mov     [rbp+var_10], rsi
0x180002b74  mov     [rbp+var_8], 0
0x180002b7c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002b83  mov     ecx, 20h ; ' '; unsigned __int64
0x180002b88  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002b8d  test    rax, rax
0x180002b90  jz      short loc_180002BA3
0x180002b92  lea     rdx, [rbp+var_10]
0x180002b96  mov     rcx, rax
0x180002b99  call    ??0?$DelegateInvokeHelper@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@V_lambda_9a0aae7dbba35881869cec547d91271e_@@$0?0PEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@23@W4AsyncStatus@23ABI@@@?$DelegateArgTraits@P8?$IAsyncOperationWithProgressCompletedHandler_impl@U?$AggregateType@PEAVDeploymentResult@Deployment@Management@Windows@@PEAUIDeploymentResult@234@@Internal@Foundation@Windows@@UDeploymentProgress@Deployment@Management@4@@Foundation@Windows@@EAAJPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@23@W4AsyncStatus@23ABI@@@Z@Details@WRL@Microsoft@@QEAA@$$QEAV_lambda_9a0aae7dbba35881869cec547d91271e_@@@Z; Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IAsyncOperationWithProgressCompletedHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::IDeploymentResult *>,Windows::Management::Deployment::DeploymentProgress>::*)(Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,ABI::Windows::Foundation::AsyncStatus)>::DelegateInvokeHelper<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,_lambda_9a0aae7dbba35881869cec547d91271e_,-1,Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,ABI::Windows::Foundation::AsyncStatus>::DelegateInvokeHelper<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,_lambda_9a0aae7dbba35881869cec547d91271e_,-1,Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,ABI::Windows::Foundation::AsyncStatus>(_lambda_9a0aae7dbba35881869cec547d91271e_ &&)
0x180002b9e  mov     rbx, rax
0x180002ba1  jmp     short loc_180002BA5
0x180002ba3  xor     ebx, ebx
0x180002ba5  mov     [rbp+arg_20], rbx
0x180002ba9  test    rbx, rbx
0x180002bac  jnz     short loc_180002BB8
0x180002bae  mov     edi, 8007000Eh
0x180002bb3  jmp     loc_180002C98
0x180002bb8  mov     rax, [r14]
0x180002bbb  mov     rdi, [rax]
0x180002bbe  lea     rcx, [rbp+arg_10]
0x180002bc2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180002bc7  lea     r8, [rbp+arg_10]
0x180002bcb  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180002bd2  mov     rcx, r14
0x180002bd5  mov     rax, rdi
0x180002bd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bdd  mov     edi, eax
0x180002bdf  test    eax, eax
0x180002be1  js      loc_180002C98
0x180002be7  mov     rax, [r14]
0x180002bea  mov     rdx, rbx
0x180002bed  mov     rcx, r14
0x180002bf0  mov     rax, [rax+40h]
0x180002bf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bf9  mov     edi, eax
0x180002bfb  test    eax, eax
0x180002bfd  js      loc_180002C98
0x180002c03  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180002c06  mov     rcx, rsi; hHandle
0x180002c09  call    cs:__imp_WaitForSingleObject
0x180002c0f  cmp     eax, 102h
0x180002c14  jnz     short loc_180002C1D
0x180002c16  mov     edi, 800705B4h
0x180002c1b  jmp     short loc_180002C98
0x180002c1d  test    eax, eax
0x180002c1f  jz      short loc_180002C38
0x180002c21  call    cs:__imp_GetLastError
0x180002c27  mov     edi, eax
0x180002c29  test    eax, eax
0x180002c2b  jle     short loc_180002C98
0x180002c2d  movzx   edi, ax
0x180002c30  or      edi, 80070000h
0x180002c36  jmp     short loc_180002C98
0x180002c38  mov     rcx, [rbp+arg_10]
0x180002c3c  mov     rax, [rcx]
0x180002c3f  lea     rdx, [rbp+arg_0]
0x180002c43  mov     rax, [rax+38h]
0x180002c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c4c  mov     edi, eax
0x180002c4e  test    eax, eax
0x180002c50  js      short loc_180002C98
0x180002c52  cmp     [rbp+arg_0], 2
0x180002c56  jnz     short loc_180002C5F
0x180002c58  mov     edi, 80073CF8h
0x180002c5d  jmp     short loc_180002C88
0x180002c5f  cmp     [rbp+arg_0], 3
0x180002c63  jnz     short loc_180002C88
0x180002c65  mov     dword ptr [rbp+arg_18], 0
0x180002c6c  mov     rcx, [rbp+arg_10]
0x180002c70  mov     rax, [rcx]
0x180002c73  lea     rdx, [rbp+arg_18]
0x180002c77  mov     rax, [rax+40h]
0x180002c7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c80  mov     edi, eax
0x180002c82  test    eax, eax
0x180002c84  cmovns  edi, dword ptr [rbp+arg_18]
0x180002c88  mov     rcx, [rbp+arg_10]
0x180002c8c  mov     rax, [rcx]
0x180002c8f  mov     rax, [rax+50h]
0x180002c93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c98  mov     rcx, rsi; hObject
0x180002c9b  call    cs:__imp_CloseHandle
0x180002ca1  nop
0x180002ca2  mov     rcx, [rbp+arg_10]
0x180002ca6  test    rcx, rcx
0x180002ca9  jz      short loc_180002CC0
0x180002cab  mov     [rbp+arg_10], 0
0x180002cb3  mov     rax, [rcx]
0x180002cb6  mov     rax, [rax+10h]
0x180002cba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cbf  nop
0x180002cc0  test    rbx, rbx
0x180002cc3  jz      short loc_180002CD5
0x180002cc5  mov     rax, [rbx]
0x180002cc8  mov     rcx, rbx
0x180002ccb  mov     rax, [rax+10h]
0x180002ccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cd4  nop
0x180002cd5  mov     eax, edi
0x180002cd7  add     rsp, 30h
0x180002cdb  pop     r14
0x180002cdd  pop     rdi
0x180002cde  pop     rsi
0x180002cdf  pop     rbx
0x180002ce0  pop     rbp
0x180002ce1  retn
```
