# SerialDeviceCapabilityHandler::AccessCheck(ushort const *,ushort const *,ushort const *,ulong,ushort const *,CapabilityHandlerAccessStatus *)

- ea: `0x180011c10`
- end: `0x180011c4b`
- name: `?AccessCheck@SerialDeviceCapabilityHandler@@UEAAJPEBG00K0PEAW4CapabilityHandlerAccessStatus@@@Z`
- size: `59`
- prototype: `__int64 __fastcall(SerialDeviceCapabilityHandler *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, enum CapabilityHandlerAccessStatus *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180011c10`
- `0x180012e9c`

## pseudocode

```c
__int64 __fastcall SerialDeviceCapabilityHandler::AccessCheck(
        SerialDeviceCapabilityHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        const unsigned __int16 *a6,
        enum CapabilityHandlerAccessStatus *a7)
{
  __int64 result; // rax
  _BYTE v8[24]; // [rsp+20h] [rbp-18h] BYREF

  v8[0] = 0;
  *(_DWORD *)a7 = 0;
  result = DeviceHelperDeviceInterfaceInSystemContainerAndRestricted(a4, v8, a3);
  if ( (int)result >= 0 )
  {
    result = 0;
    if ( !v8[0] )
      *(_DWORD *)a7 = 1;
  }
  return result;
}

```

## disassembly

```asm
0x180011c10  push    rbx
0x180011c12  sub     rsp, 30h
0x180011c16  mov     rbx, [rsp+38h+arg_30]
0x180011c1b  lea     rdx, [rsp+38h+var_18]
0x180011c20  mov     rcx, r9
0x180011c23  mov     [rsp+38h+var_18], 0
0x180011c28  mov     dword ptr [rbx], 0
0x180011c2e  call    DeviceHelperDeviceInterfaceInSystemContainerAndRestricted
0x180011c33  test    eax, eax
0x180011c35  js      short loc_180011C45
0x180011c37  xor     eax, eax
0x180011c39  cmp     [rsp+38h+var_18], al
0x180011c3d  jnz     short loc_180011C45
0x180011c3f  mov     dword ptr [rbx], 1
0x180011c45  add     rsp, 30h
0x180011c49  pop     rbx
0x180011c4a  retn
```
