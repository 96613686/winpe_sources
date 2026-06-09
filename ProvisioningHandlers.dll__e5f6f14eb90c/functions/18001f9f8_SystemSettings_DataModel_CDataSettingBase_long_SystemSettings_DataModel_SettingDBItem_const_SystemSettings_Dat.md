# SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetValue(IInspectable *)

- ea: `0x18001f9f8`
- end: `0x18001fb90`
- name: `?_SetValue@?$CDataSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@AEAAJPEAUIInspectable@@@Z`
- size: `408`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180013ab0`
- `0x18001d350`

## callees

- `0x1800067fc`
- `0x18000f64c`
- `0x180010b1c`
- `0x18001f9f8`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fad3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fb1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fad3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fb1c`

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
  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v14);
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
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v14);
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
0x18001f9f8  push    rbx
0x18001f9fa  push    rsi
0x18001f9fb  push    rdi
0x18001f9fc  sub     rsp, 20h
0x18001fa00  mov     rdi, rdx
0x18001fa03  mov     rsi, rcx
0x18001fa06  mov     edx, [rcx+0B8h]
0x18001fa0c  lea     rcx, [rsp+38h+arg_18]
0x18001fa11  call    ??0CAutoWinRtInit@DataModel@SystemSettings@@QEAA@W4AsynchronousType@12@@Z; SystemSettings::DataModel::CAutoWinRtInit::CAutoWinRtInit(SystemSettings::DataModel::AsynchronousType)
0x18001fa16  nop
0x18001fa17  mov     [rsp+38h+arg_10], 0
0x18001fa20  mov     rax, [rdi]
0x18001fa23  mov     rbx, [rax]
0x18001fa26  lea     rcx, [rsp+38h+arg_10]
0x18001fa2b  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x18001fa30  lea     r8, [rsp+38h+arg_10]
0x18001fa35  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x18001fa3c  mov     rcx, rdi
0x18001fa3f  mov     rax, rbx
0x18001fa42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa47  mov     ebx, eax
0x18001fa49  test    eax, eax
0x18001fa4b  js      loc_18001FB6A
0x18001fa51  mov     rax, [rsi]
0x18001fa54  mov     rdx, [rsp+38h+arg_10]
0x18001fa59  mov     rcx, rsi
0x18001fa5c  mov     rax, [rax+0E8h]
0x18001fa63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa68  mov     ebx, eax
0x18001fa6a  cmp     eax, 80004001h
0x18001fa6f  jnz     loc_18001FB6A
0x18001fa75  mov     [rsp+38h+arg_8], 0
0x18001fa7d  mov     rcx, [rsp+38h+arg_10]
0x18001fa82  mov     rax, [rcx]
0x18001fa85  lea     rdx, [rsp+38h+arg_8]
0x18001fa8a  mov     rax, [rax+30h]
0x18001fa8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa93  mov     ebx, eax
0x18001fa95  test    eax, eax
0x18001fa97  js      loc_18001FB6A
0x18001fa9d  mov     ecx, [rsp+38h+arg_8]
0x18001faa1  sub     ecx, 0Bh
0x18001faa4  jz      loc_18001FB2A
0x18001faaa  cmp     ecx, 1
0x18001faad  jz      short loc_18001FAB9
0x18001faaf  mov     ebx, 80070057h
0x18001fab4  jmp     loc_18001FB6A
0x18001fab9  mov     [rsp+38h+string], 0
0x18001fac2  mov     rdi, [rsp+38h+arg_10]
0x18001fac7  mov     rax, [rdi]
0x18001faca  mov     rbx, [rax+98h]
0x18001fad1  xor     ecx, ecx; string
0x18001fad3  call    cs:__imp_WindowsDeleteString
0x18001fada  nop     dword ptr [rax+rax+00h]
0x18001fadf  mov     [rsp+38h+string], 0
0x18001fae8  lea     rdx, [rsp+38h+string]
0x18001faed  mov     rcx, rdi
0x18001faf0  mov     rax, rbx
0x18001faf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001faf8  mov     ebx, eax
0x18001fafa  test    eax, eax
0x18001fafc  js      short loc_18001FB17
0x18001fafe  mov     rax, [rsi]
0x18001fb01  mov     rdx, [rsp+38h+string]
0x18001fb06  mov     rcx, rsi
0x18001fb09  mov     rax, [rax+0E0h]
0x18001fb10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb15  mov     ebx, eax
0x18001fb17  mov     rcx, [rsp+38h+string]; string
0x18001fb1c  call    cs:__imp_WindowsDeleteString
0x18001fb23  nop     dword ptr [rax+rax+00h]
0x18001fb28  jmp     short loc_18001FB6A
0x18001fb2a  mov     byte ptr [rsp+38h+string], 0
0x18001fb2f  mov     rcx, [rsp+38h+arg_10]
0x18001fb34  mov     rax, [rcx]
0x18001fb37  lea     rdx, [rsp+38h+string]
0x18001fb3c  mov     rax, [rax+90h]
0x18001fb43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb48  mov     ebx, eax
0x18001fb4a  test    eax, eax
0x18001fb4c  js      short loc_18001FB6A
0x18001fb4e  mov     rax, [rsi]
0x18001fb51  cmp     byte ptr [rsp+38h+string], 0
0x18001fb56  setnz   dl
0x18001fb59  mov     rcx, rsi
0x18001fb5c  mov     rax, [rax+0D8h]
0x18001fb63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb68  mov     ebx, eax
0x18001fb6a  lea     rcx, [rsp+38h+arg_10]
0x18001fb6f  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x18001fb74  nop
0x18001fb75  lea     rcx, [rsp+38h+arg_18]; this
0x18001fb7a  call    ??1CAutoWinRtInit@DataModel@SystemSettings@@QEAA@XZ; SystemSettings::DataModel::CAutoWinRtInit::~CAutoWinRtInit(void)
0x18001fb7f  mov     eax, ebx
0x18001fb81  jmp     short loc_18001FB87
0x18001fb83  mov     eax, dword ptr [rsp+38h+string]
0x18001fb87  add     rsp, 20h
0x18001fb8b  pop     rdi
0x18001fb8c  pop     rsi
0x18001fb8d  pop     rbx
0x18001fb8e  retn
```
