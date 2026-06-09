# ScoUpdateAvdtpSuspension

- ea: `0x14001117c`
- end: `0x1400112bd`
- name: `ScoUpdateAvdtpSuspension`
- size: `321`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x14000d140`
- `0x14000e87c`
- `0x14000ecc4`
- `0x14000f700`
- `0x1400112c4`
- `0x1400123a0`
- `0x140013cb4`
- `0x140013df8`
- `0x14002c5b8`

## callees

- `0x140004050`
- `0x1400048c8`
- `0x14000c570`
- `0x14001117c`
- `0x140011484`
- `0x14001ae00`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x14001128e`
- `ntoskrnl!KeClearEvent` at `0x14001128e`

## pseudocode

```c
bool __fastcall ScoUpdateAvdtpSuspension(__int64 a1)
{
  int v2; // r8d
  int v3; // edx
  unsigned __int8 v4; // al
  unsigned int v6; // esi
  __int64 v7; // rbx
  char v8; // [rsp+60h] [rbp+8h] BYREF

  wil::acquire_wdf_spin_lock(&v8, *(_QWORD *)(a1 + 368));
  LOBYTE(v3) = 1;
  if ( *(_DWORD *)(a1 + 376) || *(_DWORD *)(a1 + 108) || (v4 = 0, *(_DWORD *)(a1 + 456)) )
    v4 = 1;
  if ( v4 == (*(_DWORD *)(a1 + 460) != 0) )
  {
    wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&void WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&void WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(&v8);
    return 0;
  }
  else
  {
    v6 = v4;
    *(_DWORD *)(a1 + 460) = v4;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      LOBYTE(v3) = 0;
    }
    if ( (_BYTE)v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v2) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_ll(WPP_GLOBAL_Control->AttachedDevice, v3, v2, WPP_GLOBAL_Control->DeviceExtension);
    }
    wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&void WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&void WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(&v8);
    v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, a1);
    KeClearEvent((PRKEVENT)(a1 + 304));
    return (unsigned int)Bus_MpmAvdtpSuspendRequest(v7, v6) == 259;
  }
}

```

## disassembly

```asm
0x14001117c  mov     [rsp+arg_8], rbx
0x140011181  mov     [rsp+arg_10], rsi
0x140011186  push    rdi
0x140011187  sub     rsp, 50h
0x14001118b  mov     rdx, [rcx+170h]
0x140011192  mov     rdi, rcx
0x140011195  lea     rcx, [rsp+58h+arg_0]
0x14001119a  call    ?acquire_wdf_spin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUWDFSPINLOCK__@@P6AXPEAU1@@Z$1?WdfSpinLockRelease@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAUWDFSPINLOCK__@@@Z; wil::acquire_wdf_spin_lock(WDFSPINLOCK__ *)
0x14001119f  xor     r10d, r10d
0x1400111a2  mov     dl, 1
0x1400111a4  cmp     [rdi+1CCh], r10d
0x1400111ab  setnz   r9b
0x1400111af  cmp     [rdi+178h], r10d
0x1400111b6  jnz     short loc_1400111CA
0x1400111b8  cmp     [rdi+6Ch], r10d
0x1400111bc  jnz     short loc_1400111CA
0x1400111be  mov     al, r10b
0x1400111c1  cmp     [rdi+1C8h], r10d
0x1400111c8  jz      short loc_1400111CC
0x1400111ca  mov     al, dl
0x1400111cc  cmp     al, r9b
0x1400111cf  jnz     short loc_1400111E2
0x1400111d1  lea     rcx, [rsp+58h+arg_0]
0x1400111d6  call    ??1?$unique_storage@U?$resource_policy@PEAUWDFSPINLOCK__@@P6AXPEAU1@@Z$1?WdfSpinLockRelease@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(void)
0x1400111db  xor     al, al
0x1400111dd  jmp     loc_1400112AC
0x1400111e2  movzx   esi, al
0x1400111e5  mov     [rdi+1CCh], esi
0x1400111eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400111f2  lea     rax, WPP_GLOBAL_Control
0x1400111f9  cmp     rcx, rax
0x1400111fc  jz      short loc_14001120B
0x1400111fe  mov     eax, [rcx+2Ch]
0x140011201  test    al, 10h
0x140011203  jz      short loc_14001120B
0x140011205  cmp     byte ptr [rcx+29h], 4
0x140011209  jnb     short loc_14001120E
0x14001120b  mov     dl, r10b
0x14001120e  lea     rax, WPP_RECORDER_INITIALIZED
0x140011215  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001121c  setnz   r8b
0x140011220  test    dl, dl
0x140011222  jnz     short loc_140011229
0x140011224  test    r8b, r8b
0x140011227  jz      short loc_14001125D
0x140011229  movzx   eax, r9b
0x14001122d  mov     r9, [rcx+40h]
0x140011231  mov     rcx, [rcx+18h]
0x140011235  mov     [rsp+58h+var_10], esi
0x140011239  mov     [rsp+58h+var_18], eax
0x14001123d  lea     rax, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x140011244  mov     [rsp+58h+var_20], rax
0x140011249  mov     [rsp+58h+var_28], 0Bh
0x140011250  mov     [rsp+58h+var_30], 5
0x140011258  call    WPP_RECORDER_AND_TRACE_SF_ll
0x14001125d  lea     rcx, [rsp+58h+arg_0]
0x140011262  call    ??1?$unique_storage@U?$resource_policy@PEAUWDFSPINLOCK__@@P6AXPEAU1@@Z$1?WdfSpinLockRelease@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(void)
0x140011267  mov     rax, cs:WdfFunctions_01015
0x14001126e  mov     rdx, rdi
0x140011271  mov     rcx, cs:WdfDriverGlobals
0x140011278  mov     rax, [rax+660h]
0x14001127f  call    _guard_dispatch_icall
0x140011284  lea     rcx, [rdi+130h]; Event
0x14001128b  mov     rbx, rax
0x14001128e  call    cs:__imp_KeClearEvent
0x140011295  nop     dword ptr [rax+rax+00h]
0x14001129a  mov     edx, esi
0x14001129c  mov     rcx, rbx
0x14001129f  call    Bus_MpmAvdtpSuspendRequest
0x1400112a4  cmp     eax, 103h
0x1400112a9  setz    al
0x1400112ac  mov     rbx, [rsp+58h+arg_8]
0x1400112b1  mov     rsi, [rsp+58h+arg_10]
0x1400112b6  add     rsp, 50h
0x1400112ba  pop     rdi
0x1400112bb  retn
```
