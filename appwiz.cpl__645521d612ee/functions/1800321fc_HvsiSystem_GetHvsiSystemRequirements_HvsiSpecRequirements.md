# HvsiSystem::GetHvsiSystemRequirements(HvsiSpecRequirements &)

- ea: `0x1800321fc`
- end: `0x1800323e5`
- name: `?GetHvsiSystemRequirements@HvsiSystem@@SAXAEAUHvsiSpecRequirements@@@Z`
- size: `489`
- prototype: `void __fastcall(struct HvsiSpecRequirements *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180033c6c`

## callees

- `0x180031d54`
- `0x1800321fc`
- `0x1800582a2`
- `0x1800582e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003228d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800322d9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180032326`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003228d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800322d9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180032326`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x180032383`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x180032383`
- `api-ms-win-core-sysinfo-l1-2-1!GetPhysicallyInstalledSystemMemory` at `0x18003235c`
- `api-ms-win-core-sysinfo-l1-2-1!GetPhysicallyInstalledSystemMemory` at `0x18003235c`
- `KERNEL32!GetActiveProcessorCount` at `0x18003234e`
- `KERNEL32!GetActiveProcessorCount` at `0x18003234e`

## pseudocode

```c
void __fastcall HvsiSystem::GetHvsiSystemRequirements(struct HvsiSpecRequirements *a1)
{
  unsigned __int64 v2; // rax
  ULONGLONG v3; // rax
  int pvData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int64 TotalMemoryInKilobytes; // [rsp+48h] [rbp-B8h] BYREF
  union _ULARGE_INTEGER FreeBytesAvailableToCaller; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v8[264]; // [rsp+60h] [rbp-A0h] BYREF

  *(_DWORD *)a1 = 4;
  *((_DWORD *)a1 + 2) = 8;
  *((_DWORD *)a1 + 4) = 5;
  *((_BYTE *)a1 + 24) = 0;
  pcbData = 4;
  pvData = 0;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\HVSI",
          L"SpecRequiredProcessorCount",
          0x10u,
          0,
          &pvData,
          &pcbData) )
    *(_DWORD *)a1 = pvData;
  pcbData = 4;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\HVSI",
          L"SpecRequiredMemoryInGB",
          0x10u,
          0,
          &pvData,
          &pcbData) )
    *((_DWORD *)a1 + 2) = pvData;
  pcbData = 4;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\HVSI",
          L"SpecRequiredFreeDiskSpaceInGB",
          0x10u,
          0,
          &pvData,
          &pcbData) )
    *((_DWORD *)a1 + 4) = pvData;
  TotalMemoryInKilobytes = 0;
  FreeBytesAvailableToCaller.QuadPart = 0;
  *((_DWORD *)a1 + 1) = GetActiveProcessorCount(0xFFFFu);
  if ( GetPhysicallyInstalledSystemMemory(&TotalMemoryInKilobytes) )
    v2 = TotalMemoryInKilobytes >> 20;
  else
    LODWORD(v2) = 0;
  *((_DWORD *)a1 + 3) = v2;
  if ( GetDiskFreeSpaceExW(0, &FreeBytesAvailableToCaller, 0, 0) )
    v3 = FreeBytesAvailableToCaller.QuadPart >> 30;
  else
    LODWORD(v3) = 0;
  *((_DWORD *)a1 + 5) = v3;
  memset_0(v8, 0, 0x208u);
  if ( (int)HvsiSystem::GetBabyWimPath(v8) >= 0 )
    *((_BYTE *)a1 + 24) = 1;
}

```

## disassembly

```asm
0x1800321fc  mov     [rsp-8+arg_8], rbx
0x180032201  mov     [rsp-8+arg_10], r12
0x180032206  push    rbp
0x180032207  lea     rbp, [rsp-180h]
0x18003220f  sub     rsp, 280h
0x180032216  mov     rax, cs:__security_cookie
0x18003221d  xor     rax, rsp
0x180032220  mov     [rbp+180h+var_10], rax
0x180032227  lea     rax, [rsp+280h+var_23C]
0x18003222c  mov     dword ptr [rcx], 4
0x180032232  mov     [rsp+280h+pcbData], rax; pcbData
0x180032237  lea     r8, aSpecrequiredpr; "SpecRequiredProcessorCount"
0x18003223e  lea     rax, [rsp+280h+var_240]
0x180032243  mov     dword ptr [rcx+8], 8
0x18003224a  mov     rbx, rcx
0x18003224d  mov     dword ptr [rcx+10h], 5
0x180032254  mov     byte ptr [rcx+18h], 0
0x180032258  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\HVSI"
0x18003225f  mov     [rsp+280h+pvData], rax; pvData
0x180032264  mov     r12, 0FFFFFFFF80000002h
0x18003226b  mov     r9d, 10h; dwFlags
0x180032271  mov     [rsp+280h+pdwType], 0; pdwType
0x18003227a  mov     rcx, r12; hkey
0x18003227d  mov     [rsp+280h+var_23C], 4
0x180032285  mov     [rsp+280h+var_240], 0
0x18003228d  call    cs:__imp_RegGetValueW
0x180032293  test    eax, eax
0x180032295  jnz     short loc_18003229D
0x180032297  mov     eax, [rsp+280h+var_240]
0x18003229b  mov     [rbx], eax
0x18003229d  lea     rax, [rsp+280h+var_23C]
0x1800322a2  mov     [rsp+280h+var_23C], 4
0x1800322aa  mov     [rsp+280h+pcbData], rax; pcbData
0x1800322af  lea     r8, aSpecrequiredme; "SpecRequiredMemoryInGB"
0x1800322b6  lea     rax, [rsp+280h+var_240]
0x1800322bb  mov     r9d, 10h; dwFlags
0x1800322c1  mov     [rsp+280h+pvData], rax; pvData
0x1800322c6  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\HVSI"
0x1800322cd  mov     rcx, r12; hkey
0x1800322d0  mov     [rsp+280h+pdwType], 0; pdwType
0x1800322d9  call    cs:__imp_RegGetValueW
0x1800322df  test    eax, eax
0x1800322e1  jnz     short loc_1800322EA
0x1800322e3  mov     eax, [rsp+280h+var_240]
0x1800322e7  mov     [rbx+8], eax
0x1800322ea  lea     rax, [rsp+280h+var_23C]
0x1800322ef  mov     [rsp+280h+var_23C], 4
0x1800322f7  mov     [rsp+280h+pcbData], rax; pcbData
0x1800322fc  lea     r8, aSpecrequiredfr; "SpecRequiredFreeDiskSpaceInGB"
0x180032303  lea     rax, [rsp+280h+var_240]
0x180032308  mov     r9d, 10h; dwFlags
0x18003230e  mov     [rsp+280h+pvData], rax; pvData
0x180032313  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\HVSI"
0x18003231a  mov     rcx, r12; hkey
0x18003231d  mov     [rsp+280h+pdwType], 0; pdwType
0x180032326  call    cs:__imp_RegGetValueW
0x18003232c  test    eax, eax
0x18003232e  jnz     short loc_180032337
0x180032330  mov     eax, [rsp+280h+var_240]
0x180032334  mov     [rbx+10h], eax
0x180032337  mov     ecx, 0FFFFh; GroupNumber
0x18003233c  mov     [rsp+280h+TotalMemoryInKilobytes], 0
0x180032345  mov     qword ptr [rsp+280h+FreeBytesAvailableToCaller], 0
0x18003234e  call    cs:__imp_GetActiveProcessorCount
0x180032354  lea     rcx, [rsp+280h+TotalMemoryInKilobytes]; TotalMemoryInKilobytes
0x180032359  mov     [rbx+4], eax
0x18003235c  call    cs:__imp_GetPhysicallyInstalledSystemMemory
0x180032362  test    eax, eax
0x180032364  jz      short loc_180032371
0x180032366  mov     rax, [rsp+280h+TotalMemoryInKilobytes]
0x18003236b  shr     rax, 14h
0x18003236f  jmp     short loc_180032373
0x180032371  xor     eax, eax
0x180032373  xor     r9d, r9d; lpTotalNumberOfFreeBytes
0x180032376  mov     [rbx+0Ch], eax
0x180032379  xor     r8d, r8d; lpTotalNumberOfBytes
0x18003237c  lea     rdx, [rsp+280h+FreeBytesAvailableToCaller]; lpFreeBytesAvailableToCaller
0x180032381  xor     ecx, ecx; lpDirectoryName
0x180032383  call    cs:__imp_GetDiskFreeSpaceExW
0x180032389  test    eax, eax
0x18003238b  jz      short loc_180032398
0x18003238d  mov     rax, qword ptr [rsp+280h+FreeBytesAvailableToCaller]
0x180032392  shr     rax, 1Eh
0x180032396  jmp     short loc_18003239A
0x180032398  xor     eax, eax
0x18003239a  xor     edx, edx; Val
0x18003239c  mov     [rbx+14h], eax
0x18003239f  mov     r8d, 208h; Size
0x1800323a5  lea     rcx, [rsp+280h+var_220]; void *
0x1800323aa  call    memset_0
0x1800323af  lea     rcx, [rsp+280h+var_220]; unsigned __int16 *
0x1800323b4  call    ?GetBabyWimPath@HvsiSystem@@CAJPEAGK@Z; HvsiSystem::GetBabyWimPath(ushort *,ulong)
0x1800323b9  test    eax, eax
0x1800323bb  js      short loc_1800323C1
0x1800323bd  mov     byte ptr [rbx+18h], 1
0x1800323c1  mov     rcx, [rbp+180h+var_10]
0x1800323c8  xor     rcx, rsp; StackCookie
0x1800323cb  call    __security_check_cookie
0x1800323d0  lea     r11, [rsp+280h+var_s0]
0x1800323d8  mov     rbx, [r11+18h]
0x1800323dc  mov     r12, [r11+20h]
0x1800323e0  mov     rsp, r11
0x1800323e3  pop     rbp
0x1800323e4  retn
```
