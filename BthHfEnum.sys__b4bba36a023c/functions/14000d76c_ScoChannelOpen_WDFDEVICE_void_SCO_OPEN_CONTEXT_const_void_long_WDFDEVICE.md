# ScoChannelOpen(WDFDEVICE__ *,void *,_SCO_OPEN_CONTEXT const *,void (*)(long,WDFDEVICE__ *))

- ea: `0x14000d76c`
- end: `0x14000dcea`
- name: `?ScoChannelOpen@@YAJPEAUWDFDEVICE__@@PEAXPEBU_SCO_OPEN_CONTEXT@@P6AXJ0@Z@Z`
- size: `1406`
- prototype: `__int64 __fastcall(struct WDFDEVICE__ *, void *, const struct _SCO_OPEN_CONTEXT *, struct WDFREQUEST__ *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000e180`

## callees

- `0x1400041d0`
- `0x140004810`
- `0x14000a05c`
- `0x14000affc`
- `0x14000c570`
- `0x14000d76c`
- `0x14000df64`
- `0x140010be8`
- `0x1400112c4`
- `0x140011484`
- `0x140015318`
- `0x1400154d8`
- `0x14001ae00`
- `0x14002ea78`

## pseudocode

```c
__int64 __fastcall ScoChannelOpen(
        struct WDFDEVICE__ *a1,
        void *a2,
        const struct _SCO_OPEN_CONTEXT *a3,
        struct WDFREQUEST__ *a4)
{
  const struct _SCO_OPEN_CONTEXT *v5; // rbp
  __int64 v7; // rdx
  _QWORD *v8; // rbx
  __int64 v9; // r8
  char v10; // si
  unsigned int *v11; // rax
  unsigned int v12; // r14d
  __int64 *v13; // rdx
  __int64 v15; // r9
  int v16; // edi
  struct _BRB *v17; // r14
  const struct _SCO_OPEN_CONTEXT *v18; // r9
  struct WDFREQUEST__ *v19; // rbp
  int v20; // eax
  __int64 v21; // r8
  int v22; // r8d
  __int64 *v23; // rdx
  int v24; // [rsp+20h] [rbp-68h]
  int v25; // [rsp+28h] [rbp-60h]
  int v26; // [rsp+30h] [rbp-58h]
  int v27; // [rsp+38h] [rbp-50h]
  const struct _SCO_OPEN_CONTEXT *v28; // [rsp+A0h] [rbp+18h] BYREF
  struct WDFREQUEST__ *v29; // [rsp+A8h] [rbp+20h] BYREF

  v29 = a4;
  v28 = a3;
  v5 = a3;
  v8 = (_QWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFDEVICE__ *, __int64 *))(WdfFunctions_01015
                                                                                                 + 1616))(
                   WdfDriverGlobals,
                   a1,
                   off_140022150);
  v10 = 1;
  LOBYTE(v7) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_qSCOSTATECODECID(
      WPP_GLOBAL_Control->AttachedDevice,
      v7,
      v9,
      WPP_GLOBAL_Control->DeviceExtension);
  }
  v29 = 0;
  v11 = (unsigned int *)v8 + 7;
  if ( a2 )
    v11 = (unsigned int *)(v8 + 4);
  v12 = *v11;
  if ( *((_DWORD *)v8 + 26) )
    goto LABEL_29;
  LOBYTE(v7) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
  LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v7,
      v9,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      5,
      47,
      (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids);
  if ( (unsigned int)NegotiateAndValidateCodec(a1, v7, v9) )
  {
LABEL_29:
    if ( v5 )
      v15 = *((unsigned int *)v5 + 1);
    else
      v15 = 3;
    LOBYTE(v7) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_qCODECIDCODECID(
        WPP_GLOBAL_Control->AttachedDevice,
        v7,
        v9,
        WPP_GLOBAL_Control->DeviceExtension,
        v24,
        v25,
        v26,
        v27,
        (char)v5,
        v15,
        *((_DWORD *)v8 + 26));
    if ( !v5 || *((_DWORD *)v5 + 1) != *((_DWORD *)v8 + 26) )
    {
      v16 = ScoSelectChannelConfigsFromCodecId(*((unsigned int *)v8 + 26), &v28, v9, v15);
      if ( v16 < 0 )
        return (unsigned int)v16;
      v5 = v28;
    }
    v16 = AudioQueue_SetCodecId((struct WDFQUEUE__ *)v8[20], *((_DWORD *)v8 + 26));
    if ( v16 >= 0 )
    {
      v16 = AudioQueue_SetCodecId((struct WDFQUEUE__ *)v8[30], *((_DWORD *)v8 + 26));
      if ( v16 >= 0 )
      {
        v17 = (struct _BRB *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(v8[1] + 32LL))(v12, *((unsigned int *)v8 + 6));
        if ( v17 )
        {
          v16 = WdfIoTargetCreateAndFormatRequestForBrb(0, *v8, v8[1], v17, &v29);
          if ( v16 < 0 )
          {
            v19 = v29;
          }
          else
          {
            v18 = v5;
            v19 = v29;
            v20 = ScoChannelOpenBrbBuild(v29, a1, a2, v18, v17);
            v17 = 0;
            v16 = v20;
            if ( v20 >= 0 )
            {
              SetScoState(v8, 4);
              (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFREQUEST__ *, void (*)(struct WDFREQUEST__ *, struct WDFIOTARGET__ *, struct _WDF_REQUEST_COMPLETION_PARAMS *, void *), struct WDFDEVICE__ *))(WdfFunctions_01015 + 2080))(
                WdfDriverGlobals,
                v19,
                ScoOpenCompletionRoutine,
                a1);
              wil::acquire_wdf_spin_lock(&v29, v8[46]);
              v8[58] = v19;
              (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFREQUEST__ *, _QWORD, __int64, const char *))(WdfFunctions_01015 + 1640))(
                WdfDriverGlobals,
                v19,
                0,
                1904,
                "onecoreuap\\drivers\\wdm\\audio\\drivers\\bluetooth\\bthhfenum\\bthscoserver.cpp");
              wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&void WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&void WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(&v29);
              (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64))(WdfFunctions_01015 + 2552))(
                WdfDriverGlobals,
                v8[60],
                -50000000);
              if ( (*(unsigned __int8 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFREQUEST__ *, _QWORD, _QWORD))(WdfFunctions_01015 + 2024))(
                     WdfDriverGlobals,
                     v19,
                     *v8,
                     0) )
              {
                v19 = 0;
                v16 = 0;
              }
              else
              {
                LOBYTE(v21) = 1;
                (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64))(WdfFunctions_01015 + 2560))(
                  WdfDriverGlobals,
                  v8[60],
                  v21);
                wil::acquire_wdf_spin_lock(&v29, v8[46]);
                (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, __int64, const char *))(WdfFunctions_01015 + 1648))(
                  WdfDriverGlobals,
                  v8[58],
                  0,
                  1914,
                  "onecoreuap\\drivers\\wdm\\audio\\drivers\\bluetooth\\bthhfenum\\bthscoserver.cpp");
                v8[58] = 0;
                wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&void WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&void WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(&v29);
                v16 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFREQUEST__ *))(WdfFunctions_01015 + 2032))(
                        WdfDriverGlobals,
                        v19);
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
                  v10 = 0;
                }
                if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  v23 = WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids;
                  LOBYTE(v23) = v10;
                  LOBYTE(v22) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                  WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP(
                    WPP_GLOBAL_Control->AttachedDevice,
                    (_DWORD)v23,
                    v22,
                    WPP_GLOBAL_Control->DeviceExtension,
                    2,
                    5,
                    50,
                    (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids,
                    v16);
                }
                SetScoState(v8, 0);
              }
            }
          }
          if ( v19 )
            (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFREQUEST__ *))(WdfFunctions_01015 + 1664))(
              WdfDriverGlobals,
              v19);
          if ( v17 )
            (*(void (__fastcall **)(struct _BRB *))(v8[1] + 40LL))(v17);
        }
        else
        {
          return (unsigned int)-1073741670;
        }
      }
    }
    return (unsigned int)v16;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
  {
    v10 = 0;
  }
  if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v13 = WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids;
    LOBYTE(v13) = v10;
    LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)v13,
      v9,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      5,
      48,
      (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids);
  }
  return 3221225860LL;
}

```

## disassembly

```asm
0x14000d76c  mov     rax, rsp
0x14000d76f  mov     [rax+8], rbx
0x14000d773  mov     [rax+10h], rbp
0x14000d777  mov     [rax+20h], r9
0x14000d77b  mov     [rax+18h], r8
0x14000d77f  push    rsi
0x14000d780  push    rdi
0x14000d781  push    r12
0x14000d783  push    r14
0x14000d785  push    r15
0x14000d787  sub     rsp, 60h
0x14000d78b  mov     rax, cs:WdfFunctions_01015
0x14000d792  mov     r15, rdx
0x14000d795  mov     rbp, r8
0x14000d798  mov     r12, rcx
0x14000d79b  mov     r8, cs:off_140022150
0x14000d7a2  mov     rdx, rcx
0x14000d7a5  mov     rcx, cs:WdfDriverGlobals
0x14000d7ac  mov     rax, [rax+650h]
0x14000d7b3  call    _guard_dispatch_icall
0x14000d7b8  mov     rbx, rax
0x14000d7bb  mov     r10, cs:WPP_GLOBAL_Control
0x14000d7c2  lea     r11, WPP_GLOBAL_Control
0x14000d7c9  mov     sil, 1
0x14000d7cc  mov     dil, 10h
0x14000d7cf  cmp     r10, r11
0x14000d7d2  jz      short loc_14000D7E9
0x14000d7d4  mov     ecx, [r10+2Ch]
0x14000d7d8  test    dil, cl
0x14000d7db  jz      short loc_14000D7E9
0x14000d7dd  cmp     byte ptr [r10+29h], 4
0x14000d7e2  jb      short loc_14000D7E9
0x14000d7e4  mov     dl, sil
0x14000d7e7  jmp     short loc_14000D7EB
0x14000d7e9  xor     dl, dl
0x14000d7eb  lea     r9, WPP_RECORDER_INITIALIZED
0x14000d7f2  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x14000d7f9  setnz   r8b
0x14000d7fd  test    dl, dl
0x14000d7ff  jnz     short loc_14000D806
0x14000d801  test    r8b, r8b
0x14000d804  jz      short loc_14000D837
0x14000d806  mov     eax, [rax+68h]
0x14000d809  mov     r9, [r10+40h]
0x14000d80d  mov     rcx, [r10+18h]
0x14000d811  mov     [rsp+88h+var_38], eax
0x14000d815  mov     eax, [rbx+178h]
0x14000d81b  mov     [rsp+88h+var_40], eax
0x14000d81f  mov     [rsp+88h+var_48], r15
0x14000d824  call    WPP_RECORDER_AND_TRACE_SF_qSCOSTATECODECID
0x14000d829  lea     r9, WPP_RECORDER_INITIALIZED
0x14000d830  lea     r11, WPP_GLOBAL_Control
0x14000d837  mov     [rsp+88h+arg_18], 0
0x14000d843  lea     rax, [rbx+1Ch]
0x14000d847  test    r15, r15
0x14000d84a  jz      short loc_14000D850
0x14000d84c  lea     rax, [rbx+20h]
0x14000d850  cmp     dword ptr [rbx+68h], 0
0x14000d854  lea     r10, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x14000d85b  mov     r14d, [rax]
0x14000d85e  jnz     loc_14000D945
0x14000d864  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d86b  cmp     rcx, r11
0x14000d86e  jz      short loc_14000D883
0x14000d870  mov     eax, [rcx+2Ch]
0x14000d873  test    dil, al
0x14000d876  jz      short loc_14000D883
0x14000d878  cmp     byte ptr [rcx+29h], 2
0x14000d87c  jb      short loc_14000D883
0x14000d87e  mov     dl, sil
0x14000d881  jmp     short loc_14000D885
0x14000d883  xor     dl, dl
0x14000d885  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x14000d88c  setnz   r8b
0x14000d890  test    dl, dl
0x14000d892  jnz     short loc_14000D899
0x14000d894  test    r8b, r8b
0x14000d897  jz      short loc_14000D8BF
0x14000d899  mov     r9, [rcx+40h]
0x14000d89d  mov     rcx, [rcx+18h]
0x14000d8a1  mov     [rsp+88h+var_50], r10
0x14000d8a6  mov     [rsp+88h+var_58], 2Fh ; '/'
0x14000d8ad  mov     [rsp+88h+var_60], 5
0x14000d8b5  mov     byte ptr [rsp+88h+var_68], 2
0x14000d8ba  call    WPP_RECORDER_AND_TRACE_SF_
0x14000d8bf  mov     rcx, r12
0x14000d8c2  call    NegotiateAndValidateCodec
0x14000d8c7  test    eax, eax
0x14000d8c9  jnz     short loc_14000D945
0x14000d8cb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d8d2  lea     rax, WPP_GLOBAL_Control
0x14000d8d9  cmp     rcx, rax
0x14000d8dc  jz      short loc_14000D8EC
0x14000d8de  mov     eax, [rcx+2Ch]
0x14000d8e1  test    dil, al
0x14000d8e4  jz      short loc_14000D8EC
0x14000d8e6  cmp     byte ptr [rcx+29h], 2
0x14000d8ea  jnb     short loc_14000D8EF
0x14000d8ec  xor     sil, sil
0x14000d8ef  lea     rax, WPP_RECORDER_INITIALIZED
0x14000d8f6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000d8fd  setnz   r8b
0x14000d901  test    sil, sil
0x14000d904  jnz     short loc_14000D90B
0x14000d906  test    r8b, r8b
0x14000d909  jz      short loc_14000D93B
0x14000d90b  mov     r9, [rcx+40h]
0x14000d90f  lea     rdx, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x14000d916  mov     rcx, [rcx+18h]
0x14000d91a  mov     [rsp+88h+var_50], rdx
0x14000d91f  mov     dl, sil
0x14000d922  mov     [rsp+88h+var_58], 30h ; '0'
0x14000d929  mov     [rsp+88h+var_60], 5
0x14000d931  mov     byte ptr [rsp+88h+var_68], 2
0x14000d936  call    WPP_RECORDER_AND_TRACE_SF_
0x14000d93b  mov     eax, 0C0000184h
0x14000d940  jmp     loc_14000DCD0
0x14000d945  test    rbp, rbp
0x14000d948  jz      short loc_14000D950
0x14000d94a  mov     r9d, [rbp+4]
0x14000d94e  jmp     short loc_14000D956
0x14000d950  mov     r9d, 3
0x14000d956  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d95d  lea     rax, WPP_GLOBAL_Control
0x14000d964  cmp     rcx, rax
0x14000d967  jz      short loc_14000D97C
0x14000d969  mov     eax, [rcx+2Ch]
0x14000d96c  test    dil, al
0x14000d96f  jz      short loc_14000D97C
0x14000d971  cmp     byte ptr [rcx+29h], 4
0x14000d975  jb      short loc_14000D97C
0x14000d977  mov     dl, sil
0x14000d97a  jmp     short loc_14000D97E
0x14000d97c  xor     dl, dl
0x14000d97e  lea     rax, WPP_RECORDER_INITIALIZED
0x14000d985  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000d98c  setnz   r8b
0x14000d990  test    dl, dl
0x14000d992  jnz     short loc_14000D999
0x14000d994  test    r8b, r8b
0x14000d997  jz      short loc_14000D9B7
0x14000d999  mov     eax, [rbx+68h]
0x14000d99c  mov     [rsp+88h+var_38], eax
0x14000d9a0  mov     [rsp+88h+var_40], r9d
0x14000d9a5  mov     r9, [rcx+40h]
0x14000d9a9  mov     rcx, [rcx+18h]
0x14000d9ad  mov     [rsp+88h+var_48], rbp
0x14000d9b2  call    WPP_RECORDER_AND_TRACE_SF_qCODECIDCODECID
0x14000d9b7  test    rbp, rbp
0x14000d9ba  jz      short loc_14000D9C4
0x14000d9bc  mov     eax, [rbx+68h]
0x14000d9bf  cmp     [rbp+4], eax
0x14000d9c2  jz      short loc_14000D9E6
0x14000d9c4  mov     ecx, [rbx+68h]
0x14000d9c7  lea     rdx, [rsp+88h+arg_10]
0x14000d9cf  call    ?ScoSelectChannelConfigsFromCodecId@@YAJW4_CODECID@@PEAPEBU_SCO_OPEN_CONTEXT@@@Z; ScoSelectChannelConfigsFromCodecId(_CODECID,_SCO_OPEN_CONTEXT const * *)
0x14000d9d4  mov     edi, eax
0x14000d9d6  test    eax, eax
0x14000d9d8  js      loc_14000DCCE
0x14000d9de  mov     rbp, [rsp+88h+arg_10]
0x14000d9e6  mov     edx, [rbx+68h]
0x14000d9e9  mov     rcx, [rbx+0A0h]
0x14000d9f0  call    AudioQueue_SetCodecId
0x14000d9f5  mov     edi, eax
0x14000d9f7  test    eax, eax
0x14000d9f9  js      loc_14000DCCE
0x14000d9ff  mov     edx, [rbx+68h]
0x14000da02  mov     rcx, [rbx+0F0h]
0x14000da09  call    AudioQueue_SetCodecId
0x14000da0e  mov     edi, eax
0x14000da10  test    eax, eax
0x14000da12  js      loc_14000DCCE
0x14000da18  mov     rax, [rbx+8]
0x14000da1c  mov     ecx, r14d
0x14000da1f  mov     edx, [rbx+18h]
0x14000da22  mov     rax, [rax+20h]
0x14000da26  call    _guard_dispatch_icall
0x14000da2b  mov     r14, rax
0x14000da2e  test    rax, rax
0x14000da31  jnz     short loc_14000DA3D
0x14000da33  mov     edi, 0C000009Ah
0x14000da38  jmp     loc_14000DCCE
0x14000da3d  mov     r8, [rbx+8]
0x14000da41  lea     rax, [rsp+88h+arg_18]
0x14000da49  mov     rdx, [rbx]
0x14000da4c  mov     r9, r14
0x14000da4f  xor     ecx, ecx
0x14000da51  mov     [rsp+88h+var_68], rax
0x14000da56  call    WdfIoTargetCreateAndFormatRequestForBrb
0x14000da5b  mov     edi, eax
0x14000da5d  test    eax, eax
0x14000da5f  js      loc_14000DC8F
0x14000da65  mov     r9, rbp; struct _SCO_OPEN_CONTEXT *
0x14000da68  mov     [rsp+88h+var_68], r14; struct _BRB *
0x14000da6d  mov     rbp, [rsp+88h+arg_18]
0x14000da75  mov     r8, r15; void *
0x14000da78  mov     rcx, rbp; struct WDFREQUEST__ *
0x14000da7b  mov     rdx, r12; struct WDFDEVICE__ *
0x14000da7e  call    ?ScoChannelOpenBrbBuild@@YAJPEAUWDFREQUEST__@@PEAUWDFDEVICE__@@PEAXPEBU_SCO_OPEN_CONTEXT@@PEAU_BRB@@@Z; ScoChannelOpenBrbBuild(WDFREQUEST__ *,WDFDEVICE__ *,void *,_SCO_OPEN_CONTEXT const *,_BRB *)
0x14000da83  xor     r14d, r14d
0x14000da86  mov     edi, eax
0x14000da88  test    eax, eax
0x14000da8a  js      loc_14000DC97
0x14000da90  lea     edx, [r14+4]
0x14000da94  mov     rcx, rbx
0x14000da97  call    SetScoState
0x14000da9c  mov     rax, cs:WdfFunctions_01015
0x14000daa3  lea     r8, ?ScoOpenCompletionRoutine@@YAXPEAUWDFREQUEST__@@PEAUWDFIOTARGET__@@PEAU_WDF_REQUEST_COMPLETION_PARAMS@@PEAX@Z; ScoOpenCompletionRoutine(WDFREQUEST__ *,WDFIOTARGET__ *,_WDF_REQUEST_COMPLETION_PARAMS *,void *)
0x14000daaa  mov     rcx, cs:WdfDriverGlobals
0x14000dab1  mov     r9, r12
0x14000dab4  mov     rdx, rbp
0x14000dab7  mov     rax, [rax+820h]
0x14000dabe  call    _guard_dispatch_icall
0x14000dac3  mov     rdx, [rbx+170h]
0x14000daca  lea     rcx, [rsp+88h+arg_18]
0x14000dad2  call    ?acquire_wdf_spin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUWDFSPINLOCK__@@P6AXPEAU1@@Z$1?WdfSpinLockRelease@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAUWDFSPINLOCK__@@@Z; wil::acquire_wdf_spin_lock(WDFSPINLOCK__ *)
0x14000dad7  mov     [rbx+1D0h], rbp
0x14000dade  lea     rdi, aOnecoreuapDriv; "onecoreuap\\drivers\\wdm\\audio\\driver"...
0x14000dae5  mov     rax, cs:WdfFunctions_01015
0x14000daec  mov     r9d, 770h
0x14000daf2  mov     rcx, cs:WdfDriverGlobals
0x14000daf9  xor     r8d, r8d
0x14000dafc  mov     rdx, rbp
0x14000daff  mov     [rsp+88h+var_68], rdi
0x14000db04  mov     rax, [rax+668h]
0x14000db0b  call    _guard_dispatch_icall
0x14000db10  lea     rcx, [rsp+88h+arg_18]
0x14000db18  call    ??1?$unique_storage@U?$resource_policy@PEAUWDFSPINLOCK__@@P6AXPEAU1@@Z$1?WdfSpinLockRelease@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(void)
0x14000db1d  mov     rax, cs:WdfFunctions_01015
0x14000db24  mov     r8, 0FFFFFFFFFD050F80h
0x14000db2b  mov     rdx, [rbx+1E0h]
0x14000db32  mov     rcx, cs:WdfDriverGlobals
0x14000db39  mov     rax, [rax+9F8h]
0x14000db40  call    _guard_dispatch_icall
0x14000db45  mov     rax, cs:WdfFunctions_01015
0x14000db4c  xor     r9d, r9d
0x14000db4f  mov     r8, [rbx]
0x14000db52  mov     rdx, rbp
0x14000db55  mov     rcx, cs:WdfDriverGlobals
0x14000db5c  mov     rax, [rax+7E8h]
0x14000db63  call    _guard_dispatch_icall
0x14000db68  test    al, al
0x14000db6a  jnz     loc_14000DC89
0x14000db70  mov     rax, cs:WdfFunctions_01015
0x14000db77  mov     r8b, sil
0x14000db7a  mov     rdx, [rbx+1E0h]
0x14000db81  mov     rcx, cs:WdfDriverGlobals
0x14000db88  mov     rax, [rax+0A00h]
0x14000db8f  call    _guard_dispatch_icall
0x14000db94  mov     rdx, [rbx+170h]
0x14000db9b  lea     rcx, [rsp+88h+arg_18]
0x14000dba3  call    ?acquire_wdf_spin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUWDFSPINLOCK__@@P6AXPEAU1@@Z$1?WdfSpinLockRelease@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAUWDFSPINLOCK__@@@Z; wil::acquire_wdf_spin_lock(WDFSPINLOCK__ *)
0x14000dba8  mov     rax, cs:WdfFunctions_01015
0x14000dbaf  mov     r9d, 77Ah
0x14000dbb5  mov     rdx, [rbx+1D0h]
0x14000dbbc  xor     r8d, r8d
0x14000dbbf  mov     rcx, cs:WdfDriverGlobals
0x14000dbc6  mov     [rsp+88h+var_68], rdi
0x14000dbcb  mov     rax, [rax+670h]
0x14000dbd2  call    _guard_dispatch_icall
0x14000dbd7  lea     rcx, [rsp+88h+arg_18]
0x14000dbdf  mov     [rbx+1D0h], r14
0x14000dbe6  call    ??1?$unique_storage@U?$resource_policy@PEAUWDFSPINLOCK__@@P6AXPEAU1@@Z$1?WdfSpinLockRelease@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(void)
0x14000dbeb  mov     rax, cs:WdfFunctions_01015
0x14000dbf2  mov     rdx, rbp
0x14000dbf5  mov     rcx, cs:WdfDriverGlobals
0x14000dbfc  mov     rax, [rax+7F0h]
0x14000dc03  call    _guard_dispatch_icall
0x14000dc08  mov     edi, eax
0x14000dc0a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dc11  lea     rax, WPP_GLOBAL_Control
0x14000dc18  cmp     rcx, rax
0x14000dc1b  jz      short loc_14000DC2A
0x14000dc1d  mov     eax, [rcx+2Ch]
0x14000dc20  test    al, 10h
0x14000dc22  jz      short loc_14000DC2A
0x14000dc24  cmp     byte ptr [rcx+29h], 2
0x14000dc28  jnb     short loc_14000DC2D
0x14000dc2a  xor     sil, sil
0x14000dc2d  lea     rax, WPP_RECORDER_INITIALIZED
0x14000dc34  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000dc3b  setnz   r8b
0x14000dc3f  test    sil, sil
0x14000dc42  jnz     short loc_14000DC49
0x14000dc44  test    r8b, r8b
0x14000dc47  jz      short loc_14000DC7D
0x14000dc49  mov     r9, [rcx+40h]
0x14000dc4d  lea     rdx, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x14000dc54  mov     rcx, [rcx+18h]
0x14000dc58  mov     dword ptr [rsp+88h+var_48], edi
0x14000dc5c  mov     [rsp+88h+var_50], rdx
0x14000dc61  mov     dl, sil
0x14000dc64  mov     [rsp+88h+var_58], 32h ; '2'
0x14000dc6b  mov     [rsp+88h+var_60], 5
0x14000dc73  mov     byte ptr [rsp+88h+var_68], 2
0x14000dc78  call    WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP
0x14000dc7d  xor     edx, edx
0x14000dc7f  mov     rcx, rbx
0x14000dc82  call    SetScoState
0x14000dc87  jmp     short loc_14000DC97
  ... truncated ...
```
