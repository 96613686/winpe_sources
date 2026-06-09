# GetRoleConfigurationState(HfpRoleConfigurationSet *)

- ea: `0x1400285d4`
- end: `0x140028b1f`
- name: `?GetRoleConfigurationState@@YAJPEAUHfpRoleConfigurationSet@@@Z`
- size: `1355`
- prototype: `__int64 __fastcall(struct HfpRoleConfigurationSet *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x14003003c`

## callees

- `0x140001a10`
- `0x140001a2c`
- `0x140001a50`
- `0x1400044dc`
- `0x140004650`
- `0x140004810`
- `0x14001adc0`
- `0x14001ae00`
- `0x14001aea0`
- `0x14001b2c0`
- `0x1400285d4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140028669`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400286fb`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400288f6`
- `ntoskrnl!RtlInitUnicodeString` at `0x140028971`
- `ntoskrnl!RtlInitUnicodeString` at `0x140028669`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400286fb`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400288f6`
- `ntoskrnl!RtlInitUnicodeString` at `0x140028971`

## string_xrefs

- `0x140028653`: `\Registry\Machine\System\CurrentControlSet\Control\Bluetooth\Audio\Hfp`

## pseudocode

```c
__int64 __fastcall GetRoleConfigurationState(GUID *a1)
{
  int v2; // ebx
  int v3; // r8d
  char v4; // di
  int v5; // edx
  GUID v6; // xmm0
  unsigned int v7; // r14d
  unsigned int *v8; // rsi
  GUID v9; // xmm6
  int v10; // eax
  int v11; // ecx
  unsigned int (*v12)(void); // rax
  int v13; // edx
  const WCHAR *v14; // rdx
  int v15; // edx
  int v16; // r8d
  char v17; // r9
  __int64 v18; // xmm0_8
  __int64 v19; // rax
  __int64 *v20; // rdx
  __int64 v22; // [rsp+30h] [rbp-D8h]
  int v23; // [rsp+38h] [rbp-D0h]
  int v24; // [rsp+40h] [rbp-C8h]
  int v25; // [rsp+68h] [rbp-A0h] BYREF
  int v26; // [rsp+6Ch] [rbp-9Ch] BYREF
  _QWORD v27[3]; // [rsp+70h] [rbp-98h] BYREF
  GUID Buf1; // [rsp+88h] [rbp-80h] BYREF
  __int64 v29; // [rsp+98h] [rbp-70h]
  struct _UNICODE_STRING v30; // [rsp+A0h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-58h] BYREF
  _BYTE v32[24]; // [rsp+C0h] [rbp-48h] BYREF
  GUID v33; // [rsp+D8h] [rbp-30h] BYREF
  const wchar_t *v34; // [rsp+E8h] [rbp-20h]
  __int64 v35; // [rsp+F0h] [rbp-18h]
  GUID v36; // [rsp+F8h] [rbp-10h]
  const wchar_t *v37; // [rsp+108h] [rbp+0h]
  __int64 v38; // [rsp+110h] [rbp+8h]

  v34 = L"HandsFree";
  v33 = HandsfreeAudioGatewayServiceClass_UUID;
  v35 = 0;
  v37 = L"AudioGateway";
  v36 = HandsfreeServiceClass_UUID;
  v38 = 0;
  memset(a1, 0, 0x40u);
  a1[3] = HandsfreeServiceClass_UUID;
  DestinationString = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Bluetooth\\Audio\\Hfp");
  v27[0] = 0;
  wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>>>(
    &Buf1,
    v27);
  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, struct _UNICODE_STRING *, __int64))(WdfFunctions_01015
                                                                                                 + 1832))(
         WdfDriverGlobals,
         0,
         &DestinationString,
         131097);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>>>(&Buf1);
  v25 = 0;
  v4 = 1;
  if ( v2 < 0
    || (*(_OWORD *)&v27[1] = 0,
        RtlInitUnicodeString((PUNICODE_STRING)&v27[1], L"RolePreference"),
        v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD *, int *))(WdfFunctions_01015 + 1920))(
               WdfDriverGlobals,
               v27[0],
               &v27[1],
               &v25),
        v2 < 0) )
  {
    if ( v2 != -1073741772 )
      goto LABEL_59;
    v2 = 0;
  }
  else
  {
    if ( v25 == 1 )
      v6 = HandsfreeAudioGatewayServiceClass_UUID;
    else
      v6 = HandsfreeServiceClass_UUID;
    a1[3] = v6;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || (LOBYTE(v5) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    {
      LOBYTE(v5) = 0;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      || (LOBYTE(v3) = 1, !LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v3) = 0;
    }
    if ( (_BYTE)v5 || (_BYTE)v3 )
      WPP_RECORDER_AND_TRACE_SF__guid_(
        WPP_GLOBAL_Control->AttachedDevice,
        v5,
        v3,
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        4,
        14,
        (__int64)WPP_9739fd3d85a33a980818697074cd9c28_Traceguids,
        (__int64)&a1[3]);
  }
  v7 = 0;
  while ( 1 )
  {
    BYTE4(v29) = 0;
    v8 = &v33.Data1 + 8 * (int)v7;
    v9 = *(GUID *)v8;
    Buf1 = *(GUID *)v8;
    if ( !memcmp(&Buf1, &HandsfreeServiceClass_UUID, 0x10u) )
    {
      LODWORD(v29) = 4;
    }
    else
    {
      v10 = memcmp(&Buf1, &HandsfreeAudioGatewayServiceClass_UUID, 0x10u);
      v11 = v29;
      if ( !v10 )
        v11 = 2;
      LODWORD(v29) = v11;
    }
    v12 = (unsigned int (*)(void))*((_QWORD *)v8 + 3);
    if ( v12 && !v12() )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
        || (LOBYTE(v13) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
      {
        LOBYTE(v13) = 0;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        || (LOBYTE(v3) = 1, !LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v3) = 0;
      }
      if ( (_BYTE)v13 || (_BYTE)v3 )
        WPP_RECORDER_AND_TRACE_SF__guid_(
          WPP_GLOBAL_Control->AttachedDevice,
          v13,
          v3,
          WPP_GLOBAL_Control->DeviceExtension,
          5,
          4,
          15,
          (__int64)WPP_9739fd3d85a33a980818697074cd9c28_Traceguids,
          (__int64)v8);
      goto LABEL_55;
    }
    v27[1] = 0;
    v14 = (const WCHAR *)*((_QWORD *)v8 + 2);
    v30 = 0;
    RtlInitUnicodeString(&v30, v14);
    v22 = wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>>>(
            v32,
            &v27[1])
        + 8;
    v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, struct _UNICODE_STRING *, __int64))(WdfFunctions_01015 + 1832))(
           WdfDriverGlobals,
           v27[0],
           &v30,
           131097);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>>>(v32);
    v26 = 0;
    if ( v2 >= 0 )
    {
      v30 = 0;
      RtlInitUnicodeString(&v30, L"Enabled");
      v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, struct _UNICODE_STRING *, int *))(WdfFunctions_01015 + 1920))(
             WdfDriverGlobals,
             v27[1],
             &v30,
             &v26);
      if ( v2 >= 0 )
      {
        if ( v26 )
        {
          BYTE4(v29) = 1;
          v17 = 1;
        }
        else
        {
          v17 = 0;
        }
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
          || (LOBYTE(v15) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
        {
          LOBYTE(v15) = 0;
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
          || (LOBYTE(v16) = 1, !LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          LOBYTE(v16) = 0;
        }
        if ( (_BYTE)v15 || (_BYTE)v16 )
          WPP_RECORDER_AND_TRACE_SF__guid_ld(
            WPP_GLOBAL_Control->AttachedDevice,
            v15,
            v16,
            WPP_GLOBAL_Control->DeviceExtension,
            0,
            v22,
            v23,
            v24,
            (__int64)v8,
            v17,
            v26);
        goto LABEL_54;
      }
    }
    if ( v2 != -1073741772 )
      break;
LABEL_54:
    v2 = 0;
    wil::details::unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>(&v27[1]);
LABEL_55:
    v18 = v29;
    v19 = 3LL * (int)v7++;
    *(GUID *)((char *)a1 + 8 * v19) = v9;
    *((_QWORD *)&a1[1].Data1 + v19) = v18;
    if ( v7 >= 2 )
      goto LABEL_58;
  }
  wil::details::unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>(&v27[1]);
LABEL_58:
  if ( v2 < 0 )
  {
LABEL_59:
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v4 = 0;
    }
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v20 = WPP_9739fd3d85a33a980818697074cd9c28_Traceguids;
      LOBYTE(v20) = v4;
      LOBYTE(v3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v20,
        v3,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        4,
        17,
        (__int64)WPP_9739fd3d85a33a980818697074cd9c28_Traceguids,
        v2);
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>(v27);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400285d4  mov     rax, rsp
0x1400285d7  push    rbp
0x1400285d8  push    rbx
0x1400285d9  push    rsi
0x1400285da  push    rdi
0x1400285db  push    r12
0x1400285dd  push    r13
0x1400285df  push    r14
0x1400285e1  push    r15
0x1400285e3  lea     rbp, [rax-78h]
0x1400285e7  sub     rsp, 138h
0x1400285ee  movaps  xmmword ptr [rax-58h], xmm6
0x1400285f2  mov     rax, cs:__security_cookie
0x1400285f9  xor     rax, rsp
0x1400285fc  mov     [rbp+70h+var_60], rax
0x140028600  movups  xmm0, xmmword ptr cs:HandsfreeAudioGatewayServiceClass_UUID.Data1
0x140028607  xor     r12d, r12d
0x14002860a  lea     rax, aHandsfree; "HandsFree"
0x140028611  mov     [rbp+70h+var_90], rax
0x140028615  xor     edx, edx; Val
0x140028617  movdqu  [rbp+70h+var_A0], xmm0
0x14002861c  lea     rax, aAudiogateway; "AudioGateway"
0x140028623  mov     r13, rcx
0x140028626  movups  xmm0, xmmword ptr cs:HandsfreeServiceClass_UUID.Data1
0x14002862d  lea     r8d, [r12+40h]; Size
0x140028632  mov     [rbp+70h+var_88], r12
0x140028636  mov     [rbp+70h+var_70], rax
0x14002863a  movdqu  [rbp+70h+var_80], xmm0
0x14002863f  mov     [rbp+70h+var_68], r12
0x140028643  call    memset
0x140028648  movups  xmm0, xmmword ptr cs:HandsfreeServiceClass_UUID.Data1
0x14002864f  lea     rsi, [r13+30h]
0x140028653  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\System\\CurrentCon"...
0x14002865a  movdqu  xmmword ptr [rsi], xmm0
0x14002865e  lea     rcx, [rbp+70h+DestinationString]; DestinationString
0x140028662  xorps   xmm0, xmm0
0x140028665  movups  xmmword ptr [rbp+70h+DestinationString.Length], xmm0
0x140028669  call    cs:__imp_RtlInitUnicodeString
0x140028670  nop     dword ptr [rax+rax+00h]
0x140028675  lea     rdx, [rsp+170h+var_108]
0x14002867a  mov     qword ptr [rsp+170h+var_108], r12
0x14002867f  lea     rcx, [rbp+70h+Buf1]
0x140028683  call    ??$out_param@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUWDFKEY__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AU?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUWDFKEY__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@0@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUWDFKEY__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>> &)
0x140028688  mov     r9d, 20019h
0x14002868e  lea     r8, [rbp+70h+DestinationString]
0x140028692  xor     edx, edx
0x140028694  lea     rcx, [rax+8]
0x140028698  mov     rax, cs:WdfFunctions_01015
0x14002869f  mov     [rsp+170h+var_148], rcx
0x1400286a4  mov     rcx, cs:WdfDriverGlobals
0x1400286ab  mov     [rsp+170h+var_150], r12
0x1400286b0  mov     rax, [rax+728h]
0x1400286b7  call    _guard_dispatch_icall
0x1400286bc  lea     rcx, [rbp+70h+Buf1]
0x1400286c0  mov     ebx, eax
0x1400286c2  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUWDFKEY__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>>>(void)
0x1400286c7  mov     dword ptr [rsp+170h+var_110], r12d
0x1400286cc  lea     edi, [r12+1]
0x1400286d1  lea     r14, WPP_GLOBAL_Control
0x1400286d8  lea     r15, WPP_RECORDER_INITIALIZED
0x1400286df  test    ebx, ebx
0x1400286e1  js      loc_1400287C6
0x1400286e7  xorps   xmm0, xmm0
0x1400286ea  lea     rdx, aRolepreference; "RolePreference"
0x1400286f1  lea     rcx, [rsp+170h+var_108+8]; DestinationString
0x1400286f6  movups  xmmword ptr [rsp+170h+var_108+8], xmm0
0x1400286fb  call    cs:__imp_RtlInitUnicodeString
0x140028702  nop     dword ptr [rax+rax+00h]
0x140028707  mov     rax, cs:WdfFunctions_01015
0x14002870e  lea     r9, [rsp+170h+var_110]
0x140028713  mov     rdx, qword ptr [rsp+170h+var_108]
0x140028718  lea     r8, [rsp+170h+var_108+8]
0x14002871d  mov     rcx, cs:WdfDriverGlobals
0x140028724  mov     rax, [rax+780h]
0x14002872b  call    _guard_dispatch_icall
0x140028730  mov     ebx, eax
0x140028732  test    eax, eax
0x140028734  js      loc_1400287C6
0x14002873a  cmp     dword ptr [rsp+170h+var_110], edi
0x14002873e  jnz     short loc_140028749
0x140028740  movups  xmm0, xmmword ptr cs:HandsfreeAudioGatewayServiceClass_UUID.Data1
0x140028747  jmp     short loc_140028750
0x140028749  movups  xmm0, xmmword ptr cs:HandsfreeServiceClass_UUID.Data1
0x140028750  movdqu  xmmword ptr [rsi], xmm0
0x140028754  mov     rcx, cs:WPP_GLOBAL_Control
0x14002875b  cmp     rcx, r14
0x14002875e  jz      short loc_140028770
0x140028760  mov     eax, [rcx+2Ch]
0x140028763  test    al, 8
0x140028765  jz      short loc_140028770
0x140028767  cmp     byte ptr [rcx+29h], 5
0x14002876b  mov     dl, dil
0x14002876e  jnb     short loc_140028773
0x140028770  mov     dl, r12b
0x140028773  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14002877a  jz      short loc_140028786
0x14002877c  mov     r8b, dil
0x14002877f  cmp     [rcx+48h], r12w
0x140028784  jnz     short loc_140028789
0x140028786  mov     r8b, r12b
0x140028789  test    dl, dl
0x14002878b  jnz     short loc_140028792
0x14002878d  test    r8b, r8b
0x140028790  jz      short loc_1400287D5
0x140028792  mov     qword ptr [rsp+170h+var_130], rsi
0x140028797  lea     r9, WPP_9739fd3d85a33a980818697074cd9c28_Traceguids
0x14002879e  mov     [rsp+170h+var_138], r9
0x1400287a3  mov     r9, [rcx+40h]
0x1400287a7  mov     rcx, [rcx+18h]
0x1400287ab  mov     word ptr [rsp+170h+var_140], 0Eh
0x1400287b2  mov     dword ptr [rsp+170h+var_148], 4
0x1400287ba  mov     byte ptr [rsp+170h+var_150], 5
0x1400287bf  call    WPP_RECORDER_AND_TRACE_SF__guid_
0x1400287c4  jmp     short loc_1400287D5
0x1400287c6  cmp     ebx, 0C0000034h
0x1400287cc  jnz     loc_140028A85
0x1400287d2  mov     ebx, r12d
0x1400287d5  mov     r14d, r12d
0x1400287d8  movsxd  r15, r14d
0x1400287db  lea     rsi, [rbp+70h+var_A0]
0x1400287df  mov     rax, r15
0x1400287e2  mov     byte ptr [rbp+70h+var_E0+4], r12b
0x1400287e6  shl     rax, 5
0x1400287ea  lea     rdx, HandsfreeServiceClass_UUID; Buf2
0x1400287f1  add     rsi, rax
0x1400287f4  lea     rcx, [rbp+70h+Buf1]; Buf1
0x1400287f8  mov     r8d, 10h; Size
0x1400287fe  movups  xmm6, xmmword ptr [rsi]
0x140028801  movups  [rbp+70h+Buf1], xmm6
0x140028805  call    memcmp
0x14002880a  test    eax, eax
0x14002880c  jnz     short loc_140028817
0x14002880e  mov     dword ptr [rbp+70h+var_E0], 4
0x140028815  jmp     short loc_14002883D
0x140028817  mov     r8d, 10h; Size
0x14002881d  lea     rdx, HandsfreeAudioGatewayServiceClass_UUID; Buf2
0x140028824  lea     rcx, [rbp+70h+Buf1]; Buf1
0x140028828  call    memcmp
0x14002882d  mov     ecx, dword ptr [rbp+70h+var_E0]
0x140028830  test    eax, eax
0x140028832  mov     eax, 2
0x140028837  cmovz   ecx, eax
0x14002883a  mov     dword ptr [rbp+70h+var_E0], ecx
0x14002883d  mov     rax, [rsi+18h]
0x140028841  test    rax, rax
0x140028844  jz      loc_1400288DE
0x14002884a  call    _guard_dispatch_icall
0x14002884f  test    eax, eax
0x140028851  jnz     loc_1400288DE
0x140028857  mov     rcx, cs:WPP_GLOBAL_Control
0x14002885e  lea     rax, WPP_GLOBAL_Control
0x140028865  cmp     rcx, rax
0x140028868  jz      short loc_14002887A
0x14002886a  mov     eax, [rcx+2Ch]
0x14002886d  test    al, 8
0x14002886f  jz      short loc_14002887A
0x140028871  cmp     byte ptr [rcx+29h], 5
0x140028875  mov     dl, dil
0x140028878  jnb     short loc_14002887D
0x14002887a  mov     dl, r12b
0x14002887d  lea     rax, WPP_RECORDER_INITIALIZED
0x140028884  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002888b  jz      short loc_140028897
0x14002888d  mov     r8b, dil
0x140028890  cmp     [rcx+48h], r12w
0x140028895  jnz     short loc_14002889A
0x140028897  mov     r8b, r12b
0x14002889a  test    dl, dl
0x14002889c  jnz     short loc_1400288A7
0x14002889e  test    r8b, r8b
0x1400288a1  jz      loc_140028A44
0x1400288a7  mov     qword ptr [rsp+170h+var_130], rsi
0x1400288ac  lea     r9, WPP_9739fd3d85a33a980818697074cd9c28_Traceguids
0x1400288b3  mov     [rsp+170h+var_138], r9
0x1400288b8  mov     r9, [rcx+40h]
0x1400288bc  mov     rcx, [rcx+18h]
0x1400288c0  mov     word ptr [rsp+170h+var_140], 0Fh
0x1400288c7  mov     dword ptr [rsp+170h+var_148], 4
0x1400288cf  mov     byte ptr [rsp+170h+var_150], 5
0x1400288d4  call    WPP_RECORDER_AND_TRACE_SF__guid_
0x1400288d9  jmp     loc_140028A44
0x1400288de  mov     qword ptr [rsp+170h+var_108+8], r12
0x1400288e3  test    ebx, ebx
0x1400288e5  js      short loc_140028952
0x1400288e7  mov     rdx, [rsi+10h]; SourceString
0x1400288eb  lea     rcx, [rbp+70h+var_D8]; DestinationString
0x1400288ef  xorps   xmm0, xmm0
0x1400288f2  movups  xmmword ptr [rbp+70h+var_D8.Length], xmm0
0x1400288f6  call    cs:__imp_RtlInitUnicodeString
0x1400288fd  nop     dword ptr [rax+rax+00h]
0x140028902  lea     rdx, [rsp+170h+var_108+8]
0x140028907  lea     rcx, [rbp+70h+var_B8]
0x14002890b  call    ??$out_param@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUWDFKEY__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AU?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUWDFKEY__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@0@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUWDFKEY__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>> &)
0x140028910  mov     rdx, qword ptr [rsp+170h+var_108]
0x140028915  lea     r8, [rbp+70h+var_D8]
0x140028919  mov     r9d, 20019h
0x14002891f  lea     rcx, [rax+8]
0x140028923  mov     rax, cs:WdfFunctions_01015
0x14002892a  mov     [rsp+170h+var_148], rcx
0x14002892f  mov     rcx, cs:WdfDriverGlobals
0x140028936  mov     [rsp+170h+var_150], r12
0x14002893b  mov     rax, [rax+728h]
0x140028942  call    _guard_dispatch_icall
0x140028947  lea     rcx, [rbp+70h+var_B8]
0x14002894b  mov     ebx, eax
0x14002894d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUWDFKEY__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>>>(void)
0x140028952  mov     dword ptr [rsp+170h+var_110+4], r12d
0x140028957  test    ebx, ebx
0x140028959  js      loc_140028A2F
0x14002895f  xorps   xmm0, xmm0
0x140028962  lea     rdx, aEnabled; "Enabled"
0x140028969  lea     rcx, [rbp+70h+var_D8]; DestinationString
0x14002896d  movups  xmmword ptr [rbp+70h+var_D8.Length], xmm0
0x140028971  call    cs:__imp_RtlInitUnicodeString
0x140028978  nop     dword ptr [rax+rax+00h]
0x14002897d  mov     rax, cs:WdfFunctions_01015
0x140028984  lea     r9, [rsp+170h+var_110+4]
0x140028989  mov     rdx, qword ptr [rsp+170h+var_108+8]
0x14002898e  lea     r8, [rbp+70h+var_D8]
0x140028992  mov     rcx, cs:WdfDriverGlobals
0x140028999  mov     rax, [rax+780h]
0x1400289a0  call    _guard_dispatch_icall
0x1400289a5  mov     ebx, eax
0x1400289a7  test    eax, eax
0x1400289a9  js      loc_140028A2F
0x1400289af  mov     r10d, dword ptr [rsp+170h+var_110+4]
0x1400289b4  test    r10d, r10d
0x1400289b7  jz      short loc_1400289C2
0x1400289b9  mov     byte ptr [rbp+70h+var_E0+4], dil
0x1400289bd  mov     r9d, edi
0x1400289c0  jmp     short loc_1400289C5
0x1400289c2  mov     r9d, r12d
0x1400289c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400289cc  lea     rax, WPP_GLOBAL_Control
0x1400289d3  cmp     rcx, rax
0x1400289d6  jz      short loc_1400289E8
0x1400289d8  mov     eax, [rcx+2Ch]
0x1400289db  test    al, 8
0x1400289dd  jz      short loc_1400289E8
0x1400289df  cmp     byte ptr [rcx+29h], 5
0x1400289e3  mov     dl, dil
0x1400289e6  jnb     short loc_1400289EB
0x1400289e8  mov     dl, r12b
0x1400289eb  lea     rax, WPP_RECORDER_INITIALIZED
0x1400289f2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400289f9  jz      short loc_140028A05
0x1400289fb  mov     r8b, dil
0x1400289fe  cmp     [rcx+48h], r12w
0x140028a03  jnz     short loc_140028A08
0x140028a05  mov     r8b, r12b
0x140028a08  test    dl, dl
0x140028a0a  jnz     short loc_140028A11
0x140028a0c  test    r8b, r8b
0x140028a0f  jz      short loc_140028A37
0x140028a11  mov     [rsp+50h], r10d
0x140028a16  mov     [rsp+170h+var_128], r9d
0x140028a1b  mov     r9, [rcx+40h]
0x140028a1f  mov     rcx, [rcx+18h]
0x140028a23  mov     qword ptr [rsp+170h+var_130], rsi
0x140028a28  call    WPP_RECORDER_AND_TRACE_SF__guid_ld
0x140028a2d  jmp     short loc_140028A37
0x140028a2f  cmp     ebx, 0C0000034h
0x140028a35  jnz     short loc_140028A69
0x140028a37  lea     rcx, [rsp+170h+var_108+8]
0x140028a3c  mov     ebx, r12d
0x140028a3f  call    ??1?$unique_storage@U?$resource_policy@PEAUWDFSTRING__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>(void)
0x140028a44  movsd   xmm0, [rbp+70h+var_E0]
0x140028a49  lea     rax, [r15+r15*2]
0x140028a4d  add     r14d, edi
0x140028a50  movups  xmmword ptr [r13+rax*8+0], xmm6
0x140028a56  movsd   qword ptr [r13+rax*8+10h], xmm0
0x140028a5d  cmp     r14d, 2
0x140028a61  jb      loc_1400287D8
0x140028a67  jmp     short loc_140028A73
0x140028a69  lea     rcx, [rsp+170h+var_108+8]
0x140028a6e  call    ??1?$unique_storage@U?$resource_policy@PEAUWDFSTRING__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>(void)
0x140028a73  test    ebx, ebx
0x140028a75  jns     short loc_140028AEA
0x140028a77  lea     r14, WPP_GLOBAL_Control
0x140028a7e  lea     r15, WPP_RECORDER_INITIALIZED
0x140028a85  mov     rcx, cs:WPP_GLOBAL_Control
0x140028a8c  cmp     rcx, r14
0x140028a8f  jz      short loc_140028A9E
0x140028a91  mov     eax, [rcx+2Ch]
0x140028a94  test    al, 8
0x140028a96  jz      short loc_140028A9E
0x140028a98  cmp     byte ptr [rcx+29h], 2
0x140028a9c  jnb     short loc_140028AA1
0x140028a9e  mov     dil, r12b
0x140028aa1  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140028aa8  setnz   r8b
0x140028aac  test    dil, dil
0x140028aaf  jnz     short loc_140028AB6
0x140028ab1  test    r8b, r8b
0x140028ab4  jz      short loc_140028AEA
0x140028ab6  mov     r9, [rcx+40h]
0x140028aba  lea     rdx, WPP_9739fd3d85a33a980818697074cd9c28_Traceguids
0x140028ac1  mov     rcx, [rcx+18h]
0x140028ac5  mov     [rsp+170h+var_130], ebx
0x140028ac9  mov     [rsp+170h+var_138], rdx
  ... truncated ...
```
