# UsbDevice_CompleteConfigureEndpointRequest

- ea: `0x140030330`
- end: `0x1400304ba`
- name: `UsbDevice_CompleteConfigureEndpointRequest`
- size: `394`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14002ff50`

## callees

- `0x140030330`
- `0x1400304c0`
- `0x1400340ec`
- `0x140046070`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140030388`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140030388`

## pseudocode

```c
__int64 __fastcall UsbDevice_CompleteConfigureEndpointRequest(__int64 a1, int a2, int a3, int a4)
{
  int v5; // edi
  __int64 v6; // rbp
  _BYTE *v7; // rcx
  bool v8; // zf
  unsigned int v9; // esi

  if ( !*(_QWORD *)(a1 + 448) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sds(WPP_GLOBAL_Control->DeviceExtension, a2, a3, a4);
    if ( !KdRefreshDebuggerNotPresent() )
      __debugbreak();
  }
  v5 = *(_DWORD *)(a1 + 456);
  v6 = *(_QWORD *)(a1 + 448);
  if ( v5 == 259 )
    v5 = -1073741823;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_dqqd(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 72LL), *(unsigned __int8 *)(a1 + 143), a3, a4);
  v7 = *(_BYTE **)(a1 + 600);
  if ( v7 )
  {
    *(_BYTE *)(a1 + 578) = v7[80];
    *(_BYTE *)(a1 + 579) = v7[81];
    *(_BYTE *)(a1 + 580) = v7[82];
  }
  *(_DWORD *)(a1 + 584) = v5;
  v8 = *(_BYTE *)(a1 + 440) == 0;
  v9 = v5;
  *(_DWORD *)(a1 + 608) = 0;
  if ( !v8 )
    v9 = 0;
  *(_QWORD *)(a1 + 448) = 0;
  *(_QWORD *)(a1 + 600) = 0;
  *(_DWORD *)(a1 + 456) = -1073741823;
  *(_BYTE *)(a1 + 440) = 0;
  *(_BYTE *)(a1 + 460) = 0;
  if ( ((__int64)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc & 2) != 0 )
    McTemplateK0ppqqqq_EtwWriteTransfer(
      *(unsigned __int8 *)(a1 + 579),
      a2,
      a3,
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL),
      *(_QWORD *)a1,
      *(_BYTE *)(a1 + 578),
      *(_BYTE *)(a1 + 579),
      *(_BYTE *)(a1 + 580),
      v5);
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01033 + 2104))(
           WdfDriverGlobals,
           v6,
           v9);
}

```

## disassembly

```asm
0x140030330  push    rbx
0x140030332  push    rbp
0x140030333  push    rsi
0x140030334  push    rdi
0x140030335  push    r15
0x140030337  sub     rsp, 50h
0x14003033b  cmp     qword ptr [rcx+1C0h], 0
0x140030343  lea     rsi, WPP_RECORDER_INITIALIZED
0x14003034a  mov     rbx, rcx
0x14003034d  jnz     short loc_140030399
0x14003034f  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140030356  jz      short loc_140030388
0x140030358  mov     rcx, cs:WPP_GLOBAL_Control
0x14003035f  lea     rax, aUnexpectedWdfr; "Unexpected WdfRequest value"
0x140030366  mov     [rsp+78h+var_40], rax
0x14003036b  lea     rax, aOnecoreDrivers_17; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x140030372  mov     dword ptr [rsp+78h+var_48], 0AC1h
0x14003037a  mov     [rsp+78h+var_50], rax
0x14003037f  mov     rcx, [rcx+40h]
0x140030383  call    WPP_RECORDER_SF_sds
0x140030388  call    cs:__imp_KdRefreshDebuggerNotPresent
0x14003038f  nop     dword ptr [rax+rax+00h]
0x140030394  test    al, al
0x140030396  jnz     short loc_140030399
0x140030398  int     3; Trap to Debugger
0x140030399  mov     edi, [rbx+1C8h]
0x14003039f  mov     r15d, 0C0000001h
0x1400303a5  mov     rbp, [rbx+1C0h]
0x1400303ac  cmp     edi, 103h
0x1400303b2  cmovz   edi, r15d
0x1400303b6  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x1400303bd  jz      short loc_1400303E8
0x1400303bf  mov     rcx, [rbx+8]
0x1400303c3  mov     rax, [rbx]
0x1400303c6  movzx   edx, byte ptr [rbx+8Fh]
0x1400303cd  mov     [rsp+78h+var_38], edi
0x1400303d1  mov     rcx, [rcx+48h]
0x1400303d5  mov     [rsp+78h+var_40], rax
0x1400303da  mov     [rsp+78h+var_48], rbp
0x1400303df  mov     dword ptr [rsp+78h+var_50], edx
0x1400303e3  call    WPP_RECORDER_SF_dqqd
0x1400303e8  mov     rcx, [rbx+258h]
0x1400303ef  test    rcx, rcx
0x1400303f2  jz      short loc_14003040F
0x1400303f4  mov     al, [rcx+50h]
0x1400303f7  mov     [rbx+242h], al
0x1400303fd  mov     al, [rcx+51h]
0x140030400  mov     [rbx+243h], al
0x140030406  mov     al, [rcx+52h]
0x140030409  mov     [rbx+244h], al
0x14003040f  xor     eax, eax
0x140030411  mov     [rbx+248h], edi
0x140030417  cmp     [rbx+1B8h], al
0x14003041d  mov     esi, edi
0x14003041f  mov     [rbx+260h], eax
0x140030425  cmovnz  esi, eax
0x140030428  mov     [rbx+1C0h], rax
0x14003042f  mov     [rbx+258h], rax
0x140030436  mov     [rbx+1C8h], r15d
0x14003043d  mov     [rbx+1B8h], al
0x140030443  mov     [rbx+1CCh], al
0x140030449  test    byte ptr cs:WPP_MAIN_CB.Queue+40h, 2
0x140030450  jz      short loc_14003048E
0x140030452  movzx   eax, byte ptr [rbx+244h]
0x140030459  mov     r9, [rbx+8]
0x14003045d  movzx   ecx, byte ptr [rbx+243h]
0x140030464  movzx   r10d, byte ptr [rbx+242h]
0x14003046c  mov     [rsp+78h+var_38], edi
0x140030470  mov     r9, [r9+8]
0x140030474  mov     dword ptr [rsp+78h+var_40], eax
0x140030478  mov     rax, [rbx]
0x14003047b  mov     dword ptr [rsp+78h+var_48], ecx
0x14003047f  mov     dword ptr [rsp+78h+var_50], r10d
0x140030484  mov     [rsp+78h+var_58], rax
0x140030489  call    McTemplateK0ppqqqq_EtwWriteTransfer
0x14003048e  mov     rax, cs:WdfFunctions_01033
0x140030495  mov     r8d, esi
0x140030498  mov     rcx, cs:WdfDriverGlobals
0x14003049f  mov     rdx, rbp
0x1400304a2  mov     rax, [rax+838h]
0x1400304a9  call    _guard_dispatch_icall
0x1400304ae  add     rsp, 50h
0x1400304b2  pop     r15
0x1400304b4  pop     rdi
0x1400304b5  pop     rsi
0x1400304b6  pop     rbp
0x1400304b7  pop     rbx
0x1400304b8  retn
```
