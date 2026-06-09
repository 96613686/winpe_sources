# WaasMedic::CWaasRemediation::EnumeratePlugins(int *,PluginNameAndOrder * *)

- ea: `0x1800128ac`
- end: `0x180012b4b`
- name: `?EnumeratePlugins@CWaasRemediation@WaasMedic@@AEAAJPEAHPEAPEAUPluginNameAndOrder@@@Z`
- size: `671`
- prototype: `__int64 __fastcall(WaasMedic::CWaasRemediation *__hidden this, int *, struct PluginNameAndOrder **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180018d3c`

## callees

- `0x1800050a0`
- `0x180009cd0`
- `0x18000f954`
- `0x18001039c`
- `0x1800128ac`
- `0x180014c30`
- `0x18002271c`
- `0x18002e56c`
- `0x18002e81c`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012941`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800129b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012941`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800129b8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012b13`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012b13`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012a89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012aef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012a89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012aef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012a97`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012afd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012a97`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012afd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800129d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800129d0`

## string_xrefs

- `0x180012909`: `Caller requested plugin enumeration`
- `0x180012a05`: `Failed to enumerate plugins. hr = 0x%08x`
- `0x180012ad3`: `PluginId is null for index = %d.`
- `0x180012ac7`: `GetPluginDefaultSettings failed with error: 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WaasMedic::CWaasRemediation::EnumeratePlugins(
        HMODULE *this,
        int *a2,
        struct PluginNameAndOrder **a3)
{
  unsigned int v6; // ebx
  __int64 *v7; // rdi
  __int64 v8; // rax
  FARPROC ProcAddress; // rbx
  __int64 *v10; // r9
  __int64 v11; // rax
  signed int LastError; // eax
  int v13; // eax
  unsigned int v14; // edi
  unsigned __int16 *v15; // r14
  int PluginDefaultSettings; // eax
  void *v17; // rsi
  int v18; // eax
  HANDLE ProcessHeap; // rax
  void *v20; // rdi
  HANDLE v21; // rax
  LPVOID lpMem; // [rsp+20h] [rbp-A9h] BYREF
  _BYTE v24[32]; // [rsp+28h] [rbp-A1h] BYREF
  _BYTE v25[40]; // [rsp+48h] [rbp-81h] BYREF
  _BYTE v26[8]; // [rsp+70h] [rbp-59h] BYREF
  _BYTE v27[40]; // [rsp+78h] [rbp-51h] BYREF
  void **v28; // [rsp+A0h] [rbp-29h]
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+B0h] [rbp-19h] BYREF

  WaasMedic::DefaultSettingsProvider::DefaultSettingsProvider((WaasMedic::DefaultSettingsProvider *)v26);
  if ( a3 )
  {
    if ( this[8] )
    {
      LogLevelW(4u, L"Caller requested plugin enumeration");
      v7 = &SandboxAction::PluginCollection::enumeratePlugins;
      v8 = WaasMedic::ws2s(v24, &SandboxAction::PluginCollection::enumeratePlugins);
      if ( *(_QWORD *)(v8 + 24) > 0xFu )
        v8 = *(_QWORD *)v8;
      ProcAddress = GetProcAddress(this[8], (LPCSTR)v8);
      std::string::~string(v24);
      if ( ProcAddress )
        goto LABEL_17;
      v10 = &SandboxAction::PluginCollection::enumeratePlugins_compat;
      if ( (unsigned __int64)qword_1800A59B8 > 7 )
        v10 = (__int64 *)SandboxAction::PluginCollection::enumeratePlugins_compat;
      if ( (unsigned __int64)qword_1800A5998 > 7 )
        v7 = (__int64 *)SandboxAction::PluginCollection::enumeratePlugins;
      LogLevelW(3u, L"Enumeration fallback from %s to %s", v7, v10);
      v11 = WaasMedic::ws2s(v25, &SandboxAction::PluginCollection::enumeratePlugins_compat);
      if ( *(_QWORD *)(v11 + 24) > 0xFu )
        v11 = *(_QWORD *)v11;
      ProcAddress = GetProcAddress(this[8], (LPCSTR)v11);
      std::string::~string(v25);
      if ( ProcAddress )
      {
LABEL_17:
        v13 = ((__int64 (__fastcall *)(int *, struct PluginNameAndOrder **))ProcAddress)(a2, a3);
        v6 = v13;
        if ( v13 >= 0 )
        {
          v14 = 0;
          if ( *a2 > 0 )
          {
            while ( 1 )
            {
              lpMem = 0;
              v15 = (unsigned __int16 *)((char *)*a3 + 516 * (int)v14);
              if ( !v15 )
                break;
              lpMem = 0;
              PluginDefaultSettings = WaasMedic::CWaasRemediation::GetPluginDefaultSettings(
                                        (WaasMedic::CWaasRemediation *)this,
                                        v15,
                                        (unsigned __int16 **)&lpMem);
              v6 = PluginDefaultSettings;
              if ( PluginDefaultSettings < 0 )
              {
                LogLevelW(
                  2u,
                  L"GetPluginDefaultSettings failed with error: 0x%08x",
                  (unsigned int)PluginDefaultSettings);
                goto LABEL_32;
              }
              v17 = lpMem;
              if ( lpMem )
              {
                v18 = WaasMedic::DefaultSettingsProvider::SetJsonDefaultSettings(
                        (WaasMedic::DefaultSettingsProvider *)v26,
                        (char *)v15,
                        (OLECHAR *)lpMem);
                v6 = v18;
                if ( v18 < 0 )
                {
                  LogLevelW(2u, L"Failed to set default setting for %s. hr = 0x%08x", v15, (unsigned int)v18);
                  goto LABEL_32;
                }
                v17 = lpMem;
              }
              if ( v17 )
              {
                ProcessHeap = GetProcessHeap();
                HeapFree(ProcessHeap, 0, v17);
              }
              if ( (int)++v14 >= *a2 )
                goto LABEL_34;
            }
            LogLevelW(2u, L"PluginId is null for index = %d.", v14);
LABEL_32:
            v20 = lpMem;
            if ( lpMem )
            {
              v21 = GetProcessHeap();
              HeapFree(v21, 0, v20);
            }
          }
        }
        else
        {
          LogLevelW(4u, L"Failed to enumerate plugins. hr = 0x%08x", (unsigned int)v13);
        }
      }
      else
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    else
    {
      v6 = -2147312566;
    }
  }
  else
  {
    v6 = -2147467261;
  }
LABEL_34:
  v28 = &WaasMedic::CLock::`vftable';
  DeleteCriticalSection(&CriticalSection);
  std::wstring::~wstring(v27);
  return v6;
}

```

## disassembly

```asm
0x1800128ac  mov     [rsp-8+arg_18], rbx
0x1800128b1  push    rbp
0x1800128b2  push    rsi
0x1800128b3  push    rdi
0x1800128b4  push    r12
0x1800128b6  push    r13
0x1800128b8  push    r14
0x1800128ba  push    r15
0x1800128bc  lea     rbp, [rsp-27h]
0x1800128c1  sub     rsp, 0F0h
0x1800128c8  mov     rax, cs:__security_cookie
0x1800128cf  xor     rax, rsp
0x1800128d2  mov     [rbp+57h+var_40], rax
0x1800128d6  mov     r13, r8
0x1800128d9  mov     r12, rdx
0x1800128dc  mov     r15, rcx
0x1800128df  lea     rcx, [rbp+57h+var_B0]; this
0x1800128e3  call    ??0DefaultSettingsProvider@WaasMedic@@QEAA@XZ; WaasMedic::DefaultSettingsProvider::DefaultSettingsProvider(void)
0x1800128e8  nop
0x1800128e9  test    r13, r13
0x1800128ec  jnz     short loc_1800128F8
0x1800128ee  mov     ebx, 80004003h
0x1800128f3  jmp     loc_180012B04
0x1800128f8  cmp     qword ptr [r15+40h], 0
0x1800128fd  jnz     short loc_180012909
0x1800128ff  mov     ebx, 80029C4Ah
0x180012904  jmp     loc_180012B04
0x180012909  lea     rdx, aCallerRequeste; "Caller requested plugin enumeration"
0x180012910  mov     esi, 4
0x180012915  mov     ecx, esi; unsigned __int8
0x180012917  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18001291c  lea     rdi, ?enumeratePlugins@PluginCollection@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const SandboxAction::PluginCollection::enumeratePlugins
0x180012923  mov     rdx, rdi
0x180012926  lea     rcx, [rsp+120h+var_F8]
0x18001292b  call    ?ws2s@WaasMedic@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; WaasMedic::ws2s(std::wstring const &)
0x180012930  cmp     qword ptr [rax+18h], 0Fh
0x180012935  jbe     short loc_18001293A
0x180012937  mov     rax, [rax]
0x18001293a  mov     rdx, rax; lpProcName
0x18001293d  mov     rcx, [r15+40h]; hModule
0x180012941  call    cs:__imp_GetProcAddress
0x180012947  mov     rbx, rax
0x18001294a  lea     rcx, [rsp+120h+var_F8]
0x18001294f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180012954  test    rbx, rbx
0x180012957  jnz     loc_1800129EE
0x18001295d  lea     r9, ?enumeratePlugins_compat@PluginCollection@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const SandboxAction::PluginCollection::enumeratePlugins_compat
0x180012964  cmp     cs:qword_1800A59B8, 7
0x18001296c  cmova   r9, cs:?enumeratePlugins_compat@PluginCollection@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const SandboxAction::PluginCollection::enumeratePlugins_compat
0x180012974  cmp     cs:qword_1800A5998, 7
0x18001297c  cmova   rdi, cs:?enumeratePlugins@PluginCollection@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const SandboxAction::PluginCollection::enumeratePlugins
0x180012984  mov     r8, rdi
0x180012987  lea     rdx, aEnumerationFal; "Enumeration fallback from %s to %s"
0x18001298e  lea     ecx, [rbx+3]; unsigned __int8
0x180012991  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180012996  lea     rdx, ?enumeratePlugins_compat@PluginCollection@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const SandboxAction::PluginCollection::enumeratePlugins_compat
0x18001299d  lea     rcx, [rsp+120h+var_D8]
0x1800129a2  call    ?ws2s@WaasMedic@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; WaasMedic::ws2s(std::wstring const &)
0x1800129a7  cmp     qword ptr [rax+18h], 0Fh
0x1800129ac  jbe     short loc_1800129B1
0x1800129ae  mov     rax, [rax]
0x1800129b1  mov     rdx, rax; lpProcName
0x1800129b4  mov     rcx, [r15+40h]; hModule
0x1800129b8  call    cs:__imp_GetProcAddress
0x1800129be  mov     rbx, rax
0x1800129c1  lea     rcx, [rsp+120h+var_D8]
0x1800129c6  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800129cb  test    rbx, rbx
0x1800129ce  jnz     short loc_1800129EE
0x1800129d0  call    cs:__imp_GetLastError
0x1800129d6  mov     ebx, eax
0x1800129d8  test    eax, eax
0x1800129da  jle     loc_180012B04
0x1800129e0  movzx   ebx, ax
0x1800129e3  or      ebx, 80070000h
0x1800129e9  jmp     loc_180012B04
0x1800129ee  mov     rdx, r13
0x1800129f1  mov     rcx, r12
0x1800129f4  mov     rax, rbx
0x1800129f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129fc  mov     ebx, eax
0x1800129fe  test    eax, eax
0x180012a00  jns     short loc_180012A18
0x180012a02  mov     r8d, eax
0x180012a05  lea     rdx, aFailedToEnumer_0; "Failed to enumerate plugins. hr = 0x%08"...
0x180012a0c  mov     ecx, esi; unsigned __int8
0x180012a0e  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180012a13  jmp     loc_180012B04
0x180012a18  xor     edi, edi
0x180012a1a  cmp     [r12], edi
0x180012a1e  jle     loc_180012B04
0x180012a24  mov     [rsp+120h+lpMem], 0
0x180012a2d  movsxd  rax, edi
0x180012a30  imul    r14, rax, 204h
0x180012a37  add     r14, [r13+0]
0x180012a3b  jz      loc_180012AD0
0x180012a41  mov     [rsp+120h+lpMem], 0
0x180012a4a  lea     r8, [rsp+120h+lpMem]; unsigned __int16 **
0x180012a4f  mov     rdx, r14; unsigned __int16 *
0x180012a52  mov     rcx, r15; this
0x180012a55  call    ?GetPluginDefaultSettings@CWaasRemediation@WaasMedic@@AEAAJPEBGPEAPEAG@Z; WaasMedic::CWaasRemediation::GetPluginDefaultSettings(ushort const *,ushort * *)
0x180012a5a  mov     ebx, eax
0x180012a5c  test    eax, eax
0x180012a5e  js      short loc_180012AC4
0x180012a60  mov     rsi, [rsp+120h+lpMem]
0x180012a65  test    rsi, rsi
0x180012a68  jz      short loc_180012A84
0x180012a6a  mov     r8, rsi; psz
0x180012a6d  mov     rdx, r14; char *
0x180012a70  lea     rcx, [rbp+57h+var_B0]; this
0x180012a74  call    ?SetJsonDefaultSettings@DefaultSettingsProvider@WaasMedic@@QEAAJPEBG0@Z; WaasMedic::DefaultSettingsProvider::SetJsonDefaultSettings(ushort const *,ushort const *)
0x180012a79  mov     ebx, eax
0x180012a7b  test    eax, eax
0x180012a7d  js      short loc_180012AAB
0x180012a7f  mov     rsi, [rsp+120h+lpMem]
0x180012a84  test    rsi, rsi
0x180012a87  jz      short loc_180012A9D
0x180012a89  call    cs:__imp_GetProcessHeap
0x180012a8f  mov     rcx, rax; hHeap
0x180012a92  mov     r8, rsi; lpMem
0x180012a95  xor     edx, edx; dwFlags
0x180012a97  call    cs:__imp_HeapFree
0x180012a9d  inc     edi
0x180012a9f  cmp     edi, [r12]
0x180012aa3  jl      loc_180012A24
0x180012aa9  jmp     short loc_180012B04
0x180012aab  mov     r9d, eax
0x180012aae  mov     r8, r14
0x180012ab1  lea     rdx, aFailedToSetDef_0; "Failed to set default setting for %s. h"...
0x180012ab8  mov     ecx, 2; unsigned __int8
0x180012abd  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180012ac2  jmp     short loc_180012AE5
0x180012ac4  mov     r8d, eax
0x180012ac7  lea     rdx, aGetplugindefau_0; "GetPluginDefaultSettings failed with er"...
0x180012ace  jmp     short loc_180012ADA
0x180012ad0  mov     r8d, edi
0x180012ad3  lea     rdx, aPluginidIsNull; "PluginId is null for index = %d."
0x180012ada  mov     ecx, 2; unsigned __int8
0x180012adf  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180012ae4  nop
0x180012ae5  mov     rdi, [rsp+120h+lpMem]
0x180012aea  test    rdi, rdi
0x180012aed  jz      short loc_180012B04
0x180012aef  call    cs:__imp_GetProcessHeap
0x180012af5  mov     r8, rdi; lpMem
0x180012af8  xor     edx, edx; dwFlags
0x180012afa  mov     rcx, rax; hHeap
0x180012afd  call    cs:__imp_HeapFree
0x180012b03  nop
0x180012b04  lea     rax, ??_7CLock@WaasMedic@@6B@; const WaasMedic::CLock::`vftable'
0x180012b0b  mov     [rbp+57h+var_80], rax
0x180012b0f  lea     rcx, [rbp+57h+CriticalSection]; lpCriticalSection
0x180012b13  call    cs:__imp_DeleteCriticalSection
0x180012b19  lea     rcx, [rbp+57h+var_A8]; void *
0x180012b1d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012b22  mov     eax, ebx
0x180012b24  mov     rcx, [rbp+57h+var_40]
0x180012b28  xor     rcx, rsp; StackCookie
0x180012b2b  call    __security_check_cookie
0x180012b30  mov     rbx, [rsp+120h+arg_18]
0x180012b38  add     rsp, 0F0h
0x180012b3f  pop     r15
0x180012b41  pop     r14
0x180012b43  pop     r13
0x180012b45  pop     r12
0x180012b47  pop     rdi
0x180012b48  pop     rsi
0x180012b49  pop     rbp
0x180012b4a  retn
```
