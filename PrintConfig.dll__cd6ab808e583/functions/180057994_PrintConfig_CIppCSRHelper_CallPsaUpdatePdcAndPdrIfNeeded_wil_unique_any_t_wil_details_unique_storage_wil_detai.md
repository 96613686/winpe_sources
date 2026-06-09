# PrintConfig::CIppCSRHelper::CallPsaUpdatePdcAndPdrIfNeeded(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,int,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,int,ushort const *,ushort const *,ulong *,ulong *)

- ea: `0x180057994`
- end: `0x180057e2f`
- name: `?CallPsaUpdatePdcAndPdrIfNeeded@CIppCSRHelper@PrintConfig@@SAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@H0HPEBG1PEAK2@Z`
- size: `1179`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18001053c`
- `0x180042dac`

## callees

- `0x180004424`
- `0x18000f380`
- `0x18001878c`
- `0x180018bbc`
- `0x180018bfc`
- `0x1800507ac`
- `0x180057994`
- `0x180057e38`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180057b37`
- `KERNEL32!SetLastError` at `0x180057b8b`
- `KERNEL32!SetLastError` at `0x180057b37`
- `KERNEL32!SetLastError` at `0x180057b8b`
- `KERNEL32!GetLastError` at `0x180057b24`
- `KERNEL32!GetLastError` at `0x180057b78`
- `KERNEL32!GetLastError` at `0x180057b24`
- `KERNEL32!GetLastError` at `0x180057b78`
- `ole32!CoTaskMemFree` at `0x180057b2f`
- `ole32!CoTaskMemFree` at `0x180057b83`
- `ole32!CoTaskMemFree` at `0x180057b2f`
- `ole32!CoTaskMemFree` at `0x180057b83`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x180057a67`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x180057aa9`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x180057a67`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x180057aa9`
- `Print.PrintSupport.Source!UpdatePDCAndPDR` at `0x180057b0b`
- `Print.PrintSupport.Source!UpdatePDCAndPDR` at `0x180057b0b`
- `Print.PrintSupport.Source!IsPsaEnabledForContractAsCurrentUser` at `0x1800579fd`
- `Print.PrintSupport.Source!IsPsaEnabledForContractAsCurrentUser` at `0x1800579fd`
- `Print.PrintSupport.Source!UpdatePdcRegenerationRegKey` at `0x180057bc2`
- `Print.PrintSupport.Source!UpdatePdcRegenerationRegKey` at `0x180057bf9`
- `Print.PrintSupport.Source!UpdatePdcRegenerationRegKey` at `0x180057bc2`
- `Print.PrintSupport.Source!UpdatePdcRegenerationRegKey` at `0x180057bf9`

## string_xrefs

- `0x1800579eb`: `Windows.PrintSupportExtension`
- `0x180057a12`: `printscan\print\drivers\usermode\config\printconfig\ippcsrhelper.cpp`
- `0x180057bd7`: `printscan\print\drivers\usermode\config\printconfig\ippcsrhelper.cpp`
- `0x180057c0e`: `printscan\print\drivers\usermode\config\printconfig\ippcsrhelper.cpp`
- `0x180057d02`: `printscan\print\drivers\usermode\config\printconfig\ippcsrhelper.cpp`
- `0x180057d12`: `printscan\print\drivers\usermode\config\printconfig\ippcsrhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall PrintConfig::CIppCSRHelper::CallPsaUpdatePdcAndPdrIfNeeded(
        const BYTE **a1,
        UINT a2,
        const BYTE **a3,
        UINT a4,
        __int64 a5,
        __int64 a6,
        UINT *a7,
        _DWORD *a8)
{
  __int64 v12; // r15
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
  int v36; // [rsp+20h] [rbp-D8h]
  unsigned int v37; // [rsp+30h] [rbp-C8h]
  __int64 v38; // [rsp+38h] [rbp-C0h] BYREF
  int v39[2]; // [rsp+40h] [rbp-B8h] BYREF
  __int64 v40; // [rsp+48h] [rbp-B0h]
  IStream *v41; // [rsp+50h] [rbp-A8h]
  IStream *v42; // [rsp+58h] [rbp-A0h]
  const PrintCore::WindowsError *v43; // [rsp+60h] [rbp-98h] BYREF
  const hr_error *v44; // [rsp+68h] [rbp-90h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+70h] [rbp-88h] BYREF
  _BYTE v46[32]; // [rsp+90h] [rbp-68h] BYREF
  _BYTE v47[72]; // [rsp+B0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]
  char v50; // [rsp+108h] [rbp+10h] BYREF
  void **v51; // [rsp+110h] [rbp+18h]

  v51 = (void **)a3;
  v40 = -2;
  *a7 = a2;
  *a8 = 0;
  v37 = 0;
  v50 = 0;
  v12 = a6;
  v13 = IsPsaEnabledForContractAsCurrentUser(a6, L"Windows.PrintSupportExtension", &v50);
  if ( v13 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\ippcsrhelper.cpp",
      (const char *)(unsigned int)v13,
      v36);
  try
  {
    if ( v50 )
    {
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids, v12);
      }
      v14 = SHCreateMemStream(*a1, a2);
      v16 = v14;
      v41 = v14;
      if ( v14 )
        ((void (__fastcall *)(IStream *))v14->lpVtbl->AddRef)(v14);
      if ( !v16 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0x2E,
          (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\ippcsrhelper.cpp",
          v15);
      *(_QWORD *)v39 = 0;
      v17 = SHCreateMemStream(*a3, a4);
      v19 = v17;
      v42 = v17;
      if ( v17 )
        ((void (__fastcall *)(IStream *))v17->lpVtbl->AddRef)(v17);
      if ( !v19 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0x32,
          (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\ippcsrhelper.cpp",
          v18);
      v38 = 0;
      updated = UpdatePDCAndPDR(v12, v16, v19, a5);
      if ( updated < 0 )
      {
        if ( updated != -2147467263 )
        {
          v35 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
            {
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 14, WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids, v12);
              v35 = WPP_GLOBAL_Control;
            }
            if ( v35 != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control && (*((_BYTE *)v35 + 68) & 1) != 0 )
              WPP_SF_d(*((_QWORD *)v35 + 7), 15, WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids, (unsigned int)updated);
          }
          hr_error::hr_error((hr_error *)v47, updated);
          throw (hr_error *)v47;
        }
        v31 = UpdatePdcRegenerationRegKey(v12);
        if ( v31 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x42,
            (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\ippcsrhelper.cpp",
            (const char *)(unsigned int)v31,
            (int)v39);
        if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 13, WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids, v12);
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
        v23 = PrintConfig::CIppCSRHelper::ConvertIStreamToData(v39, a1, a7);
        v24 = v23;
        if ( v23 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              11,
              WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids,
              (unsigned int)v23);
          }
          hr_error::hr_error((hr_error *)pExceptionObject, v24);
          throw (hr_error *)pExceptionObject;
        }
        v25 = v51;
        v26 = *v51;
        if ( *v51 )
        {
          v27 = GetLastError();
          CoTaskMemFree(v26);
          SetLastError(v27);
          v25 = v51;
        }
        *v25 = 0;
        v28 = PrintConfig::CIppCSRHelper::ConvertIStreamToData(&v38, v25, a8);
        v29 = v28;
        if ( v28 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              12,
              WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids,
              (unsigned int)v28);
          }
          hr_error::hr_error((hr_error *)v46, v29);
          throw (hr_error *)v46;
        }
        v30 = UpdatePdcRegenerationRegKey(v12);
        if ( v30 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x3D,
            (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\ippcsrhelper.cpp",
            (const char *)(unsigned int)v30,
            (int)v39);
      }
      v32 = v38;
      if ( v38 )
      {
        v38 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      }
      ((void (__fastcall *)(IStream *))v19->lpVtbl->Release)(v19);
      v33 = *(_QWORD *)v39;
      if ( *(_QWORD *)v39 )
      {
        *(_QWORD *)v39 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      }
      ((void (__fastcall *)(IStream *))v16->lpVtbl->Release)(v16);
    }
    else if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 16, WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids, v12);
    }
  }
  catch ( std::bad_alloc )
  {
    return (unsigned int)-2147024882;
  }
  catch ( const hr_error *v44 )
  {
    return *((unsigned int *)v44 + 6);
  }
  catch ( const PrintCore::WindowsError *v43 )
  {
    return *((unsigned int *)v43 + 6);
  }
  catch ( std::exception )
  {
    return (unsigned int)-2147467259;
  }
  catch ( ... )
  {
    return (unsigned int)-2147418113;
  }
  return v37;
}

```

## disassembly

```asm
0x180057994  mov     r11, rsp
0x180057997  mov     [r11+18h], r8
0x18005799b  mov     [r11+8], rcx
0x18005799f  push    rsi
0x1800579a0  push    rdi
0x1800579a1  push    r13
0x1800579a3  push    r14
0x1800579a5  push    r15
0x1800579a7  sub     rsp, 0D0h
0x1800579ae  mov     [rsp+0F8h+var_B0], 0FFFFFFFFFFFFFFFEh
0x1800579b7  mov     [r11+20h], rbx
0x1800579bb  mov     esi, r9d
0x1800579be  mov     rbx, r8
0x1800579c1  mov     edi, edx
0x1800579c3  mov     r13, rcx
0x1800579c6  mov     rax, [rsp+0F8h+arg_30]
0x1800579ce  mov     [rax], edx
0x1800579d0  xor     r14d, r14d
0x1800579d3  mov     rax, [rsp+0F8h+arg_38]
0x1800579db  mov     [rax], r14d
0x1800579de  mov     [rsp+0F8h+var_C8], r14d
0x1800579e3  mov     [r11+10h], r14b
0x1800579e7  lea     r8, [r11+10h]
0x1800579eb  lea     rdx, aWindowsPrintsu_1; "Windows.PrintSupportExtension"
0x1800579f2  mov     r15, [rsp+0F8h+arg_28]
0x1800579fa  mov     rcx, r15
0x1800579fd  call    cs:__imp_IsPsaEnabledForContractAsCurrentUser
0x180057a03  mov     rcx, [rsp+0F8h]; this
0x180057a0b  test    eax, eax
0x180057a0d  jns     short loc_180057A22
0x180057a0f  mov     r9d, eax; char *
0x180057a12  lea     r8, aPrintscanPrint_17; "printscan\\print\\drivers\\usermode\\co"...
0x180057a19  lea     edx, [r14+29h]; void *
0x180057a1d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180057a22  cmp     [rsp+0F8h+arg_8], r14b
0x180057a2a  jz      loc_180057CAC
0x180057a30  lea     r14, WPP_GLOBAL_Control
0x180057a37  mov     rcx, cs:WPP_GLOBAL_Control
0x180057a3e  cmp     rcx, r14
0x180057a41  jz      short loc_180057A61
0x180057a43  test    byte ptr [rcx+44h], 4
0x180057a47  jz      short loc_180057A61
0x180057a49  mov     edx, 0Ah
0x180057a4e  mov     r9, r15
0x180057a51  lea     r8, WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids
0x180057a58  mov     rcx, [rcx+38h]
0x180057a5c  call    WPP_SF_S
0x180057a61  mov     edx, edi; cbInit
0x180057a63  mov     rcx, [r13+0]; pInit
0x180057a67  call    cs:__imp_SHCreateMemStream
0x180057a6d  mov     rdi, rax
0x180057a70  mov     [rsp+0F8h+var_A8], rax
0x180057a75  test    rax, rax
0x180057a78  jz      short loc_180057A8A
0x180057a7a  mov     rax, [rax]
0x180057a7d  mov     rcx, rdi
0x180057a80  mov     rax, [rax+8]
0x180057a84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057a89  nop
0x180057a8a  mov     rcx, [rsp+0F8h]; this
0x180057a92  test    rdi, rdi
0x180057a95  jz      loc_180057D02
0x180057a9b  mov     qword ptr [rsp+0F8h+var_B8], 0
0x180057aa4  mov     edx, esi; cbInit
0x180057aa6  mov     rcx, [rbx]; pInit
0x180057aa9  call    cs:__imp_SHCreateMemStream
0x180057aaf  mov     rbx, rax
0x180057ab2  mov     [rsp+0F8h+var_A0], rax
0x180057ab7  test    rax, rax
0x180057aba  jz      short loc_180057ACC
0x180057abc  mov     rax, [rax]
0x180057abf  mov     rcx, rbx
0x180057ac2  mov     rax, [rax+8]
0x180057ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057acb  nop
0x180057acc  mov     rcx, [rsp+0F8h]; this
0x180057ad4  test    rbx, rbx
0x180057ad7  jz      loc_180057D12
0x180057add  mov     [rsp+0F8h+var_C0], 0
0x180057ae6  lea     rax, [rsp+0F8h+var_C0]
0x180057aeb  mov     [rsp+0F8h+var_D0], rax
0x180057af0  lea     rax, [rsp+0F8h+var_B8]
0x180057af5  mov     qword ptr [rsp+0F8h+var_D8], rax; int
0x180057afa  mov     r9, [rsp+0F8h+arg_20]
0x180057b02  mov     r8, rbx
0x180057b05  mov     rdx, rdi
0x180057b08  mov     rcx, r15
0x180057b0b  call    cs:__imp_UpdatePDCAndPDR
0x180057b11  mov     esi, eax
0x180057b13  test    eax, eax
0x180057b15  js      loc_180057BEA
0x180057b1b  mov     r13, [r13+0]
0x180057b1f  test    r13, r13
0x180057b22  jz      short loc_180057B3D
0x180057b24  call    cs:__imp_GetLastError
0x180057b2a  mov     esi, eax
0x180057b2c  mov     rcx, r13; pv
0x180057b2f  call    cs:__imp_CoTaskMemFree
0x180057b35  mov     ecx, esi; dwErrCode
0x180057b37  call    cs:__imp_SetLastError
0x180057b3d  mov     rdx, [rsp+0F8h+arg_0]
0x180057b45  mov     qword ptr [rdx], 0
0x180057b4c  mov     r8, [rsp+0F8h+arg_30]
0x180057b54  lea     rcx, [rsp+0F8h+var_B8]
0x180057b59  call    ?ConvertIStreamToData@CIppCSRHelper@PrintConfig@@SAJAEBV?$ComPtr@UIStream@@@WRL@Microsoft@@PEAPEAEPEAK@Z; PrintConfig::CIppCSRHelper::ConvertIStreamToData(Microsoft::WRL::ComPtr<IStream> const &,uchar * *,ulong *)
0x180057b5e  mov     esi, eax
0x180057b60  test    eax, eax
0x180057b62  js      loc_180057D22
0x180057b68  mov     rax, [rsp+0F8h+arg_10]
0x180057b70  mov     r13, [rax]
0x180057b73  test    r13, r13
0x180057b76  jz      short loc_180057B99
0x180057b78  call    cs:__imp_GetLastError
0x180057b7e  mov     esi, eax
0x180057b80  mov     rcx, r13; pv
0x180057b83  call    cs:__imp_CoTaskMemFree
0x180057b89  mov     ecx, esi; dwErrCode
0x180057b8b  call    cs:__imp_SetLastError
0x180057b91  mov     rax, [rsp+0F8h+arg_10]
0x180057b99  mov     qword ptr [rax], 0
0x180057ba0  mov     r8, [rsp+0F8h+arg_38]
0x180057ba8  mov     rdx, rax
0x180057bab  lea     rcx, [rsp+0F8h+var_C0]
0x180057bb0  call    ?ConvertIStreamToData@CIppCSRHelper@PrintConfig@@SAJAEBV?$ComPtr@UIStream@@@WRL@Microsoft@@PEAPEAEPEAK@Z; PrintConfig::CIppCSRHelper::ConvertIStreamToData(Microsoft::WRL::ComPtr<IStream> const &,uchar * *,ulong *)
0x180057bb5  mov     esi, eax
0x180057bb7  test    eax, eax
0x180057bb9  js      loc_180057D69
0x180057bbf  mov     rcx, r15
0x180057bc2  call    cs:__imp_UpdatePdcRegenerationRegKey
0x180057bc8  mov     rcx, [rsp+0F8h]; this
0x180057bd0  test    eax, eax
0x180057bd2  jns     short loc_180057C4A
0x180057bd4  mov     r9d, eax; char *
0x180057bd7  lea     r8, aPrintscanPrint_17; "printscan\\print\\drivers\\usermode\\co"...
0x180057bde  mov     edx, 3Dh ; '='; void *
0x180057be3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180057be8  jmp     short loc_180057C4A
0x180057bea  cmp     esi, 80004001h
0x180057bf0  jnz     loc_180057DB6
0x180057bf6  mov     rcx, r15
0x180057bf9  call    cs:__imp_UpdatePdcRegenerationRegKey
0x180057bff  mov     rcx, [rsp+0F8h]; this
0x180057c07  test    eax, eax
0x180057c09  jns     short loc_180057C1F
0x180057c0b  mov     r9d, eax; char *
0x180057c0e  lea     r8, aPrintscanPrint_17; "printscan\\print\\drivers\\usermode\\co"...
0x180057c15  mov     edx, 42h ; 'B'; void *
0x180057c1a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180057c1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180057c26  cmp     rcx, r14
0x180057c29  jz      short loc_180057C4A
0x180057c2b  test    byte ptr [rcx+44h], 4
0x180057c2f  jz      short loc_180057C4A
0x180057c31  mov     edx, 0Dh
0x180057c36  mov     r9, r15
0x180057c39  lea     r8, WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids
0x180057c40  mov     rcx, [rcx+38h]
0x180057c44  call    WPP_SF_S
0x180057c49  nop
0x180057c4a  mov     rcx, [rsp+0F8h+var_C0]
0x180057c4f  test    rcx, rcx
0x180057c52  jz      short loc_180057C6A
0x180057c54  mov     [rsp+0F8h+var_C0], 0
0x180057c5d  mov     rax, [rcx]
0x180057c60  mov     rax, [rax+10h]
0x180057c64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057c69  nop
0x180057c6a  mov     rax, [rbx]
0x180057c6d  mov     rcx, rbx
0x180057c70  mov     rax, [rax+10h]
0x180057c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057c79  nop
0x180057c7a  mov     rcx, qword ptr [rsp+0F8h+var_B8]
0x180057c7f  test    rcx, rcx
0x180057c82  jz      short loc_180057C9A
0x180057c84  mov     qword ptr [rsp+0F8h+var_B8], 0
0x180057c8d  mov     rax, [rcx]
0x180057c90  mov     rax, [rax+10h]
0x180057c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057c99  nop
0x180057c9a  mov     rax, [rdi]
0x180057c9d  mov     rcx, rdi
0x180057ca0  mov     rax, [rax+10h]
0x180057ca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057ca9  nop
0x180057caa  jmp     short loc_180057CDE
0x180057cac  lea     r14, WPP_GLOBAL_Control
0x180057cb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180057cba  cmp     rcx, r14
0x180057cbd  jz      short loc_180057CDE
0x180057cbf  test    byte ptr [rcx+44h], 4
0x180057cc3  jz      short loc_180057CDE
0x180057cc5  mov     edx, 10h
0x180057cca  mov     r9, r15
0x180057ccd  lea     r8, WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids
0x180057cd4  mov     rcx, [rcx+38h]
0x180057cd8  call    WPP_SF_S
0x180057cdd  nop
0x180057cde  mov     eax, [rsp+0F8h+var_C8]
0x180057ce2  mov     rbx, [rsp+0F8h+arg_18]
0x180057cea  add     rsp, 0D0h
0x180057cf1  pop     r15
0x180057cf3  pop     r14
0x180057cf5  pop     r13
0x180057cf7  pop     rdi
0x180057cf8  pop     rsi
0x180057cf9  retn
0x180057cfa  jmp     short loc_180057CDE
0x180057cfc  jmp     short loc_180057CDE
0x180057cfe  jmp     short loc_180057CDE
0x180057d00  jmp     short loc_180057CDE
0x180057d02  lea     r8, aPrintscanPrint_17; "printscan\\print\\drivers\\usermode\\co"...
0x180057d09  lea     edx, [rdi+2Eh]; void *
0x180057d0c  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180057d12  lea     r8, aPrintscanPrint_17; "printscan\\print\\drivers\\usermode\\co"...
0x180057d19  lea     edx, [rbx+32h]; void *
0x180057d1c  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180057d22  mov     rcx, cs:WPP_GLOBAL_Control
0x180057d29  cmp     rcx, r14
0x180057d2c  jz      short loc_180057D4C
0x180057d2e  test    byte ptr [rcx+44h], 1
0x180057d32  jz      short loc_180057D4C
0x180057d34  mov     edx, 0Bh
0x180057d39  mov     r9d, eax
0x180057d3c  lea     r8, WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids
0x180057d43  mov     rcx, [rcx+38h]
0x180057d47  call    WPP_SF_d
0x180057d4c  mov     edx, esi; int
0x180057d4e  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x180057d53  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180057d58  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180057d5f  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x180057d64  call    _CxxThrowException_0
0x180057d69  mov     rcx, cs:WPP_GLOBAL_Control
0x180057d70  cmp     rcx, r14
0x180057d73  jz      short loc_180057D93
0x180057d75  test    byte ptr [rcx+44h], 1
0x180057d79  jz      short loc_180057D93
0x180057d7b  mov     edx, 0Ch
0x180057d80  mov     r9d, eax
0x180057d83  lea     r8, WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids
0x180057d8a  mov     rcx, [rcx+38h]
0x180057d8e  call    WPP_SF_d
0x180057d93  mov     edx, esi; int
0x180057d95  lea     rcx, [rsp+0F8h+var_68]; this
0x180057d9d  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180057da2  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180057da9  lea     rcx, [rsp+0F8h+var_68]; pExceptionObject
0x180057db1  call    _CxxThrowException_0
0x180057db6  mov     rcx, cs:WPP_GLOBAL_Control
0x180057dbd  cmp     rcx, r14
0x180057dc0  jz      short loc_180057E0A
0x180057dc2  test    byte ptr [rcx+44h], 4
0x180057dc6  jz      short loc_180057DE7
0x180057dc8  mov     edx, 0Eh
0x180057dcd  mov     r9, r15
0x180057dd0  lea     r8, WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids
0x180057dd7  mov     rcx, [rcx+38h]
0x180057ddb  call    WPP_SF_S
0x180057de0  mov     rcx, cs:WPP_GLOBAL_Control
0x180057de7  cmp     rcx, r14
0x180057dea  jz      short loc_180057E0A
0x180057dec  test    byte ptr [rcx+44h], 1
0x180057df0  jz      short loc_180057E0A
0x180057df2  mov     edx, 0Fh
0x180057df7  mov     r9d, esi
0x180057dfa  lea     r8, WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids
0x180057e01  mov     rcx, [rcx+38h]
0x180057e05  call    WPP_SF_d
0x180057e0a  mov     edx, esi; int
0x180057e0c  lea     rcx, [rsp+0F8h+var_48]; this
0x180057e14  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180057e19  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180057e20  lea     rcx, [rsp+0F8h+var_48]; pExceptionObject
0x180057e28  call    _CxxThrowException_0
```
