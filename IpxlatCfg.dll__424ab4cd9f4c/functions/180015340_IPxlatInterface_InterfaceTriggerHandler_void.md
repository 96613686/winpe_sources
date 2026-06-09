# IPxlatInterface::InterfaceTriggerHandler(void *)

- ea: `0x180015340`
- end: `0x1800156d6`
- name: `?InterfaceTriggerHandler@IPxlatInterface@@SAKPEAX@Z`
- size: `918`
- prototype: `__int64 __fastcall(char *Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001d40`
- `0x18000c224`
- `0x180012388`
- `0x1800133ac`
- `0x18001468c`
- `0x180015340`
- `0x1800158d0`
- `0x1800172a4`
- `0x180017930`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015639`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015639`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800153d2`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800153d2`

## string_xrefs

- `0x18001567f`: `Interface trigger thread explicitly shutting down`
- `0x18001564d`: `Interface trigger thread shutting down due to error`

## pseudocode

```c
__int64 __fastcall IPxlatInterface::InterfaceTriggerHandler(char *Parameter)
{
  DWORD v2; // eax
  __int64 v3; // rcx
  __int64 v4; // r8
  int v5; // ecx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // rcx
  __int64 v9; // r8
  DWORD LastError; // eax
  int v11; // edx
  DWORD v12; // edi
  __int64 v14; // [rsp+30h] [rbp-39h] BYREF
  _BYTE v15[16]; // [rsp+38h] [rbp-31h] BYREF
  const char *v16; // [rsp+48h] [rbp-21h]
  __int64 v17; // [rsp+50h] [rbp-19h]
  __int64 *v18; // [rsp+58h] [rbp-11h]
  __int64 v19; // [rsp+60h] [rbp-9h]
  HANDLE Handles[4]; // [rsp+68h] [rbp-1h] BYREF

  IPxlatInterface::CheckInterfaceIpState((IPxlatInterface *)Parameter);
  if ( !Parameter[70] && Parameter[74] )
    IPxlatInterface::GetRemotePrefix((IPxlatInterface *)Parameter);
  IPxlatInterface::UpdateTranslationState((IPxlatInterface *)Parameter);
  Handles[0] = *((HANDLE *)Parameter + 13);
  Handles[1] = *((HANDLE *)Parameter + 14);
  Handles[2] = *((HANDLE *)Parameter + 12);
  Handles[3] = *((HANDLE *)Parameter + 11);
  while ( 1 )
  {
    while ( 1 )
    {
      v2 = WaitForMultipleObjectsEx(4u, Handles, 0, 0xFFFFFFFF, 1);
      if ( v2 )
        break;
      if ( !Parameter[70] )
      {
        if ( (Microsoft_Windows_IPxlatCfgEnableBits & 2) != 0 )
        {
          v14 = *(_QWORD *)Parameter;
          v17 = 26;
          v16 = "DNS query timeout occured";
          v18 = &v14;
          v19 = 8;
          McGenEventWrite_EventWriteTransfer(v3, IPXLATCFG_INTERFACE_INFO_EVENT, v4, 3, v15);
        }
LABEL_31:
        IPxlatInterface::GetRemotePrefix((IPxlatInterface *)Parameter);
        goto LABEL_32;
      }
      if ( (Microsoft_Windows_IPxlatCfgEnableBits & 2) != 0 )
      {
        v14 = *(_QWORD *)Parameter;
        v17 = 37;
        v16 = "Unexpected DNS query timeout occured";
        v18 = &v14;
        v19 = 8;
        McGenEventWrite_EventWriteTransfer(v3, IPXLATCFG_INTERFACE_INFO_EVENT, v4, 3, v15);
      }
    }
    if ( v2 == 1 )
    {
      if ( (Microsoft_Windows_IPxlatCfgEnableBits & 2) != 0 )
      {
        v14 = *(_QWORD *)Parameter;
        v17 = 24;
        v16 = "DNS TTL timeout occured";
        v18 = &v14;
        v19 = 8;
        McGenEventWrite_EventWriteTransfer(v3, IPXLATCFG_INTERFACE_INFO_EVENT, v4, 3, v15);
      }
      *((_QWORD *)Parameter + 15) = -300000000;
      goto LABEL_31;
    }
    if ( v2 != 2 )
      break;
    if ( (Microsoft_Windows_IPxlatCfgEnableBits & 2) != 0 )
    {
      v14 = *(_QWORD *)Parameter;
      v17 = 29;
      v16 = "IP state change notification";
      v18 = &v14;
      v19 = 8;
      McGenEventWrite_EventWriteTransfer(v3, IPXLATCFG_INTERFACE_INFO_EVENT, v4, 3, v15);
    }
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress>::GetImpl'::`2'::impl) )
    {
      v5 = *((_DWORD *)Parameter + 7);
      if ( (unsigned int)(v5 - 243) > 1
        && v5 != 237
        && Parameter[73]
        && IPxlatInterface::IsSyntheticIpv6DadDuplicate((IPxlatInterface *)Parameter) )
      {
        if ( (Microsoft_Windows_IPxlatCfgEnableBits & 2) != 0 )
        {
          v14 = *(_QWORD *)Parameter;
          v17 = 47;
          v16 = "DAD failure detected on synthetic IPv6 address";
          v18 = &v14;
          v19 = 8;
          McGenEventWrite_EventWriteTransfer(v6, IPXLATCFG_INTERFACE_INFO_EVENT, v7, 3, v15);
        }
        Parameter[72] = 0;
        IPxlatInterface::UpdateTranslationState((IPxlatInterface *)Parameter);
        *(_OWORD *)(Parameter + 136) = 0;
        if ( ++*((_DWORD *)Parameter + 56) > 3u && (Microsoft_Windows_IPxlatCfgEnableBits & 8) != 0 )
        {
          v14 = *(_QWORD *)Parameter;
          v17 = 8;
          v16 = (const char *)&v14;
          McGenEventWrite_EventWriteTransfer(v8, IPXLATCFG_DAD_RETRY_EXHAUSTED_EVENT, v9, 2, v15);
        }
      }
    }
    IPxlatInterface::CheckInterfaceIpState((IPxlatInterface *)Parameter);
    if ( !Parameter[70] && !Parameter[75] && Parameter[74] )
      goto LABEL_31;
LABEL_32:
    IPxlatInterface::UpdateTranslationState((IPxlatInterface *)Parameter);
  }
  if ( v2 == 3 )
  {
    v12 = 0;
    if ( (Microsoft_Windows_IPxlatCfgEnableBits & 2) != 0 )
    {
      v14 = *(_QWORD *)Parameter;
      v17 = 50;
      v16 = "Interface trigger thread explicitly shutting down";
      v18 = &v14;
      v19 = 8;
      McGenEventWrite_EventWriteTransfer(v3, IPXLATCFG_INTERFACE_INFO_EVENT, v4, 3, v15);
    }
  }
  else
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
      McTemplateU0sqx_EventWriteTransfer(
        *(_QWORD *)Parameter,
        v11,
        (unsigned int)"Interface trigger thread shutting down due to error",
        LastError,
        *(_QWORD *)Parameter);
  }
  Parameter[72] = 0;
  IPxlatInterface::UpdateTranslationState((IPxlatInterface *)Parameter);
  return v12;
}

```

## disassembly

```asm
0x180015340  push    rbp
0x180015342  push    rbx
0x180015343  push    rsi
0x180015344  push    rdi
0x180015345  push    r12
0x180015347  push    r15
0x180015349  lea     rbp, [rsp-2Fh]
0x18001534e  sub     rsp, 98h
0x180015355  mov     rax, cs:__security_cookie
0x18001535c  xor     rax, rsp
0x18001535f  mov     [rbp+57h+var_38], rax
0x180015363  mov     rbx, rcx
0x180015366  call    ?CheckInterfaceIpState@IPxlatInterface@@AEAAXXZ; IPxlatInterface::CheckInterfaceIpState(void)
0x18001536b  xor     esi, esi
0x18001536d  cmp     [rbx+46h], sil
0x180015371  jnz     short loc_180015381
0x180015373  cmp     [rbx+4Ah], sil
0x180015377  jz      short loc_180015381
0x180015379  mov     rcx, rbx; this
0x18001537c  call    ?GetRemotePrefix@IPxlatInterface@@AEAAXXZ; IPxlatInterface::GetRemotePrefix(void)
0x180015381  mov     rcx, rbx; this
0x180015384  call    ?UpdateTranslationState@IPxlatInterface@@AEAAXXZ; IPxlatInterface::UpdateTranslationState(void)
0x180015389  mov     rax, [rbx+68h]
0x18001538d  lea     rdi, IPXLATCFG_INTERFACE_INFO_EVENT
0x180015394  mov     [rbp+57h+Handles], rax
0x180015398  mov     r12d, 8
0x18001539e  mov     rax, [rbx+70h]
0x1800153a2  mov     [rbp+57h+var_50], rax
0x1800153a6  mov     rax, [rbx+60h]
0x1800153aa  mov     [rbp+57h+var_48], rax
0x1800153ae  lea     r15d, [r12-5]
0x1800153b3  mov     rax, [rbx+58h]
0x1800153b7  mov     [rbp+57h+var_40], rax
0x1800153bb  xor     r8d, r8d; bWaitAll
0x1800153be  mov     [rsp+0C0h+bAlertable], 1; bAlertable
0x1800153c6  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800153ca  lea     rdx, [rbp+57h+Handles]; lpHandles
0x1800153ce  lea     ecx, [r8+4]; nCount
0x1800153d2  call    cs:__imp_WaitForMultipleObjectsEx
0x1800153d8  test    eax, eax
0x1800153da  jnz     loc_18001547A
0x1800153e0  cmp     [rbx+46h], sil
0x1800153e4  jnz     short loc_180015432
0x1800153e6  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 2
0x1800153ed  jz      loc_18001561F
0x1800153f3  mov     rax, [rbx]
0x1800153f6  mov     r9d, r15d
0x1800153f9  mov     [rbp+57h+var_90], rax
0x1800153fd  mov     rdx, rdi
0x180015400  lea     rax, aDnsQueryTimeou; "DNS query timeout occured"
0x180015407  mov     [rbp+57h+var_70], 1Ah
0x18001540f  mov     [rbp+57h+var_78], rax
0x180015413  lea     rax, [rbp+57h+var_90]
0x180015417  mov     [rbp+57h+var_68], rax
0x18001541b  lea     rax, [rbp+57h+var_88]
0x18001541f  mov     qword ptr [rsp+0C0h+bAlertable], rax
0x180015424  mov     [rbp+57h+var_60], r12
0x180015428  call    McGenEventWrite_EventWriteTransfer
0x18001542d  jmp     loc_18001561F
0x180015432  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 2
0x180015439  jz      short loc_1800153BB
0x18001543b  mov     rax, [rbx]
0x18001543e  mov     r9d, r15d
0x180015441  mov     [rbp+57h+var_90], rax
0x180015445  mov     rdx, rdi
0x180015448  lea     rax, aUnexpectedDnsQ; "Unexpected DNS query timeout occured"
0x18001544f  mov     [rbp+57h+var_70], 25h ; '%'
0x180015457  mov     [rbp+57h+var_78], rax
0x18001545b  lea     rax, [rbp+57h+var_90]
0x18001545f  mov     [rbp+57h+var_68], rax
0x180015463  lea     rax, [rbp+57h+var_88]
0x180015467  mov     qword ptr [rsp+0C0h+bAlertable], rax
0x18001546c  mov     [rbp+57h+var_60], r12
0x180015470  call    McGenEventWrite_EventWriteTransfer
0x180015475  jmp     loc_1800153BB
0x18001547a  cmp     eax, 1
0x18001547d  jnz     short loc_1800154CF
0x18001547f  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 2
0x180015486  jz      short loc_1800154C2
0x180015488  mov     rax, [rbx]
0x18001548b  mov     r9d, r15d
0x18001548e  mov     [rbp+57h+var_90], rax
0x180015492  mov     rdx, rdi
0x180015495  lea     rax, aDnsTtlTimeoutO; "DNS TTL timeout occured"
0x18001549c  mov     [rbp+57h+var_70], 18h
0x1800154a4  mov     [rbp+57h+var_78], rax
0x1800154a8  lea     rax, [rbp+57h+var_90]
0x1800154ac  mov     [rbp+57h+var_68], rax
0x1800154b0  lea     rax, [rbp+57h+var_88]
0x1800154b4  mov     qword ptr [rsp+0C0h+bAlertable], rax
0x1800154b9  mov     [rbp+57h+var_60], r12
0x1800154bd  call    McGenEventWrite_EventWriteTransfer
0x1800154c2  mov     qword ptr [rbx+78h], 0FFFFFFFFEE1E5D00h
0x1800154ca  jmp     loc_18001561F
0x1800154cf  cmp     eax, 2
0x1800154d2  jnz     loc_180015634
0x1800154d8  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, al
0x1800154de  jz      short loc_18001551A
0x1800154e0  mov     rax, [rbx]
0x1800154e3  mov     r9d, r15d
0x1800154e6  mov     [rbp+57h+var_90], rax
0x1800154ea  mov     rdx, rdi
0x1800154ed  lea     rax, aIpStateChangeN; "IP state change notification"
0x1800154f4  mov     [rbp+57h+var_70], 1Dh
0x1800154fc  mov     [rbp+57h+var_78], rax
0x180015500  lea     rax, [rbp+57h+var_90]
0x180015504  mov     [rbp+57h+var_68], rax
0x180015508  lea     rax, [rbp+57h+var_88]
0x18001550c  mov     qword ptr [rsp+0C0h+bAlertable], rax
0x180015511  mov     [rbp+57h+var_60], r12
0x180015515  call    McGenEventWrite_EventWriteTransfer
0x18001551a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress>::GetImpl(void)'::`2'::impl
0x180015521  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress>::__private_IsEnabled(void)
0x180015526  test    al, al
0x180015528  jz      loc_180015605
0x18001552e  mov     ecx, [rbx+1Ch]
0x180015531  lea     eax, [rcx-0F3h]
0x180015537  cmp     eax, 1
0x18001553a  jbe     loc_180015605
0x180015540  cmp     ecx, 0EDh
0x180015546  jz      loc_180015605
0x18001554c  cmp     [rbx+49h], sil
0x180015550  jz      loc_180015605
0x180015556  mov     rcx, rbx; this
0x180015559  call    ?IsSyntheticIpv6DadDuplicate@IPxlatInterface@@AEBA_NXZ; IPxlatInterface::IsSyntheticIpv6DadDuplicate(void)
0x18001555e  test    al, al
0x180015560  jz      loc_180015605
0x180015566  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 2
0x18001556d  jz      short loc_1800155A9
0x18001556f  mov     rax, [rbx]
0x180015572  mov     r9d, r15d
0x180015575  mov     [rbp+57h+var_90], rax
0x180015579  mov     rdx, rdi
0x18001557c  lea     rax, aDadFailureDete; "DAD failure detected on synthetic IPv6 "...
0x180015583  mov     [rbp+57h+var_70], 2Fh ; '/'
0x18001558b  mov     [rbp+57h+var_78], rax
0x18001558f  lea     rax, [rbp+57h+var_90]
0x180015593  mov     [rbp+57h+var_68], rax
0x180015597  lea     rax, [rbp+57h+var_88]
0x18001559b  mov     qword ptr [rsp+0C0h+bAlertable], rax
0x1800155a0  mov     [rbp+57h+var_60], r12
0x1800155a4  call    McGenEventWrite_EventWriteTransfer
0x1800155a9  mov     rcx, rbx; this
0x1800155ac  mov     [rbx+48h], sil
0x1800155b0  call    ?UpdateTranslationState@IPxlatInterface@@AEAAXXZ; IPxlatInterface::UpdateTranslationState(void)
0x1800155b5  xorps   xmm0, xmm0
0x1800155b8  movups  xmmword ptr [rbx+88h], xmm0
0x1800155bf  inc     dword ptr [rbx+0E0h]
0x1800155c5  cmp     [rbx+0E0h], r15d
0x1800155cc  jbe     short loc_180015605
0x1800155ce  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, r12b
0x1800155d5  jz      short loc_180015605
0x1800155d7  mov     rax, [rbx]
0x1800155da  lea     rdx, IPXLATCFG_DAD_RETRY_EXHAUSTED_EVENT
0x1800155e1  mov     [rbp+57h+var_90], rax
0x1800155e5  mov     r9d, 2
0x1800155eb  lea     rax, [rbp+57h+var_90]
0x1800155ef  mov     [rbp+57h+var_70], r12
0x1800155f3  mov     [rbp+57h+var_78], rax
0x1800155f7  lea     rax, [rbp+57h+var_88]
0x1800155fb  mov     qword ptr [rsp+0C0h+bAlertable], rax
0x180015600  call    McGenEventWrite_EventWriteTransfer
0x180015605  mov     rcx, rbx; this
0x180015608  call    ?CheckInterfaceIpState@IPxlatInterface@@AEAAXXZ; IPxlatInterface::CheckInterfaceIpState(void)
0x18001560d  cmp     [rbx+46h], sil
0x180015611  jnz     short loc_180015627
0x180015613  cmp     [rbx+4Bh], sil
0x180015617  jnz     short loc_180015627
0x180015619  cmp     [rbx+4Ah], sil
0x18001561d  jz      short loc_180015627
0x18001561f  mov     rcx, rbx; this
0x180015622  call    ?GetRemotePrefix@IPxlatInterface@@AEAAXXZ; IPxlatInterface::GetRemotePrefix(void)
0x180015627  mov     rcx, rbx; this
0x18001562a  call    ?UpdateTranslationState@IPxlatInterface@@AEAAXXZ; IPxlatInterface::UpdateTranslationState(void)
0x18001562f  jmp     loc_1800153BB
0x180015634  cmp     eax, r15d
0x180015637  jz      short loc_180015663
0x180015639  call    cs:__imp_GetLastError
0x18001563f  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 1
0x180015646  mov     edi, eax
0x180015648  jz      short loc_1800156AC
0x18001564a  mov     rcx, [rbx]
0x18001564d  lea     r8, aInterfaceTrigg; "Interface trigger thread shutting down "...
0x180015654  mov     r9d, eax
0x180015657  mov     qword ptr [rsp+0C0h+bAlertable], rcx
0x18001565c  call    McTemplateU0sqx_EventWriteTransfer
0x180015661  jmp     short loc_1800156AC
0x180015663  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 2
0x18001566a  mov     edi, esi
0x18001566c  jz      short loc_1800156AC
0x18001566e  mov     rax, [rbx]
0x180015671  lea     rdx, IPXLATCFG_INTERFACE_INFO_EVENT
0x180015678  mov     [rbp+57h+var_90], rax
0x18001567c  mov     r9d, r15d
0x18001567f  lea     rax, aInterfaceTrigg_0; "Interface trigger thread explicitly shu"...
0x180015686  mov     [rbp+57h+var_70], 32h ; '2'
0x18001568e  mov     [rbp+57h+var_78], rax
0x180015692  lea     rax, [rbp+57h+var_90]
0x180015696  mov     [rbp+57h+var_68], rax
0x18001569a  lea     rax, [rbp+57h+var_88]
0x18001569e  mov     qword ptr [rsp+0C0h+bAlertable], rax
0x1800156a3  mov     [rbp+57h+var_60], r12
0x1800156a7  call    McGenEventWrite_EventWriteTransfer
0x1800156ac  mov     rcx, rbx; this
0x1800156af  mov     [rbx+48h], sil
0x1800156b3  call    ?UpdateTranslationState@IPxlatInterface@@AEAAXXZ; IPxlatInterface::UpdateTranslationState(void)
0x1800156b8  mov     eax, edi
0x1800156ba  mov     rcx, [rbp+57h+var_38]
0x1800156be  xor     rcx, rsp; StackCookie
0x1800156c1  call    __security_check_cookie
0x1800156c6  add     rsp, 98h
0x1800156cd  pop     r15
0x1800156cf  pop     r12
0x1800156d1  pop     rdi
0x1800156d2  pop     rsi
0x1800156d3  pop     rbx
0x1800156d4  pop     rbp
0x1800156d5  retn
```
