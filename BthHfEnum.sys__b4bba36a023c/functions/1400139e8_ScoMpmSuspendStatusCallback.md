# ScoMpmSuspendStatusCallback

- ea: `0x1400139e8`
- end: `0x140013ad9`
- name: `ScoMpmSuspendStatusCallback`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140004160`

## callees

- `0x140004810`
- `0x14000c570`
- `0x140011484`
- `0x1400139e8`
- `0x14001ae00`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140013ac1`
- `ntoskrnl!KeSetEvent` at `0x140013ac1`

## pseudocode

```c
LONG __fastcall ScoMpmSuspendStatusCallback(__int64 a1, int a2)
{
  int v2; // edi
  __int64 v4; // rbx
  LONG result; // eax
  char v6; // [rsp+70h] [rbp+18h] BYREF

  v2 = a2;
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP(
      WPP_GLOBAL_Control->AttachedDevice,
      a2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      55,
      (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids,
      v2);
  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_140022150);
  wil::acquire_wdf_spin_lock(&v6, *(_QWORD *)(v4 + 368));
  *(_DWORD *)(v4 + 460) = v2;
  result = wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&void WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&void WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(&v6);
  if ( v2 )
    return KeSetEvent((PRKEVENT)(v4 + 304), 0, 0);
  return result;
}

```

## disassembly

```asm
0x1400139e8  mov     [rsp+arg_0], rbx
0x1400139ed  push    rdi
0x1400139ee  sub     rsp, 50h
0x1400139f2  mov     edi, edx
0x1400139f4  mov     rbx, rcx
0x1400139f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400139fe  lea     rax, WPP_GLOBAL_Control
0x140013a05  cmp     rcx, rax
0x140013a08  jz      short loc_140013A1B
0x140013a0a  mov     eax, [rcx+2Ch]
0x140013a0d  test    al, 10h
0x140013a0f  jz      short loc_140013A1B
0x140013a11  cmp     byte ptr [rcx+29h], 4
0x140013a15  jb      short loc_140013A1B
0x140013a17  mov     dl, 1
0x140013a19  jmp     short loc_140013A1D
0x140013a1b  xor     dl, dl
0x140013a1d  lea     rax, WPP_RECORDER_INITIALIZED
0x140013a24  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140013a2b  setnz   r8b
0x140013a2f  test    dl, dl
0x140013a31  jnz     short loc_140013A38
0x140013a33  test    r8b, r8b
0x140013a36  jz      short loc_140013A69
0x140013a38  mov     r9, [rcx+40h]
0x140013a3c  lea     rax, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x140013a43  mov     rcx, [rcx+18h]
0x140013a47  mov     [rsp+58h+var_18], edi
0x140013a4b  mov     [rsp+58h+var_20], rax
0x140013a50  mov     [rsp+58h+var_28], 37h ; '7'
0x140013a57  mov     [rsp+58h+var_30], 5
0x140013a5f  mov     [rsp+58h+var_38], 4
0x140013a64  call    WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP
0x140013a69  mov     rax, cs:WdfFunctions_01015
0x140013a70  mov     rdx, rbx
0x140013a73  mov     r8, cs:off_140022150
0x140013a7a  mov     rcx, cs:WdfDriverGlobals
0x140013a81  mov     rax, [rax+650h]
0x140013a88  call    _guard_dispatch_icall
0x140013a8d  lea     rcx, [rsp+58h+arg_10]
0x140013a92  mov     rbx, rax
0x140013a95  mov     rdx, [rax+170h]
0x140013a9c  call    ?acquire_wdf_spin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUWDFSPINLOCK__@@P6AXPEAU1@@Z$1?WdfSpinLockRelease@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAUWDFSPINLOCK__@@@Z; wil::acquire_wdf_spin_lock(WDFSPINLOCK__ *)
0x140013aa1  lea     rcx, [rsp+58h+arg_10]
0x140013aa6  mov     [rbx+1CCh], edi
0x140013aac  call    ??1?$unique_storage@U?$resource_policy@PEAUWDFSPINLOCK__@@P6AXPEAU1@@Z$1?WdfSpinLockRelease@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(void)
0x140013ab1  test    edi, edi
0x140013ab3  jz      short loc_140013ACD
0x140013ab5  lea     rcx, [rbx+130h]; Event
0x140013abc  xor     r8d, r8d; Wait
0x140013abf  xor     edx, edx; Increment
0x140013ac1  call    cs:__imp_KeSetEvent
0x140013ac8  nop     dword ptr [rax+rax+00h]
0x140013acd  mov     rbx, [rsp+58h+arg_0]
0x140013ad2  add     rsp, 50h
0x140013ad6  pop     rdi
0x140013ad7  retn
```
