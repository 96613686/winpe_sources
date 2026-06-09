# TryRegisterApoOnDeviceClass(ushort const *,CO_DEVICE_CATALOG_COOKIE__ * *)

- ea: `0x140045ac8`
- end: `0x140045b79`
- name: `?TryRegisterApoOnDeviceClass@@YAJPEBGPEAPEAUCO_DEVICE_CATALOG_COOKIE__@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct CO_DEVICE_CATALOG_COOKIE__ **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x140045444`

## callees

- `0x14000c33c`
- `0x140045ac8`
- `0x140045b80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140045b1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140045b61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140045b1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140045b61`
- `api-ms-win-core-com-l1-1-3!CoRegisterDeviceCatalog` at `0x140045b48`
- `api-ms-win-core-com-l1-1-3!CoRegisterDeviceCatalog` at `0x140045b48`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TryRegisterApoOnDeviceClass(const unsigned __int16 *a1, struct CO_DEVICE_CATALOG_COOKIE__ **a2)
{
  int DeviceInstanceId; // ebx
  void *v4; // rcx
  void *v5; // rcx
  bool v6; // zf
  unsigned __int16 *v8; // [rsp+28h] [rbp-18h] BYREF
  char v9; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  LPVOID pv; // [rsp+60h] [rbp+20h] BYREF

  pv = 0;
  v8 = 0;
  v9 = 1;
  DeviceInstanceId = GetDeviceInstanceId(a1, &v8);
  if ( v9 )
  {
    v4 = pv;
    pv = v8;
    if ( v4 )
      CoTaskMemFree(v4);
  }
  if ( DeviceInstanceId >= 0 )
    DeviceInstanceId = CoRegisterDeviceCatalog(pv, a2);
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x65,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\systemeffectwrapper.cpp",
      (const char *)(unsigned int)DeviceInstanceId,
      (int)&pv);
  v5 = pv;
  v6 = pv == 0;
  pv = 0;
  if ( !v6 )
    CoTaskMemFree(v5);
  return (unsigned int)DeviceInstanceId;
}

```

## disassembly

```asm
0x140045ac8  mov     [rsp-8+arg_0], rbx
0x140045acd  mov     [rsp-8+arg_8], rdi
0x140045ad2  push    rbp
0x140045ad3  mov     rbp, rsp
0x140045ad6  sub     rsp, 40h
0x140045ada  mov     rdi, rdx
0x140045add  mov     [rbp+pv], 0
0x140045ae5  lea     rax, [rbp+pv]
0x140045ae9  mov     [rbp+var_20], rax
0x140045aed  mov     [rbp+var_18], 0
0x140045af5  mov     [rbp+var_10], 1
0x140045af9  lea     rdx, [rbp+var_18]; unsigned __int16 **
0x140045afd  call    ?GetDeviceInstanceId@@YAJPEBGPEAPEAG@Z; GetDeviceInstanceId(ushort const *,ushort * *)
0x140045b02  mov     ebx, eax
0x140045b04  cmp     [rbp+var_10], 0
0x140045b08  jz      short loc_140045B23
0x140045b0a  mov     r8, [rbp+var_20]
0x140045b0e  mov     rcx, [r8]; pv
0x140045b11  mov     rdx, [rbp+var_18]
0x140045b15  mov     [r8], rdx
0x140045b18  test    rcx, rcx
0x140045b1b  jz      short loc_140045B23
0x140045b1d  call    cs:__imp_CoTaskMemFree
0x140045b23  test    ebx, ebx
0x140045b25  jns     short loc_140045B41
0x140045b27  mov     rcx, [rbp+8]; this
0x140045b2b  mov     r9d, ebx; char *
0x140045b2e  lea     r8, aAvcoreAudiocor_28; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140045b35  mov     edx, 65h ; 'e'; void *
0x140045b3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140045b3f  jmp     short loc_140045B50
0x140045b41  mov     rdx, rdi
0x140045b44  mov     rcx, [rbp+pv]
0x140045b48  call    cs:__imp_CoRegisterDeviceCatalog
0x140045b4e  mov     ebx, eax
0x140045b50  mov     rcx, [rbp+pv]; pv
0x140045b54  test    rcx, rcx
0x140045b57  mov     [rbp+pv], 0
0x140045b5f  jz      short loc_140045B67
0x140045b61  call    cs:__imp_CoTaskMemFree
0x140045b67  mov     eax, ebx
0x140045b69  mov     rbx, [rsp+40h+arg_0]
0x140045b6e  mov     rdi, [rsp+40h+arg_8]
0x140045b73  add     rsp, 40h
0x140045b77  pop     rbp
0x140045b78  retn
```
