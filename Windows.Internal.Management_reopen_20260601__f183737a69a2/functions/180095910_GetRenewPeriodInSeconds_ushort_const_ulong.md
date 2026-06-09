# GetRenewPeriodInSeconds(ushort const *,ulong *)

- ea: `0x180095910`
- end: `0x180095a4f`
- name: `?GetRenewPeriodInSeconds@@YAJPEBGPEAK@Z`
- size: `319`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800323e8`

## callees

- `0x1800184c0`
- `0x18002a028`
- `0x180095910`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800959bc`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800959bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095998`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095a2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095998`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095a2c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180095968`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180095968`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetRenewPeriodInSeconds(const unsigned __int16 *a1, unsigned int *a2)
{
  unsigned int v4; // edi
  const WCHAR *v5; // rax
  LSTATUS v6; // eax
  signed int v7; // ebx
  HKEY v8; // rcx
  HKEY v9; // rcx
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v12; // [rsp+70h] [rbp+30h] BYREF
  unsigned int v13; // [rsp+78h] [rbp+38h] BYREF

  v13 = 0;
  v4 = 3628800;
  v12 = 3628800;
  hKey = 0;
  v5 = (const WCHAR *)DMGetKnownRegPath(1);
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20019u, &hKey);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 < 0 )
  {
    v8 = hKey;
    hKey = 0;
    if ( v8 )
      RegCloseKey(v8);
    return (unsigned int)v7;
  }
  if ( (int)OmaDmRegistryGetDWORD(hKey, a1, L"RenewalPeriod", &v13) < 0 )
  {
    v7 = 0;
LABEL_13:
    *a2 = v4;
    goto LABEL_14;
  }
  v7 = ULongLongToULong(24LL * v13, &v12);
  if ( v7 >= 0 )
  {
    v7 = ULongLongToULong(60LL * v12, &v12);
    if ( v7 >= 0 )
    {
      v7 = ULongLongToULong(60LL * v12, &v12);
      if ( v7 >= 0 )
      {
        v4 = v12;
        goto LABEL_13;
      }
    }
  }
LABEL_14:
  v9 = hKey;
  hKey = 0;
  if ( v9 )
    RegCloseKey(v9);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180095910  mov     [rsp-18h+arg_0], rbx
0x180095915  mov     [rsp-18h+arg_8], rsi
0x18009591a  push    rbp
0x18009591b  push    rdi
0x18009591c  push    r14
0x18009591e  mov     rbp, rsp
0x180095921  sub     rsp, 40h
0x180095925  mov     rsi, rdx
0x180095928  mov     r14, rcx
0x18009592b  mov     [rbp+arg_18], 0
0x180095932  mov     edi, 375F00h
0x180095937  mov     [rbp+arg_10], edi
0x18009593a  mov     [rbp+hKey], 0
0x180095942  mov     ecx, 1
0x180095947  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x18009594c  lea     rcx, [rbp+hKey]
0x180095950  mov     [rsp+40h+phkResult], rcx; phkResult
0x180095955  mov     r9d, 20019h; samDesired
0x18009595b  xor     r8d, r8d; ulOptions
0x18009595e  mov     rdx, rax; lpSubKey
0x180095961  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180095968  call    cs:__imp_RegOpenKeyExW
0x18009596f  nop     dword ptr [rax+rax+00h]
0x180095974  mov     ebx, eax
0x180095976  test    eax, eax
0x180095978  jle     short loc_180095983
0x18009597a  movzx   ebx, ax
0x18009597d  or      ebx, 80070000h
0x180095983  test    ebx, ebx
0x180095985  jns     short loc_1800959AA
0x180095987  mov     rcx, [rbp+hKey]; hKey
0x18009598b  mov     [rbp+hKey], 0
0x180095993  test    rcx, rcx
0x180095996  jz      short loc_1800959A5
0x180095998  call    cs:__imp_RegCloseKey
0x18009599f  nop     dword ptr [rax+rax+00h]
0x1800959a4  nop
0x1800959a5  jmp     loc_180095A39
0x1800959aa  lea     r9, [rbp+arg_18]
0x1800959ae  lea     r8, aRenewalperiod; "RenewalPeriod"
0x1800959b5  mov     rdx, r14
0x1800959b8  mov     rcx, [rbp+hKey]
0x1800959bc  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800959c3  nop     dword ptr [rax+rax+00h]
0x1800959c8  test    eax, eax
0x1800959ca  jns     short loc_1800959D0
0x1800959cc  xor     ebx, ebx
0x1800959ce  jmp     short loc_180095A19
0x1800959d0  mov     eax, [rbp+arg_18]
0x1800959d3  lea     rcx, [rax+rax*2]
0x1800959d7  shl     rcx, 3; unsigned __int64
0x1800959db  lea     rdx, [rbp+arg_10]; unsigned int *
0x1800959df  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800959e4  mov     ebx, eax
0x1800959e6  test    eax, eax
0x1800959e8  js      short loc_180095A1B
0x1800959ea  mov     eax, [rbp+arg_10]
0x1800959ed  imul    rcx, rax, 3Ch ; '<'; unsigned __int64
0x1800959f1  lea     rdx, [rbp+arg_10]; unsigned int *
0x1800959f5  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800959fa  mov     ebx, eax
0x1800959fc  test    eax, eax
0x1800959fe  js      short loc_180095A1B
0x180095a00  mov     eax, [rbp+arg_10]
0x180095a03  imul    rcx, rax, 3Ch ; '<'; unsigned __int64
0x180095a07  lea     rdx, [rbp+arg_10]; unsigned int *
0x180095a0b  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180095a10  mov     ebx, eax
0x180095a12  test    eax, eax
0x180095a14  js      short loc_180095A1B
0x180095a16  mov     edi, [rbp+arg_10]
0x180095a19  mov     [rsi], edi
0x180095a1b  mov     rcx, [rbp+hKey]; hKey
0x180095a1f  mov     [rbp+hKey], 0
0x180095a27  test    rcx, rcx
0x180095a2a  jz      short loc_180095A39
0x180095a2c  call    cs:__imp_RegCloseKey
0x180095a33  nop     dword ptr [rax+rax+00h]
0x180095a38  nop
0x180095a39  mov     eax, ebx
0x180095a3b  mov     rbx, [rsp+40h+arg_0]
0x180095a40  mov     rsi, [rsp+40h+arg_8]
0x180095a45  add     rsp, 40h
0x180095a49  pop     r14
0x180095a4b  pop     rdi
0x180095a4c  pop     rbp
0x180095a4d  retn
```
