# DllMain

- ea: `0x18001cd2c`
- end: `0x18001cea7`
- name: `DllMain`
- size: `379`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009334`

## callees

- `0x18001b1fc`
- `0x18001cd2c`
- `0x18001cfb8`
- `0x18001cfdc`
- `0x18001d00c`
- `0x18001d1d8`
- `0x1800269d0`
- `0x180029390`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001cd44`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001cd44`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x18001ce79`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x18001ce79`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 v3; // rdx
  __int64 v4; // rdx
  __int64 v5; // rdx
  __int64 v6; // r8
  _QWORD *v7; // rdi
  TRACEHANDLE v8; // rcx

  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    qword_1801669D0 = 1;
    qword_1801669C8 = 0;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_CamTraceGuid;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    WPP_MAIN_CB = 0;
    WppInitUm();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_a085755983d436597dfcab6caa67f458_Traceguids);
    }
    McGenEventRegister_EventRegister(
      MICROSOFT_WINDOWS_PRIVACY_AUDITING_PROVIDER,
      v3,
      MICROSOFT_WINDOWS_PRIVACY_AUDITING_PROVIDER_Context,
      MICROSOFT_WINDOWS_PRIVACY_AUDITING_PROVIDER_Context);
    McGenEventRegister_EventRegister(
      MICROSOFT_WINDOWS_PRIVACY_AUDITING_PERMISSIVELEARNINGMODE_PROVIDER,
      v4,
      MICROSOFT_WINDOWS_PRIVACY_AUDITING_PERMISSIVELEARNINGMODE_PROVIDER_Context,
      MICROSOFT_WINDOWS_PRIVACY_AUDITING_PERMISSIVELEARNINGMODE_PROVIDER_Context);
    InitializeAggregateTraceLogging();
    wil::SetResultLoggingCallback(lambda_59397f8b17d4f775205943cd52eba03c_::_lambda_invoker_cdecl_);
  }
  else if ( !fdwReason )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_a085755983d436597dfcab6caa67f458_Traceguids);
    }
    wil::details::g_pfnLoggingCallback = 0;
    McGenEventUnregister_EventUnregister(
      MICROSOFT_WINDOWS_PRIVACY_AUDITING_PROVIDER_Context,
      *(_QWORD *)&fdwReason,
      lpvReserved);
    McGenEventUnregister_EventUnregister(
      MICROSOFT_WINDOWS_PRIVACY_AUDITING_PERMISSIVELEARNINGMODE_PROVIDER_Context,
      v5,
      v6);
    UninitializeAggregateTraceLogging();
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      while ( v7 )
      {
        v8 = v7[1];
        if ( v8 )
        {
          UnregisterTraceGuids(v8);
          v7[1] = 0;
        }
        v7 = (_QWORD *)*v7;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18001cd2c  mov     [rsp+arg_0], rbx
0x18001cd31  mov     [rsp+arg_8], rsi
0x18001cd36  push    rdi
0x18001cd37  sub     rsp, 20h
0x18001cd3b  cmp     edx, 1
0x18001cd3e  jnz     loc_18001CE02
0x18001cd44  call    cs:__imp_DisableThreadLibraryCalls
0x18001cd4a  xor     ebx, ebx
0x18001cd4c  mov     cs:qword_1801669D0, 1
0x18001cd57  lea     rax, WPP_ThisDir_CTLGUID_CamTraceGuid
0x18001cd5e  mov     cs:qword_1801669C8, rbx
0x18001cd65  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18001cd6c  lea     rax, WPP_MAIN_CB
0x18001cd73  mov     cs:WPP_GLOBAL_Control, rax
0x18001cd7a  mov     cs:WPP_MAIN_CB, rbx
0x18001cd81  call    WppInitUm
0x18001cd86  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd8d  lea     rsi, WPP_GLOBAL_Control
0x18001cd94  cmp     rcx, rsi
0x18001cd97  jz      short loc_18001CDB8
0x18001cd99  test    byte ptr [rcx+1Ch], 1
0x18001cd9d  jz      short loc_18001CDB8
0x18001cd9f  cmp     byte ptr [rcx+19h], 4
0x18001cda3  jb      short loc_18001CDB8
0x18001cda5  mov     rcx, [rcx+10h]
0x18001cda9  lea     edx, [rbx+0Ah]
0x18001cdac  lea     r8, WPP_a085755983d436597dfcab6caa67f458_Traceguids
0x18001cdb3  call    WPP_SF_
0x18001cdb8  lea     r9, MICROSOFT_WINDOWS_PRIVACY_AUDITING_PROVIDER_Context
0x18001cdbf  lea     r8, MICROSOFT_WINDOWS_PRIVACY_AUDITING_PROVIDER_Context
0x18001cdc6  lea     rcx, MICROSOFT_WINDOWS_PRIVACY_AUDITING_PROVIDER
0x18001cdcd  call    McGenEventRegister_EventRegister
0x18001cdd2  lea     r9, MICROSOFT_WINDOWS_PRIVACY_AUDITING_PERMISSIVELEARNINGMODE_PROVIDER_Context
0x18001cdd9  lea     r8, MICROSOFT_WINDOWS_PRIVACY_AUDITING_PERMISSIVELEARNINGMODE_PROVIDER_Context
0x18001cde0  lea     rcx, MICROSOFT_WINDOWS_PRIVACY_AUDITING_PERMISSIVELEARNINGMODE_PROVIDER
0x18001cde7  call    McGenEventRegister_EventRegister
0x18001cdec  call    ?InitializeAggregateTraceLogging@@YAXXZ; InitializeAggregateTraceLogging(void)
0x18001cdf1  lea     rcx, _lambda_59397f8b17d4f775205943cd52eba03c____lambda_invoker_cdecl_
0x18001cdf8  call    ?SetResultLoggingCallback@wil@@YAXP6AXAEBUFailureInfo@1@@_E@Z; wil::SetResultLoggingCallback(void (*)(wil::FailureInfo const &),...)
0x18001cdfd  jmp     loc_18001CE92
0x18001ce02  xor     ebx, ebx
0x18001ce04  test    edx, edx
0x18001ce06  jnz     loc_18001CE92
0x18001ce0c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce13  lea     rsi, WPP_GLOBAL_Control
0x18001ce1a  cmp     rcx, rsi
0x18001ce1d  jz      short loc_18001CE3E
0x18001ce1f  test    byte ptr [rcx+1Ch], 1
0x18001ce23  jz      short loc_18001CE3E
0x18001ce25  cmp     byte ptr [rcx+19h], 4
0x18001ce29  jb      short loc_18001CE3E
0x18001ce2b  mov     rcx, [rcx+10h]
0x18001ce2f  lea     edx, [rbx+0Ch]
0x18001ce32  lea     r8, WPP_a085755983d436597dfcab6caa67f458_Traceguids
0x18001ce39  call    WPP_SF_
0x18001ce3e  lea     rcx, MICROSOFT_WINDOWS_PRIVACY_AUDITING_PROVIDER_Context
0x18001ce45  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, rbx
0x18001ce4c  call    McGenEventUnregister_EventUnregister
0x18001ce51  lea     rcx, MICROSOFT_WINDOWS_PRIVACY_AUDITING_PERMISSIVELEARNINGMODE_PROVIDER_Context
0x18001ce58  call    McGenEventUnregister_EventUnregister
0x18001ce5d  call    ?UninitializeAggregateTraceLogging@@YAXXZ; UninitializeAggregateTraceLogging(void)
0x18001ce62  mov     rdi, cs:WPP_GLOBAL_Control
0x18001ce69  cmp     rdi, rsi
0x18001ce6c  jz      short loc_18001CE92
0x18001ce6e  jmp     short loc_18001CE86
0x18001ce70  mov     rcx, [rdi+8]; RegistrationHandle
0x18001ce74  test    rcx, rcx
0x18001ce77  jz      short loc_18001CE83
0x18001ce79  call    cs:__imp_UnregisterTraceGuids
0x18001ce7f  mov     [rdi+8], rbx
0x18001ce83  mov     rdi, [rdi]
0x18001ce86  test    rdi, rdi
0x18001ce89  jnz     short loc_18001CE70
0x18001ce8b  mov     cs:WPP_GLOBAL_Control, rsi
0x18001ce92  mov     rbx, [rsp+28h+arg_0]
0x18001ce97  mov     eax, 1
0x18001ce9c  mov     rsi, [rsp+28h+arg_8]
0x18001cea1  add     rsp, 20h
0x18001cea5  pop     rdi
0x18001cea6  retn
```
