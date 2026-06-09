# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingUtils::IsGroupPolicyAllowed(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName,bool &,bool &)

- ea: `0x140025768`
- end: `0x14002587d`
- name: `?IsGroupPolicyAllowed@AgentActivationSettingUtils@Settings@Windows@VoiceAgentServices@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AgentActivationSettingName@2345@AEA_N2@Z`
- size: `277`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400295d0`
- `0x14002a340`

## callees

- `0x140004b48`
- `0x14000e030`
- `0x140025610`
- `0x140025768`
- `0x140025e2c`

## import_xrefs

- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_GetPolicy` at `0x140025802`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_GetPolicy` at `0x140025802`

## string_xrefs

- `0x140025790`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingutils.cpp`
- `0x14002581d`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingutils.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingUtils::IsGroupPolicyAllowed(
        __int64 a1,
        int a2,
        bool *a3,
        bool *a4)
{
  const wchar_t *v7; // rbx
  __int64 v8; // rax
  int v9; // [rsp+20h] [rbp-28h]
  char *v10; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v12; // [rsp+50h] [rbp+8h] BYREF

  v12 = a1;
  if ( a2 )
  {
    if ( a2 != 1 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x93,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingutils.cpp",
        (const char *)0x80070057LL,
        v9);
      return 2147942487LL;
    }
    v7 = L"LetAppsActivateWithVoiceAboveLock";
  }
  else
  {
    v7 = L"LetAppsActivateWithVoice";
  }
  *a3 = 1;
  *a4 = 0;
  v10 = (char *)0x200000001LL;
  if ( (unsigned __int8)IsPolicyManager_GetPolicyPresent() )
  {
    v12 = 0;
    if ( (int)PolicyManager_GetPolicy(L"Privacy", v7, &v10, &v12) >= 0 )
    {
      LOBYTE(v9) = *(_DWORD *)(v12 + 8) != 1;
      wil::details::in1diag3::Log_HrIfMsg(
        retaddr,
        (void *)0xA7,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingutils.cpp",
        (const char *)0x8000FFFFLL,
        v9,
        (bool)"RetrievedInfo type is not of expected format.",
        v10);
      v8 = v12;
      if ( *(_DWORD *)(v12 + 8) == 1 )
      {
        *a3 = *(_DWORD *)(v12 + 16) != 2;
        *a4 = *(_DWORD *)(v8 + 16) != 0;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&long PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&long PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>(&v12);
  }
  return 0;
}

```

## disassembly

```asm
0x140025768  mov     [rsp+arg_8], rbx
0x14002576d  mov     [rsp+arg_10], rsi
0x140025772  mov     [rsp+arg_0], rcx
0x140025777  push    rdi
0x140025778  sub     rsp, 40h
0x14002577c  mov     rdi, r9
0x14002577f  mov     rsi, r8
0x140025782  test    edx, edx
0x140025784  jz      short loc_1400257B9
0x140025786  cmp     edx, 1
0x140025789  jz      short loc_1400257B0
0x14002578b  mov     rcx, [rsp+48h]; this
0x140025790  lea     r8, aOnecoreuapEndu_42; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140025797  mov     ebx, 80070057h
0x14002579c  mov     edx, 93h; void *
0x1400257a1  mov     r9d, ebx; char *
0x1400257a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400257a9  mov     eax, ebx
0x1400257ab  jmp     loc_14002586D
0x1400257b0  lea     rbx, aLetappsactivat_0; "LetAppsActivateWithVoiceAboveLock"
0x1400257b7  jmp     short loc_1400257C0
0x1400257b9  lea     rbx, aLetappsactivat; "LetAppsActivateWithVoice"
0x1400257c0  mov     byte ptr [r8], 1
0x1400257c4  mov     byte ptr [r9], 0
0x1400257c8  mov     dword ptr [rsp+48h+var_18], 1; char *
0x1400257d0  mov     dword ptr [rsp+48h+var_18+4], 2
0x1400257d8  call    IsPolicyManager_GetPolicyPresent
0x1400257dd  test    al, al
0x1400257df  jz      loc_14002586B
0x1400257e5  lea     r9, [rsp+48h+arg_0]
0x1400257ea  mov     [rsp+48h+arg_0], 0
0x1400257f3  lea     r8, [rsp+48h+var_18]
0x1400257f8  mov     rdx, rbx
0x1400257fb  lea     rcx, aPrivacy; "Privacy"
0x140025802  call    cs:__imp_PolicyManager_GetPolicy
0x140025808  test    eax, eax
0x14002580a  js      short loc_140025861
0x14002580c  mov     rax, [rsp+48h+arg_0]
0x140025811  lea     rdx, aRetrievedinfoT; "RetrievedInfo type is not of expected f"...
0x140025818  mov     rcx, [rsp+48h]; this
0x14002581d  lea     r8, aOnecoreuapEndu_42; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140025824  mov     qword ptr [rsp+48h+var_20], rdx; bool
0x140025829  mov     r9d, 8000FFFFh; char *
0x14002582f  mov     edx, 0A7h; void *
0x140025834  cmp     dword ptr [rax+8], 1
0x140025838  setnz   al
0x14002583b  mov     byte ptr [rsp+48h+var_28], al; int
0x14002583f  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x140025844  mov     rax, [rsp+48h+arg_0]
0x140025849  cmp     dword ptr [rax+8], 1
0x14002584d  jnz     short loc_140025861
0x14002584f  cmp     dword ptr [rax+10h], 2
0x140025853  setnz   cl
0x140025856  mov     [rsi], cl
0x140025858  cmp     dword ptr [rax+10h], 0
0x14002585c  setnz   al
0x14002585f  mov     [rdi], al
0x140025861  lea     rcx, [rsp+48h+arg_0]
0x140025866  call    ??1?$unique_storage@U?$resource_policy@PEAUPMPolicyRetrievedInfo@@P6AJPEAU1@@Z$1?PolicyManager_FreeGetPolicyData@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>(void)
0x14002586b  xor     eax, eax
0x14002586d  mov     rbx, [rsp+48h+arg_8]
0x140025872  mov     rsi, [rsp+48h+arg_10]
0x140025877  add     rsp, 40h
0x14002587b  pop     rdi
0x14002587c  retn
```
