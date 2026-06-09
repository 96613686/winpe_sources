# GetRenewRetryIntervalInSeconds(ushort const *,int,ulong *)

- ea: `0x180093250`
- end: `0x180093390`
- name: `?GetRenewRetryIntervalInSeconds@@YAJPEBGHPEAK@Z`
- size: `320`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180033584`

## callees

- `0x180019ae4`
- `0x18002b664`
- `0x180093250`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18009330c`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18009330c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800932e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180093376`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800932e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180093376`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800932b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800932b6`

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
0x180093250  mov     [rsp-28h+arg_0], rbx
0x180093255  push    rbp
0x180093256  push    rsi
0x180093257  push    rdi
0x180093258  push    r14
0x18009325a  push    r15
0x18009325c  mov     rbp, rsp
0x18009325f  sub     rsp, 40h
0x180093263  mov     rsi, r8
0x180093266  mov     r14d, edx
0x180093269  mov     r15, rcx
0x18009326c  mov     [rbp+arg_18], 0
0x180093273  mov     eax, edx
0x180093275  neg     eax
0x180093277  sbb     edi, edi
0x180093279  and     edi, 0FFF6C580h
0x18009327f  add     edi, 127500h
0x180093285  mov     [rbp+arg_8], edi
0x180093288  mov     [rbp+hKey], 0
0x180093290  mov     ecx, 1
0x180093295  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x18009329a  lea     rcx, [rbp+hKey]
0x18009329e  mov     [rsp+40h+phkResult], rcx; phkResult
0x1800932a3  mov     r9d, 20019h; samDesired
0x1800932a9  xor     r8d, r8d; ulOptions
0x1800932ac  mov     rdx, rax; lpSubKey
0x1800932af  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800932b6  call    cs:__imp_RegOpenKeyExW
0x1800932bc  mov     ebx, eax
0x1800932be  test    eax, eax
0x1800932c0  jle     short loc_1800932CB
0x1800932c2  movzx   ebx, ax
0x1800932c5  or      ebx, 80070000h
0x1800932cb  test    ebx, ebx
0x1800932cd  jns     short loc_1800932EC
0x1800932cf  mov     rcx, [rbp+hKey]; hKey
0x1800932d3  mov     [rbp+hKey], 0
0x1800932db  test    rcx, rcx
0x1800932de  jz      short loc_1800932E7
0x1800932e0  call    cs:__imp_RegCloseKey
0x1800932e6  nop
0x1800932e7  jmp     loc_18009337D
0x1800932ec  lea     rax, aRetryafterexpi; "RetryAfterExpiryInterval"
0x1800932f3  lea     r8, aRetryinterval; "RetryInterval"
0x1800932fa  test    r14d, r14d
0x1800932fd  cmovz   r8, rax
0x180093301  lea     r9, [rbp+arg_18]
0x180093305  mov     rdx, r15
0x180093308  mov     rcx, [rbp+hKey]
0x18009330c  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180093312  test    eax, eax
0x180093314  jns     short loc_18009331A
0x180093316  xor     ebx, ebx
0x180093318  jmp     short loc_180093363
0x18009331a  mov     eax, [rbp+arg_18]
0x18009331d  lea     rcx, [rax+rax*2]
0x180093321  shl     rcx, 3; unsigned __int64
0x180093325  lea     rdx, [rbp+arg_8]; unsigned int *
0x180093329  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18009332e  mov     ebx, eax
0x180093330  test    eax, eax
0x180093332  js      short loc_180093365
0x180093334  mov     eax, [rbp+arg_8]
0x180093337  imul    rcx, rax, 3Ch ; '<'; unsigned __int64
0x18009333b  lea     rdx, [rbp+arg_8]; unsigned int *
0x18009333f  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180093344  mov     ebx, eax
0x180093346  test    eax, eax
0x180093348  js      short loc_180093365
0x18009334a  mov     eax, [rbp+arg_8]
0x18009334d  imul    rcx, rax, 3Ch ; '<'; unsigned __int64
0x180093351  lea     rdx, [rbp+arg_8]; unsigned int *
0x180093355  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18009335a  mov     ebx, eax
0x18009335c  test    eax, eax
0x18009335e  js      short loc_180093365
0x180093360  mov     edi, [rbp+arg_8]
0x180093363  mov     [rsi], edi
0x180093365  mov     rcx, [rbp+hKey]; hKey
0x180093369  mov     [rbp+hKey], 0
0x180093371  test    rcx, rcx
0x180093374  jz      short loc_18009337D
0x180093376  call    cs:__imp_RegCloseKey
0x18009337c  nop
0x18009337d  mov     eax, ebx
0x18009337f  mov     rbx, [rsp+40h+arg_0]
0x180093384  add     rsp, 40h
0x180093388  pop     r15
0x18009338a  pop     r14
0x18009338c  pop     rdi
0x18009338d  pop     rsi
0x18009338e  pop     rbp
0x18009338f  retn
```
