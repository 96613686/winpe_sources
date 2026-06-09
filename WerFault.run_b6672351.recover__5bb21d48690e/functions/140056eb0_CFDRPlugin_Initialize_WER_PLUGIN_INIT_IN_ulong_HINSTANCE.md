# CFDRPlugin::Initialize(WER_PLUGIN_INIT_IN *,ulong,HINSTANCE__ *)

- ea: `0x140056eb0`
- end: `0x1400571b3`
- name: `?Initialize@CFDRPlugin@@UEAAJPEAUWER_PLUGIN_INIT_IN@@KPEAUHINSTANCE__@@@Z`
- size: `771`
- prototype: `__int64 __fastcall(CFDRPlugin *__hidden this, struct WER_PLUGIN_INIT_IN *, unsigned int, HINSTANCE)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x140002748`
- `0x14000ca20`
- `0x140014ee4`
- `0x140014f14`
- `0x1400166ec`
- `0x140056eb0`
- `0x140057940`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140056f4f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140056f6d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140056f8b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140056fa5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140056fbf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140056fd9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005712a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140056f4f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140056f6d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140056f8b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140056fa5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140056fbf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140056fd9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005712a`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140057082`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140057082`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFDRPlugin::Initialize(CFDRPlugin *this, struct WER_PLUGIN_INIT_IN *a2, __int64 a3, HINSTANCE a4)
{
  _WORD *v7; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned int v13; // ebx
  CUserModeHangReport *v14; // rcx
  __int64 v15; // rdx
  int v16; // eax
  __int64 v17; // r15
  _QWORD *v18; // r14
  DWORD ProcessId; // eax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // r8
  __int64 v25; // rcx
  __int64 v26; // r8
  void *v27[2]; // [rsp+20h] [rbp-20h] BYREF
  _WORD v28[8]; // [rsp+30h] [rbp-10h] BYREF
  int v29; // [rsp+78h] [rbp+38h] BYREF

  v7 = v28;
  v27[0] = v28;
  v27[1] = v28;
  v28[0] = 0;
  v29 = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_928a4490cd403d1d5470036a68085293_Traceguids);
      v7 = v27[0];
    }
    if ( v7 != v28 )
      operator delete(v7, (const struct std::nothrow_t *)&std::nothrow);
    return 2147942487LL;
  }
  if ( !(unsigned int)_o__wcsicmp(*(_QWORD *)a2, L"APPCRASH", a3)
    || !(unsigned int)_o__wcsicmp(*(_QWORD *)a2, L"MoAppCrash", v11)
    || !(unsigned int)_o__wcsicmp(*(_QWORD *)a2, L"AppHangB1", v11)
    || !(unsigned int)_o__wcsicmp(*(_QWORD *)a2, L"AppHangXProcB1", v11)
    || !(unsigned int)_o__wcsicmp(*(_QWORD *)a2, L"MoAppHang", v11)
    || !(unsigned int)_o__wcsicmp(*(_QWORD *)a2, L"MoAppHangXProc", v11) )
  {
    *((_QWORD *)this + 8) = a4;
    if ( (unsigned int)(*((_DWORD *)a2 + 63) - 1) > 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v10, v9, v11, v12);
    v16 = *((_DWORD *)a2 + 63);
    if ( v16 == 1 )
    {
      v17 = *((_QWORD *)a2 + 33);
      v18 = (_QWORD *)((char *)this + 40);
      *((_QWORD *)this + 5) = *((_QWORD *)a2 + 38);
      *((_DWORD *)this + 12) = *((_DWORD *)a2 + 70);
    }
    else
    {
      if ( v16 != 2 )
      {
LABEL_37:
        v13 = -2147024809;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_41;
        }
        v15 = 12;
        goto LABEL_40;
      }
      v17 = *((_QWORD *)a2 + 32);
      v18 = (_QWORD *)((char *)this + 40);
      *((_QWORD *)this + 5) = *((_QWORD *)a2 + 33);
      ProcessId = GetProcessId(*((HANDLE *)a2 + 33));
      *((_DWORD *)this + 12) = ProcessId;
      if ( !ProcessId )
        MicrosoftTelemetryAssertTriggeredNoArgs(v21, v20, v22, v23);
    }
    if ( v17 && *v18 )
    {
      v24 = -1;
      do
        ++v24;
      while ( *(_WORD *)(v17 + 2 * v24) );
      if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                              (char *)this + 8,
                              v17) )
      {
        if ( (int)CFDRPlugin::ReadFDRSessionSettings(v25, (char *)this + 80, v27, &v29) >= 0 )
        {
          *((_DWORD *)this + 18) = 1;
          if ( !(unsigned int)_o__wcsicmp(*((_QWORD *)this + 1), v27[0], v26) && *((_DWORD *)this + 12) == v29 )
            *((_DWORD *)this + 19) = 1;
        }
        v13 = 0;
      }
      else
      {
        v13 = -2147024882;
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            WPP_928a4490cd403d1d5470036a68085293_Traceguids,
            2147942414LL);
        }
      }
      goto LABEL_41;
    }
    goto LABEL_37;
  }
  v13 = -2147467263;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
  {
    goto LABEL_41;
  }
  v15 = 11;
LABEL_40:
  WPP_SF_(*((_QWORD *)v14 + 2), v15, WPP_928a4490cd403d1d5470036a68085293_Traceguids);
LABEL_41:
  if ( v27[0] != v28 )
    operator delete(v27[0], (const struct std::nothrow_t *)&std::nothrow);
  return v13;
}

```

## disassembly

```asm
0x140056eb0  mov     [rsp-28h+arg_0], rbx
0x140056eb5  mov     [rsp-28h+arg_10], rsi
0x140056eba  push    rbp
0x140056ebb  push    rdi
0x140056ebc  push    r12
0x140056ebe  push    r14
0x140056ec0  push    r15
0x140056ec2  mov     rbp, rsp
0x140056ec5  sub     rsp, 40h
0x140056ec9  mov     rdi, r9
0x140056ecc  mov     rbx, rdx
0x140056ecf  mov     rsi, rcx
0x140056ed2  lea     rcx, [rbp+var_10]
0x140056ed6  mov     [rbp+var_20], rcx
0x140056eda  lea     rax, [rbp+var_10]
0x140056ede  mov     [rbp+var_18], rax
0x140056ee2  xor     r12d, r12d
0x140056ee5  mov     [rbp+var_10], r12w
0x140056eea  mov     [rbp+arg_8], r12d
0x140056eee  test    rdx, rdx
0x140056ef1  jnz     short loc_140056F45
0x140056ef3  lea     rax, WPP_GLOBAL_Control
0x140056efa  mov     r9, cs:WPP_GLOBAL_Control
0x140056f01  cmp     r9, rax
0x140056f04  jz      short loc_140056F26
0x140056f06  lea     edi, [rdx+1]
0x140056f09  test    [r9+1Ch], dil
0x140056f0d  jz      short loc_140056F26
0x140056f0f  lea     edx, [rbx+0Ah]
0x140056f12  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x140056f19  mov     rcx, [r9+10h]
0x140056f1d  call    WPP_SF_
0x140056f22  mov     rcx, [rbp+var_20]; void *
0x140056f26  lea     rax, [rbp+var_10]
0x140056f2a  cmp     rcx, rax
0x140056f2d  jz      short loc_140056F3B
0x140056f2f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140056f36  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140056f3b  mov     eax, 80070057h
0x140056f40  jmp     loc_140057199
0x140056f45  lea     rdx, aAppcrash; "APPCRASH"
0x140056f4c  mov     rcx, [rbx]
0x140056f4f  call    cs:__imp__o__wcsicmp
0x140056f56  nop     dword ptr [rax+rax+00h]
0x140056f5b  test    eax, eax
0x140056f5d  jz      loc_140057019
0x140056f63  lea     rdx, aMoappcrash; "MoAppCrash"
0x140056f6a  mov     rcx, [rbx]
0x140056f6d  call    cs:__imp__o__wcsicmp
0x140056f74  nop     dword ptr [rax+rax+00h]
0x140056f79  test    eax, eax
0x140056f7b  jz      loc_140057019
0x140056f81  lea     rdx, aApphangb1; "AppHangB1"
0x140056f88  mov     rcx, [rbx]
0x140056f8b  call    cs:__imp__o__wcsicmp
0x140056f92  nop     dword ptr [rax+rax+00h]
0x140056f97  test    eax, eax
0x140056f99  jz      short loc_140057019
0x140056f9b  lea     rdx, aApphangxprocb1; "AppHangXProcB1"
0x140056fa2  mov     rcx, [rbx]
0x140056fa5  call    cs:__imp__o__wcsicmp
0x140056fac  nop     dword ptr [rax+rax+00h]
0x140056fb1  test    eax, eax
0x140056fb3  jz      short loc_140057019
0x140056fb5  lea     rdx, aMoapphang; "MoAppHang"
0x140056fbc  mov     rcx, [rbx]
0x140056fbf  call    cs:__imp__o__wcsicmp
0x140056fc6  nop     dword ptr [rax+rax+00h]
0x140056fcb  test    eax, eax
0x140056fcd  jz      short loc_140057019
0x140056fcf  lea     rdx, aMoapphangxproc; "MoAppHangXProc"
0x140056fd6  mov     rcx, [rbx]
0x140056fd9  call    cs:__imp__o__wcsicmp
0x140056fe0  nop     dword ptr [rax+rax+00h]
0x140056fe5  test    eax, eax
0x140056fe7  jz      short loc_140057019
0x140056fe9  mov     ebx, 80004001h
0x140056fee  lea     rax, WPP_GLOBAL_Control
0x140056ff5  mov     rcx, cs:WPP_GLOBAL_Control
0x140056ffc  cmp     rcx, rax
0x140056fff  jz      loc_14005717E
0x140057005  test    byte ptr [rcx+1Ch], 4
0x140057009  jz      loc_14005717E
0x14005700f  mov     edx, 0Bh
0x140057014  jmp     loc_14005716D
0x140057019  mov     [rsi+40h], rdi
0x14005701d  mov     eax, [rbx+0FCh]
0x140057023  mov     edi, 1
0x140057028  sub     eax, edi
0x14005702a  cmp     eax, edi
0x14005702c  jbe     short loc_140057033
0x14005702e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140057033  mov     eax, [rbx+0FCh]
0x140057039  cmp     eax, edi
0x14005703b  jnz     short loc_14005705D
0x14005703d  mov     r15, [rbx+108h]
0x140057044  lea     r14, [rsi+28h]
0x140057048  mov     rax, [rbx+130h]
0x14005704f  mov     [r14], rax
0x140057052  mov     eax, [rbx+118h]
0x140057058  mov     [rsi+30h], eax
0x14005705b  jmp     short loc_14005709A
0x14005705d  cmp     eax, 2
0x140057060  jnz     loc_14005714A
0x140057066  mov     r15, [rbx+100h]
0x14005706d  lea     r14, [rsi+28h]
0x140057071  mov     rax, [rbx+108h]
0x140057078  mov     [r14], rax
0x14005707b  mov     rcx, [rbx+108h]; Process
0x140057082  call    cs:__imp_GetProcessId
0x140057089  nop     dword ptr [rax+rax+00h]
0x14005708e  mov     [rsi+30h], eax
0x140057091  test    eax, eax
0x140057093  jnz     short loc_14005709A
0x140057095  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14005709a  test    r15, r15
0x14005709d  jz      loc_14005714A
0x1400570a3  cmp     [r14], r12
0x1400570a6  jz      loc_14005714A
0x1400570ac  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400570b0  inc     r8
0x1400570b3  cmp     [r15+r8*2], r12w
0x1400570b8  jnz     short loc_1400570B0
0x1400570ba  mov     rdx, r15
0x1400570bd  lea     rcx, [rsi+8]
0x1400570c1  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1400570c6  test    al, al
0x1400570c8  jnz     short loc_14005710A
0x1400570ca  mov     ebx, 8007000Eh
0x1400570cf  lea     rax, WPP_GLOBAL_Control
0x1400570d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400570dd  cmp     rcx, rax
0x1400570e0  jz      loc_14005717E
0x1400570e6  test    [rcx+1Ch], dil
0x1400570ea  jz      loc_14005717E
0x1400570f0  mov     edx, 0Dh
0x1400570f5  mov     r9d, ebx
0x1400570f8  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x1400570ff  mov     rcx, [rcx+10h]
0x140057103  call    WPP_SF_d
0x140057108  jmp     short loc_14005717E
0x14005710a  lea     rdx, [rsi+50h]
0x14005710e  lea     r9, [rbp+arg_8]
0x140057112  lea     r8, [rbp+var_20]
0x140057116  call    ?ReadFDRSessionSettings@CFDRPlugin@@AEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@0PEAK@Z; CFDRPlugin::ReadFDRSessionSettings(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,ulong *)
0x14005711b  test    eax, eax
0x14005711d  js      short loc_140057145
0x14005711f  mov     [rsi+48h], edi
0x140057122  mov     rdx, [rbp+var_20]
0x140057126  mov     rcx, [rsi+8]
0x14005712a  call    cs:__imp__o__wcsicmp
0x140057131  nop     dword ptr [rax+rax+00h]
0x140057136  test    eax, eax
0x140057138  jnz     short loc_140057145
0x14005713a  mov     eax, [rbp+arg_8]
0x14005713d  cmp     [rsi+30h], eax
0x140057140  jnz     short loc_140057145
0x140057142  mov     [rsi+4Ch], edi
0x140057145  mov     ebx, r12d
0x140057148  jmp     short loc_14005717E
0x14005714a  mov     ebx, 80070057h
0x14005714f  lea     rax, WPP_GLOBAL_Control
0x140057156  mov     rcx, cs:WPP_GLOBAL_Control
0x14005715d  cmp     rcx, rax
0x140057160  jz      short loc_14005717E
0x140057162  test    [rcx+1Ch], dil
0x140057166  jz      short loc_14005717E
0x140057168  mov     edx, 0Ch
0x14005716d  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x140057174  mov     rcx, [rcx+10h]
0x140057178  call    WPP_SF_
0x14005717d  nop
0x14005717e  lea     rax, [rbp+var_10]
0x140057182  mov     rcx, [rbp+var_20]; void *
0x140057186  cmp     rcx, rax
0x140057189  jz      short loc_140057197
0x14005718b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140057192  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140057197  mov     eax, ebx
0x140057199  lea     r11, [rsp+40h+var_s0]
0x14005719e  mov     rbx, [r11+30h]
0x1400571a2  mov     rsi, [r11+40h]
0x1400571a6  mov     rsp, r11
0x1400571a9  pop     r15
0x1400571ab  pop     r14
0x1400571ad  pop     r12
0x1400571af  pop     rdi
0x1400571b0  pop     rbp
0x1400571b1  retn
```
