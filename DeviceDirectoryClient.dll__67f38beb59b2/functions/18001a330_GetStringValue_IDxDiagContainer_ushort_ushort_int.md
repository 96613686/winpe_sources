# GetStringValue(IDxDiagContainer *,ushort *,ushort *,int)

- ea: `0x18001a330`
- end: `0x18001a411`
- name: `?GetStringValue@@YAJPEAUIDxDiagContainer@@PEAG1H@Z`
- size: `225`
- prototype: `__int64 __fastcall(struct IDxDiagContainer *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180018c8c`

## callees

- `0x1800050b8`
- `0x18001a330`
- `0x18002a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001a3e5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001a3e5`
- `OLEAUT32!__imp_VariantInit` at `0x18001a35b`
- `OLEAUT32!__imp_VariantInit` at `0x18001a35b`
- `OLEAUT32!__imp_VariantClear` at `0x18001a3f9`
- `OLEAUT32!__imp_VariantClear` at `0x18001a3f9`

## string_xrefs

- `0x18001a39b`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`

## pseudocode

```c
__int64 __fastcall GetStringValue(struct IDxDiagContainer *a1, unsigned __int16 *a2, unsigned __int16 *a3)
{
  int v6; // edx
  int v7; // ecx
  int v8; // ebx
  VARIANTARG pvarg; // [rsp+30h] [rbp-28h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v8 = ((__int64 (__fastcall *)(struct IDxDiagContainer *, unsigned __int16 *, VARIANTARG *))a1->lpVtbl->GetPropA)(
         a1,
         a2,
         &pvarg);
  if ( v8 >= 0 )
  {
    if ( pvarg.vt == 8 )
    {
      _o_wcscpy_s(a3, 259, pvarg.llVal);
      a3[259] = 0;
      VariantClear(&pvarg);
    }
    else
    {
      v8 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v7,
          v6,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          253,
          "CBR(var.vt == VT_BSTR)");
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v7,
      v6,
      v8,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
      252,
      "CHR(pObject->GetPropW( wstrName, &var ))");
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001a330  mov     r11, rsp
0x18001a333  mov     [r11+8], rbx
0x18001a337  mov     [r11+10h], rsi
0x18001a33b  push    rdi
0x18001a33c  sub     rsp, 50h
0x18001a340  xorps   xmm0, xmm0
0x18001a343  mov     rdi, rcx
0x18001a346  xor     eax, eax
0x18001a348  lea     rcx, [r11-28h]; pvarg
0x18001a34c  movups  xmmword ptr [rsp+58h+pvarg], xmm0
0x18001a351  mov     [r11-18h], rax
0x18001a355  mov     rsi, r8
0x18001a358  mov     rbx, rdx
0x18001a35b  call    cs:__imp_VariantInit
0x18001a361  mov     rax, [rdi]
0x18001a364  lea     r8, [rsp+58h+pvarg]
0x18001a369  mov     rdx, rbx
0x18001a36c  mov     rcx, rdi
0x18001a36f  mov     rax, [rax+40h]
0x18001a373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a378  mov     ebx, eax
0x18001a37a  test    eax, eax
0x18001a37c  jns     short loc_18001A3AC
0x18001a37e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001a385  jz      short loc_18001A3FF
0x18001a387  lea     rax, aChrPobjectGetp; "CHR(pObject->GetPropW( wstrName, &var )"...
0x18001a38e  mov     [rsp+58h+var_30], rax
0x18001a393  mov     [rsp+58h+var_38], 6FCh
0x18001a39b  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001a3a2  mov     r8d, ebx
0x18001a3a5  call    McTemplateU0dsqs_EventWriteTransfer
0x18001a3aa  jmp     short loc_18001A3FF
0x18001a3ac  cmp     word ptr [rsp+58h+pvarg], 8
0x18001a3b2  jz      short loc_18001A3D8
0x18001a3b4  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001a3bb  mov     ebx, 80070057h
0x18001a3c0  jz      short loc_18001A3FF
0x18001a3c2  lea     rax, aCbrVarVtVtBstr; "CBR(var.vt == VT_BSTR)"
0x18001a3c9  mov     [rsp+58h+var_30], rax
0x18001a3ce  mov     [rsp+58h+var_38], 6FDh
0x18001a3d6  jmp     short loc_18001A39B
0x18001a3d8  mov     r8, qword ptr [rsp+58h+pvarg+8]
0x18001a3dd  mov     edx, 103h
0x18001a3e2  mov     rcx, rsi
0x18001a3e5  call    cs:__imp__o_wcscpy_s
0x18001a3eb  xor     eax, eax
0x18001a3ed  lea     rcx, [rsp+58h+pvarg]; pvarg
0x18001a3f2  mov     [rsi+206h], ax
0x18001a3f9  call    cs:__imp_VariantClear
0x18001a3ff  mov     rsi, [rsp+58h+arg_8]
0x18001a404  mov     eax, ebx
0x18001a406  mov     rbx, [rsp+58h+arg_0]
0x18001a40b  add     rsp, 50h
0x18001a40f  pop     rdi
0x18001a410  retn
```
