# RetailDemo::Health::details::BaseEventsWithEvaluation<1>::EvaluateStateFlags(RetailDemo::Health::details::HealthStateFlags)

- ea: `0x18001e830`
- end: `0x18001eafb`
- name: `?EvaluateStateFlags@?$BaseEventsWithEvaluation@$00@details@Health@RetailDemo@@MEAA?AW4HealthEvaluationResult@234@W4HealthStateFlags@234@@Z`
- size: `715`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180003390`
- `0x180003e00`
- `0x18000c168`
- `0x18000e330`
- `0x18001092c`
- `0x18001e830`
- `0x18001fd58`
- `0x18001ff9c`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001e91f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001e91f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e8b3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e8b3`
- `ntdll!RtlGetVersion` at `0x18001e8f1`
- `ntdll!RtlGetVersion` at `0x18001e8f1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e98d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e98d`

## string_xrefs

- `0x18001ea16`: `shellcommon\internal\shell\inc\RdxHealthTracker.h`
- `0x18001ea6d`: `shellcommon\internal\shell\inc\RdxHealthTracker.h`
- `0x18001eaba`: `shellcommon\internal\shell\inc\RdxHealthTracker.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RetailDemo::Health::details::BaseEventsWithEvaluation<1>::EvaluateStateFlags(__int64 a1, __int64 a2)
{
  _DWORD *pvData; // rbx
  unsigned __int16 v5; // si
  const WCHAR *v6; // rax
  __int64 v7; // rbx
  unsigned __int64 v8; // rax
  __int64 v9; // rcx
  HRESULT v10; // eax
  wil::details::in1diag3 *v11; // rcx
  __int64 v12; // rdx
  int v13; // eax
  LPVOID v14; // rdi
  __int64 (__fastcall *v15)(LPVOID, const wchar_t *, __int64); // rbx
  __int64 v16; // rax
  __int64 v17; // rax
  int v18; // eax
  int pdwType; // [rsp+20h] [rbp-E0h]
  DWORD pcbData[2]; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v23[32]; // [rsp+50h] [rbp-B0h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+70h] [rbp-90h] BYREF
  int v25; // [rsp+18Ch] [rbp+8Ch]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  pvData = (_DWORD *)(a1 + 12);
  *(_WORD *)(a1 + 248) = 256;
  v5 = 1;
  pcbData[0] = 180;
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 216);
  if ( RegGetValueW(HKEY_LOCAL_MACHINE, v6, 0, 8u, 0, pvData, pcbData) || pcbData[0] <= 4 || *(_BYTE *)pvData != 9 )
  {
    *pvData = 0;
    *(_BYTE *)pvData = 9;
  }
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x120u);
  VersionInformation.dwOSVersionInfoSize = 292;
  if ( RtlGetVersion(&VersionInformation) || (v7 = 46073850, (v25 & 0x10000) == 0) )
    v7 = 67047419;
  *(_QWORD *)pcbData = 0;
  GetSystemTimeAsFileTime((LPFILETIME)pcbData);
  v8 = pcbData[0] + ((unsigned __int64)pcbData[1] << 32);
  if ( *(_QWORD *)(a1 + 200) )
    v8 = *(_QWORD *)(a1 + 200);
  if ( (a2 & 4) != 0 )
  {
    if ( *(int *)(a1 + 40) >= 0 )
      goto LABEL_15;
    v9 = v7 & a2;
  }
  else
  {
    v9 = v7 & a2;
    if ( (v7 & a2) != 0 )
    {
      v5 = (unsigned int)(v8 - 1791696896)
         + (((unsigned int)v8 + (v8 & 0xFFFFFFFF00000000uLL) + 432000000000LL) & 0xFFFFFFFF00000000uLL) < pcbData[0] + ((unsigned __int64)pcbData[1] << 32);
      goto LABEL_15;
    }
  }
  v5 = 0;
  if ( !v9 )
    v5 = 2;
LABEL_15:
  ppv = 0;
  v10 = CoCreateInstance(
          &GUID_efeb5035_1da0_4b73_afa2_68ed7a1d98e0,
          0,
          0x17u,
          &GUID_05521016_1798_48cc_a5be_7a5ac21ebf95,
          &ppv);
  v11 = retaddr;
  if ( v10 < 0 )
  {
    v12 = 731;
LABEL_25:
    wil::details::in1diag3::_Log_Hr(
      v11,
      (void *)v12,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\RdxHealthTracker.h",
      (const char *)(unsigned int)v10,
      pdwType);
    goto LABEL_26;
  }
  v13 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, _QWORD))(*(_QWORD *)ppv + 32LL))(
          ppv,
          L"DemoEndToEndFlags",
          (unsigned int)a2);
  if ( v13 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2DD,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\RdxHealthTracker.h",
      (const char *)(unsigned int)v13,
      pdwType);
  v14 = ppv;
  v15 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64))(*(_QWORD *)ppv + 24LL);
  v16 = RetailDemo::Health::details::HealthTrackingInfo::ToString(a1 + 16, v23);
  v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v16);
  v18 = v15(v14, L"DemoEndToEndString", v17);
  if ( v18 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2DE,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\RdxHealthTracker.h",
      (const char *)(unsigned int)v18,
      pdwType);
  std::wstring::_Tidy_deallocate(v23);
  v10 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64))(*(_QWORD *)ppv + 32LL))(
          ppv,
          L"HealthMetricVersion",
          9);
  v11 = retaddr;
  if ( v10 < 0 )
  {
    v12 = 735;
    goto LABEL_25;
  }
LABEL_26:
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&ppv);
  return v5;
}

```

## disassembly

```asm
0x18001e830  mov     [rsp-8+arg_10], rbx
0x18001e835  mov     [rsp-8+arg_18], rsi
0x18001e83a  push    rbp
0x18001e83b  push    rdi
0x18001e83c  push    r14
0x18001e83e  lea     rbp, [rsp-0B0h]
0x18001e846  sub     rsp, 1B0h
0x18001e84d  mov     rax, cs:__security_cookie
0x18001e854  xor     rax, rsp
0x18001e857  mov     [rbp+0C0h+var_20], rax
0x18001e85e  mov     rdi, rdx
0x18001e861  mov     r14, rcx
0x18001e864  lea     rbx, [rcx+0Ch]
0x18001e868  mov     word ptr [rcx+0F8h], 100h
0x18001e871  mov     esi, 1
0x18001e876  mov     [rsp+1C0h+var_180], 0B4h
0x18001e87e  add     rcx, 0D8h
0x18001e885  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001e88a  lea     rcx, [rsp+1C0h+var_180]
0x18001e88f  mov     [rsp+1C0h+pcbData], rcx; pcbData
0x18001e894  mov     [rsp+1C0h+pvData], rbx; pvData
0x18001e899  mov     [rsp+1C0h+pdwType], 0; pdwType
0x18001e8a2  lea     r9d, [rsi+7]; dwFlags
0x18001e8a6  xor     r8d, r8d; lpValue
0x18001e8a9  mov     rdx, rax; lpSubKey
0x18001e8ac  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001e8b3  call    cs:__imp_RegGetValueW
0x18001e8b9  test    eax, eax
0x18001e8bb  jnz     short loc_18001E8C9
0x18001e8bd  cmp     [rsp+1C0h+var_180], 4
0x18001e8c2  jbe     short loc_18001E8C9
0x18001e8c4  cmp     byte ptr [rbx], 9
0x18001e8c7  jz      short loc_18001E8D2
0x18001e8c9  mov     dword ptr [rbx], 0
0x18001e8cf  mov     byte ptr [rbx], 9
0x18001e8d2  xor     edx, edx; Val
0x18001e8d4  mov     r8d, 120h; Size
0x18001e8da  lea     rcx, [rsp+1C0h+VersionInformation.dwMajorVersion]; void *
0x18001e8df  call    memset_0
0x18001e8e4  mov     [rsp+1C0h+VersionInformation.dwOSVersionInfoSize], 124h
0x18001e8ec  lea     rcx, [rsp+1C0h+VersionInformation]; lpVersionInformation
0x18001e8f1  call    cs:__imp_RtlGetVersion
0x18001e8f7  test    eax, eax
0x18001e8f9  jnz     short loc_18001E90C
0x18001e8fb  test    [rbp+0C0h+var_34], 10000h
0x18001e905  mov     ebx, 2BF07FAh
0x18001e90a  jnz     short loc_18001E911
0x18001e90c  mov     ebx, 3FF0FFBh
0x18001e911  mov     qword ptr [rsp+1C0h+var_180], 0
0x18001e91a  lea     rcx, [rsp+1C0h+var_180]; lpSystemTimeAsFileTime
0x18001e91f  call    cs:__imp_GetSystemTimeAsFileTime
0x18001e925  mov     r8d, [rsp+1C0h+var_180+4]
0x18001e92a  shl     r8, 20h
0x18001e92e  mov     eax, [rsp+1C0h+var_180]
0x18001e932  add     r8, rax
0x18001e935  mov     rcx, [r14+0C8h]
0x18001e93c  mov     rax, r8
0x18001e93f  test    rcx, rcx
0x18001e942  cmovnz  rax, rcx
0x18001e946  test    dil, 4
0x18001e94a  jz      short loc_18001E9A8
0x18001e94c  cmp     dword ptr [r14+28h], 0
0x18001e951  jge     short loc_18001E966
0x18001e953  mov     rcx, rdi
0x18001e956  and     rcx, rbx
0x18001e959  xor     eax, eax
0x18001e95b  movzx   esi, ax
0x18001e95e  test    rcx, rcx
0x18001e961  jnz     short loc_18001E966
0x18001e963  lea     esi, [rax+2]
0x18001e966  mov     [rsp+1C0h+ppv], 0
0x18001e96f  lea     rax, [rsp+1C0h+ppv]
0x18001e974  mov     [rsp+1C0h+pdwType], rax; int
0x18001e979  lea     r9, _GUID_05521016_1798_48cc_a5be_7a5ac21ebf95; riid
0x18001e980  xor     edx, edx; pUnkOuter
0x18001e982  lea     r8d, [rdx+17h]; dwClsContext
0x18001e986  lea     rcx, _GUID_efeb5035_1da0_4b73_afa2_68ed7a1d98e0; rclsid
0x18001e98d  call    cs:__imp_CoCreateInstance
0x18001e993  mov     rcx, [rbp+0C8h]
0x18001e99a  test    eax, eax
0x18001e99c  jns     short loc_18001E9ED
0x18001e99e  mov     edx, 2DBh
0x18001e9a3  jmp     loc_18001EAB7
0x18001e9a8  mov     rcx, rdi
0x18001e9ab  and     rcx, rbx
0x18001e9ae  jz      short loc_18001E959
0x18001e9b0  mov     rdx, rax
0x18001e9b3  mov     r9, 0FFFFFFFF00000000h
0x18001e9bd  and     rdx, r9
0x18001e9c0  mov     ecx, eax
0x18001e9c2  mov     rax, 649534E000h
0x18001e9cc  add     rdx, rax
0x18001e9cf  add     rdx, rcx
0x18001e9d2  mov     rcx, rdx
0x18001e9d5  and     rcx, r9
0x18001e9d8  mov     eax, edx
0x18001e9da  add     rcx, rax
0x18001e9dd  xor     eax, eax
0x18001e9df  cmp     rcx, r8
0x18001e9e2  setb    al
0x18001e9e5  movzx   esi, ax
0x18001e9e8  jmp     loc_18001E966
0x18001e9ed  mov     rcx, [rsp+1C0h+ppv]
0x18001e9f2  mov     rax, [rcx]
0x18001e9f5  mov     r8d, edi
0x18001e9f8  lea     rdx, aDemoendtoendfl; "DemoEndToEndFlags"
0x18001e9ff  mov     rax, [rax+20h]
0x18001ea03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea08  mov     rcx, [rbp+0C8h]; this
0x18001ea0f  test    eax, eax
0x18001ea11  jns     short loc_18001EA27
0x18001ea13  mov     r9d, eax; char *
0x18001ea16  lea     r8, aShellcommonInt_1; "shellcommon\\internal\\shell\\inc\\RdxH"...
0x18001ea1d  mov     edx, 2DDh; void *
0x18001ea22  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001ea27  mov     rdi, [rsp+1C0h+ppv]
0x18001ea2c  mov     rax, [rdi]
0x18001ea2f  mov     rbx, [rax+18h]
0x18001ea33  lea     rcx, [r14+10h]
0x18001ea37  lea     rdx, [rsp+1C0h+var_170]
0x18001ea3c  call    ?ToString@HealthTrackingInfo@details@Health@RetailDemo@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; RetailDemo::Health::details::HealthTrackingInfo::ToString(void)
0x18001ea41  nop
0x18001ea42  mov     rcx, rax
0x18001ea45  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001ea4a  mov     r8, rax
0x18001ea4d  lea     rdx, aDemoendtoendst; "DemoEndToEndString"
0x18001ea54  mov     rcx, rdi
0x18001ea57  mov     rax, rbx
0x18001ea5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea5f  mov     rcx, [rbp+0C8h]; this
0x18001ea66  test    eax, eax
0x18001ea68  jns     short loc_18001EA7F
0x18001ea6a  mov     r9d, eax; char *
0x18001ea6d  lea     r8, aShellcommonInt_1; "shellcommon\\internal\\shell\\inc\\RdxH"...
0x18001ea74  mov     edx, 2DEh; void *
0x18001ea79  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001ea7e  nop
0x18001ea7f  lea     rcx, [rsp+1C0h+var_170]
0x18001ea84  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ea89  mov     rcx, [rsp+1C0h+ppv]
0x18001ea8e  mov     rax, [rcx]
0x18001ea91  mov     r8d, 9
0x18001ea97  lea     rdx, aHealthmetricve; "HealthMetricVersion"
0x18001ea9e  mov     rax, [rax+20h]
0x18001eaa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eaa7  mov     rcx, [rbp+0C8h]; this
0x18001eaae  test    eax, eax
0x18001eab0  jns     short loc_18001EAC7
0x18001eab2  mov     edx, 2DFh; void *
0x18001eab7  mov     r9d, eax; char *
0x18001eaba  lea     r8, aShellcommonInt_1; "shellcommon\\internal\\shell\\inc\\RdxH"...
0x18001eac1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001eac6  nop
0x18001eac7  lea     rcx, [rsp+1C0h+ppv]
0x18001eacc  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x18001ead1  movzx   eax, si
0x18001ead4  mov     rcx, [rbp+0C0h+var_20]
0x18001eadb  xor     rcx, rsp; StackCookie
0x18001eade  call    __security_check_cookie
0x18001eae3  lea     r11, [rsp+1C0h+var_10]
0x18001eaeb  mov     rbx, [r11+30h]
0x18001eaef  mov     rsi, [r11+38h]
0x18001eaf3  mov     rsp, r11
0x18001eaf6  pop     r14
0x18001eaf8  pop     rdi
0x18001eaf9  pop     rbp
0x18001eafa  retn
```
