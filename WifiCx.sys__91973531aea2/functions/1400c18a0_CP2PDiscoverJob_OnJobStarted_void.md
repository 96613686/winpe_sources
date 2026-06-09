# CP2PDiscoverJob::OnJobStarted(void)

- ea: `0x1400c18a0`
- end: `0x1400c1ded`
- name: `?OnJobStarted@CP2PDiscoverJob@@UEAAXXZ`
- size: `1357`
- prototype: `void __fastcall(CP2PDiscoverJob *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x140012f80`
- `0x140016d00`
- `0x14001d1d8`
- `0x14001e2c0`
- `0x14001eed0`
- `0x140038c74`
- `0x140050dc8`
- `0x140061178`
- `0x1400638c4`
- `0x140063e84`
- `0x1400bff68`
- `0x1400c06bc`
- `0x1400c18a0`
- `0x1400c389c`
- `0x1400c3d0c`
- `0x1400dfd00`
- `0x1400dfd40`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400c1b53`
- `ntoskrnl!RtlCompareMemory` at `0x1400c1b53`

## pseudocode

```c
void __fastcall CP2PDiscoverJob::OnJobStarted(CP2PDiscoverJob *this, __int64 a2, int a3)
{
  __int64 v3; // rsi
  int v5; // eax
  int v6; // edx
  CP2PDiscoverJob *v7; // rcx
  int v8; // r8d
  int v9; // r9d
  int v10; // edi
  int v11; // r9d
  unsigned int *v12; // rdi
  __int64 v13; // r10
  bool v14; // r9
  bool v15; // r8
  struct CBSSEntry *BSSEntryByGroupID; // rax
  unsigned int i; // esi
  char v18; // r12
  __int64 v19; // r14
  __int64 v20; // rax
  int v21; // ecx
  char v22; // r15
  __int64 v23; // r9
  __int64 v24; // rcx
  __int16 v25; // ax
  CBSSListManager *v26; // rcx
  struct CBSSEntry *v27; // rax
  CPropertyCache *v28; // rax
  int started; // eax
  int v30; // [rsp+20h] [rbp-69h]
  int v31; // [rsp+30h] [rbp-59h]
  __int64 v32; // [rsp+38h] [rbp-51h]
  bool v33; // [rsp+60h] [rbp-29h] BYREF
  bool v34; // [rsp+61h] [rbp-28h] BYREF
  bool v35; // [rsp+62h] [rbp-27h] BYREF
  unsigned int v36; // [rsp+64h] [rbp-25h] BYREF
  __int64 v37; // [rsp+68h] [rbp-21h] BYREF
  int v38; // [rsp+70h] [rbp-19h]
  _OWORD Source1[2]; // [rsp+74h] [rbp-15h] BYREF

  v3 = *((_QWORD *)this + 67);
  v36 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      a3,
      73,
      (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  }
  CJobBase::NotifyStarted(this, 1076035585);
  v30 = (_DWORD)this + 576;
  v5 = NotificationManager::RegisterForNotifications(
         *((_QWORD *)this + 67) + 1072LL,
         62,
         0,
         *((unsigned __int16 *)this + 26));
  v10 = v5;
  if ( v5 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v11 = 74;
      LODWORD(v32) = v5;
      v31 = *((_DWORD *)this + 4);
LABEL_45:
      LOBYTE(v6) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        v8,
        v11,
        (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
        (char)this,
        v31,
        v32);
    }
LABEL_46:
    CJobBase::CompleteJob(this, v10);
    goto LABEL_48;
  }
  v12 = (unsigned int *)((char *)this + 1200);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qDDDd(
      WPP_GLOBAL_Control->DeviceExtension,
      (*((unsigned __int8 *)this + 1176) >> 5) & 1,
      v8,
      v9,
      v30,
      (char)this,
      *((_DWORD *)this + 4),
      (*((_BYTE *)this + 1177) & 8) != 0,
      (*((_BYTE *)this + 1176) & 0x20) != 0,
      *v12);
  if ( (*((_BYTE *)this + 1176) & 0x20) == 0 )
  {
    v12 = (unsigned int *)((char *)this + 1200);
    if ( *((_DWORD *)this + 300) == 1 )
    {
      v35 = 1;
      v34 = 1;
      v33 = 1;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v6) = 4;
        WPP_RECORDER_SF_qD_MAC_(
          WPP_GLOBAL_Control->DeviceExtension,
          v6,
          v8,
          76,
          (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          *((_QWORD *)this + 151));
      }
      CP2PDiscoverJob::GetDiscoverySettingsFromBitmask(v7, *(_BYTE *)(*((_QWORD *)this + 151) + 6LL), &v35, &v34, &v33);
      v14 = v34;
      v15 = v35;
      *((_DWORD *)this + 162) = *(_DWORD *)v13;
      *((_WORD *)this + 326) = *(_WORD *)(v13 + 4);
      *((_OWORD *)this + 41) = *(_OWORD *)(v13 + 8);
      *((_OWORD *)this + 42) = *(_OWORD *)(v13 + 24);
      *((_DWORD *)this + 172) = *(_DWORD *)(v13 + 40);
      BSSEntryByGroupID = CBSSListManager::FindBSSEntryByGroupID(
                            (CBSSListManager *)(v3 + 1736),
                            (CP2PDiscoverJob *)((char *)this + 648),
                            v15,
                            v14,
                            v33);
      if ( BSSEntryByGroupID )
      {
        if ( *((_BYTE *)BSSEntryByGroupID + 784) )
        {
          *((_DWORD *)this + 304) = *((_DWORD *)BSSEntryByGroupID + 195);
          *((_DWORD *)this + 320) = *((_DWORD *)BSSEntryByGroupID + 194);
          if ( *((_BYTE *)BSSEntryByGroupID + 784) )
            *((_BYTE *)this + 1176) |= 0x20u;
        }
      }
    }
  }
  for ( i = 0; i < *v12; ++i )
  {
    v18 = 1;
    v37 = 0;
    v19 = 44LL * i;
    v20 = *((_QWORD *)this + 151);
    v21 = *(_DWORD *)(v19 + v20 + 8);
    v38 = v21;
    Source1[0] = *(_OWORD *)(v19 + v20 + 12);
    Source1[1] = *(_OWORD *)(v19 + v20 + 28);
    if ( v21 )
    {
      v22 = 1;
      if ( v21 != 7 || RtlCompareMemory(Source1, "DIRECT-", 7u) != 7 )
        v18 = 0;
    }
    else
    {
      v22 = 0;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v23 = v19 + *((_QWORD *)this + 151);
      WPP_RECORDER_SF_dD_SSID__MAC_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v23 + 8,
        *(unsigned __int8 *)(v23 + 6),
        v23,
        v30,
        i,
        *(_BYTE *)(v23 + 6),
        v23 + 8,
        v23,
        v22,
        v18);
    }
    v24 = *((_QWORD *)this + 151);
    LODWORD(v37) = *(_DWORD *)(v24 + 44LL * i);
    v25 = *(_WORD *)(v24 + v19 + 4);
    v26 = (CBSSListManager *)(*((_QWORD *)this + 67) + 1736LL);
    WORD2(v37) = v25;
    v27 = CBSSListManager::FindBSSEntryByGroupID(v26, (const struct _DOT11_WFD_GROUP_ID *)&v37, v18, v22, 1);
    if ( v27 )
    {
      *((_QWORD *)v27 + 84) = 0;
      *((_QWORD *)v27 + 79) = 0;
      *((_DWORD *)v27 + 218) = 0;
      *((_BYTE *)v27 + 784) = 0;
      *(_OWORD *)((char *)v27 + 824) = 0;
      *(_OWORD *)((char *)v27 + 840) = 0;
      *(_OWORD *)((char *)v27 + 852) = 0;
    }
  }
  v28 = (CPropertyCache *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 67) + 8LL) + 8LL))(*((_QWORD *)this + 67) + 8LL);
  if ( (unsigned int)CPropertyCache::GetPropertyULong(v28, 0x34u, &v36) || !v36 || (*((_BYTE *)this + 1177) & 8) != 0 )
  {
    started = CP2PDiscoverJob::TriggerDiscover((enum _WDF_EXECUTION_LEVEL)this);
    v10 = started;
    if ( !started )
    {
      *((_DWORD *)this + 148) = 2;
      goto LABEL_48;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_46;
    v11 = 81;
    goto LABEL_44;
  }
  started = CWfdChangeListenStateJob::Initialize(
              (char *)this + 1696,
              *((_QWORD *)this + 67),
              *((unsigned int *)this + 14),
              0);
  v10 = started;
  if ( started )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_46;
    v11 = 78;
LABEL_44:
    LODWORD(v32) = started;
    v31 = *((_DWORD *)this + 4);
    goto LABEL_45;
  }
  started = CJobBase::StartChildJob(this, (CP2PDiscoverJob *)((char *)this + 1696));
  v10 = started;
  if ( started )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_46;
    v11 = 79;
    goto LABEL_44;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      v8,
      80,
      (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  *((_DWORD *)this + 148) = 1;
LABEL_48:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v6) = 5;
    LODWORD(v32) = v10;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      v8,
      82,
      (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v32);
  }
}

```

## disassembly

```asm
0x1400c18a0  push    rbp
0x1400c18a2  push    rbx
0x1400c18a3  push    rsi
0x1400c18a4  push    rdi
0x1400c18a5  push    r12
0x1400c18a7  push    r13
0x1400c18a9  push    r14
0x1400c18ab  push    r15
0x1400c18ad  lea     rbp, [rsp-1Fh]
0x1400c18b2  sub     rsp, 0A8h
0x1400c18b9  mov     rax, cs:__security_cookie
0x1400c18c0  xor     rax, rsp
0x1400c18c3  mov     [rbp+57h+var_48], rax
0x1400c18c7  mov     rsi, [rcx+218h]
0x1400c18ce  xor     r13d, r13d
0x1400c18d1  mov     [rbp+57h+var_7C], r13d
0x1400c18d5  mov     rbx, rcx
0x1400c18d8  lea     r14, WPP_RECORDER_INITIALIZED
0x1400c18df  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c18e6  lea     r15, WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids
0x1400c18ed  jz      short loc_1400C1925
0x1400c18ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c18f6  cmp     byte ptr [rcx+29h], 5
0x1400c18fa  jnb     short loc_1400C1903
0x1400c18fc  cmp     [rcx+48h], r13w
0x1400c1901  jz      short loc_1400C1925
0x1400c1903  mov     eax, [rbx+10h]
0x1400c1906  mov     r9d, 49h ; 'I'
0x1400c190c  mov     rcx, [rcx+40h]
0x1400c1910  mov     dl, 5
0x1400c1912  mov     [rsp+0E0h+var_B0], eax
0x1400c1916  mov     [rsp+0E0h+var_B8], rbx
0x1400c191b  mov     [rsp+0E0h+var_C0], r15
0x1400c1920  call    WPP_RECORDER_SF_qD
0x1400c1925  mov     edx, 40230001h; int
0x1400c192a  mov     rcx, rbx; this
0x1400c192d  call    ?NotifyStarted@CJobBase@@IEAAXH@Z; CJobBase::NotifyStarted(int)
0x1400c1932  mov     rcx, [rbx+218h]
0x1400c1939  lea     rdx, [rbx+240h]
0x1400c1940  movzx   r9d, word ptr [rbx+34h]
0x1400c1945  lea     rax, [rbx+504h]
0x1400c194c  xor     r8d, r8d
0x1400c194f  mov     [rsp+0E0h+var_B8], rax
0x1400c1954  mov     [rsp+0E0h+var_C0], rdx
0x1400c1959  add     rcx, 430h
0x1400c1960  lea     edx, [r8+3Eh]
0x1400c1964  call    ?RegisterForNotifications@NotificationManager@@QEAAHW4_WDI_INDICATION_TYPE@@KGPEAVINotifyDeviceIndicationCallback@@PEAK@Z; NotificationManager::RegisterForNotifications(_WDI_INDICATION_TYPE,ulong,ushort,INotifyDeviceIndicationCallback *,ulong *)
0x1400c1969  mov     edi, eax
0x1400c196b  test    eax, eax
0x1400c196d  jz      short loc_1400C1992
0x1400c196f  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c1976  jz      loc_1400C1D73
0x1400c197c  mov     ecx, [rbx+10h]
0x1400c197f  mov     r9d, 4Ah ; 'J'
0x1400c1985  mov     dword ptr [rsp+0E0h+var_A8], eax
0x1400c1989  mov     [rsp+0E0h+var_B0], ecx
0x1400c198d  jmp     loc_1400C1D57
0x1400c1992  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c1999  lea     rdi, [rbx+4B0h]
0x1400c19a0  jz      short loc_1400C19E6
0x1400c19a2  movzx   ecx, byte ptr [rbx+499h]
0x1400c19a9  mov     eax, [rdi]
0x1400c19ab  movzx   edx, byte ptr [rbx+498h]
0x1400c19b2  mov     [rsp+0E0h+var_98], eax
0x1400c19b6  mov     eax, [rbx+10h]
0x1400c19b9  shr     ecx, 3
0x1400c19bc  and     ecx, 1
0x1400c19bf  shr     edx, 5
0x1400c19c2  and     edx, 1
0x1400c19c5  mov     dword ptr [rsp+0E0h+var_A0], edx
0x1400c19c9  mov     dword ptr [rsp+0E0h+var_A8], ecx
0x1400c19cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c19d4  mov     [rsp+0E0h+var_B0], eax
0x1400c19d8  mov     [rsp+0E0h+var_B8], rbx
0x1400c19dd  mov     rcx, [rcx+40h]
0x1400c19e1  call    WPP_RECORDER_SF_qDDDd
0x1400c19e6  test    byte ptr [rbx+498h], 20h
0x1400c19ed  jnz     loc_1400C1AF6
0x1400c19f3  lea     rdi, [rbx+4B0h]
0x1400c19fa  cmp     dword ptr [rdi], 1
0x1400c19fd  jnz     loc_1400C1AF6
0x1400c1a03  mov     [rbp+57h+var_7E], 1
0x1400c1a07  mov     [rbp+57h+var_7F], 1
0x1400c1a0b  mov     [rbp+57h+var_80], 1
0x1400c1a0f  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c1a16  jz      short loc_1400C1A4D
0x1400c1a18  mov     rax, [rbx+4B8h]
0x1400c1a1f  mov     r9d, 4Ch ; 'L'
0x1400c1a25  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c1a2c  mov     dl, 4
0x1400c1a2e  mov     [rsp+0E0h+var_A8], rax
0x1400c1a33  mov     eax, [rbx+10h]
0x1400c1a36  mov     [rsp+0E0h+var_B0], eax
0x1400c1a3a  mov     rcx, [rcx+40h]
0x1400c1a3e  mov     [rsp+0E0h+var_B8], rbx
0x1400c1a43  mov     [rsp+0E0h+var_C0], r15
0x1400c1a48  call    WPP_RECORDER_SF_qD_MAC_
0x1400c1a4d  mov     r10, [rbx+4B8h]
0x1400c1a54  lea     rax, [rbp+57h+var_80]
0x1400c1a58  lea     r9, [rbp+57h+var_7F]; bool *
0x1400c1a5c  mov     [rsp+0E0h+var_C0], rax; bool *
0x1400c1a61  lea     r8, [rbp+57h+var_7E]; bool *
0x1400c1a65  mov     dl, [r10+6]; unsigned __int8
0x1400c1a69  call    ?GetDiscoverySettingsFromBitmask@CP2PDiscoverJob@@QEAAXEPEA_N00@Z; CP2PDiscoverJob::GetDiscoverySettingsFromBitmask(uchar,bool *,bool *,bool *)
0x1400c1a6e  mov     eax, [r10]
0x1400c1a71  lea     rdx, [rbx+288h]; struct _DOT11_WFD_GROUP_ID *
0x1400c1a78  mov     r9b, [rbp+57h+var_7F]; bool
0x1400c1a7c  lea     rcx, [rsi+6C8h]; this
0x1400c1a83  mov     r8b, [rbp+57h+var_7E]; bool
0x1400c1a87  mov     [rdx], eax
0x1400c1a89  movzx   eax, word ptr [r10+4]
0x1400c1a8e  mov     [rdx+4], ax
0x1400c1a92  movups  xmm0, xmmword ptr [r10+8]
0x1400c1a97  movups  xmmword ptr [rbx+290h], xmm0
0x1400c1a9e  movups  xmm1, xmmword ptr [r10+18h]
0x1400c1aa3  movups  xmmword ptr [rbx+2A0h], xmm1
0x1400c1aaa  mov     eax, [r10+28h]
0x1400c1aae  mov     [rbx+2B0h], eax
0x1400c1ab4  mov     al, [rbp+57h+var_80]
0x1400c1ab7  mov     byte ptr [rsp+0E0h+var_C0], al; bool
0x1400c1abb  call    ?FindBSSEntryByGroupID@CBSSListManager@@QEAAPEAVCBSSEntry@@AEBU_DOT11_WFD_GROUP_ID@@_N11@Z; CBSSListManager::FindBSSEntryByGroupID(_DOT11_WFD_GROUP_ID const &,bool,bool,bool)
0x1400c1ac0  test    rax, rax
0x1400c1ac3  jz      short loc_1400C1AF6
0x1400c1ac5  cmp     [rax+310h], r13b
0x1400c1acc  jz      short loc_1400C1AF6
0x1400c1ace  mov     ecx, [rax+30Ch]
0x1400c1ad4  mov     [rbx+4C0h], ecx
0x1400c1ada  mov     ecx, [rax+308h]
0x1400c1ae0  mov     [rbx+500h], ecx
0x1400c1ae6  cmp     [rax+310h], r13b
0x1400c1aed  jz      short loc_1400C1AF6
0x1400c1aef  or      byte ptr [rbx+498h], 20h
0x1400c1af6  mov     esi, r13d
0x1400c1af9  cmp     [rdi], r13d
0x1400c1afc  jbe     loc_1400C1C49
0x1400c1b02  xor     eax, eax
0x1400c1b04  mov     r12b, 1
0x1400c1b07  mov     [rbp+57h+var_78], rax
0x1400c1b0b  mov     eax, esi
0x1400c1b0d  imul    r14, rax, 2Ch ; ','
0x1400c1b11  mov     rax, [rbx+4B8h]
0x1400c1b18  mov     ecx, [r14+rax+8]
0x1400c1b1d  mov     [rbp+57h+var_70], ecx
0x1400c1b20  movups  xmm0, xmmword ptr [r14+rax+0Ch]
0x1400c1b26  movups  [rbp+57h+Source1], xmm0
0x1400c1b2a  movups  xmm1, xmmword ptr [r14+rax+1Ch]
0x1400c1b30  movups  [rbp+57h+var_5C], xmm1
0x1400c1b34  test    ecx, ecx
0x1400c1b36  jnz     short loc_1400C1B3D
0x1400c1b38  mov     r15b, r13b
0x1400c1b3b  jmp     short loc_1400C1B68
0x1400c1b3d  mov     r15b, r12b
0x1400c1b40  cmp     ecx, 7
0x1400c1b43  jnz     short loc_1400C1B65
0x1400c1b45  mov     r8d, ecx; Length
0x1400c1b48  lea     rdx, aDirect; "DIRECT-"
0x1400c1b4f  lea     rcx, [rbp+57h+Source1]; Source1
0x1400c1b53  call    cs:__imp_RtlCompareMemory
0x1400c1b5a  nop     dword ptr [rax+rax+00h]
0x1400c1b5f  cmp     rax, 7
0x1400c1b63  jz      short loc_1400C1B68
0x1400c1b65  mov     r12b, r13b
0x1400c1b68  lea     rax, WPP_RECORDER_INITIALIZED
0x1400c1b6f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400c1b76  jz      short loc_1400C1BBE
0x1400c1b78  mov     r9, [rbx+4B8h]
0x1400c1b7f  add     r9, r14
0x1400c1b82  movzx   eax, r12b
0x1400c1b86  mov     [rsp+0E0h+var_90], eax
0x1400c1b8a  movzx   ecx, r15b
0x1400c1b8e  mov     [rsp+0E0h+var_98], ecx
0x1400c1b92  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c1b99  lea     rdx, [r9+8]
0x1400c1b9d  movzx   r8d, byte ptr [r9+6]
0x1400c1ba2  mov     [rsp+0E0h+var_A0], r9
0x1400c1ba7  mov     [rsp+0E0h+var_A8], rdx
0x1400c1bac  mov     rcx, [rcx+40h]
0x1400c1bb0  mov     [rsp+0E0h+var_B0], r8d
0x1400c1bb5  mov     dword ptr [rsp+0E0h+var_B8], esi
0x1400c1bb9  call    WPP_RECORDER_SF_dD_SSID__MAC_DD
0x1400c1bbe  mov     rcx, [rbx+4B8h]
0x1400c1bc5  lea     rdx, [rbp+57h+var_78]; struct _DOT11_WFD_GROUP_ID *
0x1400c1bc9  mov     r9b, r15b; bool
0x1400c1bcc  mov     byte ptr [rsp+0E0h+var_C0], 1; bool
0x1400c1bd1  mov     r8b, r12b; bool
0x1400c1bd4  mov     eax, [rcx+r14]
0x1400c1bd8  mov     dword ptr [rbp+57h+var_78], eax
0x1400c1bdb  movzx   eax, word ptr [rcx+r14+4]
0x1400c1be1  mov     rcx, [rbx+218h]
0x1400c1be8  add     rcx, 6C8h; this
0x1400c1bef  mov     word ptr [rbp+57h+var_78+4], ax
0x1400c1bf3  call    ?FindBSSEntryByGroupID@CBSSListManager@@QEAAPEAVCBSSEntry@@AEBU_DOT11_WFD_GROUP_ID@@_N11@Z; CBSSListManager::FindBSSEntryByGroupID(_DOT11_WFD_GROUP_ID const &,bool,bool,bool)
0x1400c1bf8  test    rax, rax
0x1400c1bfb  jz      short loc_1400C1C31
0x1400c1bfd  mov     [rax+2A0h], r13
0x1400c1c04  xorps   xmm0, xmm0
0x1400c1c07  mov     [rax+278h], r13
0x1400c1c0e  mov     [rax+368h], r13d
0x1400c1c15  mov     [rax+310h], r13b
0x1400c1c1c  movups  xmmword ptr [rax+338h], xmm0
0x1400c1c23  movups  xmmword ptr [rax+348h], xmm0
0x1400c1c2a  movups  xmmword ptr [rax+354h], xmm0
0x1400c1c31  inc     esi
0x1400c1c33  cmp     esi, [rdi]
0x1400c1c35  jb      loc_1400C1B02
0x1400c1c3b  lea     r14, WPP_RECORDER_INITIALIZED
0x1400c1c42  lea     r15, WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids
0x1400c1c49  mov     rcx, [rbx+218h]
0x1400c1c50  add     rcx, 8
0x1400c1c54  mov     rax, [rcx]
0x1400c1c57  mov     rax, [rax+8]
0x1400c1c5b  call    _guard_dispatch_icall
0x1400c1c60  lea     r8, [rbp+57h+var_7C]; unsigned int *
0x1400c1c64  mov     edx, 34h ; '4'; unsigned int
0x1400c1c69  mov     rcx, rax; this
0x1400c1c6c  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x1400c1c71  test    eax, eax
0x1400c1c73  jnz     loc_1400C1D2F
0x1400c1c79  cmp     [rbp+57h+var_7C], r13d
0x1400c1c7d  jz      loc_1400C1D2F
0x1400c1c83  test    byte ptr [rbx+499h], 8
0x1400c1c8a  jnz     loc_1400C1D2F
0x1400c1c90  mov     r8d, [rbx+38h]
0x1400c1c94  lea     rsi, [rbx+6A0h]
0x1400c1c9b  mov     rdx, [rbx+218h]
0x1400c1ca2  mov     rcx, rsi
0x1400c1ca5  xor     r9d, r9d
0x1400c1ca8  call    ?Initialize@CWfdChangeListenStateJob@@QEAAHPEAVCAdapter@@KW4_WDI_P2P_LISTEN_STATE@@@Z; CWfdChangeListenStateJob::Initialize(CAdapter *,ulong,_WDI_P2P_LISTEN_STATE)
0x1400c1cad  mov     edi, eax
0x1400c1caf  test    eax, eax
0x1400c1cb1  jz      short loc_1400C1CCB
0x1400c1cb3  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c1cba  jz      loc_1400C1D73
0x1400c1cc0  mov     r9d, 4Eh ; 'N'
0x1400c1cc6  jmp     loc_1400C1D4C
0x1400c1ccb  mov     rdx, rsi; struct CJobBase *
0x1400c1cce  mov     rcx, rbx; this
0x1400c1cd1  call    ?StartChildJob@CJobBase@@IEAAHPEAV1@@Z; CJobBase::StartChildJob(CJobBase *)
0x1400c1cd6  mov     edi, eax
0x1400c1cd8  test    eax, eax
0x1400c1cda  jz      short loc_1400C1CF1
0x1400c1cdc  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c1ce3  jz      loc_1400C1D73
0x1400c1ce9  mov     r9d, 4Fh ; 'O'
0x1400c1cef  jmp     short loc_1400C1D4C
0x1400c1cf1  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c1cf8  jz      short loc_1400C1D23
0x1400c1cfa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c1d01  mov     r9d, 50h ; 'P'
0x1400c1d07  mov     eax, [rbx+10h]
0x1400c1d0a  mov     dl, 4
0x1400c1d0c  mov     [rsp+0E0h+var_B0], eax
0x1400c1d10  mov     [rsp+0E0h+var_B8], rbx
0x1400c1d15  mov     rcx, [rcx+40h]
0x1400c1d19  mov     [rsp+0E0h+var_C0], r15
0x1400c1d1e  call    WPP_RECORDER_SF_qD
0x1400c1d23  mov     dword ptr [rbx+250h], 1
0x1400c1d2d  jmp     short loc_1400C1D89
0x1400c1d2f  mov     rcx, rbx; this
0x1400c1d32  call    ?TriggerDiscover@CP2PDiscoverJob@@QEAAHXZ; CP2PDiscoverJob::TriggerDiscover(void)
0x1400c1d37  mov     edi, eax
0x1400c1d39  test    eax, eax
0x1400c1d3b  jz      short loc_1400C1D7F
0x1400c1d3d  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c1d44  jz      short loc_1400C1D73
0x1400c1d46  mov     r9d, 51h ; 'Q'
0x1400c1d4c  mov     dword ptr [rsp+0E0h+var_A8], eax
0x1400c1d50  mov     eax, [rbx+10h]
0x1400c1d53  mov     [rsp+0E0h+var_B0], eax
0x1400c1d57  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c1d5e  mov     dl, 2
0x1400c1d60  mov     [rsp+0E0h+var_B8], rbx
0x1400c1d65  mov     [rsp+0E0h+var_C0], r15
0x1400c1d6a  mov     rcx, [rcx+40h]
0x1400c1d6e  call    WPP_RECORDER_SF_qDD
0x1400c1d73  mov     edx, edi; int
0x1400c1d75  mov     rcx, rbx; this
0x1400c1d78  call    ?CompleteJob@CJobBase@@IEAAHH@Z; CJobBase::CompleteJob(int)
0x1400c1d7d  jmp     short loc_1400C1D89
0x1400c1d7f  mov     dword ptr [rbx+250h], 2
0x1400c1d89  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c1d90  jz      short loc_1400C1DCC
0x1400c1d92  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c1d99  cmp     byte ptr [rcx+29h], 5
0x1400c1d9d  jnb     short loc_1400C1DA6
0x1400c1d9f  cmp     [rcx+48h], r13w
0x1400c1da4  jz      short loc_1400C1DCC
0x1400c1da6  mov     eax, [rbx+10h]
0x1400c1da9  mov     r9d, 52h ; 'R'
0x1400c1daf  mov     rcx, [rcx+40h]
0x1400c1db3  mov     dl, 5
0x1400c1db5  mov     dword ptr [rsp+0E0h+var_A8], edi
0x1400c1db9  mov     [rsp+0E0h+var_B0], eax
0x1400c1dbd  mov     [rsp+0E0h+var_B8], rbx
0x1400c1dc2  mov     [rsp+0E0h+var_C0], r15
0x1400c1dc7  call    WPP_RECORDER_SF_qDD
0x1400c1dcc  mov     rcx, [rbp+57h+var_48]
0x1400c1dd0  xor     rcx, rsp; StackCookie
0x1400c1dd3  call    __security_check_cookie
0x1400c1dd8  add     rsp, 0A8h
  ... truncated ...
```
