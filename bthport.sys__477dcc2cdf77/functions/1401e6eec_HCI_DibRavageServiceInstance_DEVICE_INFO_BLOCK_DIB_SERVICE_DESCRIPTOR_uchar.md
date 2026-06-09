# HCI_DibRavageServiceInstance(DEVICE_INFO_BLOCK *,_DIB_SERVICE_DESCRIPTOR *,uchar)

- ea: `0x1401e6eec`
- end: `0x1401e7091`
- name: `?HCI_DibRavageServiceInstance@@YAJPEAUDEVICE_INFO_BLOCK@@PEAU_DIB_SERVICE_DESCRIPTOR@@E@Z`
- size: `421`
- prototype: `int(struct DEVICE_INFO_BLOCK *, struct _DIB_SERVICE_DESCRIPTOR *, unsigned __int8)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1401e629c`

## callees

- `0x1401c18d0`
- `0x1401c1aec`
- `0x1401c1b90`
- `0x1401c1c04`
- `0x1401e6eec`

## import_xrefs

- `ntoskrnl!ZwDeleteKey` at `0x1401e700e`
- `ntoskrnl!ZwDeleteKey` at `0x1401e7024`
- `ntoskrnl!ZwDeleteKey` at `0x1401e700e`
- `ntoskrnl!ZwDeleteKey` at `0x1401e7024`
- `ntoskrnl!ZwClose` at `0x1401e6f81`
- `ntoskrnl!ZwClose` at `0x1401e6fb2`
- `ntoskrnl!ZwClose` at `0x1401e6fe5`
- `ntoskrnl!ZwClose` at `0x1401e6ff5`
- `ntoskrnl!ZwClose` at `0x1401e7045`
- `ntoskrnl!ZwClose` at `0x1401e7055`
- `ntoskrnl!ZwClose` at `0x1401e7065`
- `ntoskrnl!ZwClose` at `0x1401e7075`
- `ntoskrnl!ZwClose` at `0x1401e6f81`
- `ntoskrnl!ZwClose` at `0x1401e6fb2`
- `ntoskrnl!ZwClose` at `0x1401e6fe5`
- `ntoskrnl!ZwClose` at `0x1401e6ff5`
- `ntoskrnl!ZwClose` at `0x1401e7045`
- `ntoskrnl!ZwClose` at `0x1401e7055`
- `ntoskrnl!ZwClose` at `0x1401e7065`
- `ntoskrnl!ZwClose` at `0x1401e7075`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401e6f4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401e7035`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401e6f4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401e7035`

## pseudocode

```c
__int64 __fastcall HCI_DibRavageServiceInstance(struct DEVICE_INFO_BLOCK *a1, struct _GUID *a2)
{
  NTSTATUS DeviceKey; // edi
  HANDLE v5; // rcx
  HANDLE v7; // [rsp+30h] [rbp-20h] BYREF
  HANDLE KeyHandle; // [rsp+38h] [rbp-18h] BYREF
  __int128 v9; // [rsp+40h] [rbp-10h]
  HANDLE Handle; // [rsp+70h] [rbp+20h] BYREF
  unsigned int v11; // [rsp+80h] [rbp+30h] BYREF
  HANDLE v12; // [rsp+88h] [rbp+38h] BYREF

  v11 = 0;
  Handle = 0;
  v12 = 0;
  v7 = 0;
  KeyHandle = 0;
  v9 = 0;
  DeviceKey = HCI_GetDeviceKey(&a1->DeviceInfo.address, &Handle, 0);
  if ( DeviceKey < 0 )
    goto LABEL_2;
  DeviceKey = HCI_GetServicesForKey(Handle, a1->Hci, &v12, 0);
  if ( DeviceKey < 0 )
  {
    v5 = Handle;
LABEL_5:
    ZwClose(v5);
LABEL_2:
    ExFreePoolWithTag(a2, 0);
    return (unsigned int)DeviceKey;
  }
  DeviceKey = HCI_GetServiceGuidKey(v12, a2, &v7, &v11, 0);
  if ( DeviceKey < 0 )
  {
    ZwClose(Handle);
    v5 = v12;
    goto LABEL_5;
  }
  DeviceKey = HCI_GetServiceInstanceKey(v7, &a2[17].Data2, &KeyHandle, 0);
  if ( DeviceKey < 0 )
  {
    ZwClose(Handle);
    ZwClose(v12);
    v5 = v7;
    goto LABEL_5;
  }
  DeviceKey = ZwDeleteKey(KeyHandle);
  if ( DeviceKey >= 0 )
    ZwDeleteKey(v7);
  ExFreePoolWithTag(a2, 0);
  ZwClose(Handle);
  ZwClose(v12);
  ZwClose(v7);
  ZwClose(KeyHandle);
  return (unsigned int)DeviceKey;
}

```

## disassembly

```asm
0x1401e6eec  mov     [rsp-18h+arg_8], rbx
0x1401e6ef1  mov     byte ptr [rsp-18h+arg_10], r8b
0x1401e6ef6  push    rbp
0x1401e6ef7  push    rsi
0x1401e6ef8  push    rdi
0x1401e6ef9  mov     rbp, rsp
0x1401e6efc  sub     rsp, 50h
0x1401e6f00  mov     rbx, rdx
0x1401e6f03  mov     [rbp+arg_10], 0
0x1401e6f0a  mov     rsi, rcx
0x1401e6f0d  mov     [rbp+Handle], 0
0x1401e6f15  xorps   xmm0, xmm0
0x1401e6f18  mov     [rbp+arg_18], 0
0x1401e6f20  add     rcx, 20h ; ' '; unsigned __int64 *
0x1401e6f24  mov     [rbp+var_20], 0
0x1401e6f2c  lea     rdx, [rbp+Handle]; void **
0x1401e6f30  mov     [rbp+KeyHandle], 0
0x1401e6f38  xor     r8d, r8d; unsigned __int8
0x1401e6f3b  movups  [rbp+var_10], xmm0
0x1401e6f3f  call    ?HCI_GetDeviceKey@@YAJPEB_KPEAPEAXE@Z; HCI_GetDeviceKey(unsigned __int64 const *,void * *,uchar)
0x1401e6f44  mov     edi, eax
0x1401e6f46  test    eax, eax
0x1401e6f48  jns     short loc_1401E6F60
0x1401e6f4a  xor     edx, edx; Tag
0x1401e6f4c  mov     rcx, rbx; P
0x1401e6f4f  call    cs:__imp_ExFreePoolWithTag
0x1401e6f56  nop     dword ptr [rax+rax+00h]
0x1401e6f5b  jmp     loc_1401E7081
0x1401e6f60  mov     rdx, [rsi+378h]; struct HCI_INTERFACE *
0x1401e6f67  lea     r8, [rbp+arg_18]; void **
0x1401e6f6b  mov     rcx, [rbp+Handle]; void *
0x1401e6f6f  xor     r9d, r9d; unsigned __int8
0x1401e6f72  call    ?HCI_GetServicesForKey@@YAJPEAXPEAUHCI_INTERFACE@@PEAPEAXE@Z; HCI_GetServicesForKey(void *,HCI_INTERFACE *,void * *,uchar)
0x1401e6f77  mov     edi, eax
0x1401e6f79  test    eax, eax
0x1401e6f7b  jns     short loc_1401E6F8F
0x1401e6f7d  mov     rcx, [rbp+Handle]; Handle
0x1401e6f81  call    cs:__imp_ZwClose
0x1401e6f88  nop     dword ptr [rax+rax+00h]
0x1401e6f8d  jmp     short loc_1401E6F4A
0x1401e6f8f  mov     rcx, [rbp+arg_18]; void *
0x1401e6f93  lea     r9, [rbp+arg_10]; unsigned int *
0x1401e6f97  lea     r8, [rbp+var_20]; void **
0x1401e6f9b  mov     [rsp+50h+var_30], 0; unsigned __int8
0x1401e6fa0  mov     rdx, rbx; struct _GUID *
0x1401e6fa3  call    ?HCI_GetServiceGuidKey@@YAJPEAXAEBU_GUID@@PEAPEAXPEAKE@Z; HCI_GetServiceGuidKey(void *,_GUID const &,void * *,ulong *,uchar)
0x1401e6fa8  mov     edi, eax
0x1401e6faa  test    eax, eax
0x1401e6fac  jns     short loc_1401E6FC4
0x1401e6fae  mov     rcx, [rbp+Handle]; Handle
0x1401e6fb2  call    cs:__imp_ZwClose
0x1401e6fb9  nop     dword ptr [rax+rax+00h]
0x1401e6fbe  mov     rcx, [rbp+arg_18]
0x1401e6fc2  jmp     short loc_1401E6F81
0x1401e6fc4  mov     rcx, [rbp+var_20]; void *
0x1401e6fc8  lea     rdx, [rbx+114h]; unsigned __int16 *
0x1401e6fcf  xor     r9d, r9d; unsigned __int8
0x1401e6fd2  lea     r8, [rbp+KeyHandle]; void **
0x1401e6fd6  call    ?HCI_GetServiceInstanceKey@@YAJPEAXPEAGPEAPEAXE@Z; HCI_GetServiceInstanceKey(void *,ushort *,void * *,uchar)
0x1401e6fdb  mov     edi, eax
0x1401e6fdd  test    eax, eax
0x1401e6fdf  jns     short loc_1401E700A
0x1401e6fe1  mov     rcx, [rbp+Handle]; Handle
0x1401e6fe5  call    cs:__imp_ZwClose
0x1401e6fec  nop     dword ptr [rax+rax+00h]
0x1401e6ff1  mov     rcx, [rbp+arg_18]; Handle
0x1401e6ff5  call    cs:__imp_ZwClose
0x1401e6ffc  nop     dword ptr [rax+rax+00h]
0x1401e7001  mov     rcx, [rbp+var_20]
0x1401e7005  jmp     loc_1401E6F81
0x1401e700a  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1401e700e  call    cs:__imp_ZwDeleteKey
0x1401e7015  nop     dword ptr [rax+rax+00h]
0x1401e701a  mov     edi, eax
0x1401e701c  test    eax, eax
0x1401e701e  js      short loc_1401E7030
0x1401e7020  mov     rcx, [rbp+var_20]; KeyHandle
0x1401e7024  call    cs:__imp_ZwDeleteKey
0x1401e702b  nop     dword ptr [rax+rax+00h]
0x1401e7030  xor     edx, edx; Tag
0x1401e7032  mov     rcx, rbx; P
0x1401e7035  call    cs:__imp_ExFreePoolWithTag
0x1401e703c  nop     dword ptr [rax+rax+00h]
0x1401e7041  mov     rcx, [rbp+Handle]; Handle
0x1401e7045  call    cs:__imp_ZwClose
0x1401e704c  nop     dword ptr [rax+rax+00h]
0x1401e7051  mov     rcx, [rbp+arg_18]; Handle
0x1401e7055  call    cs:__imp_ZwClose
0x1401e705c  nop     dword ptr [rax+rax+00h]
0x1401e7061  mov     rcx, [rbp+var_20]; Handle
0x1401e7065  call    cs:__imp_ZwClose
0x1401e706c  nop     dword ptr [rax+rax+00h]
0x1401e7071  mov     rcx, [rbp+KeyHandle]; Handle
0x1401e7075  call    cs:__imp_ZwClose
0x1401e707c  nop     dword ptr [rax+rax+00h]
0x1401e7081  mov     rbx, [rsp+50h+arg_8]
0x1401e7086  mov     eax, edi
0x1401e7088  add     rsp, 50h
0x1401e708c  pop     rdi
0x1401e708d  pop     rsi
0x1401e708e  pop     rbp
0x1401e708f  retn
```
