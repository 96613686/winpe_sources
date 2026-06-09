# GetRenewPeriodInSeconds(ushort const *,ulong *)

- ea: `0x140012220`
- end: `0x140012328`
- name: `?GetRenewPeriodInSeconds@@YAJPEBGPEAK@Z`
- size: `264`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140007f34`

## callees

- `0x140007724`
- `0x14000b288`
- `0x140012220`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001230d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001230d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140012278`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140012278`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1400122a3`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1400122a3`

## pseudocode

```c
__int64 __fastcall GetRenewPeriodInSeconds(const unsigned __int16 *a1, unsigned int *a2)
{
  unsigned int v3; // edi
  const WCHAR *v5; // rax
  LSTATUS v6; // eax
  signed int v7; // ebx
  HKEY v8; // rcx
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v11; // [rsp+70h] [rbp+30h] BYREF
  unsigned int v12; // [rsp+78h] [rbp+38h] BYREF

  v12 = 0;
  v3 = 3628800;
  hKey = 0;
  v11 = 3628800;
  v5 = (const WCHAR *)DMGetKnownRegPath(1);
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20019u, &hKey);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  v8 = hKey;
  if ( v7 >= 0 )
  {
    if ( (int)OmaDmRegistryGetDWORD(hKey, a1, L"RenewalPeriod", &v12) >= 0 )
    {
      v7 = ULongLongToULong(24LL * v12, &v11);
      if ( v7 < 0 )
        goto LABEL_11;
      v7 = ULongLongToULong(60LL * v11, &v11);
      if ( v7 < 0 )
        goto LABEL_11;
      v7 = ULongLongToULong(60LL * v11, &v11);
      if ( v7 < 0 )
        goto LABEL_11;
      v3 = v11;
    }
    else
    {
      v7 = 0;
    }
    *a2 = v3;
LABEL_11:
    v8 = hKey;
  }
  hKey = 0;
  if ( v8 )
    RegCloseKey(v8);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140012220  mov     [rsp-18h+arg_0], rbx
0x140012225  mov     [rsp-18h+arg_8], rsi
0x14001222a  push    rbp
0x14001222b  push    rdi
0x14001222c  push    r14
0x14001222e  mov     rbp, rsp
0x140012231  sub     rsp, 40h
0x140012235  mov     r14, rcx
0x140012238  mov     [rbp+arg_18], 0
0x14001223f  mov     edi, 375F00h
0x140012244  mov     [rbp+hKey], 0
0x14001224c  mov     ecx, 1
0x140012251  mov     [rbp+arg_10], edi
0x140012254  mov     rsi, rdx
0x140012257  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x14001225c  lea     rcx, [rbp+hKey]
0x140012260  mov     r9d, 20019h; samDesired
0x140012266  mov     [rsp+40h+phkResult], rcx; phkResult
0x14001226b  xor     r8d, r8d; ulOptions
0x14001226e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140012275  mov     rdx, rax; lpSubKey
0x140012278  call    cs:__imp_RegOpenKeyExW
0x14001227e  mov     ebx, eax
0x140012280  test    eax, eax
0x140012282  jle     short loc_14001228D
0x140012284  movzx   ebx, ax
0x140012287  or      ebx, 80070000h
0x14001228d  mov     rcx, [rbp+hKey]
0x140012291  test    ebx, ebx
0x140012293  js      short loc_140012300
0x140012295  lea     r9, [rbp+arg_18]
0x140012299  mov     rdx, r14
0x14001229c  lea     r8, aRenewalperiod; "RenewalPeriod"
0x1400122a3  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1400122a9  test    eax, eax
0x1400122ab  jns     short loc_1400122B1
0x1400122ad  xor     ebx, ebx
0x1400122af  jmp     short loc_1400122FA
0x1400122b1  mov     eax, [rbp+arg_18]
0x1400122b4  lea     rdx, [rbp+arg_10]; unsigned int *
0x1400122b8  lea     rcx, [rax+rax*2]
0x1400122bc  shl     rcx, 3; unsigned __int64
0x1400122c0  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1400122c5  mov     ebx, eax
0x1400122c7  test    eax, eax
0x1400122c9  js      short loc_1400122FC
0x1400122cb  mov     eax, [rbp+arg_10]
0x1400122ce  lea     rdx, [rbp+arg_10]; unsigned int *
0x1400122d2  imul    rcx, rax, 3Ch ; '<'; unsigned __int64
0x1400122d6  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1400122db  mov     ebx, eax
0x1400122dd  test    eax, eax
0x1400122df  js      short loc_1400122FC
0x1400122e1  mov     eax, [rbp+arg_10]
0x1400122e4  lea     rdx, [rbp+arg_10]; unsigned int *
0x1400122e8  imul    rcx, rax, 3Ch ; '<'; unsigned __int64
0x1400122ec  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1400122f1  mov     ebx, eax
0x1400122f3  test    eax, eax
0x1400122f5  js      short loc_1400122FC
0x1400122f7  mov     edi, [rbp+arg_10]
0x1400122fa  mov     [rsi], edi
0x1400122fc  mov     rcx, [rbp+hKey]; hKey
0x140012300  mov     [rbp+hKey], 0
0x140012308  test    rcx, rcx
0x14001230b  jz      short loc_140012313
0x14001230d  call    cs:__imp_RegCloseKey
0x140012313  mov     rsi, [rsp+40h+arg_8]
0x140012318  mov     eax, ebx
0x14001231a  mov     rbx, [rsp+40h+arg_0]
0x14001231f  add     rsp, 40h
0x140012323  pop     r14
0x140012325  pop     rdi
0x140012326  pop     rbp
0x140012327  retn
```
