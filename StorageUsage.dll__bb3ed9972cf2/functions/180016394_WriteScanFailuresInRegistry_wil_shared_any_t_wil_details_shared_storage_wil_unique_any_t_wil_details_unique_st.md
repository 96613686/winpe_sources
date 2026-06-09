# WriteScanFailuresInRegistry(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>> &,ushort const *,ulong)

- ea: `0x180016394`
- end: `0x180016473`
- name: `?WriteScanFailuresInRegistry@@YAJAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@PEBGK@Z`
- size: `223`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180012340`

## callees

- `0x1800050f0`
- `0x180005c94`
- `0x180012230`
- `0x1800152d4`
- `0x180016394`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016430`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016430`

## pseudocode

```c
__int64 __fastcall WriteScanFailuresInRegistry(HKEY **a1, __int64 a2, int a3)
{
  const unsigned __int16 *v4; // rcx
  unsigned __int64 v5; // r9
  signed int RegValueName; // ebx
  __int64 v7; // rdx
  HKEY v9; // rcx
  LSTATUS v10; // eax
  BYTE Data[16]; // [rsp+30h] [rbp-238h] BYREF
  WCHAR ValueName[264]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  *(_DWORD *)Data = a3;
  memset_0(ValueName, 0, 0x208u);
  RegValueName = GetRegValueName(v4, L"FailureCount", ValueName, v5);
  if ( RegValueName < 0 )
  {
    v7 = 1155;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelertelemetry.cpp",
      (const char *)(unsigned int)RegValueName);
    return (unsigned int)RegValueName;
  }
  if ( *a1 )
    v9 = **a1;
  else
    v9 = 0;
  v10 = RegSetValueExW(v9, ValueName, 0, 4u, Data, 4u);
  RegValueName = v10;
  if ( v10 > 0 )
    RegValueName = (unsigned __int16)v10 | 0x80070000;
  if ( RegValueName < 0 )
  {
    v7 = 1162;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180016394  mov     [rsp+arg_8], rbx
0x180016399  push    rdi
0x18001639a  sub     rsp, 260h
0x1800163a1  mov     rax, cs:__security_cookie
0x1800163a8  xor     rax, rsp
0x1800163ab  mov     [rsp+268h+var_18], rax
0x1800163b3  mov     rdi, rcx
0x1800163b6  mov     dword ptr [rsp+268h+Data], r8d
0x1800163bb  mov     r8d, 208h; Size
0x1800163c1  lea     rcx, [rsp+268h+ValueName]; void *
0x1800163c6  xor     edx, edx; Val
0x1800163c8  call    memset_0
0x1800163cd  lea     r8, [rsp+268h+ValueName]; unsigned __int16 *
0x1800163d2  lea     rdx, aFailurecount; "FailureCount"
0x1800163d9  call    ?GetRegValueName@@YAJPEBG0PEAG_K@Z; GetRegValueName(ushort const *,ushort const *,ushort *,unsigned __int64)
0x1800163de  mov     ebx, eax
0x1800163e0  test    eax, eax
0x1800163e2  jns     short loc_180016404
0x1800163e4  mov     edx, 483h; void *
0x1800163e9  mov     rcx, [rsp+268h]; this
0x1800163f1  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800163f8  mov     r9d, ebx; char *
0x1800163fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016400  mov     eax, ebx
0x180016402  jmp     short loc_180016452
0x180016404  mov     rax, [rdi]
0x180016407  test    rax, rax
0x18001640a  jz      short loc_180016411
0x18001640c  mov     rcx, [rax]
0x18001640f  jmp     short loc_180016413
0x180016411  xor     ecx, ecx; hKey
0x180016413  mov     r9d, 4; dwType
0x180016419  lea     rax, [rsp+268h+Data]
0x18001641e  mov     [rsp+268h+cbData], r9d; cbData
0x180016423  lea     rdx, [rsp+268h+ValueName]; lpValueName
0x180016428  xor     r8d, r8d; Reserved
0x18001642b  mov     [rsp+268h+lpData], rax; lpData
0x180016430  call    cs:__imp_RegSetValueExW
0x180016436  mov     ebx, eax
0x180016438  test    eax, eax
0x18001643a  jle     short loc_180016445
0x18001643c  movzx   ebx, ax
0x18001643f  or      ebx, 80070000h
0x180016445  test    ebx, ebx
0x180016447  jns     short loc_180016450
0x180016449  mov     edx, 48Ah
0x18001644e  jmp     short loc_1800163E9
0x180016450  xor     eax, eax
0x180016452  mov     rcx, [rsp+268h+var_18]
0x18001645a  xor     rcx, rsp; StackCookie
0x18001645d  call    __security_check_cookie
0x180016462  mov     rbx, [rsp+268h+arg_8]
0x18001646a  add     rsp, 260h
0x180016471  pop     rdi
0x180016472  retn
```
