# GetRenewPeriodInSeconds(ushort const *,ulong *)

- ea: `0x180093124`
- end: `0x18009324a`
- name: `?GetRenewPeriodInSeconds@@YAJPEBGPEAK@Z`
- size: `294`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180033584`

## callees

- `0x180019ae4`
- `0x18002b664`
- `0x180093124`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800931c4`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800931c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800931a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009322e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800931a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009322e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009317c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009317c`

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
0x180093124  mov     [rsp-18h+arg_0], rbx
0x180093129  mov     [rsp-18h+arg_8], rsi
0x18009312e  push    rbp
0x18009312f  push    rdi
0x180093130  push    r14
0x180093132  mov     rbp, rsp
0x180093135  sub     rsp, 40h
0x180093139  mov     rsi, rdx
0x18009313c  mov     r14, rcx
0x18009313f  mov     [rbp+arg_18], 0
0x180093146  mov     edi, 375F00h
0x18009314b  mov     [rbp+arg_10], edi
0x18009314e  mov     [rbp+hKey], 0
0x180093156  mov     ecx, 1
0x18009315b  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x180093160  lea     rcx, [rbp+hKey]
0x180093164  mov     [rsp+40h+phkResult], rcx; phkResult
0x180093169  mov     r9d, 20019h; samDesired
0x18009316f  xor     r8d, r8d; ulOptions
0x180093172  mov     rdx, rax; lpSubKey
0x180093175  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009317c  call    cs:__imp_RegOpenKeyExW
0x180093182  mov     ebx, eax
0x180093184  test    eax, eax
0x180093186  jle     short loc_180093191
0x180093188  movzx   ebx, ax
0x18009318b  or      ebx, 80070000h
0x180093191  test    ebx, ebx
0x180093193  jns     short loc_1800931B2
0x180093195  mov     rcx, [rbp+hKey]; hKey
0x180093199  mov     [rbp+hKey], 0
0x1800931a1  test    rcx, rcx
0x1800931a4  jz      short loc_1800931AD
0x1800931a6  call    cs:__imp_RegCloseKey
0x1800931ac  nop
0x1800931ad  jmp     loc_180093235
0x1800931b2  lea     r9, [rbp+arg_18]
0x1800931b6  lea     r8, aRenewalperiod; "RenewalPeriod"
0x1800931bd  mov     rdx, r14
0x1800931c0  mov     rcx, [rbp+hKey]
0x1800931c4  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800931ca  test    eax, eax
0x1800931cc  jns     short loc_1800931D2
0x1800931ce  xor     ebx, ebx
0x1800931d0  jmp     short loc_18009321B
0x1800931d2  mov     eax, [rbp+arg_18]
0x1800931d5  lea     rcx, [rax+rax*2]
0x1800931d9  shl     rcx, 3; unsigned __int64
0x1800931dd  lea     rdx, [rbp+arg_10]; unsigned int *
0x1800931e1  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800931e6  mov     ebx, eax
0x1800931e8  test    eax, eax
0x1800931ea  js      short loc_18009321D
0x1800931ec  mov     eax, [rbp+arg_10]
0x1800931ef  imul    rcx, rax, 3Ch ; '<'; unsigned __int64
0x1800931f3  lea     rdx, [rbp+arg_10]; unsigned int *
0x1800931f7  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800931fc  mov     ebx, eax
0x1800931fe  test    eax, eax
0x180093200  js      short loc_18009321D
0x180093202  mov     eax, [rbp+arg_10]
0x180093205  imul    rcx, rax, 3Ch ; '<'; unsigned __int64
0x180093209  lea     rdx, [rbp+arg_10]; unsigned int *
0x18009320d  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180093212  mov     ebx, eax
0x180093214  test    eax, eax
0x180093216  js      short loc_18009321D
0x180093218  mov     edi, [rbp+arg_10]
0x18009321b  mov     [rsi], edi
0x18009321d  mov     rcx, [rbp+hKey]; hKey
0x180093221  mov     [rbp+hKey], 0
0x180093229  test    rcx, rcx
0x18009322c  jz      short loc_180093235
0x18009322e  call    cs:__imp_RegCloseKey
0x180093234  nop
0x180093235  mov     eax, ebx
0x180093237  mov     rbx, [rsp+40h+arg_0]
0x18009323c  mov     rsi, [rsp+40h+arg_8]
0x180093241  add     rsp, 40h
0x180093245  pop     r14
0x180093247  pop     rdi
0x180093248  pop     rbp
0x180093249  retn
```
