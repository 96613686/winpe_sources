# UsbDeviceCapabilityHandler::AccessCheck(ushort const *,ushort const *,ushort const *,ulong,ushort const *,CapabilityHandlerAccessStatus *)

- ea: `0x180011cc0`
- end: `0x180011d69`
- name: `?AccessCheck@UsbDeviceCapabilityHandler@@UEAAJPEBG00K0PEAW4CapabilityHandlerAccessStatus@@@Z`
- size: `169`
- prototype: `__int64 __fastcall(UsbDeviceCapabilityHandler *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, enum CapabilityHandlerAccessStatus *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180011cc0`
- `0x180011d70`
- `0x180012e9c`

## pseudocode

```c
__int64 __fastcall UsbDeviceCapabilityHandler::AccessCheck(
        UsbDeviceCapabilityHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        const unsigned __int16 *a6,
        enum CapabilityHandlerAccessStatus *a7)
{
  __int64 result; // rax
  int v9; // edx
  _BYTE v10[4]; // [rsp+30h] [rbp-20h] BYREF
  BYTE v11[2]; // [rsp+34h] [rbp-1Ch] BYREF
  BYTE v12[4]; // [rsp+38h] [rbp-18h] BYREF
  BYTE v13[4]; // [rsp+3Ch] [rbp-14h] BYREF
  BYTE v14[4]; // [rsp+40h] [rbp-10h] BYREF
  BYTE PropertyBuffer[12]; // [rsp+44h] [rbp-Ch] BYREF

  *(_WORD *)PropertyBuffer = 0;
  *(_WORD *)v14 = 0;
  *(_DWORD *)a7 = 0;
  *(_WORD *)v11 = 0;
  *(_WORD *)v13 = 0;
  *(_WORD *)v12 = 0;
  v10[0] = 0;
  result = DeviceHelperDeviceInterfaceInSystemContainerAndRestricted(a4, v10, a3);
  if ( (int)result >= 0 )
  {
    if ( !v10[0] )
    {
      result = UsbDeviceCapabilityHandler::GetUsbDeviceProperties(a4, PropertyBuffer, v14, v11, v13, v12);
      if ( (int)result < 0 )
        return result;
      if ( *(unsigned __int16 *)v11 > 0x10u || (v9 = 68043, !_bittest(&v9, *(unsigned __int16 *)v11)) )
      {
        if ( *(_WORD *)v11 != 224 )
          *(_DWORD *)a7 = 1;
      }
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180011cc0  mov     [rsp-8+arg_0], rbx
0x180011cc5  mov     [rsp-8+arg_8], rdi
0x180011cca  push    rbp
0x180011ccb  mov     rbp, rsp
0x180011cce  sub     rsp, 50h
0x180011cd2  mov     rbx, [rbp+arg_30]
0x180011cd6  lea     rdx, [rbp+var_20]
0x180011cda  xor     eax, eax
0x180011cdc  mov     rcx, r9
0x180011cdf  mov     rdi, r9
0x180011ce2  mov     word ptr [rbp+PropertyBuffer], ax
0x180011ce6  mov     word ptr [rbp+var_10], ax
0x180011cea  mov     [rbx], eax
0x180011cec  mov     word ptr [rbp+var_1C], ax
0x180011cf0  mov     word ptr [rbp+var_14], ax
0x180011cf4  mov     word ptr [rbp+var_18], ax
0x180011cf8  mov     [rbp+var_20], al
0x180011cfb  call    DeviceHelperDeviceInterfaceInSystemContainerAndRestricted
0x180011d00  test    eax, eax
0x180011d02  js      short loc_180011D59
0x180011d04  cmp     [rbp+var_20], 0
0x180011d08  jnz     short loc_180011D57
0x180011d0a  lea     rax, [rbp+var_18]
0x180011d0e  mov     rcx, rdi; pszDeviceInterface
0x180011d11  mov     [rsp+50h+var_28], rax; PBYTE
0x180011d16  lea     r9, [rbp+var_1C]; PBYTE
0x180011d1a  lea     rax, [rbp+var_14]
0x180011d1e  lea     r8, [rbp+var_10]; PBYTE
0x180011d22  mov     [rsp+50h+var_30], rax; PBYTE
0x180011d27  lea     rdx, [rbp+PropertyBuffer]; PropertyBuffer
0x180011d2b  call    ?GetUsbDeviceProperties@UsbDeviceCapabilityHandler@@CAJPEBGPEAG1111@Z; UsbDeviceCapabilityHandler::GetUsbDeviceProperties(ushort const *,ushort *,ushort *,ushort *,ushort *,ushort *)
0x180011d30  test    eax, eax
0x180011d32  js      short loc_180011D59
0x180011d34  movzx   ecx, word ptr [rbp+var_1C]
0x180011d38  cmp     ecx, 10h
0x180011d3b  ja      short loc_180011D47
0x180011d3d  mov     edx, 109CBh
0x180011d42  bt      edx, ecx
0x180011d45  jb      short loc_180011D57
0x180011d47  mov     eax, 0E0h
0x180011d4c  cmp     cx, ax
0x180011d4f  jz      short loc_180011D57
0x180011d51  mov     dword ptr [rbx], 1
0x180011d57  xor     eax, eax
0x180011d59  mov     rbx, [rsp+50h+arg_0]
0x180011d5e  mov     rdi, [rsp+50h+arg_8]
0x180011d63  add     rsp, 50h
0x180011d67  pop     rbp
0x180011d68  retn
```
