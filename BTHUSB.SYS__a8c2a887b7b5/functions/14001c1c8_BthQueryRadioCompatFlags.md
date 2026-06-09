# BthQueryRadioCompatFlags

- ea: `0x14001c1c8`
- end: `0x14001c287`
- name: `BthQueryRadioCompatFlags`
- size: `191`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140017858`
- `0x14001946c`

## callees

- `0x14001c1c8`
- `0x14001c290`
- `0x14001c478`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001c20a`
- `ntoskrnl!ExAllocatePool2` at `0x14001c20a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c259`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c259`
- `ntoskrnl!ObfDereferenceObject` at `0x14001c26f`
- `ntoskrnl!ObfDereferenceObject` at `0x14001c26f`
- `ntoskrnl!KseQueryDeviceFlags` at `0x14001c245`
- `ntoskrnl!KseQueryDeviceFlags` at `0x14001c245`

## pseudocode

```c
__int64 __fastcall BthQueryRadioCompatFlags(__int64 a1, struct _DEVICE_OBJECT *a2)
{
  wchar_t *Pool2; // rax
  wchar_t *v3; // rbx
  PDEVICE_OBJECT v5; // [rsp+38h] [rbp+10h] BYREF
  PVOID Object; // [rsp+40h] [rbp+18h] BYREF
  __int64 v7; // [rsp+48h] [rbp+20h] BYREF

  v5 = a2;
  Object = 0;
  v7 = 0;
  if ( a2 || (int)GetBthportDeviceObject((PFILE_OBJECT *)&Object, &v5) >= 0 )
  {
    Pool2 = (wchar_t *)ExAllocatePool2(256, 552, 1128551490);
    v3 = Pool2;
    if ( Pool2 )
    {
      if ( (int)GetRadioFingerprintString(Pool2) >= 0 )
        KseQueryDeviceFlags(v3, L"BthRadioHci", &v7);
      ExFreePoolWithTag(v3, 0x43445442u);
    }
  }
  if ( Object )
    ObfDereferenceObject(Object);
  return v7;
}

```

## disassembly

```asm
0x14001c1c8  mov     rax, rsp
0x14001c1cb  mov     [rax+10h], rdx
0x14001c1cf  push    rbx
0x14001c1d0  sub     rsp, 20h
0x14001c1d4  mov     qword ptr [rax+18h], 0
0x14001c1dc  mov     qword ptr [rax+20h], 0
0x14001c1e4  test    rdx, rdx
0x14001c1e7  jnz     short loc_14001C1FA
0x14001c1e9  lea     rdx, [rax+10h]; DeviceObject
0x14001c1ed  lea     rcx, [rax+18h]; FileObject
0x14001c1f1  call    GetBthportDeviceObject
0x14001c1f6  test    eax, eax
0x14001c1f8  js      short loc_14001C265
0x14001c1fa  mov     edx, 228h
0x14001c1ff  mov     ecx, 100h
0x14001c204  mov     r8d, 43445442h
0x14001c20a  call    cs:__imp_ExAllocatePool2
0x14001c211  nop     dword ptr [rax+rax+00h]
0x14001c216  mov     rbx, rax
0x14001c219  test    rax, rax
0x14001c21c  jz      short loc_14001C265
0x14001c21e  mov     r8, [rsp+28h+arg_8]
0x14001c223  lea     rdx, aBthradiohci; "BthRadioHci"
0x14001c22a  mov     rcx, rax; pszDest
0x14001c22d  call    GetRadioFingerprintString
0x14001c232  test    eax, eax
0x14001c234  js      short loc_14001C251
0x14001c236  lea     r8, [rsp+28h+arg_18]
0x14001c23b  mov     rcx, rbx
0x14001c23e  lea     rdx, aBthradiohci; "BthRadioHci"
0x14001c245  call    cs:__imp_KseQueryDeviceFlags
0x14001c24c  nop     dword ptr [rax+rax+00h]
0x14001c251  mov     edx, 43445442h; Tag
0x14001c256  mov     rcx, rbx; P
0x14001c259  call    cs:__imp_ExFreePoolWithTag
0x14001c260  nop     dword ptr [rax+rax+00h]
0x14001c265  mov     rcx, [rsp+28h+Object]; Object
0x14001c26a  test    rcx, rcx
0x14001c26d  jz      short loc_14001C27B
0x14001c26f  call    cs:__imp_ObfDereferenceObject
0x14001c276  nop     dword ptr [rax+rax+00h]
0x14001c27b  mov     rax, [rsp+28h+arg_18]
0x14001c280  add     rsp, 20h
0x14001c284  pop     rbx
0x14001c285  retn
```
