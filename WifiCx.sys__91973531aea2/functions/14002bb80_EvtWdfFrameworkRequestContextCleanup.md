# EvtWdfFrameworkRequestContextCleanup

- ea: `0x14002bb80`
- end: `0x14002bc28`
- name: `EvtWdfFrameworkRequestContextCleanup`
- size: `168`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x140024428`
- `0x14002bb80`
- `0x1400dfd40`

## string_xrefs

- `0x14002bbba`: `onecoreuap\net\wlan\sys\wificx\extension\src\wxdevice.cpp`

## pseudocode

```c
_UNKNOWN **__fastcall EvtWdfFrameworkRequestContextCleanup(__int64 a1)
{
  _UNKNOWN **result; // rax
  int v3; // edx
  int v4; // r8d

  result = (_UNKNOWN **)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031 + 1616))(
                          WdfDriverGlobals,
                          a1,
                          off_14010E330);
  if ( *((_BYTE *)result + 16) )
  {
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64, const char *))(WdfFunctions_01031 + 1648))(
      WdfDriverGlobals,
      a1,
      1380350039,
      1579,
      "onecoreuap\\net\\wlan\\sys\\wificx\\extension\\src\\wxdevice.cpp");
    result = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v3) = 4;
      return (_UNKNOWN **)WPP_RECORDER_SF_q(
                            WPP_GLOBAL_Control->DeviceExtension,
                            v3,
                            v4,
                            106,
                            (__int64)WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids,
                            a1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14002bb80  push    rbx
0x14002bb82  sub     rsp, 30h
0x14002bb86  mov     rax, cs:WdfFunctions_01031
0x14002bb8d  mov     rbx, rcx
0x14002bb90  mov     r8, cs:off_14010E330
0x14002bb97  mov     rdx, rcx
0x14002bb9a  mov     rcx, cs:WdfDriverGlobals
0x14002bba1  mov     rax, [rax+650h]
0x14002bba8  call    _guard_dispatch_icall
0x14002bbad  cmp     byte ptr [rax+10h], 0
0x14002bbb1  jz      short loc_14002BC21
0x14002bbb3  mov     rax, cs:WdfFunctions_01031
0x14002bbba  lea     rcx, aOnecoreuapNetW; "onecoreuap\\net\\wlan\\sys\\wificx\\ext"...
0x14002bbc1  mov     [rsp+38h+var_18], rcx
0x14002bbc6  mov     r9d, 62Bh
0x14002bbcc  mov     rcx, cs:WdfDriverGlobals
0x14002bbd3  mov     r8d, 52467857h
0x14002bbd9  mov     rdx, rbx
0x14002bbdc  mov     rax, [rax+670h]
0x14002bbe3  call    _guard_dispatch_icall
0x14002bbe8  lea     rax, WPP_RECORDER_INITIALIZED
0x14002bbef  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002bbf6  jz      short loc_14002BC21
0x14002bbf8  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bbff  lea     rax, WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids
0x14002bc06  mov     r9d, 6Ah ; 'j'
0x14002bc0c  mov     [rsp+38h+var_10], rbx
0x14002bc11  mov     dl, 4
0x14002bc13  mov     [rsp+38h+var_18], rax
0x14002bc18  mov     rcx, [rcx+40h]
0x14002bc1c  call    WPP_RECORDER_SF_q
0x14002bc21  add     rsp, 30h
0x14002bc25  pop     rbx
0x14002bc26  retn
```
