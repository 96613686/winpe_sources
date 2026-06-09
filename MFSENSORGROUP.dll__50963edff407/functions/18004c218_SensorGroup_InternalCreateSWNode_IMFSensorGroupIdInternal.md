# SensorGroup::InternalCreateSWNode(IMFSensorGroupIdInternal *)

- ea: `0x18004c218`
- end: `0x18004c4c6`
- name: `?InternalCreateSWNode@SensorGroup@@IEAAJPEAUIMFSensorGroupIdInternal@@@Z`
- size: `686`
- prototype: `__int64 __fastcall(SensorGroup *__hidden this, struct IMFSensorGroupIdInternal *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18003824c`

## callees

- `0x180005fa0`
- `0x1800313f8`
- `0x180037d70`
- `0x180044b28`
- `0x180045900`
- `0x18004c218`
- `0x180077010`

## import_xrefs

- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18004c411`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18004c411`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18004c45b`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18004c45b`

## pseudocode

```c
__int64 __fastcall SensorGroup::InternalCreateSWNode(SensorGroup *this, struct IMFSensorGroupIdInternal *a2)
{
  const char *v4; // rax
  int v5; // ebx
  __int64 v6; // rdx
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rax
  void (__fastcall *v10)(SensorGroup *); // rax
  __int64 v11; // rdx
  void *Block; // [rsp+40h] [rbp-29h] BYREF
  int v14; // [rsp+50h] [rbp-19h] BYREF
  __int64 v15; // [rsp+58h] [rbp-11h]
  const wchar_t *v16; // [rsp+60h] [rbp-9h]
  const wchar_t *v17; // [rsp+68h] [rbp-1h]
  __int64 v18; // [rsp+70h] [rbp+7h]
  int v19; // [rsp+78h] [rbp+Fh]
  const wchar_t *v20; // [rsp+80h] [rbp+17h]
  __int64 v21; // [rsp+88h] [rbp+1Fh]
  __int64 v22; // [rsp+90h] [rbp+27h]
  unsigned int v23; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 v24; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v25; // [rsp+E8h] [rbp+7Fh] BYREF

  memset_0(&v14, 0, 0x48u);
  v24 = 0;
  Block = 0;
  v23 = 0;
  v25 = 0;
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    v4 = "enable";
    if ( *((_DWORD *)this + 46) != 1 )
      v4 = "disable";
    WPP_SF_qs(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      276,
      (unsigned int)&WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids,
      (_DWORD)this,
      (__int64)v4);
  }
  if ( !a2 )
  {
    v5 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_24;
    v6 = 277;
    goto LABEL_8;
  }
  v7 = (*(__int64 (__fastcall **)(struct IMFSensorGroupIdInternal *, __int64, _QWORD, __int64 *, _QWORD))(*(_QWORD *)a2 + 192LL))(
         a2,
         13,
         0,
         &v25,
         0);
  v5 = v7;
  if ( v7 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_24;
    v8 = 278;
    goto LABEL_13;
  }
  if ( !v25 )
  {
    v5 = -1072875850;
    if ( !g_wppLevels )
      goto LABEL_24;
    v6 = 279;
    goto LABEL_8;
  }
  v7 = SensorGroupId::CreateDevPropertyArray((__int64 *)a2, &Block, &v23);
  v5 = v7;
  if ( v7 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_24;
    v8 = 280;
LABEL_13:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this, v7);
    goto LABEL_24;
  }
  v15 = v25;
  v16 = L"SGDEVAPI\\SensorGroup";
  v17 = L"SensorGroup";
  v20 = L"Media Foundation Sensor Group";
  v22 = *((_QWORD *)this + 17);
  v9 = *(_QWORD *)this;
  v14 = 72;
  v18 = 0;
  v19 = 6;
  v10 = *(void (__fastcall **)(SensorGroup *))(v9 + 8);
  v21 = 0;
  v10(this);
  v5 = SwDeviceCreate(L"SGDEVAPI", L"HTREE\\ROOT\\0", &v14, v23, Block, SensorGroup::SWDeviceCreateCallback, this, &v24);
  if ( v5 >= 0 )
  {
    *((_QWORD *)this + 19) = v24;
    v24 = 0;
    goto LABEL_24;
  }
  (*(void (__fastcall **)(SensorGroup *))(*(_QWORD *)this + 16LL))(this);
  if ( !g_wppLevels )
    goto LABEL_24;
  v6 = 281;
LABEL_8:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this, v5);
LABEL_24:
  if ( v24 )
  {
    SwDeviceClose();
    v24 = 0;
  }
  if ( v5 >= 0 )
  {
    if ( (unsigned __int8)byte_18008D62D < 8u )
      goto LABEL_32;
    v11 = 283;
  }
  else
  {
    if ( !byte_18008D62D )
      goto LABEL_32;
    v11 = 282;
  }
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v11, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this, v5);
LABEL_32:
  if ( Block )
    operator delete(Block);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004c218  push    rbp
0x18004c21a  push    rbx
0x18004c21b  push    rsi
0x18004c21c  push    rdi
0x18004c21d  push    r12
0x18004c21f  lea     rbp, [rsp-37h]
0x18004c224  sub     rsp, 0A0h
0x18004c22b  mov     rsi, rdx
0x18004c22e  mov     rdi, rcx
0x18004c231  xor     edx, edx; Val
0x18004c233  lea     rcx, [rbp+57h+var_70]; void *
0x18004c237  lea     r8d, [rdx+48h]; Size
0x18004c23b  call    memset_0
0x18004c240  mov     [rbp+57h+arg_10], 0
0x18004c248  mov     [rbp+57h+Block], 0
0x18004c250  mov     [rbp+57h+arg_8], 0
0x18004c257  mov     [rbp+57h+arg_18], 0
0x18004c25f  cmp     cs:byte_18008D62D, 8
0x18004c266  lea     r12, WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids
0x18004c26d  jb      short loc_18004C2AB
0x18004c26f  cmp     dword ptr [rdi+0B8h], 1
0x18004c276  lea     rcx, aDisable; "disable"
0x18004c27d  lea     rax, aEnable; "enable"
0x18004c284  mov     edx, 114h
0x18004c289  cmovnz  rax, rcx
0x18004c28d  mov     r9, rdi
0x18004c290  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c297  mov     r8, r12
0x18004c29a  mov     [rsp+0C0h+var_A0], rax
0x18004c29f  mov     rcx, [rcx+0D8h]
0x18004c2a6  call    WPP_SF_qs
0x18004c2ab  test    rsi, rsi
0x18004c2ae  jnz     short loc_18004C2E6
0x18004c2b0  mov     ebx, 80070057h
0x18004c2b5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004c2bc  jb      loc_18004C452
0x18004c2c2  mov     edx, 115h
0x18004c2c7  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x18004c2cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c2d2  mov     r9, rdi
0x18004c2d5  mov     r8, r12
0x18004c2d8  mov     rcx, [rcx+10h]
0x18004c2dc  call    WPP_SF_qD
0x18004c2e1  jmp     loc_18004C452
0x18004c2e6  mov     rax, [rsi]
0x18004c2e9  lea     r9, [rbp+57h+arg_18]
0x18004c2ed  xor     r8d, r8d
0x18004c2f0  mov     [rsp+0C0h+var_A0], 0
0x18004c2f9  mov     rcx, rsi
0x18004c2fc  mov     rax, [rax+0C0h]
0x18004c303  lea     edx, [r8+0Dh]
0x18004c307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c30c  mov     ebx, eax
0x18004c30e  test    eax, eax
0x18004c310  jns     short loc_18004C32A
0x18004c312  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004c319  jb      loc_18004C452
0x18004c31f  mov     edx, 116h
0x18004c324  mov     dword ptr [rsp+0C0h+var_A0], eax
0x18004c328  jmp     short loc_18004C2CB
0x18004c32a  cmp     [rbp+57h+arg_18], 0
0x18004c32f  jnz     short loc_18004C34D
0x18004c331  mov     ebx, 0C00D36B6h
0x18004c336  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004c33d  jb      loc_18004C452
0x18004c343  mov     edx, 117h
0x18004c348  jmp     loc_18004C2C7
0x18004c34d  lea     r8, [rbp+57h+arg_8]
0x18004c351  mov     rcx, rsi
0x18004c354  lea     rdx, [rbp+57h+Block]
0x18004c358  call    ?CreateDevPropertyArray@SensorGroupId@@SAJPEAUIMFSensorGroupIdInternal@@AEAV?$unique_ptr@$$BY0A@U_DEVPROPERTY@@U?$default_delete@$$BY0A@U_DEVPROPERTY@@@wistd@@@wistd@@PEAK@Z; SensorGroupId::CreateDevPropertyArray(IMFSensorGroupIdInternal *,wistd::unique_ptr<_DEVPROPERTY [0],wistd::default_delete<_DEVPROPERTY [0]>> &,ulong *)
0x18004c35d  mov     ebx, eax
0x18004c35f  test    eax, eax
0x18004c361  jns     short loc_18004C377
0x18004c363  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004c36a  jb      loc_18004C452
0x18004c370  mov     edx, 118h
0x18004c375  jmp     short loc_18004C324
0x18004c377  mov     rax, [rbp+57h+arg_18]
0x18004c37b  mov     rcx, rdi
0x18004c37e  mov     [rbp+57h+var_68], rax
0x18004c382  lea     rax, aSgdevapiSensor; "SGDEVAPI\\SensorGroup"
0x18004c389  mov     [rbp+57h+var_60], rax
0x18004c38d  lea     rax, aSensorgroup; "SensorGroup"
0x18004c394  mov     [rbp+57h+var_58], rax
0x18004c398  lea     rax, aMediaFoundatio; "Media Foundation Sensor Group"
0x18004c39f  mov     [rbp+57h+var_40], rax
0x18004c3a3  mov     rax, [rdi+88h]
0x18004c3aa  mov     [rbp+57h+var_30], rax
0x18004c3ae  mov     rax, [rdi]
0x18004c3b1  mov     [rbp+57h+var_70], 48h ; 'H'
0x18004c3b8  mov     [rbp+57h+var_50], 0
0x18004c3c0  mov     [rbp+57h+var_48], 6
0x18004c3c7  mov     rax, [rax+8]
0x18004c3cb  mov     [rbp+57h+var_38], 0
0x18004c3d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c3d8  mov     r9d, [rbp+57h+arg_8]
0x18004c3dc  lea     rax, [rbp+57h+arg_10]
0x18004c3e0  mov     [rsp+0C0h+var_88], rax
0x18004c3e5  lea     r8, [rbp+57h+var_70]
0x18004c3e9  lea     rax, ?SWDeviceCreateCallback@SensorGroup@@KAXPEAUHSWDEVICE__@@JPEAXPEBG@Z; SensorGroup::SWDeviceCreateCallback(HSWDEVICE__ *,long,void *,ushort const *)
0x18004c3f0  mov     [rsp+0C0h+var_90], rdi
0x18004c3f5  mov     [rsp+0C0h+var_98], rax
0x18004c3fa  lea     rdx, aHtreeRoot0; "HTREE\\ROOT\\0"
0x18004c401  mov     rax, [rbp+57h+Block]
0x18004c405  lea     rcx, aSgdevapi; "SGDEVAPI"
0x18004c40c  mov     [rsp+0C0h+var_A0], rax
0x18004c411  call    cs:__imp_SwDeviceCreate
0x18004c417  mov     ebx, eax
0x18004c419  test    eax, eax
0x18004c41b  jns     short loc_18004C43F
0x18004c41d  mov     rax, [rdi]
0x18004c420  mov     rcx, rdi
0x18004c423  mov     rax, [rax+10h]
0x18004c427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c42c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004c433  jb      short loc_18004C452
0x18004c435  mov     edx, 119h
0x18004c43a  jmp     loc_18004C2C7
0x18004c43f  mov     rax, [rbp+57h+arg_10]
0x18004c443  mov     [rdi+98h], rax
0x18004c44a  mov     [rbp+57h+arg_10], 0
0x18004c452  mov     rcx, [rbp+57h+arg_10]
0x18004c456  test    rcx, rcx
0x18004c459  jz      short loc_18004C469
0x18004c45b  call    cs:__imp_SwDeviceClose
0x18004c461  mov     [rbp+57h+arg_10], 0
0x18004c469  test    ebx, ebx
0x18004c46b  jns     short loc_18004C47D
0x18004c46d  cmp     cs:byte_18008D62D, 1
0x18004c474  jb      short loc_18004C4A8
0x18004c476  mov     edx, 11Ah
0x18004c47b  jmp     short loc_18004C48B
0x18004c47d  cmp     cs:byte_18008D62D, 8
0x18004c484  jb      short loc_18004C4A8
0x18004c486  mov     edx, 11Bh
0x18004c48b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c492  mov     r9, rdi
0x18004c495  mov     r8, r12
0x18004c498  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x18004c49c  mov     rcx, [rcx+0D8h]
0x18004c4a3  call    WPP_SF_qD
0x18004c4a8  mov     rcx, [rbp+57h+Block]; Block
0x18004c4ac  test    rcx, rcx
0x18004c4af  jz      short loc_18004C4B6
0x18004c4b1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004c4b6  mov     eax, ebx
0x18004c4b8  add     rsp, 0A0h
0x18004c4bf  pop     r12
0x18004c4c1  pop     rdi
0x18004c4c2  pop     rsi
0x18004c4c3  pop     rbx
0x18004c4c4  pop     rbp
0x18004c4c5  retn
```
