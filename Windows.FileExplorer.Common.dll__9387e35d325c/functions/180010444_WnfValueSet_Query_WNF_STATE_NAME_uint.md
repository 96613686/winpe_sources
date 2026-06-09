# WnfValueSet::Query(_WNF_STATE_NAME,uint)

- ea: `0x180010444`
- end: `0x180010705`
- name: `?Query@WnfValueSet@@YA?AUValueSet@Collections@Foundation@Windows@winrt@@U_WNF_STATE_NAME@@I@Z`
- size: `705`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800189e4`

## callees

- `0x18000fc58`
- `0x18000ff08`
- `0x180010010`
- `0x1800102c4`
- `0x180010444`
- `0x180010958`
- `0x180010a78`
- `0x180010bac`
- `0x180010c70`
- `0x180010cc4`
- `0x180010d04`
- `0x180010d4c`
- `0x180010da0`
- `0x180010ef8`
- `0x180022388`
- `0x180030bcc`
- `0x180037780`
- `0x180043c98`
- `0x180089010`

## import_xrefs

- `ntdll!NtQueryWnfStateData` at `0x180010518`
- `ntdll!NtQueryWnfStateData` at `0x180010518`
- `api-ms-win-ro-typeresolution-l1-1-1!RoCreatePropertySetSerializer` at `0x180010594`
- `api-ms-win-ro-typeresolution-l1-1-1!RoCreatePropertySetSerializer` at `0x180010594`

## string_xrefs

- `0x180010564`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\WnfValueSet.h`
- `0x1800106e5`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\WnfValueSet.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
winrt::Windows::Foundation::Collections::ValueSet *__fastcall WnfValueSet::Query(
        winrt::Windows::Foundation::Collections::ValueSet *a1,
        __int64 a2)
{
  __int64 v3; // rcx
  int v4; // esi
  int v5; // eax
  int v6; // eax
  unsigned int v7; // esi
  const char *v8; // r9
  int v9; // eax
  winrt::Windows::Foundation::Collections::ValueSet *result; // rax
  int v11; // [rsp+20h] [rbp-58h]
  int v12; // [rsp+20h] [rbp-58h]
  struct wil::WNF_CHANGE_STAMP_STRUCT *v13; // [rsp+30h] [rbp-48h] BYREF
  __int64 v14; // [rsp+38h] [rbp-40h] BYREF
  __int64 v15; // [rsp+40h] [rbp-38h] BYREF
  _WNF_STATE_NAME v16; // [rsp+48h] [rbp-30h]
  winrt::Windows::Foundation::Collections::ValueSet *v17; // [rsp+50h] [rbp-28h]
  __int64 *v18; // [rsp+58h] [rbp-20h]
  __int64 v19; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v17 = a1;
  v19 = a2;
  v16.Data[1] = 1;
  winrt::Windows::Foundation::Collections::ValueSet::ValueSet(a1);
  try
  {
    v16.Data[1] = 1;
    LODWORD(v14) = 1024;
    v13 = (struct wil::WNF_CHANGE_STAMP_STRUCT *)&v14;
    v18 = &qword_1800AE348;
    _InterlockedIncrement64(&qword_1800AE348);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Storage::Streams::Buffer,winrt::Windows::Storage::Streams::IBufferFactory> )
    {
      winrt::impl::consume_Windows_Storage_Streams_IBufferFactory<winrt::Windows::Storage::Streams::IBufferFactory>::Create(
        &winrt::impl::factory_cache_entry_v<winrt::Windows::Storage::Streams::Buffer,winrt::Windows::Storage::Streams::IBufferFactory>,
        &v15,
        (unsigned int)v14);
      v16.Data[1] = 7;
      _InterlockedDecrement64(&qword_1800AE348);
    }
    else
    {
      _InterlockedDecrement64(&qword_1800AE348);
      winrt::impl::factory_cache_entry<winrt::Windows::Storage::Streams::Buffer,winrt::Windows::Storage::Streams::IBufferFactory>::call<_lambda_e7631c1690498db2dc470481c9b63fc5_ &>(
        v3,
        &v15,
        &v13);
      v16.Data[1] = 3;
    }
    v4 = winrt::impl::consume_Windows_Storage_Streams_IBuffer<winrt::Windows::Storage::Streams::IBuffer>::Capacity(&v15);
    v5 = winrt::impl::consume_Windows_Storage_Streams_IBuffer<winrt::Windows::Storage::Streams::IBuffer>::data(&v15);
    LODWORD(v14) = 0;
    LODWORD(v13) = v4;
    v11 = v5;
    v6 = NtQueryWnfStateData(&v19, 0, 0, &v14);
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_NtStatus(
        retaddr,
        (void *)0x2EF,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
        (const char *)(unsigned int)v6,
        v11);
    }
    else
    {
      v7 = (unsigned int)v13;
      v13 = (struct wil::WNF_CHANGE_STAMP_STRUCT *)(unsigned int)v13;
      v8 = 0;
      if ( (_DWORD)v14
        && (int)wil::details::in1diag3::Log_IfFailedWithExpected(
                  retaddr,
                  (void *)0x43,
                  (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\WnfValueSet.h",
                  0,
                  1,
                  5) >= 0 )
      {
        winrt::impl::consume_Windows_Storage_Streams_IBuffer<winrt::Windows::Storage::Streams::IBuffer>::Length(
          &v15,
          v7);
        v14 = 0;
        v9 = RoCreatePropertySetSerializer(&v14);
        if ( v9 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x49,
            (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\WnfValueSet.h",
            (const char *)(unsigned int)v9,
            v12);
        }
        else
        {
          wil::convert_from_abi<winrt::Windows::Storage::Streams::IPropertySetSerializer>(&v13, v14);
          winrt::impl::consume_Windows_Storage_Streams_IPropertySetSerializer<winrt::Windows::Storage::Streams::IPropertySetSerializer>::Deserialize(
            &v13,
            a1,
            &v15);
          if ( v13 )
            winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v13);
        }
        if ( v14 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      }
    }
    if ( v15 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v15);
    result = a1;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x66,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\WnfValueSet.h",
      v8);
    return v17;
  }
  return result;
}

```

## disassembly

```asm
0x180010444  mov     r11, rsp
0x180010447  mov     [r11+18h], rbx
0x18001044b  mov     [r11+20h], rsi
0x18001044f  push    rdi
0x180010450  sub     rsp, 70h
0x180010454  mov     rax, cs:__security_cookie
0x18001045b  xor     rax, rsp
0x18001045e  mov     [rsp+78h+var_10], rax
0x180010463  mov     rdi, rcx
0x180010466  mov     [r11-28h], rcx
0x18001046a  mov     [r11-18h], rdx
0x18001046e  mov     [rsp+78h+var_30.Data+4], 1
0x180010476  call    ??0ValueSet@Collections@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::Collections::ValueSet::ValueSet(void)
0x18001047b  nop
0x18001047c  mov     [rsp+78h+var_30.Data+4], 1
0x180010484  mov     ebx, 400h
0x180010489  mov     dword ptr [rsp+78h+var_40], ebx
0x18001048d  lea     rax, [rsp+78h+var_40]
0x180010492  mov     [rsp+78h+var_48], rax
0x180010497  lea     rax, qword_1800AE348
0x18001049e  mov     [rsp+78h+var_20], rax
0x1800104a3  lock inc cs:qword_1800AE348
0x1800104ab  cmp     cs:??$factory_cache_entry_v@UBuffer@Streams@Storage@Windows@winrt@@UIBufferFactory@2345@@impl@winrt@@3U?$factory_cache_entry@UBuffer@Streams@Storage@Windows@winrt@@UIBufferFactory@2345@@12@A, 0; factory_cache_entry<winrt::Windows::Storage::Streams::Buffer,winrt::Windows::Storage::Streams::IBufferFactory>::winrt::factory_cache_entry<winrt::Windows::Storage::Streams::Buffer,winrt::Windows::Storage::Streams::IBufferFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Storage::Streams::Buffer,winrt::Windows::Storage::Streams::IBufferFactory>
0x1800104b3  jnz     loc_180010629
0x1800104b9  lock dec cs:qword_1800AE348
0x1800104c1  lea     r8, [rsp+78h+var_48]
0x1800104c6  lea     rdx, [rsp+78h+var_38]
0x1800104cb  call    ??$call@AEAV_lambda_e7631c1690498db2dc470481c9b63fc5_@@@?$factory_cache_entry@UBuffer@Streams@Storage@Windows@winrt@@UIBufferFactory@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_e7631c1690498db2dc470481c9b63fc5_@@@Z
0x1800104d0  mov     [rsp+78h+var_30.Data+4], 3
0x1800104d8  lea     rcx, [rsp+78h+var_38]
0x1800104dd  call    ?Capacity@?$consume_Windows_Storage_Streams_IBuffer@UIBuffer@Streams@Storage@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Storage_Streams_IBuffer<winrt::Windows::Storage::Streams::IBuffer>::Capacity(void)
0x1800104e2  mov     esi, eax
0x1800104e4  lea     rcx, [rsp+78h+var_38]
0x1800104e9  call    ?data@?$consume_Windows_Storage_Streams_IBuffer@UIBuffer@Streams@Storage@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Storage_Streams_IBuffer<winrt::Windows::Storage::Streams::IBuffer>::data(void)
0x1800104ee  mov     dword ptr [rsp+78h+var_40], 0
0x1800104f6  mov     dword ptr [rsp+78h+var_48], esi
0x1800104fa  lea     rcx, [rsp+78h+var_48]
0x1800104ff  mov     [rsp+78h+var_50], rcx; unsigned __int64 *
0x180010504  mov     [rsp+78h+var_58], rax; int
0x180010509  lea     r9, [rsp+78h+var_40]
0x18001050e  xor     r8d, r8d
0x180010511  xor     edx, edx
0x180010513  lea     rcx, [rsp+78h+var_18]
0x180010518  call    cs:__imp_NtQueryWnfStateData
0x18001051e  test    eax, eax
0x180010520  js      loc_180010654
0x180010526  cmp     dword ptr [rsp+78h+var_40], 0
0x18001052b  setnz   al
0x18001052e  mov     esi, dword ptr [rsp+78h+var_48]
0x180010532  mov     [rsp+78h+var_48], rsi; struct wil::WNF_CHANGE_STAMP_STRUCT *
0x180010537  xor     r9d, r9d; char *
0x18001053a  test    al, al
0x18001053c  jz      loc_1800105F4
0x180010542  cmp     r9d, 8007007Ah
0x180010549  jz      loc_18001066F
0x18001054f  mov     rcx, [rsp+78h]; this
0x180010554  mov     dword ptr [rsp+78h+var_50], 80070005h; char
0x18001055c  mov     dword ptr [rsp+78h+var_58], 1; int
0x180010564  lea     r8, aShellcommonShe_3; "shellcommon\\shell\\fileexplorer\\windo"...
0x18001056b  mov     edx, 43h ; 'C'; void *
0x180010570  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x180010575  test    eax, eax
0x180010577  js      short loc_1800105F4
0x180010579  mov     edx, esi
0x18001057b  lea     rcx, [rsp+78h+var_38]
0x180010580  call    ?Length@?$consume_Windows_Storage_Streams_IBuffer@UIBuffer@Streams@Storage@Windows@winrt@@@impl@winrt@@QEBA@I@Z; winrt::impl::consume_Windows_Storage_Streams_IBuffer<winrt::Windows::Storage::Streams::IBuffer>::Length(uint)
0x180010585  nop
0x180010586  mov     [rsp+78h+var_40], 0
0x18001058f  lea     rcx, [rsp+78h+var_40]
0x180010594  call    cs:__imp_RoCreatePropertySetSerializer
0x18001059a  mov     rcx, [rsp+78h]; this
0x18001059f  test    eax, eax
0x1800105a1  js      loc_1800106E2
0x1800105a7  mov     rdx, [rsp+78h+var_40]
0x1800105ac  lea     rcx, [rsp+78h+var_48]
0x1800105b1  call    ??$convert_from_abi@UIPropertySetSerializer@Streams@Storage@Windows@winrt@@@wil@@YA?AUIPropertySetSerializer@Streams@Storage@Windows@winrt@@PEAUIUnknown@@@Z; wil::convert_from_abi<winrt::Windows::Storage::Streams::IPropertySetSerializer>(IUnknown *)
0x1800105b6  nop
0x1800105b7  lea     r8, [rsp+78h+var_38]
0x1800105bc  mov     rdx, rdi
0x1800105bf  lea     rcx, [rsp+78h+var_48]
0x1800105c4  call    ?Deserialize@?$consume_Windows_Storage_Streams_IPropertySetSerializer@UIPropertySetSerializer@Streams@Storage@Windows@winrt@@@impl@winrt@@QEBA@AEBUIPropertySet@Collections@Foundation@Windows@3@AEBUIBuffer@Streams@Storage@73@@Z; winrt::impl::consume_Windows_Storage_Streams_IPropertySetSerializer<winrt::Windows::Storage::Streams::IPropertySetSerializer>::Deserialize(winrt::Windows::Foundation::Collections::IPropertySet const &,winrt::Windows::Storage::Streams::IBuffer const &)
0x1800105c9  nop
0x1800105ca  cmp     [rsp+78h+var_48], 0
0x1800105d0  jz      short loc_1800105DD
0x1800105d2  lea     rcx, [rsp+78h+var_48]
0x1800105d7  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800105dc  nop
0x1800105dd  mov     rcx, [rsp+78h+var_40]
0x1800105e2  test    rcx, rcx
0x1800105e5  jz      short loc_1800105F4
0x1800105e7  mov     rax, [rcx]
0x1800105ea  mov     rax, [rax+10h]
0x1800105ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105f3  nop
0x1800105f4  cmp     [rsp+78h+var_38], 0
0x1800105fa  jz      short loc_180010607
0x1800105fc  lea     rcx, [rsp+78h+var_38]
0x180010601  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180010606  nop
0x180010607  mov     rax, rdi
0x18001060a  mov     rcx, [rsp+78h+var_10]
0x18001060f  xor     rcx, rsp; StackCookie
0x180010612  call    __security_check_cookie
0x180010617  lea     r11, [rsp+78h+var_8]
0x18001061c  mov     rbx, [r11+20h]
0x180010620  mov     rsi, [r11+28h]
0x180010624  mov     rsp, r11
0x180010627  pop     rdi
0x180010628  retn
0x180010629  mov     r8d, dword ptr [rsp+78h+var_40]
0x18001062e  lea     rdx, [rsp+78h+var_38]
0x180010633  lea     rcx, ??$factory_cache_entry_v@UBuffer@Streams@Storage@Windows@winrt@@UIBufferFactory@2345@@impl@winrt@@3U?$factory_cache_entry@UBuffer@Streams@Storage@Windows@winrt@@UIBufferFactory@2345@@12@A; factory_cache_entry<winrt::Windows::Storage::Streams::Buffer,winrt::Windows::Storage::Streams::IBufferFactory>::winrt::factory_cache_entry<winrt::Windows::Storage::Streams::Buffer,winrt::Windows::Storage::Streams::IBufferFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Storage::Streams::Buffer,winrt::Windows::Storage::Streams::IBufferFactory>
0x18001063a  call    ?Create@?$consume_Windows_Storage_Streams_IBufferFactory@UIBufferFactory@Streams@Storage@Windows@winrt@@@impl@winrt@@QEBA@I@Z; winrt::impl::consume_Windows_Storage_Streams_IBufferFactory<winrt::Windows::Storage::Streams::IBufferFactory>::Create(uint)
0x18001063f  mov     [rsp+78h+var_30.Data+4], 7
0x180010647  lock dec cs:qword_1800AE348
0x18001064f  jmp     loc_1800104D8
0x180010654  mov     rcx, [rsp+78h]; this
0x180010659  mov     r9d, eax; char *
0x18001065c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x180010663  mov     edx, 2EFh; void *
0x180010668  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001066d  jmp     short loc_1800105F4
0x18001066f  cmp     ebx, 1000h
0x180010675  ja      loc_18001054F
0x18001067b  add     ebx, ebx
0x18001067d  mov     edx, ebx; unsigned int
0x18001067f  lea     rcx, [rsp+78h+var_40]; this
0x180010684  call    ??0Buffer@Streams@Storage@Windows@winrt@@QEAA@I@Z; winrt::Windows::Storage::Streams::Buffer::Buffer(uint)
0x180010689  mov     rdx, rax
0x18001068c  lea     rcx, [rsp+78h+var_38]
0x180010691  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x180010696  lea     rcx, [rsp+78h+var_40]
0x18001069b  call    ??1?$IIterator@UPerFolderRootInfo@Storage@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>::~IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>(void)
0x1800106a0  lea     rcx, [rsp+78h+var_38]
0x1800106a5  call    ?Capacity@?$consume_Windows_Storage_Streams_IBuffer@UIBuffer@Streams@Storage@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Storage_Streams_IBuffer<winrt::Windows::Storage::Streams::IBuffer>::Capacity(void)
0x1800106aa  mov     esi, eax
0x1800106ac  lea     rcx, [rsp+78h+var_38]
0x1800106b1  call    ?data@?$consume_Windows_Storage_Streams_IBuffer@UIBuffer@Streams@Storage@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Storage_Streams_IBuffer<winrt::Windows::Storage::Streams::IBuffer>::data(void)
0x1800106b6  mov     r9d, esi; void *
0x1800106b9  lea     rcx, [rsp+78h+var_48]
0x1800106be  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x1800106c3  mov     r8, rax; bool *
0x1800106c6  lea     rdx, [rsp+78h+var_30]; struct _WNF_STATE_NAME *
0x1800106cb  lea     rcx, [rsp+78h+var_18]; this
0x1800106d0  call    ?wnf_query_nothrow@wil@@YAJAEBU_WNF_STATE_NAME@@PEA_NPEAX_KPEA_KPEAUWNF_CHANGE_STAMP_STRUCT@1@@Z; wil::wnf_query_nothrow(_WNF_STATE_NAME const &,bool *,void *,unsigned __int64,unsigned __int64 *,wil::WNF_CHANGE_STAMP_STRUCT *)
0x1800106d5  mov     r9d, eax
0x1800106d8  mov     rsi, [rsp+78h+var_48]
0x1800106dd  jmp     loc_180010542
0x1800106e2  mov     r9d, eax; char *
0x1800106e5  lea     r8, aShellcommonShe_3; "shellcommon\\shell\\fileexplorer\\windo"...
0x1800106ec  mov     edx, 49h ; 'I'; void *
0x1800106f1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800106f6  jmp     loc_1800105DD
0x1800106fb  mov     rax, [rsp+78h+var_28]
0x180010700  jmp     loc_18001060A
```
