# DMCSP_DevDetail_GetDeviceType

- ea: `0x1800085c0`
- end: `0x180008609`
- name: `DMCSP_DevDetail_GetDeviceType`
- size: `73`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180008020`
- `0x1800080f8`
- `0x1800085c0`

## string_xrefs

- `0x1800085e7`: `SystemProductName`

## pseudocode

```c
__int64 __fastcall DMCSP_DevDetail_GetDeviceType(unsigned int a1, unsigned __int16 *a2)
{
  __int64 result; // rax

  result = QueryOneCoreInformation(L"OneCoreManufacturerModelName", a1, a2);
  if ( (int)result < 0 )
    return RegLookupHelper(L"SYSTEM\\CurrentControlSet\\Control\\SystemInformation", L"SystemProductName", a1, a2);
  return result;
}

```

## disassembly

```asm
0x1800085c0  mov     [rsp+arg_0], rbx
0x1800085c5  push    rdi
0x1800085c6  sub     rsp, 20h
0x1800085ca  mov     rbx, rdx
0x1800085cd  mov     r8, rdx; unsigned __int16 *
0x1800085d0  mov     edx, ecx; unsigned int
0x1800085d2  mov     edi, ecx
0x1800085d4  lea     rcx, aOnecoremanufac_0; "OneCoreManufacturerModelName"
0x1800085db  call    ?QueryOneCoreInformation@@YAJPEBGKPEAG@Z; QueryOneCoreInformation(ushort const *,ulong,ushort *)
0x1800085e0  test    eax, eax
0x1800085e2  jns     short loc_1800085FD
0x1800085e4  mov     r9, rbx; unsigned __int16 *
0x1800085e7  lea     rdx, aSystemproductn; "SystemProductName"
0x1800085ee  mov     r8d, edi; unsigned int
0x1800085f1  lea     rcx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Sys"...
0x1800085f8  call    ?RegLookupHelper@@YAJPEBG0KPEAG@Z; RegLookupHelper(ushort const *,ushort const *,ulong,ushort *)
0x1800085fd  mov     rbx, [rsp+28h+arg_0]
0x180008602  add     rsp, 20h
0x180008606  pop     rdi
0x180008607  retn
```
