# BthQueryDeviceCompatFlags

- ea: `0x14002f6d0`
- end: `0x14002f7a8`
- name: `BthQueryDeviceCompatFlags`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14002b5a0`

## callees

- `0x14002f6d0`
- `0x14002f7b0`
- `0x14002faa4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002f723`
- `ntoskrnl!ExAllocatePool2` at `0x14002f723`
- `ntoskrnl!ObfDereferenceObject` at `0x14002f78b`
- `ntoskrnl!ObfDereferenceObject` at `0x14002f78b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f775`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f775`
- `ntoskrnl!KseQueryDeviceFlags` at `0x14002f761`
- `ntoskrnl!KseQueryDeviceFlags` at `0x14002f761`

## pseudocode

```c
__int64 __fastcall BthQueryDeviceCompatFlags(__int64 a1)
{
  __int64 Pool2; // rax
  void *v3; // rbx
  PDEVICE_OBJECT v5; // [rsp+20h] [rbp-18h] BYREF
  __int64 v6; // [rsp+40h] [rbp+8h] BYREF
  PVOID Object; // [rsp+50h] [rbp+18h] BYREF

  v5 = 0;
  Object = 0;
  v6 = 0;
  if ( a1 )
  {
    if ( (int)GetBthportDeviceObject((PFILE_OBJECT *)&Object, &v5) >= 0 )
    {
      Pool2 = ExAllocatePool2(256, 300, 1128551490);
      v3 = (void *)Pool2;
      if ( Pool2 )
      {
        if ( (int)GetDeviceFingerprintString(a1, Pool2, L"BthDeviceHfp", v5) >= 0 )
          KseQueryDeviceFlags(v3, L"BthDeviceHfp", &v6);
        ExFreePoolWithTag(v3, 0x43445442u);
      }
    }
    if ( Object )
      ObfDereferenceObject(Object);
  }
  return v6;
}

```

## disassembly

```asm
0x14002f6d0  mov     rax, rsp
0x14002f6d3  mov     [rax+10h], rbx
0x14002f6d7  mov     [rax+18h], r8
0x14002f6db  push    rdi
0x14002f6dc  sub     rsp, 30h
0x14002f6e0  mov     qword ptr [rax-18h], 0
0x14002f6e8  mov     rdi, rcx
0x14002f6eb  mov     qword ptr [rax+18h], 0
0x14002f6f3  mov     qword ptr [rax+8], 0
0x14002f6fb  test    rcx, rcx
0x14002f6fe  jz      loc_14002F797
0x14002f704  lea     rdx, [rax-18h]; DeviceObject
0x14002f708  lea     rcx, [rax+18h]; FileObject
0x14002f70c  call    GetBthportDeviceObject
0x14002f711  test    eax, eax
0x14002f713  js      short loc_14002F781
0x14002f715  mov     edx, 12Ch
0x14002f71a  mov     r8d, 43445442h
0x14002f720  lea     ecx, [rdx-2Ch]
0x14002f723  call    cs:__imp_ExAllocatePool2
0x14002f72a  nop     dword ptr [rax+rax+00h]
0x14002f72f  mov     rbx, rax
0x14002f732  test    rax, rax
0x14002f735  jz      short loc_14002F781
0x14002f737  mov     r9, [rsp+38h+var_18]
0x14002f73c  lea     r8, aBthdevicehfp; "BthDeviceHfp"
0x14002f743  mov     rdx, rax
0x14002f746  mov     rcx, rdi
0x14002f749  call    GetDeviceFingerprintString
0x14002f74e  test    eax, eax
0x14002f750  js      short loc_14002F76D
0x14002f752  lea     r8, [rsp+38h+arg_0]
0x14002f757  mov     rcx, rbx
0x14002f75a  lea     rdx, aBthdevicehfp; "BthDeviceHfp"
0x14002f761  call    cs:__imp_KseQueryDeviceFlags
0x14002f768  nop     dword ptr [rax+rax+00h]
0x14002f76d  mov     edx, 43445442h; Tag
0x14002f772  mov     rcx, rbx; P
0x14002f775  call    cs:__imp_ExFreePoolWithTag
0x14002f77c  nop     dword ptr [rax+rax+00h]
0x14002f781  mov     rcx, [rsp+38h+Object]; Object
0x14002f786  test    rcx, rcx
0x14002f789  jz      short loc_14002F797
0x14002f78b  call    cs:__imp_ObfDereferenceObject
0x14002f792  nop     dword ptr [rax+rax+00h]
0x14002f797  mov     rax, [rsp+38h+arg_0]
0x14002f79c  mov     rbx, [rsp+38h+arg_8]
0x14002f7a1  add     rsp, 30h
0x14002f7a5  pop     rdi
0x14002f7a6  retn
```
