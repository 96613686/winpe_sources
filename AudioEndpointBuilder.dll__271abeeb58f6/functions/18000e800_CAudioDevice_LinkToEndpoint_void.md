# CAudioDevice::LinkToEndpoint(void)

- ea: `0x18000e800`
- end: `0x18000ece0`
- name: `?LinkToEndpoint@CAudioDevice@@AEAAJXZ`
- size: `1248`
- prototype: `__int64 __fastcall(CAudioDevice *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d000`

## callees

- `0x180006b0c`
- `0x18000e800`
- `0x180010da8`
- `0x180033578`
- `0x18003e920`
- `0x1800583c8`
- `0x180068010`

## import_xrefs

- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfacePropertySet` at `0x18000e99b`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfacePropertySet` at `0x18000ec4a`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfacePropertySet` at `0x18000e99b`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfacePropertySet` at `0x18000ec4a`

## string_xrefs

- `0x18000e9b2`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x18000ea09`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x18000ea4a`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x18000ead2`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x18000eb45`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x18000ebb8`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x18000ec5d`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CAudioDevice::LinkToEndpoint(CAudioDevice *this)
{
  __int64 *v2; // rcx
  __int64 v3; // rax
  int v4; // eax
  int v5; // ebx
  int v6; // eax
  int v7; // eax
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  unsigned int v13; // ebx
  int v15; // eax
  int v16; // [rsp+20h] [rbp-59h]
  __int64 v17; // [rsp+30h] [rbp-49h] BYREF
  int v18; // [rsp+38h] [rbp-41h] BYREF
  __int128 v19; // [rsp+40h] [rbp-39h] BYREF
  __int64 v20; // [rsp+50h] [rbp-29h]
  _QWORD v21[3]; // [rsp+58h] [rbp-21h] BYREF
  char v22; // [rsp+70h] [rbp-9h]
  __int128 v23; // [rsp+78h] [rbp-1h] BYREF
  __int128 v24; // [rsp+88h] [rbp+Fh]
  __int128 v25; // [rsp+98h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v17 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v18 = 0;
  v21[0] = &v18;
  v21[1] = &v19;
  v21[2] = &v17;
  v22 = 1;
  v19 = 0;
  v20 = 0;
  if ( !*((_DWORD *)this + 8) )
    goto LABEL_7;
  v2 = (__int64 *)*((_QWORD *)this + 5);
  v3 = *v2;
  v17 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v3 + 32))(v2, 2, &v17);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8E1,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
      (const char *)(unsigned int)v4,
      v16);
    if ( v18 )
    {
      v19 = 0;
      v20 = 0;
      (*(void (__fastcall **)(__int64, __int64 *, __int128 *))(*(_QWORD *)v17 + 48LL))(
        v17,
        &PKEY_SWD_DeviceInterfaceId,
        &v19);
      (*(void (__fastcall **)(__int64, __int64 *, __int128 *))(*(_QWORD *)v17 + 48LL))(
        v17,
        PKEY_SWD_DeviceInstanceId,
        &v19);
    }
    goto LABEL_31;
  }
  LOWORD(v19) = 31;
  *((_QWORD *)&v19 + 1) = *((_QWORD *)this + 2);
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int128 *))(*(_QWORD *)v17 + 48LL))(
         v17,
         &PKEY_SWD_DeviceInterfaceId,
         &v19);
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x8E6,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
      (const char *)(unsigned int)v5,
      (int)"Failed to set the device interface id for endpoint %ls",
      *((const char **)this + 1));
    if ( v18 )
    {
      v19 = 0;
      v20 = 0;
      (*(void (__fastcall **)(__int64, __int64 *, __int128 *))(*(_QWORD *)v17 + 48LL))(
        v17,
        &PKEY_SWD_DeviceInterfaceId,
        &v19);
      (*(void (__fastcall **)(__int64, __int64 *, __int128 *))(*(_QWORD *)v17 + 48LL))(
        v17,
        PKEY_SWD_DeviceInstanceId,
        &v19);
    }
    goto LABEL_31;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int128 *))(*(_QWORD *)v17 + 48LL))(
         v17,
         &PKEY_SWD_DeviceInterfaceId_Retained,
         &v19);
  v5 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8E9,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
      (const char *)(unsigned int)v6,
      v16);
    if ( v18 )
    {
      v19 = 0;
      v20 = 0;
      (*(void (__fastcall **)(__int64, __int64 *, __int128 *))(*(_QWORD *)v17 + 48LL))(
        v17,
        &PKEY_SWD_DeviceInterfaceId,
        &v19);
      (*(void (__fastcall **)(__int64, __int64 *, __int128 *))(*(_QWORD *)v17 + 48LL))(
        v17,
        PKEY_SWD_DeviceInstanceId,
        &v19);
    }
    goto LABEL_31;
  }
  v18 = 1;
  *((_QWORD *)&v19 + 1) = *(_QWORD *)this;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int128 *))(*(_QWORD *)v17 + 48LL))(
         v17,
         PKEY_SWD_DeviceInstanceId,
         &v19);
  v5 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8EF,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
      (const char *)(unsigned int)v7,
      v16);
    if ( v18 )
    {
      v19 = 0;
      v20 = 0;
      (*(void (__fastcall **)(__int64, __int64 *, __int128 *))(*(_QWORD *)v17 + 48LL))(
        v17,
        &PKEY_SWD_DeviceInterfaceId,
        &v19);
      (*(void (__fastcall **)(__int64, __int64 *, __int128 *))(*(_QWORD *)v17 + 48LL))(
        v17,
        PKEY_SWD_DeviceInstanceId,
        &v19);
    }
    goto LABEL_31;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int128 *))(*(_QWORD *)v17 + 48LL))(
         v17,
         PKEY_SWD_DeviceInstanceId_Retained,
         &v19);
  v9 = v8;
  if ( v8 >= 0 )
  {
LABEL_7:
    v23 = PKEY_SWD_EndpointId;
    v24 = 0u;
    LODWORD(v25) = 18;
    v10 = *((_QWORD *)this + 1);
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)(v10 + 2 * v11) );
    DWORD1(v25) = 2 * v11 + 2;
    *((_QWORD *)&v25 + 1) = v10;
    v12 = SwDeviceInterfacePropertySet(*((_QWORD *)this + 3), *((_QWORD *)this + 2), 1, &v23);
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8FF,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
        (const char *)(unsigned int)v12,
        v16);
      v22 = 0;
      lambda_b51d5189c6ddc3ed497dcff73fe1d1fb_::operator()(v21);
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      return v13;
    }
    v23 = PKEY_SWD_EndpointId_Retained;
    LODWORD(v24) = 8;
    v15 = SwDeviceInterfacePropertySet(*((_QWORD *)this + 3), *((_QWORD *)this + 2), 1, &v23);
    v5 = v15;
    if ( v15 >= 0 )
    {
      *((_DWORD *)this + 23) = 1;
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x907,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
      (const char *)(unsigned int)v15,
      v16);
    if ( v18 )
    {
      v19 = 0;
      v20 = 0;
      (*(void (__fastcall **)(__int64, __int64 *, __int128 *))(*(_QWORD *)v17 + 48LL))(
        v17,
        &PKEY_SWD_DeviceInterfaceId,
        &v19);
      (*(void (__fastcall **)(__int64, __int64 *, __int128 *))(*(_QWORD *)v17 + 48LL))(
        v17,
        PKEY_SWD_DeviceInstanceId,
        &v19);
    }
LABEL_31:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
    return (unsigned int)v5;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x8F2,
    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
    (const char *)(unsigned int)v8,
    v16);
  v22 = 0;
  lambda_b51d5189c6ddc3ed497dcff73fe1d1fb_::operator()(v21);
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  return v9;
}

```

## disassembly

```asm
0x18000e800  push    rbp
0x18000e802  push    rbx
0x18000e803  push    rsi
0x18000e804  push    rdi
0x18000e805  lea     rbp, [rsp-3Fh]
0x18000e80a  sub     rsp, 0B8h
0x18000e811  mov     rax, cs:__security_cookie
0x18000e818  xor     rax, rsp
0x18000e81b  mov     [rbp+57h+var_28], rax
0x18000e81f  mov     rdi, rcx
0x18000e822  xor     esi, esi
0x18000e824  mov     [rbp+57h+var_A0], rsi
0x18000e828  xorps   xmm0, xmm0
0x18000e82b  movups  [rbp+57h+var_58], xmm0
0x18000e82f  movups  [rbp+57h+var_48], xmm0
0x18000e833  movups  [rbp+57h+var_38], xmm0
0x18000e837  mov     [rbp+57h+var_98], esi
0x18000e83a  lea     rax, [rbp+57h+var_98]
0x18000e83e  mov     [rbp+57h+var_78], rax
0x18000e842  lea     rax, [rbp+57h+var_90]
0x18000e846  mov     [rbp+57h+var_70], rax
0x18000e84a  lea     rax, [rbp+57h+var_A0]
0x18000e84e  mov     [rbp+57h+var_68], rax
0x18000e852  mov     [rbp+57h+var_60], 1
0x18000e856  xor     eax, eax
0x18000e858  movups  [rbp+57h+var_90], xmm0
0x18000e85c  mov     [rbp+57h+var_80], rax
0x18000e860  cmp     [rcx+20h], eax
0x18000e863  jz      loc_18000E943
0x18000e869  mov     rcx, [rcx+28h]
0x18000e86d  mov     rax, [rcx]
0x18000e870  mov     [rbp+57h+var_A0], rsi
0x18000e874  lea     r8, [rbp+57h+var_A0]
0x18000e878  mov     edx, 2
0x18000e87d  mov     rax, [rax+20h]
0x18000e881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e886  mov     ebx, eax
0x18000e888  test    eax, eax
0x18000e88a  js      loc_18000EA43
0x18000e890  mov     eax, 1Fh
0x18000e895  mov     word ptr [rbp+57h+var_90], ax
0x18000e899  mov     rax, [rdi+10h]
0x18000e89d  mov     qword ptr [rbp+57h+var_90+8], rax
0x18000e8a1  mov     rcx, [rbp+57h+var_A0]
0x18000e8a5  mov     rax, [rcx]
0x18000e8a8  lea     r8, [rbp+57h+var_90]
0x18000e8ac  lea     rdx, PKEY_SWD_DeviceInterfaceId
0x18000e8b3  mov     rax, [rax+30h]
0x18000e8b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8bc  mov     ebx, eax
0x18000e8be  test    eax, eax
0x18000e8c0  js      loc_18000EAB6
0x18000e8c6  mov     rcx, [rbp+57h+var_A0]
0x18000e8ca  mov     rax, [rcx]
0x18000e8cd  lea     r8, [rbp+57h+var_90]
0x18000e8d1  lea     rdx, PKEY_SWD_DeviceInterfaceId_Retained
0x18000e8d8  mov     rax, [rax+30h]
0x18000e8dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8e1  mov     ebx, eax
0x18000e8e3  test    eax, eax
0x18000e8e5  js      loc_18000EB3E
0x18000e8eb  mov     [rbp+57h+var_98], 1
0x18000e8f2  mov     rax, [rdi]
0x18000e8f5  mov     qword ptr [rbp+57h+var_90+8], rax
0x18000e8f9  mov     rcx, [rbp+57h+var_A0]
0x18000e8fd  mov     rax, [rcx]
0x18000e900  lea     r8, [rbp+57h+var_90]
0x18000e904  lea     rdx, PKEY_SWD_DeviceInstanceId
0x18000e90b  mov     rax, [rax+30h]
0x18000e90f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e914  mov     ebx, eax
0x18000e916  test    eax, eax
0x18000e918  js      loc_18000EBB1
0x18000e91e  mov     rcx, [rbp+57h+var_A0]
0x18000e922  mov     rax, [rcx]
0x18000e925  lea     r8, [rbp+57h+var_90]
0x18000e929  lea     rdx, PKEY_SWD_DeviceInstanceId_Retained
0x18000e930  mov     rax, [rax+30h]
0x18000e934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e939  mov     ebx, eax
0x18000e93b  test    eax, eax
0x18000e93d  js      loc_18000EA02
0x18000e943  movups  xmm0, cs:PKEY_SWD_EndpointId
0x18000e94a  movups  [rbp+57h+var_58], xmm0
0x18000e94e  mov     eax, cs:dword_18006C678
0x18000e954  mov     dword ptr [rbp+57h+var_48], eax
0x18000e957  mov     dword ptr [rbp+57h+var_48+4], esi
0x18000e95a  mov     qword ptr [rbp+57h+var_48+8], rsi
0x18000e95e  mov     dword ptr [rbp+57h+var_38], 12h
0x18000e965  mov     rcx, [rdi+8]
0x18000e969  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000e970  lea     rax, [rax+1]
0x18000e974  cmp     word ptr [rcx+rax*2], 0
0x18000e979  jnz     short loc_18000E970
0x18000e97b  lea     eax, ds:2[rax*2]
0x18000e982  mov     dword ptr [rbp+57h+var_38+4], eax
0x18000e985  mov     qword ptr [rbp+57h+var_38+8], rcx
0x18000e989  lea     r9, [rbp+57h+var_58]
0x18000e98d  mov     r8d, 1
0x18000e993  mov     rdx, [rdi+10h]
0x18000e997  mov     rcx, [rdi+18h]
0x18000e99b  call    cs:__imp_SwDeviceInterfacePropertySet
0x18000e9a1  mov     ebx, eax
0x18000e9a3  test    eax, eax
0x18000e9a5  jns     loc_18000EC24
0x18000e9ab  mov     rcx, [rbp+5Fh]; this
0x18000e9af  mov     r9d, eax; char *
0x18000e9b2  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x18000e9b9  mov     edx, 8FFh; void *
0x18000e9be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e9c3  nop
0x18000e9c4  mov     [rbp+57h+var_60], 0
0x18000e9c8  lea     rcx, [rbp+57h+var_78]
0x18000e9cc  call    _lambda_b51d5189c6ddc3ed497dcff73fe1d1fb___operator__
0x18000e9d1  nop
0x18000e9d2  mov     rcx, [rbp+57h+var_A0]
0x18000e9d6  test    rcx, rcx
0x18000e9d9  jz      short loc_18000E9E8
0x18000e9db  mov     rax, [rcx]
0x18000e9de  mov     rax, [rax+10h]
0x18000e9e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9e7  nop
0x18000e9e8  mov     eax, ebx
0x18000e9ea  mov     rcx, [rbp+57h+var_28]
0x18000e9ee  xor     rcx, rsp; StackCookie
0x18000e9f1  call    __security_check_cookie
0x18000e9f6  add     rsp, 0B8h
0x18000e9fd  pop     rdi
0x18000e9fe  pop     rsi
0x18000e9ff  pop     rbx
0x18000ea00  pop     rbp
0x18000ea01  retn
0x18000ea02  mov     rcx, [rbp+5Fh]; this
0x18000ea06  mov     r9d, ebx; char *
0x18000ea09  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x18000ea10  mov     edx, 8F2h; void *
0x18000ea15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ea1a  nop
0x18000ea1b  mov     [rbp+57h+var_60], 0
0x18000ea1f  lea     rcx, [rbp+57h+var_78]
0x18000ea23  call    _lambda_b51d5189c6ddc3ed497dcff73fe1d1fb___operator__
0x18000ea28  nop
0x18000ea29  mov     rcx, [rbp+57h+var_A0]
0x18000ea2d  test    rcx, rcx
0x18000ea30  jz      short loc_18000EA3F
0x18000ea32  mov     rax, [rcx]
0x18000ea35  mov     rax, [rax+10h]
0x18000ea39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea3e  nop
0x18000ea3f  mov     eax, ebx
0x18000ea41  jmp     short loc_18000E9EA
0x18000ea43  mov     rcx, [rbp+5Fh]; this
0x18000ea47  mov     r9d, ebx; char *
0x18000ea4a  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x18000ea51  mov     edx, 8E1h; void *
0x18000ea56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ea5b  nop
0x18000ea5c  cmp     [rbp+57h+var_98], 0
0x18000ea60  jz      short loc_18000EAA6
0x18000ea62  xorps   xmm0, xmm0
0x18000ea65  xor     eax, eax
0x18000ea67  movups  [rbp+57h+var_90], xmm0
0x18000ea6b  mov     [rbp+57h+var_80], rax
0x18000ea6f  mov     rcx, [rbp+57h+var_A0]
0x18000ea73  mov     rax, [rcx]
0x18000ea76  lea     r8, [rbp+57h+var_90]
0x18000ea7a  lea     rdx, PKEY_SWD_DeviceInterfaceId
0x18000ea81  mov     rax, [rax+30h]
0x18000ea85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea8a  mov     rcx, [rbp+57h+var_A0]
0x18000ea8e  mov     rax, [rcx]
0x18000ea91  lea     r8, [rbp+57h+var_90]
0x18000ea95  lea     rdx, PKEY_SWD_DeviceInstanceId
0x18000ea9c  mov     rax, [rax+30h]
0x18000eaa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eaa5  nop
0x18000eaa6  lea     rcx, [rbp+57h+var_A0]
0x18000eaaa  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000eaaf  mov     eax, ebx
0x18000eab1  jmp     loc_18000E9EA
0x18000eab6  mov     rcx, [rbp+5Fh]; this
0x18000eaba  mov     rdx, [rdi+8]
0x18000eabe  mov     [rsp+0D0h+var_A8], rdx; char *
0x18000eac3  lea     rax, aFailedToSetThe; "Failed to set the device interface id f"...
0x18000eaca  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18000eacf  mov     r9d, ebx; char *
0x18000ead2  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x18000ead9  mov     edx, 8E6h; void *
0x18000eade  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000eae3  nop
0x18000eae4  cmp     [rbp+57h+var_98], 0
0x18000eae8  jz      short loc_18000EB2E
0x18000eaea  xorps   xmm0, xmm0
0x18000eaed  xor     eax, eax
0x18000eaef  movups  [rbp+57h+var_90], xmm0
0x18000eaf3  mov     [rbp+57h+var_80], rax
0x18000eaf7  mov     rcx, [rbp+57h+var_A0]
0x18000eafb  mov     rax, [rcx]
0x18000eafe  lea     r8, [rbp+57h+var_90]
0x18000eb02  lea     rdx, PKEY_SWD_DeviceInterfaceId
0x18000eb09  mov     rax, [rax+30h]
0x18000eb0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb12  mov     rcx, [rbp+57h+var_A0]
0x18000eb16  mov     rax, [rcx]
0x18000eb19  lea     r8, [rbp+57h+var_90]
0x18000eb1d  lea     rdx, PKEY_SWD_DeviceInstanceId
0x18000eb24  mov     rax, [rax+30h]
0x18000eb28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb2d  nop
0x18000eb2e  lea     rcx, [rbp+57h+var_A0]
0x18000eb32  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000eb37  mov     eax, ebx
0x18000eb39  jmp     loc_18000E9EA
0x18000eb3e  mov     rcx, [rbp+5Fh]; this
0x18000eb42  mov     r9d, ebx; char *
0x18000eb45  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x18000eb4c  mov     edx, 8E9h; void *
0x18000eb51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000eb56  nop
0x18000eb57  cmp     [rbp+57h+var_98], 0
0x18000eb5b  jz      short loc_18000EBA1
0x18000eb5d  xorps   xmm0, xmm0
0x18000eb60  xor     eax, eax
0x18000eb62  movups  [rbp+57h+var_90], xmm0
0x18000eb66  mov     [rbp+57h+var_80], rax
0x18000eb6a  mov     rcx, [rbp+57h+var_A0]
0x18000eb6e  mov     rax, [rcx]
0x18000eb71  lea     r8, [rbp+57h+var_90]
0x18000eb75  lea     rdx, PKEY_SWD_DeviceInterfaceId
0x18000eb7c  mov     rax, [rax+30h]
0x18000eb80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb85  mov     rcx, [rbp+57h+var_A0]
0x18000eb89  mov     rax, [rcx]
0x18000eb8c  lea     r8, [rbp+57h+var_90]
0x18000eb90  lea     rdx, PKEY_SWD_DeviceInstanceId
0x18000eb97  mov     rax, [rax+30h]
0x18000eb9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eba0  nop
0x18000eba1  lea     rcx, [rbp+57h+var_A0]
0x18000eba5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ebaa  mov     eax, ebx
0x18000ebac  jmp     loc_18000E9EA
0x18000ebb1  mov     rcx, [rbp+5Fh]; this
0x18000ebb5  mov     r9d, ebx; char *
0x18000ebb8  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x18000ebbf  mov     edx, 8EFh; void *
0x18000ebc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ebc9  nop
0x18000ebca  cmp     [rbp+57h+var_98], 0
0x18000ebce  jz      short loc_18000EC14
0x18000ebd0  xorps   xmm0, xmm0
0x18000ebd3  xor     eax, eax
0x18000ebd5  movups  [rbp+57h+var_90], xmm0
0x18000ebd9  mov     [rbp+57h+var_80], rax
0x18000ebdd  mov     rcx, [rbp+57h+var_A0]
0x18000ebe1  mov     rax, [rcx]
0x18000ebe4  lea     r8, [rbp+57h+var_90]
0x18000ebe8  lea     rdx, PKEY_SWD_DeviceInterfaceId
0x18000ebef  mov     rax, [rax+30h]
0x18000ebf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebf8  mov     rcx, [rbp+57h+var_A0]
0x18000ebfc  mov     rax, [rcx]
0x18000ebff  lea     r8, [rbp+57h+var_90]
0x18000ec03  lea     rdx, PKEY_SWD_DeviceInstanceId
0x18000ec0a  mov     rax, [rax+30h]
0x18000ec0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec13  nop
0x18000ec14  lea     rcx, [rbp+57h+var_A0]
0x18000ec18  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ec1d  mov     eax, ebx
0x18000ec1f  jmp     loc_18000E9EA
0x18000ec24  movups  xmm0, cs:PKEY_SWD_EndpointId_Retained
0x18000ec2b  movups  [rbp+57h+var_58], xmm0
0x18000ec2f  mov     eax, cs:dword_18006FE48
0x18000ec35  mov     dword ptr [rbp+57h+var_48], eax
0x18000ec38  lea     r9, [rbp+57h+var_58]
0x18000ec3c  mov     r8d, 1
0x18000ec42  mov     rdx, [rdi+10h]
0x18000ec46  mov     rcx, [rdi+18h]
0x18000ec4a  call    cs:__imp_SwDeviceInterfacePropertySet
0x18000ec50  mov     ebx, eax
0x18000ec52  test    eax, eax
0x18000ec54  jns     short loc_18000ECC9
0x18000ec56  mov     rcx, [rbp+5Fh]; this
0x18000ec5a  mov     r9d, eax; char *
0x18000ec5d  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x18000ec64  mov     edx, 907h; void *
0x18000ec69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ec6e  nop
0x18000ec6f  cmp     [rbp+57h+var_98], 0
0x18000ec73  jz      short loc_18000ECB9
0x18000ec75  xorps   xmm0, xmm0
0x18000ec78  xor     eax, eax
0x18000ec7a  movups  [rbp+57h+var_90], xmm0
0x18000ec7e  mov     [rbp+57h+var_80], rax
0x18000ec82  mov     rcx, [rbp+57h+var_A0]
0x18000ec86  mov     rax, [rcx]
0x18000ec89  lea     r8, [rbp+57h+var_90]
0x18000ec8d  lea     rdx, PKEY_SWD_DeviceInterfaceId
0x18000ec94  mov     rax, [rax+30h]
  ... truncated ...
```
