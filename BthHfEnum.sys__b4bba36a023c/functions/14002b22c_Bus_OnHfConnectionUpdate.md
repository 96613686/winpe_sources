# Bus_OnHfConnectionUpdate

- ea: `0x14002b22c`
- end: `0x14002b4da`
- name: `Bus_OnHfConnectionUpdate`
- size: `686`
- prototype: `__int64 __fastcall(WdfHelpers *this)`
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400037d0`
- `0x140007768`
- `0x140009ad4`

## callees

- `0x1400041d0`
- `0x14000a4d8`
- `0x14000aac0`
- `0x140013ae0`
- `0x14001ae00`
- `0x140029824`
- `0x14002b1bc`
- `0x14002b22c`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14002b438`
- `ntoskrnl!KeSetEvent` at `0x14002b438`
- `ntoskrnl!KeClearEvent` at `0x14002b425`
- `ntoskrnl!KeClearEvent` at `0x14002b425`
- `btampm!BtaMpmUpdateConnectionStatus` at `0x14002b407`
- `btampm!BtaMpmUpdateConnectionStatus` at `0x14002b407`

## pseudocode

```c
__int64 __fastcall Bus_OnHfConnectionUpdate(WdfHelpers *this, unsigned int a2)
{
  __int64 v3; // rdi
  int v4; // r8d
  __int64 v5; // rdx
  __int64 v6; // rbx
  int v7; // r8d
  PDEVICE_OBJECT *v8; // rdx
  char v9; // cl
  PDEVICE_OBJECT *v10; // rdx
  char v11; // cl
  int IsDeviceConnected; // ebx
  unsigned int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // r8
  struct _KEVENT *v16; // rcx
  unsigned int v18; // [rsp+88h] [rbp+10h] BYREF

  v18 = a2;
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WdfHelpers *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         this,
         off_1400220B0);
  Bus_SetIsConnectedProperty(this);
  v5 = *(_QWORD *)(v3 + 320);
  if ( v5 )
  {
    v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
           WdfDriverGlobals,
           v5,
           off_140022100);
    v8 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || (v9 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
    {
      v9 = 0;
    }
    if ( v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = v9;
      LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_DD(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v8,
        v7,
        WPP_GLOBAL_Control->DeviceExtension);
    }
    WdfIoQueueFindAndCompleteStatusIoctlRequest(*(_QWORD *)(v3 + 152), *(_QWORD *)(v3 + 320), 2228247, &v18, v6);
  }
  else
  {
    v10 = &WPP_GLOBAL_Control;
    v11 = 1;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || (LOBYTE(v10) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    {
      LOBYTE(v10) = 0;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || !LOWORD(WPP_GLOBAL_Control->DeviceType) )
      v11 = 0;
    if ( (_BYTE)v10 || v11 )
    {
      LOBYTE(v4) = v11;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v10,
        v4,
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        3,
        26,
        (__int64)WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids);
    }
  }
  IsDeviceConnected = Bus_IsDeviceConnected(this);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 2504))(
    WdfDriverGlobals,
    *(_QWORD *)(v3 + 328),
    0);
  v13 = v18;
  if ( v18 != IsDeviceConnected && *(_QWORD *)(v3 + 184) )
  {
    v14 = *(_QWORD *)(v3 + 184);
    v15 = (unsigned int)_InterlockedExchange((volatile __int32 *)(v3 + 180), 0);
    BtaMpmUpdateConnectionStatus(v14, v18, v15);
    v13 = v18;
  }
  v16 = (struct _KEVENT *)(v3 + 216);
  if ( v13 )
  {
    KeClearEvent(v16);
  }
  else
  {
    KeSetEvent(v16, 0, 0);
    if ( *(_QWORD *)(v3 + 368) )
    {
      if ( (*(unsigned int (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 2048))(WdfDriverGlobals) != -1073741536 )
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64))(WdfFunctions_01015 + 2104))(
          WdfDriverGlobals,
          *(_QWORD *)(v3 + 368),
          3221225860LL);
      *(_QWORD *)(v3 + 368) = 0;
    }
    ScoSetCodecId((__int64)this, 0);
    *(_DWORD *)(v3 + 376) = 0;
  }
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2512))(
           WdfDriverGlobals,
           *(_QWORD *)(v3 + 328));
}

```

## disassembly

```asm
0x14002b22c  mov     [rsp+arg_8], edx
0x14002b230  push    rbx
0x14002b231  push    rbp
0x14002b232  push    rsi
0x14002b233  push    rdi
0x14002b234  sub     rsp, 58h
0x14002b238  mov     rax, cs:WdfFunctions_01015
0x14002b23f  mov     rsi, rcx
0x14002b242  mov     r8, cs:off_1400220B0
0x14002b249  mov     rdx, rcx
0x14002b24c  mov     rcx, cs:WdfDriverGlobals
0x14002b253  mov     rax, [rax+650h]
0x14002b25a  call    _guard_dispatch_icall
0x14002b25f  mov     edx, [rsp+78h+arg_8]
0x14002b266  mov     rcx, rsi; this
0x14002b269  mov     rdi, rax
0x14002b26c  call    Bus_SetIsConnectedProperty
0x14002b271  mov     rdx, [rdi+140h]
0x14002b278  xor     ebp, ebp
0x14002b27a  test    rdx, rdx
0x14002b27d  jz      loc_14002B332
0x14002b283  mov     rcx, cs:WdfFunctions_01015
0x14002b28a  mov     r8, cs:off_140022100
0x14002b291  mov     rax, [rcx+650h]
0x14002b298  mov     rcx, cs:WdfDriverGlobals
0x14002b29f  call    _guard_dispatch_icall
0x14002b2a4  mov     rbx, rax
0x14002b2a7  mov     r10, cs:WPP_GLOBAL_Control
0x14002b2ae  lea     rdx, WPP_GLOBAL_Control
0x14002b2b5  cmp     r10, rdx
0x14002b2b8  jz      short loc_14002B2CC
0x14002b2ba  mov     ecx, [r10+2Ch]
0x14002b2be  test    cl, 4
0x14002b2c1  jz      short loc_14002B2CC
0x14002b2c3  cmp     byte ptr [r10+29h], 4
0x14002b2c8  mov     cl, 1
0x14002b2ca  jnb     short loc_14002B2CF
0x14002b2cc  mov     cl, bpl
0x14002b2cf  lea     rax, WPP_RECORDER_INITIALIZED
0x14002b2d6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002b2dd  setnz   r8b
0x14002b2e1  test    cl, cl
0x14002b2e3  jnz     short loc_14002B2EA
0x14002b2e5  test    r8b, r8b
0x14002b2e8  jz      short loc_14002B30A
0x14002b2ea  mov     eax, [rbx]
0x14002b2ec  mov     dl, cl
0x14002b2ee  mov     r9, [r10+40h]
0x14002b2f2  mov     rcx, [r10+18h]
0x14002b2f6  mov     [rsp+78h+var_30], eax
0x14002b2fa  mov     eax, [rsp+78h+arg_8]
0x14002b301  mov     [rsp+78h+var_38], eax
0x14002b305  call    WPP_RECORDER_AND_TRACE_SF_DD
0x14002b30a  mov     rdx, [rdi+140h]
0x14002b311  lea     r9, [rsp+78h+arg_8]
0x14002b319  mov     rcx, [rdi+98h]
0x14002b320  mov     r8d, 220017h
0x14002b326  mov     [rsp+78h+var_58], rbx
0x14002b32b  call    WdfIoQueueFindAndCompleteStatusIoctlRequest
0x14002b330  jmp     short loc_14002B3AD
0x14002b332  mov     r10, cs:WPP_GLOBAL_Control
0x14002b339  lea     rdx, WPP_GLOBAL_Control
0x14002b340  mov     cl, 1
0x14002b342  cmp     r10, rdx
0x14002b345  jz      short loc_14002B358
0x14002b347  mov     eax, [r10+2Ch]
0x14002b34b  test    al, 4
0x14002b34d  jz      short loc_14002B358
0x14002b34f  cmp     byte ptr [r10+29h], 5
0x14002b354  mov     dl, cl
0x14002b356  jnb     short loc_14002B35B
0x14002b358  mov     dl, bpl
0x14002b35b  lea     rax, WPP_RECORDER_INITIALIZED
0x14002b362  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002b369  jz      short loc_14002B372
0x14002b36b  cmp     [r10+48h], bp
0x14002b370  jnz     short loc_14002B375
0x14002b372  mov     cl, bpl
0x14002b375  test    dl, dl
0x14002b377  jnz     short loc_14002B37D
0x14002b379  test    cl, cl
0x14002b37b  jz      short loc_14002B3AD
0x14002b37d  mov     r9, [r10+40h]
0x14002b381  lea     rax, WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids
0x14002b388  mov     [rsp+78h+var_40], rax
0x14002b38d  mov     r8b, cl
0x14002b390  mov     rcx, [r10+18h]
0x14002b394  mov     [rsp+78h+var_48], 1Ah
0x14002b39b  mov     [rsp+78h+var_50], 3
0x14002b3a3  mov     byte ptr [rsp+78h+var_58], 5
0x14002b3a8  call    WPP_RECORDER_AND_TRACE_SF_
0x14002b3ad  mov     rcx, rsi
0x14002b3b0  call    Bus_IsDeviceConnected
0x14002b3b5  mov     rcx, cs:WdfFunctions_01015
0x14002b3bc  mov     ebx, eax
0x14002b3be  mov     rdx, [rdi+148h]
0x14002b3c5  xor     r8d, r8d
0x14002b3c8  mov     rax, [rcx+9C8h]
0x14002b3cf  mov     rcx, cs:WdfDriverGlobals
0x14002b3d6  call    _guard_dispatch_icall
0x14002b3db  mov     eax, [rsp+78h+arg_8]
0x14002b3e2  cmp     eax, ebx
0x14002b3e4  jz      short loc_14002B41A
0x14002b3e6  cmp     [rdi+0B8h], rbp
0x14002b3ed  jz      short loc_14002B41A
0x14002b3ef  mov     rcx, [rdi+0B8h]
0x14002b3f6  mov     r8d, ebp
0x14002b3f9  xchg    r8d, [rdi+0B4h]
0x14002b400  mov     edx, [rsp+78h+arg_8]
0x14002b407  call    cs:__imp_BtaMpmUpdateConnectionStatus
0x14002b40e  nop     dword ptr [rax+rax+00h]
0x14002b413  mov     eax, [rsp+78h+arg_8]
0x14002b41a  lea     rcx, [rdi+0D8h]; Event
0x14002b421  test    eax, eax
0x14002b423  jz      short loc_14002B433
0x14002b425  call    cs:__imp_KeClearEvent
0x14002b42c  nop     dword ptr [rax+rax+00h]
0x14002b431  jmp     short loc_14002B4AF
0x14002b433  xor     r8d, r8d; Wait
0x14002b436  xor     edx, edx; Increment
0x14002b438  call    cs:__imp_KeSetEvent
0x14002b43f  nop     dword ptr [rax+rax+00h]
0x14002b444  mov     rdx, [rdi+170h]
0x14002b44b  test    rdx, rdx
0x14002b44e  jz      short loc_14002B49F
0x14002b450  mov     rax, cs:WdfFunctions_01015
0x14002b457  mov     rcx, cs:WdfDriverGlobals
0x14002b45e  mov     rax, [rax+800h]
0x14002b465  call    _guard_dispatch_icall
0x14002b46a  cmp     eax, 0C0000120h
0x14002b46f  jz      short loc_14002B498
0x14002b471  mov     rax, cs:WdfFunctions_01015
0x14002b478  mov     r8d, 0C0000184h
0x14002b47e  mov     rdx, [rdi+170h]
0x14002b485  mov     rcx, cs:WdfDriverGlobals
0x14002b48c  mov     rax, [rax+838h]
0x14002b493  call    _guard_dispatch_icall
0x14002b498  mov     [rdi+170h], rbp
0x14002b49f  xor     edx, edx
0x14002b4a1  mov     rcx, rsi
0x14002b4a4  call    ScoSetCodecId
0x14002b4a9  mov     [rdi+178h], ebp
0x14002b4af  mov     rax, cs:WdfFunctions_01015
0x14002b4b6  mov     rdx, [rdi+148h]
0x14002b4bd  mov     rcx, cs:WdfDriverGlobals
0x14002b4c4  mov     rax, [rax+9D0h]
0x14002b4cb  call    _guard_dispatch_icall
0x14002b4d0  add     rsp, 58h
0x14002b4d4  pop     rdi
0x14002b4d5  pop     rsi
0x14002b4d6  pop     rbp
0x14002b4d7  pop     rbx
0x14002b4d8  retn
```
