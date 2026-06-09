# SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetValue(IInspectable *)

- ea: `0x180017ab8`
- end: `0x180017c50`
- name: `?_SetValue@?$CDataSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@AEAAJPEAUIInspectable@@@Z`
- size: `408`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180011ba0`
- `0x180017300`

## callees

- `0x1800076ac`
- `0x18000f854`
- `0x180010304`
- `0x180017ab8`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017b93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017bdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017b93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017bdc`

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
0x180017ab8  push    rbx
0x180017aba  push    rsi
0x180017abb  push    rdi
0x180017abc  sub     rsp, 20h
0x180017ac0  mov     rdi, rdx
0x180017ac3  mov     rsi, rcx
0x180017ac6  mov     edx, [rcx+0B8h]
0x180017acc  lea     rcx, [rsp+38h+arg_18]
0x180017ad1  call    ??0CAutoWinRtInit@DataModel@SystemSettings@@QEAA@W4AsynchronousType@12@@Z; SystemSettings::DataModel::CAutoWinRtInit::CAutoWinRtInit(SystemSettings::DataModel::AsynchronousType)
0x180017ad6  nop
0x180017ad7  mov     [rsp+38h+arg_10], 0
0x180017ae0  mov     rax, [rdi]
0x180017ae3  mov     rbx, [rax]
0x180017ae6  lea     rcx, [rsp+38h+arg_10]
0x180017aeb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017af0  lea     r8, [rsp+38h+arg_10]
0x180017af5  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x180017afc  mov     rcx, rdi
0x180017aff  mov     rax, rbx
0x180017b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b07  mov     ebx, eax
0x180017b09  test    eax, eax
0x180017b0b  js      loc_180017C2A
0x180017b11  mov     rax, [rsi]
0x180017b14  mov     rdx, [rsp+38h+arg_10]
0x180017b19  mov     rcx, rsi
0x180017b1c  mov     rax, [rax+0E8h]
0x180017b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b28  mov     ebx, eax
0x180017b2a  cmp     eax, 80004001h
0x180017b2f  jnz     loc_180017C2A
0x180017b35  mov     [rsp+38h+arg_8], 0
0x180017b3d  mov     rcx, [rsp+38h+arg_10]
0x180017b42  mov     rax, [rcx]
0x180017b45  lea     rdx, [rsp+38h+arg_8]
0x180017b4a  mov     rax, [rax+30h]
0x180017b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b53  mov     ebx, eax
0x180017b55  test    eax, eax
0x180017b57  js      loc_180017C2A
0x180017b5d  mov     ecx, [rsp+38h+arg_8]
0x180017b61  sub     ecx, 0Bh
0x180017b64  jz      loc_180017BEA
0x180017b6a  cmp     ecx, 1
0x180017b6d  jz      short loc_180017B79
0x180017b6f  mov     ebx, 80070057h
0x180017b74  jmp     loc_180017C2A
0x180017b79  mov     [rsp+38h+string], 0
0x180017b82  mov     rdi, [rsp+38h+arg_10]
0x180017b87  mov     rax, [rdi]
0x180017b8a  mov     rbx, [rax+98h]
0x180017b91  xor     ecx, ecx; string
0x180017b93  call    cs:__imp_WindowsDeleteString
0x180017b9a  nop     dword ptr [rax+rax+00h]
0x180017b9f  mov     [rsp+38h+string], 0
0x180017ba8  lea     rdx, [rsp+38h+string]
0x180017bad  mov     rcx, rdi
0x180017bb0  mov     rax, rbx
0x180017bb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bb8  mov     ebx, eax
0x180017bba  test    eax, eax
0x180017bbc  js      short loc_180017BD7
0x180017bbe  mov     rax, [rsi]
0x180017bc1  mov     rdx, [rsp+38h+string]
0x180017bc6  mov     rcx, rsi
0x180017bc9  mov     rax, [rax+0E0h]
0x180017bd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bd5  mov     ebx, eax
0x180017bd7  mov     rcx, [rsp+38h+string]; string
0x180017bdc  call    cs:__imp_WindowsDeleteString
0x180017be3  nop     dword ptr [rax+rax+00h]
0x180017be8  jmp     short loc_180017C2A
0x180017bea  mov     byte ptr [rsp+38h+string], 0
0x180017bef  mov     rcx, [rsp+38h+arg_10]
0x180017bf4  mov     rax, [rcx]
0x180017bf7  lea     rdx, [rsp+38h+string]
0x180017bfc  mov     rax, [rax+90h]
0x180017c03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c08  mov     ebx, eax
0x180017c0a  test    eax, eax
0x180017c0c  js      short loc_180017C2A
0x180017c0e  mov     rax, [rsi]
0x180017c11  cmp     byte ptr [rsp+38h+string], 0
0x180017c16  setnz   dl
0x180017c19  mov     rcx, rsi
0x180017c1c  mov     rax, [rax+0D8h]
0x180017c23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c28  mov     ebx, eax
0x180017c2a  lea     rcx, [rsp+38h+arg_10]
0x180017c2f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017c34  nop
0x180017c35  lea     rcx, [rsp+38h+arg_18]; this
0x180017c3a  call    ??1CAutoWinRtInit@DataModel@SystemSettings@@QEAA@XZ; SystemSettings::DataModel::CAutoWinRtInit::~CAutoWinRtInit(void)
0x180017c3f  mov     eax, ebx
0x180017c41  jmp     short loc_180017C47
0x180017c43  mov     eax, dword ptr [rsp+38h+string]
0x180017c47  add     rsp, 20h
0x180017c4b  pop     rdi
0x180017c4c  pop     rsi
0x180017c4d  pop     rbx
0x180017c4e  retn
```
