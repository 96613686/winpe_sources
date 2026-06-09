# CModelDownloadComponent::InitializeMetadataUrl(ushort const *,ushort const *,ushort const *)

- ea: `0x14000f920`
- end: `0x14000faf4`
- name: `?InitializeMetadataUrl@CModelDownloadComponent@@AEAAJPEBG00@Z`
- size: `468`
- prototype: `__int64 __fastcall(CModelDownloadComponent *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000fafc`

## callees

- `0x14000985c`
- `0x14000af50`
- `0x14000b7f0`
- `0x14000bd5c`
- `0x14000f920`
- `0x1400131e4`
- `0x140013ac0`
- `0x140013aec`
- `0x140013b90`
- `0x140013bf0`
- `0x140013c1c`
- `0x140013d08`
- `0x140013d7c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14000fa65`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14000fa65`

## string_xrefs

- `0x14000fa82`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(410)`
- `0x14000fa9c`: `CModelDownloadComponent::InitializeMetadataUrl`
- `0x14000f97e`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(414)`
- `0x14000f9fa`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(430)`
- `0x14000fa15`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(433)`
- `0x14000fa30`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(436)`
- `0x14000fa4c`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(439)`
- `0x14000fa74`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(444)`

## pseudocode

```c
__int64 __fastcall CModelDownloadComponent::InitializeMetadataUrl(
        CModelDownloadComponent *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int Value; // ebx
  const wchar_t *v9; // rax
  const unsigned __int16 *v10; // rdx
  __int64 v11; // r8
  const unsigned __int16 *v12; // rdx
  HKEY v14; // [rsp+20h] [rbp-20h]
  const unsigned __int16 *v15; // [rsp+28h] [rbp-18h]
  __int64 v16; // [rsp+30h] [rbp-10h] BYREF
  __int64 v17; // [rsp+38h] [rbp-8h] BYREF
  __int64 v18; // [rsp+78h] [rbp+38h] BYREF

  v17 = 0;
  v16 = 0;
  v18 = 0;
  if ( !a2 || !a3 || !a4 )
  {
    Value = -2147024882;
    v9 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(410)";
    goto LABEL_21;
  }
  Value = SPOneSettings::Initialize((SPOneSettings *)&v18, a2, a3, a4, v14, v15);
  if ( Value < 0 )
  {
    v9 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(414)";
LABEL_21:
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::InitializeMetadataUrl",
      v9,
      Value);
    *((_WORD *)this + 843) = 0;
    goto LABEL_22;
  }
  SPOneSettings::ForceResetQueryState((SPOneSettings *)&v18);
  swprintf_s<261>((char *)this + 120, L"%s.%s.%s.%s", a2, L"SV10", a3, a4, v16);
  CSpDynamicString::operator=(&v16, (char *)this + 120);
  v10 = (const unsigned __int16 *)((char *)this + 642);
  if ( this != (CModelDownloadComponent *)-642LL )
  {
    v11 = -1;
    do
      ++v11;
    while ( v10[v11] );
    CSpDynamicString::AppendHR((CSpDynamicString *)&v16, v10, v11);
  }
  Value = SPOneSettings::SetProperty(
            (SPOneSettings *)&v18,
            (const struct CSpDynamicString *)v10,
            (const struct CSpDynamicString *)&v16);
  if ( Value < 0 )
  {
    v9 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(430)";
    goto LABEL_21;
  }
  Value = SPOneSettings::Query((SPOneSettings *)&v18);
  if ( Value < 0 )
  {
    v9 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(433)";
    goto LABEL_21;
  }
  if ( !(unsigned int)SPOneSettings::SettingsAvailable((SPOneSettings *)&v18) )
  {
    Value = -2147024664;
    v9 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(436)";
    goto LABEL_21;
  }
  Value = SPOneSettings::GetValue((SPOneSettings *)&v18, v12, (struct CSpDynamicString *)&v17);
  if ( Value < 0 )
  {
    v9 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(439)";
    goto LABEL_21;
  }
  if ( (unsigned int)_o_wcscpy_s((char *)this + 1686, 1025, v17) )
  {
    Value = -2147418113;
    v9 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(444)";
    goto LABEL_21;
  }
LABEL_22:
  SPOneSettings::reset((SPOneSettings *)&v18);
  CSpDynamicString::_free((CSpDynamicString *)&v16);
  CSpDynamicString::_free((CSpDynamicString *)&v17);
  return (unsigned int)Value;
}

```

## disassembly

```asm
0x14000f920  mov     [rsp-28h+arg_0], rbx
0x14000f925  mov     [rsp-28h+arg_10], rsi
0x14000f92a  push    rbp
0x14000f92b  push    rdi
0x14000f92c  push    r12
0x14000f92e  push    r14
0x14000f930  push    r15
0x14000f932  mov     rbp, rsp
0x14000f935  sub     rsp, 40h
0x14000f939  mov     rdi, r9
0x14000f93c  mov     rsi, r8
0x14000f93f  mov     r14, rdx
0x14000f942  mov     r15, rcx
0x14000f945  xor     r12d, r12d
0x14000f948  mov     [rbp+var_8], r12
0x14000f94c  mov     [rbp+var_10], r12
0x14000f950  mov     [rbp+arg_8], r12
0x14000f954  test    rdx, rdx
0x14000f957  jz      loc_14000FA7D
0x14000f95d  test    r8, r8
0x14000f960  jz      loc_14000FA7D
0x14000f966  test    r9, r9
0x14000f969  jz      loc_14000FA7D
0x14000f96f  lea     rcx, [rbp+arg_8]; this
0x14000f973  call    ?Initialize@SPOneSettings@@QEAAJPEBG00PEAUHKEY__@@0@Z; SPOneSettings::Initialize(ushort const *,ushort const *,ushort const *,HKEY__ *,ushort const *)
0x14000f978  mov     ebx, eax
0x14000f97a  test    eax, eax
0x14000f97c  jns     short loc_14000F98A
0x14000f97e  lea     rax, aOnecoreuapEndu_69; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f985  jmp     loc_14000FA89
0x14000f98a  lea     rcx, [rbp+arg_8]; this
0x14000f98e  call    ?ForceResetQueryState@SPOneSettings@@QEAAJXZ; SPOneSettings::ForceResetQueryState(void)
0x14000f993  mov     [rsp+40h+var_18], rdi
0x14000f998  mov     [rsp+40h+var_20], rsi
0x14000f99d  lea     r9, aSv10; "SV10"
0x14000f9a4  mov     r8, r14
0x14000f9a7  lea     rdx, aSSSS; "%s.%s.%s.%s"
0x14000f9ae  lea     rcx, [r15+78h]
0x14000f9b2  call    ??$swprintf_s@$0BAF@@@YAHAEAY0BAF@GPEBGZZ; swprintf_s<261>(ushort (&)[261],ushort const *,...)
0x14000f9b7  lea     rdx, [r15+78h]
0x14000f9bb  lea     rcx, [rbp+var_10]
0x14000f9bf  call    ??4CSpDynamicString@@QEAAPEAGPEBG@Z; CSpDynamicString::operator=(ushort const *)
0x14000f9c4  lea     rdx, [r15+282h]; unsigned __int16 *
0x14000f9cb  test    rdx, rdx
0x14000f9ce  jz      short loc_14000F9E7
0x14000f9d0  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000f9d4  inc     r8; unsigned int
0x14000f9d7  cmp     [rdx+r8*2], r12w
0x14000f9dc  jnz     short loc_14000F9D4
0x14000f9de  lea     rcx, [rbp+var_10]; this
0x14000f9e2  call    ?AppendHR@CSpDynamicString@@QEAAJPEBGK@Z; CSpDynamicString::AppendHR(ushort const *,ulong)
0x14000f9e7  lea     r8, [rbp+var_10]; struct CSpDynamicString *
0x14000f9eb  lea     rcx, [rbp+arg_8]; this
0x14000f9ef  call    ?SetProperty@SPOneSettings@@QEAAJAEBVCSpDynamicString@@0@Z; SPOneSettings::SetProperty(CSpDynamicString const &,CSpDynamicString const &)
0x14000f9f4  mov     ebx, eax
0x14000f9f6  test    eax, eax
0x14000f9f8  jns     short loc_14000FA06
0x14000f9fa  lea     rax, aOnecoreuapEndu_89; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000fa01  jmp     loc_14000FA89
0x14000fa06  lea     rcx, [rbp+arg_8]; this
0x14000fa0a  call    ?Query@SPOneSettings@@QEAAJXZ; SPOneSettings::Query(void)
0x14000fa0f  mov     ebx, eax
0x14000fa11  test    eax, eax
0x14000fa13  jns     short loc_14000FA1E
0x14000fa15  lea     rax, aOnecoreuapEndu_12; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000fa1c  jmp     short loc_14000FA89
0x14000fa1e  lea     rcx, [rbp+arg_8]; this
0x14000fa22  call    ?SettingsAvailable@SPOneSettings@@QEBAHXZ; SPOneSettings::SettingsAvailable(void)
0x14000fa27  test    eax, eax
0x14000fa29  jnz     short loc_14000FA39
0x14000fa2b  mov     ebx, 800700E8h
0x14000fa30  lea     rax, aOnecoreuapEndu_56; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000fa37  jmp     short loc_14000FA89
0x14000fa39  lea     r8, [rbp+var_8]; struct CSpDynamicString *
0x14000fa3d  lea     rcx, [rbp+arg_8]; this
0x14000fa41  call    ?GetValue@SPOneSettings@@QEAAJPEBGAEAVCSpDynamicString@@@Z; SPOneSettings::GetValue(ushort const *,CSpDynamicString &)
0x14000fa46  mov     ebx, eax
0x14000fa48  test    eax, eax
0x14000fa4a  jns     short loc_14000FA55
0x14000fa4c  lea     rax, aOnecoreuapEndu_57; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000fa53  jmp     short loc_14000FA89
0x14000fa55  lea     rcx, [r15+696h]
0x14000fa5c  mov     r8, [rbp+var_8]
0x14000fa60  mov     edx, 401h
0x14000fa65  call    cs:__imp__o_wcscpy_s
0x14000fa6b  test    eax, eax
0x14000fa6d  jz      short loc_14000FABC
0x14000fa6f  mov     ebx, 8000FFFFh
0x14000fa74  lea     rax, aOnecoreuapEndu_45; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000fa7b  jmp     short loc_14000FA89
0x14000fa7d  mov     ebx, 8007000Eh
0x14000fa82  lea     rax, aOnecoreuapEndu_98; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000fa89  mov     ecx, 2; int
0x14000fa8e  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14000fa95  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000fa9c  lea     r9, aCmodeldownload_27; "CModelDownloadComponent::InitializeMeta"...
0x14000faa3  mov     r10d, ebx
0x14000faa6  mov     dword ptr [rsp+40h+var_18], ebx
0x14000faaa  mov     [rsp+40h+var_20], rax
0x14000faaf  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000fab4  mov     [r15+696h], r12w
0x14000fabc  lea     rcx, [rbp+arg_8]; this
0x14000fac0  call    ?reset@SPOneSettings@@AEAAXXZ; SPOneSettings::reset(void)
0x14000fac5  nop
0x14000fac6  lea     rcx, [rbp+var_10]; this
0x14000faca  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x14000facf  nop
0x14000fad0  lea     rcx, [rbp+var_8]; this
0x14000fad4  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x14000fad9  mov     eax, ebx
0x14000fadb  lea     r11, [rsp+40h+var_s0]
0x14000fae0  mov     rbx, [r11+30h]
0x14000fae4  mov     rsi, [r11+40h]
0x14000fae8  mov     rsp, r11
0x14000faeb  pop     r15
0x14000faed  pop     r14
0x14000faef  pop     r12
0x14000faf1  pop     rdi
0x14000faf2  pop     rbp
0x14000faf3  retn
```
