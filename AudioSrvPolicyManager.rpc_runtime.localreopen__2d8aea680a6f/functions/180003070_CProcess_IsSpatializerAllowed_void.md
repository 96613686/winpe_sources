# CProcess::IsSpatializerAllowed(void)

- ea: `0x180003070`
- end: `0x180003179`
- name: `?IsSpatializerAllowed@CProcess@@UEAA_NXZ`
- size: `265`
- prototype: `bool __fastcall(CProcess *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001c74`
- `0x180003070`
- `0x180003480`
- `0x180031960`
- `0x18003a5fc`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180003155`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180003155`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800030a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800030a3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800030c0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800030c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall CProcess::IsSpatializerAllowed(CProcess *this)
{
  int v1; // eax
  bool v3; // bl
  __int64 v4; // [rsp+20h] [rbp-40h] BYREF
  __int64 v5; // [rsp+28h] [rbp-38h] BYREF
  HSTRING string; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v4 = 0;
  if ( WindowsCreateStringReference(L"Windows.Graphics.Holographic.HolographicDisplay", 0x2Fu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  if ( (int)RoGetActivationFactory(string, &GUID_e464b452_7eb3_434b_95d6_1339477e80c7, &v4) < 0 )
    goto LABEL_7;
  v5 = 0;
  v1 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v4 + 64LL))(v4, &v5);
  if ( v1 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xF61,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\application.cpp",
      (const char *)(unsigned int)v1,
      v4);
  if ( v5 )
  {
    v3 = (unsigned int)CWindowsPolicyManager::GetAccessibilityAudioMonoMixState(g_PolicyManager) == 0;
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v5);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v4);
    return v3;
  }
  else
  {
LABEL_7:
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    return 0;
  }
}

```

## disassembly

```asm
0x180003070  mov     [rsp-8+arg_0], rbx
0x180003075  push    rbp
0x180003076  mov     rbp, rsp
0x180003079  sub     rsp, 60h
0x18000307d  mov     rax, cs:__security_cookie
0x180003084  xor     rax, rsp
0x180003087  mov     [rbp+var_10], rax
0x18000308b  xor     ebx, ebx
0x18000308d  mov     [rbp+var_40], rbx
0x180003091  lea     r9, [rbp+string]; string
0x180003095  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180003099  lea     edx, [rbx+2Fh]; length
0x18000309c  lea     rcx, ?RuntimeClass_Windows_Graphics_Holographic_HolographicDisplay@@3QBGB; "Windows.Graphics.Holographic.Holographi"...
0x1800030a3  call    cs:__imp_WindowsCreateStringReference
0x1800030a9  test    eax, eax
0x1800030ab  js      loc_180003146
0x1800030b1  lea     r8, [rbp+var_40]
0x1800030b5  lea     rdx, _GUID_e464b452_7eb3_434b_95d6_1339477e80c7
0x1800030bc  mov     rcx, [rbp+string]
0x1800030c0  call    cs:__imp_RoGetActivationFactory
0x1800030c6  test    eax, eax
0x1800030c8  js      short loc_1800030F0
0x1800030ca  mov     [rbp+var_38], rbx
0x1800030ce  mov     rcx, [rbp+var_40]
0x1800030d2  mov     rax, [rcx]
0x1800030d5  lea     rdx, [rbp+var_38]
0x1800030d9  mov     rax, [rax+40h]
0x1800030dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030e2  mov     rcx, [rbp+8]; this
0x1800030e6  test    eax, eax
0x1800030e8  js      short loc_180003160
0x1800030ea  cmp     [rbp+var_38], rbx
0x1800030ee  jnz     short loc_18000311F
0x1800030f0  mov     rcx, [rbp+var_40]
0x1800030f4  test    rcx, rcx
0x1800030f7  jz      short loc_180003106
0x1800030f9  mov     rax, [rcx]
0x1800030fc  mov     rax, [rax+10h]
0x180003100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003105  nop
0x180003106  xor     al, al
0x180003108  mov     rcx, [rbp+var_10]
0x18000310c  xor     rcx, rsp; StackCookie
0x18000310f  call    __security_check_cookie
0x180003114  mov     rbx, [rsp+60h+arg_0]
0x180003119  add     rsp, 60h
0x18000311d  pop     rbp
0x18000311e  retn
0x18000311f  mov     rcx, cs:?g_PolicyManager@@3PEAVCWindowsPolicyManager@@EA; this
0x180003126  call    ?GetAccessibilityAudioMonoMixState@CWindowsPolicyManager@@UEAAHXZ; CWindowsPolicyManager::GetAccessibilityAudioMonoMixState(void)
0x18000312b  test    eax, eax
0x18000312d  setz    bl
0x180003130  lea     rcx, [rbp+var_38]
0x180003134  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180003139  lea     rcx, [rbp+var_40]
0x18000313d  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180003142  mov     al, bl
0x180003144  jmp     short loc_180003108
0x180003146  xor     r9d, r9d; lpArguments
0x180003149  xor     r8d, r8d; nNumberOfArguments
0x18000314c  lea     edx, [r9+1]; dwExceptionFlags
0x180003150  mov     ecx, 0C000000Dh; dwExceptionCode
0x180003155  call    cs:__imp_RaiseException
0x18000315b  jmp     loc_1800030B1
0x180003160  mov     r9d, eax; char *
0x180003163  lea     r8, aClientcoreMult_7; "clientcore\\multimedia\\audiocore\\serv"...
0x18000316a  mov     edx, 0F61h; void *
0x18000316f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180003174  jmp     loc_1800030EA
```
