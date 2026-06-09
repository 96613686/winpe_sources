# SecurityBrokerTelemetry::LogACGDxDriverTelemetry(int)

- ea: `0x18000448c`
- end: `0x1800045e8`
- name: `?LogACGDxDriverTelemetry@SecurityBrokerTelemetry@@SAXH@Z`
- size: `348`
- prototype: `void __fastcall(int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180003060`

## callees

- `0x18000113c`
- `0x180001f97`
- `0x18000448c`
- `0x180004828`
- `0x180004870`
- `0x1800048e0`
- `0x180006980`
- `0x180007010`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180004552`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180004552`

## pseudocode

```c
void __fastcall SecurityBrokerTelemetry::LogACGDxDriverTelemetry(int a1)
{
  unsigned __int64 CurrentTimeInMs; // rdi
  unsigned __int64 NextLogTimeInMs; // r8
  __int64 v4; // rbx
  __int64 CLSID; // rax
  char v6; // [rsp+30h] [rbp-49h] BYREF
  int v7; // [rsp+34h] [rbp-45h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+40h] [rbp-39h] BYREF
  __int64 v9; // [rsp+60h] [rbp-19h]
  __int64 v10; // [rsp+68h] [rbp-11h]
  __int64 v11; // [rsp+70h] [rbp-9h]
  __int64 v12; // [rsp+78h] [rbp-1h]
  char *v13; // [rsp+80h] [rbp+7h]
  __int64 v14; // [rsp+88h] [rbp+Fh]
  int *v15; // [rsp+90h] [rbp+17h]
  __int64 v16; // [rsp+98h] [rbp+1Fh]

  CurrentTimeInMs = BrowserDataLogger::Util::GetCurrentTimeInMs();
  NextLogTimeInMs = BrowserDataLogger::Util::GetNextLogTimeInMs((__int64 *)SettingStore::IEVALUE_CodeIntegrity_NextTelemetryLogTime);
  if ( NextLogTimeInMs > CurrentTimeInMs + 60000 )
  {
    if ( NextLogTimeInMs > CurrentTimeInMs + 21600000 )
      BrowserDataLogger::Util::UpdateNextLogTime((__int64 *)SettingStore::IEVALUE_CodeIntegrity_NextTelemetryLogTime);
  }
  else
  {
    BrowserDataLogger::Util::UpdateNextLogTime((__int64 *)SettingStore::IEVALUE_CodeIntegrity_NextTelemetryLogTime);
    if ( (unsigned int)dword_18000C080 > 5
      && (qword_18000C090 & 0x400000000000LL) != 0
      && (qword_18000C098 & 0x400000000000LL) == qword_18000C098 )
    {
      v7 = a1;
      v6 = 1;
      InitOnceExecuteOnce_0(&g_InitOnce, LoadIsoDll, 0, 0);
      v4 = ((__int64 (*)(void))qword_18000F008)();
      CLSID = IEConfiguration_GetCLSID(268435459);
      v16 = 4;
      v15 = &v7;
      v9 = CLSID;
      v13 = &v6;
      v14 = 1;
      v11 = v4;
      v12 = 16;
      v10 = 16;
      tlgWriteTransfer_BrowserWriteTransfer((__int64)&dword_18000C080, (unsigned __int8 *)byte_1800097B9, 0, 0, 6u, &v8);
    }
  }
}

```

## disassembly

```asm
0x18000448c  push    rbp
0x18000448e  push    rbx
0x18000448f  push    rsi
0x180004490  push    rdi
0x180004491  lea     rbp, [rsp-3Fh]
0x180004496  sub     rsp, 0B8h
0x18000449d  mov     rax, cs:__security_cookie
0x1800044a4  xor     rax, rsp
0x1800044a7  mov     [rbp+57h+var_30], rax
0x1800044ab  mov     rbx, cs:?IEVALUE_CodeIntegrity_NextTelemetryLogTime@SettingStore@@3U?$VALUEID@PEAE@1@B; SettingStore::VALUEID<uchar *> const SettingStore::IEVALUE_CodeIntegrity_NextTelemetryLogTime
0x1800044b2  mov     esi, ecx
0x1800044b4  call    ?GetCurrentTimeInMs@Util@BrowserDataLogger@@CA_KXZ; BrowserDataLogger::Util::GetCurrentTimeInMs(void)
0x1800044b9  mov     rcx, rbx
0x1800044bc  mov     rdi, rax
0x1800044bf  call    ?GetNextLogTimeInMs@Util@BrowserDataLogger@@CA_KU?$VALUEID@PEAE@SettingStore@@@Z; BrowserDataLogger::Util::GetNextLogTimeInMs(SettingStore::VALUEID<uchar *>)
0x1800044c4  lea     rdx, [rdi+0EA60h]
0x1800044cb  mov     r8, rax
0x1800044ce  cmp     rax, rdx
0x1800044d1  ja      loc_1800045BC
0x1800044d7  mov     rcx, rbx
0x1800044da  call    ?UpdateNextLogTime@Util@BrowserDataLogger@@CA_KU?$VALUEID@PEAE@SettingStore@@@Z; BrowserDataLogger::Util::UpdateNextLogTime(SettingStore::VALUEID<uchar *>)
0x1800044df  mov     eax, cs:dword_18000C080
0x1800044e5  cmp     eax, 5
0x1800044e8  jbe     loc_1800045D0
0x1800044ee  mov     rcx, cs:qword_18000C098
0x1800044f5  mov     rdx, 400000000000h
0x1800044ff  mov     rax, cs:qword_18000C090
0x180004506  test    rdx, rax
0x180004509  jz      loc_1800045D0
0x18000450f  mov     rax, rcx
0x180004512  and     rax, rdx
0x180004515  cmp     rax, rcx
0x180004518  jnz     loc_1800045D0
0x18000451e  xor     r9d, r9d; Context
0x180004521  mov     [rbp+57h+var_9C], esi
0x180004524  xor     r8d, r8d; Parameter
0x180004527  mov     [rbp+57h+var_A0], 1
0x18000452b  lea     rdx, ?LoadIsoDll@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180004532  lea     rcx, ?g_InitOnce@@3T_RTL_RUN_ONCE@@A; InitOnce
0x180004539  call    InitOnceExecuteOnce_0
0x18000453e  mov     rax, cs:qword_18000F008
0x180004545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000454a  mov     ecx, 10000003h
0x18000454f  mov     rbx, rax
0x180004552  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x180004558  lea     rcx, [rbp+57h+var_9C]
0x18000455c  mov     [rbp+57h+var_38], 4
0x180004564  mov     [rbp+57h+var_40], rcx
0x180004568  lea     rdx, byte_1800097B9
0x18000456f  lea     rcx, [rbp+57h+var_A0]
0x180004573  mov     [rbp+57h+var_70], rax
0x180004577  lea     rax, [rbp+57h+var_90]
0x18000457b  mov     [rbp+57h+var_50], rcx
0x18000457f  mov     [rsp+0D0h+var_A8], rax
0x180004584  lea     rcx, dword_18000C080
0x18000458b  xor     r9d, r9d
0x18000458e  mov     [rbp+57h+var_48], 1
0x180004596  xor     r8d, r8d
0x180004599  mov     [rbp+57h+var_60], rbx
0x18000459d  mov     [rbp+57h+var_58], 10h
0x1800045a5  mov     [rbp+57h+var_68], 10h
0x1800045ad  mov     [rsp+0D0h+var_B0], 6
0x1800045b5  call    _tlgWriteTransfer_BrowserWriteTransfer
0x1800045ba  jmp     short loc_1800045D0
0x1800045bc  lea     rax, [rdi+1499700h]
0x1800045c3  cmp     r8, rax
0x1800045c6  jbe     short loc_1800045D0
0x1800045c8  mov     rcx, rbx
0x1800045cb  call    ?UpdateNextLogTime@Util@BrowserDataLogger@@CA_KU?$VALUEID@PEAE@SettingStore@@@Z; BrowserDataLogger::Util::UpdateNextLogTime(SettingStore::VALUEID<uchar *>)
0x1800045d0  mov     rcx, [rbp+57h+var_30]
0x1800045d4  xor     rcx, rsp; StackCookie
0x1800045d7  call    __security_check_cookie
0x1800045dc  add     rsp, 0B8h
0x1800045e3  pop     rdi
0x1800045e4  pop     rsi
0x1800045e5  pop     rbx
0x1800045e6  pop     rbp
0x1800045e7  retn
```
