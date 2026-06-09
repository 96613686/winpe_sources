# GetRenewRetryIntervalInSeconds(ushort const *,int,ulong *)

- ea: `0x140012be4`
- end: `0x140012d19`
- name: `?GetRenewRetryIntervalInSeconds@@YAJPEBGHPEAK@Z`
- size: `309`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000829c`

## callees

- `0x1400079f8`
- `0x14000b784`
- `0x140012be4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012cf9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012cf9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140012c4a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140012c4a`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140012c89`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140012c89`

## pseudocode

```c
__int64 __fastcall GetRenewRetryIntervalInSeconds(const unsigned __int16 *a1, int a2, unsigned int *a3)
{
  int v6; // edi
  const WCHAR *v7; // rax
  LSTATUS v8; // eax
  signed int v9; // ebx
  HKEY v10; // rcx
  const unsigned __int16 *v11; // r8
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v14; // [rsp+78h] [rbp+38h] BYREF
  unsigned int v15; // [rsp+88h] [rbp+48h] BYREF

  v15 = 0;
  hKey = 0;
  v6 = a2 != 0 ? 604800 : 1209600;
  v14 = v6;
  v7 = (const WCHAR *)DMGetKnownRegPath(1);
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0x20019u, &hKey);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  v10 = hKey;
  if ( v9 >= 0 )
  {
    v11 = L"RetryInterval";
    if ( !a2 )
      v11 = L"RetryAfterExpiryInterval";
    if ( (int)OmaDmRegistryGetDWORD(hKey, a1, v11, &v15) >= 0 )
    {
      v9 = ULongLongToULong(24LL * v15, &v14);
      if ( v9 < 0 )
        goto LABEL_13;
      v9 = ULongLongToULong(60LL * v14, &v14);
      if ( v9 < 0 )
        goto LABEL_13;
      v9 = ULongLongToULong(60LL * v14, &v14);
      if ( v9 < 0 )
        goto LABEL_13;
      v6 = v14;
    }
    else
    {
      v9 = 0;
    }
    *a3 = v6;
LABEL_13:
    v10 = hKey;
  }
  hKey = 0;
  if ( v10 )
    RegCloseKey(v10);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140012be4  mov     [rsp-28h+arg_0], rbx
0x140012be9  push    rbp
0x140012bea  push    rsi
0x140012beb  push    rdi
0x140012bec  push    r14
0x140012bee  push    r15
0x140012bf0  mov     rbp, rsp
0x140012bf3  sub     rsp, 40h
0x140012bf7  mov     eax, edx
0x140012bf9  mov     [rbp+arg_18], 0
0x140012c00  neg     eax
0x140012c02  mov     [rbp+hKey], 0
0x140012c0a  mov     r15, rcx
0x140012c0d  mov     rsi, r8
0x140012c10  sbb     edi, edi
0x140012c12  mov     ecx, 1
0x140012c17  and     edi, 0FFF6C580h
0x140012c1d  mov     r14d, edx
0x140012c20  add     edi, 127500h
0x140012c26  mov     [rbp+arg_8], edi
0x140012c29  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x140012c2e  lea     rcx, [rbp+hKey]
0x140012c32  mov     r9d, 20019h; samDesired
0x140012c38  mov     [rsp+40h+phkResult], rcx; phkResult
0x140012c3d  xor     r8d, r8d; ulOptions
0x140012c40  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140012c47  mov     rdx, rax; lpSubKey
0x140012c4a  call    cs:__imp_RegOpenKeyExW
0x140012c51  nop     dword ptr [rax+rax+00h]
0x140012c56  mov     ebx, eax
0x140012c58  test    eax, eax
0x140012c5a  jle     short loc_140012C65
0x140012c5c  movzx   ebx, ax
0x140012c5f  or      ebx, 80070000h
0x140012c65  mov     rcx, [rbp+hKey]
0x140012c69  test    ebx, ebx
0x140012c6b  js      short loc_140012CEC
0x140012c6d  lea     rax, aRetryafterexpi; "RetryAfterExpiryInterval"
0x140012c74  test    r14d, r14d
0x140012c77  lea     r8, aRetryinterval; "RetryInterval"
0x140012c7e  mov     rdx, r15
0x140012c81  cmovz   r8, rax
0x140012c85  lea     r9, [rbp+arg_18]
0x140012c89  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x140012c90  nop     dword ptr [rax+rax+00h]
0x140012c95  test    eax, eax
0x140012c97  jns     short loc_140012C9D
0x140012c99  xor     ebx, ebx
0x140012c9b  jmp     short loc_140012CE6
0x140012c9d  mov     eax, [rbp+arg_18]
0x140012ca0  lea     rdx, [rbp+arg_8]; unsigned int *
0x140012ca4  lea     rcx, [rax+rax*2]
0x140012ca8  shl     rcx, 3; unsigned __int64
0x140012cac  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x140012cb1  mov     ebx, eax
0x140012cb3  test    eax, eax
0x140012cb5  js      short loc_140012CE8
0x140012cb7  mov     eax, [rbp+arg_8]
0x140012cba  lea     rdx, [rbp+arg_8]; unsigned int *
0x140012cbe  imul    rcx, rax, 3Ch ; '<'; unsigned __int64
0x140012cc2  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x140012cc7  mov     ebx, eax
0x140012cc9  test    eax, eax
0x140012ccb  js      short loc_140012CE8
0x140012ccd  mov     eax, [rbp+arg_8]
0x140012cd0  lea     rdx, [rbp+arg_8]; unsigned int *
0x140012cd4  imul    rcx, rax, 3Ch ; '<'; unsigned __int64
0x140012cd8  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x140012cdd  mov     ebx, eax
0x140012cdf  test    eax, eax
0x140012ce1  js      short loc_140012CE8
0x140012ce3  mov     edi, [rbp+arg_8]
0x140012ce6  mov     [rsi], edi
0x140012ce8  mov     rcx, [rbp+hKey]; hKey
0x140012cec  mov     [rbp+hKey], 0
0x140012cf4  test    rcx, rcx
0x140012cf7  jz      short loc_140012D05
0x140012cf9  call    cs:__imp_RegCloseKey
0x140012d00  nop     dword ptr [rax+rax+00h]
0x140012d05  mov     eax, ebx
0x140012d07  mov     rbx, [rsp+40h+arg_0]
0x140012d0c  add     rsp, 40h
0x140012d10  pop     r15
0x140012d12  pop     r14
0x140012d14  pop     rdi
0x140012d15  pop     rsi
0x140012d16  pop     rbp
0x140012d17  retn
```
