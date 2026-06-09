# CP2PDiscoverJob::OnJobStepCompleted(int,void *)

- ea: `0x1400c20b0`
- end: `0x1400c25e8`
- name: `?OnJobStepCompleted@CP2PDiscoverJob@@UEAAXHPEAX@Z`
- size: `1336`
- prototype: `void __fastcall(CP2PDiscoverJob *__hidden this, int, void *)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1400032f0`
- `0x140012f80`
- `0x140016d00`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14002073c`
- `0x14002bd34`
- `0x140038c74`
- `0x140060f7c`
- `0x140063e84`
- `0x1400c06bc`
- `0x1400c20b0`
- `0x1400c3340`
- `0x1400c3a28`
- `0x1400dfd40`

## pseudocode

```c
void __fastcall CP2PDiscoverJob::OnJobStepCompleted(CP2PDiscoverJob *this, __int64 a2, void *a3, int a4)
{
  unsigned int StatusFromTaskOutput; // edi
  char v6; // si
  __int64 v7; // rcx
  int v8; // r9d
  int v9; // edx
  unsigned int v10; // eax
  unsigned int v11; // eax
  char v12; // al
  __int64 v13; // rcx
  CPropertyCache *v14; // rax
  unsigned int v15; // edx
  __int64 v16; // r8
  int v17; // r9d
  int v18; // [rsp+20h] [rbp-78h]
  int v19; // [rsp+30h] [rbp-68h]
  __int64 v20; // [rsp+38h] [rbp-60h]
  unsigned int v21; // [rsp+A0h] [rbp+8h] BYREF

  StatusFromTaskOutput = a2;
  v6 = 1;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      (_DWORD)a3,
      89,
      (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  }
  v7 = *((unsigned __int8 *)this + 1176);
  if ( (v7 & 1) != 0 )
  {
    StatusFromTaskOutput = -1073676276;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_47;
    v8 = 90;
    LODWORD(v20) = -1073676276;
LABEL_8:
    v19 = *((_DWORD *)this + 4);
LABEL_9:
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      (_DWORD)a3,
      v8,
      (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
      (char)this,
      v19,
      v20);
    goto LABEL_47;
  }
  v9 = *((_DWORD *)this + 148) - 1;
  if ( *((_DWORD *)this + 148) == 1 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 4;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        (_DWORD)a3,
        93,
        (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
        (char)this,
        *((_DWORD *)this + 4));
    }
    *((_BYTE *)this + 1177) |= 2u;
    v11 = CP2PDiscoverJob::TriggerDiscover((enum _WDF_EXECUTION_LEVEL)this);
    StatusFromTaskOutput = v11;
    if ( !v11 )
    {
      *((_DWORD *)this + 148) = 2;
      v6 = 0;
      goto LABEL_47;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_47;
    v8 = 94;
    LODWORD(v20) = v11;
    goto LABEL_8;
  }
  a2 = (unsigned int)(*((_DWORD *)this + 148) - 2);
  if ( *((_DWORD *)this + 148) == 2 )
  {
    if ( (v7 & 4) != 0 || (*((_BYTE *)this + 1177) & (unsigned __int8)~((unsigned __int8)v7 >> 1) & 1) != 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qDDDDD(
          WPP_GLOBAL_Control->DeviceExtension,
          ((unsigned int)v7 >> 2) & 1,
          (_DWORD)a3,
          a4,
          v18,
          (char)this,
          *((_DWORD *)this + 4),
          StatusFromTaskOutput,
          (v7 & 4) != 0,
          *((_BYTE *)this + 1177) & 1,
          (v7 & 2) != 0);
      *((_BYTE *)this + 1176) &= ~4u;
      v6 = 0;
      *((_BYTE *)this + 1177) &= ~1u;
      if ( (unsigned int)Feature_WiFiCx_TlvParserStaging__private_IsEnabledDeviceUsageNoInline(v7, a2, a3) )
        *((_DWORD *)this + 364) &= ~1u;
      else
        *((_DWORD *)this + 322) &= ~1u;
      v10 = CP2PDiscoverJob::TriggerDiscover((enum _WDF_EXECUTION_LEVEL)this);
      StatusFromTaskOutput = v10;
      if ( !v10 )
      {
        *((_DWORD *)this + 148) = 3;
        goto LABEL_47;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_47;
      v8 = 92;
      LODWORD(v20) = v10;
      v19 = *((_DWORD *)this + 4);
      goto LABEL_9;
    }
  }
  else
  {
    a2 = (unsigned int)(*((_DWORD *)this + 148) - 3);
    if ( *((_DWORD *)this + 148) == 3 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 4;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          (_DWORD)a3,
          95,
          (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
          (char)this,
          *((_DWORD *)this + 4));
        LOBYTE(v7) = *((_BYTE *)this + 1176);
      }
    }
    else if ( *((_DWORD *)this + 148) == 4 )
    {
      StatusFromTaskOutput = 0;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 4;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          (_DWORD)a3,
          96,
          (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
          (char)this,
          *((_DWORD *)this + 4));
      }
      goto LABEL_47;
    }
  }
  if ( (v7 & 2) != 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        (_DWORD)a3,
        97,
        (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        StatusFromTaskOutput);
    }
    StatusFromTaskOutput = 0;
  }
  else if ( StatusFromTaskOutput )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_qDdd(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        (_DWORD)a3,
        98,
        (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        StatusFromTaskOutput,
        StatusFromTaskOutput);
    }
  }
  else
  {
    v21 = 0;
    StatusFromTaskOutput = CMessageHelper::GetStatusFromTaskOutput((CP2PDiscoverJob *)((char *)this + 704), (int *)&v21);
    if ( !StatusFromTaskOutput )
      StatusFromTaskOutput = v21;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        (_DWORD)a3,
        99,
        (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        StatusFromTaskOutput);
    }
  }
LABEL_47:
  v12 = *((_BYTE *)this + 1177);
  if ( (v12 & 2) != 0 )
  {
    if ( !StatusFromTaskOutput && !v6 )
      goto LABEL_66;
    v13 = *((_QWORD *)this + 67);
    *((_BYTE *)this + 1177) = v12 & 0xFD;
    v21 = 0;
    v14 = (CPropertyCache *)(*(__int64 (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)(v13 + 8) + 8LL))(
                              v13 + 8,
                              a2,
                              a3);
    if ( !(unsigned int)CPropertyCache::GetPropertyULong(v14, 0x34u, &v21)
      && !(unsigned int)CWfdChangeListenStateJob::Initialize(
                          (char *)this + 1696,
                          *((_QWORD *)this + 67),
                          *((unsigned int *)this + 14),
                          v21)
      && !(unsigned int)CJobBase::StartChildJob(this, (CP2PDiscoverJob *)((char *)this + 1696)) )
    {
      StatusFromTaskOutput = 0;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 4;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          (_DWORD)a3,
          100,
          (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
          (char)this,
          *((_DWORD *)this + 4));
      }
      *((_DWORD *)this + 148) = 4;
      goto LABEL_66;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        (_DWORD)a3,
        101,
        (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
        (char)this,
        *((_DWORD *)this + 4));
    }
    StatusFromTaskOutput = -1073741823;
  }
  else if ( !StatusFromTaskOutput && !v6 )
  {
    goto LABEL_66;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 4;
    LODWORD(v20) = StatusFromTaskOutput;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      (_DWORD)a3,
      102,
      (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v20);
  }
  v15 = *((_DWORD *)this + 321);
  *((_DWORD *)this + 148) = 5;
  if ( v15 )
  {
    NotificationManager::DeregisterNotificationHandler((NotificationManager *)(*((_QWORD *)this + 67) + 1072LL), v15);
    *((_DWORD *)this + 321) = 0;
  }
  CP2PDiscoverJob::PrepareCompletionIndication(this);
  CJobBase::CompleteJob(this, StatusFromTaskOutput, v16, v17);
LABEL_66:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    LODWORD(v20) = StatusFromTaskOutput;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      (_DWORD)a3,
      103,
      (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v20);
  }
}

```

## disassembly

```asm
0x1400c20b0  push    rbx
0x1400c20b2  push    rbp
0x1400c20b3  push    rsi
0x1400c20b4  push    rdi
0x1400c20b5  push    r14
0x1400c20b7  push    r15
0x1400c20b9  sub     rsp, 68h
0x1400c20bd  mov     edi, edx
0x1400c20bf  mov     rbx, rcx
0x1400c20c2  mov     esi, 1
0x1400c20c7  lea     r14, WPP_RECORDER_INITIALIZED
0x1400c20ce  xor     ebp, ebp
0x1400c20d0  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c20d7  lea     r15, WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids
0x1400c20de  jz      short loc_1400C2115
0x1400c20e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c20e7  cmp     byte ptr [rcx+29h], 5
0x1400c20eb  jnb     short loc_1400C20F3
0x1400c20ed  cmp     [rcx+48h], bp
0x1400c20f1  jz      short loc_1400C2115
0x1400c20f3  mov     eax, [rbx+10h]
0x1400c20f6  mov     r9d, 59h ; 'Y'
0x1400c20fc  mov     rcx, [rcx+40h]
0x1400c2100  mov     dl, 5
0x1400c2102  mov     [rsp+98h+var_68], eax
0x1400c2106  mov     [rsp+98h+var_70], rbx
0x1400c210b  mov     [rsp+98h+var_78], r15
0x1400c2110  call    WPP_RECORDER_SF_qD
0x1400c2115  movzx   ecx, byte ptr [rbx+498h]
0x1400c211c  test    sil, cl
0x1400c211f  jz      short loc_1400C2169
0x1400c2121  mov     edi, 0C001000Ch
0x1400c2126  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c212d  jz      loc_1400C2411
0x1400c2133  mov     r9d, 5Ah ; 'Z'
0x1400c2139  mov     dword ptr [rsp+98h+var_60], 0C001000Ch
0x1400c2141  mov     eax, [rbx+10h]
0x1400c2144  mov     [rsp+98h+var_68], eax
0x1400c2148  mov     dl, 2
0x1400c214a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c2151  mov     [rsp+98h+var_70], rbx
0x1400c2156  mov     [rsp+98h+var_78], r15
0x1400c215b  mov     rcx, [rcx+40h]
0x1400c215f  call    WPP_RECORDER_SF_qDD
0x1400c2164  jmp     loc_1400C2411
0x1400c2169  mov     edx, [rbx+250h]
0x1400c216f  sub     edx, esi
0x1400c2171  jz      loc_1400C23A5
0x1400c2177  sub     edx, esi
0x1400c2179  jz      loc_1400C2202
0x1400c217f  sub     edx, esi
0x1400c2181  jz      short loc_1400C21C8
0x1400c2183  cmp     edx, esi
0x1400c2185  jnz     loc_1400C2220
0x1400c218b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c2192  mov     edi, ebp
0x1400c2194  jz      loc_1400C2411
0x1400c219a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c21a1  mov     r9d, 60h ; '`'
0x1400c21a7  mov     eax, [rbx+10h]
0x1400c21aa  mov     dl, 4
0x1400c21ac  mov     [rsp+98h+var_68], eax
0x1400c21b0  mov     [rsp+98h+var_70], rbx
0x1400c21b5  mov     rcx, [rcx+40h]
0x1400c21b9  mov     [rsp+98h+var_78], r15
0x1400c21be  call    WPP_RECORDER_SF_qD
0x1400c21c3  jmp     loc_1400C2411
0x1400c21c8  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c21cf  jz      short loc_1400C2220
0x1400c21d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c21d8  mov     r9d, 5Fh ; '_'
0x1400c21de  mov     eax, [rbx+10h]
0x1400c21e1  mov     dl, 4
0x1400c21e3  mov     [rsp+98h+var_68], eax
0x1400c21e7  mov     [rsp+98h+var_70], rbx
0x1400c21ec  mov     rcx, [rcx+40h]
0x1400c21f0  mov     [rsp+98h+var_78], r15
0x1400c21f5  call    WPP_RECORDER_SF_qD
0x1400c21fa  mov     cl, [rbx+498h]
0x1400c2200  jmp     short loc_1400C2220
0x1400c2202  test    cl, 4
0x1400c2205  jnz     loc_1400C22F5
0x1400c220b  mov     al, cl
0x1400c220d  shr     al, 1
0x1400c220f  not     al
0x1400c2211  and     al, [rbx+499h]
0x1400c2217  test    sil, al
0x1400c221a  jnz     loc_1400C22F5
0x1400c2220  test    cl, 2
0x1400c2223  jz      short loc_1400C2262
0x1400c2225  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c222c  jz      short loc_1400C225B
0x1400c222e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c2235  mov     r9d, 61h ; 'a'
0x1400c223b  mov     eax, [rbx+10h]
0x1400c223e  mov     dl, 4
0x1400c2240  mov     dword ptr [rsp+98h+var_60], edi
0x1400c2244  mov     [rsp+98h+var_68], eax
0x1400c2248  mov     rcx, [rcx+40h]
0x1400c224c  mov     [rsp+98h+var_70], rbx
0x1400c2251  mov     [rsp+98h+var_78], r15
0x1400c2256  call    WPP_RECORDER_SF_qDD
0x1400c225b  mov     edi, ebp
0x1400c225d  jmp     loc_1400C2411
0x1400c2262  test    edi, edi
0x1400c2264  jz      short loc_1400C22A9
0x1400c2266  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c226d  jz      loc_1400C2411
0x1400c2273  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c227a  mov     r9d, 62h ; 'b'
0x1400c2280  mov     eax, [rbx+10h]
0x1400c2283  mov     dl, 2
0x1400c2285  mov     [rsp+98h+var_58], edi
0x1400c2289  mov     dword ptr [rsp+98h+var_60], edi
0x1400c228d  mov     rcx, [rcx+40h]
0x1400c2291  mov     [rsp+98h+var_68], eax
0x1400c2295  mov     [rsp+98h+var_70], rbx
0x1400c229a  mov     [rsp+98h+var_78], r15
0x1400c229f  call    WPP_RECORDER_SF_qDdd
0x1400c22a4  jmp     loc_1400C2411
0x1400c22a9  lea     rcx, [rbx+2C0h]; struct Task *
0x1400c22b0  mov     [rsp+98h+arg_0], ebp
0x1400c22b7  lea     rdx, [rsp+98h+arg_0]; int *
0x1400c22bf  call    ?GetStatusFromTaskOutput@CMessageHelper@@SAHPEAVTask@@PEAH@Z; CMessageHelper::GetStatusFromTaskOutput(Task *,int *)
0x1400c22c4  test    eax, eax
0x1400c22c6  mov     edi, eax
0x1400c22c8  cmovz   edi, [rsp+98h+arg_0]
0x1400c22d0  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c22d7  jz      loc_1400C2411
0x1400c22dd  mov     eax, [rbx+10h]
0x1400c22e0  mov     r9d, 63h ; 'c'
0x1400c22e6  mov     dword ptr [rsp+98h+var_60], edi
0x1400c22ea  mov     dl, 4
0x1400c22ec  mov     [rsp+98h+var_68], eax
0x1400c22f0  jmp     loc_1400C214A
0x1400c22f5  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c22fc  jz      short loc_1400C233E
0x1400c22fe  movzx   eax, byte ptr [rbx+499h]
0x1400c2305  mov     edx, ecx
0x1400c2307  shr     ecx, 1
0x1400c2309  and     eax, esi
0x1400c230b  and     ecx, esi
0x1400c230d  shr     edx, 2
0x1400c2310  mov     [rsp+98h+var_48], ecx
0x1400c2314  and     edx, esi
0x1400c2316  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c231d  mov     [rsp+98h+var_50], eax
0x1400c2321  mov     eax, [rbx+10h]
0x1400c2324  mov     [rsp+98h+var_58], edx
0x1400c2328  mov     rcx, [rcx+40h]
0x1400c232c  mov     dword ptr [rsp+98h+var_60], edi
0x1400c2330  mov     [rsp+98h+var_68], eax
0x1400c2334  mov     [rsp+98h+var_70], rbx
0x1400c2339  call    WPP_RECORDER_SF_qDDDDD
0x1400c233e  and     byte ptr [rbx+498h], 0FBh
0x1400c2345  mov     sil, bpl
0x1400c2348  and     byte ptr [rbx+499h], 0FEh
0x1400c234f  call    Feature_WiFiCx_TlvParserStaging__private_IsEnabledDeviceUsageNoInline
0x1400c2354  test    eax, eax
0x1400c2356  jz      short loc_1400C2361
0x1400c2358  and     dword ptr [rbx+5B0h], 0FFFFFFFEh
0x1400c235f  jmp     short loc_1400C2368
0x1400c2361  and     dword ptr [rbx+508h], 0FFFFFFFEh
0x1400c2368  mov     rcx, rbx; this
0x1400c236b  call    ?TriggerDiscover@CP2PDiscoverJob@@QEAAHXZ; CP2PDiscoverJob::TriggerDiscover(void)
0x1400c2370  mov     edi, eax
0x1400c2372  test    eax, eax
0x1400c2374  jz      short loc_1400C2399
0x1400c2376  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c237d  jz      loc_1400C2411
0x1400c2383  mov     ecx, [rbx+10h]
0x1400c2386  mov     r9d, 5Ch ; '\'
0x1400c238c  mov     dword ptr [rsp+98h+var_60], eax
0x1400c2390  mov     [rsp+98h+var_68], ecx
0x1400c2394  jmp     loc_1400C2148
0x1400c2399  mov     dword ptr [rbx+250h], 3
0x1400c23a3  jmp     short loc_1400C2411
0x1400c23a5  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c23ac  jz      short loc_1400C23D7
0x1400c23ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c23b5  mov     r9d, 5Dh ; ']'
0x1400c23bb  mov     eax, [rbx+10h]
0x1400c23be  mov     dl, 4
0x1400c23c0  mov     [rsp+98h+var_68], eax
0x1400c23c4  mov     [rsp+98h+var_70], rbx
0x1400c23c9  mov     rcx, [rcx+40h]
0x1400c23cd  mov     [rsp+98h+var_78], r15
0x1400c23d2  call    WPP_RECORDER_SF_qD
0x1400c23d7  or      byte ptr [rbx+499h], 2
0x1400c23de  mov     rcx, rbx; this
0x1400c23e1  call    ?TriggerDiscover@CP2PDiscoverJob@@QEAAHXZ; CP2PDiscoverJob::TriggerDiscover(void)
0x1400c23e6  mov     edi, eax
0x1400c23e8  test    eax, eax
0x1400c23ea  jz      short loc_1400C2404
0x1400c23ec  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c23f3  jz      short loc_1400C2411
0x1400c23f5  mov     r9d, 5Eh ; '^'
0x1400c23fb  mov     dword ptr [rsp+98h+var_60], eax
0x1400c23ff  jmp     loc_1400C2141
0x1400c2404  mov     dword ptr [rbx+250h], 2
0x1400c240e  mov     sil, bpl
0x1400c2411  mov     al, [rbx+499h]
0x1400c2417  test    al, 2
0x1400c2419  jz      loc_1400C251A
0x1400c241f  test    edi, edi
0x1400c2421  jnz     short loc_1400C242C
0x1400c2423  test    sil, sil
0x1400c2426  jz      loc_1400C2598
0x1400c242c  mov     rcx, [rbx+218h]
0x1400c2433  and     al, 0FDh
0x1400c2435  mov     [rbx+499h], al
0x1400c243b  add     rcx, 8
0x1400c243f  mov     [rsp+98h+arg_0], ebp
0x1400c2446  mov     rax, [rcx]
0x1400c2449  mov     rax, [rax+8]
0x1400c244d  call    _guard_dispatch_icall
0x1400c2452  lea     r8, [rsp+98h+arg_0]; unsigned int *
0x1400c245a  mov     edx, 34h ; '4'; unsigned int
0x1400c245f  mov     rcx, rax; this
0x1400c2462  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x1400c2467  test    eax, eax
0x1400c2469  jnz     short loc_1400C24E1
0x1400c246b  mov     r9d, [rsp+98h+arg_0]
0x1400c2473  lea     rdi, [rbx+6A0h]
0x1400c247a  mov     r8d, [rbx+38h]
0x1400c247e  mov     rcx, rdi
0x1400c2481  mov     rdx, [rbx+218h]
0x1400c2488  call    ?Initialize@CWfdChangeListenStateJob@@QEAAHPEAVCAdapter@@KW4_WDI_P2P_LISTEN_STATE@@@Z; CWfdChangeListenStateJob::Initialize(CAdapter *,ulong,_WDI_P2P_LISTEN_STATE)
0x1400c248d  test    eax, eax
0x1400c248f  jnz     short loc_1400C24E1
0x1400c2491  mov     rdx, rdi; struct CJobBase *
0x1400c2494  mov     rcx, rbx; this
0x1400c2497  call    ?StartChildJob@CJobBase@@IEAAHPEAV1@@Z; CJobBase::StartChildJob(CJobBase *)
0x1400c249c  test    eax, eax
0x1400c249e  jnz     short loc_1400C24E1
0x1400c24a0  mov     edi, ebp
0x1400c24a2  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c24a9  jz      short loc_1400C24D2
0x1400c24ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c24b2  lea     r9d, [rax+64h]
0x1400c24b6  mov     eax, [rbx+10h]
0x1400c24b9  mov     dl, 4
0x1400c24bb  mov     [rsp+98h+var_68], eax
0x1400c24bf  mov     [rsp+98h+var_70], rbx
0x1400c24c4  mov     rcx, [rcx+40h]
0x1400c24c8  mov     [rsp+98h+var_78], r15
0x1400c24cd  call    WPP_RECORDER_SF_qD
0x1400c24d2  mov     dword ptr [rbx+250h], 4
0x1400c24dc  jmp     loc_1400C2598
0x1400c24e1  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c24e8  jz      short loc_1400C2513
0x1400c24ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c24f1  mov     r9d, 65h ; 'e'
0x1400c24f7  mov     eax, [rbx+10h]
0x1400c24fa  mov     dl, 4
0x1400c24fc  mov     [rsp+98h+var_68], eax
0x1400c2500  mov     [rsp+98h+var_70], rbx
0x1400c2505  mov     rcx, [rcx+40h]
0x1400c2509  mov     [rsp+98h+var_78], r15
0x1400c250e  call    WPP_RECORDER_SF_qD
0x1400c2513  mov     edi, 0C0000001h
0x1400c2518  jmp     short loc_1400C2523
0x1400c251a  test    edi, edi
0x1400c251c  jnz     short loc_1400C2523
0x1400c251e  test    sil, sil
0x1400c2521  jz      short loc_1400C2598
0x1400c2523  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c252a  jz      short loc_1400C2559
0x1400c252c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c2533  mov     r9d, 66h ; 'f'
0x1400c2539  mov     eax, [rbx+10h]
0x1400c253c  mov     dl, 4
0x1400c253e  mov     dword ptr [rsp+98h+var_60], edi
0x1400c2542  mov     [rsp+98h+var_68], eax
0x1400c2546  mov     rcx, [rcx+40h]
0x1400c254a  mov     [rsp+98h+var_70], rbx
0x1400c254f  mov     [rsp+98h+var_78], r15
0x1400c2554  call    WPP_RECORDER_SF_qDD
0x1400c2559  mov     edx, [rbx+504h]; unsigned int
0x1400c255f  mov     dword ptr [rbx+250h], 5
0x1400c2569  test    edx, edx
0x1400c256b  jz      short loc_1400C2586
0x1400c256d  mov     rcx, [rbx+218h]
0x1400c2574  add     rcx, 430h; this
0x1400c257b  call    ?DeregisterNotificationHandler@NotificationManager@@QEAAHK@Z; NotificationManager::DeregisterNotificationHandler(ulong)
0x1400c2580  mov     [rbx+504h], ebp
0x1400c2586  mov     rcx, rbx; this
0x1400c2589  call    ?PrepareCompletionIndication@CP2PDiscoverJob@@QEAAHXZ; CP2PDiscoverJob::PrepareCompletionIndication(void)
0x1400c258e  mov     edx, edi; int
0x1400c2590  mov     rcx, rbx; this
0x1400c2593  call    ?CompleteJob@CJobBase@@IEAAHH@Z; CJobBase::CompleteJob(int)
0x1400c2598  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c259f  jz      short loc_1400C25DA
0x1400c25a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c25a8  cmp     byte ptr [rcx+29h], 5
0x1400c25ac  jnb     short loc_1400C25B4
0x1400c25ae  cmp     [rcx+48h], bp
0x1400c25b2  jz      short loc_1400C25DA
0x1400c25b4  mov     eax, [rbx+10h]
0x1400c25b7  mov     r9d, 67h ; 'g'
  ... truncated ...
```
