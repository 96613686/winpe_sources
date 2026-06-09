# SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetValue(IInspectable *)

- ea: `0x18003ec54`
- end: `0x18003eddc`
- name: `?_SetValue@?$CDataSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@AEAAJPEAUIInspectable@@@Z`
- size: `392`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003bf60`
- `0x18003e0e0`

## callees

- `0x18000760c`
- `0x18003b478`
- `0x18003b8fc`
- `0x18003ec54`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ed2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ed6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ed2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ed6e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetValue(
        unsigned int *a1,
        __int64 (***a2)(void))
{
  __int64 (*v4)(void); // rbx
  int v5; // ebx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, HSTRING *); // rbx
  __int64 v8; // rdx
  const char *v9; // r9
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HSTRING string; // [rsp+40h] [rbp+8h] BYREF
  int v13; // [rsp+48h] [rbp+10h] BYREF
  __int64 v14; // [rsp+50h] [rbp+18h] BYREF
  char v15; // [rsp+58h] [rbp+20h] BYREF

  SystemSettings::DataModel::CAutoWinRtInit::CAutoWinRtInit(&v15, a1[46]);
  v14 = 0;
  v4 = **a2;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  try
  {
    v5 = v4();
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(unsigned int *, __int64))(*(_QWORD *)a1 + 232LL))(a1, v14);
      if ( v5 == -2147467263 )
      {
        v13 = 0;
        v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v14 + 48LL))(v14, &v13);
        if ( v5 >= 0 )
        {
          if ( v13 == 11 )
          {
            LOBYTE(string) = 0;
            v5 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v14 + 144LL))(v14, &string);
            if ( v5 >= 0 )
            {
              LOBYTE(v8) = (_BYTE)string != 0;
              v5 = (*(__int64 (__fastcall **)(unsigned int *, __int64))(*(_QWORD *)a1 + 216LL))(a1, v8);
            }
          }
          else if ( v13 == 12 )
          {
            string = 0;
            v6 = v14;
            v7 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v14 + 152LL);
            WindowsDeleteString(0);
            string = 0;
            v5 = v7(v6, &string);
            if ( v5 >= 0 )
              v5 = (*(__int64 (__fastcall **)(unsigned int *, HSTRING))(*(_QWORD *)a1 + 224LL))(a1, string);
            WindowsDeleteString(string);
          }
          else
          {
            v5 = -2147024809;
          }
        }
      }
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
    SystemSettings::DataModel::CAutoWinRtInit::~CAutoWinRtInit((SystemSettings::DataModel::CAutoWinRtInit *)&v15);
    result = (unsigned int)v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x973,
                           (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x18003ec54  push    rbx
0x18003ec56  push    rsi
0x18003ec57  push    rdi
0x18003ec58  sub     rsp, 20h
0x18003ec5c  mov     rdi, rdx
0x18003ec5f  mov     rsi, rcx
0x18003ec62  mov     edx, [rcx+0B8h]
0x18003ec68  lea     rcx, [rsp+38h+arg_18]
0x18003ec6d  call    ??0CAutoWinRtInit@DataModel@SystemSettings@@QEAA@W4AsynchronousType@12@@Z; SystemSettings::DataModel::CAutoWinRtInit::CAutoWinRtInit(SystemSettings::DataModel::AsynchronousType)
0x18003ec72  nop
0x18003ec73  mov     [rsp+38h+arg_10], 0
0x18003ec7c  mov     rax, [rdi]
0x18003ec7f  mov     rbx, [rax]
0x18003ec82  lea     rcx, [rsp+38h+arg_10]
0x18003ec87  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ec8c  lea     r8, [rsp+38h+arg_10]
0x18003ec91  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x18003ec98  mov     rcx, rdi
0x18003ec9b  mov     rax, rbx
0x18003ec9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eca3  mov     ebx, eax
0x18003eca5  test    eax, eax
0x18003eca7  js      loc_18003EDB6
0x18003ecad  mov     rax, [rsi]
0x18003ecb0  mov     rdx, [rsp+38h+arg_10]
0x18003ecb5  mov     rcx, rsi
0x18003ecb8  mov     rax, [rax+0E8h]
0x18003ecbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ecc4  mov     ebx, eax
0x18003ecc6  cmp     eax, 80004001h
0x18003eccb  jnz     loc_18003EDB6
0x18003ecd1  mov     [rsp+38h+arg_8], 0
0x18003ecd9  mov     rcx, [rsp+38h+arg_10]
0x18003ecde  mov     rax, [rcx]
0x18003ece1  lea     rdx, [rsp+38h+arg_8]
0x18003ece6  mov     rax, [rax+30h]
0x18003ecea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ecef  mov     ebx, eax
0x18003ecf1  test    eax, eax
0x18003ecf3  js      loc_18003EDB6
0x18003ecf9  mov     ecx, [rsp+38h+arg_8]
0x18003ecfd  sub     ecx, 0Bh
0x18003ed00  jz      short loc_18003ED76
0x18003ed02  cmp     ecx, 1
0x18003ed05  jz      short loc_18003ED11
0x18003ed07  mov     ebx, 80070057h
0x18003ed0c  jmp     loc_18003EDB6
0x18003ed11  mov     [rsp+38h+string], 0
0x18003ed1a  mov     rdi, [rsp+38h+arg_10]
0x18003ed1f  mov     rax, [rdi]
0x18003ed22  mov     rbx, [rax+98h]
0x18003ed29  xor     ecx, ecx; string
0x18003ed2b  call    cs:__imp_WindowsDeleteString
0x18003ed31  mov     [rsp+38h+string], 0
0x18003ed3a  lea     rdx, [rsp+38h+string]
0x18003ed3f  mov     rcx, rdi
0x18003ed42  mov     rax, rbx
0x18003ed45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ed4a  mov     ebx, eax
0x18003ed4c  test    eax, eax
0x18003ed4e  js      short loc_18003ED69
0x18003ed50  mov     rax, [rsi]
0x18003ed53  mov     rdx, [rsp+38h+string]
0x18003ed58  mov     rcx, rsi
0x18003ed5b  mov     rax, [rax+0E0h]
0x18003ed62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ed67  mov     ebx, eax
0x18003ed69  mov     rcx, [rsp+38h+string]; string
0x18003ed6e  call    cs:__imp_WindowsDeleteString
0x18003ed74  jmp     short loc_18003EDB6
0x18003ed76  mov     byte ptr [rsp+38h+string], 0
0x18003ed7b  mov     rcx, [rsp+38h+arg_10]
0x18003ed80  mov     rax, [rcx]
0x18003ed83  lea     rdx, [rsp+38h+string]
0x18003ed88  mov     rax, [rax+90h]
0x18003ed8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ed94  mov     ebx, eax
0x18003ed96  test    eax, eax
0x18003ed98  js      short loc_18003EDB6
0x18003ed9a  mov     rax, [rsi]
0x18003ed9d  cmp     byte ptr [rsp+38h+string], 0
0x18003eda2  setnz   dl
0x18003eda5  mov     rcx, rsi
0x18003eda8  mov     rax, [rax+0D8h]
0x18003edaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003edb4  mov     ebx, eax
0x18003edb6  lea     rcx, [rsp+38h+arg_10]
0x18003edbb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003edc0  nop
0x18003edc1  lea     rcx, [rsp+38h+arg_18]; this
0x18003edc6  call    ??1CAutoWinRtInit@DataModel@SystemSettings@@QEAA@XZ; SystemSettings::DataModel::CAutoWinRtInit::~CAutoWinRtInit(void)
0x18003edcb  mov     eax, ebx
0x18003edcd  jmp     short loc_18003EDD3
0x18003edcf  mov     eax, dword ptr [rsp+38h+string]
0x18003edd3  add     rsp, 20h
0x18003edd7  pop     rdi
0x18003edd8  pop     rsi
0x18003edd9  pop     rbx
0x18003edda  retn
```
