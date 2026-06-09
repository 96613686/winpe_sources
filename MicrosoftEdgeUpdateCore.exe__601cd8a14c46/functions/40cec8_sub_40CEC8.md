# sub_40CEC8

- ea: `0x40cec8`
- end: `0x40cf69`
- name: `sub_40CEC8`
- size: `161`
- prototype: `char()`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x40c440`

## callees

- `0x402330`
- `0x40cec8`
- `0x40d08d`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x40cefa`
- `KERNEL32!GetProcAddress` at `0x40cf09`
- `KERNEL32!GetProcAddress` at `0x40cefa`
- `KERNEL32!GetProcAddress` at `0x40cf09`
- `KERNEL32!FreeLibrary` at `0x40cf52`
- `KERNEL32!FreeLibrary` at `0x40cf52`
- `KERNEL32!LoadLibraryExW` at `0x40cee8`
- `KERNEL32!LoadLibraryExW` at `0x40cee8`

## string_xrefs

- `0x40cee3`: `netapi32.dll`

## pseudocode

```c
char sub_40CEC8()
{
  char v0; // bl
  HMODULE Library; // eax
  HMODULE v2; // esi
  FARPROC NetFreeAadJoinInformation; // edi
  FARPROC NetGetAadJoinInformation; // [esp+Ch] [ebp-10h]
  int v6; // [esp+14h] [ebp-8h] BYREF

  v0 = 0;
  Library = LoadLibraryExW(L"netapi32.dll", 0, 0x800u);
  v2 = Library;
  if ( Library )
  {
    NetGetAadJoinInformation = GetProcAddress(Library, "NetGetAadJoinInformation");
    NetFreeAadJoinInformation = GetProcAddress(v2, "NetFreeAadJoinInformation");
    if ( NetGetAadJoinInformation && NetFreeAadJoinInformation )
    {
      v6 = 0;
      if ( ((int (__thiscall *)(FARPROC, const wchar_t *, int *))NetGetAadJoinInformation)(
             NetGetAadJoinInformation,
             L"72f988bf-86f1-41af-91ab-2d7cd011db47",
             &v6) < 0
        || !v6 )
      {
        goto LABEL_8;
      }
      ((void (__thiscall *)(FARPROC, int))NetFreeAadJoinInformation)(NetFreeAadJoinInformation, v6);
      v0 = 1;
    }
    if ( v2 )
LABEL_8:
      FreeLibrary(v2);
  }
  return v0;
}

```

## disassembly

```asm
0x40cec8  push    ebp
0x40cec9  mov     ebp, esp
0x40cecb  sub     esp, 10h
0x40cece  mov     eax, ___security_cookie
0x40ced3  xor     eax, ebp
0x40ced5  mov     [ebp+var_4], eax
0x40ced8  push    ebx
0x40ced9  push    esi
0x40ceda  push    edi
0x40cedb  push    800h; dwFlags
0x40cee0  xor     ebx, ebx
0x40cee2  push    ebx; hFile
0x40cee3  push    offset LibFileName; "netapi32.dll"
0x40cee8  call    ds:LoadLibraryExW
0x40ceee  mov     esi, eax
0x40cef0  test    esi, esi
0x40cef2  jz      short loc_40CF58
0x40cef4  push    offset aNetgetaadjoini; "NetGetAadJoinInformation"
0x40cef9  push    esi; hModule
0x40cefa  call    ds:GetProcAddress
0x40cf00  push    offset aNetfreeaadjoin; "NetFreeAadJoinInformation"
0x40cf05  push    esi; hModule
0x40cf06  mov     [ebp+var_10], eax
0x40cf09  call    ds:GetProcAddress
0x40cf0f  mov     edi, eax
0x40cf11  mov     eax, [ebp+var_10]
0x40cf14  test    eax, eax
0x40cf16  jz      short loc_40CF4D
0x40cf18  test    edi, edi
0x40cf1a  jz      short loc_40CF4D
0x40cf1c  lea     ecx, [ebp+var_8]
0x40cf1f  mov     [ebp+var_8], ebx
0x40cf22  push    ecx
0x40cf23  push    offset a72f988bf86f141; "72f988bf-86f1-41af-91ab-2d7cd011db47"
0x40cf28  mov     ecx, eax
0x40cf2a  call    ds:___guard_check_icall_fptr
0x40cf30  mov     eax, [ebp+var_10]
0x40cf33  call    eax
0x40cf35  test    eax, eax
0x40cf37  js      short loc_40CF51
0x40cf39  cmp     [ebp+var_8], ebx
0x40cf3c  jz      short loc_40CF51
0x40cf3e  push    [ebp+var_8]
0x40cf41  mov     ecx, edi
0x40cf43  call    ds:___guard_check_icall_fptr
0x40cf49  call    edi
0x40cf4b  mov     bl, 1
0x40cf4d  test    esi, esi
0x40cf4f  jz      short loc_40CF58
0x40cf51  push    esi; hLibModule
0x40cf52  call    ds:FreeLibrary
0x40cf58  mov     ecx, [ebp+var_4]
0x40cf5b  mov     al, bl
0x40cf5d  pop     edi
0x40cf5e  pop     esi
0x40cf5f  xor     ecx, ebp; StackCookie
0x40cf61  pop     ebx
0x40cf62  call    @__security_check_cookie@4; __security_check_cookie(x)
0x40cf67  leave
0x40cf68  retn
```
