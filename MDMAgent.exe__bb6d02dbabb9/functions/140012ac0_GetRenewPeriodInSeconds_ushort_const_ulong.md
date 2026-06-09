# GetRenewPeriodInSeconds(ushort const *,ulong *)

- ea: `0x140012ac0`
- end: `0x140012bdb`
- name: `?GetRenewPeriodInSeconds@@YAJPEBGPEAK@Z`
- size: `283`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000829c`

## callees

- `0x1400079f8`
- `0x14000b784`
- `0x140012ac0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012bb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012bb9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140012b18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140012b18`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140012b49`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140012b49`

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
0x140012ac0  mov     [rsp-18h+arg_0], rbx
0x140012ac5  mov     [rsp-18h+arg_8], rsi
0x140012aca  push    rbp
0x140012acb  push    rdi
0x140012acc  push    r14
0x140012ace  mov     rbp, rsp
0x140012ad1  sub     rsp, 40h
0x140012ad5  mov     r14, rcx
0x140012ad8  mov     [rbp+arg_18], 0
0x140012adf  mov     edi, 375F00h
0x140012ae4  mov     [rbp+hKey], 0
0x140012aec  mov     ecx, 1
0x140012af1  mov     [rbp+arg_10], edi
0x140012af4  mov     rsi, rdx
0x140012af7  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x140012afc  lea     rcx, [rbp+hKey]
0x140012b00  mov     r9d, 20019h; samDesired
0x140012b06  mov     [rsp+40h+phkResult], rcx; phkResult
0x140012b0b  xor     r8d, r8d; ulOptions
0x140012b0e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140012b15  mov     rdx, rax; lpSubKey
0x140012b18  call    cs:__imp_RegOpenKeyExW
0x140012b1f  nop     dword ptr [rax+rax+00h]
0x140012b24  mov     ebx, eax
0x140012b26  test    eax, eax
0x140012b28  jle     short loc_140012B33
0x140012b2a  movzx   ebx, ax
0x140012b2d  or      ebx, 80070000h
0x140012b33  mov     rcx, [rbp+hKey]
0x140012b37  test    ebx, ebx
0x140012b39  js      short loc_140012BAC
0x140012b3b  lea     r9, [rbp+arg_18]
0x140012b3f  mov     rdx, r14
0x140012b42  lea     r8, aRenewalperiod; "RenewalPeriod"
0x140012b49  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x140012b50  nop     dword ptr [rax+rax+00h]
0x140012b55  test    eax, eax
0x140012b57  jns     short loc_140012B5D
0x140012b59  xor     ebx, ebx
0x140012b5b  jmp     short loc_140012BA6
0x140012b5d  mov     eax, [rbp+arg_18]
0x140012b60  lea     rdx, [rbp+arg_10]; unsigned int *
0x140012b64  lea     rcx, [rax+rax*2]
0x140012b68  shl     rcx, 3; unsigned __int64
0x140012b6c  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x140012b71  mov     ebx, eax
0x140012b73  test    eax, eax
0x140012b75  js      short loc_140012BA8
0x140012b77  mov     eax, [rbp+arg_10]
0x140012b7a  lea     rdx, [rbp+arg_10]; unsigned int *
0x140012b7e  imul    rcx, rax, 3Ch ; '<'; unsigned __int64
0x140012b82  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x140012b87  mov     ebx, eax
0x140012b89  test    eax, eax
0x140012b8b  js      short loc_140012BA8
0x140012b8d  mov     eax, [rbp+arg_10]
0x140012b90  lea     rdx, [rbp+arg_10]; unsigned int *
0x140012b94  imul    rcx, rax, 3Ch ; '<'; unsigned __int64
0x140012b98  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x140012b9d  mov     ebx, eax
0x140012b9f  test    eax, eax
0x140012ba1  js      short loc_140012BA8
0x140012ba3  mov     edi, [rbp+arg_10]
0x140012ba6  mov     [rsi], edi
0x140012ba8  mov     rcx, [rbp+hKey]; hKey
0x140012bac  mov     [rbp+hKey], 0
0x140012bb4  test    rcx, rcx
0x140012bb7  jz      short loc_140012BC5
0x140012bb9  call    cs:__imp_RegCloseKey
0x140012bc0  nop     dword ptr [rax+rax+00h]
0x140012bc5  mov     rsi, [rsp+40h+arg_8]
0x140012bca  mov     eax, ebx
0x140012bcc  mov     rbx, [rsp+40h+arg_0]
0x140012bd1  add     rsp, 40h
0x140012bd5  pop     r14
0x140012bd7  pop     rdi
0x140012bd8  pop     rbp
0x140012bd9  retn
```
