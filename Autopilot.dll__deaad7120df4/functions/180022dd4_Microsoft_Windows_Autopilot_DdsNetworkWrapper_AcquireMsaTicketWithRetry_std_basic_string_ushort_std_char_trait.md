# Microsoft::Windows::Autopilot::DdsNetworkWrapper::AcquireMsaTicketWithRetry(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180022dd4`
- end: `0x180022f97`
- name: `?AcquireMsaTicketWithRetry@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV56@@Z`
- size: `451`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180024878`

## callees

- `0x1800045d0`
- `0x180010764`
- `0x180013520`
- `0x180013580`
- `0x180017a20`
- `0x18001982c`
- `0x1800215e4`
- `0x180022dd4`
- `0x1800238cc`
- `0x180027904`

## string_xrefs

- `0x180022f3b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::DdsNetworkWrapper::AcquireMsaTicketWithRetry(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  unsigned __int64 v5; // rdx
  int v6; // esi
  __int128 *v7; // rcx
  int MsaDeviceTicket; // eax
  __int64 v9; // r8
  unsigned int v10; // ebx
  __int64 v11; // rcx
  char *v12; // r9
  int v13; // eax
  __int64 v14; // rcx
  char *v15; // rax
  __int64 v16; // r9
  __int64 *v17; // rdx
  char *v19; // [rsp+20h] [rbp-A8h]
  int v20; // [rsp+30h] [rbp-98h] BYREF
  __int64 v21; // [rsp+38h] [rbp-90h]
  __int128 v22; // [rsp+40h] [rbp-88h] BYREF
  __int64 v23; // [rsp+50h] [rbp-78h]
  __int64 v24; // [rsp+58h] [rbp-70h]
  char v25; // [rsp+60h] [rbp-68h] BYREF
  int *v26; // [rsp+70h] [rbp-58h]
  __int64 v27; // [rsp+78h] [rbp-50h]
  char v28; // [rsp+80h] [rbp-48h] BYREF
  char v29; // [rsp+90h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v21 = a2;
  v22 = 0;
  v5 = 7;
  v24 = 7;
  LOWORD(v22) = 0;
  v6 = 0;
  while ( 1 )
  {
    v23 = 0;
    v7 = &v22;
    if ( v5 > 7 )
      v7 = (__int128 *)v22;
    *(_WORD *)v7 = 0;
    MsaDeviceTicket = Microsoft::Windows::Autopilot::DdsNetworkWrapper::GetMsaDeviceTicket(v7, a2, &v22);
    v10 = MsaDeviceTicket;
    if ( MsaDeviceTicket >= 0 )
    {
LABEL_23:
      std::wstring::operator=(a3, &v22, v9);
      v10 = 0;
      goto LABEL_24;
    }
    v11 = (unsigned int)Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits;
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
    {
      if ( *(_QWORD *)(a2 + 24) <= 7u )
        v12 = (char *)a2;
      else
        v12 = *(char **)a2;
      McTemplateU0dz_EventWriteTransfer(
        (unsigned int)Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits,
        AutopilotDownloadFailedAcquireTicket,
        (unsigned int)MsaDeviceTicket,
        v12,
        v19);
      v11 = (unsigned int)Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits;
    }
    if ( v10 != -2147012859 )
      break;
    if ( (v11 & 4) != 0 )
    {
      v19 = &v28;
      McGenEventWrite_EventWriteTransfer(v11, AutopilotDownloadFailedCertificateDate, v9, 1);
    }
    v13 = Microsoft::Windows::Autopilot::AutopilotTime::ForceNetworkTimeSync();
    if ( v13 < 0 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 1) == 0 )
        goto LABEL_19;
      v20 = v13;
      v26 = &v20;
      v27 = 4;
      v15 = &v25;
      v16 = 2;
      v17 = AutopilotDownloadTimeSyncFailed;
    }
    else
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) == 0 )
        goto LABEL_19;
      v15 = &v29;
      v16 = 1;
      v17 = AutopilotDownloadTimeSyncSucceeded;
    }
    v19 = v15;
    McGenEventWrite_EventWriteTransfer(v14, v17, v9, v16);
LABEL_19:
    if ( ++v6 >= 2 )
      goto LABEL_23;
    v5 = v24;
  }
  if ( !Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(v10) )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x347,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)v10,
      (int)v19);
LABEL_24:
  std::wstring::_Tidy_deallocate((char **)&v22);
  std::wstring::_Tidy_deallocate((char **)a2);
  return v10;
}

```

## disassembly

```asm
0x180022dd4  mov     [rsp+arg_0], rbx
0x180022dd9  push    rsi
0x180022dda  push    rdi
0x180022ddb  push    r14
0x180022ddd  sub     rsp, 0B0h
0x180022de4  mov     rax, cs:__security_cookie
0x180022deb  xor     rax, rsp
0x180022dee  mov     [rsp+0C8h+var_28], rax
0x180022df6  mov     r14, r8
0x180022df9  mov     rdi, rdx
0x180022dfc  mov     [rsp+0C8h+var_90], rdx
0x180022e01  xorps   xmm0, xmm0
0x180022e04  movups  [rsp+0C8h+var_88], xmm0
0x180022e09  mov     edx, 7
0x180022e0e  mov     [rsp+0C8h+var_70], rdx
0x180022e13  xor     eax, eax
0x180022e15  mov     word ptr [rsp+0C8h+var_88], ax
0x180022e1a  xor     esi, esi
0x180022e1c  mov     [rsp+0C8h+var_78], 0
0x180022e25  lea     rcx, [rsp+0C8h+var_88]
0x180022e2a  cmp     rdx, 7
0x180022e2e  cmova   rcx, qword ptr [rsp+0C8h+var_88]
0x180022e34  xor     eax, eax
0x180022e36  mov     [rcx], ax
0x180022e39  lea     r8, [rsp+0C8h+var_88]
0x180022e3e  mov     rdx, rdi
0x180022e41  call    ?GetMsaDeviceTicket@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV56@@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::GetMsaDeviceTicket(std::wstring const &,std::wstring &)
0x180022e46  mov     ebx, eax
0x180022e48  test    eax, eax
0x180022e4a  jns     loc_180022F4E
0x180022e50  mov     ecx, cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits
0x180022e56  test    cl, 4
0x180022e59  jz      short loc_180022E7F
0x180022e5b  cmp     qword ptr [rdi+18h], 7
0x180022e60  jbe     short loc_180022E67
0x180022e62  mov     r9, [rdi]
0x180022e65  jmp     short loc_180022E6A
0x180022e67  mov     r9, rdi
0x180022e6a  mov     r8d, ebx
0x180022e6d  lea     rdx, AutopilotDownloadFailedAcquireTicket
0x180022e74  call    McTemplateU0dz_EventWriteTransfer
0x180022e79  mov     ecx, cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits
0x180022e7f  cmp     ebx, 80072F05h
0x180022e85  jnz     loc_180022F25
0x180022e8b  test    cl, 4
0x180022e8e  jz      short loc_180022EAF
0x180022e90  lea     rax, [rsp+0C8h+var_48]
0x180022e98  mov     [rsp+0C8h+var_A8], rax
0x180022e9d  mov     r9d, 1
0x180022ea3  lea     rdx, AutopilotDownloadFailedCertificateDate
0x180022eaa  call    McGenEventWrite_EventWriteTransfer
0x180022eaf  call    ?ForceNetworkTimeSync@AutopilotTime@Autopilot@Windows@Microsoft@@SAJXZ; Microsoft::Windows::Autopilot::AutopilotTime::ForceNetworkTimeSync(void)
0x180022eb4  test    eax, eax
0x180022eb6  js      short loc_180022ED8
0x180022eb8  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x180022ebf  jz      short loc_180022F14
0x180022ec1  lea     rax, [rsp+0C8h+var_38]
0x180022ec9  mov     r9d, 1
0x180022ecf  lea     rdx, AutopilotDownloadTimeSyncSucceeded
0x180022ed6  jmp     short loc_180022F0A
0x180022ed8  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 1
0x180022edf  jz      short loc_180022F14
0x180022ee1  mov     [rsp+0C8h+var_98], eax
0x180022ee5  lea     rax, [rsp+0C8h+var_98]
0x180022eea  mov     [rsp+0C8h+var_58], rax
0x180022eef  mov     [rsp+0C8h+var_50], 4
0x180022ef8  lea     rax, [rsp+0C8h+var_68]
0x180022efd  mov     r9d, 2
0x180022f03  lea     rdx, AutopilotDownloadTimeSyncFailed
0x180022f0a  mov     [rsp+0C8h+var_A8], rax
0x180022f0f  call    McGenEventWrite_EventWriteTransfer
0x180022f14  inc     esi
0x180022f16  cmp     esi, 2
0x180022f19  jge     short loc_180022F4E
0x180022f1b  mov     rdx, [rsp+0C8h+var_70]
0x180022f20  jmp     loc_180022E1C
0x180022f25  mov     ecx, ebx; int
0x180022f27  call    ?IsExpectedAcquireError@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SA_NJ@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(long)
0x180022f2c  test    al, al
0x180022f2e  jnz     short loc_180022F5D
0x180022f30  mov     rcx, [rsp+0C8h]; this
0x180022f38  mov     r9d, ebx; char *
0x180022f3b  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180022f42  mov     edx, 347h; void *
0x180022f47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022f4c  jmp     short loc_180022F5D
0x180022f4e  lea     rdx, [rsp+0C8h+var_88]
0x180022f53  mov     rcx, r14
0x180022f56  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180022f5b  xor     ebx, ebx
0x180022f5d  lea     rcx, [rsp+0C8h+var_88]
0x180022f62  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022f67  nop
0x180022f68  mov     rcx, rdi
0x180022f6b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022f70  mov     eax, ebx
0x180022f72  mov     rcx, [rsp+0C8h+var_28]
0x180022f7a  xor     rcx, rsp; StackCookie
0x180022f7d  call    __security_check_cookie
0x180022f82  mov     rbx, [rsp+0C8h+arg_0]
0x180022f8a  add     rsp, 0B0h
0x180022f91  pop     r14
0x180022f93  pop     rdi
0x180022f94  pop     rsi
0x180022f95  retn
```
