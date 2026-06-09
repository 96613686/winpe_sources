# FSMDeviceWatcher::InternalUpdateNPUBaseEffectOnDevices(_GUID const &,_GUID const &)

- ea: `0x180011dc0`
- end: `0x1800120d8`
- name: `?InternalUpdateNPUBaseEffectOnDevices@FSMDeviceWatcher@@MEAAJAEBU_GUID@@0@Z`
- size: `792`
- prototype: `int(FSMDeviceWatcher *__hidden this, const struct _GUID *, const struct _GUID *)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x1800060e8`
- `0x1800060f8`
- `0x180006a98`
- `0x180006d38`
- `0x18000d154`
- `0x18000d1e0`
- `0x18000d4f8`
- `0x18000d62c`
- `0x180011438`
- `0x180011dc0`
- `0x1800185fc`
- `0x18002fa3c`
- `0x18002fd04`
- `0x180040004`
- `0x1800426d8`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Set_Device_Interface_PropertyW` at `0x180011fce`
- `api-ms-win-devices-config-l1-1-1!CM_Set_Device_Interface_PropertyW` at `0x180011ff5`
- `api-ms-win-devices-config-l1-1-1!CM_Set_Device_Interface_PropertyW` at `0x180011fce`
- `api-ms-win-devices-config-l1-1-1!CM_Set_Device_Interface_PropertyW` at `0x180011ff5`

## pseudocode

```c
__int64 __fastcall FSMDeviceWatcher::InternalUpdateNPUBaseEffectOnDevices(
        FSMDeviceWatcher *this,
        const struct _GUID *a2,
        struct _GUID *a3)
{
  char v3; // bl
  const struct std::nothrow_t *v7; // rdx
  const struct _GUID *v8; // r8
  GuidTrace *v9; // rax
  const char *String; // rbx
  GuidTrace *v11; // rax
  const char *v12; // rax
  int v13; // edi
  __int64 v14; // rdx
  unsigned __int8 Level; // al
  const struct std::nothrow_t *v16; // rdx
  __int64 v17; // rdx
  void **i; // rbx
  __int64 v20; // rax
  void *v21; // [rsp+30h] [rbp-19h] BYREF
  void **v22[3]; // [rsp+38h] [rbp-11h] BYREF
  _BYTE v23[32]; // [rsp+50h] [rbp+7h] BYREF
  _BYTE v24[32]; // [rsp+70h] [rbp+27h] BYREF
  int v25; // [rsp+C8h] [rbp+7Fh] BYREF

  v3 = 0;
  v25 = 0;
  utl::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>(v22);
  v21 = 0;
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
  {
    v9 = GuidTrace::GuidTrace((GuidTrace *)v24, v8);
    String = GuidTrace::GetString(v9);
    v11 = GuidTrace::GuidTrace((GuidTrace *)v23, a2);
    v12 = GuidTrace::GetString(v11);
    WPP_SF_qss(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)v12, (__int64)String);
    v3 = 3;
  }
  if ( (v3 & 2) != 0 )
  {
    v3 &= ~2u;
    FSString::~FSString((FSString *)v23, v7);
  }
  if ( (v3 & 1) != 0 )
    FSString::~FSString((FSString *)v24, v7);
  v13 = FSEnumDeviceInterfaces(a2, v7, v22);
  if ( v13 < 0 )
  {
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v14 = 275;
LABEL_10:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, this, v13);
    }
LABEL_11:
    Level = _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel();
LABEL_38:
    if ( !Level )
      goto LABEL_19;
    v17 = 281;
    goto LABEL_18;
  }
  if ( v22[2] )
  {
    for ( i = v22[0]; i != (void **)v22; i = (void **)*i )
    {
      v20 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1 )
        v20 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
      if ( v20 )
      {
        LOBYTE(v25) = -1;
        if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
          WPP_SF_qS(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            278,
            (unsigned int)&WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
            (_DWORD)this,
            (__int64)i[2]);
        v13 = FSSetDeviceInterfaceProperty(
                (const unsigned __int16 *)i[2],
                &DEVPKEY_DeviceInterface_FSM_VirtualCamera_EffectsClsid,
                0xDu,
                (unsigned __int8 *const)a3,
                0x10u);
        if ( v13 < 0 )
        {
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_11;
          v14 = 279;
          goto LABEL_10;
        }
        v13 = FSSetDeviceInterfaceProperty(
                (const unsigned __int16 *)i[2],
                &DEVPKEY_DeviceInterface_IsWindowsCameraEffectAvailable,
                0x11u,
                (unsigned __int8 *const)&v25,
                1u);
        if ( v13 < 0 )
        {
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v14 = 280;
            goto LABEL_10;
          }
          break;
        }
      }
      else
      {
        if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
          WPP_SF_qS(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            277,
            (unsigned int)&WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
            (_DWORD)this,
            (__int64)i[2]);
        CM_Set_Device_Interface_PropertyW(
          (LPCWSTR)i[2],
          &DEVPKEY_DeviceInterface_FSM_VirtualCamera_EffectsClsid,
          0,
          0,
          0,
          0);
        CM_Set_Device_Interface_PropertyW(
          (LPCWSTR)i[2],
          &DEVPKEY_DeviceInterface_IsWindowsCameraEffectAvailable,
          0,
          0,
          0,
          0);
      }
    }
    Level = _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel();
    if ( v13 >= 0 )
      goto LABEL_16;
    goto LABEL_38;
  }
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 276, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, this);
  Level = _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel();
LABEL_16:
  if ( Level >= 8u )
  {
    v17 = 282;
LABEL_18:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v17, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, this, v13);
  }
LABEL_19:
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v21, v16);
  utl::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::clear(v22);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180011dc0  mov     [rsp-8+arg_0], rbx
0x180011dc5  mov     [rsp-8+arg_8], rdi
0x180011dca  push    rbp
0x180011dcb  push    r14
0x180011dcd  push    r15
0x180011dcf  lea     rbp, [rsp-47h]
0x180011dd4  sub     rsp, 90h
0x180011ddb  xor     ebx, ebx
0x180011ddd  mov     r14, rcx
0x180011de0  lea     rcx, [rbp+57h+var_68]
0x180011de4  mov     [rbp+57h+arg_18], ebx
0x180011de7  mov     r15, r8
0x180011dea  mov     rdi, rdx
0x180011ded  call    ??0?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAA@XZ; utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>(void)
0x180011df2  mov     [rbp+57h+var_70], rbx
0x180011df6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180011dfb  cmp     al, 8
0x180011dfd  jb      short loc_180011E4F
0x180011dff  mov     rdx, r8; struct _GUID *
0x180011e02  lea     rcx, [rbp+57h+var_30]; this
0x180011e06  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x180011e0b  mov     rcx, rax; this
0x180011e0e  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x180011e13  lea     rcx, [rbp+57h+var_50]; this
0x180011e17  mov     rdx, rdi; struct _GUID *
0x180011e1a  mov     rbx, rax
0x180011e1d  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x180011e22  mov     rcx, rax; this
0x180011e25  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x180011e2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e31  mov     r9, r14
0x180011e34  mov     qword ptr [rsp+0A0h+ulFlags], rbx; __int64
0x180011e39  mov     qword ptr [rsp+0A0h+PropertyBufferSize], rax; __int64
0x180011e3e  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180011e45  call    WPP_SF_qss
0x180011e4a  mov     ebx, 3
0x180011e4f  test    bl, 2
0x180011e52  jz      short loc_180011E60
0x180011e54  and     ebx, 0FFFFFFFDh
0x180011e57  lea     rcx, [rbp+57h+var_50]; this
0x180011e5b  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180011e60  test    bl, 1
0x180011e63  jz      short loc_180011E6E
0x180011e65  lea     rcx, [rbp+57h+var_30]; this
0x180011e69  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180011e6e  lea     r8, [rbp+57h+var_68]
0x180011e72  mov     rcx, rdi
0x180011e75  call    ?FSEnumDeviceInterfaces@@YAJAEBU_GUID@@_NAEAV?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z; FSEnumDeviceInterfaces(_GUID const &,bool,utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &)
0x180011e7a  mov     edi, eax
0x180011e7c  test    eax, eax
0x180011e7e  jns     short loc_180011EB6
0x180011e80  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180011e85  cmp     al, 1
0x180011e87  jb      short loc_180011EAC
0x180011e89  mov     edx, 113h
0x180011e8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e95  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x180011e9c  mov     r9, r14
0x180011e9f  mov     [rsp+0A0h+PropertyBufferSize], edi
0x180011ea3  mov     rcx, [rcx+10h]
0x180011ea7  call    WPP_SF_qD
0x180011eac  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180011eb1  jmp     loc_1800120C6
0x180011eb6  cmp     [rbp+57h+var_58], 0
0x180011ebb  jnz     loc_180011F48
0x180011ec1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180011ec6  cmp     al, 8
0x180011ec8  jb      short loc_180011EEC
0x180011eca  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ed1  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x180011ed8  mov     edx, 114h
0x180011edd  mov     r9, r14
0x180011ee0  mov     rcx, [rcx+0D8h]
0x180011ee7  call    WPP_SF_q
0x180011eec  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180011ef1  cmp     al, 8
0x180011ef3  jb      short loc_180011F1B
0x180011ef5  mov     edx, 11Ah
0x180011efa  mov     rcx, cs:WPP_GLOBAL_Control
0x180011f01  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x180011f08  mov     r9, r14
0x180011f0b  mov     [rsp+0A0h+PropertyBufferSize], edi
0x180011f0f  mov     rcx, [rcx+0D8h]
0x180011f16  call    WPP_SF_qD
0x180011f1b  lea     rcx, [rbp+57h+var_70]
0x180011f1f  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180011f24  lea     rcx, [rbp+57h+var_68]
0x180011f28  call    ?clear@?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAAXXZ; utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::clear(void)
0x180011f2d  lea     r11, [rsp+0A0h+var_10]
0x180011f35  mov     eax, edi
0x180011f37  mov     rbx, [r11+20h]
0x180011f3b  mov     rdi, [r11+28h]
0x180011f3f  mov     rsp, r11
0x180011f42  pop     r15
0x180011f44  pop     r14
0x180011f46  pop     rbp
0x180011f47  retn
0x180011f48  mov     rbx, [rbp+57h+var_68]
0x180011f4c  lea     rax, [rbp+57h+var_68]
0x180011f50  cmp     rbx, rax
0x180011f53  jz      loc_1800120B9
0x180011f59  mov     rax, [r15]
0x180011f5c  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180011f63  jnz     short loc_180011F70
0x180011f65  mov     rax, [r15+8]
0x180011f69  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x180011f70  test    rax, rax
0x180011f73  jnz     loc_180012000
0x180011f79  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180011f7e  cmp     al, 8
0x180011f80  jb      short loc_180011FAD
0x180011f82  mov     rcx, cs:WPP_GLOBAL_Control
0x180011f89  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x180011f90  mov     rax, [rbx+10h]
0x180011f94  mov     edx, 115h
0x180011f99  mov     r9, r14
0x180011f9c  mov     qword ptr [rsp+0A0h+PropertyBufferSize], rax
0x180011fa1  mov     rcx, [rcx+0D8h]
0x180011fa8  call    WPP_SF_qS
0x180011fad  mov     rcx, [rbx+10h]; pszDeviceInterface
0x180011fb1  lea     rdx, DEVPKEY_DeviceInterface_FSM_VirtualCamera_EffectsClsid; PropertyKey
0x180011fb8  mov     [rsp+0A0h+ulFlags], 0; ulFlags
0x180011fc0  xor     r9d, r9d; PropertyBuffer
0x180011fc3  xor     r8d, r8d; PropertyType
0x180011fc6  mov     [rsp+0A0h+PropertyBufferSize], 0; PropertyBufferSize
0x180011fce  call    cs:__imp_CM_Set_Device_Interface_PropertyW
0x180011fd4  mov     rcx, [rbx+10h]; pszDeviceInterface
0x180011fd8  lea     rdx, DEVPKEY_DeviceInterface_IsWindowsCameraEffectAvailable; PropertyKey
0x180011fdf  xor     r9d, r9d; PropertyBuffer
0x180011fe2  mov     [rsp+0A0h+ulFlags], 0; ulFlags
0x180011fea  xor     r8d, r8d; PropertyType
0x180011fed  mov     [rsp+0A0h+PropertyBufferSize], 0; PropertyBufferSize
0x180011ff5  call    cs:__imp_CM_Set_Device_Interface_PropertyW
0x180011ffb  jmp     loc_180012087
0x180012000  mov     byte ptr [rbp+57h+arg_18], 0FFh
0x180012004  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180012009  cmp     al, 8
0x18001200b  jb      short loc_180012038
0x18001200d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012014  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x18001201b  mov     rax, [rbx+10h]
0x18001201f  mov     edx, 116h
0x180012024  mov     r9, r14
0x180012027  mov     qword ptr [rsp+0A0h+PropertyBufferSize], rax
0x18001202c  mov     rcx, [rcx+0D8h]
0x180012033  call    WPP_SF_qS
0x180012038  mov     rcx, [rbx+10h]; unsigned __int16 *
0x18001203c  lea     rdx, DEVPKEY_DeviceInterface_FSM_VirtualCamera_EffectsClsid; struct _DEVPROPKEY *
0x180012043  mov     r9, r15; unsigned __int8 *
0x180012046  mov     [rsp+0A0h+PropertyBufferSize], 10h; ULONG
0x18001204e  mov     r8d, 0Dh; unsigned int
0x180012054  call    ?FSSetDeviceInterfaceProperty@@YAJPEBGPEBU_DEVPROPKEY@@KQEAEK@Z; FSSetDeviceInterfaceProperty(ushort const *,_DEVPROPKEY const *,ulong,uchar * const,ulong)
0x180012059  mov     edi, eax
0x18001205b  test    eax, eax
0x18001205d  js      short loc_1800120A2
0x18001205f  mov     rcx, [rbx+10h]; unsigned __int16 *
0x180012063  lea     r9, [rbp+57h+arg_18]; unsigned __int8 *
0x180012067  mov     r8d, 11h; unsigned int
0x18001206d  mov     [rsp+0A0h+PropertyBufferSize], 1; ULONG
0x180012075  lea     rdx, DEVPKEY_DeviceInterface_IsWindowsCameraEffectAvailable; struct _DEVPROPKEY *
0x18001207c  call    ?FSSetDeviceInterfaceProperty@@YAJPEBGPEBU_DEVPROPKEY@@KQEAEK@Z; FSSetDeviceInterfaceProperty(ushort const *,_DEVPROPKEY const *,ulong,uchar * const,ulong)
0x180012081  mov     edi, eax
0x180012083  test    eax, eax
0x180012085  js      short loc_18001208F
0x180012087  mov     rbx, [rbx]
0x18001208a  jmp     loc_180011F4C
0x18001208f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180012094  cmp     al, 1
0x180012096  jb      short loc_1800120B9
0x180012098  mov     edx, 118h
0x18001209d  jmp     loc_180011E8E
0x1800120a2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800120a7  cmp     al, 1
0x1800120a9  jb      loc_180011EAC
0x1800120af  mov     edx, 117h
0x1800120b4  jmp     loc_180011E8E
0x1800120b9  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800120be  test    edi, edi
0x1800120c0  jns     loc_180011EF1
0x1800120c6  cmp     al, 1
0x1800120c8  jb      loc_180011F1B
0x1800120ce  mov     edx, 119h
0x1800120d3  jmp     loc_180011EFA
```
