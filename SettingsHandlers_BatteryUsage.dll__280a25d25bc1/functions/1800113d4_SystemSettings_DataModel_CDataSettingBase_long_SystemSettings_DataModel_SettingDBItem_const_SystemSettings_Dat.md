# SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetValue(IInspectable *)

- ea: `0x1800113d4`
- end: `0x18001155c`
- name: `?_SetValue@?$CDataSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@AEAAJPEAUIInspectable@@@Z`
- size: `392`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000ea50`
- `0x180010830`

## callees

- `0x180004cfc`
- `0x18000da70`
- `0x18000dfd0`
- `0x1800113d4`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800114ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800114ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800114ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800114ee`

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
                           (unsigned int)"OneCoreUap\\Internal\\Shell\\inc\\SettingHandlersBaseCore.h",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x1800113d4  push    rbx
0x1800113d6  push    rsi
0x1800113d7  push    rdi
0x1800113d8  sub     rsp, 20h
0x1800113dc  mov     rdi, rdx
0x1800113df  mov     rsi, rcx
0x1800113e2  mov     edx, [rcx+0B8h]
0x1800113e8  lea     rcx, [rsp+38h+arg_18]
0x1800113ed  call    ??0CAutoWinRtInit@DataModel@SystemSettings@@QEAA@W4AsynchronousType@12@@Z; SystemSettings::DataModel::CAutoWinRtInit::CAutoWinRtInit(SystemSettings::DataModel::AsynchronousType)
0x1800113f2  nop
0x1800113f3  mov     [rsp+38h+arg_10], 0
0x1800113fc  mov     rax, [rdi]
0x1800113ff  mov     rbx, [rax]
0x180011402  lea     rcx, [rsp+38h+arg_10]
0x180011407  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001140c  lea     r8, [rsp+38h+arg_10]
0x180011411  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x180011418  mov     rcx, rdi
0x18001141b  mov     rax, rbx
0x18001141e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011423  mov     ebx, eax
0x180011425  test    eax, eax
0x180011427  js      loc_180011536
0x18001142d  mov     rax, [rsi]
0x180011430  mov     rdx, [rsp+38h+arg_10]
0x180011435  mov     rcx, rsi
0x180011438  mov     rax, [rax+0E8h]
0x18001143f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011444  mov     ebx, eax
0x180011446  cmp     eax, 80004001h
0x18001144b  jnz     loc_180011536
0x180011451  mov     [rsp+38h+arg_8], 0
0x180011459  mov     rcx, [rsp+38h+arg_10]
0x18001145e  mov     rax, [rcx]
0x180011461  lea     rdx, [rsp+38h+arg_8]
0x180011466  mov     rax, [rax+30h]
0x18001146a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001146f  mov     ebx, eax
0x180011471  test    eax, eax
0x180011473  js      loc_180011536
0x180011479  mov     ecx, [rsp+38h+arg_8]
0x18001147d  sub     ecx, 0Bh
0x180011480  jz      short loc_1800114F6
0x180011482  cmp     ecx, 1
0x180011485  jz      short loc_180011491
0x180011487  mov     ebx, 80070057h
0x18001148c  jmp     loc_180011536
0x180011491  mov     [rsp+38h+string], 0
0x18001149a  mov     rdi, [rsp+38h+arg_10]
0x18001149f  mov     rax, [rdi]
0x1800114a2  mov     rbx, [rax+98h]
0x1800114a9  xor     ecx, ecx; string
0x1800114ab  call    cs:__imp_WindowsDeleteString
0x1800114b1  mov     [rsp+38h+string], 0
0x1800114ba  lea     rdx, [rsp+38h+string]
0x1800114bf  mov     rcx, rdi
0x1800114c2  mov     rax, rbx
0x1800114c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114ca  mov     ebx, eax
0x1800114cc  test    eax, eax
0x1800114ce  js      short loc_1800114E9
0x1800114d0  mov     rax, [rsi]
0x1800114d3  mov     rdx, [rsp+38h+string]
0x1800114d8  mov     rcx, rsi
0x1800114db  mov     rax, [rax+0E0h]
0x1800114e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114e7  mov     ebx, eax
0x1800114e9  mov     rcx, [rsp+38h+string]; string
0x1800114ee  call    cs:__imp_WindowsDeleteString
0x1800114f4  jmp     short loc_180011536
0x1800114f6  mov     byte ptr [rsp+38h+string], 0
0x1800114fb  mov     rcx, [rsp+38h+arg_10]
0x180011500  mov     rax, [rcx]
0x180011503  lea     rdx, [rsp+38h+string]
0x180011508  mov     rax, [rax+90h]
0x18001150f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011514  mov     ebx, eax
0x180011516  test    eax, eax
0x180011518  js      short loc_180011536
0x18001151a  mov     rax, [rsi]
0x18001151d  cmp     byte ptr [rsp+38h+string], 0
0x180011522  setnz   dl
0x180011525  mov     rcx, rsi
0x180011528  mov     rax, [rax+0D8h]
0x18001152f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011534  mov     ebx, eax
0x180011536  lea     rcx, [rsp+38h+arg_10]
0x18001153b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011540  nop
0x180011541  lea     rcx, [rsp+38h+arg_18]; this
0x180011546  call    ??1CAutoWinRtInit@DataModel@SystemSettings@@QEAA@XZ; SystemSettings::DataModel::CAutoWinRtInit::~CAutoWinRtInit(void)
0x18001154b  mov     eax, ebx
0x18001154d  jmp     short loc_180011553
0x18001154f  mov     eax, dword ptr [rsp+38h+string]
0x180011553  add     rsp, 20h
0x180011557  pop     rdi
0x180011558  pop     rsi
0x180011559  pop     rbx
0x18001155a  retn
```
