# _lambda_612a61c8f178d30cb019cab59c668fc2_::operator()

- ea: `0x180035d7c`
- end: `0x180035f61`
- name: `_lambda_612a61c8f178d30cb019cab59c668fc2_::operator()`
- size: `485`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x1800382f0`

## callees

- `0x180006420`
- `0x180007f90`
- `0x180016ba4`
- `0x180017de4`
- `0x18002547c`
- `0x18002a030`
- `0x18002aad0`
- `0x18002e2d0`
- `0x180031ce4`
- `0x180035d7c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180035e3e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180035e3e`
- `dusmapi!DusmQueryUserCost` at `0x180035e97`
- `dusmapi!DusmQueryUserCost` at `0x180035e97`

## string_xrefs

- `0x180035f33`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`
- `0x180035f4f`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_612a61c8f178d30cb019cab59c668fc2_::operator()(__int64 a1, __int64 a2)
{
  int v4; // esi
  __int64 *v5; // rdi
  GUID *v6; // rbx
  __int64 result; // rax
  int v8; // eax
  __int64 v9; // rbx
  GUID *v10; // rdi
  unsigned int v11; // [rsp+20h] [rbp-E0h]
  __int64 v12; // [rsp+30h] [rbp-D0h]
  HANDLE v13; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE v14; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR v15[16]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v16; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v17[256]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  v4 = **(_DWORD **)(a1 + 48);
  v5 = *(__int64 **)(a1 + 40);
  v6 = *(GUID **)(a1 + 32);
  std::wstring::wstring(v15, **(_QWORD **)(a1 + 24));
  v13 = **(HANDLE **)(a1 + 16);
  LODWORD(v6) = WlanSyncTaskWlanToCDS::PushCloudChange<Windows::Data::WiFi::WiFiProfile>(
                  *(_QWORD *)a1,
                  *(wil::ActivityThreadWatcher **)(a1 + 8),
                  &v13,
                  v15,
                  v6,
                  v5,
                  v4,
                  0,
                  a2);
  result = std::wstring::~wstring((__int64)v15);
  if ( (_DWORD)v6 == 1 )
  {
    *(_DWORD *)(*(_QWORD *)(a1 + 40) + 40LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 40) + 44LL) = 0x80000000;
    GetSystemTimeAsFileTime((LPFILETIME)(*(_QWORD *)(a1 + 40) + 32LL));
    memset_0(&v16, 0, 0x210u);
    v16 = *(_OWORD *)*(_QWORD *)(a1 + 32);
    v8 = StringCchCopyW(v17, 0x100u, **(const unsigned __int16 ***)(a1 + 24));
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x225,
        (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
        (const char *)(unsigned int)v8,
        v11);
    v13 = 0;
    result = DusmQueryUserCost(&v16, &v13);
    if ( (_DWORD)result )
    {
      if ( (_DWORD)result != 2 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x23A,
          (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
          (const char *)(unsigned int)result,
          v11);
    }
    else
    {
      v9 = *(_QWORD *)(a1 + 40);
      v10 = *(GUID **)(a1 + 32);
      std::wstring::wstring(v15, **(_QWORD **)(a1 + 24));
      v14 = **(HANDLE **)(a1 + 16);
      WlanSyncTaskWlanToCDS::PushCloudChange<Windows::Data::WiFi::WiFiProfileCost>(
        *(_QWORD *)a1,
        *(_QWORD *)(a1 + 8),
        &v14,
        v15,
        v10,
        v9,
        v12,
        0,
        a2);
      return std::wstring::~wstring((__int64)v15);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180035d7c  mov     [rsp-8+arg_10], rbx
0x180035d81  push    rbp
0x180035d82  push    rsi
0x180035d83  push    rdi
0x180035d84  push    r14
0x180035d86  push    r15
0x180035d88  lea     rbp, [rsp-1A0h]
0x180035d90  sub     rsp, 2A0h
0x180035d97  mov     rax, cs:__security_cookie
0x180035d9e  xor     rax, rsp
0x180035da1  mov     [rbp+1C0h+var_30], rax
0x180035da8  mov     r15, rdx
0x180035dab  mov     r14, rcx
0x180035dae  mov     rax, [rcx+30h]
0x180035db2  mov     esi, [rax]
0x180035db4  mov     rdi, [rcx+28h]
0x180035db8  mov     rbx, [rcx+20h]
0x180035dbc  mov     rdx, [rcx+18h]
0x180035dc0  mov     rdx, [rdx]
0x180035dc3  lea     rcx, [rsp+2C0h+var_260]
0x180035dc8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180035dcd  nop
0x180035dce  mov     rax, [r14+10h]
0x180035dd2  mov     rcx, [rax]
0x180035dd5  mov     [rsp+2C0h+var_270], rcx
0x180035dda  mov     [rsp+2C0h+var_280], r15
0x180035ddf  mov     [rsp+2C0h+var_288], 0
0x180035de7  mov     dword ptr [rsp+2C0h+var_290], esi
0x180035deb  mov     [rsp+2C0h+var_298], rdi
0x180035df0  mov     qword ptr [rsp+2C0h+var_2A0], rbx; unsigned int
0x180035df5  lea     r9, [rsp+2C0h+var_260]
0x180035dfa  lea     r8, [rsp+2C0h+var_270]
0x180035dff  mov     rdx, [r14+8]
0x180035e03  mov     rcx, [r14]
0x180035e06  call    ??$PushCloudChange@UWiFiProfile@WiFi@Data@Windows@@@WlanSyncTaskWlanToCDS@@CA?AW4WiFiSyncAction@@AEAVWlanTriggeredSync@WiFiCloudStoreTelemetry@@AEAVActivityThreadWatcher@wil@@AEBQEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@AEBUSyncNeededProfile@WiFiCloudStore@Internal@Windows@@W4PushCloudChangeOptionFlags@@KPEBG@Z; WlanSyncTaskWlanToCDS::PushCloudChange<Windows::Data::WiFi::WiFiProfile>(WiFiCloudStoreTelemetry::WlanTriggeredSync &,wil::ActivityThreadWatcher &,void * const &,std::wstring const &,_GUID const &,Windows::Internal::WiFiCloudStore::SyncNeededProfile const &,PushCloudChangeOptionFlags,ulong,ushort const *)
0x180035e0b  mov     ebx, eax
0x180035e0d  lea     rcx, [rsp+2C0h+var_260]
0x180035e12  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180035e17  cmp     ebx, 1
0x180035e1a  jnz     loc_180035F03
0x180035e20  mov     rax, [r14+28h]
0x180035e24  mov     dword ptr [rax+28h], 4
0x180035e2b  mov     rax, [r14+28h]
0x180035e2f  mov     dword ptr [rax+2Ch], 80000000h
0x180035e36  mov     rcx, [r14+28h]
0x180035e3a  add     rcx, 20h ; ' '; lpSystemTimeAsFileTime
0x180035e3e  call    cs:__imp_GetSystemTimeAsFileTime
0x180035e44  xor     edx, edx; Val
0x180035e46  mov     r8d, 210h; Size
0x180035e4c  lea     rcx, [rbp+1C0h+var_240]; void *
0x180035e50  call    memset_0
0x180035e55  mov     rax, [r14+20h]
0x180035e59  movups  xmm0, xmmword ptr [rax]
0x180035e5c  movdqu  [rbp+1C0h+var_240], xmm0
0x180035e61  mov     r8, [r14+18h]
0x180035e65  mov     r8, [r8]; unsigned __int16 *
0x180035e68  mov     edx, 100h; unsigned __int64
0x180035e6d  lea     rcx, [rbp+1C0h+var_230]; unsigned __int16 *
0x180035e71  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180035e76  mov     rcx, [rbp+1C8h]; this
0x180035e7d  test    eax, eax
0x180035e7f  js      loc_180035F30
0x180035e85  mov     [rsp+2C0h+var_270], 0
0x180035e8e  lea     rdx, [rsp+2C0h+var_270]
0x180035e93  lea     rcx, [rbp+1C0h+var_240]
0x180035e97  call    cs:__imp_DusmQueryUserCost
0x180035e9d  test    eax, eax
0x180035e9f  jnz     loc_180035F29
0x180035ea5  mov     rbx, [r14+28h]
0x180035ea9  mov     rdi, [r14+20h]
0x180035ead  mov     rdx, [r14+18h]
0x180035eb1  mov     rdx, [rdx]
0x180035eb4  lea     rcx, [rsp+2C0h+var_260]
0x180035eb9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180035ebe  nop
0x180035ebf  mov     rax, [r14+10h]
0x180035ec3  mov     rcx, [rax]
0x180035ec6  mov     [rsp+2C0h+var_268], rcx
0x180035ecb  mov     [rsp+2C0h+var_280], r15
0x180035ed0  mov     [rsp+2C0h+var_288], 0
0x180035ed8  mov     [rsp+2C0h+var_298], rbx
0x180035edd  mov     qword ptr [rsp+2C0h+var_2A0], rdi
0x180035ee2  lea     r9, [rsp+2C0h+var_260]
0x180035ee7  lea     r8, [rsp+2C0h+var_268]
0x180035eec  mov     rdx, [r14+8]
0x180035ef0  mov     rcx, [r14]
0x180035ef3  call    ??$PushCloudChange@UWiFiProfileCost@WiFi@Data@Windows@@@WlanSyncTaskWlanToCDS@@CA?AW4WiFiSyncAction@@AEAVWlanTriggeredSync@WiFiCloudStoreTelemetry@@AEAVActivityThreadWatcher@wil@@AEBQEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@AEBUSyncNeededProfile@WiFiCloudStore@Internal@Windows@@W4PushCloudChangeOptionFlags@@KPEBG@Z; WlanSyncTaskWlanToCDS::PushCloudChange<Windows::Data::WiFi::WiFiProfileCost>(WiFiCloudStoreTelemetry::WlanTriggeredSync &,wil::ActivityThreadWatcher &,void * const &,std::wstring const &,_GUID const &,Windows::Internal::WiFiCloudStore::SyncNeededProfile const &,PushCloudChangeOptionFlags,ulong,ushort const *)
0x180035ef8  nop
0x180035ef9  lea     rcx, [rsp+2C0h+var_260]
0x180035efe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180035f03  mov     rcx, [rbp+1C0h+var_30]
0x180035f0a  xor     rcx, rsp; StackCookie
0x180035f0d  call    __security_check_cookie
0x180035f12  mov     rbx, [rsp+2C0h+arg_10]
0x180035f1a  add     rsp, 2A0h
0x180035f21  pop     r15
0x180035f23  pop     r14
0x180035f25  pop     rdi
0x180035f26  pop     rsi
0x180035f27  pop     rbp
0x180035f28  retn
0x180035f29  cmp     eax, 2
0x180035f2c  jnz     short loc_180035F45
0x180035f2e  jmp     short loc_180035F03
0x180035f30  mov     r9d, eax; char *
0x180035f33  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180035f3a  mov     edx, 225h; void *
0x180035f3f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180035f45  mov     rcx, [rbp+1C8h]; this
0x180035f4c  mov     r9d, eax; char *
0x180035f4f  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180035f56  mov     edx, 23Ah; void *
0x180035f5b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
