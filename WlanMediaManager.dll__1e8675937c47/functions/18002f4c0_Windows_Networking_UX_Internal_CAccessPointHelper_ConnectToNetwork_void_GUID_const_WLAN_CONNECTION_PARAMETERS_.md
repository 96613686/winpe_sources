# Windows::Networking::UX::Internal::CAccessPointHelper::ConnectToNetwork(void *,_GUID const &,_WLAN_CONNECTION_PARAMETERS const &)

- ea: `0x18002f4c0`
- end: `0x18002f751`
- name: `?ConnectToNetwork@CAccessPointHelper@Internal@UX@Networking@Windows@@UEAAJPEAXAEBU_GUID@@AEBU_WLAN_CONNECTION_PARAMETERS@@@Z`
- size: `657`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::CAccessPointHelper *__hidden this, HANDLE hClientHandle, const struct _GUID *, PWLAN_CONNECTION_PARAMETERS pConnectionParameters)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation`

## callees

- `0x180003ed0`
- `0x180004a70`
- `0x18000de4c`
- `0x180016c08`
- `0x18001d4d4`
- `0x18002f4c0`
- `0x180030bac`
- `0x180032f48`

## import_xrefs

- `ext-ms-win-networking-wlanapi-l1-1-0!WlanSsidToDisplayName` at `0x18002f6af`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanSsidToDisplayName` at `0x18002f6af`
- `wlanapi!WlanConnect` at `0x18002f656`
- `wlanapi!WlanConnect` at `0x18002f656`
- `TetheringStation!TetheringStationConnectApp` at `0x18002f576`
- `TetheringStation!TetheringStationConnectApp` at `0x18002f576`
- `TetheringStation!TetheringStationConnect` at `0x18002f5f9`
- `TetheringStation!TetheringStationConnect` at `0x18002f5f9`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::CAccessPointHelper::ConnectToNetwork(
        Windows::Networking::UX::Internal::CAccessPointHelper *this,
        HANDLE hClientHandle,
        const struct _GUID *a3,
        PWLAN_CONNECTION_PARAMETERS pConnectionParameters)
{
  int TetheringInfoForAccessPointName; // eax
  unsigned int v9; // ebx
  int v10; // eax
  __int64 v11; // rdx
  struct _GUID v12; // xmm0
  LPCWSTR strProfile; // r8
  int v14; // eax
  signed int v15; // eax
  PDOT11_SSID pDot11Ssid; // rcx
  GUID v17; // xmm0
  const unsigned __int16 *v18; // r8
  PVOID *v19; // rcx
  int v21[4]; // [rsp+20h] [rbp-99h] BYREF
  struct _GUID v22; // [rsp+30h] [rbp-89h] BYREF
  _BYTE v23[20]; // [rsp+40h] [rbp-79h] BYREF
  int v24; // [rsp+54h] [rbp-65h]
  unsigned __int16 v25[44]; // [rsp+60h] [rbp-59h] BYREF
  int v26; // [rsp+B8h] [rbp-1h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids);
  memset_0(v25, 0, 0x68u);
  TetheringInfoForAccessPointName = Windows::Networking::UX::Internal::CAccessPointHelper::_GetTetheringInfoForAccessPointName(
                                      this,
                                      a3,
                                      pConnectionParameters->strProfile,
                                      (struct TETHERING_INTERFACE_INFO *)v25);
  v9 = TetheringInfoForAccessPointName;
  if ( TetheringInfoForAccessPointName >= 0 )
  {
    if ( v26 )
    {
      v22 = *a3;
      *(_OWORD *)v23 = *(_OWORD *)v25;
      v10 = TetheringStationConnectApp((struct _GUID *)v23, &v22, 0);
      v9 = v10;
      if ( v10 > 0 )
        v9 = (unsigned __int16)v10 | 0x80070000;
      if ( (v9 & 0x80000000) != 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids, v9);
      }
      v11 = 1;
    }
    else
    {
      *(struct _GUID *)v23 = *a3;
      v22 = *(struct _GUID *)v25;
      v14 = TetheringStationConnect(&v22, (struct _GUID *)v23, 0);
      v9 = v14;
      if ( v14 > 0 )
        v9 = (unsigned __int16)v14 | 0x80070000;
      if ( (v9 & 0x80000000) != 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids, v9);
      }
      v11 = 0;
    }
    v12 = *a3;
    strProfile = pConnectionParameters->strProfile;
    v24 = 71;
    *(struct _GUID *)&v23[4] = v12;
    *(_DWORD *)v23 = 13;
    NetworkingTriageScenario::GetConnected::UXModelMagicTetheringConnectAction(v23, v11, strProfile, v9);
    goto LABEL_33;
  }
  if ( TetheringInfoForAccessPointName == -2147023728 )
  {
    v15 = WlanConnect(hClientHandle, a3, pConnectionParameters, 0);
    v9 = v15;
    if ( v15 > 0 )
      v9 = (unsigned __int16)v15 | 0x80070000;
    if ( (v9 & 0x80000000) != 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids, v9);
    }
    pDot11Ssid = pConnectionParameters->pDot11Ssid;
    v21[0] = 33;
    if ( !(unsigned int)((__int64 (__fastcall *)(PDOT11_SSID, __int64, unsigned __int16 *, int *))WlanSsidToDisplayName)(
                          pDot11Ssid,
                          1,
                          v25,
                          v21) )
    {
      v17 = *a3;
      v18 = pConnectionParameters->strProfile;
      *(_DWORD *)v23 = 13;
      v24 = 71;
      *(GUID *)&v23[4] = v17;
      NetworkingTriageScenario::GetConnected::UXModelWlanConnectAction(
        (const struct NetworkingTriageScenario::GetConnected::RequiredFields *)v23,
        v25,
        v18,
        v9);
    }
    goto LABEL_33;
  }
  v19 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v9;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      47,
      &WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids,
      (unsigned int)TetheringInfoForAccessPointName);
LABEL_33:
    v19 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 0x40) != 0 )
    WPP_SF_d(v19[2], 48, &WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18002f4c0  push    rbp
0x18002f4c2  push    rbx
0x18002f4c3  push    rsi
0x18002f4c4  push    rdi
0x18002f4c5  push    r12
0x18002f4c7  push    r14
0x18002f4c9  push    r15
0x18002f4cb  lea     rbp, [rsp-27h]
0x18002f4d0  sub     rsp, 0E0h
0x18002f4d7  mov     rax, cs:__security_cookie
0x18002f4de  xor     rax, rsp
0x18002f4e1  mov     [rbp+57h+var_40], rax
0x18002f4e5  mov     rsi, r9
0x18002f4e8  mov     rdi, r8
0x18002f4eb  mov     r14, rdx
0x18002f4ee  mov     rbx, rcx
0x18002f4f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f4f8  lea     r15, WPP_GLOBAL_Control
0x18002f4ff  lea     r12, WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids
0x18002f506  cmp     rcx, r15
0x18002f509  jz      short loc_18002F522
0x18002f50b  test    byte ptr [rcx+1Ch], 40h
0x18002f50f  jz      short loc_18002F522
0x18002f511  mov     rcx, [rcx+10h]
0x18002f515  mov     edx, 2Bh ; '+'
0x18002f51a  mov     r8, r12
0x18002f51d  call    WPP_SF_
0x18002f522  xor     edx, edx; Val
0x18002f524  lea     rcx, [rbp+57h+var_B0]; void *
0x18002f528  lea     r8d, [rdx+68h]; Size
0x18002f52c  call    memset_0
0x18002f531  mov     r8, [rsi+8]; unsigned __int16 *
0x18002f535  lea     r9, [rbp+57h+var_B0]; struct TETHERING_INTERFACE_INFO *
0x18002f539  mov     rdx, rdi; struct _GUID *
0x18002f53c  mov     rcx, rbx; this
0x18002f53f  call    ?_GetTetheringInfoForAccessPointName@CAccessPointHelper@Internal@UX@Networking@Windows@@AEAAJAEBU_GUID@@PEBGPEAUTETHERING_INTERFACE_INFO@@@Z; Windows::Networking::UX::Internal::CAccessPointHelper::_GetTetheringInfoForAccessPointName(_GUID const &,ushort const *,TETHERING_INTERFACE_INFO *)
0x18002f544  mov     ebx, eax
0x18002f546  test    eax, eax
0x18002f548  js      loc_18002F63F
0x18002f54e  movups  xmm0, xmmword ptr [rdi]
0x18002f551  xor     r8d, r8d
0x18002f554  movaps  xmm1, xmmword ptr [rbp+57h+var_B0]
0x18002f558  cmp     [rbp+57h+var_58], r8d
0x18002f55c  jz      loc_18002F5E5
0x18002f562  lea     rdx, [rsp+110h+var_E0]
0x18002f567  lea     rcx, [rbp+57h+var_D0]
0x18002f56b  movdqu  [rsp+110h+var_E0], xmm0
0x18002f571  movdqu  xmmword ptr [rbp+57h+var_D0], xmm1
0x18002f576  call    cs:__imp_?TetheringStationConnectApp@@YAKU_GUID@@0_N@Z; TetheringStationConnectApp(_GUID,_GUID,bool)
0x18002f57c  mov     ebx, eax
0x18002f57e  test    eax, eax
0x18002f580  jle     short loc_18002F58B
0x18002f582  movzx   ebx, ax
0x18002f585  or      ebx, 80070000h
0x18002f58b  test    ebx, ebx
0x18002f58d  jns     short loc_18002F5B5
0x18002f58f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f596  cmp     rcx, r15
0x18002f599  jz      short loc_18002F5B5
0x18002f59b  test    byte ptr [rcx+1Ch], 2
0x18002f59f  jz      short loc_18002F5B5
0x18002f5a1  mov     rcx, [rcx+10h]
0x18002f5a5  mov     edx, 2Ch ; ','
0x18002f5aa  mov     r9d, ebx
0x18002f5ad  mov     r8, r12
0x18002f5b0  call    WPP_SF_d
0x18002f5b5  mov     edx, 1
0x18002f5ba  movups  xmm0, xmmword ptr [rdi]
0x18002f5bd  mov     r8, [rsi+8]
0x18002f5c1  lea     rcx, [rbp+57h+var_D0]
0x18002f5c5  mov     r9d, ebx
0x18002f5c8  mov     [rbp+57h+var_BC], 47h ; 'G'
0x18002f5cf  movdqu  xmmword ptr [rbp+57h+var_D0+4], xmm0
0x18002f5d4  mov     dword ptr [rbp+57h+var_D0], 0Dh
0x18002f5db  call    ?UXModelMagicTetheringConnectAction@GetConnected@NetworkingTriageScenario@@SAXAEBURequiredFields@12@W4MagicTetheringSource@2@PEBGJ@Z; NetworkingTriageScenario::GetConnected::UXModelMagicTetheringConnectAction(NetworkingTriageScenario::GetConnected::RequiredFields const &,NetworkingTriageScenario::MagicTetheringSource,ushort const *,long)
0x18002f5e0  jmp     loc_18002F70B
0x18002f5e5  lea     rdx, [rbp+57h+var_D0]
0x18002f5e9  lea     rcx, [rsp+110h+var_E0]
0x18002f5ee  movdqu  xmmword ptr [rbp+57h+var_D0], xmm0
0x18002f5f3  movdqu  [rsp+110h+var_E0], xmm1
0x18002f5f9  call    cs:__imp_?TetheringStationConnect@@YAKU_GUID@@0_N@Z; TetheringStationConnect(_GUID,_GUID,bool)
0x18002f5ff  mov     ebx, eax
0x18002f601  test    eax, eax
0x18002f603  jle     short loc_18002F60E
0x18002f605  movzx   ebx, ax
0x18002f608  or      ebx, 80070000h
0x18002f60e  test    ebx, ebx
0x18002f610  jns     short loc_18002F638
0x18002f612  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f619  cmp     rcx, r15
0x18002f61c  jz      short loc_18002F638
0x18002f61e  test    byte ptr [rcx+1Ch], 2
0x18002f622  jz      short loc_18002F638
0x18002f624  mov     rcx, [rcx+10h]
0x18002f628  mov     edx, 2Dh ; '-'
0x18002f62d  mov     r9d, ebx
0x18002f630  mov     r8, r12
0x18002f633  call    WPP_SF_d
0x18002f638  xor     edx, edx
0x18002f63a  jmp     loc_18002F5BA
0x18002f63f  cmp     eax, 80070490h
0x18002f644  jnz     loc_18002F6E5
0x18002f64a  xor     r9d, r9d; pReserved
0x18002f64d  mov     r8, rsi; pConnectionParameters
0x18002f650  mov     rdx, rdi; pInterfaceGuid
0x18002f653  mov     rcx, r14; hClientHandle
0x18002f656  call    cs:__imp_WlanConnect
0x18002f65c  mov     ebx, eax
0x18002f65e  test    eax, eax
0x18002f660  jle     short loc_18002F66B
0x18002f662  movzx   ebx, ax
0x18002f665  or      ebx, 80070000h
0x18002f66b  test    ebx, ebx
0x18002f66d  jns     short loc_18002F695
0x18002f66f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f676  cmp     rcx, r15
0x18002f679  jz      short loc_18002F695
0x18002f67b  test    byte ptr [rcx+1Ch], 2
0x18002f67f  jz      short loc_18002F695
0x18002f681  mov     rcx, [rcx+10h]
0x18002f685  mov     edx, 2Eh ; '.'
0x18002f68a  mov     r9d, ebx
0x18002f68d  mov     r8, r12
0x18002f690  call    WPP_SF_d
0x18002f695  mov     rcx, [rsi+10h]
0x18002f699  lea     r9, [rsp+110h+var_F0]
0x18002f69e  lea     r8, [rbp+57h+var_B0]
0x18002f6a2  mov     [rsp+110h+var_F0], 21h ; '!'
0x18002f6aa  mov     edx, 1
0x18002f6af  call    cs:__imp_WlanSsidToDisplayName
0x18002f6b5  test    eax, eax
0x18002f6b7  jnz     short loc_18002F70B
0x18002f6b9  movups  xmm0, xmmword ptr [rdi]
0x18002f6bc  mov     r8, [rsi+8]; unsigned __int16 *
0x18002f6c0  lea     rdx, [rbp+57h+var_B0]; unsigned __int16 *
0x18002f6c4  mov     r9d, ebx; int
0x18002f6c7  mov     dword ptr [rbp+57h+var_D0], 0Dh
0x18002f6ce  lea     rcx, [rbp+57h+var_D0]; struct NetworkingTriageScenario::GetConnected::RequiredFields *
0x18002f6d2  mov     [rbp+57h+var_BC], 47h ; 'G'
0x18002f6d9  movdqu  xmmword ptr [rbp+57h+var_D0+4], xmm0
0x18002f6de  call    ?UXModelWlanConnectAction@GetConnected@NetworkingTriageScenario@@SAXAEBURequiredFields@12@PEBG1J@Z; NetworkingTriageScenario::GetConnected::UXModelWlanConnectAction(NetworkingTriageScenario::GetConnected::RequiredFields const &,ushort const *,ushort const *,long)
0x18002f6e3  jmp     short loc_18002F70B
0x18002f6e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f6ec  cmp     rcx, r15
0x18002f6ef  jz      short loc_18002F731
0x18002f6f1  test    byte ptr [rcx+1Ch], 2
0x18002f6f5  jz      short loc_18002F712
0x18002f6f7  mov     rcx, [rcx+10h]
0x18002f6fb  mov     edx, 2Fh ; '/'
0x18002f700  mov     r9d, eax
0x18002f703  mov     r8, r12
0x18002f706  call    WPP_SF_d
0x18002f70b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f712  cmp     rcx, r15
0x18002f715  jz      short loc_18002F731
0x18002f717  test    byte ptr [rcx+1Ch], 40h
0x18002f71b  jz      short loc_18002F731
0x18002f71d  mov     rcx, [rcx+10h]
0x18002f721  mov     edx, 30h ; '0'
0x18002f726  mov     r9d, ebx
0x18002f729  mov     r8, r12
0x18002f72c  call    WPP_SF_d
0x18002f731  mov     eax, ebx
0x18002f733  mov     rcx, [rbp+57h+var_40]
0x18002f737  xor     rcx, rsp; StackCookie
0x18002f73a  call    __security_check_cookie
0x18002f73f  add     rsp, 0E0h
0x18002f746  pop     r15
0x18002f748  pop     r14
0x18002f74a  pop     r12
0x18002f74c  pop     rdi
0x18002f74d  pop     rsi
0x18002f74e  pop     rbx
0x18002f74f  pop     rbp
0x18002f750  retn
```
