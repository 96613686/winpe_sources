# SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetValue(IInspectable *)

- ea: `0x18001a0bc`
- end: `0x18001a244`
- name: `?_SetValue@?$CDataSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@AEAAJPEAUIInspectable@@@Z`
- size: `392`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800129d0`
- `0x180018de0`

## callees

- `0x180008128`
- `0x1800104bc`
- `0x180011060`
- `0x18001a0bc`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a193`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a1d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a193`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a1d6`

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
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
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
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
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
0x18001a0bc  push    rbx
0x18001a0be  push    rsi
0x18001a0bf  push    rdi
0x18001a0c0  sub     rsp, 20h
0x18001a0c4  mov     rdi, rdx
0x18001a0c7  mov     rsi, rcx
0x18001a0ca  mov     edx, [rcx+0B8h]
0x18001a0d0  lea     rcx, [rsp+38h+arg_18]
0x18001a0d5  call    ??0CAutoWinRtInit@DataModel@SystemSettings@@QEAA@W4AsynchronousType@12@@Z; SystemSettings::DataModel::CAutoWinRtInit::CAutoWinRtInit(SystemSettings::DataModel::AsynchronousType)
0x18001a0da  nop
0x18001a0db  mov     [rsp+38h+arg_10], 0
0x18001a0e4  mov     rax, [rdi]
0x18001a0e7  mov     rbx, [rax]
0x18001a0ea  lea     rcx, [rsp+38h+arg_10]
0x18001a0ef  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001a0f4  lea     r8, [rsp+38h+arg_10]
0x18001a0f9  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x18001a100  mov     rcx, rdi
0x18001a103  mov     rax, rbx
0x18001a106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a10b  mov     ebx, eax
0x18001a10d  test    eax, eax
0x18001a10f  js      loc_18001A21E
0x18001a115  mov     rax, [rsi]
0x18001a118  mov     rdx, [rsp+38h+arg_10]
0x18001a11d  mov     rcx, rsi
0x18001a120  mov     rax, [rax+0E8h]
0x18001a127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a12c  mov     ebx, eax
0x18001a12e  cmp     eax, 80004001h
0x18001a133  jnz     loc_18001A21E
0x18001a139  mov     [rsp+38h+arg_8], 0
0x18001a141  mov     rcx, [rsp+38h+arg_10]
0x18001a146  mov     rax, [rcx]
0x18001a149  lea     rdx, [rsp+38h+arg_8]
0x18001a14e  mov     rax, [rax+30h]
0x18001a152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a157  mov     ebx, eax
0x18001a159  test    eax, eax
0x18001a15b  js      loc_18001A21E
0x18001a161  mov     ecx, [rsp+38h+arg_8]
0x18001a165  sub     ecx, 0Bh
0x18001a168  jz      short loc_18001A1DE
0x18001a16a  cmp     ecx, 1
0x18001a16d  jz      short loc_18001A179
0x18001a16f  mov     ebx, 80070057h
0x18001a174  jmp     loc_18001A21E
0x18001a179  mov     [rsp+38h+string], 0
0x18001a182  mov     rdi, [rsp+38h+arg_10]
0x18001a187  mov     rax, [rdi]
0x18001a18a  mov     rbx, [rax+98h]
0x18001a191  xor     ecx, ecx; string
0x18001a193  call    cs:__imp_WindowsDeleteString
0x18001a199  mov     [rsp+38h+string], 0
0x18001a1a2  lea     rdx, [rsp+38h+string]
0x18001a1a7  mov     rcx, rdi
0x18001a1aa  mov     rax, rbx
0x18001a1ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1b2  mov     ebx, eax
0x18001a1b4  test    eax, eax
0x18001a1b6  js      short loc_18001A1D1
0x18001a1b8  mov     rax, [rsi]
0x18001a1bb  mov     rdx, [rsp+38h+string]
0x18001a1c0  mov     rcx, rsi
0x18001a1c3  mov     rax, [rax+0E0h]
0x18001a1ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1cf  mov     ebx, eax
0x18001a1d1  mov     rcx, [rsp+38h+string]; string
0x18001a1d6  call    cs:__imp_WindowsDeleteString
0x18001a1dc  jmp     short loc_18001A21E
0x18001a1de  mov     byte ptr [rsp+38h+string], 0
0x18001a1e3  mov     rcx, [rsp+38h+arg_10]
0x18001a1e8  mov     rax, [rcx]
0x18001a1eb  lea     rdx, [rsp+38h+string]
0x18001a1f0  mov     rax, [rax+90h]
0x18001a1f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1fc  mov     ebx, eax
0x18001a1fe  test    eax, eax
0x18001a200  js      short loc_18001A21E
0x18001a202  mov     rax, [rsi]
0x18001a205  cmp     byte ptr [rsp+38h+string], 0
0x18001a20a  setnz   dl
0x18001a20d  mov     rcx, rsi
0x18001a210  mov     rax, [rax+0D8h]
0x18001a217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a21c  mov     ebx, eax
0x18001a21e  lea     rcx, [rsp+38h+arg_10]
0x18001a223  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001a228  nop
0x18001a229  lea     rcx, [rsp+38h+arg_18]; this
0x18001a22e  call    ??1CAutoWinRtInit@DataModel@SystemSettings@@QEAA@XZ; SystemSettings::DataModel::CAutoWinRtInit::~CAutoWinRtInit(void)
0x18001a233  mov     eax, ebx
0x18001a235  jmp     short loc_18001A23B
0x18001a237  mov     eax, dword ptr [rsp+38h+string]
0x18001a23b  add     rsp, 20h
0x18001a23f  pop     rdi
0x18001a240  pop     rsi
0x18001a241  pop     rbx
0x18001a242  retn
```
