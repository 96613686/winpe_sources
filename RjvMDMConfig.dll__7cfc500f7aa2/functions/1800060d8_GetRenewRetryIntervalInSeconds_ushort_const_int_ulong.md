# GetRenewRetryIntervalInSeconds(ushort const *,int,ulong *)

- ea: `0x1800060d8`
- end: `0x180006206`
- name: `?GetRenewRetryIntervalInSeconds@@YAJPEBGHPEAK@Z`
- size: `302`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004168`

## callees

- `0x180005a38`
- `0x1800060d8`
- `0x180006574`
- `0x180017278`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000613e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000613e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800061e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800061e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetRenewRetryIntervalInSeconds(const unsigned __int16 *a1, int a2, unsigned int *a3)
{
  int v6; // edi
  const WCHAR *v7; // rax
  LSTATUS v8; // eax
  signed int v9; // ebx
  const unsigned __int16 *v10; // r8
  HKEY v11; // rcx
  bool v12; // zf
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
  if ( v9 >= 0 )
  {
    v10 = L"RetryInterval";
    if ( !a2 )
      v10 = L"RetryAfterExpiryInterval";
    if ( (int)OmaDmRegistryGetDWORD(hKey, a1, v10, &v16) < 0 )
    {
      v9 = 0;
LABEL_12:
      *a3 = v6;
      goto LABEL_13;
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
          goto LABEL_12;
        }
      }
    }
  }
LABEL_13:
  v11 = hKey;
  v12 = hKey == 0;
  hKey = 0;
  if ( !v12 )
    RegCloseKey(v11);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800060d8  mov     [rsp-28h+arg_0], rbx
0x1800060dd  push    rbp
0x1800060de  push    rsi
0x1800060df  push    rdi
0x1800060e0  push    r14
0x1800060e2  push    r15
0x1800060e4  mov     rbp, rsp
0x1800060e7  sub     rsp, 40h
0x1800060eb  mov     rsi, r8
0x1800060ee  mov     r14d, edx
0x1800060f1  mov     r15, rcx
0x1800060f4  mov     [rbp+arg_18], 0
0x1800060fb  mov     eax, edx
0x1800060fd  neg     eax
0x1800060ff  sbb     edi, edi
0x180006101  and     edi, 0FFF6C580h
0x180006107  add     edi, 127500h
0x18000610d  mov     [rbp+arg_8], edi
0x180006110  mov     [rbp+hKey], 0
0x180006118  mov     ecx, 1
0x18000611d  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x180006122  lea     rcx, [rbp+hKey]
0x180006126  mov     [rsp+40h+phkResult], rcx; phkResult
0x18000612b  mov     r9d, 20019h; samDesired
0x180006131  xor     r8d, r8d; ulOptions
0x180006134  mov     rdx, rax; lpSubKey
0x180006137  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000613e  call    cs:__imp_RegOpenKeyExW
0x180006145  nop     dword ptr [rax+rax+00h]
0x18000614a  mov     ebx, eax
0x18000614c  test    eax, eax
0x18000614e  jle     short loc_180006159
0x180006150  movzx   ebx, ax
0x180006153  or      ebx, 80070000h
0x180006159  test    ebx, ebx
0x18000615b  js      short loc_1800061D5
0x18000615d  lea     rax, aRetryafterexpi; "RetryAfterExpiryInterval"
0x180006164  lea     r8, aRetryinterval; "RetryInterval"
0x18000616b  test    r14d, r14d
0x18000616e  cmovz   r8, rax; unsigned __int16 *
0x180006172  lea     r9, [rbp+arg_18]; unsigned int *
0x180006176  mov     rdx, r15; unsigned __int16 *
0x180006179  mov     rcx, [rbp+hKey]; HKEY
0x18000617d  call    ?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180006182  test    eax, eax
0x180006184  jns     short loc_18000618A
0x180006186  xor     ebx, ebx
0x180006188  jmp     short loc_1800061D3
0x18000618a  mov     eax, [rbp+arg_18]
0x18000618d  lea     rcx, [rax+rax*2]
0x180006191  shl     rcx, 3; unsigned __int64
0x180006195  lea     rdx, [rbp+arg_8]; unsigned int *
0x180006199  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000619e  mov     ebx, eax
0x1800061a0  test    eax, eax
0x1800061a2  js      short loc_1800061D5
0x1800061a4  mov     eax, [rbp+arg_8]
0x1800061a7  imul    rcx, rax, 3Ch ; '<'; unsigned __int64
0x1800061ab  lea     rdx, [rbp+arg_8]; unsigned int *
0x1800061af  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800061b4  mov     ebx, eax
0x1800061b6  test    eax, eax
0x1800061b8  js      short loc_1800061D5
0x1800061ba  mov     eax, [rbp+arg_8]
0x1800061bd  imul    rcx, rax, 3Ch ; '<'; unsigned __int64
0x1800061c1  lea     rdx, [rbp+arg_8]; unsigned int *
0x1800061c5  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800061ca  mov     ebx, eax
0x1800061cc  test    eax, eax
0x1800061ce  js      short loc_1800061D5
0x1800061d0  mov     edi, [rbp+arg_8]
0x1800061d3  mov     [rsi], edi
0x1800061d5  mov     rcx, [rbp+hKey]; hKey
0x1800061d9  test    rcx, rcx
0x1800061dc  mov     [rbp+hKey], 0
0x1800061e4  jz      short loc_1800061F2
0x1800061e6  call    cs:__imp_RegCloseKey
0x1800061ed  nop     dword ptr [rax+rax+00h]
0x1800061f2  mov     eax, ebx
0x1800061f4  mov     rbx, [rsp+40h+arg_0]
0x1800061f9  add     rsp, 40h
0x1800061fd  pop     r15
0x1800061ff  pop     r14
0x180006201  pop     rdi
0x180006202  pop     rsi
0x180006203  pop     rbp
0x180006204  retn
```
