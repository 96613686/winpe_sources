# SupportedFileTypes::InitializeCodecAvailableList(SupportedFileTypes::StringLinkedList *)

- ea: `0x180072134`
- end: `0x1800722c7`
- name: `?InitializeCodecAvailableList@SupportedFileTypes@@AEAAJPEAVStringLinkedList@1@@Z`
- size: `403`
- prototype: `int(SupportedFileTypes *__hidden this, struct SupportedFileTypes::StringLinkedList *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180072504`

## callees

- `0x180007040`
- `0x18002fc0c`
- `0x18003f800`
- `0x180040264`
- `0x180072134`

## import_xrefs

- `ADVAPI32!RegEnumValueW` at `0x180072240`
- `ADVAPI32!RegEnumValueW` at `0x180072240`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800721de`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800721de`
- `ADVAPI32!RegCloseKey` at `0x180072285`
- `ADVAPI32!RegCloseKey` at `0x180072285`
- `ADVAPI32!RegOpenKeyExW` at `0x18007218e`
- `ADVAPI32!RegOpenKeyExW` at `0x18007218e`

## pseudocode

```c
__int64 __fastcall SupportedFileTypes::InitializeCodecAvailableList(
        SupportedFileTypes *this,
        struct SupportedFileTypes::StringLinkedList *a2)
{
  LSTATUS v3; // eax
  LSTATUS v4; // eax
  int v5; // ebx
  DWORD i; // edi
  LSTATUS v7; // eax
  DWORD cValues; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchValueName[4]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR ValueName[264]; // [rsp+80h] [rbp-80h] BYREF

  hKey = 0;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows Photo Viewer\\AvailableDownloadableCodecs",
         0,
         0x20019u,
         &hKey);
  if ( v3 )
  {
    if ( v3 == 2 )
      return 0;
    else
      return (unsigned int)GetResultFromKnownLastError();
  }
  else
  {
    cValues = 260;
    v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0);
    v5 = v4;
    if ( v4 )
    {
      if ( v4 > 0 )
        v5 = (unsigned __int16)v4 | 0x80070000;
    }
    else
    {
      v5 = 0;
      for ( i = 0; i < cValues; ++i )
      {
        if ( v5 < 0 )
          break;
        memset_0(ValueName, 0, 0x208u);
        cchValueName[0] = 260;
        v7 = RegEnumValueW(hKey, i, ValueName, cchValueName, 0, 0, 0, 0);
        v5 = v7;
        if ( v7 )
        {
          if ( v7 > 0 )
            v5 = (unsigned __int16)v7 | 0x80070000;
        }
        else
        {
          v5 = SupportedFileTypes::StringLinkedList::Add(a2, ValueName, 4);
        }
      }
    }
    RegCloseKey(hKey);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180072134  mov     [rsp-8+arg_0], rbx
0x180072139  mov     [rsp-8+arg_10], rsi
0x18007213e  push    rbp
0x18007213f  push    rdi
0x180072140  push    r14
0x180072142  lea     rbp, [rsp-1A0h]
0x18007214a  sub     rsp, 2A0h
0x180072151  mov     rax, cs:__security_cookie
0x180072158  xor     rax, rsp
0x18007215b  mov     [rbp+1B0h+var_20], rax
0x180072162  mov     rsi, rdx
0x180072165  lea     rax, [rsp+2B0h+hKey]
0x18007216a  xor     r14d, r14d
0x18007216d  mov     [rsp+2B0h+phkResult], rax; phkResult
0x180072172  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows Photo View"...
0x180072179  mov     [rsp+2B0h+hKey], r14
0x18007217e  mov     r9d, 20019h; samDesired
0x180072184  xor     r8d, r8d; ulOptions
0x180072187  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007218e  call    cs:__imp_RegOpenKeyExW
0x180072194  test    eax, eax
0x180072196  jnz     loc_18007228D
0x18007219c  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800721a1  lea     rax, [rsp+2B0h+cValues]
0x1800721a6  mov     [rsp+2B0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1800721ab  xor     r9d, r9d; lpReserved
0x1800721ae  mov     [rsp+2B0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x1800721b3  xor     r8d, r8d; lpcchClass
0x1800721b6  mov     [rsp+2B0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x1800721bb  xor     edx, edx; lpClass
0x1800721bd  mov     [rsp+2B0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x1800721c2  mov     [rsp+2B0h+lpcValues], rax; lpcValues
0x1800721c7  mov     [rsp+2B0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x1800721cc  mov     [rsp+2B0h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x1800721d1  mov     [rsp+2B0h+phkResult], r14; lpcSubKeys
0x1800721d6  mov     [rsp+2B0h+cValues], 104h
0x1800721de  call    cs:__imp_RegQueryInfoKeyW
0x1800721e4  mov     ebx, eax
0x1800721e6  test    eax, eax
0x1800721e8  jnz     loc_180072275
0x1800721ee  mov     ebx, r14d
0x1800721f1  mov     edi, r14d
0x1800721f4  cmp     [rsp+2B0h+cValues], r14d
0x1800721f9  jbe     loc_180072280
0x1800721ff  test    ebx, ebx
0x180072201  js      short loc_180072280
0x180072203  xor     edx, edx; Val
0x180072205  lea     rcx, [rbp+1B0h+ValueName]; void *
0x180072209  mov     r8d, 208h; Size
0x18007220f  call    memset_0
0x180072214  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180072219  lea     r9, [rsp+2B0h+cchValueName]; lpcchValueName
0x18007221e  mov     [rsp+2B0h+lpcValues], r14; lpcbData
0x180072223  lea     r8, [rbp+1B0h+ValueName]; lpValueName
0x180072227  mov     [rsp+2B0h+lpcbMaxClassLen], r14; lpData
0x18007222c  mov     edx, edi; dwIndex
0x18007222e  mov     [rsp+2B0h+lpcbMaxSubKeyLen], r14; lpType
0x180072233  mov     [rsp+2B0h+phkResult], r14; lpReserved
0x180072238  mov     [rsp+2B0h+cchValueName], 104h
0x180072240  call    cs:__imp_RegEnumValueW
0x180072246  mov     ebx, eax
0x180072248  test    eax, eax
0x18007224a  jnz     short loc_180072260
0x18007224c  lea     r8d, [rax+4]; unsigned int
0x180072250  mov     rcx, rsi; this
0x180072253  lea     rdx, [rbp+1B0h+ValueName]; unsigned __int16 *
0x180072257  call    ?Add@StringLinkedList@SupportedFileTypes@@QEAAJPEBGK@Z; SupportedFileTypes::StringLinkedList::Add(ushort const *,ulong)
0x18007225c  mov     ebx, eax
0x18007225e  jmp     short loc_18007226B
0x180072260  jle     short loc_18007226B
0x180072262  movzx   ebx, ax
0x180072265  or      ebx, 80070000h
0x18007226b  inc     edi
0x18007226d  cmp     edi, [rsp+2B0h+cValues]
0x180072271  jb      short loc_1800721FF
0x180072273  jmp     short loc_180072280
0x180072275  jle     short loc_180072280
0x180072277  movzx   ebx, ax
0x18007227a  or      ebx, 80070000h
0x180072280  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180072285  call    cs:__imp_RegCloseKey
0x18007228b  jmp     short loc_18007229E
0x18007228d  cmp     eax, 2
0x180072290  jnz     short loc_180072297
0x180072292  mov     ebx, r14d
0x180072295  jmp     short loc_18007229E
0x180072297  call    GetResultFromKnownLastError
0x18007229c  mov     ebx, eax
0x18007229e  mov     eax, ebx
0x1800722a0  mov     rcx, [rbp+1B0h+var_20]
0x1800722a7  xor     rcx, rsp; StackCookie
0x1800722aa  call    __security_check_cookie
0x1800722af  lea     r11, [rsp+2B0h+var_10]
0x1800722b7  mov     rbx, [r11+20h]
0x1800722bb  mov     rsi, [r11+30h]
0x1800722bf  mov     rsp, r11
0x1800722c2  pop     r14
0x1800722c4  pop     rdi
0x1800722c5  pop     rbp
0x1800722c6  retn
```
