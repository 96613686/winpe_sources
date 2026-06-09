# CConnectJob::CheckAndUpdateCandidates(void)

- ea: `0x1400a3584`
- end: `0x1400a3c24`
- name: `?CheckAndUpdateCandidates@CConnectJob@@AEAAHXZ`
- size: `1696`
- prototype: `__int64 __fastcall(CConnectJob *__hidden this)`
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting, installer_update`

## callers

- `0x1400a2644`
- `0x1400ac598`

## callees

- `0x14000688c`
- `0x140017a90`
- `0x14001a630`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14002a34c`
- `0x14002bd34`
- `0x14002ed50`
- `0x14002ef48`
- `0x140050660`
- `0x140071720`
- `0x1400a3584`
- `0x1400b0128`
- `0x1400dfd40`

## pseudocode

```c
__int64 __fastcall CConnectJob::CheckAndUpdateCandidates(CConnectJob *this, __int64 a2, int a3)
{
  int v4; // edx
  int v5; // r8d
  unsigned int v6; // r12d
  __int64 v7; // rdx
  int v8; // r8d
  struct CPort *PortFromPortId; // rsi
  _BYTE *v10; // rax
  __int64 v11; // rax
  _QWORD *v12; // rcx
  char v13; // r15
  int v14; // eax
  int v15; // edi
  int v16; // eax
  CPropertyCache *PortPropertyCache; // rbp
  CConnectHelpers *v18; // rax
  struct CAdapterPropertyCache *v19; // rdx
  struct _ROAM_CONTROL_PARAMETERS *RoamControlParameters; // rax
  struct _ROAM_CONTROL_PARAMETERS *v21; // r13
  unsigned __int64 CurrentTime; // rax
  int v23; // r9d
  unsigned int v24; // edi
  struct DOT11_CONNECTION_INFO *CurrentConnectionInfo; // rax
  unsigned int v26; // r14d
  __int64 i; // r10
  unsigned int v28; // ebp
  __int64 j; // rcx
  __int64 v30; // r11
  __int64 v31; // rdx
  __int64 v32; // rax
  PDEVICE_OBJECT v33; // rcx
  int v34; // r9d
  char v35; // dl
  __int64 v37; // [rsp+38h] [rbp-50h]
  unsigned int v38; // [rsp+90h] [rbp+8h] BYREF
  unsigned __int8 *v39; // [rsp+98h] [rbp+10h] BYREF

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      a3,
      204,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  }
  v6 = CConnectJob::PickCandidates(this, (CConnectJob *)((char *)this + 976));
  if ( v6 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v6;
    LOBYTE(v4) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      v5,
      205,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v6);
    goto LABEL_89;
  }
  PortFromPortId = CAdapter::GetPortFromPortId(*((CAdapter **)this + 67), *((_WORD *)this + 26));
  v10 = (_BYTE *)*((_QWORD *)PortFromPortId + 9);
  if ( v10 )
    *v10 = 1;
  if ( !*((_DWORD *)this + 161) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        v8,
        206,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
        (char)this,
        *((_DWORD *)this + 4));
    }
    *((_DWORD *)this + 154) = 16777217;
    v11 = *((_QWORD *)PortFromPortId + 9);
    if ( v11 )
      *(_DWORD *)(v11 + 36) = 5;
    goto LABEL_89;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v7) = 5;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      v8,
      207,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      *((_DWORD *)this + 161));
  }
  v12 = (_QWORD *)((char *)this + 1984);
  if ( (*((_DWORD *)this + 158) & 0x10) == 0 || (v13 = 1, *v12) )
    v13 = 0;
  v14 = *((_DWORD *)this + 493);
  if ( v14 )
  {
    if ( v14 > 2 )
    {
      v15 = 0;
      if ( v14 < 4 )
      {
        v16 = 0;
        if ( *v12 )
          v16 = 20;
        v15 = v16;
      }
    }
    else
    {
      v15 = 20;
    }
  }
  else
  {
    v15 = 0;
  }
  PortPropertyCache = COidJobBase::GetPortPropertyCache(this);
  v18 = (CConnectHelpers *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 67) + 8LL) + 8LL))(*((_QWORD *)this + 67) + 8LL);
  RoamControlParameters = CConnectHelpers::GetRoamControlParameters(v18, v19);
  v8 = *((_DWORD *)this + 493);
  v21 = RoamControlParameters;
  if ( v8 < 4 )
  {
    if ( (*((_DWORD *)this + 158) & 1) != 0 )
    {
      v39 = 0;
      v38 = 0;
      CurrentTime = CSystem::get_CurrentTime();
      if ( !*((_DWORD *)this + 140)
        && CurrentTime - *((_QWORD *)PortFromPortId + 4) < 0x989680
        && CPropertyCache::GetPropertyBooleanOrDefault(PortPropertyCache, 0x82u, 1) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v23 = 208;
LABEL_42:
          WPP_RECORDER_SF_qD(
            WPP_GLOBAL_Control->DeviceExtension,
            4,
            v8,
            v23,
            (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
            (char)this,
            *((_DWORD *)this + 4));
          goto LABEL_49;
        }
        goto LABEL_49;
      }
      if ( (unsigned int)CPropertyCache::GetPropertyBuffer(PortPropertyCache, 0x49u, &v38, &v39) == -1073741436 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v23 = 209;
          goto LABEL_42;
        }
LABEL_49:
        *((_DWORD *)this + 161) = 0;
      }
    }
    else if ( !v13 )
    {
      LODWORD(v7) = *(_DWORD *)(*((_QWORD *)this + 82) + 596LL);
      if ( (unsigned int)v7 < v15 + *(_DWORD *)RoamControlParameters )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          LOBYTE(v7) = 5;
          WPP_RECORDER_SF_qDddd(
            WPP_GLOBAL_Control->DeviceExtension,
            v7,
            v8,
            210,
            (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
            (char)this,
            *((_DWORD *)this + 4),
            v8,
            *(_DWORD *)(*((_QWORD *)this + 82) + 596LL),
            v15);
        }
        goto LABEL_49;
      }
    }
  }
  if ( !*((_DWORD *)this + 161) || (*((_DWORD *)this + 158) & 0x100) == 0 )
    goto LABEL_89;
  if ( !(*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)PortFromPortId + 59) + 24LL))(
          *((_QWORD *)PortFromPortId + 59),
          3) )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v6;
    v33 = WPP_GLOBAL_Control;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u && !LOWORD(WPP_GLOBAL_Control->DeviceType) )
      goto LABEL_89;
    v34 = 214;
    v35 = 5;
LABEL_84:
    WPP_RECORDER_SF_qD(
      v33->DeviceExtension,
      v35,
      v8,
      v34,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
    goto LABEL_89;
  }
  v24 = *((_DWORD *)this + 161);
  CurrentConnectionInfo = CPort::GetCurrentConnectionInfo(PortFromPortId, 1);
  if ( CurrentConnectionInfo )
  {
    v26 = *((_DWORD *)CurrentConnectionInfo + 26);
    for ( i = 0; (unsigned int)i < v26; i = (unsigned int)(i + 1) )
    {
      v8 = 6 * i;
      if ( !*((_DWORD *)CurrentConnectionInfo + 12 * i + 33) )
      {
        v28 = *((_DWORD *)this + 161);
        for ( j = 0; (unsigned int)j < v28; j = (unsigned int)(j + 1) )
        {
          v30 = *((_QWORD *)this + j + 82);
          LODWORD(v7) = *(_DWORD *)((char *)CurrentConnectionInfo + 48 * i + 123) - *(_DWORD *)(v30 + 32);
          if ( !(_DWORD)v7 )
            LODWORD(v7) = *(unsigned __int16 *)((char *)CurrentConnectionInfo + 48 * i + 127)
                        - *(unsigned __int16 *)(v30 + 36);
          if ( !(_DWORD)v7 )
            break;
        }
        if ( (unsigned int)j < v24 )
          v24 = j;
      }
    }
  }
  if ( !v24 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        v8,
        211,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
        (char)this,
        *((_DWORD *)this + 4));
    }
    *((_DWORD *)this + 161) = 0;
    v7 = *((_QWORD *)PortFromPortId + 9);
    if ( v7 )
    {
      *(_DWORD *)(v7 + 56) = *(_DWORD *)(*((_QWORD *)this + 82) + 756LL);
      *(_DWORD *)(*((_QWORD *)PortFromPortId + 9) + 36LL) = 1;
    }
    goto LABEL_89;
  }
  if ( !v13 )
  {
    if ( v24 < *((_DWORD *)this + 161) )
    {
      _mm_lfence();
      v31 = *((_QWORD *)PortFromPortId + 9);
      if ( v31 )
      {
        *(_DWORD *)(v31 + 56) = *(_DWORD *)(*((_QWORD *)this + v24 + 82) + 756LL);
        *(_DWORD *)(*((_QWORD *)PortFromPortId + 9) + 60LL) = *(_DWORD *)(*((_QWORD *)this + 82) + 752LL);
      }
      LODWORD(v7) = *(_DWORD *)(*((_QWORD *)this + v24 + 82) + 756LL);
      v8 = *(_DWORD *)(*((_QWORD *)this + 82) + 752LL);
      if ( v8 < (unsigned int)(v7 + *((_DWORD *)v21 + 3)) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          LOBYTE(v7) = 5;
          WPP_RECORDER_SF_qDdd(
            WPP_GLOBAL_Control->DeviceExtension,
            v7,
            v8,
            212,
            (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
            (char)this,
            *((_DWORD *)this + 4),
            *(_DWORD *)(*((_QWORD *)this + v24 + 82) + 756LL),
            v8);
        }
        *((_DWORD *)this + 161) = 0;
        v32 = *((_QWORD *)PortFromPortId + 9);
        if ( v32 )
          *(_DWORD *)(v32 + 36) = 2;
      }
      goto LABEL_89;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v6;
    v33 = WPP_GLOBAL_Control;
    v34 = 213;
    v35 = 2;
    goto LABEL_84;
  }
LABEL_89:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v7) = 5;
    LODWORD(v37) = v6;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      v8,
      215,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v37);
  }
  return v6;
}

```

## disassembly

```asm
0x1400a3584  mov     [rsp+arg_10], rbx
0x1400a3589  push    rbp
0x1400a358a  push    rsi
0x1400a358b  push    rdi
0x1400a358c  push    r12
0x1400a358e  push    r13
0x1400a3590  push    r14
0x1400a3592  push    r15
0x1400a3594  sub     rsp, 50h
0x1400a3598  mov     rbx, rcx
0x1400a359b  lea     rax, WPP_RECORDER_INITIALIZED
0x1400a35a2  xor     r14d, r14d
0x1400a35a5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400a35ac  lea     rdi, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a35b3  jz      short loc_1400A35EB
0x1400a35b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a35bc  cmp     byte ptr [rcx+29h], 5
0x1400a35c0  jnb     short loc_1400A35C9
0x1400a35c2  cmp     [rcx+48h], r14w
0x1400a35c7  jz      short loc_1400A35EB
0x1400a35c9  mov     eax, [rbx+10h]
0x1400a35cc  mov     r9d, 0CCh
0x1400a35d2  mov     rcx, [rcx+40h]
0x1400a35d6  mov     dl, 5
0x1400a35d8  mov     [rsp+88h+var_58], eax
0x1400a35dc  mov     [rsp+88h+var_60], rbx
0x1400a35e1  mov     [rsp+88h+var_68], rdi
0x1400a35e6  call    WPP_RECORDER_SF_qD
0x1400a35eb  lea     rdx, [rbx+3D0h]; struct _WFC_CONNECTION_PROFILE_PARAMETERS *
0x1400a35f2  mov     rcx, rbx; this
0x1400a35f5  call    ?PickCandidates@CConnectJob@@AEAAHPEAU_WFC_CONNECTION_PROFILE_PARAMETERS@@@Z; CConnectJob::PickCandidates(_WFC_CONNECTION_PROFILE_PARAMETERS *)
0x1400a35fa  mov     r12d, eax
0x1400a35fd  test    eax, eax
0x1400a35ff  jz      short loc_1400A3648
0x1400a3601  lea     rax, WPP_RECORDER_INITIALIZED
0x1400a3608  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400a360f  jz      loc_1400A3C08
0x1400a3615  mov     ecx, [rbx+10h]
0x1400a3618  mov     r9d, 0CDh
0x1400a361e  mov     dword ptr [rsp+88h+var_50], r12d
0x1400a3623  mov     dl, 2
0x1400a3625  mov     [rsp+88h+var_58], ecx
0x1400a3629  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a3630  mov     [rsp+88h+var_60], rbx
0x1400a3635  mov     [rsp+88h+var_68], rdi
0x1400a363a  mov     rcx, [rcx+40h]
0x1400a363e  call    WPP_RECORDER_SF_qDD
0x1400a3643  jmp     loc_1400A3BBD
0x1400a3648  movzx   edx, word ptr [rbx+34h]; unsigned __int16
0x1400a364c  mov     rcx, [rbx+218h]; this
0x1400a3653  call    ?GetPortFromPortId@CAdapter@@QEAAPEAVCPort@@G@Z; CAdapter::GetPortFromPortId(ushort)
0x1400a3658  mov     rsi, rax
0x1400a365b  mov     rax, [rax+48h]
0x1400a365f  test    rax, rax
0x1400a3662  jz      short loc_1400A3667
0x1400a3664  mov     byte ptr [rax], 1
0x1400a3667  mov     eax, [rbx+284h]
0x1400a366d  test    eax, eax
0x1400a366f  jnz     short loc_1400A36DA
0x1400a3671  lea     rax, WPP_RECORDER_INITIALIZED
0x1400a3678  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400a367f  jz      short loc_1400A36B7
0x1400a3681  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a3688  cmp     byte ptr [rcx+29h], 5
0x1400a368c  jnb     short loc_1400A3695
0x1400a368e  cmp     [rcx+48h], r14w
0x1400a3693  jz      short loc_1400A36B7
0x1400a3695  mov     eax, [rbx+10h]
0x1400a3698  mov     r9d, 0CEh
0x1400a369e  mov     rcx, [rcx+40h]
0x1400a36a2  mov     dl, 5
0x1400a36a4  mov     [rsp+88h+var_58], eax
0x1400a36a8  mov     [rsp+88h+var_60], rbx
0x1400a36ad  mov     [rsp+88h+var_68], rdi
0x1400a36b2  call    WPP_RECORDER_SF_qD
0x1400a36b7  mov     dword ptr [rbx+268h], 1000001h
0x1400a36c1  mov     rax, [rsi+48h]
0x1400a36c5  test    rax, rax
0x1400a36c8  jz      loc_1400A3BBD
0x1400a36ce  mov     dword ptr [rax+24h], 5
0x1400a36d5  jmp     loc_1400A3BBD
0x1400a36da  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400a36e1  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400a36e8  jz      short loc_1400A3724
0x1400a36ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a36f1  cmp     byte ptr [rcx+29h], 5
0x1400a36f5  jnb     short loc_1400A36FE
0x1400a36f7  cmp     [rcx+48h], r14w
0x1400a36fc  jz      short loc_1400A3724
0x1400a36fe  mov     rcx, [rcx+40h]
0x1400a3702  mov     r9d, 0CFh
0x1400a3708  mov     dword ptr [rsp+88h+var_50], eax
0x1400a370c  mov     dl, 5
0x1400a370e  mov     eax, [rbx+10h]
0x1400a3711  mov     [rsp+88h+var_58], eax
0x1400a3715  mov     [rsp+88h+var_60], rbx
0x1400a371a  mov     [rsp+88h+var_68], rdi
0x1400a371f  call    WPP_RECORDER_SF_qDD
0x1400a3724  mov     eax, [rbx+278h]
0x1400a372a  lea     rcx, [rbx+7C0h]
0x1400a3731  test    al, 10h
0x1400a3733  jz      short loc_1400A373D
0x1400a3735  mov     r15b, 1
0x1400a3738  cmp     [rcx], r14
0x1400a373b  jz      short loc_1400A3740
0x1400a373d  mov     r15b, r14b
0x1400a3740  mov     eax, [rbx+7B4h]
0x1400a3746  test    eax, eax
0x1400a3748  jnz     short loc_1400A374F
0x1400a374a  mov     edi, r14d
0x1400a374d  jmp     short loc_1400A3773
0x1400a374f  cmp     eax, 2
0x1400a3752  jg      short loc_1400A375B
0x1400a3754  mov     edi, 14h
0x1400a3759  jmp     short loc_1400A3773
0x1400a375b  mov     edi, r14d
0x1400a375e  cmp     eax, 4
0x1400a3761  jge     short loc_1400A3773
0x1400a3763  cmp     [rcx], r14
0x1400a3766  mov     edi, 14h
0x1400a376b  mov     eax, r14d
0x1400a376e  cmovnz  eax, edi
0x1400a3771  mov     edi, eax
0x1400a3773  mov     rcx, rbx; this
0x1400a3776  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x1400a377b  mov     rcx, [rbx+218h]
0x1400a3782  mov     rbp, rax
0x1400a3785  add     rcx, 8
0x1400a3789  mov     rdx, [rcx]
0x1400a378c  mov     rax, [rdx+8]
0x1400a3790  call    _guard_dispatch_icall
0x1400a3795  mov     rcx, rax; this
0x1400a3798  call    ?GetRoamControlParameters@CConnectHelpers@@YAPEAU_ROAM_CONTROL_PARAMETERS@@PEAVCAdapterPropertyCache@@@Z; CConnectHelpers::GetRoamControlParameters(CAdapterPropertyCache *)
0x1400a379d  mov     r8d, [rbx+7B4h]
0x1400a37a4  mov     r13, rax
0x1400a37a7  cmp     r8d, 4
0x1400a37ab  jge     loc_1400A3905
0x1400a37b1  mov     ecx, [rbx+278h]
0x1400a37b7  test    cl, 1
0x1400a37ba  jz      loc_1400A3888
0x1400a37c0  mov     [rsp+88h+arg_8], r14
0x1400a37c8  mov     [rsp+88h+arg_0], r14d
0x1400a37d0  call    ?get_CurrentTime@CSystem@@SA_KXZ; CSystem::get_CurrentTime(void)
0x1400a37d5  cmp     [rbx+230h], r14d
0x1400a37dc  jnz     short loc_1400A381A
0x1400a37de  sub     rax, [rsi+20h]
0x1400a37e2  cmp     rax, 989680h
0x1400a37e8  jnb     short loc_1400A381A
0x1400a37ea  mov     r8b, 1; unsigned __int8
0x1400a37ed  mov     edx, 82h; unsigned int
0x1400a37f2  mov     rcx, rbp; this
0x1400a37f5  call    ?GetPropertyBooleanOrDefault@CPropertyCache@@QEAAEKE@Z; CPropertyCache::GetPropertyBooleanOrDefault(ulong,uchar)
0x1400a37fa  test    al, al
0x1400a37fc  jz      short loc_1400A381A
0x1400a37fe  lea     rax, WPP_RECORDER_INITIALIZED
0x1400a3805  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400a380c  jz      loc_1400A38FE
0x1400a3812  mov     r9d, 0D0h
0x1400a3818  jmp     short loc_1400A385C
0x1400a381a  lea     r9, [rsp+88h+arg_8]; unsigned __int8 **
0x1400a3822  mov     edx, 49h ; 'I'; unsigned int
0x1400a3827  lea     r8, [rsp+88h+arg_0]; unsigned int *
0x1400a382f  mov     rcx, rbp; this
0x1400a3832  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z; CPropertyCache::GetPropertyBuffer(ulong,ulong *,uchar * *)
0x1400a3837  cmp     eax, 0C0000184h
0x1400a383c  jnz     loc_1400A3905
0x1400a3842  lea     rax, WPP_RECORDER_INITIALIZED
0x1400a3849  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400a3850  jz      loc_1400A38FE
0x1400a3856  mov     r9d, 0D1h
0x1400a385c  mov     eax, [rbx+10h]
0x1400a385f  mov     dl, 4
0x1400a3861  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a3868  mov     [rsp+88h+var_58], eax
0x1400a386c  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a3873  mov     [rsp+88h+var_60], rbx
0x1400a3878  mov     [rsp+88h+var_68], rax
0x1400a387d  mov     rcx, [rcx+40h]
0x1400a3881  call    WPP_RECORDER_SF_qD
0x1400a3886  jmp     short loc_1400A38FE
0x1400a3888  test    r15b, r15b
0x1400a388b  jnz     short loc_1400A3905
0x1400a388d  mov     rax, [rbx+290h]
0x1400a3894  mov     ecx, [r13+0]
0x1400a3898  add     ecx, edi
0x1400a389a  mov     edx, [rax+254h]
0x1400a38a0  cmp     edx, ecx
0x1400a38a2  jnb     short loc_1400A3905
0x1400a38a4  lea     rax, WPP_RECORDER_INITIALIZED
0x1400a38ab  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400a38b2  jz      short loc_1400A38FE
0x1400a38b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a38bb  cmp     byte ptr [rcx+29h], 5
0x1400a38bf  jnb     short loc_1400A38C8
0x1400a38c1  cmp     [rcx+48h], r14w
0x1400a38c6  jz      short loc_1400A38FE
0x1400a38c8  mov     eax, [rbx+10h]
0x1400a38cb  mov     r9d, 0D2h
0x1400a38d1  mov     rcx, [rcx+40h]
0x1400a38d5  mov     [rsp+88h+var_40], edi
0x1400a38d9  mov     [rsp+88h+var_48], edx
0x1400a38dd  mov     dl, 5
0x1400a38df  mov     dword ptr [rsp+88h+var_50], r8d
0x1400a38e4  mov     [rsp+88h+var_58], eax
0x1400a38e8  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a38ef  mov     [rsp+88h+var_60], rbx
0x1400a38f4  mov     [rsp+88h+var_68], rax
0x1400a38f9  call    WPP_RECORDER_SF_qDddd
0x1400a38fe  mov     [rbx+284h], r14d
0x1400a3905  cmp     [rbx+284h], r14d
0x1400a390c  jbe     loc_1400A3BB6
0x1400a3912  test    dword ptr [rbx+278h], 100h
0x1400a391c  jz      loc_1400A3BB6
0x1400a3922  mov     rcx, [rsi+1D8h]
0x1400a3929  mov     edx, 3
0x1400a392e  mov     rax, [rcx]
0x1400a3931  mov     rax, [rax+18h]
0x1400a3935  call    _guard_dispatch_icall
0x1400a393a  test    rax, rax
0x1400a393d  jz      loc_1400A3B88
0x1400a3943  mov     edi, [rbx+284h]
0x1400a3949  mov     dl, 1; bool
0x1400a394b  mov     rcx, rsi; this
0x1400a394e  call    ?GetCurrentConnectionInfo@CPort@@QEAAPEAUDOT11_CONNECTION_INFO@@_N@Z; CPort::GetCurrentConnectionInfo(bool)
0x1400a3953  mov     r9, rax
0x1400a3956  test    rax, rax
0x1400a3959  jz      short loc_1400A39BF
0x1400a395b  mov     r14d, [rax+68h]
0x1400a395f  xor     r10d, r10d
0x1400a3962  test    r14d, r14d
0x1400a3965  jz      short loc_1400A39BC
0x1400a3967  lea     r8, [r10+r10*2]
0x1400a396b  add     r8, r8
0x1400a396e  cmp     dword ptr [r9+r8*8+84h], 0
0x1400a3977  jnz     short loc_1400A39B4
0x1400a3979  mov     ebp, [rbx+284h]
0x1400a397f  xor     ecx, ecx
0x1400a3981  test    ebp, ebp
0x1400a3983  jz      short loc_1400A39AF
0x1400a3985  mov     r11, [rbx+rcx*8+290h]
0x1400a398d  mov     edx, [r9+r8*8+7Bh]
0x1400a3992  sub     edx, [r11+20h]
0x1400a3996  jnz     short loc_1400A39A5
0x1400a3998  movzx   edx, word ptr [r9+r8*8+7Fh]
0x1400a399e  movzx   eax, word ptr [r11+24h]
0x1400a39a3  sub     edx, eax
0x1400a39a5  test    edx, edx
0x1400a39a7  jz      short loc_1400A39AF
0x1400a39a9  inc     ecx
0x1400a39ab  cmp     ecx, ebp
0x1400a39ad  jb      short loc_1400A3985
0x1400a39af  cmp     ecx, edi
0x1400a39b1  cmovb   edi, ecx
0x1400a39b4  inc     r10d
0x1400a39b7  cmp     r10d, r14d
0x1400a39ba  jb      short loc_1400A3967
0x1400a39bc  xor     r14d, r14d
0x1400a39bf  test    edi, edi
0x1400a39c1  jnz     loc_1400A3A51
0x1400a39c7  lea     rax, WPP_RECORDER_INITIALIZED
0x1400a39ce  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400a39d5  jz      short loc_1400A3A16
0x1400a39d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a39de  cmp     byte ptr [rcx+29h], 5
0x1400a39e2  jnb     short loc_1400A39EB
0x1400a39e4  cmp     [rcx+48h], r14w
0x1400a39e9  jz      short loc_1400A3A16
0x1400a39eb  mov     eax, [rbx+10h]
0x1400a39ee  lea     rdi, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a39f5  mov     rcx, [rcx+40h]
0x1400a39f9  mov     r9d, 0D3h
0x1400a39ff  mov     [rsp+88h+var_58], eax
0x1400a3a03  mov     dl, 5
0x1400a3a05  mov     [rsp+88h+var_60], rbx
0x1400a3a0a  mov     [rsp+88h+var_68], rdi
0x1400a3a0f  call    WPP_RECORDER_SF_qD
0x1400a3a14  jmp     short loc_1400A3A1D
0x1400a3a16  lea     rdi, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a3a1d  mov     [rbx+284h], r14d
0x1400a3a24  mov     rdx, [rsi+48h]
0x1400a3a28  test    rdx, rdx
0x1400a3a2b  jz      loc_1400A3BBD
0x1400a3a31  mov     rax, [rbx+290h]
0x1400a3a38  mov     ecx, [rax+2F4h]
0x1400a3a3e  mov     [rdx+38h], ecx
0x1400a3a41  mov     rax, [rsi+48h]
0x1400a3a45  mov     dword ptr [rax+24h], 1
0x1400a3a4c  jmp     loc_1400A3BBD
0x1400a3a51  test    r15b, r15b
0x1400a3a54  jnz     loc_1400A3BB6
0x1400a3a5a  cmp     edi, [rbx+284h]
0x1400a3a60  jnb     loc_1400A3B42
0x1400a3a66  lfence
0x1400a3a69  mov     rdx, [rsi+48h]
0x1400a3a6d  test    rdx, rdx
0x1400a3a70  jz      short loc_1400A3A99
0x1400a3a72  mov     eax, edi
0x1400a3a74  mov     rcx, [rbx+rax*8+290h]
0x1400a3a7c  mov     eax, [rcx+2F4h]
0x1400a3a82  mov     [rdx+38h], eax
  ... truncated ...
```
