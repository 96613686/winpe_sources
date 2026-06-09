# AvhdUtilities::CreateAutomaticVhdFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,AvhdUtilities::CreateAutomaticVhdFileFlags)

- ea: `0x140083da0`
- end: `0x140083fa2`
- name: `?CreateAutomaticVhdFile@AvhdUtilities@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0W4CreateAutomaticVhdFileFlags@1@@Z`
- size: `514`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14010692c`

## callees

- `0x14005159c`
- `0x14006af38`
- `0x140083da0`
- `0x1400841e4`
- `0x14009d7ac`
- `0x1400c3ce0`
- `0x140132940`
- `0x1401335fc`
- `0x1401bbeac`
- `0x1401ee420`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x140083e34`
- `RPCRT4!UuidCreate` at `0x140083e34`
- `VirtDisk!CreateVirtualDisk` at `0x140083f10`
- `VirtDisk!CreateVirtualDisk` at `0x140083f10`

## string_xrefs

- `0x140083dda`: `onecore\vm\common\avhd\avhdutilities.cpp`
- `0x140083e52`: `onecore\vm\common\avhd\avhdutilities.cpp`
- `0x140083f2b`: `onecore\vm\common\avhd\avhdutilities.cpp`
- `0x140083f64`: `onecore\vm\common\avhd\avhdutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall AvhdUtilities::CreateAutomaticVhdFile(unsigned __int16 *a1, __int64 a2)
{
  const unsigned __int16 *v4; // rcx
  const WCHAR *v5; // rax
  const WCHAR *v6; // rdx
  DWORD v7; // eax
  int v8; // eax
  CREATE_VIRTUAL_DISK_FLAG Flags; // [rsp+20h] [rbp-138h]
  CREATE_VIRTUAL_DISK_FLAG Flagsa; // [rsp+20h] [rbp-138h]
  struct _CREATE_VIRTUAL_DISK_PARAMETERS Parameters; // [rsp+50h] [rbp-108h] BYREF
  void *Handle; // [rsp+110h] [rbp-48h] BYREF
  struct _VIRTUAL_STORAGE_TYPE VirtualStorageType; // [rsp+118h] [rbp-40h] BYREF
  UUID Uuid; // [rsp+130h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  if ( !(unsigned int)AvhdUtilities::IsAutomaticVhd() )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x100,
      (unsigned int)"onecore\\vm\\common\\avhd\\avhdutilities.cpp",
      (const char *)0x57,
      Flags);
  VirtualStorageType.DeviceId = 0;
  VirtualStorageType.VendorId = VIRTUAL_STORAGE_TYPE_VENDOR_MICROSOFT;
  if ( *((_QWORD *)a1 + 3) <= 7u )
    v4 = a1;
  else
    v4 = *(const unsigned __int16 **)a1;
  VirtualStorageType.DeviceId = GetVhdDeviceIDFromExtension(v4);
  Uuid = 0;
  if ( UuidCreate(&Uuid) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x11E,
      (unsigned int)"onecore\\vm\\common\\avhd\\avhdutilities.cpp",
      (const char *)0x8007000ELL,
      Flags);
  memset_0(&Parameters, 0, sizeof(Parameters));
  Parameters.Version = CREATE_VIRTUAL_DISK_VERSION_2;
  Parameters.Version1.UniqueId = Uuid;
  Parameters.Version1.BlockSizeInBytes = 0;
  if ( *(_QWORD *)(a2 + 24) <= 7u )
    v5 = (const WCHAR *)a2;
  else
    v5 = *(const WCHAR **)a2;
  Parameters.Version1.SourcePath = v5;
  Handle = (void *)-1LL;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &Handle,
    -1);
  if ( *((_QWORD *)a1 + 3) <= 7u )
    v6 = a1;
  else
    v6 = *(const WCHAR **)a1;
  v7 = CreateVirtualDisk(
         &VirtualStorageType,
         v6,
         VIRTUAL_DISK_ACCESS_NONE,
         0,
         CREATE_VIRTUAL_DISK_FLAG_NONE,
         0,
         &Parameters,
         0,
         &Handle);
  if ( v7 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x136,
      (unsigned int)"onecore\\vm\\common\\avhd\\avhdutilities.cpp",
      (const char *)v7,
      Flagsa);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Handle);
  v8 = AvhdUtilities::CopyFileAcl(a1, (LPCWSTR)a2);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14E,
      (unsigned int)"onecore\\vm\\common\\avhd\\avhdutilities.cpp",
      (const char *)(unsigned int)v8,
      Flagsa);
  return 0;
}

```

## disassembly

```asm
0x140083da0  mov     [rsp+arg_10], rbx
0x140083da5  push    rdi
0x140083da6  sub     rsp, 150h
0x140083dad  mov     rax, cs:__security_cookie
0x140083db4  xor     rax, rsp
0x140083db7  mov     [rsp+158h+var_18], rax
0x140083dbf  mov     rdi, rdx
0x140083dc2  mov     rbx, rcx
0x140083dc5  call    ?IsAutomaticVhd@AvhdUtilities@@SAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; AvhdUtilities::IsAutomaticVhd(std::wstring const &)
0x140083dca  test    eax, eax
0x140083dcc  jnz     short loc_140083DEB
0x140083dce  mov     rcx, [rsp+158h]; this
0x140083dd6  lea     r9d, [rax+57h]; char *
0x140083dda  lea     r8, aOnecoreVmCommo_109; "onecore\\vm\\common\\avhd\\avhdutilitie"...
0x140083de1  mov     edx, 100h; void *
0x140083de6  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140083deb  mov     [rsp+158h+VirtualStorageType.DeviceId], 0
0x140083df6  movups  xmm0, xmmword ptr cs:VIRTUAL_STORAGE_TYPE_VENDOR_MICROSOFT.Data1
0x140083dfd  movdqu  xmmword ptr [rsp+158h+VirtualStorageType.VendorId.Data1], xmm0
0x140083e06  cmp     qword ptr [rbx+18h], 7
0x140083e0b  jbe     short loc_140083E12
0x140083e0d  mov     rcx, [rbx]
0x140083e10  jmp     short loc_140083E15
0x140083e12  mov     rcx, rbx; unsigned __int16 *
0x140083e15  call    ?GetVhdDeviceIDFromExtension@@YAKPEBG@Z; GetVhdDeviceIDFromExtension(ushort const *)
0x140083e1a  mov     [rsp+158h+VirtualStorageType.DeviceId], eax
0x140083e21  xorps   xmm0, xmm0
0x140083e24  movups  xmmword ptr [rsp+158h+Uuid.Data1], xmm0
0x140083e2c  lea     rcx, [rsp+158h+Uuid]; Uuid
0x140083e34  call    cs:__imp_UuidCreate
0x140083e3b  nop     dword ptr [rax+rax+00h]
0x140083e40  test    eax, eax
0x140083e42  jz      short loc_140083E63
0x140083e44  mov     rcx, [rsp+158h]; this
0x140083e4c  mov     r9d, 8007000Eh; char *
0x140083e52  lea     r8, aOnecoreVmCommo_109; "onecore\\vm\\common\\avhd\\avhdutilitie"...
0x140083e59  mov     edx, 11Eh; void *
0x140083e5e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140083e63  xor     edx, edx; Val
0x140083e65  mov     r8d, 0B8h; Size
0x140083e6b  lea     rcx, [rsp+158h+var_108]; void *
0x140083e70  call    memset_0
0x140083e75  mov     [rsp+158h+var_108.Version], 2
0x140083e7d  movups  xmm0, xmmword ptr [rsp+158h+Uuid.Data1]
0x140083e85  movdqu  xmmword ptr [rsp+158h+var_108.8], xmm0
0x140083e8b  mov     dword ptr [rsp+158h+var_108.8+18h], 0
0x140083e93  cmp     qword ptr [rdi+18h], 7
0x140083e98  jbe     short loc_140083E9F
0x140083e9a  mov     rax, [rdi]
0x140083e9d  jmp     short loc_140083EA2
0x140083e9f  mov     rax, rdi
0x140083ea2  mov     qword ptr [rsp+158h+var_108.8+28h], rax
0x140083eaa  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140083eae  mov     [rsp+158h+var_48], rdx
0x140083eb6  lea     rcx, [rsp+158h+var_48]
0x140083ebe  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x140083ec3  cmp     qword ptr [rbx+18h], 7
0x140083ec8  jbe     short loc_140083ECF
0x140083eca  mov     rdx, [rbx]
0x140083ecd  jmp     short loc_140083ED2
0x140083ecf  mov     rdx, rbx; Path
0x140083ed2  lea     rax, [rsp+158h+var_48]
0x140083eda  mov     [rsp+158h+Handle], rax; Handle
0x140083edf  mov     [rsp+158h+Overlapped], 0; Overlapped
0x140083ee8  lea     rax, [rsp+158h+var_108]
0x140083eed  mov     [rsp+158h+Parameters], rax; Parameters
0x140083ef2  mov     [rsp+158h+ProviderSpecificFlags], 0; ProviderSpecificFlags
0x140083efa  mov     [rsp+158h+Flags], 0; int
0x140083f02  xor     r9d, r9d; SecurityDescriptor
0x140083f05  xor     r8d, r8d; VirtualDiskAccessMask
0x140083f08  lea     rcx, [rsp+158h+VirtualStorageType]; VirtualStorageType
0x140083f10  call    cs:__imp_CreateVirtualDisk
0x140083f17  nop     dword ptr [rax+rax+00h]
0x140083f1c  mov     rcx, [rsp+158h]; this
0x140083f24  test    eax, eax
0x140083f26  jz      short loc_140083F3D
0x140083f28  mov     r9d, eax; char *
0x140083f2b  lea     r8, aOnecoreVmCommo_109; "onecore\\vm\\common\\avhd\\avhdutilitie"...
0x140083f32  mov     edx, 136h; void *
0x140083f37  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140083f3d  lea     rcx, [rsp+158h+var_48]
0x140083f45  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140083f4a  mov     rdx, rdi; LPCWSTR
0x140083f4d  mov     rcx, rbx; pObjectName
0x140083f50  call    ?CopyFileAcl@AvhdUtilities@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; AvhdUtilities::CopyFileAcl(std::wstring const &,std::wstring const &)
0x140083f55  mov     rcx, [rsp+158h]; this
0x140083f5d  test    eax, eax
0x140083f5f  jns     short loc_140083F75
0x140083f61  mov     r9d, eax; char *
0x140083f64  lea     r8, aOnecoreVmCommo_109; "onecore\\vm\\common\\avhd\\avhdutilitie"...
0x140083f6b  mov     edx, 14Eh; void *
0x140083f70  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140083f75  xor     eax, eax
0x140083f77  jmp     short loc_140083F80
0x140083f79  mov     eax, dword ptr [rsp+158h+var_48]
0x140083f80  mov     rcx, [rsp+158h+var_18]
0x140083f88  xor     rcx, rsp; StackCookie
0x140083f8b  call    __security_check_cookie
0x140083f90  mov     rbx, [rsp+158h+arg_10]
0x140083f98  add     rsp, 150h
0x140083f9f  pop     rdi
0x140083fa0  retn
```
