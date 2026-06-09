# WriteScanLevelInRegistry(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>> &,ushort const *,ulong)

- ea: `0x18001647c`
- end: `0x18001655b`
- name: `?WriteScanLevelInRegistry@@YAJAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@PEBGK@Z`
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
- `0x18001647c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016518`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016518`

## pseudocode

```c
__int64 __fastcall WriteScanLevelInRegistry(HKEY **a1, __int64 a2, int a3)
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
  RegValueName = GetRegValueName(v4, L"ScanLevel", ValueName, v5);
  if ( RegValueName < 0 )
  {
    v7 = 1214;
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
    v7 = 1221;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x18001647c  mov     [rsp+arg_8], rbx
0x180016481  push    rdi
0x180016482  sub     rsp, 260h
0x180016489  mov     rax, cs:__security_cookie
0x180016490  xor     rax, rsp
0x180016493  mov     [rsp+268h+var_18], rax
0x18001649b  mov     rdi, rcx
0x18001649e  mov     dword ptr [rsp+268h+Data], r8d
0x1800164a3  mov     r8d, 208h; Size
0x1800164a9  lea     rcx, [rsp+268h+ValueName]; void *
0x1800164ae  xor     edx, edx; Val
0x1800164b0  call    memset_0
0x1800164b5  lea     r8, [rsp+268h+ValueName]; unsigned __int16 *
0x1800164ba  lea     rdx, aScanlevel; "ScanLevel"
0x1800164c1  call    ?GetRegValueName@@YAJPEBG0PEAG_K@Z; GetRegValueName(ushort const *,ushort const *,ushort *,unsigned __int64)
0x1800164c6  mov     ebx, eax
0x1800164c8  test    eax, eax
0x1800164ca  jns     short loc_1800164EC
0x1800164cc  mov     edx, 4BEh; void *
0x1800164d1  mov     rcx, [rsp+268h]; this
0x1800164d9  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800164e0  mov     r9d, ebx; char *
0x1800164e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800164e8  mov     eax, ebx
0x1800164ea  jmp     short loc_18001653A
0x1800164ec  mov     rax, [rdi]
0x1800164ef  test    rax, rax
0x1800164f2  jz      short loc_1800164F9
0x1800164f4  mov     rcx, [rax]
0x1800164f7  jmp     short loc_1800164FB
0x1800164f9  xor     ecx, ecx; hKey
0x1800164fb  mov     r9d, 4; dwType
0x180016501  lea     rax, [rsp+268h+Data]
0x180016506  mov     [rsp+268h+cbData], r9d; cbData
0x18001650b  lea     rdx, [rsp+268h+ValueName]; lpValueName
0x180016510  xor     r8d, r8d; Reserved
0x180016513  mov     [rsp+268h+lpData], rax; lpData
0x180016518  call    cs:__imp_RegSetValueExW
0x18001651e  mov     ebx, eax
0x180016520  test    eax, eax
0x180016522  jle     short loc_18001652D
0x180016524  movzx   ebx, ax
0x180016527  or      ebx, 80070000h
0x18001652d  test    ebx, ebx
0x18001652f  jns     short loc_180016538
0x180016531  mov     edx, 4C5h
0x180016536  jmp     short loc_1800164D1
0x180016538  xor     eax, eax
0x18001653a  mov     rcx, [rsp+268h+var_18]
0x180016542  xor     rcx, rsp; StackCookie
0x180016545  call    __security_check_cookie
0x18001654a  mov     rbx, [rsp+268h+arg_8]
0x180016552  add     rsp, 260h
0x180016559  pop     rdi
0x18001655a  retn
```
