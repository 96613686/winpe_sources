# StorageService::GetMetadataFilePath(_STORAGE_DEVICE_TYPE,ulong,ushort *)

- ea: `0x180023f10`
- end: `0x18002401f`
- name: `?GetMetadataFilePath@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KPEAG@Z`
- size: `271`
- prototype: `HRESULT __fastcall(__int64, int, unsigned int, wchar_t *)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, registry_config, loader_planting, service_task`

## callers

- `0x180024480`
- `0x180029c5c`

## callees

- `0x18000d030`
- `0x180012c9c`
- `0x180023f10`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x180023f6d`
- `ntdll!RtlGetPersistedStateLocation` at `0x180023f6d`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180023fdd`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180023ff3`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180023fdd`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180023ff3`

## pseudocode

```c
HRESULT __fastcall StorageService::GetMetadataFilePath(__int64 a1, int a2, unsigned int a3, wchar_t *a4)
{
  __int64 v5; // rbp
  __int64 v6; // rsi
  int PersistedStateLocation; // eax
  signed int v9; // r11d
  HRESULT result; // eax
  int v11[4]; // [rsp+40h] [rbp-258h] BYREF
  wchar_t v12[264]; // [rsp+50h] [rbp-248h] BYREF

  v5 = a3;
  v6 = a2;
  v11[0] = 520;
  PersistedStateLocation = RtlGetPersistedStateLocation(L"WPSettingsDatID", 0, 0, 1, v12, 520, v11);
  v9 = PersistedStateLocation;
  if ( PersistedStateLocation > 0 )
    v9 = (unsigned __int16)PersistedStateLocation | 0x80070000;
  if ( v9 >= 0 )
  {
    result = StringCchCopyW(a4, 0x104u, v12);
    if ( result < 0 )
      return result;
    return v9;
  }
  if ( v9 != -1073741772 )
    return v9;
  result = StringCchCopyW(a4, 0x104u, (const wchar_t *)(*(_QWORD *)(a1 + 8 * v6 + 40) + 4LL + 1112 * v5));
  if ( result >= 0 )
  {
    result = PathCchAppend(a4, 0x104u, L"System Volume Information");
    if ( result >= 0 )
    {
      result = PathCchAppend(a4, 0x104u, L"WPSettings.dat");
      if ( result >= 0 )
        return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180023f10  push    rbx
0x180023f12  push    rbp
0x180023f13  push    rsi
0x180023f14  push    rdi
0x180023f15  sub     rsp, 278h
0x180023f1c  mov     rax, cs:__security_cookie
0x180023f23  xor     rax, rsp
0x180023f26  mov     [rsp+298h+var_38], rax
0x180023f2e  mov     rbx, rcx
0x180023f31  mov     ebp, r8d
0x180023f34  mov     ecx, 208h
0x180023f39  movsxd  rsi, edx
0x180023f3c  lea     rax, [rsp+298h+var_258]
0x180023f41  mov     [rsp+298h+var_258], ecx
0x180023f45  mov     [rsp+298h+var_268], rax
0x180023f4a  mov     rdi, r9
0x180023f4d  mov     [rsp+298h+var_270], ecx
0x180023f51  lea     rax, [rsp+298h+var_248]
0x180023f56  lea     rcx, aWpsettingsdati; "WPSettingsDatID"
0x180023f5d  mov     [rsp+298h+var_278], rax
0x180023f62  mov     r9d, 1
0x180023f68  xor     r8d, r8d
0x180023f6b  xor     edx, edx
0x180023f6d  call    cs:__imp_RtlGetPersistedStateLocation
0x180023f73  mov     r11d, eax
0x180023f76  test    eax, eax
0x180023f78  jle     short loc_180023F85
0x180023f7a  movzx   r11d, ax
0x180023f7e  or      r11d, 80070000h
0x180023f85  test    r11d, r11d
0x180023f88  js      short loc_180023FA2
0x180023f8a  lea     r8, [rsp+298h+var_248]; wchar_t *
0x180023f8f  mov     edx, 104h; unsigned __int64
0x180023f94  mov     rcx, rdi; wchar_t *
0x180023f97  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180023f9c  test    eax, eax
0x180023f9e  jns     short loc_180024000
0x180023fa0  jmp     short loc_180024003
0x180023fa2  cmp     r11d, 0C0000034h
0x180023fa9  jnz     short loc_180024000
0x180023fab  mov     rax, [rbx+rsi*8+28h]
0x180023fb0  mov     rcx, rdi; wchar_t *
0x180023fb3  add     rax, 4
0x180023fb7  mov     ebx, 104h
0x180023fbc  imul    r8, rbp, 458h
0x180023fc3  mov     edx, ebx; unsigned __int64
0x180023fc5  add     r8, rax; wchar_t *
0x180023fc8  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180023fcd  test    eax, eax
0x180023fcf  js      short loc_180024003
0x180023fd1  lea     r8, aSystemVolumeIn; "System Volume Information"
0x180023fd8  mov     edx, ebx; cchPath
0x180023fda  mov     rcx, rdi; pszPath
0x180023fdd  call    cs:__imp_PathCchAppend
0x180023fe3  test    eax, eax
0x180023fe5  js      short loc_180024003
0x180023fe7  lea     r8, aWpsettingsDat; "WPSettings.dat"
0x180023fee  mov     edx, ebx; cchPath
0x180023ff0  mov     rcx, rdi; pszPath
0x180023ff3  call    cs:__imp_PathCchAppend
0x180023ff9  test    eax, eax
0x180023ffb  js      short loc_180024003
0x180023ffd  xor     r11d, r11d
0x180024000  mov     eax, r11d
0x180024003  mov     rcx, [rsp+298h+var_38]
0x18002400b  xor     rcx, rsp; StackCookie
0x18002400e  call    __security_check_cookie
0x180024013  add     rsp, 278h
0x18002401a  pop     rdi
0x18002401b  pop     rsi
0x18002401c  pop     rbp
0x18002401d  pop     rbx
0x18002401e  retn
```
