# CommandImpl::ProcessCliCommand(wchar_t *)

- ea: `0x180048b08`
- end: `0x180048ce7`
- name: `?ProcessCliCommand@CommandImpl@@SAJPEA_W@Z`
- size: `479`
- prototype: `__int64 __fastcall(wchar_t *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180036290`

## callees

- `0x180007630`
- `0x18002e758`
- `0x180034a30`
- `0x180048b08`
- `0x180048d58`
- `0x18004aaf8`
- `0x180056500`
- `0x180056524`
- `0x18005c5e0`
- `0x18005c660`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180048b6b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180048b6b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180048c86`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180048c86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048c6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048c6b`

## string_xrefs

- `0x180048cd4`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x180048b95`: `UsoClientImpl.CommandLine`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CommandImpl::ProcessCliCommand(wchar_t *a1)
{
  const char *v2; // r9
  __int64 result; // rax
  HRESULT v4; // eax
  uus::Session *v5; // rax
  uus::Session *v6; // rbx
  __int128 v7; // xmm0
  __int64 v8; // rcx
  unsigned int v9; // edi
  void *v10; // rcx
  const struct wil::FailureInfo *v11; // rdx
  int v12; // [rsp+20h] [rbp-118h]
  _BYTE v13[16]; // [rsp+30h] [rbp-108h] BYREF
  _BYTE v14[160]; // [rsp+40h] [rbp-F8h] BYREF
  _OWORD v15[4]; // [rsp+E0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  try
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_UpdateCli>::__private_IsEnabled() )
    {
      if ( wil::details::g_pfnTelemetryCallback
        && (char *)wil::details::g_pfnTelemetryCallback != (char *)ClientTelemetry::FallbackTelemetryCallback )
      {
        memset(v14, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v14, v11);
      }
      wil::details::g_pfnTelemetryCallback = (__int64 (__fastcall *)(_QWORD, _QWORD))ClientTelemetry::FallbackTelemetryCallback;
      v4 = CoInitializeEx(0, 0);
      if ( v4 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x1284,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
          (const char *)(unsigned int)v4,
          v12);
      v5 = (uus::Session *)operator new(0x10u);
      v6 = uus::Session::Session(v5, L"UsoClientImpl.CommandLine");
      memset(v15, 0, sizeof(v15));
      v7 = 0;
      v8 = *((_QWORD *)v6 + 1);
      if ( v8 )
        v7 = *(_OWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v8 + 80LL))(v8, v13);
      *((_QWORD *)&v15[0] + 1) = 0;
      *(_QWORD *)&v15[0] = &CommandImpl::`vftable';
      *(_QWORD *)&v15[1] = 0;
      *(_OWORD *)((char *)&v15[1] + 8) = v7;
      BYTE8(v15[2]) = 0;
      v15[3] = 0;
      v9 = CommandImpl::RunCommand((CommandImpl *)v15, a1);
      if ( *(_QWORD *)&v15[1] )
        (***(void (__fastcall ****)(_QWORD, __int64))&v15[1])(*(_QWORD *)&v15[1], 1);
      v10 = (void *)*((_QWORD *)&v15[0] + 1);
      *((_QWORD *)&v15[0] + 1) = 0;
      if ( v10 )
        LocalFree(v10);
      (**(void (__fastcall ***)(uus::Session *, __int64))v6)(v6, 1);
      CoUninitialize();
      result = v9;
    }
    else
    {
      result = 2147500033LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1E,
                           (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\lib\\CommandImpl.cpp",
                           v2);
  }
  return result;
}

```

## disassembly

```asm
0x180048b08  mov     [rsp+arg_8], rbx
0x180048b0d  push    rdi
0x180048b0e  sub     rsp, 130h
0x180048b15  mov     rax, cs:__security_cookie
0x180048b1c  xor     rax, rsp
0x180048b1f  mov     [rsp+138h+var_18], rax
0x180048b27  mov     rdi, rcx
0x180048b2a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Calliope_UpdateCli@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_UpdateCli@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_UpdateCli> `wil::Feature<__WilFeatureTraits_Feature_Calliope_UpdateCli>::GetImpl(void)'::`2'::impl
0x180048b31  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_UpdateCli@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_UpdateCli>::__private_IsEnabled(void)
0x180048b36  test    al, al
0x180048b38  jnz     short loc_180048B44
0x180048b3a  mov     eax, 80004001h
0x180048b3f  jmp     loc_180048C94
0x180048b44  mov     rcx, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180048b4b  lea     rax, ?FallbackTelemetryCallback@ClientTelemetry@@SAX_NAEBUFailureInfo@wil@@@Z; ClientTelemetry::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x180048b52  test    rcx, rcx
0x180048b55  jz      short loc_180048B60
0x180048b57  cmp     rcx, rax
0x180048b5a  jnz     loc_180048CB5
0x180048b60  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rax
0x180048b67  xor     edx, edx; dwCoInit
0x180048b69  xor     ecx, ecx; pvReserved
0x180048b6b  call    cs:__imp_CoInitializeEx
0x180048b71  mov     rcx, [rsp+138h]; this
0x180048b79  test    eax, eax
0x180048b7b  js      loc_180048CD1
0x180048b81  mov     [rsp+138h+var_118], 1
0x180048b86  mov     ecx, 10h; Size
0x180048b8b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180048b90  mov     [rsp+138h+var_110], rax
0x180048b95  lea     rdx, aUsoclientimplC; "UsoClientImpl.CommandLine"
0x180048b9c  mov     rcx, rax; this
0x180048b9f  call    ??0Session@uus@@QEAA@PEB_W@Z; uus::Session::Session(wchar_t const *)
0x180048ba4  mov     rbx, rax
0x180048ba7  mov     [rsp+138h+var_110], rax
0x180048bac  xor     edx, edx; Val
0x180048bae  lea     r8d, [rdx+40h]; Size
0x180048bb2  lea     rcx, [rsp+138h+var_58]; void *
0x180048bba  call    memset
0x180048bbf  xorps   xmm0, xmm0
0x180048bc2  mov     rcx, [rbx+8]
0x180048bc6  test    rcx, rcx
0x180048bc9  jz      short loc_180048BDF
0x180048bcb  mov     rax, [rcx]
0x180048bce  lea     rdx, [rsp+138h+var_108]
0x180048bd3  mov     rax, [rax+50h]
0x180048bd7  call    _guard_dispatch_icall
0x180048bdc  movups  xmm0, xmmword ptr [rax]
0x180048bdf  mov     [rsp+138h+hMem], 0
0x180048beb  lea     rax, ??_7CommandImpl@@6B@; const CommandImpl::`vftable'
0x180048bf2  mov     [rsp+138h+var_58], rax
0x180048bfa  mov     [rsp+138h+var_48], 0
0x180048c06  movdqu  [rsp+138h+var_40], xmm0
0x180048c0f  mov     [rsp+138h+var_30], 0
0x180048c17  xorps   xmm0, xmm0
0x180048c1a  movdqa  [rsp+138h+var_28], xmm0
0x180048c23  mov     rdx, rdi; lpCmdLine
0x180048c26  lea     rcx, [rsp+138h+var_58]; this
0x180048c2e  call    ?RunCommand@CommandImpl@@AEAAJPEB_W@Z; CommandImpl::RunCommand(wchar_t const *)
0x180048c33  mov     edi, eax
0x180048c35  mov     rcx, [rsp+138h+var_48]
0x180048c3d  test    rcx, rcx
0x180048c40  jz      short loc_180048C52
0x180048c42  mov     rdx, [rcx]
0x180048c45  mov     rax, [rdx]
0x180048c48  mov     edx, 1
0x180048c4d  call    _guard_dispatch_icall
0x180048c52  mov     rcx, [rsp+138h+hMem]; hMem
0x180048c5a  mov     [rsp+138h+hMem], 0
0x180048c66  test    rcx, rcx
0x180048c69  jz      short loc_180048C72
0x180048c6b  call    cs:__imp_LocalFree
0x180048c71  nop
0x180048c72  mov     rax, [rbx]
0x180048c75  mov     edx, 1
0x180048c7a  mov     rcx, rbx
0x180048c7d  mov     rax, [rax]
0x180048c80  call    _guard_dispatch_icall
0x180048c85  nop
0x180048c86  call    cs:__imp_CoUninitialize
0x180048c8c  mov     eax, edi
0x180048c8e  jmp     short loc_180048C94
0x180048c90  mov     eax, dword ptr [rsp+138h+var_110]
0x180048c94  mov     rcx, [rsp+138h+var_18]
0x180048c9c  xor     rcx, rsp; StackCookie
0x180048c9f  call    __security_check_cookie
0x180048ca4  mov     rbx, [rsp+138h+arg_8]
0x180048cac  add     rsp, 130h
0x180048cb3  pop     rdi
0x180048cb4  retn
0x180048cb5  xor     edx, edx; Val
0x180048cb7  mov     r8d, 98h; Size
0x180048cbd  lea     rcx, [rsp+138h+var_F8]; void *
0x180048cc2  call    memset
0x180048cc7  lea     rcx, [rsp+138h+var_F8]; this
0x180048ccc  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180048cd1  mov     r9d, eax; char *
0x180048cd4  lea     r8, aCW1SPackagesMi_2; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180048cdb  mov     edx, 1284h; void *
0x180048ce0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
