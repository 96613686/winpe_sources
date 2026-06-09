# CAppRecorderPlugin::EnableAppRecorder(wchar_t const *,void *)

- ea: `0x14005014c`
- end: `0x14005050e`
- name: `?EnableAppRecorder@CAppRecorderPlugin@@AEAAJPEB_WPEAX@Z`
- size: `962`
- prototype: `__int64 __fastcall(CAppRecorderPlugin *__hidden this, const wchar_t *, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400507f0`

## callees

- `0x14000551c`
- `0x140014ee4`
- `0x140014f14`
- `0x14005014c`
- `0x140050bf4`
- `0x1400517c4`
- `0x140058408`
- `0x1400584c0`
- `0x1400586ac`
- `0x140058c04`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400502d4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400502d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400501c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400504e2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400501c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400504e2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400504ab`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400504ab`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140050405`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140050405`

## string_xrefs

- `0x1400501f9`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins`
- `0x140050376`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins\AppRecorder`
- `0x1400503fb`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins\AppRecorder`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAppRecorderPlugin::EnableAppRecorder(CAppRecorderPlugin *this, const wchar_t *a2, wchar_t *a3)
{
  int v7; // edi
  CUserModeHangReport *v8; // rcx
  __int64 v9; // rdx
  int v10; // eax
  __int64 v11; // r8
  CUserModeHangReport *v12; // rcx
  __int64 v13; // rdx
  unsigned int v14; // edi
  __int64 v15; // rsi
  HKEY *phkResult; // rax
  enum _ACCESS_MODE v17; // edx
  int v18; // eax
  BYTE Data[8]; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-8h] BYREF
  int v21; // [rsp+98h] [rbp+38h] BYREF
  DWORD dwDisposition; // [rsp+A8h] [rbp+48h] BYREF

  v21 = 0;
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
         &v21);
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
  if ( v21 )
  {
    v10 = WerPluginParseSettings(
            (CAppRecorderPlugin *)((char *)this + 80),
            2u,
            (struct KEY_DATA_TYPE *)&off_14007E500,
            2u,
            a2);
    v7 = v10;
    if ( v10 < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v13 = 25;
LABEL_18:
        WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids, (unsigned int)v10);
      }
      goto LABEL_49;
    }
    v14 = 0;
    while ( 1 )
    {
      v15 = 568LL * v14;
      if ( !(unsigned int)_o__wcsicmp((char *)this + v15 + 84, L"AppRecorderVersion", v11)
        && *(_DWORD *)((char *)this + v15 + 640) > 1u )
      {
        break;
      }
      if ( ++v14 >= 2 )
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
              v18 = WerPluginAdjustAppContainerAccessToKey(hKey, v17, 0x80010002);
              v7 = v18;
              if ( v18 < 0
                && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  30,
                  WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids,
                  (unsigned int)v18);
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
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v13 = 28;
              goto LABEL_18;
            }
          }
        }
        else
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v13 = 27;
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
0x14005014c  mov     [rsp-28h+arg_0], rbx
0x140050151  mov     [rsp-28h+arg_10], rsi
0x140050156  push    rbp
0x140050157  push    rdi
0x140050158  push    r13
0x14005015a  push    r14
0x14005015c  push    r15
0x14005015e  mov     rbp, rsp
0x140050161  sub     rsp, 60h
0x140050165  mov     r15, r8
0x140050168  mov     rsi, rdx
0x14005016b  mov     rbx, rcx
0x14005016e  mov     [rbp+arg_8], 0
0x140050175  xor     ecx, ecx
0x140050177  mov     [rbp+hKey], rcx
0x14005017b  mov     [rbp+dwDisposition], ecx
0x14005017e  lea     r13d, [rcx+1]
0x140050182  mov     dword ptr [rbp+Data], r13d
0x140050186  test    rdx, rdx
0x140050189  jnz     short loc_1400501D6
0x14005018b  lea     rbx, WPP_GLOBAL_Control
0x140050192  mov     rax, cs:WPP_GLOBAL_Control
0x140050199  cmp     rax, rbx
0x14005019c  jz      short loc_1400501BB
0x14005019e  test    [rax+1Ch], r13b
0x1400501a2  jz      short loc_1400501BB
0x1400501a4  lea     edx, [rsi+17h]
0x1400501a7  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x1400501ae  mov     rcx, [rax+10h]
0x1400501b2  call    WPP_SF_
0x1400501b7  mov     rcx, [rbp+hKey]; hKey
0x1400501bb  test    rcx, rcx
0x1400501be  jz      short loc_1400501CC
0x1400501c0  call    cs:__imp_RegCloseKey
0x1400501c7  nop     dword ptr [rax+rax+00h]
0x1400501cc  mov     eax, 80070057h
0x1400501d1  jmp     loc_1400504F4
0x1400501d6  cmp     [rbx+38h], r13d
0x1400501da  jz      loc_1400504F2
0x1400501e0  cmp     [rbx+3Ch], r13d
0x1400501e4  jz      loc_1400504F2
0x1400501ea  lea     rax, [rbp+arg_8]
0x1400501ee  mov     qword ptr [rsp+60h+dwOptions], rax; int *
0x1400501f3  mov     r9d, 2; unsigned int
0x1400501f9  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\Windows E"...
0x140050200  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x140050207  call    ?CheckPluginLastPromptedTime@@YAJPEAUHKEY__@@PEB_W1KPEAH@Z; CheckPluginLastPromptedTime(HKEY__ *,wchar_t const *,wchar_t const *,ulong,int *)
0x14005020c  mov     edi, eax
0x14005020e  test    eax, eax
0x140050210  jns     short loc_14005024D
0x140050212  lea     rbx, WPP_GLOBAL_Control
0x140050219  mov     rcx, cs:WPP_GLOBAL_Control
0x140050220  cmp     rcx, rbx
0x140050223  jz      loc_1400504D9
0x140050229  test    [rcx+1Ch], r13b
0x14005022d  jz      loc_1400504D9
0x140050233  mov     edx, 18h
0x140050238  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x14005023f  mov     rcx, [rcx+10h]
0x140050243  call    WPP_SF_
0x140050248  jmp     loc_1400504D9
0x14005024d  cmp     [rbp+arg_8], 0
0x140050251  jz      loc_1400504D7
0x140050257  lea     r14, [rbx+50h]
0x14005025b  mov     qword ptr [rsp+60h+dwOptions], rsi; wchar_t *
0x140050260  mov     edx, 2; unsigned int
0x140050265  mov     r9d, edx; unsigned int
0x140050268  lea     r8, off_14007E500; struct KEY_DATA_TYPE *
0x14005026f  mov     rcx, r14; struct _AUTOVERIFIER_IPT_SETTINGS *
0x140050272  call    ?WerPluginParseSettings@@YAJPEAU_AUTOVERIFIER_IPT_SETTINGS@@KPEAUKEY_DATA_TYPE@@KPEB_W@Z; WerPluginParseSettings(_AUTOVERIFIER_IPT_SETTINGS *,ulong,KEY_DATA_TYPE *,ulong,wchar_t const *)
0x140050277  mov     edi, eax
0x140050279  test    eax, eax
0x14005027b  jns     short loc_1400502BB
0x14005027d  lea     rbx, WPP_GLOBAL_Control
0x140050284  mov     rcx, cs:WPP_GLOBAL_Control
0x14005028b  cmp     rcx, rbx
0x14005028e  jz      loc_1400504D9
0x140050294  test    [rcx+1Ch], r13b
0x140050298  jz      loc_1400504D9
0x14005029e  mov     edx, 19h
0x1400502a3  mov     r9d, eax
0x1400502a6  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x1400502ad  mov     rcx, [rcx+10h]
0x1400502b1  call    WPP_SF_d
0x1400502b6  jmp     loc_1400504D9
0x1400502bb  xor     edi, edi
0x1400502bd  mov     eax, edi
0x1400502bf  imul    rsi, rax, 238h
0x1400502c6  lea     rcx, [rbx+54h]
0x1400502ca  add     rcx, rsi
0x1400502cd  lea     rdx, aApprecorderver; "AppRecorderVersion"
0x1400502d4  call    cs:__imp__o__wcsicmp
0x1400502db  nop     dword ptr [rax+rax+00h]
0x1400502e0  test    eax, eax
0x1400502e2  jnz     short loc_1400502F2
0x1400502e4  cmp     [rsi+rbx+280h], r13d
0x1400502ec  ja      loc_1400504D7
0x1400502f2  add     edi, r13d
0x1400502f5  cmp     edi, 2
0x1400502f8  jb      short loc_1400502BD
0x1400502fa  mov     rdx, r15; void *
0x1400502fd  mov     rcx, rbx; this
0x140050300  call    ?PromptForEnableAppRecorder@CAppRecorderPlugin@@AEAAHPEAX@Z; CAppRecorderPlugin::PromptForEnableAppRecorder(void *)
0x140050305  test    eax, eax
0x140050307  jnz     short loc_14005033D
0x140050309  lea     rbx, WPP_GLOBAL_Control
0x140050310  mov     rcx, cs:WPP_GLOBAL_Control
0x140050317  cmp     rcx, rbx
0x14005031a  jz      short loc_140050335
0x14005031c  test    byte ptr [rcx+1Ch], 4
0x140050320  jz      short loc_140050335
0x140050322  lea     edx, [rax+1Ah]
0x140050325  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x14005032c  mov     rcx, [rcx+10h]
0x140050330  call    WPP_SF_
0x140050335  mov     edi, r13d
0x140050338  jmp     loc_1400504D9
0x14005033d  mov     rcx, rbx; this
0x140050340  call    ?WriteAppCompatLayer@CAppRecorderPlugin@@AEAAJXZ; CAppRecorderPlugin::WriteAppCompatLayer(void)
0x140050345  mov     edi, eax
0x140050347  test    eax, eax
0x140050349  jns     short loc_140050376
0x14005034b  lea     rbx, WPP_GLOBAL_Control
0x140050352  mov     rcx, cs:WPP_GLOBAL_Control
0x140050359  cmp     rcx, rbx
0x14005035c  jz      loc_1400504D9
0x140050362  test    [rcx+1Ch], r13b
0x140050366  jz      loc_1400504D9
0x14005036c  mov     edx, 1Bh
0x140050371  jmp     loc_1400502A3
0x140050376  lea     r9, aSoftwareMicros_9; "Software\\Microsoft\\Windows\\Windows E"...
0x14005037d  mov     rbx, 0FFFFFFFF80000001h
0x140050384  mov     r8, rbx; HKEY
0x140050387  mov     edx, 2; unsigned int
0x14005038c  mov     rcx, r14; struct _AUTOVERIFIER_IPT_SETTINGS *
0x14005038f  call    ?WerPluginWriteSettings@@YAJPEAU_AUTOVERIFIER_IPT_SETTINGS@@KPEAUHKEY__@@PEB_W@Z; WerPluginWriteSettings(_AUTOVERIFIER_IPT_SETTINGS *,ulong,HKEY__ *,wchar_t const *)
0x140050394  mov     edi, eax
0x140050396  test    eax, eax
0x140050398  jns     short loc_1400503C5
0x14005039a  lea     rbx, WPP_GLOBAL_Control
0x1400503a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400503a8  cmp     rcx, rbx
0x1400503ab  jz      loc_1400504D9
0x1400503b1  test    [rcx+1Ch], r13b
0x1400503b5  jz      loc_1400504D9
0x1400503bb  mov     edx, 1Ch
0x1400503c0  jmp     loc_1400502A3
0x1400503c5  lea     rcx, [rbp+hKey]
0x1400503c9  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1400503ce  lea     r8, [rbp+dwDisposition]
0x1400503d2  mov     [rsp+60h+lpdwDisposition], r8; lpdwDisposition
0x1400503d7  mov     [rsp+60h+phkResult], rax; phkResult
0x1400503dc  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1400503e5  mov     [rsp+60h+samDesired], 60002h; samDesired
0x1400503ed  mov     [rsp+60h+dwOptions], 0; dwOptions
0x1400503f5  xor     r9d, r9d; lpClass
0x1400503f8  xor     r8d, r8d; Reserved
0x1400503fb  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\Windows\\Windows E"...
0x140050402  mov     rcx, rbx; hKey
0x140050405  call    cs:__imp_RegCreateKeyExW
0x14005040c  nop     dword ptr [rax+rax+00h]
0x140050411  test    eax, eax
0x140050413  jz      short loc_140050440
0x140050415  lea     rbx, WPP_GLOBAL_Control
0x14005041c  mov     rcx, cs:WPP_GLOBAL_Control
0x140050423  cmp     rcx, rbx
0x140050426  jz      loc_1400504D9
0x14005042c  test    [rcx+1Ch], r13b
0x140050430  jz      loc_1400504D9
0x140050436  mov     edx, 1Dh
0x14005043b  jmp     loc_140050238
0x140050440  mov     r8d, 80010002h; unsigned int
0x140050446  mov     rcx, [rbp+hKey]; hKey
0x14005044a  call    ?WerPluginAdjustAppContainerAccessToKey@@YAJPEAUHKEY__@@W4_ACCESS_MODE@@K@Z; WerPluginAdjustAppContainerAccessToKey(HKEY__ *,_ACCESS_MODE,ulong)
0x14005044f  mov     edi, eax
0x140050451  lea     rbx, WPP_GLOBAL_Control
0x140050458  test    eax, eax
0x14005045a  jns     short loc_140050486
0x14005045c  mov     rcx, cs:WPP_GLOBAL_Control
0x140050463  cmp     rcx, rbx
0x140050466  jz      short loc_140050486
0x140050468  test    byte ptr [rcx+1Ch], 2
0x14005046c  jz      short loc_140050486
0x14005046e  mov     edx, 1Eh
0x140050473  mov     r9d, eax
0x140050476  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x14005047d  mov     rcx, [rcx+10h]
0x140050481  call    WPP_SF_d
0x140050486  mov     [rsp+60h+samDesired], 4; cbData
0x14005048e  lea     rax, [rbp+Data]
0x140050492  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x140050497  mov     r9d, 4; dwType
0x14005049d  xor     r8d, r8d; Reserved
0x1400504a0  lea     rdx, aApprecorderena; "AppRecorderEnabled"
0x1400504a7  mov     rcx, [rbp+hKey]; hKey
0x1400504ab  call    cs:__imp_RegSetValueExW
0x1400504b2  nop     dword ptr [rax+rax+00h]
0x1400504b7  test    eax, eax
0x1400504b9  jz      short loc_1400504D7
0x1400504bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400504c2  cmp     rcx, rbx
0x1400504c5  jz      short loc_1400504D9
0x1400504c7  test    [rcx+1Ch], r13b
0x1400504cb  jz      short loc_1400504D9
0x1400504cd  mov     edx, 1Fh
0x1400504d2  jmp     loc_140050238
0x1400504d7  xor     edi, edi
0x1400504d9  mov     rcx, [rbp+hKey]; hKey
0x1400504dd  test    rcx, rcx
0x1400504e0  jz      short loc_1400504EE
0x1400504e2  call    cs:__imp_RegCloseKey
0x1400504e9  nop     dword ptr [rax+rax+00h]
0x1400504ee  mov     eax, edi
0x1400504f0  jmp     short loc_1400504F4
0x1400504f2  xor     eax, eax
0x1400504f4  lea     r11, [rsp+60h+var_s0]
0x1400504f9  mov     rbx, [r11+30h]
0x1400504fd  mov     rsi, [r11+40h]
0x140050501  mov     rsp, r11
0x140050504  pop     r15
0x140050506  pop     r14
0x140050508  pop     r13
0x14005050a  pop     rdi
0x14005050b  pop     rbp
0x14005050c  retn
```
