# RoutePolicyAsyncRedirectRoutine

- ea: `0x140007280`
- end: `0x140007d21`
- name: `RoutePolicyAsyncRedirectRoutine`
- size: `2721`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140001008`
- `0x1400012f0`
- `0x1400013b0`
- `0x140001580`
- `0x1400018cc`
- `0x14000225c`
- `0x140002d00`
- `0x140003dac`
- `0x140004e54`
- `0x14000646c`
- `0x140006cc4`
- `0x140006e28`
- `0x140006f7c`
- `0x140007050`
- `0x140007280`
- `0x140007d28`
- `0x140007d7c`
- `0x14000935c`
- `0x140009a70`
- `0x140009bbc`
- `0x14000a680`
- `0x14000a6c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140007696`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400078c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007ca9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007696`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400078c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007ca9`
- `ntoskrnl!ExAllocatePool2` at `0x1400075da`
- `ntoskrnl!ExAllocatePool2` at `0x140007642`
- `ntoskrnl!ExAllocatePool2` at `0x1400075da`
- `ntoskrnl!ExAllocatePool2` at `0x140007642`

## string_xrefs

- `0x140007721`: `No cache entry for this request`

## pseudocode

```c
void __fastcall RoutePolicyAsyncRedirectRoutine(__int64 a1)
{
  unsigned __int16 *v1; // r14
  __int64 v2; // rcx
  __int64 v3; // r8
  const struct _WCM_ROUTE_POLICY_NETWORK_REQUEST *v4; // rdx
  int v5; // ebx
  int v6; // r8d
  int v7; // r9d
  int v8; // ecx
  PVOID v9; // rsi
  char *v10; // rbx
  char *v11; // rdi
  __int16 v12; // ax
  bool v13; // zf
  __int64 *v14; // r8
  __int64 v15; // rax
  int v16; // eax
  char *v17; // rdx
  PVOID *v18; // rax
  void *v19; // r8
  struct _EVENT_DATA_DESCRIPTOR *v20; // rcx
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  char **Ptr; // r15
  __int64 Pool2; // rax
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  _QWORD *v29; // rbx
  int v30; // ecx
  void *v31; // r8
  int v32; // r9d
  PVOID *i; // rdi
  unsigned int v34; // eax
  unsigned int v35; // edi
  unsigned __int16 *v36; // rcx
  unsigned __int16 v37; // r12
  int v38; // eax
  int v39; // ecx
  int v40; // r8d
  int v41; // r9d
  PVOID v42; // r13
  int v43; // r14d
  char *v44; // rdi
  char *v45; // rsi
  int v46; // eax
  int v47; // eax
  unsigned __int16 v48; // r12
  char v49; // r14
  __int64 v50; // rdi
  struct _EVENT_DATA_DESCRIPTOR v51; // xmm6
  char **v52; // rdi
  char *v53; // rsi
  _QWORD *v54; // rsi
  _NET_LUID_LH v55; // rax
  char *v56; // rax
  char **v57; // rcx
  const union _NET_LUID_LH *v58; // r8
  _QWORD *v59; // rax
  int v60; // r9d
  int v61; // r8d
  char v62; // di
  void **v63; // [rsp+28h] [rbp-E0h]
  char v64; // [rsp+38h] [rbp-D0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v65; // [rsp+48h] [rbp-C0h] BYREF
  __int16 v66; // [rsp+58h] [rbp-B0h] BYREF
  __int16 v67; // [rsp+5Ah] [rbp-AEh] BYREF
  const char *v68; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD v69[3]; // [rsp+68h] [rbp-A0h] BYREF
  char v70; // [rsp+80h] [rbp-88h]
  struct _EVENT_DATA_DESCRIPTOR v71; // [rsp+88h] [rbp-80h] BYREF
  __int64 v72; // [rsp+98h] [rbp-70h] BYREF
  __int128 v73; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v74; // [rsp+B0h] [rbp-58h]
  __int128 v75; // [rsp+C0h] [rbp-48h]
  __int64 v76; // [rsp+D0h] [rbp-38h] BYREF
  int v77; // [rsp+E1h] [rbp-27h]
  __int16 v78; // [rsp+E5h] [rbp-23h]
  char v79; // [rsp+E7h] [rbp-21h]
  int v80; // [rsp+F0h] [rbp-18h] BYREF
  PVOID Memory[2]; // [rsp+F8h] [rbp-10h] BYREF
  _NET_LUID_LH v82; // [rsp+108h] [rbp+0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v83; // [rsp+118h] [rbp+10h] BYREF
  char *v84; // [rsp+128h] [rbp+20h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v85; // [rsp+138h] [rbp+30h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v86; // [rsp+158h] [rbp+50h] BYREF
  __int16 *v87; // [rsp+178h] [rbp+70h]
  __int64 v88; // [rsp+180h] [rbp+78h]
  __int16 *v89; // [rsp+188h] [rbp+80h]
  __int64 v90; // [rsp+190h] [rbp+88h]
  char *v91; // [rsp+198h] [rbp+90h]
  __int64 v92; // [rsp+1A0h] [rbp+98h]
  PVOID *v93; // [rsp+1A8h] [rbp+A0h]
  __int64 v94; // [rsp+1B0h] [rbp+A8h]
  __int64 *v95; // [rsp+1B8h] [rbp+B0h]
  int v96; // [rsp+1C0h] [rbp+B8h]
  int v97; // [rsp+1C4h] [rbp+BCh]
  struct _EVENT_DATA_DESCRIPTOR v98; // [rsp+1C8h] [rbp+C0h] BYREF
  int *v99; // [rsp+1E8h] [rbp+E0h]
  __int64 v100; // [rsp+1F0h] [rbp+E8h]
  struct _EVENT_DATA_DESCRIPTOR v101; // [rsp+1F8h] [rbp+F0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR *v102; // [rsp+218h] [rbp+110h]
  __int64 v103; // [rsp+220h] [rbp+118h]

  v76 = a1;
  v72 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
          WdfDriverGlobals,
          a1,
          off_140012040);
  Memory[0] = 0;
  *(_DWORD *)(v72 + 8) = 4098;
  v69[0] = &v72;
  v69[1] = &v83;
  v75 = 0u;
  v69[2] = &v76;
  v82.Value = 0;
  v83.Ptr = 0;
  LOBYTE(v83.Size) = 0;
  v73 = 0;
  v74 = 0;
  v1 = *(unsigned __int16 **)(v72 + 72);
  LODWORD(v68) = 1;
  v70 = 1;
  v5 = NetioEnumerateAddress(v2, *v1, v3, Memory);
  if ( v5 >= 0 )
  {
    v9 = Memory[0];
    v10 = (char *)Memory[0] + 8;
    v11 = (char *)Memory[0] + 80 * *(unsigned int *)Memory[0] + 8;
    while ( 1 )
    {
      if ( v10 == v11 )
      {
LABEL_20:
        FreeMibTable(v9);
        goto LABEL_21;
      }
      v12 = *v1;
      if ( *(_WORD *)v10 == *v1 )
      {
        if ( v12 == 2 )
        {
          v13 = *((_DWORD *)v10 + 1) == *((_DWORD *)v1 + 1);
        }
        else
        {
          if ( v12 != 23 )
            MicrosoftTelemetryAssertTriggeredNoArgsKM();
          if ( *((_QWORD *)v10 + 2) != *((_QWORD *)v1 + 2) )
            goto LABEL_16;
          v13 = *((_QWORD *)v10 + 1) == *((_QWORD *)v1 + 1);
        }
        if ( v13 )
        {
          *(_QWORD *)&v75 = *((_QWORD *)v10 + 4);
          goto LABEL_20;
        }
      }
LABEL_16:
      v10 += 80;
    }
  }
  v8 = (int)Memory[0];
  if ( Memory[0] )
    FreeMibTable(Memory[0]);
  if ( v5 != -1073741275 && (unsigned int)dword_140012050 > 3 )
  {
    v80 = v5;
    Memory[0] = "InterfaceLuidFromAddressFailed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v8,
      (unsigned int)&dword_14001047C,
      v6,
      v7,
      (__int64)Memory,
      (__int64)&v80);
  }
LABEL_21:
  if ( (unsigned int)dword_140012050 > 4 )
  {
    v14 = *(__int64 **)(v72 + 56);
    Memory[0] = (PVOID)v75;
    v64 = *(_BYTE *)(v72 + 64);
    v66 = **(_WORD **)(v72 + 72);
    v67 = *(_WORD *)(v72 + 66);
    if ( v14 )
    {
      v15 = -1;
      do
        ++v15;
      while ( *((_WORD *)v14 + v15) );
      v16 = 2 * v15 + 2;
    }
    else
    {
      v14 = &qword_14000C868;
      v16 = 2;
    }
    v96 = v16;
    v95 = v14;
    v93 = Memory;
    v97 = 0;
    v91 = &v64;
    v94 = 8;
    v89 = &v66;
    v92 = 1;
    v87 = &v67;
    v90 = 2;
    v88 = 2;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140012050, (unsigned __int8 *)&byte_14000F499, 0, 0, 7u, &v86);
  }
  if ( (_QWORD)v75 )
  {
    if ( (unsigned int)dword_140012050 <= 4 )
      goto LABEL_32;
    v68 = "5G route selection policies will not be applied to traffic with source binding";
    v17 = &byte_14000F69F;
    v18 = (PVOID *)&v68;
    goto LABEL_31;
  }
  *((_QWORD *)&v73 + 1) = *(_QWORD *)(v72 + 56);
  LODWORD(v73) = 2048;
  WORD4(v75) = **(_WORD **)(v72 + 72);
  if ( !RoutePolicyCache::DoesRequestMatchAnyRule((RoutePolicyCache *)&v73, v4) )
  {
    if ( (unsigned int)dword_140012050 > 4 )
    {
      Memory[0] = "Request matches no rules or does source-bind";
      v17 = (char *)&unk_14000E9C0;
      v18 = Memory;
LABEL_31:
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v8,
        (_DWORD)v17,
        v6,
        v7,
        (__int64)v18);
    }
LABEL_32:
    v70 = 0;
    lambda_abec86eb39d26369503aaafa1ba2d18c_::operator()((__int64)v69);
    if ( v83.Ptr )
    {
      v20 = &v65;
      v65 = v83;
      goto LABEL_134;
    }
    goto LABEL_135;
  }
  v65.Ptr = ExAllocatePool2(64, 48, 1684435058);
  Ptr = (char **)v65.Ptr;
  if ( !v65.Ptr )
  {
    if ( (unsigned int)dword_140012050 > 2 )
    {
      v80 = -1073741670;
      Memory[0] = "Failed to allocate INTERFACE_CONTEXT";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v21,
        (unsigned int)&unk_1400100F8,
        v22,
        v23,
        (__int64)Memory,
        (__int64)&v80);
    }
    goto LABEL_32;
  }
  Pool2 = ExAllocatePool2(64, 136, 1684435058);
  v29 = (_QWORD *)Pool2;
  if ( !Pool2 )
  {
    if ( (unsigned int)dword_140012050 > 2 )
    {
      v80 = -1073741670;
      Memory[0] = "Failed to allocate CONNECTION_CONTEXT";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v26,
        (unsigned int)byte_14000FC43,
        v27,
        v28,
        (__int64)Memory,
        (__int64)&v80);
    }
    goto LABEL_43;
  }
  if ( (int)CreateTimerWaitFlowEstablish(Pool2) < 0 )
  {
LABEL_45:
    FreeConnectionContext(v29);
LABEL_43:
    ExFreePoolWithTag(Ptr, 0x64667072u);
    goto LABEL_32;
  }
  v84 = 0;
  AcquireSpinLock(Memory, &g_cacheLock);
  for ( i = (PVOID *)g_cacheListHead; ; i = (PVOID *)*i )
  {
    if ( i == &g_cacheListHead )
    {
      if ( Memory[0] )
      {
        v71 = *(struct _EVENT_DATA_DESCRIPTOR *)Memory;
        SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)&v71);
      }
      if ( (unsigned int)dword_140012050 > 4 )
      {
        Memory[0] = "No cache entry for this request";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v30,
          (unsigned int)&unk_14000F780,
          (_DWORD)v31,
          v32,
          (__int64)Memory);
      }
      if ( v82.Value )
        RoutePolicyCallout::Wrapper_WcmKReleaseInterface(
          *((RoutePolicyCallout **)RoutePolicyCallout::g_pCalloutContext + 4),
          (void *)v82.Value,
          v31);
      v82.Value = 0;
      v34 = RoutePolicyCallout::Wrapper_WcmKGetInterfaceForNetworkRequest(
              *((RoutePolicyCallout **)RoutePolicyCallout::g_pCalloutContext + 4),
              &v73,
              (const struct _WCM_ROUTE_POLICY_NETWORK_REQUEST *)&v84,
              &v82,
              v63);
      v35 = v34;
      if ( v34 )
      {
        if ( (unsigned int)dword_140012050 > 2 )
        {
          v80 = v34;
          v100 = 4;
          v99 = &v80;
          tlgWriteTransfer_EtwWriteTransfer(
            (__int64)&dword_140012050,
            (unsigned __int8 *)&byte_14000F507,
            0,
            0,
            3u,
            &v98);
        }
        if ( v35 == 65 )
          *(_DWORD *)(v72 + 8) = 4097;
      }
      goto LABEL_61;
    }
    if ( (unsigned __int8)operator__(i + 2, &v73) )
      break;
  }
  v84 = (char *)i[8];
  if ( Memory[0] )
    SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)Memory);
LABEL_61:
  if ( !v84 )
  {
    if ( (unsigned int)dword_140012050 > 4 )
      tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140012050, (unsigned __int8 *)&qword_14000EDC8, 0, 0, 2u, &v85);
    goto LABEL_45;
  }
  Memory[0] = 0;
  v36 = *(unsigned __int16 **)(v72 + 72);
  v37 = *v36;
  v38 = NetioEnumerateAddress(v36, *v36, v31, Memory);
  if ( v38 < 0 )
  {
    if ( (unsigned int)dword_140012050 > 2 )
    {
      v80 = v38;
      v68 = "GetUnicastIpAddressTable failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_140012050,
        (unsigned int)&unk_14000FB90,
        v40,
        v41,
        (__int64)&v68,
        (__int64)&v80);
    }
    if ( Memory[0] )
      FreeMibTable(Memory[0]);
    FreeConnectionContext(v29);
    ExFreePoolWithTag(Ptr, 0x64667072u);
    v70 = 0;
    lambda_abec86eb39d26369503aaafa1ba2d18c_::operator()((__int64)v69);
    if ( v83.Ptr )
    {
      v20 = &v71;
      v71 = v83;
      goto LABEL_134;
    }
    goto LABEL_135;
  }
  v42 = Memory[0];
  v43 = 1;
  v44 = (char *)Memory[0] + 8;
  v45 = (char *)Memory[0] + 80 * *(unsigned int *)Memory[0] + 8;
  if ( (char *)Memory[0] + 8 == v45 )
    goto LABEL_100;
  do
  {
    if ( *((char **)v44 + 4) != v84 || *((_DWORD *)v44 + 16) != 4 || v44[61] )
      goto LABEL_98;
    if ( v37 == 2 )
    {
      v46 = *((_DWORD *)v44 + 1);
      if ( v46 != -1 )
      {
        if ( (v46 & 0xF0) == 0xE0 )
        {
          if ( (v46 & 0xFFFFFF) != 0xE0 )
          {
            if ( (_WORD)v46 == 0xFFEF )
            {
              v39 = 4;
            }
            else
            {
              v39 = 14;
              if ( (_BYTE)v46 == 0xEF )
                v39 = 5;
            }
            goto LABEL_90;
          }
        }
        else
        {
          v80 = 0;
          if ( (_WORD)v46 != 0xFEA9 )
          {
            v39 = 14;
            if ( (_BYTE)v46 != 127 )
              goto LABEL_90;
          }
        }
      }
      v39 = 2;
LABEL_90:
      if ( v39 <= v43 )
        goto LABEL_97;
      v43 = v39;
      *((_OWORD *)v29 + 4) = *(_OWORD *)v44;
      goto LABEL_96;
    }
    if ( v37 != 23 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    v47 = Ipv6AddressScope(v44 + 8);
    if ( v47 > v43 )
    {
      v43 = v47;
      *((_OWORD *)v29 + 4) = *(_OWORD *)v44;
      *(_OWORD *)((char *)v29 + 76) = *(_OWORD *)(v44 + 12);
LABEL_96:
      v39 = *(unsigned __int16 *)(v72 + 66);
      *((_WORD *)v29 + 33) = v39;
    }
LABEL_97:
    if ( v43 == 14 )
      break;
LABEL_98:
    v44 += 80;
  }
  while ( v44 != v45 );
  Ptr = (char **)v65.Ptr;
  v42 = Memory[0];
LABEL_100:
  v48 = *((_WORD *)v29 + 32);
  v49 = 0;
  if ( v48 )
  {
    v50 = AcquireSpinLock(Memory, (char *)RoutePolicyCallout::g_pCalloutContext + 40);
    if ( &v83 != (struct _EVENT_DATA_DESCRIPTOR *)v50 )
    {
      v51 = *(struct _EVENT_DATA_DESCRIPTOR *)v50;
      if ( v83.Ptr )
      {
        v71 = v83;
        SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)&v71);
      }
      v83 = v51;
      *(_DWORD *)(v50 + 9) = v77;
      *(_WORD *)(v50 + 13) = v78;
      *(_BYTE *)(v50 + 15) = v79;
      *(_QWORD *)v50 = 0;
      *(_BYTE *)(v50 + 8) = 0;
    }
    if ( Memory[0] )
    {
      v85 = *(struct _EVENT_DATA_DESCRIPTOR *)Memory;
      SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)&v85);
    }
    v52 = Ptr;
    v53 = (char *)*((_QWORD *)RoutePolicyCallout::g_pCalloutContext + 6);
    if ( v53 != (char *)RoutePolicyCallout::g_pCalloutContext + 48 )
    {
      while ( *((char **)v53 + 2) != v84 )
      {
        v53 = *(char **)v53;
        if ( v53 == (char *)RoutePolicyCallout::g_pCalloutContext + 48 )
          goto LABEL_115;
      }
      if ( (unsigned int)dword_140012050 > 4 )
        tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140012050, (unsigned __int8 *)&byte_14000F56F, 0, 0, 2u, &v98);
      v52 = (char **)v53;
    }
    if ( v52 == Ptr )
    {
LABEL_115:
      if ( (unsigned int)dword_140012050 > 4 )
      {
        v65.Ptr = (ULONGLONG)v84;
        v103 = 8;
        v102 = &v65;
        tlgWriteTransfer_EtwWriteTransfer(
          (__int64)&dword_140012050,
          (unsigned __int8 *)&word_14000EAFA,
          0,
          0,
          3u,
          &v101);
      }
      v54 = v52 + 4;
      v52[2] = v84;
      v55.Value = v82.Value;
      v82.Value = 0;
      v52[3] = (char *)v55.Value;
      v56 = (char *)RoutePolicyCallout::g_pCalloutContext + 48;
      v52[5] = (char *)(v52 + 4);
      v52[4] = (char *)(v52 + 4);
      v57 = (char **)*((_QWORD *)v56 + 1);
      if ( *v57 == v56 )
      {
        *v52 = v56;
        v52[1] = (char *)v57;
        *v57 = (char *)v52;
        *((_QWORD *)v56 + 1) = v52;
        LOBYTE(v68) = 0;
        goto LABEL_120;
      }
      goto LABEL_121;
    }
    v54 = v52 + 4;
LABEL_120:
    *((_BYTE *)v29 + 130) = *(_BYTE *)(v72 + 64);
    *((_OWORD *)v29 + 1) = v73;
    *((_OWORD *)v29 + 2) = v74;
    *((_OWORD *)v29 + 3) = v75;
    *(_QWORD *)(v72 + 56) = 0;
    StartTimerWaitFlowEstablish(v29);
    v59 = (_QWORD *)v54[1];
    if ( (_QWORD *)*v59 != v54 )
LABEL_121:
      __fastfail(3u);
    *v29 = v54;
    v29[1] = v59;
    *v59 = v29;
    v54[1] = v29;
    RoutePolicyCache::AddRequestResult(
      (RoutePolicyCache *)(v29 + 2),
      (const struct _WCM_ROUTE_POLICY_NETWORK_REQUEST *)&v84,
      v58);
    if ( *((_WORD *)v29 + 32) == 23 )
    {
      v60 = *((_DWORD *)v29 + 22);
      v61 = (_DWORD)v29 + 72;
    }
    else
    {
      v60 = 0;
      v61 = (_DWORD)v29 + 68;
    }
    INETADDR_SETSOCKADDR(v48, *(_QWORD *)(v72 + 72), v61, v60, *(_WORD *)(*(_QWORD *)(v72 + 72) + 2LL));
    v62 = (char)v68;
  }
  else
  {
    v62 = 1;
    v49 = 1;
    if ( (unsigned int)dword_140012050 > 2 )
    {
      v80 = -1073741071;
      v65.Ptr = (ULONGLONG)"No preferred address";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v39,
        (unsigned int)&byte_1400104BF,
        v40,
        v41,
        (__int64)&v65,
        (__int64)&v80);
    }
  }
  FreeMibTable(v42);
  if ( v49 )
    FreeConnectionContext(v29);
  if ( v62 )
    ExFreePoolWithTag(Ptr, 0x64667072u);
  v70 = 0;
  lambda_abec86eb39d26369503aaafa1ba2d18c_::operator()((__int64)v69);
  if ( v83.Ptr )
  {
    v20 = &v85;
    v85 = v83;
LABEL_134:
    SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)v20);
  }
LABEL_135:
  if ( v82.Value )
    RoutePolicyCallout::Wrapper_WcmKReleaseInterface(
      *((RoutePolicyCallout **)RoutePolicyCallout::g_pCalloutContext + 4),
      (void *)v82.Value,
      v19);
}

```

## disassembly

```asm
0x140007280  mov     rax, rsp
0x140007283  push    rbp
0x140007284  push    rbx
0x140007285  push    rsi
0x140007286  push    rdi
0x140007287  push    r12
0x140007289  push    r13
0x14000728b  push    r14
0x14000728d  push    r15
0x14000728f  lea     rbp, [rax-188h]
0x140007296  sub     rsp, 248h
0x14000729d  movaps  xmmword ptr [rax-58h], xmm6
0x1400072a1  mov     rax, cs:__security_cookie
0x1400072a8  xor     rax, rsp
0x1400072ab  mov     [rbp+180h+var_60], rax
0x1400072b2  mov     rax, cs:WdfFunctions_01015
0x1400072b9  mov     rdx, rcx
0x1400072bc  mov     r8, cs:off_140012040
0x1400072c3  mov     [rbp+180h+var_1B8], rcx
0x1400072c7  mov     rcx, cs:WdfDriverGlobals
0x1400072ce  mov     rax, [rax+650h]
0x1400072d5  call    _guard_dispatch_icall
0x1400072da  mov     [rbp+180h+var_1F0], rax
0x1400072de  lea     r9, [rbp+180h+Memory]
0x1400072e2  xor     r13d, r13d
0x1400072e5  xorps   xmm0, xmm0
0x1400072e8  mov     [rbp+180h+Memory], r13
0x1400072ec  mov     dword ptr [rax+8], 1002h
0x1400072f3  lea     rax, [rbp+180h+var_1F0]
0x1400072f7  mov     [rsp+280h+var_220], rax
0x1400072fc  lea     rax, [rbp+180h+var_170]
0x140007300  mov     [rsp+280h+var_218], rax
0x140007305  lea     esi, [r13+1]
0x140007309  mov     qword ptr [rbp+180h+var_1C8], r13
0x14000730d  lea     rax, [rbp+180h+var_1B8]
0x140007311  mov     qword ptr [rsp+280h+var_210], rax
0x140007316  xor     eax, eax
0x140007318  mov     dword ptr [rbp+180h+var_1C8+0Ah], eax
0x14000731b  mov     word ptr [rbp+180h+var_1C8+0Eh], ax
0x14000731f  mov     rax, [rbp+180h+var_1F0]
0x140007323  mov     qword ptr [rbp+180h+var_180], r13
0x140007327  mov     qword ptr [rbp+180h+var_170], r13
0x14000732b  mov     byte ptr [rbp+180h+var_170+8], r13b
0x14000732f  movups  [rbp+180h+var_1E8], xmm0
0x140007333  mov     word ptr [rbp+180h+var_1C8+8], r13w
0x140007338  movups  [rbp+180h+var_1D8], xmm0
0x14000733c  mov     r14, [rax+48h]
0x140007340  mov     qword ptr [rbp+180h+var_1C8], r13
0x140007344  mov     dword ptr [rsp+280h+var_228], esi
0x140007348  mov     [rsp+280h+var_208], sil
0x14000734d  movzx   edx, word ptr [r14]
0x140007351  call    NetioEnumerateAddress
0x140007356  lea     r12d, [r13+2]
0x14000735a  mov     ebx, eax
0x14000735c  test    eax, eax
0x14000735e  jns     short loc_1400073B7
0x140007360  mov     rcx, [rbp+180h+Memory]; Memory
0x140007364  test    rcx, rcx
0x140007367  jz      short loc_14000736E
0x140007369  call    FreeMibTable
0x14000736e  cmp     ebx, 0C0000225h
0x140007374  jz      loc_140007425
0x14000737a  mov     eax, cs:dword_140012050
0x140007380  cmp     eax, 3
0x140007383  jbe     loc_140007425
0x140007389  lea     rax, aInterfaceluidf; "InterfaceLuidFromAddressFailed"
0x140007390  mov     [rbp+180h+var_198], ebx
0x140007393  mov     [rbp+180h+Memory], rax
0x140007397  lea     rdx, dword_14001047C
0x14000739e  lea     rax, [rbp+180h+var_198]
0x1400073a2  mov     [rsp+280h+var_258], rax
0x1400073a7  lea     rax, [rbp+180h+Memory]
0x1400073ab  mov     qword ptr [rsp+280h+var_260], rax
0x1400073b0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400073b5  jmp     short loc_140007425
0x1400073b7  mov     rsi, [rbp+180h+Memory]
0x1400073bb  mov     eax, [rsi]
0x1400073bd  lea     rbx, [rsi+8]
0x1400073c1  lea     rdi, [rax+rax*4]
0x1400073c5  shl     rdi, 4
0x1400073c9  add     rdi, rbx
0x1400073cc  jmp     short loc_140007409
0x1400073ce  movzx   eax, word ptr [r14]
0x1400073d2  cmp     [rbx], ax
0x1400073d5  jnz     short loc_140007405
0x1400073d7  cmp     ax, r12w
0x1400073db  jnz     short loc_1400073E6
0x1400073dd  mov     eax, [r14+4]
0x1400073e1  cmp     [rbx+4], eax
0x1400073e4  jmp     short loc_140007403
0x1400073e6  cmp     ax, 17h
0x1400073ea  jz      short loc_1400073F1
0x1400073ec  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400073f1  mov     rax, [r14+10h]
0x1400073f5  cmp     [rbx+10h], rax
0x1400073f9  jnz     short loc_140007405
0x1400073fb  mov     rax, [r14+8]
0x1400073ff  cmp     [rbx+8], rax
0x140007403  jz      short loc_140007410
0x140007405  add     rbx, 50h ; 'P'
0x140007409  cmp     rbx, rdi
0x14000740c  jnz     short loc_1400073CE
0x14000740e  jmp     short loc_140007418
0x140007410  mov     rax, [rbx+20h]
0x140007414  mov     qword ptr [rbp+180h+var_1C8], rax
0x140007418  mov     rcx, rsi; Memory
0x14000741b  call    FreeMibTable
0x140007420  mov     esi, 1
0x140007425  mov     eax, cs:dword_140012050
0x14000742b  mov     r14d, 4
0x140007431  cmp     eax, r14d
0x140007434  jbe     loc_140007517
0x14000743a  mov     rdx, [rbp+180h+var_1F0]
0x14000743e  mov     rax, qword ptr [rbp+180h+var_1C8]
0x140007442  mov     r8, [rdx+38h]
0x140007446  mov     [rbp+180h+Memory], rax
0x14000744a  mov     al, [rdx+40h]
0x14000744d  mov     [rsp+280h+var_250], al
0x140007451  mov     rax, [rdx+48h]
0x140007455  movzx   ecx, word ptr [rax]
0x140007458  mov     word ptr [rsp+280h+var_230], cx
0x14000745d  movzx   eax, word ptr [rdx+42h]
0x140007461  mov     word ptr [rsp+280h+var_230+2], ax
0x140007466  test    r8, r8
0x140007469  jz      short loc_140007482
0x14000746b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000746f  inc     rax
0x140007472  cmp     [r8+rax*2], r13w
0x140007477  jnz     short loc_14000746F
0x140007479  lea     eax, ds:2[rax*2]
0x140007480  jmp     short loc_14000748C
0x140007482  lea     r8, qword_14000C868
0x140007489  mov     eax, r12d
0x14000748c  mov     [rbp+180h+var_C8], eax
0x140007492  lea     rdx, byte_14000F499; int
0x140007499  lea     rax, [rbp+180h+Memory]
0x14000749d  mov     [rbp+180h+var_D0], r8
0x1400074a4  mov     [rbp+180h+var_E0], rax
0x1400074ab  lea     rcx, dword_140012050; int
0x1400074b2  lea     rax, [rsp+280h+var_250]
0x1400074b7  mov     [rbp+180h+var_C4], r13d
0x1400074be  mov     [rbp+180h+var_F0], rax
0x1400074c5  xor     r9d, r9d; int
0x1400074c8  lea     rax, [rsp+280h+var_230]
0x1400074cd  mov     [rbp+180h+var_D8], 8
0x1400074d8  mov     [rbp+180h+var_100], rax
0x1400074df  xor     r8d, r8d; int
0x1400074e2  lea     rax, [rsp+280h+var_230+2]
0x1400074e7  mov     [rbp+180h+var_E8], 1
0x1400074f2  mov     [rbp+180h+var_110], rax
0x1400074f6  lea     rax, [rbp+180h+var_130]
0x1400074fa  mov     [rsp+280h+var_258], rax; PEVENT_DATA_DESCRIPTOR
0x1400074ff  mov     [rsp+280h+var_260], 7; ULONG
0x140007507  mov     [rbp+180h+var_F8], r12
0x14000750e  mov     [rbp+180h+var_108], r12
0x140007512  call    _tlgWriteTransfer_EtwWriteTransfer
0x140007517  cmp     qword ptr [rbp+180h+var_1C8], r13
0x14000751b  jz      short loc_140007577
0x14000751d  mov     eax, cs:dword_140012050
0x140007523  cmp     eax, r14d
0x140007526  jbe     short loc_14000754A
0x140007528  lea     rax, a5gRouteSelecti; "5G route selection policies will not be"...
0x14000752f  mov     [rsp+280h+var_228], rax
0x140007534  lea     rdx, byte_14000F69F
0x14000753b  lea     rax, [rsp+280h+var_228]
0x140007540  mov     qword ptr [rsp+280h+var_260], rax
0x140007545  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x14000754a  lea     rcx, [rsp+280h+var_220]
0x14000754f  mov     [rsp+280h+var_208], r13b
0x140007554  call    _lambda_abec86eb39d26369503aaafa1ba2d18c___operator__
0x140007559  cmp     qword ptr [rbp+180h+var_170], r13
0x14000755d  jz      loc_140007CDC
0x140007563  movaps  xmm0, [rbp+180h+var_170]
0x140007567  lea     rcx, [rsp+280h+var_248+8]
0x14000756c  movdqa  [rsp+280h+var_248+8], xmm0
0x140007572  jmp     loc_140007CD7
0x140007577  mov     rcx, [rbp+180h+var_1F0]
0x14000757b  mov     rax, [rcx+38h]
0x14000757f  mov     qword ptr [rbp+180h+var_1E8+8], rax
0x140007583  mov     dword ptr [rbp+180h+var_1E8], 800h
0x14000758a  mov     rax, [rcx+48h]
0x14000758e  movzx   ecx, word ptr [rax]
0x140007591  mov     word ptr [rbp+180h+var_1C8+8], cx
0x140007595  lea     rcx, [rbp+180h+var_1E8]; this
0x140007599  call    ?DoesRequestMatchAnyRule@RoutePolicyCache@@YA_NAEBU_WCM_ROUTE_POLICY_NETWORK_REQUEST@@@Z; RoutePolicyCache::DoesRequestMatchAnyRule(_WCM_ROUTE_POLICY_NETWORK_REQUEST const &)
0x14000759e  test    al, al
0x1400075a0  jnz     short loc_1400075C8
0x1400075a2  mov     eax, cs:dword_140012050
0x1400075a8  cmp     eax, r14d
0x1400075ab  jbe     short loc_14000754A
0x1400075ad  lea     rax, aRequestMatches; "Request matches no rules or does source"...
0x1400075b4  mov     [rbp+180h+Memory], rax
0x1400075b8  lea     rdx, unk_14000E9C0
0x1400075bf  lea     rax, [rbp+180h+Memory]
0x1400075c3  jmp     loc_140007540
0x1400075c8  mov     edx, 30h ; '0'
0x1400075cd  mov     edi, 64667072h
0x1400075d2  mov     r8d, edi
0x1400075d5  lea     ebx, [rdx+10h]
0x1400075d8  mov     ecx, ebx
0x1400075da  call    cs:__imp_ExAllocatePool2
0x1400075e1  nop     dword ptr [rax+rax+00h]
0x1400075e6  mov     qword ptr [rsp+280h+var_248+8], rax
0x1400075eb  mov     r15, rax
0x1400075ee  test    rax, rax
0x1400075f1  jnz     short loc_140007637
0x1400075f3  mov     eax, cs:dword_140012050
0x1400075f9  cmp     eax, r12d
0x1400075fc  jbe     loc_14000754A
0x140007602  lea     rax, aFailedToAlloca_2; "Failed to allocate INTERFACE_CONTEXT"
0x140007609  mov     [rbp+180h+var_198], 0C000009Ah
0x140007610  mov     [rbp+180h+Memory], rax
0x140007614  lea     rdx, unk_1400100F8
0x14000761b  lea     rax, [rbp+180h+var_198]
0x14000761f  mov     [rsp+280h+var_258], rax
0x140007624  lea     rax, [rbp+180h+Memory]
0x140007628  mov     qword ptr [rsp+280h+var_260], rax
0x14000762d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140007632  jmp     loc_14000754A
0x140007637  mov     r8d, edi
0x14000763a  mov     edx, 88h
0x14000763f  mov     rcx, rbx
0x140007642  call    cs:__imp_ExAllocatePool2
0x140007649  nop     dword ptr [rax+rax+00h]
0x14000764e  mov     rbx, rax
0x140007651  test    rax, rax
0x140007654  jnz     short loc_1400076A7
0x140007656  mov     eax, cs:dword_140012050
0x14000765c  cmp     eax, r12d
0x14000765f  jbe     short loc_140007691
0x140007661  lea     rax, aFailedToAlloca_8; "Failed to allocate CONNECTION_CONTEXT"
0x140007668  mov     [rbp+180h+var_198], 0C000009Ah
0x14000766f  mov     [rbp+180h+Memory], rax
0x140007673  lea     rdx, byte_14000FC43
0x14000767a  lea     rax, [rbp+180h+var_198]
0x14000767e  mov     [rsp+280h+var_258], rax
0x140007683  lea     rax, [rbp+180h+Memory]
0x140007687  mov     qword ptr [rsp+280h+var_260], rax
0x14000768c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140007691  mov     edx, edi; Tag
0x140007693  mov     rcx, r15; P
0x140007696  call    cs:__imp_ExFreePoolWithTag
0x14000769d  nop     dword ptr [rax+rax+00h]
0x1400076a2  jmp     loc_14000754A
0x1400076a7  mov     rcx, rbx
0x1400076aa  call    CreateTimerWaitFlowEstablish
0x1400076af  test    eax, eax
0x1400076b1  jns     short loc_1400076BD
0x1400076b3  mov     rcx, rbx; P
0x1400076b6  call    FreeConnectionContext
0x1400076bb  jmp     short loc_140007691
0x1400076bd  lea     rdx, ?g_cacheLock@@3_KA; unsigned __int64 g_cacheLock
0x1400076c4  mov     [rbp+180h+var_160], r13
0x1400076c8  lea     rcx, [rbp+180h+Memory]
0x1400076cc  call    ?AcquireSpinLock@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUSpinLockAndSavedIrql@@@Z$1?Release@1@SAX0@ZU?$integral_constant@_K$01@wistd@@U1@PEA_K$0A@$$T@details@wil@@@details@wil@@@wil@@PEA_K@Z; AcquireSpinLock(unsigned __int64 *)
0x1400076d1  mov     rdi, cs:?g_cacheListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_cacheListHead
0x1400076d8  jmp     short loc_1400076F2
0x1400076da  lea     rcx, [rdi+10h]
0x1400076de  lea     rdx, [rbp+180h+var_1E8]
0x1400076e2  call    operator__
0x1400076e7  test    al, al
0x1400076e9  jnz     loc_140007827
0x1400076ef  mov     rdi, [rdi]
0x1400076f2  lea     rax, ?g_cacheListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_cacheListHead
0x1400076f9  cmp     rdi, rax
0x1400076fc  jnz     short loc_1400076DA
0x1400076fe  cmp     [rbp+180h+Memory], r13
0x140007702  jz      short loc_140007716
0x140007704  movaps  xmm0, xmmword ptr [rbp+180h+Memory]
0x140007708  lea     rcx, [rbp+180h+var_200]; struct SpinLockAndSavedIrql *
0x14000770c  movdqa  [rbp+180h+var_200], xmm0
0x140007711  call    ?Release@SpinLockAndSavedIrql@@SAXAEBU1@@Z; SpinLockAndSavedIrql::Release(SpinLockAndSavedIrql const &)
0x140007716  mov     eax, cs:dword_140012050
0x14000771c  cmp     eax, r14d
0x14000771f  jbe     short loc_140007741
0x140007721  lea     rax, aNoCacheEntryFo; "No cache entry for this request"
0x140007728  mov     [rbp+180h+Memory], rax
0x14000772c  lea     rdx, unk_14000F780
0x140007733  lea     rax, [rbp+180h+Memory]
0x140007737  mov     qword ptr [rsp+280h+var_260], rax; void **
0x14000773c  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x140007741  mov     rdx, qword ptr [rbp+180h+var_180]; void *
0x140007745  test    rdx, rdx
0x140007748  jz      short loc_14000775A
0x14000774a  mov     rcx, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140007751  mov     rcx, [rcx+20h]; this
0x140007755  call    ?Wrapper_WcmKReleaseInterface@RoutePolicyCallout@@YAKPEAX0@Z; RoutePolicyCallout::Wrapper_WcmKReleaseInterface(void *,void *)
0x14000775a  mov     rcx, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140007761  lea     r9, [rbp+180h+var_180]; union _NET_LUID_LH *
0x140007765  mov     qword ptr [rbp+180h+var_180], r13
0x140007769  lea     r8, [rbp+180h+var_160]; struct _WCM_ROUTE_POLICY_NETWORK_REQUEST *
0x14000776d  lea     rdx, [rbp+180h+var_1E8]; void *
0x140007771  mov     rcx, [rcx+20h]; this
0x140007775  call    ?Wrapper_WcmKGetInterfaceForNetworkRequest@RoutePolicyCallout@@YAKPEAXAEBU_WCM_ROUTE_POLICY_NETWORK_REQUEST@@PEAT_NET_LUID_LH@@PEAPEAX@Z; RoutePolicyCallout::Wrapper_WcmKGetInterfaceForNetworkRequest(void *,_WCM_ROUTE_POLICY_NETWORK_REQUEST const &,_NET_LUID_LH *,void * *)
0x14000777a  mov     edi, eax
0x14000777c  test    eax, eax
0x14000777e  jz      short loc_1400077DD
0x140007780  mov     ecx, cs:dword_140012050
0x140007786  cmp     ecx, r12d
0x140007789  jbe     short loc_1400077CD
  ... truncated ...
```
