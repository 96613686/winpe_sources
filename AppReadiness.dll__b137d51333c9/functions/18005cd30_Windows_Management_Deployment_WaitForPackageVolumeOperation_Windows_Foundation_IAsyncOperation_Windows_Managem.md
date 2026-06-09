# Windows::Management::Deployment::WaitForPackageVolumeOperation(Windows::Foundation::IAsyncOperation<Windows::Management::Deployment::PackageVolume *> *,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Management::Deployment::PackageVolume *> *,Windows::Management::Deployment::IPackageVolume * *)

- ea: `0x18005cd30`
- end: `0x18005cf0b`
- name: `?WaitForPackageVolumeOperation@Deployment@Management@Windows@@YAJPEAU?$IAsyncOperation@PEAVPackageVolume@Deployment@Management@Windows@@@Foundation@3@PEAU?$IAsyncOperationCompletedHandler@PEAVPackageVolume@Deployment@Management@Windows@@@53@PEAPEAUIPackageVolume@123@@Z`
- size: `475`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010afc`

## callees

- `0x180002958`
- `0x180016d80`
- `0x180049a54`
- `0x18005cd30`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005ce2d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005ce2d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18005cd64`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18005cd64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cd72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ce37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cd72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ce37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ced2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ced2`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Management::Deployment::WaitForPackageVolumeOperation(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        __int64 a2,
        __int64 a3)
{
  __int64 v5; // rbx
  HANDLE Event; // rax
  void *v7; // r14
  signed int v8; // eax
  signed int v9; // edi
  __int64 *v10; // rax
  __int64 (__fastcall *v11)(_QWORD, GUID *, __int64 *); // rdi
  signed int LastError; // eax
  __int64 v14; // [rsp+20h] [rbp-20h] BYREF
  __int128 v15; // [rsp+28h] [rbp-18h] BYREF
  int v16; // [rsp+78h] [rbp+38h] BYREF
  int v17; // [rsp+7Ch] [rbp+3Ch]
  __int64 v18; // [rsp+88h] [rbp+48h] BYREF

  v17 = HIDWORD(a2);
  v5 = 0;
  v14 = 0;
  v16 = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  v7 = Event;
  if ( Event )
  {
    v15 = (unsigned __int64)Event;
    v10 = Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IAsyncOperationCompletedHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::Management::Deployment::PackageVolume *,Windows::Management::Deployment::IPackageVolume *>>::*)(Windows::Foundation::IAsyncOperation<Windows::Management::Deployment::PackageVolume *> *,enum ABI::Windows::Foundation::AsyncStatus)>::DelegateInvokeHelper<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Management::Deployment::PackageVolume *>,_lambda_c45c6a1ebc6e1958651ded08aead5a1e_,-1,Windows::Foundation::IAsyncOperation<Windows::Management::Deployment::PackageVolume *> *,enum ABI::Windows::Foundation::AsyncStatus>,_lambda_c45c6a1ebc6e1958651ded08aead5a1e_>(
            &v18,
            &v15);
    v5 = *v10;
    *v10 = 0;
    if ( v18 )
    {
      v18 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Management::Deployment::PackageVolume *>>::Release();
    }
    *(_QWORD *)&v15 = v5;
    if ( v5 )
    {
      v11 = **a1;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
      v9 = v11(a1, &GUID_00000036_0000_0000_c000_000000000046, &v14);
      if ( v9 >= 0 )
      {
        v9 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*a1)[6])(a1, v5);
        if ( v9 >= 0 )
        {
          if ( WaitForSingleObject(v7, 0xFFFFFFFF) )
          {
            LastError = GetLastError();
            v9 = LastError;
            if ( LastError > 0 )
              v9 = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v14 + 56LL))(v14, &v16);
            if ( v9 >= 0 )
            {
              if ( !a3
                || (v9 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*a1)[8])(
                           a1,
                           a3),
                    v9 >= 0) )
              {
                if ( v16 == 2 )
                {
                  v9 = -2147009288;
                }
                else if ( v16 == 3 )
                {
                  LODWORD(v18) = 0;
                  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v14 + 64LL))(v14, &v18);
                  if ( v9 >= 0 )
                    v9 = v18;
                }
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 80LL))(v14);
              }
            }
          }
        }
      }
    }
    else
    {
      v9 = -2147024882;
    }
    CloseHandle(v7);
  }
  else
  {
    v8 = GetLastError();
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18005cd30  mov     [rsp-28h+arg_0], rbx
0x18005cd35  mov     [rsp-28h+arg_8], rdx
0x18005cd3a  push    rbp
0x18005cd3b  push    rsi
0x18005cd3c  push    rdi
0x18005cd3d  push    r14
0x18005cd3f  push    r15
0x18005cd41  mov     rbp, rsp
0x18005cd44  sub     rsp, 40h
0x18005cd48  mov     r15, r8
0x18005cd4b  mov     rsi, rcx
0x18005cd4e  xor     ebx, ebx
0x18005cd50  mov     [rbp+var_20], rbx
0x18005cd54  mov     dword ptr [rbp+arg_8], ebx
0x18005cd57  mov     r9d, 1F0003h; dwDesiredAccess
0x18005cd5d  xor     r8d, r8d; dwFlags
0x18005cd60  xor     edx, edx; lpName
0x18005cd62  xor     ecx, ecx; lpEventAttributes
0x18005cd64  call    cs:__imp_CreateEventExW
0x18005cd6a  mov     r14, rax
0x18005cd6d  test    rax, rax
0x18005cd70  jnz     short loc_18005CD90
0x18005cd72  call    cs:__imp_GetLastError
0x18005cd78  mov     edi, eax
0x18005cd7a  test    eax, eax
0x18005cd7c  jle     loc_18005CED9
0x18005cd82  movzx   edi, ax
0x18005cd85  or      edi, 80070000h
0x18005cd8b  jmp     loc_18005CED9
0x18005cd90  mov     [rbp+var_18], r14
0x18005cd94  mov     [rbp+var_10], 0
0x18005cd9c  lea     rdx, [rbp+var_18]
0x18005cda0  lea     rcx, [rbp+arg_18]
0x18005cda4  call    ??$Make@U?$DelegateInvokeHelper@U?$IAsyncOperationCompletedHandler@PEAVPackageVolume@Deployment@Management@Windows@@@Foundation@Windows@@V_lambda_c45c6a1ebc6e1958651ded08aead5a1e_@@$0?0PEAU?$IAsyncOperation@PEAVPackageVolume@Deployment@Management@Windows@@@23@W4AsyncStatus@23ABI@@@?$DelegateArgTraits@P8?$IAsyncOperationCompletedHandler_impl@U?$AggregateType@PEAVPackageVolume@Deployment@Management@Windows@@PEAUIPackageVolume@234@@Internal@Foundation@Windows@@@Foundation@Windows@@EAAJPEAU?$IAsyncOperation@PEAVPackageVolume@Deployment@Management@Windows@@@23@W4AsyncStatus@23ABI@@@Z@Details@WRL@Microsoft@@V_lambda_c45c6a1ebc6e1958651ded08aead5a1e_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@U?$DelegateInvokeHelper@U?$IAsyncOperationCompletedHandler@PEAVPackageVolume@Deployment@Management@Windows@@@Foundation@Windows@@V_lambda_c45c6a1ebc6e1958651ded08aead5a1e_@@$0?0PEAU?$IAsyncOperation@PEAVPackageVolume@Deployment@Management@Windows@@@23@W4AsyncStatus@23ABI@@@?$DelegateArgTraits@P8?$IAsyncOperationCompletedHandler_impl@U?$AggregateType@PEAVPackageVolume@Deployment@Management@Windows@@PEAUIPackageVolume@234@@Internal@Foundation@Windows@@@Foundation@Windows@@EAAJPEAU?$IAsyncOperation@PEAVPackageVolume@Deployment@Management@Windows@@@23@W4AsyncStatus@23ABI@@@Z@Details@WRL@Microsoft@@@12@$$QEAV_lambda_c45c6a1ebc6e1958651ded08aead5a1e_@@@Z; Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IAsyncOperationCompletedHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::Management::Deployment::PackageVolume *,Windows::Management::Deployment::IPackageVolume *>>::*)(Windows::Foundation::IAsyncOperation<Windows::Management::Deployment::PackageVolume *> *,ABI::Windows::Foundation::AsyncStatus)>::DelegateInvokeHelper<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Management::Deployment::PackageVolume *>,_lambda_c45c6a1ebc6e1958651ded08aead5a1e_,-1,Windows::Foundation::IAsyncOperation<Windows::Management::Deployment::PackageVolume *> *,ABI::Windows::Foundation::AsyncStatus>,_lambda_c45c6a1ebc6e1958651ded08aead5a1e_>(_lambda_c45c6a1ebc6e1958651ded08aead5a1e_ &&)
0x18005cda9  mov     rbx, [rax]
0x18005cdac  mov     qword ptr [rax], 0
0x18005cdb3  mov     rcx, [rbp+arg_18]
0x18005cdb7  test    rcx, rcx
0x18005cdba  jz      short loc_18005CDC9
0x18005cdbc  mov     [rbp+arg_18], 0
0x18005cdc4  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVPackageVolume@Deployment@Management@Windows@@@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Management::Deployment::PackageVolume *>>::Release(void)
0x18005cdc9  mov     [rbp+var_18], rbx
0x18005cdcd  test    rbx, rbx
0x18005cdd0  jnz     short loc_18005CDDC
0x18005cdd2  mov     edi, 8007000Eh
0x18005cdd7  jmp     loc_18005CECF
0x18005cddc  mov     rax, [rsi]
0x18005cddf  mov     rdi, [rax]
0x18005cde2  lea     rcx, [rbp+var_20]
0x18005cde6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005cdeb  lea     r8, [rbp+var_20]
0x18005cdef  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18005cdf6  mov     rcx, rsi
0x18005cdf9  mov     rax, rdi
0x18005cdfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ce01  mov     edi, eax
0x18005ce03  test    eax, eax
0x18005ce05  js      loc_18005CECF
0x18005ce0b  mov     rax, [rsi]
0x18005ce0e  mov     rdx, rbx
0x18005ce11  mov     rcx, rsi
0x18005ce14  mov     rax, [rax+30h]
0x18005ce18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ce1d  mov     edi, eax
0x18005ce1f  test    eax, eax
0x18005ce21  js      loc_18005CECF
0x18005ce27  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18005ce2a  mov     rcx, r14; hHandle
0x18005ce2d  call    cs:__imp_WaitForSingleObject
0x18005ce33  test    eax, eax
0x18005ce35  jz      short loc_18005CE52
0x18005ce37  call    cs:__imp_GetLastError
0x18005ce3d  mov     edi, eax
0x18005ce3f  test    eax, eax
0x18005ce41  jle     loc_18005CECF
0x18005ce47  movzx   edi, ax
0x18005ce4a  or      edi, 80070000h
0x18005ce50  jmp     short loc_18005CECF
0x18005ce52  mov     rcx, [rbp+var_20]
0x18005ce56  mov     rax, [rcx]
0x18005ce59  lea     rdx, [rbp+arg_8]
0x18005ce5d  mov     rax, [rax+38h]
0x18005ce61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ce66  mov     edi, eax
0x18005ce68  test    eax, eax
0x18005ce6a  js      short loc_18005CECF
0x18005ce6c  test    r15, r15
0x18005ce6f  jz      short loc_18005CE89
0x18005ce71  mov     rax, [rsi]
0x18005ce74  mov     rdx, r15
0x18005ce77  mov     rcx, rsi
0x18005ce7a  mov     rax, [rax+40h]
0x18005ce7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ce83  mov     edi, eax
0x18005ce85  test    eax, eax
0x18005ce87  js      short loc_18005CECF
0x18005ce89  cmp     dword ptr [rbp+arg_8], 2
0x18005ce8d  jnz     short loc_18005CE96
0x18005ce8f  mov     edi, 80073CF8h
0x18005ce94  jmp     short loc_18005CEBF
0x18005ce96  cmp     dword ptr [rbp+arg_8], 3
0x18005ce9a  jnz     short loc_18005CEBF
0x18005ce9c  mov     dword ptr [rbp+arg_18], 0
0x18005cea3  mov     rcx, [rbp+var_20]
0x18005cea7  mov     rax, [rcx]
0x18005ceaa  lea     rdx, [rbp+arg_18]
0x18005ceae  mov     rax, [rax+40h]
0x18005ceb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ceb7  mov     edi, eax
0x18005ceb9  test    eax, eax
0x18005cebb  cmovns  edi, dword ptr [rbp+arg_18]
0x18005cebf  mov     rcx, [rbp+var_20]
0x18005cec3  mov     rax, [rcx]
0x18005cec6  mov     rax, [rax+50h]
0x18005ceca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cecf  mov     rcx, r14; hObject
0x18005ced2  call    cs:__imp_CloseHandle
0x18005ced8  nop
0x18005ced9  lea     rcx, [rbp+var_20]
0x18005cedd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005cee2  nop
0x18005cee3  test    rbx, rbx
0x18005cee6  jz      short loc_18005CEF8
0x18005cee8  mov     rax, [rbx]
0x18005ceeb  mov     rcx, rbx
0x18005ceee  mov     rax, [rax+10h]
0x18005cef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cef7  nop
0x18005cef8  mov     eax, edi
0x18005cefa  mov     rbx, [rsp+40h+arg_0]
0x18005ceff  add     rsp, 40h
0x18005cf03  pop     r15
0x18005cf05  pop     r14
0x18005cf07  pop     rdi
0x18005cf08  pop     rsi
0x18005cf09  pop     rbp
0x18005cf0a  retn
```
