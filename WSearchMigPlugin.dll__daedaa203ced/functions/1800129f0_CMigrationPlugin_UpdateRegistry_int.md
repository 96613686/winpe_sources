# CMigrationPlugin::UpdateRegistry(int)

- ea: `0x1800129f0`
- end: `0x180012afd`
- name: `?UpdateRegistry@CMigrationPlugin@@SAJH@Z`
- size: `269`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x18000d2b0`
- `0x18000d498`
- `0x18000d8f0`
- `0x1800129f0`
- `0x180012b04`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012ad4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012aeb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012ad4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012aeb`

## string_xrefs

- `0x180012a30`: `CMigrationPlugin Object`

## pseudocode

```c
__int64 __fastcall CMigrationPlugin::UpdateRegistry(int a1)
{
  HRESULT v2; // ebx
  unsigned int *v3; // rcx
  unsigned __int64 v4; // rdx
  void **v6; // [rsp+40h] [rbp-38h] BYREF
  void *Block[2]; // [rsp+48h] [rbp-30h]
  int v8; // [rsp+58h] [rbp-20h]
  unsigned int *i; // [rsp+A8h] [rbp+30h] BYREF

  v8 = 0;
  v6 = &ATL::CRegistryVirtualMachine::`vftable';
  *(_OWORD *)Block = 0;
  v2 = ATL::CRegistryVirtualMachine::AddStandardReplacements((ATL::CRegistryVirtualMachine *)&v6);
  if ( v2 >= 0 )
  {
    ATL::CRegistryVirtualMachine::AddReplacement(
      (ATL::CRegistryVirtualMachine *)&v6,
      L"FriendlyName",
      L"CMigrationPlugin Object");
    v3 = (unsigned int *)`CMigrationPlugin::GetOpCodes'::`2'::rgOps;
    v2 = 0;
    for ( i = (unsigned int *)`CMigrationPlugin::GetOpCodes'::`2'::rgOps; ; v3 = i )
    {
      v4 = *v3;
      if ( !(_DWORD)v4 )
        break;
      if ( (v4 & 0xF0000000) != 0x70000000 )
      {
        v2 = -2147467259;
        break;
      }
      i = v3 + 1;
      v2 = ATL::CRegistryVirtualMachine::VMUpdateRegistryRecurse(
             (ATL::CRegistryVirtualMachine *)&v6,
             (HKEY)((v4 >> 14) & 0x3FFF | 0xFFFFFFFF80000000uLL),
             &i,
             (struct ATL::RGSStrings *)&`CMigrationPlugin::GetOpcodeStringVals'::`2'::rgStrings,
             (struct ATL::RGSDWORD *)&`CMigrationPlugin::GetOpcodeDWORDVals'::`2'::rgDWORDS,
             (struct ATL::RGSBinary *)`CMigrationPlugin::GetOpcodeBinaryVals'::`2'::rgBinary,
             a1);
      if ( v2 < 0 )
        break;
    }
  }
  v6 = &ATL::CRegistryVirtualMachine::`vftable';
  ATL::CRegistryVirtualMachine::ClearReplacements((ATL::CRegistryVirtualMachine *)&v6);
  if ( Block[0] )
  {
    free(Block[0]);
    Block[0] = 0;
  }
  if ( Block[1] )
    free(Block[1]);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800129f0  push    rbp
0x1800129f2  push    rbx
0x1800129f3  push    rdi
0x1800129f4  push    r14
0x1800129f6  mov     rbp, rsp
0x1800129f9  sub     rsp, 78h
0x1800129fd  mov     edi, ecx
0x1800129ff  mov     [rbp+var_20], 0
0x180012a06  xorps   xmm0, xmm0
0x180012a09  lea     r14, ??_7CRegistryVirtualMachine@ATL@@6B@; const ATL::CRegistryVirtualMachine::`vftable'
0x180012a10  lea     rcx, [rbp+var_38]; this
0x180012a14  mov     [rbp+var_38], r14
0x180012a18  movdqu  xmmword ptr [rbp+Block], xmm0
0x180012a1d  call    ?AddStandardReplacements@CRegistryVirtualMachine@ATL@@QEAAJXZ; ATL::CRegistryVirtualMachine::AddStandardReplacements(void)
0x180012a22  lea     rcx, [rbp+var_38]; this
0x180012a26  mov     ebx, eax
0x180012a28  test    eax, eax
0x180012a2a  js      loc_180012AC2
0x180012a30  lea     r8, aCmigrationplug; "CMigrationPlugin Object"
0x180012a37  lea     rdx, aFriendlyname_0; "FriendlyName"
0x180012a3e  call    ?AddReplacement@CRegistryVirtualMachine@ATL@@UEAAJPEB_W0@Z; ATL::CRegistryVirtualMachine::AddReplacement(wchar_t const *,wchar_t const *)
0x180012a43  lea     rcx, ?rgOps@?1??GetOpCodes@CMigrationPlugin@@SAPEAKXZ@4PAKA; ulong near * `CMigrationPlugin::GetOpCodes(void)'::`2'::rgOps
0x180012a4a  xor     ebx, ebx
0x180012a4c  mov     [rbp+arg_8], rcx
0x180012a50  mov     edx, [rcx]
0x180012a52  test    edx, edx
0x180012a54  jz      short loc_180012ABE
0x180012a56  mov     eax, edx
0x180012a58  and     eax, 0F0000000h
0x180012a5d  cmp     eax, 70000000h
0x180012a62  jnz     short loc_180012AB9
0x180012a64  shr     rdx, 0Eh
0x180012a68  lea     rax, ?rgBinary@?1??GetOpcodeBinaryVals@CMigrationPlugin@@SAPEAURGSBinary@ATL@@XZ@4PAU34@A; ATL::RGSBinary near * `CMigrationPlugin::GetOpcodeBinaryVals(void)'::`2'::rgBinary
0x180012a6f  add     rcx, 4
0x180012a73  mov     [rsp+78h+var_48], edi; int
0x180012a77  mov     [rsp+78h+var_50], rax; struct ATL::RGSBinary *
0x180012a7c  lea     r9, ?rgStrings@?1??GetOpcodeStringVals@CMigrationPlugin@@SAPEAURGSStrings@ATL@@XZ@4PAU34@A; struct ATL::RGSStrings *
0x180012a83  and     edx, 3FFFh
0x180012a89  mov     [rbp+arg_8], rcx
0x180012a8d  lea     rax, ?rgDWORDS@?1??GetOpcodeDWORDVals@CMigrationPlugin@@SAPEAURGSDWORD@ATL@@XZ@4PAU34@A; ATL::RGSDWORD near * `CMigrationPlugin::GetOpcodeDWORDVals(void)'::`2'::rgDWORDS
0x180012a94  or      rdx, 0FFFFFFFF80000000h; HKEY
0x180012a9b  lea     r8, [rbp+arg_8]; unsigned int **
0x180012a9f  mov     [rsp+78h+var_58], rax; struct ATL::RGSDWORD *
0x180012aa4  lea     rcx, [rbp+var_38]; this
0x180012aa8  call    ?VMUpdateRegistryRecurse@CRegistryVirtualMachine@ATL@@QEAAJPEAUHKEY__@@AEAPEAKPEAURGSStrings@2@PEAURGSDWORD@2@PEAURGSBinary@2@H@Z; ATL::CRegistryVirtualMachine::VMUpdateRegistryRecurse(HKEY__ *,ulong * &,ATL::RGSStrings *,ATL::RGSDWORD *,ATL::RGSBinary *,int)
0x180012aad  mov     ebx, eax
0x180012aaf  test    eax, eax
0x180012ab1  js      short loc_180012ABE
0x180012ab3  mov     rcx, [rbp+arg_8]
0x180012ab7  jmp     short loc_180012A50
0x180012ab9  mov     ebx, 80004005h
0x180012abe  lea     rcx, [rbp+var_38]; this
0x180012ac2  mov     [rbp+var_38], r14
0x180012ac6  call    ?ClearReplacements@CRegistryVirtualMachine@ATL@@UEAAJXZ; ATL::CRegistryVirtualMachine::ClearReplacements(void)
0x180012acb  mov     rcx, [rbp+Block]; Block
0x180012acf  test    rcx, rcx
0x180012ad2  jz      short loc_180012AE2
0x180012ad4  call    cs:__imp_free
0x180012ada  mov     [rbp+Block], 0
0x180012ae2  mov     rcx, [rbp+Block+8]; Block
0x180012ae6  test    rcx, rcx
0x180012ae9  jz      short loc_180012AF1
0x180012aeb  call    cs:__imp_free
0x180012af1  mov     eax, ebx
0x180012af3  add     rsp, 78h
0x180012af7  pop     r14
0x180012af9  pop     rdi
0x180012afa  pop     rbx
0x180012afb  pop     rbp
0x180012afc  retn
```
