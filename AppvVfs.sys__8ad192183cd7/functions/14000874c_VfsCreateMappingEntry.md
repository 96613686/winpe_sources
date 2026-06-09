# VfsCreateMappingEntry

- ea: `0x14000874c`
- end: `0x140008907`
- name: `VfsCreateMappingEntry`
- size: `443`
- prototype: `__int64 __fastcall(PCUNICODE_STRING VolumeName, const UNICODE_STRING *, const UNICODE_STRING *, const UNICODE_STRING *, const UNICODE_STRING *, const UNICODE_STRING *, int *, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140009580`

## callees

- `0x14000874c`
- `0x140009368`
- `0x14000e59c`
- `0x140011438`
- `0x140011520`
- `0x140012acc`
- `0x14001376c`
- `0x140014000`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140008776`
- `ntoskrnl!ExAllocatePool2` at `0x140008776`
- `FLTMGR!FltObjectDereference` at `0x1400088b9`
- `FLTMGR!FltObjectDereference` at `0x1400088b9`

## string_xrefs

- `0x1400087de`: `VfsCreateMappingEntry() - Failed to get device volume name for volume: %wZ\n Status: 0x%08X`
- `0x140008883`: `VfsCreateMappingEntry() - Failed to get instance for volume: %wZ\n Status: 0x%08X`
- `0x1400088d5`: `VfsCreateMappingEntry() - Failed to create security descriptors for directory: %wZ\n Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsCreateMappingEntry(
        PCUNICODE_STRING VolumeName,
        const UNICODE_STRING *a2,
        const UNICODE_STRING *a3,
        const UNICODE_STRING *a4,
        const UNICODE_STRING *a5,
        const UNICODE_STRING *a6,
        int *a7,
        _QWORD *a8)
{
  __int64 Pool2; // rax
  char *v13; // rdi
  int DeviceVolumeNameFromVolumeName; // eax
  int MappingNames; // ebx
  PCUNICODE_STRING v17; // r9
  int v18; // eax
  int InstanceFromVolumeName; // eax
  const UNICODE_STRING *v20; // r9
  const WCHAR *v21; // r8
  __int64 v22; // [rsp+20h] [rbp-68h]
  __int64 v23; // [rsp+20h] [rbp-68h]

  Pool2 = ExAllocatePool2(256, 96, 1699563094);
  v13 = (char *)Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  memset((void *)(Pool2 + 8), 0, 0x58u);
  *(_QWORD *)v13 = 1;
  DeviceVolumeNameFromVolumeName = VfsGetDeviceVolumeNameFromVolumeName(VolumeName);
  MappingNames = DeviceVolumeNameFromVolumeName;
  if ( DeviceVolumeNameFromVolumeName < 0 )
  {
    v17 = VolumeName;
LABEL_5:
    LogWrite(
      1,
      0,
      L"VfsCreateMappingEntry() - Failed to get device volume name for volume: %wZ\n Status: 0x%08X",
      v17,
      DeviceVolumeNameFromVolumeName);
    goto LABEL_15;
  }
  DeviceVolumeNameFromVolumeName = VfsGetDeviceVolumeNameFromVolumeName(a4);
  MappingNames = DeviceVolumeNameFromVolumeName;
  if ( DeviceVolumeNameFromVolumeName < 0 )
  {
    v17 = a4;
    goto LABEL_5;
  }
  MappingNames = CreateMappingNames(a2, a3, a5, a6, v22, (struct _UNICODE_STRING **)v13 + 5);
  if ( MappingNames >= 0 )
  {
    v18 = *a7;
    *((_DWORD *)v13 + 1) = *a7;
    if ( (v18 & 1) != 0 )
    {
      InstanceFromVolumeName = VfsGetInstanceFromVolumeName((PCUNICODE_STRING)(v13 + 24));
      MappingNames = InstanceFromVolumeName;
      if ( InstanceFromVolumeName >= 0 )
      {
        MappingNames = VfsCreateSecurityDescriptors(0, (__int64)(v13 + 72));
        FltObjectDereference(0);
        if ( MappingNames >= 0 )
          goto LABEL_15;
        LODWORD(v23) = MappingNames;
        v20 = a5;
        v21 = L"VfsCreateMappingEntry() - Failed to create security descriptors for directory: %wZ\n Status: 0x%08X";
      }
      else
      {
        LODWORD(v23) = InstanceFromVolumeName;
        v20 = (const UNICODE_STRING *)(v13 + 24);
        v21 = L"VfsCreateMappingEntry() - Failed to get instance for volume: %wZ\n Status: 0x%08X";
      }
      LogWrite(1, 0, v21, v20, v23);
    }
  }
LABEL_15:
  if ( MappingNames < 0 )
    VfsReleaseMappingEntry(v13);
  else
    *a8 = v13;
  return (unsigned int)MappingNames;
}

```

## disassembly

```asm
0x14000874c  push    rbx
0x14000874e  push    rsi
0x14000874f  push    rdi
0x140008750  push    r12
0x140008752  push    r13
0x140008754  push    r14
0x140008756  sub     rsp, 58h
0x14000875a  mov     r14, r9
0x14000875d  mov     r12, r8
0x140008760  mov     r13, rdx
0x140008763  mov     rsi, rcx
0x140008766  mov     edx, 60h ; '`'
0x14000876b  mov     ecx, 100h
0x140008770  mov     r8d, 654D4656h
0x140008776  call    cs:__imp_ExAllocatePool2
0x14000877d  nop     dword ptr [rax+rax+00h]
0x140008782  mov     rdi, rax
0x140008785  test    rax, rax
0x140008788  jnz     short loc_14000879E
0x14000878a  mov     eax, 0C000009Ah
0x14000878f  add     rsp, 58h
0x140008793  pop     r14
0x140008795  pop     r13
0x140008797  pop     r12
0x140008799  pop     rdi
0x14000879a  pop     rsi
0x14000879b  pop     rbx
0x14000879c  retn
0x14000879e  mov     [rsp+88h+var_58], 0
0x1400087a6  mov     [rsp+88h+var_48], rdi
0x1400087ab  lea     rcx, [rax+8]; void *
0x1400087af  xor     edx, edx; Val
0x1400087b1  lea     r8d, [rdx+58h]; Size
0x1400087b5  call    memset
0x1400087ba  mov     qword ptr [rdi], 1
0x1400087c1  lea     r8, [rdi+8]
0x1400087c5  mov     rcx, rsi; VolumeName
0x1400087c8  call    VfsGetDeviceVolumeNameFromVolumeName
0x1400087cd  mov     ebx, eax
0x1400087cf  mov     [rsp+88h+var_58], eax
0x1400087d3  test    eax, eax
0x1400087d5  jns     short loc_1400087EF
0x1400087d7  mov     r9, rsi
0x1400087da  mov     dword ptr [rsp+88h+var_68], eax
0x1400087de  lea     r8, aVfscreatemappi_1; "VfsCreateMappingEntry() - Failed to get"...
0x1400087e5  mov     ecx, 1
0x1400087ea  jmp     loc_1400088DF
0x1400087ef  lea     rsi, [rdi+18h]
0x1400087f3  mov     r8, rsi
0x1400087f6  mov     rcx, r14; VolumeName
0x1400087f9  call    VfsGetDeviceVolumeNameFromVolumeName
0x1400087fe  mov     ebx, eax
0x140008800  mov     [rsp+88h+var_58], eax
0x140008804  test    eax, eax
0x140008806  jns     short loc_14000880D
0x140008808  mov     r9, r14
0x14000880b  jmp     short loc_1400087DA
0x14000880d  lea     rax, [rdi+28h]
0x140008811  mov     [rsp+88h+var_60], rax
0x140008816  mov     r9, [rsp+88h+arg_28]
0x14000881e  mov     r8, [rsp+88h+arg_20]
0x140008826  mov     rdx, r12
0x140008829  mov     rcx, r13
0x14000882c  call    CreateMappingNames
0x140008831  mov     ebx, eax
0x140008833  mov     [rsp+88h+var_58], eax
0x140008837  test    eax, eax
0x140008839  js      loc_1400088E7
0x14000883f  mov     r14, [rsp+88h+arg_30]
0x140008847  mov     eax, [r14]
0x14000884a  mov     [rdi+4], eax
0x14000884d  mov     r12d, 1
0x140008853  test    r12b, al
0x140008856  jz      loc_1400088E7
0x14000885c  mov     [rsp+88h+FltObject], 0
0x140008865  lea     rdx, [rsp+88h+FltObject]
0x14000886a  mov     rcx, rsi; String2
0x14000886d  call    VfsGetInstanceFromVolumeName
0x140008872  mov     ebx, eax
0x140008874  mov     [rsp+88h+var_58], eax
0x140008878  test    eax, eax
0x14000887a  jns     short loc_14000888C
0x14000887c  mov     dword ptr [rsp+88h+var_68], eax
0x140008880  mov     r9, rsi
0x140008883  lea     r8, aVfscreatemappi; "VfsCreateMappingEntry() - Failed to get"...
0x14000888a  jmp     short loc_1400088DC
0x14000888c  lea     rax, [rdi+48h]
0x140008890  mov     [rsp+88h+var_68], rax; __int64
0x140008895  mov     r9, [r14+8]
0x140008899  mov     r8, [rsp+88h+arg_20]
0x1400088a1  mov     rdx, rsi
0x1400088a4  mov     rcx, [rsp+88h+FltObject]; Instance
0x1400088a9  call    VfsCreateSecurityDescriptors
0x1400088ae  mov     ebx, eax
0x1400088b0  mov     [rsp+88h+var_58], eax
0x1400088b4  mov     rcx, [rsp+88h+FltObject]; FltObject
0x1400088b9  call    cs:__imp_FltObjectDereference
0x1400088c0  nop     dword ptr [rax+rax+00h]
0x1400088c5  test    ebx, ebx
0x1400088c7  jns     short loc_1400088E7
0x1400088c9  mov     dword ptr [rsp+88h+var_68], ebx
0x1400088cd  mov     r9, [rsp+88h+arg_20]
0x1400088d5  lea     r8, aVfscreatemappi_0; "VfsCreateMappingEntry() - Failed to cre"...
0x1400088dc  mov     ecx, r12d
0x1400088df  xor     edx, edx
0x1400088e1  call    LogWrite
0x1400088e6  nop
0x1400088e7  test    ebx, ebx
0x1400088e9  js      short loc_1400088F8
0x1400088eb  mov     rax, [rsp+88h+arg_38]
0x1400088f3  mov     [rax], rdi
0x1400088f6  jmp     short loc_140008900
0x1400088f8  mov     rcx, rdi; P
0x1400088fb  call    VfsReleaseMappingEntry
0x140008900  mov     eax, ebx
0x140008902  jmp     loc_14000878F
0x140014d17  push    rbp
0x140014d19  sub     rsp, 30h
0x140014d1d  mov     rbp, rdx
0x140014d20  cmp     dword ptr [rbp+30h], 0
0x140014d24  jl      short loc_140014D36
0x140014d26  mov     rcx, [rbp+0C8h]
0x140014d2d  mov     rax, [rbp+40h]
0x140014d31  mov     [rcx], rax
0x140014d34  jmp     short loc_140014D40
0x140014d36  mov     rcx, [rbp+40h]; P
0x140014d3a  call    VfsReleaseMappingEntry
0x140014d3f  nop
0x140014d40  add     rsp, 30h
0x140014d44  pop     rbp
0x140014d45  retn
```
