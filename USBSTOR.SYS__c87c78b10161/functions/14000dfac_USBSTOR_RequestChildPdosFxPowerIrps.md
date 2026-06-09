# USBSTOR_RequestChildPdosFxPowerIrps

- ea: `0x14000dfac`
- end: `0x14000e057`
- name: `USBSTOR_RequestChildPdosFxPowerIrps`
- size: `171`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000df00`
- `0x140010ad0`
- `0x140010b50`

## callees

- `0x140003630`
- `0x14000dfac`
- `0x14000e060`

## import_xrefs

- `ntoskrnl!PoRequestPowerIrp` at `0x14000e014`
- `ntoskrnl!PoRequestPowerIrp` at `0x14000e014`

## pseudocode

```c
void __fastcall USBSTOR_RequestChildPdosFxPowerIrps(char *Context, int a2)
{
  char *v2; // r14
  __int64 v3; // rbp
  char *v4; // rbx
  __int64 v6; // r8

  v2 = Context + 32;
  v3 = a2;
  v4 = (char *)*((_QWORD *)Context + 4);
  *((_DWORD *)Context + 491) = 1;
  while ( v4 != v2 )
  {
    if ( *((_DWORD *)v4 + 6) != (_DWORD)v3 )
    {
      v6 = *((_QWORD *)v4 + 4);
      if ( v6 )
        USBSTOR_LogEntry(2017884243, *((_QWORD *)v4 - 2), v6, v3);
      _InterlockedIncrement((volatile signed __int32 *)Context + 491);
      if ( PoRequestPowerIrp(
             *((PDEVICE_OBJECT *)v4 - 2),
             2u,
             (POWER_STATE)v3,
             (PREQUEST_POWER_COMPLETE)USBSTOR_PdoFxPowerCompletion,
             Context,
             0) < 0 )
        _InterlockedDecrement((volatile signed __int32 *)Context + 491);
    }
    v4 = *(char **)v4;
  }
  USBSTOR_PdoFxPowerCompletion(0, 2u, (POWER_STATE)v3, (int *)Context);
}

```

## disassembly

```asm
0x14000dfac  push    rbx
0x14000dfae  push    rbp
0x14000dfaf  push    rsi
0x14000dfb0  push    rdi
0x14000dfb1  push    r14
0x14000dfb3  sub     rsp, 30h
0x14000dfb7  lea     r14, [rcx+20h]
0x14000dfbb  movsxd  rbp, edx
0x14000dfbe  mov     rbx, [r14]
0x14000dfc1  mov     rdi, rcx
0x14000dfc4  mov     dword ptr [rcx+7ACh], 1
0x14000dfce  jmp     short loc_14000E02E
0x14000dfd0  cmp     [rbx+18h], ebp
0x14000dfd3  jz      short loc_14000E02B
0x14000dfd5  mov     r8, [rbx+20h]
0x14000dfd9  test    r8, r8
0x14000dfdc  jz      short loc_14000DFEF
0x14000dfde  mov     rdx, [rbx-10h]
0x14000dfe2  mov     r9, rbp
0x14000dfe5  mov     ecx, 78467853h
0x14000dfea  call    USBSTOR_LogEntry
0x14000dfef  lock inc dword ptr [rdi+7ACh]
0x14000dff6  mov     rcx, [rbx-10h]; DeviceObject
0x14000dffa  lea     r9, USBSTOR_PdoFxPowerCompletion; CompletionFunction
0x14000e001  mov     [rsp+58h+Irp], 0; Irp
0x14000e00a  mov     r8d, ebp; PowerState
0x14000e00d  mov     dl, 2; MinorFunction
0x14000e00f  mov     [rsp+58h+Context], rdi; Context
0x14000e014  call    cs:__imp_PoRequestPowerIrp
0x14000e01b  nop     dword ptr [rax+rax+00h]
0x14000e020  test    eax, eax
0x14000e022  jns     short loc_14000E02B
0x14000e024  lock dec dword ptr [rdi+7ACh]
0x14000e02b  mov     rbx, [rbx]
0x14000e02e  cmp     rbx, r14
0x14000e031  jnz     short loc_14000DFD0
0x14000e033  mov     r9, rdi; Context
0x14000e036  mov     [rsp+58h+Context], 0; IoStatus
0x14000e03f  mov     r8d, ebp; PowerState
0x14000e042  mov     dl, 2; MinorFunction
0x14000e044  xor     ecx, ecx; DeviceObject
0x14000e046  call    USBSTOR_PdoFxPowerCompletion
0x14000e04b  add     rsp, 30h
0x14000e04f  pop     r14
0x14000e051  pop     rdi
0x14000e052  pop     rsi
0x14000e053  pop     rbp
0x14000e054  pop     rbx
0x14000e055  retn
```
