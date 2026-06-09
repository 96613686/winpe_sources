# GetRenewPeriodInSeconds(ushort const *,ulong *)

- ea: `0x140051a48`
- end: `0x140051b40`
- name: `?GetRenewPeriodInSeconds@@YAJPEBGPEAK@Z`
- size: `248`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x14002c1b0`

## callees

- `0x140051a48`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140051acd`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140051acd`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140051a6d`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140051a6d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140051aa0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140051aa0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051b28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051b28`

## pseudocode

```c
__int64 __fastcall GetRenewPeriodInSeconds(const unsigned __int16 *a1, unsigned int *a2)
{
  char IsStateSeparationEnabled; // al
  LSTATUS v5; // eax
  signed int v6; // ebx
  HKEY v7; // rcx
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  unsigned int v12; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  v12 = 0;
  hKey = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         *(wchar_t **)((char *)off_14005EF50 + (IsStateSeparationEnabled != 0 ? 8 : 0)),
         0,
         0x20019u,
         &hKey);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  v7 = hKey;
  if ( v6 >= 0 )
  {
    if ( (int)OmaDmRegistryGetDWORD(hKey, a1, L"RenewalPeriod", &v12) >= 0 )
    {
      v9 = 24LL * v12;
      if ( v9 > 0xFFFFFFFF
        || (v10 = 60LL * (unsigned int)v9, v10 > 0xFFFFFFFF)
        || (v8 = 60LL * (unsigned int)v10, v8 > 0xFFFFFFFF) )
      {
        v6 = -2147024362;
        goto LABEL_11;
      }
    }
    else
    {
      LODWORD(v8) = 3628800;
    }
    v6 = 0;
    *a2 = v8;
LABEL_11:
    v7 = hKey;
  }
  hKey = 0;
  if ( v7 )
    RegCloseKey(v7);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140051a48  mov     rax, rsp
0x140051a4b  mov     [rax+8], rbx
0x140051a4f  mov     [rax+10h], rsi
0x140051a53  push    rdi
0x140051a54  sub     rsp, 30h
0x140051a58  mov     rdi, rdx
0x140051a5b  mov     dword ptr [rax+18h], 0
0x140051a62  mov     rsi, rcx
0x140051a65  mov     qword ptr [rax+20h], 0
0x140051a6d  call    cs:__imp_RtlIsStateSeparationEnabled
0x140051a73  lea     rcx, off_14005EF50; "Software\\Microsoft\\Enrollments"
0x140051a7a  mov     r9d, 20019h; samDesired
0x140051a80  neg     al
0x140051a82  lea     rax, [rsp+38h+hKey]
0x140051a87  sbb     rdx, rdx
0x140051a8a  mov     [rsp+38h+phkResult], rax; phkResult
0x140051a8f  and     edx, 8
0x140051a92  xor     r8d, r8d; ulOptions
0x140051a95  mov     rdx, [rdx+rcx]; lpSubKey
0x140051a99  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140051aa0  call    cs:__imp_RegOpenKeyExW
0x140051aa6  mov     ebx, eax
0x140051aa8  test    eax, eax
0x140051aaa  jle     short loc_140051AB5
0x140051aac  movzx   ebx, ax
0x140051aaf  or      ebx, 80070000h
0x140051ab5  mov     rcx, [rsp+38h+hKey]
0x140051aba  test    ebx, ebx
0x140051abc  js      short loc_140051B1A
0x140051abe  lea     r9, [rsp+38h+arg_10]
0x140051ac3  mov     rdx, rsi
0x140051ac6  lea     r8, aRenewalperiod; "RenewalPeriod"
0x140051acd  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x140051ad3  test    eax, eax
0x140051ad5  jns     short loc_140051ADE
0x140051ad7  mov     eax, 375F00h
0x140051adc  jmp     short loc_140051B0A
0x140051ade  mov     eax, [rsp+38h+arg_10]
0x140051ae2  mov     edx, 0FFFFFFFFh
0x140051ae7  lea     rcx, [rax+rax*2]
0x140051aeb  shl     rcx, 3
0x140051aef  cmp     rcx, rdx
0x140051af2  ja      short loc_140051B10
0x140051af4  mov     eax, ecx
0x140051af6  imul    rcx, rax, 3Ch ; '<'
0x140051afa  cmp     rcx, rdx
0x140051afd  ja      short loc_140051B10
0x140051aff  mov     eax, ecx
0x140051b01  imul    rax, 3Ch ; '<'
0x140051b05  cmp     rax, rdx
0x140051b08  ja      short loc_140051B10
0x140051b0a  xor     ebx, ebx
0x140051b0c  mov     [rdi], eax
0x140051b0e  jmp     short loc_140051B15
0x140051b10  mov     ebx, 80070216h
0x140051b15  mov     rcx, [rsp+38h+hKey]; hKey
0x140051b1a  mov     [rsp+38h+hKey], 0
0x140051b23  test    rcx, rcx
0x140051b26  jz      short loc_140051B2E
0x140051b28  call    cs:__imp_RegCloseKey
0x140051b2e  mov     rsi, [rsp+38h+arg_8]
0x140051b33  mov     eax, ebx
0x140051b35  mov     rbx, [rsp+38h+arg_0]
0x140051b3a  add     rsp, 30h
0x140051b3e  pop     rdi
0x140051b3f  retn
```
