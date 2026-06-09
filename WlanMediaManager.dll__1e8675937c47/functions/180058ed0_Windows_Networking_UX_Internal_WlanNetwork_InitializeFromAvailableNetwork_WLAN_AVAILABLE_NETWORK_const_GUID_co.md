# Windows::Networking::UX::Internal::WlanNetwork::InitializeFromAvailableNetwork(_WLAN_AVAILABLE_NETWORK const *,_GUID const &)

- ea: `0x180058ed0`
- end: `0x180059251`
- name: `?InitializeFromAvailableNetwork@WlanNetwork@Internal@UX@Networking@Windows@@QEAAJPEBU_WLAN_AVAILABLE_NETWORK@@AEBU_GUID@@@Z`
- size: `897`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::WlanNetwork *__hidden this, const struct _WLAN_AVAILABLE_NETWORK *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003b9e0`

## callees

- `0x180004a70`
- `0x180006249`
- `0x1800097b4`
- `0x18000de4c`
- `0x18001d4d4`
- `0x18002f290`
- `0x180058ed0`
- `0x18005a344`
- `0x18005a4d8`
- `0x18005a6dc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180058f23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180058f23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058f67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058f67`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::WlanNetwork::InitializeFromAvailableNetwork(
        Windows::Networking::UX::Internal::WlanNetwork *this,
        const struct _WLAN_AVAILABLE_NETWORK *a2,
        const struct _GUID *a3)
{
  void *v6; // rax
  _OWORD **v7; // rsi
  _OWORD *v8; // rcx
  __int64 v9; // r8
  int *v10; // rdx
  const struct _WLAN_AVAILABLE_NETWORK *v11; // rax
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  int v25; // eax
  int *v26; // rax
  __int64 v27; // rdx
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  int v41; // eax
  int v42; // eax
  unsigned int v43; // esi
  _BOOL8 bSecurityEnabled; // rcx
  bool v46; // al
  WLAN_SIGNAL_QUALITY wlanSignalQuality; // edx
  int v48; // r8d
  WLAN_REASON_CODE wlanNotConnectableReason; // ecx
  WLAN_REASON_CODE v50; // ecx
  WLAN_REASON_CODE v51; // ecx
  WLAN_REASON_CODE v52; // ecx
  ULONG uNumberOfPhyTypes; // ecx
  int v54; // ebx
  __int64 v55; // rdx
  int v56[160]; // [rsp+20h] [rbp-298h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+0h]
  LPVOID pv; // [rsp+2C0h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_986cb96e1ae83fcb14083ce1067b4995_Traceguids);
  v6 = CoTaskMemAlloc(0x274u);
  pv = v6;
  if ( v6 )
    memset_0(v6, 0, 0x274u);
  v7 = (_OWORD **)((char *)this + 248);
  wistd::unique_ptr<_L2_NOTIFICATION_DATA,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
    (char *)this + 248,
    &pv);
  if ( pv )
    CoTaskMemFree(pv);
  v8 = *v7;
  if ( !*v7 )
  {
    v54 = -2147024882;
    v55 = 1111;
    goto LABEL_39;
  }
  v9 = 4;
  v10 = v56;
  v11 = a2;
  do
  {
    v12 = *(_OWORD *)&v11->strProfileName[8];
    *(_OWORD *)v10 = *(_OWORD *)v11->strProfileName;
    v13 = *(_OWORD *)&v11->strProfileName[16];
    *((_OWORD *)v10 + 1) = v12;
    v14 = *(_OWORD *)&v11->strProfileName[24];
    *((_OWORD *)v10 + 2) = v13;
    v15 = *(_OWORD *)&v11->strProfileName[32];
    *((_OWORD *)v10 + 3) = v14;
    v16 = *(_OWORD *)&v11->strProfileName[40];
    *((_OWORD *)v10 + 4) = v15;
    v17 = *(_OWORD *)&v11->strProfileName[48];
    *((_OWORD *)v10 + 5) = v16;
    v18 = *(_OWORD *)&v11->strProfileName[56];
    v11 = (const struct _WLAN_AVAILABLE_NETWORK *)((char *)v11 + 128);
    *((_OWORD *)v10 + 6) = v17;
    *((_OWORD *)v10 + 7) = v18;
    v10 += 32;
    --v9;
  }
  while ( v9 );
  v19 = *(_OWORD *)&v11->strProfileName[8];
  *(_OWORD *)v10 = *(_OWORD *)v11->strProfileName;
  v20 = *(_OWORD *)&v11->strProfileName[16];
  *((_OWORD *)v10 + 1) = v19;
  v21 = *(_OWORD *)&v11->strProfileName[24];
  *((_OWORD *)v10 + 2) = v20;
  v22 = *(_OWORD *)&v11->strProfileName[32];
  *((_OWORD *)v10 + 3) = v21;
  v23 = *(_OWORD *)&v11->strProfileName[40];
  *((_OWORD *)v10 + 4) = v22;
  v24 = *(_OWORD *)&v11->strProfileName[48];
  v25 = *(_DWORD *)&v11->strProfileName[56];
  *((_OWORD *)v10 + 5) = v23;
  *((_OWORD *)v10 + 6) = v24;
  v10[28] = v25;
  v26 = v56;
  v27 = 4;
  do
  {
    v28 = *((_OWORD *)v26 + 1);
    *v8 = *(_OWORD *)v26;
    v29 = *((_OWORD *)v26 + 2);
    v8[1] = v28;
    v30 = *((_OWORD *)v26 + 3);
    v8[2] = v29;
    v31 = *((_OWORD *)v26 + 4);
    v8[3] = v30;
    v32 = *((_OWORD *)v26 + 5);
    v8[4] = v31;
    v33 = *((_OWORD *)v26 + 6);
    v8[5] = v32;
    v34 = *((_OWORD *)v26 + 7);
    v26 += 32;
    v8[6] = v33;
    v8[7] = v34;
    v8 += 8;
    --v27;
  }
  while ( v27 );
  v35 = *((_OWORD *)v26 + 1);
  *v8 = *(_OWORD *)v26;
  v36 = *((_OWORD *)v26 + 2);
  v8[1] = v35;
  v37 = *((_OWORD *)v26 + 3);
  v8[2] = v36;
  v38 = *((_OWORD *)v26 + 4);
  v8[3] = v37;
  v39 = *((_OWORD *)v26 + 5);
  v8[4] = v38;
  v40 = *((_OWORD *)v26 + 6);
  v41 = v26[28];
  v8[5] = v39;
  v8[6] = v40;
  *((_DWORD *)v8 + 28) = v41;
  v42 = Windows::Networking::UX::Internal::WlanNetwork::_SetName(this, a2);
  v43 = v42;
  if ( v42 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45C,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlannetwork.cpp",
      (const char *)(unsigned int)v42,
      v56[0]);
    return v43;
  }
  bSecurityEnabled = a2->bSecurityEnabled;
  *((_BYTE *)this + 60) = bSecurityEnabled;
  *((_DWORD *)this + 49) = a2->dot11DefaultAuthAlgorithm;
  *((_DWORD *)this + 50) = a2->dot11DefaultCipherAlgorithm;
  v46 = bSecurityEnabled && a2->dot11DefaultAuthAlgorithm != 10;
  *((_BYTE *)this + 61) = v46;
  *((_DWORD *)this + 14) = !a2->bNetworkConnectable;
  wlanSignalQuality = a2->wlanSignalQuality;
  *((_DWORD *)this + 48) = wlanSignalQuality;
  *((_DWORD *)this + 17) = Windows::Networking::UX::Internal::WlanNetwork::_WlanSignalValueToBar(
                             (Windows::Networking::UX::Internal::WlanNetwork *)bSecurityEnabled,
                             wlanSignalQuality);
  *((_DWORD *)this + 20) = 0;
  if ( !v48 )
  {
    wlanNotConnectableReason = a2->wlanNotConnectableReason;
    if ( wlanNotConnectableReason == 163843 )
    {
      *((_DWORD *)this + 20) = 2;
      goto LABEL_30;
    }
    if ( wlanNotConnectableReason - 720897 > 0x11 )
    {
      *((_DWORD *)this + 20) = 1;
    }
    else
    {
      v50 = wlanNotConnectableReason - 720901;
      if ( !v50 )
      {
LABEL_27:
        *((_DWORD *)this + 20) = 10;
        goto LABEL_30;
      }
      v51 = v50 - 1;
      if ( v51 )
      {
        v52 = v51 - 4;
        if ( !v52 || v52 == 6 )
          goto LABEL_27;
      }
      else
      {
        *((_DWORD *)this + 20) = 11;
      }
    }
  }
LABEL_30:
  uNumberOfPhyTypes = 8;
  if ( a2->uNumberOfPhyTypes < 8 )
    uNumberOfPhyTypes = a2->uNumberOfPhyTypes;
  *((_DWORD *)this + 51) = uNumberOfPhyTypes;
  memcpy_0((char *)this + 212, a2->dot11PhyTypes, 4LL * uNumberOfPhyTypes);
  *((struct _GUID *)this + 16) = *a3;
  v54 = Windows::Networking::UX::Internal::WlanNetwork::_SetSignature(this, a2);
  if ( v54 < 0 )
  {
    v55 = 1123;
LABEL_39:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v55,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlannetwork.cpp",
      (const char *)(unsigned int)v54,
      v56[0]);
    return (unsigned int)v54;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_986cb96e1ae83fcb14083ce1067b4995_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x180058ed0  mov     [rsp+arg_8], rbx
0x180058ed5  mov     [rsp+arg_10], rbp
0x180058eda  push    rsi
0x180058edb  push    rdi
0x180058edc  push    r15
0x180058ede  sub     rsp, 2A0h
0x180058ee5  mov     rbp, r8
0x180058ee8  mov     rdi, rdx
0x180058eeb  mov     rbx, rcx
0x180058eee  mov     rcx, cs:WPP_GLOBAL_Control
0x180058ef5  lea     r15, WPP_GLOBAL_Control
0x180058efc  cmp     rcx, r15
0x180058eff  jz      short loc_180058F1C
0x180058f01  test    byte ptr [rcx+1Ch], 40h
0x180058f05  jz      short loc_180058F1C
0x180058f07  mov     rcx, [rcx+10h]
0x180058f0b  lea     r8, WPP_986cb96e1ae83fcb14083ce1067b4995_Traceguids
0x180058f12  mov     edx, 36h ; '6'
0x180058f17  call    WPP_SF_
0x180058f1c  mov     esi, 274h
0x180058f21  mov     ecx, esi; cb
0x180058f23  call    cs:__imp_CoTaskMemAlloc
0x180058f29  mov     [rsp+2B8h+pv], rax
0x180058f31  test    rax, rax
0x180058f34  jz      short loc_180058F43
0x180058f36  mov     r8d, esi; Size
0x180058f39  xor     edx, edx; Val
0x180058f3b  mov     rcx, rax; void *
0x180058f3e  call    memset_0
0x180058f43  lea     rsi, [rbx+0F8h]
0x180058f4a  mov     rcx, rsi
0x180058f4d  lea     rdx, [rsp+2B8h+pv]
0x180058f55  call    ??4?$unique_ptr@U_L2_NOTIFICATION_DATA@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<_L2_NOTIFICATION_DATA,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<_L2_NOTIFICATION_DATA,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x180058f5a  mov     rcx, [rsp+2B8h+pv]; pv
0x180058f62  test    rcx, rcx
0x180058f65  jz      short loc_180058F6D
0x180058f67  call    cs:__imp_CoTaskMemFree
0x180058f6d  mov     rcx, [rsi]
0x180058f70  test    rcx, rcx
0x180058f73  jz      loc_180059216
0x180058f79  mov     r8d, 4
0x180058f7f  lea     rdx, [rsp+2B8h+var_298]
0x180058f84  mov     rax, rdi
0x180058f87  lea     r9d, [r8+7Ch]
0x180058f8b  movups  xmm0, xmmword ptr [rax]
0x180058f8e  movups  xmm1, xmmword ptr [rax+10h]
0x180058f92  movups  xmmword ptr [rdx], xmm0
0x180058f95  movups  xmm0, xmmword ptr [rax+20h]
0x180058f99  movups  xmmword ptr [rdx+10h], xmm1
0x180058f9d  movups  xmm1, xmmword ptr [rax+30h]
0x180058fa1  movups  xmmword ptr [rdx+20h], xmm0
0x180058fa5  movups  xmm0, xmmword ptr [rax+40h]
0x180058fa9  movups  xmmword ptr [rdx+30h], xmm1
0x180058fad  movups  xmm1, xmmword ptr [rax+50h]
0x180058fb1  movups  xmmword ptr [rdx+40h], xmm0
0x180058fb5  movups  xmm0, xmmword ptr [rax+60h]
0x180058fb9  movups  xmmword ptr [rdx+50h], xmm1
0x180058fbd  movups  xmm1, xmmword ptr [rax+70h]
0x180058fc1  add     rax, r9
0x180058fc4  movups  xmmword ptr [rdx+60h], xmm0
0x180058fc8  movups  xmmword ptr [rdx+70h], xmm1
0x180058fcc  add     rdx, r9
0x180058fcf  sub     r8, 1
0x180058fd3  jnz     short loc_180058F8B
0x180058fd5  movups  xmm0, xmmword ptr [rax]
0x180058fd8  movups  xmm1, xmmword ptr [rax+10h]
0x180058fdc  movups  xmmword ptr [rdx], xmm0
0x180058fdf  movups  xmm0, xmmword ptr [rax+20h]
0x180058fe3  movups  xmmword ptr [rdx+10h], xmm1
0x180058fe7  movups  xmm1, xmmword ptr [rax+30h]
0x180058feb  movups  xmmword ptr [rdx+20h], xmm0
0x180058fef  movups  xmm0, xmmword ptr [rax+40h]
0x180058ff3  movups  xmmword ptr [rdx+30h], xmm1
0x180058ff7  movups  xmm1, xmmword ptr [rax+50h]
0x180058ffb  movups  xmmword ptr [rdx+40h], xmm0
0x180058fff  movups  xmm0, xmmword ptr [rax+60h]
0x180059003  mov     eax, [rax+70h]
0x180059006  movups  xmmword ptr [rdx+50h], xmm1
0x18005900a  movups  xmmword ptr [rdx+60h], xmm0
0x18005900e  mov     [rdx+70h], eax
0x180059011  lea     rax, [rsp+2B8h+var_298]
0x180059016  lea     edx, [r8+4]
0x18005901a  movups  xmm0, xmmword ptr [rax]
0x18005901d  movups  xmm1, xmmword ptr [rax+10h]
0x180059021  movups  xmmword ptr [rcx], xmm0
0x180059024  movups  xmm0, xmmword ptr [rax+20h]
0x180059028  movups  xmmword ptr [rcx+10h], xmm1
0x18005902c  movups  xmm1, xmmword ptr [rax+30h]
0x180059030  movups  xmmword ptr [rcx+20h], xmm0
0x180059034  movups  xmm0, xmmword ptr [rax+40h]
0x180059038  movups  xmmword ptr [rcx+30h], xmm1
0x18005903c  movups  xmm1, xmmword ptr [rax+50h]
0x180059040  movups  xmmword ptr [rcx+40h], xmm0
0x180059044  movups  xmm0, xmmword ptr [rax+60h]
0x180059048  movups  xmmword ptr [rcx+50h], xmm1
0x18005904c  movups  xmm1, xmmword ptr [rax+70h]
0x180059050  add     rax, r9
0x180059053  movups  xmmword ptr [rcx+60h], xmm0
0x180059057  movups  xmmword ptr [rcx+70h], xmm1
0x18005905b  add     rcx, r9
0x18005905e  sub     rdx, 1
0x180059062  jnz     short loc_18005901A
0x180059064  movups  xmm0, xmmword ptr [rax]
0x180059067  mov     rdx, rdi; struct _WLAN_AVAILABLE_NETWORK *
0x18005906a  movups  xmm1, xmmword ptr [rax+10h]
0x18005906e  movups  xmmword ptr [rcx], xmm0
0x180059071  movups  xmm0, xmmword ptr [rax+20h]
0x180059075  movups  xmmword ptr [rcx+10h], xmm1
0x180059079  movups  xmm1, xmmword ptr [rax+30h]
0x18005907d  movups  xmmword ptr [rcx+20h], xmm0
0x180059081  movups  xmm0, xmmword ptr [rax+40h]
0x180059085  movups  xmmword ptr [rcx+30h], xmm1
0x180059089  movups  xmm1, xmmword ptr [rax+50h]
0x18005908d  movups  xmmword ptr [rcx+40h], xmm0
0x180059091  movups  xmm0, xmmword ptr [rax+60h]
0x180059095  mov     eax, [rax+70h]
0x180059098  movups  xmmword ptr [rcx+50h], xmm1
0x18005909c  movups  xmmword ptr [rcx+60h], xmm0
0x1800590a0  mov     [rcx+70h], eax
0x1800590a3  mov     rcx, rbx; this
0x1800590a6  call    ?_SetName@WlanNetwork@Internal@UX@Networking@Windows@@IEAAJPEBU_WLAN_AVAILABLE_NETWORK@@@Z; Windows::Networking::UX::Internal::WlanNetwork::_SetName(_WLAN_AVAILABLE_NETWORK const *)
0x1800590ab  mov     esi, eax
0x1800590ad  test    eax, eax
0x1800590af  jns     short loc_1800590D4
0x1800590b1  mov     rcx, [rsp+2B8h]; this
0x1800590b9  lea     r8, aOnecoreuapNetU_26; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x1800590c0  mov     r9d, eax; char *
0x1800590c3  mov     edx, 45Ch; void *
0x1800590c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800590cd  mov     eax, esi
0x1800590cf  jmp     loc_180059239
0x1800590d4  mov     ecx, [rdi+260h]; this
0x1800590da  test    ecx, ecx
0x1800590dc  setnz   al
0x1800590df  mov     [rbx+3Ch], al
0x1800590e2  mov     eax, [rdi+264h]
0x1800590e8  mov     [rbx+0C4h], eax
0x1800590ee  mov     eax, [rdi+268h]
0x1800590f4  mov     [rbx+0C8h], eax
0x1800590fa  test    ecx, ecx
0x1800590fc  jz      short loc_18005910B
0x1800590fe  cmp     dword ptr [rdi+264h], 0Ah
0x180059105  jz      short loc_18005910B
0x180059107  mov     al, 1
0x180059109  jmp     short loc_18005910D
0x18005910b  xor     eax, eax
0x18005910d  mov     [rbx+3Dh], al
0x180059110  xor     eax, eax
0x180059112  mov     r8d, [rdi+22Ch]
0x180059119  test    r8d, r8d
0x18005911c  setz    al
0x18005911f  mov     [rbx+38h], eax
0x180059122  mov     edx, [rdi+25Ch]; unsigned int
0x180059128  mov     [rbx+0C0h], edx
0x18005912e  call    ?_WlanSignalValueToBar@WlanNetwork@Internal@UX@Networking@Windows@@IEAAKK@Z; Windows::Networking::UX::Internal::WlanNetwork::_WlanSignalValueToBar(ulong)
0x180059133  mov     [rbx+44h], eax
0x180059136  mov     dword ptr [rbx+50h], 0
0x18005913d  test    r8d, r8d
0x180059140  jnz     short loc_180059194
0x180059142  mov     ecx, [rdi+230h]
0x180059148  cmp     ecx, 28003h
0x18005914e  jnz     short loc_180059159
0x180059150  mov     dword ptr [rbx+50h], 2
0x180059157  jmp     short loc_180059194
0x180059159  lea     eax, [rcx-0B0001h]
0x18005915f  cmp     eax, 11h
0x180059162  ja      short loc_18005918D
0x180059164  sub     ecx, 0B0005h
0x18005916a  jz      short loc_18005917B
0x18005916c  sub     ecx, 1
0x18005916f  jz      short loc_180059184
0x180059171  sub     ecx, 4
0x180059174  jz      short loc_18005917B
0x180059176  cmp     ecx, 6
0x180059179  jnz     short loc_180059194
0x18005917b  mov     dword ptr [rbx+50h], 0Ah
0x180059182  jmp     short loc_180059194
0x180059184  mov     dword ptr [rbx+50h], 0Bh
0x18005918b  jmp     short loc_180059194
0x18005918d  mov     dword ptr [rbx+50h], 1
0x180059194  mov     eax, [rdi+234h]
0x18005919a  lea     rdx, [rdi+238h]; Src
0x1800591a1  mov     ecx, 8
0x1800591a6  cmp     eax, ecx
0x1800591a8  cmovb   ecx, eax
0x1800591ab  mov     r8d, ecx
0x1800591ae  mov     [rbx+0CCh], ecx
0x1800591b4  lea     rcx, [rbx+0D4h]; void *
0x1800591bb  shl     r8, 2; Size
0x1800591bf  call    memcpy_0
0x1800591c4  movups  xmm0, xmmword ptr [rbp+0]
0x1800591c8  mov     rdx, rdi; struct _WLAN_AVAILABLE_NETWORK *
0x1800591cb  mov     rcx, rbx; this
0x1800591ce  movdqu  xmmword ptr [rbx+100h], xmm0
0x1800591d6  call    ?_SetSignature@WlanNetwork@Internal@UX@Networking@Windows@@IEAAJPEBU_WLAN_AVAILABLE_NETWORK@@@Z; Windows::Networking::UX::Internal::WlanNetwork::_SetSignature(_WLAN_AVAILABLE_NETWORK const *)
0x1800591db  mov     ebx, eax
0x1800591dd  test    eax, eax
0x1800591df  jns     short loc_1800591E8
0x1800591e1  mov     edx, 463h
0x1800591e6  jmp     short loc_180059220
0x1800591e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800591ef  cmp     rcx, r15
0x1800591f2  jz      short loc_180059212
0x1800591f4  test    byte ptr [rcx+1Ch], 40h
0x1800591f8  jz      short loc_180059212
0x1800591fa  mov     rcx, [rcx+10h]
0x1800591fe  lea     r8, WPP_986cb96e1ae83fcb14083ce1067b4995_Traceguids
0x180059205  mov     edx, 37h ; '7'
0x18005920a  xor     r9d, r9d
0x18005920d  call    WPP_SF_d
0x180059212  xor     eax, eax
0x180059214  jmp     short loc_180059239
0x180059216  mov     ebx, 8007000Eh
0x18005921b  mov     edx, 457h; void *
0x180059220  mov     rcx, [rsp+2B8h]; this
0x180059228  lea     r8, aOnecoreuapNetU_26; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18005922f  mov     r9d, ebx; char *
0x180059232  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059237  mov     eax, ebx
0x180059239  lea     r11, [rsp+2B8h+var_18]
0x180059241  mov     rbx, [r11+28h]
0x180059245  mov     rbp, [r11+30h]
0x180059249  mov     rsp, r11
0x18005924c  pop     r15
0x18005924e  pop     rdi
0x18005924f  pop     rsi
0x180059250  retn
```
