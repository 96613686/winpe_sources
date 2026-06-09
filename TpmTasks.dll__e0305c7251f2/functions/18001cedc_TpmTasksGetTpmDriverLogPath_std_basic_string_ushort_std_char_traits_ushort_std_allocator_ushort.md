# TpmTasksGetTpmDriverLogPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001cedc`
- end: `0x18001d0cc`
- name: `?TpmTasksGetTpmDriverLogPath@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `496`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800166dc`
- `0x18001c930`

## callees

- `0x1800078b0`
- `0x1800085bc`
- `0x1800085d4`
- `0x18000d524`
- `0x18000eb18`
- `0x18001be20`
- `0x18001cedc`
- `0x18002386c`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x18001cf90`
- `ntdll!RtlGetPersistedStateLocation` at `0x18001d06b`
- `ntdll!RtlGetPersistedStateLocation` at `0x18001cf90`
- `ntdll!RtlGetPersistedStateLocation` at `0x18001d06b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cfae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cfae`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001d00a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001d00a`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18001cfa4`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18001cfa4`

## string_xrefs

- `0x18001cf6d`: `SYSTEM\CurrentControlSet\Services\Tpm`
- `0x18001cfda`: `WBCLPath`
- `0x18001d064`: `TpmDriverLogPath`

## pseudocode

```c
__int64 __fastcall TpmTasksGetTpmDriverLogPath(__int64 a1)
{
  signed int LastError; // eax
  unsigned int v3; // ebx
  __int64 v4; // rax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  int v7; // [rsp+44h] [rbp-BCh] BYREF
  _BYTE v8[40]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v9[264]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE Src[528]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR Buffer; // [rsp+490h] [rbp+390h] BYREF
  _BYTE v12[526]; // [rsp+492h] [rbp+392h] BYREF
  WCHAR SubKey[264]; // [rsp+6A0h] [rbp+5A0h] BYREF

  Buffer = 0;
  memset_0(v12, 0, 0x206u);
  memset_0(v9, 0, 0x208u);
  memset_0(Src, 0, 0x208u);
  pcbData = 0;
  memset_0(SubKey, 0, 0x208u);
  v7 = 520;
  RtlGetPersistedStateLocation(L"TpmRegDriverTpm", 0, L"SYSTEM\\CurrentControlSet\\Services\\Tpm", 0, SubKey, 520, &v7);
  if ( GetWindowsDirectoryW(&Buffer, 0x104u) )
  {
    pcbData = 520;
    if ( RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"WBCLPath", 2u, 0, Src, &pcbData) )
    {
      v3 = StringCchPrintfW(v9, 0x104u, L"%s\\Logs\\MeasuredBoot", &Buffer);
      if ( (v3 & 0x80000000) != 0 )
        return v3;
      pcbData = 520;
      if ( (unsigned int)RtlGetPersistedStateLocation(L"TpmDriverLogPath", 0, v9, 1, Src, 520, &pcbData) )
      {
LABEL_9:
        v4 = std::wstring::wstring((__int64)v8, (__int64)v9);
        std::wstring::operator=(a1, v4);
        std::wstring::_Tidy_deallocate(v8);
        return v3;
      }
    }
    else
    {
      v3 = 0;
    }
    memcpy_0(v9, Src, pcbData);
    goto LABEL_9;
  }
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return v3;
}

```

## disassembly

```asm
0x18001cedc  push    rbp
0x18001cede  push    rbx
0x18001cedf  push    rsi
0x18001cee0  push    rdi
0x18001cee1  lea     rbp, [rsp-7C8h]
0x18001cee9  sub     rsp, 8C8h
0x18001cef0  mov     rax, cs:__security_cookie
0x18001cef7  xor     rax, rsp
0x18001cefa  mov     [rbp+7E0h+var_30], rax
0x18001cf01  mov     rdi, rcx
0x18001cf04  xor     eax, eax
0x18001cf06  lea     rcx, [rbp+7E0h+var_44E]; void *
0x18001cf0d  mov     [rbp+7E0h+Buffer], ax
0x18001cf14  xor     edx, edx; Val
0x18001cf16  mov     r8d, 206h; Size
0x18001cf1c  call    memset_0
0x18001cf21  mov     esi, 208h
0x18001cf26  lea     rcx, [rsp+8E0h+var_870]; void *
0x18001cf2b  mov     r8d, esi; Size
0x18001cf2e  xor     edx, edx; Val
0x18001cf30  call    memset_0
0x18001cf35  mov     r8d, esi; Size
0x18001cf38  lea     rcx, [rbp+7E0h+Src]; void *
0x18001cf3f  xor     edx, edx; Val
0x18001cf41  call    memset_0
0x18001cf46  mov     r8d, esi; Size
0x18001cf49  mov     [rsp+8E0h+var_8A0], 0
0x18001cf51  xor     edx, edx; Val
0x18001cf53  lea     rcx, [rbp+7E0h+SubKey]; void *
0x18001cf5a  call    memset_0
0x18001cf5f  lea     rax, [rsp+8E0h+var_89C]
0x18001cf64  mov     [rsp+8E0h+var_89C], esi
0x18001cf68  mov     [rsp+8E0h+pcbData], rax
0x18001cf6d  lea     r8, aSystemCurrentc_23; "SYSTEM\\CurrentControlSet\\Services\\Tp"...
0x18001cf74  lea     rax, [rbp+7E0h+SubKey]
0x18001cf7b  mov     dword ptr [rsp+8E0h+pvData], esi
0x18001cf7f  xor     r9d, r9d
0x18001cf82  mov     [rsp+8E0h+pdwType], rax
0x18001cf87  xor     edx, edx
0x18001cf89  lea     rcx, aTpmregdrivertp; "TpmRegDriverTpm"
0x18001cf90  call    cs:__imp_RtlGetPersistedStateLocation
0x18001cf96  mov     ebx, 104h
0x18001cf9b  lea     rcx, [rbp+7E0h+Buffer]; lpBuffer
0x18001cfa2  mov     edx, ebx; uSize
0x18001cfa4  call    cs:__imp_GetWindowsDirectoryW
0x18001cfaa  test    eax, eax
0x18001cfac  jnz     short loc_18001CFCC
0x18001cfae  call    cs:__imp_GetLastError
0x18001cfb4  mov     ebx, eax
0x18001cfb6  test    eax, eax
0x18001cfb8  jle     loc_18001D0AF
0x18001cfbe  movzx   ebx, ax
0x18001cfc1  or      ebx, 80070000h
0x18001cfc7  jmp     loc_18001D0AF
0x18001cfcc  lea     rax, [rsp+8E0h+var_8A0]
0x18001cfd1  mov     [rsp+8E0h+var_8A0], esi
0x18001cfd5  mov     [rsp+8E0h+pcbData], rax; pcbData
0x18001cfda  lea     r8, aWbclpath; "WBCLPath"
0x18001cfe1  lea     rax, [rbp+7E0h+Src]
0x18001cfe8  mov     r9d, 2; dwFlags
0x18001cfee  mov     [rsp+8E0h+pvData], rax; pvData
0x18001cff3  lea     rdx, [rbp+7E0h+SubKey]; lpSubKey
0x18001cffa  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001d001  mov     [rsp+8E0h+pdwType], 0; pdwType
0x18001d00a  call    cs:__imp_RegGetValueW
0x18001d010  lea     rcx, [rsp+8E0h+var_870]; unsigned __int16 *
0x18001d015  test    eax, eax
0x18001d017  jnz     short loc_18001D01D
0x18001d019  xor     ebx, ebx
0x18001d01b  jmp     short loc_18001D07A
0x18001d01d  lea     r9, [rbp+7E0h+Buffer]
0x18001d024  mov     rdx, rbx; unsigned __int64
0x18001d027  lea     r8, aSLogsMeasuredb; "%s\\Logs\\MeasuredBoot"
0x18001d02e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001d033  mov     ebx, eax
0x18001d035  test    eax, eax
0x18001d037  js      short loc_18001D0AF
0x18001d039  lea     rax, [rsp+8E0h+var_8A0]
0x18001d03e  mov     [rsp+8E0h+var_8A0], esi
0x18001d042  mov     [rsp+8E0h+pcbData], rax
0x18001d047  lea     r8, [rsp+8E0h+var_870]
0x18001d04c  lea     rax, [rbp+7E0h+Src]
0x18001d053  mov     dword ptr [rsp+8E0h+pvData], esi
0x18001d057  mov     r9d, 1
0x18001d05d  mov     [rsp+8E0h+pdwType], rax
0x18001d062  xor     edx, edx
0x18001d064  lea     rcx, aTpmdriverlogpa; "TpmDriverLogPath"
0x18001d06b  call    cs:__imp_RtlGetPersistedStateLocation
0x18001d071  test    eax, eax
0x18001d073  jnz     short loc_18001D08B
0x18001d075  lea     rcx, [rsp+8E0h+var_870]; void *
0x18001d07a  mov     r8d, [rsp+8E0h+var_8A0]; Size
0x18001d07f  lea     rdx, [rbp+7E0h+Src]; Src
0x18001d086  call    memcpy_0
0x18001d08b  lea     rdx, [rsp+8E0h+var_870]
0x18001d090  lea     rcx, [rsp+8E0h+var_898]
0x18001d095  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001d09a  mov     rdx, rax
0x18001d09d  mov     rcx, rdi
0x18001d0a0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001d0a5  lea     rcx, [rsp+8E0h+var_898]
0x18001d0aa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d0af  mov     eax, ebx
0x18001d0b1  mov     rcx, [rbp+7E0h+var_30]
0x18001d0b8  xor     rcx, rsp; StackCookie
0x18001d0bb  call    __security_check_cookie
0x18001d0c0  add     rsp, 8C8h
0x18001d0c7  pop     rdi
0x18001d0c8  pop     rsi
0x18001d0c9  pop     rbx
0x18001d0ca  pop     rbp
0x18001d0cb  retn
```
