# CBroker::SebEvent::OnEnable(void)

- ea: `0x18000df40`
- end: `0x18000e4e6`
- name: `?OnEnable@SebEvent@CBroker@@QEAAXXZ`
- size: `1446`
- prototype: `void __fastcall(CBroker::SebEvent *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009740`
- `0x1800168b0`

## callees

- `0x1800030e0`
- `0x180003120`
- `0x1800039a0`
- `0x180008c00`
- `0x18000df40`
- `0x180013950`
- `0x18001cf50`
- `0x18001d9ac`
- `0x1800223e0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000dffe`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000dffe`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000dfd2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000dfd2`
- `ntdll!RtlWakeAddressAll` at `0x18000e123`
- `ntdll!RtlWakeAddressAll` at `0x18000e123`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18000e0fd`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18000e0fd`
- `ntdll!NtQueryWnfStateData` at `0x18000e060`
- `ntdll!NtQueryWnfStateData` at `0x18000e060`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e004`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e004`
- `BrokerLib!BrSignalBrokerEvent2` at `0x18000e237`
- `BrokerLib!BrSignalBrokerEvent2` at `0x18000e237`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CBroker::SebEvent::OnEnable(CBroker::SebEvent *this)
{
  char *v2; // rdi
  char v3; // si
  _BYTE *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // r12d
  _QWORD *v8; // rcx
  int v9; // ecx
  int v10; // eax
  _QWORD *v11; // rcx
  unsigned int v12; // eax
  char *v13; // rcx
  __int64 v14; // rdx
  unsigned int v15; // edx
  unsigned __int8 v16; // al
  int v17; // ecx
  __int64 v18; // rcx
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  unsigned int v21; // edx
  _BYTE v22[4]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v23; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v24; // [rsp+48h] [rbp-B8h] BYREF
  void **pExceptionObject; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+68h] [rbp-98h]
  char *v28; // [rsp+70h] [rbp-90h]
  char v29; // [rsp+78h] [rbp-88h]
  DWORD CurrentThreadId; // [rsp+7Ch] [rbp-84h]
  _DWORD v31[1024]; // [rsp+80h] [rbp-80h] BYREF

  v24 = 0;
  v23 = 0;
  v22[0] = 0;
  v2 = (char *)this + 240;
  v28 = (char *)this + 240;
  v3 = 0;
  v4 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF__guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids,
      (char *)this + 120);
    v4 = WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)this + 39) && *((_BYTE *)this + 161) )
  {
    if ( (v4[28] & 0x40) == 0 )
      goto LABEL_7;
    if ( v4[25] < 4u )
      goto LABEL_28;
    v14 = 30;
    goto LABEL_34;
  }
  RtlAcquireSRWLockExclusive(v2);
  CurrentThreadId = GetCurrentThreadId();
  v3 = 1;
  v29 = 1;
  if ( !*((_DWORD *)this + 26) && !*((_DWORD *)this + 27) || !*((_DWORD *)this + 28) && !*((_DWORD *)this + 29) )
  {
    *((_QWORD *)this + 21) = 0;
    v13 = (char *)this + 152;
    *((_DWORD *)this + 38) = 0;
LABEL_26:
    RtlWakeAddressAll(v13, v5);
LABEL_27:
    v4 = WPP_GLOBAL_Control;
    goto LABEL_28;
  }
  if ( !*((_DWORD *)this + 38) )
  {
    v23 = 4096;
    v7 = NtQueryWnfStateData((char *)this + 104, 0, 0, &v24, v31, &v23);
    v8 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF__guid_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids,
        (char *)this + 120,
        v23);
      v8 = WPP_GLOBAL_Control;
    }
    if ( v7 < 0 )
    {
      if ( (*((_BYTE *)v8 + 28) & 0x40) != 0 && *((_BYTE *)v8 + 25) >= 2u )
        WPP_SF__guid_D(v8[2], 33, &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids, (char *)this + 120, v7);
      v26 = 0;
      if ( v7 == -1073741790 )
      {
        v27 = 5;
        pExceptionObject = &Broker::AccessDenied::`vftable';
        throw (Broker::AccessDenied *)&pExceptionObject;
      }
      if ( v7 == -1073741772 )
      {
        v27 = 3;
        pExceptionObject = &Broker::NotFound::`vftable';
        throw (Broker::NotFound *)&pExceptionObject;
      }
      v27 = 7;
      pExceptionObject = &Broker::EventInternalError::`vftable';
      throw (Broker::EventInternalError *)&pExceptionObject;
    }
    *((_BYTE *)this + 160) = 0;
    v22[0] = 0;
    v9 = *((_DWORD *)this + 25);
    if ( !v9 )
      goto LABEL_18;
    v15 = 0;
    if ( v23 < *((_DWORD *)this + 44) )
    {
LABEL_36:
      v16 = CBroker::SebEvent::EvaluateCondition(this, v15, v6);
      v22[0] = v16;
      v17 = *((_DWORD *)this + 25);
      if ( v17 != 1 && v17 != 4 )
        goto LABEL_18;
      v18 = *((_QWORD *)this + 17);
      if ( v18 )
      {
        if ( (int)BrSignalBrokerEvent2(v18, *((_QWORD *)this + 18), v22, 0, 0, 0) >= 0 )
          goto LABEL_18;
        v19 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_18;
        v20 = 35;
      }
      else
      {
        if ( (int)PubSebLevelEventSyncInternal(*((_QWORD *)this + 14), v16) >= 0 )
          goto LABEL_18;
        v19 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_18;
        v20 = 34;
      }
      WPP_SF__guid_(v19[2], v20, &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids, (char *)this + 120);
LABEL_18:
      v10 = v22[0];
      *((_BYTE *)this + 160) = v22[0];
      v11 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF__guid_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids,
          (char *)this + 120,
          v10);
        v11 = WPP_GLOBAL_Control;
      }
      if ( (*((_BYTE *)v11 + 28) & 0x40) != 0 && *((_BYTE *)v11 + 25) >= 4u )
        WPP_SF__guid_(v11[2], 37, &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids, (char *)this + 120);
      v12 = RtlSubscribeWnfStateChangeNotification(
              (char *)this + 168,
              *((_QWORD *)this + 13),
              v24,
              CBroker::SebPublishWnfEventCallback,
              this,
              0,
              0,
              0);
      if ( v12 )
      {
        if ( v12 == -1073741790 )
        {
          v26 = 0;
          v27 = 5;
          pExceptionObject = &Broker::AccessDenied::`vftable';
          throw (Broker::AccessDenied *)&pExceptionObject;
        }
        if ( v12 == -1073741772 )
        {
          v26 = 0;
          v27 = 3;
          pExceptionObject = &Broker::NotFound::`vftable';
          throw (Broker::NotFound *)&pExceptionObject;
        }
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids, v12);
        v26 = 0;
        v27 = 7;
        pExceptionObject = &Broker::EventInternalError::`vftable';
        throw (Broker::EventInternalError *)&pExceptionObject;
      }
      *((_QWORD *)this + 25) = 0;
      *((_DWORD *)this + 38) = 1;
      v13 = (char *)this + 152;
      goto LABEL_26;
    }
    if ( v9 == 4 )
    {
      v15 = (unsigned __int8)(v31[0] >> 14);
      if ( (unsigned __int8)(v31[0] >> 14) )
        goto LABEL_36;
      v21 = v31[0];
    }
    else
    {
      v21 = v31[0];
    }
    v15 = (v21 >> 1) & 1;
    goto LABEL_36;
  }
  v4 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
    goto LABEL_7;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v14 = 31;
LABEL_34:
    WPP_SF__guid_(*((_QWORD *)v4 + 2), v14, &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids, (char *)this + 120);
    goto LABEL_27;
  }
LABEL_28:
  if ( (v4[28] & 0x40) != 0 && v4[25] >= 4u )
    WPP_SF__guid_(*((_QWORD *)v4 + 2), 39, &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids, (char *)this + 120);
LABEL_7:
  if ( v3 )
    RtlReleaseSRWLockExclusive(v2);
}

```

## disassembly

```asm
0x18000df40  push    rbp
0x18000df42  push    rbx
0x18000df43  push    rsi
0x18000df44  push    rdi
0x18000df45  push    r12
0x18000df47  push    r13
0x18000df49  push    r14
0x18000df4b  push    r15
0x18000df4d  lea     rbp, [rsp-0F98h]
0x18000df55  mov     eax, 1098h
0x18000df5a  call    _alloca_probe
0x18000df5f  sub     rsp, rax
0x18000df62  mov     rax, cs:__security_cookie
0x18000df69  xor     rax, rsp
0x18000df6c  mov     [rbp+0FD0h+var_50], rax
0x18000df73  mov     rbx, rcx
0x18000df76  xor     r13d, r13d
0x18000df79  mov     [rsp+10D0h+var_1088], r13d
0x18000df7e  mov     [rsp+10D0h+var_108C], r13d
0x18000df83  mov     [rsp+10D0h+var_1090], r13b
0x18000df88  lea     rdi, [rcx+0F0h]
0x18000df8f  mov     [rsp+10D0h+var_1060], rdi
0x18000df94  xor     sil, sil
0x18000df97  mov     rcx, cs:WPP_GLOBAL_Control
0x18000df9e  test    byte ptr [rcx+1Ch], 40h
0x18000dfa2  jz      short loc_18000DFAE
0x18000dfa4  cmp     byte ptr [rcx+19h], 4
0x18000dfa8  jnb     loc_18000E162
0x18000dfae  cmp     dword ptr [rbx+9Ch], 0
0x18000dfb5  jz      short loc_18000DFFB
0x18000dfb7  cmp     byte ptr [rbx+0A1h], 0
0x18000dfbe  jz      short loc_18000DFFB
0x18000dfc0  test    byte ptr [rcx+1Ch], 40h
0x18000dfc4  jnz     loc_18000E2D6
0x18000dfca  test    sil, sil
0x18000dfcd  jz      short loc_18000DFD8
0x18000dfcf  mov     rcx, rdi
0x18000dfd2  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000dfd8  mov     rcx, [rbp+0FD0h+var_50]
0x18000dfdf  xor     rcx, rsp; StackCookie
0x18000dfe2  call    __security_check_cookie
0x18000dfe7  add     rsp, 1098h
0x18000dfee  pop     r15
0x18000dff0  pop     r14
0x18000dff2  pop     r13
0x18000dff4  pop     r12
0x18000dff6  pop     rdi
0x18000dff7  pop     rsi
0x18000dff8  pop     rbx
0x18000dff9  pop     rbp
0x18000dffa  retn
0x18000dffb  mov     rcx, rdi
0x18000dffe  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000e004  call    cs:__imp_GetCurrentThreadId
0x18000e00a  mov     [rsp+10D0h+var_1054], eax
0x18000e00e  mov     sil, 1
0x18000e011  mov     [rsp+10D0h+var_1058], sil
0x18000e016  cmp     dword ptr [rbx+68h], 0
0x18000e01a  jz      loc_18000E2EA
0x18000e020  cmp     dword ptr [rbx+70h], 0
0x18000e024  jz      loc_18000E2F5
0x18000e02a  cmp     dword ptr [rbx+98h], 0
0x18000e031  jnz     loc_18000E1A5
0x18000e037  mov     [rsp+10D0h+var_108C], 1000h
0x18000e03f  lea     rax, [rsp+10D0h+var_108C]
0x18000e044  mov     [rsp+10D0h+var_10A8], rax
0x18000e049  lea     rax, [rbp+0FD0h+var_1050]
0x18000e04d  mov     [rsp+10D0h+var_10B0], rax
0x18000e052  lea     r9, [rsp+10D0h+var_1088]
0x18000e057  xor     r8d, r8d
0x18000e05a  xor     edx, edx
0x18000e05c  lea     rcx, [rbx+68h]
0x18000e060  call    cs:__imp_NtQueryWnfStateData
0x18000e066  mov     r12d, eax
0x18000e069  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e070  test    byte ptr [rcx+1Ch], 40h
0x18000e074  jz      short loc_18000E080
0x18000e076  cmp     byte ptr [rcx+19h], 4
0x18000e07a  jnb     loc_18000E27E
0x18000e080  test    r12d, r12d
0x18000e083  js      loc_18000E315
0x18000e089  mov     byte ptr [rbx+0A0h], 0
0x18000e090  mov     [rsp+10D0h+var_1090], 0
0x18000e095  mov     ecx, [rbx+64h]
0x18000e098  test    ecx, ecx
0x18000e09a  jnz     loc_18000E1DE
0x18000e0a0  movzx   eax, [rsp+10D0h+var_1090]
0x18000e0a5  mov     [rbx+0A0h], al
0x18000e0ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e0b2  test    [rcx+1Ch], sil
0x18000e0b6  jz      short loc_18000E0C2
0x18000e0b8  cmp     byte ptr [rcx+19h], 4
0x18000e0bc  jnb     loc_18000E2AD
0x18000e0c2  test    byte ptr [rcx+1Ch], 40h
0x18000e0c6  jz      short loc_18000E0D2
0x18000e0c8  cmp     byte ptr [rcx+19h], 4
0x18000e0cc  jnb     loc_18000E187
0x18000e0d2  lea     rcx, [rbx+0A8h]
0x18000e0d9  mov     [rsp+10D0h+var_1098], r13d
0x18000e0de  mov     [rsp+10D0h+var_10A0], r13d
0x18000e0e3  mov     [rsp+10D0h+var_10A8], r13
0x18000e0e8  mov     [rsp+10D0h+var_10B0], rbx
0x18000e0ed  lea     r9, ?SebPublishWnfEventCallback@CBroker@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; CBroker::SebPublishWnfEventCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18000e0f4  mov     r8d, [rsp+10D0h+var_1088]
0x18000e0f9  mov     rdx, [rbx+68h]
0x18000e0fd  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x18000e103  test    eax, eax
0x18000e105  jnz     loc_18000E423
0x18000e10b  mov     [rbx+0C8h], r13
0x18000e112  mov     dword ptr [rbx+98h], 1
0x18000e11c  lea     rcx, [rbx+98h]
0x18000e123  call    cs:__imp_RtlWakeAddressAll
0x18000e129  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e130  test    byte ptr [rcx+1Ch], 40h
0x18000e134  jz      loc_18000DFCA
0x18000e13a  cmp     byte ptr [rcx+19h], 4
0x18000e13e  jb      loc_18000DFCA
0x18000e144  lea     r9, [rbx+78h]
0x18000e148  mov     edx, 27h ; '''
0x18000e14d  lea     r8, WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids
0x18000e154  mov     rcx, [rcx+10h]
0x18000e158  call    WPP_SF__guid_
0x18000e15d  jmp     loc_18000DFCA
0x18000e162  lea     r9, [rbx+78h]
0x18000e166  mov     edx, 1Dh
0x18000e16b  lea     r8, WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids
0x18000e172  mov     rcx, [rcx+10h]
0x18000e176  call    WPP_SF__guid_
0x18000e17b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e182  jmp     loc_18000DFAE
0x18000e187  lea     r9, [rbx+78h]
0x18000e18b  mov     edx, 25h ; '%'
0x18000e190  lea     r8, WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids
0x18000e197  mov     rcx, [rcx+10h]
0x18000e19b  call    WPP_SF__guid_
0x18000e1a0  jmp     loc_18000E0D2
0x18000e1a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e1ac  test    byte ptr [rcx+1Ch], 40h
0x18000e1b0  jz      loc_18000DFCA
0x18000e1b6  cmp     byte ptr [rcx+19h], 4
0x18000e1ba  jb      loc_18000E130
0x18000e1c0  mov     edx, 1Fh
0x18000e1c5  lea     r9, [rbx+78h]
0x18000e1c9  lea     r8, WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids
0x18000e1d0  mov     rcx, [rcx+10h]
0x18000e1d4  call    WPP_SF__guid_
0x18000e1d9  jmp     loc_18000E129
0x18000e1de  mov     edx, r13d; unsigned int
0x18000e1e1  mov     eax, [rbx+0B0h]
0x18000e1e7  cmp     [rsp+10D0h+var_108C], eax
0x18000e1eb  jnb     loc_18000E3C1
0x18000e1f1  mov     rcx, rbx; this
0x18000e1f4  call    ?EvaluateCondition@SebEvent@CBroker@@AEAAHK@Z; CBroker::SebEvent::EvaluateCondition(ulong)
0x18000e1f9  mov     [rsp+10D0h+var_1090], al
0x18000e1fd  mov     ecx, [rbx+64h]
0x18000e200  cmp     ecx, 1
0x18000e203  jz      short loc_18000E20E
0x18000e205  cmp     ecx, 4
0x18000e208  jnz     loc_18000E0A0
0x18000e20e  mov     rcx, [rbx+88h]
0x18000e215  test    rcx, rcx
0x18000e218  jz      loc_18000E3EA
0x18000e21e  mov     [rsp+10D0h+var_10A8], r13
0x18000e223  mov     dword ptr [rsp+10D0h+var_10B0], r13d
0x18000e228  xor     r9d, r9d
0x18000e22b  lea     r8, [rsp+10D0h+var_1090]
0x18000e230  mov     rdx, [rbx+90h]
0x18000e237  call    cs:__imp_BrSignalBrokerEvent2
0x18000e23d  test    eax, eax
0x18000e23f  jns     loc_18000E0A0
0x18000e245  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e24c  test    byte ptr [rcx+1Ch], 40h
0x18000e250  jz      loc_18000E0A0
0x18000e256  cmp     byte ptr [rcx+19h], 2
0x18000e25a  jb      loc_18000E0A0
0x18000e260  mov     edx, 23h ; '#'
0x18000e265  lea     r9, [rbx+78h]
0x18000e269  lea     r8, WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids
0x18000e270  mov     rcx, [rcx+10h]
0x18000e274  call    WPP_SF__guid_
0x18000e279  jmp     loc_18000E0A0
0x18000e27e  lea     r9, [rbx+78h]
0x18000e282  mov     edx, 20h ; ' '
0x18000e287  mov     r8d, [rsp+10D0h+var_108C]
0x18000e28c  mov     dword ptr [rsp+10D0h+var_10B0], r8d
0x18000e291  lea     r8, WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids
0x18000e298  mov     rcx, [rcx+10h]
0x18000e29c  call    WPP_SF__guid_D
0x18000e2a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e2a8  jmp     loc_18000E080
0x18000e2ad  lea     r9, [rbx+78h]
0x18000e2b1  mov     edx, 24h ; '$'
0x18000e2b6  mov     dword ptr [rsp+10D0h+var_10B0], eax
0x18000e2ba  lea     r8, WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids
0x18000e2c1  mov     rcx, [rcx+10h]
0x18000e2c5  call    WPP_SF__guid_D
0x18000e2ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e2d1  jmp     loc_18000E0C2
0x18000e2d6  cmp     byte ptr [rcx+19h], 4
0x18000e2da  jb      loc_18000E130
0x18000e2e0  mov     edx, 1Eh
0x18000e2e5  jmp     loc_18000E1C5
0x18000e2ea  cmp     dword ptr [rbx+6Ch], 0
0x18000e2ee  jz      short loc_18000E2FF
0x18000e2f0  jmp     loc_18000E020
0x18000e2f5  cmp     dword ptr [rbx+74h], 0
0x18000e2f9  jnz     loc_18000E02A
0x18000e2ff  mov     [rbx+0A8h], r13
0x18000e306  lea     rcx, [rbx+98h]
0x18000e30d  mov     [rcx], r13d
0x18000e310  jmp     loc_18000E123
0x18000e315  test    byte ptr [rcx+1Ch], 40h
0x18000e319  jz      short loc_18000E33F
0x18000e31b  cmp     byte ptr [rcx+19h], 2
0x18000e31f  jb      short loc_18000E33F
0x18000e321  lea     r9, [rbx+78h]
0x18000e325  mov     edx, 21h ; '!'
0x18000e32a  mov     dword ptr [rsp+10D0h+var_10B0], r12d
0x18000e32f  lea     r8, WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids
0x18000e336  mov     rcx, [rcx+10h]
0x18000e33a  call    WPP_SF__guid_D
0x18000e33f  xorps   xmm0, xmm0
0x18000e342  lea     rcx, [rsp+10D0h+pExceptionObject]; pExceptionObject
0x18000e347  movups  [rsp+10D0h+var_1078], xmm0
0x18000e34c  cmp     r12d, 0C0000022h
0x18000e353  jnz     short loc_18000E376
0x18000e355  mov     [rsp+10D0h+var_1068], 5
0x18000e35d  lea     rax, ??_7AccessDenied@Broker@@6B@; const Broker::AccessDenied::`vftable'
0x18000e364  mov     [rsp+10D0h+pExceptionObject], rax
0x18000e369  lea     rdx, _TI3?AUAccessDenied@Broker@@; pThrowInfo
0x18000e370  call    _CxxThrowException_0
0x18000e376  cmp     r12d, 0C0000034h
0x18000e37d  jnz     short loc_18000E3A0
0x18000e37f  mov     [rsp+10D0h+var_1068], 3
0x18000e387  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x18000e38e  mov     [rsp+10D0h+pExceptionObject], rax
0x18000e393  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x18000e39a  call    _CxxThrowException_0
0x18000e3a0  mov     [rsp+10D0h+var_1068], 7
0x18000e3a8  lea     rax, ??_7EventInternalError@Broker@@6B@; const Broker::EventInternalError::`vftable'
0x18000e3af  mov     [rsp+10D0h+pExceptionObject], rax
0x18000e3b4  lea     rdx, _TI3?AUEventInternalError@Broker@@; pThrowInfo
0x18000e3bb  call    _CxxThrowException_0
0x18000e3c1  cmp     ecx, 4
0x18000e3c4  jnz     short loc_18000E3DD
0x18000e3c6  mov     ecx, [rbp+0FD0h+var_1050]
0x18000e3c9  mov     eax, ecx
0x18000e3cb  shr     eax, 0Eh
0x18000e3ce  movzx   edx, al
0x18000e3d1  test    al, al
0x18000e3d3  jnz     loc_18000E1F1
0x18000e3d9  mov     edx, ecx
0x18000e3db  jmp     short loc_18000E3E0
0x18000e3dd  mov     edx, [rbp+0FD0h+var_1050]
0x18000e3e0  shr     edx, 1
0x18000e3e2  and     edx, 1
0x18000e3e5  jmp     loc_18000E1F1
0x18000e3ea  movzx   edx, al
0x18000e3ed  mov     rcx, [rbx+70h]
0x18000e3f1  call    PubSebLevelEventSyncInternal
0x18000e3f6  test    eax, eax
0x18000e3f8  jns     loc_18000E0A0
0x18000e3fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e405  test    byte ptr [rcx+1Ch], 40h
0x18000e409  jz      loc_18000E0A0
0x18000e40f  cmp     byte ptr [rcx+19h], 2
0x18000e413  jb      loc_18000E0A0
0x18000e419  mov     edx, 22h ; '"'
0x18000e41e  jmp     loc_18000E265
0x18000e423  cmp     eax, 0C0000022h
0x18000e428  jnz     short loc_18000E458
0x18000e42a  xorps   xmm0, xmm0
0x18000e42d  movups  [rsp+10D0h+var_1078], xmm0
0x18000e432  mov     [rsp+10D0h+var_1068], 5
0x18000e43a  lea     rax, ??_7AccessDenied@Broker@@6B@; const Broker::AccessDenied::`vftable'
0x18000e441  mov     [rsp+10D0h+pExceptionObject], rax
0x18000e446  lea     rdx, _TI3?AUAccessDenied@Broker@@; pThrowInfo
0x18000e44d  lea     rcx, [rsp+10D0h+pExceptionObject]; pExceptionObject
0x18000e452  call    _CxxThrowException_0
0x18000e458  cmp     eax, 0C0000034h
0x18000e45d  jnz     short loc_18000E48D
0x18000e45f  xorps   xmm0, xmm0
0x18000e462  movups  [rsp+10D0h+var_1078], xmm0
0x18000e467  mov     [rsp+10D0h+var_1068], 3
0x18000e46f  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x18000e476  mov     [rsp+10D0h+pExceptionObject], rax
0x18000e47b  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x18000e482  lea     rcx, [rsp+10D0h+pExceptionObject]; pExceptionObject
0x18000e487  call    _CxxThrowException_0
0x18000e48d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e494  test    byte ptr [rcx+1Ch], 40h
0x18000e498  jz      short loc_18000E4B8
0x18000e49a  cmp     byte ptr [rcx+19h], 2
0x18000e49e  jb      short loc_18000E4B8
0x18000e4a0  mov     edx, 26h ; '&'
0x18000e4a5  mov     r9d, eax
0x18000e4a8  lea     r8, WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids
0x18000e4af  mov     rcx, [rcx+10h]
0x18000e4b3  call    WPP_SF_d
0x18000e4b8  xorps   xmm0, xmm0
  ... truncated ...
```
