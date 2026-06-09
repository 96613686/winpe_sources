# FltGetVolumeProperties

- ea: `0x180074ca0`
- end: `0x180074e2d`
- name: `FltGetVolumeProperties`
- size: `397`
- prototype: `NTSTATUS __stdcall(PFLT_VOLUME Volume, PFLT_VOLUME_PROPERTIES VolumeProperties, ULONG VolumePropertiesLength, PULONG LengthReturned)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180085d70`

## callees

- `0x180074ca0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x180074d74`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180074da5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180074ddc`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180074d74`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180074da5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180074ddc`

## pseudocode

```c
NTSTATUS __stdcall FltGetVolumeProperties(
        PFLT_VOLUME Volume,
        PFLT_VOLUME_PROPERTIES VolumeProperties,
        ULONG VolumePropertiesLength,
        PULONG LengthReturned)
{
  _UNICODE_STRING *p_DeviceName; // r15
  _UNICODE_STRING *p_CDODeviceName; // rsi
  _UNICODE_STRING *p_CDODriverName; // r14
  ULONG v9; // edi
  NTSTATUS result; // eax
  _DEVICE_OBJECT *DiskDeviceObject; // rax
  _UNICODE_STRING *p_FileSystemDeviceName; // rcx
  unsigned __int16 Length; // ax
  unsigned __int16 v14; // r8
  __int64 v15; // rdx
  unsigned __int16 v16; // r9
  wchar_t *v17; // r8

  p_DeviceName = &Volume->DeviceName;
  p_CDODeviceName = &Volume->CDODeviceName;
  p_CDODriverName = &Volume->CDODriverName;
  v9 = Volume->CDODeviceName.Length + Volume->CDODriverName.Length + Volume->DeviceName.Length + 72;
  if ( VolumePropertiesLength >= 0x48 )
  {
    VolumeProperties->DeviceType = Volume->DeviceObject->DeviceType;
    VolumeProperties->DeviceObjectFlags = Volume->DeviceObject->Flags;
    VolumeProperties->AlignmentRequirement = Volume->DeviceObject->AlignmentRequirement;
    *(_DWORD *)&VolumeProperties->SectorSize = Volume->DeviceObject->SectorSize;
    if ( (Volume->Flags & 0x800) != 0 )
      VolumeProperties->Flags |= 1u;
    DiskDeviceObject = Volume->DiskDeviceObject;
    if ( !DiskDeviceObject )
      DiskDeviceObject = Volume->DeviceObject;
    p_FileSystemDeviceName = &VolumeProperties->FileSystemDeviceName;
    VolumeProperties->DeviceCharacteristics = DiskDeviceObject->Characteristics;
    if ( VolumePropertiesLength < v9 )
    {
      *p_FileSystemDeviceName = 0;
      result = -2147483643;
      v9 = 72;
      VolumeProperties->FileSystemDriverName = 0;
      VolumeProperties->RealDeviceName = 0;
    }
    else
    {
      Length = p_CDODeviceName->Length;
      *p_FileSystemDeviceName = 0;
      VolumeProperties->FileSystemDeviceName.MaximumLength = Length;
      VolumeProperties->FileSystemDeviceName.Buffer = (wchar_t *)&VolumeProperties[1];
      RtlCopyUnicodeString(p_FileSystemDeviceName, p_CDODeviceName);
      v14 = p_CDODriverName->Length;
      v15 = p_CDODeviceName->Length + 72LL;
      VolumeProperties->FileSystemDriverName = 0;
      VolumeProperties->FileSystemDriverName.Buffer = (wchar_t *)((char *)VolumeProperties + v15);
      VolumeProperties->FileSystemDriverName.MaximumLength = v14;
      RtlCopyUnicodeString(&VolumeProperties->FileSystemDriverName, p_CDODriverName);
      v16 = p_DeviceName->Length;
      v17 = (wchar_t *)((char *)&VolumeProperties[1] + p_CDODriverName->Length + p_CDODeviceName->Length);
      VolumeProperties->RealDeviceName = 0;
      VolumeProperties->RealDeviceName.MaximumLength = v16;
      VolumeProperties->RealDeviceName.Buffer = v17;
      RtlCopyUnicodeString(&VolumeProperties->RealDeviceName, p_DeviceName);
      result = 0;
    }
    *LengthReturned = v9;
  }
  else
  {
    *LengthReturned = v9;
    return -1073741789;
  }
  return result;
}

```

## disassembly

```asm
0x180074ca0  push    rbx
0x180074ca2  push    rbp
0x180074ca3  push    rsi
0x180074ca4  push    rdi
0x180074ca5  push    r14
0x180074ca7  push    r15
0x180074ca9  sub     rsp, 28h
0x180074cad  movzx   edi, word ptr [rcx+70h]
0x180074cb1  lea     r15, [rcx+70h]
0x180074cb5  add     edi, 48h ; 'H'
0x180074cb8  lea     rsi, [rcx+0A0h]
0x180074cbf  movzx   eax, word ptr [rsi]
0x180074cc2  lea     r14, [rcx+0B0h]
0x180074cc9  movzx   r10d, word ptr [r14]
0x180074ccd  mov     rbp, r9
0x180074cd0  add     r10d, eax
0x180074cd3  mov     rbx, rdx
0x180074cd6  add     edi, r10d
0x180074cd9  cmp     r8d, 48h ; 'H'
0x180074cdd  jnb     short loc_180074CF5
0x180074cdf  mov     [r9], edi
0x180074ce2  mov     eax, 0C0000023h
0x180074ce7  add     rsp, 28h
0x180074ceb  pop     r15
0x180074ced  pop     r14
0x180074cef  pop     rdi
0x180074cf0  pop     rsi
0x180074cf1  pop     rbp
0x180074cf2  pop     rbx
0x180074cf3  retn
0x180074cf5  mov     rax, [rcx+40h]
0x180074cf9  mov     [rsp+58h+arg_0], r13
0x180074cfe  mov     edx, [rax+48h]
0x180074d01  mov     [rbx], edx
0x180074d03  mov     rax, [rcx+40h]
0x180074d07  mov     edx, [rax+30h]
0x180074d0a  mov     [rbx+8], edx
0x180074d0d  mov     rax, [rcx+40h]
0x180074d11  mov     edx, [rax+98h]
0x180074d17  mov     [rbx+0Ch], edx
0x180074d1a  mov     rax, [rcx+40h]
0x180074d1e  movzx   edx, word ptr [rax+130h]
0x180074d25  xor     eax, eax
0x180074d27  mov     [rbx+12h], ax
0x180074d2b  mov     [rbx+10h], dx
0x180074d2f  mov     eax, [rcx+38h]
0x180074d32  bt      eax, 0Bh
0x180074d36  jb      loc_180074E1A
0x180074d3c  mov     rax, [rcx+48h]
0x180074d40  test    rax, rax
0x180074d43  jz      loc_180074E24
0x180074d49  mov     eax, [rax+34h]
0x180074d4c  lea     rcx, [rbx+28h]; DestinationString
0x180074d50  mov     [rbx+4], eax
0x180074d53  xorps   xmm0, xmm0
0x180074d56  cmp     r8d, edi
0x180074d59  jb      loc_180074E00
0x180074d5f  movzx   eax, word ptr [rsi]
0x180074d62  mov     rdx, rsi; SourceString
0x180074d65  movups  xmmword ptr [rcx], xmm0
0x180074d68  mov     [rcx+2], ax
0x180074d6c  lea     rax, [rbx+48h]
0x180074d70  mov     [rcx+8], rax
0x180074d74  call    cs:__imp_RtlCopyUnicodeString
0x180074d7b  nop     dword ptr [rax+rax+00h]
0x180074d80  movzx   edx, word ptr [rsi]
0x180074d83  lea     rcx, [rbx+18h]; DestinationString
0x180074d87  movzx   r8d, word ptr [r14]
0x180074d8b  add     rdx, 48h ; 'H'
0x180074d8f  add     rdx, rbx
0x180074d92  xorps   xmm0, xmm0
0x180074d95  movups  xmmword ptr [rbx+18h], xmm0
0x180074d99  mov     [rbx+20h], rdx
0x180074d9d  mov     rdx, r14; SourceString
0x180074da0  mov     [rbx+1Ah], r8w
0x180074da5  call    cs:__imp_RtlCopyUnicodeString
0x180074dac  nop     dword ptr [rax+rax+00h]
0x180074db1  movzx   r8d, word ptr [r14]
0x180074db5  xorps   xmm0, xmm0
0x180074db8  movzx   ecx, word ptr [rsi]
0x180074dbb  add     r8, rbx
0x180074dbe  movzx   r9d, word ptr [r15]
0x180074dc2  add     rcx, 48h ; 'H'
0x180074dc6  add     r8, rcx
0x180074dc9  mov     rdx, r15; SourceString
0x180074dcc  lea     rcx, [rbx+38h]; DestinationString
0x180074dd0  movups  xmmword ptr [rcx], xmm0
0x180074dd3  mov     [rcx+2], r9w
0x180074dd8  mov     [rcx+8], r8
0x180074ddc  call    cs:__imp_RtlCopyUnicodeString
0x180074de3  nop     dword ptr [rax+rax+00h]
0x180074de8  xor     eax, eax
0x180074dea  mov     [rbp+0], edi
0x180074ded  mov     r13, [rsp+58h+arg_0]
0x180074df2  add     rsp, 28h
0x180074df6  pop     r15
0x180074df8  pop     r14
0x180074dfa  pop     rdi
0x180074dfb  pop     rsi
0x180074dfc  pop     rbp
0x180074dfd  pop     rbx
0x180074dfe  retn
0x180074e00  movups  xmmword ptr [rcx], xmm0
0x180074e03  mov     eax, 80000005h
0x180074e08  mov     edi, 48h ; 'H'
0x180074e0d  xorps   xmm1, xmm1
0x180074e10  movups  xmmword ptr [rbx+18h], xmm1
0x180074e14  movups  xmmword ptr [rbx+38h], xmm0
0x180074e18  jmp     short loc_180074DEA
0x180074e1a  or      word ptr [rbx+12h], 1
0x180074e1f  jmp     loc_180074D3C
0x180074e24  mov     rax, [rcx+40h]
0x180074e28  jmp     loc_180074D49
```
