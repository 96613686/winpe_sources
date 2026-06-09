# PrintConfig::CIppCSRHelper::CallPsaUpdatePdcAndPdrIfNeeded(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,int,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,int,ushort const *,ushort const *,ulong *,ulong *)

- ea: `0x180059c78`
- end: `0x18005a15c`
- name: `?CallPsaUpdatePdcAndPdrIfNeeded@CIppCSRHelper@PrintConfig@@SAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@H0HPEBG1PEAK2@Z`
- size: `1252`
- prototype: `__int64 __fastcall(const BYTE **, UINT, const BYTE **, UINT, __int64, const wchar_t *, UINT *, _DWORD *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180010abc`
- `0x1800446d8`

## callees

- `0x180004564`
- `0x18000f830`
- `0x1800192fc`
- `0x1800197b4`
- `0x1800197f8`
- `0x180052778`
- `0x180059c78`
- `0x18005a164`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180059e3f`
- `KERNEL32!SetLastError` at `0x180059ea5`
- `KERNEL32!SetLastError` at `0x180059e3f`
- `KERNEL32!SetLastError` at `0x180059ea5`
- `KERNEL32!GetLastError` at `0x180059e20`
- `KERNEL32!GetLastError` at `0x180059e86`
- `KERNEL32!GetLastError` at `0x180059e20`
- `KERNEL32!GetLastError` at `0x180059e86`
- `ole32!CoTaskMemFree` at `0x180059e31`
- `ole32!CoTaskMemFree` at `0x180059e97`
- `ole32!CoTaskMemFree` at `0x180059e31`
- `ole32!CoTaskMemFree` at `0x180059e97`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x180059d51`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x180059d99`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x180059d51`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x180059d99`
- `Print.PrintSupport.Source!UpdatePDCAndPDR` at `0x180059e01`
- `Print.PrintSupport.Source!UpdatePDCAndPDR` at `0x180059e01`
- `Print.PrintSupport.Source!IsPsaEnabledForContractAsCurrentUser` at `0x180059ce1`
- `Print.PrintSupport.Source!IsPsaEnabledForContractAsCurrentUser` at `0x180059ce1`
- `Print.PrintSupport.Source!UpdatePdcRegenerationRegKey` at `0x180059ee2`
- `Print.PrintSupport.Source!UpdatePdcRegenerationRegKey` at `0x180059f1f`
- `Print.PrintSupport.Source!UpdatePdcRegenerationRegKey` at `0x180059ee2`
- `Print.PrintSupport.Source!UpdatePdcRegenerationRegKey` at `0x180059f1f`

## string_xrefs

- `0x180059ccf`: `Windows.PrintSupportExtension`
- `0x180059cfc`: `printscan\print\drivers\usermode\config\printconfig\ippcsrhelper.cpp`
- `0x180059efd`: `printscan\print\drivers\usermode\config\printconfig\ippcsrhelper.cpp`
- `0x180059f3a`: `printscan\print\drivers\usermode\config\printconfig\ippcsrhelper.cpp`
- `0x18005a02f`: `printscan\print\drivers\usermode\config\printconfig\ippcsrhelper.cpp`
- `0x18005a03f`: `printscan\print\drivers\usermode\config\printconfig\ippcsrhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall PrintConfig::CIppCSRHelper::CallPsaUpdatePdcAndPdrIfNeeded(
        const BYTE **a1,
        UINT a2,
        const BYTE **a3,
        UINT a4,
        __int64 a5,
        const wchar_t *a6,
        UINT *a7,
        _DWORD *a8)
{
  const wchar_t *v12; // r15
  int v13; // eax
  IStream *v14; // rax
  const char *v15; // r9
  IStream *v16; // rdi
  IStream *v17; // rax
  const char *v18; // r9
  IStream *v19; // rbx
  int updated; // esi
  BYTE *v21; // r13
  DWORD LastError; // esi
  int v23; // eax
  int v24; // esi
  void **v25; // rax
  void *v26; // r13
  DWORD v27; // esi
  int v28; // eax
  int v29; // esi
  int v30; // eax
  int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rcx
  PrintConfig::CPageImageableSize *v35; // rcx
  unsigned int v36; // [rsp+30h] [rbp-C8h]
  __int64 v37; // [rsp+38h] [rbp-C0h] BYREF
  int v38[2]; // [rsp+40h] [rbp-B8h] BYREF
  __int64 v39; // [rsp+48h] [rbp-B0h]
  IStream *v40; // [rsp+50h] [rbp-A8h]
  IStream *v41; // [rsp+58h] [rbp-A0h]
  const PrintCore::WindowsError *v42; // [rsp+60h] [rbp-98h] BYREF
  const hr_error *v43; // [rsp+68h] [rbp-90h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+70h] [rbp-88h] BYREF
  _BYTE v45[32]; // [rsp+90h] [rbp-68h] BYREF
  _BYTE v46[72]; // [rsp+B0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]
  char v49; // [rsp+108h] [rbp+10h] BYREF
  void **v50; // [rsp+110h] [rbp+18h]

  v50 = (void **)a3;
  v39 = -2;
  *a7 = a2;
  *a8 = 0;
  v36 = 0;
  v49 = 0;
  v12 = a6;
  v13 = IsPsaEnabledForContractAsCurrentUser(a6, L"Windows.PrintSupportExtension", &v49);
  if ( v13 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x29,
      (__int64)"printscan\\print\\drivers\\usermode\\config\\printconfig\\ippcsrhelper.cpp",
      (const char *)(unsigned int)v13);
  try
  {
    if ( v49 )
    {
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          0xAu,
          (const GUID *)WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids,
          v12);
      }
      v14 = SHCreateMemStream(*a1, a2);
      v16 = v14;
      v40 = v14;
      if ( v14 )
        ((void (__fastcall *)(IStream *))v14->lpVtbl->AddRef)(v14);
      if ( !v16 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          46,
          (__int64)"printscan\\print\\drivers\\usermode\\config\\printconfig\\ippcsrhelper.cpp",
          v15);
      *(_QWORD *)v38 = 0;
      v17 = SHCreateMemStream(*a3, a4);
      v19 = v17;
      v41 = v17;
      if ( v17 )
        ((void (__fastcall *)(IStream *))v17->lpVtbl->AddRef)(v17);
      if ( !v19 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          50,
          (__int64)"printscan\\print\\drivers\\usermode\\config\\printconfig\\ippcsrhelper.cpp",
          v18);
      v37 = 0;
      updated = UpdatePDCAndPDR(v12, v16, v19, a5, v38, &v37);
      if ( updated < 0 )
      {
        if ( updated != -2147467263 )
        {
          v35 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
            {
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                0xEu,
                (const GUID *)WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids,
                v12);
              v35 = WPP_GLOBAL_Control;
            }
            if ( v35 != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control && (*((_BYTE *)v35 + 68) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)v35 + 7),
                0xFu,
                (const GUID *)WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids,
                updated);
          }
          hr_error::hr_error((hr_error *)v46, updated);
          throw (hr_error *)v46;
        }
        v31 = UpdatePdcRegenerationRegKey(v12);
        if ( v31 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x42,
            (__int64)"printscan\\print\\drivers\\usermode\\config\\printconfig\\ippcsrhelper.cpp",
            (const char *)(unsigned int)v31);
        if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            0xDu,
            (const GUID *)WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids,
            v12);
        }
      }
      else
      {
        v21 = (BYTE *)*a1;
        if ( v21 )
        {
          LastError = GetLastError();
          CoTaskMemFree(v21);
          SetLastError(LastError);
        }
        *a1 = 0;
        v23 = PrintConfig::CIppCSRHelper::ConvertIStreamToData(v38, a1, a7);
        v24 = v23;
        if ( v23 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              0xBu,
              (const GUID *)WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids,
              v23);
          }
          hr_error::hr_error((hr_error *)pExceptionObject, v24);
          throw (hr_error *)pExceptionObject;
        }
        v25 = v50;
        v26 = *v50;
        if ( *v50 )
        {
          v27 = GetLastError();
          CoTaskMemFree(v26);
          SetLastError(v27);
          v25 = v50;
        }
        *v25 = 0;
        v28 = PrintConfig::CIppCSRHelper::ConvertIStreamToData(&v37, v25, a8);
        v29 = v28;
        if ( v28 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              0xCu,
              (const GUID *)WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids,
              v28);
          }
          hr_error::hr_error((hr_error *)v45, v29);
          throw (hr_error *)v45;
        }
        v30 = UpdatePdcRegenerationRegKey(v12);
        if ( v30 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x3D,
            (__int64)"printscan\\print\\drivers\\usermode\\config\\printconfig\\ippcsrhelper.cpp",
            (const char *)(unsigned int)v30);
      }
      v32 = v37;
      if ( v37 )
      {
        v37 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      }
      ((void (__fastcall *)(IStream *))v19->lpVtbl->Release)(v19);
      v33 = *(_QWORD *)v38;
      if ( *(_QWORD *)v38 )
      {
        *(_QWORD *)v38 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      }
      ((void (__fastcall *)(IStream *))v16->lpVtbl->Release)(v16);
    }
    else if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x10u,
        (const GUID *)WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids,
        v12);
    }
  }
  catch ( std::bad_alloc )
  {
    return (unsigned int)-2147024882;
  }
  catch ( const hr_error *v43 )
  {
    return *((unsigned int *)v43 + 6);
  }
  catch ( const PrintCore::WindowsError *v42 )
  {
    return *((unsigned int *)v42 + 6);
  }
  catch ( std::exception )
  {
    return (unsigned int)-2147467259;
  }
  catch ( ... )
  {
    return (unsigned int)-2147418113;
  }
  return v36;
}

```

## disassembly

```asm
0x180059c78  mov     r11, rsp
0x180059c7b  mov     [r11+18h], r8
0x180059c7f  mov     [r11+8], rcx
0x180059c83  push    rsi
0x180059c84  push    rdi
0x180059c85  push    r13
0x180059c87  push    r14
0x180059c89  push    r15
0x180059c8b  sub     rsp, 0D0h
0x180059c92  mov     [rsp+0F8h+var_B0], 0FFFFFFFFFFFFFFFEh
0x180059c9b  mov     [r11+20h], rbx
0x180059c9f  mov     esi, r9d
0x180059ca2  mov     rbx, r8
0x180059ca5  mov     edi, edx
0x180059ca7  mov     r13, rcx
0x180059caa  mov     rax, [rsp+0F8h+arg_30]
0x180059cb2  mov     [rax], edx
0x180059cb4  xor     r14d, r14d
0x180059cb7  mov     rax, [rsp+0F8h+arg_38]
0x180059cbf  mov     [rax], r14d
0x180059cc2  mov     [rsp+0F8h+var_C8], r14d
0x180059cc7  mov     [r11+10h], r14b
0x180059ccb  lea     r8, [r11+10h]
0x180059ccf  lea     rdx, aWindowsPrintsu_1; "Windows.PrintSupportExtension"
0x180059cd6  mov     r15, [rsp+0F8h+arg_28]
0x180059cde  mov     rcx, r15
0x180059ce1  call    cs:__imp_IsPsaEnabledForContractAsCurrentUser
0x180059ce8  nop     dword ptr [rax+rax+00h]
0x180059ced  mov     rcx, [rsp+0F8h]; this
0x180059cf5  test    eax, eax
0x180059cf7  jns     short loc_180059D0C
0x180059cf9  mov     r9d, eax; char *
0x180059cfc  lea     r8, aPrintscanPrint_17; "printscan\\print\\drivers\\usermode\\co"...
0x180059d03  lea     edx, [r14+29h]; void *
0x180059d07  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180059d0c  cmp     [rsp+0F8h+arg_8], r14b
0x180059d14  jz      loc_180059FD8
0x180059d1a  lea     r14, WPP_GLOBAL_Control
0x180059d21  mov     rcx, cs:WPP_GLOBAL_Control
0x180059d28  cmp     rcx, r14
0x180059d2b  jz      short loc_180059D4B
0x180059d2d  test    byte ptr [rcx+44h], 4
0x180059d31  jz      short loc_180059D4B
0x180059d33  mov     edx, 0Ah
0x180059d38  mov     r9, r15
0x180059d3b  lea     r8, WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids
0x180059d42  mov     rcx, [rcx+38h]
0x180059d46  call    WPP_SF_S
0x180059d4b  mov     edx, edi; cbInit
0x180059d4d  mov     rcx, [r13+0]; pInit
0x180059d51  call    cs:__imp_SHCreateMemStream
0x180059d58  nop     dword ptr [rax+rax+00h]
0x180059d5d  mov     rdi, rax
0x180059d60  mov     [rsp+0F8h+var_A8], rax
0x180059d65  test    rax, rax
0x180059d68  jz      short loc_180059D7A
0x180059d6a  mov     rax, [rax]
0x180059d6d  mov     rcx, rdi
0x180059d70  mov     rax, [rax+8]
0x180059d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059d79  nop
0x180059d7a  mov     rcx, [rsp+0F8h]; this
0x180059d82  test    rdi, rdi
0x180059d85  jz      loc_18005A02F
0x180059d8b  mov     qword ptr [rsp+0F8h+var_B8], 0
0x180059d94  mov     edx, esi; cbInit
0x180059d96  mov     rcx, [rbx]; pInit
0x180059d99  call    cs:__imp_SHCreateMemStream
0x180059da0  nop     dword ptr [rax+rax+00h]
0x180059da5  mov     rbx, rax
0x180059da8  mov     [rsp+0F8h+var_A0], rax
0x180059dad  test    rax, rax
0x180059db0  jz      short loc_180059DC2
0x180059db2  mov     rax, [rax]
0x180059db5  mov     rcx, rbx
0x180059db8  mov     rax, [rax+8]
0x180059dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059dc1  nop
0x180059dc2  mov     rcx, [rsp+0F8h]; this
0x180059dca  test    rbx, rbx
0x180059dcd  jz      loc_18005A03F
0x180059dd3  mov     [rsp+0F8h+var_C0], 0
0x180059ddc  lea     rax, [rsp+0F8h+var_C0]
0x180059de1  mov     [rsp+0F8h+var_D0], rax
0x180059de6  lea     rax, [rsp+0F8h+var_B8]
0x180059deb  mov     qword ptr [rsp+0F8h+var_D8], rax; int
0x180059df0  mov     r9, [rsp+0F8h+arg_20]
0x180059df8  mov     r8, rbx
0x180059dfb  mov     rdx, rdi
0x180059dfe  mov     rcx, r15
0x180059e01  call    cs:__imp_UpdatePDCAndPDR
0x180059e08  nop     dword ptr [rax+rax+00h]
0x180059e0d  mov     esi, eax
0x180059e0f  test    eax, eax
0x180059e11  js      loc_180059F10
0x180059e17  mov     r13, [r13+0]
0x180059e1b  test    r13, r13
0x180059e1e  jz      short loc_180059E4B
0x180059e20  call    cs:__imp_GetLastError
0x180059e27  nop     dword ptr [rax+rax+00h]
0x180059e2c  mov     esi, eax
0x180059e2e  mov     rcx, r13; pv
0x180059e31  call    cs:__imp_CoTaskMemFree
0x180059e38  nop     dword ptr [rax+rax+00h]
0x180059e3d  mov     ecx, esi; dwErrCode
0x180059e3f  call    cs:__imp_SetLastError
0x180059e46  nop     dword ptr [rax+rax+00h]
0x180059e4b  mov     rdx, [rsp+0F8h+arg_0]
0x180059e53  mov     qword ptr [rdx], 0
0x180059e5a  mov     r8, [rsp+0F8h+arg_30]
0x180059e62  lea     rcx, [rsp+0F8h+var_B8]
0x180059e67  call    ?ConvertIStreamToData@CIppCSRHelper@PrintConfig@@SAJAEBV?$ComPtr@UIStream@@@WRL@Microsoft@@PEAPEAEPEAK@Z; PrintConfig::CIppCSRHelper::ConvertIStreamToData(Microsoft::WRL::ComPtr<IStream> const &,uchar * *,ulong *)
0x180059e6c  mov     esi, eax
0x180059e6e  test    eax, eax
0x180059e70  js      loc_18005A04F
0x180059e76  mov     rax, [rsp+0F8h+arg_10]
0x180059e7e  mov     r13, [rax]
0x180059e81  test    r13, r13
0x180059e84  jz      short loc_180059EB9
0x180059e86  call    cs:__imp_GetLastError
0x180059e8d  nop     dword ptr [rax+rax+00h]
0x180059e92  mov     esi, eax
0x180059e94  mov     rcx, r13; pv
0x180059e97  call    cs:__imp_CoTaskMemFree
0x180059e9e  nop     dword ptr [rax+rax+00h]
0x180059ea3  mov     ecx, esi; dwErrCode
0x180059ea5  call    cs:__imp_SetLastError
0x180059eac  nop     dword ptr [rax+rax+00h]
0x180059eb1  mov     rax, [rsp+0F8h+arg_10]
0x180059eb9  mov     qword ptr [rax], 0
0x180059ec0  mov     r8, [rsp+0F8h+arg_38]
0x180059ec8  mov     rdx, rax
0x180059ecb  lea     rcx, [rsp+0F8h+var_C0]
0x180059ed0  call    ?ConvertIStreamToData@CIppCSRHelper@PrintConfig@@SAJAEBV?$ComPtr@UIStream@@@WRL@Microsoft@@PEAPEAEPEAK@Z; PrintConfig::CIppCSRHelper::ConvertIStreamToData(Microsoft::WRL::ComPtr<IStream> const &,uchar * *,ulong *)
0x180059ed5  mov     esi, eax
0x180059ed7  test    eax, eax
0x180059ed9  js      loc_18005A096
0x180059edf  mov     rcx, r15
0x180059ee2  call    cs:__imp_UpdatePdcRegenerationRegKey
0x180059ee9  nop     dword ptr [rax+rax+00h]
0x180059eee  mov     rcx, [rsp+0F8h]; this
0x180059ef6  test    eax, eax
0x180059ef8  jns     short loc_180059F76
0x180059efa  mov     r9d, eax; char *
0x180059efd  lea     r8, aPrintscanPrint_17; "printscan\\print\\drivers\\usermode\\co"...
0x180059f04  mov     edx, 3Dh ; '='; void *
0x180059f09  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180059f0e  jmp     short loc_180059F76
0x180059f10  cmp     esi, 80004001h
0x180059f16  jnz     loc_18005A0E3
0x180059f1c  mov     rcx, r15
0x180059f1f  call    cs:__imp_UpdatePdcRegenerationRegKey
0x180059f26  nop     dword ptr [rax+rax+00h]
0x180059f2b  mov     rcx, [rsp+0F8h]; this
0x180059f33  test    eax, eax
0x180059f35  jns     short loc_180059F4B
0x180059f37  mov     r9d, eax; char *
0x180059f3a  lea     r8, aPrintscanPrint_17; "printscan\\print\\drivers\\usermode\\co"...
0x180059f41  mov     edx, 42h ; 'B'; void *
0x180059f46  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180059f4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180059f52  cmp     rcx, r14
0x180059f55  jz      short loc_180059F76
0x180059f57  test    byte ptr [rcx+44h], 4
0x180059f5b  jz      short loc_180059F76
0x180059f5d  mov     edx, 0Dh
0x180059f62  mov     r9, r15
0x180059f65  lea     r8, WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids
0x180059f6c  mov     rcx, [rcx+38h]
0x180059f70  call    WPP_SF_S
0x180059f75  nop
0x180059f76  mov     rcx, [rsp+0F8h+var_C0]
0x180059f7b  test    rcx, rcx
0x180059f7e  jz      short loc_180059F96
0x180059f80  mov     [rsp+0F8h+var_C0], 0
0x180059f89  mov     rax, [rcx]
0x180059f8c  mov     rax, [rax+10h]
0x180059f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f95  nop
0x180059f96  mov     rax, [rbx]
0x180059f99  mov     rcx, rbx
0x180059f9c  mov     rax, [rax+10h]
0x180059fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059fa5  nop
0x180059fa6  mov     rcx, qword ptr [rsp+0F8h+var_B8]
0x180059fab  test    rcx, rcx
0x180059fae  jz      short loc_180059FC6
0x180059fb0  mov     qword ptr [rsp+0F8h+var_B8], 0
0x180059fb9  mov     rax, [rcx]
0x180059fbc  mov     rax, [rax+10h]
0x180059fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059fc5  nop
0x180059fc6  mov     rax, [rdi]
0x180059fc9  mov     rcx, rdi
0x180059fcc  mov     rax, [rax+10h]
0x180059fd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059fd5  nop
0x180059fd6  jmp     short loc_18005A00A
0x180059fd8  lea     r14, WPP_GLOBAL_Control
0x180059fdf  mov     rcx, cs:WPP_GLOBAL_Control
0x180059fe6  cmp     rcx, r14
0x180059fe9  jz      short loc_18005A00A
0x180059feb  test    byte ptr [rcx+44h], 4
0x180059fef  jz      short loc_18005A00A
0x180059ff1  mov     edx, 10h
0x180059ff6  mov     r9, r15
0x180059ff9  lea     r8, WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids
0x18005a000  mov     rcx, [rcx+38h]
0x18005a004  call    WPP_SF_S
0x18005a009  nop
0x18005a00a  mov     eax, [rsp+0F8h+var_C8]
0x18005a00e  mov     rbx, [rsp+0F8h+arg_18]
0x18005a016  add     rsp, 0D0h
0x18005a01d  pop     r15
0x18005a01f  pop     r14
0x18005a021  pop     r13
0x18005a023  pop     rdi
0x18005a024  pop     rsi
0x18005a025  retn
0x18005a027  jmp     short loc_18005A00A
0x18005a029  jmp     short loc_18005A00A
0x18005a02b  jmp     short loc_18005A00A
0x18005a02d  jmp     short loc_18005A00A
0x18005a02f  lea     r8, aPrintscanPrint_17; "printscan\\print\\drivers\\usermode\\co"...
0x18005a036  lea     edx, [rdi+2Eh]; void *
0x18005a039  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18005a03f  lea     r8, aPrintscanPrint_17; "printscan\\print\\drivers\\usermode\\co"...
0x18005a046  lea     edx, [rbx+32h]; void *
0x18005a049  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18005a04f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a056  cmp     rcx, r14
0x18005a059  jz      short loc_18005A079
0x18005a05b  test    byte ptr [rcx+44h], 1
0x18005a05f  jz      short loc_18005A079
0x18005a061  mov     edx, 0Bh
0x18005a066  mov     r9d, eax
0x18005a069  lea     r8, WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids
0x18005a070  mov     rcx, [rcx+38h]
0x18005a074  call    WPP_SF_d
0x18005a079  mov     edx, esi; int
0x18005a07b  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x18005a080  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18005a085  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18005a08c  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x18005a091  call    _CxxThrowException_0
0x18005a096  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a09d  cmp     rcx, r14
0x18005a0a0  jz      short loc_18005A0C0
0x18005a0a2  test    byte ptr [rcx+44h], 1
0x18005a0a6  jz      short loc_18005A0C0
0x18005a0a8  mov     edx, 0Ch
0x18005a0ad  mov     r9d, eax
0x18005a0b0  lea     r8, WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids
0x18005a0b7  mov     rcx, [rcx+38h]
0x18005a0bb  call    WPP_SF_d
0x18005a0c0  mov     edx, esi; int
0x18005a0c2  lea     rcx, [rsp+0F8h+var_68]; this
0x18005a0ca  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18005a0cf  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18005a0d6  lea     rcx, [rsp+0F8h+var_68]; pExceptionObject
0x18005a0de  call    _CxxThrowException_0
0x18005a0e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a0ea  cmp     rcx, r14
0x18005a0ed  jz      short loc_18005A137
0x18005a0ef  test    byte ptr [rcx+44h], 4
0x18005a0f3  jz      short loc_18005A114
0x18005a0f5  mov     edx, 0Eh
0x18005a0fa  mov     r9, r15
0x18005a0fd  lea     r8, WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids
0x18005a104  mov     rcx, [rcx+38h]
0x18005a108  call    WPP_SF_S
0x18005a10d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a114  cmp     rcx, r14
0x18005a117  jz      short loc_18005A137
0x18005a119  test    byte ptr [rcx+44h], 1
0x18005a11d  jz      short loc_18005A137
0x18005a11f  mov     edx, 0Fh
0x18005a124  mov     r9d, esi
0x18005a127  lea     r8, WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids
0x18005a12e  mov     rcx, [rcx+38h]
0x18005a132  call    WPP_SF_d
0x18005a137  mov     edx, esi; int
0x18005a139  lea     rcx, [rsp+0F8h+var_48]; this
0x18005a141  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18005a146  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18005a14d  lea     rcx, [rsp+0F8h+var_48]; pExceptionObject
0x18005a155  call    _CxxThrowException_0
```
