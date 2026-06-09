# Windows::System::Inventory::CInstalledDesktopAppStatics::GetInventory(Windows::Foundation::Collections::Internal::Vector<Windows::System::Inventory::InstalledDesktopApp *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::Inventory::InstalledDesktopApp *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::Inventory::InstalledDesktopApp *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::System::Inventory::InstalledDesktopApp *>> *)

- ea: `0x180025d34`
- end: `0x180025e6a`
- name: `?GetInventory@CInstalledDesktopAppStatics@Inventory@System@Windows@@CAJPEAV?$Vector@PEAVInstalledDesktopApp@Inventory@System@Windows@@U?$DefaultEqualityPredicate@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVInstalledDesktopApp@Inventory@System@Windows@@@6784@U?$DefaultVectorOptions@PEAVInstalledDesktopApp@Inventory@System@Windows@@@6784@@Internal@Collections@Foundation@4@@Z`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180023250`

## callees

- `0x180025d34`
- `0x180025ef4`
- `0x1800260e8`
- `0x1800295dc`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180025d8b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180025d8b`

## string_xrefs

- `0x180025d4f`: `RTInstalledDesktopAppTest`
- `0x180025de3`: `Windows::System::Inventory::CInstalledDesktopAppStatics::GetInventory`
- `0x180025e4f`: `Windows::System::Inventory::CInstalledDesktopAppStatics::GetInventory`
- `0x180025d78`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`

## pseudocode

```c
__int64 __fastcall Windows::System::Inventory::CInstalledDesktopAppStatics::GetInventory(__int64 a1)
{
  int InventoryFromRpc; // ebx
  unsigned int v3; // eax
  __int64 v4; // rcx
  __int64 v5; // rax
  unsigned int pvData; // [rsp+68h] [rbp+28h] BYREF
  int v8; // [rsp+70h] [rbp+30h] BYREF
  DWORD pcbData; // [rsp+78h] [rbp+38h] BYREF

  pvData = 0;
  pcbData = 4;
  InventoryFromRpc = -2147467259;
  RegGetValueW(
    HKEY_LOCAL_MACHINE,
    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
    L"RTInstalledDesktopAppTest",
    0x20000010u,
    0,
    &pvData,
    &pcbData);
  v3 = pvData;
  if ( pvData >= 3 )
  {
    v3 = 0;
    pvData = 0;
  }
  if ( v3 != 2 )
  {
    InventoryFromRpc = Windows::System::Inventory::CInstalledDesktopAppStatics::GetInventoryFromRpc(a1);
    if ( InventoryFromRpc >= 0 )
    {
      v4 = *(_QWORD *)a1;
      v8 = 0;
      if ( (*(int (__fastcall **)(__int64, int *))(v4 + 56))(a1, &v8) >= 0 )
        AslLogCallPrintf(
          3,
          "Windows::System::Inventory::CInstalledDesktopAppStatics::GetInventory",
          243,
          "Successfully retrieved %d apps from RCP",
          v8);
    }
    v3 = pvData;
  }
  if ( v3 != 1 && InventoryFromRpc < 0 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 120LL))(a1);
    InventoryFromRpc = Windows::System::Inventory::CInstalledDesktopAppStatics::GetInventoryFromArp(a1);
    if ( InventoryFromRpc >= 0 )
    {
      v5 = *(_QWORD *)a1;
      v8 = 0;
      if ( (*(int (__fastcall **)(__int64, int *))(v5 + 56))(a1, &v8) >= 0 )
        AslLogCallPrintf(
          3,
          "Windows::System::Inventory::CInstalledDesktopAppStatics::GetInventory",
          257,
          "Successfully retrieved %d apps from ARP",
          v8);
    }
  }
  return (unsigned int)InventoryFromRpc;
}

```

## disassembly

```asm
0x180025d34  push    rbp
0x180025d36  push    rbx
0x180025d37  push    rdi
0x180025d38  mov     rbp, rsp
0x180025d3b  sub     rsp, 40h
0x180025d3f  lea     rax, [rbp+arg_18]
0x180025d43  mov     [rbp+arg_8], 0
0x180025d4a  mov     [rsp+40h+pcbData], rax; pcbData
0x180025d4f  lea     r8, aRtinstalleddes; "RTInstalledDesktopAppTest"
0x180025d56  lea     rax, [rbp+arg_8]
0x180025d5a  mov     [rbp+arg_18], 4
0x180025d61  mov     rdi, rcx
0x180025d64  mov     [rsp+40h+pvData], rax; pvData
0x180025d69  mov     r9d, 20000010h; dwFlags
0x180025d6f  mov     [rsp+40h+pdwType], 0; pdwType
0x180025d78  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180025d7f  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180025d86  mov     ebx, 80004005h
0x180025d8b  call    cs:__imp_RegGetValueW
0x180025d91  mov     eax, [rbp+arg_8]
0x180025d94  cmp     eax, 3
0x180025d97  jb      short loc_180025D9E
0x180025d99  xor     eax, eax
0x180025d9b  mov     [rbp+arg_8], eax
0x180025d9e  cmp     eax, 2
0x180025da1  jz      short loc_180025DF7
0x180025da3  mov     rcx, rdi
0x180025da6  call    ?GetInventoryFromRpc@CInstalledDesktopAppStatics@Inventory@System@Windows@@CAJPEAV?$Vector@PEAVInstalledDesktopApp@Inventory@System@Windows@@U?$DefaultEqualityPredicate@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVInstalledDesktopApp@Inventory@System@Windows@@@6784@U?$DefaultVectorOptions@PEAVInstalledDesktopApp@Inventory@System@Windows@@@6784@@Internal@Collections@Foundation@4@@Z; Windows::System::Inventory::CInstalledDesktopAppStatics::GetInventoryFromRpc(Windows::Foundation::Collections::Internal::Vector<Windows::System::Inventory::InstalledDesktopApp *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::Inventory::InstalledDesktopApp *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::Inventory::InstalledDesktopApp *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::System::Inventory::InstalledDesktopApp *>> *)
0x180025dab  mov     ebx, eax
0x180025dad  test    eax, eax
0x180025daf  js      short loc_180025DF4
0x180025db1  mov     rcx, [rdi]
0x180025db4  lea     rdx, [rbp+arg_10]
0x180025db8  mov     [rbp+arg_10], 0
0x180025dbf  mov     rax, [rcx+38h]
0x180025dc3  mov     rcx, rdi
0x180025dc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025dcb  test    eax, eax
0x180025dcd  js      short loc_180025DF4
0x180025dcf  mov     eax, [rbp+arg_10]
0x180025dd2  lea     r9, aSuccessfullyRe; "Successfully retrieved %d apps from RCP"
0x180025dd9  mov     r8d, 0F3h
0x180025ddf  mov     dword ptr [rsp+40h+pdwType], eax
0x180025de3  lea     rdx, aWindowsSystemI_0; "Windows::System::Inventory::CInstalledD"...
0x180025dea  mov     ecx, 3
0x180025def  call    AslLogCallPrintf
0x180025df4  mov     eax, [rbp+arg_8]
0x180025df7  cmp     eax, 1
0x180025dfa  jz      short loc_180025E60
0x180025dfc  test    ebx, ebx
0x180025dfe  jns     short loc_180025E60
0x180025e00  mov     rax, [rdi]
0x180025e03  mov     rcx, rdi
0x180025e06  mov     rax, [rax+78h]
0x180025e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e0f  mov     rcx, rdi
0x180025e12  call    ?GetInventoryFromArp@CInstalledDesktopAppStatics@Inventory@System@Windows@@CAJPEAV?$Vector@PEAVInstalledDesktopApp@Inventory@System@Windows@@U?$DefaultEqualityPredicate@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVInstalledDesktopApp@Inventory@System@Windows@@@6784@U?$DefaultVectorOptions@PEAVInstalledDesktopApp@Inventory@System@Windows@@@6784@@Internal@Collections@Foundation@4@@Z; Windows::System::Inventory::CInstalledDesktopAppStatics::GetInventoryFromArp(Windows::Foundation::Collections::Internal::Vector<Windows::System::Inventory::InstalledDesktopApp *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::Inventory::InstalledDesktopApp *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::Inventory::InstalledDesktopApp *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::System::Inventory::InstalledDesktopApp *>> *)
0x180025e17  mov     ebx, eax
0x180025e19  test    eax, eax
0x180025e1b  js      short loc_180025E60
0x180025e1d  mov     rax, [rdi]
0x180025e20  lea     rdx, [rbp+arg_10]
0x180025e24  mov     rcx, rdi
0x180025e27  mov     [rbp+arg_10], 0
0x180025e2e  mov     rax, [rax+38h]
0x180025e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e37  test    eax, eax
0x180025e39  js      short loc_180025E60
0x180025e3b  mov     eax, [rbp+arg_10]
0x180025e3e  lea     r9, aSuccessfullyRe_0; "Successfully retrieved %d apps from ARP"
0x180025e45  mov     r8d, 101h
0x180025e4b  mov     dword ptr [rsp+40h+pdwType], eax
0x180025e4f  lea     rdx, aWindowsSystemI_0; "Windows::System::Inventory::CInstalledD"...
0x180025e56  mov     ecx, 3
0x180025e5b  call    AslLogCallPrintf
0x180025e60  mov     eax, ebx
0x180025e62  add     rsp, 40h
0x180025e66  pop     rdi
0x180025e67  pop     rbx
0x180025e68  pop     rbp
0x180025e69  retn
```
