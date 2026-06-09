# BfpShouldVetoBinding

- ea: `0x140003adc`
- end: `0x140003e0b`
- name: `BfpShouldVetoBinding`
- size: `815`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140024294`

## callees

- `0x140003adc`
- `0x140004b90`
- `0x140004fc0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140003daa`
- `ntoskrnl!ObfDereferenceObject` at `0x140003daa`
- `FLTMGR!FltGetVolumeFromName` at `0x140003b98`
- `FLTMGR!FltGetVolumeFromName` at `0x140003b98`
- `FLTMGR!FltIsEcpAcknowledged` at `0x140003d66`
- `FLTMGR!FltIsEcpAcknowledged` at `0x140003d66`
- `FLTMGR!FltGetVolumeInstanceFromName` at `0x140003cc2`
- `FLTMGR!FltGetVolumeInstanceFromName` at `0x140003cc2`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x140003bf1`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x140003bf1`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140003dc7`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140003dc7`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x140003c66`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x140003c66`
- `FLTMGR!FltAllocateExtraCreateParameter` at `0x140003c37`
- `FLTMGR!FltAllocateExtraCreateParameter` at `0x140003c37`
- `FLTMGR!FltQueryInformationByName` at `0x140003d31`
- `FLTMGR!FltQueryInformationByName` at `0x140003d31`
- `FLTMGR!FltGetDiskDeviceObject` at `0x140003bb8`
- `FLTMGR!FltGetDiskDeviceObject` at `0x140003bb8`
- `FLTMGR!FltObjectDereference` at `0x140003d94`
- `FLTMGR!FltObjectDereference` at `0x140003ddd`
- `FLTMGR!FltObjectDereference` at `0x140003d94`
- `FLTMGR!FltObjectDereference` at `0x140003ddd`

## pseudocode

```c
__int64 __fastcall BfpShouldVetoBinding(__int64 a1, USHORT a2, char a3)
{
  NTSTATUS VolumeFromName; // ebx
  int v7; // eax
  PVOID EcpContext; // [rsp+40h] [rbp-C0h] BYREF
  PFLT_VOLUME RetVolume; // [rsp+48h] [rbp-B8h] BYREF
  PECP_LIST EcpList; // [rsp+50h] [rbp-B0h] BYREF
  PDEVICE_OBJECT DiskDeviceObject; // [rsp+58h] [rbp-A8h] BYREF
  PFLT_INSTANCE RetInstance; // [rsp+60h] [rbp-A0h] BYREF
  UNICODE_STRING VolumeName; // [rsp+68h] [rbp-98h] BYREF
  __int128 v15; // [rsp+78h] [rbp-88h] BYREF
  __int128 v16; // [rsp+88h] [rbp-78h]
  __int64 v17; // [rsp+98h] [rbp-68h]
  _BYTE v18[48]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v19; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v20[112]; // [rsp+E0h] [rbp-20h] BYREF

  DiskDeviceObject = 0;
  *(_DWORD *)(&VolumeName.MaximumLength + 1) = 0;
  EcpList = 0;
  EcpContext = 0;
  LOWORD(v17) = 0;
  RetVolume = 0;
  RetInstance = 0;
  v15 = 0;
  v16 = 0;
  memset(v18, 0, 44);
  v19 = 0;
  memset(v20, 0, 0x68u);
  if ( a2 > *(_WORD *)a1 )
    return (unsigned int)-1073741811;
  VolumeName.Buffer = *(PWSTR *)(a1 + 8);
  VolumeName.Length = a2;
  VolumeName.MaximumLength = a2;
  VolumeFromName = FltGetVolumeFromName(g_BindFltState, &VolumeName, &RetVolume);
  if ( VolumeFromName >= 0 )
  {
    VolumeFromName = FltGetDiskDeviceObject(RetVolume, &DiskDeviceObject);
    if ( VolumeFromName >= 0 )
    {
      if ( (DiskDeviceObject->Flags & 0x100) != 0 )
      {
        VolumeFromName = FltAllocateExtraCreateParameterList(g_BindFltState, 0, &EcpList);
        if ( VolumeFromName < 0 )
          goto LABEL_19;
        VolumeFromName = FltAllocateExtraCreateParameter(
                           g_BindFltState,
                           &GUID_ECP_TYPE_VETO_BINDING,
                           1u,
                           0,
                           0,
                           0x63654642u,
                           &EcpContext);
        if ( VolumeFromName < 0 )
          goto LABEL_19;
        *(_BYTE *)EcpContext = 0;
        VolumeFromName = FltInsertExtraCreateParameter(g_BindFltState, EcpList, EcpContext);
        if ( VolumeFromName < 0 )
          goto LABEL_19;
        WORD3(v15) = 0;
        *(_DWORD *)((char *)&v15 + 2) = 0;
        LOWORD(v15) = 40;
        *((_QWORD *)&v15 + 1) = EcpList;
        v16 = 0;
        v17 = 1;
        VolumeFromName = FltGetVolumeInstanceFromName(g_BindFltState, RetVolume, 0, &RetInstance);
        if ( VolumeFromName < 0 )
          goto LABEL_19;
        *(_DWORD *)v18 = 48;
        *(_QWORD *)&v18[8] = 0;
        *(_DWORD *)&v18[24] = 512;
        *(_QWORD *)&v18[16] = a1;
        *(_OWORD *)&v18[32] = 0;
        v7 = FltQueryInformationByName(g_BindFltState, RetInstance, v18, &v19, v20, 104, 77, &v15);
        VolumeFromName = v7;
        if ( a3 && (v7 == -1073741772 || v7 == -1073741766) )
        {
          VolumeFromName = 0;
        }
        else if ( v7 < 0 )
        {
          goto LABEL_19;
        }
        if ( FltIsEcpAcknowledged(g_BindFltState, EcpContext) )
        {
          if ( *(_BYTE *)EcpContext )
            VolumeFromName = -1073741790;
          goto LABEL_19;
        }
      }
      VolumeFromName = 0;
    }
  }
LABEL_19:
  if ( RetVolume )
    FltObjectDereference(RetVolume);
  if ( DiskDeviceObject )
    ObfDereferenceObject(DiskDeviceObject);
  if ( EcpList )
    FltFreeExtraCreateParameterList(g_BindFltState, EcpList);
  if ( RetInstance )
    FltObjectDereference(RetInstance);
  return (unsigned int)VolumeFromName;
}

```

## disassembly

```asm
0x140003adc  mov     [rsp-8+arg_10], rbx
0x140003ae1  push    rbp
0x140003ae2  push    rsi
0x140003ae3  push    rdi
0x140003ae4  lea     rbp, [rsp-60h]
0x140003ae9  sub     rsp, 160h
0x140003af0  mov     rax, cs:__security_cookie
0x140003af7  xor     rax, rsp
0x140003afa  mov     [rbp+70h+var_20], rax
0x140003afe  xorps   xmm0, xmm0
0x140003b01  mov     [rsp+170h+DiskDeviceObject], 0
0x140003b0a  xor     eax, eax
0x140003b0c  mov     dword ptr [rsp+170h+VolumeName+4], 0
0x140003b14  mov     sil, r8b
0x140003b17  mov     [rsp+170h+EcpList], 0
0x140003b20  movzx   ebx, dx
0x140003b23  mov     [rsp+170h+var_130], 0
0x140003b2c  mov     rdi, rcx
0x140003b2f  mov     word ptr [rbp+70h+var_D8], ax
0x140003b33  movups  [rbp+70h+var_C0], xmm0
0x140003b37  lea     r8d, [rax+68h]; Size
0x140003b3b  mov     [rsp+170h+RetVolume], rax
0x140003b40  xor     edx, edx; Val
0x140003b42  mov     [rsp+170h+RetInstance], rax
0x140003b47  lea     rcx, [rbp+70h+var_90]; void *
0x140003b4b  movups  [rsp+170h+var_F8], xmm0
0x140003b50  movups  [rbp+70h+var_E8], xmm0
0x140003b54  movups  [rbp+70h+var_D0], xmm0
0x140003b58  movups  [rbp+70h+var_C0+0Ch], xmm0
0x140003b5c  movups  [rbp+70h+var_A0], xmm0
0x140003b60  call    memset
0x140003b65  cmp     bx, [rdi]
0x140003b68  jbe     short loc_140003B74
0x140003b6a  mov     ebx, 0C000000Dh
0x140003b6f  jmp     loc_140003DE9
0x140003b74  mov     rax, [rdi+8]
0x140003b78  lea     r8, [rsp+170h+RetVolume]; RetVolume
0x140003b7d  mov     rcx, cs:g_BindFltState; Filter
0x140003b84  lea     rdx, [rsp+170h+VolumeName]; VolumeName
0x140003b89  mov     [rsp+170h+VolumeName.Buffer], rax
0x140003b8e  mov     [rsp+170h+VolumeName.Length], bx
0x140003b93  mov     [rsp+170h+VolumeName.MaximumLength], bx
0x140003b98  call    cs:__imp_FltGetVolumeFromName
0x140003b9f  nop     dword ptr [rax+rax+00h]
0x140003ba4  mov     ebx, eax
0x140003ba6  test    eax, eax
0x140003ba8  js      loc_140003D8A
0x140003bae  mov     rcx, [rsp+170h+RetVolume]; Volume
0x140003bb3  lea     rdx, [rsp+170h+DiskDeviceObject]; DiskDeviceObject
0x140003bb8  call    cs:__imp_FltGetDiskDeviceObject
0x140003bbf  nop     dword ptr [rax+rax+00h]
0x140003bc4  mov     ebx, eax
0x140003bc6  test    eax, eax
0x140003bc8  js      loc_140003D8A
0x140003bce  mov     rax, [rsp+170h+DiskDeviceObject]
0x140003bd3  test    dword ptr [rax+30h], 100h
0x140003bda  jnz     short loc_140003BE3
0x140003bdc  xor     ebx, ebx
0x140003bde  jmp     loc_140003D8A
0x140003be3  mov     rcx, cs:g_BindFltState; Filter
0x140003bea  lea     r8, [rsp+170h+EcpList]; EcpList
0x140003bef  xor     edx, edx; Flags
0x140003bf1  call    cs:__imp_FltAllocateExtraCreateParameterList
0x140003bf8  nop     dword ptr [rax+rax+00h]
0x140003bfd  mov     ebx, eax
0x140003bff  test    eax, eax
0x140003c01  js      loc_140003D8A
0x140003c07  mov     rcx, cs:g_BindFltState; Filter
0x140003c0e  lea     rax, [rsp+170h+var_130]
0x140003c13  mov     [rsp+170h+EcpContext], rax; EcpContext
0x140003c18  lea     rdx, GUID_ECP_TYPE_VETO_BINDING; EcpType
0x140003c1f  xor     r9d, r9d; Flags
0x140003c22  mov     [rsp+170h+PoolTag], 63654642h; PoolTag
0x140003c2a  mov     [rsp+170h+CleanupCallback], 0; CleanupCallback
0x140003c33  lea     r8d, [r9+1]; SizeOfContext
0x140003c37  call    cs:__imp_FltAllocateExtraCreateParameter
0x140003c3e  nop     dword ptr [rax+rax+00h]
0x140003c43  mov     ebx, eax
0x140003c45  test    eax, eax
0x140003c47  js      loc_140003D8A
0x140003c4d  mov     rax, [rsp+170h+var_130]
0x140003c52  mov     byte ptr [rax], 0
0x140003c55  mov     r8, [rsp+170h+var_130]; EcpContext
0x140003c5a  mov     rdx, [rsp+170h+EcpList]; EcpList
0x140003c5f  mov     rcx, cs:g_BindFltState; Filter
0x140003c66  call    cs:__imp_FltInsertExtraCreateParameter
0x140003c6d  nop     dword ptr [rax+rax+00h]
0x140003c72  mov     ebx, eax
0x140003c74  test    eax, eax
0x140003c76  js      loc_140003D8A
0x140003c7c  mov     rdx, [rsp+170h+RetVolume]; Volume
0x140003c81  lea     r9, [rsp+170h+RetInstance]; RetInstance
0x140003c86  mov     rcx, cs:g_BindFltState; Filter
0x140003c8d  xor     eax, eax
0x140003c8f  mov     word ptr [rsp+170h+var_F8+6], ax
0x140003c94  xorps   xmm0, xmm0
0x140003c97  mov     eax, 28h ; '('
0x140003c9c  mov     dword ptr [rsp+170h+var_F8+2], 0
0x140003ca4  mov     word ptr [rsp+170h+var_F8], ax
0x140003ca9  xor     r8d, r8d; InstanceName
0x140003cac  mov     rax, [rsp+170h+EcpList]
0x140003cb1  mov     qword ptr [rbp+70h+var_F8+8], rax
0x140003cb5  movdqu  [rbp+70h+var_E8], xmm0
0x140003cba  mov     [rbp+70h+var_D8], 1
0x140003cc2  call    cs:__imp_FltGetVolumeInstanceFromName
0x140003cc9  nop     dword ptr [rax+rax+00h]
0x140003cce  mov     ebx, eax
0x140003cd0  test    eax, eax
0x140003cd2  js      loc_140003D8A
0x140003cd8  mov     rdx, [rsp+170h+RetInstance]
0x140003cdd  lea     rax, [rsp+170h+var_F8]
0x140003ce2  mov     rcx, cs:g_BindFltState
0x140003ce9  lea     r9, [rbp+70h+var_A0]
0x140003ced  mov     [rsp+170h+var_138], rax
0x140003cf2  lea     r8, [rbp+70h+var_D0]
0x140003cf6  mov     dword ptr [rsp+170h+EcpContext], 4Dh ; 'M'
0x140003cfe  lea     rax, [rbp+70h+var_90]
0x140003d02  xorps   xmm0, xmm0
0x140003d05  mov     [rsp+170h+PoolTag], 68h ; 'h'
0x140003d0d  mov     [rsp+170h+CleanupCallback], rax
0x140003d12  mov     dword ptr [rbp+70h+var_D0], 30h ; '0'
0x140003d19  mov     qword ptr [rbp+70h+var_D0+8], 0
0x140003d21  mov     dword ptr [rbp+70h+var_C0+8], 200h
0x140003d28  mov     qword ptr [rbp+70h+var_C0], rdi
0x140003d2c  movdqu  [rbp+70h+var_B0], xmm0
0x140003d31  call    cs:__imp_FltQueryInformationByName
0x140003d38  nop     dword ptr [rax+rax+00h]
0x140003d3d  mov     ebx, eax
0x140003d3f  test    sil, sil
0x140003d42  jz      short loc_140003D56
0x140003d44  cmp     eax, 0C0000034h
0x140003d49  jz      short loc_140003D52
0x140003d4b  cmp     eax, 0C000003Ah
0x140003d50  jnz     short loc_140003D56
0x140003d52  xor     ebx, ebx
0x140003d54  jmp     short loc_140003D5A
0x140003d56  test    eax, eax
0x140003d58  js      short loc_140003D8A
0x140003d5a  mov     rdx, [rsp+170h+var_130]; EcpContext
0x140003d5f  mov     rcx, cs:g_BindFltState; Filter
0x140003d66  call    cs:__imp_FltIsEcpAcknowledged
0x140003d6d  nop     dword ptr [rax+rax+00h]
0x140003d72  test    al, al
0x140003d74  jz      loc_140003BDC
0x140003d7a  mov     rax, [rsp+170h+var_130]
0x140003d7f  mov     ecx, 0C0000022h
0x140003d84  cmp     byte ptr [rax], 0
0x140003d87  cmovnz  ebx, ecx
0x140003d8a  mov     rcx, [rsp+170h+RetVolume]; FltObject
0x140003d8f  test    rcx, rcx
0x140003d92  jz      short loc_140003DA0
0x140003d94  call    cs:__imp_FltObjectDereference
0x140003d9b  nop     dword ptr [rax+rax+00h]
0x140003da0  mov     rcx, [rsp+170h+DiskDeviceObject]; Object
0x140003da5  test    rcx, rcx
0x140003da8  jz      short loc_140003DB6
0x140003daa  call    cs:__imp_ObfDereferenceObject
0x140003db1  nop     dword ptr [rax+rax+00h]
0x140003db6  mov     rdx, [rsp+170h+EcpList]; EcpList
0x140003dbb  test    rdx, rdx
0x140003dbe  jz      short loc_140003DD3
0x140003dc0  mov     rcx, cs:g_BindFltState; Filter
0x140003dc7  call    cs:__imp_FltFreeExtraCreateParameterList
0x140003dce  nop     dword ptr [rax+rax+00h]
0x140003dd3  mov     rcx, [rsp+170h+RetInstance]; FltObject
0x140003dd8  test    rcx, rcx
0x140003ddb  jz      short loc_140003DE9
0x140003ddd  call    cs:__imp_FltObjectDereference
0x140003de4  nop     dword ptr [rax+rax+00h]
0x140003de9  mov     eax, ebx
0x140003deb  mov     rcx, [rbp+70h+var_20]
0x140003def  xor     rcx, rsp; StackCookie
0x140003df2  call    __security_check_cookie
0x140003df7  mov     rbx, [rsp+170h+arg_10]
0x140003dff  add     rsp, 160h
0x140003e06  pop     rdi
0x140003e07  pop     rsi
0x140003e08  pop     rbp
0x140003e09  retn
```
