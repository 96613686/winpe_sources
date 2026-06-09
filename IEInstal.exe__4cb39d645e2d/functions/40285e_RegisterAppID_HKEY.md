# RegisterAppID(HKEY__ *)

- ea: `0x40285e`
- end: `0x402912`
- name: `?RegisterAppID@@YGKPAUHKEY__@@@Z`
- size: `180`
- prototype: `LSTATUS __thiscall(HKEY this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x409551`

## callees

- `0x40285e`
- `0x40cb60`
- `0x40eb27`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x40289d`
- `ADVAPI32!RegDeleteValueW` at `0x40289d`
- `ADVAPI32!RegSetValueExW` at `0x4028f6`
- `ADVAPI32!RegSetValueExW` at `0x4028f6`
- `KERNEL32!GetModuleHandleW` at `0x4028b5`
- `KERNEL32!GetModuleHandleW` at `0x4028b5`
- `KERNEL32!GetLastError` at `0x4028fe`
- `KERNEL32!GetLastError` at `0x4028fe`
- `USER32!LoadStringW` at `0x4028bc`
- `USER32!LoadStringW` at `0x4028bc`

## pseudocode

```c
LSTATUS __thiscall RegisterAppID(HKEY this)
{
  HMODULE ModuleHandleW; // eax
  WCHAR Buffer[256]; // [esp+8h] [ebp-204h] BYREF

  memset(Buffer, 0, sizeof(Buffer));
  RegDeleteValueW(this, L"RunAs");
  ModuleHandleW = GetModuleHandleW(0);
  if ( LoadStringW(ModuleHandleW, 0x3E9u, Buffer, 256) <= 0 )
    return GetLastError();
  else
    return RegSetValueExW(this, &Data, 0, 1u, (const BYTE *)Buffer, 2 * wcslen(Buffer) + 2);
}

```

## disassembly

```asm
0x40285e  mov     edi, edi
0x402860  push    ebp
0x402861  mov     ebp, esp
0x402863  sub     esp, 204h
0x402869  mov     eax, ___security_cookie
0x40286e  xor     eax, ebp
0x402870  mov     [ebp+var_4], eax
0x402873  push    esi
0x402874  push    edi
0x402875  xor     eax, eax
0x402877  xor     edi, edi
0x402879  push    1FEh; Size
0x40287e  mov     [ebp+Buffer], ax
0x402885  mov     esi, ecx
0x402887  lea     eax, [ebp+var_202]
0x40288d  push    edi; Val
0x40288e  push    eax; void *
0x40288f  call    _memset
0x402894  add     esp, 0Ch
0x402897  push    offset ValueName; "RunAs"
0x40289c  push    esi; hKey
0x40289d  call    ds:__imp__RegDeleteValueW@8; RegDeleteValueW(x,x)
0x4028a3  push    100h; cchBufferMax
0x4028a8  lea     eax, [ebp+Buffer]
0x4028ae  push    eax; lpBuffer
0x4028af  push    3E9h; uID
0x4028b4  push    edi; lpModuleName
0x4028b5  call    ds:__imp__GetModuleHandleW@4; GetModuleHandleW(x)
0x4028bb  push    eax; hInstance
0x4028bc  call    ds:__imp__LoadStringW@16; LoadStringW(x,x,x,x)
0x4028c2  test    eax, eax
0x4028c4  jle     short loc_4028FE
0x4028c6  lea     ecx, [ebp+Buffer]
0x4028cc  lea     edx, [ecx+2]
0x4028cf  mov     ax, [ecx]
0x4028d2  add     ecx, 2
0x4028d5  cmp     ax, di
0x4028d8  jnz     short loc_4028CF
0x4028da  sub     ecx, edx
0x4028dc  sar     ecx, 1
0x4028de  lea     eax, ds:2[ecx*2]
0x4028e5  push    eax; cbData
0x4028e6  lea     eax, [ebp+Buffer]
0x4028ec  push    eax; lpData
0x4028ed  push    1; dwType
0x4028ef  push    edi; Reserved
0x4028f0  push    offset Data; lpValueName
0x4028f5  push    esi; hKey
0x4028f6  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x4028fc  jmp     short loc_402904
0x4028fe  call    ds:__imp__GetLastError@0; GetLastError()
0x402904  mov     ecx, [ebp+var_4]
0x402907  pop     edi
0x402908  xor     ecx, ebp; StackCookie
0x40290a  pop     esi
0x40290b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x402910  leave
0x402911  retn
```
