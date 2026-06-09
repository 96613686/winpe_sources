# ExecuteAction(ushort const *,ushort const *,uchar *)

- ea: `0x140007f3c`
- end: `0x140008276`
- name: `?ExecuteAction@@YAJPEBG0PEAE@Z`
- size: `826`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `16`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x140009580`
- `0x140009900`

## callees

- `0x140002a30`
- `0x140004290`
- `0x140004670`
- `0x14000644c`
- `0x14000796c`
- `0x140007a38`
- `0x140007ba4`
- `0x140007e1c`
- `0x140007f3c`
- `0x140008c20`
- `0x140008cac`
- `0x140008f2c`
- `0x14000b470`
- `0x14000edac`
- `0x140012014`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000804b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000804b`

## string_xrefs

- `0x14000819d`: `Plugin_IsApplicable`
- `0x140007fc0`: `AgentActionActivity`

## pseudocode

```c
__int64 __fastcall ExecuteAction(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned __int8 *a3)
{
  const unsigned __int16 *v5; // rbx
  unsigned int v6; // ebx
  __int64 v7; // r8
  __int64 v8; // rax
  FARPROC ProcAddress; // rdi
  int LastErrorMsg; // eax
  char **v11; // rcx
  const unsigned __int16 *v12; // rax
  signed __int64 v13; // rcx
  int v14; // r8d
  int v15; // edx
  int v16; // eax
  __int64 v17; // rdx
  unsigned __int64 v18; // r9
  __int64 *v19; // rdx
  const unsigned __int16 *v20; // rax
  signed __int64 v21; // rdx
  int v22; // r9d
  int v23; // r8d
  __int64 *v24; // rcx
  const unsigned __int16 *v25; // rax
  signed __int64 v26; // rcx
  int v27; // r8d
  int v28; // edx
  __int64 *v29; // rax
  signed __int64 v30; // rax
  int v31; // r8d
  int v32; // edx
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v36[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v37; // [rsp+38h] [rbp-C8h]
  _OWORD v38[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v39[32]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v40[42]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  v37 = -2;
  v5 = a1;
  LogLevelW(4u, L"Caller request %s method for %s", a1, a2);
  if ( g_hPluginCollection )
  {
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
      v40,
      "AgentActionActivity");
    v40[0] = &WaasMedic::TelemetryProvider::AgentActionActivity::`vftable';
    WaasMedic::TelemetryProvider::AgentActionActivity::StartActivity(
      (WaasMedic::TelemetryProvider::AgentActionActivity *)v40,
      &g_pszCVBuff,
      (const unsigned __int16 *)g_pszCapsuleName,
      a2,
      v5);
    memset(v38, 0, sizeof(v38));
    v7 = -1;
    do
      ++v7;
    while ( v5[v7] );
    std::wstring::_Construct<1,unsigned short const *>(v38, v5);
    v8 = WaasMedic::ws2s(v39, v38);
    if ( *(_QWORD *)(v8 + 24) > 0xFu )
      v8 = *(_QWORD *)v8;
    ProcAddress = GetProcAddress(g_hPluginCollection, (LPCSTR)v8);
    std::string::~string(v39);
    std::wstring::~wstring(v38);
    if ( !ProcAddress )
    {
      LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                       retaddr,
                       (void *)0x31,
                       (unsigned int)"onecore\\enduser\\waasmedic\\sandbox\\server\\worker.cpp",
                       "GetProcAddress failed to find action: %ws",
                       (const char *)v5);
LABEL_27:
      v6 = LastErrorMsg;
      goto LABEL_48;
    }
    v11 = &SandboxAction::Plugin::init;
    if ( (unsigned __int64)qword_1400208C8 > 7 )
      v11 = (char **)SandboxAction::Plugin::init;
    v12 = v5;
    v13 = (char *)v11 - (char *)v5;
    do
    {
      v14 = *(const unsigned __int16 *)((char *)v12 + v13);
      v15 = *v12 - v14;
      if ( v15 )
        break;
      ++v12;
    }
    while ( v14 );
    if ( v15 )
    {
      v19 = &SandboxAction::Plugin::performAction;
      if ( (unsigned __int64)qword_140020828 > 7 )
        v19 = (__int64 *)SandboxAction::Plugin::performAction;
      v20 = v5;
      v21 = (char *)v19 - (char *)v5;
      do
      {
        v22 = *(const unsigned __int16 *)((char *)v20 + v21);
        v23 = *v20 - v22;
        if ( v23 )
          break;
        ++v20;
      }
      while ( v22 );
      if ( v23 )
      {
        v24 = &SandboxAction::Plugin::detectCondition;
        if ( (unsigned __int64)qword_140020928 > 7 )
          v24 = (__int64 *)SandboxAction::Plugin::detectCondition;
        v25 = v5;
        v26 = (char *)v24 - (char *)v5;
        do
        {
          v27 = *(const unsigned __int16 *)((char *)v25 + v26);
          v28 = *v25 - v27;
          if ( v28 )
            break;
          ++v25;
        }
        while ( v27 );
        if ( !v28 || !wcscmp_0(v5, L"Plugin_IsApplicable") )
        {
          v36[0] = 0;
          v16 = ((__int64 (__fastcall *)(const unsigned __int16 *, unsigned __int8 *))ProcAddress)(a2, v36);
          v6 = v16;
          if ( v16 < 0 )
          {
            v17 = 67;
            goto LABEL_17;
          }
          *a3 = v36[0];
        }
        else
        {
          v29 = &SandboxAction::PluginCollection::setCorrelationVector;
          if ( (unsigned __int64)qword_140020848 > 7 )
            v29 = (__int64 *)SandboxAction::PluginCollection::setCorrelationVector;
          v30 = (char *)v29 - (char *)v5;
          do
          {
            v31 = *(const unsigned __int16 *)((char *)v5 + v30);
            v32 = *v5 - v31;
            if ( v32 )
              break;
            ++v5;
          }
          while ( v31 );
          if ( !v32 )
          {
            v16 = ((__int64 (__fastcall *)(char *))ProcAddress)(&g_pszCVBuff);
            v6 = v16;
            if ( v16 < 0 )
            {
              v17 = 74;
              goto LABEL_17;
            }
          }
        }
      }
      else
      {
        v6 = ((__int64 (__fastcall *)(const unsigned __int16 *))ProcAddress)(a2);
        if ( (v6 & 0x80000000) != 0 )
        {
          LastErrorMsg = -2147023673;
          if ( v6 == -2147023673 )
            goto LABEL_27;
          v18 = v6;
          v17 = 59;
LABEL_18:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v17,
            (unsigned int)"onecore\\enduser\\waasmedic\\sandbox\\server\\worker.cpp",
            (const char *)v18,
            v35);
LABEL_48:
          v40[0] = &WaasMedic::TelemetryProvider::AgentActionActivity::`vftable';
          wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v40);
          wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v40);
          return v6;
        }
      }
    }
    else
    {
      v16 = ProcAddress();
      v6 = v16;
      if ( v16 < 0 )
      {
        v17 = 54;
LABEL_17:
        v18 = (unsigned int)v16;
        goto LABEL_18;
      }
    }
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
      v40,
      0);
    v6 = 0;
    goto LABEL_48;
  }
  v6 = -2147312566;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2A,
    (unsigned int)"onecore\\enduser\\waasmedic\\sandbox\\server\\worker.cpp",
    (const char *)0x80029C4ALL,
    v34);
  return v6;
}

```

## disassembly

```asm
0x140007f3c  push    rbp
0x140007f3e  push    rbx
0x140007f3f  push    rsi
0x140007f40  push    rdi
0x140007f41  push    r12
0x140007f43  push    r14
0x140007f45  push    r15
0x140007f47  lea     rbp, [rsp-0E0h]
0x140007f4f  sub     rsp, 1E0h
0x140007f56  mov     [rsp+210h+var_1D8], 0FFFFFFFFFFFFFFFEh
0x140007f5f  mov     rax, cs:__security_cookie
0x140007f66  xor     rax, rsp
0x140007f69  mov     [rbp+110h+var_40], rax
0x140007f70  mov     r14, r8
0x140007f73  mov     rsi, rdx
0x140007f76  mov     rbx, rcx
0x140007f79  mov     r9, rdx
0x140007f7c  mov     r8, rcx
0x140007f7f  lea     rdx, aCallerRequestS; "Caller request %s method for %s"
0x140007f86  mov     ecx, 4; unsigned __int8
0x140007f8b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x140007f90  xor     r15d, r15d
0x140007f93  cmp     cs:?g_hPluginCollection@@3PEAUHINSTANCE__@@EA, r15; HINSTANCE__ * g_hPluginCollection
0x140007f9a  jnz     short loc_140007FC0
0x140007f9c  mov     rcx, [rbp+118h]; this
0x140007fa3  mov     ebx, 80029C4Ah
0x140007fa8  mov     r9d, ebx; char *
0x140007fab  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\sandbox\\s"...
0x140007fb2  lea     edx, [r15+2Ah]; void *
0x140007fb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007fbb  jmp     loc_140008253
0x140007fc0  lea     rdx, aAgentactionact; "AgentActionActivity"
0x140007fc7  lea     rcx, [rbp+110h+var_190]
0x140007fcb  call    ??0?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140007fd0  lea     r12, ??_7AgentActionActivity@TelemetryProvider@WaasMedic@@6B@; const WaasMedic::TelemetryProvider::AgentActionActivity::`vftable'
0x140007fd7  mov     [rbp+110h+var_190], r12
0x140007fdb  mov     qword ptr [rsp+210h+var_1F0], rbx; int
0x140007fe0  mov     r9, rsi; unsigned __int16 *
0x140007fe3  mov     r8, cs:?g_pszCapsuleName@@3PEAGEA; unsigned __int16 *
0x140007fea  lea     rdx, ?g_pszCVBuff@@3PADA; char *
0x140007ff1  lea     rcx, [rbp+110h+var_190]; this
0x140007ff5  call    ?StartActivity@AgentActionActivity@TelemetryProvider@WaasMedic@@QEAAXPEBDPEBG11@Z; WaasMedic::TelemetryProvider::AgentActionActivity::StartActivity(char const *,ushort const *,ushort const *,ushort const *)
0x140007ffa  nop
0x140007ffb  xorps   xmm0, xmm0
0x140007ffe  movups  [rsp+210h+var_1D0], xmm0
0x140008003  xorps   xmm1, xmm1
0x140008006  movdqu  [rsp+210h+var_1C0], xmm1
0x14000800c  or      r8, 0FFFFFFFFFFFFFFFFh
0x140008010  inc     r8
0x140008013  cmp     [rbx+r8*2], r15w
0x140008018  jnz     short loc_140008010
0x14000801a  mov     rdx, rbx
0x14000801d  lea     rcx, [rsp+210h+var_1D0]
0x140008022  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140008027  nop
0x140008028  lea     rdx, [rsp+210h+var_1D0]
0x14000802d  lea     rcx, [rsp+210h+var_1B0]
0x140008032  call    ?ws2s@WaasMedic@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; WaasMedic::ws2s(std::wstring const &)
0x140008037  cmp     qword ptr [rax+18h], 0Fh
0x14000803c  jbe     short loc_140008041
0x14000803e  mov     rax, [rax]
0x140008041  mov     rdx, rax; lpProcName
0x140008044  mov     rcx, cs:?g_hPluginCollection@@3PEAUHINSTANCE__@@EA; hModule
0x14000804b  call    cs:__imp_GetProcAddress
0x140008051  mov     rdi, rax
0x140008054  lea     rcx, [rsp+210h+var_1B0]
0x140008059  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14000805e  nop
0x14000805f  lea     rcx, [rsp+210h+var_1D0]; void *
0x140008064  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140008069  test    rdi, rdi
0x14000806c  jnz     short loc_140008095
0x14000806e  mov     rcx, [rbp+118h]; this
0x140008075  mov     qword ptr [rsp+210h+var_1F0], rbx; char *
0x14000807a  lea     r9, aGetprocaddress; "GetProcAddress failed to find action: %"...
0x140008081  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\sandbox\\s"...
0x140008088  lea     edx, [rdi+31h]; void *
0x14000808b  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x140008090  jmp     loc_140008155
0x140008095  lea     rcx, ?init@Plugin@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const SandboxAction::Plugin::init
0x14000809c  cmp     cs:qword_1400208C8, 7
0x1400080a4  cmova   rcx, cs:?init@Plugin@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const SandboxAction::Plugin::init
0x1400080ac  mov     rax, rbx
0x1400080af  sub     rcx, rbx
0x1400080b2  movzx   edx, word ptr [rax]
0x1400080b5  movzx   r8d, word ptr [rax+rcx]
0x1400080ba  sub     edx, r8d
0x1400080bd  jnz     short loc_1400080C8
0x1400080bf  add     rax, 2
0x1400080c3  test    r8d, r8d
0x1400080c6  jnz     short loc_1400080B2
0x1400080c8  test    edx, edx
0x1400080ca  jnz     short loc_1400080FE
0x1400080cc  mov     rax, rdi
0x1400080cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400080d4  mov     ebx, eax
0x1400080d6  test    eax, eax
0x1400080d8  jns     loc_14000822F
0x1400080de  mov     edx, 36h ; '6'; void *
0x1400080e3  mov     r9d, eax; char *
0x1400080e6  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\sandbox\\s"...
0x1400080ed  mov     rcx, [rbp+118h]; this
0x1400080f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400080f9  jmp     loc_14000823D
0x1400080fe  lea     rdx, ?performAction@Plugin@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const SandboxAction::Plugin::performAction
0x140008105  cmp     cs:qword_140020828, 7
0x14000810d  cmova   rdx, cs:?performAction@Plugin@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const SandboxAction::Plugin::performAction
0x140008115  mov     rax, rbx
0x140008118  sub     rdx, rbx
0x14000811b  movzx   r8d, word ptr [rax]
0x14000811f  movzx   r9d, word ptr [rax+rdx]
0x140008124  sub     r8d, r9d
0x140008127  jnz     short loc_140008132
0x140008129  add     rax, 2
0x14000812d  test    r9d, r9d
0x140008130  jnz     short loc_14000811B
0x140008132  test    r8d, r8d
0x140008135  jnz     short loc_140008166
0x140008137  mov     rcx, rsi
0x14000813a  mov     rax, rdi
0x14000813d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008142  mov     ebx, eax
0x140008144  test    eax, eax
0x140008146  jns     loc_14000822F
0x14000814c  mov     eax, 800704C7h
0x140008151  cmp     ebx, eax
0x140008153  jnz     short loc_14000815C
0x140008155  mov     ebx, eax
0x140008157  jmp     loc_14000823D
0x14000815c  mov     r9d, ebx
0x14000815f  mov     edx, 3Bh ; ';'
0x140008164  jmp     short loc_1400080E6
0x140008166  lea     rcx, ?detectCondition@Plugin@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const SandboxAction::Plugin::detectCondition
0x14000816d  cmp     cs:qword_140020928, 7
0x140008175  cmova   rcx, cs:?detectCondition@Plugin@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const SandboxAction::Plugin::detectCondition
0x14000817d  mov     rax, rbx
0x140008180  sub     rcx, rbx
0x140008183  movzx   edx, word ptr [rax]
0x140008186  movzx   r8d, word ptr [rax+rcx]
0x14000818b  sub     edx, r8d
0x14000818e  jnz     short loc_140008199
0x140008190  add     rax, 2
0x140008194  test    r8d, r8d
0x140008197  jnz     short loc_140008183
0x140008199  test    edx, edx
0x14000819b  jz      short loc_140008203
0x14000819d  lea     rdx, aPluginIsapplic; "Plugin_IsApplicable"
0x1400081a4  mov     rcx, rbx; String1
0x1400081a7  call    wcscmp_0
0x1400081ac  test    eax, eax
0x1400081ae  jz      short loc_140008203
0x1400081b0  lea     rax, ?setCorrelationVector@PluginCollection@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const SandboxAction::PluginCollection::setCorrelationVector
0x1400081b7  cmp     cs:qword_140020848, 7
0x1400081bf  cmova   rax, cs:?setCorrelationVector@PluginCollection@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const SandboxAction::PluginCollection::setCorrelationVector
0x1400081c7  sub     rax, rbx
0x1400081ca  movzx   edx, word ptr [rbx]
0x1400081cd  movzx   r8d, word ptr [rbx+rax]
0x1400081d2  sub     edx, r8d
0x1400081d5  jnz     short loc_1400081E0
0x1400081d7  add     rbx, 2
0x1400081db  test    r8d, r8d
0x1400081de  jnz     short loc_1400081CA
0x1400081e0  test    edx, edx
0x1400081e2  jnz     short loc_14000822F
0x1400081e4  lea     rcx, ?g_pszCVBuff@@3PADA; char near * g_pszCVBuff
0x1400081eb  mov     rax, rdi
0x1400081ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400081f3  mov     ebx, eax
0x1400081f5  test    eax, eax
0x1400081f7  jns     short loc_14000822F
0x1400081f9  mov     edx, 4Ah ; 'J'
0x1400081fe  jmp     loc_1400080E3
0x140008203  mov     [rsp+210h+var_1E0], r15b
0x140008208  lea     rdx, [rsp+210h+var_1E0]
0x14000820d  mov     rcx, rsi
0x140008210  mov     rax, rdi
0x140008213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008218  mov     ebx, eax
0x14000821a  test    eax, eax
0x14000821c  jns     short loc_140008228
0x14000821e  mov     edx, 43h ; 'C'
0x140008223  jmp     loc_1400080E3
0x140008228  mov     al, [rsp+210h+var_1E0]
0x14000822c  mov     [r14], al
0x14000822f  xor     edx, edx
0x140008231  lea     rcx, [rbp+110h+var_190]
0x140008235  call    ?Stop@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14000823a  mov     ebx, r15d
0x14000823d  mov     [rbp+110h+var_190], r12
0x140008241  lea     rcx, [rbp+110h+var_190]
0x140008245  call    ?Destroy@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x14000824a  lea     rcx, [rbp+110h+var_190]
0x14000824e  call    ??1?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x140008253  mov     eax, ebx
0x140008255  mov     rcx, [rbp+110h+var_40]
0x14000825c  xor     rcx, rsp; StackCookie
0x14000825f  call    __security_check_cookie
0x140008264  add     rsp, 1E0h
0x14000826b  pop     r15
0x14000826d  pop     r14
0x14000826f  pop     r12
0x140008271  pop     rdi
0x140008272  pop     rsi
0x140008273  pop     rbx
0x140008274  pop     rbp
0x140008275  retn
```
