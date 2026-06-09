# SetAutoUpdateState(WindowsUpdate::Internal::AutoUpdateState)

- ea: `0x180028ac4`
- end: `0x180028b3b`
- name: `?SetAutoUpdateState@@YAJW4AutoUpdateState@Internal@WindowsUpdate@@@Z`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180020a1c`

## callees

- `0x180028ac4`
- `0x180029190`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180028b24`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180028b24`

## string_xrefs

- `0x180028aeb`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsStore\WindowsUpdate`

## pseudocode

```c
LSTATUS __fastcall SetAutoUpdateState(int a1)
{
  LSTATUS result; // eax
  int v2; // eax
  const WCHAR *RegistryLocation; // rax
  int Data; // [rsp+40h] [rbp+8h] BYREF

  if ( a1 == 1 || (result = -2147024809, !a1) )
  {
    v2 = 4;
    if ( a1 != 1 )
      v2 = 2;
    Data = v2;
    RegistryLocation = (const WCHAR *)_InitOnceAndGetRegistryLocation(
                                        &qword_18006A468,
                                        L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsStore\\WindowsUpdate");
    result = RegSetKeyValueW(HKEY_LOCAL_MACHINE, RegistryLocation, L"AutoDownload", 4u, &Data, 4u);
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180028ac4  sub     rsp, 38h
0x180028ac8  cmp     ecx, 1
0x180028acb  jz      short loc_180028AD6
0x180028acd  mov     eax, 80070057h
0x180028ad2  test    ecx, ecx
0x180028ad4  jnz     short loc_180028B36
0x180028ad6  mov     eax, 4
0x180028adb  cmp     ecx, 1
0x180028ade  lea     rcx, qword_18006A468
0x180028ae5  lea     edx, [rax-2]
0x180028ae8  cmovnz  eax, edx
0x180028aeb  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180028af2  mov     [rsp+38h+Data], eax
0x180028af6  call    ?_InitOnceAndGetRegistryLocation@@YAPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; _InitOnceAndGetRegistryLocation(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *)
0x180028afb  lea     rcx, [rsp+38h+Data]
0x180028b00  mov     [rsp+38h+cbData], 4; cbData
0x180028b08  mov     [rsp+38h+lpData], rcx; lpData
0x180028b0d  lea     r8, aAutodownload; "AutoDownload"
0x180028b14  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180028b1b  mov     r9d, 4; dwType
0x180028b21  mov     rdx, rax; lpSubKey
0x180028b24  call    cs:__imp_RegSetKeyValueW
0x180028b2a  test    eax, eax
0x180028b2c  jle     short loc_180028B36
0x180028b2e  movzx   eax, ax
0x180028b31  or      eax, 80070000h
0x180028b36  add     rsp, 38h
0x180028b3a  retn
```
