# A2DP_Device::PostDeviceStart(void)

- ea: `0x1400320a8`
- end: `0x14003255b`
- name: `?PostDeviceStart@A2DP_Device@@QEAAJXZ`
- size: `1203`
- prototype: `__int64 __fastcall(A2DP_Device *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14003be00`

## callees

- `0x140003530`
- `0x140006410`
- `0x14000e690`
- `0x14001bbc4`
- `0x14001bd20`
- `0x14001de68`
- `0x14002d890`
- `0x14002d8e8`
- `0x14002ea7c`
- `0x1400320a8`
- `0x14003374c`
- `0x140079ecc`
- `0x14007d440`
- `0x14007dd00`

## string_xrefs

- `0x140032185`: `Sideband Device already instantiated in post-device-start.`

## pseudocode

```c
__int64 __fastcall A2DP_Device::PostDeviceStart(A2DP_Device *this)
{
  char v2; // bl
  bool v3; // dl
  __int64 v4; // rcx
  bool v5; // r14
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  A2dpSidebandAudioWdmDevice **v10; // rsi
  __int64 v11; // rax
  int v12; // edx
  int v13; // r8d
  PDEVICE_OBJECT v14; // rcx
  int v15; // eax
  int v16; // edx
  int v17; // r8d
  unsigned int v18; // edi
  int IsEnabledDeviceUsageNoInline; // eax
  A2dpSidebandAudioWdmDevice **v21; // rsi
  __int64 v22; // rcx
  __int64 v23; // rax
  int v24; // edx
  int v25; // esi
  int v26; // r8d
  PDEVICE_OBJECT v27; // r10
  __int64 v28; // rax
  __int16 v29; // [rsp+30h] [rbp-30h]
  __int16 v30; // [rsp+30h] [rbp-30h]
  char v31; // [rsp+40h] [rbp-20h]
  _BYTE v32[8]; // [rsp+50h] [rbp-10h] BYREF
  utl::_RefCountBase *v33; // [rsp+58h] [rbp-8h]
  A2DP_Device *v34; // [rsp+90h] [rbp+30h] BYREF

  v2 = 1;
  v3 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      32,
      (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids,
      (char)this);
  A2DP_Device::SleepstudyRegister(this);
  LOBYTE(v4) = *(_BYTE *)(*((_QWORD *)this + 1) + 89LL);
  if ( (_BYTE)v4 || !*((_BYTE *)this + 3468) )
  {
    v5 = 0;
    if ( (_BYTE)v4 )
      goto LABEL_14;
  }
  else
  {
    v5 = 1;
  }
  A2DP_Device::StartServiceReadyTimer(this);
LABEL_14:
  if ( !(unsigned int)Feature_60759990__private_IsEnabledDeviceUsageNoInline(v4) )
  {
    IsEnabledDeviceUsageNoInline = Feature_55795972__private_IsEnabledDeviceUsageNoInline(v7, v6, v8, v9);
    v21 = (A2dpSidebandAudioWdmDevice **)((char *)this + 3472);
    v22 = *((_QWORD *)this + 434);
    if ( IsEnabledDeviceUsageNoInline )
    {
      if ( v22 )
      {
        A2dpSidebandAudioWdmDevice::Enable((A2dpSidebandAudioWdmDevice *)(v22 + 456));
LABEL_62:
        A2dpRole::CreateAudioDevice(*((A2dpRole **)this + 1), (const struct _GUID *)((char *)this + 936), v5);
        return 0;
      }
      v34 = this;
      v23 = utl::make_shared<A2dpSidebandAudioWdmDevice,A2DP_Device *>(v32, &v34);
      utl::shared_ptr<A2dpAudioCodec>::operator=((char *)this + 3472, v23);
      if ( v33 )
        utl::_RefCountBase::_DecStrong(v33);
      if ( !*v21 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          v2 = 0;
        }
        LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( !v2 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return 3221225626LL;
        v29 = 35;
        goto LABEL_74;
      }
      *((_BYTE *)this + 3488) = 1;
      _mm_mfence();
      v25 = A2dpSidebandAudioWdmDevice::RegisterInterface(*v21, *(PDEVICE_OBJECT *)(*((_QWORD *)this + 46) + 32LL));
      if ( v25 >= 0 )
        goto LABEL_62;
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        v2 = 0;
      }
      LOBYTE(v26) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v2 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return (unsigned int)v25;
      v31 = v25;
      v30 = 36;
LABEL_57:
      LOBYTE(v24) = v2;
      WPP_RECORDER_AND_TRACE_SF_d(
        v27->AttachedDevice,
        v24,
        v26,
        v27->DeviceExtension,
        2,
        18,
        v30,
        (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids,
        v31);
      return (unsigned int)v25;
    }
    if ( v22 )
    {
      A2dpSidebandAudioWdmDevice::Enable((A2dpSidebandAudioWdmDevice *)(v22 + 456));
    }
    else
    {
      v34 = this;
      v28 = utl::make_shared<A2dpSidebandAudioWdmDevice,A2DP_Device *>(v32, &v34);
      utl::shared_ptr<A2dpAudioCodec>::operator=((char *)this + 3472, v28);
      if ( v33 )
        utl::_RefCountBase::_DecStrong(v33);
      if ( !*v21 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          v2 = 0;
        }
        LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( !v2 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return 3221225626LL;
        v29 = 37;
        goto LABEL_74;
      }
      v25 = A2dpSidebandAudioWdmDevice::RegisterInterface(*v21, *(PDEVICE_OBJECT *)(*((_QWORD *)this + 46) + 32LL));
      if ( v25 < 0 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          v2 = 0;
        }
        LOBYTE(v26) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( !v2 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return (unsigned int)v25;
        v31 = v25;
        v30 = 38;
        goto LABEL_57;
      }
    }
    *((_BYTE *)this + 3488) = 1;
    _mm_mfence();
    goto LABEL_62;
  }
  v10 = (A2dpSidebandAudioWdmDevice **)((char *)this + 3472);
  if ( *((_QWORD *)this + 434) )
    MicrosoftTelemetryAssertTriggeredMsgKM("Sideband Device already instantiated in post-device-start.");
  v34 = this;
  v11 = utl::make_shared<A2dpSidebandAudioWdmDevice,A2DP_Device *>(v32, &v34);
  utl::shared_ptr<A2dpAudioCodec>::operator=((char *)this + 3472, v11);
  if ( v33 )
    utl::_RefCountBase::_DecStrong(v33);
  if ( !*v10 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v2 = 0;
    }
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v2 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return 3221225626LL;
    v29 = 33;
LABEL_74:
    LOBYTE(v12) = v2;
    WPP_RECORDER_AND_TRACE_SF_d(
      v14->AttachedDevice,
      v12,
      v13,
      v14->DeviceExtension,
      2,
      18,
      v29,
      (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids,
      154);
    return 3221225626LL;
  }
  A2dpRole::CreateAudioDevice(*((A2dpRole **)this + 1), (const struct _GUID *)((char *)this + 936), v5);
  *((_BYTE *)this + 3488) = 1;
  _mm_mfence();
  v15 = A2dpSidebandAudioWdmDevice::RegisterInterface(*v10, *(PDEVICE_OBJECT *)(*((_QWORD *)this + 46) + 32LL));
  v18 = v15;
  if ( v15 >= 0 )
    return 0;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
  {
    v2 = 0;
  }
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v16) = v2;
    LOBYTE(v17) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v16,
      v17,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      18,
      34,
      (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids,
      v15);
  }
  return v18;
}

```

## disassembly

```asm
0x1400320a8  mov     [rsp-28h+arg_8], rbx
0x1400320ad  mov     [rsp-28h+arg_10], rsi
0x1400320b2  push    rbp
0x1400320b3  push    rdi
0x1400320b4  push    r12
0x1400320b6  push    r13
0x1400320b8  push    r14
0x1400320ba  mov     rbp, rsp
0x1400320bd  sub     rsp, 60h
0x1400320c1  mov     rdi, rcx
0x1400320c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400320cb  lea     r12, WPP_GLOBAL_Control
0x1400320d2  mov     bl, 1
0x1400320d4  cmp     rcx, r12
0x1400320d7  jz      short loc_1400320EA
0x1400320d9  mov     eax, [rcx+2Ch]
0x1400320dc  test    al, 10h
0x1400320de  jz      short loc_1400320EA
0x1400320e0  cmp     byte ptr [rcx+29h], 4
0x1400320e4  jb      short loc_1400320EA
0x1400320e6  mov     dl, bl
0x1400320e8  jmp     short loc_1400320EC
0x1400320ea  xor     dl, dl
0x1400320ec  lea     r13, WPP_RECORDER_INITIALIZED
0x1400320f3  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400320fa  lea     r9, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x140032101  setnz   r8b
0x140032105  test    dl, dl
0x140032107  jnz     short loc_14003210E
0x140032109  test    r8b, r8b
0x14003210c  jz      short loc_140032139
0x14003210e  mov     qword ptr [rsp+60h+var_20], rdi
0x140032113  mov     [rsp+60h+var_28], r9
0x140032118  mov     r9, [rcx+40h]
0x14003211c  mov     rcx, [rcx+18h]
0x140032120  mov     [rsp+60h+var_30], 20h ; ' '
0x140032127  mov     [rsp+60h+var_38], 5
0x14003212f  mov     [rsp+60h+var_40], 4
0x140032134  call    WPP_RECORDER_AND_TRACE_SF_q
0x140032139  mov     rcx, rdi; this
0x14003213c  call    ?SleepstudyRegister@A2DP_Device@@AEAAJXZ; A2DP_Device::SleepstudyRegister(void)
0x140032141  mov     rax, [rdi+8]
0x140032145  mov     cl, [rax+59h]
0x140032148  mov     al, [rdi+0D8Ch]
0x14003214e  nop
0x14003214f  test    cl, cl
0x140032151  jnz     short loc_14003215C
0x140032153  test    al, al
0x140032155  jz      short loc_14003215C
0x140032157  mov     r14b, bl
0x14003215a  jmp     short loc_140032163
0x14003215c  xor     r14b, r14b
0x14003215f  test    cl, cl
0x140032161  jnz     short loc_14003216B
0x140032163  mov     rcx, rdi; this
0x140032166  call    ?StartServiceReadyTimer@A2DP_Device@@AEAAXXZ; A2DP_Device::StartServiceReadyTimer(void)
0x14003216b  call    Feature_60759990__private_IsEnabledDeviceUsageNoInline
0x140032170  test    eax, eax
0x140032172  jz      loc_1400322BD
0x140032178  lea     rsi, [rdi+0D90h]
0x14003217f  cmp     qword ptr [rsi], 0
0x140032183  jz      short loc_140032191
0x140032185  lea     rcx, aSidebandDevice; "Sideband Device already instantiated in"...
0x14003218c  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140032191  lea     rdx, [rbp+arg_0]
0x140032195  mov     [rbp+arg_0], rdi
0x140032199  lea     rcx, [rbp+var_10]
0x14003219d  call    ??$make_shared@VA2dpSidebandAudioWdmDevice@@PEAVA2DP_Device@@@utl@@YA?AV?$shared_ptr@VA2dpSidebandAudioWdmDevice@@@0@$$QEAPEAVA2DP_Device@@@Z; utl::make_shared<A2dpSidebandAudioWdmDevice,A2DP_Device *>(A2DP_Device * &&)
0x1400321a2  mov     rdx, rax
0x1400321a5  mov     rcx, rsi
0x1400321a8  call    ??4?$shared_ptr@VA2dpAudioCodec@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::shared_ptr<A2dpAudioCodec>::operator=(utl::shared_ptr<A2dpAudioCodec> &&)
0x1400321ad  mov     rcx, [rbp+var_8]; this
0x1400321b1  test    rcx, rcx
0x1400321b4  jz      short loc_1400321BB
0x1400321b6  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400321bb  cmp     qword ptr [rsi], 0
0x1400321bf  jnz     short loc_140032216
0x1400321c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400321c8  cmp     rcx, r12
0x1400321cb  jz      short loc_1400321DC
0x1400321cd  test    dword ptr [rcx+2Ch], 20000h
0x1400321d4  jz      short loc_1400321DC
0x1400321d6  cmp     byte ptr [rcx+29h], 2
0x1400321da  jnb     short loc_1400321DE
0x1400321dc  xor     bl, bl
0x1400321de  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400321e5  setnz   r8b
0x1400321e9  test    bl, bl
0x1400321eb  jnz     short loc_1400321F6
0x1400321ed  test    r8b, r8b
0x1400321f0  jz      loc_1400324E4
0x1400321f6  mov     dword ptr [rsp+60h+var_20], 0C000009Ah
0x1400321fe  lea     r9, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x140032205  mov     [rsp+60h+var_28], r9
0x14003220a  mov     [rsp+60h+var_30], 21h ; '!'
0x140032211  jmp     loc_1400324C8
0x140032216  mov     rcx, [rdi+8]; this
0x14003221a  lea     rdx, [rdi+3A8h]; struct _GUID *
0x140032221  mov     r8b, r14b; bool
0x140032224  call    ?CreateAudioDevice@A2dpRole@@QEAAJAEBU_GUID@@_N@Z; A2dpRole::CreateAudioDevice(_GUID const &,bool)
0x140032229  nop
0x14003222a  mov     [rdi+0DA0h], bl
0x140032230  mfence
0x140032233  mov     rdx, [rdi+170h]
0x14003223a  mov     rcx, [rsi]; this
0x14003223d  mov     rdx, [rdx+20h]; PhysicalDeviceObject
0x140032241  call    ?RegisterInterface@A2dpSidebandAudioWdmDevice@@UEAAJPEAU_DEVICE_OBJECT@@@Z; A2dpSidebandAudioWdmDevice::RegisterInterface(_DEVICE_OBJECT *)
0x140032246  mov     edi, eax
0x140032248  test    eax, eax
0x14003224a  jns     loc_14003242E
0x140032250  mov     r10, cs:WPP_GLOBAL_Control
0x140032257  cmp     r10, r12
0x14003225a  jz      short loc_14003226D
0x14003225c  test    dword ptr [r10+2Ch], 20000h
0x140032264  jz      short loc_14003226D
0x140032266  cmp     byte ptr [r10+29h], 2
0x14003226b  jnb     short loc_14003226F
0x14003226d  xor     bl, bl
0x14003226f  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140032276  setnz   r8b
0x14003227a  test    bl, bl
0x14003227c  jnz     short loc_140032283
0x14003227e  test    r8b, r8b
0x140032281  jz      short loc_1400322B6
0x140032283  mov     rcx, [r10+18h]
0x140032287  lea     r9, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x14003228e  mov     dword ptr [rsp+60h+var_20], edi
0x140032292  mov     dl, bl
0x140032294  mov     [rsp+60h+var_28], r9
0x140032299  mov     r9, [r10+40h]
0x14003229d  mov     [rsp+60h+var_30], 22h ; '"'
0x1400322a4  mov     [rsp+60h+var_38], 12h
0x1400322ac  mov     [rsp+60h+var_40], 2
0x1400322b1  call    WPP_RECORDER_AND_TRACE_SF_d
0x1400322b6  mov     eax, edi
0x1400322b8  jmp     loc_140032430
0x1400322bd  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x1400322c2  lea     rsi, [rdi+0D90h]
0x1400322c9  mov     rcx, [rsi]
0x1400322cc  test    eax, eax
0x1400322ce  jz      loc_140032400
0x1400322d4  test    rcx, rcx
0x1400322d7  jz      short loc_1400322EA
0x1400322d9  add     rcx, 1C8h; this
0x1400322e0  call    ?Enable@A2dpSidebandAudioWdmDevice@@UEAAXXZ; A2dpSidebandAudioWdmDevice::Enable(void)
0x1400322e5  jmp     loc_14003241B
0x1400322ea  lea     rdx, [rbp+arg_0]
0x1400322ee  mov     [rbp+arg_0], rdi
0x1400322f2  lea     rcx, [rbp+var_10]
0x1400322f6  call    ??$make_shared@VA2dpSidebandAudioWdmDevice@@PEAVA2DP_Device@@@utl@@YA?AV?$shared_ptr@VA2dpSidebandAudioWdmDevice@@@0@$$QEAPEAVA2DP_Device@@@Z; utl::make_shared<A2dpSidebandAudioWdmDevice,A2DP_Device *>(A2DP_Device * &&)
0x1400322fb  mov     rdx, rax
0x1400322fe  mov     rcx, rsi
0x140032301  call    ??4?$shared_ptr@VA2dpAudioCodec@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::shared_ptr<A2dpAudioCodec>::operator=(utl::shared_ptr<A2dpAudioCodec> &&)
0x140032306  mov     rcx, [rbp+var_8]; this
0x14003230a  test    rcx, rcx
0x14003230d  jz      short loc_140032314
0x14003230f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140032314  cmp     qword ptr [rsi], 0
0x140032318  jnz     short loc_14003236F
0x14003231a  mov     rcx, cs:WPP_GLOBAL_Control
0x140032321  cmp     rcx, r12
0x140032324  jz      short loc_140032335
0x140032326  test    dword ptr [rcx+2Ch], 20000h
0x14003232d  jz      short loc_140032335
0x14003232f  cmp     byte ptr [rcx+29h], 2
0x140032333  jnb     short loc_140032337
0x140032335  xor     bl, bl
0x140032337  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14003233e  setnz   r8b
0x140032342  test    bl, bl
0x140032344  jnz     short loc_14003234F
0x140032346  test    r8b, r8b
0x140032349  jz      loc_1400324E4
0x14003234f  mov     dword ptr [rsp+60h+var_20], 0C000009Ah
0x140032357  lea     r9, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x14003235e  mov     [rsp+60h+var_28], r9
0x140032363  mov     [rsp+60h+var_30], 23h ; '#'
0x14003236a  jmp     loc_1400324C8
0x14003236f  nop
0x140032370  mov     [rdi+0DA0h], bl
0x140032376  mfence
0x140032379  mov     rdx, [rdi+170h]
0x140032380  mov     rcx, [rsi]; this
0x140032383  mov     rdx, [rdx+20h]; PhysicalDeviceObject
0x140032387  call    ?RegisterInterface@A2dpSidebandAudioWdmDevice@@UEAAJPEAU_DEVICE_OBJECT@@@Z; A2dpSidebandAudioWdmDevice::RegisterInterface(_DEVICE_OBJECT *)
0x14003238c  mov     esi, eax
0x14003238e  test    eax, eax
0x140032390  jns     loc_14003241B
0x140032396  mov     r10, cs:WPP_GLOBAL_Control
0x14003239d  cmp     r10, r12
0x1400323a0  jz      short loc_1400323B3
0x1400323a2  test    dword ptr [r10+2Ch], 20000h
0x1400323aa  jz      short loc_1400323B3
0x1400323ac  cmp     byte ptr [r10+29h], 2
0x1400323b1  jnb     short loc_1400323B5
0x1400323b3  xor     bl, bl
0x1400323b5  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400323bc  setnz   r8b
0x1400323c0  test    bl, bl
0x1400323c2  jnz     short loc_1400323C9
0x1400323c4  test    r8b, r8b
0x1400323c7  jz      short loc_1400323FC
0x1400323c9  mov     dword ptr [rsp+60h+var_20], esi
0x1400323cd  lea     r9, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x1400323d4  mov     [rsp+60h+var_28], r9
0x1400323d9  mov     [rsp+60h+var_30], 24h ; '$'
0x1400323e0  mov     r9, [r10+40h]
0x1400323e4  mov     dl, bl
0x1400323e6  mov     rcx, [r10+18h]
0x1400323ea  mov     [rsp+60h+var_38], 12h
0x1400323f2  mov     [rsp+60h+var_40], 2
0x1400323f7  call    WPP_RECORDER_AND_TRACE_SF_d
0x1400323fc  mov     eax, esi
0x1400323fe  jmp     short loc_140032430
0x140032400  test    rcx, rcx
0x140032403  jz      short loc_14003244A
0x140032405  add     rcx, 1C8h; this
0x14003240c  call    ?Enable@A2dpSidebandAudioWdmDevice@@UEAAXXZ; A2dpSidebandAudioWdmDevice::Enable(void)
0x140032411  nop
0x140032412  mov     [rdi+0DA0h], bl
0x140032418  mfence
0x14003241b  mov     rcx, [rdi+8]; this
0x14003241f  lea     rdx, [rdi+3A8h]; struct _GUID *
0x140032426  mov     r8b, r14b; bool
0x140032429  call    ?CreateAudioDevice@A2dpRole@@QEAAJAEBU_GUID@@_N@Z; A2dpRole::CreateAudioDevice(_GUID const &,bool)
0x14003242e  xor     eax, eax
0x140032430  lea     r11, [rsp+60h+var_s0]
0x140032435  mov     rbx, [r11+38h]
0x140032439  mov     rsi, [r11+40h]
0x14003243d  mov     rsp, r11
0x140032440  pop     r14
0x140032442  pop     r13
0x140032444  pop     r12
0x140032446  pop     rdi
0x140032447  pop     rbp
0x140032448  retn
0x14003244a  lea     rdx, [rbp+arg_0]
0x14003244e  mov     [rbp+arg_0], rdi
0x140032452  lea     rcx, [rbp+var_10]
0x140032456  call    ??$make_shared@VA2dpSidebandAudioWdmDevice@@PEAVA2DP_Device@@@utl@@YA?AV?$shared_ptr@VA2dpSidebandAudioWdmDevice@@@0@$$QEAPEAVA2DP_Device@@@Z; utl::make_shared<A2dpSidebandAudioWdmDevice,A2DP_Device *>(A2DP_Device * &&)
0x14003245b  mov     rdx, rax
0x14003245e  mov     rcx, rsi
0x140032461  call    ??4?$shared_ptr@VA2dpAudioCodec@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::shared_ptr<A2dpAudioCodec>::operator=(utl::shared_ptr<A2dpAudioCodec> &&)
0x140032466  mov     rcx, [rbp+var_8]; this
0x14003246a  test    rcx, rcx
0x14003246d  jz      short loc_140032474
0x14003246f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140032474  mov     rcx, [rsi]; this
0x140032477  test    rcx, rcx
0x14003247a  jnz     short loc_1400324EE
0x14003247c  mov     rcx, cs:WPP_GLOBAL_Control
0x140032483  cmp     rcx, r12
0x140032486  jz      short loc_140032497
0x140032488  test    dword ptr [rcx+2Ch], 20000h
0x14003248f  jz      short loc_140032497
0x140032491  cmp     byte ptr [rcx+29h], 2
0x140032495  jnb     short loc_140032499
0x140032497  xor     bl, bl
0x140032499  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400324a0  setnz   r8b
0x1400324a4  test    bl, bl
0x1400324a6  jnz     short loc_1400324AD
0x1400324a8  test    r8b, r8b
0x1400324ab  jz      short loc_1400324E4
0x1400324ad  mov     dword ptr [rsp+60h+var_20], 0C000009Ah
0x1400324b5  lea     r9, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x1400324bc  mov     [rsp+60h+var_28], r9
0x1400324c1  mov     [rsp+60h+var_30], 25h ; '%'
0x1400324c8  mov     r9, [rcx+40h]
0x1400324cc  mov     dl, bl
0x1400324ce  mov     rcx, [rcx+18h]
0x1400324d2  mov     [rsp+60h+var_38], 12h
0x1400324da  mov     [rsp+60h+var_40], 2
0x1400324df  call    WPP_RECORDER_AND_TRACE_SF_d
0x1400324e4  mov     eax, 0C000009Ah
0x1400324e9  jmp     loc_140032430
0x1400324ee  mov     rdx, [rdi+170h]
0x1400324f5  mov     rdx, [rdx+20h]; PhysicalDeviceObject
0x1400324f9  call    ?RegisterInterface@A2dpSidebandAudioWdmDevice@@UEAAJPEAU_DEVICE_OBJECT@@@Z; A2dpSidebandAudioWdmDevice::RegisterInterface(_DEVICE_OBJECT *)
0x1400324fe  mov     esi, eax
0x140032500  test    eax, eax
0x140032502  jns     loc_140032411
0x140032508  mov     r10, cs:WPP_GLOBAL_Control
0x14003250f  cmp     r10, r12
0x140032512  jz      short loc_140032525
0x140032514  test    dword ptr [r10+2Ch], 20000h
0x14003251c  jz      short loc_140032525
0x14003251e  cmp     byte ptr [r10+29h], 2
0x140032523  jnb     short loc_140032527
0x140032525  xor     bl, bl
0x140032527  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14003252e  setnz   r8b
0x140032532  test    bl, bl
0x140032534  jnz     short loc_14003253F
0x140032536  test    r8b, r8b
0x140032539  jz      loc_1400323FC
0x14003253f  mov     dword ptr [rsp+60h+var_20], esi
0x140032543  lea     r9, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x14003254a  mov     [rsp+60h+var_28], r9
0x14003254f  mov     [rsp+60h+var_30], 26h ; '&'
  ... truncated ...
```
