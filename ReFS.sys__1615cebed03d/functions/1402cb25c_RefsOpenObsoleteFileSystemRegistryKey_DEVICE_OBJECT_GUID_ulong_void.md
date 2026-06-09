# RefsOpenObsoleteFileSystemRegistryKey(_DEVICE_OBJECT *,_GUID *,ulong,void * *)

- ea: `0x1402cb25c`
- end: `0x1402cb5b9`
- name: `?RefsOpenObsoleteFileSystemRegistryKey@@YAJPEAU_DEVICE_OBJECT@@PEAU_GUID@@KPEAPEAX@Z`
- size: `861`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, struct _GUID *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1402cb02c`

## callees

- `0x1400862c0`
- `0x1400d0fd8`
- `0x1401f3fc0`
- `0x1401f40a0`
- `0x1401f4400`
- `0x1402cb25c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1402cb452`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402cb452`
- `ntoskrnl!ZwClose` at `0x1402cb575`
- `ntoskrnl!ZwClose` at `0x1402cb58b`
- `ntoskrnl!ZwClose` at `0x1402cb575`
- `ntoskrnl!ZwClose` at `0x1402cb58b`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1402cb2f4`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1402cb2f4`
- `ntoskrnl!ZwOpenKey` at `0x1402cb3a4`
- `ntoskrnl!ZwOpenKey` at `0x1402cb3a4`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1402cb487`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1402cb463`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1402cb463`

## string_xrefs

- `0x1402cb354`: `mount.c`
- `0x1402cb419`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
__int64 __fastcall RefsOpenObsoleteFileSystemRegistryKey(
        PDEVICE_OBJECT DeviceObject,
        struct _GUID *a2,
        __int64 a3,
        void **a4)
{
  int v6; // ebx
  unsigned int v7; // r9d
  void *v8; // rbx
  PVOID SystemRoutineAddress; // rax
  __int64 v10; // rax
  void *KeyHandle; // [rsp+30h] [rbp-D0h] BYREF
  void *DeviceRegKey; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v14[2]; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v17[14]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v18; // [rsp+100h] [rbp+0h] BYREF

  DeviceRegKey = 0;
  KeyHandle = 0;
  v14[0] = 1441812;
  memset(v17, 0, sizeof(v17));
  v14[1] = L"FileSystem";
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  *a4 = 0;
  v18 = 0;
  v6 = IoOpenDeviceRegistryKey(DeviceObject, 1u, 1u, &DeviceRegKey);
  if ( v6 >= 0 )
  {
    ObjectAttributes.RootDirectory = DeviceRegKey;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v14;
    ObjectAttributes.Attributes = 1600;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v6 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    if ( v6 >= 0 )
    {
      v8 = KeyHandle;
      v17[2] = L"FsGuid";
      v17[0] = 0;
      v17[3] = &v18;
      LODWORD(v17[1]) = 308;
      LODWORD(v17[4]) = 50331648;
      LODWORD(v18) = -16;
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
      SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
      if ( !SystemRoutineAddress )
        SystemRoutineAddress = RtlQueryRegistryValues;
      v6 = ((__int64 (__fastcall *)(__int64, void *, _QWORD *, _QWORD, _QWORD))SystemRoutineAddress)(
             0x40000000,
             v8,
             v17,
             0,
             0);
      if ( v6 >= 0 )
      {
        v10 = *(_QWORD *)&a2->Data1 - v18;
        if ( *(_QWORD *)&a2->Data1 == (_QWORD)v18 )
          v10 = *(_QWORD *)a2->Data4 - *((_QWORD *)&v18 + 1);
        if ( v10 )
        {
          v6 = -1073740578;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              79,
              WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids,
              3221226718LL);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
          {
            v7 = 5699;
            goto LABEL_8;
          }
        }
        else
        {
          *a4 = KeyHandle;
          KeyHandle = 0;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            78,
            WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids,
            (unsigned int)v6);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
        {
          v7 = 5693;
          goto LABEL_8;
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          77,
          WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids,
          (unsigned int)v6);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        v7 = 5661;
        goto LABEL_8;
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        76,
        WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids,
        (unsigned int)v6);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
    {
      v7 = 5641;
LABEL_8:
      RefsStatusDebug(v6, 0, "mount.c", v7);
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( DeviceRegKey )
    ZwClose(DeviceRegKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1402cb25c  mov     [rsp-8+arg_8], rbx
0x1402cb261  push    rbp
0x1402cb262  push    rsi
0x1402cb263  push    rdi
0x1402cb264  lea     rbp, [rsp-20h]
0x1402cb269  sub     rsp, 120h
0x1402cb270  mov     rax, cs:__security_cookie
0x1402cb277  xor     rax, rsp
0x1402cb27a  mov     [rbp+30h+var_20], rax
0x1402cb27e  xorps   xmm0, xmm0
0x1402cb281  mov     [rsp+130h+DeviceRegKey], 0
0x1402cb28a  mov     rdi, rdx
0x1402cb28d  mov     [rsp+130h+KeyHandle], 0
0x1402cb296  xor     edx, edx; Val
0x1402cb298  mov     [rsp+130h+var_F0], 160014h
0x1402cb2a1  mov     rbx, rcx
0x1402cb2a4  mov     [rbp+30h+var_A0], 0
0x1402cb2ac  lea     rax, aFilesystem; "FileSystem"
0x1402cb2b3  mov     rsi, r9
0x1402cb2b6  lea     rcx, [rbp+30h+var_98]; void *
0x1402cb2ba  mov     [rsp+130h+var_E8], rax
0x1402cb2bf  lea     r8d, [rdx+68h]; Size
0x1402cb2c3  movups  xmmword ptr [rsp+130h+ObjectAttributes.Length], xmm0
0x1402cb2c8  movups  xmmword ptr [rsp+130h+ObjectAttributes.ObjectName], xmm0
0x1402cb2cd  movups  xmmword ptr [rbp+30h+ObjectAttributes.SecurityDescriptor], xmm0
0x1402cb2d1  call    memset
0x1402cb2d6  mov     edx, 1; DevInstKeyType
0x1402cb2db  mov     qword ptr [rsi], 0
0x1402cb2e2  xorps   xmm0, xmm0
0x1402cb2e5  lea     r9, [rsp+130h+DeviceRegKey]; DeviceRegKey
0x1402cb2ea  mov     r8d, edx; DesiredAccess
0x1402cb2ed  mov     rcx, rbx; DeviceObject
0x1402cb2f0  movups  [rbp+30h+var_30], xmm0
0x1402cb2f4  call    cs:__imp_IoOpenDeviceRegistryKey
0x1402cb2fb  nop     dword ptr [rax+rax+00h]
0x1402cb300  mov     ebx, eax
0x1402cb302  test    eax, eax
0x1402cb304  jns     short loc_1402CB369
0x1402cb306  mov     rcx, cs:WPP_GLOBAL_Control
0x1402cb30d  lea     rax, WPP_GLOBAL_Control
0x1402cb314  cmp     rcx, rax
0x1402cb317  jz      short loc_1402CB340
0x1402cb319  test    dword ptr [rcx+2Ch], 100h
0x1402cb320  jz      short loc_1402CB340
0x1402cb322  cmp     byte ptr [rcx+29h], 4
0x1402cb326  jb      short loc_1402CB340
0x1402cb328  mov     rcx, [rcx+18h]
0x1402cb32c  lea     r8, WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids
0x1402cb333  mov     edx, 4Ch ; 'L'
0x1402cb338  mov     r9d, ebx
0x1402cb33b  call    WPP_SF_d
0x1402cb340  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402cb346  test    al, al
0x1402cb348  jz      loc_1402CB56B
0x1402cb34e  mov     r9d, 1609h; unsigned int
0x1402cb354  lea     r8, aMountC; "mount.c"
0x1402cb35b  xor     edx, edx; struct _IRP_CONTEXT *
0x1402cb35d  mov     ecx, ebx; Status
0x1402cb35f  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402cb364  jmp     loc_1402CB56B
0x1402cb369  mov     rax, [rsp+130h+DeviceRegKey]
0x1402cb36e  lea     r8, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x1402cb373  mov     [rsp+130h+ObjectAttributes.RootDirectory], rax
0x1402cb378  lea     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x1402cb37d  lea     rax, [rsp+130h+var_F0]
0x1402cb382  mov     [rsp+130h+ObjectAttributes.Length], 30h ; '0'
0x1402cb38a  xorps   xmm0, xmm0
0x1402cb38d  mov     [rsp+130h+ObjectAttributes.ObjectName], rax
0x1402cb392  mov     edx, 20019h; DesiredAccess
0x1402cb397  mov     [rsp+130h+ObjectAttributes.Attributes], 640h
0x1402cb39f  movdqu  xmmword ptr [rbp+30h+ObjectAttributes.SecurityDescriptor], xmm0
0x1402cb3a4  call    cs:__imp_ZwOpenKey
0x1402cb3ab  nop     dword ptr [rax+rax+00h]
0x1402cb3b0  mov     ebx, eax
0x1402cb3b2  test    eax, eax
0x1402cb3b4  jns     short loc_1402CB409
0x1402cb3b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1402cb3bd  lea     rax, WPP_GLOBAL_Control
0x1402cb3c4  cmp     rcx, rax
0x1402cb3c7  jz      short loc_1402CB3F0
0x1402cb3c9  test    dword ptr [rcx+2Ch], 100h
0x1402cb3d0  jz      short loc_1402CB3F0
0x1402cb3d2  cmp     byte ptr [rcx+29h], 4
0x1402cb3d6  jb      short loc_1402CB3F0
0x1402cb3d8  mov     rcx, [rcx+18h]
0x1402cb3dc  lea     r8, WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids
0x1402cb3e3  mov     edx, 4Dh ; 'M'
0x1402cb3e8  mov     r9d, ebx
0x1402cb3eb  call    WPP_SF_d
0x1402cb3f0  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402cb3f6  test    al, al
0x1402cb3f8  jz      loc_1402CB56B
0x1402cb3fe  mov     r9d, 161Dh
0x1402cb404  jmp     loc_1402CB354
0x1402cb409  mov     rbx, [rsp+130h+KeyHandle]
0x1402cb40e  lea     rax, aFsguid; "FsGuid"
0x1402cb415  mov     [rbp+30h+var_90], rax
0x1402cb419  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x1402cb420  lea     rax, [rbp+30h+var_30]
0x1402cb424  mov     [rbp+30h+var_A0], 0
0x1402cb42c  xorps   xmm0, xmm0
0x1402cb42f  mov     [rbp+30h+var_88], rax
0x1402cb433  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x1402cb438  mov     [rbp+30h+var_98], 134h
0x1402cb43f  mov     [rbp+30h+var_80], 3000000h
0x1402cb446  mov     dword ptr [rbp+30h+var_30], 0FFFFFFF0h
0x1402cb44d  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm0
0x1402cb452  call    cs:__imp_RtlInitUnicodeString
0x1402cb459  nop     dword ptr [rax+rax+00h]
0x1402cb45e  lea     rcx, [rsp+130h+DestinationString]; SystemRoutineName
0x1402cb463  call    cs:__imp_MmGetSystemRoutineAddress
0x1402cb46a  nop     dword ptr [rax+rax+00h]
0x1402cb46f  lea     r8, [rbp+30h+var_A0]
0x1402cb473  mov     [rsp+130h+var_110], 0
0x1402cb47c  test    rax, rax
0x1402cb47f  mov     rdx, rbx
0x1402cb482  mov     ecx, 40000000h
0x1402cb487  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x1402cb48f  xor     r9d, r9d
0x1402cb492  call    _guard_dispatch_icall
0x1402cb497  mov     ebx, eax
0x1402cb499  test    eax, eax
0x1402cb49b  jns     short loc_1402CB4F0
0x1402cb49d  mov     rcx, cs:WPP_GLOBAL_Control
0x1402cb4a4  lea     rax, WPP_GLOBAL_Control
0x1402cb4ab  cmp     rcx, rax
0x1402cb4ae  jz      short loc_1402CB4D7
0x1402cb4b0  test    dword ptr [rcx+2Ch], 100h
0x1402cb4b7  jz      short loc_1402CB4D7
0x1402cb4b9  cmp     byte ptr [rcx+29h], 4
0x1402cb4bd  jb      short loc_1402CB4D7
0x1402cb4bf  mov     rcx, [rcx+18h]
0x1402cb4c3  lea     r8, WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids
0x1402cb4ca  mov     edx, 4Eh ; 'N'
0x1402cb4cf  mov     r9d, ebx
0x1402cb4d2  call    WPP_SF_d
0x1402cb4d7  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402cb4dd  test    al, al
0x1402cb4df  jz      loc_1402CB56B
0x1402cb4e5  mov     r9d, 163Dh
0x1402cb4eb  jmp     loc_1402CB354
0x1402cb4f0  mov     rax, [rdi]
0x1402cb4f3  sub     rax, qword ptr [rbp+30h+var_30]
0x1402cb4f7  jnz     short loc_1402CB501
0x1402cb4f9  mov     rax, [rdi+8]
0x1402cb4fd  sub     rax, qword ptr [rbp+30h+var_30+8]
0x1402cb501  test    rax, rax
0x1402cb504  jz      short loc_1402CB55A
0x1402cb506  mov     rcx, cs:WPP_GLOBAL_Control
0x1402cb50d  lea     rax, WPP_GLOBAL_Control
0x1402cb514  mov     ebx, 0C00004DEh
0x1402cb519  cmp     rcx, rax
0x1402cb51c  jz      short loc_1402CB545
0x1402cb51e  test    dword ptr [rcx+2Ch], 100h
0x1402cb525  jz      short loc_1402CB545
0x1402cb527  cmp     byte ptr [rcx+29h], 4
0x1402cb52b  jb      short loc_1402CB545
0x1402cb52d  mov     rcx, [rcx+18h]
0x1402cb531  lea     r8, WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids
0x1402cb538  mov     edx, 4Fh ; 'O'
0x1402cb53d  mov     r9d, ebx
0x1402cb540  call    WPP_SF_d
0x1402cb545  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402cb54b  test    al, al
0x1402cb54d  jz      short loc_1402CB56B
0x1402cb54f  mov     r9d, 1643h
0x1402cb555  jmp     loc_1402CB354
0x1402cb55a  mov     rax, [rsp+130h+KeyHandle]
0x1402cb55f  mov     [rsi], rax
0x1402cb562  mov     [rsp+130h+KeyHandle], 0
0x1402cb56b  mov     rcx, [rsp+130h+KeyHandle]; Handle
0x1402cb570  test    rcx, rcx
0x1402cb573  jz      short loc_1402CB581
0x1402cb575  call    cs:__imp_ZwClose
0x1402cb57c  nop     dword ptr [rax+rax+00h]
0x1402cb581  mov     rcx, [rsp+130h+DeviceRegKey]; Handle
0x1402cb586  test    rcx, rcx
0x1402cb589  jz      short loc_1402CB597
0x1402cb58b  call    cs:__imp_ZwClose
0x1402cb592  nop     dword ptr [rax+rax+00h]
0x1402cb597  mov     eax, ebx
0x1402cb599  mov     rcx, [rbp+30h+var_20]
0x1402cb59d  xor     rcx, rsp; StackCookie
0x1402cb5a0  call    __security_check_cookie
0x1402cb5a5  mov     rbx, [rsp+130h+arg_8]
0x1402cb5ad  add     rsp, 120h
0x1402cb5b4  pop     rdi
0x1402cb5b5  pop     rsi
0x1402cb5b6  pop     rbp
0x1402cb5b7  retn
```
