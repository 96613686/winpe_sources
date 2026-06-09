# UpdateReserveManager::EnsureNotInSafeMode(void)

- ea: `0x180015ad0`
- end: `0x180015b2d`
- name: `?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ`
- size: `93`
- prototype: `__int64 __fastcall(UpdateReserveManager *__hidden this)`
- caller_count: `43`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180012340`
- `0x180012bf0`
- `0x18001328c`
- `0x1800133c4`
- `0x1800133f8`
- `0x180013600`
- `0x180013770`
- `0x180014740`
- `0x180014854`
- `0x180014960`
- `0x180015240`
- `0x1800155e0`
- `0x180015b34`
- `0x180015e20`
- `0x1800166a8`
- `0x180016d98`
- `0x180016fb8`
- `0x1800172a8`
- `0x180017380`
- `0x1800191f0`
- `0x1800192e0`
- `0x180019634`
- `0x18001a968`
- `0x18001ac20`
- `0x18001aff0`
- `0x18001b3d0`
- `0x18001b560`
- `0x18001b760`
- `0x18001b8f0`
- `0x18001c9e0`
- `0x18001cb28`
- `0x18001ce74`
- `0x18001ee88`
- `0x18001fa18`
- `0x18001faf0`
- `0x18001fd00`
- `0x18001fd60`
- `0x180020200`
- `0x1800204d0`
- `0x180020778`
- `0x180020c70`
- `0x180021850`
- `0x180021a28`

## callees

- `0x18000fafc`
- `0x180015ad0`

## string_xrefs

- `0x180015ae0`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180015afa`: `UpdateReserveManager::EnsureNotInSafeMode`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::EnsureNotInSafeMode(UpdateReserveManager *this)
{
  _QWORD v2[5]; // [rsp+20h] [rbp-28h] BYREF

  if ( !*((_BYTE *)this + 1178) )
    return 0;
  v2[2] = 1804;
  v2[0] = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
  v2[1] = "UpdateReserveManager::EnsureNotInSafeMode";
  v2[3] = "((SCODE) (((unsigned long)(1)<<31) | ((unsigned long)(15)<<16) | ((unsigned long)(0x977))) )";
  RtlReportErrorOrigination(v2, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2148469111LL);
  return 2148469111LL;
}

```

## disassembly

```asm
0x180015ad0  mov     r11, rsp
0x180015ad3  sub     rsp, 48h
0x180015ad7  cmp     byte ptr [rcx+49Ah], 0
0x180015ade  jz      short loc_180015B26
0x180015ae0  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180015ae7  mov     qword ptr [r11-18h], 70Ch
0x180015aef  mov     [r11-28h], rax
0x180015af3  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180015afa  lea     rax, aUpdatereservem_6; "UpdateReserveManager::EnsureNotInSafeMo"...
0x180015b01  mov     r8d, 800F0977h
0x180015b07  mov     [r11-20h], rax
0x180015b0b  lea     rcx, [r11-28h]
0x180015b0f  lea     rax, aScodeUnsignedL; "((SCODE) (((unsigned long)(1)<<31) | (("...
0x180015b16  mov     [r11-10h], rax
0x180015b1a  call    RtlReportErrorOrigination
0x180015b1f  mov     eax, 800F0977h
0x180015b24  jmp     short loc_180015B28
0x180015b26  xor     eax, eax
0x180015b28  add     rsp, 48h
0x180015b2c  retn
```
