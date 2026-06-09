# EvtAdapterUpdateNdisPmParameters

- ea: `0x140008ff0`
- end: `0x14000908e`
- name: `EvtAdapterUpdateNdisPmParameters`
- size: `158`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x1400051ac`
- `0x140008ff0`
- `0x140047e90`

## pseudocode

```c
__int64 __fastcall EvtAdapterUpdateNdisPmParameters(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  unsigned __int16 v4; // cx
  int v5; // edx
  __int64 v6; // rcx

  result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031 + 1616))(
             WdfDriverGlobals,
             a1,
             off_14005DF38);
  if ( !*(_DWORD *)(result + 92) )
  {
    v4 = *(_WORD *)(a2 + 2);
    v5 = 20;
    if ( v4 >= 0x14u )
    {
      v6 = *(_QWORD *)(result + 24);
      *(_DWORD *)(v6 + 1364) = *(_DWORD *)(a2 + 12);
      result = *(unsigned int *)(a2 + 16);
      *(_DWORD *)(v6 + 1368) = result;
    }
    else
    {
      result = (__int64)&WPP_RECORDER_INITIALIZED;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v5) = 2;
        return WPP_RECORDER_SF_DD(
                 WPP_GLOBAL_Control->DeviceExtension,
                 v5,
                 8,
                 11,
                 (__int64)WPP_b3608f89b9e4367ac44795c7db9eacb1_Traceguids,
                 20,
                 v4);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140008ff0  push    rbx
0x140008ff2  sub     rsp, 40h
0x140008ff6  mov     rax, cs:WdfFunctions_01031
0x140008ffd  mov     rbx, rdx
0x140009000  mov     r8, cs:off_14005DF38
0x140009007  mov     rdx, rcx
0x14000900a  mov     rcx, cs:WdfDriverGlobals
0x140009011  mov     rax, [rax+650h]
0x140009018  call    _guard_dispatch_icall
0x14000901d  cmp     dword ptr [rax+5Ch], 0
0x140009021  jnz     short loc_140009087
0x140009023  movzx   ecx, word ptr [rbx+2]
0x140009027  mov     edx, 14h
0x14000902c  cmp     cx, dx
0x14000902f  jnb     short loc_140009071
0x140009031  lea     rax, WPP_RECORDER_INITIALIZED
0x140009038  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000903f  jz      short loc_140009087
0x140009041  mov     [rsp+48h+var_18], ecx
0x140009045  lea     r9d, [rdx-9]
0x140009049  mov     rcx, cs:WPP_GLOBAL_Control
0x140009050  lea     rax, WPP_b3608f89b9e4367ac44795c7db9eacb1_Traceguids
0x140009057  mov     [rsp+48h+var_20], edx
0x14000905b  lea     r8d, [rdx-0Ch]
0x14000905f  mov     dl, 2
0x140009061  mov     [rsp+48h+var_28], rax
0x140009066  mov     rcx, [rcx+40h]
0x14000906a  call    WPP_RECORDER_SF_DD
0x14000906f  jmp     short loc_140009087
0x140009071  mov     rcx, [rax+18h]
0x140009075  mov     eax, [rbx+0Ch]
0x140009078  mov     [rcx+554h], eax
0x14000907e  mov     eax, [rbx+10h]
0x140009081  mov     [rcx+558h], eax
0x140009087  add     rsp, 40h
0x14000908b  pop     rbx
0x14000908c  retn
```
