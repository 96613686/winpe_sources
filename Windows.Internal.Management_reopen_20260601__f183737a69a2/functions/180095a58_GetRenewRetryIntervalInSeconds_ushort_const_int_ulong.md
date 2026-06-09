# GetRenewRetryIntervalInSeconds(ushort const *,int,ulong *)

- ea: `0x180095a58`
- end: `0x180095bb1`
- name: `?GetRenewRetryIntervalInSeconds@@YAJPEBGHPEAK@Z`
- size: `345`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800323e8`

## callees

- `0x1800184c0`
- `0x18002a028`
- `0x180095a58`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x180095b20`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x180095b20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095aee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095b90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095aee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095b90`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180095abe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180095abe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetRenewRetryIntervalInSeconds(const unsigned __int16 *a1, int a2, unsigned int *a3)
{
  int v6; // edi
  const WCHAR *v7; // rax
  LSTATUS v8; // eax
  signed int v9; // ebx
  HKEY v10; // rcx
  const unsigned __int16 *v11; // r8
  HKEY v12; // rcx
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v15; // [rsp+78h] [rbp+38h] BYREF
  unsigned int v16; // [rsp+88h] [rbp+48h] BYREF

  v16 = 0;
  v6 = a2 != 0 ? 604800 : 1209600;
  v15 = v6;
  hKey = 0;
  v7 = (const WCHAR *)DMGetKnownRegPath(1);
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0x20019u, &hKey);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v9 < 0 )
  {
    v10 = hKey;
    hKey = 0;
    if ( v10 )
      RegCloseKey(v10);
    return (unsigned int)v9;
  }
  v11 = L"RetryInterval";
  if ( !a2 )
    v11 = L"RetryAfterExpiryInterval";
  if ( (int)OmaDmRegistryGetDWORD(hKey, a1, v11, &v16) < 0 )
  {
    v9 = 0;
LABEL_15:
    *a3 = v6;
    goto LABEL_16;
  }
  v9 = ULongLongToULong(24LL * v16, &v15);
  if ( v9 >= 0 )
  {
    v9 = ULongLongToULong(60LL * v15, &v15);
    if ( v9 >= 0 )
    {
      v9 = ULongLongToULong(60LL * v15, &v15);
      if ( v9 >= 0 )
      {
        v6 = v15;
        goto LABEL_15;
      }
    }
  }
LABEL_16:
  v12 = hKey;
  hKey = 0;
  if ( v12 )
    RegCloseKey(v12);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180095a58  mov     [rsp-28h+arg_0], rbx
0x180095a5d  push    rbp
0x180095a5e  push    rsi
0x180095a5f  push    rdi
0x180095a60  push    r14
0x180095a62  push    r15
0x180095a64  mov     rbp, rsp
0x180095a67  sub     rsp, 40h
0x180095a6b  mov     rsi, r8
0x180095a6e  mov     r14d, edx
0x180095a71  mov     r15, rcx
0x180095a74  mov     [rbp+arg_18], 0
0x180095a7b  mov     eax, edx
0x180095a7d  neg     eax
0x180095a7f  sbb     edi, edi
0x180095a81  and     edi, 0FFF6C580h
0x180095a87  add     edi, 127500h
0x180095a8d  mov     [rbp+arg_8], edi
0x180095a90  mov     [rbp+hKey], 0
0x180095a98  mov     ecx, 1
0x180095a9d  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x180095aa2  lea     rcx, [rbp+hKey]
0x180095aa6  mov     [rsp+40h+phkResult], rcx; phkResult
0x180095aab  mov     r9d, 20019h; samDesired
0x180095ab1  xor     r8d, r8d; ulOptions
0x180095ab4  mov     rdx, rax; lpSubKey
0x180095ab7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180095abe  call    cs:__imp_RegOpenKeyExW
0x180095ac5  nop     dword ptr [rax+rax+00h]
0x180095aca  mov     ebx, eax
0x180095acc  test    eax, eax
0x180095ace  jle     short loc_180095AD9
0x180095ad0  movzx   ebx, ax
0x180095ad3  or      ebx, 80070000h
0x180095ad9  test    ebx, ebx
0x180095adb  jns     short loc_180095B00
0x180095add  mov     rcx, [rbp+hKey]; hKey
0x180095ae1  mov     [rbp+hKey], 0
0x180095ae9  test    rcx, rcx
0x180095aec  jz      short loc_180095AFB
0x180095aee  call    cs:__imp_RegCloseKey
0x180095af5  nop     dword ptr [rax+rax+00h]
0x180095afa  nop
0x180095afb  jmp     loc_180095B9D
0x180095b00  lea     rax, aRetryafterexpi; "RetryAfterExpiryInterval"
0x180095b07  lea     r8, aRetryinterval; "RetryInterval"
0x180095b0e  test    r14d, r14d
0x180095b11  cmovz   r8, rax
0x180095b15  lea     r9, [rbp+arg_18]
0x180095b19  mov     rdx, r15
0x180095b1c  mov     rcx, [rbp+hKey]
0x180095b20  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180095b27  nop     dword ptr [rax+rax+00h]
0x180095b2c  test    eax, eax
0x180095b2e  jns     short loc_180095B34
0x180095b30  xor     ebx, ebx
0x180095b32  jmp     short loc_180095B7D
0x180095b34  mov     eax, [rbp+arg_18]
0x180095b37  lea     rcx, [rax+rax*2]
0x180095b3b  shl     rcx, 3; unsigned __int64
0x180095b3f  lea     rdx, [rbp+arg_8]; unsigned int *
0x180095b43  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180095b48  mov     ebx, eax
0x180095b4a  test    eax, eax
0x180095b4c  js      short loc_180095B7F
0x180095b4e  mov     eax, [rbp+arg_8]
0x180095b51  imul    rcx, rax, 3Ch ; '<'; unsigned __int64
0x180095b55  lea     rdx, [rbp+arg_8]; unsigned int *
0x180095b59  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180095b5e  mov     ebx, eax
0x180095b60  test    eax, eax
0x180095b62  js      short loc_180095B7F
0x180095b64  mov     eax, [rbp+arg_8]
0x180095b67  imul    rcx, rax, 3Ch ; '<'; unsigned __int64
0x180095b6b  lea     rdx, [rbp+arg_8]; unsigned int *
0x180095b6f  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180095b74  mov     ebx, eax
0x180095b76  test    eax, eax
0x180095b78  js      short loc_180095B7F
0x180095b7a  mov     edi, [rbp+arg_8]
0x180095b7d  mov     [rsi], edi
0x180095b7f  mov     rcx, [rbp+hKey]; hKey
0x180095b83  mov     [rbp+hKey], 0
0x180095b8b  test    rcx, rcx
0x180095b8e  jz      short loc_180095B9D
0x180095b90  call    cs:__imp_RegCloseKey
0x180095b97  nop     dword ptr [rax+rax+00h]
0x180095b9c  nop
0x180095b9d  mov     eax, ebx
0x180095b9f  mov     rbx, [rsp+40h+arg_0]
0x180095ba4  add     rsp, 40h
0x180095ba8  pop     r15
0x180095baa  pop     r14
0x180095bac  pop     rdi
0x180095bad  pop     rsi
0x180095bae  pop     rbp
0x180095baf  retn
```
