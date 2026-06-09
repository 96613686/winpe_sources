# _DeviceHelperValidateInterfacePath(ushort const *,ushort * *)

- ea: `0x180003dc0`
- end: `0x180003e61`
- name: `?_DeviceHelperValidateInterfacePath@@YAJPEBGPEAPEAG@Z`
- size: `161`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180002cd8`
- `0x180012e9c`

## callees

- `0x180003dc0`
- `0x180003e68`
- `0x180004c70`

## import_xrefs

- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180003e46`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180003e46`

## pseudocode

```c
__int64 __fastcall _DeviceHelperValidateInterfacePath(unsigned __int16 *a1, unsigned __int16 **a2)
{
  __int64 v3; // [rsp+38h] [rbp-40h] BYREF
  DEVPROPKEY v4; // [rsp+40h] [rbp-38h]
  int v5; // [rsp+54h] [rbp-24h]
  __int64 v6; // [rsp+58h] [rbp-20h]

  v3 = 0;
  v4 = DEVPKEY_DeviceInterface_ClassGuid;
  v5 = 0;
  v6 = 0;
  if ( a2 )
    *a2 = 0;
  return (unsigned int)DeviceHelperGetDevPropertiesFromInterfacePath(a1, (__int64)&v3, (__int64)a2);
}

```

## disassembly

```asm
0x180003dc0  push    rbx
0x180003dc2  sub     rsp, 70h
0x180003dc6  mov     rax, cs:__security_cookie
0x180003dcd  xor     rax, rsp
0x180003dd0  mov     [rsp+78h+var_18], rax
0x180003dd5  mov     eax, cs:DEVPKEY_DeviceInterface_ClassGuid.pid
0x180003ddb  mov     [rsp+78h+var_48], 0
0x180003de3  mov     [rsp+78h+var_40], 0
0x180003dec  mov     [rsp+78h+var_28], eax
0x180003df0  mov     [rsp+78h+var_24], 0
0x180003df8  mov     [rsp+78h+var_20], 0
0x180003e01  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data1
0x180003e08  movups  [rsp+78h+var_38], xmm0
0x180003e0d  test    rdx, rdx
0x180003e10  jz      short loc_180003E19
0x180003e12  mov     qword ptr [rdx], 0
0x180003e19  lea     rax, [rsp+78h+var_40]
0x180003e1e  mov     [rsp+78h+var_50], rdx; __int64
0x180003e23  lea     r9, [rsp+78h+var_48]
0x180003e28  mov     [rsp+78h+var_58], rax; __int64
0x180003e2d  lea     r8, [rsp+78h+var_38]
0x180003e32  call    DeviceHelperGetDevPropertiesFromInterfacePath
0x180003e37  mov     ecx, [rsp+78h+var_48]
0x180003e3b  mov     ebx, eax
0x180003e3d  test    ecx, ecx
0x180003e3f  jz      short loc_180003E4C
0x180003e41  mov     rdx, [rsp+78h+var_40]
0x180003e46  call    cs:__imp_DevFreeObjectProperties
0x180003e4c  mov     eax, ebx
0x180003e4e  mov     rcx, [rsp+78h+var_18]
0x180003e53  xor     rcx, rsp; StackCookie
0x180003e56  call    __security_check_cookie
0x180003e5b  add     rsp, 70h
0x180003e5f  pop     rbx
0x180003e60  retn
```
