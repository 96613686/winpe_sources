# Docking::VirtualInput::PtpInputManager::_Uninitialize(void)

- ea: `0x18001adb0`
- end: `0x18001adf5`
- name: `?_Uninitialize@PtpInputManager@VirtualInput@Docking@@MEAAJXZ`
- size: `69`
- prototype: `__int64 __fastcall(Docking::VirtualInput::PtpInputManager *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001a250`

## callees

- `0x18001adb0`

## import_xrefs

- `ext-ms-win-ntuser-rim-l1-1-0!RemoveInjectionDevice` at `0x18001addb`
- `ext-ms-win-ntuser-rim-l1-1-0!RemoveInjectionDevice` at `0x18001addb`

## pseudocode

```c
__int64 __fastcall Docking::VirtualInput::PtpInputManager::_Uninitialize(Docking::VirtualInput::PtpInputManager *this)
{
  *((_QWORD *)this + 14) = 0;
  if ( *((_QWORD *)this + 12) )
  {
    RemoveInjectionDevice(*((_QWORD *)this + 12));
    *((_QWORD *)this + 12) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18001adb0  mov     [rsp+arg_0], rcx
0x18001adb5  sub     rsp, 28h
0x18001adb9  mov     rax, [rsp+28h+arg_0]
0x18001adbe  mov     qword ptr [rax+70h], 0
0x18001adc6  mov     rax, [rsp+28h+arg_0]
0x18001adcb  cmp     qword ptr [rax+60h], 0
0x18001add0  jz      short loc_18001ADEE
0x18001add2  mov     rax, [rsp+28h+arg_0]
0x18001add7  mov     rcx, [rax+60h]
0x18001addb  call    cs:__imp_RemoveInjectionDevice
0x18001ade1  mov     rax, [rsp+28h+arg_0]
0x18001ade6  mov     qword ptr [rax+60h], 0
0x18001adee  xor     eax, eax
0x18001adf0  add     rsp, 28h
0x18001adf4  retn
```
