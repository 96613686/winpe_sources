# CP2PDiscoverJob::InitializeDiscoverByGroupID(CAdapter *,ulong,_DOT11_WFD_GROUP_ID const &,bool,bool,bool,bool,_DOT11_WFD_CHANNEL *,CBSSEntry *)

- ea: `0x1400c08f0`
- end: `0x1400c0eb0`
- name: `?InitializeDiscoverByGroupID@CP2PDiscoverJob@@QEAAHPEAVCAdapter@@KAEBU_DOT11_WFD_GROUP_ID@@_N222PEAU_DOT11_WFD_CHANNEL@@PEAVCBSSEntry@@@Z`
- size: `1472`
- prototype: `__int64 __fastcall(CP2PDiscoverJob *__hidden this, struct CAdapter *, unsigned int, const struct _DOT11_WFD_GROUP_ID *, bool, bool, bool, bool, struct _DOT11_WFD_CHANNEL *, struct CBSSEntry *)`
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140034a50`
- `0x140034e90`
- `0x14004f2b0`
- `0x1400b58e8`

## callees

- `0x1400032f0`
- `0x140009420`
- `0x14000c940`
- `0x140017f40`
- `0x14001e2c0`
- `0x14001eed0`
- `0x140076138`
- `0x1400c08f0`
- `0x1400c41e0`
- `0x1400dfd40`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400c0c93`
- `ntoskrnl!RtlCompareMemory` at `0x1400c0c93`

## pseudocode

```c
__int64 __fastcall CP2PDiscoverJob::InitializeDiscoverByGroupID(
        CP2PDiscoverJob *this,
        struct CAdapter *a2,
        int a3,
        const struct _DOT11_WFD_GROUP_ID *a4,
        char a5,
        char a6,
        bool a7,
        bool a8,
        struct _DOT11_WFD_CHANNEL *a9,
        struct CBSSEntry *a10)
{
  const struct _DOT11_WFD_GROUP_ID *v10; // rdi
  struct CAdapter *v11; // rbp
  void *v13; // rcx
  void *v14; // rcx
  unsigned int v15; // eax
  int v16; // edx
  int v17; // r8d
  int v18; // r9d
  unsigned int v19; // ebp
  int v20; // edx
  int v21; // r8d
  int *v22; // rbx
  int IsEnabledDeviceUsageNoInline; // eax
  int v24; // ecx
  char *v25; // r8
  bool v26; // zf
  int v27; // eax
  _DWORD *v28; // rbx
  _DWORD *v29; // rdx
  _DWORD *v30; // r12
  _WORD *v31; // rax
  int v32; // edx
  int v33; // r8d
  __int64 v34; // rcx
  struct CAdapterPropertyCache *v35; // rax
  int v37; // [rsp+20h] [rbp-78h]
  __int64 v38; // [rsp+38h] [rbp-60h]

  v10 = a4;
  v11 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      a3,
      116,
      (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  }
  v13 = (void *)*((_QWORD *)this + 211);
  if ( v13 )
  {
    operator delete(v13);
    *((_QWORD *)this + 211) = 0;
  }
  v14 = (void *)*((_QWORD *)this + 151);
  if ( v14 )
  {
    operator delete(v14);
    *((_QWORD *)this + 151) = 0;
  }
  LOBYTE(a4) = 1;
  LOBYTE(v37) = 0;
  v15 = COidJobBase::InitializeWithoutOid(this, 120, v11, a4);
  v19 = v15;
  if ( v15 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v19;
    LOBYTE(v16) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v16,
      v17,
      117,
      (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v15);
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qD_SSID__MAC_ddd(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v10 + 8,
        a9 != 0,
        v18,
        v37,
        (char)this,
        *((_DWORD *)this + 4),
        (__int64)v10 + 8,
        (__int64)v10,
        a5,
        a6,
        a9 != 0);
    *((_BYTE *)this + 1177) |= 8u;
    *(_OWORD *)((char *)this + 648) = *(_OWORD *)v10;
    *(_OWORD *)((char *)this + 664) = *((_OWORD *)v10 + 1);
    *(_OWORD *)((char *)this + 676) = *(_OWORD *)((char *)v10 + 28);
    if ( a6 || !a5 )
    {
      v22 = (int *)((char *)this + 692);
      if ( a8 )
        *v22 = 5000;
      else
        *v22 = 15000;
    }
    else
    {
      v22 = (int *)((char *)this + 692);
      *((_DWORD *)this + 173) = 120000;
    }
    IsEnabledDeviceUsageNoInline = Feature_WiFiCx_TlvParserStaging__private_IsEnabledDeviceUsageNoInline();
    v24 = *v22;
    v25 = (char *)this + 660;
    v26 = IsEnabledDeviceUsageNoInline == 0;
    *((_DWORD *)this + 174) = *v22;
    v27 = *((_DWORD *)this + 164);
    v28 = (_DWORD *)((char *)this + 1460);
    v29 = (_DWORD *)((char *)this + 600);
    if ( v26 )
    {
      *((_DWORD *)this + 322) |= 2u;
      v30 = (_DWORD *)((char *)this + 1292);
      *((_DWORD *)this + 323) = 4;
      *((_QWORD *)this + 76) = v25;
      *v29 = v27;
      *((_DWORD *)this + 325) = 3;
      *((_BYTE *)this + 1296) = 1;
      *((_BYTE *)this + 1308) = 0;
      *((_DWORD *)this + 328) = 50;
      *((_DWORD *)this + 329) = 40;
      *((_DWORD *)this + 330) = 100;
      *((_DWORD *)this + 331) = v24;
      *((_QWORD *)this + 170) = v29;
      *((_DWORD *)this + 338) = 1;
    }
    else
    {
      *((_BYTE *)this + 1476) = 0;
      v30 = (_DWORD *)((char *)this + 1292);
      *v28 = 4;
      *((_DWORD *)this + 367) = 3;
      *((_BYTE *)this + 1464) = 1;
      *((_DWORD *)this + 370) = 50;
      *((_DWORD *)this + 372) = 40;
      *((_DWORD *)this + 373) = 100;
      *((_DWORD *)this + 374) = v24;
      *((_QWORD *)this + 76) = v25;
      *v29 = v27;
      *((_DWORD *)this + 364) |= 2u;
      *((_QWORD *)this + 192) = v29;
      *((_DWORD *)this + 382) = 1;
    }
    *((_DWORD *)this + 300) = 1;
    v31 = operator new(0x2Cu);
    *((_QWORD *)this + 151) = v31;
    if ( v31 )
    {
      *(_DWORD *)v31 = *(_DWORD *)v10;
      v31[2] = *((_WORD *)v10 + 2);
      v34 = *((_QWORD *)this + 151);
      *(_OWORD *)(v34 + 8) = *(_OWORD *)((char *)v10 + 8);
      *(_OWORD *)(v34 + 24) = *(_OWORD *)((char *)v10 + 24);
      *(_DWORD *)(v34 + 40) = *((_DWORD *)v10 + 10);
      *(_BYTE *)(*((_QWORD *)this + 151) + 6LL) = 1;
      if ( *((_DWORD *)v10 + 2) != 7 || RtlCompareMemory((char *)v10 + 12, "DIRECT-", 7u) != 7 )
      {
        if ( (unsigned int)Feature_WiFiCx_TlvParserStaging__private_IsEnabledDeviceUsageNoInline() )
          *v28 = 1;
        else
          *v30 = 1;
        *(_BYTE *)(*((_QWORD *)this + 151) + 6LL) = 2;
      }
      *((_BYTE *)this + 1176) = (8 * a5) | (16 * a6) | *((_BYTE *)this + 1176) & 0xE7;
      if ( a9 )
      {
        v35 = (struct CAdapterPropertyCache *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 67)
                                                                                             + 8LL)
                                                                                 + 8LL))(*((_QWORD *)this + 67) + 8LL);
        if ( !(unsigned int)ConvertP2PChannelToBandChannel(
                              v35,
                              a9,
                              (CP2PDiscoverJob *)((char *)this + 1216),
                              (unsigned int *)this + 320) )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v20) = 4;
            WPP_RECORDER_SF_qD(
              WPP_GLOBAL_Control->DeviceExtension,
              v20,
              v21,
              120,
              (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
              (char)this,
              *((_DWORD *)this + 4));
          }
          *((_BYTE *)this + 1176) |= 0x20u;
        }
      }
      if ( (*((_BYTE *)this + 1176) & 0x20) == 0 && a10 )
      {
        if ( *((_BYTE *)a10 + 784) )
        {
          *((_DWORD *)this + 304) = *((_DWORD *)a10 + 195);
          *((_DWORD *)this + 320) = *((_DWORD *)a10 + 194);
        }
        if ( *((_BYTE *)a10 + 784) == 1 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v20) = 4;
            WPP_RECORDER_SF_qD(
              WPP_GLOBAL_Control->DeviceExtension,
              v20,
              v21,
              121,
              (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
              (char)this,
              *((_DWORD *)this + 4));
          }
          *((_BYTE *)this + 1176) |= 0x20u;
        }
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v20) = 4;
        LODWORD(v38) = a7;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v20,
          v21,
          122,
          (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          v38);
      }
      *((_BYTE *)this + 1177) = (4 * a7) | *((_BYTE *)this + 1177) & 0xFB;
    }
    else
    {
      v19 = -1073741670;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v19;
      LODWORD(v38) = -1073741670;
      LOBYTE(v32) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v32,
        v33,
        119,
        (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        v38);
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v20) = 5;
    LODWORD(v38) = v19;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v20,
      v21,
      123,
      (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v38);
  }
  return v19;
}

```

## disassembly

```asm
0x1400c08f0  push    rbx
0x1400c08f2  push    rbp
0x1400c08f3  push    rsi
0x1400c08f4  push    rdi
0x1400c08f5  push    r12
0x1400c08f7  push    r14
0x1400c08f9  push    r15
0x1400c08fb  sub     rsp, 60h
0x1400c08ff  mov     rdi, r9
0x1400c0902  mov     ebx, r8d
0x1400c0905  mov     rbp, rdx
0x1400c0908  mov     rsi, rcx
0x1400c090b  lea     r14, WPP_RECORDER_INITIALIZED
0x1400c0912  xor     r12d, r12d
0x1400c0915  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c091c  lea     r15, WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids
0x1400c0923  jz      short loc_1400C095B
0x1400c0925  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c092c  cmp     byte ptr [rcx+29h], 5
0x1400c0930  jnb     short loc_1400C0939
0x1400c0932  cmp     [rcx+48h], r12w
0x1400c0937  jz      short loc_1400C095B
0x1400c0939  mov     eax, [rsi+10h]
0x1400c093c  mov     r9d, 74h ; 't'
0x1400c0942  mov     rcx, [rcx+40h]
0x1400c0946  mov     dl, 5
0x1400c0948  mov     [rsp+98h+var_68], eax
0x1400c094c  mov     [rsp+98h+var_70], rsi
0x1400c0951  mov     [rsp+98h+var_78], r15
0x1400c0956  call    WPP_RECORDER_SF_qD
0x1400c095b  mov     rcx, [rsi+698h]; void *
0x1400c0962  test    rcx, rcx
0x1400c0965  jz      short loc_1400C0973
0x1400c0967  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400c096c  mov     [rsi+698h], r12
0x1400c0973  mov     rcx, [rsi+4B8h]; void *
0x1400c097a  test    rcx, rcx
0x1400c097d  jz      short loc_1400C098B
0x1400c097f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400c0984  mov     [rsi+4B8h], r12
0x1400c098b  mov     byte ptr [rsp+98h+var_58], r12b
0x1400c0990  mov     r9b, 1
0x1400c0993  mov     dword ptr [rsp+98h+var_60], ebx
0x1400c0997  mov     r8, rbp
0x1400c099a  mov     [rsp+98h+var_68], 0Ch
0x1400c09a2  mov     edx, 78h ; 'x'
0x1400c09a7  mov     dword ptr [rsp+98h+var_70], 1
0x1400c09af  mov     rcx, rsi
0x1400c09b2  mov     byte ptr [rsp+98h+var_78], r12b
0x1400c09b7  call    ?InitializeWithoutOid@COidJobBase@@IEAAHW4_WFC_JOB_TYPE@@PEAVCAdapter@@_N2W4_WFC_SERIALIZED_JOB_PRIORITY_SCOPE@@W4_WFC_SERIALIZED_JOB_PRIORITY@@K2@Z; COidJobBase::InitializeWithoutOid(_WFC_JOB_TYPE,CAdapter *,bool,bool,_WFC_SERIALIZED_JOB_PRIORITY_SCOPE,_WFC_SERIALIZED_JOB_PRIORITY,ulong,bool)
0x1400c09bc  mov     ebp, eax
0x1400c09be  test    eax, eax
0x1400c09c0  jz      short loc_1400C0A01
0x1400c09c2  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c09c9  jz      loc_1400C0E9E
0x1400c09cf  mov     ecx, [rsi+10h]
0x1400c09d2  mov     r9d, 75h ; 'u'
0x1400c09d8  mov     dword ptr [rsp+98h+var_60], eax
0x1400c09dc  mov     dl, 2
0x1400c09de  mov     [rsp+98h+var_68], ecx
0x1400c09e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c09e9  mov     [rsp+98h+var_70], rsi
0x1400c09ee  mov     [rsp+98h+var_78], r15
0x1400c09f3  mov     rcx, [rcx+40h]
0x1400c09f7  call    WPP_RECORDER_SF_qDD
0x1400c09fc  jmp     loc_1400C0E5B
0x1400c0a01  movzx   r15d, [rsp+98h+arg_28]
0x1400c0a0a  lea     rax, WPP_RECORDER_INITIALIZED
0x1400c0a11  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400c0a18  movzx   r14d, [rsp+98h+arg_20]
0x1400c0a21  jz      short loc_1400C0A6B
0x1400c0a23  cmp     [rsp+98h+arg_40], r12
0x1400c0a2b  lea     rdx, [rdi+8]
0x1400c0a2f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c0a36  mov     r8d, r12d
0x1400c0a39  mov     eax, [rsi+10h]
0x1400c0a3c  setnz   r8b
0x1400c0a40  mov     [rsp+98h+var_40], r8d
0x1400c0a45  mov     [rsp+98h+var_48], r15d
0x1400c0a4a  mov     rcx, [rcx+40h]
0x1400c0a4e  mov     [rsp+98h+var_50], r14d
0x1400c0a53  mov     [rsp+98h+var_58], rdi
0x1400c0a58  mov     [rsp+98h+var_60], rdx
0x1400c0a5d  mov     [rsp+98h+var_68], eax
0x1400c0a61  mov     [rsp+98h+var_70], rsi
0x1400c0a66  call    WPP_RECORDER_SF_qD_SSID__MAC_ddd
0x1400c0a6b  or      byte ptr [rsi+499h], 8
0x1400c0a72  movups  xmm0, xmmword ptr [rdi]
0x1400c0a75  movups  xmmword ptr [rsi+288h], xmm0
0x1400c0a7c  movups  xmm1, xmmword ptr [rdi+10h]
0x1400c0a80  movups  xmmword ptr [rsi+298h], xmm1
0x1400c0a87  movups  xmm0, xmmword ptr [rdi+1Ch]
0x1400c0a8b  movups  xmmword ptr [rsi+2A4h], xmm0
0x1400c0a92  test    r15b, r15b
0x1400c0a95  jnz     short loc_1400C0AAB
0x1400c0a97  test    r14b, r14b
0x1400c0a9a  jz      short loc_1400C0AAB
0x1400c0a9c  lea     rbx, [rsi+2B4h]
0x1400c0aa3  mov     dword ptr [rbx], 1D4C0h
0x1400c0aa9  jmp     short loc_1400C0ACA
0x1400c0aab  lea     rbx, [rsi+2B4h]
0x1400c0ab2  cmp     [rsp+98h+arg_38], r12b
0x1400c0aba  jz      short loc_1400C0AC4
0x1400c0abc  mov     dword ptr [rbx], 1388h
0x1400c0ac2  jmp     short loc_1400C0ACA
0x1400c0ac4  mov     dword ptr [rbx], 3A98h
0x1400c0aca  call    Feature_WiFiCx_TlvParserStaging__private_IsEnabledDeviceUsageNoInline
0x1400c0acf  mov     ecx, [rbx]
0x1400c0ad1  lea     r8, [rsi+294h]
0x1400c0ad8  test    eax, eax
0x1400c0ada  mov     [rsi+2B8h], ecx
0x1400c0ae0  mov     eax, [rsi+290h]
0x1400c0ae6  lea     rbx, [rsi+5B4h]
0x1400c0aed  lea     rdx, [rsi+258h]
0x1400c0af4  jz      short loc_1400C0B62
0x1400c0af6  mov     [rsi+5C4h], r12b
0x1400c0afd  lea     r12, [rsi+50Ch]
0x1400c0b04  mov     dword ptr [rbx], 4
0x1400c0b0a  mov     dword ptr [rsi+5BCh], 3
0x1400c0b14  mov     byte ptr [rsi+5B8h], 1
0x1400c0b1b  mov     dword ptr [rsi+5C8h], 32h ; '2'
0x1400c0b25  mov     dword ptr [rsi+5D0h], 28h ; '('
0x1400c0b2f  mov     dword ptr [rsi+5D4h], 64h ; 'd'
0x1400c0b39  mov     [rsi+5D8h], ecx
0x1400c0b3f  mov     [rsi+260h], r8
0x1400c0b46  mov     [rdx], eax
0x1400c0b48  or      dword ptr [rsi+5B0h], 2
0x1400c0b4f  mov     [rsi+600h], rdx
0x1400c0b56  mov     dword ptr [rsi+5F8h], 1
0x1400c0b60  jmp     short loc_1400C0BCE
0x1400c0b62  or      dword ptr [rsi+508h], 2
0x1400c0b69  lea     r12, [rsi+50Ch]
0x1400c0b70  mov     dword ptr [r12], 4
0x1400c0b78  mov     [rsi+260h], r8
0x1400c0b7f  mov     [rdx], eax
0x1400c0b81  mov     dword ptr [rsi+514h], 3
0x1400c0b8b  mov     byte ptr [rsi+510h], 1
0x1400c0b92  mov     byte ptr [rsi+51Ch], 0
0x1400c0b99  mov     dword ptr [rsi+520h], 32h ; '2'
0x1400c0ba3  mov     dword ptr [rsi+524h], 28h ; '('
0x1400c0bad  mov     dword ptr [rsi+528h], 64h ; 'd'
0x1400c0bb7  mov     [rsi+52Ch], ecx
0x1400c0bbd  mov     [rsi+550h], rdx
0x1400c0bc4  mov     dword ptr [rsi+548h], 1
0x1400c0bce  mov     ecx, 2Ch ; ','; unsigned __int64
0x1400c0bd3  mov     dword ptr [rsi+4B0h], 1
0x1400c0bdd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400c0be2  mov     [rsi+4B8h], rax
0x1400c0be9  mov     rcx, rax
0x1400c0bec  test    rax, rax
0x1400c0bef  jnz     short loc_1400C0C48
0x1400c0bf1  mov     ebp, 0C000009Ah
0x1400c0bf6  lea     r14, WPP_RECORDER_INITIALIZED
0x1400c0bfd  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c0c04  jz      loc_1400C0E9E
0x1400c0c0a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c0c11  lea     r9d, [rax+77h]
0x1400c0c15  mov     eax, [rsi+10h]
0x1400c0c18  lea     r15, WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids
0x1400c0c1f  mov     dword ptr [rsp+98h+var_60], 0C000009Ah
0x1400c0c27  mov     dl, 2
0x1400c0c29  mov     [rsp+98h+var_68], eax
0x1400c0c2d  mov     rcx, [rcx+40h]
0x1400c0c31  mov     [rsp+98h+var_70], rsi
0x1400c0c36  mov     [rsp+98h+var_78], r15
0x1400c0c3b  call    WPP_RECORDER_SF_qDD
0x1400c0c40  xor     r12d, r12d
0x1400c0c43  jmp     loc_1400C0E5B
0x1400c0c48  mov     eax, [rdi]
0x1400c0c4a  mov     [rcx], eax
0x1400c0c4c  movzx   eax, word ptr [rdi+4]
0x1400c0c50  mov     [rcx+4], ax
0x1400c0c54  mov     rcx, [rsi+4B8h]
0x1400c0c5b  movups  xmm0, xmmword ptr [rdi+8]
0x1400c0c5f  movups  xmmword ptr [rcx+8], xmm0
0x1400c0c63  movups  xmm1, xmmword ptr [rdi+18h]
0x1400c0c67  movups  xmmword ptr [rcx+18h], xmm1
0x1400c0c6b  mov     eax, [rdi+28h]
0x1400c0c6e  mov     [rcx+28h], eax
0x1400c0c71  mov     rax, [rsi+4B8h]
0x1400c0c78  mov     byte ptr [rax+6], 1
0x1400c0c7c  cmp     dword ptr [rdi+8], 7
0x1400c0c80  jnz     short loc_1400C0CA5
0x1400c0c82  lea     rcx, [rdi+0Ch]; Source1
0x1400c0c86  mov     r8d, 7; Length
0x1400c0c8c  lea     rdx, aDirect; "DIRECT-"
0x1400c0c93  call    cs:__imp_RtlCompareMemory
0x1400c0c9a  nop     dword ptr [rax+rax+00h]
0x1400c0c9f  cmp     rax, 7
0x1400c0ca3  jz      short loc_1400C0CC9
0x1400c0ca5  call    Feature_WiFiCx_TlvParserStaging__private_IsEnabledDeviceUsageNoInline
0x1400c0caa  test    eax, eax
0x1400c0cac  jz      short loc_1400C0CB6
0x1400c0cae  mov     dword ptr [rbx], 1
0x1400c0cb4  jmp     short loc_1400C0CBE
0x1400c0cb6  mov     dword ptr [r12], 1
0x1400c0cbe  mov     rax, [rsi+4B8h]
0x1400c0cc5  mov     byte ptr [rax+6], 2
0x1400c0cc9  mov     al, [rsi+498h]
0x1400c0ccf  xor     r12d, r12d
0x1400c0cd2  and     al, 0EFh
0x1400c0cd4  shl     r15b, 4
0x1400c0cd8  or      al, r15b
0x1400c0cdb  shl     r14b, 3
0x1400c0cdf  and     al, 0F7h
0x1400c0ce1  mov     r15b, 20h ; ' '
0x1400c0ce4  or      al, r14b
0x1400c0ce7  mov     [rsi+498h], al
0x1400c0ced  cmp     [rsp+98h+arg_40], r12
0x1400c0cf5  jz      loc_1400C0D7C
0x1400c0cfb  mov     rcx, [rsi+218h]
0x1400c0d02  add     rcx, 8
0x1400c0d06  mov     rax, [rcx]
0x1400c0d09  mov     rax, [rax+8]
0x1400c0d0d  call    _guard_dispatch_icall
0x1400c0d12  mov     rdx, [rsp+98h+arg_40]; struct _WFD_OTA_CHANNEL *
0x1400c0d1a  lea     r9, [rsi+500h]; unsigned int *
0x1400c0d21  mov     rcx, rax; this
0x1400c0d24  lea     r8, [rsi+4C0h]; enum _WDI_BAND_ID *
0x1400c0d2b  call    ?ConvertP2PChannelToBandChannel@@YAHPEAVCAdapterPropertyCache@@PEAU_WFD_OTA_CHANNEL@@PEAW4_WDI_BAND_ID@@PEAI@Z; ConvertP2PChannelToBandChannel(CAdapterPropertyCache *,_WFD_OTA_CHANNEL *,_WDI_BAND_ID *,uint *)
0x1400c0d30  test    eax, eax
0x1400c0d32  jnz     short loc_1400C0D7C
0x1400c0d34  lea     r14, WPP_RECORDER_INITIALIZED
0x1400c0d3b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c0d42  lea     rbx, WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids
0x1400c0d49  jz      short loc_1400C0D73
0x1400c0d4b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c0d52  lea     r9d, [r12+78h]
0x1400c0d57  mov     eax, [rsi+10h]
0x1400c0d5a  mov     dl, 4
0x1400c0d5c  mov     [rsp+98h+var_68], eax
0x1400c0d60  mov     [rsp+98h+var_70], rsi
0x1400c0d65  mov     rcx, [rcx+40h]
0x1400c0d69  mov     [rsp+98h+var_78], rbx
0x1400c0d6e  call    WPP_RECORDER_SF_qD
0x1400c0d73  or      [rsi+498h], r15b
0x1400c0d7a  jmp     short loc_1400C0D8A
0x1400c0d7c  lea     rbx, WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids
0x1400c0d83  lea     r14, WPP_RECORDER_INITIALIZED
0x1400c0d8a  test    [rsi+498h], r15b
0x1400c0d91  jnz     short loc_1400C0E03
0x1400c0d93  mov     rcx, [rsp+98h+arg_48]
0x1400c0d9b  test    rcx, rcx
0x1400c0d9e  jz      short loc_1400C0E03
0x1400c0da0  cmp     [rcx+310h], r12b
0x1400c0da7  jz      short loc_1400C0DC1
0x1400c0da9  mov     eax, [rcx+30Ch]
0x1400c0daf  mov     [rsi+4C0h], eax
0x1400c0db5  mov     eax, [rcx+308h]
0x1400c0dbb  mov     [rsi+500h], eax
0x1400c0dc1  cmp     byte ptr [rcx+310h], 1
0x1400c0dc8  jnz     short loc_1400C0E03
0x1400c0dca  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c0dd1  jz      short loc_1400C0DFC
0x1400c0dd3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c0dda  mov     r9d, 79h ; 'y'
0x1400c0de0  mov     eax, [rsi+10h]
0x1400c0de3  mov     dl, 4
0x1400c0de5  mov     [rsp+98h+var_68], eax
0x1400c0de9  mov     [rsp+98h+var_70], rsi
0x1400c0dee  mov     rcx, [rcx+40h]
0x1400c0df2  mov     [rsp+98h+var_78], rbx
0x1400c0df7  call    WPP_RECORDER_SF_qD
0x1400c0dfc  or      [rsi+498h], r15b
0x1400c0e03  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c0e0a  lea     r15, WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids
0x1400c0e11  movzx   ebx, [rsp+98h+arg_30]
0x1400c0e19  jz      short loc_1400C0E48
0x1400c0e1b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c0e22  mov     r9d, 7Ah ; 'z'
0x1400c0e28  mov     eax, [rsi+10h]
0x1400c0e2b  mov     dl, 4
0x1400c0e2d  mov     dword ptr [rsp+98h+var_60], ebx
0x1400c0e31  mov     [rsp+98h+var_68], eax
0x1400c0e35  mov     rcx, [rcx+40h]
0x1400c0e39  mov     [rsp+98h+var_70], rsi
0x1400c0e3e  mov     [rsp+98h+var_78], r15
0x1400c0e43  call    WPP_RECORDER_SF_qDD
0x1400c0e48  mov     al, [rsi+499h]
0x1400c0e4e  and     al, 0FBh
0x1400c0e50  shl     bl, 2
0x1400c0e53  or      al, bl
0x1400c0e55  mov     [rsi+499h], al
0x1400c0e5b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c0e62  jz      short loc_1400C0E9E
0x1400c0e64  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c0e6b  cmp     byte ptr [rcx+29h], 5
0x1400c0e6f  jnb     short loc_1400C0E78
0x1400c0e71  cmp     [rcx+48h], r12w
0x1400c0e76  jz      short loc_1400C0E9E
0x1400c0e78  mov     eax, [rsi+10h]
0x1400c0e7b  mov     r9d, 7Bh ; '{'
0x1400c0e81  mov     rcx, [rcx+40h]
0x1400c0e85  mov     dl, 5
0x1400c0e87  mov     dword ptr [rsp+98h+var_60], ebp
0x1400c0e8b  mov     [rsp+98h+var_68], eax
0x1400c0e8f  mov     [rsp+98h+var_70], rsi
0x1400c0e94  mov     [rsp+98h+var_78], r15
0x1400c0e99  call    WPP_RECORDER_SF_qDD
0x1400c0e9e  mov     eax, ebp
  ... truncated ...
```
