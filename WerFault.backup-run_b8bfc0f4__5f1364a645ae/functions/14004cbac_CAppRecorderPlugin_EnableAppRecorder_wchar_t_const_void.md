# CAppRecorderPlugin::EnableAppRecorder(wchar_t const *,void *)

- ea: `0x14004cbac`
- end: `0x14004cf4f`
- name: `?EnableAppRecorder@CAppRecorderPlugin@@AEAAJPEB_WPEAX@Z`
- size: `931`
- prototype: `__int64 __fastcall(CAppRecorderPlugin *__hidden this, const wchar_t *, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14004d230`

## callees

- `0x140005468`
- `0x14001444c`
- `0x140014474`
- `0x14004cbac`
- `0x14004d690`
- `0x14004e1ac`
- `0x1400549e8`
- `0x140054aa0`
- `0x140054c74`
- `0x1400551c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004cd2e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004cd2e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004cc20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004cf2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004cc20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004cf2a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14004cef9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14004cef9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004ce59`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004ce59`

## string_xrefs

- `0x14004cc53`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins`
- `0x14004cdca`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins\AppRecorder`
- `0x14004ce4f`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins\AppRecorder`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAppRecorderPlugin::EnableAppRecorder(CAppRecorderPlugin *this, const wchar_t *a2, wchar_t *a3)
{
  int v7; // edi
  CUserModeHangReport *v8; // rcx
  __int64 v9; // rdx
  int v10; // eax
  CUserModeHangReport *v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // edi
  __int64 v14; // rsi
  HKEY *phkResult; // rax
  enum _ACCESS_MODE v16; // edx
  int v17; // eax
  BYTE Data[8]; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-8h] BYREF
  int v20; // [rsp+98h] [rbp+38h] BYREF
  DWORD dwDisposition; // [rsp+A8h] [rbp+48h] BYREF

  v20 = 0;
  hKey = 0;
  dwDisposition = 0;
  *(_DWORD *)Data = 1;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids);
    }
    return 2147942487LL;
  }
  if ( *((_DWORD *)this + 14) == 1 || *((_DWORD *)this + 15) == 1 )
    return 0;
  v7 = CheckPluginLastPromptedTime(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Plugins",
         a3,
         2u,
         &v20);
  if ( v7 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 24;
LABEL_12:
      WPP_SF_(*((_QWORD *)v8 + 2), v9, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids);
    }
    goto LABEL_49;
  }
  if ( v20 )
  {
    v10 = WerPluginParseSettings(
            (CAppRecorderPlugin *)((char *)this + 80),
            2u,
            (struct KEY_DATA_TYPE *)&off_14007A500,
            2u,
            a2);
    v7 = v10;
    if ( v10 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 25;
LABEL_18:
        WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids, (unsigned int)v10);
      }
      goto LABEL_49;
    }
    v13 = 0;
    while ( 1 )
    {
      v14 = 568LL * v13;
      if ( !(unsigned int)_o__wcsicmp((char *)this + v14 + 84, L"AppRecorderVersion")
        && *(_DWORD *)((char *)this + v14 + 640) > 1u )
      {
        break;
      }
      if ( ++v13 >= 2 )
      {
        if ( !(unsigned int)CAppRecorderPlugin::PromptForEnableAppRecorder(this, a3) )
        {
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids);
          }
          v7 = 1;
          goto LABEL_49;
        }
        v10 = CAppRecorderPlugin::WriteAppCompatLayer(this);
        v7 = v10;
        if ( v10 >= 0 )
        {
          v10 = WerPluginWriteSettings(
                  (const BYTE *)this + 80,
                  2u,
                  HKEY_CURRENT_USER,
                  L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Plugins\\AppRecorder");
          v7 = v10;
          if ( v10 >= 0 )
          {
            phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
            if ( RegCreateKeyExW(
                   HKEY_CURRENT_USER,
                   L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Plugins\\AppRecorder",
                   0,
                   0,
                   0,
                   0x60002u,
                   0,
                   phkResult,
                   &dwDisposition) )
            {
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v9 = 29;
                goto LABEL_12;
              }
            }
            else
            {
              v17 = WerPluginAdjustAppContainerAccessToKey(hKey, v16, 0x80010002);
              v7 = v17;
              if ( v17 < 0
                && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  30,
                  WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids,
                  (unsigned int)v17);
              }
              if ( !RegSetValueExW(hKey, L"AppRecorderEnabled", 0, 4u, Data, 4u) )
                break;
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v9 = 31;
                goto LABEL_12;
              }
            }
          }
          else
          {
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v12 = 28;
              goto LABEL_18;
            }
          }
        }
        else
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v12 = 27;
            goto LABEL_18;
          }
        }
        goto LABEL_49;
      }
    }
  }
  v7 = 0;
LABEL_49:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14004cbac  mov     [rsp-28h+arg_0], rbx
0x14004cbb1  mov     [rsp-28h+arg_10], rsi
0x14004cbb6  push    rbp
0x14004cbb7  push    rdi
0x14004cbb8  push    r13
0x14004cbba  push    r14
0x14004cbbc  push    r15
0x14004cbbe  mov     rbp, rsp
0x14004cbc1  sub     rsp, 60h
0x14004cbc5  mov     r15, r8
0x14004cbc8  mov     rsi, rdx
0x14004cbcb  mov     rbx, rcx
0x14004cbce  mov     [rbp+arg_8], 0
0x14004cbd5  xor     ecx, ecx
0x14004cbd7  mov     [rbp+hKey], rcx
0x14004cbdb  mov     [rbp+dwDisposition], ecx
0x14004cbde  lea     r13d, [rcx+1]
0x14004cbe2  mov     dword ptr [rbp+Data], r13d
0x14004cbe6  test    rdx, rdx
0x14004cbe9  jnz     short loc_14004CC30
0x14004cbeb  lea     rbx, WPP_GLOBAL_Control
0x14004cbf2  mov     rax, cs:WPP_GLOBAL_Control
0x14004cbf9  cmp     rax, rbx
0x14004cbfc  jz      short loc_14004CC1B
0x14004cbfe  test    [rax+1Ch], r13b
0x14004cc02  jz      short loc_14004CC1B
0x14004cc04  lea     edx, [rsi+17h]
0x14004cc07  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x14004cc0e  mov     rcx, [rax+10h]
0x14004cc12  call    WPP_SF_
0x14004cc17  mov     rcx, [rbp+hKey]; hKey
0x14004cc1b  test    rcx, rcx
0x14004cc1e  jz      short loc_14004CC26
0x14004cc20  call    cs:__imp_RegCloseKey
0x14004cc26  mov     eax, 80070057h
0x14004cc2b  jmp     loc_14004CF36
0x14004cc30  cmp     [rbx+38h], r13d
0x14004cc34  jz      loc_14004CF34
0x14004cc3a  cmp     [rbx+3Ch], r13d
0x14004cc3e  jz      loc_14004CF34
0x14004cc44  lea     rax, [rbp+arg_8]
0x14004cc48  mov     qword ptr [rsp+60h+dwOptions], rax; int *
0x14004cc4d  mov     r9d, 2; unsigned int
0x14004cc53  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\Windows E"...
0x14004cc5a  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x14004cc61  call    ?CheckPluginLastPromptedTime@@YAJPEAUHKEY__@@PEB_W1KPEAH@Z; CheckPluginLastPromptedTime(HKEY__ *,wchar_t const *,wchar_t const *,ulong,int *)
0x14004cc66  mov     edi, eax
0x14004cc68  test    eax, eax
0x14004cc6a  jns     short loc_14004CCA7
0x14004cc6c  lea     rbx, WPP_GLOBAL_Control
0x14004cc73  mov     rcx, cs:WPP_GLOBAL_Control
0x14004cc7a  cmp     rcx, rbx
0x14004cc7d  jz      loc_14004CF21
0x14004cc83  test    [rcx+1Ch], r13b
0x14004cc87  jz      loc_14004CF21
0x14004cc8d  mov     edx, 18h
0x14004cc92  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x14004cc99  mov     rcx, [rcx+10h]
0x14004cc9d  call    WPP_SF_
0x14004cca2  jmp     loc_14004CF21
0x14004cca7  cmp     [rbp+arg_8], 0
0x14004ccab  jz      loc_14004CF1F
0x14004ccb1  lea     r14, [rbx+50h]
0x14004ccb5  mov     qword ptr [rsp+60h+dwOptions], rsi; wchar_t *
0x14004ccba  mov     edx, 2; unsigned int
0x14004ccbf  mov     r9d, edx; unsigned int
0x14004ccc2  lea     r8, off_14007A500; struct KEY_DATA_TYPE *
0x14004ccc9  mov     rcx, r14; struct _AUTOVERIFIER_IPT_SETTINGS *
0x14004cccc  call    ?WerPluginParseSettings@@YAJPEAU_AUTOVERIFIER_IPT_SETTINGS@@KPEAUKEY_DATA_TYPE@@KPEB_W@Z; WerPluginParseSettings(_AUTOVERIFIER_IPT_SETTINGS *,ulong,KEY_DATA_TYPE *,ulong,wchar_t const *)
0x14004ccd1  mov     edi, eax
0x14004ccd3  test    eax, eax
0x14004ccd5  jns     short loc_14004CD15
0x14004ccd7  lea     rbx, WPP_GLOBAL_Control
0x14004ccde  mov     rcx, cs:WPP_GLOBAL_Control
0x14004cce5  cmp     rcx, rbx
0x14004cce8  jz      loc_14004CF21
0x14004ccee  test    [rcx+1Ch], r13b
0x14004ccf2  jz      loc_14004CF21
0x14004ccf8  mov     edx, 19h
0x14004ccfd  mov     r9d, eax
0x14004cd00  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x14004cd07  mov     rcx, [rcx+10h]
0x14004cd0b  call    WPP_SF_d
0x14004cd10  jmp     loc_14004CF21
0x14004cd15  xor     edi, edi
0x14004cd17  mov     eax, edi
0x14004cd19  imul    rsi, rax, 238h
0x14004cd20  lea     rcx, [rbx+54h]
0x14004cd24  add     rcx, rsi
0x14004cd27  lea     rdx, aApprecorderver; "AppRecorderVersion"
0x14004cd2e  call    cs:__imp__o__wcsicmp
0x14004cd34  test    eax, eax
0x14004cd36  jnz     short loc_14004CD46
0x14004cd38  cmp     [rsi+rbx+280h], r13d
0x14004cd40  ja      loc_14004CF1F
0x14004cd46  add     edi, r13d
0x14004cd49  cmp     edi, 2
0x14004cd4c  jb      short loc_14004CD17
0x14004cd4e  mov     rdx, r15; void *
0x14004cd51  mov     rcx, rbx; this
0x14004cd54  call    ?PromptForEnableAppRecorder@CAppRecorderPlugin@@AEAAHPEAX@Z; CAppRecorderPlugin::PromptForEnableAppRecorder(void *)
0x14004cd59  test    eax, eax
0x14004cd5b  jnz     short loc_14004CD91
0x14004cd5d  lea     rbx, WPP_GLOBAL_Control
0x14004cd64  mov     rcx, cs:WPP_GLOBAL_Control
0x14004cd6b  cmp     rcx, rbx
0x14004cd6e  jz      short loc_14004CD89
0x14004cd70  test    byte ptr [rcx+1Ch], 4
0x14004cd74  jz      short loc_14004CD89
0x14004cd76  lea     edx, [rax+1Ah]
0x14004cd79  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x14004cd80  mov     rcx, [rcx+10h]
0x14004cd84  call    WPP_SF_
0x14004cd89  mov     edi, r13d
0x14004cd8c  jmp     loc_14004CF21
0x14004cd91  mov     rcx, rbx; this
0x14004cd94  call    ?WriteAppCompatLayer@CAppRecorderPlugin@@AEAAJXZ; CAppRecorderPlugin::WriteAppCompatLayer(void)
0x14004cd99  mov     edi, eax
0x14004cd9b  test    eax, eax
0x14004cd9d  jns     short loc_14004CDCA
0x14004cd9f  lea     rbx, WPP_GLOBAL_Control
0x14004cda6  mov     rcx, cs:WPP_GLOBAL_Control
0x14004cdad  cmp     rcx, rbx
0x14004cdb0  jz      loc_14004CF21
0x14004cdb6  test    [rcx+1Ch], r13b
0x14004cdba  jz      loc_14004CF21
0x14004cdc0  mov     edx, 1Bh
0x14004cdc5  jmp     loc_14004CCFD
0x14004cdca  lea     r9, aSoftwareMicros_9; "Software\\Microsoft\\Windows\\Windows E"...
0x14004cdd1  mov     rbx, 0FFFFFFFF80000001h
0x14004cdd8  mov     r8, rbx; HKEY
0x14004cddb  mov     edx, 2; unsigned int
0x14004cde0  mov     rcx, r14; struct _AUTOVERIFIER_IPT_SETTINGS *
0x14004cde3  call    ?WerPluginWriteSettings@@YAJPEAU_AUTOVERIFIER_IPT_SETTINGS@@KPEAUHKEY__@@PEB_W@Z; WerPluginWriteSettings(_AUTOVERIFIER_IPT_SETTINGS *,ulong,HKEY__ *,wchar_t const *)
0x14004cde8  mov     edi, eax
0x14004cdea  test    eax, eax
0x14004cdec  jns     short loc_14004CE19
0x14004cdee  lea     rbx, WPP_GLOBAL_Control
0x14004cdf5  mov     rcx, cs:WPP_GLOBAL_Control
0x14004cdfc  cmp     rcx, rbx
0x14004cdff  jz      loc_14004CF21
0x14004ce05  test    [rcx+1Ch], r13b
0x14004ce09  jz      loc_14004CF21
0x14004ce0f  mov     edx, 1Ch
0x14004ce14  jmp     loc_14004CCFD
0x14004ce19  lea     rcx, [rbp+hKey]
0x14004ce1d  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14004ce22  lea     r8, [rbp+dwDisposition]
0x14004ce26  mov     [rsp+60h+lpdwDisposition], r8; lpdwDisposition
0x14004ce2b  mov     [rsp+60h+phkResult], rax; phkResult
0x14004ce30  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14004ce39  mov     [rsp+60h+samDesired], 60002h; samDesired
0x14004ce41  mov     [rsp+60h+dwOptions], 0; dwOptions
0x14004ce49  xor     r9d, r9d; lpClass
0x14004ce4c  xor     r8d, r8d; Reserved
0x14004ce4f  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\Windows\\Windows E"...
0x14004ce56  mov     rcx, rbx; hKey
0x14004ce59  call    cs:__imp_RegCreateKeyExW
0x14004ce5f  test    eax, eax
0x14004ce61  jz      short loc_14004CE8E
0x14004ce63  lea     rbx, WPP_GLOBAL_Control
0x14004ce6a  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ce71  cmp     rcx, rbx
0x14004ce74  jz      loc_14004CF21
0x14004ce7a  test    [rcx+1Ch], r13b
0x14004ce7e  jz      loc_14004CF21
0x14004ce84  mov     edx, 1Dh
0x14004ce89  jmp     loc_14004CC92
0x14004ce8e  mov     r8d, 80010002h; unsigned int
0x14004ce94  mov     rcx, [rbp+hKey]; hKey
0x14004ce98  call    ?WerPluginAdjustAppContainerAccessToKey@@YAJPEAUHKEY__@@W4_ACCESS_MODE@@K@Z; WerPluginAdjustAppContainerAccessToKey(HKEY__ *,_ACCESS_MODE,ulong)
0x14004ce9d  mov     edi, eax
0x14004ce9f  lea     rbx, WPP_GLOBAL_Control
0x14004cea6  test    eax, eax
0x14004cea8  jns     short loc_14004CED4
0x14004ceaa  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ceb1  cmp     rcx, rbx
0x14004ceb4  jz      short loc_14004CED4
0x14004ceb6  test    byte ptr [rcx+1Ch], 2
0x14004ceba  jz      short loc_14004CED4
0x14004cebc  mov     edx, 1Eh
0x14004cec1  mov     r9d, eax
0x14004cec4  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x14004cecb  mov     rcx, [rcx+10h]
0x14004cecf  call    WPP_SF_d
0x14004ced4  mov     [rsp+60h+samDesired], 4; cbData
0x14004cedc  lea     rax, [rbp+Data]
0x14004cee0  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x14004cee5  mov     r9d, 4; dwType
0x14004ceeb  xor     r8d, r8d; Reserved
0x14004ceee  lea     rdx, aApprecorderena; "AppRecorderEnabled"
0x14004cef5  mov     rcx, [rbp+hKey]; hKey
0x14004cef9  call    cs:__imp_RegSetValueExW
0x14004ceff  test    eax, eax
0x14004cf01  jz      short loc_14004CF1F
0x14004cf03  mov     rcx, cs:WPP_GLOBAL_Control
0x14004cf0a  cmp     rcx, rbx
0x14004cf0d  jz      short loc_14004CF21
0x14004cf0f  test    [rcx+1Ch], r13b
0x14004cf13  jz      short loc_14004CF21
0x14004cf15  mov     edx, 1Fh
0x14004cf1a  jmp     loc_14004CC92
0x14004cf1f  xor     edi, edi
0x14004cf21  mov     rcx, [rbp+hKey]; hKey
0x14004cf25  test    rcx, rcx
0x14004cf28  jz      short loc_14004CF30
0x14004cf2a  call    cs:__imp_RegCloseKey
0x14004cf30  mov     eax, edi
0x14004cf32  jmp     short loc_14004CF36
0x14004cf34  xor     eax, eax
0x14004cf36  lea     r11, [rsp+60h+var_s0]
0x14004cf3b  mov     rbx, [r11+30h]
0x14004cf3f  mov     rsi, [r11+40h]
0x14004cf43  mov     rsp, r11
0x14004cf46  pop     r15
0x14004cf48  pop     r14
0x14004cf4a  pop     r13
0x14004cf4c  pop     rdi
0x14004cf4d  pop     rbp
0x14004cf4e  retn
```
