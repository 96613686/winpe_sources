# FreePluginLibrary

- ea: `0x1400093c0`
- end: `0x140009570`
- name: `FreePluginLibrary`
- size: `432`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x140002a30`
- `0x14000796c`
- `0x140007a38`
- `0x140007ba4`
- `0x140007e1c`
- `0x140008cac`
- `0x140008f2c`
- `0x1400093c0`
- `0x14000b470`
- `0x14000edac`
- `0x14000f228`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009481`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009481`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000950a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000950a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009499`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009499`

## string_xrefs

- `0x1400094e6`: `PluginAction %s failed, plugin: %s, hr = 0x%08x`
- `0x14000941a`: `AgentActionActivity`

## pseudocode

```c
__int64 FreePluginLibrary()
{
  unsigned int v0; // ebx
  const unsigned __int16 *v1; // rbx
  __int64 v2; // rax
  __int64 (*ProcAddress)(void); // rbx
  signed int LastError; // eax
  int v5; // eax
  void *v6; // rdx
  unsigned __int16 *v8; // [rsp+28h] [rbp-E0h]
  _OWORD v9[2]; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v10[42]; // [rsp+68h] [rbp-A0h] BYREF

  v0 = 0;
  if ( g_hPluginCollection )
  {
    v1 = (const unsigned __int16 *)&SandboxAction::Plugin::uninit;
    if ( *((_QWORD *)&xmmword_1400208A0 + 1) > 7u )
      v1 = SandboxAction::Plugin::uninit;
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
      (__int64)v10,
      (__int64)"AgentActionActivity");
    v10[0] = &WaasMedic::TelemetryProvider::AgentActionActivity::`vftable';
    WaasMedic::TelemetryProvider::AgentActionActivity::StartActivity(
      (WaasMedic::TelemetryProvider::AgentActionActivity *)v10,
      &g_pszCVBuff,
      (const unsigned __int16 *)g_pszCapsuleName,
      &dword_1400158BC,
      v1);
    v2 = WaasMedic::ws2s(v9, &SandboxAction::Plugin::uninit);
    if ( *(_QWORD *)(v2 + 24) > 0xFu )
      v2 = *(_QWORD *)v2;
    ProcAddress = GetProcAddress(g_hPluginCollection, (LPCSTR)v2);
    std::string::~string(v9);
    if ( ProcAddress )
    {
      v5 = ProcAddress();
      v0 = v5;
      if ( v5 < 0 )
      {
        v9[0] = *(_OWORD *)&SandboxAction::Plugin::uninit;
        v9[1] = xmmword_1400208A0;
        LODWORD(v8) = v5;
        LogLevelW(2u, L"PluginAction %s failed, plugin: %s, hr = 0x%08x", v9, &dword_1400158BC, v8);
      }
    }
    else
    {
      LastError = GetLastError();
      v0 = LastError;
      if ( LastError > 0 )
        v0 = (unsigned __int16)LastError | 0x80070000;
    }
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
      v10,
      v0);
    if ( !FreeLibrary(g_hPluginCollection) )
      v0 = -2147312566;
    WaasMedic::SafeFree(g_pszCapsuleName, v6);
    g_pszCapsuleName = 0;
    v10[0] = &WaasMedic::TelemetryProvider::AgentActionActivity::`vftable';
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v10);
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)v10);
  }
  return v0;
}

```

## disassembly

```asm
0x1400093c0  mov     rax, rsp
0x1400093c3  push    rbp
0x1400093c4  lea     rbp, [rax-0C8h]
0x1400093cb  sub     rsp, 1C0h
0x1400093d2  mov     [rsp+1C0h+var_190], 0FFFFFFFFFFFFFFFEh
0x1400093db  mov     [rax+8], rbx
0x1400093df  mov     [rax+10h], rdi
0x1400093e3  mov     rax, cs:__security_cookie
0x1400093ea  xor     rax, rsp
0x1400093ed  mov     [rbp+0C0h+var_10], rax
0x1400093f4  xor     ebx, ebx
0x1400093f6  cmp     cs:?g_hPluginCollection@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hPluginCollection
0x1400093fd  jz      loc_14000954A
0x140009403  lea     rbx, ?uninit@Plugin@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const SandboxAction::Plugin::uninit
0x14000940a  cmp     qword ptr cs:xmmword_1400208A0+8, 7
0x140009412  cmova   rbx, qword ptr cs:?uninit@Plugin@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const SandboxAction::Plugin::uninit
0x14000941a  lea     rdx, aAgentactionact; "AgentActionActivity"
0x140009421  lea     rcx, [rsp+1C0h+var_160]
0x140009426  call    ??0?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14000942b  lea     rdi, ??_7AgentActionActivity@TelemetryProvider@WaasMedic@@6B@; const WaasMedic::TelemetryProvider::AgentActionActivity::`vftable'
0x140009432  mov     [rsp+1C0h+var_160], rdi
0x140009437  mov     [rsp+1C0h+var_1A0], rbx; unsigned __int16 *
0x14000943c  lea     r9, dword_1400158BC; unsigned __int16 *
0x140009443  mov     r8, cs:?g_pszCapsuleName@@3PEAGEA; unsigned __int16 *
0x14000944a  lea     rdx, ?g_pszCVBuff@@3PADA; char *
0x140009451  lea     rcx, [rsp+1C0h+var_160]; this
0x140009456  call    ?StartActivity@AgentActionActivity@TelemetryProvider@WaasMedic@@QEAAXPEBDPEBG11@Z; WaasMedic::TelemetryProvider::AgentActionActivity::StartActivity(char const *,ushort const *,ushort const *,ushort const *)
0x14000945b  nop
0x14000945c  lea     rdx, ?uninit@Plugin@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const SandboxAction::Plugin::uninit
0x140009463  lea     rcx, [rsp+1C0h+var_188+8]
0x140009468  call    ?ws2s@WaasMedic@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; WaasMedic::ws2s(std::wstring const &)
0x14000946d  cmp     qword ptr [rax+18h], 0Fh
0x140009472  jbe     short loc_140009477
0x140009474  mov     rax, [rax]
0x140009477  mov     rdx, rax; lpProcName
0x14000947a  mov     rcx, cs:?g_hPluginCollection@@3PEAUHINSTANCE__@@EA; hModule
0x140009481  call    cs:__imp_GetProcAddress
0x140009487  mov     rbx, rax
0x14000948a  lea     rcx, [rsp+1C0h+var_188+8]
0x14000948f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140009494  test    rbx, rbx
0x140009497  jnz     short loc_1400094B0
0x140009499  call    cs:__imp_GetLastError
0x14000949f  mov     ebx, eax
0x1400094a1  test    eax, eax
0x1400094a3  jle     short loc_1400094F7
0x1400094a5  movzx   ebx, ax
0x1400094a8  or      ebx, 80070000h
0x1400094ae  jmp     short loc_1400094F7
0x1400094b0  mov     rax, rbx
0x1400094b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400094b8  mov     ebx, eax
0x1400094ba  test    eax, eax
0x1400094bc  jns     short loc_1400094F7
0x1400094be  movaps  xmm0, cs:?uninit@Plugin@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const SandboxAction::Plugin::uninit
0x1400094c5  movaps  [rsp+1C0h+var_188+8], xmm0
0x1400094ca  movaps  xmm1, cs:xmmword_1400208A0
0x1400094d1  movaps  [rsp+1C0h+var_178+8], xmm1
0x1400094d6  mov     dword ptr [rsp+1C0h+var_1A0], eax
0x1400094da  lea     r9, dword_1400158BC
0x1400094e1  lea     r8, [rsp+1C0h+var_188+8]
0x1400094e6  lea     rdx, aPluginactionSF; "PluginAction %s failed, plugin: %s, hr "...
0x1400094ed  mov     ecx, 2; unsigned __int8
0x1400094f2  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1400094f7  mov     edx, ebx
0x1400094f9  lea     rcx, [rsp+1C0h+var_160]
0x1400094fe  call    ?Stop@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140009503  mov     rcx, cs:?g_hPluginCollection@@3PEAUHINSTANCE__@@EA; hLibModule
0x14000950a  call    cs:__imp_FreeLibrary
0x140009510  mov     ecx, 80029C4Ah
0x140009515  test    eax, eax
0x140009517  cmovz   ebx, ecx
0x14000951a  mov     rcx, cs:?g_pszCapsuleName@@3PEAGEA; this
0x140009521  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x140009526  mov     cs:?g_pszCapsuleName@@3PEAGEA, 0; ushort * g_pszCapsuleName
0x140009531  mov     [rsp+1C0h+var_160], rdi
0x140009536  lea     rcx, [rsp+1C0h+var_160]
0x14000953b  call    ?Destroy@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140009540  lea     rcx, [rsp+1C0h+var_160]
0x140009545  call    ??1?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x14000954a  mov     eax, ebx
0x14000954c  mov     rcx, [rbp+0C0h+var_10]
0x140009553  xor     rcx, rsp; StackCookie
0x140009556  call    __security_check_cookie
0x14000955b  lea     r11, [rsp+1C0h+var_s0]
0x140009563  mov     rbx, [r11+10h]
0x140009567  mov     rdi, [r11+18h]
0x14000956b  mov     rsp, r11
0x14000956e  pop     rbp
0x14000956f  retn
```
