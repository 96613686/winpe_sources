# Microsoft::Windows::Autopilot::DdsNetworkWrapper::AcquireMsaTicketWithRetry(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18002230c`
- end: `0x1800224ce`
- name: `?AcquireMsaTicketWithRetry@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV56@@Z`
- size: `450`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180023cb0`

## callees

- `0x1800045b0`
- `0x1800105f4`
- `0x180013280`
- `0x1800132d8`
- `0x1800174f0`
- `0x180019230`
- `0x180020bd0`
- `0x18002230c`
- `0x180022d84`
- `0x180026990`

## string_xrefs

- `0x180022473`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::Autopilot::DdsNetworkWrapper::AcquireMsaTicketWithRetry(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  unsigned __int64 v5; // rdx
  int v6; // esi
  __int128 *v7; // rcx
  int MsaDeviceTicket; // eax
  unsigned int v9; // edx
  __int64 v10; // r8
  unsigned int v11; // ebx
  __int64 v12; // rcx
  _QWORD *v13; // r9
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // r8
  struct _EVENT_DATA_DESCRIPTOR *v17; // rax
  ULONG v18; // r9d
  __int64 *v19; // rdx
  int v21; // [rsp+20h] [rbp-A8h]
  int v22; // [rsp+30h] [rbp-98h] BYREF
  _QWORD *v23; // [rsp+38h] [rbp-90h]
  __int128 v24; // [rsp+40h] [rbp-88h] BYREF
  __int64 v25; // [rsp+50h] [rbp-78h]
  __int64 v26; // [rsp+58h] [rbp-70h]
  char v27; // [rsp+60h] [rbp-68h] BYREF
  int *v28; // [rsp+70h] [rbp-58h]
  __int64 v29; // [rsp+78h] [rbp-50h]
  struct _EVENT_DATA_DESCRIPTOR v30; // [rsp+80h] [rbp-48h] BYREF
  char v31; // [rsp+90h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v23 = a2;
  v24 = 0;
  v5 = 7;
  v26 = 7;
  LOWORD(v24) = 0;
  v6 = 0;
  while ( 1 )
  {
    v25 = 0;
    v7 = &v24;
    if ( v5 > 7 )
      v7 = (__int128 *)v24;
    *(_WORD *)v7 = 0;
    MsaDeviceTicket = Microsoft::Windows::Autopilot::DdsNetworkWrapper::GetMsaDeviceTicket(
                        (__int64)v7,
                        a2,
                        (char **)&v24);
    v11 = MsaDeviceTicket;
    if ( MsaDeviceTicket >= 0 )
    {
LABEL_23:
      std::wstring::operator=(a3, &v24);
      v11 = 0;
      goto LABEL_24;
    }
    v12 = (unsigned int)Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits;
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
    {
      if ( a2[3] <= 7u )
        v13 = a2;
      else
        v13 = (_QWORD *)*a2;
      McTemplateU0dz_EventWriteTransfer(
        (unsigned int)Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits,
        AutopilotDownloadFailedAcquireTicket,
        (unsigned int)MsaDeviceTicket,
        v13);
      v12 = (unsigned int)Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits;
    }
    if ( v11 != -2147012859 )
      break;
    if ( (v12 & 4) != 0 )
      McGenEventWrite_EventWriteTransfer(
        v12,
        (const EVENT_DESCRIPTOR *)AutopilotDownloadFailedCertificateDate,
        v10,
        1u,
        &v30);
    v14 = Microsoft::Windows::Autopilot::AutopilotTime::ForceNetworkTimeSync((const unsigned __int16 *)v12, v9);
    if ( v14 < 0 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 1) == 0 )
        goto LABEL_19;
      v22 = v14;
      v28 = &v22;
      v29 = 4;
      v17 = (struct _EVENT_DATA_DESCRIPTOR *)&v27;
      v18 = 2;
      v19 = AutopilotDownloadTimeSyncFailed;
    }
    else
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) == 0 )
        goto LABEL_19;
      v17 = (struct _EVENT_DATA_DESCRIPTOR *)&v31;
      v18 = 1;
      v19 = AutopilotDownloadTimeSyncSucceeded;
    }
    McGenEventWrite_EventWriteTransfer(v15, (const EVENT_DESCRIPTOR *)v19, v16, v18, v17);
LABEL_19:
    if ( ++v6 >= 2 )
      goto LABEL_23;
    v5 = v26;
  }
  if ( !Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(v11) )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x347,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)v11,
      v21);
LABEL_24:
  std::wstring::_Tidy_deallocate(&v24);
  std::wstring::_Tidy_deallocate(a2);
  return v11;
}

```

## disassembly

```asm
0x18002230c  mov     [rsp+arg_0], rbx
0x180022311  push    rsi
0x180022312  push    rdi
0x180022313  push    r14
0x180022315  sub     rsp, 0B0h
0x18002231c  mov     rax, cs:__security_cookie
0x180022323  xor     rax, rsp
0x180022326  mov     [rsp+0C8h+var_28], rax
0x18002232e  mov     r14, r8
0x180022331  mov     rdi, rdx
0x180022334  mov     [rsp+0C8h+var_90], rdx
0x180022339  xorps   xmm0, xmm0
0x18002233c  movups  [rsp+0C8h+var_88], xmm0
0x180022341  mov     edx, 7
0x180022346  mov     [rsp+0C8h+var_70], rdx
0x18002234b  xor     eax, eax
0x18002234d  mov     word ptr [rsp+0C8h+var_88], ax
0x180022352  xor     esi, esi
0x180022354  mov     [rsp+0C8h+var_78], 0
0x18002235d  lea     rcx, [rsp+0C8h+var_88]
0x180022362  cmp     rdx, 7
0x180022366  cmova   rcx, qword ptr [rsp+0C8h+var_88]
0x18002236c  xor     eax, eax
0x18002236e  mov     [rcx], ax
0x180022371  lea     r8, [rsp+0C8h+var_88]
0x180022376  mov     rdx, rdi
0x180022379  call    ?GetMsaDeviceTicket@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV56@@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::GetMsaDeviceTicket(std::wstring const &,std::wstring &)
0x18002237e  mov     ebx, eax
0x180022380  test    eax, eax
0x180022382  jns     loc_180022486
0x180022388  mov     ecx, cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits
0x18002238e  test    cl, 4
0x180022391  jz      short loc_1800223B7
0x180022393  cmp     qword ptr [rdi+18h], 7
0x180022398  jbe     short loc_18002239F
0x18002239a  mov     r9, [rdi]
0x18002239d  jmp     short loc_1800223A2
0x18002239f  mov     r9, rdi
0x1800223a2  mov     r8d, ebx
0x1800223a5  lea     rdx, AutopilotDownloadFailedAcquireTicket
0x1800223ac  call    McTemplateU0dz_EventWriteTransfer
0x1800223b1  mov     ecx, cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits
0x1800223b7  cmp     ebx, 80072F05h
0x1800223bd  jnz     loc_18002245D
0x1800223c3  test    cl, 4
0x1800223c6  jz      short loc_1800223E7
0x1800223c8  lea     rax, [rsp+0C8h+var_48]
0x1800223d0  mov     qword ptr [rsp+0C8h+var_A8], rax
0x1800223d5  mov     r9d, 1
0x1800223db  lea     rdx, AutopilotDownloadFailedCertificateDate
0x1800223e2  call    McGenEventWrite_EventWriteTransfer
0x1800223e7  call    ?ForceNetworkTimeSync@AutopilotTime@Autopilot@Windows@Microsoft@@SAJXZ; Microsoft::Windows::Autopilot::AutopilotTime::ForceNetworkTimeSync(void)
0x1800223ec  test    eax, eax
0x1800223ee  js      short loc_180022410
0x1800223f0  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x1800223f7  jz      short loc_18002244C
0x1800223f9  lea     rax, [rsp+0C8h+var_38]
0x180022401  mov     r9d, 1
0x180022407  lea     rdx, AutopilotDownloadTimeSyncSucceeded
0x18002240e  jmp     short loc_180022442
0x180022410  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 1
0x180022417  jz      short loc_18002244C
0x180022419  mov     [rsp+0C8h+var_98], eax
0x18002241d  lea     rax, [rsp+0C8h+var_98]
0x180022422  mov     [rsp+0C8h+var_58], rax
0x180022427  mov     [rsp+0C8h+var_50], 4
0x180022430  lea     rax, [rsp+0C8h+var_68]
0x180022435  mov     r9d, 2
0x18002243b  lea     rdx, AutopilotDownloadTimeSyncFailed
0x180022442  mov     qword ptr [rsp+0C8h+var_A8], rax
0x180022447  call    McGenEventWrite_EventWriteTransfer
0x18002244c  inc     esi
0x18002244e  cmp     esi, 2
0x180022451  jge     short loc_180022486
0x180022453  mov     rdx, [rsp+0C8h+var_70]
0x180022458  jmp     loc_180022354
0x18002245d  mov     ecx, ebx; int
0x18002245f  call    ?IsExpectedAcquireError@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SA_NJ@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(long)
0x180022464  test    al, al
0x180022466  jnz     short loc_180022495
0x180022468  mov     rcx, [rsp+0C8h]; this
0x180022470  mov     r9d, ebx; char *
0x180022473  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002247a  mov     edx, 347h; void *
0x18002247f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022484  jmp     short loc_180022495
0x180022486  lea     rdx, [rsp+0C8h+var_88]
0x18002248b  mov     rcx, r14
0x18002248e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180022493  xor     ebx, ebx
0x180022495  lea     rcx, [rsp+0C8h+var_88]
0x18002249a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002249f  nop
0x1800224a0  mov     rcx, rdi
0x1800224a3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800224a8  mov     eax, ebx
0x1800224aa  mov     rcx, [rsp+0C8h+var_28]
0x1800224b2  xor     rcx, rsp; StackCookie
0x1800224b5  call    __security_check_cookie
0x1800224ba  mov     rbx, [rsp+0C8h+arg_0]
0x1800224c2  add     rsp, 0B0h
0x1800224c9  pop     r14
0x1800224cb  pop     rdi
0x1800224cc  pop     rsi
0x1800224cd  retn
```
