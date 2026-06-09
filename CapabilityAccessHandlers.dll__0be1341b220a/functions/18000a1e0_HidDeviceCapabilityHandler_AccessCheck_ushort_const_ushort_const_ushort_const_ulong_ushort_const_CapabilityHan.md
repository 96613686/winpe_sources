# HidDeviceCapabilityHandler::AccessCheck(ushort const *,ushort const *,ushort const *,ulong,ushort const *,CapabilityHandlerAccessStatus *)

- ea: `0x18000a1e0`
- end: `0x18000a2a9`
- name: `?AccessCheck@HidDeviceCapabilityHandler@@UEAAJPEBG00K0PEAW4CapabilityHandlerAccessStatus@@@Z`
- size: `201`
- prototype: `__int64 __fastcall(HidDeviceCapabilityHandler *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, DWORD dwProcessId, const unsigned __int16 *, enum CapabilityHandlerAccessStatus *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000a1e0`
- `0x18000a324`
- `0x180012e9c`
- `0x180013348`

## pseudocode

```c
__int64 __fastcall HidDeviceCapabilityHandler::AccessCheck(
        HidDeviceCapabilityHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        DWORD dwProcessId,
        const unsigned __int16 *a6,
        enum CapabilityHandlerAccessStatus *a7)
{
  __int64 result; // rax
  bool v9; // zf
  _BYTE v10[4]; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int16 v11; // [rsp+34h] [rbp-1Ch] BYREF
  unsigned __int16 v12[2]; // [rsp+38h] [rbp-18h] BYREF
  BYTE v13[4]; // [rsp+3Ch] [rbp-14h] BYREF
  BYTE PropertyBuffer[16]; // [rsp+40h] [rbp-10h] BYREF

  *(_WORD *)PropertyBuffer = 0;
  *(_WORD *)v13 = 0;
  *(_DWORD *)a7 = 0;
  v11 = 0;
  v12[0] = 0;
  v10[0] = 0;
  result = DeviceHelperDeviceInterfaceInSystemContainerAndRestricted(a4, v10, a3);
  if ( (int)result >= 0 )
  {
    if ( v10[0] )
      return 0;
    result = HidDeviceCapabilityHandler::GetDeviceProperties(a4, PropertyBuffer, v13, &v11, v12);
    if ( (int)result < 0 )
      return result;
    switch ( v11 )
    {
      case 0u:
        return 0;
      case 1u:
        if ( v12[0] == 2 || v12[0] == 6 || v12[0] == 7 )
          return 0;
        v9 = v12[0] == 128;
        break;
      case 7u:
        return 0;
      case 0xBu:
        v9 = (unsigned __int8)DeviceHelperIsCapabilityPresentForProcessId(dwProcessId) == 0;
        break;
      case 0xCu:
      case 0xDu:
        return 0;
      default:
        v9 = v11 == 32;
        break;
    }
    if ( !v9 )
      *(_DWORD *)a7 = 1;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000a1e0  mov     [rsp-8+arg_0], rbx
0x18000a1e5  mov     [rsp-8+arg_8], rdi
0x18000a1ea  push    rbp
0x18000a1eb  mov     rbp, rsp
0x18000a1ee  sub     rsp, 50h
0x18000a1f2  mov     rbx, [rbp+arg_30]
0x18000a1f6  lea     rdx, [rbp+var_20]
0x18000a1fa  xor     eax, eax
0x18000a1fc  mov     rcx, r9
0x18000a1ff  mov     rdi, r9
0x18000a202  mov     word ptr [rbp+PropertyBuffer], ax
0x18000a206  mov     word ptr [rbp+var_14], ax
0x18000a20a  mov     [rbx], eax
0x18000a20c  mov     [rbp+var_1C], ax
0x18000a210  mov     [rbp+var_18], ax
0x18000a214  mov     [rbp+var_20], al
0x18000a217  call    DeviceHelperDeviceInterfaceInSystemContainerAndRestricted
0x18000a21c  test    eax, eax
0x18000a21e  js      short loc_18000A299
0x18000a220  cmp     [rbp+var_20], 0
0x18000a224  jnz     short loc_18000A297
0x18000a226  lea     rax, [rbp+var_18]
0x18000a22a  mov     rcx, rdi; pszDeviceInterface
0x18000a22d  lea     r9, [rbp+var_1C]; unsigned __int16 *
0x18000a231  mov     [rsp+50h+var_30], rax; unsigned __int16 *
0x18000a236  lea     r8, [rbp+var_14]; PBYTE
0x18000a23a  lea     rdx, [rbp+PropertyBuffer]; PropertyBuffer
0x18000a23e  call    ?GetDeviceProperties@HidDeviceCapabilityHandler@@CAJPEBGPEAG111@Z; HidDeviceCapabilityHandler::GetDeviceProperties(ushort const *,ushort *,ushort *,ushort *,ushort *)
0x18000a243  test    eax, eax
0x18000a245  js      short loc_18000A299
0x18000a247  movzx   ecx, [rbp+var_1C]
0x18000a24b  test    ecx, ecx
0x18000a24d  jz      short loc_18000A297
0x18000a24f  sub     ecx, 1
0x18000a252  jz      short loc_18000A279
0x18000a254  sub     ecx, 6
0x18000a257  jz      short loc_18000A297
0x18000a259  sub     ecx, 4
0x18000a25c  jz      short loc_18000A26D
0x18000a25e  sub     ecx, 1
0x18000a261  jz      short loc_18000A297
0x18000a263  sub     ecx, 1
0x18000a266  jz      short loc_18000A297
0x18000a268  cmp     ecx, 13h
0x18000a26b  jmp     short loc_18000A28F
0x18000a26d  mov     ecx, [rbp+dwProcessId]; dwProcessId
0x18000a270  call    DeviceHelperIsCapabilityPresentForProcessId
0x18000a275  test    al, al
0x18000a277  jmp     short loc_18000A28F
0x18000a279  movzx   ecx, [rbp+var_18]
0x18000a27d  sub     ecx, 2
0x18000a280  jz      short loc_18000A297
0x18000a282  sub     ecx, 4
0x18000a285  jz      short loc_18000A297
0x18000a287  sub     ecx, 1
0x18000a28a  jz      short loc_18000A297
0x18000a28c  cmp     ecx, 79h ; 'y'
0x18000a28f  jz      short loc_18000A297
0x18000a291  mov     dword ptr [rbx], 1
0x18000a297  xor     eax, eax
0x18000a299  mov     rbx, [rsp+50h+arg_0]
0x18000a29e  mov     rdi, [rsp+50h+arg_8]
0x18000a2a3  add     rsp, 50h
0x18000a2a7  pop     rbp
0x18000a2a8  retn
```
