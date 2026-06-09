# wil::reg::create_unique_key_nothrow(HKEY__ *,wchar_t const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)

- ea: `0x1800472d8`
- end: `0x180047374`
- name: `?create_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEB_WAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z`
- size: `156`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18003cfc8`
- `0x18005acac`
- `0x180062ba8`

## callees

- `0x1800472d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800472f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800472f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180047306`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180047306`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800472fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800472fe`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180047359`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180047359`

## pseudocode

```c
LSTATUS __fastcall wil::reg::create_unique_key_nothrow(__int64 a1, const WCHAR *a2, HKEY *a3, DWORD a4)
{
  HKEY v4; // rsi
  DWORD LastError; // ebx
  LSTATUS result; // eax
  DWORD dwDisposition; // [rsp+98h] [rbp+20h] BYREF

  dwDisposition = a4;
  v4 = *a3;
  if ( *a3 )
  {
    LastError = GetLastError();
    RegCloseKey(v4);
    SetLastError(LastError);
  }
  *a3 = 0;
  dwDisposition = 0;
  result = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0, 0, 0xF003Fu, 0, a3, &dwDisposition);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800472d8  mov     [rsp+dwDisposition], r9d
0x1800472dd  push    rbx
0x1800472de  push    rbp
0x1800472df  push    rsi
0x1800472e0  push    rdi
0x1800472e1  sub     rsp, 58h
0x1800472e5  mov     rsi, [r8]
0x1800472e8  mov     rdi, r8
0x1800472eb  mov     rbp, rdx
0x1800472ee  test    rsi, rsi
0x1800472f1  jz      short loc_18004730C
0x1800472f3  call    cs:__imp_GetLastError
0x1800472f9  mov     rcx, rsi; hKey
0x1800472fc  mov     ebx, eax
0x1800472fe  call    cs:__imp_RegCloseKey
0x180047304  mov     ecx, ebx; dwErrCode
0x180047306  call    cs:__imp_SetLastError
0x18004730c  lea     rax, [rsp+78h+dwDisposition]
0x180047314  mov     qword ptr [rdi], 0
0x18004731b  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x180047320  xor     r9d, r9d; lpClass
0x180047323  mov     [rsp+78h+phkResult], rdi; phkResult
0x180047328  xor     r8d, r8d; Reserved
0x18004732b  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180047334  mov     rdx, rbp; lpSubKey
0x180047337  mov     [rsp+78h+samDesired], 0F003Fh; samDesired
0x18004733f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180047346  mov     [rsp+78h+dwOptions], 0; dwOptions
0x18004734e  mov     [rsp+78h+dwDisposition], 0
0x180047359  call    cs:__imp_RegCreateKeyExW
0x18004735f  test    eax, eax
0x180047361  jle     short loc_18004736B
0x180047363  movzx   eax, ax
0x180047366  or      eax, 80070000h
0x18004736b  add     rsp, 58h
0x18004736f  pop     rdi
0x180047370  pop     rsi
0x180047371  pop     rbp
0x180047372  pop     rbx
0x180047373  retn
```
