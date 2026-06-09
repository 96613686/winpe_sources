# SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverMultipleBatterySingleton::OnBatteryReportChanged(Windows::Devices::Power::IBattery *,IInspectable *)

- ea: `0x1800249b0`
- end: `0x180024b0d`
- name: `?OnBatteryReportChanged@CBatterySaverMultipleBatterySingleton@BatterySaverOneCoreDataModel@SystemSettings@@QEAAJPEAUIBattery@Power@Devices@Windows@@PEAUIInspectable@@@Z`
- size: `349`
- prototype: `__int64 __fastcall(SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverMultipleBatterySingleton *__hidden this, struct Windows::Devices::Power::IBattery *, struct IInspectable *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000cfa4`
- `0x18000eacc`
- `0x180017998`
- `0x1800249b0`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180024a7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180024a7a`

## pseudocode

```c
__int64 __fastcall SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverMultipleBatterySingleton::OnBatteryReportChanged(
        SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverMultipleBatterySingleton *this,
        struct Windows::Devices::Power::IBattery *a2,
        struct IInspectable *a3)
{
  __int64 v5; // rax
  int v6; // eax
  unsigned int v7; // ebx
  unsigned int i; // ebx
  __int64 v9; // r14
  __int64 v10; // rax
  __int64 *v11; // rcx
  __int64 v12; // rax
  HRESULT v13; // edi
  __int64 v14; // rdx
  __int64 v15; // rsi
  __int64 v16; // rbx
  void (__fastcall *v17)(__int64, __int64); // rdi
  __int64 v18; // r8
  __int64 v19; // rdx
  HSTRING string1; // [rsp+20h] [rbp-28h] BYREF
  unsigned int *v21; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  INT32 result; // [rsp+50h] [rbp+8h] BYREF
  HSTRING string2; // [rsp+68h] [rbp+20h] BYREF

  if ( *((_DWORD *)this + 58) == -1 )
    return 2147943568LL;
  v5 = *(_QWORD *)a2;
  string1 = 0;
  v6 = (*(__int64 (__fastcall **)(struct Windows::Devices::Power::IBattery *, HSTRING *))(v5 + 48))(a2, &string1);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x578,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batterysaver\\lib\\batterysaver.cpp",
      (const char *)(unsigned int)v6,
      (int)string1);
    return v7;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= *((_DWORD *)this + 58) )
      return 0;
    v9 = 2 * (i + 15LL);
    v10 = *((_QWORD *)this + 2 * i + 30);
    if ( !v10 )
      continue;
    v11 = *(__int64 **)(v10 + 24);
    if ( !v11 )
      continue;
    v12 = *v11;
    result = 0;
    string2 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(v12 + 48))(v11, &string2);
    if ( v13 < 0 )
      break;
    v13 = WindowsCompareStringOrdinal(string1, string2, &result);
    if ( v13 < 0 )
    {
      v19 = 1413;
      goto LABEL_17;
    }
    if ( !result )
    {
      _mm_lfence();
      v14 = *((_QWORD *)this + 2 * i + 30);
      v15 = *(_QWORD *)(v14 + 24);
      v16 = v14 + 32;
      v17 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 56LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v14 + 32);
      v17(v15, v16);
      v21 = (unsigned int *)*((_QWORD *)this + v9);
      SystemSettings::DataModel::CSingletonHelper<int>::_Notify<_lambda_e398eed577395da8d81f0cd0fd7d36b5_>(
        (__int64)this,
        &v21,
        v18);
      return 0;
    }
  }
  v19 = 1412;
LABEL_17:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v19,
    (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batterysaver\\lib\\batterysaver.cpp",
    (const char *)(unsigned int)v13,
    (int)string1);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800249b0  mov     [rsp+arg_8], rbx
0x1800249b5  mov     [rsp+arg_10], rbp
0x1800249ba  push    rsi
0x1800249bb  push    rdi
0x1800249bc  push    r14
0x1800249be  sub     rsp, 30h
0x1800249c2  cmp     dword ptr [rcx+0E8h], 0FFFFFFFFh
0x1800249c9  mov     r8, rdx
0x1800249cc  mov     rbp, rcx
0x1800249cf  jnz     short loc_1800249DB
0x1800249d1  mov     eax, 80070490h
0x1800249d6  jmp     loc_180024AD6
0x1800249db  mov     rax, [rdx]
0x1800249de  xor     esi, esi
0x1800249e0  lea     rdx, [rsp+48h+string1]
0x1800249e5  mov     [rsp+48h+string1], rsi; int
0x1800249ea  mov     rcx, r8
0x1800249ed  mov     rax, [rax+30h]
0x1800249f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249f6  mov     ebx, eax
0x1800249f8  test    eax, eax
0x1800249fa  jns     short loc_180024A1C
0x1800249fc  mov     rcx, [rsp+48h]; this
0x180024a01  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\coresettinghandlers"...
0x180024a08  mov     r9d, eax; char *
0x180024a0b  mov     edx, 578h; void *
0x180024a10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024a15  mov     eax, ebx
0x180024a17  jmp     loc_180024AD6
0x180024a1c  mov     ebx, esi
0x180024a1e  cmp     ebx, [rbp+0E8h]
0x180024a24  jnb     loc_180024AD4
0x180024a2a  mov     r14d, ebx
0x180024a2d  add     r14, 0Fh
0x180024a31  add     r14, r14
0x180024a34  mov     rax, [rbp+r14*8+0]
0x180024a39  test    rax, rax
0x180024a3c  jz      short loc_180024A8C
0x180024a3e  mov     rcx, [rax+18h]
0x180024a42  test    rcx, rcx
0x180024a45  jz      short loc_180024A8C
0x180024a47  mov     rax, [rcx]
0x180024a4a  lea     rdx, [rsp+48h+string2]
0x180024a4f  mov     [rsp+48h+result], esi
0x180024a53  mov     [rsp+48h+string2], rsi
0x180024a58  mov     rax, [rax+30h]
0x180024a5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a61  mov     edi, eax
0x180024a63  test    eax, eax
0x180024a65  js      loc_180024AF0
0x180024a6b  mov     rdx, [rsp+48h+string2]; string2
0x180024a70  lea     r8, [rsp+48h+result]; result
0x180024a75  mov     rcx, [rsp+48h+string1]; string1
0x180024a7a  call    cs:__imp_WindowsCompareStringOrdinal
0x180024a80  mov     edi, eax
0x180024a82  test    eax, eax
0x180024a84  js      short loc_180024AE9
0x180024a86  cmp     [rsp+48h+result], esi
0x180024a8a  jz      short loc_180024A90
0x180024a8c  inc     ebx
0x180024a8e  jmp     short loc_180024A1E
0x180024a90  lfence
0x180024a93  mov     rdx, [rbp+r14*8+0]
0x180024a98  mov     rsi, [rdx+18h]
0x180024a9c  lea     rbx, [rdx+20h]
0x180024aa0  mov     rcx, rbx
0x180024aa3  mov     rax, [rsi]
0x180024aa6  mov     rdi, [rax+38h]
0x180024aaa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024aaf  mov     rdx, rbx
0x180024ab2  mov     rcx, rsi
0x180024ab5  mov     rax, rdi
0x180024ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024abd  mov     rax, [rbp+r14*8+0]
0x180024ac2  lea     rdx, [rsp+48h+var_20]
0x180024ac7  mov     rcx, rbp
0x180024aca  mov     [rsp+48h+var_20], rax
0x180024acf  call    ??$_Notify@V_lambda_e398eed577395da8d81f0cd0fd7d36b5_@@@?$CSingletonHelper@H@DataModel@SystemSettings@@AEAAXAEBV_lambda_e398eed577395da8d81f0cd0fd7d36b5_@@@Z; SystemSettings::DataModel::CSingletonHelper<int>::_Notify<_lambda_e398eed577395da8d81f0cd0fd7d36b5_>(_lambda_e398eed577395da8d81f0cd0fd7d36b5_ const &)
0x180024ad4  xor     eax, eax
0x180024ad6  mov     rbx, [rsp+48h+arg_8]
0x180024adb  mov     rbp, [rsp+48h+arg_10]
0x180024ae0  add     rsp, 30h
0x180024ae4  pop     r14
0x180024ae6  pop     rdi
0x180024ae7  pop     rsi
0x180024ae8  retn
0x180024ae9  mov     edx, 585h
0x180024aee  jmp     short loc_180024AF5
0x180024af0  mov     edx, 584h; void *
0x180024af5  mov     rcx, [rsp+48h]; this
0x180024afa  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\coresettinghandlers"...
0x180024b01  mov     r9d, edi; char *
0x180024b04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024b09  mov     eax, edi
0x180024b0b  jmp     short loc_180024AD6
```
