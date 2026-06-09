# CLogonController::_SetLockScreenActiveLockHeld(bool,bool,bool)

- ea: `0x180019330`
- end: `0x180019514`
- name: `?_SetLockScreenActiveLockHeld@CLogonController@@AEAAJ_N00@Z`
- size: `484`
- prototype: `__int64 __fastcall(CLogonController *__hidden this, bool, bool, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180019520`
- `0x18005b514`

## callees

- `0x18000e750`
- `0x180017e44`
- `0x180019330`
- `0x18005d488`
- `0x1800735f0`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800194a5`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800194a5`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180019471`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180019471`
- `ntdll!RtlPublishWnfStateData` at `0x180019423`
- `ntdll!RtlPublishWnfStateData` at `0x180019423`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180019378`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180019395`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1800193f5`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180019378`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180019395`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1800193f5`

## pseudocode

```c
__int64 __fastcall CLogonController::_SetLockScreenActiveLockHeld(
        CLogonController *this,
        unsigned __int8 a2,
        char a3,
        char a4)
{
  int v4; // edi
  unsigned int v7; // ebx
  int v9; // eax
  unsigned int v10; // edi
  __int64 v11; // rdi
  char v12; // bp
  unsigned int v13; // ebx
  int v14; // eax
  int v15; // [rsp+20h] [rbp-38h]
  int v16; // [rsp+20h] [rbp-38h]
  int v17; // [rsp+20h] [rbp-38h]
  int pvParam; // [rsp+30h] [rbp-28h] BYREF
  _DWORD v19[9]; // [rsp+34h] [rbp-24h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  char v21; // [rsp+68h] [rbp+10h] BYREF

  v4 = a2;
  if ( a2 )
  {
    if ( a3 && !*((_BYTE *)this + 272) )
    {
      if ( !SystemParametersInfoW(0xABu, 1u, 0, 0) )
      {
        pvParam = 0;
        SystemParametersInfoW(0xAAu, 0, &pvParam, 0);
        if ( !pvParam )
        {
          v7 = -2147024809;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBE2,
            (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
            (const char *)0x80070057LL,
            v15);
          v21 = 1;
          LogonControllerTelemetry::FailedToSetLockScreenHardening<bool>(&v21);
          return v7;
        }
      }
      *((_BYTE *)this + 272) = 1;
    }
  }
  else if ( *((_BYTE *)this + 272) )
  {
    SystemParametersInfoW(0xABu, 0, 0, 0);
    *((_BYTE *)this + 272) = 0;
  }
  v19[0] = v4;
  v9 = RtlPublishWnfStateData(WNF_SHEL_LOCKSCREEN_ACTIVE, 0, v19, 4, 0);
  v10 = v9 | 0x10000000;
  if ( v9 >= 0 )
  {
    LogonControllerTelemetry::PublishedLockScreenActiveWNF<unsigned long &>(v19);
    v11 = *((_QWORD *)this + 18);
    v12 = 0;
    AcquireSRWLockExclusive((PSRWLOCK)(v11 + 504));
    v13 = *(_DWORD *)(v11 + 512);
    if ( (v13 & 0x20000) == 0 && a4 != ((*(_DWORD *)(v11 + 512) & 0x200) != 0) )
    {
      v13 ^= 0x200u;
      v12 = 1;
      *(_DWORD *)(v11 + 512) = v13;
    }
    if ( v11 != -504 )
      ReleaseSRWLockExclusive((PSRWLOCK)(v11 + 504));
    if ( v12 )
    {
      v14 = Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::CredProvData::IDisplayStateProvider *,enum Windows::Internal::UI::Logon::CredProvData::DisplayStateFlags>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<CProcessStateManager *,enum Windows::Internal::UI::Logon::CredProvData::DisplayStateFlags>(
              v11 + 480,
              v11,
              v13);
      v7 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x57A,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\processstatemanager.cpp",
          (const char *)(unsigned int)v14,
          v16);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xBF9,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
          (const char *)v7,
          v17);
        return v7;
      }
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBF7,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)v10,
      v16);
    return v10;
  }
}

```

## disassembly

```asm
0x180019330  mov     [rsp+arg_0], rbx
0x180019335  mov     [rsp+arg_10], rbp
0x18001933a  push    rsi
0x18001933b  push    rdi
0x18001933c  push    r14
0x18001933e  sub     rsp, 40h
0x180019342  movzx   edi, dl
0x180019345  mov     r14b, r9b
0x180019348  mov     rbx, rcx
0x18001934b  test    dl, dl
0x18001934d  jz      loc_1800193DF
0x180019353  test    r8b, r8b
0x180019356  jz      loc_180019402
0x18001935c  cmp     byte ptr [rcx+110h], 0
0x180019363  jnz     loc_180019402
0x180019369  xor     r9d, r9d; fWinIni
0x18001936c  xor     r8d, r8d; pvParam
0x18001936f  mov     ecx, 0ABh; uiAction
0x180019374  lea     edx, [r9+1]; uiParam
0x180019378  call    cs:__imp_SystemParametersInfoW
0x18001937e  test    eax, eax
0x180019380  jnz     short loc_1800193D6
0x180019382  xor     r9d, r9d; fWinIni
0x180019385  mov     [rsp+58h+pvParam], eax
0x180019389  lea     r8, [rsp+58h+pvParam]; pvParam
0x18001938e  xor     edx, edx; uiParam
0x180019390  mov     ecx, 0AAh; uiAction
0x180019395  call    cs:__imp_SystemParametersInfoW
0x18001939b  cmp     [rsp+58h+pvParam], 0
0x1800193a0  jnz     short loc_1800193D6
0x1800193a2  mov     rcx, [rsp+58h]; this
0x1800193a7  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x1800193ae  mov     ebx, 80070057h
0x1800193b3  mov     edx, 0BE2h; void *
0x1800193b8  mov     r9d, ebx; char *
0x1800193bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800193c0  lea     rcx, [rsp+58h+arg_8]
0x1800193c5  mov     [rsp+58h+arg_8], 1
0x1800193ca  call    ??$FailedToSetLockScreenHardening@_N@LogonControllerTelemetry@@SAX$$QEA_N@Z; LogonControllerTelemetry::FailedToSetLockScreenHardening<bool>(bool &&)
0x1800193cf  mov     eax, ebx
0x1800193d1  jmp     loc_180019501
0x1800193d6  mov     byte ptr [rbx+110h], 1
0x1800193dd  jmp     short loc_180019402
0x1800193df  cmp     byte ptr [rcx+110h], 0
0x1800193e6  jz      short loc_180019402
0x1800193e8  xor     r9d, r9d; fWinIni
0x1800193eb  xor     r8d, r8d; pvParam
0x1800193ee  xor     edx, edx; uiParam
0x1800193f0  mov     ecx, 0ABh; uiAction
0x1800193f5  call    cs:__imp_SystemParametersInfoW
0x1800193fb  mov     byte ptr [rbx+110h], 0
0x180019402  mov     rcx, cs:WNF_SHEL_LOCKSCREEN_ACTIVE
0x180019409  lea     r8, [rsp+58h+var_24]
0x18001940e  mov     r9d, 4
0x180019414  mov     [rsp+58h+var_24], edi
0x180019418  xor     edx, edx
0x18001941a  mov     qword ptr [rsp+58h+var_38], 0; int
0x180019423  call    cs:__imp_RtlPublishWnfStateData
0x180019429  mov     edi, eax
0x18001942b  or      edi, 10000000h
0x180019431  jge     short loc_180019453
0x180019433  mov     rcx, [rsp+58h]; this
0x180019438  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x18001943f  mov     r9d, edi; char *
0x180019442  mov     edx, 0BF7h; void *
0x180019447  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001944c  mov     eax, edi
0x18001944e  jmp     loc_180019501
0x180019453  lea     rcx, [rsp+58h+var_24]
0x180019458  call    ??$PublishedLockScreenActiveWNF@AEAK@LogonControllerTelemetry@@SAXAEAK@Z; LogonControllerTelemetry::PublishedLockScreenActiveWNF<ulong &>(ulong &)
0x18001945d  mov     rdi, [rbx+90h]
0x180019464  xor     bpl, bpl
0x180019467  lea     rsi, [rdi+1F8h]
0x18001946e  mov     rcx, rsi; SRWLock
0x180019471  call    cs:__imp_AcquireSRWLockExclusive
0x180019477  mov     ebx, [rdi+200h]
0x18001947d  bt      ebx, 11h
0x180019481  jb      short loc_18001949D
0x180019483  mov     ecx, ebx
0x180019485  shr     ecx, 9
0x180019488  and     ecx, 1
0x18001948b  cmp     r14b, cl
0x18001948e  jz      short loc_18001949D
0x180019490  btc     ebx, 9
0x180019494  mov     bpl, 1
0x180019497  mov     [rdi+200h], ebx
0x18001949d  test    rsi, rsi
0x1800194a0  jz      short loc_1800194AB
0x1800194a2  mov     rcx, rsi; SRWLock
0x1800194a5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800194ab  test    bpl, bpl
0x1800194ae  jz      short loc_1800194FF
0x1800194b0  lea     rcx, [rdi+1E0h]
0x1800194b7  mov     r8d, ebx
0x1800194ba  mov     rdx, rdi
0x1800194bd  call    ??$InvokeAll@PEAVCProcessStateManager@@W4DisplayStateFlags@CredProvData@Logon@UI@Internal@Windows@@@?$EventSource@U?$ITypedEventHandler@PEAUIDisplayStateProvider@CredProvData@Logon@UI@Internal@Windows@@W4DisplayStateFlags@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJPEAVCProcessStateManager@@W4DisplayStateFlags@CredProvData@Logon@UI@Internal@Windows@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::CredProvData::IDisplayStateProvider *,Windows::Internal::UI::Logon::CredProvData::DisplayStateFlags>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<CProcessStateManager *,Windows::Internal::UI::Logon::CredProvData::DisplayStateFlags>(CProcessStateManager *,Windows::Internal::UI::Logon::CredProvData::DisplayStateFlags)
0x1800194c2  mov     ebx, eax
0x1800194c4  test    eax, eax
0x1800194c6  jns     short loc_1800194FF
0x1800194c8  mov     rcx, [rsp+58h]; this
0x1800194cd  lea     r8, aPcshellShellAu_8; "pcshell\\shell\\auth\\authux\\controlle"...
0x1800194d4  mov     r9d, eax; char *
0x1800194d7  mov     edx, 57Ah; void *
0x1800194dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800194e1  mov     rcx, [rsp+58h]; this
0x1800194e6  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x1800194ed  mov     r9d, ebx; char *
0x1800194f0  mov     edx, 0BF9h; void *
0x1800194f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800194fa  jmp     loc_1800193CF
0x1800194ff  xor     eax, eax
0x180019501  mov     rbx, [rsp+58h+arg_0]
0x180019506  mov     rbp, [rsp+58h+arg_10]
0x18001950b  add     rsp, 40h
0x18001950f  pop     r14
0x180019511  pop     rdi
0x180019512  pop     rsi
0x180019513  retn
```
