# SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetValue(IInspectable *)

- ea: `0x18002b0f4`
- end: `0x18002b27c`
- name: `?_SetValue@?$CDataSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@AEAAJPEAUIInspectable@@@Z`
- size: `392`
- prototype: `__int64 __fastcall(unsigned int *, __int64 (***)(void))`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001d650`
- `0x180028b50`

## callees

- `0x18000cfa4`
- `0x180019074`
- `0x18001a4f4`
- `0x18002b0f4`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b1cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b20e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b1cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b20e`

## pseudocode

```c
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
                           (unsigned int)"OnecoreUAP\\internal\\Shell\\inc\\SettingHandlersBaseCore.h",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x18002b0f4  push    rbx
0x18002b0f6  push    rsi
0x18002b0f7  push    rdi
0x18002b0f8  sub     rsp, 20h
0x18002b0fc  mov     rdi, rdx
0x18002b0ff  mov     rsi, rcx
0x18002b102  mov     edx, [rcx+0B8h]
0x18002b108  lea     rcx, [rsp+38h+arg_18]
0x18002b10d  call    ??0CAutoWinRtInit@DataModel@SystemSettings@@QEAA@W4AsynchronousType@12@@Z; SystemSettings::DataModel::CAutoWinRtInit::CAutoWinRtInit(SystemSettings::DataModel::AsynchronousType)
0x18002b112  nop
0x18002b113  mov     [rsp+38h+arg_10], 0
0x18002b11c  mov     rax, [rdi]
0x18002b11f  mov     rbx, [rax]
0x18002b122  lea     rcx, [rsp+38h+arg_10]
0x18002b127  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b12c  lea     r8, [rsp+38h+arg_10]
0x18002b131  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x18002b138  mov     rcx, rdi
0x18002b13b  mov     rax, rbx
0x18002b13e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b143  mov     ebx, eax
0x18002b145  test    eax, eax
0x18002b147  js      loc_18002B256
0x18002b14d  mov     rax, [rsi]
0x18002b150  mov     rdx, [rsp+38h+arg_10]
0x18002b155  mov     rcx, rsi
0x18002b158  mov     rax, [rax+0E8h]
0x18002b15f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b164  mov     ebx, eax
0x18002b166  cmp     eax, 80004001h
0x18002b16b  jnz     loc_18002B256
0x18002b171  mov     [rsp+38h+arg_8], 0
0x18002b179  mov     rcx, [rsp+38h+arg_10]
0x18002b17e  mov     rax, [rcx]
0x18002b181  lea     rdx, [rsp+38h+arg_8]
0x18002b186  mov     rax, [rax+30h]
0x18002b18a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b18f  mov     ebx, eax
0x18002b191  test    eax, eax
0x18002b193  js      loc_18002B256
0x18002b199  mov     ecx, [rsp+38h+arg_8]
0x18002b19d  sub     ecx, 0Bh
0x18002b1a0  jz      short loc_18002B216
0x18002b1a2  cmp     ecx, 1
0x18002b1a5  jz      short loc_18002B1B1
0x18002b1a7  mov     ebx, 80070057h
0x18002b1ac  jmp     loc_18002B256
0x18002b1b1  mov     [rsp+38h+string], 0
0x18002b1ba  mov     rdi, [rsp+38h+arg_10]
0x18002b1bf  mov     rax, [rdi]
0x18002b1c2  mov     rbx, [rax+98h]
0x18002b1c9  xor     ecx, ecx; string
0x18002b1cb  call    cs:__imp_WindowsDeleteString
0x18002b1d1  mov     [rsp+38h+string], 0
0x18002b1da  lea     rdx, [rsp+38h+string]
0x18002b1df  mov     rcx, rdi
0x18002b1e2  mov     rax, rbx
0x18002b1e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b1ea  mov     ebx, eax
0x18002b1ec  test    eax, eax
0x18002b1ee  js      short loc_18002B209
0x18002b1f0  mov     rax, [rsi]
0x18002b1f3  mov     rdx, [rsp+38h+string]
0x18002b1f8  mov     rcx, rsi
0x18002b1fb  mov     rax, [rax+0E0h]
0x18002b202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b207  mov     ebx, eax
0x18002b209  mov     rcx, [rsp+38h+string]; string
0x18002b20e  call    cs:__imp_WindowsDeleteString
0x18002b214  jmp     short loc_18002B256
0x18002b216  mov     byte ptr [rsp+38h+string], 0
0x18002b21b  mov     rcx, [rsp+38h+arg_10]
0x18002b220  mov     rax, [rcx]
0x18002b223  lea     rdx, [rsp+38h+string]
0x18002b228  mov     rax, [rax+90h]
0x18002b22f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b234  mov     ebx, eax
0x18002b236  test    eax, eax
0x18002b238  js      short loc_18002B256
0x18002b23a  mov     rax, [rsi]
0x18002b23d  cmp     byte ptr [rsp+38h+string], 0
0x18002b242  setnz   dl
0x18002b245  mov     rcx, rsi
0x18002b248  mov     rax, [rax+0D8h]
0x18002b24f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b254  mov     ebx, eax
0x18002b256  lea     rcx, [rsp+38h+arg_10]
0x18002b25b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b260  nop
0x18002b261  lea     rcx, [rsp+38h+arg_18]; this
0x18002b266  call    ??1CAutoWinRtInit@DataModel@SystemSettings@@QEAA@XZ; SystemSettings::DataModel::CAutoWinRtInit::~CAutoWinRtInit(void)
0x18002b26b  mov     eax, ebx
0x18002b26d  jmp     short loc_18002B273
0x18002b26f  mov     eax, dword ptr [rsp+38h+string]
0x18002b273  add     rsp, 20h
0x18002b277  pop     rdi
0x18002b278  pop     rsi
0x18002b279  pop     rbx
0x18002b27a  retn
```
