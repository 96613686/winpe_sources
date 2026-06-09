# FltpGetLegacyInstanceInformation

- ea: `0x1800509d0`
- end: `0x180050d24`
- name: `FltpGetLegacyInstanceInformation`
- size: `852`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path`

## callers

- `0x1800753c0`

## callees

- `0x180009f20`
- `0x180024800`
- `0x180024940`
- `0x180024c40`
- `0x1800509d0`
- `0x18005224c`
- `0x18005c5a0`
- `0x180064e80`
- `0x180067b00`
- `0x18006aef0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x180050ccd`
- `ntoskrnl!ObfDereferenceObject` at `0x180050ce1`
- `ntoskrnl!ObfDereferenceObject` at `0x180050ccd`
- `ntoskrnl!ObfDereferenceObject` at `0x180050ce1`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180050bfc`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180050c5c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180050bfc`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180050c5c`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x180050ab0`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x180050ab0`
- `ntoskrnl!IoGetDiskDeviceObject` at `0x180050ac7`
- `ntoskrnl!IoGetDiskDeviceObject` at `0x180050ac7`

## pseudocode

```c
__int64 __fastcall FltpGetLegacyInstanceInformation(
        PDEVICE_OBJECT DeviceObject,
        int a2,
        __int64 a3,
        unsigned int a4,
        unsigned int *a5)
{
  struct _DRIVER_OBJECT *DriverObject; // r13
  unsigned int CharReverse; // eax
  unsigned __int16 Length; // r15
  struct _DEVICE_OBJECT *DeviceAttachmentBaseRef; // r14
  unsigned int v12; // eax
  struct _DEVICE_OBJECT *v13; // rcx
  unsigned int ObjectName; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  unsigned int v17; // ebx
  const UNICODE_STRING *v18; // rax
  const UNICODE_STRING *v19; // rsi
  unsigned __int16 v20; // ax
  unsigned __int16 v21; // r8
  unsigned __int16 v22; // cx
  unsigned int v23; // r12d
  PDEVICE_OBJECT v24; // rax
  PVPB Vpb; // rdx
  unsigned __int16 v26; // bx
  unsigned __int16 v27; // bx
  unsigned __int16 v28; // ax
  __int64 v29; // rbx
  __int16 v31[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v32; // [rsp+34h] [rbp-CCh]
  PDEVICE_OBJECT DiskDeviceObject; // [rsp+38h] [rbp-C8h] BYREF
  void *Src; // [rsp+40h] [rbp-C0h] BYREF
  UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int *v36; // [rsp+58h] [rbp-A8h]
  UNICODE_STRING SourceString[18]; // [rsp+60h] [rbp-A0h] BYREF

  v36 = a5;
  DiskDeviceObject = 0;
  Src = 0;
  v31[0] = 0;
  v32 = a4;
  DestinationString = 0;
  memset(SourceString, 0, sizeof(SourceString));
  *a5 = 0;
  DriverObject = DeviceObject->DriverObject;
  CharReverse = FltpFindCharReverse(
                  DriverObject->DriverName.Buffer,
                  DriverObject->DriverName.Length,
                  92,
                  (unsigned int)&Src,
                  (__int64)v31);
  if ( (int)FltpDbgStatus(CharReverse, "minkernel\\fs\\filtermgr\\filter\\enumerationsup.c", 4772, 0) < 0 )
  {
    Length = DriverObject->DriverName.Length;
    Src = DriverObject->DriverName.Buffer;
  }
  else
  {
    Length = v31[0] - 2;
    Src = (char *)Src + 2;
  }
  DeviceAttachmentBaseRef = IoGetDeviceAttachmentBaseRef(DeviceObject);
  v12 = IoGetDiskDeviceObject(DeviceAttachmentBaseRef, &DiskDeviceObject);
  if ( (int)FltpDbgStatus(v12, "minkernel\\fs\\filtermgr\\filter\\enumerationsup.c", 4807, 0) >= 0 )
  {
    v13 = DiskDeviceObject;
  }
  else
  {
    v13 = DeviceAttachmentBaseRef;
    DeviceAttachmentBaseRef = 0;
    DiskDeviceObject = v13;
  }
  *(_DWORD *)&SourceString[1].Length = 0;
  *(_QWORD *)&SourceString[0].Length = 16646144;
  *(_QWORD *)(&SourceString[1].MaximumLength + 1) = 254;
  SourceString[0].Buffer = (wchar_t *)&SourceString[1].Buffer + 2;
  ObjectName = FltpGetObjectName(v13);
  if ( (int)FltpDbgStatus(ObjectName, "minkernel\\fs\\filtermgr\\filter\\enumerationsup.c", 4818, 0) < 0 )
    SourceString[0].Length = 0;
  if ( a2 == 3 )
  {
    v18 = (const UNICODE_STRING *)FltpCalculateLegacyFilterAltitude(DriverObject, v15, v16, 0);
    v19 = v18;
    if ( v18 )
      v20 = v18->Length;
    else
      v20 = 0;
    v21 = SourceString[0].Length;
    v22 = v20 + SourceString[0].Length + Length;
    v23 = (unsigned __int16)(v22 + 28);
    if ( v32 >= v23 )
    {
      v24 = DiskDeviceObject;
      *(_DWORD *)a3 = 0;
      *(_QWORD *)(a3 + 4) = 2;
      Vpb = v24->Vpb;
      if ( Vpb && Vpb->DeviceObject != DeviceAttachmentBaseRef )
        *(_DWORD *)(a3 + 8) = 1;
      if ( v19 )
      {
        DestinationString.MaximumLength = v22;
        DestinationString.Buffer = (wchar_t *)(a3 + 28);
        DestinationString.Length = 0;
        RtlCopyUnicodeString(&DestinationString, v19);
        v26 = v19->Length;
        v21 = SourceString[0].Length;
      }
      else
      {
        v26 = 0;
      }
      *(_WORD *)(a3 + 12) = v26;
      v27 = v26 + 28;
      *(_WORD *)(a3 + 14) = 28;
      LOWORD(v32) = v27;
      if ( v21 )
      {
        DestinationString.Length = 0;
        DestinationString.MaximumLength = v23 - v27;
        DestinationString.Buffer = (wchar_t *)(a3 + v27);
        RtlCopyUnicodeString(&DestinationString, SourceString);
        v28 = SourceString[0].Length;
        *(_WORD *)(a3 + 16) = SourceString[0].Length;
      }
      else
      {
        *(_WORD *)(a3 + 16) = 0;
        v28 = 0;
      }
      *(_WORD *)(a3 + 18) = v32;
      v29 = (unsigned __int16)(v28 + v27);
      memmove((void *)(a3 + v29), Src, Length);
      *(_WORD *)(a3 + 20) = Length;
      *(_WORD *)(a3 + 22) = v29;
      *(_DWORD *)(a3 + 24) = FltpGetSupportedFeaturesValue(DriverObject, v19, 0);
      v17 = 0;
      *v36 = v23;
    }
    else
    {
      *a5 = v23;
      v17 = -1073741789;
    }
  }
  else
  {
    v17 = -1073741811;
  }
  if ( DiskDeviceObject )
    ObfDereferenceObject(DiskDeviceObject);
  if ( DeviceAttachmentBaseRef )
    ObfDereferenceObject(DeviceAttachmentBaseRef);
  FltpCleanupNameControl(SourceString);
  return v17;
}

```

## disassembly

```asm
0x1800509d0  mov     [rsp-8+arg_8], rbx
0x1800509d5  push    rbp
0x1800509d6  push    rsi
0x1800509d7  push    rdi
0x1800509d8  push    r12
0x1800509da  push    r13
0x1800509dc  push    r14
0x1800509de  push    r15
0x1800509e0  lea     rbp, [rsp-90h]
0x1800509e8  sub     rsp, 190h
0x1800509ef  mov     rax, cs:__security_cookie
0x1800509f6  xor     rax, rsp
0x1800509f9  mov     [rbp+0C0h+var_40], rax
0x180050a00  mov     rbx, [rbp+0C0h+arg_20]
0x180050a07  xor     r14d, r14d
0x180050a0a  mov     rdi, r8
0x180050a0d  mov     [rsp+1C0h+var_168], rbx
0x180050a12  mov     r12d, edx
0x180050a15  mov     [rsp+1C0h+DiskDeviceObject], r14
0x180050a1a  mov     rsi, rcx
0x180050a1d  mov     [rsp+1C0h+Src], r14
0x180050a22  xorps   xmm0, xmm0
0x180050a25  mov     [rsp+1C0h+var_190], r14w
0x180050a2b  xor     edx, edx; Val
0x180050a2d  mov     [rsp+1C0h+var_18C], r9d
0x180050a32  mov     r8d, 120h; Size
0x180050a38  lea     rcx, [rsp+1C0h+SourceString]; void *
0x180050a3d  movups  xmmword ptr [rsp+1C0h+DestinationString.Length], xmm0
0x180050a42  call    memset
0x180050a47  mov     [rbx], r14d
0x180050a4a  lea     rax, [rsp+1C0h+var_190]
0x180050a4f  mov     r13, [rsi+8]
0x180050a53  lea     r8d, [r14+5Ch]
0x180050a57  lea     r9, [rsp+1C0h+Src]
0x180050a5c  mov     [rsp+1C0h+var_1A0], rax
0x180050a61  movzx   edx, word ptr [r13+38h]
0x180050a66  mov     rcx, [r13+40h]
0x180050a6a  call    FltpFindCharReverse
0x180050a6f  mov     r8d, 12A4h
0x180050a75  lea     rdx, aMinkernelFsFil_29; "minkernel\\fs\\filtermgr\\filter\\enume"...
0x180050a7c  xor     r9d, r9d
0x180050a7f  mov     ecx, eax
0x180050a81  call    FltpDbgStatus
0x180050a86  lea     ecx, [r14+2]
0x180050a8a  test    eax, eax
0x180050a8c  js      short loc_180050A9F
0x180050a8e  movzx   r15d, [rsp+1C0h+var_190]
0x180050a94  sub     r15w, cx
0x180050a98  add     [rsp+1C0h+Src], rcx
0x180050a9d  jmp     short loc_180050AAD
0x180050a9f  mov     rax, [r13+40h]
0x180050aa3  movzx   r15d, word ptr [r13+38h]
0x180050aa8  mov     [rsp+1C0h+Src], rax
0x180050aad  mov     rcx, rsi; DeviceObject
0x180050ab0  call    cs:__imp_IoGetDeviceAttachmentBaseRef
0x180050ab7  nop     dword ptr [rax+rax+00h]
0x180050abc  mov     rcx, rax; FileSystemDeviceObject
0x180050abf  lea     rdx, [rsp+1C0h+DiskDeviceObject]; DiskDeviceObject
0x180050ac4  mov     r14, rax
0x180050ac7  call    cs:__imp_IoGetDiskDeviceObject
0x180050ace  nop     dword ptr [rax+rax+00h]
0x180050ad3  mov     r8d, 12C7h
0x180050ad9  lea     rdx, aMinkernelFsFil_29; "minkernel\\fs\\filtermgr\\filter\\enume"...
0x180050ae0  mov     ecx, eax
0x180050ae2  xor     r9d, r9d
0x180050ae5  call    FltpDbgStatus
0x180050aea  test    eax, eax
0x180050aec  jns     short loc_180050AFB
0x180050aee  mov     rcx, r14
0x180050af1  xor     r14d, r14d
0x180050af4  mov     [rsp+1C0h+DiskDeviceObject], rcx
0x180050af9  jmp     short loc_180050B00
0x180050afb  mov     rcx, [rsp+1C0h+DiskDeviceObject]; Object
0x180050b00  xorps   xmm0, xmm0
0x180050b03  mov     [rsp+1C0h+var_150], 0
0x180050b0b  movups  xmmword ptr [rsp+1C0h+SourceString.Length], xmm0
0x180050b10  mov     eax, 0FEh
0x180050b15  mov     [rsp+1C0h+var_14C], 0FEh
0x180050b1e  mov     [rsp+1C0h+SourceString.MaximumLength], ax
0x180050b23  lea     rdx, [rsp+1C0h+SourceString]
0x180050b28  lea     rax, [rsp+1C0h+var_144]
0x180050b2d  mov     [rsp+1C0h+SourceString.Buffer], rax
0x180050b32  call    FltpGetObjectName
0x180050b37  mov     r8d, 12D2h
0x180050b3d  lea     rdx, aMinkernelFsFil_29; "minkernel\\fs\\filtermgr\\filter\\enume"...
0x180050b44  xor     r9d, r9d
0x180050b47  mov     ecx, eax
0x180050b49  call    FltpDbgStatus
0x180050b4e  xor     r9d, r9d
0x180050b51  test    eax, eax
0x180050b53  jns     short loc_180050B5B
0x180050b55  mov     [rsp+1C0h+SourceString.Length], r9w
0x180050b5b  cmp     r12d, 3
0x180050b5f  jz      short loc_180050B6B
0x180050b61  mov     ebx, 0C000000Dh
0x180050b66  jmp     loc_180050CC3
0x180050b6b  mov     rcx, r13
0x180050b6e  call    FltpCalculateLegacyFilterAltitude
0x180050b73  xor     r9d, r9d
0x180050b76  mov     rsi, rax
0x180050b79  test    rax, rax
0x180050b7c  jnz     short loc_180050B83
0x180050b7e  mov     eax, r9d
0x180050b81  jmp     short loc_180050B86
0x180050b83  movzx   eax, word ptr [rax]
0x180050b86  movzx   r8d, [rsp+1C0h+SourceString.Length]
0x180050b8c  mov     r10d, 1Ch
0x180050b92  lea     ecx, [r8+r15]
0x180050b96  add     cx, ax
0x180050b99  lea     eax, [r10+rcx]
0x180050b9d  movzx   r12d, ax
0x180050ba1  cmp     [rsp+1C0h+var_18C], r12d
0x180050ba6  jnb     short loc_180050BB5
0x180050ba8  mov     [rbx], r12d
0x180050bab  mov     ebx, 0C0000023h
0x180050bb0  jmp     loc_180050CC3
0x180050bb5  mov     rax, [rsp+1C0h+DiskDeviceObject]
0x180050bba  mov     [rdi], r9d
0x180050bbd  mov     qword ptr [rdi+4], 2
0x180050bc5  mov     rdx, [rax+38h]
0x180050bc9  test    rdx, rdx
0x180050bcc  jz      short loc_180050BDB
0x180050bce  cmp     [rdx+8], r14
0x180050bd2  jz      short loc_180050BDB
0x180050bd4  mov     dword ptr [rdi+8], 1
0x180050bdb  test    rsi, rsi
0x180050bde  jz      short loc_180050C1A
0x180050be0  mov     [rsp+1C0h+DestinationString.MaximumLength], cx
0x180050be5  lea     rax, [rdi+1Ch]
0x180050be9  lea     rcx, [rsp+1C0h+DestinationString]; DestinationString
0x180050bee  mov     [rsp+1C0h+DestinationString.Buffer], rax
0x180050bf3  mov     rdx, rsi; SourceString
0x180050bf6  mov     [rsp+1C0h+DestinationString.Length], r9w
0x180050bfc  call    cs:__imp_RtlCopyUnicodeString
0x180050c03  nop     dword ptr [rax+rax+00h]
0x180050c08  movzx   ebx, word ptr [rsi]
0x180050c0b  xor     r9d, r9d
0x180050c0e  movzx   r8d, [rsp+1C0h+SourceString.Length]
0x180050c14  lea     r10d, [r9+1Ch]
0x180050c18  jmp     short loc_180050C1D
0x180050c1a  mov     ebx, r9d
0x180050c1d  mov     [rdi+0Ch], bx
0x180050c21  add     bx, r10w
0x180050c25  mov     [rdi+0Eh], r10w
0x180050c2a  mov     word ptr [rsp+1C0h+var_18C], bx
0x180050c2f  test    r8w, r8w
0x180050c33  jz      short loc_180050C73
0x180050c35  movzx   eax, r12w
0x180050c39  mov     [rsp+1C0h+DestinationString.Length], r9w
0x180050c3f  sub     ax, bx
0x180050c42  lea     rdx, [rsp+1C0h+SourceString]; SourceString
0x180050c47  mov     [rsp+1C0h+DestinationString.MaximumLength], ax
0x180050c4c  lea     rcx, [rsp+1C0h+DestinationString]; DestinationString
0x180050c51  movzx   eax, bx
0x180050c54  add     rax, rdi
0x180050c57  mov     [rsp+1C0h+DestinationString.Buffer], rax
0x180050c5c  call    cs:__imp_RtlCopyUnicodeString
0x180050c63  nop     dword ptr [rax+rax+00h]
0x180050c68  movzx   eax, [rsp+1C0h+SourceString.Length]
0x180050c6d  mov     [rdi+10h], ax
0x180050c71  jmp     short loc_180050C7B
0x180050c73  mov     [rdi+10h], r9w
0x180050c78  mov     eax, r9d
0x180050c7b  mov     ecx, [rsp+1C0h+var_18C]
0x180050c7f  add     bx, ax
0x180050c82  mov     [rdi+12h], cx
0x180050c86  mov     rdx, [rsp+1C0h+Src]; Src
0x180050c8b  movzx   ebx, bx
0x180050c8e  movzx   r8d, r15w; Size
0x180050c92  lea     rcx, [rdi+rbx]; void *
0x180050c96  call    memmove
0x180050c9b  xor     r8d, r8d
0x180050c9e  mov     [rdi+14h], r15w
0x180050ca3  mov     rdx, rsi
0x180050ca6  mov     [rdi+16h], bx
0x180050caa  mov     rcx, r13
0x180050cad  call    FltpGetSupportedFeaturesValue
0x180050cb2  mov     [rdi+18h], eax
0x180050cb5  xor     r9d, r9d
0x180050cb8  mov     rax, [rsp+1C0h+var_168]
0x180050cbd  mov     ebx, r9d
0x180050cc0  mov     [rax], r12d
0x180050cc3  mov     rcx, [rsp+1C0h+DiskDeviceObject]; Object
0x180050cc8  test    rcx, rcx
0x180050ccb  jz      short loc_180050CD9
0x180050ccd  call    cs:__imp_ObfDereferenceObject
0x180050cd4  nop     dword ptr [rax+rax+00h]
0x180050cd9  test    r14, r14
0x180050cdc  jz      short loc_180050CED
0x180050cde  mov     rcx, r14; Object
0x180050ce1  call    cs:__imp_ObfDereferenceObject
0x180050ce8  nop     dword ptr [rax+rax+00h]
0x180050ced  lea     rcx, [rsp+1C0h+SourceString]
0x180050cf2  call    FltpCleanupNameControl
0x180050cf7  mov     eax, ebx
0x180050cf9  mov     rcx, [rbp+0C0h+var_40]
0x180050d00  xor     rcx, rsp; StackCookie
0x180050d03  call    __security_check_cookie
0x180050d08  mov     rbx, [rsp+1C0h+arg_8]
0x180050d10  add     rsp, 190h
0x180050d17  pop     r15
0x180050d19  pop     r14
0x180050d1b  pop     r13
0x180050d1d  pop     r12
0x180050d1f  pop     rdi
0x180050d20  pop     rsi
0x180050d21  pop     rbp
0x180050d22  retn
```
