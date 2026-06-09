# BthIoctlSetServiceEvents

- ea: `0x140007154`
- end: `0x140007471`
- name: `BthIoctlSetServiceEvents`
- size: `797`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140029170`

## callees

- `0x1400041d0`
- `0x140007154`
- `0x14001a258`
- `0x14001ae00`
- `0x14002ae68`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000727f`
- `ntoskrnl!ObfDereferenceObject` at `0x14000729b`
- `ntoskrnl!ObfDereferenceObject` at `0x14000727f`
- `ntoskrnl!ObfDereferenceObject` at `0x14000729b`
- `btampm!BtaMpmConnectionRequest` at `0x1400073ac`
- `btampm!BtaMpmConnectionRequest` at `0x1400073ac`

## pseudocode

```c
__int64 __fastcall BthIoctlSetServiceEvents(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rax
  __int64 v5; // rdx
  __int64 v6; // r8
  _QWORD *v7; // rbx
  __int64 v9; // rax
  __int64 v10; // rdi
  void *v11; // rcx
  __int64 v12; // rax
  int v13; // edx
  int v14; // r8d
  __int64 v15; // rbx
  __int64 v16; // rcx

  v4 = (_QWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                   WdfDriverGlobals,
                   a2,
                   off_140022088);
  v7 = v4;
  if ( v4 )
  {
    if ( *v4 && v4[1] )
    {
      v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2216))(WdfDriverGlobals, a2);
      v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
              WdfDriverGlobals,
              v9,
              off_140022128);
      if ( *(_QWORD *)v10 )
      {
        ObfDereferenceObject(*(PVOID *)v10);
        *(_QWORD *)v10 = 0;
      }
      v11 = *(void **)(v10 + 8);
      if ( v11 )
      {
        ObfDereferenceObject(v11);
        *(_QWORD *)(v10 + 8) = 0;
      }
      *(_QWORD *)v10 = *v7;
      v12 = v7[1];
      *v7 = 0;
      *(_QWORD *)(v10 + 8) = v12;
      v7[1] = 0;
      if ( (unsigned int)Bus_IsAutoConnectionDisabled() )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          LOBYTE(v13) = 0;
        }
        else
        {
          v13 = 1;
        }
        if ( (_BYTE)v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_(
            WPP_GLOBAL_Control->AttachedDevice,
            v13,
            v14,
            WPP_GLOBAL_Control->DeviceExtension,
            4,
            2,
            23,
            (__int64)WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids);
        }
      }
      else
      {
        v15 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                WdfDriverGlobals,
                a1,
                off_1400220B0);
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 2504))(
          WdfDriverGlobals,
          *(_QWORD *)(v15 + 328),
          0);
        v16 = *(_QWORD *)(v15 + 184);
        if ( v16 )
          BtaMpmConnectionRequest(v16, 1, 1);
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2512))(
          WdfDriverGlobals,
          *(_QWORD *)(v15 + 328));
      }
      return 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        LOBYTE(v5) = 0;
      }
      else
      {
        v5 = 1;
      }
      LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          v5,
          v6,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          4,
          22,
          (__int64)WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids);
      MicrosoftTelemetryAssertTriggeredMsgKM("IOCTL_BUSENUM_SET_EVENT_HANDLES handles were not referenced.", v5, v6);
      return 3221225485LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      LOBYTE(v5) = 0;
    }
    else
    {
      v5 = 1;
    }
    LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v5,
        v6,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        4,
        21,
        (__int64)WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids);
    MicrosoftTelemetryAssertTriggeredMsgKM("IOCTL_BUSENUM_SET_EVENT_HANDLES does not have request context set.", v5, v6);
    return 3221225488LL;
  }
}

```

## disassembly

```asm
0x140007154  mov     [rsp+arg_0], rbx
0x140007159  mov     [rsp+arg_8], rsi
0x14000715e  push    rdi
0x14000715f  sub     rsp, 40h
0x140007163  mov     rax, cs:WdfFunctions_01015
0x14000716a  mov     rsi, rcx
0x14000716d  mov     r8, cs:off_140022088
0x140007174  mov     rdi, rdx
0x140007177  mov     rcx, cs:WdfDriverGlobals
0x14000717e  mov     rax, [rax+650h]
0x140007185  call    _guard_dispatch_icall
0x14000718a  mov     rbx, rax
0x14000718d  test    rax, rax
0x140007190  jnz     loc_14000721B
0x140007196  mov     rcx, cs:WPP_GLOBAL_Control
0x14000719d  lea     rax, WPP_GLOBAL_Control
0x1400071a4  cmp     rcx, rax
0x1400071a7  jz      short loc_1400071BB
0x1400071a9  mov     eax, [rcx+2Ch]
0x1400071ac  test    al, 8
0x1400071ae  jz      short loc_1400071BB
0x1400071b0  cmp     byte ptr [rcx+29h], 2
0x1400071b4  jb      short loc_1400071BB
0x1400071b6  lea     edx, [rbx+1]
0x1400071b9  jmp     short loc_1400071BD
0x1400071bb  xor     dl, dl
0x1400071bd  lea     rax, WPP_RECORDER_INITIALIZED
0x1400071c4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400071cb  setnz   r8b
0x1400071cf  test    dl, dl
0x1400071d1  jnz     short loc_1400071D8
0x1400071d3  test    r8b, r8b
0x1400071d6  jz      short loc_140007205
0x1400071d8  mov     r9, [rcx+40h]
0x1400071dc  lea     rax, WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids
0x1400071e3  mov     rcx, [rcx+18h]
0x1400071e7  mov     [rsp+48h+var_10], rax
0x1400071ec  mov     [rsp+48h+var_18], 15h
0x1400071f3  mov     [rsp+48h+var_20], 4
0x1400071fb  mov     [rsp+48h+var_28], 2
0x140007200  call    WPP_RECORDER_AND_TRACE_SF_
0x140007205  lea     rcx, aIoctlBusenumSe; "IOCTL_BUSENUM_SET_EVENT_HANDLES does no"...
0x14000720c  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140007211  mov     eax, 0C0000010h
0x140007216  jmp     loc_140007460
0x14000721b  cmp     qword ptr [rax], 0
0x14000721f  jz      loc_1400073DE
0x140007225  cmp     qword ptr [rax+8], 0
0x14000722a  jz      loc_1400073DE
0x140007230  mov     rax, cs:WdfFunctions_01015
0x140007237  mov     rdx, rdi
0x14000723a  mov     rcx, cs:WdfDriverGlobals
0x140007241  mov     rax, [rax+8A8h]
0x140007248  call    _guard_dispatch_icall
0x14000724d  mov     rcx, cs:WdfFunctions_01015
0x140007254  mov     rdx, rax
0x140007257  mov     r8, cs:off_140022128
0x14000725e  mov     r9, [rcx+650h]
0x140007265  mov     rcx, cs:WdfDriverGlobals
0x14000726c  mov     rax, r9
0x14000726f  call    _guard_dispatch_icall
0x140007274  mov     rdi, rax
0x140007277  mov     rcx, [rax]; Object
0x14000727a  test    rcx, rcx
0x14000727d  jz      short loc_140007292
0x14000727f  call    cs:__imp_ObfDereferenceObject
0x140007286  nop     dword ptr [rax+rax+00h]
0x14000728b  mov     qword ptr [rdi], 0
0x140007292  mov     rcx, [rdi+8]; Object
0x140007296  test    rcx, rcx
0x140007299  jz      short loc_1400072AF
0x14000729b  call    cs:__imp_ObfDereferenceObject
0x1400072a2  nop     dword ptr [rax+rax+00h]
0x1400072a7  mov     qword ptr [rdi+8], 0
0x1400072af  mov     rax, [rbx]
0x1400072b2  mov     [rdi], rax
0x1400072b5  mov     rax, [rbx+8]
0x1400072b9  mov     qword ptr [rbx], 0
0x1400072c0  mov     [rdi+8], rax
0x1400072c4  mov     qword ptr [rbx+8], 0
0x1400072cc  call    Bus_IsAutoConnectionDisabled
0x1400072d1  test    eax, eax
0x1400072d3  jz      short loc_14000734D
0x1400072d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400072dc  lea     rax, WPP_GLOBAL_Control
0x1400072e3  cmp     rcx, rax
0x1400072e6  jz      short loc_1400072FC
0x1400072e8  mov     eax, [rcx+2Ch]
0x1400072eb  test    al, 2
0x1400072ed  jz      short loc_1400072FC
0x1400072ef  cmp     byte ptr [rcx+29h], 4
0x1400072f3  jb      short loc_1400072FC
0x1400072f5  mov     edx, 1
0x1400072fa  jmp     short loc_1400072FE
0x1400072fc  xor     dl, dl
0x1400072fe  lea     rax, WPP_RECORDER_INITIALIZED
0x140007305  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000730c  setnz   r8b
0x140007310  test    dl, dl
0x140007312  jnz     short loc_140007319
0x140007314  test    r8b, r8b
0x140007317  jz      short loc_140007346
0x140007319  mov     r9, [rcx+40h]
0x14000731d  lea     rax, WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids
0x140007324  mov     rcx, [rcx+18h]
0x140007328  mov     [rsp+48h+var_10], rax
0x14000732d  mov     [rsp+48h+var_18], 17h
0x140007334  mov     [rsp+48h+var_20], 2
0x14000733c  mov     [rsp+48h+var_28], 4
0x140007341  call    WPP_RECORDER_AND_TRACE_SF_
0x140007346  xor     eax, eax
0x140007348  jmp     loc_140007460
0x14000734d  mov     rax, cs:WdfFunctions_01015
0x140007354  mov     rdx, rsi
0x140007357  mov     r8, cs:off_1400220B0
0x14000735e  mov     rcx, cs:WdfDriverGlobals
0x140007365  mov     rax, [rax+650h]
0x14000736c  call    _guard_dispatch_icall
0x140007371  mov     rcx, cs:WdfFunctions_01015
0x140007378  mov     rbx, rax
0x14000737b  xor     r8d, r8d
0x14000737e  mov     rax, [rcx+9C8h]
0x140007385  mov     rcx, cs:WdfDriverGlobals
0x14000738c  mov     rdx, [rbx+148h]
0x140007393  call    _guard_dispatch_icall
0x140007398  mov     rcx, [rbx+0B8h]
0x14000739f  test    rcx, rcx
0x1400073a2  jz      short loc_1400073B8
0x1400073a4  mov     edx, 1
0x1400073a9  mov     r8d, edx
0x1400073ac  call    cs:__imp_BtaMpmConnectionRequest
0x1400073b3  nop     dword ptr [rax+rax+00h]
0x1400073b8  mov     rax, cs:WdfFunctions_01015
0x1400073bf  mov     rdx, [rbx+148h]
0x1400073c6  mov     rcx, cs:WdfDriverGlobals
0x1400073cd  mov     rax, [rax+9D0h]
0x1400073d4  call    _guard_dispatch_icall
0x1400073d9  jmp     loc_140007346
0x1400073de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400073e5  lea     rax, WPP_GLOBAL_Control
0x1400073ec  cmp     rcx, rax
0x1400073ef  jz      short loc_140007405
0x1400073f1  mov     eax, [rcx+2Ch]
0x1400073f4  test    al, 8
0x1400073f6  jz      short loc_140007405
0x1400073f8  cmp     byte ptr [rcx+29h], 2
0x1400073fc  jb      short loc_140007405
0x1400073fe  mov     edx, 1
0x140007403  jmp     short loc_140007407
0x140007405  xor     dl, dl
0x140007407  lea     rax, WPP_RECORDER_INITIALIZED
0x14000740e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007415  setnz   r8b
0x140007419  test    dl, dl
0x14000741b  jnz     short loc_140007422
0x14000741d  test    r8b, r8b
0x140007420  jz      short loc_14000744F
0x140007422  mov     r9, [rcx+40h]
0x140007426  lea     rax, WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids
0x14000742d  mov     rcx, [rcx+18h]
0x140007431  mov     [rsp+48h+var_10], rax
0x140007436  mov     [rsp+48h+var_18], 16h
0x14000743d  mov     [rsp+48h+var_20], 4
0x140007445  mov     [rsp+48h+var_28], 2
0x14000744a  call    WPP_RECORDER_AND_TRACE_SF_
0x14000744f  lea     rcx, aIoctlBusenumSe_0; "IOCTL_BUSENUM_SET_EVENT_HANDLES handles"...
0x140007456  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14000745b  mov     eax, 0C000000Dh
0x140007460  mov     rbx, [rsp+48h+arg_0]
0x140007465  mov     rsi, [rsp+48h+arg_8]
0x14000746a  add     rsp, 40h
0x14000746e  pop     rdi
0x14000746f  retn
```
