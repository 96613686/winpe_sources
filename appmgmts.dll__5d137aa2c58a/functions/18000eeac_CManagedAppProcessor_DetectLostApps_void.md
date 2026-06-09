# CManagedAppProcessor::DetectLostApps(void)

- ea: `0x18000eeac`
- end: `0x18000f01e`
- name: `?DetectLostApps@CManagedAppProcessor@@AEAAHXZ`
- size: `370`
- prototype: `__int64 __fastcall(CManagedAppProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000df00`

## callees

- `0x1800016d0`
- `0x18000eeac`
- `0x180012fbc`
- `0x18001b1a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ef63`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ef63`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ef9a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ef9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000efa4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000efa4`

## pseudocode

```c
__int64 __fastcall CManagedAppProcessor::DetectLostApps(CManagedAppProcessor *this)
{
  bool v1; // zf
  char *v3; // rdi
  __int64 i; // rcx
  BYTE Data[4]; // [rsp+30h] [rbp-19h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-15h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-11h] BYREF
  WCHAR SubKey[40]; // [rsp+40h] [rbp-9h] BYREF

  v1 = *((_DWORD *)this + 99) == 1;
  hKey = 0;
  cbData = 0;
  *(_DWORD *)Data = 0;
  if ( !v1 && *((_DWORD *)this + 74) )
  {
    v3 = (char *)this + 184;
    *((_QWORD *)this + 26) = *((_QWORD *)this + 25);
    for ( i = *((_QWORD *)this + 24); ; i = *(_QWORD *)(*((_QWORD *)this + 25) + 8LL) )
    {
      *((_QWORD *)this + 25) = i;
      if ( (char *)i == v3 )
        i = 0;
      if ( !i )
        break;
      GuidToString((struct _GUID *)(i + 24), SubKey);
      if ( RegOpenKeyExW(*((HKEY *)this + 36), SubKey, 0, 0x20019u, &hKey) )
      {
        *((_QWORD *)this + 25) = *((_QWORD *)this + 26);
        if ( *(_DWORD *)&gDebugLevel )
          _DebugMsg(4, 0xC33u);
        return 1;
      }
      *(_DWORD *)Data = 0;
      cbData = 4;
      RegQueryValueExW(hKey, L"AppState", 0, 0, Data, &cbData);
      RegCloseKey(hKey);
      if ( (Data[0] & 3) == 0 )
        return 1;
    }
    *((_QWORD *)this + 25) = *((_QWORD *)this + 26);
  }
  return 0;
}

```

## disassembly

```asm
0x18000eeac  mov     [rsp-8+arg_8], rbx
0x18000eeb1  mov     [rsp-8+arg_10], rdi
0x18000eeb6  push    rbp
0x18000eeb7  lea     rbp, [rsp-57h]
0x18000eebc  sub     rsp, 0A0h
0x18000eec3  mov     rax, cs:__security_cookie
0x18000eeca  xor     rax, rsp
0x18000eecd  mov     [rbp+57h+var_10], rax
0x18000eed1  cmp     dword ptr [rcx+18Ch], 1
0x18000eed8  mov     rbx, rcx
0x18000eedb  mov     [rbp+57h+hKey], 0
0x18000eee3  mov     [rbp+57h+cbData], 0
0x18000eeea  mov     dword ptr [rbp+57h+Data], 0
0x18000eef1  jz      loc_18000EFFB
0x18000eef7  cmp     dword ptr [rcx+128h], 0
0x18000eefe  jz      loc_18000EFFB
0x18000ef04  mov     rax, [rcx+0C8h]
0x18000ef0b  lea     rdi, [rbx+0B8h]
0x18000ef12  mov     [rcx+0D0h], rax
0x18000ef19  mov     rcx, [rcx+0C0h]
0x18000ef20  xor     eax, eax
0x18000ef22  mov     [rbx+0C8h], rcx
0x18000ef29  cmp     rcx, rdi
0x18000ef2c  cmovz   rcx, rax
0x18000ef30  test    rcx, rcx
0x18000ef33  jz      loc_18000EFED
0x18000ef39  add     rcx, 18h; struct _GUID *
0x18000ef3d  lea     rdx, [rbp+57h+SubKey]; unsigned __int16 *
0x18000ef41  call    ?GuidToString@@YAXAEAU_GUID@@PEAG@Z; GuidToString(_GUID &,ushort *)
0x18000ef46  mov     rcx, [rbx+120h]; hKey
0x18000ef4d  lea     rax, [rbp+57h+hKey]
0x18000ef51  mov     r9d, 20019h; samDesired
0x18000ef57  mov     [rsp+0A0h+phkResult], rax; phkResult
0x18000ef5c  xor     r8d, r8d; ulOptions
0x18000ef5f  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x18000ef63  call    cs:__imp_RegOpenKeyExW
0x18000ef69  test    eax, eax
0x18000ef6b  jnz     short loc_18000EFC0
0x18000ef6d  mov     rcx, [rbp+57h+hKey]; hKey
0x18000ef71  lea     rdx, aAppstate; "AppState"
0x18000ef78  mov     dword ptr [rbp+57h+Data], eax
0x18000ef7b  xor     r9d, r9d; lpType
0x18000ef7e  lea     rax, [rbp+57h+cbData]
0x18000ef82  mov     [rbp+57h+cbData], 4
0x18000ef89  mov     [rsp+0A0h+lpcbData], rax; lpcbData
0x18000ef8e  xor     r8d, r8d; lpReserved
0x18000ef91  lea     rax, [rbp+57h+Data]
0x18000ef95  mov     [rsp+0A0h+phkResult], rax; lpData
0x18000ef9a  call    cs:__imp_RegQueryValueExW
0x18000efa0  mov     rcx, [rbp+57h+hKey]; hKey
0x18000efa4  call    cs:__imp_RegCloseKey
0x18000efaa  test    [rbp+57h+Data], 3
0x18000efae  jz      short loc_18000EFE6
0x18000efb0  mov     rax, [rbx+0C8h]
0x18000efb7  mov     rcx, [rax+8]
0x18000efbb  jmp     loc_18000EF20
0x18000efc0  mov     rdx, [rbx+0D0h]
0x18000efc7  mov     [rbx+0C8h], rdx
0x18000efce  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x18000efd5  jz      short loc_18000EFE6
0x18000efd7  mov     edx, 0C33h; unsigned int
0x18000efdc  mov     ecx, 4; unsigned int
0x18000efe1  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000efe6  mov     eax, 1
0x18000efeb  jmp     short loc_18000EFFD
0x18000efed  mov     rax, [rbx+0D0h]
0x18000eff4  mov     [rbx+0C8h], rax
0x18000effb  xor     eax, eax
0x18000effd  mov     rcx, [rbp+57h+var_10]
0x18000f001  xor     rcx, rsp; StackCookie
0x18000f004  call    __security_check_cookie
0x18000f009  lea     r11, [rsp+0A0h+var_s0]
0x18000f011  mov     rbx, [r11+18h]
0x18000f015  mov     rdi, [r11+20h]
0x18000f019  mov     rsp, r11
0x18000f01c  pop     rbp
0x18000f01d  retn
```
