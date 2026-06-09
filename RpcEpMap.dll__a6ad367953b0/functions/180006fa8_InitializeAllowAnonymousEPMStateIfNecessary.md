# InitializeAllowAnonymousEPMStateIfNecessary

- ea: `0x180006fa8`
- end: `0x18000708e`
- name: `InitializeAllowAnonymousEPMStateIfNecessary`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004f50`

## callees

- `0x180006fa8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180007041`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180007041`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000704e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000704e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006ff3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006ff3`

## string_xrefs

- `0x180007017`: `AllowAnonymousAccessToEPM`

## pseudocode

```c
__int64 InitializeAllowAnonymousEPMStateIfNecessary()
{
  LSTATUS v0; // eax
  signed __int32 v1; // ecx
  LSTATUS ValueW; // ebx
  DWORD pcbData; // [rsp+50h] [rbp+8h] BYREF
  int pvData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hkey; // [rsp+60h] [rbp+18h] BYREF

  hkey = 0;
  pcbData = 0;
  pvData = 0;
  if ( EPMAllowAnonymous != 1 )
    return 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\Windows NT\\Rpc", 0, 0x20019u, &hkey);
  if ( v0 )
  {
    v1 = 2;
    if ( v0 == 2 )
      goto LABEL_9;
    return 14;
  }
  pcbData = 4;
  ValueW = RegGetValueW(hkey, 0, L"AllowAnonymousAccessToEPM", 0x18u, 0, &pvData, &pcbData);
  RegCloseKey(hkey);
  if ( ValueW )
  {
    v1 = 2;
    if ( ValueW != 2 )
      return 14;
  }
  else
  {
    v1 = (pvData != 0) + 2;
  }
LABEL_9:
  _InterlockedCompareExchange(&EPMAllowAnonymous, v1, 1);
  return 0;
}

```

## disassembly

```asm
0x180006fa8  mov     rax, rsp
0x180006fab  push    rbx
0x180006fac  sub     rsp, 40h
0x180006fb0  cmp     cs:EPMAllowAnonymous, 1
0x180006fb7  mov     qword ptr [rax+18h], 0
0x180006fbf  mov     dword ptr [rax+8], 0
0x180006fc6  mov     dword ptr [rax+10h], 0
0x180006fcd  jnz     loc_180007086
0x180006fd3  lea     rax, [rax+18h]
0x180006fd7  mov     r9d, 20019h; samDesired
0x180006fdd  xor     r8d, r8d; ulOptions
0x180006fe0  mov     [rsp+48h+phkResult], rax; phkResult
0x180006fe5  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x180006fec  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006ff3  call    cs:__imp_RegOpenKeyExW
0x180006ff9  test    eax, eax
0x180006ffb  jz      short loc_180007008
0x180006ffd  mov     ecx, 2
0x180007002  cmp     eax, ecx
0x180007004  jnz     short loc_180007061
0x180007006  jmp     short loc_180007079
0x180007008  mov     rcx, [rsp+48h+hkey]; hkey
0x18000700d  lea     rax, [rsp+48h+arg_0]
0x180007012  mov     [rsp+48h+pcbData], rax; pcbData
0x180007017  lea     r8, Value; "AllowAnonymousAccessToEPM"
0x18000701e  lea     rax, [rsp+48h+arg_8]
0x180007023  mov     [rsp+48h+arg_0], 4
0x18000702b  mov     [rsp+48h+pvData], rax; pvData
0x180007030  mov     r9d, 18h; dwFlags
0x180007036  xor     edx, edx; lpSubKey
0x180007038  mov     [rsp+48h+phkResult], 0; pdwType
0x180007041  call    cs:__imp_RegGetValueW
0x180007047  mov     rcx, [rsp+48h+hkey]; hKey
0x18000704c  mov     ebx, eax
0x18000704e  call    cs:__imp_RegCloseKey
0x180007054  test    ebx, ebx
0x180007056  jz      short loc_180007068
0x180007058  mov     ecx, 2
0x18000705d  cmp     ebx, ecx
0x18000705f  jz      short loc_180007079
0x180007061  mov     eax, 0Eh
0x180007066  jmp     short loc_180007088
0x180007068  mov     ecx, [rsp+48h+arg_8]
0x18000706c  neg     ecx
0x18000706e  mov     ecx, 2
0x180007073  sbb     edx, edx
0x180007075  neg     edx
0x180007077  add     ecx, edx
0x180007079  mov     eax, 1
0x18000707e  lock cmpxchg cs:EPMAllowAnonymous, ecx
0x180007086  xor     eax, eax
0x180007088  add     rsp, 40h
0x18000708c  pop     rbx
0x18000708d  retn
```
